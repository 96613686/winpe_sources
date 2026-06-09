# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006320`
- end: `0x180006378`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006320`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000633f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000633f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000634f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000634f`

## string_xrefs

- `0x180006335`: `kernelbase.dll`

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
0x180006320  mov     [rsp+arg_0], rbx
0x180006325  mov     [rsp+arg_8], rsi
0x18000632a  push    rdi
0x18000632b  sub     rsp, 20h
0x18000632f  mov     rsi, rcx
0x180006332  mov     ebx, r8d
0x180006335  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000633c  mov     rdi, rdx
0x18000633f  call    cs:__imp_GetModuleHandleW
0x180006345  mov     rcx, rax; hModule
0x180006348  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000634f  call    cs:__imp_GetProcAddress
0x180006355  test    rax, rax
0x180006358  jz      short loc_180006368
0x18000635a  mov     r8d, ebx
0x18000635d  mov     rdx, rdi
0x180006360  mov     rcx, rsi
0x180006363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006368  mov     rbx, [rsp+28h+arg_0]
0x18000636d  mov     rsi, [rsp+28h+arg_8]
0x180006372  add     rsp, 20h
0x180006376  pop     rdi
0x180006377  retn
```
