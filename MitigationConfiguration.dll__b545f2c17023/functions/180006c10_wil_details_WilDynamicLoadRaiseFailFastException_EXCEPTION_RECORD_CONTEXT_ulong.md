# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006c10`
- end: `0x180006c68`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006c10`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c2f`

## string_xrefs

- `0x180006c25`: `kernelbase.dll`

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
0x180006c10  mov     [rsp+arg_0], rbx
0x180006c15  mov     [rsp+arg_8], rsi
0x180006c1a  push    rdi
0x180006c1b  sub     rsp, 20h
0x180006c1f  mov     rsi, rcx
0x180006c22  mov     ebx, r8d
0x180006c25  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006c2c  mov     rdi, rdx
0x180006c2f  call    cs:__imp_GetModuleHandleW
0x180006c35  mov     rcx, rax; hModule
0x180006c38  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180006c3f  call    cs:__imp_GetProcAddress
0x180006c45  test    rax, rax
0x180006c48  jz      short loc_180006C58
0x180006c4a  mov     r8d, ebx
0x180006c4d  mov     rdx, rdi
0x180006c50  mov     rcx, rsi
0x180006c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c58  mov     rbx, [rsp+28h+arg_0]
0x180006c5d  mov     rsi, [rsp+28h+arg_8]
0x180006c62  add     rsp, 20h
0x180006c66  pop     rdi
0x180006c67  retn
```
