# WskProControlCallbacks

- ea: `0x140060094`
- end: `0x140060653`
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
- `0x140060094`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14006045b`
- `ntoskrnl!IofCompleteRequest` at `0x14006045b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060152`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060181`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060218`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400602e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060378`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060406`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060495`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400604e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006051c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400605b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400605fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060152`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060181`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060218`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400602e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060378`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060406`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140060495`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400604e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006051c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400605b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400605fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060169`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060270`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006032d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400603e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060433`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060547`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060169`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060270`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006032d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400603e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060433`
- `ntoskrnl!KeReleaseSpinLock` at `0x140060547`

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
0x140060094  mov     [rsp-38h+arg_0], rbx
0x140060099  push    rbp
0x14006009a  push    rsi
0x14006009b  push    rdi
0x14006009c  push    r12
0x14006009e  push    r13
0x1400600a0  push    r14
0x1400600a2  push    r15
0x1400600a4  mov     rbp, rsp
0x1400600a7  sub     rsp, 80h
0x1400600ae  xor     r12d, r12d
0x1400600b1  mov     eax, edx
0x1400600b3  btr     eax, 1Fh
0x1400600b7  mov     rsi, r8
0x1400600ba  test    edx, edx
0x1400600bc  mov     rdi, rcx
0x1400600bf  mov     ebx, 103h
0x1400600c4  cmovns  eax, edx
0x1400600c7  movzx   r14d, ax
0x1400600cb  cmp     eax, r14d
0x1400600ce  jz      short loc_1400600DA
0x1400600d0  mov     ebx, 0C000000Dh
0x1400600d5  jmp     loc_140060442
0x1400600da  mov     rax, [rcx+0A0h]
0x1400600e1  test    [rax+4Ah], r14w
0x1400600e6  jz      short loc_1400600F2
0x1400600e8  mov     ebx, 0C0000010h
0x1400600ed  jmp     loc_140060442
0x1400600f2  movzx   ecx, word ptr [rcx]
0x1400600f5  shr     edx, 1Fh
0x1400600f8  sub     ecx, 0ACE0h
0x1400600fe  jz      short loc_1400600E8
0x140060100  sub     ecx, 1
0x140060103  jz      loc_140060558
0x140060109  sub     ecx, 1
0x14006010c  jz      loc_140060199
0x140060112  sub     ecx, 1
0x140060115  jz      short loc_140060126
0x140060117  cmp     ecx, 1
0x14006011a  jz      short loc_1400600E8
0x14006011c  mov     ebx, 0C0000008h
0x140060121  jmp     loc_140060442
0x140060126  cmp     byte ptr [rdi+2], 1
0x14006012a  jnz     loc_14006055E
0x140060130  mov     r15d, 100h
0x140060136  cmp     r14w, r15w
0x14006013a  jnz     short loc_1400600D0
0x14006013c  test    dl, dl
0x14006013e  jnz     short loc_14006017D
0x140060140  mov     rax, [rdi+48h]
0x140060144  test    rax, rax
0x140060147  jz      short loc_1400600E8
0x140060149  cmp     [rax], r12
0x14006014c  jz      short loc_1400600E8
0x14006014e  lea     rcx, [rdi+10h]; SpinLock
0x140060152  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140060159  nop     dword ptr [rax+rax+00h]
0x14006015e  or      [rdi+22h], r15w
0x140060163  mov     dl, al; NewIrql
0x140060165  lea     rcx, [rdi+10h]; SpinLock
0x140060169  call    cs:__imp_KeReleaseSpinLock
0x140060170  nop     dword ptr [rax+rax+00h]
0x140060175  mov     ebx, r12d
0x140060178  jmp     loc_140060442
0x14006017d  lea     rcx, [rdi+10h]; SpinLock
0x140060181  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140060188  nop     dword ptr [rax+rax+00h]
0x14006018d  mov     dl, al
0x14006018f  mov     eax, 0FEFFh
0x140060194  jmp     loc_140060610
0x140060199  cmp     byte ptr [rdi+2], 2
0x14006019d  jnz     loc_14006055E
0x1400601a3  test    dl, dl
0x1400601a5  jnz     loc_140060485
0x1400601ab  test    r14d, 0FFFFFF2Fh
0x1400601b2  jnz     loc_1400600D0
0x1400601b8  mov     rcx, [rdi+48h]
0x1400601bc  test    rcx, rcx
0x1400601bf  jz      loc_1400600E8
0x1400601c5  movzx   eax, r14w
0x1400601c9  mov     r15d, 40h ; '@'
0x1400601cf  and     ax, r15w
0x1400601d3  mov     [rbp+arg_18], ax
0x1400601d7  jz      short loc_1400601E2
0x1400601d9  cmp     [rcx], r12
0x1400601dc  jz      loc_1400600E8
0x1400601e2  mov     r13d, 80h
0x1400601e8  movzx   eax, r14w
0x1400601ec  and     ax, r13w
0x1400601f0  mov     [rbp+var_60], ax
0x1400601f4  jz      short loc_140060200
0x1400601f6  cmp     [rcx+8], r12
0x1400601fa  jz      loc_1400600E8
0x140060200  and     r14w, 10h
0x140060205  jz      short loc_140060211
0x140060207  cmp     [rcx+10h], r12
0x14006020b  jz      loc_1400600E8
0x140060211  lea     rcx, [rdi+10h]; SpinLock
0x140060215  mov     ebx, r12d
0x140060218  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006021f  nop     dword ptr [rax+rax+00h]
0x140060224  xor     ecx, ecx
0x140060226  mov     [rbp+NewIrql], al
0x140060229  mov     r12b, 1
0x14006022c  test    r14w, r14w
0x140060230  jz      loc_1400602CD
0x140060236  movzx   eax, word ptr [rdi+22h]
0x14006023a  lea     r14d, [rcx+10h]
0x14006023e  mov     word ptr [rbp+arg_10], ax
0x140060242  test    r14b, al
0x140060245  jnz     loc_1400602CD
0x14006024b  lea     r8d, [rcx+50h]; Size
0x14006024f  xor     edx, edx; Val
0x140060251  lea     rcx, [rbp+var_50]; void *
0x140060255  call    memset
0x14006025a  movzx   eax, word ptr [rbp+arg_10]
0x14006025e  mov     dl, [rbp+NewIrql]; NewIrql
0x140060261  or      ax, r14w
0x140060265  lea     r14, [rdi+10h]
0x140060269  mov     [rdi+22h], ax
0x14006026d  mov     rcx, r14; SpinLock
0x140060270  call    cs:__imp_KeReleaseSpinLock
0x140060277  nop     dword ptr [rax+rax+00h]
0x14006027c  xor     ecx, ecx
0x14006027e  mov     [rbp+var_48], rdi
0x140060282  mov     [rbp+var_40], ecx
0x140060285  lea     rax, AfdTLDontCareIOCompletion
0x14006028c  mov     [rbp+var_50], rax
0x140060290  lea     rdx, [rbp+var_50]
0x140060294  lea     rax, AfdTLSockOptEnable
0x14006029b  mov     [rbp+var_3C], 0FFFDh
0x1400602a2  mov     [rbp+var_30], rax
0x1400602a6  mov     r12b, cl
0x1400602a9  mov     rax, [rdi+38h]
0x1400602ad  mov     rcx, [rdi+28h]
0x1400602b1  mov     [rbp+var_38], 34h ; '4'
0x1400602b8  mov     [rbp+var_28], 4
0x1400602c0  mov     rax, [rax+8]
0x1400602c4  call    _guard_dispatch_icall
0x1400602c9  xor     ecx, ecx
0x1400602cb  jmp     short loc_1400602D1
0x1400602cd  lea     r14, [rdi+10h]
0x1400602d1  cmp     [rbp+arg_18], cx
0x1400602d5  jz      loc_140060362
0x1400602db  test    r12b, r12b
0x1400602de  jnz     short loc_1400602F5
0x1400602e0  mov     rcx, r14; SpinLock
0x1400602e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400602ea  nop     dword ptr [rax+rax+00h]
0x1400602ef  mov     [rbp+NewIrql], al
0x1400602f2  mov     r12b, 1
0x1400602f5  movzx   eax, word ptr [rdi+22h]
0x1400602f9  test    r15b, al
0x1400602fc  jnz     short loc_140060362
0x1400602fe  or      ax, r15w
0x140060302  mov     r15d, [rdi+4]
0x140060306  mov     [rdi+22h], ax
0x14006030a  test    r13b, r15b
0x14006030d  jz      short loc_140060362
0x14006030f  xor     edx, edx; Val
0x140060311  lea     rcx, [rbp+var_50]; void *
0x140060315  lea     r8d, [rdx+50h]; Size
0x140060319  call    memset
0x14006031e  mov     dl, [rbp+NewIrql]; NewIrql
0x140060321  btr     r15d, 7
0x140060326  mov     rcx, r14; SpinLock
0x140060329  mov     [rdi+4], r15d
0x14006032d  call    cs:__imp_KeReleaseSpinLock
0x140060334  nop     dword ptr [rax+rax+00h]
0x140060339  xor     ecx, ecx
0x14006033b  lea     rax, AfdTLDontCareIOCompletion
0x140060342  mov     [rbp+var_50], rax
0x140060346  lea     rdx, [rbp+var_50]
0x14006034a  mov     rax, [rdi+38h]
0x14006034e  mov     r12b, cl
0x140060351  mov     [rbp+var_48], rcx
0x140060355  mov     rcx, [rdi+28h]
0x140060359  mov     rax, [rax+20h]
0x14006035d  call    _guard_dispatch_icall
0x140060362  xor     r15d, r15d
0x140060365  cmp     [rbp+var_60], r15w
0x14006036a  jz      loc_140060428
0x140060370  test    r12b, r12b
0x140060373  jnz     short loc_14006038E
0x140060375  mov     rcx, r14; SpinLock
0x140060378  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006037f  nop     dword ptr [rax+rax+00h]
0x140060384  mov     cl, al
0x140060386  mov     [rbp+NewIrql], al
0x140060389  mov     r12b, 1
0x14006038c  jmp     short loc_140060391
0x14006038e  mov     cl, [rbp+NewIrql]
0x140060391  movzx   eax, word ptr [rdi+22h]
0x140060395  test    r13b, al
0x140060398  jnz     loc_14006042D
0x14006039e  or      ax, r13w
0x1400603a2  mov     [rdi+22h], ax
0x1400603a6  mov     eax, [rdi+4]
0x1400603a9  test    eax, 0C00h
0x1400603ae  jz      short loc_140060428
0x1400603b0  xor     r12d, r12d
0x1400603b3  mov     [rbp+arg_10], r12d
0x1400603b7  jmp     short loc_1400603BC
0x1400603b9  xor     r12d, r12d
0x1400603bc  bt      eax, 0Bh
0x1400603c0  jnb     short loc_1400603D3
0x1400603c2  mov     [rbp+arg_10], 1
0x1400603c9  and     eax, 0FFFFF3FFh
0x1400603ce  mov     r15b, r12b
0x1400603d1  jmp     short loc_1400603DE
0x1400603d3  btr     eax, 0Ah
0x1400603d7  mov     r15b, 1
0x1400603da  bts     eax, 0Ch
0x1400603de  mov     dl, cl; NewIrql
0x1400603e0  mov     [rdi+4], eax
0x1400603e3  mov     rcx, r14; SpinLock
0x1400603e6  call    cs:__imp_KeReleaseSpinLock
0x1400603ed  nop     dword ptr [rax+rax+00h]
0x1400603f2  lea     rdx, [rbp+arg_10]
0x1400603f6  mov     rcx, rdi
0x1400603f9  call    WskProTLEVENTDisconnect
0x1400603fe  test    r15b, r15b
0x140060401  jz      short loc_140060442
0x140060403  mov     rcx, r14; SpinLock
0x140060406  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006040d  nop     dword ptr [rax+rax+00h]
0x140060412  btr     dword ptr [rdi+4], 0Ch
0x140060417  mov     r12b, 1
0x14006041a  mov     cl, al
0x14006041c  mov     [rbp+NewIrql], al
0x14006041f  mov     eax, [rdi+4]
0x140060422  bt      eax, 0Bh
0x140060426  jb      short loc_1400603B9
0x140060428  test    r12b, r12b
0x14006042b  jz      short loc_14006043F
0x14006042d  mov     dl, [rbp+NewIrql]; NewIrql
0x140060430  mov     rcx, r14; SpinLock
0x140060433  call    cs:__imp_KeReleaseSpinLock
0x14006043a  nop     dword ptr [rax+rax+00h]
0x14006043f  xor     r12d, r12d
0x140060442  test    rsi, rsi
0x140060445  jz      short loc_140060467
0x140060447  cmp     ebx, 103h
0x14006044d  jz      short loc_140060467
0x14006044f  xor     edx, edx; PriorityBoost
0x140060451  mov     [rsi+38h], r12
0x140060455  mov     rcx, rsi; Irp
0x140060458  mov     [rsi+30h], ebx
0x14006045b  call    cs:__imp_IofCompleteRequest
0x140060462  nop     dword ptr [rax+rax+00h]
0x140060467  mov     eax, ebx
0x140060469  mov     rbx, [rsp+80h+arg_0]
0x140060471  add     rsp, 80h
0x140060478  pop     r15
0x14006047a  pop     r14
0x14006047c  pop     r13
0x14006047e  pop     r12
0x140060480  pop     rdi
0x140060481  pop     rsi
0x140060482  pop     rbp
0x140060483  retn
0x140060485  mov     r13d, 80h
0x14006048b  cmp     r14w, r13w
0x14006048f  jnz     short loc_1400604D9
0x140060491  lea     rcx, [rdi+10h]; SpinLock
0x140060495  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006049c  nop     dword ptr [rax+rax+00h]
0x1400604a1  mov     dl, al
0x1400604a3  mov     eax, 0FF7Fh
0x1400604a8  and     [rdi+22h], ax
0x1400604ac  test    dword ptr [rdi+4], 300h
0x1400604b3  jz      loc_140060540
0x1400604b9  test    rsi, rsi
0x1400604bc  jz      loc_140060623
0x1400604c2  mov     rax, [rsi+0B8h]
0x1400604c9  or      byte ptr [rax+3], 1
0x1400604cd  mov     [rsi+0B0h], r13
0x1400604d4  jmp     loc_14006063F
0x1400604d9  mov     r15d, 40h ; '@'
0x1400604df  cmp     r14w, r15w
0x1400604e3  jnz     short loc_140060508
0x1400604e5  lea     rcx, [rdi+10h]; SpinLock
0x1400604e9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400604f0  nop     dword ptr [rax+rax+00h]
0x1400604f5  mov     dl, al
0x1400604f7  mov     eax, 0FFBFh
0x1400604fc  and     [rdi+22h], ax
0x140060500  mov     eax, [rdi+4]
0x140060503  test    r15b, al
0x140060506  jmp     short loc_14006053A
0x140060508  mov     r15d, 10h
0x14006050e  cmp     r14w, r15w
0x140060512  jnz     loc_1400600D0
0x140060518  lea     rcx, [rdi+10h]; SpinLock
0x14006051c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140060523  nop     dword ptr [rax+rax+00h]
0x140060528  mov     dl, al; NewIrql
0x14006052a  mov     eax, 0FFEFh
0x14006052f  and     [rdi+22h], ax
0x140060533  test    dword ptr [rdi+4], 2000h
  ... truncated ...
```
