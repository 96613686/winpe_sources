# CVideoObjectDecoder::clipMVInRangeUV(long &,long &,long,long)

- ea: `0x180019b20`
- end: `0x180019b88`
- name: `?clipMVInRangeUV@CVideoObjectDecoder@@AEAAXAEAJ0JJ@Z`
- size: `104`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, int *, int *, int, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e5c`
- `0x180017a40`
- `0x180036f80`
- `0x1800372f8`

## callees

- `0x180019b20`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::clipMVInRangeUV(CVideoObjectDecoder *this, int *a2, int *a3, int a4)
{
  int v4; // r10d
  int v5; // eax
  int v6; // eax
  int v7; // eax

  v4 = *a2;
  if ( a4 )
  {
    v7 = *((_DWORD *)this + 3) - 16;
    if ( v4 < v7 || (v7 = *((_DWORD *)this + 5), v4 > v7) )
      *a2 = v7;
    v6 = *((_DWORD *)this + 4) - 16;
    if ( *a3 < v6 )
      goto LABEL_7;
    v6 = *((_DWORD *)this + 6);
    if ( *a3 > v6 )
      goto LABEL_7;
  }
  else
  {
    v5 = *((_DWORD *)this + 341);
    if ( v4 < v5 || (v5 = *((_DWORD *)this + 342), v4 > v5) )
      *a2 = v5;
    v6 = *((_DWORD *)this + 343);
    if ( *a3 < v6 || (v6 = *((_DWORD *)this + 344), *a3 > v6) )
LABEL_7:
      *a3 = v6;
  }
}

```

## disassembly

```asm
0x180019b20  mov     r10d, [rdx]
0x180019b23  test    r9d, r9d
0x180019b26  jnz     short loc_180019B5B
0x180019b28  mov     eax, [rcx+554h]
0x180019b2e  cmp     r10d, eax
0x180019b31  jl      short loc_180019B3E
0x180019b33  mov     eax, [rcx+558h]
0x180019b39  cmp     r10d, eax
0x180019b3c  jle     short loc_180019B40
0x180019b3e  mov     [rdx], eax
0x180019b40  mov     eax, [rcx+55Ch]
0x180019b46  mov     edx, [r8]
0x180019b49  cmp     edx, eax
0x180019b4b  jl      short loc_180019B57
0x180019b4d  mov     eax, [rcx+560h]
0x180019b53  cmp     edx, eax
0x180019b55  jle     short locret_180019B5A
0x180019b57  mov     [r8], eax
0x180019b5a  retn
0x180019b5b  mov     eax, [rcx+0Ch]
0x180019b5e  add     eax, 0FFFFFFF0h
0x180019b61  cmp     r10d, eax
0x180019b64  jge     short loc_180019B7E
0x180019b66  mov     [rdx], eax
0x180019b68  mov     eax, [rcx+10h]
0x180019b6b  mov     edx, [r8]
0x180019b6e  add     eax, 0FFFFFFF0h
0x180019b71  cmp     edx, eax
0x180019b73  jl      short loc_180019B57
0x180019b75  mov     eax, [rcx+18h]
0x180019b78  cmp     edx, eax
0x180019b7a  jle     short locret_180019B5A
0x180019b7c  jmp     short loc_180019B57
0x180019b7e  mov     eax, [rcx+14h]
0x180019b81  cmp     r10d, eax
0x180019b84  jle     short loc_180019B68
0x180019b86  jmp     short loc_180019B66
```
