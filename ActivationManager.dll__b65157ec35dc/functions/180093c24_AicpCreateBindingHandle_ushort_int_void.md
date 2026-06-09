# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x180093c24`
- end: `0x180093d79`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `341`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005697c`

## callees

- `0x18005bb2c`
- `0x180093c24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093cc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093cc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093d50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093d50`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180093ce0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180093ce0`
- `RPCRT4!RpcStringFreeW` at `0x180093caa`
- `RPCRT4!RpcStringFreeW` at `0x180093caa`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180093d32`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180093d32`
- `RPCRT4!RpcStringBindingComposeW` at `0x180093c86`
- `RPCRT4!RpcStringBindingComposeW` at `0x180093c86`
- `RPCRT4!RpcBindingFree` at `0x180093d61`
- `RPCRT4!RpcBindingFree` at `0x180093d61`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180093c9e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180093c9e`

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
                  (RPC_WSTR)L"0497B57D-2E66-424F-A0C6-157CD5D41700",
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
      v6 = LocalAlloc(0x40u, 0x44u);
      v4 = v6;
      if ( v6 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid) )
        {
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          *(_QWORD *)&SecurityQOS.Capabilities = 1;
          v10 = v4;
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
  LocalFree(v4);
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError_0;
}

```

## disassembly

```asm
0x180093c24  mov     r11, rsp
0x180093c27  mov     [r11+18h], rbx
0x180093c2b  mov     [rsp-18h+cbSid], edx
0x180093c2f  mov     [r11+8], rcx
0x180093c33  push    rbp
0x180093c34  push    rsi
0x180093c35  push    rdi
0x180093c36  mov     rbp, rsp
0x180093c39  sub     rsp, 70h
0x180093c3d  xor     eax, eax
0x180093c3f  mov     [rbp+StringBinding], 0
0x180093c47  xorps   xmm0, xmm0
0x180093c4a  mov     [rbp+var_10], rax
0x180093c4e  mov     [rbp+cbSid], eax
0x180093c51  lea     rdx, ProtSeq; "ncalrpc"
0x180093c58  lea     rax, [rbp+StringBinding]
0x180093c5c  mov     [rbp+Binding], 0
0x180093c64  mov     rsi, r8
0x180093c67  mov     [r11-60h], rax
0x180093c6b  xor     edi, edi
0x180093c6d  lea     rcx, ObjUuid; "0497B57D-2E66-424F-A0C6-157CD5D41700"
0x180093c74  xor     r9d, r9d; Endpoint
0x180093c77  mov     [r11-68h], rdi
0x180093c7b  xor     r8d, r8d; NetworkAddr
0x180093c7e  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x180093c82  movups  [rbp+var_20], xmm0
0x180093c86  call    cs:__imp_RpcStringBindingComposeW
0x180093c8c  mov     ebx, eax
0x180093c8e  test    eax, eax
0x180093c90  jnz     loc_180093D4D
0x180093c96  mov     rcx, [rbp+StringBinding]; StringBinding
0x180093c9a  lea     rdx, [rbp+Binding]; Binding
0x180093c9e  call    cs:__imp_RpcBindingFromStringBindingW
0x180093ca4  lea     rcx, [rbp+StringBinding]; String
0x180093ca8  mov     ebx, eax
0x180093caa  call    cs:__imp_RpcStringFreeW
0x180093cb0  test    ebx, ebx
0x180093cb2  jnz     loc_180093D4D
0x180093cb8  lea     edx, [rdi+44h]; uBytes
0x180093cbb  lea     ecx, [rdi+40h]; uFlags
0x180093cbe  mov     [rbp+cbSid], edx
0x180093cc1  call    cs:__imp_LocalAlloc
0x180093cc7  mov     rdi, rax
0x180093cca  test    rax, rax
0x180093ccd  jnz     short loc_180093CD4
0x180093ccf  lea     ebx, [rax+8]
0x180093cd2  jmp     short loc_180093D4D
0x180093cd4  xor     edx, edx; DomainSid
0x180093cd6  lea     r9, [rbp+cbSid]; cbSid
0x180093cda  mov     r8, rdi; pSid
0x180093cdd  lea     ecx, [rdx+16h]; WellKnownSidType
0x180093ce0  call    cs:__imp_CreateWellKnownSid
0x180093ce6  test    eax, eax
0x180093ce8  jnz     short loc_180093CF3
0x180093cea  call    GetLastError_0
0x180093cef  mov     ebx, eax
0x180093cf1  jmp     short loc_180093D4D
0x180093cf3  mov     rcx, [rbp+Binding]; Binding
0x180093cf7  mov     eax, 3
0x180093cfc  xor     edx, edx; ServerPrincName
0x180093cfe  mov     [rbp+var_30.Version], eax
0x180093d01  mov     [rbp+var_30.ImpersonationType], eax
0x180093d04  lea     rax, [rbp+var_30]
0x180093d08  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180093d0d  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x180093d15  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180093d19  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x180093d22  lea     r8d, [rdx+6]; AuthnLevel
0x180093d26  mov     qword ptr [rbp+var_30.Capabilities], 1
0x180093d2e  mov     [rbp+var_10], rdi
0x180093d32  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180093d38  mov     ebx, eax
0x180093d3a  test    eax, eax
0x180093d3c  jnz     short loc_180093D4D
0x180093d3e  mov     rax, [rbp+Binding]
0x180093d42  mov     [rsi], rax
0x180093d45  mov     [rbp+Binding], 0
0x180093d4d  mov     rcx, rdi; hMem
0x180093d50  call    cs:__imp_LocalFree
0x180093d56  cmp     [rbp+Binding], 0
0x180093d5b  jz      short loc_180093D67
0x180093d5d  lea     rcx, [rbp+Binding]; Binding
0x180093d61  call    cs:__imp_RpcBindingFree
0x180093d67  mov     eax, ebx
0x180093d69  mov     rbx, [rsp+70h+arg_10]
0x180093d71  add     rsp, 70h
0x180093d75  pop     rdi
0x180093d76  pop     rsi
0x180093d77  pop     rbp
0x180093d78  retn
```
