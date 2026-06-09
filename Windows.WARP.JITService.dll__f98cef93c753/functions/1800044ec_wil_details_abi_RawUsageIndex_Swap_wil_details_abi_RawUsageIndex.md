# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x1800044ec`
- end: `0x1800045ae`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005710`
- `0x1800057e8`
- `0x180007368`

## callees

- `0x1800044ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004553`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000457d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004553`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000457d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004545`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000456f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004545`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000456f`

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
0x1800044ec  push    rbx
0x1800044ee  push    rbp
0x1800044ef  push    rsi
0x1800044f0  push    rdi
0x1800044f1  sub     rsp, 48h
0x1800044f5  mov     rbp, [rcx+30h]
0x1800044f9  mov     rbx, rdx
0x1800044fc  movaps  [rsp+68h+var_38], xmm6
0x180004501  mov     rdi, rcx
0x180004504  movups  xmm6, xmmword ptr [rcx+18h]
0x180004508  movaps  [rsp+68h+var_48], xmm7
0x18000450d  movsd   xmm7, qword ptr [rcx+28h]
0x180004512  mov     qword ptr [rcx+30h], 0
0x18000451a  movups  xmm0, xmmword ptr [rdx+18h]
0x18000451e  movups  xmmword ptr [rcx+18h], xmm0
0x180004522  movsd   xmm1, qword ptr [rdx+28h]
0x180004527  movsd   qword ptr [rcx+28h], xmm1
0x18000452c  mov     rax, [rdx+30h]
0x180004530  mov     qword ptr [rdx+30h], 0
0x180004538  mov     rsi, [rcx+30h]
0x18000453c  mov     [rcx+30h], rax
0x180004540  test    rsi, rsi
0x180004543  jz      short loc_180004559
0x180004545  call    cs:__imp_GetProcessHeap
0x18000454b  mov     r8, rsi; lpMem
0x18000454e  xor     edx, edx; dwFlags
0x180004550  mov     rcx, rax; hHeap
0x180004553  call    cs:__imp_HeapFree
0x180004559  movups  xmmword ptr [rbx+18h], xmm6
0x18000455d  movsd   qword ptr [rbx+28h], xmm7
0x180004562  mov     rsi, [rbx+30h]
0x180004566  mov     [rbx+30h], rbp
0x18000456a  test    rsi, rsi
0x18000456d  jz      short loc_180004583
0x18000456f  call    cs:__imp_GetProcessHeap
0x180004575  mov     r8, rsi; lpMem
0x180004578  xor     edx, edx; dwFlags
0x18000457a  mov     rcx, rax; hHeap
0x18000457d  call    cs:__imp_HeapFree
0x180004583  mov     al, [rbx+38h]
0x180004586  mov     cl, [rdi+38h]
0x180004589  movaps  xmm6, [rsp+68h+var_38]
0x18000458e  movaps  xmm7, [rsp+68h+var_48]
0x180004593  mov     [rdi+38h], al
0x180004596  mov     al, [rbx+39h]
0x180004599  mov     [rbx+38h], cl
0x18000459c  mov     cl, [rdi+39h]
0x18000459f  mov     [rdi+39h], al
0x1800045a2  mov     [rbx+39h], cl
0x1800045a5  add     rsp, 48h
0x1800045a9  pop     rdi
0x1800045aa  pop     rsi
0x1800045ab  pop     rbp
0x1800045ac  pop     rbx
0x1800045ad  retn
```
