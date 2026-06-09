# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180025890`
- end: `0x1800258df`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `79`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016c3e`
- `0x180021f5c`
- `0x180025890`
- `0x180028010`

## string_xrefs

- `0x1800258a5`: `kernelbase.dll`

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
0x180025890  mov     [rsp+arg_0], rbx
0x180025895  mov     [rsp+arg_8], rsi
0x18002589a  push    rdi
0x18002589b  sub     rsp, 20h
0x18002589f  mov     rsi, rcx
0x1800258a2  mov     ebx, r8d
0x1800258a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800258ac  mov     rdi, rdx
0x1800258af  call    GetModuleHandleW_0
0x1800258b4  mov     rcx, rax
0x1800258b7  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800258bc  test    rax, rax
0x1800258bf  jz      short loc_1800258CF
0x1800258c1  mov     r8d, ebx
0x1800258c4  mov     rdx, rdi
0x1800258c7  mov     rcx, rsi
0x1800258ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258cf  mov     rbx, [rsp+28h+arg_0]
0x1800258d4  mov     rsi, [rsp+28h+arg_8]
0x1800258d9  add     rsp, 20h
0x1800258dd  pop     rdi
0x1800258de  retn
```
