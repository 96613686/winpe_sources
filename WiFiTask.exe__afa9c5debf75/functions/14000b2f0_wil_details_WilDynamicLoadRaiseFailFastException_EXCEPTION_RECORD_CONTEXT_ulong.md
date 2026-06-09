# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000b2f0`
- end: `0x14000b348`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b2f0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b30f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b30f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b31f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b31f`

## string_xrefs

- `0x14000b305`: `kernelbase.dll`

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
0x14000b2f0  mov     [rsp+arg_0], rbx
0x14000b2f5  mov     [rsp+arg_8], rsi
0x14000b2fa  push    rdi
0x14000b2fb  sub     rsp, 20h
0x14000b2ff  mov     rsi, rcx
0x14000b302  mov     ebx, r8d
0x14000b305  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000b30c  mov     rdi, rdx
0x14000b30f  call    cs:__imp_GetModuleHandleW
0x14000b315  mov     rcx, rax; hModule
0x14000b318  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000b31f  call    cs:__imp_GetProcAddress
0x14000b325  test    rax, rax
0x14000b328  jz      short loc_14000B338
0x14000b32a  mov     r8d, ebx
0x14000b32d  mov     rdx, rdi
0x14000b330  mov     rcx, rsi
0x14000b333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b338  mov     rbx, [rsp+28h+arg_0]
0x14000b33d  mov     rsi, [rsp+28h+arg_8]
0x14000b342  add     rsp, 20h
0x14000b346  pop     rdi
0x14000b347  retn
```
