# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18002f160`
- end: `0x18002f1f2`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800306f0`

## callees

- `0x18002f160`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002f1a5`
- `KERNEL32!HeapFree` at `0x18002f1d6`
- `KERNEL32!HeapFree` at `0x18002f1a5`
- `KERNEL32!HeapFree` at `0x18002f1d6`
- `KERNEL32!GetProcessHeap` at `0x18002f197`
- `KERNEL32!GetProcessHeap` at `0x18002f1c8`
- `KERNEL32!GetProcessHeap` at `0x18002f197`
- `KERNEL32!GetProcessHeap` at `0x18002f1c8`

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
0x18002f160  mov     [rsp+arg_10], rbx
0x18002f165  push    rbp
0x18002f166  push    rsi
0x18002f167  push    r14
0x18002f169  sub     rsp, 20h
0x18002f16d  mov     rbx, [rcx+18h]
0x18002f171  xor     r14d, r14d
0x18002f174  movzx   eax, word ptr [rcx+20h]
0x18002f178  mov     rbp, rcx
0x18002f17b  lea     rsi, [rax+rax*4]
0x18002f17f  shl     rsi, 4
0x18002f183  add     rsi, rbx
0x18002f186  cmp     rbx, rsi
0x18002f189  jz      short loc_18002F1C4
0x18002f18b  mov     [rsp+38h+arg_8], rdi
0x18002f190  add     rbx, 40h ; '@'
0x18002f194  mov     rdi, [rbx]
0x18002f197  call    cs:__imp_GetProcessHeap
0x18002f19d  mov     r8, rdi; lpMem
0x18002f1a0  xor     edx, edx; dwFlags
0x18002f1a2  mov     rcx, rax; hHeap
0x18002f1a5  call    cs:__imp_HeapFree
0x18002f1ab  mov     [rbx], r14
0x18002f1ae  mov     [rbx+8], r14
0x18002f1b2  lea     rbx, [rbx+50h]
0x18002f1b6  lea     rax, [rbx-40h]
0x18002f1ba  cmp     rax, rsi
0x18002f1bd  jnz     short loc_18002F194
0x18002f1bf  mov     rdi, [rsp+38h+arg_8]
0x18002f1c4  mov     rbx, [rbp+18h]
0x18002f1c8  call    cs:__imp_GetProcessHeap
0x18002f1ce  mov     r8, rbx; lpMem
0x18002f1d1  xor     edx, edx; dwFlags
0x18002f1d3  mov     rcx, rax; hHeap
0x18002f1d6  call    cs:__imp_HeapFree
0x18002f1dc  mov     rbx, [rsp+38h+arg_10]
0x18002f1e1  mov     [rbp+20h], r14d
0x18002f1e5  mov     [rbp+18h], r14
0x18002f1e9  add     rsp, 20h
0x18002f1ed  pop     r14
0x18002f1ef  pop     rsi
0x18002f1f0  pop     rbp
0x18002f1f1  retn
```
