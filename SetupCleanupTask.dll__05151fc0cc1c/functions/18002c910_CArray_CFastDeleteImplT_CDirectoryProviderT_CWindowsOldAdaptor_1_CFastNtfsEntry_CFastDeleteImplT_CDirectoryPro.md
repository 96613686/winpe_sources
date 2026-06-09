# CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x18002c910`
- end: `0x18002c9f4`
- name: `?SetSize@?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18002620c`
- `0x18002b224`

## callees

- `0x180002746`
- `0x180027008`
- `0x1800293a4`
- `0x18002c910`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c957`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c957`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c949`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c99b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c9cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c949`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c99b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c9cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c9a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c9dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c9a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c9dd`

## pseudocode

```c
__int64 __fastcall CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::SetSize(
        __int64 a1,
        int a2)
{
  __int64 v2; // rsi
  void *v3; // rbx
  int v5; // ebp
  HANDLE v6; // rax
  void *v7; // rax
  unsigned int v8; // edi
  void *v9; // r14
  HANDLE ProcessHeap; // rax
  void *v11; // rax

  v2 = a2;
  v3 = 0;
  if ( *(_DWORD *)a1 == a2 )
  {
LABEL_14:
    v8 = 0;
    goto LABEL_15;
  }
  v5 = *(_DWORD *)(a1 + 4);
  if ( a2 < v5 )
    v5 = a2;
  if ( a2 <= 0 )
  {
LABEL_9:
    v9 = *(void **)(a1 + 8);
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
    v11 = 0;
    if ( v3 )
      v11 = v3;
    *(_QWORD *)(a1 + 8) = v11;
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)a1 = v2;
    goto LABEL_14;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = GetProcessHeap();
  v7 = HeapAlloc(v6, 0, 8 * v2);
  v3 = v7;
  if ( v7 )
  {
    if ( v5 )
      memcpy_0(v7, *(const void **)(a1 + 8), 8LL * v5);
    goto LABEL_9;
  }
  v8 = -2147024882;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  return v8;
}

```

## disassembly

```asm
0x18002c910  push    rbx
0x18002c912  push    rbp
0x18002c913  push    rsi
0x18002c914  push    rdi
0x18002c915  push    r12
0x18002c917  push    r14
0x18002c919  push    r15
0x18002c91b  sub     rsp, 20h
0x18002c91f  movsxd  rsi, edx
0x18002c922  xor     ebx, ebx
0x18002c924  mov     rdi, rcx
0x18002c927  cmp     [rcx], esi
0x18002c929  jz      loc_18002C9C1
0x18002c92f  mov     ebp, [rcx+4]
0x18002c932  cmp     esi, ebp
0x18002c934  cmovl   ebp, esi
0x18002c937  test    edx, edx
0x18002c939  jle     short loc_18002C98A
0x18002c93b  xor     ecx, ecx
0x18002c93d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002c942  mov     rbx, rsi
0x18002c945  shl     rbx, 3
0x18002c949  call    cs:__imp_GetProcessHeap
0x18002c94f  mov     r8, rbx; dwBytes
0x18002c952  xor     edx, edx; dwFlags
0x18002c954  mov     rcx, rax; hHeap
0x18002c957  call    cs:__imp_HeapAlloc
0x18002c95d  mov     rbx, rax
0x18002c960  test    rax, rax
0x18002c963  jnz     short loc_18002C973
0x18002c965  mov     edi, 8007000Eh
0x18002c96a  mov     ecx, edi
0x18002c96c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002c971  jmp     short loc_18002C9C3
0x18002c973  test    ebp, ebp
0x18002c975  jz      short loc_18002C98A
0x18002c977  mov     rdx, [rdi+8]; Src
0x18002c97b  mov     rcx, rax; void *
0x18002c97e  movsxd  r8, ebp
0x18002c981  shl     r8, 3; Size
0x18002c985  call    memcpy_0
0x18002c98a  mov     r14, [rdi+8]
0x18002c98e  mov     r15, rbx
0x18002c991  mov     r12, rbx
0x18002c994  xor     ebx, ebx
0x18002c996  test    r14, r14
0x18002c999  jz      short loc_18002C9AF
0x18002c99b  call    cs:__imp_GetProcessHeap
0x18002c9a1  mov     r8, r14; lpMem
0x18002c9a4  xor     edx, edx; dwFlags
0x18002c9a6  mov     rcx, rax; hHeap
0x18002c9a9  call    cs:__imp_HeapFree
0x18002c9af  xor     eax, eax
0x18002c9b1  test    r15, r15
0x18002c9b4  cmovnz  rax, r12
0x18002c9b8  mov     [rdi+8], rax
0x18002c9bc  mov     [rdi+4], ebp
0x18002c9bf  mov     [rdi], esi
0x18002c9c1  xor     edi, edi
0x18002c9c3  mov     ecx, edi
0x18002c9c5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002c9ca  test    rbx, rbx
0x18002c9cd  jz      short loc_18002C9E3
0x18002c9cf  call    cs:__imp_GetProcessHeap
0x18002c9d5  mov     r8, rbx; lpMem
0x18002c9d8  xor     edx, edx; dwFlags
0x18002c9da  mov     rcx, rax; hHeap
0x18002c9dd  call    cs:__imp_HeapFree
0x18002c9e3  mov     eax, edi
0x18002c9e5  add     rsp, 20h
0x18002c9e9  pop     r15
0x18002c9eb  pop     r14
0x18002c9ed  pop     r12
0x18002c9ef  pop     rdi
0x18002c9f0  pop     rsi
0x18002c9f1  pop     rbp
0x18002c9f2  pop     rbx
0x18002c9f3  retn
```
