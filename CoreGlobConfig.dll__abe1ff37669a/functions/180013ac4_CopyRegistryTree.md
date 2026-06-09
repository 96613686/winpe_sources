# CopyRegistryTree

- ea: `0x180013ac4`
- end: `0x180014028`
- name: `CopyRegistryTree`
- size: `1380`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180013ac4`
- `0x18001f0b0`
- `0x180020490`

## callees

- `0x180006cbc`
- `0x180008294`
- `0x1800087e4`
- `0x180008870`
- `0x180011428`
- `0x180013ac4`
- `0x180014030`
- `0x180018c10`
- `0x18001ebcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013c29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013e02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013c29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013e02`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013b7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013c3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013d65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013e16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013b7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013c3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013d65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013e16`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013c99`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013c99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013cca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013cca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013d1f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013d1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013b43`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013b43`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013bc2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013bc2`

## string_xrefs

- `0x180013bee`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180013ee1`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180013f07`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180013f4b`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180013f75`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180013ffa`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall CopyRegistryTree(HKEY a1, const unsigned __int16 *a2, HKEY a3, const unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // r14
  DWORD v8; // esi
  unsigned int v9; // eax
  unsigned int v10; // r8d
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v14; // rdi
  unsigned int v15; // eax
  unsigned int v16; // r8d
  int v17; // eax
  int v18; // ebx
  void *v19; // rdx
  wil::details *v20; // rcx
  DWORD v21; // ebx
  HANDLE v22; // rax
  WCHAR *v23; // rsi
  void *v24; // rdx
  DWORD i; // r15d
  unsigned int v26; // eax
  unsigned int v27; // r8d
  __int64 v28; // rcx
  __int64 v29; // rax
  DWORD v30; // ebx
  HANDLE v31; // rax
  unsigned __int16 *v32; // rdi
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rcx
  DWORD v37; // ebx
  HANDLE v38; // rax
  unsigned __int16 *v39; // rbx
  __int64 v40; // rax
  int v41; // r14d
  void *v42; // rdx
  void *v43; // rdx
  __int64 v44; // rdx
  void *v45; // rdx
  __int64 v46; // rdx
  void *v47; // rdx
  void *v48; // rdx
  __int64 v49; // rdx
  void *v50; // rdx
  __int64 v51; // rdx
  unsigned int lpcSubKeys; // [rsp+28h] [rbp-69h]
  unsigned int lpcSubKeysa; // [rsp+28h] [rbp-69h]
  DWORD cchValueName; // [rsp+68h] [rbp-29h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+6Ch] [rbp-25h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-21h] BYREF
  DWORD cValues; // [rsp+74h] [rbp-1Dh] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-9h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp-1h] BYREF
  WCHAR *v62; // [rsp+98h] [rbp+7h]
  unsigned __int16 *v63; // [rsp+A0h] [rbp+Fh]
  unsigned __int16 *v64; // [rsp+A8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v4 = a4;
  v8 = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cSubKeys = 0;
  cValues = 0;
  v9 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v9 )
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)0x10F, v10, (const char *)v9, lpcSubKeys);
  v12 = ++cbMaxValueNameLen;
  ProcessHeap = GetProcessHeap();
  v14 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * v12);
  if ( v14 )
  {
    while ( v8 < cValues )
    {
      cchValueName = cbMaxValueNameLen;
      v15 = RegEnumValueW(a1, v8, v14, &cchValueName, 0, 0, 0, 0);
      if ( v15 )
      {
        v18 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x119, v16, (const char *)v15, lpcSubKeys);
LABEL_10:
        v20 = (wil::details *)v14;
LABEL_11:
        wil::details::FreeProcessHeap(v20, v19);
        return v18;
      }
      v17 = CopyValue(a1, v14, a3, v14);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11A,
          (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
          (const char *)(unsigned int)v17,
          lpcSubKeys);
        goto LABEL_10;
      }
      ++v8;
    }
    v21 = ++cbMaxSubKeyLen;
    v22 = GetProcessHeap();
    v23 = (WCHAR *)HeapAlloc(v22, 8u, 2LL * v21);
    v62 = v23;
    wil::details::FreeProcessHeap((wil::details *)v14, v24);
    if ( !v23 )
    {
      v51 = 287;
      goto LABEL_63;
    }
    hKey = 0;
    phkResult = 0;
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchValueName = cbMaxSubKeyLen;
      v26 = RegEnumKeyExW(a1, i, v23, &cchValueName, 0, 0, 0, 0);
      if ( v26 )
      {
        v49 = 295;
        goto LABEL_58;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v26 = RegOpenKeyExW(a1, v23, 0, 0x20019u, &hKey);
      if ( v26 != 5 )
      {
        if ( v26 )
        {
          v49 = 304;
          goto LABEL_58;
        }
        dwDisposition = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &phkResult,
          0);
        v26 = RegCreateKeyExW(a3, v23, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
        if ( v26 )
        {
          v49 = 316;
LABEL_58:
          v18 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v49, v27, (const char *)v26, lpcSubKeysa);
          goto LABEL_59;
        }
        v28 = -1;
        do
          ++v28;
        while ( a2[v28] );
        v29 = -1;
        do
          ++v29;
        while ( v23[v29] );
        v30 = v28 + v29 + 3;
        cchValueName = v30;
        v31 = GetProcessHeap();
        v32 = (unsigned __int16 *)HeapAlloc(v31, 8u, 2LL * v30);
        v63 = v32;
        if ( !v32 )
        {
          v18 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x141,
            (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
            (const char *)0x8007000ELL,
            lpcSubKeysa);
          goto LABEL_59;
        }
        v33 = -1;
        do
          ++v33;
        while ( a2[v33] );
        if ( v33 )
        {
          v34 = StringCchCopyW(v32, cchValueName, a2);
          v18 = v34;
          if ( v34 < 0 )
          {
            v44 = 325;
            goto LABEL_45;
          }
          v34 = StringCchCatW(v32, cchValueName, L"\\");
          v18 = v34;
          if ( v34 < 0 )
          {
            v44 = 326;
LABEL_45:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v44,
              (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
              (const char *)(unsigned int)v34,
              lpcSubKeysa);
            goto LABEL_46;
          }
        }
        v34 = StringCchCatW(v32, cchValueName, v23);
        v18 = v34;
        if ( v34 < 0 )
        {
          v44 = 329;
          goto LABEL_45;
        }
        v35 = -1;
        v36 = -1;
        do
          ++v36;
        while ( v4[v36] );
        do
          ++v35;
        while ( v23[v35] );
        v37 = v36 + v35 + 3;
        cchValueName = v37;
        v38 = GetProcessHeap();
        v39 = (unsigned __int16 *)HeapAlloc(v38, 8u, 2LL * v37);
        v64 = v39;
        if ( !v39 )
        {
          v18 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14E,
            (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
            (const char *)0x8007000ELL,
            lpcSubKeysa);
LABEL_46:
          wil::details::FreeProcessHeap((wil::details *)v32, v45);
LABEL_59:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          v20 = (wil::details *)v23;
          goto LABEL_11;
        }
        v40 = -1;
        do
          ++v40;
        while ( v4[v40] );
        if ( v40 )
        {
          v41 = StringCchCopyW(v39, cchValueName, v4);
          if ( v41 < 0 )
          {
            v46 = 338;
            goto LABEL_49;
          }
          v41 = StringCchCatW(v39, cchValueName, L"\\");
          if ( v41 < 0 )
          {
            v46 = 339;
LABEL_49:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v46,
              (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
              (const char *)(unsigned int)v41,
              lpcSubKeysa);
            wil::details::FreeProcessHeap((wil::details *)v39, v47);
            wil::details::FreeProcessHeap((wil::details *)v32, v48);
            v18 = v41;
            goto LABEL_59;
          }
        }
        v41 = StringCchCatW(v39, cchValueName, v23);
        if ( v41 < 0 )
        {
          v46 = 342;
          goto LABEL_49;
        }
        v41 = CopyRegistryTree(hKey, v32, phkResult, v39);
        if ( v41 < 0 )
        {
          v46 = 349;
          goto LABEL_49;
        }
        wil::details::FreeProcessHeap((wil::details *)v39, v42);
        wil::details::FreeProcessHeap((wil::details *)v32, v43);
        v4 = a4;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::FreeProcessHeap((wil::details *)v23, v50);
    return 0;
  }
  else
  {
    v51 = 276;
LABEL_63:
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v51,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)0x8007000ELL,
      lpcSubKeys);
    return v18;
  }
}

```

## disassembly

```asm
0x180013ac4  mov     rax, rsp
0x180013ac7  mov     [rax+8], rbx
0x180013acb  mov     [rax+20h], r9
0x180013acf  mov     [rax+18h], r8
0x180013ad3  push    rbp
0x180013ad4  push    rsi
0x180013ad5  push    rdi
0x180013ad6  push    r12
0x180013ad8  push    r13
0x180013ada  push    r14
0x180013adc  push    r15
0x180013ade  lea     rbp, [rax-5Fh]
0x180013ae2  sub     rsp, 0B0h
0x180013ae9  mov     r14, r9
0x180013aec  mov     r15, r8
0x180013aef  mov     r13, rdx
0x180013af2  mov     r12, rcx
0x180013af5  xor     esi, esi
0x180013af7  mov     [rbp+57h+cbMaxSubKeyLen], esi
0x180013afa  mov     [rbp+57h+cbMaxValueNameLen], esi
0x180013afd  mov     [rbp+57h+cSubKeys], esi
0x180013b00  mov     [rbp+57h+cValues], esi
0x180013b03  mov     [rsp+58h], rsi; lpftLastWriteTime
0x180013b08  mov     [rsp+0E0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180013b0d  mov     [rsp+0E0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180013b12  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180013b16  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180013b1b  lea     rax, [rbp+57h+cValues]
0x180013b1f  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x180013b24  mov     [rsp+0E0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180013b29  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180013b2d  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180013b32  lea     rax, [rbp+57h+cSubKeys]
0x180013b36  mov     [rsp+0E0h+lpcSubKeys], rax; int
0x180013b3b  xor     r9d, r9d; lpReserved
0x180013b3e  xor     r8d, r8d; lpcchClass
0x180013b41  xor     edx, edx; lpClass
0x180013b43  call    cs:__imp_RegQueryInfoKeyW
0x180013b49  test    eax, eax
0x180013b4b  jz      short loc_180013B63
0x180013b4d  mov     rcx, [rbp+5Fh]; this
0x180013b51  mov     r9d, eax; char *
0x180013b54  mov     edx, 10Fh; void *
0x180013b59  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013b5e  jmp     loc_18001400D
0x180013b63  mov     ebx, [rbp+57h+cbMaxValueNameLen]
0x180013b66  inc     ebx
0x180013b68  mov     [rbp+57h+cbMaxValueNameLen], ebx
0x180013b6b  call    cs:__imp_GetProcessHeap
0x180013b71  mov     r8d, ebx
0x180013b74  add     r8, r8; dwBytes
0x180013b77  mov     edx, 8; dwFlags
0x180013b7c  mov     rcx, rax; hHeap
0x180013b7f  call    cs:__imp_HeapAlloc
0x180013b85  mov     rdi, rax
0x180013b88  test    rax, rax
0x180013b8b  jz      loc_180013FED
0x180013b91  cmp     esi, [rbp+57h+cValues]
0x180013b94  jnb     loc_180013C21
0x180013b9a  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x180013b9d  mov     [rbp+57h+cchValueName], ecx
0x180013ba0  xor     ebx, ebx
0x180013ba2  mov     [rsp+0E0h+lpcValues], rbx; lpcbData
0x180013ba7  mov     [rsp+0E0h+lpcbMaxClassLen], rbx; lpData
0x180013bac  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rbx; lpType
0x180013bb1  mov     [rsp+0E0h+lpcSubKeys], rbx; unsigned int
0x180013bb6  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180013bba  mov     r8, rdi; lpValueName
0x180013bbd  mov     edx, esi; dwIndex
0x180013bbf  mov     rcx, r12; hKey
0x180013bc2  call    cs:__imp_RegEnumValueW
0x180013bc8  test    eax, eax
0x180013bca  jnz     short loc_180013C01
0x180013bcc  mov     r9, rdi; LPCWSTR
0x180013bcf  mov     r8, r15; HKEY
0x180013bd2  mov     rdx, rdi; lpValueName
0x180013bd5  mov     rcx, r12; hKey
0x180013bd8  call    CopyValue
0x180013bdd  mov     ebx, eax
0x180013bdf  test    eax, eax
0x180013be1  js      short loc_180013BE7
0x180013be3  inc     esi
0x180013be5  jmp     short loc_180013B91
0x180013be7  mov     rcx, [rbp+5Fh]; this
0x180013beb  mov     r9d, eax; char *
0x180013bee  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180013bf5  mov     edx, 11Ah; void *
0x180013bfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013bff  jmp     short loc_180013C14
0x180013c01  mov     rcx, [rbp+5Fh]; this
0x180013c05  mov     r9d, eax; char *
0x180013c08  mov     edx, 119h; void *
0x180013c0d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013c12  mov     ebx, eax
0x180013c14  mov     rcx, rdi; this
0x180013c17  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180013c1c  jmp     loc_18001400B
0x180013c21  mov     ebx, [rbp+57h+cbMaxSubKeyLen]
0x180013c24  inc     ebx
0x180013c26  mov     [rbp+57h+cbMaxSubKeyLen], ebx
0x180013c29  call    cs:__imp_GetProcessHeap
0x180013c2f  mov     r8d, ebx
0x180013c32  add     r8, r8; dwBytes
0x180013c35  mov     edx, 8; dwFlags
0x180013c3a  mov     rcx, rax; hHeap
0x180013c3d  call    cs:__imp_HeapAlloc
0x180013c43  mov     rsi, rax
0x180013c46  mov     [rbp+57h+var_50], rax
0x180013c4a  mov     rcx, rdi; this
0x180013c4d  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180013c52  xor     ebx, ebx
0x180013c54  test    rsi, rsi
0x180013c57  jz      loc_180013FE6
0x180013c5d  mov     [rbp+57h+hKey], rbx
0x180013c61  mov     [rbp+57h+phkResult], rbx
0x180013c65  mov     r15d, ebx
0x180013c68  cmp     r15d, [rbp+57h+cSubKeys]
0x180013c6c  jnb     loc_180013FC6
0x180013c72  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180013c75  mov     [rbp+57h+cchValueName], eax
0x180013c78  mov     [rsp+0E0h+lpcValues], rbx; lpftLastWriteTime
0x180013c7d  mov     [rsp+0E0h+lpcbMaxClassLen], rbx; lpcchClass
0x180013c82  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rbx; lpClass
0x180013c87  mov     [rsp+0E0h+lpcSubKeys], rbx; unsigned int
0x180013c8c  lea     r9, [rbp+57h+cchValueName]; lpcchName
0x180013c90  mov     r8, rsi; lpName
0x180013c93  mov     edx, r15d; dwIndex
0x180013c96  mov     rcx, r12; hKey
0x180013c99  call    cs:__imp_RegEnumKeyExW
0x180013c9f  test    eax, eax
0x180013ca1  jnz     loc_180013F97
0x180013ca7  xor     edx, edx
0x180013ca9  lea     rcx, [rbp+57h+hKey]
0x180013cad  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013cb2  lea     rax, [rbp+57h+hKey]
0x180013cb6  mov     [rsp+0E0h+lpcSubKeys], rax; phkResult
0x180013cbb  mov     r9d, 20019h; samDesired
0x180013cc1  xor     r8d, r8d; ulOptions
0x180013cc4  mov     rdx, rsi; lpSubKey
0x180013cc7  mov     rcx, r12; hKey
0x180013cca  call    cs:__imp_RegOpenKeyExW
0x180013cd0  cmp     eax, 5
0x180013cd3  jz      loc_180013EC6
0x180013cd9  test    eax, eax
0x180013cdb  jnz     loc_180013F90
0x180013ce1  mov     [rbp+57h+dwDisposition], ebx
0x180013ce4  xor     edx, edx
0x180013ce6  lea     rcx, [rbp+57h+phkResult]
0x180013cea  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013cef  lea     rax, [rbp+57h+dwDisposition]
0x180013cf3  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x180013cf8  lea     rax, [rbp+57h+phkResult]
0x180013cfc  mov     [rsp+0E0h+lpcValues], rax; phkResult
0x180013d01  mov     [rsp+0E0h+lpcbMaxClassLen], rbx; lpSecurityAttributes
0x180013d06  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], 0F003Fh; samDesired
0x180013d0e  mov     dword ptr [rsp+0E0h+lpcSubKeys], ebx; int
0x180013d12  xor     r9d, r9d; lpClass
0x180013d15  xor     r8d, r8d; Reserved
0x180013d18  mov     rdx, rsi; lpSubKey
0x180013d1b  mov     rcx, [rbp+57h+arg_10]; hKey
0x180013d1f  call    cs:__imp_RegCreateKeyExW
0x180013d25  test    eax, eax
0x180013d27  jnz     loc_180013F89
0x180013d2d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013d31  inc     rcx
0x180013d34  cmp     [r13+rcx*2+0], bx
0x180013d3a  jnz     short loc_180013D31
0x180013d3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013d40  inc     rax
0x180013d43  cmp     [rsi+rax*2], bx
0x180013d47  jnz     short loc_180013D40
0x180013d49  lea     ebx, [rax+3]
0x180013d4c  add     ebx, ecx
0x180013d4e  mov     [rbp+57h+cchValueName], ebx
0x180013d51  call    cs:__imp_GetProcessHeap
0x180013d57  mov     r8d, ebx
0x180013d5a  add     r8, r8; dwBytes
0x180013d5d  mov     edx, 8; dwFlags
0x180013d62  mov     rcx, rax; hHeap
0x180013d65  call    cs:__imp_HeapAlloc
0x180013d6b  mov     rdi, rax
0x180013d6e  mov     [rbp+57h+var_48], rax
0x180013d72  xor     r11d, r11d
0x180013d75  test    rax, rax
0x180013d78  jz      loc_180013F69
0x180013d7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013d82  inc     rax
0x180013d85  cmp     [r13+rax*2+0], r11w
0x180013d8b  jnz     short loc_180013D82
0x180013d8d  test    rax, rax
0x180013d90  jz      short loc_180013DC6
0x180013d92  mov     edx, [rbp+57h+cchValueName]; unsigned __int64
0x180013d95  mov     r8, r13; unsigned __int16 *
0x180013d98  mov     rcx, rdi; unsigned __int16 *
0x180013d9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013da0  mov     ebx, eax
0x180013da2  test    eax, eax
0x180013da4  js      loc_180013ED5
0x180013daa  mov     edx, [rbp+57h+cchValueName]; unsigned __int64
0x180013dad  lea     r8, asc_180028050; "\\"
0x180013db4  mov     rcx, rdi; unsigned __int16 *
0x180013db7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013dbc  mov     ebx, eax
0x180013dbe  test    eax, eax
0x180013dc0  js      loc_180013ECE
0x180013dc6  mov     edx, [rbp+57h+cchValueName]; unsigned __int64
0x180013dc9  mov     r8, rsi; unsigned __int16 *
0x180013dcc  mov     rcx, rdi; unsigned __int16 *
0x180013dcf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013dd4  mov     ebx, eax
0x180013dd6  xor     edx, edx
0x180013dd8  test    eax, eax
0x180013dda  js      loc_180013F5F
0x180013de0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013de4  mov     rcx, rax
0x180013de7  inc     rcx
0x180013dea  cmp     [r14+rcx*2], dx
0x180013def  jnz     short loc_180013DE7
0x180013df1  inc     rax
0x180013df4  cmp     [rsi+rax*2], dx
0x180013df8  jnz     short loc_180013DF1
0x180013dfa  lea     ebx, [rax+3]
0x180013dfd  add     ebx, ecx
0x180013dff  mov     [rbp+57h+cchValueName], ebx
0x180013e02  call    cs:__imp_GetProcessHeap
0x180013e08  mov     r8d, ebx
0x180013e0b  add     r8, r8; dwBytes
0x180013e0e  mov     edx, 8; dwFlags
0x180013e13  mov     rcx, rax; hHeap
0x180013e16  call    cs:__imp_HeapAlloc
0x180013e1c  mov     rbx, rax
0x180013e1f  mov     [rbp+57h+var_40], rax
0x180013e23  xor     r11d, r11d
0x180013e26  test    rax, rax
0x180013e29  jz      loc_180013F3F
0x180013e2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013e33  inc     rax
0x180013e36  cmp     [r14+rax*2], r11w
0x180013e3b  jnz     short loc_180013E33
0x180013e3d  test    rax, rax
0x180013e40  jz      short loc_180013E78
0x180013e42  mov     edx, [rbp+57h+cchValueName]; unsigned __int64
0x180013e45  mov     r8, r14; unsigned __int16 *
0x180013e48  mov     rcx, rbx; unsigned __int16 *
0x180013e4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013e50  mov     r14d, eax
0x180013e53  test    eax, eax
0x180013e55  js      loc_180013F02
0x180013e5b  mov     edx, [rbp+57h+cchValueName]; unsigned __int64
0x180013e5e  lea     r8, asc_180028050; "\\"
0x180013e65  mov     rcx, rbx; unsigned __int16 *
0x180013e68  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013e6d  mov     r14d, eax
0x180013e70  test    eax, eax
0x180013e72  js      loc_180013EFB
0x180013e78  mov     edx, [rbp+57h+cchValueName]; unsigned __int64
0x180013e7b  mov     r8, rsi; unsigned __int16 *
0x180013e7e  mov     rcx, rbx; unsigned __int16 *
0x180013e81  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013e86  mov     r14d, eax
0x180013e89  test    eax, eax
0x180013e8b  js      loc_180013F38
0x180013e91  mov     r9, rbx
0x180013e94  mov     r8, [rbp+57h+phkResult]
0x180013e98  mov     rdx, rdi
0x180013e9b  mov     rcx, [rbp+57h+hKey]
0x180013e9f  call    CopyRegistryTree
0x180013ea4  mov     r14d, eax
0x180013ea7  test    eax, eax
0x180013ea9  js      loc_180013F31
0x180013eaf  mov     rcx, rbx; this
0x180013eb2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180013eb7  nop
0x180013eb8  mov     rcx, rdi; this
0x180013ebb  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180013ec0  mov     r14, [rbp+57h+arg_18]
0x180013ec4  xor     ebx, ebx
0x180013ec6  inc     r15d
0x180013ec9  jmp     loc_180013C68
0x180013ece  mov     edx, 146h
0x180013ed3  jmp     short loc_180013EDA
0x180013ed5  mov     edx, 145h; void *
0x180013eda  mov     rcx, [rbp+5Fh]; this
0x180013ede  mov     r9d, eax; char *
0x180013ee1  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180013ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013eed  nop
0x180013eee  mov     rcx, rdi; this
0x180013ef1  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180013ef6  jmp     loc_180013FAA
0x180013efb  mov     edx, 153h
0x180013f00  jmp     short loc_180013F07
0x180013f02  mov     edx, 152h; void *
0x180013f07  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180013f0e  mov     r9d, r14d; char *
0x180013f11  mov     rcx, [rbp+5Fh]; this
0x180013f15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f1a  nop
0x180013f1b  mov     rcx, rbx; this
0x180013f1e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
  ... truncated ...
```
