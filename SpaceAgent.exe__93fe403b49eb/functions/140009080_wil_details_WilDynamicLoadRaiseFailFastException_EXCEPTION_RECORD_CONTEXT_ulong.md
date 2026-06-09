# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140009080`
- end: `0x1400090d0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003890`
- `0x140009080`
- `0x140020010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000909f`
- `KERNEL32!GetModuleHandleW` at `0x14000909f`

## string_xrefs

- `0x140009095`: `kernelbase.dll`

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
0x140009080  mov     [rsp+arg_0], rbx
0x140009085  mov     [rsp+arg_8], rsi
0x14000908a  push    rdi
0x14000908b  sub     rsp, 20h
0x14000908f  mov     rsi, rcx
0x140009092  mov     ebx, r8d
0x140009095  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000909c  mov     rdi, rdx
0x14000909f  call    cs:__imp_GetModuleHandleW
0x1400090a5  mov     rcx, rax
0x1400090a8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1400090ad  test    rax, rax
0x1400090b0  jz      short loc_1400090C0
0x1400090b2  mov     r8d, ebx
0x1400090b5  mov     rdx, rdi
0x1400090b8  mov     rcx, rsi
0x1400090bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400090c0  mov     rbx, [rsp+28h+arg_0]
0x1400090c5  mov     rsi, [rsp+28h+arg_8]
0x1400090ca  add     rsp, 20h
0x1400090ce  pop     rdi
0x1400090cf  retn
```
