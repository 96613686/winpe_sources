# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000c330`
- end: `0x18000c380`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008010`
- `0x18000c330`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c34f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c34f`

## string_xrefs

- `0x18000c345`: `kernelbase.dll`

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
0x18000c330  mov     [rsp+arg_0], rbx
0x18000c335  mov     [rsp+arg_8], rsi
0x18000c33a  push    rdi
0x18000c33b  sub     rsp, 20h
0x18000c33f  mov     rsi, rcx
0x18000c342  mov     ebx, r8d
0x18000c345  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c34c  mov     rdi, rdx
0x18000c34f  call    cs:__imp_GetModuleHandleW
0x18000c355  mov     rcx, rax
0x18000c358  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000c35d  test    rax, rax
0x18000c360  jz      short loc_18000C370
0x18000c362  mov     r8d, ebx
0x18000c365  mov     rdx, rdi
0x18000c368  mov     rcx, rsi
0x18000c36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c370  mov     rbx, [rsp+28h+arg_0]
0x18000c375  mov     rsi, [rsp+28h+arg_8]
0x18000c37a  add     rsp, 20h
0x18000c37e  pop     rdi
0x18000c37f  retn
```
