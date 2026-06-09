# SdbpGetMatchingTextAttributes

- ea: `0x18004e5d4`
- end: `0x18004e829`
- name: `SdbpGetMatchingTextAttributes`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18004ddc0`

## callees

- `0x18000beb0`
- `0x18000ecc0`
- `0x18000f114`
- `0x18000f150`
- `0x180016590`
- `0x180018f20`
- `0x180022b10`
- `0x18004e5d4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004e6ee`
- `ntdll!RtlAllocateHeap` at `0x18004e6ee`

## string_xrefs

- `0x18004e637`: `Failed to get MATCHING_TEXT file path`
- `0x18004e7df`: `Failed to read MATCHING_TEXT file path`
- `0x18004e690`: `Failed to read text to match`
- `0x18004e74f`: `Failed to read text encoding`
- `0x18004e728`: `Failed to read matching text blob`
- `0x18004e774`: `Failed to read encoding type`

## pseudocode

```c
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
  _WORD *StringTagPtr; // rax
  _WORD *v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // ebp
  unsigned int TagDataSize; // eax
  unsigned int v18; // esi
  PVOID Heap; // rax
  unsigned int v20; // eax
  int DWORDTag; // ebp
  unsigned int v22; // eax

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
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1850, "Failed to get MATCHING_TEXT file path");
    return v11;
  }
  StringTagPtr = (_WORD *)SdbGetStringTagPtr(a1, FirstTag);
  v14 = StringTagPtr;
  if ( !StringTagPtr || !*StringTagPtr )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1862, "Failed to read MATCHING_TEXT file path");
LABEL_24:
    if ( v7 )
      AslFree(NtCurrentPeb()->ProcessHeap, v7);
    return v11;
  }
  v15 = SdbFindFirstTag(a1, v9, 36883);
  v16 = v15;
  if ( !v15 )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1871, "Failed to read text to match");
    return v11;
  }
  TagDataSize = SdbGetTagDataSize(a1, v15);
  v18 = TagDataSize;
  if ( !TagDataSize )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1877, "Failed to get text to match blob");
    return v11;
  }
  if ( TagDataSize == 0x20000000 )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1881, "Failed to get text size to match blob");
    return v11;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TagDataSize + 2LL);
  v7 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1887, "Failed to allocate memory for text blob");
    return v11;
  }
  if ( !(unsigned int)SdbReadBinaryTag(a1, v16, Heap, v18) )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1892, "Failed to read matching text blob");
    goto LABEL_24;
  }
  v20 = SdbFindFirstTag(a1, v9, 16467);
  if ( !v20 )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1901, "Failed to read text encoding");
    goto LABEL_24;
  }
  DWORDTag = SdbReadDWORDTag(a1, v20, 0);
  if ( !DWORDTag )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1907, "Failed to read encoding type");
    goto LABEL_24;
  }
  v22 = SdbFindFirstTag(a1, v9, 16385);
  if ( v22 )
    v8 = SdbReadDWORDTag(a1, v22, 0x2000u);
  v11 = 1;
  *a3 = v14;
  *a4 = v7;
  *a5 = v18;
  *a6 = DWORDTag;
  *a7 = v8;
  return v11;
}

```

## disassembly

```asm
0x18004e5d4  mov     [rsp+arg_0], rbx
0x18004e5d9  mov     [rsp+arg_18], r9
0x18004e5de  mov     [rsp+arg_10], r8
0x18004e5e3  push    rbp
0x18004e5e4  push    rsi
0x18004e5e5  push    rdi
0x18004e5e6  push    r12
0x18004e5e8  push    r13
0x18004e5ea  push    r14
0x18004e5ec  push    r15
0x18004e5ee  sub     rsp, 20h
0x18004e5f2  mov     rax, [rsp+58h+arg_20]
0x18004e5fa  xor     ebx, ebx
0x18004e5fc  mov     [r8], rbx
0x18004e5ff  mov     r12d, 2000h
0x18004e605  mov     r8d, 6001h
0x18004e60b  mov     [r9], rbx
0x18004e60e  mov     r15d, edx
0x18004e611  mov     rdi, rcx
0x18004e614  mov     [rax], ebx
0x18004e616  mov     r13d, ebx
0x18004e619  mov     rax, [rsp+58h+arg_28]
0x18004e621  mov     [rax], ebx
0x18004e623  mov     rax, [rsp+58h+arg_30]
0x18004e62b  mov     [rax], r12d
0x18004e62e  call    SdbFindFirstTag
0x18004e633  test    eax, eax
0x18004e635  jnz     short loc_18004E65A
0x18004e637  lea     r9, aFailedToGetMat; "Failed to get MATCHING_TEXT file path"
0x18004e63e  mov     r8d, 73Ah
0x18004e644  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x18004e64b  mov     ecx, 1
0x18004e650  call    AslLogCallPrintf
0x18004e655  jmp     loc_18004E811
0x18004e65a  mov     edx, eax
0x18004e65c  mov     rcx, rdi
0x18004e65f  call    SdbGetStringTagPtr
0x18004e664  mov     r14, rax
0x18004e667  test    rax, rax
0x18004e66a  jz      loc_18004E7D9
0x18004e670  cmp     [rax], bx
0x18004e673  jz      loc_18004E7D9
0x18004e679  mov     r8d, 9013h
0x18004e67f  mov     edx, r15d
0x18004e682  mov     rcx, rdi
0x18004e685  call    SdbFindFirstTag
0x18004e68a  mov     ebp, eax
0x18004e68c  test    eax, eax
0x18004e68e  jnz     short loc_18004E69F
0x18004e690  lea     r9, aFailedToReadTe_0; "Failed to read text to match"
0x18004e697  mov     r8d, 74Fh
0x18004e69d  jmp     short loc_18004E644
0x18004e69f  mov     edx, ebp
0x18004e6a1  mov     rcx, rdi
0x18004e6a4  call    SdbGetTagDataSize
0x18004e6a9  mov     esi, eax
0x18004e6ab  test    eax, eax
0x18004e6ad  jnz     short loc_18004E6BE
0x18004e6af  lea     r9, aFailedToGetTex; "Failed to get text to match blob"
0x18004e6b6  mov     r8d, 755h
0x18004e6bc  jmp     short loc_18004E644
0x18004e6be  cmp     esi, 20000000h
0x18004e6c4  jnz     short loc_18004E6D8
0x18004e6c6  lea     r9, aFailedToGetTex_0; "Failed to get text size to match blob"
0x18004e6cd  mov     r8d, 759h
0x18004e6d3  jmp     loc_18004E644
0x18004e6d8  mov     rcx, gs:60h
0x18004e6e1  lea     r8, [rsi+2]; Size
0x18004e6e5  mov     edx, 8; Flags
0x18004e6ea  mov     rcx, [rcx+30h]; HeapHandle
0x18004e6ee  call    cs:__imp_RtlAllocateHeap
0x18004e6f4  mov     rbx, rax
0x18004e6f7  test    rax, rax
0x18004e6fa  jnz     short loc_18004E70E
0x18004e6fc  lea     r9, aFailedToAlloca; "Failed to allocate memory for text blob"
0x18004e703  mov     r8d, 75Fh
0x18004e709  jmp     loc_18004E644
0x18004e70e  mov     r9d, esi
0x18004e711  mov     r8, rbx
0x18004e714  mov     edx, ebp
0x18004e716  mov     rcx, rdi
0x18004e719  call    SdbReadBinaryTag
0x18004e71e  test    eax, eax
0x18004e720  jnz     short loc_18004E734
0x18004e722  mov     r8d, 764h
0x18004e728  lea     r9, aFailedToReadMa_0; "Failed to read matching text blob"
0x18004e72f  jmp     loc_18004E7E6
0x18004e734  mov     r8d, 4053h
0x18004e73a  mov     edx, r15d
0x18004e73d  mov     rcx, rdi
0x18004e740  call    SdbFindFirstTag
0x18004e745  test    eax, eax
0x18004e747  jnz     short loc_18004E75B
0x18004e749  mov     r8d, 76Dh
0x18004e74f  lea     r9, aFailedToReadTe; "Failed to read text encoding"
0x18004e756  jmp     loc_18004E7E6
0x18004e75b  xor     r8d, r8d
0x18004e75e  mov     edx, eax
0x18004e760  mov     rcx, rdi
0x18004e763  call    SdbReadDWORDTag
0x18004e768  mov     ebp, eax
0x18004e76a  test    eax, eax
0x18004e76c  jnz     short loc_18004E77D
0x18004e76e  mov     r8d, 773h
0x18004e774  lea     r9, aFailedToReadEn; "Failed to read encoding type"
0x18004e77b  jmp     short loc_18004E7E6
0x18004e77d  mov     r8d, 4001h
0x18004e783  mov     edx, r15d
0x18004e786  mov     rcx, rdi
0x18004e789  call    SdbFindFirstTag
0x18004e78e  test    eax, eax
0x18004e790  jz      short loc_18004E7A2
0x18004e792  mov     r8d, r12d
0x18004e795  mov     edx, eax
0x18004e797  mov     rcx, rdi
0x18004e79a  call    SdbReadDWORDTag
0x18004e79f  mov     r12d, eax
0x18004e7a2  mov     rax, [rsp+58h+arg_10]
0x18004e7a7  mov     r13d, 1
0x18004e7ad  mov     [rax], r14
0x18004e7b0  mov     rax, [rsp+58h+arg_18]
0x18004e7b5  mov     [rax], rbx
0x18004e7b8  mov     rax, [rsp+58h+arg_20]
0x18004e7c0  mov     [rax], esi
0x18004e7c2  mov     rax, [rsp+58h+arg_28]
0x18004e7ca  mov     [rax], ebp
0x18004e7cc  mov     rax, [rsp+58h+arg_30]
0x18004e7d4  mov     [rax], r12d
0x18004e7d7  jmp     short loc_18004E811
0x18004e7d9  mov     r8d, 746h
0x18004e7df  lea     r9, aFailedToReadMa_3; "Failed to read MATCHING_TEXT file path"
0x18004e7e6  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x18004e7ed  mov     ecx, 1
0x18004e7f2  call    AslLogCallPrintf
0x18004e7f7  test    rbx, rbx
0x18004e7fa  jz      short loc_18004E811
0x18004e7fc  mov     rcx, gs:60h
0x18004e805  mov     rdx, rbx
0x18004e808  mov     rcx, [rcx+30h]
0x18004e80c  call    AslFree
0x18004e811  mov     rbx, [rsp+58h+arg_0]
0x18004e816  mov     eax, r13d
0x18004e819  add     rsp, 20h
0x18004e81d  pop     r15
0x18004e81f  pop     r14
0x18004e821  pop     r13
0x18004e823  pop     r12
0x18004e825  pop     rdi
0x18004e826  pop     rsi
0x18004e827  pop     rbp
0x18004e828  retn
```
