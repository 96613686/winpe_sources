# GetRpcBinding

- ea: `0x18000fed4`
- end: `0x18001003d`
- name: `GetRpcBinding`
- size: `361`
- prototype: `RPC_BINDING_HANDLE *__fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010ac0`

## callees

- `0x180005318`
- `0x180005a38`
- `0x18000a674`
- `0x18000fc10`
- `0x18000fed4`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000ff66`
- `RPCRT4!RpcBindingFree` at `0x18000ff66`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ff7f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ff7f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ff20`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ff20`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000fff5`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000fff5`

## string_xrefs

- `0x18000ff3d`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`
- `0x18000ff9c`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`
- `0x180010012`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
RPC_BINDING_HANDLE *__fastcall GetRpcBinding(RPC_BINDING_HANDLE *Binding)
{
  RPC_STATUS v2; // eax
  RPC_BINDING_HANDLE v3; // rdi
  RPC_STATUS v4; // eax
  RPC_STATUS v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int Options; // [rsp+20h] [rbp-29h]
  int Optionsa; // [rsp+20h] [rbp-29h]
  _BYTE SecurityQOS[20]; // [rsp+48h] [rbp-1h] BYREF
  int v12; // [rsp+5Ch] [rbp+13h]
  __int128 v13; // [rsp+60h] [rbp+17h]
  __int64 v14; // [rsp+70h] [rbp+27h]
  __int64 v15; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  RPC_WSTR StringBinding; // [rsp+B8h] [rbp+6Fh] BYREF
  RPC_BINDING_HANDLE Bindinga; // [rsp+C0h] [rbp+77h] BYREF
  char v19; // [rsp+C8h] [rbp+7Fh] BYREF

  *Binding = 0;
  StringBinding = 0;
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"W32TIME_ALT", 0, &StringBinding);
  if ( v2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
      (const char *)(v2 | 0x80010000),
      Options);
  v3 = *Binding;
  if ( *Binding )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v19);
    Bindinga = v3;
    RpcBindingFree(&Bindinga);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v19);
  }
  *Binding = 0;
  v4 = RpcBindingFromStringBindingW(StringBinding, Binding);
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
      (const char *)(v4 | 0x80010000),
      Options);
  *(_QWORD *)SecurityQOS = 5;
  *(_DWORD *)&SecurityQOS[8] = 0;
  *(_QWORD *)&SecurityQOS[12] = 2;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v5 = RpcBindingSetAuthInfoExW(*Binding, 0, 6u, 0xAu, 0, 0, (RPC_SECURITY_QOS *)SecurityQOS);
  if ( v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6C,
      (int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
      (const char *)(v5 | 0x80010000),
      Optionsa);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
    &StringBinding,
    v6,
    v7,
    0);
  return Binding;
}

```

## disassembly

```asm
0x18000fed4  mov     [rsp-8+arg_0], rcx
0x18000fed9  push    rbp
0x18000feda  push    rbx
0x18000fedb  push    rsi
0x18000fedc  push    rdi
0x18000fedd  lea     rbp, [rsp-3Fh]
0x18000fee2  sub     rsp, 88h
0x18000fee9  mov     rbx, rcx
0x18000feec  xor     esi, esi
0x18000feee  mov     [rbp+57h+var_60], esi
0x18000fef1  mov     [rcx], rsi
0x18000fef4  mov     [rbp+57h+var_60], 1
0x18000fefb  mov     [rbp+57h+arg_8], rsi
0x18000feff  lea     rax, [rbp+57h+arg_8]
0x18000ff03  mov     [rsp+0A0h+StringBinding], rax; StringBinding
0x18000ff08  mov     [rsp+0A0h+Options], rsi; int
0x18000ff0d  lea     r9, Endpoint; "W32TIME_ALT"
0x18000ff14  xor     r8d, r8d; NetworkAddr
0x18000ff17  lea     rdx, ProtSeq; "ncalrpc"
0x18000ff1e  xor     ecx, ecx; ObjUuid
0x18000ff20  call    cs:__imp_RpcStringBindingComposeW
0x18000ff26  mov     ecx, eax
0x18000ff28  or      ecx, 80010000h
0x18000ff2e  mov     r9d, esi
0x18000ff31  test    eax, eax
0x18000ff33  cmovnz  r9d, ecx; char *
0x18000ff37  mov     rcx, [rbp+5Fh]; this
0x18000ff3b  jz      short loc_18000FF4D
0x18000ff3d  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x18000ff44  lea     edx, [rsi+51h]; void *
0x18000ff47  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ff4d  mov     rdi, [rbx]
0x18000ff50  test    rdi, rdi
0x18000ff53  jz      short loc_18000FF75
0x18000ff55  lea     rcx, [rbp+57h+arg_18]; this
0x18000ff59  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000ff5e  mov     [rbp+57h+Binding], rdi
0x18000ff62  lea     rcx, [rbp+57h+Binding]; Binding
0x18000ff66  call    cs:__imp_RpcBindingFree
0x18000ff6c  lea     rcx, [rbp+57h+arg_18]; this
0x18000ff70  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ff75  mov     [rbx], rsi
0x18000ff78  mov     rdx, rbx; Binding
0x18000ff7b  mov     rcx, [rbp+57h+arg_8]; StringBinding
0x18000ff7f  call    cs:__imp_RpcBindingFromStringBindingW
0x18000ff85  mov     ecx, eax
0x18000ff87  or      ecx, 80010000h
0x18000ff8d  mov     r9d, esi
0x18000ff90  test    eax, eax
0x18000ff92  cmovnz  r9d, ecx; char *
0x18000ff96  mov     rcx, [rbp+5Fh]; this
0x18000ff9a  jz      short loc_18000FFAE
0x18000ff9c  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x18000ffa3  mov     edx, 54h ; 'T'; void *
0x18000ffa8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ffae  mov     qword ptr [rbp+57h+var_58], 5
0x18000ffb6  mov     dword ptr [rbp+57h+var_58+8], esi
0x18000ffb9  mov     qword ptr [rbp+57h+var_58+0Ch], 2
0x18000ffc1  xor     eax, eax
0x18000ffc3  mov     [rbp+57h+var_44], eax
0x18000ffc6  xorps   xmm0, xmm0
0x18000ffc9  movdqu  [rbp+57h+var_40], xmm0
0x18000ffce  mov     [rbp+57h+var_30], rsi
0x18000ffd2  mov     [rbp+57h+var_28], rsi
0x18000ffd6  lea     rax, [rbp+57h+var_58]
0x18000ffda  mov     [rsp+0A0h+SecurityQOS], rax; SecurityQOS
0x18000ffdf  mov     dword ptr [rsp+0A0h+StringBinding], esi; AuthzSvc
0x18000ffe3  mov     [rsp+0A0h+Options], rsi; int
0x18000ffe8  xor     edx, edx; ServerPrincName
0x18000ffea  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18000ffee  lea     r8d, [rdx+6]; AuthnLevel
0x18000fff2  mov     rcx, [rbx]; Binding
0x18000fff5  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000fffb  mov     ecx, eax
0x18000fffd  or      ecx, 80010000h
0x180010003  mov     r9d, esi
0x180010006  test    eax, eax
0x180010008  cmovnz  r9d, ecx; char *
0x18001000c  mov     rcx, [rbp+5Fh]; this
0x180010010  jz      short loc_180010024
0x180010012  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x180010019  mov     edx, 6Ch ; 'l'; void *
0x18001001e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010024  lea     rcx, [rbp+57h+arg_8]
0x180010028  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001002d  mov     rax, rbx
0x180010030  add     rsp, 88h
0x180010037  pop     rdi
0x180010038  pop     rsi
0x180010039  pop     rbx
0x18001003a  pop     rbp
0x18001003b  retn
```
