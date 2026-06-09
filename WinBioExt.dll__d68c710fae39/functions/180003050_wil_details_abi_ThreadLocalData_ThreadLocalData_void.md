# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003050`
- end: `0x1800030cc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e98`

## callees

- `0x180003050`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003075`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003075`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003083`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003083`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030b4`

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
0x180003050  push    rbx
0x180003052  push    rbp
0x180003053  push    rsi
0x180003054  push    rdi
0x180003055  sub     rsp, 28h
0x180003059  movzx   eax, word ptr [rcx+20h]
0x18000305d  mov     rsi, rcx
0x180003060  mov     rdi, [rcx+18h]
0x180003064  lea     rbp, [rax+rax*4]
0x180003068  shl     rbp, 4
0x18000306c  add     rbp, rdi
0x18000306f  jmp     short loc_18000309D
0x180003071  mov     rbx, [rdi+40h]
0x180003075  call    cs:__imp_GetProcessHeap
0x18000307b  mov     r8, rbx; lpMem
0x18000307e  xor     edx, edx; dwFlags
0x180003080  mov     rcx, rax; hHeap
0x180003083  call    cs:__imp_HeapFree
0x180003089  mov     qword ptr [rdi+40h], 0
0x180003091  mov     qword ptr [rdi+48h], 0
0x180003099  add     rdi, 50h ; 'P'
0x18000309d  cmp     rdi, rbp
0x1800030a0  jnz     short loc_180003071
0x1800030a2  mov     rbx, [rsi+18h]
0x1800030a6  call    cs:__imp_GetProcessHeap
0x1800030ac  mov     r8, rbx; lpMem
0x1800030af  xor     edx, edx; dwFlags
0x1800030b1  mov     rcx, rax; hHeap
0x1800030b4  call    cs:__imp_HeapFree
0x1800030ba  xor     eax, eax
0x1800030bc  mov     [rsi+20h], eax
0x1800030bf  mov     [rsi+18h], rax
0x1800030c3  add     rsp, 28h
0x1800030c7  pop     rdi
0x1800030c8  pop     rsi
0x1800030c9  pop     rbp
0x1800030ca  pop     rbx
0x1800030cb  retn
```
