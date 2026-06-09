# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x4068c0`
- end: `0x4068fb`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YGXPAU_EXCEPTION_RECORD@@PAU_CONTEXT@@K@Z`
- size: `59`
- prototype: `void __stdcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4068c0`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x4068d7`
- `KERNEL32!GetProcAddress` at `0x4068d7`
- `KERNEL32!GetModuleHandleW` at `0x4068cb`
- `KERNEL32!GetModuleHandleW` at `0x4068cb`

## string_xrefs

- `0x4068c6`: `kernelbase.dll`

## pseudocode

```c
void __stdcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3,
        unsigned int a4)
{
  HMODULE ModuleHandleW; // eax
  void (__stdcall *RaiseFailFastException)(PEXCEPTION_RECORD, PCONTEXT, DWORD); // eax

  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  RaiseFailFastException = (void (__stdcall *)(PEXCEPTION_RECORD, PCONTEXT, DWORD))GetProcAddress(
                                                                                     ModuleHandleW,
                                                                                     "RaiseFailFastException");
  if ( RaiseFailFastException )
    ((void (__thiscall *)(void (__stdcall *)(PEXCEPTION_RECORD, PCONTEXT, DWORD), wil::details *, struct _EXCEPTION_RECORD *, struct _CONTEXT *))RaiseFailFastException)(
      RaiseFailFastException,
      this,
      a2,
      a3);
}

```

## disassembly

```asm
0x4068c0  mov     edi, edi
0x4068c2  push    ebp
0x4068c3  mov     ebp, esp
0x4068c5  push    esi
0x4068c6  push    offset ModuleName; "kernelbase.dll"
0x4068cb  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x4068d1  push    offset aRaisefailfaste; "RaiseFailFastException"
0x4068d6  push    eax; hModule
0x4068d7  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x4068dd  mov     esi, eax
0x4068df  test    esi, esi
0x4068e1  jz      short loc_4068F6
0x4068e3  push    [ebp+arg_8]
0x4068e6  mov     ecx, esi
0x4068e8  push    [ebp+arg_4]
0x4068eb  push    [ebp+this]
0x4068ee  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x4068f4  call    esi
0x4068f6  pop     esi
0x4068f7  pop     ebp
0x4068f8  retn    0Ch
```
