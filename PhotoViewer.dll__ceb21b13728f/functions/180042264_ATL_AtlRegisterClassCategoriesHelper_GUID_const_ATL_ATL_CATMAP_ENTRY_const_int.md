# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180042264`
- end: `0x18004259f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180043d4c`
- `0x180044924`
- `0x180044ce0`

## callees

- `0x1800046f8`
- `0x18000cb74`
- `0x18000fb90`
- `0x180029e38`
- `0x180035b18`
- `0x180038944`
- `0x18003f800`
- `0x180042264`
- `0x180043014`
- `0x180080010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800423a9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800423c3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800424a5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800424c0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800423a9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800423c3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800424a5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800424c0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004238f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004248a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004238f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004248a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004244e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004251f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004244e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18004251f`
- `ole32!CoCreateInstance` at `0x1800422ec`
- `ole32!CoCreateInstance` at `0x1800422ec`
- `ole32!StringFromGUID2` at `0x180042373`
- `ole32!StringFromGUID2` at `0x180042373`

## string_xrefs

- `0x180042384`: `CLSID\`
- `0x18004247c`: `CLSID\`

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
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180042264  mov     [rsp-8+arg_10], rbx
0x180042269  mov     [rsp-8+arg_18], rsi
0x18004226e  push    rbp
0x18004226f  push    rdi
0x180042270  push    r12
0x180042272  push    r14
0x180042274  push    r15
0x180042276  lea     rbp, [rsp-150h]
0x18004227e  sub     rsp, 250h
0x180042285  mov     rax, cs:__security_cookie
0x18004228c  xor     rax, rsp
0x18004228f  mov     [rbp+170h+var_30], rax
0x180042296  xor     r15d, r15d
0x180042299  xorps   xmm0, xmm0
0x18004229c  mov     [rsp+270h+var_208], r15
0x1800422a1  mov     r14d, r8d
0x1800422a4  mov     rbx, rdx
0x1800422a7  mov     rsi, rcx
0x1800422aa  movups  [rbp+170h+var_1C8], xmm0
0x1800422ae  test    rdx, rdx
0x1800422b1  jz      loc_180042565
0x1800422b7  lea     rdx, GUID_NULL
0x1800422be  call    InlineIsEqualGUID
0x1800422c3  test    eax, eax
0x1800422c5  jnz     loc_180042565
0x1800422cb  lea     rax, [rsp+270h+var_208]
0x1800422d0  xor     edx, edx; pUnkOuter
0x1800422d2  lea     r12d, [r15+1]
0x1800422d6  mov     [rsp+270h+ppv], rax; ppv
0x1800422db  mov     r8d, r12d; dwClsContext
0x1800422de  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800422e5  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800422ec  call    cs:__imp_CoCreateInstance
0x1800422f2  test    eax, eax
0x1800422f4  js      loc_180042565
0x1800422fa  cmp     [rbx], r15d
0x1800422fd  jz      short loc_18004235C
0x1800422ff  mov     rax, [rbx+8]
0x180042303  lea     r9, [rbp+170h+var_1C8]
0x180042307  mov     rcx, [rsp+270h+var_208]
0x18004230c  mov     r8d, r12d
0x18004230f  mov     rdx, rsi
0x180042312  movups  xmm0, xmmword ptr [rax]
0x180042315  movdqu  [rbp+170h+var_1C8], xmm0
0x18004231a  mov     rax, [rcx]
0x18004231d  test    r14d, r14d
0x180042320  jz      short loc_180042342
0x180042322  cmp     [rbx], r12d
0x180042325  jnz     short loc_18004232D
0x180042327  mov     rax, [rax+28h]
0x18004232b  jmp     short loc_180042331
0x18004232d  mov     rax, [rax+38h]
0x180042331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042336  mov     edi, eax
0x180042338  test    eax, eax
0x18004233a  js      loc_180042568
0x180042340  jmp     short loc_180042356
0x180042342  cmp     [rbx], r12d
0x180042345  jnz     short loc_18004234D
0x180042347  mov     rax, [rax+30h]
0x18004234b  jmp     short loc_180042351
0x18004234d  mov     rax, [rax+40h]
0x180042351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042356  add     rbx, 10h
0x18004235a  jmp     short loc_1800422FA
0x18004235c  test    r14d, r14d
0x18004235f  jnz     loc_180042565
0x180042365  lea     r8d, [r14+40h]; cchMax
0x180042369  mov     rcx, rsi; rguid
0x18004236c  lea     rdx, [rbp+170h+sz]; lpsz
0x180042373  call    cs:__imp_StringFromGUID2
0x180042379  mov     esi, 80h
0x18004237e  mov     [rbp+170h+var_1D0], r15
0x180042382  mov     edx, esi
0x180042384  lea     r8, aClsid; "CLSID\\"
0x18004238b  lea     rcx, [rbp+170h+SubKey]
0x18004238f  call    cs:__imp__o_wcscpy_s
0x180042395  mov     ecx, eax; int
0x180042397  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004239c  lea     r8, [rbp+170h+sz]
0x1800423a3  mov     edx, esi
0x1800423a5  lea     rcx, [rbp+170h+SubKey]
0x1800423a9  call    cs:__imp__o_wcscat_s
0x1800423af  mov     ecx, eax; int
0x1800423b1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800423b6  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800423bd  mov     edx, esi
0x1800423bf  lea     rcx, [rbp+170h+SubKey]
0x1800423c3  call    cs:__imp__o_wcscat_s
0x1800423c9  mov     ecx, eax; int
0x1800423cb  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800423d0  mov     rdi, 0FFFFFFFF80000000h
0x1800423d7  mov     [rbp+170h+var_1E0], r15
0x1800423db  mov     r14d, 20019h
0x1800423e1  mov     [rbp+170h+var_1E8], rdi
0x1800423e5  mov     r9d, r14d; unsigned int
0x1800423e8  mov     [rbp+170h+var_1D8], r15
0x1800423ec  mov     rdx, rdi; hKey
0x1800423ef  mov     [rsp+270h+hKey], r15
0x1800423f4  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1800423f8  mov     [rsp+270h+var_1F8], r15
0x1800423fd  lea     rcx, [rsp+270h+hKey]; this
0x180042402  mov     [rbp+170h+var_1F0], r15
0x180042406  mov     [rsp+270h+cSubKeys], r15d
0x18004240b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180042410  test    eax, eax
0x180042412  jnz     short loc_18004247C
0x180042414  mov     rcx, [rsp+270h+hKey]; hKey
0x180042419  lea     rax, [rsp+270h+cSubKeys]
0x18004241e  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180042423  xor     r9d, r9d; lpReserved
0x180042426  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18004242b  xor     r8d, r8d; lpcchClass
0x18004242e  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180042433  xor     edx, edx; lpClass
0x180042435  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18004243a  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18004243f  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180042444  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180042449  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18004244e  call    cs:__imp_RegQueryInfoKeyW
0x180042454  lea     rcx, [rsp+270h+hKey]; this
0x180042459  mov     ebx, eax
0x18004245b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180042460  test    ebx, ebx
0x180042462  jnz     short loc_18004247C
0x180042464  cmp     [rsp+270h+cSubKeys], r15d
0x180042469  jnz     short loc_18004247C
0x18004246b  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18004246f  lea     rcx, [rbp+170h+var_1E8]; this
0x180042473  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180042478  mov     rdi, [rbp+170h+var_1E8]
0x18004247c  lea     r8, aClsid; "CLSID\\"
0x180042483  mov     rdx, rsi
0x180042486  lea     rcx, [rbp+170h+SubKey]
0x18004248a  call    cs:__imp__o_wcscpy_s
0x180042490  mov     ecx, eax; int
0x180042492  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180042497  lea     r8, [rbp+170h+sz]
0x18004249e  mov     rdx, rsi
0x1800424a1  lea     rcx, [rbp+170h+SubKey]
0x1800424a5  call    cs:__imp__o_wcscat_s
0x1800424ab  mov     ecx, eax; int
0x1800424ad  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800424b2  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800424b9  mov     rdx, rsi
0x1800424bc  lea     rcx, [rbp+170h+SubKey]
0x1800424c0  call    cs:__imp__o_wcscat_s
0x1800424c6  mov     ecx, eax; int
0x1800424c8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800424cd  mov     r9d, r14d; unsigned int
0x1800424d0  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x1800424d4  mov     rdx, rdi; hKey
0x1800424d7  lea     rcx, [rsp+270h+hKey]; this
0x1800424dc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800424e1  test    eax, eax
0x1800424e3  jnz     short loc_180042549
0x1800424e5  mov     rcx, [rsp+270h+hKey]; hKey
0x1800424ea  lea     rax, [rsp+270h+cSubKeys]
0x1800424ef  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800424f4  xor     r9d, r9d; lpReserved
0x1800424f7  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800424fc  xor     r8d, r8d; lpcchClass
0x1800424ff  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180042504  xor     edx, edx; lpClass
0x180042506  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18004250b  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180042510  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180042515  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18004251a  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18004251f  call    cs:__imp_RegQueryInfoKeyW
0x180042525  lea     rcx, [rsp+270h+hKey]; this
0x18004252a  mov     ebx, eax
0x18004252c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180042531  test    ebx, ebx
0x180042533  jnz     short loc_180042549
0x180042535  cmp     [rsp+270h+cSubKeys], r15d
0x18004253a  jnz     short loc_180042549
0x18004253c  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x180042540  lea     rcx, [rbp+170h+var_1E8]; this
0x180042544  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180042549  lea     rcx, [rsp+270h+hKey]; this
0x18004254e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180042553  lea     rcx, [rbp+170h+var_1E8]; this
0x180042557  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004255c  lea     rcx, [rbp+170h+var_1D0]
0x180042560  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180042565  mov     edi, r15d
0x180042568  lea     rcx, [rsp+270h+var_208]
0x18004256d  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180042572  mov     eax, edi
0x180042574  mov     rcx, [rbp+170h+var_30]
0x18004257b  xor     rcx, rsp; StackCookie
0x18004257e  call    __security_check_cookie
0x180042583  lea     r11, [rsp+270h+var_20]
0x18004258b  mov     rbx, [r11+40h]
0x18004258f  mov     rsi, [r11+48h]
0x180042593  mov     rsp, r11
0x180042596  pop     r15
0x180042598  pop     r14
0x18004259a  pop     r12
0x18004259c  pop     rdi
0x18004259d  pop     rbp
0x18004259e  retn
```
