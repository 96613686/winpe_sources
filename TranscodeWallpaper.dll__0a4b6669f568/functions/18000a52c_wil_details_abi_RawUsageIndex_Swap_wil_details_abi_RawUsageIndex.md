# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000a52c`
- end: `0x18000a5ee`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007744`
- `0x180009174`
- `0x180009c34`

## callees

- `0x18000a52c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a585`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a585`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a593`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a593`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5bd`

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
0x18000a52c  push    rbx
0x18000a52e  push    rbp
0x18000a52f  push    rsi
0x18000a530  push    rdi
0x18000a531  sub     rsp, 48h
0x18000a535  mov     rbp, [rcx+30h]
0x18000a539  mov     rbx, rdx
0x18000a53c  movaps  [rsp+68h+var_38], xmm6
0x18000a541  mov     rdi, rcx
0x18000a544  movups  xmm6, xmmword ptr [rcx+18h]
0x18000a548  movaps  [rsp+68h+var_48], xmm7
0x18000a54d  movsd   xmm7, qword ptr [rcx+28h]
0x18000a552  mov     qword ptr [rcx+30h], 0
0x18000a55a  movups  xmm0, xmmword ptr [rdx+18h]
0x18000a55e  movups  xmmword ptr [rcx+18h], xmm0
0x18000a562  movsd   xmm1, qword ptr [rdx+28h]
0x18000a567  movsd   qword ptr [rcx+28h], xmm1
0x18000a56c  mov     rax, [rdx+30h]
0x18000a570  mov     qword ptr [rdx+30h], 0
0x18000a578  mov     rsi, [rcx+30h]
0x18000a57c  mov     [rcx+30h], rax
0x18000a580  test    rsi, rsi
0x18000a583  jz      short loc_18000A599
0x18000a585  call    cs:__imp_GetProcessHeap
0x18000a58b  mov     r8, rsi; lpMem
0x18000a58e  xor     edx, edx; dwFlags
0x18000a590  mov     rcx, rax; hHeap
0x18000a593  call    cs:__imp_HeapFree
0x18000a599  movups  xmmword ptr [rbx+18h], xmm6
0x18000a59d  movsd   qword ptr [rbx+28h], xmm7
0x18000a5a2  mov     rsi, [rbx+30h]
0x18000a5a6  mov     [rbx+30h], rbp
0x18000a5aa  test    rsi, rsi
0x18000a5ad  jz      short loc_18000A5C3
0x18000a5af  call    cs:__imp_GetProcessHeap
0x18000a5b5  mov     r8, rsi; lpMem
0x18000a5b8  xor     edx, edx; dwFlags
0x18000a5ba  mov     rcx, rax; hHeap
0x18000a5bd  call    cs:__imp_HeapFree
0x18000a5c3  mov     al, [rbx+38h]
0x18000a5c6  mov     cl, [rdi+38h]
0x18000a5c9  movaps  xmm6, [rsp+68h+var_38]
0x18000a5ce  movaps  xmm7, [rsp+68h+var_48]
0x18000a5d3  mov     [rdi+38h], al
0x18000a5d6  mov     al, [rbx+39h]
0x18000a5d9  mov     [rbx+38h], cl
0x18000a5dc  mov     cl, [rdi+39h]
0x18000a5df  mov     [rdi+39h], al
0x18000a5e2  mov     [rbx+39h], cl
0x18000a5e5  add     rsp, 48h
0x18000a5e9  pop     rdi
0x18000a5ea  pop     rsi
0x18000a5eb  pop     rbp
0x18000a5ec  pop     rbx
0x18000a5ed  retn
```
