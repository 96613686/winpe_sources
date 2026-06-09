# Concurrency::details::platform::InitializeSystemFunctionPointers(void)

- ea: `0x18030f804`
- end: `0x18030f908`
- name: `?InitializeSystemFunctionPointers@platform@details@Concurrency@@YAXXZ`
- size: `260`
- prototype: `void __fastcall(Concurrency::details::platform *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1803148a0`

## callees

- `0x18030f804`
- `0x18030fec8`
- `0x1803104c8`
- `0x18032b080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18030f8a8`
- `KERNEL32!GetLastError` at `0x18030f8d8`
- `KERNEL32!GetLastError` at `0x18030f8a8`
- `KERNEL32!GetLastError` at `0x18030f8d8`
- `KERNEL32!GetProcAddress` at `0x18030f828`
- `KERNEL32!GetProcAddress` at `0x18030f83b`
- `KERNEL32!GetProcAddress` at `0x18030f883`
- `KERNEL32!GetProcAddress` at `0x18030f828`
- `KERNEL32!GetProcAddress` at `0x18030f83b`
- `KERNEL32!GetProcAddress` at `0x18030f883`
- `KERNEL32!GetModuleHandleW` at `0x18030f815`
- `KERNEL32!GetModuleHandleW` at `0x18030f873`
- `KERNEL32!GetModuleHandleW` at `0x18030f815`
- `KERNEL32!GetModuleHandleW` at `0x18030f873`

## string_xrefs

- `0x18030f80e`: `kernel32.dll`
- `0x18030f865`: `kernel32.dll`
- `0x18030f81e`: `SetThreadGroupAffinity`
- `0x18030f82e`: `GetThreadGroupAffinity`

## pseudocode

```c
void __fastcall Concurrency::details::platform::InitializeSystemFunctionPointers(Concurrency::details::platform *this)
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v3; // rax
  FARPROC v4; // rbx
  HMODULE v5; // rax
  FARPROC v6; // rax
  signed int LastError; // eax
  unsigned int v8; // edx
  signed int v9; // eax
  unsigned int v10; // edx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "SetThreadGroupAffinity");
  v3 = GetProcAddress(ModuleHandleW, "GetThreadGroupAffinity");
  v4 = v3;
  if ( !ProcAddress || !v3 )
  {
    LastError = GetLastError();
    v8 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v8 = LastError;
    Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
      (Concurrency::scheduler_resource_allocation_error *)pExceptionObject,
      v8);
    throw (Concurrency::scheduler_resource_allocation_error *)pExceptionObject;
  }
  qword_1804C6EF8 = Concurrency::details::Security::EncodePointer(ProcAddress);
  qword_1804C6F00 = Concurrency::details::Security::EncodePointer(v4);
  v5 = GetModuleHandleW(L"kernel32.dll");
  v6 = GetProcAddress(v5, "GetCurrentProcessorNumberEx");
  if ( !v6 )
  {
    v9 = GetLastError();
    v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v10 = v9;
    Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(
      (Concurrency::scheduler_resource_allocation_error *)pExceptionObject,
      v10);
    throw (Concurrency::scheduler_resource_allocation_error *)pExceptionObject;
  }
  qword_1804C6EF0 = Concurrency::details::Security::EncodePointer(v6);
}

```

## disassembly

```asm
0x18030f804  mov     [rsp+arg_0], rbx
0x18030f809  push    rdi
0x18030f80a  sub     rsp, 40h
0x18030f80e  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18030f815  call    cs:__imp_GetModuleHandleW
0x18030f81b  mov     rcx, rax; hModule
0x18030f81e  lea     rdx, aSetthreadgroup; "SetThreadGroupAffinity"
0x18030f825  mov     rbx, rax
0x18030f828  call    cs:__imp_GetProcAddress
0x18030f82e  lea     rdx, aGetthreadgroup; "GetThreadGroupAffinity"
0x18030f835  mov     rcx, rbx; hModule
0x18030f838  mov     rdi, rax
0x18030f83b  call    cs:__imp_GetProcAddress
0x18030f841  mov     rbx, rax
0x18030f844  test    rdi, rdi
0x18030f847  jz      short loc_18030F8A8
0x18030f849  test    rax, rax
0x18030f84c  jz      short loc_18030F8A8
0x18030f84e  mov     rcx, rdi; void *
0x18030f851  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x18030f856  mov     rcx, rbx; void *
0x18030f859  mov     cs:qword_1804C6EF8, rax
0x18030f860  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x18030f865  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18030f86c  mov     cs:qword_1804C6F00, rax
0x18030f873  call    cs:__imp_GetModuleHandleW
0x18030f879  mov     rcx, rax; hModule
0x18030f87c  lea     rdx, aGetcurrentproc_0; "GetCurrentProcessorNumberEx"
0x18030f883  call    cs:__imp_GetProcAddress
0x18030f889  test    rax, rax
0x18030f88c  jz      short loc_18030F8D8
0x18030f88e  mov     rcx, rax; void *
0x18030f891  call    ?EncodePointer@Security@details@Concurrency@@SAPEAXPEAX@Z; Concurrency::details::Security::EncodePointer(void *)
0x18030f896  mov     rbx, [rsp+48h+arg_0]
0x18030f89b  mov     cs:qword_1804C6EF0, rax
0x18030f8a2  add     rsp, 40h
0x18030f8a6  pop     rdi
0x18030f8a7  retn
0x18030f8a8  call    cs:__imp_GetLastError
0x18030f8ae  movzx   edx, ax
0x18030f8b1  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18030f8b6  or      edx, 80070000h
0x18030f8bc  test    eax, eax
0x18030f8be  cmovle  edx, eax; int
0x18030f8c1  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x18030f8c6  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x18030f8cd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18030f8d2  call    _CxxThrowException
0x18030f8d8  call    cs:__imp_GetLastError
0x18030f8de  movzx   edx, ax
0x18030f8e1  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18030f8e6  or      edx, 80070000h
0x18030f8ec  test    eax, eax
0x18030f8ee  cmovle  edx, eax; int
0x18030f8f1  call    ??0scheduler_resource_allocation_error@Concurrency@@QEAA@J@Z; Concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error(long)
0x18030f8f6  lea     rdx, _TI2?AVscheduler_resource_allocation_error@Concurrency@@; pThrowInfo
0x18030f8fd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18030f902  call    _CxxThrowException
```
