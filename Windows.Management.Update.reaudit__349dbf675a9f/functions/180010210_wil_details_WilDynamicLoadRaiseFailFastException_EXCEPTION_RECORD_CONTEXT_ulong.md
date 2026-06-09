# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180010210`
- end: `0x180010275`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010210`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010245`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010245`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001022f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001022f`

## string_xrefs

- `0x180010225`: `kernelbase.dll`

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
0x180010210  mov     [rsp+arg_0], rbx
0x180010215  mov     [rsp+arg_8], rsi
0x18001021a  push    rdi
0x18001021b  sub     rsp, 20h
0x18001021f  mov     rsi, rcx
0x180010222  mov     ebx, r8d
0x180010225  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001022c  mov     rdi, rdx
0x18001022f  call    cs:__imp_GetModuleHandleW
0x180010236  nop     dword ptr [rax+rax+00h]
0x18001023b  mov     rcx, rax; hModule
0x18001023e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180010245  call    cs:__imp_GetProcAddress
0x18001024c  nop     dword ptr [rax+rax+00h]
0x180010251  test    rax, rax
0x180010254  jz      short loc_180010264
0x180010256  mov     r8d, ebx
0x180010259  mov     rdx, rdi
0x18001025c  mov     rcx, rsi
0x18001025f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010264  mov     rbx, [rsp+28h+arg_0]
0x180010269  mov     rsi, [rsp+28h+arg_8]
0x18001026e  add     rsp, 20h
0x180010272  pop     rdi
0x180010273  retn
```
