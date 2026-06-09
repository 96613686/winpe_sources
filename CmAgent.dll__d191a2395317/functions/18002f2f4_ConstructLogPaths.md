# ConstructLogPaths

- ea: `0x18002f2f4`
- end: `0x18002f4ae`
- name: `ConstructLogPaths`
- size: `442`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18002f9c4`

## callees

- `0x180002b28`
- `0x180002b34`
- `0x180002c00`
- `0x180002c0c`
- `0x180002c48`
- `0x18002f2f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f46a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f46a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002f313`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002f379`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002f313`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002f379`

## pseudocode

```c
__int64 __fastcall ConstructLogPaths(HANDLE hFile, __int64 a2, _QWORD *a3)
{
  DWORD FinalPathNameByHandleW; // eax
  __int64 v6; // rbx
  DWORD LastError; // ebx
  WCHAR *v8; // rax
  WCHAR *v9; // rbp
  void *v10; // rsi
  void *v11; // rdi
  DWORD v12; // eax
  __int64 v13; // r14
  void *v14; // rax
  rsize_t v15; // rbx

  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
  v6 = FinalPathNameByHandleW;
  if ( FinalPathNameByHandleW )
  {
    v8 = (WCHAR *)o__aligned_malloc_0(2LL * FinalPathNameByHandleW, 0x10u);
    v9 = v8;
    if ( v8 )
    {
      v10 = 0;
      v11 = 0;
      memset_0(v8, 0, 2 * v6);
      v12 = GetFinalPathNameByHandleW(hFile, v9, v6, 0);
      if ( v12 && v12 + 1 == (_DWORD)v6 && (v13 = v6 - 1, v6 != 1) )
      {
        v10 = o__aligned_malloc_0(2 * v13 + 12, 0x10u);
        v14 = o__aligned_malloc_0(2 * v13 + 12, 0x10u);
        v11 = v14;
        if ( v10 && v14 )
        {
          memset_0(v10, 0, 2 * v13 + 12);
          memset_0(v11, 0, 2 * v13 + 12);
          v15 = (unsigned __int64)(2 * v13 + 12) >> 1;
          if ( (unsigned int)o_wcsncpy_s_0(v10, v15, v9, v13)
            || wcscat_s((wchar_t *)v10, v15, L".LOG1")
            || (unsigned int)o_wcsncpy_s_0(v11, v15, v9, v13)
            || wcscat_s((wchar_t *)v11, v15, L".LOG2") )
          {
            LastError = 1359;
          }
          else
          {
            *a3 = v10;
            v10 = 0;
            a3[1] = v11;
            v11 = 0;
            LastError = 0;
          }
        }
        else
        {
          LastError = 8;
        }
      }
      else
      {
        LastError = GetLastError();
      }
      aligned_free(v9);
      if ( v10 )
        aligned_free(v10);
      if ( v11 )
        aligned_free(v11);
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18002f2f4  push    rbx
0x18002f2f6  push    rbp
0x18002f2f7  push    rsi
0x18002f2f8  push    rdi
0x18002f2f9  push    r12
0x18002f2fb  push    r13
0x18002f2fd  push    r14
0x18002f2ff  push    r15
0x18002f301  sub     rsp, 28h
0x18002f305  mov     r12, r8
0x18002f308  xor     r9d, r9d; dwFlags
0x18002f30b  xor     r8d, r8d; cchFilePath
0x18002f30e  xor     edx, edx; lpszFilePath
0x18002f310  mov     r13, rcx
0x18002f313  call    cs:__imp_GetFinalPathNameByHandleW
0x18002f31a  nop     dword ptr [rax+rax+00h]
0x18002f31f  mov     ebx, eax
0x18002f321  test    eax, eax
0x18002f323  jnz     short loc_18002F338
0x18002f325  call    cs:__imp_GetLastError
0x18002f32c  nop     dword ptr [rax+rax+00h]
0x18002f331  mov     ebx, eax
0x18002f333  jmp     loc_18002F49A
0x18002f338  lea     r15, [rbx+rbx]
0x18002f33c  mov     edx, 10h; Alignment
0x18002f341  mov     rcx, r15; Size
0x18002f344  mov     r14, rbx
0x18002f347  call    _o__aligned_malloc_0
0x18002f34c  mov     rbp, rax
0x18002f34f  test    rax, rax
0x18002f352  jnz     short loc_18002F35C
0x18002f354  lea     ebx, [rax+8]
0x18002f357  jmp     loc_18002F49A
0x18002f35c  mov     r8, r15; Size
0x18002f35f  xor     edx, edx; Val
0x18002f361  mov     rcx, rbp; void *
0x18002f364  xor     esi, esi
0x18002f366  xor     edi, edi
0x18002f368  call    memset_0
0x18002f36d  xor     r9d, r9d; dwFlags
0x18002f370  mov     r8d, ebx; cchFilePath
0x18002f373  mov     rdx, rbp; lpszFilePath
0x18002f376  mov     rcx, r13; hFile
0x18002f379  call    cs:__imp_GetFinalPathNameByHandleW
0x18002f380  nop     dword ptr [rax+rax+00h]
0x18002f385  test    eax, eax
0x18002f387  jz      loc_18002F46A
0x18002f38d  inc     eax
0x18002f38f  cmp     eax, ebx
0x18002f391  jnz     loc_18002F46A
0x18002f397  sub     r14, 1
0x18002f39b  jz      loc_18002F46A
0x18002f3a1  lea     rbx, ds:0Ch[r14*2]
0x18002f3a9  lea     edi, [rsi+10h]
0x18002f3ac  mov     rcx, rbx; Size
0x18002f3af  mov     edx, edi; Alignment
0x18002f3b1  call    _o__aligned_malloc_0
0x18002f3b6  mov     edx, edi; Alignment
0x18002f3b8  mov     rcx, rbx; Size
0x18002f3bb  mov     rsi, rax
0x18002f3be  call    _o__aligned_malloc_0
0x18002f3c3  mov     rdi, rax
0x18002f3c6  test    rsi, rsi
0x18002f3c9  jz      loc_18002F463
0x18002f3cf  test    rax, rax
0x18002f3d2  jz      loc_18002F463
0x18002f3d8  mov     r8, rbx; Size
0x18002f3db  xor     edx, edx; Val
0x18002f3dd  mov     rcx, rsi; void *
0x18002f3e0  call    memset_0
0x18002f3e5  mov     r8, rbx; Size
0x18002f3e8  xor     edx, edx; Val
0x18002f3ea  mov     rcx, rdi; void *
0x18002f3ed  call    memset_0
0x18002f3f2  shr     rbx, 1
0x18002f3f5  mov     r9, r14
0x18002f3f8  mov     rdx, rbx
0x18002f3fb  mov     r8, rbp
0x18002f3fe  mov     rcx, rsi
0x18002f401  call    _o_wcsncpy_s_0
0x18002f406  test    eax, eax
0x18002f408  jz      short loc_18002F411
0x18002f40a  mov     ebx, 54Fh
0x18002f40f  jmp     short loc_18002F478
0x18002f411  lea     r8, aLog1; ".LOG1"
0x18002f418  mov     rdx, rbx; SizeInWords
0x18002f41b  mov     rcx, rsi; Destination
0x18002f41e  call    wcscat_s
0x18002f423  test    eax, eax
0x18002f425  jnz     short loc_18002F40A
0x18002f427  mov     r9, r14
0x18002f42a  mov     r8, rbp
0x18002f42d  mov     rdx, rbx
0x18002f430  mov     rcx, rdi
0x18002f433  call    _o_wcsncpy_s_0
0x18002f438  test    eax, eax
0x18002f43a  jnz     short loc_18002F40A
0x18002f43c  lea     r8, aLog2; ".LOG2"
0x18002f443  mov     rdx, rbx; SizeInWords
0x18002f446  mov     rcx, rdi; Destination
0x18002f449  call    wcscat_s
0x18002f44e  test    eax, eax
0x18002f450  jnz     short loc_18002F40A
0x18002f452  mov     [r12], rsi
0x18002f456  xor     esi, esi
0x18002f458  mov     [r12+8], rdi
0x18002f45d  xor     edi, edi
0x18002f45f  xor     ebx, ebx
0x18002f461  jmp     short loc_18002F478
0x18002f463  mov     ebx, 8
0x18002f468  jmp     short loc_18002F478
0x18002f46a  call    cs:__imp_GetLastError
0x18002f471  nop     dword ptr [rax+rax+00h]
0x18002f476  mov     ebx, eax
0x18002f478  mov     rcx, rbp; Block
0x18002f47b  call    _aligned_free
0x18002f480  test    rsi, rsi
0x18002f483  jz      short loc_18002F48D
0x18002f485  mov     rcx, rsi; Block
0x18002f488  call    _aligned_free
0x18002f48d  test    rdi, rdi
0x18002f490  jz      short loc_18002F49A
0x18002f492  mov     rcx, rdi; Block
0x18002f495  call    _aligned_free
0x18002f49a  mov     eax, ebx
0x18002f49c  add     rsp, 28h
0x18002f4a0  pop     r15
0x18002f4a2  pop     r14
0x18002f4a4  pop     r13
0x18002f4a6  pop     r12
0x18002f4a8  pop     rdi
0x18002f4a9  pop     rsi
0x18002f4aa  pop     rbp
0x18002f4ab  pop     rbx
0x18002f4ac  retn
```
