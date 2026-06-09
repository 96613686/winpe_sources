# DwAddLuidIfNotPresent

- ea: `0x1800997b4`
- end: `0x18009997d`
- name: `DwAddLuidIfNotPresent`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180012940`

## callees

- `0x1800997b4`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800997d8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800997d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009988c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009988c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099961`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099961`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099953`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099953`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099879`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099879`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009984d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800998b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009984d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800998b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099948`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099948`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180099937`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180099937`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009981e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009981e`

## string_xrefs

- `0x1800997ec`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x1800997e3`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`

## pseudocode

```c
__int64 __fastcall DwAddLuidIfNotPresent(__int64 a1)
{
  BYTE *v1; // rsi
  char IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int v4; // ebx
  DWORD v5; // edx
  int v6; // r15d
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  const BYTE *v9; // r14
  __int64 v10; // rdi
  DWORD LastError; // eax
  __int64 v12; // r8
  DWORD v13; // edi
  HANDLE v14; // rax
  int v16; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v16 = a1;
  v1 = 0;
  hKey = 0;
  cbData = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v3 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  if ( !IsStateSeparationEnabled )
    v3 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 0x20007u, 0, &hKey, 0);
  if ( !v4 )
  {
    v4 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, 0, &cbData);
    if ( v4 )
      goto LABEL_19;
    v5 = cbData;
    v6 = 0;
    if ( cbData )
    {
      v7 = cbData;
      ProcessHeap = GetProcessHeap();
      v1 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7 + 4);
      if ( !v1 )
      {
        v9 = 0;
        v10 = 0;
        LastError = GetLastError();
        v5 = cbData;
        v4 = LastError;
        goto LABEL_15;
      }
      v4 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, v1, &cbData);
      if ( v4 )
        goto LABEL_19;
      v5 = cbData;
    }
    v12 = 0;
    v10 = v5 >> 2;
    v9 = v1;
    if ( !(_DWORD)v10 )
      goto LABEL_17;
    while ( *(_DWORD *)&v1[4 * v12] != v16 )
    {
      v12 = (unsigned int)(v12 + 1);
      if ( (unsigned int)v12 >= (unsigned int)v10 )
        goto LABEL_15;
    }
    v6 = 1;
LABEL_15:
    if ( !v4 && !v6 )
    {
LABEL_17:
      if ( v5 )
      {
        *(_DWORD *)&v9[4 * v10] = v16;
        v13 = 4 * v10 + 4;
LABEL_21:
        v4 = RegSetValueExW(hKey, L"AllocatedLuids", 0, 3u, v9, v13);
        goto LABEL_22;
      }
LABEL_20:
      v9 = (const BYTE *)&v16;
      v13 = 4;
      goto LABEL_21;
    }
LABEL_19:
    if ( v4 != 2 )
      goto LABEL_22;
    goto LABEL_20;
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v1);
  }
  return v4;
}

```

## disassembly

```asm
0x1800997b4  mov     [rsp-28h+arg_18], rbx
0x1800997b9  mov     [rsp-28h+arg_0], ecx
0x1800997bd  push    rbp
0x1800997be  push    rsi
0x1800997bf  push    rdi
0x1800997c0  push    r14
0x1800997c2  push    r15
0x1800997c4  mov     rbp, rsp
0x1800997c7  sub     rsp, 50h
0x1800997cb  xor     esi, esi
0x1800997cd  mov     [rbp+hKey], 0
0x1800997d5  mov     [rbp+cbData], esi
0x1800997d8  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800997de  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x1800997e3  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800997ea  test    al, al
0x1800997ec  lea     rdx, aOsdataSystemCu_3; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800997f3  lea     rax, [rbp+hKey]
0x1800997f7  mov     [rsp+50h+phkResult], rax; phkResult
0x1800997fc  cmovz   rdx, rcx; lpSubKey
0x180099800  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180099805  xor     r9d, r9d; lpClass
0x180099808  mov     [rsp+50h+samDesired], 20007h; samDesired
0x180099810  xor     r8d, r8d; Reserved
0x180099813  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009981a  mov     [rsp+50h+dwOptions], esi; dwOptions
0x18009981e  call    cs:__imp_RegCreateKeyExW
0x180099824  mov     ebx, eax
0x180099826  test    eax, eax
0x180099828  jnz     loc_18009993F
0x18009982e  mov     rcx, [rbp+hKey]; hKey
0x180099832  lea     rax, [rbp+cbData]
0x180099836  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x18009983b  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180099842  xor     r9d, r9d; lpType
0x180099845  mov     qword ptr [rsp+50h+dwOptions], rsi; lpData
0x18009984a  xor     r8d, r8d; lpReserved
0x18009984d  call    cs:__imp_RegQueryValueExW
0x180099853  mov     ebx, eax
0x180099855  test    eax, eax
0x180099857  jnz     loc_18009990C
0x18009985d  mov     edx, [rbp+cbData]
0x180099860  xor     r15d, r15d
0x180099863  test    edx, edx
0x180099865  jz      short loc_1800998C7
0x180099867  mov     ebx, edx
0x180099869  call    cs:__imp_GetProcessHeap
0x18009986f  mov     rcx, rax; hHeap
0x180099872  lea     r8, [rbx+4]; dwBytes
0x180099876  lea     edx, [rsi+8]; dwFlags
0x180099879  call    cs:__imp_HeapAlloc
0x18009987f  mov     rsi, rax
0x180099882  test    rax, rax
0x180099885  jnz     short loc_180099899
0x180099887  xor     r14d, r14d
0x18009988a  xor     edi, edi
0x18009988c  call    cs:__imp_GetLastError
0x180099892  mov     edx, [rbp+cbData]
0x180099895  mov     ebx, eax
0x180099897  jmp     short loc_1800998EF
0x180099899  mov     rcx, [rbp+hKey]; hKey
0x18009989d  lea     rax, [rbp+cbData]
0x1800998a1  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x1800998a6  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x1800998ad  xor     r9d, r9d; lpType
0x1800998b0  mov     qword ptr [rsp+50h+dwOptions], rsi; lpData
0x1800998b5  xor     r8d, r8d; lpReserved
0x1800998b8  call    cs:__imp_RegQueryValueExW
0x1800998be  mov     ebx, eax
0x1800998c0  test    eax, eax
0x1800998c2  jnz     short loc_18009990C
0x1800998c4  mov     edx, [rbp+cbData]
0x1800998c7  mov     edi, edx
0x1800998c9  xor     r8d, r8d
0x1800998cc  shr     edi, 2
0x1800998cf  mov     r14, rsi
0x1800998d2  test    edi, edi
0x1800998d4  jz      short loc_1800998F8
0x1800998d6  mov     eax, [rbp+arg_0]
0x1800998d9  cmp     [rsi+r8*4], eax
0x1800998dd  jz      short loc_1800998E9
0x1800998df  inc     r8d
0x1800998e2  cmp     r8d, edi
0x1800998e5  jb      short loc_1800998D6
0x1800998e7  jmp     short loc_1800998EF
0x1800998e9  mov     r15d, 1
0x1800998ef  test    ebx, ebx
0x1800998f1  jnz     short loc_18009990C
0x1800998f3  test    r15d, r15d
0x1800998f6  jnz     short loc_18009990C
0x1800998f8  test    edx, edx
0x1800998fa  jz      short loc_180099911
0x1800998fc  mov     eax, [rbp+arg_0]
0x1800998ff  mov     [r14+rdi*4], eax
0x180099903  lea     edi, ds:4[rdi*4]
0x18009990a  jmp     short loc_18009991A
0x18009990c  cmp     ebx, 2
0x18009990f  jnz     short loc_18009993F
0x180099911  lea     r14, [rbp+arg_0]
0x180099915  mov     edi, 4
0x18009991a  mov     rcx, [rbp+hKey]; hKey
0x18009991e  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180099925  mov     [rsp+50h+samDesired], edi; cbData
0x180099929  mov     r9d, 3; dwType
0x18009992f  xor     r8d, r8d; Reserved
0x180099932  mov     qword ptr [rsp+50h+dwOptions], r14; lpData
0x180099937  call    cs:__imp_RegSetValueExW
0x18009993d  mov     ebx, eax
0x18009993f  mov     rcx, [rbp+hKey]; hKey
0x180099943  test    rcx, rcx
0x180099946  jz      short loc_18009994E
0x180099948  call    cs:__imp_RegCloseKey
0x18009994e  test    rsi, rsi
0x180099951  jz      short loc_180099967
0x180099953  call    cs:__imp_GetProcessHeap
0x180099959  mov     r8, rsi; lpMem
0x18009995c  xor     edx, edx; dwFlags
0x18009995e  mov     rcx, rax; hHeap
0x180099961  call    cs:__imp_HeapFree
0x180099967  mov     eax, ebx
0x180099969  mov     rbx, [rsp+50h+arg_18]
0x180099971  add     rsp, 50h
0x180099975  pop     r15
0x180099977  pop     r14
0x180099979  pop     rdi
0x18009997a  pop     rsi
0x18009997b  pop     rbp
0x18009997c  retn
```
