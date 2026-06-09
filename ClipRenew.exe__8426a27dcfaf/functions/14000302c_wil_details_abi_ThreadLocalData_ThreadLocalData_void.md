# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x14000302c`
- end: `0x1400030a8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f60`

## callees

- `0x14000302c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003082`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003082`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000305f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003090`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000305f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003090`

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
0x14000302c  push    rbx
0x14000302e  push    rbp
0x14000302f  push    rsi
0x140003030  push    rdi
0x140003031  sub     rsp, 28h
0x140003035  movzx   eax, word ptr [rcx+20h]
0x140003039  mov     rsi, rcx
0x14000303c  mov     rdi, [rcx+18h]
0x140003040  lea     rbp, [rax+rax*4]
0x140003044  shl     rbp, 4
0x140003048  add     rbp, rdi
0x14000304b  jmp     short loc_140003079
0x14000304d  mov     rbx, [rdi+40h]
0x140003051  call    cs:__imp_GetProcessHeap
0x140003057  mov     r8, rbx; lpMem
0x14000305a  xor     edx, edx; dwFlags
0x14000305c  mov     rcx, rax; hHeap
0x14000305f  call    cs:__imp_HeapFree
0x140003065  mov     qword ptr [rdi+40h], 0
0x14000306d  mov     qword ptr [rdi+48h], 0
0x140003075  add     rdi, 50h ; 'P'
0x140003079  cmp     rdi, rbp
0x14000307c  jnz     short loc_14000304D
0x14000307e  mov     rbx, [rsi+18h]
0x140003082  call    cs:__imp_GetProcessHeap
0x140003088  mov     r8, rbx; lpMem
0x14000308b  xor     edx, edx; dwFlags
0x14000308d  mov     rcx, rax; hHeap
0x140003090  call    cs:__imp_HeapFree
0x140003096  xor     eax, eax
0x140003098  mov     [rsi+20h], eax
0x14000309b  mov     [rsi+18h], rax
0x14000309f  add     rsp, 28h
0x1400030a3  pop     rdi
0x1400030a4  pop     rsi
0x1400030a5  pop     rbp
0x1400030a6  pop     rbx
0x1400030a7  retn
```
