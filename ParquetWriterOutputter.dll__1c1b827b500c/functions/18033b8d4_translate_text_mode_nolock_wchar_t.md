# translate_text_mode_nolock_wchar_t_

- ea: `0x18033b8d4`
- end: `0x18033bb01`
- name: `translate_text_mode_nolock_wchar_t_`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18033bf1c`

## callees

- `0x18033b8d4`
- `0x18033ce88`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18033b9ba`
- `KERNEL32!ReadFile` at `0x18033b9ba`

## pseudocode

```c
__int64 __fastcall translate_text_mode_nolock_wchar_t_(unsigned int a1, __int16 *a2, __int64 a3)
{
  __int64 v4; // r15
  unsigned __int64 v5; // rdi
  __int64 v7; // rax
  void *v8; // rcx
  __int16 *v9; // r12
  __int16 *v10; // rsi
  __int16 *v11; // rbx
  __int16 *v12; // rbp
  __int16 v13; // ax
  __int64 i; // rdx
  __int64 v15; // rcx
  char v16; // al
  __int16 Buffer; // [rsp+80h] [rbp+8h] BYREF
  __int16 v19; // [rsp+88h] [rbp+10h]
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF
  void *v21; // [rsp+98h] [rbp+20h]

  v4 = (__int64)(int)a1 >> 6;
  v5 = (unsigned __int64)(a1 & 0x3F) << 6;
  v7 = _pioinfo[v4];
  v8 = *(void **)(v7 + v5 + 40);
  v21 = v8;
  if ( a3 && *a2 == 10 )
    *(_BYTE *)(v7 + v5 + 56) |= 4u;
  else
    *(_BYTE *)(v7 + v5 + 56) &= ~4u;
  v9 = &a2[a3];
  v10 = a2;
  v11 = a2;
  if ( a2 < v9 )
  {
    v12 = a2 + 1;
    do
    {
      v13 = *v10;
      if ( *v10 == 26 )
      {
        v15 = _pioinfo[v4];
        v16 = *(_BYTE *)(v15 + v5 + 56);
        if ( (v16 & 0x40) != 0 )
          *v11++ = *v10;
        else
          *(_BYTE *)(v15 + v5 + 56) = v16 | 2;
        return 2 * (v11 - a2);
      }
      if ( v13 == 13 )
      {
        if ( v12 >= v9 )
        {
          ++v10;
          ++v12;
          if ( ReadFile(v8, &Buffer, 2u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
          {
            if ( (*(_BYTE *)(_pioinfo[v4] + v5 + 56) & 0x48) != 0 )
            {
              if ( Buffer == 10 )
              {
                *v11 = 10;
              }
              else
              {
                v19 = Buffer;
                *v11 = 13;
                for ( i = 0; i < 2; ++i )
                  *(_BYTE *)(v5 + _pioinfo[v4] + i + 58) = *((_BYTE *)&v19 + i);
                *(_BYTE *)(_pioinfo[v4] + v5 + 60) = 10;
              }
            }
            else if ( Buffer == 10 && v11 == a2 )
            {
              *v11++ = 10;
            }
            else
            {
              lseeki64_nolock(a1, -2, 1);
              if ( Buffer != 10 )
                *v11++ = 13;
            }
          }
          else
          {
            *v11++ = 13;
          }
          v8 = v21;
          continue;
        }
        if ( *v12 == 10 )
        {
          v10 += 2;
          *v11 = 10;
          v12 += 2;
          ++v11;
          continue;
        }
        *v11 = 13;
      }
      else
      {
        *v11 = v13;
      }
      ++v11;
      ++v10;
      ++v12;
    }
    while ( v10 < v9 );
  }
  return 2 * (v11 - a2);
}

```

## disassembly

```asm
0x18033b8d4  push    rbx
0x18033b8d6  push    rbp
0x18033b8d7  push    rsi
0x18033b8d8  push    rdi
0x18033b8d9  push    r12
0x18033b8db  push    r13
0x18033b8dd  push    r14
0x18033b8df  push    r15
0x18033b8e1  sub     rsp, 38h
0x18033b8e5  movsxd  r13, ecx
0x18033b8e8  lea     r10, __pioinfo
0x18033b8ef  mov     rdi, r13
0x18033b8f2  mov     r15, r13
0x18033b8f5  sar     r15, 6
0x18033b8f9  and     edi, 3Fh
0x18033b8fc  shl     rdi, 6
0x18033b900  mov     r14, rdx
0x18033b903  mov     r9d, 0Ah
0x18033b909  mov     rax, [r10+r15*8]
0x18033b90d  mov     rcx, [rax+rdi+28h]; hFile
0x18033b912  mov     [rsp+78h+arg_18], rcx
0x18033b91a  test    r8, r8
0x18033b91d  jz      short loc_18033B92C
0x18033b91f  cmp     [rdx], r9w
0x18033b923  jnz     short loc_18033B92C
0x18033b925  or      byte ptr [rax+rdi+38h], 4
0x18033b92a  jmp     short loc_18033B931
0x18033b92c  and     byte ptr [rax+rdi+38h], 0FBh
0x18033b931  lea     r12, [rdx+r8*2]
0x18033b935  mov     rsi, rdx
0x18033b938  mov     rbx, rdx
0x18033b93b  cmp     rdx, r12
0x18033b93e  jnb     loc_18033BAE6
0x18033b944  lea     rbp, [rdx+2]
0x18033b948  mov     edx, 0Dh
0x18033b94d  movzx   eax, word ptr [rsi]
0x18033b950  cmp     ax, 1Ah
0x18033b954  jz      loc_18033BAC8
0x18033b95a  cmp     ax, dx
0x18033b95d  jz      short loc_18033B973
0x18033b95f  mov     [rbx], ax
0x18033b962  add     rbx, 2
0x18033b966  add     rsi, 2
0x18033b96a  add     rbp, 2
0x18033b96e  jmp     loc_18033BA0D
0x18033b973  cmp     rbp, r12
0x18033b976  jnb     short loc_18033B996
0x18033b978  cmp     [rbp+0], r9w
0x18033b97d  jnz     short loc_18033B991
0x18033b97f  add     rsi, 4
0x18033b983  mov     [rbx], r9w
0x18033b987  add     rbp, 4
0x18033b98b  add     rbx, 2
0x18033b98f  jmp     short loc_18033BA0D
0x18033b991  mov     [rbx], dx
0x18033b994  jmp     short loc_18033B962
0x18033b996  and     [rsp+78h+var_58], 0
0x18033b99c  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18033b9a4  mov     r8d, 2; nNumberOfBytesToRead
0x18033b9aa  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x18033b9b2  add     rsi, 2
0x18033b9b6  add     rbp, 2
0x18033b9ba  call    cs:__imp_ReadFile
0x18033b9c0  test    eax, eax
0x18033b9c2  jz      loc_18033BAAC
0x18033b9c8  cmp     [rsp+78h+NumberOfBytesRead], 0
0x18033b9d0  jz      loc_18033BAAC
0x18033b9d6  lea     r10, __pioinfo
0x18033b9dd  mov     r9d, 0Ah
0x18033b9e3  mov     rax, [r10+r15*8]
0x18033b9e7  test    byte ptr [rax+rdi+38h], 48h
0x18033b9ec  jz      short loc_18033BA53
0x18033b9ee  movzx   eax, [rsp+78h+Buffer]
0x18033b9f6  cmp     ax, r9w
0x18033b9fa  jnz     short loc_18033BA1B
0x18033b9fc  mov     [rbx], r9w
0x18033ba00  mov     edx, 0Dh
0x18033ba05  mov     rcx, [rsp+78h+arg_18]
0x18033ba0d  cmp     rsi, r12
0x18033ba10  jb      loc_18033B94D
0x18033ba16  jmp     loc_18033BAE6
0x18033ba1b  mov     ecx, 0Dh
0x18033ba20  mov     [rsp+78h+arg_8], ax
0x18033ba28  mov     [rbx], cx
0x18033ba2b  xor     edx, edx
0x18033ba2d  mov     rcx, [r10+r15*8]
0x18033ba31  mov     al, byte ptr [rsp+rdx+78h+arg_8]
0x18033ba38  add     rcx, rdi
0x18033ba3b  mov     [rcx+rdx+3Ah], al
0x18033ba3f  inc     rdx
0x18033ba42  cmp     rdx, 2
0x18033ba46  jl      short loc_18033BA2D
0x18033ba48  mov     rax, [r10+r15*8]
0x18033ba4c  mov     [rax+rdi+3Ch], r9b
0x18033ba51  jmp     short loc_18033BA00
0x18033ba53  cmp     [rsp+78h+Buffer], r9w
0x18033ba5c  jnz     short loc_18033BA6D
0x18033ba5e  cmp     rbx, r14
0x18033ba61  jnz     short loc_18033BA6D
0x18033ba63  mov     [rbx], r9w
0x18033ba67  add     rbx, 2
0x18033ba6b  jmp     short loc_18033BA00
0x18033ba6d  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18033ba74  mov     ecx, r13d
0x18033ba77  lea     r8d, [rdx+3]
0x18033ba7b  call    _lseeki64_nolock
0x18033ba80  mov     r9d, 0Ah
0x18033ba86  lea     r10, __pioinfo
0x18033ba8d  cmp     [rsp+78h+Buffer], r9w
0x18033ba96  jz      loc_18033BA00
0x18033ba9c  lea     edx, [r9+3]
0x18033baa0  mov     [rbx], dx
0x18033baa3  add     rbx, 2
0x18033baa7  jmp     loc_18033BA05
0x18033baac  mov     edx, 0Dh
0x18033bab1  lea     r10, __pioinfo
0x18033bab8  mov     [rbx], dx
0x18033babb  add     rbx, 2
0x18033babf  lea     r9d, [rdx-3]
0x18033bac3  jmp     loc_18033BA05
0x18033bac8  mov     rcx, [r10+r15*8]
0x18033bacc  mov     al, [rcx+rdi+38h]
0x18033bad0  test    al, 40h
0x18033bad2  jnz     short loc_18033BADC
0x18033bad4  or      al, 2
0x18033bad6  mov     [rcx+rdi+38h], al
0x18033bada  jmp     short loc_18033BAE6
0x18033badc  movzx   ecx, word ptr [rsi]
0x18033badf  mov     [rbx], cx
0x18033bae2  add     rbx, 2
0x18033bae6  sub     rbx, r14
0x18033bae9  sar     rbx, 1
0x18033baec  lea     rax, [rbx+rbx]
0x18033baf0  add     rsp, 38h
0x18033baf4  pop     r15
0x18033baf6  pop     r14
0x18033baf8  pop     r13
0x18033bafa  pop     r12
0x18033bafc  pop     rdi
0x18033bafd  pop     rsi
0x18033bafe  pop     rbp
0x18033baff  pop     rbx
0x18033bb00  retn
```
