# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180007280`
- end: `0x180007342`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003224`
- `0x180005e1c`
- `0x180006920`

## callees

- `0x180007280`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007303`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007303`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007311`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800072e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007311`

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
0x180007280  push    rbx
0x180007282  push    rbp
0x180007283  push    rsi
0x180007284  push    rdi
0x180007285  sub     rsp, 48h
0x180007289  mov     rbp, [rcx+30h]
0x18000728d  mov     rbx, rdx
0x180007290  movaps  [rsp+68h+var_38], xmm6
0x180007295  mov     rdi, rcx
0x180007298  movups  xmm6, xmmword ptr [rcx+18h]
0x18000729c  movaps  [rsp+68h+var_48], xmm7
0x1800072a1  movsd   xmm7, qword ptr [rcx+28h]
0x1800072a6  mov     qword ptr [rcx+30h], 0
0x1800072ae  movups  xmm0, xmmword ptr [rdx+18h]
0x1800072b2  movups  xmmword ptr [rcx+18h], xmm0
0x1800072b6  movsd   xmm1, qword ptr [rdx+28h]
0x1800072bb  movsd   qword ptr [rcx+28h], xmm1
0x1800072c0  mov     rax, [rdx+30h]
0x1800072c4  mov     qword ptr [rdx+30h], 0
0x1800072cc  mov     rsi, [rcx+30h]
0x1800072d0  mov     [rcx+30h], rax
0x1800072d4  test    rsi, rsi
0x1800072d7  jz      short loc_1800072ED
0x1800072d9  call    cs:__imp_GetProcessHeap
0x1800072df  mov     r8, rsi; lpMem
0x1800072e2  xor     edx, edx; dwFlags
0x1800072e4  mov     rcx, rax; hHeap
0x1800072e7  call    cs:__imp_HeapFree
0x1800072ed  movups  xmmword ptr [rbx+18h], xmm6
0x1800072f1  movsd   qword ptr [rbx+28h], xmm7
0x1800072f6  mov     rsi, [rbx+30h]
0x1800072fa  mov     [rbx+30h], rbp
0x1800072fe  test    rsi, rsi
0x180007301  jz      short loc_180007317
0x180007303  call    cs:__imp_GetProcessHeap
0x180007309  mov     r8, rsi; lpMem
0x18000730c  xor     edx, edx; dwFlags
0x18000730e  mov     rcx, rax; hHeap
0x180007311  call    cs:__imp_HeapFree
0x180007317  mov     al, [rbx+38h]
0x18000731a  mov     cl, [rdi+38h]
0x18000731d  movaps  xmm6, [rsp+68h+var_38]
0x180007322  movaps  xmm7, [rsp+68h+var_48]
0x180007327  mov     [rdi+38h], al
0x18000732a  mov     al, [rbx+39h]
0x18000732d  mov     [rbx+38h], cl
0x180007330  mov     cl, [rdi+39h]
0x180007333  mov     [rdi+39h], al
0x180007336  mov     [rbx+39h], cl
0x180007339  add     rsp, 48h
0x18000733d  pop     rdi
0x18000733e  pop     rsi
0x18000733f  pop     rbp
0x180007340  pop     rbx
0x180007341  retn
```
