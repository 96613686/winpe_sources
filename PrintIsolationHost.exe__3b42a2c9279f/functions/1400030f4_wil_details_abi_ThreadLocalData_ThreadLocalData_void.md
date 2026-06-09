# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400030f4`
- end: `0x140003170`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003028`

## callees

- `0x1400030f4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003127`
- `KERNEL32!HeapFree` at `0x140003158`
- `KERNEL32!HeapFree` at `0x140003127`
- `KERNEL32!HeapFree` at `0x140003158`
- `KERNEL32!GetProcessHeap` at `0x140003119`
- `KERNEL32!GetProcessHeap` at `0x14000314a`
- `KERNEL32!GetProcessHeap` at `0x140003119`
- `KERNEL32!GetProcessHeap` at `0x14000314a`

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
0x1400030f4  push    rbx
0x1400030f6  push    rbp
0x1400030f7  push    rsi
0x1400030f8  push    rdi
0x1400030f9  sub     rsp, 28h
0x1400030fd  movzx   eax, word ptr [rcx+20h]
0x140003101  mov     rsi, rcx
0x140003104  mov     rdi, [rcx+18h]
0x140003108  lea     rbp, [rax+rax*4]
0x14000310c  shl     rbp, 4
0x140003110  add     rbp, rdi
0x140003113  jmp     short loc_140003141
0x140003115  mov     rbx, [rdi+40h]
0x140003119  call    cs:__imp_GetProcessHeap
0x14000311f  mov     r8, rbx; lpMem
0x140003122  xor     edx, edx; dwFlags
0x140003124  mov     rcx, rax; hHeap
0x140003127  call    cs:__imp_HeapFree
0x14000312d  mov     qword ptr [rdi+40h], 0
0x140003135  mov     qword ptr [rdi+48h], 0
0x14000313d  add     rdi, 50h ; 'P'
0x140003141  cmp     rdi, rbp
0x140003144  jnz     short loc_140003115
0x140003146  mov     rbx, [rsi+18h]
0x14000314a  call    cs:__imp_GetProcessHeap
0x140003150  mov     r8, rbx; lpMem
0x140003153  xor     edx, edx; dwFlags
0x140003155  mov     rcx, rax; hHeap
0x140003158  call    cs:__imp_HeapFree
0x14000315e  xor     eax, eax
0x140003160  mov     [rsi+20h], eax
0x140003163  mov     [rsi+18h], rax
0x140003167  add     rsp, 28h
0x14000316b  pop     rdi
0x14000316c  pop     rsi
0x14000316d  pop     rbp
0x14000316e  pop     rbx
0x14000316f  retn
```
