# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800037e0`
- end: `0x18000385c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003208`

## callees

- `0x1800037e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003813`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003844`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003813`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003844`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003836`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003836`

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
0x1800037e0  push    rbx
0x1800037e2  push    rbp
0x1800037e3  push    rsi
0x1800037e4  push    rdi
0x1800037e5  sub     rsp, 28h
0x1800037e9  movzx   eax, word ptr [rcx+20h]
0x1800037ed  mov     rsi, rcx
0x1800037f0  mov     rdi, [rcx+18h]
0x1800037f4  lea     rbp, [rax+rax*4]
0x1800037f8  shl     rbp, 4
0x1800037fc  add     rbp, rdi
0x1800037ff  jmp     short loc_18000382D
0x180003801  mov     rbx, [rdi+40h]
0x180003805  call    cs:__imp_GetProcessHeap
0x18000380b  mov     r8, rbx; lpMem
0x18000380e  xor     edx, edx; dwFlags
0x180003810  mov     rcx, rax; hHeap
0x180003813  call    cs:__imp_HeapFree
0x180003819  mov     qword ptr [rdi+40h], 0
0x180003821  mov     qword ptr [rdi+48h], 0
0x180003829  add     rdi, 50h ; 'P'
0x18000382d  cmp     rdi, rbp
0x180003830  jnz     short loc_180003801
0x180003832  mov     rbx, [rsi+18h]
0x180003836  call    cs:__imp_GetProcessHeap
0x18000383c  mov     r8, rbx; lpMem
0x18000383f  xor     edx, edx; dwFlags
0x180003841  mov     rcx, rax; hHeap
0x180003844  call    cs:__imp_HeapFree
0x18000384a  xor     eax, eax
0x18000384c  mov     [rsi+20h], eax
0x18000384f  mov     [rsi+18h], rax
0x180003853  add     rsp, 28h
0x180003857  pop     rdi
0x180003858  pop     rsi
0x180003859  pop     rbp
0x18000385a  pop     rbx
0x18000385b  retn
```
