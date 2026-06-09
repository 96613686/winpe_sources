# AslPathWildcardFindFirst

- ea: `0x180034bb0`
- end: `0x180035110`
- name: `AslPathWildcardFindFirst`
- size: `1376`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting`

## callers

- `0x18004def0`

## callees

- `0x1800055e0`
- `0x1800056fc`
- `0x18000f114`
- `0x180018f20`
- `0x180023ae0`
- `0x1800245cc`
- `0x180024a14`
- `0x180024a80`
- `0x18002cf94`
- `0x18002e918`
- `0x18002ecb4`
- `0x180034bb0`
- `0x18003c2d0`
- `0x18003f11c`
- `0x180059175`
- `0x180059199`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180034e94`
- `ntdll!RtlReAllocateHeap` at `0x180035000`
- `ntdll!RtlReAllocateHeap` at `0x180034e94`
- `ntdll!RtlReAllocateHeap` at `0x180035000`
- `ntdll!RtlInitUnicodeString` at `0x180034f17`
- `ntdll!RtlInitUnicodeString` at `0x180034f17`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180034c47`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180034c47`
- `ntdll!RtlFreeHeap` at `0x180034eb6`
- `ntdll!RtlFreeHeap` at `0x180034eb6`
- `ntdll!RtlFreeUnicodeString` at `0x1800350b2`
- `ntdll!RtlFreeUnicodeString` at `0x1800350b2`
- `ntdll!RtlAllocateHeap` at `0x180034cd7`
- `ntdll!RtlAllocateHeap` at `0x180034dbe`
- `ntdll!RtlAllocateHeap` at `0x180034e74`
- `ntdll!RtlAllocateHeap` at `0x180034fe0`
- `ntdll!RtlAllocateHeap` at `0x180034cd7`
- `ntdll!RtlAllocateHeap` at `0x180034dbe`
- `ntdll!RtlAllocateHeap` at `0x180034e74`
- `ntdll!RtlAllocateHeap` at `0x180034fe0`

## string_xrefs

- `0x18003508c`: `AslpPathWildcardPushNode failed [%x]`
- `0x180034ee0`: `AslpPathWildcardInitStack`
- `0x180034c57`: `Failed to convert dos path to nt path [%x]`
- `0x180034d38`: `AslPathWildcardFindFirst`
- `0x18003509d`: `AslPathWildcardFindFirst`
- `0x180034c7c`: `AslPathCleanUstr failed [%x]`
- `0x180034d0d`: `RtlStringCbCopyNW failed [%x]`
- `0x180034d8f`: `RtlStringCbCopyNW failed [%x]`
- `0x180034d2b`: `Failed to split the wildcard path`
- `0x180034ef1`: `AslpPathWildcardInitStack failed [%x]`
- `0x180034f49`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindFirst(_WORD *a1, ULONGLONG a2, const wchar_t *a3, __int64 *a4)
{
  __int64 v6; // r13
  const WCHAR *v8; // r14
  int v9; // eax
  int Next; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  const WCHAR *Heap; // rax
  int v15; // eax
  int Leaves; // eax
  WCHAR *Buffer; // rcx
  int v18; // eax
  __int64 v19; // rdi
  int v20; // eax
  HRESULT v21; // eax
  ULONGLONG v22; // r10
  int v23; // r9d
  void *v24; // r8
  size_t v25; // rsi
  void *v26; // rcx
  PVOID v27; // rax
  PVOID v28; // rbx
  void *v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  int matched; // eax
  ULONGLONG v33; // r15
  __int64 v34; // rbx
  ULONGLONG v35; // rdx
  ULONGLONG v36; // rcx
  __int64 v37; // r9
  ULONGLONG v38; // rbx
  void *v39; // r8
  size_t v40; // r13
  void *v41; // rcx
  PVOID v42; // rax
  PVOID v43; // rsi
  ULONGLONG v44; // rcx
  _OWORD *v45; // rdx
  __int64 v46; // [rsp+20h] [rbp-60h]
  _DWORD *v47; // [rsp+30h] [rbp-50h] BYREF
  ULONGLONG pullResult; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  __int128 v51; // [rsp+60h] [rbp-20h] BYREF
  __int128 v52; // [rsp+70h] [rbp-10h]
  ULONGLONG Size; // [rsp+C8h] [rbp+48h] BYREF

  Size = a2;
  v6 = (__int64)a1;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 || !*a3 )
    return 3221225713LL;
  if ( !a4 )
    return 3221225714LL;
  *a4 = 0;
  *a1 = 0;
  v47 = 0;
  LOWORD(Size) = 0;
  UnicodeString = 0;
  v8 = 0;
  DestinationString = 0;
  v51 = 0;
  v52 = 0;
  v9 = RtlDosPathNameToNtPathName_U_WithStatus(a3, &UnicodeString, 0, 0);
  Next = v9;
  if ( v9 >= 0 )
  {
    v11 = AslPathCleanUstr(&UnicodeString);
    Next = v11;
    if ( v11 < 0 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2257, "AslPathCleanUstr failed [%x]", v11);
      goto LABEL_62;
    }
    v12 = RtlUShortAdd(UnicodeString.Length, 4, &Size);
    Next = v12;
    if ( v12 < 0 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2263, "RtlUShortAdd failed [%x]", v12);
      goto LABEL_62;
    }
    v13 = (unsigned __int16)Size;
    Heap = (const WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)Size);
    v8 = Heap;
    if ( !Heap )
      goto LABEL_14;
    v15 = RtlStringCbCopyNW(Heap, v13, UnicodeString.Buffer, UnicodeString.Length);
    Next = v15;
    if ( v15 < 0 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2275, "RtlStringCbCopyNW failed [%x]", v15);
      goto LABEL_62;
    }
    Leaves = AslpPathWildcardMakeLeaves(v8);
    if ( !Leaves )
    {
      Next = -1073741767;
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2293, "Failed to split the wildcard path");
      goto LABEL_62;
    }
    if ( Leaves == 1 )
    {
      Buffer = UnicodeString.Buffer;
      *a4 = -1;
      if ( (unsigned int)AslDoesFileExistNtPath(Buffer) )
      {
        v18 = RtlStringCchCopyW(v6, 260, a3);
        Next = v18;
        if ( v18 >= 0 )
          Next = 0;
        else
          AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2311, "RtlStringCbCopyNW failed [%x]", v18);
      }
      else
      {
        Next = -2147483642;
      }
      goto LABEL_62;
    }
    v47 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
    v19 = (__int64)v47;
    if ( !v47 )
    {
LABEL_14:
      Next = -1073741801;
      goto LABEL_62;
    }
    v20 = wcsncmp_0(a3, L"\\??\\", 4u);
    Size = 0;
    *v47 = v20 != 0;
    *(_QWORD *)(v19 + 8) = v8;
    v8 = 0;
    *(_OWORD *)(v19 + 16) = 0;
    *(_OWORD *)(v19 + 32) = 0;
    *(_OWORD *)(v19 + 48) = 0;
    *(_QWORD *)(v19 + 16) = NtCurrentPeb()->ProcessHeap;
    *(_QWORD *)(v19 + 48) = 16;
    *(_QWORD *)(v19 + 24) = 32;
    v21 = ULongLongMult(0, 0x20u, &pullResult);
    v23 = -1073741675;
    if ( v21 < 0 || ULongLongMult(v22, *(_QWORD *)(v19 + 24), &Size) < 0 )
    {
      Next = v23;
    }
    else
    {
      v24 = *(void **)(v19 + 56);
      v25 = Size;
      v26 = *(void **)(v19 + 16);
      if ( v24 )
      {
        v28 = RtlReAllocateHeap(v26, 0, v24, Size);
      }
      else
      {
        v27 = RtlAllocateHeap(v26, 0, Size);
        v28 = v27;
        if ( v27 )
          memset_0(v27, 0, v25);
      }
      if ( v28 )
      {
        *(_QWORD *)(v19 + 56) = v28;
        *(_QWORD *)(v19 + 40) = 16;
        goto LABEL_40;
      }
      Next = -1073741801;
    }
    v29 = *(void **)(v19 + 56);
    if ( v29 )
      RtlFreeHeap(*(HANDLE *)(v19 + 16), 0, v29);
    *(_OWORD *)(v19 + 16) = 0;
    *(_OWORD *)(v19 + 32) = 0;
    *(_OWORD *)(v19 + 48) = 0;
    if ( Next < 0 )
    {
      AslLogCallPrintf(1, "AslpPathWildcardInitStack", 2148, "RtlArrayInitialize failed [%x]", Next);
      v30 = "AslpPathWildcardInitStack failed [%x]";
      v31 = 2349;
LABEL_61:
      LODWORD(v46) = Next;
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", v31, v30, v46);
      goto LABEL_62;
    }
LABEL_40:
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v19 + 8));
    matched = AslpPathWildcardAllocMatchNode(
                (unsigned int)&v51,
                (unsigned int)&DestinationString,
                *(_QWORD *)(v19 + 8),
                1,
                0,
                0);
    Next = matched;
    if ( matched < 0 )
    {
      LODWORD(v46) = matched;
      AslLogCallPrintf(
        1,
        "AslPathWildcardFindFirst",
        2362,
        "AslpPathWildcardAllocMatchNode failed to create root of path [%x]",
        v46);
      goto LABEL_62;
    }
    v33 = *(_QWORD *)(v19 + 32);
    if ( v33 >= *(_QWORD *)(v19 + 40) )
    {
      if ( v33 + 1 <= *(_QWORD *)(v19 + 40) )
      {
        Next = -1073741811;
LABEL_60:
        v30 = "AslpPathWildcardPushNode failed [%x]";
        v31 = 2368;
        goto LABEL_61;
      }
      v34 = *(_QWORD *)(v19 + 48) - 1LL;
      if ( *(_QWORD *)(v19 + 48) + v33 < v33 + 1
        || (v35 = *(_QWORD *)(v19 + 24), v36 = *(_QWORD *)(v19 + 40), Size = 0, ULongLongMult(v36, v35, &pullResult) < 0)
        || (v38 = v37 & ~v34, ULongLongMult(v38, *(_QWORD *)(v19 + 24), &Size) < 0) )
      {
        Next = -1073741675;
        goto LABEL_60;
      }
      v39 = *(void **)(v19 + 56);
      v40 = Size;
      v41 = *(void **)(v19 + 16);
      if ( v39 )
      {
        v43 = RtlReAllocateHeap(v41, 0, v39, Size);
      }
      else
      {
        v42 = RtlAllocateHeap(v41, 0, Size);
        v43 = v42;
        if ( v42 )
          memset_0(v42, 0, v40);
      }
      v6 = (__int64)a1;
      if ( !v43 )
      {
        Next = -1073741801;
        goto LABEL_60;
      }
      *(_QWORD *)(v19 + 56) = v43;
      *(_QWORD *)(v19 + 40) = v38;
    }
    v44 = *(_QWORD *)(v19 + 24);
    Size = 0;
    if ( ULongLongMult(v44, v33, &Size) >= 0 )
    {
      v45 = (_OWORD *)(*(_QWORD *)(v19 + 56) + Size);
      if ( (unsigned __int64)v45 >= *(_QWORD *)(v19 + 56) )
      {
        *v45 = v51;
        v45[1] = v52;
        ++*(_QWORD *)(v19 + 32);
        *a4 = v19;
        v51 = 0;
        v52 = 0;
        Next = AslPathWildcardFindNext(v6, 260, v19);
        goto LABEL_62;
      }
    }
    Next = -1073741675;
    goto LABEL_60;
  }
  AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2246, "Failed to convert dos path to nt path [%x]", v9);
LABEL_62:
  RtlFreeUnicodeString(&UnicodeString);
  if ( v8 )
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
  if ( Next < 0 )
  {
    AslpPathWildcardFreeFindContext(&v47);
    AslpPathWildcardFreeMatchNode(&v51);
    *a4 = 0;
  }
  return (unsigned int)Next;
}

```

## disassembly

```asm
0x180034bb0  mov     [rsp-38h+arg_10], rbx
0x180034bb5  mov     [rsp-38h+Size], rdx
0x180034bba  mov     [rsp-38h+arg_0], rcx
0x180034bbf  push    rbp
0x180034bc0  push    rsi
0x180034bc1  push    rdi
0x180034bc2  push    r12
0x180034bc4  push    r13
0x180034bc6  push    r14
0x180034bc8  push    r15
0x180034bca  mov     rbp, rsp
0x180034bcd  sub     rsp, 80h
0x180034bd4  xor     r15d, r15d
0x180034bd7  mov     r12, r9
0x180034bda  mov     rsi, r8
0x180034bdd  mov     r13, rcx
0x180034be0  test    rcx, rcx
0x180034be3  jnz     short loc_180034BEF
0x180034be5  mov     eax, 0C00000EFh
0x180034bea  jmp     loc_1800350F5
0x180034bef  test    rsi, rsi
0x180034bf2  jz      loc_1800350F0
0x180034bf8  cmp     [r8], r15w
0x180034bfc  jz      loc_1800350F0
0x180034c02  test    r12, r12
0x180034c05  jnz     short loc_180034C11
0x180034c07  mov     eax, 0C00000F2h
0x180034c0c  jmp     loc_1800350F5
0x180034c11  xorps   xmm0, xmm0
0x180034c14  mov     [r9], r15
0x180034c17  xorps   xmm1, xmm1
0x180034c1a  mov     [rcx], r15w
0x180034c1e  xor     r9d, r9d
0x180034c21  mov     [rbp+var_50], r15
0x180034c25  mov     rcx, rsi
0x180034c28  mov     word ptr [rbp+Size], r15w
0x180034c2d  xor     r8d, r8d
0x180034c30  lea     rdx, [rbp+UnicodeString]
0x180034c34  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180034c38  mov     r14, r15
0x180034c3b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180034c3f  movups  [rbp+var_20], xmm1
0x180034c43  movups  [rbp+var_10], xmm1
0x180034c47  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180034c4d  mov     ebx, eax
0x180034c4f  test    eax, eax
0x180034c51  jns     short loc_180034C69
0x180034c53  mov     dword ptr [rsp+80h+var_60], eax
0x180034c57  lea     r9, aFailedToConver_17; "Failed to convert dos path to nt path ["...
0x180034c5e  mov     r8d, 8C6h
0x180034c64  jmp     loc_18003509D
0x180034c69  lea     rcx, [rbp+UnicodeString]
0x180034c6d  call    AslPathCleanUstr
0x180034c72  mov     ebx, eax
0x180034c74  test    eax, eax
0x180034c76  jns     short loc_180034C8E
0x180034c78  mov     dword ptr [rsp+80h+var_60], eax
0x180034c7c  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x180034c83  mov     r8d, 8D1h
0x180034c89  jmp     loc_18003509D
0x180034c8e  movzx   ecx, [rbp+UnicodeString.Length]
0x180034c92  lea     r8, [rbp+Size]
0x180034c96  mov     edx, 4
0x180034c9b  call    RtlUShortAdd
0x180034ca0  mov     ebx, eax
0x180034ca2  test    eax, eax
0x180034ca4  jns     short loc_180034CBC
0x180034ca6  mov     dword ptr [rsp+80h+var_60], eax
0x180034caa  lea     r9, aRtlushortaddFa_0; "RtlUShortAdd failed [%x]"
0x180034cb1  mov     r8d, 8D7h
0x180034cb7  jmp     loc_18003509D
0x180034cbc  mov     rcx, gs:60h
0x180034cc5  mov     edi, 8
0x180034cca  movzx   ebx, word ptr [rbp+Size]
0x180034cce  mov     edx, edi; Flags
0x180034cd0  mov     r8d, ebx; Size
0x180034cd3  mov     rcx, [rcx+30h]; HeapHandle
0x180034cd7  call    cs:__imp_RtlAllocateHeap
0x180034cdd  mov     r14, rax
0x180034ce0  test    rax, rax
0x180034ce3  jnz     short loc_180034CEF
0x180034ce5  mov     ebx, 0C0000017h
0x180034cea  jmp     loc_1800350AE
0x180034cef  movzx   r9d, [rbp+UnicodeString.Length]
0x180034cf4  mov     rdx, rbx
0x180034cf7  mov     r8, [rbp+UnicodeString.Buffer]
0x180034cfb  mov     rcx, r14
0x180034cfe  call    RtlStringCbCopyNW
0x180034d03  mov     ebx, eax
0x180034d05  test    eax, eax
0x180034d07  jns     short loc_180034D1F
0x180034d09  mov     dword ptr [rsp+80h+var_60], eax
0x180034d0d  lea     r9, aRtlstringcbcop_0; "RtlStringCbCopyNW failed [%x]"
0x180034d14  mov     r8d, 8E3h
0x180034d1a  jmp     loc_18003509D
0x180034d1f  mov     rcx, r14; SourceString
0x180034d22  call    AslpPathWildcardMakeLeaves
0x180034d27  test    eax, eax
0x180034d29  jnz     short loc_180034D51
0x180034d2b  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x180034d32  mov     r8d, 8F5h
0x180034d38  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x180034d3f  mov     ebx, 0C0000039h
0x180034d44  lea     ecx, [rax+1]
0x180034d47  call    AslLogCallPrintf
0x180034d4c  jmp     loc_1800350AE
0x180034d51  cmp     eax, 1
0x180034d54  jnz     short loc_180034DA9
0x180034d56  mov     rcx, [rbp+UnicodeString.Buffer]; FileName
0x180034d5a  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180034d62  call    AslDoesFileExistNtPath
0x180034d67  test    eax, eax
0x180034d69  jnz     short loc_180034D75
0x180034d6b  mov     ebx, 80000006h
0x180034d70  jmp     loc_1800350AE
0x180034d75  mov     r8, rsi
0x180034d78  mov     edx, 104h
0x180034d7d  mov     rcx, r13
0x180034d80  call    RtlStringCchCopyW
0x180034d85  mov     ebx, eax
0x180034d87  test    eax, eax
0x180034d89  jns     short loc_180034DA1
0x180034d8b  mov     dword ptr [rsp+80h+var_60], eax
0x180034d8f  lea     r9, aRtlstringcbcop_0; "RtlStringCbCopyNW failed [%x]"
0x180034d96  mov     r8d, 907h
0x180034d9c  jmp     loc_18003509D
0x180034da1  mov     ebx, r15d
0x180034da4  jmp     loc_1800350AE
0x180034da9  mov     rcx, gs:60h
0x180034db2  mov     r8d, 40h ; '@'; Size
0x180034db8  mov     edx, edi; Flags
0x180034dba  mov     rcx, [rcx+30h]; HeapHandle
0x180034dbe  call    cs:__imp_RtlAllocateHeap
0x180034dc4  mov     [rbp+var_50], rax
0x180034dc8  mov     rdi, rax
0x180034dcb  test    rax, rax
0x180034dce  jz      loc_180034CE5
0x180034dd4  mov     r8d, 4; MaxCount
0x180034dda  lea     rdx, asc_180067AF0; "\\??\\"
0x180034de1  mov     rcx, rsi; String1
0x180034de4  call    wcsncmp_0
0x180034de9  test    eax, eax
0x180034deb  mov     [rbp+Size], r15
0x180034def  mov     ecx, r15d
0x180034df2  lea     r8, [rbp+pullResult]; pullResult
0x180034df6  setnz   cl
0x180034df9  xorps   xmm0, xmm0
0x180034dfc  mov     [rdi], ecx
0x180034dfe  mov     r10d, 10h
0x180034e04  mov     [rdi+8], r14
0x180034e08  mov     r14, r15
0x180034e0b  movups  xmmword ptr [rdi+10h], xmm0
0x180034e0f  movups  xmmword ptr [rdi+20h], xmm0
0x180034e13  lea     edx, [r10+10h]; ullMultiplier
0x180034e17  movups  xmmword ptr [rdi+30h], xmm0
0x180034e1b  mov     rax, gs:60h
0x180034e24  mov     rcx, [rax+30h]
0x180034e28  mov     [rdi+10h], rcx
0x180034e2c  xor     ecx, ecx; ullMultiplicand
0x180034e2e  mov     [rdi+30h], r10
0x180034e32  mov     [rdi+18h], rdx
0x180034e36  call    ULongLongMult
0x180034e3b  mov     r9d, 0C0000095h
0x180034e41  test    eax, eax
0x180034e43  jns     short loc_180034E4A
0x180034e45  mov     ebx, r9d
0x180034e48  jmp     short loc_180034EA7
0x180034e4a  mov     rdx, [rdi+18h]; ullMultiplier
0x180034e4e  lea     r8, [rbp+Size]; pullResult
0x180034e52  mov     rcx, r10; ullMultiplicand
0x180034e55  call    ULongLongMult
0x180034e5a  test    eax, eax
0x180034e5c  js      short loc_180034E45
0x180034e5e  mov     r8, [rdi+38h]; Ptr
0x180034e62  xor     edx, edx; Flags
0x180034e64  mov     rsi, [rbp+Size]
0x180034e68  mov     rcx, [rdi+10h]; Heap
0x180034e6c  test    r8, r8
0x180034e6f  jnz     short loc_180034E91
0x180034e71  mov     r8, rsi; Size
0x180034e74  call    cs:__imp_RtlAllocateHeap
0x180034e7a  mov     rbx, rax
0x180034e7d  test    rax, rax
0x180034e80  jz      short loc_180034E9D
0x180034e82  mov     r8, rsi; Size
0x180034e85  xor     edx, edx; Val
0x180034e87  mov     rcx, rax; void *
0x180034e8a  call    memset_0
0x180034e8f  jmp     short loc_180034E9D
0x180034e91  mov     r9, rsi; Size
0x180034e94  call    cs:__imp_RtlReAllocateHeap
0x180034e9a  mov     rbx, rax
0x180034e9d  test    rbx, rbx
0x180034ea0  jnz     short loc_180034F03
0x180034ea2  mov     ebx, 0C0000017h
0x180034ea7  mov     r8, [rdi+38h]; P
0x180034eab  test    r8, r8
0x180034eae  jz      short loc_180034EBC
0x180034eb0  mov     rcx, [rdi+10h]; HeapHandle
0x180034eb4  xor     edx, edx; Flags
0x180034eb6  call    cs:__imp_RtlFreeHeap
0x180034ebc  xorps   xmm0, xmm0
0x180034ebf  movups  xmmword ptr [rdi+10h], xmm0
0x180034ec3  movups  xmmword ptr [rdi+20h], xmm0
0x180034ec7  movups  xmmword ptr [rdi+30h], xmm0
0x180034ecb  test    ebx, ebx
0x180034ecd  jns     short loc_180034F0F
0x180034ecf  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x180034ed6  mov     dword ptr [rsp+80h+var_60], ebx
0x180034eda  mov     r8d, 864h
0x180034ee0  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x180034ee7  mov     ecx, 1
0x180034eec  call    AslLogCallPrintf
0x180034ef1  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x180034ef8  mov     r8d, 92Dh
0x180034efe  jmp     loc_180035099
0x180034f03  mov     [rdi+38h], rbx
0x180034f07  mov     qword ptr [rdi+28h], 10h
0x180034f0f  mov     rdx, [rdi+8]; SourceString
0x180034f13  lea     rcx, [rbp+DestinationString]; DestinationString
0x180034f17  call    cs:__imp_RtlInitUnicodeString
0x180034f1d  mov     r8, [rdi+8]
0x180034f21  lea     rdx, [rbp+DestinationString]
0x180034f25  mov     r9d, 1
0x180034f2b  mov     [rsp+80h+var_58], r15w
0x180034f31  lea     rcx, [rbp+var_20]
0x180034f35  mov     [rsp+80h+var_60], r15
0x180034f3a  call    AslpPathWildcardAllocMatchNode
0x180034f3f  mov     ebx, eax
0x180034f41  test    eax, eax
0x180034f43  jns     short loc_180034F5B
0x180034f45  mov     dword ptr [rsp+80h+var_60], eax
0x180034f49  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x180034f50  mov     r8d, 93Ah
0x180034f56  jmp     loc_18003509D
0x180034f5b  mov     r15, [rdi+20h]
0x180034f5f  cmp     r15, [rdi+28h]
0x180034f63  jb      loc_180035028
0x180034f69  lea     rcx, [r15+1]
0x180034f6d  cmp     rcx, [rdi+28h]
0x180034f71  ja      short loc_180034F7D
0x180034f73  mov     ebx, 0C000000Dh
0x180034f78  jmp     loc_180035017
0x180034f7d  mov     rbx, [rdi+30h]
0x180034f81  dec     rbx
0x180034f84  lea     r9, [rbx+rcx]
0x180034f88  cmp     r9, rcx
0x180034f8b  jnb     short loc_180034F97
0x180034f8d  mov     ebx, 0C0000095h
0x180034f92  jmp     loc_180035017
0x180034f97  mov     rdx, [rdi+18h]; ullMultiplier
0x180034f9b  lea     r8, [rbp+pullResult]; pullResult
0x180034f9f  mov     rcx, [rdi+28h]; ullMultiplicand
0x180034fa3  mov     [rbp+Size], r14
0x180034fa7  call    ULongLongMult
0x180034fac  test    eax, eax
0x180034fae  js      short loc_180034F8D
0x180034fb0  mov     rdx, [rdi+18h]; ullMultiplier
0x180034fb4  lea     r8, [rbp+Size]; pullResult
0x180034fb8  not     rbx
0x180034fbb  and     rbx, r9
0x180034fbe  mov     rcx, rbx; ullMultiplicand
0x180034fc1  call    ULongLongMult
0x180034fc6  test    eax, eax
0x180034fc8  js      short loc_180034F8D
0x180034fca  mov     r8, [rdi+38h]; Ptr
0x180034fce  xor     edx, edx; Flags
0x180034fd0  mov     r13, [rbp+Size]
0x180034fd4  mov     rcx, [rdi+10h]; Heap
0x180034fd8  test    r8, r8
0x180034fdb  jnz     short loc_180034FFD
0x180034fdd  mov     r8, r13; Size
0x180034fe0  call    cs:__imp_RtlAllocateHeap
0x180034fe6  mov     rsi, rax
0x180034fe9  test    rax, rax
0x180034fec  jz      short loc_180035009
0x180034fee  mov     r8, r13; Size
0x180034ff1  xor     edx, edx; Val
0x180034ff3  mov     rcx, rax; void *
0x180034ff6  call    memset_0
0x180034ffb  jmp     short loc_180035009
0x180034ffd  mov     r9, r13; Size
0x180035000  call    cs:__imp_RtlReAllocateHeap
0x180035006  mov     rsi, rax
0x180035009  mov     r13, [rbp+arg_0]
0x18003500d  test    rsi, rsi
0x180035010  jnz     short loc_180035020
0x180035012  mov     ebx, 0C0000017h
0x180035017  xor     r15d, r15d
0x18003501a  test    ebx, ebx
0x18003501c  jns     short loc_180035064
0x18003501e  jmp     short loc_18003508C
0x180035020  mov     [rdi+38h], rsi
0x180035024  mov     [rdi+28h], rbx
0x180035028  mov     rcx, [rdi+18h]; ullMultiplicand
0x18003502c  lea     r8, [rbp+Size]; pullResult
0x180035030  mov     rdx, r15; ullMultiplier
0x180035033  mov     [rbp+Size], r14
0x180035037  call    ULongLongMult
0x18003503c  xor     r15d, r15d
  ... truncated ...
```
