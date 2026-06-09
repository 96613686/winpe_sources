# sqlite3DequoteNumber

- ea: `0x18006e170`
- end: `0x18006e26e`
- name: `sqlite3DequoteNumber`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000213c`

## callees

- `0x180011bcc`
- `0x18003d610`
- `0x18006e170`

## string_xrefs

- `0x18006e21f`: `unrecognized token: "%s"`

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
        if ( (*((_BYTE *)&qword_1800B4FF0 + (unsigned __int8)*(v3 - 1)) & 8) == 0
          || (v2 = (unsigned __int8)v3[1], (*((_BYTE *)&qword_1800B4FF0 + v2) & 8) == 0) )
        {
LABEL_17:
          v2 = sqlite3ErrorMsg(a1, "unrecognized token: \"%s\"", *(const char **)(a2 + 8));
        }
      }
      else
      {
        if ( (*((_BYTE *)&qword_1800B4FF0 + (unsigned __int8)*(v3 - 1)) & 4) == 0 )
          goto LABEL_17;
        v2 = (unsigned __int8)v3[1];
        if ( (*((_BYTE *)&qword_1800B4FF0 + v2) & 4) == 0 )
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
0x18006e170  test    rdx, rdx
0x18006e173  jz      locret_18006E26D
0x18006e179  push    rbx
0x18006e17a  push    rbp
0x18006e17b  push    rsi
0x18006e17c  push    rdi
0x18006e17d  push    r14
0x18006e17f  push    r15
0x18006e181  sub     rsp, 28h
0x18006e185  mov     rdi, [rdx+8]
0x18006e189  mov     rbx, rdx
0x18006e18c  mov     rbp, rcx
0x18006e18f  mov     r14, rdi
0x18006e192  cmp     byte ptr [rdi], 30h ; '0'
0x18006e195  jnz     short loc_18006E1A7
0x18006e197  mov     al, [rdi+1]
0x18006e19a  sub     al, 58h ; 'X'
0x18006e19c  test    al, 0DFh
0x18006e19e  jnz     short loc_18006E1A7
0x18006e1a0  mov     esi, 1
0x18006e1a5  jmp     short loc_18006E1A9
0x18006e1a7  xor     esi, esi
0x18006e1a9  mov     [rsp+58h+arg_8], 0
0x18006e1b1  lea     r15, qword_1800B4FF0
0x18006e1b8  mov     byte ptr [rdx], 9Bh
0x18006e1bb  mov     al, [rdi]
0x18006e1bd  cmp     al, 5Fh ; '_'
0x18006e1bf  jz      short loc_18006E1E4
0x18006e1c1  mov     [r14], al
0x18006e1c4  inc     r14
0x18006e1c7  mov     al, [rdi]
0x18006e1c9  sub     al, 2Eh ; '.'
0x18006e1cb  cmp     al, 37h ; '7'
0x18006e1cd  ja      short loc_18006E22E
0x18006e1cf  mov     rcx, 80000000800001h
0x18006e1d9  bt      rcx, rax
0x18006e1dd  jnb     short loc_18006E22E
0x18006e1df  mov     byte ptr [rbx], 99h
0x18006e1e2  jmp     short loc_18006E22E
0x18006e1e4  test    esi, esi
0x18006e1e6  jnz     short loc_18006E200
0x18006e1e8  movzx   eax, byte ptr [rdi-1]
0x18006e1ec  test    byte ptr [rax+r15], 4
0x18006e1f1  jz      short loc_18006E21B
0x18006e1f3  movzx   eax, byte ptr [rdi+1]
0x18006e1f7  test    byte ptr [rax+r15], 4
0x18006e1fc  jnz     short loc_18006E22E
0x18006e1fe  jmp     short loc_18006E21B
0x18006e200  cmp     esi, 1
0x18006e203  jnz     short loc_18006E22E
0x18006e205  movzx   eax, byte ptr [rdi-1]
0x18006e209  test    byte ptr [rax+r15], 8
0x18006e20e  jz      short loc_18006E21B
0x18006e210  movzx   eax, byte ptr [rdi+1]
0x18006e214  test    byte ptr [rax+r15], 8
0x18006e219  jnz     short loc_18006E22E
0x18006e21b  mov     r8, [rbx+8]
0x18006e21f  lea     rdx, aUnrecognizedTo; "unrecognized token: \"%s\""
0x18006e226  mov     rcx, rbp
0x18006e229  call    sqlite3ErrorMsg
0x18006e22e  mov     al, [rdi]
0x18006e230  inc     rdi
0x18006e233  test    al, al
0x18006e235  jnz     short loc_18006E1BB
0x18006e237  test    esi, esi
0x18006e239  jz      short loc_18006E23E
0x18006e23b  mov     byte ptr [rbx], 9Bh
0x18006e23e  cmp     byte ptr [rbx], 9Bh
0x18006e241  jnz     short loc_18006E261
0x18006e243  mov     rcx, [rbx+8]
0x18006e247  lea     rdx, [rsp+58h+arg_8]
0x18006e24c  call    sqlite3GetInt32
0x18006e251  test    eax, eax
0x18006e253  jz      short loc_18006E261
0x18006e255  mov     eax, [rsp+58h+arg_8]
0x18006e259  bts     dword ptr [rbx+4], 0Bh
0x18006e25e  mov     [rbx+8], eax
0x18006e261  add     rsp, 28h
0x18006e265  pop     r15
0x18006e267  pop     r14
0x18006e269  pop     rdi
0x18006e26a  pop     rsi
0x18006e26b  pop     rbp
0x18006e26c  pop     rbx
0x18006e26d  retn
```
