# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007bd0`
- end: `0x180007c28`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007bd0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007bff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007bff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007bef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007bef`

## string_xrefs

- `0x180007be5`: `kernelbase.dll`

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
0x180007bd0  mov     [rsp+arg_0], rbx
0x180007bd5  mov     [rsp+arg_8], rsi
0x180007bda  push    rdi
0x180007bdb  sub     rsp, 20h
0x180007bdf  mov     rsi, rcx
0x180007be2  mov     ebx, r8d
0x180007be5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007bec  mov     rdi, rdx
0x180007bef  call    cs:__imp_GetModuleHandleW
0x180007bf5  mov     rcx, rax; hModule
0x180007bf8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180007bff  call    cs:__imp_GetProcAddress
0x180007c05  test    rax, rax
0x180007c08  jz      short loc_180007C18
0x180007c0a  mov     r8d, ebx
0x180007c0d  mov     rdx, rdi
0x180007c10  mov     rcx, rsi
0x180007c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c18  mov     rbx, [rsp+28h+arg_0]
0x180007c1d  mov     rsi, [rsp+28h+arg_8]
0x180007c22  add     rsp, 20h
0x180007c26  pop     rdi
0x180007c27  retn
```
