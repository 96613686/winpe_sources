# ChangeGroup::CalculateFFKWithPrerequisiteComplementedByDK(ISyncKnowledge *,ulong)

- ea: `0x180078174`
- end: `0x18007834e`
- name: `?CalculateFFKWithPrerequisiteComplementedByDK@ChangeGroup@@AEAAJPEAUISyncKnowledge@@K@Z`
- size: `474`
- prototype: `__int64 __fastcall(ChangeGroup *__hidden this, struct ISyncKnowledge *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180078cf4`
- `0x180078df0`

## callees

- `0x18000a0f0`
- `0x180077ed8`
- `0x180078174`
- `0x18009323e`
- `0x180094010`

## pseudocode

```c
__int64 __fastcall ChangeGroup::CalculateFFKWithPrerequisiteComplementedByDK(
        ChangeGroup *this,
        struct ISyncKnowledge *a2,
        unsigned int a3)
{
  __int64 v3; // rax
  __int64 v5; // rsi
  __int64 v7; // rbx
  unsigned int v8; // esi
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // r14
  __int64 *v12; // r15
  __int64 v13; // rcx
  unsigned int v14; // eax
  BOOL v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // [rsp+60h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 13);
  v5 = a3;
  v7 = a3;
  if ( v3 )
  {
    if ( *(_QWORD *)(v3 + 8LL * a3) )
    {
      v8 = -2147217379;
LABEL_27:
      v17 = *((_QWORD *)this + 13);
      if ( v17 )
      {
        v18 = *(_QWORD *)(v17 + 8 * v7);
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          *(_QWORD *)(*((_QWORD *)this + 13) + 8 * v7) = 0;
        }
      }
      return v8;
    }
  }
  else
  {
    v9 = SeAlloc(saturated_mul(*((unsigned int *)this + 20), 8u));
    *((_QWORD *)this + 13) = v9;
    if ( !v9 )
    {
      v8 = -2147024882;
      goto LABEL_27;
    }
    memset_0(v9, 0, 8LL * *((unsigned int *)this + 20));
  }
  v10 = *((_QWORD *)this + 12);
  v11 = 8 * v5;
  if ( v10 )
  {
    if ( *(_QWORD *)(v10 + 8 * v5) )
    {
      v8 = 0;
      v12 = (__int64 *)((char *)this + 96);
      goto LABEL_12;
    }
    v12 = (__int64 *)((char *)this + 96);
  }
  else
  {
    v12 = (__int64 *)((char *)this + 96);
  }
  v8 = ChangeGroup::CalculateFFKComplementedByDKImpl(this, a2, v5);
  if ( v8 )
    goto LABEL_27;
LABEL_12:
  v13 = *((_QWORD *)this + 8);
  if ( v13 )
  {
    if ( v13 != *((_QWORD *)this + 5) )
    {
      v16 = *v12;
      goto LABEL_21;
    }
    v15 = 0;
  }
  else
  {
    v14 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, _QWORD))a2->lpVtbl->ContainsKnowledge)(
            a2,
            *((_QWORD *)this + 4));
    v8 = 0;
    if ( v14 != 1 )
      v8 = v14;
    v15 = v14 == 1;
  }
  if ( v8 )
    goto LABEL_27;
  v16 = *v12;
  if ( !v15 )
  {
    *(_QWORD *)(v11 + *((_QWORD *)this + 13)) = *(_QWORD *)(v16 + v11);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 + *((_QWORD *)this + 12)) + 8LL))(*(_QWORD *)(v11 + *((_QWORD *)this + 12)));
    return v8;
  }
LABEL_21:
  v20 = 0;
  v8 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v16 + v11))(
         *(_QWORD *)(v16 + v11),
         &GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8,
         &v20);
  if ( (v8 & 0x80000000) == 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ISyncKnowledge *, __int64))(*(_QWORD *)v20 + 288LL))(
           v20,
           *((_QWORD *)this + 4),
           a2,
           v11 + *((_QWORD *)this + 13));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( v8 )
    goto LABEL_27;
  return v8;
}

```

## disassembly

```asm
0x180078174  mov     [rsp+arg_8], rbx
0x180078179  mov     [rsp+arg_10], rbp
0x18007817e  push    rsi
0x18007817f  push    rdi
0x180078180  push    r12
0x180078182  push    r14
0x180078184  push    r15
0x180078186  sub     rsp, 30h
0x18007818a  mov     rax, [rcx+68h]
0x18007818e  mov     r12, rdx
0x180078191  mov     esi, r8d
0x180078194  mov     rdi, rcx
0x180078197  mov     ebx, r8d
0x18007819a  test    rax, rax
0x18007819d  jz      short loc_1800781B0
0x18007819f  cmp     qword ptr [rax+rsi*8], 0
0x1800781a4  jz      short loc_1800781ED
0x1800781a6  mov     esi, 8004101Dh
0x1800781ab  jmp     loc_18007830B
0x1800781b0  mov     ecx, [rcx+50h]
0x1800781b3  mov     eax, 8
0x1800781b8  mul     rcx
0x1800781bb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800781c2  cmovb   rax, rcx
0x1800781c6  mov     rcx, rax; unsigned __int64
0x1800781c9  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800781ce  mov     [rdi+68h], rax
0x1800781d2  test    rax, rax
0x1800781d5  jz      loc_180078306
0x1800781db  mov     r8d, [rdi+50h]
0x1800781df  xor     edx, edx; Val
0x1800781e1  shl     r8, 3; Size
0x1800781e5  mov     rcx, rax; void *
0x1800781e8  call    memset_0
0x1800781ed  lea     rbp, [rdi+60h]
0x1800781f1  mov     rax, [rbp+0]
0x1800781f5  lea     r14, ds:0[rsi*8]
0x1800781fd  test    rax, rax
0x180078200  jz      short loc_180078216
0x180078202  cmp     qword ptr [rax+r14], 0
0x180078207  jnz     short loc_18007820F
0x180078209  lea     r15, [rdi+60h]
0x18007820d  jmp     short loc_180078219
0x18007820f  xor     esi, esi
0x180078211  mov     r15, rbp
0x180078214  jmp     short loc_180078231
0x180078216  mov     r15, rbp
0x180078219  mov     r8d, esi; unsigned int
0x18007821c  mov     rdx, r12; struct ISyncKnowledge *
0x18007821f  mov     rcx, rdi; this
0x180078222  call    ?CalculateFFKComplementedByDKImpl@ChangeGroup@@AEAAJPEAUISyncKnowledge@@K@Z; ChangeGroup::CalculateFFKComplementedByDKImpl(ISyncKnowledge *,ulong)
0x180078227  mov     esi, eax
0x180078229  test    eax, eax
0x18007822b  jnz     loc_18007830B
0x180078231  mov     rcx, [rdi+40h]
0x180078235  test    rcx, rcx
0x180078238  jnz     short loc_180078263
0x18007823a  mov     rax, [r12]
0x18007823e  mov     rcx, r12
0x180078241  mov     rdx, [rdi+20h]
0x180078245  mov     rax, [rax+98h]
0x18007824c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078251  xor     esi, esi
0x180078253  cmp     eax, 1
0x180078256  cmovnz  esi, eax
0x180078259  xor     ecx, ecx
0x18007825b  cmp     eax, 1
0x18007825e  setz    cl
0x180078261  jmp     short loc_180078270
0x180078263  cmp     rcx, [rdi+28h]
0x180078267  jz      short loc_18007826E
0x180078269  mov     rax, [r15]
0x18007826c  jmp     short loc_18007827F
0x18007826e  xor     ecx, ecx
0x180078270  test    esi, esi
0x180078272  jnz     loc_18007830B
0x180078278  mov     rax, [r15]
0x18007827b  test    ecx, ecx
0x18007827d  jz      short loc_1800782E4
0x18007827f  mov     [rsp+58h+arg_0], 0
0x180078288  lea     r8, [rsp+58h+arg_0]
0x18007828d  mov     rcx, [rax+r14]
0x180078291  lea     rdx, _GUID_ed0addc0_3b4b_46a1_9a45_45661d2114c8
0x180078298  mov     rax, [rcx]
0x18007829b  mov     rax, [rax]
0x18007829e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782a3  mov     esi, eax
0x1800782a5  test    eax, eax
0x1800782a7  js      short loc_1800782DE
0x1800782a9  mov     rcx, [rsp+58h+arg_0]
0x1800782ae  mov     r8, r12
0x1800782b1  mov     r9, [rdi+68h]
0x1800782b5  add     r9, r14
0x1800782b8  mov     rdx, [rcx]
0x1800782bb  mov     rax, [rdx+120h]
0x1800782c2  mov     rdx, [rdi+20h]
0x1800782c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782cb  mov     rcx, [rsp+58h+arg_0]
0x1800782d0  mov     esi, eax
0x1800782d2  mov     rax, [rcx]
0x1800782d5  mov     rax, [rax+10h]
0x1800782d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782de  test    esi, esi
0x1800782e0  jz      short loc_180078335
0x1800782e2  jmp     short loc_18007830B
0x1800782e4  mov     rax, [rax+r14]
0x1800782e8  mov     rcx, [rdi+68h]
0x1800782ec  mov     [r14+rcx], rax
0x1800782f0  mov     rax, [rbp+0]
0x1800782f4  mov     rcx, [r14+rax]
0x1800782f8  mov     rax, [rcx]
0x1800782fb  mov     rax, [rax+8]
0x1800782ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078304  jmp     short loc_180078335
0x180078306  mov     esi, 8007000Eh
0x18007830b  mov     rcx, [rdi+68h]
0x18007830f  test    rcx, rcx
0x180078312  jz      short loc_180078335
0x180078314  mov     rcx, [rcx+rbx*8]
0x180078318  test    rcx, rcx
0x18007831b  jz      short loc_180078335
0x18007831d  mov     rax, [rcx]
0x180078320  mov     rax, [rax+10h]
0x180078324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078329  mov     rax, [rdi+68h]
0x18007832d  mov     qword ptr [rax+rbx*8], 0
0x180078335  mov     rbx, [rsp+58h+arg_8]
0x18007833a  mov     eax, esi
0x18007833c  mov     rbp, [rsp+58h+arg_10]
0x180078341  add     rsp, 30h
0x180078345  pop     r15
0x180078347  pop     r14
0x180078349  pop     r12
0x18007834b  pop     rdi
0x18007834c  pop     rsi
0x18007834d  retn
```
