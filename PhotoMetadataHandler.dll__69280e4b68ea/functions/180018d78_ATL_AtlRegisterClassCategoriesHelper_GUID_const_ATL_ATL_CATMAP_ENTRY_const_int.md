# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180018d78`
- end: `0x1800190ae`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `822`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a040`
- `0x18001a940`
- `0x18001b000`

## callees

- `0x180008b54`
- `0x18000ab30`
- `0x18000fd88`
- `0x18000fde8`
- `0x180011698`
- `0x180016a40`
- `0x180018078`
- `0x180018d78`
- `0x180019470`
- `0x18001afd0`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018eaf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018fa2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018eaf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018fa2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018e00`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018e00`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018e8d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018e8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180018f60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180019027`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180018f60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180019027`

## string_xrefs

- `0x180018ea4`: `CLSID\`
- `0x180018f94`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r9
  HKEY v14; // rdi
  LSTATUS v15; // ebx
  int v16; // eax
  unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // r9
  LSTATUS v21; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v28 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v28 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v28);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v28);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v28);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v28);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v27 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v10, (unsigned __int64)sz, v11);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v12, (unsigned __int64)L"\\Required Categories", v13);
      v14 = HKEY_CLASSES_ROOT;
      v26[1] = 0;
      v26[0] = 0xFFFFFFFF80000000uLL;
      v26[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v15 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v15 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, SubKey);
          v14 = (HKEY)v26[0];
        }
      }
      v16 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v16);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v17, (unsigned __int64)sz, v18);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v19, (unsigned __int64)L"\\Implemented Categories", v20);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v14, SubKey, 0x20019u) )
      {
        v21 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v21 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v26);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
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
0x180018d78  mov     [rsp-8+arg_10], rbx
0x180018d7d  mov     [rsp-8+arg_18], rsi
0x180018d82  push    rbp
0x180018d83  push    rdi
0x180018d84  push    r12
0x180018d86  push    r14
0x180018d88  push    r15
0x180018d8a  lea     rbp, [rsp-150h]
0x180018d92  sub     rsp, 250h
0x180018d99  mov     rax, cs:__security_cookie
0x180018da0  xor     rax, rsp
0x180018da3  mov     [rbp+170h+var_30], rax
0x180018daa  xor     r15d, r15d
0x180018dad  xorps   xmm0, xmm0
0x180018db0  mov     [rsp+270h+var_208], r15
0x180018db5  mov     r14d, r8d
0x180018db8  mov     rbx, rdx
0x180018dbb  mov     rsi, rcx
0x180018dbe  movups  [rbp+170h+var_1C8], xmm0
0x180018dc2  test    rdx, rdx
0x180018dc5  jz      loc_180019073
0x180018dcb  lea     rdx, GUID_NULL; struct _GUID *
0x180018dd2  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180018dd7  test    eax, eax
0x180018dd9  jnz     loc_180019073
0x180018ddf  lea     rax, [rsp+270h+var_208]
0x180018de4  xor     edx, edx; pUnkOuter
0x180018de6  lea     r12d, [r15+1]
0x180018dea  mov     [rsp+270h+ppv], rax; ppv
0x180018def  mov     r8d, r12d; dwClsContext
0x180018df2  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180018df9  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180018e00  call    cs:__imp_CoCreateInstance
0x180018e07  nop     dword ptr [rax+rax+00h]
0x180018e0c  test    eax, eax
0x180018e0e  js      loc_180019073
0x180018e14  cmp     [rbx], r15d
0x180018e17  jz      short loc_180018E76
0x180018e19  mov     rax, [rbx+8]
0x180018e1d  lea     r9, [rbp+170h+var_1C8]
0x180018e21  mov     rcx, [rsp+270h+var_208]
0x180018e26  mov     r8d, r12d
0x180018e29  mov     rdx, rsi
0x180018e2c  movups  xmm0, xmmword ptr [rax]
0x180018e2f  movdqu  [rbp+170h+var_1C8], xmm0
0x180018e34  mov     rax, [rcx]
0x180018e37  test    r14d, r14d
0x180018e3a  jz      short loc_180018E5C
0x180018e3c  cmp     [rbx], r12d
0x180018e3f  jnz     short loc_180018E47
0x180018e41  mov     rax, [rax+28h]
0x180018e45  jmp     short loc_180018E4B
0x180018e47  mov     rax, [rax+38h]
0x180018e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e50  mov     edi, eax
0x180018e52  test    eax, eax
0x180018e54  js      loc_180019076
0x180018e5a  jmp     short loc_180018E70
0x180018e5c  cmp     [rbx], r12d
0x180018e5f  jnz     short loc_180018E67
0x180018e61  mov     rax, [rax+30h]
0x180018e65  jmp     short loc_180018E6B
0x180018e67  mov     rax, [rax+40h]
0x180018e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e70  add     rbx, 10h
0x180018e74  jmp     short loc_180018E14
0x180018e76  test    r14d, r14d
0x180018e79  jnz     loc_180019073
0x180018e7f  lea     r8d, [r14+40h]; cchMax
0x180018e83  mov     rcx, rsi; rguid
0x180018e86  lea     rdx, [rbp+170h+sz]; lpsz
0x180018e8d  call    cs:__imp_StringFromGUID2
0x180018e94  nop     dword ptr [rax+rax+00h]
0x180018e99  mov     esi, 80h
0x180018e9e  mov     [rbp+170h+var_1D0], r15
0x180018ea2  mov     edx, esi
0x180018ea4  lea     r8, aClsid; "CLSID\\"
0x180018eab  lea     rcx, [rbp+170h+SubKey]
0x180018eaf  call    cs:__imp__o_wcscpy_s
0x180018eb6  nop     dword ptr [rax+rax+00h]
0x180018ebb  mov     ecx, eax; int
0x180018ebd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018ec2  lea     r8, [rbp+170h+sz]; unsigned __int64
0x180018ec9  lea     rcx, [rbp+170h+SubKey]; this
0x180018ecd  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180018ed2  lea     r8, aRequiredCatego; "\\Required Categories"
0x180018ed9  lea     rcx, [rbp+170h+SubKey]; this
0x180018edd  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180018ee2  mov     rdi, 0FFFFFFFF80000000h
0x180018ee9  mov     [rbp+170h+var_1E0], r15
0x180018eed  mov     r14d, 20019h
0x180018ef3  mov     [rbp+170h+var_1E8], rdi
0x180018ef7  mov     r9d, r14d; unsigned int
0x180018efa  mov     [rbp+170h+var_1D8], r15
0x180018efe  mov     rdx, rdi; hKey
0x180018f01  mov     [rsp+270h+hKey], r15
0x180018f06  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180018f0a  mov     [rsp+270h+var_1F8], r15
0x180018f0f  lea     rcx, [rsp+270h+hKey]; this
0x180018f14  mov     [rbp+170h+var_1F0], r15
0x180018f18  mov     [rsp+270h+cSubKeys], r15d
0x180018f1d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180018f22  test    eax, eax
0x180018f24  jnz     short loc_180018F94
0x180018f26  mov     rcx, [rsp+270h+hKey]; hKey
0x180018f2b  lea     rax, [rsp+270h+cSubKeys]
0x180018f30  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180018f35  xor     r9d, r9d; lpReserved
0x180018f38  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180018f3d  xor     r8d, r8d; lpcchClass
0x180018f40  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180018f45  xor     edx, edx; lpClass
0x180018f47  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180018f4c  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180018f51  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180018f56  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180018f5b  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180018f60  call    cs:__imp_RegQueryInfoKeyW
0x180018f67  nop     dword ptr [rax+rax+00h]
0x180018f6c  lea     rcx, [rsp+270h+hKey]; this
0x180018f71  mov     ebx, eax
0x180018f73  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018f78  test    ebx, ebx
0x180018f7a  jnz     short loc_180018F94
0x180018f7c  cmp     [rsp+270h+cSubKeys], r15d
0x180018f81  jnz     short loc_180018F94
0x180018f83  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180018f87  lea     rcx, [rbp+170h+var_1E8]; this
0x180018f8b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180018f90  mov     rdi, [rbp+170h+var_1E8]
0x180018f94  lea     r8, aClsid; "CLSID\\"
0x180018f9b  mov     rdx, rsi
0x180018f9e  lea     rcx, [rbp+170h+SubKey]
0x180018fa2  call    cs:__imp__o_wcscpy_s
0x180018fa9  nop     dword ptr [rax+rax+00h]
0x180018fae  mov     ecx, eax; int
0x180018fb0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018fb5  lea     r8, [rbp+170h+sz]; unsigned __int64
0x180018fbc  lea     rcx, [rbp+170h+SubKey]; this
0x180018fc0  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180018fc5  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180018fcc  lea     rcx, [rbp+170h+SubKey]; this
0x180018fd0  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180018fd5  mov     r9d, r14d; unsigned int
0x180018fd8  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180018fdc  mov     rdx, rdi; hKey
0x180018fdf  lea     rcx, [rsp+270h+hKey]; this
0x180018fe4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180018fe9  test    eax, eax
0x180018feb  jnz     short loc_180019057
0x180018fed  mov     rcx, [rsp+270h+hKey]; hKey
0x180018ff2  lea     rax, [rsp+270h+cSubKeys]
0x180018ff7  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180018ffc  xor     r9d, r9d; lpReserved
0x180018fff  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180019004  xor     r8d, r8d; lpcchClass
0x180019007  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001900c  xor     edx, edx; lpClass
0x18001900e  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180019013  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180019018  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001901d  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180019022  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180019027  call    cs:__imp_RegQueryInfoKeyW
0x18001902e  nop     dword ptr [rax+rax+00h]
0x180019033  lea     rcx, [rsp+270h+hKey]; this
0x180019038  mov     ebx, eax
0x18001903a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001903f  test    ebx, ebx
0x180019041  jnz     short loc_180019057
0x180019043  cmp     [rsp+270h+cSubKeys], r15d
0x180019048  jnz     short loc_180019057
0x18001904a  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18001904e  lea     rcx, [rbp+170h+var_1E8]; this
0x180019052  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180019057  lea     rcx, [rsp+270h+hKey]; this
0x18001905c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019061  lea     rcx, [rbp+170h+var_1E8]; this
0x180019065  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001906a  lea     rcx, [rbp+170h+var_1D0]
0x18001906e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019073  mov     edi, r15d
0x180019076  lea     rcx, [rsp+270h+var_208]
0x18001907b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180019080  mov     eax, edi
0x180019082  mov     rcx, [rbp+170h+var_30]
0x180019089  xor     rcx, rsp; StackCookie
0x18001908c  call    __security_check_cookie
0x180019091  lea     r11, [rsp+270h+var_20]
0x180019099  mov     rbx, [r11+40h]
0x18001909d  mov     rsi, [r11+48h]
0x1800190a1  mov     rsp, r11
0x1800190a4  pop     r15
0x1800190a6  pop     r14
0x1800190a8  pop     r12
0x1800190aa  pop     rdi
0x1800190ab  pop     rbp
0x1800190ac  retn
```
