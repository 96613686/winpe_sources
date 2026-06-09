# SdbOpenDatabaseEx

- ea: `0x180002f60`
- end: `0x1800032e5`
- name: `SdbOpenDatabaseEx`
- size: `901`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002be0`
- `0x180002f50`
- `0x1800440a0`
- `0x180047710`
- `0x180048668`
- `0x18004cde0`

## callees

- `0x180002934`
- `0x180002f60`
- `0x180005dfc`
- `0x18000f080`
- `0x18000f114`
- `0x180015a6c`
- `0x180015e8c`
- `0x180018f20`
- `0x18002e818`
- `0x180032d2c`
- `0x1800353b0`
- `0x1800500bc`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180002feb`
- `ntdll!RtlAllocateHeap` at `0x180002feb`

## string_xrefs

- `0x180002f8a`: `Flags:%d; DatabasePath:%ws`
- `0x180002fa5`: `SdbOpenDatabaseEx`
- `0x18000300a`: `SdbOpenDatabaseEx`
- `0x18000309f`: `SdbOpenDatabaseEx`
- `0x1800030eb`: `SdbOpenDatabaseEx`
- `0x180003117`: `SdbOpenDatabaseEx`
- `0x18000317d`: `SdbOpenDatabaseEx`
- `0x18000324f`: `SdbOpenDatabaseEx`
- `0x18000328e`: `SdbOpenDatabaseEx`
- `0x180003170`: `Failed to create file mapping [%x]`
- `0x180003105`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x1800030da`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x180003281`: `Failed to open SDB - File size too large or small.`
- `0x1800031f1`: `Failed to read database header`
- `0x180003242`: `SdbpOpenCompressedDatabase failed to open compressed database.`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(const wchar_t *a1, __int64 a2, unsigned int a3)
{
  const WCHAR *v5; // rax
  _QWORD *Heap; // rax
  _QWORD *v7; // rbx
  int MergeRedirectPath; // eax
  int v9; // r14d
  int v10; // esi
  const wchar_t *FileNamePart; // rax
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rsi
  __int64 v17; // rdx
  __int64 v19; // [rsp+20h] [rbp-40h]
  int v20; // [rsp+30h] [rbp-30h] BYREF
  WCHAR *v21; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-20h] BYREF
  __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  int v24; // [rsp+50h] [rbp-10h]

  v23 = 0;
  v24 = 0;
  v20 = 0;
  v5 = a1;
  if ( !a1 )
    v5 = &word_1800626B4;
  AslLogCallPrintf(3, "SdbOpenDatabaseEx", 2501, "Flags:%d; DatabasePath:%ws", a3, v5);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v22 = Heap;
  v7 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xA80u);
    v21 = 0;
    if ( (a3 & 0x10) != 0 )
      goto LABEL_47;
    MergeRedirectPath = SdbGetMergeRedirectPath(&v21, &v20, (a3 & 0x20) == 0, a1);
    v9 = MergeRedirectPath;
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          "SdbOpenDatabaseEx",
          2527,
          "SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]",
          MergeRedirectPath);
      v10 = v9;
    }
    else if ( v21 )
    {
      if ( (a3 & 0x20) != 0 )
      {
        if ( !v20 )
          *((_DWORD *)v7 + 6) |= 0x20u;
      }
      else if ( v20 )
      {
        FileNamePart = AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2539,
          "Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].",
          FileNamePart);
      }
      v12 = AslFileMappingCreate((const wchar_t ***)v7, v21, 0, 0, 0);
      v10 = v12;
      if ( v12 < 0 )
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2558,
          "Failed to create file mapping for redirected SDB file [%x]",
          v12);
    }
    else
    {
      v10 = -1073741772;
    }
    if ( v21 )
      AslFree(NtCurrentPeb()->ProcessHeap, v21);
    if ( v10 < 0 || !*v7 )
    {
LABEL_47:
      v13 = AslFileMappingCreate((const wchar_t ***)v7, a1, 0, 0, 0);
      if ( v13 < 0 )
      {
        v14 = "Failed to create file mapping [%x]";
        v15 = 2580;
LABEL_25:
        LODWORD(v19) = v13;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", v15, v14, v19);
        goto LABEL_42;
      }
    }
    v16 = *(_QWORD *)(*v7 + 24LL);
    if ( (unsigned __int64)(v16 - 42) > 0xFFFFFD5 )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2589, "Failed to open SDB - File size too large or small.");
      goto LABEL_42;
    }
    v13 = AslFileMappingEnsureMappedAsEx(*v7);
    if ( v13 < 0 )
    {
      v14 = "Failed to map SDB [%x]";
      v15 = 2595;
      goto LABEL_25;
    }
    *((_DWORD *)v7 + 4) = 0;
    *((_DWORD *)v7 + 5) = v16;
    v7[1] = AslFileMappingGetViewBase(*v7);
    if ( !(unsigned int)SdbpReadMappedData(v7, 0, &v23, 12) )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2608, "Failed to read database header");
      goto LABEL_42;
    }
    v13 = v24;
    if ( v24 != 1717724275 )
    {
      if ( v24 == 1717724282 )
      {
        if ( (unsigned int)SdbpOpenCompressedDatabase(&v22, v17, a3) )
          return v22;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2627, "SdbpOpenCompressedDatabase failed to open compressed database.");
        v7 = v22;
LABEL_42:
        if ( v7 )
        {
          AslFileMappingDelete(*v7);
          AslFree(NtCurrentPeb()->ProcessHeap, v7);
        }
        return 0;
      }
      if ( (a3 & 2) == 0 )
      {
        v14 = "Magic does not match a valid value: 0x%lx";
        v15 = 2621;
        goto LABEL_25;
      }
    }
    if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v23, a3) )
      return v7;
    goto LABEL_42;
  }
  AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2509, "Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x180002f60  mov     r11, rsp
0x180002f63  mov     [r11+10h], rbx
0x180002f67  mov     [r11+20h], rsi
0x180002f6b  push    rbp
0x180002f6c  push    rdi
0x180002f6d  push    r12
0x180002f6f  push    r13
0x180002f71  push    r14
0x180002f73  mov     rbp, rsp
0x180002f76  sub     rsp, 60h
0x180002f7a  mov     rax, cs:__security_cookie
0x180002f81  xor     rax, rsp
0x180002f84  mov     [rbp+var_8], rax
0x180002f88  xor     eax, eax
0x180002f8a  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x180002f91  mov     r13, rcx
0x180002f94  mov     [rbp+var_18], rax
0x180002f98  mov     [rbp+var_10], eax
0x180002f9b  lea     rcx, word_1800626B4
0x180002fa2  mov     [rbp+var_30], eax
0x180002fa5  lea     rdx, aSdbopendatabas_0; "SdbOpenDatabaseEx"
0x180002fac  mov     r12d, r8d
0x180002faf  test    r13, r13
0x180002fb2  mov     rax, r13
0x180002fb5  cmovz   rax, rcx
0x180002fb9  mov     ecx, 3
0x180002fbe  mov     [r11-60h], rax
0x180002fc2  mov     [r11-68h], r8d
0x180002fc6  mov     r8d, 9C5h
0x180002fcc  call    AslLogCallPrintf
0x180002fd1  mov     rcx, gs:60h
0x180002fda  mov     edi, 0A80h
0x180002fdf  mov     r8d, edi; Size
0x180002fe2  mov     edx, 8; Flags
0x180002fe7  mov     rcx, [rcx+30h]; HeapHandle
0x180002feb  call    cs:__imp_RtlAllocateHeap
0x180002ff1  mov     [rbp+var_20], rax
0x180002ff5  mov     rbx, rax
0x180002ff8  test    rax, rax
0x180002ffb  jnz     short loc_18000301E
0x180002ffd  lea     r9, aFailedToAlloca_27; "Failed to allocate DB structure"
0x180003004  mov     r8d, 9CDh
0x18000300a  lea     rdx, aSdbopendatabas_0; "SdbOpenDatabaseEx"
0x180003011  lea     ecx, [rax+1]
0x180003014  call    AslLogCallPrintf
0x180003019  jmp     loc_1800032BE
0x18000301e  mov     r8, rdi; Size
0x180003021  xor     edx, edx; Val
0x180003023  mov     rcx, rbx; void *
0x180003026  call    memset_0
0x18000302b  mov     [rbp+var_28], 0
0x180003033  mov     edi, 1
0x180003038  test    r12b, 10h
0x18000303c  jnz     loc_180003152
0x180003042  lea     r8d, [rdi-1]
0x180003046  mov     esi, r12d
0x180003049  and     esi, 20h
0x18000304c  lea     rdx, [rbp+var_30]
0x180003050  mov     r9, r13
0x180003053  lea     rcx, [rbp+var_28]
0x180003057  setz    r8b
0x18000305b  call    SdbGetMergeRedirectPath
0x180003060  mov     r14d, eax
0x180003063  test    eax, eax
0x180003065  js      loc_1800030FB
0x18000306b  cmp     [rbp+var_28], 0
0x180003070  jnz     short loc_18000307C
0x180003072  mov     esi, 0C0000034h
0x180003077  jmp     loc_18000312B
0x18000307c  test    esi, esi
0x18000307e  jnz     short loc_1800030AF
0x180003080  cmp     [rbp+var_30], esi
0x180003083  jz      short loc_1800030B9
0x180003085  mov     rcx, r13
0x180003088  call    AslPathGetFileNamePart
0x18000308d  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x180003094  mov     [rsp+60h+var_40], rax
0x180003099  mov     r8d, 9EBh
0x18000309f  lea     rdx, aSdbopendatabas_0; "SdbOpenDatabaseEx"
0x1800030a6  mov     ecx, edi
0x1800030a8  call    AslLogCallPrintf
0x1800030ad  jmp     short loc_1800030B9
0x1800030af  cmp     [rbp+var_30], 0
0x1800030b3  jnz     short loc_1800030B9
0x1800030b5  or      dword ptr [rbx+18h], 20h
0x1800030b9  mov     rdx, [rbp+var_28]
0x1800030bd  xor     r9d, r9d
0x1800030c0  xor     r8d, r8d
0x1800030c3  mov     [rsp+60h+var_40], 0
0x1800030cc  mov     rcx, rbx
0x1800030cf  call    AslFileMappingCreate
0x1800030d4  mov     esi, eax
0x1800030d6  test    eax, eax
0x1800030d8  jns     short loc_18000312B
0x1800030da  lea     r9, aFailedToCreate_7; "Failed to create file mapping for redir"...
0x1800030e1  mov     dword ptr [rsp+60h+var_40], eax
0x1800030e5  mov     r8d, 9FEh
0x1800030eb  lea     rdx, aSdbopendatabas_0; "SdbOpenDatabaseEx"
0x1800030f2  mov     ecx, edi
0x1800030f4  call    AslLogCallPrintf
0x1800030f9  jmp     short loc_18000312B
0x1800030fb  mov     esi, 0C0000034h
0x180003100  cmp     r14d, esi
0x180003103  jz      short loc_180003128
0x180003105  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x18000310c  mov     dword ptr [rsp+60h+var_40], r14d
0x180003111  mov     r8d, 9DFh
0x180003117  lea     rdx, aSdbopendatabas_0; "SdbOpenDatabaseEx"
0x18000311e  mov     ecx, 3
0x180003123  call    AslLogCallPrintf
0x180003128  mov     esi, r14d
0x18000312b  cmp     [rbp+var_28], 0
0x180003130  jz      short loc_180003148
0x180003132  mov     rcx, gs:60h
0x18000313b  mov     rdx, [rbp+var_28]
0x18000313f  mov     rcx, [rcx+30h]
0x180003143  call    AslFree
0x180003148  test    esi, esi
0x18000314a  js      short loc_180003152
0x18000314c  cmp     qword ptr [rbx], 0
0x180003150  jnz     short loc_180003194
0x180003152  xor     r9d, r9d
0x180003155  mov     [rsp+60h+var_40], 0
0x18000315e  xor     r8d, r8d
0x180003161  mov     rdx, r13
0x180003164  mov     rcx, rbx
0x180003167  call    AslFileMappingCreate
0x18000316c  test    eax, eax
0x18000316e  jns     short loc_180003194
0x180003170  lea     r9, aFailedToCreate_1; "Failed to create file mapping [%x]"
0x180003177  mov     r8d, 0A14h
0x18000317d  lea     rdx, aSdbopendatabas_0; "SdbOpenDatabaseEx"
0x180003184  mov     dword ptr [rsp+60h+var_40], eax
0x180003188  mov     ecx, edi
0x18000318a  call    AslLogCallPrintf
0x18000318f  jmp     loc_18000329C
0x180003194  mov     rcx, [rbx]
0x180003197  mov     rsi, [rcx+18h]
0x18000319b  lea     rax, [rsi-2Ah]
0x18000319f  cmp     rax, 0FFFFFD5h
0x1800031a5  ja      loc_180003281
0x1800031ab  call    AslFileMappingEnsureMappedAsEx
0x1800031b0  test    eax, eax
0x1800031b2  jns     short loc_1800031C3
0x1800031b4  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x1800031bb  mov     r8d, 0A23h
0x1800031c1  jmp     short loc_18000317D
0x1800031c3  mov     dword ptr [rbx+10h], 0
0x1800031ca  mov     [rbx+14h], esi
0x1800031cd  mov     rcx, [rbx]
0x1800031d0  call    AslFileMappingGetViewBase
0x1800031d5  mov     r9d, 0Ch
0x1800031db  mov     [rbx+8], rax
0x1800031df  lea     r8, [rbp+var_18]
0x1800031e3  xor     edx, edx
0x1800031e5  mov     rcx, rbx
0x1800031e8  call    SdbpReadMappedData
0x1800031ed  test    eax, eax
0x1800031ef  jnz     short loc_180003203
0x1800031f1  lea     r9, aFailedToReadDa_1; "Failed to read database header"
0x1800031f8  mov     r8d, 0A30h
0x1800031fe  jmp     loc_18000328E
0x180003203  mov     eax, [rbp+var_10]
0x180003206  mov     ecx, 6662647Ah
0x18000320b  cmp     eax, 66626473h
0x180003210  jz      short loc_18000322E
0x180003212  cmp     eax, ecx
0x180003214  jz      short loc_180003232
0x180003216  test    r12b, 2
0x18000321a  jnz     short loc_18000322E
0x18000321c  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x180003223  mov     r8d, 0A3Dh
0x180003229  jmp     loc_18000317D
0x18000322e  cmp     eax, ecx
0x180003230  jnz     short loc_180003269
0x180003232  mov     r8d, r12d
0x180003235  lea     rcx, [rbp+var_20]
0x180003239  call    SdbpOpenCompressedDatabase
0x18000323e  test    eax, eax
0x180003240  jnz     short loc_180003263
0x180003242  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x180003249  mov     r8d, 0A43h
0x18000324f  lea     rdx, aSdbopendatabas_0; "SdbOpenDatabaseEx"
0x180003256  mov     ecx, edi
0x180003258  call    AslLogCallPrintf
0x18000325d  mov     rbx, [rbp+var_20]
0x180003261  jmp     short loc_18000329C
0x180003263  mov     rbx, [rbp+var_20]
0x180003267  jmp     short loc_18000327C
0x180003269  mov     r8d, r12d
0x18000326c  lea     rdx, [rbp+var_18]
0x180003270  mov     rcx, rbx
0x180003273  call    SdbpValidateAndApplyCompatFlags
0x180003278  test    eax, eax
0x18000327a  jz      short loc_18000329C
0x18000327c  mov     rax, rbx
0x18000327f  jmp     short loc_1800032C0
0x180003281  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x180003288  mov     r8d, 0A1Dh
0x18000328e  lea     rdx, aSdbopendatabas_0; "SdbOpenDatabaseEx"
0x180003295  mov     ecx, edi
0x180003297  call    AslLogCallPrintf
0x18000329c  test    rbx, rbx
0x18000329f  jz      short loc_1800032BE
0x1800032a1  mov     rcx, [rbx]
0x1800032a4  call    AslFileMappingDelete
0x1800032a9  mov     rcx, gs:60h
0x1800032b2  mov     rdx, rbx
0x1800032b5  mov     rcx, [rcx+30h]
0x1800032b9  call    AslFree
0x1800032be  xor     eax, eax
0x1800032c0  mov     rcx, [rbp+var_8]
0x1800032c4  xor     rcx, rsp; StackCookie
0x1800032c7  call    __security_check_cookie
0x1800032cc  lea     r11, [rsp+60h+var_s0]
0x1800032d1  mov     rbx, [r11+38h]
0x1800032d5  mov     rsi, [r11+48h]
0x1800032d9  mov     rsp, r11
0x1800032dc  pop     r14
0x1800032de  pop     r13
0x1800032e0  pop     r12
0x1800032e2  pop     rdi
0x1800032e3  pop     rbp
0x1800032e4  retn
```
