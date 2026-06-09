# SecurityManager::InitializeRpcClient(void)

- ea: `0x140273348`
- end: `0x140273584`
- name: `?InitializeRpcClient@SecurityManager@@AEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1402741a0`

## callees

- `0x14005adc4`
- `0x14005ae4c`
- `0x1400b42b0`
- `0x1400b652c`
- `0x140132940`
- `0x1401335fc`
- `0x140273348`
- `0x140274914`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1402733ce`
- `RPCRT4!RpcStringFreeW` at `0x140273433`
- `RPCRT4!RpcStringFreeW` at `0x140273551`
- `RPCRT4!RpcStringFreeW` at `0x1402733ce`
- `RPCRT4!RpcStringFreeW` at `0x140273433`
- `RPCRT4!RpcStringFreeW` at `0x140273551`
- `RPCRT4!RpcBindingSetOption` at `0x1402734dc`
- `RPCRT4!RpcBindingSetOption` at `0x1402734dc`
- `RPCRT4!RpcStringBindingComposeW` at `0x1402733ff`
- `RPCRT4!RpcStringBindingComposeW` at `0x1402733ff`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14027352d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14027352d`
- `RPCRT4!RpcEpResolveBinding` at `0x1402734b0`
- `RPCRT4!RpcEpResolveBinding` at `0x1402734b0`
- `RPCRT4!RpcBindingFree` at `0x14027348a`
- `RPCRT4!RpcBindingFree` at `0x14027348a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140273452`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140273452`

## string_xrefs

- `0x1402733b0`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273418`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
__int64 __fastcall SecurityManager::InitializeRpcClient(SecurityManager *this)
{
  int v2; // eax
  unsigned int v3; // edi
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  void *v8; // rdi
  RPC_BINDING_HANDLE v9; // rsi
  void *v10; // rcx
  int Options; // [rsp+20h] [rbp-99h]
  unsigned int Optionsa; // [rsp+20h] [rbp-99h]
  _BYTE v13[8]; // [rsp+40h] [rbp-79h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-71h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE v16; // [rsp+58h] [rbp-61h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int16 Endpoint[64]; // [rsp+70h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  String = 0;
  memset_0(Endpoint, 0, sizeof(Endpoint));
  v2 = StringCchPrintfW(Endpoint, 0x40u, L"%016llX", *((_QWORD *)this + 48));
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E5,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v2,
      Options);
    return v3;
  }
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &String);
  if ( v5 )
  {
    v6 = 2288;
LABEL_5:
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v6,
           (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
           (const char *)v5,
           Optionsa);
    if ( String )
      RpcStringFreeW(&String);
    return v7;
  }
  Binding = 0;
  v5 = RpcBindingFromStringBindingW(String, &Binding);
  if ( v5 )
  {
    v6 = 2296;
    goto LABEL_5;
  }
  v8 = (void *)*((_QWORD *)this + 46);
  v9 = Binding;
  if ( v8 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v13);
    v16 = v8;
    RpcBindingFree(&v16);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
  }
  *((_QWORD *)this + 46) = v9;
  v5 = RpcEpResolveBinding(v9, qword_1402DBD20);
  if ( v5 )
  {
    v6 = 2305;
    goto LABEL_5;
  }
  v5 = RpcBindingSetOption(*((RPC_BINDING_HANDLE *)this + 46), 0xCu, 0x15F90u);
  if ( v5 )
  {
    v6 = 2316;
    goto LABEL_5;
  }
  v10 = (void *)*((_QWORD *)this + 46);
  *(_QWORD *)&SecurityQOS.Version = 1;
  SecurityQOS.IdentityTracking = 0;
  SecurityQOS.ImpersonationType = 2;
  v5 = RpcBindingSetAuthInfoExW(v10, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
  if ( v5 )
  {
    v6 = 2355;
    goto LABEL_5;
  }
  if ( String )
    RpcStringFreeW(&String);
  return 0;
}

```

## disassembly

```asm
0x140273348  mov     [rsp-8+arg_8], rbx
0x14027334d  mov     [rsp-8+arg_10], rsi
0x140273352  push    rbp
0x140273353  push    rdi
0x140273354  push    r14
0x140273356  lea     rbp, [rsp-47h]
0x14027335b  sub     rsp, 100h
0x140273362  mov     rax, cs:__security_cookie
0x140273369  xor     rax, rsp
0x14027336c  mov     [rbp+57h+var_20], rax
0x140273370  mov     rbx, rcx
0x140273373  xor     r14d, r14d
0x140273376  lea     rcx, [rbp+57h+Endpoint]; void *
0x14027337a  mov     [rbp+57h+String], r14
0x14027337e  xor     edx, edx; Val
0x140273380  mov     r8d, 80h; Size
0x140273386  call    memset_0
0x14027338b  mov     r9, [rbx+180h]
0x140273392  lea     r8, a016llx; "%016llX"
0x140273399  lea     edx, [r14+40h]; unsigned __int64
0x14027339d  lea     rcx, [rbp+57h+Endpoint]; unsigned __int16 *
0x1402733a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1402733a6  mov     edi, eax
0x1402733a8  test    eax, eax
0x1402733aa  jns     short loc_1402733E1
0x1402733ac  mov     rcx, [rbp+5Fh]; this
0x1402733b0  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402733b7  mov     r9d, eax; char *
0x1402733ba  mov     edx, 8E5h; void *
0x1402733bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402733c4  cmp     [rbp+57h+String], r14
0x1402733c8  jz      short loc_1402733DA
0x1402733ca  lea     rcx, [rbp+57h+String]; String
0x1402733ce  call    cs:__imp_RpcStringFreeW
0x1402733d5  nop     dword ptr [rax+rax+00h]
0x1402733da  mov     eax, edi
0x1402733dc  jmp     loc_14027355F
0x1402733e1  lea     rax, [rbp+57h+String]
0x1402733e5  xor     r8d, r8d; NetworkAddr
0x1402733e8  mov     [rsp+110h+StringBinding], rax; StringBinding
0x1402733ed  lea     r9, [rbp+57h+Endpoint]; Endpoint
0x1402733f1  lea     rdx, ProtSeq; "ncalrpc"
0x1402733f8  mov     [rsp+110h+Options], r14; unsigned int
0x1402733fd  xor     ecx, ecx; ObjUuid
0x1402733ff  call    cs:__imp_RpcStringBindingComposeW
0x140273406  nop     dword ptr [rax+rax+00h]
0x14027340b  test    eax, eax
0x14027340d  jz      short loc_140273446
0x14027340f  mov     edx, 8F0h; void *
0x140273414  mov     rcx, [rbp+5Fh]; this
0x140273418  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027341f  mov     r9d, eax; char *
0x140273422  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140273427  mov     ebx, eax
0x140273429  cmp     [rbp+57h+String], r14
0x14027342d  jz      short loc_14027343F
0x14027342f  lea     rcx, [rbp+57h+String]; String
0x140273433  call    cs:__imp_RpcStringFreeW
0x14027343a  nop     dword ptr [rax+rax+00h]
0x14027343f  mov     eax, ebx
0x140273441  jmp     loc_14027355F
0x140273446  mov     rcx, [rbp+57h+String]; StringBinding
0x14027344a  lea     rdx, [rbp+57h+Binding]; Binding
0x14027344e  mov     [rbp+57h+Binding], r14
0x140273452  call    cs:__imp_RpcBindingFromStringBindingW
0x140273459  nop     dword ptr [rax+rax+00h]
0x14027345e  test    eax, eax
0x140273460  jz      short loc_140273469
0x140273462  mov     edx, 8F8h
0x140273467  jmp     short loc_140273414
0x140273469  mov     rdi, [rbx+170h]
0x140273470  mov     rsi, [rbp+57h+Binding]
0x140273474  test    rdi, rdi
0x140273477  jz      short loc_14027349F
0x140273479  lea     rcx, [rbp+57h+var_D0]; this
0x14027347d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140273482  lea     rcx, [rbp+57h+var_B8]; Binding
0x140273486  mov     [rbp+57h+var_B8], rdi
0x14027348a  call    cs:__imp_RpcBindingFree
0x140273491  nop     dword ptr [rax+rax+00h]
0x140273496  lea     rcx, [rbp+57h+var_D0]; this
0x14027349a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14027349f  lea     rdx, qword_1402DBD20; IfSpec
0x1402734a6  mov     [rbx+170h], rsi
0x1402734ad  mov     rcx, rsi; Binding
0x1402734b0  call    cs:__imp_RpcEpResolveBinding
0x1402734b7  nop     dword ptr [rax+rax+00h]
0x1402734bc  test    eax, eax
0x1402734be  jz      short loc_1402734CA
0x1402734c0  mov     edx, 901h
0x1402734c5  jmp     loc_140273414
0x1402734ca  mov     rcx, [rbx+170h]; hBinding
0x1402734d1  mov     edx, 0Ch; option
0x1402734d6  mov     r8d, 15F90h; optionValue
0x1402734dc  call    cs:__imp_RpcBindingSetOption
0x1402734e3  nop     dword ptr [rax+rax+00h]
0x1402734e8  test    eax, eax
0x1402734ea  jz      short loc_1402734F6
0x1402734ec  mov     edx, 90Ch
0x1402734f1  jmp     loc_140273414
0x1402734f6  mov     rcx, [rbx+170h]; Binding
0x1402734fd  lea     rax, [rbp+57h+var_B0]
0x140273501  xor     edx, edx; ServerPrincName
0x140273503  mov     [rsp+110h+SecurityQOS], rax; SecurityQOS
0x140273508  mov     dword ptr [rsp+110h+StringBinding], r14d; AuthzSvc
0x14027350d  mov     qword ptr [rbp+57h+var_B0.Version], 1
0x140273515  mov     [rbp+57h+var_B0.IdentityTracking], r14d
0x140273519  lea     r9d, [rdx+0Ah]; AuthnSvc
0x14027351d  mov     [rbp+57h+var_B0.ImpersonationType], 2
0x140273524  lea     r8d, [rdx+6]; AuthnLevel
0x140273528  mov     [rsp+110h+Options], r14; AuthIdentity
0x14027352d  call    cs:__imp_RpcBindingSetAuthInfoExW
0x140273534  nop     dword ptr [rax+rax+00h]
0x140273539  test    eax, eax
0x14027353b  jz      short loc_140273547
0x14027353d  mov     edx, 933h
0x140273542  jmp     loc_140273414
0x140273547  cmp     [rbp+57h+String], r14
0x14027354b  jz      short loc_14027355D
0x14027354d  lea     rcx, [rbp+57h+String]; String
0x140273551  call    cs:__imp_RpcStringFreeW
0x140273558  nop     dword ptr [rax+rax+00h]
0x14027355d  xor     eax, eax
0x14027355f  mov     rcx, [rbp+57h+var_20]
0x140273563  xor     rcx, rsp; StackCookie
0x140273566  call    __security_check_cookie
0x14027356b  lea     r11, [rsp+110h+var_10]
0x140273573  mov     rbx, [r11+28h]
0x140273577  mov     rsi, [r11+30h]
0x14027357b  mov     rsp, r11
0x14027357e  pop     r14
0x140273580  pop     rdi
0x140273581  pop     rbp
0x140273582  retn
```
