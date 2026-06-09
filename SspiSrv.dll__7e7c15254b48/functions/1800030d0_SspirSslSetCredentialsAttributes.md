# SspirSslSetCredentialsAttributes

- ea: `0x1800030d0`
- end: `0x18000315d`
- name: `SspirSslSetCredentialsAttributes`
- size: `141`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int128 *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800030d0`
- `0x180003340`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirSslSetCredentialsAttributes(__int64 a1, _QWORD *a2, __int128 *a3, __int64 a4)
{
  __int64 (__fastcall *v4)(__int64, _QWORD *, __int128 *, __int64, __int64); // rax
  __int128 v5; // xmm0
  _QWORD v7[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+40h] [rbp-28h] BYREF

  if ( !gLsapSspiExtension )
    return 3221225659LL;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, __int64, __int64))(gLsapSspiExtension + 88);
  if ( !v4 )
    return 3221225659LL;
  if ( !a2 || !a3 || !a4 )
    return 3221225485LL;
  v5 = *a3;
  v7[0] = *a2;
  v7[1] = a2[1];
  v8 = v5;
  return v4(a1, v7, &v8, 96, a4);
}

```

## disassembly

```asm
0x1800030d0  mov     r11, rsp
0x1800030d3  sub     rsp, 68h
0x1800030d7  mov     rax, cs:__security_cookie
0x1800030de  xor     rax, rsp
0x1800030e1  mov     [rsp+68h+var_18], rax
0x1800030e6  mov     rax, cs:gLsapSspiExtension
0x1800030ed  mov     r10, rdx
0x1800030f0  test    rax, rax
0x1800030f3  jz      short loc_180003146
0x1800030f5  mov     rax, [rax+58h]
0x1800030f9  test    rax, rax
0x1800030fc  jz      short loc_180003146
0x1800030fe  test    rdx, rdx
0x180003101  jz      short loc_18000313F
0x180003103  test    r8, r8
0x180003106  jz      short loc_18000313F
0x180003108  test    r9, r9
0x18000310b  jz      short loc_18000313F
0x18000310d  mov     rdx, [rdx]
0x180003110  movups  xmm0, xmmword ptr [r8]
0x180003114  mov     [r11-38h], rdx
0x180003118  lea     r8, [r11-28h]
0x18000311c  mov     rdx, [r10+8]
0x180003120  mov     [r11-30h], rdx
0x180003124  lea     rdx, [r11-38h]
0x180003128  mov     [r11-48h], r9
0x18000312c  mov     r9d, 60h ; '`'
0x180003132  movdqu  [rsp+68h+var_28], xmm0
0x180003138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313d  jmp     short loc_18000314B
0x18000313f  mov     eax, 0C000000Dh
0x180003144  jmp     short loc_18000314B
0x180003146  mov     eax, 0C00000BBh
0x18000314b  mov     rcx, [rsp+68h+var_18]
0x180003150  xor     rcx, rsp; StackCookie
0x180003153  call    __security_check_cookie
0x180003158  add     rsp, 68h
0x18000315c  retn
```
