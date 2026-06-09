# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a3b0`
- end: `0x18000a408`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a3b0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a3df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a3df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a3cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a3cf`

## string_xrefs

- `0x18000a3c5`: `kernelbase.dll`

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
0x18000a3b0  mov     [rsp+arg_0], rbx
0x18000a3b5  mov     [rsp+arg_8], rsi
0x18000a3ba  push    rdi
0x18000a3bb  sub     rsp, 20h
0x18000a3bf  mov     rsi, rcx
0x18000a3c2  mov     ebx, r8d
0x18000a3c5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a3cc  mov     rdi, rdx
0x18000a3cf  call    cs:__imp_GetModuleHandleW
0x18000a3d5  mov     rcx, rax; hModule
0x18000a3d8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a3df  call    cs:__imp_GetProcAddress
0x18000a3e5  test    rax, rax
0x18000a3e8  jz      short loc_18000A3F8
0x18000a3ea  mov     r8d, ebx
0x18000a3ed  mov     rdx, rdi
0x18000a3f0  mov     rcx, rsi
0x18000a3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3f8  mov     rbx, [rsp+28h+arg_0]
0x18000a3fd  mov     rsi, [rsp+28h+arg_8]
0x18000a402  add     rsp, 20h
0x18000a406  pop     rdi
0x18000a407  retn
```
