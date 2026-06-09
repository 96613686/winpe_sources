# FormLongPathName

- ea: `0x18002ef7c`
- end: `0x18002f086`
- name: `FormLongPathName`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e578`
- `0x180030590`

## callees

- `0x18002ef7c`
- `0x18002f238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f063`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f073`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f063`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002effc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f01a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002effc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f01a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f059`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002efb6`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002eff2`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002efb6`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18002eff2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002efd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002efd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002efc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f041`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002efc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f041`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f04f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f04f`

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
0x18002ef7c  push    rbx
0x18002ef7e  push    rbp
0x18002ef7f  push    rsi
0x18002ef80  push    rdi
0x18002ef81  push    r14
0x18002ef83  sub     rsp, 20h
0x18002ef87  test    rcx, rcx
0x18002ef8a  jz      loc_18002F06E
0x18002ef90  xor     eax, eax
0x18002ef92  cmp     ax, [rcx]
0x18002ef95  jz      loc_18002F06E
0x18002ef9b  xor     edx, edx
0x18002ef9d  call    PrepareUnicodePathEx
0x18002efa2  mov     rbp, rax
0x18002efa5  test    rax, rax
0x18002efa8  jz      loc_18002F057
0x18002efae  xor     r8d, r8d; cchBuffer
0x18002efb1  xor     edx, edx; lpszLongPath
0x18002efb3  mov     rcx, rax; lpszShortPath
0x18002efb6  call    cs:__imp_GetLongPathNameW
0x18002efbc  mov     edi, eax
0x18002efbe  test    eax, eax
0x18002efc0  jz      short loc_18002F01A
0x18002efc2  mov     ebx, edi
0x18002efc4  add     rbx, rbx
0x18002efc7  call    cs:__imp_GetProcessHeap
0x18002efcd  mov     r8, rbx; dwBytes
0x18002efd0  mov     edx, 8; dwFlags
0x18002efd5  mov     rcx, rax; hHeap
0x18002efd8  call    cs:__imp_HeapAlloc
0x18002efde  mov     rsi, rax
0x18002efe1  test    rax, rax
0x18002efe4  jz      short loc_18002F007
0x18002efe6  mov     r8d, edi; cchBuffer
0x18002efe9  mov     rdx, rax; lpszLongPath
0x18002efec  mov     rcx, rbp; lpszShortPath
0x18002efef  xor     r14d, r14d
0x18002eff2  call    cs:__imp_GetLongPathNameW
0x18002eff8  test    eax, eax
0x18002effa  jnz     short loc_18002F00D
0x18002effc  call    cs:__imp_GetLastError
0x18002f002  mov     r14d, eax
0x18002f005  jmp     short loc_18002F00D
0x18002f007  mov     r14d, 0Eh
0x18002f00d  mov     rax, rsi
0x18002f010  test    rsi, rsi
0x18002f013  jz      short loc_18002F027
0x18002f015  mov     rbx, rsi
0x18002f018  jmp     short loc_18002F02A
0x18002f01a  call    cs:__imp_GetLastError
0x18002f020  xor     esi, esi
0x18002f022  mov     r14d, eax
0x18002f025  xor     eax, eax
0x18002f027  mov     rbx, rbp
0x18002f02a  xor     edi, edi
0x18002f02c  test    rsi, rsi
0x18002f02f  cmovnz  edi, r14d
0x18002f033  xor     esi, esi
0x18002f035  test    rax, rax
0x18002f038  cmovnz  rsi, rbp
0x18002f03c  test    rsi, rsi
0x18002f03f  jz      short loc_18002F061
0x18002f041  call    cs:__imp_GetProcessHeap
0x18002f047  mov     r8, rsi; lpMem
0x18002f04a  xor     edx, edx; dwFlags
0x18002f04c  mov     rcx, rax; hHeap
0x18002f04f  call    cs:__imp_HeapFree
0x18002f055  jmp     short loc_18002F061
0x18002f057  xor     ebx, ebx
0x18002f059  call    cs:__imp_GetLastError
0x18002f05f  mov     edi, eax
0x18002f061  mov     ecx, edi; dwErrCode
0x18002f063  call    cs:__imp_SetLastError
0x18002f069  mov     rax, rbx
0x18002f06c  jmp     short loc_18002F07B
0x18002f06e  mov     ecx, 57h ; 'W'; dwErrCode
0x18002f073  call    cs:__imp_SetLastError
0x18002f079  xor     eax, eax
0x18002f07b  add     rsp, 20h
0x18002f07f  pop     r14
0x18002f081  pop     rdi
0x18002f082  pop     rsi
0x18002f083  pop     rbp
0x18002f084  pop     rbx
0x18002f085  retn
```
