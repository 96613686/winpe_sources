# CComAuthInfo2::ApplyProxyBlanket(IUnknown *,ulong)

- ea: `0x18001bf94`
- end: `0x18001c0cd`
- name: `?ApplyProxyBlanket@CComAuthInfo2@@QEAAJPEAUIUnknown@@K@Z`
- size: `313`
- prototype: `int(CComAuthInfo2 *__hidden this, struct IUnknown *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013430`
- `0x18001a578`

## callees

- `0x18001bf94`
- `0x18001c0d4`
- `0x18001c2dc`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x18001bfec`
- `ole32!CoSetProxyBlanket` at `0x18001c09c`
- `ole32!CoSetProxyBlanket` at `0x18001bfec`
- `ole32!CoSetProxyBlanket` at `0x18001c09c`
- `ole32!CoQueryProxyBlanket` at `0x18001c062`
- `ole32!CoQueryProxyBlanket` at `0x18001c062`
- `ole32!CoTaskMemFree` at `0x18001c0ad`
- `ole32!CoTaskMemFree` at `0x18001c0ad`

## pseudocode

```c
__int64 __fastcall CComAuthInfo2::ApplyProxyBlanket(CComAuthInfo2 *this, struct IUnknown *a2, DWORD a3)
{
  struct _COSERVERINFO *ServerInfoStruct; // rax
  struct _COSERVERINFO *v5; // rbx
  COAUTHINFO *v6; // rdx
  HRESULT v7; // edi
  DWORD pwAuthnSvc; // [rsp+40h] [rbp-20h] BYREF
  DWORD pCapabilites; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD pAuthnLevel; // [rsp+48h] [rbp-18h] BYREF
  LPOLESTR pServerPrincName; // [rsp+50h] [rbp-10h] BYREF
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+58h] [rbp-8h] BYREF
  DWORD pImpLevel; // [rsp+90h] [rbp+30h] BYREF
  DWORD pAuthzSvc; // [rsp+98h] [rbp+38h] BYREF

  pImpLevel = a3;
  ServerInfoStruct = CComAuthInfo2::CreateServerInfoStruct(this, (unsigned int)a2);
  v5 = ServerInfoStruct;
  if ( !ServerInfoStruct
    || (v6 = ServerInfoStruct->pAuthInfo) == 0
    || (v7 = CoSetProxyBlanket(
               a2,
               v6->dwAuthnSvc,
               v6->dwAuthzSvc,
               v6->pwszServerPrincName,
               v6->dwAuthnLevel,
               v6->dwImpersonationLevel,
               v6->pAuthIdentityData,
               v6->dwCapabilities),
        v7 < 0) )
  {
    pwAuthnSvc = 0;
    pAuthzSvc = 0;
    pAuthnLevel = 0;
    pImpLevel = 0;
    pCapabilites = 0;
    pServerPrincName = 0;
    pAuthInfo = 0;
    v7 = CoQueryProxyBlanket(
           a2,
           &pwAuthnSvc,
           &pAuthzSvc,
           &pServerPrincName,
           &pAuthnLevel,
           &pImpLevel,
           &pAuthInfo,
           &pCapabilites);
    if ( v7 >= 0 )
      v7 = CoSetProxyBlanket(a2, pwAuthnSvc, pAuthzSvc, pServerPrincName, 0, pImpLevel, pAuthInfo, 0x40u);
    if ( pServerPrincName )
      CoTaskMemFree(pServerPrincName);
  }
  CComAuthInfo2::FreeServerInfoStruct(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001bf94  mov     [rsp-18h+arg_0], rbx
0x18001bf99  mov     [rsp-18h+pImpLevel], r8d
0x18001bf9e  push    rbp
0x18001bf9f  push    rsi
0x18001bfa0  push    rdi
0x18001bfa1  mov     rbp, rsp
0x18001bfa4  sub     rsp, 60h
0x18001bfa8  mov     rsi, rdx
0x18001bfab  call    ?CreateServerInfoStruct@CComAuthInfo2@@QEBAPEAU_COSERVERINFO@@K@Z; CComAuthInfo2::CreateServerInfoStruct(ulong)
0x18001bfb0  mov     rbx, rax
0x18001bfb3  test    rax, rax
0x18001bfb6  jz      short loc_18001BFFC
0x18001bfb8  mov     rdx, [rax+10h]
0x18001bfbc  test    rdx, rdx
0x18001bfbf  jz      short loc_18001BFFC
0x18001bfc1  mov     ecx, [rdx+20h]
0x18001bfc4  mov     eax, [rdx+10h]
0x18001bfc7  mov     r9, [rdx+8]; pServerPrincName
0x18001bfcb  mov     r8d, [rdx+4]; dwAuthzSvc
0x18001bfcf  mov     [rsp+60h+dwCapabilities], ecx; dwCapabilities
0x18001bfd3  mov     rcx, [rdx+18h]
0x18001bfd7  mov     [rsp+60h+pAuthInfo], rcx; pAuthInfo
0x18001bfdc  mov     ecx, [rdx+14h]
0x18001bfdf  mov     edx, [rdx]; dwAuthnSvc
0x18001bfe1  mov     [rsp+60h+dwImpLevel], ecx; dwImpLevel
0x18001bfe5  mov     rcx, rsi; pProxy
0x18001bfe8  mov     [rsp+60h+dwAuthnLevel], eax; dwAuthnLevel
0x18001bfec  call    cs:__imp_CoSetProxyBlanket
0x18001bff2  mov     edi, eax
0x18001bff4  test    eax, eax
0x18001bff6  jns     loc_18001C0B3
0x18001bffc  lea     rax, [rbp+pCapabilites]
0x18001c000  mov     [rbp+pwAuthnSvc], 0
0x18001c007  mov     qword ptr [rsp+60h+dwCapabilities], rax; pCapabilites
0x18001c00c  lea     r9, [rbp+pServerPrincName]; pServerPrincName
0x18001c010  lea     rax, [rbp+var_8]
0x18001c014  mov     [rbp+pAuthzSvc], 0
0x18001c01b  mov     [rsp+60h+pAuthInfo], rax; pAuthInfo
0x18001c020  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x18001c024  lea     rax, [rbp+pImpLevel]
0x18001c028  mov     [rbp+pAuthnLevel], 0
0x18001c02f  mov     qword ptr [rsp+60h+dwImpLevel], rax; pImpLevel
0x18001c034  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x18001c038  lea     rax, [rbp+pAuthnLevel]
0x18001c03c  mov     [rbp+pImpLevel], 0
0x18001c043  mov     rcx, rsi; pProxy
0x18001c046  mov     qword ptr [rsp+60h+dwAuthnLevel], rax; pAuthnLevel
0x18001c04b  mov     [rbp+pCapabilites], 0
0x18001c052  mov     [rbp+pServerPrincName], 0
0x18001c05a  mov     [rbp+var_8], 0
0x18001c062  call    cs:__imp_CoQueryProxyBlanket
0x18001c068  mov     edi, eax
0x18001c06a  test    eax, eax
0x18001c06c  js      short loc_18001C0A4
0x18001c06e  mov     rax, [rbp+var_8]
0x18001c072  mov     rcx, rsi; pProxy
0x18001c075  mov     r9, [rbp+pServerPrincName]; pServerPrincName
0x18001c079  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x18001c07d  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x18001c080  mov     [rsp+60h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18001c088  mov     [rsp+60h+pAuthInfo], rax; pAuthInfo
0x18001c08d  mov     eax, [rbp+pImpLevel]
0x18001c090  mov     [rsp+60h+dwImpLevel], eax; dwImpLevel
0x18001c094  mov     [rsp+60h+dwAuthnLevel], 0; dwAuthnLevel
0x18001c09c  call    cs:__imp_CoSetProxyBlanket
0x18001c0a2  mov     edi, eax
0x18001c0a4  mov     rcx, [rbp+pServerPrincName]; pv
0x18001c0a8  test    rcx, rcx
0x18001c0ab  jz      short loc_18001C0B3
0x18001c0ad  call    cs:__imp_CoTaskMemFree
0x18001c0b3  mov     rcx, rbx; Block
0x18001c0b6  call    ?FreeServerInfoStruct@CComAuthInfo2@@SAXPEAU_COSERVERINFO@@@Z; CComAuthInfo2::FreeServerInfoStruct(_COSERVERINFO *)
0x18001c0bb  mov     rbx, [rsp+60h+arg_0]
0x18001c0c3  mov     eax, edi
0x18001c0c5  add     rsp, 60h
0x18001c0c9  pop     rdi
0x18001c0ca  pop     rsi
0x18001c0cb  pop     rbp
0x18001c0cc  retn
```
