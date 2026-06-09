# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005720`
- end: `0x180005777`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002244`
- `0x180005720`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000573f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000573f`

## string_xrefs

- `0x180005735`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x180005720  mov     [rsp+arg_0], rbx
0x180005725  mov     [rsp+arg_8], rsi
0x18000572a  push    rdi
0x18000572b  sub     rsp, 20h
0x18000572f  mov     rsi, rcx
0x180005732  mov     ebx, r8d
0x180005735  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000573c  mov     rdi, rdx
0x18000573f  call    cs:__imp_GetModuleHandleW
0x180005746  nop     dword ptr [rax+rax+00h]
0x18000574b  mov     rcx, rax
0x18000574e  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x180005753  test    rax, rax
0x180005756  jz      short loc_180005766
0x180005758  mov     r8d, ebx
0x18000575b  mov     rdx, rdi
0x18000575e  mov     rcx, rsi
0x180005761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005766  mov     rbx, [rsp+28h+arg_0]
0x18000576b  mov     rsi, [rsp+28h+arg_8]
0x180005770  add     rsp, 20h
0x180005774  pop     rdi
0x180005775  retn
```
