# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005890`
- end: `0x1800058e8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005890`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800058bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800058bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058af`

## string_xrefs

- `0x1800058a5`: `kernelbase.dll`

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
0x180005890  mov     [rsp+arg_0], rbx
0x180005895  mov     [rsp+arg_8], rsi
0x18000589a  push    rdi
0x18000589b  sub     rsp, 20h
0x18000589f  mov     rsi, rcx
0x1800058a2  mov     ebx, r8d
0x1800058a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800058ac  mov     rdi, rdx
0x1800058af  call    cs:__imp_GetModuleHandleW
0x1800058b5  mov     rcx, rax; hModule
0x1800058b8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800058bf  call    cs:__imp_GetProcAddress
0x1800058c5  test    rax, rax
0x1800058c8  jz      short loc_1800058D8
0x1800058ca  mov     r8d, ebx
0x1800058cd  mov     rdx, rdi
0x1800058d0  mov     rcx, rsi
0x1800058d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d8  mov     rbx, [rsp+28h+arg_0]
0x1800058dd  mov     rsi, [rsp+28h+arg_8]
0x1800058e2  add     rsp, 20h
0x1800058e6  pop     rdi
0x1800058e7  retn
```
