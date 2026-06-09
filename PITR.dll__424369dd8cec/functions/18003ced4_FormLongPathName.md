# FormLongPathName

- ea: `0x18003ced4`
- end: `0x18003cfde`
- name: `FormLongPathName`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18003b094`
- `0x18003bfb0`
- `0x18003e3e0`

## callees

- `0x18003ced4`
- `0x18003d238`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003cf0e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003cf4a`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003cf0e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003cf4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cf1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cf99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cf1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cf99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cf30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cf30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cfa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cfa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cfbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cfcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cfbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cfcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfb1`

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
0x18003ced4  push    rbx
0x18003ced6  push    rbp
0x18003ced7  push    rsi
0x18003ced8  push    rdi
0x18003ced9  push    r14
0x18003cedb  sub     rsp, 20h
0x18003cedf  test    rcx, rcx
0x18003cee2  jz      loc_18003CFC6
0x18003cee8  xor     eax, eax
0x18003ceea  cmp     ax, [rcx]
0x18003ceed  jz      loc_18003CFC6
0x18003cef3  xor     edx, edx
0x18003cef5  call    PrepareUnicodePathEx
0x18003cefa  mov     rbp, rax
0x18003cefd  test    rax, rax
0x18003cf00  jz      loc_18003CFAF
0x18003cf06  xor     r8d, r8d; cchBuffer
0x18003cf09  xor     edx, edx; lpszLongPath
0x18003cf0b  mov     rcx, rax; lpszShortPath
0x18003cf0e  call    cs:__imp_GetLongPathNameW
0x18003cf14  mov     edi, eax
0x18003cf16  test    eax, eax
0x18003cf18  jz      short loc_18003CF72
0x18003cf1a  mov     ebx, edi
0x18003cf1c  add     rbx, rbx
0x18003cf1f  call    cs:__imp_GetProcessHeap
0x18003cf25  mov     r8, rbx; dwBytes
0x18003cf28  mov     edx, 8; dwFlags
0x18003cf2d  mov     rcx, rax; hHeap
0x18003cf30  call    cs:__imp_HeapAlloc
0x18003cf36  mov     rsi, rax
0x18003cf39  test    rax, rax
0x18003cf3c  jz      short loc_18003CF5F
0x18003cf3e  mov     r8d, edi; cchBuffer
0x18003cf41  mov     rdx, rax; lpszLongPath
0x18003cf44  mov     rcx, rbp; lpszShortPath
0x18003cf47  xor     r14d, r14d
0x18003cf4a  call    cs:__imp_GetLongPathNameW
0x18003cf50  test    eax, eax
0x18003cf52  jnz     short loc_18003CF65
0x18003cf54  call    cs:__imp_GetLastError
0x18003cf5a  mov     r14d, eax
0x18003cf5d  jmp     short loc_18003CF65
0x18003cf5f  mov     r14d, 0Eh
0x18003cf65  mov     rax, rsi
0x18003cf68  test    rsi, rsi
0x18003cf6b  jz      short loc_18003CF7F
0x18003cf6d  mov     rbx, rsi
0x18003cf70  jmp     short loc_18003CF82
0x18003cf72  call    cs:__imp_GetLastError
0x18003cf78  xor     esi, esi
0x18003cf7a  mov     r14d, eax
0x18003cf7d  xor     eax, eax
0x18003cf7f  mov     rbx, rbp
0x18003cf82  xor     edi, edi
0x18003cf84  test    rsi, rsi
0x18003cf87  cmovnz  edi, r14d
0x18003cf8b  xor     esi, esi
0x18003cf8d  test    rax, rax
0x18003cf90  cmovnz  rsi, rbp
0x18003cf94  test    rsi, rsi
0x18003cf97  jz      short loc_18003CFB9
0x18003cf99  call    cs:__imp_GetProcessHeap
0x18003cf9f  mov     r8, rsi; lpMem
0x18003cfa2  xor     edx, edx; dwFlags
0x18003cfa4  mov     rcx, rax; hHeap
0x18003cfa7  call    cs:__imp_HeapFree
0x18003cfad  jmp     short loc_18003CFB9
0x18003cfaf  xor     ebx, ebx
0x18003cfb1  call    cs:__imp_GetLastError
0x18003cfb7  mov     edi, eax
0x18003cfb9  mov     ecx, edi; dwErrCode
0x18003cfbb  call    cs:__imp_SetLastError
0x18003cfc1  mov     rax, rbx
0x18003cfc4  jmp     short loc_18003CFD3
0x18003cfc6  mov     ecx, 57h ; 'W'; dwErrCode
0x18003cfcb  call    cs:__imp_SetLastError
0x18003cfd1  xor     eax, eax
0x18003cfd3  add     rsp, 20h
0x18003cfd7  pop     r14
0x18003cfd9  pop     rdi
0x18003cfda  pop     rsi
0x18003cfdb  pop     rbp
0x18003cfdc  pop     rbx
0x18003cfdd  retn
```
