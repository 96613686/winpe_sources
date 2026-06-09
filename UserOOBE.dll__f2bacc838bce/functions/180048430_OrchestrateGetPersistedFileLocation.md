# OrchestrateGetPersistedFileLocation

- ea: `0x180048430`
- end: `0x180048594`
- name: `OrchestrateGetPersistedFileLocation`
- size: `356`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180048650`

## callees

- `0x180047bd0`
- `0x180048430`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004844e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004844e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048467`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048467`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800484af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048512`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800484af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048512`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048520`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048520`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800484c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800484c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048560`

## string_xrefs

- `0x1800484fc`: `OrchestrateGetPersistedFileLocation: Failed to retrieve redirected path, lResult=0x%x`
- `0x18004843d`: `api-ms-win-stateseparation-helpers-l1-1-0.dll`
- `0x180048566`: `OrchestrateGetPersistedFileLocation: Failed to get handle to api-ms-win-stateseparation-helpers-l1-1-0.dll, GLE = 0x%x`
- `0x180048557`: `OrchestrateGetPersistedFileLocation: Failed to get procedure GetPersistedRegistryLocationW from api-ms-win-stateseparation-helpers-l1-1-0.dll, GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall OrchestrateGetPersistedFileLocation(SIZE_T a1, _QWORD *a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v5)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rbp
  unsigned int v6; // eax
  int v7; // ebx
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  void *v10; // rdi
  unsigned int v11; // eax
  HANDLE v12; // rax
  DWORD LastError; // eax
  const wchar_t *v14; // rdx
  SIZE_T dwBytes; // [rsp+60h] [rbp+8h] BYREF

  dwBytes = a1;
  *a2 = 0;
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-stateseparation-helpers-l1-1-0.dll");
  if ( !ModuleHandleW )
  {
    LastError = GetLastError();
    v14 = L"OrchestrateGetPersistedFileLocation: Failed to get handle to api-ms-win-stateseparation-helpers-l1-1-0.dll, GLE = 0x%x";
    goto LABEL_13;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "GetPersistedFileLocationW");
  v5 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    v14 = L"OrchestrateGetPersistedFileLocation: Failed to get procedure GetPersistedRegistryLocationW from api-ms-win-sta"
           "teseparation-helpers-l1-1-0.dll, GLE = 0x%x";
LABEL_13:
    v7 = LastError;
    UnattendLogW(1, v14, LastError);
    goto LABEL_14;
  }
  LODWORD(dwBytes) = 0;
  v6 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, _QWORD, SIZE_T *))ProcAddress)(
         L"WindowsSetupState",
         0,
         0,
         0,
         &dwBytes);
  v7 = v6;
  if ( v6 != 234 )
  {
    if ( v6 == 2 )
    {
      LOWORD(v7) = 1168;
      return (unsigned __int16)v7 | 0x80070000;
    }
    UnattendLogW(
      1,
      L"OrchestrateGetPersistedFileLocation: Failed to find a redirection mapping for [%s], lResult=0x%x",
      L"WindowsSetupState",
      v6);
LABEL_14:
    if ( v7 <= 0 )
      return (unsigned int)v7;
    return (unsigned __int16)v7 | 0x80070000;
  }
  v8 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 8u, v8);
  v11 = v5(L"WindowsSetupState", 0, v10, (unsigned int)dwBytes, 0);
  v7 = v11;
  if ( v11 )
  {
    UnattendLogW(1, L"OrchestrateGetPersistedFileLocation: Failed to retrieve redirected path, lResult=0x%x", v11);
    if ( v10 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v10);
    }
    goto LABEL_14;
  }
  *a2 = v10;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180048430  mov     [rsp+dwBytes], rcx
0x180048435  push    rbx
0x180048436  push    rbp
0x180048437  push    rsi
0x180048438  push    rdi
0x180048439  sub     rsp, 38h
0x18004843d  lea     rcx, aApiMsWinStates_1; "api-ms-win-stateseparation-helpers-l1-1"...
0x180048444  mov     qword ptr [rdx], 0
0x18004844b  mov     rsi, rdx
0x18004844e  call    cs:__imp_GetModuleHandleW
0x180048454  test    rax, rax
0x180048457  jz      loc_180048560
0x18004845d  lea     rdx, aGetpersistedfi; "GetPersistedFileLocationW"
0x180048464  mov     rcx, rax; hModule
0x180048467  call    cs:__imp_GetProcAddress
0x18004846d  mov     rbp, rax
0x180048470  test    rax, rax
0x180048473  jz      loc_180048551
0x180048479  lea     rax, [rsp+58h+dwBytes]
0x18004847e  mov     dword ptr [rsp+58h+dwBytes], 0
0x180048486  mov     [rsp+58h+var_38], rax
0x18004848b  lea     rcx, aWindowssetupst; "WindowsSetupState"
0x180048492  mov     rax, rbp
0x180048495  xor     r9d, r9d
0x180048498  xor     r8d, r8d
0x18004849b  xor     edx, edx
0x18004849d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484a2  mov     ebx, eax
0x1800484a4  cmp     eax, 0EAh
0x1800484a9  jnz     short loc_180048528
0x1800484ab  mov     ebx, dword ptr [rsp+58h+dwBytes]
0x1800484af  call    cs:__imp_GetProcessHeap
0x1800484b5  mov     r8d, ebx; dwBytes
0x1800484b8  mov     edx, 8; dwFlags
0x1800484bd  mov     rcx, rax; hHeap
0x1800484c0  call    cs:__imp_HeapAlloc
0x1800484c6  mov     r9d, dword ptr [rsp+58h+dwBytes]
0x1800484cb  lea     rcx, aWindowssetupst; "WindowsSetupState"
0x1800484d2  mov     rdi, rax
0x1800484d5  mov     [rsp+58h+var_38], 0
0x1800484de  mov     r8, rax
0x1800484e1  xor     edx, edx
0x1800484e3  mov     rax, rbp
0x1800484e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484eb  mov     ebx, eax
0x1800484ed  test    eax, eax
0x1800484ef  jnz     short loc_1800484F9
0x1800484f1  mov     [rsi], rdi
0x1800484f4  jmp     loc_180048589
0x1800484f9  mov     r8d, eax
0x1800484fc  lea     rdx, aOrchestrateget_0; "OrchestrateGetPersistedFileLocation: Fa"...
0x180048503  mov     ecx, 1
0x180048508  call    UnattendLogW
0x18004850d  test    rdi, rdi
0x180048510  jz      short loc_18004857C
0x180048512  call    cs:__imp_GetProcessHeap
0x180048518  mov     r8, rdi; lpMem
0x18004851b  xor     edx, edx; dwFlags
0x18004851d  mov     rcx, rax; hHeap
0x180048520  call    cs:__imp_HeapFree
0x180048526  jmp     short loc_18004857C
0x180048528  cmp     eax, 2
0x18004852b  jnz     short loc_180048534
0x18004852d  mov     ebx, 490h
0x180048532  jmp     short loc_180048580
0x180048534  mov     r9d, eax
0x180048537  lea     r8, aWindowssetupst; "WindowsSetupState"
0x18004853e  lea     rdx, aOrchestrateget_1; "OrchestrateGetPersistedFileLocation: Fa"...
0x180048545  mov     ecx, 1
0x18004854a  call    UnattendLogW
0x18004854f  jmp     short loc_18004857C
0x180048551  call    cs:__imp_GetLastError
0x180048557  lea     rdx, aOrchestrateget_2; "OrchestrateGetPersistedFileLocation: Fa"...
0x18004855e  jmp     short loc_18004856D
0x180048560  call    cs:__imp_GetLastError
0x180048566  lea     rdx, aOrchestrateget; "OrchestrateGetPersistedFileLocation: Fa"...
0x18004856d  mov     r8d, eax
0x180048570  mov     ecx, 1
0x180048575  mov     ebx, eax
0x180048577  call    UnattendLogW
0x18004857c  test    ebx, ebx
0x18004857e  jle     short loc_180048589
0x180048580  movzx   ebx, bx
0x180048583  or      ebx, 80070000h
0x180048589  mov     eax, ebx
0x18004858b  add     rsp, 38h
0x18004858f  pop     rdi
0x180048590  pop     rsi
0x180048591  pop     rbp
0x180048592  pop     rbx
0x180048593  retn
```
