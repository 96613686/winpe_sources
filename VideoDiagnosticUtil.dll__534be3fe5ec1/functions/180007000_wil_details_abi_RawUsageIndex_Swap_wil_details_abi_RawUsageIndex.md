# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x180007000`
- end: `0x1800070db`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `219`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e38`
- `0x180005b40`
- `0x180006658`

## callees

- `0x180007000`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180007059`
- `KERNEL32!GetProcessHeap` at `0x18000708f`
- `KERNEL32!GetProcessHeap` at `0x180007059`
- `KERNEL32!GetProcessHeap` at `0x18000708f`
- `KERNEL32!HeapFree` at `0x18000706d`
- `KERNEL32!HeapFree` at `0x1800070a3`
- `KERNEL32!HeapFree` at `0x18000706d`
- `KERNEL32!HeapFree` at `0x1800070a3`

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
0x180007000  push    rbx
0x180007002  push    rbp
0x180007003  push    rsi
0x180007004  push    rdi
0x180007005  sub     rsp, 48h
0x180007009  mov     rbp, [rcx+30h]
0x18000700d  mov     rbx, rdx
0x180007010  movaps  [rsp+68h+var_38], xmm6
0x180007015  mov     rdi, rcx
0x180007018  movups  xmm6, xmmword ptr [rcx+18h]
0x18000701c  movaps  [rsp+68h+var_48], xmm7
0x180007021  movsd   xmm7, qword ptr [rcx+28h]
0x180007026  mov     qword ptr [rcx+30h], 0
0x18000702e  movups  xmm0, xmmword ptr [rdx+18h]
0x180007032  movups  xmmword ptr [rcx+18h], xmm0
0x180007036  movsd   xmm1, qword ptr [rdx+28h]
0x18000703b  movsd   qword ptr [rcx+28h], xmm1
0x180007040  mov     rax, [rdx+30h]
0x180007044  mov     qword ptr [rdx+30h], 0
0x18000704c  mov     rsi, [rcx+30h]
0x180007050  mov     [rcx+30h], rax
0x180007054  test    rsi, rsi
0x180007057  jz      short loc_180007079
0x180007059  call    cs:__imp_GetProcessHeap
0x180007060  nop     dword ptr [rax+rax+00h]
0x180007065  mov     r8, rsi; lpMem
0x180007068  xor     edx, edx; dwFlags
0x18000706a  mov     rcx, rax; hHeap
0x18000706d  call    cs:__imp_HeapFree
0x180007074  nop     dword ptr [rax+rax+00h]
0x180007079  movups  xmmword ptr [rbx+18h], xmm6
0x18000707d  movsd   qword ptr [rbx+28h], xmm7
0x180007082  mov     rsi, [rbx+30h]
0x180007086  mov     [rbx+30h], rbp
0x18000708a  test    rsi, rsi
0x18000708d  jz      short loc_1800070AF
0x18000708f  call    cs:__imp_GetProcessHeap
0x180007096  nop     dword ptr [rax+rax+00h]
0x18000709b  mov     r8, rsi; lpMem
0x18000709e  xor     edx, edx; dwFlags
0x1800070a0  mov     rcx, rax; hHeap
0x1800070a3  call    cs:__imp_HeapFree
0x1800070aa  nop     dword ptr [rax+rax+00h]
0x1800070af  mov     al, [rbx+38h]
0x1800070b2  mov     cl, [rdi+38h]
0x1800070b5  movaps  xmm6, [rsp+68h+var_38]
0x1800070ba  movaps  xmm7, [rsp+68h+var_48]
0x1800070bf  mov     [rdi+38h], al
0x1800070c2  mov     al, [rbx+39h]
0x1800070c5  mov     [rbx+38h], cl
0x1800070c8  mov     cl, [rdi+39h]
0x1800070cb  mov     [rdi+39h], al
0x1800070ce  mov     [rbx+39h], cl
0x1800070d1  add     rsp, 48h
0x1800070d5  pop     rdi
0x1800070d6  pop     rsi
0x1800070d7  pop     rbp
0x1800070d8  pop     rbx
0x1800070d9  retn
```
