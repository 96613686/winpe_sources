# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400037e0`
- end: `0x14000385c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030ac`

## callees

- `0x1400037e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003836`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003836`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003813`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003844`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003813`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003844`

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
0x1400037e0  push    rbx
0x1400037e2  push    rbp
0x1400037e3  push    rsi
0x1400037e4  push    rdi
0x1400037e5  sub     rsp, 28h
0x1400037e9  movzx   eax, word ptr [rcx+20h]
0x1400037ed  mov     rsi, rcx
0x1400037f0  mov     rdi, [rcx+18h]
0x1400037f4  lea     rbp, [rax+rax*4]
0x1400037f8  shl     rbp, 4
0x1400037fc  add     rbp, rdi
0x1400037ff  jmp     short loc_14000382D
0x140003801  mov     rbx, [rdi+40h]
0x140003805  call    cs:__imp_GetProcessHeap
0x14000380b  mov     r8, rbx; lpMem
0x14000380e  xor     edx, edx; dwFlags
0x140003810  mov     rcx, rax; hHeap
0x140003813  call    cs:__imp_HeapFree
0x140003819  mov     qword ptr [rdi+40h], 0
0x140003821  mov     qword ptr [rdi+48h], 0
0x140003829  add     rdi, 50h ; 'P'
0x14000382d  cmp     rdi, rbp
0x140003830  jnz     short loc_140003801
0x140003832  mov     rbx, [rsi+18h]
0x140003836  call    cs:__imp_GetProcessHeap
0x14000383c  mov     r8, rbx; lpMem
0x14000383f  xor     edx, edx; dwFlags
0x140003841  mov     rcx, rax; hHeap
0x140003844  call    cs:__imp_HeapFree
0x14000384a  xor     eax, eax
0x14000384c  mov     [rsi+20h], eax
0x14000384f  mov     [rsi+18h], rax
0x140003853  add     rsp, 28h
0x140003857  pop     rdi
0x140003858  pop     rsi
0x140003859  pop     rbp
0x14000385a  pop     rbx
0x14000385b  retn
```
