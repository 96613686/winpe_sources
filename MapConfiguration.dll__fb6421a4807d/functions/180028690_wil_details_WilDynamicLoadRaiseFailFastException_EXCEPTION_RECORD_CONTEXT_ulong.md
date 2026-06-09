# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180028690`
- end: `0x1800286e0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180026774`
- `0x180028690`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800286af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800286af`

## string_xrefs

- `0x1800286a5`: `kernelbase.dll`

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
0x180028690  mov     [rsp+arg_0], rbx
0x180028695  mov     [rsp+arg_8], rsi
0x18002869a  push    rdi
0x18002869b  sub     rsp, 20h
0x18002869f  mov     rsi, rcx
0x1800286a2  mov     ebx, r8d
0x1800286a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800286ac  mov     rdi, rdx
0x1800286af  call    cs:__imp_GetModuleHandleW
0x1800286b5  mov     rcx, rax
0x1800286b8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800286bd  test    rax, rax
0x1800286c0  jz      short loc_1800286D0
0x1800286c2  mov     r8d, ebx
0x1800286c5  mov     rdx, rdi
0x1800286c8  mov     rcx, rsi
0x1800286cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286d0  mov     rbx, [rsp+28h+arg_0]
0x1800286d5  mov     rsi, [rsp+28h+arg_8]
0x1800286da  add     rsp, 20h
0x1800286de  pop     rdi
0x1800286df  retn
```
