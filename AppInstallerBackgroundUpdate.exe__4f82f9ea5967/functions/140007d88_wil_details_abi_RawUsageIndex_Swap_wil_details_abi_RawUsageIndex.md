# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x140007d88`
- end: `0x140007e4a`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005be8`
- `0x140006f14`
- `0x140007910`

## callees

- `0x140007d88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007de1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007e0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007de1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007e0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007def`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007e19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007def`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007e19`

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
0x140007d88  push    rbx
0x140007d8a  push    rbp
0x140007d8b  push    rsi
0x140007d8c  push    rdi
0x140007d8d  sub     rsp, 48h
0x140007d91  mov     rbp, [rcx+30h]
0x140007d95  mov     rbx, rdx
0x140007d98  movaps  [rsp+68h+var_38], xmm6
0x140007d9d  mov     rdi, rcx
0x140007da0  movups  xmm6, xmmword ptr [rcx+18h]
0x140007da4  movaps  [rsp+68h+var_48], xmm7
0x140007da9  movsd   xmm7, qword ptr [rcx+28h]
0x140007dae  mov     qword ptr [rcx+30h], 0
0x140007db6  movups  xmm0, xmmword ptr [rdx+18h]
0x140007dba  movups  xmmword ptr [rcx+18h], xmm0
0x140007dbe  movsd   xmm1, qword ptr [rdx+28h]
0x140007dc3  movsd   qword ptr [rcx+28h], xmm1
0x140007dc8  mov     rax, [rdx+30h]
0x140007dcc  mov     qword ptr [rdx+30h], 0
0x140007dd4  mov     rsi, [rcx+30h]
0x140007dd8  mov     [rcx+30h], rax
0x140007ddc  test    rsi, rsi
0x140007ddf  jz      short loc_140007DF5
0x140007de1  call    cs:__imp_GetProcessHeap
0x140007de7  mov     r8, rsi; lpMem
0x140007dea  xor     edx, edx; dwFlags
0x140007dec  mov     rcx, rax; hHeap
0x140007def  call    cs:__imp_HeapFree
0x140007df5  movups  xmmword ptr [rbx+18h], xmm6
0x140007df9  movsd   qword ptr [rbx+28h], xmm7
0x140007dfe  mov     rsi, [rbx+30h]
0x140007e02  mov     [rbx+30h], rbp
0x140007e06  test    rsi, rsi
0x140007e09  jz      short loc_140007E1F
0x140007e0b  call    cs:__imp_GetProcessHeap
0x140007e11  mov     r8, rsi; lpMem
0x140007e14  xor     edx, edx; dwFlags
0x140007e16  mov     rcx, rax; hHeap
0x140007e19  call    cs:__imp_HeapFree
0x140007e1f  mov     al, [rbx+38h]
0x140007e22  mov     cl, [rdi+38h]
0x140007e25  movaps  xmm6, [rsp+68h+var_38]
0x140007e2a  movaps  xmm7, [rsp+68h+var_48]
0x140007e2f  mov     [rdi+38h], al
0x140007e32  mov     al, [rbx+39h]
0x140007e35  mov     [rbx+38h], cl
0x140007e38  mov     cl, [rdi+39h]
0x140007e3b  mov     [rdi+39h], al
0x140007e3e  mov     [rbx+39h], cl
0x140007e41  add     rsp, 48h
0x140007e45  pop     rdi
0x140007e46  pop     rsi
0x140007e47  pop     rbp
0x140007e48  pop     rbx
0x140007e49  retn
```
