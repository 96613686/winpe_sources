# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000bb08`
- end: `0x18000be43`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d020`
- `0x18000da74`
- `0x18000e2b0`

## callees

- `0x180002300`
- `0x18000ac10`
- `0x18000ad14`
- `0x18000b9a4`
- `0x18000bb08`
- `0x18000bf84`
- `0x18000c2bc`
- `0x18000c8a0`
- `0x18000e328`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000bc4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000bc67`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000bd49`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000bd64`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000bc4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000bc67`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000bd49`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000bd64`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bc33`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bd2e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bc33`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bd2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000bcf2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000bdc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000bcf2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000bdc3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bb90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bb90`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000bc17`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000bc17`

## string_xrefs

- `0x18000bc28`: `CLSID\`
- `0x18000bd20`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(
        GUID *rguid,
        const struct ATL::_ATL_CATMAP_ENTRY *a2,
        __int64 a3)
{
  int v3; // r14d
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
  v3 = a3;
  v4 = a2;
  v24 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL, a3)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v24 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( v3 )
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
    if ( !v3 )
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x18000bb08  mov     [rsp-8+arg_10], rbx
0x18000bb0d  mov     [rsp-8+arg_18], rsi
0x18000bb12  push    rbp
0x18000bb13  push    rdi
0x18000bb14  push    r12
0x18000bb16  push    r14
0x18000bb18  push    r15
0x18000bb1a  lea     rbp, [rsp-150h]
0x18000bb22  sub     rsp, 250h
0x18000bb29  mov     rax, cs:__security_cookie
0x18000bb30  xor     rax, rsp
0x18000bb33  mov     [rbp+170h+var_30], rax
0x18000bb3a  xor     r15d, r15d
0x18000bb3d  xorps   xmm0, xmm0
0x18000bb40  mov     [rsp+270h+var_208], r15
0x18000bb45  mov     r14d, r8d
0x18000bb48  mov     rbx, rdx
0x18000bb4b  mov     rsi, rcx
0x18000bb4e  movups  [rbp+170h+var_1C8], xmm0
0x18000bb52  test    rdx, rdx
0x18000bb55  jz      loc_18000BE09
0x18000bb5b  lea     rdx, GUID_NULL
0x18000bb62  call    InlineIsEqualGUID
0x18000bb67  test    eax, eax
0x18000bb69  jnz     loc_18000BE09
0x18000bb6f  lea     rax, [rsp+270h+var_208]
0x18000bb74  xor     edx, edx; pUnkOuter
0x18000bb76  lea     r12d, [r15+1]
0x18000bb7a  mov     [rsp+270h+ppv], rax; ppv
0x18000bb7f  mov     r8d, r12d; dwClsContext
0x18000bb82  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000bb89  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000bb90  call    cs:__imp_CoCreateInstance
0x18000bb96  test    eax, eax
0x18000bb98  js      loc_18000BE09
0x18000bb9e  cmp     [rbx], r15d
0x18000bba1  jz      short loc_18000BC00
0x18000bba3  mov     rax, [rbx+8]
0x18000bba7  lea     r9, [rbp+170h+var_1C8]
0x18000bbab  mov     rcx, [rsp+270h+var_208]
0x18000bbb0  mov     r8d, r12d
0x18000bbb3  mov     rdx, rsi
0x18000bbb6  movups  xmm0, xmmword ptr [rax]
0x18000bbb9  movdqu  [rbp+170h+var_1C8], xmm0
0x18000bbbe  mov     rax, [rcx]
0x18000bbc1  test    r14d, r14d
0x18000bbc4  jz      short loc_18000BBE6
0x18000bbc6  cmp     [rbx], r12d
0x18000bbc9  jnz     short loc_18000BBD1
0x18000bbcb  mov     rax, [rax+28h]
0x18000bbcf  jmp     short loc_18000BBD5
0x18000bbd1  mov     rax, [rax+38h]
0x18000bbd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbda  mov     edi, eax
0x18000bbdc  test    eax, eax
0x18000bbde  js      loc_18000BE0C
0x18000bbe4  jmp     short loc_18000BBFA
0x18000bbe6  cmp     [rbx], r12d
0x18000bbe9  jnz     short loc_18000BBF1
0x18000bbeb  mov     rax, [rax+30h]
0x18000bbef  jmp     short loc_18000BBF5
0x18000bbf1  mov     rax, [rax+40h]
0x18000bbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbfa  add     rbx, 10h
0x18000bbfe  jmp     short loc_18000BB9E
0x18000bc00  test    r14d, r14d
0x18000bc03  jnz     loc_18000BE09
0x18000bc09  lea     r8d, [r14+40h]; cchMax
0x18000bc0d  mov     rcx, rsi; rguid
0x18000bc10  lea     rdx, [rbp+170h+sz]; lpsz
0x18000bc17  call    cs:__imp_StringFromGUID2
0x18000bc1d  mov     esi, 80h
0x18000bc22  mov     [rbp+170h+var_1D0], r15
0x18000bc26  mov     edx, esi
0x18000bc28  lea     r8, aClsid; "CLSID\\"
0x18000bc2f  lea     rcx, [rbp+170h+SubKey]
0x18000bc33  call    cs:__imp__o_wcscpy_s
0x18000bc39  mov     ecx, eax; int
0x18000bc3b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bc40  lea     r8, [rbp+170h+sz]
0x18000bc47  mov     edx, esi
0x18000bc49  lea     rcx, [rbp+170h+SubKey]
0x18000bc4d  call    cs:__imp__o_wcscat_s
0x18000bc53  mov     ecx, eax; int
0x18000bc55  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bc5a  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000bc61  mov     edx, esi
0x18000bc63  lea     rcx, [rbp+170h+SubKey]
0x18000bc67  call    cs:__imp__o_wcscat_s
0x18000bc6d  mov     ecx, eax; int
0x18000bc6f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bc74  mov     rdi, 0FFFFFFFF80000000h
0x18000bc7b  mov     [rbp+170h+var_1E0], r15
0x18000bc7f  mov     r14d, 20019h
0x18000bc85  mov     [rbp+170h+var_1E8], rdi
0x18000bc89  mov     r9d, r14d; unsigned int
0x18000bc8c  mov     [rbp+170h+var_1D8], r15
0x18000bc90  mov     rdx, rdi; hKey
0x18000bc93  mov     [rsp+270h+hKey], r15
0x18000bc98  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18000bc9c  mov     [rsp+270h+var_1F8], r15
0x18000bca1  lea     rcx, [rsp+270h+hKey]; this
0x18000bca6  mov     [rbp+170h+var_1F0], r15
0x18000bcaa  mov     [rsp+270h+cSubKeys], r15d
0x18000bcaf  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000bcb4  test    eax, eax
0x18000bcb6  jnz     short loc_18000BD20
0x18000bcb8  mov     rcx, [rsp+270h+hKey]; hKey
0x18000bcbd  lea     rax, [rsp+270h+cSubKeys]
0x18000bcc2  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000bcc7  xor     r9d, r9d; lpReserved
0x18000bcca  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000bccf  xor     r8d, r8d; lpcchClass
0x18000bcd2  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000bcd7  xor     edx, edx; lpClass
0x18000bcd9  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000bcde  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000bce3  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000bce8  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000bced  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000bcf2  call    cs:__imp_RegQueryInfoKeyW
0x18000bcf8  lea     rcx, [rsp+270h+hKey]; this
0x18000bcfd  mov     ebx, eax
0x18000bcff  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000bd04  test    ebx, ebx
0x18000bd06  jnz     short loc_18000BD20
0x18000bd08  cmp     [rsp+270h+cSubKeys], r15d
0x18000bd0d  jnz     short loc_18000BD20
0x18000bd0f  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x18000bd13  lea     rcx, [rbp+170h+var_1E8]; this
0x18000bd17  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18000bd1c  mov     rdi, [rbp+170h+var_1E8]
0x18000bd20  lea     r8, aClsid; "CLSID\\"
0x18000bd27  mov     rdx, rsi
0x18000bd2a  lea     rcx, [rbp+170h+SubKey]
0x18000bd2e  call    cs:__imp__o_wcscpy_s
0x18000bd34  mov     ecx, eax; int
0x18000bd36  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bd3b  lea     r8, [rbp+170h+sz]
0x18000bd42  mov     rdx, rsi
0x18000bd45  lea     rcx, [rbp+170h+SubKey]
0x18000bd49  call    cs:__imp__o_wcscat_s
0x18000bd4f  mov     ecx, eax; int
0x18000bd51  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bd56  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000bd5d  mov     rdx, rsi
0x18000bd60  lea     rcx, [rbp+170h+SubKey]
0x18000bd64  call    cs:__imp__o_wcscat_s
0x18000bd6a  mov     ecx, eax; int
0x18000bd6c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bd71  mov     r9d, r14d; unsigned int
0x18000bd74  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x18000bd78  mov     rdx, rdi; hKey
0x18000bd7b  lea     rcx, [rsp+270h+hKey]; this
0x18000bd80  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000bd85  test    eax, eax
0x18000bd87  jnz     short loc_18000BDED
0x18000bd89  mov     rcx, [rsp+270h+hKey]; hKey
0x18000bd8e  lea     rax, [rsp+270h+cSubKeys]
0x18000bd93  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000bd98  xor     r9d, r9d; lpReserved
0x18000bd9b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000bda0  xor     r8d, r8d; lpcchClass
0x18000bda3  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000bda8  xor     edx, edx; lpClass
0x18000bdaa  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000bdaf  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000bdb4  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000bdb9  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000bdbe  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000bdc3  call    cs:__imp_RegQueryInfoKeyW
0x18000bdc9  lea     rcx, [rsp+270h+hKey]; this
0x18000bdce  mov     ebx, eax
0x18000bdd0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000bdd5  test    ebx, ebx
0x18000bdd7  jnz     short loc_18000BDED
0x18000bdd9  cmp     [rsp+270h+cSubKeys], r15d
0x18000bdde  jnz     short loc_18000BDED
0x18000bde0  lea     rdx, [rbp+170h+SubKey]; wchar_t *
0x18000bde4  lea     rcx, [rbp+170h+var_1E8]; this
0x18000bde8  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18000bded  lea     rcx, [rsp+270h+hKey]; this
0x18000bdf2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000bdf7  lea     rcx, [rbp+170h+var_1E8]; this
0x18000bdfb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000be00  lea     rcx, [rbp+170h+var_1D0]
0x18000be04  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000be09  mov     edi, r15d
0x18000be0c  lea     rcx, [rsp+270h+var_208]
0x18000be11  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000be16  mov     eax, edi
0x18000be18  mov     rcx, [rbp+170h+var_30]
0x18000be1f  xor     rcx, rsp; StackCookie
0x18000be22  call    __security_check_cookie
0x18000be27  lea     r11, [rsp+270h+var_20]
0x18000be2f  mov     rbx, [r11+40h]
0x18000be33  mov     rsi, [r11+48h]
0x18000be37  mov     rsp, r11
0x18000be3a  pop     r15
0x18000be3c  pop     r14
0x18000be3e  pop     r12
0x18000be40  pop     rdi
0x18000be41  pop     rbp
0x18000be42  retn
```
