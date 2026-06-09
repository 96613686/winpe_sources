# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006000`
- end: `0x140006058`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006000`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000602f`
- `KERNEL32!GetProcAddress` at `0x14000602f`
- `KERNEL32!GetModuleHandleW` at `0x14000601f`
- `KERNEL32!GetModuleHandleW` at `0x14000601f`

## string_xrefs

- `0x140006015`: `kernelbase.dll`

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
0x140006000  mov     [rsp+arg_0], rbx
0x140006005  mov     [rsp+arg_8], rsi
0x14000600a  push    rdi
0x14000600b  sub     rsp, 20h
0x14000600f  mov     rsi, rcx
0x140006012  mov     ebx, r8d
0x140006015  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000601c  mov     rdi, rdx
0x14000601f  call    cs:__imp_GetModuleHandleW
0x140006025  mov     rcx, rax; hModule
0x140006028  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000602f  call    cs:__imp_GetProcAddress
0x140006035  test    rax, rax
0x140006038  jz      short loc_140006048
0x14000603a  mov     r8d, ebx
0x14000603d  mov     rdx, rdi
0x140006040  mov     rcx, rsi
0x140006043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006048  mov     rbx, [rsp+28h+arg_0]
0x14000604d  mov     rsi, [rsp+28h+arg_8]
0x140006052  add     rsp, 20h
0x140006056  pop     rdi
0x140006057  retn
```
