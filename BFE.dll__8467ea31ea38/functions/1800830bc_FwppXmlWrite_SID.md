# FwppXmlWrite_SID

- ea: `0x1800830bc`
- end: `0x180083165`
- name: `FwppXmlWrite_SID`
- size: `169`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003189c`
- `0x180031bcc`
- `0x18007ea64`
- `0x180083170`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180032494`
- `0x180056bf4`
- `0x180058b30`
- `0x1800830bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800830f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800830f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083130`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800830ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800830ec`

## string_xrefs

- `0x1800830ff`: `ConvertSidToStringSidW`
- `0x18008313b`: `FwppXmlWrite_SID`

## pseudocode

```c
__int64 __fastcall FwppXmlWrite_SID(__int64 a1, __int64 a2, void *a3)
{
  DWORD LastError; // eax
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  LPWSTR StringSid; // [rsp+20h] [rbp-18h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a3, &StringSid) )
  {
    v8 = FwppConvertUnicodeToUtf8Unsafe(StringSid);
    v7 = FwppXmlWriteElementUnsafe(a1, a2, v8);
    LocalFree(StringSid);
  }
  else
  {
    LastError = GetLastError();
    v7 = WfpReportSysErrorAsWinError(v6, "ConvertSidToStringSidW", LastError);
  }
  if ( v7 )
    WfpReportError(v7, "FwppXmlWrite_SID");
  return v7;
}

```

## disassembly

```asm
0x1800830bc  mov     [rsp+arg_18], rbx
0x1800830c1  push    rdi
0x1800830c2  sub     rsp, 30h
0x1800830c6  mov     rax, cs:__security_cookie
0x1800830cd  xor     rax, rsp
0x1800830d0  mov     [rsp+38h+var_10], rax
0x1800830d5  mov     rdi, rdx
0x1800830d8  mov     [rsp+38h+StringSid], 0
0x1800830e1  mov     rbx, rcx
0x1800830e4  lea     rdx, [rsp+38h+StringSid]; StringSid
0x1800830e9  mov     rcx, r8; Sid
0x1800830ec  call    cs:__imp_ConvertSidToStringSidW
0x1800830f2  test    eax, eax
0x1800830f4  jnz     short loc_180083110
0x1800830f6  call    cs:__imp_GetLastError
0x1800830fc  mov     r8d, eax
0x1800830ff  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSidW"
0x180083106  call    WfpReportSysErrorAsWinError
0x18008310b  mov     rbx, rax
0x18008310e  jmp     short loc_180083136
0x180083110  mov     rcx, [rsp+38h+StringSid]
0x180083115  call    FwppConvertUnicodeToUtf8Unsafe
0x18008311a  mov     r8, rax
0x18008311d  mov     rdx, rdi
0x180083120  mov     rcx, rbx
0x180083123  call    FwppXmlWriteElementUnsafe
0x180083128  mov     rcx, [rsp+38h+StringSid]; hMem
0x18008312d  mov     rbx, rax
0x180083130  call    cs:__imp_LocalFree
0x180083136  test    rbx, rbx
0x180083139  jz      short loc_18008314A
0x18008313b  lea     rdx, aFwppxmlwriteSi_0; "FwppXmlWrite_SID"
0x180083142  mov     rcx, rbx
0x180083145  call    WfpReportError
0x18008314a  mov     rax, rbx
0x18008314d  mov     rcx, [rsp+38h+var_10]
0x180083152  xor     rcx, rsp; StackCookie
0x180083155  call    __security_check_cookie
0x18008315a  mov     rbx, [rsp+38h+arg_18]
0x18008315f  add     rsp, 30h
0x180083163  pop     rdi
0x180083164  retn
```
