# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007fd0`
- end: `0x180008020`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003c7c`
- `0x180007fd0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007fef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007fef`

## string_xrefs

- `0x180007fe5`: `kernelbase.dll`

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
0x180007fd0  mov     [rsp+arg_0], rbx
0x180007fd5  mov     [rsp+arg_8], rsi
0x180007fda  push    rdi
0x180007fdb  sub     rsp, 20h
0x180007fdf  mov     rsi, rcx
0x180007fe2  mov     ebx, r8d
0x180007fe5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007fec  mov     rdi, rdx
0x180007fef  call    cs:__imp_GetModuleHandleW
0x180007ff5  mov     rcx, rax
0x180007ff8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180007ffd  test    rax, rax
0x180008000  jz      short loc_180008010
0x180008002  mov     r8d, ebx
0x180008005  mov     rdx, rdi
0x180008008  mov     rcx, rsi
0x18000800b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008010  mov     rbx, [rsp+28h+arg_0]
0x180008015  mov     rsi, [rsp+28h+arg_8]
0x18000801a  add     rsp, 20h
0x18000801e  pop     rdi
0x18000801f  retn
```
