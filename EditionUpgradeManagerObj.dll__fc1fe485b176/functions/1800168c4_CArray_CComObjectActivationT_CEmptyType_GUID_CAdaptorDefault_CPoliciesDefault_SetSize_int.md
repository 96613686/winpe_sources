# CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x1800168c4`
- end: `0x1800169a8`
- name: `?SetSize@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `228`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014800`
- `0x180014ba0`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x1800168c4`
- `0x18002295c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001695d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016991`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001695d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016991`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001690b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001690b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800168fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001694f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016983`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800168fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001694f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016983`

## pseudocode

```c
__int64 __fastcall CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(
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
0x1800168c4  push    rbx
0x1800168c6  push    rbp
0x1800168c7  push    rsi
0x1800168c8  push    rdi
0x1800168c9  push    r12
0x1800168cb  push    r14
0x1800168cd  push    r15
0x1800168cf  sub     rsp, 20h
0x1800168d3  movsxd  rsi, edx
0x1800168d6  xor     ebx, ebx
0x1800168d8  mov     rdi, rcx
0x1800168db  cmp     [rcx], esi
0x1800168dd  jz      loc_180016975
0x1800168e3  mov     ebp, [rcx+4]
0x1800168e6  cmp     esi, ebp
0x1800168e8  cmovl   ebp, esi
0x1800168eb  test    edx, edx
0x1800168ed  jle     short loc_18001693E
0x1800168ef  xor     ecx, ecx
0x1800168f1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800168f6  mov     rbx, rsi
0x1800168f9  shl     rbx, 3
0x1800168fd  call    cs:__imp_GetProcessHeap
0x180016903  mov     r8, rbx; dwBytes
0x180016906  xor     edx, edx; dwFlags
0x180016908  mov     rcx, rax; hHeap
0x18001690b  call    cs:__imp_HeapAlloc
0x180016911  mov     rbx, rax
0x180016914  test    rax, rax
0x180016917  jnz     short loc_180016927
0x180016919  mov     edi, 8007000Eh
0x18001691e  mov     ecx, edi
0x180016920  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016925  jmp     short loc_180016977
0x180016927  test    ebp, ebp
0x180016929  jz      short loc_18001693E
0x18001692b  mov     rdx, [rdi+8]; Src
0x18001692f  mov     rcx, rax; void *
0x180016932  movsxd  r8, ebp
0x180016935  shl     r8, 3; Size
0x180016939  call    memcpy_0
0x18001693e  mov     r14, [rdi+8]
0x180016942  mov     r15, rbx
0x180016945  mov     r12, rbx
0x180016948  xor     ebx, ebx
0x18001694a  test    r14, r14
0x18001694d  jz      short loc_180016963
0x18001694f  call    cs:__imp_GetProcessHeap
0x180016955  mov     r8, r14; lpMem
0x180016958  xor     edx, edx; dwFlags
0x18001695a  mov     rcx, rax; hHeap
0x18001695d  call    cs:__imp_HeapFree
0x180016963  xor     eax, eax
0x180016965  test    r15, r15
0x180016968  cmovnz  rax, r12
0x18001696c  mov     [rdi+8], rax
0x180016970  mov     [rdi+4], ebp
0x180016973  mov     [rdi], esi
0x180016975  xor     edi, edi
0x180016977  mov     ecx, edi
0x180016979  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001697e  test    rbx, rbx
0x180016981  jz      short loc_180016997
0x180016983  call    cs:__imp_GetProcessHeap
0x180016989  mov     r8, rbx; lpMem
0x18001698c  xor     edx, edx; dwFlags
0x18001698e  mov     rcx, rax; hHeap
0x180016991  call    cs:__imp_HeapFree
0x180016997  mov     eax, edi
0x180016999  add     rsp, 20h
0x18001699d  pop     r15
0x18001699f  pop     r14
0x1800169a1  pop     r12
0x1800169a3  pop     rdi
0x1800169a4  pop     rsi
0x1800169a5  pop     rbp
0x1800169a6  pop     rbx
0x1800169a7  retn
```
