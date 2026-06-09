# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800119b0`
- end: `0x180011a08`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800119b0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800119cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800119cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800119df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800119df`

## string_xrefs

- `0x1800119c5`: `kernelbase.dll`

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
0x1800119b0  mov     [rsp+arg_0], rbx
0x1800119b5  mov     [rsp+arg_8], rsi
0x1800119ba  push    rdi
0x1800119bb  sub     rsp, 20h
0x1800119bf  mov     rsi, rcx
0x1800119c2  mov     ebx, r8d
0x1800119c5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800119cc  mov     rdi, rdx
0x1800119cf  call    cs:__imp_GetModuleHandleW
0x1800119d5  mov     rcx, rax; hModule
0x1800119d8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800119df  call    cs:__imp_GetProcAddress
0x1800119e5  test    rax, rax
0x1800119e8  jz      short loc_1800119F8
0x1800119ea  mov     r8d, ebx
0x1800119ed  mov     rdx, rdi
0x1800119f0  mov     rcx, rsi
0x1800119f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f8  mov     rbx, [rsp+28h+arg_0]
0x1800119fd  mov     rsi, [rsp+28h+arg_8]
0x180011a02  add     rsp, 20h
0x180011a06  pop     rdi
0x180011a07  retn
```
