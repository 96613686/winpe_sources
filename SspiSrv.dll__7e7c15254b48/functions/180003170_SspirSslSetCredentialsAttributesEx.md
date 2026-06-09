# SspirSslSetCredentialsAttributesEx

- ea: `0x180003170`
- end: `0x180003201`
- name: `SspirSslSetCredentialsAttributesEx`
- size: `145`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int128 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180003170`
- `0x180003340`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirSslSetCredentialsAttributesEx(__int64 a1, _QWORD *a2, __int128 *a3, __int64 a4, __int64 a5)
{
  __int64 (__fastcall *v5)(__int64, _QWORD *, __int128 *); // rax
  __int128 v6; // xmm0
  _QWORD v8[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v9; // [rsp+40h] [rbp-28h] BYREF

  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(gLsapSspiExtension + 88);
  if ( !v5 )
    return 3221225659LL;
  if ( !a2 || !a3 || !a5 )
    return 3221225485LL;
  v6 = *a3;
  v8[0] = *a2;
  v8[1] = a2[1];
  v9 = v6;
  return v5(a1, v8, &v9);
}

```

## disassembly

```asm
0x180003170  sub     rsp, 68h
0x180003174  mov     rax, cs:__security_cookie
0x18000317b  xor     rax, rsp
0x18000317e  mov     [rsp+68h+var_18], rax
0x180003183  mov     rax, cs:gLsapSspiExtension
0x18000318a  mov     r10, rdx
0x18000318d  mov     r11, [rsp+68h+arg_20]
0x180003195  test    rax, rax
0x180003198  jz      short loc_1800031EA
0x18000319a  mov     rax, [rax+58h]
0x18000319e  test    rax, rax
0x1800031a1  jz      short loc_1800031EA
0x1800031a3  test    rdx, rdx
0x1800031a6  jz      short loc_1800031E3
0x1800031a8  test    r8, r8
0x1800031ab  jz      short loc_1800031E3
0x1800031ad  test    r11, r11
0x1800031b0  jz      short loc_1800031E3
0x1800031b2  mov     rdx, [rdx]
0x1800031b5  movups  xmm0, xmmword ptr [r8]
0x1800031b9  mov     [rsp+68h+var_38], rdx
0x1800031be  lea     r8, [rsp+68h+var_28]
0x1800031c3  mov     rdx, [r10+8]
0x1800031c7  mov     [rsp+68h+var_30], rdx
0x1800031cc  lea     rdx, [rsp+68h+var_38]
0x1800031d1  movdqu  [rsp+68h+var_28], xmm0
0x1800031d7  mov     [rsp+68h+var_48], r11
0x1800031dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e1  jmp     short loc_1800031EF
0x1800031e3  mov     eax, 0C000000Dh
0x1800031e8  jmp     short loc_1800031EF
0x1800031ea  mov     eax, 0C00000BBh
0x1800031ef  mov     rcx, [rsp+68h+var_18]
0x1800031f4  xor     rcx, rsp; StackCookie
0x1800031f7  call    __security_check_cookie
0x1800031fc  add     rsp, 68h
0x180003200  retn
```
