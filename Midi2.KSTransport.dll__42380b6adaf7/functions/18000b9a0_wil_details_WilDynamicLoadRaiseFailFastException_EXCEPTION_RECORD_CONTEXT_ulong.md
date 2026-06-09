# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000b9a0`
- end: `0x18000b9f8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b9a0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b9bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b9bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9cf`

## string_xrefs

- `0x18000b9b5`: `kernelbase.dll`

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
0x18000b9a0  mov     [rsp+arg_0], rbx
0x18000b9a5  mov     [rsp+arg_8], rsi
0x18000b9aa  push    rdi
0x18000b9ab  sub     rsp, 20h
0x18000b9af  mov     rsi, rcx
0x18000b9b2  mov     ebx, r8d
0x18000b9b5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b9bc  mov     rdi, rdx
0x18000b9bf  call    cs:__imp_GetModuleHandleW
0x18000b9c5  mov     rcx, rax; hModule
0x18000b9c8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000b9cf  call    cs:__imp_GetProcAddress
0x18000b9d5  test    rax, rax
0x18000b9d8  jz      short loc_18000B9E8
0x18000b9da  mov     r8d, ebx
0x18000b9dd  mov     rdx, rdi
0x18000b9e0  mov     rcx, rsi
0x18000b9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e8  mov     rbx, [rsp+28h+arg_0]
0x18000b9ed  mov     rsi, [rsp+28h+arg_8]
0x18000b9f2  add     rsp, 20h
0x18000b9f6  pop     rdi
0x18000b9f7  retn
```
