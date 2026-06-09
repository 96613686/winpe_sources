# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000b3a0`
- end: `0x18000b3f8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b3a0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b3bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b3bf`

## string_xrefs

- `0x18000b3b5`: `kernelbase.dll`

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
0x18000b3a0  mov     [rsp+arg_0], rbx
0x18000b3a5  mov     [rsp+arg_8], rsi
0x18000b3aa  push    rdi
0x18000b3ab  sub     rsp, 20h
0x18000b3af  mov     rsi, rcx
0x18000b3b2  mov     ebx, r8d
0x18000b3b5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b3bc  mov     rdi, rdx
0x18000b3bf  call    cs:__imp_GetModuleHandleW
0x18000b3c5  mov     rcx, rax; hModule
0x18000b3c8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000b3cf  call    cs:__imp_GetProcAddress
0x18000b3d5  test    rax, rax
0x18000b3d8  jz      short loc_18000B3E8
0x18000b3da  mov     r8d, ebx
0x18000b3dd  mov     rdx, rdi
0x18000b3e0  mov     rcx, rsi
0x18000b3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e8  mov     rbx, [rsp+28h+arg_0]
0x18000b3ed  mov     rsi, [rsp+28h+arg_8]
0x18000b3f2  add     rsp, 20h
0x18000b3f6  pop     rdi
0x18000b3f7  retn
```
