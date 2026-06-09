# Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContextNoThrow

- ea: `0x180090648`
- end: `0x180090750`
- name: `Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContextNoThrow`
- size: `264`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180090a20`

## callees

- `0x180006770`
- `0x18001330c`
- `0x18001332c`
- `0x180013ac8`
- `0x180087ab4`
- `0x180090524`
- `0x180090648`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800906b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800906b7`

## pseudocode

```c
__int64 __fastcall Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContextNoThrow(
        unsigned __int16 *a1,
        WCHAR *a2)
{
  int token_information; // eax
  unsigned int v4; // ebx
  void *v6; // rbx
  const char *v7; // r9
  unsigned int LastError; // edi
  int v9; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPWSTR StringSid; // [rsp+38h] [rbp+10h] BYREF
  void *Block; // [rsp+40h] [rbp+18h] BYREF

  StringSid = a2;
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, (__int64)a2);
  v4 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\PenAndInkSettingsInternal.h",
      (const char *)(unsigned int)token_information,
      v10);
    if ( Block )
      operator delete(Block);
    return v4;
  }
  v6 = Block;
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x16,
                  (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\PenAndInkSettingsInternal.h",
                  v7);
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    if ( v6 )
      operator delete(v6);
    return LastError;
  }
  v9 = StringCchPrintfW(
         a1,
         0x400u,
         L"D:AI(A;CIIO;GR;;;AC)(A;CI;KR;;;AC)(A;CI;KR;;;S-1-15-3-1024-1065365936-1281604716-3511738428-1654721687-43273447"
          "9-3232135806-4053264122-3456934681)(A;OICIID;KA;;;%s)(A;OICIID;KR;;;RC)(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)",
         StringSid);
  LastError = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\PenAndInkSettingsInternal.h",
      (const char *)(unsigned int)v9,
      v10);
    goto LABEL_7;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  if ( v6 )
    operator delete(v6);
  return 0;
}

```

## disassembly

```asm
0x180090648  mov     rax, rsp
0x18009064b  mov     [rax+8], rbx
0x18009064f  mov     [rax+10h], rdx
0x180090653  push    rdi; int
0x180090654  sub     rsp, 20h
0x180090658  mov     rdi, rcx
0x18009065b  mov     qword ptr [rax+18h], 0
0x180090663  lea     rcx, [rax+18h]
0x180090667  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18009066c  mov     ebx, eax
0x18009066e  test    eax, eax
0x180090670  jns     short loc_1800906A1
0x180090672  mov     rcx, [rsp+28h]; this
0x180090677  lea     r8, aOnecoreuapWind_45; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18009067e  mov     r9d, eax; char *
0x180090681  mov     edx, 14h; void *
0x180090686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009068b  mov     rcx, [rsp+28h+Block]; Block
0x180090690  test    rcx, rcx
0x180090693  jz      short loc_18009069A
0x180090695  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009069a  mov     eax, ebx
0x18009069c  jmp     loc_180090745
0x1800906a1  mov     rbx, [rsp+28h+Block]
0x1800906a6  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800906ab  mov     [rsp+28h+StringSid], 0
0x1800906b4  mov     rcx, [rbx]; Sid
0x1800906b7  call    cs:__imp_ConvertSidToStringSidW
0x1800906bd  test    eax, eax
0x1800906bf  jnz     short loc_1800906F2
0x1800906c1  mov     rcx, [rsp+28h]; this
0x1800906c6  lea     r8, aOnecoreuapWind_45; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800906cd  lea     edx, [rax+16h]; void *
0x1800906d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800906d5  mov     edi, eax
0x1800906d7  lea     rcx, [rsp+28h+StringSid]
0x1800906dc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800906e1  test    rbx, rbx
0x1800906e4  jz      short loc_1800906EE
0x1800906e6  mov     rcx, rbx; Block
0x1800906e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800906ee  mov     eax, edi
0x1800906f0  jmp     short loc_180090745
0x1800906f2  mov     r9, [rsp+28h+StringSid]
0x1800906f7  lea     r8, aDAiACiioGrAcAC; "D:AI(A;CIIO;GR;;;AC)(A;CI;KR;;;AC)(A;CI"...
0x1800906fe  mov     edx, 400h; unsigned __int64
0x180090703  mov     rcx, rdi; unsigned __int16 *
0x180090706  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009070b  mov     edi, eax
0x18009070d  test    eax, eax
0x18009070f  jns     short loc_18009072C
0x180090711  mov     rcx, [rsp+28h]; this
0x180090716  lea     r8, aOnecoreuapWind_45; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18009071d  mov     r9d, eax; char *
0x180090720  mov     edx, 1Fh; void *
0x180090725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009072a  jmp     short loc_1800906D7
0x18009072c  lea     rcx, [rsp+28h+StringSid]
0x180090731  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180090736  test    rbx, rbx
0x180090739  jz      short loc_180090743
0x18009073b  mov     rcx, rbx; Block
0x18009073e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180090743  xor     eax, eax
0x180090745  mov     rbx, [rsp+28h+arg_0]
0x18009074a  add     rsp, 20h
0x18009074e  pop     rdi
0x18009074f  retn
```
