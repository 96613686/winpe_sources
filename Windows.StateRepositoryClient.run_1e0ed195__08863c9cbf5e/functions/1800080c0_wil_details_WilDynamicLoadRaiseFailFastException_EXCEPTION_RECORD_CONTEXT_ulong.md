# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800080c0`
- end: `0x180008110`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004488`
- `0x1800080c0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080df`

## string_xrefs

- `0x1800080d5`: `kernelbase.dll`

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
0x1800080c0  mov     [rsp+arg_0], rbx
0x1800080c5  mov     [rsp+arg_8], rsi
0x1800080ca  push    rdi
0x1800080cb  sub     rsp, 20h
0x1800080cf  mov     rsi, rcx
0x1800080d2  mov     ebx, r8d
0x1800080d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800080dc  mov     rdi, rdx
0x1800080df  call    cs:__imp_GetModuleHandleW
0x1800080e5  mov     rcx, rax
0x1800080e8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800080ed  test    rax, rax
0x1800080f0  jz      short loc_180008100
0x1800080f2  mov     r8d, ebx
0x1800080f5  mov     rdx, rdi
0x1800080f8  mov     rcx, rsi
0x1800080fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008100  mov     rbx, [rsp+28h+arg_0]
0x180008105  mov     rsi, [rsp+28h+arg_8]
0x18000810a  add     rsp, 20h
0x18000810e  pop     rdi
0x18000810f  retn
```
