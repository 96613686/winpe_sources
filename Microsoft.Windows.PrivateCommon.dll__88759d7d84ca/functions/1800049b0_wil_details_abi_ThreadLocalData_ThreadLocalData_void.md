# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800049b0`
- end: `0x180004a42`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c30`

## callees

- `0x1800049b0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800049f5`
- `KERNEL32!HeapFree` at `0x180004a26`
- `KERNEL32!HeapFree` at `0x1800049f5`
- `KERNEL32!HeapFree` at `0x180004a26`
- `KERNEL32!GetProcessHeap` at `0x1800049e7`
- `KERNEL32!GetProcessHeap` at `0x180004a18`
- `KERNEL32!GetProcessHeap` at `0x1800049e7`
- `KERNEL32!GetProcessHeap` at `0x180004a18`

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
0x1800049b0  mov     [rsp+arg_10], rbx
0x1800049b5  push    rbp
0x1800049b6  push    rsi
0x1800049b7  push    r14
0x1800049b9  sub     rsp, 20h
0x1800049bd  mov     rbx, [rcx+18h]
0x1800049c1  xor     r14d, r14d
0x1800049c4  movzx   eax, word ptr [rcx+20h]
0x1800049c8  mov     rbp, rcx
0x1800049cb  lea     rsi, [rax+rax*4]
0x1800049cf  shl     rsi, 4
0x1800049d3  add     rsi, rbx
0x1800049d6  cmp     rbx, rsi
0x1800049d9  jz      short loc_180004A14
0x1800049db  mov     [rsp+38h+arg_8], rdi
0x1800049e0  add     rbx, 40h ; '@'
0x1800049e4  mov     rdi, [rbx]
0x1800049e7  call    cs:__imp_GetProcessHeap
0x1800049ed  mov     r8, rdi; lpMem
0x1800049f0  xor     edx, edx; dwFlags
0x1800049f2  mov     rcx, rax; hHeap
0x1800049f5  call    cs:__imp_HeapFree
0x1800049fb  mov     [rbx], r14
0x1800049fe  mov     [rbx+8], r14
0x180004a02  lea     rbx, [rbx+50h]
0x180004a06  lea     rax, [rbx-40h]
0x180004a0a  cmp     rax, rsi
0x180004a0d  jnz     short loc_1800049E4
0x180004a0f  mov     rdi, [rsp+38h+arg_8]
0x180004a14  mov     rbx, [rbp+18h]
0x180004a18  call    cs:__imp_GetProcessHeap
0x180004a1e  mov     r8, rbx; lpMem
0x180004a21  xor     edx, edx; dwFlags
0x180004a23  mov     rcx, rax; hHeap
0x180004a26  call    cs:__imp_HeapFree
0x180004a2c  mov     rbx, [rsp+38h+arg_10]
0x180004a31  mov     [rbp+20h], r14d
0x180004a35  mov     [rbp+18h], r14
0x180004a39  add     rsp, 20h
0x180004a3d  pop     r14
0x180004a3f  pop     rsi
0x180004a40  pop     rbp
0x180004a41  retn
```
