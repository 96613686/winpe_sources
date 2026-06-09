# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180001a38`
- end: `0x180001f3f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1287`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800013c0`
- `0x180001490`

## callees

- `0x180001848`
- `0x180001a38`
- `0x180002238`
- `0x180007700`
- `0x18000baa0`
- `0x18000bb1c`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x180001d25`
- `ADVAPI32!RegDeleteKeyW` at `0x180001ec1`
- `ADVAPI32!RegDeleteKeyW` at `0x180001d25`
- `ADVAPI32!RegDeleteKeyW` at `0x180001ec1`
- `ADVAPI32!RegCloseKey` at `0x180001ca9`
- `ADVAPI32!RegCloseKey` at `0x180001e4c`
- `ADVAPI32!RegCloseKey` at `0x180001ecf`
- `ADVAPI32!RegCloseKey` at `0x180001ed8`
- `ADVAPI32!RegCloseKey` at `0x180001ca9`
- `ADVAPI32!RegCloseKey` at `0x180001e4c`
- `ADVAPI32!RegCloseKey` at `0x180001ecf`
- `ADVAPI32!RegCloseKey` at `0x180001ed8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180001c99`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180001e3c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180001c99`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180001e3c`
- `KERNEL32!GetModuleHandleW` at `0x180001cd4`
- `KERNEL32!GetModuleHandleW` at `0x180001e70`
- `KERNEL32!GetModuleHandleW` at `0x180001cd4`
- `KERNEL32!GetModuleHandleW` at `0x180001e70`
- `KERNEL32!GetProcAddress` at `0x180001ce9`
- `KERNEL32!GetProcAddress` at `0x180001e85`
- `KERNEL32!GetProcAddress` at `0x180001ce9`
- `KERNEL32!GetProcAddress` at `0x180001e85`
- `ole32!CoCreateInstance` at `0x180001ad6`
- `ole32!CoCreateInstance` at `0x180001ad6`
- `ole32!StringFromGUID2` at `0x180001b58`
- `ole32!StringFromGUID2` at `0x180001b58`

## string_xrefs

- `0x180001b6f`: `CLSID\`
- `0x180001d30`: `CLSID\`
- `0x180001ccd`: `Advapi32.dll`
- `0x180001e69`: `Advapi32.dll`
- `0x180001cdf`: `RegDeleteKeyExW`
- `0x180001e7b`: `RegDeleteKeyExW`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rsi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // ecx
  errno_t v11; // eax
  errno_t v12; // eax
  errno_t v13; // eax
  HKEY v14; // rbx
  LSTATUS v15; // edi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  errno_t v18; // eax
  errno_t v19; // eax
  errno_t v20; // eax
  int v21; // eax
  HKEY v22; // rbx
  LSTATUS v23; // edi
  HMODULE v24; // rax
  FARPROC v25; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h] BYREF
  wchar_t Destination[128]; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR sz[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  ppv = 0;
  v4 = a2;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4]
    || CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
    goto LABEL_83;
  }
  while ( 1 )
  {
    v10 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
      break;
    v32 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( a3 )
    {
      v6 = *(_QWORD *)ppv;
      if ( v10 == 1 )
        v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v32);
      else
        v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v32);
      v8 = v7;
      if ( v7 < 0 )
        goto LABEL_84;
    }
    else
    {
      v9 = *(_QWORD *)ppv;
      if ( v10 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 48))(ppv, rguid, 1, &v32);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 64))(ppv, rguid, 1, &v32);
    }
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( a3 )
    goto LABEL_83;
  if ( !StringFromGUID2(rguid, sz, 64) )
  {
    v8 = 13;
    goto LABEL_84;
  }
  v11 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
  if ( v11 )
  {
    if ( v11 == 12 )
      goto LABEL_87;
    if ( v11 == 22 || v11 == 34 )
      goto LABEL_89;
    if ( v11 != 80 )
      goto LABEL_88;
  }
  v12 = wcscat_s(Destination, 0x80u, sz);
  if ( v12 )
  {
    if ( v12 == 12 )
      goto LABEL_87;
    if ( v12 == 22 || v12 == 34 )
      goto LABEL_89;
    if ( v12 != 80 )
      goto LABEL_88;
  }
  v13 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
  if ( v13 )
  {
    if ( v13 == 12 )
      goto LABEL_87;
    if ( v13 == 22 || v13 == 34 )
      goto LABEL_89;
    if ( v13 != 80 )
      goto LABEL_88;
  }
  v30 = 0;
  hKey = 0;
  v31 = 0;
  cSubKeys = 0;
  if ( !ATL::CRegKey::Open((ATL::CRegKey *)&hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
  {
    v14 = hKey;
    v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v14 )
    {
      RegCloseKey(v14);
      hKey = 0;
    }
    LODWORD(v30) = 0;
    if ( !v15 && !cSubKeys )
    {
      if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
      {
        ProcAddress = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
      }
      else
      {
        ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
        if ( ModuleHandleW )
        {
          ProcAddress = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
          `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)ProcAddress;
        }
        else
        {
          ProcAddress = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
        }
        `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
      }
      if ( ProcAddress )
        ((void (__fastcall *)(unsigned __int64, wchar_t *, _QWORD, _QWORD))ProcAddress)(
          0xFFFFFFFF80000000uLL,
          Destination,
          0,
          0);
      else
        RegDeleteKeyW(HKEY_CLASSES_ROOT, Destination);
    }
  }
  v18 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
  if ( v18 )
  {
    if ( v18 == 12 )
      goto LABEL_87;
    if ( v18 == 22 || v18 == 34 )
      goto LABEL_89;
    if ( v18 != 80 )
      goto LABEL_88;
  }
  v19 = wcscat_s(Destination, 0x80u, sz);
  if ( v19 )
  {
    if ( v19 == 12 )
      goto LABEL_87;
    if ( v19 == 22 || v19 == 34 )
      goto LABEL_89;
    if ( v19 != 80 )
      goto LABEL_88;
  }
  v20 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
  if ( v20 )
  {
    if ( v20 != 12 )
    {
      if ( v20 != 22 && v20 != 34 )
      {
        if ( v20 == 80 )
          goto LABEL_66;
LABEL_88:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_89:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_87:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_66:
  v21 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u);
  v22 = hKey;
  if ( !v21 )
  {
    v23 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v22 )
    {
      RegCloseKey(v22);
      v22 = 0;
    }
    if ( !v23 && !cSubKeys )
    {
      if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
      {
        v25 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
      }
      else
      {
        v24 = GetModuleHandleW(L"Advapi32.dll");
        if ( v24 )
        {
          v25 = GetProcAddress(v24, "RegDeleteKeyExW");
          `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)v25;
        }
        else
        {
          v25 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
        }
        `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
      }
      if ( v25 )
        ((void (__fastcall *)(unsigned __int64, wchar_t *, _QWORD, _QWORD))v25)(
          0xFFFFFFFF80000000uLL,
          Destination,
          0,
          0);
      else
        RegDeleteKeyW(HKEY_CLASSES_ROOT, Destination);
    }
  }
  if ( v22 )
    RegCloseKey(v22);
  RegCloseKey(HKEY_CLASSES_ROOT);
LABEL_83:
  v8 = 0;
LABEL_84:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x180001a38  mov     [rsp-8+arg_10], rbx
0x180001a3d  mov     [rsp-8+arg_18], rsi
0x180001a42  push    rbp
0x180001a43  push    rdi
0x180001a44  push    r12
0x180001a46  push    r14
0x180001a48  push    r15
0x180001a4a  lea     rbp, [rsp-130h]
0x180001a52  sub     rsp, 230h
0x180001a59  mov     rax, cs:__security_cookie
0x180001a60  xor     rax, rsp
0x180001a63  mov     [rbp+150h+var_30], rax
0x180001a6a  xor     r15d, r15d
0x180001a6d  mov     r14d, r8d
0x180001a70  mov     [rsp+250h+var_1E8], r15
0x180001a75  mov     rsi, rdx
0x180001a78  mov     rbx, rcx
0x180001a7b  test    rdx, rdx
0x180001a7e  jz      loc_180001EDE
0x180001a84  mov     eax, cs:GUID_NULL.Data1
0x180001a8a  cmp     [rcx], eax
0x180001a8c  jnz     short loc_180001AB3
0x180001a8e  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180001a94  cmp     [rcx+4], eax
0x180001a97  jnz     short loc_180001AB3
0x180001a99  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180001a9f  cmp     [rcx+8], eax
0x180001aa2  jnz     short loc_180001AB3
0x180001aa4  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180001aaa  cmp     [rcx+0Ch], eax
0x180001aad  jz      loc_180001EDE
0x180001ab3  lea     rax, [rsp+250h+var_1E8]
0x180001ab8  mov     r12d, 1
0x180001abe  mov     r8d, r12d; dwClsContext
0x180001ac1  mov     [rsp+250h+ppv], rax; ppv
0x180001ac6  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180001acd  xor     edx, edx; pUnkOuter
0x180001acf  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180001ad6  call    cs:__imp_CoCreateInstance
0x180001adc  test    eax, eax
0x180001ade  js      loc_180001EDE
0x180001ae4  jmp     short loc_180001B3B
0x180001ae6  mov     rax, [rsi+8]
0x180001aea  lea     r9, [rbp+150h+var_1C8]
0x180001aee  mov     r8d, r12d
0x180001af1  mov     rdx, rbx
0x180001af4  movups  xmm0, xmmword ptr [rax]
0x180001af7  movdqu  [rbp+150h+var_1C8], xmm0
0x180001afc  test    r14d, r14d
0x180001aff  jz      short loc_180001B22
0x180001b01  cmp     ecx, r12d
0x180001b04  mov     rcx, [rsp+250h+var_1E8]
0x180001b09  mov     rax, [rcx]
0x180001b0c  jnz     short loc_180001B13
0x180001b0e  call    qword ptr [rax+28h]
0x180001b11  jmp     short loc_180001B16
0x180001b13  call    qword ptr [rax+38h]
0x180001b16  mov     edi, eax
0x180001b18  test    eax, eax
0x180001b1a  js      loc_180001EE1
0x180001b20  jmp     short loc_180001B37
0x180001b22  cmp     ecx, r12d
0x180001b25  mov     rcx, [rsp+250h+var_1E8]
0x180001b2a  mov     rax, [rcx]
0x180001b2d  jnz     short loc_180001B34
0x180001b2f  call    qword ptr [rax+30h]
0x180001b32  jmp     short loc_180001B37
0x180001b34  call    qword ptr [rax+40h]
0x180001b37  add     rsi, 10h
0x180001b3b  mov     ecx, [rsi]
0x180001b3d  test    ecx, ecx
0x180001b3f  jnz     short loc_180001AE6
0x180001b41  test    r14d, r14d
0x180001b44  jnz     loc_180001EDE
0x180001b4a  lea     r8d, [rcx+40h]; cchMax
0x180001b4e  mov     rcx, rbx; rguid
0x180001b51  lea     rdx, [rbp+150h+sz]; lpsz
0x180001b58  call    cs:__imp_StringFromGUID2
0x180001b5e  test    eax, eax
0x180001b60  jnz     short loc_180001B6A
0x180001b62  lea     edi, [rax+0Dh]
0x180001b65  jmp     loc_180001EE1
0x180001b6a  mov     esi, 80h
0x180001b6f  lea     r8, aClsid; "CLSID\\"
0x180001b76  mov     edx, esi; SizeInWords
0x180001b78  lea     rcx, [rbp+150h+Destination]; Destination
0x180001b7c  call    wcscpy_s
0x180001b81  lea     r14d, [rsi-74h]
0x180001b85  test    eax, eax
0x180001b87  jz      short loc_180001BAD
0x180001b89  cmp     eax, r14d
0x180001b8c  jz      loc_180001F1E
0x180001b92  cmp     eax, 16h
0x180001b95  jz      loc_180001F34
0x180001b9b  cmp     eax, 22h ; '"'
0x180001b9e  jz      loc_180001F34
0x180001ba4  cmp     eax, 50h ; 'P'
0x180001ba7  jnz     loc_180001F29
0x180001bad  lea     r8, [rbp+150h+sz]; Source
0x180001bb4  mov     rdx, rsi; SizeInWords
0x180001bb7  lea     rcx, [rbp+150h+Destination]; Destination
0x180001bbb  call    wcscat_s
0x180001bc0  test    eax, eax
0x180001bc2  jz      short loc_180001BE8
0x180001bc4  cmp     eax, r14d
0x180001bc7  jz      loc_180001F1E
0x180001bcd  cmp     eax, 16h
0x180001bd0  jz      loc_180001F34
0x180001bd6  cmp     eax, 22h ; '"'
0x180001bd9  jz      loc_180001F34
0x180001bdf  cmp     eax, 50h ; 'P'
0x180001be2  jnz     loc_180001F29
0x180001be8  lea     r8, aRequiredCatego; "\\Required Categories"
0x180001bef  mov     rdx, rsi; SizeInWords
0x180001bf2  lea     rcx, [rbp+150h+Destination]; Destination
0x180001bf6  call    wcscat_s
0x180001bfb  test    eax, eax
0x180001bfd  jz      short loc_180001C23
0x180001bff  cmp     eax, r14d
0x180001c02  jz      loc_180001F1E
0x180001c08  cmp     eax, 16h
0x180001c0b  jz      loc_180001F34
0x180001c11  cmp     eax, 22h ; '"'
0x180001c14  jz      loc_180001F34
0x180001c1a  cmp     eax, 50h ; 'P'
0x180001c1d  jnz     loc_180001F29
0x180001c23  mov     rsi, 0FFFFFFFF80000000h
0x180001c2a  mov     [rsp+250h+var_1D8], r15
0x180001c2f  mov     rdx, rsi; HKEY
0x180001c32  mov     [rsp+250h+hKey], r15
0x180001c37  mov     r9d, 20019h; unsigned int
0x180001c3d  mov     [rbp+150h+var_1D0], r15
0x180001c41  lea     r8, [rbp+150h+Destination]; unsigned __int16 *
0x180001c45  mov     [rsp+250h+cSubKeys], r15d
0x180001c4a  lea     rcx, [rsp+250h+hKey]; this
0x180001c4f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180001c54  test    eax, eax
0x180001c56  jnz     loc_180001D2B
0x180001c5c  mov     rbx, [rsp+250h+hKey]
0x180001c61  lea     rax, [rsp+250h+cSubKeys]
0x180001c66  mov     [rsp+250h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180001c6b  xor     r9d, r9d; lpReserved
0x180001c6e  mov     [rsp+250h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180001c73  xor     r8d, r8d; lpcchClass
0x180001c76  mov     [rsp+250h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180001c7b  xor     edx, edx; lpClass
0x180001c7d  mov     [rsp+250h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180001c82  mov     rcx, rbx; hKey
0x180001c85  mov     [rsp+250h+lpcValues], r15; lpcValues
0x180001c8a  mov     [rsp+250h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180001c8f  mov     [rsp+250h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180001c94  mov     [rsp+250h+ppv], rax; lpcSubKeys
0x180001c99  call    cs:__imp_RegQueryInfoKeyW
0x180001c9f  mov     edi, eax
0x180001ca1  test    rbx, rbx
0x180001ca4  jz      short loc_180001CB4
0x180001ca6  mov     rcx, rbx; hKey
0x180001ca9  call    cs:__imp_RegCloseKey
0x180001caf  mov     [rsp+250h+hKey], r15
0x180001cb4  mov     dword ptr [rsp+250h+var_1D8], r15d
0x180001cb9  test    edi, edi
0x180001cbb  jnz     short loc_180001D2B
0x180001cbd  cmp     [rsp+250h+cSubKeys], r15d
0x180001cc2  jnz     short loc_180001D2B
0x180001cc4  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, r15b; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x180001ccb  jnz     short loc_180001D08
0x180001ccd  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x180001cd4  call    cs:__imp_GetModuleHandleW
0x180001cda  test    rax, rax
0x180001cdd  jz      short loc_180001CF8
0x180001cdf  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180001ce6  mov     rcx, rax; hModule
0x180001ce9  call    cs:__imp_GetProcAddress
0x180001cef  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001cf6  jmp     short loc_180001CFF
0x180001cf8  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001cff  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, r12b; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x180001d06  jmp     short loc_180001D0F
0x180001d08  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001d0f  lea     rdx, [rbp+150h+Destination]; lpSubKey
0x180001d13  mov     rcx, rsi; hKey
0x180001d16  test    rax, rax
0x180001d19  jz      short loc_180001D25
0x180001d1b  xor     r9d, r9d
0x180001d1e  xor     r8d, r8d
0x180001d21  call    rax
0x180001d23  jmp     short loc_180001D2B
0x180001d25  call    cs:__imp_RegDeleteKeyW
0x180001d2b  mov     ebx, 80h
0x180001d30  lea     r8, aClsid; "CLSID\\"
0x180001d37  mov     edx, ebx; SizeInWords
0x180001d39  lea     rcx, [rbp+150h+Destination]; Destination
0x180001d3d  call    wcscpy_s
0x180001d42  test    eax, eax
0x180001d44  jz      short loc_180001D6A
0x180001d46  cmp     eax, r14d
0x180001d49  jz      loc_180001F1E
0x180001d4f  cmp     eax, 16h
0x180001d52  jz      loc_180001F34
0x180001d58  cmp     eax, 22h ; '"'
0x180001d5b  jz      loc_180001F34
0x180001d61  cmp     eax, 50h ; 'P'
0x180001d64  jnz     loc_180001F29
0x180001d6a  lea     r8, [rbp+150h+sz]; Source
0x180001d71  mov     rdx, rbx; SizeInWords
0x180001d74  lea     rcx, [rbp+150h+Destination]; Destination
0x180001d78  call    wcscat_s
0x180001d7d  test    eax, eax
0x180001d7f  jz      short loc_180001DA5
0x180001d81  cmp     eax, r14d
0x180001d84  jz      loc_180001F1E
0x180001d8a  cmp     eax, 16h
0x180001d8d  jz      loc_180001F34
0x180001d93  cmp     eax, 22h ; '"'
0x180001d96  jz      loc_180001F34
0x180001d9c  cmp     eax, 50h ; 'P'
0x180001d9f  jnz     loc_180001F29
0x180001da5  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180001dac  mov     rdx, rbx; SizeInWords
0x180001daf  lea     rcx, [rbp+150h+Destination]; Destination
0x180001db3  call    wcscat_s
0x180001db8  test    eax, eax
0x180001dba  jz      short loc_180001DE0
0x180001dbc  cmp     eax, r14d
0x180001dbf  jz      loc_180001F1E
0x180001dc5  cmp     eax, 16h
0x180001dc8  jz      loc_180001F34
0x180001dce  cmp     eax, 22h ; '"'
0x180001dd1  jz      loc_180001F34
0x180001dd7  cmp     eax, 50h ; 'P'
0x180001dda  jnz     loc_180001F29
0x180001de0  mov     r9d, 20019h; unsigned int
0x180001de6  lea     r8, [rbp+150h+Destination]; unsigned __int16 *
0x180001dea  mov     rdx, rsi; HKEY
0x180001ded  lea     rcx, [rsp+250h+hKey]; this
0x180001df2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180001df7  mov     rbx, [rsp+250h+hKey]
0x180001dfc  test    eax, eax
0x180001dfe  jnz     loc_180001EC7
0x180001e04  mov     [rsp+250h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180001e09  lea     rax, [rsp+250h+cSubKeys]
0x180001e0e  mov     [rsp+250h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180001e13  xor     r9d, r9d; lpReserved
0x180001e16  mov     [rsp+250h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180001e1b  xor     r8d, r8d; lpcchClass
0x180001e1e  mov     [rsp+250h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180001e23  xor     edx, edx; lpClass
0x180001e25  mov     [rsp+250h+lpcValues], r15; lpcValues
0x180001e2a  mov     rcx, rbx; hKey
0x180001e2d  mov     [rsp+250h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180001e32  mov     [rsp+250h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180001e37  mov     [rsp+250h+ppv], rax; lpcSubKeys
0x180001e3c  call    cs:__imp_RegQueryInfoKeyW
0x180001e42  mov     edi, eax
0x180001e44  test    rbx, rbx
0x180001e47  jz      short loc_180001E55
0x180001e49  mov     rcx, rbx; hKey
0x180001e4c  call    cs:__imp_RegCloseKey
0x180001e52  mov     rbx, r15
0x180001e55  test    edi, edi
0x180001e57  jnz     short loc_180001EC7
0x180001e59  cmp     [rsp+250h+cSubKeys], r15d
0x180001e5e  jnz     short loc_180001EC7
0x180001e60  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, r15b; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x180001e67  jnz     short loc_180001EA4
0x180001e69  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x180001e70  call    cs:__imp_GetModuleHandleW
0x180001e76  test    rax, rax
0x180001e79  jz      short loc_180001E94
0x180001e7b  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180001e82  mov     rcx, rax; hModule
0x180001e85  call    cs:__imp_GetProcAddress
0x180001e8b  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001e92  jmp     short loc_180001E9B
0x180001e94  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001e9b  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, r12b; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x180001ea2  jmp     short loc_180001EAB
0x180001ea4  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001eab  lea     rdx, [rbp+150h+Destination]; lpSubKey
0x180001eaf  mov     rcx, rsi; hKey
0x180001eb2  test    rax, rax
0x180001eb5  jz      short loc_180001EC1
0x180001eb7  xor     r9d, r9d
0x180001eba  xor     r8d, r8d
0x180001ebd  call    rax
0x180001ebf  jmp     short loc_180001EC7
0x180001ec1  call    cs:__imp_RegDeleteKeyW
0x180001ec7  test    rbx, rbx
0x180001eca  jz      short loc_180001ED5
0x180001ecc  mov     rcx, rbx; hKey
0x180001ecf  call    cs:__imp_RegCloseKey
0x180001ed5  mov     rcx, rsi; hKey
0x180001ed8  call    cs:__imp_RegCloseKey
0x180001ede  mov     edi, r15d
0x180001ee1  mov     rcx, [rsp+250h+var_1E8]
0x180001ee6  test    rcx, rcx
0x180001ee9  jz      short loc_180001EF1
0x180001eeb  mov     rdx, [rcx]
0x180001eee  call    qword ptr [rdx+10h]
0x180001ef1  mov     eax, edi
  ... truncated ...
```
