# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006c20`
- end: `0x180006c78`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006c20`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c3f`

## string_xrefs

- `0x180006c35`: `kernelbase.dll`

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
0x180006c20  mov     [rsp+arg_0], rbx
0x180006c25  mov     [rsp+arg_8], rsi
0x180006c2a  push    rdi
0x180006c2b  sub     rsp, 20h
0x180006c2f  mov     rsi, rcx
0x180006c32  mov     ebx, r8d
0x180006c35  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006c3c  mov     rdi, rdx
0x180006c3f  call    cs:__imp_GetModuleHandleW
0x180006c45  mov     rcx, rax; hModule
0x180006c48  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180006c4f  call    cs:__imp_GetProcAddress
0x180006c55  test    rax, rax
0x180006c58  jz      short loc_180006C68
0x180006c5a  mov     r8d, ebx
0x180006c5d  mov     rdx, rdi
0x180006c60  mov     rcx, rsi
0x180006c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c68  mov     rbx, [rsp+28h+arg_0]
0x180006c6d  mov     rsi, [rsp+28h+arg_8]
0x180006c72  add     rsp, 20h
0x180006c76  pop     rdi
0x180006c77  retn
```
