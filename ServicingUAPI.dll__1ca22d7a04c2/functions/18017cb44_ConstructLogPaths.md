# ConstructLogPaths

- ea: `0x18017cb44`
- end: `0x18017cd92`
- name: `ConstructLogPaths`
- size: `590`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18017d298`

## callees

- `0x180003ae2`
- `0x180003aee`
- `0x180003c04`
- `0x180003c10`
- `0x180003c64`
- `0x18017cb44`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18017ccf3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18017ccf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017cb87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ccdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017cb87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ccdb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18017cb75`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18017cbdd`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18017cb75`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18017cbdd`

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
  WCHAR *v11; // rax
  WCHAR *v12; // rbp
  DWORD v13; // eax
  size_t v14; // r14
  void *v15; // rax
  rsize_t v16; // rbx
  size_t v17; // r12
  WCHAR *v18; // rax

  v3 = 0;
  v4 = 0;
  v5 = a3;
  if ( Source )
  {
    v14 = wcsnlen(Source, 0x100u);
    v17 = 2 * v14 + 2;
    v18 = (WCHAR *)o__aligned_malloc_0(v17, 0x10u);
    v12 = v18;
    if ( !v18 )
      return 8;
    memset_0(v18, 0, v17);
    if ( (unsigned int)o_wcsncpy_s_0(v12, v17 >> 1, Source, v14) )
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
    v11 = (WCHAR *)o__aligned_malloc_0(2LL * FinalPathNameByHandleW, 0x10u);
    v12 = v11;
    if ( !v11 )
      return 8;
    memset_0(v11, 0, 2 * v9);
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
  v3 = o__aligned_malloc_0(2 * v14 + 12, 0x10u);
  v15 = o__aligned_malloc_0(2 * v14 + 12, 0x10u);
  v4 = v15;
  if ( !v3 || !v15 )
  {
    LastError = 8;
    goto LABEL_22;
  }
  memset_0(v3, 0, 2 * v14 + 12);
  memset_0(v4, 0, 2 * v14 + 12);
  v16 = (2 * v14 + 12) >> 1;
  if ( (unsigned int)o_wcsncpy_s_0(v3, v16, v12, v14)
    || wcscat_s((wchar_t *)v3, v16, L".LOG1")
    || (unsigned int)o_wcsncpy_s_0(v4, v16, v12, v14)
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
  aligned_free(v12);
  if ( v3 )
    aligned_free(v3);
  if ( v4 )
    aligned_free(v4);
  return LastError;
}

```

## disassembly

```asm
0x18017cb44  mov     [rsp+arg_10], r8
0x18017cb49  push    rbx
0x18017cb4a  push    rbp
0x18017cb4b  push    rsi
0x18017cb4c  push    rdi
0x18017cb4d  push    r12
0x18017cb4f  push    r13
0x18017cb51  push    r14
0x18017cb53  push    r15
0x18017cb55  sub     rsp, 28h
0x18017cb59  xor     esi, esi
0x18017cb5b  xor     edi, edi
0x18017cb5d  mov     r13, r8
0x18017cb60  mov     rbx, rdx
0x18017cb63  mov     r12, rcx
0x18017cb66  test    rdx, rdx
0x18017cb69  jnz     loc_18017CCEB
0x18017cb6f  xor     r9d, r9d; dwFlags
0x18017cb72  xor     r8d, r8d; cchFilePath
0x18017cb75  call    cs:__imp_GetFinalPathNameByHandleW
0x18017cb7c  nop     dword ptr [rax+rax+00h]
0x18017cb81  mov     ebx, eax
0x18017cb83  test    eax, eax
0x18017cb85  jnz     short loc_18017CB9A
0x18017cb87  call    cs:__imp_GetLastError
0x18017cb8e  nop     dword ptr [rax+rax+00h]
0x18017cb93  mov     ebx, eax
0x18017cb95  jmp     loc_18017CD7E
0x18017cb9a  lea     r13, [rbx+rbx]
0x18017cb9e  mov     r15d, 10h
0x18017cba4  mov     edx, r15d; Alignment
0x18017cba7  mov     rcx, r13; Size
0x18017cbaa  mov     r14, rbx
0x18017cbad  call    _o__aligned_malloc_0
0x18017cbb2  mov     rbp, rax
0x18017cbb5  test    rax, rax
0x18017cbb8  jnz     short loc_18017CBC4
0x18017cbba  mov     ebx, 8
0x18017cbbf  jmp     loc_18017CD7E
0x18017cbc4  mov     r8, r13; Size
0x18017cbc7  xor     edx, edx; Val
0x18017cbc9  mov     rcx, rbp; void *
0x18017cbcc  call    memset_0
0x18017cbd1  xor     r9d, r9d; dwFlags
0x18017cbd4  mov     r8d, ebx; cchFilePath
0x18017cbd7  mov     rdx, rbp; lpszFilePath
0x18017cbda  mov     rcx, r12; hFile
0x18017cbdd  call    cs:__imp_GetFinalPathNameByHandleW
0x18017cbe4  nop     dword ptr [rax+rax+00h]
0x18017cbe9  test    eax, eax
0x18017cbeb  jz      loc_18017CCDB
0x18017cbf1  inc     eax
0x18017cbf3  cmp     eax, ebx
0x18017cbf5  jnz     loc_18017CCDB
0x18017cbfb  mov     r13, [rsp+68h+arg_10]
0x18017cc03  dec     r14
0x18017cc06  test    r14, r14
0x18017cc09  jz      loc_18017CCDB
0x18017cc0f  lea     rbx, ds:0Ch[r14*2]
0x18017cc17  mov     rdx, r15; Alignment
0x18017cc1a  mov     rcx, rbx; Size
0x18017cc1d  call    _o__aligned_malloc_0
0x18017cc22  mov     rdx, r15; Alignment
0x18017cc25  mov     rcx, rbx; Size
0x18017cc28  mov     rsi, rax
0x18017cc2b  call    _o__aligned_malloc_0
0x18017cc30  mov     rdi, rax
0x18017cc33  test    rsi, rsi
0x18017cc36  jz      loc_18017CD57
0x18017cc3c  test    rax, rax
0x18017cc3f  jz      loc_18017CD57
0x18017cc45  mov     r8, rbx; Size
0x18017cc48  xor     edx, edx; Val
0x18017cc4a  mov     rcx, rsi; void *
0x18017cc4d  call    memset_0
0x18017cc52  mov     r8, rbx; Size
0x18017cc55  xor     edx, edx; Val
0x18017cc57  mov     rcx, rdi; void *
0x18017cc5a  call    memset_0
0x18017cc5f  shr     rbx, 1
0x18017cc62  mov     r9, r14
0x18017cc65  mov     rdx, rbx
0x18017cc68  mov     r8, rbp
0x18017cc6b  mov     rcx, rsi
0x18017cc6e  call    _o_wcsncpy_s_0
0x18017cc73  test    eax, eax
0x18017cc75  jnz     loc_18017CD50
0x18017cc7b  lea     r8, aLog1; ".LOG1"
0x18017cc82  mov     rdx, rbx; SizeInWords
0x18017cc85  mov     rcx, rsi; Destination
0x18017cc88  call    wcscat_s
0x18017cc8d  test    eax, eax
0x18017cc8f  jnz     loc_18017CD50
0x18017cc95  mov     r9, r14
0x18017cc98  mov     r8, rbp
0x18017cc9b  mov     rdx, rbx
0x18017cc9e  mov     rcx, rdi
0x18017cca1  call    _o_wcsncpy_s_0
0x18017cca6  test    eax, eax
0x18017cca8  jnz     loc_18017CD50
0x18017ccae  lea     r8, aLog2; ".LOG2"
0x18017ccb5  mov     rdx, rbx; SizeInWords
0x18017ccb8  mov     rcx, rdi; Destination
0x18017ccbb  call    wcscat_s
0x18017ccc0  test    eax, eax
0x18017ccc2  jnz     loc_18017CD50
0x18017ccc8  mov     [r13+0], rsi
0x18017cccc  xor     esi, esi
0x18017ccce  mov     [r13+8], rdi
0x18017ccd2  xor     edi, edi
0x18017ccd4  xor     ebx, ebx
0x18017ccd6  jmp     loc_18017CD5C
0x18017ccdb  call    cs:__imp_GetLastError
0x18017cce2  nop     dword ptr [rax+rax+00h]
0x18017cce7  mov     ebx, eax
0x18017cce9  jmp     short loc_18017CD5C
0x18017cceb  mov     edx, 100h; MaxCount
0x18017ccf0  mov     rcx, rbx; Source
0x18017ccf3  call    cs:__imp_wcsnlen
0x18017ccfa  nop     dword ptr [rax+rax+00h]
0x18017ccff  mov     r15d, 10h
0x18017cd05  mov     r14, rax
0x18017cd08  mov     edx, r15d; Alignment
0x18017cd0b  lea     r12, ds:2[rax*2]
0x18017cd13  mov     rcx, r12; Size
0x18017cd16  call    _o__aligned_malloc_0
0x18017cd1b  mov     rbp, rax
0x18017cd1e  test    rax, rax
0x18017cd21  jz      loc_18017CBBA
0x18017cd27  mov     r8, r12; Size
0x18017cd2a  xor     edx, edx; Val
0x18017cd2c  mov     rcx, rax; void *
0x18017cd2f  call    memset_0
0x18017cd34  shr     r12, 1
0x18017cd37  mov     r9, r14
0x18017cd3a  mov     rdx, r12
0x18017cd3d  mov     r8, rbx
0x18017cd40  mov     rcx, rbp
0x18017cd43  call    _o_wcsncpy_s_0
0x18017cd48  test    eax, eax
0x18017cd4a  jz      loc_18017CC06
0x18017cd50  mov     ebx, 54Fh
0x18017cd55  jmp     short loc_18017CD5C
0x18017cd57  mov     ebx, 8
0x18017cd5c  mov     rcx, rbp; Block
0x18017cd5f  call    _aligned_free
0x18017cd64  test    rsi, rsi
0x18017cd67  jz      short loc_18017CD71
0x18017cd69  mov     rcx, rsi; Block
0x18017cd6c  call    _aligned_free
0x18017cd71  test    rdi, rdi
0x18017cd74  jz      short loc_18017CD7E
0x18017cd76  mov     rcx, rdi; Block
0x18017cd79  call    _aligned_free
0x18017cd7e  mov     eax, ebx
0x18017cd80  add     rsp, 28h
0x18017cd84  pop     r15
0x18017cd86  pop     r14
0x18017cd88  pop     r13
0x18017cd8a  pop     r12
0x18017cd8c  pop     rdi
0x18017cd8d  pop     rsi
0x18017cd8e  pop     rbp
0x18017cd8f  pop     rbx
0x18017cd90  retn
```
