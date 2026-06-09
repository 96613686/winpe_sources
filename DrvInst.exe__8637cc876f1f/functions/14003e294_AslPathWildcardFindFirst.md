# AslPathWildcardFindFirst

- ea: `0x14003e294`
- end: `0x14003e7f4`
- name: `AslPathWildcardFindFirst`
- size: `1376`
- prototype: `__int64 __fastcall(_WORD *, ULONGLONG, const wchar_t *, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting`

## callers

- `0x140031f20`

## callees

- `0x14002fea8`
- `0x1400344cc`
- `0x14003bf18`
- `0x14003c0c8`
- `0x14003c368`
- `0x14003da70`
- `0x14003e294`
- `0x14003e7fc`
- `0x14003f624`
- `0x14003f8b0`
- `0x14003f9a4`
- `0x14003fa00`
- `0x14003fd14`
- `0x14003fd84`
- `0x140045eea`
- `0x140045f02`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14003e5fb`
- `ntdll!RtlInitUnicodeString` at `0x14003e5fb`
- `ntdll!RtlFreeUnicodeString` at `0x14003e796`
- `ntdll!RtlFreeUnicodeString` at `0x14003e796`
- `ntdll!RtlFreeHeap` at `0x14003e59a`
- `ntdll!RtlFreeHeap` at `0x14003e59a`
- `ntdll!RtlReAllocateHeap` at `0x14003e578`
- `ntdll!RtlReAllocateHeap` at `0x14003e6e4`
- `ntdll!RtlReAllocateHeap` at `0x14003e578`
- `ntdll!RtlReAllocateHeap` at `0x14003e6e4`
- `ntdll!RtlAllocateHeap` at `0x14003e3bb`
- `ntdll!RtlAllocateHeap` at `0x14003e4a2`
- `ntdll!RtlAllocateHeap` at `0x14003e558`
- `ntdll!RtlAllocateHeap` at `0x14003e6c4`
- `ntdll!RtlAllocateHeap` at `0x14003e3bb`
- `ntdll!RtlAllocateHeap` at `0x14003e4a2`
- `ntdll!RtlAllocateHeap` at `0x14003e558`
- `ntdll!RtlAllocateHeap` at `0x14003e6c4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14003e32b`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14003e32b`

## string_xrefs

- `0x14003e5c4`: `AslpPathWildcardInitStack`
- `0x14003e41c`: `AslPathWildcardFindFirst`
- `0x14003e781`: `AslPathWildcardFindFirst`
- `0x14003e33b`: `Failed to convert dos path to nt path [%x]`
- `0x14003e360`: `AslPathCleanUstr failed [%x]`
- `0x14003e40f`: `Failed to split the wildcard path`
- `0x14003e3f1`: `RtlStringCbCopyNW failed [%x]`
- `0x14003e473`: `RtlStringCbCopyNW failed [%x]`
- `0x14003e62d`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`
- `0x14003e5d5`: `AslpPathWildcardInitStack failed [%x]`
- `0x14003e770`: `AslpPathWildcardPushNode failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindFirst(_WORD *a1, ULONGLONG a2, const wchar_t *a3, _QWORD *a4)
{
  _WORD *v6; // r13
  WCHAR *v8; // r14
  int v9; // eax
  int Next; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  WCHAR *Heap; // rax
  int v15; // eax
  int Leaves; // eax
  WCHAR *Buffer; // rcx
  int v18; // eax
  _DWORD *v19; // rdi
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
  v6 = a1;
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
    v11 = AslPathCleanUstr(&UnicodeString.Length);
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
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)Size);
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
    v19 = v47;
    if ( !v47 )
    {
LABEL_14:
      Next = -1073741801;
      goto LABEL_62;
    }
    v20 = wcsncmp_0(a3, L"\\??\\", 4u);
    Size = 0;
    *v47 = v20 != 0;
    *((_QWORD *)v19 + 1) = v8;
    v8 = 0;
    *((_OWORD *)v19 + 1) = 0;
    *((_OWORD *)v19 + 2) = 0;
    *((_OWORD *)v19 + 3) = 0;
    *((_QWORD *)v19 + 2) = NtCurrentPeb()->ProcessHeap;
    *((_QWORD *)v19 + 6) = 16;
    *((_QWORD *)v19 + 3) = 32;
    v21 = ULongLongMult(0, 0x20u, &pullResult);
    v23 = -1073741675;
    if ( v21 < 0 || ULongLongMult(v22, *((_QWORD *)v19 + 3), &Size) < 0 )
    {
      Next = v23;
    }
    else
    {
      v24 = (void *)*((_QWORD *)v19 + 7);
      v25 = Size;
      v26 = (void *)*((_QWORD *)v19 + 2);
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
        *((_QWORD *)v19 + 7) = v28;
        *((_QWORD *)v19 + 5) = 16;
        goto LABEL_40;
      }
      Next = -1073741801;
    }
    v29 = (void *)*((_QWORD *)v19 + 7);
    if ( v29 )
      RtlFreeHeap(*((HANDLE *)v19 + 2), 0, v29);
    *((_OWORD *)v19 + 1) = 0;
    *((_OWORD *)v19 + 2) = 0;
    *((_OWORD *)v19 + 3) = 0;
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
    RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v19 + 1));
    matched = AslpPathWildcardAllocMatchNode(
                (unsigned int)&v51,
                (unsigned int)&DestinationString,
                *((_QWORD *)v19 + 1),
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
    v33 = *((_QWORD *)v19 + 4);
    if ( v33 >= *((_QWORD *)v19 + 5) )
    {
      if ( v33 + 1 <= *((_QWORD *)v19 + 5) )
      {
        Next = -1073741811;
LABEL_60:
        v30 = "AslpPathWildcardPushNode failed [%x]";
        v31 = 2368;
        goto LABEL_61;
      }
      v34 = *((_QWORD *)v19 + 6) - 1LL;
      if ( *((_QWORD *)v19 + 6) + v33 < v33 + 1
        || (v35 = *((_QWORD *)v19 + 3), v36 = *((_QWORD *)v19 + 5), Size = 0, ULongLongMult(v36, v35, &pullResult) < 0)
        || (v38 = v37 & ~v34, ULongLongMult(v38, *((_QWORD *)v19 + 3), &Size) < 0) )
      {
        Next = -1073741675;
        goto LABEL_60;
      }
      v39 = (void *)*((_QWORD *)v19 + 7);
      v40 = Size;
      v41 = (void *)*((_QWORD *)v19 + 2);
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
      v6 = a1;
      if ( !v43 )
      {
        Next = -1073741801;
        goto LABEL_60;
      }
      *((_QWORD *)v19 + 7) = v43;
      *((_QWORD *)v19 + 5) = v38;
    }
    v44 = *((_QWORD *)v19 + 3);
    Size = 0;
    if ( ULongLongMult(v44, v33, &Size) >= 0 )
    {
      v45 = (_OWORD *)(*((_QWORD *)v19 + 7) + Size);
      if ( (unsigned __int64)v45 >= *((_QWORD *)v19 + 7) )
      {
        *v45 = v51;
        v45[1] = v52;
        ++*((_QWORD *)v19 + 4);
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
0x14003e294  mov     [rsp-38h+arg_10], rbx
0x14003e299  mov     [rsp-38h+Size], rdx
0x14003e29e  mov     [rsp-38h+arg_0], rcx
0x14003e2a3  push    rbp
0x14003e2a4  push    rsi
0x14003e2a5  push    rdi
0x14003e2a6  push    r12
0x14003e2a8  push    r13
0x14003e2aa  push    r14
0x14003e2ac  push    r15
0x14003e2ae  mov     rbp, rsp
0x14003e2b1  sub     rsp, 80h
0x14003e2b8  xor     r15d, r15d
0x14003e2bb  mov     r12, r9
0x14003e2be  mov     rsi, r8
0x14003e2c1  mov     r13, rcx
0x14003e2c4  test    rcx, rcx
0x14003e2c7  jnz     short loc_14003E2D3
0x14003e2c9  mov     eax, 0C00000EFh
0x14003e2ce  jmp     loc_14003E7D9
0x14003e2d3  test    rsi, rsi
0x14003e2d6  jz      loc_14003E7D4
0x14003e2dc  cmp     [r8], r15w
0x14003e2e0  jz      loc_14003E7D4
0x14003e2e6  test    r12, r12
0x14003e2e9  jnz     short loc_14003E2F5
0x14003e2eb  mov     eax, 0C00000F2h
0x14003e2f0  jmp     loc_14003E7D9
0x14003e2f5  xorps   xmm0, xmm0
0x14003e2f8  mov     [r9], r15
0x14003e2fb  xorps   xmm1, xmm1
0x14003e2fe  mov     [rcx], r15w
0x14003e302  xor     r9d, r9d
0x14003e305  mov     [rbp+var_50], r15
0x14003e309  mov     rcx, rsi
0x14003e30c  mov     word ptr [rbp+Size], r15w
0x14003e311  xor     r8d, r8d
0x14003e314  lea     rdx, [rbp+UnicodeString]
0x14003e318  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14003e31c  mov     r14, r15
0x14003e31f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14003e323  movups  [rbp+var_20], xmm1
0x14003e327  movups  [rbp+var_10], xmm1
0x14003e32b  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14003e331  mov     ebx, eax
0x14003e333  test    eax, eax
0x14003e335  jns     short loc_14003E34D
0x14003e337  mov     dword ptr [rsp+80h+var_60], eax
0x14003e33b  lea     r9, aFailedToConver_3; "Failed to convert dos path to nt path ["...
0x14003e342  mov     r8d, 8C6h
0x14003e348  jmp     loc_14003E781
0x14003e34d  lea     rcx, [rbp+UnicodeString]
0x14003e351  call    AslPathCleanUstr
0x14003e356  mov     ebx, eax
0x14003e358  test    eax, eax
0x14003e35a  jns     short loc_14003E372
0x14003e35c  mov     dword ptr [rsp+80h+var_60], eax
0x14003e360  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x14003e367  mov     r8d, 8D1h
0x14003e36d  jmp     loc_14003E781
0x14003e372  movzx   ecx, [rbp+UnicodeString.Length]
0x14003e376  lea     r8, [rbp+Size]
0x14003e37a  mov     edx, 4
0x14003e37f  call    RtlUShortAdd
0x14003e384  mov     ebx, eax
0x14003e386  test    eax, eax
0x14003e388  jns     short loc_14003E3A0
0x14003e38a  mov     dword ptr [rsp+80h+var_60], eax
0x14003e38e  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x14003e395  mov     r8d, 8D7h
0x14003e39b  jmp     loc_14003E781
0x14003e3a0  mov     rcx, gs:60h
0x14003e3a9  mov     edi, 8
0x14003e3ae  movzx   ebx, word ptr [rbp+Size]
0x14003e3b2  mov     edx, edi; Flags
0x14003e3b4  mov     r8d, ebx; Size
0x14003e3b7  mov     rcx, [rcx+30h]; HeapHandle
0x14003e3bb  call    cs:__imp_RtlAllocateHeap
0x14003e3c1  mov     r14, rax
0x14003e3c4  test    rax, rax
0x14003e3c7  jnz     short loc_14003E3D3
0x14003e3c9  mov     ebx, 0C0000017h
0x14003e3ce  jmp     loc_14003E792
0x14003e3d3  movzx   r9d, [rbp+UnicodeString.Length]
0x14003e3d8  mov     rdx, rbx
0x14003e3db  mov     r8, [rbp+UnicodeString.Buffer]
0x14003e3df  mov     rcx, r14
0x14003e3e2  call    RtlStringCbCopyNW
0x14003e3e7  mov     ebx, eax
0x14003e3e9  test    eax, eax
0x14003e3eb  jns     short loc_14003E403
0x14003e3ed  mov     dword ptr [rsp+80h+var_60], eax
0x14003e3f1  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x14003e3f8  mov     r8d, 8E3h
0x14003e3fe  jmp     loc_14003E781
0x14003e403  mov     rcx, r14; SourceString
0x14003e406  call    AslpPathWildcardMakeLeaves
0x14003e40b  test    eax, eax
0x14003e40d  jnz     short loc_14003E435
0x14003e40f  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x14003e416  mov     r8d, 8F5h
0x14003e41c  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x14003e423  mov     ebx, 0C0000039h
0x14003e428  lea     ecx, [rax+1]
0x14003e42b  call    AslLogCallPrintf
0x14003e430  jmp     loc_14003E792
0x14003e435  cmp     eax, 1
0x14003e438  jnz     short loc_14003E48D
0x14003e43a  mov     rcx, [rbp+UnicodeString.Buffer]; FileName
0x14003e43e  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x14003e446  call    AslDoesFileExistNtPath
0x14003e44b  test    eax, eax
0x14003e44d  jnz     short loc_14003E459
0x14003e44f  mov     ebx, 80000006h
0x14003e454  jmp     loc_14003E792
0x14003e459  mov     r8, rsi
0x14003e45c  mov     edx, 104h
0x14003e461  mov     rcx, r13
0x14003e464  call    RtlStringCchCopyW
0x14003e469  mov     ebx, eax
0x14003e46b  test    eax, eax
0x14003e46d  jns     short loc_14003E485
0x14003e46f  mov     dword ptr [rsp+80h+var_60], eax
0x14003e473  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x14003e47a  mov     r8d, 907h
0x14003e480  jmp     loc_14003E781
0x14003e485  mov     ebx, r15d
0x14003e488  jmp     loc_14003E792
0x14003e48d  mov     rcx, gs:60h
0x14003e496  mov     r8d, 40h ; '@'; Size
0x14003e49c  mov     edx, edi; Flags
0x14003e49e  mov     rcx, [rcx+30h]; HeapHandle
0x14003e4a2  call    cs:__imp_RtlAllocateHeap
0x14003e4a8  mov     [rbp+var_50], rax
0x14003e4ac  mov     rdi, rax
0x14003e4af  test    rax, rax
0x14003e4b2  jz      loc_14003E3C9
0x14003e4b8  mov     r8d, 4; MaxCount
0x14003e4be  lea     rdx, asc_140053D58; "\\??\\"
0x14003e4c5  mov     rcx, rsi; String1
0x14003e4c8  call    wcsncmp_0
0x14003e4cd  test    eax, eax
0x14003e4cf  mov     [rbp+Size], r15
0x14003e4d3  mov     ecx, r15d
0x14003e4d6  lea     r8, [rbp+pullResult]; pullResult
0x14003e4da  setnz   cl
0x14003e4dd  xorps   xmm0, xmm0
0x14003e4e0  mov     [rdi], ecx
0x14003e4e2  mov     r10d, 10h
0x14003e4e8  mov     [rdi+8], r14
0x14003e4ec  mov     r14, r15
0x14003e4ef  movups  xmmword ptr [rdi+10h], xmm0
0x14003e4f3  movups  xmmword ptr [rdi+20h], xmm0
0x14003e4f7  lea     edx, [r10+10h]; ullMultiplier
0x14003e4fb  movups  xmmword ptr [rdi+30h], xmm0
0x14003e4ff  mov     rax, gs:60h
0x14003e508  mov     rcx, [rax+30h]
0x14003e50c  mov     [rdi+10h], rcx
0x14003e510  xor     ecx, ecx; ullMultiplicand
0x14003e512  mov     [rdi+30h], r10
0x14003e516  mov     [rdi+18h], rdx
0x14003e51a  call    ULongLongMult
0x14003e51f  mov     r9d, 0C0000095h
0x14003e525  test    eax, eax
0x14003e527  jns     short loc_14003E52E
0x14003e529  mov     ebx, r9d
0x14003e52c  jmp     short loc_14003E58B
0x14003e52e  mov     rdx, [rdi+18h]; ullMultiplier
0x14003e532  lea     r8, [rbp+Size]; pullResult
0x14003e536  mov     rcx, r10; ullMultiplicand
0x14003e539  call    ULongLongMult
0x14003e53e  test    eax, eax
0x14003e540  js      short loc_14003E529
0x14003e542  mov     r8, [rdi+38h]; Ptr
0x14003e546  xor     edx, edx; Flags
0x14003e548  mov     rsi, [rbp+Size]
0x14003e54c  mov     rcx, [rdi+10h]; Heap
0x14003e550  test    r8, r8
0x14003e553  jnz     short loc_14003E575
0x14003e555  mov     r8, rsi; Size
0x14003e558  call    cs:__imp_RtlAllocateHeap
0x14003e55e  mov     rbx, rax
0x14003e561  test    rax, rax
0x14003e564  jz      short loc_14003E581
0x14003e566  mov     r8, rsi; Size
0x14003e569  xor     edx, edx; Val
0x14003e56b  mov     rcx, rax; void *
0x14003e56e  call    memset_0
0x14003e573  jmp     short loc_14003E581
0x14003e575  mov     r9, rsi; Size
0x14003e578  call    cs:__imp_RtlReAllocateHeap
0x14003e57e  mov     rbx, rax
0x14003e581  test    rbx, rbx
0x14003e584  jnz     short loc_14003E5E7
0x14003e586  mov     ebx, 0C0000017h
0x14003e58b  mov     r8, [rdi+38h]; P
0x14003e58f  test    r8, r8
0x14003e592  jz      short loc_14003E5A0
0x14003e594  mov     rcx, [rdi+10h]; HeapHandle
0x14003e598  xor     edx, edx; Flags
0x14003e59a  call    cs:__imp_RtlFreeHeap
0x14003e5a0  xorps   xmm0, xmm0
0x14003e5a3  movups  xmmword ptr [rdi+10h], xmm0
0x14003e5a7  movups  xmmword ptr [rdi+20h], xmm0
0x14003e5ab  movups  xmmword ptr [rdi+30h], xmm0
0x14003e5af  test    ebx, ebx
0x14003e5b1  jns     short loc_14003E5F3
0x14003e5b3  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x14003e5ba  mov     dword ptr [rsp+80h+var_60], ebx
0x14003e5be  mov     r8d, 864h
0x14003e5c4  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x14003e5cb  mov     ecx, 1
0x14003e5d0  call    AslLogCallPrintf
0x14003e5d5  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x14003e5dc  mov     r8d, 92Dh
0x14003e5e2  jmp     loc_14003E77D
0x14003e5e7  mov     [rdi+38h], rbx
0x14003e5eb  mov     qword ptr [rdi+28h], 10h
0x14003e5f3  mov     rdx, [rdi+8]; SourceString
0x14003e5f7  lea     rcx, [rbp+DestinationString]; DestinationString
0x14003e5fb  call    cs:__imp_RtlInitUnicodeString
0x14003e601  mov     r8, [rdi+8]
0x14003e605  lea     rdx, [rbp+DestinationString]
0x14003e609  mov     r9d, 1
0x14003e60f  mov     [rsp+80h+var_58], r15w
0x14003e615  lea     rcx, [rbp+var_20]
0x14003e619  mov     [rsp+80h+var_60], r15
0x14003e61e  call    AslpPathWildcardAllocMatchNode
0x14003e623  mov     ebx, eax
0x14003e625  test    eax, eax
0x14003e627  jns     short loc_14003E63F
0x14003e629  mov     dword ptr [rsp+80h+var_60], eax
0x14003e62d  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x14003e634  mov     r8d, 93Ah
0x14003e63a  jmp     loc_14003E781
0x14003e63f  mov     r15, [rdi+20h]
0x14003e643  cmp     r15, [rdi+28h]
0x14003e647  jb      loc_14003E70C
0x14003e64d  lea     rcx, [r15+1]
0x14003e651  cmp     rcx, [rdi+28h]
0x14003e655  ja      short loc_14003E661
0x14003e657  mov     ebx, 0C000000Dh
0x14003e65c  jmp     loc_14003E6FB
0x14003e661  mov     rbx, [rdi+30h]
0x14003e665  dec     rbx
0x14003e668  lea     r9, [rbx+rcx]
0x14003e66c  cmp     r9, rcx
0x14003e66f  jnb     short loc_14003E67B
0x14003e671  mov     ebx, 0C0000095h
0x14003e676  jmp     loc_14003E6FB
0x14003e67b  mov     rdx, [rdi+18h]; ullMultiplier
0x14003e67f  lea     r8, [rbp+pullResult]; pullResult
0x14003e683  mov     rcx, [rdi+28h]; ullMultiplicand
0x14003e687  mov     [rbp+Size], r14
0x14003e68b  call    ULongLongMult
0x14003e690  test    eax, eax
0x14003e692  js      short loc_14003E671
0x14003e694  mov     rdx, [rdi+18h]; ullMultiplier
0x14003e698  lea     r8, [rbp+Size]; pullResult
0x14003e69c  not     rbx
0x14003e69f  and     rbx, r9
0x14003e6a2  mov     rcx, rbx; ullMultiplicand
0x14003e6a5  call    ULongLongMult
0x14003e6aa  test    eax, eax
0x14003e6ac  js      short loc_14003E671
0x14003e6ae  mov     r8, [rdi+38h]; Ptr
0x14003e6b2  xor     edx, edx; Flags
0x14003e6b4  mov     r13, [rbp+Size]
0x14003e6b8  mov     rcx, [rdi+10h]; Heap
0x14003e6bc  test    r8, r8
0x14003e6bf  jnz     short loc_14003E6E1
0x14003e6c1  mov     r8, r13; Size
0x14003e6c4  call    cs:__imp_RtlAllocateHeap
0x14003e6ca  mov     rsi, rax
0x14003e6cd  test    rax, rax
0x14003e6d0  jz      short loc_14003E6ED
0x14003e6d2  mov     r8, r13; Size
0x14003e6d5  xor     edx, edx; Val
0x14003e6d7  mov     rcx, rax; void *
0x14003e6da  call    memset_0
0x14003e6df  jmp     short loc_14003E6ED
0x14003e6e1  mov     r9, r13; Size
0x14003e6e4  call    cs:__imp_RtlReAllocateHeap
0x14003e6ea  mov     rsi, rax
0x14003e6ed  mov     r13, [rbp+arg_0]
0x14003e6f1  test    rsi, rsi
0x14003e6f4  jnz     short loc_14003E704
0x14003e6f6  mov     ebx, 0C0000017h
0x14003e6fb  xor     r15d, r15d
0x14003e6fe  test    ebx, ebx
0x14003e700  jns     short loc_14003E748
0x14003e702  jmp     short loc_14003E770
0x14003e704  mov     [rdi+38h], rsi
0x14003e708  mov     [rdi+28h], rbx
0x14003e70c  mov     rcx, [rdi+18h]; ullMultiplicand
0x14003e710  lea     r8, [rbp+Size]; pullResult
0x14003e714  mov     rdx, r15; ullMultiplier
0x14003e717  mov     [rbp+Size], r14
0x14003e71b  call    ULongLongMult
0x14003e720  xor     r15d, r15d
  ... truncated ...
```
