# LsapCreateBindingHandleWithCreds

- ea: `0x180061f40`
- end: `0x180062036`
- name: `LsapCreateBindingHandleWithCreds`
- size: `246`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr, RPC_WSTR ServerPrincName, unsigned int AuthnLevel, unsigned int AuthnSvc, RPC_AUTH_IDENTITY_HANDLE AuthIdentity, unsigned int AuthzSvc, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180061890`
- `0x180061a54`
- `0x180061c4c`

## callees

- `0x180061f40`
- `0x180065066`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180061fea`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180061fea`
- `RPCRT4!I_RpcMapWin32Status` at `0x180062027`
- `RPCRT4!I_RpcMapWin32Status` at `0x180062027`
- `RPCRT4!RpcBindingFree` at `0x180061ffb`
- `RPCRT4!RpcBindingFree` at `0x180061ffb`
- `RPCRT4!RpcStringFreeW` at `0x18006200f`
- `RPCRT4!RpcStringFreeW` at `0x18006200f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180061fb8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180061fb8`
- `RPCRT4!RpcStringBindingComposeW` at `0x180061fa2`
- `RPCRT4!RpcStringBindingComposeW` at `0x180061fa2`

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
0x180061f40  push    rbx
0x180061f42  push    rbp
0x180061f43  push    rsi
0x180061f44  push    rdi
0x180061f45  sub     rsp, 48h
0x180061f49  mov     esi, r8d
0x180061f4c  mov     [rsp+68h+String], 0
0x180061f55  mov     rbp, rdx
0x180061f58  mov     [rsp+68h+Binding], 0
0x180061f61  mov     r8d, 2; MaxCount
0x180061f67  lea     rdx, asc_180083C5C; "\\\\"
0x180061f6e  mov     edi, r9d
0x180061f71  mov     rbx, rcx
0x180061f74  call    wcsncmp_0
0x180061f79  test    eax, eax
0x180061f7b  lea     r8, [rbx+4]
0x180061f7f  lea     rax, [rsp+68h+String]
0x180061f84  cmovnz  r8, rbx; NetworkAddr
0x180061f88  mov     [rsp+68h+StringBinding], rax; StringBinding
0x180061f8d  xor     r9d, r9d; Endpoint
0x180061f90  mov     [rsp+68h+Options], 0; Options
0x180061f99  xor     ecx, ecx; ObjUuid
0x180061f9b  lea     rdx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180061fa2  call    cs:__imp_RpcStringBindingComposeW
0x180061fa8  mov     ebx, eax
0x180061faa  test    eax, eax
0x180061fac  jnz     short loc_180062015
0x180061fae  mov     rcx, [rsp+68h+String]; StringBinding
0x180061fb3  lea     rdx, [rsp+68h+Binding]; Binding
0x180061fb8  call    cs:__imp_RpcBindingFromStringBindingW
0x180061fbe  mov     ebx, eax
0x180061fc0  test    eax, eax
0x180061fc2  jnz     short loc_18006200A
0x180061fc4  mov     eax, [rsp+68h+AuthzSvc]
0x180061fcb  mov     r9d, edi; AuthnSvc
0x180061fce  mov     rcx, [rsp+68h+Binding]; Binding
0x180061fd3  mov     r8d, esi; AuthnLevel
0x180061fd6  mov     dword ptr [rsp+68h+StringBinding], eax; AuthzSvc
0x180061fda  mov     rdx, rbp; ServerPrincName
0x180061fdd  mov     rax, [rsp+68h+AuthIdentity]
0x180061fe5  mov     [rsp+68h+Options], rax; AuthIdentity
0x180061fea  call    cs:__imp_RpcBindingSetAuthInfoW
0x180061ff0  mov     ebx, eax
0x180061ff2  test    eax, eax
0x180061ff4  jz      short loc_18006200A
0x180061ff6  lea     rcx, [rsp+68h+Binding]; Binding
0x180061ffb  call    cs:__imp_RpcBindingFree
0x180062001  mov     [rsp+68h+Binding], 0
0x18006200a  lea     rcx, [rsp+68h+String]; String
0x18006200f  call    cs:__imp_RpcStringFreeW
0x180062015  mov     rcx, [rsp+68h+arg_30]
0x18006201d  mov     rax, [rsp+68h+Binding]
0x180062022  mov     [rcx], rax
0x180062025  mov     ecx, ebx; Status
0x180062027  call    cs:__imp_I_RpcMapWin32Status
0x18006202d  add     rsp, 48h
0x180062031  pop     rdi
0x180062032  pop     rsi
0x180062033  pop     rbp
0x180062034  pop     rbx
0x180062035  retn
```
