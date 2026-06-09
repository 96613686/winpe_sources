# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x1800072e0`
- end: `0x1800073a2`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d94`
- `0x180005d60`
- `0x180006814`

## callees

- `0x1800072e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007347`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007371`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007347`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007371`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007339`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007363`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007339`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007363`

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
0x1800072e0  push    rbx
0x1800072e2  push    rbp
0x1800072e3  push    rsi
0x1800072e4  push    rdi
0x1800072e5  sub     rsp, 48h
0x1800072e9  mov     rbp, [rcx+30h]
0x1800072ed  mov     rbx, rdx
0x1800072f0  movaps  [rsp+68h+var_38], xmm6
0x1800072f5  mov     rdi, rcx
0x1800072f8  movups  xmm6, xmmword ptr [rcx+18h]
0x1800072fc  movaps  [rsp+68h+var_48], xmm7
0x180007301  movsd   xmm7, qword ptr [rcx+28h]
0x180007306  mov     qword ptr [rcx+30h], 0
0x18000730e  movups  xmm0, xmmword ptr [rdx+18h]
0x180007312  movups  xmmword ptr [rcx+18h], xmm0
0x180007316  movsd   xmm1, qword ptr [rdx+28h]
0x18000731b  movsd   qword ptr [rcx+28h], xmm1
0x180007320  mov     rax, [rdx+30h]
0x180007324  mov     qword ptr [rdx+30h], 0
0x18000732c  mov     rsi, [rcx+30h]
0x180007330  mov     [rcx+30h], rax
0x180007334  test    rsi, rsi
0x180007337  jz      short loc_18000734D
0x180007339  call    cs:__imp_GetProcessHeap
0x18000733f  mov     r8, rsi; lpMem
0x180007342  xor     edx, edx; dwFlags
0x180007344  mov     rcx, rax; hHeap
0x180007347  call    cs:__imp_HeapFree
0x18000734d  movups  xmmword ptr [rbx+18h], xmm6
0x180007351  movsd   qword ptr [rbx+28h], xmm7
0x180007356  mov     rsi, [rbx+30h]
0x18000735a  mov     [rbx+30h], rbp
0x18000735e  test    rsi, rsi
0x180007361  jz      short loc_180007377
0x180007363  call    cs:__imp_GetProcessHeap
0x180007369  mov     r8, rsi; lpMem
0x18000736c  xor     edx, edx; dwFlags
0x18000736e  mov     rcx, rax; hHeap
0x180007371  call    cs:__imp_HeapFree
0x180007377  mov     al, [rbx+38h]
0x18000737a  mov     cl, [rdi+38h]
0x18000737d  movaps  xmm6, [rsp+68h+var_38]
0x180007382  movaps  xmm7, [rsp+68h+var_48]
0x180007387  mov     [rdi+38h], al
0x18000738a  mov     al, [rbx+39h]
0x18000738d  mov     [rbx+38h], cl
0x180007390  mov     cl, [rdi+39h]
0x180007393  mov     [rdi+39h], al
0x180007396  mov     [rbx+39h], cl
0x180007399  add     rsp, 48h
0x18000739d  pop     rdi
0x18000739e  pop     rsi
0x18000739f  pop     rbp
0x1800073a0  pop     rbx
0x1800073a1  retn
```
