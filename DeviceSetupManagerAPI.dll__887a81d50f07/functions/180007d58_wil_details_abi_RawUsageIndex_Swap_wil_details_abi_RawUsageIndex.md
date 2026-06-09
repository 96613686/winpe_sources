# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180007d58`
- end: `0x180007e1a`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003570`
- `0x180006320`
- `0x180006e30`

## callees

- `0x180007d58`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007db1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ddb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007db1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ddb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007de9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007de9`

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
0x180007d58  push    rbx
0x180007d5a  push    rbp
0x180007d5b  push    rsi
0x180007d5c  push    rdi
0x180007d5d  sub     rsp, 48h
0x180007d61  mov     rbp, [rcx+30h]
0x180007d65  mov     rbx, rdx
0x180007d68  movaps  [rsp+68h+var_38], xmm6
0x180007d6d  mov     rdi, rcx
0x180007d70  movups  xmm6, xmmword ptr [rcx+18h]
0x180007d74  movaps  [rsp+68h+var_48], xmm7
0x180007d79  movsd   xmm7, qword ptr [rcx+28h]
0x180007d7e  mov     qword ptr [rcx+30h], 0
0x180007d86  movups  xmm0, xmmword ptr [rdx+18h]
0x180007d8a  movups  xmmword ptr [rcx+18h], xmm0
0x180007d8e  movsd   xmm1, qword ptr [rdx+28h]
0x180007d93  movsd   qword ptr [rcx+28h], xmm1
0x180007d98  mov     rax, [rdx+30h]
0x180007d9c  mov     qword ptr [rdx+30h], 0
0x180007da4  mov     rsi, [rcx+30h]
0x180007da8  mov     [rcx+30h], rax
0x180007dac  test    rsi, rsi
0x180007daf  jz      short loc_180007DC5
0x180007db1  call    cs:__imp_GetProcessHeap
0x180007db7  mov     r8, rsi; lpMem
0x180007dba  xor     edx, edx; dwFlags
0x180007dbc  mov     rcx, rax; hHeap
0x180007dbf  call    cs:__imp_HeapFree
0x180007dc5  movups  xmmword ptr [rbx+18h], xmm6
0x180007dc9  movsd   qword ptr [rbx+28h], xmm7
0x180007dce  mov     rsi, [rbx+30h]
0x180007dd2  mov     [rbx+30h], rbp
0x180007dd6  test    rsi, rsi
0x180007dd9  jz      short loc_180007DEF
0x180007ddb  call    cs:__imp_GetProcessHeap
0x180007de1  mov     r8, rsi; lpMem
0x180007de4  xor     edx, edx; dwFlags
0x180007de6  mov     rcx, rax; hHeap
0x180007de9  call    cs:__imp_HeapFree
0x180007def  mov     al, [rbx+38h]
0x180007df2  mov     cl, [rdi+38h]
0x180007df5  movaps  xmm6, [rsp+68h+var_38]
0x180007dfa  movaps  xmm7, [rsp+68h+var_48]
0x180007dff  mov     [rdi+38h], al
0x180007e02  mov     al, [rbx+39h]
0x180007e05  mov     [rbx+38h], cl
0x180007e08  mov     cl, [rdi+39h]
0x180007e0b  mov     [rdi+39h], al
0x180007e0e  mov     [rbx+39h], cl
0x180007e11  add     rsp, 48h
0x180007e15  pop     rdi
0x180007e16  pop     rsi
0x180007e17  pop     rbp
0x180007e18  pop     rbx
0x180007e19  retn
```
