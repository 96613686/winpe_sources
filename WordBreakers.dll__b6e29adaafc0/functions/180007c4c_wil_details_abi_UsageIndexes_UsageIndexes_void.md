# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180007c4c`
- end: `0x180007cd9`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007948`
- `0x1800099c0`
- `0x18000a370`
- `0x18000bc23`

## callees

- `0x180007c4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007cba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007cba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ca3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ca3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cc8`

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
0x180007c4c  mov     [rsp+arg_0], rbx
0x180007c51  push    rdi
0x180007c52  sub     rsp, 20h
0x180007c56  mov     rdi, [rcx+0B0h]
0x180007c5d  mov     rbx, rcx
0x180007c60  mov     qword ptr [rcx+0B0h], 0
0x180007c6b  test    rdi, rdi
0x180007c6e  jz      short loc_180007C84
0x180007c70  call    cs:__imp_GetProcessHeap
0x180007c76  mov     r8, rdi; lpMem
0x180007c79  xor     edx, edx; dwFlags
0x180007c7b  mov     rcx, rax; hHeap
0x180007c7e  call    cs:__imp_HeapFree
0x180007c84  mov     rdi, [rbx+70h]
0x180007c88  mov     qword ptr [rbx+70h], 0
0x180007c90  test    rdi, rdi
0x180007c93  jz      short loc_180007CA9
0x180007c95  call    cs:__imp_GetProcessHeap
0x180007c9b  mov     r8, rdi; lpMem
0x180007c9e  xor     edx, edx; dwFlags
0x180007ca0  mov     rcx, rax; hHeap
0x180007ca3  call    cs:__imp_HeapFree
0x180007ca9  mov     rdi, [rbx+30h]
0x180007cad  mov     qword ptr [rbx+30h], 0
0x180007cb5  test    rdi, rdi
0x180007cb8  jz      short loc_180007CCE
0x180007cba  call    cs:__imp_GetProcessHeap
0x180007cc0  mov     r8, rdi; lpMem
0x180007cc3  xor     edx, edx; dwFlags
0x180007cc5  mov     rcx, rax; hHeap
0x180007cc8  call    cs:__imp_HeapFree
0x180007cce  mov     rbx, [rsp+28h+arg_0]
0x180007cd3  add     rsp, 20h
0x180007cd7  pop     rdi
0x180007cd8  retn
```
