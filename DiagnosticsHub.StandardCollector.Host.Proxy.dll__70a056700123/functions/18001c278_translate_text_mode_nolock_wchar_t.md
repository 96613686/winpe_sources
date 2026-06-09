# translate_text_mode_nolock_wchar_t_

- ea: `0x18001c278`
- end: `0x18001c473`
- name: `translate_text_mode_nolock_wchar_t_`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001c9fc`

## callees

- `0x18001b0e8`
- `0x18001c278`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18001c35f`
- `KERNEL32!ReadFile` at `0x18001c35f`

## pseudocode

```c
__int64 __fastcall translate_text_mode_nolock_wchar_t_(int a1, __int16 *a2, __int64 a3)
{
  __int64 v3; // r15
  __int64 v4; // rdi
  __int64 v5; // r12
  __int64 v7; // rbp
  __int64 v8; // rax
  void *v9; // r10
  __int16 *v10; // r8
  __int16 *v11; // rax
  __int16 *v12; // rbx
  __int16 v13; // dx
  __int16 *v14; // rcx
  __int64 v15; // rcx
  char v16; // al
  __int16 Buffer; // [rsp+70h] [rbp+8h] BYREF
  __int16 v19; // [rsp+78h] [rbp+10h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF

  v3 = a1;
  v4 = 0;
  v5 = (__int64)a1 >> 6;
  v7 = 9LL * (a1 & 0x3F);
  v8 = _pioinfo[v5];
  v9 = *(void **)(v8 + 72LL * (a1 & 0x3F) + 40);
  if ( a3 && *a2 == 10 )
    *(_BYTE *)(v8 + 72LL * (a1 & 0x3F) + 56) |= 4u;
  else
    *(_BYTE *)(v8 + 72LL * (a1 & 0x3F) + 56) &= ~4u;
  v10 = &a2[a3];
  v11 = a2;
  v12 = a2;
  if ( a2 >= v10 )
    return 2 * (unsigned int)(v12 - a2);
  while ( 1 )
  {
    v13 = *v11;
    if ( *v11 == 26 )
    {
      v15 = _pioinfo[v3 >> 6];
      v16 = *(_BYTE *)(v15 + 72 * (v3 & 0x3F) + 56);
      if ( (v16 & 0x40) == 0 )
      {
        *(_BYTE *)(v15 + 72 * (v3 & 0x3F) + 56) = v16 | 2;
        return 2 * (unsigned int)(v12 - a2);
      }
      *v12 = 26;
      return 2 * (unsigned int)(++v12 - a2);
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
    if ( v11 >= v10 )
      return 2 * (unsigned int)(v12 - a2);
  }
  Buffer = 0;
  NumberOfBytesRead = 0;
  if ( !ReadFile(v9, &Buffer, 2u, &NumberOfBytesRead, 0) || !NumberOfBytesRead )
  {
LABEL_25:
    *v12 = 13;
    return 2 * (unsigned int)(++v12 - a2);
  }
  if ( (*(_BYTE *)(_pioinfo[v5] + 8 * v7 + 56) & 0x48) == 0 )
  {
    if ( Buffer == 10 && v12 == a2 )
      goto LABEL_18;
    lseeki64_nolock((unsigned int)v3, -2, 1);
    if ( Buffer == 10 )
      return 2 * (unsigned int)(v12 - a2);
    goto LABEL_25;
  }
  if ( Buffer == 10 )
  {
LABEL_18:
    *v12 = 10;
    return 2 * (unsigned int)(++v12 - a2);
  }
  v19 = Buffer;
  *v12 = 13;
  do
  {
    *(_BYTE *)(_pioinfo[v3 >> 6] + 72 * (v3 & 0x3F) + v4 + 58) = *((_BYTE *)&v19 + v4);
    ++v4;
  }
  while ( v4 < 2 );
  *(_BYTE *)(_pioinfo[v3 >> 6] + 72 * (v3 & 0x3F) + 60) = 10;
  return 2 * (unsigned int)(++v12 - a2);
}

```

## disassembly

```asm
0x18001c278  mov     [rsp+arg_18], rbx
0x18001c27d  push    rbp
0x18001c27e  push    rsi
0x18001c27f  push    rdi
0x18001c280  push    r12
0x18001c282  push    r13
0x18001c284  push    r14
0x18001c286  push    r15
0x18001c288  sub     rsp, 30h
0x18001c28c  movsxd  r15, ecx
0x18001c28f  xor     edi, edi
0x18001c291  mov     rax, r15
0x18001c294  lea     rcx, __pioinfo
0x18001c29b  and     eax, 3Fh
0x18001c29e  mov     r12, r15
0x18001c2a1  sar     r12, 6
0x18001c2a5  mov     rsi, rdx
0x18001c2a8  lea     r9d, [rdi+0Ah]
0x18001c2ac  mov     r14, r15
0x18001c2af  lea     rbp, [rax+rax*8]
0x18001c2b3  mov     rax, [rcx+r12*8]
0x18001c2b7  mov     r10, [rax+rbp*8+28h]
0x18001c2bc  test    r8, r8
0x18001c2bf  jz      short loc_18001C2CE
0x18001c2c1  cmp     [rdx], r9w
0x18001c2c5  jnz     short loc_18001C2CE
0x18001c2c7  or      byte ptr [rax+rbp*8+38h], 4
0x18001c2cc  jmp     short loc_18001C2D3
0x18001c2ce  and     byte ptr [rax+rbp*8+38h], 0FBh
0x18001c2d3  lea     r8, [rdx+r8*2]
0x18001c2d7  mov     rax, rsi
0x18001c2da  mov     rbx, rsi
0x18001c2dd  cmp     rsi, r8
0x18001c2e0  jnb     loc_18001C452
0x18001c2e6  mov     r11d, 0Dh
0x18001c2ec  lea     r13d, [r11-0Bh]
0x18001c2f0  movzx   edx, word ptr [rax]
0x18001c2f3  cmp     dx, 1Ah
0x18001c2f7  jz      loc_18001C41D
0x18001c2fd  lea     rcx, [rax+2]
0x18001c301  cmp     dx, r11w
0x18001c305  jnz     short loc_18001C31B
0x18001c307  cmp     rcx, r8
0x18001c30a  jnb     short loc_18001C33B
0x18001c30c  cmp     [rcx], r9w
0x18001c310  jnz     short loc_18001C31B
0x18001c312  add     rax, 4
0x18001c316  mov     edx, r9d
0x18001c319  jmp     short loc_18001C31E
0x18001c31b  mov     rax, rcx
0x18001c31e  mov     [rbx], dx
0x18001c321  mov     r9, r13
0x18001c324  mov     rcx, rbx
0x18001c327  mov     r9d, 0Ah
0x18001c32d  lea     rbx, [rbx+r13]
0x18001c331  cmp     rax, r8
0x18001c334  jb      short loc_18001C2F0
0x18001c336  jmp     loc_18001C452
0x18001c33b  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001c343  mov     [rsp+68h+Buffer], di
0x18001c348  mov     r8d, r13d; nNumberOfBytesToRead
0x18001c34b  mov     [rsp+68h+NumberOfBytesRead], edi
0x18001c352  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x18001c357  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x18001c35c  mov     rcx, r10; hFile
0x18001c35f  call    cs:__imp_ReadFile
0x18001c365  test    eax, eax
0x18001c367  jz      loc_18001C416
0x18001c36d  cmp     [rsp+68h+NumberOfBytesRead], edi
0x18001c374  jz      loc_18001C416
0x18001c37a  lea     r9, __pioinfo
0x18001c381  mov     rax, [r9+r12*8]
0x18001c385  test    byte ptr [rax+rbp*8+38h], 48h
0x18001c38a  mov     ebp, 0Ah
0x18001c38f  jz      short loc_18001C3F0
0x18001c391  movzx   eax, [rsp+68h+Buffer]
0x18001c396  cmp     ax, bp
0x18001c399  jnz     short loc_18001C3A3
0x18001c39b  mov     [rbx], bp
0x18001c39e  jmp     loc_18001C44F
0x18001c3a3  mov     [rsp+68h+arg_8], ax
0x18001c3a8  mov     rdx, r14
0x18001c3ab  mov     rax, r14
0x18001c3ae  sar     rdx, 6
0x18001c3b2  and     eax, 3Fh
0x18001c3b5  mov     word ptr [rbx], 0Dh
0x18001c3ba  lea     r8, [rax+rax*8]
0x18001c3be  mov     rax, [r9+rdx*8]
0x18001c3c2  lea     rcx, [rax+r8*8]
0x18001c3c6  mov     al, byte ptr [rsp+rdi+68h+arg_8]
0x18001c3ca  mov     [rcx+rdi+3Ah], al
0x18001c3ce  inc     rdi
0x18001c3d1  cmp     rdi, r13
0x18001c3d4  jl      short loc_18001C3BE
0x18001c3d6  mov     rax, r14
0x18001c3d9  sar     rax, 6
0x18001c3dd  and     r14d, 3Fh
0x18001c3e1  mov     rax, [r9+rax*8]
0x18001c3e5  lea     rcx, [r14+r14*8]
0x18001c3e9  mov     [rax+rcx*8+3Ch], bpl
0x18001c3ee  jmp     short loc_18001C44F
0x18001c3f0  cmp     [rsp+68h+Buffer], bp
0x18001c3f5  jnz     short loc_18001C3FC
0x18001c3f7  cmp     rbx, rsi
0x18001c3fa  jz      short loc_18001C39B
0x18001c3fc  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18001c403  mov     ecx, r15d
0x18001c406  lea     r8d, [rdx+3]
0x18001c40a  call    _lseeki64_nolock
0x18001c40f  cmp     [rsp+68h+Buffer], bp
0x18001c414  jz      short loc_18001C452
0x18001c416  mov     word ptr [rbx], 0Dh
0x18001c41b  jmp     short loc_18001C44F
0x18001c41d  mov     rcx, r15
0x18001c420  lea     r9, __pioinfo
0x18001c427  and     ecx, 3Fh
0x18001c42a  mov     rax, r15
0x18001c42d  sar     rax, 6
0x18001c431  lea     r8, [rcx+rcx*8]
0x18001c435  mov     rcx, [r9+rax*8]
0x18001c439  mov     al, [rcx+r8*8+38h]
0x18001c43e  test    al, 40h
0x18001c440  jnz     short loc_18001C44C
0x18001c442  or      al, r13b
0x18001c445  mov     [rcx+r8*8+38h], al
0x18001c44a  jmp     short loc_18001C452
0x18001c44c  mov     [rbx], dx
0x18001c44f  add     rbx, r13
0x18001c452  sub     rbx, rsi
0x18001c455  sar     rbx, 1
0x18001c458  lea     eax, [rbx+rbx]
0x18001c45b  mov     rbx, [rsp+68h+arg_18]
0x18001c463  add     rsp, 30h
0x18001c467  pop     r15
0x18001c469  pop     r14
0x18001c46b  pop     r13
0x18001c46d  pop     r12
0x18001c46f  pop     rdi
0x18001c470  pop     rsi
0x18001c471  pop     rbp
0x18001c472  retn
```
