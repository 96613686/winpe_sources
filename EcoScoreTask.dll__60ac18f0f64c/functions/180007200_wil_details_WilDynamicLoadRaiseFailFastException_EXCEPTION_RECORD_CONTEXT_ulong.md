# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007200`
- end: `0x180007258`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007200`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000722f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000722f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000721f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000721f`

## string_xrefs

- `0x180007215`: `kernelbase.dll`

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
0x180007200  mov     [rsp+arg_0], rbx
0x180007205  mov     [rsp+arg_8], rsi
0x18000720a  push    rdi
0x18000720b  sub     rsp, 20h
0x18000720f  mov     rsi, rcx
0x180007212  mov     ebx, r8d
0x180007215  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000721c  mov     rdi, rdx
0x18000721f  call    cs:__imp_GetModuleHandleW
0x180007225  mov     rcx, rax; hModule
0x180007228  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000722f  call    cs:__imp_GetProcAddress
0x180007235  test    rax, rax
0x180007238  jz      short loc_180007248
0x18000723a  mov     r8d, ebx
0x18000723d  mov     rdx, rdi
0x180007240  mov     rcx, rsi
0x180007243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007248  mov     rbx, [rsp+28h+arg_0]
0x18000724d  mov     rsi, [rsp+28h+arg_8]
0x180007252  add     rsp, 20h
0x180007256  pop     rdi
0x180007257  retn
```
