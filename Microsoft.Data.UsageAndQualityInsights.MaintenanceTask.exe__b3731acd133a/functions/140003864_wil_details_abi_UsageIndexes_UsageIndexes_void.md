# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140003864`
- end: `0x1400038f1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400033f0`
- `0x140006600`
- `0x140007110`
- `0x14000b93e`

## callees

- `0x140003864`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003888`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400038ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400038d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003888`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400038ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400038d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400038bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400038e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400038bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400038e0`

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
0x140003864  mov     [rsp+arg_0], rbx
0x140003869  push    rdi
0x14000386a  sub     rsp, 20h
0x14000386e  mov     rdi, [rcx+0B0h]
0x140003875  mov     rbx, rcx
0x140003878  mov     qword ptr [rcx+0B0h], 0
0x140003883  test    rdi, rdi
0x140003886  jz      short loc_14000389C
0x140003888  call    cs:__imp_GetProcessHeap
0x14000388e  mov     r8, rdi; lpMem
0x140003891  xor     edx, edx; dwFlags
0x140003893  mov     rcx, rax; hHeap
0x140003896  call    cs:__imp_HeapFree
0x14000389c  mov     rdi, [rbx+70h]
0x1400038a0  mov     qword ptr [rbx+70h], 0
0x1400038a8  test    rdi, rdi
0x1400038ab  jz      short loc_1400038C1
0x1400038ad  call    cs:__imp_GetProcessHeap
0x1400038b3  mov     r8, rdi; lpMem
0x1400038b6  xor     edx, edx; dwFlags
0x1400038b8  mov     rcx, rax; hHeap
0x1400038bb  call    cs:__imp_HeapFree
0x1400038c1  mov     rdi, [rbx+30h]
0x1400038c5  mov     qword ptr [rbx+30h], 0
0x1400038cd  test    rdi, rdi
0x1400038d0  jz      short loc_1400038E6
0x1400038d2  call    cs:__imp_GetProcessHeap
0x1400038d8  mov     r8, rdi; lpMem
0x1400038db  xor     edx, edx; dwFlags
0x1400038dd  mov     rcx, rax; hHeap
0x1400038e0  call    cs:__imp_HeapFree
0x1400038e6  mov     rbx, [rsp+28h+arg_0]
0x1400038eb  add     rsp, 20h
0x1400038ef  pop     rdi
0x1400038f0  retn
```
