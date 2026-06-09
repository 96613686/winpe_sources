# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180003718`
- end: `0x1800037a5`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003328`
- `0x18000713c`
- `0x180007910`
- `0x18000caea`

## callees

- `0x180003718`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000374a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000376f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003794`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000374a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000376f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003794`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000373c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003761`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000373c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003761`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003786`

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
0x180003718  mov     [rsp+arg_0], rbx
0x18000371d  push    rdi
0x18000371e  sub     rsp, 20h
0x180003722  mov     rdi, [rcx+0B0h]
0x180003729  mov     rbx, rcx
0x18000372c  mov     qword ptr [rcx+0B0h], 0
0x180003737  test    rdi, rdi
0x18000373a  jz      short loc_180003750
0x18000373c  call    cs:__imp_GetProcessHeap
0x180003742  mov     r8, rdi; lpMem
0x180003745  xor     edx, edx; dwFlags
0x180003747  mov     rcx, rax; hHeap
0x18000374a  call    cs:__imp_HeapFree
0x180003750  mov     rdi, [rbx+70h]
0x180003754  mov     qword ptr [rbx+70h], 0
0x18000375c  test    rdi, rdi
0x18000375f  jz      short loc_180003775
0x180003761  call    cs:__imp_GetProcessHeap
0x180003767  mov     r8, rdi; lpMem
0x18000376a  xor     edx, edx; dwFlags
0x18000376c  mov     rcx, rax; hHeap
0x18000376f  call    cs:__imp_HeapFree
0x180003775  mov     rdi, [rbx+30h]
0x180003779  mov     qword ptr [rbx+30h], 0
0x180003781  test    rdi, rdi
0x180003784  jz      short loc_18000379A
0x180003786  call    cs:__imp_GetProcessHeap
0x18000378c  mov     r8, rdi; lpMem
0x18000378f  xor     edx, edx; dwFlags
0x180003791  mov     rcx, rax; hHeap
0x180003794  call    cs:__imp_HeapFree
0x18000379a  mov     rbx, [rsp+28h+arg_0]
0x18000379f  add     rsp, 20h
0x1800037a3  pop     rdi
0x1800037a4  retn
```
