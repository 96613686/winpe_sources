# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400037d8`
- end: `0x140003854`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031f4`

## callees

- `0x1400037d8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000380b`
- `KERNEL32!HeapFree` at `0x14000383c`
- `KERNEL32!HeapFree` at `0x14000380b`
- `KERNEL32!HeapFree` at `0x14000383c`
- `KERNEL32!GetProcessHeap` at `0x1400037fd`
- `KERNEL32!GetProcessHeap` at `0x14000382e`
- `KERNEL32!GetProcessHeap` at `0x1400037fd`
- `KERNEL32!GetProcessHeap` at `0x14000382e`

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
0x1400037d8  push    rbx
0x1400037da  push    rbp
0x1400037db  push    rsi
0x1400037dc  push    rdi
0x1400037dd  sub     rsp, 28h
0x1400037e1  movzx   eax, word ptr [rcx+20h]
0x1400037e5  mov     rsi, rcx
0x1400037e8  mov     rdi, [rcx+18h]
0x1400037ec  lea     rbp, [rax+rax*4]
0x1400037f0  shl     rbp, 4
0x1400037f4  add     rbp, rdi
0x1400037f7  jmp     short loc_140003825
0x1400037f9  mov     rbx, [rdi+40h]
0x1400037fd  call    cs:__imp_GetProcessHeap
0x140003803  mov     r8, rbx; lpMem
0x140003806  xor     edx, edx; dwFlags
0x140003808  mov     rcx, rax; hHeap
0x14000380b  call    cs:__imp_HeapFree
0x140003811  mov     qword ptr [rdi+40h], 0
0x140003819  mov     qword ptr [rdi+48h], 0
0x140003821  add     rdi, 50h ; 'P'
0x140003825  cmp     rdi, rbp
0x140003828  jnz     short loc_1400037F9
0x14000382a  mov     rbx, [rsi+18h]
0x14000382e  call    cs:__imp_GetProcessHeap
0x140003834  mov     r8, rbx; lpMem
0x140003837  xor     edx, edx; dwFlags
0x140003839  mov     rcx, rax; hHeap
0x14000383c  call    cs:__imp_HeapFree
0x140003842  xor     eax, eax
0x140003844  mov     [rsi+20h], eax
0x140003847  mov     [rsi+18h], rax
0x14000384b  add     rsp, 28h
0x14000384f  pop     rdi
0x140003850  pop     rsi
0x140003851  pop     rbp
0x140003852  pop     rbx
0x140003853  retn
```
