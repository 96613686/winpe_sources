# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008790`
- end: `0x1800087e8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008790`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800087af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800087af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087bf`

## string_xrefs

- `0x1800087a5`: `kernelbase.dll`

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
0x180008790  mov     [rsp+arg_0], rbx
0x180008795  mov     [rsp+arg_8], rsi
0x18000879a  push    rdi
0x18000879b  sub     rsp, 20h
0x18000879f  mov     rsi, rcx
0x1800087a2  mov     ebx, r8d
0x1800087a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800087ac  mov     rdi, rdx
0x1800087af  call    cs:__imp_GetModuleHandleW
0x1800087b5  mov     rcx, rax; hModule
0x1800087b8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800087bf  call    cs:__imp_GetProcAddress
0x1800087c5  test    rax, rax
0x1800087c8  jz      short loc_1800087D8
0x1800087ca  mov     r8d, ebx
0x1800087cd  mov     rdx, rdi
0x1800087d0  mov     rcx, rsi
0x1800087d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d8  mov     rbx, [rsp+28h+arg_0]
0x1800087dd  mov     rsi, [rsp+28h+arg_8]
0x1800087e2  add     rsp, 20h
0x1800087e6  pop     rdi
0x1800087e7  retn
```
