# Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContextNoThrow

- ea: `0x180013554`
- end: `0x18001365c`
- name: `Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContextNoThrow`
- size: `264`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800134b8`

## callees

- `0x1800035b0`
- `0x18000a29c`
- `0x18000a2bc`
- `0x18000ac78`
- `0x18000f9cc`
- `0x180010fa0`
- `0x180013554`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800135c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800135c3`

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
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\PenAndInkSettingsInternal.h",
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
                  (unsigned int)"onecoreuap\\internal\\sdk\\inc\\PenAndInkSettingsInternal.h",
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
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\PenAndInkSettingsInternal.h",
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
0x180013554  mov     rax, rsp
0x180013557  mov     [rax+8], rbx
0x18001355b  mov     [rax+10h], rdx
0x18001355f  push    rdi; int
0x180013560  sub     rsp, 20h
0x180013564  mov     rdi, rcx
0x180013567  mov     qword ptr [rax+18h], 0
0x18001356f  lea     rcx, [rax+18h]
0x180013573  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180013578  mov     ebx, eax
0x18001357a  test    eax, eax
0x18001357c  jns     short loc_1800135AD
0x18001357e  mov     rcx, [rsp+28h]; this
0x180013583  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\PenAndI"...
0x18001358a  mov     r9d, eax; char *
0x18001358d  mov     edx, 14h; void *
0x180013592  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013597  mov     rcx, [rsp+28h+Block]; Block
0x18001359c  test    rcx, rcx
0x18001359f  jz      short loc_1800135A6
0x1800135a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800135a6  mov     eax, ebx
0x1800135a8  jmp     loc_180013651
0x1800135ad  mov     rbx, [rsp+28h+Block]
0x1800135b2  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800135b7  mov     [rsp+28h+StringSid], 0
0x1800135c0  mov     rcx, [rbx]; Sid
0x1800135c3  call    cs:__imp_ConvertSidToStringSidW
0x1800135c9  test    eax, eax
0x1800135cb  jnz     short loc_1800135FE
0x1800135cd  mov     rcx, [rsp+28h]; this
0x1800135d2  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\PenAndI"...
0x1800135d9  lea     edx, [rax+16h]; void *
0x1800135dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800135e1  mov     edi, eax
0x1800135e3  lea     rcx, [rsp+28h+StringSid]
0x1800135e8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800135ed  test    rbx, rbx
0x1800135f0  jz      short loc_1800135FA
0x1800135f2  mov     rcx, rbx; Block
0x1800135f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800135fa  mov     eax, edi
0x1800135fc  jmp     short loc_180013651
0x1800135fe  mov     r9, [rsp+28h+StringSid]
0x180013603  lea     r8, aDAiACiioGrAcAC; "D:AI(A;CIIO;GR;;;AC)(A;CI;KR;;;AC)(A;CI"...
0x18001360a  mov     edx, 400h; unsigned __int64
0x18001360f  mov     rcx, rdi; unsigned __int16 *
0x180013612  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013617  mov     edi, eax
0x180013619  test    eax, eax
0x18001361b  jns     short loc_180013638
0x18001361d  mov     rcx, [rsp+28h]; this
0x180013622  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\sdk\\inc\\PenAndI"...
0x180013629  mov     r9d, eax; char *
0x18001362c  mov     edx, 1Fh; void *
0x180013631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013636  jmp     short loc_1800135E3
0x180013638  lea     rcx, [rsp+28h+StringSid]
0x18001363d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180013642  test    rbx, rbx
0x180013645  jz      short loc_18001364F
0x180013647  mov     rcx, rbx; Block
0x18001364a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001364f  xor     eax, eax
0x180013651  mov     rbx, [rsp+28h+arg_0]
0x180013656  add     rsp, 20h
0x18001365a  pop     rdi
0x18001365b  retn
```
