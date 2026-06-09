# CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)

- ea: `0x1400067f4`
- end: `0x14000691c`
- name: `?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z`
- size: `296`
- prototype: `__int64 __fastcall(void *Src, unsigned int, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007dcc`
- `0x140012938`

## callees

- `0x140003454`
- `0x140004780`
- `0x1400067f4`
- `0x140013462`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000689d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000689d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400068ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400068ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006905`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006905`

## pseudocode

```c
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
0x1400067f4  push    rbx
0x1400067f6  push    rbp
0x1400067f7  push    rsi
0x1400067f8  push    rdi
0x1400067f9  push    r12
0x1400067fb  push    r14
0x1400067fd  push    r15
0x1400067ff  sub     rsp, 20h
0x140006803  xor     ebx, ebx
0x140006805  mov     ebp, edx
0x140006807  mov     r14, r8
0x14000680a  mov     r15, rcx
0x14000680d  test    rcx, rcx
0x140006810  jz      loc_1400068E6
0x140006816  lea     esi, [rbp+1]
0x140006819  mov     r12d, 80070216h
0x14000681f  cmp     esi, ebp
0x140006821  jb      short loc_140006827
0x140006823  xor     edi, edi
0x140006825  jmp     short loc_140006834
0x140006827  xor     esi, esi
0x140006829  mov     ecx, r12d
0x14000682c  mov     edi, r12d
0x14000682f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006834  mov     ecx, edi
0x140006836  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000683b  test    edi, edi
0x14000683d  jns     short loc_14000684B
0x14000683f  mov     ecx, edi
0x140006841  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006846  jmp     loc_1400068EB
0x14000684b  test    esi, esi
0x14000684d  jz      short loc_14000686B
0x14000684f  lea     ecx, [rsi+rsi]
0x140006852  mov     eax, ecx
0x140006854  shr     eax, 1
0x140006856  cmp     eax, esi
0x140006858  jz      short loc_140006867
0x14000685a  mov     ecx, r12d
0x14000685d  mov     edi, r12d
0x140006860  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006865  jmp     short loc_14000686F
0x140006867  mov     esi, ecx
0x140006869  jmp     short loc_14000686D
0x14000686b  xor     esi, esi
0x14000686d  xor     edi, edi
0x14000686f  mov     ecx, edi
0x140006871  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140006876  test    edi, edi
0x140006878  js      short loc_14000683F
0x14000687a  lea     eax, [rsi+4]
0x14000687d  cmp     eax, esi
0x14000687f  jb      short loc_140006887
0x140006881  mov     esi, eax
0x140006883  xor     edi, edi
0x140006885  jmp     short loc_140006892
0x140006887  mov     ecx, r12d
0x14000688a  mov     edi, r12d
0x14000688d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006892  mov     ecx, edi
0x140006894  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140006899  test    edi, edi
0x14000689b  js      short loc_14000683F
0x14000689d  call    cs:__imp_GetProcessHeap
0x1400068a3  mov     r8d, esi; dwBytes
0x1400068a6  xor     edx, edx; dwFlags
0x1400068a8  mov     rcx, rax; hHeap
0x1400068ab  call    cs:__imp_HeapAlloc
0x1400068b1  test    rax, rax
0x1400068b4  jnz     short loc_1400068BD
0x1400068b6  mov     edi, 8007000Eh
0x1400068bb  jmp     short loc_14000683F
0x1400068bd  lea     rdi, [rax+4]
0x1400068c1  mov     [rax], ebp
0x1400068c3  lea     rbx, ds:0[rbp*2]
0x1400068cb  mov     rcx, rdi; void *
0x1400068ce  mov     r8, rbx; Size
0x1400068d1  mov     rdx, r15; Src
0x1400068d4  call    memcpy_0
0x1400068d9  xor     eax, eax
0x1400068db  mov     [rbx+rdi], ax
0x1400068df  xor     ebx, ebx
0x1400068e1  mov     [r14], rdi
0x1400068e4  jmp     short loc_1400068E9
0x1400068e6  mov     [r8], rbx
0x1400068e9  xor     edi, edi
0x1400068eb  mov     ecx, edi
0x1400068ed  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400068f2  test    rbx, rbx
0x1400068f5  jz      short loc_14000690B
0x1400068f7  call    cs:__imp_GetProcessHeap
0x1400068fd  mov     r8, rbx; lpMem
0x140006900  xor     edx, edx; dwFlags
0x140006902  mov     rcx, rax; hHeap
0x140006905  call    cs:__imp_HeapFree
0x14000690b  mov     eax, edi
0x14000690d  add     rsp, 20h
0x140006911  pop     r15
0x140006913  pop     r14
0x140006915  pop     r12
0x140006917  pop     rdi
0x140006918  pop     rsi
0x140006919  pop     rbp
0x14000691a  pop     rbx
0x14000691b  retn
```
