# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180007e18`
- end: `0x180007eda`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003410`
- `0x180006220`
- `0x180006d30`

## callees

- `0x180007e18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ea9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e9b`

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
0x180007e18  push    rbx
0x180007e1a  push    rbp
0x180007e1b  push    rsi
0x180007e1c  push    rdi
0x180007e1d  sub     rsp, 48h
0x180007e21  mov     rbp, [rcx+30h]
0x180007e25  mov     rbx, rdx
0x180007e28  movaps  [rsp+68h+var_38], xmm6
0x180007e2d  mov     rdi, rcx
0x180007e30  movups  xmm6, xmmword ptr [rcx+18h]
0x180007e34  movaps  [rsp+68h+var_48], xmm7
0x180007e39  movsd   xmm7, qword ptr [rcx+28h]
0x180007e3e  mov     qword ptr [rcx+30h], 0
0x180007e46  movups  xmm0, xmmword ptr [rdx+18h]
0x180007e4a  movups  xmmword ptr [rcx+18h], xmm0
0x180007e4e  movsd   xmm1, qword ptr [rdx+28h]
0x180007e53  movsd   qword ptr [rcx+28h], xmm1
0x180007e58  mov     rax, [rdx+30h]
0x180007e5c  mov     qword ptr [rdx+30h], 0
0x180007e64  mov     rsi, [rcx+30h]
0x180007e68  mov     [rcx+30h], rax
0x180007e6c  test    rsi, rsi
0x180007e6f  jz      short loc_180007E85
0x180007e71  call    cs:__imp_GetProcessHeap
0x180007e77  mov     r8, rsi; lpMem
0x180007e7a  xor     edx, edx; dwFlags
0x180007e7c  mov     rcx, rax; hHeap
0x180007e7f  call    cs:__imp_HeapFree
0x180007e85  movups  xmmword ptr [rbx+18h], xmm6
0x180007e89  movsd   qword ptr [rbx+28h], xmm7
0x180007e8e  mov     rsi, [rbx+30h]
0x180007e92  mov     [rbx+30h], rbp
0x180007e96  test    rsi, rsi
0x180007e99  jz      short loc_180007EAF
0x180007e9b  call    cs:__imp_GetProcessHeap
0x180007ea1  mov     r8, rsi; lpMem
0x180007ea4  xor     edx, edx; dwFlags
0x180007ea6  mov     rcx, rax; hHeap
0x180007ea9  call    cs:__imp_HeapFree
0x180007eaf  mov     al, [rbx+38h]
0x180007eb2  mov     cl, [rdi+38h]
0x180007eb5  movaps  xmm6, [rsp+68h+var_38]
0x180007eba  movaps  xmm7, [rsp+68h+var_48]
0x180007ebf  mov     [rdi+38h], al
0x180007ec2  mov     al, [rbx+39h]
0x180007ec5  mov     [rbx+38h], cl
0x180007ec8  mov     cl, [rdi+39h]
0x180007ecb  mov     [rdi+39h], al
0x180007ece  mov     [rbx+39h], cl
0x180007ed1  add     rsp, 48h
0x180007ed5  pop     rdi
0x180007ed6  pop     rsi
0x180007ed7  pop     rbp
0x180007ed8  pop     rbx
0x180007ed9  retn
```
