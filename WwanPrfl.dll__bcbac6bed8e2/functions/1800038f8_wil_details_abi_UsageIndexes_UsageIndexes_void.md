# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800038f8`
- end: `0x180003985`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003484`
- `0x180006a00`
- `0x180007510`
- `0x180013857`

## callees

- `0x1800038f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000392a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000394f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003974`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000392a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000394f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000391c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000391c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003966`

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
0x1800038f8  mov     [rsp+arg_0], rbx
0x1800038fd  push    rdi
0x1800038fe  sub     rsp, 20h
0x180003902  mov     rdi, [rcx+0B0h]
0x180003909  mov     rbx, rcx
0x18000390c  mov     qword ptr [rcx+0B0h], 0
0x180003917  test    rdi, rdi
0x18000391a  jz      short loc_180003930
0x18000391c  call    cs:__imp_GetProcessHeap
0x180003922  mov     r8, rdi; lpMem
0x180003925  xor     edx, edx; dwFlags
0x180003927  mov     rcx, rax; hHeap
0x18000392a  call    cs:__imp_HeapFree
0x180003930  mov     rdi, [rbx+70h]
0x180003934  mov     qword ptr [rbx+70h], 0
0x18000393c  test    rdi, rdi
0x18000393f  jz      short loc_180003955
0x180003941  call    cs:__imp_GetProcessHeap
0x180003947  mov     r8, rdi; lpMem
0x18000394a  xor     edx, edx; dwFlags
0x18000394c  mov     rcx, rax; hHeap
0x18000394f  call    cs:__imp_HeapFree
0x180003955  mov     rdi, [rbx+30h]
0x180003959  mov     qword ptr [rbx+30h], 0
0x180003961  test    rdi, rdi
0x180003964  jz      short loc_18000397A
0x180003966  call    cs:__imp_GetProcessHeap
0x18000396c  mov     r8, rdi; lpMem
0x18000396f  xor     edx, edx; dwFlags
0x180003971  mov     rcx, rax; hHeap
0x180003974  call    cs:__imp_HeapFree
0x18000397a  mov     rbx, [rsp+28h+arg_0]
0x18000397f  add     rsp, 20h
0x180003983  pop     rdi
0x180003984  retn
```
