# SdbReadMsiTransformInfo

- ea: `0x180049140`
- end: `0x1800494df`
- name: `SdbReadMsiTransformInfo`
- size: `927`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callees

- `0x180006ba0`
- `0x180006c20`
- `0x180007020`
- `0x180009720`
- `0x180009f10`
- `0x18000a960`
- `0x18000ae70`
- `0x18000ecc0`
- `0x18000efe0`
- `0x18000f114`
- `0x18000f150`
- `0x180018f20`
- `0x180048318`
- `0x180049140`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180049343`
- `ntdll!RtlAllocateHeap` at `0x180049343`

## string_xrefs

- `0x1800491a6`: `SdbReadMsiTransformInfo`
- `0x180049367`: `SdbReadMsiTransformInfo`
- `0x1800493a6`: `SdbReadMsiTransformInfo`
- `0x1800494a4`: `SdbReadMsiTransformInfo`
- `0x1800492ab`: `Failed to get MSI Transform for tag 0x%x`
- `0x180049395`: `Failed to read filename string tag, length %d characters, tag 0x%x`

## pseudocode

```c
__int64 __fastcall SdbReadMsiTransformInfo(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  __int64 v9; // r15
  unsigned int FirstTag; // eax
  unsigned int ItemFromItemRef; // eax
  unsigned int v12; // edi
  __int64 v13; // r14
  unsigned int FirstTagRef; // eax
  unsigned int DWORDTagRef; // eax
  unsigned int v16; // r12d
  __int64 v17; // rdx
  unsigned int v18; // eax
  unsigned int v19; // r12d
  __int64 v20; // rdi
  __int64 StringTagPtr; // rax
  PVOID Heap; // rax
  void *v23; // r13
  unsigned int v24; // edi
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int LibraryFile; // eax
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // [rsp+20h] [rbp-30h]
  int v31[2]; // [rsp+30h] [rbp-20h] BYREF
  int v32; // [rsp+38h] [rbp-18h] BYREF
  int v33; // [rsp+3Ch] [rbp-14h]
  __int64 v34; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v36; // [rsp+A8h] [rbp+58h] BYREF

  v36 = 0;
  v33 = 0;
  *(_OWORD *)a3 = 0;
  v32 = 0;
  *(_QWORD *)v31 = 0;
  v4 = a2;
  if ( !(unsigned int)SdbTagRefToTagID(a1, a2, v31, &v36) )
  {
    v6 = "Failed to convert tagref 0x%lx to tagid";
    v7 = 1057;
LABEL_3:
    AslLogCallPrintf(1, "SdbReadMsiTransformInfo", v7, v6, v4);
    return 0;
  }
  v9 = *(_QWORD *)v31;
  if ( (unsigned __int16)SdbGetTagFromTagID(*(_QWORD *)v31, v36) != 28689 )
  {
    v6 = "Bad Transform reference 0x%lx";
    v7 = 1062;
    goto LABEL_3;
  }
  FirstTag = SdbFindFirstTag(v9, v36, 24577);
  if ( FirstTag )
    *(_QWORD *)a3 = SdbGetStringTagPtr(v9, FirstTag);
  ItemFromItemRef = SdbGetItemFromItemRef(a1, v4, 24577, 16411, 28688);
  v12 = ItemFromItemRef;
  if ( !ItemFromItemRef )
    return 1;
  v31[0] = 0;
  *(_DWORD *)(a3 + 8) = ItemFromItemRef;
  v13 = 0;
  FirstTagRef = SdbFindFirstTagRef(a1, ItemFromItemRef, 16411);
  if ( FirstTagRef )
  {
    DWORDTagRef = SdbReadDWORDTagRef(a1, FirstTagRef, 0);
    v16 = DWORDTagRef;
    if ( *(_QWORD *)(a1 + 8) == v9
      && (v17 = *(_QWORD *)(a1 + 16)) != 0
      && (unsigned int)SdbpIsEntryIdAvailableInOtherDb(v9, v17, DWORDTagRef, 0) )
    {
      v31[0] = 1;
    }
    else if ( v16 )
    {
      v13 = v9;
    }
  }
  v18 = SdbFindFirstTagRef(a1, v12, 24607);
  v19 = v18;
  if ( !v18 )
  {
    LODWORD(v30) = v12;
    AslLogCallPrintf(1, "SdbReadMsiTransformInfo", 1129, "Failed to get MSI Transform for tag 0x%x", v30);
    return 0;
  }
  v34 = 0;
  v36 = 0;
  if ( (unsigned int)SdbTagRefToTagID(a1, v18, &v34, &v36) )
  {
    LODWORD(v20) = 0;
    StringTagPtr = SdbGetStringTagPtr(v34, v36);
    if ( StringTagPtr )
    {
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)(StringTagPtr + 2 * v20) );
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpGetStringRefLength", 575, "Failed to convert tag 0x%x to tagid", v19);
    LODWORD(v20) = 0;
  }
  v36 = v20 + 1;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v20 + 1));
  v23 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(
      1,
      "SdbReadMsiTransformInfo",
      1137,
      "Failed to allocate buffer for %ld characters tag 0x%lx",
      v20,
      v19);
    return 0;
  }
  if ( !(unsigned int)SdbReadStringTagRef(a1, v19, Heap, v36) )
  {
    AslLogCallPrintf(
      1,
      "SdbReadMsiTransformInfo",
      1145,
      "Failed to read filename string tag, length %d characters, tag 0x%x",
      v20,
      v19);
    AslFree(NtCurrentPeb()->ProcessHeap, v23);
    return 0;
  }
  v24 = 0;
  if ( *(_QWORD *)(a1 + 8) == v9
    || *(_QWORD *)(a1 + 16) == v9
    || (v13 = v9, (v24 = SdbpGetLibraryFile(v9, (wchar_t *)v23)) == 0) )
  {
    v25 = *(_QWORD *)(a1 + 16);
    if ( v25 && (v13 = *(_QWORD *)(a1 + 16), v26 = SdbpGetLibraryFile(v25, (wchar_t *)v23), (v24 = v26) != 0) )
    {
      if ( (unsigned int)SdbFindFirstTag(*(_QWORD *)(a1 + 16), v26, 4120) )
        v24 = 0;
    }
    else if ( !v31[0] )
    {
      v13 = *(_QWORD *)(a1 + 8);
      LibraryFile = SdbpGetLibraryFile(v13, (wchar_t *)v23);
      v24 = LibraryFile;
      if ( LibraryFile )
      {
        v28 = *(_QWORD *)(a1 + 16);
        if ( v28 )
        {
          if ( (unsigned int)SdbpIsEntryIdAvailableInOtherDb(v9, v28, LibraryFile, 24607) )
            v24 = 0;
        }
      }
    }
  }
  AslFree(NtCurrentPeb()->ProcessHeap, v23);
  if ( v24 && v13 )
  {
    if ( (unsigned int)SdbTagIDToTagRef(a1, v13, v24, &v32) )
    {
      v29 = v32;
    }
    else
    {
      AslLogCallPrintf(1, "SdbReadMsiTransformInfo", 1206, "Failed to convert File tag to tagref 0x%lx", v24);
      v29 = 0;
    }
  }
  else
  {
    v29 = v33;
  }
  *(_DWORD *)(a3 + 12) = v29;
  return 1;
}

```

## disassembly

```asm
0x180049140  mov     [rsp-38h+arg_0], rbx
0x180049145  mov     [rsp-38h+arg_10], r8
0x18004914a  push    rbp
0x18004914b  push    rsi
0x18004914c  push    rdi
0x18004914d  push    r12
0x18004914f  push    r13
0x180049151  push    r14
0x180049153  push    r15
0x180049155  mov     rbp, rsp
0x180049158  sub     rsp, 50h
0x18004915c  xor     r13d, r13d
0x18004915f  lea     r9, [rbp+arg_18]
0x180049163  mov     eax, r13d
0x180049166  mov     [rbp+arg_18], r13d
0x18004916a  xorps   xmm0, xmm0
0x18004916d  mov     [rbp+var_14], eax
0x180049170  movups  xmmword ptr [r8], xmm0
0x180049174  mov     r12, r8
0x180049177  mov     [rbp+var_18], eax
0x18004917a  lea     r8, [rbp+var_20]
0x18004917e  mov     qword ptr [rbp+var_20], r13
0x180049182  mov     ebx, edx
0x180049184  mov     rsi, rcx
0x180049187  call    SdbTagRefToTagID
0x18004918c  test    eax, eax
0x18004918e  jnz     short loc_1800491B9
0x180049190  lea     r9, aFailedToConver_21; "Failed to convert tagref 0x%lx to tagid"
0x180049197  mov     r8d, 421h
0x18004919d  mov     dword ptr [rsp+50h+var_30], ebx
0x1800491a1  mov     ecx, 1
0x1800491a6  lea     rdx, aSdbreadmsitran_0; "SdbReadMsiTransformInfo"
0x1800491ad  call    AslLogCallPrintf
0x1800491b2  xor     eax, eax
0x1800491b4  jmp     loc_1800494C7
0x1800491b9  mov     r15, qword ptr [rbp+var_20]
0x1800491bd  mov     edx, [rbp+arg_18]
0x1800491c0  mov     rcx, r15
0x1800491c3  call    SdbGetTagFromTagID
0x1800491c8  mov     ecx, 7011h
0x1800491cd  cmp     ax, cx
0x1800491d0  jz      short loc_1800491E1
0x1800491d2  lea     r9, aBadTransformRe; "Bad Transform reference 0x%lx"
0x1800491d9  mov     r8d, 426h
0x1800491df  jmp     short loc_18004919D
0x1800491e1  mov     edx, [rbp+arg_18]
0x1800491e4  mov     edi, 6001h
0x1800491e9  mov     r8d, edi
0x1800491ec  mov     rcx, r15
0x1800491ef  call    SdbFindFirstTag
0x1800491f4  test    eax, eax
0x1800491f6  jz      short loc_180049206
0x1800491f8  mov     edx, eax
0x1800491fa  mov     rcx, r15
0x1800491fd  call    SdbGetStringTagPtr
0x180049202  mov     [r12], rax
0x180049206  mov     r9d, 401Bh
0x18004920c  mov     word ptr [rsp+50h+var_30], 7010h
0x180049213  mov     r8d, edi
0x180049216  mov     edx, ebx
0x180049218  mov     rcx, rsi
0x18004921b  call    SdbGetItemFromItemRef
0x180049220  mov     edi, eax
0x180049222  test    eax, eax
0x180049224  jnz     short loc_18004922E
0x180049226  lea     eax, [rdi+1]
0x180049229  jmp     loc_1800494C7
0x18004922e  mov     r8d, 401Bh
0x180049234  mov     [rbp+var_20], r13d
0x180049238  mov     edx, edi
0x18004923a  mov     [r12+8], edi
0x18004923f  mov     rcx, rsi
0x180049242  mov     r14, r13
0x180049245  call    SdbFindFirstTagRef
0x18004924a  mov     ebx, 1
0x18004924f  test    eax, eax
0x180049251  jz      short loc_180049290
0x180049253  xor     r8d, r8d
0x180049256  mov     edx, eax
0x180049258  mov     rcx, rsi
0x18004925b  call    SdbReadDWORDTagRef
0x180049260  mov     r12d, eax
0x180049263  cmp     [rsi+8], r15
0x180049267  jnz     short loc_180049289
0x180049269  mov     rdx, [rsi+10h]
0x18004926d  test    rdx, rdx
0x180049270  jz      short loc_180049289
0x180049272  xor     r9d, r9d
0x180049275  mov     r8d, eax
0x180049278  mov     rcx, r15
0x18004927b  call    SdbpIsEntryIdAvailableInOtherDb
0x180049280  test    eax, eax
0x180049282  jz      short loc_180049289
0x180049284  mov     [rbp+var_20], ebx
0x180049287  jmp     short loc_180049290
0x180049289  test    r12d, r12d
0x18004928c  cmovnz  r14, r15
0x180049290  mov     r8d, 601Fh
0x180049296  mov     edx, edi
0x180049298  mov     rcx, rsi
0x18004929b  call    SdbFindFirstTagRef
0x1800492a0  mov     r12d, eax
0x1800492a3  test    eax, eax
0x1800492a5  jnz     short loc_1800492BF
0x1800492a7  mov     dword ptr [rsp+50h+var_30], edi
0x1800492ab  lea     r9, aFailedToGetMsi; "Failed to get MSI Transform for tag 0x%"...
0x1800492b2  mov     r8d, 469h
0x1800492b8  mov     ecx, ebx
0x1800492ba  jmp     loc_1800491A6
0x1800492bf  lea     r9, [rbp+arg_18]
0x1800492c3  mov     [rbp+var_10], r13
0x1800492c7  lea     r8, [rbp+var_10]
0x1800492cb  mov     [rbp+arg_18], r13d
0x1800492cf  mov     edx, r12d
0x1800492d2  mov     rcx, rsi
0x1800492d5  call    SdbTagRefToTagID
0x1800492da  test    eax, eax
0x1800492dc  jnz     short loc_180049303
0x1800492de  lea     r9, aFailedToConver_15; "Failed to convert tag 0x%x to tagid"
0x1800492e5  mov     dword ptr [rsp+50h+var_30], r12d
0x1800492ea  mov     r8d, 23Fh
0x1800492f0  lea     rdx, aSdbpgetstringr; "SdbpGetStringRefLength"
0x1800492f7  mov     ecx, ebx
0x1800492f9  call    AslLogCallPrintf
0x1800492fe  mov     edi, r13d
0x180049301  jmp     short loc_180049325
0x180049303  mov     edx, [rbp+arg_18]
0x180049306  mov     edi, r13d
0x180049309  mov     rcx, [rbp+var_10]
0x18004930d  call    SdbGetStringTagPtr
0x180049312  test    rax, rax
0x180049315  jz      short loc_180049325
0x180049317  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004931b  inc     rdi
0x18004931e  cmp     [rax+rdi*2], r13w
0x180049323  jnz     short loc_18004931B
0x180049325  mov     rcx, gs:60h
0x18004932e  lea     eax, [rdi+1]
0x180049331  mov     r8d, eax
0x180049334  mov     edx, 8; Flags
0x180049339  add     r8, r8; Size
0x18004933c  mov     [rbp+arg_18], eax
0x18004933f  mov     rcx, [rcx+30h]; HeapHandle
0x180049343  call    cs:__imp_RtlAllocateHeap
0x180049349  mov     r13, rax
0x18004934c  test    rax, rax
0x18004934f  jnz     short loc_18004937A
0x180049351  mov     [rsp+50h+var_28], r12d
0x180049356  lea     r9, aFailedToAlloca_17; "Failed to allocate buffer for %ld chara"...
0x18004935d  mov     r8d, 471h
0x180049363  mov     dword ptr [rsp+50h+var_30], edi
0x180049367  lea     rdx, aSdbreadmsitran_0; "SdbReadMsiTransformInfo"
0x18004936e  mov     ecx, ebx
0x180049370  call    AslLogCallPrintf
0x180049375  jmp     loc_1800491B2
0x18004937a  mov     r9d, [rbp+arg_18]
0x18004937e  mov     r8, r13
0x180049381  mov     edx, r12d
0x180049384  mov     rcx, rsi
0x180049387  call    SdbReadStringTagRef
0x18004938c  test    eax, eax
0x18004938e  jnz     short loc_1800493CE
0x180049390  mov     [rsp+50h+var_28], r12d
0x180049395  lea     r9, aFailedToReadFi; "Failed to read filename string tag, len"...
0x18004939c  mov     r8d, 479h
0x1800493a2  mov     dword ptr [rsp+50h+var_30], edi
0x1800493a6  lea     rdx, aSdbreadmsitran_0; "SdbReadMsiTransformInfo"
0x1800493ad  mov     ecx, ebx
0x1800493af  call    AslLogCallPrintf
0x1800493b4  mov     rcx, gs:60h
0x1800493bd  mov     rdx, r13
0x1800493c0  mov     rcx, [rcx+30h]
0x1800493c4  call    AslFree
0x1800493c9  jmp     loc_1800491B2
0x1800493ce  xor     edi, edi
0x1800493d0  cmp     [rsi+8], r15
0x1800493d4  jz      short loc_1800493F0
0x1800493d6  cmp     [rsi+10h], r15
0x1800493da  jz      short loc_1800493F0
0x1800493dc  mov     rdx, r13; String1
0x1800493df  mov     rcx, r15; int
0x1800493e2  mov     r14, r15
0x1800493e5  call    SdbpGetLibraryFile
0x1800493ea  mov     edi, eax
0x1800493ec  test    eax, eax
0x1800493ee  jnz     short loc_18004945F
0x1800493f0  mov     rcx, [rsi+10h]; int
0x1800493f4  test    rcx, rcx
0x1800493f7  jz      short loc_180049423
0x1800493f9  mov     rdx, r13; String1
0x1800493fc  mov     r14, rcx
0x1800493ff  call    SdbpGetLibraryFile
0x180049404  mov     edi, eax
0x180049406  test    eax, eax
0x180049408  jz      short loc_180049423
0x18004940a  mov     rcx, [rsi+10h]
0x18004940e  mov     r8d, 1018h
0x180049414  mov     edx, eax
0x180049416  call    SdbFindFirstTag
0x18004941b  test    eax, eax
0x18004941d  jz      short loc_18004945F
0x18004941f  xor     edi, edi
0x180049421  jmp     short loc_18004945F
0x180049423  cmp     [rbp+var_20], 0
0x180049427  jnz     short loc_18004945F
0x180049429  mov     r14, [rsi+8]
0x18004942d  mov     rdx, r13; String1
0x180049430  mov     rcx, r14; int
0x180049433  call    SdbpGetLibraryFile
0x180049438  mov     edi, eax
0x18004943a  test    eax, eax
0x18004943c  jz      short loc_18004945F
0x18004943e  mov     rdx, [rsi+10h]
0x180049442  test    rdx, rdx
0x180049445  jz      short loc_18004945F
0x180049447  mov     r9d, 601Fh
0x18004944d  mov     r8d, eax
0x180049450  mov     rcx, r15
0x180049453  call    SdbpIsEntryIdAvailableInOtherDb
0x180049458  xor     ecx, ecx
0x18004945a  test    eax, eax
0x18004945c  cmovnz  edi, ecx
0x18004945f  mov     rcx, gs:60h
0x180049468  mov     rdx, r13
0x18004946b  mov     rcx, [rcx+30h]
0x18004946f  call    AslFree
0x180049474  test    edi, edi
0x180049476  jz      short loc_1800494BB
0x180049478  test    r14, r14
0x18004947b  jz      short loc_1800494BB
0x18004947d  lea     r9, [rbp+var_18]
0x180049481  mov     r8d, edi
0x180049484  mov     rdx, r14
0x180049487  mov     rcx, rsi
0x18004948a  call    SdbTagIDToTagRef
0x18004948f  test    eax, eax
0x180049491  jnz     short loc_1800494B6
0x180049493  lea     r9, aFailedToConver_10; "Failed to convert File tag to tagref 0x"...
0x18004949a  mov     dword ptr [rsp+50h+var_30], edi
0x18004949e  mov     r8d, 4B6h
0x1800494a4  lea     rdx, aSdbreadmsitran_0; "SdbReadMsiTransformInfo"
0x1800494ab  mov     ecx, ebx
0x1800494ad  call    AslLogCallPrintf
0x1800494b2  xor     eax, eax
0x1800494b4  jmp     short loc_1800494BE
0x1800494b6  mov     eax, [rbp+var_18]
0x1800494b9  jmp     short loc_1800494BE
0x1800494bb  mov     eax, [rbp+var_14]
0x1800494be  mov     rcx, [rbp+arg_10]
0x1800494c2  mov     [rcx+0Ch], eax
0x1800494c5  mov     eax, ebx
0x1800494c7  mov     rbx, [rsp+50h+arg_0]
0x1800494cf  add     rsp, 50h
0x1800494d3  pop     r15
0x1800494d5  pop     r14
0x1800494d7  pop     r13
0x1800494d9  pop     r12
0x1800494db  pop     rdi
0x1800494dc  pop     rsi
0x1800494dd  pop     rbp
0x1800494de  retn
```
