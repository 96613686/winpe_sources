# ConstructLogPaths

- ea: `0x18008703c`
- end: `0x18008727c`
- name: `ConstructLogPaths`
- size: `576`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x180087778`

## callees

- `0x1800298c0`
- `0x18002bc90`
- `0x18002bf30`
- `0x180037670`
- `0x180086b34`
- `0x18008703c`
- `0x180097e20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008707f`
- `KERNEL32!GetLastError` at `0x1800871cc`
- `KERNEL32!GetLastError` at `0x18008707f`
- `KERNEL32!GetLastError` at `0x1800871cc`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18008706d`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1800870d5`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18008706d`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1800870d5`

## pseudocode

```c
__int64 __fastcall ConstructLogPaths(HANDLE hFile, wchar_t *Source, _QWORD *a3)
{
  void *v3; // rsi
  void *v4; // rdi
  _QWORD *v5; // r13
  DWORD FinalPathNameByHandleW; // eax
  __int64 v9; // rbx
  DWORD LastError; // ebx
  wchar_t *v11; // rax
  wchar_t *v12; // rbp
  DWORD v13; // eax
  rsize_t v14; // r14
  void *v15; // rax
  rsize_t v16; // rbx
  size_t v17; // r12
  wchar_t *v18; // rax

  v3 = 0;
  v4 = 0;
  v5 = a3;
  if ( Source )
  {
    v14 = wcsnlen(Source, 0x100u);
    v17 = 2 * v14 + 2;
    v18 = (wchar_t *)aligned_malloc(v17, 0x10u);
    v12 = v18;
    if ( !v18 )
      return 8;
    memset(v18, 0, v17);
    if ( wcsncpy_s(v12, v17 >> 1, Source, v14) )
    {
LABEL_20:
      LastError = 1359;
      goto LABEL_22;
    }
  }
  else
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
    v9 = FinalPathNameByHandleW;
    if ( !FinalPathNameByHandleW )
      return GetLastError();
    v11 = (wchar_t *)aligned_malloc(2LL * FinalPathNameByHandleW, 0x10u);
    v12 = v11;
    if ( !v11 )
      return 8;
    memset(v11, 0, 2 * v9);
    v13 = GetFinalPathNameByHandleW(hFile, v12, v9, 0);
    if ( !v13 || v13 + 1 != (_DWORD)v9 )
      goto LABEL_17;
    v5 = a3;
    v14 = v9 - 1;
  }
  if ( !v14 )
  {
LABEL_17:
    LastError = GetLastError();
    goto LABEL_22;
  }
  v3 = aligned_malloc(2 * v14 + 12, 0x10u);
  v15 = aligned_malloc(2 * v14 + 12, 0x10u);
  v4 = v15;
  if ( !v3 || !v15 )
  {
    LastError = 8;
    goto LABEL_22;
  }
  memset(v3, 0, 2 * v14 + 12);
  memset(v4, 0, 2 * v14 + 12);
  v16 = (2 * v14 + 12) >> 1;
  if ( wcsncpy_s((wchar_t *)v3, v16, v12, v14)
    || wcscat_s((wchar_t *)v3, v16, L".LOG1")
    || wcsncpy_s((wchar_t *)v4, v16, v12, v14)
    || wcscat_s((wchar_t *)v4, v16, L".LOG2") )
  {
    goto LABEL_20;
  }
  *v5 = v3;
  v3 = 0;
  v5[1] = v4;
  v4 = 0;
  LastError = 0;
LABEL_22:
  ORFree(v12);
  if ( v3 )
    ORFree(v3);
  if ( v4 )
    ORFree(v4);
  return LastError;
}

```

## disassembly

```asm
0x18008703c  mov     [rsp+arg_10], r8
0x180087041  push    rbx
0x180087042  push    rbp
0x180087043  push    rsi
0x180087044  push    rdi
0x180087045  push    r12
0x180087047  push    r13
0x180087049  push    r14
0x18008704b  push    r15
0x18008704d  sub     rsp, 28h
0x180087051  xor     esi, esi
0x180087053  xor     edi, edi
0x180087055  mov     r13, r8
0x180087058  mov     rbx, rdx
0x18008705b  mov     r12, rcx
0x18008705e  test    rdx, rdx
0x180087061  jnz     loc_1800871DC
0x180087067  xor     r9d, r9d; dwFlags
0x18008706a  xor     r8d, r8d; cchFilePath
0x18008706d  call    cs:__imp_GetFinalPathNameByHandleW
0x180087074  nop     dword ptr [rax+rax+00h]
0x180087079  mov     ebx, eax
0x18008707b  test    eax, eax
0x18008707d  jnz     short loc_180087092
0x18008707f  call    cs:__imp_GetLastError
0x180087086  nop     dword ptr [rax+rax+00h]
0x18008708b  mov     ebx, eax
0x18008708d  jmp     loc_180087268
0x180087092  lea     r13, [rbx+rbx]
0x180087096  mov     r15d, 10h
0x18008709c  mov     edx, r15d; Alignment
0x18008709f  mov     rcx, r13; Size
0x1800870a2  mov     r14, rbx
0x1800870a5  call    _aligned_malloc
0x1800870aa  mov     rbp, rax
0x1800870ad  test    rax, rax
0x1800870b0  jnz     short loc_1800870BC
0x1800870b2  mov     ebx, 8
0x1800870b7  jmp     loc_180087268
0x1800870bc  mov     r8, r13; Size
0x1800870bf  xor     edx, edx; Val
0x1800870c1  mov     rcx, rbp; void *
0x1800870c4  call    memset
0x1800870c9  xor     r9d, r9d; dwFlags
0x1800870cc  mov     r8d, ebx; cchFilePath
0x1800870cf  mov     rdx, rbp; lpszFilePath
0x1800870d2  mov     rcx, r12; hFile
0x1800870d5  call    cs:__imp_GetFinalPathNameByHandleW
0x1800870dc  nop     dword ptr [rax+rax+00h]
0x1800870e1  test    eax, eax
0x1800870e3  jz      loc_1800871CC
0x1800870e9  inc     eax
0x1800870eb  cmp     eax, ebx
0x1800870ed  jnz     loc_1800871CC
0x1800870f3  mov     r13, [rsp+68h+arg_10]
0x1800870fb  dec     r14
0x1800870fe  test    r14, r14
0x180087101  jz      loc_1800871CC
0x180087107  lea     rbx, ds:0Ch[r14*2]
0x18008710f  mov     rdx, r15; Alignment
0x180087112  mov     rcx, rbx; Size
0x180087115  call    _aligned_malloc
0x18008711a  mov     rdx, r15; Alignment
0x18008711d  mov     rcx, rbx; Size
0x180087120  mov     rsi, rax
0x180087123  call    _aligned_malloc
0x180087128  mov     rdi, rax
0x18008712b  test    rsi, rsi
0x18008712e  jz      loc_180087241
0x180087134  test    rax, rax
0x180087137  jz      loc_180087241
0x18008713d  mov     r8, rbx; Size
0x180087140  xor     edx, edx; Val
0x180087142  mov     rcx, rsi; void *
0x180087145  call    memset
0x18008714a  mov     r8, rbx; Size
0x18008714d  xor     edx, edx; Val
0x18008714f  mov     rcx, rdi; void *
0x180087152  call    memset
0x180087157  shr     rbx, 1
0x18008715a  mov     r9, r14; MaxCount
0x18008715d  mov     rdx, rbx; SizeInWords
0x180087160  mov     r8, rbp; Source
0x180087163  mov     rcx, rsi; Destination
0x180087166  call    wcsncpy_s
0x18008716b  test    eax, eax
0x18008716d  jnz     loc_18008723A
0x180087173  lea     r8, aLog1; ".LOG1"
0x18008717a  mov     rdx, rbx; SizeInWords
0x18008717d  mov     rcx, rsi; Destination
0x180087180  call    wcscat_s
0x180087185  test    eax, eax
0x180087187  jnz     loc_18008723A
0x18008718d  mov     r9, r14; MaxCount
0x180087190  mov     r8, rbp; Source
0x180087193  mov     rdx, rbx; SizeInWords
0x180087196  mov     rcx, rdi; Destination
0x180087199  call    wcsncpy_s
0x18008719e  test    eax, eax
0x1800871a0  jnz     loc_18008723A
0x1800871a6  lea     r8, aLog2; ".LOG2"
0x1800871ad  mov     rdx, rbx; SizeInWords
0x1800871b0  mov     rcx, rdi; Destination
0x1800871b3  call    wcscat_s
0x1800871b8  test    eax, eax
0x1800871ba  jnz     short loc_18008723A
0x1800871bc  mov     [r13+0], rsi
0x1800871c0  xor     esi, esi
0x1800871c2  mov     [r13+8], rdi
0x1800871c6  xor     edi, edi
0x1800871c8  xor     ebx, ebx
0x1800871ca  jmp     short loc_180087246
0x1800871cc  call    cs:__imp_GetLastError
0x1800871d3  nop     dword ptr [rax+rax+00h]
0x1800871d8  mov     ebx, eax
0x1800871da  jmp     short loc_180087246
0x1800871dc  mov     edx, 100h; MaxCount
0x1800871e1  mov     rcx, rbx; Source
0x1800871e4  call    wcsnlen
0x1800871e9  mov     r15d, 10h
0x1800871ef  mov     r14, rax
0x1800871f2  mov     edx, r15d; Alignment
0x1800871f5  lea     r12, ds:2[rax*2]
0x1800871fd  mov     rcx, r12; Size
0x180087200  call    _aligned_malloc
0x180087205  mov     rbp, rax
0x180087208  test    rax, rax
0x18008720b  jz      loc_1800870B2
0x180087211  mov     r8, r12; Size
0x180087214  xor     edx, edx; Val
0x180087216  mov     rcx, rax; void *
0x180087219  call    memset
0x18008721e  shr     r12, 1
0x180087221  mov     r9, r14; MaxCount
0x180087224  mov     rdx, r12; SizeInWords
0x180087227  mov     r8, rbx; Source
0x18008722a  mov     rcx, rbp; Destination
0x18008722d  call    wcsncpy_s
0x180087232  test    eax, eax
0x180087234  jz      loc_1800870FE
0x18008723a  mov     ebx, 54Fh
0x18008723f  jmp     short loc_180087246
0x180087241  mov     ebx, 8
0x180087246  mov     rcx, rbp
0x180087249  call    ORFree
0x18008724e  test    rsi, rsi
0x180087251  jz      short loc_18008725B
0x180087253  mov     rcx, rsi
0x180087256  call    ORFree
0x18008725b  test    rdi, rdi
0x18008725e  jz      short loc_180087268
0x180087260  mov     rcx, rdi
0x180087263  call    ORFree
0x180087268  mov     eax, ebx
0x18008726a  add     rsp, 28h
0x18008726e  pop     r15
0x180087270  pop     r14
0x180087272  pop     r13
0x180087274  pop     r12
0x180087276  pop     rdi
0x180087277  pop     rsi
0x180087278  pop     rbp
0x180087279  pop     rbx
0x18008727a  retn
```
