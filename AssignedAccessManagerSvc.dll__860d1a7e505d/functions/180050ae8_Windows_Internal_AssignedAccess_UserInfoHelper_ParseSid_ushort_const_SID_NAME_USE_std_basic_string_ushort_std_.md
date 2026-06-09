# Windows::Internal::AssignedAccess::UserInfoHelper::ParseSid(ushort const *,_SID_NAME_USE &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180050ae8`
- end: `0x180050ced`
- name: `?ParseSid@UserInfoHelper@AssignedAccess@Internal@Windows@@CAJPEBGAEAW4_SID_NAME_USE@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z`
- size: `517`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800502d0`
- `0x1800505d0`

## callees

- `0x18000b694`
- `0x18000b6b4`
- `0x18002001c`
- `0x18002074c`
- `0x1800221e0`
- `0x18004b930`
- `0x18004c19c`
- `0x18004eca0`
- `0x180050ae8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050bc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050bc9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050b69`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050b69`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180050bbf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180050c52`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180050bbf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180050c52`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::AssignedAccess::UserInfoHelper::ParseSid(
        __int64 a1,
        enum _SID_NAME_USE *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int LastError; // ebx
  __int64 v8; // r9
  LPCWSTR v9; // r10
  const char *v10; // r9
  signed int v11; // eax
  const char *v12; // r9
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  int ReferencedDomainName; // [rsp+20h] [rbp-60h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-60h]
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  PSID Sid; // [rsp+48h] [rbp-38h] BYREF
  LPWSTR v22[3]; // [rsp+50h] [rbp-30h] BYREF
  LPWSTR Name[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD cchReferencedDomainName; // [rsp+A0h] [rbp+20h] BYREF

  if ( a1 )
  {
    *a2 = SidTypeUnknown;
    *(_QWORD *)(a3 + 16) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) = 0;
    *(_QWORD *)(v8 + 16) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4) = 0;
    Sid = 0;
    if ( !ConvertStringSidToSidW(v9, &Sid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x5E,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
                    v10);
LABEL_16:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      return LastError;
    }
    cchName = 0;
    cchReferencedDomainName = 0;
    if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, a2) )
    {
      v11 = GetLastError();
      LastError = v11;
      if ( v11 == 1332 )
        goto LABEL_15;
      if ( v11 != 122 )
      {
        if ( v11 > 0 )
          LastError = (unsigned __int16)v11 | 0x80070000;
        if ( (LastError & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x67,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
            (const char *)LastError,
            ReferencedDomainNamea);
        goto LABEL_16;
      }
    }
    std::vector<unsigned short>::vector<unsigned short>(Name, cchName);
    std::vector<unsigned short>::vector<unsigned short>(v22, cchReferencedDomainName);
    if ( !LookupAccountSidW(0, Sid, Name[0], &cchName, v22[0], &cchReferencedDomainName, a2) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6F,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
                    v12);
      std::vector<unsigned short>::_Tidy(v22);
      std::vector<unsigned short>::_Tidy(Name);
      goto LABEL_16;
    }
    v13 = std::_WChar_traits<unsigned short>::length(Name[0]);
    std::wstring::_Assign<unsigned short>(a3, v14, v13);
    v15 = std::_WChar_traits<unsigned short>::length(v22[0]);
    std::wstring::_Assign<unsigned short>(a4, v16, v15);
    std::vector<unsigned short>::_Tidy(v22);
    std::vector<unsigned short>::_Tidy(Name);
LABEL_15:
    LastError = 0;
    goto LABEL_16;
  }
  LastError = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x58,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
    (const char *)0x80004003LL,
    ReferencedDomainName);
  return LastError;
}

```

## disassembly

```asm
0x180050ae8  mov     [rsp-18h+arg_8], rbx
0x180050aed  mov     [rsp-18h+arg_10], rsi
0x180050af2  push    rbp
0x180050af3  push    rdi
0x180050af4  push    r14
0x180050af6  mov     rbp, rsp
0x180050af9  sub     rsp, 80h
0x180050b00  mov     rsi, r9
0x180050b03  mov     r14, r8
0x180050b06  mov     rdi, rdx
0x180050b09  mov     r10, rcx
0x180050b0c  test    rcx, rcx
0x180050b0f  jnz     short loc_180050B32
0x180050b11  mov     rcx, [rbp+18h]; this
0x180050b15  mov     ebx, 80004003h
0x180050b1a  mov     r9d, ebx; char *
0x180050b1d  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050b24  lea     edx, [r10+58h]; void *
0x180050b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050b2d  jmp     loc_180050CD3
0x180050b32  mov     dword ptr [rdx], 8
0x180050b38  mov     qword ptr [r8+10h], 0
0x180050b40  mov     rcx, r14
0x180050b43  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050b48  xor     ecx, ecx
0x180050b4a  mov     [rax], cx
0x180050b4d  mov     [r9+10h], rcx
0x180050b51  mov     rcx, rsi
0x180050b54  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050b59  xor     ecx, ecx
0x180050b5b  mov     [rax], cx
0x180050b5e  mov     [rbp+Sid], rcx
0x180050b62  lea     rdx, [rbp+Sid]; Sid
0x180050b66  mov     rcx, r10; StringSid
0x180050b69  call    cs:__imp_ConvertStringSidToSidW
0x180050b6f  test    eax, eax
0x180050b71  jnz     short loc_180050B8D
0x180050b73  mov     rcx, [rbp+18h]; this
0x180050b77  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050b7e  lea     edx, [rax+5Eh]; void *
0x180050b81  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050b86  mov     ebx, eax
0x180050b88  jmp     loc_180050CCA
0x180050b8d  mov     [rbp+cchName], 0
0x180050b94  mov     [rbp+arg_0], 0
0x180050b9b  mov     [rsp+80h+peUse], rdi; peUse
0x180050ba0  lea     rax, [rbp+arg_0]
0x180050ba4  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180050ba9  mov     [rsp+80h+ReferencedDomainName], 0; int
0x180050bb2  lea     r9, [rbp+cchName]; cchName
0x180050bb6  xor     r8d, r8d; Name
0x180050bb9  mov     rdx, [rbp+Sid]; Sid
0x180050bbd  xor     ecx, ecx; lpSystemName
0x180050bbf  call    cs:__imp_LookupAccountSidW
0x180050bc5  test    eax, eax
0x180050bc7  jnz     short loc_180050C13
0x180050bc9  call    cs:__imp_GetLastError
0x180050bcf  mov     ebx, eax
0x180050bd1  cmp     eax, 534h
0x180050bd6  jz      loc_180050CC8
0x180050bdc  cmp     eax, 7Ah ; 'z'
0x180050bdf  jz      short loc_180050C13
0x180050be1  test    eax, eax
0x180050be3  jle     short loc_180050BEE
0x180050be5  movzx   ebx, ax
0x180050be8  or      ebx, 80070000h
0x180050bee  test    ebx, ebx
0x180050bf0  jns     loc_180050CCA
0x180050bf6  mov     rcx, [rbp+18h]; this
0x180050bfa  mov     r9d, ebx; char *
0x180050bfd  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050c04  mov     edx, 67h ; 'g'; void *
0x180050c09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050c0e  jmp     loc_180050CCA
0x180050c13  mov     edx, [rbp+cchName]
0x180050c16  lea     rcx, [rbp+Name]
0x180050c1a  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180050c1f  nop
0x180050c20  mov     edx, [rbp+arg_0]
0x180050c23  lea     rcx, [rbp+var_30]
0x180050c27  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180050c2c  nop
0x180050c2d  mov     rax, [rbp+var_30]
0x180050c31  mov     [rsp+80h+peUse], rdi; peUse
0x180050c36  lea     rcx, [rbp+arg_0]
0x180050c3a  mov     [rsp+80h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180050c3f  mov     [rsp+80h+ReferencedDomainName], rax; ReferencedDomainName
0x180050c44  lea     r9, [rbp+cchName]; cchName
0x180050c48  mov     r8, [rbp+Name]; Name
0x180050c4c  mov     rdx, [rbp+Sid]; Sid
0x180050c50  xor     ecx, ecx; lpSystemName
0x180050c52  call    cs:__imp_LookupAccountSidW
0x180050c58  test    eax, eax
0x180050c5a  jnz     short loc_180050C86
0x180050c5c  mov     rcx, [rbp+18h]; this
0x180050c60  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050c67  lea     edx, [rax+6Fh]; void *
0x180050c6a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050c6f  mov     ebx, eax
0x180050c71  lea     rcx, [rbp+var_30]
0x180050c75  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180050c7a  nop
0x180050c7b  lea     rcx, [rbp+Name]
0x180050c7f  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180050c84  jmp     short loc_180050CCA
0x180050c86  mov     rcx, [rbp+Name]
0x180050c8a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180050c8f  mov     r8, rax
0x180050c92  mov     rdx, rcx
0x180050c95  mov     rcx, r14
0x180050c98  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180050c9d  mov     rcx, [rbp+var_30]
0x180050ca1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180050ca6  mov     r8, rax
0x180050ca9  mov     rdx, rcx
0x180050cac  mov     rcx, rsi
0x180050caf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180050cb4  nop
0x180050cb5  lea     rcx, [rbp+var_30]
0x180050cb9  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180050cbe  nop
0x180050cbf  lea     rcx, [rbp+Name]
0x180050cc3  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180050cc8  xor     ebx, ebx
0x180050cca  lea     rcx, [rbp+Sid]
0x180050cce  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050cd3  mov     eax, ebx
0x180050cd5  lea     r11, [rsp+80h+var_s0]
0x180050cdd  mov     rbx, [r11+28h]
0x180050ce1  mov     rsi, [r11+30h]
0x180050ce5  mov     rsp, r11
0x180050ce8  pop     r14
0x180050cea  pop     rdi
0x180050ceb  pop     rbp
0x180050cec  retn
```
