# FormLongPathName

- ea: `0x180052f10`
- end: `0x18005301a`
- name: `FormLongPathName`
- size: `266`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180053994`

## callees

- `0x180052f10`
- `0x180053234`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180052f4a`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180052f86`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180052f4a`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180052f86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052fe3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052fe3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052f5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052fd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052f5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052fd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052f6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052f6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ff7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053007`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ff7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052fed`

## pseudocode

```c
const WCHAR *__fastcall FormLongPathName(unsigned __int16 *a1)
{
  const WCHAR *v1; // rax
  const WCHAR *v2; // rbp
  DWORD LongPathNameW; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rax
  WCHAR *v6; // rsi
  DWORD v7; // r14d
  WCHAR *v8; // rax
  const WCHAR *v9; // rbx
  DWORD LastError; // edi
  WCHAR *v11; // rsi
  HANDLE v12; // rax

  if ( a1 && *a1 )
  {
    v1 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v2 = v1;
    if ( !v1 )
    {
      v9 = 0;
      LastError = GetLastError();
LABEL_20:
      SetLastError(LastError);
      return v9;
    }
    LongPathNameW = GetLongPathNameW(v1, 0, 0);
    if ( LongPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v5 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * LongPathNameW);
      v6 = v5;
      if ( v5 )
      {
        v7 = 0;
        if ( !GetLongPathNameW(v2, v5, LongPathNameW) )
          v7 = GetLastError();
      }
      else
      {
        v7 = 14;
      }
      v8 = v6;
      if ( v6 )
      {
        v9 = v6;
LABEL_13:
        LastError = 0;
        if ( v6 )
          LastError = v7;
        v11 = 0;
        if ( v8 )
          v11 = (WCHAR *)v2;
        if ( v11 )
        {
          v12 = GetProcessHeap();
          HeapFree(v12, 0, v11);
        }
        goto LABEL_20;
      }
    }
    else
    {
      v6 = 0;
      v7 = GetLastError();
      v8 = 0;
    }
    v9 = v2;
    goto LABEL_13;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180052f10  push    rbx
0x180052f12  push    rbp
0x180052f13  push    rsi
0x180052f14  push    rdi
0x180052f15  push    r14
0x180052f17  sub     rsp, 20h
0x180052f1b  test    rcx, rcx
0x180052f1e  jz      loc_180053002
0x180052f24  xor     eax, eax
0x180052f26  cmp     ax, [rcx]
0x180052f29  jz      loc_180053002
0x180052f2f  xor     edx, edx
0x180052f31  call    PrepareUnicodePathEx
0x180052f36  mov     rbp, rax
0x180052f39  test    rax, rax
0x180052f3c  jz      loc_180052FEB
0x180052f42  xor     r8d, r8d; cchBuffer
0x180052f45  xor     edx, edx; lpszLongPath
0x180052f47  mov     rcx, rax; lpszShortPath
0x180052f4a  call    cs:__imp_GetLongPathNameW
0x180052f50  mov     edi, eax
0x180052f52  test    eax, eax
0x180052f54  jz      short loc_180052FAE
0x180052f56  mov     ebx, edi
0x180052f58  add     rbx, rbx
0x180052f5b  call    cs:__imp_GetProcessHeap
0x180052f61  mov     r8, rbx; dwBytes
0x180052f64  mov     edx, 8; dwFlags
0x180052f69  mov     rcx, rax; hHeap
0x180052f6c  call    cs:__imp_HeapAlloc
0x180052f72  mov     rsi, rax
0x180052f75  test    rax, rax
0x180052f78  jz      short loc_180052F9B
0x180052f7a  mov     r8d, edi; cchBuffer
0x180052f7d  mov     rdx, rax; lpszLongPath
0x180052f80  mov     rcx, rbp; lpszShortPath
0x180052f83  xor     r14d, r14d
0x180052f86  call    cs:__imp_GetLongPathNameW
0x180052f8c  test    eax, eax
0x180052f8e  jnz     short loc_180052FA1
0x180052f90  call    cs:__imp_GetLastError
0x180052f96  mov     r14d, eax
0x180052f99  jmp     short loc_180052FA1
0x180052f9b  mov     r14d, 0Eh
0x180052fa1  mov     rax, rsi
0x180052fa4  test    rsi, rsi
0x180052fa7  jz      short loc_180052FBB
0x180052fa9  mov     rbx, rsi
0x180052fac  jmp     short loc_180052FBE
0x180052fae  call    cs:__imp_GetLastError
0x180052fb4  xor     esi, esi
0x180052fb6  mov     r14d, eax
0x180052fb9  xor     eax, eax
0x180052fbb  mov     rbx, rbp
0x180052fbe  xor     edi, edi
0x180052fc0  test    rsi, rsi
0x180052fc3  cmovnz  edi, r14d
0x180052fc7  xor     esi, esi
0x180052fc9  test    rax, rax
0x180052fcc  cmovnz  rsi, rbp
0x180052fd0  test    rsi, rsi
0x180052fd3  jz      short loc_180052FF5
0x180052fd5  call    cs:__imp_GetProcessHeap
0x180052fdb  mov     r8, rsi; lpMem
0x180052fde  xor     edx, edx; dwFlags
0x180052fe0  mov     rcx, rax; hHeap
0x180052fe3  call    cs:__imp_HeapFree
0x180052fe9  jmp     short loc_180052FF5
0x180052feb  xor     ebx, ebx
0x180052fed  call    cs:__imp_GetLastError
0x180052ff3  mov     edi, eax
0x180052ff5  mov     ecx, edi; dwErrCode
0x180052ff7  call    cs:__imp_SetLastError
0x180052ffd  mov     rax, rbx
0x180053000  jmp     short loc_18005300F
0x180053002  mov     ecx, 57h ; 'W'; dwErrCode
0x180053007  call    cs:__imp_SetLastError
0x18005300d  xor     eax, eax
0x18005300f  add     rsp, 20h
0x180053013  pop     r14
0x180053015  pop     rdi
0x180053016  pop     rsi
0x180053017  pop     rbp
0x180053018  pop     rbx
0x180053019  retn
```
