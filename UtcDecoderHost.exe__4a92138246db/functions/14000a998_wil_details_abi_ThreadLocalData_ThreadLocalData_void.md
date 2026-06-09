# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x14000a998`
- end: `0x14000aa14`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a700`

## callees

- `0x14000a998`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a9cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a9fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a9cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a9fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a9bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a9ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a9bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a9ee`

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
0x14000a998  push    rbx
0x14000a99a  push    rbp
0x14000a99b  push    rsi
0x14000a99c  push    rdi
0x14000a99d  sub     rsp, 28h
0x14000a9a1  movzx   eax, word ptr [rcx+20h]
0x14000a9a5  mov     rsi, rcx
0x14000a9a8  mov     rdi, [rcx+18h]
0x14000a9ac  lea     rbp, [rax+rax*4]
0x14000a9b0  shl     rbp, 4
0x14000a9b4  add     rbp, rdi
0x14000a9b7  jmp     short loc_14000A9E5
0x14000a9b9  mov     rbx, [rdi+40h]
0x14000a9bd  call    cs:__imp_GetProcessHeap
0x14000a9c3  mov     r8, rbx; lpMem
0x14000a9c6  xor     edx, edx; dwFlags
0x14000a9c8  mov     rcx, rax; hHeap
0x14000a9cb  call    cs:__imp_HeapFree
0x14000a9d1  mov     qword ptr [rdi+40h], 0
0x14000a9d9  mov     qword ptr [rdi+48h], 0
0x14000a9e1  add     rdi, 50h ; 'P'
0x14000a9e5  cmp     rdi, rbp
0x14000a9e8  jnz     short loc_14000A9B9
0x14000a9ea  mov     rbx, [rsi+18h]
0x14000a9ee  call    cs:__imp_GetProcessHeap
0x14000a9f4  mov     r8, rbx; lpMem
0x14000a9f7  xor     edx, edx; dwFlags
0x14000a9f9  mov     rcx, rax; hHeap
0x14000a9fc  call    cs:__imp_HeapFree
0x14000aa02  xor     eax, eax
0x14000aa04  mov     [rsi+20h], eax
0x14000aa07  mov     [rsi+18h], rax
0x14000aa0b  add     rsp, 28h
0x14000aa0f  pop     rdi
0x14000aa10  pop     rsi
0x14000aa11  pop     rbp
0x14000aa12  pop     rbx
0x14000aa13  retn
```
