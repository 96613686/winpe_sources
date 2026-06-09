# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005f80`
- end: `0x180005fd8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005f80`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005faf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005faf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f9f`

## string_xrefs

- `0x180005f95`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x180005f80  mov     [rsp+arg_0], rbx
0x180005f85  mov     [rsp+arg_8], rsi
0x180005f8a  push    rdi
0x180005f8b  sub     rsp, 20h
0x180005f8f  mov     rsi, rcx
0x180005f92  mov     ebx, r8d
0x180005f95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005f9c  mov     rdi, rdx
0x180005f9f  call    cs:__imp_GetModuleHandleW
0x180005fa5  mov     rcx, rax; hModule
0x180005fa8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180005faf  call    cs:__imp_GetProcAddress
0x180005fb5  test    rax, rax
0x180005fb8  jz      short loc_180005FC8
0x180005fba  mov     r8d, ebx
0x180005fbd  mov     rdx, rdi
0x180005fc0  mov     rcx, rsi
0x180005fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc8  mov     rbx, [rsp+28h+arg_0]
0x180005fcd  mov     rsi, [rsp+28h+arg_8]
0x180005fd2  add     rsp, 20h
0x180005fd6  pop     rdi
0x180005fd7  retn
```
