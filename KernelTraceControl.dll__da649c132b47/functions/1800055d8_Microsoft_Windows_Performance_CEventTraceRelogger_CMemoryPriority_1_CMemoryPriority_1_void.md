# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)

- ea: `0x1800055d8`
- end: `0x1800056c7`
- name: `??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002fa0`

## callees

- `0x1800055d8`
- `0x180027910`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180005668`
- `KERNEL32!GetCurrentThread` at `0x18000569d`
- `KERNEL32!GetCurrentThread` at `0x180005668`
- `KERNEL32!GetCurrentThread` at `0x18000569d`
- `KERNEL32!GetModuleHandleW` at `0x1800055ec`
- `KERNEL32!GetModuleHandleW` at `0x180005601`
- `KERNEL32!GetModuleHandleW` at `0x180005616`
- `KERNEL32!GetModuleHandleW` at `0x1800055ec`
- `KERNEL32!GetModuleHandleW` at `0x180005601`
- `KERNEL32!GetModuleHandleW` at `0x180005616`
- `KERNEL32!GetProcAddress` at `0x18000563a`
- `KERNEL32!GetProcAddress` at `0x18000564d`
- `KERNEL32!GetProcAddress` at `0x18000563a`
- `KERNEL32!GetProcAddress` at `0x18000564d`

## string_xrefs

- `0x1800055e5`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x1800055fa`: `kernel32.dll`
- `0x18000560f`: `kernelbase.dll`
- `0x180005630`: `SetThreadInformation`
- `0x180005640`: `GetThreadInformation`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(
        __int64 a1)
{
  HMODULE ModuleHandleW; // rdi
  FARPROC ProcAddress; // rax
  bool v4; // zf
  HANDLE CurrentThread; // rax
  HANDLE v6; // rax
  int v8; // [rsp+40h] [rbp+8h] BYREF

  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
  if ( ModuleHandleW
    || (ModuleHandleW = GetModuleHandleW(L"kernel32.dll")) != 0
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll")) != 0 )
  {
    *(_QWORD *)a1 = GetProcAddress(ModuleHandleW, "SetThreadInformation");
    ProcAddress = GetProcAddress(ModuleHandleW, "GetThreadInformation");
    v4 = *(_QWORD *)a1 == 0;
    *(_QWORD *)(a1 + 8) = ProcAddress;
    if ( !v4 )
    {
      if ( ProcAddress )
      {
        v8 = 0;
        CurrentThread = GetCurrentThread();
        if ( (*(unsigned int (__fastcall **)(HANDLE, _QWORD, int *, __int64))(a1 + 8))(CurrentThread, 0, &v8, 4) )
        {
          *(_DWORD *)(a1 + 16) = v8;
          v8 = 1;
          v6 = GetCurrentThread();
          (*(void (__fastcall **)(HANDLE, _QWORD, int *, __int64))a1)(v6, 0, &v8, 4);
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
0x1800055d8  mov     [rsp+arg_8], rbx
0x1800055dd  push    rdi
0x1800055de  sub     rsp, 30h
0x1800055e2  mov     rbx, rcx
0x1800055e5  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-3.d"...
0x1800055ec  call    cs:__imp_GetModuleHandleW
0x1800055f2  mov     rdi, rax
0x1800055f5  test    rax, rax
0x1800055f8  jnz     short loc_180005630
0x1800055fa  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180005601  call    cs:__imp_GetModuleHandleW
0x180005607  mov     rdi, rax
0x18000560a  test    rax, rax
0x18000560d  jnz     short loc_180005630
0x18000560f  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005616  call    cs:__imp_GetModuleHandleW
0x18000561c  mov     rdi, rax
0x18000561f  test    rax, rax
0x180005622  jnz     short loc_180005630
0x180005624  and     [rbx], rax
0x180005627  and     [rbx+8], rax
0x18000562b  jmp     loc_1800056B9
0x180005630  lea     rdx, ProcName; "SetThreadInformation"
0x180005637  mov     rcx, rdi; hModule
0x18000563a  call    cs:__imp_GetProcAddress
0x180005640  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x180005647  mov     rcx, rdi; hModule
0x18000564a  mov     [rbx], rax
0x18000564d  call    cs:__imp_GetProcAddress
0x180005653  cmp     qword ptr [rbx], 0
0x180005657  mov     [rbx+8], rax
0x18000565b  jz      short loc_1800056B9
0x18000565d  test    rax, rax
0x180005660  jz      short loc_1800056B9
0x180005662  xor     eax, eax
0x180005664  mov     [rsp+38h+arg_0], eax
0x180005668  call    cs:__imp_GetCurrentThread
0x18000566e  mov     edi, 4
0x180005673  lea     r8, [rsp+38h+arg_0]
0x180005678  mov     rcx, rax
0x18000567b  mov     r9d, edi
0x18000567e  mov     rax, [rbx+8]
0x180005682  xor     edx, edx
0x180005684  call    cs:__guard_dispatch_icall_fptr
0x18000568a  test    eax, eax
0x18000568c  jz      short loc_1800056B9
0x18000568e  mov     eax, [rsp+38h+arg_0]
0x180005692  mov     [rbx+10h], eax
0x180005695  mov     [rsp+38h+arg_0], 1
0x18000569d  call    cs:__imp_GetCurrentThread
0x1800056a3  mov     r9d, edi
0x1800056a6  lea     r8, [rsp+38h+arg_0]
0x1800056ab  mov     rcx, rax
0x1800056ae  xor     edx, edx
0x1800056b0  mov     rax, [rbx]
0x1800056b3  call    cs:__guard_dispatch_icall_fptr
0x1800056b9  mov     rax, rbx
0x1800056bc  mov     rbx, [rsp+38h+arg_8]
0x1800056c1  add     rsp, 30h
0x1800056c5  pop     rdi
0x1800056c6  retn
```
