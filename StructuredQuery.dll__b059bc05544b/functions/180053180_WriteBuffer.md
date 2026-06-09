# WriteBuffer

- ea: `0x180053180`
- end: `0x18005331f`
- name: `WriteBuffer`
- size: `415`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180052fd8`

## callees

- `0x180053180`
- `0x180059920`
- `0x18005db14`
- `0x18005e048`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18005325f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800532ac`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18005325f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800532ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800532cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800532cf`

## pseudocode

```c
__int64 __fastcall WriteBuffer(HANDLE hFile, DWORD a2, __int16 *a3, int a4)
{
  int v4; // edi
  __int16 *v5; // rsi
  __int16 *v6; // rdx
  int v7; // ebx
  int i; // r8d
  int v10; // eax
  unsigned int v11; // r15d
  unsigned __int64 v12; // rax
  __int16 *v13; // rax
  const struct std::nothrow_t *v14; // rdx
  __int16 *v15; // r14
  __int16 v16; // cx
  unsigned int Error; // ebx
  int v18; // eax
  DWORD cbMultiByte; // ebp
  CHAR *lpMultiByteStr; // rax
  CHAR *v21; // rsi
  const struct std::nothrow_t *v22; // rdx
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+10h] BYREF

  NumberOfBytesWritten = a2;
  v4 = 0;
  v5 = a3;
  v6 = a3;
  v7 = a4;
  for ( i = a4; i; --i )
  {
    v10 = v4 + 1;
    if ( *v6 != 10 )
      v10 = v4;
    ++v6;
    v4 = v10;
  }
  v11 = v4 + a4;
  if ( v4 )
  {
    v12 = 2LL * v11;
    if ( !is_mul_ok(v11, 2u) )
      v12 = -1;
    v13 = (__int16 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v13;
    if ( !v13 )
    {
      Error = -2147024882;
LABEL_25:
      operator delete(v15, v14);
      return Error;
    }
    for ( ; v7; --v7 )
    {
      v16 = *v5;
      if ( *v5 == 10 )
        *v13++ = 13;
      *v13 = v16;
      ++v5;
      ++v13;
    }
  }
  else
  {
    v15 = v5;
  }
  v18 = WideCharToMultiByte(0xFDE9u, 0, (LPCWCH)v15, v11, 0, 0, 0, 0);
  cbMultiByte = v18;
  if ( v18 <= 0 )
  {
    Error = ResultFromKnownLastError();
  }
  else
  {
    lpMultiByteStr = (CHAR *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
    v21 = lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      if ( WideCharToMultiByte(0xFDE9u, 0, (LPCWCH)v15, v11, lpMultiByteStr, cbMultiByte, 0, 0) <= 0
        || (Error = 0, NumberOfBytesWritten = 0, !WriteFile(hFile, v21, cbMultiByte, &NumberOfBytesWritten, 0)) )
      {
        Error = ResultFromKnownLastError();
      }
      operator delete(v21, v22);
    }
    else
    {
      Error = -2147024882;
    }
  }
  if ( v4 )
    goto LABEL_25;
  return Error;
}

```

## disassembly

```asm
0x180053180  mov     [rsp+arg_0], rbx
0x180053185  mov     [rsp+arg_10], rbp
0x18005318a  mov     [rsp+NumberOfBytesWritten], edx
0x18005318e  push    rsi
0x18005318f  push    rdi
0x180053190  push    r12
0x180053192  push    r14
0x180053194  push    r15
0x180053196  sub     rsp, 40h
0x18005319a  xor     edi, edi
0x18005319c  mov     rsi, r8
0x18005319f  mov     rdx, r8
0x1800531a2  mov     ebx, r9d
0x1800531a5  mov     r12, rcx
0x1800531a8  mov     r8d, r9d
0x1800531ab  lea     ebp, [rdi+2]
0x1800531ae  test    r9d, r9d
0x1800531b1  jz      short loc_1800531C8
0x1800531b3  cmp     word ptr [rdx], 0Ah
0x1800531b7  lea     eax, [rdi+1]
0x1800531ba  cmovnz  eax, edi
0x1800531bd  add     rdx, rbp
0x1800531c0  mov     edi, eax
0x1800531c2  add     r8d, 0FFFFFFFFh
0x1800531c6  jnz     short loc_1800531B3
0x1800531c8  lea     r15d, [rdi+r9]
0x1800531cc  test    edi, edi
0x1800531ce  jz      short loc_18005322A
0x1800531d0  mov     ecx, r15d
0x1800531d3  mov     rax, rbp
0x1800531d6  mul     rcx
0x1800531d9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800531e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800531e7  cmovb   rax, rcx
0x1800531eb  mov     rcx, rax; unsigned __int64
0x1800531ee  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800531f3  mov     r14, rax
0x1800531f6  test    rax, rax
0x1800531f9  jz      short loc_180053220
0x1800531fb  test    ebx, ebx
0x1800531fd  jz      short loc_18005322D
0x1800531ff  movzx   ecx, word ptr [rsi]
0x180053202  cmp     cx, 0Ah
0x180053206  jnz     short loc_180053210
0x180053208  mov     word ptr [rax], 0Dh
0x18005320d  add     rax, rbp
0x180053210  mov     [rax], cx
0x180053213  add     rsi, rbp
0x180053216  add     rax, rbp
0x180053219  add     ebx, 0FFFFFFFFh
0x18005321c  jnz     short loc_1800531FF
0x18005321e  jmp     short loc_18005322D
0x180053220  mov     ebx, 8007000Eh
0x180053225  jmp     loc_1800532FC
0x18005322a  mov     r14, rsi
0x18005322d  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180053236  mov     ebx, 0FDE9h
0x18005323b  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x180053244  mov     ecx, ebx; CodePage
0x180053246  mov     [rsp+68h+cbMultiByte], 0; cbMultiByte
0x18005324e  mov     r9d, r15d; cchWideChar
0x180053251  mov     r8, r14; lpWideCharStr
0x180053254  mov     [rsp+68h+lpMultiByteStr], 0; lpMultiByteStr
0x18005325d  xor     edx, edx; dwFlags
0x18005325f  call    cs:__imp_WideCharToMultiByte
0x180053265  movsxd  rbp, eax
0x180053268  test    eax, eax
0x18005326a  jle     loc_1800532F1
0x180053270  mov     rcx, rbp; unsigned __int64
0x180053273  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005327a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005327f  mov     rsi, rax
0x180053282  test    rax, rax
0x180053285  jz      short loc_1800532EA
0x180053287  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180053290  mov     r9d, r15d; cchWideChar
0x180053293  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18005329c  mov     r8, r14; lpWideCharStr
0x18005329f  mov     [rsp+68h+cbMultiByte], ebp; cbMultiByte
0x1800532a3  xor     edx, edx; dwFlags
0x1800532a5  mov     ecx, ebx; CodePage
0x1800532a7  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x1800532ac  call    cs:__imp_WideCharToMultiByte
0x1800532b2  test    eax, eax
0x1800532b4  jle     short loc_1800532D9
0x1800532b6  xor     ebx, ebx
0x1800532b8  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800532bd  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800532c0  mov     [rsp+68h+NumberOfBytesWritten], ebx
0x1800532c4  mov     rdx, rsi; lpBuffer
0x1800532c7  mov     [rsp+68h+lpMultiByteStr], rbx; lpOverlapped
0x1800532cc  mov     rcx, r12; hFile
0x1800532cf  call    cs:__imp_WriteFile
0x1800532d5  test    eax, eax
0x1800532d7  jnz     short loc_1800532E0
0x1800532d9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800532de  mov     ebx, eax
0x1800532e0  mov     rcx, rsi; void *
0x1800532e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800532e8  jmp     short loc_1800532F8
0x1800532ea  mov     ebx, 8007000Eh
0x1800532ef  jmp     short loc_1800532F8
0x1800532f1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800532f6  mov     ebx, eax
0x1800532f8  test    edi, edi
0x1800532fa  jz      short loc_180053304
0x1800532fc  mov     rcx, r14; void *
0x1800532ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180053304  lea     r11, [rsp+68h+var_28]
0x180053309  mov     eax, ebx
0x18005330b  mov     rbx, [r11+30h]
0x18005330f  mov     rbp, [r11+40h]
0x180053313  mov     rsp, r11
0x180053316  pop     r15
0x180053318  pop     r14
0x18005331a  pop     r12
0x18005331c  pop     rdi
0x18005331d  pop     rsi
0x18005331e  retn
```
