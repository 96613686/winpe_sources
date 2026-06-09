# MdmLogCollector::GetUefiCompressedAsBase64String(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18010f7a0`
- end: `0x18010f943`
- name: `?GetUefiCompressedAsBase64String@MdmLogCollector@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(LPCWSTR lpGuid, LPCWSTR lpName)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180019000`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef558`
- `0x1800ef5d8`
- `0x1800f97d0`
- `0x18010772c`
- `0x1801077f8`
- `0x18010f7a0`
- `0x18010f94c`
- `0x18011150c`

## import_xrefs

- `CRYPT32!CryptBinaryToStringW` at `0x18010f866`
- `CRYPT32!CryptBinaryToStringW` at `0x18010f8ba`
- `CRYPT32!CryptBinaryToStringW` at `0x18010f866`
- `CRYPT32!CryptBinaryToStringW` at `0x18010f8ba`

## string_xrefs

- `0x18010f80e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f874`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f8c8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmLogCollector::GetUefiCompressedAsBase64String(LPCWSTR lpGuid, LPCWSTR lpName, __int64 a3)
{
  int UefiDataAsByteArray; // eax
  unsigned int LastError; // ebx
  DWORD v8; // ebx
  const char *v9; // r9
  WCHAR *v10; // rax
  const char *v11; // r9
  DWORD v12; // eax
  int pcchString; // [rsp+20h] [rbp-60h]
  DWORD v15; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v16[4]; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD cbBinary; // [rsp+38h] [rbp-48h] BYREF
  BYTE *pbBinary[3]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  std::vector<unsigned char>::vector<unsigned char>(pbBinary, 102400, v16);
  cbBinary = 0;
  UefiDataAsByteArray = ModernDeployment::Autopilot::Core::UefiGeneralUtilsT<ModernDeployment::Autopilot::Core::EmptyTemplateClassType>::GetUefiDataAsByteArray(
                          lpGuid,
                          lpName,
                          pbBinary[0],
                          0x19000u,
                          (__int64)&cbBinary);
  LastError = UefiDataAsByteArray;
  if ( UefiDataAsByteArray >= 0 )
  {
    v8 = cbBinary;
    if ( cbBinary )
    {
      v15 = 0;
      if ( !CryptBinaryToStringW(pbBinary[0], cbBinary, 0x40000001u, 0, &v15) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x536,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                      v9);
        goto LABEL_14;
      }
      std::wstring::wstring(v19, v15, 0);
      v10 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
      if ( !CryptBinaryToStringW(pbBinary[0], v8, 0x40000001u, v10, &v15) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x53E,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                      v11);
        std::wstring::_Tidy_deallocate(v19);
        goto LABEL_14;
      }
      if ( v15 )
        v12 = v15 - 1;
      else
        v12 = 0;
      std::wstring::resize(v19, v12, 0);
      std::wstring::operator=(a3, v19);
      std::wstring::_Tidy_deallocate(v19);
    }
    else
    {
      *(_QWORD *)(a3 + 16) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) = 0;
    }
    LastError = 0;
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x528,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
    (const char *)(unsigned int)UefiDataAsByteArray,
    pcchString);
LABEL_14:
  std::vector<unsigned char>::_Tidy(pbBinary);
  return LastError;
}

```

## disassembly

```asm
0x18010f7a0  mov     [rsp-18h+arg_18], rbx
0x18010f7a5  push    rbp
0x18010f7a6  push    rsi
0x18010f7a7  push    rdi
0x18010f7a8  mov     rbp, rsp
0x18010f7ab  sub     rsp, 80h
0x18010f7b2  mov     rax, cs:__security_cookie
0x18010f7b9  xor     rax, rsp
0x18010f7bc  mov     [rbp+var_8], rax
0x18010f7c0  mov     rsi, r8
0x18010f7c3  mov     rdi, rdx
0x18010f7c6  mov     rbx, rcx
0x18010f7c9  lea     r8, [rbp+var_4C]
0x18010f7cd  mov     edx, 19000h
0x18010f7d2  lea     rcx, [rbp+pbBinary]
0x18010f7d6  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18010f7db  nop
0x18010f7dc  mov     [rbp+cbBinary], 0
0x18010f7e3  lea     rax, [rbp+cbBinary]
0x18010f7e7  mov     qword ptr [rsp+80h+pcchString], rax; int
0x18010f7ec  mov     r9d, 19000h; nSize
0x18010f7f2  mov     r8, [rbp+pbBinary]; pBuffer
0x18010f7f6  mov     rdx, rdi; lpName
0x18010f7f9  mov     rcx, rbx; lpGuid
0x18010f7fc  call    ?GetUefiDataAsByteArray@?$UefiGeneralUtilsT@VEmptyTemplateClassType@Core@Autopilot@ModernDeployment@@@Core@Autopilot@ModernDeployment@@SAJPEBG0PEAEKAEAK@Z; ModernDeployment::Autopilot::Core::UefiGeneralUtilsT<ModernDeployment::Autopilot::Core::EmptyTemplateClassType>::GetUefiDataAsByteArray(ushort const *,ushort const *,uchar *,ulong,ulong &)
0x18010f801  mov     ebx, eax
0x18010f803  test    eax, eax
0x18010f805  jns     short loc_18010F824
0x18010f807  mov     rcx, [rbp+18h]; this
0x18010f80b  mov     r9d, eax; char *
0x18010f80e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f815  mov     edx, 528h; void *
0x18010f81a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f81f  jmp     loc_18010F919
0x18010f824  mov     ebx, [rbp+cbBinary]
0x18010f827  test    ebx, ebx
0x18010f829  jnz     short loc_18010F845
0x18010f82b  mov     qword ptr [rsi+10h], 0
0x18010f833  mov     rcx, rsi
0x18010f836  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f83b  xor     ecx, ecx
0x18010f83d  mov     [rax], cx
0x18010f840  jmp     loc_18010F917
0x18010f845  mov     [rbp+var_50], 0
0x18010f84c  lea     rax, [rbp+var_50]
0x18010f850  mov     qword ptr [rsp+80h+pcchString], rax; pcchString
0x18010f855  xor     r9d, r9d; pszString
0x18010f858  mov     edi, 40000001h
0x18010f85d  mov     r8d, edi; dwFlags
0x18010f860  mov     edx, ebx; cbBinary
0x18010f862  mov     rcx, [rbp+pbBinary]; pbBinary
0x18010f866  call    cs:__imp_CryptBinaryToStringW
0x18010f86c  test    eax, eax
0x18010f86e  jnz     short loc_18010F88C
0x18010f870  mov     rcx, [rbp+18h]; this
0x18010f874  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f87b  mov     edx, 536h; void *
0x18010f880  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010f885  mov     ebx, eax
0x18010f887  jmp     loc_18010F919
0x18010f88c  xor     r8d, r8d
0x18010f88f  mov     edx, [rbp+var_50]
0x18010f892  lea     rcx, [rbp+var_28]
0x18010f896  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18010f89b  nop
0x18010f89c  lea     rcx, [rbp+var_28]
0x18010f8a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f8a5  mov     r9, rax; pszString
0x18010f8a8  lea     rax, [rbp+var_50]
0x18010f8ac  mov     qword ptr [rsp+80h+pcchString], rax; pcchString
0x18010f8b1  mov     r8d, edi; dwFlags
0x18010f8b4  mov     edx, ebx; cbBinary
0x18010f8b6  mov     rcx, [rbp+pbBinary]; pbBinary
0x18010f8ba  call    cs:__imp_CryptBinaryToStringW
0x18010f8c0  test    eax, eax
0x18010f8c2  jnz     short loc_18010F8E6
0x18010f8c4  mov     rcx, [rbp+18h]; this
0x18010f8c8  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f8cf  mov     edx, 53Eh; void *
0x18010f8d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010f8d9  mov     ebx, eax
0x18010f8db  lea     rcx, [rbp+var_28]
0x18010f8df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f8e4  jmp     short loc_18010F919
0x18010f8e6  mov     eax, [rbp+var_50]
0x18010f8e9  test    eax, eax
0x18010f8eb  jz      short loc_18010F8F1
0x18010f8ed  dec     eax
0x18010f8ef  jmp     short loc_18010F8F3
0x18010f8f1  xor     eax, eax
0x18010f8f3  xor     r8d, r8d
0x18010f8f6  mov     edx, eax
0x18010f8f8  lea     rcx, [rbp+var_28]
0x18010f8fc  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18010f901  lea     rdx, [rbp+var_28]
0x18010f905  mov     rcx, rsi
0x18010f908  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18010f90d  nop
0x18010f90e  lea     rcx, [rbp+var_28]
0x18010f912  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f917  xor     ebx, ebx
0x18010f919  lea     rcx, [rbp+pbBinary]
0x18010f91d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18010f922  mov     eax, ebx
0x18010f924  mov     rcx, [rbp+var_8]
0x18010f928  xor     rcx, rsp; StackCookie
0x18010f92b  call    __security_check_cookie
0x18010f930  mov     rbx, [rsp+80h+arg_18]
0x18010f938  add     rsp, 80h
0x18010f93f  pop     rdi
0x18010f940  pop     rsi
0x18010f941  pop     rbp
0x18010f942  retn
```
