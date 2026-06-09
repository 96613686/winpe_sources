# sqlite3PagerSharedLock

- ea: `0x180044838`
- end: `0x180044b2a`
- name: `sqlite3PagerSharedLock`
- size: `754`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: ``

## callers

- `0x180044514`
- `0x180093a44`
- `0x18009d2c0`

## callees

- `0x18002619c`
- `0x180032e98`
- `0x18003338c`
- `0x18003f514`
- `0x180041314`
- `0x180043990`
- `0x180044838`
- `0x180044bd4`
- `0x180046368`
- `0x1800488b8`
- `0x18005f1d8`
- `0x18005fa64`
- `0x18005fce4`
- `0x180060100`
- `0x1800789c0`
- `0x18008a0d4`
- `0x18008a350`
- `0x1800b0010`

## string_xrefs

- `0x180044aa5`: `cannot open file`

## pseudocode

```c
__int64 __fastcall sqlite3PagerSharedLock(__int64 *a1)
{
  unsigned int Transaction; // edi
  __int64 v3; // rax
  __int64 *v5; // rcx
  __int64 v6; // r8
  unsigned int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  int v13; // [rsp+30h] [rbp-20h] BYREF
  __int128 v14; // [rsp+38h] [rbp-18h] BYREF

  Transaction = 0;
  if ( a1[41] || *((_BYTE *)a1 + 21) )
    goto LABEL_2;
  v13 = 1;
  Transaction = pager_wait_on_lock(a1, 1);
  if ( Transaction )
    goto LABEL_18;
  if ( *((_BYTE *)a1 + 22) > 1u )
    goto LABEL_56;
  Transaction = hasHotJournal(a1, &v13);
  if ( Transaction )
    goto LABEL_18;
  if ( v13 )
  {
LABEL_56:
    if ( *((_BYTE *)a1 + 18) )
    {
      Transaction = 776;
      goto LABEL_18;
    }
    Transaction = pagerLockDb(a1, 4);
    if ( Transaction )
      goto LABEL_18;
    if ( !*(_QWORD *)a1[10] && *((_BYTE *)a1 + 9) != 2 )
    {
      v9 = *a1;
      v10 = a1[28];
      v13 = 0;
      Transaction = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(v9 + 56))(v9, v10, 0, &v13);
      if ( !Transaction )
      {
        if ( v13 )
        {
          v11 = a1[10];
          v12 = a1[28];
          LODWORD(v14) = 0;
          Transaction = sqlite3OsOpen(v9, v12, v11, 2050, (__int64)&v14);
          if ( !Transaction && (v14 & 1) != 0 )
          {
            Transaction = sqlite3ReportError(14, 62609, "cannot open file");
            sqlite3OsClose(a1[10]);
          }
        }
      }
    }
    if ( *(_QWORD *)a1[10] )
    {
      Transaction = pagerSyncHotJournal(a1);
      if ( Transaction )
        goto LABEL_53;
      Transaction = pager_playback(a1, *((_BYTE *)a1 + 16) == 0);
      *((_BYTE *)a1 + 21) = 0;
    }
    else if ( !*((_BYTE *)a1 + 8) )
    {
      pagerUnlockDb(a1, 1);
    }
    if ( !Transaction )
      goto LABEL_26;
LABEL_53:
    pager_error(a1, Transaction);
    goto LABEL_18;
  }
LABEL_26:
  if ( !*((_BYTE *)a1 + 16) && *((_BYTE *)a1 + 28) )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1[9] + 16LL))(a1[9], &v14, 16);
    Transaction = v7;
    if ( v7 )
    {
      if ( v7 != 522 )
        goto LABEL_18;
      v14 = 0;
    }
    v8 = a1[17] - v14;
    if ( !v8 )
      v8 = a1[18] - *((_QWORD *)&v14 + 1);
    if ( v8 )
    {
      pager_reset(a1);
      if ( *((_BYTE *)a1 + 27) )
        sqlite3OsUnfetch(a1[9], 0, 0);
    }
  }
  Transaction = pagerOpenWalIfPresent(a1);
LABEL_2:
  if ( a1[41] )
    Transaction = pagerBeginReadTransaction(a1);
  if ( !*((_BYTE *)a1 + 16) && !*((_BYTE *)a1 + 21) )
  {
    if ( Transaction )
    {
LABEL_18:
      pager_unlock(a1);
      return Transaction;
    }
    v3 = a1[41];
    if ( v3 && *(__int16 *)(v3 + 60) >= 0 )
    {
      LODWORD(v3) = *(_DWORD *)(v3 + 92);
      if ( (_DWORD)v3 )
      {
LABEL_10:
        if ( (unsigned int)v3 > *((_DWORD *)a1 + 47) )
          *((_DWORD *)a1 + 47) = v3;
        *((_DWORD *)a1 + 8) = v3;
        Transaction = 0;
        goto LABEL_13;
      }
    }
    else
    {
      LODWORD(v3) = 0;
    }
    v5 = (__int64 *)a1[9];
    v6 = *v5;
    if ( *v5 )
    {
      *(_QWORD *)&v14 = 0;
      Transaction = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v6 + 48))(v5, &v14);
      if ( Transaction )
        goto LABEL_13;
      v3 = (a1[25] + (__int64)v14 - 1) / a1[25];
    }
    goto LABEL_10;
  }
LABEL_13:
  if ( Transaction )
    goto LABEL_18;
  *((_BYTE *)a1 + 21) = 1;
  *((_BYTE *)a1 + 28) = 1;
  return Transaction;
}

```

## disassembly

```asm
0x180044838  mov     [rsp-18h+arg_8], rbx
0x18004483d  mov     [rsp-18h+arg_10], rsi
0x180044842  push    rbp
0x180044843  push    rdi
0x180044844  push    r14
0x180044846  mov     rbp, rsp
0x180044849  sub     rsp, 50h
0x18004484d  mov     rax, cs:__security_cookie
0x180044854  xor     rax, rsp
0x180044857  mov     [rbp+var_8], rax
0x18004485b  xor     r14d, r14d
0x18004485e  mov     rbx, rcx
0x180044861  mov     edi, r14d
0x180044864  cmp     [rcx+148h], r14
0x18004486b  jz      short loc_1800448EB
0x18004486d  cmp     [rbx+148h], r14
0x180044874  jz      short loc_180044880
0x180044876  mov     rcx, rbx
0x180044879  call    pagerBeginReadTransaction
0x18004487e  mov     edi, eax
0x180044880  cmp     [rbx+10h], r14b
0x180044884  jnz     short loc_1800448BC
0x180044886  cmp     [rbx+15h], r14b
0x18004488a  jnz     short loc_1800448BC
0x18004488c  test    edi, edi
0x18004488e  jnz     short loc_18004490C
0x180044890  mov     rax, [rbx+148h]
0x180044897  test    rax, rax
0x18004489a  jz      short loc_180044916
0x18004489c  cmp     [rax+3Ch], r14w
0x1800448a1  jl      short loc_180044916
0x1800448a3  mov     eax, [rax+5Ch]
0x1800448a6  test    eax, eax
0x1800448a8  jz      short loc_180044919
0x1800448aa  cmp     eax, [rbx+0BCh]
0x1800448b0  ja      loc_180044B1F
0x1800448b6  mov     [rbx+20h], eax
0x1800448b9  mov     edi, r14d
0x1800448bc  test    edi, edi
0x1800448be  jnz     short loc_18004490C
0x1800448c0  mov     byte ptr [rbx+15h], 1
0x1800448c4  mov     byte ptr [rbx+1Ch], 1
0x1800448c8  mov     eax, edi
0x1800448ca  mov     rcx, [rbp+var_8]
0x1800448ce  xor     rcx, rsp; StackCookie
0x1800448d1  call    __security_check_cookie
0x1800448d6  lea     r11, [rsp+50h+var_s0]
0x1800448db  mov     rbx, [r11+28h]
0x1800448df  mov     rsi, [r11+30h]
0x1800448e3  mov     rsp, r11
0x1800448e6  pop     r14
0x1800448e8  pop     rdi
0x1800448e9  pop     rbp
0x1800448ea  retn
0x1800448eb  cmp     [rcx+15h], r14b
0x1800448ef  jnz     loc_18004486D
0x1800448f5  mov     edx, 1
0x1800448fa  mov     [rbp+var_20], 1
0x180044901  call    pager_wait_on_lock
0x180044906  mov     edi, eax
0x180044908  test    eax, eax
0x18004490a  jz      short loc_180044957
0x18004490c  mov     rcx, rbx
0x18004490f  call    pager_unlock
0x180044914  jmp     short loc_1800448C8
0x180044916  mov     eax, r14d
0x180044919  mov     rcx, [rbx+48h]
0x18004491d  mov     r8, [rcx]
0x180044920  test    r8, r8
0x180044923  jz      short loc_1800448AA
0x180044925  mov     qword ptr [rbp+var_18], r14
0x180044929  lea     rdx, [rbp+var_18]
0x18004492d  mov     rax, [r8+30h]
0x180044931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044936  mov     edi, eax
0x180044938  test    eax, eax
0x18004493a  jnz     short loc_1800448BC
0x18004493c  mov     rcx, [rbx+0C8h]
0x180044943  mov     rax, qword ptr [rbp+var_18]
0x180044947  dec     rax
0x18004494a  add     rax, rcx
0x18004494d  cqo
0x18004494f  idiv    rcx
0x180044952  jmp     loc_1800448AA
0x180044957  cmp     byte ptr [rbx+16h], 1
0x18004495b  ja      loc_180044A0C
0x180044961  lea     rdx, [rbp+var_20]
0x180044965  mov     rcx, rbx
0x180044968  call    hasHotJournal
0x18004496d  mov     edi, eax
0x18004496f  test    eax, eax
0x180044971  jnz     short loc_18004490C
0x180044973  cmp     [rbp+var_20], r14d
0x180044977  jnz     loc_180044A0C
0x18004497d  cmp     [rbx+10h], r14b
0x180044981  jz      short loc_180044992
0x180044983  mov     rcx, rbx
0x180044986  call    pagerOpenWalIfPresent
0x18004498b  mov     edi, eax
0x18004498d  jmp     loc_18004486D
0x180044992  cmp     [rbx+1Ch], r14b
0x180044996  jz      short loc_180044983
0x180044998  mov     rcx, [rbx+48h]
0x18004499c  lea     rdx, [rbp+var_18]
0x1800449a0  mov     r9d, 18h
0x1800449a6  mov     rax, [rcx]
0x1800449a9  lea     r8d, [r9-8]
0x1800449ad  mov     rax, [rax+10h]
0x1800449b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800449b6  mov     edi, eax
0x1800449b8  test    eax, eax
0x1800449ba  jz      short loc_1800449CE
0x1800449bc  cmp     eax, 20Ah
0x1800449c1  jnz     loc_18004490C
0x1800449c7  xorps   xmm0, xmm0
0x1800449ca  movups  [rbp+var_18], xmm0
0x1800449ce  mov     rax, [rbx+88h]
0x1800449d5  sub     rax, qword ptr [rbp+var_18]
0x1800449d9  jnz     short loc_1800449E6
0x1800449db  mov     rax, [rbx+90h]
0x1800449e2  sub     rax, qword ptr [rbp+var_18+8]
0x1800449e6  test    rax, rax
0x1800449e9  jz      short loc_180044983
0x1800449eb  mov     rcx, rbx
0x1800449ee  call    pager_reset
0x1800449f3  cmp     [rbx+1Bh], r14b
0x1800449f7  jz      short loc_180044983
0x1800449f9  mov     rcx, [rbx+48h]
0x1800449fd  xor     r8d, r8d
0x180044a00  xor     edx, edx
0x180044a02  call    sqlite3OsUnfetch
0x180044a07  jmp     loc_180044983
0x180044a0c  cmp     [rbx+12h], r14b
0x180044a10  jz      short loc_180044A1C
0x180044a12  mov     edi, 308h
0x180044a17  jmp     loc_18004490C
0x180044a1c  mov     edx, 4
0x180044a21  mov     rcx, rbx
0x180044a24  call    pagerLockDb
0x180044a29  mov     edi, eax
0x180044a2b  test    eax, eax
0x180044a2d  jnz     loc_18004490C
0x180044a33  mov     rax, [rbx+50h]
0x180044a37  cmp     [rax], r14
0x180044a3a  jnz     loc_180044AC4
0x180044a40  cmp     byte ptr [rbx+9], 2
0x180044a44  jz      short loc_180044AC4
0x180044a46  mov     rsi, [rbx]
0x180044a49  lea     r9, [rbp+var_20]
0x180044a4d  mov     rdx, [rbx+0E0h]
0x180044a54  xor     r8d, r8d
0x180044a57  mov     [rbp+var_20], r14d
0x180044a5b  mov     rcx, rsi
0x180044a5e  mov     rax, [rsi+38h]
0x180044a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a67  mov     edi, eax
0x180044a69  test    eax, eax
0x180044a6b  jnz     short loc_180044AC4
0x180044a6d  cmp     [rbp+var_20], r14d
0x180044a71  jz      short loc_180044AC4
0x180044a73  mov     r8, [rbx+50h]
0x180044a77  lea     rax, [rbp+var_18]
0x180044a7b  mov     rdx, [rbx+0E0h]
0x180044a82  mov     r9d, 802h
0x180044a88  mov     rcx, rsi
0x180044a8b  mov     [rsp+50h+var_30], rax
0x180044a90  mov     dword ptr [rbp+var_18], r14d
0x180044a94  call    sqlite3OsOpen
0x180044a99  mov     edi, eax
0x180044a9b  test    eax, eax
0x180044a9d  jnz     short loc_180044AC4
0x180044a9f  test    byte ptr [rbp+var_18], 1
0x180044aa3  jz      short loc_180044AC4
0x180044aa5  lea     r8, aCannotOpenFile; "cannot open file"
0x180044aac  mov     edx, 0F491h
0x180044ab1  lea     ecx, [rax+0Eh]
0x180044ab4  call    sqlite3ReportError
0x180044ab9  mov     rcx, [rbx+50h]
0x180044abd  mov     edi, eax
0x180044abf  call    sqlite3OsClose
0x180044ac4  mov     rax, [rbx+50h]
0x180044ac8  cmp     [rax], r14
0x180044acb  jz      short loc_180044AF5
0x180044acd  mov     rcx, rbx
0x180044ad0  call    pagerSyncHotJournal
0x180044ad5  mov     edi, eax
0x180044ad7  test    eax, eax
0x180044ad9  jnz     short loc_180044B10
0x180044adb  cmp     [rbx+10h], r14b
0x180044adf  mov     edx, r14d
0x180044ae2  mov     rcx, rbx
0x180044ae5  setz    dl
0x180044ae8  call    pager_playback
0x180044aed  mov     edi, eax
0x180044aef  mov     [rbx+15h], r14b
0x180044af3  jmp     short loc_180044B08
0x180044af5  cmp     [rbx+8], r14b
0x180044af9  jnz     short loc_180044B08
0x180044afb  mov     edx, 1
0x180044b00  mov     rcx, rbx
0x180044b03  call    pagerUnlockDb
0x180044b08  test    edi, edi
0x180044b0a  jz      loc_18004497D
0x180044b10  mov     edx, edi
0x180044b12  mov     rcx, rbx
0x180044b15  call    pager_error
0x180044b1a  jmp     loc_18004490C
0x180044b1f  mov     [rbx+0BCh], eax
0x180044b25  jmp     loc_1800448B6
```
