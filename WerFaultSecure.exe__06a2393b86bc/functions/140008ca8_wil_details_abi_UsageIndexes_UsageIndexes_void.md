# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140008ca8`
- end: `0x140008d35`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140008920`
- `0x14000b1e8`
- `0x14000bcf8`
- `0x14001149d`

## callees

- `0x140008ca8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ccc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008d16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ccc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008d16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008cda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008cff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008d24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008cda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008cff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008d24`

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
0x140008ca8  mov     [rsp+arg_0], rbx
0x140008cad  push    rdi
0x140008cae  sub     rsp, 20h
0x140008cb2  mov     rdi, [rcx+0B0h]
0x140008cb9  mov     rbx, rcx
0x140008cbc  mov     qword ptr [rcx+0B0h], 0
0x140008cc7  test    rdi, rdi
0x140008cca  jz      short loc_140008CE0
0x140008ccc  call    cs:__imp_GetProcessHeap
0x140008cd2  mov     r8, rdi; lpMem
0x140008cd5  xor     edx, edx; dwFlags
0x140008cd7  mov     rcx, rax; hHeap
0x140008cda  call    cs:__imp_HeapFree
0x140008ce0  mov     rdi, [rbx+70h]
0x140008ce4  mov     qword ptr [rbx+70h], 0
0x140008cec  test    rdi, rdi
0x140008cef  jz      short loc_140008D05
0x140008cf1  call    cs:__imp_GetProcessHeap
0x140008cf7  mov     r8, rdi; lpMem
0x140008cfa  xor     edx, edx; dwFlags
0x140008cfc  mov     rcx, rax; hHeap
0x140008cff  call    cs:__imp_HeapFree
0x140008d05  mov     rdi, [rbx+30h]
0x140008d09  mov     qword ptr [rbx+30h], 0
0x140008d11  test    rdi, rdi
0x140008d14  jz      short loc_140008D2A
0x140008d16  call    cs:__imp_GetProcessHeap
0x140008d1c  mov     r8, rdi; lpMem
0x140008d1f  xor     edx, edx; dwFlags
0x140008d21  mov     rcx, rax; hHeap
0x140008d24  call    cs:__imp_HeapFree
0x140008d2a  mov     rbx, [rsp+28h+arg_0]
0x140008d2f  add     rsp, 20h
0x140008d33  pop     rdi
0x140008d34  retn
```
