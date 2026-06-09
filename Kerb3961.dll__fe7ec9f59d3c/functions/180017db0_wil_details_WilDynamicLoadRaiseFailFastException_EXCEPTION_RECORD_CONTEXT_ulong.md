# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180017db0`
- end: `0x180017e08`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017db0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017ddf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017ddf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017dcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017dcf`

## string_xrefs

- `0x180017dc5`: `kernelbase.dll`

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
0x180017db0  mov     [rsp+arg_0], rbx
0x180017db5  mov     [rsp+arg_8], rsi
0x180017dba  push    rdi
0x180017dbb  sub     rsp, 20h
0x180017dbf  mov     rsi, rcx
0x180017dc2  mov     ebx, r8d
0x180017dc5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180017dcc  mov     rdi, rdx
0x180017dcf  call    cs:__imp_GetModuleHandleW
0x180017dd5  mov     rcx, rax; hModule
0x180017dd8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180017ddf  call    cs:__imp_GetProcAddress
0x180017de5  test    rax, rax
0x180017de8  jz      short loc_180017DF8
0x180017dea  mov     r8d, ebx
0x180017ded  mov     rdx, rdi
0x180017df0  mov     rcx, rsi
0x180017df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017df8  mov     rbx, [rsp+28h+arg_0]
0x180017dfd  mov     rsi, [rsp+28h+arg_8]
0x180017e02  add     rsp, 20h
0x180017e06  pop     rdi
0x180017e07  retn
```
