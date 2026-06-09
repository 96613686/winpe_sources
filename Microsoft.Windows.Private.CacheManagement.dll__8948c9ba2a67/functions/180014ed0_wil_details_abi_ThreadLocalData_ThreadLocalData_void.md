# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180014ed0`
- end: `0x180014f62`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015f40`

## callees

- `0x180014ed0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180014f15`
- `KERNEL32!HeapFree` at `0x180014f46`
- `KERNEL32!HeapFree` at `0x180014f15`
- `KERNEL32!HeapFree` at `0x180014f46`
- `KERNEL32!GetProcessHeap` at `0x180014f07`
- `KERNEL32!GetProcessHeap` at `0x180014f38`
- `KERNEL32!GetProcessHeap` at `0x180014f07`
- `KERNEL32!GetProcessHeap` at `0x180014f38`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  __int64 v4; // rbx
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax

  v1 = *((_QWORD *)this + 3);
  v3 = v1 + 80LL * *((unsigned __int16 *)this + 16);
  if ( v1 != v3 )
  {
    v4 = v1 + 64;
    do
    {
      v5 = *(void **)v4;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      *(_QWORD *)v4 = 0;
      *(_QWORD *)(v4 + 8) = 0;
      v4 += 80;
    }
    while ( v4 - 64 != v3 );
  }
  v7 = (void *)*((_QWORD *)this + 3);
  v8 = GetProcessHeap();
  HeapFree(v8, 0, v7);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180014ed0  mov     [rsp+arg_10], rbx
0x180014ed5  push    rbp
0x180014ed6  push    rsi
0x180014ed7  push    r14
0x180014ed9  sub     rsp, 20h
0x180014edd  mov     rbx, [rcx+18h]
0x180014ee1  xor     r14d, r14d
0x180014ee4  movzx   eax, word ptr [rcx+20h]
0x180014ee8  mov     rbp, rcx
0x180014eeb  lea     rsi, [rax+rax*4]
0x180014eef  shl     rsi, 4
0x180014ef3  add     rsi, rbx
0x180014ef6  cmp     rbx, rsi
0x180014ef9  jz      short loc_180014F34
0x180014efb  mov     [rsp+38h+arg_8], rdi
0x180014f00  add     rbx, 40h ; '@'
0x180014f04  mov     rdi, [rbx]
0x180014f07  call    cs:__imp_GetProcessHeap
0x180014f0d  mov     r8, rdi; lpMem
0x180014f10  xor     edx, edx; dwFlags
0x180014f12  mov     rcx, rax; hHeap
0x180014f15  call    cs:__imp_HeapFree
0x180014f1b  mov     [rbx], r14
0x180014f1e  mov     [rbx+8], r14
0x180014f22  lea     rbx, [rbx+50h]
0x180014f26  lea     rax, [rbx-40h]
0x180014f2a  cmp     rax, rsi
0x180014f2d  jnz     short loc_180014F04
0x180014f2f  mov     rdi, [rsp+38h+arg_8]
0x180014f34  mov     rbx, [rbp+18h]
0x180014f38  call    cs:__imp_GetProcessHeap
0x180014f3e  mov     r8, rbx; lpMem
0x180014f41  xor     edx, edx; dwFlags
0x180014f43  mov     rcx, rax; hHeap
0x180014f46  call    cs:__imp_HeapFree
0x180014f4c  mov     rbx, [rsp+38h+arg_10]
0x180014f51  mov     [rbp+20h], r14d
0x180014f55  mov     [rbp+18h], r14
0x180014f59  add     rsp, 20h
0x180014f5d  pop     r14
0x180014f5f  pop     rsi
0x180014f60  pop     rbp
0x180014f61  retn
```
