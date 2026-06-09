# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18002b490`
- end: `0x18002b7c8`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `824`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002b0b4`
- `0x18002d36c`
- `0x18002dc84`
- `0x18002e2e0`

## callees

- `0x1800160b0`
- `0x1800277b0`
- `0x18002a140`
- `0x18002a2e0`
- `0x18002b160`
- `0x18002b490`
- `0x18002bbe4`
- `0x18002bec4`
- `0x18002cbe0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002b5d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002b5ec`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002b6cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002b6ea`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002b5d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002b5ec`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002b6cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002b6ea`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002b5b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002b6b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002b5b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002b6b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002b677`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002b748`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002b677`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002b748`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b516`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b516`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b59c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b59c`

## string_xrefs

- `0x18002b5ad`: `CLSID\`
- `0x18002b6a6`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  LSTATUS v17; // ebx
  HKEY hKey[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v20[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+90h] [rbp-70h] BYREF
  DWORD cSubKeys; // [rsp+98h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v24 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v24 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v24);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v24);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v24);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v24);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v21 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v20[1] = 0;
      v20[0] = 0xFFFFFFFF80000000uLL;
      v20[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v20, SubKey);
          v12 = (HKEY)v20[0];
        }
      }
      v14 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, SubKey, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v20, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v20);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18002b490  mov     [rsp-8+arg_10], rbx
0x18002b495  mov     [rsp-8+arg_18], rsi
0x18002b49a  push    rbp
0x18002b49b  push    rdi
0x18002b49c  push    r12
0x18002b49e  push    r14
0x18002b4a0  push    r15
0x18002b4a2  lea     rbp, [rsp-150h]
0x18002b4aa  sub     rsp, 250h
0x18002b4b1  mov     rax, cs:__security_cookie
0x18002b4b8  xor     rax, rsp
0x18002b4bb  mov     [rbp+170h+var_30], rax
0x18002b4c2  xor     r15d, r15d
0x18002b4c5  xorps   xmm0, xmm0
0x18002b4c8  mov     [rbp+170h+var_1D0], r15
0x18002b4cc  mov     r14d, r8d
0x18002b4cf  mov     rbx, rdx
0x18002b4d2  mov     rsi, rcx
0x18002b4d5  movups  [rbp+170h+var_1C8], xmm0
0x18002b4d9  test    rdx, rdx
0x18002b4dc  jz      loc_18002B78F
0x18002b4e2  lea     rdx, GUID_NULL; struct _GUID *
0x18002b4e9  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18002b4ee  test    eax, eax
0x18002b4f0  jnz     loc_18002B78F
0x18002b4f6  lea     rax, [rbp+170h+var_1D0]
0x18002b4fa  xor     edx, edx; pUnkOuter
0x18002b4fc  lea     r12d, [r15+1]
0x18002b500  mov     [rsp+270h+ppv], rax; ppv
0x18002b505  mov     r8d, r12d; dwClsContext
0x18002b508  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18002b50f  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18002b516  call    cs:__imp_CoCreateInstance
0x18002b51c  test    eax, eax
0x18002b51e  js      loc_18002B78F
0x18002b524  cmp     [rbx], r15d
0x18002b527  jz      short loc_18002B585
0x18002b529  mov     rax, [rbx+8]
0x18002b52d  lea     r9, [rbp+170h+var_1C8]
0x18002b531  mov     rcx, [rbp+170h+var_1D0]
0x18002b535  mov     r8d, r12d
0x18002b538  mov     rdx, rsi
0x18002b53b  movups  xmm0, xmmword ptr [rax]
0x18002b53e  movdqu  [rbp+170h+var_1C8], xmm0
0x18002b543  mov     rax, [rcx]
0x18002b546  test    r14d, r14d
0x18002b549  jz      short loc_18002B56B
0x18002b54b  cmp     [rbx], r12d
0x18002b54e  jnz     short loc_18002B556
0x18002b550  mov     rax, [rax+28h]
0x18002b554  jmp     short loc_18002B55A
0x18002b556  mov     rax, [rax+38h]
0x18002b55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b55f  mov     edi, eax
0x18002b561  test    eax, eax
0x18002b563  js      loc_18002B792
0x18002b569  jmp     short loc_18002B57F
0x18002b56b  cmp     [rbx], r12d
0x18002b56e  jnz     short loc_18002B576
0x18002b570  mov     rax, [rax+30h]
0x18002b574  jmp     short loc_18002B57A
0x18002b576  mov     rax, [rax+40h]
0x18002b57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b57f  add     rbx, 10h
0x18002b583  jmp     short loc_18002B524
0x18002b585  test    r14d, r14d
0x18002b588  jnz     loc_18002B78F
0x18002b58e  lea     r8d, [r14+40h]; cchMax
0x18002b592  mov     rcx, rsi; rguid
0x18002b595  lea     rdx, [rbp+170h+sz]; lpsz
0x18002b59c  call    cs:__imp_StringFromGUID2
0x18002b5a2  mov     esi, 80h
0x18002b5a7  mov     [rbp+170h+var_1E0], r15
0x18002b5ab  mov     edx, esi
0x18002b5ad  lea     r8, aClsid; "CLSID\\"
0x18002b5b4  lea     rcx, [rbp+170h+SubKey]
0x18002b5b8  call    cs:__imp__o_wcscpy_s
0x18002b5be  mov     ecx, eax; int
0x18002b5c0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002b5c5  lea     r8, [rbp+170h+sz]
0x18002b5cc  mov     edx, esi
0x18002b5ce  lea     rcx, [rbp+170h+SubKey]
0x18002b5d2  call    cs:__imp__o_wcscat_s
0x18002b5d8  mov     ecx, eax; int
0x18002b5da  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002b5df  lea     r8, aRequiredCatego; "\\Required Categories"
0x18002b5e6  mov     edx, esi
0x18002b5e8  lea     rcx, [rbp+170h+SubKey]
0x18002b5ec  call    cs:__imp__o_wcscat_s
0x18002b5f2  mov     ecx, eax; int
0x18002b5f4  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002b5f9  mov     rdi, 0FFFFFFFF80000000h
0x18002b600  mov     [rbp+170h+var_1F0], r15
0x18002b604  mov     r14d, 20019h
0x18002b60a  mov     [rsp+270h+var_1F8], rdi
0x18002b60f  mov     r9d, r14d; unsigned int
0x18002b612  mov     [rbp+170h+var_1E8], r15
0x18002b616  mov     rdx, rdi; hKey
0x18002b619  mov     [rsp+270h+hKey], r15
0x18002b61e  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18002b622  mov     [rsp+270h+var_208], r15
0x18002b627  lea     rcx, [rsp+270h+hKey]; this
0x18002b62c  mov     [rsp+270h+var_200], r15
0x18002b631  mov     [rbp+170h+cSubKeys], r15d
0x18002b635  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002b63a  test    eax, eax
0x18002b63c  jnz     short loc_18002B6A6
0x18002b63e  mov     rcx, [rsp+270h+hKey]; hKey
0x18002b643  lea     rax, [rbp+170h+cSubKeys]
0x18002b647  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002b64c  xor     r9d, r9d; lpReserved
0x18002b64f  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002b654  xor     r8d, r8d; lpcchClass
0x18002b657  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002b65c  xor     edx, edx; lpClass
0x18002b65e  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002b663  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18002b668  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002b66d  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002b672  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18002b677  call    cs:__imp_RegQueryInfoKeyW
0x18002b67d  lea     rcx, [rsp+270h+hKey]; this
0x18002b682  mov     ebx, eax
0x18002b684  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002b689  test    ebx, ebx
0x18002b68b  jnz     short loc_18002B6A6
0x18002b68d  cmp     [rbp+170h+cSubKeys], r15d
0x18002b691  jnz     short loc_18002B6A6
0x18002b693  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18002b697  lea     rcx, [rsp+270h+var_1F8]; this
0x18002b69c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002b6a1  mov     rdi, [rsp+270h+var_1F8]
0x18002b6a6  lea     r8, aClsid; "CLSID\\"
0x18002b6ad  mov     rdx, rsi
0x18002b6b0  lea     rcx, [rbp+170h+SubKey]
0x18002b6b4  call    cs:__imp__o_wcscpy_s
0x18002b6ba  mov     ecx, eax; int
0x18002b6bc  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002b6c1  lea     r8, [rbp+170h+sz]
0x18002b6c8  mov     rdx, rsi
0x18002b6cb  lea     rcx, [rbp+170h+SubKey]
0x18002b6cf  call    cs:__imp__o_wcscat_s
0x18002b6d5  mov     ecx, eax; int
0x18002b6d7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002b6dc  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18002b6e3  mov     rdx, rsi
0x18002b6e6  lea     rcx, [rbp+170h+SubKey]
0x18002b6ea  call    cs:__imp__o_wcscat_s
0x18002b6f0  mov     ecx, eax; int
0x18002b6f2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002b6f7  mov     r9d, r14d; unsigned int
0x18002b6fa  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18002b6fe  mov     rdx, rdi; hKey
0x18002b701  lea     rcx, [rsp+270h+hKey]; this
0x18002b706  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002b70b  test    eax, eax
0x18002b70d  jnz     short loc_18002B772
0x18002b70f  mov     rcx, [rsp+270h+hKey]; hKey
0x18002b714  lea     rax, [rbp+170h+cSubKeys]
0x18002b718  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002b71d  xor     r9d, r9d; lpReserved
0x18002b720  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002b725  xor     r8d, r8d; lpcchClass
0x18002b728  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002b72d  xor     edx, edx; lpClass
0x18002b72f  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002b734  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18002b739  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002b73e  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002b743  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18002b748  call    cs:__imp_RegQueryInfoKeyW
0x18002b74e  lea     rcx, [rsp+270h+hKey]; this
0x18002b753  mov     ebx, eax
0x18002b755  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002b75a  test    ebx, ebx
0x18002b75c  jnz     short loc_18002B772
0x18002b75e  cmp     [rbp+170h+cSubKeys], r15d
0x18002b762  jnz     short loc_18002B772
0x18002b764  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18002b768  lea     rcx, [rsp+270h+var_1F8]; this
0x18002b76d  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002b772  lea     rcx, [rsp+270h+hKey]; this
0x18002b777  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002b77c  lea     rcx, [rsp+270h+var_1F8]; this
0x18002b781  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002b786  lea     rcx, [rbp+170h+var_1E0]
0x18002b78a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002b78f  mov     edi, r15d
0x18002b792  lea     rcx, [rbp+170h+var_1D0]
0x18002b796  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b79b  mov     eax, edi
0x18002b79d  mov     rcx, [rbp+170h+var_30]
0x18002b7a4  xor     rcx, rsp; StackCookie
0x18002b7a7  call    __security_check_cookie
0x18002b7ac  lea     r11, [rsp+270h+var_20]
0x18002b7b4  mov     rbx, [r11+40h]
0x18002b7b8  mov     rsi, [r11+48h]
0x18002b7bc  mov     rsp, r11
0x18002b7bf  pop     r15
0x18002b7c1  pop     r14
0x18002b7c3  pop     r12
0x18002b7c5  pop     rdi
0x18002b7c6  pop     rbp
0x18002b7c7  retn
```
