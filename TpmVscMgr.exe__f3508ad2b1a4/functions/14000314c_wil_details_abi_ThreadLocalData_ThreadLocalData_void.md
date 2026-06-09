# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x14000314c`
- end: `0x1400031c8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f94`

## callees

- `0x14000314c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000317f`
- `KERNEL32!HeapFree` at `0x1400031b0`
- `KERNEL32!HeapFree` at `0x14000317f`
- `KERNEL32!HeapFree` at `0x1400031b0`
- `KERNEL32!GetProcessHeap` at `0x140003171`
- `KERNEL32!GetProcessHeap` at `0x1400031a2`
- `KERNEL32!GetProcessHeap` at `0x140003171`
- `KERNEL32!GetProcessHeap` at `0x1400031a2`

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
0x14000314c  push    rbx
0x14000314e  push    rbp
0x14000314f  push    rsi
0x140003150  push    rdi
0x140003151  sub     rsp, 28h
0x140003155  movzx   eax, word ptr [rcx+20h]
0x140003159  mov     rsi, rcx
0x14000315c  mov     rdi, [rcx+18h]
0x140003160  lea     rbp, [rax+rax*4]
0x140003164  shl     rbp, 4
0x140003168  add     rbp, rdi
0x14000316b  jmp     short loc_140003199
0x14000316d  mov     rbx, [rdi+40h]
0x140003171  call    cs:__imp_GetProcessHeap
0x140003177  mov     r8, rbx; lpMem
0x14000317a  xor     edx, edx; dwFlags
0x14000317c  mov     rcx, rax; hHeap
0x14000317f  call    cs:__imp_HeapFree
0x140003185  mov     qword ptr [rdi+40h], 0
0x14000318d  mov     qword ptr [rdi+48h], 0
0x140003195  add     rdi, 50h ; 'P'
0x140003199  cmp     rdi, rbp
0x14000319c  jnz     short loc_14000316D
0x14000319e  mov     rbx, [rsi+18h]
0x1400031a2  call    cs:__imp_GetProcessHeap
0x1400031a8  mov     r8, rbx; lpMem
0x1400031ab  xor     edx, edx; dwFlags
0x1400031ad  mov     rcx, rax; hHeap
0x1400031b0  call    cs:__imp_HeapFree
0x1400031b6  xor     eax, eax
0x1400031b8  mov     [rsi+20h], eax
0x1400031bb  mov     [rsi+18h], rax
0x1400031bf  add     rsp, 28h
0x1400031c3  pop     rdi
0x1400031c4  pop     rsi
0x1400031c5  pop     rbp
0x1400031c6  pop     rbx
0x1400031c7  retn
```
