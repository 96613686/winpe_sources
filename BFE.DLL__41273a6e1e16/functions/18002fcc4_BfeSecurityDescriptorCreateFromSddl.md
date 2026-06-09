# BfeSecurityDescriptorCreateFromSddl

- ea: `0x18002fcc4`
- end: `0x18002fd2e`
- name: `BfeSecurityDescriptorCreateFromSddl`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002fc14`
- `0x180032274`
- `0x18006800c`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x18002fcc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcde`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002fd1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002fd1c`

## string_xrefs

- `0x18002fced`: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- `0x18002fd01`: `BfeSecurityDescriptorCreateFromSddl`

## pseudocode

```c
__int64 __fastcall BfeSecurityDescriptorCreateFromSddl(const WCHAR *a1, PSECURITY_DESCRIPTOR *a2)
{
  __int64 v2; // rbx
  DWORD LastError; // eax
  __int64 v5; // rcx
  __int64 v6; // rax

  v2 = 0;
  if ( a1 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, a2, 0) )
    {
      LastError = GetLastError();
      v6 = WfpReportSysErrorAsWinError(v5, "ConvertStringSecurityDescriptorToSecurityDescriptorW", LastError);
      v2 = v6;
      if ( v6 )
        WfpReportError(v6, "BfeSecurityDescriptorCreateFromSddl");
    }
  }
  else
  {
    *a2 = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18002fcc4  push    rbx
0x18002fcc6  sub     rsp, 20h
0x18002fcca  xor     ebx, ebx
0x18002fccc  test    rcx, rcx
0x18002fccf  jnz     short loc_18002FD12
0x18002fcd1  mov     [rdx], rbx
0x18002fcd4  mov     rax, rbx
0x18002fcd7  add     rsp, 20h
0x18002fcdb  pop     rbx
0x18002fcdc  retn
0x18002fcde  call    cs:__imp_GetLastError
0x18002fce5  nop     dword ptr [rax+rax+00h]
0x18002fcea  mov     r8d, eax
0x18002fced  lea     rdx, aConvertstrings_2; "ConvertStringSecurityDescriptorToSecuri"...
0x18002fcf4  call    WfpReportSysErrorAsWinError
0x18002fcf9  mov     rbx, rax
0x18002fcfc  test    rax, rax
0x18002fcff  jz      short loc_18002FCD4
0x18002fd01  lea     rdx, aBfesecuritydes; "BfeSecurityDescriptorCreateFromSddl"
0x18002fd08  mov     rcx, rax
0x18002fd0b  call    WfpReportError
0x18002fd10  jmp     short loc_18002FCD4
0x18002fd12  xor     r9d, r9d; SecurityDescriptorSize
0x18002fd15  mov     r8, rdx; SecurityDescriptor
0x18002fd18  lea     edx, [r9+1]; StringSDRevision
0x18002fd1c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002fd23  nop     dword ptr [rax+rax+00h]
0x18002fd28  test    eax, eax
0x18002fd2a  jnz     short loc_18002FCD4
0x18002fd2c  jmp     short loc_18002FCDE
```
