# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18001af20`
- end: `0x18001af70`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180018088`
- `0x18001af20`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001af3f`
- `KERNEL32!GetModuleHandleW` at `0x18001af3f`

## string_xrefs

- `0x18001af35`: `kernelbase.dll`

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
0x18001af20  mov     [rsp+arg_0], rbx
0x18001af25  mov     [rsp+arg_8], rsi
0x18001af2a  push    rdi
0x18001af2b  sub     rsp, 20h
0x18001af2f  mov     rsi, rcx
0x18001af32  mov     ebx, r8d
0x18001af35  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001af3c  mov     rdi, rdx
0x18001af3f  call    cs:__imp_GetModuleHandleW
0x18001af45  mov     rcx, rax
0x18001af48  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18001af4d  test    rax, rax
0x18001af50  jz      short loc_18001AF60
0x18001af52  mov     r8d, ebx
0x18001af55  mov     rdx, rdi
0x18001af58  mov     rcx, rsi
0x18001af5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af60  mov     rbx, [rsp+28h+arg_0]
0x18001af65  mov     rsi, [rsp+28h+arg_8]
0x18001af6a  add     rsp, 20h
0x18001af6e  pop     rdi
0x18001af6f  retn
```
