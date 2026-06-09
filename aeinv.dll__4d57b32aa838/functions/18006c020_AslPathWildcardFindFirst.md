# AslPathWildcardFindFirst

- ea: `0x18006c020`
- end: `0x18006c582`
- name: `AslPathWildcardFindFirst`
- size: `1378`
- prototype: `__int64 __fastcall(_WORD *, SIZE_T, const wchar_t *, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting`

## callers

- `0x180121230`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x18002256c`
- `0x1800303b0`
- `0x18004afb0`
- `0x18004ba9c`
- `0x18005a8bc`
- `0x18006a724`
- `0x18006b80c`
- `0x18006c020`
- `0x18006f9ec`
- `0x18006fc78`
- `0x18006fd6c`
- `0x18006fdc8`
- `0x1800701fc`
- `0x180125478`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006c525`
- `ntdll!RtlFreeUnicodeString` at `0x18006c525`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006c0b7`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006c0b7`
- `ntdll!RtlAllocateHeap` at `0x18006c147`
- `ntdll!RtlAllocateHeap` at `0x18006c22d`
- `ntdll!RtlAllocateHeap` at `0x18006c147`
- `ntdll!RtlAllocateHeap` at `0x18006c22d`
- `ntdll!RtlInitUnicodeString` at `0x18006c38b`
- `ntdll!RtlInitUnicodeString` at `0x18006c38b`
- `KERNEL32!HeapReAlloc` at `0x18006c308`
- `KERNEL32!HeapReAlloc` at `0x18006c474`
- `KERNEL32!HeapReAlloc` at `0x18006c308`
- `KERNEL32!HeapReAlloc` at `0x18006c474`
- `KERNEL32!GetProcessHeap` at `0x18006c278`
- `KERNEL32!GetProcessHeap` at `0x18006c278`
- `KERNEL32!HeapAlloc` at `0x18006c2e8`
- `KERNEL32!HeapAlloc` at `0x18006c454`
- `KERNEL32!HeapAlloc` at `0x18006c2e8`
- `KERNEL32!HeapAlloc` at `0x18006c454`
- `KERNEL32!HeapFree` at `0x18006c32a`
- `KERNEL32!HeapFree` at `0x18006c32a`

## string_xrefs

- `0x18006c4ff`: `AslpPathWildcardPushNode failed [%x]`
- `0x18006c354`: `AslpPathWildcardInitStack`
- `0x18006c0c7`: `Failed to convert dos path to nt path [%x]`
- `0x18006c1a8`: `AslPathWildcardFindFirst`
- `0x18006c510`: `AslPathWildcardFindFirst`
- `0x18006c0ec`: `AslPathCleanUstr failed [%x]`
- `0x18006c17d`: `RtlStringCbCopyNW failed [%x]`
- `0x18006c1fe`: `RtlStringCbCopyNW failed [%x]`
- `0x18006c19b`: `Failed to split the wildcard path`
- `0x18006c365`: `AslpPathWildcardInitStack failed [%x]`
- `0x18006c3bd`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=67
__int64 __fastcall AslPathWildcardFindFirst(_WORD *a1, SIZE_T a2, const wchar_t *a3, __int64 *a4)
{
  __int64 v6; // r12
  const WCHAR *v8; // r14
  int matched; // ebx
  const char *v10; // r9
  int v11; // r8d
  __int64 v12; // rbx
  const WCHAR *Heap; // rax
  int Leaves; // eax
  WCHAR *Buffer; // rcx
  __int64 v16; // rdi
  HANDLE ProcessHeap; // rax
  int v18; // eax
  unsigned __int64 v19; // r10
  int v20; // r9d
  void *v21; // r8
  SIZE_T v22; // rsi
  void *v23; // rcx
  void *v24; // rax
  LPVOID v25; // rbx
  void *v26; // r8
  unsigned __int64 v27; // r13
  __int64 v28; // rbx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rcx
  __int64 v31; // r9
  unsigned __int64 v32; // rbx
  void *v33; // r8
  SIZE_T v34; // r12
  void *v35; // rcx
  void *v36; // rax
  LPVOID v37; // rsi
  unsigned __int64 v38; // rcx
  _OWORD *v39; // rdx
  _DWORD *v40; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v41; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  __int128 v44; // [rsp+60h] [rbp-20h] BYREF
  __int128 v45; // [rsp+70h] [rbp-10h]
  SIZE_T dwBytes; // [rsp+C8h] [rbp+48h] BYREF

  dwBytes = a2;
  v6 = (__int64)a1;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 || !*a3 )
    return 3221225713LL;
  if ( !a4 )
    return 3221225714LL;
  *a4 = 0;
  *a1 = 0;
  v40 = 0;
  LOWORD(dwBytes) = 0;
  UnicodeString = 0;
  v8 = 0;
  DestinationString = 0;
  v44 = 0;
  v45 = 0;
  matched = RtlDosPathNameToNtPathName_U_WithStatus(a3, &UnicodeString, 0, 0);
  if ( matched < 0 )
  {
    v10 = "Failed to convert dos path to nt path [%x]";
    v11 = 2246;
LABEL_61:
    AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindFirst", v11, (_DWORD)v10);
    goto LABEL_62;
  }
  matched = AslPathCleanUstr(&UnicodeString);
  if ( matched < 0 )
  {
    v10 = "AslPathCleanUstr failed [%x]";
    v11 = 2257;
    goto LABEL_61;
  }
  matched = RtlUShortAdd(UnicodeString.Length, 4, &dwBytes);
  if ( matched < 0 )
  {
    v10 = "RtlUShortAdd failed [%x]";
    v11 = 2263;
    goto LABEL_61;
  }
  v12 = (unsigned __int16)dwBytes;
  Heap = (const WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)dwBytes);
  v8 = Heap;
  if ( !Heap )
    goto LABEL_14;
  matched = RtlStringCbCopyNW(Heap, v12, UnicodeString.Buffer, UnicodeString.Length);
  if ( matched < 0 )
  {
    v10 = "RtlStringCbCopyNW failed [%x]";
    v11 = 2275;
    goto LABEL_61;
  }
  Leaves = AslpPathWildcardMakeLeaves(v8);
  if ( !Leaves )
  {
    matched = -1073741767;
    AslLogCallPrintf(
      1,
      (unsigned int)"AslPathWildcardFindFirst",
      2293,
      (unsigned int)"Failed to split the wildcard path");
    goto LABEL_62;
  }
  if ( Leaves != 1 )
  {
    v40 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
    v16 = (__int64)v40;
    if ( !v40 )
    {
LABEL_14:
      matched = -1073741801;
      goto LABEL_62;
    }
    *v40 = wcsncmp_0(a3, L"\\??\\", 4u) != 0;
    *(_QWORD *)(v16 + 8) = v8;
    v8 = 0;
    *(_OWORD *)(v16 + 16) = 0;
    *(_OWORD *)(v16 + 32) = 0;
    *(_OWORD *)(v16 + 48) = 0;
    ProcessHeap = GetProcessHeap();
    *(_QWORD *)(v16 + 32) = 0;
    *(_QWORD *)(v16 + 16) = ProcessHeap;
    *(_QWORD *)(v16 + 48) = 16;
    *(_QWORD *)(v16 + 40) = 0;
    *(_QWORD *)(v16 + 56) = 0;
    *(_QWORD *)(v16 + 24) = 32;
    dwBytes = 0;
    v18 = ULongLongMult(0, 0x20u, &v41);
    v20 = -2147483637;
    if ( v18 < 0 || (int)ULongLongMult(v19, *(_QWORD *)(v16 + 24), &dwBytes) < 0 )
    {
      matched = v20;
    }
    else
    {
      v21 = *(void **)(v16 + 56);
      v22 = dwBytes;
      v23 = *(void **)(v16 + 16);
      if ( v21 )
      {
        v25 = HeapReAlloc(v23, 0, v21, dwBytes);
      }
      else
      {
        v24 = HeapAlloc(v23, 0, dwBytes);
        v25 = v24;
        if ( v24 )
          memset_0(v24, 0, v22);
      }
      if ( v25 )
      {
        *(_QWORD *)(v16 + 56) = v25;
        *(_QWORD *)(v16 + 40) = 16;
        goto LABEL_40;
      }
      matched = -2147024882;
    }
    v26 = *(void **)(v16 + 56);
    if ( v26 )
      HeapFree(*(HANDLE *)(v16 + 16), 0, v26);
    *(_OWORD *)(v16 + 16) = 0;
    *(_OWORD *)(v16 + 32) = 0;
    *(_OWORD *)(v16 + 48) = 0;
    if ( matched < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpPathWildcardInitStack",
        2148,
        (unsigned int)"RtlArrayInitialize failed [%x]");
      v10 = "AslpPathWildcardInitStack failed [%x]";
      v11 = 2349;
      goto LABEL_61;
    }
LABEL_40:
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v16 + 8));
    matched = AslpPathWildcardAllocMatchNode(
                (unsigned int)&v44,
                (unsigned int)&DestinationString,
                *(_QWORD *)(v16 + 8),
                1,
                0,
                0);
    if ( matched < 0 )
    {
      v10 = "AslpPathWildcardAllocMatchNode failed to create root of path [%x]";
      v11 = 2362;
      goto LABEL_61;
    }
    v27 = *(_QWORD *)(v16 + 32);
    if ( v27 >= *(_QWORD *)(v16 + 40) )
    {
      if ( v27 + 1 <= *(_QWORD *)(v16 + 40) )
      {
        matched = -2147024809;
        goto LABEL_60;
      }
      v28 = *(_QWORD *)(v16 + 48) - 1LL;
      if ( *(_QWORD *)(v16 + 48) + v27 < v27 + 1
        || (v29 = *(_QWORD *)(v16 + 24), v30 = *(_QWORD *)(v16 + 40),
                                         dwBytes = 0,
                                         (int)ULongLongMult(v30, v29, &v41) < 0)
        || (v32 = v31 & ~v28, (int)ULongLongMult(v32, *(_QWORD *)(v16 + 24), &dwBytes) < 0) )
      {
        matched = -2147483637;
        goto LABEL_60;
      }
      v33 = *(void **)(v16 + 56);
      v34 = dwBytes;
      v35 = *(void **)(v16 + 16);
      if ( v33 )
      {
        v37 = HeapReAlloc(v35, 0, v33, dwBytes);
      }
      else
      {
        v36 = HeapAlloc(v35, 0, dwBytes);
        v37 = v36;
        if ( v36 )
          memset_0(v36, 0, v34);
      }
      v6 = (__int64)a1;
      if ( !v37 )
      {
        matched = -2147024882;
        goto LABEL_60;
      }
      *(_QWORD *)(v16 + 56) = v37;
      *(_QWORD *)(v16 + 40) = v32;
    }
    v38 = *(_QWORD *)(v16 + 24);
    dwBytes = 0;
    if ( (int)ULongLongMult(v38, v27, &dwBytes) >= 0 )
    {
      v39 = (_OWORD *)(*(_QWORD *)(v16 + 56) + dwBytes);
      if ( (unsigned __int64)v39 >= *(_QWORD *)(v16 + 56) )
      {
        *v39 = v44;
        v39[1] = v45;
        ++*(_QWORD *)(v16 + 32);
        *a4 = v16;
        v44 = 0;
        v45 = 0;
        matched = AslPathWildcardFindNext(v6, 260, v16);
        goto LABEL_62;
      }
    }
    matched = -2147483637;
LABEL_60:
    v10 = "AslpPathWildcardPushNode failed [%x]";
    v11 = 2368;
    goto LABEL_61;
  }
  Buffer = UnicodeString.Buffer;
  *a4 = -1;
  if ( (unsigned int)AslDoesFileExistNtPath(Buffer) )
  {
    matched = RtlStringCchCopyW(v6, 260, a3);
    if ( matched < 0 )
    {
      v10 = "RtlStringCbCopyNW failed [%x]";
      v11 = 2311;
      goto LABEL_61;
    }
    matched = 0;
  }
  else
  {
    matched = -2147483642;
  }
LABEL_62:
  RtlFreeUnicodeString(&UnicodeString);
  if ( v8 )
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
  if ( matched < 0 )
  {
    AslpPathWildcardFreeFindContext(&v40);
    AslpPathWildcardFreeMatchNode(&v44);
    *a4 = 0;
  }
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x18006c020  mov     [rsp-38h+arg_10], rbx
0x18006c025  mov     [rsp-38h+dwBytes], rdx
0x18006c02a  mov     [rsp-38h+arg_0], rcx
0x18006c02f  push    rbp
0x18006c030  push    rsi
0x18006c031  push    rdi
0x18006c032  push    r12
0x18006c034  push    r13
0x18006c036  push    r14
0x18006c038  push    r15
0x18006c03a  mov     rbp, rsp
0x18006c03d  sub     rsp, 80h
0x18006c044  xor     r13d, r13d
0x18006c047  mov     r15, r9
0x18006c04a  mov     rsi, r8
0x18006c04d  mov     r12, rcx
0x18006c050  test    rcx, rcx
0x18006c053  jnz     short loc_18006C05F
0x18006c055  mov     eax, 0C00000EFh
0x18006c05a  jmp     loc_18006C567
0x18006c05f  test    rsi, rsi
0x18006c062  jz      loc_18006C562
0x18006c068  cmp     [r8], r13w
0x18006c06c  jz      loc_18006C562
0x18006c072  test    r15, r15
0x18006c075  jnz     short loc_18006C081
0x18006c077  mov     eax, 0C00000F2h
0x18006c07c  jmp     loc_18006C567
0x18006c081  xorps   xmm0, xmm0
0x18006c084  mov     [r9], r13
0x18006c087  xorps   xmm1, xmm1
0x18006c08a  mov     [rcx], r13w
0x18006c08e  xor     r9d, r9d
0x18006c091  mov     [rbp+var_50], r13
0x18006c095  mov     rcx, rsi
0x18006c098  mov     word ptr [rbp+dwBytes], r13w
0x18006c09d  xor     r8d, r8d
0x18006c0a0  lea     rdx, [rbp+UnicodeString]
0x18006c0a4  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18006c0a8  mov     r14, r13
0x18006c0ab  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006c0af  movups  [rbp+var_20], xmm1
0x18006c0b3  movups  [rbp+var_10], xmm1
0x18006c0b7  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18006c0bd  mov     ebx, eax
0x18006c0bf  test    eax, eax
0x18006c0c1  jns     short loc_18006C0D9
0x18006c0c3  mov     dword ptr [rsp+80h+var_60], eax
0x18006c0c7  lea     r9, aFailedToConver_2; "Failed to convert dos path to nt path ["...
0x18006c0ce  mov     r8d, 8C6h
0x18006c0d4  jmp     loc_18006C510
0x18006c0d9  lea     rcx, [rbp+UnicodeString]
0x18006c0dd  call    AslPathCleanUstr
0x18006c0e2  mov     ebx, eax
0x18006c0e4  test    eax, eax
0x18006c0e6  jns     short loc_18006C0FE
0x18006c0e8  mov     dword ptr [rsp+80h+var_60], eax
0x18006c0ec  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x18006c0f3  mov     r8d, 8D1h
0x18006c0f9  jmp     loc_18006C510
0x18006c0fe  movzx   ecx, [rbp+UnicodeString.Length]
0x18006c102  lea     r8, [rbp+dwBytes]
0x18006c106  mov     edx, 4
0x18006c10b  call    RtlUShortAdd
0x18006c110  mov     ebx, eax
0x18006c112  test    eax, eax
0x18006c114  jns     short loc_18006C12C
0x18006c116  mov     dword ptr [rsp+80h+var_60], eax
0x18006c11a  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x18006c121  mov     r8d, 8D7h
0x18006c127  jmp     loc_18006C510
0x18006c12c  mov     rcx, gs:60h
0x18006c135  mov     edi, 8
0x18006c13a  movzx   ebx, word ptr [rbp+dwBytes]
0x18006c13e  mov     edx, edi; Flags
0x18006c140  mov     r8d, ebx; Size
0x18006c143  mov     rcx, [rcx+30h]; HeapHandle
0x18006c147  call    cs:__imp_RtlAllocateHeap
0x18006c14d  mov     r14, rax
0x18006c150  test    rax, rax
0x18006c153  jnz     short loc_18006C15F
0x18006c155  mov     ebx, 0C0000017h
0x18006c15a  jmp     loc_18006C521
0x18006c15f  movzx   r9d, [rbp+UnicodeString.Length]
0x18006c164  mov     rdx, rbx
0x18006c167  mov     r8, [rbp+UnicodeString.Buffer]
0x18006c16b  mov     rcx, r14
0x18006c16e  call    RtlStringCbCopyNW
0x18006c173  mov     ebx, eax
0x18006c175  test    eax, eax
0x18006c177  jns     short loc_18006C18F
0x18006c179  mov     dword ptr [rsp+80h+var_60], eax
0x18006c17d  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x18006c184  mov     r8d, 8E3h
0x18006c18a  jmp     loc_18006C510
0x18006c18f  mov     rcx, r14; SourceString
0x18006c192  call    AslpPathWildcardMakeLeaves
0x18006c197  test    eax, eax
0x18006c199  jnz     short loc_18006C1C1
0x18006c19b  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x18006c1a2  mov     r8d, 8F5h
0x18006c1a8  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x18006c1af  mov     ebx, 0C0000039h
0x18006c1b4  lea     ecx, [rax+1]
0x18006c1b7  call    AslLogCallPrintf
0x18006c1bc  jmp     loc_18006C521
0x18006c1c1  cmp     eax, 1
0x18006c1c4  jnz     short loc_18006C218
0x18006c1c6  mov     rcx, [rbp+UnicodeString.Buffer]; FileName
0x18006c1ca  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18006c1d1  call    AslDoesFileExistNtPath
0x18006c1d6  test    eax, eax
0x18006c1d8  jnz     short loc_18006C1E4
0x18006c1da  mov     ebx, 80000006h
0x18006c1df  jmp     loc_18006C521
0x18006c1e4  mov     r8, rsi
0x18006c1e7  mov     edx, 104h
0x18006c1ec  mov     rcx, r12
0x18006c1ef  call    RtlStringCchCopyW
0x18006c1f4  mov     ebx, eax
0x18006c1f6  test    eax, eax
0x18006c1f8  jns     short loc_18006C210
0x18006c1fa  mov     dword ptr [rsp+80h+var_60], eax
0x18006c1fe  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x18006c205  mov     r8d, 907h
0x18006c20b  jmp     loc_18006C510
0x18006c210  mov     ebx, r13d
0x18006c213  jmp     loc_18006C521
0x18006c218  mov     rcx, gs:60h
0x18006c221  mov     r8d, 40h ; '@'; Size
0x18006c227  mov     edx, edi; Flags
0x18006c229  mov     rcx, [rcx+30h]; HeapHandle
0x18006c22d  call    cs:__imp_RtlAllocateHeap
0x18006c233  mov     [rbp+var_50], rax
0x18006c237  mov     rdi, rax
0x18006c23a  test    rax, rax
0x18006c23d  jz      loc_18006C155
0x18006c243  mov     r8d, 4; MaxCount
0x18006c249  lea     rdx, asc_18013CFF8; "\\??\\"
0x18006c250  mov     rcx, rsi; String1
0x18006c253  call    wcsncmp_0
0x18006c258  xorps   xmm0, xmm0
0x18006c25b  mov     ecx, r13d
0x18006c25e  test    eax, eax
0x18006c260  setnz   cl
0x18006c263  mov     [rdi], ecx
0x18006c265  mov     [rdi+8], r14
0x18006c269  mov     r14, r13
0x18006c26c  movups  xmmword ptr [rdi+10h], xmm0
0x18006c270  movups  xmmword ptr [rdi+20h], xmm0
0x18006c274  movups  xmmword ptr [rdi+30h], xmm0
0x18006c278  call    cs:__imp_GetProcessHeap
0x18006c27e  mov     r10d, 10h
0x18006c284  mov     [rdi+20h], r13
0x18006c288  lea     r8, [rbp+var_48]; unsigned __int64 *
0x18006c28c  mov     [rdi+10h], rax
0x18006c290  xor     ecx, ecx; unsigned __int64
0x18006c292  mov     [rdi+30h], r10
0x18006c296  mov     [rdi+28h], r13
0x18006c29a  lea     edx, [r10+10h]; unsigned __int64
0x18006c29e  mov     [rdi+38h], r13
0x18006c2a2  mov     [rdi+18h], rdx
0x18006c2a6  mov     [rbp+dwBytes], r13
0x18006c2aa  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006c2af  mov     r9d, 8000000Bh
0x18006c2b5  test    eax, eax
0x18006c2b7  jns     short loc_18006C2BE
0x18006c2b9  mov     ebx, r9d
0x18006c2bc  jmp     short loc_18006C31B
0x18006c2be  mov     rdx, [rdi+18h]; unsigned __int64
0x18006c2c2  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18006c2c6  mov     rcx, r10; unsigned __int64
0x18006c2c9  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006c2ce  test    eax, eax
0x18006c2d0  js      short loc_18006C2B9
0x18006c2d2  mov     r8, [rdi+38h]; lpMem
0x18006c2d6  xor     edx, edx; dwFlags
0x18006c2d8  mov     rsi, [rbp+dwBytes]
0x18006c2dc  mov     rcx, [rdi+10h]; hHeap
0x18006c2e0  test    r8, r8
0x18006c2e3  jnz     short loc_18006C305
0x18006c2e5  mov     r8, rsi; dwBytes
0x18006c2e8  call    cs:__imp_HeapAlloc
0x18006c2ee  mov     rbx, rax
0x18006c2f1  test    rax, rax
0x18006c2f4  jz      short loc_18006C311
0x18006c2f6  mov     r8, rsi; Size
0x18006c2f9  xor     edx, edx; Val
0x18006c2fb  mov     rcx, rax; void *
0x18006c2fe  call    memset_0
0x18006c303  jmp     short loc_18006C311
0x18006c305  mov     r9, rsi; dwBytes
0x18006c308  call    cs:__imp_HeapReAlloc
0x18006c30e  mov     rbx, rax
0x18006c311  test    rbx, rbx
0x18006c314  jnz     short loc_18006C377
0x18006c316  mov     ebx, 8007000Eh
0x18006c31b  mov     r8, [rdi+38h]; lpMem
0x18006c31f  test    r8, r8
0x18006c322  jz      short loc_18006C330
0x18006c324  mov     rcx, [rdi+10h]; hHeap
0x18006c328  xor     edx, edx; dwFlags
0x18006c32a  call    cs:__imp_HeapFree
0x18006c330  xorps   xmm0, xmm0
0x18006c333  movups  xmmword ptr [rdi+10h], xmm0
0x18006c337  movups  xmmword ptr [rdi+20h], xmm0
0x18006c33b  movups  xmmword ptr [rdi+30h], xmm0
0x18006c33f  test    ebx, ebx
0x18006c341  jns     short loc_18006C383
0x18006c343  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x18006c34a  mov     dword ptr [rsp+80h+var_60], ebx
0x18006c34e  mov     r8d, 864h
0x18006c354  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x18006c35b  mov     ecx, 1
0x18006c360  call    AslLogCallPrintf
0x18006c365  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x18006c36c  mov     r8d, 92Dh
0x18006c372  jmp     loc_18006C50C
0x18006c377  mov     [rdi+38h], rbx
0x18006c37b  mov     qword ptr [rdi+28h], 10h
0x18006c383  mov     rdx, [rdi+8]; SourceString
0x18006c387  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006c38b  call    cs:__imp_RtlInitUnicodeString
0x18006c391  mov     r8, [rdi+8]
0x18006c395  lea     rdx, [rbp+DestinationString]
0x18006c399  mov     r9d, 1
0x18006c39f  mov     [rsp+80h+var_58], r13w
0x18006c3a5  lea     rcx, [rbp+var_20]
0x18006c3a9  mov     [rsp+80h+var_60], r13
0x18006c3ae  call    AslpPathWildcardAllocMatchNode
0x18006c3b3  mov     ebx, eax
0x18006c3b5  test    eax, eax
0x18006c3b7  jns     short loc_18006C3CF
0x18006c3b9  mov     dword ptr [rsp+80h+var_60], eax
0x18006c3bd  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x18006c3c4  mov     r8d, 93Ah
0x18006c3ca  jmp     loc_18006C510
0x18006c3cf  mov     r13, [rdi+20h]
0x18006c3d3  cmp     r13, [rdi+28h]
0x18006c3d7  jb      loc_18006C49C
0x18006c3dd  lea     rcx, [r13+1]
0x18006c3e1  cmp     rcx, [rdi+28h]
0x18006c3e5  ja      short loc_18006C3F1
0x18006c3e7  mov     ebx, 80070057h
0x18006c3ec  jmp     loc_18006C48B
0x18006c3f1  mov     rbx, [rdi+30h]
0x18006c3f5  dec     rbx
0x18006c3f8  lea     r9, [rbx+rcx]
0x18006c3fc  cmp     r9, rcx
0x18006c3ff  jnb     short loc_18006C40B
0x18006c401  mov     ebx, 8000000Bh
0x18006c406  jmp     loc_18006C48B
0x18006c40b  mov     rdx, [rdi+18h]; unsigned __int64
0x18006c40f  lea     r8, [rbp+var_48]; unsigned __int64 *
0x18006c413  mov     rcx, [rdi+28h]; unsigned __int64
0x18006c417  mov     [rbp+dwBytes], r14
0x18006c41b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006c420  test    eax, eax
0x18006c422  js      short loc_18006C401
0x18006c424  mov     rdx, [rdi+18h]; unsigned __int64
0x18006c428  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18006c42c  not     rbx
0x18006c42f  and     rbx, r9
0x18006c432  mov     rcx, rbx; unsigned __int64
0x18006c435  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006c43a  test    eax, eax
0x18006c43c  js      short loc_18006C401
0x18006c43e  mov     r8, [rdi+38h]; lpMem
0x18006c442  xor     edx, edx; dwFlags
0x18006c444  mov     r12, [rbp+dwBytes]
0x18006c448  mov     rcx, [rdi+10h]; hHeap
0x18006c44c  test    r8, r8
0x18006c44f  jnz     short loc_18006C471
0x18006c451  mov     r8, r12; dwBytes
0x18006c454  call    cs:__imp_HeapAlloc
0x18006c45a  mov     rsi, rax
0x18006c45d  test    rax, rax
0x18006c460  jz      short loc_18006C47D
0x18006c462  mov     r8, r12; Size
0x18006c465  xor     edx, edx; Val
0x18006c467  mov     rcx, rax; void *
0x18006c46a  call    memset_0
0x18006c46f  jmp     short loc_18006C47D
0x18006c471  mov     r9, r12; dwBytes
0x18006c474  call    cs:__imp_HeapReAlloc
0x18006c47a  mov     rsi, rax
0x18006c47d  mov     r12, [rbp+arg_0]
0x18006c481  test    rsi, rsi
0x18006c484  jnz     short loc_18006C494
0x18006c486  mov     ebx, 8007000Eh
0x18006c48b  xor     r13d, r13d
0x18006c48e  test    ebx, ebx
0x18006c490  jns     short loc_18006C4D8
0x18006c492  jmp     short loc_18006C4FF
0x18006c494  mov     [rdi+38h], rsi
0x18006c498  mov     [rdi+28h], rbx
0x18006c49c  mov     rcx, [rdi+18h]; unsigned __int64
0x18006c4a0  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18006c4a4  mov     rdx, r13; unsigned __int64
0x18006c4a7  mov     [rbp+dwBytes], r14
  ... truncated ...
```
