import pandas as pd
import re
from datetime import datetime

data = pd.read_csv('../user_taglist.csv')

class RegTaglist:
    
    def __init__(self):
        self.pattern = None
        self.x = None
        self.public_var()
        
    def public_var(self):
        self.pattern = re.compile(r'\d+')
        
    
    def get_features(self, data):
        self.user_id = data.user_id.iloc[0]
        self.taglist = data.taglist.iloc[0]
        result_dic = {}
        result_dic['user_id'] = self.user_id
        tag_list = self.pattern.findall(self.taglist)
        for i in tag_list:
             result_dic['x_'+i] = 1
        result_dic['sum_x'] = len(tag_list)
        result_df = pd.DataFrame(result_dic, index=[0])
        self.x = result_df
        return self.x

reg_taglist = RegTaglist()
df = pd.DataFrame()
reg_taglist = RegTaglist()
for i in range(1000):
    df = pd.concat([df,reg_taglist.get_features(data[i:i+1])],axis=0,sort=False, sort=True)
