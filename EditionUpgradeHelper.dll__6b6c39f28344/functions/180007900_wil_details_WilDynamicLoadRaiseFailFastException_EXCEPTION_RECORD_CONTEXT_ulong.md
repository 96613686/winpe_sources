# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007900`
- end: `0x180007958`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007900`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000791f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000791f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000792f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000792f`

## string_xrefs

- `0x180007915`: `kernelbase.dll`

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
0x180007900  mov     [rsp+arg_0], rbx
0x180007905  mov     [rsp+arg_8], rsi
0x18000790a  push    rdi
0x18000790b  sub     rsp, 20h
0x18000790f  mov     rsi, rcx
0x180007912  mov     ebx, r8d
0x180007915  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000791c  mov     rdi, rdx
0x18000791f  call    cs:__imp_GetModuleHandleW
0x180007925  mov     rcx, rax; hModule
0x180007928  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000792f  call    cs:__imp_GetProcAddress
0x180007935  test    rax, rax
0x180007938  jz      short loc_180007948
0x18000793a  mov     r8d, ebx
0x18000793d  mov     rdx, rdi
0x180007940  mov     rcx, rsi
0x180007943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007948  mov     rbx, [rsp+28h+arg_0]
0x18000794d  mov     rsi, [rsp+28h+arg_8]
0x180007952  add     rsp, 20h
0x180007956  pop     rdi
0x180007957  retn
```
