# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180009400`
- end: `0x1800094c2`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800054e4`
- `0x18000807c`
- `0x180008b30`

## callees

- `0x180009400`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009467`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009491`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009467`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009491`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009483`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009483`

## pseudocode

```c
void __fastcall wil::details_abi::RawUsageIndex::Swap(
        wil::details_abi::RawUsageIndex *this,
        struct wil::details_abi::RawUsageIndex *a2)
{
  __int64 v2; // rbp
  __int128 v5; // xmm6
  __int64 v6; // xmm7_8
  __int64 v7; // rax
  void *v8; // rsi
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  char v12; // cl
  char v13; // al
  char v14; // cl

  v2 = *((_QWORD *)this + 6);
  v5 = *(_OWORD *)((char *)this + 24);
  v6 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = 0;
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)a2 + 24);
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 5);
  v7 = *((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = 0;
  v8 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v7;
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  *(_OWORD *)((char *)a2 + 24) = v5;
  *((_QWORD *)a2 + 5) = v6;
  v10 = (void *)*((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = v2;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  v12 = *((_BYTE *)this + 56);
  *((_BYTE *)this + 56) = *((_BYTE *)a2 + 56);
  v13 = *((_BYTE *)a2 + 57);
  *((_BYTE *)a2 + 56) = v12;
  v14 = *((_BYTE *)this + 57);
  *((_BYTE *)this + 57) = v13;
  *((_BYTE *)a2 + 57) = v14;
}

```

## disassembly

```asm
0x180009400  push    rbx
0x180009402  push    rbp
0x180009403  push    rsi
0x180009404  push    rdi
0x180009405  sub     rsp, 48h
0x180009409  mov     rbp, [rcx+30h]
0x18000940d  mov     rbx, rdx
0x180009410  movaps  [rsp+68h+var_38], xmm6
0x180009415  mov     rdi, rcx
0x180009418  movups  xmm6, xmmword ptr [rcx+18h]
0x18000941c  movaps  [rsp+68h+var_48], xmm7
0x180009421  movsd   xmm7, qword ptr [rcx+28h]
0x180009426  mov     qword ptr [rcx+30h], 0
0x18000942e  movups  xmm0, xmmword ptr [rdx+18h]
0x180009432  movups  xmmword ptr [rcx+18h], xmm0
0x180009436  movsd   xmm1, qword ptr [rdx+28h]
0x18000943b  movsd   qword ptr [rcx+28h], xmm1
0x180009440  mov     rax, [rdx+30h]
0x180009444  mov     qword ptr [rdx+30h], 0
0x18000944c  mov     rsi, [rcx+30h]
0x180009450  mov     [rcx+30h], rax
0x180009454  test    rsi, rsi
0x180009457  jz      short loc_18000946D
0x180009459  call    cs:__imp_GetProcessHeap
0x18000945f  mov     r8, rsi; lpMem
0x180009462  xor     edx, edx; dwFlags
0x180009464  mov     rcx, rax; hHeap
0x180009467  call    cs:__imp_HeapFree
0x18000946d  movups  xmmword ptr [rbx+18h], xmm6
0x180009471  movsd   qword ptr [rbx+28h], xmm7
0x180009476  mov     rsi, [rbx+30h]
0x18000947a  mov     [rbx+30h], rbp
0x18000947e  test    rsi, rsi
0x180009481  jz      short loc_180009497
0x180009483  call    cs:__imp_GetProcessHeap
0x180009489  mov     r8, rsi; lpMem
0x18000948c  xor     edx, edx; dwFlags
0x18000948e  mov     rcx, rax; hHeap
0x180009491  call    cs:__imp_HeapFree
0x180009497  mov     al, [rbx+38h]
0x18000949a  mov     cl, [rdi+38h]
0x18000949d  movaps  xmm6, [rsp+68h+var_38]
0x1800094a2  movaps  xmm7, [rsp+68h+var_48]
0x1800094a7  mov     [rdi+38h], al
0x1800094aa  mov     al, [rbx+39h]
0x1800094ad  mov     [rbx+38h], cl
0x1800094b0  mov     cl, [rdi+39h]
0x1800094b3  mov     [rdi+39h], al
0x1800094b6  mov     [rbx+39h], cl
0x1800094b9  add     rsp, 48h
0x1800094bd  pop     rdi
0x1800094be  pop     rsi
0x1800094bf  pop     rbp
0x1800094c0  pop     rbx
0x1800094c1  retn
```
