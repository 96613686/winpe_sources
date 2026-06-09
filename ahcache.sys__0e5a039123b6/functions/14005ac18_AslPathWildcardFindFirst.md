# AslPathWildcardFindFirst

- ea: `0x14005ac18`
- end: `0x14005b1b6`
- name: `AslPathWildcardFindFirst`
- size: `1438`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest, ULONGLONG, const wchar_t *, _QWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path`

## callers

- `0x14002f430`

## callees

- `0x1400012f0`
- `0x140001820`
- `0x140001f58`
- `0x1400020ec`
- `0x14000436d`
- `0x14000437f`
- `0x14000440f`
- `0x1400079c8`
- `0x140007b40`
- `0x140007e40`
- `0x140031afc`
- `0x14003e364`
- `0x140045d44`
- `0x14004fee8`
- `0x140050724`
- `0x140050944`
- `0x140050a14`
- `0x140050ba4`
- `0x1400513c0`
- `0x14005498c`
- `0x14005ac18`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14005b15e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14005b15e`
- `ntoskrnl!RtlCreateUnicodeString` at `0x14005acaa`
- `ntoskrnl!RtlCreateUnicodeString` at `0x14005acaa`

## string_xrefs

- `0x14005b13b`: `AslpPathWildcardPushNode failed [%x]`
- `0x14005afaa`: `AslpPathWildcardInitStack`
- `0x14005acbf`: `RtlCreateUnicodeString failed`
- `0x14005acd1`: `AslPathWildcardFindFirst`
- `0x14005b14e`: `AslPathWildcardFindFirst`
- `0x14005acf1`: `AslPathCleanUstr failed [%x]`
- `0x14005ad76`: `RtlStringCbCopyNW failed [%x]`
- `0x14005adea`: `RtlStringCbCopyNW failed [%x]`
- `0x14005ad99`: `Failed to split the wildcard path`
- `0x14005afb8`: `AslpPathWildcardInitStack failed [%x]`
- `0x14005af59`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindFirst(NTSTRSAFE_PWSTR pszDest, ULONGLONG a2, const wchar_t *a3, _QWORD *a4)
{
  WCHAR *v8; // r12
  int Next; // ebx
  int v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v13; // rcx
  size_t v14; // rbx
  wchar_t *v15; // rax
  NTSTATUS v16; // eax
  int Leaves; // eax
  __int64 v18; // rcx
  wchar_t *Buffer; // rcx
  NTSTATUS v20; // eax
  _DWORD *v21; // rdi
  int v22; // eax
  HRESULT v23; // eax
  ULONGLONG v24; // r10
  int v25; // r9d
  size_t v26; // r14
  void *v27; // r15
  PVOID PoolWithTag_0; // rax
  void *v29; // rbx
  int matched; // eax
  void *v31; // rcx
  ULONGLONG v32; // rax
  ULONGLONG v33; // rcx
  __int64 v34; // r14
  ULONGLONG v35; // rdx
  __int64 v36; // r9
  ULONGLONG v37; // r14
  SIZE_T v38; // r15
  PVOID v39; // rax
  void *v40; // rbx
  PVOID v41; // rax
  ULONGLONG v42; // rcx
  ULONGLONG v43; // rcx
  ULONGLONG v44; // rdx
  __int64 v45; // rcx
  NTSTRSAFE_PCWSTR pszSrc; // [rsp+28h] [rbp-49h]
  ULONGLONG pullResult; // [rsp+38h] [rbp-39h] BYREF
  _DWORD *v48; // [rsp+40h] [rbp-31h] BYREF
  ULONGLONG v49; // [rsp+48h] [rbp-29h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-21h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-11h] BYREF
  struct _UNICODE_STRING v52; // [rsp+70h] [rbp-1h] BYREF
  __int128 v53; // [rsp+80h] [rbp+Fh]
  ULONGLONG pusResult; // [rsp+E0h] [rbp+6Fh] BYREF

  pusResult = a2;
  if ( !pszDest )
    return 3221225711LL;
  if ( !a3 || !*a3 )
    return 3221225713LL;
  if ( !a4 )
    return 3221225714LL;
  *pszDest = 0;
  v48 = 0;
  LOWORD(pusResult) = 0;
  *a4 = 0;
  DestinationString = 0;
  v8 = 0;
  SourceString = 0;
  v52 = 0;
  v53 = 0;
  if ( RtlCreateUnicodeString(&DestinationString, a3) )
  {
    v10 = AslPathCleanUstr(&DestinationString.Length);
    Next = v10;
    if ( v10 < 0 )
    {
      v11 = "AslPathCleanUstr failed [%x]";
      v12 = 2257;
LABEL_11:
      LODWORD(pszSrc) = v10;
LABEL_67:
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", v12, v11, pszSrc);
      goto LABEL_68;
    }
    v10 = RtlUShortAdd(DestinationString.Length, 4u, (USHORT *)&pusResult);
    Next = v10;
    if ( v10 < 0 )
    {
      v11 = "RtlUShortAdd failed [%x]";
      v12 = 2263;
      goto LABEL_11;
    }
    v14 = (unsigned __int16)pusResult;
    v15 = (wchar_t *)AslAlloc(v13, (unsigned __int16)pusResult, 1);
    v8 = v15;
    if ( !v15 )
      goto LABEL_15;
    v16 = RtlStringCbCopyNW(v15, v14, DestinationString.Buffer, DestinationString.Length);
    Next = v16;
    if ( v16 < 0 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2275, "RtlStringCbCopyNW failed [%x]", v16);
      goto LABEL_68;
    }
    Leaves = AslpPathWildcardMakeLeaves(v8);
    if ( !Leaves )
    {
      Next = -1073741767;
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2293, "Failed to split the wildcard path");
      goto LABEL_68;
    }
    if ( Leaves == 1 )
    {
      Buffer = DestinationString.Buffer;
      *a4 = -1;
      if ( AslDoesFileExistNtPath(Buffer) )
      {
        v20 = RtlStringCchCopyW(pszDest, 0x104u, a3);
        Next = v20;
        if ( v20 >= 0 )
          Next = 0;
        else
          AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2311, "RtlStringCbCopyNW failed [%x]", v20);
      }
      else
      {
        Next = -2147483642;
      }
      goto LABEL_68;
    }
    v48 = (_DWORD *)AslAlloc(v18, 64, 1);
    v21 = v48;
    if ( !v48 )
    {
LABEL_15:
      Next = -1073741801;
      goto LABEL_68;
    }
    v22 = wcsncmp_0(a3, L"\\??\\", 4u);
    pusResult = 0;
    pullResult = 0;
    *v48 = v22 != 0;
    *((_QWORD *)v21 + 1) = v8;
    v8 = 0;
    *((_QWORD *)v21 + 2) = 0;
    *((_QWORD *)v21 + 6) = 16;
    *((_QWORD *)v21 + 4) = 0;
    *((_QWORD *)v21 + 5) = 0;
    *((_QWORD *)v21 + 7) = 0;
    *((_QWORD *)v21 + 3) = 32;
    v23 = ULongLongMult(0, 0x20u, &pusResult);
    v25 = -1073741675;
    if ( v23 < 0 || ULongLongMult(v24, *((_QWORD *)v21 + 3), &pullResult) < 0 )
    {
      Next = v25;
    }
    else
    {
      v26 = pullResult;
      v27 = (void *)*((_QWORD *)v21 + 7);
      PoolWithTag_0 = ExAllocatePoolWithTag_0(PagedPool, pullResult, 0x72615452u);
      v29 = PoolWithTag_0;
      if ( v27 )
      {
        if ( PoolWithTag_0 )
        {
          memset(PoolWithTag_0, 0, v26);
          if ( pusResult < v26 )
            v26 = pusResult;
          memmove(v29, v27, v26);
          ExFreePoolWithTag_0(v27, 0x72615452u);
          goto LABEL_37;
        }
      }
      else if ( PoolWithTag_0 )
      {
        memset(PoolWithTag_0, 0, v26);
LABEL_37:
        *((_QWORD *)v21 + 7) = v29;
        *((_QWORD *)v21 + 5) = 16;
        goto LABEL_38;
      }
      Next = -1073741801;
    }
    v31 = (void *)*((_QWORD *)v21 + 7);
    if ( v31 )
      ExFreePoolWithTag_0(v31, 0x72615452u);
    *((_OWORD *)v21 + 1) = 0;
    *((_OWORD *)v21 + 2) = 0;
    *((_OWORD *)v21 + 3) = 0;
    if ( Next < 0 )
    {
      AslLogCallPrintf(1, "AslpPathWildcardInitStack", 2148, "RtlArrayInitialize failed [%x]", Next);
      v11 = "AslpPathWildcardInitStack failed [%x]";
      v12 = 2349;
LABEL_66:
      LODWORD(pszSrc) = Next;
      goto LABEL_67;
    }
LABEL_38:
    RtlInitUnicodeString_0(&SourceString, *((PCWSTR *)v21 + 1));
    matched = AslpPathWildcardAllocMatchNode(&v52, &SourceString, 0, 0);
    Next = matched;
    if ( matched < 0 )
    {
      LODWORD(pszSrc) = matched;
      AslLogCallPrintf(
        1,
        "AslPathWildcardFindFirst",
        2362,
        "AslpPathWildcardAllocMatchNode failed to create root of path [%x]",
        pszSrc);
      goto LABEL_68;
    }
    v32 = *((_QWORD *)v21 + 4);
    v33 = *((_QWORD *)v21 + 5);
    v49 = v32;
    if ( v32 < v33 )
      goto LABEL_60;
    if ( v32 + 1 <= v33 )
    {
      Next = -1073741811;
LABEL_65:
      v11 = "AslpPathWildcardPushNode failed [%x]";
      v12 = 2368;
      goto LABEL_66;
    }
    v34 = *((_QWORD *)v21 + 6) - 1LL;
    if ( *((_QWORD *)v21 + 6) + v32 < v32 + 1
      || (v35 = *((_QWORD *)v21 + 3), pusResult = 0, pullResult = 0, ULongLongMult(v33, v35, &pusResult) < 0)
      || (v37 = v36 & ~v34, ULongLongMult(v37, *((_QWORD *)v21 + 3), &pullResult) < 0) )
    {
      Next = -1073741675;
      goto LABEL_65;
    }
    v38 = pullResult;
    pullResult = *((_QWORD *)v21 + 7);
    if ( pullResult )
    {
      v41 = ExAllocatePoolWithTag_0(PagedPool, v38, 0x72615452u);
      v40 = v41;
      if ( v41 )
      {
        memset(v41, 0, v38);
        if ( pusResult < v38 )
          v38 = pusResult;
        memmove(v40, (const void *)pullResult, v38);
        ExFreePoolWithTag_0((PVOID)pullResult, 0x72615452u);
        goto LABEL_59;
      }
    }
    else
    {
      v39 = ExAllocatePoolWithTag_0(PagedPool, v38, 0x72615452u);
      v40 = v39;
      if ( v39 )
      {
        memset(v39, 0, v38);
LABEL_59:
        v32 = v49;
        *((_QWORD *)v21 + 7) = v40;
        *((_QWORD *)v21 + 5) = v37;
LABEL_60:
        v42 = *((_QWORD *)v21 + 3);
        pusResult = 0;
        if ( ULongLongMult(v42, v32, &pusResult) >= 0 )
        {
          v43 = *((_QWORD *)v21 + 7);
          v44 = v43 + pusResult;
          if ( v43 + pusResult >= v43 )
          {
            *(struct _UNICODE_STRING *)v44 = v52;
            *(_OWORD *)(v44 + 16) = v53;
            ++*((_QWORD *)v21 + 4);
            *a4 = v21;
            v52 = 0;
            v53 = 0;
            Next = AslPathWildcardFindNext(pszDest, v44, v21);
            goto LABEL_68;
          }
        }
        Next = -1073741675;
        goto LABEL_65;
      }
    }
    Next = -1073741801;
    goto LABEL_65;
  }
  Next = -1073741801;
  AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2236, "RtlCreateUnicodeString failed");
LABEL_68:
  RtlFreeUnicodeString(&DestinationString);
  if ( v8 )
    AslFree(v45, v8);
  if ( Next < 0 )
  {
    AslpPathWildcardFreeFindContext(&v48);
    AslpPathWildcardFreeMatchNode(&v52);
    *a4 = 0;
  }
  return (unsigned int)Next;
}

```

## disassembly

```asm
0x14005ac18  mov     rax, rsp
0x14005ac1b  mov     [rax+18h], rbx
0x14005ac1f  mov     [rax+10h], rdx
0x14005ac23  mov     [rax+8], rcx
0x14005ac27  push    rbp
0x14005ac28  push    rsi
0x14005ac29  push    rdi
0x14005ac2a  push    r12
0x14005ac2c  push    r13
0x14005ac2e  push    r14
0x14005ac30  push    r15
0x14005ac32  lea     rbp, [rax-5Fh]
0x14005ac36  sub     rsp, 90h
0x14005ac3d  xor     r15d, r15d
0x14005ac40  mov     r13, r9
0x14005ac43  mov     r14, r8
0x14005ac46  mov     rdi, rcx
0x14005ac49  test    rcx, rcx
0x14005ac4c  jnz     short loc_14005AC58
0x14005ac4e  mov     eax, 0C00000EFh
0x14005ac53  jmp     loc_14005B19A
0x14005ac58  test    r14, r14
0x14005ac5b  jz      loc_14005B195
0x14005ac61  cmp     [r8], r15w
0x14005ac65  jz      loc_14005B195
0x14005ac6b  test    r13, r13
0x14005ac6e  jnz     short loc_14005AC7A
0x14005ac70  mov     eax, 0C00000F2h
0x14005ac75  jmp     loc_14005B19A
0x14005ac7a  xorps   xmm0, xmm0
0x14005ac7d  mov     [rcx], r15w
0x14005ac81  xorps   xmm1, xmm1
0x14005ac84  mov     [rbp+57h+var_88], r15
0x14005ac88  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005ac8c  mov     word ptr [rbp+57h+pusResult], r15w
0x14005ac91  mov     rdx, r14; SourceString
0x14005ac94  mov     [r9], r15
0x14005ac97  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005ac9b  mov     r12, r15
0x14005ac9e  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x14005aca2  movups  xmmword ptr [rbp+57h+var_58.Length], xmm1
0x14005aca6  movups  [rbp+57h+var_48], xmm1
0x14005acaa  call    cs:__imp_RtlCreateUnicodeString
0x14005acb1  nop     dword ptr [rax+rax+00h]
0x14005acb6  test    al, al
0x14005acb8  jnz     short loc_14005ACE2
0x14005acba  mov     ebx, 0C0000017h
0x14005acbf  lea     r9, aRtlcreateunico; "RtlCreateUnicodeString failed"
0x14005acc6  mov     r8d, 8BCh
0x14005accc  mov     ecx, 1
0x14005acd1  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x14005acd8  call    AslLogCallPrintf
0x14005acdd  jmp     loc_14005B15A
0x14005ace2  lea     rcx, [rbp+57h+DestinationString]
0x14005ace6  call    AslPathCleanUstr
0x14005aceb  mov     ebx, eax
0x14005aced  test    eax, eax
0x14005acef  jns     short loc_14005AD0C
0x14005acf1  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x14005acf8  mov     r8d, 8D1h
0x14005acfe  mov     dword ptr [rsp+0C0h+pszSrc], eax
0x14005ad02  mov     ecx, 1
0x14005ad07  jmp     loc_14005B14E
0x14005ad0c  movzx   ecx, [rbp+57h+DestinationString.Length]; usAugend
0x14005ad10  lea     r8, [rbp+57h+pusResult]; pusResult
0x14005ad14  mov     edx, 4; usAddend
0x14005ad19  call    RtlUShortAdd
0x14005ad1e  mov     ebx, eax
0x14005ad20  test    eax, eax
0x14005ad22  jns     short loc_14005AD33
0x14005ad24  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x14005ad2b  mov     r8d, 8D7h
0x14005ad31  jmp     short loc_14005ACFE
0x14005ad33  movzx   ebx, word ptr [rbp+57h+pusResult]
0x14005ad37  mov     esi, 1
0x14005ad3c  mov     r8d, esi
0x14005ad3f  mov     edx, ebx
0x14005ad41  call    AslAlloc
0x14005ad46  mov     r12, rax
0x14005ad49  test    rax, rax
0x14005ad4c  jnz     short loc_14005AD58
0x14005ad4e  mov     ebx, 0C0000017h
0x14005ad53  jmp     loc_14005B15A
0x14005ad58  movzx   r9d, [rbp+57h+DestinationString.Length]; cbToCopy
0x14005ad5d  mov     rdx, rbx; cbDest
0x14005ad60  mov     r8, [rbp+57h+DestinationString.Buffer]; pszSrc
0x14005ad64  mov     rcx, r12; pszDest
0x14005ad67  call    RtlStringCbCopyNW
0x14005ad6c  mov     ebx, eax
0x14005ad6e  test    eax, eax
0x14005ad70  jns     short loc_14005AD88
0x14005ad72  mov     dword ptr [rsp+0C0h+pszSrc], eax
0x14005ad76  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x14005ad7d  mov     r8d, 8E3h
0x14005ad83  jmp     loc_14005B14C
0x14005ad88  mov     rcx, r12; SourceString
0x14005ad8b  call    AslpPathWildcardMakeLeaves
0x14005ad90  test    eax, eax
0x14005ad92  jnz     short loc_14005ADAD
0x14005ad94  mov     ebx, 0C0000039h
0x14005ad99  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x14005ada0  mov     r8d, 8F5h
0x14005ada6  mov     ecx, esi
0x14005ada8  jmp     loc_14005ACD1
0x14005adad  cmp     eax, esi
0x14005adaf  jnz     short loc_14005AE04
0x14005adb1  mov     rcx, [rbp+57h+DestinationString.Buffer]; SourceString
0x14005adb5  mov     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x14005adbd  call    AslDoesFileExistNtPath
0x14005adc2  test    eax, eax
0x14005adc4  jnz     short loc_14005ADD0
0x14005adc6  mov     ebx, 80000006h
0x14005adcb  jmp     loc_14005B15A
0x14005add0  mov     r8, r14; pszSrc
0x14005add3  mov     edx, 104h; cchDest
0x14005add8  mov     rcx, rdi; pszDest
0x14005addb  call    RtlStringCchCopyW
0x14005ade0  mov     ebx, eax
0x14005ade2  test    eax, eax
0x14005ade4  jns     short loc_14005ADFC
0x14005ade6  mov     dword ptr [rsp+0C0h+pszSrc], eax
0x14005adea  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x14005adf1  mov     r8d, 907h
0x14005adf7  jmp     loc_14005B14C
0x14005adfc  mov     ebx, r15d
0x14005adff  jmp     loc_14005B15A
0x14005ae04  mov     r8d, esi
0x14005ae07  mov     edx, 40h ; '@'
0x14005ae0c  call    AslAlloc
0x14005ae11  mov     [rbp+57h+var_88], rax
0x14005ae15  mov     rdi, rax
0x14005ae18  test    rax, rax
0x14005ae1b  jz      loc_14005AD4E
0x14005ae21  mov     r8d, 4; MaxCount
0x14005ae27  lea     rdx, asc_14000EAD8; "\\??\\"
0x14005ae2e  mov     rcx, r14; Str1
0x14005ae31  call    wcsncmp_0
0x14005ae36  mov     ecx, r15d
0x14005ae39  mov     [rbp+57h+pusResult], r15
0x14005ae3d  test    eax, eax
0x14005ae3f  mov     [rbp+57h+pullResult], r15
0x14005ae43  mov     r10d, 10h
0x14005ae49  lea     r8, [rbp+57h+pusResult]; pullResult
0x14005ae4d  setnz   cl
0x14005ae50  mov     [rdi], ecx
0x14005ae52  xor     ecx, ecx; ullMultiplicand
0x14005ae54  mov     [rdi+8], r12
0x14005ae58  mov     r12, r15
0x14005ae5b  lea     edx, [r10+10h]; ullMultiplier
0x14005ae5f  mov     [rdi+10h], r15
0x14005ae63  mov     [rdi+30h], r10
0x14005ae67  mov     [rdi+20h], r15
0x14005ae6b  mov     [rdi+28h], r15
0x14005ae6f  mov     [rdi+38h], r15
0x14005ae73  mov     [rdi+18h], rdx
0x14005ae77  call    ULongLongMult
0x14005ae7c  mov     r9d, 0C0000095h
0x14005ae82  test    eax, eax
0x14005ae84  jns     short loc_14005AE8E
0x14005ae86  mov     ebx, r9d
0x14005ae89  jmp     loc_14005AF73
0x14005ae8e  mov     rdx, [rdi+18h]; ullMultiplier
0x14005ae92  lea     r8, [rbp+57h+pullResult]; pullResult
0x14005ae96  mov     rcx, r10; ullMultiplicand
0x14005ae99  call    ULongLongMult
0x14005ae9e  test    eax, eax
0x14005aea0  js      short loc_14005AE86
0x14005aea2  mov     r14, [rbp+57h+pullResult]
0x14005aea6  mov     r8d, 72615452h; Tag
0x14005aeac  mov     r15, [rdi+38h]
0x14005aeb0  mov     rdx, r14; NumberOfBytes
0x14005aeb3  mov     ecx, esi; PoolType
0x14005aeb5  call    ExAllocatePoolWithTag_0
0x14005aeba  mov     rbx, rax
0x14005aebd  test    r15, r15
0x14005aec0  jnz     short loc_14005AEDA
0x14005aec2  test    rax, rax
0x14005aec5  jz      loc_14005AF6E
0x14005aecb  mov     r8, r14; Size
0x14005aece  xor     edx, edx; Val
0x14005aed0  mov     rcx, rax; void *
0x14005aed3  call    memset
0x14005aed8  jmp     short loc_14005AF17
0x14005aeda  test    rax, rax
0x14005aedd  jz      loc_14005AF6B
0x14005aee3  mov     r8, r14; Size
0x14005aee6  xor     edx, edx; Val
0x14005aee8  mov     rcx, rbx; void *
0x14005aeeb  call    memset
0x14005aef0  cmp     [rbp+57h+pusResult], r14
0x14005aef4  mov     rdx, r15; Src
0x14005aef7  mov     rcx, rbx; void *
0x14005aefa  cmovb   r14, [rbp+57h+pusResult]
0x14005aeff  mov     r8, r14; Size
0x14005af02  call    memmove
0x14005af07  mov     edx, 72615452h; Tag
0x14005af0c  mov     rcx, r15; P
0x14005af0f  call    ExFreePoolWithTag_0
0x14005af14  xor     r15d, r15d
0x14005af17  mov     [rdi+38h], rbx
0x14005af1b  mov     qword ptr [rdi+28h], 10h
0x14005af23  mov     rdx, [rdi+8]; SourceString
0x14005af27  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x14005af2b  call    RtlInitUnicodeString_0
0x14005af30  mov     r8, [rdi+8]
0x14005af34  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14005af38  mov     r9d, esi
0x14005af3b  mov     [rsp+28h], r15w; __int16
0x14005af41  lea     rcx, [rbp+57h+var_58]; DestinationString
0x14005af45  mov     [rsp+0C0h+pszSrc], r15; pszSrc
0x14005af4a  call    AslpPathWildcardAllocMatchNode
0x14005af4f  mov     ebx, eax
0x14005af51  test    eax, eax
0x14005af53  jns     short loc_14005AFCA
0x14005af55  mov     dword ptr [rsp+0C0h+pszSrc], eax
0x14005af59  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x14005af60  mov     r8d, 93Ah
0x14005af66  jmp     loc_14005B14C
0x14005af6b  xor     r15d, r15d
0x14005af6e  mov     ebx, 0C0000017h
0x14005af73  mov     rcx, [rdi+38h]; P
0x14005af77  test    rcx, rcx
0x14005af7a  jz      short loc_14005AF86
0x14005af7c  mov     edx, 72615452h; Tag
0x14005af81  call    ExFreePoolWithTag_0
0x14005af86  xorps   xmm0, xmm0
0x14005af89  movups  xmmword ptr [rdi+10h], xmm0
0x14005af8d  movups  xmmword ptr [rdi+20h], xmm0
0x14005af91  movups  xmmword ptr [rdi+30h], xmm0
0x14005af95  test    ebx, ebx
0x14005af97  jns     short loc_14005AF23
0x14005af99  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x14005afa0  mov     dword ptr [rsp+0C0h+pszSrc], ebx
0x14005afa4  mov     r8d, 864h
0x14005afaa  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x14005afb1  mov     ecx, esi
0x14005afb3  call    AslLogCallPrintf
0x14005afb8  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x14005afbf  mov     r8d, 92Dh
0x14005afc5  jmp     loc_14005B148
0x14005afca  mov     rax, [rdi+20h]
0x14005afce  mov     rcx, [rdi+28h]; ullMultiplicand
0x14005afd2  mov     [rbp+57h+var_80], rax
0x14005afd6  cmp     rax, rcx
0x14005afd9  jb      loc_14005B0CE
0x14005afdf  lea     rdx, [rax+1]
0x14005afe3  cmp     rdx, rcx
0x14005afe6  ja      short loc_14005AFF2
0x14005afe8  mov     ebx, 0C000000Dh
0x14005afed  jmp     loc_14005B130
0x14005aff2  mov     r14, [rdi+30h]
0x14005aff6  dec     r14
0x14005aff9  lea     r9, [r14+rdx]
0x14005affd  cmp     r9, rdx
0x14005b000  jnb     short loc_14005B00C
0x14005b002  mov     ebx, 0C0000095h
0x14005b007  jmp     loc_14005B130
0x14005b00c  mov     rdx, [rdi+18h]; ullMultiplier
0x14005b010  lea     r8, [rbp+57h+pusResult]; pullResult
0x14005b014  mov     [rbp+57h+pusResult], r15
0x14005b018  mov     [rbp+57h+pullResult], r15
0x14005b01c  call    ULongLongMult
0x14005b021  test    eax, eax
0x14005b023  js      short loc_14005B002
0x14005b025  mov     rdx, [rdi+18h]; ullMultiplier
0x14005b029  lea     r8, [rbp+57h+pullResult]; pullResult
0x14005b02d  not     r14
0x14005b030  and     r14, r9
0x14005b033  mov     rcx, r14; ullMultiplicand
0x14005b036  call    ULongLongMult
0x14005b03b  test    eax, eax
0x14005b03d  js      short loc_14005B002
0x14005b03f  mov     rax, [rdi+38h]
0x14005b043  mov     r8d, 72615452h; Tag
0x14005b049  mov     r15, [rbp+57h+pullResult]
0x14005b04d  mov     ecx, esi; PoolType
0x14005b04f  mov     [rbp+57h+pullResult], rax
0x14005b053  mov     rdx, r15; NumberOfBytes
0x14005b056  test    rax, rax
0x14005b059  jnz     short loc_14005B07B
0x14005b05b  call    ExAllocatePoolWithTag_0
0x14005b060  mov     rbx, rax
0x14005b063  test    rax, rax
0x14005b066  jz      loc_14005B128
0x14005b06c  mov     r8, r15; Size
0x14005b06f  xor     edx, edx; Val
0x14005b071  mov     rcx, rax; void *
0x14005b074  call    memset
0x14005b079  jmp     short loc_14005B0BF
0x14005b07b  call    ExAllocatePoolWithTag_0
0x14005b080  mov     rbx, rax
0x14005b083  test    rax, rax
0x14005b086  jz      loc_14005B128
0x14005b08c  mov     r8, r15; Size
0x14005b08f  xor     edx, edx; Val
0x14005b091  mov     rcx, rax; void *
0x14005b094  call    memset
0x14005b099  cmp     [rbp+57h+pusResult], r15
0x14005b09d  mov     rcx, rbx; void *
0x14005b0a0  mov     rdx, [rbp+57h+pullResult]; Src
  ... truncated ...
```
