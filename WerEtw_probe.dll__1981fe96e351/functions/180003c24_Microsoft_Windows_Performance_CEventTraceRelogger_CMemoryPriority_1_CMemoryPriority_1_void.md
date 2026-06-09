# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)

- ea: `0x180003c24`
- end: `0x180003d19`
- name: `??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007790`

## callees

- `0x180003c24`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003ced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003ced`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003c38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003c4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003c62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003c38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003c4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003c62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c99`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c99`

## string_xrefs

- `0x180003c31`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x180003c46`: `kernel32.dll`
- `0x180003c5b`: `kernelbase.dll`
- `0x180003c7c`: `SetThreadInformation`
- `0x180003c8c`: `GetThreadInformation`

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
0x180003c24  mov     [rsp+arg_8], rbx
0x180003c29  push    rdi
0x180003c2a  sub     rsp, 30h
0x180003c2e  mov     rdi, rcx
0x180003c31  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-3.d"...
0x180003c38  call    cs:__imp_GetModuleHandleW
0x180003c3e  mov     rbx, rax
0x180003c41  test    rax, rax
0x180003c44  jnz     short loc_180003C6B
0x180003c46  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003c4d  call    cs:__imp_GetModuleHandleW
0x180003c53  mov     rbx, rax
0x180003c56  test    rax, rax
0x180003c59  jnz     short loc_180003C6B
0x180003c5b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180003c62  call    cs:__imp_GetModuleHandleW
0x180003c68  mov     rbx, rax
0x180003c6b  test    rbx, rbx
0x180003c6e  jnz     short loc_180003C7C
0x180003c70  mov     [rdi], rbx
0x180003c73  mov     [rdi+8], rbx
0x180003c77  jmp     loc_180003D0B
0x180003c7c  lea     rdx, ProcName; "SetThreadInformation"
0x180003c83  mov     rcx, rbx; hModule
0x180003c86  call    cs:__imp_GetProcAddress
0x180003c8c  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x180003c93  mov     rcx, rbx; hModule
0x180003c96  mov     [rdi], rax
0x180003c99  call    cs:__imp_GetProcAddress
0x180003c9f  cmp     qword ptr [rdi], 0
0x180003ca3  mov     rbx, rax
0x180003ca6  mov     [rdi+8], rax
0x180003caa  jz      short loc_180003D0B
0x180003cac  test    rax, rax
0x180003caf  jz      short loc_180003D0B
0x180003cb1  mov     [rsp+38h+arg_0], 0
0x180003cb9  call    cs:__imp_GetCurrentThread
0x180003cbf  mov     r9d, 4
0x180003cc5  lea     r8, [rsp+38h+arg_0]
0x180003cca  mov     rcx, rax
0x180003ccd  xor     edx, edx
0x180003ccf  mov     rax, rbx
0x180003cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cd7  test    eax, eax
0x180003cd9  jz      short loc_180003D0B
0x180003cdb  mov     eax, [rsp+38h+arg_0]
0x180003cdf  mov     rbx, [rdi]
0x180003ce2  mov     [rdi+10h], eax
0x180003ce5  mov     [rsp+38h+arg_0], 1
0x180003ced  call    cs:__imp_GetCurrentThread
0x180003cf3  mov     r9d, 4
0x180003cf9  lea     r8, [rsp+38h+arg_0]
0x180003cfe  mov     rcx, rax
0x180003d01  xor     edx, edx
0x180003d03  mov     rax, rbx
0x180003d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d0b  mov     rbx, [rsp+38h+arg_8]
0x180003d10  mov     rax, rdi
0x180003d13  add     rsp, 30h
0x180003d17  pop     rdi
0x180003d18  retn
```
