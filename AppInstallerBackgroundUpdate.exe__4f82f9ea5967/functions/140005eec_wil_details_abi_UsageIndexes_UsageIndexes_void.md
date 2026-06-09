# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140005eec`
- end: `0x140005f79`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140005be8`
- `0x140006f14`
- `0x140007910`
- `0x140008abe`

## callees

- `0x140005eec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005f1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005f43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005f1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005f43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005f68`

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
0x140005eec  mov     [rsp+arg_0], rbx
0x140005ef1  push    rdi
0x140005ef2  sub     rsp, 20h
0x140005ef6  mov     rdi, [rcx+0B0h]
0x140005efd  mov     rbx, rcx
0x140005f00  mov     qword ptr [rcx+0B0h], 0
0x140005f0b  test    rdi, rdi
0x140005f0e  jz      short loc_140005F24
0x140005f10  call    cs:__imp_GetProcessHeap
0x140005f16  mov     r8, rdi; lpMem
0x140005f19  xor     edx, edx; dwFlags
0x140005f1b  mov     rcx, rax; hHeap
0x140005f1e  call    cs:__imp_HeapFree
0x140005f24  mov     rdi, [rbx+70h]
0x140005f28  mov     qword ptr [rbx+70h], 0
0x140005f30  test    rdi, rdi
0x140005f33  jz      short loc_140005F49
0x140005f35  call    cs:__imp_GetProcessHeap
0x140005f3b  mov     r8, rdi; lpMem
0x140005f3e  xor     edx, edx; dwFlags
0x140005f40  mov     rcx, rax; hHeap
0x140005f43  call    cs:__imp_HeapFree
0x140005f49  mov     rdi, [rbx+30h]
0x140005f4d  mov     qword ptr [rbx+30h], 0
0x140005f55  test    rdi, rdi
0x140005f58  jz      short loc_140005F6E
0x140005f5a  call    cs:__imp_GetProcessHeap
0x140005f60  mov     r8, rdi; lpMem
0x140005f63  xor     edx, edx; dwFlags
0x140005f65  mov     rcx, rax; hHeap
0x140005f68  call    cs:__imp_HeapFree
0x140005f6e  mov     rbx, [rsp+28h+arg_0]
0x140005f73  add     rsp, 20h
0x140005f77  pop     rdi
0x140005f78  retn
```
