# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180011e90`
- end: `0x180011ef5`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011e90`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011eaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011eaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011ec5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011ec5`

## string_xrefs

- `0x180011ea5`: `kernelbase.dll`

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
0x180011e90  mov     [rsp+arg_0], rbx
0x180011e95  mov     [rsp+arg_8], rsi
0x180011e9a  push    rdi
0x180011e9b  sub     rsp, 20h
0x180011e9f  mov     rsi, rcx
0x180011ea2  mov     ebx, r8d
0x180011ea5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180011eac  mov     rdi, rdx
0x180011eaf  call    cs:__imp_GetModuleHandleW
0x180011eb6  nop     dword ptr [rax+rax+00h]
0x180011ebb  mov     rcx, rax; hModule
0x180011ebe  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180011ec5  call    cs:__imp_GetProcAddress
0x180011ecc  nop     dword ptr [rax+rax+00h]
0x180011ed1  test    rax, rax
0x180011ed4  jz      short loc_180011EE4
0x180011ed6  mov     r8d, ebx
0x180011ed9  mov     rdx, rdi
0x180011edc  mov     rcx, rsi
0x180011edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ee4  mov     rbx, [rsp+28h+arg_0]
0x180011ee9  mov     rsi, [rsp+28h+arg_8]
0x180011eee  add     rsp, 20h
0x180011ef2  pop     rdi
0x180011ef3  retn
```
