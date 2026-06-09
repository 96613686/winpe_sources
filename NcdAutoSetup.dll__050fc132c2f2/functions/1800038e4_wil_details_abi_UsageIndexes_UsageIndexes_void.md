# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800038e4`
- end: `0x180003971`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003594`
- `0x1800065cc`
- `0x180007080`

## callees

- `0x1800038e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003916`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000393b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003960`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003916`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000393b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003908`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000392d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003952`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003908`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000392d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003952`

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
0x1800038e4  mov     [rsp+arg_0], rbx
0x1800038e9  push    rdi
0x1800038ea  sub     rsp, 20h
0x1800038ee  mov     rdi, [rcx+0B0h]
0x1800038f5  mov     rbx, rcx
0x1800038f8  mov     qword ptr [rcx+0B0h], 0
0x180003903  test    rdi, rdi
0x180003906  jz      short loc_18000391C
0x180003908  call    cs:__imp_GetProcessHeap
0x18000390e  mov     r8, rdi; lpMem
0x180003911  xor     edx, edx; dwFlags
0x180003913  mov     rcx, rax; hHeap
0x180003916  call    cs:__imp_HeapFree
0x18000391c  mov     rdi, [rbx+70h]
0x180003920  mov     qword ptr [rbx+70h], 0
0x180003928  test    rdi, rdi
0x18000392b  jz      short loc_180003941
0x18000392d  call    cs:__imp_GetProcessHeap
0x180003933  mov     r8, rdi; lpMem
0x180003936  xor     edx, edx; dwFlags
0x180003938  mov     rcx, rax; hHeap
0x18000393b  call    cs:__imp_HeapFree
0x180003941  mov     rdi, [rbx+30h]
0x180003945  mov     qword ptr [rbx+30h], 0
0x18000394d  test    rdi, rdi
0x180003950  jz      short loc_180003966
0x180003952  call    cs:__imp_GetProcessHeap
0x180003958  mov     r8, rdi; lpMem
0x18000395b  xor     edx, edx; dwFlags
0x18000395d  mov     rcx, rax; hHeap
0x180003960  call    cs:__imp_HeapFree
0x180003966  mov     rbx, [rsp+28h+arg_0]
0x18000396b  add     rsp, 20h
0x18000396f  pop     rdi
0x180003970  retn
```
