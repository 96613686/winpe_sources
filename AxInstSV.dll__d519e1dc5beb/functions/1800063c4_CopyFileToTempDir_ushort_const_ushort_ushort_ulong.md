# CopyFileToTempDir(ushort const *,ushort *,ushort *,ulong)

- ea: `0x1800063c4`
- end: `0x180006510`
- name: `?CopyFileToTempDir@@YAJPEBGPEAG1K@Z`
- size: `332`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005ee0`

## callees

- `0x180001720`
- `0x180005b30`
- `0x180005b78`
- `0x1800063c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000648c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000648c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006436`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006436`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800064c1`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800064c1`

## pseudocode

```c
__int64 __fastcall CopyFileToTempDir(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v6; // rsi
  WCHAR v7; // ax
  LPWSTR v8; // rcx
  _WORD *v9; // rax
  int i; // ebx
  int v11; // ebx
  signed int LastError; // eax
  __int64 v14; // [rsp+20h] [rbp-258h]
  WCHAR FileName[264]; // [rsp+30h] [rbp-248h] BYREF

  v6 = a2;
  if ( a2 )
  {
    v7 = *a2;
    if ( !*a2 )
      return (unsigned int)-2147467259;
    v8 = a2;
    do
    {
      if ( v7 == 92 || *v8 == 58 || *v8 == 47 )
      {
        v9 = v8 + 1;
        if ( v8[1] )
        {
          if ( *v9 != 92 && *v9 != 47 )
            v6 = v8 + 1;
        }
      }
      v8 = CharNextW(v8);
      v7 = *v8;
    }
    while ( *v8 );
  }
  if ( v6 != a2 )
  {
    for ( i = 1; i <= 500; ++i )
    {
      LODWORD(v14) = i;
      if ( (int)StringCchPrintfW(FileName, 0x104u, L"%s\\[%d]%s", a1, v14, v6) < 0 || GetFileAttributesW(FileName) == -1 )
      {
        v11 = StringCchCopyW(a3, 0x104u, FileName);
        if ( v11 >= 0 && !CopyFileW(a2, FileName, 1) )
        {
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
        return (unsigned int)v11;
      }
    }
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x1800063c4  mov     [rsp+arg_18], rbx
0x1800063c9  push    rbp
0x1800063ca  push    rsi
0x1800063cb  push    rdi
0x1800063cc  push    r14
0x1800063ce  push    r15
0x1800063d0  sub     rsp, 250h
0x1800063d7  mov     rax, cs:__security_cookie
0x1800063de  xor     rax, rsp
0x1800063e1  mov     [rsp+278h+var_38], rax
0x1800063e9  xor     r15d, r15d
0x1800063ec  mov     rbp, r8
0x1800063ef  mov     rdi, rdx
0x1800063f2  mov     r14, rcx
0x1800063f5  mov     rsi, rdx
0x1800063f8  test    rdx, rdx
0x1800063fb  jz      short loc_180006447
0x1800063fd  movzx   eax, word ptr [rdx]
0x180006400  test    ax, ax
0x180006403  jz      loc_1800064E2
0x180006409  mov     rcx, rdx; lpsz
0x18000640c  cmp     ax, 5Ch ; '\'
0x180006410  jz      short loc_18000641E
0x180006412  cmp     word ptr [rcx], 3Ah ; ':'
0x180006416  jz      short loc_18000641E
0x180006418  cmp     word ptr [rcx], 2Fh ; '/'
0x18000641c  jnz     short loc_180006436
0x18000641e  lea     rax, [rcx+2]
0x180006422  cmp     [rax], r15w
0x180006426  jz      short loc_180006436
0x180006428  cmp     word ptr [rax], 5Ch ; '\'
0x18000642c  jz      short loc_180006436
0x18000642e  cmp     word ptr [rax], 2Fh ; '/'
0x180006432  cmovnz  rsi, rax
0x180006436  call    cs:__imp_CharNextW
0x18000643c  mov     rcx, rax
0x18000643f  movzx   eax, word ptr [rax]
0x180006442  test    ax, ax
0x180006445  jnz     short loc_18000640C
0x180006447  cmp     rsi, rdi
0x18000644a  jz      loc_1800064E2
0x180006450  mov     ebx, 1
0x180006455  cmp     ebx, 1F4h
0x18000645b  jg      loc_1800064E2
0x180006461  mov     [rsp+278h+var_250], rsi
0x180006466  lea     r8, aSDS; "%s\\[%d]%s"
0x18000646d  mov     r9, r14
0x180006470  mov     dword ptr [rsp+278h+var_258], ebx
0x180006474  mov     edx, 104h; unsigned __int64
0x180006479  lea     rcx, [rsp+278h+FileName]; unsigned __int16 *
0x18000647e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006483  test    eax, eax
0x180006485  js      short loc_18000649B
0x180006487  lea     rcx, [rsp+278h+FileName]; lpFileName
0x18000648c  call    cs:__imp_GetFileAttributesW
0x180006492  cmp     eax, 0FFFFFFFFh
0x180006495  jz      short loc_18000649B
0x180006497  inc     ebx
0x180006499  jmp     short loc_180006455
0x18000649b  lea     r8, [rsp+278h+FileName]; unsigned __int16 *
0x1800064a0  mov     edx, 104h; unsigned __int64
0x1800064a5  mov     rcx, rbp; unsigned __int16 *
0x1800064a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800064ad  mov     ebx, eax
0x1800064af  test    eax, eax
0x1800064b1  js      short loc_1800064E7
0x1800064b3  mov     r8d, 1; bFailIfExists
0x1800064b9  lea     rdx, [rsp+278h+FileName]; lpNewFileName
0x1800064be  mov     rcx, rdi; lpExistingFileName
0x1800064c1  call    cs:__imp_CopyFileW
0x1800064c7  test    eax, eax
0x1800064c9  jnz     short loc_1800064E7
0x1800064cb  call    cs:__imp_GetLastError
0x1800064d1  mov     ebx, eax
0x1800064d3  test    eax, eax
0x1800064d5  jle     short loc_1800064E7
0x1800064d7  movzx   ebx, ax
0x1800064da  or      ebx, 80070000h
0x1800064e0  jmp     short loc_1800064E7
0x1800064e2  mov     ebx, 80004005h
0x1800064e7  mov     eax, ebx
0x1800064e9  mov     rcx, [rsp+278h+var_38]
0x1800064f1  xor     rcx, rsp; StackCookie
0x1800064f4  call    __security_check_cookie
0x1800064f9  mov     rbx, [rsp+278h+arg_18]
0x180006501  add     rsp, 250h
0x180006508  pop     r15
0x18000650a  pop     r14
0x18000650c  pop     rdi
0x18000650d  pop     rsi
0x18000650e  pop     rbp
0x18000650f  retn
```
