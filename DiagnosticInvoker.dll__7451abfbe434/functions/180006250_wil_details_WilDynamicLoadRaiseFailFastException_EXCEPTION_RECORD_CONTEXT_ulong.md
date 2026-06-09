# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006250`
- end: `0x1800062a8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006250`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000626f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000626f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000627f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000627f`

## string_xrefs

- `0x180006265`: `kernelbase.dll`

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
0x180006250  mov     [rsp+arg_0], rbx
0x180006255  mov     [rsp+arg_8], rsi
0x18000625a  push    rdi
0x18000625b  sub     rsp, 20h
0x18000625f  mov     rsi, rcx
0x180006262  mov     ebx, r8d
0x180006265  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000626c  mov     rdi, rdx
0x18000626f  call    cs:__imp_GetModuleHandleW
0x180006275  mov     rcx, rax; hModule
0x180006278  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000627f  call    cs:__imp_GetProcAddress
0x180006285  test    rax, rax
0x180006288  jz      short loc_180006298
0x18000628a  mov     r8d, ebx
0x18000628d  mov     rdx, rdi
0x180006290  mov     rcx, rsi
0x180006293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006298  mov     rbx, [rsp+28h+arg_0]
0x18000629d  mov     rsi, [rsp+28h+arg_8]
0x1800062a2  add     rsp, 20h
0x1800062a6  pop     rdi
0x1800062a7  retn
```
