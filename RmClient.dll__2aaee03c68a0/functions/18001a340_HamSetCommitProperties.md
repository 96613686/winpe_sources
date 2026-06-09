# HamSetCommitProperties

- ea: `0x18001a340`
- end: `0x18001a446`
- name: `HamSetCommitProperties`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010fb0`
- `0x18001a340`

## pseudocode

```c
__int64 __fastcall HamSetCommitProperties(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // r11
  unsigned __int64 v4; // r10
  _QWORD *v5; // r9
  __int64 v7; // r9
  unsigned __int64 v8; // r10
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a2 )
    return 3221225712LL;
  if ( !a3 )
    return 3221225713LL;
  if ( a2 > a3 )
    return 3221225520LL;
  if ( a2 == -1 )
  {
    a1[41] = -1;
    a1[42] = -1;
    a1[36] = 0;
  }
  else
  {
    if ( (int)RtlULongLongMult(a2, 0x5Au, &v10) < 0 )
      return 3221225712LL;
    *(_QWORD *)(v7 + 336) = v10 / 0x64;
    RtlULongLongMult(v8, 0x32u, &v10);
    v9 = v10 / 0x64;
    v5[41] = v10 / 0x64;
    v5[36] = v9;
  }
  v5[44] = v3;
  v5[43] = v4;
  *((_DWORD *)v5 + 74) |= 4u;
  v5[40] |= 0xFuLL;
  return 0;
}

```

## disassembly

```asm
0x18001a340  push    rbx
0x18001a342  sub     rsp, 20h
0x18001a346  mov     [rsp+28h+arg_8], 0
0x18001a34f  mov     r11, r8
0x18001a352  mov     r10, rdx
0x18001a355  mov     r9, rcx
0x18001a358  test    rdx, rdx
0x18001a35b  jnz     short loc_18001A367
0x18001a35d  mov     eax, 0C00000F0h
0x18001a362  jmp     loc_18001A440
0x18001a367  test    r11, r11
0x18001a36a  jnz     short loc_18001A376
0x18001a36c  mov     eax, 0C00000F1h
0x18001a371  jmp     loc_18001A440
0x18001a376  cmp     r10, r11
0x18001a379  jbe     short loc_18001A385
0x18001a37b  mov     eax, 0C0000030h
0x18001a380  jmp     loc_18001A440
0x18001a385  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a389  cmp     r10, rax
0x18001a38c  jnz     short loc_18001A3A9
0x18001a38e  mov     [rcx+148h], rax
0x18001a395  mov     [rcx+150h], rax
0x18001a39c  mov     qword ptr [rcx+120h], 0
0x18001a3a7  jmp     short loc_18001A420
0x18001a3a9  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x18001a3ae  mov     edx, 5Ah ; 'Z'; unsigned __int64
0x18001a3b3  mov     rcx, r10; unsigned __int64
0x18001a3b6  call    ?RtlULongLongMult@@YAJ_K0PEA_K@Z; RtlULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001a3bb  test    eax, eax
0x18001a3bd  js      short loc_18001A35D
0x18001a3bf  mov     rcx, [rsp+28h+arg_8]
0x18001a3c4  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x18001a3c9  mov     rbx, 47AE147AE147AE15h
0x18001a3d3  mov     rax, rbx
0x18001a3d6  mul     rcx
0x18001a3d9  sub     rcx, rdx
0x18001a3dc  shr     rcx, 1
0x18001a3df  add     rcx, rdx
0x18001a3e2  mov     edx, 32h ; '2'; unsigned __int64
0x18001a3e7  shr     rcx, 6
0x18001a3eb  mov     [r9+150h], rcx
0x18001a3f2  mov     rcx, r10; unsigned __int64
0x18001a3f5  call    ?RtlULongLongMult@@YAJ_K0PEA_K@Z; RtlULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001a3fa  mov     r8, [rsp+28h+arg_8]
0x18001a3ff  mov     rax, rbx
0x18001a402  mul     r8
0x18001a405  sub     r8, rdx
0x18001a408  shr     r8, 1
0x18001a40b  add     r8, rdx
0x18001a40e  shr     r8, 6
0x18001a412  mov     [r9+148h], r8
0x18001a419  mov     [r9+120h], r8
0x18001a420  mov     [r9+160h], r11
0x18001a427  mov     [r9+158h], r10
0x18001a42e  or      dword ptr [r9+128h], 4
0x18001a436  or      qword ptr [r9+140h], 0Fh
0x18001a43e  xor     eax, eax
0x18001a440  add     rsp, 20h
0x18001a444  pop     rbx
0x18001a445  retn
```
