# autoVacuumCommit

- ea: `0x180073510`
- end: `0x1800736c6`
- name: `autoVacuumCommit`
- size: `438`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003fb60`
- `0x180040640`

## callees

- `0x18002619c`
- `0x180028090`
- `0x18003747c`
- `0x1800487ec`
- `0x18005f878`
- `0x180073510`
- `0x1800736cc`
- `0x18007e8f8`
- `0x180081064`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall autoVacuumCommit(__int64 a1)
{
  __int64 *v1; // rbx
  unsigned int v2; // esi
  __int64 v3; // r12
  __int64 v4; // rcx
  unsigned int v5; // edi
  __int64 *v6; // r10
  unsigned int v7; // r8d
  __int64 v8; // rcx
  unsigned __int32 v9; // r14d
  __int64 (__fastcall *v10)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int); // r11
  unsigned int i; // edx
  unsigned __int32 v12; // r15d
  unsigned int v14; // eax
  unsigned int v15; // ebp
  __int64 v16; // rdx
  unsigned int j; // eax

  v1 = *(__int64 **)(a1 + 8);
  v2 = 0;
  v3 = *v1;
  invalidateAllOverflowCache(v1);
  if ( *((_BYTE *)v1 + 34) )
    return v2;
  v5 = *((_DWORD *)v1 + 16);
  if ( (unsigned int)ptrmapPageno(v4, v5) == v5 || (v7 = *((_DWORD *)v1 + 13), v5 == dword_1800D085C / v7 + 1) )
  {
    v16 = 74977;
    return sqlite3ReportError(11, v16, "database corruption");
  }
  v8 = *v6;
  v9 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v1[3] + 80) + 36LL));
  v10 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(*v6 + 344);
  if ( v10 )
  {
    for ( i = 0; (signed int)i < *(_DWORD *)(v8 + 40); ++i )
    {
      if ( *(__int64 **)(32LL * i + *(_QWORD *)(v8 + 32) + 8) == v6 )
        break;
    }
    v12 = v10(*(_QWORD *)(v8 + 328), *(_QWORD *)(32LL * (int)i + *(_QWORD *)(v8 + 32)), v5, v9, v7);
    if ( v12 > v9 )
      v12 = v9;
    if ( !v12 )
      return 0;
  }
  else
  {
    v12 = v9;
  }
  v14 = finalDbSize(v1, v5, v12);
  v15 = v14;
  if ( v14 <= v5 )
  {
    if ( v14 >= v5 )
      goto LABEL_20;
    for ( j = saveAllCursors(v1, 0, 0); ; j = incrVacuumStep(v1, v15, v5--, v12 == v9) )
    {
      v2 = j;
LABEL_20:
      if ( v5 <= v15 || v2 )
        break;
    }
    if ( v2 != 101 && v2 )
      goto LABEL_28;
    if ( v9 )
    {
      v2 = sqlite3PagerWrite(*(_QWORD *)(v1[3] + 112));
      if ( v12 == v9 )
      {
        *(_DWORD *)(*(_QWORD *)(v1[3] + 80) + 32LL) = 0;
        *(_DWORD *)(*(_QWORD *)(v1[3] + 80) + 36LL) = 0;
      }
      *(_DWORD *)(*(_QWORD *)(v1[3] + 80) + 28LL) = _byteswap_ulong(v15);
      *((_BYTE *)v1 + 35) = 1;
      *((_DWORD *)v1 + 16) = v15;
    }
    if ( v2 )
LABEL_28:
      sqlite3PagerRollback(v3);
    return v2;
  }
  v16 = 75004;
  return sqlite3ReportError(11, v16, "database corruption");
}

```

## disassembly

```asm
0x180073510  push    rbx
0x180073512  push    rbp
0x180073513  push    rsi
0x180073514  push    rdi
0x180073515  push    r12
0x180073517  push    r14
0x180073519  push    r15
0x18007351b  sub     rsp, 30h
0x18007351f  mov     rbx, [rcx+8]
0x180073523  mov     r10, rcx
0x180073526  mov     rcx, rbx
0x180073529  xor     esi, esi
0x18007352b  mov     r12, [rbx]
0x18007352e  call    invalidateAllOverflowCache
0x180073533  cmp     [rbx+22h], sil
0x180073537  jnz     loc_18007369D
0x18007353d  mov     edi, [rbx+40h]
0x180073540  mov     edx, edi
0x180073542  call    ptrmapPageno
0x180073547  cmp     eax, edi
0x180073549  jz      loc_1800736AE
0x18007354f  mov     eax, cs:dword_1800D085C
0x180073555  xor     edx, edx
0x180073557  mov     r8d, [rbx+34h]
0x18007355b  div     r8d
0x18007355e  inc     eax
0x180073560  cmp     edi, eax
0x180073562  jz      loc_1800736AE
0x180073568  mov     rax, [rbx+18h]
0x18007356c  mov     rcx, [rax+50h]
0x180073570  mov     r14d, [rcx+24h]
0x180073574  mov     rcx, [r10]
0x180073577  bswap   r14d
0x18007357a  mov     r11, [rcx+158h]
0x180073581  test    r11, r11
0x180073584  jz      short loc_1800735E4
0x180073586  xor     edx, edx
0x180073588  cmp     [rcx+28h], edx
0x18007358b  jle     short loc_1800735A5
0x18007358d  mov     r9, [rcx+20h]
0x180073591  mov     eax, edx
0x180073593  shl     rax, 5
0x180073597  cmp     [rax+r9+8], r10
0x18007359c  jz      short loc_1800735A5
0x18007359e  inc     edx
0x1800735a0  cmp     edx, [rcx+28h]
0x1800735a3  jl      short loc_180073591
0x1800735a5  movsxd  r10, edx
0x1800735a8  mov     r9d, r14d
0x1800735ab  mov     rdx, [rcx+20h]
0x1800735af  mov     rax, r11
0x1800735b2  mov     rcx, [rcx+148h]
0x1800735b9  shl     r10, 5
0x1800735bd  mov     [rsp+68h+var_48], r8d
0x1800735c2  mov     r8d, edi
0x1800735c5  mov     rdx, [r10+rdx]
0x1800735c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735ce  cmp     eax, r14d
0x1800735d1  mov     r15d, eax
0x1800735d4  cmova   r15d, r14d
0x1800735d8  test    r15d, r15d
0x1800735db  jnz     short loc_1800735E7
0x1800735dd  xor     eax, eax
0x1800735df  jmp     loc_18007369F
0x1800735e4  mov     r15d, r14d
0x1800735e7  mov     r8d, r15d
0x1800735ea  mov     edx, edi
0x1800735ec  mov     rcx, rbx
0x1800735ef  call    finalDbSize
0x1800735f4  mov     ebp, eax
0x1800735f6  cmp     eax, edi
0x1800735f8  jbe     short loc_180073604
0x1800735fa  mov     edx, 124FCh
0x1800735ff  jmp     loc_1800736B3
0x180073604  jnb     short loc_180073634
0x180073606  xor     r8d, r8d
0x180073609  xor     edx, edx
0x18007360b  mov     rcx, rbx
0x18007360e  call    saveAllCursors
0x180073613  jmp     short loc_180073632
0x180073615  test    esi, esi
0x180073617  jnz     short loc_180073638
0x180073619  xor     r9d, r9d
0x18007361c  mov     r8d, edi
0x18007361f  cmp     r15d, r14d
0x180073622  mov     edx, ebp
0x180073624  mov     rcx, rbx
0x180073627  setz    r9b
0x18007362b  call    incrVacuumStep
0x180073630  dec     edi
0x180073632  mov     esi, eax
0x180073634  cmp     edi, ebp
0x180073636  ja      short loc_180073615
0x180073638  cmp     esi, 65h ; 'e'
0x18007363b  jz      short loc_180073641
0x18007363d  test    esi, esi
0x18007363f  jnz     short loc_180073695
0x180073641  test    r14d, r14d
0x180073644  jz      short loc_180073691
0x180073646  mov     rcx, [rbx+18h]
0x18007364a  mov     rcx, [rcx+70h]
0x18007364e  call    sqlite3PagerWrite
0x180073653  mov     esi, eax
0x180073655  cmp     r15d, r14d
0x180073658  jnz     short loc_180073678
0x18007365a  mov     rax, [rbx+18h]
0x18007365e  mov     rcx, [rax+50h]
0x180073662  mov     dword ptr [rcx+20h], 0
0x180073669  mov     rax, [rbx+18h]
0x18007366d  mov     rcx, [rax+50h]
0x180073671  mov     dword ptr [rcx+24h], 0
0x180073678  mov     rax, [rbx+18h]
0x18007367c  mov     r8d, ebp
0x18007367f  bswap   r8d
0x180073682  mov     rdx, [rax+50h]
0x180073686  mov     [rdx+1Ch], r8d
0x18007368a  mov     byte ptr [rbx+23h], 1
0x18007368e  mov     [rbx+40h], ebp
0x180073691  test    esi, esi
0x180073693  jz      short loc_18007369D
0x180073695  mov     rcx, r12
0x180073698  call    sqlite3PagerRollback
0x18007369d  mov     eax, esi
0x18007369f  add     rsp, 30h
0x1800736a3  pop     r15
0x1800736a5  pop     r14
0x1800736a7  pop     r12
0x1800736a9  pop     rdi
0x1800736aa  pop     rsi
0x1800736ab  pop     rbp
0x1800736ac  pop     rbx
0x1800736ad  retn
0x1800736ae  mov     edx, 124E1h
0x1800736b3  lea     r8, aDatabaseCorrup; "database corruption"
0x1800736ba  mov     ecx, 0Bh
0x1800736bf  call    sqlite3ReportError
0x1800736c4  jmp     short loc_18007369F
```
