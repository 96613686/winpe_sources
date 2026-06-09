# winWrite

- ea: `0x180048c00`
- end: `0x180048dab`
- name: `winWrite`
- size: `427`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800257e0`
- `0x180048c00`
- `0x18004909c`
- `0x1800b0010`

## string_xrefs

- `0x180048d06`: `winWrite2`
- `0x180048d5c`: `winWrite1`

## pseudocode

```c
__int64 __fastcall winWrite(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  int v4; // ebp
  __int64 v5; // rdi
  __int64 v9; // r15
  int v10; // eax
  DWORD v12; // eax
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  _QWORD v15[2]; // [rsp+30h] [rbp-58h] BYREF
  int v16; // [rsp+40h] [rbp-48h]
  int v17; // [rsp+44h] [rbp-44h]
  __int64 v18; // [rsp+48h] [rbp-40h]
  unsigned int v19; // [rsp+A0h] [rbp+18h] BYREF

  v16 = a4;
  v4 = 0;
  v19 = 0;
  v15[0] = 0;
  v5 = a4;
  v15[1] = 0;
  v18 = 0;
  v9 = 0x804000018000001LL;
  v10 = HIDWORD(a4) & 0x7FFFFFFF;
  while ( 2 )
  {
    v17 = v10;
    while ( 1 )
    {
      if ( a3 <= 0 )
      {
        if ( v4 )
          sqlite3_log(
            27,
            "delayed %dms for lock/sharing conflict at line %d",
            v4 * dword_1800D0C70 * (v4 + 1) / 2,
            49645);
        return 0;
      }
      if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, unsigned int *, _QWORD *))off_1800CE3C0)(
                           *(_QWORD *)(a1 + 16),
                           a2,
                           (unsigned int)a3,
                           &v19,
                           v15) )
        break;
      v12 = off_1800CE078();
      v13 = v12;
      if ( v4 >= dword_1800D0858 )
        goto LABEL_16;
      v14 = v12 - 5;
      if ( ((unsigned int)v14 > 0x3B || !_bittest64(&v9, v14)) && (_DWORD)v13 != 121 && (_DWORD)v13 != 1231 )
        goto LABEL_16;
      ++v4;
      ((void (__fastcall *)(_QWORD, __int64))off_1800CE330)((unsigned int)(dword_1800D0C70 * v4), v13);
    }
    if ( v19 && v19 <= a3 )
    {
      v5 += v19;
      a2 += v19;
      v16 = v5;
      v10 = HIDWORD(v5) & 0x7FFFFFFF;
      a3 -= v19;
      continue;
    }
    break;
  }
  LODWORD(v13) = off_1800CE078();
LABEL_16:
  *(_DWORD *)(a1 + 32) = v13;
  if ( (_DWORD)v13 == 39 || (_DWORD)v13 == 112 )
    return winLogErrorAtLine(13, v13, (unsigned int)"winWrite1", *(_QWORD *)(a1 + 48), 49638);
  else
    return winLogErrorAtLine(778, v13, (unsigned int)"winWrite2", *(_QWORD *)(a1 + 48), 49643);
}

```

## disassembly

```asm
0x180048c00  mov     r11, rsp
0x180048c03  push    rbx
0x180048c04  push    rbp
0x180048c05  push    rsi
0x180048c06  push    rdi
0x180048c07  push    r14
0x180048c09  push    r15
0x180048c0b  sub     rsp, 58h
0x180048c0f  xor     eax, eax
0x180048c11  mov     [r11-48h], r9d
0x180048c15  mov     ebp, eax
0x180048c17  mov     [r11+18h], eax
0x180048c1b  mov     [r11-58h], rax
0x180048c1f  mov     rdi, r9
0x180048c22  mov     [r11-50h], rax
0x180048c26  mov     ebx, r8d
0x180048c29  mov     [r11-40h], rax
0x180048c2d  mov     rsi, rdx
0x180048c30  mov     rax, r9
0x180048c33  mov     r14, rcx
0x180048c36  sar     rax, 20h
0x180048c3a  mov     r15, 804000018000001h
0x180048c44  btr     eax, 1Fh
0x180048c48  mov     [rsp+88h+var_44], eax
0x180048c4c  test    ebx, ebx
0x180048c4e  jg      short loc_180048C67
0x180048c50  test    ebp, ebp
0x180048c52  jnz     loc_180048D7A
0x180048c58  xor     eax, eax
0x180048c5a  add     rsp, 58h
0x180048c5e  pop     r15
0x180048c60  pop     r14
0x180048c62  pop     rdi
0x180048c63  pop     rsi
0x180048c64  pop     rbp
0x180048c65  pop     rbx
0x180048c66  retn
0x180048c67  mov     rcx, [r14+10h]
0x180048c6b  lea     rax, [rsp+88h+var_58]
0x180048c70  mov     [rsp+88h+var_68], rax
0x180048c75  lea     r9, [rsp+88h+arg_10]
0x180048c7d  mov     rax, cs:off_1800CE3C0
0x180048c84  mov     r8d, ebx
0x180048c87  mov     rdx, rsi
0x180048c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c8f  test    eax, eax
0x180048c91  jz      short loc_180048CC3
0x180048c93  mov     edx, [rsp+88h+arg_10]
0x180048c9a  test    edx, edx
0x180048c9c  jz      loc_180048D2C
0x180048ca2  cmp     edx, ebx
0x180048ca4  ja      loc_180048D2C
0x180048caa  add     rdi, rdx
0x180048cad  add     rsi, rdx
0x180048cb0  mov     rax, rdi
0x180048cb3  mov     [rsp+88h+var_48], edi
0x180048cb7  sar     rax, 20h
0x180048cbb  btr     eax, 1Fh
0x180048cbf  sub     ebx, edx
0x180048cc1  jmp     short loc_180048C48
0x180048cc3  mov     rax, cs:off_1800CE078
0x180048cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ccf  cmp     ebp, cs:dword_1800D0858
0x180048cd5  mov     edx, eax
0x180048cd7  jge     short loc_180048CF4
0x180048cd9  add     eax, 0FFFFFFFBh
0x180048cdc  cmp     eax, 3Bh ; ';'
0x180048cdf  ja      short loc_180048CE7
0x180048ce1  bt      r15, rax
0x180048ce5  jb      short loc_180048D3C
0x180048ce7  cmp     edx, 79h ; 'y'
0x180048cea  jz      short loc_180048D3C
0x180048cec  cmp     edx, 4CFh
0x180048cf2  jz      short loc_180048D3C
0x180048cf4  mov     [r14+20h], edx
0x180048cf8  cmp     edx, 27h ; '''
0x180048cfb  jz      short loc_180048D58
0x180048cfd  cmp     edx, 70h ; 'p'
0x180048d00  jz      short loc_180048D58
0x180048d02  mov     r9, [r14+30h]
0x180048d06  lea     r8, aWinwrite2; "winWrite2"
0x180048d0d  mov     ecx, 30Ah
0x180048d12  mov     dword ptr [rsp+88h+var_68], 0C1EBh
0x180048d1a  call    winLogErrorAtLine
0x180048d1f  add     rsp, 58h
0x180048d23  pop     r15
0x180048d25  pop     r14
0x180048d27  pop     rdi
0x180048d28  pop     rsi
0x180048d29  pop     rbp
0x180048d2a  pop     rbx
0x180048d2b  retn
0x180048d2c  mov     rax, cs:off_1800CE078
0x180048d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d38  mov     edx, eax
0x180048d3a  jmp     short loc_180048CF4
0x180048d3c  mov     rax, cs:off_1800CE330
0x180048d43  inc     ebp
0x180048d45  mov     ecx, ebp
0x180048d47  imul    ecx, cs:dword_1800D0C70
0x180048d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d53  jmp     loc_180048C4C
0x180048d58  mov     r9, [r14+30h]
0x180048d5c  lea     r8, aWinwrite1; "winWrite1"
0x180048d63  mov     ecx, 0Dh
0x180048d68  mov     dword ptr [rsp+88h+var_68], 0C1E6h
0x180048d70  call    winLogErrorAtLine
0x180048d75  jmp     loc_180048C5A
0x180048d7a  lea     eax, [rbp+1]
0x180048d7d  mov     r9d, 0C1EDh
0x180048d83  imul    eax, cs:dword_1800D0C70
0x180048d8a  mov     ecx, 1Bh
0x180048d8f  imul    eax, ebp
0x180048d92  cdq
0x180048d93  sub     eax, edx
0x180048d95  lea     rdx, aDelayedDmsForL; "delayed %dms for lock/sharing conflict "...
0x180048d9c  sar     eax, 1
0x180048d9e  mov     r8d, eax
0x180048da1  call    sqlite3_log
0x180048da6  jmp     loc_180048C58
```
