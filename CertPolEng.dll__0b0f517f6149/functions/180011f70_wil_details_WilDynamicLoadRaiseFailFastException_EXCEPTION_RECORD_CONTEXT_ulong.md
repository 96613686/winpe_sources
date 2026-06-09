# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180011f70`
- end: `0x180011fc8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011f70`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011f8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011f8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011f9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011f9f`

## string_xrefs

- `0x180011f85`: `kernelbase.dll`

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
0x180011f70  mov     [rsp+arg_0], rbx
0x180011f75  mov     [rsp+arg_8], rsi
0x180011f7a  push    rdi
0x180011f7b  sub     rsp, 20h
0x180011f7f  mov     rsi, rcx
0x180011f82  mov     ebx, r8d
0x180011f85  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180011f8c  mov     rdi, rdx
0x180011f8f  call    cs:__imp_GetModuleHandleW
0x180011f95  mov     rcx, rax; hModule
0x180011f98  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180011f9f  call    cs:__imp_GetProcAddress
0x180011fa5  test    rax, rax
0x180011fa8  jz      short loc_180011FB8
0x180011faa  mov     r8d, ebx
0x180011fad  mov     rdx, rdi
0x180011fb0  mov     rcx, rsi
0x180011fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fb8  mov     rbx, [rsp+28h+arg_0]
0x180011fbd  mov     rsi, [rsp+28h+arg_8]
0x180011fc2  add     rsp, 20h
0x180011fc6  pop     rdi
0x180011fc7  retn
```
