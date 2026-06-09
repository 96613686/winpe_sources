# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800064b8`
- end: `0x180006545`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005fc4`
- `0x18000a9c0`
- `0x18000b50c`
- `0x18001052c`

## callees

- `0x1800064b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000650f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006534`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000650f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006534`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006501`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006526`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006501`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006526`

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
0x1800064b8  mov     [rsp+arg_0], rbx
0x1800064bd  push    rdi
0x1800064be  sub     rsp, 20h
0x1800064c2  mov     rdi, [rcx+0B0h]
0x1800064c9  mov     rbx, rcx
0x1800064cc  mov     qword ptr [rcx+0B0h], 0
0x1800064d7  test    rdi, rdi
0x1800064da  jz      short loc_1800064F0
0x1800064dc  call    cs:__imp_GetProcessHeap
0x1800064e2  mov     r8, rdi; lpMem
0x1800064e5  xor     edx, edx; dwFlags
0x1800064e7  mov     rcx, rax; hHeap
0x1800064ea  call    cs:__imp_HeapFree
0x1800064f0  mov     rdi, [rbx+70h]
0x1800064f4  mov     qword ptr [rbx+70h], 0
0x1800064fc  test    rdi, rdi
0x1800064ff  jz      short loc_180006515
0x180006501  call    cs:__imp_GetProcessHeap
0x180006507  mov     r8, rdi; lpMem
0x18000650a  xor     edx, edx; dwFlags
0x18000650c  mov     rcx, rax; hHeap
0x18000650f  call    cs:__imp_HeapFree
0x180006515  mov     rdi, [rbx+30h]
0x180006519  mov     qword ptr [rbx+30h], 0
0x180006521  test    rdi, rdi
0x180006524  jz      short loc_18000653A
0x180006526  call    cs:__imp_GetProcessHeap
0x18000652c  mov     r8, rdi; lpMem
0x18000652f  xor     edx, edx; dwFlags
0x180006531  mov     rcx, rax; hHeap
0x180006534  call    cs:__imp_HeapFree
0x18000653a  mov     rbx, [rsp+28h+arg_0]
0x18000653f  add     rsp, 20h
0x180006543  pop     rdi
0x180006544  retn
```
