# LoadInterfaceFromPrintVerifier(ushort const *,IUnknown *,_GUID const &,_GUID const &,IUnknown * *)

- ea: `0x180051710`
- end: `0x180051789`
- name: `?LoadInterfaceFromPrintVerifier@@YAJPEBGPEAUIUnknown@@AEBU_GUID@@2PEAPEAU1@@Z`
- size: `121`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, const struct _GUID *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800372c4`

## callees

- `0x180051710`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18005173b`
- `KERNEL32!GetProcAddress` at `0x18005173b`

## string_xrefs

- `0x180051734`: `PrintVerifierCreatePluginInterfaceWrapper`

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
0x180051710  mov     [rsp+arg_0], rbx
0x180051715  mov     [rsp+arg_8], rsi
0x18005171a  push    rdi
0x18005171b  sub     rsp, 30h
0x18005171f  mov     rsi, rcx
0x180051722  mov     rbx, r9
0x180051725  mov     rcx, cs:ghPrintVerifierModule; hModule
0x18005172c  mov     rdi, rdx
0x18005172f  test    rcx, rcx
0x180051732  jz      short loc_180051773
0x180051734  lea     rdx, aPrintverifierc; "PrintVerifierCreatePluginInterfaceWrapp"...
0x18005173b  call    cs:__imp_GetProcAddress
0x180051742  nop     dword ptr [rax+rax+00h]
0x180051747  mov     r10, rax
0x18005174a  test    rax, rax
0x18005174d  jz      short loc_180051773
0x18005174f  mov     rax, [rsp+38h+arg_20]
0x180051754  lea     r8, CLSID_OEMRENDER
0x18005175b  mov     [rsp+38h+var_18], rax
0x180051760  mov     r9, rbx
0x180051763  mov     rax, r10
0x180051766  mov     rdx, rdi
0x180051769  mov     rcx, rsi
0x18005176c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051771  jmp     short loc_180051778
0x180051773  mov     eax, 8000FFFFh
0x180051778  mov     rbx, [rsp+38h+arg_0]
0x18005177d  mov     rsi, [rsp+38h+arg_8]
0x180051782  add     rsp, 30h
0x180051786  pop     rdi
0x180051787  retn
```
