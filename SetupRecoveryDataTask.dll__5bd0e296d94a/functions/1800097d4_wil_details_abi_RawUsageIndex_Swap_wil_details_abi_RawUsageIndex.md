# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x1800097d4`
- end: `0x18000989d`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `201`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000713c`
- `0x180007910`

## callees

- `0x1800097d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000983e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009868`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000983e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009868`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009830`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000985a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009830`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000985a`

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
0x1800097d4  mov     [rsp+arg_10], rbx
0x1800097d9  push    rbp
0x1800097da  push    rsi
0x1800097db  push    rdi
0x1800097dc  sub     rsp, 40h
0x1800097e0  mov     rbp, [rcx+30h]
0x1800097e4  mov     rbx, rdx
0x1800097e7  movaps  [rsp+58h+var_28], xmm6
0x1800097ec  mov     rdi, rcx
0x1800097ef  movups  xmm6, xmmword ptr [rcx+18h]
0x1800097f3  movaps  [rsp+58h+var_38], xmm7
0x1800097f8  movsd   xmm7, qword ptr [rcx+28h]
0x1800097fd  mov     qword ptr [rcx+30h], 0
0x180009805  movups  xmm0, xmmword ptr [rdx+18h]
0x180009809  movups  xmmword ptr [rcx+18h], xmm0
0x18000980d  movsd   xmm1, qword ptr [rdx+28h]
0x180009812  movsd   qword ptr [rcx+28h], xmm1
0x180009817  mov     rax, [rdx+30h]
0x18000981b  mov     qword ptr [rdx+30h], 0
0x180009823  mov     rsi, [rcx+30h]
0x180009827  mov     [rcx+30h], rax
0x18000982b  test    rsi, rsi
0x18000982e  jz      short loc_180009844
0x180009830  call    cs:__imp_GetProcessHeap
0x180009836  mov     r8, rsi; lpMem
0x180009839  xor     edx, edx; dwFlags
0x18000983b  mov     rcx, rax; hHeap
0x18000983e  call    cs:__imp_HeapFree
0x180009844  movups  xmmword ptr [rbx+18h], xmm6
0x180009848  movsd   qword ptr [rbx+28h], xmm7
0x18000984d  mov     rsi, [rbx+30h]
0x180009851  mov     [rbx+30h], rbp
0x180009855  test    rsi, rsi
0x180009858  jz      short loc_18000986E
0x18000985a  call    cs:__imp_GetProcessHeap
0x180009860  mov     r8, rsi; lpMem
0x180009863  xor     edx, edx; dwFlags
0x180009865  mov     rcx, rax; hHeap
0x180009868  call    cs:__imp_HeapFree
0x18000986e  mov     al, [rbx+38h]
0x180009871  mov     cl, [rdi+38h]
0x180009874  movaps  xmm6, [rsp+58h+var_28]
0x180009879  movaps  xmm7, [rsp+58h+var_38]
0x18000987e  mov     [rdi+38h], al
0x180009881  mov     al, [rbx+39h]
0x180009884  mov     [rbx+38h], cl
0x180009887  mov     cl, [rdi+39h]
0x18000988a  mov     [rdi+39h], al
0x18000988d  mov     [rbx+39h], cl
0x180009890  mov     rbx, [rsp+58h+arg_10]
0x180009895  add     rsp, 40h
0x180009899  pop     rdi
0x18000989a  pop     rsi
0x18000989b  pop     rbp
0x18000989c  retn
```
