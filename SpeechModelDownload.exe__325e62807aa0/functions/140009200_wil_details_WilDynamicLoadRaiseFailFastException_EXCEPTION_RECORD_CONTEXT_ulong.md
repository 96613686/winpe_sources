# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140009200`
- end: `0x140009258`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009200`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000921f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000921f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000922f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000922f`

## string_xrefs

- `0x140009215`: `kernelbase.dll`

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
0x140009200  mov     [rsp+arg_0], rbx
0x140009205  mov     [rsp+arg_8], rsi
0x14000920a  push    rdi
0x14000920b  sub     rsp, 20h
0x14000920f  mov     rsi, rcx
0x140009212  mov     ebx, r8d
0x140009215  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000921c  mov     rdi, rdx
0x14000921f  call    cs:__imp_GetModuleHandleW
0x140009225  mov     rcx, rax; hModule
0x140009228  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000922f  call    cs:__imp_GetProcAddress
0x140009235  test    rax, rax
0x140009238  jz      short loc_140009248
0x14000923a  mov     r8d, ebx
0x14000923d  mov     rdx, rdi
0x140009240  mov     rcx, rsi
0x140009243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009248  mov     rbx, [rsp+28h+arg_0]
0x14000924d  mov     rsi, [rsp+28h+arg_8]
0x140009252  add     rsp, 20h
0x140009256  pop     rdi
0x140009257  retn
```
