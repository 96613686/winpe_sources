# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180003574`
- end: `0x180003601`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003224`
- `0x180005e1c`
- `0x180006920`

## callees

- `0x180003574`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003598`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003598`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035f0`

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
0x180003574  mov     [rsp+arg_0], rbx
0x180003579  push    rdi
0x18000357a  sub     rsp, 20h
0x18000357e  mov     rdi, [rcx+0B0h]
0x180003585  mov     rbx, rcx
0x180003588  mov     qword ptr [rcx+0B0h], 0
0x180003593  test    rdi, rdi
0x180003596  jz      short loc_1800035AC
0x180003598  call    cs:__imp_GetProcessHeap
0x18000359e  mov     r8, rdi; lpMem
0x1800035a1  xor     edx, edx; dwFlags
0x1800035a3  mov     rcx, rax; hHeap
0x1800035a6  call    cs:__imp_HeapFree
0x1800035ac  mov     rdi, [rbx+70h]
0x1800035b0  mov     qword ptr [rbx+70h], 0
0x1800035b8  test    rdi, rdi
0x1800035bb  jz      short loc_1800035D1
0x1800035bd  call    cs:__imp_GetProcessHeap
0x1800035c3  mov     r8, rdi; lpMem
0x1800035c6  xor     edx, edx; dwFlags
0x1800035c8  mov     rcx, rax; hHeap
0x1800035cb  call    cs:__imp_HeapFree
0x1800035d1  mov     rdi, [rbx+30h]
0x1800035d5  mov     qword ptr [rbx+30h], 0
0x1800035dd  test    rdi, rdi
0x1800035e0  jz      short loc_1800035F6
0x1800035e2  call    cs:__imp_GetProcessHeap
0x1800035e8  mov     r8, rdi; lpMem
0x1800035eb  xor     edx, edx; dwFlags
0x1800035ed  mov     rcx, rax; hHeap
0x1800035f0  call    cs:__imp_HeapFree
0x1800035f6  mov     rbx, [rsp+28h+arg_0]
0x1800035fb  add     rsp, 20h
0x1800035ff  pop     rdi
0x180003600  retn
```
