# File::~File(void)

- ea: `0x180002768`
- end: `0x1800027bb`
- name: `??1File@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001948`
- `0x180001e9c`
- `0x18000228c`
- `0x180002474`

## callees

- `0x180002768`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800027a2`
- `KERNEL32!HeapFree` at `0x1800027a2`
- `KERNEL32!GetProcessHeap` at `0x180002794`
- `KERNEL32!GetProcessHeap` at `0x180002794`
- `KERNEL32!CloseHandle` at `0x18000277e`
- `KERNEL32!CloseHandle` at `0x18000277e`

## pseudocode

```c
void __fastcall File::~File(HANDLE *this)
{
  HANDLE v2; // rdi
  HANDLE ProcessHeap; // rax

  if ( *this != (HANDLE)-1LL )
  {
    CloseHandle(*this);
    *this = (HANDLE)-1LL;
  }
  v2 = this[1];
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    this[1] = 0;
  }
}

```

## disassembly

```asm
0x180002768  mov     [rsp+arg_0], rbx
0x18000276d  push    rdi
0x18000276e  sub     rsp, 20h
0x180002772  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180002776  mov     rbx, rcx
0x180002779  jz      short loc_18000278B
0x18000277b  mov     rcx, [rcx]; hObject
0x18000277e  call    cs:__imp_CloseHandle
0x180002784  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000278b  mov     rdi, [rbx+8]
0x18000278f  test    rdi, rdi
0x180002792  jz      short loc_1800027B0
0x180002794  call    cs:__imp_GetProcessHeap
0x18000279a  mov     r8, rdi; lpMem
0x18000279d  xor     edx, edx; dwFlags
0x18000279f  mov     rcx, rax; hHeap
0x1800027a2  call    cs:__imp_HeapFree
0x1800027a8  mov     qword ptr [rbx+8], 0
0x1800027b0  mov     rbx, [rsp+28h+arg_0]
0x1800027b5  add     rsp, 20h
0x1800027b9  pop     rdi
0x1800027ba  retn
```
