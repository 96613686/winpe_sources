# WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ABI::Windows::Internal::Storage::PathAccessChecks)

- ea: `0x180015b24`
- end: `0x180015d49`
- name: `?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@QEBA_NAEAVIdentity@Utilities@3@W4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z`
- size: `549`
- prototype: `char __fastcall(WindowsStorage::Utilities *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015d50`

## callees

- `0x180002be0`
- `0x1800038f0`
- `0x180010670`
- `0x180010690`
- `0x1800119d4`
- `0x180011aa4`
- `0x180011f20`
- `0x18001597c`
- `0x180015a74`
- `0x180015ad4`
- `0x180015b24`
- `0x1800160d4`
- `0x180016180`
- `0x1800162c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015c0c`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180015c9f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180015c9f`
- `ext-ms-win-winrt-storage-l1-2-0!PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage` at `0x180015c3e`
- `ext-ms-win-winrt-storage-l1-2-0!PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage` at `0x180015c3e`
- `ext-ms-win-winrt-storage-l1-2-2!StorageItemHelpers_IsSupportedRemovablePath` at `0x180015c79`
- `ext-ms-win-winrt-storage-l1-2-2!StorageItemHelpers_IsSupportedRemovablePath` at `0x180015c79`

## string_xrefs

- `0x180015c52`: `onecore\base\windows.storage\src\pathaccesscheck.cpp`

## pseudocode

```c
char __fastcall WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
        WindowsStorage::Utilities *a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v6; // rdx
  bool *v7; // r9
  __int16 FileAttributesOfClosestExtantAncestor; // ax
  char v9; // bl
  __int64 v10; // rcx
  PCWSTR StringRawBuffer; // r14
  int v12; // eax
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v18[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h]
  _QWORD v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[352]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  start_scoped_activity<TraceProvider::AccessCheckActivity>(v21);
  v19 = 0;
  std::vector<unsigned short>::vector<unsigned short>(v20);
  LOWORD(v15) = 0;
  std::vector<unsigned short>::assign(v20, v6, &v15);
  v19 = v20[0];
  LOBYTE(v15) = 0;
  FileAttributesOfClosestExtantAncestor = WindowsStorage::Utilities::GetFileAttributesOfClosestExtantAncestor(
                                            a1,
                                            (const struct WindowsStorage::Utilities::CanonicalPath *)v18,
                                            (struct WindowsStorage::Utilities::CanonicalPath *)&v15,
                                            v7);
  if ( (_BYTE)v15 )
  {
    if ( (a3 & 2) != 0 && (FileAttributesOfClosestExtantAncestor & 0x400) != 0 )
      goto LABEL_7;
    if ( (FileAttributesOfClosestExtantAncestor & 0x10) != 0 )
      a3 |= 0x10000u;
  }
  if ( (unsigned __int8)WindowsStorage::Win32BrokeredAPIs::FilePathAccess::_DeniedBy_BasicPathChecks(a1, a3) )
  {
LABEL_7:
    v9 = 0;
LABEL_20:
    std::vector<unsigned short>::_Tidy(v20);
    wil::details::lambda_call<_lambda_35144ee3bfa3248f9e2416642c0e640a_>::~lambda_call<_lambda_35144ee3bfa3248f9e2416642c0e640a_>((TraceProvider::AccessCheckActivity *)v21);
    return v9;
  }
  WindowsStorage::Utilities::NtObjectPath::FromFileName(&string, v20[0]);
  if ( (unsigned __int8)WindowsStorage::Win32BrokeredAPIs::FilePathAccess::_AllowedBy_AccessLists(v10, a2, a3, &string) )
    goto LABEL_19;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( (a3 & 0x40) != 0 && (unsigned __int8)IsPathContainedByManifestedKnownFolder_FullTrustCaller_ForPackagePresent() )
  {
    v16 = 0;
    v15 = 0;
    v12 = PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage(
            StringRawBuffer,
            *(_QWORD *)(a2 + 8),
            &v15,
            &v16);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\base\\windows.storage\\src\\pathaccesscheck.cpp",
        (const char *)(unsigned int)v12,
        v15);
    if ( v15 )
      goto LABEL_19;
  }
  v16 = 0;
  if ( (int)StorageItemHelpers_IsSupportedRemovablePath(*((_QWORD *)a1 + 2), &v16) >= 0 && v16 )
  {
    LOBYTE(v15) = 0;
    v13 = CapabilityCheck(*(_QWORD *)(a2 + 8), L"removableStorage", &v15);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecore\\base\\windows.storage\\src\\identity.cpp",
        (const char *)(unsigned int)v13,
        v15);
    if ( (_BYTE)v15 )
    {
LABEL_19:
      WindowsDeleteString(string);
      string = 0;
      v9 = 1;
      goto LABEL_20;
    }
  }
  WindowsDeleteString(string);
  string = 0;
  std::vector<unsigned short>::_Tidy(v20);
  wil::details::lambda_call<_lambda_35144ee3bfa3248f9e2416642c0e640a_>::~lambda_call<_lambda_35144ee3bfa3248f9e2416642c0e640a_>((TraceProvider::AccessCheckActivity *)v21);
  return 0;
}

```

## disassembly

```asm
0x180015b24  mov     [rsp-8+arg_10], rbx
0x180015b29  push    rbp
0x180015b2a  push    rsi
0x180015b2b  push    rdi
0x180015b2c  push    r14
0x180015b2e  push    r15
0x180015b30  lea     rbp, [rsp-0D0h]
0x180015b38  sub     rsp, 1D0h
0x180015b3f  mov     rax, cs:__security_cookie
0x180015b46  xor     rax, rsp
0x180015b49  mov     [rbp+0F0h+var_30], rax
0x180015b50  mov     ebx, r8d
0x180015b53  mov     rdi, rdx
0x180015b56  mov     rsi, rcx
0x180015b59  xor     r15d, r15d
0x180015b5c  lea     rcx, [rsp+1F0h+var_190]
0x180015b61  call    ??$start_scoped_activity@VAccessCheckActivity@TraceProvider@@@@YA?A_PXZ
0x180015b66  nop
0x180015b67  mov     [rsp+1F0h+var_1B8], r15
0x180015b6c  lea     rcx, [rsp+1F0h+var_1B0]
0x180015b71  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::vector<ushort>(void)
0x180015b76  nop
0x180015b77  mov     word ptr [rsp+1F0h+var_1D0], r15w
0x180015b7d  lea     r8, [rsp+1F0h+var_1D0]
0x180015b82  lea     rcx, [rsp+1F0h+var_1B0]
0x180015b87  call    ?assign@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KAEBG@Z; std::vector<ushort>::assign(unsigned __int64,ushort const &)
0x180015b8c  mov     rax, [rsp+1F0h+var_1B0]
0x180015b91  mov     [rsp+1F0h+var_1B8], rax
0x180015b96  mov     byte ptr [rsp+1F0h+var_1D0], r15b
0x180015b9b  lea     r8, [rsp+1F0h+var_1D0]; struct WindowsStorage::Utilities::CanonicalPath *
0x180015ba0  lea     rdx, [rsp+1F0h+var_1C0]; struct WindowsStorage::Utilities::CanonicalPath *
0x180015ba5  mov     rcx, rsi; this
0x180015ba8  call    ?GetFileAttributesOfClosestExtantAncestor@Utilities@WindowsStorage@@YAKAEBVCanonicalPath@12@PEAV312@PEA_N@Z; WindowsStorage::Utilities::GetFileAttributesOfClosestExtantAncestor(WindowsStorage::Utilities::CanonicalPath const &,WindowsStorage::Utilities::CanonicalPath *,bool *)
0x180015bad  cmp     byte ptr [rsp+1F0h+var_1D0], r15b
0x180015bb2  jz      short loc_180015BC7
0x180015bb4  test    bl, 2
0x180015bb7  jz      short loc_180015BBF
0x180015bb9  bt      eax, 0Ah
0x180015bbd  jb      short loc_180015BD5
0x180015bbf  test    al, 10h
0x180015bc1  jz      short loc_180015BC7
0x180015bc3  bts     ebx, 10h
0x180015bc7  mov     edx, ebx
0x180015bc9  mov     rcx, rsi
0x180015bcc  call    ?_DeniedBy_BasicPathChecks@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@AEBA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::_DeniedBy_BasicPathChecks(ABI::Windows::Internal::Storage::PathAccessChecks)
0x180015bd1  test    al, al
0x180015bd3  jz      short loc_180015BDD
0x180015bd5  mov     bl, r15b
0x180015bd8  jmp     loc_180015CE3
0x180015bdd  mov     rdx, [rsp+1F0h+var_1B0]
0x180015be2  lea     rcx, [rsp+1F0h+string]
0x180015be7  call    ?FromFileName@NtObjectPath@Utilities@WindowsStorage@@SA?AV123@PEBG@Z; WindowsStorage::Utilities::NtObjectPath::FromFileName(ushort const *)
0x180015bec  nop
0x180015bed  lea     r9, [rsp+1F0h+string]
0x180015bf2  mov     r8d, ebx
0x180015bf5  mov     rdx, rdi
0x180015bf8  call    ?_AllowedBy_AccessLists@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@AEBA_NAEAVIdentity@Utilities@3@W4PathAccessChecks@Storage@Internal@Windows@ABI@@AEBVNtObjectPath@53@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::_AllowedBy_AccessLists(WindowsStorage::Utilities::Identity &,ABI::Windows::Internal::Storage::PathAccessChecks,WindowsStorage::Utilities::NtObjectPath const &)
0x180015bfd  test    al, al
0x180015bff  jnz     loc_180015CD1
0x180015c05  xor     edx, edx; length
0x180015c07  mov     rcx, [rsp+1F0h+string]; string
0x180015c0c  call    cs:__imp_WindowsGetStringRawBuffer
0x180015c12  mov     r14, rax
0x180015c15  test    bl, 40h
0x180015c18  jz      short loc_180015C6B
0x180015c1a  call    IsPathContainedByManifestedKnownFolder_FullTrustCaller_ForPackagePresent
0x180015c1f  test    al, al
0x180015c21  jz      short loc_180015C6B
0x180015c23  mov     [rsp+1F0h+var_1CC], r15d
0x180015c28  mov     [rsp+1F0h+var_1D0], r15d; int
0x180015c2d  lea     r9, [rsp+1F0h+var_1CC]
0x180015c32  lea     r8, [rsp+1F0h+var_1D0]
0x180015c37  mov     rdx, [rdi+8]
0x180015c3b  mov     rcx, r14
0x180015c3e  call    cs:__imp_PathContainedByManifestedKnownFolder_FullTrustCaller_ForPackage
0x180015c44  mov     rcx, [rbp+0F8h]; this
0x180015c4b  test    eax, eax
0x180015c4d  jns     short loc_180015C64
0x180015c4f  mov     r9d, eax; char *
0x180015c52  lea     r8, aOnecoreBaseWin_8; "onecore\\base\\windows.storage\\src\\pa"...
0x180015c59  mov     edx, 0E5h; void *
0x180015c5e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015c64  cmp     [rsp+1F0h+var_1D0], r15d
0x180015c69  jnz     short loc_180015CD1
0x180015c6b  mov     [rsp+1F0h+var_1CC], r15d
0x180015c70  lea     rdx, [rsp+1F0h+var_1CC]
0x180015c75  mov     rcx, [rsi+10h]
0x180015c79  call    cs:__imp_StorageItemHelpers_IsSupportedRemovablePath
0x180015c7f  test    eax, eax
0x180015c81  js      short loc_180015CFC
0x180015c83  cmp     [rsp+1F0h+var_1CC], r15d
0x180015c88  jz      short loc_180015CFC
0x180015c8a  mov     byte ptr [rsp+1F0h+var_1D0], r15b; int
0x180015c8f  lea     r8, [rsp+1F0h+var_1D0]
0x180015c94  lea     rdx, aRemovablestora; "removableStorage"
0x180015c9b  mov     rcx, [rdi+8]
0x180015c9f  call    cs:__imp_CapabilityCheck
0x180015ca5  mov     rcx, [rbp+0F8h]; this
0x180015cac  test    eax, eax
0x180015cae  jns     short loc_180015CC5
0x180015cb0  mov     r9d, eax; char *
0x180015cb3  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\windows.storage\\src\\id"...
0x180015cba  mov     edx, 0B3h; void *
0x180015cbf  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180015cc5  cmp     byte ptr [rsp+1F0h+var_1D0], r15b
0x180015cca  setnz   al
0x180015ccd  test    al, al
0x180015ccf  jz      short loc_180015CFC
0x180015cd1  mov     rcx, [rsp+1F0h+string]; string
0x180015cd6  call    cs:__imp_WindowsDeleteString
0x180015cdc  mov     [rsp+1F0h+string], r15
0x180015ce1  mov     bl, 1
0x180015ce3  lea     rcx, [rsp+1F0h+var_1B0]
0x180015ce8  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180015ced  nop
0x180015cee  lea     rcx, [rsp+1F0h+var_190]; this
0x180015cf3  call    ??1?$lambda_call@V_lambda_35144ee3bfa3248f9e2416642c0e640a_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_35144ee3bfa3248f9e2416642c0e640a_>::~lambda_call<_lambda_35144ee3bfa3248f9e2416642c0e640a_>(void)
0x180015cf8  mov     al, bl
0x180015cfa  jmp     short loc_180015D23
0x180015cfc  mov     rcx, [rsp+1F0h+string]; string
0x180015d01  call    cs:__imp_WindowsDeleteString
0x180015d07  mov     [rsp+1F0h+string], r15
0x180015d0c  lea     rcx, [rsp+1F0h+var_1B0]
0x180015d11  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180015d16  nop
0x180015d17  lea     rcx, [rsp+1F0h+var_190]; this
0x180015d1c  call    ??1?$lambda_call@V_lambda_35144ee3bfa3248f9e2416642c0e640a_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_35144ee3bfa3248f9e2416642c0e640a_>::~lambda_call<_lambda_35144ee3bfa3248f9e2416642c0e640a_>(void)
0x180015d21  xor     al, al
0x180015d23  mov     rcx, [rbp+0F0h+var_30]
0x180015d2a  xor     rcx, rsp; StackCookie
0x180015d2d  call    __security_check_cookie
0x180015d32  mov     rbx, [rsp+1F0h+arg_10]
0x180015d3a  add     rsp, 1D0h
0x180015d41  pop     r15
0x180015d43  pop     r14
0x180015d45  pop     rdi
0x180015d46  pop     rsi
0x180015d47  pop     rbp
0x180015d48  retn
```
