# SymCryptWipeAsm

- ea: `0x180009170`
- end: `0x180009221`
- name: `SymCryptWipeAsm`
- size: `177`
- prototype: ``
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x18004a3c0`
- `0x18005158c`
- `0x180051848`
- `0x180051b68`
- `0x180051c08`
- `0x1800537b0`
- `0x180053e58`
- `0x1800540bc`
- `0x1800541c8`
- `0x180054310`
- `0x180054e10`
- `0x180054fe4`
- `0x1800550e8`
- `0x180055314`
- `0x1800553f8`
- `0x1800554b0`
- `0x18005575c`
- `0x18005594c`
- `0x180055d38`
- `0x180055dc4`
- `0x180055ea8`
- `0x180056054`
- `0x1800561d0`
- `0x180056c24`
- `0x180056dc0`
- `0x1800572e0`
- `0x180057380`
- `0x180057630`
- `0x180057a20`
- `0x180057b60`
- `0x180057c70`
- `0x180058028`
- `0x180058090`

## callees

- `0x180009170`

## pseudocode

```c
__int64 __fastcall SymCryptWipeAsm(__int64 a1, unsigned __int64 a2)
{
  bool v2; // cf
  unsigned __int64 i; // rdx
  unsigned int v4; // edx
  __int64 result; // rax

  if ( a2 < 0x10 )
  {
    result = 0;
    if ( (unsigned int)a2 < 8 )
    {
      if ( (unsigned int)a2 < 4 )
      {
        if ( (unsigned int)a2 < 2 )
        {
          if ( (_DWORD)a2 )
            *(_BYTE *)a1 = 0;
        }
        else
        {
          *(_WORD *)a1 = 0;
          *(_WORD *)(a1 + a2 - 2) = 0;
        }
      }
      else
      {
        *(_DWORD *)a1 = 0;
        *(_DWORD *)(a1 + a2 - 4) = 0;
      }
    }
    else
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + a2 - 8) = 0;
    }
  }
  else if ( (a1 & 0xF) != 0
         && (*(_QWORD *)a1 = 0, *(_QWORD *)(a1 + 8) = 0, result = -(int)a1 & 0xF, a1 += result, a2 -= result, a2 < 0x10) )
  {
    result = 0;
    *(_QWORD *)(a1 + a2 - 16) = 0;
    *(_QWORD *)(a1 + a2 - 8) = 0;
  }
  else
  {
    *(_OWORD *)a1 = 0;
    if ( (a2 & 0x10) != 0 )
      a1 += 16;
    v2 = a2 < 0x20;
    for ( i = a2 - 32; !v2; i -= 32LL )
    {
      *(_OWORD *)a1 = 0;
      *(_OWORD *)(a1 + 16) = 0;
      a1 += 32;
      v2 = i < 0x20;
    }
    v4 = i & 0xF;
    if ( v4 )
    {
      result = 0;
      *(_QWORD *)(a1 + v4 - 16) = 0;
      *(_QWORD *)(a1 + v4 - 8) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009170  xorps   xmm0, xmm0
0x180009173  cmp     rdx, 10h
0x180009177  jb      loc_1800091F0
0x18000917d  test    rcx, 0Fh
0x180009184  jnz     short loc_1800091C4
0x180009186  test    rdx, 10h
0x18000918d  movaps  xmmword ptr [rcx], xmm0
0x180009190  lea     r8, [rcx+10h]
0x180009194  cmovnz  rcx, r8
0x180009198  sub     rdx, 20h ; ' '
0x18000919c  jb      short loc_1800091B1
0x18000919e  xchg    ax, ax
0x1800091a0  movaps  xmmword ptr [rcx], xmm0
0x1800091a3  movaps  xmmword ptr [rcx+10h], xmm0
0x1800091a7  add     rcx, 20h ; ' '
0x1800091ab  sub     rdx, 20h ; ' '
0x1800091af  jnb     short loc_1800091A0
0x1800091b1  and     edx, 0Fh
0x1800091b4  jnz     short loc_1800091B7
0x1800091b6  retn
0x1800091b7  xor     eax, eax
0x1800091b9  mov     [rcx+rdx-10h], rax
0x1800091be  mov     [rcx+rdx-8], rax
0x1800091c3  retn
0x1800091c4  xor     eax, eax
0x1800091c6  mov     [rcx], rax
0x1800091c9  mov     [rcx+8], rax
0x1800091cd  mov     eax, ecx
0x1800091cf  neg     eax
0x1800091d1  and     eax, 0Fh
0x1800091d4  add     rcx, rax
0x1800091d7  sub     rdx, rax
0x1800091da  cmp     rdx, 10h
0x1800091de  jnb     short loc_180009186
0x1800091e0  xor     eax, eax
0x1800091e2  mov     [rcx+rdx-10h], rax
0x1800091e7  mov     [rcx+rdx-8], rax
0x1800091ec  retn
0x1800091f0  xor     eax, eax
0x1800091f2  cmp     edx, 8
0x1800091f5  jb      short loc_180009200
0x1800091f7  mov     [rcx], rax
0x1800091fa  mov     [rcx+rdx-8], rax
0x1800091ff  retn
0x180009200  cmp     edx, 4
0x180009203  jb      short loc_18000920C
0x180009205  mov     [rcx], eax
0x180009207  mov     [rcx+rdx-4], eax
0x18000920b  retn
0x18000920c  cmp     edx, 2
0x18000920f  jb      short loc_18000921A
0x180009211  mov     [rcx], ax
0x180009214  mov     [rcx+rdx-2], ax
0x180009219  retn
0x18000921a  or      edx, edx
0x18000921c  jz      short locret_180009220
0x18000921e  mov     [rcx], al
0x180009220  retn
```
