# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18000366c`
- end: `0x1800036e8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fe8`

## callees

- `0x18000366c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000369f`
- `KERNEL32!HeapFree` at `0x1800036d0`
- `KERNEL32!HeapFree` at `0x18000369f`
- `KERNEL32!HeapFree` at `0x1800036d0`
- `KERNEL32!GetProcessHeap` at `0x180003691`
- `KERNEL32!GetProcessHeap` at `0x1800036c2`
- `KERNEL32!GetProcessHeap` at `0x180003691`
- `KERNEL32!GetProcessHeap` at `0x1800036c2`

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
0x18000366c  push    rbx
0x18000366e  push    rbp
0x18000366f  push    rsi
0x180003670  push    rdi
0x180003671  sub     rsp, 28h
0x180003675  movzx   eax, word ptr [rcx+20h]
0x180003679  mov     rsi, rcx
0x18000367c  mov     rdi, [rcx+18h]
0x180003680  lea     rbp, [rax+rax*4]
0x180003684  shl     rbp, 4
0x180003688  add     rbp, rdi
0x18000368b  jmp     short loc_1800036B9
0x18000368d  mov     rbx, [rdi+40h]
0x180003691  call    cs:__imp_GetProcessHeap
0x180003697  mov     r8, rbx; lpMem
0x18000369a  xor     edx, edx; dwFlags
0x18000369c  mov     rcx, rax; hHeap
0x18000369f  call    cs:__imp_HeapFree
0x1800036a5  mov     qword ptr [rdi+40h], 0
0x1800036ad  mov     qword ptr [rdi+48h], 0
0x1800036b5  add     rdi, 50h ; 'P'
0x1800036b9  cmp     rdi, rbp
0x1800036bc  jnz     short loc_18000368D
0x1800036be  mov     rbx, [rsi+18h]
0x1800036c2  call    cs:__imp_GetProcessHeap
0x1800036c8  mov     r8, rbx; lpMem
0x1800036cb  xor     edx, edx; dwFlags
0x1800036cd  mov     rcx, rax; hHeap
0x1800036d0  call    cs:__imp_HeapFree
0x1800036d6  xor     eax, eax
0x1800036d8  mov     [rsi+20h], eax
0x1800036db  mov     [rsi+18h], rax
0x1800036df  add     rsp, 28h
0x1800036e3  pop     rdi
0x1800036e4  pop     rsi
0x1800036e5  pop     rbp
0x1800036e6  pop     rbx
0x1800036e7  retn
```
