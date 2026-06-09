# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008da0`
- end: `0x180008df8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008da0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008dcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008dcf`

## string_xrefs

- `0x180008db5`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x180008da0  mov     [rsp+arg_0], rbx
0x180008da5  mov     [rsp+arg_8], rsi
0x180008daa  push    rdi
0x180008dab  sub     rsp, 20h
0x180008daf  mov     rsi, rcx
0x180008db2  mov     ebx, r8d
0x180008db5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008dbc  mov     rdi, rdx
0x180008dbf  call    cs:__imp_GetModuleHandleW
0x180008dc5  mov     rcx, rax; hModule
0x180008dc8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180008dcf  call    cs:__imp_GetProcAddress
0x180008dd5  test    rax, rax
0x180008dd8  jz      short loc_180008DE8
0x180008dda  mov     r8d, ebx
0x180008ddd  mov     rdx, rdi
0x180008de0  mov     rcx, rsi
0x180008de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008de8  mov     rbx, [rsp+28h+arg_0]
0x180008ded  mov     rsi, [rsp+28h+arg_8]
0x180008df2  add     rsp, 20h
0x180008df6  pop     rdi
0x180008df7  retn
```
