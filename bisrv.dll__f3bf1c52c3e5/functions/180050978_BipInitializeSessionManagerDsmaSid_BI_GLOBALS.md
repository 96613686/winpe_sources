# BipInitializeSessionManagerDsmaSid(_BI_GLOBALS *)

- ea: `0x180050978`
- end: `0x180050a56`
- name: `?BipInitializeSessionManagerDsmaSid@@YAJPEAU_BI_GLOBALS@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(struct _BI_GLOBALS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007d668`

## callees

- `0x180050978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a1b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800509fd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800509fd`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180050a46`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180050a46`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800509d2`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800509d2`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800509b9`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800509b9`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180050a37`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180050a37`

## pseudocode

```c
__int64 __fastcall BipInitializeSessionManagerDsmaSid(struct _BI_GLOBALS *a1)
{
  int LastError; // ebx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  DWORD cbSid; // [rsp+78h] [rbp+28h] BYREF
  PVOID DomainInfo; // [rsp+80h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp+38h] BYREF

  cbSid = 0;
  DomainInfo = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  LastError = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x801u, &PolicyHandle);
  if ( LastError >= 0 )
  {
    LastError = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
    if ( LastError >= 0 )
    {
      cbSid = 68;
      if ( CreateWellKnownSid(
             WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
             *((PSID *)DomainInfo + 2),
             (char *)a1 + 2172,
             &cbSid) )
      {
        LastError = 0;
      }
      else if ( (int)GetLastError() > 0 )
      {
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  if ( DomainInfo )
    LsaLookupFreeMemory(DomainInfo);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180050978  push    rbp
0x18005097a  push    rbx
0x18005097b  push    rdi
0x18005097c  mov     rbp, rsp
0x18005097f  sub     rsp, 50h
0x180050983  xorps   xmm0, xmm0
0x180050986  mov     [rbp+cbSid], 0
0x18005098d  mov     rdi, rcx
0x180050990  mov     [rbp+DomainInfo], 0
0x180050998  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x18005099c  mov     [rbp+PolicyHandle], 0
0x1800509a4  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x1800509a8  mov     edx, 801h; AccessMask
0x1800509ad  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800509b1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800509b5  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800509b9  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800509bf  mov     ebx, eax
0x1800509c1  test    eax, eax
0x1800509c3  js      short loc_180050A2E
0x1800509c5  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800509c9  lea     r8, [rbp+DomainInfo]; DomainInfo
0x1800509cd  mov     edx, 5; DomainInfoClass
0x1800509d2  call    cs:__imp_LsaLookupGetDomainInfo
0x1800509d8  mov     ebx, eax
0x1800509da  test    eax, eax
0x1800509dc  js      short loc_180050A2E
0x1800509de  mov     rdx, [rbp+DomainInfo]
0x1800509e2  lea     r8, [rdi+87Ch]; pSid
0x1800509e9  mov     [rbp+cbSid], 44h ; 'D'
0x1800509f0  lea     r9, [rbp+cbSid]; cbSid
0x1800509f4  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x1800509f9  mov     rdx, [rdx+10h]; DomainSid
0x1800509fd  call    cs:__imp_CreateWellKnownSid
0x180050a03  test    eax, eax
0x180050a05  jnz     short loc_180050A2C
0x180050a07  call    cs:__imp_GetLastError
0x180050a0d  test    eax, eax
0x180050a0f  jg      short loc_180050A1B
0x180050a11  call    cs:__imp_GetLastError
0x180050a17  mov     ebx, eax
0x180050a19  jmp     short loc_180050A2E
0x180050a1b  call    cs:__imp_GetLastError
0x180050a21  movzx   ebx, ax
0x180050a24  or      ebx, 0C0070000h
0x180050a2a  jmp     short loc_180050A2E
0x180050a2c  xor     ebx, ebx
0x180050a2e  mov     rcx, [rbp+DomainInfo]; Buffer
0x180050a32  test    rcx, rcx
0x180050a35  jz      short loc_180050A3D
0x180050a37  call    cs:__imp_LsaLookupFreeMemory
0x180050a3d  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180050a41  test    rcx, rcx
0x180050a44  jz      short loc_180050A4C
0x180050a46  call    cs:__imp_LsaLookupClose
0x180050a4c  mov     eax, ebx
0x180050a4e  add     rsp, 50h
0x180050a52  pop     rdi
0x180050a53  pop     rbx
0x180050a54  pop     rbp
0x180050a55  retn
```
