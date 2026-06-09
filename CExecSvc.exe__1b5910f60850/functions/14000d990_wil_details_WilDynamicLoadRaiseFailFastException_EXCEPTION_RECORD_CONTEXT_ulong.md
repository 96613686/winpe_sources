# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000d990`
- end: `0x14000d9e8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000d990`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d9bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d9bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d9af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000d9af`

## string_xrefs

- `0x14000d9a5`: `kernelbase.dll`

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
0x14000d990  mov     [rsp+arg_0], rbx
0x14000d995  mov     [rsp+arg_8], rsi
0x14000d99a  push    rdi
0x14000d99b  sub     rsp, 20h
0x14000d99f  mov     rsi, rcx
0x14000d9a2  mov     ebx, r8d
0x14000d9a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000d9ac  mov     rdi, rdx
0x14000d9af  call    cs:__imp_GetModuleHandleW
0x14000d9b5  mov     rcx, rax; hModule
0x14000d9b8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000d9bf  call    cs:__imp_GetProcAddress
0x14000d9c5  test    rax, rax
0x14000d9c8  jz      short loc_14000D9D8
0x14000d9ca  mov     r8d, ebx
0x14000d9cd  mov     rdx, rdi
0x14000d9d0  mov     rcx, rsi
0x14000d9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9d8  mov     rbx, [rsp+28h+arg_0]
0x14000d9dd  mov     rsi, [rsp+28h+arg_8]
0x14000d9e2  add     rsp, 20h
0x14000d9e6  pop     rdi
0x14000d9e7  retn
```
