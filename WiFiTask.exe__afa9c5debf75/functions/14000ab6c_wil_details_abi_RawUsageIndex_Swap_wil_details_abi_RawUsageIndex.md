# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000ab6c`
- end: `0x14000ac2e`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037d0`
- `0x140008830`
- `0x140009340`

## callees

- `0x14000ab6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000abd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000abfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000abd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000abfd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000abc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000abef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000abc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000abef`

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
0x14000ab6c  push    rbx
0x14000ab6e  push    rbp
0x14000ab6f  push    rsi
0x14000ab70  push    rdi
0x14000ab71  sub     rsp, 48h
0x14000ab75  mov     rbp, [rcx+30h]
0x14000ab79  mov     rbx, rdx
0x14000ab7c  movaps  [rsp+68h+var_38], xmm6
0x14000ab81  mov     rdi, rcx
0x14000ab84  movups  xmm6, xmmword ptr [rcx+18h]
0x14000ab88  movaps  [rsp+68h+var_48], xmm7
0x14000ab8d  movsd   xmm7, qword ptr [rcx+28h]
0x14000ab92  mov     qword ptr [rcx+30h], 0
0x14000ab9a  movups  xmm0, xmmword ptr [rdx+18h]
0x14000ab9e  movups  xmmword ptr [rcx+18h], xmm0
0x14000aba2  movsd   xmm1, qword ptr [rdx+28h]
0x14000aba7  movsd   qword ptr [rcx+28h], xmm1
0x14000abac  mov     rax, [rdx+30h]
0x14000abb0  mov     qword ptr [rdx+30h], 0
0x14000abb8  mov     rsi, [rcx+30h]
0x14000abbc  mov     [rcx+30h], rax
0x14000abc0  test    rsi, rsi
0x14000abc3  jz      short loc_14000ABD9
0x14000abc5  call    cs:__imp_GetProcessHeap
0x14000abcb  mov     r8, rsi; lpMem
0x14000abce  xor     edx, edx; dwFlags
0x14000abd0  mov     rcx, rax; hHeap
0x14000abd3  call    cs:__imp_HeapFree
0x14000abd9  movups  xmmword ptr [rbx+18h], xmm6
0x14000abdd  movsd   qword ptr [rbx+28h], xmm7
0x14000abe2  mov     rsi, [rbx+30h]
0x14000abe6  mov     [rbx+30h], rbp
0x14000abea  test    rsi, rsi
0x14000abed  jz      short loc_14000AC03
0x14000abef  call    cs:__imp_GetProcessHeap
0x14000abf5  mov     r8, rsi; lpMem
0x14000abf8  xor     edx, edx; dwFlags
0x14000abfa  mov     rcx, rax; hHeap
0x14000abfd  call    cs:__imp_HeapFree
0x14000ac03  mov     al, [rbx+38h]
0x14000ac06  mov     cl, [rdi+38h]
0x14000ac09  movaps  xmm6, [rsp+68h+var_38]
0x14000ac0e  movaps  xmm7, [rsp+68h+var_48]
0x14000ac13  mov     [rdi+38h], al
0x14000ac16  mov     al, [rbx+39h]
0x14000ac19  mov     [rbx+38h], cl
0x14000ac1c  mov     cl, [rdi+39h]
0x14000ac1f  mov     [rdi+39h], al
0x14000ac22  mov     [rbx+39h], cl
0x14000ac25  add     rsp, 48h
0x14000ac29  pop     rdi
0x14000ac2a  pop     rsi
0x14000ac2b  pop     rbp
0x14000ac2c  pop     rbx
0x14000ac2d  retn
```
