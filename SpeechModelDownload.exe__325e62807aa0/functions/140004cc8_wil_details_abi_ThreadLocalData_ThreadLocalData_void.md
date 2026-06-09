# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140004cc8`
- end: `0x140004d44`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004a20`

## callees

- `0x140004cc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004ced`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004d1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004ced`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004d1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004cfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004d2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004cfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004d2c`

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
0x140004cc8  push    rbx
0x140004cca  push    rbp
0x140004ccb  push    rsi
0x140004ccc  push    rdi
0x140004ccd  sub     rsp, 28h
0x140004cd1  movzx   eax, word ptr [rcx+20h]
0x140004cd5  mov     rsi, rcx
0x140004cd8  mov     rdi, [rcx+18h]
0x140004cdc  lea     rbp, [rax+rax*4]
0x140004ce0  shl     rbp, 4
0x140004ce4  add     rbp, rdi
0x140004ce7  jmp     short loc_140004D15
0x140004ce9  mov     rbx, [rdi+40h]
0x140004ced  call    cs:__imp_GetProcessHeap
0x140004cf3  mov     r8, rbx; lpMem
0x140004cf6  xor     edx, edx; dwFlags
0x140004cf8  mov     rcx, rax; hHeap
0x140004cfb  call    cs:__imp_HeapFree
0x140004d01  mov     qword ptr [rdi+40h], 0
0x140004d09  mov     qword ptr [rdi+48h], 0
0x140004d11  add     rdi, 50h ; 'P'
0x140004d15  cmp     rdi, rbp
0x140004d18  jnz     short loc_140004CE9
0x140004d1a  mov     rbx, [rsi+18h]
0x140004d1e  call    cs:__imp_GetProcessHeap
0x140004d24  mov     r8, rbx; lpMem
0x140004d27  xor     edx, edx; dwFlags
0x140004d29  mov     rcx, rax; hHeap
0x140004d2c  call    cs:__imp_HeapFree
0x140004d32  xor     eax, eax
0x140004d34  mov     [rsi+20h], eax
0x140004d37  mov     [rsi+18h], rax
0x140004d3b  add     rsp, 28h
0x140004d3f  pop     rdi
0x140004d40  pop     rsi
0x140004d41  pop     rbp
0x140004d42  pop     rbx
0x140004d43  retn
```
