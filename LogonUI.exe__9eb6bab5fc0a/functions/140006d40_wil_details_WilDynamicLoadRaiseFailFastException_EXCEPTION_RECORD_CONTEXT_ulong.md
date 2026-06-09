# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140006d40`
- end: `0x140006d98`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006d40`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d5f`

## string_xrefs

- `0x140006d55`: `kernelbase.dll`

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
0x140006d40  mov     [rsp+arg_0], rbx
0x140006d45  mov     [rsp+arg_8], rsi
0x140006d4a  push    rdi
0x140006d4b  sub     rsp, 20h
0x140006d4f  mov     rsi, rcx
0x140006d52  mov     ebx, r8d
0x140006d55  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140006d5c  mov     rdi, rdx
0x140006d5f  call    cs:__imp_GetModuleHandleW
0x140006d65  mov     rcx, rax; hModule
0x140006d68  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140006d6f  call    cs:__imp_GetProcAddress
0x140006d75  test    rax, rax
0x140006d78  jz      short loc_140006D88
0x140006d7a  mov     r8d, ebx
0x140006d7d  mov     rdx, rdi
0x140006d80  mov     rcx, rsi
0x140006d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d88  mov     rbx, [rsp+28h+arg_0]
0x140006d8d  mov     rsi, [rsp+28h+arg_8]
0x140006d92  add     rsp, 20h
0x140006d96  pop     rdi
0x140006d97  retn
```
