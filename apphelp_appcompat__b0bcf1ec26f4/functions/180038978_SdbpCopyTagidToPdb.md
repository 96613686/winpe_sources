# SdbpCopyTagidToPdb

- ea: `0x180038978`
- end: `0x180038edb`
- name: `SdbpCopyTagidToPdb`
- size: `1379`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `loader_planting`

## callers

- `0x180038978`
- `0x1800404f0`

## callees

- `0x180006ba0`
- `0x180006c20`
- `0x18000b720`
- `0x18000bca0`
- `0x18000beb0`
- `0x18000efe0`
- `0x18000f114`
- `0x18000f150`
- `0x180011240`
- `0x180022b10`
- `0x180024a80`
- `0x180026ca0`
- `0x18002ed10`
- `0x180038978`
- `0x18003f610`
- `0x18003fc80`
- `0x18003fe90`
- `0x18003fee0`
- `0x180040100`
- `0x180040150`
- `0x180040190`
- `0x180040230`
- `0x180040300`
- `0x18004c110`
- `0x180059235`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180038da2`
- `ntdll!RtlReAllocateHeap` at `0x180038da2`
- `ntdll!RtlAllocateHeap` at `0x180038d82`
- `ntdll!RtlAllocateHeap` at `0x180038d82`

## string_xrefs

- `0x1800389d2`: `SdbpCopyTagidToPdb`
- `0x180038e55`: `SdbpCopyTagidToPdb`
- `0x180038bcd`: `Failed to read tagid from original pdb.`
- `0x180038b52`: `Failed to read string from original pdb.`
- `0x180038ac2`: `SdbBeginWriteListTag failed.`
- `0x180038b31`: `SdbEndWriteListTag failed`

## pseudocode

```c
__int64 __fastcall SdbpCopyTagidToPdb(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5, unsigned int a6)
{
  unsigned __int16 TagFromTagID; // ax
  int v12; // ebx
  int v13; // ebx
  int v14; // eax
  unsigned int TagDataSize; // r14d
  __int64 BinaryTagData; // rax
  int v17; // eax
  __int64 v18; // r12
  unsigned int v19; // r13d
  unsigned int i; // eax
  unsigned int v21; // r15d
  __int64 StringTagPtr; // rax
  __int64 QWORDTag; // rax
  unsigned __int64 j; // rax
  unsigned int DWORDTag; // eax
  unsigned int v26; // r12d
  __int16 v27; // dx
  unsigned int k; // eax
  __int64 v29; // rcx
  __int64 *v30; // r15
  ULONGLONG v31; // rax
  int v32; // eax
  __int64 v33; // r12
  ULONGLONG v34; // rdx
  ULONGLONG v35; // rcx
  __int64 v36; // r9
  ULONGLONG v37; // r12
  void *v38; // r8
  size_t v39; // r13
  void *v40; // rcx
  PVOID v41; // rax
  PVOID Heap; // r15
  unsigned int v43; // eax
  ULONGLONG v44; // rcx
  _QWORD *v45; // r9
  __int64 *v46; // r10
  int v47; // r11d
  ULONGLONG v48; // rdx
  __int64 v49; // rax
  unsigned __int16 WORDTag; // ax
  __int64 v51; // r8
  __int64 v52; // [rsp+20h] [rbp-40h]
  ULONGLONG Size; // [rsp+30h] [rbp-30h] BYREF
  ULONGLONG ullMultiplier; // [rsp+38h] [rbp-28h]
  ULONGLONG pullResult; // [rsp+40h] [rbp-20h] BYREF
  __int64 v56; // [rsp+48h] [rbp-18h] BYREF
  int v57; // [rsp+A0h] [rbp+40h]
  int v58; // [rsp+B0h] [rbp+50h] BYREF

  v57 = a1;
  if ( !a3 )
    return 0;
  v58 = 0;
  TagFromTagID = SdbGetTagFromTagID(a2, a3);
  v12 = TagFromTagID;
  if ( TagFromTagID )
  {
    v14 = TagFromTagID & 0xF000;
    switch ( v14 )
    {
      case 4096:
        v17 = SdbWriteNULLTag(a5, (unsigned __int16)v12);
        return v17 == 0 ? 0xC00000E5 : 0;
      case 8192:
        LOBYTE(v51) = SdbReadBYTETag(a2, a3, 0);
        v17 = SdbWriteBYTETag(a5, (unsigned __int16)v12, v51);
        return v17 == 0 ? 0xC00000E5 : 0;
      case 12288:
        WORDTag = SdbReadWORDTag(a2, a3, 0);
        v17 = SdbWriteWORDTag(a5, (unsigned __int16)v12, WORDTag);
        return v17 == 0 ? 0xC00000E5 : 0;
    }
    if ( v14 != 0x4000 )
    {
      switch ( v14 )
      {
        case 20480:
          QWORDTag = SdbReadQWORDTag(a2, a3, 0);
          v17 = SdbWriteQWORDTag(a5, (unsigned __int16)v12, QWORDTag);
          break;
        case 24576:
          goto LABEL_27;
        case 28672:
          v18 = a5;
          v19 = SdbBeginWriteListTag(a5, (unsigned __int16)v12);
          if ( v19 )
          {
            v13 = -1073741823;
            for ( i = SdbGetFirstChild(a2, a3); ; i = SdbGetNextChild(a2, a3, v21) )
            {
              v21 = i;
              if ( !i )
                break;
              v13 = SdbpCopyTagidToPdb(v57, a2, i, a4, v18, a3);
              if ( v13 < 0 )
                return (unsigned int)v13;
            }
            if ( (unsigned int)SdbEndWriteListTag(v18, v19) )
              return (unsigned int)v13;
            AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1130, "SdbEndWriteListTag failed");
          }
          else
          {
            AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1114, "SdbBeginWriteListTag failed.");
          }
          return (unsigned int)-1073741595;
        case 32768:
LABEL_27:
          StringTagPtr = SdbGetStringTagPtr(a2, a3);
          if ( !StringTagPtr )
          {
            AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1103, "Failed to read string from original pdb.");
            return (unsigned int)-1073741595;
          }
          v17 = SdbWriteStringTag(a5, (unsigned __int16)v12, StringTagPtr);
          break;
        case 36864:
          TagDataSize = SdbGetTagDataSize(a2, a3);
          if ( TagDataSize == 0x20000000 )
          {
            AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1141, "SdbGetTagDataSize returned unfinished tag size");
            return (unsigned int)-1073741595;
          }
          BinaryTagData = SdbGetBinaryTagData(a2, a3);
          v17 = SdbWriteBinaryTag(a5, (unsigned __int16)v12, BinaryTagData, TagDataSize);
          break;
        default:
          AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1159, "Unknown tag type encountered for tag: %x", v12);
          return (unsigned int)-1073741595;
      }
      return v17 == 0 ? 0xC00000E5 : 0;
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= 9 )
        goto LABEL_67;
      if ( word_180069670[j] == (_WORD)v12 )
        break;
    }
    DWORDTag = SdbReadDWORDTag(a2, a3, 0);
    if ( !DWORDTag )
    {
      AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1012, "Failed to read tagid from original pdb.");
      return (unsigned int)-1073741595;
    }
    v56 = 0;
    if ( !(unsigned int)SdbTagIDToTagRef(a1, a2, DWORDTag, &v56) )
    {
      AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1034, "Failed to get a TagRef for a reference tagid.");
      return (unsigned int)-1073741595;
    }
    v26 = a6;
    if ( a6 )
    {
      v27 = SdbGetTagFromTagID(a2, a6);
      if ( !v27 )
      {
        AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1042, "Failed to get a Tag for a parent tagid.");
        return (unsigned int)-1073741595;
      }
      for ( k = 0; ; ++k )
      {
        if ( k >= 0xD )
          goto LABEL_51;
        v29 = 2LL * (int)k;
        if ( WORD1(qword_1800695A0[v29]) == v27 )
          break;
      }
      v30 = &qword_1800695A0[v29];
      if ( !&qword_1800695A0[v29] )
      {
LABEL_51:
        AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1049, "Failed to find the merge info from the source ref parent.");
        return (unsigned int)-1073741595;
      }
      if ( !(unsigned int)SdbTagIDToTagRef(a1, a2, v26, &v58) )
      {
        AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1055, "Failed to get a TagRef for a parent tagid.");
        return (unsigned int)-1073741595;
      }
      LODWORD(v56) = SdbGetItemFromItemRef(
                       a1,
                       v58,
                       *((unsigned __int16 *)v30 + 4),
                       *((unsigned __int16 *)v30 + 2),
                       *(_WORD *)v30);
      if ( !(_DWORD)v56 )
      {
        AslLogCallPrintf(
          1,
          "SdbpCopyTagidToPdb",
          1065,
          "Failed to get a true definition TagRef for a candidate definition TagRef.");
        return (unsigned int)-1073741595;
      }
    }
    v31 = *(_QWORD *)(a4 + 16);
    HIDWORD(v56) = 0;
    ullMultiplier = v31;
    v58 = *(_DWORD *)(a5 + 20);
    if ( v31 >= *(_QWORD *)(a4 + 24) )
    {
      if ( v31 + 1 <= *(_QWORD *)(a4 + 24) )
      {
        v32 = -1073741811;
LABEL_72:
        LODWORD(v52) = v32;
        AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 1086, "RtlArrayAppend failed [%x]", v52);
        return (unsigned int)-1073741595;
      }
      v33 = *(_QWORD *)(a4 + 32) - 1LL;
      if ( *(_QWORD *)(a4 + 32) + v31 < v31 + 1
        || (v34 = *(_QWORD *)(a4 + 8), v35 = *(_QWORD *)(a4 + 24), Size = 0, ULongLongMult(v35, v34, &pullResult) < 0)
        || (v37 = v36 & ~v33, ULongLongMult(v37, *(_QWORD *)(a4 + 8), &Size) < 0) )
      {
        v32 = -1073741675;
        goto LABEL_72;
      }
      v38 = *(void **)(a4 + 40);
      v39 = Size;
      v40 = *(void **)a4;
      if ( v38 )
      {
        Heap = RtlReAllocateHeap(v40, 0, v38, Size);
      }
      else
      {
        v41 = RtlAllocateHeap(v40, 0, Size);
        Heap = v41;
        if ( v41 )
          memset_0(v41, 0, v39);
      }
      if ( !Heap )
      {
        v32 = -1073741801;
        goto LABEL_72;
      }
      v31 = ullMultiplier;
      *(_QWORD *)(a4 + 40) = Heap;
      *(_QWORD *)(a4 + 24) = v37;
    }
    v44 = *(_QWORD *)(a4 + 8);
    Size = 0;
    if ( ULongLongMult(v44, v31, &Size) >= 0 )
    {
      v48 = *(_QWORD *)(a4 + 40) + Size;
      if ( v48 >= *(_QWORD *)(a4 + 40) )
      {
        v49 = *v45 + 1LL;
        *(_QWORD *)v48 = v56;
        *v46 = v49;
        *(_DWORD *)(v48 + 8) = v47;
LABEL_67:
        v43 = SdbReadDWORDTag(a2, a3, 0);
        v17 = SdbWriteDWORDTag(a5, (unsigned __int16)v12, v43);
        return v17 == 0 ? 0xC00000E5 : 0;
      }
    }
    v32 = -1073741675;
    goto LABEL_72;
  }
  AslLogCallPrintf(1, "SdbpCopyTagidToPdb", 979, "SdbGetTagFromTagID failed to get the tag from the tagid");
  return (unsigned int)-1073741595;
}

```

## disassembly

```asm
0x180038978  mov     [rsp-38h+arg_8], rbx
0x18003897d  mov     [rsp-38h+arg_0], rcx
0x180038982  push    rbp
0x180038983  push    rsi
0x180038984  push    rdi
0x180038985  push    r12
0x180038987  push    r13
0x180038989  push    r14
0x18003898b  push    r15
0x18003898d  mov     rbp, rsp
0x180038990  sub     rsp, 60h
0x180038994  xor     r15d, r15d
0x180038997  mov     r14, r9
0x18003899a  mov     esi, r8d
0x18003899d  mov     rdi, rdx
0x1800389a0  mov     r13, rcx
0x1800389a3  test    r8d, r8d
0x1800389a6  jnz     short loc_1800389AF
0x1800389a8  xor     eax, eax
0x1800389aa  jmp     loc_180038EC3
0x1800389af  mov     edx, esi
0x1800389b1  mov     [rbp+arg_10], r15d
0x1800389b5  mov     rcx, rdi
0x1800389b8  call    SdbGetTagFromTagID
0x1800389bd  movzx   ebx, ax
0x1800389c0  test    bx, bx
0x1800389c3  jnz     short loc_1800389ED
0x1800389c5  lea     r9, aSdbgettagfromt_0; "SdbGetTagFromTagID failed to get the ta"...
0x1800389cc  mov     r8d, 3D3h
0x1800389d2  lea     rdx, aSdbpcopytagidt; "SdbpCopyTagidToPdb"
0x1800389d9  mov     ecx, 1
0x1800389de  call    AslLogCallPrintf
0x1800389e3  mov     ebx, 0C00000E5h
0x1800389e8  jmp     loc_180038EC1
0x1800389ed  mov     eax, ebx
0x1800389ef  and     eax, 0F000h
0x1800389f4  cmp     eax, 1000h
0x1800389f9  jz      loc_180038EA8
0x1800389ff  cmp     eax, 2000h
0x180038a04  jz      loc_180038E8A
0x180038a0a  cmp     eax, 3000h
0x180038a0f  jz      loc_180038E6B
0x180038a15  cmp     eax, 4000h
0x180038a1a  jz      loc_180038B99
0x180038a20  cmp     eax, 5000h
0x180038a25  jz      loc_180038B78
0x180038a2b  cmp     eax, 6000h
0x180038a30  jz      loc_180038B43
0x180038a36  cmp     eax, 7000h
0x180038a3b  jz      short loc_180038AAC
0x180038a3d  cmp     eax, 8000h
0x180038a42  jz      loc_180038B43
0x180038a48  cmp     eax, 9000h
0x180038a4d  jz      short loc_180038A65
0x180038a4f  mov     dword ptr [rsp+60h+var_40], ebx
0x180038a53  lea     r9, aUnknownTagType; "Unknown tag type encountered for tag: %"...
0x180038a5a  mov     r8d, 487h
0x180038a60  jmp     loc_180038E55
0x180038a65  mov     edx, esi
0x180038a67  mov     rcx, rdi
0x180038a6a  call    SdbGetTagDataSize
0x180038a6f  mov     r14d, eax
0x180038a72  cmp     eax, 20000000h
0x180038a77  jnz     short loc_180038A8B
0x180038a79  lea     r9, aSdbgettagdatas_1; "SdbGetTagDataSize returned unfinished t"...
0x180038a80  mov     r8d, 475h
0x180038a86  jmp     loc_1800389D2
0x180038a8b  mov     edx, esi
0x180038a8d  mov     rcx, rdi
0x180038a90  call    SdbGetBinaryTagData
0x180038a95  mov     rcx, [rbp+arg_20]
0x180038a99  mov     r9d, r14d
0x180038a9c  mov     r8, rax
0x180038a9f  movzx   edx, bx
0x180038aa2  call    SdbWriteBinaryTag
0x180038aa7  jmp     loc_180038EB4
0x180038aac  mov     r12, [rbp+arg_20]
0x180038ab0  movzx   edx, bx
0x180038ab3  mov     rcx, r12
0x180038ab6  call    SdbBeginWriteListTag
0x180038abb  mov     r13d, eax
0x180038abe  test    eax, eax
0x180038ac0  jnz     short loc_180038AD4
0x180038ac2  lea     r9, aSdbbeginwritel_0; "SdbBeginWriteListTag failed."
0x180038ac9  mov     r8d, 45Ah
0x180038acf  jmp     loc_1800389D2
0x180038ad4  mov     edx, esi
0x180038ad6  mov     rcx, rdi
0x180038ad9  mov     ebx, 0C0000001h
0x180038ade  call    SdbGetFirstChild
0x180038ae3  mov     r15d, eax
0x180038ae6  test    eax, eax
0x180038ae8  jz      short loc_180038B1E
0x180038aea  mov     rcx, [rbp+arg_0]
0x180038aee  mov     r9, r14
0x180038af1  mov     [rsp+60h+var_38], esi
0x180038af5  mov     r8d, eax
0x180038af8  mov     rdx, rdi
0x180038afb  mov     [rsp+60h+var_40], r12
0x180038b00  call    SdbpCopyTagidToPdb
0x180038b05  mov     ebx, eax
0x180038b07  test    eax, eax
0x180038b09  js      loc_180038EC1
0x180038b0f  mov     r8d, r15d
0x180038b12  mov     edx, esi
0x180038b14  mov     rcx, rdi
0x180038b17  call    SdbGetNextChild
0x180038b1c  jmp     short loc_180038AE3
0x180038b1e  mov     edx, r13d
0x180038b21  mov     rcx, r12
0x180038b24  call    SdbEndWriteListTag
0x180038b29  test    eax, eax
0x180038b2b  jnz     loc_180038EC1
0x180038b31  lea     r9, aSdbendwritelis_0; "SdbEndWriteListTag failed"
0x180038b38  mov     r8d, 46Ah
0x180038b3e  jmp     loc_1800389D2
0x180038b43  mov     edx, esi
0x180038b45  mov     rcx, rdi
0x180038b48  call    SdbGetStringTagPtr
0x180038b4d  test    rax, rax
0x180038b50  jnz     short loc_180038B64
0x180038b52  lea     r9, aFailedToReadSt; "Failed to read string from original pdb"...
0x180038b59  mov     r8d, 44Fh
0x180038b5f  jmp     loc_1800389D2
0x180038b64  mov     rcx, [rbp+arg_20]
0x180038b68  mov     r8, rax
0x180038b6b  movzx   edx, bx
0x180038b6e  call    SdbWriteStringTag
0x180038b73  jmp     loc_180038EB4
0x180038b78  xor     r8d, r8d
0x180038b7b  mov     edx, esi
0x180038b7d  mov     rcx, rdi
0x180038b80  call    SdbReadQWORDTag
0x180038b85  mov     rcx, [rbp+arg_20]
0x180038b89  mov     r8, rax
0x180038b8c  movzx   edx, bx
0x180038b8f  call    SdbWriteQWORDTag
0x180038b94  jmp     loc_180038EB4
0x180038b99  mov     rax, r15
0x180038b9c  lea     rcx, __ImageBase
0x180038ba3  cmp     rax, 9
0x180038ba7  jnb     loc_180038DDD
0x180038bad  cmp     ds:rva word_180069670[rcx+rax*2], bx
0x180038bb5  jz      short loc_180038BBC
0x180038bb7  inc     rax
0x180038bba  jmp     short loc_180038BA3
0x180038bbc  xor     r8d, r8d
0x180038bbf  mov     edx, esi
0x180038bc1  mov     rcx, rdi
0x180038bc4  call    SdbReadDWORDTag
0x180038bc9  test    eax, eax
0x180038bcb  jnz     short loc_180038BDF
0x180038bcd  lea     r9, aFailedToReadTa_1; "Failed to read tagid from original pdb."
0x180038bd4  mov     r8d, 3F4h
0x180038bda  jmp     loc_1800389D2
0x180038bdf  xor     ecx, ecx
0x180038be1  lea     r9, [rbp+var_18]
0x180038be5  mov     [rbp+var_18], rcx
0x180038be9  mov     r8d, eax
0x180038bec  mov     rcx, r13
0x180038bef  mov     rdx, rdi
0x180038bf2  call    SdbTagIDToTagRef
0x180038bf7  test    eax, eax
0x180038bf9  jnz     short loc_180038C0D
0x180038bfb  lea     r9, aFailedToGetATa; "Failed to get a TagRef for a reference "...
0x180038c02  mov     r8d, 40Ah
0x180038c08  jmp     loc_1800389D2
0x180038c0d  mov     r12d, [rbp+arg_28]
0x180038c11  test    r12d, r12d
0x180038c14  jz      loc_180038CE9
0x180038c1a  mov     edx, r12d
0x180038c1d  mov     rcx, rdi
0x180038c20  call    SdbGetTagFromTagID
0x180038c25  movzx   edx, ax
0x180038c28  cmp     r15w, ax
0x180038c2c  jnz     short loc_180038C40
0x180038c2e  lea     r9, aFailedToGetATa_0; "Failed to get a Tag for a parent tagid."
0x180038c35  mov     r8d, 412h
0x180038c3b  jmp     loc_1800389D2
0x180038c40  mov     eax, r15d
0x180038c43  lea     r8, __ImageBase
0x180038c4a  cmp     eax, 0Dh
0x180038c4d  jnb     loc_180038CD7
0x180038c53  movsxd  rcx, eax
0x180038c56  shl     rcx, 4
0x180038c5a  cmp     [rcx+r8+695A2h], dx
0x180038c63  jz      short loc_180038C69
0x180038c65  inc     eax
0x180038c67  jmp     short loc_180038C4A
0x180038c69  lea     r15, rva qword_1800695A0[r8]
0x180038c70  add     r15, rcx
0x180038c73  jz      short loc_180038CD7
0x180038c75  lea     r9, [rbp+arg_10]
0x180038c79  mov     r8d, r12d
0x180038c7c  mov     rdx, rdi
0x180038c7f  mov     rcx, r13
0x180038c82  call    SdbTagIDToTagRef
0x180038c87  test    eax, eax
0x180038c89  jnz     short loc_180038C9D
0x180038c8b  lea     r9, aFailedToGetATa_1; "Failed to get a TagRef for a parent tag"...
0x180038c92  mov     r8d, 41Fh
0x180038c98  jmp     loc_1800389D2
0x180038c9d  movzx   eax, word ptr [r15]
0x180038ca1  mov     rcx, r13
0x180038ca4  movzx   r9d, word ptr [r15+4]
0x180038ca9  movzx   r8d, word ptr [r15+8]
0x180038cae  mov     edx, [rbp+arg_10]
0x180038cb1  mov     word ptr [rsp+60h+var_40], ax
0x180038cb6  call    SdbGetItemFromItemRef
0x180038cbb  xor     r15d, r15d
0x180038cbe  mov     dword ptr [rbp+var_18], eax
0x180038cc1  test    eax, eax
0x180038cc3  jnz     short loc_180038CE9
0x180038cc5  lea     r9, aFailedToGetATr; "Failed to get a true definition TagRef "...
0x180038ccc  mov     r8d, 429h
0x180038cd2  jmp     loc_1800389D2
0x180038cd7  lea     r9, aFailedToFindTh; "Failed to find the merge info from the "...
0x180038cde  mov     r8d, 419h
0x180038ce4  jmp     loc_1800389D2
0x180038ce9  mov     r11, [rbp+arg_20]
0x180038ced  lea     r10, [r14+10h]
0x180038cf1  mov     rax, [r10]
0x180038cf4  mov     dword ptr [rbp+var_18+4], r15d
0x180038cf8  mov     [rbp+ullMultiplier], rax
0x180038cfc  mov     r11d, [r11+14h]
0x180038d00  mov     [rbp+arg_10], r11d
0x180038d04  cmp     rax, [r14+18h]
0x180038d08  jb      loc_180038DFE
0x180038d0e  lea     rcx, [rax+1]
0x180038d12  cmp     rcx, [r14+18h]
0x180038d16  ja      short loc_180038D22
0x180038d18  mov     eax, 0C000000Dh
0x180038d1d  jmp     loc_180038DD9
0x180038d22  mov     r12, [r14+20h]
0x180038d26  dec     r12
0x180038d29  lea     r9, [r12+rcx]
0x180038d2d  cmp     r9, rcx
0x180038d30  jb      loc_180038DD4
0x180038d36  mov     rdx, [r14+8]; ullMultiplier
0x180038d3a  lea     r8, [rbp+pullResult]; pullResult
0x180038d3e  mov     rcx, [r14+18h]; ullMultiplicand
0x180038d42  mov     [rbp+Size], r15
0x180038d46  call    ULongLongMult
0x180038d4b  test    eax, eax
0x180038d4d  js      loc_180038DD4
0x180038d53  mov     rdx, [r14+8]; ullMultiplier
0x180038d57  lea     r8, [rbp+Size]; pullResult
0x180038d5b  not     r12
0x180038d5e  and     r12, r9
0x180038d61  mov     rcx, r12; ullMultiplicand
0x180038d64  call    ULongLongMult
0x180038d69  test    eax, eax
0x180038d6b  js      short loc_180038DD4
0x180038d6d  mov     r8, [r14+28h]; Ptr
0x180038d71  xor     edx, edx; Flags
0x180038d73  mov     r13, [rbp+Size]
0x180038d77  mov     rcx, [r14]; Heap
0x180038d7a  test    r8, r8
0x180038d7d  jnz     short loc_180038D9F
0x180038d7f  mov     r8, r13; Size
0x180038d82  call    cs:__imp_RtlAllocateHeap
0x180038d88  mov     r15, rax
0x180038d8b  test    rax, rax
0x180038d8e  jz      short loc_180038DAB
0x180038d90  mov     r8, r13; Size
0x180038d93  xor     edx, edx; Val
0x180038d95  mov     rcx, rax; void *
0x180038d98  call    memset_0
0x180038d9d  jmp     short loc_180038DAB
0x180038d9f  mov     r9, r13; Size
0x180038da2  call    cs:__imp_RtlReAllocateHeap
0x180038da8  mov     r15, rax
0x180038dab  test    r15, r15
0x180038dae  jnz     short loc_180038DB7
0x180038db0  mov     eax, 0C0000017h
0x180038db5  jmp     short loc_180038DD9
0x180038db7  mov     rax, [rbp+ullMultiplier]
0x180038dbb  lea     r9, [r14+10h]
0x180038dbf  mov     r11d, [rbp+arg_10]
0x180038dc3  lea     r10, [r14+10h]
0x180038dc7  mov     [r14+28h], r15
0x180038dcb  xor     r15d, r15d
0x180038dce  mov     [r14+18h], r12
0x180038dd2  jmp     short loc_180038E01
0x180038dd4  mov     eax, 0C0000095h
0x180038dd9  test    eax, eax
0x180038ddb  jnz     short loc_180038E44
0x180038ddd  xor     r8d, r8d
0x180038de0  mov     edx, esi
0x180038de2  mov     rcx, rdi
0x180038de5  call    SdbReadDWORDTag
0x180038dea  mov     rcx, [rbp+arg_20]
0x180038dee  mov     r8d, eax
0x180038df1  movzx   edx, bx
0x180038df4  call    SdbWriteDWORDTag
0x180038df9  jmp     loc_180038EB4
0x180038dfe  mov     r9, r10
0x180038e01  mov     rcx, [r14+8]; ullMultiplicand
0x180038e05  lea     r8, [rbp+Size]; pullResult
0x180038e09  mov     rdx, rax; ullMultiplier
  ... truncated ...
```
