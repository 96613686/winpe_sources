# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000b950`
- end: `0x18000b9a8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b950`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b96f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b96f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b97f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b97f`

## string_xrefs

- `0x18000b965`: `kernelbase.dll`

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
0x18000b950  mov     [rsp+arg_0], rbx
0x18000b955  mov     [rsp+arg_8], rsi
0x18000b95a  push    rdi
0x18000b95b  sub     rsp, 20h
0x18000b95f  mov     rsi, rcx
0x18000b962  mov     ebx, r8d
0x18000b965  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b96c  mov     rdi, rdx
0x18000b96f  call    cs:__imp_GetModuleHandleW
0x18000b975  mov     rcx, rax; hModule
0x18000b978  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000b97f  call    cs:__imp_GetProcAddress
0x18000b985  test    rax, rax
0x18000b988  jz      short loc_18000B998
0x18000b98a  mov     r8d, ebx
0x18000b98d  mov     rdx, rdi
0x18000b990  mov     rcx, rsi
0x18000b993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b998  mov     rbx, [rsp+28h+arg_0]
0x18000b99d  mov     rsi, [rsp+28h+arg_8]
0x18000b9a2  add     rsp, 20h
0x18000b9a6  pop     rdi
0x18000b9a7  retn
```
