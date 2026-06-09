# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800ad8a0`
- end: `0x1800ad8fa`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `90`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800ad8a0`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ad8bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ad8bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad8d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad8d0`

## string_xrefs

- `0x1800ad8b8`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x1800ad8a0  mov     [rsp+arg_0], rbx
0x1800ad8a5  mov     [rsp+arg_8], rsi
0x1800ad8aa  push    rdi
0x1800ad8ab  sub     rsp, 20h
0x1800ad8af  mov     ebx, r8d
0x1800ad8b2  mov     rdi, rdx
0x1800ad8b5  mov     rsi, rcx
0x1800ad8b8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800ad8bf  call    cs:__imp_GetModuleHandleW
0x1800ad8c5  nop
0x1800ad8c6  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800ad8cd  mov     rcx, rax; hModule
0x1800ad8d0  call    cs:__imp_GetProcAddress
0x1800ad8d6  nop
0x1800ad8d7  test    rax, rax
0x1800ad8da  jz      short loc_1800AD8EA
0x1800ad8dc  mov     r8d, ebx
0x1800ad8df  mov     rdx, rdi
0x1800ad8e2  mov     rcx, rsi
0x1800ad8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad8ea  mov     rbx, [rsp+28h+arg_0]
0x1800ad8ef  mov     rsi, [rsp+28h+arg_8]
0x1800ad8f4  add     rsp, 20h
0x1800ad8f8  pop     rdi
0x1800ad8f9  retn
```
