# CLogFile::WriteLog(LOGFILETYPE,char const *)

- ea: `0x1800048d0`
- end: `0x180004b2c`
- name: `?WriteLog@CLogFile@@UEAAJW4LOGFILETYPE@@PEBD@Z`
- size: `604`
- prototype: `int __high(enum LOGFILETYPE, const char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180001900`
- `0x1800046b4`
- `0x1800048d0`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180004932`
- `KERNEL32!WaitForSingleObject` at `0x180004932`
- `KERNEL32!SetFilePointer` at `0x1800049b1`
- `KERNEL32!SetFilePointer` at `0x1800049b1`
- `KERNEL32!GetLocalTime` at `0x18000494a`
- `KERNEL32!GetLocalTime` at `0x18000494a`
- `KERNEL32!WriteFile` at `0x1800049e7`
- `KERNEL32!WriteFile` at `0x180004a97`
- `KERNEL32!WriteFile` at `0x180004ad7`
- `KERNEL32!WriteFile` at `0x1800049e7`
- `KERNEL32!WriteFile` at `0x180004a97`
- `KERNEL32!WriteFile` at `0x180004ad7`
- `KERNEL32!ReleaseMutex` at `0x180004ae1`
- `KERNEL32!ReleaseMutex` at `0x180004ae1`
- `KERNEL32!EnterCriticalSection` at `0x180004925`
- `KERNEL32!EnterCriticalSection` at `0x180004925`
- `KERNEL32!LeaveCriticalSection` at `0x180004aeb`
- `KERNEL32!LeaveCriticalSection` at `0x180004aeb`
- `SHLWAPI!StrCmpNIA` at `0x180004a0f`
- `SHLWAPI!StrCmpNIA` at `0x180004a0f`

## pseudocode

```c
__int64 __fastcall CLogFile::WriteLog(__int64 a1, int a2, char *a3)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  __int64 v8; // r15
  unsigned int v9; // ebx
  __int64 v10; // r8
  const CHAR **i; // rbx
  const CHAR *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // rax
  char v17; // cl
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-40h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-38h] BYREF
  char Buffer[32]; // [rsp+58h] [rbp-28h] BYREF

  v3 = -1;
  v4 = a2;
  NumberOfBytesWritten = 0;
  SystemTime = 0;
  if ( *(_QWORD *)(a1 + 16) == -1 )
    return 2147549183LL;
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  if ( WaitForSingleObject(*(HANDLE *)(a1 + 40), 0xFFFFFFFF) )
  {
    v9 = -2147467259;
  }
  else
  {
    GetLocalTime(&SystemTime);
    if ( (unsigned int)v4 < 3 )
    {
      StringCchPrintfA(
        Buffer,
        0x1Eu,
        "%s: %.2d:%.2d:%.2d [%s] ",
        (const char *)(a1 + 24),
        SystemTime.wHour,
        SystemTime.wMinute,
        SystemTime.wSecond,
        off_180015390[v4]);
      if ( SetFilePointer(*(HANDLE *)(a1 + 16), 0, 0, 2u) == -1 )
        goto LABEL_8;
      v10 = -1;
      do
        ++v10;
      while ( Buffer[v10] );
      if ( !WriteFile(*(HANDLE *)(a1 + 16), Buffer, v10, &NumberOfBytesWritten, 0) )
        goto LABEL_8;
      for ( i = (const CHAR **)off_18001C020; ; ++i )
      {
        v12 = *i;
        if ( !*i )
          break;
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        if ( !StrCmpNIA(a3, v12, v13) )
        {
          v14 = PszDupA(a3);
          v8 = v14;
          if ( !v14 )
          {
            v9 = -2147024882;
            goto LABEL_37;
          }
          a3 = (char *)v14;
          if ( *i )
          {
            v15 = -1;
            do
              ++v15;
            while ( (*i)[v15] );
          }
          else
          {
            v15 = 0;
          }
          v16 = (char *)(v8 + v15);
          v17 = *v16;
          if ( *v16 )
          {
            while ( v17 != 13 )
            {
              *v16++ = 42;
              v17 = *v16;
              if ( !*v16 )
                goto LABEL_28;
            }
          }
          goto LABEL_29;
        }
      }
LABEL_28:
      if ( !a3 )
      {
        LODWORD(v3) = 0;
        goto LABEL_32;
      }
      do
LABEL_29:
        ++v3;
      while ( a3[v3] );
LABEL_32:
      if ( WriteFile(*(HANDLE *)(a1 + 16), a3, v3, &NumberOfBytesWritten, 0) )
      {
        v9 = 0;
        if ( (int)v3 < 2 || a3[(int)v3 - 1] != 10 || a3[(int)v3 - 2] != 13 )
          WriteFile(*(HANDLE *)(a1 + 16), "\r\n", 2u, &NumberOfBytesWritten, 0);
      }
      else
      {
LABEL_8:
        v9 = -2147467259;
      }
    }
    else
    {
      v9 = -2147418113;
    }
LABEL_37:
    ReleaseMutex(*(HANDLE *)(a1 + 40));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  if ( v8 )
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v8);
  return v9;
}

```

## disassembly

```asm
0x1800048d0  push    rbp
0x1800048d2  push    rbx
0x1800048d3  push    rsi
0x1800048d4  push    rdi
0x1800048d5  push    r12
0x1800048d7  push    r14
0x1800048d9  push    r15
0x1800048db  mov     rbp, rsp
0x1800048de  sub     rsp, 80h
0x1800048e5  mov     rax, cs:__security_cookie
0x1800048ec  xor     rax, rsp
0x1800048ef  mov     [rbp+var_8], rax
0x1800048f3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800048f7  movsxd  rbx, edx
0x1800048fa  xorps   xmm0, xmm0
0x1800048fd  mov     rsi, r8
0x180004900  mov     r14, rcx
0x180004903  mov     [rbp+NumberOfBytesWritten], 0
0x18000490a  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000490e  cmp     [rcx+10h], rdi
0x180004912  jnz     short loc_18000491E
0x180004914  mov     eax, 8000FFFFh
0x180004919  jmp     loc_180004B0E
0x18000491e  add     rcx, 30h ; '0'; lpCriticalSection
0x180004922  xor     r15d, r15d
0x180004925  call    cs:__imp_EnterCriticalSection
0x18000492b  mov     rcx, [r14+28h]; hHandle
0x18000492f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004932  call    cs:__imp_WaitForSingleObject
0x180004938  test    eax, eax
0x18000493a  jz      short loc_180004946
0x18000493c  mov     ebx, 80004005h
0x180004941  jmp     loc_180004AE7
0x180004946  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000494a  call    cs:__imp_GetLocalTime
0x180004950  cmp     ebx, 3
0x180004953  jb      short loc_18000495F
0x180004955  mov     ebx, 8000FFFFh
0x18000495a  jmp     loc_180004ADD
0x18000495f  movzx   ecx, [rbp+SystemTime.wSecond]
0x180004963  lea     r10, off_180015390; "rx"
0x18000496a  movzx   edx, [rbp+SystemTime.wMinute]
0x18000496e  lea     r9, [r14+18h]
0x180004972  movzx   r8d, [rbp+SystemTime.wHour]
0x180004977  mov     rax, [r10+rbx*8]
0x18000497b  mov     [rsp+80h+var_48], rax
0x180004980  mov     [rsp+80h+var_50], ecx
0x180004984  lea     rcx, [rbp+Buffer]; char *
0x180004988  mov     [rsp+80h+var_58], edx
0x18000498c  mov     edx, 1Eh; unsigned __int64
0x180004991  mov     dword ptr [rsp+80h+lpOverlapped], r8d
0x180004996  lea     r8, aS2d2d2dS; "%s: %.2d:%.2d:%.2d [%s] "
0x18000499d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800049a2  mov     rcx, [r14+10h]; hFile
0x1800049a6  mov     r9d, 2; dwMoveMethod
0x1800049ac  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800049af  xor     edx, edx; lDistanceToMove
0x1800049b1  call    cs:__imp_SetFilePointer
0x1800049b7  cmp     eax, 0FFFFFFFFh
0x1800049ba  jnz     short loc_1800049C6
0x1800049bc  mov     ebx, 80004005h
0x1800049c1  jmp     loc_180004ADD
0x1800049c6  lea     rax, [rbp+Buffer]
0x1800049ca  mov     r8, rdi
0x1800049cd  inc     r8; nNumberOfBytesToWrite
0x1800049d0  cmp     [rax+r8], r15b
0x1800049d4  jnz     short loc_1800049CD
0x1800049d6  mov     rcx, [r14+10h]; hFile
0x1800049da  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800049de  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800049e2  mov     [rsp+80h+lpOverlapped], r15; lpOverlapped
0x1800049e7  call    cs:__imp_WriteFile
0x1800049ed  test    eax, eax
0x1800049ef  jz      short loc_1800049BC
0x1800049f1  lea     rbx, off_18001C020; "AUTHINFO PASS "
0x1800049f8  mov     rdx, [rbx]; psz2
0x1800049fb  test    rdx, rdx
0x1800049fe  jz      short loc_180004A6E
0x180004a00  mov     r8, rdi
0x180004a03  inc     r8; nChar
0x180004a06  cmp     [rdx+r8], r15b
0x180004a0a  jnz     short loc_180004A03
0x180004a0c  mov     rcx, rsi; psz1
0x180004a0f  call    cs:__imp_StrCmpNIA
0x180004a15  test    eax, eax
0x180004a17  jz      short loc_180004A1F
0x180004a19  add     rbx, 8
0x180004a1d  jmp     short loc_1800049F8
0x180004a1f  mov     rcx, rsi; Src
0x180004a22  call    PszDupA
0x180004a27  mov     r15, rax
0x180004a2a  test    rax, rax
0x180004a2d  jnz     short loc_180004A39
0x180004a2f  mov     ebx, 8007000Eh
0x180004a34  jmp     loc_180004ADD
0x180004a39  mov     rcx, [rbx]
0x180004a3c  mov     rsi, r15
0x180004a3f  test    rcx, rcx
0x180004a42  jz      short loc_180004A52
0x180004a44  mov     rax, rdi
0x180004a47  inc     rax
0x180004a4a  cmp     byte ptr [rcx+rax], 0
0x180004a4e  jnz     short loc_180004A47
0x180004a50  jmp     short loc_180004A54
0x180004a52  xor     eax, eax
0x180004a54  add     rax, r15
0x180004a57  mov     cl, [rax]
0x180004a59  test    cl, cl
0x180004a5b  jz      short loc_180004A73
0x180004a5d  cmp     cl, 0Dh
0x180004a60  jz      short loc_180004A73
0x180004a62  mov     byte ptr [rax], 2Ah ; '*'
0x180004a65  inc     rax
0x180004a68  mov     cl, [rax]
0x180004a6a  test    cl, cl
0x180004a6c  jnz     short loc_180004A5D
0x180004a6e  test    rsi, rsi
0x180004a71  jz      short loc_180004A7E
0x180004a73  inc     rdi
0x180004a76  cmp     byte ptr [rsi+rdi], 0
0x180004a7a  jnz     short loc_180004A73
0x180004a7c  jmp     short loc_180004A80
0x180004a7e  xor     edi, edi
0x180004a80  mov     rcx, [r14+10h]; hFile
0x180004a84  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004a88  mov     r8d, edi; nNumberOfBytesToWrite
0x180004a8b  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x180004a94  mov     rdx, rsi; lpBuffer
0x180004a97  call    cs:__imp_WriteFile
0x180004a9d  test    eax, eax
0x180004a9f  jz      loc_1800049BC
0x180004aa5  xor     ebx, ebx
0x180004aa7  cmp     edi, 2
0x180004aaa  jl      short loc_180004ABD
0x180004aac  movsxd  rax, edi
0x180004aaf  cmp     byte ptr [rax+rsi-1], 0Ah
0x180004ab4  jnz     short loc_180004ABD
0x180004ab6  cmp     byte ptr [rax+rsi-2], 0Dh
0x180004abb  jz      short loc_180004ADD
0x180004abd  mov     rcx, [r14+10h]; hFile
0x180004ac1  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004ac5  mov     r8d, 2; nNumberOfBytesToWrite
0x180004acb  mov     [rsp+80h+lpOverlapped], rbx; lpOverlapped
0x180004ad0  lea     rdx, asc_180016954; "\r\n"
0x180004ad7  call    cs:__imp_WriteFile
0x180004add  mov     rcx, [r14+28h]; hMutex
0x180004ae1  call    cs:__imp_ReleaseMutex
0x180004ae7  lea     rcx, [r14+30h]; lpCriticalSection
0x180004aeb  call    cs:__imp_LeaveCriticalSection
0x180004af1  test    r15, r15
0x180004af4  jz      short loc_180004B0C
0x180004af6  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180004afd  mov     rdx, [rcx]
0x180004b00  mov     rax, [rdx+28h]
0x180004b04  mov     rdx, r15
0x180004b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b0c  mov     eax, ebx
0x180004b0e  mov     rcx, [rbp+var_8]
0x180004b12  xor     rcx, rsp; StackCookie
0x180004b15  call    __security_check_cookie
0x180004b1a  add     rsp, 80h
0x180004b21  pop     r15
0x180004b23  pop     r14
0x180004b25  pop     r12
0x180004b27  pop     rdi
0x180004b28  pop     rsi
0x180004b29  pop     rbx
0x180004b2a  pop     rbp
0x180004b2b  retn
```
