# Csl::UpdateObjectAcl(Csl::Path const &,Csl::SecurityObjectType,void *,ulong,_ACCESS_MODE)

- ea: `0x18002f2c8`
- end: `0x18002f495`
- name: `?UpdateObjectAcl@Csl@@YAJAEBVPath@1@W4SecurityObjectType@1@PEAXKW4_ACCESS_MODE@@@Z`
- size: `461`
- prototype: `int __high(const struct Path *, enum Csl::SecurityObjectType, void *, unsigned int, enum _ACCESS_MODE)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002ed40`

## callees

- `0x18000dad8`
- `0x18002f2c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f371`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f371`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f359`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f409`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f359`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f409`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f478`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002f443`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002f443`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002f326`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002f326`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002f3d2`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002f3d2`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18002f3ad`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18002f3ad`

## string_xrefs

- `0x18002f33a`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002f3eb`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Csl::UpdateObjectAcl(LPCWSTR *a1, __int64 a2, void *a3, DWORD a4)
{
  DWORD NamedSecurityInfoW; // eax
  unsigned int v8; // ebx
  DWORD v10; // ebx
  DWORD FileAttributesW; // eax
  DWORD v12; // eax
  __int64 v13; // rdx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-41h]
  PACL NewAcl; // [rsp+40h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+48h] [rbp-19h] BYREF
  PACL OldAcl; // [rsp+50h] [rbp-11h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+58h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  OldAcl = 0;
  hMem = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(*a1, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  if ( NamedSecurityInfoW )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x210,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
           (const char *)NamedSecurityInfoW,
           ppsidGroup);
LABEL_3:
    if ( hMem )
      LocalFree(hMem);
    return v8;
  }
  v10 = 0;
  FileAttributesW = GetFileAttributesW(*a1);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
    v10 = 3;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 36);
  pListOfExplicitEntries.grfAccessPermissions = a4;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = v10;
  BuildTrusteeWithSidW(&pListOfExplicitEntries.Trustee, a3);
  NewAcl = 0;
  v12 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
  if ( v12 )
  {
    v13 = 548;
    goto LABEL_11;
  }
  v12 = SetNamedSecurityInfoW((LPWSTR)*a1, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
  if ( v12 )
  {
    v13 = 557;
LABEL_11:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v13,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
           (const char *)v12,
           ppsidGroup);
    if ( NewAcl )
      LocalFree(NewAcl);
    goto LABEL_3;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x18002f2c8  push    rbp
0x18002f2ca  push    rbx
0x18002f2cb  push    rsi
0x18002f2cc  push    rdi
0x18002f2cd  push    r14
0x18002f2cf  lea     rbp, [rsp-2Fh]
0x18002f2d4  sub     rsp, 90h
0x18002f2db  mov     esi, r9d
0x18002f2de  mov     [rbp+4Fh+OldAcl], 0
0x18002f2e6  xor     r9d, r9d; ppsidOwner
0x18002f2e9  mov     [rbp+4Fh+hMem], 0
0x18002f2f1  lea     rax, [rbp+4Fh+hMem]
0x18002f2f5  mov     r14, r8
0x18002f2f8  mov     [rsp+0B0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002f2fd  mov     rdi, rcx
0x18002f300  mov     rcx, [rcx]; pObjectName
0x18002f303  lea     rax, [rbp+4Fh+OldAcl]
0x18002f307  mov     [rsp+0B0h+ppSacl], 0; ppSacl
0x18002f310  lea     edx, [r9+1]; ObjectType
0x18002f314  mov     [rsp+0B0h+ppDacl], rax; ppDacl
0x18002f319  lea     r8d, [r9+4]; SecurityInfo
0x18002f31d  mov     [rsp+0B0h+ppsidGroup], 0; unsigned int
0x18002f326  call    cs:__imp_GetNamedSecurityInfoW
0x18002f32d  nop     dword ptr [rax+rax+00h]
0x18002f332  test    eax, eax
0x18002f334  jz      short loc_18002F36C
0x18002f336  mov     rcx, [rbp+57h]; this
0x18002f33a  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002f341  mov     r9d, eax; char *
0x18002f344  mov     edx, 210h; void *
0x18002f349  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f34e  mov     ebx, eax
0x18002f350  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18002f354  test    rcx, rcx
0x18002f357  jz      short loc_18002F365
0x18002f359  call    cs:__imp_LocalFree
0x18002f360  nop     dword ptr [rax+rax+00h]
0x18002f365  mov     eax, ebx
0x18002f367  jmp     loc_18002F486
0x18002f36c  mov     rcx, [rdi]; lpFileName
0x18002f36f  xor     ebx, ebx
0x18002f371  call    cs:__imp_GetFileAttributesW
0x18002f378  nop     dword ptr [rax+rax+00h]
0x18002f37d  cmp     eax, 0FFFFFFFFh
0x18002f380  jz      short loc_18002F38A
0x18002f382  test    al, 10h
0x18002f384  lea     eax, [rbx+3]
0x18002f387  cmovnz  ebx, eax
0x18002f38a  xorps   xmm0, xmm0
0x18002f38d  lea     rcx, [rbp+4Fh+pListOfExplicitEntries.Trustee]; pTrustee
0x18002f391  movups  xmmword ptr [rbp+4Fh+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18002f395  mov     rdx, r14; pSid
0x18002f398  mov     [rbp+4Fh+pListOfExplicitEntries.grfAccessPermissions], esi
0x18002f39b  mov     [rbp+4Fh+pListOfExplicitEntries.grfAccessMode], 1
0x18002f3a2  mov     [rbp+4Fh+pListOfExplicitEntries.grfInheritance], ebx
0x18002f3a5  movups  xmmword ptr [rbp+4Fh+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18002f3a9  movups  xmmword ptr [rbp+4Fh+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18002f3ad  call    cs:__imp_BuildTrusteeWithSidW
0x18002f3b4  nop     dword ptr [rax+rax+00h]
0x18002f3b9  mov     r8, [rbp+4Fh+OldAcl]; OldAcl
0x18002f3bd  lea     r9, [rbp+4Fh+NewAcl]; NewAcl
0x18002f3c1  lea     rdx, [rbp+4Fh+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002f3c5  mov     [rbp+4Fh+NewAcl], 0
0x18002f3cd  mov     ecx, 1; cCountOfExplicitEntries
0x18002f3d2  call    cs:__imp_SetEntriesInAclW
0x18002f3d9  nop     dword ptr [rax+rax+00h]
0x18002f3de  test    eax, eax
0x18002f3e0  jz      short loc_18002F41A
0x18002f3e2  mov     edx, 224h; void *
0x18002f3e7  mov     rcx, [rbp+57h]; this
0x18002f3eb  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002f3f2  mov     r9d, eax; char *
0x18002f3f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f3fa  mov     rcx, [rbp+4Fh+NewAcl]; hMem
0x18002f3fe  mov     ebx, eax
0x18002f400  test    rcx, rcx
0x18002f403  jz      loc_18002F350
0x18002f409  call    cs:__imp_LocalFree
0x18002f410  nop     dword ptr [rax+rax+00h]
0x18002f415  jmp     loc_18002F350
0x18002f41a  mov     rax, [rbp+4Fh+NewAcl]
0x18002f41e  xor     r9d, r9d; psidOwner
0x18002f421  mov     rcx, [rdi]; pObjectName
0x18002f424  mov     [rsp+0B0h+ppSacl], 0; pSacl
0x18002f42d  mov     [rsp+0B0h+ppDacl], rax; pDacl
0x18002f432  lea     edx, [r9+1]; ObjectType
0x18002f436  mov     [rsp+0B0h+ppsidGroup], 0; psidGroup
0x18002f43f  lea     r8d, [r9+4]; SecurityInfo
0x18002f443  call    cs:__imp_SetNamedSecurityInfoW
0x18002f44a  nop     dword ptr [rax+rax+00h]
0x18002f44f  test    eax, eax
0x18002f451  jz      short loc_18002F45A
0x18002f453  mov     edx, 22Dh
0x18002f458  jmp     short loc_18002F3E7
0x18002f45a  mov     rcx, [rbp+4Fh+NewAcl]; hMem
0x18002f45e  test    rcx, rcx
0x18002f461  jz      short loc_18002F46F
0x18002f463  call    cs:__imp_LocalFree
0x18002f46a  nop     dword ptr [rax+rax+00h]
0x18002f46f  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18002f473  test    rcx, rcx
0x18002f476  jz      short loc_18002F484
0x18002f478  call    cs:__imp_LocalFree
0x18002f47f  nop     dword ptr [rax+rax+00h]
0x18002f484  xor     eax, eax
0x18002f486  add     rsp, 90h
0x18002f48d  pop     r14
0x18002f48f  pop     rdi
0x18002f490  pop     rsi
0x18002f491  pop     rbx
0x18002f492  pop     rbp
0x18002f493  retn
```
