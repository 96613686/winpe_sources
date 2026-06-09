# Windows::Internal::Management::Provision::SessionManager::IsWellKnownSid(ushort const *,bool *)

- ea: `0x18003e234`
- end: `0x18003e2d6`
- name: `?IsWellKnownSid@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEBGPEA_N@Z`
- size: `162`
- prototype: `int(Windows::Internal::Management::Provision::SessionManager *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003cf50`

## callees

- `0x18000a284`
- `0x180017204`
- `0x18003e234`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003e27e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003e290`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003e2a2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003e2b4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003e27e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003e290`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003e2a2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003e2b4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003e252`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003e252`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Management::Provision::SessionManager::IsWellKnownSid(
        Windows::Internal::Management::Provision::SessionManager *this,
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
                  (void *)0x7F,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
                  v4);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return LastError;
}

```

## disassembly

```asm
0x18003e234  mov     [rsp+Sid], rcx
0x18003e239  push    rbx
0x18003e23a  sub     rsp, 20h
0x18003e23e  mov     rcx, rdx; StringSid
0x18003e241  mov     [rsp+28h+Sid], 0
0x18003e24a  lea     rdx, [rsp+28h+Sid]; Sid
0x18003e24f  mov     rbx, r8
0x18003e252  call    cs:__imp_ConvertStringSidToSidW
0x18003e258  test    eax, eax
0x18003e25a  jnz     short loc_18003E274
0x18003e25c  mov     rcx, [rsp+28h]; this
0x18003e261  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003e268  lea     edx, [rax+7Fh]; void *
0x18003e26b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e270  mov     ebx, eax
0x18003e272  jmp     short loc_18003E2C4
0x18003e274  mov     rcx, [rsp+28h+Sid]; pSid
0x18003e279  mov     edx, 16h; WellKnownSidType
0x18003e27e  call    cs:__imp_IsWellKnownSid
0x18003e284  test    eax, eax
0x18003e286  jnz     short loc_18003E2BE
0x18003e288  mov     rcx, [rsp+28h+Sid]; pSid
0x18003e28d  lea     edx, [rax+17h]; WellKnownSidType
0x18003e290  call    cs:__imp_IsWellKnownSid
0x18003e296  test    eax, eax
0x18003e298  jnz     short loc_18003E2BE
0x18003e29a  mov     rcx, [rsp+28h+Sid]; pSid
0x18003e29f  lea     edx, [rax+18h]; WellKnownSidType
0x18003e2a2  call    cs:__imp_IsWellKnownSid
0x18003e2a8  test    eax, eax
0x18003e2aa  jnz     short loc_18003E2BE
0x18003e2ac  mov     rcx, [rsp+28h+Sid]; pSid
0x18003e2b1  lea     edx, [rax+45h]; WellKnownSidType
0x18003e2b4  call    cs:__imp_IsWellKnownSid
0x18003e2ba  test    eax, eax
0x18003e2bc  jz      short loc_18003E2C0
0x18003e2be  mov     al, 1
0x18003e2c0  mov     [rbx], al
0x18003e2c2  xor     ebx, ebx
0x18003e2c4  lea     rcx, [rsp+28h+Sid]
0x18003e2c9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003e2ce  mov     eax, ebx
0x18003e2d0  add     rsp, 20h
0x18003e2d4  pop     rbx
0x18003e2d5  retn
```
