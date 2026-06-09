# LsapCreateBindingHandleWithCreds

- ea: `0x18006eaf0`
- end: `0x18006ec0b`
- name: `LsapCreateBindingHandleWithCreds`
- size: `283`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr, RPC_WSTR ServerPrincName, unsigned int AuthnLevel, unsigned int AuthnSvc, RPC_AUTH_IDENTITY_HANDLE AuthIdentity, unsigned int AuthzSvc, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006e3f0`
- `0x18006e5c8`
- `0x18006e7e0`

## callees

- `0x18006eaf0`
- `0x180072066`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18006eba6`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18006eba6`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006ebf5`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006ebf5`
- `RPCRT4!RpcBindingFree` at `0x18006ebbd`
- `RPCRT4!RpcBindingFree` at `0x18006ebbd`
- `RPCRT4!RpcStringFreeW` at `0x18006ebd7`
- `RPCRT4!RpcStringFreeW` at `0x18006ebd7`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18006eb6e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18006eb6e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18006eb52`
- `RPCRT4!RpcStringBindingComposeW` at `0x18006eb52`

## pseudocode

```c
int __fastcall LsapCreateBindingHandleWithCreds(
        const wchar_t *NetworkAddr,
        RPC_WSTR ServerPrincName,
        unsigned int AuthnLevel,
        unsigned int AuthnSvc,
        RPC_AUTH_IDENTITY_HANDLE AuthIdentity,
        unsigned int AuthzSvc,
        RPC_BINDING_HANDLE *a7)
{
  int v11; // eax
  unsigned __int16 *v12; // r8
  RPC_STATUS v13; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-38h] BYREF
  RPC_WSTR String[6]; // [rsp+38h] [rbp-30h] BYREF

  String[0] = 0;
  Binding = 0;
  v11 = wcsncmp_0(NetworkAddr, L"\\\\", 2u);
  v12 = (unsigned __int16 *)(NetworkAddr + 2);
  if ( v11 )
    v12 = (unsigned __int16 *)NetworkAddr;
  v13 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", v12, 0, 0, String);
  if ( !v13 )
  {
    v13 = RpcBindingFromStringBindingW(String[0], &Binding);
    if ( !v13 )
    {
      v13 = RpcBindingSetAuthInfoW(Binding, ServerPrincName, AuthnLevel, AuthnSvc, AuthIdentity, AuthzSvc);
      if ( v13 )
      {
        RpcBindingFree(&Binding);
        Binding = 0;
      }
    }
    RpcStringFreeW(String);
  }
  *a7 = Binding;
  return I_RpcMapWin32Status(v13);
}

```

## disassembly

```asm
0x18006eaf0  push    rbx
0x18006eaf2  push    rbp
0x18006eaf3  push    rsi
0x18006eaf4  push    rdi
0x18006eaf5  sub     rsp, 48h
0x18006eaf9  mov     esi, r8d
0x18006eafc  mov     [rsp+68h+String], 0
0x18006eb05  mov     rbp, rdx
0x18006eb08  mov     [rsp+68h+Binding], 0
0x18006eb11  mov     r8d, 2; MaxCount
0x18006eb17  lea     rdx, asc_180091E14; "\\\\"
0x18006eb1e  mov     edi, r9d
0x18006eb21  mov     rbx, rcx
0x18006eb24  call    wcsncmp_0
0x18006eb29  test    eax, eax
0x18006eb2b  lea     r8, [rbx+4]
0x18006eb2f  lea     rax, [rsp+68h+String]
0x18006eb34  cmovnz  r8, rbx; NetworkAddr
0x18006eb38  mov     [rsp+68h+StringBinding], rax; StringBinding
0x18006eb3d  xor     r9d, r9d; Endpoint
0x18006eb40  mov     [rsp+68h+Options], 0; Options
0x18006eb49  xor     ecx, ecx; ObjUuid
0x18006eb4b  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x18006eb52  call    cs:__imp_RpcStringBindingComposeW
0x18006eb59  nop     dword ptr [rax+rax+00h]
0x18006eb5e  mov     ebx, eax
0x18006eb60  test    eax, eax
0x18006eb62  jnz     short loc_18006EBE3
0x18006eb64  mov     rcx, [rsp+68h+String]; StringBinding
0x18006eb69  lea     rdx, [rsp+68h+Binding]; Binding
0x18006eb6e  call    cs:__imp_RpcBindingFromStringBindingW
0x18006eb75  nop     dword ptr [rax+rax+00h]
0x18006eb7a  mov     ebx, eax
0x18006eb7c  test    eax, eax
0x18006eb7e  jnz     short loc_18006EBD2
0x18006eb80  mov     eax, [rsp+68h+AuthzSvc]
0x18006eb87  mov     r9d, edi; AuthnSvc
0x18006eb8a  mov     rcx, [rsp+68h+Binding]; Binding
0x18006eb8f  mov     r8d, esi; AuthnLevel
0x18006eb92  mov     dword ptr [rsp+68h+StringBinding], eax; AuthzSvc
0x18006eb96  mov     rdx, rbp; ServerPrincName
0x18006eb99  mov     rax, [rsp+68h+AuthIdentity]
0x18006eba1  mov     [rsp+68h+Options], rax; AuthIdentity
0x18006eba6  call    cs:__imp_RpcBindingSetAuthInfoW
0x18006ebad  nop     dword ptr [rax+rax+00h]
0x18006ebb2  mov     ebx, eax
0x18006ebb4  test    eax, eax
0x18006ebb6  jz      short loc_18006EBD2
0x18006ebb8  lea     rcx, [rsp+68h+Binding]; Binding
0x18006ebbd  call    cs:__imp_RpcBindingFree
0x18006ebc4  nop     dword ptr [rax+rax+00h]
0x18006ebc9  mov     [rsp+68h+Binding], 0
0x18006ebd2  lea     rcx, [rsp+68h+String]; String
0x18006ebd7  call    cs:__imp_RpcStringFreeW
0x18006ebde  nop     dword ptr [rax+rax+00h]
0x18006ebe3  mov     rcx, [rsp+68h+arg_30]
0x18006ebeb  mov     rax, [rsp+68h+Binding]
0x18006ebf0  mov     [rcx], rax
0x18006ebf3  mov     ecx, ebx; Status
0x18006ebf5  call    cs:__imp_I_RpcMapWin32Status
0x18006ebfc  nop     dword ptr [rax+rax+00h]
0x18006ec01  add     rsp, 48h
0x18006ec05  pop     rdi
0x18006ec06  pop     rsi
0x18006ec07  pop     rbp
0x18006ec08  pop     rbx
0x18006ec09  retn
```
