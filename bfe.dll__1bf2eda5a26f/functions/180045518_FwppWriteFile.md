# FwppWriteFile

- ea: `0x180045518`
- end: `0x18004559e`
- name: `FwppWriteFile`
- size: `134`
- prototype: `__int64 __fastcall(void *, const void *, DWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180024370`
- `0x180087854`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180045518`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045577`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004554a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004554a`

## string_xrefs

- `0x180045592`: `FwppWriteFile`
- `0x18008ab09`: `FwppWriteFile`
- `0x180045580`: `WriteFile`

## pseudocode

```c
__int64 __fastcall FwppWriteFile(void *a1, const void *a2, DWORD a3)
{
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 LastError; // r8
  const char *v8; // rdx
  __int64 v9; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-18h] BYREF

  NumberOfBytesWritten = 0;
  if ( WriteFile(a1, a2, a3, &NumberOfBytesWritten, 0) )
  {
    v5 = 0;
    if ( NumberOfBytesWritten == a3 )
      return v5;
    LastError = 112;
    v8 = "FwppWriteFile";
  }
  else
  {
    LastError = GetLastError();
    v8 = "WriteFile";
  }
  v9 = WfpReportSysErrorAsWinError(v4, v8, LastError);
  v5 = v9;
  if ( v9 )
    WfpReportError(v9, "FwppWriteFile");
  return v5;
}

```

## disassembly

```asm
0x180045518  mov     [rsp+arg_18], rbx
0x18004551d  push    rdi
0x18004551e  sub     rsp, 40h
0x180045522  mov     rax, cs:__security_cookie
0x180045529  xor     rax, rsp
0x18004552c  mov     [rsp+48h+var_10], rax
0x180045531  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180045536  mov     [rsp+48h+NumberOfBytesWritten], 0
0x18004553e  mov     edi, r8d
0x180045541  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18004554a  call    cs:__imp_WriteFile
0x180045550  test    eax, eax
0x180045552  jz      short loc_180045577
0x180045554  xor     ebx, ebx
0x180045556  cmp     [rsp+48h+NumberOfBytesWritten], edi
0x18004555a  jnz     short loc_18004558C
0x18004555c  mov     rax, rbx
0x18004555f  mov     rcx, [rsp+48h+var_10]
0x180045564  xor     rcx, rsp; StackCookie
0x180045567  call    __security_check_cookie
0x18004556c  mov     rbx, [rsp+48h+arg_18]
0x180045571  add     rsp, 40h
0x180045575  pop     rdi
0x180045576  retn
0x180045577  call    cs:__imp_GetLastError
0x18004557d  mov     r8d, eax
0x180045580  lea     rdx, aWritefile; "WriteFile"
0x180045587  jmp     loc_18008AAF8
0x18004558c  mov     r8d, 70h ; 'p'
0x180045592  lea     rdx, aFwppwritefile; "FwppWriteFile"
0x180045599  jmp     loc_18008AAF8
0x18008aaf8  call    WfpReportSysErrorAsWinError
0x18008aafd  mov     rbx, rax
0x18008ab00  test    rax, rax
0x18008ab03  jz      loc_18004555C
0x18008ab09  lea     rdx, aFwppwritefile; "FwppWriteFile"
0x18008ab10  mov     rcx, rax
0x18008ab13  call    WfpReportError
0x18008ab18  nop
0x18008ab19  jmp     loc_18004555C
```
