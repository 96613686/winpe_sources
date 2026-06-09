# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180005880`
- end: `0x18000590d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005710`
- `0x1800057e8`
- `0x180007368`
- `0x180009940`

## callees

- `0x180005880`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058ee`

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
0x180005880  mov     [rsp+arg_0], rbx
0x180005885  push    rdi
0x180005886  sub     rsp, 20h
0x18000588a  mov     rdi, [rcx+0B0h]
0x180005891  mov     rbx, rcx
0x180005894  mov     qword ptr [rcx+0B0h], 0
0x18000589f  test    rdi, rdi
0x1800058a2  jz      short loc_1800058B8
0x1800058a4  call    cs:__imp_GetProcessHeap
0x1800058aa  mov     r8, rdi; lpMem
0x1800058ad  xor     edx, edx; dwFlags
0x1800058af  mov     rcx, rax; hHeap
0x1800058b2  call    cs:__imp_HeapFree
0x1800058b8  mov     rdi, [rbx+70h]
0x1800058bc  mov     qword ptr [rbx+70h], 0
0x1800058c4  test    rdi, rdi
0x1800058c7  jz      short loc_1800058DD
0x1800058c9  call    cs:__imp_GetProcessHeap
0x1800058cf  mov     r8, rdi; lpMem
0x1800058d2  xor     edx, edx; dwFlags
0x1800058d4  mov     rcx, rax; hHeap
0x1800058d7  call    cs:__imp_HeapFree
0x1800058dd  mov     rdi, [rbx+30h]
0x1800058e1  mov     qword ptr [rbx+30h], 0
0x1800058e9  test    rdi, rdi
0x1800058ec  jz      short loc_180005902
0x1800058ee  call    cs:__imp_GetProcessHeap
0x1800058f4  mov     r8, rdi; lpMem
0x1800058f7  xor     edx, edx; dwFlags
0x1800058f9  mov     rcx, rax; hHeap
0x1800058fc  call    cs:__imp_HeapFree
0x180005902  mov     rbx, [rsp+28h+arg_0]
0x180005907  add     rsp, 20h
0x18000590b  pop     rdi
0x18000590c  retn
```
