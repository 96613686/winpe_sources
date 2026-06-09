# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000def0`
- end: `0x18000df48`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(_EXCEPTION_RECORD *exr, _CONTEXT *ctxt, unsigned int flags)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000def0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000df1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000df1f`

## string_xrefs

- `0x18000df05`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        _EXCEPTION_RECORD *exr,
        _CONTEXT *ctxt,
        unsigned int flags)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(_EXCEPTION_RECORD *, _CONTEXT *, _QWORD))ProcAddress)(exr, ctxt, flags);
}

```

## disassembly

```asm
0x18000def0  mov     [rsp+arg_0], rbx
0x18000def5  mov     [rsp+arg_8], rsi
0x18000defa  push    rdi
0x18000defb  sub     rsp, 20h
0x18000deff  mov     rsi, exr
0x18000df02  mov     ebx, flags
0x18000df05  lea     exr, aKernelbaseDll; "kernelbase.dll"
0x18000df0c  mov     rdi, ctxt
0x18000df0f  call    cs:__imp_GetModuleHandleW
0x18000df15  mov     exr, rax; hModule
0x18000df18  lea     ctxt, aRaisefailfaste; "RaiseFailFastException"
0x18000df1f  call    cs:__imp_GetProcAddress
0x18000df25  test    rax, rax
0x18000df28  jz      short loc_18000DF38
0x18000df2a  mov     flags, ebx
0x18000df2d  mov     ctxt, rdi
0x18000df30  mov     exr, rsi
0x18000df33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df38  mov     rbx, [rsp+28h+arg_0]
0x18000df3d  mov     rsi, [rsp+28h+arg_8]
0x18000df42  add     rsp, 20h
0x18000df46  pop     rdi
0x18000df47  retn
```
