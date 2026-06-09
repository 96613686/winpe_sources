# write_text_utf16le_nolock

- ea: `0x18033c694`
- end: `0x18033c7b0`
- name: `write_text_utf16le_nolock`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18033ca10`

## callees

- `0x18030c3f0`
- `0x18030cf60`
- `0x18033c694`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033c77d`
- `KERNEL32!GetLastError` at `0x18033c77d`
- `KERNEL32!WriteFile` at `0x18033c761`
- `KERNEL32!WriteFile` at `0x18033c761`

## pseudocode

```c
DWORD *__fastcall write_text_utf16le_nolock(DWORD *a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  __int64 v7; // rax
  void *v8; // r14
  char *v9; // rbx
  __int16 v10; // ax
  DWORD v11; // ebx
  DWORD v12; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v16; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
  *a1 = 0;
  v6 = a3;
  a1[1] = 0;
  v7 = _pioinfo[(__int64)a2 >> 6];
  a1[2] = 0;
  v8 = *(void **)(v7 + ((unsigned __int64)(a2 & 0x3F) << 6) + 40);
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v9 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v10 = *v6++;
        if ( v10 == 10 )
        {
          a1[2] += 2;
          *(_WORD *)v9 = 13;
          v9 += 2;
        }
        *(_WORD *)v9 = v10;
        v9 += 2;
      }
      while ( v9 < (char *)&v16 );
      v11 = 2 * ((v9 - Buffer) >> 1);
      if ( !WriteFile(v8, Buffer, v11, &NumberOfBytesWritten, 0) )
        break;
      v12 = NumberOfBytesWritten;
      a1[1] += NumberOfBytesWritten;
      if ( v12 < v11 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x18033c694  mov     [rsp+arg_0], rbx
0x18033c699  mov     [rsp+arg_10], rbp
0x18033c69e  push    rsi
0x18033c69f  push    rdi
0x18033c6a0  push    r14
0x18033c6a2  mov     eax, 1450h
0x18033c6a7  call    _alloca_probe
0x18033c6ac  sub     rsp, rax
0x18033c6af  mov     rax, cs:__security_cookie
0x18033c6b6  xor     rax, rsp
0x18033c6b9  mov     [rsp+1468h+var_28], rax
0x18033c6c1  mov     rdi, rcx
0x18033c6c4  movsxd  r10, edx
0x18033c6c7  mov     rax, r10
0x18033c6ca  mov     ebp, r9d
0x18033c6cd  sar     rax, 6
0x18033c6d1  lea     rcx, __pioinfo
0x18033c6d8  and     r10d, 3Fh
0x18033c6dc  add     rbp, r8
0x18033c6df  and     dword ptr [rdi], 0
0x18033c6e2  mov     rsi, r8
0x18033c6e5  and     dword ptr [rdi+4], 0
0x18033c6e9  mov     rax, [rcx+rax*8]
0x18033c6ed  and     dword ptr [rdi+8], 0
0x18033c6f1  shl     r10, 6
0x18033c6f5  mov     r14, [rax+r10+28h]
0x18033c6fa  cmp     r8, rbp
0x18033c6fd  jnb     loc_18033C785
0x18033c703  lea     rbx, [rsp+1468h+Buffer]
0x18033c708  cmp     rsi, rbp
0x18033c70b  jnb     short loc_18033C73E
0x18033c70d  movzx   eax, word ptr [rsi]
0x18033c710  add     rsi, 2
0x18033c714  cmp     ax, 0Ah
0x18033c718  jnz     short loc_18033C72A
0x18033c71a  add     dword ptr [rdi+8], 2
0x18033c71e  mov     ecx, 0Dh
0x18033c723  mov     [rbx], cx
0x18033c726  add     rbx, 2
0x18033c72a  mov     [rbx], ax
0x18033c72d  add     rbx, 2
0x18033c731  lea     rax, [rsp+1468h+var_2A]
0x18033c739  cmp     rbx, rax
0x18033c73c  jb      short loc_18033C708
0x18033c73e  and     [rsp+1468h+var_1448], 0
0x18033c744  lea     rax, [rsp+1468h+Buffer]
0x18033c749  sub     rbx, rax
0x18033c74c  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18033c751  sar     rbx, 1
0x18033c754  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18033c759  add     ebx, ebx
0x18033c75b  mov     rcx, r14; hFile
0x18033c75e  mov     r8d, ebx; nNumberOfBytesToWrite
0x18033c761  call    cs:__imp_WriteFile
0x18033c767  test    eax, eax
0x18033c769  jz      short loc_18033C77D
0x18033c76b  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18033c76f  add     [rdi+4], eax
0x18033c772  cmp     eax, ebx
0x18033c774  jb      short loc_18033C785
0x18033c776  cmp     rsi, rbp
0x18033c779  jb      short loc_18033C703
0x18033c77b  jmp     short loc_18033C785
0x18033c77d  call    cs:__imp_GetLastError
0x18033c783  mov     [rdi], eax
0x18033c785  mov     rax, rdi
0x18033c788  mov     rcx, [rsp+1468h+var_28]
0x18033c790  xor     rcx, rsp; StackCookie
0x18033c793  call    __security_check_cookie
0x18033c798  lea     r11, [rsp+1468h+var_18]
0x18033c7a0  mov     rbx, [r11+20h]
0x18033c7a4  mov     rbp, [r11+30h]
0x18033c7a8  mov     rsp, r11
0x18033c7ab  pop     r14
0x18033c7ad  pop     rdi
0x18033c7ae  pop     rsi
0x18033c7af  retn
```
