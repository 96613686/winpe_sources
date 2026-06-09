# translate_text_mode_nolock_char_

- ea: `0x18001c840`
- end: `0x18001c9d5`
- name: `translate_text_mode_nolock_char_`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001b848`
- `0x18001c840`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18001c914`
- `KERNEL32!ReadFile` at `0x18001c914`

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
0x18001c840  mov     [rsp+arg_10], rbx
0x18001c845  mov     [rsp+arg_18], rbp
0x18001c84a  push    rsi
0x18001c84b  push    rdi
0x18001c84c  push    r12
0x18001c84e  push    r14
0x18001c850  push    r15
0x18001c852  sub     rsp, 30h
0x18001c856  movsxd  rbp, ecx
0x18001c859  lea     r9, __pioinfo
0x18001c860  mov     rax, rbp
0x18001c863  mov     r15, rbp
0x18001c866  and     eax, 3Fh
0x18001c869  sar     r15, 6
0x18001c86d  mov     rdi, rdx
0x18001c870  mov     r14, rbp
0x18001c873  lea     rsi, [rax+rax*8]
0x18001c877  mov     rax, [r9+r15*8]
0x18001c87b  mov     r10, [rax+rsi*8+28h]
0x18001c880  test    r8, r8
0x18001c883  jz      short loc_18001C891
0x18001c885  cmp     byte ptr [rdx], 0Ah
0x18001c888  jnz     short loc_18001C891
0x18001c88a  or      byte ptr [rax+rsi*8+38h], 4
0x18001c88f  jmp     short loc_18001C896
0x18001c891  and     byte ptr [rax+rsi*8+38h], 0FBh
0x18001c896  add     r8, rdi
0x18001c899  mov     rax, rdi
0x18001c89c  mov     rbx, rdi
0x18001c89f  cmp     rdi, r8
0x18001c8a2  jnb     loc_18001C9BA
0x18001c8a8  mov     r12d, 1
0x18001c8ae  mov     dl, [rax]
0x18001c8b0  cmp     dl, 1Ah
0x18001c8b3  jz      loc_18001C987
0x18001c8b9  lea     rcx, [rax+1]
0x18001c8bd  cmp     dl, 0Dh
0x18001c8c0  jnz     short loc_18001C8D4
0x18001c8c2  cmp     rcx, r8
0x18001c8c5  jnb     short loc_18001C8F2
0x18001c8c7  cmp     byte ptr [rcx], 0Ah
0x18001c8ca  jnz     short loc_18001C8D4
0x18001c8cc  add     rax, 2
0x18001c8d0  mov     dl, 0Ah
0x18001c8d2  jmp     short loc_18001C8D7
0x18001c8d4  mov     rax, rcx
0x18001c8d7  mov     [rbx], dl
0x18001c8d9  mov     rcx, rbx
0x18001c8dc  lea     rbx, [r12+rbx]
0x18001c8e0  mov     r9, r12
0x18001c8e3  mov     [rsp+58h+NumberOfBytesRead], rbx
0x18001c8e8  cmp     rax, r8
0x18001c8eb  jb      short loc_18001C8AE
0x18001c8ed  jmp     loc_18001C9BA
0x18001c8f2  xor     r9d, r9d
0x18001c8f5  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x18001c8fa  mov     [rsp+58h+Buffer], r9b
0x18001c8ff  mov     r8d, r12d; nNumberOfBytesToRead
0x18001c902  mov     dword ptr [rsp+58h+NumberOfBytesRead], r9d
0x18001c907  mov     rcx, r10; hFile
0x18001c90a  mov     [rsp+58h+lpOverlapped], r9; lpOverlapped
0x18001c90f  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001c914  call    cs:__imp_ReadFile
0x18001c91a  test    eax, eax
0x18001c91c  jz      short loc_18001C982
0x18001c91e  cmp     dword ptr [rsp+58h+NumberOfBytesRead], 0
0x18001c923  jz      short loc_18001C982
0x18001c925  lea     r9, __pioinfo
0x18001c92c  mov     rax, [r9+r15*8]
0x18001c930  test    byte ptr [rax+rsi*8+38h], 48h
0x18001c935  jz      short loc_18001C961
0x18001c937  mov     dl, [rsp+58h+Buffer]
0x18001c93b  cmp     dl, 0Ah
0x18001c93e  jnz     short loc_18001C945
0x18001c940  mov     byte ptr [rbx], 0Ah
0x18001c943  jmp     short loc_18001C9B7
0x18001c945  mov     rax, r14
0x18001c948  mov     byte ptr [rbx], 0Dh
0x18001c94b  sar     rax, 6
0x18001c94f  and     r14d, 3Fh
0x18001c953  mov     rax, [r9+rax*8]
0x18001c957  lea     rcx, [r14+r14*8]
0x18001c95b  mov     [rax+rcx*8+3Ah], dl
0x18001c95f  jmp     short loc_18001C9B7
0x18001c961  cmp     [rsp+58h+Buffer], 0Ah
0x18001c966  jnz     short loc_18001C96D
0x18001c968  cmp     rbx, rdi
0x18001c96b  jz      short loc_18001C940
0x18001c96d  mov     r8d, r12d
0x18001c970  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c974  mov     ecx, ebp
0x18001c976  call    _lseeki64_nolock
0x18001c97b  cmp     [rsp+58h+Buffer], 0Ah
0x18001c980  jz      short loc_18001C9BA
0x18001c982  mov     byte ptr [rbx], 0Dh
0x18001c985  jmp     short loc_18001C9B7
0x18001c987  mov     rcx, rbp
0x18001c98a  lea     r9, __pioinfo
0x18001c991  and     ecx, 3Fh
0x18001c994  mov     rax, rbp
0x18001c997  sar     rax, 6
0x18001c99b  lea     r8, [rcx+rcx*8]
0x18001c99f  mov     rcx, [r9+rax*8]
0x18001c9a3  mov     al, [rcx+r8*8+38h]
0x18001c9a8  test    al, 40h
0x18001c9aa  jnz     short loc_18001C9B5
0x18001c9ac  or      al, 2
0x18001c9ae  mov     [rcx+r8*8+38h], al
0x18001c9b3  jmp     short loc_18001C9BA
0x18001c9b5  mov     [rbx], dl
0x18001c9b7  add     rbx, r12
0x18001c9ba  mov     rbp, [rsp+58h+arg_18]
0x18001c9bf  sub     ebx, edi
0x18001c9c1  mov     eax, ebx
0x18001c9c3  mov     rbx, [rsp+58h+arg_10]
0x18001c9c8  add     rsp, 30h
0x18001c9cc  pop     r15
0x18001c9ce  pop     r14
0x18001c9d0  pop     r12
0x18001c9d2  pop     rdi
0x18001c9d3  pop     rsi
0x18001c9d4  retn
```
