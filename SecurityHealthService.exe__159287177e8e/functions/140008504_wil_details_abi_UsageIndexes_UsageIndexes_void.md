# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140008504`
- end: `0x140008591`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140008090`
- `0x14000a4b8`
- `0x14000aff4`
- `0x1400123b6`

## callees

- `0x140008504`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008536`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000855b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008580`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008536`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000855b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008580`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008528`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000854d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008528`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000854d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008572`

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
0x140008504  mov     [rsp+arg_0], rbx
0x140008509  push    rdi
0x14000850a  sub     rsp, 20h
0x14000850e  mov     rdi, [rcx+0B0h]
0x140008515  mov     rbx, rcx
0x140008518  mov     qword ptr [rcx+0B0h], 0
0x140008523  test    rdi, rdi
0x140008526  jz      short loc_14000853C
0x140008528  call    cs:__imp_GetProcessHeap
0x14000852e  mov     r8, rdi; lpMem
0x140008531  xor     edx, edx; dwFlags
0x140008533  mov     rcx, rax; hHeap
0x140008536  call    cs:__imp_HeapFree
0x14000853c  mov     rdi, [rbx+70h]
0x140008540  mov     qword ptr [rbx+70h], 0
0x140008548  test    rdi, rdi
0x14000854b  jz      short loc_140008561
0x14000854d  call    cs:__imp_GetProcessHeap
0x140008553  mov     r8, rdi; lpMem
0x140008556  xor     edx, edx; dwFlags
0x140008558  mov     rcx, rax; hHeap
0x14000855b  call    cs:__imp_HeapFree
0x140008561  mov     rdi, [rbx+30h]
0x140008565  mov     qword ptr [rbx+30h], 0
0x14000856d  test    rdi, rdi
0x140008570  jz      short loc_140008586
0x140008572  call    cs:__imp_GetProcessHeap
0x140008578  mov     r8, rdi; lpMem
0x14000857b  xor     edx, edx; dwFlags
0x14000857d  mov     rcx, rax; hHeap
0x140008580  call    cs:__imp_HeapFree
0x140008586  mov     rbx, [rsp+28h+arg_0]
0x14000858b  add     rsp, 20h
0x14000858f  pop     rdi
0x140008590  retn
```
