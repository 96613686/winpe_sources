# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180015fe0`
- end: `0x180016030`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800138c0`
- `0x180015fe0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180015fff`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180015fff`

## string_xrefs

- `0x180015ff5`: `kernelbase.dll`

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
0x180015fe0  mov     [rsp+arg_0], rbx
0x180015fe5  mov     [rsp+arg_8], rsi
0x180015fea  push    rdi
0x180015feb  sub     rsp, 20h
0x180015fef  mov     rsi, rcx
0x180015ff2  mov     ebx, r8d
0x180015ff5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180015ffc  mov     rdi, rdx
0x180015fff  call    cs:__imp_GetModuleHandleW
0x180016005  mov     rcx, rax
0x180016008  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18001600d  test    rax, rax
0x180016010  jz      short loc_180016020
0x180016012  mov     r8d, ebx
0x180016015  mov     rdx, rdi
0x180016018  mov     rcx, rsi
0x18001601b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016020  mov     rbx, [rsp+28h+arg_0]
0x180016025  mov     rsi, [rsp+28h+arg_8]
0x18001602a  add     rsp, 20h
0x18001602e  pop     rdi
0x18001602f  retn
```
