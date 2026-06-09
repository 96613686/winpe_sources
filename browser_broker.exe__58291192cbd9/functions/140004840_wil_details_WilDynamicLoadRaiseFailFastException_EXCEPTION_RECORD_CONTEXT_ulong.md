# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140004840`
- end: `0x140004890`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002024`
- `0x140004840`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000485f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000485f`

## string_xrefs

- `0x140004855`: `kernelbase.dll`

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
0x140004840  mov     [rsp+arg_0], rbx
0x140004845  mov     [rsp+arg_8], rsi
0x14000484a  push    rdi
0x14000484b  sub     rsp, 20h
0x14000484f  mov     rsi, rcx
0x140004852  mov     ebx, r8d
0x140004855  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000485c  mov     rdi, rdx
0x14000485f  call    cs:__imp_GetModuleHandleW
0x140004865  mov     rcx, rax
0x140004868  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x14000486d  test    rax, rax
0x140004870  jz      short loc_140004880
0x140004872  mov     r8d, ebx
0x140004875  mov     rdx, rdi
0x140004878  mov     rcx, rsi
0x14000487b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004880  mov     rbx, [rsp+28h+arg_0]
0x140004885  mov     rsi, [rsp+28h+arg_8]
0x14000488a  add     rsp, 20h
0x14000488e  pop     rdi
0x14000488f  retn
```
