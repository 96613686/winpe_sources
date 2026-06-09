# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180005f98`
- end: `0x180006025`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b2c`
- `0x18000cfd0`
- `0x18000da94`
- `0x1800148c8`

## callees

- `0x180005f98`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180005fbc`
- `KERNEL32!GetProcessHeap` at `0x180005fe1`
- `KERNEL32!GetProcessHeap` at `0x180006006`
- `KERNEL32!GetProcessHeap` at `0x180005fbc`
- `KERNEL32!GetProcessHeap` at `0x180005fe1`
- `KERNEL32!GetProcessHeap` at `0x180006006`
- `KERNEL32!HeapFree` at `0x180005fca`
- `KERNEL32!HeapFree` at `0x180005fef`
- `KERNEL32!HeapFree` at `0x180006014`
- `KERNEL32!HeapFree` at `0x180005fca`
- `KERNEL32!HeapFree` at `0x180005fef`
- `KERNEL32!HeapFree` at `0x180006014`

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
0x180005f98  mov     [rsp+arg_0], rbx
0x180005f9d  push    rdi
0x180005f9e  sub     rsp, 20h
0x180005fa2  mov     rdi, [rcx+0B0h]
0x180005fa9  mov     rbx, rcx
0x180005fac  mov     qword ptr [rcx+0B0h], 0
0x180005fb7  test    rdi, rdi
0x180005fba  jz      short loc_180005FD0
0x180005fbc  call    cs:__imp_GetProcessHeap
0x180005fc2  mov     r8, rdi; lpMem
0x180005fc5  xor     edx, edx; dwFlags
0x180005fc7  mov     rcx, rax; hHeap
0x180005fca  call    cs:__imp_HeapFree
0x180005fd0  mov     rdi, [rbx+70h]
0x180005fd4  mov     qword ptr [rbx+70h], 0
0x180005fdc  test    rdi, rdi
0x180005fdf  jz      short loc_180005FF5
0x180005fe1  call    cs:__imp_GetProcessHeap
0x180005fe7  mov     r8, rdi; lpMem
0x180005fea  xor     edx, edx; dwFlags
0x180005fec  mov     rcx, rax; hHeap
0x180005fef  call    cs:__imp_HeapFree
0x180005ff5  mov     rdi, [rbx+30h]
0x180005ff9  mov     qword ptr [rbx+30h], 0
0x180006001  test    rdi, rdi
0x180006004  jz      short loc_18000601A
0x180006006  call    cs:__imp_GetProcessHeap
0x18000600c  mov     r8, rdi; lpMem
0x18000600f  xor     edx, edx; dwFlags
0x180006011  mov     rcx, rax; hHeap
0x180006014  call    cs:__imp_HeapFree
0x18000601a  mov     rbx, [rsp+28h+arg_0]
0x18000601f  add     rsp, 20h
0x180006023  pop     rdi
0x180006024  retn
```
