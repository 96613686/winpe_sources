# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)

- ea: `0x180072b60`
- end: `0x180072c55`
- name: `??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `245`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f3e0`

## callees

- `0x180072b60`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180072b74`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180072b89`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180072b9e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180072b74`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180072b89`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180072b9e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180072bc2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180072bd5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180072bc2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180072bd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072bf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072c29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072bf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072c29`

## string_xrefs

- `0x180072b97`: `kernelbase.dll`
- `0x180072b6d`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x180072b82`: `kernel32.dll`
- `0x180072bb8`: `SetThreadInformation`
- `0x180072bc8`: `GetThreadInformation`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(
        __int64 a1)
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rax
  bool v4; // zf
  unsigned int (__fastcall *v5)(_QWORD, _QWORD, _QWORD, _QWORD); // rbx
  HANDLE CurrentThread; // rax
  void (__fastcall *v7)(HANDLE, _QWORD, int *, __int64); // rbx
  HANDLE v8; // rax
  int v10; // [rsp+40h] [rbp+8h] BYREF

  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  }
  if ( ModuleHandleW )
  {
    *(_QWORD *)a1 = GetProcAddress(ModuleHandleW, "SetThreadInformation");
    ProcAddress = GetProcAddress(ModuleHandleW, "GetThreadInformation");
    v4 = *(_QWORD *)a1 == 0;
    v5 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    *(_QWORD *)(a1 + 8) = ProcAddress;
    if ( !v4 )
    {
      if ( ProcAddress )
      {
        v10 = 0;
        CurrentThread = GetCurrentThread();
        if ( v5(CurrentThread, 0, &v10, 4) )
        {
          v7 = *(void (__fastcall **)(HANDLE, _QWORD, int *, __int64))a1;
          *(_DWORD *)(a1 + 16) = v10;
          v10 = 1;
          v8 = GetCurrentThread();
          v7(v8, 0, &v10, 4);
        }
      }
    }
  }
  else
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180072b60  mov     [rsp+arg_8], rbx
0x180072b65  push    rdi
0x180072b66  sub     rsp, 30h
0x180072b6a  mov     rdi, rcx
0x180072b6d  lea     rcx, aApiMsWinCorePr_4; "api-ms-win-core-processthreads-l1-1-3.d"...
0x180072b74  call    cs:__imp_GetModuleHandleW
0x180072b7a  mov     rbx, rax
0x180072b7d  test    rax, rax
0x180072b80  jnz     short loc_180072BA7
0x180072b82  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180072b89  call    cs:__imp_GetModuleHandleW
0x180072b8f  mov     rbx, rax
0x180072b92  test    rax, rax
0x180072b95  jnz     short loc_180072BA7
0x180072b97  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180072b9e  call    cs:__imp_GetModuleHandleW
0x180072ba4  mov     rbx, rax
0x180072ba7  test    rbx, rbx
0x180072baa  jnz     short loc_180072BB8
0x180072bac  mov     [rdi], rbx
0x180072baf  mov     [rdi+8], rbx
0x180072bb3  jmp     loc_180072C47
0x180072bb8  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x180072bbf  mov     rcx, rbx; hModule
0x180072bc2  call    cs:__imp_GetProcAddress
0x180072bc8  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x180072bcf  mov     rcx, rbx; hModule
0x180072bd2  mov     [rdi], rax
0x180072bd5  call    cs:__imp_GetProcAddress
0x180072bdb  cmp     qword ptr [rdi], 0
0x180072bdf  mov     rbx, rax
0x180072be2  mov     [rdi+8], rax
0x180072be6  jz      short loc_180072C47
0x180072be8  test    rax, rax
0x180072beb  jz      short loc_180072C47
0x180072bed  mov     [rsp+38h+arg_0], 0
0x180072bf5  call    cs:__imp_GetCurrentThread
0x180072bfb  mov     r9d, 4
0x180072c01  lea     r8, [rsp+38h+arg_0]
0x180072c06  mov     rcx, rax
0x180072c09  xor     edx, edx
0x180072c0b  mov     rax, rbx
0x180072c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c13  test    eax, eax
0x180072c15  jz      short loc_180072C47
0x180072c17  mov     eax, [rsp+38h+arg_0]
0x180072c1b  mov     rbx, [rdi]
0x180072c1e  mov     [rdi+10h], eax
0x180072c21  mov     [rsp+38h+arg_0], 1
0x180072c29  call    cs:__imp_GetCurrentThread
0x180072c2f  mov     r9d, 4
0x180072c35  lea     r8, [rsp+38h+arg_0]
0x180072c3a  mov     rcx, rax
0x180072c3d  xor     edx, edx
0x180072c3f  mov     rax, rbx
0x180072c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c47  mov     rbx, [rsp+38h+arg_8]
0x180072c4c  mov     rax, rdi
0x180072c4f  add     rsp, 30h
0x180072c53  pop     rdi
0x180072c54  retn
```
