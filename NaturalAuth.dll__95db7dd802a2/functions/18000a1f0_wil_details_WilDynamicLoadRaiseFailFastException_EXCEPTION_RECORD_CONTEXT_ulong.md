# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a1f0`
- end: `0x18000a240`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005f88`
- `0x18000a1f0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a20f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a20f`

## string_xrefs

- `0x18000a205`: `kernelbase.dll`

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
0x18000a1f0  mov     [rsp+arg_0], rbx
0x18000a1f5  mov     [rsp+arg_8], rsi
0x18000a1fa  push    rdi
0x18000a1fb  sub     rsp, 20h
0x18000a1ff  mov     rsi, rcx
0x18000a202  mov     ebx, r8d
0x18000a205  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a20c  mov     rdi, rdx
0x18000a20f  call    cs:__imp_GetModuleHandleW
0x18000a215  mov     rcx, rax
0x18000a218  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000a21d  test    rax, rax
0x18000a220  jz      short loc_18000A230
0x18000a222  mov     r8d, ebx
0x18000a225  mov     rdx, rdi
0x18000a228  mov     rcx, rsi
0x18000a22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a230  mov     rbx, [rsp+28h+arg_0]
0x18000a235  mov     rsi, [rsp+28h+arg_8]
0x18000a23a  add     rsp, 20h
0x18000a23e  pop     rdi
0x18000a23f  retn
```
