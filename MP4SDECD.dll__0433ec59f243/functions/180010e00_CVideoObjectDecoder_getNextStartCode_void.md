# CVideoObjectDecoder::getNextStartCode(void)

- ea: `0x180010e00`
- end: `0x180011115`
- name: `?getNextStartCode@CVideoObjectDecoder@@QEAAJXZ`
- size: `789`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ddf4`
- `0x18000ebd0`
- `0x18001f53c`

## callees

- `0x180002cc0`
- `0x180010e00`
- `0x1800176e4`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::getNextStartCode(CVideoObjectDecoder *this)
{
  CInputBitStream *v2; // rbx
  __int64 v3; // r15
  int v4; // r13d
  unsigned int v5; // r12d
  int Peek; // eax
  int v7; // r8d
  unsigned int v8; // eax
  __int64 result; // rax
  int v10; // r9d
  unsigned int v11; // r9d
  int v12; // ecx
  int v13; // ecx
  unsigned __int8 *v14; // r10
  int v15; // edx
  int v16; // r8d
  int v17; // edx
  int v18; // eax
  int v19; // eax
  unsigned int v20; // r8d
  int v21; // ecx
  __int64 v22; // rax
  unsigned int v23; // r8d
  int v24; // ecx

  *(_DWORD *)(*((_QWORD *)this + 675) + 16LL) &= 0xFFFFFFF8;
  while ( 1 )
  {
    v2 = (CInputBitStream *)*((_QWORD *)this + 675);
    if ( *((_DWORD *)v2 + 5) )
      goto LABEL_18;
    v3 = *((unsigned int *)v2 + 4);
    v4 = *((_DWORD *)v2 + 2);
    if ( (unsigned int)(v3 + 8 * v4) >= 0x18 )
      break;
LABEL_8:
    v7 = *((_DWORD *)v2 + 2);
    if ( (unsigned int)(8 * v7) >= 8 || (unsigned int)(*((_DWORD *)v2 + 4) + 8 * v7) >= 8 )
    {
      v8 = *((_DWORD *)v2 + 4);
      if ( v8 < 8 )
      {
        v11 = 8 - v8;
        if ( v7 < 4 )
        {
          v13 = 0;
          *(_QWORD *)((char *)v2 + 12) = 0;
          if ( v7 )
          {
            v14 = *(unsigned __int8 **)v2;
            v15 = 0;
            v16 = v7 - 1;
            do
            {
              v17 = v15 << 8;
              v13 += 8;
              *((_DWORD *)v2 + 3) = v17;
              v18 = *v14++;
              v15 = v18 | v17;
              *((_DWORD *)v2 + 2) = v16;
              v19 = v16;
              *(_QWORD *)v2 = v14;
              --v16;
              *((_DWORD *)v2 + 3) = v15;
              *((_DWORD *)v2 + 4) = v13;
            }
            while ( v19 );
          }
          *((_DWORD *)v2 + 4) = v13 - v11;
        }
        else
        {
          v12 = *(unsigned __int8 *)(*(_QWORD *)v2 + 3LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)v2 + 2LL)
                | (((**(unsigned __int8 **)v2 << 8) | *(unsigned __int8 *)(*(_QWORD *)v2 + 1LL)) << 8)) << 8);
          *(_QWORD *)v2 += 4LL;
          *((_DWORD *)v2 + 2) = v7 - 4;
          *((_DWORD *)v2 + 3) = v12;
          *((_DWORD *)v2 + 4) = 32 - v11;
        }
      }
      else
      {
        *((_DWORD *)v2 + 4) = v8 - 8;
      }
      goto LABEL_11;
    }
LABEL_18:
    *((_DWORD *)v2 + 5) = 1;
LABEL_11:
    if ( *(_DWORD *)(*((_QWORD *)this + 675) + 20LL) )
      return 4;
  }
  v5 = *((_DWORD *)v2 + 3);
  if ( (unsigned int)v3 < 0x18 )
  {
    v10 = *((_DWORD *)&GetMask + v3) & v5;
    if ( v4 < 4 )
      Peek = CInputBitStream::finalLoadPeek(*((CInputBitStream **)this + 675), v10, 24 - (int)v3);
    else
      Peek = (v10 << (24 - v3))
           | *((_DWORD *)&GetMask + (unsigned int)(24 - v3))
           & ((unsigned int)(*(unsigned __int8 *)(*(_QWORD *)v2 + 3LL)
                           | ((*(unsigned __int8 *)(*(_QWORD *)v2 + 2LL)
                             | ((*(unsigned __int8 *)(*(_QWORD *)v2 + 1LL) | (**(unsigned __int8 **)v2 << 8)) << 8)) << 8)) >> (32 - (24 - v3)));
  }
  else
  {
    Peek = (v5 >> (v3 - 24)) & 0xFFFFFF;
  }
  if ( Peek != 1 )
  {
    if ( (Peek & 0xFFFFFC) == 0x80 )
    {
      if ( (unsigned int)(8 * v4) < 0x16 && (unsigned int)(*((_DWORD *)v2 + 4) + 8 * v4) < 0x16 )
      {
        *((_DWORD *)v2 + 5) = 1;
      }
      else
      {
        v22 = *((unsigned int *)v2 + 4);
        if ( (unsigned int)v22 >= 0x16 )
        {
          *((_DWORD *)v2 + 4) = v22 - 22;
        }
        else
        {
          v23 = 22 - v22;
          if ( v4 >= 4 )
          {
            v24 = *(unsigned __int8 *)(*(_QWORD *)v2 + 3LL)
                | ((*(unsigned __int8 *)(*(_QWORD *)v2 + 2LL)
                  | (((**(unsigned __int8 **)v2 << 8) | *(unsigned __int8 *)(*(_QWORD *)v2 + 1LL)) << 8)) << 8);
            *(_QWORD *)v2 += 4LL;
            *((_DWORD *)v2 + 3) = v24;
            *((_DWORD *)v2 + 2) = v4 - 4;
            result = 1;
            *((_DWORD *)v2 + 4) = 32 - v23;
            return result;
          }
          CInputBitStream::finalLoad(v2, v5 & *((_DWORD *)&GetMask + v22), v23);
        }
      }
      return 1;
    }
    goto LABEL_8;
  }
  if ( (unsigned int)v3 < 0x18 )
  {
    v20 = 24 - v3;
    if ( v4 < 4 )
    {
      CInputBitStream::finalLoad(v2, v5 & *((_DWORD *)&GetMask + v3), v20);
    }
    else
    {
      v21 = *(unsigned __int8 *)(*(_QWORD *)v2 + 3LL)
          | ((*(unsigned __int8 *)(*(_QWORD *)v2 + 2LL)
            | (((**(unsigned __int8 **)v2 << 8) | *(unsigned __int8 *)(*(_QWORD *)v2 + 1LL)) << 8)) << 8);
      *(_QWORD *)v2 += 4LL;
      *((_DWORD *)v2 + 3) = v21;
      *((_DWORD *)v2 + 2) = v4 - 4;
      *((_DWORD *)v2 + 4) = 32 - v20;
    }
  }
  else
  {
    *((_DWORD *)v2 + 4) = v3 - 24;
  }
  return 0;
}

```

## disassembly

```asm
0x180010e00  push    rbx
0x180010e02  push    rbp
0x180010e03  push    rsi
0x180010e04  push    rdi
0x180010e05  push    r14
0x180010e07  sub     rsp, 20h
0x180010e0b  mov     rax, [rcx+1518h]
0x180010e12  lea     r11, ?GetMask@@3QBKB; ulong const near * const GetMask
0x180010e19  mov     [rsp+48h+arg_0], r12
0x180010e1e  mov     rbp, rcx
0x180010e21  mov     [rsp+48h+arg_8], r13
0x180010e26  mov     [rsp+48h+arg_10], r15
0x180010e2b  and     dword ptr [rax+10h], 0FFFFFFF8h
0x180010e2f  mov     rbx, [rbp+1518h]
0x180010e36  mov     r10d, 20h ; ' '
0x180010e3c  mov     r8d, 18h
0x180010e42  mov     edi, [rbx+14h]
0x180010e45  test    edi, edi
0x180010e47  jnz     loc_180010F84
0x180010e4d  mov     r15d, [rbx+10h]
0x180010e51  mov     r13d, [rbx+8]
0x180010e55  lea     eax, [r15+r13*8]
0x180010e59  cmp     eax, r8d
0x180010e5c  jb      short loc_180010E8E
0x180010e5e  mov     r12d, [rbx+0Ch]
0x180010e62  cmp     r15d, r8d
0x180010e65  jb      short loc_180010ED4
0x180010e67  lea     ecx, [r15-18h]
0x180010e6b  mov     eax, r12d
0x180010e6e  shr     eax, cl
0x180010e70  and     eax, 0FFFFFFh
0x180010e75  cmp     eax, 1
0x180010e78  jz      loc_180010FDB
0x180010e7e  and     eax, 0FFFFFCh
0x180010e83  cmp     eax, 80h
0x180010e88  jz      loc_180011086
0x180010e8e  test    edi, edi
0x180010e90  jnz     loc_180010F84
0x180010e96  mov     r8d, [rbx+8]
0x180010e9a  lea     ecx, ds:0[r8*8]
0x180010ea2  cmp     ecx, 8
0x180010ea5  jb      loc_180010F78
0x180010eab  mov     eax, [rbx+10h]
0x180010eae  cmp     eax, 8
0x180010eb1  jb      short loc_180010F29
0x180010eb3  add     eax, 0FFFFFFF8h
0x180010eb6  mov     [rbx+10h], eax
0x180010eb9  mov     rax, [rbp+1518h]
0x180010ec0  cmp     dword ptr [rax+14h], 0
0x180010ec4  jz      loc_180010E2F
0x180010eca  mov     eax, 4
0x180010ecf  jmp     loc_180010FEA
0x180010ed4  mov     r9d, r12d
0x180010ed7  sub     r8d, r15d; unsigned int
0x180010eda  and     r9d, [r11+r15*4]
0x180010ede  cmp     r13d, 4
0x180010ee2  jl      loc_180011059
0x180010ee8  mov     rdx, [rbx]
0x180010eeb  movzx   ecx, byte ptr [rdx+1]
0x180010eef  movzx   eax, byte ptr [rdx]
0x180010ef2  shl     eax, 8
0x180010ef5  or      eax, ecx
0x180010ef7  movzx   ecx, byte ptr [rdx+2]
0x180010efb  movzx   edx, byte ptr [rdx+3]
0x180010eff  shl     eax, 8
0x180010f02  or      eax, ecx
0x180010f04  mov     ecx, r10d
0x180010f07  shl     eax, 8
0x180010f0a  sub     ecx, r8d
0x180010f0d  or      eax, edx
0x180010f0f  shr     eax, cl
0x180010f11  mov     ecx, r8d
0x180010f14  and     eax, [r11+r8*4]
0x180010f18  shl     r9d, cl
0x180010f1b  or      eax, r9d
0x180010f1e  mov     r8d, 18h
0x180010f24  jmp     loc_180010E75
0x180010f29  mov     r9d, 8
0x180010f2f  sub     r9d, eax
0x180010f32  cmp     r8d, 4
0x180010f36  jl      short loc_180010F90
0x180010f38  mov     rdx, [rbx]
0x180010f3b  movzx   eax, byte ptr [rdx]
0x180010f3e  movzx   ecx, byte ptr [rdx+1]
0x180010f42  shl     eax, 8
0x180010f45  or      ecx, eax
0x180010f47  movzx   eax, byte ptr [rdx+2]
0x180010f4b  shl     ecx, 8
0x180010f4e  or      ecx, eax
0x180010f50  movzx   eax, byte ptr [rdx+3]
0x180010f54  shl     ecx, 8
0x180010f57  or      ecx, eax
0x180010f59  lea     rax, [rdx+4]
0x180010f5d  mov     [rbx], rax
0x180010f60  lea     eax, [r8-4]
0x180010f64  mov     [rbx+8], eax
0x180010f67  mov     eax, r10d
0x180010f6a  sub     eax, r9d
0x180010f6d  mov     [rbx+0Ch], ecx
0x180010f70  mov     [rbx+10h], eax
0x180010f73  jmp     loc_180010EB9
0x180010f78  add     ecx, [rbx+10h]
0x180010f7b  cmp     ecx, 8
0x180010f7e  jnb     loc_180010EAB
0x180010f84  mov     dword ptr [rbx+14h], 1
0x180010f8b  jmp     loc_180010EB9
0x180010f90  xor     ecx, ecx
0x180010f92  mov     qword ptr [rbx+0Ch], 0
0x180010f9a  test    r8d, r8d
0x180010f9d  jz      short loc_180010FD0
0x180010f9f  mov     r10, [rbx]
0x180010fa2  xor     edx, edx
0x180010fa4  dec     r8d
0x180010fa7  shl     edx, 8
0x180010faa  add     ecx, 8
0x180010fad  mov     [rbx+0Ch], edx
0x180010fb0  movzx   eax, byte ptr [r10]
0x180010fb4  inc     r10
0x180010fb7  or      edx, eax
0x180010fb9  mov     [rbx+8], r8d
0x180010fbd  mov     eax, r8d
0x180010fc0  mov     [rbx], r10
0x180010fc3  dec     r8d
0x180010fc6  mov     [rbx+0Ch], edx
0x180010fc9  mov     [rbx+10h], ecx
0x180010fcc  test    eax, eax
0x180010fce  jnz     short loc_180010FA7
0x180010fd0  sub     ecx, r9d
0x180010fd3  mov     [rbx+10h], ecx
0x180010fd6  jmp     loc_180010EB9
0x180010fdb  cmp     r15d, 18h
0x180010fdf  jb      short loc_180011004
0x180010fe1  lea     eax, [r15-18h]
0x180010fe5  mov     [rbx+10h], eax
0x180010fe8  xor     eax, eax
0x180010fea  mov     r15, [rsp+48h+arg_10]
0x180010fef  mov     r13, [rsp+48h+arg_8]
0x180010ff4  mov     r12, [rsp+48h+arg_0]
0x180010ff9  add     rsp, 20h
0x180010ffd  pop     r14
0x180010fff  pop     rdi
0x180011000  pop     rsi
0x180011001  pop     rbp
0x180011002  pop     rbx
0x180011003  retn
0x180011004  sub     r8d, r15d; unsigned int
0x180011007  cmp     r13d, 4
0x18001100b  jl      short loc_180011048
0x18001100d  mov     rdx, [rbx]
0x180011010  movzx   eax, byte ptr [rdx]
0x180011013  movzx   ecx, byte ptr [rdx+1]
0x180011017  shl     eax, 8
0x18001101a  or      ecx, eax
0x18001101c  movzx   eax, byte ptr [rdx+2]
0x180011020  shl     ecx, 8
0x180011023  or      ecx, eax
0x180011025  movzx   eax, byte ptr [rdx+3]
0x180011029  shl     ecx, 8
0x18001102c  or      ecx, eax
0x18001102e  lea     rax, [rdx+4]
0x180011032  mov     [rbx], rax
0x180011035  sub     r10d, r8d
0x180011038  lea     eax, [r13-4]
0x18001103c  mov     [rbx+0Ch], ecx
0x18001103f  mov     [rbx+8], eax
0x180011042  mov     [rbx+10h], r10d
0x180011046  jmp     short loc_180010FE8
0x180011048  mov     edx, [r11+r15*4]
0x18001104c  mov     rcx, rbx; this
0x18001104f  and     edx, r12d; unsigned int
0x180011052  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x180011057  jmp     short loc_180010FE8
0x180011059  mov     edx, r9d; unsigned int
0x18001105c  mov     rcx, rbx; this
0x18001105f  call    ?finalLoadPeek@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoadPeek(ulong,ulong)
0x180011064  mov     r10d, 20h ; ' '
0x18001106a  lea     r11, ?GetMask@@3QBKB; ulong const near * const GetMask
0x180011071  jmp     loc_180010F1E
0x180011076  add     eax, 0FFFFFFEAh
0x180011079  mov     [rbx+10h], eax
0x18001107c  mov     eax, 1
0x180011081  jmp     loc_180010FEA
0x180011086  lea     ecx, ds:0[r13*8]
0x18001108e  cmp     ecx, 16h
0x180011091  jnb     short loc_18001109B
0x180011093  add     ecx, [rbx+10h]
0x180011096  cmp     ecx, 16h
0x180011099  jb      short loc_180011109
0x18001109b  mov     eax, [rbx+10h]
0x18001109e  cmp     eax, 16h
0x1800110a1  jnb     short loc_180011076
0x1800110a3  mov     r8d, 16h
0x1800110a9  sub     r8d, eax; unsigned int
0x1800110ac  cmp     r13d, 4
0x1800110b0  jl      short loc_1800110F5
0x1800110b2  mov     rdx, [rbx]
0x1800110b5  movzx   eax, byte ptr [rdx]
0x1800110b8  movzx   ecx, byte ptr [rdx+1]
0x1800110bc  shl     eax, 8
0x1800110bf  or      ecx, eax
0x1800110c1  movzx   eax, byte ptr [rdx+2]
0x1800110c5  shl     ecx, 8
0x1800110c8  or      ecx, eax
0x1800110ca  movzx   eax, byte ptr [rdx+3]
0x1800110ce  shl     ecx, 8
0x1800110d1  or      ecx, eax
0x1800110d3  lea     rax, [rdx+4]
0x1800110d7  mov     [rbx], rax
0x1800110da  sub     r10d, r8d
0x1800110dd  lea     eax, [r13-4]
0x1800110e1  mov     [rbx+0Ch], ecx
0x1800110e4  mov     [rbx+8], eax
0x1800110e7  mov     eax, 1
0x1800110ec  mov     [rbx+10h], r10d
0x1800110f0  jmp     loc_180010FEA
0x1800110f5  mov     edx, [r11+rax*4]
0x1800110f9  mov     rcx, rbx; this
0x1800110fc  and     edx, r12d; unsigned int
0x1800110ff  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x180011104  jmp     loc_18001107C
0x180011109  mov     dword ptr [rbx+14h], 1
0x180011110  jmp     loc_18001107C
```
