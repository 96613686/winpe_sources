# FormLongPathName

- ea: `0x180066ffc`
- end: `0x180067106`
- name: `FormLongPathName`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180065870`
- `0x180066484`
- `0x180068ae8`

## callees

- `0x180066ffc`
- `0x1800673b0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800670e3`
- `KERNEL32!SetLastError` at `0x1800670f3`
- `KERNEL32!SetLastError` at `0x1800670e3`
- `KERNEL32!SetLastError` at `0x1800670f3`
- `KERNEL32!GetLastError` at `0x18006707c`
- `KERNEL32!GetLastError` at `0x18006709a`
- `KERNEL32!GetLastError` at `0x1800670d9`
- `KERNEL32!GetLastError` at `0x18006707c`
- `KERNEL32!GetLastError` at `0x18006709a`
- `KERNEL32!GetLastError` at `0x1800670d9`
- `KERNEL32!HeapFree` at `0x1800670cf`
- `KERNEL32!HeapFree` at `0x1800670cf`
- `KERNEL32!HeapAlloc` at `0x180067058`
- `KERNEL32!HeapAlloc` at `0x180067058`
- `KERNEL32!GetProcessHeap` at `0x180067047`
- `KERNEL32!GetProcessHeap` at `0x1800670c1`
- `KERNEL32!GetProcessHeap` at `0x180067047`
- `KERNEL32!GetProcessHeap` at `0x1800670c1`
- `KERNEL32!GetLongPathNameW` at `0x180067036`
- `KERNEL32!GetLongPathNameW` at `0x180067072`
- `KERNEL32!GetLongPathNameW` at `0x180067036`
- `KERNEL32!GetLongPathNameW` at `0x180067072`

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
0x180066ffc  push    rbx
0x180066ffe  push    rbp
0x180066fff  push    rsi
0x180067000  push    rdi
0x180067001  push    r14
0x180067003  sub     rsp, 20h
0x180067007  test    rcx, rcx
0x18006700a  jz      loc_1800670EE
0x180067010  xor     eax, eax
0x180067012  cmp     ax, [rcx]
0x180067015  jz      loc_1800670EE
0x18006701b  xor     edx, edx
0x18006701d  call    PrepareUnicodePathEx
0x180067022  mov     rbp, rax
0x180067025  test    rax, rax
0x180067028  jz      loc_1800670D7
0x18006702e  xor     r8d, r8d; cchBuffer
0x180067031  xor     edx, edx; lpszLongPath
0x180067033  mov     rcx, rax; lpszShortPath
0x180067036  call    cs:__imp_GetLongPathNameW
0x18006703c  mov     edi, eax
0x18006703e  test    eax, eax
0x180067040  jz      short loc_18006709A
0x180067042  mov     ebx, edi
0x180067044  add     rbx, rbx
0x180067047  call    cs:__imp_GetProcessHeap
0x18006704d  mov     r8, rbx; dwBytes
0x180067050  mov     edx, 8; dwFlags
0x180067055  mov     rcx, rax; hHeap
0x180067058  call    cs:__imp_HeapAlloc
0x18006705e  mov     rsi, rax
0x180067061  test    rax, rax
0x180067064  jz      short loc_180067087
0x180067066  mov     r8d, edi; cchBuffer
0x180067069  mov     rdx, rax; lpszLongPath
0x18006706c  mov     rcx, rbp; lpszShortPath
0x18006706f  xor     r14d, r14d
0x180067072  call    cs:__imp_GetLongPathNameW
0x180067078  test    eax, eax
0x18006707a  jnz     short loc_18006708D
0x18006707c  call    cs:__imp_GetLastError
0x180067082  mov     r14d, eax
0x180067085  jmp     short loc_18006708D
0x180067087  mov     r14d, 0Eh
0x18006708d  mov     rax, rsi
0x180067090  test    rsi, rsi
0x180067093  jz      short loc_1800670A7
0x180067095  mov     rbx, rsi
0x180067098  jmp     short loc_1800670AA
0x18006709a  call    cs:__imp_GetLastError
0x1800670a0  xor     esi, esi
0x1800670a2  mov     r14d, eax
0x1800670a5  xor     eax, eax
0x1800670a7  mov     rbx, rbp
0x1800670aa  xor     edi, edi
0x1800670ac  test    rsi, rsi
0x1800670af  cmovnz  edi, r14d
0x1800670b3  xor     esi, esi
0x1800670b5  test    rax, rax
0x1800670b8  cmovnz  rsi, rbp
0x1800670bc  test    rsi, rsi
0x1800670bf  jz      short loc_1800670E1
0x1800670c1  call    cs:__imp_GetProcessHeap
0x1800670c7  mov     r8, rsi; lpMem
0x1800670ca  xor     edx, edx; dwFlags
0x1800670cc  mov     rcx, rax; hHeap
0x1800670cf  call    cs:__imp_HeapFree
0x1800670d5  jmp     short loc_1800670E1
0x1800670d7  xor     ebx, ebx
0x1800670d9  call    cs:__imp_GetLastError
0x1800670df  mov     edi, eax
0x1800670e1  mov     ecx, edi; dwErrCode
0x1800670e3  call    cs:__imp_SetLastError
0x1800670e9  mov     rax, rbx
0x1800670ec  jmp     short loc_1800670FB
0x1800670ee  mov     ecx, 57h ; 'W'; dwErrCode
0x1800670f3  call    cs:__imp_SetLastError
0x1800670f9  xor     eax, eax
0x1800670fb  add     rsp, 20h
0x1800670ff  pop     r14
0x180067101  pop     rdi
0x180067102  pop     rsi
0x180067103  pop     rbp
0x180067104  pop     rbx
0x180067105  retn
```
