# Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::LogWInternal(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void const *)

- ea: `0x14002ea5c`
- end: `0x14002ec09`
- name: `?LogWInternal@SettingLogger@Settings@Windows@VoiceAgentServices@Microsoft@@AEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@00HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@PEBX@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002e900`

## callees

- `0x140002d30`
- `0x14001296c`
- `0x140012d68`
- `0x140021658`
- `0x1400243ec`
- `0x14002cf68`
- `0x14002cf84`
- `0x14002d1c8`
- `0x14002d6fc`
- `0x14002da00`
- `0x14002f1b4`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x14002eb1c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x14002eb1c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x14002eae4`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x14002eb44`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x14002eae4`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z` at `0x14002eb44`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::SettingLogger::LogWInternal(
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
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v20[16]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[232]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v24[240]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v25[3]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v26[32]; // [rsp+248h] [rbp+148h] BYREF

  v25[0] = a2;
  v25[1] = a4;
  v25[2] = a6;
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v23);
  v10 = std::operator<<<char>(v24, a2);
  v11 = std::operator<<<std::char_traits<char>>(v10, " 0x");
  v12 = std::ostream::operator<<(v11, a7);
  v13 = std::operator<<<std::char_traits<char>>(v12, " ");
  v14 = std::operator<<<char>(v13, a4);
  v15 = std::operator<<<std::char_traits<char>>(v14, " @ ");
  std::ostream::operator<<(v15, a5);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v20);
  v16 = std::operator<<<std::char_traits<char>>(v21, "0x");
  std::ostream::operator<<(v16, a7);
  std::stringbuf::str(v22, v26);
  v18 = std::_String_val<std::_Simple_types<char>>::_Myptr(v26);
  v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
  v25[0] = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingTraceW<char *,unsigned short *,char *>(
    v25,
    &v19,
    &v18);
  std::string::~string(v26);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v20);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v23);
  std::string::~string(a2);
  std::string::~string(a3);
  std::string::~string(a4);
  return std::wstring::~wstring(a6);
}

```

## disassembly

```asm
0x14002ea5c  mov     [rsp-8+arg_0], rbx
0x14002ea61  push    rbp
0x14002ea62  push    rsi
0x14002ea63  push    rdi
0x14002ea64  push    r14
0x14002ea66  push    r15
0x14002ea68  lea     rbp, [rsp-170h]
0x14002ea70  sub     rsp, 270h
0x14002ea77  mov     rax, cs:__security_cookie
0x14002ea7e  xor     rax, rsp
0x14002ea81  mov     [rbp+190h+var_28], rax
0x14002ea88  mov     r15, r9
0x14002ea8b  mov     r14, r8
0x14002ea8e  mov     rsi, rdx
0x14002ea91  mov     [rbp+190h+var_60], rdx
0x14002ea98  mov     [rsp+290h+var_268], r8
0x14002ea9d  mov     [rbp+190h+var_58], r9
0x14002eaa4  mov     rdi, [rbp+190h+arg_28]
0x14002eaab  mov     [rbp+190h+var_50], rdi
0x14002eab2  mov     rbx, [rbp+190h+arg_30]
0x14002eab9  lea     rcx, [rbp+190h+var_160]
0x14002eabd  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x14002eac2  nop
0x14002eac3  mov     rdx, rsi
0x14002eac6  lea     rcx, [rbp+190h+var_150]
0x14002eaca  call    ??$?6DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<<char>(std::ostream &,std::string const &)
0x14002eacf  mov     rcx, rax
0x14002ead2  lea     rdx, a0x_0; " 0x"
0x14002ead9  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002eade  mov     rdx, rbx
0x14002eae1  mov     rcx, rax
0x14002eae4  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z; std::ostream::operator<<(void const *)
0x14002eaea  mov     rcx, rax
0x14002eaed  lea     rdx, asc_140040764; " "
0x14002eaf4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002eaf9  mov     rdx, r15
0x14002eafc  mov     rcx, rax
0x14002eaff  call    ??$?6DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<<char>(std::ostream &,std::string const &)
0x14002eb04  mov     rcx, rax
0x14002eb07  lea     rdx, asc_14004074C; " @ "
0x14002eb0e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002eb13  mov     edx, [rbp+190h+arg_20]
0x14002eb19  mov     rcx, rax
0x14002eb1c  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x14002eb22  lea     rcx, [rsp+290h+var_260]
0x14002eb27  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x14002eb2c  nop
0x14002eb2d  lea     rdx, a0x; "0x"
0x14002eb34  lea     rcx, [rsp+290h+var_250]
0x14002eb39  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14002eb3e  mov     rdx, rbx
0x14002eb41  mov     rcx, rax
0x14002eb44  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@PEBX@Z; std::ostream::operator<<(void const *)
0x14002eb4a  lea     rdx, [rbp+190h+var_48]
0x14002eb51  lea     rcx, [rsp+290h+var_248]
0x14002eb56  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x14002eb5b  lea     rcx, [rbp+190h+var_48]
0x14002eb62  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x14002eb67  mov     [rsp+290h+var_270], rax
0x14002eb6c  mov     rcx, rdi
0x14002eb6f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002eb74  mov     [rsp+290h+var_268], rax
0x14002eb79  mov     rcx, rsi
0x14002eb7c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x14002eb81  mov     [rbp+190h+var_60], rax
0x14002eb88  lea     r8, [rsp+290h+var_270]
0x14002eb8d  lea     rdx, [rsp+290h+var_268]
0x14002eb92  lea     rcx, [rbp+190h+var_60]
0x14002eb99  call    ??$AgentActivationSettingTraceW@PEADPEAGPEAD@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEAD$$QEAPEAG0@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::AgentActivationSettingTraceW<char *,ushort *,char *>(char * &&,ushort * &&,char * &&)
0x14002eb9e  lea     rcx, [rbp+190h+var_48]
0x14002eba5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ebaa  nop
0x14002ebab  lea     rcx, [rsp+290h+var_260]
0x14002ebb0  call    ??_D?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(void)
0x14002ebb5  nop
0x14002ebb6  lea     rcx, [rbp+190h+var_160]
0x14002ebba  call    ??_D?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(void)
0x14002ebbf  nop
0x14002ebc0  mov     rcx, rsi
0x14002ebc3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ebc8  nop
0x14002ebc9  mov     rcx, r14
0x14002ebcc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ebd1  nop
0x14002ebd2  mov     rcx, r15
0x14002ebd5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002ebda  nop
0x14002ebdb  mov     rcx, rdi
0x14002ebde  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002ebe3  mov     rcx, [rbp+190h+var_28]
0x14002ebea  xor     rcx, rsp; StackCookie
0x14002ebed  call    __security_check_cookie
0x14002ebf2  mov     rbx, [rsp+290h+arg_0]
0x14002ebfa  add     rsp, 270h
0x14002ec01  pop     r15
0x14002ec03  pop     r14
0x14002ec05  pop     rdi
0x14002ec06  pop     rsi
0x14002ec07  pop     rbp
0x14002ec08  retn
```
