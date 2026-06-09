# FwppWriteFile

- ea: `0x1800473bc`
- end: `0x18004744f`
- name: `FwppWriteFile`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180026d90`
- `0x18008a794`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x1800473bc`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047422`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800473ee`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800473ee`

## string_xrefs

- `0x180047443`: `FwppWriteFile`
- `0x18008dc03`: `FwppWriteFile`
- `0x180047431`: `WriteFile`

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
0x1800473bc  mov     [rsp+arg_18], rbx
0x1800473c1  push    rdi
0x1800473c2  sub     rsp, 40h
0x1800473c6  mov     rax, cs:__security_cookie
0x1800473cd  xor     rax, rsp
0x1800473d0  mov     [rsp+48h+var_10], rax
0x1800473d5  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800473da  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1800473e2  mov     edi, r8d
0x1800473e5  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800473ee  call    cs:__imp_WriteFile
0x1800473f5  nop     dword ptr [rax+rax+00h]
0x1800473fa  test    eax, eax
0x1800473fc  jz      short loc_180047422
0x1800473fe  xor     ebx, ebx
0x180047400  cmp     [rsp+48h+NumberOfBytesWritten], edi
0x180047404  jnz     short loc_18004743D
0x180047406  mov     rax, rbx
0x180047409  mov     rcx, [rsp+48h+var_10]
0x18004740e  xor     rcx, rsp; StackCookie
0x180047411  call    __security_check_cookie
0x180047416  mov     rbx, [rsp+48h+arg_18]
0x18004741b  add     rsp, 40h
0x18004741f  pop     rdi
0x180047420  retn
0x180047422  call    cs:__imp_GetLastError
0x180047429  nop     dword ptr [rax+rax+00h]
0x18004742e  mov     r8d, eax
0x180047431  lea     rdx, aWritefile; "WriteFile"
0x180047438  jmp     loc_18008DBF2
0x18004743d  mov     r8d, 70h ; 'p'
0x180047443  lea     rdx, aFwppwritefile; "FwppWriteFile"
0x18004744a  jmp     loc_18008DBF2
0x18008dbf2  call    WfpReportSysErrorAsWinError
0x18008dbf7  mov     rbx, rax
0x18008dbfa  test    rax, rax
0x18008dbfd  jz      loc_180047406
0x18008dc03  lea     rdx, aFwppwritefile; "FwppWriteFile"
0x18008dc0a  mov     rcx, rax
0x18008dc0d  call    WfpReportError
0x18008dc12  nop
0x18008dc13  jmp     loc_180047406
```
