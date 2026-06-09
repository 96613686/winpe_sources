# CBufferedReader::FillBuffer(ulong,ulong *)

- ea: `0x1800326f8`
- end: `0x180032889`
- name: `?FillBuffer@CBufferedReader@@AEAAJKPEAK@Z`
- size: `401`
- prototype: `int(CBufferedReader *__hidden this, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180032890`
- `0x180032b74`

## callees

- `0x1800326f8`

## import_xrefs

- `msvcrt!free` at `0x18003286d`
- `msvcrt!free` at `0x18003286d`
- `msvcrt!malloc` at `0x180032734`
- `msvcrt!malloc` at `0x180032734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003281e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003281e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800327bf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800327bf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003276b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032816`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003276b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032816`

## pseudocode

```c
__int64 __fastcall CBufferedReader::FillBuffer(HANDLE *this, unsigned int a2, unsigned int *a3)
{
  __int64 v3; // r12
  void *v6; // rax
  void *v7; // rbp
  unsigned int v8; // edi
  HANDLE v9; // rcx
  BOOL v10; // ebx
  signed int v11; // eax
  int v12; // ebx
  signed int v13; // eax
  BOOL File; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+10h] BYREF

  v3 = a2;
  if ( a2 <= 1 && a3 )
  {
    if ( *((_DWORD *)this + 16394) )
    {
      File = ReadFile(*this, (char *)this + 32770 * a2 + 8, 0x8000u, a3, 0);
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( !File )
        return v8;
      v7 = 0;
    }
    else
    {
      v6 = malloc(0x4000u);
      v7 = v6;
      if ( !v6 )
        return (unsigned int)-2147024882;
      v9 = *this;
      NumberOfBytesRead = 0;
      v10 = ReadFile(v9, v6, 0x4000u, &NumberOfBytesRead, 0);
      v11 = GetLastError();
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      if ( !v10 )
      {
LABEL_22:
        free(v7);
        return v8;
      }
      if ( NumberOfBytesRead )
      {
        v12 = 2 * MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v7, NumberOfBytesRead, (LPWSTR)this + 16385 * v3 + 4, 0x8000);
        *a3 = v12;
        v13 = GetLastError();
        v8 = v13;
        if ( v13 > 0 )
          v8 = (unsigned __int16)v13 | 0x80070000;
        if ( !v12 )
          goto LABEL_22;
      }
      else
      {
        *a3 = 0;
      }
    }
    v8 = 0;
    *((_DWORD *)this + 16387) += *a3;
    *((_DWORD *)this + v3 + 16390) = *a3 >> 1;
    if ( *a3 != 0x8000 )
    {
      v8 = 1;
      *((_DWORD *)this + 16392) = 1;
    }
    if ( !v7 )
      return v8;
    goto LABEL_22;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800326f8  push    rbx
0x1800326fa  push    rbp
0x1800326fb  push    rsi
0x1800326fc  push    rdi
0x1800326fd  push    r12
0x1800326ff  push    r14
0x180032701  sub     rsp, 38h
0x180032705  mov     r12d, edx
0x180032708  mov     r14, r8
0x18003270b  mov     rsi, rcx
0x18003270e  cmp     edx, 1
0x180032711  ja      loc_180032877
0x180032717  test    r8, r8
0x18003271a  jz      loc_180032877
0x180032720  cmp     dword ptr [rcx+10028h], 0
0x180032727  jnz     loc_1800327F3
0x18003272d  mov     ebx, 4000h
0x180032732  mov     ecx, ebx; Size
0x180032734  call    cs:__imp_malloc
0x18003273a  mov     rbp, rax
0x18003273d  test    rax, rax
0x180032740  jnz     short loc_18003274C
0x180032742  mov     edi, 8007000Eh
0x180032747  jmp     loc_180032873
0x18003274c  mov     rcx, [rsi]; hFile
0x18003274f  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032754  mov     r8d, ebx; nNumberOfBytesToRead
0x180032757  mov     [rsp+68h+NumberOfBytesRead], 0
0x18003275f  mov     rdx, rbp; lpBuffer
0x180032762  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18003276b  call    cs:__imp_ReadFile
0x180032771  mov     ebx, eax
0x180032773  call    cs:__imp_GetLastError
0x180032779  mov     edi, eax
0x18003277b  test    eax, eax
0x18003277d  jle     short loc_180032788
0x18003277f  movzx   edi, ax
0x180032782  or      edi, 80070000h
0x180032788  test    ebx, ebx
0x18003278a  jz      loc_18003286A
0x180032790  mov     r9d, [rsp+68h+NumberOfBytesRead]; cbMultiByte
0x180032795  test    r9d, r9d
0x180032798  jz      short loc_1800327EA
0x18003279a  imul    rcx, r12, 8002h
0x1800327a1  mov     [rsp+68h+cchWideChar], 8000h; cchWideChar
0x1800327a9  mov     r8, rbp; lpMultiByteStr
0x1800327ac  add     rcx, 8
0x1800327b0  xor     edx, edx; dwFlags
0x1800327b2  add     rcx, rsi
0x1800327b5  mov     [rsp+68h+lpOverlapped], rcx; lpWideCharStr
0x1800327ba  mov     ecx, 0FDE9h; CodePage
0x1800327bf  call    cs:__imp_MultiByteToWideChar
0x1800327c5  mov     ebx, eax
0x1800327c7  add     ebx, ebx
0x1800327c9  mov     [r14], ebx
0x1800327cc  call    cs:__imp_GetLastError
0x1800327d2  mov     edi, eax
0x1800327d4  test    eax, eax
0x1800327d6  jle     short loc_1800327E1
0x1800327d8  movzx   edi, ax
0x1800327db  or      edi, 80070000h
0x1800327e1  test    ebx, ebx
0x1800327e3  jnz     short loc_180032839
0x1800327e5  jmp     loc_18003286A
0x1800327ea  mov     dword ptr [r14], 0
0x1800327f1  jmp     short loc_180032839
0x1800327f3  mov     rcx, [rcx]; hFile
0x1800327f6  mov     r9, r14; lpNumberOfBytesRead
0x1800327f9  imul    rdx, r12, 8002h
0x180032800  mov     r8d, 8000h; nNumberOfBytesToRead
0x180032806  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18003280f  add     rdx, 8
0x180032813  add     rdx, rsi; lpBuffer
0x180032816  call    cs:__imp_ReadFile
0x18003281c  mov     ebx, eax
0x18003281e  call    cs:__imp_GetLastError
0x180032824  mov     edi, eax
0x180032826  test    eax, eax
0x180032828  jle     short loc_180032833
0x18003282a  movzx   edi, ax
0x18003282d  or      edi, 80070000h
0x180032833  test    ebx, ebx
0x180032835  jz      short loc_180032873
0x180032837  xor     ebp, ebp
0x180032839  mov     eax, [r14]
0x18003283c  xor     edi, edi
0x18003283e  add     [rsi+1000Ch], eax
0x180032844  mov     eax, [r14]
0x180032847  shr     eax, 1
0x180032849  mov     [rsi+r12*4+10018h], eax
0x180032851  cmp     dword ptr [r14], 8000h
0x180032858  jz      short loc_180032865
0x18003285a  lea     eax, [rdi+1]
0x18003285d  mov     edi, eax
0x18003285f  mov     [rsi+10020h], eax
0x180032865  test    rbp, rbp
0x180032868  jz      short loc_180032873
0x18003286a  mov     rcx, rbp; Block
0x18003286d  call    cs:__imp_free
0x180032873  mov     eax, edi
0x180032875  jmp     short loc_18003287C
0x180032877  mov     eax, 80070057h
0x18003287c  add     rsp, 38h
0x180032880  pop     r14
0x180032882  pop     r12
0x180032884  pop     rdi
0x180032885  pop     rsi
0x180032886  pop     rbp
0x180032887  pop     rbx
0x180032888  retn
```
