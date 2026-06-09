# _anonymous_namespace_::IsValidSessionServiceRequest

- ea: `0x18003223c`
- end: `0x1800323b3`
- name: `_anonymous_namespace_::IsValidSessionServiceRequest`
- size: `375`
- prototype: `__int64 __fastcall(GUID *rguid, PSID pSid1, PSID pSid2, HANDLE ClientToken)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033e00`
- `0x180034078`
- `0x180034340`

## callees

- `0x180031fe4`
- `0x18003223c`
- `0x18003d864`
- `0x180049b50`
- `0x18004ad58`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003230b`
- `KERNEL32!LocalFree` at `0x180032316`
- `KERNEL32!LocalFree` at `0x18003230b`
- `KERNEL32!LocalFree` at `0x180032316`
- `ole32!StringFromGUID2` at `0x1800322b7`
- `ole32!StringFromGUID2` at `0x1800322b7`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18003228b`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800322a1`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18003228b`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800322a1`
- `ADVAPI32!EqualSid` at `0x18003236a`
- `ADVAPI32!EqualSid` at `0x18003236a`

## string_xrefs

- `0x1800322d8`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x18003233a`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x180032389`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`

## pseudocode

```c
char __fastcall anonymous_namespace_::IsValidSessionServiceRequest(
        GUID *rguid,
        PSID pSid1,
        PSID pSid2,
        HANDLE ClientToken)
{
  int pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v10; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[112]; // [rsp+50h] [rbp-B0h] BYREF

  if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) && ConvertSidToStringSidW(pSid1, &StringSid) )
  {
    if ( ConvertSidToStringSidW(pSid2, &v10) )
    {
      if ( !StringFromGUID2(rguid, sz, 39) )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      sz[39] = 0;
      sz[78] = 0;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
        L"Request from '%s' for session %s (Owner: %s)",
        v10,
        sz,
        StringSid);
      LocalFree(v10);
    }
    LocalFree(StringSid);
  }
  if ( !(unsigned int)anonymous_namespace_::QueryIsAdministrator(ClientToken) )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
      L"Request from administrator.");
    return 1;
  }
  if ( EqualSid(pSid1, pSid2) )
    return 1;
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)_logger + 168),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
    L"Request from non-session owner.");
  return 0;
}

```

## disassembly

```asm
0x18003223c  push    rbp
0x18003223e  push    rbx
0x18003223f  push    rsi
0x180032240  push    rdi
0x180032241  push    r14
0x180032243  push    r15
0x180032245  lea     rbp, [rsp-48h]
0x18003224a  sub     rsp, 148h
0x180032251  mov     rax, cs:__security_cookie
0x180032258  xor     rax, rsp
0x18003225b  mov     [rbp+70h+var_40], rax
0x18003225f  mov     rsi, rcx
0x180032262  xor     r15d, r15d
0x180032265  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003226c  mov     r14, r9
0x18003226f  mov     rdi, r8
0x180032272  mov     rbx, rdx
0x180032275  mov     rax, [rcx+40h]
0x180032279  cmp     [rcx+38h], rax
0x18003227d  jz      loc_18003231C
0x180032283  lea     rdx, [rsp+170h+StringSid]; StringSid
0x180032288  mov     rcx, rbx; Sid
0x18003228b  call    cs:__imp_ConvertSidToStringSidW
0x180032291  test    eax, eax
0x180032293  jz      loc_18003231C
0x180032299  lea     rdx, [rsp+170h+var_138]; StringSid
0x18003229e  mov     rcx, rdi; Sid
0x1800322a1  call    cs:__imp_ConvertSidToStringSidW
0x1800322a7  test    eax, eax
0x1800322a9  jz      short loc_180032311
0x1800322ab  lea     r8d, [r15+27h]; cchMax
0x1800322af  mov     rcx, rsi; rguid
0x1800322b2  lea     rdx, [rsp+170h+sz]; lpsz
0x1800322b7  call    cs:__imp_StringFromGUID2
0x1800322bd  test    eax, eax
0x1800322bf  jz      loc_180032399
0x1800322c5  mov     rax, [rsp+170h+StringSid]
0x1800322ca  lea     r8, aRequestFromSFo; "Request from '%s' for session %s (Owner"...
0x1800322d1  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800322d8  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800322df  mov     r9, [rsp+170h+var_138]
0x1800322e4  add     rcx, 38h ; '8'; this
0x1800322e8  mov     [rsp+170h+var_148], rax
0x1800322ed  lea     rax, [rsp+170h+sz]
0x1800322f2  mov     [rsp+170h+var_150], rax
0x1800322f7  mov     [rbp+70h+var_D2], r15w
0x1800322fc  mov     [rbp+70h+var_84], r15w
0x180032301  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180032306  mov     rcx, [rsp+170h+var_138]; hMem
0x18003230b  call    cs:__imp_LocalFree
0x180032311  mov     rcx, [rsp+170h+StringSid]; hMem
0x180032316  call    cs:__imp_LocalFree
0x18003231c  mov     rcx, r14; ClientToken
0x18003231f  call    _anonymous_namespace___QueryIsAdministrator
0x180032324  test    eax, eax
0x180032326  jnz     short loc_180032364
0x180032328  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003232f  lea     r8, aRequestFromAdm; "Request from administrator."
0x180032336  add     rcx, 38h ; '8'; this
0x18003233a  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180032341  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180032346  mov     al, 1
0x180032348  mov     rcx, [rbp+70h+var_40]
0x18003234c  xor     rcx, rsp; StackCookie
0x18003234f  call    __security_check_cookie
0x180032354  add     rsp, 148h
0x18003235b  pop     r15
0x18003235d  pop     r14
0x18003235f  pop     rdi
0x180032360  pop     rsi
0x180032361  pop     rbx
0x180032362  pop     rbp
0x180032363  retn
0x180032364  mov     rdx, rdi; pSid2
0x180032367  mov     rcx, rbx; pSid1
0x18003236a  call    cs:__imp_EqualSid
0x180032370  test    eax, eax
0x180032372  jnz     short loc_180032346
0x180032374  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003237b  lea     r8, aRequestFromNon; "Request from non-session owner."
0x180032382  add     rcx, 0A8h; this
0x180032389  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180032390  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180032395  xor     al, al
0x180032397  jmp     short loc_180032348
0x180032399  lea     rdx, _TI1J; pThrowInfo
0x1800323a0  mov     [rsp+170h+pExceptionObject], 8007000Eh
0x1800323a8  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x1800323ad  call    _CxxThrowException_0
```
