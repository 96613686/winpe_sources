# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000a228`
- end: `0x18000a2ea`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a7c`
- `0x1800087f0`
- `0x180009300`

## callees

- `0x18000a228`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a28f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a28f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a281`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a281`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ab`

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
0x18000a228  push    rbx
0x18000a22a  push    rbp
0x18000a22b  push    rsi
0x18000a22c  push    rdi
0x18000a22d  sub     rsp, 48h
0x18000a231  mov     rbp, [rcx+30h]
0x18000a235  mov     rbx, rdx
0x18000a238  movaps  [rsp+68h+var_38], xmm6
0x18000a23d  mov     rdi, rcx
0x18000a240  movups  xmm6, xmmword ptr [rcx+18h]
0x18000a244  movaps  [rsp+68h+var_48], xmm7
0x18000a249  movsd   xmm7, qword ptr [rcx+28h]
0x18000a24e  mov     qword ptr [rcx+30h], 0
0x18000a256  movups  xmm0, xmmword ptr [rdx+18h]
0x18000a25a  movups  xmmword ptr [rcx+18h], xmm0
0x18000a25e  movsd   xmm1, qword ptr [rdx+28h]
0x18000a263  movsd   qword ptr [rcx+28h], xmm1
0x18000a268  mov     rax, [rdx+30h]
0x18000a26c  mov     qword ptr [rdx+30h], 0
0x18000a274  mov     rsi, [rcx+30h]
0x18000a278  mov     [rcx+30h], rax
0x18000a27c  test    rsi, rsi
0x18000a27f  jz      short loc_18000A295
0x18000a281  call    cs:__imp_GetProcessHeap
0x18000a287  mov     r8, rsi; lpMem
0x18000a28a  xor     edx, edx; dwFlags
0x18000a28c  mov     rcx, rax; hHeap
0x18000a28f  call    cs:__imp_HeapFree
0x18000a295  movups  xmmword ptr [rbx+18h], xmm6
0x18000a299  movsd   qword ptr [rbx+28h], xmm7
0x18000a29e  mov     rsi, [rbx+30h]
0x18000a2a2  mov     [rbx+30h], rbp
0x18000a2a6  test    rsi, rsi
0x18000a2a9  jz      short loc_18000A2BF
0x18000a2ab  call    cs:__imp_GetProcessHeap
0x18000a2b1  mov     r8, rsi; lpMem
0x18000a2b4  xor     edx, edx; dwFlags
0x18000a2b6  mov     rcx, rax; hHeap
0x18000a2b9  call    cs:__imp_HeapFree
0x18000a2bf  mov     al, [rbx+38h]
0x18000a2c2  mov     cl, [rdi+38h]
0x18000a2c5  movaps  xmm6, [rsp+68h+var_38]
0x18000a2ca  movaps  xmm7, [rsp+68h+var_48]
0x18000a2cf  mov     [rdi+38h], al
0x18000a2d2  mov     al, [rbx+39h]
0x18000a2d5  mov     [rbx+38h], cl
0x18000a2d8  mov     cl, [rdi+39h]
0x18000a2db  mov     [rdi+39h], al
0x18000a2de  mov     [rbx+39h], cl
0x18000a2e1  add     rsp, 48h
0x18000a2e5  pop     rdi
0x18000a2e6  pop     rsi
0x18000a2e7  pop     rbp
0x18000a2e8  pop     rbx
0x18000a2e9  retn
```
