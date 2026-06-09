# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000ae30`
- end: `0x18000ae8a`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ae30`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000ae4f`
- `KERNEL32!GetModuleHandleW` at `0x18000ae4f`
- `KERNEL32!GetProcAddress` at `0x18000ae60`
- `KERNEL32!GetProcAddress` at `0x18000ae60`

## string_xrefs

- `0x18000ae48`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x18000ae30  mov     [rsp+arg_0], rbx
0x18000ae35  mov     [rsp+arg_8], rsi
0x18000ae3a  push    rdi
0x18000ae3b  sub     rsp, 20h
0x18000ae3f  mov     ebx, r8d
0x18000ae42  mov     rdi, rdx
0x18000ae45  mov     rsi, rcx
0x18000ae48  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ae4f  call    cs:__imp_GetModuleHandleW
0x18000ae55  nop
0x18000ae56  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000ae5d  mov     rcx, rax; hModule
0x18000ae60  call    cs:__imp_GetProcAddress
0x18000ae66  nop
0x18000ae67  test    rax, rax
0x18000ae6a  jz      short loc_18000AE7A
0x18000ae6c  mov     r8d, ebx
0x18000ae6f  mov     rdx, rdi
0x18000ae72  mov     rcx, rsi
0x18000ae75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae7a  mov     rbx, [rsp+28h+arg_0]
0x18000ae7f  mov     rsi, [rsp+28h+arg_8]
0x18000ae84  add     rsp, 20h
0x18000ae88  pop     rdi
0x18000ae89  retn
```
