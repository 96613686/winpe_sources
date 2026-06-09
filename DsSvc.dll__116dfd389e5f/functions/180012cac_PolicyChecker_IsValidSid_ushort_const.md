# PolicyChecker::IsValidSid(ushort const *)

- ea: `0x180012cac`
- end: `0x180012d4e`
- name: `?IsValidSid@PolicyChecker@@SAHPEBG@Z`
- size: `162`
- prototype: `__int64 __fastcall(LPCWSTR StringSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e364`
- `0x180012c70`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000c93c`
- `0x180012364`
- `0x180012cac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ce2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180012d2a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180012d2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180012cd6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180012cd6`

## string_xrefs

- `0x180012cfc`: `Unable to convert String %s to SID. HR=0x%x`
- `0x180012d12`: `PolicyChecker::IsValidSid`

## pseudocode

```c
__int64 __fastcall PolicyChecker::IsValidSid(LPCWSTR StringSid)
{
  PSID *v2; // rax
  unsigned int valid; // edi
  signed int LastError; // eax
  signed int v5; // ebx
  DSLogger *v6; // rax
  signed int v8; // [rsp+28h] [rbp-10h]
  PSID pSid; // [rsp+48h] [rbp+10h] BYREF

  pSid = 0;
  v2 = (PSID *)tlx::replace<void *,void * (*)(void *),&void * LocalFree(void *),0>(&pSid);
  if ( ConvertStringSidToSidW(StringSid, v2) )
    goto LABEL_5;
  valid = 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  v6 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  v8 = v5;
  DSLogger::LogError(
    v6,
    L"PolicyChecker::IsValidSid",
    0x178u,
    L"Unable to convert String %s to SID. HR=0x%x",
    StringSid,
    v8);
  if ( v5 >= 0 )
LABEL_5:
    valid = IsValidSid(pSid);
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&pSid);
  return valid;
}

```

## disassembly

```asm
0x180012cac  mov     rax, rsp
0x180012caf  mov     [rax+8], rbx
0x180012cb3  mov     [rax+18h], rsi
0x180012cb7  push    rdi
0x180012cb8  sub     rsp, 30h
0x180012cbc  mov     rsi, rcx
0x180012cbf  mov     qword ptr [rax+10h], 0
0x180012cc7  lea     rcx, [rax+10h]
0x180012ccb  call    ??$replace@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<void *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0> &)
0x180012cd0  mov     rdx, rax; Sid
0x180012cd3  mov     rcx, rsi; StringSid
0x180012cd6  call    cs:__imp_ConvertStringSidToSidW
0x180012cdc  test    eax, eax
0x180012cde  jnz     short loc_180012D25
0x180012ce0  xor     edi, edi
0x180012ce2  call    cs:__imp_GetLastError
0x180012ce8  mov     ebx, eax
0x180012cea  test    eax, eax
0x180012cec  jle     short loc_180012CF7
0x180012cee  movzx   ebx, ax
0x180012cf1  or      ebx, 80070000h
0x180012cf7  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012cfc  lea     r9, aUnableToConver; "Unable to convert String %s to SID. HR="...
0x180012d03  mov     [rsp+38h+var_10], ebx
0x180012d07  mov     r8d, 178h; unsigned int
0x180012d0d  mov     [rsp+38h+var_18], rsi
0x180012d12  lea     rdx, aPolicycheckerI; "PolicyChecker::IsValidSid"
0x180012d19  mov     rcx, rax; this
0x180012d1c  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012d21  test    ebx, ebx
0x180012d23  js      short loc_180012D32
0x180012d25  mov     rcx, [rsp+38h+pSid]; pSid
0x180012d2a  call    cs:__imp_IsValidSid
0x180012d30  mov     edi, eax
0x180012d32  lea     rcx, [rsp+38h+pSid]
0x180012d37  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180012d3c  mov     rbx, [rsp+38h+arg_0]
0x180012d41  mov     eax, edi
0x180012d43  mov     rsi, [rsp+38h+arg_10]
0x180012d48  add     rsp, 30h
0x180012d4c  pop     rdi
0x180012d4d  retn
```
