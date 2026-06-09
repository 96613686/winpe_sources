# write_double_translated_ansi_nolock

- ea: `0x18033c384`
- end: `0x18033c58c`
- name: `write_double_translated_ansi_nolock`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18033ca10`

## callees

- `0x18030c3f0`
- `0x18033c384`
- `0x180345864`
- `0x18034a3d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033c55a`
- `KERNEL32!GetLastError` at `0x18033c55a`
- `KERNEL32!WideCharToMultiByte` at `0x18033c4bd`
- `KERNEL32!WideCharToMultiByte` at `0x18033c4bd`
- `KERNEL32!WriteFile` at `0x18033c4e3`
- `KERNEL32!WriteFile` at `0x18033c522`
- `KERNEL32!WriteFile` at `0x18033c4e3`
- `KERNEL32!WriteFile` at `0x18033c522`
- `KERNEL32!GetConsoleCP` at `0x18033c3e1`
- `KERNEL32!GetConsoleCP` at `0x18033c3e1`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(__int64 a1, int a2, const char *a3, int a4)
{
  __int64 v4; // r15
  unsigned __int64 v5; // rsi
  unsigned __int64 v8; // r12
  const char *v9; // rdi
  bool i; // cf
  char v11; // r13
  __int64 v12; // rdx
  char v13; // cl
  char v14; // al
  size_t v15; // r8
  const char *v16; // rdx
  DWORD v17; // eax
  DWORD v18; // r14d
  wchar_t DstCh[2]; // [rsp+40h] [rbp-40h] BYREF
  __int16 Buffer; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-38h] BYREF
  UINT CodePage; // [rsp+4Ch] [rbp-34h]
  HANDLE hFile; // [rsp+50h] [rbp-30h]
  const char *v25; // [rsp+58h] [rbp-28h]
  _BYTE v26[8]; // [rsp+60h] [rbp-20h] BYREF
  CHAR MultiByteStr[8]; // [rsp+68h] [rbp-18h] BYREF

  v4 = (__int64)a2 >> 6;
  v5 = (unsigned __int64)(a2 & 0x3F) << 6;
  v25 = a3;
  v8 = (unsigned __int64)&a3[a4];
  hFile = *(HANDLE *)(_pioinfo[v4] + v5 + 40);
  CodePage = GetConsoleCP();
  *(_QWORD *)a1 = 0;
  v9 = a3;
  *(_DWORD *)(a1 + 8) = 0;
  for ( i = (unsigned __int64)a3 < v8; i; i = (unsigned __int64)v9 < v8 )
  {
    v11 = *v9;
    DstCh[0] = 0;
    v12 = _pioinfo[v4];
    v13 = *(_BYTE *)(v12 + v5 + 61);
    if ( (v13 & 4) != 0 )
    {
      v14 = *(_BYTE *)(v12 + v5 + 62);
      *(_BYTE *)(v12 + v5 + 61) = v13 & 0xFB;
      v15 = 2;
      v16 = v26;
      v26[0] = v14;
      v26[1] = v11;
      goto LABEL_10;
    }
    if ( (_pctype_func()[*(unsigned __int8 *)v9] & 0x8000u) == 0 )
    {
      v15 = 1;
      v16 = v9;
LABEL_10:
      if ( mbtowc(DstCh, v16, v15) == -1 )
        return a1;
      goto LABEL_11;
    }
    if ( (unsigned __int64)v9 >= v8 )
    {
      *(_BYTE *)(_pioinfo[v4] + v5 + 62) = *v9;
      *(_BYTE *)(_pioinfo[v4] + v5 + 61) |= 4u;
      ++*(_DWORD *)(a1 + 4);
      return a1;
    }
    if ( mbtowc(DstCh, v9, 2u) == -1 )
      return a1;
    ++v9;
LABEL_11:
    ++v9;
    v17 = WideCharToMultiByte(CodePage, 0, DstCh, 1, MultiByteStr, 5, 0, 0);
    v18 = v17;
    if ( !v17 )
      return a1;
    if ( !WriteFile(hFile, MultiByteStr, v17, &NumberOfBytesWritten, 0) )
    {
LABEL_20:
      *(_DWORD *)a1 = GetLastError();
      return a1;
    }
    *(_DWORD *)(a1 + 4) = (_DWORD)v9 + *(_DWORD *)(a1 + 8) - (_DWORD)v25;
    if ( NumberOfBytesWritten < v18 )
      return a1;
    if ( v11 == 10 )
    {
      Buffer = 13;
      if ( !WriteFile(hFile, &Buffer, 1u, &NumberOfBytesWritten, 0) )
        goto LABEL_20;
      if ( !NumberOfBytesWritten )
        return a1;
      ++*(_DWORD *)(a1 + 8);
      ++*(_DWORD *)(a1 + 4);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18033c384  mov     [rsp-38h+arg_0], rbx
0x18033c389  push    rbp
0x18033c38a  push    rsi
0x18033c38b  push    rdi
0x18033c38c  push    r12
0x18033c38e  push    r13
0x18033c390  push    r14
0x18033c392  push    r15
0x18033c394  mov     rbp, rsp
0x18033c397  sub     rsp, 80h
0x18033c39e  mov     rax, cs:__security_cookie
0x18033c3a5  xor     rax, rsp
0x18033c3a8  mov     [rbp+var_10], rax
0x18033c3ac  movsxd  rsi, edx
0x18033c3af  lea     rax, __pioinfo
0x18033c3b6  mov     r15, rsi
0x18033c3b9  mov     r12d, r9d
0x18033c3bc  sar     r15, 6
0x18033c3c0  and     esi, 3Fh
0x18033c3c3  shl     rsi, 6
0x18033c3c7  mov     r14, r8
0x18033c3ca  mov     [rbp+var_28], r8
0x18033c3ce  mov     rbx, rcx
0x18033c3d1  add     r12, r8
0x18033c3d4  mov     rax, [rax+r15*8]
0x18033c3d8  mov     rax, [rax+rsi+28h]
0x18033c3dd  mov     [rbp+hFile], rax
0x18033c3e1  call    cs:__imp_GetConsoleCP
0x18033c3e7  xor     edx, edx
0x18033c3e9  mov     [rbp+CodePage], eax
0x18033c3ec  mov     [rbx], rdx
0x18033c3ef  mov     rdi, r14
0x18033c3f2  mov     [rbx+8], edx
0x18033c3f5  cmp     r14, r12
0x18033c3f8  jnb     loc_18033C562
0x18033c3fe  mov     r13b, [rdi]
0x18033c401  lea     r14, __pioinfo
0x18033c408  mov     [rbp+DstCh], dx
0x18033c40c  mov     rdx, [r14+r15*8]
0x18033c410  mov     cl, [rdx+rsi+3Dh]
0x18033c414  test    cl, 4
0x18033c417  jz      short loc_18033C437
0x18033c419  mov     al, [rdx+rsi+3Eh]
0x18033c41d  and     cl, 0FBh
0x18033c420  mov     [rdx+rsi+3Dh], cl
0x18033c424  mov     r8d, 2
0x18033c42a  lea     rdx, [rbp+var_20]
0x18033c42e  mov     [rbp+var_20], al
0x18033c431  mov     [rbp+var_1F], r13b
0x18033c435  jmp     short loc_18033C47C
0x18033c437  call    __pctype_func
0x18033c43c  movzx   ecx, byte ptr [rdi]
0x18033c43f  mov     edx, 8000h
0x18033c444  test    [rax+rcx*2], dx
0x18033c448  jz      short loc_18033C473
0x18033c44a  cmp     rdi, r12
0x18033c44d  jnb     loc_18033C542
0x18033c453  mov     r8d, 2; SrcSizeInBytes
0x18033c459  lea     rcx, [rbp+DstCh]; DstCh
0x18033c45d  mov     rdx, rdi; SrcCh
0x18033c460  call    mbtowc
0x18033c465  cmp     eax, 0FFFFFFFFh
0x18033c468  jz      loc_18033C562
0x18033c46e  inc     rdi
0x18033c471  jmp     short loc_18033C48E
0x18033c473  mov     r8d, 1; SrcSizeInBytes
0x18033c479  mov     rdx, rdi; SrcCh
0x18033c47c  lea     rcx, [rbp+DstCh]; DstCh
0x18033c480  call    mbtowc
0x18033c485  cmp     eax, 0FFFFFFFFh
0x18033c488  jz      loc_18033C562
0x18033c48e  and     [rsp+80h+var_48], 0
0x18033c494  lea     rax, [rbp+MultiByteStr]
0x18033c498  and     [rsp+80h+var_50], 0
0x18033c49e  lea     r8, [rbp+DstCh]; lpWideCharStr
0x18033c4a2  mov     ecx, [rbp+CodePage]; CodePage
0x18033c4a5  mov     r9d, 1; cchWideChar
0x18033c4ab  mov     [rsp+80h+cbMultiByte], 5; cbMultiByte
0x18033c4b3  xor     edx, edx; dwFlags
0x18033c4b5  mov     [rsp+80h+lpMultiByteStr], rax; lpOverlapped
0x18033c4ba  inc     rdi
0x18033c4bd  call    cs:__imp_WideCharToMultiByte
0x18033c4c3  mov     r14d, eax
0x18033c4c6  test    eax, eax
0x18033c4c8  jz      loc_18033C562
0x18033c4ce  mov     rcx, [rbp+hFile]; hFile
0x18033c4d2  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18033c4d6  and     [rsp+80h+lpMultiByteStr], 0
0x18033c4dc  lea     rdx, [rbp+MultiByteStr]; lpBuffer
0x18033c4e0  mov     r8d, eax; nNumberOfBytesToWrite
0x18033c4e3  call    cs:__imp_WriteFile
0x18033c4e9  xor     edx, edx
0x18033c4eb  test    eax, eax
0x18033c4ed  jz      short loc_18033C55A
0x18033c4ef  mov     ecx, [rbx+8]
0x18033c4f2  sub     ecx, dword ptr [rbp+var_28]
0x18033c4f5  add     ecx, edi
0x18033c4f7  mov     [rbx+4], ecx
0x18033c4fa  cmp     [rbp+NumberOfBytesWritten], r14d
0x18033c4fe  jb      short loc_18033C562
0x18033c500  cmp     r13b, 0Ah
0x18033c504  jnz     short loc_18033C53A
0x18033c506  mov     rcx, [rbp+hFile]; hFile
0x18033c50a  lea     eax, [rdx+0Dh]
0x18033c50d  mov     [rsp+80h+lpMultiByteStr], rdx; lpOverlapped
0x18033c512  lea     r8d, [rdx+1]; nNumberOfBytesToWrite
0x18033c516  lea     rdx, [rbp+Buffer]; lpBuffer
0x18033c51a  mov     [rbp+Buffer], ax
0x18033c51e  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18033c522  call    cs:__imp_WriteFile
0x18033c528  xor     edx, edx
0x18033c52a  test    eax, eax
0x18033c52c  jz      short loc_18033C55A
0x18033c52e  cmp     [rbp+NumberOfBytesWritten], 1
0x18033c532  jb      short loc_18033C562
0x18033c534  inc     dword ptr [rbx+8]
0x18033c537  inc     dword ptr [rbx+4]
0x18033c53a  cmp     rdi, r12
0x18033c53d  jmp     loc_18033C3F8
0x18033c542  mov     al, [rdi]
0x18033c544  mov     rcx, [r14+r15*8]
0x18033c548  mov     [rcx+rsi+3Eh], al
0x18033c54c  mov     rax, [r14+r15*8]
0x18033c550  or      byte ptr [rax+rsi+3Dh], 4
0x18033c555  inc     dword ptr [rbx+4]
0x18033c558  jmp     short loc_18033C562
0x18033c55a  call    cs:__imp_GetLastError
0x18033c560  mov     [rbx], eax
0x18033c562  mov     rax, rbx
0x18033c565  mov     rcx, [rbp+var_10]
0x18033c569  xor     rcx, rsp; StackCookie
0x18033c56c  call    __security_check_cookie
0x18033c571  mov     rbx, [rsp+80h+arg_0]
0x18033c579  add     rsp, 80h
0x18033c580  pop     r15
0x18033c582  pop     r14
0x18033c584  pop     r13
0x18033c586  pop     r12
0x18033c588  pop     rdi
0x18033c589  pop     rsi
0x18033c58a  pop     rbp
0x18033c58b  retn
```
