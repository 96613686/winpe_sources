# OSIntegration::DEH::Internal::AddAceToObjectSecurityDescriptor(ushort const *,_SE_OBJECT_TYPE,ushort *,_TRUSTEE_FORM,ulong,_ACCESS_MODE,ulong)

- ea: `0x180069c14`
- end: `0x180069dda`
- name: `?AddAceToObjectSecurityDescriptor@Internal@DEH@OSIntegration@@YAJPEBGW4_SE_OBJECT_TYPE@@PEAGW4_TRUSTEE_FORM@@KW4_ACCESS_MODE@@K@Z`
- size: `454`
- prototype: `__int64 __usercall@<rax>(LPWSTR pObjectName@<rcx>, const unsigned __int16 *@<rdx>, enum _SE_OBJECT_TYPE@<r8d>, unsigned __int16 *@<r9>, enum _TRUSTEE_FORM, unsigned int, enum _ACCESS_MODE, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800546d8`
- `0x1800e5b78`

## callees

- `0x180048cd4`
- `0x180069c14`
- `0x180069eb4`
- `0x180075e2c`
- `0x1800762cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069ca7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069cc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069d14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069ca7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069cc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180069d14`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180069d42`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180069d42`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180069d82`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180069d82`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180069c74`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180069c74`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::AddAceToObjectSecurityDescriptor(
        LPWSTR pObjectName,
        const unsigned __int16 *a2,
        WCHAR *a3,
        unsigned __int16 *a4,
        enum _TRUSTEE_FORM a5,
        ACCESS_MODE a6)
{
  DWORD NamedSecurityInfoW; // eax
  unsigned int v9; // ebx
  DWORD v10; // eax
  __int64 v11; // rdx
  unsigned int psidGroup; // [rsp+28h] [rbp-31h]
  HLOCAL pDacl; // [rsp+48h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-9h] BYREF
  PACL OldAcl; // [rsp+58h] [rbp-1h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A0h] [rbp+47h]

  pDacl = 0;
  OldAcl = 0;
  hMem = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( !NamedSecurityInfoW )
  {
    pListOfExplicitEntries.Trustee.ptstrName = a3;
    pListOfExplicitEntries.grfAccessPermissions = a5;
    pListOfExplicitEntries.grfAccessMode = a6;
    memset(&pListOfExplicitEntries.grfInheritance, 0, 32);
    pDacl = 0;
    v10 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, (PACL *)&pDacl);
    if ( v10 )
    {
      v11 = 93;
    }
    else
    {
      v10 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, (PACL)pDacl, 0);
      if ( !v10 )
      {
        v9 = 0;
        goto LABEL_11;
      }
      v11 = 103;
    }
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v11,
           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
           (const char *)v10,
           psidGroup);
LABEL_11:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pDacl);
    return v9;
  }
  v9 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x51,
         (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
         (const char *)NamedSecurityInfoW,
         psidGroup);
  if ( hMem )
    LocalFree(hMem);
  return v9;
}

```

## disassembly

```asm
0x180069c14  mov     r11, rsp
0x180069c17  mov     [r11+8], rbx
0x180069c1b  mov     [r11+10h], rdi
0x180069c1f  push    rbp
0x180069c20  lea     rbp, [r11-47h]
0x180069c24  sub     rsp, 90h
0x180069c2b  xor     r9d, r9d; ppsidOwner
0x180069c2e  mov     [rbp+3Fh+var_50], 0
0x180069c36  lea     rax, [rbp+3Fh+hMem]
0x180069c3a  mov     [rbp+3Fh+OldAcl], 0
0x180069c42  mov     [r11-60h], rax
0x180069c46  mov     rbx, r8
0x180069c49  mov     qword ptr [r11-68h], 0
0x180069c51  lea     rax, [rbp+3Fh+OldAcl]
0x180069c55  mov     [r11-70h], rax
0x180069c59  lea     edx, [r9+1]; ObjectType
0x180069c5d  lea     r8d, [r9+4]; SecurityInfo
0x180069c61  mov     qword ptr [r11-78h], 0
0x180069c69  mov     rdi, rcx
0x180069c6c  mov     [rbp+3Fh+hMem], 0
0x180069c74  call    cs:__imp_GetNamedSecurityInfoW
0x180069c7b  nop     dword ptr [rax+rax+00h]
0x180069c80  test    eax, eax
0x180069c82  jz      short loc_180069CD1
0x180069c84  mov     rcx, [rbp+47h]; this
0x180069c88  lea     r8, aOnecoreAdminAp_29; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180069c8f  mov     r9d, eax; char *
0x180069c92  mov     edx, 51h ; 'Q'; void *
0x180069c97  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180069c9c  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180069ca0  mov     ebx, eax
0x180069ca2  test    rcx, rcx
0x180069ca5  jz      short loc_180069CB3
0x180069ca7  call    cs:__imp_LocalFree
0x180069cae  nop     dword ptr [rax+rax+00h]
0x180069cb3  mov     rcx, [rbp+3Fh+var_50]; hMem
0x180069cb7  test    rcx, rcx
0x180069cba  jz      loc_180069DC2
0x180069cc0  call    cs:__imp_LocalFree
0x180069cc7  nop     dword ptr [rax+rax+00h]
0x180069ccc  jmp     loc_180069DC2
0x180069cd1  mov     eax, [rbp+3Fh+arg_20]
0x180069cd4  xorps   xmm0, xmm0
0x180069cd7  mov     [rbp+3Fh+pListOfExplicitEntries.Trustee.ptstrName], rbx
0x180069cdb  mov     rbx, [rbp+3Fh+var_50]
0x180069cdf  mov     [rbp+3Fh+pListOfExplicitEntries.grfAccessPermissions], eax
0x180069ce2  mov     eax, [rbp+3Fh+arg_28]
0x180069ce5  mov     qword ptr [rbp+3Fh+pListOfExplicitEntries.Trustee.TrusteeType], 0
0x180069ced  mov     [rbp+3Fh+pListOfExplicitEntries.grfAccessMode], eax
0x180069cf0  mov     [rbp+3Fh+pListOfExplicitEntries.grfInheritance], 0
0x180069cf7  mov     [rbp+3Fh+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x180069cfe  movdqu  xmmword ptr [rbp+3Fh+pListOfExplicitEntries+0Ch], xmm0
0x180069d03  test    rbx, rbx
0x180069d06  jz      short loc_180069D29
0x180069d08  lea     rcx, [rbp+3Fh+var_38]; this
0x180069d0c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180069d11  mov     rcx, rbx; hMem
0x180069d14  call    cs:__imp_LocalFree
0x180069d1b  nop     dword ptr [rax+rax+00h]
0x180069d20  lea     rcx, [rbp+3Fh+var_38]; this
0x180069d24  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180069d29  mov     r8, [rbp+3Fh+OldAcl]; OldAcl
0x180069d2d  lea     r9, [rbp+3Fh+var_50]; NewAcl
0x180069d31  lea     rdx, [rbp+3Fh+pListOfExplicitEntries]; pListOfExplicitEntries
0x180069d35  mov     [rbp+3Fh+var_50], 0
0x180069d3d  mov     ecx, 1; cCountOfExplicitEntries
0x180069d42  call    cs:__imp_SetEntriesInAclW
0x180069d49  nop     dword ptr [rax+rax+00h]
0x180069d4e  test    eax, eax
0x180069d50  jz      short loc_180069D59
0x180069d52  mov     edx, 5Dh ; ']'
0x180069d57  jmp     short loc_180069D97
0x180069d59  mov     rax, [rbp+3Fh+var_50]
0x180069d5d  xor     r9d, r9d; psidOwner
0x180069d60  mov     [rsp+90h+pSacl], 0; pSacl
0x180069d69  mov     rcx, rdi; pObjectName
0x180069d6c  mov     [rsp+90h+pDacl], rax; pDacl
0x180069d71  mov     [rsp+90h+psidGroup], 0; unsigned int
0x180069d7a  lea     edx, [r9+1]; ObjectType
0x180069d7e  lea     r8d, [r9+4]; SecurityInfo
0x180069d82  call    cs:__imp_SetNamedSecurityInfoW
0x180069d89  nop     dword ptr [rax+rax+00h]
0x180069d8e  test    eax, eax
0x180069d90  jz      short loc_180069DAE
0x180069d92  mov     edx, 67h ; 'g'; void *
0x180069d97  mov     rcx, [rbp+47h]; this
0x180069d9b  lea     r8, aOnecoreAdminAp_29; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180069da2  mov     r9d, eax; char *
0x180069da5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180069daa  mov     ebx, eax
0x180069dac  jmp     short loc_180069DB0
0x180069dae  xor     ebx, ebx
0x180069db0  lea     rcx, [rbp+3Fh+hMem]
0x180069db4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180069db9  lea     rcx, [rbp+3Fh+var_50]
0x180069dbd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180069dc2  lea     r11, [rsp+90h+var_s0]
0x180069dca  mov     eax, ebx
0x180069dcc  mov     rbx, [r11+10h]
0x180069dd0  mov     rdi, [r11+18h]
0x180069dd4  mov     rsp, r11
0x180069dd7  pop     rbp
0x180069dd8  retn
```
