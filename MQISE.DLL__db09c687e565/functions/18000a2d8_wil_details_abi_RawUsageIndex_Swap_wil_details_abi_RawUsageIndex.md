# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000a2d8`
- end: `0x18000a39c`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `196`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bd8`
- `0x180008900`
- `0x1800093d8`

## callees

- `0x18000a2d8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a331`
- `KERNEL32!GetProcessHeap` at `0x18000a35c`
- `KERNEL32!GetProcessHeap` at `0x18000a331`
- `KERNEL32!GetProcessHeap` at `0x18000a35c`
- `KERNEL32!HeapFree` at `0x18000a33f`
- `KERNEL32!HeapFree` at `0x18000a36a`
- `KERNEL32!HeapFree` at `0x18000a33f`
- `KERNEL32!HeapFree` at `0x18000a36a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::RawUsageIndex::Swap(
        wil::details_abi::RawUsageIndex *this,
        struct wil::details_abi::RawUsageIndex *a2)
{
  __int128 v4; // xmm6
  __int64 v5; // xmm7_8
  __int64 v6; // rbp
  __int64 v7; // rax
  void *v8; // rsi
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  char v12; // cl
  char v13; // cl

  v4 = *(_OWORD *)((char *)this + 24);
  v5 = *((_QWORD *)this + 5);
  v6 = *((_QWORD *)this + 6);
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
  *(_OWORD *)((char *)a2 + 24) = v4;
  *((_QWORD *)a2 + 5) = v5;
  v10 = (void *)*((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = v6;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  v12 = *((_BYTE *)this + 56);
  *((_BYTE *)this + 56) = *((_BYTE *)a2 + 56);
  *((_BYTE *)a2 + 56) = v12;
  v13 = *((_BYTE *)this + 57);
  *((_BYTE *)this + 57) = *((_BYTE *)a2 + 57);
  *((_BYTE *)a2 + 57) = v13;
}

```

## disassembly

```asm
0x18000a2d8  push    rbx
0x18000a2da  push    rbp
0x18000a2db  push    rsi
0x18000a2dc  push    rdi
0x18000a2dd  sub     rsp, 48h
0x18000a2e1  movaps  [rsp+68h+var_38], xmm6
0x18000a2e6  movaps  [rsp+68h+var_48], xmm7
0x18000a2eb  mov     rbx, rdx
0x18000a2ee  mov     rdi, rcx
0x18000a2f1  movups  xmm6, xmmword ptr [rcx+18h]
0x18000a2f5  movsd   xmm7, qword ptr [rcx+28h]
0x18000a2fa  mov     rbp, [rcx+30h]
0x18000a2fe  mov     qword ptr [rcx+30h], 0
0x18000a306  movups  xmm0, xmmword ptr [rdx+18h]
0x18000a30a  movups  xmmword ptr [rcx+18h], xmm0
0x18000a30e  movsd   xmm1, qword ptr [rdx+28h]
0x18000a313  movsd   qword ptr [rcx+28h], xmm1
0x18000a318  mov     rax, [rdx+30h]
0x18000a31c  mov     qword ptr [rdx+30h], 0
0x18000a324  mov     rsi, [rcx+30h]
0x18000a328  mov     [rcx+30h], rax
0x18000a32c  test    rsi, rsi
0x18000a32f  jz      short loc_18000A346
0x18000a331  call    cs:__imp_GetProcessHeap
0x18000a337  mov     rcx, rax; hHeap
0x18000a33a  mov     r8, rsi; lpMem
0x18000a33d  xor     edx, edx; dwFlags
0x18000a33f  call    cs:__imp_HeapFree
0x18000a345  nop
0x18000a346  movups  xmmword ptr [rbx+18h], xmm6
0x18000a34a  movsd   qword ptr [rbx+28h], xmm7
0x18000a34f  mov     rsi, [rbx+30h]
0x18000a353  mov     [rbx+30h], rbp
0x18000a357  test    rsi, rsi
0x18000a35a  jz      short loc_18000A371
0x18000a35c  call    cs:__imp_GetProcessHeap
0x18000a362  mov     rcx, rax; hHeap
0x18000a365  mov     r8, rsi; lpMem
0x18000a368  xor     edx, edx; dwFlags
0x18000a36a  call    cs:__imp_HeapFree
0x18000a370  nop
0x18000a371  mov     cl, [rdi+38h]
0x18000a374  mov     al, [rbx+38h]
0x18000a377  mov     [rdi+38h], al
0x18000a37a  mov     [rbx+38h], cl
0x18000a37d  mov     cl, [rdi+39h]
0x18000a380  mov     al, [rbx+39h]
0x18000a383  mov     [rdi+39h], al
0x18000a386  mov     [rbx+39h], cl
0x18000a389  movaps  xmm6, [rsp+68h+var_38]
0x18000a38e  movaps  xmm7, [rsp+68h+var_48]
0x18000a393  add     rsp, 48h
0x18000a397  pop     rdi
0x18000a398  pop     rsi
0x18000a399  pop     rbp
0x18000a39a  pop     rbx
0x18000a39b  retn
```
