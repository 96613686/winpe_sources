# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003bc0`
- end: `0x140003c3c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003374`

## callees

- `0x140003bc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003bf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003bf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c16`

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
0x140003bc0  push    rbx
0x140003bc2  push    rbp
0x140003bc3  push    rsi
0x140003bc4  push    rdi
0x140003bc5  sub     rsp, 28h
0x140003bc9  movzx   eax, word ptr [rcx+20h]
0x140003bcd  mov     rsi, rcx
0x140003bd0  mov     rdi, [rcx+18h]
0x140003bd4  lea     rbp, [rax+rax*4]
0x140003bd8  shl     rbp, 4
0x140003bdc  add     rbp, rdi
0x140003bdf  jmp     short loc_140003C0D
0x140003be1  mov     rbx, [rdi+40h]
0x140003be5  call    cs:__imp_GetProcessHeap
0x140003beb  mov     r8, rbx; lpMem
0x140003bee  xor     edx, edx; dwFlags
0x140003bf0  mov     rcx, rax; hHeap
0x140003bf3  call    cs:__imp_HeapFree
0x140003bf9  mov     qword ptr [rdi+40h], 0
0x140003c01  mov     qword ptr [rdi+48h], 0
0x140003c09  add     rdi, 50h ; 'P'
0x140003c0d  cmp     rdi, rbp
0x140003c10  jnz     short loc_140003BE1
0x140003c12  mov     rbx, [rsi+18h]
0x140003c16  call    cs:__imp_GetProcessHeap
0x140003c1c  mov     r8, rbx; lpMem
0x140003c1f  xor     edx, edx; dwFlags
0x140003c21  mov     rcx, rax; hHeap
0x140003c24  call    cs:__imp_HeapFree
0x140003c2a  xor     eax, eax
0x140003c2c  mov     [rsi+20h], eax
0x140003c2f  mov     [rsi+18h], rax
0x140003c33  add     rsp, 28h
0x140003c37  pop     rdi
0x140003c38  pop     rsi
0x140003c39  pop     rbp
0x140003c3a  pop     rbx
0x140003c3b  retn
```
