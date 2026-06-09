# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003cc8`
- end: `0x180003d44`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003594`

## callees

- `0x180003cc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ced`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ced`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d1e`

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
0x180003cc8  push    rbx
0x180003cca  push    rbp
0x180003ccb  push    rsi
0x180003ccc  push    rdi
0x180003ccd  sub     rsp, 28h
0x180003cd1  movzx   eax, word ptr [rcx+20h]
0x180003cd5  mov     rsi, rcx
0x180003cd8  mov     rdi, [rcx+18h]
0x180003cdc  lea     rbp, [rax+rax*4]
0x180003ce0  shl     rbp, 4
0x180003ce4  add     rbp, rdi
0x180003ce7  jmp     short loc_180003D15
0x180003ce9  mov     rbx, [rdi+40h]
0x180003ced  call    cs:__imp_GetProcessHeap
0x180003cf3  mov     r8, rbx; lpMem
0x180003cf6  xor     edx, edx; dwFlags
0x180003cf8  mov     rcx, rax; hHeap
0x180003cfb  call    cs:__imp_HeapFree
0x180003d01  mov     qword ptr [rdi+40h], 0
0x180003d09  mov     qword ptr [rdi+48h], 0
0x180003d11  add     rdi, 50h ; 'P'
0x180003d15  cmp     rdi, rbp
0x180003d18  jnz     short loc_180003CE9
0x180003d1a  mov     rbx, [rsi+18h]
0x180003d1e  call    cs:__imp_GetProcessHeap
0x180003d24  mov     r8, rbx; lpMem
0x180003d27  xor     edx, edx; dwFlags
0x180003d29  mov     rcx, rax; hHeap
0x180003d2c  call    cs:__imp_HeapFree
0x180003d32  xor     eax, eax
0x180003d34  mov     [rsi+20h], eax
0x180003d37  mov     [rsi+18h], rax
0x180003d3b  add     rsp, 28h
0x180003d3f  pop     rdi
0x180003d40  pop     rsi
0x180003d41  pop     rbp
0x180003d42  pop     rbx
0x180003d43  retn
```
