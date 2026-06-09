# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14001175c`
- end: `0x14001181e`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005f0c`
- `0x1400104d0`
- `0x140010e70`

## callees

- `0x14001175c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400117b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400117df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400117b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400117df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400117c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400117ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400117c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400117ed`

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
0x14001175c  push    rbx
0x14001175e  push    rbp
0x14001175f  push    rsi
0x140011760  push    rdi
0x140011761  sub     rsp, 48h
0x140011765  mov     rbp, [rcx+30h]
0x140011769  mov     rbx, rdx
0x14001176c  movaps  [rsp+68h+var_38], xmm6
0x140011771  mov     rdi, rcx
0x140011774  movups  xmm6, xmmword ptr [rcx+18h]
0x140011778  movaps  [rsp+68h+var_48], xmm7
0x14001177d  movsd   xmm7, qword ptr [rcx+28h]
0x140011782  mov     qword ptr [rcx+30h], 0
0x14001178a  movups  xmm0, xmmword ptr [rdx+18h]
0x14001178e  movups  xmmword ptr [rcx+18h], xmm0
0x140011792  movsd   xmm1, qword ptr [rdx+28h]
0x140011797  movsd   qword ptr [rcx+28h], xmm1
0x14001179c  mov     rax, [rdx+30h]
0x1400117a0  mov     qword ptr [rdx+30h], 0
0x1400117a8  mov     rsi, [rcx+30h]
0x1400117ac  mov     [rcx+30h], rax
0x1400117b0  test    rsi, rsi
0x1400117b3  jz      short loc_1400117C9
0x1400117b5  call    cs:__imp_GetProcessHeap
0x1400117bb  mov     r8, rsi; lpMem
0x1400117be  xor     edx, edx; dwFlags
0x1400117c0  mov     rcx, rax; hHeap
0x1400117c3  call    cs:__imp_HeapFree
0x1400117c9  movups  xmmword ptr [rbx+18h], xmm6
0x1400117cd  movsd   qword ptr [rbx+28h], xmm7
0x1400117d2  mov     rsi, [rbx+30h]
0x1400117d6  mov     [rbx+30h], rbp
0x1400117da  test    rsi, rsi
0x1400117dd  jz      short loc_1400117F3
0x1400117df  call    cs:__imp_GetProcessHeap
0x1400117e5  mov     r8, rsi; lpMem
0x1400117e8  xor     edx, edx; dwFlags
0x1400117ea  mov     rcx, rax; hHeap
0x1400117ed  call    cs:__imp_HeapFree
0x1400117f3  mov     al, [rbx+38h]
0x1400117f6  mov     cl, [rdi+38h]
0x1400117f9  movaps  xmm6, [rsp+68h+var_38]
0x1400117fe  movaps  xmm7, [rsp+68h+var_48]
0x140011803  mov     [rdi+38h], al
0x140011806  mov     al, [rbx+39h]
0x140011809  mov     [rbx+38h], cl
0x14001180c  mov     cl, [rdi+39h]
0x14001180f  mov     [rdi+39h], al
0x140011812  mov     [rbx+39h], cl
0x140011815  add     rsp, 48h
0x140011819  pop     rdi
0x14001181a  pop     rsi
0x14001181b  pop     rbp
0x14001181c  pop     rbx
0x14001181d  retn
```
