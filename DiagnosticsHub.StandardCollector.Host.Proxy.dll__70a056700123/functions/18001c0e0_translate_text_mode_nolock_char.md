# translate_text_mode_nolock_char_

- ea: `0x18001c0e0`
- end: `0x18001c275`
- name: `translate_text_mode_nolock_char_`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001b0e8`
- `0x18001c0e0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18001c1b4`
- `KERNEL32!ReadFile` at `0x18001c1b4`

## pseudocode

```c
__int64 __fastcall translate_text_mode_nolock_char_(int a1, char *a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v4; // r15
  __int64 v6; // r14
  __int64 v7; // rsi
  __int64 v8; // rax
  void *v9; // r10
  char *v10; // r8
  char *v11; // rax
  char *v12; // rbx
  char v13; // dl
  char *v14; // rcx
  char v15; // dl
  __int64 v16; // rcx
  char v17; // al
  char Buffer; // [rsp+60h] [rbp+8h] BYREF
  char *NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF

  v3 = a1;
  v4 = (__int64)a1 >> 6;
  v6 = a1;
  v7 = 9LL * (a1 & 0x3F);
  v8 = _pioinfo[v4];
  v9 = *(void **)(v8 + 72LL * (a1 & 0x3F) + 40);
  if ( a3 && *a2 == 10 )
    *(_BYTE *)(v8 + 72LL * (a1 & 0x3F) + 56) |= 4u;
  else
    *(_BYTE *)(v8 + 72LL * (a1 & 0x3F) + 56) &= ~4u;
  v10 = &a2[a3];
  v11 = a2;
  v12 = a2;
  if ( a2 >= v10 )
    return (unsigned int)((_DWORD)v12 - (_DWORD)a2);
  while ( 1 )
  {
    v13 = *v11;
    if ( *v11 == 26 )
    {
      v16 = _pioinfo[v3 >> 6];
      v17 = *(_BYTE *)(v16 + 72 * (v3 & 0x3F) + 56);
      if ( (v17 & 0x40) == 0 )
      {
        *(_BYTE *)(v16 + 72 * (v3 & 0x3F) + 56) = v17 | 2;
        return (unsigned int)((_DWORD)v12 - (_DWORD)a2);
      }
      *v12 = 26;
      goto LABEL_27;
    }
    v14 = v11 + 1;
    if ( v13 != 13 )
    {
LABEL_11:
      ++v11;
      goto LABEL_12;
    }
    if ( v14 >= v10 )
      break;
    if ( *v14 != 10 )
      goto LABEL_11;
    v11 += 2;
    v13 = 10;
LABEL_12:
    *v12++ = v13;
    NumberOfBytesRead = v12;
    if ( v11 >= v10 )
      return (unsigned int)((_DWORD)v12 - (_DWORD)a2);
  }
  Buffer = 0;
  LODWORD(NumberOfBytesRead) = 0;
  if ( !ReadFile(v9, &Buffer, 1u, (LPDWORD)&NumberOfBytesRead, 0) || !(_DWORD)NumberOfBytesRead )
  {
LABEL_23:
    *v12 = 13;
    goto LABEL_27;
  }
  if ( (*(_BYTE *)(_pioinfo[v4] + 8 * v7 + 56) & 0x48) == 0 )
  {
    if ( Buffer == 10 && v12 == a2 )
      goto LABEL_18;
    lseeki64_nolock((unsigned int)v3, -1, 1);
    if ( Buffer == 10 )
      return (unsigned int)((_DWORD)v12 - (_DWORD)a2);
    goto LABEL_23;
  }
  v15 = Buffer;
  if ( Buffer == 10 )
  {
LABEL_18:
    *v12 = 10;
    goto LABEL_27;
  }
  *v12 = 13;
  *(_BYTE *)(_pioinfo[v6 >> 6] + 72 * (v6 & 0x3F) + 58) = v15;
LABEL_27:
  LODWORD(v12) = (_DWORD)v12 + 1;
  return (unsigned int)((_DWORD)v12 - (_DWORD)a2);
}

```

## disassembly

```asm
0x18001c0e0  mov     [rsp+arg_10], rbx
0x18001c0e5  mov     [rsp+arg_18], rbp
0x18001c0ea  push    rsi
0x18001c0eb  push    rdi
0x18001c0ec  push    r12
0x18001c0ee  push    r14
0x18001c0f0  push    r15
0x18001c0f2  sub     rsp, 30h
0x18001c0f6  movsxd  rbp, ecx
0x18001c0f9  lea     r9, __pioinfo
0x18001c100  mov     rax, rbp
0x18001c103  mov     r15, rbp
0x18001c106  and     eax, 3Fh
0x18001c109  sar     r15, 6
0x18001c10d  mov     rdi, rdx
0x18001c110  mov     r14, rbp
0x18001c113  lea     rsi, [rax+rax*8]
0x18001c117  mov     rax, [r9+r15*8]
0x18001c11b  mov     r10, [rax+rsi*8+28h]
0x18001c120  test    r8, r8
0x18001c123  jz      short loc_18001C131
0x18001c125  cmp     byte ptr [rdx], 0Ah
0x18001c128  jnz     short loc_18001C131
0x18001c12a  or      byte ptr [rax+rsi*8+38h], 4
0x18001c12f  jmp     short loc_18001C136
0x18001c131  and     byte ptr [rax+rsi*8+38h], 0FBh
0x18001c136  add     r8, rdi
0x18001c139  mov     rax, rdi
0x18001c13c  mov     rbx, rdi
0x18001c13f  cmp     rdi, r8
0x18001c142  jnb     loc_18001C25A
0x18001c148  mov     r12d, 1
0x18001c14e  mov     dl, [rax]
0x18001c150  cmp     dl, 1Ah
0x18001c153  jz      loc_18001C227
0x18001c159  lea     rcx, [rax+1]
0x18001c15d  cmp     dl, 0Dh
0x18001c160  jnz     short loc_18001C174
0x18001c162  cmp     rcx, r8
0x18001c165  jnb     short loc_18001C192
0x18001c167  cmp     byte ptr [rcx], 0Ah
0x18001c16a  jnz     short loc_18001C174
0x18001c16c  add     rax, 2
0x18001c170  mov     dl, 0Ah
0x18001c172  jmp     short loc_18001C177
0x18001c174  mov     rax, rcx
0x18001c177  mov     [rbx], dl
0x18001c179  mov     rcx, rbx
0x18001c17c  lea     rbx, [r12+rbx]
0x18001c180  mov     r9, r12
0x18001c183  mov     [rsp+58h+NumberOfBytesRead], rbx
0x18001c188  cmp     rax, r8
0x18001c18b  jb      short loc_18001C14E
0x18001c18d  jmp     loc_18001C25A
0x18001c192  xor     r9d, r9d
0x18001c195  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x18001c19a  mov     [rsp+58h+Buffer], r9b
0x18001c19f  mov     r8d, r12d; nNumberOfBytesToRead
0x18001c1a2  mov     dword ptr [rsp+58h+NumberOfBytesRead], r9d
0x18001c1a7  mov     rcx, r10; hFile
0x18001c1aa  mov     [rsp+58h+lpOverlapped], r9; lpOverlapped
0x18001c1af  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001c1b4  call    cs:__imp_ReadFile
0x18001c1ba  test    eax, eax
0x18001c1bc  jz      short loc_18001C222
0x18001c1be  cmp     dword ptr [rsp+58h+NumberOfBytesRead], 0
0x18001c1c3  jz      short loc_18001C222
0x18001c1c5  lea     r9, __pioinfo
0x18001c1cc  mov     rax, [r9+r15*8]
0x18001c1d0  test    byte ptr [rax+rsi*8+38h], 48h
0x18001c1d5  jz      short loc_18001C201
0x18001c1d7  mov     dl, [rsp+58h+Buffer]
0x18001c1db  cmp     dl, 0Ah
0x18001c1de  jnz     short loc_18001C1E5
0x18001c1e0  mov     byte ptr [rbx], 0Ah
0x18001c1e3  jmp     short loc_18001C257
0x18001c1e5  mov     rax, r14
0x18001c1e8  mov     byte ptr [rbx], 0Dh
0x18001c1eb  sar     rax, 6
0x18001c1ef  and     r14d, 3Fh
0x18001c1f3  mov     rax, [r9+rax*8]
0x18001c1f7  lea     rcx, [r14+r14*8]
0x18001c1fb  mov     [rax+rcx*8+3Ah], dl
0x18001c1ff  jmp     short loc_18001C257
0x18001c201  cmp     [rsp+58h+Buffer], 0Ah
0x18001c206  jnz     short loc_18001C20D
0x18001c208  cmp     rbx, rdi
0x18001c20b  jz      short loc_18001C1E0
0x18001c20d  mov     r8d, r12d
0x18001c210  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c214  mov     ecx, ebp
0x18001c216  call    _lseeki64_nolock
0x18001c21b  cmp     [rsp+58h+Buffer], 0Ah
0x18001c220  jz      short loc_18001C25A
0x18001c222  mov     byte ptr [rbx], 0Dh
0x18001c225  jmp     short loc_18001C257
0x18001c227  mov     rcx, rbp
0x18001c22a  lea     r9, __pioinfo
0x18001c231  and     ecx, 3Fh
0x18001c234  mov     rax, rbp
0x18001c237  sar     rax, 6
0x18001c23b  lea     r8, [rcx+rcx*8]
0x18001c23f  mov     rcx, [r9+rax*8]
0x18001c243  mov     al, [rcx+r8*8+38h]
0x18001c248  test    al, 40h
0x18001c24a  jnz     short loc_18001C255
0x18001c24c  or      al, 2
0x18001c24e  mov     [rcx+r8*8+38h], al
0x18001c253  jmp     short loc_18001C25A
0x18001c255  mov     [rbx], dl
0x18001c257  add     rbx, r12
0x18001c25a  mov     rbp, [rsp+58h+arg_18]
0x18001c25f  sub     ebx, edi
0x18001c261  mov     eax, ebx
0x18001c263  mov     rbx, [rsp+58h+arg_10]
0x18001c268  add     rsp, 30h
0x18001c26c  pop     r15
0x18001c26e  pop     r14
0x18001c270  pop     r12
0x18001c272  pop     rdi
0x18001c273  pop     rsi
0x18001c274  retn
```
