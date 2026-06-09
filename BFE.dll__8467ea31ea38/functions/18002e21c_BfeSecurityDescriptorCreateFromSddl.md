# BfeSecurityDescriptorCreateFromSddl

- ea: `0x18002e21c`
- end: `0x18002e279`
- name: `BfeSecurityDescriptorCreateFromSddl`
- size: `93`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e174`
- `0x1800476a0`
- `0x180065b00`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x18002e21c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e235`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e26d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002e26d`

## string_xrefs

- `0x18002e23e`: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- `0x18002e252`: `BfeSecurityDescriptorCreateFromSddl`

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
0x18002e21c  push    rbx
0x18002e21e  sub     rsp, 20h
0x18002e222  xor     ebx, ebx
0x18002e224  test    rcx, rcx
0x18002e227  jnz     short loc_18002E263
0x18002e229  mov     [rdx], rbx
0x18002e22c  mov     rax, rbx
0x18002e22f  add     rsp, 20h
0x18002e233  pop     rbx
0x18002e234  retn
0x18002e235  call    cs:__imp_GetLastError
0x18002e23b  mov     r8d, eax
0x18002e23e  lea     rdx, aConvertstrings_2; "ConvertStringSecurityDescriptorToSecuri"...
0x18002e245  call    WfpReportSysErrorAsWinError
0x18002e24a  mov     rbx, rax
0x18002e24d  test    rax, rax
0x18002e250  jz      short loc_18002E22C
0x18002e252  lea     rdx, aBfesecuritydes; "BfeSecurityDescriptorCreateFromSddl"
0x18002e259  mov     rcx, rax
0x18002e25c  call    WfpReportError
0x18002e261  jmp     short loc_18002E22C
0x18002e263  xor     r9d, r9d; SecurityDescriptorSize
0x18002e266  mov     r8, rdx; SecurityDescriptor
0x18002e269  lea     edx, [r9+1]; StringSDRevision
0x18002e26d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002e273  test    eax, eax
0x18002e275  jnz     short loc_18002E22C
0x18002e277  jmp     short loc_18002E235
```
