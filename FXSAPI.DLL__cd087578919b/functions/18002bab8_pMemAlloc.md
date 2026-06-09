# pMemAlloc

- ea: `0x18002bab8`
- end: `0x18002bb50`
- name: `pMemAlloc`
- size: `152`
- prototype: `__int64 __fastcall(SIZE_T dwBytes)`
- caller_count: `39`
- callee_count: `4`
- tags: ``

## callers

- `0x180004394`
- `0x180006308`
- `0x180009dd0`
- `0x18000a9f0`
- `0x180011ed0`
- `0x180012760`
- `0x1800129e0`
- `0x180015040`
- `0x180016278`
- `0x180016964`
- `0x1800190d0`
- `0x18001e5e0`
- `0x180024ed0`
- `0x180025104`
- `0x180025df0`
- `0x180027e30`
- `0x180028ef0`
- `0x18002b090`
- `0x18002bc50`
- `0x18002bcf8`
- `0x18002c7bc`
- `0x18002c890`
- `0x18002d224`
- `0x18002dff4`
- `0x18002ed50`
- `0x18002fbc8`
- `0x180030230`
- `0x180031e24`
- `0x180031f94`
- `0x180033a24`
- `0x180033af4`
- `0x180033ea4`
- `0x180036dbc`
- `0x180038b68`
- `0x180039128`
- `0x180039a24`
- `0x18003a5ec`
- `0x18003a860`
- `0x18003c0e8`

## callees

- `0x18002ba60`
- `0x18002bab8`
- `0x18002d0e4`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002bae4`
- `KERNEL32!GetProcessHeap` at `0x18002bae4`
- `KERNEL32!SetLastError` at `0x18002bb35`
- `KERNEL32!SetLastError` at `0x18002bb35`
- `KERNEL32!HeapAlloc` at `0x18002bb0f`
- `KERNEL32!HeapAlloc` at `0x18002bb0f`

## pseudocode

```c
LPVOID __fastcall pMemAlloc(SIZE_T dwBytes)
{
  LPVOID v2; // rax
  HANDLE v3; // rcx
  HANDLE ProcessHeap; // rax
  LPVOID v6; // rbx

  if ( pMemAllocUser )
  {
    v2 = pMemAllocUser(dwBytes);
  }
  else
  {
    v3 = hHeap;
    if ( !hHeap )
    {
      ProcessHeap = GetProcessHeap();
      if ( !(unsigned int)HeapExistingInitialize(ProcessHeap) )
        return 0;
      v3 = hHeap;
    }
    v2 = HeapAlloc(v3, 8u, dwBytes);
  }
  v6 = v2;
  if ( !v2 )
  {
    fax_dprintf(L"MemAlloc() failed, size=%d", dwBytes);
    SetLastError(8u);
  }
  return v6;
}

```

## disassembly

```asm
0x18002bab8  mov     [rsp+arg_0], rbx
0x18002babd  push    rdi
0x18002babe  sub     rsp, 20h
0x18002bac2  mov     rax, cs:?pMemAllocUser@@3P6APEAX_K@ZEA; void * (*pMemAllocUser)(unsigned __int64)
0x18002bac9  mov     rdi, rcx
0x18002bacc  test    rax, rax
0x18002bacf  jz      short loc_18002BAD8
0x18002bad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bad6  jmp     short loc_18002BB1B
0x18002bad8  mov     rcx, cs:hHeap
0x18002badf  test    rcx, rcx
0x18002bae2  jnz     short loc_18002BB07
0x18002bae4  call    cs:__imp_GetProcessHeap
0x18002baeb  nop     dword ptr [rax+rax+00h]
0x18002baf0  mov     rcx, rax
0x18002baf3  call    HeapExistingInitialize
0x18002baf8  test    eax, eax
0x18002bafa  jnz     short loc_18002BB00
0x18002bafc  xor     eax, eax
0x18002bafe  jmp     short loc_18002BB44
0x18002bb00  mov     rcx, cs:hHeap; hHeap
0x18002bb07  mov     r8, rdi; dwBytes
0x18002bb0a  mov     edx, 8; dwFlags
0x18002bb0f  call    cs:__imp_HeapAlloc
0x18002bb16  nop     dword ptr [rax+rax+00h]
0x18002bb1b  mov     rbx, rax
0x18002bb1e  test    rax, rax
0x18002bb21  jnz     short loc_18002BB41
0x18002bb23  mov     rdx, rdi
0x18002bb26  lea     rcx, aMemallocFailed; "MemAlloc() failed, size=%d"
0x18002bb2d  call    fax_dprintf
0x18002bb32  lea     ecx, [rbx+8]; dwErrCode
0x18002bb35  call    cs:__imp_SetLastError
0x18002bb3c  nop     dword ptr [rax+rax+00h]
0x18002bb41  mov     rax, rbx
0x18002bb44  mov     rbx, [rsp+28h+arg_0]
0x18002bb49  add     rsp, 20h
0x18002bb4d  pop     rdi
0x18002bb4e  retn
```
