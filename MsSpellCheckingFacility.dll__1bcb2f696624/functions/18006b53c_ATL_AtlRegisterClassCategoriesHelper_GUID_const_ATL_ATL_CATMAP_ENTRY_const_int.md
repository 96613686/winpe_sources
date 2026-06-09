# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18006b53c`
- end: `0x18006b877`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006bb20`
- `0x18006c3b0`

## callees

- `0x180037328`
- `0x180040cc4`
- `0x18005d14c`
- `0x180061320`
- `0x18006afd4`
- `0x18006b53c`
- `0x18006b8d4`
- `0x18006ba64`
- `0x18006c190`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006b681`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006b69b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006b77d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006b798`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006b681`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006b69b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006b77d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006b798`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006b667`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006b762`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006b667`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006b762`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b5c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b5c4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006b64b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006b64b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006b726`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006b7f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006b726`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006b7f7`

## string_xrefs

- `0x18006b65c`: `CLSID\`
- `0x18006b754`: `CLSID\`

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
0x18006b53c  mov     [rsp-8+arg_10], rbx
0x18006b541  mov     [rsp-8+arg_18], rsi
0x18006b546  push    rbp
0x18006b547  push    rdi
0x18006b548  push    r12
0x18006b54a  push    r14
0x18006b54c  push    r15
0x18006b54e  lea     rbp, [rsp-150h]
0x18006b556  sub     rsp, 250h
0x18006b55d  mov     rax, cs:__security_cookie
0x18006b564  xor     rax, rsp
0x18006b567  mov     [rbp+170h+var_30], rax
0x18006b56e  xor     r15d, r15d
0x18006b571  xorps   xmm0, xmm0
0x18006b574  mov     [rsp+270h+var_208], r15
0x18006b579  mov     r14d, r8d
0x18006b57c  mov     rbx, rdx
0x18006b57f  mov     rsi, rcx
0x18006b582  movups  [rbp+170h+var_1C8], xmm0
0x18006b586  test    rdx, rdx
0x18006b589  jz      loc_18006B83D
0x18006b58f  lea     rdx, GUID_NULL; struct _GUID *
0x18006b596  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18006b59b  test    eax, eax
0x18006b59d  jnz     loc_18006B83D
0x18006b5a3  lea     rax, [rsp+270h+var_208]
0x18006b5a8  xor     edx, edx; pUnkOuter
0x18006b5aa  lea     r12d, [r15+1]
0x18006b5ae  mov     [rsp+270h+ppv], rax; ppv
0x18006b5b3  mov     r8d, r12d; dwClsContext
0x18006b5b6  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18006b5bd  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18006b5c4  call    cs:__imp_CoCreateInstance
0x18006b5ca  test    eax, eax
0x18006b5cc  js      loc_18006B83D
0x18006b5d2  cmp     [rbx], r15d
0x18006b5d5  jz      short loc_18006B634
0x18006b5d7  mov     rax, [rbx+8]
0x18006b5db  lea     r9, [rbp+170h+var_1C8]
0x18006b5df  mov     rcx, [rsp+270h+var_208]
0x18006b5e4  mov     r8d, r12d
0x18006b5e7  mov     rdx, rsi
0x18006b5ea  movups  xmm0, xmmword ptr [rax]
0x18006b5ed  movdqu  [rbp+170h+var_1C8], xmm0
0x18006b5f2  mov     rax, [rcx]
0x18006b5f5  test    r14d, r14d
0x18006b5f8  jz      short loc_18006B61A
0x18006b5fa  cmp     [rbx], r12d
0x18006b5fd  jnz     short loc_18006B605
0x18006b5ff  mov     rax, [rax+28h]
0x18006b603  jmp     short loc_18006B609
0x18006b605  mov     rax, [rax+38h]
0x18006b609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b60e  mov     edi, eax
0x18006b610  test    eax, eax
0x18006b612  js      loc_18006B840
0x18006b618  jmp     short loc_18006B62E
0x18006b61a  cmp     [rbx], r12d
0x18006b61d  jnz     short loc_18006B625
0x18006b61f  mov     rax, [rax+30h]
0x18006b623  jmp     short loc_18006B629
0x18006b625  mov     rax, [rax+40h]
0x18006b629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b62e  add     rbx, 10h
0x18006b632  jmp     short loc_18006B5D2
0x18006b634  test    r14d, r14d
0x18006b637  jnz     loc_18006B83D
0x18006b63d  lea     r8d, [r14+40h]; cchMax
0x18006b641  mov     rcx, rsi; rguid
0x18006b644  lea     rdx, [rbp+170h+sz]; lpsz
0x18006b64b  call    cs:__imp_StringFromGUID2
0x18006b651  mov     esi, 80h
0x18006b656  mov     [rbp+170h+var_1D0], r15
0x18006b65a  mov     edx, esi
0x18006b65c  lea     r8, aClsid; "CLSID\\"
0x18006b663  lea     rcx, [rbp+170h+SubKey]
0x18006b667  call    cs:__imp__o_wcscpy_s
0x18006b66d  mov     ecx, eax; int
0x18006b66f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006b674  lea     r8, [rbp+170h+sz]
0x18006b67b  mov     edx, esi
0x18006b67d  lea     rcx, [rbp+170h+SubKey]
0x18006b681  call    cs:__imp__o_wcscat_s
0x18006b687  mov     ecx, eax; int
0x18006b689  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006b68e  lea     r8, aRequiredCatego; "\\Required Categories"
0x18006b695  mov     edx, esi
0x18006b697  lea     rcx, [rbp+170h+SubKey]
0x18006b69b  call    cs:__imp__o_wcscat_s
0x18006b6a1  mov     ecx, eax; int
0x18006b6a3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006b6a8  mov     rdi, 0FFFFFFFF80000000h
0x18006b6af  mov     [rbp+170h+var_1E0], r15
0x18006b6b3  mov     r14d, 20019h
0x18006b6b9  mov     [rbp+170h+var_1E8], rdi
0x18006b6bd  mov     r9d, r14d; unsigned int
0x18006b6c0  mov     [rbp+170h+var_1D8], r15
0x18006b6c4  mov     rdx, rdi; hKey
0x18006b6c7  mov     [rsp+270h+hKey], r15
0x18006b6cc  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18006b6d0  mov     [rsp+270h+var_1F8], r15
0x18006b6d5  lea     rcx, [rsp+270h+hKey]; this
0x18006b6da  mov     [rbp+170h+var_1F0], r15
0x18006b6de  mov     [rsp+270h+cSubKeys], r15d
0x18006b6e3  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18006b6e8  test    eax, eax
0x18006b6ea  jnz     short loc_18006B754
0x18006b6ec  mov     rcx, [rsp+270h+hKey]; hKey
0x18006b6f1  lea     rax, [rsp+270h+cSubKeys]
0x18006b6f6  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18006b6fb  xor     r9d, r9d; lpReserved
0x18006b6fe  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18006b703  xor     r8d, r8d; lpcchClass
0x18006b706  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18006b70b  xor     edx, edx; lpClass
0x18006b70d  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18006b712  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18006b717  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18006b71c  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18006b721  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18006b726  call    cs:__imp_RegQueryInfoKeyW
0x18006b72c  lea     rcx, [rsp+270h+hKey]; this
0x18006b731  mov     ebx, eax
0x18006b733  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006b738  test    ebx, ebx
0x18006b73a  jnz     short loc_18006B754
0x18006b73c  cmp     [rsp+270h+cSubKeys], r15d
0x18006b741  jnz     short loc_18006B754
0x18006b743  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18006b747  lea     rcx, [rbp+170h+var_1E8]; this
0x18006b74b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18006b750  mov     rdi, [rbp+170h+var_1E8]
0x18006b754  lea     r8, aClsid; "CLSID\\"
0x18006b75b  mov     rdx, rsi
0x18006b75e  lea     rcx, [rbp+170h+SubKey]
0x18006b762  call    cs:__imp__o_wcscpy_s
0x18006b768  mov     ecx, eax; int
0x18006b76a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006b76f  lea     r8, [rbp+170h+sz]
0x18006b776  mov     rdx, rsi
0x18006b779  lea     rcx, [rbp+170h+SubKey]
0x18006b77d  call    cs:__imp__o_wcscat_s
0x18006b783  mov     ecx, eax; int
0x18006b785  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006b78a  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18006b791  mov     rdx, rsi
0x18006b794  lea     rcx, [rbp+170h+SubKey]
0x18006b798  call    cs:__imp__o_wcscat_s
0x18006b79e  mov     ecx, eax; int
0x18006b7a0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18006b7a5  mov     r9d, r14d; unsigned int
0x18006b7a8  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18006b7ac  mov     rdx, rdi; hKey
0x18006b7af  lea     rcx, [rsp+270h+hKey]; this
0x18006b7b4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18006b7b9  test    eax, eax
0x18006b7bb  jnz     short loc_18006B821
0x18006b7bd  mov     rcx, [rsp+270h+hKey]; hKey
0x18006b7c2  lea     rax, [rsp+270h+cSubKeys]
0x18006b7c7  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18006b7cc  xor     r9d, r9d; lpReserved
0x18006b7cf  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18006b7d4  xor     r8d, r8d; lpcchClass
0x18006b7d7  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18006b7dc  xor     edx, edx; lpClass
0x18006b7de  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18006b7e3  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18006b7e8  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18006b7ed  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18006b7f2  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18006b7f7  call    cs:__imp_RegQueryInfoKeyW
0x18006b7fd  lea     rcx, [rsp+270h+hKey]; this
0x18006b802  mov     ebx, eax
0x18006b804  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006b809  test    ebx, ebx
0x18006b80b  jnz     short loc_18006B821
0x18006b80d  cmp     [rsp+270h+cSubKeys], r15d
0x18006b812  jnz     short loc_18006B821
0x18006b814  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18006b818  lea     rcx, [rbp+170h+var_1E8]; this
0x18006b81c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18006b821  lea     rcx, [rsp+270h+hKey]; this
0x18006b826  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006b82b  lea     rcx, [rbp+170h+var_1E8]; this
0x18006b82f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006b834  lea     rcx, [rbp+170h+var_1D0]
0x18006b838  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18006b83d  mov     edi, r15d
0x18006b840  lea     rcx, [rsp+270h+var_208]
0x18006b845  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b84a  mov     eax, edi
0x18006b84c  mov     rcx, [rbp+170h+var_30]
0x18006b853  xor     rcx, rsp; StackCookie
0x18006b856  call    __security_check_cookie
0x18006b85b  lea     r11, [rsp+270h+var_20]
0x18006b863  mov     rbx, [r11+40h]
0x18006b867  mov     rsi, [r11+48h]
0x18006b86b  mov     rsp, r11
0x18006b86e  pop     r15
0x18006b870  pop     r14
0x18006b872  pop     r12
0x18006b874  pop     rdi
0x18006b875  pop     rbp
0x18006b876  retn
```
