# ChangeGroup::CalculateFFKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl(ISyncKnowledge *,ulong)

- ea: `0x180078354`
- end: `0x18007856a`
- name: `?CalculateFFKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl@ChangeGroup@@AEAAJPEAUISyncKnowledge@@K@Z`
- size: `534`
- prototype: `__int64 __fastcall(ChangeGroup *__hidden this, struct ISyncKnowledge *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180078df0`

## callees

- `0x18000a0f0`
- `0x180077ed8`
- `0x180078354`
- `0x18009323e`
- `0x180094010`

## pseudocode

```c
__int64 __fastcall ChangeGroup::CalculateFFKWithPrerequisiteComplementedByDKWithMoveinsExcludedImpl(
        ChangeGroup *this,
        struct ISyncKnowledge *a2,
        unsigned int a3)
{
  __int64 v3; // rax
  __int64 v5; // rbp
  __int64 v7; // rbx
  int v8; // esi
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  BOOL v13; // ecx
  unsigned int *v14; // rax
  unsigned int v15; // r14d
  __int64 v16; // rax
  void (*v17)(void); // rax
  __int64 v18; // rbp
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v24; // [rsp+70h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 14);
  v5 = a3;
  v7 = a3;
  if ( v3 )
  {
    if ( *(_QWORD *)(v3 + 8LL * a3) )
    {
      v8 = -2147217379;
LABEL_32:
      v21 = *((_QWORD *)this + 14);
      if ( v21 )
      {
        v22 = *(_QWORD *)(v21 + 8 * v7);
        if ( v22 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v7) = 0;
        }
      }
      return (unsigned int)v8;
    }
  }
  else
  {
    v9 = SeAlloc(saturated_mul(*((unsigned int *)this + 20), 8u));
    *((_QWORD *)this + 14) = v9;
    if ( !v9 )
    {
      v8 = -2147024882;
      goto LABEL_32;
    }
    memset_0(v9, 0, 8LL * *((unsigned int *)this + 20));
  }
  v10 = *((_QWORD *)this + 12);
  if ( !v10 || (v8 = 0, !*(_QWORD *)(v10 + 8 * v5)) )
  {
    v8 = ChangeGroup::CalculateFFKComplementedByDKImpl(this, a2, v5);
    if ( v8 )
      goto LABEL_32;
  }
  v11 = *((_QWORD *)this + 8);
  if ( v11 )
  {
    if ( v11 != *((_QWORD *)this + 5) )
    {
      v13 = 1;
      goto LABEL_17;
    }
    v13 = 0;
  }
  else
  {
    v12 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, _QWORD))a2->lpVtbl->ContainsKnowledge)(
            a2,
            *((_QWORD *)this + 4));
    v8 = 0;
    if ( v12 != 1 )
      v8 = v12;
    v13 = v12 == 1;
  }
  if ( v8 )
    goto LABEL_32;
LABEL_17:
  v14 = (unsigned int *)*((_QWORD *)this + 24);
  v15 = 0;
  if ( v14 )
    v15 = *v14;
  v16 = *((_QWORD *)this + 12);
  if ( v13 )
  {
    v24 = 0;
    v8 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v16 + 8 * v5))(
           *(_QWORD *)(v16 + 8 * v5),
           &GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8,
           &v24);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ISyncKnowledge *, __int64))(*(_QWORD *)v24 + 288LL))(
             v24,
             *((_QWORD *)this + 4),
             a2,
             *((_QWORD *)this + 14) + 8 * v5);
      v17 = *(void (**)(void))(*(_QWORD *)v24 + 16LL);
LABEL_25:
      v17();
    }
  }
  else
  {
    if ( !v15 )
    {
      *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v5) = *(_QWORD *)(v16 + 8 * v5);
      v17 = *(void (**)(void))(**(_QWORD **)(*((_QWORD *)this + 12) + 8 * v5) + 8LL);
      goto LABEL_25;
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v16 + 8 * v5) + 80LL))(
           *(_QWORD *)(v16 + 8 * v5),
           *((_QWORD *)this + 14) + 8 * v5);
  }
  v18 = 0;
  if ( v8 )
    goto LABEL_32;
  do
  {
    if ( (unsigned int)v18 >= v15 )
      break;
    v19 = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v7);
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 136LL))(
            v19,
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 24) + 16LL) + 8 * v18));
    v18 = (unsigned int)(v18 + 1);
    v8 = v20;
  }
  while ( !v20 );
  if ( v8 )
    goto LABEL_32;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180078354  push    rbx
0x180078356  push    rbp
0x180078357  push    rsi
0x180078358  push    rdi
0x180078359  push    r14
0x18007835b  push    r15
0x18007835d  sub     rsp, 38h
0x180078361  mov     rax, [rcx+70h]
0x180078365  mov     r15, rdx
0x180078368  mov     ebp, r8d
0x18007836b  mov     rdi, rcx
0x18007836e  mov     ebx, r8d
0x180078371  test    rax, rax
0x180078374  jz      short loc_180078387
0x180078376  cmp     qword ptr [rax+rbp*8], 0
0x18007837b  jz      short loc_1800783C4
0x18007837d  mov     esi, 8004101Dh
0x180078382  jmp     loc_180078531
0x180078387  mov     ecx, [rcx+50h]
0x18007838a  mov     eax, 8
0x18007838f  mul     rcx
0x180078392  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180078399  cmovb   rax, rcx
0x18007839d  mov     rcx, rax; unsigned __int64
0x1800783a0  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800783a5  mov     [rdi+70h], rax
0x1800783a9  test    rax, rax
0x1800783ac  jz      loc_18007852C
0x1800783b2  mov     r8d, [rdi+50h]
0x1800783b6  xor     edx, edx; Val
0x1800783b8  shl     r8, 3; Size
0x1800783bc  mov     rcx, rax; void *
0x1800783bf  call    memset_0
0x1800783c4  mov     rax, [rdi+60h]
0x1800783c8  test    rax, rax
0x1800783cb  jz      short loc_1800783D5
0x1800783cd  xor     esi, esi
0x1800783cf  cmp     [rax+rbp*8], rsi
0x1800783d3  jnz     short loc_1800783ED
0x1800783d5  mov     r8d, ebp; unsigned int
0x1800783d8  mov     rdx, r15; struct ISyncKnowledge *
0x1800783db  mov     rcx, rdi; this
0x1800783de  call    ?CalculateFFKComplementedByDKImpl@ChangeGroup@@AEAAJPEAUISyncKnowledge@@K@Z; ChangeGroup::CalculateFFKComplementedByDKImpl(ISyncKnowledge *,ulong)
0x1800783e3  mov     esi, eax
0x1800783e5  test    eax, eax
0x1800783e7  jnz     loc_180078531
0x1800783ed  mov     rcx, [rdi+40h]
0x1800783f1  test    rcx, rcx
0x1800783f4  jnz     short loc_18007841E
0x1800783f6  mov     rax, [r15]
0x1800783f9  mov     rcx, r15
0x1800783fc  mov     rdx, [rdi+20h]
0x180078400  mov     rax, [rax+98h]
0x180078407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007840c  xor     esi, esi
0x18007840e  cmp     eax, 1
0x180078411  cmovnz  esi, eax
0x180078414  xor     ecx, ecx
0x180078416  cmp     eax, 1
0x180078419  setz    cl
0x18007841c  jmp     short loc_18007842D
0x18007841e  cmp     rcx, [rdi+28h]
0x180078422  jz      short loc_18007842B
0x180078424  mov     ecx, 1
0x180078429  jmp     short loc_180078435
0x18007842b  xor     ecx, ecx
0x18007842d  test    esi, esi
0x18007842f  jnz     loc_180078531
0x180078435  mov     rax, [rdi+0C0h]
0x18007843c  xor     r14d, r14d
0x18007843f  test    rax, rax
0x180078442  jz      short loc_180078447
0x180078444  mov     r14d, [rax]
0x180078447  mov     rax, [rdi+60h]
0x18007844b  test    ecx, ecx
0x18007844d  jz      short loc_1800784AC
0x18007844f  mov     [rsp+68h+arg_0], 0
0x180078458  lea     r8, [rsp+68h+arg_0]
0x18007845d  mov     rcx, [rax+rbp*8]
0x180078461  lea     rdx, _GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8
0x180078468  mov     rax, [rcx]
0x18007846b  mov     rax, [rax]
0x18007846e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078473  mov     esi, eax
0x180078475  test    eax, eax
0x180078477  js      short loc_1800784ED
0x180078479  mov     rax, [rdi+70h]
0x18007847d  mov     r8, r15
0x180078480  mov     rcx, [rsp+68h+arg_0]
0x180078485  lea     r9, [rax+rbp*8]
0x180078489  mov     rdx, [rcx]
0x18007848c  mov     rax, [rdx+120h]
0x180078493  mov     rdx, [rdi+20h]
0x180078497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007849c  mov     rcx, [rsp+68h+arg_0]
0x1800784a1  mov     esi, eax
0x1800784a3  mov     rax, [rcx]
0x1800784a6  mov     rax, [rax+10h]
0x1800784aa  jmp     short loc_1800784E8
0x1800784ac  test    r14d, r14d
0x1800784af  jz      short loc_1800784CD
0x1800784b1  mov     rcx, [rax+rbp*8]
0x1800784b5  mov     rax, [rdi+70h]
0x1800784b9  mov     r8, [rcx]
0x1800784bc  lea     rdx, [rax+rbp*8]
0x1800784c0  mov     rax, [r8+50h]
0x1800784c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784c9  mov     esi, eax
0x1800784cb  jmp     short loc_1800784ED
0x1800784cd  mov     rax, [rax+rbp*8]
0x1800784d1  mov     rcx, [rdi+70h]
0x1800784d5  mov     [rcx+rbp*8], rax
0x1800784d9  mov     rax, [rdi+60h]
0x1800784dd  mov     rcx, [rax+rbp*8]
0x1800784e1  mov     rax, [rcx]
0x1800784e4  mov     rax, [rax+8]
0x1800784e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784ed  xor     ebp, ebp
0x1800784ef  test    esi, esi
0x1800784f1  jnz     short loc_180078531
0x1800784f3  cmp     ebp, r14d
0x1800784f6  jnb     short loc_180078526
0x1800784f8  mov     rax, [rdi+70h]
0x1800784fc  mov     rcx, [rax+rbx*8]
0x180078500  mov     rax, [rdi+0C0h]
0x180078507  mov     r8, [rcx]
0x18007850a  mov     rdx, [rax+10h]
0x18007850e  mov     rax, [r8+88h]
0x180078515  mov     rdx, [rdx+rbp*8]
0x180078519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007851e  inc     ebp
0x180078520  mov     esi, eax
0x180078522  test    eax, eax
0x180078524  jz      short loc_1800784F3
0x180078526  test    esi, esi
0x180078528  jz      short loc_18007855B
0x18007852a  jmp     short loc_180078531
0x18007852c  mov     esi, 8007000Eh
0x180078531  mov     rcx, [rdi+70h]
0x180078535  test    rcx, rcx
0x180078538  jz      short loc_18007855B
0x18007853a  mov     rcx, [rcx+rbx*8]
0x18007853e  test    rcx, rcx
0x180078541  jz      short loc_18007855B
0x180078543  mov     rax, [rcx]
0x180078546  mov     rax, [rax+10h]
0x18007854a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007854f  mov     rax, [rdi+70h]
0x180078553  mov     qword ptr [rax+rbx*8], 0
0x18007855b  mov     eax, esi
0x18007855d  add     rsp, 38h
0x180078561  pop     r15
0x180078563  pop     r14
0x180078565  pop     rdi
0x180078566  pop     rsi
0x180078567  pop     rbp
0x180078568  pop     rbx
0x180078569  retn
```
