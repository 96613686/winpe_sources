# Windows::Internal::Management::Provision::SessionManager::IsWellKnownSid(ushort const *,bool *)

- ea: `0x18003dbe4`
- end: `0x18003dca5`
- name: `?IsWellKnownSid@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEBGPEA_N@Z`
- size: `193`
- prototype: `int(Windows::Internal::Management::Provision::SessionManager *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c82c`

## callees

- `0x18000a5a4`
- `0x1800179f8`
- `0x18003dbe4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003dc34`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003dc4c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003dc64`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003dc7c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003dc34`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003dc4c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003dc64`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003dc7c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003dc02`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003dc02`

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
0x18003dbe4  mov     [rsp+Sid], rcx
0x18003dbe9  push    rbx
0x18003dbea  sub     rsp, 20h
0x18003dbee  mov     rcx, rdx; StringSid
0x18003dbf1  mov     [rsp+28h+Sid], 0
0x18003dbfa  lea     rdx, [rsp+28h+Sid]; Sid
0x18003dbff  mov     rbx, r8
0x18003dc02  call    cs:__imp_ConvertStringSidToSidW
0x18003dc09  nop     dword ptr [rax+rax+00h]
0x18003dc0e  test    eax, eax
0x18003dc10  jnz     short loc_18003DC2A
0x18003dc12  mov     rcx, [rsp+28h]; this
0x18003dc17  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003dc1e  lea     edx, [rax+7Fh]; void *
0x18003dc21  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003dc26  mov     ebx, eax
0x18003dc28  jmp     short loc_18003DC92
0x18003dc2a  mov     rcx, [rsp+28h+Sid]; pSid
0x18003dc2f  mov     edx, 16h; WellKnownSidType
0x18003dc34  call    cs:__imp_IsWellKnownSid
0x18003dc3b  nop     dword ptr [rax+rax+00h]
0x18003dc40  test    eax, eax
0x18003dc42  jnz     short loc_18003DC8C
0x18003dc44  mov     rcx, [rsp+28h+Sid]; pSid
0x18003dc49  lea     edx, [rax+17h]; WellKnownSidType
0x18003dc4c  call    cs:__imp_IsWellKnownSid
0x18003dc53  nop     dword ptr [rax+rax+00h]
0x18003dc58  test    eax, eax
0x18003dc5a  jnz     short loc_18003DC8C
0x18003dc5c  mov     rcx, [rsp+28h+Sid]; pSid
0x18003dc61  lea     edx, [rax+18h]; WellKnownSidType
0x18003dc64  call    cs:__imp_IsWellKnownSid
0x18003dc6b  nop     dword ptr [rax+rax+00h]
0x18003dc70  test    eax, eax
0x18003dc72  jnz     short loc_18003DC8C
0x18003dc74  mov     rcx, [rsp+28h+Sid]; pSid
0x18003dc79  lea     edx, [rax+45h]; WellKnownSidType
0x18003dc7c  call    cs:__imp_IsWellKnownSid
0x18003dc83  nop     dword ptr [rax+rax+00h]
0x18003dc88  test    eax, eax
0x18003dc8a  jz      short loc_18003DC8E
0x18003dc8c  mov     al, 1
0x18003dc8e  mov     [rbx], al
0x18003dc90  xor     ebx, ebx
0x18003dc92  lea     rcx, [rsp+28h+Sid]
0x18003dc97  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003dc9c  mov     eax, ebx
0x18003dc9e  add     rsp, 20h
0x18003dca2  pop     rbx
0x18003dca3  retn
```
