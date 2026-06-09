# BfeFilterDestroy

- ea: `0x18000e680`
- end: `0x18000ea4a`
- name: `BfeFilterDestroy`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180008240`
- `0x18000e680`
- `0x18000ea50`
- `0x18000ef6c`
- `0x180024d34`
- `0x180024e9c`
- `0x180036920`
- `0x180036964`
- `0x1800540ec`
- `0x1800542bc`
- `0x180058b30`
- `0x180087dc0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000ea00`
- `ntdll!RtlEqualSid` at `0x18000ea00`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000e8db`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000e8ff`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000ea33`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000e8db`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000e8ff`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000ea33`
- `ntdll!RtlLookupEntryHashTable` at `0x18000e874`
- `ntdll!RtlLookupEntryHashTable` at `0x18000e874`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000ea1a`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000ea1a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e95a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e984`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e9ae`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e95a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e984`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e9ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e761`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e79e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e761`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e79e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7d8`

## pseudocode

```c
int __fastcall BfeFilterDestroy(__int64 *a1)
{
  int v2; // ecx
  _DWORD *v3; // rdi
  unsigned __int16 *v4; // rsi
  _DWORD *i; // rax
  __int64 v7; // rbp
  __int64 v8; // rcx
  int result; // eax
  __int64 *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rsi
  void *v13; // r14
  __int64 v14; // rax
  __int64 j; // rax
  __int64 v16; // rbp
  __int64 *v17; // rax
  __int64 **v18; // rcx
  unsigned int v19; // eax
  const void *v20; // r8
  const void *v21; // r8
  BOOL v22; // esi
  __int128 v23; // [rsp+28h] [rbp-40h] BYREF
  __int64 v24; // [rsp+38h] [rbp-30h]

  if ( *((_DWORD *)a1 + 8) )
    --LODWORD(qword_1800F2668[261]);
  v2 = *((_DWORD *)a1 + 7);
  if ( v2 != -1 )
  {
    v3 = 0;
    v4 = *(unsigned __int16 **)(a1[1] + 16);
    for ( i = (_DWORD *)*((_QWORD *)v4 + 1); i; i = *(_DWORD **)i )
    {
      if ( i[5] == v2 )
      {
        v3 = i;
        break;
      }
    }
    if ( v3[4]-- == 1 )
    {
      if ( v3[6] != -1 && !BfeDriverDeleteIndex(*v4) )
        v3[6] = -1;
      DeleteIndexFromLayer(*v4, (unsigned int)v3[5]);
      v3[5] = -1;
    }
  }
  v7 = *a1;
  v22 = memcmp_0((const void *)(*a1 + 64), &FWPM_LAYER_NAME_RESOLUTION_CACHE_V4, 0x10u) == 0;
  if ( !memcmp_0((const void *)(v7 + 64), &FWPM_LAYER_NAME_RESOLUTION_CACHE_V6, 0x10u) || v22 )
  {
    v10 = a1 + 5;
    if ( a1[5] || a1[6] )
    {
      v11 = *(_QWORD *)(v7 + 120);
      v12 = 0;
      v23 = 0;
      v13 = *(void **)(v11 + 32);
      v24 = 0;
      v14 = BfeComputeSidSignature(v13);
      if ( !v14 )
        v14 = -1;
      for ( j = RtlLookupEntryHashTable(&qword_1800F2668[262], v14, &v23);
            ;
            j = RtlGetNextEntryHashTable(&qword_1800F2668[262], &v23) )
      {
        v16 = j;
        if ( !j )
          break;
        if ( RtlEqualSid(*(PSID *)(j + 24), v13) )
        {
          v12 = v16;
          break;
        }
      }
      v17 = (__int64 *)*v10;
      if ( *(__int64 **)(*v10 + 8) != v10 || (v18 = (__int64 **)a1[6], *v18 != v10) )
        __fastfail(3u);
      *v18 = v17;
      v17[1] = (__int64)v18;
      v19 = *(_DWORD *)(v12 + 48);
      if ( v19 <= 1 )
      {
        RtlRemoveEntryHashTable(&qword_1800F2668[262], v12, 0);
        WfpRestructureHashtable(&qword_1800F2668[262]);
        BfeFreeSidEntry(v12);
      }
      else
      {
        *(_DWORD *)(v12 + 48) = v19 - 1;
      }
      if ( *((_DWORD *)a1 + 22) )
      {
        RtlRemoveEntryHashTable(&qword_1800F2668[268], a1 + 8, 0);
        WfpRestructureHashtable(&qword_1800F2668[268]);
      }
      if ( *((_DWORD *)a1 + 30) )
      {
        RtlRemoveEntryHashTable(&qword_1800F2668[274], a1 + 12, 0);
        WfpRestructureHashtable(&qword_1800F2668[274]);
      }
    }
  }
  if ( *a1 )
    BfeDestroyInner_FWPM_FILTER0();
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    WfpMemFree25B(a1);
  }
  else
  {
    if ( gWfpTrackHeapBytes && *a1 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, (LPCVOID)*a1));
    HeapFree(gWfpHeap, 0, (LPVOID)*a1);
    *a1 = 0xBADBADFABADBADFAuLL;
  }
  v8 = a1[2];
  if ( v8 )
    BfeDestroyInner_FWPS_FILTER3(v8);
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    WfpMemFree25B(a1 + 2);
  }
  else
  {
    if ( gWfpTrackHeapBytes )
    {
      v20 = (const void *)a1[2];
      if ( v20 )
        _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v20));
    }
    HeapFree(gWfpHeap, 0, (LPVOID)a1[2]);
    a1[2] = 0xBADBADFABADBADFAuLL;
  }
  if ( a1[7] )
    BfeDestroyInner_FWPM_FILTER0();
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
    return WfpMemFree25B(a1 + 7);
  if ( gWfpTrackHeapBytes )
  {
    v21 = (const void *)a1[7];
    if ( v21 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v21));
  }
  result = HeapFree(gWfpHeap, 0, (LPVOID)a1[7]);
  a1[7] = 0xBADBADFABADBADFAuLL;
  return result;
}

```

## disassembly

```asm
0x18000e680  mov     [rsp+arg_10], rbx
0x18000e685  push    rbp
0x18000e686  push    rsi
0x18000e687  push    rdi
0x18000e688  sub     rsp, 50h
0x18000e68c  mov     rax, cs:__security_cookie
0x18000e693  xor     rax, rsp
0x18000e696  mov     [rsp+68h+var_28], rax
0x18000e69b  cmp     dword ptr [rcx+20h], 0
0x18000e69f  mov     rbx, rcx
0x18000e6a2  jz      short loc_18000E6AA
0x18000e6a4  dec     dword ptr cs:qword_1800F2668+828h
0x18000e6aa  mov     ecx, [rcx+1Ch]
0x18000e6ad  cmp     ecx, 0FFFFFFFFh
0x18000e6b0  jz      short loc_18000E6DC
0x18000e6b2  mov     rax, [rbx+8]
0x18000e6b6  xor     edi, edi
0x18000e6b8  mov     rsi, [rax+10h]
0x18000e6bc  mov     rax, [rsi+8]
0x18000e6c0  test    rax, rax
0x18000e6c3  jz      short loc_18000E6D2
0x18000e6c5  cmp     [rax+14h], ecx
0x18000e6c8  jz      short loc_18000E6CF
0x18000e6ca  mov     rax, [rax]
0x18000e6cd  jmp     short loc_18000E6C0
0x18000e6cf  mov     rdi, rax
0x18000e6d2  sub     dword ptr [rdi+10h], 1
0x18000e6d6  jz      loc_18000E91B
0x18000e6dc  mov     rbp, [rbx]
0x18000e6df  lea     rdx, FWPM_LAYER_NAME_RESOLUTION_CACHE_V4; Buf2
0x18000e6e6  mov     r8d, 10h; Size
0x18000e6ec  xor     esi, esi
0x18000e6ee  lea     rcx, [rbp+40h]; Buf1
0x18000e6f2  call    memcmp_0
0x18000e6f7  test    eax, eax
0x18000e6f9  jz      loc_18000E9DF
0x18000e6ff  mov     r8d, 10h; Size
0x18000e705  lea     rdx, FWPM_LAYER_NAME_RESOLUTION_CACHE_V6; Buf2
0x18000e70c  lea     rcx, [rbp+40h]; Buf1
0x18000e710  call    memcmp_0
0x18000e715  test    eax, eax
0x18000e717  jz      loc_18000E822
0x18000e71d  test    esi, esi
0x18000e71f  jnz     loc_18000E822
0x18000e725  mov     rcx, [rbx]
0x18000e728  test    rcx, rcx
0x18000e72b  jz      short loc_18000E732
0x18000e72d  call    BfeDestroyInner_FWPM_FILTER0
0x18000e732  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000e737  mov     rsi, 0BADBADFABADBADFAh
0x18000e741  test    eax, eax
0x18000e743  jnz     loc_18000E7FF
0x18000e749  cmp     cs:gWfpTrackHeapBytes, eax
0x18000e74f  jnz     loc_18000E945
0x18000e755  mov     r8, [rbx]; lpMem
0x18000e758  xor     edx, edx; dwFlags
0x18000e75a  mov     rcx, cs:gWfpHeap; hHeap
0x18000e761  call    cs:__imp_HeapFree
0x18000e767  mov     [rbx], rsi
0x18000e76a  mov     rcx, [rbx+10h]
0x18000e76e  test    rcx, rcx
0x18000e771  jz      short loc_18000E778
0x18000e773  call    BfeDestroyInner_FWPS_FILTER3
0x18000e778  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000e77d  test    eax, eax
0x18000e77f  jnz     loc_18000E80C
0x18000e785  cmp     cs:gWfpTrackHeapBytes, eax
0x18000e78b  jnz     loc_18000E96E
0x18000e791  mov     r8, [rbx+10h]; lpMem
0x18000e795  xor     edx, edx; dwFlags
0x18000e797  mov     rcx, cs:gWfpHeap; hHeap
0x18000e79e  call    cs:__imp_HeapFree
0x18000e7a4  mov     [rbx+10h], rsi
0x18000e7a8  mov     rcx, [rbx+38h]
0x18000e7ac  test    rcx, rcx
0x18000e7af  jz      short loc_18000E7B6
0x18000e7b1  call    BfeDestroyInner_FWPM_FILTER0
0x18000e7b6  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000e7bb  test    eax, eax
0x18000e7bd  jnz     short loc_18000E817
0x18000e7bf  cmp     cs:gWfpTrackHeapBytes, eax
0x18000e7c5  jnz     loc_18000E998
0x18000e7cb  mov     r8, [rbx+38h]; lpMem
0x18000e7cf  xor     edx, edx; dwFlags
0x18000e7d1  mov     rcx, cs:gWfpHeap; hHeap
0x18000e7d8  call    cs:__imp_HeapFree
0x18000e7de  mov     [rbx+38h], rsi
0x18000e7e2  mov     rcx, [rsp+68h+var_28]
0x18000e7e7  xor     rcx, rsp; StackCookie
0x18000e7ea  call    __security_check_cookie
0x18000e7ef  mov     rbx, [rsp+68h+arg_10]
0x18000e7f7  add     rsp, 50h
0x18000e7fb  pop     rdi
0x18000e7fc  pop     rsi
0x18000e7fd  pop     rbp
0x18000e7fe  retn
0x18000e7ff  mov     rcx, rbx
0x18000e802  call    WfpMemFree25B
0x18000e807  jmp     loc_18000E76A
0x18000e80c  lea     rcx, [rbx+10h]
0x18000e810  call    WfpMemFree25B
0x18000e815  jmp     short loc_18000E7A8
0x18000e817  lea     rcx, [rbx+38h]
0x18000e81b  call    WfpMemFree25B
0x18000e820  jmp     short loc_18000E7E2
0x18000e822  cmp     qword ptr [rbx+28h], 0
0x18000e827  lea     rdi, [rbx+28h]
0x18000e82b  jz      loc_18000E9E9
0x18000e831  mov     rax, [rbp+78h]
0x18000e835  xorps   xmm0, xmm0
0x18000e838  mov     [rsp+68h+arg_8], r14
0x18000e83d  xor     esi, esi
0x18000e83f  movups  [rsp+68h+var_40], xmm0
0x18000e844  mov     r14, [rax+20h]
0x18000e848  xor     eax, eax
0x18000e84a  mov     rcx, r14
0x18000e84d  mov     [rsp+68h+var_30], rax
0x18000e852  call    BfeComputeSidSignature
0x18000e857  test    rax, rax
0x18000e85a  lea     r8, [rsp+68h+var_40]
0x18000e85f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e866  cmovz   rax, rcx
0x18000e86a  lea     rcx, qword_1800F2668+830h
0x18000e871  mov     rdx, rax
0x18000e874  call    cs:__imp_RtlLookupEntryHashTable
0x18000e87a  mov     rbp, rax
0x18000e87d  test    rax, rax
0x18000e880  jnz     loc_18000E9F9
0x18000e886  mov     rax, [rdi]
0x18000e889  mov     r14, [rsp+68h+arg_8]
0x18000e88e  cmp     [rax+8], rdi
0x18000e892  jnz     loc_18000E93E
0x18000e898  mov     rcx, [rdi+8]
0x18000e89c  cmp     [rcx], rdi
0x18000e89f  jnz     loc_18000E93E
0x18000e8a5  mov     [rcx], rax
0x18000e8a8  mov     [rax+8], rcx
0x18000e8ac  mov     eax, [rsi+30h]
0x18000e8af  cmp     eax, 1
0x18000e8b2  jbe     short loc_18000E8F2
0x18000e8b4  dec     eax
0x18000e8b6  mov     [rsi+30h], eax
0x18000e8b9  cmp     dword ptr [rbx+58h], 0
0x18000e8bd  jnz     loc_18000EA25
0x18000e8c3  cmp     dword ptr [rbx+78h], 0
0x18000e8c7  jz      loc_18000E725
0x18000e8cd  lea     rdx, [rbx+60h]
0x18000e8d1  xor     r8d, r8d
0x18000e8d4  lea     rcx, qword_1800F2668+890h
0x18000e8db  call    cs:__imp_RtlRemoveEntryHashTable
0x18000e8e1  lea     rcx, qword_1800F2668+890h
0x18000e8e8  call    WfpRestructureHashtable
0x18000e8ed  jmp     loc_18000E725
0x18000e8f2  xor     r8d, r8d
0x18000e8f5  lea     rcx, qword_1800F2668+830h
0x18000e8fc  mov     rdx, rsi
0x18000e8ff  call    cs:__imp_RtlRemoveEntryHashTable
0x18000e905  lea     rcx, qword_1800F2668+830h
0x18000e90c  call    WfpRestructureHashtable
0x18000e911  mov     rcx, rsi
0x18000e914  call    BfeFreeSidEntry
0x18000e919  jmp     short loc_18000E8B9
0x18000e91b  mov     edx, [rdi+18h]
0x18000e91e  cmp     edx, 0FFFFFFFFh
0x18000e921  jnz     loc_18000E9C2
0x18000e927  mov     edx, [rdi+14h]
0x18000e92a  movzx   ecx, word ptr [rsi]
0x18000e92d  call    DeleteIndexFromLayer
0x18000e932  mov     dword ptr [rdi+14h], 0FFFFFFFFh
0x18000e939  jmp     loc_18000E6DC
0x18000e93e  mov     ecx, 3
0x18000e943  int     29h; Win8: RtlFailFast(ecx)
0x18000e945  mov     r8, [rbx]; lpMem
0x18000e948  test    r8, r8
0x18000e94b  jz      loc_18000E755
0x18000e951  mov     rcx, cs:gWfpHeap; hHeap
0x18000e958  xor     edx, edx; dwFlags
0x18000e95a  call    cs:__imp_HeapSize
0x18000e960  neg     eax
0x18000e962  lock add cs:gWfpHeapBytesAllocated, eax
0x18000e969  jmp     loc_18000E755
0x18000e96e  mov     r8, [rbx+10h]; lpMem
0x18000e972  test    r8, r8
0x18000e975  jz      loc_18000E791
0x18000e97b  mov     rcx, cs:gWfpHeap; hHeap
0x18000e982  xor     edx, edx; dwFlags
0x18000e984  call    cs:__imp_HeapSize
0x18000e98a  neg     eax
0x18000e98c  lock add cs:gWfpHeapBytesAllocated, eax
0x18000e993  jmp     loc_18000E791
0x18000e998  mov     r8, [rbx+38h]; lpMem
0x18000e99c  test    r8, r8
0x18000e99f  jz      loc_18000E7CB
0x18000e9a5  mov     rcx, cs:gWfpHeap; hHeap
0x18000e9ac  xor     edx, edx; dwFlags
0x18000e9ae  call    cs:__imp_HeapSize
0x18000e9b4  neg     eax
0x18000e9b6  lock add cs:gWfpHeapBytesAllocated, eax
0x18000e9bd  jmp     loc_18000E7CB
0x18000e9c2  movzx   ecx, word ptr [rsi]
0x18000e9c5  call    BfeDriverDeleteIndex
0x18000e9ca  test    rax, rax
0x18000e9cd  jnz     loc_18000E927
0x18000e9d3  mov     dword ptr [rdi+18h], 0FFFFFFFFh
0x18000e9da  jmp     loc_18000E927
0x18000e9df  mov     esi, 1
0x18000e9e4  jmp     loc_18000E6FF
0x18000e9e9  cmp     qword ptr [rbx+30h], 0
0x18000e9ee  jz      loc_18000E725
0x18000e9f4  jmp     loc_18000E831
0x18000e9f9  mov     rcx, [rbp+18h]; Sid1
0x18000e9fd  mov     rdx, r14; Sid2
0x18000ea00  call    cs:__imp_RtlEqualSid
0x18000ea06  test    al, al
0x18000ea08  jnz     loc_180088A04
0x18000ea0e  lea     rdx, [rsp+68h+var_40]
0x18000ea13  lea     rcx, qword_1800F2668+830h
0x18000ea1a  call    cs:__imp_RtlGetNextEntryHashTable
0x18000ea20  jmp     loc_18000E87A
0x18000ea25  lea     rdx, [rbx+40h]
0x18000ea29  xor     r8d, r8d
0x18000ea2c  lea     rcx, qword_1800F2668+860h
0x18000ea33  call    cs:__imp_RtlRemoveEntryHashTable
0x18000ea39  lea     rcx, qword_1800F2668+860h
0x18000ea40  call    WfpRestructureHashtable
0x18000ea45  jmp     loc_18000E8C3
0x180088a04  mov     rsi, rbp
0x180088a07  jmp     loc_18000E886
```
