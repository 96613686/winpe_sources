# CFileStream::Write(uchar *,ulong,ulong *)

- ea: `0x180017170`
- end: `0x1800172b7`
- name: `?Write@CFileStream@@QEAAHPEAEKPEAK@Z`
- size: `327`
- prototype: `int(CFileStream *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014960`

## callees

- `0x1800163d4`
- `0x18001692c`
- `0x180016f00`
- `0x180016f90`
- `0x180017170`

## pseudocode

```c
__int64 __fastcall CFileStream::Write(CFileStream *this, unsigned __int8 *a2, unsigned int a3, unsigned int *a4)
{
  bool v4; // zf
  unsigned int v6; // ebp
  unsigned int *v9; // rsi
  unsigned int *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // r15
  int v13; // edx
  __int64 v14; // rcx
  unsigned int v16; // [rsp+60h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 94) == 0;
  v6 = a3;
  *a4 = 0;
  if ( v4 )
    return 0;
  v16 = 0;
  v9 = (unsigned int *)((char *)this + 372);
  v10 = (unsigned int *)((char *)this + 380);
  if ( a3 )
  {
    while ( 1 )
    {
      v11 = *((int *)this + 91);
      if ( (int)v11 < 0 )
        break;
      v12 = 88 * v11;
      if ( !(unsigned int)CFileBuffer::QueryPosition((CFileStream *)((char *)this + 88 * v11 + 8), *v9, *v10) )
      {
        if ( !(unsigned int)CFileBuffer::Commit((HANDLE *)((char *)this + v12 + 8)) )
          return 0;
        if ( *((_DWORD *)this + 94) == 1 )
        {
          v13 = *((_DWORD *)this + 91);
        }
        else
        {
          v13 = (*((_DWORD *)this + 91) + 1) % *((_DWORD *)this + 90);
          *((_DWORD *)this + 91) = v13;
        }
LABEL_10:
        if ( !(unsigned int)CFileBuffer::WaitComplete((CFileStream *)((char *)this + 88 * v13 + 8)) )
          return 0;
      }
      if ( !(unsigned int)CFileBuffer::Write(
                            (CFileStream *)((char *)this + 88 * *((int *)this + 91) + 8),
                            *v9,
                            a2,
                            v6,
                            *v10,
                            &v16) )
        return 0;
      v14 = v16;
      *v9 += v16;
      a2 += v14;
      *a4 += v14;
      v6 -= v14;
      if ( !v6 )
        goto LABEL_13;
    }
    *((_DWORD *)this + 91) = 0;
    v13 = 0;
    goto LABEL_10;
  }
LABEL_13:
  if ( *v9 > *v10 )
    *v10 = *v9;
  return 1;
}

```

## disassembly

```asm
0x180017170  mov     [rsp+arg_8], rbx
0x180017175  mov     [rsp+arg_10], rbp
0x18001717a  push    rsi
0x18001717b  push    rdi
0x18001717c  push    r12
0x18001717e  push    r14
0x180017180  push    r15
0x180017182  sub     rsp, 30h
0x180017186  cmp     dword ptr [rcx+178h], 0
0x18001718d  mov     r14, r9
0x180017190  mov     ebp, r8d
0x180017193  mov     dword ptr [r9], 0
0x18001719a  mov     r12, rdx
0x18001719d  mov     rbx, rcx
0x1800171a0  jz      loc_18001729E
0x1800171a6  mov     [rsp+58h+arg_0], 0
0x1800171ae  lea     rsi, [rcx+174h]
0x1800171b5  lea     rdi, [rcx+17Ch]
0x1800171bc  test    r8d, r8d
0x1800171bf  jz      loc_18001728F
0x1800171c5  movsxd  rax, dword ptr [rbx+16Ch]
0x1800171cc  test    eax, eax
0x1800171ce  js      short loc_180017225
0x1800171d0  mov     r8d, [rdi]; unsigned int
0x1800171d3  lea     rcx, [rbx+8]
0x1800171d7  mov     edx, [rsi]; unsigned int
0x1800171d9  imul    r15, rax, 58h ; 'X'
0x1800171dd  add     rcx, r15; this
0x1800171e0  call    ?QueryPosition@CFileBuffer@@QEAAHKK@Z; CFileBuffer::QueryPosition(ulong,ulong)
0x1800171e5  test    eax, eax
0x1800171e7  jnz     short loc_180017248
0x1800171e9  lea     rcx, [rbx+8]
0x1800171ed  add     rcx, r15; this
0x1800171f0  call    ?Commit@CFileBuffer@@QEAAHXZ; CFileBuffer::Commit(void)
0x1800171f5  test    eax, eax
0x1800171f7  jz      loc_18001729E
0x1800171fd  cmp     dword ptr [rbx+178h], 1
0x180017204  jz      short loc_18001721D
0x180017206  mov     eax, [rbx+16Ch]
0x18001720c  inc     eax
0x18001720e  cdq
0x18001720f  idiv    dword ptr [rbx+168h]
0x180017215  mov     [rbx+16Ch], edx
0x18001721b  jmp     short loc_180017231
0x18001721d  mov     edx, [rbx+16Ch]
0x180017223  jmp     short loc_180017231
0x180017225  mov     dword ptr [rbx+16Ch], 0
0x18001722f  xor     edx, edx
0x180017231  movsxd  rax, edx
0x180017234  imul    rcx, rax, 58h ; 'X'
0x180017238  add     rcx, 8
0x18001723c  add     rcx, rbx; this
0x18001723f  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x180017244  test    eax, eax
0x180017246  jz      short loc_18001729E
0x180017248  movsxd  rax, dword ptr [rbx+16Ch]
0x18001724f  mov     r9d, ebp; unsigned int
0x180017252  mov     edx, [rsi]; unsigned int
0x180017254  mov     r8, r12; unsigned __int8 *
0x180017257  imul    rcx, rax, 58h ; 'X'
0x18001725b  lea     rax, [rsp+58h+arg_0]
0x180017260  mov     [rsp+58h+var_30], rax; unsigned int *
0x180017265  add     rcx, 8
0x180017269  mov     eax, [rdi]
0x18001726b  add     rcx, rbx; this
0x18001726e  mov     [rsp+58h+var_38], eax; unsigned int
0x180017272  call    ?Write@CFileBuffer@@QEAAHKPEAEKKPEAK@Z; CFileBuffer::Write(ulong,uchar *,ulong,ulong,ulong *)
0x180017277  test    eax, eax
0x180017279  jz      short loc_18001729E
0x18001727b  mov     ecx, [rsp+58h+arg_0]
0x18001727f  add     [rsi], ecx
0x180017281  add     r12, rcx
0x180017284  add     [r14], ecx
0x180017287  sub     ebp, ecx
0x180017289  jnz     loc_1800171C5
0x18001728f  mov     ecx, [rsi]
0x180017291  cmp     ecx, [rdi]
0x180017293  jbe     short loc_180017297
0x180017295  mov     [rdi], ecx
0x180017297  mov     eax, 1
0x18001729c  jmp     short loc_1800172A0
0x18001729e  xor     eax, eax
0x1800172a0  mov     rbx, [rsp+58h+arg_8]
0x1800172a5  mov     rbp, [rsp+58h+arg_10]
0x1800172aa  add     rsp, 30h
0x1800172ae  pop     r15
0x1800172b0  pop     r14
0x1800172b2  pop     r12
0x1800172b4  pop     rdi
0x1800172b5  pop     rsi
0x1800172b6  retn
```
