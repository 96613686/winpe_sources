# sqlite3DequoteNumber

- ea: `0x180067644`
- end: `0x180067742`
- name: `sqlite3DequoteNumber`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180031b38`

## callees

- `0x18004b280`
- `0x180060ce8`
- `0x180067644`

## string_xrefs

- `0x1800676f3`: `unrecognized token: "%s"`

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
  *(_BYTE *)a2 = -100;
  do
  {
    if ( *v3 == 95 )
    {
      if ( v7 )
      {
        if ( (*((_BYTE *)&qword_18009E630 + (unsigned __int8)*(v3 - 1)) & 8) == 0
          || (v2 = (unsigned __int8)v3[1], (*((_BYTE *)&qword_18009E630 + v2) & 8) == 0) )
        {
LABEL_17:
          v2 = sqlite3ErrorMsg(a1, "unrecognized token: \"%s\"", *(const char **)(a2 + 8));
        }
      }
      else
      {
        if ( (*((_BYTE *)&qword_18009E630 + (unsigned __int8)*(v3 - 1)) & 4) == 0 )
          goto LABEL_17;
        v2 = (unsigned __int8)v3[1];
        if ( (*((_BYTE *)&qword_18009E630 + v2) & 4) == 0 )
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
          *(_BYTE *)a2 = -102;
      }
    }
  }
  while ( *v3++ );
  if ( v7 )
    *(_BYTE *)a2 = -100;
  if ( *(_BYTE *)a2 == 0x9C )
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
0x180067644  test    rdx, rdx
0x180067647  jz      locret_180067741
0x18006764d  push    rbx
0x18006764e  push    rbp
0x18006764f  push    rsi
0x180067650  push    rdi
0x180067651  push    r14
0x180067653  push    r15
0x180067655  sub     rsp, 28h
0x180067659  mov     rdi, [rdx+8]
0x18006765d  mov     rbx, rdx
0x180067660  mov     rbp, rcx
0x180067663  mov     r14, rdi
0x180067666  cmp     byte ptr [rdi], 30h ; '0'
0x180067669  jnz     short loc_18006767B
0x18006766b  mov     al, [rdi+1]
0x18006766e  sub     al, 58h ; 'X'
0x180067670  test    al, 0DFh
0x180067672  jnz     short loc_18006767B
0x180067674  mov     esi, 1
0x180067679  jmp     short loc_18006767D
0x18006767b  xor     esi, esi
0x18006767d  mov     [rsp+58h+arg_8], 0
0x180067685  lea     r15, qword_18009E630
0x18006768c  mov     byte ptr [rdx], 9Ch
0x18006768f  mov     al, [rdi]
0x180067691  cmp     al, 5Fh ; '_'
0x180067693  jz      short loc_1800676B8
0x180067695  mov     [r14], al
0x180067698  inc     r14
0x18006769b  mov     al, [rdi]
0x18006769d  sub     al, 2Eh ; '.'
0x18006769f  cmp     al, 37h ; '7'
0x1800676a1  ja      short loc_180067702
0x1800676a3  mov     rcx, 80000000800001h
0x1800676ad  bt      rcx, rax
0x1800676b1  jnb     short loc_180067702
0x1800676b3  mov     byte ptr [rbx], 9Ah
0x1800676b6  jmp     short loc_180067702
0x1800676b8  test    esi, esi
0x1800676ba  jnz     short loc_1800676D4
0x1800676bc  movzx   eax, byte ptr [rdi-1]
0x1800676c0  test    byte ptr [rax+r15], 4
0x1800676c5  jz      short loc_1800676EF
0x1800676c7  movzx   eax, byte ptr [rdi+1]
0x1800676cb  test    byte ptr [rax+r15], 4
0x1800676d0  jnz     short loc_180067702
0x1800676d2  jmp     short loc_1800676EF
0x1800676d4  cmp     esi, 1
0x1800676d7  jnz     short loc_180067702
0x1800676d9  movzx   eax, byte ptr [rdi-1]
0x1800676dd  test    byte ptr [rax+r15], 8
0x1800676e2  jz      short loc_1800676EF
0x1800676e4  movzx   eax, byte ptr [rdi+1]
0x1800676e8  test    byte ptr [rax+r15], 8
0x1800676ed  jnz     short loc_180067702
0x1800676ef  mov     r8, [rbx+8]
0x1800676f3  lea     rdx, aUnrecognizedTo; "unrecognized token: \"%s\""
0x1800676fa  mov     rcx, rbp
0x1800676fd  call    sqlite3ErrorMsg
0x180067702  mov     al, [rdi]
0x180067704  inc     rdi
0x180067707  test    al, al
0x180067709  jnz     short loc_18006768F
0x18006770b  test    esi, esi
0x18006770d  jz      short loc_180067712
0x18006770f  mov     byte ptr [rbx], 9Ch
0x180067712  cmp     byte ptr [rbx], 9Ch
0x180067715  jnz     short loc_180067735
0x180067717  mov     rcx, [rbx+8]
0x18006771b  lea     rdx, [rsp+58h+arg_8]
0x180067720  call    sqlite3GetInt32
0x180067725  test    eax, eax
0x180067727  jz      short loc_180067735
0x180067729  mov     eax, [rsp+58h+arg_8]
0x18006772d  bts     dword ptr [rbx+4], 0Bh
0x180067732  mov     [rbx+8], eax
0x180067735  add     rsp, 28h
0x180067739  pop     r15
0x18006773b  pop     r14
0x18006773d  pop     rdi
0x18006773e  pop     rsi
0x18006773f  pop     rbp
0x180067740  pop     rbx
0x180067741  retn
```
