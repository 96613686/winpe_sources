# TakeOwnership(ushort *)

- ea: `0x180028768`
- end: `0x180028b03`
- name: `?TakeOwnership@@YAJPEAG@Z`
- size: `923`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800246b8`

## callees

- `0x18000d3bc`
- `0x180028154`
- `0x180028768`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002889d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002892b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002889d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002892b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800288bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002894a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800288bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002894a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002880d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180028907`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180028990`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002880d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180028907`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180028990`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028854`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002886a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028880`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800288ae`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002893c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028aa4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028aba`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028ad0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028854`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002886a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028880`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800288ae`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002893c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028aa4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028aba`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028ad0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002883e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028a8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002883e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028a8e`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180028a6d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180028a6d`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180028a1c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180028a1c`

## string_xrefs

- `0x180028826`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180028a35`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

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
0x180028768  mov     [rsp-8+arg_8], rbx
0x18002876d  mov     [rsp-8+arg_10], rsi
0x180028772  push    rbp
0x180028773  push    rdi
0x180028774  push    r14
0x180028776  lea     rbp, [rsp-40h]
0x18002877b  sub     rsp, 140h
0x180028782  mov     rax, cs:__security_cookie
0x180028789  xor     rax, rsp
0x18002878c  mov     [rbp+50h+var_20], rax
0x180028790  xor     r14d, r14d
0x180028793  mov     word ptr [rbp+50h+pIdentifierAuthority.Value+4], 100h
0x180028799  mov     rsi, rcx
0x18002879c  mov     [rsp+150h+var_E8], r14
0x1800287a1  lea     rcx, [rbp+50h+pListOfExplicitEntries]; void *
0x1800287a5  mov     [rsp+150h+var_F0], r14
0x1800287aa  xor     edx, edx; Val
0x1800287ac  mov     [rsp+150h+hMem], r14
0x1800287b1  mov     r8d, 90h; Size
0x1800287b7  mov     dword ptr [rbp+50h+pIdentifierAuthority.Value], r14d
0x1800287bb  mov     dword ptr [rbp+50h+var_C8.Value], r14d
0x1800287bf  mov     dword ptr [rbp+50h+var_C0.Value], r14d
0x1800287c3  mov     word ptr [rbp+50h+var_C8.Value+4], 500h
0x1800287c9  mov     word ptr [rbp+50h+var_C0.Value+4], 500h
0x1800287cf  call    memset_0
0x1800287d4  lea     rax, [rsp+150h+var_D8]
0x1800287d9  mov     [rsp+150h+var_D8], r14
0x1800287de  mov     [rsp+150h+pSid], rax; pSid
0x1800287e3  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x1800287e7  mov     [rsp+150h+nSubAuthority7], r14d; nSubAuthority7
0x1800287ec  xor     r9d, r9d; nSubAuthority1
0x1800287ef  mov     [rsp+150h+nSubAuthority6], r14d; nSubAuthority6
0x1800287f4  xor     r8d, r8d; nSubAuthority0
0x1800287f7  mov     [rsp+150h+nSubAuthority5], r14d; nSubAuthority5
0x1800287fc  mov     dl, 1; nSubAuthorityCount
0x1800287fe  mov     [rsp+150h+nSubAuthority4], r14d; nSubAuthority4
0x180028803  mov     [rsp+150h+nSubAuthority3], r14d; nSubAuthority3
0x180028808  mov     [rsp+150h+nSubAuthority2], r14d; nSubAuthority2
0x18002880d  call    cs:__imp_AllocateAndInitializeSid
0x180028814  nop     dword ptr [rax+rax+00h]
0x180028819  test    eax, eax
0x18002881b  jnz     short loc_180028893
0x18002881d  mov     edx, 8Ah; void *
0x180028822  mov     rcx, [rbp+58h]; this
0x180028826  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002882d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028832  mov     rcx, [rsp+150h+hMem]; hMem
0x180028837  mov     ebx, eax
0x180028839  test    rcx, rcx
0x18002883c  jz      short loc_18002884A
0x18002883e  call    cs:__imp_LocalFree
0x180028845  nop     dword ptr [rax+rax+00h]
0x18002884a  mov     rcx, [rsp+150h+var_D8]; pSid
0x18002884f  test    rcx, rcx
0x180028852  jz      short loc_180028860
0x180028854  call    cs:__imp_FreeSid
0x18002885b  nop     dword ptr [rax+rax+00h]
0x180028860  mov     rcx, [rsp+150h+var_F0]; pSid
0x180028865  test    rcx, rcx
0x180028868  jz      short loc_180028876
0x18002886a  call    cs:__imp_FreeSid
0x180028871  nop     dword ptr [rax+rax+00h]
0x180028876  mov     rcx, [rsp+150h+var_E8]; pSid
0x18002887b  test    rcx, rcx
0x18002887e  jz      short loc_18002888C
0x180028880  call    cs:__imp_FreeSid
0x180028887  nop     dword ptr [rax+rax+00h]
0x18002888c  mov     eax, ebx
0x18002888e  jmp     loc_180028ADE
0x180028893  mov     rdi, [rsp+150h+var_E8]
0x180028898  test    rdi, rdi
0x18002889b  jz      short loc_1800288C8
0x18002889d  call    cs:__imp_GetLastError
0x1800288a4  nop     dword ptr [rax+rax+00h]
0x1800288a9  mov     rcx, rdi; pSid
0x1800288ac  mov     ebx, eax
0x1800288ae  call    cs:__imp_FreeSid
0x1800288b5  nop     dword ptr [rax+rax+00h]
0x1800288ba  mov     ecx, ebx; dwErrCode
0x1800288bc  call    cs:__imp_SetLastError
0x1800288c3  nop     dword ptr [rax+rax+00h]
0x1800288c8  lea     rax, [rsp+150h+var_E8]
0x1800288cd  mov     [rsp+150h+var_E8], r14
0x1800288d2  mov     [rsp+150h+pSid], rax; pSid
0x1800288d7  lea     rcx, [rbp+50h+var_C8]; pIdentifierAuthority
0x1800288db  mov     [rsp+150h+nSubAuthority7], r14d; nSubAuthority7
0x1800288e0  mov     r9d, 220h; nSubAuthority1
0x1800288e6  mov     [rsp+150h+nSubAuthority6], r14d; nSubAuthority6
0x1800288eb  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800288f1  mov     [rsp+150h+nSubAuthority5], r14d; nSubAuthority5
0x1800288f6  mov     dl, 2; nSubAuthorityCount
0x1800288f8  mov     [rsp+150h+nSubAuthority4], r14d; nSubAuthority4
0x1800288fd  mov     [rsp+150h+nSubAuthority3], r14d; nSubAuthority3
0x180028902  mov     [rsp+150h+nSubAuthority2], r14d; nSubAuthority2
0x180028907  call    cs:__imp_AllocateAndInitializeSid
0x18002890e  nop     dword ptr [rax+rax+00h]
0x180028913  test    eax, eax
0x180028915  jnz     short loc_180028921
0x180028917  mov     edx, 91h
0x18002891c  jmp     loc_180028822
0x180028921  mov     rdi, [rsp+150h+var_F0]
0x180028926  test    rdi, rdi
0x180028929  jz      short loc_180028956
0x18002892b  call    cs:__imp_GetLastError
0x180028932  nop     dword ptr [rax+rax+00h]
0x180028937  mov     rcx, rdi; pSid
0x18002893a  mov     ebx, eax
0x18002893c  call    cs:__imp_FreeSid
0x180028943  nop     dword ptr [rax+rax+00h]
0x180028948  mov     ecx, ebx; dwErrCode
0x18002894a  call    cs:__imp_SetLastError
0x180028951  nop     dword ptr [rax+rax+00h]
0x180028956  lea     rax, [rsp+150h+var_F0]
0x18002895b  mov     [rsp+150h+var_F0], r14
0x180028960  mov     [rsp+150h+pSid], rax; pSid
0x180028965  lea     rcx, [rbp+50h+var_C0]; pIdentifierAuthority
0x180028969  mov     [rsp+150h+nSubAuthority7], r14d; nSubAuthority7
0x18002896e  xor     r9d, r9d; nSubAuthority1
0x180028971  mov     [rsp+150h+nSubAuthority6], r14d; nSubAuthority6
0x180028976  mov     dl, 1; nSubAuthorityCount
0x180028978  mov     [rsp+150h+nSubAuthority5], r14d; nSubAuthority5
0x18002897d  mov     [rsp+150h+nSubAuthority4], r14d; nSubAuthority4
0x180028982  mov     [rsp+150h+nSubAuthority3], r14d; nSubAuthority3
0x180028987  lea     r8d, [r9+12h]; nSubAuthority0
0x18002898b  mov     [rsp+150h+nSubAuthority2], r14d; unsigned int
0x180028990  call    cs:__imp_AllocateAndInitializeSid
0x180028997  nop     dword ptr [rax+rax+00h]
0x18002899c  test    eax, eax
0x18002899e  jnz     short loc_1800289AA
0x1800289a0  mov     edx, 97h
0x1800289a5  jmp     loc_180028822
0x1800289aa  mov     rax, [rsp+150h+var_D8]
0x1800289af  lea     r9, [rsp+150h+hMem]; NewAcl
0x1800289b4  mov     edx, 10010000h
0x1800289b9  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800289bd  mov     rax, [rsp+150h+var_E8]
0x1800289c2  xor     r8d, r8d; OldAcl
0x1800289c5  mov     [rbp+50h+var_58], rax
0x1800289c9  mov     rax, [rsp+150h+var_F0]
0x1800289ce  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], edx
0x1800289d1  mov     [rbp+50h+var_80], edx
0x1800289d4  lea     ecx, [r8+3]; cCountOfExplicitEntries
0x1800289d8  mov     [rbp+50h+var_50], edx
0x1800289db  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800289df  mov     [rbp+50h+var_28], rax
0x1800289e3  mov     qword ptr [rbp+50h+pListOfExplicitEntries.grfAccessMode], 4
0x1800289eb  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x1800289ef  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1800289f6  mov     [rbp+50h+var_7C], 4
0x1800289fe  mov     [rbp+50h+var_64], r14d
0x180028a02  mov     [rbp+50h+var_60], 2
0x180028a09  mov     [rbp+50h+var_4C], 2
0x180028a11  mov     [rbp+50h+var_34], r14d
0x180028a15  mov     [rbp+50h+var_30], 8
0x180028a1c  call    cs:__imp_SetEntriesInAclW
0x180028a23  nop     dword ptr [rax+rax+00h]
0x180028a28  test    eax, eax
0x180028a2a  jz      short loc_180028A49
0x180028a2c  mov     edx, 0B1h; void *
0x180028a31  mov     rcx, [rbp+58h]; this
0x180028a35  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028a3c  mov     r9d, eax; char *
0x180028a3f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028a44  jmp     loc_180028832
0x180028a49  mov     rax, [rsp+150h+hMem]
0x180028a4e  xor     r9d, r9d; psidOwner
0x180028a51  mov     qword ptr [rsp+150h+nSubAuthority4], r14; pSacl
0x180028a56  mov     r8d, 80000004h; SecurityInfo
0x180028a5c  mov     qword ptr [rsp+150h+nSubAuthority3], rax; pDacl
0x180028a61  mov     rcx, rsi; pObjectName
0x180028a64  mov     qword ptr [rsp+150h+nSubAuthority2], r14; psidGroup
0x180028a69  lea     edx, [r9+1]; ObjectType
0x180028a6d  call    cs:__imp_SetNamedSecurityInfoW
0x180028a74  nop     dword ptr [rax+rax+00h]
0x180028a79  test    eax, eax
0x180028a7b  jz      short loc_180028A84
0x180028a7d  mov     edx, 0BAh
0x180028a82  jmp     short loc_180028A31
0x180028a84  mov     rcx, [rsp+150h+hMem]; hMem
0x180028a89  test    rcx, rcx
0x180028a8c  jz      short loc_180028A9A
0x180028a8e  call    cs:__imp_LocalFree
0x180028a95  nop     dword ptr [rax+rax+00h]
0x180028a9a  mov     rcx, [rsp+150h+var_D8]; pSid
0x180028a9f  test    rcx, rcx
0x180028aa2  jz      short loc_180028AB0
0x180028aa4  call    cs:__imp_FreeSid
0x180028aab  nop     dword ptr [rax+rax+00h]
0x180028ab0  mov     rcx, [rsp+150h+var_F0]; pSid
0x180028ab5  test    rcx, rcx
0x180028ab8  jz      short loc_180028AC6
0x180028aba  call    cs:__imp_FreeSid
0x180028ac1  nop     dword ptr [rax+rax+00h]
0x180028ac6  mov     rcx, [rsp+150h+var_E8]; pSid
0x180028acb  test    rcx, rcx
0x180028ace  jz      short loc_180028ADC
0x180028ad0  call    cs:__imp_FreeSid
0x180028ad7  nop     dword ptr [rax+rax+00h]
0x180028adc  xor     eax, eax
0x180028ade  mov     rcx, [rbp+50h+var_20]
0x180028ae2  xor     rcx, rsp; StackCookie
0x180028ae5  call    __security_check_cookie
0x180028aea  lea     r11, [rsp+150h+var_10]
0x180028af2  mov     rbx, [r11+28h]
0x180028af6  mov     rsi, [r11+30h]
0x180028afa  mov     rsp, r11
0x180028afd  pop     r14
0x180028aff  pop     rdi
0x180028b00  pop     rbp
0x180028b01  retn
```
