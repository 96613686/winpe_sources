# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800114b4`
- end: `0x180011566`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `178`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180010fb8`
- `0x180014208`
- `0x180014d30`
- `0x180018dff`

## callees

- `0x1800114b4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800114ec`
- `KERNEL32!HeapFree` at `0x18001151d`
- `KERNEL32!HeapFree` at `0x18001154e`
- `KERNEL32!HeapFree` at `0x1800114ec`
- `KERNEL32!HeapFree` at `0x18001151d`
- `KERNEL32!HeapFree` at `0x18001154e`
- `KERNEL32!GetProcessHeap` at `0x1800114d8`
- `KERNEL32!GetProcessHeap` at `0x180011509`
- `KERNEL32!GetProcessHeap` at `0x18001153a`
- `KERNEL32!GetProcessHeap` at `0x1800114d8`
- `KERNEL32!GetProcessHeap` at `0x180011509`
- `KERNEL32!GetProcessHeap` at `0x18001153a`

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
0x1800114b4  mov     [rsp+arg_0], rbx
0x1800114b9  push    rdi
0x1800114ba  sub     rsp, 20h
0x1800114be  mov     rdi, [rcx+0B0h]
0x1800114c5  mov     rbx, rcx
0x1800114c8  mov     qword ptr [rcx+0B0h], 0
0x1800114d3  test    rdi, rdi
0x1800114d6  jz      short loc_1800114F8
0x1800114d8  call    cs:__imp_GetProcessHeap
0x1800114df  nop     dword ptr [rax+rax+00h]
0x1800114e4  mov     r8, rdi; lpMem
0x1800114e7  xor     edx, edx; dwFlags
0x1800114e9  mov     rcx, rax; hHeap
0x1800114ec  call    cs:__imp_HeapFree
0x1800114f3  nop     dword ptr [rax+rax+00h]
0x1800114f8  mov     rdi, [rbx+70h]
0x1800114fc  mov     qword ptr [rbx+70h], 0
0x180011504  test    rdi, rdi
0x180011507  jz      short loc_180011529
0x180011509  call    cs:__imp_GetProcessHeap
0x180011510  nop     dword ptr [rax+rax+00h]
0x180011515  mov     r8, rdi; lpMem
0x180011518  xor     edx, edx; dwFlags
0x18001151a  mov     rcx, rax; hHeap
0x18001151d  call    cs:__imp_HeapFree
0x180011524  nop     dword ptr [rax+rax+00h]
0x180011529  mov     rdi, [rbx+30h]
0x18001152d  mov     qword ptr [rbx+30h], 0
0x180011535  test    rdi, rdi
0x180011538  jz      short loc_18001155A
0x18001153a  call    cs:__imp_GetProcessHeap
0x180011541  nop     dword ptr [rax+rax+00h]
0x180011546  mov     r8, rdi; lpMem
0x180011549  xor     edx, edx; dwFlags
0x18001154b  mov     rcx, rax; hHeap
0x18001154e  call    cs:__imp_HeapFree
0x180011555  nop     dword ptr [rax+rax+00h]
0x18001155a  mov     rbx, [rsp+28h+arg_0]
0x18001155f  add     rsp, 20h
0x180011563  pop     rdi
0x180011564  retn
```
