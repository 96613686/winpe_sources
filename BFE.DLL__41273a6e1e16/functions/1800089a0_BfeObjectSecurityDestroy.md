# BfeObjectSecurityDestroy

- ea: `0x1800089a0`
- end: `0x180008ad5`
- name: `BfeObjectSecurityDestroy`
- size: `309`
- prototype: ``
- caller_count: `24`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800085b8`
- `0x1800321a0`
- `0x1800321fc`
- `0x180040270`
- `0x180040990`
- `0x180040e5c`
- `0x1800410a0`
- `0x180041a20`
- `0x1800451a0`
- `0x1800590dc`
- `0x18005922c`
- `0x180067d58`
- `0x180067df4`
- `0x18006a534`
- `0x18006b460`
- `0x18006b6f0`
- `0x18006ba58`
- `0x18006be5c`
- `0x18006bf3c`
- `0x18006bf70`
- `0x18006c100`
- `0x18006df70`
- `0x180072d44`
- `0x18007470c`

## callees

- `0x1800089a0`
- `0x180055f04`
- `0x1800560f8`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800089df`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800089df`
- `ntdll!RtlExpandHashTable` at `0x180008a88`
- `ntdll!RtlExpandHashTable` at `0x180008a88`
- `ntdll!RtlContractHashTable` at `0x180008a67`
- `ntdll!RtlContractHashTable` at `0x180008a67`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180008abb`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180008abb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a2c`

## pseudocode

```c
unsigned __int64 __fastcall BfeObjectSecurityDestroy(_QWORD *a1)
{
  _DWORD *v2; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rcx
  unsigned int v7; // esi
  unsigned __int64 result; // rax
  _DWORD *v9; // [rsp+28h] [rbp-10h] BYREF

  v2 = (_DWORD *)(*a1 - 28LL);
  if ( !*a1 )
    v2 = 0;
  v9 = v2;
  if ( v2 )
  {
    if ( v2[6]-- == 1 )
    {
      RtlRemoveEntryHashTable(&qword_1800F5AD0, v2, 0);
      v6 = (unsigned int)dword_1800F5AD8;
      v7 = dword_1800F5AE4;
      if ( dword_1800F5AE4 > (unsigned int)(3 * dword_1800F5AD8) )
      {
        do
        {
          if ( !(unsigned __int8)RtlExpandHashTable(&qword_1800F5AD0) )
            break;
          v6 = (unsigned int)(3 * dword_1800F5AD8);
        }
        while ( v7 > (unsigned int)v6 );
      }
      else if ( dword_1800F5AE4 < (unsigned int)dword_1800F5AD8 )
      {
        while ( (unsigned __int8)RtlContractHashTable(&qword_1800F5AD0) && v7 < dword_1800F5AD8 )
          ;
      }
      if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v6, v4, v5) )
      {
        WfpMemFree25B(&v9);
      }
      else
      {
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v2));
        HeapFree(gWfpHeap, 0, v2);
      }
    }
  }
  result = 0xBADBADFABADBADFAuLL;
  *a1 = 0xBADBADFABADBADFAuLL;
  return result;
}

```

## disassembly

```asm
0x1800089a0  mov     [rsp+arg_10], rbx
0x1800089a5  push    rdi
0x1800089a6  sub     rsp, 30h
0x1800089aa  mov     rax, [rcx]
0x1800089ad  mov     rdi, rcx
0x1800089b0  xor     ecx, ecx
0x1800089b2  test    rax, rax
0x1800089b5  lea     rbx, [rax-1Ch]
0x1800089b9  cmovz   rbx, rcx
0x1800089bd  mov     [rsp+38h+var_10], rbx
0x1800089c2  test    rbx, rbx
0x1800089c5  jz      short loc_180008A38
0x1800089c7  sub     dword ptr [rbx+18h], 1
0x1800089cb  jnz     short loc_180008A38
0x1800089cd  xor     r8d, r8d
0x1800089d0  mov     [rsp+38h+arg_8], rsi
0x1800089d5  mov     rdx, rbx
0x1800089d8  lea     rcx, qword_1800F5AD0
0x1800089df  call    cs:__imp_RtlRemoveEntryHashTable
0x1800089e6  nop     dword ptr [rax+rax+00h]
0x1800089eb  mov     ecx, cs:dword_1800F5AD8
0x1800089f1  mov     esi, cs:dword_1800F5AE4
0x1800089f7  lea     eax, [rcx+rcx*2]
0x1800089fa  cmp     esi, eax
0x1800089fc  ja      loc_180008A81
0x180008a02  cmp     esi, ecx
0x180008a04  jb      short loc_180008A60
0x180008a06  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180008a0b  mov     rsi, [rsp+38h+arg_8]
0x180008a10  test    eax, eax
0x180008a12  jnz     short loc_180008A51
0x180008a14  cmp     cs:gWfpTrackHeapBytes, eax
0x180008a1a  jnz     loc_180008AAF
0x180008a20  mov     rcx, cs:gWfpHeap; hHeap
0x180008a27  mov     r8, rbx; lpMem
0x180008a2a  xor     edx, edx; dwFlags
0x180008a2c  call    cs:__imp_HeapFree
0x180008a33  nop     dword ptr [rax+rax+00h]
0x180008a38  mov     rbx, [rsp+38h+arg_10]
0x180008a3d  mov     rax, 0BADBADFABADBADFAh
0x180008a47  mov     [rdi], rax
0x180008a4a  add     rsp, 30h
0x180008a4e  pop     rdi
0x180008a4f  retn
0x180008a51  lea     rcx, [rsp+38h+var_10]
0x180008a56  call    WfpMemFree25B
0x180008a5b  jmp     short loc_180008A38
0x180008a60  lea     rcx, qword_1800F5AD0
0x180008a67  call    cs:__imp_RtlContractHashTable
0x180008a6e  nop     dword ptr [rax+rax+00h]
0x180008a73  test    al, al
0x180008a75  jz      short loc_180008A06
0x180008a77  cmp     esi, cs:dword_1800F5AD8
0x180008a7d  jb      short loc_180008A60
0x180008a7f  jmp     short loc_180008A06
0x180008a81  lea     rcx, qword_1800F5AD0
0x180008a88  call    cs:__imp_RtlExpandHashTable
0x180008a8f  nop     dword ptr [rax+rax+00h]
0x180008a94  test    al, al
0x180008a96  jz      loc_180008A06
0x180008a9c  mov     eax, cs:dword_1800F5AD8
0x180008aa2  lea     ecx, [rax+rax*2]
0x180008aa5  cmp     esi, ecx
0x180008aa7  jbe     loc_180008A06
0x180008aad  jmp     short loc_180008A81
0x180008aaf  mov     rcx, cs:gWfpHeap; hHeap
0x180008ab6  mov     r8, rbx; lpMem
0x180008ab9  xor     edx, edx; dwFlags
0x180008abb  call    cs:__imp_HeapSize
0x180008ac2  nop     dword ptr [rax+rax+00h]
0x180008ac7  neg     eax
0x180008ac9  lock add cs:gWfpHeapBytesAllocated, eax
0x180008ad0  jmp     loc_180008A20
```
