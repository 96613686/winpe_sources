# Csl::GrantVmGroupAccess(Csl::Path const &,ulong)

- ea: `0x18002ed40`
- end: `0x18002efb9`
- name: `?GrantVmGroupAccess@Csl@@YAJAEBVPath@1@K@Z`
- size: `633`
- prototype: `__int64 __fastcall(Csl *__hidden this, const struct Path *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180084b1c`
- `0x180085654`
- `0x1800c9334`

## callees

- `0x180004bd0`
- `0x18000da68`
- `0x18000da88`
- `0x18002ed40`
- `0x18002f2c8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002ee2e`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002ee2e`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002edee`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002edee`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ee56`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ee8a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ee56`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ee8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ee45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ee45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ee01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ee01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002edaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eec3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002edaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eec3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002ed7a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002ed7a`

## string_xrefs

- `0x18002ed8e`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002edd6`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002eeb2`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002eef5`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002ef50`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002ef6d`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Csl::GrantVmGroupAccess(Csl *this, const struct Path *a2)
{
  unsigned int v2; // r15d
  __int64 v4; // rdx
  const char *v5; // r9
  unsigned int LastError; // ebx
  int updated; // eax
  DWORD SidLengthRequired; // eax
  HLOCAL v10; // rax
  void *v11; // rsi
  void *v12; // rbx
  const char *v13; // r9
  __int64 v14; // rdx
  PDWORD SidSubAuthority; // rdi
  PDWORD v16; // rdi
  __int64 v17; // rdx
  int v18; // edi
  int v19; // eax
  int v20; // [rsp+20h] [rbp-30h]
  PSID Sid; // [rsp+30h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v2 = (unsigned int)a2;
  Sid = 0;
  if ( !ConvertStringSidToSidW(
          L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704",
          &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x27C,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                  v5);
LABEL_3:
    if ( Sid )
      LocalFree(Sid);
    return LastError;
  }
  updated = Csl::UpdateObjectAcl(this, v4, Sid, v2);
  LastError = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)(unsigned int)updated,
      v20);
    goto LABEL_3;
  }
  SidLengthRequired = GetSidLengthRequired(2u);
  v10 = LocalAlloc(0x40u, SidLengthRequired);
  v11 = v10;
  if ( !v10 )
  {
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)0x8007000ELL,
      v20);
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x287,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)(unsigned int)v18,
      v20);
LABEL_28:
    if ( Sid )
      LocalFree(Sid);
    return (unsigned int)v18;
  }
  v12 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( InitializeSid(v10, &pIdentifierAuthority, 2u) )
  {
    SetLastError(0);
    SidSubAuthority = GetSidSubAuthority(v11, 0);
    if ( GetLastError() )
    {
      v14 = 82;
    }
    else
    {
      *SidSubAuthority = 83;
      v16 = GetSidSubAuthority(v11, 1u);
      if ( !GetLastError() )
      {
        *v16 = 0;
        v12 = v11;
        goto LABEL_18;
      }
      v14 = 88;
    }
  }
  else
  {
    v14 = 75;
  }
  v18 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
          v13);
  LocalFree(v11);
  if ( v18 < 0 )
    goto LABEL_27;
LABEL_18:
  v19 = Csl::UpdateObjectAcl(this, v17, v12, v2);
  v18 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)(unsigned int)v19,
      v20);
    if ( v12 )
      LocalFree(v12);
    goto LABEL_28;
  }
  if ( v12 )
    LocalFree(v12);
  if ( Sid )
    LocalFree(Sid);
  return 0;
}

```

## disassembly

```asm
0x18002ed40  mov     [rsp-28h+arg_10], rbx
0x18002ed45  push    rbp
0x18002ed46  push    rsi
0x18002ed47  push    rdi
0x18002ed48  push    r14
0x18002ed4a  push    r15
0x18002ed4c  mov     rbp, rsp
0x18002ed4f  sub     rsp, 50h
0x18002ed53  mov     rax, cs:__security_cookie
0x18002ed5a  xor     rax, rsp
0x18002ed5d  mov     [rbp+var_10], rax
0x18002ed61  mov     r15d, edx
0x18002ed64  mov     [rbp+Sid], 0
0x18002ed6c  mov     r14, rcx
0x18002ed6f  lea     rdx, [rbp+Sid]; Sid
0x18002ed73  lea     rcx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x18002ed7a  call    cs:__imp_ConvertStringSidToSidW
0x18002ed81  nop     dword ptr [rax+rax+00h]
0x18002ed86  test    eax, eax
0x18002ed88  jnz     short loc_18002EDBD
0x18002ed8a  mov     rcx, [rbp+28h]; this
0x18002ed8e  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002ed95  mov     edx, 27Ch; void *
0x18002ed9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ed9f  mov     ebx, eax
0x18002eda1  mov     rcx, [rbp+Sid]; hMem
0x18002eda5  test    rcx, rcx
0x18002eda8  jz      short loc_18002EDB6
0x18002edaa  call    cs:__imp_LocalFree
0x18002edb1  nop     dword ptr [rax+rax+00h]
0x18002edb6  mov     eax, ebx
0x18002edb8  jmp     loc_18002EF98
0x18002edbd  mov     r8, [rbp+Sid]
0x18002edc1  mov     r9d, r15d
0x18002edc4  mov     rcx, r14
0x18002edc7  call    ?UpdateObjectAcl@Csl@@YAJAEBVPath@1@W4SecurityObjectType@1@PEAXKW4_ACCESS_MODE@@@Z; Csl::UpdateObjectAcl(Csl::Path const &,Csl::SecurityObjectType,void *,ulong,_ACCESS_MODE)
0x18002edcc  mov     ebx, eax
0x18002edce  test    eax, eax
0x18002edd0  jns     short loc_18002EDEC
0x18002edd2  mov     rcx, [rbp+28h]; this
0x18002edd6  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002eddd  mov     r9d, eax; char *
0x18002ede0  mov     edx, 283h; void *
0x18002ede5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002edea  jmp     short loc_18002EDA1
0x18002edec  mov     cl, 2; nSubAuthorityCount
0x18002edee  call    cs:__imp_GetSidLengthRequired
0x18002edf5  nop     dword ptr [rax+rax+00h]
0x18002edfa  mov     edx, eax; uBytes
0x18002edfc  mov     ecx, 40h ; '@'; uFlags
0x18002ee01  call    cs:__imp_LocalAlloc
0x18002ee08  nop     dword ptr [rax+rax+00h]
0x18002ee0d  mov     rsi, rax
0x18002ee10  test    rax, rax
0x18002ee13  jz      loc_18002EF4C
0x18002ee19  xor     ebx, ebx
0x18002ee1b  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18002ee21  mov     r8b, 2; nSubAuthorityCount
0x18002ee24  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18002ee27  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18002ee2b  mov     rcx, rax; Sid
0x18002ee2e  call    cs:__imp_InitializeSid
0x18002ee35  nop     dword ptr [rax+rax+00h]
0x18002ee3a  test    eax, eax
0x18002ee3c  jnz     short loc_18002EE43
0x18002ee3e  lea     edx, [rbx+4Bh]
0x18002ee41  jmp     short loc_18002EEAE
0x18002ee43  xor     ecx, ecx; dwErrCode
0x18002ee45  call    cs:__imp_SetLastError
0x18002ee4c  nop     dword ptr [rax+rax+00h]
0x18002ee51  xor     edx, edx; nSubAuthority
0x18002ee53  mov     rcx, rsi; pSid
0x18002ee56  call    cs:__imp_GetSidSubAuthority
0x18002ee5d  nop     dword ptr [rax+rax+00h]
0x18002ee62  mov     rdi, rax
0x18002ee65  call    cs:__imp_GetLastError
0x18002ee6c  nop     dword ptr [rax+rax+00h]
0x18002ee71  test    eax, eax
0x18002ee73  jz      short loc_18002EE7C
0x18002ee75  mov     edx, 52h ; 'R'
0x18002ee7a  jmp     short loc_18002EEAE
0x18002ee7c  mov     edx, 1; nSubAuthority
0x18002ee81  mov     dword ptr [rdi], 53h ; 'S'
0x18002ee87  mov     rcx, rsi; pSid
0x18002ee8a  call    cs:__imp_GetSidSubAuthority
0x18002ee91  nop     dword ptr [rax+rax+00h]
0x18002ee96  mov     rdi, rax
0x18002ee99  call    cs:__imp_GetLastError
0x18002eea0  nop     dword ptr [rax+rax+00h]
0x18002eea5  test    eax, eax
0x18002eea7  jz      short loc_18002EED8
0x18002eea9  mov     edx, 58h ; 'X'; void *
0x18002eeae  mov     rcx, [rbp+28h]; this
0x18002eeb2  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002eeb9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002eebe  mov     rcx, rsi; hMem
0x18002eec1  mov     edi, eax
0x18002eec3  call    cs:__imp_LocalFree
0x18002eeca  nop     dword ptr [rax+rax+00h]
0x18002eecf  test    edi, edi
0x18002eed1  jns     short loc_18002EEDD
0x18002eed3  jmp     loc_18002EF69
0x18002eed8  mov     [rdi], ebx
0x18002eeda  mov     rbx, rsi
0x18002eedd  mov     r9d, r15d
0x18002eee0  mov     r8, rbx
0x18002eee3  mov     rcx, r14
0x18002eee6  call    ?UpdateObjectAcl@Csl@@YAJAEBVPath@1@W4SecurityObjectType@1@PEAXKW4_ACCESS_MODE@@@Z; Csl::UpdateObjectAcl(Csl::Path const &,Csl::SecurityObjectType,void *,ulong,_ACCESS_MODE)
0x18002eeeb  mov     edi, eax
0x18002eeed  test    eax, eax
0x18002eeef  jns     short loc_18002EF1F
0x18002eef1  mov     rcx, [rbp+28h]; this
0x18002eef5  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002eefc  mov     r9d, eax; char *
0x18002eeff  mov     edx, 28Eh; void *
0x18002ef04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef09  test    rbx, rbx
0x18002ef0c  jz      short loc_18002EF81
0x18002ef0e  mov     rcx, rbx; hMem
0x18002ef11  call    cs:__imp_LocalFree
0x18002ef18  nop     dword ptr [rax+rax+00h]
0x18002ef1d  jmp     short loc_18002EF81
0x18002ef1f  test    rbx, rbx
0x18002ef22  jz      short loc_18002EF33
0x18002ef24  mov     rcx, rbx; hMem
0x18002ef27  call    cs:__imp_LocalFree
0x18002ef2e  nop     dword ptr [rax+rax+00h]
0x18002ef33  mov     rcx, [rbp+Sid]; hMem
0x18002ef37  test    rcx, rcx
0x18002ef3a  jz      short loc_18002EF48
0x18002ef3c  call    cs:__imp_LocalFree
0x18002ef43  nop     dword ptr [rax+rax+00h]
0x18002ef48  xor     eax, eax
0x18002ef4a  jmp     short loc_18002EF98
0x18002ef4c  mov     rcx, [rbp+28h]; this
0x18002ef50  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002ef57  mov     edi, 8007000Eh
0x18002ef5c  mov     edx, 45h ; 'E'; void *
0x18002ef61  mov     r9d, edi; char *
0x18002ef64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef69  mov     rcx, [rbp+28h]; this
0x18002ef6d  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002ef74  mov     r9d, edi; char *
0x18002ef77  mov     edx, 287h; void *
0x18002ef7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef81  mov     rcx, [rbp+Sid]; hMem
0x18002ef85  test    rcx, rcx
0x18002ef88  jz      short loc_18002EF96
0x18002ef8a  call    cs:__imp_LocalFree
0x18002ef91  nop     dword ptr [rax+rax+00h]
0x18002ef96  mov     eax, edi
0x18002ef98  mov     rcx, [rbp+var_10]
0x18002ef9c  xor     rcx, rsp; StackCookie
0x18002ef9f  call    __security_check_cookie
0x18002efa4  mov     rbx, [rsp+50h+arg_10]
0x18002efac  add     rsp, 50h
0x18002efb0  pop     r15
0x18002efb2  pop     r14
0x18002efb4  pop     rdi
0x18002efb5  pop     rsi
0x18002efb6  pop     rbp
0x18002efb7  retn
```
