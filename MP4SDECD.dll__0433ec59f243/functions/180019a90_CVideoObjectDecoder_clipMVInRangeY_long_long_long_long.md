# CVideoObjectDecoder::clipMVInRangeY(long &,long &,long,long)

- ea: `0x180019a90`
- end: `0x180019b12`
- name: `?clipMVInRangeY@CVideoObjectDecoder@@AEAAXAEAJ0JJ@Z`
- size: `130`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, int *, int *, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e5c`
- `0x180036f80`
- `0x1800372f8`

## callees

- `0x180019a90`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::clipMVInRangeY(CVideoObjectDecoder *this, int *a2, int *a3, int a4, int a5)
{
  int v5; // r11d
  int v6; // r10d
  int v7; // eax
  int v8; // eax
  int v9; // eax

  v5 = 16;
  v6 = *a2;
  if ( a5 )
    v5 = a5;
  if ( a4 )
  {
    v9 = 4 * (*((_DWORD *)this + 3) - v5);
    if ( v6 < v9 || (v9 = 4 * *((_DWORD *)this + 5), v6 > v9) )
      *a2 = v9;
    v8 = 4 * (*((_DWORD *)this + 4) - v5);
    if ( *a3 < v8 )
      goto LABEL_9;
    v8 = 4 * *((_DWORD *)this + 6);
    if ( *a3 > v8 )
      goto LABEL_9;
  }
  else
  {
    v7 = *((_DWORD *)this + 337);
    if ( v6 < v7 || (v7 = *((_DWORD *)this + 338), v6 > v7) )
      *a2 = v7;
    v8 = *((_DWORD *)this + 339);
    if ( *a3 < v8 || (v8 = *((_DWORD *)this + 340), *a3 > v8) )
LABEL_9:
      *a3 = v8;
  }
}

```

## disassembly

```asm
0x180019a90  mov     eax, [rsp+arg_20]
0x180019a94  mov     r11d, 10h
0x180019a9a  mov     r10d, [rdx]
0x180019a9d  test    eax, eax
0x180019a9f  cmovnz  r11d, eax
0x180019aa3  test    r9d, r9d
0x180019aa6  jnz     short loc_180019ADB
0x180019aa8  mov     eax, [rcx+544h]
0x180019aae  cmp     r10d, eax
0x180019ab1  jl      short loc_180019ABE
0x180019ab3  mov     eax, [rcx+548h]
0x180019ab9  cmp     r10d, eax
0x180019abc  jle     short loc_180019AC0
0x180019abe  mov     [rdx], eax
0x180019ac0  mov     eax, [rcx+54Ch]
0x180019ac6  mov     edx, [r8]
0x180019ac9  cmp     edx, eax
0x180019acb  jl      short loc_180019AD7
0x180019acd  mov     eax, [rcx+550h]
0x180019ad3  cmp     edx, eax
0x180019ad5  jle     short locret_180019ADA
0x180019ad7  mov     [r8], eax
0x180019ada  retn
0x180019adb  mov     eax, [rcx+0Ch]
0x180019ade  sub     eax, r11d
0x180019ae1  shl     eax, 2
0x180019ae4  cmp     r10d, eax
0x180019ae7  jl      short loc_180019AF4
0x180019ae9  mov     eax, [rcx+14h]
0x180019aec  shl     eax, 2
0x180019aef  cmp     r10d, eax
0x180019af2  jle     short loc_180019AF6
0x180019af4  mov     [rdx], eax
0x180019af6  mov     eax, [rcx+10h]
0x180019af9  mov     edx, [r8]
0x180019afc  sub     eax, r11d
0x180019aff  shl     eax, 2
0x180019b02  cmp     edx, eax
0x180019b04  jl      short loc_180019AD7
0x180019b06  mov     eax, [rcx+18h]
0x180019b09  shl     eax, 2
0x180019b0c  cmp     edx, eax
0x180019b0e  jle     short locret_180019ADA
0x180019b10  jmp     short loc_180019AD7
```
