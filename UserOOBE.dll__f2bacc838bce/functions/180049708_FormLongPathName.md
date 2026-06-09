# FormLongPathName

- ea: `0x180049708`
- end: `0x180049812`
- name: `FormLongPathName`
- size: `266`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180048b84`

## callees

- `0x180049708`
- `0x18004997c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800497cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800497cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800497db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800497db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049764`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800497ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800497ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800497ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800497ff`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180049742`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18004977e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180049742`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18004977e`

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
0x180049708  push    rbx
0x18004970a  push    rbp
0x18004970b  push    rsi
0x18004970c  push    rdi
0x18004970d  push    r14
0x18004970f  sub     rsp, 20h
0x180049713  test    rcx, rcx
0x180049716  jz      loc_1800497FA
0x18004971c  xor     eax, eax
0x18004971e  cmp     ax, [rcx]
0x180049721  jz      loc_1800497FA
0x180049727  xor     edx, edx
0x180049729  call    PrepareUnicodePathEx
0x18004972e  mov     rbp, rax
0x180049731  test    rax, rax
0x180049734  jz      loc_1800497E3
0x18004973a  xor     r8d, r8d; cchBuffer
0x18004973d  xor     edx, edx; lpszLongPath
0x18004973f  mov     rcx, rax; lpszShortPath
0x180049742  call    cs:__imp_GetLongPathNameW
0x180049748  mov     edi, eax
0x18004974a  test    eax, eax
0x18004974c  jz      short loc_1800497A6
0x18004974e  mov     ebx, edi
0x180049750  add     rbx, rbx
0x180049753  call    cs:__imp_GetProcessHeap
0x180049759  mov     r8, rbx; dwBytes
0x18004975c  mov     edx, 8; dwFlags
0x180049761  mov     rcx, rax; hHeap
0x180049764  call    cs:__imp_HeapAlloc
0x18004976a  mov     rsi, rax
0x18004976d  test    rax, rax
0x180049770  jz      short loc_180049793
0x180049772  mov     r8d, edi; cchBuffer
0x180049775  mov     rdx, rax; lpszLongPath
0x180049778  mov     rcx, rbp; lpszShortPath
0x18004977b  xor     r14d, r14d
0x18004977e  call    cs:__imp_GetLongPathNameW
0x180049784  test    eax, eax
0x180049786  jnz     short loc_180049799
0x180049788  call    cs:__imp_GetLastError
0x18004978e  mov     r14d, eax
0x180049791  jmp     short loc_180049799
0x180049793  mov     r14d, 0Eh
0x180049799  mov     rax, rsi
0x18004979c  test    rsi, rsi
0x18004979f  jz      short loc_1800497B3
0x1800497a1  mov     rbx, rsi
0x1800497a4  jmp     short loc_1800497B6
0x1800497a6  call    cs:__imp_GetLastError
0x1800497ac  xor     esi, esi
0x1800497ae  mov     r14d, eax
0x1800497b1  xor     eax, eax
0x1800497b3  mov     rbx, rbp
0x1800497b6  xor     edi, edi
0x1800497b8  test    rsi, rsi
0x1800497bb  cmovnz  edi, r14d
0x1800497bf  xor     esi, esi
0x1800497c1  test    rax, rax
0x1800497c4  cmovnz  rsi, rbp
0x1800497c8  test    rsi, rsi
0x1800497cb  jz      short loc_1800497ED
0x1800497cd  call    cs:__imp_GetProcessHeap
0x1800497d3  mov     r8, rsi; lpMem
0x1800497d6  xor     edx, edx; dwFlags
0x1800497d8  mov     rcx, rax; hHeap
0x1800497db  call    cs:__imp_HeapFree
0x1800497e1  jmp     short loc_1800497ED
0x1800497e3  xor     ebx, ebx
0x1800497e5  call    cs:__imp_GetLastError
0x1800497eb  mov     edi, eax
0x1800497ed  mov     ecx, edi; dwErrCode
0x1800497ef  call    cs:__imp_SetLastError
0x1800497f5  mov     rax, rbx
0x1800497f8  jmp     short loc_180049807
0x1800497fa  mov     ecx, 57h ; 'W'; dwErrCode
0x1800497ff  call    cs:__imp_SetLastError
0x180049805  xor     eax, eax
0x180049807  add     rsp, 20h
0x18004980b  pop     r14
0x18004980d  pop     rdi
0x18004980e  pop     rsi
0x18004980f  pop     rbp
0x180049810  pop     rbx
0x180049811  retn
```
