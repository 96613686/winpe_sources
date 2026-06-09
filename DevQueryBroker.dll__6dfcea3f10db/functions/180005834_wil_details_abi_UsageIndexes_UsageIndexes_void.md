# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180005834`
- end: `0x1800058c1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800054e4`
- `0x18000807c`
- `0x180008b30`

## callees

- `0x180005834`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005866`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000588b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005866`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000588b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005858`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000587d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005858`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000587d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058a2`

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
0x180005834  mov     [rsp+arg_0], rbx
0x180005839  push    rdi
0x18000583a  sub     rsp, 20h
0x18000583e  mov     rdi, [rcx+0B0h]
0x180005845  mov     rbx, rcx
0x180005848  mov     qword ptr [rcx+0B0h], 0
0x180005853  test    rdi, rdi
0x180005856  jz      short loc_18000586C
0x180005858  call    cs:__imp_GetProcessHeap
0x18000585e  mov     r8, rdi; lpMem
0x180005861  xor     edx, edx; dwFlags
0x180005863  mov     rcx, rax; hHeap
0x180005866  call    cs:__imp_HeapFree
0x18000586c  mov     rdi, [rbx+70h]
0x180005870  mov     qword ptr [rbx+70h], 0
0x180005878  test    rdi, rdi
0x18000587b  jz      short loc_180005891
0x18000587d  call    cs:__imp_GetProcessHeap
0x180005883  mov     r8, rdi; lpMem
0x180005886  xor     edx, edx; dwFlags
0x180005888  mov     rcx, rax; hHeap
0x18000588b  call    cs:__imp_HeapFree
0x180005891  mov     rdi, [rbx+30h]
0x180005895  mov     qword ptr [rbx+30h], 0
0x18000589d  test    rdi, rdi
0x1800058a0  jz      short loc_1800058B6
0x1800058a2  call    cs:__imp_GetProcessHeap
0x1800058a8  mov     r8, rdi; lpMem
0x1800058ab  xor     edx, edx; dwFlags
0x1800058ad  mov     rcx, rax; hHeap
0x1800058b0  call    cs:__imp_HeapFree
0x1800058b6  mov     rbx, [rsp+28h+arg_0]
0x1800058bb  add     rsp, 20h
0x1800058bf  pop     rdi
0x1800058c0  retn
```
