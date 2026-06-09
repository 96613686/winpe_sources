# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180010dec`
- end: `0x180010e79`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180010920`
- `0x1800139c0`
- `0x180014484`
- `0x18001802f`

## callees

- `0x180010dec`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010e1e`
- `KERNEL32!HeapFree` at `0x180010e43`
- `KERNEL32!HeapFree` at `0x180010e68`
- `KERNEL32!HeapFree` at `0x180010e1e`
- `KERNEL32!HeapFree` at `0x180010e43`
- `KERNEL32!HeapFree` at `0x180010e68`
- `KERNEL32!GetProcessHeap` at `0x180010e10`
- `KERNEL32!GetProcessHeap` at `0x180010e35`
- `KERNEL32!GetProcessHeap` at `0x180010e5a`
- `KERNEL32!GetProcessHeap` at `0x180010e10`
- `KERNEL32!GetProcessHeap` at `0x180010e35`
- `KERNEL32!GetProcessHeap` at `0x180010e5a`

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
0x180010dec  mov     [rsp+arg_0], rbx
0x180010df1  push    rdi
0x180010df2  sub     rsp, 20h
0x180010df6  mov     rdi, [rcx+0B0h]
0x180010dfd  mov     rbx, rcx
0x180010e00  mov     qword ptr [rcx+0B0h], 0
0x180010e0b  test    rdi, rdi
0x180010e0e  jz      short loc_180010E24
0x180010e10  call    cs:__imp_GetProcessHeap
0x180010e16  mov     r8, rdi; lpMem
0x180010e19  xor     edx, edx; dwFlags
0x180010e1b  mov     rcx, rax; hHeap
0x180010e1e  call    cs:__imp_HeapFree
0x180010e24  mov     rdi, [rbx+70h]
0x180010e28  mov     qword ptr [rbx+70h], 0
0x180010e30  test    rdi, rdi
0x180010e33  jz      short loc_180010E49
0x180010e35  call    cs:__imp_GetProcessHeap
0x180010e3b  mov     r8, rdi; lpMem
0x180010e3e  xor     edx, edx; dwFlags
0x180010e40  mov     rcx, rax; hHeap
0x180010e43  call    cs:__imp_HeapFree
0x180010e49  mov     rdi, [rbx+30h]
0x180010e4d  mov     qword ptr [rbx+30h], 0
0x180010e55  test    rdi, rdi
0x180010e58  jz      short loc_180010E6E
0x180010e5a  call    cs:__imp_GetProcessHeap
0x180010e60  mov     r8, rdi; lpMem
0x180010e63  xor     edx, edx; dwFlags
0x180010e65  mov     rcx, rax; hHeap
0x180010e68  call    cs:__imp_HeapFree
0x180010e6e  mov     rbx, [rsp+28h+arg_0]
0x180010e73  add     rsp, 20h
0x180010e77  pop     rdi
0x180010e78  retn
```
