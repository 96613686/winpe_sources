# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000b1a0`
- end: `0x18000b1f8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b1a0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b1cf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b1cf`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b1bf`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b1bf`

## string_xrefs

- `0x18000b1b5`: `kernelbase.dll`

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
0x18000b1a0  mov     [rsp+arg_0], rbx
0x18000b1a5  mov     [rsp+arg_8], rsi
0x18000b1aa  push    rdi
0x18000b1ab  sub     rsp, 20h
0x18000b1af  mov     rsi, rcx
0x18000b1b2  mov     ebx, r8d
0x18000b1b5  lea     rcx, ModuleName; "kernelbase.dll"
0x18000b1bc  mov     rdi, rdx
0x18000b1bf  call    cs:__imp_GetModuleHandleW
0x18000b1c5  mov     rcx, rax; hModule
0x18000b1c8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000b1cf  call    cs:__imp_GetProcAddress
0x18000b1d5  test    rax, rax
0x18000b1d8  jz      short loc_18000B1E8
0x18000b1da  mov     r8d, ebx
0x18000b1dd  mov     rdx, rdi
0x18000b1e0  mov     rcx, rsi
0x18000b1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1e8  mov     rbx, [rsp+28h+arg_0]
0x18000b1ed  mov     rsi, [rsp+28h+arg_8]
0x18000b1f2  add     rsp, 20h
0x18000b1f6  pop     rdi
0x18000b1f7  retn
```
