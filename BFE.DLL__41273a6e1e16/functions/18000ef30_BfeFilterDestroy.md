# BfeFilterDestroy

- ea: `0x18000ef30`
- end: `0x18000f343`
- name: `BfeFilterDestroy`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006ed0`

## callees

- `0x1800087f0`
- `0x18000ef30`
- `0x18000f34c`
- `0x18000f8c8`
- `0x180020000`
- `0x180020168`
- `0x180035634`
- `0x18003567c`
- `0x180055f04`
- `0x1800560f8`
- `0x18005aa60`
- `0x18008ad60`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000f2e7`
- `ntdll!RtlEqualSid` at `0x18000f2e7`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000f1a4`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000f1ce`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000f326`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000f1a4`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000f1ce`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000f326`
- `ntdll!RtlLookupEntryHashTable` at `0x18000f137`
- `ntdll!RtlLookupEntryHashTable` at `0x18000f137`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000f307`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000f307`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f22f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f25f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f28f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f22f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f25f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f28f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f011`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f054`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f011`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f054`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f094`

## pseudocode

```c
int __fastcall BfeFilterDestroy(__int64 *a1)
{
  int v2; // ecx
  _DWORD *v3; // rdi
  unsigned __int16 *v4; // rsi
  _DWORD *i; // rax
  __int64 v7; // rbp
  int result; // eax
  __int64 *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rsi
  void *v12; // r14
  __int64 v13; // rax
  __int64 j; // rax
  __int64 v15; // rbp
  __int64 *v16; // rax
  __int64 **v17; // rcx
  unsigned int v18; // eax
  const void *v19; // r8
  const void *v20; // r8
  BOOL v21; // esi
  __int128 v22; // [rsp+28h] [rbp-40h] BYREF
  __int64 v23; // [rsp+38h] [rbp-30h]

  if ( *((_DWORD *)a1 + 8) )
    --dword_1800F5EB0;
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
  v21 = memcmp_0((const void *)(*a1 + 64), &FWPM_LAYER_NAME_RESOLUTION_CACHE_V4, 0x10u) == 0;
  if ( !memcmp_0((const void *)(v7 + 64), &FWPM_LAYER_NAME_RESOLUTION_CACHE_V6, 0x10u) || v21 )
  {
    v9 = a1 + 5;
    if ( a1[5] || a1[6] )
    {
      v10 = *(_QWORD *)(v7 + 120);
      v11 = 0;
      v22 = 0;
      v12 = *(void **)(v10 + 32);
      v23 = 0;
      v13 = BfeComputeSidSignature(v12);
      if ( !v13 )
        v13 = -1;
      for ( j = RtlLookupEntryHashTable(qword_1800F5EB8, v13, &v22); ; j = RtlGetNextEntryHashTable(
                                                                             qword_1800F5EB8,
                                                                             &v22) )
      {
        v15 = j;
        if ( !j )
          break;
        if ( RtlEqualSid(*(PSID *)(j + 24), v12) )
        {
          v11 = v15;
          break;
        }
      }
      v16 = (__int64 *)*v9;
      if ( *(__int64 **)(*v9 + 8) != v9 || (v17 = (__int64 **)a1[6], *v17 != v9) )
        __fastfail(3u);
      *v17 = v16;
      v16[1] = (__int64)v17;
      v18 = *(_DWORD *)(v11 + 48);
      if ( v18 <= 1 )
      {
        RtlRemoveEntryHashTable(qword_1800F5EB8, v11, 0);
        WfpRestructureHashtable(qword_1800F5EB8);
        BfeFreeSidEntry(v11);
      }
      else
      {
        *(_DWORD *)(v11 + 48) = v18 - 1;
      }
      if ( *((_DWORD *)a1 + 22) )
      {
        RtlRemoveEntryHashTable(qword_1800F5EE8, a1 + 8, 0);
        WfpRestructureHashtable(qword_1800F5EE8);
      }
      if ( *((_DWORD *)a1 + 30) )
      {
        RtlRemoveEntryHashTable(qword_1800F5F18, a1 + 12, 0);
        WfpRestructureHashtable(qword_1800F5F18);
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
  if ( a1[2] )
    BfeDestroyInner_FWPS_FILTER3();
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    WfpMemFree25B(a1 + 2);
  }
  else
  {
    if ( gWfpTrackHeapBytes )
    {
      v19 = (const void *)a1[2];
      if ( v19 )
        _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v19));
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
    v20 = (const void *)a1[7];
    if ( v20 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v20));
  }
  result = HeapFree(gWfpHeap, 0, (LPVOID)a1[7]);
  a1[7] = 0xBADBADFABADBADFAuLL;
  return result;
}

```

## disassembly

```asm
0x18000ef30  mov     [rsp+arg_10], rbx
0x18000ef35  push    rbp
0x18000ef36  push    rsi
0x18000ef37  push    rdi
0x18000ef38  sub     rsp, 50h
0x18000ef3c  mov     rax, cs:__security_cookie
0x18000ef43  xor     rax, rsp
0x18000ef46  mov     [rsp+68h+var_28], rax
0x18000ef4b  cmp     dword ptr [rcx+20h], 0
0x18000ef4f  mov     rbx, rcx
0x18000ef52  jz      short loc_18000EF5A
0x18000ef54  dec     cs:dword_1800F5EB0
0x18000ef5a  mov     ecx, [rcx+1Ch]
0x18000ef5d  cmp     ecx, 0FFFFFFFFh
0x18000ef60  jz      short loc_18000EF8C
0x18000ef62  mov     rax, [rbx+8]
0x18000ef66  xor     edi, edi
0x18000ef68  mov     rsi, [rax+10h]
0x18000ef6c  mov     rax, [rsi+8]
0x18000ef70  test    rax, rax
0x18000ef73  jz      short loc_18000EF82
0x18000ef75  cmp     [rax+14h], ecx
0x18000ef78  jz      short loc_18000EF7F
0x18000ef7a  mov     rax, [rax]
0x18000ef7d  jmp     short loc_18000EF70
0x18000ef7f  mov     rdi, rax
0x18000ef82  sub     dword ptr [rdi+10h], 1
0x18000ef86  jz      loc_18000F1F0
0x18000ef8c  mov     rbp, [rbx]
0x18000ef8f  lea     rdx, FWPM_LAYER_NAME_RESOLUTION_CACHE_V4; Buf2
0x18000ef96  mov     r8d, 10h; Size
0x18000ef9c  xor     esi, esi
0x18000ef9e  lea     rcx, [rbp+40h]; Buf1
0x18000efa2  call    memcmp_0
0x18000efa7  test    eax, eax
0x18000efa9  jz      loc_18000F2C6
0x18000efaf  mov     r8d, 10h; Size
0x18000efb5  lea     rdx, FWPM_LAYER_NAME_RESOLUTION_CACHE_V6; Buf2
0x18000efbc  lea     rcx, [rbp+40h]; Buf1
0x18000efc0  call    memcmp_0
0x18000efc5  test    eax, eax
0x18000efc7  jz      loc_18000F0E5
0x18000efcd  test    esi, esi
0x18000efcf  jnz     loc_18000F0E5
0x18000efd5  mov     rcx, [rbx]
0x18000efd8  test    rcx, rcx
0x18000efdb  jz      short loc_18000EFE2
0x18000efdd  call    BfeDestroyInner_FWPM_FILTER0
0x18000efe2  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000efe7  mov     rsi, 0BADBADFABADBADFAh
0x18000eff1  test    eax, eax
0x18000eff3  jnz     loc_18000F0C2
0x18000eff9  cmp     cs:gWfpTrackHeapBytes, eax
0x18000efff  jnz     loc_18000F21A
0x18000f005  mov     r8, [rbx]; lpMem
0x18000f008  xor     edx, edx; dwFlags
0x18000f00a  mov     rcx, cs:gWfpHeap; hHeap
0x18000f011  call    cs:__imp_HeapFree
0x18000f018  nop     dword ptr [rax+rax+00h]
0x18000f01d  mov     [rbx], rsi
0x18000f020  mov     rcx, [rbx+10h]
0x18000f024  test    rcx, rcx
0x18000f027  jz      short loc_18000F02E
0x18000f029  call    BfeDestroyInner_FWPS_FILTER3
0x18000f02e  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000f033  test    eax, eax
0x18000f035  jnz     loc_18000F0CF
0x18000f03b  cmp     cs:gWfpTrackHeapBytes, eax
0x18000f041  jnz     loc_18000F249
0x18000f047  mov     r8, [rbx+10h]; lpMem
0x18000f04b  xor     edx, edx; dwFlags
0x18000f04d  mov     rcx, cs:gWfpHeap; hHeap
0x18000f054  call    cs:__imp_HeapFree
0x18000f05b  nop     dword ptr [rax+rax+00h]
0x18000f060  mov     [rbx+10h], rsi
0x18000f064  mov     rcx, [rbx+38h]
0x18000f068  test    rcx, rcx
0x18000f06b  jz      short loc_18000F072
0x18000f06d  call    BfeDestroyInner_FWPM_FILTER0
0x18000f072  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000f077  test    eax, eax
0x18000f079  jnz     short loc_18000F0DA
0x18000f07b  cmp     cs:gWfpTrackHeapBytes, eax
0x18000f081  jnz     loc_18000F279
0x18000f087  mov     r8, [rbx+38h]; lpMem
0x18000f08b  xor     edx, edx; dwFlags
0x18000f08d  mov     rcx, cs:gWfpHeap; hHeap
0x18000f094  call    cs:__imp_HeapFree
0x18000f09b  nop     dword ptr [rax+rax+00h]
0x18000f0a0  mov     [rbx+38h], rsi
0x18000f0a4  mov     rcx, [rsp+68h+var_28]
0x18000f0a9  xor     rcx, rsp; StackCookie
0x18000f0ac  call    __security_check_cookie
0x18000f0b1  mov     rbx, [rsp+68h+arg_10]
0x18000f0b9  add     rsp, 50h
0x18000f0bd  pop     rdi
0x18000f0be  pop     rsi
0x18000f0bf  pop     rbp
0x18000f0c0  retn
0x18000f0c2  mov     rcx, rbx
0x18000f0c5  call    WfpMemFree25B
0x18000f0ca  jmp     loc_18000F020
0x18000f0cf  lea     rcx, [rbx+10h]
0x18000f0d3  call    WfpMemFree25B
0x18000f0d8  jmp     short loc_18000F064
0x18000f0da  lea     rcx, [rbx+38h]
0x18000f0de  call    WfpMemFree25B
0x18000f0e3  jmp     short loc_18000F0A4
0x18000f0e5  cmp     qword ptr [rbx+28h], 0
0x18000f0ea  lea     rdi, [rbx+28h]
0x18000f0ee  jz      loc_18000F2D0
0x18000f0f4  mov     rax, [rbp+78h]
0x18000f0f8  xorps   xmm0, xmm0
0x18000f0fb  mov     [rsp+68h+arg_8], r14
0x18000f100  xor     esi, esi
0x18000f102  movups  [rsp+68h+var_40], xmm0
0x18000f107  mov     r14, [rax+20h]
0x18000f10b  xor     eax, eax
0x18000f10d  mov     rcx, r14
0x18000f110  mov     [rsp+68h+var_30], rax
0x18000f115  call    BfeComputeSidSignature
0x18000f11a  test    rax, rax
0x18000f11d  lea     r8, [rsp+68h+var_40]
0x18000f122  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f129  cmovz   rax, rcx
0x18000f12d  lea     rcx, qword_1800F5EB8
0x18000f134  mov     rdx, rax
0x18000f137  call    cs:__imp_RtlLookupEntryHashTable
0x18000f13e  nop     dword ptr [rax+rax+00h]
0x18000f143  mov     rbp, rax
0x18000f146  test    rax, rax
0x18000f149  jnz     loc_18000F2E0
0x18000f14f  mov     rax, [rdi]
0x18000f152  mov     r14, [rsp+68h+arg_8]
0x18000f157  cmp     [rax+8], rdi
0x18000f15b  jnz     loc_18000F213
0x18000f161  mov     rcx, [rdi+8]
0x18000f165  cmp     [rcx], rdi
0x18000f168  jnz     loc_18000F213
0x18000f16e  mov     [rcx], rax
0x18000f171  mov     [rax+8], rcx
0x18000f175  mov     eax, [rsi+30h]
0x18000f178  cmp     eax, 1
0x18000f17b  jbe     short loc_18000F1C1
0x18000f17d  dec     eax
0x18000f17f  mov     [rsi+30h], eax
0x18000f182  cmp     dword ptr [rbx+58h], 0
0x18000f186  jnz     loc_18000F318
0x18000f18c  cmp     dword ptr [rbx+78h], 0
0x18000f190  jz      loc_18000EFD5
0x18000f196  lea     rdx, [rbx+60h]
0x18000f19a  xor     r8d, r8d
0x18000f19d  lea     rcx, qword_1800F5F18
0x18000f1a4  call    cs:__imp_RtlRemoveEntryHashTable
0x18000f1ab  nop     dword ptr [rax+rax+00h]
0x18000f1b0  lea     rcx, qword_1800F5F18
0x18000f1b7  call    WfpRestructureHashtable
0x18000f1bc  jmp     loc_18000EFD5
0x18000f1c1  xor     r8d, r8d
0x18000f1c4  lea     rcx, qword_1800F5EB8
0x18000f1cb  mov     rdx, rsi
0x18000f1ce  call    cs:__imp_RtlRemoveEntryHashTable
0x18000f1d5  nop     dword ptr [rax+rax+00h]
0x18000f1da  lea     rcx, qword_1800F5EB8
0x18000f1e1  call    WfpRestructureHashtable
0x18000f1e6  mov     rcx, rsi
0x18000f1e9  call    BfeFreeSidEntry
0x18000f1ee  jmp     short loc_18000F182
0x18000f1f0  mov     edx, [rdi+18h]
0x18000f1f3  cmp     edx, 0FFFFFFFFh
0x18000f1f6  jnz     loc_18000F2A9
0x18000f1fc  mov     edx, [rdi+14h]
0x18000f1ff  movzx   ecx, word ptr [rsi]
0x18000f202  call    DeleteIndexFromLayer
0x18000f207  mov     dword ptr [rdi+14h], 0FFFFFFFFh
0x18000f20e  jmp     loc_18000EF8C
0x18000f213  mov     ecx, 3
0x18000f218  int     29h; Win8: RtlFailFast(ecx)
0x18000f21a  mov     r8, [rbx]; lpMem
0x18000f21d  test    r8, r8
0x18000f220  jz      loc_18000F005
0x18000f226  mov     rcx, cs:gWfpHeap; hHeap
0x18000f22d  xor     edx, edx; dwFlags
0x18000f22f  call    cs:__imp_HeapSize
0x18000f236  nop     dword ptr [rax+rax+00h]
0x18000f23b  neg     eax
0x18000f23d  lock add cs:gWfpHeapBytesAllocated, eax
0x18000f244  jmp     loc_18000F005
0x18000f249  mov     r8, [rbx+10h]; lpMem
0x18000f24d  test    r8, r8
0x18000f250  jz      loc_18000F047
0x18000f256  mov     rcx, cs:gWfpHeap; hHeap
0x18000f25d  xor     edx, edx; dwFlags
0x18000f25f  call    cs:__imp_HeapSize
0x18000f266  nop     dword ptr [rax+rax+00h]
0x18000f26b  neg     eax
0x18000f26d  lock add cs:gWfpHeapBytesAllocated, eax
0x18000f274  jmp     loc_18000F047
0x18000f279  mov     r8, [rbx+38h]; lpMem
0x18000f27d  test    r8, r8
0x18000f280  jz      loc_18000F087
0x18000f286  mov     rcx, cs:gWfpHeap; hHeap
0x18000f28d  xor     edx, edx; dwFlags
0x18000f28f  call    cs:__imp_HeapSize
0x18000f296  nop     dword ptr [rax+rax+00h]
0x18000f29b  neg     eax
0x18000f29d  lock add cs:gWfpHeapBytesAllocated, eax
0x18000f2a4  jmp     loc_18000F087
0x18000f2a9  movzx   ecx, word ptr [rsi]
0x18000f2ac  call    BfeDriverDeleteIndex
0x18000f2b1  test    rax, rax
0x18000f2b4  jnz     loc_18000F1FC
0x18000f2ba  mov     dword ptr [rdi+18h], 0FFFFFFFFh
0x18000f2c1  jmp     loc_18000F1FC
0x18000f2c6  mov     esi, 1
0x18000f2cb  jmp     loc_18000EFAF
0x18000f2d0  cmp     qword ptr [rbx+30h], 0
0x18000f2d5  jz      loc_18000EFD5
0x18000f2db  jmp     loc_18000F0F4
0x18000f2e0  mov     rcx, [rbp+18h]; Sid1
0x18000f2e4  mov     rdx, r14; Sid2
0x18000f2e7  call    cs:__imp_RtlEqualSid
0x18000f2ee  nop     dword ptr [rax+rax+00h]
0x18000f2f3  test    al, al
0x18000f2f5  jnz     loc_18008B8E6
0x18000f2fb  lea     rdx, [rsp+68h+var_40]
0x18000f300  lea     rcx, qword_1800F5EB8
0x18000f307  call    cs:__imp_RtlGetNextEntryHashTable
0x18000f30e  nop     dword ptr [rax+rax+00h]
0x18000f313  jmp     loc_18000F143
0x18000f318  lea     rdx, [rbx+40h]
0x18000f31c  xor     r8d, r8d
0x18000f31f  lea     rcx, qword_1800F5EE8
0x18000f326  call    cs:__imp_RtlRemoveEntryHashTable
0x18000f32d  nop     dword ptr [rax+rax+00h]
0x18000f332  lea     rcx, qword_1800F5EE8
0x18000f339  call    WfpRestructureHashtable
0x18000f33e  jmp     loc_18000F18C
0x18008b8e6  mov     rsi, rbp
0x18008b8e9  jmp     loc_18000F14F
```
