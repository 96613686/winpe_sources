# MemGetAnsiMuiSafePath

- ea: `0x18000c708`
- end: `0x18000c818`
- name: `MemGetAnsiMuiSafePath`
- size: `272`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ca5c`

## callees

- `0x180002eb8`
- `0x180002fb8`
- `0x18000c708`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000c73d`
- `KERNEL32!HeapAlloc` at `0x18000c7cd`
- `KERNEL32!HeapAlloc` at `0x18000c73d`
- `KERNEL32!HeapAlloc` at `0x18000c7cd`
- `KERNEL32!GetProcessHeap` at `0x18000c72f`
- `KERNEL32!GetProcessHeap` at `0x18000c766`
- `KERNEL32!GetProcessHeap` at `0x18000c7be`
- `KERNEL32!GetProcessHeap` at `0x18000c7fc`
- `KERNEL32!GetProcessHeap` at `0x18000c72f`
- `KERNEL32!GetProcessHeap` at `0x18000c766`
- `KERNEL32!GetProcessHeap` at `0x18000c7be`
- `KERNEL32!GetProcessHeap` at `0x18000c7fc`
- `KERNEL32!HeapFree` at `0x18000c774`
- `KERNEL32!HeapFree` at `0x18000c80a`
- `KERNEL32!HeapFree` at `0x18000c774`
- `KERNEL32!HeapFree` at `0x18000c80a`
- `KERNEL32!GetShortPathNameW` at `0x18000c71b`
- `KERNEL32!GetShortPathNameW` at `0x18000c754`
- `KERNEL32!GetShortPathNameW` at `0x18000c71b`
- `KERNEL32!GetShortPathNameW` at `0x18000c754`

## pseudocode

```c
__int64 __fastcall MemGetAnsiMuiSafePath(unsigned __int16 *a1)
{
  DWORD ShortPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  WCHAR *v5; // rdi
  DWORD v6; // eax
  HANDLE v7; // rax
  unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  HANDLE v12; // rax
  unsigned __int16 *v13; // rax
  __int64 v14; // rbx
  HANDLE v15; // rax

  ShortPathNameW = GetShortPathNameW(a1, 0, 0);
  if ( ShortPathNameW )
  {
    ProcessHeap = GetProcessHeap();
    v4 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 2LL * ShortPathNameW);
    v5 = v4;
    if ( !v4 )
      return 0;
    v6 = GetShortPathNameW(a1, v4, ShortPathNameW);
    if ( !v6 || v6 >= ShortPathNameW )
    {
LABEL_5:
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v5);
      return 0;
    }
  }
  else
  {
    if ( !a1 )
      return 0;
    v9 = a1;
    v10 = 0x7FFFFFFF;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v10;
    }
    while ( v10 );
    if ( !v10 )
      return 0;
    v11 = ((0x7FFFFFFF - v10) & -(__int64)(v10 != 0)) + 1;
    v12 = GetProcessHeap();
    v13 = (unsigned __int16 *)HeapAlloc(v12, 0, (unsigned int)(2 * v11));
    v5 = v13;
    if ( !v13 )
      return 0;
    if ( (int)StringCchCopyW(v13, v11, a1) < 0 )
      goto LABEL_5;
  }
  v14 = ConvertUnicodeToANSI(v5);
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v5);
  return v14;
}

```

## disassembly

```asm
0x18000c708  push    rbx
0x18000c70a  push    rbp
0x18000c70b  push    rsi
0x18000c70c  push    rdi
0x18000c70d  push    r14
0x18000c70f  sub     rsp, 20h
0x18000c713  xor     r8d, r8d; cchBuffer
0x18000c716  xor     edx, edx; lpszShortPath
0x18000c718  mov     rsi, rcx
0x18000c71b  call    cs:__imp_GetShortPathNameW
0x18000c721  xor     r14d, r14d
0x18000c724  mov     ebp, eax
0x18000c726  test    eax, eax
0x18000c728  jz      short loc_18000C787
0x18000c72a  mov     ebx, ebp
0x18000c72c  add     rbx, rbx
0x18000c72f  call    cs:__imp_GetProcessHeap
0x18000c735  mov     r8, rbx; dwBytes
0x18000c738  xor     edx, edx; dwFlags
0x18000c73a  mov     rcx, rax; hHeap
0x18000c73d  call    cs:__imp_HeapAlloc
0x18000c743  mov     rdi, rax
0x18000c746  test    rax, rax
0x18000c749  jz      short loc_18000C77A
0x18000c74b  mov     r8d, ebp; cchBuffer
0x18000c74e  mov     rdx, rax; lpszShortPath
0x18000c751  mov     rcx, rsi; lpszLongPath
0x18000c754  call    cs:__imp_GetShortPathNameW
0x18000c75a  test    eax, eax
0x18000c75c  jz      short loc_18000C766
0x18000c75e  cmp     eax, ebp
0x18000c760  jb      loc_18000C7F1
0x18000c766  call    cs:__imp_GetProcessHeap
0x18000c76c  mov     r8, rdi; lpMem
0x18000c76f  xor     edx, edx; dwFlags
0x18000c771  mov     rcx, rax; hHeap
0x18000c774  call    cs:__imp_HeapFree
0x18000c77a  xor     eax, eax
0x18000c77c  add     rsp, 20h
0x18000c780  pop     r14
0x18000c782  pop     rdi
0x18000c783  pop     rsi
0x18000c784  pop     rbp
0x18000c785  pop     rbx
0x18000c786  retn
0x18000c787  test    rsi, rsi
0x18000c78a  jz      short loc_18000C77A
0x18000c78c  mov     edx, 7FFFFFFFh
0x18000c791  mov     rax, rsi
0x18000c794  mov     ecx, edx
0x18000c796  cmp     [rax], r14w
0x18000c79a  jz      short loc_18000C7A6
0x18000c79c  add     rax, 2
0x18000c7a0  sub     rcx, 1
0x18000c7a4  jnz     short loc_18000C796
0x18000c7a6  sub     rdx, rcx
0x18000c7a9  mov     rax, rcx
0x18000c7ac  neg     rax
0x18000c7af  sbb     r8, r8
0x18000c7b2  and     r8, rdx
0x18000c7b5  test    rcx, rcx
0x18000c7b8  jz      short loc_18000C77A
0x18000c7ba  lea     rbx, [r8+1]
0x18000c7be  call    cs:__imp_GetProcessHeap
0x18000c7c4  lea     r8d, [rbx+rbx]; dwBytes
0x18000c7c8  xor     edx, edx; dwFlags
0x18000c7ca  mov     rcx, rax; hHeap
0x18000c7cd  call    cs:__imp_HeapAlloc
0x18000c7d3  mov     rdi, rax
0x18000c7d6  test    rax, rax
0x18000c7d9  jz      short loc_18000C77A
0x18000c7db  mov     r8, rsi; unsigned __int16 *
0x18000c7de  mov     rdx, rbx; unsigned __int64
0x18000c7e1  mov     rcx, rax; unsigned __int16 *
0x18000c7e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c7e9  test    eax, eax
0x18000c7eb  js      loc_18000C766
0x18000c7f1  mov     rcx, rdi; lpWideCharStr
0x18000c7f4  call    ConvertUnicodeToANSI
0x18000c7f9  mov     rbx, rax
0x18000c7fc  call    cs:__imp_GetProcessHeap
0x18000c802  mov     r8, rdi; lpMem
0x18000c805  xor     edx, edx; dwFlags
0x18000c807  mov     rcx, rax; hHeap
0x18000c80a  call    cs:__imp_HeapFree
0x18000c810  mov     rax, rbx
0x18000c813  jmp     loc_18000C77C
```
