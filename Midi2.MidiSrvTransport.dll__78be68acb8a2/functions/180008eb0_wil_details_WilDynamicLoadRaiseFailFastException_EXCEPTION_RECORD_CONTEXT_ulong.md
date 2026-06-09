# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008eb0`
- end: `0x180008f08`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008eb0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ecf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ecf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008edf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008edf`

## string_xrefs

- `0x180008ec5`: `kernelbase.dll`

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
0x180008eb0  mov     [rsp+arg_0], rbx
0x180008eb5  mov     [rsp+arg_8], rsi
0x180008eba  push    rdi
0x180008ebb  sub     rsp, 20h
0x180008ebf  mov     rsi, rcx
0x180008ec2  mov     ebx, r8d
0x180008ec5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008ecc  mov     rdi, rdx
0x180008ecf  call    cs:__imp_GetModuleHandleW
0x180008ed5  mov     rcx, rax; hModule
0x180008ed8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180008edf  call    cs:__imp_GetProcAddress
0x180008ee5  test    rax, rax
0x180008ee8  jz      short loc_180008EF8
0x180008eea  mov     r8d, ebx
0x180008eed  mov     rdx, rdi
0x180008ef0  mov     rcx, rsi
0x180008ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef8  mov     rbx, [rsp+28h+arg_0]
0x180008efd  mov     rsi, [rsp+28h+arg_8]
0x180008f02  add     rsp, 20h
0x180008f06  pop     rdi
0x180008f07  retn
```
