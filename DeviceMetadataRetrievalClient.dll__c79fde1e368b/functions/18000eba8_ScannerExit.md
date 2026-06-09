# _ScannerExit

- ea: `0x18000eba8`
- end: `0x18000ec5e`
- name: `_ScannerExit`
- size: `182`
- prototype: `void __fastcall(char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800041a0`
- `0x180004320`
- `0x18000d64c`

## callees

- `0x18000eba8`
- `0x1800136c6`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000ebc7`
- `KERNEL32!GetProcessHeap` at `0x18000ebe4`
- `KERNEL32!GetProcessHeap` at `0x18000ec01`
- `KERNEL32!GetProcessHeap` at `0x18000ec3f`
- `KERNEL32!GetProcessHeap` at `0x18000ebc7`
- `KERNEL32!GetProcessHeap` at `0x18000ebe4`
- `KERNEL32!GetProcessHeap` at `0x18000ec01`
- `KERNEL32!GetProcessHeap` at `0x18000ec3f`
- `KERNEL32!HeapFree` at `0x18000ebd5`
- `KERNEL32!HeapFree` at `0x18000ebf2`
- `KERNEL32!HeapFree` at `0x18000ec0f`
- `KERNEL32!HeapFree` at `0x18000ec4d`
- `KERNEL32!HeapFree` at `0x18000ebd5`
- `KERNEL32!HeapFree` at `0x18000ebf2`
- `KERNEL32!HeapFree` at `0x18000ec0f`
- `KERNEL32!HeapFree` at `0x18000ec4d`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec1f`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec29`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec1f`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec29`

## pseudocode

```c
void __fastcall ScannerExit(char *a1)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  HANDLE v8; // rax

  if ( a1 )
  {
    v1 = (void *)*((_QWORD *)a1 + 1);
    if ( v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    v4 = (void *)*((_QWORD *)a1 + 2);
    if ( v4 )
    {
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v4);
    }
    v6 = (void *)*((_QWORD *)a1 + 3);
    if ( v6 )
    {
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
    }
    if ( *((_DWORD *)a1 + 16) )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
      DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
    }
    memset_0(a1, 0, 0x98u);
    v8 = GetProcessHeap();
    HeapFree(v8, 0, a1);
  }
}

```

## disassembly

```asm
0x18000eba8  test    rcx, rcx
0x18000ebab  jz      locret_18000EC5D
0x18000ebb1  mov     [rsp+arg_0], rbx
0x18000ebb6  push    rdi
0x18000ebb7  sub     rsp, 20h
0x18000ebbb  mov     rdi, [rcx+8]
0x18000ebbf  mov     rbx, rcx
0x18000ebc2  test    rdi, rdi
0x18000ebc5  jz      short loc_18000EBDB
0x18000ebc7  call    cs:__imp_GetProcessHeap
0x18000ebcd  mov     r8, rdi; lpMem
0x18000ebd0  xor     edx, edx; dwFlags
0x18000ebd2  mov     rcx, rax; hHeap
0x18000ebd5  call    cs:__imp_HeapFree
0x18000ebdb  mov     rdi, [rbx+10h]
0x18000ebdf  test    rdi, rdi
0x18000ebe2  jz      short loc_18000EBF8
0x18000ebe4  call    cs:__imp_GetProcessHeap
0x18000ebea  mov     r8, rdi; lpMem
0x18000ebed  xor     edx, edx; dwFlags
0x18000ebef  mov     rcx, rax; hHeap
0x18000ebf2  call    cs:__imp_HeapFree
0x18000ebf8  mov     rdi, [rbx+18h]
0x18000ebfc  test    rdi, rdi
0x18000ebff  jz      short loc_18000EC15
0x18000ec01  call    cs:__imp_GetProcessHeap
0x18000ec07  mov     r8, rdi; lpMem
0x18000ec0a  xor     edx, edx; dwFlags
0x18000ec0c  mov     rcx, rax; hHeap
0x18000ec0f  call    cs:__imp_HeapFree
0x18000ec15  cmp     dword ptr [rbx+40h], 0
0x18000ec19  jz      short loc_18000EC2F
0x18000ec1b  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000ec1f  call    cs:__imp_DeleteCriticalSection
0x18000ec25  lea     rcx, [rbx+70h]; lpCriticalSection
0x18000ec29  call    cs:__imp_DeleteCriticalSection
0x18000ec2f  xor     edx, edx; Val
0x18000ec31  mov     r8d, 98h; Size
0x18000ec37  mov     rcx, rbx; void *
0x18000ec3a  call    memset_0
0x18000ec3f  call    cs:__imp_GetProcessHeap
0x18000ec45  mov     r8, rbx; lpMem
0x18000ec48  xor     edx, edx; dwFlags
0x18000ec4a  mov     rcx, rax; hHeap
0x18000ec4d  call    cs:__imp_HeapFree
0x18000ec53  mov     rbx, [rsp+28h+arg_0]
0x18000ec58  add     rsp, 20h
0x18000ec5c  pop     rdi
0x18000ec5d  retn
```
