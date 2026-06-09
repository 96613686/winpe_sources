# ServiceInterface<void *,HMAPSSTORAGE__ *>::TryOpenService(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMAPSSTORAGE__ * *)

- ea: `0x180010038`
- end: `0x1800102de`
- name: `?TryOpenService@?$ServiceInterface@PEAXPEAUHMAPSSTORAGE__@@@@AEAAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMAPSSTORAGE__@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000fdb0`

## callees

- `0x180002550`
- `0x180006214`
- `0x180008cb4`
- `0x18000b1a8`
- `0x180010038`
- `0x1800102e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010124`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010137`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010137`
- `RPCRT4!RpcBindingBind` at `0x1800101ae`
- `RPCRT4!RpcBindingBind` at `0x1800101ae`
- `RPCRT4!RpcBindingCreateW` at `0x180010186`
- `RPCRT4!RpcBindingCreateW` at `0x180010186`
- `RPCRT4!RpcBindingFree` at `0x1800102b8`
- `RPCRT4!RpcBindingFree` at `0x1800102b8`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180010153`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180010153`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18001012f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800101df`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010234`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18001012f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800101df`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180010234`

## string_xrefs

- `0x180010147`: `MapsBrokerRpc\Service`
- `0x1800100f4`: `MapsBroker`

## pseudocode

```c
__int64 __fastcall ServiceInterface<void *,HMAPSSTORAGE__ *>::TryOpenService(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4)
{
  signed int started; // eax
  signed int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int TransientObjectSecurityDescriptor; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // eax
  RPC_BINDING_HANDLE *v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-C8h] BYREF
  RPC_BINDING_HANDLE v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+7Ch] [rbp-84h]
  int v28; // [rsp+84h] [rbp-7Ch]
  __int128 v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  __int64 v31; // [rsp+A0h] [rbp-60h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+A8h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v22 = a3;
  v24 = 0;
  v23 = 0;
  *a4 = 0;
  Binding = 0;
  *(_QWORD *)v19 = 0;
  *(_QWORD *)&Template.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Template.NetworkAddress, 0, 40);
  v25 = 5;
  v26 = 1;
  v27 = 3;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  *(_QWORD *)&Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v25;
  started = StartServiceW(L"MapsBroker");
  v7 = started;
  if ( started >= 0 )
  {
    *(_QWORD *)v19 = 0;
    TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(9, L"MapsBrokerRpc\\Service", v19);
    if ( TransientObjectSecurityDescriptor < 0 )
    {
      v7 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             v11,
             v12,
             (const char *)(unsigned int)TransientObjectSecurityDescriptor,
             v18);
      goto LABEL_11;
    }
    v31 = *(_QWORD *)v19;
    v13 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
    v7 = v13 != 0 ? v13 | 0x80010000 : 0;
    if ( v7 >= 0 )
    {
      v14 = RpcBindingBind(0, Binding, *(RPC_IF_HANDLE *)a1);
      v7 = v14 != 0 ? v14 | 0x80010000 : 0;
      if ( v7 >= 0 )
      {
        if ( *(_QWORD *)v19 )
          FreeTransientObjectSecurityDescriptor(*(_QWORD *)v19);
        goto LABEL_20;
      }
      v9 = 163;
    }
    else
    {
      v9 = 157;
    }
    v8 = (unsigned int)v7;
  }
  else
  {
    v8 = (unsigned int)started;
    v9 = 140;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
    (const char *)v8);
LABEL_11:
  if ( *(_QWORD *)v19 )
    FreeTransientObjectSecurityDescriptor(*(_QWORD *)v19);
  if ( v7 == -2147024891 )
  {
    v7 = -2080374777;
    goto LABEL_16;
  }
  if ( v7 >= 0 )
  {
LABEL_20:
    *(_QWORD *)v19 = &v23;
    v21 = Binding;
    v16 = wil::invoke_rpc_nothrow<long (*&)(unsigned short const *,enum __MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),unsigned short const * &,enum __MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(
            (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 8),
            &v24,
            &v22,
            &v21,
            v19);
    v7 = v16;
    *a4 = v23;
    if ( v16 >= 0 )
    {
      if ( !Binding )
        return (unsigned int)v7;
      v21 = Binding;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
        (const char *)(unsigned int)v16);
      if ( !Binding )
        return (unsigned int)v7;
      v21 = Binding;
    }
    v15 = &v21;
    goto LABEL_26;
  }
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB4,
    (int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
    (const char *)(unsigned int)v7);
  if ( Binding )
  {
    *(_QWORD *)v19 = Binding;
    v15 = (RPC_BINDING_HANDLE *)v19;
LABEL_26:
    RpcBindingFree(v15);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010038  push    rbp
0x18001003a  push    rbx
0x18001003b  push    rsi
0x18001003c  push    rdi
0x18001003d  push    r12
0x18001003f  push    r14
0x180010041  push    r15
0x180010043  lea     rbp, [rsp-10h]
0x180010048  sub     rsp, 110h
0x18001004f  mov     rax, cs:__security_cookie
0x180010056  xor     rax, rsp
0x180010059  mov     [rbp+40h+var_38], rax
0x18001005d  mov     r14, r9
0x180010060  mov     rsi, rcx
0x180010063  mov     [rsp+140h+var_F8], r8d
0x180010068  xor     r15d, r15d
0x18001006b  mov     [rsp+140h+var_E0], r15
0x180010070  mov     [rsp+140h+var_F0], r15
0x180010075  mov     [r9], r15
0x180010078  mov     [rsp+140h+Binding], r15
0x18001007d  mov     qword ptr [rsp+140h+var_110], r15
0x180010082  lea     edx, [r15+1]
0x180010086  mov     qword ptr [rbp+40h+Template.Version], rdx
0x18001008a  mov     qword ptr [rbp+40h+Template.ProtocolSequence], 3
0x180010092  xorps   xmm0, xmm0
0x180010095  movdqu  xmmword ptr [rbp+40h+Template.NetworkAddress], xmm0
0x18001009a  mov     qword ptr [rbp+40h+Template.u1], r15
0x18001009e  mov     [rbp+40h+Template.ObjectUuid.Data1], r15d
0x1800100a2  xor     eax, eax
0x1800100a4  mov     qword ptr [rbp+40h+Template.ObjectUuid.Data2], rax
0x1800100a8  mov     dword ptr [rbp+40h+Template.ObjectUuid.Data4+4], eax
0x1800100ab  mov     [rsp+140h+var_D0], 5
0x1800100b4  mov     [rsp+140h+var_C8], edx
0x1800100b8  mov     [rsp+140h+var_C4], 3
0x1800100c1  mov     [rbp+40h+var_BC], eax
0x1800100c4  movdqu  [rbp+40h+var_B8], xmm0
0x1800100c9  mov     [rbp+40h+var_A8], r15
0x1800100cd  mov     [rbp+40h+var_A0], r15
0x1800100d1  mov     qword ptr [rbp+40h+Security.Version], rdx
0x1800100d5  mov     [rbp+40h+Security.ServerPrincName], r15
0x1800100d9  mov     [rbp+40h+Security.AuthnLevel], 6
0x1800100e0  mov     [rbp+40h+Security.AuthnSvc], 0Ah
0x1800100e7  mov     [rbp+40h+Security.AuthIdentity], r15
0x1800100eb  lea     rax, [rsp+140h+var_D0]
0x1800100f0  mov     [rbp+40h+Security.SecurityQos], rax
0x1800100f4  lea     rcx, aMapsbroker_2; "MapsBroker"
0x1800100fb  call    ?StartServiceW@@YAJPEBG@Z; StartServiceW(ushort const *)
0x180010100  mov     ebx, eax
0x180010102  lea     r12, aOnecoreuapWind; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180010109  test    eax, eax
0x18001010b  jns     short loc_18001011A
0x18001010d  mov     r9d, eax
0x180010110  mov     edx, 8Ch
0x180010115  jmp     loc_1800101C8
0x18001011a  mov     rdi, qword ptr [rsp+140h+var_110]
0x18001011f  test    rdi, rdi
0x180010122  jz      short loc_18001013D
0x180010124  call    cs:__imp_GetLastError
0x18001012a  mov     ebx, eax
0x18001012c  mov     rcx, rdi
0x18001012f  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180010135  mov     ecx, ebx; dwErrCode
0x180010137  call    cs:__imp_SetLastError
0x18001013d  mov     qword ptr [rsp+140h+var_110], r15
0x180010142  lea     r8, [rsp+140h+var_110]
0x180010147  lea     rdx, aMapsbrokerrpcS_2; "MapsBrokerRpc\\Service"
0x18001014e  mov     ecx, 9
0x180010153  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180010159  test    eax, eax
0x18001015b  jns     short loc_18001016D
0x18001015d  mov     rcx, [rbp+48h]; this
0x180010161  mov     r9d, eax; char *
0x180010164  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180010169  mov     ebx, eax
0x18001016b  jmp     short loc_1800101D5
0x18001016d  mov     rax, qword ptr [rsp+140h+var_110]
0x180010172  mov     [rbp+40h+var_A0], rax
0x180010176  lea     r9, [rsp+140h+Binding]; Binding
0x18001017b  xor     r8d, r8d; Options
0x18001017e  lea     rdx, [rbp+40h+Security]; Security
0x180010182  lea     rcx, [rbp+40h+Template]; Template
0x180010186  call    cs:__imp_RpcBindingCreateW
0x18001018c  mov     ecx, eax
0x18001018e  mov     edi, 80010000h
0x180010193  or      ecx, edi
0x180010195  neg     eax
0x180010197  sbb     ebx, ebx
0x180010199  and     ebx, ecx
0x18001019b  jge     short loc_1800101A4
0x18001019d  mov     edx, 9Dh
0x1800101a2  jmp     short loc_1800101C5
0x1800101a4  mov     r8, [rsi]; IfSpec
0x1800101a7  mov     rdx, [rsp+140h+Binding]; Binding
0x1800101ac  xor     ecx, ecx; pAsync
0x1800101ae  call    cs:__imp_RpcBindingBind
0x1800101b4  mov     ecx, eax
0x1800101b6  or      ecx, edi
0x1800101b8  neg     eax
0x1800101ba  sbb     ebx, ebx
0x1800101bc  and     ebx, ecx
0x1800101be  jge     short loc_18001022A
0x1800101c0  mov     edx, 0A3h; void *
0x1800101c5  mov     r9d, ebx; char *
0x1800101c8  mov     r8, r12; unsigned int
0x1800101cb  mov     rcx, [rbp+48h]; this
0x1800101cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800101d4  nop
0x1800101d5  mov     rcx, qword ptr [rsp+140h+var_110]
0x1800101da  test    rcx, rcx
0x1800101dd  jz      short loc_1800101E5
0x1800101df  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800101e5  cmp     ebx, 80070005h
0x1800101eb  jnz     short loc_1800101F4
0x1800101ed  mov     ebx, 84000007h
0x1800101f2  jmp     short loc_1800101F8
0x1800101f4  test    ebx, ebx
0x1800101f6  jns     short loc_18001023A
0x1800101f8  mov     rcx, [rbp+48h]; this
0x1800101fc  mov     r9d, ebx; char *
0x1800101ff  mov     r8, r12; unsigned int
0x180010202  mov     edx, 0B4h; void *
0x180010207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001020c  nop
0x18001020d  mov     rcx, [rsp+140h+Binding]
0x180010212  test    rcx, rcx
0x180010215  jz      loc_1800102BE
0x18001021b  mov     qword ptr [rsp+140h+var_110], rcx
0x180010220  lea     rcx, [rsp+140h+var_110]
0x180010225  jmp     loc_1800102B8
0x18001022a  mov     rcx, qword ptr [rsp+140h+var_110]
0x18001022f  test    rcx, rcx
0x180010232  jz      short loc_18001023A
0x180010234  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18001023a  lea     rax, [rsp+140h+var_F0]
0x18001023f  mov     qword ptr [rsp+140h+var_110], rax
0x180010244  mov     rax, [rsp+140h+Binding]
0x180010249  mov     [rsp+140h+var_100], rax
0x18001024e  lea     rcx, [rsi+8]
0x180010252  lea     rax, [rsp+140h+var_110]
0x180010257  mov     qword ptr [rsp+140h+var_120], rax; int
0x18001025c  lea     r9, [rsp+140h+var_100]
0x180010261  lea     r8, [rsp+140h+var_F8]
0x180010266  lea     rdx, [rsp+140h+var_E0]
0x18001026b  call    ??$invoke_rpc_nothrow@AEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@PEAXPEAPEAX@wil@@YAJAEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@$$QEAPEAX$$QEAPEAPEAX@Z; wil::invoke_rpc_nothrow<long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void * &&,void * * &&)
0x180010270  mov     ebx, eax
0x180010272  mov     rcx, [rsp+140h+var_F0]
0x180010277  mov     [r14], rcx
0x18001027a  test    eax, eax
0x18001027c  jns     short loc_1800102A4
0x18001027e  mov     rcx, [rbp+48h]; this
0x180010282  mov     r9d, eax; char *
0x180010285  mov     r8, r12; unsigned int
0x180010288  mov     edx, 0B9h; void *
0x18001028d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010292  nop
0x180010293  mov     rcx, [rsp+140h+Binding]
0x180010298  test    rcx, rcx
0x18001029b  jz      short loc_1800102BE
0x18001029d  mov     [rsp+140h+var_100], rcx
0x1800102a2  jmp     short loc_1800102B3
0x1800102a4  mov     rax, [rsp+140h+Binding]
0x1800102a9  test    rax, rax
0x1800102ac  jz      short loc_1800102BE
0x1800102ae  mov     [rsp+140h+var_100], rax
0x1800102b3  lea     rcx, [rsp+140h+var_100]; Binding
0x1800102b8  call    cs:__imp_RpcBindingFree
0x1800102be  mov     eax, ebx
0x1800102c0  mov     rcx, [rbp+40h+var_38]
0x1800102c4  xor     rcx, rsp; StackCookie
0x1800102c7  call    __security_check_cookie
0x1800102cc  add     rsp, 110h
0x1800102d3  pop     r15
0x1800102d5  pop     r14
0x1800102d7  pop     r12
0x1800102d9  pop     rdi
0x1800102da  pop     rsi
0x1800102db  pop     rbx
0x1800102dc  pop     rbp
0x1800102dd  retn
```
