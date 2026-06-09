# ApplyPKCS1SigningFormat

- ea: `0x18000f6a8`
- end: `0x18000f81a`
- name: `ApplyPKCS1SigningFormat`
- size: `370`
- prototype: `__int64 __fastcall(void *Src, size_t Size, const void *, unsigned int, _WORD *, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012a70`
- `0x180016b60`

## callees

- `0x180005060`
- `0x18000f6a8`
- `0x18001b79d`
- `0x18001b7a9`

## string_xrefs

- `0x18000f714`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall ApplyPKCS1SigningFormat(
        void *Src,
        size_t Size,
        const void *a3,
        unsigned int a4,
        _WORD *a5,
        unsigned int a6,
        int a7)
{
  size_t v7; // rdi
  size_t v9; // rbp
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int v14; // r14d
  unsigned int v15; // r13d
  size_t v16; // r12
  unsigned int v17; // ebx
  char *v18; // rcx

  v7 = (unsigned int)Size;
  v9 = a4;
  if ( !a7 )
  {
    v10 = a4;
    goto LABEL_9;
  }
  if ( !Src )
  {
    if ( (_DWORD)Size )
      return (unsigned int)-1073741811;
    goto LABEL_7;
  }
  if ( !(_DWORD)Size )
  {
LABEL_7:
    v10 = a4 + 2;
    goto LABEL_9;
  }
  v10 = Size + a4 + 6;
LABEL_9:
  if ( v10 > 0x80 )
  {
    v11 = -1073741595;
    v12 = 95;
    v13 = 3221225701LL;
LABEL_11:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c", v12);
    return v11;
  }
  if ( v10 + 11 > a6 )
  {
    v11 = -1073741811;
    v12 = 105;
    v13 = 3221225485LL;
    goto LABEL_11;
  }
  v14 = a6 - v10;
  v15 = v14 - 3;
  *a5 = 256;
  *((_BYTE *)a5 + v14 - 1) = 0;
  v16 = a6 - v10 - 3;
  memset_0(a5 + 1, 255, v16);
  if ( a7 )
  {
    if ( Src && (_DWORD)v7 )
    {
      *((_BYTE *)a5 + v14) = 48;
      *((_BYTE *)a5 + v15 + 4) = v10 - 2;
      *((_BYTE *)a5 + v15 + 5) = 48;
      v17 = 5;
      *((_BYTE *)a5 + v15 + 6) = v7;
      memcpy_0((char *)a5 + v16 + 7, Src, v7);
    }
    else
    {
      v17 = 1;
    }
    *((_BYTE *)a5 + (unsigned int)v7 + v15 + v17 + 2) = 4;
    *((_BYTE *)a5 + (unsigned int)v7 + v14 + v17) = v9;
    v18 = (char *)a5 + v16 + v17 + v7 + 4;
  }
  else
  {
    v18 = (char *)a5 + v16 + 3;
  }
  memcpy_0(v18, a3, v9);
  return 0;
}

```

## disassembly

```asm
0x18000f6a8  mov     [rsp+Src], r8
0x18000f6ad  push    rbx
0x18000f6ae  push    rbp
0x18000f6af  push    rsi
0x18000f6b0  push    rdi
0x18000f6b1  push    r12
0x18000f6b3  push    r13
0x18000f6b5  push    r14
0x18000f6b7  push    r15
0x18000f6b9  sub     rsp, 28h
0x18000f6bd  mov     edi, edx
0x18000f6bf  mov     r15, rcx
0x18000f6c2  xor     edx, edx
0x18000f6c4  mov     ebp, r9d
0x18000f6c7  cmp     [rsp+68h+arg_30], edx
0x18000f6ce  jz      short loc_18000F6F3
0x18000f6d0  test    rcx, rcx
0x18000f6d3  jz      short loc_18000F6E0
0x18000f6d5  test    edi, edi
0x18000f6d7  jz      short loc_18000F6EE
0x18000f6d9  lea     ebx, [rbp+6]
0x18000f6dc  add     ebx, edi
0x18000f6de  jmp     short loc_18000F6F5
0x18000f6e0  test    edi, edi
0x18000f6e2  jz      short loc_18000F6EE
0x18000f6e4  mov     ebx, 0C000000Dh
0x18000f6e9  jmp     loc_18000F806
0x18000f6ee  lea     ebx, [rbp+2]
0x18000f6f1  jmp     short loc_18000F6F5
0x18000f6f3  mov     ebx, ebp
0x18000f6f5  cmp     ebx, 80h
0x18000f6fb  jbe     short loc_18000F725
0x18000f6fd  mov     ebx, 0C00000E5h
0x18000f702  mov     r9d, 5Fh ; '_'
0x18000f708  mov     ecx, 0C00000E5h
0x18000f70d  lea     rdx, aStatus; "Status"
0x18000f714  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f71b  call    DebugTraceError
0x18000f720  jmp     loc_18000F806
0x18000f725  mov     r14d, [rsp+68h+arg_28]
0x18000f72d  lea     eax, [rbx+0Bh]
0x18000f730  cmp     eax, r14d
0x18000f733  jbe     short loc_18000F747
0x18000f735  mov     ebx, 0C000000Dh
0x18000f73a  mov     r9d, 69h ; 'i'
0x18000f740  mov     ecx, 0C000000Dh
0x18000f745  jmp     short loc_18000F70D
0x18000f747  mov     rsi, [rsp+68h+arg_20]
0x18000f74f  sub     r14d, ebx
0x18000f752  lea     r13d, [r14-3]
0x18000f756  mov     word ptr [rsi], 100h
0x18000f75b  lea     eax, [r13+2]
0x18000f75f  mov     r8d, r13d; Size
0x18000f762  mov     [rax+rsi], dl
0x18000f765  lea     rcx, [rsi+2]; void *
0x18000f769  mov     edx, 0FFh; Val
0x18000f76e  mov     r12d, r13d
0x18000f771  call    memset_0
0x18000f776  cmp     [rsp+68h+arg_30], 0
0x18000f77e  jz      short loc_18000F7ED
0x18000f780  test    r15, r15
0x18000f783  jz      short loc_18000F7C1
0x18000f785  test    edi, edi
0x18000f787  jz      short loc_18000F7C1
0x18000f789  lea     eax, [r13+4]
0x18000f78d  mov     byte ptr [r14+rsi], 30h ; '0'
0x18000f792  sub     bl, 2
0x18000f795  lea     rcx, [rsi+7]
0x18000f799  mov     [rax+rsi], bl
0x18000f79c  mov     r8, rdi; Size
0x18000f79f  lea     eax, [r13+5]
0x18000f7a3  add     rcx, r12; void *
0x18000f7a6  mov     byte ptr [rax+rsi], 30h ; '0'
0x18000f7aa  mov     rdx, r15; Src
0x18000f7ad  lea     eax, [r13+6]
0x18000f7b1  mov     ebx, 5
0x18000f7b6  mov     [rax+rsi], dil
0x18000f7ba  call    memcpy_0
0x18000f7bf  jmp     short loc_18000F7C6
0x18000f7c1  mov     ebx, 1
0x18000f7c6  lea     ecx, [rbx+2]
0x18000f7c9  add     ecx, r13d
0x18000f7cc  lea     eax, [r14+rbx]
0x18000f7d0  add     eax, edi
0x18000f7d2  add     ecx, edi
0x18000f7d4  mov     byte ptr [rcx+rsi], 4
0x18000f7d8  lea     rcx, [rdi+4]
0x18000f7dc  mov     [rax+rsi], bpl
0x18000f7e0  mov     eax, ebx
0x18000f7e2  add     rax, r12
0x18000f7e5  add     rcx, rax
0x18000f7e8  add     rcx, rsi
0x18000f7eb  jmp     short loc_18000F7F4
0x18000f7ed  lea     rcx, [rsi+3]
0x18000f7f1  add     rcx, r12; void *
0x18000f7f4  mov     rdx, [rsp+68h+Src]; Src
0x18000f7fc  mov     r8, rbp; Size
0x18000f7ff  call    memcpy_0
0x18000f804  xor     ebx, ebx
0x18000f806  mov     eax, ebx
0x18000f808  add     rsp, 28h
0x18000f80c  pop     r15
0x18000f80e  pop     r14
0x18000f810  pop     r13
0x18000f812  pop     r12
0x18000f814  pop     rdi
0x18000f815  pop     rsi
0x18000f816  pop     rbp
0x18000f817  pop     rbx
0x18000f818  retn
```
