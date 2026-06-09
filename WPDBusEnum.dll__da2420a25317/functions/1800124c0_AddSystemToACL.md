# AddSystemToACL

- ea: `0x1800124c0`
- end: `0x1800127e3`
- name: `AddSystemToACL`
- size: `803`
- prototype: `__int64 __fastcall(PACL OldAcl, PACL *NewAcl)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001396c`

## callees

- `0x1800097d0`
- `0x18000a192`
- `0x1800124c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001276b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001277b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001278b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001279b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800127aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800127b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001276b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001277b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001278b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001279b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800127aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800127b9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001254d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012591`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800125ca`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012601`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001263e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001267a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001254d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012591`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800125ca`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012601`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001263e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001267a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180012759`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180012759`

## pseudocode

```c
__int64 __fastcall AddSystemToACL(PACL OldAcl, PACL *NewAcl)
{
  DWORD LastError; // eax
  ULONG v5; // ecx
  DWORD v6; // ebx
  PSID hMem; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid; // [rsp+68h] [rbp-98h] BYREF
  PSID v10; // [rsp+70h] [rbp-90h] BYREF
  PSID v11; // [rsp+78h] [rbp-88h] BYREF
  PSID v12; // [rsp+80h] [rbp-80h] BYREF
  PSID v13; // [rsp+88h] [rbp-78h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp-70h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v15; // [rsp+98h] [rbp-68h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A0h] [rbp-60h] BYREF
  int v17; // [rsp+D0h] [rbp-30h]
  __int64 v18; // [rsp+D4h] [rbp-2Ch]
  int v19; // [rsp+ECh] [rbp-14h]
  int v20; // [rsp+F0h] [rbp-10h]
  PSID v21; // [rsp+F8h] [rbp-8h]
  int v22; // [rsp+100h] [rbp+0h]
  __int64 v23; // [rsp+104h] [rbp+4h]
  int v24; // [rsp+11Ch] [rbp+1Ch]
  int v25; // [rsp+120h] [rbp+20h]
  PSID v26; // [rsp+128h] [rbp+28h]
  int v27; // [rsp+130h] [rbp+30h]
  __int64 v28; // [rsp+134h] [rbp+34h]
  int v29; // [rsp+14Ch] [rbp+4Ch]
  int v30; // [rsp+150h] [rbp+50h]
  PSID v31; // [rsp+158h] [rbp+58h]
  int v32; // [rsp+160h] [rbp+60h]
  __int64 v33; // [rsp+164h] [rbp+64h]
  int v34; // [rsp+17Ch] [rbp+7Ch]
  int v35; // [rsp+180h] [rbp+80h]
  PSID v36; // [rsp+188h] [rbp+88h]
  int v37; // [rsp+190h] [rbp+90h]
  __int64 v38; // [rsp+194h] [rbp+94h]
  int v39; // [rsp+1ACh] [rbp+ACh]
  int v40; // [rsp+1B0h] [rbp+B0h]
  PSID v41; // [rsp+1B8h] [rbp+B8h]

  *(_WORD *)&v15.Value[4] = 256;
  hMem = 0;
  pSid = 0;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  *(_DWORD *)v15.Value = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &hMem)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &v10)
    && AllocateAndInitializeSid(&v15, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v12)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v11)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &v13) )
  {
    memset_0(&pListOfExplicitEntries, 0, 0x120u);
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)hMem;
    v21 = pSid;
    v5 = 3;
    v26 = v10;
    pListOfExplicitEntries.grfAccessPermissions = 2032127;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
    v17 = 2032127;
    v18 = 2;
    v19 = 0;
    v20 = 2;
    v22 = 2032127;
    v23 = 2;
    v24 = 0;
    v25 = 2;
    if ( !OldAcl )
    {
      v31 = v12;
      v36 = v11;
      v27 = 1179808;
      v32 = 1179808;
      v5 = 6;
      v41 = v13;
      v28 = 2;
      v29 = 0;
      v30 = 2;
      v33 = 2;
      v34 = 0;
      v35 = 2;
      v37 = 2032127;
      v38 = 2;
      v39 = 0;
      v40 = 2;
    }
    LastError = SetEntriesInAclW(v5, &pListOfExplicitEntries, OldAcl, NewAcl);
  }
  else
  {
    LastError = GetLastError();
  }
  v6 = LastError;
  if ( hMem )
    LocalFree(hMem);
  if ( pSid )
    LocalFree(pSid);
  if ( v10 )
    LocalFree(v10);
  if ( v11 )
    LocalFree(v11);
  if ( v12 )
    LocalFree(v12);
  if ( v13 )
    LocalFree(v13);
  return v6;
}

```

## disassembly

```asm
0x1800124c0  mov     [rsp-8+arg_10], rbx
0x1800124c5  push    rbp
0x1800124c6  push    rsi
0x1800124c7  push    rdi
0x1800124c8  lea     rbp, [rsp-0D0h]
0x1800124d0  sub     rsp, 1D0h
0x1800124d7  mov     rax, cs:__security_cookie
0x1800124de  xor     rax, rsp
0x1800124e1  mov     [rbp+0E0h+var_20], rax
0x1800124e8  xor     esi, esi
0x1800124ea  mov     word ptr [rbp+0E0h+var_148.Value+4], 100h
0x1800124f0  lea     rax, [rsp+1E0h+hMem]
0x1800124f5  mov     [rsp+1E0h+hMem], rsi
0x1800124fa  mov     [rsp+1E0h+pSid], rax; pSid
0x1800124ff  mov     rdi, rdx
0x180012502  mov     [rsp+1E0h+nSubAuthority7], esi; nSubAuthority7
0x180012506  mov     rbx, rcx
0x180012509  mov     [rsp+1E0h+nSubAuthority6], esi; nSubAuthority6
0x18001250d  lea     r8d, [rsi+12h]; nSubAuthority0
0x180012511  mov     [rsp+1E0h+nSubAuthority5], esi; nSubAuthority5
0x180012515  lea     rcx, [rbp+0E0h+pIdentifierAuthority]; pIdentifierAuthority
0x180012519  mov     [rsp+1E0h+nSubAuthority4], esi; nSubAuthority4
0x18001251d  xor     r9d, r9d; nSubAuthority1
0x180012520  mov     [rsp+1E0h+nSubAuthority3], esi; nSubAuthority3
0x180012524  mov     dl, 1; nSubAuthorityCount
0x180012526  mov     [rsp+1E0h+nSubAuthority2], esi; nSubAuthority2
0x18001252a  mov     [rsp+1E0h+var_178], rsi
0x18001252f  mov     [rsp+1E0h+var_170], rsi
0x180012534  mov     [rbp+0E0h+var_160], rsi
0x180012538  mov     [rsp+1E0h+var_168], rsi
0x18001253d  mov     [rbp+0E0h+var_158], rsi
0x180012541  mov     dword ptr [rbp+0E0h+var_148.Value], esi
0x180012544  mov     dword ptr [rbp+0E0h+pIdentifierAuthority.Value], esi
0x180012547  mov     word ptr [rbp+0E0h+pIdentifierAuthority.Value+4], 500h
0x18001254d  call    cs:__imp_AllocateAndInitializeSid
0x180012553  test    eax, eax
0x180012555  jnz     short loc_180012562
0x180012557  call    cs:__imp_GetLastError
0x18001255d  jmp     loc_18001275F
0x180012562  lea     rax, [rsp+1E0h+var_178]
0x180012567  xor     r9d, r9d; nSubAuthority1
0x18001256a  mov     [rsp+1E0h+pSid], rax; pSid
0x18001256f  lea     rcx, [rbp+0E0h+pIdentifierAuthority]; pIdentifierAuthority
0x180012573  mov     [rsp+1E0h+nSubAuthority7], esi; nSubAuthority7
0x180012577  mov     dl, 1; nSubAuthorityCount
0x180012579  mov     [rsp+1E0h+nSubAuthority6], esi; nSubAuthority6
0x18001257d  mov     [rsp+1E0h+nSubAuthority5], esi; nSubAuthority5
0x180012581  lea     r8d, [r9+13h]; nSubAuthority0
0x180012585  mov     [rsp+1E0h+nSubAuthority4], esi; nSubAuthority4
0x180012589  mov     [rsp+1E0h+nSubAuthority3], esi; nSubAuthority3
0x18001258d  mov     [rsp+1E0h+nSubAuthority2], esi; nSubAuthority2
0x180012591  call    cs:__imp_AllocateAndInitializeSid
0x180012597  test    eax, eax
0x180012599  jz      short loc_180012557
0x18001259b  lea     rax, [rsp+1E0h+var_170]
0x1800125a0  xor     r9d, r9d; nSubAuthority1
0x1800125a3  mov     [rsp+1E0h+pSid], rax; pSid
0x1800125a8  lea     rcx, [rbp+0E0h+pIdentifierAuthority]; pIdentifierAuthority
0x1800125ac  mov     [rsp+1E0h+nSubAuthority7], esi; nSubAuthority7
0x1800125b0  mov     dl, 1; nSubAuthorityCount
0x1800125b2  mov     [rsp+1E0h+nSubAuthority6], esi; nSubAuthority6
0x1800125b6  mov     [rsp+1E0h+nSubAuthority5], esi; nSubAuthority5
0x1800125ba  lea     r8d, [r9+4]; nSubAuthority0
0x1800125be  mov     [rsp+1E0h+nSubAuthority4], esi; nSubAuthority4
0x1800125c2  mov     [rsp+1E0h+nSubAuthority3], esi; nSubAuthority3
0x1800125c6  mov     [rsp+1E0h+nSubAuthority2], esi; nSubAuthority2
0x1800125ca  call    cs:__imp_AllocateAndInitializeSid
0x1800125d0  test    eax, eax
0x1800125d2  jz      short loc_180012557
0x1800125d4  lea     rax, [rbp+0E0h+var_160]
0x1800125d8  xor     r9d, r9d; nSubAuthority1
0x1800125db  mov     [rsp+1E0h+pSid], rax; pSid
0x1800125e0  lea     rcx, [rbp+0E0h+var_148]; pIdentifierAuthority
0x1800125e4  mov     [rsp+1E0h+nSubAuthority7], esi; nSubAuthority7
0x1800125e8  xor     r8d, r8d; nSubAuthority0
0x1800125eb  mov     [rsp+1E0h+nSubAuthority6], esi; nSubAuthority6
0x1800125ef  mov     dl, 1; nSubAuthorityCount
0x1800125f1  mov     [rsp+1E0h+nSubAuthority5], esi; nSubAuthority5
0x1800125f5  mov     [rsp+1E0h+nSubAuthority4], esi; nSubAuthority4
0x1800125f9  mov     [rsp+1E0h+nSubAuthority3], esi; nSubAuthority3
0x1800125fd  mov     [rsp+1E0h+nSubAuthority2], esi; nSubAuthority2
0x180012601  call    cs:__imp_AllocateAndInitializeSid
0x180012607  test    eax, eax
0x180012609  jz      loc_180012557
0x18001260f  lea     rax, [rsp+1E0h+var_168]
0x180012614  xor     r9d, r9d; nSubAuthority1
0x180012617  mov     [rsp+1E0h+pSid], rax; pSid
0x18001261c  lea     rcx, [rbp+0E0h+pIdentifierAuthority]; pIdentifierAuthority
0x180012620  mov     [rsp+1E0h+nSubAuthority7], esi; nSubAuthority7
0x180012624  mov     dl, 1; nSubAuthorityCount
0x180012626  mov     [rsp+1E0h+nSubAuthority6], esi; nSubAuthority6
0x18001262a  mov     [rsp+1E0h+nSubAuthority5], esi; nSubAuthority5
0x18001262e  lea     r8d, [r9+0Ch]; nSubAuthority0
0x180012632  mov     [rsp+1E0h+nSubAuthority4], esi; nSubAuthority4
0x180012636  mov     [rsp+1E0h+nSubAuthority3], esi; nSubAuthority3
0x18001263a  mov     [rsp+1E0h+nSubAuthority2], esi; nSubAuthority2
0x18001263e  call    cs:__imp_AllocateAndInitializeSid
0x180012644  test    eax, eax
0x180012646  jz      loc_180012557
0x18001264c  lea     rax, [rbp+0E0h+var_158]
0x180012650  xor     r9d, r9d; nSubAuthority1
0x180012653  mov     [rsp+1E0h+pSid], rax; pSid
0x180012658  lea     rcx, [rbp+0E0h+pIdentifierAuthority]; pIdentifierAuthority
0x18001265c  mov     [rsp+1E0h+nSubAuthority7], esi; nSubAuthority7
0x180012660  mov     dl, 1; nSubAuthorityCount
0x180012662  mov     [rsp+1E0h+nSubAuthority6], esi; nSubAuthority6
0x180012666  mov     [rsp+1E0h+nSubAuthority5], esi; nSubAuthority5
0x18001266a  lea     r8d, [r9+0Bh]; nSubAuthority0
0x18001266e  mov     [rsp+1E0h+nSubAuthority4], esi; nSubAuthority4
0x180012672  mov     [rsp+1E0h+nSubAuthority3], esi; nSubAuthority3
0x180012676  mov     [rsp+1E0h+nSubAuthority2], esi; nSubAuthority2
0x18001267a  call    cs:__imp_AllocateAndInitializeSid
0x180012680  test    eax, eax
0x180012682  jz      loc_180012557
0x180012688  xor     edx, edx; Val
0x18001268a  lea     rcx, [rbp+0E0h+pListOfExplicitEntries]; void *
0x18001268e  mov     r8d, 120h; Size
0x180012694  call    memset_0
0x180012699  mov     rax, [rsp+1E0h+hMem]
0x18001269e  mov     edx, 2
0x1800126a3  mov     [rbp+0E0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800126a7  mov     r8d, 1F01FFh
0x1800126ad  mov     rax, [rsp+1E0h+var_178]
0x1800126b2  mov     [rbp+0E0h+var_E8], rax
0x1800126b6  mov     rax, [rsp+1E0h+var_170]
0x1800126bb  lea     ecx, [rdx+1]
0x1800126be  mov     [rbp+0E0h+var_B8], rax
0x1800126c2  mov     [rbp+0E0h+pListOfExplicitEntries.grfAccessPermissions], r8d
0x1800126c6  mov     qword ptr [rbp+0E0h+pListOfExplicitEntries.grfAccessMode], rdx
0x1800126ca  mov     [rbp+0E0h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x1800126cd  mov     [rbp+0E0h+pListOfExplicitEntries.Trustee.TrusteeType], edx
0x1800126d0  mov     [rbp+0E0h+var_110], r8d
0x1800126d4  mov     [rbp+0E0h+var_10C], rdx
0x1800126d8  mov     [rbp+0E0h+var_F4], esi
0x1800126db  mov     [rbp+0E0h+var_F0], edx
0x1800126de  mov     [rbp+0E0h+var_E0], r8d
0x1800126e2  mov     [rbp+0E0h+var_DC], rdx
0x1800126e6  mov     [rbp+0E0h+var_C4], esi
0x1800126e9  mov     [rbp+0E0h+var_C0], edx
0x1800126ec  test    rbx, rbx
0x1800126ef  jnz     short loc_18001274F
0x1800126f1  mov     rax, [rbp+0E0h+var_160]
0x1800126f5  mov     ecx, 1200A0h
0x1800126fa  mov     [rbp+0E0h+var_88], rax
0x1800126fe  mov     rax, [rsp+1E0h+var_168]
0x180012703  mov     [rbp+0E0h+var_58], rax
0x18001270a  mov     rax, [rbp+0E0h+var_158]
0x18001270e  mov     [rbp+0E0h+var_B0], ecx
0x180012711  mov     [rbp+0E0h+var_80], ecx
0x180012714  lea     ecx, [rdx+4]; cCountOfExplicitEntries
0x180012717  mov     [rbp+0E0h+var_28], rax
0x18001271e  mov     [rbp+0E0h+var_AC], rdx
0x180012722  mov     [rbp+0E0h+var_94], esi
0x180012725  mov     [rbp+0E0h+var_90], edx
0x180012728  mov     [rbp+0E0h+var_7C], rdx
0x18001272c  mov     [rbp+0E0h+var_64], esi
0x18001272f  mov     [rbp+0E0h+var_60], edx
0x180012735  mov     [rbp+0E0h+var_50], r8d
0x18001273c  mov     [rbp+0E0h+var_4C], rdx
0x180012743  mov     [rbp+0E0h+var_34], esi
0x180012749  mov     [rbp+0E0h+var_30], edx
0x18001274f  mov     r9, rdi; NewAcl
0x180012752  lea     rdx, [rbp+0E0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180012756  mov     r8, rbx; OldAcl
0x180012759  call    cs:__imp_SetEntriesInAclW
0x18001275f  mov     ebx, eax
0x180012761  mov     rcx, [rsp+1E0h+hMem]; hMem
0x180012766  test    rcx, rcx
0x180012769  jz      short loc_180012771
0x18001276b  call    cs:__imp_LocalFree
0x180012771  mov     rcx, [rsp+1E0h+var_178]; hMem
0x180012776  test    rcx, rcx
0x180012779  jz      short loc_180012781
0x18001277b  call    cs:__imp_LocalFree
0x180012781  mov     rcx, [rsp+1E0h+var_170]; hMem
0x180012786  test    rcx, rcx
0x180012789  jz      short loc_180012791
0x18001278b  call    cs:__imp_LocalFree
0x180012791  mov     rcx, [rsp+1E0h+var_168]; hMem
0x180012796  test    rcx, rcx
0x180012799  jz      short loc_1800127A1
0x18001279b  call    cs:__imp_LocalFree
0x1800127a1  mov     rcx, [rbp+0E0h+var_160]; hMem
0x1800127a5  test    rcx, rcx
0x1800127a8  jz      short loc_1800127B0
0x1800127aa  call    cs:__imp_LocalFree
0x1800127b0  mov     rcx, [rbp+0E0h+var_158]; hMem
0x1800127b4  test    rcx, rcx
0x1800127b7  jz      short loc_1800127BF
0x1800127b9  call    cs:__imp_LocalFree
0x1800127bf  mov     eax, ebx
0x1800127c1  mov     rcx, [rbp+0E0h+var_20]
0x1800127c8  xor     rcx, rsp; StackCookie
0x1800127cb  call    __security_check_cookie
0x1800127d0  mov     rbx, [rsp+1E0h+arg_10]
0x1800127d8  add     rsp, 1D0h
0x1800127df  pop     rdi
0x1800127e0  pop     rsi
0x1800127e1  pop     rbp
0x1800127e2  retn
```
