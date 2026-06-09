# write_text_utf16le_nolock

- ea: `0x1800185e8`
- end: `0x180018701`
- name: `write_text_utf16le_nolock`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180018960`

## callees

- `0x180007700`
- `0x1800185e8`
- `0x18001aff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800186ce`
- `KERNEL32!GetLastError` at `0x1800186ce`
- `KERNEL32!WriteFile` at `0x1800186b2`
- `KERNEL32!WriteFile` at `0x1800186b2`

## pseudocode

```c
__int64 __fastcall write_text_utf16le_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  __int16 v9; // ax
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v15; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = a3;
  v7 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v8 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v9 = *v6++;
        if ( v9 == 10 )
        {
          *(_DWORD *)(a1 + 8) += 2;
          *(_WORD *)v8 = 13;
          v8 += 2;
        }
        *(_WORD *)v8 = v9;
        v8 += 2;
      }
      while ( v8 < (char *)&v15 );
      v10 = 2 * ((v8 - Buffer) >> 1);
      if ( !WriteFile(v7, Buffer, v10, &NumberOfBytesWritten, 0) )
        break;
      v11 = NumberOfBytesWritten;
      *(_DWORD *)(a1 + 4) += NumberOfBytesWritten;
      if ( v11 < v10 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x1800185e8  mov     [rsp+arg_0], rbx
0x1800185ed  mov     [rsp+arg_10], rbp
0x1800185f2  push    rsi
0x1800185f3  push    rdi
0x1800185f4  push    r14
0x1800185f6  mov     eax, 1450h
0x1800185fb  call    _alloca_probe
0x180018600  sub     rsp, rax
0x180018603  mov     rax, cs:__security_cookie
0x18001860a  xor     rax, rsp
0x18001860d  mov     [rsp+1468h+var_28], rax
0x180018615  movsxd  r10, edx
0x180018618  mov     rdi, rcx
0x18001861b  mov     rax, r10
0x18001861e  mov     ebp, r9d
0x180018621  sar     rax, 6
0x180018625  lea     rcx, __pioinfo
0x18001862c  and     r10d, 3Fh
0x180018630  add     rbp, r8
0x180018633  mov     rsi, r8
0x180018636  mov     rax, [rcx+rax*8]
0x18001863a  lea     rdx, [r10+r10*8]
0x18001863e  mov     r14, [rax+rdx*8+28h]
0x180018643  xor     eax, eax
0x180018645  mov     [rdi], rax
0x180018648  mov     [rdi+8], eax
0x18001864b  cmp     r8, rbp
0x18001864e  jnb     loc_1800186D6
0x180018654  lea     rbx, [rsp+1468h+Buffer]
0x180018659  cmp     rsi, rbp
0x18001865c  jnb     short loc_18001868F
0x18001865e  movzx   eax, word ptr [rsi]
0x180018661  add     rsi, 2
0x180018665  cmp     ax, 0Ah
0x180018669  jnz     short loc_18001867B
0x18001866b  add     dword ptr [rdi+8], 2
0x18001866f  mov     ecx, 0Dh
0x180018674  mov     [rbx], cx
0x180018677  add     rbx, 2
0x18001867b  mov     [rbx], ax
0x18001867e  add     rbx, 2
0x180018682  lea     rax, [rsp+1468h+var_2A]
0x18001868a  cmp     rbx, rax
0x18001868d  jb      short loc_180018659
0x18001868f  and     [rsp+1468h+var_1448], 0
0x180018695  lea     rax, [rsp+1468h+Buffer]
0x18001869a  sub     rbx, rax
0x18001869d  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800186a2  sar     rbx, 1
0x1800186a5  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x1800186aa  add     ebx, ebx
0x1800186ac  mov     rcx, r14; hFile
0x1800186af  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800186b2  call    cs:__imp_WriteFile
0x1800186b8  test    eax, eax
0x1800186ba  jz      short loc_1800186CE
0x1800186bc  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x1800186c0  add     [rdi+4], eax
0x1800186c3  cmp     eax, ebx
0x1800186c5  jb      short loc_1800186D6
0x1800186c7  cmp     rsi, rbp
0x1800186ca  jb      short loc_180018654
0x1800186cc  jmp     short loc_1800186D6
0x1800186ce  call    cs:__imp_GetLastError
0x1800186d4  mov     [rdi], eax
0x1800186d6  mov     rax, rdi
0x1800186d9  mov     rcx, [rsp+1468h+var_28]
0x1800186e1  xor     rcx, rsp; StackCookie
0x1800186e4  call    __security_check_cookie
0x1800186e9  lea     r11, [rsp+1468h+var_18]
0x1800186f1  mov     rbx, [r11+20h]
0x1800186f5  mov     rbp, [r11+30h]
0x1800186f9  mov     rsp, r11
0x1800186fc  pop     r14
0x1800186fe  pop     rdi
0x1800186ff  pop     rsi
0x180018700  retn
```
