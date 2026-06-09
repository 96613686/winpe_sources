# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18002c8d0`
- end: `0x18002c920`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002bd00`
- `0x18002c8d0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c8ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c8ef`

## string_xrefs

- `0x18002c8e5`: `kernelbase.dll`

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
0x18002c8d0  mov     [rsp+arg_0], rbx
0x18002c8d5  mov     [rsp+arg_8], rsi
0x18002c8da  push    rdi
0x18002c8db  sub     rsp, 20h
0x18002c8df  mov     rsi, rcx
0x18002c8e2  mov     ebx, r8d
0x18002c8e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002c8ec  mov     rdi, rdx
0x18002c8ef  call    cs:__imp_GetModuleHandleW
0x18002c8f5  mov     rcx, rax
0x18002c8f8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18002c8fd  test    rax, rax
0x18002c900  jz      short loc_18002C910
0x18002c902  mov     r8d, ebx
0x18002c905  mov     rdx, rdi
0x18002c908  mov     rcx, rsi
0x18002c90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c910  mov     rbx, [rsp+28h+arg_0]
0x18002c915  mov     rsi, [rsp+28h+arg_8]
0x18002c91a  add     rsp, 20h
0x18002c91e  pop     rdi
0x18002c91f  retn
```
