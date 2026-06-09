# SdbQueryResultsToMiniDb

- ea: `0x180037b2c`
- end: `0x18003823a`
- name: `SdbQueryResultsToMiniDb`
- size: `1806`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x180001730`

## callees

- `0x18000f114`
- `0x180024a80`
- `0x180037b2c`
- `0x180038240`
- `0x18003f610`
- `0x18003fc80`
- `0x18003fee0`
- `0x180040100`
- `0x180040190`
- `0x180040230`
- `0x1800404f0`
- `0x180040584`
- `0x180040650`
- `0x180059235`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180037ebf`
- `ntdll!RtlReAllocateHeap` at `0x180037ebf`
- `ntdll!ZwQuerySystemTime` at `0x180037cec`
- `ntdll!ZwQuerySystemTime` at `0x180037cec`
- `ntdll!RtlFreeHeap` at `0x18003821e`
- `ntdll!RtlFreeHeap` at `0x18003821e`
- `ntdll!RtlAllocateHeap` at `0x180037bcf`
- `ntdll!RtlAllocateHeap` at `0x180037e9c`
- `ntdll!RtlAllocateHeap` at `0x180037bcf`
- `ntdll!RtlAllocateHeap` at `0x180037e9c`

## string_xrefs

- `0x180037c47`: `SdbpCreateDatabaseInMemory failed.`
- `0x180037da0`: `SdbpCopyTagrefToPdb failed [%x]`
- `0x1800380ba`: `SdbpCopyTagrefToPdb failed to copy a definition [%x]`

## pseudocode

```c
__int64 __fastcall SdbQueryResultsToMiniDb(ULONGLONG a1, __int64 a2, __int64 *a3)
{
  __int64 v4; // r14
  struct _PEB *v5; // rax
  HRESULT v6; // eax
  int v7; // r10d
  void *v8; // r9
  int v9; // ebx
  char *Heap; // rax
  char *v11; // rdi
  _DWORD *DatabaseInMemory; // rax
  __int64 v13; // rsi
  unsigned int v14; // eax
  NTSTATUS v15; // eax
  const char *v16; // r9
  __int64 v17; // r8
  unsigned __int64 i; // rdi
  __int64 v19; // rdx
  int v20; // eax
  const char *v21; // r9
  __int64 v22; // r8
  ULONGLONG v23; // r9
  ULONGLONG v24; // r15
  ULONGLONG v25; // r13
  ULONGLONG v26; // rax
  unsigned int v27; // eax
  int v28; // eax
  unsigned __int64 v29; // r12
  __int64 v30; // r9
  ULONGLONG v31; // r11
  ULONGLONG v32; // r12
  size_t v33; // r13
  char *v34; // rax
  char *v35; // r14
  int v36; // r11d
  char *v37; // rcx
  const char *v38; // r9
  __int64 v39; // r8
  ULONGLONG j; // r14
  char *v41; // r9
  int v42; // r13d
  ULONGLONG v43; // r10
  unsigned int v44; // r12d
  ULONGLONG v45; // r11
  char *v46; // rax
  char *v47; // rcx
  ULONGLONG k; // r9
  __int64 v49; // r9
  char *v50; // rdx
  unsigned __int64 v51; // r10
  unsigned __int64 v52; // rcx
  _DWORD *v53; // r8
  ULONGLONG pullResult[2]; // [rsp+38h] [rbp-59h] BYREF
  ULONGLONG ullMultiplier[2]; // [rsp+48h] [rbp-49h] BYREF
  ULONGLONG ullMultiplicand[2]; // [rsp+58h] [rbp-39h]
  PVOID Ptr[2]; // [rsp+68h] [rbp-29h]
  unsigned int v59; // [rsp+78h] [rbp-19h]
  __int64 v60; // [rsp+80h] [rbp-11h]
  union _LARGE_INTEGER CurrentTime; // [rsp+90h] [rbp-1h] BYREF
  ULONGLONG v62[10]; // [rsp+98h] [rbp+7h] BYREF
  ULONGLONG v63; // [rsp+F8h] [rbp+67h] BYREF
  __int64 v64; // [rsp+100h] [rbp+6Fh]
  __int64 *v65; // [rsp+108h] [rbp+77h]
  ULONGLONG Size; // [rsp+110h] [rbp+7Fh] BYREF

  v65 = a3;
  v64 = a2;
  v63 = a1;
  v4 = a2;
  CurrentTime.QuadPart = 0;
  v5 = NtCurrentPeb();
  *a3 = 0;
  v60 = 0;
  ullMultiplicand[0] = 0;
  ullMultiplier[0] = (ULONGLONG)v5->ProcessHeap;
  Ptr[0] = (PVOID)8;
  ullMultiplicand[1] = 0;
  Ptr[1] = 0;
  ullMultiplier[1] = 16;
  Size = 0;
  v6 = ULongLongMult(0, 0x10u, pullResult);
  v7 = -1073741675;
  if ( v6 >= 0 && ULongLongMult(8u, 0x10u, &Size) >= 0 )
  {
    Heap = (char *)RtlAllocateHeap(v8, 0, Size);
    v11 = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, Size);
      Ptr[1] = v11;
      ullMultiplicand[1] = 8;
      goto LABEL_10;
    }
    v9 = -1073741801;
  }
  else
  {
    v9 = v7;
  }
  *(_OWORD *)ullMultiplier = 0;
  *(_OWORD *)ullMultiplicand = 0;
  *(_OWORD *)Ptr = 0;
  if ( v9 < 0 )
  {
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1293, "RtlArrayInitialize failed [%x]", v9);
    v11 = (char *)Ptr[1];
    goto LABEL_104;
  }
  v11 = (char *)Ptr[1];
LABEL_10:
  DatabaseInMemory = SdbpCreateDatabaseInMemory();
  v13 = (__int64)DatabaseInMemory;
  if ( !DatabaseInMemory )
  {
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1299, "SdbpCreateDatabaseInMemory failed.");
    v9 = -1073741801;
    goto LABEL_104;
  }
  DatabaseInMemory[6] |= 0x10u;
  v14 = SdbBeginWriteListTag(DatabaseInMemory, 30722);
  if ( !v14 )
  {
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1318, "Failed writing INDEXES tag");
LABEL_14:
    v9 = -1073741595;
LABEL_102:
    SdbCloseDatabase((_QWORD *)v13);
    goto LABEL_104;
  }
  if ( !(unsigned int)SdbEndWriteListTag(v13, v14) )
  {
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1324, "Failed writing INDEXES close tag");
    goto LABEL_14;
  }
  v59 = SdbBeginWriteListTag(v13, 28673);
  if ( !v59 )
  {
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1331, "Failed writing DATABASE tag");
    goto LABEL_14;
  }
  v15 = ZwQuerySystemTime(&CurrentTime);
  v9 = v15;
  if ( v15 < 0 )
  {
    v16 = "ZwQuerySystemTime failed [%x]";
    v17 = 1341;
LABEL_101:
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", v17, v16, v15);
    goto LABEL_102;
  }
  if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SdbWriteQWORDTag)(
                        v13,
                        20481,
                        (union _LARGE_INTEGER)CurrentTime.QuadPart) )
  {
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1347, "Failed writing TIME tag");
    goto LABEL_14;
  }
  SdbWriteStringTag(v13, 24577, L"Mini DB from query results");
  SdbWriteDWORDTag(v13, 16417, *(unsigned int *)(a1 + 552));
  SdbWriteBinaryTag(v13, 36871, &GUID_MINIPDB_SDB, 16);
  for ( i = 0; i < *(unsigned int *)(v4 + 168); ++i )
  {
    v19 = *(unsigned int *)(v4 + 4 * i);
    if ( (_DWORD)v19 )
    {
      v20 = SdbpCopyTagrefToPdb(a1, v19, ullMultiplier, v13);
      v9 = v20;
      if ( v20 < 0 )
      {
        v21 = "SdbpCopyTagrefToPdb failed [%x]";
        v22 = 1371;
LABEL_29:
        AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", v22, v21, v20);
        v11 = (char *)Ptr[1];
        goto LABEL_102;
      }
    }
  }
  v11 = (char *)Ptr[1];
  v23 = 0;
  v24 = ullMultiplicand[0];
  v25 = ullMultiplier[1];
  while ( 1 )
  {
    v26 = *(unsigned int *)(v4 + 172);
    pullResult[1] = v23;
    if ( v23 >= v26 )
      break;
    v27 = *(_DWORD *)(v4 + 4 * v23 + 128);
    if ( v27 )
    {
      v60 = v27;
      LODWORD(Size) = 0;
      if ( v24 >= ullMultiplicand[1] )
      {
        if ( v24 + 1 <= ullMultiplicand[1] )
        {
          v28 = -1073741811;
          goto LABEL_52;
        }
        v29 = (unsigned __int64)Ptr[0] - 1;
        if ( (char *)Ptr[0] + v24 < (PVOID)(v24 + 1)
          || (pullResult[0] = 0, ULongLongMult(ullMultiplicand[1], ullMultiplier[1], v62) < 0)
          || (v32 = v30 & ~v29, ULongLongMult(v32, v31, pullResult) < 0) )
        {
          v28 = -1073741675;
          goto LABEL_52;
        }
        v33 = pullResult[0];
        if ( v11 )
        {
          v35 = (char *)RtlReAllocateHeap((HANDLE)ullMultiplier[0], 0, v11, pullResult[0]);
        }
        else
        {
          v34 = (char *)RtlAllocateHeap((PVOID)ullMultiplier[0], 0, pullResult[0]);
          v35 = v34;
          if ( v34 )
            memset_0(v34, 0, v33);
        }
        v25 = ullMultiplier[1];
        if ( !v35 )
        {
          v28 = -1073741801;
          goto LABEL_52;
        }
        v11 = v35;
        Ptr[1] = v35;
        v4 = v64;
        ullMultiplicand[1] = v32;
      }
      Size = 0;
      if ( ULongLongMult(v25, v24, &Size) < 0 || (v37 = &v11[Size], &v11[Size] < v11) )
      {
        v28 = -1073741675;
LABEL_52:
        v38 = "RtlArrayAppend failed [%x]";
        v39 = 1394;
LABEL_53:
        AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", v39, v38, v28);
        goto LABEL_14;
      }
      ++v24;
      *(_QWORD *)v37 = v60;
      *((_DWORD *)v37 + 2) = v36;
      ullMultiplicand[0] = v24;
    }
    ++v23;
  }
  LODWORD(Size) = SdbBeginWriteListTag(v13, 28674);
  for ( j = 0; j < v24; ++j )
  {
    pullResult[0] = 0;
    if ( ULongLongMult(v25, j, pullResult) < 0 || (v41 = &v11[pullResult[0]], &v11[pullResult[0]] < v11) || !v41 )
    {
      AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1411, "RtlArrayGet failed to return a value for index %d", j);
      goto LABEL_14;
    }
    if ( !*((_DWORD *)v41 + 1) )
    {
      v42 = *(_DWORD *)(v13 + 20);
      v43 = j;
      v44 = *(_DWORD *)v41;
      while ( 1 )
      {
        if ( !v43 )
          goto LABEL_69;
        if ( v43 - 1 >= v24
          || (pullResult[0] = 0, ULongLongMult(ullMultiplier[1], v43 - 1, pullResult) < 0)
          || (v46 = &v11[pullResult[0]], &v11[pullResult[0]] < v11)
          || !v46 )
        {
          v28 = v43 - 1;
          v39 = 1436;
          v38 = "RtlArrayGet failed to return a value for index %d";
          goto LABEL_53;
        }
        if ( *(_DWORD *)v46 == v44 )
          break;
        v43 = v45;
      }
      *((_DWORD *)v41 + 1) = *((_DWORD *)v46 + 1);
LABEL_69:
      if ( *((_DWORD *)v41 + 1) )
      {
LABEL_76:
        v25 = ullMultiplier[1];
        continue;
      }
      v20 = SdbpCopyTagrefToPdb(v63, v44, ullMultiplier, v13);
      v9 = v20;
      if ( v20 < 0 )
      {
        v21 = "SdbpCopyTagrefToPdb failed to copy a definition [%x]";
        v22 = 1463;
        goto LABEL_29;
      }
      v24 = ullMultiplicand[0];
      v11 = (char *)Ptr[1];
      if ( j < ullMultiplicand[0] )
      {
        pullResult[0] = 0;
        if ( ULongLongMult(ullMultiplier[1], j, pullResult) >= 0 )
        {
          v47 = &v11[pullResult[0]];
          if ( &v11[pullResult[0]] >= v11 )
          {
            if ( v47 )
            {
              *((_DWORD *)v47 + 1) = v42;
              goto LABEL_76;
            }
          }
        }
      }
      AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1474, "RtlArrayGet failed to return a value for index %d", j);
      goto LABEL_14;
    }
  }
  if ( !(unsigned int)SdbEndWriteListTag(v13, Size) )
  {
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1483, "Failed writing LIBRARY close tag");
    goto LABEL_14;
  }
  if ( !(unsigned int)SdbEndWriteListTag(v13, v59) )
  {
    AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1489, "Failed writing DATABASE close tag");
    goto LABEL_14;
  }
  for ( k = 0; k < v24; k = v49 + 1 )
  {
    v63 = 0;
    if ( ULongLongMult(ullMultiplier[1], k, &v63) < 0 || (v50 = &v11[v63], &v11[v63] < v11) || !v50 )
    {
      AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1502, "RtlArrayGet failed to return a value for index %d", v49);
      goto LABEL_14;
    }
    if ( *((_DWORD *)v50 + 2) )
    {
      v51 = *(_QWORD *)(v13 + 8);
      v52 = v51 + *((unsigned int *)v50 + 2);
      if ( v52 < v51
        || (v53 = (_DWORD *)(v52 + 2), v52 + 2 < v52)
        || (unsigned __int64)v53 > v51 + *(unsigned int *)(v13 + 20) - 4LL )
      {
        AslLogCallPrintf(1, "SdbQueryResultsToMiniDb", 1517, "Error calculating address of ref tagid");
        goto LABEL_102;
      }
      *v53 = *((_DWORD *)v50 + 1);
    }
  }
  v15 = SdbpFinalizeMiniDbInMemory(v13);
  v9 = v15;
  if ( v15 < 0 )
  {
    v16 = "SdbpFinalizeMiniDbInMemory failed to finalize mini db [%x]";
    v17 = 1530;
    goto LABEL_101;
  }
  v9 = 0;
  *v65 = v13;
LABEL_104:
  if ( v11 )
    RtlFreeHeap((HANDLE)ullMultiplier[0], 0, v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037b2c  mov     rax, rsp
0x180037b2f  mov     [rax+18h], r8
0x180037b33  mov     [rax+10h], rdx
0x180037b37  mov     [rax+8], rcx
0x180037b3b  push    rbp
0x180037b3c  push    rbx
0x180037b3d  push    rsi
0x180037b3e  push    rdi
0x180037b3f  push    r12
0x180037b41  push    r13
0x180037b43  push    r14
0x180037b45  push    r15
0x180037b47  lea     rbp, [rax-5Fh]
0x180037b4b  sub     rsp, 0A8h
0x180037b52  mov     r15, rcx
0x180037b55  mov     r14, rdx
0x180037b58  xor     ecx, ecx; ullMultiplicand
0x180037b5a  mov     qword ptr [rbp+57h+CurrentTime], rcx
0x180037b5e  mov     rax, gs:60h
0x180037b67  mov     [r8], rcx
0x180037b6a  lea     r8, [rbp+57h+pullResult]; pullResult
0x180037b6e  lea     r13d, [rcx+10h]
0x180037b72  mov     [rbp+57h+var_68], rcx
0x180037b76  lea     ebx, [rcx+8]
0x180037b79  mov     [rbp+57h+ullMultiplicand], rcx
0x180037b7d  mov     r9, [rax+30h]
0x180037b81  mov     edx, r13d; ullMultiplier
0x180037b84  mov     [rbp+57h+ullMultiplier], r9
0x180037b88  mov     [rbp+57h+Ptr], rbx
0x180037b8c  mov     [rbp+57h+ullMultiplicand+8], rcx
0x180037b90  mov     [rbp+57h+Ptr+8], rcx
0x180037b94  mov     [rbp+57h+ullMultiplier+8], r13
0x180037b98  mov     [rbp+57h+Size], rcx
0x180037b9c  call    ULongLongMult
0x180037ba1  mov     r10d, 0C0000095h
0x180037ba7  lea     r12d, [r10-7Eh]
0x180037bab  test    eax, eax
0x180037bad  js      short loc_180037BC1
0x180037baf  lea     r8, [rbp+57h+Size]; pullResult
0x180037bb3  mov     edx, r13d; ullMultiplier
0x180037bb6  mov     ecx, ebx; ullMultiplicand
0x180037bb8  call    ULongLongMult
0x180037bbd  test    eax, eax
0x180037bbf  jns     short loc_180037BC6
0x180037bc1  mov     ebx, r10d
0x180037bc4  jmp     short loc_180037BF8
0x180037bc6  mov     r8, [rbp+57h+Size]; Size
0x180037bca  xor     edx, edx; Flags
0x180037bcc  mov     rcx, r9; HeapHandle
0x180037bcf  call    cs:__imp_RtlAllocateHeap
0x180037bd5  mov     rdi, rax
0x180037bd8  test    rax, rax
0x180037bdb  jz      short loc_180037BF5
0x180037bdd  mov     r8, [rbp+57h+Size]; Size
0x180037be1  xor     edx, edx; Val
0x180037be3  mov     rcx, rax; void *
0x180037be6  call    memset_0
0x180037beb  mov     [rbp+57h+Ptr+8], rdi
0x180037bef  mov     [rbp+57h+ullMultiplicand+8], rbx
0x180037bf3  jmp     short loc_180037C3A
0x180037bf5  mov     ebx, r12d
0x180037bf8  xorps   xmm0, xmm0
0x180037bfb  movups  xmmword ptr [rbp+57h+ullMultiplier], xmm0
0x180037bff  movups  xmmword ptr [rbp+57h+ullMultiplicand], xmm0
0x180037c03  movups  xmmword ptr [rbp+57h+Ptr], xmm0
0x180037c07  test    ebx, ebx
0x180037c09  jns     short loc_180037C36
0x180037c0b  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x180037c12  mov     [rsp+20h], ebx
0x180037c16  mov     r8d, 50Dh
0x180037c1c  lea     rdx, aSdbqueryresult_0; "SdbQueryResultsToMiniDb"
0x180037c23  mov     ecx, 1
0x180037c28  call    AslLogCallPrintf
0x180037c2d  mov     rdi, [rbp+57h+Ptr+8]
0x180037c31  jmp     loc_180038210
0x180037c36  mov     rdi, [rbp+57h+Ptr+8]
0x180037c3a  call    SdbpCreateDatabaseInMemory
0x180037c3f  mov     rsi, rax
0x180037c42  test    rax, rax
0x180037c45  jnz     short loc_180037C6B
0x180037c47  lea     r9, aSdbpcreatedata_0; "SdbpCreateDatabaseInMemory failed."
0x180037c4e  mov     r8d, 513h
0x180037c54  lea     rdx, aSdbqueryresult_0; "SdbQueryResultsToMiniDb"
0x180037c5b  lea     ecx, [rax+1]
0x180037c5e  call    AslLogCallPrintf
0x180037c63  mov     ebx, r12d
0x180037c66  jmp     loc_180038210
0x180037c6b  or      [rax+18h], r13d
0x180037c6f  mov     edx, 7802h
0x180037c74  mov     rcx, rsi
0x180037c77  call    SdbBeginWriteListTag
0x180037c7c  test    eax, eax
0x180037c7e  jnz     short loc_180037CA8
0x180037c80  lea     r9, aFailedWritingI_0; "Failed writing INDEXES tag"
0x180037c87  mov     r8d, 526h
0x180037c8d  lea     rdx, aSdbqueryresult_0; "SdbQueryResultsToMiniDb"
0x180037c94  mov     ecx, 1
0x180037c99  call    AslLogCallPrintf
0x180037c9e  mov     ebx, 0C00000E5h
0x180037ca3  jmp     loc_1800381FD
0x180037ca8  mov     edx, eax
0x180037caa  mov     rcx, rsi
0x180037cad  call    SdbEndWriteListTag
0x180037cb2  test    eax, eax
0x180037cb4  jnz     short loc_180037CC5
0x180037cb6  lea     r9, aFailedWritingI; "Failed writing INDEXES close tag"
0x180037cbd  mov     r8d, 52Ch
0x180037cc3  jmp     short loc_180037C8D
0x180037cc5  mov     edx, 7001h
0x180037cca  mov     rcx, rsi
0x180037ccd  call    SdbBeginWriteListTag
0x180037cd2  mov     [rbp+57h+var_70], eax
0x180037cd5  test    eax, eax
0x180037cd7  jnz     short loc_180037CE8
0x180037cd9  lea     r9, aFailedWritingD_0; "Failed writing DATABASE tag"
0x180037ce0  mov     r8d, 533h
0x180037ce6  jmp     short loc_180037C8D
0x180037ce8  lea     rcx, [rbp+57h+CurrentTime]; CurrentTime
0x180037cec  call    cs:__imp_ZwQuerySystemTime
0x180037cf2  mov     ebx, eax
0x180037cf4  test    eax, eax
0x180037cf6  jns     short loc_180037D0A
0x180037cf8  lea     r9, aZwquerysystemt; "ZwQuerySystemTime failed [%x]"
0x180037cff  mov     r8d, 53Dh
0x180037d05  jmp     loc_1800381E8
0x180037d0a  mov     r8, qword ptr [rbp+57h+CurrentTime]
0x180037d0e  mov     edx, 5001h
0x180037d13  mov     rcx, rsi
0x180037d16  call    SdbWriteQWORDTag
0x180037d1b  test    eax, eax
0x180037d1d  jnz     short loc_180037D31
0x180037d1f  lea     r9, aFailedWritingT; "Failed writing TIME tag"
0x180037d26  mov     r8d, 543h
0x180037d2c  jmp     loc_180037C8D
0x180037d31  mov     edx, 6001h
0x180037d36  lea     r8, aMiniDbFromQuer; "Mini DB from query results"
0x180037d3d  mov     rcx, rsi
0x180037d40  call    SdbWriteStringTag
0x180037d45  mov     r8d, [r15+228h]
0x180037d4c  mov     edx, 4021h
0x180037d51  mov     rcx, rsi
0x180037d54  call    SdbWriteDWORDTag
0x180037d59  mov     edx, 9007h
0x180037d5e  lea     r8, GUID_MINIPDB_SDB
0x180037d65  mov     r9d, r13d
0x180037d68  mov     rcx, rsi
0x180037d6b  call    SdbWriteBinaryTag
0x180037d70  xor     edi, edi
0x180037d72  mov     eax, [r14+0A8h]
0x180037d79  cmp     rdi, rax
0x180037d7c  jnb     short loc_180037DCB
0x180037d7e  mov     edx, [r14+rdi*4]
0x180037d82  test    edx, edx
0x180037d84  jz      short loc_180037D9B
0x180037d86  mov     r9, rsi
0x180037d89  lea     r8, [rbp+57h+ullMultiplier]
0x180037d8d  mov     rcx, r15
0x180037d90  call    SdbpCopyTagrefToPdb
0x180037d95  mov     ebx, eax
0x180037d97  test    eax, eax
0x180037d99  js      short loc_180037DA0
0x180037d9b  inc     rdi
0x180037d9e  jmp     short loc_180037D72
0x180037da0  lea     r9, aSdbpcopytagref; "SdbpCopyTagrefToPdb failed [%x]"
0x180037da7  mov     r8d, 55Bh
0x180037dad  lea     rdx, aSdbqueryresult_0; "SdbQueryResultsToMiniDb"
0x180037db4  mov     [rsp+20h], eax
0x180037db8  mov     ecx, 1
0x180037dbd  call    AslLogCallPrintf
0x180037dc2  mov     rdi, [rbp+57h+Ptr+8]
0x180037dc6  jmp     loc_1800381FD
0x180037dcb  mov     rdi, [rbp+57h+Ptr+8]
0x180037dcf  xor     r9d, r9d
0x180037dd2  mov     r15, [rbp+57h+ullMultiplicand]
0x180037dd6  mov     r13, [rbp+57h+ullMultiplier+8]
0x180037dda  mov     eax, [r14+0ACh]
0x180037de1  mov     [rbp+57h+var_A8], r9
0x180037de5  cmp     r9, rax
0x180037de8  jnb     loc_180037F62
0x180037dee  mov     eax, [r14+r9*4+80h]
0x180037df6  test    eax, eax
0x180037df8  jz      loc_180037F2E
0x180037dfe  mov     r10, [rbp+57h+ullMultiplicand+8]
0x180037e02  xor     r11d, r11d
0x180037e05  mov     dword ptr [rbp+57h+var_68], eax
0x180037e08  mov     dword ptr [rbp+57h+var_68+4], 0
0x180037e0f  mov     dword ptr [rbp+57h+Size], r11d
0x180037e13  cmp     r15, r10
0x180037e16  jb      loc_180037EF3
0x180037e1c  lea     rax, [r15+1]
0x180037e20  cmp     rax, r10
0x180037e23  ja      short loc_180037E2C
0x180037e25  mov     eax, 0C000000Dh
0x180037e2a  jmp     short loc_180037E64
0x180037e2c  mov     r12, [rbp+57h+Ptr]
0x180037e30  dec     r12
0x180037e33  lea     r9, [r12+rax]
0x180037e37  cmp     r9, rax
0x180037e3a  jb      short loc_180037E5B
0x180037e3c  mov     [rbp+57h+pullResult], r11
0x180037e40  lea     r8, [rbp+57h+var_50]; pullResult
0x180037e44  mov     r11, [rbp+57h+ullMultiplier+8]
0x180037e48  mov     rcx, r10; ullMultiplicand
0x180037e4b  mov     rdx, r11; ullMultiplier
0x180037e4e  call    ULongLongMult
0x180037e53  test    eax, eax
0x180037e55  jns     short loc_180037E71
0x180037e57  mov     r13, [rbp+57h+ullMultiplier+8]
0x180037e5b  mov     r9, [rbp+57h+var_A8]
0x180037e5f  mov     eax, 0C0000095h
0x180037e64  test    eax, eax
0x180037e66  jnz     loc_180037F3B
0x180037e6c  jmp     loc_180037F2E
0x180037e71  not     r12
0x180037e74  lea     r8, [rbp+57h+pullResult]; pullResult
0x180037e78  and     r12, r9
0x180037e7b  mov     rdx, r11; ullMultiplier
0x180037e7e  mov     rcx, r12; ullMultiplicand
0x180037e81  call    ULongLongMult
0x180037e86  test    eax, eax
0x180037e88  js      short loc_180037E57
0x180037e8a  mov     r13, [rbp+57h+pullResult]
0x180037e8e  xor     edx, edx; Flags
0x180037e90  mov     rcx, [rbp+57h+ullMultiplier]; Heap
0x180037e94  test    rdi, rdi
0x180037e97  jnz     short loc_180037EB9
0x180037e99  mov     r8, r13; Size
0x180037e9c  call    cs:__imp_RtlAllocateHeap
0x180037ea2  mov     r14, rax
0x180037ea5  test    rax, rax
0x180037ea8  jz      short loc_180037EC8
0x180037eaa  mov     r8, r13; Size
0x180037ead  xor     edx, edx; Val
0x180037eaf  mov     rcx, rax; void *
0x180037eb2  call    memset_0
0x180037eb7  jmp     short loc_180037EC8
0x180037eb9  mov     r9, r13; Size
0x180037ebc  mov     r8, rdi; Ptr
0x180037ebf  call    cs:__imp_RtlReAllocateHeap
0x180037ec5  mov     r14, rax
0x180037ec8  mov     r9, [rbp+57h+var_A8]
0x180037ecc  mov     r13, [rbp+57h+ullMultiplier+8]
0x180037ed0  test    r14, r14
0x180037ed3  jnz     short loc_180037EE0
0x180037ed5  mov     r14, [rbp+57h+arg_8]
0x180037ed9  mov     eax, 0C0000017h
0x180037ede  jmp     short loc_180037E64
0x180037ee0  mov     r11d, dword ptr [rbp+57h+Size]
0x180037ee4  mov     rdi, r14
0x180037ee7  mov     [rbp+57h+Ptr+8], r14
0x180037eeb  mov     r14, [rbp+57h+arg_8]
0x180037eef  mov     [rbp+57h+ullMultiplicand+8], r12
0x180037ef3  lea     r8, [rbp+57h+Size]; pullResult
0x180037ef7  mov     [rbp+57h+Size], 0
0x180037eff  mov     rdx, r15; ullMultiplier
0x180037f02  mov     rcx, r13; ullMultiplicand
0x180037f05  call    ULongLongMult
0x180037f0a  test    eax, eax
0x180037f0c  js      short loc_180037F36
0x180037f0e  mov     rcx, [rbp+57h+Size]
0x180037f12  add     rcx, rdi
0x180037f15  cmp     rcx, rdi
0x180037f18  jb      short loc_180037F36
0x180037f1a  movsd   xmm0, [rbp+57h+var_68]
0x180037f1f  inc     r15
0x180037f22  movsd   qword ptr [rcx], xmm0
0x180037f26  mov     [rcx+8], r11d
0x180037f2a  mov     [rbp+57h+ullMultiplicand], r15
0x180037f2e  inc     r9
0x180037f31  jmp     loc_180037DDA
0x180037f36  mov     eax, 0C0000095h
0x180037f3b  lea     r9, aRtlarrayappend; "RtlArrayAppend failed [%x]"
0x180037f42  mov     r8d, 572h
0x180037f48  mov     [rsp+20h], eax
0x180037f4c  lea     rdx, aSdbqueryresult_0; "SdbQueryResultsToMiniDb"
0x180037f53  mov     ecx, 1
0x180037f58  call    AslLogCallPrintf
0x180037f5d  jmp     loc_180037C9E
0x180037f62  mov     edx, 7002h
0x180037f67  mov     rcx, rsi
0x180037f6a  call    SdbBeginWriteListTag
0x180037f6f  mov     dword ptr [rbp+57h+Size], eax
0x180037f72  xor     r14d, r14d
0x180037f75  cmp     r14, r15
0x180037f78  jnb     loc_1800380E3
0x180037f7e  lea     r8, [rbp+57h+pullResult]; pullResult
0x180037f82  mov     [rbp+57h+pullResult], 0
0x180037f8a  mov     rdx, r14; ullMultiplier
0x180037f8d  mov     rcx, r13; ullMultiplicand
0x180037f90  call    ULongLongMult
0x180037f95  test    eax, eax
0x180037f97  js      loc_1800380CC
0x180037f9d  mov     r9, [rbp+57h+pullResult]
0x180037fa1  add     r9, rdi
0x180037fa4  cmp     r9, rdi
0x180037fa7  jb      loc_1800380CC
0x180037fad  test    r9, r9
0x180037fb0  jz      loc_1800380CC
0x180037fb6  cmp     dword ptr [r9+4], 0
0x180037fbb  jnz     loc_180038085
  ... truncated ...
```
