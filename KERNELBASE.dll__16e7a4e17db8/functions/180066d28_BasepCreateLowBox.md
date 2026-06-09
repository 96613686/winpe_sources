# BasepCreateLowBox

- ea: `0x180066d28`
- end: `0x1800673d5`
- name: `BasepCreateLowBox`
- size: `1709`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180066d00`
- `0x18007f610`

## callees

- `0x180033800`
- `0x180066d28`
- `0x1800673dc`
- `0x180067550`
- `0x180067cb0`
- `0x18006ee28`
- `0x1800f5368`
- `0x18012d119`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180066e58`
- `ntdll!NtQueryInformationToken` at `0x180067179`
- `ntdll!NtQueryInformationToken` at `0x180066e58`
- `ntdll!NtQueryInformationToken` at `0x180067179`
- `ntdll!NtClose` at `0x180066fc6`
- `ntdll!NtClose` at `0x180066fd5`
- `ntdll!NtClose` at `0x180066fe4`
- `ntdll!NtClose` at `0x180066ff3`
- `ntdll!NtClose` at `0x180067002`
- `ntdll!NtClose` at `0x180067011`
- `ntdll!NtClose` at `0x18006702d`
- `ntdll!NtClose` at `0x180067135`
- `ntdll!NtClose` at `0x180066fc6`
- `ntdll!NtClose` at `0x180066fd5`
- `ntdll!NtClose` at `0x180066fe4`
- `ntdll!NtClose` at `0x180066ff3`
- `ntdll!NtClose` at `0x180067002`
- `ntdll!NtClose` at `0x180067011`
- `ntdll!NtClose` at `0x18006702d`
- `ntdll!NtClose` at `0x180067135`
- `ntdll!RtlFreeSid` at `0x18006703f`
- `ntdll!RtlFreeSid` at `0x18006704e`
- `ntdll!RtlFreeSid` at `0x18006703f`
- `ntdll!RtlFreeSid` at `0x18006704e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180067295`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180067295`
- `ntdll!RtlGetAppContainerSidType` at `0x180066f31`
- `ntdll!RtlGetAppContainerSidType` at `0x180066f31`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x180067194`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x180067194`
- `ntdll!RtlFreeHeap` at `0x18006706b`
- `ntdll!RtlFreeHeap` at `0x18006706b`
- `ntdll!NtOpenProcessToken` at `0x1800673b4`
- `ntdll!NtOpenProcessToken` at `0x1800673b4`
- `ntdll!NtOpenThreadToken` at `0x180067373`
- `ntdll!NtOpenThreadToken` at `0x180067373`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180067324`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180067324`
- `ntdll!NtCreateLowBoxToken` at `0x180066f9b`
- `ntdll!NtCreateLowBoxToken` at `0x180066f9b`
- `ntdll!RtlAllocateHeap` at `0x1800671c4`
- `ntdll!RtlAllocateHeap` at `0x1800671c4`

## pseudocode

```c
NTSTATUS __fastcall BasepCreateLowBox(HANDLE TokenHandle, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r15
  HANDLE v5; // rdi
  __int64 v6; // rsi
  int v7; // r14d
  int TokenFromLowboxToken; // ebx
  char v9; // si
  int v10; // r14d
  PSID v11; // rcx
  void *v12; // rdi
  NTSTATUS result; // eax
  void **v14; // r8
  void **v15; // r8
  _QWORD *Heap; // rax
  PSID v17; // rbx
  ULONG SubAuthority7; // r12d
  ULONG SubAuthority6; // r15d
  ULONG SubAuthority5; // r14d
  ULONG v21; // esi
  ULONG v22; // edi
  ULONG *SidSubAuthority; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  int SubAuthority3; // [rsp+28h] [rbp-D8h]
  ULONG SubAuthority4[2]; // [rsp+30h] [rbp-D0h]
  int v27; // [rsp+60h] [rbp-A0h]
  _QWORD *P; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  ULONG v30; // [rsp+78h] [rbp-88h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+7Ch] [rbp-84h] BYREF
  int TokenInformation; // [rsp+80h] [rbp-80h] BYREF
  PSID Sid; // [rsp+88h] [rbp-78h] BYREF
  int v34; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+94h] [rbp-6Ch] BYREF
  HANDLE TokenHandlea; // [rsp+98h] [rbp-68h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-60h] BYREF
  __int128 Handle; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v40; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v41; // [rsp+D8h] [rbp-28h] BYREF
  PSID v42; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE v43; // [rsp+E8h] [rbp-18h]
  __int64 v44; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD *v46; // [rsp+100h] [rbp+0h]
  _BYTE v47[48]; // [rsp+108h] [rbp+8h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+138h] [rbp+38h] BYREF
  __int128 v49; // [rsp+140h] [rbp+40h] BYREF
  __int128 v50; // [rsp+150h] [rbp+50h]
  __int128 v51; // [rsp+160h] [rbp+60h]
  HANDLE v52; // [rsp+170h] [rbp+70h]
  WCHAR packageFamilyName[72]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v54[10]; // [rsp+210h] [rbp+110h] BYREF

  v46 = a3;
  v43 = TokenHandle;
  v3 = a3;
  TokenHandlea = 0;
  v39 = 0u;
  v5 = TokenHandle;
  TokenInformation = 0;
  Handle = 0u;
  v30 = 0;
  memset(v47, 0, 44);
  v40 = 0u;
  v41 = 0;
  v37 = 0;
  v49 = 0;
  v52 = 0;
  v50 = 0;
  v51 = 0;
  memset_0(v54, 0, 0x4Cu);
  Sid = 0;
  packageFamilyNameLength = 65;
  v34 = 1179650;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  v42 = 0;
  v35 = 0;
  if ( !*(_QWORD *)a2 )
    return -1073741811;
  v6 = *(_QWORD *)(a2 + 8);
  v7 = *(_DWORD *)(a2 + 16);
  v29 = v6;
  v27 = v7;
  if ( !ValuesQueried )
  {
    RtlQueryRegistryValuesEx(2, L"Session Manager\\NamespaceSeparation", &BnoRegistryConfigurationTable);
    if ( InteractiveUserNameSpaceSeparation )
    {
      AppcontainerUserNameSpaceSeparation = 1;
      InteractiveUserNameSpaceSeparation = 1;
    }
    ValuesQueried = 1;
  }
  if ( !v5 )
  {
    if ( NtCurrentTeb()->IsImpersonating )
      result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xF01FFu, 0, &TokenHandlea);
    else
      result = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xF01FFu, &TokenHandlea);
    if ( result < 0 )
      return result;
    v5 = TokenHandlea;
    v43 = TokenHandlea;
  }
  P = 0;
  if ( *(_DWORD *)(a2 + 16) && !*(_QWORD *)(a2 + 8) )
  {
    TokenFromLowboxToken = -1073741811;
    goto LABEL_49;
  }
  TokenFromLowboxToken = NtQueryInformationToken(v5, TokenIsAppContainer, &TokenInformation, 4u, &v30);
  if ( TokenFromLowboxToken < 0 )
  {
LABEL_49:
    v12 = 0;
    goto LABEL_16;
  }
  v44 = 0;
  v45 = 0;
  v9 = 0;
  AppModelPolicy_GetPolicy_Internal((_DWORD)v5, 33, (unsigned int)&v34, (unsigned int)&v45, (__int64)&v44);
  v10 = 6;
  if ( TokenInformation )
  {
    v30 = 76;
    result = NtQueryInformationToken(v5, TokenAppContainerSid, v54, 0x4Cu, &v30);
    TokenFromLowboxToken = result;
    if ( result < 0 )
      return result;
    if ( (unsigned __int8)RtlIsParentOfChildAppContainer(v54[0], *(_QWORD *)a2) )
    {
      v9 = 1;
    }
    else
    {
      TokenFromLowboxToken = BasepCreateTokenFromLowboxToken(v5);
      if ( TokenFromLowboxToken < 0 )
        goto LABEL_48;
    }
LABEL_58:
    if ( TokenInformation && !v9 )
    {
LABEL_13:
      *v3 = v37;
      goto LABEL_14;
    }
LABEL_8:
    TokenFromLowboxToken = BasepCreateLowBoxObjectDirectories(
                             *(PSID *)a2,
                             v5,
                             (HANDLE *)&Handle,
                             (HANDLE *)&Handle + 1,
                             (HANDLE *)&v39,
                             (__int64)&v39 + 8,
                             &v40,
                             (HANDLE *)&v40 + 1,
                             &v41);
    if ( TokenFromLowboxToken < 0 )
      goto LABEL_14;
    v11 = *(PSID *)a2;
    v49 = Handle;
    v50 = v39;
    v51 = v40;
    TokenFromLowboxToken = RtlGetAppContainerSidType(v11, &v35);
    if ( TokenFromLowboxToken < 0 )
      goto LABEL_14;
    if ( v35 == 1 )
    {
      v10 = 7;
      v52 = v41;
    }
    *(_DWORD *)v47 = 48;
    *(_QWORD *)SubAuthority4 = *(_QWORD *)(a2 + 8);
    SubAuthority3 = *(_DWORD *)(a2 + 16);
    ReturnLength = *(PULONG *)a2;
    memset(&v47[8], 0, 20);
    *(_OWORD *)&v47[32] = 0;
    TokenFromLowboxToken = NtCreateLowBoxToken(
                             &v37,
                             v5,
                             983551,
                             v47,
                             ReturnLength,
                             SubAuthority3,
                             *(_QWORD *)SubAuthority4,
                             v10,
                             &v49);
    if ( TokenFromLowboxToken < 0 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( v34 != 2162689 )
    goto LABEL_8;
  if ( GetPackageFamilyNameFromToken(v5, &packageFamilyNameLength, packageFamilyName) > 0 )
    TokenFromLowboxToken = (unsigned __int16)GetPackageFamilyNameFromToken(
                                               v5,
                                               &packageFamilyNameLength,
                                               packageFamilyName)
                         | 0xC0070000;
  else
    TokenFromLowboxToken = GetPackageFamilyNameFromToken(v5, &packageFamilyNameLength, packageFamilyName);
  if ( TokenFromLowboxToken < 0
    || ((int)ARI::Internal::PackageSidFromFamilyName(packageFamilyName, (const unsigned __int16 *)&Sid, v14) > 0
      ? (TokenFromLowboxToken = (unsigned __int16)ARI::Internal::PackageSidFromFamilyName(
                                                    packageFamilyName,
                                                    (const unsigned __int16 *)&Sid,
                                                    v15)
                              | 0xC0070000)
      : (TokenFromLowboxToken = ARI::Internal::PackageSidFromFamilyName(
                                  packageFamilyName,
                                  (const unsigned __int16 *)&Sid,
                                  v15)),
        TokenFromLowboxToken < 0) )
  {
LABEL_48:
    v7 = v27;
    v6 = v29;
    goto LABEL_49;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * (unsigned int)(*(_DWORD *)(a2 + 16) + 1));
  P = Heap;
  v12 = Heap;
  if ( !Heap )
  {
    TokenFromLowboxToken = -1073741801;
    goto LABEL_15;
  }
  if ( *(_DWORD *)(a2 + 16) )
    memcpy_0(Heap, *(const void **)(a2 + 8), 16LL * *(unsigned int *)(a2 + 16));
  v17 = Sid;
  SubAuthority7 = *GetSidSubAuthority(Sid, 7u);
  SubAuthority6 = *GetSidSubAuthority(v17, 6u);
  SubAuthority5 = *GetSidSubAuthority(v17, 5u);
  v21 = *GetSidSubAuthority(v17, 4u);
  v22 = *GetSidSubAuthority(v17, 3u);
  LODWORD(v17) = *GetSidSubAuthority(v17, 2u);
  SidSubAuthority = GetSidSubAuthority(Sid, 1u);
  TokenFromLowboxToken = RtlAllocateAndInitializeSid(
                           &IdentifierAuthority,
                           8u,
                           3u,
                           *SidSubAuthority,
                           (ULONG)v17,
                           v22,
                           v21,
                           SubAuthority5,
                           SubAuthority6,
                           SubAuthority7,
                           &v42);
  if ( TokenFromLowboxToken >= 0 )
  {
    v10 = 6;
    v9 = 0;
    v5 = v43;
    v3 = v46;
    P[2 * *(unsigned int *)(a2 + 16)] = v42;
    LODWORD(P[2 * (unsigned int)(*(_DWORD *)(a2 + 16))++ + 1]) = 4;
    *(_QWORD *)(a2 + 8) = P;
    goto LABEL_58;
  }
LABEL_14:
  v12 = P;
LABEL_15:
  v6 = v29;
  v7 = v27;
LABEL_16:
  if ( (_QWORD)Handle )
    NtClose((HANDLE)Handle);
  if ( *((_QWORD *)&Handle + 1) )
    NtClose(*((HANDLE *)&Handle + 1));
  if ( (_QWORD)v39 )
    NtClose((HANDLE)v39);
  if ( *((_QWORD *)&v39 + 1) )
    NtClose(*((HANDLE *)&v39 + 1));
  if ( (_QWORD)v40 )
    NtClose((HANDLE)v40);
  if ( *((_QWORD *)&v40 + 1) )
    NtClose(*((HANDLE *)&v40 + 1));
  if ( v41 )
    NtClose(v41);
  if ( TokenHandlea )
    NtClose(TokenHandlea);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v42 )
    RtlFreeSid(v42);
  if ( v12 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  *(_QWORD *)(a2 + 8) = v6;
  result = TokenFromLowboxToken;
  *(_DWORD *)(a2 + 16) = v7;
  return result;
}

```

## disassembly

```asm
0x180066d28  mov     [rsp-8+arg_18], rbx
0x180066d2d  push    rbp
0x180066d2e  push    rsi
0x180066d2f  push    rdi
0x180066d30  push    r12
0x180066d32  push    r13
0x180066d34  push    r14
0x180066d36  push    r15
0x180066d38  lea     rbp, [rsp-170h]
0x180066d40  sub     rsp, 270h
0x180066d47  mov     rax, cs:__security_cookie
0x180066d4e  xor     rax, rsp
0x180066d51  mov     [rbp+1A0h+var_40], rax
0x180066d58  xor     r12d, r12d
0x180066d5b  mov     [rbp+1A0h+var_1A0], r8
0x180066d5f  xorps   xmm0, xmm0
0x180066d62  mov     [rbp+1A0h+var_1B8], rcx
0x180066d66  mov     r15, r8
0x180066d69  mov     [rbp+1A0h+TokenHandle], r12
0x180066d6d  mov     r13, rdx
0x180066d70  mov     qword ptr [rbp+1A0h+var_1E8], r12
0x180066d74  mov     rdi, rcx
0x180066d77  mov     [rbp+1A0h+TokenInformation], r12d
0x180066d7b  xor     eax, eax
0x180066d7d  mov     qword ptr [rbp+1A0h+var_1E8+8], r12
0x180066d81  movups  [rbp+1A0h+var_188], xmm0
0x180066d85  lea     r8d, [r12+4Ch]; Size
0x180066d8a  mov     qword ptr [rbp+1A0h+Handle], r12
0x180066d8e  xor     edx, edx; Val
0x180066d90  mov     [rsp+2A0h+var_228], r12d
0x180066d95  lea     rcx, [rbp+1A0h+var_90]; void *
0x180066d9c  mov     qword ptr [rbp+1A0h+Handle+8], r12
0x180066da0  movups  [rbp+1A0h+var_198], xmm0
0x180066da4  mov     qword ptr [rbp+1A0h+var_1D8], r12
0x180066da8  movups  [rbp+1A0h+var_188+0Ch], xmm0
0x180066dac  mov     qword ptr [rbp+1A0h+var_1D8+8], r12
0x180066db0  mov     [rbp+1A0h+var_1C8], r12
0x180066db4  mov     [rbp+1A0h+var_200], r12
0x180066db8  movups  [rbp+1A0h+var_160], xmm0
0x180066dbc  mov     [rbp+1A0h+var_130], rax
0x180066dc0  movups  [rbp+1A0h+var_150], xmm0
0x180066dc4  movups  [rbp+1A0h+var_140], xmm0
0x180066dc8  call    memset_0
0x180066dcd  mov     [rbp+1A0h+Sid], r12
0x180066dd1  mov     [rsp+2A0h+packageFamilyNameLength], 41h ; 'A'
0x180066dd9  mov     [rbp+1A0h+var_210], 120002h
0x180066de0  mov     dword ptr [rbp+1A0h+IdentifierAuthority.Value], r12d
0x180066de4  mov     word ptr [rbp+1A0h+IdentifierAuthority.Value+4], 0F00h
0x180066dea  mov     [rbp+1A0h+var_1C0], r12
0x180066dee  mov     [rbp+1A0h+var_20C], r12d
0x180066df2  cmp     [r13+0], r12
0x180066df6  jz      loc_18006734A
0x180066dfc  cmp     cs:ValuesQueried, r12d
0x180066e03  lea     ebx, [r12+1]
0x180066e08  mov     rsi, [r13+8]
0x180066e0c  mov     r14d, [r13+10h]
0x180066e10  mov     [rsp+2A0h+var_230], rsi
0x180066e15  mov     [rsp+2A0h+var_240], r14d
0x180066e1a  jz      loc_18006730A
0x180066e20  mov     ecx, 0F01FFh
0x180066e25  test    rdi, rdi
0x180066e28  jz      loc_180067354
0x180066e2e  mov     [rsp+2A0h+P], r12
0x180066e33  cmp     [r13+10h], r12d
0x180066e37  ja      loc_1800670A5
0x180066e3d  mov     r9d, 4; TokenInformationLength
0x180066e43  lea     rax, [rsp+2A0h+var_228]
0x180066e48  lea     r8, [rbp+1A0h+TokenInformation]; TokenInformation
0x180066e4c  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180066e51  mov     rcx, rdi; TokenHandle
0x180066e54  lea     edx, [r9+19h]; TokenInformationClass
0x180066e58  call    cs:__imp_NtQueryInformationToken
0x180066e5e  mov     ebx, eax
0x180066e60  test    eax, eax
0x180066e62  js      loc_18006712D
0x180066e68  lea     rax, [rbp+1A0h+var_1B0]
0x180066e6c  mov     [rbp+1A0h+var_1B0], r12
0x180066e70  lea     r9, [rbp+1A0h+var_1A8]
0x180066e74  mov     [rsp+2A0h+ReturnLength], rax
0x180066e79  lea     r8, [rbp+1A0h+var_210]
0x180066e7d  mov     [rbp+1A0h+var_1A8], r12
0x180066e81  mov     edx, 21h ; '!'
0x180066e86  mov     rcx, rdi
0x180066e89  mov     sil, r12b
0x180066e8c  call    AppModelPolicy_GetPolicy_Internal
0x180066e91  mov     r14d, 6
0x180066e97  cmp     [rbp+1A0h+TokenInformation], r12d
0x180066e9b  jnz     loc_180067153
0x180066ea1  cmp     [rbp+1A0h+var_210], 210001h
0x180066ea8  jz      loc_1800670B6
0x180066eae  mov     rcx, [r13+0]; Sid
0x180066eb2  lea     rax, [rbp+1A0h+var_1C8]
0x180066eb6  mov     qword ptr [rsp+2A0h+SubAuthority6], rax; __int64
0x180066ebb  lea     r9, [rbp+1A0h+Handle+8]
0x180066ebf  lea     rax, [rbp+1A0h+var_1D8+8]
0x180066ec3  mov     rdx, rdi; TokenHandle
0x180066ec6  mov     qword ptr [rsp+2A0h+SubAuthority5], rax; __int64
0x180066ecb  lea     r8, [rbp+1A0h+Handle]
0x180066ecf  lea     rax, [rbp+1A0h+var_1D8]
0x180066ed3  mov     qword ptr [rsp+2A0h+SubAuthority4], rax; __int64
0x180066ed8  lea     rax, [rbp+1A0h+var_1E8+8]
0x180066edc  mov     qword ptr [rsp+2A0h+SubAuthority3], rax; __int64
0x180066ee1  lea     rax, [rbp+1A0h+var_1E8]
0x180066ee5  mov     [rsp+2A0h+ReturnLength], rax; __int64
0x180066eea  call    BasepCreateLowBoxObjectDirectories
0x180066eef  mov     ebx, eax
0x180066ef1  test    eax, eax
0x180066ef3  js      loc_180066FAE
0x180066ef9  mov     rax, qword ptr [rbp+1A0h+Handle]
0x180066efd  lea     rdx, [rbp+1A0h+var_20C]
0x180066f01  mov     rcx, [r13+0]
0x180066f05  mov     qword ptr [rbp+1A0h+var_160], rax
0x180066f09  mov     rax, qword ptr [rbp+1A0h+Handle+8]
0x180066f0d  mov     qword ptr [rbp+1A0h+var_160+8], rax
0x180066f11  mov     rax, qword ptr [rbp+1A0h+var_1E8]
0x180066f15  mov     qword ptr [rbp+1A0h+var_150], rax
0x180066f19  mov     rax, qword ptr [rbp+1A0h+var_1E8+8]
0x180066f1d  mov     qword ptr [rbp+1A0h+var_150+8], rax
0x180066f21  mov     rax, qword ptr [rbp+1A0h+var_1D8]
0x180066f25  mov     qword ptr [rbp+1A0h+var_140], rax
0x180066f29  mov     rax, qword ptr [rbp+1A0h+var_1D8+8]
0x180066f2d  mov     qword ptr [rbp+1A0h+var_140+8], rax
0x180066f31  call    cs:__imp_RtlGetAppContainerSidType
0x180066f37  mov     ebx, eax
0x180066f39  test    eax, eax
0x180066f3b  js      short loc_180066FAE
0x180066f3d  cmp     [rbp+1A0h+var_20C], 1
0x180066f41  jz      loc_180067140
0x180066f47  lea     rax, [rbp+1A0h+var_160]
0x180066f4b  mov     dword ptr [rbp+1A0h+var_198], 30h ; '0'
0x180066f52  mov     qword ptr [rsp+2A0h+SubAuthority6], rax
0x180066f57  lea     r9, [rbp+1A0h+var_198]
0x180066f5b  mov     rax, [r13+8]
0x180066f5f  lea     rcx, [rbp+1A0h+var_200]
0x180066f63  mov     [rsp+2A0h+SubAuthority5], r14d
0x180066f68  xorps   xmm0, xmm0
0x180066f6b  mov     qword ptr [rsp+2A0h+SubAuthority4], rax
0x180066f70  mov     r8d, 0F01FFh
0x180066f76  mov     eax, [r13+10h]
0x180066f7a  mov     rdx, rdi
0x180066f7d  mov     [rsp+2A0h+SubAuthority3], eax
0x180066f81  mov     rax, [r13+0]
0x180066f85  mov     [rsp+2A0h+ReturnLength], rax
0x180066f8a  mov     qword ptr [rbp+1A0h+var_198+8], r12
0x180066f8e  mov     dword ptr [rbp+1A0h+var_188+8], r12d
0x180066f92  mov     qword ptr [rbp+1A0h+var_188], r12
0x180066f96  movdqu  [rbp+1A0h+var_178], xmm0
0x180066f9b  call    cs:__imp_NtCreateLowBoxToken
0x180066fa1  mov     ebx, eax
0x180066fa3  test    eax, eax
0x180066fa5  js      short loc_180066FAE
0x180066fa7  mov     rax, [rbp+1A0h+var_200]
0x180066fab  mov     [r15], rax
0x180066fae  mov     rdi, [rsp+2A0h+P]
0x180066fb3  mov     rsi, [rsp+2A0h+var_230]
0x180066fb8  mov     r14d, [rsp+2A0h+var_240]
0x180066fbd  mov     rcx, qword ptr [rbp+1A0h+Handle]; Handle
0x180066fc1  test    rcx, rcx
0x180066fc4  jz      short loc_180066FCC
0x180066fc6  call    cs:__imp_NtClose
0x180066fcc  mov     rcx, qword ptr [rbp+1A0h+Handle+8]; Handle
0x180066fd0  test    rcx, rcx
0x180066fd3  jz      short loc_180066FDB
0x180066fd5  call    cs:__imp_NtClose
0x180066fdb  mov     rcx, qword ptr [rbp+1A0h+var_1E8]; Handle
0x180066fdf  test    rcx, rcx
0x180066fe2  jz      short loc_180066FEA
0x180066fe4  call    cs:__imp_NtClose
0x180066fea  mov     rcx, qword ptr [rbp+1A0h+var_1E8+8]; Handle
0x180066fee  test    rcx, rcx
0x180066ff1  jz      short loc_180066FF9
0x180066ff3  call    cs:__imp_NtClose
0x180066ff9  mov     rcx, qword ptr [rbp+1A0h+var_1D8]; Handle
0x180066ffd  test    rcx, rcx
0x180067000  jz      short loc_180067008
0x180067002  call    cs:__imp_NtClose
0x180067008  mov     rcx, qword ptr [rbp+1A0h+var_1D8+8]; Handle
0x18006700c  test    rcx, rcx
0x18006700f  jz      short loc_180067017
0x180067011  call    cs:__imp_NtClose
0x180067017  mov     rcx, [rbp+1A0h+var_1C8]; Handle
0x18006701b  test    rcx, rcx
0x18006701e  jnz     loc_180067135
0x180067024  mov     rcx, [rbp+1A0h+TokenHandle]; Handle
0x180067028  test    rcx, rcx
0x18006702b  jz      short loc_180067033
0x18006702d  call    cs:__imp_NtClose
0x180067033  mov     rax, [rbp+1A0h+Sid]
0x180067037  test    rax, rax
0x18006703a  jz      short loc_180067045
0x18006703c  mov     rcx, rax; Sid
0x18006703f  call    cs:__imp_RtlFreeSid
0x180067045  mov     rcx, [rbp+1A0h+var_1C0]; Sid
0x180067049  test    rcx, rcx
0x18006704c  jz      short loc_180067054
0x18006704e  call    cs:__imp_RtlFreeSid
0x180067054  test    rdi, rdi
0x180067057  jz      short loc_180067071
0x180067059  mov     rcx, gs:60h
0x180067062  mov     r8, rdi; P
0x180067065  xor     edx, edx; Flags
0x180067067  mov     rcx, [rcx+30h]; HeapHandle
0x18006706b  call    cs:__imp_RtlFreeHeap
0x180067071  mov     [r13+8], rsi
0x180067075  mov     eax, ebx
0x180067077  mov     [r13+10h], r14d
0x18006707b  mov     rcx, [rbp+1A0h+var_40]
0x180067082  xor     rcx, rsp; StackCookie
0x180067085  call    __security_check_cookie
0x18006708a  mov     rbx, [rsp+2A0h+arg_18]
0x180067092  add     rsp, 270h
0x180067099  pop     r15
0x18006709b  pop     r14
0x18006709d  pop     r13
0x18006709f  pop     r12
0x1800670a1  pop     rdi
0x1800670a2  pop     rsi
0x1800670a3  pop     rbp
0x1800670a4  retn
0x1800670a5  cmp     [r13+8], r12
0x1800670a9  jnz     loc_180066E3D
0x1800670af  mov     ebx, 0C000000Dh
0x1800670b4  jmp     short loc_18006712D
0x1800670b6  lea     r8, [rbp+1A0h+packageFamilyName]; packageFamilyName
0x1800670bd  mov     rcx, rdi; token
0x1800670c0  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800670c5  call    GetPackageFamilyNameFromToken
0x1800670ca  lea     r8, [rbp+1A0h+packageFamilyName]; packageFamilyName
0x1800670d1  mov     esi, 0C0070000h
0x1800670d6  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800670db  mov     rcx, rdi; token
0x1800670de  test    eax, eax
0x1800670e0  jg      loc_1800672FB
0x1800670e6  call    GetPackageFamilyNameFromToken
0x1800670eb  mov     ebx, eax
0x1800670ed  test    ebx, ebx
0x1800670ef  js      short loc_180067123
0x1800670f1  lea     rdx, [rbp+1A0h+Sid]; unsigned __int16 *
0x1800670f5  lea     rcx, [rbp+1A0h+packageFamilyName]; SourceString
0x1800670fc  call    ?PackageSidFromFamilyName@Internal@ARI@@YAJPEBGPEAPEAX@Z; ARI::Internal::PackageSidFromFamilyName(ushort const *,void * *)
0x180067101  lea     rdx, [rbp+1A0h+Sid]; unsigned __int16 *
0x180067105  lea     rcx, [rbp+1A0h+packageFamilyName]; SourceString
0x18006710c  test    eax, eax
0x18006710e  jg      loc_1800673BC
0x180067114  call    ?PackageSidFromFamilyName@Internal@ARI@@YAJPEBGPEAPEAX@Z; ARI::Internal::PackageSidFromFamilyName(ushort const *,void * *)
0x180067119  mov     ebx, eax
0x18006711b  test    ebx, ebx
0x18006711d  jns     loc_1800671AA
0x180067123  mov     r14d, [rsp+2A0h+var_240]
0x180067128  mov     rsi, [rsp+2A0h+var_230]
0x18006712d  mov     rdi, r12
0x180067130  jmp     loc_180066FBD
0x180067135  call    cs:__imp_NtClose
0x18006713b  jmp     loc_180067024
0x180067140  mov     rax, [rbp+1A0h+var_1C8]
0x180067144  mov     r14d, 7
0x18006714a  mov     [rbp+1A0h+var_130], rax
0x18006714e  jmp     loc_180066F47
0x180067153  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180067159  mov     [rsp+2A0h+var_228], 4Ch ; 'L'
0x180067161  lea     rax, [rsp+2A0h+var_228]
0x180067166  mov     rcx, rdi; TokenHandle
0x180067169  lea     r8, [rbp+1A0h+var_90]; TokenInformation
0x180067170  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180067175  lea     edx, [r9-2Dh]; TokenInformationClass
0x180067179  call    cs:__imp_NtQueryInformationToken
0x18006717f  mov     ebx, eax
0x180067181  test    eax, eax
0x180067183  js      loc_18006707B
0x180067189  mov     rdx, [r13+0]
0x18006718d  mov     rcx, [rbp+1A0h+var_90]
0x180067194  call    cs:__imp_RtlIsParentOfChildAppContainer
0x18006719a  test    al, al
0x18006719c  jz      loc_18006738E
0x1800671a2  mov     sil, 1
0x1800671a5  jmp     loc_1800672E3
0x1800671aa  mov     r8d, [r13+10h]
0x1800671ae  xor     edx, edx; Flags
0x1800671b0  mov     rcx, gs:60h
0x1800671b9  inc     r8d
0x1800671bc  shl     r8, 4; Size
0x1800671c0  mov     rcx, [rcx+30h]; HeapHandle
0x1800671c4  call    cs:__imp_RtlAllocateHeap
0x1800671ca  mov     [rsp+2A0h+P], rax
0x1800671cf  mov     rdi, rax
0x1800671d2  test    rax, rax
0x1800671d5  jz      loc_1800673CB
0x1800671db  cmp     [r13+10h], r12d
0x1800671df  jbe     short loc_1800671F5
0x1800671e1  mov     r8d, [r13+10h]
0x1800671e5  mov     rcx, rax; void *
0x1800671e8  mov     rdx, [r13+8]; Src
0x1800671ec  shl     r8, 4; Size
0x1800671f0  call    memcpy_0
0x1800671f5  mov     rbx, [rbp+1A0h+Sid]
0x1800671f9  mov     edx, 7; nSubAuthority
0x1800671fe  mov     rcx, rbx; pSid
0x180067201  call    GetSidSubAuthority
0x180067206  mov     edx, r14d; nSubAuthority
0x180067209  mov     rcx, rbx; pSid
  ... truncated ...
```
