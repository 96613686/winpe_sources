# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180004320`
- end: `0x180004378`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004320`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000434f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000434f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000433f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000433f`

## string_xrefs

- `0x180004335`: `kernelbase.dll`

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
0x180004320  mov     [rsp+arg_0], rbx
0x180004325  mov     [rsp+arg_8], rsi
0x18000432a  push    rdi
0x18000432b  sub     rsp, 20h
0x18000432f  mov     rsi, rcx
0x180004332  mov     ebx, r8d
0x180004335  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000433c  mov     rdi, rdx
0x18000433f  call    cs:__imp_GetModuleHandleW
0x180004345  mov     rcx, rax; hModule
0x180004348  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000434f  call    cs:__imp_GetProcAddress
0x180004355  test    rax, rax
0x180004358  jz      short loc_180004368
0x18000435a  mov     r8d, ebx
0x18000435d  mov     rdx, rdi
0x180004360  mov     rcx, rsi
0x180004363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004368  mov     rbx, [rsp+28h+arg_0]
0x18000436d  mov     rsi, [rsp+28h+arg_8]
0x180004372  add     rsp, 20h
0x180004376  pop     rdi
0x180004377  retn
```
