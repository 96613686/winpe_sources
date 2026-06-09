# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180015228`
- end: `0x1800152ea`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010920`
- `0x1800139c0`
- `0x180014484`

## callees

- `0x180015228`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001528f`
- `KERNEL32!HeapFree` at `0x1800152b9`
- `KERNEL32!HeapFree` at `0x18001528f`
- `KERNEL32!HeapFree` at `0x1800152b9`
- `KERNEL32!GetProcessHeap` at `0x180015281`
- `KERNEL32!GetProcessHeap` at `0x1800152ab`
- `KERNEL32!GetProcessHeap` at `0x180015281`
- `KERNEL32!GetProcessHeap` at `0x1800152ab`

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
0x180015228  push    rbx
0x18001522a  push    rbp
0x18001522b  push    rsi
0x18001522c  push    rdi
0x18001522d  sub     rsp, 48h
0x180015231  mov     rbp, [rcx+30h]
0x180015235  mov     rbx, rdx
0x180015238  movaps  [rsp+68h+var_38], xmm6
0x18001523d  mov     rdi, rcx
0x180015240  movups  xmm6, xmmword ptr [rcx+18h]
0x180015244  movaps  [rsp+68h+var_48], xmm7
0x180015249  movsd   xmm7, qword ptr [rcx+28h]
0x18001524e  mov     qword ptr [rcx+30h], 0
0x180015256  movups  xmm0, xmmword ptr [rdx+18h]
0x18001525a  movups  xmmword ptr [rcx+18h], xmm0
0x18001525e  movsd   xmm1, qword ptr [rdx+28h]
0x180015263  movsd   qword ptr [rcx+28h], xmm1
0x180015268  mov     rax, [rdx+30h]
0x18001526c  mov     qword ptr [rdx+30h], 0
0x180015274  mov     rsi, [rcx+30h]
0x180015278  mov     [rcx+30h], rax
0x18001527c  test    rsi, rsi
0x18001527f  jz      short loc_180015295
0x180015281  call    cs:__imp_GetProcessHeap
0x180015287  mov     r8, rsi; lpMem
0x18001528a  xor     edx, edx; dwFlags
0x18001528c  mov     rcx, rax; hHeap
0x18001528f  call    cs:__imp_HeapFree
0x180015295  movups  xmmword ptr [rbx+18h], xmm6
0x180015299  movsd   qword ptr [rbx+28h], xmm7
0x18001529e  mov     rsi, [rbx+30h]
0x1800152a2  mov     [rbx+30h], rbp
0x1800152a6  test    rsi, rsi
0x1800152a9  jz      short loc_1800152BF
0x1800152ab  call    cs:__imp_GetProcessHeap
0x1800152b1  mov     r8, rsi; lpMem
0x1800152b4  xor     edx, edx; dwFlags
0x1800152b6  mov     rcx, rax; hHeap
0x1800152b9  call    cs:__imp_HeapFree
0x1800152bf  mov     al, [rbx+38h]
0x1800152c2  mov     cl, [rdi+38h]
0x1800152c5  movaps  xmm6, [rsp+68h+var_38]
0x1800152ca  movaps  xmm7, [rsp+68h+var_48]
0x1800152cf  mov     [rdi+38h], al
0x1800152d2  mov     al, [rbx+39h]
0x1800152d5  mov     [rbx+38h], cl
0x1800152d8  mov     cl, [rdi+39h]
0x1800152db  mov     [rdi+39h], al
0x1800152de  mov     [rbx+39h], cl
0x1800152e1  add     rsp, 48h
0x1800152e5  pop     rdi
0x1800152e6  pop     rsi
0x1800152e7  pop     rbp
0x1800152e8  pop     rbx
0x1800152e9  retn
```
