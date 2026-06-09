# sqlite3PagerSharedLock

- ea: `0x180007154`
- end: `0x1800073e3`
- name: `sqlite3PagerSharedLock`
- size: `655`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: ``

## callers

- `0x180006e2c`
- `0x180085ea4`

## callees

- `0x180007154`
- `0x1800076b4`
- `0x180007750`
- `0x18000793c`
- `0x180008770`
- `0x18000b0ac`
- `0x1800222e8`
- `0x180024978`
- `0x180049508`
- `0x18004a48c`
- `0x18004d658`
- `0x18004d6b0`
- `0x180054220`
- `0x1800560d4`
- `0x180060134`
- `0x180067c8c`
- `0x180068880`
- `0x18007ab60`
- `0x18007ae78`
- `0x18009a010`

## string_xrefs

- `0x1800072d7`: `cannot open file`

## pseudocode

```c
__int64 __fastcall sqlite3PagerSharedLock(__int64 a1)
{
  unsigned int Transaction; // edi
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rax
  int v10; // [rsp+30h] [rbp-20h] BYREF
  int v11; // [rsp+34h] [rbp-1Ch] BYREF
  __int128 v12; // [rsp+38h] [rbp-18h] BYREF

  Transaction = 0;
  if ( *(_QWORD *)(a1 + 296) || *(_BYTE *)(a1 + 21) )
    goto LABEL_2;
  v10 = 1;
  Transaction = pager_wait_on_lock(a1, 1);
  if ( Transaction )
    goto LABEL_10;
  if ( *(_BYTE *)(a1 + 22) > 1u )
    goto LABEL_48;
  Transaction = hasHotJournal(a1, &v10);
  if ( Transaction )
    goto LABEL_10;
  if ( v10 )
  {
LABEL_48:
    if ( *(_BYTE *)(a1 + 18) )
    {
      Transaction = 776;
      goto LABEL_10;
    }
    Transaction = pagerLockDb(a1, 4);
    if ( Transaction )
      goto LABEL_10;
    if ( !**(_QWORD **)(a1 + 80) && *(_BYTE *)(a1 + 9) != 2 )
    {
      v4 = *(_QWORD *)a1;
      v5 = *(_QWORD *)(a1 + 224);
      v10 = 0;
      Transaction = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(v4 + 56))(v4, v5, 0, &v10);
      if ( !Transaction )
      {
        if ( v10 )
        {
          v6 = *(_QWORD *)(a1 + 80);
          v7 = *(_QWORD *)(a1 + 224);
          v11 = 0;
          Transaction = sqlite3OsOpen(v4, v7, v6, 2050, (__int64)&v11);
          if ( !Transaction && (v11 & 1) != 0 )
          {
            Transaction = sqlite3ReportError(14, 62526, "cannot open file");
            sqlite3OsClose(*(_QWORD *)(a1 + 80));
          }
        }
      }
    }
    if ( **(_QWORD **)(a1 + 80) )
    {
      Transaction = pagerSyncHotJournal(a1);
      if ( Transaction )
        goto LABEL_35;
      Transaction = pager_playback(a1, *(_BYTE *)(a1 + 16) == 0);
      *(_BYTE *)(a1 + 21) = 0;
    }
    else if ( !*(_BYTE *)(a1 + 8) )
    {
      pagerUnlockDb(a1, 1);
    }
    if ( !Transaction )
      goto LABEL_17;
LABEL_35:
    pager_error(a1, Transaction);
    goto LABEL_10;
  }
LABEL_17:
  if ( !*(_BYTE *)(a1 + 16) && *(_BYTE *)(a1 + 28) )
  {
    v8 = sqlite3OsRead(*(_QWORD *)(a1 + 72), &v12, 16);
    Transaction = v8;
    if ( v8 )
    {
      if ( v8 != 522 )
        goto LABEL_10;
      v12 = 0;
    }
    v9 = *(_QWORD *)(a1 + 136) - v12;
    if ( !v9 )
      v9 = *(_QWORD *)(a1 + 144) - *((_QWORD *)&v12 + 1);
    if ( v9 )
    {
      pager_reset(a1);
      if ( *(_BYTE *)(a1 + 27) )
        sqlite3OsUnfetch(*(_QWORD *)(a1 + 72), 0, 0);
    }
  }
  Transaction = (unsigned int)pagerOpenWalIfPresent((_QWORD *)a1);
LABEL_2:
  if ( *(_QWORD *)(a1 + 296) )
    Transaction = pagerBeginReadTransaction(a1);
  if ( !*(_BYTE *)(a1 + 16) && !*(_BYTE *)(a1 + 21) )
  {
    if ( Transaction )
      goto LABEL_10;
    Transaction = pagerPagecount(a1, a1 + 32);
  }
  if ( Transaction )
  {
LABEL_10:
    pager_unlock(a1);
    return Transaction;
  }
  *(_BYTE *)(a1 + 21) = 1;
  *(_BYTE *)(a1 + 28) = 1;
  return Transaction;
}

```

## disassembly

```asm
0x180007154  mov     [rsp-18h+arg_8], rbx
0x180007159  mov     [rsp-18h+arg_10], rsi
0x18000715e  push    rbp
0x18000715f  push    rdi
0x180007160  push    r14
0x180007162  mov     rbp, rsp
0x180007165  sub     rsp, 50h
0x180007169  mov     rax, cs:__security_cookie
0x180007170  xor     rax, rsp
0x180007173  mov     [rbp+var_8], rax
0x180007177  xor     r14d, r14d
0x18000717a  mov     rbx, rcx
0x18000717d  mov     edi, r14d
0x180007180  cmp     [rcx+128h], r14
0x180007187  jz      short loc_1800071EB
0x180007189  cmp     [rbx+128h], r14
0x180007190  jnz     short loc_1800071DF
0x180007192  cmp     [rbx+10h], r14b
0x180007196  jz      short loc_1800071C7
0x180007198  test    edi, edi
0x18000719a  jnz     short loc_1800071D5
0x18000719c  mov     byte ptr [rbx+15h], 1
0x1800071a0  mov     byte ptr [rbx+1Ch], 1
0x1800071a4  mov     eax, edi
0x1800071a6  mov     rcx, [rbp+var_8]
0x1800071aa  xor     rcx, rsp; StackCookie
0x1800071ad  call    __security_check_cookie
0x1800071b2  lea     r11, [rsp+50h+var_s0]
0x1800071b7  mov     rbx, [r11+28h]
0x1800071bb  mov     rsi, [r11+30h]
0x1800071bf  mov     rsp, r11
0x1800071c2  pop     r14
0x1800071c4  pop     rdi
0x1800071c5  pop     rbp
0x1800071c6  retn
0x1800071c7  cmp     [rbx+15h], r14b
0x1800071cb  jnz     short loc_180007198
0x1800071cd  test    edi, edi
0x1800071cf  jz      loc_1800073D0
0x1800071d5  mov     rcx, rbx
0x1800071d8  call    pager_unlock
0x1800071dd  jmp     short loc_1800071A4
0x1800071df  mov     rcx, rbx
0x1800071e2  call    pagerBeginReadTransaction
0x1800071e7  mov     edi, eax
0x1800071e9  jmp     short loc_180007192
0x1800071eb  cmp     [rcx+15h], r14b
0x1800071ef  jnz     short loc_180007189
0x1800071f1  mov     edx, 1
0x1800071f6  mov     [rbp+var_20], 1
0x1800071fd  call    pager_wait_on_lock
0x180007202  mov     edi, eax
0x180007204  test    eax, eax
0x180007206  jnz     short loc_1800071D5
0x180007208  cmp     byte ptr [rbx+16h], 1
0x18000720c  jbe     short loc_18000723A
0x18000720e  cmp     [rbx+12h], r14b
0x180007212  jz      short loc_18000724E
0x180007214  mov     edi, 308h
0x180007219  jmp     short loc_1800071D5
0x18000721b  cmp     [rbp+var_20], r14d
0x18000721f  jnz     short loc_18000720E
0x180007221  cmp     [rbx+10h], r14b
0x180007225  jz      loc_180007351
0x18000722b  mov     rcx, rbx
0x18000722e  call    pagerOpenWalIfPresent
0x180007233  mov     edi, eax
0x180007235  jmp     loc_180007189
0x18000723a  lea     rdx, [rbp+var_20]
0x18000723e  mov     rcx, rbx
0x180007241  call    hasHotJournal
0x180007246  mov     edi, eax
0x180007248  test    eax, eax
0x18000724a  jnz     short loc_1800071D5
0x18000724c  jmp     short loc_18000721B
0x18000724e  mov     edx, 4
0x180007253  mov     rcx, rbx
0x180007256  call    pagerLockDb
0x18000725b  mov     edi, eax
0x18000725d  test    eax, eax
0x18000725f  jnz     loc_1800071D5
0x180007265  mov     rax, [rbx+50h]
0x180007269  cmp     [rax], r14
0x18000726c  jnz     loc_1800072F6
0x180007272  cmp     byte ptr [rbx+9], 2
0x180007276  jz      short loc_1800072F6
0x180007278  mov     rsi, [rbx]
0x18000727b  lea     r9, [rbp+var_20]
0x18000727f  mov     rdx, [rbx+0E0h]
0x180007286  xor     r8d, r8d
0x180007289  mov     [rbp+var_20], r14d
0x18000728d  mov     rcx, rsi
0x180007290  mov     rax, [rsi+38h]
0x180007294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007299  mov     edi, eax
0x18000729b  test    eax, eax
0x18000729d  jnz     short loc_1800072F6
0x18000729f  cmp     [rbp+var_20], r14d
0x1800072a3  jz      short loc_1800072F6
0x1800072a5  mov     r8, [rbx+50h]
0x1800072a9  lea     rax, [rbp+var_1C]
0x1800072ad  mov     rdx, [rbx+0E0h]
0x1800072b4  mov     r9d, 802h
0x1800072ba  mov     rcx, rsi
0x1800072bd  mov     [rsp+50h+var_30], rax
0x1800072c2  mov     [rbp+var_1C], r14d
0x1800072c6  call    sqlite3OsOpen
0x1800072cb  mov     edi, eax
0x1800072cd  test    eax, eax
0x1800072cf  jnz     short loc_1800072F6
0x1800072d1  test    byte ptr [rbp+var_1C], 1
0x1800072d5  jz      short loc_1800072F6
0x1800072d7  lea     r8, aCannotOpenFile; "cannot open file"
0x1800072de  mov     edx, 0F43Eh
0x1800072e3  lea     ecx, [rax+0Eh]
0x1800072e6  call    sqlite3ReportError
0x1800072eb  mov     rcx, [rbx+50h]
0x1800072ef  mov     edi, eax
0x1800072f1  call    sqlite3OsClose
0x1800072f6  mov     rax, [rbx+50h]
0x1800072fa  cmp     [rax], r14
0x1800072fd  jz      short loc_180007327
0x1800072ff  mov     rcx, rbx
0x180007302  call    pagerSyncHotJournal
0x180007307  mov     edi, eax
0x180007309  test    eax, eax
0x18000730b  jnz     short loc_180007342
0x18000730d  cmp     [rbx+10h], r14b
0x180007311  mov     edx, r14d
0x180007314  mov     rcx, rbx
0x180007317  setz    dl
0x18000731a  call    pager_playback
0x18000731f  mov     edi, eax
0x180007321  mov     [rbx+15h], r14b
0x180007325  jmp     short loc_18000733A
0x180007327  cmp     [rbx+8], r14b
0x18000732b  jnz     short loc_18000733A
0x18000732d  mov     edx, 1
0x180007332  mov     rcx, rbx
0x180007335  call    pagerUnlockDb
0x18000733a  test    edi, edi
0x18000733c  jz      loc_180007221
0x180007342  mov     edx, edi
0x180007344  mov     rcx, rbx
0x180007347  call    pager_error
0x18000734c  jmp     loc_1800071D5
0x180007351  cmp     [rbx+1Ch], r14b
0x180007355  jz      loc_18000722B
0x18000735b  mov     rcx, [rbx+48h]
0x18000735f  lea     rdx, [rbp+var_18]
0x180007363  mov     r9d, 18h
0x180007369  lea     r8d, [r9-8]
0x18000736d  call    sqlite3OsRead
0x180007372  mov     edi, eax
0x180007374  test    eax, eax
0x180007376  jz      short loc_18000738A
0x180007378  cmp     eax, 20Ah
0x18000737d  jnz     loc_1800071D5
0x180007383  xorps   xmm0, xmm0
0x180007386  movups  [rbp+var_18], xmm0
0x18000738a  mov     rax, [rbx+88h]
0x180007391  sub     rax, qword ptr [rbp+var_18]
0x180007395  jnz     short loc_1800073A2
0x180007397  mov     rax, [rbx+90h]
0x18000739e  sub     rax, qword ptr [rbp+var_18+8]
0x1800073a2  test    rax, rax
0x1800073a5  jz      loc_18000722B
0x1800073ab  mov     rcx, rbx
0x1800073ae  call    pager_reset
0x1800073b3  cmp     [rbx+1Bh], r14b
0x1800073b7  jz      loc_18000722B
0x1800073bd  mov     rcx, [rbx+48h]
0x1800073c1  xor     r8d, r8d
0x1800073c4  xor     edx, edx
0x1800073c6  call    sqlite3OsUnfetch
0x1800073cb  jmp     loc_18000722B
0x1800073d0  lea     rdx, [rbx+20h]
0x1800073d4  mov     rcx, rbx
0x1800073d7  call    pagerPagecount
0x1800073dc  mov     edi, eax
0x1800073de  jmp     loc_180007198
```
