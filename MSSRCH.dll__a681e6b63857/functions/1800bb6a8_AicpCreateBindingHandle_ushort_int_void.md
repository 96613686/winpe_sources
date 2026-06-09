# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x1800bb6a8`
- end: `0x1800bb7fb`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `339`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800baffc`

## callees

- `0x1800bb6a8`
- `0x18012581f`
- `0x180125976`
- `0x180125982`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bb763`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bb763`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800bb722`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800bb722`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800bb70a`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800bb70a`
- `RPCRT4!RpcStringFreeW` at `0x1800bb72e`
- `RPCRT4!RpcStringFreeW` at `0x1800bb72e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800bb7b5`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800bb7b5`
- `RPCRT4!RpcBindingFree` at `0x1800bb7e3`
- `RPCRT4!RpcBindingFree` at `0x1800bb7e3`

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
      v6 = LocalAlloc_0(0x40u, 0x44u);
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
  LocalFree_0(v4);
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError_0;
}

```

## disassembly

```asm
0x1800bb6a8  mov     r11, rsp
0x1800bb6ab  mov     [r11+18h], rbx
0x1800bb6af  mov     [rsp-18h+cbSid], edx
0x1800bb6b3  mov     [r11+8], rcx
0x1800bb6b7  push    rbp
0x1800bb6b8  push    rsi
0x1800bb6b9  push    rdi
0x1800bb6ba  mov     rbp, rsp
0x1800bb6bd  sub     rsp, 70h
0x1800bb6c1  xor     eax, eax
0x1800bb6c3  mov     [rbp+StringBinding], 0
0x1800bb6cb  xorps   xmm0, xmm0
0x1800bb6ce  mov     [rbp+var_10], rax
0x1800bb6d2  mov     [rbp+cbSid], eax
0x1800bb6d5  lea     rdx, ProtSeq; "ncalrpc"
0x1800bb6dc  lea     rax, [rbp+StringBinding]
0x1800bb6e0  mov     [rbp+Binding], 0
0x1800bb6e8  mov     rsi, r8
0x1800bb6eb  mov     [r11-60h], rax
0x1800bb6ef  xor     edi, edi
0x1800bb6f1  lea     rcx, ObjUuid; "0497B57D-2E66-424F-A0C6-157CD5D41700"
0x1800bb6f8  xor     r9d, r9d; Endpoint
0x1800bb6fb  mov     [r11-68h], rdi
0x1800bb6ff  xor     r8d, r8d; NetworkAddr
0x1800bb702  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x1800bb706  movups  [rbp+var_20], xmm0
0x1800bb70a  call    cs:__imp_RpcStringBindingComposeW
0x1800bb710  mov     ebx, eax
0x1800bb712  test    eax, eax
0x1800bb714  jnz     loc_1800BB7D0
0x1800bb71a  mov     rcx, [rbp+StringBinding]; StringBinding
0x1800bb71e  lea     rdx, [rbp+Binding]; Binding
0x1800bb722  call    cs:__imp_RpcBindingFromStringBindingW
0x1800bb728  lea     rcx, [rbp+StringBinding]; String
0x1800bb72c  mov     ebx, eax
0x1800bb72e  call    cs:__imp_RpcStringFreeW
0x1800bb734  test    ebx, ebx
0x1800bb736  jnz     loc_1800BB7D0
0x1800bb73c  lea     edx, [rdi+44h]; uBytes
0x1800bb73f  lea     ecx, [rdi+40h]; uFlags
0x1800bb742  mov     [rbp+cbSid], edx
0x1800bb745  call    LocalAlloc_0
0x1800bb74a  mov     rdi, rax
0x1800bb74d  test    rax, rax
0x1800bb750  jnz     short loc_1800BB757
0x1800bb752  lea     ebx, [rax+8]
0x1800bb755  jmp     short loc_1800BB7D0
0x1800bb757  xor     edx, edx; DomainSid
0x1800bb759  lea     r9, [rbp+cbSid]; cbSid
0x1800bb75d  mov     r8, rdi; pSid
0x1800bb760  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800bb763  call    cs:__imp_CreateWellKnownSid
0x1800bb769  test    eax, eax
0x1800bb76b  jnz     short loc_1800BB776
0x1800bb76d  call    GetLastError_0
0x1800bb772  mov     ebx, eax
0x1800bb774  jmp     short loc_1800BB7D0
0x1800bb776  mov     rcx, [rbp+Binding]; Binding
0x1800bb77a  mov     eax, 3
0x1800bb77f  xor     edx, edx; ServerPrincName
0x1800bb781  mov     [rbp+var_30.Version], eax
0x1800bb784  mov     [rbp+var_30.ImpersonationType], eax
0x1800bb787  lea     rax, [rbp+var_30]
0x1800bb78b  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x1800bb790  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x1800bb798  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1800bb79c  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x1800bb7a5  lea     r8d, [rdx+6]; AuthnLevel
0x1800bb7a9  mov     qword ptr [rbp+var_30.Capabilities], 1
0x1800bb7b1  mov     [rbp+var_10], rdi
0x1800bb7b5  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800bb7bb  mov     ebx, eax
0x1800bb7bd  test    eax, eax
0x1800bb7bf  jnz     short loc_1800BB7D0
0x1800bb7c1  mov     rax, [rbp+Binding]
0x1800bb7c5  mov     [rsi], rax
0x1800bb7c8  mov     [rbp+Binding], 0
0x1800bb7d0  mov     rcx, rdi; hMem
0x1800bb7d3  call    LocalFree_0
0x1800bb7d8  cmp     [rbp+Binding], 0
0x1800bb7dd  jz      short loc_1800BB7E9
0x1800bb7df  lea     rcx, [rbp+Binding]; Binding
0x1800bb7e3  call    cs:__imp_RpcBindingFree
0x1800bb7e9  mov     eax, ebx
0x1800bb7eb  mov     rbx, [rsp+70h+arg_10]
0x1800bb7f3  add     rsp, 70h
0x1800bb7f7  pop     rdi
0x1800bb7f8  pop     rsi
0x1800bb7f9  pop     rbp
0x1800bb7fa  retn
```
