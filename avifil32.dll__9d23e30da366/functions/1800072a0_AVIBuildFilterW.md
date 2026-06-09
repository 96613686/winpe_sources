# AVIBuildFilterW

- ea: `0x1800072a0`
- end: `0x180007864`
- name: `AVIBuildFilterW`
- size: `1476`
- prototype: `HRESULT __stdcall(LPWSTR lpszFilter, LONG cbFilter, BOOL fSaving)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800071a0`

## callees

- `0x180001460`
- `0x1800014a0`
- `0x18000703c`
- `0x1800070ec`
- `0x1800072a0`
- `0x180017359`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180007387`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800077a9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000781a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180007387`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800077a9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000781a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180007346`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180007346`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000737e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180007390`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800077a0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800077b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180007811`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180007823`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000737e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180007390`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800077a0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800077b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180007811`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180007823`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007463`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007463`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180007655`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000769d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800076aa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800076d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180007770`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180007788`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180007655`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000769d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800076aa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800076d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180007770`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180007788`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000733d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000733d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007399`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800077bb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000782c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007399`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800077bb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000782c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800072ff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800072ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007601`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800077c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007802`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007601`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800077c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007802`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180007371`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000761a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180007371`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000761a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18000740b`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800075e7`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18000740b`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800075e7`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x18000743a`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x18000751f`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180007688`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x18000743a`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x18000751f`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180007688`

## string_xrefs

- `0x180007613`: `Clsid`
- `0x18000736a`: `AVIFile\Extensions`

## pseudocode

```c
HRESULT __stdcall AVIBuildFilterW(LPWSTR lpszFilter, LONG cbFilter, BOOL fSaving)
{
  unsigned __int16 *v4; // r14
  int StringW; // eax
  __int64 v6; // r12
  int i; // edx
  HGLOBAL v8; // rax
  unsigned __int16 *v9; // rdi
  HGLOBAL v11; // rax
  HGLOBAL v12; // rax
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  _WORD *v16; // rax
  _WORD *v17; // rcx
  int v18; // r13d
  int v19; // r14d
  __int64 v20; // rbx
  WCHAR *p_Data; // r8
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rcx
  WCHAR v26; // dx
  int v27; // eax
  WCHAR *v28; // r8
  int v29; // ecx
  int v30; // eax
  unsigned __int64 v32; // rdx
  WCHAR *v33; // r8
  unsigned __int16 *v34; // rcx
  unsigned __int64 v35; // rdx
  WCHAR *v36; // r8
  int j; // esi
  int v38; // eax
  int v39; // ebx
  int v40; // ecx
  int v41; // eax
  int v42; // r15d
  __int64 v43; // rdx
  unsigned __int16 *v44; // r14
  __int64 v45; // r8
  unsigned __int16 *v46; // rax
  unsigned __int16 *v47; // r9
  unsigned __int16 *v48; // rcx
  __int64 v49; // rbx
  HGLOBAL v50; // rax
  HGLOBAL v51; // rax
  HGLOBAL v52; // rax
  HGLOBAL v53; // rax
  __int64 v54; // [rsp+20h] [rbp-E0h]
  LONG cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Data; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v60[254]; // [rsp+62h] [rbp-9Eh] BYREF
  WCHAR Buffer[40]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR SubKey[128]; // [rsp+1B0h] [rbp+B0h] BYREF

  LODWORD(v54) = fSaving;
  v4 = lpszFilter;
  phkResult = 0;
  cbData = 0;
  StringW = LoadStringW(ghMod, 0xB9u, Buffer, 40);
  v6 = StringW;
  for ( i = 0; i < StringW; ++i )
  {
    if ( Buffer[i] == 64 )
    {
      if ( 2 * (unsigned __int64)(unsigned int)i >= 0x50 )
        _report_rangecheckfailure();
      Buffer[i] = 0;
    }
  }
  v8 = GlobalAlloc(0x42u, 0x18000u);
  v9 = (unsigned __int16 *)GlobalLock(v8);
  if ( !v9 )
    return -2147205017;
  if ( RegOpenKeyW(HKEY_CLASSES_ROOT, L"AVIFile\\Extensions", &phkResult) )
    goto LABEL_9;
  v13 = 2147483646;
  v14 = L"{00020000-0000-0000-C000-000000000046}";
  v15 = 64;
  v16 = v9 + 192;
  do
  {
    if ( !v13 )
      break;
    if ( !*v14 )
      break;
    *v16++ = *v14++;
    --v13;
    --v15;
  }
  while ( v15 );
  HIDWORD(v54) = 0;
  v17 = v16 - 1;
  v18 = 1;
  if ( v15 )
    v17 = v16;
  *v17 = 0;
  if ( !RegEnumKeyW(phkResult, 0, Name, 0xAu) )
  {
    v19 = v54;
    while ( 1 )
    {
      cbData = 256;
      if ( RegQueryValueW(phkResult, Name, &Data, &cbData) )
      {
LABEL_47:
        v4 = lpszFilter;
        break;
      }
      LODWORD(v20) = 1;
      if ( v18 >= 1 )
      {
        do
        {
          if ( !lstrcmpW(&Data, &v9[192 * (int)v20]) )
            break;
          LODWORD(v20) = v20 + 1;
        }
        while ( (int)v20 <= v18 );
        v19 = v54;
      }
      if ( (_DWORD)v20 == v18 + 1 )
      {
        if ( v18 == 256 )
          goto LABEL_46;
        v20 = (int)v20;
        p_Data = &Data;
        v22 = 2147483646;
        v23 = 64;
        v24 = &v9[192 * (int)v20];
        do
        {
          if ( !v22 )
            break;
          if ( !*p_Data )
            break;
          *v24++ = *p_Data++;
          --v22;
          --v23;
        }
        while ( v23 );
        v25 = v24 - 1;
        if ( v23 )
          v25 = v24;
        *v25 = 0;
        cbData = 256;
        StringCchPrintfW(SubKey, 0x80u, L"%s\\AVIFile", &Data, v54);
        if ( !RegQueryValueW(phkResult, SubKey, &Data, &cbData) )
        {
          v26 = Data;
          v27 = 0;
          if ( Data )
          {
            v28 = &Data;
            do
            {
              v29 = 5 * v27;
              v30 = v26;
              v26 = *++v28;
              v27 = v30 + 2 * v29 - 48;
            }
            while ( *v28 );
          }
          if ( v19 ? (v27 & 2) == 0 : (v27 & 1) == 0 )
            goto LABEL_46;
        }
        ++v18;
      }
      else
      {
        v20 = (int)v20;
      }
      StringCchPrintfW(&Data, 0x80u, L";*.%s", Name, v54);
      v33 = (WCHAR *)v60;
      v34 = &v9[192 * v20 + 64];
      if ( *v34 )
        v33 = &Data;
      StringCchCatW(v34, v32, v33);
      v36 = (WCHAR *)v60;
      if ( v9[64] )
        v36 = &Data;
      StringCchCatW(v9 + 64, v35, v36);
LABEL_46:
      ++HIDWORD(v54);
      if ( RegEnumKeyW(phkResult, HIDWORD(v54), Name, 0xAu) )
        goto LABEL_47;
    }
  }
  RegCloseKey(phkResult);
  if ( RegOpenKeyW(HKEY_CLASSES_ROOT, L"Clsid", &phkResult) )
  {
LABEL_9:
    v11 = GlobalHandle(v9);
    GlobalUnlock(v11);
    v12 = GlobalHandle(v9);
    GlobalFree(v12);
    return -2147204921;
  }
  for ( j = 0; j <= v18; ++j )
  {
    if ( cbFilter <= 0 )
      break;
    if ( j )
    {
      cbData = 256;
      if ( RegQueryValueW(phkResult, &v9[192 * j], &Data, &cbData) )
        continue;
      v39 = lstrlenW(&v9[192 * j + 64]);
      if ( cbFilter < v39 + lstrlenW(&Data) + 10 )
        break;
      StringCchPrintfW(v4, cbFilter, L"%s", &Data);
      v38 = lstrlenW(v4);
    }
    else
    {
      StringCchPrintfW(v4, cbFilter, L"All multimedia files");
      v38 = lstrlenW(v4);
    }
    v40 = v38;
    v41 = v38 + 1;
    v42 = cbFilter - v41;
    cbData = v41;
    v43 = v42;
    v44 = &v4[v40 + 1];
    if ( v42 )
    {
      if ( (unsigned __int64)v42 > 0x7FFFFFFF )
      {
        *v44 = 0;
      }
      else
      {
        v45 = 2147483646;
        v46 = v44;
        v47 = &v9[192 * j + 64];
        do
        {
          if ( !v45 )
            break;
          if ( !*v47 )
            break;
          *v46++ = *v47++;
          --v45;
          --v43;
        }
        while ( v43 );
        v48 = v46 - 1;
        if ( v43 )
          v48 = v46;
        *v48 = 0;
      }
    }
    v49 = 192LL * j;
    cbFilter = -1 - lstrlenW(&v9[v49 + 64]) + v42;
    v4 = &v44[lstrlenW(&v9[v49 + 64]) + 1];
    if ( cbFilter <= 0 )
    {
      v50 = GlobalHandle(v9);
      GlobalUnlock(v50);
      v51 = GlobalHandle(v9);
      GlobalFree(v51);
      RegCloseKey(phkResult);
      return -2147205004;
    }
  }
  if ( cbFilter > (int)v6 )
  {
    memcpy_0(v4, Buffer, 2 * v6);
    v4 += v6;
  }
  RegCloseKey(phkResult);
  *v4 = 0;
  v52 = GlobalHandle(v9);
  GlobalUnlock(v52);
  v53 = GlobalHandle(v9);
  GlobalFree(v53);
  return 0;
}

```

## disassembly

```asm
0x1800072a0  mov     [rsp-8+arg_10], rbx
0x1800072a5  push    rbp
0x1800072a6  push    rsi
0x1800072a7  push    rdi
0x1800072a8  push    r12
0x1800072aa  push    r13
0x1800072ac  push    r14
0x1800072ae  push    r15
0x1800072b0  lea     rbp, [rsp-1C0h]
0x1800072b8  sub     rsp, 2C0h
0x1800072bf  mov     rax, cs:__security_cookie
0x1800072c6  xor     rax, rsp
0x1800072c9  mov     [rbp+1F0h+var_40], rax
0x1800072d0  xor     ebx, ebx
0x1800072d2  mov     [rsp+2F0h+var_2D0], r8d
0x1800072d7  mov     r15d, edx
0x1800072da  mov     [rsp+2F0h+var_2C8], rcx
0x1800072df  mov     r14, rcx
0x1800072e2  mov     [rsp+2F0h+phkResult], rbx
0x1800072e7  mov     rcx, cs:ghMod; hInstance
0x1800072ee  lea     r8, [rbp+1F0h+Buffer]; lpBuffer
0x1800072f2  lea     r9d, [rbx+28h]; cchBufferMax
0x1800072f6  mov     [rsp+2F0h+cbData], ebx
0x1800072fa  mov     edx, 0B9h; uID
0x1800072ff  call    cs:__imp_LoadStringW
0x180007305  movsxd  r12, eax
0x180007308  mov     edx, ebx
0x18000730a  lea     esi, [rbx+40h]
0x18000730d  test    eax, eax
0x18000730f  jle     short loc_180007333
0x180007311  mov     ecx, edx
0x180007313  add     rcx, rcx
0x180007316  cmp     [rbp+rcx+1F0h+Buffer], si
0x18000731b  jnz     short loc_18000732C
0x18000731d  cmp     rcx, 50h ; 'P'
0x180007321  jnb     loc_18000785E
0x180007327  mov     [rbp+rcx+1F0h+Buffer], bx
0x18000732c  inc     edx
0x18000732e  cmp     edx, r12d
0x180007331  jl      short loc_180007311
0x180007333  mov     edx, 18000h; dwBytes
0x180007338  mov     ecx, 42h ; 'B'; uFlags
0x18000733d  call    cs:__imp_GlobalAlloc
0x180007343  mov     rcx, rax; hMem
0x180007346  call    cs:__imp_GlobalLock
0x18000734c  mov     rdi, rax
0x18000734f  test    rax, rax
0x180007352  jnz     short loc_18000735E
0x180007354  mov     eax, 80044067h
0x180007359  jmp     loc_180007834
0x18000735e  lea     r8, [rsp+2F0h+phkResult]; phkResult
0x180007363  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000736a  lea     rdx, SubKey; "AVIFile\\Extensions"
0x180007371  call    cs:__imp_RegOpenKeyW
0x180007377  test    eax, eax
0x180007379  jz      short loc_1800073A9
0x18000737b  mov     rcx, rdi; pMem
0x18000737e  call    cs:__imp_GlobalHandle
0x180007384  mov     rcx, rax; hMem
0x180007387  call    cs:__imp_GlobalUnlock
0x18000738d  mov     rcx, rdi; pMem
0x180007390  call    cs:__imp_GlobalHandle
0x180007396  mov     rcx, rax; hMem
0x180007399  call    cs:__imp_GlobalFree
0x18000739f  mov     eax, 800440C7h
0x1800073a4  jmp     loc_180007834
0x1800073a9  mov     ecx, 7FFFFFFEh
0x1800073ae  lea     r8, a00020000000000; "{00020000-0000-0000-C000-000000000046}"
0x1800073b5  mov     rdx, rsi
0x1800073b8  lea     rax, [rdi+180h]
0x1800073bf  test    rcx, rcx
0x1800073c2  jz      short loc_1800073E3
0x1800073c4  movzx   r9d, word ptr [r8]
0x1800073c8  test    r9w, r9w
0x1800073cc  jz      short loc_1800073E3
0x1800073ce  mov     [rax], r9w
0x1800073d2  add     r8, 2
0x1800073d6  add     rax, 2
0x1800073da  dec     rcx
0x1800073dd  sub     rdx, 1
0x1800073e1  jnz     short loc_1800073BF
0x1800073e3  test    rdx, rdx
0x1800073e6  mov     [rsp+2F0h+var_2CC], ebx
0x1800073ea  lea     rcx, [rax-2]
0x1800073ee  mov     r13d, 1
0x1800073f4  cmovnz  rcx, rax
0x1800073f8  lea     r8, [rsp+2F0h+Name]; lpName
0x1800073fd  xor     edx, edx; dwIndex
0x1800073ff  lea     r9d, [r13+9]; cchName
0x180007403  mov     [rcx], bx
0x180007406  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x18000740b  call    cs:__imp_RegEnumKeyW
0x180007411  test    eax, eax
0x180007413  jnz     loc_1800075FC
0x180007419  mov     r14d, [rsp+2F0h+var_2D0]
0x18000741e  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180007423  lea     r9, [rsp+2F0h+cbData]; lpcbData
0x180007428  lea     r8, [rsp+2F0h+Data]; lpData
0x18000742d  mov     [rsp+2F0h+cbData], 100h
0x180007435  lea     rdx, [rsp+2F0h+Name]; lpSubKey
0x18000743a  call    cs:__imp_RegQueryValueW
0x180007440  test    eax, eax
0x180007442  jnz     loc_1800075F7
0x180007448  lea     ebx, [rax+1]
0x18000744b  cmp     r13d, ebx
0x18000744e  jl      short loc_180007479
0x180007450  movsxd  rax, ebx
0x180007453  lea     rcx, [rsp+2F0h+Data]; lpString1
0x180007458  lea     rdx, [rax+rax*2]
0x18000745c  shl     rdx, 7
0x180007460  add     rdx, rdi; lpString2
0x180007463  call    cs:__imp_lstrcmpW
0x180007469  test    eax, eax
0x18000746b  jz      short loc_180007474
0x18000746d  inc     ebx
0x18000746f  cmp     ebx, r13d
0x180007472  jle     short loc_180007450
0x180007474  mov     r14d, [rsp+2F0h+var_2D0]
0x180007479  lea     esi, [r13+1]
0x18000747d  cmp     ebx, esi
0x18000747f  jnz     loc_180007569
0x180007485  mov     r11d, 100h
0x18000748b  cmp     r13d, r11d
0x18000748e  jz      loc_1800075CB
0x180007494  movsxd  rbx, ebx
0x180007497  lea     r8, [rsp+2F0h+Data]
0x18000749c  mov     ecx, 7FFFFFFEh
0x1800074a1  mov     edx, 40h ; '@'
0x1800074a6  lea     rax, [rbx+rbx*2]
0x1800074aa  shl     rax, 7
0x1800074ae  add     rax, rdi
0x1800074b1  xor     r10d, r10d
0x1800074b4  test    rcx, rcx
0x1800074b7  jz      short loc_1800074D8
0x1800074b9  movzx   r9d, word ptr [r8]
0x1800074bd  test    r9w, r9w
0x1800074c1  jz      short loc_1800074D8
0x1800074c3  mov     [rax], r9w
0x1800074c7  add     r8, 2
0x1800074cb  add     rax, 2
0x1800074cf  dec     rcx
0x1800074d2  sub     rdx, 1
0x1800074d6  jnz     short loc_1800074B4
0x1800074d8  test    rdx, rdx
0x1800074db  lea     rcx, [rax-2]
0x1800074df  lea     r9, [rsp+2F0h+Data]
0x1800074e4  mov     edx, 80h; unsigned __int64
0x1800074e9  cmovnz  rcx, rax
0x1800074ed  lea     r8, aSAvifile; "%s\\AVIFile"
0x1800074f4  mov     [rcx], r10w
0x1800074f8  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x1800074ff  mov     [rsp+2F0h+cbData], r11d
0x180007504  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007509  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x18000750e  lea     r9, [rsp+2F0h+cbData]; lpcbData
0x180007513  lea     r8, [rsp+2F0h+Data]; lpData
0x180007518  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18000751f  call    cs:__imp_RegQueryValueW
0x180007525  xor     r9d, r9d
0x180007528  test    eax, eax
0x18000752a  jnz     short loc_180007564
0x18000752c  movzx   edx, [rsp+2F0h+Data]
0x180007531  mov     eax, r9d
0x180007534  test    dx, dx
0x180007537  jz      short loc_180007557
0x180007539  lea     r8, [rsp+2F0h+Data]
0x18000753e  lea     ecx, [rax+rax*4]
0x180007541  movzx   eax, dx
0x180007544  lea     r8, [r8+2]
0x180007548  movzx   edx, word ptr [r8]
0x18000754c  lea     eax, [rax+rcx*2]
0x18000754f  add     eax, 0FFFFFFD0h
0x180007552  test    dx, dx
0x180007555  jnz     short loc_18000753E
0x180007557  test    r14d, r14d
0x18000755a  jz      short loc_180007560
0x18000755c  test    al, 2
0x18000755e  jmp     short loc_180007562
0x180007560  test    al, 1
0x180007562  jz      short loc_1800075CB
0x180007564  mov     r13d, esi
0x180007567  jmp     short loc_18000756C
0x180007569  movsxd  rbx, ebx
0x18000756c  lea     r9, [rsp+2F0h+Name]
0x180007571  mov     edx, 80h; unsigned __int64
0x180007576  lea     r8, aS_0; ";*.%s"
0x18000757d  lea     rcx, [rsp+2F0h+Data]; unsigned __int16 *
0x180007582  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007587  lea     rcx, [rbx+rbx*2]
0x18000758b  xor     ebx, ebx
0x18000758d  shl     rcx, 7
0x180007591  lea     rax, [rsp+2F0h+Data]
0x180007596  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18000759a  lea     r8, [rsp+2F0h+var_28E]
0x18000759f  add     rcx, rdi; unsigned __int16 *
0x1800075a2  cmp     [rcx], bx
0x1800075a5  cmovnz  r8, rax; unsigned __int16 *
0x1800075a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800075ae  lea     rcx, [rdi+80h]; unsigned __int16 *
0x1800075b5  cmp     [rcx], bx
0x1800075b8  lea     rax, [rsp+2F0h+Data]
0x1800075bd  lea     r8, [rsp+2F0h+var_28E]
0x1800075c2  cmovnz  r8, rax; unsigned __int16 *
0x1800075c6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800075cb  mov     ebx, [rsp+2F0h+var_2CC]
0x1800075cf  lea     r8, [rsp+2F0h+Name]; lpName
0x1800075d4  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x1800075d9  inc     ebx
0x1800075db  mov     edx, ebx; dwIndex
0x1800075dd  mov     [rsp+2F0h+var_2CC], ebx
0x1800075e1  mov     r9d, 0Ah; cchName
0x1800075e7  call    cs:__imp_RegEnumKeyW
0x1800075ed  xor     ebx, ebx
0x1800075ef  test    eax, eax
0x1800075f1  jz      loc_18000741E
0x1800075f7  mov     r14, [rsp+2F0h+var_2C8]
0x1800075fc  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180007601  call    cs:__imp_RegCloseKey
0x180007607  lea     r8, [rsp+2F0h+phkResult]; phkResult
0x18000760c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007613  lea     rdx, aClsid; "Clsid"
0x18000761a  call    cs:__imp_RegOpenKeyW
0x180007620  test    eax, eax
0x180007622  jnz     loc_18000737B
0x180007628  mov     esi, ebx
0x18000762a  test    r13d, r13d
0x18000762d  js      loc_1800077E0
0x180007633  test    r15d, r15d
0x180007636  jle     loc_1800077E0
0x18000763c  test    esi, esi
0x18000763e  jnz     short loc_180007660
0x180007640  movsxd  rdx, r15d; unsigned __int64
0x180007643  lea     r8, aAllMultimediaF; "All multimedia files"
0x18000764a  mov     rcx, r14; unsigned __int16 *
0x18000764d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007652  mov     rcx, r14; lpString
0x180007655  call    cs:__imp_lstrlenW
0x18000765b  jmp     loc_1800076E0
0x180007660  mov     rcx, [rsp+2F0h+phkResult]; hKey
0x180007665  lea     r9, [rsp+2F0h+cbData]; lpcbData
0x18000766a  movsxd  rax, esi
0x18000766d  lea     r8, [rsp+2F0h+Data]; lpData
0x180007672  mov     [rsp+2F0h+cbData], 100h
0x18000767a  lea     rbx, [rax+rax*2]
0x18000767e  shl     rbx, 7
0x180007682  add     rbx, rdi
0x180007685  mov     rdx, rbx; lpSubKey
0x180007688  call    cs:__imp_RegQueryValueW
0x18000768e  test    eax, eax
0x180007690  jnz     loc_1800077D3
0x180007696  lea     rcx, [rbx+80h]; lpString
0x18000769d  call    cs:__imp_lstrlenW
0x1800076a3  lea     rcx, [rsp+2F0h+Data]; lpString
0x1800076a8  mov     ebx, eax
0x1800076aa  call    cs:__imp_lstrlenW
0x1800076b0  lea     ecx, [rax+0Ah]
0x1800076b3  add     ecx, ebx
0x1800076b5  cmp     r15d, ecx
0x1800076b8  jl      loc_1800077E0
0x1800076be  movsxd  rdx, r15d; unsigned __int64
0x1800076c1  lea     r9, [rsp+2F0h+Data]
0x1800076c6  lea     r8, aS; "%s"
0x1800076cd  mov     rcx, r14; unsigned __int16 *
0x1800076d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800076d5  mov     rcx, r14; lpString
0x1800076d8  call    cs:__imp_lstrlenW
0x1800076de  xor     ebx, ebx
0x1800076e0  mov     ecx, eax
0x1800076e2  lea     eax, [rax+1]
0x1800076e5  sub     r15d, eax
0x1800076e8  mov     [rsp+2F0h+cbData], eax
0x1800076ec  movsxd  rax, ecx
0x1800076ef  movsxd  rdx, r15d
0x1800076f2  lea     r14, [r14+rax*2]
0x1800076f6  lea     r14, [r14+2]
0x1800076fa  jz      short loc_180007752
0x1800076fc  cmp     rdx, 7FFFFFFFh
0x180007703  ja      short loc_180007757
0x180007705  movsxd  rax, esi
0x180007708  mov     r8d, 7FFFFFFEh
0x18000770e  lea     r9, [rax+rax*2]
0x180007712  mov     rax, r14
0x180007715  shl     r9, 7
0x180007719  sub     r9, 0FFFFFFFFFFFFFF80h
0x18000771d  add     r9, rdi
0x180007720  test    r8, r8
0x180007723  jz      short loc_180007742
0x180007725  movzx   ecx, word ptr [r9]
0x180007729  test    cx, cx
0x18000772c  jz      short loc_180007742
0x18000772e  mov     [rax], cx
0x180007731  add     r9, 2
0x180007735  add     rax, 2
0x180007739  dec     r8
0x18000773c  sub     rdx, 1
0x180007740  jnz     short loc_180007720
0x180007742  test    rdx, rdx
0x180007745  lea     rcx, [rax-2]
0x180007749  cmovnz  rcx, rax
0x18000774d  mov     [rcx], bx
  ... truncated ...
```
