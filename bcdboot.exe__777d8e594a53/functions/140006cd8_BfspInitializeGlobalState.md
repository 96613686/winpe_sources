# BfspInitializeGlobalState

- ea: `0x140006cd8`
- end: `0x1400074ee`
- name: `BfspInitializeGlobalState`
- size: `2070`
- prototype: `__int64 __fastcall(char *Src, int, void *, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, loader_planting`

## callers

- `0x140003d30`
- `0x140004080`

## callees

- `0x140001738`
- `0x140002c14`
- `0x140002f14`
- `0x14000636c`
- `0x140006cd8`
- `0x14000c7bc`
- `0x14000e628`
- `0x1400127a4`
- `0x140017830`
- `0x140026010`
- `0x1400265e2`
- `0x1400265fa`
- `0x140026650`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x140006f2c`
- `msvcrt!wcscpy_s` at `0x14000701d`
- `msvcrt!wcscpy_s` at `0x140006f2c`
- `msvcrt!wcscpy_s` at `0x14000701d`
- `msvcrt!swprintf_s` at `0x14000739b`
- `msvcrt!swprintf_s` at `0x1400073c5`
- `msvcrt!swprintf_s` at `0x14000739b`
- `msvcrt!swprintf_s` at `0x1400073c5`
- `msvcrt!_wcsnicmp` at `0x140006f8e`
- `msvcrt!_wcsnicmp` at `0x140006fd2`
- `msvcrt!_wcsnicmp` at `0x1400071f8`
- `msvcrt!_wcsnicmp` at `0x140006f8e`
- `msvcrt!_wcsnicmp` at `0x140006fd2`
- `msvcrt!_wcsnicmp` at `0x1400071f8`
- `msvcrt!wcschr` at `0x140007209`
- `msvcrt!wcschr` at `0x140007209`
- `KERNEL32!GetLastError` at `0x140006e22`
- `KERNEL32!GetLastError` at `0x140006ed2`
- `KERNEL32!GetLastError` at `0x140006f02`
- `KERNEL32!GetLastError` at `0x14000742c`
- `KERNEL32!GetLastError` at `0x140006e22`
- `KERNEL32!GetLastError` at `0x140006ed2`
- `KERNEL32!GetLastError` at `0x140006f02`
- `KERNEL32!GetLastError` at `0x14000742c`
- `KERNEL32!HeapAlloc` at `0x140006dbe`
- `KERNEL32!HeapAlloc` at `0x140007068`
- `KERNEL32!HeapAlloc` at `0x1400070c8`
- `KERNEL32!HeapAlloc` at `0x14000715f`
- `KERNEL32!HeapAlloc` at `0x1400072bc`
- `KERNEL32!HeapAlloc` at `0x140007325`
- `KERNEL32!HeapAlloc` at `0x140007482`
- `KERNEL32!HeapAlloc` at `0x140006dbe`
- `KERNEL32!HeapAlloc` at `0x140007068`
- `KERNEL32!HeapAlloc` at `0x1400070c8`
- `KERNEL32!HeapAlloc` at `0x14000715f`
- `KERNEL32!HeapAlloc` at `0x1400072bc`
- `KERNEL32!HeapAlloc` at `0x140007325`
- `KERNEL32!HeapAlloc` at `0x140007482`
- `KERNEL32!GetProcessHeap` at `0x140006dad`
- `KERNEL32!GetProcessHeap` at `0x140007057`
- `KERNEL32!GetProcessHeap` at `0x1400070b7`
- `KERNEL32!GetProcessHeap` at `0x14000714e`
- `KERNEL32!GetProcessHeap` at `0x1400072ab`
- `KERNEL32!GetProcessHeap` at `0x140007314`
- `KERNEL32!GetProcessHeap` at `0x140007471`
- `KERNEL32!GetProcessHeap` at `0x140006dad`
- `KERNEL32!GetProcessHeap` at `0x140007057`
- `KERNEL32!GetProcessHeap` at `0x1400070b7`
- `KERNEL32!GetProcessHeap` at `0x14000714e`
- `KERNEL32!GetProcessHeap` at `0x1400072ab`
- `KERNEL32!GetProcessHeap` at `0x140007314`
- `KERNEL32!GetProcessHeap` at `0x140007471`
- `KERNEL32!QueryDosDeviceW` at `0x140006ec4`
- `KERNEL32!QueryDosDeviceW` at `0x140006ec4`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140006ef8`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140006ef8`
- `KERNEL32!LoadLibraryExW` at `0x140007415`
- `KERNEL32!LoadLibraryExW` at `0x140007415`
- `KERNEL32!GetVolumePathNameW` at `0x140006e15`
- `KERNEL32!GetVolumePathNameW` at `0x140006fed`
- `KERNEL32!GetVolumePathNameW` at `0x140006e15`
- `KERNEL32!GetVolumePathNameW` at `0x140006fed`
- `SHLWAPI!PathRemoveBackslashW` at `0x140007008`
- `SHLWAPI!PathRemoveBackslashW` at `0x140007008`
- `SHLWAPI!PathIsPrefixW` at `0x140006d7c`
- `SHLWAPI!PathIsPrefixW` at `0x140006d7c`
- `ntdll!RtlFreeHeap` at `0x14000726e`
- `ntdll!RtlFreeHeap` at `0x140007286`
- `ntdll!RtlFreeHeap` at `0x14000726e`
- `ntdll!RtlFreeHeap` at `0x140007286`
- `ntdll!RtlInitUnicodeString` at `0x1400071cc`
- `ntdll!RtlInitUnicodeString` at `0x140007224`
- `ntdll!RtlInitUnicodeString` at `0x1400071cc`
- `ntdll!RtlInitUnicodeString` at `0x140007224`

## string_xrefs

- `0x140006e2b`: `Failed to GetVolumePathName for %ws (%u).`
- `0x140006e53`: `VolumePathName for %ws is %ws`
- `0x140006e96`: `Invalid VolumePathNameLegth %ws`
- `0x140006f0f`: `Unable to GetVolumeNameForVolumeMountPoint %ws (%u).`
- `0x1400070f8`: `Expected provided path "%ws" to start with %ws`
- `0x140007367`: `\System32\bootstr.dll`

## pseudocode

```c
__int64 __fastcall BfspInitializeGlobalState(char *Src, int a2, void *a3, __int64 a4)
{
  const wchar_t *v5; // rsi
  const WCHAR *v8; // rdi
  char v9; // r12
  __int64 v10; // r15
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rax
  SIZE_T v14; // rdi
  HANDLE ProcessHeap; // rax
  void *v16; // rax
  DWORD LastError; // eax
  unsigned int v18; // ebx
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rax
  DWORD v21; // eax
  DWORD v22; // eax
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  SIZE_T v28; // rdi
  HANDLE v29; // rax
  WCHAR *v30; // rax
  __int64 v31; // rax
  SIZE_T v32; // rdi
  HANDLE v33; // rax
  void *v34; // rax
  const wchar_t *v35; // r12
  __int64 v36; // rax
  wchar_t *v37; // rsi
  SIZE_T v38; // rdi
  HANDLE v39; // rax
  void *v40; // rax
  wchar_t *SystemPartition; // rax
  const wchar_t *PartitionVhdFilePathFromUnicodeString; // rax
  WCHAR *v43; // rdi
  __int64 v44; // rax
  void *v45; // r14
  __int64 v46; // rcx
  size_t v47; // rsi
  SIZE_T v48; // r14
  HANDLE v49; // rax
  _DWORD *v50; // rax
  void *v51; // rdi
  __int64 v52; // rax
  size_t v53; // rsi
  SIZE_T v54; // r14
  HANDLE v55; // rax
  _DWORD *v56; // rax
  void *v57; // rdi
  LANGID v58; // di
  DWORD v59; // eax
  __int64 v60; // rax
  HANDLE v61; // rax
  void *v62; // rax
  char v64; // [rsp+40h] [rbp-C0h]
  int v65; // [rsp+44h] [rbp-BCh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  void *Srca; // [rsp+58h] [rbp-A8h]
  WCHAR TargetPath; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v69; // [rsp+62h] [rbp-9Eh]
  WCHAR szVolumePathName[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR szVolumeName[56]; // [rsp+480h] [rbp+380h] BYREF
  wchar_t Buffer[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  WCHAR pszPath[14]; // [rsp+700h] [rbp+600h] BYREF
  wchar_t Source[250]; // [rsp+71Ch] [rbp+61Ch] BYREF

  Srca = a3;
  v65 = 0;
  v5 = (const wchar_t *)a3;
  v8 = 0;
  DestinationString = 0;
  if ( a4 )
    v8 = *(const WCHAR **)(a4 + 8);
  memset_0(&BfspGlobals, 0, 0x68u);
  dword_14003F8FC = a2;
  if ( !Src || *(_WORD *)Src != 92 || (v9 = 1, *((_WORD *)Src + 1) != 92) )
    v9 = 0;
  v10 = -1;
  v64 = v9;
  if ( v8 && PathIsPrefixW(v8, (LPCWSTR)Src) )
  {
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
    v12 = (unsigned int)v11;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&Src[2 * v13] );
    v14 = 2 * (v13 - v12) + 2;
    ProcessHeap = GetProcessHeap();
    v16 = HeapAlloc(ProcessHeap, 8u, v14);
    qword_14003F938 = (__int64)v16;
    if ( !v16 )
      goto LABEL_94;
    memcpy_0(v16, &Src[2 * v12], v14);
    v5 = (const wchar_t *)Srca;
  }
  else
  {
    qword_14003F938 = 0;
  }
  if ( Src )
  {
    if ( v9 )
    {
      v25 = -1;
      do
        ++v25;
      while ( *(_WORD *)&Src[2 * v25] );
      if ( v25 < 0xE || _wcsnicmp(L"\\\\?\\GLOBALROOT", (const wchar_t *)Src, 0xEu) )
      {
        BfspLogMessage(4, L"Expected provided path \"%ws\" to start with %ws", Src, L"\\\\?\\GLOBALROOT");
        goto LABEL_20;
      }
      if ( !GetVolumePathNameW((LPCWSTR)Src, pszPath, 0x104u) )
      {
        v18 = -1073741823;
        goto LABEL_95;
      }
      PathRemoveBackslashW(pszPath);
      wcscpy_s(&TargetPath, 0x104u, Source);
      v26 = -1;
      do
        ++v26;
      while ( *(&TargetPath + v26) );
      Src += 2 * v26 + 28;
    }
    else
    {
      if ( !GetVolumePathNameW((LPCWSTR)Src, szVolumePathName, 0x104u) )
      {
        LastError = GetLastError();
        BfspLogMessage(4, L"Failed to GetVolumePathName for %ws (%u).", Src, LastError);
LABEL_20:
        v18 = -1073741811;
LABEL_95:
        BfspLogMessage(4, L"Failed to initialize global state. Status = [%x]", v18);
        BfspDestroyGlobalState();
        return v18;
      }
      BfspLogMessage(2, L"VolumePathName for %ws is %ws", Src, szVolumePathName);
      v19 = -1;
      do
        ++v19;
      while ( szVolumePathName[v19] );
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&Src[2 * v20] );
      if ( v19 > v20 )
      {
        BfspLogMessage(4, L"Invalid VolumePathNameLegth %ws", szVolumePathName);
        goto LABEL_20;
      }
      if ( v19 == 3 )
      {
        szVolumePathName[2] = 0;
        if ( !QueryDosDeviceW(szVolumePathName, &TargetPath, 0x104u) )
        {
          v21 = GetLastError();
          BfspLogMessage(4, L"Failed to QueryDosDevice for %ws (%u).", szVolumePathName, v21);
          goto LABEL_20;
        }
      }
      else
      {
        if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x32u) )
        {
          v22 = GetLastError();
          BfspLogMessage(4, L"Unable to GetVolumeNameForVolumeMountPoint %ws (%u).", szVolumePathName, v22);
          goto LABEL_20;
        }
        wcscpy_s(&TargetPath, 0x104u, szVolumeName);
        v23 = -1;
        do
          ++v23;
        while ( *(&TargetPath + v23) );
        if ( v23 > 1 )
        {
          if ( v69 == 92 )
            v69 = 63;
          if ( *((_WORD *)&Srca + v23 + 3) == 92 )
          {
            v24 = 2 * v23 - 2;
            if ( v24 >= 0x208 )
              _report_rangecheckfailure();
            *(WCHAR *)((char *)&TargetPath + v24) = 0;
          }
        }
      }
      if ( !_wcsnicmp(szVolumePathName, (const wchar_t *)Src, v19 - 1) )
        Src = &Src[2 * v19 - 2];
    }
    v27 = -1;
    do
      ++v27;
    while ( *(&TargetPath + v27) );
    v28 = 2 * v27 + 2;
    v29 = GetProcessHeap();
    v30 = (WCHAR *)HeapAlloc(v29, 8u, v28);
    SourceString = v30;
    if ( !v30 )
      goto LABEL_94;
    memcpy_0(v30, &TargetPath, v28);
    BfspLogMessage(2, L"SystemRoot is %ws", Src);
    v31 = -1;
    do
      ++v31;
    while ( *(_WORD *)&Src[2 * v31] );
    v32 = 2 * v31 + 2;
    v33 = GetProcessHeap();
    v34 = HeapAlloc(v33, 8u, v32);
    qword_14003F930 = v34;
    if ( !v34 )
    {
LABEL_94:
      v18 = -1073741801;
      goto LABEL_95;
    }
    memcpy_0(v34, Src, v32);
  }
  byte_14003F8F8 = (unsigned int)BfspGetFirmwareType() == 2;
  v35 = L"en-us";
  v36 = -1;
  if ( v5 )
    v35 = v5;
  LOWORD(v37) = 0;
  do
    ++v36;
  while ( v35[v36] );
  v38 = 2 * v36 + 2;
  v39 = GetProcessHeap();
  v40 = HeapAlloc(v39, 8u, v38);
  qword_14003F908 = v40;
  if ( !v40 )
    goto LABEL_94;
  memcpy_0(v40, v35, v38);
  SystemPartition = BfspGetSystemPartition(0);
  ::Src = SystemPartition;
  if ( !SystemPartition )
  {
    v18 = -1073741275;
    goto LABEL_95;
  }
  if ( (a2 & 0x10) != 0 )
  {
    byte_14003F8F9 = BfspIsVhdVolume(SystemPartition);
    if ( byte_14003F8F9 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      PartitionVhdFilePathFromUnicodeString = (const wchar_t *)BiGetPartitionVhdFilePathFromUnicodeString(&DestinationString);
      v43 = (WCHAR *)PartitionVhdFilePathFromUnicodeString;
      if ( PartitionVhdFilePathFromUnicodeString )
      {
        if ( !_wcsnicmp(PartitionVhdFilePathFromUnicodeString, L"\\Device\\HarddiskVolume", 0x16u) )
        {
          v37 = wcschr(v43 + 22, 0x5Cu);
          if ( v37 )
          {
            *v37 = 0;
            RtlInitUnicodeString(&DestinationString, v43);
            v44 = BiGetPartitionVhdFilePathFromUnicodeString(&DestinationString);
            *v37 = 92;
            v45 = (void *)v44;
            LOWORD(v37) = 0;
            if ( v44 )
            {
              BfspLogMessage(2, L"Nested VHD NtDevice detected: %ws", v44);
              byte_14003F8FA = 1;
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v45);
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v43);
      }
    }
    SystemPartition = (wchar_t *)::Src;
  }
  v46 = -1;
  do
    ++v46;
  while ( SystemPartition[v46] != (_WORD)v37 );
  v47 = 2 * v46 + 2;
  v48 = 2 * v46 + 62;
  v49 = GetProcessHeap();
  v50 = HeapAlloc(v49, 8u, v48);
  v51 = v50;
  if ( !v50 )
    goto LABEL_94;
  *v50 = 2;
  memcpy_0(v50 + 5, ::Src, v47);
  dword_14003F920 = v48;
  v52 = -1;
  lpMem = v51;
  do
    ++v52;
  while ( *(&TargetPath + v52) );
  v53 = 2 * v52 + 2;
  v54 = 2 * v52 + 62;
  v55 = GetProcessHeap();
  v56 = HeapAlloc(v55, 8u, v54);
  v57 = v56;
  if ( !v56 )
    goto LABEL_94;
  *v56 = 2;
  memcpy_0(v56 + 5, &TargetPath, v53);
  dword_14003F8E8 = v54;
  BfspGlobals = v57;
  if ( Src )
  {
    v58 = 0;
    if ( v64 )
      swprintf_s(Buffer, 0x104u, L"%s%s%s%s", L"\\\\?\\GLOBALROOT", &TargetPath, Src, L"\\System32\\bootstr.dll");
    else
      swprintf_s(Buffer, 0x104u, L"%s%s%s", szVolumePathName, Src, L"\\System32\\bootstr.dll");
    if ( (int)LangNameToLcid(v35, &v65) >= 0 )
      v58 = v65;
    word_14003F900 = v58;
    lpSource = LoadMUILibraryW(Buffer, 8u, v58);
    if ( !lpSource )
    {
      lpSource = LoadLibraryExW(Buffer, 0, 2u);
      if ( !lpSource )
      {
        v18 = -1073741823;
        v59 = GetLastError();
        BfspLogMessage(4, L"BCD strings MUI load failure %ws (%u).", Buffer, v59);
        goto LABEL_95;
      }
    }
  }
  v18 = 0;
  if ( a4 )
  {
    v60 = *(_QWORD *)(a4 + 24);
    if ( v60 )
    {
      do
        ++v10;
      while ( *(_WORD *)(v60 + 2 * v10) );
      v61 = GetProcessHeap();
      v62 = HeapAlloc(v61, 8u, 2 * v10 + 2);
      qword_14003F940 = v62;
      if ( v62 )
      {
        memcpy_0(v62, *(const void **)(a4 + 24), 2 * v10 + 2);
        return v18;
      }
      goto LABEL_94;
    }
  }
  return v18;
}

```

## disassembly

```asm
0x140006cd8  push    rbp
0x140006cda  push    rbx
0x140006cdb  push    rsi
0x140006cdc  push    rdi
0x140006cdd  push    r12
0x140006cdf  push    r13
0x140006ce1  push    r14
0x140006ce3  push    r15
0x140006ce5  lea     rbp, [rsp-828h]
0x140006ced  sub     rsp, 928h
0x140006cf4  mov     rax, cs:__security_cookie
0x140006cfb  xor     rax, rsp
0x140006cfe  mov     [rbp+860h+var_50], rax
0x140006d05  xor     r15d, r15d
0x140006d08  mov     [rsp+960h+Src], r8
0x140006d0d  mov     [rsp+960h+var_91C], r15d
0x140006d12  xorps   xmm0, xmm0
0x140006d15  mov     r13, r9
0x140006d18  mov     rsi, r8
0x140006d1b  mov     r14d, edx
0x140006d1e  mov     rbx, rcx
0x140006d21  mov     edi, r15d
0x140006d24  movups  xmmword ptr [rsp+960h+DestinationString.Length], xmm0
0x140006d29  test    r9, r9
0x140006d2c  jz      short loc_140006D32
0x140006d2e  mov     rdi, [r9+8]
0x140006d32  xor     edx, edx; Val
0x140006d34  lea     rcx, BfspGlobals; void *
0x140006d3b  lea     r8d, [rdx+68h]; Size
0x140006d3f  call    memset_0
0x140006d44  mov     cs:dword_14003F8FC, r14d
0x140006d4b  mov     eax, 5Ch ; '\'
0x140006d50  test    rbx, rbx
0x140006d53  jz      short loc_140006D63
0x140006d55  cmp     [rbx], ax
0x140006d58  jnz     short loc_140006D63
0x140006d5a  mov     r12b, 1
0x140006d5d  cmp     [rbx+2], ax
0x140006d61  jz      short loc_140006D66
0x140006d63  mov     r12b, r15b
0x140006d66  or      r15, 0FFFFFFFFFFFFFFFFh
0x140006d6a  mov     [rsp+960h+var_920], r12b
0x140006d6f  xor     ecx, ecx
0x140006d71  test    rdi, rdi
0x140006d74  jz      short loc_140006DEA
0x140006d76  mov     rdx, rbx; pszPath
0x140006d79  mov     rcx, rdi; pszPrefix
0x140006d7c  call    cs:__imp_PathIsPrefixW
0x140006d82  xor     ecx, ecx
0x140006d84  test    eax, eax
0x140006d86  jz      short loc_140006DEA
0x140006d88  mov     rax, r15
0x140006d8b  inc     rax
0x140006d8e  cmp     [rdi+rax*2], cx
0x140006d92  jnz     short loc_140006D8B
0x140006d94  mov     esi, eax
0x140006d96  mov     rax, r15
0x140006d99  inc     rax
0x140006d9c  cmp     [rbx+rax*2], cx
0x140006da0  jnz     short loc_140006D99
0x140006da2  sub     rax, rsi
0x140006da5  lea     rdi, ds:2[rax*2]
0x140006dad  call    cs:__imp_GetProcessHeap
0x140006db3  mov     r8, rdi; dwBytes
0x140006db6  mov     edx, 8; dwFlags
0x140006dbb  mov     rcx, rax; hHeap
0x140006dbe  call    cs:__imp_HeapAlloc
0x140006dc4  mov     cs:qword_14003F938, rax
0x140006dcb  test    rax, rax
0x140006dce  jz      loc_140007494
0x140006dd4  lea     rdx, [rbx+rsi*2]; Src
0x140006dd8  mov     r8, rdi; Size
0x140006ddb  mov     rcx, rax; void *
0x140006dde  call    memcpy_0
0x140006de3  mov     rsi, [rsp+960h+Src]
0x140006de8  jmp     short loc_140006DF1
0x140006dea  mov     cs:qword_14003F938, rcx
0x140006df1  mov     edi, 104h
0x140006df6  test    rbx, rbx
0x140006df9  jz      loc_14000710E
0x140006dff  test    r12b, r12b
0x140006e02  jnz     loc_140006FA9
0x140006e08  mov     r8d, edi; cchBufferLength
0x140006e0b  lea     rdx, [rbp+860h+szVolumePathName]; lpszVolumePathName
0x140006e12  mov     rcx, rbx; lpszFileName
0x140006e15  call    cs:__imp_GetVolumePathNameW
0x140006e1b  xor     r12d, r12d
0x140006e1e  test    eax, eax
0x140006e20  jnz     short loc_140006E49
0x140006e22  call    cs:__imp_GetLastError
0x140006e28  mov     r8, rbx
0x140006e2b  lea     rdx, aFailedToGetvol; "Failed to GetVolumePathName for %ws (%u"...
0x140006e32  mov     r9d, eax
0x140006e35  mov     ecx, 4
0x140006e3a  call    BfspLogMessage
0x140006e3f  mov     ebx, 0C000000Dh
0x140006e44  jmp     loc_140007499
0x140006e49  lea     r9, [rbp+860h+szVolumePathName]
0x140006e50  mov     r8, rbx
0x140006e53  lea     rdx, aVolumepathname; "VolumePathName for %ws is %ws"
0x140006e5a  mov     ecx, 2
0x140006e5f  call    BfspLogMessage
0x140006e64  lea     rax, [rbp+860h+szVolumePathName]
0x140006e6b  mov     rdi, r15
0x140006e6e  inc     rdi
0x140006e71  cmp     [rax+rdi*2], r12w
0x140006e76  jnz     short loc_140006E6E
0x140006e78  mov     rax, r15
0x140006e7b  inc     rax
0x140006e7e  cmp     [rbx+rax*2], r12w
0x140006e83  jnz     short loc_140006E7B
0x140006e85  cmp     rdi, rax
0x140006e88  jbe     short loc_140006EA4
0x140006e8a  lea     r8, [rbp+860h+szVolumePathName]
0x140006e91  mov     ecx, 4
0x140006e96  lea     rdx, aInvalidVolumep; "Invalid VolumePathNameLegth %ws"
0x140006e9d  call    BfspLogMessage
0x140006ea2  jmp     short loc_140006E3F
0x140006ea4  lea     rcx, [rbp+860h+szVolumePathName]; lpszVolumeMountPoint
0x140006eab  cmp     rdi, 3
0x140006eaf  jnz     short loc_140006EEB
0x140006eb1  mov     r8d, 104h; ucchMax
0x140006eb7  mov     [rbp+860h+var_6EC], r12w
0x140006ebf  lea     rdx, [rsp+960h+TargetPath]; lpTargetPath
0x140006ec4  call    cs:__imp_QueryDosDeviceW
0x140006eca  test    eax, eax
0x140006ecc  jnz     loc_140006F80
0x140006ed2  call    cs:__imp_GetLastError
0x140006ed8  lea     r8, [rbp+860h+szVolumePathName]
0x140006edf  lea     rdx, aFailedToQueryd; "Failed to QueryDosDevice for %ws (%u)."
0x140006ee6  jmp     loc_140006E32
0x140006eeb  mov     r8d, 32h ; '2'; cchBufferLength
0x140006ef1  lea     rdx, [rbp+860h+szVolumeName]; lpszVolumeName
0x140006ef8  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140006efe  test    eax, eax
0x140006f00  jnz     short loc_140006F1B
0x140006f02  call    cs:__imp_GetLastError
0x140006f08  lea     r8, [rbp+860h+szVolumePathName]
0x140006f0f  lea     rdx, aUnableToGetvol; "Unable to GetVolumeNameForVolumeMountPo"...
0x140006f16  jmp     loc_140006E32
0x140006f1b  lea     r8, [rbp+860h+szVolumeName]; Source
0x140006f22  mov     edx, 104h; SizeInWords
0x140006f27  lea     rcx, [rsp+960h+TargetPath]; Destination
0x140006f2c  call    cs:__imp_wcscpy_s
0x140006f32  lea     rcx, [rsp+960h+TargetPath]
0x140006f37  mov     rax, r15
0x140006f3a  inc     rax
0x140006f3d  cmp     [rcx+rax*2], r12w
0x140006f42  jnz     short loc_140006F3A
0x140006f44  cmp     rax, 1
0x140006f48  jbe     short loc_140006F80
0x140006f4a  mov     edx, 5Ch ; '\'
0x140006f4f  cmp     [rsp+960h+var_8FE], dx
0x140006f54  jnz     short loc_140006F5E
0x140006f56  lea     ecx, [rdx-1Dh]
0x140006f59  mov     [rsp+960h+var_8FE], cx
0x140006f5e  cmp     word ptr [rsp+rax*2+960h+Src+6], dx
0x140006f63  jnz     short loc_140006F80
0x140006f65  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140006f6d  cmp     rcx, 208h
0x140006f74  jnb     loc_1400074E8
0x140006f7a  mov     [rsp+rcx+960h+TargetPath], r12w
0x140006f80  lea     r8, [rdi-1]; MaxCount
0x140006f84  mov     rdx, rbx; String2
0x140006f87  lea     rcx, [rbp+860h+szVolumePathName]; String1
0x140006f8e  call    cs:__imp__wcsnicmp
0x140006f94  test    eax, eax
0x140006f96  jnz     loc_14000703D
0x140006f9c  lea     rbx, [rbx+rdi*2]
0x140006fa0  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140006fa4  jmp     loc_14000703D
0x140006fa9  mov     rax, r15
0x140006fac  xor     r12d, r12d
0x140006faf  inc     rax
0x140006fb2  cmp     [rbx+rax*2], r12w
0x140006fb7  jnz     short loc_140006FAF
0x140006fb9  mov     r8d, 0Eh; MaxCount
0x140006fbf  cmp     rax, r8
0x140006fc2  jb      loc_1400070EE
0x140006fc8  mov     rdx, rbx; String2
0x140006fcb  lea     rcx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x140006fd2  call    cs:__imp__wcsnicmp
0x140006fd8  test    eax, eax
0x140006fda  jnz     loc_1400070EE
0x140006fe0  mov     r8d, edi; cchBufferLength
0x140006fe3  lea     rdx, [rbp+860h+pszPath]; lpszVolumePathName
0x140006fea  mov     rcx, rbx; lpszFileName
0x140006fed  call    cs:__imp_GetVolumePathNameW
0x140006ff3  test    eax, eax
0x140006ff5  jnz     short loc_140007001
0x140006ff7  mov     ebx, 0C0000001h
0x140006ffc  jmp     loc_140007499
0x140007001  lea     rcx, [rbp+860h+pszPath]; pszPath
0x140007008  call    cs:__imp_PathRemoveBackslashW
0x14000700e  lea     r8, [rbp+860h+Source]; Source
0x140007015  mov     rdx, rdi; SizeInWords
0x140007018  lea     rcx, [rsp+960h+TargetPath]; Destination
0x14000701d  call    cs:__imp_wcscpy_s
0x140007023  lea     rcx, [rsp+960h+TargetPath]
0x140007028  mov     rax, r15
0x14000702b  inc     rax
0x14000702e  cmp     [rcx+rax*2], r12w
0x140007033  jnz     short loc_14000702B
0x140007035  lea     rbx, [rbx+rax*2]
0x140007039  add     rbx, 1Ch
0x14000703d  lea     rcx, [rsp+960h+TargetPath]
0x140007042  mov     rax, r15
0x140007045  inc     rax
0x140007048  cmp     [rcx+rax*2], r12w
0x14000704d  jnz     short loc_140007045
0x14000704f  lea     rdi, ds:2[rax*2]
0x140007057  call    cs:__imp_GetProcessHeap
0x14000705d  mov     r8, rdi; dwBytes
0x140007060  mov     edx, 8; dwFlags
0x140007065  mov     rcx, rax; hHeap
0x140007068  call    cs:__imp_HeapAlloc
0x14000706e  mov     cs:SourceString, rax
0x140007075  test    rax, rax
0x140007078  jz      loc_140007494
0x14000707e  mov     r8, rdi; Size
0x140007081  lea     rdx, [rsp+960h+TargetPath]; Src
0x140007086  mov     rcx, rax; void *
0x140007089  call    memcpy_0
0x14000708e  mov     r8, rbx
0x140007091  lea     rdx, aSystemrootIsWs; "SystemRoot is %ws"
0x140007098  mov     ecx, 2
0x14000709d  call    BfspLogMessage
0x1400070a2  mov     rax, r15
0x1400070a5  inc     rax
0x1400070a8  cmp     [rbx+rax*2], r12w
0x1400070ad  jnz     short loc_1400070A5
0x1400070af  lea     rdi, ds:2[rax*2]
0x1400070b7  call    cs:__imp_GetProcessHeap
0x1400070bd  mov     r8, rdi; dwBytes
0x1400070c0  mov     edx, 8; dwFlags
0x1400070c5  mov     rcx, rax; hHeap
0x1400070c8  call    cs:__imp_HeapAlloc
0x1400070ce  mov     cs:qword_14003F930, rax
0x1400070d5  test    rax, rax
0x1400070d8  jz      loc_140007494
0x1400070de  mov     r8, rdi; Size
0x1400070e1  mov     rdx, rbx; Src
0x1400070e4  mov     rcx, rax; void *
0x1400070e7  call    memcpy_0
0x1400070ec  jmp     short loc_140007111
0x1400070ee  lea     r9, aGlobalroot; "\\\\?\\GLOBALROOT"
0x1400070f5  mov     r8, rbx
0x1400070f8  lea     rdx, aExpectedProvid; "Expected provided path \"%ws\" to start"...
0x1400070ff  mov     ecx, 4
0x140007104  call    BfspLogMessage
0x140007109  jmp     loc_140006E3F
0x14000710e  xor     r12d, r12d
0x140007111  mov     cs:byte_14003F8F8, r12b
0x140007118  call    BfspGetFirmwareType
0x14000711d  cmp     eax, 2
0x140007120  jnz     short loc_140007129
0x140007122  mov     cs:byte_14003F8F8, 1
0x140007129  test    rsi, rsi
0x14000712c  lea     r12, aEnUs; "en-us"
0x140007133  mov     rax, r15
0x140007136  cmovnz  r12, rsi
0x14000713a  xor     esi, esi
0x14000713c  inc     rax
0x14000713f  cmp     [r12+rax*2], si
0x140007144  jnz     short loc_14000713C
0x140007146  lea     rdi, ds:2[rax*2]
0x14000714e  call    cs:__imp_GetProcessHeap
0x140007154  mov     r8, rdi; dwBytes
0x140007157  mov     edx, 8; dwFlags
0x14000715c  mov     rcx, rax; hHeap
0x14000715f  call    cs:__imp_HeapAlloc
0x140007165  mov     cs:qword_14003F908, rax
0x14000716c  test    rax, rax
0x14000716f  jz      loc_140007494
0x140007175  mov     r8, rdi; Size
0x140007178  mov     rdx, r12; Src
0x14000717b  mov     rcx, rax; void *
0x14000717e  call    memcpy_0
0x140007183  xor     ecx, ecx
0x140007185  call    BfspGetSystemPartition
0x14000718a  mov     cs:Src, rax
0x140007191  test    rax, rax
0x140007194  jnz     short loc_1400071A0
0x140007196  mov     ebx, 0C0000225h
0x14000719b  jmp     loc_140007499
0x1400071a0  test    r14b, 10h
0x1400071a4  jz      loc_140007293
0x1400071aa  mov     rcx, rax; SourceString
0x1400071ad  call    BfspIsVhdVolume
0x1400071b2  mov     cs:byte_14003F8F9, al
0x1400071b8  test    al, al
0x1400071ba  jz      loc_14000728C
0x1400071c0  mov     rdx, cs:SourceString; SourceString
0x1400071c7  lea     rcx, [rsp+960h+DestinationString]; DestinationString
0x1400071cc  call    cs:__imp_RtlInitUnicodeString
0x1400071d2  lea     rcx, [rsp+960h+DestinationString]
0x1400071d7  call    BiGetPartitionVhdFilePathFromUnicodeString
0x1400071dc  mov     rdi, rax
0x1400071df  test    rax, rax
0x1400071e2  jz      loc_14000728C
  ... truncated ...
```
