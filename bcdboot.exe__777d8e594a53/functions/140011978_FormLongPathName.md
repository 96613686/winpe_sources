# FormLongPathName

- ea: `0x140011978`
- end: `0x140011a82`
- name: `FormLongPathName`
- size: `266`
- prototype: `const WCHAR *__fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140012810`

## callees

- `0x140011978`
- `0x140011b18`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140011a5f`
- `KERNEL32!SetLastError` at `0x140011a6f`
- `KERNEL32!SetLastError` at `0x140011a5f`
- `KERNEL32!SetLastError` at `0x140011a6f`
- `KERNEL32!GetLastError` at `0x1400119f8`
- `KERNEL32!GetLastError` at `0x140011a16`
- `KERNEL32!GetLastError` at `0x140011a55`
- `KERNEL32!GetLastError` at `0x1400119f8`
- `KERNEL32!GetLastError` at `0x140011a16`
- `KERNEL32!GetLastError` at `0x140011a55`
- `KERNEL32!HeapFree` at `0x140011a4b`
- `KERNEL32!HeapFree` at `0x140011a4b`
- `KERNEL32!HeapAlloc` at `0x1400119d4`
- `KERNEL32!HeapAlloc` at `0x1400119d4`
- `KERNEL32!GetProcessHeap` at `0x1400119c3`
- `KERNEL32!GetProcessHeap` at `0x140011a3d`
- `KERNEL32!GetProcessHeap` at `0x1400119c3`
- `KERNEL32!GetProcessHeap` at `0x140011a3d`
- `KERNEL32!GetLongPathNameW` at `0x1400119b2`
- `KERNEL32!GetLongPathNameW` at `0x1400119ee`
- `KERNEL32!GetLongPathNameW` at `0x1400119b2`
- `KERNEL32!GetLongPathNameW` at `0x1400119ee`

## pseudocode

```c
const WCHAR *__fastcall FormLongPathName(const wchar_t *a1)
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
0x140011978  push    rbx
0x14001197a  push    rbp
0x14001197b  push    rsi
0x14001197c  push    rdi
0x14001197d  push    r14
0x14001197f  sub     rsp, 20h
0x140011983  test    rcx, rcx
0x140011986  jz      loc_140011A6A
0x14001198c  xor     eax, eax
0x14001198e  cmp     ax, [rcx]
0x140011991  jz      loc_140011A6A
0x140011997  xor     edx, edx
0x140011999  call    PrepareUnicodePathEx
0x14001199e  mov     rbp, rax
0x1400119a1  test    rax, rax
0x1400119a4  jz      loc_140011A53
0x1400119aa  xor     r8d, r8d; cchBuffer
0x1400119ad  xor     edx, edx; lpszLongPath
0x1400119af  mov     rcx, rax; lpszShortPath
0x1400119b2  call    cs:__imp_GetLongPathNameW
0x1400119b8  mov     edi, eax
0x1400119ba  test    eax, eax
0x1400119bc  jz      short loc_140011A16
0x1400119be  mov     ebx, edi
0x1400119c0  add     rbx, rbx
0x1400119c3  call    cs:__imp_GetProcessHeap
0x1400119c9  mov     r8, rbx; dwBytes
0x1400119cc  mov     edx, 8; dwFlags
0x1400119d1  mov     rcx, rax; hHeap
0x1400119d4  call    cs:__imp_HeapAlloc
0x1400119da  mov     rsi, rax
0x1400119dd  test    rax, rax
0x1400119e0  jz      short loc_140011A03
0x1400119e2  mov     r8d, edi; cchBuffer
0x1400119e5  mov     rdx, rax; lpszLongPath
0x1400119e8  mov     rcx, rbp; lpszShortPath
0x1400119eb  xor     r14d, r14d
0x1400119ee  call    cs:__imp_GetLongPathNameW
0x1400119f4  test    eax, eax
0x1400119f6  jnz     short loc_140011A09
0x1400119f8  call    cs:__imp_GetLastError
0x1400119fe  mov     r14d, eax
0x140011a01  jmp     short loc_140011A09
0x140011a03  mov     r14d, 0Eh
0x140011a09  mov     rax, rsi
0x140011a0c  test    rsi, rsi
0x140011a0f  jz      short loc_140011A23
0x140011a11  mov     rbx, rsi
0x140011a14  jmp     short loc_140011A26
0x140011a16  call    cs:__imp_GetLastError
0x140011a1c  xor     esi, esi
0x140011a1e  mov     r14d, eax
0x140011a21  xor     eax, eax
0x140011a23  mov     rbx, rbp
0x140011a26  xor     edi, edi
0x140011a28  test    rsi, rsi
0x140011a2b  cmovnz  edi, r14d
0x140011a2f  xor     esi, esi
0x140011a31  test    rax, rax
0x140011a34  cmovnz  rsi, rbp
0x140011a38  test    rsi, rsi
0x140011a3b  jz      short loc_140011A5D
0x140011a3d  call    cs:__imp_GetProcessHeap
0x140011a43  mov     r8, rsi; lpMem
0x140011a46  xor     edx, edx; dwFlags
0x140011a48  mov     rcx, rax; hHeap
0x140011a4b  call    cs:__imp_HeapFree
0x140011a51  jmp     short loc_140011A5D
0x140011a53  xor     ebx, ebx
0x140011a55  call    cs:__imp_GetLastError
0x140011a5b  mov     edi, eax
0x140011a5d  mov     ecx, edi; dwErrCode
0x140011a5f  call    cs:__imp_SetLastError
0x140011a65  mov     rax, rbx
0x140011a68  jmp     short loc_140011A77
0x140011a6a  mov     ecx, 57h ; 'W'; dwErrCode
0x140011a6f  call    cs:__imp_SetLastError
0x140011a75  xor     eax, eax
0x140011a77  add     rsp, 20h
0x140011a7b  pop     r14
0x140011a7d  pop     rdi
0x140011a7e  pop     rsi
0x140011a7f  pop     rbp
0x140011a80  pop     rbx
0x140011a81  retn
```
