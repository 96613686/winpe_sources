# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800076ac`
- end: `0x180007739`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800073a8`
- `0x1800086b8`
- `0x1800090c0`
- `0x18000a52d`

## callees

- `0x1800076ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000771a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000771a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007703`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007703`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007728`

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
0x1800076ac  mov     [rsp+arg_0], rbx
0x1800076b1  push    rdi
0x1800076b2  sub     rsp, 20h
0x1800076b6  mov     rdi, [rcx+0B0h]
0x1800076bd  mov     rbx, rcx
0x1800076c0  mov     qword ptr [rcx+0B0h], 0
0x1800076cb  test    rdi, rdi
0x1800076ce  jz      short loc_1800076E4
0x1800076d0  call    cs:__imp_GetProcessHeap
0x1800076d6  mov     r8, rdi; lpMem
0x1800076d9  xor     edx, edx; dwFlags
0x1800076db  mov     rcx, rax; hHeap
0x1800076de  call    cs:__imp_HeapFree
0x1800076e4  mov     rdi, [rbx+70h]
0x1800076e8  mov     qword ptr [rbx+70h], 0
0x1800076f0  test    rdi, rdi
0x1800076f3  jz      short loc_180007709
0x1800076f5  call    cs:__imp_GetProcessHeap
0x1800076fb  mov     r8, rdi; lpMem
0x1800076fe  xor     edx, edx; dwFlags
0x180007700  mov     rcx, rax; hHeap
0x180007703  call    cs:__imp_HeapFree
0x180007709  mov     rdi, [rbx+30h]
0x18000770d  mov     qword ptr [rbx+30h], 0
0x180007715  test    rdi, rdi
0x180007718  jz      short loc_18000772E
0x18000771a  call    cs:__imp_GetProcessHeap
0x180007720  mov     r8, rdi; lpMem
0x180007723  xor     edx, edx; dwFlags
0x180007725  mov     rcx, rax; hHeap
0x180007728  call    cs:__imp_HeapFree
0x18000772e  mov     rbx, [rsp+28h+arg_0]
0x180007733  add     rsp, 20h
0x180007737  pop     rdi
0x180007738  retn
```
