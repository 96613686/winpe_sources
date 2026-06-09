# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180058250`
- end: `0x1800582b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `104`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180058250`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005826f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005826f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058286`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058286`

## string_xrefs

- `0x180058268`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v3 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v3);
}

```

## disassembly

```asm
0x180058250  mov     [rsp+arg_0], rbx
0x180058255  mov     [rsp+arg_8], rsi
0x18005825a  push    rdi
0x18005825b  sub     rsp, 20h
0x18005825f  mov     ebx, r8d
0x180058262  mov     rdi, rdx
0x180058265  mov     rsi, rcx
0x180058268  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18005826f  call    cs:__imp_GetModuleHandleW
0x180058276  nop     dword ptr [rax+rax+00h]
0x18005827b  nop
0x18005827c  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180058283  mov     rcx, rax; hModule
0x180058286  call    cs:__imp_GetProcAddress
0x18005828d  nop     dword ptr [rax+rax+00h]
0x180058292  nop
0x180058293  test    rax, rax
0x180058296  jz      short loc_1800582A7
0x180058298  mov     r8d, ebx
0x18005829b  mov     rdx, rdi
0x18005829e  mov     rcx, rsi
0x1800582a1  call    cs:__guard_dispatch_icall_fptr
0x1800582a7  mov     rbx, [rsp+28h+arg_0]
0x1800582ac  mov     rsi, [rsp+28h+arg_8]
0x1800582b1  add     rsp, 20h
0x1800582b5  pop     rdi
0x1800582b6  retn
```
