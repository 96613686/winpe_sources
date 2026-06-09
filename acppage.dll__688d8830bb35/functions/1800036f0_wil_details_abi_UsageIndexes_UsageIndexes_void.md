# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800036f0`
- end: `0x18000377d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033a0`
- `0x180006600`
- `0x1800070b4`

## callees

- `0x1800036f0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003722`
- `KERNEL32!HeapFree` at `0x180003747`
- `KERNEL32!HeapFree` at `0x18000376c`
- `KERNEL32!HeapFree` at `0x180003722`
- `KERNEL32!HeapFree` at `0x180003747`
- `KERNEL32!HeapFree` at `0x18000376c`
- `KERNEL32!GetProcessHeap` at `0x180003714`
- `KERNEL32!GetProcessHeap` at `0x180003739`
- `KERNEL32!GetProcessHeap` at `0x18000375e`
- `KERNEL32!GetProcessHeap` at `0x180003714`
- `KERNEL32!GetProcessHeap` at `0x180003739`
- `KERNEL32!GetProcessHeap` at `0x18000375e`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
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
0x1800036f0  mov     [rsp+arg_0], rbx
0x1800036f5  push    rdi
0x1800036f6  sub     rsp, 20h
0x1800036fa  mov     rdi, [rcx+0B0h]
0x180003701  mov     rbx, rcx
0x180003704  mov     qword ptr [rcx+0B0h], 0
0x18000370f  test    rdi, rdi
0x180003712  jz      short loc_180003728
0x180003714  call    cs:__imp_GetProcessHeap
0x18000371a  mov     r8, rdi; lpMem
0x18000371d  xor     edx, edx; dwFlags
0x18000371f  mov     rcx, rax; hHeap
0x180003722  call    cs:__imp_HeapFree
0x180003728  mov     rdi, [rbx+70h]
0x18000372c  mov     qword ptr [rbx+70h], 0
0x180003734  test    rdi, rdi
0x180003737  jz      short loc_18000374D
0x180003739  call    cs:__imp_GetProcessHeap
0x18000373f  mov     r8, rdi; lpMem
0x180003742  xor     edx, edx; dwFlags
0x180003744  mov     rcx, rax; hHeap
0x180003747  call    cs:__imp_HeapFree
0x18000374d  mov     rdi, [rbx+30h]
0x180003751  mov     qword ptr [rbx+30h], 0
0x180003759  test    rdi, rdi
0x18000375c  jz      short loc_180003772
0x18000375e  call    cs:__imp_GetProcessHeap
0x180003764  mov     r8, rdi; lpMem
0x180003767  xor     edx, edx; dwFlags
0x180003769  mov     rcx, rax; hHeap
0x18000376c  call    cs:__imp_HeapFree
0x180003772  mov     rbx, [rsp+28h+arg_0]
0x180003777  add     rsp, 20h
0x18000377b  pop     rdi
0x18000377c  retn
```
