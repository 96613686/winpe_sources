# SspirNegQueryContextAttributes

- ea: `0x180002d60`
- end: `0x180002e5f`
- name: `SspirNegQueryContextAttributes`
- size: `255`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int128 *, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800013d0`
- `0x180001510`
- `0x180002d60`
- `0x180003340`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirNegQueryContextAttributes(__int64 a1, _QWORD *a2, __int128 *a3, unsigned int a4, _QWORD *a5)
{
  void *v7; // rax
  void *v8; // rbx
  int v10; // edi
  _QWORD v11[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-38h] BYREF

  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 80) )
    return 3221225659LL;
  if ( !a2 )
    return 3221225485LL;
  if ( !a3 )
    return 3221225485LL;
  if ( !a5 )
    return 3221225485LL;
  v11[0] = *a2;
  v11[1] = a2[1];
  v12 = *a3;
  if ( a4 )
  {
    if ( a4 != 12 )
      return 3221225485LL;
  }
  v7 = MIDL_user_allocate(0x10u);
  v8 = v7;
  if ( !v7 )
    return 3221225626LL;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, _QWORD, void *))(gLsapSspiExtension + 80))(
          a1,
          v11,
          &v12,
          a4,
          v7);
  if ( v10 < 0 )
    MIDL_user_free(v8);
  else
    *a5 = v8;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180002d60  mov     [rsp+arg_10], rbx
0x180002d65  push    rbp
0x180002d66  push    rsi
0x180002d67  push    rdi
0x180002d68  sub     rsp, 60h
0x180002d6c  mov     rax, cs:__security_cookie
0x180002d73  xor     rax, rsp
0x180002d76  mov     [rsp+78h+var_28], rax
0x180002d7b  mov     rax, cs:gLsapSspiExtension
0x180002d82  mov     edi, r9d
0x180002d85  mov     rsi, [rsp+78h+arg_20]
0x180002d8d  mov     rbp, rcx
0x180002d90  test    rax, rax
0x180002d93  jz      loc_180002E3D
0x180002d99  cmp     qword ptr [rax+50h], 0
0x180002d9e  jz      loc_180002E3D
0x180002da4  test    rdx, rdx
0x180002da7  jz      loc_180002E36
0x180002dad  test    r8, r8
0x180002db0  jz      loc_180002E36
0x180002db6  test    rsi, rsi
0x180002db9  jz      short loc_180002E36
0x180002dbb  mov     rax, [rdx]
0x180002dbe  mov     [rsp+78h+var_48], rax
0x180002dc3  mov     rax, [rdx+8]
0x180002dc7  mov     [rsp+78h+var_40], rax
0x180002dcc  movups  xmm0, xmmword ptr [r8]
0x180002dd0  movdqu  [rsp+78h+var_38], xmm0
0x180002dd6  test    r9d, r9d
0x180002dd9  jz      short loc_180002DE1
0x180002ddb  cmp     r9d, 0Ch
0x180002ddf  jnz     short loc_180002E36
0x180002de1  mov     ecx, 10h; size
0x180002de6  call    MIDL_user_allocate
0x180002deb  mov     rbx, rax
0x180002dee  test    rax, rax
0x180002df1  jnz     short loc_180002DFA
0x180002df3  mov     eax, 0C000009Ah
0x180002df8  jmp     short loc_180002E42
0x180002dfa  mov     rax, cs:gLsapSspiExtension
0x180002e01  lea     r8, [rsp+78h+var_38]
0x180002e06  mov     r9d, edi
0x180002e09  mov     [rsp+78h+var_58], rbx
0x180002e0e  lea     rdx, [rsp+78h+var_48]
0x180002e13  mov     rcx, rbp
0x180002e16  mov     rax, [rax+50h]
0x180002e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1f  mov     edi, eax
0x180002e21  test    eax, eax
0x180002e23  js      short loc_180002E2A
0x180002e25  mov     [rsi], rbx
0x180002e28  jmp     short loc_180002E32
0x180002e2a  mov     rcx, rbx; void *
0x180002e2d  call    MIDL_user_free
0x180002e32  mov     eax, edi
0x180002e34  jmp     short loc_180002E42
0x180002e36  mov     eax, 0C000000Dh
0x180002e3b  jmp     short loc_180002E42
0x180002e3d  mov     eax, 0C00000BBh
0x180002e42  mov     rcx, [rsp+78h+var_28]
0x180002e47  xor     rcx, rsp; StackCookie
0x180002e4a  call    __security_check_cookie
0x180002e4f  mov     rbx, [rsp+78h+arg_10]
0x180002e57  add     rsp, 60h
0x180002e5b  pop     rdi
0x180002e5c  pop     rsi
0x180002e5d  pop     rbp
0x180002e5e  retn
```
