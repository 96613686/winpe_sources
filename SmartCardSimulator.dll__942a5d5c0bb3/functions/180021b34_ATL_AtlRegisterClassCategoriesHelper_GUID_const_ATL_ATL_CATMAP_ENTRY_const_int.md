# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180021b34`
- end: `0x180021e63`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `815`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022ad8`
- `0x180023204`

## callees

- `0x18001ebe8`
- `0x18001ecb8`
- `0x18002184c`
- `0x180021b34`
- `0x1800220d4`
- `0x18002246c`
- `0x1800228ec`
- `0x1800229c0`
- `0x180058700`
- `0x18005e010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180021c79`
- `msvcrt!wcscat_s` at `0x180021c93`
- `msvcrt!wcscat_s` at `0x180021d6c`
- `msvcrt!wcscat_s` at `0x180021d87`
- `msvcrt!wcscat_s` at `0x180021c79`
- `msvcrt!wcscat_s` at `0x180021c93`
- `msvcrt!wcscat_s` at `0x180021d6c`
- `msvcrt!wcscat_s` at `0x180021d87`
- `msvcrt!wcscpy_s` at `0x180021c5f`
- `msvcrt!wcscpy_s` at `0x180021d51`
- `msvcrt!wcscpy_s` at `0x180021c5f`
- `msvcrt!wcscpy_s` at `0x180021d51`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180021c43`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180021c43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021bbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021bbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021d15`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021de3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021d15`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021de3`

## string_xrefs

- `0x180021c54`: `CLSID\`
- `0x180021d43`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  errno_t v9; // eax
  errno_t v10; // eax
  errno_t v11; // eax
  HKEY v12; // rdi
  unsigned int v13; // r9d
  LSTATUS v14; // ebx
  errno_t v15; // eax
  errno_t v16; // eax
  errno_t v17; // eax
  unsigned int v18; // r9d
  LSTATUS v19; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v24[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v26 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v26 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v26);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v26);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v26);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v26);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v25 = 0;
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v24[1] = 0;
      v24[0] = 0xFFFFFFFF80000000uLL;
      v24[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, v13) )
      {
        v14 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v14 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, Destination);
          v12 = (HKEY)v24[0];
        }
      }
      v15 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v15);
      v16 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v16);
      v17 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v17);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, Destination, v18) )
      {
        v19 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v19 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v24);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<ITypeLib>::~CComPtrBase<ITypeLib>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180021b34  mov     [rsp-8+arg_10], rbx
0x180021b39  mov     [rsp-8+arg_18], rsi
0x180021b3e  push    rbp
0x180021b3f  push    rdi
0x180021b40  push    r12
0x180021b42  push    r14
0x180021b44  push    r15
0x180021b46  lea     rbp, [rsp-150h]
0x180021b4e  sub     rsp, 250h
0x180021b55  mov     rax, cs:__security_cookie
0x180021b5c  xor     rax, rsp
0x180021b5f  mov     [rbp+170h+var_30], rax
0x180021b66  xor     r15d, r15d
0x180021b69  xorps   xmm0, xmm0
0x180021b6c  mov     [rsp+270h+var_208], r15
0x180021b71  mov     r14d, r8d
0x180021b74  mov     rbx, rdx
0x180021b77  mov     rsi, rcx
0x180021b7a  movups  [rbp+170h+var_1C8], xmm0
0x180021b7e  test    rdx, rdx
0x180021b81  jz      loc_180021E29
0x180021b87  lea     rdx, GUID_NULL; struct _GUID *
0x180021b8e  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180021b93  test    eax, eax
0x180021b95  jnz     loc_180021E29
0x180021b9b  lea     rax, [rsp+270h+var_208]
0x180021ba0  xor     edx, edx; pUnkOuter
0x180021ba2  lea     r12d, [r15+1]
0x180021ba6  mov     [rsp+270h+ppv], rax; ppv
0x180021bab  mov     r8d, r12d; dwClsContext
0x180021bae  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180021bb5  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180021bbc  call    cs:__imp_CoCreateInstance
0x180021bc2  test    eax, eax
0x180021bc4  js      loc_180021E29
0x180021bca  cmp     [rbx], r15d
0x180021bcd  jz      short loc_180021C2C
0x180021bcf  mov     rax, [rbx+8]
0x180021bd3  lea     r9, [rbp+170h+var_1C8]
0x180021bd7  mov     rcx, [rsp+270h+var_208]
0x180021bdc  mov     r8d, r12d
0x180021bdf  mov     rdx, rsi
0x180021be2  movups  xmm0, xmmword ptr [rax]
0x180021be5  movdqu  [rbp+170h+var_1C8], xmm0
0x180021bea  mov     rax, [rcx]
0x180021bed  test    r14d, r14d
0x180021bf0  jz      short loc_180021C12
0x180021bf2  cmp     [rbx], r12d
0x180021bf5  jnz     short loc_180021BFD
0x180021bf7  mov     rax, [rax+28h]
0x180021bfb  jmp     short loc_180021C01
0x180021bfd  mov     rax, [rax+38h]
0x180021c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c06  mov     edi, eax
0x180021c08  test    eax, eax
0x180021c0a  js      loc_180021E2C
0x180021c10  jmp     short loc_180021C26
0x180021c12  cmp     [rbx], r12d
0x180021c15  jnz     short loc_180021C1D
0x180021c17  mov     rax, [rax+30h]
0x180021c1b  jmp     short loc_180021C21
0x180021c1d  mov     rax, [rax+40h]
0x180021c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c26  add     rbx, 10h
0x180021c2a  jmp     short loc_180021BCA
0x180021c2c  test    r14d, r14d
0x180021c2f  jnz     loc_180021E29
0x180021c35  lea     r8d, [r14+40h]; cchMax
0x180021c39  mov     rcx, rsi; rguid
0x180021c3c  lea     rdx, [rbp+170h+sz]; lpsz
0x180021c43  call    cs:__imp_StringFromGUID2
0x180021c49  mov     esi, 80h
0x180021c4e  mov     [rbp+170h+var_1D0], r15
0x180021c52  mov     edx, esi; SizeInWords
0x180021c54  lea     r8, aClsid; "CLSID\\"
0x180021c5b  lea     rcx, [rbp+170h+Destination]; Destination
0x180021c5f  call    cs:__imp_wcscpy_s
0x180021c65  mov     ecx, eax; int
0x180021c67  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180021c6c  lea     r8, [rbp+170h+sz]; Source
0x180021c73  mov     edx, esi; SizeInWords
0x180021c75  lea     rcx, [rbp+170h+Destination]; Destination
0x180021c79  call    cs:__imp_wcscat_s
0x180021c7f  mov     ecx, eax; int
0x180021c81  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180021c86  lea     r8, aRequiredCatego; "\\Required Categories"
0x180021c8d  mov     edx, esi; SizeInWords
0x180021c8f  lea     rcx, [rbp+170h+Destination]; Destination
0x180021c93  call    cs:__imp_wcscat_s
0x180021c99  mov     ecx, eax; int
0x180021c9b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180021ca0  mov     rdi, 0FFFFFFFF80000000h
0x180021ca7  mov     [rbp+170h+var_1E0], r15
0x180021cab  mov     rdx, rdi; hKey
0x180021cae  mov     [rbp+170h+var_1E8], rdi
0x180021cb2  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180021cb6  mov     [rbp+170h+var_1D8], r15
0x180021cba  lea     rcx, [rsp+270h+hKey]; this
0x180021cbf  mov     [rsp+270h+hKey], r15
0x180021cc4  mov     [rsp+270h+var_1F8], r15
0x180021cc9  mov     [rbp+170h+var_1F0], r15
0x180021ccd  mov     [rsp+270h+cSubKeys], r15d
0x180021cd2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180021cd7  test    eax, eax
0x180021cd9  jnz     short loc_180021D43
0x180021cdb  mov     rcx, [rsp+270h+hKey]; hKey
0x180021ce0  lea     rax, [rsp+270h+cSubKeys]
0x180021ce5  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180021cea  xor     r9d, r9d; lpReserved
0x180021ced  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180021cf2  xor     r8d, r8d; lpcchClass
0x180021cf5  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180021cfa  xor     edx, edx; lpClass
0x180021cfc  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180021d01  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180021d06  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180021d0b  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180021d10  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180021d15  call    cs:__imp_RegQueryInfoKeyW
0x180021d1b  lea     rcx, [rsp+270h+hKey]; this
0x180021d20  mov     ebx, eax
0x180021d22  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021d27  test    ebx, ebx
0x180021d29  jnz     short loc_180021D43
0x180021d2b  cmp     [rsp+270h+cSubKeys], r15d
0x180021d30  jnz     short loc_180021D43
0x180021d32  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180021d36  lea     rcx, [rbp+170h+var_1E8]; this
0x180021d3a  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180021d3f  mov     rdi, [rbp+170h+var_1E8]
0x180021d43  lea     r8, aClsid; "CLSID\\"
0x180021d4a  mov     rdx, rsi; SizeInWords
0x180021d4d  lea     rcx, [rbp+170h+Destination]; Destination
0x180021d51  call    cs:__imp_wcscpy_s
0x180021d57  mov     ecx, eax; int
0x180021d59  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180021d5e  lea     r8, [rbp+170h+sz]; Source
0x180021d65  mov     rdx, rsi; SizeInWords
0x180021d68  lea     rcx, [rbp+170h+Destination]; Destination
0x180021d6c  call    cs:__imp_wcscat_s
0x180021d72  mov     ecx, eax; int
0x180021d74  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180021d79  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180021d80  mov     rdx, rsi; SizeInWords
0x180021d83  lea     rcx, [rbp+170h+Destination]; Destination
0x180021d87  call    cs:__imp_wcscat_s
0x180021d8d  mov     ecx, eax; int
0x180021d8f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180021d94  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180021d98  mov     rdx, rdi; hKey
0x180021d9b  lea     rcx, [rsp+270h+hKey]; this
0x180021da0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180021da5  test    eax, eax
0x180021da7  jnz     short loc_180021E0D
0x180021da9  mov     rcx, [rsp+270h+hKey]; hKey
0x180021dae  lea     rax, [rsp+270h+cSubKeys]
0x180021db3  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180021db8  xor     r9d, r9d; lpReserved
0x180021dbb  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180021dc0  xor     r8d, r8d; lpcchClass
0x180021dc3  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180021dc8  xor     edx, edx; lpClass
0x180021dca  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180021dcf  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180021dd4  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180021dd9  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180021dde  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180021de3  call    cs:__imp_RegQueryInfoKeyW
0x180021de9  lea     rcx, [rsp+270h+hKey]; this
0x180021dee  mov     ebx, eax
0x180021df0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021df5  test    ebx, ebx
0x180021df7  jnz     short loc_180021E0D
0x180021df9  cmp     [rsp+270h+cSubKeys], r15d
0x180021dfe  jnz     short loc_180021E0D
0x180021e00  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180021e04  lea     rcx, [rbp+170h+var_1E8]; this
0x180021e08  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180021e0d  lea     rcx, [rsp+270h+hKey]; this
0x180021e12  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021e17  lea     rcx, [rbp+170h+var_1E8]; this
0x180021e1b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021e20  lea     rcx, [rbp+170h+var_1D0]
0x180021e24  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180021e29  mov     edi, r15d
0x180021e2c  lea     rcx, [rsp+270h+var_208]
0x180021e31  call    ??1?$CComPtrBase@UITypeLib@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITypeLib>::~CComPtrBase<ITypeLib>(void)
0x180021e36  mov     eax, edi
0x180021e38  mov     rcx, [rbp+170h+var_30]
0x180021e3f  xor     rcx, rsp; StackCookie
0x180021e42  call    __security_check_cookie
0x180021e47  lea     r11, [rsp+270h+var_20]
0x180021e4f  mov     rbx, [r11+40h]
0x180021e53  mov     rsi, [r11+48h]
0x180021e57  mov     rsp, r11
0x180021e5a  pop     r15
0x180021e5c  pop     r14
0x180021e5e  pop     r12
0x180021e60  pop     rdi
0x180021e61  pop     rbp
0x180021e62  retn
```
