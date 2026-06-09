# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180011358`
- end: `0x1800113d4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001128c`

## callees

- `0x180011358`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001137d`
- `KERNEL32!GetProcessHeap` at `0x1800113ae`
- `KERNEL32!GetProcessHeap` at `0x18001137d`
- `KERNEL32!GetProcessHeap` at `0x1800113ae`
- `KERNEL32!HeapFree` at `0x18001138b`
- `KERNEL32!HeapFree` at `0x1800113bc`
- `KERNEL32!HeapFree` at `0x18001138b`
- `KERNEL32!HeapFree` at `0x1800113bc`

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
0x180011358  push    rbx
0x18001135a  push    rbp
0x18001135b  push    rsi
0x18001135c  push    rdi
0x18001135d  sub     rsp, 28h
0x180011361  movzx   eax, word ptr [rcx+20h]
0x180011365  mov     rsi, rcx
0x180011368  mov     rdi, [rcx+18h]
0x18001136c  lea     rbp, [rax+rax*4]
0x180011370  shl     rbp, 4
0x180011374  add     rbp, rdi
0x180011377  jmp     short loc_1800113A5
0x180011379  mov     rbx, [rdi+40h]
0x18001137d  call    cs:__imp_GetProcessHeap
0x180011383  mov     r8, rbx; lpMem
0x180011386  xor     edx, edx; dwFlags
0x180011388  mov     rcx, rax; hHeap
0x18001138b  call    cs:__imp_HeapFree
0x180011391  mov     qword ptr [rdi+40h], 0
0x180011399  mov     qword ptr [rdi+48h], 0
0x1800113a1  add     rdi, 50h ; 'P'
0x1800113a5  cmp     rdi, rbp
0x1800113a8  jnz     short loc_180011379
0x1800113aa  mov     rbx, [rsi+18h]
0x1800113ae  call    cs:__imp_GetProcessHeap
0x1800113b4  mov     r8, rbx; lpMem
0x1800113b7  xor     edx, edx; dwFlags
0x1800113b9  mov     rcx, rax; hHeap
0x1800113bc  call    cs:__imp_HeapFree
0x1800113c2  xor     eax, eax
0x1800113c4  mov     [rsi+20h], eax
0x1800113c7  mov     [rsi+18h], rax
0x1800113cb  add     rsp, 28h
0x1800113cf  pop     rdi
0x1800113d0  pop     rsi
0x1800113d1  pop     rbp
0x1800113d2  pop     rbx
0x1800113d3  retn
```
