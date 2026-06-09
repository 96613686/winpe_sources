# winRead

- ea: `0x1800a3df0`
- end: `0x1800a3f42`
- name: `winRead`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800293d4`
- `0x180029cdc`
- `0x1800388f0`
- `0x180045374`
- `0x1800a3df0`
- `0x1800a6d08`
- `0x1800a8010`

## string_xrefs

- `0x1800a3ee8`: `winRead`

## pseudocode

```c
__int64 __fastcall winRead(__int64 a1, char *a2, int a3, __int64 a4)
{
  __int64 v4; // rsi
  unsigned int v6; // r14d
  const void *v8; // rdx
  int v10; // edi
  int v11; // edx
  __int64 v12; // r9
  unsigned int v13; // [rsp+30h] [rbp-30h] BYREF
  __int128 v14; // [rsp+38h] [rbp-28h] BYREF
  __int128 v15; // [rsp+48h] [rbp-18h]
  int v16; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v17; // [rsp+A8h] [rbp+48h] BYREF

  v4 = a4;
  v6 = a3;
  v13 = 0;
  v14 = 0;
  v17 = 0;
  v15 = 0;
  if ( a4 < *(_QWORD *)(a1 + 80) )
  {
    v8 = (const void *)(a4 + *(_QWORD *)(a1 + 72));
    if ( a3 + a4 <= *(_QWORD *)(a1 + 80) )
    {
      memcpy_0(a2, v8, a3);
      return 0;
    }
    v10 = *(_DWORD *)(a1 + 80) - a4;
    memcpy_0(a2, v8, v10);
    a2 += v10;
    v6 -= v10;
    v4 += v10;
  }
  *(_QWORD *)&v15 = v4 & 0x7FFFFFFFFFFFFFFFLL;
  while ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, char *, _QWORD, unsigned int *, __int128 *))off_1800C4338)(
                           *(_QWORD *)(a1 + 16),
                           a2,
                           v6,
                           &v13,
                           &v14)
       && off_1800C40C8() != 38 )
  {
    v16 = 0;
    if ( !(unsigned int)winRetryIoerr(&v17, &v16) )
    {
      v11 = v16;
      v12 = *(_QWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 32) = v16;
      return winLogErrorAtLine(266, v11, (unsigned int)"winRead", v12, 49431);
    }
  }
  winLogIoerr(v17, 49433);
  if ( v13 >= v6 )
    return 0;
  memset_0(&a2[v13], 0, v6 - v13);
  return 522;
}

```

## disassembly

```asm
0x1800a3df0  mov     [rsp-28h+arg_8], rbx
0x1800a3df5  mov     [rsp-28h+arg_10], rsi
0x1800a3dfa  push    rbp
0x1800a3dfb  push    rdi
0x1800a3dfc  push    r12
0x1800a3dfe  push    r14
0x1800a3e00  push    r15
0x1800a3e02  mov     rbp, rsp
0x1800a3e05  sub     rsp, 60h
0x1800a3e09  xorps   xmm0, xmm0
0x1800a3e0c  mov     rsi, r9
0x1800a3e0f  mov     r12, rdx
0x1800a3e12  movsxd  r14, r8d
0x1800a3e15  mov     r15, rcx
0x1800a3e18  mov     [rbp+var_30], 0
0x1800a3e1f  movups  [rbp+var_28], xmm0
0x1800a3e23  mov     [rbp+arg_18], 0
0x1800a3e2a  movups  [rbp+var_18], xmm0
0x1800a3e2e  cmp     r9, [rcx+50h]
0x1800a3e32  jge     short loc_1800A3E87
0x1800a3e34  mov     rdx, [rcx+48h]
0x1800a3e38  lea     rax, [r14+r9]
0x1800a3e3c  add     rdx, r9; Src
0x1800a3e3f  mov     r8, r14; Size
0x1800a3e42  cmp     rax, [rcx+50h]
0x1800a3e46  jg      short loc_1800A3E6B
0x1800a3e48  mov     rcx, r12; void *
0x1800a3e4b  call    memcpy_0
0x1800a3e50  xor     eax, eax
0x1800a3e52  lea     r11, [rsp+60h+var_s0]
0x1800a3e57  mov     rbx, [r11+38h]
0x1800a3e5b  mov     rsi, [r11+40h]
0x1800a3e5f  mov     rsp, r11
0x1800a3e62  pop     r15
0x1800a3e64  pop     r14
0x1800a3e66  pop     r12
0x1800a3e68  pop     rdi
0x1800a3e69  pop     rbp
0x1800a3e6a  retn
0x1800a3e6b  mov     edi, [rcx+50h]
0x1800a3e6e  mov     rcx, r12; void *
0x1800a3e71  sub     edi, esi
0x1800a3e73  movsxd  rbx, edi
0x1800a3e76  mov     r8, rbx; Size
0x1800a3e79  call    memcpy_0
0x1800a3e7e  add     r12, rbx
0x1800a3e81  sub     r14d, edi
0x1800a3e84  add     rsi, rbx
0x1800a3e87  mov     dword ptr [rbp+var_18], esi
0x1800a3e8a  sar     rsi, 20h
0x1800a3e8e  btr     esi, 1Fh
0x1800a3e92  mov     dword ptr [rbp+var_18+4], esi
0x1800a3e95  mov     rcx, [r15+10h]
0x1800a3e99  lea     rax, [rbp+var_28]
0x1800a3e9d  mov     [rsp+60h+var_40], rax
0x1800a3ea2  lea     r9, [rbp+var_30]
0x1800a3ea6  mov     rax, cs:off_1800C4338
0x1800a3ead  mov     r8d, r14d
0x1800a3eb0  mov     rdx, r12
0x1800a3eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3eb8  test    eax, eax
0x1800a3eba  jnz     short loc_1800A3F0E
0x1800a3ebc  mov     rax, cs:off_1800C40C8
0x1800a3ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ec8  cmp     eax, 26h ; '&'
0x1800a3ecb  jz      short loc_1800A3F0E
0x1800a3ecd  lea     rdx, [rbp+arg_0]
0x1800a3ed1  mov     [rbp+arg_0], 0
0x1800a3ed8  lea     rcx, [rbp+arg_18]
0x1800a3edc  call    winRetryIoerr
0x1800a3ee1  test    eax, eax
0x1800a3ee3  jnz     short loc_1800A3E95
0x1800a3ee5  mov     edx, [rbp+arg_0]
0x1800a3ee8  lea     r8, aWinread; "winRead"
0x1800a3eef  mov     r9, [r15+30h]
0x1800a3ef3  mov     ecx, 10Ah
0x1800a3ef8  mov     [r15+20h], edx
0x1800a3efc  mov     dword ptr [rsp+60h+var_40], 0C117h
0x1800a3f04  call    winLogErrorAtLine
0x1800a3f09  jmp     loc_1800A3E52
0x1800a3f0e  mov     ecx, [rbp+arg_18]
0x1800a3f11  mov     edx, 0C119h
0x1800a3f16  call    winLogIoerr
0x1800a3f1b  mov     eax, [rbp+var_30]
0x1800a3f1e  cmp     eax, r14d
0x1800a3f21  jnb     loc_1800A3E50
0x1800a3f27  sub     r14d, eax
0x1800a3f2a  lea     rcx, [r12+rax]; void *
0x1800a3f2e  mov     r8d, r14d; Size
0x1800a3f31  xor     edx, edx; Val
0x1800a3f33  call    memset_0
0x1800a3f38  mov     eax, 20Ah
0x1800a3f3d  jmp     loc_1800A3E52
```
