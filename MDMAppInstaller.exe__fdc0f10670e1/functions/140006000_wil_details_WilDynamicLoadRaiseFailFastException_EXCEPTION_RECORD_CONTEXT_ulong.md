# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006000`
- end: `0x140006050`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002d60`
- `0x140006000`
- `0x14001c010`

## import_xrefs

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
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
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
0x140006025  mov     rcx, rax
0x140006028  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000602d  test    rax, rax
0x140006030  jz      short loc_140006040
0x140006032  mov     r8d, ebx
0x140006035  mov     rdx, rdi
0x140006038  mov     rcx, rsi
0x14000603b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006040  mov     rbx, [rsp+28h+arg_0]
0x140006045  mov     rsi, [rsp+28h+arg_8]
0x14000604a  add     rsp, 20h
0x14000604e  pop     rdi
0x14000604f  retn
```
