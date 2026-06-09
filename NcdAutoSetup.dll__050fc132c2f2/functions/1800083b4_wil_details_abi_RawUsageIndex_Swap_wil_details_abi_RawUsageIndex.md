# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x1800083b4`
- end: `0x180008476`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003594`
- `0x1800065cc`
- `0x180007080`

## callees

- `0x1800083b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000841b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008445`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000841b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000840d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008437`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000840d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008437`

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
0x1800083b4  push    rbx
0x1800083b6  push    rbp
0x1800083b7  push    rsi
0x1800083b8  push    rdi
0x1800083b9  sub     rsp, 48h
0x1800083bd  mov     rbp, [rcx+30h]
0x1800083c1  mov     rbx, rdx
0x1800083c4  movaps  [rsp+68h+var_38], xmm6
0x1800083c9  mov     rdi, rcx
0x1800083cc  movups  xmm6, xmmword ptr [rcx+18h]
0x1800083d0  movaps  [rsp+68h+var_48], xmm7
0x1800083d5  movsd   xmm7, qword ptr [rcx+28h]
0x1800083da  mov     qword ptr [rcx+30h], 0
0x1800083e2  movups  xmm0, xmmword ptr [rdx+18h]
0x1800083e6  movups  xmmword ptr [rcx+18h], xmm0
0x1800083ea  movsd   xmm1, qword ptr [rdx+28h]
0x1800083ef  movsd   qword ptr [rcx+28h], xmm1
0x1800083f4  mov     rax, [rdx+30h]
0x1800083f8  mov     qword ptr [rdx+30h], 0
0x180008400  mov     rsi, [rcx+30h]
0x180008404  mov     [rcx+30h], rax
0x180008408  test    rsi, rsi
0x18000840b  jz      short loc_180008421
0x18000840d  call    cs:__imp_GetProcessHeap
0x180008413  mov     r8, rsi; lpMem
0x180008416  xor     edx, edx; dwFlags
0x180008418  mov     rcx, rax; hHeap
0x18000841b  call    cs:__imp_HeapFree
0x180008421  movups  xmmword ptr [rbx+18h], xmm6
0x180008425  movsd   qword ptr [rbx+28h], xmm7
0x18000842a  mov     rsi, [rbx+30h]
0x18000842e  mov     [rbx+30h], rbp
0x180008432  test    rsi, rsi
0x180008435  jz      short loc_18000844B
0x180008437  call    cs:__imp_GetProcessHeap
0x18000843d  mov     r8, rsi; lpMem
0x180008440  xor     edx, edx; dwFlags
0x180008442  mov     rcx, rax; hHeap
0x180008445  call    cs:__imp_HeapFree
0x18000844b  mov     al, [rbx+38h]
0x18000844e  mov     cl, [rdi+38h]
0x180008451  movaps  xmm6, [rsp+68h+var_38]
0x180008456  movaps  xmm7, [rsp+68h+var_48]
0x18000845b  mov     [rdi+38h], al
0x18000845e  mov     al, [rbx+39h]
0x180008461  mov     [rbx+38h], cl
0x180008464  mov     cl, [rdi+39h]
0x180008467  mov     [rdi+39h], al
0x18000846a  mov     [rbx+39h], cl
0x18000846d  add     rsp, 48h
0x180008471  pop     rdi
0x180008472  pop     rsi
0x180008473  pop     rbp
0x180008474  pop     rbx
0x180008475  retn
```
