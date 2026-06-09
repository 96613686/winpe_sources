# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18002d210`
- end: `0x18002d268`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002d210`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d23f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d23f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d22f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d22f`

## string_xrefs

- `0x18002d225`: `kernelbase.dll`

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
0x18002d210  mov     [rsp+arg_0], rbx
0x18002d215  mov     [rsp+arg_8], rsi
0x18002d21a  push    rdi
0x18002d21b  sub     rsp, 20h
0x18002d21f  mov     rsi, rcx
0x18002d222  mov     ebx, r8d
0x18002d225  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002d22c  mov     rdi, rdx
0x18002d22f  call    cs:__imp_GetModuleHandleW
0x18002d235  mov     rcx, rax; hModule
0x18002d238  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18002d23f  call    cs:__imp_GetProcAddress
0x18002d245  test    rax, rax
0x18002d248  jz      short loc_18002D258
0x18002d24a  mov     r8d, ebx
0x18002d24d  mov     rdx, rdi
0x18002d250  mov     rcx, rsi
0x18002d253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d258  mov     rbx, [rsp+28h+arg_0]
0x18002d25d  mov     rsi, [rsp+28h+arg_8]
0x18002d262  add     rsp, 20h
0x18002d266  pop     rdi
0x18002d267  retn
```
