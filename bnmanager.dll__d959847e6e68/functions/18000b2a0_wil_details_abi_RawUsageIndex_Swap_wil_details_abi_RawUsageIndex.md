# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000b2a0`
- end: `0x18000b362`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005274`
- `0x1800095e0`
- `0x18000a190`

## callees

- `0x18000b2a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b307`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b331`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b307`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b323`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b323`

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
0x18000b2a0  push    rbx
0x18000b2a2  push    rbp
0x18000b2a3  push    rsi
0x18000b2a4  push    rdi
0x18000b2a5  sub     rsp, 48h
0x18000b2a9  mov     rbp, [rcx+30h]
0x18000b2ad  mov     rbx, rdx
0x18000b2b0  movaps  [rsp+68h+var_38], xmm6
0x18000b2b5  mov     rdi, rcx
0x18000b2b8  movups  xmm6, xmmword ptr [rcx+18h]
0x18000b2bc  movaps  [rsp+68h+var_48], xmm7
0x18000b2c1  movsd   xmm7, qword ptr [rcx+28h]
0x18000b2c6  mov     qword ptr [rcx+30h], 0
0x18000b2ce  movups  xmm0, xmmword ptr [rdx+18h]
0x18000b2d2  movups  xmmword ptr [rcx+18h], xmm0
0x18000b2d6  movsd   xmm1, qword ptr [rdx+28h]
0x18000b2db  movsd   qword ptr [rcx+28h], xmm1
0x18000b2e0  mov     rax, [rdx+30h]
0x18000b2e4  mov     qword ptr [rdx+30h], 0
0x18000b2ec  mov     rsi, [rcx+30h]
0x18000b2f0  mov     [rcx+30h], rax
0x18000b2f4  test    rsi, rsi
0x18000b2f7  jz      short loc_18000B30D
0x18000b2f9  call    cs:__imp_GetProcessHeap
0x18000b2ff  mov     r8, rsi; lpMem
0x18000b302  xor     edx, edx; dwFlags
0x18000b304  mov     rcx, rax; hHeap
0x18000b307  call    cs:__imp_HeapFree
0x18000b30d  movups  xmmword ptr [rbx+18h], xmm6
0x18000b311  movsd   qword ptr [rbx+28h], xmm7
0x18000b316  mov     rsi, [rbx+30h]
0x18000b31a  mov     [rbx+30h], rbp
0x18000b31e  test    rsi, rsi
0x18000b321  jz      short loc_18000B337
0x18000b323  call    cs:__imp_GetProcessHeap
0x18000b329  mov     r8, rsi; lpMem
0x18000b32c  xor     edx, edx; dwFlags
0x18000b32e  mov     rcx, rax; hHeap
0x18000b331  call    cs:__imp_HeapFree
0x18000b337  mov     al, [rbx+38h]
0x18000b33a  mov     cl, [rdi+38h]
0x18000b33d  movaps  xmm6, [rsp+68h+var_38]
0x18000b342  movaps  xmm7, [rsp+68h+var_48]
0x18000b347  mov     [rdi+38h], al
0x18000b34a  mov     al, [rbx+39h]
0x18000b34d  mov     [rbx+38h], cl
0x18000b350  mov     cl, [rdi+39h]
0x18000b353  mov     [rdi+39h], al
0x18000b356  mov     [rbx+39h], cl
0x18000b359  add     rsp, 48h
0x18000b35d  pop     rdi
0x18000b35e  pop     rsi
0x18000b35f  pop     rbp
0x18000b360  pop     rbx
0x18000b361  retn
```
