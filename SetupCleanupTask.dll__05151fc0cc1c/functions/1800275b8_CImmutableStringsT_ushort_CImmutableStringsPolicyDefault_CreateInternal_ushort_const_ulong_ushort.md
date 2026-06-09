# CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)

- ea: `0x1800275b8`
- end: `0x1800276e0`
- name: `?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(void *Src, unsigned int, _QWORD *)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180026598`
- `0x180027028`
- `0x180027d04`
- `0x180027f3c`
- `0x180028a08`
- `0x18002aed4`
- `0x18002b4ec`
- `0x18002b848`

## callees

- `0x180002746`
- `0x180027008`
- `0x1800275b8`
- `0x1800293a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002766f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002766f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027661`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800276bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027661`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800276bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800276c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800276c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
        void *Src,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v3; // rbp
  unsigned int v6; // esi
  int v7; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rax
  _DWORD *v10; // rdi

  v3 = a2;
  if ( !Src )
  {
    *a3 = 0;
    goto LABEL_22;
  }
  v6 = a2 + 1;
  if ( a2 + 1 < a2 )
  {
    v6 = 0;
    v7 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  else
  {
    v7 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
    goto LABEL_6;
  if ( !v6 )
  {
    v6 = 0;
    goto LABEL_12;
  }
  if ( (2 * v6) >> 1 == v6 )
  {
    v6 *= 2;
LABEL_12:
    v7 = 0;
    goto LABEL_13;
  }
  v7 = -2147024362;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
LABEL_13:
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
  v9 = HeapAlloc(ProcessHeap, 0, v6);
  if ( v9 )
  {
    v10 = v9 + 1;
    *v9 = v3;
    memcpy_0(v9 + 1, Src, 2 * v3);
    *((_WORD *)v10 + v3) = 0;
    *a3 = v10;
LABEL_22:
    v7 = 0;
    goto LABEL_23;
  }
  v7 = -2147024882;
LABEL_6:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800275b8  push    rbx
0x1800275ba  push    rbp
0x1800275bb  push    rsi
0x1800275bc  push    rdi
0x1800275bd  push    r12
0x1800275bf  push    r14
0x1800275c1  push    r15
0x1800275c3  sub     rsp, 20h
0x1800275c7  xor     ebx, ebx
0x1800275c9  mov     ebp, edx
0x1800275cb  mov     r14, r8
0x1800275ce  mov     r15, rcx
0x1800275d1  test    rcx, rcx
0x1800275d4  jz      loc_1800276AA
0x1800275da  lea     esi, [rbp+1]
0x1800275dd  mov     r12d, 80070216h
0x1800275e3  cmp     esi, ebp
0x1800275e5  jb      short loc_1800275EB
0x1800275e7  xor     edi, edi
0x1800275e9  jmp     short loc_1800275F8
0x1800275eb  xor     esi, esi
0x1800275ed  mov     ecx, r12d
0x1800275f0  mov     edi, r12d
0x1800275f3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800275f8  mov     ecx, edi
0x1800275fa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800275ff  test    edi, edi
0x180027601  jns     short loc_18002760F
0x180027603  mov     ecx, edi
0x180027605  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002760a  jmp     loc_1800276AF
0x18002760f  test    esi, esi
0x180027611  jz      short loc_18002762F
0x180027613  lea     ecx, [rsi+rsi]
0x180027616  mov     eax, ecx
0x180027618  shr     eax, 1
0x18002761a  cmp     eax, esi
0x18002761c  jz      short loc_18002762B
0x18002761e  mov     ecx, r12d
0x180027621  mov     edi, r12d
0x180027624  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027629  jmp     short loc_180027633
0x18002762b  mov     esi, ecx
0x18002762d  jmp     short loc_180027631
0x18002762f  xor     esi, esi
0x180027631  xor     edi, edi
0x180027633  mov     ecx, edi
0x180027635  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002763a  test    edi, edi
0x18002763c  js      short loc_180027603
0x18002763e  lea     eax, [rsi+4]
0x180027641  cmp     eax, esi
0x180027643  jb      short loc_18002764B
0x180027645  mov     esi, eax
0x180027647  xor     edi, edi
0x180027649  jmp     short loc_180027656
0x18002764b  mov     ecx, r12d
0x18002764e  mov     edi, r12d
0x180027651  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027656  mov     ecx, edi
0x180027658  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002765d  test    edi, edi
0x18002765f  js      short loc_180027603
0x180027661  call    cs:__imp_GetProcessHeap
0x180027667  mov     r8d, esi; dwBytes
0x18002766a  xor     edx, edx; dwFlags
0x18002766c  mov     rcx, rax; hHeap
0x18002766f  call    cs:__imp_HeapAlloc
0x180027675  test    rax, rax
0x180027678  jnz     short loc_180027681
0x18002767a  mov     edi, 8007000Eh
0x18002767f  jmp     short loc_180027603
0x180027681  lea     rdi, [rax+4]
0x180027685  mov     [rax], ebp
0x180027687  lea     rbx, ds:0[rbp*2]
0x18002768f  mov     rcx, rdi; void *
0x180027692  mov     r8, rbx; Size
0x180027695  mov     rdx, r15; Src
0x180027698  call    memcpy_0
0x18002769d  xor     eax, eax
0x18002769f  mov     [rbx+rdi], ax
0x1800276a3  xor     ebx, ebx
0x1800276a5  mov     [r14], rdi
0x1800276a8  jmp     short loc_1800276AD
0x1800276aa  mov     [r8], rbx
0x1800276ad  xor     edi, edi
0x1800276af  mov     ecx, edi
0x1800276b1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800276b6  test    rbx, rbx
0x1800276b9  jz      short loc_1800276CF
0x1800276bb  call    cs:__imp_GetProcessHeap
0x1800276c1  mov     r8, rbx; lpMem
0x1800276c4  xor     edx, edx; dwFlags
0x1800276c6  mov     rcx, rax; hHeap
0x1800276c9  call    cs:__imp_HeapFree
0x1800276cf  mov     eax, edi
0x1800276d1  add     rsp, 20h
0x1800276d5  pop     r15
0x1800276d7  pop     r14
0x1800276d9  pop     r12
0x1800276db  pop     rdi
0x1800276dc  pop     rsi
0x1800276dd  pop     rbp
0x1800276de  pop     rbx
0x1800276df  retn
```
