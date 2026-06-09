# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000a0d0`
- end: `0x18000a128`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a0d0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a0ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a0ef`

## string_xrefs

- `0x18000a0e5`: `kernelbase.dll`

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
0x18000a0d0  mov     [rsp+arg_0], rbx
0x18000a0d5  mov     [rsp+arg_8], rsi
0x18000a0da  push    rdi
0x18000a0db  sub     rsp, 20h
0x18000a0df  mov     rsi, rcx
0x18000a0e2  mov     ebx, r8d
0x18000a0e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a0ec  mov     rdi, rdx
0x18000a0ef  call    cs:__imp_GetModuleHandleW
0x18000a0f5  mov     rcx, rax; hModule
0x18000a0f8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000a0ff  call    cs:__imp_GetProcAddress
0x18000a105  test    rax, rax
0x18000a108  jz      short loc_18000A118
0x18000a10a  mov     r8d, ebx
0x18000a10d  mov     rdx, rdi
0x18000a110  mov     rcx, rsi
0x18000a113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a118  mov     rbx, [rsp+28h+arg_0]
0x18000a11d  mov     rsi, [rsp+28h+arg_8]
0x18000a122  add     rsp, 20h
0x18000a126  pop     rdi
0x18000a127  retn
```
