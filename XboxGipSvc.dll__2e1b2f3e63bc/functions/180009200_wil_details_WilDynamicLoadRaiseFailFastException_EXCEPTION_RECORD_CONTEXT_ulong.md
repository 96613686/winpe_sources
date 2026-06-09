# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180009200`
- end: `0x180009258`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009200`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000922f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000922f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000921f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000921f`

## string_xrefs

- `0x180009215`: `kernelbase.dll`

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
0x180009200  mov     [rsp+arg_0], rbx
0x180009205  mov     [rsp+arg_8], rsi
0x18000920a  push    rdi
0x18000920b  sub     rsp, 20h
0x18000920f  mov     rsi, rcx
0x180009212  mov     ebx, r8d
0x180009215  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000921c  mov     rdi, rdx
0x18000921f  call    cs:__imp_GetModuleHandleW
0x180009225  mov     rcx, rax; hModule
0x180009228  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000922f  call    cs:__imp_GetProcAddress
0x180009235  test    rax, rax
0x180009238  jz      short loc_180009248
0x18000923a  mov     r8d, ebx
0x18000923d  mov     rdx, rdi
0x180009240  mov     rcx, rsi
0x180009243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009248  mov     rbx, [rsp+28h+arg_0]
0x18000924d  mov     rsi, [rsp+28h+arg_8]
0x180009252  add     rsp, 20h
0x180009256  pop     rdi
0x180009257  retn
```
