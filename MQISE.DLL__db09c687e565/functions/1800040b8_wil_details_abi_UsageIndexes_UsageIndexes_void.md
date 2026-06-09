# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800040b8`
- end: `0x180004148`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bd8`
- `0x180008900`
- `0x1800093d8`
- `0x18000fbe6`

## callees

- `0x1800040b8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800040dc`
- `KERNEL32!GetProcessHeap` at `0x180004102`
- `KERNEL32!GetProcessHeap` at `0x180004128`
- `KERNEL32!GetProcessHeap` at `0x1800040dc`
- `KERNEL32!GetProcessHeap` at `0x180004102`
- `KERNEL32!GetProcessHeap` at `0x180004128`
- `KERNEL32!HeapFree` at `0x1800040ea`
- `KERNEL32!HeapFree` at `0x180004110`
- `KERNEL32!HeapFree` at `0x180004136`
- `KERNEL32!HeapFree` at `0x1800040ea`
- `KERNEL32!HeapFree` at `0x180004110`
- `KERNEL32!HeapFree` at `0x180004136`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v2 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
}

```

## disassembly

```asm
0x1800040b8  mov     [rsp+arg_0], rbx
0x1800040bd  push    rdi
0x1800040be  sub     rsp, 20h
0x1800040c2  mov     rbx, rcx
0x1800040c5  mov     rdi, [rcx+0B0h]
0x1800040cc  mov     qword ptr [rcx+0B0h], 0
0x1800040d7  test    rdi, rdi
0x1800040da  jz      short loc_1800040F1
0x1800040dc  call    cs:__imp_GetProcessHeap
0x1800040e2  mov     rcx, rax; hHeap
0x1800040e5  mov     r8, rdi; lpMem
0x1800040e8  xor     edx, edx; dwFlags
0x1800040ea  call    cs:__imp_HeapFree
0x1800040f0  nop
0x1800040f1  mov     rdi, [rbx+70h]
0x1800040f5  mov     qword ptr [rbx+70h], 0
0x1800040fd  test    rdi, rdi
0x180004100  jz      short loc_180004117
0x180004102  call    cs:__imp_GetProcessHeap
0x180004108  mov     rcx, rax; hHeap
0x18000410b  mov     r8, rdi; lpMem
0x18000410e  xor     edx, edx; dwFlags
0x180004110  call    cs:__imp_HeapFree
0x180004116  nop
0x180004117  mov     rdi, [rbx+30h]
0x18000411b  mov     qword ptr [rbx+30h], 0
0x180004123  test    rdi, rdi
0x180004126  jz      short loc_18000413D
0x180004128  call    cs:__imp_GetProcessHeap
0x18000412e  mov     rcx, rax; hHeap
0x180004131  mov     r8, rdi; lpMem
0x180004134  xor     edx, edx; dwFlags
0x180004136  call    cs:__imp_HeapFree
0x18000413c  nop
0x18000413d  mov     rbx, [rsp+28h+arg_0]
0x180004142  add     rsp, 20h
0x180004146  pop     rdi
0x180004147  retn
```
