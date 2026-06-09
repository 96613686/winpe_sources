# IkeSecurityDescriptorCreateFromSddl

- ea: `0x1800ecb24`
- end: `0x1800ecb76`
- name: `IkeSecurityDescriptorCreateFromSddl`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a08`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x1800ecb24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ecb46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ecb46`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ecb3c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ecb3c`

## string_xrefs

- `0x1800ecb53`: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- `0x1800ecb62`: `IkeSecurityDescriptorCreateFromSddl`

## pseudocode

```c
__int64 __fastcall IkeSecurityDescriptorCreateFromSddl(__int64 a1, PSECURITY_DESCRIPTOR *a2)
{
  __int64 v2; // rbx
  DWORD LastError; // eax
  __int64 v4; // rcx

  v2 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:(A;;GA;;;BA)(A;;GRGWGX;;;S-1-5-80-3044542841-3639452079-4096941652-1606687743-1256249853)(A;;GRGWGX;"
           ";;S-1-5-80-3088073201-1464728630-1879813800-1107566885-823218052)(A;;GRGX;;;S-1-5-80-3635958274-2059881490-22"
           "25992882-984577281-633327304)(A;;GRGWGX;;;S-1-5-80-3139157870-2983391045-3678747466-658725712-1809340420)(A;;"
           "GRGWGX;;;S-1-5-80-1510742542-3632397484-604094731-3920060944-1272132581)(A;;0x40;;;WD)",
          1u,
          a2,
          0) )
  {
    LastError = GetLastError();
    v2 = WfpReportSysErrorAsWinError(v4, "ConvertStringSecurityDescriptorToSecurityDescriptorW", LastError, 1);
  }
  return IkeReturnError(v2, "IkeSecurityDescriptorCreateFromSddl");
}

```

## disassembly

```asm
0x1800ecb24  push    rbx
0x1800ecb26  sub     rsp, 20h
0x1800ecb2a  mov     r8, rdx; SecurityDescriptor
0x1800ecb2d  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;GA;;;BA)(A;;GRGWGX;;;S-1-"...
0x1800ecb34  xor     ebx, ebx
0x1800ecb36  xor     r9d, r9d; SecurityDescriptorSize
0x1800ecb39  lea     edx, [rbx+1]; StringSDRevision
0x1800ecb3c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ecb42  test    eax, eax
0x1800ecb44  jnz     short loc_1800ECB62
0x1800ecb46  call    cs:__imp_GetLastError
0x1800ecb4c  mov     r8d, eax
0x1800ecb4f  lea     r9d, [rbx+1]
0x1800ecb53  lea     rdx, aConvertstrings_2; "ConvertStringSecurityDescriptorToSecuri"...
0x1800ecb5a  call    WfpReportSysErrorAsWinError
0x1800ecb5f  mov     rbx, rax
0x1800ecb62  lea     rdx, aIkesecuritydes; "IkeSecurityDescriptorCreateFromSddl"
0x1800ecb69  mov     rcx, rbx
0x1800ecb6c  add     rsp, 20h
0x1800ecb70  pop     rbx
0x1800ecb71  jmp     IkeReturnError
```
