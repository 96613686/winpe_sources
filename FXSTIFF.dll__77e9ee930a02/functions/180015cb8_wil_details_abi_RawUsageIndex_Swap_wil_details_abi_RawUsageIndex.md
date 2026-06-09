# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180015cb8`
- end: `0x180015d93`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `219`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010fb8`
- `0x180014208`
- `0x180014d30`

## callees

- `0x180015cb8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180015d25`
- `KERNEL32!HeapFree` at `0x180015d5b`
- `KERNEL32!HeapFree` at `0x180015d25`
- `KERNEL32!HeapFree` at `0x180015d5b`
- `KERNEL32!GetProcessHeap` at `0x180015d11`
- `KERNEL32!GetProcessHeap` at `0x180015d47`
- `KERNEL32!GetProcessHeap` at `0x180015d11`
- `KERNEL32!GetProcessHeap` at `0x180015d47`

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
0x180015cb8  push    rbx
0x180015cba  push    rbp
0x180015cbb  push    rsi
0x180015cbc  push    rdi
0x180015cbd  sub     rsp, 48h
0x180015cc1  mov     rbp, [rcx+30h]
0x180015cc5  mov     rbx, rdx
0x180015cc8  movaps  [rsp+68h+var_38], xmm6
0x180015ccd  mov     rdi, rcx
0x180015cd0  movups  xmm6, xmmword ptr [rcx+18h]
0x180015cd4  movaps  [rsp+68h+var_48], xmm7
0x180015cd9  movsd   xmm7, qword ptr [rcx+28h]
0x180015cde  mov     qword ptr [rcx+30h], 0
0x180015ce6  movups  xmm0, xmmword ptr [rdx+18h]
0x180015cea  movups  xmmword ptr [rcx+18h], xmm0
0x180015cee  movsd   xmm1, qword ptr [rdx+28h]
0x180015cf3  movsd   qword ptr [rcx+28h], xmm1
0x180015cf8  mov     rax, [rdx+30h]
0x180015cfc  mov     qword ptr [rdx+30h], 0
0x180015d04  mov     rsi, [rcx+30h]
0x180015d08  mov     [rcx+30h], rax
0x180015d0c  test    rsi, rsi
0x180015d0f  jz      short loc_180015D31
0x180015d11  call    cs:__imp_GetProcessHeap
0x180015d18  nop     dword ptr [rax+rax+00h]
0x180015d1d  mov     r8, rsi; lpMem
0x180015d20  xor     edx, edx; dwFlags
0x180015d22  mov     rcx, rax; hHeap
0x180015d25  call    cs:__imp_HeapFree
0x180015d2c  nop     dword ptr [rax+rax+00h]
0x180015d31  movups  xmmword ptr [rbx+18h], xmm6
0x180015d35  movsd   qword ptr [rbx+28h], xmm7
0x180015d3a  mov     rsi, [rbx+30h]
0x180015d3e  mov     [rbx+30h], rbp
0x180015d42  test    rsi, rsi
0x180015d45  jz      short loc_180015D67
0x180015d47  call    cs:__imp_GetProcessHeap
0x180015d4e  nop     dword ptr [rax+rax+00h]
0x180015d53  mov     r8, rsi; lpMem
0x180015d56  xor     edx, edx; dwFlags
0x180015d58  mov     rcx, rax; hHeap
0x180015d5b  call    cs:__imp_HeapFree
0x180015d62  nop     dword ptr [rax+rax+00h]
0x180015d67  mov     al, [rbx+38h]
0x180015d6a  mov     cl, [rdi+38h]
0x180015d6d  movaps  xmm6, [rsp+68h+var_38]
0x180015d72  movaps  xmm7, [rsp+68h+var_48]
0x180015d77  mov     [rdi+38h], al
0x180015d7a  mov     al, [rbx+39h]
0x180015d7d  mov     [rbx+38h], cl
0x180015d80  mov     cl, [rdi+39h]
0x180015d83  mov     [rdi+39h], al
0x180015d86  mov     [rbx+39h], cl
0x180015d89  add     rsp, 48h
0x180015d8d  pop     rdi
0x180015d8e  pop     rsi
0x180015d8f  pop     rbp
0x180015d90  pop     rbx
0x180015d91  retn
```
