# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1400071c0`
- end: `0x140007218`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400071c0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400071ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400071ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400071df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400071df`

## string_xrefs

- `0x1400071d5`: `kernelbase.dll`

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
0x1400071c0  mov     [rsp+arg_0], rbx
0x1400071c5  mov     [rsp+arg_8], rsi
0x1400071ca  push    rdi
0x1400071cb  sub     rsp, 20h
0x1400071cf  mov     rsi, rcx
0x1400071d2  mov     ebx, r8d
0x1400071d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400071dc  mov     rdi, rdx
0x1400071df  call    cs:__imp_GetModuleHandleW
0x1400071e5  mov     rcx, rax; hModule
0x1400071e8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1400071ef  call    cs:__imp_GetProcAddress
0x1400071f5  test    rax, rax
0x1400071f8  jz      short loc_140007208
0x1400071fa  mov     r8d, ebx
0x1400071fd  mov     rdx, rdi
0x140007200  mov     rcx, rsi
0x140007203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007208  mov     rbx, [rsp+28h+arg_0]
0x14000720d  mov     rsi, [rsp+28h+arg_8]
0x140007212  add     rsp, 20h
0x140007216  pop     rdi
0x140007217  retn
```
