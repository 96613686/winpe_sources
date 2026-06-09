# ParseUncPath

- ea: `0x18002f08c`
- end: `0x18002f231`
- name: `ParseUncPath`
- size: `421`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002f238`

## callees

- `0x180002ecf`
- `0x180002edb`
- `0x18002da5c`
- `0x18002f08c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f1f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f1f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f203`
- `ntdll!RtlAllocateHeap` at `0x18002f1ad`
- `ntdll!RtlAllocateHeap` at `0x18002f1ad`

## pseudocode

```c
__int64 __fastcall ParseUncPath(STRSAFE_PCNZWCH pszSrc, _DWORD *a2, wchar_t **a3)
{
  unsigned int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  wchar_t *v11; // rax
  wchar_t *v12; // rdi
  size_t v13; // rsi
  wchar_t *v14; // rax
  wchar_t *Heap; // rax
  HANDLE ProcessHeap; // rax

  if ( !pszSrc )
    return (unsigned int)-2147024809;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( pszSrc[v8] );
  if ( v8 >= 2 && !wcsnicmp_0(pszSrc, L"\\\\", 2u) )
  {
    v9 = -1;
    do
      ++v9;
    while ( pszSrc[v9] );
    v10 = v9 >= 8 && wcsnicmp_0(pszSrc, L"\\\\?\\UNC\\", 8u) == 0;
    v11 = wcschr_0((STRSAFE_PCNZWCH)((char *)pszSrc + (v10 ? 16LL : 4LL)), 0x5Cu);
    if ( !v11 )
      return (unsigned int)-2147024883;
    v12 = 0;
    v13 = -1;
    do
      ++v13;
    while ( pszSrc[v13] );
    v14 = wcschr_0(v11 + 1, 0x5Cu);
    if ( v14 )
      v13 = v14 - pszSrc;
    if ( a3 )
    {
      do
        ++v7;
      while ( pszSrc[v7] );
      if ( v13 > v7 )
      {
        v6 = -2147024809;
      }
      else
      {
        v6 = -2147024882;
        Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (v13 + 1));
        v12 = Heap;
        if ( Heap )
          v6 = StringCchCopyNW(Heap, v13 + 1, pszSrc, v13);
      }
      if ( (v6 & 0x80000000) != 0 )
      {
LABEL_29:
        if ( v12 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v12);
        }
        return v6;
      }
      *a3 = v12;
      v12 = 0;
    }
    else
    {
      v6 = 0;
    }
    if ( !a2 )
      return v6;
    *a2 = 1;
    goto LABEL_29;
  }
  v6 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  return v6;
}

```

## disassembly

```asm
0x18002f08c  push    rbx
0x18002f08e  push    rbp
0x18002f08f  push    rsi
0x18002f090  push    rdi
0x18002f091  push    r12
0x18002f093  push    r13
0x18002f095  push    r14
0x18002f097  push    r15
0x18002f099  sub     rsp, 28h
0x18002f09d  xor     r13d, r13d
0x18002f0a0  mov     r15, r8
0x18002f0a3  mov     r14, rdx
0x18002f0a6  mov     rbp, rcx
0x18002f0a9  test    rcx, rcx
0x18002f0ac  jnz     short loc_18002F0B8
0x18002f0ae  mov     ebx, 80070057h
0x18002f0b3  jmp     loc_18002F21E
0x18002f0b8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f0bc  mov     rax, rbx
0x18002f0bf  inc     rax
0x18002f0c2  cmp     [rcx+rax*2], r13w
0x18002f0c7  jnz     short loc_18002F0BF
0x18002f0c9  mov     r8d, 2; MaxCount
0x18002f0cf  cmp     rax, r8
0x18002f0d2  jb      loc_18002F20B
0x18002f0d8  lea     rdx, asc_180043684; "\\\\"
0x18002f0df  call    _wcsnicmp_0
0x18002f0e4  test    eax, eax
0x18002f0e6  jnz     loc_18002F20B
0x18002f0ec  mov     rax, rbx
0x18002f0ef  inc     rax
0x18002f0f2  cmp     [rbp+rax*2+0], r13w
0x18002f0f8  jnz     short loc_18002F0EF
0x18002f0fa  cmp     rax, 8
0x18002f0fe  jnb     short loc_18002F105
0x18002f100  mov     ecx, r13d
0x18002f103  jmp     short loc_18002F122
0x18002f105  mov     r8d, 8; MaxCount
0x18002f10b  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x18002f112  mov     rcx, rbp; String1
0x18002f115  call    _wcsnicmp_0
0x18002f11a  test    eax, eax
0x18002f11c  mov     ecx, r13d
0x18002f11f  setz    cl
0x18002f122  neg     ecx
0x18002f124  mov     r12d, 5Ch ; '\'
0x18002f12a  mov     edx, r12d; Ch
0x18002f12d  sbb     rcx, rcx
0x18002f130  and     ecx, 0Ch
0x18002f133  add     rcx, 4
0x18002f137  add     rcx, rbp; Str
0x18002f13a  call    wcschr_0
0x18002f13f  test    rax, rax
0x18002f142  jnz     short loc_18002F14E
0x18002f144  mov     ebx, 8007000Dh
0x18002f149  jmp     loc_18002F21E
0x18002f14e  mov     rdi, r13
0x18002f151  mov     rsi, rbx
0x18002f154  inc     rsi
0x18002f157  cmp     [rbp+rsi*2+0], r13w
0x18002f15d  jnz     short loc_18002F154
0x18002f15f  mov     edx, r12d; Ch
0x18002f162  lea     rcx, [rax+2]; Str
0x18002f166  call    wcschr_0
0x18002f16b  test    rax, rax
0x18002f16e  jz      short loc_18002F179
0x18002f170  mov     rsi, rax
0x18002f173  sub     rsi, rbp
0x18002f176  sar     rsi, 1
0x18002f179  test    r15, r15
0x18002f17c  jz      short loc_18002F1E1
0x18002f17e  inc     rbx
0x18002f181  cmp     [rbp+rbx*2+0], r13w
0x18002f187  jnz     short loc_18002F17E
0x18002f189  cmp     rsi, rbx
0x18002f18c  ja      short loc_18002F1D0
0x18002f18e  mov     rcx, gs:60h
0x18002f197  lea     r12, [rsi+1]
0x18002f19b  lea     r8, [r12+r12]; Size
0x18002f19f  mov     edx, 8; Flags
0x18002f1a4  mov     ebx, 8007000Eh
0x18002f1a9  mov     rcx, [rcx+30h]; HeapHandle
0x18002f1ad  call    cs:__imp_RtlAllocateHeap
0x18002f1b3  mov     rdi, rax
0x18002f1b6  test    rax, rax
0x18002f1b9  jz      short loc_18002F1D5
0x18002f1bb  mov     r9, rsi; cchToCopy
0x18002f1be  mov     r8, rbp; pszSrc
0x18002f1c1  mov     rdx, r12; cchDest
0x18002f1c4  mov     rcx, rax; pszDest
0x18002f1c7  call    StringCchCopyNW
0x18002f1cc  mov     ebx, eax
0x18002f1ce  jmp     short loc_18002F1D5
0x18002f1d0  mov     ebx, 80070057h
0x18002f1d5  test    ebx, ebx
0x18002f1d7  js      short loc_18002F1F0
0x18002f1d9  mov     [r15], rdi
0x18002f1dc  mov     rdi, r13
0x18002f1df  jmp     short loc_18002F1E4
0x18002f1e1  mov     ebx, r13d
0x18002f1e4  test    r14, r14
0x18002f1e7  jz      short loc_18002F21E
0x18002f1e9  mov     dword ptr [r14], 1
0x18002f1f0  test    rdi, rdi
0x18002f1f3  jz      short loc_18002F21E
0x18002f1f5  call    cs:__imp_GetProcessHeap
0x18002f1fb  mov     r8, rdi; lpMem
0x18002f1fe  xor     edx, edx; dwFlags
0x18002f200  mov     rcx, rax; hHeap
0x18002f203  call    cs:__imp_HeapFree
0x18002f209  jmp     short loc_18002F21E
0x18002f20b  mov     ebx, r13d
0x18002f20e  test    r14, r14
0x18002f211  jz      short loc_18002F216
0x18002f213  mov     [r14], r13d
0x18002f216  test    r15, r15
0x18002f219  jz      short loc_18002F21E
0x18002f21b  mov     [r15], r13
0x18002f21e  mov     eax, ebx
0x18002f220  add     rsp, 28h
0x18002f224  pop     r15
0x18002f226  pop     r14
0x18002f228  pop     r13
0x18002f22a  pop     r12
0x18002f22c  pop     rdi
0x18002f22d  pop     rsi
0x18002f22e  pop     rbp
0x18002f22f  pop     rbx
0x18002f230  retn
```
