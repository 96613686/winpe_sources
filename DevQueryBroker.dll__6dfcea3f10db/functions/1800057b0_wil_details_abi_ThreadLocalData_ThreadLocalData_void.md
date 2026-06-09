# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800057b0`
- end: `0x18000582c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005324`

## callees

- `0x1800057b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005814`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005806`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005806`

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
0x1800057b0  push    rbx
0x1800057b2  push    rbp
0x1800057b3  push    rsi
0x1800057b4  push    rdi
0x1800057b5  sub     rsp, 28h
0x1800057b9  movzx   eax, word ptr [rcx+20h]
0x1800057bd  mov     rsi, rcx
0x1800057c0  mov     rdi, [rcx+18h]
0x1800057c4  lea     rbp, [rax+rax*4]
0x1800057c8  shl     rbp, 4
0x1800057cc  add     rbp, rdi
0x1800057cf  jmp     short loc_1800057FD
0x1800057d1  mov     rbx, [rdi+40h]
0x1800057d5  call    cs:__imp_GetProcessHeap
0x1800057db  mov     r8, rbx; lpMem
0x1800057de  xor     edx, edx; dwFlags
0x1800057e0  mov     rcx, rax; hHeap
0x1800057e3  call    cs:__imp_HeapFree
0x1800057e9  mov     qword ptr [rdi+40h], 0
0x1800057f1  mov     qword ptr [rdi+48h], 0
0x1800057f9  add     rdi, 50h ; 'P'
0x1800057fd  cmp     rdi, rbp
0x180005800  jnz     short loc_1800057D1
0x180005802  mov     rbx, [rsi+18h]
0x180005806  call    cs:__imp_GetProcessHeap
0x18000580c  mov     r8, rbx; lpMem
0x18000580f  xor     edx, edx; dwFlags
0x180005811  mov     rcx, rax; hHeap
0x180005814  call    cs:__imp_HeapFree
0x18000581a  xor     eax, eax
0x18000581c  mov     [rsi+20h], eax
0x18000581f  mov     [rsi+18h], rax
0x180005823  add     rsp, 28h
0x180005827  pop     rdi
0x180005828  pop     rsi
0x180005829  pop     rbp
0x18000582a  pop     rbx
0x18000582b  retn
```
