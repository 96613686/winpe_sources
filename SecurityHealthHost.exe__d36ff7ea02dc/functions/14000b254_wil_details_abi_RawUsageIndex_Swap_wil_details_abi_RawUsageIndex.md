# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000b254`
- end: `0x14000b316`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400072b0`
- `0x140009804`
- `0x14000a318`

## callees

- `0x14000b254`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b2ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b2d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b2ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b2d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b2bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b2e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b2bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b2e5`

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
0x14000b254  push    rbx
0x14000b256  push    rbp
0x14000b257  push    rsi
0x14000b258  push    rdi
0x14000b259  sub     rsp, 48h
0x14000b25d  mov     rbp, [rcx+30h]
0x14000b261  mov     rbx, rdx
0x14000b264  movaps  [rsp+68h+var_38], xmm6
0x14000b269  mov     rdi, rcx
0x14000b26c  movups  xmm6, xmmword ptr [rcx+18h]
0x14000b270  movaps  [rsp+68h+var_48], xmm7
0x14000b275  movsd   xmm7, qword ptr [rcx+28h]
0x14000b27a  mov     qword ptr [rcx+30h], 0
0x14000b282  movups  xmm0, xmmword ptr [rdx+18h]
0x14000b286  movups  xmmword ptr [rcx+18h], xmm0
0x14000b28a  movsd   xmm1, qword ptr [rdx+28h]
0x14000b28f  movsd   qword ptr [rcx+28h], xmm1
0x14000b294  mov     rax, [rdx+30h]
0x14000b298  mov     qword ptr [rdx+30h], 0
0x14000b2a0  mov     rsi, [rcx+30h]
0x14000b2a4  mov     [rcx+30h], rax
0x14000b2a8  test    rsi, rsi
0x14000b2ab  jz      short loc_14000B2C1
0x14000b2ad  call    cs:__imp_GetProcessHeap
0x14000b2b3  mov     r8, rsi; lpMem
0x14000b2b6  xor     edx, edx; dwFlags
0x14000b2b8  mov     rcx, rax; hHeap
0x14000b2bb  call    cs:__imp_HeapFree
0x14000b2c1  movups  xmmword ptr [rbx+18h], xmm6
0x14000b2c5  movsd   qword ptr [rbx+28h], xmm7
0x14000b2ca  mov     rsi, [rbx+30h]
0x14000b2ce  mov     [rbx+30h], rbp
0x14000b2d2  test    rsi, rsi
0x14000b2d5  jz      short loc_14000B2EB
0x14000b2d7  call    cs:__imp_GetProcessHeap
0x14000b2dd  mov     r8, rsi; lpMem
0x14000b2e0  xor     edx, edx; dwFlags
0x14000b2e2  mov     rcx, rax; hHeap
0x14000b2e5  call    cs:__imp_HeapFree
0x14000b2eb  mov     al, [rbx+38h]
0x14000b2ee  mov     cl, [rdi+38h]
0x14000b2f1  movaps  xmm6, [rsp+68h+var_38]
0x14000b2f6  movaps  xmm7, [rsp+68h+var_48]
0x14000b2fb  mov     [rdi+38h], al
0x14000b2fe  mov     al, [rbx+39h]
0x14000b301  mov     [rbx+38h], cl
0x14000b304  mov     cl, [rdi+39h]
0x14000b307  mov     [rdi+39h], al
0x14000b30a  mov     [rbx+39h], cl
0x14000b30d  add     rsp, 48h
0x14000b311  pop     rdi
0x14000b312  pop     rsi
0x14000b313  pop     rbp
0x14000b314  pop     rbx
0x14000b315  retn
```
