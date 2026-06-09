# FormLongPathName

- ea: `0x180006578`
- end: `0x180006682`
- name: `FormLongPathName`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c48`

## callees

- `0x180006578`
- `0x1800067f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800065f8`
- `KERNEL32!GetLastError` at `0x180006616`
- `KERNEL32!GetLastError` at `0x180006655`
- `KERNEL32!GetLastError` at `0x1800065f8`
- `KERNEL32!GetLastError` at `0x180006616`
- `KERNEL32!GetLastError` at `0x180006655`
- `KERNEL32!HeapFree` at `0x18000664b`
- `KERNEL32!HeapFree` at `0x18000664b`
- `KERNEL32!HeapAlloc` at `0x1800065d4`
- `KERNEL32!HeapAlloc` at `0x1800065d4`
- `KERNEL32!GetProcessHeap` at `0x1800065c3`
- `KERNEL32!GetProcessHeap` at `0x18000663d`
- `KERNEL32!GetProcessHeap` at `0x1800065c3`
- `KERNEL32!GetProcessHeap` at `0x18000663d`
- `KERNEL32!SetLastError` at `0x18000665f`
- `KERNEL32!SetLastError` at `0x18000666f`
- `KERNEL32!SetLastError` at `0x18000665f`
- `KERNEL32!SetLastError` at `0x18000666f`
- `KERNEL32!GetLongPathNameW` at `0x1800065b2`
- `KERNEL32!GetLongPathNameW` at `0x1800065ee`
- `KERNEL32!GetLongPathNameW` at `0x1800065b2`
- `KERNEL32!GetLongPathNameW` at `0x1800065ee`

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
0x180006578  push    rbx
0x18000657a  push    rbp
0x18000657b  push    rsi
0x18000657c  push    rdi
0x18000657d  push    r14
0x18000657f  sub     rsp, 20h
0x180006583  test    rcx, rcx
0x180006586  jz      loc_18000666A
0x18000658c  xor     eax, eax
0x18000658e  cmp     ax, [rcx]
0x180006591  jz      loc_18000666A
0x180006597  xor     edx, edx
0x180006599  call    PrepareUnicodePathEx
0x18000659e  mov     rbp, rax
0x1800065a1  test    rax, rax
0x1800065a4  jz      loc_180006653
0x1800065aa  xor     r8d, r8d; cchBuffer
0x1800065ad  xor     edx, edx; lpszLongPath
0x1800065af  mov     rcx, rax; lpszShortPath
0x1800065b2  call    cs:__imp_GetLongPathNameW
0x1800065b8  mov     edi, eax
0x1800065ba  test    eax, eax
0x1800065bc  jz      short loc_180006616
0x1800065be  mov     ebx, edi
0x1800065c0  add     rbx, rbx
0x1800065c3  call    cs:__imp_GetProcessHeap
0x1800065c9  mov     r8, rbx; dwBytes
0x1800065cc  mov     edx, 8; dwFlags
0x1800065d1  mov     rcx, rax; hHeap
0x1800065d4  call    cs:__imp_HeapAlloc
0x1800065da  mov     rsi, rax
0x1800065dd  test    rax, rax
0x1800065e0  jz      short loc_180006603
0x1800065e2  mov     r8d, edi; cchBuffer
0x1800065e5  mov     rdx, rax; lpszLongPath
0x1800065e8  mov     rcx, rbp; lpszShortPath
0x1800065eb  xor     r14d, r14d
0x1800065ee  call    cs:__imp_GetLongPathNameW
0x1800065f4  test    eax, eax
0x1800065f6  jnz     short loc_180006609
0x1800065f8  call    cs:__imp_GetLastError
0x1800065fe  mov     r14d, eax
0x180006601  jmp     short loc_180006609
0x180006603  mov     r14d, 0Eh
0x180006609  mov     rax, rsi
0x18000660c  test    rsi, rsi
0x18000660f  jz      short loc_180006623
0x180006611  mov     rbx, rsi
0x180006614  jmp     short loc_180006626
0x180006616  call    cs:__imp_GetLastError
0x18000661c  xor     esi, esi
0x18000661e  mov     r14d, eax
0x180006621  xor     eax, eax
0x180006623  mov     rbx, rbp
0x180006626  xor     edi, edi
0x180006628  test    rsi, rsi
0x18000662b  cmovnz  edi, r14d
0x18000662f  xor     esi, esi
0x180006631  test    rax, rax
0x180006634  cmovnz  rsi, rbp
0x180006638  test    rsi, rsi
0x18000663b  jz      short loc_18000665D
0x18000663d  call    cs:__imp_GetProcessHeap
0x180006643  mov     r8, rsi; lpMem
0x180006646  xor     edx, edx; dwFlags
0x180006648  mov     rcx, rax; hHeap
0x18000664b  call    cs:__imp_HeapFree
0x180006651  jmp     short loc_18000665D
0x180006653  xor     ebx, ebx
0x180006655  call    cs:__imp_GetLastError
0x18000665b  mov     edi, eax
0x18000665d  mov     ecx, edi; dwErrCode
0x18000665f  call    cs:__imp_SetLastError
0x180006665  mov     rax, rbx
0x180006668  jmp     short loc_180006677
0x18000666a  mov     ecx, 57h ; 'W'; dwErrCode
0x18000666f  call    cs:__imp_SetLastError
0x180006675  xor     eax, eax
0x180006677  add     rsp, 20h
0x18000667b  pop     r14
0x18000667d  pop     rdi
0x18000667e  pop     rsi
0x18000667f  pop     rbp
0x180006680  pop     rbx
0x180006681  retn
```
