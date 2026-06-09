# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180011170`
- end: `0x1800111c8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011170`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001119f`
- `KERNEL32!GetProcAddress` at `0x18001119f`
- `KERNEL32!GetModuleHandleW` at `0x18001118f`
- `KERNEL32!GetModuleHandleW` at `0x18001118f`

## string_xrefs

- `0x180011185`: `kernelbase.dll`

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
0x180011170  mov     [rsp+arg_0], rbx
0x180011175  mov     [rsp+arg_8], rsi
0x18001117a  push    rdi
0x18001117b  sub     rsp, 20h
0x18001117f  mov     rsi, rcx
0x180011182  mov     ebx, r8d
0x180011185  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001118c  mov     rdi, rdx
0x18001118f  call    cs:__imp_GetModuleHandleW
0x180011195  mov     rcx, rax; hModule
0x180011198  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001119f  call    cs:__imp_GetProcAddress
0x1800111a5  test    rax, rax
0x1800111a8  jz      short loc_1800111B8
0x1800111aa  mov     r8d, ebx
0x1800111ad  mov     rdx, rdi
0x1800111b0  mov     rcx, rsi
0x1800111b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111b8  mov     rbx, [rsp+28h+arg_0]
0x1800111bd  mov     rsi, [rsp+28h+arg_8]
0x1800111c2  add     rsp, 20h
0x1800111c6  pop     rdi
0x1800111c7  retn
```
