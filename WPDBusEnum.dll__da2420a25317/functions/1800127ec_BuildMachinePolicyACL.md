# BuildMachinePolicyACL

- ea: `0x1800127ec`
- end: `0x180012b81`
- name: `BuildMachinePolicyACL`
- size: `917`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004f10`
- `0x180005f60`

## callees

- `0x1800097d0`
- `0x18000a192`
- `0x1800127ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a22`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001287c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800128b9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800128f6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012932`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001296a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800129a2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001287c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800128b9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800128f6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012932`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001296a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800129a2`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180012b63`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180012b63`

## pseudocode

```c
__int64 __fastcall BuildMachinePolicyACL(unsigned int a1, HLOCAL *a2)
{
  __int64 v2; // rbx
  DWORD LastError; // ebx
  unsigned int v6; // ecx
  ULONG v7; // ecx
  unsigned int v8; // eax
  unsigned int v9; // eax
  PSID hMem; // [rsp+60h] [rbp-A0h] BYREF
  PSID v11; // [rsp+68h] [rbp-98h] BYREF
  PSID pSid; // [rsp+70h] [rbp-90h] BYREF
  PSID v13; // [rsp+78h] [rbp-88h] BYREF
  PSID v14; // [rsp+80h] [rbp-80h] BYREF
  PSID v15; // [rsp+88h] [rbp-78h] BYREF
  PACL NewAcl; // [rsp+90h] [rbp-70h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v18; // [rsp+A0h] [rbp-60h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+B0h] [rbp-50h] BYREF
  int v20; // [rsp+E0h] [rbp-20h]
  __int64 v21; // [rsp+E4h] [rbp-1Ch]
  int v22; // [rsp+FCh] [rbp-4h]
  int v23; // [rsp+100h] [rbp+0h]
  PSID v24; // [rsp+108h] [rbp+8h]
  unsigned int v25; // [rsp+110h] [rbp+10h]
  int v26; // [rsp+114h] [rbp+14h]
  int v27; // [rsp+118h] [rbp+18h]
  int v28; // [rsp+12Ch] [rbp+2Ch]
  int v29; // [rsp+130h] [rbp+30h]
  PSID v30; // [rsp+138h] [rbp+38h]
  int v31; // [rsp+140h] [rbp+40h]
  __int64 v32; // [rsp+144h] [rbp+44h]
  int v33; // [rsp+15Ch] [rbp+5Ch]
  int v34; // [rsp+160h] [rbp+60h]
  PSID v35; // [rsp+168h] [rbp+68h]
  int v36; // [rsp+170h] [rbp+70h]
  __int64 v37; // [rsp+174h] [rbp+74h]
  int v38; // [rsp+18Ch] [rbp+8Ch]
  int v39; // [rsp+190h] [rbp+90h]
  PSID v40; // [rsp+198h] [rbp+98h]
  unsigned int v41; // [rsp+1A0h] [rbp+A0h]
  __int64 v42; // [rsp+1A4h] [rbp+A4h]
  int v43; // [rsp+1BCh] [rbp+BCh]
  int v44; // [rsp+1C0h] [rbp+C0h]
  PSID v45; // [rsp+1C8h] [rbp+C8h]

  v2 = a1;
  *a2 = 0;
  NewAcl = 0;
  hMem = 0;
  v11 = 0;
  pSid = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v18.Value = 0;
  *(_WORD *)&v18.Value[4] = 256;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &hMem)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &v11)
    || !AllocateAndInitializeSid(&v18, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v13)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v14)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &v15) )
  {
    LastError = GetLastError();
    if ( !LastError )
      goto LABEL_10;
    goto LABEL_8;
  }
  memset_0(&pListOfExplicitEntries, 0, 0x120u);
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)hMem;
  v24 = v11;
  pListOfExplicitEntries.grfAccessPermissions = 2032127;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  v20 = 2032127;
  v21 = 2;
  v22 = 0;
  v23 = 2;
  v27 = 0;
  v28 = 0;
  v29 = 2;
  v30 = pSid;
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == 7 )
    {
      v7 = 3;
      v8 = HIDWORD(StorageDeviceAccess[v2]) & 0xFFEDFFFF;
      v26 = 3;
      v25 = v8;
      goto LABEL_29;
    }
    v7 = 4;
    v25 = StorageDeviceAccess[v2];
    v9 = HIDWORD(StorageDeviceAccess[v2]) & 0xFFEDFFFF;
    v32 = 3;
    v31 = v9;
    v35 = pSid;
  }
  else
  {
    v6 = StorageDeviceAccess[v2];
    v35 = v13;
    v40 = v14;
    v25 = v6;
    v41 = v6;
    v7 = 6;
    v45 = v15;
    v31 = 1179808;
    v32 = 2;
    v36 = 1179808;
    v37 = 2;
    v38 = 0;
    v39 = 2;
    v42 = 2;
    v43 = 0;
    v44 = 2;
  }
  v34 = 2;
  v33 = 0;
  v26 = 2;
LABEL_29:
  LastError = SetEntriesInAclW(v7, &pListOfExplicitEntries, 0, &NewAcl);
  if ( !LastError )
  {
    LastError = 0;
    *a2 = NewAcl;
    goto LABEL_10;
  }
LABEL_8:
  if ( *a2 )
    LocalFree(*a2);
LABEL_10:
  if ( hMem )
    LocalFree(hMem);
  if ( v11 )
    LocalFree(v11);
  if ( pSid )
    LocalFree(pSid);
  if ( v13 )
    LocalFree(v13);
  if ( v14 )
    LocalFree(v14);
  if ( v15 )
    LocalFree(v15);
  return LastError;
}

```

## disassembly

```asm
0x1800127ec  push    rbp
0x1800127ee  push    rbx
0x1800127ef  push    rsi
0x1800127f0  push    rdi
0x1800127f1  lea     rbp, [rsp-0E8h]
0x1800127f9  sub     rsp, 1E8h
0x180012800  mov     rax, cs:__security_cookie
0x180012807  xor     rax, rsp
0x18001280a  mov     [rbp+100h+var_30], rax
0x180012811  xor     esi, esi
0x180012813  mov     ebx, ecx
0x180012815  lea     rax, [rsp+200h+var_190]
0x18001281a  mov     [rdx], rsi
0x18001281d  mov     [rsp+200h+pSid], rax; pSid
0x180012822  lea     rcx, [rbp+100h+pIdentifierAuthority]; pIdentifierAuthority
0x180012826  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x18001282a  mov     rdi, rdx
0x18001282d  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180012831  lea     r8d, [rsi+4]; nSubAuthority0
0x180012835  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x180012839  xor     r9d, r9d; nSubAuthority1
0x18001283c  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x180012840  mov     dl, 1; nSubAuthorityCount
0x180012842  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x180012846  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x18001284a  mov     [rbp+100h+NewAcl], rsi
0x18001284e  mov     [rsp+200h+hMem], rsi
0x180012853  mov     [rsp+200h+var_198], rsi
0x180012858  mov     [rsp+200h+var_190], rsi
0x18001285d  mov     [rsp+200h+var_188], rsi
0x180012862  mov     [rbp+100h+var_180], rsi
0x180012866  mov     [rbp+100h+var_178], rsi
0x18001286a  mov     dword ptr [rbp+100h+pIdentifierAuthority.Value], esi
0x18001286d  mov     word ptr [rbp+100h+pIdentifierAuthority.Value+4], 500h
0x180012873  mov     dword ptr [rbp+100h+var_160.Value], esi
0x180012876  mov     word ptr [rbp+100h+var_160.Value+4], 100h
0x18001287c  call    cs:__imp_AllocateAndInitializeSid
0x180012882  test    eax, eax
0x180012884  jz      loc_1800129B0
0x18001288a  lea     rax, [rsp+200h+hMem]
0x18001288f  xor     r9d, r9d; nSubAuthority1
0x180012892  mov     [rsp+200h+pSid], rax; pSid
0x180012897  lea     r8d, [rsi+12h]; nSubAuthority0
0x18001289b  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x18001289f  lea     rcx, [rbp+100h+pIdentifierAuthority]; pIdentifierAuthority
0x1800128a3  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x1800128a7  mov     dl, 1; nSubAuthorityCount
0x1800128a9  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x1800128ad  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x1800128b1  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x1800128b5  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x1800128b9  call    cs:__imp_AllocateAndInitializeSid
0x1800128bf  test    eax, eax
0x1800128c1  jz      loc_1800129B0
0x1800128c7  lea     rax, [rsp+200h+var_198]
0x1800128cc  xor     r9d, r9d; nSubAuthority1
0x1800128cf  mov     [rsp+200h+pSid], rax; pSid
0x1800128d4  lea     r8d, [rsi+13h]; nSubAuthority0
0x1800128d8  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x1800128dc  lea     rcx, [rbp+100h+pIdentifierAuthority]; pIdentifierAuthority
0x1800128e0  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x1800128e4  mov     dl, 1; nSubAuthorityCount
0x1800128e6  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x1800128ea  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x1800128ee  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x1800128f2  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x1800128f6  call    cs:__imp_AllocateAndInitializeSid
0x1800128fc  test    eax, eax
0x1800128fe  jz      loc_1800129B0
0x180012904  lea     rax, [rsp+200h+var_188]
0x180012909  xor     r9d, r9d; nSubAuthority1
0x18001290c  mov     [rsp+200h+pSid], rax; pSid
0x180012911  lea     rcx, [rbp+100h+var_160]; pIdentifierAuthority
0x180012915  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x180012919  xor     r8d, r8d; nSubAuthority0
0x18001291c  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180012920  mov     dl, 1; nSubAuthorityCount
0x180012922  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x180012926  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x18001292a  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x18001292e  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x180012932  call    cs:__imp_AllocateAndInitializeSid
0x180012938  test    eax, eax
0x18001293a  jz      short loc_1800129B0
0x18001293c  lea     rax, [rbp+100h+var_180]
0x180012940  xor     r9d, r9d; nSubAuthority1
0x180012943  mov     [rsp+200h+pSid], rax; pSid
0x180012948  lea     r8d, [rsi+0Ch]; nSubAuthority0
0x18001294c  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x180012950  lea     rcx, [rbp+100h+pIdentifierAuthority]; pIdentifierAuthority
0x180012954  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180012958  mov     dl, 1; nSubAuthorityCount
0x18001295a  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x18001295e  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x180012962  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x180012966  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x18001296a  call    cs:__imp_AllocateAndInitializeSid
0x180012970  test    eax, eax
0x180012972  jz      short loc_1800129B0
0x180012974  lea     rax, [rbp+100h+var_178]
0x180012978  xor     r9d, r9d; nSubAuthority1
0x18001297b  mov     [rsp+200h+pSid], rax; pSid
0x180012980  lea     r8d, [rsi+0Bh]; nSubAuthority0
0x180012984  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x180012988  lea     rcx, [rbp+100h+pIdentifierAuthority]; pIdentifierAuthority
0x18001298c  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180012990  mov     dl, 1; nSubAuthorityCount
0x180012992  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x180012996  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x18001299a  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x18001299e  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x1800129a2  call    cs:__imp_AllocateAndInitializeSid
0x1800129a8  test    eax, eax
0x1800129aa  jnz     loc_180012A45
0x1800129b0  call    cs:__imp_GetLastError
0x1800129b6  mov     ebx, eax
0x1800129b8  test    eax, eax
0x1800129ba  jz      short loc_1800129CA
0x1800129bc  mov     rcx, [rdi]; hMem
0x1800129bf  test    rcx, rcx
0x1800129c2  jz      short loc_1800129CA
0x1800129c4  call    cs:__imp_LocalFree
0x1800129ca  mov     rcx, [rsp+200h+hMem]; hMem
0x1800129cf  test    rcx, rcx
0x1800129d2  jz      short loc_1800129DA
0x1800129d4  call    cs:__imp_LocalFree
0x1800129da  mov     rcx, [rsp+200h+var_198]; hMem
0x1800129df  test    rcx, rcx
0x1800129e2  jz      short loc_1800129EA
0x1800129e4  call    cs:__imp_LocalFree
0x1800129ea  mov     rcx, [rsp+200h+var_190]; hMem
0x1800129ef  test    rcx, rcx
0x1800129f2  jz      short loc_1800129FA
0x1800129f4  call    cs:__imp_LocalFree
0x1800129fa  mov     rcx, [rsp+200h+var_188]; hMem
0x1800129ff  test    rcx, rcx
0x180012a02  jz      short loc_180012A0A
0x180012a04  call    cs:__imp_LocalFree
0x180012a0a  mov     rcx, [rbp+100h+var_180]; hMem
0x180012a0e  test    rcx, rcx
0x180012a11  jz      short loc_180012A19
0x180012a13  call    cs:__imp_LocalFree
0x180012a19  mov     rcx, [rbp+100h+var_178]; hMem
0x180012a1d  test    rcx, rcx
0x180012a20  jz      short loc_180012A28
0x180012a22  call    cs:__imp_LocalFree
0x180012a28  mov     eax, ebx
0x180012a2a  mov     rcx, [rbp+100h+var_30]
0x180012a31  xor     rcx, rsp; StackCookie
0x180012a34  call    __security_check_cookie
0x180012a39  add     rsp, 1E8h
0x180012a40  pop     rdi
0x180012a41  pop     rsi
0x180012a42  pop     rbx
0x180012a43  pop     rbp
0x180012a44  retn
0x180012a45  xor     edx, edx; Val
0x180012a47  lea     rcx, [rbp+100h+pListOfExplicitEntries]; void *
0x180012a4b  mov     r8d, 120h; Size
0x180012a51  call    memset_0
0x180012a56  mov     rax, [rsp+200h+hMem]
0x180012a5b  mov     r10d, 2
0x180012a61  mov     r9, [rsp+200h+var_190]
0x180012a66  mov     ecx, 1F01FFh
0x180012a6b  mov     [rbp+100h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180012a6f  lea     rdx, StorageDeviceAccess
0x180012a76  mov     rax, [rsp+200h+var_198]
0x180012a7b  mov     [rbp+100h+var_F8], rax
0x180012a7f  mov     [rbp+100h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180012a82  mov     qword ptr [rbp+100h+pListOfExplicitEntries.grfAccessMode], r10
0x180012a86  mov     [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x180012a89  mov     [rbp+100h+pListOfExplicitEntries.Trustee.TrusteeType], r10d
0x180012a8d  mov     [rbp+100h+var_120], ecx
0x180012a90  mov     [rbp+100h+var_11C], r10
0x180012a94  mov     [rbp+100h+var_104], esi
0x180012a97  mov     [rbp+100h+var_100], r10d
0x180012a9b  mov     [rbp+100h+var_E8], esi
0x180012a9e  mov     [rbp+100h+var_D4], esi
0x180012aa1  mov     [rbp+100h+var_D0], r10d
0x180012aa5  mov     [rbp+100h+var_C8], r9
0x180012aa9  test    ebx, ebx
0x180012aab  jnz     short loc_180012B11
0x180012aad  mov     ecx, [rdx+rbx*8]
0x180012ab0  mov     edx, 1200A0h
0x180012ab5  mov     rax, [rsp+200h+var_188]
0x180012aba  mov     [rbp+100h+var_98], rax
0x180012abe  mov     rax, [rbp+100h+var_180]
0x180012ac2  mov     [rbp+100h+var_68], rax
0x180012ac9  mov     rax, [rbp+100h+var_178]
0x180012acd  mov     [rbp+100h+var_F0], ecx
0x180012ad0  mov     [rbp+100h+var_60], ecx
0x180012ad6  lea     ecx, [rbx+6]
0x180012ad9  mov     [rbp+100h+var_38], rax
0x180012ae0  mov     [rbp+100h+var_C0], edx
0x180012ae3  mov     [rbp+100h+var_BC], r10
0x180012ae7  mov     [rbp+100h+var_90], edx
0x180012aea  mov     [rbp+100h+var_8C], r10
0x180012aee  mov     [rbp+100h+var_74], esi
0x180012af4  mov     [rbp+100h+var_70], r10d
0x180012afb  mov     [rbp+100h+var_5C], r10
0x180012b02  mov     [rbp+100h+var_44], esi
0x180012b08  mov     [rbp+100h+var_40], r10d
0x180012b0f  jmp     short loc_180012B4D
0x180012b11  cmp     ebx, 7
0x180012b14  jnz     short loc_180012B2A
0x180012b16  mov     eax, [rdx+rbx*8+4]
0x180012b1a  lea     ecx, [rbx-4]
0x180012b1d  and     eax, 0FFEDFFFFh
0x180012b22  mov     [rbp+100h+var_EC], ecx
0x180012b25  mov     [rbp+100h+var_F0], eax
0x180012b28  jmp     short loc_180012B58
0x180012b2a  mov     eax, [rdx+rbx*8]
0x180012b2d  mov     ecx, 4; cCountOfExplicitEntries
0x180012b32  mov     [rbp+100h+var_F0], eax
0x180012b35  mov     eax, [rdx+rbx*8+4]
0x180012b39  and     eax, 0FFEDFFFFh
0x180012b3e  mov     [rbp+100h+var_BC], 3
0x180012b46  mov     [rbp+100h+var_C0], eax
0x180012b49  mov     [rbp+100h+var_98], r9
0x180012b4d  mov     [rbp+100h+var_A0], r10d
0x180012b51  mov     [rbp+100h+var_A4], esi
0x180012b54  mov     [rbp+100h+var_EC], r10d
0x180012b58  lea     r9, [rbp+100h+NewAcl]; NewAcl
0x180012b5c  xor     r8d, r8d; OldAcl
0x180012b5f  lea     rdx, [rbp+100h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180012b63  call    cs:__imp_SetEntriesInAclW
0x180012b69  mov     ebx, eax
0x180012b6b  test    eax, eax
0x180012b6d  jnz     loc_1800129BC
0x180012b73  mov     rax, [rbp+100h+NewAcl]
0x180012b77  mov     ebx, esi
0x180012b79  mov     [rdi], rax
0x180012b7c  jmp     loc_1800129CA
```
