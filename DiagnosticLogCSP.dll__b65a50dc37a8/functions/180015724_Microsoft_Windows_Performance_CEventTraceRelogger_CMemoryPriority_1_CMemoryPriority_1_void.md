# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)

- ea: `0x180015724`
- end: `0x180015844`
- name: `??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800199c0`

## callees

- `0x180015724`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015738`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015753`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001576e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015738`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015753`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001576e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015798`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800157b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015798`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800157b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800157d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800157d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015811`

## string_xrefs

- `0x180015767`: `kernelbase.dll`
- `0x180015731`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x18001574c`: `kernel32.dll`
- `0x18001578e`: `SetThreadInformation`
- `0x1800157a4`: `GetThreadInformation`

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
0x180015724  mov     [rsp+arg_8], rbx
0x180015729  push    rdi
0x18001572a  sub     rsp, 30h
0x18001572e  mov     rdi, rcx
0x180015731  lea     rcx, aApiMsWinCorePr_2; "api-ms-win-core-processthreads-l1-1-3.d"...
0x180015738  call    cs:__imp_GetModuleHandleW
0x18001573f  nop     dword ptr [rax+rax+00h]
0x180015744  mov     rbx, rax
0x180015747  test    rax, rax
0x18001574a  jnz     short loc_18001577D
0x18001574c  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180015753  call    cs:__imp_GetModuleHandleW
0x18001575a  nop     dword ptr [rax+rax+00h]
0x18001575f  mov     rbx, rax
0x180015762  test    rax, rax
0x180015765  jnz     short loc_18001577D
0x180015767  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001576e  call    cs:__imp_GetModuleHandleW
0x180015775  nop     dword ptr [rax+rax+00h]
0x18001577a  mov     rbx, rax
0x18001577d  test    rbx, rbx
0x180015780  jnz     short loc_18001578E
0x180015782  mov     [rdi], rbx
0x180015785  mov     [rdi+8], rbx
0x180015789  jmp     loc_180015835
0x18001578e  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x180015795  mov     rcx, rbx; hModule
0x180015798  call    cs:__imp_GetProcAddress
0x18001579f  nop     dword ptr [rax+rax+00h]
0x1800157a4  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x1800157ab  mov     rcx, rbx; hModule
0x1800157ae  mov     [rdi], rax
0x1800157b1  call    cs:__imp_GetProcAddress
0x1800157b8  nop     dword ptr [rax+rax+00h]
0x1800157bd  cmp     qword ptr [rdi], 0
0x1800157c1  mov     rbx, rax
0x1800157c4  mov     [rdi+8], rax
0x1800157c8  jz      short loc_180015835
0x1800157ca  test    rax, rax
0x1800157cd  jz      short loc_180015835
0x1800157cf  mov     [rsp+38h+arg_0], 0
0x1800157d7  call    cs:__imp_GetCurrentThread
0x1800157de  nop     dword ptr [rax+rax+00h]
0x1800157e3  mov     r9d, 4
0x1800157e9  lea     r8, [rsp+38h+arg_0]
0x1800157ee  mov     rcx, rax
0x1800157f1  xor     edx, edx
0x1800157f3  mov     rax, rbx
0x1800157f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157fb  test    eax, eax
0x1800157fd  jz      short loc_180015835
0x1800157ff  mov     eax, [rsp+38h+arg_0]
0x180015803  mov     rbx, [rdi]
0x180015806  mov     [rdi+10h], eax
0x180015809  mov     [rsp+38h+arg_0], 1
0x180015811  call    cs:__imp_GetCurrentThread
0x180015818  nop     dword ptr [rax+rax+00h]
0x18001581d  mov     r9d, 4
0x180015823  lea     r8, [rsp+38h+arg_0]
0x180015828  mov     rcx, rax
0x18001582b  xor     edx, edx
0x18001582d  mov     rax, rbx
0x180015830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015835  mov     rbx, [rsp+38h+arg_8]
0x18001583a  mov     rax, rdi
0x18001583d  add     rsp, 30h
0x180015841  pop     rdi
0x180015842  retn
```
