# SdbpGetMatchingTextAttributes

- ea: `0x180121f08`
- end: `0x18012215d`
- name: `SdbpGetMatchingTextAttributes`
- size: `597`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *, unsigned int *, _DWORD *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180121100`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x18011e5ac`
- `0x18011ebe8`
- `0x18011ec88`
- `0x18011eed8`
- `0x18011ef7c`
- `0x180121f08`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180122022`
- `ntdll!RtlAllocateHeap` at `0x180122022`

## string_xrefs

- `0x180121f6b`: `Failed to get MATCHING_TEXT file path`
- `0x180122113`: `Failed to read MATCHING_TEXT file path`
- `0x180121fc4`: `Failed to read text to match`
- `0x180122083`: `Failed to read text encoding`
- `0x1801220a8`: `Failed to read encoding type`
- `0x18012205c`: `Failed to read matching text blob`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SdbpGetMatchingTextAttributes(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        unsigned int *a5,
        _DWORD *a6,
        int *a7)
{
  PVOID v7; // rbx
  int v8; // r12d
  unsigned int v9; // r15d
  unsigned int v11; // r13d
  unsigned int FirstTag; // eax
  const char *v13; // r9
  int v14; // r8d
  _WORD *StringTagPtr; // rax
  _WORD *v16; // r14
  unsigned int v17; // eax
  unsigned int v18; // ebp
  unsigned int TagDataSize; // eax
  unsigned int v20; // esi
  PVOID Heap; // rax
  int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // eax
  int DWORDTag; // ebp
  unsigned int v26; // eax

  v7 = 0;
  *a3 = 0;
  v8 = 0x2000;
  *a4 = 0;
  v9 = a2;
  *a5 = 0;
  v11 = 0;
  *a6 = 0;
  *a7 = 0x2000;
  FirstTag = SdbFindFirstTag(a1, a2, 24577);
  if ( !FirstTag )
  {
    v13 = "Failed to get MATCHING_TEXT file path";
    v14 = 1850;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"SdbpGetMatchingTextAttributes", v14, (_DWORD)v13);
    return v11;
  }
  StringTagPtr = (_WORD *)SdbGetStringTagPtr(a1, FirstTag);
  v16 = StringTagPtr;
  if ( !StringTagPtr || !*StringTagPtr )
  {
    v22 = 1862;
    v23 = "Failed to read MATCHING_TEXT file path";
LABEL_24:
    AslLogCallPrintf(1, (unsigned int)"SdbpGetMatchingTextAttributes", v22, (_DWORD)v23);
    if ( v7 )
      AslFree(NtCurrentPeb()->ProcessHeap, v7);
    return v11;
  }
  v17 = SdbFindFirstTag(a1, v9, 36883);
  v18 = v17;
  if ( !v17 )
  {
    v13 = "Failed to read text to match";
    v14 = 1871;
    goto LABEL_3;
  }
  TagDataSize = SdbGetTagDataSize(a1, v17);
  v20 = TagDataSize;
  if ( !TagDataSize )
  {
    v13 = "Failed to get text to match blob";
    v14 = 1877;
    goto LABEL_3;
  }
  if ( TagDataSize == 0x20000000 )
  {
    v13 = "Failed to get text size to match blob";
    v14 = 1881;
    goto LABEL_3;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TagDataSize + 2LL);
  v7 = Heap;
  if ( !Heap )
  {
    v13 = "Failed to allocate memory for text blob";
    v14 = 1887;
    goto LABEL_3;
  }
  if ( !(unsigned int)SdbReadBinaryTag(a1, v18, Heap, v20) )
  {
    v22 = 1892;
    v23 = "Failed to read matching text blob";
    goto LABEL_24;
  }
  v24 = SdbFindFirstTag(a1, v9, 16467);
  if ( !v24 )
  {
    v22 = 1901;
    v23 = "Failed to read text encoding";
    goto LABEL_24;
  }
  DWORDTag = SdbReadDWORDTag(a1, v24, 0);
  if ( !DWORDTag )
  {
    v22 = 1907;
    v23 = "Failed to read encoding type";
    goto LABEL_24;
  }
  v26 = SdbFindFirstTag(a1, v9, 16385);
  if ( v26 )
    v8 = SdbReadDWORDTag(a1, v26, 0x2000);
  v11 = 1;
  *a3 = v16;
  *a4 = v7;
  *a5 = v20;
  *a6 = DWORDTag;
  *a7 = v8;
  return v11;
}

```

## disassembly

```asm
0x180121f08  mov     [rsp+arg_0], rbx
0x180121f0d  mov     [rsp+arg_18], r9
0x180121f12  mov     [rsp+arg_10], r8
0x180121f17  push    rbp
0x180121f18  push    rsi
0x180121f19  push    rdi
0x180121f1a  push    r12
0x180121f1c  push    r13
0x180121f1e  push    r14
0x180121f20  push    r15
0x180121f22  sub     rsp, 20h
0x180121f26  mov     rax, [rsp+58h+arg_20]
0x180121f2e  xor     ebx, ebx
0x180121f30  mov     [r8], rbx
0x180121f33  mov     r12d, 2000h
0x180121f39  mov     r8d, 6001h
0x180121f3f  mov     [r9], rbx
0x180121f42  mov     r15d, edx
0x180121f45  mov     rdi, rcx
0x180121f48  mov     [rax], ebx
0x180121f4a  mov     r13d, ebx
0x180121f4d  mov     rax, [rsp+58h+arg_28]
0x180121f55  mov     [rax], ebx
0x180121f57  mov     rax, [rsp+58h+arg_30]
0x180121f5f  mov     [rax], r12d
0x180121f62  call    SdbFindFirstTag
0x180121f67  test    eax, eax
0x180121f69  jnz     short loc_180121F8E
0x180121f6b  lea     r9, aFailedToGetMat; "Failed to get MATCHING_TEXT file path"
0x180121f72  mov     r8d, 73Ah
0x180121f78  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x180121f7f  mov     ecx, 1
0x180121f84  call    AslLogCallPrintf
0x180121f89  jmp     loc_180122145
0x180121f8e  mov     edx, eax
0x180121f90  mov     rcx, rdi
0x180121f93  call    SdbGetStringTagPtr
0x180121f98  mov     r14, rax
0x180121f9b  test    rax, rax
0x180121f9e  jz      loc_18012210D
0x180121fa4  cmp     [rax], bx
0x180121fa7  jz      loc_18012210D
0x180121fad  mov     r8d, 9013h
0x180121fb3  mov     edx, r15d
0x180121fb6  mov     rcx, rdi
0x180121fb9  call    SdbFindFirstTag
0x180121fbe  mov     ebp, eax
0x180121fc0  test    eax, eax
0x180121fc2  jnz     short loc_180121FD3
0x180121fc4  lea     r9, aFailedToReadTe_0; "Failed to read text to match"
0x180121fcb  mov     r8d, 74Fh
0x180121fd1  jmp     short loc_180121F78
0x180121fd3  mov     edx, ebp
0x180121fd5  mov     rcx, rdi
0x180121fd8  call    SdbGetTagDataSize
0x180121fdd  mov     esi, eax
0x180121fdf  test    eax, eax
0x180121fe1  jnz     short loc_180121FF2
0x180121fe3  lea     r9, aFailedToGetTex; "Failed to get text to match blob"
0x180121fea  mov     r8d, 755h
0x180121ff0  jmp     short loc_180121F78
0x180121ff2  cmp     esi, 20000000h
0x180121ff8  jnz     short loc_18012200C
0x180121ffa  lea     r9, aFailedToGetTex_0; "Failed to get text size to match blob"
0x180122001  mov     r8d, 759h
0x180122007  jmp     loc_180121F78
0x18012200c  mov     rcx, gs:60h
0x180122015  lea     r8, [rsi+2]; Size
0x180122019  mov     edx, 8; Flags
0x18012201e  mov     rcx, [rcx+30h]; HeapHandle
0x180122022  call    cs:__imp_RtlAllocateHeap
0x180122028  mov     rbx, rax
0x18012202b  test    rax, rax
0x18012202e  jnz     short loc_180122042
0x180122030  lea     r9, aFailedToAlloca; "Failed to allocate memory for text blob"
0x180122037  mov     r8d, 75Fh
0x18012203d  jmp     loc_180121F78
0x180122042  mov     r9d, esi
0x180122045  mov     r8, rbx
0x180122048  mov     edx, ebp
0x18012204a  mov     rcx, rdi
0x18012204d  call    SdbReadBinaryTag
0x180122052  test    eax, eax
0x180122054  jnz     short loc_180122068
0x180122056  mov     r8d, 764h
0x18012205c  lea     r9, aFailedToReadMa_0; "Failed to read matching text blob"
0x180122063  jmp     loc_18012211A
0x180122068  mov     r8d, 4053h
0x18012206e  mov     edx, r15d
0x180122071  mov     rcx, rdi
0x180122074  call    SdbFindFirstTag
0x180122079  test    eax, eax
0x18012207b  jnz     short loc_18012208F
0x18012207d  mov     r8d, 76Dh
0x180122083  lea     r9, aFailedToReadTe; "Failed to read text encoding"
0x18012208a  jmp     loc_18012211A
0x18012208f  xor     r8d, r8d
0x180122092  mov     edx, eax
0x180122094  mov     rcx, rdi
0x180122097  call    SdbReadDWORDTag
0x18012209c  mov     ebp, eax
0x18012209e  test    eax, eax
0x1801220a0  jnz     short loc_1801220B1
0x1801220a2  mov     r8d, 773h
0x1801220a8  lea     r9, aFailedToReadEn; "Failed to read encoding type"
0x1801220af  jmp     short loc_18012211A
0x1801220b1  mov     r8d, 4001h
0x1801220b7  mov     edx, r15d
0x1801220ba  mov     rcx, rdi
0x1801220bd  call    SdbFindFirstTag
0x1801220c2  test    eax, eax
0x1801220c4  jz      short loc_1801220D6
0x1801220c6  mov     r8d, r12d
0x1801220c9  mov     edx, eax
0x1801220cb  mov     rcx, rdi
0x1801220ce  call    SdbReadDWORDTag
0x1801220d3  mov     r12d, eax
0x1801220d6  mov     rax, [rsp+58h+arg_10]
0x1801220db  mov     r13d, 1
0x1801220e1  mov     [rax], r14
0x1801220e4  mov     rax, [rsp+58h+arg_18]
0x1801220e9  mov     [rax], rbx
0x1801220ec  mov     rax, [rsp+58h+arg_20]
0x1801220f4  mov     [rax], esi
0x1801220f6  mov     rax, [rsp+58h+arg_28]
0x1801220fe  mov     [rax], ebp
0x180122100  mov     rax, [rsp+58h+arg_30]
0x180122108  mov     [rax], r12d
0x18012210b  jmp     short loc_180122145
0x18012210d  mov     r8d, 746h
0x180122113  lea     r9, aFailedToReadMa_3; "Failed to read MATCHING_TEXT file path"
0x18012211a  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x180122121  mov     ecx, 1
0x180122126  call    AslLogCallPrintf
0x18012212b  test    rbx, rbx
0x18012212e  jz      short loc_180122145
0x180122130  mov     rcx, gs:60h
0x180122139  mov     rdx, rbx
0x18012213c  mov     rcx, [rcx+30h]
0x180122140  call    AslFree
0x180122145  mov     rbx, [rsp+58h+arg_0]
0x18012214a  mov     eax, r13d
0x18012214d  add     rsp, 20h
0x180122151  pop     r15
0x180122153  pop     r14
0x180122155  pop     r13
0x180122157  pop     r12
0x180122159  pop     rdi
0x18012215a  pop     rsi
0x18012215b  pop     rbp
0x18012215c  retn
```
