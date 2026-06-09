# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180044ed0`
- end: `0x180044f20`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180041bf4`
- `0x180044ed0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180044eef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180044eef`

## string_xrefs

- `0x180044ee5`: `kernelbase.dll`

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
0x180044ed0  mov     [rsp+arg_0], rbx
0x180044ed5  mov     [rsp+arg_8], rsi
0x180044eda  push    rdi
0x180044edb  sub     rsp, 20h
0x180044edf  mov     rsi, rcx
0x180044ee2  mov     ebx, r8d
0x180044ee5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180044eec  mov     rdi, rdx
0x180044eef  call    cs:__imp_GetModuleHandleW
0x180044ef5  mov     rcx, rax
0x180044ef8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180044efd  test    rax, rax
0x180044f00  jz      short loc_180044F10
0x180044f02  mov     r8d, ebx
0x180044f05  mov     rdx, rdi
0x180044f08  mov     rcx, rsi
0x180044f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f10  mov     rbx, [rsp+28h+arg_0]
0x180044f15  mov     rsi, [rsp+28h+arg_8]
0x180044f1a  add     rsp, 20h
0x180044f1e  pop     rdi
0x180044f1f  retn
```
