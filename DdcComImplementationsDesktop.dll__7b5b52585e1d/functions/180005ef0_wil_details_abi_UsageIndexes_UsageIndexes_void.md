# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180005ef0`
- end: `0x180005f7d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a7c`
- `0x1800087f0`
- `0x180009300`
- `0x18000bead`

## callees

- `0x180005ef0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f5e`

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
0x180005ef0  mov     [rsp+arg_0], rbx
0x180005ef5  push    rdi
0x180005ef6  sub     rsp, 20h
0x180005efa  mov     rdi, [rcx+0B0h]
0x180005f01  mov     rbx, rcx
0x180005f04  mov     qword ptr [rcx+0B0h], 0
0x180005f0f  test    rdi, rdi
0x180005f12  jz      short loc_180005F28
0x180005f14  call    cs:__imp_GetProcessHeap
0x180005f1a  mov     r8, rdi; lpMem
0x180005f1d  xor     edx, edx; dwFlags
0x180005f1f  mov     rcx, rax; hHeap
0x180005f22  call    cs:__imp_HeapFree
0x180005f28  mov     rdi, [rbx+70h]
0x180005f2c  mov     qword ptr [rbx+70h], 0
0x180005f34  test    rdi, rdi
0x180005f37  jz      short loc_180005F4D
0x180005f39  call    cs:__imp_GetProcessHeap
0x180005f3f  mov     r8, rdi; lpMem
0x180005f42  xor     edx, edx; dwFlags
0x180005f44  mov     rcx, rax; hHeap
0x180005f47  call    cs:__imp_HeapFree
0x180005f4d  mov     rdi, [rbx+30h]
0x180005f51  mov     qword ptr [rbx+30h], 0
0x180005f59  test    rdi, rdi
0x180005f5c  jz      short loc_180005F72
0x180005f5e  call    cs:__imp_GetProcessHeap
0x180005f64  mov     r8, rdi; lpMem
0x180005f67  xor     edx, edx; dwFlags
0x180005f69  mov     rcx, rax; hHeap
0x180005f6c  call    cs:__imp_HeapFree
0x180005f72  mov     rbx, [rsp+28h+arg_0]
0x180005f77  add     rsp, 20h
0x180005f7b  pop     rdi
0x180005f7c  retn
```
