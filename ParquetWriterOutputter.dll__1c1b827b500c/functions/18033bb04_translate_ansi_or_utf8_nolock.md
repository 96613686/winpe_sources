# translate_ansi_or_utf8_nolock

- ea: `0x18033bb04`
- end: `0x18033be01`
- name: `translate_ansi_or_utf8_nolock`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18033bf1c`

## callees

- `0x180334700`
- `0x180334770`
- `0x18033bb04`
- `0x18033ce88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033bdb8`
- `KERNEL32!GetLastError` at `0x18033bdb8`
- `KERNEL32!ReadFile` at `0x18033bbdb`
- `KERNEL32!ReadFile` at `0x18033bbdb`
- `KERNEL32!MultiByteToWideChar` at `0x18033bdac`
- `KERNEL32!MultiByteToWideChar` at `0x18033bdac`

## pseudocode

```c
__int64 __fastcall translate_ansi_or_utf8_nolock(
        unsigned int a1,
        const CHAR *a2,
        __int64 a3,
        WCHAR *a4,
        int cchWideChar)
{
  WCHAR *lpWideCharStr; // rbp
  unsigned int v6; // r9d
  __int64 v8; // r15
  unsigned __int64 v9; // rdi
  __int64 v10; // rax
  void *v11; // r13
  const CHAR *v12; // r12
  const CHAR *v13; // rsi
  CHAR *v14; // rbx
  const CHAR *v15; // rbp
  CHAR v16; // al
  char v17; // cl
  __int64 v18; // rcx
  char v19; // al
  unsigned int v20; // ebx
  __int64 v22; // rcx
  char *v23; // rbx
  unsigned int i; // edx
  __int64 v25; // r8
  char v26; // al
  char v27; // al
  int v28; // ebx
  unsigned int v29; // eax
  DWORD LastError; // eax
  __int64 v31; // rcx
  char Buffer; // [rsp+88h] [rbp+10h] BYREF
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF
  WCHAR *v35; // [rsp+98h] [rbp+20h]

  v35 = a4;
  lpWideCharStr = a4;
  v6 = a1;
  v8 = (__int64)(int)a1 >> 6;
  v9 = (unsigned __int64)(a1 & 0x3F) << 6;
  v10 = _pioinfo[v8];
  v11 = *(void **)(v10 + v9 + 40);
  if ( a3 && *a2 == 10 )
    *(_BYTE *)(v10 + v9 + 56) |= 4u;
  else
    *(_BYTE *)(v10 + v9 + 56) &= ~4u;
  v12 = &a2[a3];
  v13 = a2;
  v14 = (CHAR *)a2;
  if ( a2 >= &a2[a3] )
    goto LABEL_33;
  v15 = a2 + 1;
  while ( 1 )
  {
    v16 = *v13;
    if ( *v13 == 26 )
      break;
    if ( v16 != 13 )
    {
      *v14 = v16;
LABEL_10:
      ++v14;
      ++v13;
      ++v15;
      goto LABEL_27;
    }
    if ( v15 < v12 )
    {
      if ( *v15 == 10 )
      {
        v13 += 2;
        v15 += 2;
LABEL_14:
        *v14 = 10;
LABEL_26:
        ++v14;
        goto LABEL_27;
      }
      *v14 = 13;
      goto LABEL_10;
    }
    ++v13;
    ++v15;
    if ( !ReadFile(v11, &Buffer, 1u, &NumberOfBytesRead, 0) || !NumberOfBytesRead )
    {
LABEL_25:
      *v14 = 13;
      goto LABEL_26;
    }
    if ( (*(_BYTE *)(_pioinfo[v8] + v9 + 56) & 0x48) != 0 )
    {
      v17 = Buffer;
      if ( Buffer == 10 )
      {
        *v14 = 10;
      }
      else
      {
        *v14 = 13;
        *(_BYTE *)(_pioinfo[v8] + v9 + 58) = v17;
      }
      goto LABEL_27;
    }
    if ( Buffer == 10 && v14 == a2 )
      goto LABEL_14;
    lseeki64_nolock(a1, -1, 1);
    if ( Buffer != 10 )
      goto LABEL_25;
LABEL_27:
    if ( v13 >= v12 )
      goto LABEL_32;
  }
  v18 = _pioinfo[v8];
  v19 = *(_BYTE *)(v18 + v9 + 56);
  if ( (v19 & 0x40) != 0 )
  {
    *v14 = *v13;
    LODWORD(v14) = (_DWORD)v14 + 1;
  }
  else
  {
    *(_BYTE *)(v18 + v9 + 56) = v19 | 2;
  }
LABEL_32:
  v6 = a1;
  lpWideCharStr = v35;
LABEL_33:
  v20 = (_DWORD)v14 - (_DWORD)a2;
  if ( !v20 )
    return 0;
  v22 = _pioinfo[v8];
  if ( !*(_BYTE *)(v22 + v9 + 57) )
    return v20;
  v23 = (char *)&a2[v20 - 1];
  if ( *v23 >= 0 )
  {
    LODWORD(v23) = (_DWORD)v23 + 1;
    goto LABEL_56;
  }
  for ( i = 1; !*((_BYTE *)lookuptrailbytes + (unsigned __int8)*v23) && i <= 4 && v23 >= a2; ++i )
    --v23;
  v25 = (unsigned __int8)*v23;
  if ( !*((_BYTE *)lookuptrailbytes + v25) )
  {
    *errno() = 42;
    return 0xFFFFFFFFLL;
  }
  if ( *((char *)lookuptrailbytes + v25) + 1 == i )
  {
    LODWORD(v23) = i + (_DWORD)v23;
  }
  else if ( (*(_BYTE *)(v22 + v9 + 56) & 0x48) != 0 )
  {
    ++v23;
    *(_BYTE *)(v22 + v9 + 58) = v25;
    if ( i >= 2 )
    {
      v26 = *v23++;
      *(_BYTE *)(_pioinfo[v8] + v9 + 59) = v26;
    }
    if ( i == 3 )
    {
      v27 = *v23;
      LODWORD(v23) = (_DWORD)v23 + 1;
      *(_BYTE *)(_pioinfo[v8] + v9 + 60) = v27;
    }
    LODWORD(v23) = (_DWORD)v23 - i;
  }
  else
  {
    lseeki64_nolock(v6, -i, 1);
  }
LABEL_56:
  v28 = (_DWORD)v23 - (_DWORD)a2;
  v29 = MultiByteToWideChar(0xFDE9u, 0, a2, v28, lpWideCharStr, cchWideChar);
  if ( v29 )
  {
    v31 = _pioinfo[v8];
    *(_BYTE *)(v31 + v9 + 61) &= ~2u;
    *(_BYTE *)(v31 + v9 + 61) |= 2 * (v29 != v28);
    return 2LL * v29;
  }
  else
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error(LastError);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x18033bb04  mov     [rsp+arg_18], r9
0x18033bb09  mov     [rsp+arg_0], ecx
0x18033bb0d  push    rbx
0x18033bb0e  push    rbp
0x18033bb0f  push    rsi
0x18033bb10  push    rdi
0x18033bb11  push    r12
0x18033bb13  push    r13
0x18033bb15  push    r14
0x18033bb17  push    r15
0x18033bb19  sub     rsp, 38h
0x18033bb1d  mov     rbp, r9
0x18033bb20  lea     r10, cs:180000000h
0x18033bb27  movsxd  r9, ecx
0x18033bb2a  mov     r14, rdx
0x18033bb2d  mov     rdi, r9
0x18033bb30  mov     r15, r9
0x18033bb33  sar     r15, 6
0x18033bb37  and     edi, 3Fh
0x18033bb3a  shl     rdi, 6
0x18033bb3e  mov     rax, rva __pioinfo[r10+r15*8]
0x18033bb46  mov     r13, [rax+rdi+28h]
0x18033bb4b  test    r8, r8
0x18033bb4e  jz      short loc_18033BB5C
0x18033bb50  cmp     byte ptr [rdx], 0Ah
0x18033bb53  jnz     short loc_18033BB5C
0x18033bb55  or      byte ptr [rax+rdi+38h], 4
0x18033bb5a  jmp     short loc_18033BB61
0x18033bb5c  and     byte ptr [rax+rdi+38h], 0FBh
0x18033bb61  lea     r12, [rdx+r8]
0x18033bb65  mov     rsi, rdx
0x18033bb68  mov     rbx, rdx
0x18033bb6b  cmp     rdx, r12
0x18033bb6e  jnb     loc_18033BCA9
0x18033bb74  lea     rbp, [rdx+1]
0x18033bb78  mov     al, [rsi]
0x18033bb7a  cmp     al, 1Ah
0x18033bb7c  jz      loc_18033BC7A
0x18033bb82  cmp     al, 0Dh
0x18033bb84  jz      short loc_18033BB96
0x18033bb86  mov     [rbx], al
0x18033bb88  inc     rbx
0x18033bb8b  inc     rsi
0x18033bb8e  inc     rbp
0x18033bb91  jmp     loc_18033BC6F
0x18033bb96  cmp     rbp, r12
0x18033bb99  jnb     short loc_18033BBB6
0x18033bb9b  cmp     byte ptr [rbp+0], 0Ah
0x18033bb9f  jnz     short loc_18033BBB1
0x18033bba1  add     rsi, 2
0x18033bba5  add     rbp, 2
0x18033bba9  mov     byte ptr [rbx], 0Ah
0x18033bbac  jmp     loc_18033BC6C
0x18033bbb1  mov     byte ptr [rbx], 0Dh
0x18033bbb4  jmp     short loc_18033BB88
0x18033bbb6  and     [rsp+78h+lpWideCharStr], 0
0x18033bbbc  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18033bbc4  mov     r8d, 1; nNumberOfBytesToRead
0x18033bbca  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x18033bbd2  mov     rcx, r13; hFile
0x18033bbd5  inc     rsi
0x18033bbd8  inc     rbp
0x18033bbdb  call    cs:__imp_ReadFile
0x18033bbe1  test    eax, eax
0x18033bbe3  jz      short loc_18033BC62
0x18033bbe5  cmp     [rsp+78h+NumberOfBytesRead], 0
0x18033bbed  jz      short loc_18033BC62
0x18033bbef  lea     r10, cs:180000000h
0x18033bbf6  mov     rax, rva __pioinfo[r10+r15*8]
0x18033bbfe  test    byte ptr [rax+rdi+38h], 48h
0x18033bc03  jz      short loc_18033BC26
0x18033bc05  mov     cl, [rsp+78h+Buffer]
0x18033bc0c  cmp     cl, 0Ah
0x18033bc0f  jnz     short loc_18033BC15
0x18033bc11  mov     [rbx], cl
0x18033bc13  jmp     short loc_18033BC6F
0x18033bc15  mov     byte ptr [rbx], 0Dh
0x18033bc18  mov     rax, rva __pioinfo[r10+r15*8]
0x18033bc20  mov     [rax+rdi+3Ah], cl
0x18033bc24  jmp     short loc_18033BC6F
0x18033bc26  cmp     [rsp+78h+Buffer], 0Ah
0x18033bc2e  jnz     short loc_18033BC39
0x18033bc30  cmp     rbx, r14
0x18033bc33  jz      loc_18033BBA9
0x18033bc39  mov     ecx, [rsp+78h+arg_0]
0x18033bc40  mov     r8d, 1
0x18033bc46  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18033bc4a  call    _lseeki64_nolock
0x18033bc4f  cmp     [rsp+78h+Buffer], 0Ah
0x18033bc57  lea     r10, cs:180000000h
0x18033bc5e  jz      short loc_18033BC6F
0x18033bc60  jmp     short loc_18033BC69
0x18033bc62  lea     r10, cs:180000000h
0x18033bc69  mov     byte ptr [rbx], 0Dh
0x18033bc6c  inc     rbx
0x18033bc6f  cmp     rsi, r12
0x18033bc72  jb      loc_18033BB78
0x18033bc78  jmp     short loc_18033BC99
0x18033bc7a  mov     rcx, rva __pioinfo[r10+r15*8]
0x18033bc82  mov     al, [rcx+rdi+38h]
0x18033bc86  test    al, 40h
0x18033bc88  jnz     short loc_18033BC92
0x18033bc8a  or      al, 2
0x18033bc8c  mov     [rcx+rdi+38h], al
0x18033bc90  jmp     short loc_18033BC99
0x18033bc92  mov     al, [rsi]
0x18033bc94  mov     [rbx], al
0x18033bc96  inc     rbx
0x18033bc99  mov     r9d, [rsp+78h+arg_0]
0x18033bca1  mov     rbp, [rsp+78h+arg_18]
0x18033bca9  sub     ebx, r14d
0x18033bcac  jnz     short loc_18033BCB5
0x18033bcae  xor     eax, eax
0x18033bcb0  jmp     loc_18033BDF0
0x18033bcb5  mov     rcx, rva __pioinfo[r10+r15*8]
0x18033bcbd  cmp     byte ptr [rcx+rdi+39h], 0
0x18033bcc2  jnz     short loc_18033BCCB
0x18033bcc4  mov     eax, ebx
0x18033bcc6  jmp     loc_18033BDF0
0x18033bccb  movsxd  rax, ebx
0x18033bcce  lea     rbx, [r14-1]
0x18033bcd2  add     rbx, rax
0x18033bcd5  test    byte ptr [rbx], 80h
0x18033bcd8  jnz     short loc_18033BCE2
0x18033bcda  inc     rbx
0x18033bcdd  jmp     loc_18033BD8C
0x18033bce2  mov     edx, 1
0x18033bce7  jmp     short loc_18033BCF8
0x18033bce9  cmp     edx, 4
0x18033bcec  ja      short loc_18033BD06
0x18033bcee  cmp     rbx, r14
0x18033bcf1  jb      short loc_18033BD06
0x18033bcf3  dec     rbx
0x18033bcf6  inc     edx
0x18033bcf8  movzx   eax, byte ptr [rbx]
0x18033bcfb  cmp     byte ptr [rax+r10+4A85D0h], 0
0x18033bd04  jz      short loc_18033BCE9
0x18033bd06  movzx   r8d, byte ptr [rbx]
0x18033bd0a  movsx   eax, byte ptr [r8+r10+4A85D0h]
0x18033bd13  test    eax, eax
0x18033bd15  jnz     short loc_18033BD2A
0x18033bd17  call    _errno
0x18033bd1c  mov     dword ptr [rax], 2Ah ; '*'
0x18033bd22  or      eax, 0FFFFFFFFh
0x18033bd25  jmp     loc_18033BDF0
0x18033bd2a  inc     eax
0x18033bd2c  cmp     eax, edx
0x18033bd2e  jnz     short loc_18033BD37
0x18033bd30  mov     eax, edx
0x18033bd32  add     rbx, rax
0x18033bd35  jmp     short loc_18033BD8C
0x18033bd37  test    byte ptr [rcx+rdi+38h], 48h
0x18033bd3c  jz      short loc_18033BD79
0x18033bd3e  inc     rbx
0x18033bd41  mov     [rcx+rdi+3Ah], r8b
0x18033bd46  cmp     edx, 2
0x18033bd49  jb      short loc_18033BD5C
0x18033bd4b  mov     al, [rbx]
0x18033bd4d  inc     rbx
0x18033bd50  mov     rcx, rva __pioinfo[r10+r15*8]
0x18033bd58  mov     [rcx+rdi+3Bh], al
0x18033bd5c  cmp     edx, 3
0x18033bd5f  jnz     short loc_18033BD72
0x18033bd61  mov     al, [rbx]
0x18033bd63  inc     rbx
0x18033bd66  mov     rcx, rva __pioinfo[r10+r15*8]
0x18033bd6e  mov     [rcx+rdi+3Ch], al
0x18033bd72  mov     eax, edx
0x18033bd74  sub     rbx, rax
0x18033bd77  jmp     short loc_18033BD8C
0x18033bd79  neg     edx
0x18033bd7b  mov     r8d, 1
0x18033bd81  movsxd  rdx, edx
0x18033bd84  mov     ecx, r9d
0x18033bd87  call    _lseeki64_nolock
0x18033bd8c  mov     eax, [rsp+78h+arg_20]
0x18033bd93  sub     ebx, r14d
0x18033bd96  mov     [rsp+78h+cchWideChar], eax; cchWideChar
0x18033bd9a  mov     r9d, ebx; cbMultiByte
0x18033bd9d  mov     r8, r14; lpMultiByteStr
0x18033bda0  mov     [rsp+78h+lpWideCharStr], rbp; lpWideCharStr
0x18033bda5  xor     edx, edx; dwFlags
0x18033bda7  mov     ecx, 0FDE9h; CodePage
0x18033bdac  call    cs:__imp_MultiByteToWideChar
0x18033bdb2  mov     edx, eax
0x18033bdb4  test    eax, eax
0x18033bdb6  jnz     short loc_18033BDCA
0x18033bdb8  call    cs:__imp_GetLastError
0x18033bdbe  mov     ecx, eax
0x18033bdc0  call    __acrt_errno_map_os_error
0x18033bdc5  jmp     loc_18033BD22
0x18033bdca  lea     rcx, cs:180000000h
0x18033bdd1  mov     rcx, rva __pioinfo[rcx+r15*8]
0x18033bdd9  and     byte ptr [rcx+rdi+3Dh], 0FDh
0x18033bdde  cmp     eax, ebx
0x18033bde0  setnz   al
0x18033bde3  and     al, 1
0x18033bde5  add     al, al
0x18033bde7  or      [rcx+rdi+3Dh], al
0x18033bdeb  mov     eax, edx
0x18033bded  add     rax, rax
0x18033bdf0  add     rsp, 38h
0x18033bdf4  pop     r15
0x18033bdf6  pop     r14
0x18033bdf8  pop     r13
0x18033bdfa  pop     r12
0x18033bdfc  pop     rdi
0x18033bdfd  pop     rsi
0x18033bdfe  pop     rbp
0x18033bdff  pop     rbx
0x18033be00  retn
```
