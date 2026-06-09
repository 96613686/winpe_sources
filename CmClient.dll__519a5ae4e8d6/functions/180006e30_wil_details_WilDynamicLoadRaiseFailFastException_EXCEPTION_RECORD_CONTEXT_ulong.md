# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006e30`
- end: `0x180006e88`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006e30`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006e4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006e4f`

## string_xrefs

- `0x180006e45`: `kernelbase.dll`

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
0x180006e30  mov     [rsp+arg_0], rbx
0x180006e35  mov     [rsp+arg_8], rsi
0x180006e3a  push    rdi
0x180006e3b  sub     rsp, 20h
0x180006e3f  mov     rsi, rcx
0x180006e42  mov     ebx, r8d
0x180006e45  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006e4c  mov     rdi, rdx
0x180006e4f  call    cs:__imp_GetModuleHandleW
0x180006e55  mov     rcx, rax; hModule
0x180006e58  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180006e5f  call    cs:__imp_GetProcAddress
0x180006e65  test    rax, rax
0x180006e68  jz      short loc_180006E78
0x180006e6a  mov     r8d, ebx
0x180006e6d  mov     rdx, rdi
0x180006e70  mov     rcx, rsi
0x180006e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e78  mov     rbx, [rsp+28h+arg_0]
0x180006e7d  mov     rsi, [rsp+28h+arg_8]
0x180006e82  add     rsp, 20h
0x180006e86  pop     rdi
0x180006e87  retn
```
