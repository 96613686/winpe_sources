# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000c754`
- end: `0x14000c816`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140008920`
- `0x14000b1e8`
- `0x14000bcf8`

## callees

- `0x14000c754`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c7ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c7d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c7ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c7d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c7bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c7e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c7bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c7e5`

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
0x14000c754  push    rbx
0x14000c756  push    rbp
0x14000c757  push    rsi
0x14000c758  push    rdi
0x14000c759  sub     rsp, 48h
0x14000c75d  mov     rbp, [rcx+30h]
0x14000c761  mov     rbx, rdx
0x14000c764  movaps  [rsp+68h+var_38], xmm6
0x14000c769  mov     rdi, rcx
0x14000c76c  movups  xmm6, xmmword ptr [rcx+18h]
0x14000c770  movaps  [rsp+68h+var_48], xmm7
0x14000c775  movsd   xmm7, qword ptr [rcx+28h]
0x14000c77a  mov     qword ptr [rcx+30h], 0
0x14000c782  movups  xmm0, xmmword ptr [rdx+18h]
0x14000c786  movups  xmmword ptr [rcx+18h], xmm0
0x14000c78a  movsd   xmm1, qword ptr [rdx+28h]
0x14000c78f  movsd   qword ptr [rcx+28h], xmm1
0x14000c794  mov     rax, [rdx+30h]
0x14000c798  mov     qword ptr [rdx+30h], 0
0x14000c7a0  mov     rsi, [rcx+30h]
0x14000c7a4  mov     [rcx+30h], rax
0x14000c7a8  test    rsi, rsi
0x14000c7ab  jz      short loc_14000C7C1
0x14000c7ad  call    cs:__imp_GetProcessHeap
0x14000c7b3  mov     r8, rsi; lpMem
0x14000c7b6  xor     edx, edx; dwFlags
0x14000c7b8  mov     rcx, rax; hHeap
0x14000c7bb  call    cs:__imp_HeapFree
0x14000c7c1  movups  xmmword ptr [rbx+18h], xmm6
0x14000c7c5  movsd   qword ptr [rbx+28h], xmm7
0x14000c7ca  mov     rsi, [rbx+30h]
0x14000c7ce  mov     [rbx+30h], rbp
0x14000c7d2  test    rsi, rsi
0x14000c7d5  jz      short loc_14000C7EB
0x14000c7d7  call    cs:__imp_GetProcessHeap
0x14000c7dd  mov     r8, rsi; lpMem
0x14000c7e0  xor     edx, edx; dwFlags
0x14000c7e2  mov     rcx, rax; hHeap
0x14000c7e5  call    cs:__imp_HeapFree
0x14000c7eb  mov     al, [rbx+38h]
0x14000c7ee  mov     cl, [rdi+38h]
0x14000c7f1  movaps  xmm6, [rsp+68h+var_38]
0x14000c7f6  movaps  xmm7, [rsp+68h+var_48]
0x14000c7fb  mov     [rdi+38h], al
0x14000c7fe  mov     al, [rbx+39h]
0x14000c801  mov     [rbx+38h], cl
0x14000c804  mov     cl, [rdi+39h]
0x14000c807  mov     [rdi+39h], al
0x14000c80a  mov     [rbx+39h], cl
0x14000c80d  add     rsp, 48h
0x14000c811  pop     rdi
0x14000c812  pop     rsi
0x14000c813  pop     rbp
0x14000c814  pop     rbx
0x14000c815  retn
```
