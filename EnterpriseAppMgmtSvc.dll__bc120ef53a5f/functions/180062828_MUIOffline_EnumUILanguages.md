# MUIOffline_EnumUILanguages

- ea: `0x180062828`
- end: `0x180062a76`
- name: `MUIOffline_EnumUILanguages`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003fcf0`

## callees

- `0x180005ff4`
- `0x180062828`
- `0x180062a7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800628d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800628d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800628b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800629e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800628b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800629e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800629f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800629f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062a1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062a4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062a4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062928`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800629ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062928`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800629ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800629d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062a3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800629d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062a3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062962`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062962`

## pseudocode

```c
__int64 __fastcall MUIOffline_EnumUILanguages(_WORD *a1, __int64 a2, DWORD a3, __int64 a4)
{
  HKEY v5; // rcx
  unsigned int v7; // r15d
  __int64 v8; // rcx
  _WORD *v9; // rax
  LSTATUS v10; // ebx
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  __int64 v13; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v15; // r8
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  WCHAR *v19; // rdi
  HANDLE v20; // rax
  DWORD LastError; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-30h]
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  HKEY v25; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  __int64 Data; // [rsp+98h] [rbp+48h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+50h] BYREF

  Type = a3;
  Data = a2;
  v5 = 0;
  v25 = 0;
  v7 = 0;
  if ( !a1 )
  {
    v10 = 87;
    goto LABEL_23;
  }
  hKey = 0;
  v8 = 0x7FFFFFFF;
  Type = 0;
  LODWORD(Data) = 0;
  v9 = a1;
  cbData = 4;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  if ( !v8 )
  {
    v10 = 50;
LABEL_20:
    v5 = 0;
    v25 = 0;
    goto LABEL_23;
  }
  v11 = ((0x7FFFFFFF - (_DWORD)v8) & (unsigned int)-(v8 != 0)) + 16;
  v12 = (unsigned int)v11;
  v13 = 2 * v11;
  ProcessHeap = GetProcessHeap();
  v15 = v13;
  v10 = 8;
  v16 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v15);
  v19 = v16;
  if ( v16 )
  {
    if ( (int)StringCchPrintfW(v16, (unsigned int)v12, L"%s\\Select", a1) < 0 )
      goto LABEL_9;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &hKey);
    if ( v10 )
      goto LABEL_15;
    v10 = RegQueryValueExW(hKey, L"Default", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v10 )
      goto LABEL_15;
    if ( Type == 4
      && (LODWORD(phkResult) = Data, (int)StringCchPrintfW(v19, v12, L"%s\\ControlSet%03u", a1, phkResult) >= 0) )
    {
      v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &v25);
    }
    else
    {
LABEL_9:
      v10 = 50;
    }
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v19 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v19);
  }
  if ( v10 )
    goto LABEL_20;
  v7 = MUIOffline_EnumUILanguagesFromKey(v25, v17, v18, a4);
  LastError = GetLastError();
  v5 = v25;
  v10 = LastError;
LABEL_23:
  if ( v5 )
    RegCloseKey(v5);
  if ( v10 )
    SetLastError(v10);
  return v7;
}

```

## disassembly

```asm
0x180062828  mov     [rsp-38h+arg_0], rbx
0x18006282d  mov     [rsp-38h+Type], r8d
0x180062832  mov     [rsp-38h+Data], rdx
0x180062837  push    rbp
0x180062838  push    rsi
0x180062839  push    rdi
0x18006283a  push    r12
0x18006283c  push    r13
0x18006283e  push    r14
0x180062840  push    r15
0x180062842  mov     rbp, rsp
0x180062845  sub     rsp, 50h
0x180062849  xor     r13d, r13d
0x18006284c  mov     rsi, rcx
0x18006284f  mov     ecx, r13d; hKey
0x180062852  mov     r12, r9
0x180062855  mov     [rbp+var_18], rcx
0x180062859  mov     r15d, r13d
0x18006285c  test    rsi, rsi
0x18006285f  jz      loc_180062A32
0x180062865  mov     edx, 7FFFFFFFh
0x18006286a  mov     [rbp+hKey], r13
0x18006286e  mov     ecx, edx
0x180062870  mov     [rbp+Type], r13d
0x180062874  mov     dword ptr [rbp+Data], r13d
0x180062878  mov     rax, rsi
0x18006287b  mov     [rbp+cbData], 4
0x180062882  cmp     [rax], r13w
0x180062886  jz      short loc_180062892
0x180062888  add     rax, 2
0x18006288c  sub     rcx, 1
0x180062890  jnz     short loc_180062882
0x180062892  sub     rdx, rcx
0x180062895  mov     rax, rcx
0x180062898  neg     rax
0x18006289b  sbb     rax, rax
0x18006289e  and     rax, rdx
0x1800628a1  test    rcx, rcx
0x1800628a4  jnz     short loc_1800628AE
0x1800628a6  lea     ebx, [rcx+32h]
0x1800628a9  jmp     loc_180062A06
0x1800628ae  add     eax, 10h
0x1800628b1  mov     r14d, eax
0x1800628b4  lea     rbx, [rax+rax]
0x1800628b8  call    cs:__imp_GetProcessHeap
0x1800628bf  nop     dword ptr [rax+rax+00h]
0x1800628c4  mov     r8, rbx; dwBytes
0x1800628c7  mov     ebx, 8
0x1800628cc  mov     edx, ebx; dwFlags
0x1800628ce  mov     rcx, rax; hHeap
0x1800628d1  call    cs:__imp_HeapAlloc
0x1800628d8  nop     dword ptr [rax+rax+00h]
0x1800628dd  mov     rdi, rax
0x1800628e0  test    rax, rax
0x1800628e3  jz      loc_1800629C8
0x1800628e9  mov     r9, rsi
0x1800628ec  lea     r8, aSSelect; "%s\\Select"
0x1800628f3  mov     edx, r14d; unsigned __int64
0x1800628f6  mov     rcx, rax; unsigned __int16 *
0x1800628f9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800628fe  test    eax, eax
0x180062900  jns     short loc_18006290C
0x180062902  mov     ebx, 32h ; '2'
0x180062907  jmp     loc_1800629C8
0x18006290c  lea     rax, [rbp+hKey]
0x180062910  mov     r9d, 20019h; samDesired
0x180062916  xor     r8d, r8d; ulOptions
0x180062919  mov     [rsp+50h+phkResult], rax; phkResult
0x18006291e  mov     rdx, rdi; lpSubKey
0x180062921  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180062928  call    cs:__imp_RegOpenKeyExW
0x18006292f  nop     dword ptr [rax+rax+00h]
0x180062934  mov     ebx, eax
0x180062936  test    eax, eax
0x180062938  jnz     loc_1800629C8
0x18006293e  mov     rcx, [rbp+hKey]; hKey
0x180062942  lea     rax, [rbp+cbData]
0x180062946  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18006294b  lea     r9, [rbp+Type]; lpType
0x18006294f  lea     rax, [rbp+Data]
0x180062953  xor     r8d, r8d; lpReserved
0x180062956  lea     rdx, aDefault; "Default"
0x18006295d  mov     [rsp+50h+phkResult], rax; lpData
0x180062962  call    cs:__imp_RegQueryValueExW
0x180062969  nop     dword ptr [rax+rax+00h]
0x18006296e  mov     ebx, eax
0x180062970  test    eax, eax
0x180062972  jnz     short loc_1800629C8
0x180062974  cmp     [rbp+Type], 4
0x180062978  jnz     short loc_180062902
0x18006297a  mov     eax, dword ptr [rbp+Data]
0x18006297d  lea     r8, aSControlset03u; "%s\\ControlSet%03u"
0x180062984  mov     r9, rsi
0x180062987  mov     dword ptr [rsp+50h+phkResult], eax
0x18006298b  mov     rdx, r14; unsigned __int64
0x18006298e  mov     rcx, rdi; unsigned __int16 *
0x180062991  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180062996  test    eax, eax
0x180062998  js      loc_180062902
0x18006299e  lea     rax, [rbp+var_18]
0x1800629a2  mov     r9d, 20019h; samDesired
0x1800629a8  xor     r8d, r8d; ulOptions
0x1800629ab  mov     [rsp+50h+phkResult], rax; phkResult
0x1800629b0  mov     rdx, rdi; lpSubKey
0x1800629b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800629ba  call    cs:__imp_RegOpenKeyExW
0x1800629c1  nop     dword ptr [rax+rax+00h]
0x1800629c6  mov     ebx, eax
0x1800629c8  mov     rcx, [rbp+hKey]; hKey
0x1800629cc  test    rcx, rcx
0x1800629cf  jz      short loc_1800629DD
0x1800629d1  call    cs:__imp_RegCloseKey
0x1800629d8  nop     dword ptr [rax+rax+00h]
0x1800629dd  test    rdi, rdi
0x1800629e0  jz      short loc_180062A02
0x1800629e2  call    cs:__imp_GetProcessHeap
0x1800629e9  nop     dword ptr [rax+rax+00h]
0x1800629ee  mov     r8, rdi; lpMem
0x1800629f1  xor     edx, edx; dwFlags
0x1800629f3  mov     rcx, rax; hHeap
0x1800629f6  call    cs:__imp_HeapFree
0x1800629fd  nop     dword ptr [rax+rax+00h]
0x180062a02  test    ebx, ebx
0x180062a04  jz      short loc_180062A0F
0x180062a06  mov     rcx, r13
0x180062a09  mov     [rbp+var_18], rcx
0x180062a0d  jmp     short loc_180062A37
0x180062a0f  mov     rcx, [rbp+var_18]
0x180062a13  mov     r9, r12
0x180062a16  call    MUIOffline_EnumUILanguagesFromKey
0x180062a1b  mov     r15d, eax
0x180062a1e  call    cs:__imp_GetLastError
0x180062a25  nop     dword ptr [rax+rax+00h]
0x180062a2a  mov     rcx, [rbp+var_18]
0x180062a2e  mov     ebx, eax
0x180062a30  jmp     short loc_180062A37
0x180062a32  mov     ebx, 57h ; 'W'
0x180062a37  test    rcx, rcx
0x180062a3a  jz      short loc_180062A48
0x180062a3c  call    cs:__imp_RegCloseKey
0x180062a43  nop     dword ptr [rax+rax+00h]
0x180062a48  test    ebx, ebx
0x180062a4a  jz      short loc_180062A5A
0x180062a4c  mov     ecx, ebx; dwErrCode
0x180062a4e  call    cs:__imp_SetLastError
0x180062a55  nop     dword ptr [rax+rax+00h]
0x180062a5a  mov     rbx, [rsp+50h+arg_0]
0x180062a62  mov     eax, r15d
0x180062a65  add     rsp, 50h
0x180062a69  pop     r15
0x180062a6b  pop     r14
0x180062a6d  pop     r13
0x180062a6f  pop     r12
0x180062a71  pop     rdi
0x180062a72  pop     rsi
0x180062a73  pop     rbp
0x180062a74  retn
```
