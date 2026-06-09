# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009a80`
- end: `0x180009ad8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009a80`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009aaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009aaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009a9f`

## string_xrefs

- `0x180009a95`: `kernelbase.dll`

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
0x180009a80  mov     [rsp+arg_0], rbx
0x180009a85  mov     [rsp+arg_8], rsi
0x180009a8a  push    rdi
0x180009a8b  sub     rsp, 20h
0x180009a8f  mov     rsi, rcx
0x180009a92  mov     ebx, r8d
0x180009a95  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009a9c  mov     rdi, rdx
0x180009a9f  call    cs:__imp_GetModuleHandleW
0x180009aa5  mov     rcx, rax; hModule
0x180009aa8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180009aaf  call    cs:__imp_GetProcAddress
0x180009ab5  test    rax, rax
0x180009ab8  jz      short loc_180009AC8
0x180009aba  mov     r8d, ebx
0x180009abd  mov     rdx, rdi
0x180009ac0  mov     rcx, rsi
0x180009ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac8  mov     rbx, [rsp+28h+arg_0]
0x180009acd  mov     rsi, [rsp+28h+arg_8]
0x180009ad2  add     rsp, 20h
0x180009ad6  pop     rdi
0x180009ad7  retn
```
