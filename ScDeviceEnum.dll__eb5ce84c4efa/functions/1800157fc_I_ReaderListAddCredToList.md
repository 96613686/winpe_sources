# I_ReaderListAddCredToList

- ea: `0x1800157fc`
- end: `0x180015847`
- name: `I_ReaderListAddCredToList`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int16 *, __int64 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180016500`
- `0x180017544`
- `0x180017f9c`
- `0x180019250`

## callees

- `0x1800157fc`

## pseudocode

```c
__int64 __fastcall I_ReaderListAddCredToList(_QWORD *a1, unsigned __int16 *a2, __int64 *a3)
{
  __int64 v3; // rax
  int v4; // r10d
  int v5; // r9d
  __int64 result; // rax

  if ( !a2 || !*a1 )
    goto LABEL_13;
  v3 = *a1 - (_QWORD)a2;
  do
  {
    v4 = *(unsigned __int16 *)((char *)a2 + v3);
    v5 = *a2 - v4;
    if ( v5 )
      break;
    ++a2;
  }
  while ( v4 );
  if ( !v5 )
  {
    result = *a3;
    a1[13] = *a3;
    *a3 = (__int64)a1;
  }
  else
  {
LABEL_13:
    while ( 1 )
    {
      result = *a3;
      if ( !*a3 )
        break;
      a3 = (__int64 *)(result + 104);
    }
    *a3 = (__int64)a1;
    a1[13] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800157fc  test    rdx, rdx
0x1800157ff  jz      short loc_180015837
0x180015801  mov     rax, [rcx]
0x180015804  test    rax, rax
0x180015807  jz      short loc_180015837
0x180015809  sub     rax, rdx
0x18001580c  movzx   r9d, word ptr [rdx]
0x180015810  movzx   r10d, word ptr [rdx+rax]
0x180015815  sub     r9d, r10d
0x180015818  jnz     short loc_180015823
0x18001581a  add     rdx, 2
0x18001581e  test    r10d, r10d
0x180015821  jnz     short loc_18001580C
0x180015823  test    r9d, r9d
0x180015826  jnz     short loc_180015837
0x180015828  mov     rax, [r8]
0x18001582b  mov     [rcx+68h], rax
0x18001582f  mov     [r8], rcx
0x180015832  retn
0x180015833  lea     r8, [rax+68h]
0x180015837  mov     rax, [r8]
0x18001583a  test    rax, rax
0x18001583d  jnz     short loc_180015833
0x18001583f  mov     [r8], rcx
0x180015842  mov     [rcx+68h], rax
0x180015846  retn
```
