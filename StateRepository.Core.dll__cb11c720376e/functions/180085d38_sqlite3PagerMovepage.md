# sqlite3PagerMovepage

- ea: `0x180085d38`
- end: `0x180085e9c`
- name: `sqlite3PagerMovepage`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18007d23c`

## callees

- `0x1800217c0`
- `0x180021b0c`
- `0x180021c88`
- `0x180025ce0`
- `0x1800472fc`
- `0x180047374`
- `0x18004aa70`
- `0x18005b434`
- `0x180060134`
- `0x180081828`
- `0x180085d38`

## pseudocode

```c
__int64 __fastcall sqlite3PagerMovepage(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 result; // rax
  __int16 v9; // ax
  unsigned int v10; // ebp
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  unsigned int v16; // r14d
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // [rsp+60h] [rbp+8h] BYREF

  if ( !*(_BYTE *)(a1 + 16) || (result = sqlite3PagerWrite(a2), !(_DWORD)result) )
  {
    if ( (*(_BYTE *)(a2 + 52) & 2) == 0 || (result = subjournalPageIfRequired(a2), !(_DWORD)result) )
    {
      v9 = *(_WORD *)(a2 + 52);
      v10 = 0;
      if ( (v9 & 8) != 0 && !a4 )
        v10 = *(_DWORD *)(a2 + 48);
      *(_WORD *)(a2 + 52) = v9 & 0xFFF7;
      v11 = sqlite3PagerLookup(a1, a3);
      v15 = v11;
      if ( v11 )
      {
        if ( *(__int64 *)(v11 + 56) > 1 )
        {
          sqlite3PagerUnrefNotNull(v11, v12, v13, v14);
          return sqlite3ReportError(11, 64420, "database corruption");
        }
        *(_WORD *)(a2 + 52) |= *(_WORD *)(v11 + 52) & 8;
        if ( *(_BYTE *)(a1 + 16) )
          sqlite3PcacheMove(v11, (unsigned int)(*(_DWORD *)(a1 + 32) + 1));
        else
          sqlite3PcacheDrop(v11);
      }
      v16 = *(_DWORD *)(a2 + 48);
      sqlite3PcacheMove(a2, a3);
      sqlite3PcacheMakeDirty(a2);
      if ( *(_BYTE *)(a1 + 16) && v15 )
      {
        sqlite3PcacheMove(v15, v16);
        sqlite3PagerUnrefNotNull(v15, v17, v18, v19);
      }
      if ( v10 )
      {
        v24 = 0;
        v20 = sqlite3PagerGet(a1, v10, &v24, 0);
        if ( v20 )
        {
          if ( v10 <= *(_DWORD *)(a1 + 36) )
            sqlite3BitvecClear(*(_QWORD *)(a1 + 64), v10, *(_QWORD *)(a1 + 280));
          return v20;
        }
        *(_WORD *)(v24 + 52) |= 8u;
        sqlite3PcacheMakeDirty(v24);
        sqlite3PagerUnrefNotNull(v24, v21, v22, v23);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180085d38  push    rbx
0x180085d3a  push    rbp
0x180085d3b  push    rsi
0x180085d3c  push    rdi
0x180085d3d  push    r14
0x180085d3f  push    r15
0x180085d41  sub     rsp, 28h
0x180085d45  cmp     byte ptr [rcx+10h], 0
0x180085d49  mov     edi, r9d
0x180085d4c  mov     r15d, r8d
0x180085d4f  mov     rbx, rdx
0x180085d52  mov     rsi, rcx
0x180085d55  jz      short loc_180085D67
0x180085d57  mov     rcx, rdx
0x180085d5a  call    sqlite3PagerWrite
0x180085d5f  test    eax, eax
0x180085d61  jnz     loc_180085E8F
0x180085d67  test    byte ptr [rbx+34h], 2
0x180085d6b  jz      short loc_180085D7D
0x180085d6d  mov     rcx, rbx
0x180085d70  call    subjournalPageIfRequired
0x180085d75  test    eax, eax
0x180085d77  jnz     loc_180085E8F
0x180085d7d  movzx   eax, word ptr [rbx+34h]
0x180085d81  xor     ebp, ebp
0x180085d83  test    al, 8
0x180085d85  jz      short loc_180085D8E
0x180085d87  test    edi, edi
0x180085d89  jnz     short loc_180085D8E
0x180085d8b  mov     ebp, [rbx+30h]
0x180085d8e  mov     ecx, 0FFF7h
0x180085d93  mov     edx, r15d
0x180085d96  and     ax, cx
0x180085d99  mov     rcx, rsi
0x180085d9c  mov     [rbx+34h], ax
0x180085da0  call    sqlite3PagerLookup
0x180085da5  mov     rdi, rax
0x180085da8  test    rax, rax
0x180085dab  jz      short loc_180085DFA
0x180085dad  cmp     qword ptr [rax+38h], 1
0x180085db2  mov     rcx, rax
0x180085db5  jle     short loc_180085DD7
0x180085db7  call    sqlite3PagerUnrefNotNull
0x180085dbc  lea     r8, aDatabaseCorrup; "database corruption"
0x180085dc3  mov     edx, 0FBA4h
0x180085dc8  mov     ecx, 0Bh
0x180085dcd  call    sqlite3ReportError
0x180085dd2  jmp     loc_180085E8F
0x180085dd7  movzx   eax, word ptr [rax+34h]
0x180085ddb  and     ax, 8
0x180085ddf  or      [rbx+34h], ax
0x180085de3  cmp     byte ptr [rsi+10h], 0
0x180085de7  jz      short loc_180085DF5
0x180085de9  mov     edx, [rsi+20h]
0x180085dec  inc     edx
0x180085dee  call    sqlite3PcacheMove
0x180085df3  jmp     short loc_180085DFA
0x180085df5  call    sqlite3PcacheDrop
0x180085dfa  mov     r14d, [rbx+30h]
0x180085dfe  mov     edx, r15d
0x180085e01  mov     rcx, rbx
0x180085e04  call    sqlite3PcacheMove
0x180085e09  mov     rcx, rbx
0x180085e0c  call    sqlite3PcacheMakeDirty
0x180085e11  cmp     byte ptr [rsi+10h], 0
0x180085e15  jz      short loc_180085E2F
0x180085e17  test    rdi, rdi
0x180085e1a  jz      short loc_180085E2F
0x180085e1c  mov     edx, r14d
0x180085e1f  mov     rcx, rdi
0x180085e22  call    sqlite3PcacheMove
0x180085e27  mov     rcx, rdi
0x180085e2a  call    sqlite3PagerUnrefNotNull
0x180085e2f  test    ebp, ebp
0x180085e31  jz      short loc_180085E8D
0x180085e33  xor     r9d, r9d
0x180085e36  mov     [rsp+58h+arg_0], 0
0x180085e3f  lea     r8, [rsp+58h+arg_0]
0x180085e44  mov     edx, ebp
0x180085e46  mov     rcx, rsi
0x180085e49  call    sqlite3PagerGet
0x180085e4e  mov     ebx, eax
0x180085e50  test    eax, eax
0x180085e52  jz      short loc_180085E6F
0x180085e54  cmp     ebp, [rsi+24h]
0x180085e57  ja      short loc_180085E6B
0x180085e59  mov     r8, [rsi+118h]
0x180085e60  mov     edx, ebp
0x180085e62  mov     rcx, [rsi+40h]
0x180085e66  call    sqlite3BitvecClear
0x180085e6b  mov     eax, ebx
0x180085e6d  jmp     short loc_180085E8F
0x180085e6f  mov     rax, [rsp+58h+arg_0]
0x180085e74  or      word ptr [rax+34h], 8
0x180085e79  mov     rcx, [rsp+58h+arg_0]
0x180085e7e  call    sqlite3PcacheMakeDirty
0x180085e83  mov     rcx, [rsp+58h+arg_0]
0x180085e88  call    sqlite3PagerUnrefNotNull
0x180085e8d  xor     eax, eax
0x180085e8f  add     rsp, 28h
0x180085e93  pop     r15
0x180085e95  pop     r14
0x180085e97  pop     rdi
0x180085e98  pop     rsi
0x180085e99  pop     rbp
0x180085e9a  pop     rbx
0x180085e9b  retn
```
