# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x14000ceb4`
- end: `0x14000d1ef`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d8e8`
- `0x14000dbdc`

## callees

- `0x140003340`
- `0x1400035c8`
- `0x140004d30`
- `0x140005134`
- `0x140005dc0`
- `0x1400083d0`
- `0x14000c828`
- `0x14000ceb4`
- `0x140015aa0`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x14000d09e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000d16f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000d09e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000d16f`
- `msvcrt!wcscat_s` at `0x14000cff9`
- `msvcrt!wcscat_s` at `0x14000d013`
- `msvcrt!wcscat_s` at `0x14000d0f5`
- `msvcrt!wcscat_s` at `0x14000d110`
- `msvcrt!wcscat_s` at `0x14000cff9`
- `msvcrt!wcscat_s` at `0x14000d013`
- `msvcrt!wcscat_s` at `0x14000d0f5`
- `msvcrt!wcscat_s` at `0x14000d110`
- `msvcrt!wcscpy_s` at `0x14000cfdf`
- `msvcrt!wcscpy_s` at `0x14000d0da`
- `msvcrt!wcscpy_s` at `0x14000cfdf`
- `msvcrt!wcscpy_s` at `0x14000d0da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000cf3c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000cf3c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000cfc3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000cfc3`

## string_xrefs

- `0x14000cfd4`: `CLSID\`
- `0x14000d0cc`: `CLSID\`

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
  LSTATUS v13; // ebx
  errno_t v14; // eax
  errno_t v15; // eax
  errno_t v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
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
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
          v12 = (HKEY)v22[0];
        }
      }
      v14 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, Destination, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x14000ceb4  mov     [rsp-8+arg_10], rbx
0x14000ceb9  mov     [rsp-8+arg_18], rsi
0x14000cebe  push    rbp
0x14000cebf  push    rdi
0x14000cec0  push    r12
0x14000cec2  push    r14
0x14000cec4  push    r15
0x14000cec6  lea     rbp, [rsp-150h]
0x14000cece  sub     rsp, 250h
0x14000ced5  mov     rax, cs:__security_cookie
0x14000cedc  xor     rax, rsp
0x14000cedf  mov     [rbp+170h+var_30], rax
0x14000cee6  xor     r15d, r15d
0x14000cee9  xorps   xmm0, xmm0
0x14000ceec  mov     [rsp+270h+var_208], r15
0x14000cef1  mov     r14d, r8d
0x14000cef4  mov     rbx, rdx
0x14000cef7  mov     rsi, rcx
0x14000cefa  movups  [rbp+170h+var_1C8], xmm0
0x14000cefe  test    rdx, rdx
0x14000cf01  jz      loc_14000D1B5
0x14000cf07  lea     rdx, GUID_NULL
0x14000cf0e  call    InlineIsEqualGUID
0x14000cf13  test    eax, eax
0x14000cf15  jnz     loc_14000D1B5
0x14000cf1b  lea     rax, [rsp+270h+var_208]
0x14000cf20  xor     edx, edx; pUnkOuter
0x14000cf22  lea     r12d, [r15+1]
0x14000cf26  mov     [rsp+270h+ppv], rax; ppv
0x14000cf2b  mov     r8d, r12d; dwClsContext
0x14000cf2e  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x14000cf35  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x14000cf3c  call    cs:__imp_CoCreateInstance
0x14000cf42  test    eax, eax
0x14000cf44  js      loc_14000D1B5
0x14000cf4a  cmp     [rbx], r15d
0x14000cf4d  jz      short loc_14000CFAC
0x14000cf4f  mov     rax, [rbx+8]
0x14000cf53  lea     r9, [rbp+170h+var_1C8]
0x14000cf57  mov     rcx, [rsp+270h+var_208]
0x14000cf5c  mov     r8d, r12d
0x14000cf5f  mov     rdx, rsi
0x14000cf62  movups  xmm0, xmmword ptr [rax]
0x14000cf65  movdqu  [rbp+170h+var_1C8], xmm0
0x14000cf6a  mov     rax, [rcx]
0x14000cf6d  test    r14d, r14d
0x14000cf70  jz      short loc_14000CF92
0x14000cf72  cmp     [rbx], r12d
0x14000cf75  jnz     short loc_14000CF7D
0x14000cf77  mov     rax, [rax+28h]
0x14000cf7b  jmp     short loc_14000CF81
0x14000cf7d  mov     rax, [rax+38h]
0x14000cf81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf86  mov     edi, eax
0x14000cf88  test    eax, eax
0x14000cf8a  js      loc_14000D1B8
0x14000cf90  jmp     short loc_14000CFA6
0x14000cf92  cmp     [rbx], r12d
0x14000cf95  jnz     short loc_14000CF9D
0x14000cf97  mov     rax, [rax+30h]
0x14000cf9b  jmp     short loc_14000CFA1
0x14000cf9d  mov     rax, [rax+40h]
0x14000cfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cfa6  add     rbx, 10h
0x14000cfaa  jmp     short loc_14000CF4A
0x14000cfac  test    r14d, r14d
0x14000cfaf  jnz     loc_14000D1B5
0x14000cfb5  lea     r8d, [r14+40h]; cchMax
0x14000cfb9  mov     rcx, rsi; rguid
0x14000cfbc  lea     rdx, [rbp+170h+sz]; lpsz
0x14000cfc3  call    cs:__imp_StringFromGUID2
0x14000cfc9  mov     esi, 80h
0x14000cfce  mov     [rbp+170h+var_1D0], r15
0x14000cfd2  mov     edx, esi; SizeInWords
0x14000cfd4  lea     r8, aClsid; "CLSID\\"
0x14000cfdb  lea     rcx, [rbp+170h+Destination]; Destination
0x14000cfdf  call    cs:__imp_wcscpy_s
0x14000cfe5  mov     ecx, eax; int
0x14000cfe7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000cfec  lea     r8, [rbp+170h+sz]; Source
0x14000cff3  mov     edx, esi; SizeInWords
0x14000cff5  lea     rcx, [rbp+170h+Destination]; Destination
0x14000cff9  call    cs:__imp_wcscat_s
0x14000cfff  mov     ecx, eax; int
0x14000d001  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000d006  lea     r8, aRequiredCatego; "\\Required Categories"
0x14000d00d  mov     edx, esi; SizeInWords
0x14000d00f  lea     rcx, [rbp+170h+Destination]; Destination
0x14000d013  call    cs:__imp_wcscat_s
0x14000d019  mov     ecx, eax; int
0x14000d01b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000d020  mov     rdi, 0FFFFFFFF80000000h
0x14000d027  mov     [rbp+170h+var_1E0], r15
0x14000d02b  mov     r14d, 20019h
0x14000d031  mov     [rbp+170h+var_1E8], rdi
0x14000d035  mov     r9d, r14d; unsigned int
0x14000d038  mov     [rbp+170h+var_1D8], r15
0x14000d03c  mov     rdx, rdi; hKey
0x14000d03f  mov     [rsp+270h+hKey], r15
0x14000d044  lea     r8, [rbp+170h+Destination]; lpSubKey
0x14000d048  mov     [rsp+270h+var_1F8], r15
0x14000d04d  lea     rcx, [rsp+270h+hKey]; this
0x14000d052  mov     [rbp+170h+var_1F0], r15
0x14000d056  mov     [rsp+270h+cSubKeys], r15d
0x14000d05b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000d060  test    eax, eax
0x14000d062  jnz     short loc_14000D0CC
0x14000d064  mov     rcx, [rsp+270h+hKey]; hKey
0x14000d069  lea     rax, [rsp+270h+cSubKeys]
0x14000d06e  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14000d073  xor     r9d, r9d; lpReserved
0x14000d076  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14000d07b  xor     r8d, r8d; lpcchClass
0x14000d07e  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14000d083  xor     edx, edx; lpClass
0x14000d085  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x14000d08a  mov     [rsp+270h+lpcValues], r15; lpcValues
0x14000d08f  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x14000d094  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x14000d099  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x14000d09e  call    cs:__imp_RegQueryInfoKeyW
0x14000d0a4  lea     rcx, [rsp+270h+hKey]; this
0x14000d0a9  mov     ebx, eax
0x14000d0ab  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000d0b0  test    ebx, ebx
0x14000d0b2  jnz     short loc_14000D0CC
0x14000d0b4  cmp     [rsp+270h+cSubKeys], r15d
0x14000d0b9  jnz     short loc_14000D0CC
0x14000d0bb  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x14000d0bf  lea     rcx, [rbp+170h+var_1E8]; this
0x14000d0c3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14000d0c8  mov     rdi, [rbp+170h+var_1E8]
0x14000d0cc  lea     r8, aClsid; "CLSID\\"
0x14000d0d3  mov     rdx, rsi; SizeInWords
0x14000d0d6  lea     rcx, [rbp+170h+Destination]; Destination
0x14000d0da  call    cs:__imp_wcscpy_s
0x14000d0e0  mov     ecx, eax; int
0x14000d0e2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000d0e7  lea     r8, [rbp+170h+sz]; Source
0x14000d0ee  mov     rdx, rsi; SizeInWords
0x14000d0f1  lea     rcx, [rbp+170h+Destination]; Destination
0x14000d0f5  call    cs:__imp_wcscat_s
0x14000d0fb  mov     ecx, eax; int
0x14000d0fd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000d102  lea     r8, aImplementedCat; "\\Implemented Categories"
0x14000d109  mov     rdx, rsi; SizeInWords
0x14000d10c  lea     rcx, [rbp+170h+Destination]; Destination
0x14000d110  call    cs:__imp_wcscat_s
0x14000d116  mov     ecx, eax; int
0x14000d118  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000d11d  mov     r9d, r14d; unsigned int
0x14000d120  lea     r8, [rbp+170h+Destination]; lpSubKey
0x14000d124  mov     rdx, rdi; hKey
0x14000d127  lea     rcx, [rsp+270h+hKey]; this
0x14000d12c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000d131  test    eax, eax
0x14000d133  jnz     short loc_14000D199
0x14000d135  mov     rcx, [rsp+270h+hKey]; hKey
0x14000d13a  lea     rax, [rsp+270h+cSubKeys]
0x14000d13f  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14000d144  xor     r9d, r9d; lpReserved
0x14000d147  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14000d14c  xor     r8d, r8d; lpcchClass
0x14000d14f  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14000d154  xor     edx, edx; lpClass
0x14000d156  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x14000d15b  mov     [rsp+270h+lpcValues], r15; lpcValues
0x14000d160  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x14000d165  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x14000d16a  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x14000d16f  call    cs:__imp_RegQueryInfoKeyW
0x14000d175  lea     rcx, [rsp+270h+hKey]; this
0x14000d17a  mov     ebx, eax
0x14000d17c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000d181  test    ebx, ebx
0x14000d183  jnz     short loc_14000D199
0x14000d185  cmp     [rsp+270h+cSubKeys], r15d
0x14000d18a  jnz     short loc_14000D199
0x14000d18c  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x14000d190  lea     rcx, [rbp+170h+var_1E8]; this
0x14000d194  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14000d199  lea     rcx, [rsp+270h+hKey]; this
0x14000d19e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000d1a3  lea     rcx, [rbp+170h+var_1E8]; this
0x14000d1a7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000d1ac  lea     rcx, [rbp+170h+var_1D0]
0x14000d1b0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14000d1b5  mov     edi, r15d
0x14000d1b8  lea     rcx, [rsp+270h+var_208]
0x14000d1bd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000d1c2  mov     eax, edi
0x14000d1c4  mov     rcx, [rbp+170h+var_30]
0x14000d1cb  xor     rcx, rsp; StackCookie
0x14000d1ce  call    __security_check_cookie
0x14000d1d3  lea     r11, [rsp+270h+var_20]
0x14000d1db  mov     rbx, [r11+40h]
0x14000d1df  mov     rsi, [r11+48h]
0x14000d1e3  mov     rsp, r11
0x14000d1e6  pop     r15
0x14000d1e8  pop     r14
0x14000d1ea  pop     r12
0x14000d1ec  pop     rdi
0x14000d1ed  pop     rbp
0x14000d1ee  retn
```
