# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180017a70`
- end: `0x180017ac8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017a70`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017a8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017a8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017a9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017a9f`

## string_xrefs

- `0x180017a85`: `kernelbase.dll`

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
0x180017a70  mov     [rsp+arg_0], rbx
0x180017a75  mov     [rsp+arg_8], rsi
0x180017a7a  push    rdi
0x180017a7b  sub     rsp, 20h
0x180017a7f  mov     rsi, rcx
0x180017a82  mov     ebx, r8d
0x180017a85  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180017a8c  mov     rdi, rdx
0x180017a8f  call    cs:__imp_GetModuleHandleW
0x180017a95  mov     rcx, rax; hModule
0x180017a98  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180017a9f  call    cs:__imp_GetProcAddress
0x180017aa5  test    rax, rax
0x180017aa8  jz      short loc_180017AB8
0x180017aaa  mov     r8d, ebx
0x180017aad  mov     rdx, rdi
0x180017ab0  mov     rcx, rsi
0x180017ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ab8  mov     rbx, [rsp+28h+arg_0]
0x180017abd  mov     rsi, [rsp+28h+arg_8]
0x180017ac2  add     rsp, 20h
0x180017ac6  pop     rdi
0x180017ac7  retn
```
