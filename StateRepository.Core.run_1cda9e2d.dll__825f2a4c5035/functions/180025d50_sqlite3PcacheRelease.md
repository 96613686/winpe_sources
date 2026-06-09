# sqlite3PcacheRelease

- ea: `0x180025d50`
- end: `0x180025e0c`
- name: `sqlite3PcacheRelease`
- size: `188`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180006e2c`
- `0x180024468`
- `0x180024ef8`
- `0x1800257ac`
- `0x180025870`
- `0x180025960`
- `0x1800259b0`
- `0x180025ce0`
- `0x1800473f0`
- `0x18007b124`

## callees

- `0x180025d50`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3PcacheRelease(__int64 a1)
{
  __int64 result; // rax
  bool v2; // zf
  __int64 v3; // r9
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rdx

  result = *(_QWORD *)(a1 + 24);
  --*(_QWORD *)(result + 24);
  v2 = (*(_QWORD *)(a1 + 56))-- == 1;
  if ( v2 )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (*(_BYTE *)(a1 + 52) & 1) != 0 )
    {
      if ( *(_BYTE *)(v3 + 48) )
        return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))xmmword_1800B5718)(
                 *(_QWORD *)(v3 + 72),
                 *(_QWORD *)a1,
                 0);
    }
    else
    {
      if ( *(_QWORD *)(v3 + 16) == a1 )
        *(_QWORD *)(v3 + 16) = *(_QWORD *)(a1 + 72);
      v4 = *(_QWORD *)(a1 + 64);
      v5 = *(_QWORD *)(a1 + 72);
      if ( v4 )
        *(_QWORD *)(v4 + 72) = v5;
      else
        *(_QWORD *)(v3 + 8) = v5;
      v6 = *(_QWORD *)(a1 + 72);
      v7 = *(_QWORD *)(a1 + 64);
      if ( v6 )
      {
        *(_QWORD *)(v6 + 64) = v7;
      }
      else
      {
        *(_QWORD *)v3 = v7;
        if ( !v7 )
          *(_BYTE *)(v3 + 49) = 2;
      }
      *(_QWORD *)(a1 + 72) = 0;
      result = *(_QWORD *)v3;
      *(_QWORD *)(a1 + 64) = *(_QWORD *)v3;
      if ( result )
      {
        *(_QWORD *)(result + 72) = a1;
      }
      else
      {
        v2 = *(_BYTE *)(v3 + 48) == 0;
        *(_QWORD *)(v3 + 8) = a1;
        if ( !v2 )
          *(_BYTE *)(v3 + 49) = 1;
      }
      v2 = *(_QWORD *)(v3 + 16) == 0;
      *(_QWORD *)v3 = a1;
      if ( v2 && (*(_BYTE *)(a1 + 52) & 8) == 0 )
        *(_QWORD *)(v3 + 16) = a1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025d50  mov     rax, [rcx+18h]
0x180025d54  dec     qword ptr [rax+18h]
0x180025d58  sub     qword ptr [rcx+38h], 1
0x180025d5d  jnz     short locret_180025D86
0x180025d5f  test    byte ptr [rcx+34h], 1
0x180025d63  mov     r9, [rcx+18h]
0x180025d67  jz      short loc_180025D87
0x180025d69  cmp     byte ptr [r9+30h], 0
0x180025d6e  jz      short locret_180025D86
0x180025d70  mov     rdx, [rcx]
0x180025d73  xor     r8d, r8d
0x180025d76  mov     rcx, [r9+48h]
0x180025d7a  mov     rax, qword ptr cs:xmmword_1800B5718
0x180025d81  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180025d86  retn
0x180025d87  cmp     [r9+10h], rcx
0x180025d8b  jnz     short loc_180025D95
0x180025d8d  mov     rax, [rcx+48h]
0x180025d91  mov     [r9+10h], rax
0x180025d95  mov     rax, [rcx+40h]
0x180025d99  mov     rdx, [rcx+48h]
0x180025d9d  test    rax, rax
0x180025da0  jz      short loc_180025DE5
0x180025da2  mov     [rax+48h], rdx
0x180025da6  mov     rax, [rcx+48h]
0x180025daa  mov     rdx, [rcx+40h]
0x180025dae  test    rax, rax
0x180025db1  jz      short loc_180025DEB
0x180025db3  mov     [rax+40h], rdx
0x180025db7  mov     qword ptr [rcx+48h], 0
0x180025dbf  mov     rax, [r9]
0x180025dc2  mov     [rcx+40h], rax
0x180025dc6  test    rax, rax
0x180025dc9  jz      short loc_180025DFA
0x180025dcb  mov     [rax+48h], rcx
0x180025dcf  cmp     qword ptr [r9+10h], 0
0x180025dd4  mov     [r9], rcx
0x180025dd7  jnz     short locret_180025D86
0x180025dd9  test    byte ptr [rcx+34h], 8
0x180025ddd  jnz     short locret_180025D86
0x180025ddf  mov     [r9+10h], rcx
0x180025de3  jmp     short locret_180025D86
0x180025de5  mov     [r9+8], rdx
0x180025de9  jmp     short loc_180025DA6
0x180025deb  mov     [r9], rdx
0x180025dee  test    rdx, rdx
0x180025df1  jnz     short loc_180025DB7
0x180025df3  mov     byte ptr [r9+31h], 2
0x180025df8  jmp     short loc_180025DB7
0x180025dfa  cmp     byte ptr [r9+30h], 0
0x180025dff  mov     [r9+8], rcx
0x180025e03  jz      short loc_180025DCF
0x180025e05  mov     byte ptr [r9+31h], 1
0x180025e0a  jmp     short loc_180025DCF
```
