# CFileStream::Read(uchar *,ulong,ulong *)

- ea: `0x180016a94`
- end: `0x180016d19`
- name: `?Read@CFileStream@@QEAAHPEAEKPEAK@Z`
- size: `645`
- prototype: `int(CFileStream *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014880`

## callees

- `0x1800163d4`
- `0x18001692c`
- `0x180016990`
- `0x180016a94`
- `0x180016d20`
- `0x180016f00`

## pseudocode

```c
__int64 __fastcall CFileStream::Read(CFileStream *this, unsigned __int8 *a2, unsigned int a3, unsigned int *a4)
{
  bool v4; // zf
  unsigned int v6; // edi
  unsigned __int8 *v7; // r14
  unsigned int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // eax
  int v12; // esi
  __int64 v13; // rax
  __int64 v14; // rbp
  int v15; // eax
  int v16; // ebp
  int v17; // eax
  int v18; // r15d
  int v19; // r14d
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // edx
  __int64 v24; // rax
  __int64 v25; // r8
  int v26; // ecx
  unsigned int v27; // edx
  unsigned int v29; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int8 *v30; // [rsp+78h] [rbp+10h]

  v30 = a2;
  v4 = *((_DWORD *)this + 94) == 0;
  v6 = a3;
  *a4 = 0;
  v7 = a2;
  if ( v4 )
    return 0;
  v9 = *((_DWORD *)this + 95);
  v10 = *((_DWORD *)this + 93);
  if ( v10 < v9 )
  {
    v11 = v9 - v10;
    v29 = 0;
    if ( a3 >= v11 )
      v6 = v11;
    if ( v6 )
    {
      v12 = 0;
      while ( 1 )
      {
        v13 = *((int *)this + 91);
        if ( (int)v13 < 0 )
          break;
        v14 = 88 * v13;
        if ( !(unsigned int)CFileBuffer::QueryPosition(
                              (CFileStream *)((char *)this + 88 * v13 + 8),
                              *((_DWORD *)this + 93),
                              *((_DWORD *)this + 95)) )
        {
          if ( !(unsigned int)CFileBuffer::Commit((HANDLE *)((char *)this + v14 + 8)) )
            return 0;
          v15 = *((_DWORD *)this + 94);
          if ( v15 == 3 )
          {
            *((_DWORD *)this + 91) = (*((_DWORD *)this + 91) + 1) % *((_DWORD *)this + 90);
          }
          else if ( v15 == 2 )
          {
            v16 = *((_DWORD *)this + 90);
            v17 = *((_DWORD *)this + 91);
            *((_DWORD *)this + 91) = -1;
            if ( v16 > 0 )
            {
              v18 = 0;
              v19 = (v17 + 1) % v16;
              while ( !(unsigned int)CFileBuffer::QueryPosition(
                                       (CFileStream *)((char *)this + 88 * v19 + 8),
                                       *((_DWORD *)this + 93),
                                       *((_DWORD *)this + 95)) )
              {
                ++v18;
                v19 = (v19 + 1) % v16;
                if ( v18 >= v16 )
                  goto LABEL_19;
              }
              *((_DWORD *)this + 91) = v19;
LABEL_19:
              v7 = v30;
            }
            v20 = *((_DWORD *)this + 91);
            if ( v20 < 0 )
            {
              v20 = (*((_DWORD *)this + 92) + 1) % v16;
              *((_DWORD *)this + 91) = v20;
              *((_DWORD *)this + 92) = v20;
            }
            if ( v20 == *((_DWORD *)this + 92) )
              v12 = 1;
          }
LABEL_26:
          if ( !(unsigned int)CFileBuffer::WaitComplete((CFileStream *)((char *)this + 88 * *((int *)this + 91) + 8)) )
            return 0;
        }
        if ( !(unsigned int)CFileBuffer::Read(
                              (CFileStream *)((char *)this + 88 * *((int *)this + 91) + 8),
                              *((_DWORD *)this + 93),
                              v7,
                              v6,
                              *((_DWORD *)this + 95),
                              &v29) )
          return 0;
        v21 = v29;
        *((_DWORD *)this + 93) += v29;
        v7 += v21;
        *a4 += v21;
        v6 -= v21;
        v30 = v7;
        if ( v12 )
        {
          v22 = *((int *)this + 91);
          v23 = ((int)v22 + 1) % *((_DWORD *)this + 90);
          v24 = 88 * v22;
          v25 = v23;
          *((_DWORD *)this + 92) = v23;
          if ( *((_DWORD *)this + 22 * v22 + 2) == 2 || (v26 = *(_DWORD *)((char *)this + v24 + 36)) == 0 )
            v27 = 0;
          else
            v27 = v26 + *(_DWORD *)((char *)this + v24 + 40);
          CFileBuffer::ReadAhead((CFileStream *)((char *)this + 88 * v25 + 8), v27, *((_DWORD *)this + 95));
          v12 = 0;
        }
        if ( !v6 )
          return 1;
      }
      v4 = *((_DWORD *)this + 92) == 0;
      *((_DWORD *)this + 91) = 0;
      if ( v4 )
        v12 = 1;
      goto LABEL_26;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180016a94  mov     [rsp+arg_10], rbx
0x180016a99  mov     [rsp+arg_8], rdx
0x180016a9e  push    rbp
0x180016a9f  push    rsi
0x180016aa0  push    rdi
0x180016aa1  push    r12
0x180016aa3  push    r13
0x180016aa5  push    r14
0x180016aa7  push    r15
0x180016aa9  sub     rsp, 30h
0x180016aad  cmp     dword ptr [rcx+178h], 0
0x180016ab4  mov     r13, r9
0x180016ab7  mov     edi, r8d
0x180016aba  mov     dword ptr [r9], 0
0x180016ac1  mov     r14, rdx
0x180016ac4  mov     rbx, rcx
0x180016ac7  jz      loc_180016CFF
0x180016acd  mov     eax, [rcx+17Ch]
0x180016ad3  mov     r15d, 1
0x180016ad9  mov     ecx, [rcx+174h]
0x180016adf  cmp     ecx, eax
0x180016ae1  jnb     loc_180016CFA
0x180016ae7  sub     eax, ecx
0x180016ae9  mov     [rsp+68h+arg_0], 0
0x180016af1  cmp     r8d, eax
0x180016af4  cmovnb  edi, eax
0x180016af7  test    edi, edi
0x180016af9  jz      loc_180016CFA
0x180016aff  xor     esi, esi
0x180016b01  movsxd  rax, dword ptr [rbx+16Ch]
0x180016b08  test    eax, eax
0x180016b0a  js      loc_180016C16
0x180016b10  mov     r8d, [rbx+17Ch]; unsigned int
0x180016b17  lea     rcx, [rbx+8]
0x180016b1b  mov     edx, [rbx+174h]; unsigned int
0x180016b21  imul    rbp, rax, 58h ; 'X'
0x180016b25  add     rcx, rbp; this
0x180016b28  call    ?QueryPosition@CFileBuffer@@QEAAHKK@Z; CFileBuffer::QueryPosition(ulong,ulong)
0x180016b2d  test    eax, eax
0x180016b2f  jnz     loc_180016C4A
0x180016b35  lea     rcx, [rbx+8]
0x180016b39  add     rcx, rbp; this
0x180016b3c  call    ?Commit@CFileBuffer@@QEAAHXZ; CFileBuffer::Commit(void)
0x180016b41  test    eax, eax
0x180016b43  jz      loc_180016CFF
0x180016b49  mov     eax, [rbx+178h]
0x180016b4f  cmp     eax, 3
0x180016b52  jnz     short loc_180016B6F
0x180016b54  mov     eax, [rbx+16Ch]
0x180016b5a  add     eax, r15d
0x180016b5d  cdq
0x180016b5e  idiv    dword ptr [rbx+168h]
0x180016b64  mov     [rbx+16Ch], edx
0x180016b6a  jmp     loc_180016C2B
0x180016b6f  cmp     eax, 2
0x180016b72  jnz     loc_180016C2B
0x180016b78  mov     ebp, [rbx+168h]
0x180016b7e  mov     eax, [rbx+16Ch]
0x180016b84  mov     dword ptr [rbx+16Ch], 0FFFFFFFFh
0x180016b8e  test    ebp, ebp
0x180016b90  jle     short loc_180016BE7
0x180016b92  xor     r15d, r15d
0x180016b95  lea     r12, [rbx+8]
0x180016b99  inc     eax
0x180016b9b  cdq
0x180016b9c  idiv    ebp
0x180016b9e  mov     r14d, edx
0x180016ba1  mov     r8d, [rbx+17Ch]; unsigned int
0x180016ba8  mov     edx, [rbx+174h]; unsigned int
0x180016bae  movsxd  rax, r14d
0x180016bb1  imul    rcx, rax, 58h ; 'X'
0x180016bb5  add     rcx, r12; this
0x180016bb8  call    ?QueryPosition@CFileBuffer@@QEAAHKK@Z; CFileBuffer::QueryPosition(ulong,ulong)
0x180016bbd  test    eax, eax
0x180016bbf  jnz     short loc_180016BD5
0x180016bc1  lea     eax, [r14+1]
0x180016bc5  inc     r15d
0x180016bc8  cdq
0x180016bc9  idiv    ebp
0x180016bcb  mov     r14d, edx
0x180016bce  cmp     r15d, ebp
0x180016bd1  jl      short loc_180016BA1
0x180016bd3  jmp     short loc_180016BDC
0x180016bd5  mov     [rbx+16Ch], r14d
0x180016bdc  mov     r14, [rsp+68h+arg_8]
0x180016be1  mov     r15d, 1
0x180016be7  mov     edx, [rbx+16Ch]
0x180016bed  test    edx, edx
0x180016bef  jns     short loc_180016C09
0x180016bf1  mov     eax, [rbx+170h]
0x180016bf7  add     eax, r15d
0x180016bfa  cdq
0x180016bfb  idiv    ebp
0x180016bfd  mov     [rbx+16Ch], edx
0x180016c03  mov     [rbx+170h], edx
0x180016c09  cmp     edx, [rbx+170h]
0x180016c0f  jnz     short loc_180016C2B
0x180016c11  mov     esi, r15d
0x180016c14  jmp     short loc_180016C2B
0x180016c16  cmp     dword ptr [rbx+170h], 0
0x180016c1d  mov     dword ptr [rbx+16Ch], 0
0x180016c27  cmovz   esi, r15d
0x180016c2b  movsxd  rax, dword ptr [rbx+16Ch]
0x180016c32  imul    rcx, rax, 58h ; 'X'
0x180016c36  add     rcx, 8
0x180016c3a  add     rcx, rbx; this
0x180016c3d  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x180016c42  test    eax, eax
0x180016c44  jz      loc_180016CFF
0x180016c4a  movsxd  rax, dword ptr [rbx+16Ch]
0x180016c51  mov     r9d, edi; unsigned int
0x180016c54  mov     edx, [rbx+174h]; unsigned int
0x180016c5a  mov     r8, r14; unsigned __int8 *
0x180016c5d  imul    rcx, rax, 58h ; 'X'
0x180016c61  lea     rax, [rsp+68h+arg_0]
0x180016c66  mov     [rsp+68h+var_40], rax; unsigned int *
0x180016c6b  add     rcx, 8
0x180016c6f  mov     eax, [rbx+17Ch]
0x180016c75  add     rcx, rbx; this
0x180016c78  mov     [rsp+68h+var_48], eax; unsigned int
0x180016c7c  call    ?Read@CFileBuffer@@QEAAHKPEAEKKPEAK@Z; CFileBuffer::Read(ulong,uchar *,ulong,ulong,ulong *)
0x180016c81  test    eax, eax
0x180016c83  jz      short loc_180016CFF
0x180016c85  mov     ecx, [rsp+68h+arg_0]
0x180016c89  add     [rbx+174h], ecx
0x180016c8f  add     r14, rcx
0x180016c92  add     [r13+0], ecx
0x180016c96  sub     edi, ecx
0x180016c98  mov     [rsp+68h+arg_8], r14
0x180016c9d  test    esi, esi
0x180016c9f  jz      short loc_180016CF2
0x180016ca1  movsxd  rcx, dword ptr [rbx+16Ch]
0x180016ca8  lea     eax, [rcx+1]
0x180016cab  cdq
0x180016cac  idiv    dword ptr [rbx+168h]
0x180016cb2  imul    rax, rcx, 58h ; 'X'
0x180016cb6  movsxd  r8, edx
0x180016cb9  mov     [rbx+170h], r8d
0x180016cc0  cmp     dword ptr [rax+rbx+8], 2
0x180016cc5  jz      short loc_180016CD7
0x180016cc7  mov     ecx, [rax+rbx+24h]
0x180016ccb  test    ecx, ecx
0x180016ccd  jz      short loc_180016CD7
0x180016ccf  mov     edx, [rax+rbx+28h]
0x180016cd3  add     edx, ecx
0x180016cd5  jmp     short loc_180016CD9
0x180016cd7  xor     edx, edx; unsigned int
0x180016cd9  imul    rcx, r8, 58h ; 'X'
0x180016cdd  mov     r8d, [rbx+17Ch]; unsigned int
0x180016ce4  add     rcx, 8
0x180016ce8  add     rcx, rbx; this
0x180016ceb  call    ?ReadAhead@CFileBuffer@@QEAAXKK@Z; CFileBuffer::ReadAhead(ulong,ulong)
0x180016cf0  xor     esi, esi
0x180016cf2  test    edi, edi
0x180016cf4  jnz     loc_180016B01
0x180016cfa  mov     eax, r15d
0x180016cfd  jmp     short loc_180016D01
0x180016cff  xor     eax, eax
0x180016d01  mov     rbx, [rsp+68h+arg_10]
0x180016d09  add     rsp, 30h
0x180016d0d  pop     r15
0x180016d0f  pop     r14
0x180016d11  pop     r13
0x180016d13  pop     r12
0x180016d15  pop     rdi
0x180016d16  pop     rsi
0x180016d17  pop     rbp
0x180016d18  retn
```
