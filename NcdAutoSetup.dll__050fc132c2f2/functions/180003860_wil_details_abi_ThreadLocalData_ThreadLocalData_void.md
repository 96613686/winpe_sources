# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003860`
- end: `0x1800038dc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000322c`

## callees

- `0x180003860`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003893`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003893`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038b6`

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
0x180003860  push    rbx
0x180003862  push    rbp
0x180003863  push    rsi
0x180003864  push    rdi
0x180003865  sub     rsp, 28h
0x180003869  movzx   eax, word ptr [rcx+20h]
0x18000386d  mov     rsi, rcx
0x180003870  mov     rdi, [rcx+18h]
0x180003874  lea     rbp, [rax+rax*4]
0x180003878  shl     rbp, 4
0x18000387c  add     rbp, rdi
0x18000387f  jmp     short loc_1800038AD
0x180003881  mov     rbx, [rdi+40h]
0x180003885  call    cs:__imp_GetProcessHeap
0x18000388b  mov     r8, rbx; lpMem
0x18000388e  xor     edx, edx; dwFlags
0x180003890  mov     rcx, rax; hHeap
0x180003893  call    cs:__imp_HeapFree
0x180003899  mov     qword ptr [rdi+40h], 0
0x1800038a1  mov     qword ptr [rdi+48h], 0
0x1800038a9  add     rdi, 50h ; 'P'
0x1800038ad  cmp     rdi, rbp
0x1800038b0  jnz     short loc_180003881
0x1800038b2  mov     rbx, [rsi+18h]
0x1800038b6  call    cs:__imp_GetProcessHeap
0x1800038bc  mov     r8, rbx; lpMem
0x1800038bf  xor     edx, edx; dwFlags
0x1800038c1  mov     rcx, rax; hHeap
0x1800038c4  call    cs:__imp_HeapFree
0x1800038ca  xor     eax, eax
0x1800038cc  mov     [rsi+20h], eax
0x1800038cf  mov     [rsi+18h], rax
0x1800038d3  add     rsp, 28h
0x1800038d7  pop     rdi
0x1800038d8  pop     rsi
0x1800038d9  pop     rbp
0x1800038da  pop     rbx
0x1800038db  retn
```
