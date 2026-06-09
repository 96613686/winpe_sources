# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x140015d64`
- end: `0x140015e26`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400131ec`
- `0x140014c14`
- `0x140015610`

## callees

- `0x140015d64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015dcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015df5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015dcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015df5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015dbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015de7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015dbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015de7`

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
0x140015d64  push    rbx
0x140015d66  push    rbp
0x140015d67  push    rsi
0x140015d68  push    rdi
0x140015d69  sub     rsp, 48h
0x140015d6d  mov     rbp, [rcx+30h]
0x140015d71  mov     rbx, rdx
0x140015d74  movaps  [rsp+68h+var_38], xmm6
0x140015d79  mov     rdi, rcx
0x140015d7c  movups  xmm6, xmmword ptr [rcx+18h]
0x140015d80  movaps  [rsp+68h+var_48], xmm7
0x140015d85  movsd   xmm7, qword ptr [rcx+28h]
0x140015d8a  mov     qword ptr [rcx+30h], 0
0x140015d92  movups  xmm0, xmmword ptr [rdx+18h]
0x140015d96  movups  xmmword ptr [rcx+18h], xmm0
0x140015d9a  movsd   xmm1, qword ptr [rdx+28h]
0x140015d9f  movsd   qword ptr [rcx+28h], xmm1
0x140015da4  mov     rax, [rdx+30h]
0x140015da8  mov     qword ptr [rdx+30h], 0
0x140015db0  mov     rsi, [rcx+30h]
0x140015db4  mov     [rcx+30h], rax
0x140015db8  test    rsi, rsi
0x140015dbb  jz      short loc_140015DD1
0x140015dbd  call    cs:__imp_GetProcessHeap
0x140015dc3  mov     r8, rsi; lpMem
0x140015dc6  xor     edx, edx; dwFlags
0x140015dc8  mov     rcx, rax; hHeap
0x140015dcb  call    cs:__imp_HeapFree
0x140015dd1  movups  xmmword ptr [rbx+18h], xmm6
0x140015dd5  movsd   qword ptr [rbx+28h], xmm7
0x140015dda  mov     rsi, [rbx+30h]
0x140015dde  mov     [rbx+30h], rbp
0x140015de2  test    rsi, rsi
0x140015de5  jz      short loc_140015DFB
0x140015de7  call    cs:__imp_GetProcessHeap
0x140015ded  mov     r8, rsi; lpMem
0x140015df0  xor     edx, edx; dwFlags
0x140015df2  mov     rcx, rax; hHeap
0x140015df5  call    cs:__imp_HeapFree
0x140015dfb  mov     al, [rbx+38h]
0x140015dfe  mov     cl, [rdi+38h]
0x140015e01  movaps  xmm6, [rsp+68h+var_38]
0x140015e06  movaps  xmm7, [rsp+68h+var_48]
0x140015e0b  mov     [rdi+38h], al
0x140015e0e  mov     al, [rbx+39h]
0x140015e11  mov     [rbx+38h], cl
0x140015e14  mov     cl, [rdi+39h]
0x140015e17  mov     [rdi+39h], al
0x140015e1a  mov     [rbx+39h], cl
0x140015e1d  add     rsp, 48h
0x140015e21  pop     rdi
0x140015e22  pop     rsi
0x140015e23  pop     rbp
0x140015e24  pop     rbx
0x140015e25  retn
```
