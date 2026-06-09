# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008400`
- end: `0x180008458`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008400`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000842f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000842f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000841f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000841f`

## string_xrefs

- `0x180008415`: `kernelbase.dll`

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
0x180008400  mov     [rsp+arg_0], rbx
0x180008405  mov     [rsp+arg_8], rsi
0x18000840a  push    rdi
0x18000840b  sub     rsp, 20h
0x18000840f  mov     rsi, rcx
0x180008412  mov     ebx, r8d
0x180008415  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000841c  mov     rdi, rdx
0x18000841f  call    cs:__imp_GetModuleHandleW
0x180008425  mov     rcx, rax; hModule
0x180008428  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000842f  call    cs:__imp_GetProcAddress
0x180008435  test    rax, rax
0x180008438  jz      short loc_180008448
0x18000843a  mov     r8d, ebx
0x18000843d  mov     rdx, rdi
0x180008440  mov     rcx, rsi
0x180008443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008448  mov     rbx, [rsp+28h+arg_0]
0x18000844d  mov     rsi, [rsp+28h+arg_8]
0x180008452  add     rsp, 20h
0x180008456  pop     rdi
0x180008457  retn
```
