# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1400054a0`
- end: `0x1400054f8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400054a0`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400054bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400054bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400054cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400054cf`

## string_xrefs

- `0x1400054b5`: `kernelbase.dll`

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
0x1400054a0  mov     [rsp+arg_0], rbx
0x1400054a5  mov     [rsp+arg_8], rsi
0x1400054aa  push    rdi
0x1400054ab  sub     rsp, 20h
0x1400054af  mov     rsi, rcx
0x1400054b2  mov     ebx, r8d
0x1400054b5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400054bc  mov     rdi, rdx
0x1400054bf  call    cs:__imp_GetModuleHandleW
0x1400054c5  mov     rcx, rax; hModule
0x1400054c8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1400054cf  call    cs:__imp_GetProcAddress
0x1400054d5  test    rax, rax
0x1400054d8  jz      short loc_1400054E8
0x1400054da  mov     r8d, ebx
0x1400054dd  mov     rdx, rdi
0x1400054e0  mov     rcx, rsi
0x1400054e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054e8  mov     rbx, [rsp+28h+arg_0]
0x1400054ed  mov     rsi, [rsp+28h+arg_8]
0x1400054f2  add     rsp, 20h
0x1400054f6  pop     rdi
0x1400054f7  retn
```
