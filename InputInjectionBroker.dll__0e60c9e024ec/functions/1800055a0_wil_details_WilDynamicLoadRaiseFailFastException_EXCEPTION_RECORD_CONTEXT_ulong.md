# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800055a0`
- end: `0x1800055f8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800055a0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055bf`

## string_xrefs

- `0x1800055b5`: `kernelbase.dll`

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
0x1800055a0  mov     [rsp+arg_0], rbx
0x1800055a5  mov     [rsp+arg_8], rsi
0x1800055aa  push    rdi
0x1800055ab  sub     rsp, 20h
0x1800055af  mov     rsi, rcx
0x1800055b2  mov     ebx, r8d
0x1800055b5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800055bc  mov     rdi, rdx
0x1800055bf  call    cs:__imp_GetModuleHandleW
0x1800055c5  mov     rcx, rax; hModule
0x1800055c8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800055cf  call    cs:__imp_GetProcAddress
0x1800055d5  test    rax, rax
0x1800055d8  jz      short loc_1800055E8
0x1800055da  mov     r8d, ebx
0x1800055dd  mov     rdx, rdi
0x1800055e0  mov     rcx, rsi
0x1800055e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055e8  mov     rbx, [rsp+28h+arg_0]
0x1800055ed  mov     rsi, [rsp+28h+arg_8]
0x1800055f2  add     rsp, 20h
0x1800055f6  pop     rdi
0x1800055f7  retn
```
