# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18001833c`
- end: `0x180018677`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019490`
- `0x180019d44`
- `0x18001a390`

## callees

- `0x180007804`
- `0x18000aef0`
- `0x18000f620`
- `0x18000f678`
- `0x180010e60`
- `0x180016020`
- `0x1800175c0`
- `0x18001833c`
- `0x180018998`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018481`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001849b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001857d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018598`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018481`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001849b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001857d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180018598`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018467`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018562`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018467`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018562`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800183c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800183c4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001844b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001844b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180018526`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800185f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180018526`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800185f7`

## string_xrefs

- `0x18001845c`: `CLSID\`
- `0x180018554`: `CLSID\`

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
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
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
      v23 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
          v12 = (HKEY)v22[0];
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
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
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
0x18001833c  mov     [rsp-8+arg_10], rbx
0x180018341  mov     [rsp-8+arg_18], rsi
0x180018346  push    rbp
0x180018347  push    rdi
0x180018348  push    r12
0x18001834a  push    r14
0x18001834c  push    r15
0x18001834e  lea     rbp, [rsp-150h]
0x180018356  sub     rsp, 250h
0x18001835d  mov     rax, cs:__security_cookie
0x180018364  xor     rax, rsp
0x180018367  mov     [rbp+170h+var_30], rax
0x18001836e  xor     r15d, r15d
0x180018371  xorps   xmm0, xmm0
0x180018374  mov     [rsp+270h+var_208], r15
0x180018379  mov     r14d, r8d
0x18001837c  mov     rbx, rdx
0x18001837f  mov     rsi, rcx
0x180018382  movups  [rbp+170h+var_1C8], xmm0
0x180018386  test    rdx, rdx
0x180018389  jz      loc_18001863D
0x18001838f  lea     rdx, GUID_NULL; struct _GUID *
0x180018396  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001839b  test    eax, eax
0x18001839d  jnz     loc_18001863D
0x1800183a3  lea     rax, [rsp+270h+var_208]
0x1800183a8  xor     edx, edx; pUnkOuter
0x1800183aa  lea     r12d, [r15+1]
0x1800183ae  mov     [rsp+270h+ppv], rax; ppv
0x1800183b3  mov     r8d, r12d; dwClsContext
0x1800183b6  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800183bd  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800183c4  call    cs:__imp_CoCreateInstance
0x1800183ca  test    eax, eax
0x1800183cc  js      loc_18001863D
0x1800183d2  cmp     [rbx], r15d
0x1800183d5  jz      short loc_180018434
0x1800183d7  mov     rax, [rbx+8]
0x1800183db  lea     r9, [rbp+170h+var_1C8]
0x1800183df  mov     rcx, [rsp+270h+var_208]
0x1800183e4  mov     r8d, r12d
0x1800183e7  mov     rdx, rsi
0x1800183ea  movups  xmm0, xmmword ptr [rax]
0x1800183ed  movdqu  [rbp+170h+var_1C8], xmm0
0x1800183f2  mov     rax, [rcx]
0x1800183f5  test    r14d, r14d
0x1800183f8  jz      short loc_18001841A
0x1800183fa  cmp     [rbx], r12d
0x1800183fd  jnz     short loc_180018405
0x1800183ff  mov     rax, [rax+28h]
0x180018403  jmp     short loc_180018409
0x180018405  mov     rax, [rax+38h]
0x180018409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001840e  mov     edi, eax
0x180018410  test    eax, eax
0x180018412  js      loc_180018640
0x180018418  jmp     short loc_18001842E
0x18001841a  cmp     [rbx], r12d
0x18001841d  jnz     short loc_180018425
0x18001841f  mov     rax, [rax+30h]
0x180018423  jmp     short loc_180018429
0x180018425  mov     rax, [rax+40h]
0x180018429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001842e  add     rbx, 10h
0x180018432  jmp     short loc_1800183D2
0x180018434  test    r14d, r14d
0x180018437  jnz     loc_18001863D
0x18001843d  lea     r8d, [r14+40h]; cchMax
0x180018441  mov     rcx, rsi; rguid
0x180018444  lea     rdx, [rbp+170h+sz]; lpsz
0x18001844b  call    cs:__imp_StringFromGUID2
0x180018451  mov     esi, 80h
0x180018456  mov     [rbp+170h+var_1D0], r15
0x18001845a  mov     edx, esi
0x18001845c  lea     r8, aClsid; "CLSID\\"
0x180018463  lea     rcx, [rbp+170h+SubKey]
0x180018467  call    cs:__imp__o_wcscpy_s
0x18001846d  mov     ecx, eax; int
0x18001846f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018474  lea     r8, [rbp+170h+sz]
0x18001847b  mov     edx, esi
0x18001847d  lea     rcx, [rbp+170h+SubKey]
0x180018481  call    cs:__imp__o_wcscat_s
0x180018487  mov     ecx, eax; int
0x180018489  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001848e  lea     r8, aRequiredCatego; "\\Required Categories"
0x180018495  mov     edx, esi
0x180018497  lea     rcx, [rbp+170h+SubKey]
0x18001849b  call    cs:__imp__o_wcscat_s
0x1800184a1  mov     ecx, eax; int
0x1800184a3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800184a8  mov     rdi, 0FFFFFFFF80000000h
0x1800184af  mov     [rbp+170h+var_1E0], r15
0x1800184b3  mov     r14d, 20019h
0x1800184b9  mov     [rbp+170h+var_1E8], rdi
0x1800184bd  mov     r9d, r14d; unsigned int
0x1800184c0  mov     [rbp+170h+var_1D8], r15
0x1800184c4  mov     rdx, rdi; hKey
0x1800184c7  mov     [rsp+270h+hKey], r15
0x1800184cc  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1800184d0  mov     [rsp+270h+var_1F8], r15
0x1800184d5  lea     rcx, [rsp+270h+hKey]; this
0x1800184da  mov     [rbp+170h+var_1F0], r15
0x1800184de  mov     [rsp+270h+cSubKeys], r15d
0x1800184e3  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800184e8  test    eax, eax
0x1800184ea  jnz     short loc_180018554
0x1800184ec  mov     rcx, [rsp+270h+hKey]; hKey
0x1800184f1  lea     rax, [rsp+270h+cSubKeys]
0x1800184f6  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800184fb  xor     r9d, r9d; lpReserved
0x1800184fe  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180018503  xor     r8d, r8d; lpcchClass
0x180018506  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001850b  xor     edx, edx; lpClass
0x18001850d  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180018512  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180018517  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001851c  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180018521  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180018526  call    cs:__imp_RegQueryInfoKeyW
0x18001852c  lea     rcx, [rsp+270h+hKey]; this
0x180018531  mov     ebx, eax
0x180018533  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018538  test    ebx, ebx
0x18001853a  jnz     short loc_180018554
0x18001853c  cmp     [rsp+270h+cSubKeys], r15d
0x180018541  jnz     short loc_180018554
0x180018543  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180018547  lea     rcx, [rbp+170h+var_1E8]; this
0x18001854b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180018550  mov     rdi, [rbp+170h+var_1E8]
0x180018554  lea     r8, aClsid; "CLSID\\"
0x18001855b  mov     rdx, rsi
0x18001855e  lea     rcx, [rbp+170h+SubKey]
0x180018562  call    cs:__imp__o_wcscpy_s
0x180018568  mov     ecx, eax; int
0x18001856a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001856f  lea     r8, [rbp+170h+sz]
0x180018576  mov     rdx, rsi
0x180018579  lea     rcx, [rbp+170h+SubKey]
0x18001857d  call    cs:__imp__o_wcscat_s
0x180018583  mov     ecx, eax; int
0x180018585  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001858a  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180018591  mov     rdx, rsi
0x180018594  lea     rcx, [rbp+170h+SubKey]
0x180018598  call    cs:__imp__o_wcscat_s
0x18001859e  mov     ecx, eax; int
0x1800185a0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800185a5  mov     r9d, r14d; unsigned int
0x1800185a8  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1800185ac  mov     rdx, rdi; hKey
0x1800185af  lea     rcx, [rsp+270h+hKey]; this
0x1800185b4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800185b9  test    eax, eax
0x1800185bb  jnz     short loc_180018621
0x1800185bd  mov     rcx, [rsp+270h+hKey]; hKey
0x1800185c2  lea     rax, [rsp+270h+cSubKeys]
0x1800185c7  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800185cc  xor     r9d, r9d; lpReserved
0x1800185cf  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800185d4  xor     r8d, r8d; lpcchClass
0x1800185d7  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800185dc  xor     edx, edx; lpClass
0x1800185de  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800185e3  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1800185e8  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800185ed  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800185f2  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800185f7  call    cs:__imp_RegQueryInfoKeyW
0x1800185fd  lea     rcx, [rsp+270h+hKey]; this
0x180018602  mov     ebx, eax
0x180018604  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018609  test    ebx, ebx
0x18001860b  jnz     short loc_180018621
0x18001860d  cmp     [rsp+270h+cSubKeys], r15d
0x180018612  jnz     short loc_180018621
0x180018614  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180018618  lea     rcx, [rbp+170h+var_1E8]; this
0x18001861c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180018621  lea     rcx, [rsp+270h+hKey]; this
0x180018626  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001862b  lea     rcx, [rbp+170h+var_1E8]; this
0x18001862f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018634  lea     rcx, [rbp+170h+var_1D0]
0x180018638  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001863d  mov     edi, r15d
0x180018640  lea     rcx, [rsp+270h+var_208]
0x180018645  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001864a  mov     eax, edi
0x18001864c  mov     rcx, [rbp+170h+var_30]
0x180018653  xor     rcx, rsp; StackCookie
0x180018656  call    __security_check_cookie
0x18001865b  lea     r11, [rsp+270h+var_20]
0x180018663  mov     rbx, [r11+40h]
0x180018667  mov     rsi, [r11+48h]
0x18001866b  mov     rsp, r11
0x18001866e  pop     r15
0x180018670  pop     r14
0x180018672  pop     r12
0x180018674  pop     rdi
0x180018675  pop     rbp
0x180018676  retn
```
