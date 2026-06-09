# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18002d198`
- end: `0x18002d4cb`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `819`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002cd84`
- `0x18002f26c`
- `0x18002fbc4`
- `0x180030290`

## callees

- `0x1800161d0`
- `0x1800294b0`
- `0x18002be80`
- `0x18002c02c`
- `0x18002ce30`
- `0x18002d198`
- `0x18002d9b0`
- `0x18002dca8`
- `0x18002ea60`
- `0x180030260`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002d2cc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002d3c0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002d2cc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002d3c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d37d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d444`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d37d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d444`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d21e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d21e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d2aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d2aa`

## string_xrefs

- `0x18002d2c1`: `CLSID\`
- `0x18002d3b2`: `CLSID\`

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
  HKEY hKey[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v24[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h] BYREF
  DWORD cSubKeys; // [rsp+98h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp-60h] BYREF
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
      v25 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v10, (unsigned __int64)sz, v11);
      ATL::Checked::wcscat_s((ATL::Checked *)SubKey, v12, (unsigned __int64)L"\\Required Categories", v13);
      v14 = HKEY_CLASSES_ROOT;
      v24[1] = 0;
      v24[0] = 0xFFFFFFFF80000000uLL;
      v24[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v15 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v15 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, SubKey);
          v14 = (HKEY)v24[0];
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
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v24, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v24);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
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
0x18002d198  mov     [rsp-8+arg_10], rbx
0x18002d19d  mov     [rsp-8+arg_18], rsi
0x18002d1a2  push    rbp
0x18002d1a3  push    rdi
0x18002d1a4  push    r12
0x18002d1a6  push    r14
0x18002d1a8  push    r15
0x18002d1aa  lea     rbp, [rsp-150h]
0x18002d1b2  sub     rsp, 250h
0x18002d1b9  mov     rax, cs:__security_cookie
0x18002d1c0  xor     rax, rsp
0x18002d1c3  mov     [rbp+170h+var_30], rax
0x18002d1ca  xor     r15d, r15d
0x18002d1cd  xorps   xmm0, xmm0
0x18002d1d0  mov     [rbp+170h+var_1D0], r15
0x18002d1d4  mov     r14d, r8d
0x18002d1d7  mov     rbx, rdx
0x18002d1da  mov     rsi, rcx
0x18002d1dd  movups  [rbp+170h+var_1C8], xmm0
0x18002d1e1  test    rdx, rdx
0x18002d1e4  jz      loc_18002D491
0x18002d1ea  lea     rdx, GUID_NULL; struct _GUID *
0x18002d1f1  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18002d1f6  test    eax, eax
0x18002d1f8  jnz     loc_18002D491
0x18002d1fe  lea     rax, [rbp+170h+var_1D0]
0x18002d202  xor     edx, edx; pUnkOuter
0x18002d204  lea     r12d, [r15+1]
0x18002d208  mov     [rsp+270h+ppv], rax; ppv
0x18002d20d  mov     r8d, r12d; dwClsContext
0x18002d210  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18002d217  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18002d21e  call    cs:__imp_CoCreateInstance
0x18002d225  nop     dword ptr [rax+rax+00h]
0x18002d22a  test    eax, eax
0x18002d22c  js      loc_18002D491
0x18002d232  cmp     [rbx], r15d
0x18002d235  jz      short loc_18002D293
0x18002d237  mov     rax, [rbx+8]
0x18002d23b  lea     r9, [rbp+170h+var_1C8]
0x18002d23f  mov     rcx, [rbp+170h+var_1D0]
0x18002d243  mov     r8d, r12d
0x18002d246  mov     rdx, rsi
0x18002d249  movups  xmm0, xmmword ptr [rax]
0x18002d24c  movdqu  [rbp+170h+var_1C8], xmm0
0x18002d251  mov     rax, [rcx]
0x18002d254  test    r14d, r14d
0x18002d257  jz      short loc_18002D279
0x18002d259  cmp     [rbx], r12d
0x18002d25c  jnz     short loc_18002D264
0x18002d25e  mov     rax, [rax+28h]
0x18002d262  jmp     short loc_18002D268
0x18002d264  mov     rax, [rax+38h]
0x18002d268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d26d  mov     edi, eax
0x18002d26f  test    eax, eax
0x18002d271  js      loc_18002D494
0x18002d277  jmp     short loc_18002D28D
0x18002d279  cmp     [rbx], r12d
0x18002d27c  jnz     short loc_18002D284
0x18002d27e  mov     rax, [rax+30h]
0x18002d282  jmp     short loc_18002D288
0x18002d284  mov     rax, [rax+40h]
0x18002d288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d28d  add     rbx, 10h
0x18002d291  jmp     short loc_18002D232
0x18002d293  test    r14d, r14d
0x18002d296  jnz     loc_18002D491
0x18002d29c  lea     r8d, [r14+40h]; cchMax
0x18002d2a0  mov     rcx, rsi; rguid
0x18002d2a3  lea     rdx, [rbp+170h+sz]; lpsz
0x18002d2aa  call    cs:__imp_StringFromGUID2
0x18002d2b1  nop     dword ptr [rax+rax+00h]
0x18002d2b6  mov     esi, 80h
0x18002d2bb  mov     [rbp+170h+var_1E0], r15
0x18002d2bf  mov     edx, esi
0x18002d2c1  lea     r8, aClsid; "CLSID\\"
0x18002d2c8  lea     rcx, [rbp+170h+SubKey]
0x18002d2cc  call    cs:__imp__o_wcscpy_s
0x18002d2d3  nop     dword ptr [rax+rax+00h]
0x18002d2d8  mov     ecx, eax; int
0x18002d2da  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002d2df  lea     r8, [rbp+170h+sz]; unsigned __int64
0x18002d2e6  lea     rcx, [rbp+170h+SubKey]; this
0x18002d2ea  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x18002d2ef  lea     r8, aRequiredCatego; "\\Required Categories"
0x18002d2f6  lea     rcx, [rbp+170h+SubKey]; this
0x18002d2fa  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x18002d2ff  mov     rdi, 0FFFFFFFF80000000h
0x18002d306  mov     [rbp+170h+var_1F0], r15
0x18002d30a  mov     r14d, 20019h
0x18002d310  mov     [rsp+270h+var_1F8], rdi
0x18002d315  mov     r9d, r14d; unsigned int
0x18002d318  mov     [rbp+170h+var_1E8], r15
0x18002d31c  mov     rdx, rdi; hKey
0x18002d31f  mov     [rsp+270h+hKey], r15
0x18002d324  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18002d328  mov     [rsp+270h+var_208], r15
0x18002d32d  lea     rcx, [rsp+270h+hKey]; this
0x18002d332  mov     [rsp+270h+var_200], r15
0x18002d337  mov     [rbp+170h+cSubKeys], r15d
0x18002d33b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d340  test    eax, eax
0x18002d342  jnz     short loc_18002D3B2
0x18002d344  mov     rcx, [rsp+270h+hKey]; hKey
0x18002d349  lea     rax, [rbp+170h+cSubKeys]
0x18002d34d  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002d352  xor     r9d, r9d; lpReserved
0x18002d355  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002d35a  xor     r8d, r8d; lpcchClass
0x18002d35d  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002d362  xor     edx, edx; lpClass
0x18002d364  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002d369  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18002d36e  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002d373  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002d378  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18002d37d  call    cs:__imp_RegQueryInfoKeyW
0x18002d384  nop     dword ptr [rax+rax+00h]
0x18002d389  lea     rcx, [rsp+270h+hKey]; this
0x18002d38e  mov     ebx, eax
0x18002d390  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d395  test    ebx, ebx
0x18002d397  jnz     short loc_18002D3B2
0x18002d399  cmp     [rbp+170h+cSubKeys], r15d
0x18002d39d  jnz     short loc_18002D3B2
0x18002d39f  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18002d3a3  lea     rcx, [rsp+270h+var_1F8]; this
0x18002d3a8  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002d3ad  mov     rdi, [rsp+270h+var_1F8]
0x18002d3b2  lea     r8, aClsid; "CLSID\\"
0x18002d3b9  mov     rdx, rsi
0x18002d3bc  lea     rcx, [rbp+170h+SubKey]
0x18002d3c0  call    cs:__imp__o_wcscpy_s
0x18002d3c7  nop     dword ptr [rax+rax+00h]
0x18002d3cc  mov     ecx, eax; int
0x18002d3ce  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002d3d3  lea     r8, [rbp+170h+sz]; unsigned __int64
0x18002d3da  lea     rcx, [rbp+170h+SubKey]; this
0x18002d3de  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x18002d3e3  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18002d3ea  lea     rcx, [rbp+170h+SubKey]; this
0x18002d3ee  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x18002d3f3  mov     r9d, r14d; unsigned int
0x18002d3f6  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18002d3fa  mov     rdx, rdi; hKey
0x18002d3fd  lea     rcx, [rsp+270h+hKey]; this
0x18002d402  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d407  test    eax, eax
0x18002d409  jnz     short loc_18002D474
0x18002d40b  mov     rcx, [rsp+270h+hKey]; hKey
0x18002d410  lea     rax, [rbp+170h+cSubKeys]
0x18002d414  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002d419  xor     r9d, r9d; lpReserved
0x18002d41c  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002d421  xor     r8d, r8d; lpcchClass
0x18002d424  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002d429  xor     edx, edx; lpClass
0x18002d42b  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002d430  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18002d435  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002d43a  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002d43f  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18002d444  call    cs:__imp_RegQueryInfoKeyW
0x18002d44b  nop     dword ptr [rax+rax+00h]
0x18002d450  lea     rcx, [rsp+270h+hKey]; this
0x18002d455  mov     ebx, eax
0x18002d457  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d45c  test    ebx, ebx
0x18002d45e  jnz     short loc_18002D474
0x18002d460  cmp     [rbp+170h+cSubKeys], r15d
0x18002d464  jnz     short loc_18002D474
0x18002d466  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18002d46a  lea     rcx, [rsp+270h+var_1F8]; this
0x18002d46f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002d474  lea     rcx, [rsp+270h+hKey]; this
0x18002d479  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d47e  lea     rcx, [rsp+270h+var_1F8]; this
0x18002d483  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d488  lea     rcx, [rbp+170h+var_1E0]
0x18002d48c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002d491  mov     edi, r15d
0x18002d494  lea     rcx, [rbp+170h+var_1D0]
0x18002d498  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d49d  mov     eax, edi
0x18002d49f  mov     rcx, [rbp+170h+var_30]
0x18002d4a6  xor     rcx, rsp; StackCookie
0x18002d4a9  call    __security_check_cookie
0x18002d4ae  lea     r11, [rsp+270h+var_20]
0x18002d4b6  mov     rbx, [r11+40h]
0x18002d4ba  mov     rsi, [r11+48h]
0x18002d4be  mov     rsp, r11
0x18002d4c1  pop     r15
0x18002d4c3  pop     r14
0x18002d4c5  pop     r12
0x18002d4c7  pop     rdi
0x18002d4c8  pop     rbp
0x18002d4c9  retn
```
