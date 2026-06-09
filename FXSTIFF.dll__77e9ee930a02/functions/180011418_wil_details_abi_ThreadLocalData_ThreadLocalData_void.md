# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180011418`
- end: `0x1800114ad`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010d24`

## callees

- `0x180011418`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180011451`
- `KERNEL32!HeapFree` at `0x18001148e`
- `KERNEL32!HeapFree` at `0x180011451`
- `KERNEL32!HeapFree` at `0x18001148e`
- `KERNEL32!GetProcessHeap` at `0x18001143d`
- `KERNEL32!GetProcessHeap` at `0x18001147a`
- `KERNEL32!GetProcessHeap` at `0x18001143d`
- `KERNEL32!GetProcessHeap` at `0x18001147a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
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
0x180011418  push    rbx
0x18001141a  push    rbp
0x18001141b  push    rsi
0x18001141c  push    rdi
0x18001141d  sub     rsp, 28h
0x180011421  movzx   eax, word ptr [rcx+20h]
0x180011425  mov     rsi, rcx
0x180011428  mov     rdi, [rcx+18h]
0x18001142c  lea     rbp, [rax+rax*4]
0x180011430  shl     rbp, 4
0x180011434  add     rbp, rdi
0x180011437  jmp     short loc_180011471
0x180011439  mov     rbx, [rdi+40h]
0x18001143d  call    cs:__imp_GetProcessHeap
0x180011444  nop     dword ptr [rax+rax+00h]
0x180011449  mov     r8, rbx; lpMem
0x18001144c  xor     edx, edx; dwFlags
0x18001144e  mov     rcx, rax; hHeap
0x180011451  call    cs:__imp_HeapFree
0x180011458  nop     dword ptr [rax+rax+00h]
0x18001145d  mov     qword ptr [rdi+40h], 0
0x180011465  mov     qword ptr [rdi+48h], 0
0x18001146d  add     rdi, 50h ; 'P'
0x180011471  cmp     rdi, rbp
0x180011474  jnz     short loc_180011439
0x180011476  mov     rbx, [rsi+18h]
0x18001147a  call    cs:__imp_GetProcessHeap
0x180011481  nop     dword ptr [rax+rax+00h]
0x180011486  mov     r8, rbx; lpMem
0x180011489  xor     edx, edx; dwFlags
0x18001148b  mov     rcx, rax; hHeap
0x18001148e  call    cs:__imp_HeapFree
0x180011495  nop     dword ptr [rax+rax+00h]
0x18001149a  xor     eax, eax
0x18001149c  mov     [rsi+20h], eax
0x18001149f  mov     [rsi+18h], rax
0x1800114a3  add     rsp, 28h
0x1800114a7  pop     rdi
0x1800114a8  pop     rsi
0x1800114a9  pop     rbp
0x1800114aa  pop     rbx
0x1800114ab  retn
```
