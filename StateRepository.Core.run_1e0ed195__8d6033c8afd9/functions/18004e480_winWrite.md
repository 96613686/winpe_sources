# winWrite

- ea: `0x18004e480`
- end: `0x18004e621`
- name: `winWrite`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800061e4`
- `0x1800275f0`
- `0x18004e480`
- `0x18004e670`
- `0x18009a010`

## string_xrefs

- `0x18004e524`: `winWrite1`
- `0x18004e5dc`: `winWrite2`

## pseudocode

```c
__int64 __fastcall winWrite(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  int v4; // ebx
  __int64 v5; // rsi
  int v9; // eax
  __int64 v10; // rdx
  DWORD v12; // eax
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD v15[2]; // [rsp+30h] [rbp-38h] BYREF
  int v16; // [rsp+40h] [rbp-28h]
  int v17; // [rsp+44h] [rbp-24h]
  __int64 v18; // [rsp+48h] [rbp-20h]
  unsigned int v19; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  v16 = a4;
  v19 = 0;
  v5 = a4;
  v15[0] = 0;
  v15[1] = 0;
  v18 = 0;
  v9 = HIDWORD(a4) & 0x7FFFFFFF;
LABEL_2:
  v17 = v9;
  while ( a3 > 0 )
  {
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, unsigned int *, _QWORD *))off_1800B33C0)(
                         *(_QWORD *)(a1 + 16),
                         a2,
                         (unsigned int)a3,
                         &v19,
                         v15) )
    {
      if ( v19 && v19 <= a3 )
      {
        v5 += v19;
        a2 += v19;
        v16 = v5;
        v9 = HIDWORD(v5) & 0x7FFFFFFF;
        a3 -= v19;
        goto LABEL_2;
      }
      LODWORD(v10) = off_1800B3078();
LABEL_7:
      *(_DWORD *)(a1 + 32) = v10;
      if ( (_DWORD)v10 == 39 || (_DWORD)v10 == 112 )
        return winLogErrorAtLine(13, v10, (unsigned int)"winWrite1", *(_QWORD *)(a1 + 48), 49639);
      else
        return winLogErrorAtLine(778, v10, (unsigned int)"winWrite2", *(_QWORD *)(a1 + 48), 49644);
    }
    v12 = off_1800B3078();
    v10 = v12;
    if ( v4 >= dword_1800B5618 )
      goto LABEL_7;
    if ( v12 != 1231 )
    {
      v13 = v12 - 5;
      if ( (unsigned int)v13 > 0x3B || (v14 = 0x804000018000001LL, !_bittest64(&v14, v13)) )
      {
        if ( (_DWORD)v10 != 121 )
          goto LABEL_7;
      }
    }
    ++v4;
    sqlite3_win32_sleep((unsigned int)(dword_1800B5A30 * v4), v10);
  }
  if ( v4 )
    sqlite3_log(27, "delayed %dms for lock/sharing conflict at line %d", v4 * dword_1800B5A30 * (v4 + 1) / 2, 49646);
  return 0;
}

```

## disassembly

```asm
0x18004e480  mov     rax, rsp
0x18004e483  mov     [rax+8], rbx
0x18004e487  mov     [rax+10h], rbp
0x18004e48b  push    rsi
0x18004e48c  push    rdi
0x18004e48d  push    r14
0x18004e48f  sub     rsp, 50h
0x18004e493  xor     ebx, ebx
0x18004e495  mov     [rax-28h], r9d
0x18004e499  mov     [rax+18h], ebx
0x18004e49c  mov     rsi, r9
0x18004e49f  mov     [rax-38h], rbx
0x18004e4a3  mov     edi, r8d
0x18004e4a6  mov     [rax-30h], rbx
0x18004e4aa  mov     r14, rdx
0x18004e4ad  mov     [rax-20h], rbx
0x18004e4b1  mov     rbp, rcx
0x18004e4b4  mov     rax, r9
0x18004e4b7  sar     rax, 20h
0x18004e4bb  btr     eax, 1Fh
0x18004e4bf  mov     [rsp+68h+var_24], eax
0x18004e4c3  test    edi, edi
0x18004e4c5  jle     loc_18004E58D
0x18004e4cb  mov     rcx, [rbp+10h]
0x18004e4cf  lea     rax, [rsp+68h+var_38]
0x18004e4d4  mov     [rsp+68h+var_48], rax
0x18004e4d9  lea     r9, [rsp+68h+arg_10]
0x18004e4e1  mov     rax, cs:off_1800B33C0
0x18004e4e8  mov     r8d, edi
0x18004e4eb  mov     rdx, r14
0x18004e4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4f3  test    eax, eax
0x18004e4f5  jz      short loc_18004E53B
0x18004e4f7  mov     edx, [rsp+68h+arg_10]
0x18004e4fe  test    edx, edx
0x18004e500  jnz     short loc_18004E56D
0x18004e502  mov     rax, cs:off_1800B3078
0x18004e509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e50e  mov     edx, eax
0x18004e510  mov     [rbp+20h], edx
0x18004e513  cmp     edx, 27h ; '''
0x18004e516  jnz     loc_18004E5CB
0x18004e51c  mov     dword ptr [rsp+68h+var_48], 0C1E7h
0x18004e524  lea     r8, aWinwrite1; "winWrite1"
0x18004e52b  mov     ecx, 0Dh
0x18004e530  mov     r9, [rbp+30h]
0x18004e534  call    winLogErrorAtLine
0x18004e539  jmp     short loc_18004E593
0x18004e53b  mov     rax, cs:off_1800B3078
0x18004e542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e547  cmp     ebx, cs:dword_1800B5618
0x18004e54d  mov     edx, eax
0x18004e54f  jge     short loc_18004E510
0x18004e551  cmp     eax, 4CFh
0x18004e556  jnz     short loc_18004E5A6
0x18004e558  inc     ebx
0x18004e55a  mov     ecx, ebx
0x18004e55c  imul    ecx, cs:dword_1800B5A30
0x18004e563  call    sqlite3_win32_sleep
0x18004e568  jmp     loc_18004E4C3
0x18004e56d  cmp     edx, edi
0x18004e56f  ja      short loc_18004E502
0x18004e571  add     rsi, rdx
0x18004e574  add     r14, rdx
0x18004e577  mov     rax, rsi
0x18004e57a  mov     [rsp+68h+var_28], esi
0x18004e57e  sar     rax, 20h
0x18004e582  btr     eax, 1Fh
0x18004e586  sub     edi, edx
0x18004e588  jmp     loc_18004E4BF
0x18004e58d  test    ebx, ebx
0x18004e58f  jnz     short loc_18004E5ED
0x18004e591  xor     eax, eax
0x18004e593  mov     rbx, [rsp+68h+arg_0]
0x18004e598  mov     rbp, [rsp+68h+arg_8]
0x18004e59d  add     rsp, 50h
0x18004e5a1  pop     r14
0x18004e5a3  pop     rdi
0x18004e5a4  pop     rsi
0x18004e5a5  retn
0x18004e5a6  add     eax, 0FFFFFFFBh
0x18004e5a9  cmp     eax, 3Bh ; ';'
0x18004e5ac  jbe     short loc_18004E5B9
0x18004e5ae  cmp     edx, 79h ; 'y'
0x18004e5b1  jnz     loc_18004E510
0x18004e5b7  jmp     short loc_18004E558
0x18004e5b9  mov     rcx, 804000018000001h
0x18004e5c3  bt      rcx, rax
0x18004e5c7  jb      short loc_18004E558
0x18004e5c9  jmp     short loc_18004E5AE
0x18004e5cb  cmp     edx, 70h ; 'p'
0x18004e5ce  jz      loc_18004E51C
0x18004e5d4  mov     dword ptr [rsp+68h+var_48], 0C1ECh
0x18004e5dc  lea     r8, aWinwrite2; "winWrite2"
0x18004e5e3  mov     ecx, 30Ah
0x18004e5e8  jmp     loc_18004E530
0x18004e5ed  mov     ecx, 2
0x18004e5f2  lea     eax, [rbx+1]
0x18004e5f5  imul    eax, cs:dword_1800B5A30
0x18004e5fc  mov     r9d, 0C1EEh
0x18004e602  imul    eax, ebx
0x18004e605  cdq
0x18004e606  idiv    ecx
0x18004e608  lea     rdx, aDelayedDmsForL; "delayed %dms for lock/sharing conflict "...
0x18004e60f  mov     ecx, 1Bh
0x18004e614  mov     r8d, eax
0x18004e617  call    sqlite3_log
0x18004e61c  jmp     loc_18004E591
```
