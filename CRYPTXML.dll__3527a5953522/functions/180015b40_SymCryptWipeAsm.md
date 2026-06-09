# SymCryptWipeAsm

- ea: `0x180015b40`
- end: `0x180015bf1`
- name: `SymCryptWipeAsm`
- size: `177`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180011eec`
- `0x180014590`
- `0x180017c58`
- `0x180017f34`
- `0x180017fec`
- `0x1800180e0`

## callees

- `0x180015b40`

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
0x180015b40  xorps   xmm0, xmm0
0x180015b43  cmp     rdx, 10h
0x180015b47  jb      loc_180015BC0
0x180015b4d  test    rcx, 0Fh
0x180015b54  jnz     short loc_180015B94
0x180015b56  test    rdx, 10h
0x180015b5d  movaps  xmmword ptr [rcx], xmm0
0x180015b60  lea     r8, [rcx+10h]
0x180015b64  cmovnz  rcx, r8
0x180015b68  sub     rdx, 20h ; ' '
0x180015b6c  jb      short loc_180015B81
0x180015b6e  xchg    ax, ax
0x180015b70  movaps  xmmword ptr [rcx], xmm0
0x180015b73  movaps  xmmword ptr [rcx+10h], xmm0
0x180015b77  add     rcx, 20h ; ' '
0x180015b7b  sub     rdx, 20h ; ' '
0x180015b7f  jnb     short loc_180015B70
0x180015b81  and     edx, 0Fh
0x180015b84  jnz     short loc_180015B87
0x180015b86  retn
0x180015b87  xor     eax, eax
0x180015b89  mov     [rcx+rdx-10h], rax
0x180015b8e  mov     [rcx+rdx-8], rax
0x180015b93  retn
0x180015b94  xor     eax, eax
0x180015b96  mov     [rcx], rax
0x180015b99  mov     [rcx+8], rax
0x180015b9d  mov     eax, ecx
0x180015b9f  neg     eax
0x180015ba1  and     eax, 0Fh
0x180015ba4  add     rcx, rax
0x180015ba7  sub     rdx, rax
0x180015baa  cmp     rdx, 10h
0x180015bae  jnb     short loc_180015B56
0x180015bb0  xor     eax, eax
0x180015bb2  mov     [rcx+rdx-10h], rax
0x180015bb7  mov     [rcx+rdx-8], rax
0x180015bbc  retn
0x180015bc0  xor     eax, eax
0x180015bc2  cmp     edx, 8
0x180015bc5  jb      short loc_180015BD0
0x180015bc7  mov     [rcx], rax
0x180015bca  mov     [rcx+rdx-8], rax
0x180015bcf  retn
0x180015bd0  cmp     edx, 4
0x180015bd3  jb      short loc_180015BDC
0x180015bd5  mov     [rcx], eax
0x180015bd7  mov     [rcx+rdx-4], eax
0x180015bdb  retn
0x180015bdc  cmp     edx, 2
0x180015bdf  jb      short loc_180015BEA
0x180015be1  mov     [rcx], ax
0x180015be4  mov     [rcx+rdx-2], ax
0x180015be9  retn
0x180015bea  or      edx, edx
0x180015bec  jz      short locret_180015BF0
0x180015bee  mov     [rcx], al
0x180015bf0  retn
```
