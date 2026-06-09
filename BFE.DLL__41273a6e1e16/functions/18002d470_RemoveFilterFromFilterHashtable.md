# RemoveFilterFromFilterHashtable

- ea: `0x18002d470`
- end: `0x18002d744`
- name: `RemoveFilterFromFilterHashtable`
- size: `724`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800289d0`
- `0x180033f90`
- `0x18007fcc8`

## callees

- `0x1800135ac`
- `0x1800197d0`
- `0x18002d470`
- `0x180055f04`
- `0x1800560f8`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18002d607`
- `ntdll!RtlRemoveEntryHashTable` at `0x18002d607`
- `ntdll!RtlLookupEntryHashTable` at `0x18002d5b2`
- `ntdll!RtlLookupEntryHashTable` at `0x18002d5b2`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002d693`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002d693`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d493`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d493`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d652`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d70a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d652`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d70a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002d6b5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002d6b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d638`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d638`

## string_xrefs

- `0x18002d730`: `RtlRemoveEntryHashTable`
- `0x18002d716`: `RemoveFilterFromFilterHashtable`

## pseudocode

```c
__int64 __fastcall RemoveFilterFromFilterHashtable(unsigned __int16 a1, unsigned __int64 a2)
{
  int v2; // edi
  void *v4; // rsi
  unsigned __int8 *v5; // r8
  __int64 v6; // rdx
  __int64 i; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v15; // rax
  __int128 v16; // [rsp+20h] [rbp-28h] BYREF
  __int64 v17; // [rsp+30h] [rbp-18h]
  __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v2 = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)gWfpGlobal + 25);
  v4 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  _mm_lfence();
  _mm_lfence();
  v5 = (unsigned __int8 *)gWfpGlobal;
  _mm_lfence();
  v6 = v5[331]
     + 37
     * (v5[330]
      + 37
      * (v5[329]
       + 37
       * (v5[328]
        + 37
        * (HIBYTE(a2)
         + 37
         * (BYTE6(a2)
          + 37
          * (BYTE5(a2)
           + 37
           * (BYTE4(a2)
            + 37
            * (BYTE3(a2)
             + 37
             * (BYTE2(a2) + 37
                          * (BYTE1(a2) + 37 * ((unsigned __int8)a2 + 37 * (37LL * (unsigned __int8)v2 + BYTE1(v2)))))))))))));
  if ( !v6 )
    v6 = -1;
  for ( i = RtlLookupEntryHashTable(*((_QWORD *)gWfpGlobal + 40), v6, &v16);
        i;
        i = RtlGetNextEntryHashTable(*((_QWORD *)gWfpGlobal + 40), &v16) )
  {
    v9 = gWfpGlobal;
    if ( *(_DWORD *)(i + 24) == *((_DWORD *)gWfpGlobal + 82) && *(_DWORD *)(i + 28) == v2 && *(_QWORD *)(i + 32) == a2 )
    {
      v4 = (void *)i;
      v18 = i;
      v10 = 0;
      goto LABEL_9;
    }
  }
  v15 = WfpReportSysErrorAsNtStatus(v8, "RtlLookupEntryHashTable", 3221225473LL);
  v10 = v15;
  if ( v15 )
  {
    WfpReportError(v15, "FindEntryFromFilterHashtable");
    LeaveCriticalSection((LPCRITICAL_SECTION)gWfpGlobal + 25);
    goto LABEL_21;
  }
  v9 = gWfpGlobal;
LABEL_9:
  if ( (unsigned __int8)RtlRemoveEntryHashTable(v9[40], v4, 0) )
  {
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v12, v11, v13) )
    {
      WfpMemFree25B(&v18);
    }
    else
    {
      if ( gWfpTrackHeapBytes && v4 )
        _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v4));
      HeapFree(gWfpHeap, 0, v4);
    }
  }
  else
  {
    v10 = WfpReportSysErrorAsNtStatus(v12, "RtlRemoveEntryHashTable", 3221225473LL);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)gWfpGlobal + 25);
  if ( v10 )
LABEL_21:
    WfpReportError(v10, "RemoveFilterFromFilterHashtable");
  return v10;
}

```

## disassembly

```asm
0x18002d470  mov     [rsp+arg_0], rbx
0x18002d475  mov     [rsp+arg_10], rsi
0x18002d47a  push    rdi
0x18002d47b  sub     rsp, 40h
0x18002d47f  movzx   edi, cx
0x18002d482  mov     rbx, rdx
0x18002d485  mov     rcx, cs:gWfpGlobal
0x18002d48c  add     rcx, 3E8h; lpCriticalSection
0x18002d493  call    cs:__imp_EnterCriticalSection
0x18002d49a  nop     dword ptr [rax+rax+00h]
0x18002d49f  xor     eax, eax
0x18002d4a1  xor     esi, esi
0x18002d4a3  mov     [rsp+48h+var_18], rax
0x18002d4a8  xorps   xmm0, xmm0
0x18002d4ab  movzx   eax, di
0x18002d4ae  mov     [rsp+48h+arg_8], rsi
0x18002d4b3  shr     ax, 8
0x18002d4b7  movzx   ecx, ax
0x18002d4ba  movzx   eax, dil
0x18002d4be  movups  [rsp+48h+var_28], xmm0
0x18002d4c3  lfence
0x18002d4c6  imul    rax, 25h ; '%'
0x18002d4ca  add     rcx, rax
0x18002d4cd  lfence
0x18002d4d0  mov     r8, cs:gWfpGlobal
0x18002d4d7  imul    rdx, rcx, 25h ; '%'
0x18002d4db  movzx   eax, bl
0x18002d4de  add     rdx, rax
0x18002d4e1  mov     rax, rbx
0x18002d4e4  shr     rax, 8
0x18002d4e8  movzx   eax, al
0x18002d4eb  imul    rcx, rdx, 25h ; '%'
0x18002d4ef  add     rcx, rax
0x18002d4f2  mov     rax, rbx
0x18002d4f5  shr     rax, 10h
0x18002d4f9  movzx   eax, al
0x18002d4fc  imul    rdx, rcx, 25h ; '%'
0x18002d500  add     rdx, rax
0x18002d503  mov     rax, rbx
0x18002d506  shr     rax, 18h
0x18002d50a  movzx   eax, al
0x18002d50d  imul    rcx, rdx, 25h ; '%'
0x18002d511  add     rcx, rax
0x18002d514  mov     rax, rbx
0x18002d517  shr     rax, 20h
0x18002d51b  movzx   eax, al
0x18002d51e  imul    rdx, rcx, 25h ; '%'
0x18002d522  add     rdx, rax
0x18002d525  mov     rax, rbx
0x18002d528  shr     rax, 28h
0x18002d52c  movzx   eax, al
0x18002d52f  imul    rcx, rdx, 25h ; '%'
0x18002d533  add     rcx, rax
0x18002d536  mov     rax, rbx
0x18002d539  shr     rax, 30h
0x18002d53d  movzx   eax, al
0x18002d540  imul    rdx, rcx, 25h ; '%'
0x18002d544  add     rdx, rax
0x18002d547  mov     rax, rbx
0x18002d54a  imul    rdx, 25h ; '%'
0x18002d54e  shr     rax, 38h
0x18002d552  add     rdx, rax
0x18002d555  lfence
0x18002d558  movzx   eax, byte ptr [r8+148h]
0x18002d560  imul    rcx, rdx, 25h ; '%'
0x18002d564  add     rcx, rax
0x18002d567  movzx   eax, byte ptr [r8+149h]
0x18002d56f  imul    rdx, rcx, 25h ; '%'
0x18002d573  add     rdx, rax
0x18002d576  movzx   eax, byte ptr [r8+14Ah]
0x18002d57e  imul    rcx, rdx, 25h ; '%'
0x18002d582  add     rcx, rax
0x18002d585  movzx   eax, byte ptr [r8+14Bh]
0x18002d58d  imul    rdx, rcx, 25h ; '%'
0x18002d591  mov     rcx, cs:gWfpGlobal
0x18002d598  lea     r8, [rsp+48h+var_28]
0x18002d59d  add     rdx, rax
0x18002d5a0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002d5a7  cmovz   rdx, rax
0x18002d5ab  mov     rcx, [rcx+140h]
0x18002d5b2  call    cs:__imp_RtlLookupEntryHashTable
0x18002d5b9  nop     dword ptr [rax+rax+00h]
0x18002d5be  test    rax, rax
0x18002d5c1  jz      loc_18002D6CF
0x18002d5c7  mov     rcx, cs:gWfpGlobal
0x18002d5ce  mov     edx, [rcx+148h]
0x18002d5d4  cmp     [rax+18h], edx
0x18002d5d7  jnz     loc_18002D687
0x18002d5dd  cmp     [rax+1Ch], edi
0x18002d5e0  jnz     loc_18002D687
0x18002d5e6  cmp     [rax+20h], rbx
0x18002d5ea  jnz     loc_18002D687
0x18002d5f0  mov     rsi, rax
0x18002d5f3  mov     [rsp+48h+arg_8], rax
0x18002d5f8  xor     ebx, ebx
0x18002d5fa  mov     rcx, [rcx+140h]
0x18002d601  xor     r8d, r8d
0x18002d604  mov     rdx, rsi
0x18002d607  call    cs:__imp_RtlRemoveEntryHashTable
0x18002d60e  nop     dword ptr [rax+rax+00h]
0x18002d613  test    al, al
0x18002d615  jz      loc_18002D72A
0x18002d61b  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18002d620  test    eax, eax
0x18002d622  jnz     short loc_18002D67B
0x18002d624  cmp     cs:gWfpTrackHeapBytes, eax
0x18002d62a  jnz     short loc_18002D6A4
0x18002d62c  mov     rcx, cs:gWfpHeap; hHeap
0x18002d633  mov     r8, rsi; lpMem
0x18002d636  xor     edx, edx; dwFlags
0x18002d638  call    cs:__imp_HeapFree
0x18002d63f  nop     dword ptr [rax+rax+00h]
0x18002d644  mov     rcx, cs:gWfpGlobal
0x18002d64b  add     rcx, 3E8h; lpCriticalSection
0x18002d652  call    cs:__imp_LeaveCriticalSection
0x18002d659  nop     dword ptr [rax+rax+00h]
0x18002d65e  test    rbx, rbx
0x18002d661  jnz     loc_18002D716
0x18002d667  mov     rsi, [rsp+48h+arg_10]
0x18002d66c  mov     rax, rbx
0x18002d66f  mov     rbx, [rsp+48h+arg_0]
0x18002d674  add     rsp, 40h
0x18002d678  pop     rdi
0x18002d679  retn
0x18002d67b  lea     rcx, [rsp+48h+arg_8]
0x18002d680  call    WfpMemFree25B
0x18002d685  jmp     short loc_18002D644
0x18002d687  mov     rcx, [rcx+140h]
0x18002d68e  lea     rdx, [rsp+48h+var_28]
0x18002d693  call    cs:__imp_RtlGetNextEntryHashTable
0x18002d69a  nop     dword ptr [rax+rax+00h]
0x18002d69f  jmp     loc_18002D5BE
0x18002d6a4  test    rsi, rsi
0x18002d6a7  jz      short loc_18002D62C
0x18002d6a9  mov     rcx, cs:gWfpHeap; hHeap
0x18002d6b0  mov     r8, rsi; lpMem
0x18002d6b3  xor     edx, edx; dwFlags
0x18002d6b5  call    cs:__imp_HeapSize
0x18002d6bc  nop     dword ptr [rax+rax+00h]
0x18002d6c1  neg     eax
0x18002d6c3  lock add cs:gWfpHeapBytesAllocated, eax
0x18002d6ca  jmp     loc_18002D62C
0x18002d6cf  mov     r8d, 0C0000001h
0x18002d6d5  lea     rdx, aRtllookupentry; "RtlLookupEntryHashTable"
0x18002d6dc  call    WfpReportSysErrorAsNtStatus
0x18002d6e1  mov     rbx, rax
0x18002d6e4  test    rax, rax
0x18002d6e7  jz      loc_18008C340
0x18002d6ed  lea     rdx, aFindentryfromf; "FindEntryFromFilterHashtable"
0x18002d6f4  mov     rcx, rax
0x18002d6f7  call    WfpReportError
0x18002d6fc  mov     rcx, cs:gWfpGlobal
0x18002d703  add     rcx, 3E8h; lpCriticalSection
0x18002d70a  call    cs:__imp_LeaveCriticalSection
0x18002d711  nop     dword ptr [rax+rax+00h]
0x18002d716  lea     rdx, aRemovefilterfr; "RemoveFilterFromFilterHashtable"
0x18002d71d  mov     rcx, rbx
0x18002d720  call    WfpReportError
0x18002d725  jmp     loc_18002D667
0x18002d72a  mov     r8d, 0C0000001h
0x18002d730  lea     rdx, aRtlremoveentry; "RtlRemoveEntryHashTable"
0x18002d737  call    WfpReportSysErrorAsNtStatus
0x18002d73c  mov     rbx, rax
0x18002d73f  jmp     loc_18002D644
0x18008c340  mov     rcx, cs:gWfpGlobal
0x18008c347  jmp     loc_18002D5FA
```
