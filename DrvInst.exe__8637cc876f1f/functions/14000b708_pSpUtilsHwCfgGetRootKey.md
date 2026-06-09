# _pSpUtilsHwCfgGetRootKey

- ea: `0x14000b708`
- end: `0x14000b8d4`
- name: `_pSpUtilsHwCfgGetRootKey`
- size: `460`
- prototype: `__int64 __fastcall(__int64, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d644`

## callees

- `0x14000b708`
- `0x140047010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000b7b3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000b81c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000b7b3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000b81c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b754`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b754`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000b8be`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000b8be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000b738`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000b738`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b7ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b7ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b8a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b8a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b843`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b872`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b843`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000b872`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b8b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b8b0`

## string_xrefs

- `0x14000b731`: `ntdll.dll`
- `0x14000b773`: `System\HardwareConfig`
- `0x14000b7f1`: `System\HardwareConfig`
- `0x14000b860`: `System\HardwareConfig`
- `0x14000b782`: `HardwareConfigState`
- `0x14000b7fc`: `HardwareConfigState`

## pseudocode

```c
__int64 __fastcall pSpUtilsHwCfgGetRootKey(__int64 a1, HKEY *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rbx
  NTSTATUS v7; // eax
  ULONG v8; // ebx
  WCHAR *v9; // rdi
  NTSTATUS v10; // eax
  SIZE_T dwBytes; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  hKey = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v4 = Library;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation"),
        (v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))ProcAddress) == 0) )
  {
    v9 = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\HardwareConfig", 0, 1u, &hKey);
    if ( v8 )
      goto LABEL_16;
    goto LABEL_14;
  }
  v7 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const WCHAR *, _QWORD, _QWORD, _DWORD, SIZE_T *))ProcAddress)(
         L"HardwareConfigState",
         0,
         L"System\\HardwareConfig",
         0,
         0,
         0,
         &dwBytes);
  if ( v7 >= 0 )
  {
    v8 = 1359;
    goto LABEL_16;
  }
  if ( v7 != -2147483643 )
  {
    v8 = RtlNtStatusToDosErrorNoTeb(v7);
    goto LABEL_16;
  }
  v9 = (WCHAR *)HeapAlloc(hHeap, 0, (unsigned int)dwBytes);
  if ( !v9 )
  {
    v8 = 8;
    goto LABEL_16;
  }
  v10 = v6(L"HardwareConfigState", 0, L"System\\HardwareConfig", 0, v9, dwBytes, &dwBytes);
  if ( v10 >= 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 1u, &hKey);
    if ( v8 )
      goto LABEL_15;
LABEL_14:
    *a2 = hKey;
    hKey = 0;
    if ( !v9 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v8 = RtlNtStatusToDosErrorNoTeb(v10);
LABEL_15:
  HeapFree(hHeap, 0, v9);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    FreeLibrary(v4);
  return v8;
}

```

## disassembly

```asm
0x14000b708  mov     rax, rsp
0x14000b70b  mov     [rax+10h], rbx
0x14000b70f  mov     [rax+8], ecx
0x14000b712  push    rsi
0x14000b713  push    rdi
0x14000b714  push    r14
0x14000b716  sub     rsp, 40h
0x14000b71a  mov     r14, rdx
0x14000b71d  mov     dword ptr [rax+8], 0
0x14000b724  xor     edx, edx; hFile
0x14000b726  mov     qword ptr [rax+18h], 0
0x14000b72e  xor     r8d, r8d; dwFlags
0x14000b731  lea     rcx, LibFileName; "ntdll.dll"
0x14000b738  call    cs:__imp_LoadLibraryExW
0x14000b73e  mov     rsi, rax
0x14000b741  test    rax, rax
0x14000b744  jz      loc_14000B851
0x14000b74a  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x14000b751  mov     rcx, rax; hModule
0x14000b754  call    cs:__imp_GetProcAddress
0x14000b75a  mov     rbx, rax
0x14000b75d  test    rax, rax
0x14000b760  jz      loc_14000B851
0x14000b766  lea     rax, [rsp+58h+dwBytes]
0x14000b76b  xor     r9d, r9d
0x14000b76e  mov     [rsp+58h+var_28], rax
0x14000b773  lea     r8, SubKey; "System\\HardwareConfig"
0x14000b77a  mov     [rsp+58h+var_30], 0
0x14000b782  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x14000b789  mov     rax, rbx
0x14000b78c  mov     [rsp+58h+phkResult], 0
0x14000b795  xor     edx, edx
0x14000b797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b79c  test    eax, eax
0x14000b79e  js      short loc_14000B7AA
0x14000b7a0  mov     ebx, 54Fh
0x14000b7a5  jmp     loc_14000B8A6
0x14000b7aa  cmp     eax, 80000005h
0x14000b7af  jz      short loc_14000B7C0
0x14000b7b1  mov     ecx, eax; Status
0x14000b7b3  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14000b7b9  mov     ebx, eax
0x14000b7bb  jmp     loc_14000B8A6
0x14000b7c0  mov     r8d, dword ptr [rsp+58h+dwBytes]; dwBytes
0x14000b7c5  xor     edx, edx; dwFlags
0x14000b7c7  mov     rcx, cs:hHeap; hHeap
0x14000b7ce  call    cs:__imp_HeapAlloc
0x14000b7d4  mov     rdi, rax
0x14000b7d7  test    rax, rax
0x14000b7da  jnz     short loc_14000B7E4
0x14000b7dc  lea     ebx, [rax+8]
0x14000b7df  jmp     loc_14000B8A6
0x14000b7e4  lea     rax, [rsp+58h+dwBytes]
0x14000b7e9  xor     r9d, r9d
0x14000b7ec  mov     [rsp+58h+var_28], rax
0x14000b7f1  lea     r8, SubKey; "System\\HardwareConfig"
0x14000b7f8  mov     eax, dword ptr [rsp+58h+dwBytes]
0x14000b7fc  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x14000b803  mov     [rsp+58h+var_30], eax
0x14000b807  xor     edx, edx
0x14000b809  mov     rax, rbx
0x14000b80c  mov     [rsp+58h+phkResult], rdi
0x14000b811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b816  test    eax, eax
0x14000b818  jns     short loc_14000B826
0x14000b81a  mov     ecx, eax; Status
0x14000b81c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14000b822  mov     ebx, eax
0x14000b824  jmp     short loc_14000B894
0x14000b826  lea     rax, [rsp+58h+hKey]
0x14000b82b  mov     r9d, 1; samDesired
0x14000b831  xor     r8d, r8d; ulOptions
0x14000b834  mov     [rsp+58h+phkResult], rax; phkResult
0x14000b839  mov     rdx, rdi; lpSubKey
0x14000b83c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000b843  call    cs:__imp_RegOpenKeyExW
0x14000b849  mov     ebx, eax
0x14000b84b  test    eax, eax
0x14000b84d  jnz     short loc_14000B894
0x14000b84f  jmp     short loc_14000B87E
0x14000b851  lea     rax, [rsp+58h+hKey]
0x14000b856  xor     edi, edi
0x14000b858  xor     r8d, r8d; ulOptions
0x14000b85b  mov     [rsp+58h+phkResult], rax; phkResult
0x14000b860  lea     rdx, SubKey; "System\\HardwareConfig"
0x14000b867  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000b86e  lea     r9d, [rdi+1]; samDesired
0x14000b872  call    cs:__imp_RegOpenKeyExW
0x14000b878  mov     ebx, eax
0x14000b87a  test    eax, eax
0x14000b87c  jnz     short loc_14000B8A6
0x14000b87e  mov     rax, [rsp+58h+hKey]
0x14000b883  mov     [r14], rax
0x14000b886  mov     [rsp+58h+hKey], 0
0x14000b88f  test    rdi, rdi
0x14000b892  jz      short loc_14000B8A6
0x14000b894  mov     rcx, cs:hHeap; hHeap
0x14000b89b  mov     r8, rdi; lpMem
0x14000b89e  xor     edx, edx; dwFlags
0x14000b8a0  call    cs:__imp_HeapFree
0x14000b8a6  mov     rcx, [rsp+58h+hKey]; hKey
0x14000b8ab  test    rcx, rcx
0x14000b8ae  jz      short loc_14000B8B6
0x14000b8b0  call    cs:__imp_RegCloseKey
0x14000b8b6  test    rsi, rsi
0x14000b8b9  jz      short loc_14000B8C4
0x14000b8bb  mov     rcx, rsi; hLibModule
0x14000b8be  call    cs:__imp_FreeLibrary
0x14000b8c4  mov     eax, ebx
0x14000b8c6  mov     rbx, [rsp+58h+arg_8]
0x14000b8cb  add     rsp, 40h
0x14000b8cf  pop     r14
0x14000b8d1  pop     rdi
0x14000b8d2  pop     rsi
0x14000b8d3  retn
```
