# SspirLookupAccountSid

- ea: `0x180001c80`
- end: `0x180001d6c`
- name: `SspirLookupAccountSid`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int128 *, void *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001c80`
- `0x180004010`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180001cf5`
- `ntdll!RtlValidSid` at `0x180001cf5`

## pseudocode

```c
__int64 __fastcall SspirLookupAccountSid(__int64 a1, __int128 *a2, void *a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int128 v11; // [rsp+40h] [rbp-28h] BYREF

  v11 = 0;
  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 104) )
    return 3221225659LL;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
    return 3221225485LL;
  if ( !RtlValidSid(a3) )
    return 3221225592LL;
  v11 = *a2;
  return (*(__int64 (__fastcall **)(__int64, __int128 *, void *, __int64, __int64, __int64))(gLsapSspiExtension + 104))(
           a1,
           &v11,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180001c80  mov     [rsp+arg_10], rbx
0x180001c85  push    rbp
0x180001c86  push    rsi
0x180001c87  push    rdi
0x180001c88  sub     rsp, 50h
0x180001c8c  mov     rax, cs:gLsapSspiExtension
0x180001c93  xorps   xmm0, xmm0
0x180001c96  mov     rdi, r9
0x180001c99  mov     rbx, r8
0x180001c9c  mov     rsi, rdx
0x180001c9f  mov     rbp, rcx
0x180001ca2  movups  [rsp+68h+var_28], xmm0
0x180001ca7  test    rax, rax
0x180001caa  jz      loc_180001D57
0x180001cb0  cmp     qword ptr [rax+68h], 0
0x180001cb5  jz      loc_180001D57
0x180001cbb  mov     [rsp+68h+arg_0], r14
0x180001cc0  mov     [rsp+68h+arg_8], r15
0x180001cc5  test    rdx, rdx
0x180001cc8  jz      loc_180001D50
0x180001cce  test    rbx, rbx
0x180001cd1  jz      short loc_180001D50
0x180001cd3  test    r9, r9
0x180001cd6  jz      short loc_180001D50
0x180001cd8  mov     r14, [rsp+68h+arg_20]
0x180001ce0  test    r14, r14
0x180001ce3  jz      short loc_180001D50
0x180001ce5  mov     r15, [rsp+68h+arg_28]
0x180001ced  test    r15, r15
0x180001cf0  jz      short loc_180001D50
0x180001cf2  mov     rcx, rbx; Sid
0x180001cf5  call    cs:__imp_RtlValidSid
0x180001cfb  test    al, al
0x180001cfd  jnz     short loc_180001D1E
0x180001cff  mov     eax, 0C0000078h
0x180001d04  mov     r14, [rsp+68h+arg_0]
0x180001d09  mov     r15, [rsp+68h+arg_8]
0x180001d0e  mov     rbx, [rsp+68h+arg_10]
0x180001d16  add     rsp, 50h
0x180001d1a  pop     rdi
0x180001d1b  pop     rsi
0x180001d1c  pop     rbp
0x180001d1d  retn
0x180001d1e  movups  xmm0, xmmword ptr [rsi]
0x180001d21  mov     rax, cs:gLsapSspiExtension
0x180001d28  lea     rdx, [rsp+68h+var_28]
0x180001d2d  mov     [rsp+68h+var_40], r15
0x180001d32  mov     r9, rdi
0x180001d35  movups  [rsp+68h+var_28], xmm0
0x180001d3a  mov     r8, rbx
0x180001d3d  mov     [rsp+68h+var_48], r14
0x180001d42  mov     rax, [rax+68h]
0x180001d46  mov     rcx, rbp
0x180001d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d4e  jmp     short loc_180001D04
0x180001d50  mov     eax, 0C000000Dh
0x180001d55  jmp     short loc_180001D04
0x180001d57  mov     rbx, [rsp+68h+arg_10]
0x180001d5f  mov     eax, 0C00000BBh
0x180001d64  add     rsp, 50h
0x180001d68  pop     rdi
0x180001d69  pop     rsi
0x180001d6a  pop     rbp
0x180001d6b  retn
```
