# WskProControlCallbacks

- ea: `0x140060234`
- end: `0x1400607f3`
- name: `WskProControlCallbacks`
- size: `1471`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140025720`

## callees

- `0x1400265e0`
- `0x140060234`
- `0x140072920`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400605fb`
- `ntoskrnl!IofCompleteRequest` at `0x1400605fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400602f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060321`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400603b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060483`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060518`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400605a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060635`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060689`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400606bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060754`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006079d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400602f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060321`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400603b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060483`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060518`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400605a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060635`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060689`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400606bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060754`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006079d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060309`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060410`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400604cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060586`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400605d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400606e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060309`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060410`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400604cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060586`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400605d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400606e7`

## pseudocode

```c
__int64 __fastcall WskProControlCallbacks(unsigned __int16 *a1, int a2, IRP *a3)
{
  int v3; // eax
  unsigned int v6; // ebx
  char v7; // r14
  unsigned int v8; // edx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // r15
  _QWORD *v14; // rax
  KIRQL v15; // al
  KIRQL v16; // dl
  __int16 v17; // ax
  _QWORD *v18; // rcx
  __int16 v19; // r14
  char v20; // r12
  KSPIN_LOCK *v21; // r14
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int16 v24; // ax
  int v25; // r15d
  __int64 v26; // rax
  KIRQL v27; // cl
  unsigned __int16 v28; // ax
  int v29; // eax
  unsigned int v30; // eax
  char v31; // r15
  KIRQL v32; // al
  bool v34; // zf
  _QWORD *v35; // rax
  unsigned __int16 v36; // cx
  __int16 v37; // [rsp+20h] [rbp-60h]
  _QWORD v38[10]; // [rsp+30h] [rbp-50h] BYREF
  KIRQL NewIrql; // [rsp+C8h] [rbp+48h]
  int v40; // [rsp+D0h] [rbp+50h] BYREF
  __int16 v41; // [rsp+D8h] [rbp+58h]

  v3 = a2 & 0x7FFFFFFF;
  v6 = 259;
  if ( a2 >= 0 )
    v3 = a2;
  v7 = v3;
  if ( v3 != (unsigned __int16)v3 )
    goto LABEL_4;
  if ( ((unsigned __int16)v3 & *(_WORD *)(*((_QWORD *)a1 + 20) + 74LL)) != 0 )
    goto LABEL_6;
  v8 = (unsigned int)a2 >> 31;
  v9 = *a1 - 44256;
  if ( !v9 )
    goto LABEL_6;
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( *((_BYTE *)a1 + 2) != 1 )
      goto LABEL_71;
    if ( (_BYTE)v8 )
    {
      v13 = 512;
      if ( (_WORD)v3 == 512 )
      {
        v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
        v17 = -513;
        goto LABEL_81;
      }
    }
    else if ( (v3 & 0xFD2F) == 0 && (v3 & 0x2D0) != 0 && (v3 & 0x200) != 0 )
    {
      v35 = (_QWORD *)*((_QWORD *)a1 + 9);
      if ( v35 && *v35 )
      {
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
        v36 = a1[17];
        if ( (v36 & 0x200) == 0 )
          a1[17] = v36 | v7 & 0xD0 | 0x200;
        goto LABEL_19;
      }
LABEL_6:
      v6 = -1073741808;
      goto LABEL_55;
    }
    goto LABEL_4;
  }
  v11 = v10 - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      if ( v12 != 1 )
      {
        v6 = -1073741816;
        goto LABEL_55;
      }
      goto LABEL_6;
    }
    if ( *((_BYTE *)a1 + 2) == 1 )
    {
      v13 = 256;
      if ( (_WORD)v3 == 256 )
      {
        if ( !(_BYTE)v8 )
        {
          v14 = (_QWORD *)*((_QWORD *)a1 + 9);
          if ( v14 && *v14 )
          {
            v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
            a1[17] |= 0x100u;
LABEL_19:
            KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, v15);
            v6 = 0;
            goto LABEL_55;
          }
          goto LABEL_6;
        }
        v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
        v17 = -257;
LABEL_81:
        a1[17] &= v17;
        if ( *((_DWORD *)a1 + 24) )
          goto LABEL_82;
        goto LABEL_68;
      }
      goto LABEL_4;
    }
LABEL_71:
    v6 = -1073741436;
    goto LABEL_55;
  }
  if ( *((_BYTE *)a1 + 2) != 2 )
    goto LABEL_71;
  if ( (_BYTE)v8 )
  {
    if ( (_WORD)v3 == 128 )
    {
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
      a1[17] &= ~0x80u;
      if ( (*((_DWORD *)a1 + 1) & 0x300) != 0 )
      {
        if ( !a3 )
        {
LABEL_83:
          v6 = 1073741843;
          goto LABEL_69;
        }
        a3->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        a3->Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)128;
LABEL_85:
        a3->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)*((_QWORD *)a1 + 14);
        *((_QWORD *)a1 + 14) = a3;
        goto LABEL_69;
      }
      goto LABEL_68;
    }
    v13 = 64;
    if ( (_WORD)v3 == 64 )
    {
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
      a1[17] &= ~0x40u;
      v34 = (*((_DWORD *)a1 + 1) & 0x40) == 0;
    }
    else
    {
      v13 = 16;
      if ( (_WORD)v3 != 16 )
        goto LABEL_4;
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
      a1[17] &= ~0x10u;
      v34 = (*((_DWORD *)a1 + 1) & 0x2000) == 0;
    }
    if ( !v34 )
    {
LABEL_82:
      if ( !a3 )
        goto LABEL_83;
      a3->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      a3->Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)v13;
      goto LABEL_85;
    }
LABEL_68:
    v6 = 0;
LABEL_69:
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, v16);
    goto LABEL_55;
  }
  if ( (v3 & 0xFF2F) != 0 )
  {
LABEL_4:
    v6 = -1073741811;
    goto LABEL_55;
  }
  v18 = (_QWORD *)*((_QWORD *)a1 + 9);
  if ( !v18 )
    goto LABEL_6;
  v41 = v3 & 0x40;
  if ( (v3 & 0x40) != 0 && !*v18 )
    goto LABEL_6;
  v37 = v3 & 0x80;
  if ( (v3 & 0x80) != 0 && !v18[1] )
    goto LABEL_6;
  v19 = v3 & 0x10;
  if ( (v3 & 0x10) != 0 && !v18[2] )
    goto LABEL_6;
  v6 = 0;
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
  v20 = 1;
  if ( !v19 || (LOWORD(v40) = a1[17], (v40 & 0x10) != 0) )
  {
    v21 = (KSPIN_LOCK *)(a1 + 8);
  }
  else
  {
    memset(v38, 0, sizeof(v38));
    v21 = (KSPIN_LOCK *)(a1 + 8);
    a1[17] = v40 | 0x10;
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, NewIrql);
    v38[1] = a1;
    v38[2] = 0xFFFD00000000LL;
    v38[0] = AfdTLDontCareIOCompletion;
    v38[4] = &AfdTLSockOptEnable;
    v20 = 0;
    v22 = *((_QWORD *)a1 + 7);
    v23 = *((_QWORD *)a1 + 5);
    LODWORD(v38[3]) = 52;
    v38[5] = 4;
    (*(void (__fastcall **)(__int64, _QWORD *))(v22 + 8))(v23, v38);
  }
  if ( v41 )
  {
    if ( !v20 )
    {
      NewIrql = KeAcquireSpinLockRaiseToDpc(v21);
      v20 = 1;
    }
    v24 = a1[17];
    if ( (v24 & 0x40) == 0 )
    {
      v25 = *((_DWORD *)a1 + 1);
      a1[17] = v24 | 0x40;
      if ( (v25 & 0x80) != 0 )
      {
        memset(v38, 0, sizeof(v38));
        *((_DWORD *)a1 + 1) = v25 & 0xFFFFFF7F;
        KeReleaseSpinLock(v21, NewIrql);
        v38[0] = AfdTLDontCareIOCompletion;
        v26 = *((_QWORD *)a1 + 7);
        v20 = 0;
        v38[1] = 0;
        (*(void (__fastcall **)(_QWORD, _QWORD *))(v26 + 32))(*((_QWORD *)a1 + 5), v38);
      }
    }
  }
  if ( !v37 )
    goto LABEL_53;
  if ( v20 )
  {
    v27 = NewIrql;
  }
  else
  {
    v27 = KeAcquireSpinLockRaiseToDpc(v21);
    NewIrql = v27;
    v20 = 1;
  }
  v28 = a1[17];
  if ( (v28 & 0x80) != 0 )
    goto LABEL_54;
  a1[17] = v28 | 0x80;
  v29 = *((_DWORD *)a1 + 1);
  if ( (v29 & 0xC00) == 0 )
  {
LABEL_53:
    if ( !v20 )
      goto LABEL_55;
LABEL_54:
    KeReleaseSpinLock(v21, NewIrql);
    goto LABEL_55;
  }
  v40 = 0;
  while ( 1 )
  {
    if ( (v29 & 0x800) != 0 )
    {
      v40 = 1;
      v30 = v29 & 0xFFFFF3FF;
      v31 = 0;
    }
    else
    {
      v31 = 1;
      v30 = v29 & 0xFFFFEBFF | 0x1000;
    }
    *((_DWORD *)a1 + 1) = v30;
    KeReleaseSpinLock(v21, v27);
    WskProTLEVENTDisconnect(a1, &v40);
    if ( !v31 )
      break;
    v32 = KeAcquireSpinLockRaiseToDpc(v21);
    *((_DWORD *)a1 + 1) &= ~0x1000u;
    v20 = 1;
    v27 = v32;
    NewIrql = v32;
    v29 = *((_DWORD *)a1 + 1);
    if ( (v29 & 0x800) == 0 )
      goto LABEL_53;
  }
LABEL_55:
  if ( a3 && v6 != 259 )
  {
    a3->IoStatus.Information = 0;
    a3->IoStatus.Status = v6;
    IofCompleteRequest(a3, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x140060234  mov     [rsp-38h+arg_0], rbx
0x140060239  push    rbp
0x14006023a  push    rsi
0x14006023b  push    rdi
0x14006023c  push    r12
0x14006023e  push    r13
0x140060240  push    r14
0x140060242  push    r15
0x140060244  mov     rbp, rsp
0x140060247  sub     rsp, 80h
0x14006024e  xor     r12d, r12d
0x140060251  mov     eax, edx
0x140060253  btr     eax, 1Fh
0x140060257  mov     rsi, r8
0x14006025a  test    edx, edx
0x14006025c  mov     rdi, rcx
0x14006025f  mov     ebx, 103h
0x140060264  cmovns  eax, edx
0x140060267  movzx   r14d, ax
0x14006026b  cmp     eax, r14d
0x14006026e  jz      short loc_14006027A
0x140060270  mov     ebx, 0C000000Dh
0x140060275  jmp     loc_1400605E2
0x14006027a  mov     rax, [rcx+0A0h]
0x140060281  test    [rax+4Ah], r14w
0x140060286  jz      short loc_140060292
0x140060288  mov     ebx, 0C0000010h
0x14006028d  jmp     loc_1400605E2
0x140060292  movzx   ecx, word ptr [rcx]
0x140060295  shr     edx, 1Fh
0x140060298  sub     ecx, 0ACE0h
0x14006029e  jz      short loc_140060288
0x1400602a0  sub     ecx, 1
0x1400602a3  jz      loc_1400606F8
0x1400602a9  sub     ecx, 1
0x1400602ac  jz      loc_140060339
0x1400602b2  sub     ecx, 1
0x1400602b5  jz      short loc_1400602C6
0x1400602b7  cmp     ecx, 1
0x1400602ba  jz      short loc_140060288
0x1400602bc  mov     ebx, 0C0000008h
0x1400602c1  jmp     loc_1400605E2
0x1400602c6  cmp     byte ptr [rdi+2], 1
0x1400602ca  jnz     loc_1400606FE
0x1400602d0  mov     r15d, 100h
0x1400602d6  cmp     r14w, r15w
0x1400602da  jnz     short loc_140060270
0x1400602dc  test    dl, dl
0x1400602de  jnz     short loc_14006031D
0x1400602e0  mov     rax, [rdi+48h]
0x1400602e4  test    rax, rax
0x1400602e7  jz      short loc_140060288
0x1400602e9  cmp     [rax], r12
0x1400602ec  jz      short loc_140060288
0x1400602ee  lea     rcx, [rdi+10h]; SpinLock
0x1400602f2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400602f9  nop     dword ptr [rax+rax+00h]
0x1400602fe  or      [rdi+22h], r15w
0x140060303  mov     dl, al; NewIrql
0x140060305  lea     rcx, [rdi+10h]; SpinLock
0x140060309  call    cs:__imp_KeReleaseSpinLock
0x140060310  nop     dword ptr [rax+rax+00h]
0x140060315  mov     ebx, r12d
0x140060318  jmp     loc_1400605E2
0x14006031d  lea     rcx, [rdi+10h]; SpinLock
0x140060321  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140060328  nop     dword ptr [rax+rax+00h]
0x14006032d  mov     dl, al
0x14006032f  mov     eax, 0FEFFh
0x140060334  jmp     loc_1400607B0
0x140060339  cmp     byte ptr [rdi+2], 2
0x14006033d  jnz     loc_1400606FE
0x140060343  test    dl, dl
0x140060345  jnz     loc_140060625
0x14006034b  test    r14d, 0FFFFFF2Fh
0x140060352  jnz     loc_140060270
0x140060358  mov     rcx, [rdi+48h]
0x14006035c  test    rcx, rcx
0x14006035f  jz      loc_140060288
0x140060365  movzx   eax, r14w
0x140060369  mov     r15d, 40h ; '@'
0x14006036f  and     ax, r15w
0x140060373  mov     [rbp+arg_18], ax
0x140060377  jz      short loc_140060382
0x140060379  cmp     [rcx], r12
0x14006037c  jz      loc_140060288
0x140060382  mov     r13d, 80h
0x140060388  movzx   eax, r14w
0x14006038c  and     ax, r13w
0x140060390  mov     [rbp+var_60], ax
0x140060394  jz      short loc_1400603A0
0x140060396  cmp     [rcx+8], r12
0x14006039a  jz      loc_140060288
0x1400603a0  and     r14w, 10h
0x1400603a5  jz      short loc_1400603B1
0x1400603a7  cmp     [rcx+10h], r12
0x1400603ab  jz      loc_140060288
0x1400603b1  lea     rcx, [rdi+10h]; SpinLock
0x1400603b5  mov     ebx, r12d
0x1400603b8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400603bf  nop     dword ptr [rax+rax+00h]
0x1400603c4  xor     ecx, ecx
0x1400603c6  mov     [rbp+NewIrql], al
0x1400603c9  mov     r12b, 1
0x1400603cc  test    r14w, r14w
0x1400603d0  jz      loc_14006046D
0x1400603d6  movzx   eax, word ptr [rdi+22h]
0x1400603da  lea     r14d, [rcx+10h]
0x1400603de  mov     word ptr [rbp+arg_10], ax
0x1400603e2  test    r14b, al
0x1400603e5  jnz     loc_14006046D
0x1400603eb  lea     r8d, [rcx+50h]; Size
0x1400603ef  xor     edx, edx; Val
0x1400603f1  lea     rcx, [rbp+var_50]; void *
0x1400603f5  call    memset
0x1400603fa  movzx   eax, word ptr [rbp+arg_10]
0x1400603fe  mov     dl, [rbp+NewIrql]; NewIrql
0x140060401  or      ax, r14w
0x140060405  lea     r14, [rdi+10h]
0x140060409  mov     [rdi+22h], ax
0x14006040d  mov     rcx, r14; SpinLock
0x140060410  call    cs:__imp_KeReleaseSpinLock
0x140060417  nop     dword ptr [rax+rax+00h]
0x14006041c  xor     ecx, ecx
0x14006041e  mov     [rbp+var_48], rdi
0x140060422  mov     [rbp+var_40], ecx
0x140060425  lea     rax, AfdTLDontCareIOCompletion
0x14006042c  mov     [rbp+var_50], rax
0x140060430  lea     rdx, [rbp+var_50]
0x140060434  lea     rax, AfdTLSockOptEnable
0x14006043b  mov     [rbp+var_3C], 0FFFDh
0x140060442  mov     [rbp+var_30], rax
0x140060446  mov     r12b, cl
0x140060449  mov     rax, [rdi+38h]
0x14006044d  mov     rcx, [rdi+28h]
0x140060451  mov     [rbp+var_38], 34h ; '4'
0x140060458  mov     [rbp+var_28], 4
0x140060460  mov     rax, [rax+8]
0x140060464  call    _guard_dispatch_icall
0x140060469  xor     ecx, ecx
0x14006046b  jmp     short loc_140060471
0x14006046d  lea     r14, [rdi+10h]
0x140060471  cmp     [rbp+arg_18], cx
0x140060475  jz      loc_140060502
0x14006047b  test    r12b, r12b
0x14006047e  jnz     short loc_140060495
0x140060480  mov     rcx, r14; SpinLock
0x140060483  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006048a  nop     dword ptr [rax+rax+00h]
0x14006048f  mov     [rbp+NewIrql], al
0x140060492  mov     r12b, 1
0x140060495  movzx   eax, word ptr [rdi+22h]
0x140060499  test    r15b, al
0x14006049c  jnz     short loc_140060502
0x14006049e  or      ax, r15w
0x1400604a2  mov     r15d, [rdi+4]
0x1400604a6  mov     [rdi+22h], ax
0x1400604aa  test    r13b, r15b
0x1400604ad  jz      short loc_140060502
0x1400604af  xor     edx, edx; Val
0x1400604b1  lea     rcx, [rbp+var_50]; void *
0x1400604b5  lea     r8d, [rdx+50h]; Size
0x1400604b9  call    memset
0x1400604be  mov     dl, [rbp+NewIrql]; NewIrql
0x1400604c1  btr     r15d, 7
0x1400604c6  mov     rcx, r14; SpinLock
0x1400604c9  mov     [rdi+4], r15d
0x1400604cd  call    cs:__imp_KeReleaseSpinLock
0x1400604d4  nop     dword ptr [rax+rax+00h]
0x1400604d9  xor     ecx, ecx
0x1400604db  lea     rax, AfdTLDontCareIOCompletion
0x1400604e2  mov     [rbp+var_50], rax
0x1400604e6  lea     rdx, [rbp+var_50]
0x1400604ea  mov     rax, [rdi+38h]
0x1400604ee  mov     r12b, cl
0x1400604f1  mov     [rbp+var_48], rcx
0x1400604f5  mov     rcx, [rdi+28h]
0x1400604f9  mov     rax, [rax+20h]
0x1400604fd  call    _guard_dispatch_icall
0x140060502  xor     r15d, r15d
0x140060505  cmp     [rbp+var_60], r15w
0x14006050a  jz      loc_1400605C8
0x140060510  test    r12b, r12b
0x140060513  jnz     short loc_14006052E
0x140060515  mov     rcx, r14; SpinLock
0x140060518  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006051f  nop     dword ptr [rax+rax+00h]
0x140060524  mov     cl, al
0x140060526  mov     [rbp+NewIrql], al
0x140060529  mov     r12b, 1
0x14006052c  jmp     short loc_140060531
0x14006052e  mov     cl, [rbp+NewIrql]
0x140060531  movzx   eax, word ptr [rdi+22h]
0x140060535  test    r13b, al
0x140060538  jnz     loc_1400605CD
0x14006053e  or      ax, r13w
0x140060542  mov     [rdi+22h], ax
0x140060546  mov     eax, [rdi+4]
0x140060549  test    eax, 0C00h
0x14006054e  jz      short loc_1400605C8
0x140060550  xor     r12d, r12d
0x140060553  mov     [rbp+arg_10], r12d
0x140060557  jmp     short loc_14006055C
0x140060559  xor     r12d, r12d
0x14006055c  bt      eax, 0Bh
0x140060560  jnb     short loc_140060573
0x140060562  mov     [rbp+arg_10], 1
0x140060569  and     eax, 0FFFFF3FFh
0x14006056e  mov     r15b, r12b
0x140060571  jmp     short loc_14006057E
0x140060573  btr     eax, 0Ah
0x140060577  mov     r15b, 1
0x14006057a  bts     eax, 0Ch
0x14006057e  mov     dl, cl; NewIrql
0x140060580  mov     [rdi+4], eax
0x140060583  mov     rcx, r14; SpinLock
0x140060586  call    cs:__imp_KeReleaseSpinLock
0x14006058d  nop     dword ptr [rax+rax+00h]
0x140060592  lea     rdx, [rbp+arg_10]
0x140060596  mov     rcx, rdi
0x140060599  call    WskProTLEVENTDisconnect
0x14006059e  test    r15b, r15b
0x1400605a1  jz      short loc_1400605E2
0x1400605a3  mov     rcx, r14; SpinLock
0x1400605a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400605ad  nop     dword ptr [rax+rax+00h]
0x1400605b2  btr     dword ptr [rdi+4], 0Ch
0x1400605b7  mov     r12b, 1
0x1400605ba  mov     cl, al
0x1400605bc  mov     [rbp+NewIrql], al
0x1400605bf  mov     eax, [rdi+4]
0x1400605c2  bt      eax, 0Bh
0x1400605c6  jb      short loc_140060559
0x1400605c8  test    r12b, r12b
0x1400605cb  jz      short loc_1400605DF
0x1400605cd  mov     dl, [rbp+NewIrql]; NewIrql
0x1400605d0  mov     rcx, r14; SpinLock
0x1400605d3  call    cs:__imp_KeReleaseSpinLock
0x1400605da  nop     dword ptr [rax+rax+00h]
0x1400605df  xor     r12d, r12d
0x1400605e2  test    rsi, rsi
0x1400605e5  jz      short loc_140060607
0x1400605e7  cmp     ebx, 103h
0x1400605ed  jz      short loc_140060607
0x1400605ef  xor     edx, edx; PriorityBoost
0x1400605f1  mov     [rsi+38h], r12
0x1400605f5  mov     rcx, rsi; Irp
0x1400605f8  mov     [rsi+30h], ebx
0x1400605fb  call    cs:__imp_IofCompleteRequest
0x140060602  nop     dword ptr [rax+rax+00h]
0x140060607  mov     eax, ebx
0x140060609  mov     rbx, [rsp+80h+arg_0]
0x140060611  add     rsp, 80h
0x140060618  pop     r15
0x14006061a  pop     r14
0x14006061c  pop     r13
0x14006061e  pop     r12
0x140060620  pop     rdi
0x140060621  pop     rsi
0x140060622  pop     rbp
0x140060623  retn
0x140060625  mov     r13d, 80h
0x14006062b  cmp     r14w, r13w
0x14006062f  jnz     short loc_140060679
0x140060631  lea     rcx, [rdi+10h]; SpinLock
0x140060635  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006063c  nop     dword ptr [rax+rax+00h]
0x140060641  mov     dl, al
0x140060643  mov     eax, 0FF7Fh
0x140060648  and     [rdi+22h], ax
0x14006064c  test    dword ptr [rdi+4], 300h
0x140060653  jz      loc_1400606E0
0x140060659  test    rsi, rsi
0x14006065c  jz      loc_1400607C3
0x140060662  mov     rax, [rsi+0B8h]
0x140060669  or      byte ptr [rax+3], 1
0x14006066d  mov     [rsi+0B0h], r13
0x140060674  jmp     loc_1400607DF
0x140060679  mov     r15d, 40h ; '@'
0x14006067f  cmp     r14w, r15w
0x140060683  jnz     short loc_1400606A8
0x140060685  lea     rcx, [rdi+10h]; SpinLock
0x140060689  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140060690  nop     dword ptr [rax+rax+00h]
0x140060695  mov     dl, al
0x140060697  mov     eax, 0FFBFh
0x14006069c  and     [rdi+22h], ax
0x1400606a0  mov     eax, [rdi+4]
0x1400606a3  test    r15b, al
0x1400606a6  jmp     short loc_1400606DA
0x1400606a8  mov     r15d, 10h
0x1400606ae  cmp     r14w, r15w
0x1400606b2  jnz     loc_140060270
0x1400606b8  lea     rcx, [rdi+10h]; SpinLock
0x1400606bc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400606c3  nop     dword ptr [rax+rax+00h]
0x1400606c8  mov     dl, al; NewIrql
0x1400606ca  mov     eax, 0FFEFh
0x1400606cf  and     [rdi+22h], ax
0x1400606d3  test    dword ptr [rdi+4], 2000h
  ... truncated ...
```
