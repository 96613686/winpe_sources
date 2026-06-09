# RemoveFilterFromFilterHashtable

- ea: `0x18002bad0`
- end: `0x18002bd73`
- name: `RemoveFilterFromFilterHashtable`
- size: `675`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180027214`
- `0x1800364ac`
- `0x18007cf10`

## callees

- `0x180012b54`
- `0x180018b74`
- `0x18002bad0`
- `0x1800540ec`
- `0x1800542bc`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18002bc5b`
- `ntdll!RtlRemoveEntryHashTable` at `0x18002bc5b`
- `ntdll!RtlLookupEntryHashTable` at `0x18002bc0c`
- `ntdll!RtlLookupEntryHashTable` at `0x18002bc0c`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002bcd4`
- `ntdll!RtlGetNextEntryHashTable` at `0x18002bcd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002baf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002baf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bc9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bd3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bc9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bd3f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002bcf0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18002bcf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bc86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bc86`

## string_xrefs

- `0x18002bd5f`: `RtlRemoveEntryHashTable`
- `0x18002bd45`: `RemoveFilterFromFilterHashtable`

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
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v15; // rax
  __int128 v16; // [rsp+20h] [rbp-28h] BYREF
  __int64 v17; // [rsp+30h] [rbp-18h]
  __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v2 = a1;
  EnterCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 1000LL));
  v4 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  _mm_lfence();
  _mm_lfence();
  v5 = (unsigned __int8 *)MEMORY[0x1800EF368][58];
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
  for ( i = RtlLookupEntryHashTable(*(_QWORD *)(MEMORY[0x1800EF368][58] + 320LL), v6, &v16);
        i;
        i = RtlGetNextEntryHashTable(*(_QWORD *)(MEMORY[0x1800EF368][58] + 320LL), &v16) )
  {
    v9 = MEMORY[0x1800EF368][58];
    if ( *(_DWORD *)(i + 24) == *(_DWORD *)(MEMORY[0x1800EF368][58] + 328LL)
      && *(_DWORD *)(i + 28) == v2
      && *(_QWORD *)(i + 32) == a2 )
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
    LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 1000LL));
    goto LABEL_21;
  }
  v9 = MEMORY[0x1800EF368][58];
LABEL_9:
  if ( (unsigned __int8)RtlRemoveEntryHashTable(*(_QWORD *)(v9 + 320), v4, 0) )
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
  LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 1000LL));
  if ( v10 )
LABEL_21:
    WfpReportError(v10, "RemoveFilterFromFilterHashtable");
  return v10;
}

```

## disassembly

```asm
0x18002bad0  mov     [rsp+arg_0], rbx
0x18002bad5  mov     [rsp+arg_10], rsi
0x18002bada  push    rdi
0x18002badb  sub     rsp, 40h
0x18002badf  movzx   edi, cx
0x18002bae2  mov     rbx, rdx
0x18002bae5  mov     rcx, cs:1800EF538h
0x18002baec  add     rcx, 3E8h; lpCriticalSection
0x18002baf3  call    cs:__imp_EnterCriticalSection
0x18002baf9  xor     eax, eax
0x18002bafb  xor     esi, esi
0x18002bafd  mov     [rsp+48h+var_18], rax
0x18002bb02  xorps   xmm0, xmm0
0x18002bb05  movzx   eax, di
0x18002bb08  mov     [rsp+48h+arg_8], rsi
0x18002bb0d  shr     ax, 8
0x18002bb11  movzx   ecx, ax
0x18002bb14  movzx   eax, dil
0x18002bb18  movups  [rsp+48h+var_28], xmm0
0x18002bb1d  lfence
0x18002bb20  imul    rax, 25h ; '%'
0x18002bb24  add     rcx, rax
0x18002bb27  lfence
0x18002bb2a  mov     r8, cs:1800EF538h
0x18002bb31  imul    rdx, rcx, 25h ; '%'
0x18002bb35  movzx   eax, bl
0x18002bb38  add     rdx, rax
0x18002bb3b  mov     rax, rbx
0x18002bb3e  shr     rax, 8
0x18002bb42  movzx   eax, al
0x18002bb45  imul    rcx, rdx, 25h ; '%'
0x18002bb49  add     rcx, rax
0x18002bb4c  mov     rax, rbx
0x18002bb4f  shr     rax, 10h
0x18002bb53  movzx   eax, al
0x18002bb56  imul    rdx, rcx, 25h ; '%'
0x18002bb5a  add     rdx, rax
0x18002bb5d  mov     rax, rbx
0x18002bb60  shr     rax, 18h
0x18002bb64  movzx   eax, al
0x18002bb67  imul    rcx, rdx, 25h ; '%'
0x18002bb6b  add     rcx, rax
0x18002bb6e  mov     rax, rbx
0x18002bb71  shr     rax, 20h
0x18002bb75  movzx   eax, al
0x18002bb78  imul    rdx, rcx, 25h ; '%'
0x18002bb7c  add     rdx, rax
0x18002bb7f  mov     rax, rbx
0x18002bb82  shr     rax, 28h
0x18002bb86  movzx   eax, al
0x18002bb89  imul    rcx, rdx, 25h ; '%'
0x18002bb8d  add     rcx, rax
0x18002bb90  mov     rax, rbx
0x18002bb93  shr     rax, 30h
0x18002bb97  movzx   eax, al
0x18002bb9a  imul    rdx, rcx, 25h ; '%'
0x18002bb9e  add     rdx, rax
0x18002bba1  mov     rax, rbx
0x18002bba4  imul    rdx, 25h ; '%'
0x18002bba8  shr     rax, 38h
0x18002bbac  add     rdx, rax
0x18002bbaf  lfence
0x18002bbb2  movzx   eax, byte ptr [r8+148h]
0x18002bbba  imul    rcx, rdx, 25h ; '%'
0x18002bbbe  add     rcx, rax
0x18002bbc1  movzx   eax, byte ptr [r8+149h]
0x18002bbc9  imul    rdx, rcx, 25h ; '%'
0x18002bbcd  add     rdx, rax
0x18002bbd0  movzx   eax, byte ptr [r8+14Ah]
0x18002bbd8  imul    rcx, rdx, 25h ; '%'
0x18002bbdc  add     rcx, rax
0x18002bbdf  movzx   eax, byte ptr [r8+14Bh]
0x18002bbe7  imul    rdx, rcx, 25h ; '%'
0x18002bbeb  mov     rcx, cs:1800EF538h
0x18002bbf2  lea     r8, [rsp+48h+var_28]
0x18002bbf7  add     rdx, rax
0x18002bbfa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002bc01  cmovz   rdx, rax
0x18002bc05  mov     rcx, [rcx+140h]
0x18002bc0c  call    cs:__imp_RtlLookupEntryHashTable
0x18002bc12  test    rax, rax
0x18002bc15  jz      loc_18002BD04
0x18002bc1b  mov     rcx, cs:1800EF538h
0x18002bc22  mov     edx, [rcx+148h]
0x18002bc28  cmp     [rax+18h], edx
0x18002bc2b  jnz     loc_18002BCC8
0x18002bc31  cmp     [rax+1Ch], edi
0x18002bc34  jnz     loc_18002BCC8
0x18002bc3a  cmp     [rax+20h], rbx
0x18002bc3e  jnz     loc_18002BCC8
0x18002bc44  mov     rsi, rax
0x18002bc47  mov     [rsp+48h+arg_8], rax
0x18002bc4c  xor     ebx, ebx
0x18002bc4e  mov     rcx, [rcx+140h]
0x18002bc55  xor     r8d, r8d
0x18002bc58  mov     rdx, rsi
0x18002bc5b  call    cs:__imp_RtlRemoveEntryHashTable
0x18002bc61  test    al, al
0x18002bc63  jz      loc_18002BD59
0x18002bc69  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18002bc6e  test    eax, eax
0x18002bc70  jnz     short loc_18002BCBC
0x18002bc72  cmp     cs:gWfpTrackHeapBytes, eax
0x18002bc78  jnz     short loc_18002BCDF
0x18002bc7a  mov     rcx, cs:gWfpHeap; hHeap
0x18002bc81  mov     r8, rsi; lpMem
0x18002bc84  xor     edx, edx; dwFlags
0x18002bc86  call    cs:__imp_HeapFree
0x18002bc8c  mov     rcx, cs:1800EF538h
0x18002bc93  add     rcx, 3E8h; lpCriticalSection
0x18002bc9a  call    cs:__imp_LeaveCriticalSection
0x18002bca0  test    rbx, rbx
0x18002bca3  jnz     loc_18002BD45
0x18002bca9  mov     rsi, [rsp+48h+arg_10]
0x18002bcae  mov     rax, rbx
0x18002bcb1  mov     rbx, [rsp+48h+arg_0]
0x18002bcb6  add     rsp, 40h
0x18002bcba  pop     rdi
0x18002bcbb  retn
0x18002bcbc  lea     rcx, [rsp+48h+arg_8]
0x18002bcc1  call    WfpMemFree25B
0x18002bcc6  jmp     short loc_18002BC8C
0x18002bcc8  mov     rcx, [rcx+140h]
0x18002bccf  lea     rdx, [rsp+48h+var_28]
0x18002bcd4  call    cs:__imp_RtlGetNextEntryHashTable
0x18002bcda  jmp     loc_18002BC12
0x18002bcdf  test    rsi, rsi
0x18002bce2  jz      short loc_18002BC7A
0x18002bce4  mov     rcx, cs:gWfpHeap; hHeap
0x18002bceb  mov     r8, rsi; lpMem
0x18002bcee  xor     edx, edx; dwFlags
0x18002bcf0  call    cs:__imp_HeapSize
0x18002bcf6  neg     eax
0x18002bcf8  lock add cs:gWfpHeapBytesAllocated, eax
0x18002bcff  jmp     loc_18002BC7A
0x18002bd04  mov     r8d, 0C0000001h
0x18002bd0a  lea     rdx, aRtllookupentry; "RtlLookupEntryHashTable"
0x18002bd11  call    WfpReportSysErrorAsNtStatus
0x18002bd16  mov     rbx, rax
0x18002bd19  test    rax, rax
0x18002bd1c  jz      loc_1800893B6
0x18002bd22  lea     rdx, aFindentryfromf; "FindEntryFromFilterHashtable"
0x18002bd29  mov     rcx, rax
0x18002bd2c  call    WfpReportError
0x18002bd31  mov     rcx, cs:1800EF538h
0x18002bd38  add     rcx, 3E8h; lpCriticalSection
0x18002bd3f  call    cs:__imp_LeaveCriticalSection
0x18002bd45  lea     rdx, aRemovefilterfr; "RemoveFilterFromFilterHashtable"
0x18002bd4c  mov     rcx, rbx
0x18002bd4f  call    WfpReportError
0x18002bd54  jmp     loc_18002BCA9
0x18002bd59  mov     r8d, 0C0000001h
0x18002bd5f  lea     rdx, aRtlremoveentry; "RtlRemoveEntryHashTable"
0x18002bd66  call    WfpReportSysErrorAsNtStatus
0x18002bd6b  mov     rbx, rax
0x18002bd6e  jmp     loc_18002BC8C
0x1800893b6  mov     rcx, cs:1800EF538h
0x1800893bd  jmp     loc_18002BC4E
```
