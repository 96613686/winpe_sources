# Windows::Management::MdmSession::IsWellKnownSid(ushort const *,bool *)

- ea: `0x18009bc30`
- end: `0x18009bcf3`
- name: `?IsWellKnownSid@MdmSession@Management@Windows@@AEAAJPEBGPEA_N@Z`
- size: `195`
- prototype: `int(Windows::Management::MdmSession *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009bb40`

## callees

- `0x18000a5a4`
- `0x1800179f8`
- `0x18009bc30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009bc82`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009bc9a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009bcb2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009bcca`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009bc82`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009bc9a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009bcb2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009bcca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18009bc4e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18009bc4e`

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
0x18009bc30  mov     [rsp+Sid], rcx
0x18009bc35  push    rbx
0x18009bc36  sub     rsp, 20h
0x18009bc3a  mov     rcx, rdx; StringSid
0x18009bc3d  mov     [rsp+28h+Sid], 0
0x18009bc46  lea     rdx, [rsp+28h+Sid]; Sid
0x18009bc4b  mov     rbx, r8
0x18009bc4e  call    cs:__imp_ConvertStringSidToSidW
0x18009bc55  nop     dword ptr [rax+rax+00h]
0x18009bc5a  test    eax, eax
0x18009bc5c  jnz     short loc_18009BC78
0x18009bc5e  mov     rcx, [rsp+28h]; this
0x18009bc63  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009bc6a  mov     edx, 8Fh; void *
0x18009bc6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009bc74  mov     ebx, eax
0x18009bc76  jmp     short loc_18009BCE0
0x18009bc78  mov     rcx, [rsp+28h+Sid]; pSid
0x18009bc7d  mov     edx, 16h; WellKnownSidType
0x18009bc82  call    cs:__imp_IsWellKnownSid
0x18009bc89  nop     dword ptr [rax+rax+00h]
0x18009bc8e  test    eax, eax
0x18009bc90  jnz     short loc_18009BCDA
0x18009bc92  mov     rcx, [rsp+28h+Sid]; pSid
0x18009bc97  lea     edx, [rax+17h]; WellKnownSidType
0x18009bc9a  call    cs:__imp_IsWellKnownSid
0x18009bca1  nop     dword ptr [rax+rax+00h]
0x18009bca6  test    eax, eax
0x18009bca8  jnz     short loc_18009BCDA
0x18009bcaa  mov     rcx, [rsp+28h+Sid]; pSid
0x18009bcaf  lea     edx, [rax+18h]; WellKnownSidType
0x18009bcb2  call    cs:__imp_IsWellKnownSid
0x18009bcb9  nop     dword ptr [rax+rax+00h]
0x18009bcbe  test    eax, eax
0x18009bcc0  jnz     short loc_18009BCDA
0x18009bcc2  mov     rcx, [rsp+28h+Sid]; pSid
0x18009bcc7  lea     edx, [rax+45h]; WellKnownSidType
0x18009bcca  call    cs:__imp_IsWellKnownSid
0x18009bcd1  nop     dword ptr [rax+rax+00h]
0x18009bcd6  test    eax, eax
0x18009bcd8  jz      short loc_18009BCDC
0x18009bcda  mov     al, 1
0x18009bcdc  mov     [rbx], al
0x18009bcde  xor     ebx, ebx
0x18009bce0  lea     rcx, [rsp+28h+Sid]
0x18009bce5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009bcea  mov     eax, ebx
0x18009bcec  add     rsp, 20h
0x18009bcf0  pop     rbx
0x18009bcf1  retn
```
