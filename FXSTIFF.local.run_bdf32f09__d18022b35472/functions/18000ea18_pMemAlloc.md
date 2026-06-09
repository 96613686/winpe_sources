# pMemAlloc

- ea: `0x18000ea18`
- end: `0x18000eab8`
- name: `pMemAlloc`
- size: `160`
- prototype: `LPVOID __fastcall(SIZE_T dwBytes)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x18000400c`
- `0x180004344`
- `0x180005d80`
- `0x1800069c0`
- `0x180007d60`
- `0x1800087a0`
- `0x1800091a0`
- `0x1800098c0`
- `0x18000e16c`
- `0x18000eafc`
- `0x18000ee14`
- `0x18000efb0`
- `0x180016304`
- `0x18001639c`
- `0x18001646c`
- `0x180016a08`
- `0x180016d30`
- `0x180016f40`
- `0x180017190`
- `0x180017280`
- `0x1800173a0`
- `0x1800174e0`
- `0x1800175a8`
- `0x18001795c`

## callees

- `0x18000ea18`
- `0x180016794`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000ea84`
- `KERNEL32!HeapAlloc` at `0x18000ea84`
- `KERNEL32!GetProcessHeap` at `0x18000ea44`
- `KERNEL32!GetProcessHeap` at `0x18000ea44`
- `KERNEL32!SetLastError` at `0x18000ea68`
- `KERNEL32!SetLastError` at `0x18000eaa4`
- `KERNEL32!SetLastError` at `0x18000ea68`
- `KERNEL32!SetLastError` at `0x18000eaa4`

## pseudocode

```c
LPVOID __fastcall pMemAlloc(SIZE_T dwBytes)
{
  LPVOID v2; // rax
  HANDLE ProcessHeap; // rax
  LPVOID v5; // rbx

  if ( pMemAllocUser )
  {
    v2 = pMemAllocUser(dwBytes);
  }
  else
  {
    ProcessHeap = hHeap;
    if ( !hHeap )
    {
      ProcessHeap = GetProcessHeap();
      pMemAllocUser = 0;
      pMemFreeUser = 0;
      if ( !ProcessHeap )
      {
        SetLastError(6u);
        return 0;
      }
      hHeap = ProcessHeap;
    }
    v2 = HeapAlloc(ProcessHeap, 8u, dwBytes);
  }
  v5 = v2;
  if ( !v2 )
  {
    fax_dprintf(L"MemAlloc() failed, size=%d", dwBytes);
    SetLastError(8u);
  }
  return v5;
}

```

## disassembly

```asm
0x18000ea18  mov     [rsp+arg_0], rbx
0x18000ea1d  push    rdi
0x18000ea1e  sub     rsp, 20h
0x18000ea22  mov     rax, cs:?pMemAllocUser@@3P6APEAX_K@ZEA; void * (*pMemAllocUser)(unsigned __int64)
0x18000ea29  mov     rdi, rcx
0x18000ea2c  test    rax, rax
0x18000ea2f  jz      short loc_18000EA38
0x18000ea31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea36  jmp     short loc_18000EA8A
0x18000ea38  mov     rax, cs:hHeap
0x18000ea3f  test    rax, rax
0x18000ea42  jnz     short loc_18000EA79
0x18000ea44  call    cs:__imp_GetProcessHeap
0x18000ea4a  mov     cs:?pMemAllocUser@@3P6APEAX_K@ZEA, 0; void * (*pMemAllocUser)(unsigned __int64)
0x18000ea55  mov     cs:?pMemFreeUser@@3P6AXPEAX@ZEA, 0; void (*pMemFreeUser)(void *)
0x18000ea60  test    rax, rax
0x18000ea63  jnz     short loc_18000EA72
0x18000ea65  lea     ecx, [rax+6]; dwErrCode
0x18000ea68  call    cs:__imp_SetLastError
0x18000ea6e  xor     eax, eax
0x18000ea70  jmp     short loc_18000EAAD
0x18000ea72  mov     cs:hHeap, rax
0x18000ea79  mov     r8, rdi; dwBytes
0x18000ea7c  mov     edx, 8; dwFlags
0x18000ea81  mov     rcx, rax; hHeap
0x18000ea84  call    cs:__imp_HeapAlloc
0x18000ea8a  mov     rbx, rax
0x18000ea8d  test    rax, rax
0x18000ea90  jnz     short loc_18000EAAA
0x18000ea92  mov     rdx, rdi
0x18000ea95  lea     rcx, aMemallocFailed; "MemAlloc() failed, size=%d"
0x18000ea9c  call    fax_dprintf
0x18000eaa1  lea     ecx, [rbx+8]; dwErrCode
0x18000eaa4  call    cs:__imp_SetLastError
0x18000eaaa  mov     rax, rbx
0x18000eaad  mov     rbx, [rsp+28h+arg_0]
0x18000eab2  add     rsp, 20h
0x18000eab6  pop     rdi
0x18000eab7  retn
```
