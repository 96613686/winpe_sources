# WINRT_IMPL_RoGetActivationFactory

- ea: `0x18000b4d0`
- end: `0x18000b55b`
- name: `WINRT_IMPL_RoGetActivationFactory`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d7f0`

## callees

- `0x180002aaf`
- `0x18000b4d0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000b50d`
- `KERNEL32!LoadLibraryExW` at `0x18000b50d`

## string_xrefs

- `0x18000b506`: `combase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WINRT_IMPL_RoGetActivationFactory(__int64 a1, __int64 a2, __int64 a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)`winrt::impl::downlevel::runtime_RoGetActivationFactory'::`2'::handler;
  if ( !`winrt::impl::downlevel::runtime_RoGetActivationFactory'::`2'::handler )
  {
    Library = LoadLibraryExW(L"combase.dll", 0, 0x800u);
    ProcAddress = WINRT_IMPL_GetProcAddress(Library, "RoGetActivationFactory");
    `winrt::impl::downlevel::runtime_RoGetActivationFactory'::`2'::handler = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      ProcAddress = (FARPROC)winrt::impl::downlevel::fallback_RoGetActivationFactory;
      `winrt::impl::downlevel::runtime_RoGetActivationFactory'::`2'::handler = (__int64)winrt::impl::downlevel::fallback_RoGetActivationFactory;
    }
  }
  return ((__int64 (__fastcall *)(__int64, __int64, __int64))ProcAddress)(a1, a2, a3);
}

```

## disassembly

```asm
0x18000b4d0  push    rdi
0x18000b4d2  sub     rsp, 30h
0x18000b4d6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000b4df  mov     [rsp+38h+arg_0], rbx
0x18000b4e4  mov     [rsp+38h+arg_8], rsi
0x18000b4e9  mov     rbx, r8
0x18000b4ec  mov     rdi, rdx
0x18000b4ef  mov     rsi, rcx
0x18000b4f2  mov     rax, cs:?handler@?1??runtime_RoGetActivationFactory@downlevel@impl@winrt@@YAHPEAXAEBUguid@4@PEAPEAX@Z@4P6AH012@_EEA
0x18000b4f9  test    rax, rax
0x18000b4fc  jnz     short loc_18000B53C
0x18000b4fe  xor     edx, edx; hFile
0x18000b500  mov     r8d, 800h; dwFlags
0x18000b506  lea     rcx, LibFileName; "combase.dll"
0x18000b50d  call    cs:__imp_LoadLibraryExW
0x18000b513  mov     rcx, rax; hModule
0x18000b516  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x18000b51d  call    WINRT_IMPL_GetProcAddress
0x18000b522  mov     cs:?handler@?1??runtime_RoGetActivationFactory@downlevel@impl@winrt@@YAHPEAXAEBUguid@4@PEAPEAX@Z@4P6AH012@_EEA, rax
0x18000b529  test    rax, rax
0x18000b52c  jnz     short loc_18000B53C
0x18000b52e  lea     rax, ?fallback_RoGetActivationFactory@downlevel@impl@winrt@@YAHPEAXAEBUguid@3@PEAPEAX@Z; winrt::impl::downlevel::fallback_RoGetActivationFactory(void *,winrt::guid const &,void * *)
0x18000b535  mov     cs:?handler@?1??runtime_RoGetActivationFactory@downlevel@impl@winrt@@YAHPEAXAEBUguid@4@PEAPEAX@Z@4P6AH012@_EEA, rax
0x18000b53c  mov     r8, rbx
0x18000b53f  mov     rdx, rdi
0x18000b542  mov     rcx, rsi
0x18000b545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b54a  nop
0x18000b54b  mov     rbx, [rsp+38h+arg_0]
0x18000b550  mov     rsi, [rsp+38h+arg_8]
0x18000b555  add     rsp, 30h
0x18000b559  pop     rdi
0x18000b55a  retn
```
