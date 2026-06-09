# common_ftell_translated_utf8_nolock

- ea: `0x180350d1c`
- end: `0x180350e91`
- name: `common_ftell_translated_utf8_nolock`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180350a2c`

## callees

- `0x18030c3f0`
- `0x18030cf60`
- `0x18033ce80`
- `0x18034b3d4`
- `0x180350d1c`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180350dea`
- `KERNEL32!ReadFile` at `0x180350dea`

## pseudocode

```c
__int64 __fastcall common_ftell_translated_utf8_nolock(__int64 a1, __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdi
  int v5; // r15d
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  __int64 v9; // rbp
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r12
  unsigned __int8 *v13; // rdx
  unsigned __int8 *v14; // rcx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-1058h] BYREF
  _BYTE Buffer[4096]; // [rsp+40h] [rbp-1048h] BYREF

  v3 = fileno((FILE *)a1);
  v4 = 0;
  v5 = v3;
  if ( !*(_DWORD *)(a1 + 16) )
    return a2;
  v7 = (__int64)v3 >> 6;
  v8 = (unsigned __int64)(v3 & 0x3F) << 6;
  v9 = (*(_QWORD *)a1 - *(_QWORD *)(a1 + 8)) / 2LL;
  v10 = lseeki64(v3, *(_QWORD *)(_pioinfo[v7] + v8 + 48), 0);
  v11 = _pioinfo[v7];
  v12 = v10;
  if ( v10 != *(_QWORD *)(v11 + v8 + 48)
    || !ReadFile(*(HANDLE *)(v11 + v8 + 40), Buffer, 0x1000u, &NumberOfBytesRead, 0)
    || lseeki64(v5, a2, 0) < 0
    || v9 > NumberOfBytesRead )
  {
    return -1;
  }
  v13 = &Buffer[NumberOfBytesRead];
  v14 = Buffer;
  if ( v9 )
  {
    do
    {
      if ( v14 >= v13 )
        break;
      if ( *v14 == 13 )
      {
        if ( v14 < v13 - 1 && v14[1] == 10 )
          ++v14;
      }
      else
      {
        v14 += *((char *)lookuptrailbytes + *v14);
      }
      ++v4;
      ++v14;
    }
    while ( v4 != v9 );
  }
  return v12 + v14 - Buffer;
}

```

## disassembly

```asm
0x180350d1c  mov     [rsp+arg_10], rbx
0x180350d21  mov     [rsp+arg_0], rcx
0x180350d26  push    rbp
0x180350d27  push    rsi
0x180350d28  push    rdi
0x180350d29  push    r12
0x180350d2b  push    r13
0x180350d2d  push    r14
0x180350d2f  push    r15
0x180350d31  mov     eax, 1050h
0x180350d36  call    _alloca_probe
0x180350d3b  sub     rsp, rax
0x180350d3e  mov     rax, cs:__security_cookie
0x180350d45  xor     rax, rsp
0x180350d48  mov     [rsp+1088h+var_48], rax
0x180350d50  mov     rsi, rdx
0x180350d53  call    _fileno
0x180350d58  mov     rcx, [rsp+1088h+arg_0]
0x180350d60  xor     edi, edi
0x180350d62  movsxd  r15, eax
0x180350d65  cmp     [rcx+10h], edi
0x180350d68  jnz     short loc_180350D72
0x180350d6a  mov     rax, rsi
0x180350d6d  jmp     loc_180350E66
0x180350d72  mov     rax, [rcx]
0x180350d75  lea     r13, cs:180000000h
0x180350d7c  sub     rax, [rcx+8]
0x180350d80  mov     r14, r15
0x180350d83  cqo
0x180350d85  mov     rbx, r15
0x180350d88  sub     rax, rdx
0x180350d8b  sar     rbx, 6
0x180350d8f  sar     rax, 1
0x180350d92  and     r14d, 3Fh
0x180350d96  shl     r14, 6
0x180350d9a  xor     r8d, r8d; Origin
0x180350d9d  mov     ecx, r15d; FileHandle
0x180350da0  mov     rbp, rax
0x180350da3  mov     rdx, rva __pioinfo[r13+rbx*8]
0x180350dab  mov     rdx, [rdx+r14+30h]; Offset
0x180350db0  call    _lseeki64
0x180350db5  mov     rcx, rva __pioinfo[r13+rbx*8]
0x180350dbd  mov     r12, rax
0x180350dc0  cmp     rax, [rcx+r14+30h]
0x180350dc5  jz      short loc_180350DD0
0x180350dc7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180350dcb  jmp     loc_180350E66
0x180350dd0  mov     rcx, [rcx+r14+28h]; hFile
0x180350dd5  lea     r9, [rsp+1088h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180350dda  mov     r8d, 1000h; nNumberOfBytesToRead
0x180350de0  mov     [rsp+1088h+lpOverlapped], rdi; lpOverlapped
0x180350de5  lea     rdx, [rsp+1088h+Buffer]; lpBuffer
0x180350dea  call    cs:__imp_ReadFile
0x180350df0  test    eax, eax
0x180350df2  jz      short loc_180350DC7
0x180350df4  xor     r8d, r8d; Origin
0x180350df7  mov     rdx, rsi; Offset
0x180350dfa  mov     ecx, r15d; FileHandle
0x180350dfd  call    _lseeki64
0x180350e02  test    rax, rax
0x180350e05  js      short loc_180350DC7
0x180350e07  mov     eax, [rsp+1088h+NumberOfBytesRead]
0x180350e0b  cmp     rbp, rax
0x180350e0e  jg      short loc_180350DC7
0x180350e10  lea     rdx, [rsp+1088h+Buffer]
0x180350e15  add     rdx, rax
0x180350e18  lea     rcx, [rsp+1088h+Buffer]
0x180350e1d  test    rbp, rbp
0x180350e20  jz      short loc_180350E5A
0x180350e22  cmp     rcx, rdx
0x180350e25  jnb     short loc_180350E5A
0x180350e27  cmp     byte ptr [rcx], 0Dh
0x180350e2a  jnz     short loc_180350E40
0x180350e2c  lea     rax, [rdx-1]
0x180350e30  cmp     rcx, rax
0x180350e33  jnb     short loc_180350E4F
0x180350e35  cmp     byte ptr [rcx+1], 0Ah
0x180350e39  jnz     short loc_180350E4F
0x180350e3b  inc     rcx
0x180350e3e  jmp     short loc_180350E4F
0x180350e40  movzx   eax, byte ptr [rcx]
0x180350e43  movsx   rax, byte ptr [rax+r13+4A85D0h]
0x180350e4c  add     rcx, rax
0x180350e4f  inc     rdi
0x180350e52  inc     rcx
0x180350e55  cmp     rdi, rbp
0x180350e58  jnz     short loc_180350E22
0x180350e5a  lea     rax, [rsp+1088h+Buffer]
0x180350e5f  sub     rcx, rax
0x180350e62  lea     rax, [r12+rcx]
0x180350e66  mov     rcx, [rsp+1088h+var_48]
0x180350e6e  xor     rcx, rsp; StackCookie
0x180350e71  call    __security_check_cookie
0x180350e76  mov     rbx, [rsp+1088h+arg_10]
0x180350e7e  add     rsp, 1050h
0x180350e85  pop     r15
0x180350e87  pop     r14
0x180350e89  pop     r13
0x180350e8b  pop     r12
0x180350e8d  pop     rdi
0x180350e8e  pop     rsi
0x180350e8f  pop     rbp
0x180350e90  retn
```
