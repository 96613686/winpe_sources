# Appx::Packaging::FileSystemHelper::CreateDirectoryTree(ushort *,bool)

- ea: `0x180097f6c`
- end: `0x180098145`
- name: `?CreateDirectoryTree@FileSystemHelper@Packaging@Appx@@SAJPEAG_N@Z`
- size: `473`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c3d08`

## callees

- `0x1800059f0`
- `0x1800133fc`
- `0x180097f6c`
- `0x1800992c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009806e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009806e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098109`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009805e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800980f0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009805e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800980f0`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::FileSystemHelper::CreateDirectoryTree(unsigned __int16 *a1)
{
  __int64 v1; // rdx
  unsigned int v2; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  int v6; // eax
  unsigned __int64 v7; // rdx
  unsigned int v8; // edi
  unsigned __int64 v9; // rdx
  const WCHAR *v10; // rsi
  WCHAR *v11; // rdi
  char v12; // bp
  signed int LastError; // eax
  __int16 i; // ax
  signed int v15; // eax
  LPCWSTR lpPathName[2]; // [rsp+20h] [rbp-58h] BYREF
  int v17; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a1 )
  {
    v1 = 25;
    goto LABEL_3;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  if ( a1[v5 - 1] == 92 )
  {
    v1 = 26;
LABEL_3:
    v2 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v1,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filesystemhelper.cpp",
      (const char *)0x80070057LL,
      (int)lpPathName[0]);
    return v2;
  }
  v17 = 0;
  *(_OWORD *)lpPathName = 0;
  v6 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)lpPathName, a1);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v10 = lpPathName[1];
    do
      ++v4;
    while ( lpPathName[1][v4] );
    v11 = (WCHAR *)&lpPathName[1][v4];
    v12 = 0;
    while ( !v12 && v11 > v10 )
    {
      if ( *--v11 == 92 )
      {
        if ( *(v11 - 1) == 58 )
          break;
        *v11 = 0;
        if ( CreateDirectoryW(v10, 0) || (LastError = GetLastError(), v2 = LastError, LastError == 183) )
        {
          v12 = 1;
        }
        else if ( LastError != 3 )
        {
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
          if ( (v2 & 0x80000000) != 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x50,
              (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filesystemhelper.cpp",
              (const char *)v2,
              (int)lpPathName[0]);
LABEL_29:
          if ( lpPathName[1] )
            operator delete((void *)lpPathName[1], v7);
          return v2;
        }
        *v11 = 92;
      }
    }
LABEL_31:
    for ( i = *v11; i; i = 92 )
    {
      if ( *++v11 != 92 )
        goto LABEL_31;
      *v11 = 0;
      if ( !CreateDirectoryW(v10, 0) )
      {
        v15 = GetLastError();
        v2 = v15;
        if ( v15 > 0 )
          v2 = (unsigned __int16)v15 | 0x80070000;
        goto LABEL_29;
      }
      *v11 = 92;
    }
    if ( lpPathName[1] )
      operator delete((void *)lpPathName[1], v7);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filesystemhelper.cpp",
      (const char *)(unsigned int)v6,
      (int)lpPathName[0]);
    if ( lpPathName[1] )
      operator delete((void *)lpPathName[1], v9);
    return v8;
  }
}

```

## disassembly

```asm
0x180097f6c  push    rbx
0x180097f6e  push    rbp
0x180097f6f  push    rsi
0x180097f70  push    rdi
0x180097f71  push    r14
0x180097f73  push    r15
0x180097f75  sub     rsp, 48h
0x180097f79  xor     r14d, r14d
0x180097f7c  test    rcx, rcx
0x180097f7f  jnz     short loc_180097FA4
0x180097f81  lea     edx, [rcx+19h]; void *
0x180097f84  mov     rcx, [rsp+78h]; this
0x180097f89  lea     r8, aOnecorePrintsc_71; "onecore\\printscan\\appxpackaging\\lib"...
0x180097f90  mov     ebx, 80070057h
0x180097f95  mov     r9d, ebx; char *
0x180097f98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097f9d  mov     eax, ebx
0x180097f9f  jmp     loc_180098137
0x180097fa4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180097fa8  mov     rax, rbx
0x180097fab  inc     rax
0x180097fae  cmp     [rcx+rax*2], r14w
0x180097fb3  jnz     short loc_180097FAB
0x180097fb5  mov     r15d, 5Ch ; '\'
0x180097fbb  cmp     [rcx+rax*2-2], r15w
0x180097fc1  jnz     short loc_180097FC9
0x180097fc3  lea     edx, [r15-42h]
0x180097fc7  jmp     short loc_180097F84
0x180097fc9  xorps   xmm0, xmm0
0x180097fcc  mov     [rsp+78h+var_48], r14d
0x180097fd1  mov     rdx, rcx; unsigned __int16 *
0x180097fd4  lea     rcx, [rsp+78h+lpPathName]; this
0x180097fd9  movups  xmmword ptr [rsp+78h+lpPathName], xmm0; int
0x180097fde  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180097fe3  mov     edi, eax
0x180097fe5  test    eax, eax
0x180097fe7  jns     short loc_180098018
0x180097fe9  mov     rcx, [rsp+78h]; this
0x180097fee  lea     r8, aOnecorePrintsc_71; "onecore\\printscan\\appxpackaging\\lib"...
0x180097ff5  mov     r9d, eax; char *
0x180097ff8  mov     edx, 26h ; '&'; void *
0x180097ffd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098002  mov     rcx, [rsp+78h+lpPathName+8]; void *
0x180098007  test    rcx, rcx
0x18009800a  jz      short loc_180098011
0x18009800c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180098011  mov     eax, edi
0x180098013  jmp     loc_180098137
0x180098018  mov     rsi, [rsp+78h+lpPathName+8]
0x18009801d  inc     rbx
0x180098020  cmp     [rsi+rbx*2], r14w
0x180098025  jnz     short loc_18009801D
0x180098027  lea     rdi, [rsi+rbx*2]
0x18009802b  mov     bpl, r14b
0x18009802e  test    bpl, bpl
0x180098031  jnz     loc_1800980D5
0x180098037  cmp     rdi, rsi
0x18009803a  jbe     loc_1800980D5
0x180098040  sub     rdi, 2
0x180098044  cmp     [rdi], r15w
0x180098048  jnz     short loc_18009802E
0x18009804a  cmp     word ptr [rdi-2], 3Ah ; ':'
0x18009804f  jz      loc_1800980D5
0x180098055  xor     edx, edx; lpSecurityAttributes
0x180098057  mov     [rdi], r14w
0x18009805b  mov     rcx, rsi; lpPathName
0x18009805e  call    cs:__imp_CreateDirectoryW
0x180098065  nop     dword ptr [rax+rax+00h]
0x18009806a  test    eax, eax
0x18009806c  jnz     short loc_180098083
0x18009806e  call    cs:__imp_GetLastError
0x180098075  nop     dword ptr [rax+rax+00h]
0x18009807a  mov     ebx, eax
0x18009807c  cmp     eax, 0B7h
0x180098081  jnz     short loc_180098088
0x180098083  mov     bpl, 1
0x180098086  jmp     short loc_18009808D
0x180098088  cmp     eax, 3
0x18009808b  jnz     short loc_180098093
0x18009808d  mov     [rdi], r15w
0x180098091  jmp     short loc_18009802E
0x180098093  test    eax, eax
0x180098095  jle     short loc_1800980A0
0x180098097  movzx   ebx, ax
0x18009809a  or      ebx, 80070000h
0x1800980a0  test    ebx, ebx
0x1800980a2  jns     short loc_1800980BD
0x1800980a4  mov     rcx, [rsp+78h]; this
0x1800980a9  lea     r8, aOnecorePrintsc_71; "onecore\\printscan\\appxpackaging\\lib"...
0x1800980b0  mov     r9d, ebx; char *
0x1800980b3  mov     edx, 50h ; 'P'; void *
0x1800980b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800980bd  mov     rcx, [rsp+78h+lpPathName+8]; void *
0x1800980c2  test    rcx, rcx
0x1800980c5  jz      loc_180097F9D
0x1800980cb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800980d0  jmp     loc_180097F9D
0x1800980d5  movzx   eax, word ptr [rdi]
0x1800980d8  test    ax, ax
0x1800980db  jz      short loc_180098126
0x1800980dd  add     rdi, 2
0x1800980e1  cmp     [rdi], r15w
0x1800980e5  jnz     short loc_1800980D5
0x1800980e7  xor     edx, edx; lpSecurityAttributes
0x1800980e9  mov     [rdi], r14w
0x1800980ed  mov     rcx, rsi; lpPathName
0x1800980f0  call    cs:__imp_CreateDirectoryW
0x1800980f7  nop     dword ptr [rax+rax+00h]
0x1800980fc  test    eax, eax
0x1800980fe  jz      short loc_180098109
0x180098100  mov     [rdi], r15w
0x180098104  mov     eax, r15d
0x180098107  jmp     short loc_1800980D8
0x180098109  call    cs:__imp_GetLastError
0x180098110  nop     dword ptr [rax+rax+00h]
0x180098115  mov     ebx, eax
0x180098117  test    eax, eax
0x180098119  jle     short loc_1800980BD
0x18009811b  movzx   ebx, ax
0x18009811e  or      ebx, 80070000h
0x180098124  jmp     short loc_1800980BD
0x180098126  mov     rcx, [rsp+78h+lpPathName+8]; void *
0x18009812b  test    rcx, rcx
0x18009812e  jz      short loc_180098135
0x180098130  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180098135  xor     eax, eax
0x180098137  add     rsp, 48h
0x18009813b  pop     r15
0x18009813d  pop     r14
0x18009813f  pop     rdi
0x180098140  pop     rsi
0x180098141  pop     rbp
0x180098142  pop     rbx
0x180098143  retn
```
