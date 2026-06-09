# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006fb0`
- end: `0x180007008`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006fb0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006fdf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006fdf`

## string_xrefs

- `0x180006fc5`: `kernelbase.dll`

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
0x180006fb0  mov     [rsp+arg_0], rbx
0x180006fb5  mov     [rsp+arg_8], rsi
0x180006fba  push    rdi
0x180006fbb  sub     rsp, 20h
0x180006fbf  mov     rsi, rcx
0x180006fc2  mov     ebx, r8d
0x180006fc5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006fcc  mov     rdi, rdx
0x180006fcf  call    cs:__imp_GetModuleHandleW
0x180006fd5  mov     rcx, rax; hModule
0x180006fd8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180006fdf  call    cs:__imp_GetProcAddress
0x180006fe5  test    rax, rax
0x180006fe8  jz      short loc_180006FF8
0x180006fea  mov     r8d, ebx
0x180006fed  mov     rdx, rdi
0x180006ff0  mov     rcx, rsi
0x180006ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff8  mov     rbx, [rsp+28h+arg_0]
0x180006ffd  mov     rsi, [rsp+28h+arg_8]
0x180007002  add     rsp, 20h
0x180007006  pop     rdi
0x180007007  retn
```
