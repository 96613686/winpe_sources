# SetProxyImpersonationLevel(IUnknown *,ulong)

- ea: `0x180014544`
- end: `0x18001461b`
- name: `?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z`
- size: `215`
- prototype: `__int64 __fastcall(IUnknown *pProxy)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x180005830`
- `0x180007c50`
- `0x180013430`
- `0x180013708`

## callees

- `0x180014544`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x1800145fa`
- `ole32!CoSetProxyBlanket` at `0x1800145fa`
- `ole32!CoQueryProxyBlanket` at `0x1800145b7`
- `ole32!CoQueryProxyBlanket` at `0x1800145b7`
- `ole32!CoTaskMemFree` at `0x18001460b`
- `ole32!CoTaskMemFree` at `0x18001460b`

## pseudocode

```c
__int64 __fastcall SetProxyImpersonationLevel(IUnknown *pProxy)
{
  HRESULT v2; // ebx
  DWORD dwCapabilities; // eax
  DWORD pwAuthnSvc; // [rsp+40h] [rbp-20h] BYREF
  DWORD v6; // [rsp+44h] [rbp-1Ch] BYREF
  LPOLESTR pServerPrincName; // [rsp+48h] [rbp-18h] BYREF
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+50h] [rbp-10h] BYREF
  DWORD v9; // [rsp+88h] [rbp+28h] BYREF
  DWORD dwAuthnLevel; // [rsp+90h] [rbp+30h] BYREF
  DWORD pAuthzSvc; // [rsp+98h] [rbp+38h] BYREF

  pwAuthnSvc = 0;
  pAuthzSvc = 0;
  dwAuthnLevel = 0;
  v6 = 0;
  v9 = 0;
  pServerPrincName = 0;
  pAuthInfo = 0;
  v2 = CoQueryProxyBlanket(pProxy, &pwAuthnSvc, &pAuthzSvc, &pServerPrincName, &dwAuthnLevel, &v6, &pAuthInfo, &v9);
  if ( v2 >= 0 )
  {
    dwCapabilities = v9;
    if ( (v9 & 0x20) == 0 )
    {
      dwCapabilities = v9 | 0x40;
      v9 |= 0x40u;
    }
    v2 = CoSetProxyBlanket(pProxy, pwAuthnSvc, pAuthzSvc, pServerPrincName, dwAuthnLevel, 3u, pAuthInfo, dwCapabilities);
  }
  if ( pServerPrincName )
    CoTaskMemFree(pServerPrincName);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180014544  mov     [rsp-18h+arg_8], edx
0x180014548  mov     r11, rsp
0x18001454b  push    rbp
0x18001454c  push    rbx
0x18001454d  push    rdi
0x18001454e  mov     rbp, rsp
0x180014551  sub     rsp, 60h
0x180014555  lea     rax, [rbp+arg_8]
0x180014559  mov     [rbp+pwAuthnSvc], 0
0x180014560  mov     [r11-40h], rax
0x180014564  lea     r9, [rbp+pServerPrincName]; pServerPrincName
0x180014568  lea     rax, [rbp+var_10]
0x18001456c  mov     [rbp+pAuthzSvc], 0
0x180014573  mov     [r11-48h], rax
0x180014577  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x18001457b  lea     rax, [rbp+var_1C]
0x18001457f  mov     [rbp+arg_10], 0
0x180014586  mov     [r11-50h], rax
0x18001458a  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x18001458e  lea     rax, [rbp+arg_10]
0x180014592  mov     [rbp+var_1C], 0
0x180014599  mov     [r11-58h], rax
0x18001459d  mov     rdi, rcx
0x1800145a0  mov     [rbp+arg_8], 0
0x1800145a7  mov     [rbp+pServerPrincName], 0
0x1800145af  mov     [rbp+var_10], 0
0x1800145b7  call    cs:__imp_CoQueryProxyBlanket
0x1800145bd  mov     ebx, eax
0x1800145bf  test    eax, eax
0x1800145c1  js      short loc_180014602
0x1800145c3  mov     eax, [rbp+arg_8]
0x1800145c6  test    al, 20h
0x1800145c8  jnz     short loc_1800145D0
0x1800145ca  or      eax, 40h
0x1800145cd  mov     [rbp+arg_8], eax
0x1800145d0  mov     r9, [rbp+pServerPrincName]; pServerPrincName
0x1800145d4  mov     rcx, rdi; pProxy
0x1800145d7  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x1800145db  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x1800145de  mov     [rsp+60h+dwCapabilities], eax; dwCapabilities
0x1800145e2  mov     rax, [rbp+var_10]
0x1800145e6  mov     [rsp+60h+pAuthInfo], rax; pAuthInfo
0x1800145eb  mov     eax, [rbp+arg_10]
0x1800145ee  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x1800145f6  mov     [rsp+60h+dwAuthnLevel], eax; dwAuthnLevel
0x1800145fa  call    cs:__imp_CoSetProxyBlanket
0x180014600  mov     ebx, eax
0x180014602  mov     rcx, [rbp+pServerPrincName]; pv
0x180014606  test    rcx, rcx
0x180014609  jz      short loc_180014611
0x18001460b  call    cs:__imp_CoTaskMemFree
0x180014611  mov     eax, ebx
0x180014613  add     rsp, 60h
0x180014617  pop     rdi
0x180014618  pop     rbx
0x180014619  pop     rbp
0x18001461a  retn
```
