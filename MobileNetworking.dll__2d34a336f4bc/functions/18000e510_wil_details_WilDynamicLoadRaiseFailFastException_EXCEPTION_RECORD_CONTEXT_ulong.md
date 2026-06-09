# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000e510`
- end: `0x18000e560`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000de90`
- `0x18000e510`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e52f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e52f`

## string_xrefs

- `0x18000e525`: `kernelbase.dll`

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
0x18000e510  mov     [rsp+arg_0], rbx
0x18000e515  mov     [rsp+arg_8], rsi
0x18000e51a  push    rdi
0x18000e51b  sub     rsp, 20h
0x18000e51f  mov     rsi, rcx
0x18000e522  mov     ebx, r8d
0x18000e525  lea     rcx, ModuleName; "kernelbase.dll"
0x18000e52c  mov     rdi, rdx
0x18000e52f  call    cs:__imp_GetModuleHandleW
0x18000e535  mov     rcx, rax
0x18000e538  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000e53d  test    rax, rax
0x18000e540  jz      short loc_18000E550
0x18000e542  mov     r8d, ebx
0x18000e545  mov     rdx, rdi
0x18000e548  mov     rcx, rsi
0x18000e54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e550  mov     rbx, [rsp+28h+arg_0]
0x18000e555  mov     rsi, [rsp+28h+arg_8]
0x18000e55a  add     rsp, 20h
0x18000e55e  pop     rdi
0x18000e55f  retn
```
