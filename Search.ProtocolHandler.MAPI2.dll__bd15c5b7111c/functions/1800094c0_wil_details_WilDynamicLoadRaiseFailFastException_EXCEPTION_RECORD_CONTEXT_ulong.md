# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800094c0`
- end: `0x180009510`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003aa0`
- `0x1800094c0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800094df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800094df`

## string_xrefs

- `0x1800094d5`: `kernelbase.dll`

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
0x1800094c0  mov     [rsp+arg_0], rbx
0x1800094c5  mov     [rsp+arg_8], rsi
0x1800094ca  push    rdi
0x1800094cb  sub     rsp, 20h
0x1800094cf  mov     rsi, rcx
0x1800094d2  mov     ebx, r8d
0x1800094d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800094dc  mov     rdi, rdx
0x1800094df  call    cs:__imp_GetModuleHandleW
0x1800094e5  mov     rcx, rax
0x1800094e8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800094ed  test    rax, rax
0x1800094f0  jz      short loc_180009500
0x1800094f2  mov     r8d, ebx
0x1800094f5  mov     rdx, rdi
0x1800094f8  mov     rcx, rsi
0x1800094fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009500  mov     rbx, [rsp+28h+arg_0]
0x180009505  mov     rsi, [rsp+28h+arg_8]
0x18000950a  add     rsp, 20h
0x18000950e  pop     rdi
0x18000950f  retn
```
