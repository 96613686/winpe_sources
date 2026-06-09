# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180003884`
- end: `0x180003911`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003410`
- `0x180006220`
- `0x180006d30`
- `0x18000cd30`

## callees

- `0x180003884`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003900`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003900`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038f2`

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
0x180003884  mov     [rsp+arg_0], rbx
0x180003889  push    rdi
0x18000388a  sub     rsp, 20h
0x18000388e  mov     rdi, [rcx+0B0h]
0x180003895  mov     rbx, rcx
0x180003898  mov     qword ptr [rcx+0B0h], 0
0x1800038a3  test    rdi, rdi
0x1800038a6  jz      short loc_1800038BC
0x1800038a8  call    cs:__imp_GetProcessHeap
0x1800038ae  mov     r8, rdi; lpMem
0x1800038b1  xor     edx, edx; dwFlags
0x1800038b3  mov     rcx, rax; hHeap
0x1800038b6  call    cs:__imp_HeapFree
0x1800038bc  mov     rdi, [rbx+70h]
0x1800038c0  mov     qword ptr [rbx+70h], 0
0x1800038c8  test    rdi, rdi
0x1800038cb  jz      short loc_1800038E1
0x1800038cd  call    cs:__imp_GetProcessHeap
0x1800038d3  mov     r8, rdi; lpMem
0x1800038d6  xor     edx, edx; dwFlags
0x1800038d8  mov     rcx, rax; hHeap
0x1800038db  call    cs:__imp_HeapFree
0x1800038e1  mov     rdi, [rbx+30h]
0x1800038e5  mov     qword ptr [rbx+30h], 0
0x1800038ed  test    rdi, rdi
0x1800038f0  jz      short loc_180003906
0x1800038f2  call    cs:__imp_GetProcessHeap
0x1800038f8  mov     r8, rdi; lpMem
0x1800038fb  xor     edx, edx; dwFlags
0x1800038fd  mov     rcx, rax; hHeap
0x180003900  call    cs:__imp_HeapFree
0x180003906  mov     rbx, [rsp+28h+arg_0]
0x18000390b  add     rsp, 20h
0x18000390f  pop     rdi
0x180003910  retn
```
