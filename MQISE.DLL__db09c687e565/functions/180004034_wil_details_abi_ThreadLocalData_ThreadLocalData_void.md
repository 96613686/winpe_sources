# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004034`
- end: `0x1800040b0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034bc`

## callees

- `0x180004034`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180004059`
- `KERNEL32!GetProcessHeap` at `0x18000408a`
- `KERNEL32!GetProcessHeap` at `0x180004059`
- `KERNEL32!GetProcessHeap` at `0x18000408a`
- `KERNEL32!HeapFree` at `0x180004067`
- `KERNEL32!HeapFree` at `0x180004098`
- `KERNEL32!HeapFree` at `0x180004067`
- `KERNEL32!HeapFree` at `0x180004098`

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
0x180004034  push    rbx
0x180004036  push    rbp
0x180004037  push    rsi
0x180004038  push    rdi
0x180004039  sub     rsp, 28h
0x18000403d  mov     rsi, rcx
0x180004040  mov     rdi, [rcx+18h]
0x180004044  movzx   eax, word ptr [rcx+20h]
0x180004048  lea     rbp, [rax+rax*4]
0x18000404c  shl     rbp, 4
0x180004050  add     rbp, rdi
0x180004053  jmp     short loc_180004081
0x180004055  mov     rbx, [rdi+40h]
0x180004059  call    cs:__imp_GetProcessHeap
0x18000405f  mov     r8, rbx; lpMem
0x180004062  xor     edx, edx; dwFlags
0x180004064  mov     rcx, rax; hHeap
0x180004067  call    cs:__imp_HeapFree
0x18000406d  mov     qword ptr [rdi+40h], 0
0x180004075  mov     qword ptr [rdi+48h], 0
0x18000407d  add     rdi, 50h ; 'P'
0x180004081  cmp     rdi, rbp
0x180004084  jnz     short loc_180004055
0x180004086  mov     rbx, [rsi+18h]
0x18000408a  call    cs:__imp_GetProcessHeap
0x180004090  mov     r8, rbx; lpMem
0x180004093  xor     edx, edx; dwFlags
0x180004095  mov     rcx, rax; hHeap
0x180004098  call    cs:__imp_HeapFree
0x18000409e  xor     eax, eax
0x1800040a0  mov     [rsi+20h], eax
0x1800040a3  mov     [rsi+18h], rax
0x1800040a7  add     rsp, 28h
0x1800040ab  pop     rdi
0x1800040ac  pop     rsi
0x1800040ad  pop     rbp
0x1800040ae  pop     rbx
0x1800040af  retn
```
