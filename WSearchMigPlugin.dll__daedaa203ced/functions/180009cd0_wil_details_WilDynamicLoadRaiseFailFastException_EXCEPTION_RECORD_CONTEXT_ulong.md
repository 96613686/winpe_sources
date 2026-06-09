# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009cd0`
- end: `0x180009d28`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009cd0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009cef`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180009cef`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009cff`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009cff`

## string_xrefs

- `0x180009ce5`: `kernelbase.dll`

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
0x180009cd0  mov     [rsp+arg_0], rbx
0x180009cd5  mov     [rsp+arg_8], rsi
0x180009cda  push    rdi
0x180009cdb  sub     rsp, 20h
0x180009cdf  mov     rsi, rcx
0x180009ce2  mov     ebx, r8d
0x180009ce5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009cec  mov     rdi, rdx
0x180009cef  call    cs:__imp_GetModuleHandleW
0x180009cf5  mov     rcx, rax; hModule
0x180009cf8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180009cff  call    cs:__imp_GetProcAddress
0x180009d05  test    rax, rax
0x180009d08  jz      short loc_180009D18
0x180009d0a  mov     r8d, ebx
0x180009d0d  mov     rdx, rdi
0x180009d10  mov     rcx, rsi
0x180009d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d18  mov     rbx, [rsp+28h+arg_0]
0x180009d1d  mov     rsi, [rsp+28h+arg_8]
0x180009d22  add     rsp, 20h
0x180009d26  pop     rdi
0x180009d27  retn
```
