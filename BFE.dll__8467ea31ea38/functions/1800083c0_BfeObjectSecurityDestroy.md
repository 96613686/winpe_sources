# BfeObjectSecurityDestroy

- ea: `0x1800083c0`
- end: `0x1800084d8`
- name: `BfeObjectSecurityDestroy`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `24`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008028`
- `0x180030890`
- `0x1800308e8`
- `0x18003efe0`
- `0x18003f6f0`
- `0x18003fb08`
- `0x18003fdd0`
- `0x1800412c0`
- `0x1800434e0`
- `0x1800573b8`
- `0x180057508`
- `0x180065890`
- `0x18006591c`
- `0x180067fac`
- `0x180068ec8`
- `0x18006914c`
- `0x1800694a4`
- `0x180069888`
- `0x180069968`
- `0x18006999c`
- `0x180069b1c`
- `0x18006b948`
- `0x180070604`
- `0x180071e9c`

## callees

- `0x1800083c0`
- `0x1800540ec`
- `0x1800542bc`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800083ff`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800083ff`
- `ntdll!RtlExpandHashTable` at `0x180008497`
- `ntdll!RtlExpandHashTable` at `0x180008497`
- `ntdll!RtlContractHashTable` at `0x180008477`
- `ntdll!RtlContractHashTable` at `0x180008477`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800084c4`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800084c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008442`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008442`

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
      RtlRemoveEntryHashTable(&qword_1800F2AB0, v2, 0);
      v6 = (unsigned int)dword_1800F2AB8;
      v7 = dword_1800F2AC4;
      if ( dword_1800F2AC4 > (unsigned int)(3 * dword_1800F2AB8) )
      {
        do
        {
          if ( !(unsigned __int8)RtlExpandHashTable(&qword_1800F2AB0) )
            break;
          v6 = (unsigned int)(3 * dword_1800F2AB8);
        }
        while ( v7 > (unsigned int)v6 );
      }
      else if ( dword_1800F2AC4 < (unsigned int)dword_1800F2AB8 )
      {
        while ( (unsigned __int8)RtlContractHashTable(&qword_1800F2AB0) && v7 < dword_1800F2AB8 )
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
0x1800083c0  mov     [rsp+arg_10], rbx
0x1800083c5  push    rdi
0x1800083c6  sub     rsp, 30h
0x1800083ca  mov     rax, [rcx]
0x1800083cd  mov     rdi, rcx
0x1800083d0  xor     ecx, ecx
0x1800083d2  test    rax, rax
0x1800083d5  lea     rbx, [rax-1Ch]
0x1800083d9  cmovz   rbx, rcx
0x1800083dd  mov     [rsp+38h+var_10], rbx
0x1800083e2  test    rbx, rbx
0x1800083e5  jz      short loc_180008448
0x1800083e7  sub     dword ptr [rbx+18h], 1
0x1800083eb  jnz     short loc_180008448
0x1800083ed  xor     r8d, r8d
0x1800083f0  mov     [rsp+38h+arg_8], rsi
0x1800083f5  mov     rdx, rbx
0x1800083f8  lea     rcx, qword_1800F2AB0
0x1800083ff  call    cs:__imp_RtlRemoveEntryHashTable
0x180008405  mov     ecx, cs:dword_1800F2AB8
0x18000840b  mov     esi, cs:dword_1800F2AC4
0x180008411  lea     eax, [rcx+rcx*2]
0x180008414  cmp     esi, eax
0x180008416  ja      short loc_180008490
0x180008418  cmp     esi, ecx
0x18000841a  jb      short loc_180008470
0x18000841c  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180008421  mov     rsi, [rsp+38h+arg_8]
0x180008426  test    eax, eax
0x180008428  jnz     short loc_180008460
0x18000842a  cmp     cs:gWfpTrackHeapBytes, eax
0x180008430  jnz     loc_1800084B8
0x180008436  mov     rcx, cs:gWfpHeap; hHeap
0x18000843d  mov     r8, rbx; lpMem
0x180008440  xor     edx, edx; dwFlags
0x180008442  call    cs:__imp_HeapFree
0x180008448  mov     rbx, [rsp+38h+arg_10]
0x18000844d  mov     rax, 0BADBADFABADBADFAh
0x180008457  mov     [rdi], rax
0x18000845a  add     rsp, 30h
0x18000845e  pop     rdi
0x18000845f  retn
0x180008460  lea     rcx, [rsp+38h+var_10]
0x180008465  call    WfpMemFree25B
0x18000846a  jmp     short loc_180008448
0x180008470  lea     rcx, qword_1800F2AB0
0x180008477  call    cs:__imp_RtlContractHashTable
0x18000847d  test    al, al
0x18000847f  jz      short loc_18000841C
0x180008481  cmp     esi, cs:dword_1800F2AB8
0x180008487  jb      short loc_180008470
0x180008489  jmp     short loc_18000841C
0x180008490  lea     rcx, qword_1800F2AB0
0x180008497  call    cs:__imp_RtlExpandHashTable
0x18000849d  test    al, al
0x18000849f  jz      loc_18000841C
0x1800084a5  mov     eax, cs:dword_1800F2AB8
0x1800084ab  lea     ecx, [rax+rax*2]
0x1800084ae  cmp     esi, ecx
0x1800084b0  jbe     loc_18000841C
0x1800084b6  jmp     short loc_180008490
0x1800084b8  mov     rcx, cs:gWfpHeap; hHeap
0x1800084bf  mov     r8, rbx; lpMem
0x1800084c2  xor     edx, edx; dwFlags
0x1800084c4  call    cs:__imp_HeapSize
0x1800084ca  neg     eax
0x1800084cc  lock add cs:gWfpHeapBytesAllocated, eax
0x1800084d3  jmp     loc_180008436
```
