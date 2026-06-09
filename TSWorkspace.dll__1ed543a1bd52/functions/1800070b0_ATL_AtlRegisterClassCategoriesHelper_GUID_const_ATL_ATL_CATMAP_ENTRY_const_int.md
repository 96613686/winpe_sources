# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800070b0`
- end: `0x1800073f6`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `838`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b738`
- `0x18000caa4`
- `0x18000e7a0`
- `0x18000e860`

## callees

- `0x180004a18`
- `0x180005374`
- `0x180006cc8`
- `0x1800070b0`
- `0x180007844`
- `0x1800098fc`
- `0x18000a9a4`
- `0x18000e94c`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800071fd`
- `msvcrt!wcscat_s` at `0x180007217`
- `msvcrt!wcscat_s` at `0x1800072f9`
- `msvcrt!wcscat_s` at `0x180007314`
- `msvcrt!wcscat_s` at `0x1800071fd`
- `msvcrt!wcscat_s` at `0x180007217`
- `msvcrt!wcscat_s` at `0x1800072f9`
- `msvcrt!wcscat_s` at `0x180007314`
- `msvcrt!wcscpy_s` at `0x1800071e3`
- `msvcrt!wcscpy_s` at `0x1800072de`
- `msvcrt!wcscpy_s` at `0x1800071e3`
- `msvcrt!wcscpy_s` at `0x1800072de`
- `ole32!StringFromGUID2` at `0x1800071c7`
- `ole32!StringFromGUID2` at `0x1800071c7`
- `ole32!CoCreateInstance` at `0x180007140`
- `ole32!CoCreateInstance` at `0x180007140`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800072a2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007373`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800072a2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180007373`

## string_xrefs

- `0x1800071d1`: `CLSID\`
- `0x1800072d0`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  LSTATUS InfoKeyW; // ebx
  errno_t v14; // eax
  errno_t v15; // eax
  errno_t v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys[2]; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v23[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v24; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t Destination[128]; // [rsp+C8h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C8h] [rbp+C0h] BYREF

  v23[1] = -2;
  v4 = a2;
  ppv = 0;
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
      v23[0] = 0;
      v9 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = wcscat_s(Destination, 0x80u, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[1] = 0;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys[0] = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
      {
        InfoKeyW = RegQueryInfoKeyW(hKey[0], 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !InfoKeyW && !cSubKeys[0] )
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
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys[0] )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v23);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x1800070b0  mov     rax, rsp
0x1800070b3  push    rbp
0x1800070b4  push    rdi
0x1800070b5  push    r12
0x1800070b7  push    r14
0x1800070b9  push    r15
0x1800070bb  lea     rbp, [rax-178h]
0x1800070c2  sub     rsp, 250h
0x1800070c9  mov     [rbp+170h+var_1C8], 0FFFFFFFFFFFFFFFEh
0x1800070d1  mov     [rax+18h], rbx
0x1800070d5  mov     [rax+20h], rsi
0x1800070d9  mov     rax, cs:__security_cookie
0x1800070e0  xor     rax, rsp
0x1800070e3  mov     [rbp+170h+var_30], rax
0x1800070ea  mov     r14d, r8d
0x1800070ed  mov     rbx, rdx
0x1800070f0  mov     rsi, rcx
0x1800070f3  xor     r15d, r15d
0x1800070f6  mov     [rsp+270h+var_208], r15
0x1800070fb  xorps   xmm0, xmm0
0x1800070fe  movups  [rbp+170h+var_1C0], xmm0
0x180007102  test    rdx, rdx
0x180007105  jz      loc_1800073BC
0x18000710b  lea     rdx, GUID_NULL
0x180007112  call    InlineIsEqualGUID
0x180007117  test    eax, eax
0x180007119  jnz     loc_1800073BC
0x18000711f  lea     rax, [rsp+270h+var_208]
0x180007124  mov     [rsp+270h+ppv], rax; ppv
0x180007129  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180007130  lea     r12d, [r15+1]
0x180007134  mov     r8d, r12d; dwClsContext
0x180007137  xor     edx, edx; pUnkOuter
0x180007139  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180007140  call    cs:__imp_CoCreateInstance
0x180007146  test    eax, eax
0x180007148  js      loc_1800073BC
0x18000714e  cmp     [rbx], r15d
0x180007151  jz      short loc_1800071B0
0x180007153  mov     rax, [rbx+8]
0x180007157  movups  xmm0, xmmword ptr [rax]
0x18000715a  movdqu  [rbp+170h+var_1C0], xmm0
0x18000715f  mov     rcx, [rsp+270h+var_208]
0x180007164  lea     r9, [rbp+170h+var_1C0]
0x180007168  mov     r8d, r12d
0x18000716b  mov     rdx, rsi
0x18000716e  mov     rax, [rcx]
0x180007171  test    r14d, r14d
0x180007174  jz      short loc_180007196
0x180007176  cmp     [rbx], r12d
0x180007179  jnz     short loc_180007181
0x18000717b  mov     rax, [rax+28h]
0x18000717f  jmp     short loc_180007185
0x180007181  mov     rax, [rax+38h]
0x180007185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000718a  mov     edi, eax
0x18000718c  test    eax, eax
0x18000718e  js      loc_1800073BF
0x180007194  jmp     short loc_1800071AA
0x180007196  cmp     [rbx], r12d
0x180007199  jnz     short loc_1800071A1
0x18000719b  mov     rax, [rax+30h]
0x18000719f  jmp     short loc_1800071A5
0x1800071a1  mov     rax, [rax+40h]
0x1800071a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071aa  add     rbx, 10h
0x1800071ae  jmp     short loc_18000714E
0x1800071b0  test    r14d, r14d
0x1800071b3  jnz     loc_1800073BC
0x1800071b9  lea     r8d, [r14+40h]; cchMax
0x1800071bd  lea     rdx, [rbp+170h+sz]; lpsz
0x1800071c4  mov     rcx, rsi; rguid
0x1800071c7  call    cs:__imp_StringFromGUID2
0x1800071cd  mov     [rbp+170h+var_1D0], r15
0x1800071d1  lea     r8, aClsid; "CLSID\\"
0x1800071d8  mov     esi, 80h
0x1800071dd  mov     edx, esi; SizeInWords
0x1800071df  lea     rcx, [rbp+170h+Destination]; Destination
0x1800071e3  call    cs:__imp_wcscpy_s
0x1800071e9  mov     ecx, eax; int
0x1800071eb  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800071f0  lea     r8, [rbp+170h+sz]; Source
0x1800071f7  mov     edx, esi; SizeInWords
0x1800071f9  lea     rcx, [rbp+170h+Destination]; Destination
0x1800071fd  call    cs:__imp_wcscat_s
0x180007203  mov     ecx, eax; int
0x180007205  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000720a  lea     r8, aRequiredCatego; "\\Required Categories"
0x180007211  mov     edx, esi; SizeInWords
0x180007213  lea     rcx, [rbp+170h+Destination]; Destination
0x180007217  call    cs:__imp_wcscat_s
0x18000721d  mov     ecx, eax; int
0x18000721f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007224  mov     rdi, 0FFFFFFFF80000000h
0x18000722b  mov     [rbp+170h+var_1E8], rdi
0x18000722f  mov     [rbp+170h+var_1E0], r15
0x180007233  mov     [rbp+170h+var_1D8], r15
0x180007237  mov     [rsp+270h+hKey], r15
0x18000723c  mov     [rsp+270h+var_1F8], r15
0x180007241  mov     [rbp+170h+var_1F0], r15
0x180007245  mov     [rsp+270h+cSubKeys], r15d
0x18000724a  mov     r14d, 20019h
0x180007250  mov     r9d, r14d; unsigned int
0x180007253  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180007257  mov     rdx, rdi; hKey
0x18000725a  lea     rcx, [rsp+270h+hKey]; this
0x18000725f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007264  test    eax, eax
0x180007266  jnz     short loc_1800072D0
0x180007268  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000726d  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180007272  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180007277  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000727c  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180007281  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180007286  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000728b  lea     rax, [rsp+270h+cSubKeys]
0x180007290  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180007295  xor     r9d, r9d; lpReserved
0x180007298  xor     r8d, r8d; lpcchClass
0x18000729b  xor     edx, edx; lpClass
0x18000729d  mov     rcx, [rsp+270h+hKey]; hKey
0x1800072a2  call    cs:__imp_RegQueryInfoKeyW
0x1800072a8  mov     ebx, eax
0x1800072aa  lea     rcx, [rsp+270h+hKey]; this
0x1800072af  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800072b4  test    ebx, ebx
0x1800072b6  jnz     short loc_1800072D0
0x1800072b8  cmp     [rsp+270h+cSubKeys], r15d
0x1800072bd  jnz     short loc_1800072D0
0x1800072bf  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x1800072c3  lea     rcx, [rbp+170h+var_1E8]; this
0x1800072c7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800072cc  mov     rdi, [rbp+170h+var_1E8]
0x1800072d0  lea     r8, aClsid; "CLSID\\"
0x1800072d7  mov     rdx, rsi; SizeInWords
0x1800072da  lea     rcx, [rbp+170h+Destination]; Destination
0x1800072de  call    cs:__imp_wcscpy_s
0x1800072e4  mov     ecx, eax; int
0x1800072e6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800072eb  lea     r8, [rbp+170h+sz]; Source
0x1800072f2  mov     rdx, rsi; SizeInWords
0x1800072f5  lea     rcx, [rbp+170h+Destination]; Destination
0x1800072f9  call    cs:__imp_wcscat_s
0x1800072ff  mov     ecx, eax; int
0x180007301  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007306  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000730d  mov     rdx, rsi; SizeInWords
0x180007310  lea     rcx, [rbp+170h+Destination]; Destination
0x180007314  call    cs:__imp_wcscat_s
0x18000731a  mov     ecx, eax; int
0x18000731c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007321  mov     r9d, r14d; unsigned int
0x180007324  lea     r8, [rbp+170h+Destination]; lpSubKey
0x180007328  mov     rdx, rdi; hKey
0x18000732b  lea     rcx, [rsp+270h+hKey]; this
0x180007330  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007335  test    eax, eax
0x180007337  jnz     short loc_18000739E
0x180007339  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000733e  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180007343  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180007348  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000734d  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180007352  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180007357  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000735c  lea     rax, [rsp+270h+cSubKeys]
0x180007361  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180007366  xor     r9d, r9d; lpReserved
0x180007369  xor     r8d, r8d; lpcchClass
0x18000736c  xor     edx, edx; lpClass
0x18000736e  mov     rcx, [rsp+270h+hKey]; hKey
0x180007373  call    cs:__imp_RegQueryInfoKeyW
0x180007379  mov     ebx, eax
0x18000737b  lea     rcx, [rsp+270h+hKey]; this
0x180007380  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007385  test    ebx, ebx
0x180007387  jnz     short loc_18000739E
0x180007389  cmp     [rsp+270h+cSubKeys], r15d
0x18000738e  jnz     short loc_18000739E
0x180007390  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x180007394  lea     rcx, [rbp+170h+var_1E8]; this
0x180007398  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000739d  nop
0x18000739e  lea     rcx, [rsp+270h+hKey]; this
0x1800073a3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800073a8  nop
0x1800073a9  lea     rcx, [rbp+170h+var_1E8]; this
0x1800073ad  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800073b2  nop
0x1800073b3  lea     rcx, [rbp+170h+var_1D0]
0x1800073b7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800073bc  mov     edi, r15d
0x1800073bf  lea     rcx, [rsp+270h+var_208]
0x1800073c4  call    ??1?$CComPtr@UIXMLDOMSchemaCollection@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(void)
0x1800073c9  mov     eax, edi
0x1800073cb  mov     rcx, [rbp+170h+var_30]
0x1800073d2  xor     rcx, rsp; StackCookie
0x1800073d5  call    __security_check_cookie
0x1800073da  lea     r11, [rsp+270h+var_20]
0x1800073e2  mov     rbx, [r11+40h]
0x1800073e6  mov     rsi, [r11+48h]
0x1800073ea  mov     rsp, r11
0x1800073ed  pop     r15
0x1800073ef  pop     r14
0x1800073f1  pop     r12
0x1800073f3  pop     rdi
0x1800073f4  pop     rbp
0x1800073f5  retn
```
