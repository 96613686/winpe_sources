# LoadInterfaceFromPrintVerifier(ushort const *,IUnknown *,_GUID const &,_GUID const &,IUnknown * *)

- ea: `0x18004ffb0`
- end: `0x180050022`
- name: `?LoadInterfaceFromPrintVerifier@@YAJPEBGPEAUIUnknown@@AEBU_GUID@@2PEAPEAU1@@Z`
- size: `114`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, const struct _GUID *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180036894`

## callees

- `0x18004ffb0`
- `0x180075010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18004ffdb`
- `KERNEL32!GetProcAddress` at `0x18004ffdb`

## string_xrefs

- `0x18004ffd4`: `PrintVerifierCreatePluginInterfaceWrapper`

## pseudocode

```c
__int64 __fastcall LoadInterfaceFromPrintVerifier(
        const unsigned __int16 *a1,
        struct IUnknown *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  FARPROC ProcAddress; // rax

  if ( ghPrintVerifierModule
    && (ProcAddress = GetProcAddress(ghPrintVerifierModule, "PrintVerifierCreatePluginInterfaceWrapper")) != 0 )
  {
    return ((__int64 (__fastcall *)(const unsigned __int16 *, struct IUnknown *, GUID *, const struct _GUID *, struct IUnknown **))ProcAddress)(
             a1,
             a2,
             &CLSID_OEMRENDER,
             a4,
             a5);
  }
  else
  {
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18004ffb0  mov     [rsp+arg_0], rbx
0x18004ffb5  mov     [rsp+arg_8], rsi
0x18004ffba  push    rdi
0x18004ffbb  sub     rsp, 30h
0x18004ffbf  mov     rsi, rcx
0x18004ffc2  mov     rbx, r9
0x18004ffc5  mov     rcx, cs:ghPrintVerifierModule; hModule
0x18004ffcc  mov     rdi, rdx
0x18004ffcf  test    rcx, rcx
0x18004ffd2  jz      short loc_18005000D
0x18004ffd4  lea     rdx, aPrintverifierc; "PrintVerifierCreatePluginInterfaceWrapp"...
0x18004ffdb  call    cs:__imp_GetProcAddress
0x18004ffe1  mov     r10, rax
0x18004ffe4  test    rax, rax
0x18004ffe7  jz      short loc_18005000D
0x18004ffe9  mov     rax, [rsp+38h+arg_20]
0x18004ffee  lea     r8, CLSID_OEMRENDER
0x18004fff5  mov     [rsp+38h+var_18], rax
0x18004fffa  mov     r9, rbx
0x18004fffd  mov     rax, r10
0x180050000  mov     rdx, rdi
0x180050003  mov     rcx, rsi
0x180050006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005000b  jmp     short loc_180050012
0x18005000d  mov     eax, 8000FFFFh
0x180050012  mov     rbx, [rsp+38h+arg_0]
0x180050017  mov     rsi, [rsp+38h+arg_8]
0x18005001c  add     rsp, 30h
0x180050020  pop     rdi
0x180050021  retn
```
