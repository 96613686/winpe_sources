# StructuredQuery1::WriteBuffer

- ea: `0x180042030`
- end: `0x1800421d5`
- name: `StructuredQuery1::WriteBuffer`
- size: `421`
- prototype: `__int64 __fastcall(HANDLE hFile, UINT CodePage, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180041f20`

## callees

- `0x180042030`
- `0x180059920`
- `0x18005db14`
- `0x18005e048`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800420a9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800420fb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800420a9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800420fb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180042124`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180042124`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::WriteBuffer(HANDLE hFile, UINT CodePage, __int16 *a3, int a4)
{
  int v4; // ebx
  __int16 *v5; // rsi
  int i; // edi
  bool v9; // zf
  int v10; // eax
  unsigned int v11; // r15d
  __int16 *v12; // r14
  int v13; // eax
  DWORD cbMultiByte; // ebp
  CHAR *lpMultiByteStr; // rax
  const struct std::nothrow_t *v16; // rdx
  CHAR *v17; // rsi
  unsigned int Error; // ebx
  const struct std::nothrow_t *v19; // rdx
  unsigned __int64 v21; // rax
  __int16 *v22; // rax
  __int16 v23; // cx
  DWORD NumberOfBytesWritten; // [rsp+A8h] [rbp+20h] BYREF

  v4 = a4;
  v5 = a3;
  for ( i = 0; a4; --a4 )
  {
    v9 = *a3 == 10;
    v10 = i + 1;
    ++a3;
    if ( !v9 )
      v10 = i;
    i = v10;
  }
  v11 = i + v4;
  if ( i )
  {
    v21 = 2LL * v11;
    if ( !is_mul_ok(v11, 2u) )
      v21 = -1;
    v22 = (__int16 *)operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v22;
    if ( !v22 )
    {
      Error = -2147024882;
LABEL_14:
      operator delete(v12, v16);
      return Error;
    }
    for ( ; v4; --v4 )
    {
      v23 = *v5;
      if ( *v5 == 10 )
        *v22++ = 13;
      *v22 = v23;
      ++v5;
      ++v22;
    }
  }
  else
  {
    v12 = v5;
  }
  v13 = WideCharToMultiByte(CodePage, CodePage == 0 ? 0x400 : 0, (LPCWCH)v12, v11, 0, 0, 0, 0);
  cbMultiByte = v13;
  if ( v13 <= 0 )
  {
    Error = ResultFromKnownLastError();
  }
  else
  {
    lpMultiByteStr = (CHAR *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
    v17 = lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      if ( WideCharToMultiByte(CodePage, CodePage == 0 ? 0x400 : 0, (LPCWCH)v12, v11, lpMultiByteStr, cbMultiByte, 0, 0) <= 0
        || (Error = 0, NumberOfBytesWritten = 0, !WriteFile(hFile, v17, cbMultiByte, &NumberOfBytesWritten, 0)) )
      {
        Error = ResultFromKnownLastError();
      }
      operator delete(v17, v19);
    }
    else
    {
      Error = -2147024882;
    }
  }
  if ( i )
    goto LABEL_14;
  return Error;
}

```

## disassembly

```asm
0x180042030  push    rbx
0x180042032  push    rbp
0x180042033  push    rsi
0x180042034  push    rdi
0x180042035  push    r12
0x180042037  push    r13
0x180042039  push    r14
0x18004203b  push    r15
0x18004203d  sub     rsp, 48h
0x180042041  xor     ebp, ebp
0x180042043  mov     ebx, r9d
0x180042046  mov     rsi, r8
0x180042049  mov     r12d, edx
0x18004204c  mov     r13, rcx
0x18004204f  mov     edi, ebp
0x180042051  test    r9d, r9d
0x180042054  jz      short loc_18004206D
0x180042056  cmp     word ptr [r8], 0Ah
0x18004205b  lea     eax, [rdi+1]
0x18004205e  lea     r8, [r8+2]
0x180042062  cmovnz  eax, edi
0x180042065  mov     edi, eax
0x180042067  add     r9d, 0FFFFFFFFh
0x18004206b  jnz     short loc_180042056
0x18004206d  lea     r15d, [rdi+rbx]
0x180042071  test    edi, edi
0x180042073  jnz     loc_18004215C
0x180042079  mov     r14, rsi
0x18004207c  mov     [rsp+88h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x180042081  mov     eax, r12d
0x180042084  neg     eax
0x180042086  mov     [rsp+88h+lpDefaultChar], rbp; lpDefaultChar
0x18004208b  mov     [rsp+88h+cbMultiByte], ebp; cbMultiByte
0x18004208f  mov     r9d, r15d; cchWideChar
0x180042092  sbb     ebx, ebx
0x180042094  mov     [rsp+88h+lpMultiByteStr], rbp; lpMultiByteStr
0x180042099  not     ebx
0x18004209b  mov     r8, r14; lpWideCharStr
0x18004209e  and     ebx, 400h
0x1800420a4  mov     ecx, r12d; CodePage
0x1800420a7  mov     edx, ebx; dwFlags
0x1800420a9  call    cs:__imp_WideCharToMultiByte
0x1800420af  movsxd  rbp, eax
0x1800420b2  test    eax, eax
0x1800420b4  jle     loc_1800421BF
0x1800420ba  mov     rcx, rbp; unsigned __int64
0x1800420bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800420c4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800420c9  mov     rsi, rax
0x1800420cc  test    rax, rax
0x1800420cf  jz      loc_1800421CB
0x1800420d5  mov     [rsp+88h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800420de  mov     r9d, r15d; cchWideChar
0x1800420e1  mov     [rsp+88h+lpDefaultChar], 0; lpDefaultChar
0x1800420ea  mov     r8, r14; lpWideCharStr
0x1800420ed  mov     [rsp+88h+cbMultiByte], ebp; cbMultiByte
0x1800420f1  mov     edx, ebx; dwFlags
0x1800420f3  mov     ecx, r12d; CodePage
0x1800420f6  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x1800420fb  call    cs:__imp_WideCharToMultiByte
0x180042101  test    eax, eax
0x180042103  jle     short loc_18004212E
0x180042105  xor     ebx, ebx
0x180042107  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004210f  mov     r8d, ebp; nNumberOfBytesToWrite
0x180042112  mov     [rsp+88h+NumberOfBytesWritten], ebx
0x180042119  mov     rdx, rsi; lpBuffer
0x18004211c  mov     [rsp+88h+lpMultiByteStr], rbx; lpOverlapped
0x180042121  mov     rcx, r13; hFile
0x180042124  call    cs:__imp_WriteFile
0x18004212a  test    eax, eax
0x18004212c  jnz     short loc_180042135
0x18004212e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180042133  mov     ebx, eax
0x180042135  mov     rcx, rsi; void *
0x180042138  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004213d  test    edi, edi
0x18004213f  jz      short loc_180042149
0x180042141  mov     rcx, r14; void *
0x180042144  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042149  mov     eax, ebx
0x18004214b  add     rsp, 48h
0x18004214f  pop     r15
0x180042151  pop     r14
0x180042153  pop     r13
0x180042155  pop     r12
0x180042157  pop     rdi
0x180042158  pop     rsi
0x180042159  pop     rbp
0x18004215a  pop     rbx
0x18004215b  retn
0x18004215c  mov     ecx, r15d
0x18004215f  mov     eax, 2
0x180042164  mul     rcx
0x180042167  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004216e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042175  cmovb   rax, rcx
0x180042179  mov     rcx, rax; unsigned __int64
0x18004217c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180042181  mov     r14, rax
0x180042184  test    rax, rax
0x180042187  jnz     short loc_180042190
0x180042189  mov     ebx, 8007000Eh
0x18004218e  jmp     short loc_180042141
0x180042190  test    ebx, ebx
0x180042192  jz      loc_18004207C
0x180042198  movzx   ecx, word ptr [rsi]
0x18004219b  cmp     cx, 0Ah
0x18004219f  jnz     short loc_1800421AA
0x1800421a1  mov     word ptr [rax], 0Dh
0x1800421a6  add     rax, 2
0x1800421aa  mov     [rax], cx
0x1800421ad  add     rsi, 2
0x1800421b1  add     rax, 2
0x1800421b5  add     ebx, 0FFFFFFFFh
0x1800421b8  jnz     short loc_180042198
0x1800421ba  jmp     loc_18004207C
0x1800421bf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800421c4  mov     ebx, eax
0x1800421c6  jmp     loc_18004213D
0x1800421cb  mov     ebx, 8007000Eh
0x1800421d0  jmp     loc_18004213D
```
