# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1400134f0`
- end: `0x14001357d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400131ec`
- `0x140014c14`
- `0x140015610`
- `0x1400179a9`

## callees

- `0x1400134f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001356c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001356c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001355e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001355e`

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
0x1400134f0  mov     [rsp+arg_0], rbx
0x1400134f5  push    rdi
0x1400134f6  sub     rsp, 20h
0x1400134fa  mov     rdi, [rcx+0B0h]
0x140013501  mov     rbx, rcx
0x140013504  mov     qword ptr [rcx+0B0h], 0
0x14001350f  test    rdi, rdi
0x140013512  jz      short loc_140013528
0x140013514  call    cs:__imp_GetProcessHeap
0x14001351a  mov     r8, rdi; lpMem
0x14001351d  xor     edx, edx; dwFlags
0x14001351f  mov     rcx, rax; hHeap
0x140013522  call    cs:__imp_HeapFree
0x140013528  mov     rdi, [rbx+70h]
0x14001352c  mov     qword ptr [rbx+70h], 0
0x140013534  test    rdi, rdi
0x140013537  jz      short loc_14001354D
0x140013539  call    cs:__imp_GetProcessHeap
0x14001353f  mov     r8, rdi; lpMem
0x140013542  xor     edx, edx; dwFlags
0x140013544  mov     rcx, rax; hHeap
0x140013547  call    cs:__imp_HeapFree
0x14001354d  mov     rdi, [rbx+30h]
0x140013551  mov     qword ptr [rbx+30h], 0
0x140013559  test    rdi, rdi
0x14001355c  jz      short loc_140013572
0x14001355e  call    cs:__imp_GetProcessHeap
0x140013564  mov     r8, rdi; lpMem
0x140013567  xor     edx, edx; dwFlags
0x140013569  mov     rcx, rax; hHeap
0x14001356c  call    cs:__imp_HeapFree
0x140013572  mov     rbx, [rsp+28h+arg_0]
0x140013577  add     rsp, 20h
0x14001357b  pop     rdi
0x14001357c  retn
```
