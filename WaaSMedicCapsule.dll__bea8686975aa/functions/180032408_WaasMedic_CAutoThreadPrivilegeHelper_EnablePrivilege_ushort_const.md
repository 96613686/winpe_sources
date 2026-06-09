# WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(ushort const *)

- ea: `0x180032408`
- end: `0x180032551`
- name: `?EnablePrivilege@CAutoThreadPrivilegeHelper@WaasMedic@@QEAAJPEBG@Z`
- size: `329`
- prototype: `int(WaasMedic::CAutoThreadPrivilegeHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002c2a8`
- `0x18003100c`
- `0x180031224`
- `0x18004b3e8`
- `0x18005b214`

## callees

- `0x180003bb0`
- `0x18002543c`
- `0x180031f54`
- `0x180032408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032506`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800324d1`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800324d1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003246a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003246a`

## string_xrefs

- `0x1800324f0`: `Failed to enable the requested privilege: %s, 0x%08X`
- `0x180032489`: `Failed to lookup the %s privilege value: 0x%08X`
- `0x180032441`: `Failed to acquire thread token: 0%x08X`
- `0x18003251b`: `Failed to assign the requested privileges: %s, 0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
        WaasMedic::CAutoThreadPrivilegeHelper *this,
        const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  int v5; // eax
  signed int v6; // eax
  void *v7; // rcx
  signed int v8; // eax
  signed int LastError; // eax
  _LUID Luid; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  v2 = 0;
  if ( *((_BYTE *)this + 8)
    || (v5 = WaasMedic::CAutoThreadPrivilegeHelper::AcquireThreadToken((PHANDLE)this), v2 = v5, v5 >= 0) )
  {
    Luid = 0;
    if ( LookupPrivilegeValueW(0, a2, &Luid) )
    {
      v7 = *(void **)this;
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      if ( AdjustTokenPrivileges(v7, 0, &NewState, 0x10u, 0, 0) )
      {
        if ( GetLastError() == 1300 )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
          LogLevelW(2u, L"Failed to assign the requested privileges: %s, 0x%08X", a2, v2);
        }
      }
      else
      {
        v8 = GetLastError();
        v2 = v8;
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
        LogLevelW(2u, L"Failed to enable the requested privilege: %s, 0x%08X", a2, v2);
      }
    }
    else
    {
      v6 = GetLastError();
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      LogLevelW(2u, L"Failed to lookup the %s privilege value: 0x%08X", a2, v2);
    }
  }
  else
  {
    LogLevelW(2u, L"Failed to acquire thread token: 0%x08X", (unsigned int)v5);
  }
  return v2;
}

```

## disassembly

```asm
0x180032408  mov     [rsp+arg_10], rbx
0x18003240d  mov     [rsp+arg_18], rsi
0x180032412  push    rdi
0x180032413  sub     rsp, 50h
0x180032417  mov     rax, cs:__security_cookie
0x18003241e  xor     rax, rsp
0x180032421  mov     [rsp+58h+var_10], rax
0x180032426  xor     ebx, ebx
0x180032428  mov     rdi, rdx
0x18003242b  mov     rsi, rcx
0x18003242e  cmp     [rcx+8], bl
0x180032431  jnz     short loc_180032457
0x180032433  call    ?AcquireThreadToken@CAutoThreadPrivilegeHelper@WaasMedic@@AEAAJXZ; WaasMedic::CAutoThreadPrivilegeHelper::AcquireThreadToken(void)
0x180032438  mov     ebx, eax
0x18003243a  test    eax, eax
0x18003243c  jns     short loc_180032457
0x18003243e  mov     r8d, eax
0x180032441  lea     rdx, aFailedToAcquir; "Failed to acquire thread token: 0%x08X"
0x180032448  mov     ecx, 2; unsigned __int8
0x18003244d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180032452  jmp     loc_180032532
0x180032457  lea     r8, [rsp+58h+Luid]; lpLuid
0x18003245c  mov     qword ptr [rsp+58h+Luid.LowPart], 0
0x180032465  mov     rdx, rdi; lpName
0x180032468  xor     ecx, ecx; lpSystemName
0x18003246a  call    cs:__imp_LookupPrivilegeValueW
0x180032470  test    eax, eax
0x180032472  jnz     short loc_180032495
0x180032474  call    cs:__imp_GetLastError
0x18003247a  mov     ebx, eax
0x18003247c  test    eax, eax
0x18003247e  jle     short loc_180032489
0x180032480  movzx   ebx, ax
0x180032483  or      ebx, 80070000h
0x180032489  lea     rdx, aFailedToLookup; "Failed to lookup the %s privilege value"...
0x180032490  jmp     loc_180032522
0x180032495  mov     rax, qword ptr [rsp+58h+Luid.LowPart]
0x18003249a  lea     r8, [rsp+58h+NewState]; NewState
0x18003249f  mov     rcx, [rsi]; TokenHandle
0x1800324a2  mov     r9d, 10h; BufferLength
0x1800324a8  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1800324b1  xor     edx, edx; DisableAllPrivileges
0x1800324b3  mov     qword ptr [rsp+58h+NewState.Privileges.Luid.LowPart], rax
0x1800324b8  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1800324c0  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x1800324c8  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1800324d1  call    cs:__imp_AdjustTokenPrivileges
0x1800324d7  test    eax, eax
0x1800324d9  jnz     short loc_1800324F9
0x1800324db  call    cs:__imp_GetLastError
0x1800324e1  mov     ebx, eax
0x1800324e3  test    eax, eax
0x1800324e5  jle     short loc_1800324F0
0x1800324e7  movzx   ebx, ax
0x1800324ea  or      ebx, 80070000h
0x1800324f0  lea     rdx, aFailedToEnable_0; "Failed to enable the requested privileg"...
0x1800324f7  jmp     short loc_180032522
0x1800324f9  call    cs:__imp_GetLastError
0x1800324ff  cmp     eax, 514h
0x180032504  jnz     short loc_180032532
0x180032506  call    cs:__imp_GetLastError
0x18003250c  mov     ebx, eax
0x18003250e  test    eax, eax
0x180032510  jle     short loc_18003251B
0x180032512  movzx   ebx, ax
0x180032515  or      ebx, 80070000h
0x18003251b  lea     rdx, aFailedToAssign; "Failed to assign the requested privileg"...
0x180032522  mov     r8, rdi
0x180032525  mov     r9d, ebx
0x180032528  mov     ecx, 2; unsigned __int8
0x18003252d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180032532  mov     eax, ebx
0x180032534  mov     rcx, [rsp+58h+var_10]
0x180032539  xor     rcx, rsp; StackCookie
0x18003253c  call    __security_check_cookie
0x180032541  mov     rbx, [rsp+58h+arg_10]
0x180032546  mov     rsi, [rsp+58h+arg_18]
0x18003254b  add     rsp, 50h
0x18003254f  pop     rdi
0x180032550  retn
```
