# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800031ec`
- end: `0x18000329e`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `178`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e38`
- `0x180005b40`
- `0x180006658`

## callees

- `0x1800031ec`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003210`
- `KERNEL32!GetProcessHeap` at `0x180003241`
- `KERNEL32!GetProcessHeap` at `0x180003272`
- `KERNEL32!GetProcessHeap` at `0x180003210`
- `KERNEL32!GetProcessHeap` at `0x180003241`
- `KERNEL32!GetProcessHeap` at `0x180003272`
- `KERNEL32!HeapFree` at `0x180003224`
- `KERNEL32!HeapFree` at `0x180003255`
- `KERNEL32!HeapFree` at `0x180003286`
- `KERNEL32!HeapFree` at `0x180003224`
- `KERNEL32!HeapFree` at `0x180003255`
- `KERNEL32!HeapFree` at `0x180003286`

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
0x1800031ec  mov     [rsp+arg_0], rbx
0x1800031f1  push    rdi
0x1800031f2  sub     rsp, 20h
0x1800031f6  mov     rdi, [rcx+0B0h]
0x1800031fd  mov     rbx, rcx
0x180003200  mov     qword ptr [rcx+0B0h], 0
0x18000320b  test    rdi, rdi
0x18000320e  jz      short loc_180003230
0x180003210  call    cs:__imp_GetProcessHeap
0x180003217  nop     dword ptr [rax+rax+00h]
0x18000321c  mov     r8, rdi; lpMem
0x18000321f  xor     edx, edx; dwFlags
0x180003221  mov     rcx, rax; hHeap
0x180003224  call    cs:__imp_HeapFree
0x18000322b  nop     dword ptr [rax+rax+00h]
0x180003230  mov     rdi, [rbx+70h]
0x180003234  mov     qword ptr [rbx+70h], 0
0x18000323c  test    rdi, rdi
0x18000323f  jz      short loc_180003261
0x180003241  call    cs:__imp_GetProcessHeap
0x180003248  nop     dword ptr [rax+rax+00h]
0x18000324d  mov     r8, rdi; lpMem
0x180003250  xor     edx, edx; dwFlags
0x180003252  mov     rcx, rax; hHeap
0x180003255  call    cs:__imp_HeapFree
0x18000325c  nop     dword ptr [rax+rax+00h]
0x180003261  mov     rdi, [rbx+30h]
0x180003265  mov     qword ptr [rbx+30h], 0
0x18000326d  test    rdi, rdi
0x180003270  jz      short loc_180003292
0x180003272  call    cs:__imp_GetProcessHeap
0x180003279  nop     dword ptr [rax+rax+00h]
0x18000327e  mov     r8, rdi; lpMem
0x180003281  xor     edx, edx; dwFlags
0x180003283  mov     rcx, rax; hHeap
0x180003286  call    cs:__imp_HeapFree
0x18000328d  nop     dword ptr [rax+rax+00h]
0x180003292  mov     rbx, [rsp+28h+arg_0]
0x180003297  add     rsp, 20h
0x18000329b  pop     rdi
0x18000329c  retn
```
