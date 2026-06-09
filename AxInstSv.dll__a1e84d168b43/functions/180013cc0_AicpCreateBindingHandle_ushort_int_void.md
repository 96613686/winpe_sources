# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x180013cc0`
- end: `0x180013e14`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `340`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800138f0`

## callees

- `0x180002283`
- `0x18000228f`
- `0x18000229b`
- `0x180013cc0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180013d7b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180013d7b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013d3a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013d3a`
- `RPCRT4!RpcBindingFree` at `0x180013dfc`
- `RPCRT4!RpcBindingFree` at `0x180013dfc`
- `RPCRT4!RpcStringFreeW` at `0x180013d46`
- `RPCRT4!RpcStringFreeW` at `0x180013d46`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013d22`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013d22`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180013dce`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180013dce`

## pseudocode

```c
__int64 __fastcall AicpCreateBindingHandle(unsigned __int16 *a1, __int64 a2, void **a3)
{
  void *v4; // rdi
  DWORD LastError_0; // ebx
  HLOCAL v6; // rax
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-30h] BYREF
  __int128 v9; // [rsp+50h] [rbp-20h]
  void *v10; // [rsp+60h] [rbp-10h]
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp+20h] BYREF
  DWORD cbSid; // [rsp+98h] [rbp+28h] BYREF
  RPC_WSTR StringBinding; // [rsp+A8h] [rbp+38h] BYREF

  StringBinding = 0;
  v10 = 0;
  cbSid = 0;
  Binding = 0;
  v4 = 0;
  SecurityQOS = 0;
  v9 = 0;
  LastError_0 = RpcStringBindingComposeW(
                  (RPC_WSTR)L"58e604e8-9adb-4d2e-a464-3b0683fb1480",
                  (RPC_WSTR)L"ncalrpc",
                  0,
                  0,
                  0,
                  &StringBinding);
  if ( !LastError_0 )
  {
    LastError_0 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    RpcStringFreeW(&StringBinding);
    if ( !LastError_0 )
    {
      cbSid = 68;
      v6 = LocalAlloc_0(0x40u, 0x44u);
      v4 = v6;
      if ( v6 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid) )
        {
          v10 = v4;
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          LastError_0 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
          if ( !LastError_0 )
          {
            *a3 = Binding;
            Binding = 0;
          }
        }
        else
        {
          LastError_0 = GetLastError_0();
        }
      }
      else
      {
        LastError_0 = 8;
      }
    }
  }
  LocalFree_0(v4);
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError_0;
}

```

## disassembly

```asm
0x180013cc0  mov     r11, rsp
0x180013cc3  mov     [r11+18h], rbx
0x180013cc7  mov     [rsp-18h+cbSid], edx
0x180013ccb  mov     [r11+8], rcx
0x180013ccf  push    rbp
0x180013cd0  push    rsi
0x180013cd1  push    rdi
0x180013cd2  mov     rbp, rsp
0x180013cd5  sub     rsp, 70h
0x180013cd9  xor     eax, eax
0x180013cdb  mov     [rbp+StringBinding], 0
0x180013ce3  xorps   xmm0, xmm0
0x180013ce6  mov     [rbp+var_10], rax
0x180013cea  mov     [rbp+cbSid], eax
0x180013ced  lea     rdx, ProtSeq; "ncalrpc"
0x180013cf4  lea     rax, [rbp+StringBinding]
0x180013cf8  mov     [rbp+Binding], 0
0x180013d00  mov     rsi, r8
0x180013d03  mov     [r11-60h], rax
0x180013d07  xor     edi, edi
0x180013d09  lea     rcx, ObjUuid; "58e604e8-9adb-4d2e-a464-3b0683fb1480"
0x180013d10  xor     r9d, r9d; Endpoint
0x180013d13  mov     [r11-68h], rdi
0x180013d17  xor     r8d, r8d; NetworkAddr
0x180013d1a  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x180013d1e  movups  [rbp+var_20], xmm0
0x180013d22  call    cs:__imp_RpcStringBindingComposeW
0x180013d28  mov     ebx, eax
0x180013d2a  test    eax, eax
0x180013d2c  jnz     loc_180013DE9
0x180013d32  mov     rcx, [rbp+StringBinding]; StringBinding
0x180013d36  lea     rdx, [rbp+Binding]; Binding
0x180013d3a  call    cs:__imp_RpcBindingFromStringBindingW
0x180013d40  lea     rcx, [rbp+StringBinding]; String
0x180013d44  mov     ebx, eax
0x180013d46  call    cs:__imp_RpcStringFreeW
0x180013d4c  test    ebx, ebx
0x180013d4e  jnz     loc_180013DE9
0x180013d54  lea     edx, [rdi+44h]; uBytes
0x180013d57  lea     ecx, [rdi+40h]; uFlags
0x180013d5a  mov     [rbp+cbSid], edx
0x180013d5d  call    LocalAlloc_0
0x180013d62  mov     rdi, rax
0x180013d65  test    rax, rax
0x180013d68  jnz     short loc_180013D6F
0x180013d6a  lea     ebx, [rax+8]
0x180013d6d  jmp     short loc_180013DE9
0x180013d6f  xor     edx, edx; DomainSid
0x180013d71  lea     r9, [rbp+cbSid]; cbSid
0x180013d75  mov     r8, rdi; pSid
0x180013d78  lea     ecx, [rdx+16h]; WellKnownSidType
0x180013d7b  call    cs:__imp_CreateWellKnownSid
0x180013d81  test    eax, eax
0x180013d83  jnz     short loc_180013D8E
0x180013d85  call    GetLastError_0
0x180013d8a  mov     ebx, eax
0x180013d8c  jmp     short loc_180013DE9
0x180013d8e  mov     ecx, 3
0x180013d93  mov     [rbp+var_10], rdi
0x180013d97  mov     [rbp+var_30.Version], ecx
0x180013d9a  xor     edx, edx; ServerPrincName
0x180013d9c  mov     [rbp+var_30.ImpersonationType], ecx
0x180013d9f  lea     eax, [rcx-2]
0x180013da2  mov     [rbp+var_30.Capabilities], eax
0x180013da5  lea     r9d, [rcx+7]; AuthnSvc
0x180013da9  mov     [rbp+var_30.IdentityTracking], eax
0x180013dac  lea     r8d, [rcx+3]; AuthnLevel
0x180013db0  mov     rcx, [rbp+Binding]; Binding
0x180013db4  lea     rax, [rbp+var_30]
0x180013db8  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180013dbd  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x180013dc5  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x180013dce  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180013dd4  mov     ebx, eax
0x180013dd6  test    eax, eax
0x180013dd8  jnz     short loc_180013DE9
0x180013dda  mov     rax, [rbp+Binding]
0x180013dde  mov     [rsi], rax
0x180013de1  mov     [rbp+Binding], 0
0x180013de9  mov     rcx, rdi; hMem
0x180013dec  call    LocalFree_0
0x180013df1  cmp     [rbp+Binding], 0
0x180013df6  jz      short loc_180013E02
0x180013df8  lea     rcx, [rbp+Binding]; Binding
0x180013dfc  call    cs:__imp_RpcBindingFree
0x180013e02  mov     eax, ebx
0x180013e04  mov     rbx, [rsp+70h+arg_10]
0x180013e0c  add     rsp, 70h
0x180013e10  pop     rdi
0x180013e11  pop     rsi
0x180013e12  pop     rbp
0x180013e13  retn
```
