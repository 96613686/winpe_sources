# HwCfgGetRootKey

- ea: `0x180075fa0`
- end: `0x18007617b`
- name: `HwCfgGetRootKey`
- size: `475`
- prototype: `__int64 __fastcall(__int64, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180075ef0`

## callees

- `0x180075fa0`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180075fd4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180075fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075ff0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180075ff0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180076160`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180076160`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007606e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007606e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076142`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076142`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076060`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076134`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076060`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076134`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800760e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076112`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800760e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076112`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076152`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007604f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800760bc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007604f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800760bc`

## string_xrefs

- `0x180075fcd`: `ntdll.dll`
- `0x18007601e`: `HardwareConfigState`
- `0x18007609c`: `HardwareConfigState`
- `0x18007600f`: `System\HardwareConfig`
- `0x180076091`: `System\HardwareConfig`
- `0x180076100`: `System\HardwareConfig`

## pseudocode

```c
__int64 __fastcall HwCfgGetRootKey(__int64 a1, HKEY *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rbp
  NTSTATUS v7; // eax
  ULONG v8; // ebx
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rdi
  NTSTATUS v12; // eax
  HANDLE v13; // rax
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
    v11 = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\HardwareConfig", 0, 8u, &hKey);
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
  v9 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v11 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v9);
  if ( !v11 )
  {
    v8 = 8;
    goto LABEL_16;
  }
  v12 = v6(L"HardwareConfigState", 0, L"System\\HardwareConfig", 0, v11, dwBytes, &dwBytes);
  if ( v12 >= 0 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 8u, &hKey);
    if ( v8 )
      goto LABEL_15;
LABEL_14:
    *a2 = hKey;
    hKey = 0;
    if ( !v11 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v8 = RtlNtStatusToDosErrorNoTeb(v12);
LABEL_15:
  v13 = GetProcessHeap();
  HeapFree(v13, 0, v11);
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
0x180075fa0  mov     rax, rsp
0x180075fa3  mov     [rax+10h], rbx
0x180075fa7  mov     [rax+20h], rbp
0x180075fab  mov     [rax+8], ecx
0x180075fae  push    rsi
0x180075faf  push    rdi
0x180075fb0  push    r14
0x180075fb2  sub     rsp, 40h
0x180075fb6  mov     r14, rdx
0x180075fb9  mov     dword ptr [rax+8], 0
0x180075fc0  xor     edx, edx; hFile
0x180075fc2  mov     qword ptr [rax+18h], 0
0x180075fca  xor     r8d, r8d; dwFlags
0x180075fcd  lea     rcx, ModuleName; "ntdll.dll"
0x180075fd4  call    cs:__imp_LoadLibraryExW
0x180075fda  mov     rsi, rax
0x180075fdd  test    rax, rax
0x180075fe0  jz      loc_1800760F1
0x180075fe6  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180075fed  mov     rcx, rax; hModule
0x180075ff0  call    cs:__imp_GetProcAddress
0x180075ff6  mov     rbp, rax
0x180075ff9  test    rax, rax
0x180075ffc  jz      loc_1800760F1
0x180076002  lea     rax, [rsp+58h+dwBytes]
0x180076007  xor     r9d, r9d
0x18007600a  mov     [rsp+58h+var_28], rax
0x18007600f  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x180076016  mov     [rsp+58h+var_30], 0
0x18007601e  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x180076025  mov     rax, rbp
0x180076028  mov     [rsp+58h+phkResult], 0
0x180076031  xor     edx, edx
0x180076033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076038  test    eax, eax
0x18007603a  js      short loc_180076046
0x18007603c  mov     ebx, 54Fh
0x180076041  jmp     loc_180076148
0x180076046  cmp     eax, 80000005h
0x18007604b  jz      short loc_18007605C
0x18007604d  mov     ecx, eax; Status
0x18007604f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180076055  mov     ebx, eax
0x180076057  jmp     loc_180076148
0x18007605c  mov     ebx, dword ptr [rsp+58h+dwBytes]
0x180076060  call    cs:__imp_GetProcessHeap
0x180076066  mov     r8d, ebx; dwBytes
0x180076069  xor     edx, edx; dwFlags
0x18007606b  mov     rcx, rax; hHeap
0x18007606e  call    cs:__imp_HeapAlloc
0x180076074  mov     rdi, rax
0x180076077  test    rax, rax
0x18007607a  jnz     short loc_180076084
0x18007607c  lea     ebx, [rax+8]
0x18007607f  jmp     loc_180076148
0x180076084  lea     rax, [rsp+58h+dwBytes]
0x180076089  xor     r9d, r9d
0x18007608c  mov     [rsp+58h+var_28], rax
0x180076091  lea     r8, aSystemHardware; "System\\HardwareConfig"
0x180076098  mov     eax, dword ptr [rsp+58h+dwBytes]
0x18007609c  lea     rcx, aHardwareconfig; "HardwareConfigState"
0x1800760a3  mov     [rsp+58h+var_30], eax
0x1800760a7  xor     edx, edx
0x1800760a9  mov     rax, rbp
0x1800760ac  mov     [rsp+58h+phkResult], rdi
0x1800760b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760b6  test    eax, eax
0x1800760b8  jns     short loc_1800760C6
0x1800760ba  mov     ecx, eax; Status
0x1800760bc  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800760c2  mov     ebx, eax
0x1800760c4  jmp     short loc_180076134
0x1800760c6  lea     rax, [rsp+58h+hKey]
0x1800760cb  mov     r9d, 8; samDesired
0x1800760d1  xor     r8d, r8d; ulOptions
0x1800760d4  mov     [rsp+58h+phkResult], rax; phkResult
0x1800760d9  mov     rdx, rdi; lpSubKey
0x1800760dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800760e3  call    cs:__imp_RegOpenKeyExW
0x1800760e9  mov     ebx, eax
0x1800760eb  test    eax, eax
0x1800760ed  jnz     short loc_180076134
0x1800760ef  jmp     short loc_18007611E
0x1800760f1  lea     rax, [rsp+58h+hKey]
0x1800760f6  xor     edi, edi
0x1800760f8  xor     r8d, r8d; ulOptions
0x1800760fb  mov     [rsp+58h+phkResult], rax; phkResult
0x180076100  lea     rdx, aSystemHardware; "System\\HardwareConfig"
0x180076107  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007610e  lea     r9d, [rdi+8]; samDesired
0x180076112  call    cs:__imp_RegOpenKeyExW
0x180076118  mov     ebx, eax
0x18007611a  test    eax, eax
0x18007611c  jnz     short loc_180076148
0x18007611e  mov     rax, [rsp+58h+hKey]
0x180076123  mov     [r14], rax
0x180076126  mov     [rsp+58h+hKey], 0
0x18007612f  test    rdi, rdi
0x180076132  jz      short loc_180076148
0x180076134  call    cs:__imp_GetProcessHeap
0x18007613a  mov     r8, rdi; lpMem
0x18007613d  xor     edx, edx; dwFlags
0x18007613f  mov     rcx, rax; hHeap
0x180076142  call    cs:__imp_HeapFree
0x180076148  mov     rcx, [rsp+58h+hKey]; hKey
0x18007614d  test    rcx, rcx
0x180076150  jz      short loc_180076158
0x180076152  call    cs:__imp_RegCloseKey
0x180076158  test    rsi, rsi
0x18007615b  jz      short loc_180076166
0x18007615d  mov     rcx, rsi; hLibModule
0x180076160  call    cs:__imp_FreeLibrary
0x180076166  mov     rbp, [rsp+58h+arg_18]
0x18007616b  mov     eax, ebx
0x18007616d  mov     rbx, [rsp+58h+arg_8]
0x180076172  add     rsp, 40h
0x180076176  pop     r14
0x180076178  pop     rdi
0x180076179  pop     rsi
0x18007617a  retn
```
