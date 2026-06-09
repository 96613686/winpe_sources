# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140003c44`
- end: `0x140003cd1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037d0`
- `0x140008830`
- `0x140009340`
- `0x140010fd7`

## callees

- `0x140003c44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003cc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003cc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003cb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003cb2`

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
0x140003c44  mov     [rsp+arg_0], rbx
0x140003c49  push    rdi
0x140003c4a  sub     rsp, 20h
0x140003c4e  mov     rdi, [rcx+0B0h]
0x140003c55  mov     rbx, rcx
0x140003c58  mov     qword ptr [rcx+0B0h], 0
0x140003c63  test    rdi, rdi
0x140003c66  jz      short loc_140003C7C
0x140003c68  call    cs:__imp_GetProcessHeap
0x140003c6e  mov     r8, rdi; lpMem
0x140003c71  xor     edx, edx; dwFlags
0x140003c73  mov     rcx, rax; hHeap
0x140003c76  call    cs:__imp_HeapFree
0x140003c7c  mov     rdi, [rbx+70h]
0x140003c80  mov     qword ptr [rbx+70h], 0
0x140003c88  test    rdi, rdi
0x140003c8b  jz      short loc_140003CA1
0x140003c8d  call    cs:__imp_GetProcessHeap
0x140003c93  mov     r8, rdi; lpMem
0x140003c96  xor     edx, edx; dwFlags
0x140003c98  mov     rcx, rax; hHeap
0x140003c9b  call    cs:__imp_HeapFree
0x140003ca1  mov     rdi, [rbx+30h]
0x140003ca5  mov     qword ptr [rbx+30h], 0
0x140003cad  test    rdi, rdi
0x140003cb0  jz      short loc_140003CC6
0x140003cb2  call    cs:__imp_GetProcessHeap
0x140003cb8  mov     r8, rdi; lpMem
0x140003cbb  xor     edx, edx; dwFlags
0x140003cbd  mov     rcx, rax; hHeap
0x140003cc0  call    cs:__imp_HeapFree
0x140003cc6  mov     rbx, [rsp+28h+arg_0]
0x140003ccb  add     rsp, 20h
0x140003ccf  pop     rdi
0x140003cd0  retn
```
