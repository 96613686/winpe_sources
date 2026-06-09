# DuplicateSID

- ea: `0x18006830c`
- end: `0x180068390`
- name: `DuplicateSID`
- size: `132`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180068398`

## callees

- `0x18006830c`

## import_xrefs

- `ADVAPI32!CopySid` at `0x180068349`
- `ADVAPI32!CopySid` at `0x180068349`
- `ADVAPI32!GetLengthSid` at `0x180068318`
- `ADVAPI32!GetLengthSid` at `0x180068318`
- `KERNEL32!SetLastError` at `0x18006837e`
- `KERNEL32!SetLastError` at `0x18006837e`
- `KERNEL32!GetLastError` at `0x180068353`
- `KERNEL32!GetLastError` at `0x180068353`
- `KERNEL32!HeapFree` at `0x180068369`
- `KERNEL32!HeapFree` at `0x180068369`
- `KERNEL32!HeapAlloc` at `0x180068331`
- `KERNEL32!HeapAlloc` at `0x180068331`
- `KERNEL32!GetProcessHeap` at `0x180068320`
- `KERNEL32!GetProcessHeap` at `0x18006835b`
- `KERNEL32!GetProcessHeap` at `0x180068320`
- `KERNEL32!GetProcessHeap` at `0x18006835b`

## pseudocode

```c
void *__fastcall DuplicateSID(PSID pSourceSid)
{
  DWORD LengthSid; // ebp
  HANDLE ProcessHeap; // rax
  void *v4; // rax
  void *v5; // rbx
  DWORD LastError; // edi
  HANDLE v7; // rax

  LengthSid = GetLengthSid(pSourceSid);
  ProcessHeap = GetProcessHeap();
  v4 = HeapAlloc(ProcessHeap, 8u, LengthSid);
  v5 = v4;
  if ( v4 )
  {
    LastError = 0;
    if ( !CopySid(LengthSid, v4, pSourceSid) )
    {
      LastError = GetLastError();
      v7 = GetProcessHeap();
      if ( HeapFree(v7, 0, v5) )
        v5 = 0;
    }
  }
  else
  {
    LastError = 14;
  }
  SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x18006830c  push    rbx
0x18006830e  push    rbp
0x18006830f  push    rsi
0x180068310  push    rdi
0x180068311  sub     rsp, 28h
0x180068315  mov     rsi, rcx
0x180068318  call    cs:__imp_GetLengthSid
0x18006831e  mov     ebp, eax
0x180068320  call    cs:__imp_GetProcessHeap
0x180068326  mov     r8d, ebp; dwBytes
0x180068329  mov     edx, 8; dwFlags
0x18006832e  mov     rcx, rax; hHeap
0x180068331  call    cs:__imp_HeapAlloc
0x180068337  mov     rbx, rax
0x18006833a  test    rax, rax
0x18006833d  jz      short loc_180068377
0x18006833f  mov     r8, rsi; pSourceSid
0x180068342  mov     rdx, rax; pDestinationSid
0x180068345  mov     ecx, ebp; nDestinationSidLength
0x180068347  xor     edi, edi
0x180068349  call    cs:__imp_CopySid
0x18006834f  test    eax, eax
0x180068351  jnz     short loc_18006837C
0x180068353  call    cs:__imp_GetLastError
0x180068359  mov     edi, eax
0x18006835b  call    cs:__imp_GetProcessHeap
0x180068361  mov     r8, rbx; lpMem
0x180068364  xor     edx, edx; dwFlags
0x180068366  mov     rcx, rax; hHeap
0x180068369  call    cs:__imp_HeapFree
0x18006836f  test    eax, eax
0x180068371  jz      short loc_18006837C
0x180068373  xor     ebx, ebx
0x180068375  jmp     short loc_18006837C
0x180068377  mov     edi, 0Eh
0x18006837c  mov     ecx, edi; dwErrCode
0x18006837e  call    cs:__imp_SetLastError
0x180068384  mov     rax, rbx
0x180068387  add     rsp, 28h
0x18006838b  pop     rdi
0x18006838c  pop     rsi
0x18006838d  pop     rbp
0x18006838e  pop     rbx
0x18006838f  retn
```
