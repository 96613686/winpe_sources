# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x14000bfe4`
- end: `0x14000c071`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bd38`
- `0x14000d0cc`
- `0x14000d6a0`
- `0x1400121ea`

## callees

- `0x14000bfe4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c016`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c03b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c060`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c016`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c03b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c060`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c02d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c052`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c02d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c052`

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
0x14000bfe4  mov     [rsp+arg_0], rbx
0x14000bfe9  push    rdi
0x14000bfea  sub     rsp, 20h
0x14000bfee  mov     rdi, [rcx+0B0h]
0x14000bff5  mov     rbx, rcx
0x14000bff8  mov     qword ptr [rcx+0B0h], 0
0x14000c003  test    rdi, rdi
0x14000c006  jz      short loc_14000C01C
0x14000c008  call    cs:__imp_GetProcessHeap
0x14000c00e  mov     r8, rdi; lpMem
0x14000c011  xor     edx, edx; dwFlags
0x14000c013  mov     rcx, rax; hHeap
0x14000c016  call    cs:__imp_HeapFree
0x14000c01c  mov     rdi, [rbx+70h]
0x14000c020  mov     qword ptr [rbx+70h], 0
0x14000c028  test    rdi, rdi
0x14000c02b  jz      short loc_14000C041
0x14000c02d  call    cs:__imp_GetProcessHeap
0x14000c033  mov     r8, rdi; lpMem
0x14000c036  xor     edx, edx; dwFlags
0x14000c038  mov     rcx, rax; hHeap
0x14000c03b  call    cs:__imp_HeapFree
0x14000c041  mov     rdi, [rbx+30h]
0x14000c045  mov     qword ptr [rbx+30h], 0
0x14000c04d  test    rdi, rdi
0x14000c050  jz      short loc_14000C066
0x14000c052  call    cs:__imp_GetProcessHeap
0x14000c058  mov     r8, rdi; lpMem
0x14000c05b  xor     edx, edx; dwFlags
0x14000c05d  mov     rcx, rax; hHeap
0x14000c060  call    cs:__imp_HeapFree
0x14000c066  mov     rbx, [rsp+28h+arg_0]
0x14000c06b  add     rsp, 20h
0x14000c06f  pop     rdi
0x14000c070  retn
```
