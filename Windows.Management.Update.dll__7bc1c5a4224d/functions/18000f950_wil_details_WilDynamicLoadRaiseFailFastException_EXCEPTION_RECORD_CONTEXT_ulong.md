# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000f950`
- end: `0x18000f9a8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f950`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f96f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f96f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f97f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f97f`

## string_xrefs

- `0x18000f965`: `kernelbase.dll`

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
0x18000f950  mov     [rsp+arg_0], rbx
0x18000f955  mov     [rsp+arg_8], rsi
0x18000f95a  push    rdi
0x18000f95b  sub     rsp, 20h
0x18000f95f  mov     rsi, rcx
0x18000f962  mov     ebx, r8d
0x18000f965  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000f96c  mov     rdi, rdx
0x18000f96f  call    cs:__imp_GetModuleHandleW
0x18000f975  mov     rcx, rax; hModule
0x18000f978  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000f97f  call    cs:__imp_GetProcAddress
0x18000f985  test    rax, rax
0x18000f988  jz      short loc_18000F998
0x18000f98a  mov     r8d, ebx
0x18000f98d  mov     rdx, rdi
0x18000f990  mov     rcx, rsi
0x18000f993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f998  mov     rbx, [rsp+28h+arg_0]
0x18000f99d  mov     rsi, [rsp+28h+arg_8]
0x18000f9a2  add     rsp, 20h
0x18000f9a6  pop     rdi
0x18000f9a7  retn
```
