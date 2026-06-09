# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000aa98`
- end: `0x18000ab5a`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007948`
- `0x1800099c0`
- `0x18000a370`

## callees

- `0x18000aa98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aaf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aaf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aaff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aaff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab29`

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
0x18000aa98  push    rbx
0x18000aa9a  push    rbp
0x18000aa9b  push    rsi
0x18000aa9c  push    rdi
0x18000aa9d  sub     rsp, 48h
0x18000aaa1  mov     rbp, [rcx+30h]
0x18000aaa5  mov     rbx, rdx
0x18000aaa8  movaps  [rsp+68h+var_38], xmm6
0x18000aaad  mov     rdi, rcx
0x18000aab0  movups  xmm6, xmmword ptr [rcx+18h]
0x18000aab4  movaps  [rsp+68h+var_48], xmm7
0x18000aab9  movsd   xmm7, qword ptr [rcx+28h]
0x18000aabe  mov     qword ptr [rcx+30h], 0
0x18000aac6  movups  xmm0, xmmword ptr [rdx+18h]
0x18000aaca  movups  xmmword ptr [rcx+18h], xmm0
0x18000aace  movsd   xmm1, qword ptr [rdx+28h]
0x18000aad3  movsd   qword ptr [rcx+28h], xmm1
0x18000aad8  mov     rax, [rdx+30h]
0x18000aadc  mov     qword ptr [rdx+30h], 0
0x18000aae4  mov     rsi, [rcx+30h]
0x18000aae8  mov     [rcx+30h], rax
0x18000aaec  test    rsi, rsi
0x18000aaef  jz      short loc_18000AB05
0x18000aaf1  call    cs:__imp_GetProcessHeap
0x18000aaf7  mov     r8, rsi; lpMem
0x18000aafa  xor     edx, edx; dwFlags
0x18000aafc  mov     rcx, rax; hHeap
0x18000aaff  call    cs:__imp_HeapFree
0x18000ab05  movups  xmmword ptr [rbx+18h], xmm6
0x18000ab09  movsd   qword ptr [rbx+28h], xmm7
0x18000ab0e  mov     rsi, [rbx+30h]
0x18000ab12  mov     [rbx+30h], rbp
0x18000ab16  test    rsi, rsi
0x18000ab19  jz      short loc_18000AB2F
0x18000ab1b  call    cs:__imp_GetProcessHeap
0x18000ab21  mov     r8, rsi; lpMem
0x18000ab24  xor     edx, edx; dwFlags
0x18000ab26  mov     rcx, rax; hHeap
0x18000ab29  call    cs:__imp_HeapFree
0x18000ab2f  mov     al, [rbx+38h]
0x18000ab32  mov     cl, [rdi+38h]
0x18000ab35  movaps  xmm6, [rsp+68h+var_38]
0x18000ab3a  movaps  xmm7, [rsp+68h+var_48]
0x18000ab3f  mov     [rdi+38h], al
0x18000ab42  mov     al, [rbx+39h]
0x18000ab45  mov     [rbx+38h], cl
0x18000ab48  mov     cl, [rdi+39h]
0x18000ab4b  mov     [rdi+39h], al
0x18000ab4e  mov     [rbx+39h], cl
0x18000ab51  add     rsp, 48h
0x18000ab55  pop     rdi
0x18000ab56  pop     rsi
0x18000ab57  pop     rbp
0x18000ab58  pop     rbx
0x18000ab59  retn
```
