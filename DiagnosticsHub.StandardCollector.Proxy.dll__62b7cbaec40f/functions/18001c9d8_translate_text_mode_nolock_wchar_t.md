# translate_text_mode_nolock_wchar_t_

- ea: `0x18001c9d8`
- end: `0x18001cbd3`
- name: `translate_text_mode_nolock_wchar_t_`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001d15c`

## callees

- `0x18001b848`
- `0x18001c9d8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18001cabf`
- `KERNEL32!ReadFile` at `0x18001cabf`

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
0x18001c9d8  mov     [rsp+arg_18], rbx
0x18001c9dd  push    rbp
0x18001c9de  push    rsi
0x18001c9df  push    rdi
0x18001c9e0  push    r12
0x18001c9e2  push    r13
0x18001c9e4  push    r14
0x18001c9e6  push    r15
0x18001c9e8  sub     rsp, 30h
0x18001c9ec  movsxd  r15, ecx
0x18001c9ef  xor     edi, edi
0x18001c9f1  mov     rax, r15
0x18001c9f4  lea     rcx, __pioinfo
0x18001c9fb  and     eax, 3Fh
0x18001c9fe  mov     r12, r15
0x18001ca01  sar     r12, 6
0x18001ca05  mov     rsi, rdx
0x18001ca08  lea     r9d, [rdi+0Ah]
0x18001ca0c  mov     r14, r15
0x18001ca0f  lea     rbp, [rax+rax*8]
0x18001ca13  mov     rax, [rcx+r12*8]
0x18001ca17  mov     r10, [rax+rbp*8+28h]
0x18001ca1c  test    r8, r8
0x18001ca1f  jz      short loc_18001CA2E
0x18001ca21  cmp     [rdx], r9w
0x18001ca25  jnz     short loc_18001CA2E
0x18001ca27  or      byte ptr [rax+rbp*8+38h], 4
0x18001ca2c  jmp     short loc_18001CA33
0x18001ca2e  and     byte ptr [rax+rbp*8+38h], 0FBh
0x18001ca33  lea     r8, [rdx+r8*2]
0x18001ca37  mov     rax, rsi
0x18001ca3a  mov     rbx, rsi
0x18001ca3d  cmp     rsi, r8
0x18001ca40  jnb     loc_18001CBB2
0x18001ca46  mov     r11d, 0Dh
0x18001ca4c  lea     r13d, [r11-0Bh]
0x18001ca50  movzx   edx, word ptr [rax]
0x18001ca53  cmp     dx, 1Ah
0x18001ca57  jz      loc_18001CB7D
0x18001ca5d  lea     rcx, [rax+2]
0x18001ca61  cmp     dx, r11w
0x18001ca65  jnz     short loc_18001CA7B
0x18001ca67  cmp     rcx, r8
0x18001ca6a  jnb     short loc_18001CA9B
0x18001ca6c  cmp     [rcx], r9w
0x18001ca70  jnz     short loc_18001CA7B
0x18001ca72  add     rax, 4
0x18001ca76  mov     edx, r9d
0x18001ca79  jmp     short loc_18001CA7E
0x18001ca7b  mov     rax, rcx
0x18001ca7e  mov     [rbx], dx
0x18001ca81  mov     r9, r13
0x18001ca84  mov     rcx, rbx
0x18001ca87  mov     r9d, 0Ah
0x18001ca8d  lea     rbx, [rbx+r13]
0x18001ca91  cmp     rax, r8
0x18001ca94  jb      short loc_18001CA50
0x18001ca96  jmp     loc_18001CBB2
0x18001ca9b  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001caa3  mov     [rsp+68h+Buffer], di
0x18001caa8  mov     r8d, r13d; nNumberOfBytesToRead
0x18001caab  mov     [rsp+68h+NumberOfBytesRead], edi
0x18001cab2  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x18001cab7  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x18001cabc  mov     rcx, r10; hFile
0x18001cabf  call    cs:__imp_ReadFile
0x18001cac5  test    eax, eax
0x18001cac7  jz      loc_18001CB76
0x18001cacd  cmp     [rsp+68h+NumberOfBytesRead], edi
0x18001cad4  jz      loc_18001CB76
0x18001cada  lea     r9, __pioinfo
0x18001cae1  mov     rax, [r9+r12*8]
0x18001cae5  test    byte ptr [rax+rbp*8+38h], 48h
0x18001caea  mov     ebp, 0Ah
0x18001caef  jz      short loc_18001CB50
0x18001caf1  movzx   eax, [rsp+68h+Buffer]
0x18001caf6  cmp     ax, bp
0x18001caf9  jnz     short loc_18001CB03
0x18001cafb  mov     [rbx], bp
0x18001cafe  jmp     loc_18001CBAF
0x18001cb03  mov     [rsp+68h+arg_8], ax
0x18001cb08  mov     rdx, r14
0x18001cb0b  mov     rax, r14
0x18001cb0e  sar     rdx, 6
0x18001cb12  and     eax, 3Fh
0x18001cb15  mov     word ptr [rbx], 0Dh
0x18001cb1a  lea     r8, [rax+rax*8]
0x18001cb1e  mov     rax, [r9+rdx*8]
0x18001cb22  lea     rcx, [rax+r8*8]
0x18001cb26  mov     al, byte ptr [rsp+rdi+68h+arg_8]
0x18001cb2a  mov     [rcx+rdi+3Ah], al
0x18001cb2e  inc     rdi
0x18001cb31  cmp     rdi, r13
0x18001cb34  jl      short loc_18001CB1E
0x18001cb36  mov     rax, r14
0x18001cb39  sar     rax, 6
0x18001cb3d  and     r14d, 3Fh
0x18001cb41  mov     rax, [r9+rax*8]
0x18001cb45  lea     rcx, [r14+r14*8]
0x18001cb49  mov     [rax+rcx*8+3Ch], bpl
0x18001cb4e  jmp     short loc_18001CBAF
0x18001cb50  cmp     [rsp+68h+Buffer], bp
0x18001cb55  jnz     short loc_18001CB5C
0x18001cb57  cmp     rbx, rsi
0x18001cb5a  jz      short loc_18001CAFB
0x18001cb5c  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18001cb63  mov     ecx, r15d
0x18001cb66  lea     r8d, [rdx+3]
0x18001cb6a  call    _lseeki64_nolock
0x18001cb6f  cmp     [rsp+68h+Buffer], bp
0x18001cb74  jz      short loc_18001CBB2
0x18001cb76  mov     word ptr [rbx], 0Dh
0x18001cb7b  jmp     short loc_18001CBAF
0x18001cb7d  mov     rcx, r15
0x18001cb80  lea     r9, __pioinfo
0x18001cb87  and     ecx, 3Fh
0x18001cb8a  mov     rax, r15
0x18001cb8d  sar     rax, 6
0x18001cb91  lea     r8, [rcx+rcx*8]
0x18001cb95  mov     rcx, [r9+rax*8]
0x18001cb99  mov     al, [rcx+r8*8+38h]
0x18001cb9e  test    al, 40h
0x18001cba0  jnz     short loc_18001CBAC
0x18001cba2  or      al, r13b
0x18001cba5  mov     [rcx+r8*8+38h], al
0x18001cbaa  jmp     short loc_18001CBB2
0x18001cbac  mov     [rbx], dx
0x18001cbaf  add     rbx, r13
0x18001cbb2  sub     rbx, rsi
0x18001cbb5  sar     rbx, 1
0x18001cbb8  lea     eax, [rbx+rbx]
0x18001cbbb  mov     rbx, [rsp+68h+arg_18]
0x18001cbc3  add     rsp, 30h
0x18001cbc7  pop     r15
0x18001cbc9  pop     r14
0x18001cbcb  pop     r13
0x18001cbcd  pop     r12
0x18001cbcf  pop     rdi
0x18001cbd0  pop     rsi
0x18001cbd1  pop     rbp
0x18001cbd2  retn
```
