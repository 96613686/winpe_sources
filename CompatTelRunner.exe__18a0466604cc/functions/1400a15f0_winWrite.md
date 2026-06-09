# winWrite

- ea: `0x1400a15f0`
- end: `0x1400a1721`
- name: `winWrite`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14009fa4c`
- `0x14009fb28`
- `0x1400a07a8`
- `0x1400a15f0`
- `0x1400a8010`

## string_xrefs

- `0x1400a1708`: `winWrite1`
- `0x1400a16f2`: `winWrite2`

## pseudocode

```c
__int64 __fastcall winWrite(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v4; // rdi
  int v5; // ebx
  DWORD v8; // eax
  _QWORD v10[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+40h] [rbp-10h]
  __int64 v12; // [rsp+48h] [rbp-8h]
  DWORD v13; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v14; // [rsp+88h] [rbp+38h] BYREF
  unsigned int v15; // [rsp+90h] [rbp+40h] BYREF

  v14 = 0;
  v4 = a4;
  v15 = 0;
  v13 = 0;
  v5 = a3;
  v10[0] = 0;
  v10[1] = 0;
  v12 = 0;
  v11 = a4 & 0x7FFFFFFFFFFFFFFFLL;
  if ( a3 <= 0 )
    goto LABEL_9;
  while ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, unsigned int *, _QWORD *))off_1400C5FB0)(
                           *(_QWORD *)(a1 + 16),
                           a2,
                           (unsigned int)v5,
                           &v15,
                           v10) )
  {
    if ( !(unsigned int)winRetryIoerr(&v14, &v13) )
    {
      v8 = v13;
      goto LABEL_11;
    }
LABEL_8:
    if ( v5 <= 0 )
      goto LABEL_9;
  }
  if ( v15 && v15 <= v5 )
  {
    v4 += v15;
    a2 += v15;
    v11 = v4 & 0x7FFFFFFFFFFFFFFFLL;
    v5 -= v15;
    goto LABEL_8;
  }
  v8 = off_1400C5C68();
LABEL_11:
  if ( !v5 )
  {
LABEL_9:
    winLogIoerr(v14, 48692);
    return 0;
  }
  *(_DWORD *)(a1 + 32) = v8;
  if ( v8 == 39 || v8 == 112 )
    return winLogErrorAtLine(13, v8, (unsigned int)"winWrite1", *(_QWORD *)(a1 + 48), 48685);
  else
    return winLogErrorAtLine(778, v8, (unsigned int)"winWrite2", *(_QWORD *)(a1 + 48), 48690);
}

```

## disassembly

```asm
0x1400a15f0  push    rbp
0x1400a15f2  push    rbx
0x1400a15f3  push    rsi
0x1400a15f4  push    rdi
0x1400a15f5  push    r14
0x1400a15f7  mov     rbp, rsp
0x1400a15fa  sub     rsp, 50h
0x1400a15fe  mov     rax, r9
0x1400a1601  mov     [rbp+arg_8], 0
0x1400a1608  sar     rax, 20h
0x1400a160c  mov     rdi, r9
0x1400a160f  btr     eax, 1Fh
0x1400a1613  mov     [rbp+arg_10], 0
0x1400a161a  mov     [rbp+arg_0], 0
0x1400a1621  mov     ebx, r8d
0x1400a1624  mov     [rbp+var_20], 0
0x1400a162c  mov     r14, rdx
0x1400a162f  mov     [rbp+var_18], 0
0x1400a1637  mov     rsi, rcx
0x1400a163a  mov     [rbp+var_8], 0
0x1400a1642  mov     dword ptr [rbp+var_10], r9d
0x1400a1646  mov     dword ptr [rbp+var_10+4], eax
0x1400a1649  test    r8d, r8d
0x1400a164c  jle     short loc_1400A16B3
0x1400a164e  mov     rcx, [rsi+10h]
0x1400a1652  lea     rax, [rbp+var_20]
0x1400a1656  mov     [rsp+50h+var_30], rax
0x1400a165b  lea     r9, [rbp+arg_10]
0x1400a165f  mov     rax, cs:off_1400C5FB0
0x1400a1666  mov     r8d, ebx
0x1400a1669  mov     rdx, r14
0x1400a166c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a1671  test    eax, eax
0x1400a1673  jnz     short loc_1400A168B
0x1400a1675  lea     rdx, [rbp+arg_0]
0x1400a1679  lea     rcx, [rbp+arg_8]
0x1400a167d  call    winRetryIoerr
0x1400a1682  test    eax, eax
0x1400a1684  jnz     short loc_1400A16AF
0x1400a1686  mov     eax, [rbp+arg_0]
0x1400a1689  jmp     short loc_1400A16D9
0x1400a168b  mov     edx, [rbp+arg_10]
0x1400a168e  test    edx, edx
0x1400a1690  jz      short loc_1400A16CD
0x1400a1692  cmp     edx, ebx
0x1400a1694  ja      short loc_1400A16CD
0x1400a1696  add     rdi, rdx
0x1400a1699  add     r14, rdx
0x1400a169c  mov     rax, rdi
0x1400a169f  mov     dword ptr [rbp+var_10], edi
0x1400a16a2  sar     rax, 20h
0x1400a16a6  btr     eax, 1Fh
0x1400a16aa  mov     dword ptr [rbp+var_10+4], eax
0x1400a16ad  sub     ebx, edx
0x1400a16af  test    ebx, ebx
0x1400a16b1  jg      short loc_1400A164E
0x1400a16b3  mov     ecx, [rbp+arg_8]
0x1400a16b6  mov     edx, 0BE34h
0x1400a16bb  call    winLogIoerr
0x1400a16c0  xor     eax, eax
0x1400a16c2  add     rsp, 50h
0x1400a16c6  pop     r14
0x1400a16c8  pop     rdi
0x1400a16c9  pop     rsi
0x1400a16ca  pop     rbx
0x1400a16cb  pop     rbp
0x1400a16cc  retn
0x1400a16cd  mov     rax, cs:off_1400C5C68
0x1400a16d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a16d9  test    ebx, ebx
0x1400a16db  jz      short loc_1400A16B3
0x1400a16dd  mov     [rsi+20h], eax
0x1400a16e0  cmp     eax, 27h ; '''
0x1400a16e3  jz      short loc_1400A1700
0x1400a16e5  cmp     eax, 70h ; 'p'
0x1400a16e8  jz      short loc_1400A1700
0x1400a16ea  mov     dword ptr [rsp+50h+var_30], 0BE32h
0x1400a16f2  lea     r8, aWinwrite2; "winWrite2"
0x1400a16f9  mov     ecx, 30Ah
0x1400a16fe  jmp     short loc_1400A1714
0x1400a1700  mov     dword ptr [rsp+50h+var_30], 0BE2Dh
0x1400a1708  lea     r8, aWinwrite1; "winWrite1"
0x1400a170f  mov     ecx, 0Dh
0x1400a1714  mov     r9, [rsi+30h]
0x1400a1718  mov     edx, eax
0x1400a171a  call    winLogErrorAtLine
0x1400a171f  jmp     short loc_1400A16C2
```
