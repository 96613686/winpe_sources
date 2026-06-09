# RetailDemoUserAgent::SetDesiredTimeZone(ushort const * const)

- ea: `0x18004088c`
- end: `0x180040c0d`
- name: `?SetDesiredTimeZone@RetailDemoUserAgent@@AEAAJQEBG@Z`
- size: `897`
- prototype: `int(RetailDemoUserAgent *__hidden this, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003d870`

## callees

- `0x180003390`
- `0x180003e00`
- `0x18000649c`
- `0x18000aa5c`
- `0x18000aa7c`
- `0x18000c168`
- `0x18000c1a8`
- `0x18001092c`
- `0x180033e78`
- `0x180036120`
- `0x180036434`
- `0x180036c68`
- `0x18004088c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800409c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040b20`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800409c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040b20`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040969`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040ad0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040969`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040ad0`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x180040b40`
- `api-ms-win-core-timezone-l1-1-0!SetDynamicTimeZoneInformation` at `0x180040b40`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x1800408e0`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x1800408e0`
- `api-ms-win-core-timezone-l1-1-0!EnumDynamicTimeZoneInformation` at `0x180040a09`
- `api-ms-win-core-timezone-l1-1-0!EnumDynamicTimeZoneInformation` at `0x180040a09`

## string_xrefs

- `0x180040b6e`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180040bb8`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RetailDemoUserAgent::SetDesiredTimeZone(RetailDemoUserAgent *this, const WCHAR *a2)
{
  int v3; // r14d
  DWORD DynamicTimeZoneInformation; // eax
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rax
  const WCHAR *v8; // rax
  LSTATUS ValueW; // eax
  signed int v10; // ebx
  const char *v11; // r9
  __int64 result; // rax
  unsigned int v13; // edi
  unsigned __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  const WCHAR *v18; // rax
  LSTATUS v19; // eax
  signed int v20; // ebx
  const unsigned __int16 *v21; // rdx
  const char *v22; // r9
  unsigned int LastError; // ebx
  int pdwType; // [rsp+20h] [rbp-638h]
  DWORD pcbData; // [rsp+40h] [rbp-618h] BYREF
  _BYTE v26[16]; // [rsp+48h] [rbp-610h] BYREF
  __int64 v27; // [rsp+58h] [rbp-600h]
  _BYTE v28[32]; // [rsp+68h] [rbp-5F0h] BYREF
  char TokenHandle[56]; // [rsp+88h] [rbp-5D0h] BYREF
  DYNAMIC_TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+C0h] [rbp-598h] BYREF
  _TIME_DYNAMIC_ZONE_INFORMATION pTimeZoneInformation; // [rsp+270h] [rbp-3E8h] BYREF
  WCHAR String2[264]; // [rsp+420h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+658h] [rbp+0h]

  v3 = 0;
  pcbData = 0;
  memset_0(&pTimeZoneInformation, 0, sizeof(pTimeZoneInformation));
  DynamicTimeZoneInformation = GetDynamicTimeZoneInformation(&pTimeZoneInformation);
  try
  {
    if ( DynamicTimeZoneInformation == -1 )
      goto LABEL_9;
    memset_0(String2, 0, 0x208u);
    v5 = std::wstring::wstring((__int64)TokenHandle, (__int64)pTimeZoneInformation.TimeZoneKeyName);
    v7 = std::operator+<unsigned short>(v28, v6, v5);
    pcbData = 520;
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v8, L"Display", 2u, 0, String2, &pcbData);
    v10 = ValueW;
    if ( ValueW )
    {
      String2[0] = 0;
      if ( ValueW > 0 )
        v10 = (unsigned __int16)ValueW | 0x80070000;
    }
    std::wstring::_Tidy_deallocate(v28);
    std::wstring::_Tidy_deallocate(TokenHandle);
    if ( v10 < 0 || CompareStringOrdinal(a2, -1, String2, -1, 1) != 2 )
    {
LABEL_9:
      std::wstring::wstring((__int64)v26, (__int64)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones\\");
      v13 = 0;
      memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
      while ( 1 )
      {
        if ( (unsigned int)EnumDynamicTimeZoneInformation(v13, &TimeZoneInformation) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E0,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
            (const char *)0x80070490LL,
            pdwType);
          std::wstring::_Tidy_deallocate(v26);
          return 2147943568LL;
        }
        memset_0(String2, 0, 0x208u);
        v14 = -1;
        do
          ++v14;
        while ( TimeZoneInformation.TimeZoneKeyName[v14] );
        if ( 0x7FFFFFFFFFFFFFFELL - v27 < v14 )
          std::_Xlen_string();
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
        std::wstring::wstring(v28, v16, v17, v15, v17, TimeZoneInformation.TimeZoneKeyName, v16);
        pcbData = 520;
        v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
        v19 = RegGetValueW(HKEY_LOCAL_MACHINE, v18, L"Display", 2u, 0, String2, &pcbData);
        v20 = v19;
        if ( v19 )
        {
          String2[0] = 0;
          if ( v19 > 0 )
            v20 = (unsigned __int16)v19 | 0x80070000;
        }
        std::wstring::_Tidy_deallocate(v28);
        if ( v20 >= 0 && CompareStringOrdinal(a2, -1, String2, -1, 1) == 2 )
          break;
        ++v13;
        v3 |= 1u;
      }
      unique_adjust_token_privilege::unique_adjust_token_privilege(TokenHandle, v21);
      if ( SetDynamicTimeZoneInformation(&TimeZoneInformation) )
      {
        unique_adjust_token_privilege::~unique_adjust_token_privilege((unique_adjust_token_privilege *)TokenHandle);
        std::wstring::_Tidy_deallocate(v26);
        result = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1DA,
                      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retail"
                                    "demouseragent.cpp",
                      v22);
        unique_adjust_token_privilege::~unique_adjust_token_privilege((unique_adjust_token_privilege *)TokenHandle);
        std::wstring::_Tidy_deallocate(v26);
        result = LastError;
      }
    }
    else
    {
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1E2,
                           (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\r"
                                         "etaildemouseragent.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18004088c  mov     [rsp+arg_0], rbx
0x180040891  mov     [rsp+arg_10], rdi
0x180040896  push    r12
0x180040898  push    r14
0x18004089a  push    r15
0x18004089c  sub     rsp, 640h
0x1800408a3  mov     rax, cs:__security_cookie
0x1800408aa  xor     rax, rsp
0x1800408ad  mov     [rsp+658h+var_28], rax
0x1800408b5  mov     r15, rdx
0x1800408b8  xor     r12d, r12d
0x1800408bb  mov     r14d, r12d
0x1800408be  mov     [rsp+658h+var_618], r12d
0x1800408c3  xor     edx, edx; Val
0x1800408c5  mov     r8d, 1B0h; Size
0x1800408cb  lea     rcx, [rsp+658h+pTimeZoneInformation]; void *
0x1800408d3  call    memset_0
0x1800408d8  lea     rcx, [rsp+658h+pTimeZoneInformation]; pTimeZoneInformation
0x1800408e0  call    cs:__imp_GetDynamicTimeZoneInformation
0x1800408e6  cmp     eax, 0FFFFFFFFh
0x1800408e9  jz      loc_1800409D5
0x1800408ef  xor     edx, edx; Val
0x1800408f1  mov     r8d, 208h; Size
0x1800408f7  lea     rcx, [rsp+658h+String2]; void *
0x1800408ff  call    memset_0
0x180040904  lea     rdx, [rsp+658h+pTimeZoneInformation.TimeZoneKeyName]
0x18004090c  lea     rcx, [rsp+658h+TokenHandle]
0x180040914  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040919  nop
0x18004091a  mov     r8, rax
0x18004091d  lea     rcx, [rsp+658h+var_5F0]
0x180040922  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180040927  mov     [rsp+658h+var_618], 208h
0x18004092f  mov     rcx, rax
0x180040932  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180040937  mov     rdx, rax; lpSubKey
0x18004093a  lea     rax, [rsp+658h+var_618]
0x18004093f  mov     [rsp+658h+pcbData], rax; pcbData
0x180040944  lea     rax, [rsp+658h+String2]
0x18004094c  mov     [rsp+658h+pvData], rax; pvData
0x180040951  mov     [rsp+658h+pdwType], r12; pdwType
0x180040956  lea     r9d, [r12+2]; dwFlags
0x18004095b  lea     r8, aDisplay; "Display"
0x180040962  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180040969  call    cs:__imp_RegGetValueW
0x18004096f  mov     ebx, eax
0x180040971  test    eax, eax
0x180040973  jz      short loc_180040989
0x180040975  mov     [rsp+658h+String2], r12w
0x18004097e  jle     short loc_180040989
0x180040980  movzx   ebx, ax
0x180040983  or      ebx, 80070000h
0x180040989  shr     ebx, 1Fh
0x18004098c  lea     rcx, [rsp+658h+var_5F0]
0x180040991  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040996  nop
0x180040997  lea     rcx, [rsp+658h+TokenHandle]
0x18004099f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800409a4  xor     bl, 1
0x1800409a7  jz      short loc_1800409D5
0x1800409a9  mov     dword ptr [rsp+658h+pdwType], 1; bIgnoreCase
0x1800409b1  or      r9d, 0FFFFFFFFh; cchCount2
0x1800409b5  lea     r8, [rsp+658h+String2]; lpString2
0x1800409bd  or      edx, r9d; cchCount1
0x1800409c0  mov     rcx, r15; lpString1
0x1800409c3  call    cs:__imp_CompareStringOrdinal
0x1800409c9  cmp     eax, 2
0x1800409cc  jnz     short loc_1800409D5
0x1800409ce  xor     eax, eax
0x1800409d0  jmp     loc_180040BDC
0x1800409d5  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800409dc  lea     rcx, [rsp+658h+var_610]
0x1800409e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800409e6  nop
0x1800409e7  mov     edi, r12d
0x1800409ea  xor     edx, edx; Val
0x1800409ec  mov     r8d, 1B0h; Size
0x1800409f2  lea     rcx, [rsp+658h+TimeZoneInformation]; void *
0x1800409fa  call    memset_0
0x1800409ff  lea     rdx, [rsp+658h+TimeZoneInformation]
0x180040a07  mov     ecx, edi
0x180040a09  call    cs:__imp_EnumDynamicTimeZoneInformation
0x180040a0f  test    eax, eax
0x180040a11  jnz     loc_180040BA8
0x180040a17  xor     edx, edx; Val
0x180040a19  mov     r8d, 208h; Size
0x180040a1f  lea     rcx, [rsp+658h+String2]; void *
0x180040a27  call    memset_0
0x180040a2c  mov     r8, [rsp+658h+var_600]
0x180040a31  lea     rax, [rsp+658h+TimeZoneInformation.TimeZoneKeyName]
0x180040a39  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180040a3d  inc     rdx
0x180040a40  cmp     [rax+rdx*2], r12w
0x180040a45  jnz     short loc_180040A3D
0x180040a47  mov     rax, 7FFFFFFFFFFFFFFEh
0x180040a51  sub     rax, r8
0x180040a54  cmp     rax, rdx
0x180040a57  jb      loc_180040C06
0x180040a5d  lea     rcx, [rsp+658h+var_610]
0x180040a62  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180040a67  mov     r9, rax
0x180040a6a  mov     [rsp+658h+pcbData], rdx
0x180040a6f  lea     rax, [rsp+658h+TimeZoneInformation.TimeZoneKeyName]
0x180040a77  mov     [rsp+658h+pvData], rax
0x180040a7c  mov     [rsp+658h+pdwType], r8
0x180040a81  lea     rcx, [rsp+658h+var_5F0]
0x180040a86  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180040a8b  mov     [rsp+658h+var_618], 208h
0x180040a93  lea     rcx, [rsp+658h+var_5F0]
0x180040a98  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180040a9d  mov     rdx, rax; lpSubKey
0x180040aa0  lea     rax, [rsp+658h+var_618]
0x180040aa5  mov     [rsp+658h+pcbData], rax; pcbData
0x180040aaa  lea     rax, [rsp+658h+String2]
0x180040ab2  mov     [rsp+658h+pvData], rax; pvData
0x180040ab7  mov     [rsp+658h+pdwType], r12; pdwType
0x180040abc  mov     r9d, 2; dwFlags
0x180040ac2  lea     r8, aDisplay; "Display"
0x180040ac9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180040ad0  call    cs:__imp_RegGetValueW
0x180040ad6  mov     ebx, eax
0x180040ad8  test    eax, eax
0x180040ada  jz      short loc_180040AF0
0x180040adc  mov     [rsp+658h+String2], r12w
0x180040ae5  jle     short loc_180040AF0
0x180040ae7  movzx   ebx, ax
0x180040aea  or      ebx, 80070000h
0x180040af0  lea     rcx, [rsp+658h+var_5F0]
0x180040af5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040afa  shr     ebx, 1Fh
0x180040afd  xor     bl, 1
0x180040b00  jz      loc_180040B9D
0x180040b06  mov     dword ptr [rsp+658h+pdwType], 1; bIgnoreCase
0x180040b0e  or      r9d, 0FFFFFFFFh; cchCount2
0x180040b12  lea     r8, [rsp+658h+String2]; lpString2
0x180040b1a  or      edx, r9d; cchCount1
0x180040b1d  mov     rcx, r15; lpString1
0x180040b20  call    cs:__imp_CompareStringOrdinal
0x180040b26  cmp     eax, 2
0x180040b29  jnz     short loc_180040B9D
0x180040b2b  lea     rcx, [rsp+658h+TokenHandle]; TokenHandle
0x180040b33  call    ??0unique_adjust_token_privilege@@QEAA@PEBG@Z; unique_adjust_token_privilege::unique_adjust_token_privilege(ushort const *)
0x180040b38  lea     rcx, [rsp+658h+TimeZoneInformation]; lpTimeZoneInformation
0x180040b40  call    cs:__imp_SetDynamicTimeZoneInformation
0x180040b46  test    eax, eax
0x180040b48  jz      short loc_180040B66
0x180040b4a  lea     rcx, [rsp+658h+TokenHandle]; this
0x180040b52  call    ??1unique_adjust_token_privilege@@QEAA@XZ; unique_adjust_token_privilege::~unique_adjust_token_privilege(void)
0x180040b57  nop
0x180040b58  lea     rcx, [rsp+658h+var_610]
0x180040b5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040b62  xor     eax, eax
0x180040b64  jmp     short loc_180040BDC
0x180040b66  mov     rcx, [rsp+658h]; this
0x180040b6e  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180040b75  mov     edx, 1DAh; void *
0x180040b7a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040b7f  mov     ebx, eax
0x180040b81  lea     rcx, [rsp+658h+TokenHandle]; this
0x180040b89  call    ??1unique_adjust_token_privilege@@QEAA@XZ; unique_adjust_token_privilege::~unique_adjust_token_privilege(void)
0x180040b8e  nop
0x180040b8f  lea     rcx, [rsp+658h+var_610]
0x180040b94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040b99  mov     eax, ebx
0x180040b9b  jmp     short loc_180040BDC
0x180040b9d  inc     edi
0x180040b9f  or      r14d, 1
0x180040ba3  jmp     loc_1800409FF
0x180040ba8  mov     rcx, [rsp+658h]; this
0x180040bb0  mov     ebx, 80070490h
0x180040bb5  mov     r9d, ebx; char *
0x180040bb8  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180040bbf  mov     edx, 1E0h; void *
0x180040bc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040bc9  nop
0x180040bca  lea     rcx, [rsp+658h+var_610]
0x180040bcf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040bd4  mov     eax, ebx
0x180040bd6  jmp     short loc_180040BDC
0x180040bd8  mov     eax, [rsp+658h+var_618]
0x180040bdc  mov     rcx, [rsp+658h+var_28]
0x180040be4  xor     rcx, rsp; StackCookie
0x180040be7  call    __security_check_cookie
0x180040bec  lea     r11, [rsp+658h+var_18]
0x180040bf4  mov     rbx, [r11+20h]
0x180040bf8  mov     rdi, [r11+30h]
0x180040bfc  mov     rsp, r11
0x180040bff  pop     r15
0x180040c01  pop     r14
0x180040c03  pop     r12
0x180040c05  retn
0x180040c06  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
