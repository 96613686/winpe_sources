# CILogRead::ReadNext(_ULARGE_INTEGER *,ulong *,ushort *)

- ea: `0x180002ea0`
- end: `0x180003243`
- name: `?ReadNext@CILogRead@@UEAAJPEAT_ULARGE_INTEGER@@PEAKPEAG@Z`
- size: `931`
- prototype: `__int64 __fastcall(CILogRead *__hidden this, union _ULARGE_INTEGER *, unsigned int *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x18000130c`
- `0x180002ea0`
- `0x180009178`
- `0x18000ce68`
- `0x18000cec8`
- `0x18000d160`
- `0x18001280a`

## pseudocode

```c
__int64 __fastcall CILogRead::ReadNext(
        CILogRead *this,
        union _ULARGE_INTEGER *a2,
        unsigned int *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rdi
  unsigned int *v5; // r14
  union _ULARGE_INTEGER *v6; // r15
  char *v7; // r9
  char *v8; // rsi
  __int64 v9; // rcx
  unsigned __int64 v10; // rax
  union _ULARGE_INTEGER *v11; // r10
  unsigned __int64 v12; // r12
  ulong v13; // edx
  unsigned int v14; // r8d
  unsigned int v15; // r13d
  void *v17; // rcx
  unsigned __int64 v18; // rax
  __int64 v19; // rax
  void *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  struct _LOGRECHEADER *v23; // rcx
  union _ULARGE_INTEGER *v24; // rdx
  void *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  ulong v29; // [rsp+40h] [rbp-88h]
  unsigned int v30; // [rsp+44h] [rbp-84h] BYREF
  int v31; // [rsp+48h] [rbp-80h]
  int v32; // [rsp+4Ch] [rbp-7Ch]
  unsigned int v33; // [rsp+50h] [rbp-78h]
  char *v34; // [rsp+58h] [rbp-70h]
  int v35; // [rsp+60h] [rbp-68h] BYREF
  struct _LOGRECHEADER *v36; // [rsp+68h] [rbp-60h] BYREF
  char *v37; // [rsp+70h] [rbp-58h]
  char *v38; // [rsp+78h] [rbp-50h]
  ulong v39; // [rsp+80h] [rbp-48h] BYREF
  union _ULARGE_INTEGER *v40; // [rsp+88h] [rbp-40h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v7 = (char *)this + 16;
  v34 = (char *)this + 16;
  if ( !*(_QWORD *)(*((_QWORD *)this + 2) + 392LL) )
    return 2147549183LL;
  v8 = (char *)this + 8;
  v9 = *((_QWORD *)this + 1);
  if ( !v9 )
    return 2147549183LL;
  if ( !a3 )
    return 2147942487LL;
  v10 = *(_QWORD *)(v9 + 544);
  if ( !v10 )
    goto LABEL_48;
  v37 = v7;
  v38 = v8;
  v11 = a2;
  v40 = a2;
  v12 = HIDWORD(v10);
  v13 = 0;
  v29 = 0;
  v32 = 0;
  v14 = 1;
  if ( !*(_DWORD *)(v9 + 552) )
  {
LABEL_48:
    *v5 = 0;
    if ( v6 )
      v6->QuadPart = 0;
    if ( v4 )
      *v4 = 0;
    return 2147942487LL;
  }
  while ( !v32 && v14 )
  {
    v15 = *(_DWORD *)(*(_QWORD *)v8 + 572LL);
    v33 = v15;
    if ( v15 < (unsigned int)v10 )
    {
      LODWORD(v12) = v12 + 1;
      **(_DWORD **)(*(_QWORD *)v7 + 392LL) = v12;
    }
    v31 = v12;
    if ( !v15 )
    {
      *v5 = 0;
      if ( v6 )
        v11->QuadPart = 0;
      if ( v4 )
        *v4 = 0;
      return 2147487787LL;
    }
    if ( *(_QWORD *)(*(_QWORD *)v8 + 544LL) )
    {
      try
      {
        if ( (unsigned int)CReadMap::ReleaseAndSet((CReadMap *)(*(_QWORD *)v8 + 352LL), (unsigned int)v12, v15) )
          CLogState::AttemptRead(*(CLogState **)(*(_QWORD *)v34 + 400LL), (struct CReadMap *)(*(_QWORD *)v8 + 352LL), 0);
      }
      catch ( long v35 )
      {
        *a3 = 0;
        if ( a4 )
          *a4 = 0;
        v26 = *((_QWORD *)this + 1);
        if ( *(_QWORD *)(v26 + 584) )
          operator delete(*(void **)(v26 + 584));
        *(_QWORD *)(*((_QWORD *)this + 1) + 544LL) = 0;
        CReadMap::ReleaseAndSet((CReadMap *)(*((_QWORD *)this + 1) + 352LL), 0, 0);
        v27 = v35;
        if ( v35 == -2147479510 )
          v27 = -2147479509;
        v35 = v27;
        v29 = v27;
        v7 = v37;
        v13 = v27;
        v15 = v33;
        v8 = v38;
        v34 = v37;
        LODWORD(v12) = v31;
        v14 = 0;
        v6 = a2;
        v5 = a3;
        v4 = a4;
        goto LABEL_41;
      }
      catch ( ulong v39 )
      {
        *a3 = 0;
        if ( a4 )
          *a4 = 0;
        v28 = *((_QWORD *)this + 1);
        if ( *(_QWORD *)(v28 + 584) )
          operator delete(*(void **)(v28 + 584));
        *(_QWORD *)(*((_QWORD *)this + 1) + 544LL) = 0;
        CReadMap::ReleaseAndSet((CReadMap *)(*((_QWORD *)this + 1) + 352LL), 0, 0);
        v29 = v39;
        v7 = v37;
        v13 = v39;
        v15 = v33;
        v8 = v38;
        v34 = v37;
        LODWORD(v12) = v31;
        v14 = 0;
        v6 = a2;
        v5 = a3;
        v4 = a4;
        goto LABEL_41;
      }
    }
    *(_DWORD *)(*(_QWORD *)v8 + 576LL) = CReadMap::GetBufCount((CReadMap *)(*(_QWORD *)v8 + 352LL));
    v30 = 0;
    v17 = *(void **)(*(_QWORD *)v8 + 584LL);
    if ( v17 )
      operator delete(v17);
    v18 = 16LL * *(unsigned int *)(*(_QWORD *)v8 + 576LL);
    if ( !is_mul_ok(*(unsigned int *)(*(_QWORD *)v8 + 576LL), 0x10u) )
      v18 = -1;
    *(_QWORD *)(*(_QWORD *)v8 + 584LL) = operator new[](v18);
    v19 = *(_QWORD *)v8;
    v20 = *(void **)(*(_QWORD *)v8 + 584LL);
    if ( !v20 )
    {
      *(_QWORD *)(v19 + 544) = 0;
      CReadMap::ReleaseAndSet((CReadMap *)(*(_QWORD *)v8 + 352LL), 0, 0);
      *v5 = 0;
      if ( v4 )
        *v4 = 0;
      return 2147942414LL;
    }
    memset_0(v20, 0, 16LL * *(unsigned int *)(v19 + 576));
    v36 = 0;
    v30 = CReadMap::ReadRecord(
            (CReadMap *)(*(_QWORD *)v8 + 352LL),
            v12,
            *(_DWORD *)(*(_QWORD *)v8 + 576LL),
            &v30,
            &v36,
            *(struct _LOGREC **)(*(_QWORD *)v8 + 584LL),
            0,
            0);
    v21 = *(_QWORD *)v8;
    if ( v30 )
    {
      *(_DWORD *)(v21 + 544) = v15;
      *(_DWORD *)(v21 + 548) = v12;
      v22 = *(_QWORD *)v8;
      v23 = v36;
      *(_OWORD *)(v22 + 552) = *(_OWORD *)v36;
      *(_QWORD *)(v22 + 568) = *((_QWORD *)v23 + 2);
      v24 = *(union _ULARGE_INTEGER **)v8;
      if ( *((_DWORD *)v23 + 4) == *(_DWORD *)(*(_QWORD *)v8 + 328LL) && *((_WORD *)v23 + 7) == 1 )
      {
        v32 = 1;
        if ( v6 )
          *v6 = v24[68];
        *v5 = *((_DWORD *)v23 + 2);
        if ( v4 )
          *v4 = *((_WORD *)v23 + 6);
      }
    }
    else
    {
      *(_QWORD *)(v21 + 544) = 0;
      CReadMap::ReleaseAndSet((CReadMap *)(*(_QWORD *)v8 + 352LL), 0, 0);
      *v5 = 0;
      if ( v4 )
        *v4 = 0;
      v25 = *(void **)(*(_QWORD *)v8 + 584LL);
      if ( v25 )
        operator delete(v25);
      v29 = -2147479509;
    }
    v13 = v29;
    v14 = v30;
    v7 = v34;
LABEL_41:
    LODWORD(v10) = v15;
    v11 = v40;
  }
  if ( v13 )
  {
    *v5 = 0;
    if ( v6 )
      v11->QuadPart = 0;
    if ( v4 )
      *v4 = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180002ea0  mov     rax, rsp
0x180002ea3  mov     [rax+20h], r9
0x180002ea7  mov     [rax+18h], r8
0x180002eab  mov     [rax+10h], rdx
0x180002eaf  mov     [rax+8], rcx
0x180002eb3  push    rbx
0x180002eb4  push    rsi
0x180002eb5  push    rdi
0x180002eb6  push    r12
0x180002eb8  push    r13
0x180002eba  push    r14
0x180002ebc  push    r15
0x180002ebe  sub     rsp, 90h
0x180002ec5  mov     rdi, r9
0x180002ec8  mov     r14, r8
0x180002ecb  mov     r15, rdx
0x180002ece  lea     r9, [rcx+10h]
0x180002ed2  mov     [rsp+0C8h+var_70], r9
0x180002ed7  mov     rax, [r9]
0x180002eda  xor     ebx, ebx
0x180002edc  cmp     [rax+188h], rbx
0x180002ee3  jz      loc_18000322A
0x180002ee9  lea     rsi, [rcx+8]
0x180002eed  mov     rcx, [rsi]
0x180002ef0  test    rcx, rcx
0x180002ef3  jz      loc_18000322A
0x180002ef9  test    r8, r8
0x180002efc  jz      loc_180003223
0x180002f02  mov     rax, [rcx+220h]
0x180002f09  test    rax, rax
0x180002f0c  jz      loc_180003210
0x180002f12  mov     [rsp+0C8h+var_58], r9
0x180002f17  mov     [rsp+0C8h+var_50], rsi
0x180002f1c  mov     r10, rdx
0x180002f1f  mov     [rsp+0C8h+var_40], rdx
0x180002f27  mov     r12, rax
0x180002f2a  shr     r12, 20h
0x180002f2e  mov     edx, ebx
0x180002f30  mov     [rsp+0C8h+var_88], ebx
0x180002f34  mov     [rsp+0C8h+var_7C], ebx
0x180002f38  lea     r8d, [rbx+1]
0x180002f3c  cmp     [rcx+228h], ebx
0x180002f42  jz      loc_180003210
0x180002f48  cmp     [rsp+0C8h+var_7C], ebx
0x180002f4c  jnz     loc_1800031F5
0x180002f52  test    r8d, r8d
0x180002f55  jz      loc_1800031F5
0x180002f5b  mov     rcx, [rsi]
0x180002f5e  mov     r13d, [rcx+23Ch]
0x180002f65  mov     [rsp+0C8h+var_78], r13d
0x180002f6a  cmp     r13d, eax
0x180002f6d  jnb     short loc_180002F7F
0x180002f6f  inc     r12d
0x180002f72  mov     rax, [r9]
0x180002f75  mov     rcx, [rax+188h]
0x180002f7c  mov     [rcx], r12d
0x180002f7f  mov     [rsp+0C8h+var_80], r12d
0x180002f84  test    r13d, r13d
0x180002f87  jnz     short loc_180002FA6
0x180002f89  mov     [r14], ebx
0x180002f8c  test    r15, r15
0x180002f8f  jz      short loc_180002F94
0x180002f91  mov     [r10], rbx
0x180002f94  test    rdi, rdi
0x180002f97  jz      short loc_180002F9C
0x180002f99  mov     [rdi], bx
0x180002f9c  mov     eax, 8000102Bh
0x180002fa1  jmp     loc_18000322F
0x180002fa6  mov     rcx, [rsi]
0x180002fa9  cmp     [rcx+220h], rbx
0x180002fb0  jz      short loc_180002FE9
0x180002fb2  add     rcx, 160h; this
0x180002fb9  mov     r8d, r13d; unsigned int
0x180002fbc  mov     edx, r12d; unsigned int
0x180002fbf  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180002fc4  test    eax, eax
0x180002fc6  jz      short loc_180002FE9
0x180002fc8  mov     rdx, [rsi]
0x180002fcb  add     rdx, 160h; struct CReadMap *
0x180002fd2  mov     rcx, [rsp+0C8h+var_70]
0x180002fd7  mov     rcx, [rcx]
0x180002fda  xor     r8d, r8d; int
0x180002fdd  mov     rcx, [rcx+190h]; this
0x180002fe4  call    ?AttemptRead@CLogState@@QEAAXAEAVCReadMap@@H@Z; CLogState::AttemptRead(CReadMap &,int)
0x180002fe9  mov     rcx, [rsi]
0x180002fec  add     rcx, 160h; this
0x180002ff3  call    ?GetBufCount@CReadMap@@QEAAKXZ; CReadMap::GetBufCount(void)
0x180002ff8  mov     ecx, eax
0x180002ffa  mov     rax, [rsi]
0x180002ffd  mov     [rax+240h], ecx
0x180003003  mov     [rsp+0C8h+var_84], ebx
0x180003007  mov     rax, [rsi]
0x18000300a  mov     rcx, [rax+248h]; Block
0x180003011  test    rcx, rcx
0x180003014  jz      short loc_18000301B
0x180003016  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000301b  mov     rax, [rsi]
0x18000301e  mov     ecx, [rax+240h]
0x180003024  mov     eax, 10h
0x180003029  mul     rcx
0x18000302c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003033  cmovb   rax, rcx
0x180003037  mov     rcx, rax; unsigned __int64
0x18000303a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000303f  mov     rcx, rax
0x180003042  mov     rax, [rsi]
0x180003045  mov     [rax+248h], rcx
0x18000304c  mov     rax, [rsi]
0x18000304f  mov     rcx, [rax+248h]; void *
0x180003056  xor     edx, edx; unsigned int
0x180003058  test    rcx, rcx
0x18000305b  jnz     short loc_18000308B
0x18000305d  mov     [rax+220h], rbx
0x180003064  mov     rcx, [rsi]
0x180003067  add     rcx, 160h; this
0x18000306e  xor     r8d, r8d; unsigned int
0x180003071  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180003076  mov     [r14], ebx
0x180003079  test    rdi, rdi
0x18000307c  jz      short loc_180003081
0x18000307e  mov     [rdi], bx
0x180003081  mov     eax, 8007000Eh
0x180003086  jmp     loc_18000322F
0x18000308b  mov     r8d, [rax+240h]
0x180003092  shl     r8, 4; Size
0x180003096  call    memset_0
0x18000309b  mov     [rsp+0C8h+var_60], rbx
0x1800030a0  mov     r8, [rsi]
0x1800030a3  lea     rcx, [r8+160h]; this
0x1800030aa  mov     [rsp+0C8h+var_90], rbx; unsigned int *
0x1800030af  mov     [rsp+0C8h+var_98], ebx; int
0x1800030b3  mov     rax, [r8+248h]
0x1800030ba  mov     [rsp+0C8h+var_A0], rax; struct _LOGREC *
0x1800030bf  lea     rax, [rsp+0C8h+var_60]
0x1800030c4  mov     [rsp+0C8h+var_A8], rax; struct _LOGRECHEADER **
0x1800030c9  lea     r9, [rsp+0C8h+var_84]; unsigned int *
0x1800030ce  mov     r8d, [r8+240h]; unsigned int
0x1800030d5  mov     edx, r12d; unsigned int
0x1800030d8  call    ?ReadRecord@CReadMap@@QEAAHKKPEAKPEAPEAU_LOGRECHEADER@@PEAU_LOGREC@@H0@Z; CReadMap::ReadRecord(ulong,ulong,ulong *,_LOGRECHEADER * *,_LOGREC *,int,ulong *)
0x1800030dd  mov     [rsp+0C8h+var_84], eax
0x1800030e1  mov     rcx, [rsi]
0x1800030e4  test    eax, eax
0x1800030e6  jz      short loc_180003155
0x1800030e8  mov     [rcx+220h], r13d
0x1800030ef  mov     [rcx+224h], r12d
0x1800030f6  mov     rax, [rsi]
0x1800030f9  mov     rcx, [rsp+0C8h+var_60]
0x1800030fe  movups  xmm0, xmmword ptr [rcx]
0x180003101  movups  xmmword ptr [rax+228h], xmm0
0x180003108  movsd   xmm1, qword ptr [rcx+10h]
0x18000310d  movsd   qword ptr [rax+238h], xmm1
0x180003115  mov     rdx, [rsi]
0x180003118  mov     eax, [rdx+148h]
0x18000311e  cmp     [rcx+10h], eax
0x180003121  jnz     short loc_180003197
0x180003123  mov     eax, 1
0x180003128  cmp     [rcx+0Eh], ax
0x18000312c  jnz     short loc_180003197
0x18000312e  mov     [rsp+0C8h+var_7C], eax
0x180003132  test    r15, r15
0x180003135  jz      short loc_180003141
0x180003137  mov     rax, [rdx+220h]
0x18000313e  mov     [r15], rax
0x180003141  mov     eax, [rcx+8]
0x180003144  mov     [r14], eax
0x180003147  test    rdi, rdi
0x18000314a  jz      short loc_180003197
0x18000314c  movzx   eax, word ptr [rcx+0Ch]
0x180003150  mov     [rdi], ax
0x180003153  jmp     short loc_180003197
0x180003155  mov     [rcx+220h], rbx
0x18000315c  mov     rcx, [rsi]
0x18000315f  add     rcx, 160h; this
0x180003166  xor     r8d, r8d; unsigned int
0x180003169  xor     edx, edx; unsigned int
0x18000316b  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180003170  mov     [r14], ebx
0x180003173  test    rdi, rdi
0x180003176  jz      short loc_18000317B
0x180003178  mov     [rdi], bx
0x18000317b  mov     rax, [rsi]
0x18000317e  mov     rcx, [rax+248h]; Block
0x180003185  test    rcx, rcx
0x180003188  jz      short loc_18000318F
0x18000318a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000318f  mov     [rsp+0C8h+var_88], 8000102Bh
0x180003197  mov     edx, [rsp+0C8h+var_88]
0x18000319b  mov     r8d, [rsp+0C8h+var_84]
0x1800031a0  mov     r9, [rsp+0C8h+var_70]
0x1800031a5  jmp     short loc_1800031E5
0x1800031a7  mov     r9, [rsp+0C8h+var_58]
0x1800031ac  xor     ebx, ebx
0x1800031ae  mov     edx, [rsp+0C8h+var_88]
0x1800031b2  mov     r13d, [rsp+0C8h+var_78]
0x1800031b7  mov     rsi, [rsp+0C8h+var_50]
0x1800031bc  mov     [rsp+0C8h+var_70], r9
0x1800031c1  mov     r12d, [rsp+0C8h+var_80]
0x1800031c6  mov     r8d, ebx
0x1800031c9  mov     [rsp+0C8h+var_88], edx
0x1800031cd  mov     r15, [rsp+0C8h+arg_8]
0x1800031d5  mov     r14, [rsp+0C8h+arg_10]
0x1800031dd  mov     rdi, [rsp+0C8h+arg_18]
0x1800031e5  mov     eax, r13d
0x1800031e8  mov     r10, [rsp+0C8h+var_40]
0x1800031f0  jmp     loc_180002F48
0x1800031f5  test    edx, edx
0x1800031f7  jz      short loc_18000320C
0x1800031f9  mov     [r14], ebx
0x1800031fc  test    r15, r15
0x1800031ff  jz      short loc_180003204
0x180003201  mov     [r10], rbx
0x180003204  test    rdi, rdi
0x180003207  jz      short loc_18000320C
0x180003209  mov     [rdi], bx
0x18000320c  mov     eax, edx
0x18000320e  jmp     short loc_18000322F
0x180003210  mov     [r14], ebx
0x180003213  test    r15, r15
0x180003216  jz      short loc_18000321B
0x180003218  mov     [r15], rbx
0x18000321b  test    rdi, rdi
0x18000321e  jz      short loc_180003223
0x180003220  mov     [rdi], bx
0x180003223  mov     eax, 80070057h
0x180003228  jmp     short loc_18000322F
0x18000322a  mov     eax, 8000FFFFh
0x18000322f  add     rsp, 90h
0x180003236  pop     r15
0x180003238  pop     r14
0x18000323a  pop     r13
0x18000323c  pop     r12
0x18000323e  pop     rdi
0x18000323f  pop     rsi
0x180003240  pop     rbx
0x180003241  retn
```
