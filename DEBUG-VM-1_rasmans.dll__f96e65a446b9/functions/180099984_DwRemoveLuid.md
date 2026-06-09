# DwRemoveLuid

- ea: `0x180099984`
- end: `0x180099b82`
- name: `DwRemoveLuid`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180019e90`

## callees

- `0x180099984`
- `0x1800e71ee`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800999a9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800999a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099a41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099b50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099b69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099b50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099b69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099a24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099aab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099b42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099b5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099a24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099aab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099b42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180099b5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099a33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099abd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099a33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180099abd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180099a0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180099a6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180099a0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180099a6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800999dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800999dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099b37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099b37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180099b26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180099b26`

## string_xrefs

- `0x1800999be`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x1800999af`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`

## pseudocode

```c
__int64 __fastcall DwRemoveLuid(__int64 a1)
{
  BYTE *v1; // rsi
  int v2; // edi
  BYTE *v3; // r15
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int v6; // ebx
  DWORD v7; // ecx
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  unsigned int v11; // ecx
  __int64 v12; // r14
  __int64 v13; // rbx
  HANDLE v14; // rax
  BYTE *v15; // rax
  unsigned int v16; // ebx
  HANDLE v17; // rax
  HANDLE v18; // rax
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  v1 = 0;
  hKey = 0;
  cbData = 0;
  v2 = a1;
  v3 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  if ( !IsStateSeparationEnabled )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20007u, &hKey);
  if ( !v6 )
  {
    v6 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, 0, &cbData);
    if ( !v6 )
    {
      v7 = cbData;
      if ( cbData )
      {
        v8 = cbData;
        ProcessHeap = GetProcessHeap();
        v1 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v8);
        if ( !v1 )
          goto LABEL_7;
        v6 = RegQueryValueExW(hKey, L"AllocatedLuids", 0, 0, v1, &cbData);
        if ( v6 )
          goto LABEL_17;
        v7 = cbData;
      }
      v11 = v7 >> 2;
      v12 = 0;
      if ( !v11 )
        goto LABEL_17;
      while ( *(_DWORD *)&v1[4 * v12] != v2 )
      {
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= v11 )
          goto LABEL_17;
      }
      cbData = 4 * v11;
      v13 = 4 * v11;
      v14 = GetProcessHeap();
      v15 = (BYTE *)HeapAlloc(v14, 8u, v13 - 4);
      v3 = v15;
      if ( v15 )
      {
        v16 = cbData - 4 * v12 - 4;
        memcpy_0(v15, v1, (unsigned int)(4 * v12));
        memcpy_0(&v3[(unsigned int)(4 * v12)], &v1[4 * (unsigned int)(v12 + 1)], v16);
        LastError = RegSetValueExW(hKey, L"AllocatedLuids", 0, 3u, v3, cbData - 4);
        goto LABEL_16;
      }
LABEL_7:
      LastError = GetLastError();
LABEL_16:
      v6 = LastError;
    }
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v1);
  }
  if ( v3 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v3);
  }
  return v6;
}

```

## disassembly

```asm
0x180099984  mov     [rsp-28h+arg_0], rbx
0x180099989  push    rbp
0x18009998a  push    rsi
0x18009998b  push    rdi
0x18009998c  push    r14
0x18009998e  push    r15
0x180099990  mov     rbp, rsp
0x180099993  sub     rsp, 30h
0x180099997  xor     esi, esi
0x180099999  mov     [rbp+hKey], 0
0x1800999a1  mov     [rbp+cbData], esi
0x1800999a4  mov     edi, ecx
0x1800999a6  xor     r15d, r15d
0x1800999a9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800999af  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800999b6  mov     r9d, 20007h; samDesired
0x1800999bc  test    al, al
0x1800999be  lea     rdx, aOsdataSystemCu_3; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800999c5  lea     rax, [rbp+hKey]
0x1800999c9  cmovz   rdx, rcx; lpSubKey
0x1800999cd  mov     [rsp+30h+phkResult], rax; phkResult
0x1800999d2  xor     r8d, r8d; ulOptions
0x1800999d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800999dc  call    cs:__imp_RegOpenKeyExW
0x1800999e2  mov     ebx, eax
0x1800999e4  test    eax, eax
0x1800999e6  jnz     loc_180099B2E
0x1800999ec  mov     rcx, [rbp+hKey]; hKey
0x1800999f0  lea     rax, [rbp+cbData]
0x1800999f4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800999f9  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180099a00  xor     r9d, r9d; lpType
0x180099a03  mov     [rsp+30h+phkResult], rsi; lpData
0x180099a08  xor     r8d, r8d; lpReserved
0x180099a0b  call    cs:__imp_RegQueryValueExW
0x180099a11  mov     ebx, eax
0x180099a13  test    eax, eax
0x180099a15  jnz     loc_180099B2E
0x180099a1b  mov     ecx, [rbp+cbData]
0x180099a1e  test    ecx, ecx
0x180099a20  jz      short loc_180099A7E
0x180099a22  mov     ebx, ecx
0x180099a24  call    cs:__imp_GetProcessHeap
0x180099a2a  mov     r8d, ebx; dwBytes
0x180099a2d  lea     edx, [rsi+8]; dwFlags
0x180099a30  mov     rcx, rax; hHeap
0x180099a33  call    cs:__imp_HeapAlloc
0x180099a39  mov     rsi, rax
0x180099a3c  test    rax, rax
0x180099a3f  jnz     short loc_180099A4C
0x180099a41  call    cs:__imp_GetLastError
0x180099a47  jmp     loc_180099B2C
0x180099a4c  mov     rcx, [rbp+hKey]; hKey
0x180099a50  lea     rax, [rbp+cbData]
0x180099a54  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180099a59  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180099a60  xor     r9d, r9d; lpType
0x180099a63  mov     [rsp+30h+phkResult], rsi; lpData
0x180099a68  xor     r8d, r8d; lpReserved
0x180099a6b  call    cs:__imp_RegQueryValueExW
0x180099a71  mov     ebx, eax
0x180099a73  test    eax, eax
0x180099a75  jnz     loc_180099B2E
0x180099a7b  mov     ecx, [rbp+cbData]
0x180099a7e  shr     ecx, 2
0x180099a81  xor     r14d, r14d
0x180099a84  test    ecx, ecx
0x180099a86  jz      loc_180099B2E
0x180099a8c  cmp     [rsi+r14*4], edi
0x180099a90  jz      short loc_180099A9F
0x180099a92  inc     r14d
0x180099a95  cmp     r14d, ecx
0x180099a98  jb      short loc_180099A8C
0x180099a9a  jmp     loc_180099B2E
0x180099a9f  lea     eax, ds:0[rcx*4]
0x180099aa6  mov     [rbp+cbData], eax
0x180099aa9  mov     ebx, eax
0x180099aab  call    cs:__imp_GetProcessHeap
0x180099ab1  lea     r8, [rbx-4]; dwBytes
0x180099ab5  mov     edx, 8; dwFlags
0x180099aba  mov     rcx, rax; hHeap
0x180099abd  call    cs:__imp_HeapAlloc
0x180099ac3  mov     r15, rax
0x180099ac6  test    rax, rax
0x180099ac9  jz      loc_180099A41
0x180099acf  mov     ebx, [rbp+cbData]
0x180099ad2  lea     ecx, ds:0[r14*4]
0x180099ada  sub     ebx, ecx
0x180099adc  mov     edi, ecx
0x180099ade  mov     r8d, ecx; Size
0x180099ae1  mov     rdx, rsi; Src
0x180099ae4  mov     rcx, rax; void *
0x180099ae7  add     ebx, 0FFFFFFFCh
0x180099aea  call    memcpy_0
0x180099aef  lea     eax, [r14+1]
0x180099af3  mov     r8d, ebx; Size
0x180099af6  lea     rcx, [rdi+r15]; void *
0x180099afa  lea     rdx, [rsi+rax*4]; Src
0x180099afe  call    memcpy_0
0x180099b03  mov     eax, [rbp+cbData]
0x180099b06  lea     rdx, aAllocatedluids; "AllocatedLuids"
0x180099b0d  mov     rcx, [rbp+hKey]; hKey
0x180099b11  add     eax, 0FFFFFFFCh
0x180099b14  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x180099b18  mov     r9d, 3; dwType
0x180099b1e  xor     r8d, r8d; Reserved
0x180099b21  mov     [rsp+30h+phkResult], r15; lpData
0x180099b26  call    cs:__imp_RegSetValueExW
0x180099b2c  mov     ebx, eax
0x180099b2e  mov     rcx, [rbp+hKey]; hKey
0x180099b32  test    rcx, rcx
0x180099b35  jz      short loc_180099B3D
0x180099b37  call    cs:__imp_RegCloseKey
0x180099b3d  test    rsi, rsi
0x180099b40  jz      short loc_180099B56
0x180099b42  call    cs:__imp_GetProcessHeap
0x180099b48  mov     r8, rsi; lpMem
0x180099b4b  xor     edx, edx; dwFlags
0x180099b4d  mov     rcx, rax; hHeap
0x180099b50  call    cs:__imp_HeapFree
0x180099b56  test    r15, r15
0x180099b59  jz      short loc_180099B6F
0x180099b5b  call    cs:__imp_GetProcessHeap
0x180099b61  mov     r8, r15; lpMem
0x180099b64  xor     edx, edx; dwFlags
0x180099b66  mov     rcx, rax; hHeap
0x180099b69  call    cs:__imp_HeapFree
0x180099b6f  mov     eax, ebx
0x180099b71  mov     rbx, [rsp+30h+arg_0]
0x180099b76  add     rsp, 30h
0x180099b7a  pop     r15
0x180099b7c  pop     r14
0x180099b7e  pop     rdi
0x180099b7f  pop     rsi
0x180099b80  pop     rbp
0x180099b81  retn
```
