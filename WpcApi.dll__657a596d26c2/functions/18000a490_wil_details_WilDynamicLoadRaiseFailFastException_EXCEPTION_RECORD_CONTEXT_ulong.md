# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a490`
- end: `0x18000a4e8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a490`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a4af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a4af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4bf`

## string_xrefs

- `0x18000a4a5`: `kernelbase.dll`

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
0x18000a490  mov     [rsp+arg_0], rbx
0x18000a495  mov     [rsp+arg_8], rsi
0x18000a49a  push    rdi
0x18000a49b  sub     rsp, 20h
0x18000a49f  mov     rsi, rcx
0x18000a4a2  mov     ebx, r8d
0x18000a4a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a4ac  mov     rdi, rdx
0x18000a4af  call    cs:__imp_GetModuleHandleW
0x18000a4b5  mov     rcx, rax; hModule
0x18000a4b8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a4bf  call    cs:__imp_GetProcAddress
0x18000a4c5  test    rax, rax
0x18000a4c8  jz      short loc_18000A4D8
0x18000a4ca  mov     r8d, ebx
0x18000a4cd  mov     rdx, rdi
0x18000a4d0  mov     rcx, rsi
0x18000a4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4d8  mov     rbx, [rsp+28h+arg_0]
0x18000a4dd  mov     rsi, [rsp+28h+arg_8]
0x18000a4e2  add     rsp, 20h
0x18000a4e6  pop     rdi
0x18000a4e7  retn
```
