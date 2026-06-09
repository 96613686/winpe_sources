# BuildPathMultiHr

- ea: `0x18002ec90`
- end: `0x18002edea`
- name: `BuildPathMultiHr`
- size: `346`
- prototype: `__int64 __fastcall(wchar_t **, unsigned int, const wchar_t *, const wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180031778`
- `0x180031bc4`

## callees

- `0x18002d79c`
- `0x18002ec90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ed61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ed7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002edbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ed7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002edbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ed8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002edcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ed8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002edcc`

## pseudocode

```c
__int64 __fastcall BuildPathMultiHr(wchar_t **a1, unsigned int a2, const wchar_t *a3, const wchar_t *a4, __int64 a5)
{
  unsigned int v6; // esi
  const wchar_t **v7; // r14
  wchar_t *v8; // rdi
  signed int v9; // ebx
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // eax
  const wchar_t *v13; // rdx
  __int64 v14; // rbp
  signed int v15; // eax
  bool v16; // sf
  signed int v17; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax

  if ( a1 )
  {
    v6 = 2;
    if ( a2 >= 2 )
    {
      v7 = (const wchar_t **)&a5;
      v8 = (wchar_t *)BuildPath(a3, a4);
      if ( v8 )
      {
        v9 = 0;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError < 0;
        if ( LastError > 0 )
          v11 = 1;
        if ( v11 )
        {
          v12 = GetLastError();
          v9 = v12;
          if ( v12 > 0 )
            v9 = (unsigned __int16)v12 | 0x80070000;
        }
        else
        {
          v9 = -2147467259;
        }
      }
      if ( a2 <= 2 )
      {
LABEL_27:
        if ( v9 >= 0 )
        {
          *a1 = v8;
          return (unsigned int)v9;
        }
      }
      else
      {
        while ( v9 >= 0 )
        {
          v13 = *v7++;
          v14 = BuildPath(v8, v13);
          if ( v14 )
          {
            v9 = 0;
          }
          else
          {
            v15 = GetLastError();
            v16 = v15 < 0;
            if ( v15 > 0 )
              v16 = 1;
            if ( v16 )
            {
              v17 = GetLastError();
              v9 = v17;
              if ( v17 > 0 )
                v9 = (unsigned __int16)v17 | 0x80070000;
            }
            else
            {
              v9 = -2147467259;
            }
          }
          if ( v8 )
          {
            ProcessHeap = GetProcessHeap();
            if ( HeapFree(ProcessHeap, 0, v8) )
              v8 = 0;
          }
          ++v6;
          if ( v9 < 0 )
            v14 = (__int64)v8;
          v8 = (wchar_t *)v14;
          if ( v6 >= a2 )
            goto LABEL_27;
        }
      }
      if ( v8 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v8);
      }
      return (unsigned int)v9;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002ec90  mov     rax, rsp
0x18002ec93  mov     [rax+10h], edx
0x18002ec96  mov     [rax+18h], r8
0x18002ec9a  mov     [rax+20h], r9
0x18002ec9e  push    rbx
0x18002ec9f  push    rbp
0x18002eca0  push    rsi
0x18002eca1  push    rdi
0x18002eca2  push    r12
0x18002eca4  push    r14
0x18002eca6  push    r15
0x18002eca8  sub     rsp, 30h
0x18002ecac  mov     r15, rcx
0x18002ecaf  mov     qword ptr [rax-48h], 0
0x18002ecb7  lea     rcx, [rax+18h]
0x18002ecbb  test    r15, r15
0x18002ecbe  jz      loc_18002EDD6
0x18002ecc4  mov     esi, 2
0x18002ecc9  cmp     edx, esi
0x18002eccb  jb      loc_18002EDD6
0x18002ecd1  lea     r14, [rcx+10h]
0x18002ecd5  mov     rcx, [rcx]; pszSrc
0x18002ecd8  mov     rdx, [r14-8]; STRSAFE_PCNZWCH
0x18002ecdc  call    BuildPath
0x18002ece1  mov     rdi, rax
0x18002ece4  mov     r12d, 80070000h
0x18002ecea  test    rax, rax
0x18002eced  jz      short loc_18002ECF3
0x18002ecef  xor     ebx, ebx
0x18002ecf1  jmp     short loc_18002ED20
0x18002ecf3  call    cs:__imp_GetLastError
0x18002ecf9  test    eax, eax
0x18002ecfb  jle     short loc_18002ED05
0x18002ecfd  movzx   eax, ax
0x18002ed00  or      eax, r12d
0x18002ed03  test    eax, eax
0x18002ed05  jns     short loc_18002ED1B
0x18002ed07  call    cs:__imp_GetLastError
0x18002ed0d  mov     ebx, eax
0x18002ed0f  test    eax, eax
0x18002ed11  jle     short loc_18002ED20
0x18002ed13  movzx   ebx, ax
0x18002ed16  or      ebx, r12d
0x18002ed19  jmp     short loc_18002ED20
0x18002ed1b  mov     ebx, 80004005h
0x18002ed20  cmp     [rsp+68h+arg_8], esi
0x18002ed24  jbe     loc_18002EDB0
0x18002ed2a  test    ebx, ebx
0x18002ed2c  js      loc_18002EDB9
0x18002ed32  mov     rdx, [r14]; STRSAFE_PCNZWCH
0x18002ed35  add     r14, 8
0x18002ed39  mov     rcx, rdi; pszSrc
0x18002ed3c  call    BuildPath
0x18002ed41  mov     rbp, rax
0x18002ed44  test    rax, rax
0x18002ed47  jz      short loc_18002ED4D
0x18002ed49  xor     ebx, ebx
0x18002ed4b  jmp     short loc_18002ED7A
0x18002ed4d  call    cs:__imp_GetLastError
0x18002ed53  test    eax, eax
0x18002ed55  jle     short loc_18002ED5F
0x18002ed57  movzx   eax, ax
0x18002ed5a  or      eax, r12d
0x18002ed5d  test    eax, eax
0x18002ed5f  jns     short loc_18002ED75
0x18002ed61  call    cs:__imp_GetLastError
0x18002ed67  mov     ebx, eax
0x18002ed69  test    eax, eax
0x18002ed6b  jle     short loc_18002ED7A
0x18002ed6d  movzx   ebx, ax
0x18002ed70  or      ebx, r12d
0x18002ed73  jmp     short loc_18002ED7A
0x18002ed75  mov     ebx, 80004005h
0x18002ed7a  test    rdi, rdi
0x18002ed7d  jz      short loc_18002ED9B
0x18002ed7f  call    cs:__imp_GetProcessHeap
0x18002ed85  mov     r8, rdi; lpMem
0x18002ed88  xor     edx, edx; dwFlags
0x18002ed8a  mov     rcx, rax; hHeap
0x18002ed8d  call    cs:__imp_HeapFree
0x18002ed93  xor     ecx, ecx
0x18002ed95  test    eax, eax
0x18002ed97  cmovnz  rdi, rcx
0x18002ed9b  inc     esi
0x18002ed9d  test    ebx, ebx
0x18002ed9f  cmovs   rbp, rdi
0x18002eda3  mov     rdi, rbp
0x18002eda6  cmp     esi, [rsp+68h+arg_8]
0x18002edaa  jb      loc_18002ED2A
0x18002edb0  test    ebx, ebx
0x18002edb2  js      short loc_18002EDB9
0x18002edb4  mov     [r15], rdi
0x18002edb7  jmp     short loc_18002EDD2
0x18002edb9  test    rdi, rdi
0x18002edbc  jz      short loc_18002EDD2
0x18002edbe  call    cs:__imp_GetProcessHeap
0x18002edc4  mov     r8, rdi; lpMem
0x18002edc7  xor     edx, edx; dwFlags
0x18002edc9  mov     rcx, rax; hHeap
0x18002edcc  call    cs:__imp_HeapFree
0x18002edd2  mov     eax, ebx
0x18002edd4  jmp     short loc_18002EDDB
0x18002edd6  mov     eax, 80070057h
0x18002eddb  add     rsp, 30h
0x18002eddf  pop     r15
0x18002ede1  pop     r14
0x18002ede3  pop     r12
0x18002ede5  pop     rdi
0x18002ede6  pop     rsi
0x18002ede7  pop     rbp
0x18002ede8  pop     rbx
0x18002ede9  retn
```
