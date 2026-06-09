# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008650`
- end: `0x1800086a8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008650`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000866f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000866f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000867f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000867f`

## string_xrefs

- `0x180008665`: `kernelbase.dll`

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
0x180008650  mov     [rsp+arg_0], rbx
0x180008655  mov     [rsp+arg_8], rsi
0x18000865a  push    rdi
0x18000865b  sub     rsp, 20h
0x18000865f  mov     rsi, rcx
0x180008662  mov     ebx, r8d
0x180008665  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000866c  mov     rdi, rdx
0x18000866f  call    cs:__imp_GetModuleHandleW
0x180008675  mov     rcx, rax; hModule
0x180008678  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000867f  call    cs:__imp_GetProcAddress
0x180008685  test    rax, rax
0x180008688  jz      short loc_180008698
0x18000868a  mov     r8d, ebx
0x18000868d  mov     rdx, rdi
0x180008690  mov     rcx, rsi
0x180008693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008698  mov     rbx, [rsp+28h+arg_0]
0x18000869d  mov     rsi, [rsp+28h+arg_8]
0x1800086a2  add     rsp, 20h
0x1800086a6  pop     rdi
0x1800086a7  retn
```
