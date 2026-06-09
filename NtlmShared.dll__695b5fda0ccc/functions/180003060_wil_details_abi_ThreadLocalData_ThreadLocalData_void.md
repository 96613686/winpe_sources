# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003060`
- end: `0x1800030dc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a88`

## callees

- `0x180003060`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003093`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003093`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030b6`

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
0x180003060  push    rbx
0x180003062  push    rbp
0x180003063  push    rsi
0x180003064  push    rdi
0x180003065  sub     rsp, 28h
0x180003069  movzx   eax, word ptr [rcx+20h]
0x18000306d  mov     rsi, rcx
0x180003070  mov     rdi, [rcx+18h]
0x180003074  lea     rbp, [rax+rax*4]
0x180003078  shl     rbp, 4
0x18000307c  add     rbp, rdi
0x18000307f  jmp     short loc_1800030AD
0x180003081  mov     rbx, [rdi+40h]
0x180003085  call    cs:__imp_GetProcessHeap
0x18000308b  mov     r8, rbx; lpMem
0x18000308e  xor     edx, edx; dwFlags
0x180003090  mov     rcx, rax; hHeap
0x180003093  call    cs:__imp_HeapFree
0x180003099  mov     qword ptr [rdi+40h], 0
0x1800030a1  mov     qword ptr [rdi+48h], 0
0x1800030a9  add     rdi, 50h ; 'P'
0x1800030ad  cmp     rdi, rbp
0x1800030b0  jnz     short loc_180003081
0x1800030b2  mov     rbx, [rsi+18h]
0x1800030b6  call    cs:__imp_GetProcessHeap
0x1800030bc  mov     r8, rbx; lpMem
0x1800030bf  xor     edx, edx; dwFlags
0x1800030c1  mov     rcx, rax; hHeap
0x1800030c4  call    cs:__imp_HeapFree
0x1800030ca  xor     eax, eax
0x1800030cc  mov     [rsi+20h], eax
0x1800030cf  mov     [rsi+18h], rax
0x1800030d3  add     rsp, 28h
0x1800030d7  pop     rdi
0x1800030d8  pop     rsi
0x1800030d9  pop     rbp
0x1800030da  pop     rbx
0x1800030db  retn
```
