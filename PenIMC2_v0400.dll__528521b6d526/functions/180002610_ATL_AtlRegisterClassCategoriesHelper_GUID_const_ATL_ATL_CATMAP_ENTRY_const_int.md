# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180002610`
- end: `0x180002bf2`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1506`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001510`
- `0x180001650`

## callees

- `0x180002610`
- `0x180004484`
- `0x18000cdb0`
- `0x18000e4a0`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x18000294a`
- `ADVAPI32!RegDeleteKeyW` at `0x180002b36`
- `ADVAPI32!RegDeleteKeyW` at `0x18000294a`
- `ADVAPI32!RegDeleteKeyW` at `0x180002b36`
- `ADVAPI32!RegCloseKey` at `0x1800028c3`
- `ADVAPI32!RegCloseKey` at `0x180002a41`
- `ADVAPI32!RegCloseKey` at `0x180002aaf`
- `ADVAPI32!RegCloseKey` at `0x180002b45`
- `ADVAPI32!RegCloseKey` at `0x180002b5b`
- `ADVAPI32!RegCloseKey` at `0x1800028c3`
- `ADVAPI32!RegCloseKey` at `0x180002a41`
- `ADVAPI32!RegCloseKey` at `0x180002aaf`
- `ADVAPI32!RegCloseKey` at `0x180002b45`
- `ADVAPI32!RegCloseKey` at `0x180002b5b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800028b2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002a9e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800028b2`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002a9e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000285a`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a28`
- `ADVAPI32!RegOpenKeyExW` at `0x18000285a`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a28`
- `KERNEL32!GetProcAddress` at `0x180002906`
- `KERNEL32!GetProcAddress` at `0x180002af2`
- `KERNEL32!GetProcAddress` at `0x180002906`
- `KERNEL32!GetProcAddress` at `0x180002af2`
- `KERNEL32!GetModuleHandleW` at `0x1800028f1`
- `KERNEL32!GetModuleHandleW` at `0x180002add`
- `KERNEL32!GetModuleHandleW` at `0x1800028f1`
- `KERNEL32!GetModuleHandleW` at `0x180002add`
- `ucrtbase_clr0400!wcscat_s` at `0x1800027aa`
- `ucrtbase_clr0400!wcscat_s` at `0x1800027e5`
- `ucrtbase_clr0400!wcscat_s` at `0x18000299d`
- `ucrtbase_clr0400!wcscat_s` at `0x1800029d8`
- `ucrtbase_clr0400!wcscat_s` at `0x1800027aa`
- `ucrtbase_clr0400!wcscat_s` at `0x1800027e5`
- `ucrtbase_clr0400!wcscat_s` at `0x18000299d`
- `ucrtbase_clr0400!wcscat_s` at `0x1800029d8`
- `ucrtbase_clr0400!wcscpy_s` at `0x180002768`
- `ucrtbase_clr0400!wcscpy_s` at `0x180002962`
- `ucrtbase_clr0400!wcscpy_s` at `0x180002768`
- `ucrtbase_clr0400!wcscpy_s` at `0x180002962`
- `ole32!StringFromGUID2` at `0x180002740`
- `ole32!StringFromGUID2` at `0x180002740`
- `ole32!CoCreateInstance` at `0x1800026ae`
- `ole32!CoCreateInstance` at `0x1800026ae`

## string_xrefs

- `0x180002756`: `CLSID\`
- `0x180002950`: `CLSID\`
- `0x1800028ea`: `Advapi32.dll`
- `0x180002ad6`: `Advapi32.dll`
- `0x1800028fc`: `RegDeleteKeyExW`
- `0x180002ae8`: `RegDeleteKeyExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  __int64 v15; // rdi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  errno_t v18; // eax
  errno_t v19; // eax
  errno_t v20; // eax
  HKEY v21; // rbx
  __int64 v22; // rdi
  HMODULE v23; // rax
  FARPROC v24; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  unsigned __int64 v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int128 v36; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = a2;
  ppv = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4]
    || CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
    goto LABEL_81;
  }
  while ( 1 )
  {
    v10 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
      break;
    v36 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( a3 )
    {
      v6 = *(_QWORD *)ppv;
      if ( v10 == 1 )
        v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v36);
      else
        v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v36);
      v8 = v7;
      if ( v7 < 0 )
        goto LABEL_82;
    }
    else
    {
      v9 = *(_QWORD *)ppv;
      if ( v10 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 48))(ppv, rguid, 1, &v36);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v9 + 64))(ppv, rguid, 1, &v36);
    }
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( a3 )
    goto LABEL_81;
  if ( !StringFromGUID2(rguid, sz, 64) )
  {
    v8 = 13;
    goto LABEL_82;
  }
  v35 = 0;
  v11 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
  if ( v11 )
  {
    if ( v11 == 12 )
      goto LABEL_88;
    if ( v11 == 22 || v11 == 34 )
      goto LABEL_87;
    if ( v11 != 80 )
      goto LABEL_86;
  }
  v12 = wcscat_s(Destination, 0x80u, sz);
  switch ( v12 )
  {
    case 0:
      goto LABEL_32;
    case 12:
      goto LABEL_88;
    case 22:
    case 34:
LABEL_87:
      ATL::AtlThrowImpl(-2147024809);
  }
  if ( v12 != 80 )
    goto LABEL_86;
LABEL_32:
  v13 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
  switch ( v13 )
  {
    case 0:
      goto LABEL_37;
    case 12:
LABEL_88:
      ATL::AtlThrowImpl(-2147024882);
    case 22:
    case 34:
      goto LABEL_87;
  }
  if ( v13 != 80 )
LABEL_86:
    ATL::AtlThrowImpl(-2147467259);
LABEL_37:
  v32 = 0xFFFFFFFF80000000uLL;
  v33 = 0;
  v34 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  cSubKeys = 0;
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
  {
    v14 = phkResult;
    v29 = phkResult;
    v30 = 0;
    v15 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v14 )
    {
      RegCloseKey(v14);
      v29 = 0;
    }
    v30 = 0;
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
      goto LABEL_85;
    if ( v18 == 22 || v18 == 34 )
      goto LABEL_90;
    if ( v18 != 80 )
      goto LABEL_89;
  }
  v19 = wcscat_s(Destination, 0x80u, sz);
  if ( v19 )
  {
    if ( v19 == 12 )
      goto LABEL_85;
    if ( v19 == 22 || v19 == 34 )
      goto LABEL_90;
    if ( v19 != 80 )
      goto LABEL_89;
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
LABEL_89:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_90:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_85:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_66:
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
  {
    v21 = phkResult;
    v29 = phkResult;
    v30 = 0;
    v22 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v21 )
    {
      RegCloseKey(v21);
      v29 = 0;
    }
    v30 = 0;
    if ( !v22 && !cSubKeys )
    {
      if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
      {
        v24 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
      }
      else
      {
        v23 = GetModuleHandleW(L"Advapi32.dll");
        if ( v23 )
        {
          v24 = GetProcAddress(v23, "RegDeleteKeyExW");
          `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)v24;
        }
        else
        {
          v24 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
        }
        `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
      }
      if ( v24 )
        ((void (__fastcall *)(unsigned __int64, wchar_t *, _QWORD, _QWORD))v24)(
          0xFFFFFFFF80000000uLL,
          Destination,
          0,
          0);
      else
        RegDeleteKeyW(HKEY_CLASSES_ROOT, Destination);
    }
  }
  v30 = 0;
  RegCloseKey(HKEY_CLASSES_ROOT);
  v32 = 0;
  v33 = 0;
LABEL_81:
  v8 = 0;
LABEL_82:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x180002610  mov     [rsp-8+arg_10], rbx
0x180002615  mov     [rsp-8+arg_18], rsi
0x18000261a  push    rbp
0x18000261b  push    rdi
0x18000261c  push    r12
0x18000261e  push    r14
0x180002620  push    r15
0x180002622  lea     rbp, [rsp-150h]
0x18000262a  sub     rsp, 250h
0x180002631  mov     rax, cs:__security_cookie
0x180002638  xor     rax, rsp
0x18000263b  mov     [rbp+170h+var_30], rax
0x180002642  mov     r14d, r8d
0x180002645  mov     rsi, rdx
0x180002648  mov     rbx, rcx
0x18000264b  xor     r15d, r15d
0x18000264e  mov     [rsp+270h+var_208], r15
0x180002653  test    rdx, rdx
0x180002656  jz      loc_180002B69
0x18000265c  mov     eax, cs:GUID_NULL.Data1
0x180002662  cmp     [rcx], eax
0x180002664  jnz     short loc_18000268B
0x180002666  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000266c  cmp     [rcx+4], eax
0x18000266f  jnz     short loc_18000268B
0x180002671  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180002677  cmp     [rcx+8], eax
0x18000267a  jnz     short loc_18000268B
0x18000267c  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180002682  cmp     [rcx+0Ch], eax
0x180002685  jz      loc_180002B69
0x18000268b  lea     rax, [rsp+270h+var_208]
0x180002690  mov     [rsp+270h+ppv], rax; ppv
0x180002695  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000269c  mov     r12d, 1
0x1800026a2  mov     r8d, r12d; dwClsContext
0x1800026a5  xor     edx, edx; pUnkOuter
0x1800026a7  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800026ae  call    cs:__imp_CoCreateInstance
0x1800026b4  test    eax, eax
0x1800026b6  js      loc_180002B69
0x1800026bc  jmp     short loc_180002723
0x1800026be  mov     rax, [rsi+8]
0x1800026c2  movups  xmm0, xmmword ptr [rax]
0x1800026c5  movdqu  [rbp+170h+var_1C0], xmm0
0x1800026ca  lea     r9, [rbp+170h+var_1C0]
0x1800026ce  mov     r8d, r12d
0x1800026d1  mov     rdx, rbx
0x1800026d4  test    r14d, r14d
0x1800026d7  jz      short loc_180002702
0x1800026d9  cmp     ecx, r12d
0x1800026dc  mov     rcx, [rsp+270h+var_208]
0x1800026e1  mov     rax, [rcx]
0x1800026e4  jnz     short loc_1800026EC
0x1800026e6  mov     rax, [rax+28h]
0x1800026ea  jmp     short loc_1800026F0
0x1800026ec  mov     rax, [rax+38h]
0x1800026f0  call    cs:__guard_dispatch_icall_fptr
0x1800026f6  mov     edi, eax
0x1800026f8  test    eax, eax
0x1800026fa  js      loc_180002B6C
0x180002700  jmp     short loc_18000271F
0x180002702  cmp     ecx, r12d
0x180002705  mov     rcx, [rsp+270h+var_208]
0x18000270a  mov     rax, [rcx]
0x18000270d  jnz     short loc_180002715
0x18000270f  mov     rax, [rax+30h]
0x180002713  jmp     short loc_180002719
0x180002715  mov     rax, [rax+40h]
0x180002719  call    cs:__guard_dispatch_icall_fptr
0x18000271f  add     rsi, 10h
0x180002723  mov     ecx, [rsi]
0x180002725  test    ecx, ecx
0x180002727  jnz     short loc_1800026BE
0x180002729  test    r14d, r14d
0x18000272c  jnz     loc_180002B69
0x180002732  lea     r8d, [rcx+40h]; cchMax
0x180002736  lea     rdx, [rbp+170h+sz]; lpsz
0x18000273d  mov     rcx, rbx; rguid
0x180002740  call    cs:__imp_StringFromGUID2
0x180002746  test    eax, eax
0x180002748  jnz     short loc_180002752
0x18000274a  lea     edi, [rax+0Dh]
0x18000274d  jmp     loc_180002B6C
0x180002752  mov     [rbp+170h+var_1C8], r15
0x180002756  lea     r8, aClsid; "CLSID\\"
0x18000275d  mov     ebx, 80h
0x180002762  mov     edx, ebx; SizeInWords
0x180002764  lea     rcx, [rbp+170h+Destination]; Destination
0x180002768  call    cs:__imp_wcscpy_s
0x18000276e  lea     esi, [rbx-74h]
0x180002771  lea     r14d, [rbx-6Ah]
0x180002775  test    eax, eax
0x180002777  jz      short loc_18000279C
0x180002779  cmp     eax, esi
0x18000277b  jz      loc_180002BD1
0x180002781  cmp     eax, r14d
0x180002784  jz      loc_180002BC6
0x18000278a  cmp     eax, 22h ; '"'
0x18000278d  jz      loc_180002BC6
0x180002793  cmp     eax, 50h ; 'P'
0x180002796  jnz     loc_180002BBB
0x18000279c  lea     r8, [rbp+170h+sz]; Source
0x1800027a3  mov     rdx, rbx; SizeInWords
0x1800027a6  lea     rcx, [rbp+170h+Destination]; Destination
0x1800027aa  call    cs:__imp_wcscat_s
0x1800027b0  test    eax, eax
0x1800027b2  jz      short loc_1800027D7
0x1800027b4  cmp     eax, esi
0x1800027b6  jz      loc_180002BD1
0x1800027bc  cmp     eax, r14d
0x1800027bf  jz      loc_180002BC6
0x1800027c5  cmp     eax, 22h ; '"'
0x1800027c8  jz      loc_180002BC6
0x1800027ce  cmp     eax, 50h ; 'P'
0x1800027d1  jnz     loc_180002BBB
0x1800027d7  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800027de  mov     rdx, rbx; SizeInWords
0x1800027e1  lea     rcx, [rbp+170h+Destination]; Destination
0x1800027e5  call    cs:__imp_wcscat_s
0x1800027eb  test    eax, eax
0x1800027ed  jz      short loc_180002812
0x1800027ef  cmp     eax, esi
0x1800027f1  jz      loc_180002BD1
0x1800027f7  cmp     eax, r14d
0x1800027fa  jz      loc_180002BC6
0x180002800  cmp     eax, 22h ; '"'
0x180002803  jz      loc_180002BC6
0x180002809  cmp     eax, 50h ; 'P'
0x18000280c  jnz     loc_180002BBB
0x180002812  mov     [rbp+170h+var_1E0], 0FFFFFFFF80000000h
0x18000281a  mov     [rbp+170h+var_1D8], r15d
0x18000281e  mov     [rbp+170h+var_1D0], r15
0x180002822  mov     rbx, r15
0x180002825  mov     [rsp+270h+var_1F8], rbx
0x18000282a  mov     [rbp+170h+var_1F0], r15d
0x18000282e  mov     [rbp+170h+var_1E8], r15
0x180002832  mov     [rsp+270h+cSubKeys], r15d
0x180002837  mov     [rsp+270h+phkResult], r15
0x18000283c  lea     rax, [rsp+270h+phkResult]
0x180002841  mov     [rsp+270h+ppv], rax; phkResult
0x180002846  mov     r9d, 20019h; samDesired
0x18000284c  xor     r8d, r8d; ulOptions
0x18000284f  lea     rdx, [rbp+170h+Destination]; lpSubKey
0x180002853  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000285a  call    cs:__imp_RegOpenKeyExW
0x180002860  test    eax, eax
0x180002862  jnz     loc_180002950
0x180002868  mov     [rbp+170h+var_1F0], r15d
0x18000286c  mov     rbx, [rsp+270h+phkResult]
0x180002871  mov     [rsp+270h+var_1F8], rbx
0x180002876  mov     [rbp+170h+var_1F0], r15d
0x18000287a  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000287f  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180002884  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180002889  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000288e  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180002893  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180002898  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000289d  lea     rax, [rsp+270h+cSubKeys]
0x1800028a2  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x1800028a7  xor     r9d, r9d; lpReserved
0x1800028aa  xor     r8d, r8d; lpcchClass
0x1800028ad  xor     edx, edx; lpClass
0x1800028af  mov     rcx, rbx; hKey
0x1800028b2  call    cs:__imp_RegQueryInfoKeyW
0x1800028b8  movsxd  rdi, eax
0x1800028bb  test    rbx, rbx
0x1800028be  jz      short loc_1800028D1
0x1800028c0  mov     rcx, rbx; hKey
0x1800028c3  call    cs:__imp_RegCloseKey
0x1800028c9  mov     rbx, r15
0x1800028cc  mov     [rsp+270h+var_1F8], rbx
0x1800028d1  mov     [rbp+170h+var_1F0], r15d
0x1800028d5  test    rdi, rdi
0x1800028d8  jnz     short loc_180002950
0x1800028da  cmp     [rsp+270h+cSubKeys], r15d
0x1800028df  jnz     short loc_180002950
0x1800028e1  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, r15b; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x1800028e8  jnz     short loc_180002925
0x1800028ea  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x1800028f1  call    cs:__imp_GetModuleHandleW
0x1800028f7  test    rax, rax
0x1800028fa  jz      short loc_180002915
0x1800028fc  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180002903  mov     rcx, rax; hModule
0x180002906  call    cs:__imp_GetProcAddress
0x18000290c  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180002913  jmp     short loc_18000291C
0x180002915  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x18000291c  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, r12b; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x180002923  jmp     short loc_18000292C
0x180002925  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x18000292c  lea     rdx, [rbp+170h+Destination]; lpSubKey
0x180002930  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002937  test    rax, rax
0x18000293a  jz      short loc_18000294A
0x18000293c  xor     r9d, r9d
0x18000293f  xor     r8d, r8d
0x180002942  call    cs:__guard_dispatch_icall_fptr
0x180002948  jmp     short loc_180002950
0x18000294a  call    cs:__imp_RegDeleteKeyW
0x180002950  lea     r8, aClsid; "CLSID\\"
0x180002957  mov     edi, 80h
0x18000295c  mov     edx, edi; SizeInWords
0x18000295e  lea     rcx, [rbp+170h+Destination]; Destination
0x180002962  call    cs:__imp_wcscpy_s
0x180002968  test    eax, eax
0x18000296a  jz      short loc_18000298F
0x18000296c  cmp     eax, esi
0x18000296e  jz      loc_180002BB0
0x180002974  cmp     eax, r14d
0x180002977  jz      loc_180002BE7
0x18000297d  cmp     eax, 22h ; '"'
0x180002980  jz      loc_180002BE7
0x180002986  cmp     eax, 50h ; 'P'
0x180002989  jnz     loc_180002BDC
0x18000298f  lea     r8, [rbp+170h+sz]; Source
0x180002996  mov     rdx, rdi; SizeInWords
0x180002999  lea     rcx, [rbp+170h+Destination]; Destination
0x18000299d  call    cs:__imp_wcscat_s
0x1800029a3  test    eax, eax
0x1800029a5  jz      short loc_1800029CA
0x1800029a7  cmp     eax, esi
0x1800029a9  jz      loc_180002BB0
0x1800029af  cmp     eax, r14d
0x1800029b2  jz      loc_180002BE7
0x1800029b8  cmp     eax, 22h ; '"'
0x1800029bb  jz      loc_180002BE7
0x1800029c1  cmp     eax, 50h ; 'P'
0x1800029c4  jnz     loc_180002BDC
0x1800029ca  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800029d1  mov     rdx, rdi; SizeInWords
0x1800029d4  lea     rcx, [rbp+170h+Destination]; Destination
0x1800029d8  call    cs:__imp_wcscat_s
0x1800029de  test    eax, eax
0x1800029e0  jz      short loc_180002A05
0x1800029e2  cmp     eax, esi
0x1800029e4  jz      loc_180002BB0
0x1800029ea  cmp     eax, r14d
0x1800029ed  jz      loc_180002BE7
0x1800029f3  cmp     eax, 22h ; '"'
0x1800029f6  jz      loc_180002BE7
0x1800029fc  cmp     eax, 50h ; 'P'
0x1800029ff  jnz     loc_180002BDC
0x180002a05  mov     [rsp+270h+phkResult], r15
0x180002a0a  lea     rax, [rsp+270h+phkResult]
0x180002a0f  mov     [rsp+270h+ppv], rax; phkResult
0x180002a14  mov     r9d, 20019h; samDesired
0x180002a1a  xor     r8d, r8d; ulOptions
0x180002a1d  lea     rdx, [rbp+170h+Destination]; lpSubKey
0x180002a21  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002a28  call    cs:__imp_RegOpenKeyExW
0x180002a2e  test    eax, eax
0x180002a30  jnz     loc_180002B3D
0x180002a36  mov     eax, r15d
0x180002a39  test    rbx, rbx
0x180002a3c  jz      short loc_180002A4C
0x180002a3e  mov     rcx, rbx; hKey
0x180002a41  call    cs:__imp_RegCloseKey
0x180002a47  mov     [rsp+270h+var_1F8], r15
0x180002a4c  mov     [rbp+170h+var_1F0], r15d
0x180002a50  mov     rbx, [rsp+270h+phkResult]
0x180002a55  mov     [rsp+270h+var_1F8], rbx
0x180002a5a  mov     [rbp+170h+var_1F0], r15d
0x180002a5e  test    eax, eax
0x180002a60  jnz     loc_180002B3D
0x180002a66  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180002a6b  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180002a70  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180002a75  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180002a7a  mov     [rsp+270h+lpcValues], r15; lpcValues
0x180002a7f  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180002a84  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180002a89  lea     rax, [rsp+270h+cSubKeys]
0x180002a8e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x180002a93  xor     r9d, r9d; lpReserved
0x180002a96  xor     r8d, r8d; lpcchClass
0x180002a99  xor     edx, edx; lpClass
0x180002a9b  mov     rcx, rbx; hKey
0x180002a9e  call    cs:__imp_RegQueryInfoKeyW
0x180002aa4  movsxd  rdi, eax
0x180002aa7  test    rbx, rbx
0x180002aaa  jz      short loc_180002ABD
0x180002aac  mov     rcx, rbx; hKey
0x180002aaf  call    cs:__imp_RegCloseKey
0x180002ab5  mov     rbx, r15
0x180002ab8  mov     [rsp+270h+var_1F8], rbx
0x180002abd  mov     [rbp+170h+var_1F0], r15d
0x180002ac1  test    rdi, rdi
0x180002ac4  jnz     short loc_180002B3D
0x180002ac6  cmp     [rsp+270h+cSubKeys], r15d
0x180002acb  jnz     short loc_180002B3D
0x180002acd  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, r15b; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x180002ad4  jnz     short loc_180002B11
0x180002ad6  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x180002add  call    cs:__imp_GetModuleHandleW
0x180002ae3  test    rax, rax
0x180002ae6  jz      short loc_180002B01
0x180002ae8  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
  ... truncated ...
```
