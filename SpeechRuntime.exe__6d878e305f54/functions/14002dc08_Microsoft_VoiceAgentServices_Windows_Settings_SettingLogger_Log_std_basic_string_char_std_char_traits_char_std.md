# Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::Log(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,int,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,void const *)

- ea: `0x14002dc08`
- end: `0x14002dded`
- name: `?Log@SettingLogger@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@00H0PEBX@Z`
- size: `485`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002de00`
- `0x14002dfa0`
- `0x14002e0a0`
- `0x14002e1a0`
- `0x14002e2a0`
- `0x14002e3a0`
- `0x14002e470`
- `0x14002e580`
- `0x14002e690`

## callees

- `0x140002d30`
- `0x140021658`
- `0x1400243ec`
- `0x14002cf68`
- `0x14002cf84`
- `0x14002d144`
- `0x14002d6fc`
- `0x14002da00`
- `0x14002f1b4`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x14002dcc9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x14002dcc9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x14002dc95`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x14002dd0b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x14002dc95`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x14002dd0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::Log(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v22[16]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[232]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v26[8]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v27[232]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v28[3]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v29[32]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v30[32]; // [rsp+268h] [rbp+168h] BYREF

  v28[0] = a2;
  v28[1] = a4;
  v28[2] = a6;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v25);
  v10 = std::operator<<<char>(v26, a2);
  v11 = std::operator<<<std::char_traits<char>>(v10, " 0x");
  v12 = std::ostream::operator<<(v11, a7);
  v13 = std::operator<<<std::char_traits<char>>(v12, " ");
  v14 = std::operator<<<char>(v13, a4);
  v15 = std::operator<<<std::char_traits<char>>(v14, " @ ");
  v16 = std::ostream::operator<<(v15, a5);
  v17 = std::operator<<<std::char_traits<char>>(v16, " ");
  std::operator<<<char>(v17, a6);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v22);
  v18 = std::operator<<<std::char_traits<char>>(v23, "0x");
  std::ostream::operator<<(v18, a7);
  std::stringbuf::str(v24, v30);
  v20 = std::_String_val<std::_Simple_types<char>>::_Myptr(v30);
  std::stringbuf::str(v27, v29);
  v21 = std::_String_val<std::_Simple_types<char>>::_Myptr(v29);
  v28[0] = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingTrace<char *,char *,char *>(
    v28,
    &v21,
    &v20);
  std::string::~string(v29);
  std::string::~string(v30);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v22);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v25);
  std::string::~string(a2);
  std::string::~string(a3);
  std::string::~string(a4);
  return std::string::~string(a6);
}

```

## disassembly

```asm
0x14002dc08  push    rbp
0x14002dc0a  push    rbx
0x14002dc0b  push    rsi
0x14002dc0c  push    rdi
0x14002dc0d  push    r12
0x14002dc0f  push    r14
0x14002dc11  push    r15
0x14002dc13  lea     rbp, [rsp-190h]
0x14002dc1b  sub     rsp, 290h
0x14002dc22  mov     rax, cs:__security_cookie
0x14002dc29  xor     rax, rsp
0x14002dc2c  mov     [rbp+1C0h+var_38], rax
0x14002dc33  mov     r12, r9
0x14002dc36  mov     r15, r8
0x14002dc39  mov     r14, rdx
0x14002dc3c  mov     [rbp+1C0h+var_90], rdx
0x14002dc43  mov     [rsp+2C0h+var_298], r8
0x14002dc48  mov     [rbp+1C0h+var_88], r9
0x14002dc4f  mov     ebx, [rbp+1C0h+arg_20]
0x14002dc55  mov     rsi, [rbp+1C0h+arg_28]
0x14002dc5c  mov     [rbp+1C0h+var_80], rsi
0x14002dc63  mov     rdi, [rbp+1C0h+arg_30]
0x14002dc6a  lea     rcx, [rbp+1C0h+var_190]
0x14002dc6e  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x14002dc73  nop
0x14002dc74  mov     rdx, r14
0x14002dc77  lea     rcx, [rbp+1C0h+var_180]
0x14002dc7b  call    ??$?6DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<<char>(std::ostream &,std::string const &)
0x14002dc80  mov     rcx, rax
0x14002dc83  lea     rdx, a0x_0; " 0x"
0x14002dc8a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002dc8f  mov     rdx, rdi
0x14002dc92  mov     rcx, rax
0x14002dc95  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z; std::ostream::operator<<(void const *)
0x14002dc9b  mov     rcx, rax
0x14002dc9e  lea     rdx, asc_140040764; " "
0x14002dca5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002dcaa  mov     rdx, r12
0x14002dcad  mov     rcx, rax
0x14002dcb0  call    ??$?6DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<<char>(std::ostream &,std::string const &)
0x14002dcb5  mov     rcx, rax
0x14002dcb8  lea     rdx, asc_14004074C; " @ "
0x14002dcbf  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002dcc4  mov     edx, ebx
0x14002dcc6  mov     rcx, rax
0x14002dcc9  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x14002dccf  mov     rcx, rax
0x14002dcd2  lea     rdx, asc_140040764; " "
0x14002dcd9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002dcde  mov     rdx, rsi
0x14002dce1  mov     rcx, rax
0x14002dce4  call    ??$?6DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<<char>(std::ostream &,std::string const &)
0x14002dce9  lea     rcx, [rsp+2C0h+var_290]
0x14002dcee  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x14002dcf3  nop
0x14002dcf4  lea     rdx, a0x; "0x"
0x14002dcfb  lea     rcx, [rsp+2C0h+var_280]
0x14002dd00  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002dd05  mov     rdx, rdi
0x14002dd08  mov     rcx, rax
0x14002dd0b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z; std::ostream::operator<<(void const *)
0x14002dd11  lea     rdx, [rbp+1C0h+var_58]
0x14002dd18  lea     rcx, [rsp+2C0h+var_278]
0x14002dd1d  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x14002dd22  nop
0x14002dd23  lea     rcx, [rbp+1C0h+var_58]
0x14002dd2a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x14002dd2f  mov     [rsp+2C0h+var_2A0], rax
0x14002dd34  lea     rdx, [rbp+1C0h+var_78]
0x14002dd3b  lea     rcx, [rbp+1C0h+var_178]
0x14002dd3f  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x14002dd44  lea     rcx, [rbp+1C0h+var_78]
0x14002dd4b  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x14002dd50  mov     [rsp+2C0h+var_298], rax
0x14002dd55  mov     rcx, r14
0x14002dd58  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x14002dd5d  mov     [rbp+1C0h+var_90], rax
0x14002dd64  lea     r8, [rsp+2C0h+var_2A0]
0x14002dd69  lea     rdx, [rsp+2C0h+var_298]
0x14002dd6e  lea     rcx, [rbp+1C0h+var_90]
0x14002dd75  call    ??$AgentActivationSettingTrace@PEADPEADPEAD@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEAD00@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingTrace<char *,char *,char *>(char * &&,char * &&,char * &&)
0x14002dd7a  lea     rcx, [rbp+1C0h+var_78]
0x14002dd81  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002dd86  nop
0x14002dd87  lea     rcx, [rbp+1C0h+var_58]
0x14002dd8e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002dd93  nop
0x14002dd94  lea     rcx, [rsp+2C0h+var_290]
0x14002dd99  call    ??_D?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(void)
0x14002dd9e  nop
0x14002dd9f  lea     rcx, [rbp+1C0h+var_190]
0x14002dda3  call    ??_D?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(void)
0x14002dda8  nop
0x14002dda9  mov     rcx, r14
0x14002ddac  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ddb1  nop
0x14002ddb2  mov     rcx, r15
0x14002ddb5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ddba  nop
0x14002ddbb  mov     rcx, r12
0x14002ddbe  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ddc3  nop
0x14002ddc4  mov     rcx, rsi
0x14002ddc7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ddcc  mov     rcx, [rbp+1C0h+var_38]
0x14002ddd3  xor     rcx, rsp; StackCookie
0x14002ddd6  call    __security_check_cookie
0x14002dddb  add     rsp, 290h
0x14002dde2  pop     r15
0x14002dde4  pop     r14
0x14002dde6  pop     r12
0x14002dde8  pop     rdi
0x14002dde9  pop     rsi
0x14002ddea  pop     rbx
0x14002ddeb  pop     rbp
0x14002ddec  retn
```
