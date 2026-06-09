# IsEnumerationBlocked(IUnknown *)

- ea: `0x180003778`
- end: `0x1800037dc`
- name: `?IsEnumerationBlocked@@YAHPEAUIUnknown@@@Z`
- size: `100`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180003610`
- `0x18000c984`
- `0x18000caa8`
- `0x18000cb00`

## callees

- `0x180003778`
- `0x180010010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800037a0`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800037a0`

## pseudocode

```c
__int64 __fastcall IsEnumerationBlocked(struct IUnknown *a1)
{
  unsigned int v2; // [rsp+38h] [rbp+10h] BYREF
  void *ppvOut; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  ppvOut = 0;
  if ( IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_EnumerationOptions,
         &GUID_e9faf793_31c2_406a_8096_da07bf7de0a4,
         &ppvOut) >= 0 )
  {
    (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v2);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return v2;
}

```

## disassembly

```asm
0x180003778  sub     rsp, 28h
0x18000377c  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180003781  mov     [rsp+28h+arg_8], 0
0x180003789  lea     r8, _GUID_e9faf793_31c2_406a_8096_da07bf7de0a4; riid
0x180003790  mov     [rsp+28h+ppvOut], 0
0x180003799  lea     rdx, SID_EnumerationOptions; guidService
0x1800037a0  call    cs:__imp_IUnknown_QueryService
0x1800037a6  test    eax, eax
0x1800037a8  jns     short loc_1800037B3
0x1800037aa  mov     eax, [rsp+28h+arg_8]
0x1800037ae  add     rsp, 28h
0x1800037b2  retn
0x1800037b3  mov     rcx, [rsp+28h+ppvOut]
0x1800037b8  lea     rdx, [rsp+28h+arg_8]
0x1800037bd  mov     rax, [rcx]
0x1800037c0  mov     rax, [rax+18h]
0x1800037c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c9  mov     rcx, [rsp+28h+ppvOut]
0x1800037ce  mov     rax, [rcx]
0x1800037d1  mov     rax, [rax+10h]
0x1800037d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037da  jmp     short loc_1800037AA
```
