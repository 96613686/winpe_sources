# CFileBuffer::Write(ulong,uchar *,ulong,ulong,ulong *)

- ea: `0x180016f90`
- end: `0x18001716a`
- name: `?Write@CFileBuffer@@QEAAHKPEAEKKPEAK@Z`
- size: `474`
- prototype: `__int64 __usercall@<rax>(CFileBuffer *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017170`

## callees

- `0x1800163d4`
- `0x180016e2c`
- `0x180016f00`
- `0x180016f90`
- `0x180017359`

## pseudocode

```c
__int64 __fastcall CFileBuffer::Write(
        CFileBuffer *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned __int64 v8; // r14
  int v10; // r8d
  int *v11; // rbx
  int v12; // edx
  unsigned __int64 v13; // r9
  int v14; // r8d
  unsigned int v15; // r10d
  int v16; // r8d
  _DWORD *v17; // rsi
  unsigned __int64 v18; // r9
  unsigned int v19; // ebp
  int v20; // r14d
  unsigned int v21; // eax
  void *v22; // rcx
  unsigned int v23; // ebx
  __int64 v24; // rax
  __int64 result; // rax

  v8 = a2;
  *((_DWORD *)this + 10) = a5;
  *a6 = 0;
  if ( *(_DWORD *)this && !(unsigned int)CFileBuffer::WaitComplete(this) || *(_DWORD *)this == 2 )
    return 0;
  v10 = *((_DWORD *)this + 7);
  v11 = (int *)((char *)this + 32);
  if ( v10 )
  {
    v12 = *v11;
    if ( (unsigned int)v8 >= *v11
      && (unsigned int)v8 < v12 + *((_DWORD *)this + 6)
      && ((unsigned int)v8 < v12 + v10 || v12 + v10 >= a5) )
    {
      goto LABEL_16;
    }
    if ( !(unsigned int)CFileBuffer::Commit((HANDLE *)this) || !(unsigned int)CFileBuffer::WaitComplete(this) )
      return 0;
    *((_DWORD *)this + 7) = 0;
  }
  v13 = *((unsigned int *)this + 9);
  v14 = v8 - v8 % v13;
  *v11 = v14;
  if ( v8 < v13 + a5 - 1LL - (v13 + a5 - 1LL) % v13 )
  {
    if ( (unsigned int)v8 % (unsigned int)v13 )
    {
      *((_DWORD *)this + 7) = v13;
      if ( !(unsigned int)CFileBuffer::ReadIntoBuffer(this, 0, v14, v13)
        || !(unsigned int)CFileBuffer::WaitComplete(this) )
      {
        return 0;
      }
    }
  }
LABEL_16:
  v15 = v8 + a4;
  v16 = *v11;
  v17 = (_DWORD *)((char *)this + 36);
  if ( (unsigned int)v8 + a4 >= *v11 + *((_DWORD *)this + 6) )
    goto LABEL_23;
  v18 = (unsigned int)*v17;
  if ( !(v15 % (unsigned int)v18) || v15 <= v16 + *((_DWORD *)this + 7) || v15 >= a5 )
    goto LABEL_23;
  v19 = v15 - v15 % *v17;
  *((_DWORD *)this + 7) = v18;
  if ( !(unsigned int)CFileBuffer::ReadIntoBuffer(this, v15 - v15 % v18 - v16, v15 - v15 % v18, v18)
    || !(unsigned int)CFileBuffer::WaitComplete(this) )
  {
    return 0;
  }
  v16 = *v11;
  *((_DWORD *)this + 7) = *v17 + v19 - *v11;
LABEL_23:
  v20 = v8 - v16;
  v21 = *((_DWORD *)this + 6) - v20;
  if ( a4 < v21 )
    v21 = a4;
  v22 = (void *)(*((_QWORD *)this + 1) + v20);
  v23 = v21;
  *a6 = v21;
  memcpy_0(v22, a3, v21);
  v24 = v20 + v23;
  if ( (unsigned int)v24 > *((_DWORD *)this + 7) )
    *((_DWORD *)this + 7) = v24 + *v17 - 1 - (v24 + (unsigned __int64)(unsigned int)*v17 - 1) % (unsigned int)*v17;
  result = 1;
  *((_DWORD *)this + 1) = 1;
  return result;
}

```

## disassembly

```asm
0x180016f90  push    rbx
0x180016f92  push    rbp
0x180016f93  push    rsi
0x180016f94  push    rdi
0x180016f95  push    r12
0x180016f97  push    r13
0x180016f99  push    r14
0x180016f9b  push    r15
0x180016f9d  sub     rsp, 28h
0x180016fa1  mov     r12, [rsp+68h+arg_28]
0x180016fa9  xor     esi, esi
0x180016fab  mov     r15d, r9d
0x180016fae  mov     ebp, [rsp+68h+arg_20]
0x180016fb5  mov     r13, r8
0x180016fb8  mov     r14d, edx
0x180016fbb  mov     rdi, rcx
0x180016fbe  mov     [rcx+28h], ebp
0x180016fc1  mov     [r12], esi
0x180016fc5  cmp     [rcx], esi
0x180016fc7  jz      short loc_180016FD6
0x180016fc9  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x180016fce  test    eax, eax
0x180016fd0  jz      loc_180017157
0x180016fd6  cmp     dword ptr [rdi], 2
0x180016fd9  jz      loc_180017157
0x180016fdf  mov     r8d, [rdi+1Ch]
0x180016fe3  lea     rbx, [rdi+20h]
0x180016fe7  test    r8d, r8d
0x180016fea  jz      short loc_180017035
0x180016fec  mov     edx, [rbx]
0x180016fee  cmp     r14d, edx
0x180016ff1  jb      short loc_180017012
0x180016ff3  mov     ecx, [rdi+18h]
0x180016ff6  add     ecx, edx
0x180016ff8  cmp     r14d, ecx
0x180016ffb  jnb     short loc_180017012
0x180016ffd  lea     eax, [rdx+r8]
0x180017001  cmp     r14d, eax
0x180017004  jb      loc_180017093
0x18001700a  cmp     eax, ebp
0x18001700c  jnb     loc_180017093
0x180017012  mov     rcx, rdi; this
0x180017015  call    ?Commit@CFileBuffer@@QEAAHXZ; CFileBuffer::Commit(void)
0x18001701a  test    eax, eax
0x18001701c  jz      loc_180017157
0x180017022  mov     rcx, rdi; this
0x180017025  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x18001702a  test    eax, eax
0x18001702c  jz      loc_180017157
0x180017032  mov     [rdi+1Ch], esi
0x180017035  mov     r9d, [rdi+24h]; unsigned int
0x180017039  lea     rcx, [rbp-1]
0x18001703d  xor     edx, edx
0x18001703f  mov     rax, r14
0x180017042  div     r9
0x180017045  add     rcx, r9
0x180017048  mov     r8d, r14d
0x18001704b  sub     r8d, edx; unsigned int
0x18001704e  mov     rax, rcx
0x180017051  xor     edx, edx
0x180017053  mov     [rbx], r8d
0x180017056  div     r9
0x180017059  sub     rcx, rdx
0x18001705c  cmp     r14, rcx
0x18001705f  jnb     short loc_180017093
0x180017061  xor     edx, edx
0x180017063  mov     eax, r14d
0x180017066  div     r9d
0x180017069  test    edx, edx
0x18001706b  jz      short loc_180017093
0x18001706d  xor     edx, edx; int
0x18001706f  mov     [rdi+1Ch], r9d
0x180017073  mov     rcx, rdi; this
0x180017076  call    ?ReadIntoBuffer@CFileBuffer@@AEAAHHKK@Z; CFileBuffer::ReadIntoBuffer(int,ulong,ulong)
0x18001707b  test    eax, eax
0x18001707d  jz      loc_180017157
0x180017083  mov     rcx, rdi; this
0x180017086  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x18001708b  test    eax, eax
0x18001708d  jz      loc_180017157
0x180017093  mov     ecx, [rdi+18h]
0x180017096  lea     r10d, [r14+r15]
0x18001709a  mov     r8d, [rbx]
0x18001709d  lea     rsi, [rdi+24h]
0x1800170a1  add     ecx, r8d
0x1800170a4  cmp     r10d, ecx
0x1800170a7  jnb     short loc_180017104
0x1800170a9  mov     r9d, [rsi]; unsigned int
0x1800170ac  xor     edx, edx
0x1800170ae  mov     eax, r10d
0x1800170b1  div     r9d
0x1800170b4  test    edx, edx
0x1800170b6  jz      short loc_180017104
0x1800170b8  mov     ecx, [rdi+1Ch]
0x1800170bb  add     ecx, r8d
0x1800170be  cmp     r10d, ecx
0x1800170c1  jbe     short loc_180017104
0x1800170c3  cmp     r10d, ebp
0x1800170c6  jnb     short loc_180017104
0x1800170c8  xor     edx, edx
0x1800170ca  mov     eax, r10d
0x1800170cd  div     r9
0x1800170d0  mov     ebp, r10d
0x1800170d3  mov     rcx, rdi; this
0x1800170d6  sub     ebp, edx
0x1800170d8  mov     [rdi+1Ch], r9d
0x1800170dc  mov     edx, ebp
0x1800170de  sub     edx, r8d; int
0x1800170e1  mov     r8d, ebp; unsigned int
0x1800170e4  call    ?ReadIntoBuffer@CFileBuffer@@AEAAHHKK@Z; CFileBuffer::ReadIntoBuffer(int,ulong,ulong)
0x1800170e9  test    eax, eax
0x1800170eb  jz      short loc_180017157
0x1800170ed  mov     rcx, rdi; this
0x1800170f0  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x1800170f5  test    eax, eax
0x1800170f7  jz      short loc_180017157
0x1800170f9  mov     r8d, [rbx]
0x1800170fc  sub     ebp, r8d
0x1800170ff  add     ebp, [rsi]
0x180017101  mov     [rdi+1Ch], ebp
0x180017104  mov     eax, [rdi+18h]
0x180017107  sub     r14d, r8d
0x18001710a  sub     eax, r14d
0x18001710d  movsxd  rcx, r14d
0x180017110  cmp     r15d, eax
0x180017113  mov     rdx, r13; Src
0x180017116  cmovb   eax, r15d
0x18001711a  add     rcx, [rdi+8]; void *
0x18001711e  mov     ebx, eax
0x180017120  mov     r8d, eax; Size
0x180017123  mov     [r12], ebx
0x180017127  call    memcpy_0
0x18001712c  lea     eax, [r14+rbx]
0x180017130  cmp     eax, [rdi+1Ch]
0x180017133  jbe     short loc_18001714D
0x180017135  mov     ecx, [rsi]
0x180017137  xor     edx, edx
0x180017139  lea     r8, [rcx-1]
0x18001713d  add     r8, rax
0x180017140  mov     rax, r8
0x180017143  div     rcx
0x180017146  sub     r8d, edx
0x180017149  mov     [rdi+1Ch], r8d
0x18001714d  mov     eax, 1
0x180017152  mov     [rdi+4], eax
0x180017155  jmp     short loc_180017159
0x180017157  xor     eax, eax
0x180017159  add     rsp, 28h
0x18001715d  pop     r15
0x18001715f  pop     r14
0x180017161  pop     r13
0x180017163  pop     r12
0x180017165  pop     rdi
0x180017166  pop     rsi
0x180017167  pop     rbp
0x180017168  pop     rbx
0x180017169  retn
```
