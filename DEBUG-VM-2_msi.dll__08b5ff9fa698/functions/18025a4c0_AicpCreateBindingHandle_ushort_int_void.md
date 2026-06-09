# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x18025a4c0`
- end: `0x18025a614`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `340`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180259fb0`

## callees

- `0x1801701b2`
- `0x1801701d6`
- `0x1801701ee`
- `0x18025a4c0`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18025a5ce`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18025a5ce`
- `RPCRT4!RpcStringFreeW` at `0x18025a546`
- `RPCRT4!RpcStringFreeW` at `0x18025a546`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18025a53a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18025a53a`
- `RPCRT4!RpcBindingFree` at `0x18025a5fc`
- `RPCRT4!RpcBindingFree` at `0x18025a5fc`
- `RPCRT4!RpcStringBindingComposeW` at `0x18025a522`
- `RPCRT4!RpcStringBindingComposeW` at `0x18025a522`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18025a57b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18025a57b`

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
                  (RPC_WSTR)L"fd7a0523-dc70-43dd-9b2e-9c5ed48225b1",
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
0x18025a4c0  mov     r11, rsp
0x18025a4c3  mov     [r11+18h], rbx
0x18025a4c7  mov     [rsp-18h+cbSid], edx
0x18025a4cb  mov     [r11+8], rcx
0x18025a4cf  push    rbp
0x18025a4d0  push    rsi
0x18025a4d1  push    rdi
0x18025a4d2  mov     rbp, rsp
0x18025a4d5  sub     rsp, 70h
0x18025a4d9  xor     eax, eax
0x18025a4db  mov     [rbp+StringBinding], 0
0x18025a4e3  xorps   xmm0, xmm0
0x18025a4e6  mov     [rbp+var_10], rax
0x18025a4ea  mov     [rbp+cbSid], eax
0x18025a4ed  lea     rdx, ProtSeq; "ncalrpc"
0x18025a4f4  lea     rax, [rbp+StringBinding]
0x18025a4f8  mov     [rbp+Binding], 0
0x18025a500  mov     rsi, r8
0x18025a503  mov     [r11-60h], rax
0x18025a507  xor     edi, edi
0x18025a509  lea     rcx, ObjUuid; "fd7a0523-dc70-43dd-9b2e-9c5ed48225b1"
0x18025a510  xor     r9d, r9d; Endpoint
0x18025a513  mov     [r11-68h], rdi
0x18025a517  xor     r8d, r8d; NetworkAddr
0x18025a51a  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x18025a51e  movups  [rbp+var_20], xmm0
0x18025a522  call    cs:__imp_RpcStringBindingComposeW
0x18025a528  mov     ebx, eax
0x18025a52a  test    eax, eax
0x18025a52c  jnz     loc_18025A5E9
0x18025a532  mov     rcx, [rbp+StringBinding]; StringBinding
0x18025a536  lea     rdx, [rbp+Binding]; Binding
0x18025a53a  call    cs:__imp_RpcBindingFromStringBindingW
0x18025a540  lea     rcx, [rbp+StringBinding]; String
0x18025a544  mov     ebx, eax
0x18025a546  call    cs:__imp_RpcStringFreeW
0x18025a54c  test    ebx, ebx
0x18025a54e  jnz     loc_18025A5E9
0x18025a554  lea     edx, [rdi+44h]; uBytes
0x18025a557  lea     ecx, [rdi+40h]; uFlags
0x18025a55a  mov     [rbp+cbSid], edx
0x18025a55d  call    LocalAlloc_0
0x18025a562  mov     rdi, rax
0x18025a565  test    rax, rax
0x18025a568  jnz     short loc_18025A56F
0x18025a56a  lea     ebx, [rax+8]
0x18025a56d  jmp     short loc_18025A5E9
0x18025a56f  xor     edx, edx; DomainSid
0x18025a571  lea     r9, [rbp+cbSid]; cbSid
0x18025a575  mov     r8, rdi; pSid
0x18025a578  lea     ecx, [rdx+16h]; WellKnownSidType
0x18025a57b  call    cs:__imp_CreateWellKnownSid
0x18025a581  test    eax, eax
0x18025a583  jnz     short loc_18025A58E
0x18025a585  call    GetLastError_0
0x18025a58a  mov     ebx, eax
0x18025a58c  jmp     short loc_18025A5E9
0x18025a58e  mov     ecx, 3
0x18025a593  mov     [rbp+var_10], rdi
0x18025a597  mov     [rbp+var_30.Version], ecx
0x18025a59a  xor     edx, edx; ServerPrincName
0x18025a59c  mov     [rbp+var_30.ImpersonationType], ecx
0x18025a59f  lea     eax, [rcx-2]
0x18025a5a2  mov     [rbp+var_30.Capabilities], eax
0x18025a5a5  lea     r9d, [rcx+7]; AuthnSvc
0x18025a5a9  mov     [rbp+var_30.IdentityTracking], eax
0x18025a5ac  lea     r8d, [rcx+3]; AuthnLevel
0x18025a5b0  mov     rcx, [rbp+Binding]; Binding
0x18025a5b4  lea     rax, [rbp+var_30]
0x18025a5b8  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x18025a5bd  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x18025a5c5  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x18025a5ce  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18025a5d4  mov     ebx, eax
0x18025a5d6  test    eax, eax
0x18025a5d8  jnz     short loc_18025A5E9
0x18025a5da  mov     rax, [rbp+Binding]
0x18025a5de  mov     [rsi], rax
0x18025a5e1  mov     [rbp+Binding], 0
0x18025a5e9  mov     rcx, rdi; hMem
0x18025a5ec  call    LocalFree_0
0x18025a5f1  cmp     [rbp+Binding], 0
0x18025a5f6  jz      short loc_18025A602
0x18025a5f8  lea     rcx, [rbp+Binding]; Binding
0x18025a5fc  call    cs:__imp_RpcBindingFree
0x18025a602  mov     eax, ebx
0x18025a604  mov     rbx, [rsp+70h+arg_10]
0x18025a60c  add     rsp, 70h
0x18025a610  pop     rdi
0x18025a611  pop     rsi
0x18025a612  pop     rbp
0x18025a613  retn
```
