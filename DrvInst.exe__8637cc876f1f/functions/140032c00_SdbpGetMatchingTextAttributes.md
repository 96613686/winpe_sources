# SdbpGetMatchingTextAttributes

- ea: `0x140032c00`
- end: `0x140032e55`
- name: `SdbpGetMatchingTextAttributes`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400318e0`

## callees

- `0x140032c00`
- `0x1400396b8`
- `0x140039c28`
- `0x140039cc8`
- `0x140039f14`
- `0x140039fb8`
- `0x14003bf18`
- `0x14003c368`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140032d1a`
- `ntdll!RtlAllocateHeap` at `0x140032d1a`

## string_xrefs

- `0x140032c63`: `Failed to get MATCHING_TEXT file path`
- `0x140032e0b`: `Failed to read MATCHING_TEXT file path`
- `0x140032cbc`: `Failed to read text to match`
- `0x140032d7b`: `Failed to read text encoding`
- `0x140032d54`: `Failed to read matching text blob`
- `0x140032da0`: `Failed to read encoding type`

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
  void *v7; // rbx
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
    v8 = SdbReadDWORDTag(a1, v22, 0x2000);
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
0x140032c00  mov     [rsp+arg_0], rbx
0x140032c05  mov     [rsp+arg_18], r9
0x140032c0a  mov     [rsp+arg_10], r8
0x140032c0f  push    rbp
0x140032c10  push    rsi
0x140032c11  push    rdi
0x140032c12  push    r12
0x140032c14  push    r13
0x140032c16  push    r14
0x140032c18  push    r15
0x140032c1a  sub     rsp, 20h
0x140032c1e  mov     rax, [rsp+58h+arg_20]
0x140032c26  xor     ebx, ebx
0x140032c28  mov     [r8], rbx
0x140032c2b  mov     r12d, 2000h
0x140032c31  mov     r8d, 6001h
0x140032c37  mov     [r9], rbx
0x140032c3a  mov     r15d, edx
0x140032c3d  mov     rdi, rcx
0x140032c40  mov     [rax], ebx
0x140032c42  mov     r13d, ebx
0x140032c45  mov     rax, [rsp+58h+arg_28]
0x140032c4d  mov     [rax], ebx
0x140032c4f  mov     rax, [rsp+58h+arg_30]
0x140032c57  mov     [rax], r12d
0x140032c5a  call    SdbFindFirstTag
0x140032c5f  test    eax, eax
0x140032c61  jnz     short loc_140032C86
0x140032c63  lea     r9, aFailedToGetMat; "Failed to get MATCHING_TEXT file path"
0x140032c6a  mov     r8d, 73Ah
0x140032c70  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140032c77  mov     ecx, 1
0x140032c7c  call    AslLogCallPrintf
0x140032c81  jmp     loc_140032E3D
0x140032c86  mov     edx, eax
0x140032c88  mov     rcx, rdi
0x140032c8b  call    SdbGetStringTagPtr
0x140032c90  mov     r14, rax
0x140032c93  test    rax, rax
0x140032c96  jz      loc_140032E05
0x140032c9c  cmp     [rax], bx
0x140032c9f  jz      loc_140032E05
0x140032ca5  mov     r8d, 9013h
0x140032cab  mov     edx, r15d
0x140032cae  mov     rcx, rdi
0x140032cb1  call    SdbFindFirstTag
0x140032cb6  mov     ebp, eax
0x140032cb8  test    eax, eax
0x140032cba  jnz     short loc_140032CCB
0x140032cbc  lea     r9, aFailedToReadTe_0; "Failed to read text to match"
0x140032cc3  mov     r8d, 74Fh
0x140032cc9  jmp     short loc_140032C70
0x140032ccb  mov     edx, ebp
0x140032ccd  mov     rcx, rdi
0x140032cd0  call    SdbGetTagDataSize
0x140032cd5  mov     esi, eax
0x140032cd7  test    eax, eax
0x140032cd9  jnz     short loc_140032CEA
0x140032cdb  lea     r9, aFailedToGetTex; "Failed to get text to match blob"
0x140032ce2  mov     r8d, 755h
0x140032ce8  jmp     short loc_140032C70
0x140032cea  cmp     esi, 20000000h
0x140032cf0  jnz     short loc_140032D04
0x140032cf2  lea     r9, aFailedToGetTex_0; "Failed to get text size to match blob"
0x140032cf9  mov     r8d, 759h
0x140032cff  jmp     loc_140032C70
0x140032d04  mov     rcx, gs:60h
0x140032d0d  lea     r8, [rsi+2]; Size
0x140032d11  mov     edx, 8; Flags
0x140032d16  mov     rcx, [rcx+30h]; HeapHandle
0x140032d1a  call    cs:__imp_RtlAllocateHeap
0x140032d20  mov     rbx, rax
0x140032d23  test    rax, rax
0x140032d26  jnz     short loc_140032D3A
0x140032d28  lea     r9, aFailedToAlloca; "Failed to allocate memory for text blob"
0x140032d2f  mov     r8d, 75Fh
0x140032d35  jmp     loc_140032C70
0x140032d3a  mov     r9d, esi
0x140032d3d  mov     r8, rbx
0x140032d40  mov     edx, ebp
0x140032d42  mov     rcx, rdi
0x140032d45  call    SdbReadBinaryTag
0x140032d4a  test    eax, eax
0x140032d4c  jnz     short loc_140032D60
0x140032d4e  mov     r8d, 764h
0x140032d54  lea     r9, aFailedToReadMa_0; "Failed to read matching text blob"
0x140032d5b  jmp     loc_140032E12
0x140032d60  mov     r8d, 4053h
0x140032d66  mov     edx, r15d
0x140032d69  mov     rcx, rdi
0x140032d6c  call    SdbFindFirstTag
0x140032d71  test    eax, eax
0x140032d73  jnz     short loc_140032D87
0x140032d75  mov     r8d, 76Dh
0x140032d7b  lea     r9, aFailedToReadTe; "Failed to read text encoding"
0x140032d82  jmp     loc_140032E12
0x140032d87  xor     r8d, r8d
0x140032d8a  mov     edx, eax
0x140032d8c  mov     rcx, rdi
0x140032d8f  call    SdbReadDWORDTag
0x140032d94  mov     ebp, eax
0x140032d96  test    eax, eax
0x140032d98  jnz     short loc_140032DA9
0x140032d9a  mov     r8d, 773h
0x140032da0  lea     r9, aFailedToReadEn; "Failed to read encoding type"
0x140032da7  jmp     short loc_140032E12
0x140032da9  mov     r8d, 4001h
0x140032daf  mov     edx, r15d
0x140032db2  mov     rcx, rdi
0x140032db5  call    SdbFindFirstTag
0x140032dba  test    eax, eax
0x140032dbc  jz      short loc_140032DCE
0x140032dbe  mov     r8d, r12d
0x140032dc1  mov     edx, eax
0x140032dc3  mov     rcx, rdi
0x140032dc6  call    SdbReadDWORDTag
0x140032dcb  mov     r12d, eax
0x140032dce  mov     rax, [rsp+58h+arg_10]
0x140032dd3  mov     r13d, 1
0x140032dd9  mov     [rax], r14
0x140032ddc  mov     rax, [rsp+58h+arg_18]
0x140032de1  mov     [rax], rbx
0x140032de4  mov     rax, [rsp+58h+arg_20]
0x140032dec  mov     [rax], esi
0x140032dee  mov     rax, [rsp+58h+arg_28]
0x140032df6  mov     [rax], ebp
0x140032df8  mov     rax, [rsp+58h+arg_30]
0x140032e00  mov     [rax], r12d
0x140032e03  jmp     short loc_140032E3D
0x140032e05  mov     r8d, 746h
0x140032e0b  lea     r9, aFailedToReadMa_3; "Failed to read MATCHING_TEXT file path"
0x140032e12  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140032e19  mov     ecx, 1
0x140032e1e  call    AslLogCallPrintf
0x140032e23  test    rbx, rbx
0x140032e26  jz      short loc_140032E3D
0x140032e28  mov     rcx, gs:60h
0x140032e31  mov     rdx, rbx
0x140032e34  mov     rcx, [rcx+30h]
0x140032e38  call    AslFree
0x140032e3d  mov     rbx, [rsp+58h+arg_0]
0x140032e42  mov     eax, r13d
0x140032e45  add     rsp, 20h
0x140032e49  pop     r15
0x140032e4b  pop     r14
0x140032e4d  pop     r13
0x140032e4f  pop     r12
0x140032e51  pop     rdi
0x140032e52  pop     rsi
0x140032e53  pop     rbp
0x140032e54  retn
```
