# ConstructLogPaths

- ea: `0x180087fa8`
- end: `0x1800881e8`
- name: `ConstructLogPaths`
- size: `576`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1800886d8`

## callees

- `0x1800259b0`
- `0x180027d80`
- `0x180028020`
- `0x180033760`
- `0x180087aa0`
- `0x180087fa8`
- `0x180099cb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180087feb`
- `KERNEL32!GetLastError` at `0x180088138`
- `KERNEL32!GetLastError` at `0x180087feb`
- `KERNEL32!GetLastError` at `0x180088138`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180087fd9`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180088041`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180087fd9`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180088041`

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
0x180087fa8  mov     [rsp+arg_10], r8
0x180087fad  push    rbx
0x180087fae  push    rbp
0x180087faf  push    rsi
0x180087fb0  push    rdi
0x180087fb1  push    r12
0x180087fb3  push    r13
0x180087fb5  push    r14
0x180087fb7  push    r15
0x180087fb9  sub     rsp, 28h
0x180087fbd  xor     esi, esi
0x180087fbf  xor     edi, edi
0x180087fc1  mov     r13, r8
0x180087fc4  mov     rbx, rdx
0x180087fc7  mov     r12, rcx
0x180087fca  test    rdx, rdx
0x180087fcd  jnz     loc_180088148
0x180087fd3  xor     r9d, r9d; dwFlags
0x180087fd6  xor     r8d, r8d; cchFilePath
0x180087fd9  call    cs:__imp_GetFinalPathNameByHandleW
0x180087fe0  nop     dword ptr [rax+rax+00h]
0x180087fe5  mov     ebx, eax
0x180087fe7  test    eax, eax
0x180087fe9  jnz     short loc_180087FFE
0x180087feb  call    cs:__imp_GetLastError
0x180087ff2  nop     dword ptr [rax+rax+00h]
0x180087ff7  mov     ebx, eax
0x180087ff9  jmp     loc_1800881D4
0x180087ffe  lea     r13, [rbx+rbx]
0x180088002  mov     r15d, 10h
0x180088008  mov     edx, r15d; Alignment
0x18008800b  mov     rcx, r13; Size
0x18008800e  mov     r14, rbx
0x180088011  call    _aligned_malloc
0x180088016  mov     rbp, rax
0x180088019  test    rax, rax
0x18008801c  jnz     short loc_180088028
0x18008801e  mov     ebx, 8
0x180088023  jmp     loc_1800881D4
0x180088028  mov     r8, r13; Size
0x18008802b  xor     edx, edx; Val
0x18008802d  mov     rcx, rbp; void *
0x180088030  call    memset
0x180088035  xor     r9d, r9d; dwFlags
0x180088038  mov     r8d, ebx; cchFilePath
0x18008803b  mov     rdx, rbp; lpszFilePath
0x18008803e  mov     rcx, r12; hFile
0x180088041  call    cs:__imp_GetFinalPathNameByHandleW
0x180088048  nop     dword ptr [rax+rax+00h]
0x18008804d  test    eax, eax
0x18008804f  jz      loc_180088138
0x180088055  inc     eax
0x180088057  cmp     eax, ebx
0x180088059  jnz     loc_180088138
0x18008805f  mov     r13, [rsp+68h+arg_10]
0x180088067  dec     r14
0x18008806a  test    r14, r14
0x18008806d  jz      loc_180088138
0x180088073  lea     rbx, ds:0Ch[r14*2]
0x18008807b  mov     rdx, r15; Alignment
0x18008807e  mov     rcx, rbx; Size
0x180088081  call    _aligned_malloc
0x180088086  mov     rdx, r15; Alignment
0x180088089  mov     rcx, rbx; Size
0x18008808c  mov     rsi, rax
0x18008808f  call    _aligned_malloc
0x180088094  mov     rdi, rax
0x180088097  test    rsi, rsi
0x18008809a  jz      loc_1800881AD
0x1800880a0  test    rax, rax
0x1800880a3  jz      loc_1800881AD
0x1800880a9  mov     r8, rbx; Size
0x1800880ac  xor     edx, edx; Val
0x1800880ae  mov     rcx, rsi; void *
0x1800880b1  call    memset
0x1800880b6  mov     r8, rbx; Size
0x1800880b9  xor     edx, edx; Val
0x1800880bb  mov     rcx, rdi; void *
0x1800880be  call    memset
0x1800880c3  shr     rbx, 1
0x1800880c6  mov     r9, r14; MaxCount
0x1800880c9  mov     rdx, rbx; SizeInWords
0x1800880cc  mov     r8, rbp; Source
0x1800880cf  mov     rcx, rsi; Destination
0x1800880d2  call    wcsncpy_s
0x1800880d7  test    eax, eax
0x1800880d9  jnz     loc_1800881A6
0x1800880df  lea     r8, aLog1; ".LOG1"
0x1800880e6  mov     rdx, rbx; SizeInWords
0x1800880e9  mov     rcx, rsi; Destination
0x1800880ec  call    wcscat_s
0x1800880f1  test    eax, eax
0x1800880f3  jnz     loc_1800881A6
0x1800880f9  mov     r9, r14; MaxCount
0x1800880fc  mov     r8, rbp; Source
0x1800880ff  mov     rdx, rbx; SizeInWords
0x180088102  mov     rcx, rdi; Destination
0x180088105  call    wcsncpy_s
0x18008810a  test    eax, eax
0x18008810c  jnz     loc_1800881A6
0x180088112  lea     r8, aLog2; ".LOG2"
0x180088119  mov     rdx, rbx; SizeInWords
0x18008811c  mov     rcx, rdi; Destination
0x18008811f  call    wcscat_s
0x180088124  test    eax, eax
0x180088126  jnz     short loc_1800881A6
0x180088128  mov     [r13+0], rsi
0x18008812c  xor     esi, esi
0x18008812e  mov     [r13+8], rdi
0x180088132  xor     edi, edi
0x180088134  xor     ebx, ebx
0x180088136  jmp     short loc_1800881B2
0x180088138  call    cs:__imp_GetLastError
0x18008813f  nop     dword ptr [rax+rax+00h]
0x180088144  mov     ebx, eax
0x180088146  jmp     short loc_1800881B2
0x180088148  mov     edx, 100h; MaxCount
0x18008814d  mov     rcx, rbx; Source
0x180088150  call    wcsnlen
0x180088155  mov     r15d, 10h
0x18008815b  mov     r14, rax
0x18008815e  mov     edx, r15d; Alignment
0x180088161  lea     r12, ds:2[rax*2]
0x180088169  mov     rcx, r12; Size
0x18008816c  call    _aligned_malloc
0x180088171  mov     rbp, rax
0x180088174  test    rax, rax
0x180088177  jz      loc_18008801E
0x18008817d  mov     r8, r12; Size
0x180088180  xor     edx, edx; Val
0x180088182  mov     rcx, rax; void *
0x180088185  call    memset
0x18008818a  shr     r12, 1
0x18008818d  mov     r9, r14; MaxCount
0x180088190  mov     rdx, r12; SizeInWords
0x180088193  mov     r8, rbx; Source
0x180088196  mov     rcx, rbp; Destination
0x180088199  call    wcsncpy_s
0x18008819e  test    eax, eax
0x1800881a0  jz      loc_18008806A
0x1800881a6  mov     ebx, 54Fh
0x1800881ab  jmp     short loc_1800881B2
0x1800881ad  mov     ebx, 8
0x1800881b2  mov     rcx, rbp
0x1800881b5  call    ORFree
0x1800881ba  test    rsi, rsi
0x1800881bd  jz      short loc_1800881C7
0x1800881bf  mov     rcx, rsi
0x1800881c2  call    ORFree
0x1800881c7  test    rdi, rdi
0x1800881ca  jz      short loc_1800881D4
0x1800881cc  mov     rcx, rdi
0x1800881cf  call    ORFree
0x1800881d4  mov     eax, ebx
0x1800881d6  add     rsp, 28h
0x1800881da  pop     r15
0x1800881dc  pop     r14
0x1800881de  pop     r13
0x1800881e0  pop     r12
0x1800881e2  pop     rdi
0x1800881e3  pop     rsi
0x1800881e4  pop     rbp
0x1800881e5  pop     rbx
0x1800881e6  retn
```
