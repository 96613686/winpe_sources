# CloudCacheInitializer::AddCapabilityAccessToObject(ushort const *,_SE_OBJECT_TYPE,ushort const *)

- ea: `0x18003b5f4`
- end: `0x18003b962`
- name: `?AddCapabilityAccessToObject@CloudCacheInitializer@@AEAAJPEBGW4_SE_OBJECT_TYPE@@0@Z`
- size: `878`
- prototype: `int(CloudCacheInitializer *__hidden this, const unsigned __int16 *, enum _SE_OBJECT_TYPE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c1a0`

## callees

- `0x1800320d4`
- `0x18003b254`
- `0x18003b5f4`
- `0x18003b968`
- `0x1800c7f8c`
- `0x1800c8458`
- `0x1800ff298`
- `0x1801201a0`
- `0x180120c94`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b932`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b93d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b932`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b93d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b795`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b894`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b795`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b894`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8ec`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003b691`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003b691`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18003b7c4`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18003b7c4`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003b76f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003b76f`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18003b6f5`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18003b6f5`

## string_xrefs

- `0x18003b834`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003b86f`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003b8c7`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003b919`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003b951`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`

## pseudocode

```c
__int64 __fastcall CloudCacheInitializer::AddCapabilityAccessToObject(
        CloudCacheInitializer *this,
        WCHAR *a2,
        enum _SE_OBJECT_TYPE a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rcx
  const wchar_t *v6; // rax
  unsigned __int64 v7; // r9
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  DWORD NamedSecurityInfoW; // eax
  DWORD v12; // ebx
  PACL v13; // r8
  DWORD v14; // eax
  PACL v15; // rcx
  int v17; // eax
  PACL v18; // rcx
  HANDLE v19; // rcx
  int v20; // eax
  PACL v21; // rcx
  __int64 v22; // rdx
  int ppsidGroup; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-E0h]
  unsigned int ppsidGroupb; // [rsp+20h] [rbp-E0h]
  PACL pDacl; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  PACL OldAcl; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v30; // [rsp+60h] [rbp-A0h] BYREF
  PACL *p_pDacl; // [rsp+70h] [rbp-90h]
  PACL NewAcl; // [rsp+78h] [rbp-88h] BYREF
  char v33; // [rsp+80h] [rbp-80h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+C0h] [rbp-40h]
  int v36; // [rsp+C4h] [rbp-3Ch]
  int v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+DCh] [rbp-24h]
  _BYTE *v39; // [rsp+E8h] [rbp-18h]
  _BYTE v40[48]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v41[48]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v30 = 0;
  v5 = 0x7FFF;
  v6 = L"cloudStore";
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = v5 == 0 ? 0xC000000D : 0;
  if ( !v5 )
  {
    v22 = 943;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v22,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
             (const char *)v7,
             ppsidGroup);
  }
  *((_QWORD *)&v30 + 1) = L"cloudStore";
  LOWORD(v30) = -2 - 2 * v5;
  WORD1(v30) = -2 * v5;
  v8 = RtlDeriveCapabilitySidsFromName(&v30, v40, v41, v7);
  if ( v8 < 0 )
  {
    v7 = (unsigned int)v8;
    v22 = 950;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v22,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
             (const char *)v7,
             ppsidGroup);
  }
  hObject = (HANDLE)-1LL;
  v9 = CloudStoreUtilities::CreateFileEnsureNotLinked(a2, &hObject);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BD,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)(unsigned int)v9,
      ppsidGroup);
LABEL_33:
    std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&hObject);
    return v10;
  }
  OldAcl = 0;
  hMem = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( NamedSecurityInfoW )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3C2,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)NamedSecurityInfoW,
            ppsidGroupa);
    if ( hMem )
      LocalFree(hMem);
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return v10;
    v19 = hObject;
LABEL_37:
    CloseHandle(v19);
    return v10;
  }
  memset_0(&pListOfExplicitEntries, 0, 0x60u);
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v41;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
  v39 = v40;
  v35 = 0x10000000;
  v37 = 3;
  p_pDacl = &pDacl;
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  v36 = 2;
  v38 = 0;
  pDacl = 0;
  NewAcl = 0;
  v33 = 1;
  v12 = SetEntriesInAclW(2u, &pListOfExplicitEntries, OldAcl, &NewAcl);
  if ( v33 )
  {
    v13 = *p_pDacl;
    *p_pDacl = NewAcl;
    if ( v13 )
      LocalFree(v13);
  }
  if ( v12 )
  {
    v20 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3D4,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)v12,
            ppsidGroupa);
    v21 = pDacl;
    v10 = v20;
    pDacl = 0;
    if ( v21 )
      LocalFree(v21);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    goto LABEL_33;
  }
  v14 = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
  if ( v14 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3D5,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            (const char *)v14,
            ppsidGroupb);
    v18 = pDacl;
    v10 = v17;
    pDacl = 0;
    if ( v18 )
      LocalFree(v18);
    if ( hMem )
      LocalFree(hMem);
    v19 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return v10;
    goto LABEL_37;
  }
  v15 = pDacl;
  pDacl = 0;
  if ( v15 )
    LocalFree(v15);
  if ( hMem )
    LocalFree(hMem);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x18003b5f4  mov     [rsp-8+arg_0], rbx
0x18003b5f9  mov     [rsp-8+arg_10], rsi
0x18003b5fe  push    rbp
0x18003b5ff  push    rdi
0x18003b600  push    r14
0x18003b602  lea     rbp, [rsp-60h]
0x18003b607  sub     rsp, 160h
0x18003b60e  mov     rax, cs:__security_cookie
0x18003b615  xor     rax, rsp
0x18003b618  mov     [rbp+70h+var_20], rax
0x18003b61c  xor     esi, esi
0x18003b61e  mov     rdi, rdx
0x18003b621  xorps   xmm0, xmm0
0x18003b624  lea     rdx, aCloudstore; "cloudStore"
0x18003b62b  movups  [rsp+170h+var_110], xmm0
0x18003b630  mov     ecx, 7FFFh
0x18003b635  mov     rax, rdx
0x18003b638  lea     r14d, [rsi+2]
0x18003b63c  cmp     [rax], si
0x18003b63f  jz      short loc_18003B64A
0x18003b641  add     rax, r14
0x18003b644  sub     rcx, 1
0x18003b648  jnz     short loc_18003B63C
0x18003b64a  mov     rax, rcx
0x18003b64d  neg     rax
0x18003b650  sbb     r9d, r9d
0x18003b653  not     r9d
0x18003b656  and     r9d, 0C000000Dh; char *
0x18003b65d  test    rcx, rcx
0x18003b660  jz      loc_18003B948
0x18003b666  add     cx, cx
0x18003b669  mov     qword ptr [rsp+170h+var_110+8], rdx
0x18003b66e  mov     eax, 0FFFEh
0x18003b673  lea     r8, [rbp+70h+var_50]
0x18003b677  sub     ax, cx
0x18003b67a  lea     rdx, [rbp+70h+var_80]
0x18003b67e  mov     word ptr [rsp+170h+var_110], ax
0x18003b683  lea     rcx, [rsp+170h+var_110]
0x18003b688  add     ax, r14w
0x18003b68c  mov     word ptr [rsp+170h+var_110+2], ax
0x18003b691  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18003b697  test    eax, eax
0x18003b699  js      loc_18003B90B
0x18003b69f  lea     rdx, [rsp+170h+hObject]
0x18003b6a4  mov     [rsp+170h+hObject], 0FFFFFFFFFFFFFFFFh
0x18003b6ad  mov     rcx, rdi; lpFileName
0x18003b6b0  call    ?CreateFileEnsureNotLinked@CloudStoreUtilities@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; CloudStoreUtilities::CreateFileEnsureNotLinked(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18003b6b5  mov     ebx, eax
0x18003b6b7  test    eax, eax
0x18003b6b9  js      loc_18003B915
0x18003b6bf  xor     r9d, r9d; ppsidOwner
0x18003b6c2  mov     [rsp+170h+OldAcl], rsi
0x18003b6c7  lea     rax, [rsp+170h+hMem]
0x18003b6cc  mov     [rsp+170h+hMem], rsi
0x18003b6d1  mov     [rsp+170h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18003b6d6  mov     rcx, rdi; pObjectName
0x18003b6d9  lea     rax, [rsp+170h+OldAcl]
0x18003b6de  mov     [rsp+170h+ppSacl], rsi; ppSacl
0x18003b6e3  mov     [rsp+170h+ppDacl], rax; ppDacl
0x18003b6e8  lea     edx, [r9+1]; ObjectType
0x18003b6ec  lea     r8d, [r9+4]; SecurityInfo
0x18003b6f0  mov     [rsp+170h+ppsidGroup], rsi; unsigned int
0x18003b6f5  call    cs:__imp_GetNamedSecurityInfoW
0x18003b6fb  test    eax, eax
0x18003b6fd  jnz     loc_18003B830
0x18003b703  xor     edx, edx; Val
0x18003b705  lea     r8d, [rax+60h]; Size
0x18003b709  lea     rcx, [rbp+70h+pListOfExplicitEntries]; void *
0x18003b70d  call    memset_0
0x18003b712  mov     r8, [rsp+170h+OldAcl]; OldAcl
0x18003b717  lea     rax, [rbp+70h+var_50]
0x18003b71b  mov     ecx, 3
0x18003b720  mov     [rbp+70h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18003b724  mov     edx, 10000000h
0x18003b729  mov     [rbp+70h+pListOfExplicitEntries.grfInheritance], ecx
0x18003b72c  lea     rax, [rbp+70h+var_80]
0x18003b730  mov     [rbp+70h+pListOfExplicitEntries.grfAccessPermissions], edx
0x18003b733  mov     [rbp+70h+var_88], rax
0x18003b737  lea     r9, [rsp+170h+NewAcl]; NewAcl
0x18003b73c  lea     rax, [rsp+170h+pDacl]
0x18003b741  mov     [rbp+70h+var_B0], edx
0x18003b744  mov     [rbp+70h+var_A8], ecx
0x18003b747  lea     rdx, [rbp+70h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18003b74b  mov     ecx, r14d; cCountOfExplicitEntries
0x18003b74e  mov     [rsp+170h+var_100], rax
0x18003b753  mov     [rbp+70h+pListOfExplicitEntries.grfAccessMode], r14d
0x18003b757  mov     [rbp+70h+pListOfExplicitEntries.Trustee.TrusteeForm], esi
0x18003b75a  mov     [rbp+70h+var_AC], r14d
0x18003b75e  mov     [rbp+70h+var_94], esi
0x18003b761  mov     [rsp+170h+pDacl], rsi
0x18003b766  mov     [rsp+170h+NewAcl], rsi
0x18003b76b  mov     [rbp+70h+var_F0], 1
0x18003b76f  call    cs:__imp_SetEntriesInAclW
0x18003b775  mov     ebx, eax
0x18003b777  cmp     [rbp+70h+var_F0], sil
0x18003b77b  jz      short loc_18003B79B
0x18003b77d  mov     rdx, [rsp+170h+var_100]
0x18003b782  mov     rcx, [rsp+170h+NewAcl]
0x18003b787  mov     r8, [rdx]
0x18003b78a  mov     [rdx], rcx
0x18003b78d  test    r8, r8
0x18003b790  jz      short loc_18003B79B
0x18003b792  mov     rcx, r8; hMem
0x18003b795  call    cs:__imp_LocalFree
0x18003b79b  test    ebx, ebx
0x18003b79d  jnz     loc_18003B8C3
0x18003b7a3  mov     rax, [rsp+170h+pDacl]
0x18003b7a8  lea     edx, [rbx+1]; ObjectType
0x18003b7ab  mov     [rsp+170h+ppSacl], rsi; pSacl
0x18003b7b0  lea     r8d, [rbx+4]; SecurityInfo
0x18003b7b4  mov     [rsp+170h+ppDacl], rax; pDacl
0x18003b7b9  xor     r9d, r9d; psidOwner
0x18003b7bc  mov     rcx, rdi; pObjectName
0x18003b7bf  mov     [rsp+170h+ppsidGroup], rsi; unsigned int
0x18003b7c4  call    cs:__imp_SetNamedSecurityInfoW
0x18003b7ca  test    eax, eax
0x18003b7cc  jnz     loc_18003B86B
0x18003b7d2  mov     rcx, [rsp+170h+pDacl]; hMem
0x18003b7d7  mov     [rsp+170h+pDacl], rsi
0x18003b7dc  test    rcx, rcx
0x18003b7df  jz      short loc_18003B7E7
0x18003b7e1  call    cs:__imp_LocalFree
0x18003b7e7  mov     rcx, [rsp+170h+hMem]; hMem
0x18003b7ec  test    rcx, rcx
0x18003b7ef  jz      short loc_18003B7F7
0x18003b7f1  call    cs:__imp_LocalFree
0x18003b7f7  mov     rcx, [rsp+170h+hObject]; hObject
0x18003b7fc  lea     rax, [rcx-1]
0x18003b800  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b804  jbe     loc_18003B93D
0x18003b80a  xor     eax, eax
0x18003b80c  mov     rcx, [rbp+70h+var_20]
0x18003b810  xor     rcx, rsp; StackCookie
0x18003b813  call    __security_check_cookie
0x18003b818  lea     r11, [rsp+170h+var_10]
0x18003b820  mov     rbx, [r11+20h]
0x18003b824  mov     rsi, [r11+30h]
0x18003b828  mov     rsp, r11
0x18003b82b  pop     r14
0x18003b82d  pop     rdi
0x18003b82e  pop     rbp
0x18003b82f  retn
0x18003b830  mov     rcx, [rbp+78h]; this
0x18003b834  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003b83b  mov     r9d, eax; char *
0x18003b83e  mov     edx, 3C2h; void *
0x18003b843  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003b848  mov     rcx, [rsp+170h+hMem]; hMem
0x18003b84d  mov     ebx, eax
0x18003b84f  test    rcx, rcx
0x18003b852  jnz     short loc_18003B8BB
0x18003b854  mov     rdx, [rsp+170h+hObject]
0x18003b859  lea     rcx, [rdx-1]
0x18003b85d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003b861  jbe     loc_18003B92F
0x18003b867  mov     eax, ebx
0x18003b869  jmp     short loc_18003B80C
0x18003b86b  mov     rcx, [rbp+78h]; this
0x18003b86f  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003b876  mov     r9d, eax; char *
0x18003b879  mov     edx, 3D5h; void *
0x18003b87e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003b883  mov     rcx, [rsp+170h+pDacl]; hMem
0x18003b888  mov     ebx, eax
0x18003b88a  mov     [rsp+170h+pDacl], rsi
0x18003b88f  test    rcx, rcx
0x18003b892  jz      short loc_18003B89A
0x18003b894  call    cs:__imp_LocalFree
0x18003b89a  mov     rcx, [rsp+170h+hMem]; hMem
0x18003b89f  test    rcx, rcx
0x18003b8a2  jz      short loc_18003B8AA
0x18003b8a4  call    cs:__imp_LocalFree
0x18003b8aa  mov     rcx, [rsp+170h+hObject]
0x18003b8af  lea     rax, [rcx-1]
0x18003b8b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b8b7  ja      short loc_18003B867
0x18003b8b9  jmp     short loc_18003B932
0x18003b8bb  call    cs:__imp_LocalFree
0x18003b8c1  jmp     short loc_18003B854
0x18003b8c3  mov     rcx, [rbp+78h]; this
0x18003b8c7  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003b8ce  mov     r9d, ebx; char *
0x18003b8d1  mov     edx, 3D4h; void *
0x18003b8d6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003b8db  mov     rcx, [rsp+170h+pDacl]; hMem
0x18003b8e0  mov     ebx, eax
0x18003b8e2  mov     [rsp+170h+pDacl], rsi
0x18003b8e7  test    rcx, rcx
0x18003b8ea  jz      short loc_18003B8F2
0x18003b8ec  call    cs:__imp_LocalFree
0x18003b8f2  lea     rcx, [rsp+170h+hMem]
0x18003b8f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b8fc  lea     rcx, [rsp+170h+hObject]
0x18003b901  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x18003b906  jmp     loc_18003B867
0x18003b90b  mov     r9d, eax
0x18003b90e  mov     edx, 3B6h
0x18003b913  jmp     short loc_18003B94D
0x18003b915  mov     rcx, [rbp+78h]; this
0x18003b919  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003b920  mov     r9d, eax; char *
0x18003b923  mov     edx, 3BDh; void *
0x18003b928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b92d  jmp     short loc_18003B8FC
0x18003b92f  mov     rcx, rdx; hObject
0x18003b932  call    cs:__imp_CloseHandle
0x18003b938  jmp     loc_18003B867
0x18003b93d  call    cs:__imp_CloseHandle
0x18003b943  jmp     loc_18003B80A
0x18003b948  mov     edx, 3AFh; void *
0x18003b94d  mov     rcx, [rbp+78h]; this
0x18003b951  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003b958  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003b95d  jmp     loc_18003B80C
```
