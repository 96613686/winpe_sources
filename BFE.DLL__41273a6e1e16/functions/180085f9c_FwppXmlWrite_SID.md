# FwppXmlWrite_SID

- ea: `0x180085f9c`
- end: `0x180086058`
- name: `FwppXmlWrite_SID`
- size: `188`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003bfb0`
- `0x18003c2e4`
- `0x1800818b4`
- `0x180086060`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x18003cbd0`
- `0x180058abc`
- `0x18005aa60`
- `0x180085f9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085fdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008601c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008601c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180085fcc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180085fcc`

## string_xrefs

- `0x18008602d`: `FwppXmlWrite_SID`
- `0x180085feb`: `ConvertSidToStringSidW`

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
0x180085f9c  mov     [rsp+arg_18], rbx
0x180085fa1  push    rdi
0x180085fa2  sub     rsp, 30h
0x180085fa6  mov     rax, cs:__security_cookie
0x180085fad  xor     rax, rsp
0x180085fb0  mov     [rsp+38h+var_10], rax
0x180085fb5  mov     rdi, rdx
0x180085fb8  mov     [rsp+38h+StringSid], 0
0x180085fc1  mov     rbx, rcx
0x180085fc4  lea     rdx, [rsp+38h+StringSid]; StringSid
0x180085fc9  mov     rcx, r8; Sid
0x180085fcc  call    cs:__imp_ConvertSidToStringSidW
0x180085fd3  nop     dword ptr [rax+rax+00h]
0x180085fd8  test    eax, eax
0x180085fda  jnz     short loc_180085FFC
0x180085fdc  call    cs:__imp_GetLastError
0x180085fe3  nop     dword ptr [rax+rax+00h]
0x180085fe8  mov     r8d, eax
0x180085feb  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSidW"
0x180085ff2  call    WfpReportSysErrorAsWinError
0x180085ff7  mov     rbx, rax
0x180085ffa  jmp     short loc_180086028
0x180085ffc  mov     rcx, [rsp+38h+StringSid]
0x180086001  call    FwppConvertUnicodeToUtf8Unsafe
0x180086006  mov     r8, rax
0x180086009  mov     rdx, rdi
0x18008600c  mov     rcx, rbx
0x18008600f  call    FwppXmlWriteElementUnsafe
0x180086014  mov     rcx, [rsp+38h+StringSid]; hMem
0x180086019  mov     rbx, rax
0x18008601c  call    cs:__imp_LocalFree
0x180086023  nop     dword ptr [rax+rax+00h]
0x180086028  test    rbx, rbx
0x18008602b  jz      short loc_18008603C
0x18008602d  lea     rdx, aFwppxmlwriteSi_0; "FwppXmlWrite_SID"
0x180086034  mov     rcx, rbx
0x180086037  call    WfpReportError
0x18008603c  mov     rax, rbx
0x18008603f  mov     rcx, [rsp+38h+var_10]
0x180086044  xor     rcx, rsp; StackCookie
0x180086047  call    __security_check_cookie
0x18008604c  mov     rbx, [rsp+38h+arg_18]
0x180086051  add     rsp, 30h
0x180086055  pop     rdi
0x180086056  retn
```
