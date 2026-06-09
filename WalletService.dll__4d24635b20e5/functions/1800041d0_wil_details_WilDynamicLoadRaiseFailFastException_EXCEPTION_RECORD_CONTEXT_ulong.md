# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800041d0`
- end: `0x180004220`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003a24`
- `0x1800041d0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800041ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800041ef`

## string_xrefs

- `0x1800041e5`: `kernelbase.dll`

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
0x1800041d0  mov     [rsp+arg_0], rbx
0x1800041d5  mov     [rsp+arg_8], rsi
0x1800041da  push    rdi
0x1800041db  sub     rsp, 20h
0x1800041df  mov     rsi, rcx
0x1800041e2  mov     ebx, r8d
0x1800041e5  lea     rcx, ModuleName; "kernelbase.dll"
0x1800041ec  mov     rdi, rdx
0x1800041ef  call    cs:__imp_GetModuleHandleW
0x1800041f5  mov     rcx, rax
0x1800041f8  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x1800041fd  test    rax, rax
0x180004200  jz      short loc_180004210
0x180004202  mov     r8d, ebx
0x180004205  mov     rdx, rdi
0x180004208  mov     rcx, rsi
0x18000420b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004210  mov     rbx, [rsp+28h+arg_0]
0x180004215  mov     rsi, [rsp+28h+arg_8]
0x18000421a  add     rsp, 20h
0x18000421e  pop     rdi
0x18000421f  retn
```
