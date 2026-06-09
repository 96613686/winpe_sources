# ClipStorage::ResultAppliesToUser(_tagCLIP_LICENSE_DATA const &,ushort const *)

- ea: `0x180026a48`
- end: `0x180026b4e`
- name: `?ResultAppliesToUser@ClipStorage@@AEAA_NAEBU_tagCLIP_LICENSE_DATA@@PEBG@Z`
- size: `262`
- prototype: `bool(ClipStorage *__hidden this, const struct _tagCLIP_LICENSE_DATA *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800107b0`
- `0x180026b60`

## callees

- `0x180011960`
- `0x180026a48`
- `0x18008a400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026b3a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026b3a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026a89`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026a89`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180026af0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180026af0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180026ab5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180026ab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ClipStorage::ResultAppliesToUser(
        ClipStorage *this,
        const struct _tagCLIP_LICENSE_DATA *a2,
        const unsigned __int16 *a3)
{
  char v5; // bl
  const WCHAR *v6; // rcx
  const char *v7; // r9
  unsigned __int64 i; // rdi
  int LastError; // eax
  void **v11; // [rsp+30h] [rbp-38h] BYREF
  PSID Sid; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( *(_DWORD *)a2 != 6 )
    return 0;
  v5 = 1;
  v6 = *(const WCHAR **)((char *)a2 + 156);
  if ( !v6 )
    return v5;
  if ( !a3 )
    return 0;
  if ( CompareStringOrdinal(v6, -1, a3, -1, 0) != 2 )
  {
    v11 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    Sid = 0;
    if ( !ConvertStringSidToSidW(a3, &Sid) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x24C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\clipstorage.cpp",
        v7);
    v5 = 0;
    for ( i = 0; i < 2; ++i )
    {
      if ( EqualSid((char *)this + 68 * i + 32, Sid) )
      {
        v5 = 1;
        break;
      }
    }
    v11 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
    if ( Sid && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(&v11) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180026a48  push    rbx
0x180026a4a  push    rbp
0x180026a4b  push    rsi
0x180026a4c  push    rdi
0x180026a4d  sub     rsp, 48h
0x180026a51  mov     rdi, r8
0x180026a54  mov     rsi, rcx
0x180026a57  cmp     dword ptr [rdx], 6
0x180026a5a  jnz     loc_180026B41
0x180026a60  mov     bl, 1
0x180026a62  mov     rcx, [rdx+9Ch]; lpString1
0x180026a69  test    rcx, rcx
0x180026a6c  jz      loc_180026B43
0x180026a72  test    r8, r8
0x180026a75  jz      loc_180026B41
0x180026a7b  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x180026a83  or      edx, 0FFFFFFFFh; cchCount1
0x180026a86  mov     r9d, edx; cchCount2
0x180026a89  call    cs:__imp_CompareStringOrdinal
0x180026a8f  cmp     eax, 2
0x180026a92  jz      loc_180026B43
0x180026a98  lea     rbp, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180026a9f  mov     [rsp+68h+var_38], rbp
0x180026aa4  mov     [rsp+68h+Sid], 0
0x180026aad  lea     rdx, [rsp+68h+Sid]; Sid
0x180026ab2  mov     rcx, rdi; StringSid
0x180026ab5  call    cs:__imp_ConvertStringSidToSidW
0x180026abb  mov     rcx, [rsp+68h]; this
0x180026ac0  test    eax, eax
0x180026ac2  jnz     short loc_180026AD6
0x180026ac4  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\licensem"...
0x180026acb  mov     edx, 24Ch; void *
0x180026ad0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180026ad6  xor     bl, bl
0x180026ad8  xor     edi, edi
0x180026ada  cmp     rdi, 2
0x180026ade  jnb     short loc_180026B01
0x180026ae0  imul    rcx, rdi, 44h ; 'D'
0x180026ae4  add     rcx, 20h ; ' '
0x180026ae8  add     rcx, rsi; pSid1
0x180026aeb  mov     rdx, [rsp+68h+Sid]; pSid2
0x180026af0  call    cs:__imp_EqualSid
0x180026af6  test    eax, eax
0x180026af8  jnz     short loc_180026AFF
0x180026afa  inc     rdi
0x180026afd  jmp     short loc_180026ADA
0x180026aff  mov     bl, 1
0x180026b01  mov     [rsp+68h+var_38], rbp
0x180026b06  cmp     [rsp+68h+Sid], 0
0x180026b0c  jz      short loc_180026B43
0x180026b0e  lea     rcx, [rsp+68h+var_38]
0x180026b13  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x180026b18  test    al, al
0x180026b1a  jnz     short loc_180026B43
0x180026b1c  call    cs:__imp_GetLastError
0x180026b22  test    eax, eax
0x180026b24  jle     short loc_180026B2E
0x180026b26  movzx   eax, ax
0x180026b29  or      eax, 80070000h
0x180026b2e  xor     r9d, r9d; lpArguments
0x180026b31  xor     r8d, r8d; nNumberOfArguments
0x180026b34  lea     edx, [r9+1]; dwExceptionFlags
0x180026b38  mov     ecx, eax; dwExceptionCode
0x180026b3a  call    cs:__imp_RaiseException
0x180026b40  int     3; Trap to Debugger
0x180026b41  xor     bl, bl
0x180026b43  mov     al, bl
0x180026b45  add     rsp, 48h
0x180026b49  pop     rdi
0x180026b4a  pop     rsi
0x180026b4b  pop     rbp
0x180026b4c  pop     rbx
0x180026b4d  retn
```
