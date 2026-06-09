# FormLongPathName

- ea: `0x180064b54`
- end: `0x180064ca1`
- name: `FormLongPathName`
- size: `333`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180063538`
- `0x1800666b4`
- `0x180067990`

## callees

- `0x180064b54`
- `0x180064e8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064bbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064ba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064c3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064ba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064c3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064c51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064c71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064c87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064c71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064c87`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180064b8e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180064bdc`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180064b8e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180064bdc`

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
0x180064b54  push    rbx
0x180064b56  push    rbp
0x180064b57  push    rsi
0x180064b58  push    rdi
0x180064b59  push    r14
0x180064b5b  sub     rsp, 20h
0x180064b5f  test    rcx, rcx
0x180064b62  jz      loc_180064C82
0x180064b68  xor     eax, eax
0x180064b6a  cmp     ax, [rcx]
0x180064b6d  jz      loc_180064C82
0x180064b73  xor     edx, edx
0x180064b75  call    PrepareUnicodePathEx
0x180064b7a  mov     rbp, rax
0x180064b7d  test    rax, rax
0x180064b80  jz      loc_180064C5F
0x180064b86  xor     r8d, r8d; cchBuffer
0x180064b89  xor     edx, edx; lpszLongPath
0x180064b8b  mov     rcx, rax; lpszShortPath
0x180064b8e  call    cs:__imp_GetLongPathNameW
0x180064b95  nop     dword ptr [rax+rax+00h]
0x180064b9a  mov     edi, eax
0x180064b9c  test    eax, eax
0x180064b9e  jz      short loc_180064C10
0x180064ba0  mov     ebx, edi
0x180064ba2  add     rbx, rbx
0x180064ba5  call    cs:__imp_GetProcessHeap
0x180064bac  nop     dword ptr [rax+rax+00h]
0x180064bb1  mov     r8, rbx; dwBytes
0x180064bb4  mov     edx, 8; dwFlags
0x180064bb9  mov     rcx, rax; hHeap
0x180064bbc  call    cs:__imp_HeapAlloc
0x180064bc3  nop     dword ptr [rax+rax+00h]
0x180064bc8  mov     rsi, rax
0x180064bcb  test    rax, rax
0x180064bce  jz      short loc_180064BFD
0x180064bd0  mov     r8d, edi; cchBuffer
0x180064bd3  mov     rdx, rax; lpszLongPath
0x180064bd6  mov     rcx, rbp; lpszShortPath
0x180064bd9  xor     r14d, r14d
0x180064bdc  call    cs:__imp_GetLongPathNameW
0x180064be3  nop     dword ptr [rax+rax+00h]
0x180064be8  test    eax, eax
0x180064bea  jnz     short loc_180064C03
0x180064bec  call    cs:__imp_GetLastError
0x180064bf3  nop     dword ptr [rax+rax+00h]
0x180064bf8  mov     r14d, eax
0x180064bfb  jmp     short loc_180064C03
0x180064bfd  mov     r14d, 0Eh
0x180064c03  mov     rax, rsi
0x180064c06  test    rsi, rsi
0x180064c09  jz      short loc_180064C23
0x180064c0b  mov     rbx, rsi
0x180064c0e  jmp     short loc_180064C26
0x180064c10  call    cs:__imp_GetLastError
0x180064c17  nop     dword ptr [rax+rax+00h]
0x180064c1c  xor     esi, esi
0x180064c1e  mov     r14d, eax
0x180064c21  xor     eax, eax
0x180064c23  mov     rbx, rbp
0x180064c26  xor     edi, edi
0x180064c28  test    rsi, rsi
0x180064c2b  cmovnz  edi, r14d
0x180064c2f  xor     esi, esi
0x180064c31  test    rax, rax
0x180064c34  cmovnz  rsi, rbp
0x180064c38  test    rsi, rsi
0x180064c3b  jz      short loc_180064C6F
0x180064c3d  call    cs:__imp_GetProcessHeap
0x180064c44  nop     dword ptr [rax+rax+00h]
0x180064c49  mov     r8, rsi; lpMem
0x180064c4c  xor     edx, edx; dwFlags
0x180064c4e  mov     rcx, rax; hHeap
0x180064c51  call    cs:__imp_HeapFree
0x180064c58  nop     dword ptr [rax+rax+00h]
0x180064c5d  jmp     short loc_180064C6F
0x180064c5f  xor     ebx, ebx
0x180064c61  call    cs:__imp_GetLastError
0x180064c68  nop     dword ptr [rax+rax+00h]
0x180064c6d  mov     edi, eax
0x180064c6f  mov     ecx, edi; dwErrCode
0x180064c71  call    cs:__imp_SetLastError
0x180064c78  nop     dword ptr [rax+rax+00h]
0x180064c7d  mov     rax, rbx
0x180064c80  jmp     short loc_180064C95
0x180064c82  mov     ecx, 57h ; 'W'; dwErrCode
0x180064c87  call    cs:__imp_SetLastError
0x180064c8e  nop     dword ptr [rax+rax+00h]
0x180064c93  xor     eax, eax
0x180064c95  add     rsp, 20h
0x180064c99  pop     r14
0x180064c9b  pop     rdi
0x180064c9c  pop     rsi
0x180064c9d  pop     rbp
0x180064c9e  pop     rbx
0x180064c9f  retn
```
