# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140008ea0`
- end: `0x140008f2d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140008a34`
- `0x14000c560`
- `0x14000d0ac`
- `0x1400122d4`

## callees

- `0x140008ea0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008f1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008f1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ee9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008f0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ee9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008f0e`

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
0x140008ea0  mov     [rsp+arg_0], rbx
0x140008ea5  push    rdi
0x140008ea6  sub     rsp, 20h
0x140008eaa  mov     rdi, [rcx+0B0h]
0x140008eb1  mov     rbx, rcx
0x140008eb4  mov     qword ptr [rcx+0B0h], 0
0x140008ebf  test    rdi, rdi
0x140008ec2  jz      short loc_140008ED8
0x140008ec4  call    cs:__imp_GetProcessHeap
0x140008eca  mov     r8, rdi; lpMem
0x140008ecd  xor     edx, edx; dwFlags
0x140008ecf  mov     rcx, rax; hHeap
0x140008ed2  call    cs:__imp_HeapFree
0x140008ed8  mov     rdi, [rbx+70h]
0x140008edc  mov     qword ptr [rbx+70h], 0
0x140008ee4  test    rdi, rdi
0x140008ee7  jz      short loc_140008EFD
0x140008ee9  call    cs:__imp_GetProcessHeap
0x140008eef  mov     r8, rdi; lpMem
0x140008ef2  xor     edx, edx; dwFlags
0x140008ef4  mov     rcx, rax; hHeap
0x140008ef7  call    cs:__imp_HeapFree
0x140008efd  mov     rdi, [rbx+30h]
0x140008f01  mov     qword ptr [rbx+30h], 0
0x140008f09  test    rdi, rdi
0x140008f0c  jz      short loc_140008F22
0x140008f0e  call    cs:__imp_GetProcessHeap
0x140008f14  mov     r8, rdi; lpMem
0x140008f17  xor     edx, edx; dwFlags
0x140008f19  mov     rcx, rax; hHeap
0x140008f1c  call    cs:__imp_HeapFree
0x140008f22  mov     rbx, [rsp+28h+arg_0]
0x140008f27  add     rsp, 20h
0x140008f2b  pop     rdi
0x140008f2c  retn
```
