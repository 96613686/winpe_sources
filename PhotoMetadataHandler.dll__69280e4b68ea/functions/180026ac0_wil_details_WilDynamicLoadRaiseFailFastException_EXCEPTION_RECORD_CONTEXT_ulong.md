# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180026ac0`
- end: `0x180026b10`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001768e`
- `0x180023060`
- `0x180026ac0`
- `0x180029010`

## string_xrefs

- `0x180026ad5`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW_0; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW_0 = GetModuleHandleW_0(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW_0);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x180026ac0  mov     [rsp+arg_0], rbx
0x180026ac5  mov     [rsp+arg_8], rsi
0x180026aca  push    rdi
0x180026acb  sub     rsp, 20h
0x180026acf  mov     rsi, rcx
0x180026ad2  mov     ebx, r8d
0x180026ad5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180026adc  mov     rdi, rdx
0x180026adf  call    GetModuleHandleW_0
0x180026ae4  mov     rcx, rax
0x180026ae7  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180026aec  test    rax, rax
0x180026aef  jz      short loc_180026AFF
0x180026af1  mov     r8d, ebx
0x180026af4  mov     rdx, rdi
0x180026af7  mov     rcx, rsi
0x180026afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aff  mov     rbx, [rsp+28h+arg_0]
0x180026b04  mov     rsi, [rsp+28h+arg_8]
0x180026b09  add     rsp, 20h
0x180026b0d  pop     rdi
0x180026b0e  retn
```
