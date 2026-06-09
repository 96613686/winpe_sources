# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180015a44`
- end: `0x180015d7a`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `822`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018efc`
- `0x180019c64`
- `0x18001a780`

## callees

- `0x18000e380`
- `0x18000e490`
- `0x18000ee1c`
- `0x180013f48`
- `0x180015728`
- `0x180015a44`
- `0x1800161e0`
- `0x180017490`
- `0x18001a74c`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180015b7b`
- `msvcrt!wcscpy_s` at `0x180015c6e`
- `msvcrt!wcscpy_s` at `0x180015b7b`
- `msvcrt!wcscpy_s` at `0x180015c6e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015b59`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015b59`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015acc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015acc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015c2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015cf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015c2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015cf3`

## string_xrefs

- `0x180015b70`: `CLSID\`
- `0x180015c60`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  errno_t v9; // eax
  unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r9
  HKEY v14; // rdi
  LSTATUS v15; // ebx
  errno_t v16; // eax
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
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
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
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v10, (unsigned __int64)sz, v11);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v12, (unsigned __int64)L"\\Required Categories", v13);
      v14 = HKEY_CLASSES_ROOT;
      v26[1] = 0;
      v26[0] = 0xFFFFFFFF80000000uLL;
      v26[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        v15 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v15 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, Destination);
          v14 = (HKEY)v26[0];
        }
      }
      v16 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v16);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v17, (unsigned __int64)sz, v18);
      ATL::Checked::wcscat_s((ATL::Checked *)Destination, v19, (unsigned __int64)L"\\Implemented Categories", v20);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v14, Destination, 0x20019u) )
      {
        v21 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v21 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v26, Destination);
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
0x180015a44  mov     [rsp-8+arg_10], rbx
0x180015a49  mov     [rsp-8+arg_18], rsi
0x180015a4e  push    rbp
0x180015a4f  push    rdi
0x180015a50  push    r12
0x180015a52  push    r14
0x180015a54  push    r15
0x180015a56  lea     rbp, [rsp-150h]
0x180015a5e  sub     rsp, 250h
0x180015a65  mov     rax, cs:__security_cookie
0x180015a6c  xor     rax, rsp
0x180015a6f  mov     [rbp+170h+var_30], rax
0x180015a76  xor     r15d, r15d
0x180015a79  xorps   xmm0, xmm0
0x180015a7c  mov     [rsp+270h+var_208], r15
0x180015a81  mov     r14d, r8d
0x180015a84  mov     rbx, rdx
0x180015a87  mov     rsi, rcx
0x180015a8a  movups  [rbp+170h+var_1C8], xmm0
0x180015a8e  test    rdx, rdx
0x180015a91  jz      loc_180015D3F
0x180015a97  lea     rdx, GUID_NULL
0x180015a9e  call    InlineIsEqualGUID
0x180015aa3  test    eax, eax
0x180015aa5  jnz     loc_180015D3F
0x180015aab  lea     rax, [rsp+270h+var_208]
0x180015ab0  xor     edx, edx; pUnkOuter
0x180015ab2  lea     r12d, [r15+1]
0x180015ab6  mov     [rsp+270h+ppv], rax; ppv
0x180015abb  mov     r8d, r12d; dwClsContext
0x180015abe  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180015ac5  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180015acc  call    cs:__imp_CoCreateInstance
0x180015ad3  nop     dword ptr [rax+rax+00h]
0x180015ad8  test    eax, eax
0x180015ada  js      loc_180015D3F
0x180015ae0  cmp     [rbx], r15d
0x180015ae3  jz      short loc_180015B42
0x180015ae5  mov     rax, [rbx+8]
0x180015ae9  lea     r9, [rbp+170h+var_1C8]
0x180015aed  mov     rcx, [rsp+270h+var_208]
0x180015af2  mov     r8d, r12d
0x180015af5  mov     rdx, rsi
0x180015af8  movups  xmm0, xmmword ptr [rax]
0x180015afb  movdqu  [rbp+170h+var_1C8], xmm0
0x180015b00  mov     rax, [rcx]
0x180015b03  test    r14d, r14d
0x180015b06  jz      short loc_180015B28
0x180015b08  cmp     [rbx], r12d
0x180015b0b  jnz     short loc_180015B13
0x180015b0d  mov     rax, [rax+28h]
0x180015b11  jmp     short loc_180015B17
0x180015b13  mov     rax, [rax+38h]
0x180015b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b1c  mov     edi, eax
0x180015b1e  test    eax, eax
0x180015b20  js      loc_180015D42
0x180015b26  jmp     short loc_180015B3C
0x180015b28  cmp     [rbx], r12d
0x180015b2b  jnz     short loc_180015B33
0x180015b2d  mov     rax, [rax+30h]
0x180015b31  jmp     short loc_180015B37
0x180015b33  mov     rax, [rax+40h]
0x180015b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b3c  add     rbx, 10h
0x180015b40  jmp     short loc_180015AE0
0x180015b42  test    r14d, r14d
0x180015b45  jnz     loc_180015D3F
0x180015b4b  lea     r8d, [r14+40h]; cchMax
0x180015b4f  mov     rcx, rsi; rguid
0x180015b52  lea     rdx, [rbp+170h+sz]; lpsz
0x180015b59  call    cs:__imp_StringFromGUID2
0x180015b60  nop     dword ptr [rax+rax+00h]
0x180015b65  mov     esi, 80h
0x180015b6a  mov     [rbp+170h+var_1D0], r15
0x180015b6e  mov     edx, esi; SizeInWords
0x180015b70  lea     r8, aClsid; "CLSID\\"
0x180015b77  lea     rcx, [rbp+170h+Destination]; Destination
0x180015b7b  call    cs:__imp_wcscpy_s
0x180015b82  nop     dword ptr [rax+rax+00h]
0x180015b87  mov     ecx, eax; int
0x180015b89  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180015b8e  lea     r8, [rbp+170h+sz]; unsigned __int64
0x180015b95  lea     rcx, [rbp+170h+Destination]; this
0x180015b99  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180015b9e  lea     r8, aRequiredCatego; "\\Required Categories"
0x180015ba5  lea     rcx, [rbp+170h+Destination]; this
0x180015ba9  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180015bae  mov     rdi, 0FFFFFFFF80000000h
0x180015bb5  mov     [rbp+170h+var_1E0], r15
0x180015bb9  mov     r14d, 20019h
0x180015bbf  mov     [rbp+170h+var_1E8], rdi
0x180015bc3  mov     r9d, r14d; unsigned int
0x180015bc6  mov     [rbp+170h+var_1D8], r15
0x180015bca  mov     rdx, rdi; hKey
0x180015bcd  mov     [rsp+270h+hKey], r15
0x180015bd2  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180015bd6  mov     [rsp+270h+var_1F8], r15
0x180015bdb  lea     rcx, [rsp+270h+hKey]; this
0x180015be0  mov     [rbp+170h+var_1F0], r15
0x180015be4  mov     [rsp+270h+cSubKeys], r15d
0x180015be9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180015bee  test    eax, eax
0x180015bf0  jnz     short loc_180015C60
0x180015bf2  mov     rcx, [rsp+270h+hKey]; hKey
0x180015bf7  lea     rax, [rsp+270h+cSubKeys]
0x180015bfc  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180015c01  xor     r9d, r9d; lpReserved
0x180015c04  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180015c09  xor     r8d, r8d; lpcchClass
0x180015c0c  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180015c11  xor     edx, edx; lpClass
0x180015c13  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180015c18  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180015c1d  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180015c22  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180015c27  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180015c2c  call    cs:__imp_RegQueryInfoKeyW
0x180015c33  nop     dword ptr [rax+rax+00h]
0x180015c38  lea     rcx, [rsp+270h+hKey]; this
0x180015c3d  mov     ebx, eax
0x180015c3f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015c44  test    ebx, ebx
0x180015c46  jnz     short loc_180015C60
0x180015c48  cmp     [rsp+270h+cSubKeys], r15d
0x180015c4d  jnz     short loc_180015C60
0x180015c4f  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180015c53  lea     rcx, [rbp+170h+var_1E8]; this
0x180015c57  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180015c5c  mov     rdi, [rbp+170h+var_1E8]
0x180015c60  lea     r8, aClsid; "CLSID\\"
0x180015c67  mov     rdx, rsi; SizeInWords
0x180015c6a  lea     rcx, [rbp+170h+Destination]; Destination
0x180015c6e  call    cs:__imp_wcscpy_s
0x180015c75  nop     dword ptr [rax+rax+00h]
0x180015c7a  mov     ecx, eax; int
0x180015c7c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180015c81  lea     r8, [rbp+170h+sz]; unsigned __int64
0x180015c88  lea     rcx, [rbp+170h+Destination]; this
0x180015c8c  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180015c91  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180015c98  lea     rcx, [rbp+170h+Destination]; this
0x180015c9c  call    ?wcscat_s@Checked@ATL@@YAXPEAG_KPEBG@Z; ATL::Checked::wcscat_s(ushort *,unsigned __int64,ushort const *)
0x180015ca1  mov     r9d, r14d; unsigned int
0x180015ca4  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180015ca8  mov     rdx, rdi; hKey
0x180015cab  lea     rcx, [rsp+270h+hKey]; this
0x180015cb0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180015cb5  test    eax, eax
0x180015cb7  jnz     short loc_180015D23
0x180015cb9  mov     rcx, [rsp+270h+hKey]; hKey
0x180015cbe  lea     rax, [rsp+270h+cSubKeys]
0x180015cc3  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180015cc8  xor     r9d, r9d; lpReserved
0x180015ccb  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180015cd0  xor     r8d, r8d; lpcchClass
0x180015cd3  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180015cd8  xor     edx, edx; lpClass
0x180015cda  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180015cdf  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180015ce4  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180015ce9  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180015cee  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180015cf3  call    cs:__imp_RegQueryInfoKeyW
0x180015cfa  nop     dword ptr [rax+rax+00h]
0x180015cff  lea     rcx, [rsp+270h+hKey]; this
0x180015d04  mov     ebx, eax
0x180015d06  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015d0b  test    ebx, ebx
0x180015d0d  jnz     short loc_180015D23
0x180015d0f  cmp     [rsp+270h+cSubKeys], r15d
0x180015d14  jnz     short loc_180015D23
0x180015d16  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180015d1a  lea     rcx, [rbp+170h+var_1E8]; this
0x180015d1e  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180015d23  lea     rcx, [rsp+270h+hKey]; this
0x180015d28  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015d2d  lea     rcx, [rbp+170h+var_1E8]; this
0x180015d31  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015d36  lea     rcx, [rbp+170h+var_1D0]
0x180015d3a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180015d3f  mov     edi, r15d
0x180015d42  lea     rcx, [rsp+270h+var_208]
0x180015d47  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015d4c  mov     eax, edi
0x180015d4e  mov     rcx, [rbp+170h+var_30]
0x180015d55  xor     rcx, rsp; StackCookie
0x180015d58  call    __security_check_cookie
0x180015d5d  lea     r11, [rsp+270h+var_20]
0x180015d65  mov     rbx, [r11+40h]
0x180015d69  mov     rsi, [r11+48h]
0x180015d6d  mov     rsp, r11
0x180015d70  pop     r15
0x180015d72  pop     r14
0x180015d74  pop     r12
0x180015d76  pop     rdi
0x180015d77  pop     rbp
0x180015d78  retn
```
