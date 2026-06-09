# CASFFrameIndexMaker::CompleteStreamIndex(CASFBaseIndexMaker::STREAM_INFO *,unsigned __int64)

- ea: `0x180032110`
- end: `0x18003227a`
- name: `?CompleteStreamIndex@CASFFrameIndexMaker@@AEAAJPEAUSTREAM_INFO@CASFBaseIndexMaker@@_K@Z`
- size: `362`
- prototype: `__int64 __fastcall(CASFFrameIndexMaker *__hidden this, struct CASFBaseIndexMaker::STREAM_INFO *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180032070`
- `0x180032690`

## callees

- `0x1800043cc`
- `0x18002f114`
- `0x18002fcb0`
- `0x180032110`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFFrameIndexMaker::CompleteStreamIndex(
        CASFFrameIndexMaker *this,
        struct CASFBaseIndexMaker::STREAM_INFO *a2,
        unsigned __int64 a3)
{
  __int64 result; // rax
  unsigned int v7; // r14d
  unsigned __int64 v8; // rbx
  __int64 v9; // r15
  unsigned __int64 v10; // rbx
  __int64 v11; // rdx
  char *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r10
  _BYTE v16[24]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v17[80]; // [rsp+48h] [rbp-50h] BYREF

  if ( a3 < *((unsigned int *)this + 17) )
    return 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = *((_QWORD *)a2 + 4);
    if ( v8 > a3 - *((unsigned int *)this + 17) )
      break;
    v9 = -1;
    if ( *((_DWORD *)a2 + 148)
      && *(_QWORD *)CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::operator[]((char *)a2 + 40, v16, 0) <= v8 )
    {
      while ( 1 )
      {
        v9 = *(_QWORD *)(CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::operator[]((char *)a2 + 40, v17, 0) + 16);
        if ( *((_DWORD *)a2 + 148) < 2u )
          break;
        v10 = *((_QWORD *)a2 + 4);
        if ( *(_QWORD *)CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::operator[]((char *)a2 + 40, v17, 1) > v10 )
          break;
        CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::RemoveAt((char *)a2 + 40, 0);
      }
    }
    v11 = *((unsigned int *)a2 + 3);
    v12 = (char *)this + 128;
    if ( *((_WORD *)a2 + 2) == 255 )
    {
      v13 = CTDynArray<IASFIndexBlock *,20>::operator[](v12, v11);
      if ( v9 == -1 )
        v14 = -1;
      else
        v14 = *((_QWORD *)a2 + 4) - v9;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v13 + 136LL))(
        v13,
        *((_QWORD *)a2 + 4),
        *((unsigned __int16 *)a2 + 1),
        *((unsigned __int16 *)a2 + 2),
        v14);
    }
    else
    {
      v15 = CTDynArray<IASFIndexBlock *,20>::operator[](v12, v11);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v15 + 136LL))(
        v15,
        *((_QWORD *)a2 + 4),
        *((unsigned __int16 *)a2 + 1),
        *((unsigned __int16 *)a2 + 2),
        v9);
    }
    if ( ++*((_DWORD *)a2 + 2) >= *((_DWORD *)this + 18) )
    {
      if ( !*((_DWORD *)a2 + 3) )
      {
        result = (*(__int64 (__fastcall **)(CASFFrameIndexMaker *))(*(_QWORD *)this + 80LL))(this);
        v7 = result;
        if ( (int)result < 0 )
          return result;
      }
      --*((_DWORD *)a2 + 3);
      *((_DWORD *)a2 + 2) = 0;
    }
    *((_QWORD *)a2 + 4) += *((unsigned int *)this + 16);
  }
  return v7;
}

```

## disassembly

```asm
0x180032110  push    rbx
0x180032112  push    rbp
0x180032113  push    rsi
0x180032114  push    rdi
0x180032115  push    r12
0x180032117  push    r14
0x180032119  push    r15
0x18003211b  sub     rsp, 60h
0x18003211f  mov     eax, [rcx+44h]
0x180032122  mov     r12, r8
0x180032125  mov     rdi, rdx
0x180032128  mov     rsi, rcx
0x18003212b  cmp     r8, rax
0x18003212e  jnb     short loc_180032137
0x180032130  xor     eax, eax
0x180032132  jmp     loc_18003226B
0x180032137  xor     r14d, r14d
0x18003213a  mov     eax, [rsi+44h]
0x18003213d  mov     rcx, r12
0x180032140  mov     rbx, [rdi+20h]
0x180032144  sub     rcx, rax
0x180032147  cmp     rbx, rcx
0x18003214a  ja      loc_180032268
0x180032150  or      r15, 0FFFFFFFFFFFFFFFFh
0x180032154  lea     rbp, [rdi+28h]
0x180032158  cmp     dword ptr [rbp+228h], 1
0x18003215f  jb      short loc_1800321BB
0x180032161  xor     r8d, r8d
0x180032164  lea     rdx, [rsp+98h+var_68]
0x180032169  mov     rcx, rbp
0x18003216c  call    ??A?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEBA?AUSEEK_POINT@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::operator[](ulong)
0x180032171  cmp     [rax], rbx
0x180032174  ja      short loc_1800321BB
0x180032176  jmp     short loc_18003219E
0x180032178  mov     rbx, [rdi+20h]
0x18003217c  lea     rdx, [rsp+98h+var_50]
0x180032181  mov     r8d, 1
0x180032187  mov     rcx, rbp
0x18003218a  call    ??A?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEBA?AUSEEK_POINT@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::operator[](ulong)
0x18003218f  cmp     [rax], rbx
0x180032192  ja      short loc_1800321BB
0x180032194  xor     edx, edx
0x180032196  mov     rcx, rbp
0x180032199  call    ?RemoveAt@?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::RemoveAt(ulong,ulong)
0x18003219e  xor     r8d, r8d
0x1800321a1  lea     rdx, [rsp+98h+var_50]
0x1800321a6  mov     rcx, rbp
0x1800321a9  call    ??A?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@QEBA?AUSEEK_POINT@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::operator[](ulong)
0x1800321ae  cmp     dword ptr [rdi+250h], 2
0x1800321b5  mov     r15, [rax+10h]
0x1800321b9  jnb     short loc_180032178
0x1800321bb  mov     edx, [rdi+0Ch]
0x1800321be  lea     rcx, [rsi+80h]
0x1800321c5  mov     eax, 0FFh
0x1800321ca  cmp     [rdi+4], ax
0x1800321ce  jnz     short loc_1800321FE
0x1800321d0  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x1800321d5  mov     rcx, [rax]
0x1800321d8  mov     r10, [rcx+88h]
0x1800321df  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800321e3  jnz     short loc_1800321EA
0x1800321e5  or      rcx, r15
0x1800321e8  jmp     short loc_1800321F1
0x1800321ea  mov     rcx, [rdi+20h]
0x1800321ee  sub     rcx, r15
0x1800321f1  mov     [rsp+98h+var_78], rcx
0x1800321f6  mov     rcx, rax
0x1800321f9  mov     rax, r10
0x1800321fc  jmp     short loc_180032218
0x1800321fe  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x180032203  mov     r10, rax
0x180032206  mov     [rsp+98h+var_78], r15
0x18003220b  mov     rcx, [rax]
0x18003220e  mov     rax, [rcx+88h]
0x180032215  mov     rcx, r10
0x180032218  movzx   r9d, word ptr [rdi+4]
0x18003221d  movzx   r8d, word ptr [rdi+2]
0x180032222  mov     rdx, [rdi+20h]
0x180032226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003222b  inc     dword ptr [rdi+8]
0x18003222e  mov     eax, [rdi+8]
0x180032231  cmp     eax, [rsi+48h]
0x180032234  jb      short loc_18003225C
0x180032236  cmp     dword ptr [rdi+0Ch], 0
0x18003223a  jnz     short loc_180032252
0x18003223c  mov     rax, [rsi]
0x18003223f  mov     rcx, rsi
0x180032242  mov     rax, [rax+50h]
0x180032246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003224b  mov     r14d, eax
0x18003224e  test    eax, eax
0x180032250  js      short loc_18003226B
0x180032252  dec     dword ptr [rdi+0Ch]
0x180032255  mov     dword ptr [rdi+8], 0
0x18003225c  mov     ecx, [rsi+40h]
0x18003225f  add     [rdi+20h], rcx
0x180032263  jmp     loc_18003213A
0x180032268  mov     eax, r14d
0x18003226b  add     rsp, 60h
0x18003226f  pop     r15
0x180032271  pop     r14
0x180032273  pop     r12
0x180032275  pop     rdi
0x180032276  pop     rsi
0x180032277  pop     rbp
0x180032278  pop     rbx
0x180032279  retn
```
