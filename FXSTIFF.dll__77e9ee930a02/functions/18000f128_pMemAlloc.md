# pMemAlloc

- ea: `0x18000f128`
- end: `0x18000f1c0`
- name: `pMemAlloc`
- size: `152`
- prototype: `LPVOID __fastcall(SIZE_T dwBytes)`
- caller_count: `24`
- callee_count: `4`
- tags: ``

## callers

- `0x180004050`
- `0x18000438c`
- `0x180005ed0`
- `0x180006bb0`
- `0x180008070`
- `0x180008b70`
- `0x180009600`
- `0x180009d40`
- `0x18000e784`
- `0x18000f20c`
- `0x18000f550`
- `0x18000f710`
- `0x180016ff0`
- `0x180017098`
- `0x18001716c`
- `0x180017744`
- `0x180017aa0`
- `0x180017cb0`
- `0x180017f10`
- `0x180018000`
- `0x180018130`
- `0x180018270`
- `0x180018340`
- `0x180018718`

## callees

- `0x18000f0dc`
- `0x18000f128`
- `0x1800174d8`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000f17f`
- `KERNEL32!HeapAlloc` at `0x18000f17f`
- `KERNEL32!GetProcessHeap` at `0x18000f154`
- `KERNEL32!GetProcessHeap` at `0x18000f154`
- `KERNEL32!SetLastError` at `0x18000f1a5`
- `KERNEL32!SetLastError` at `0x18000f1a5`

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
0x18000f128  mov     [rsp+arg_0], rbx
0x18000f12d  push    rdi
0x18000f12e  sub     rsp, 20h
0x18000f132  mov     rax, cs:?pMemAllocUser@@3P6APEAX_K@ZEA; void * (*pMemAllocUser)(unsigned __int64)
0x18000f139  mov     rdi, rcx
0x18000f13c  test    rax, rax
0x18000f13f  jz      short loc_18000F148
0x18000f141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f146  jmp     short loc_18000F18B
0x18000f148  mov     rcx, cs:hHeap
0x18000f14f  test    rcx, rcx
0x18000f152  jnz     short loc_18000F177
0x18000f154  call    cs:__imp_GetProcessHeap
0x18000f15b  nop     dword ptr [rax+rax+00h]
0x18000f160  mov     rcx, rax
0x18000f163  call    HeapExistingInitialize
0x18000f168  test    eax, eax
0x18000f16a  jnz     short loc_18000F170
0x18000f16c  xor     eax, eax
0x18000f16e  jmp     short loc_18000F1B4
0x18000f170  mov     rcx, cs:hHeap; hHeap
0x18000f177  mov     r8, rdi; dwBytes
0x18000f17a  mov     edx, 8; dwFlags
0x18000f17f  call    cs:__imp_HeapAlloc
0x18000f186  nop     dword ptr [rax+rax+00h]
0x18000f18b  mov     rbx, rax
0x18000f18e  test    rax, rax
0x18000f191  jnz     short loc_18000F1B1
0x18000f193  mov     rdx, rdi
0x18000f196  lea     rcx, aMemallocFailed; "MemAlloc() failed, size=%d"
0x18000f19d  call    fax_dprintf
0x18000f1a2  lea     ecx, [rbx+8]; dwErrCode
0x18000f1a5  call    cs:__imp_SetLastError
0x18000f1ac  nop     dword ptr [rax+rax+00h]
0x18000f1b1  mov     rax, rbx
0x18000f1b4  mov     rbx, [rsp+28h+arg_0]
0x18000f1b9  add     rsp, 20h
0x18000f1bd  pop     rdi
0x18000f1be  retn
```
