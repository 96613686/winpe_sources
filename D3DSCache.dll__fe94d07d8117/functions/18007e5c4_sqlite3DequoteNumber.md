# sqlite3DequoteNumber

- ea: `0x18007e5c4`
- end: `0x18007e6c2`
- name: `sqlite3DequoteNumber`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bc30`

## callees

- `0x180014464`
- `0x18007e5c4`
- `0x180083814`

## string_xrefs

- `0x18007e673`: `unrecognized token: "%s"`

## pseudocode

```c
void __fastcall sqlite3DequoteNumber(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // rax
  _BYTE *v3; // rdi
  _BYTE *v6; // r14
  BOOL v7; // esi
  __int64 v8; // rcx
  int v10; // eax
  int v11; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return;
  v3 = *(_BYTE **)(a2 + 8);
  v6 = v3;
  v7 = *v3 == 48 && ((v3[1] - 88) & 0xDF) == 0;
  v11 = 0;
  *(_BYTE *)a2 = -101;
  do
  {
    if ( *v3 == 95 )
    {
      if ( v7 )
      {
        if ( (*((_BYTE *)&qword_1800ADE90 + (unsigned __int8)*(v3 - 1)) & 8) == 0
          || (v2 = (unsigned __int8)v3[1], (*((_BYTE *)&qword_1800ADE90 + v2) & 8) == 0) )
        {
LABEL_17:
          v2 = sqlite3ErrorMsg(a1, "unrecognized token: \"%s\"", *(const char **)(a2 + 8));
        }
      }
      else
      {
        if ( (*((_BYTE *)&qword_1800ADE90 + (unsigned __int8)*(v3 - 1)) & 4) == 0 )
          goto LABEL_17;
        v2 = (unsigned __int8)v3[1];
        if ( (*((_BYTE *)&qword_1800ADE90 + v2) & 4) == 0 )
          goto LABEL_17;
      }
    }
    else
    {
      *v6++ = *v3;
      LOBYTE(v2) = *v3 - 46;
      if ( (unsigned __int8)v2 <= 0x37u )
      {
        v8 = 0x80000000800001LL;
        if ( _bittest64(&v8, v2) )
          *(_BYTE *)a2 = -103;
      }
    }
  }
  while ( *v3++ );
  if ( v7 )
    *(_BYTE *)a2 = -101;
  if ( *(_BYTE *)a2 == 0x9B )
  {
    if ( (unsigned int)sqlite3GetInt32(*(_QWORD *)(a2 + 8), &v11) )
    {
      v10 = v11;
      *(_DWORD *)(a2 + 4) |= 0x800u;
      *(_DWORD *)(a2 + 8) = v10;
    }
  }
}

```

## disassembly

```asm
0x18007e5c4  test    rdx, rdx
0x18007e5c7  jz      locret_18007E6C1
0x18007e5cd  push    rbx
0x18007e5ce  push    rbp
0x18007e5cf  push    rsi
0x18007e5d0  push    rdi
0x18007e5d1  push    r14
0x18007e5d3  push    r15
0x18007e5d5  sub     rsp, 28h
0x18007e5d9  mov     rdi, [rdx+8]
0x18007e5dd  mov     rbx, rdx
0x18007e5e0  mov     rbp, rcx
0x18007e5e3  mov     r14, rdi
0x18007e5e6  cmp     byte ptr [rdi], 30h ; '0'
0x18007e5e9  jnz     short loc_18007E5FB
0x18007e5eb  mov     al, [rdi+1]
0x18007e5ee  sub     al, 58h ; 'X'
0x18007e5f0  test    al, 0DFh
0x18007e5f2  jnz     short loc_18007E5FB
0x18007e5f4  mov     esi, 1
0x18007e5f9  jmp     short loc_18007E5FD
0x18007e5fb  xor     esi, esi
0x18007e5fd  mov     [rsp+58h+arg_8], 0
0x18007e605  lea     r15, qword_1800ADE90
0x18007e60c  mov     byte ptr [rdx], 9Bh
0x18007e60f  mov     al, [rdi]
0x18007e611  cmp     al, 5Fh ; '_'
0x18007e613  jz      short loc_18007E638
0x18007e615  mov     [r14], al
0x18007e618  inc     r14
0x18007e61b  mov     al, [rdi]
0x18007e61d  sub     al, 2Eh ; '.'
0x18007e61f  cmp     al, 37h ; '7'
0x18007e621  ja      short loc_18007E682
0x18007e623  mov     rcx, 80000000800001h
0x18007e62d  bt      rcx, rax
0x18007e631  jnb     short loc_18007E682
0x18007e633  mov     byte ptr [rbx], 99h
0x18007e636  jmp     short loc_18007E682
0x18007e638  test    esi, esi
0x18007e63a  jnz     short loc_18007E654
0x18007e63c  movzx   eax, byte ptr [rdi-1]
0x18007e640  test    byte ptr [rax+r15], 4
0x18007e645  jz      short loc_18007E66F
0x18007e647  movzx   eax, byte ptr [rdi+1]
0x18007e64b  test    byte ptr [rax+r15], 4
0x18007e650  jz      short loc_18007E66F
0x18007e652  jmp     short loc_18007E682
0x18007e654  cmp     esi, 1
0x18007e657  jnz     short loc_18007E682
0x18007e659  movzx   eax, byte ptr [rdi-1]
0x18007e65d  test    byte ptr [rax+r15], 8
0x18007e662  jz      short loc_18007E66F
0x18007e664  movzx   eax, byte ptr [rdi+1]
0x18007e668  test    byte ptr [rax+r15], 8
0x18007e66d  jnz     short loc_18007E682
0x18007e66f  mov     r8, [rbx+8]
0x18007e673  lea     rdx, aUnrecognizedTo; "unrecognized token: \"%s\""
0x18007e67a  mov     rcx, rbp
0x18007e67d  call    sqlite3ErrorMsg
0x18007e682  mov     al, [rdi]
0x18007e684  inc     rdi
0x18007e687  test    al, al
0x18007e689  jnz     short loc_18007E60F
0x18007e68b  test    esi, esi
0x18007e68d  jz      short loc_18007E692
0x18007e68f  mov     byte ptr [rbx], 9Bh
0x18007e692  cmp     byte ptr [rbx], 9Bh
0x18007e695  jnz     short loc_18007E6B5
0x18007e697  mov     rcx, [rbx+8]
0x18007e69b  lea     rdx, [rsp+58h+arg_8]
0x18007e6a0  call    sqlite3GetInt32
0x18007e6a5  test    eax, eax
0x18007e6a7  jz      short loc_18007E6B5
0x18007e6a9  mov     eax, [rsp+58h+arg_8]
0x18007e6ad  bts     dword ptr [rbx+4], 0Bh
0x18007e6b2  mov     [rbx+8], eax
0x18007e6b5  add     rsp, 28h
0x18007e6b9  pop     r15
0x18007e6bb  pop     r14
0x18007e6bd  pop     rdi
0x18007e6be  pop     rsi
0x18007e6bf  pop     rbp
0x18007e6c0  pop     rbx
0x18007e6c1  retn
```
