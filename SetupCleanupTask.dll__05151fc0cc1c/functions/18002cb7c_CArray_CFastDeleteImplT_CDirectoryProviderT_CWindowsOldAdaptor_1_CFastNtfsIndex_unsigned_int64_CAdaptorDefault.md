# CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x18002cb7c`
- end: `0x18002cc60`
- name: `?SetSize@?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180026824`
- `0x18002aed4`

## callees

- `0x180002746`
- `0x180027008`
- `0x1800293a4`
- `0x18002cb7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cbc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cbc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cbb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cc07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cc3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cbb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cc07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cc3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cc15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cc49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cc15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cc49`

## pseudocode

```c
__int64 __fastcall CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(
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
  v7 = HeapAlloc(v6, 0, 16 * v2);
  v3 = v7;
  if ( v7 )
  {
    if ( v5 )
      memcpy_0(v7, *(const void **)(a1 + 8), 16LL * v5);
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
0x18002cb7c  push    rbx
0x18002cb7e  push    rbp
0x18002cb7f  push    rsi
0x18002cb80  push    rdi
0x18002cb81  push    r12
0x18002cb83  push    r14
0x18002cb85  push    r15
0x18002cb87  sub     rsp, 20h
0x18002cb8b  movsxd  rsi, edx
0x18002cb8e  xor     ebx, ebx
0x18002cb90  mov     rdi, rcx
0x18002cb93  cmp     [rcx], esi
0x18002cb95  jz      loc_18002CC2D
0x18002cb9b  mov     ebp, [rcx+4]
0x18002cb9e  cmp     esi, ebp
0x18002cba0  cmovl   ebp, esi
0x18002cba3  test    edx, edx
0x18002cba5  jle     short loc_18002CBF6
0x18002cba7  xor     ecx, ecx
0x18002cba9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cbae  mov     rbx, rsi
0x18002cbb1  shl     rbx, 4
0x18002cbb5  call    cs:__imp_GetProcessHeap
0x18002cbbb  mov     r8, rbx; dwBytes
0x18002cbbe  xor     edx, edx; dwFlags
0x18002cbc0  mov     rcx, rax; hHeap
0x18002cbc3  call    cs:__imp_HeapAlloc
0x18002cbc9  mov     rbx, rax
0x18002cbcc  test    rax, rax
0x18002cbcf  jnz     short loc_18002CBDF
0x18002cbd1  mov     edi, 8007000Eh
0x18002cbd6  mov     ecx, edi
0x18002cbd8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002cbdd  jmp     short loc_18002CC2F
0x18002cbdf  test    ebp, ebp
0x18002cbe1  jz      short loc_18002CBF6
0x18002cbe3  mov     rdx, [rdi+8]; Src
0x18002cbe7  mov     rcx, rax; void *
0x18002cbea  movsxd  r8, ebp
0x18002cbed  shl     r8, 4; Size
0x18002cbf1  call    memcpy_0
0x18002cbf6  mov     r14, [rdi+8]
0x18002cbfa  mov     r15, rbx
0x18002cbfd  mov     r12, rbx
0x18002cc00  xor     ebx, ebx
0x18002cc02  test    r14, r14
0x18002cc05  jz      short loc_18002CC1B
0x18002cc07  call    cs:__imp_GetProcessHeap
0x18002cc0d  mov     r8, r14; lpMem
0x18002cc10  xor     edx, edx; dwFlags
0x18002cc12  mov     rcx, rax; hHeap
0x18002cc15  call    cs:__imp_HeapFree
0x18002cc1b  xor     eax, eax
0x18002cc1d  test    r15, r15
0x18002cc20  cmovnz  rax, r12
0x18002cc24  mov     [rdi+8], rax
0x18002cc28  mov     [rdi+4], ebp
0x18002cc2b  mov     [rdi], esi
0x18002cc2d  xor     edi, edi
0x18002cc2f  mov     ecx, edi
0x18002cc31  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cc36  test    rbx, rbx
0x18002cc39  jz      short loc_18002CC4F
0x18002cc3b  call    cs:__imp_GetProcessHeap
0x18002cc41  mov     r8, rbx; lpMem
0x18002cc44  xor     edx, edx; dwFlags
0x18002cc46  mov     rcx, rax; hHeap
0x18002cc49  call    cs:__imp_HeapFree
0x18002cc4f  mov     eax, edi
0x18002cc51  add     rsp, 20h
0x18002cc55  pop     r15
0x18002cc57  pop     r14
0x18002cc59  pop     r12
0x18002cc5b  pop     rdi
0x18002cc5c  pop     rsi
0x18002cc5d  pop     rbp
0x18002cc5e  pop     rbx
0x18002cc5f  retn
```
