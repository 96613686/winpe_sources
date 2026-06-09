# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140008240`
- end: `0x1400082cd`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140007f3c`
- `0x14000b440`
- `0x14000c13c`
- `0x14000e7d4`

## callees

- `0x140008240`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008272`
- `KERNEL32!HeapFree` at `0x140008297`
- `KERNEL32!HeapFree` at `0x1400082bc`
- `KERNEL32!HeapFree` at `0x140008272`
- `KERNEL32!HeapFree` at `0x140008297`
- `KERNEL32!HeapFree` at `0x1400082bc`
- `KERNEL32!GetProcessHeap` at `0x140008264`
- `KERNEL32!GetProcessHeap` at `0x140008289`
- `KERNEL32!GetProcessHeap` at `0x1400082ae`
- `KERNEL32!GetProcessHeap` at `0x140008264`
- `KERNEL32!GetProcessHeap` at `0x140008289`
- `KERNEL32!GetProcessHeap` at `0x1400082ae`

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
0x140008240  mov     [rsp+arg_0], rbx
0x140008245  push    rdi
0x140008246  sub     rsp, 20h
0x14000824a  mov     rdi, [rcx+0B0h]
0x140008251  mov     rbx, rcx
0x140008254  mov     qword ptr [rcx+0B0h], 0
0x14000825f  test    rdi, rdi
0x140008262  jz      short loc_140008278
0x140008264  call    cs:__imp_GetProcessHeap
0x14000826a  mov     r8, rdi; lpMem
0x14000826d  xor     edx, edx; dwFlags
0x14000826f  mov     rcx, rax; hHeap
0x140008272  call    cs:__imp_HeapFree
0x140008278  mov     rdi, [rbx+70h]
0x14000827c  mov     qword ptr [rbx+70h], 0
0x140008284  test    rdi, rdi
0x140008287  jz      short loc_14000829D
0x140008289  call    cs:__imp_GetProcessHeap
0x14000828f  mov     r8, rdi; lpMem
0x140008292  xor     edx, edx; dwFlags
0x140008294  mov     rcx, rax; hHeap
0x140008297  call    cs:__imp_HeapFree
0x14000829d  mov     rdi, [rbx+30h]
0x1400082a1  mov     qword ptr [rbx+30h], 0
0x1400082a9  test    rdi, rdi
0x1400082ac  jz      short loc_1400082C2
0x1400082ae  call    cs:__imp_GetProcessHeap
0x1400082b4  mov     r8, rdi; lpMem
0x1400082b7  xor     edx, edx; dwFlags
0x1400082b9  mov     rcx, rax; hHeap
0x1400082bc  call    cs:__imp_HeapFree
0x1400082c2  mov     rbx, [rsp+28h+arg_0]
0x1400082c7  add     rsp, 20h
0x1400082cb  pop     rdi
0x1400082cc  retn
```
