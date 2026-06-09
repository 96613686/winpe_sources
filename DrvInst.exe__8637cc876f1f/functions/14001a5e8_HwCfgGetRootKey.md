# HwCfgGetRootKey

- ea: `0x14001a5e8`
- end: `0x14001a7d7`
- name: `HwCfgGetRootKey`
- size: `495`
- prototype: `__int64 __fastcall(REGSAM samDesired)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14001a460`
- `0x14001a534`
- `0x14001a7e0`

## callees

- `0x14001a5e8`
- `0x140047010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001a699`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001a70f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001a699`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001a70f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001a637`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001a637`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001a7be`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001a7be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001a61b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001a61b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001a6bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001a6bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a6ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a78f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a6ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a78f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a79d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a79d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a736`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a767`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a736`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a767`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a7b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a7b0`

## string_xrefs

- `0x14001a611`: `ntdll.dll`
- `0x14001a659`: `System\HardwareConfig`
- `0x14001a6e1`: `System\HardwareConfig`
- `0x14001a757`: `System\HardwareConfig`
- `0x14001a668`: `HardwareConfigState`
- `0x14001a6ef`: `HardwareConfigState`

## pseudocode

```c
__int64 __fastcall HwCfgGetRootKey(REGSAM samDesired, HKEY *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rsi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v7)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rbp
  NTSTATUS v8; // eax
  ULONG v9; // ebx
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rdi
  NTSTATUS v13; // eax
  HANDLE v14; // rax
  SIZE_T dwBytes; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  hKey = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v5 = Library;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation"),
        (v7 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))ProcAddress) == 0) )
  {
    v12 = 0;
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\HardwareConfig", 0, samDesired, &hKey);
    if ( v9 )
      goto LABEL_16;
    goto LABEL_14;
  }
  v8 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const WCHAR *, _QWORD, _QWORD, _DWORD, SIZE_T *))ProcAddress)(
         L"HardwareConfigState",
         0,
         L"System\\HardwareConfig",
         0,
         0,
         0,
         &dwBytes);
  if ( v8 >= 0 )
  {
    v9 = 1359;
    goto LABEL_16;
  }
  if ( v8 != -2147483643 )
  {
    v9 = RtlNtStatusToDosErrorNoTeb(v8);
    goto LABEL_16;
  }
  v10 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v12 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v10);
  if ( !v12 )
  {
    v9 = 8;
    goto LABEL_16;
  }
  v13 = v7(L"HardwareConfigState", 0, L"System\\HardwareConfig", 0, v12, dwBytes, &dwBytes);
  if ( v13 >= 0 )
  {
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, samDesired, &hKey);
    if ( v9 )
      goto LABEL_15;
LABEL_14:
    *a2 = hKey;
    hKey = 0;
    if ( !v12 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v9 = RtlNtStatusToDosErrorNoTeb(v13);
LABEL_15:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v12);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    FreeLibrary(v5);
  return v9;
}

```

## disassembly

```asm
0x14001a5e8  mov     rax, rsp
0x14001a5eb  mov     [rax+8], rbx
0x14001a5ef  push    rbp
0x14001a5f0  push    rsi
0x14001a5f1  push    rdi
0x14001a5f2  push    r14
0x14001a5f4  push    r15
0x14001a5f6  sub     rsp, 40h
0x14001a5fa  mov     r15, rdx
0x14001a5fd  mov     dword ptr [rax+18h], 0
0x14001a604  mov     r14d, ecx
0x14001a607  mov     qword ptr [rax+20h], 0
0x14001a60f  xor     edx, edx; hFile
0x14001a611  lea     rcx, LibFileName; "ntdll.dll"
0x14001a618  xor     r8d, r8d; dwFlags
0x14001a61b  call    cs:__imp_LoadLibraryExW
0x14001a621  mov     rsi, rax
0x14001a624  test    rax, rax
0x14001a627  jz      loc_14001A744
0x14001a62d  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x14001a634  mov     rcx, rax; hModule
0x14001a637  call    cs:__imp_GetProcAddress
0x14001a63d  mov     rbp, rax
0x14001a640  test    rax, rax
0x14001a643  jz      loc_14001A744
0x14001a649  lea     rax, [rsp+68h+dwBytes]
0x14001a651  xor     r9d, r9d
0x14001a654  mov     [rsp+68h+var_38], rax
0x14001a659  lea     r8, SubKey; "System\\HardwareConfig"
0x14001a660  mov     [rsp+68h+var_40], 0
0x14001a668  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x14001a66f  mov     rax, rbp
0x14001a672  mov     [rsp+68h+phkResult], 0
0x14001a67b  xor     edx, edx
0x14001a67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a682  test    eax, eax
0x14001a684  js      short loc_14001A690
0x14001a686  mov     ebx, 54Fh
0x14001a68b  jmp     loc_14001A7A3
0x14001a690  cmp     eax, 80000005h
0x14001a695  jz      short loc_14001A6A6
0x14001a697  mov     ecx, eax; Status
0x14001a699  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14001a69f  mov     ebx, eax
0x14001a6a1  jmp     loc_14001A7A3
0x14001a6a6  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x14001a6ad  call    cs:__imp_GetProcessHeap
0x14001a6b3  mov     r8d, ebx; dwBytes
0x14001a6b6  xor     edx, edx; dwFlags
0x14001a6b8  mov     rcx, rax; hHeap
0x14001a6bb  call    cs:__imp_HeapAlloc
0x14001a6c1  mov     rdi, rax
0x14001a6c4  test    rax, rax
0x14001a6c7  jnz     short loc_14001A6D1
0x14001a6c9  lea     ebx, [rax+8]
0x14001a6cc  jmp     loc_14001A7A3
0x14001a6d1  lea     rax, [rsp+68h+dwBytes]
0x14001a6d9  xor     r9d, r9d
0x14001a6dc  mov     [rsp+68h+var_38], rax
0x14001a6e1  lea     r8, SubKey; "System\\HardwareConfig"
0x14001a6e8  mov     eax, dword ptr [rsp+68h+dwBytes]
0x14001a6ef  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x14001a6f6  mov     [rsp+68h+var_40], eax
0x14001a6fa  xor     edx, edx
0x14001a6fc  mov     rax, rbp
0x14001a6ff  mov     [rsp+68h+phkResult], rdi
0x14001a704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a709  test    eax, eax
0x14001a70b  jns     short loc_14001A719
0x14001a70d  mov     ecx, eax; Status
0x14001a70f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14001a715  mov     ebx, eax
0x14001a717  jmp     short loc_14001A78F
0x14001a719  lea     rax, [rsp+68h+hKey]
0x14001a721  mov     r9d, r14d; samDesired
0x14001a724  xor     r8d, r8d; ulOptions
0x14001a727  mov     [rsp+68h+phkResult], rax; phkResult
0x14001a72c  mov     rdx, rdi; lpSubKey
0x14001a72f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001a736  call    cs:__imp_RegOpenKeyExW
0x14001a73c  mov     ebx, eax
0x14001a73e  test    eax, eax
0x14001a740  jnz     short loc_14001A78F
0x14001a742  jmp     short loc_14001A773
0x14001a744  lea     rax, [rsp+68h+hKey]
0x14001a74c  mov     r9d, r14d; samDesired
0x14001a74f  xor     r8d, r8d; ulOptions
0x14001a752  mov     [rsp+68h+phkResult], rax; phkResult
0x14001a757  lea     rdx, SubKey; "System\\HardwareConfig"
0x14001a75e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001a765  xor     edi, edi
0x14001a767  call    cs:__imp_RegOpenKeyExW
0x14001a76d  mov     ebx, eax
0x14001a76f  test    eax, eax
0x14001a771  jnz     short loc_14001A7A3
0x14001a773  mov     rax, [rsp+68h+hKey]
0x14001a77b  mov     [r15], rax
0x14001a77e  mov     [rsp+68h+hKey], 0
0x14001a78a  test    rdi, rdi
0x14001a78d  jz      short loc_14001A7A3
0x14001a78f  call    cs:__imp_GetProcessHeap
0x14001a795  mov     r8, rdi; lpMem
0x14001a798  xor     edx, edx; dwFlags
0x14001a79a  mov     rcx, rax; hHeap
0x14001a79d  call    cs:__imp_HeapFree
0x14001a7a3  mov     rcx, [rsp+68h+hKey]; hKey
0x14001a7ab  test    rcx, rcx
0x14001a7ae  jz      short loc_14001A7B6
0x14001a7b0  call    cs:__imp_RegCloseKey
0x14001a7b6  test    rsi, rsi
0x14001a7b9  jz      short loc_14001A7C4
0x14001a7bb  mov     rcx, rsi; hLibModule
0x14001a7be  call    cs:__imp_FreeLibrary
0x14001a7c4  mov     eax, ebx
0x14001a7c6  mov     rbx, [rsp+68h+arg_0]
0x14001a7cb  add     rsp, 40h
0x14001a7cf  pop     r15
0x14001a7d1  pop     r14
0x14001a7d3  pop     rdi
0x14001a7d4  pop     rsi
0x14001a7d5  pop     rbp
0x14001a7d6  retn
```
