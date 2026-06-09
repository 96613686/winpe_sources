# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180009550`
- end: `0x180009612`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800073a8`
- `0x1800086b8`
- `0x1800090c0`

## callees

- `0x180009550`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095e1`

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
0x180009550  push    rbx
0x180009552  push    rbp
0x180009553  push    rsi
0x180009554  push    rdi
0x180009555  sub     rsp, 48h
0x180009559  mov     rbp, [rcx+30h]
0x18000955d  mov     rbx, rdx
0x180009560  movaps  [rsp+68h+var_38], xmm6
0x180009565  mov     rdi, rcx
0x180009568  movups  xmm6, xmmword ptr [rcx+18h]
0x18000956c  movaps  [rsp+68h+var_48], xmm7
0x180009571  movsd   xmm7, qword ptr [rcx+28h]
0x180009576  mov     qword ptr [rcx+30h], 0
0x18000957e  movups  xmm0, xmmword ptr [rdx+18h]
0x180009582  movups  xmmword ptr [rcx+18h], xmm0
0x180009586  movsd   xmm1, qword ptr [rdx+28h]
0x18000958b  movsd   qword ptr [rcx+28h], xmm1
0x180009590  mov     rax, [rdx+30h]
0x180009594  mov     qword ptr [rdx+30h], 0
0x18000959c  mov     rsi, [rcx+30h]
0x1800095a0  mov     [rcx+30h], rax
0x1800095a4  test    rsi, rsi
0x1800095a7  jz      short loc_1800095BD
0x1800095a9  call    cs:__imp_GetProcessHeap
0x1800095af  mov     r8, rsi; lpMem
0x1800095b2  xor     edx, edx; dwFlags
0x1800095b4  mov     rcx, rax; hHeap
0x1800095b7  call    cs:__imp_HeapFree
0x1800095bd  movups  xmmword ptr [rbx+18h], xmm6
0x1800095c1  movsd   qword ptr [rbx+28h], xmm7
0x1800095c6  mov     rsi, [rbx+30h]
0x1800095ca  mov     [rbx+30h], rbp
0x1800095ce  test    rsi, rsi
0x1800095d1  jz      short loc_1800095E7
0x1800095d3  call    cs:__imp_GetProcessHeap
0x1800095d9  mov     r8, rsi; lpMem
0x1800095dc  xor     edx, edx; dwFlags
0x1800095de  mov     rcx, rax; hHeap
0x1800095e1  call    cs:__imp_HeapFree
0x1800095e7  mov     al, [rbx+38h]
0x1800095ea  mov     cl, [rdi+38h]
0x1800095ed  movaps  xmm6, [rsp+68h+var_38]
0x1800095f2  movaps  xmm7, [rsp+68h+var_48]
0x1800095f7  mov     [rdi+38h], al
0x1800095fa  mov     al, [rbx+39h]
0x1800095fd  mov     [rbx+38h], cl
0x180009600  mov     cl, [rdi+39h]
0x180009603  mov     [rdi+39h], al
0x180009606  mov     [rbx+39h], cl
0x180009609  add     rsp, 48h
0x18000960d  pop     rdi
0x18000960e  pop     rsi
0x18000960f  pop     rbp
0x180009610  pop     rbx
0x180009611  retn
```
