# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008f40`
- end: `0x180008f98`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008f40`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008f5f`

## string_xrefs

- `0x180008f55`: `kernelbase.dll`

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
0x180008f40  mov     [rsp+arg_0], rbx
0x180008f45  mov     [rsp+arg_8], rsi
0x180008f4a  push    rdi
0x180008f4b  sub     rsp, 20h
0x180008f4f  mov     rsi, rcx
0x180008f52  mov     ebx, r8d
0x180008f55  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008f5c  mov     rdi, rdx
0x180008f5f  call    cs:__imp_GetModuleHandleW
0x180008f65  mov     rcx, rax; hModule
0x180008f68  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180008f6f  call    cs:__imp_GetProcAddress
0x180008f75  test    rax, rax
0x180008f78  jz      short loc_180008F88
0x180008f7a  mov     r8d, ebx
0x180008f7d  mov     rdx, rdi
0x180008f80  mov     rcx, rsi
0x180008f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f88  mov     rbx, [rsp+28h+arg_0]
0x180008f8d  mov     rsi, [rsp+28h+arg_8]
0x180008f92  add     rsp, 20h
0x180008f96  pop     rdi
0x180008f97  retn
```
