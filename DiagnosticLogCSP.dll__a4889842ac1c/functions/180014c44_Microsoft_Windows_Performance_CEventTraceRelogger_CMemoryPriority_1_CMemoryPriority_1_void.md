# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)

- ea: `0x180014c44`
- end: `0x180014d39`
- name: `??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `245`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018c40`

## callees

- `0x180014c44`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c82`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014c82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014ca6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014cb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014ca6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014cd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014d0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014cd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014d0d`

## string_xrefs

- `0x180014c7b`: `kernelbase.dll`
- `0x180014c51`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x180014c66`: `kernel32.dll`
- `0x180014c9c`: `SetThreadInformation`
- `0x180014cac`: `GetThreadInformation`

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
0x180014c44  mov     [rsp+arg_8], rbx
0x180014c49  push    rdi
0x180014c4a  sub     rsp, 30h
0x180014c4e  mov     rdi, rcx
0x180014c51  lea     rcx, aApiMsWinCorePr_2; "api-ms-win-core-processthreads-l1-1-3.d"...
0x180014c58  call    cs:__imp_GetModuleHandleW
0x180014c5e  mov     rbx, rax
0x180014c61  test    rax, rax
0x180014c64  jnz     short loc_180014C8B
0x180014c66  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180014c6d  call    cs:__imp_GetModuleHandleW
0x180014c73  mov     rbx, rax
0x180014c76  test    rax, rax
0x180014c79  jnz     short loc_180014C8B
0x180014c7b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180014c82  call    cs:__imp_GetModuleHandleW
0x180014c88  mov     rbx, rax
0x180014c8b  test    rbx, rbx
0x180014c8e  jnz     short loc_180014C9C
0x180014c90  mov     [rdi], rbx
0x180014c93  mov     [rdi+8], rbx
0x180014c97  jmp     loc_180014D2B
0x180014c9c  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x180014ca3  mov     rcx, rbx; hModule
0x180014ca6  call    cs:__imp_GetProcAddress
0x180014cac  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x180014cb3  mov     rcx, rbx; hModule
0x180014cb6  mov     [rdi], rax
0x180014cb9  call    cs:__imp_GetProcAddress
0x180014cbf  cmp     qword ptr [rdi], 0
0x180014cc3  mov     rbx, rax
0x180014cc6  mov     [rdi+8], rax
0x180014cca  jz      short loc_180014D2B
0x180014ccc  test    rax, rax
0x180014ccf  jz      short loc_180014D2B
0x180014cd1  mov     [rsp+38h+arg_0], 0
0x180014cd9  call    cs:__imp_GetCurrentThread
0x180014cdf  mov     r9d, 4
0x180014ce5  lea     r8, [rsp+38h+arg_0]
0x180014cea  mov     rcx, rax
0x180014ced  xor     edx, edx
0x180014cef  mov     rax, rbx
0x180014cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cf7  test    eax, eax
0x180014cf9  jz      short loc_180014D2B
0x180014cfb  mov     eax, [rsp+38h+arg_0]
0x180014cff  mov     rbx, [rdi]
0x180014d02  mov     [rdi+10h], eax
0x180014d05  mov     [rsp+38h+arg_0], 1
0x180014d0d  call    cs:__imp_GetCurrentThread
0x180014d13  mov     r9d, 4
0x180014d19  lea     r8, [rsp+38h+arg_0]
0x180014d1e  mov     rcx, rax
0x180014d21  xor     edx, edx
0x180014d23  mov     rax, rbx
0x180014d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d2b  mov     rbx, [rsp+38h+arg_8]
0x180014d30  mov     rax, rdi
0x180014d33  add     rsp, 30h
0x180014d37  pop     rdi
0x180014d38  retn
```
