# StartAddress

- ea: `0x180104b90`
- end: `0x180104c00`
- name: `StartAddress`
- size: `112`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180104b90`
- `0x180104da4`
- `0x180107c04`
- `0x180108e14`
- `0x18010dee4`
- `0x180110c8c`
- `0x18013b850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104b9e`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180104ba6`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180104ba6`

## pseudocode

```c
void __fastcall __noreturn StartAddress(_BYTE *Parameter)
{
  DWORD LastError; // eax
  unsigned int v3; // eax

  if ( !Parameter )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  *(_QWORD *)(sub_180108E14() + 960) = Parameter;
  if ( (unsigned int)sub_180110C8C() == 2 )
    Parameter[32] = (unsigned int)sub_18010DEE4(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))Parameter)(*((_QWORD *)Parameter + 1));
  sub_180104DA4(v3);
}

```

## disassembly

```asm
0x180104b90  push    rbx
0x180104b92  sub     rsp, 20h
0x180104b96  mov     rbx, rcx
0x180104b99  test    rcx, rcx
0x180104b9c  jnz     short loc_180104BAD
0x180104b9e  call    cs:__imp_GetLastError
0x180104ba4  mov     ecx, eax; dwExitCode
0x180104ba6  call    cs:ExitThread
0x180104bad  call    sub_180108E14
0x180104bb2  mov     [rax+3C0h], rbx
0x180104bb9  call    sub_180110C8C
0x180104bbe  cmp     eax, 2
0x180104bc1  jnz     short loc_180104BD3
0x180104bc3  lea     ecx, [rax-1]
0x180104bc6  call    sub_18010DEE4
0x180104bcb  test    eax, eax
0x180104bcd  setz    al
0x180104bd0  mov     [rbx+20h], al
0x180104bd3  mov     r10, 9E0C2E5B32D12870h
0x180104bdd  mov     rcx, [rbx+8]
0x180104be1  mov     rax, [rbx]
0x180104be4  call    cs:__guard_xfg_dispatch_icall_fptr
0x180104bea  mov     ecx, eax
0x180104bec  call    sub_180104DA4
0x180104bf2  mov     ecx, eax
0x180104bf4  call    sub_180107C04
0x180104bf9  nop
0x180104bfa  add     rsp, 20h
0x180104bfe  pop     rbx
0x180104bff  retn
```
