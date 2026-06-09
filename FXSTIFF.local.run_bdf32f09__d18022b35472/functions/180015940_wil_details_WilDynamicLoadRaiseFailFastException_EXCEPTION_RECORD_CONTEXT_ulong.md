# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180015940`
- end: `0x18001599a`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180015940`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001595f`
- `KERNEL32!GetModuleHandleW` at `0x18001595f`
- `KERNEL32!GetProcAddress` at `0x180015970`
- `KERNEL32!GetProcAddress` at `0x180015970`

## string_xrefs

- `0x180015958`: `kernelbase.dll`

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
0x180015940  mov     [rsp+arg_0], rbx
0x180015945  mov     [rsp+arg_8], rsi
0x18001594a  push    rdi
0x18001594b  sub     rsp, 20h
0x18001594f  mov     ebx, r8d
0x180015952  mov     rdi, rdx
0x180015955  mov     rsi, rcx
0x180015958  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001595f  call    cs:__imp_GetModuleHandleW
0x180015965  nop
0x180015966  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001596d  mov     rcx, rax; hModule
0x180015970  call    cs:__imp_GetProcAddress
0x180015976  nop
0x180015977  test    rax, rax
0x18001597a  jz      short loc_18001598A
0x18001597c  mov     r8d, ebx
0x18001597f  mov     rdx, rdi
0x180015982  mov     rcx, rsi
0x180015985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001598a  mov     rbx, [rsp+28h+arg_0]
0x18001598f  mov     rsi, [rsp+28h+arg_8]
0x180015994  add     rsp, 20h
0x180015998  pop     rdi
0x180015999  retn
```
