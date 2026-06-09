# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000cd10`
- end: `0x14000cdd2`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140007f3c`
- `0x14000b440`
- `0x14000c13c`

## callees

- `0x14000cd10`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000cd77`
- `KERNEL32!HeapFree` at `0x14000cda1`
- `KERNEL32!HeapFree` at `0x14000cd77`
- `KERNEL32!HeapFree` at `0x14000cda1`
- `KERNEL32!GetProcessHeap` at `0x14000cd69`
- `KERNEL32!GetProcessHeap` at `0x14000cd93`
- `KERNEL32!GetProcessHeap` at `0x14000cd69`
- `KERNEL32!GetProcessHeap` at `0x14000cd93`

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
0x14000cd10  push    rbx
0x14000cd12  push    rbp
0x14000cd13  push    rsi
0x14000cd14  push    rdi
0x14000cd15  sub     rsp, 48h
0x14000cd19  mov     rbp, [rcx+30h]
0x14000cd1d  mov     rbx, rdx
0x14000cd20  movaps  [rsp+68h+var_38], xmm6
0x14000cd25  mov     rdi, rcx
0x14000cd28  movups  xmm6, xmmword ptr [rcx+18h]
0x14000cd2c  movaps  [rsp+68h+var_48], xmm7
0x14000cd31  movsd   xmm7, qword ptr [rcx+28h]
0x14000cd36  mov     qword ptr [rcx+30h], 0
0x14000cd3e  movups  xmm0, xmmword ptr [rdx+18h]
0x14000cd42  movups  xmmword ptr [rcx+18h], xmm0
0x14000cd46  movsd   xmm1, qword ptr [rdx+28h]
0x14000cd4b  movsd   qword ptr [rcx+28h], xmm1
0x14000cd50  mov     rax, [rdx+30h]
0x14000cd54  mov     qword ptr [rdx+30h], 0
0x14000cd5c  mov     rsi, [rcx+30h]
0x14000cd60  mov     [rcx+30h], rax
0x14000cd64  test    rsi, rsi
0x14000cd67  jz      short loc_14000CD7D
0x14000cd69  call    cs:__imp_GetProcessHeap
0x14000cd6f  mov     r8, rsi; lpMem
0x14000cd72  xor     edx, edx; dwFlags
0x14000cd74  mov     rcx, rax; hHeap
0x14000cd77  call    cs:__imp_HeapFree
0x14000cd7d  movups  xmmword ptr [rbx+18h], xmm6
0x14000cd81  movsd   qword ptr [rbx+28h], xmm7
0x14000cd86  mov     rsi, [rbx+30h]
0x14000cd8a  mov     [rbx+30h], rbp
0x14000cd8e  test    rsi, rsi
0x14000cd91  jz      short loc_14000CDA7
0x14000cd93  call    cs:__imp_GetProcessHeap
0x14000cd99  mov     r8, rsi; lpMem
0x14000cd9c  xor     edx, edx; dwFlags
0x14000cd9e  mov     rcx, rax; hHeap
0x14000cda1  call    cs:__imp_HeapFree
0x14000cda7  mov     al, [rbx+38h]
0x14000cdaa  mov     cl, [rdi+38h]
0x14000cdad  movaps  xmm6, [rsp+68h+var_38]
0x14000cdb2  movaps  xmm7, [rsp+68h+var_48]
0x14000cdb7  mov     [rdi+38h], al
0x14000cdba  mov     al, [rbx+39h]
0x14000cdbd  mov     [rbx+38h], cl
0x14000cdc0  mov     cl, [rdi+39h]
0x14000cdc3  mov     [rdi+39h], al
0x14000cdc6  mov     [rbx+39h], cl
0x14000cdc9  add     rsp, 48h
0x14000cdcd  pop     rdi
0x14000cdce  pop     rsi
0x14000cdcf  pop     rbp
0x14000cdd0  pop     rbx
0x14000cdd1  retn
```
