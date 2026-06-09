# FormLongPathName

- ea: `0x18005fa9c`
- end: `0x18005fba6`
- name: `FormLongPathName`
- size: `266`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18005e748`
- `0x1800612f0`
- `0x1800623f4`

## callees

- `0x18005fa9c`
- `0x18005fd24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005faf8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005faf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fae7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fb61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fae7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fb61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fb6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fb6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fb83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fb93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fb83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fb93`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005fad6`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005fb12`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005fad6`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005fb12`

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
0x18005fa9c  push    rbx
0x18005fa9e  push    rbp
0x18005fa9f  push    rsi
0x18005faa0  push    rdi
0x18005faa1  push    r14
0x18005faa3  sub     rsp, 20h
0x18005faa7  test    rcx, rcx
0x18005faaa  jz      loc_18005FB8E
0x18005fab0  xor     eax, eax
0x18005fab2  cmp     ax, [rcx]
0x18005fab5  jz      loc_18005FB8E
0x18005fabb  xor     edx, edx
0x18005fabd  call    PrepareUnicodePathEx
0x18005fac2  mov     rbp, rax
0x18005fac5  test    rax, rax
0x18005fac8  jz      loc_18005FB77
0x18005face  xor     r8d, r8d; cchBuffer
0x18005fad1  xor     edx, edx; lpszLongPath
0x18005fad3  mov     rcx, rax; lpszShortPath
0x18005fad6  call    cs:__imp_GetLongPathNameW
0x18005fadc  mov     edi, eax
0x18005fade  test    eax, eax
0x18005fae0  jz      short loc_18005FB3A
0x18005fae2  mov     ebx, edi
0x18005fae4  add     rbx, rbx
0x18005fae7  call    cs:__imp_GetProcessHeap
0x18005faed  mov     r8, rbx; dwBytes
0x18005faf0  mov     edx, 8; dwFlags
0x18005faf5  mov     rcx, rax; hHeap
0x18005faf8  call    cs:__imp_HeapAlloc
0x18005fafe  mov     rsi, rax
0x18005fb01  test    rax, rax
0x18005fb04  jz      short loc_18005FB27
0x18005fb06  mov     r8d, edi; cchBuffer
0x18005fb09  mov     rdx, rax; lpszLongPath
0x18005fb0c  mov     rcx, rbp; lpszShortPath
0x18005fb0f  xor     r14d, r14d
0x18005fb12  call    cs:__imp_GetLongPathNameW
0x18005fb18  test    eax, eax
0x18005fb1a  jnz     short loc_18005FB2D
0x18005fb1c  call    cs:__imp_GetLastError
0x18005fb22  mov     r14d, eax
0x18005fb25  jmp     short loc_18005FB2D
0x18005fb27  mov     r14d, 0Eh
0x18005fb2d  mov     rax, rsi
0x18005fb30  test    rsi, rsi
0x18005fb33  jz      short loc_18005FB47
0x18005fb35  mov     rbx, rsi
0x18005fb38  jmp     short loc_18005FB4A
0x18005fb3a  call    cs:__imp_GetLastError
0x18005fb40  xor     esi, esi
0x18005fb42  mov     r14d, eax
0x18005fb45  xor     eax, eax
0x18005fb47  mov     rbx, rbp
0x18005fb4a  xor     edi, edi
0x18005fb4c  test    rsi, rsi
0x18005fb4f  cmovnz  edi, r14d
0x18005fb53  xor     esi, esi
0x18005fb55  test    rax, rax
0x18005fb58  cmovnz  rsi, rbp
0x18005fb5c  test    rsi, rsi
0x18005fb5f  jz      short loc_18005FB81
0x18005fb61  call    cs:__imp_GetProcessHeap
0x18005fb67  mov     r8, rsi; lpMem
0x18005fb6a  xor     edx, edx; dwFlags
0x18005fb6c  mov     rcx, rax; hHeap
0x18005fb6f  call    cs:__imp_HeapFree
0x18005fb75  jmp     short loc_18005FB81
0x18005fb77  xor     ebx, ebx
0x18005fb79  call    cs:__imp_GetLastError
0x18005fb7f  mov     edi, eax
0x18005fb81  mov     ecx, edi; dwErrCode
0x18005fb83  call    cs:__imp_SetLastError
0x18005fb89  mov     rax, rbx
0x18005fb8c  jmp     short loc_18005FB9B
0x18005fb8e  mov     ecx, 57h ; 'W'; dwErrCode
0x18005fb93  call    cs:__imp_SetLastError
0x18005fb99  xor     eax, eax
0x18005fb9b  add     rsp, 20h
0x18005fb9f  pop     r14
0x18005fba1  pop     rdi
0x18005fba2  pop     rsi
0x18005fba3  pop     rbp
0x18005fba4  pop     rbx
0x18005fba5  retn
```
