# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140007724`
- end: `0x1400077b1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400072b0`
- `0x140009804`
- `0x14000a318`
- `0x14000fcd9`

## callees

- `0x140007724`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007748`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000776d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007792`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007748`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000776d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007792`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007756`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000777b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400077a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007756`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000777b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400077a0`

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
0x140007724  mov     [rsp+arg_0], rbx
0x140007729  push    rdi
0x14000772a  sub     rsp, 20h
0x14000772e  mov     rdi, [rcx+0B0h]
0x140007735  mov     rbx, rcx
0x140007738  mov     qword ptr [rcx+0B0h], 0
0x140007743  test    rdi, rdi
0x140007746  jz      short loc_14000775C
0x140007748  call    cs:__imp_GetProcessHeap
0x14000774e  mov     r8, rdi; lpMem
0x140007751  xor     edx, edx; dwFlags
0x140007753  mov     rcx, rax; hHeap
0x140007756  call    cs:__imp_HeapFree
0x14000775c  mov     rdi, [rbx+70h]
0x140007760  mov     qword ptr [rbx+70h], 0
0x140007768  test    rdi, rdi
0x14000776b  jz      short loc_140007781
0x14000776d  call    cs:__imp_GetProcessHeap
0x140007773  mov     r8, rdi; lpMem
0x140007776  xor     edx, edx; dwFlags
0x140007778  mov     rcx, rax; hHeap
0x14000777b  call    cs:__imp_HeapFree
0x140007781  mov     rdi, [rbx+30h]
0x140007785  mov     qword ptr [rbx+30h], 0
0x14000778d  test    rdi, rdi
0x140007790  jz      short loc_1400077A6
0x140007792  call    cs:__imp_GetProcessHeap
0x140007798  mov     r8, rdi; lpMem
0x14000779b  xor     edx, edx; dwFlags
0x14000779d  mov     rcx, rax; hHeap
0x1400077a0  call    cs:__imp_HeapFree
0x1400077a6  mov     rbx, [rsp+28h+arg_0]
0x1400077ab  add     rsp, 20h
0x1400077af  pop     rdi
0x1400077b0  retn
```
