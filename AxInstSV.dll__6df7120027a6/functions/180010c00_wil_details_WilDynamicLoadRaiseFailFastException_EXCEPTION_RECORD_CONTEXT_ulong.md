# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180010c00`
- end: `0x180010c50`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076e8`
- `0x180010c00`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010c1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010c1f`

## string_xrefs

- `0x180010c15`: `kernelbase.dll`

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
0x180010c00  mov     [rsp+arg_0], rbx
0x180010c05  mov     [rsp+arg_8], rsi
0x180010c0a  push    rdi
0x180010c0b  sub     rsp, 20h
0x180010c0f  mov     rsi, rcx
0x180010c12  mov     ebx, r8d
0x180010c15  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180010c1c  mov     rdi, rdx
0x180010c1f  call    cs:__imp_GetModuleHandleW
0x180010c25  mov     rcx, rax
0x180010c28  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180010c2d  test    rax, rax
0x180010c30  jz      short loc_180010C40
0x180010c32  mov     r8d, ebx
0x180010c35  mov     rdx, rdi
0x180010c38  mov     rcx, rsi
0x180010c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c40  mov     rbx, [rsp+28h+arg_0]
0x180010c45  mov     rsi, [rsp+28h+arg_8]
0x180010c4a  add     rsp, 20h
0x180010c4e  pop     rdi
0x180010c4f  retn
```
