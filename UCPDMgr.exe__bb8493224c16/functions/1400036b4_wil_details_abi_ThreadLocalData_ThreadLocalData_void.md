# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400036b4`
- end: `0x140003746`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005e1c`

## callees

- `0x1400036b4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400036f9`
- `KERNEL32!HeapFree` at `0x140003725`
- `KERNEL32!HeapFree` at `0x1400036f9`
- `KERNEL32!HeapFree` at `0x140003725`
- `KERNEL32!GetProcessHeap` at `0x1400036eb`
- `KERNEL32!GetProcessHeap` at `0x140003717`
- `KERNEL32!GetProcessHeap` at `0x1400036eb`
- `KERNEL32!GetProcessHeap` at `0x140003717`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rdi
  __int64 v3; // rbp
  __int64 v4; // rdi
  void *v5; // rbx
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
0x1400036b4  mov     [rsp+arg_8], rbx
0x1400036b9  mov     [rsp+arg_10], rbp
0x1400036be  push    rsi
0x1400036bf  push    rdi
0x1400036c0  push    r14
0x1400036c2  sub     rsp, 20h
0x1400036c6  mov     rdi, [rcx+18h]
0x1400036ca  xor     r14d, r14d
0x1400036cd  movzx   eax, word ptr [rcx+20h]
0x1400036d1  mov     rsi, rcx
0x1400036d4  lea     rbp, [rax+rax*4]
0x1400036d8  shl     rbp, 4
0x1400036dc  add     rbp, rdi
0x1400036df  cmp     rdi, rbp
0x1400036e2  jz      short loc_140003713
0x1400036e4  add     rdi, 40h ; '@'
0x1400036e8  mov     rbx, [rdi]
0x1400036eb  call    cs:__imp_GetProcessHeap
0x1400036f1  mov     r8, rbx; lpMem
0x1400036f4  xor     edx, edx; dwFlags
0x1400036f6  mov     rcx, rax; hHeap
0x1400036f9  call    cs:__imp_HeapFree
0x1400036ff  mov     [rdi], r14
0x140003702  mov     [rdi+8], r14
0x140003706  lea     rdi, [rdi+50h]
0x14000370a  lea     rax, [rdi-40h]
0x14000370e  cmp     rax, rbp
0x140003711  jnz     short loc_1400036E8
0x140003713  mov     rbx, [rsi+18h]
0x140003717  call    cs:__imp_GetProcessHeap
0x14000371d  mov     r8, rbx; lpMem
0x140003720  xor     edx, edx; dwFlags
0x140003722  mov     rcx, rax; hHeap
0x140003725  call    cs:__imp_HeapFree
0x14000372b  mov     rbx, [rsp+38h+arg_8]
0x140003730  mov     rbp, [rsp+38h+arg_10]
0x140003735  mov     [rsi+20h], r14d
0x140003739  mov     [rsi+18h], r14
0x14000373d  add     rsp, 20h
0x140003741  pop     r14
0x140003743  pop     rdi
0x140003744  pop     rsi
0x140003745  retn
```
