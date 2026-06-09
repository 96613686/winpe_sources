# LKRhash::CLKRLinearHashTable::_DeleteNode(LKRhash::CBucket * const,LKRhash::CNodeClump * &,LKRhash::CNodeClump * &,int &)

- ea: `0x18000943c`
- end: `0x18000956c`
- name: `?_DeleteNode@CLKRLinearHashTable@LKRhash@@AEAA_NQEAVCBucket@2@AEAPEAVCNodeClump@2@1AEAH@Z`
- size: `304`
- prototype: `bool __fastcall(LKRhash::CLKRLinearHashTable *__hidden this, struct LKRhash::CBucket *const, struct LKRhash::CNodeClump **, struct LKRhash::CNodeClump **, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800091b0`

## callees

- `0x18000943c`
- `0x18000b010`

## pseudocode

```c
char __fastcall LKRhash::CLKRLinearHashTable::_DeleteNode(
        LKRhash::CLKRLinearHashTable *this,
        struct LKRhash::CNodeClump **a2,
        struct LKRhash::CNodeClump **a3,
        struct LKRhash::CNodeClump **a4,
        int *a5)
{
  struct LKRhash::CNodeClump *v9; // r11
  __int64 v10; // r9
  struct LKRhash::CNodeClump *v11; // r10
  int v12; // r8d
  struct LKRhash::CNodeClump *v13; // rcx
  __int64 v14; // rdx
  int v15; // r8d
  struct LKRhash::CNodeClump *v16; // rax
  char *v17; // rdx

  (*((void (__fastcall **)(_QWORD, __int64))this + 7))(*((_QWORD *)*a3 + *a5 + 3), 0xFFFFFFFFLL);
  v9 = *a3;
  v10 = *a5;
  v11 = *a3;
  v12 = *a5;
  while ( *((_QWORD *)v11 + 2) )
  {
    v11 = (struct LKRhash::CNodeClump *)*((_QWORD *)v11 + 2);
    v12 = 0;
  }
  while ( v12 != 4 && *((_DWORD *)v11 + v12) != 31678523 )
    ++v12;
  v13 = (struct LKRhash::CNodeClump *)(a2 + 1);
  v14 = v12;
  v15 = v12 - 1;
  *((_QWORD *)v9 + v10 + 3) = *((_QWORD *)v11 + v14 + 2);
  *((_DWORD *)v9 + v10) = *((_DWORD *)v11 + v14 - 1);
  *((_QWORD *)v11 + v14 + 2) = 0;
  *((_DWORD *)v11 + v14 - 1) = 31678523;
  if ( (_DWORD)v10 )
  {
    *a5 = v10 - 1;
  }
  else if ( v9 == v13 )
  {
    *a5 = -1;
  }
  else
  {
    v16 = *a4;
    *a5 = 4;
    *a3 = v16;
    if ( v16 == v13 )
    {
      *a4 = 0;
    }
    else
    {
      *a4 = v13;
      if ( a2[3] != v16 )
      {
        v17 = (char *)(a2 + 1);
        do
          v17 = (char *)*((_QWORD *)v17 + 2);
        while ( *((struct LKRhash::CNodeClump **)v17 + 2) != v16 );
        *a4 = (struct LKRhash::CNodeClump *)v17;
      }
    }
  }
  if ( !v15 && v11 != v13 )
  {
    while ( *((struct LKRhash::CNodeClump **)v13 + 2) != v11 )
      v13 = (struct LKRhash::CNodeClump *)*((_QWORD *)v13 + 2);
    *((_QWORD *)v13 + 2) = 0;
    (*(void (__fastcall **)(_QWORD, struct LKRhash::CNodeClump *, __int64))(**((_QWORD **)this + 18) + 8LL))(
      *((_QWORD *)this + 18),
      v11,
      4);
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 30);
  return 1;
}

```

## disassembly

```asm
0x18000943c  push    rbx
0x18000943e  push    rbp
0x18000943f  push    rsi
0x180009440  push    rdi
0x180009441  push    r14
0x180009443  sub     rsp, 20h
0x180009447  mov     rdi, [rsp+48h+arg_20]
0x18000944c  mov     rsi, rcx
0x18000944f  mov     rcx, [r8]
0x180009452  mov     rbp, rdx
0x180009455  or      edx, 0FFFFFFFFh
0x180009458  mov     rbx, r9
0x18000945b  mov     r14, r8
0x18000945e  movsxd  rax, dword ptr [rdi]
0x180009461  mov     rcx, [rcx+rax*8+18h]
0x180009466  mov     rax, [rsi+38h]
0x18000946a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000946f  mov     r11, [r14]
0x180009472  movsxd  r9, dword ptr [rdi]
0x180009475  mov     r10, r11
0x180009478  mov     r8d, r9d
0x18000947b  mov     rax, [r10+10h]
0x18000947f  test    rax, rax
0x180009482  jz      short loc_18000949C
0x180009484  mov     r10, rax
0x180009487  xor     r8d, r8d
0x18000948a  jmp     short loc_18000947B
0x18000948c  movsxd  rax, r8d
0x18000948f  cmp     dword ptr [r10+rax*4], 1E3603Bh
0x180009497  jz      short loc_1800094A2
0x180009499  inc     r8d
0x18000949c  cmp     r8d, 4
0x1800094a0  jnz     short loc_18000948C
0x1800094a2  movsxd  rax, r8d
0x1800094a5  lea     rcx, [rbp+8]
0x1800094a9  mov     rdx, rax
0x1800094ac  dec     r8d
0x1800094af  mov     rax, [r10+rax*8+10h]
0x1800094b4  mov     [r11+r9*8+18h], rax
0x1800094b9  mov     eax, [r10+rdx*4-4]
0x1800094be  mov     [r11+r9*4], eax
0x1800094c2  mov     qword ptr [r10+rdx*8+10h], 0
0x1800094cb  mov     dword ptr [r10+rdx*4-4], 1E3603Bh
0x1800094d4  test    r9d, r9d
0x1800094d7  jz      short loc_1800094E1
0x1800094d9  lea     eax, [r9-1]
0x1800094dd  mov     [rdi], eax
0x1800094df  jmp     short loc_180009521
0x1800094e1  cmp     r11, rcx
0x1800094e4  jnz     short loc_1800094EE
0x1800094e6  mov     dword ptr [rdi], 0FFFFFFFFh
0x1800094ec  jmp     short loc_180009521
0x1800094ee  mov     rax, [rbx]
0x1800094f1  mov     dword ptr [rdi], 4
0x1800094f7  mov     [r14], rax
0x1800094fa  cmp     rax, rcx
0x1800094fd  jnz     short loc_180009508
0x1800094ff  mov     qword ptr [rbx], 0
0x180009506  jmp     short loc_180009521
0x180009508  mov     [rbx], rcx
0x18000950b  cmp     [rbp+18h], rax
0x18000950f  jz      short loc_180009521
0x180009511  mov     rdx, rcx
0x180009514  mov     rdx, [rdx+10h]
0x180009518  cmp     [rdx+10h], rax
0x18000951c  jnz     short loc_180009514
0x18000951e  mov     [rbx], rdx
0x180009521  test    r8d, r8d
0x180009524  jnz     short loc_18000955B
0x180009526  cmp     r10, rcx
0x180009529  jz      short loc_18000955B
0x18000952b  jmp     short loc_180009531
0x18000952d  mov     rcx, [rcx+10h]
0x180009531  cmp     [rcx+10h], r10
0x180009535  jnz     short loc_18000952D
0x180009537  mov     qword ptr [rcx+10h], 0
0x18000953f  mov     r8d, 4
0x180009545  mov     rcx, [rsi+90h]
0x18000954c  mov     rdx, r10
0x18000954f  mov     r9, [rcx]
0x180009552  mov     rax, [r9+8]
0x180009556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955b  lock dec dword ptr [rsi+78h]
0x18000955f  mov     al, 1
0x180009561  add     rsp, 20h
0x180009565  pop     r14
0x180009567  pop     rdi
0x180009568  pop     rsi
0x180009569  pop     rbp
0x18000956a  pop     rbx
0x18000956b  retn
```
