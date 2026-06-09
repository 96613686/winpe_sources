# GetRpcHandle(void)

- ea: `0x18000762c`
- end: `0x18000784f`
- name: `?GetRpcHandle@@YA?AV?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@XZ`
- size: `547`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e9e0`
- `0x18000f060`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## callees

- `0x180001960`
- `0x18000762c`
- `0x18000be30`
- `0x18000be60`
- `0x18000e9c4`
- `0x18000ef94`
- `0x18000efb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007835`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000771c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000771c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007772`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007772`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007687`
- `RPCRT4!RpcStringBindingComposeW` at `0x180007687`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800076be`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800076be`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetRpcHandle(__int64 a1)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // edx
  int v4; // r9d
  RPC_STATUS v5; // eax
  unsigned int v6; // edx
  int v7; // r9d
  const char *v8; // r8
  RPC_STATUS v9; // eax
  unsigned int v10; // edx
  int v11; // r9d
  signed int v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  signed int LastError; // eax
  int v17; // edx
  unsigned int v18; // r8d
  void **v19; // [rsp+68h] [rbp-41h] BYREF
  PSID pSid; // [rsp+70h] [rbp-39h] BYREF
  void **v21; // [rsp+78h] [rbp-31h] BYREF
  RPC_WSTR StringBinding; // [rsp+80h] [rbp-29h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+88h] [rbp-21h] BYREF
  __int128 v24; // [rsp+98h] [rbp-11h]
  PSID v25; // [rsp+A8h] [rbp-1h]
  __int64 v26; // [rsp+B0h] [rbp+7h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp+Fh] BYREF

  v26 = a1;
  v21 = &Microsoft::WRL::Wrappers::HandleT<RpcStringBindingTraits>::`vftable';
  StringBinding = 0;
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &StringBinding);
  if ( v2 >= 1 )
    v2 |= 0x80010000;
  if ( v2 < 0 )
LABEL_20:
    wil::details::in1diag3::_Throw_Hr((wil::details::in1diag3 *)0x240, v3, (const char *)(unsigned int)v2, v4);
  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  v5 = RpcBindingFromStringBindingW(StringBinding, (RPC_BINDING_HANDLE *)(a1 + 8));
  if ( v5 >= 1 )
    v5 |= 0x80010000;
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr((wil::details::in1diag3 *)0x243, v6, (const char *)(unsigned int)v5, v7);
  v19 = &Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::`vftable';
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      (wil::details::in1diag3 *)0x247,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
      v8);
  v24 = 0;
  SecurityQOS.Version = 3;
  SecurityQOS.Capabilities = 1;
  SecurityQOS.IdentityTracking = 1;
  SecurityQOS.ImpersonationType = 3;
  v25 = pSid;
  v9 = RpcBindingSetAuthInfoExW(*(RPC_BINDING_HANDLE *)(a1 + 8), 0, 6u, 0xAu, 0, 0, &SecurityQOS);
  if ( v9 >= 1 )
    v9 |= 0x80010000;
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr((wil::details::in1diag3 *)0x251, v10, (const char *)(unsigned int)v9, v11);
  v19 = &Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::`vftable';
  if ( pSid )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::InternalClose(&v19) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v17, v18);
      JUMPOUT(0x18000784ELL);
    }
    pSid = 0;
  }
  v21 = &Microsoft::WRL::Wrappers::HandleT<RpcStringBindingTraits>::`vftable';
  if ( StringBinding && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RpcStringBindingTraits>::InternalClose(&v21) )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    goto LABEL_20;
  }
  return a1;
}

```

## disassembly

```asm
0x18000762c  push    rbp
0x18000762e  push    rbx
0x18000762f  push    rsi
0x180007630  push    rdi
0x180007631  push    r12
0x180007633  push    r13
0x180007635  lea     rbp, [rsp-2Fh]
0x18000763a  sub     rsp, 0D8h
0x180007641  mov     rax, cs:__security_cookie
0x180007648  xor     rax, rsp
0x18000764b  mov     [rbp+57h+var_40], rax
0x18000764f  mov     rbx, rcx
0x180007652  mov     [rbp+57h+var_50], rcx
0x180007656  xor     esi, esi
0x180007658  mov     [rbp+57h+var_A0], esi
0x18000765b  lea     r13, ??_7?$HandleT@URpcStringBindingTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcStringBindingTraits>::`vftable'
0x180007662  mov     [rbp+57h+var_88], r13
0x180007666  mov     [rbp+57h+var_80], rsi
0x18000766a  lea     rax, [rbp+57h+var_80]
0x18000766e  mov     [rsp+100h+StringBinding], rax; StringBinding
0x180007673  mov     [rsp+100h+Options], rsi; Options
0x180007678  xor     r9d, r9d; Endpoint
0x18000767b  xor     r8d, r8d; NetworkAddr
0x18000767e  lea     rdx, ProtSeq; "ncalrpc"
0x180007685  xor     ecx, ecx; ObjUuid
0x180007687  call    cs:__imp_RpcStringBindingComposeW
0x18000768d  cmp     eax, 1
0x180007690  jl      short loc_180007697
0x180007692  or      eax, 80010000h
0x180007697  test    eax, eax
0x180007699  js      loc_1800077F9
0x18000769f  lea     rax, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x1800076a6  mov     [rbx], rax
0x1800076a9  lea     rdi, [rbx+8]
0x1800076ad  mov     [rdi], rsi
0x1800076b0  mov     [rbp+57h+var_A0], 1
0x1800076b7  mov     rdx, rdi; Binding
0x1800076ba  mov     rcx, [rbp+57h+var_80]; StringBinding
0x1800076be  call    cs:__imp_RpcBindingFromStringBindingW
0x1800076c4  cmp     eax, 1
0x1800076c7  jl      short loc_1800076CE
0x1800076c9  or      eax, 80010000h
0x1800076ce  test    eax, eax
0x1800076d0  js      loc_180007807
0x1800076d6  lea     r12, ??_7?$HandleT@USidBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::`vftable'
0x1800076dd  mov     [rbp+57h+var_98], r12
0x1800076e1  mov     [rbp+57h+var_90], rsi
0x1800076e5  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800076e8  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800076ee  lea     rax, [rbp+57h+var_90]
0x1800076f2  mov     [rsp+100h+pSid], rax; pSid
0x1800076f7  mov     [rsp+100h+nSubAuthority7], esi; nSubAuthority7
0x1800076fb  mov     [rsp+100h+nSubAuthority6], esi; nSubAuthority6
0x1800076ff  mov     [rsp+100h+nSubAuthority5], esi; nSubAuthority5
0x180007703  mov     [rsp+100h+nSubAuthority4], esi; nSubAuthority4
0x180007707  mov     dword ptr [rsp+100h+StringBinding], esi; nSubAuthority3
0x18000770b  mov     dword ptr [rsp+100h+Options], esi; nSubAuthority2
0x18000770f  xor     r9d, r9d; nSubAuthority1
0x180007712  lea     r8d, [r9+13h]; nSubAuthority0
0x180007716  mov     dl, 1; nSubAuthorityCount
0x180007718  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000771c  call    cs:__imp_AllocateAndInitializeSid
0x180007722  test    eax, eax
0x180007724  jz      loc_180007815
0x18000772a  xorps   xmm0, xmm0
0x18000772d  movdqu  [rbp+57h+var_68], xmm0
0x180007732  mov     eax, 3
0x180007737  mov     [rbp+57h+SecurityQOS.Version], eax
0x18000773a  mov     [rbp+57h+SecurityQOS.Capabilities], 1
0x180007741  mov     [rbp+57h+SecurityQOS.IdentityTracking], 1
0x180007748  mov     [rbp+57h+SecurityQOS.ImpersonationType], eax
0x18000774b  mov     rax, [rbp+57h+var_90]
0x18000774f  mov     [rbp+57h+var_58], rax
0x180007753  lea     rax, [rbp+57h+SecurityQOS]
0x180007757  mov     qword ptr [rsp+100h+nSubAuthority4], rax; SecurityQOS
0x18000775c  mov     dword ptr [rsp+100h+StringBinding], esi; AuthzSvc
0x180007760  mov     [rsp+100h+Options], rsi; AuthIdentity
0x180007765  xor     edx, edx; ServerPrincName
0x180007767  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18000776b  lea     r8d, [rdx+6]; AuthnLevel
0x18000776f  mov     rcx, [rdi]; Binding
0x180007772  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180007778  cmp     eax, 1
0x18000777b  jl      short loc_180007782
0x18000777d  or      eax, 80010000h
0x180007782  test    eax, eax
0x180007784  js      loc_180007827
0x18000778a  mov     [rbp+57h+var_98], r12
0x18000778e  cmp     [rbp+57h+var_90], rsi
0x180007792  jz      short loc_1800077A9
0x180007794  lea     rcx, [rbp+57h+var_98]
0x180007798  call    ?InternalClose@?$HandleT@USidBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::InternalClose(void)
0x18000779d  test    al, al
0x18000779f  jz      loc_180007835
0x1800077a5  mov     [rbp+57h+var_90], rsi
0x1800077a9  mov     [rbp+57h+var_88], r13
0x1800077ad  cmp     [rbp+57h+var_80], rsi
0x1800077b1  jz      short loc_1800077C0
0x1800077b3  lea     rcx, [rbp+57h+var_88]
0x1800077b7  call    ?InternalClose@?$HandleT@URpcStringBindingTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcStringBindingTraits>::InternalClose(void)
0x1800077bc  test    al, al
0x1800077be  jz      short loc_1800077DF
0x1800077c0  mov     rax, rbx
0x1800077c3  mov     rcx, [rbp+57h+var_40]
0x1800077c7  xor     rcx, rsp; StackCookie
0x1800077ca  call    __security_check_cookie
0x1800077cf  add     rsp, 0D8h
0x1800077d6  pop     r13
0x1800077d8  pop     r12
0x1800077da  pop     rdi
0x1800077db  pop     rsi
0x1800077dc  pop     rbx
0x1800077dd  pop     rbp
0x1800077de  retn
0x1800077df  call    cs:__imp_GetLastError
0x1800077e5  test    eax, eax
0x1800077e7  jle     short loc_1800077F1
0x1800077e9  movzx   eax, ax
0x1800077ec  or      eax, 80070000h
0x1800077f1  mov     ecx, eax; this
0x1800077f3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800077f8  nop
0x1800077f9  mov     r8d, eax; char *
0x1800077fc  mov     ecx, 240h; this
0x180007801  call    ?_Throw_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(uint,char const *,long)
0x180007807  mov     r8d, eax; char *
0x18000780a  mov     ecx, 243h; this
0x18000780f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(uint,char const *,long)
0x180007815  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000781c  mov     ecx, 247h; this
0x180007821  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(uint,char const *)
0x180007827  mov     r8d, eax; char *
0x18000782a  mov     ecx, 251h; this
0x18000782f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(uint,char const *,long)
0x180007835  call    cs:__imp_GetLastError
0x18000783b  test    eax, eax
0x18000783d  jle     short loc_180007847
0x18000783f  movzx   eax, ax
0x180007842  or      eax, 80070000h
0x180007847  mov     ecx, eax; this
0x180007849  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
