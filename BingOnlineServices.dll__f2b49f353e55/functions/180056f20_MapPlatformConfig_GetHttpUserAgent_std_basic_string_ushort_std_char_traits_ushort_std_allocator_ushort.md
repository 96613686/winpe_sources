# MapPlatformConfig::GetHttpUserAgent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180056f20`
- end: `0x18005702c`
- name: `?GetHttpUserAgent@MapPlatformConfig@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18001b910`

## callees

- `0x180002c2c`
- `0x180004fa0`
- `0x180009778`
- `0x18000e5a8`
- `0x180015914`
- `0x1800562dc`
- `0x180056f20`
- `0x180058fb0`
- `0x180059028`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180056f87`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180056f87`

## string_xrefs

- `0x180056f7e`: `MapPlatformConfig::GetHttpUserAgent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MapPlatformConfig::GetHttpUserAgent(__int64 a1)
{
  unsigned int v2; // ebx
  const unsigned __int16 *v3; // rcx
  LSTATUS RegDword; // eax
  const unsigned __int16 *v5; // rcx
  int v6; // r8d
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rax
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v14[40]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[512]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  v13 = 0;
  v12 = 0;
  std::wstring::wstring(v14);
  RegDword = RegUtils::GetRegDword(v3, L"CurrentMajorVersionNumber", &v13);
  if ( RegDword >= 0 )
  {
    RegDword = RegUtils::GetRegDword(v5, L"CurrentMinorVersionNumber", &v12);
    if ( RegDword >= 0 )
    {
      RegDword = RegUtils::GetRegString(v8, v7, v9, v14);
      if ( RegDword >= 0 )
      {
        v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
        swprintf_s<256>(v15, L"Windows Maps (%lu.%lu.%s)", v13, v12, v10);
        std::wstring::assign(a1, v15);
        goto LABEL_9;
      }
      v6 = 146;
    }
    else
    {
      v6 = 145;
    }
  }
  else
  {
    v6 = 144;
  }
  v2 = ZTraceReportPropagationNoThis(RegDword, "MapPlatformConfig::GetHttpUserAgent", v6);
LABEL_9:
  std::wstring::_Tidy_deallocate(v14);
  return v2;
}

```

## disassembly

```asm
0x180056f20  mov     [rsp-8+arg_8], rbx
0x180056f25  mov     [rsp-8+arg_10], rdi
0x180056f2a  push    rbp
0x180056f2b  lea     rbp, [rsp-170h]
0x180056f33  sub     rsp, 270h
0x180056f3a  mov     rax, cs:__security_cookie
0x180056f41  xor     rax, rsp
0x180056f44  mov     [rbp+170h+var_10], rax
0x180056f4b  mov     rdi, rcx
0x180056f4e  xor     ebx, ebx
0x180056f50  mov     [rsp+270h+var_23C], ebx
0x180056f54  mov     [rsp+270h+var_240], ebx
0x180056f58  lea     rcx, [rsp+270h+var_238]
0x180056f5d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180056f62  nop
0x180056f63  lea     r8, [rsp+270h+var_23C]; unsigned int *
0x180056f68  lea     rdx, aCurrentmajorve; "CurrentMajorVersionNumber"
0x180056f6f  call    ?GetRegDword@RegUtils@@SAJPEBG0PEAK@Z; RegUtils::GetRegDword(ushort const *,ushort const *,ulong *)
0x180056f74  test    eax, eax
0x180056f76  jns     short loc_180056F91
0x180056f78  mov     r8d, 90h
0x180056f7e  lea     rdx, aMapplatformcon; "MapPlatformConfig::GetHttpUserAgent"
0x180056f85  mov     ecx, eax
0x180056f87  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180056f8d  mov     ebx, eax
0x180056f8f  jmp     short loc_180056FFC
0x180056f91  lea     r8, [rsp+270h+var_240]; unsigned int *
0x180056f96  lea     rdx, aCurrentminorve; "CurrentMinorVersionNumber"
0x180056f9d  call    ?GetRegDword@RegUtils@@SAJPEBG0PEAK@Z; RegUtils::GetRegDword(ushort const *,ushort const *,ulong *)
0x180056fa2  test    eax, eax
0x180056fa4  jns     short loc_180056FAE
0x180056fa6  mov     r8d, 91h
0x180056fac  jmp     short loc_180056F7E
0x180056fae  lea     r9, [rsp+270h+var_238]
0x180056fb3  call    ?GetRegString@RegUtils@@SAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetRegString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x180056fb8  test    eax, eax
0x180056fba  jns     short loc_180056FC4
0x180056fbc  mov     r8d, 92h
0x180056fc2  jmp     short loc_180056F7E
0x180056fc4  lea     rcx, [rsp+270h+var_238]
0x180056fc9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056fce  mov     [rsp+270h+var_250], rax
0x180056fd3  mov     r9d, [rsp+270h+var_240]
0x180056fd8  mov     r8d, [rsp+270h+var_23C]
0x180056fdd  lea     rdx, aWindowsMapsLuL; "Windows Maps (%lu.%lu.%s)"
0x180056fe4  lea     rcx, [rsp+270h+var_210]
0x180056fe9  call    ??$swprintf_s@$0BAA@@@YAHAEAY0BAA@GPEBGZZ; swprintf_s<256>(ushort (&)[256],ushort const *,...)
0x180056fee  lea     rdx, [rsp+270h+var_210]
0x180056ff3  mov     rcx, rdi
0x180056ff6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180056ffb  nop
0x180056ffc  lea     rcx, [rsp+270h+var_238]
0x180057001  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180057006  mov     eax, ebx
0x180057008  mov     rcx, [rbp+170h+var_10]
0x18005700f  xor     rcx, rsp; StackCookie
0x180057012  call    __security_check_cookie
0x180057017  lea     r11, [rsp+270h+var_s0]
0x18005701f  mov     rbx, [r11+18h]
0x180057023  mov     rdi, [r11+20h]
0x180057027  mov     rsp, r11
0x18005702a  pop     rbp
0x18005702b  retn
```
