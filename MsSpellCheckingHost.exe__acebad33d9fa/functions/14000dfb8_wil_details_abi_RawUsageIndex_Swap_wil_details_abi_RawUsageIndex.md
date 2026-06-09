# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000dfb8`
- end: `0x14000e07a`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140008a34`
- `0x14000c560`
- `0x14000d0ac`

## callees

- `0x14000dfb8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e01f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e049`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e01f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e049`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e03b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e03b`

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
0x14000dfb8  push    rbx
0x14000dfba  push    rbp
0x14000dfbb  push    rsi
0x14000dfbc  push    rdi
0x14000dfbd  sub     rsp, 48h
0x14000dfc1  mov     rbp, [rcx+30h]
0x14000dfc5  mov     rbx, rdx
0x14000dfc8  movaps  [rsp+68h+var_38], xmm6
0x14000dfcd  mov     rdi, rcx
0x14000dfd0  movups  xmm6, xmmword ptr [rcx+18h]
0x14000dfd4  movaps  [rsp+68h+var_48], xmm7
0x14000dfd9  movsd   xmm7, qword ptr [rcx+28h]
0x14000dfde  mov     qword ptr [rcx+30h], 0
0x14000dfe6  movups  xmm0, xmmword ptr [rdx+18h]
0x14000dfea  movups  xmmword ptr [rcx+18h], xmm0
0x14000dfee  movsd   xmm1, qword ptr [rdx+28h]
0x14000dff3  movsd   qword ptr [rcx+28h], xmm1
0x14000dff8  mov     rax, [rdx+30h]
0x14000dffc  mov     qword ptr [rdx+30h], 0
0x14000e004  mov     rsi, [rcx+30h]
0x14000e008  mov     [rcx+30h], rax
0x14000e00c  test    rsi, rsi
0x14000e00f  jz      short loc_14000E025
0x14000e011  call    cs:__imp_GetProcessHeap
0x14000e017  mov     r8, rsi; lpMem
0x14000e01a  xor     edx, edx; dwFlags
0x14000e01c  mov     rcx, rax; hHeap
0x14000e01f  call    cs:__imp_HeapFree
0x14000e025  movups  xmmword ptr [rbx+18h], xmm6
0x14000e029  movsd   qword ptr [rbx+28h], xmm7
0x14000e02e  mov     rsi, [rbx+30h]
0x14000e032  mov     [rbx+30h], rbp
0x14000e036  test    rsi, rsi
0x14000e039  jz      short loc_14000E04F
0x14000e03b  call    cs:__imp_GetProcessHeap
0x14000e041  mov     r8, rsi; lpMem
0x14000e044  xor     edx, edx; dwFlags
0x14000e046  mov     rcx, rax; hHeap
0x14000e049  call    cs:__imp_HeapFree
0x14000e04f  mov     al, [rbx+38h]
0x14000e052  mov     cl, [rdi+38h]
0x14000e055  movaps  xmm6, [rsp+68h+var_38]
0x14000e05a  movaps  xmm7, [rsp+68h+var_48]
0x14000e05f  mov     [rdi+38h], al
0x14000e062  mov     al, [rbx+39h]
0x14000e065  mov     [rbx+38h], cl
0x14000e068  mov     cl, [rdi+39h]
0x14000e06b  mov     [rdi+39h], al
0x14000e06e  mov     [rbx+39h], cl
0x14000e071  add     rsp, 48h
0x14000e075  pop     rdi
0x14000e076  pop     rsi
0x14000e077  pop     rbp
0x14000e078  pop     rbx
0x14000e079  retn
```
