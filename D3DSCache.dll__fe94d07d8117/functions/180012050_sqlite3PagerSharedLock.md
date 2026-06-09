# sqlite3PagerSharedLock

- ea: `0x180012050`
- end: `0x180012325`
- name: `sqlite3PagerSharedLock`
- size: `725`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x180011d60`
- `0x180087e98`

## callees

- `0x180012050`
- `0x18001232c`
- `0x180032e10`
- `0x180032fa4`
- `0x1800378e8`
- `0x180038fec`
- `0x1800396b0`
- `0x18003a860`
- `0x18003b648`
- `0x18003fae4`
- `0x180042dac`
- `0x1800449f0`
- `0x180062e88`
- `0x18006dcf0`
- `0x18006e088`
- `0x18006e1dc`
- `0x18006e6d8`
- `0x1800a8010`

## string_xrefs

- `0x1800121bc`: `cannot open file`

## pseudocode

```c
__int64 __fastcall sqlite3PagerSharedLock(__int64 *a1)
{
  unsigned int Transaction; // edi
  int v3; // esi
  char v4; // al
  unsigned int v5; // eax
  __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rax
  int v13; // [rsp+30h] [rbp-28h] BYREF
  int v14; // [rsp+34h] [rbp-24h] BYREF
  __int128 v15; // [rsp+38h] [rbp-20h] BYREF

  Transaction = 0;
  if ( !a1[37] && !*((_BYTE *)a1 + 21) )
  {
    v3 = 1;
    v13 = 1;
    do
    {
      v4 = *((_BYTE *)a1 + 22);
      if ( v4 )
      {
        Transaction = 0;
        if ( v4 != 5 )
          break;
      }
      if ( *((_BYTE *)a1 + 17) )
      {
        Transaction = 0;
LABEL_12:
        if ( *((_BYTE *)a1 + 22) != 5 )
          *((_BYTE *)a1 + 22) = 1;
        break;
      }
      v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1[9] + 56LL))(a1[9], 1);
      Transaction = v5;
      if ( !v5 )
        goto LABEL_12;
    }
    while ( v5 == 5 && ((unsigned int (__fastcall *)(__int64))a1[29])(a1[30]) );
    if ( Transaction )
      goto LABEL_54;
    if ( *((_BYTE *)a1 + 22) <= 1u )
    {
      Transaction = hasHotJournal(a1, &v13);
      if ( Transaction )
        goto LABEL_54;
      v3 = v13;
    }
    if ( v3 )
    {
      if ( *((_BYTE *)a1 + 18) )
      {
        Transaction = 776;
        goto LABEL_54;
      }
      Transaction = pagerLockDb(a1, 4);
      if ( Transaction )
        goto LABEL_54;
      if ( !*(_QWORD *)a1[10] && *((_BYTE *)a1 + 9) != 2 )
      {
        v6 = *a1;
        v7 = a1[28];
        v13 = 0;
        Transaction = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(v6 + 56))(v6, v7, 0, &v13);
        if ( !Transaction )
        {
          if ( v13 )
          {
            v8 = a1[10];
            v9 = a1[28];
            v14 = 0;
            Transaction = sqlite3OsOpen(v6, v9, v8, 2050, (__int64)&v14);
            if ( !Transaction && (v14 & 1) != 0 )
            {
              Transaction = sqlite3ReportError(14, 62418, "cannot open file");
              sqlite3OsClose(a1[10]);
            }
          }
        }
      }
      if ( *(_QWORD *)a1[10] )
      {
        Transaction = pagerSyncHotJournal(a1);
        if ( Transaction )
        {
LABEL_35:
          pager_error(a1, Transaction);
          goto LABEL_54;
        }
        Transaction = pager_playback(a1, *((_BYTE *)a1 + 16) == 0);
        *((_BYTE *)a1 + 21) = 0;
      }
      else if ( !*((_BYTE *)a1 + 8) )
      {
        pagerUnlockDb(a1, 1);
      }
      if ( Transaction )
        goto LABEL_35;
    }
    if ( !*((_BYTE *)a1 + 16) && *((_BYTE *)a1 + 28) )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, __int64))(*(_QWORD *)a1[9] + 16LL))(
              a1[9],
              &v15,
              16,
              24);
      Transaction = v10;
      if ( v10 )
      {
        if ( v10 != 522 )
          goto LABEL_54;
        v15 = 0;
      }
      v11 = a1[17] - v15;
      if ( !v11 )
        v11 = a1[18] - *((_QWORD *)&v15 + 1);
      if ( v11 )
      {
        pager_reset(a1);
        if ( *((_BYTE *)a1 + 27) )
          sqlite3OsUnfetch(a1[9], 0, 0);
      }
    }
    Transaction = pagerOpenWalIfPresent(a1);
  }
  if ( a1[37] )
    Transaction = pagerBeginReadTransaction(a1);
  if ( !*((_BYTE *)a1 + 16) && !*((_BYTE *)a1 + 21) )
  {
    if ( Transaction )
      goto LABEL_54;
    Transaction = pagerPagecount(a1, a1 + 4);
  }
  if ( !Transaction )
  {
    *((_BYTE *)a1 + 21) = 1;
    *((_BYTE *)a1 + 28) = 1;
    return Transaction;
  }
LABEL_54:
  pager_unlock(a1);
  return Transaction;
}

```

## disassembly

```asm
0x180012050  mov     [rsp+arg_8], rbx
0x180012055  mov     [rsp+arg_10], rsi
0x18001205a  push    rdi
0x18001205b  sub     rsp, 50h
0x18001205f  mov     rax, cs:__security_cookie
0x180012066  xor     rax, rsp
0x180012069  mov     [rsp+58h+var_10], rax
0x18001206e  xor     edi, edi
0x180012070  mov     rbx, rcx
0x180012073  cmp     [rcx+128h], rdi
0x18001207a  jnz     loc_1800122BE
0x180012080  cmp     [rcx+15h], dil
0x180012084  jnz     loc_1800122BE
0x18001208a  mov     esi, 1
0x18001208f  mov     [rsp+58h+var_28], esi
0x180012093  movzx   eax, byte ptr [rbx+16h]
0x180012097  cmp     al, sil
0x18001209a  jb      short loc_1800120A2
0x18001209c  xor     edi, edi
0x18001209e  cmp     al, 5
0x1800120a0  jnz     short loc_1800120EA
0x1800120a2  cmp     byte ptr [rbx+11h], 0
0x1800120a6  jnz     short loc_1800120DE
0x1800120a8  mov     rcx, [rbx+48h]
0x1800120ac  mov     edx, esi
0x1800120ae  mov     rax, [rcx]
0x1800120b1  mov     rax, [rax+38h]
0x1800120b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120ba  mov     edi, eax
0x1800120bc  test    eax, eax
0x1800120be  jz      short loc_1800120E0
0x1800120c0  cmp     eax, 5
0x1800120c3  jnz     short loc_1800120EA
0x1800120c5  mov     rcx, [rbx+0F0h]
0x1800120cc  mov     rax, [rbx+0E8h]
0x1800120d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120d8  test    eax, eax
0x1800120da  jnz     short loc_180012093
0x1800120dc  jmp     short loc_1800120EA
0x1800120de  xor     edi, edi
0x1800120e0  cmp     byte ptr [rbx+16h], 5
0x1800120e4  jz      short loc_1800120EA
0x1800120e6  mov     [rbx+16h], sil
0x1800120ea  test    edi, edi
0x1800120ec  jnz     loc_1800122F4
0x1800120f2  cmp     [rbx+16h], sil
0x1800120f6  ja      short loc_180012113
0x1800120f8  lea     rdx, [rsp+58h+var_28]
0x1800120fd  mov     rcx, rbx
0x180012100  call    hasHotJournal
0x180012105  mov     edi, eax
0x180012107  test    eax, eax
0x180012109  jnz     loc_1800122F4
0x18001210f  mov     esi, [rsp+58h+var_28]
0x180012113  test    esi, esi
0x180012115  jz      loc_180012233
0x18001211b  cmp     byte ptr [rbx+12h], 0
0x18001211f  jz      short loc_18001212B
0x180012121  mov     edi, 308h
0x180012126  jmp     loc_1800122F4
0x18001212b  mov     edx, 4
0x180012130  mov     rcx, rbx
0x180012133  call    pagerLockDb
0x180012138  mov     edi, eax
0x18001213a  test    eax, eax
0x18001213c  jnz     loc_1800122F4
0x180012142  mov     rcx, [rbx+50h]
0x180012146  cmp     qword ptr [rcx], 0
0x18001214a  jnz     loc_1800121DD
0x180012150  cmp     byte ptr [rbx+9], 2
0x180012154  jz      loc_1800121DD
0x18001215a  mov     rsi, [rbx]
0x18001215d  lea     r9, [rsp+58h+var_28]
0x180012162  mov     rdx, [rbx+0E0h]
0x180012169  xor     r8d, r8d
0x18001216c  mov     [rsp+58h+var_28], eax
0x180012170  mov     rcx, rsi
0x180012173  mov     rax, [rsi+38h]
0x180012177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001217c  mov     edi, eax
0x18001217e  test    eax, eax
0x180012180  jnz     short loc_1800121DD
0x180012182  cmp     [rsp+58h+var_28], eax
0x180012186  jz      short loc_1800121DD
0x180012188  mov     r8, [rbx+50h]
0x18001218c  mov     r9d, 802h
0x180012192  mov     rdx, [rbx+0E0h]
0x180012199  mov     rcx, rsi
0x18001219c  mov     [rsp+58h+var_24], eax
0x1800121a0  lea     rax, [rsp+58h+var_24]
0x1800121a5  mov     [rsp+58h+var_38], rax
0x1800121aa  call    sqlite3OsOpen
0x1800121af  mov     edi, eax
0x1800121b1  test    eax, eax
0x1800121b3  jnz     short loc_1800121DD
0x1800121b5  test    byte ptr [rsp+58h+var_24], 1
0x1800121ba  jz      short loc_1800121DD
0x1800121bc  lea     r8, aCannotOpenFile; "cannot open file"
0x1800121c3  mov     edx, 0F3D2h
0x1800121c8  mov     ecx, 0Eh
0x1800121cd  call    sqlite3ReportError
0x1800121d2  mov     rcx, [rbx+50h]
0x1800121d6  mov     edi, eax
0x1800121d8  call    sqlite3OsClose
0x1800121dd  mov     rax, [rbx+50h]
0x1800121e1  cmp     qword ptr [rax], 0
0x1800121e5  jz      short loc_18001220D
0x1800121e7  mov     rcx, rbx
0x1800121ea  call    pagerSyncHotJournal
0x1800121ef  mov     edi, eax
0x1800121f1  test    eax, eax
0x1800121f3  jnz     short loc_180012224
0x1800121f5  xor     edx, edx
0x1800121f7  mov     rcx, rbx
0x1800121fa  cmp     [rbx+10h], dl
0x1800121fd  setz    dl
0x180012200  call    pager_playback
0x180012205  mov     edi, eax
0x180012207  mov     byte ptr [rbx+15h], 0
0x18001220b  jmp     short loc_180012220
0x18001220d  cmp     byte ptr [rbx+8], 0
0x180012211  jnz     short loc_180012220
0x180012213  mov     edx, 1
0x180012218  mov     rcx, rbx
0x18001221b  call    pagerUnlockDb
0x180012220  test    edi, edi
0x180012222  jz      short loc_180012233
0x180012224  mov     edx, edi
0x180012226  mov     rcx, rbx
0x180012229  call    pager_error
0x18001222e  jmp     loc_1800122F4
0x180012233  cmp     byte ptr [rbx+10h], 0
0x180012237  jnz     short loc_1800122B4
0x180012239  cmp     byte ptr [rbx+1Ch], 0
0x18001223d  jz      short loc_1800122B4
0x18001223f  mov     rcx, [rbx+48h]
0x180012243  lea     rdx, [rsp+58h+var_20]
0x180012248  mov     r9d, 18h
0x18001224e  mov     r8d, 10h
0x180012254  mov     rax, [rcx]
0x180012257  mov     rax, [rax+10h]
0x18001225b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012260  mov     edi, eax
0x180012262  test    eax, eax
0x180012264  jz      short loc_180012279
0x180012266  cmp     eax, 20Ah
0x18001226b  jnz     loc_1800122F4
0x180012271  xorps   xmm0, xmm0
0x180012274  movups  [rsp+58h+var_20], xmm0
0x180012279  mov     rax, [rbx+88h]
0x180012280  sub     rax, qword ptr [rsp+58h+var_20]
0x180012285  jnz     short loc_180012293
0x180012287  mov     rax, [rbx+90h]
0x18001228e  sub     rax, qword ptr [rsp+58h+var_20+8]
0x180012293  test    rax, rax
0x180012296  jz      short loc_1800122B4
0x180012298  mov     rcx, rbx
0x18001229b  call    pager_reset
0x1800122a0  cmp     byte ptr [rbx+1Bh], 0
0x1800122a4  jz      short loc_1800122B4
0x1800122a6  mov     rcx, [rbx+48h]
0x1800122aa  xor     r8d, r8d
0x1800122ad  xor     edx, edx
0x1800122af  call    sqlite3OsUnfetch
0x1800122b4  mov     rcx, rbx
0x1800122b7  call    pagerOpenWalIfPresent
0x1800122bc  mov     edi, eax
0x1800122be  cmp     qword ptr [rbx+128h], 0
0x1800122c6  jz      short loc_1800122D2
0x1800122c8  mov     rcx, rbx
0x1800122cb  call    pagerBeginReadTransaction
0x1800122d0  mov     edi, eax
0x1800122d2  cmp     byte ptr [rbx+10h], 0
0x1800122d6  jnz     short loc_1800122F0
0x1800122d8  cmp     byte ptr [rbx+15h], 0
0x1800122dc  jnz     short loc_1800122F0
0x1800122de  test    edi, edi
0x1800122e0  jnz     short loc_1800122F4
0x1800122e2  lea     rdx, [rbx+20h]
0x1800122e6  mov     rcx, rbx
0x1800122e9  call    pagerPagecount
0x1800122ee  mov     edi, eax
0x1800122f0  test    edi, edi
0x1800122f2  jz      short loc_1800122FE
0x1800122f4  mov     rcx, rbx
0x1800122f7  call    pager_unlock
0x1800122fc  jmp     short loc_180012306
0x1800122fe  mov     byte ptr [rbx+15h], 1
0x180012302  mov     byte ptr [rbx+1Ch], 1
0x180012306  mov     eax, edi
0x180012308  mov     rcx, [rsp+58h+var_10]
0x18001230d  xor     rcx, rsp; StackCookie
0x180012310  call    __security_check_cookie
0x180012315  mov     rbx, [rsp+58h+arg_8]
0x18001231a  mov     rsi, [rsp+58h+arg_10]
0x18001231f  add     rsp, 50h
0x180012323  pop     rdi
0x180012324  retn
```
