# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x1800084bc`
- end: `0x180008551`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007508`

## callees

- `0x1800084bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008532`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008532`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000851e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000851e`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::Clear(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800084bc  push    rbx
0x1800084be  push    rbp
0x1800084bf  push    rsi
0x1800084c0  push    rdi
0x1800084c1  sub     rsp, 28h
0x1800084c5  movzx   eax, word ptr [rcx+20h]
0x1800084c9  mov     rsi, rcx
0x1800084cc  mov     rdi, [rcx+18h]
0x1800084d0  lea     rbp, [rax+rax*4]
0x1800084d4  shl     rbp, 4
0x1800084d8  add     rbp, rdi
0x1800084db  jmp     short loc_180008515
0x1800084dd  mov     rbx, [rdi+40h]
0x1800084e1  call    cs:__imp_GetProcessHeap
0x1800084e8  nop     dword ptr [rax+rax+00h]
0x1800084ed  mov     r8, rbx; lpMem
0x1800084f0  xor     edx, edx; dwFlags
0x1800084f2  mov     rcx, rax; hHeap
0x1800084f5  call    cs:__imp_HeapFree
0x1800084fc  nop     dword ptr [rax+rax+00h]
0x180008501  mov     qword ptr [rdi+40h], 0
0x180008509  mov     qword ptr [rdi+48h], 0
0x180008511  add     rdi, 50h ; 'P'
0x180008515  cmp     rdi, rbp
0x180008518  jnz     short loc_1800084DD
0x18000851a  mov     rbx, [rsi+18h]
0x18000851e  call    cs:__imp_GetProcessHeap
0x180008525  nop     dword ptr [rax+rax+00h]
0x18000852a  mov     r8, rbx; lpMem
0x18000852d  xor     edx, edx; dwFlags
0x18000852f  mov     rcx, rax; hHeap
0x180008532  call    cs:__imp_HeapFree
0x180008539  nop     dword ptr [rax+rax+00h]
0x18000853e  xor     eax, eax
0x180008540  mov     [rsi+20h], eax
0x180008543  mov     [rsi+18h], rax
0x180008547  add     rsp, 28h
0x18000854b  pop     rdi
0x18000854c  pop     rsi
0x18000854d  pop     rbp
0x18000854e  pop     rbx
0x18000854f  retn
```
