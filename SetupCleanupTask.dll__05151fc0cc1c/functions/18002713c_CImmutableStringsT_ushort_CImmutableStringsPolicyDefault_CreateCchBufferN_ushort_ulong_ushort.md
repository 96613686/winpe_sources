# CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateCchBufferN(ushort,ulong,ushort * *)

- ea: `0x18002713c`
- end: `0x180027244`
- name: `?CreateCchBufferN@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJGKPEAPEAG@Z`
- size: `264`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180027d04`
- `0x18002c6a0`

## callees

- `0x180027008`
- `0x18002713c`
- `0x1800293a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800271be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800271be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800271b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027221`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800271b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027221`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002722f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002722f`

## pseudocode

```c
__int64 __fastcall CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateCchBufferN(
        __int64 a1,
        int a2,
        _QWORD *a3)
{
  _DWORD *v3; // rbx
  unsigned int v6; // esi
  int v7; // edi
  HANDLE ProcessHeap; // rax
  __int64 v9; // rcx
  _DWORD *v10; // rdx
  HANDLE v11; // rax

  v3 = 0;
  if ( a2 )
  {
    v6 = 2 * a2;
    if ( (unsigned int)(2 * a2) >> 1 == a2 )
    {
      v7 = 0;
    }
    else
    {
      v6 = 0;
      v7 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_6;
    if ( v6 + 4 < v6 )
    {
      v7 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    else
    {
      v6 += 4;
      v7 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      goto LABEL_6;
    ProcessHeap = GetProcessHeap();
    v3 = HeapAlloc(ProcessHeap, 0, v6);
    if ( !v3 )
    {
      v7 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
      goto LABEL_20;
    }
    if ( a2 )
    {
      *v3 = a2 - 1;
      v7 = 0;
    }
    else
    {
      v7 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
    {
LABEL_6:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
      goto LABEL_20;
    }
    v9 = (unsigned int)*v3;
    v10 = v3 + 1;
    v3 = 0;
    *((_WORD *)v10 + v9) = 0;
    *a3 = v10;
  }
  else
  {
    *a3 = 0;
  }
  v7 = 0;
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v3 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v3);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002713c  push    rbx
0x18002713e  push    rbp
0x18002713f  push    rsi
0x180027140  push    rdi
0x180027141  push    r14
0x180027143  push    r15
0x180027145  sub     rsp, 28h
0x180027149  xor     ebx, ebx
0x18002714b  mov     r15, r8
0x18002714e  mov     r14d, edx
0x180027151  test    edx, edx
0x180027153  jz      loc_180027210
0x180027159  lea     esi, [rdx+rdx]
0x18002715c  mov     ebp, 80070216h
0x180027161  mov     eax, esi
0x180027163  shr     eax, 1
0x180027165  cmp     eax, edx
0x180027167  jz      short loc_180027176
0x180027169  xor     esi, esi
0x18002716b  mov     ecx, ebp
0x18002716d  mov     edi, ebp
0x18002716f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027174  jmp     short loc_180027178
0x180027176  xor     edi, edi
0x180027178  mov     ecx, edi
0x18002717a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002717f  test    edi, edi
0x180027181  jns     short loc_18002718F
0x180027183  mov     ecx, edi
0x180027185  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002718a  jmp     loc_180027215
0x18002718f  lea     eax, [rsi+4]
0x180027192  cmp     eax, esi
0x180027194  jb      short loc_18002719C
0x180027196  mov     esi, eax
0x180027198  xor     edi, edi
0x18002719a  jmp     short loc_1800271A5
0x18002719c  mov     ecx, ebp
0x18002719e  mov     edi, ebp
0x1800271a0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800271a5  mov     ecx, edi
0x1800271a7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800271ac  test    edi, edi
0x1800271ae  js      short loc_180027183
0x1800271b0  call    cs:__imp_GetProcessHeap
0x1800271b6  mov     r8d, esi; dwBytes
0x1800271b9  xor     edx, edx; dwFlags
0x1800271bb  mov     rcx, rax; hHeap
0x1800271be  call    cs:__imp_HeapAlloc
0x1800271c4  mov     rbx, rax
0x1800271c7  test    rax, rax
0x1800271ca  jnz     short loc_1800271DA
0x1800271cc  mov     edi, 8007000Eh
0x1800271d1  mov     ecx, edi
0x1800271d3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800271d8  jmp     short loc_180027215
0x1800271da  lea     eax, [r14-1]
0x1800271de  cmp     eax, r14d
0x1800271e1  ja      short loc_1800271E9
0x1800271e3  mov     [rbx], eax
0x1800271e5  xor     edi, edi
0x1800271e7  jmp     short loc_1800271F2
0x1800271e9  mov     ecx, ebp
0x1800271eb  mov     edi, ebp
0x1800271ed  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800271f2  mov     ecx, edi
0x1800271f4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800271f9  test    edi, edi
0x1800271fb  js      short loc_180027183
0x1800271fd  mov     ecx, [rbx]
0x1800271ff  lea     rdx, [rbx+4]
0x180027203  xor     eax, eax
0x180027205  xor     ebx, ebx
0x180027207  mov     [rdx+rcx*2], ax
0x18002720b  mov     [r15], rdx
0x18002720e  jmp     short loc_180027213
0x180027210  mov     [r8], rbx
0x180027213  xor     edi, edi
0x180027215  mov     ecx, edi
0x180027217  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002721c  test    rbx, rbx
0x18002721f  jz      short loc_180027235
0x180027221  call    cs:__imp_GetProcessHeap
0x180027227  mov     r8, rbx; lpMem
0x18002722a  xor     edx, edx; dwFlags
0x18002722c  mov     rcx, rax; hHeap
0x18002722f  call    cs:__imp_HeapFree
0x180027235  mov     eax, edi
0x180027237  add     rsp, 28h
0x18002723b  pop     r15
0x18002723d  pop     r14
0x18002723f  pop     rdi
0x180027240  pop     rsi
0x180027241  pop     rbp
0x180027242  pop     rbx
0x180027243  retn
```
