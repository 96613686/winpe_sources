# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005a10`
- end: `0x180005a68`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005a10`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a3f`

## string_xrefs

- `0x180005a25`: `kernelbase.dll`

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
0x180005a10  mov     [rsp+arg_0], rbx
0x180005a15  mov     [rsp+arg_8], rsi
0x180005a1a  push    rdi
0x180005a1b  sub     rsp, 20h
0x180005a1f  mov     rsi, rcx
0x180005a22  mov     ebx, r8d
0x180005a25  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005a2c  mov     rdi, rdx
0x180005a2f  call    cs:__imp_GetModuleHandleW
0x180005a35  mov     rcx, rax; hModule
0x180005a38  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180005a3f  call    cs:__imp_GetProcAddress
0x180005a45  test    rax, rax
0x180005a48  jz      short loc_180005A58
0x180005a4a  mov     r8d, ebx
0x180005a4d  mov     rdx, rdi
0x180005a50  mov     rcx, rsi
0x180005a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a58  mov     rbx, [rsp+28h+arg_0]
0x180005a5d  mov     rsi, [rsp+28h+arg_8]
0x180005a62  add     rsp, 20h
0x180005a66  pop     rdi
0x180005a67  retn
```
