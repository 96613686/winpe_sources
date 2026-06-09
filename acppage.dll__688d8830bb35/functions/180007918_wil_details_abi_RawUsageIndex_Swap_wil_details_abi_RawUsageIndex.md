# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180007918`
- end: `0x1800079da`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033a0`
- `0x180006600`
- `0x1800070b4`

## callees

- `0x180007918`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000797f`
- `KERNEL32!HeapFree` at `0x1800079a9`
- `KERNEL32!HeapFree` at `0x18000797f`
- `KERNEL32!HeapFree` at `0x1800079a9`
- `KERNEL32!GetProcessHeap` at `0x180007971`
- `KERNEL32!GetProcessHeap` at `0x18000799b`
- `KERNEL32!GetProcessHeap` at `0x180007971`
- `KERNEL32!GetProcessHeap` at `0x18000799b`

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
0x180007918  push    rbx
0x18000791a  push    rbp
0x18000791b  push    rsi
0x18000791c  push    rdi
0x18000791d  sub     rsp, 48h
0x180007921  mov     rbp, [rcx+30h]
0x180007925  mov     rbx, rdx
0x180007928  movaps  [rsp+68h+var_38], xmm6
0x18000792d  mov     rdi, rcx
0x180007930  movups  xmm6, xmmword ptr [rcx+18h]
0x180007934  movaps  [rsp+68h+var_48], xmm7
0x180007939  movsd   xmm7, qword ptr [rcx+28h]
0x18000793e  mov     qword ptr [rcx+30h], 0
0x180007946  movups  xmm0, xmmword ptr [rdx+18h]
0x18000794a  movups  xmmword ptr [rcx+18h], xmm0
0x18000794e  movsd   xmm1, qword ptr [rdx+28h]
0x180007953  movsd   qword ptr [rcx+28h], xmm1
0x180007958  mov     rax, [rdx+30h]
0x18000795c  mov     qword ptr [rdx+30h], 0
0x180007964  mov     rsi, [rcx+30h]
0x180007968  mov     [rcx+30h], rax
0x18000796c  test    rsi, rsi
0x18000796f  jz      short loc_180007985
0x180007971  call    cs:__imp_GetProcessHeap
0x180007977  mov     r8, rsi; lpMem
0x18000797a  xor     edx, edx; dwFlags
0x18000797c  mov     rcx, rax; hHeap
0x18000797f  call    cs:__imp_HeapFree
0x180007985  movups  xmmword ptr [rbx+18h], xmm6
0x180007989  movsd   qword ptr [rbx+28h], xmm7
0x18000798e  mov     rsi, [rbx+30h]
0x180007992  mov     [rbx+30h], rbp
0x180007996  test    rsi, rsi
0x180007999  jz      short loc_1800079AF
0x18000799b  call    cs:__imp_GetProcessHeap
0x1800079a1  mov     r8, rsi; lpMem
0x1800079a4  xor     edx, edx; dwFlags
0x1800079a6  mov     rcx, rax; hHeap
0x1800079a9  call    cs:__imp_HeapFree
0x1800079af  mov     al, [rbx+38h]
0x1800079b2  mov     cl, [rdi+38h]
0x1800079b5  movaps  xmm6, [rsp+68h+var_38]
0x1800079ba  movaps  xmm7, [rsp+68h+var_48]
0x1800079bf  mov     [rdi+38h], al
0x1800079c2  mov     al, [rbx+39h]
0x1800079c5  mov     [rbx+38h], cl
0x1800079c8  mov     cl, [rdi+39h]
0x1800079cb  mov     [rdi+39h], al
0x1800079ce  mov     [rbx+39h], cl
0x1800079d1  add     rsp, 48h
0x1800079d5  pop     rdi
0x1800079d6  pop     rsi
0x1800079d7  pop     rbp
0x1800079d8  pop     rbx
0x1800079d9  retn
```
