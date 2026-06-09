# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006be0`
- end: `0x140006c30`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002360`
- `0x140006be0`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006bff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006bff`

## string_xrefs

- `0x140006bf5`: `kernelbase.dll`

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
0x140006be0  mov     [rsp+arg_0], rbx
0x140006be5  mov     [rsp+arg_8], rsi
0x140006bea  push    rdi
0x140006beb  sub     rsp, 20h
0x140006bef  mov     rsi, rcx
0x140006bf2  mov     ebx, r8d
0x140006bf5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140006bfc  mov     rdi, rdx
0x140006bff  call    cs:__imp_GetModuleHandleW
0x140006c05  mov     rcx, rax
0x140006c08  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x140006c0d  test    rax, rax
0x140006c10  jz      short loc_140006C20
0x140006c12  mov     r8d, ebx
0x140006c15  mov     rdx, rdi
0x140006c18  mov     rcx, rsi
0x140006c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c20  mov     rbx, [rsp+28h+arg_0]
0x140006c25  mov     rsi, [rsp+28h+arg_8]
0x140006c2a  add     rsp, 20h
0x140006c2e  pop     rdi
0x140006c2f  retn
```
