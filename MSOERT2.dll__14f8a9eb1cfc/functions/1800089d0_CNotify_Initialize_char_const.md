# CNotify::Initialize(char const *)

- ea: `0x1800089d0`
- end: `0x180008bc4`
- name: `?Initialize@CNotify@@UEAAJPEBD@Z`
- size: `500`
- prototype: `int(CNotify *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800018d0`
- `0x180003614`
- `0x1800046b4`
- `0x1800089d0`
- `0x180010270`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180008a9a`
- `KERNEL32!WaitForSingleObject` at `0x180008a9a`
- `KERNEL32!ReleaseMutex` at `0x180008b7a`
- `KERNEL32!ReleaseMutex` at `0x180008b7a`
- `KERNEL32!CreateMutexA` at `0x180008a79`
- `KERNEL32!CreateMutexA` at `0x180008a79`
- `KERNEL32!CreateFileMappingA` at `0x180008b3c`
- `KERNEL32!CreateFileMappingA` at `0x180008b3c`
- `KERNEL32!MapViewOfFile` at `0x180008b5d`
- `KERNEL32!MapViewOfFile` at `0x180008b5d`

## pseudocode

```c
__int64 __fastcall CNotify::Initialize(CNotify *this, const char *a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // rdx
  int v7; // r14d
  __int64 v8; // rax
  unsigned int v9; // ebx
  char *lpName; // rdi
  unsigned int v11; // ebx
  HANDLE MutexA; // rax
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // rdx
  HANDLE FileMappingA; // rax
  LPVOID v18; // rax
  char v20[272]; // [rsp+30h] [rbp-148h] BYREF

  v4 = StringCchCopyA(v20, 0x104u, a2);
  LOBYTE(v5) = 95;
  LOBYTE(v6) = 92;
  v7 = v4;
  ReplaceChars(v20, v6, v5);
  v8 = -1;
  do
    ++v8;
  while ( v20[v8] );
  v9 = v8 + 13;
  lpName = (char *)PszAllocA((int)v8 + 13);
  if ( !lpName )
    return (unsigned int)-2147024882;
  StringCchPrintfA(lpName, v9, "Local\\%s%s", v20, "mutex");
  MutexA = CreateMutexA(0, 0, lpName);
  *((_QWORD *)this + 2) = MutexA;
  if ( !MutexA )
  {
    v11 = -2147024882;
LABEL_21:
    ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, lpName);
    return v11;
  }
  if ( WaitForSingleObject(MutexA, 0x2710u) )
  {
    v11 = -2147467259;
    goto LABEL_21;
  }
  ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, lpName);
  if ( a2 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
  }
  else
  {
    LODWORD(v13) = 0;
  }
  v14 = v13 + 11;
  lpName = (char *)PszAllocA((int)v13 + 11);
  if ( lpName
    && (StringCchPrintfA(lpName, v14, "%s%s", a2, "mappedfile"),
        LOBYTE(v15) = 95,
        LOBYTE(v16) = 92,
        ReplaceChars(lpName, v16, v15),
        FileMappingA = CreateFileMappingA((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0xC08u, lpName),
        (*((_QWORD *)this + 3) = FileMappingA) != 0) )
  {
    v18 = MapViewOfFile(FileMappingA, 2u, 0, 0, 0xC08u);
    *((_QWORD *)this + 4) = v18;
    if ( !v18 )
      v7 = -2147024882;
    v11 = v7;
  }
  else
  {
    v11 = -2147024882;
  }
  ReleaseMutex(*((HANDLE *)this + 2));
  if ( lpName )
    goto LABEL_21;
  return v11;
}

```

## disassembly

```asm
0x1800089d0  mov     [rsp+arg_10], rbx
0x1800089d5  push    rbp
0x1800089d6  push    rsi
0x1800089d7  push    rdi
0x1800089d8  push    r14
0x1800089da  push    r15
0x1800089dc  sub     rsp, 150h
0x1800089e3  mov     rax, cs:__security_cookie
0x1800089ea  xor     rax, rsp
0x1800089ed  mov     [rsp+178h+var_38], rax
0x1800089f5  mov     rbp, rdx
0x1800089f8  mov     rsi, rcx
0x1800089fb  mov     r8, rdx; char *
0x1800089fe  lea     rcx, [rsp+178h+var_148]; char *
0x180008a03  mov     edx, 104h; unsigned __int64
0x180008a08  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180008a0d  mov     r8b, 5Fh ; '_'
0x180008a10  lea     rcx, [rsp+178h+var_148]
0x180008a15  mov     dl, 5Ch ; '\'
0x180008a17  mov     r14d, eax
0x180008a1a  call    ReplaceChars
0x180008a1f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180008a23  lea     rcx, [rsp+178h+var_148]
0x180008a28  mov     rax, r15
0x180008a2b  inc     rax
0x180008a2e  cmp     byte ptr [rcx+rax], 0
0x180008a32  jnz     short loc_180008A2B
0x180008a34  lea     ebx, [rax+0Dh]
0x180008a37  mov     ecx, ebx
0x180008a39  call    PszAllocA
0x180008a3e  mov     rdi, rax
0x180008a41  test    rax, rax
0x180008a44  jnz     short loc_180008A50
0x180008a46  mov     ebx, 8007000Eh
0x180008a4b  jmp     loc_180008B9B
0x180008a50  lea     rax, aMutex; "mutex"
0x180008a57  mov     edx, ebx; unsigned __int64
0x180008a59  lea     r9, [rsp+178h+var_148]
0x180008a5e  mov     qword ptr [rsp+178h+dwMaximumSizeLow], rax
0x180008a63  lea     r8, aLocalSS_0; "Local\\%s%s"
0x180008a6a  mov     rcx, rdi; char *
0x180008a6d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008a72  mov     r8, rdi; lpName
0x180008a75  xor     edx, edx; bInitialOwner
0x180008a77  xor     ecx, ecx; lpMutexAttributes
0x180008a79  call    cs:__imp_CreateMutexA
0x180008a7f  mov     [rsi+10h], rax
0x180008a83  test    rax, rax
0x180008a86  jnz     short loc_180008A92
0x180008a88  mov     ebx, 8007000Eh
0x180008a8d  jmp     loc_180008B85
0x180008a92  mov     edx, 2710h; dwMilliseconds
0x180008a97  mov     rcx, rax; hHandle
0x180008a9a  call    cs:__imp_WaitForSingleObject
0x180008aa0  test    eax, eax
0x180008aa2  jz      short loc_180008AAE
0x180008aa4  mov     ebx, 80004005h
0x180008aa9  jmp     loc_180008B85
0x180008aae  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180008ab5  mov     rdx, rdi
0x180008ab8  mov     rax, [rcx]
0x180008abb  mov     rax, [rax+28h]
0x180008abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac4  test    rbp, rbp
0x180008ac7  jz      short loc_180008AD7
0x180008ac9  mov     rax, r15
0x180008acc  inc     rax
0x180008acf  cmp     byte ptr [rax+rbp], 0
0x180008ad3  jnz     short loc_180008ACC
0x180008ad5  jmp     short loc_180008AD9
0x180008ad7  xor     eax, eax
0x180008ad9  lea     ebx, [rax+0Bh]
0x180008adc  mov     ecx, ebx
0x180008ade  call    PszAllocA
0x180008ae3  mov     rdi, rax
0x180008ae6  test    rax, rax
0x180008ae9  jnz     short loc_180008AF5
0x180008aeb  mov     ebx, 8007000Eh
0x180008af0  jmp     loc_180008B76
0x180008af5  lea     rax, aMappedfile; "mappedfile"
0x180008afc  mov     edx, ebx; unsigned __int64
0x180008afe  mov     r9, rbp
0x180008b01  mov     qword ptr [rsp+178h+dwMaximumSizeLow], rax
0x180008b06  lea     r8, aSS_0; "%s%s"
0x180008b0d  mov     rcx, rdi; char *
0x180008b10  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008b15  mov     r8b, 5Fh ; '_'
0x180008b18  mov     dl, 5Ch ; '\'
0x180008b1a  mov     rcx, rdi
0x180008b1d  call    ReplaceChars
0x180008b22  xor     r9d, r9d; dwMaximumSizeHigh
0x180008b25  mov     [rsp+178h+lpName], rdi; lpName
0x180008b2a  mov     ebx, 0C08h
0x180008b2f  xor     edx, edx; lpFileMappingAttributes
0x180008b31  mov     rcx, r15; hFile
0x180008b34  mov     [rsp+178h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x180008b38  lea     r8d, [r9+4]; flProtect
0x180008b3c  call    cs:__imp_CreateFileMappingA
0x180008b42  mov     [rsi+18h], rax
0x180008b46  test    rax, rax
0x180008b49  jz      short loc_180008AEB
0x180008b4b  xor     r9d, r9d; dwFileOffsetLow
0x180008b4e  mov     qword ptr [rsp+178h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x180008b53  xor     r8d, r8d; dwFileOffsetHigh
0x180008b56  mov     rcx, rax; hFileMappingObject
0x180008b59  lea     edx, [r9+2]; dwDesiredAccess
0x180008b5d  call    cs:__imp_MapViewOfFile
0x180008b63  mov     ebx, 8007000Eh
0x180008b68  mov     [rsi+20h], rax
0x180008b6c  test    rax, rax
0x180008b6f  cmovz   r14d, ebx
0x180008b73  mov     ebx, r14d
0x180008b76  mov     rcx, [rsi+10h]; hMutex
0x180008b7a  call    cs:__imp_ReleaseMutex
0x180008b80  test    rdi, rdi
0x180008b83  jz      short loc_180008B9B
0x180008b85  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180008b8c  mov     rdx, [rcx]
0x180008b8f  mov     rax, [rdx+28h]
0x180008b93  mov     rdx, rdi
0x180008b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9b  mov     eax, ebx
0x180008b9d  mov     rcx, [rsp+178h+var_38]
0x180008ba5  xor     rcx, rsp; StackCookie
0x180008ba8  call    __security_check_cookie
0x180008bad  mov     rbx, [rsp+178h+arg_10]
0x180008bb5  add     rsp, 150h
0x180008bbc  pop     r15
0x180008bbe  pop     r14
0x180008bc0  pop     rdi
0x180008bc1  pop     rsi
0x180008bc2  pop     rbp
0x180008bc3  retn
```
