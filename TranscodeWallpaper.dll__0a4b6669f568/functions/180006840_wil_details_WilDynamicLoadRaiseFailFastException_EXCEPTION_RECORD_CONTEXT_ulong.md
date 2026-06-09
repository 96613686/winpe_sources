# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180006840`
- end: `0x180006898`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006840`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000686f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000686f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000685f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000685f`

## string_xrefs

- `0x180006855`: `kernelbase.dll`

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
0x180006840  mov     [rsp+arg_0], rbx
0x180006845  mov     [rsp+arg_8], rsi
0x18000684a  push    rdi
0x18000684b  sub     rsp, 20h
0x18000684f  mov     rsi, rcx
0x180006852  mov     ebx, r8d
0x180006855  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000685c  mov     rdi, rdx
0x18000685f  call    cs:__imp_GetModuleHandleW
0x180006865  mov     rcx, rax; hModule
0x180006868  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000686f  call    cs:__imp_GetProcAddress
0x180006875  test    rax, rax
0x180006878  jz      short loc_180006888
0x18000687a  mov     r8d, ebx
0x18000687d  mov     rdx, rdi
0x180006880  mov     rcx, rsi
0x180006883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006888  mov     rbx, [rsp+28h+arg_0]
0x18000688d  mov     rsi, [rsp+28h+arg_8]
0x180006892  add     rsp, 20h
0x180006896  pop     rdi
0x180006897  retn
```
