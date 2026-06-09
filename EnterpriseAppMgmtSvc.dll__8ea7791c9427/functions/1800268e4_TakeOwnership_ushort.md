# TakeOwnership(ushort *)

- ea: `0x1800268e4`
- end: `0x180026c0c`
- name: `?TakeOwnership@@YAJPEAG@Z`
- size: `808`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022df8`

## callees

- `0x18000cfc8`
- `0x18002636c`
- `0x1800268e4`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026a84`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026989`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026a53`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026ac4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026989`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026a53`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180026ac4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800269c4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800269d4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800269e4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026a06`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026a7c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026bc0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026bd0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026be0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800269c4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800269d4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800269e4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026a06`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026a7c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026bc0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026bd0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026be0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026bb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026bb0`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180026b95`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180026b95`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180026b4a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180026b4a`

## string_xrefs

- `0x18002699c`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180026b5d`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
__int64 __fastcall TakeOwnership(LPWSTR pObjectName)
{
  const char *v2; // r9
  __int64 v3; // rdx
  int LastError; // eax
  unsigned int v5; // ebx
  DWORD v7; // eax
  __int64 v8; // rdx
  unsigned int nSubAuthority2; // [rsp+20h] [rbp-E0h]
  PSID v10; // [rsp+60h] [rbp-A0h] BYREF
  PSID v11; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid; // [rsp+78h] [rbp-88h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp-80h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v15; // [rsp+88h] [rbp-78h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v16; // [rsp+90h] [rbp-70h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A0h] [rbp-60h] BYREF
  int v18; // [rsp+D0h] [rbp-30h]
  __int64 v19; // [rsp+D4h] [rbp-2Ch]
  int v20; // [rsp+ECh] [rbp-14h]
  int v21; // [rsp+F0h] [rbp-10h]
  PSID v22; // [rsp+F8h] [rbp-8h]
  int v23; // [rsp+100h] [rbp+0h]
  __int64 v24; // [rsp+104h] [rbp+4h]
  int v25; // [rsp+11Ch] [rbp+1Ch]
  int v26; // [rsp+120h] [rbp+20h]
  PSID v27; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  v11 = 0;
  v10 = 0;
  hMem = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_DWORD *)v15.Value = 0;
  *(_DWORD *)v16.Value = 0;
  *(_WORD *)&v15.Value[4] = 1280;
  *(_WORD *)&v16.Value[4] = 1280;
  memset_0(&pListOfExplicitEntries, 0, 0x90u);
  pSid = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v3 = 138;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v3,
                  (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\"
                                "packagemanager.cpp",
                  v2);
LABEL_4:
    v5 = LastError;
    if ( hMem )
      LocalFree(hMem);
    if ( pSid )
      FreeSid(pSid);
    if ( v10 )
      FreeSid(v10);
    if ( v11 )
      FreeSid(v11);
    return v5;
  }
  v11 = 0;
  if ( !AllocateAndInitializeSid(&v15, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v11) )
  {
    v3 = 145;
    goto LABEL_3;
  }
  v10 = 0;
  if ( !AllocateAndInitializeSid(&v16, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v10) )
  {
    v3 = 151;
    goto LABEL_3;
  }
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  v22 = v11;
  pListOfExplicitEntries.grfAccessPermissions = 268500992;
  v18 = 268500992;
  v23 = 268500992;
  v27 = v10;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 4;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  v19 = 4;
  v20 = 0;
  v21 = 2;
  v24 = 2;
  v25 = 0;
  v26 = 8;
  v7 = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, (PACL *)&hMem);
  if ( v7 )
  {
    v8 = 177;
LABEL_19:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\"
                                "packagemanager.cpp",
                  (const char *)v7,
                  nSubAuthority2);
    goto LABEL_4;
  }
  v7 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000004, 0, 0, (PACL)hMem, 0);
  if ( v7 )
  {
    v8 = 186;
    goto LABEL_19;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( pSid )
    FreeSid(pSid);
  if ( v10 )
    FreeSid(v10);
  if ( v11 )
    FreeSid(v11);
  return 0;
}

```

## disassembly

```asm
0x1800268e4  mov     [rsp-8+arg_8], rbx
0x1800268e9  mov     [rsp-8+arg_10], rsi
0x1800268ee  push    rbp
0x1800268ef  push    rdi
0x1800268f0  push    r14
0x1800268f2  lea     rbp, [rsp-40h]
0x1800268f7  sub     rsp, 140h
0x1800268fe  mov     rax, cs:__security_cookie
0x180026905  xor     rax, rsp
0x180026908  mov     [rbp+50h+var_20], rax
0x18002690c  xor     r14d, r14d
0x18002690f  mov     word ptr [rbp+50h+pIdentifierAuthority.Value+4], 100h
0x180026915  mov     rsi, rcx
0x180026918  mov     [rsp+150h+var_E8], r14
0x18002691d  lea     rcx, [rbp+50h+pListOfExplicitEntries]; void *
0x180026921  mov     [rsp+150h+var_F0], r14
0x180026926  xor     edx, edx; Val
0x180026928  mov     [rsp+150h+hMem], r14
0x18002692d  mov     r8d, 90h; Size
0x180026933  mov     dword ptr [rbp+50h+pIdentifierAuthority.Value], r14d
0x180026937  mov     dword ptr [rbp+50h+var_C8.Value], r14d
0x18002693b  mov     dword ptr [rbp+50h+var_C0.Value], r14d
0x18002693f  mov     word ptr [rbp+50h+var_C8.Value+4], 500h
0x180026945  mov     word ptr [rbp+50h+var_C0.Value+4], 500h
0x18002694b  call    memset_0
0x180026950  lea     rax, [rsp+150h+var_D8]
0x180026955  mov     [rsp+150h+var_D8], r14
0x18002695a  mov     [rsp+150h+pSid], rax; pSid
0x18002695f  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x180026963  mov     [rsp+150h+nSubAuthority7], r14d; nSubAuthority7
0x180026968  xor     r9d, r9d; nSubAuthority1
0x18002696b  mov     [rsp+150h+nSubAuthority6], r14d; nSubAuthority6
0x180026970  xor     r8d, r8d; nSubAuthority0
0x180026973  mov     [rsp+150h+nSubAuthority5], r14d; nSubAuthority5
0x180026978  mov     dl, 1; nSubAuthorityCount
0x18002697a  mov     [rsp+150h+nSubAuthority4], r14d; nSubAuthority4
0x18002697f  mov     [rsp+150h+nSubAuthority3], r14d; nSubAuthority3
0x180026984  mov     [rsp+150h+nSubAuthority2], r14d; nSubAuthority2
0x180026989  call    cs:__imp_AllocateAndInitializeSid
0x18002698f  test    eax, eax
0x180026991  jnz     short loc_1800269F1
0x180026993  mov     edx, 8Ah; void *
0x180026998  mov     rcx, [rbp+58h]; this
0x18002699c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800269a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800269a8  mov     rcx, [rsp+150h+hMem]; hMem
0x1800269ad  mov     ebx, eax
0x1800269af  test    rcx, rcx
0x1800269b2  jz      short loc_1800269BA
0x1800269b4  call    cs:__imp_LocalFree
0x1800269ba  mov     rcx, [rsp+150h+var_D8]; pSid
0x1800269bf  test    rcx, rcx
0x1800269c2  jz      short loc_1800269CA
0x1800269c4  call    cs:__imp_FreeSid
0x1800269ca  mov     rcx, [rsp+150h+var_F0]; pSid
0x1800269cf  test    rcx, rcx
0x1800269d2  jz      short loc_1800269DA
0x1800269d4  call    cs:__imp_FreeSid
0x1800269da  mov     rcx, [rsp+150h+var_E8]; pSid
0x1800269df  test    rcx, rcx
0x1800269e2  jz      short loc_1800269EA
0x1800269e4  call    cs:__imp_FreeSid
0x1800269ea  mov     eax, ebx
0x1800269ec  jmp     loc_180026BE8
0x1800269f1  mov     rdi, [rsp+150h+var_E8]
0x1800269f6  test    rdi, rdi
0x1800269f9  jz      short loc_180026A14
0x1800269fb  call    cs:__imp_GetLastError
0x180026a01  mov     rcx, rdi; pSid
0x180026a04  mov     ebx, eax
0x180026a06  call    cs:__imp_FreeSid
0x180026a0c  mov     ecx, ebx; dwErrCode
0x180026a0e  call    cs:__imp_SetLastError
0x180026a14  lea     rax, [rsp+150h+var_E8]
0x180026a19  mov     [rsp+150h+var_E8], r14
0x180026a1e  mov     [rsp+150h+pSid], rax; pSid
0x180026a23  lea     rcx, [rbp+50h+var_C8]; pIdentifierAuthority
0x180026a27  mov     [rsp+150h+nSubAuthority7], r14d; nSubAuthority7
0x180026a2c  mov     r9d, 220h; nSubAuthority1
0x180026a32  mov     [rsp+150h+nSubAuthority6], r14d; nSubAuthority6
0x180026a37  mov     r8d, 20h ; ' '; nSubAuthority0
0x180026a3d  mov     [rsp+150h+nSubAuthority5], r14d; nSubAuthority5
0x180026a42  mov     dl, 2; nSubAuthorityCount
0x180026a44  mov     [rsp+150h+nSubAuthority4], r14d; nSubAuthority4
0x180026a49  mov     [rsp+150h+nSubAuthority3], r14d; nSubAuthority3
0x180026a4e  mov     [rsp+150h+nSubAuthority2], r14d; nSubAuthority2
0x180026a53  call    cs:__imp_AllocateAndInitializeSid
0x180026a59  test    eax, eax
0x180026a5b  jnz     short loc_180026A67
0x180026a5d  mov     edx, 91h
0x180026a62  jmp     loc_180026998
0x180026a67  mov     rdi, [rsp+150h+var_F0]
0x180026a6c  test    rdi, rdi
0x180026a6f  jz      short loc_180026A8A
0x180026a71  call    cs:__imp_GetLastError
0x180026a77  mov     rcx, rdi; pSid
0x180026a7a  mov     ebx, eax
0x180026a7c  call    cs:__imp_FreeSid
0x180026a82  mov     ecx, ebx; dwErrCode
0x180026a84  call    cs:__imp_SetLastError
0x180026a8a  lea     rax, [rsp+150h+var_F0]
0x180026a8f  mov     [rsp+150h+var_F0], r14
0x180026a94  mov     [rsp+150h+pSid], rax; pSid
0x180026a99  lea     rcx, [rbp+50h+var_C0]; pIdentifierAuthority
0x180026a9d  mov     [rsp+150h+nSubAuthority7], r14d; nSubAuthority7
0x180026aa2  xor     r9d, r9d; nSubAuthority1
0x180026aa5  mov     [rsp+150h+nSubAuthority6], r14d; nSubAuthority6
0x180026aaa  mov     dl, 1; nSubAuthorityCount
0x180026aac  mov     [rsp+150h+nSubAuthority5], r14d; nSubAuthority5
0x180026ab1  mov     [rsp+150h+nSubAuthority4], r14d; nSubAuthority4
0x180026ab6  mov     [rsp+150h+nSubAuthority3], r14d; nSubAuthority3
0x180026abb  lea     r8d, [r9+12h]; nSubAuthority0
0x180026abf  mov     [rsp+150h+nSubAuthority2], r14d; unsigned int
0x180026ac4  call    cs:__imp_AllocateAndInitializeSid
0x180026aca  test    eax, eax
0x180026acc  jnz     short loc_180026AD8
0x180026ace  mov     edx, 97h
0x180026ad3  jmp     loc_180026998
0x180026ad8  mov     rax, [rsp+150h+var_D8]
0x180026add  lea     r9, [rsp+150h+hMem]; NewAcl
0x180026ae2  mov     edx, 10010000h
0x180026ae7  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180026aeb  mov     rax, [rsp+150h+var_E8]
0x180026af0  xor     r8d, r8d; OldAcl
0x180026af3  mov     [rbp+50h+var_58], rax
0x180026af7  mov     rax, [rsp+150h+var_F0]
0x180026afc  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], edx
0x180026aff  mov     [rbp+50h+var_80], edx
0x180026b02  lea     ecx, [r8+3]; cCountOfExplicitEntries
0x180026b06  mov     [rbp+50h+var_50], edx
0x180026b09  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180026b0d  mov     [rbp+50h+var_28], rax
0x180026b11  mov     qword ptr [rbp+50h+pListOfExplicitEntries.grfAccessMode], 4
0x180026b19  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x180026b1d  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x180026b24  mov     [rbp+50h+var_7C], 4
0x180026b2c  mov     [rbp+50h+var_64], r14d
0x180026b30  mov     [rbp+50h+var_60], 2
0x180026b37  mov     [rbp+50h+var_4C], 2
0x180026b3f  mov     [rbp+50h+var_34], r14d
0x180026b43  mov     [rbp+50h+var_30], 8
0x180026b4a  call    cs:__imp_SetEntriesInAclW
0x180026b50  test    eax, eax
0x180026b52  jz      short loc_180026B71
0x180026b54  mov     edx, 0B1h; void *
0x180026b59  mov     rcx, [rbp+58h]; this
0x180026b5d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026b64  mov     r9d, eax; char *
0x180026b67  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026b6c  jmp     loc_1800269A8
0x180026b71  mov     rax, [rsp+150h+hMem]
0x180026b76  xor     r9d, r9d; psidOwner
0x180026b79  mov     qword ptr [rsp+150h+nSubAuthority4], r14; pSacl
0x180026b7e  mov     r8d, 80000004h; SecurityInfo
0x180026b84  mov     qword ptr [rsp+150h+nSubAuthority3], rax; pDacl
0x180026b89  mov     rcx, rsi; pObjectName
0x180026b8c  mov     qword ptr [rsp+150h+nSubAuthority2], r14; psidGroup
0x180026b91  lea     edx, [r9+1]; ObjectType
0x180026b95  call    cs:__imp_SetNamedSecurityInfoW
0x180026b9b  test    eax, eax
0x180026b9d  jz      short loc_180026BA6
0x180026b9f  mov     edx, 0BAh
0x180026ba4  jmp     short loc_180026B59
0x180026ba6  mov     rcx, [rsp+150h+hMem]; hMem
0x180026bab  test    rcx, rcx
0x180026bae  jz      short loc_180026BB6
0x180026bb0  call    cs:__imp_LocalFree
0x180026bb6  mov     rcx, [rsp+150h+var_D8]; pSid
0x180026bbb  test    rcx, rcx
0x180026bbe  jz      short loc_180026BC6
0x180026bc0  call    cs:__imp_FreeSid
0x180026bc6  mov     rcx, [rsp+150h+var_F0]; pSid
0x180026bcb  test    rcx, rcx
0x180026bce  jz      short loc_180026BD6
0x180026bd0  call    cs:__imp_FreeSid
0x180026bd6  mov     rcx, [rsp+150h+var_E8]; pSid
0x180026bdb  test    rcx, rcx
0x180026bde  jz      short loc_180026BE6
0x180026be0  call    cs:__imp_FreeSid
0x180026be6  xor     eax, eax
0x180026be8  mov     rcx, [rbp+50h+var_20]
0x180026bec  xor     rcx, rsp; StackCookie
0x180026bef  call    __security_check_cookie
0x180026bf4  lea     r11, [rsp+150h+var_10]
0x180026bfc  mov     rbx, [r11+28h]
0x180026c00  mov     rsi, [r11+30h]
0x180026c04  mov     rsp, r11
0x180026c07  pop     r14
0x180026c09  pop     rdi
0x180026c0a  pop     rbp
0x180026c0b  retn
```
