# Windows::Management::MdmSession::IsWellKnownSid(ushort const *,bool *)

- ea: `0x1800990c4`
- end: `0x180099168`
- name: `?IsWellKnownSid@MdmSession@Management@Windows@@AEAAJPEBGPEA_N@Z`
- size: `164`
- prototype: `int(Windows::Management::MdmSession *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180098fd8`

## callees

- `0x18000a284`
- `0x180017204`
- `0x1800990c4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180099110`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180099122`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180099134`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180099146`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180099110`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180099122`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180099134`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180099146`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800990e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800990e2`

## pseudocode

```c
__int64 __fastcall Windows::Management::MdmSession::IsWellKnownSid(
        Windows::Management::MdmSession *this,
        const unsigned __int16 *a2,
        bool *a3)
{
  const char *v4; // r9
  unsigned int LastError; // ebx
  BOOL v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSID Sid; // [rsp+30h] [rbp+8h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    if ( IsWellKnownSid(Sid, WinLocalSystemSid)
      || IsWellKnownSid(Sid, WinLocalServiceSid)
      || IsWellKnownSid(Sid, WinNetworkServiceSid)
      || (v6 = IsWellKnownSid(Sid, WinSystemLabelSid)) )
    {
      LOBYTE(v6) = 1;
    }
    *a3 = v6;
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x8F,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
                  v4);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return LastError;
}

```

## disassembly

```asm
0x1800990c4  mov     [rsp+Sid], rcx
0x1800990c9  push    rbx
0x1800990ca  sub     rsp, 20h
0x1800990ce  mov     rcx, rdx; StringSid
0x1800990d1  mov     [rsp+28h+Sid], 0
0x1800990da  lea     rdx, [rsp+28h+Sid]; Sid
0x1800990df  mov     rbx, r8
0x1800990e2  call    cs:__imp_ConvertStringSidToSidW
0x1800990e8  test    eax, eax
0x1800990ea  jnz     short loc_180099106
0x1800990ec  mov     rcx, [rsp+28h]; this
0x1800990f1  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x1800990f8  mov     edx, 8Fh; void *
0x1800990fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180099102  mov     ebx, eax
0x180099104  jmp     short loc_180099156
0x180099106  mov     rcx, [rsp+28h+Sid]; pSid
0x18009910b  mov     edx, 16h; WellKnownSidType
0x180099110  call    cs:__imp_IsWellKnownSid
0x180099116  test    eax, eax
0x180099118  jnz     short loc_180099150
0x18009911a  mov     rcx, [rsp+28h+Sid]; pSid
0x18009911f  lea     edx, [rax+17h]; WellKnownSidType
0x180099122  call    cs:__imp_IsWellKnownSid
0x180099128  test    eax, eax
0x18009912a  jnz     short loc_180099150
0x18009912c  mov     rcx, [rsp+28h+Sid]; pSid
0x180099131  lea     edx, [rax+18h]; WellKnownSidType
0x180099134  call    cs:__imp_IsWellKnownSid
0x18009913a  test    eax, eax
0x18009913c  jnz     short loc_180099150
0x18009913e  mov     rcx, [rsp+28h+Sid]; pSid
0x180099143  lea     edx, [rax+45h]; WellKnownSidType
0x180099146  call    cs:__imp_IsWellKnownSid
0x18009914c  test    eax, eax
0x18009914e  jz      short loc_180099152
0x180099150  mov     al, 1
0x180099152  mov     [rbx], al
0x180099154  xor     ebx, ebx
0x180099156  lea     rcx, [rsp+28h+Sid]
0x18009915b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180099160  mov     eax, ebx
0x180099162  add     rsp, 20h
0x180099166  pop     rbx
0x180099167  retn
```
