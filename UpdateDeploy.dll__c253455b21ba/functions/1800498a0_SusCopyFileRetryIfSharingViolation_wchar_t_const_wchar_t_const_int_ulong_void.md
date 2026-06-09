# SusCopyFileRetryIfSharingViolation(wchar_t const *,wchar_t const *,int,ulong,void *)

- ea: `0x1800498a0`
- end: `0x18004997e`
- name: `?SusCopyFileRetryIfSharingViolation@@YAJPEB_W0HKPEAX@Z`
- size: `222`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, BOOL bFailIfExists, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18003fd7c`
- `0x1800530e4`

## callees

- `0x180003180`
- `0x1800498a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498cd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049905`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049905`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180049914`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180049914`

## pseudocode

```c
__int64 __fastcall SusCopyFileRetryIfSharingViolation(
        LPCWSTR lpExistingFileName,
        LPCWSTR lpNewFileName,
        BOOL bFailIfExists,
        int a4)
{
  BOOL v5; // ebp
  const WCHAR *v6; // r14
  const WCHAR *v7; // r15
  int v8; // esi
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned int v11; // edi
  int v12; // eax
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = bFailIfExists;
  v6 = lpNewFileName;
  v7 = lpExistingFileName;
  v8 = 0;
  while ( 1 )
  {
    if ( CopyFileW(lpExistingFileName, lpNewFileName, bFailIfExists) )
      return 0;
    LastError = GetLastError();
    v10 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v10 = LastError;
    if ( (v10 & 0x80000000) == 0 )
      break;
    v11 = v10;
    if ( v10 != -2147024891 && v10 != -2147024864 )
      goto LABEL_13;
    v12 = v8++;
    if ( a4 == v12 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x643,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
        (const char *)v10,
        v14);
      return v10;
    }
    Sleep(0x1F4u);
    bFailIfExists = v5;
    lpNewFileName = v6;
    lpExistingFileName = v7;
  }
  v11 = -2147418113;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x633,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)v11,
    v14);
  return v11;
}

```

## disassembly

```asm
0x1800498a0  mov     rax, rsp
0x1800498a3  mov     [rax+8], rbx
0x1800498a7  mov     [rax+10h], rbp
0x1800498ab  mov     [rax+18h], rsi
0x1800498af  mov     [rax+20h], rdi
0x1800498b3  push    r12
0x1800498b5  push    r14
0x1800498b7  push    r15
0x1800498b9  sub     rsp, 20h
0x1800498bd  mov     r12d, r9d
0x1800498c0  mov     ebp, r8d
0x1800498c3  mov     r14, rdx
0x1800498c6  mov     r15, rcx
0x1800498c9  xor     esi, esi
0x1800498cb  jmp     short loc_180049914
0x1800498cd  call    cs:__imp_GetLastError
0x1800498d3  movzx   ebx, ax
0x1800498d6  or      ebx, 80070000h
0x1800498dc  test    eax, eax
0x1800498de  cmovle  ebx, eax
0x1800498e1  test    ebx, ebx
0x1800498e3  jns     short loc_18004995C
0x1800498e5  mov     edi, ebx
0x1800498e7  cmp     ebx, 80070005h
0x1800498ed  jz      short loc_1800498F7
0x1800498ef  cmp     ebx, 80070020h
0x1800498f5  jnz     short loc_180049961
0x1800498f7  mov     eax, esi
0x1800498f9  inc     esi
0x1800498fb  cmp     r12d, eax
0x1800498fe  jz      short loc_18004993F
0x180049900  mov     ecx, 1F4h; dwMilliseconds
0x180049905  call    cs:__imp_Sleep
0x18004990b  mov     r8d, ebp; bFailIfExists
0x18004990e  mov     rdx, r14; lpNewFileName
0x180049911  mov     rcx, r15; lpExistingFileName
0x180049914  call    cs:__imp_CopyFileW
0x18004991a  test    eax, eax
0x18004991c  jz      short loc_1800498CD
0x18004991e  xor     eax, eax
0x180049920  mov     rbx, [rsp+38h+arg_0]
0x180049925  mov     rbp, [rsp+38h+arg_8]
0x18004992a  mov     rsi, [rsp+38h+arg_10]
0x18004992f  mov     rdi, [rsp+38h+arg_18]
0x180049934  add     rsp, 20h
0x180049938  pop     r15
0x18004993a  pop     r14
0x18004993c  pop     r12
0x18004993e  retn
0x18004993f  mov     rcx, [rsp+38h]; this
0x180049944  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004994b  mov     r9d, ebx; char *
0x18004994e  mov     edx, 643h; void *
0x180049953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049958  mov     eax, ebx
0x18004995a  jmp     short loc_180049920
0x18004995c  mov     edi, 8000FFFFh
0x180049961  mov     rcx, [rsp+38h]; this
0x180049966  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004996d  mov     r9d, edi; char *
0x180049970  mov     edx, 633h; void *
0x180049975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004997a  mov     eax, edi
0x18004997c  jmp     short loc_180049920
```
