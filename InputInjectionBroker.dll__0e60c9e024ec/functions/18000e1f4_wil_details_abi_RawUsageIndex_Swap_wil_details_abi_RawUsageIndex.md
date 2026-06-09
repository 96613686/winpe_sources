# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000e1f4`
- end: `0x18000e2b6`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009944`
- `0x18000d220`
- `0x18000dbd0`

## callees

- `0x18000e1f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e24d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e24d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e277`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e25b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e25b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e285`

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
0x18000e1f4  push    rbx
0x18000e1f6  push    rbp
0x18000e1f7  push    rsi
0x18000e1f8  push    rdi
0x18000e1f9  sub     rsp, 48h
0x18000e1fd  mov     rbp, [rcx+30h]
0x18000e201  mov     rbx, rdx
0x18000e204  movaps  [rsp+68h+var_38], xmm6
0x18000e209  mov     rdi, rcx
0x18000e20c  movups  xmm6, xmmword ptr [rcx+18h]
0x18000e210  movaps  [rsp+68h+var_48], xmm7
0x18000e215  movsd   xmm7, qword ptr [rcx+28h]
0x18000e21a  mov     qword ptr [rcx+30h], 0
0x18000e222  movups  xmm0, xmmword ptr [rdx+18h]
0x18000e226  movups  xmmword ptr [rcx+18h], xmm0
0x18000e22a  movsd   xmm1, qword ptr [rdx+28h]
0x18000e22f  movsd   qword ptr [rcx+28h], xmm1
0x18000e234  mov     rax, [rdx+30h]
0x18000e238  mov     qword ptr [rdx+30h], 0
0x18000e240  mov     rsi, [rcx+30h]
0x18000e244  mov     [rcx+30h], rax
0x18000e248  test    rsi, rsi
0x18000e24b  jz      short loc_18000E261
0x18000e24d  call    cs:__imp_GetProcessHeap
0x18000e253  mov     r8, rsi; lpMem
0x18000e256  xor     edx, edx; dwFlags
0x18000e258  mov     rcx, rax; hHeap
0x18000e25b  call    cs:__imp_HeapFree
0x18000e261  movups  xmmword ptr [rbx+18h], xmm6
0x18000e265  movsd   qword ptr [rbx+28h], xmm7
0x18000e26a  mov     rsi, [rbx+30h]
0x18000e26e  mov     [rbx+30h], rbp
0x18000e272  test    rsi, rsi
0x18000e275  jz      short loc_18000E28B
0x18000e277  call    cs:__imp_GetProcessHeap
0x18000e27d  mov     r8, rsi; lpMem
0x18000e280  xor     edx, edx; dwFlags
0x18000e282  mov     rcx, rax; hHeap
0x18000e285  call    cs:__imp_HeapFree
0x18000e28b  mov     al, [rbx+38h]
0x18000e28e  mov     cl, [rdi+38h]
0x18000e291  movaps  xmm6, [rsp+68h+var_38]
0x18000e296  movaps  xmm7, [rsp+68h+var_48]
0x18000e29b  mov     [rdi+38h], al
0x18000e29e  mov     al, [rbx+39h]
0x18000e2a1  mov     [rbx+38h], cl
0x18000e2a4  mov     cl, [rdi+39h]
0x18000e2a7  mov     [rdi+39h], al
0x18000e2aa  mov     [rbx+39h], cl
0x18000e2ad  add     rsp, 48h
0x18000e2b1  pop     rdi
0x18000e2b2  pop     rsi
0x18000e2b3  pop     rbp
0x18000e2b4  pop     rbx
0x18000e2b5  retn
```
