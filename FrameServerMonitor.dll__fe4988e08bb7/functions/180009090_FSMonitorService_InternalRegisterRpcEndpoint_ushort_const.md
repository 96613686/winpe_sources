# FSMonitorService::InternalRegisterRpcEndpoint(ushort const *)

- ea: `0x180009090`
- end: `0x180009505`
- name: `?InternalRegisterRpcEndpoint@FSMonitorService@@IEAAJPEBG@Z`
- size: `1141`
- prototype: `__int64 __fastcall(FSMonitorService *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c100`

## callees

- `0x180002f90`
- `0x180003274`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006ae8`
- `0x180007040`
- `0x180007068`
- `0x180009090`
- `0x18000b388`
- `0x18000c684`
- `0x18000d294`
- `0x18000d2f0`
- `0x18000d4f8`
- `0x18000d62c`
- `0x180031998`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000946f`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000946f`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180009170`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180009170`
- `RPCRT4!RpcServerUseProtseqW` at `0x180009205`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000921d`
- `RPCRT4!RpcServerUseProtseqW` at `0x180009205`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000921d`
- `RPCRT4!RpcStringFreeW` at `0x1800092a3`
- `RPCRT4!RpcStringFreeW` at `0x1800092eb`
- `RPCRT4!RpcStringFreeW` at `0x1800092a3`
- `RPCRT4!RpcStringFreeW` at `0x1800092eb`
- `RPCRT4!RpcEpRegisterW` at `0x180009418`
- `RPCRT4!RpcEpRegisterW` at `0x18000942f`
- `RPCRT4!RpcEpRegisterW` at `0x180009418`
- `RPCRT4!RpcEpRegisterW` at `0x18000942f`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800093a2`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800093d5`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800093a2`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800093d5`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180009338`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18000934f`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180009338`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18000934f`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1800092c7`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180009309`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1800092c7`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180009309`
- `RPCRT4!RpcServerInqBindings` at `0x18000924e`
- `RPCRT4!RpcServerInqBindings` at `0x180009267`
- `RPCRT4!RpcServerInqBindings` at `0x18000924e`
- `RPCRT4!RpcServerInqBindings` at `0x180009267`

## pseudocode

```c
__int64 __fastcall FSMonitorService::InternalRegisterRpcEndpoint(FSMonitorService *this, const unsigned __int16 *a2)
{
  int v3; // ecx
  signed int v4; // ebx
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // ecx
  __int64 v7; // rdx
  unsigned __int16 *v8; // rbx
  unsigned __int16 *v9; // rbx
  RPC_WSTR v10; // rcx
  _BYTE v12[8]; // [rsp+40h] [rbp-30h] BYREF
  void **v13; // [rsp+48h] [rbp-28h] BYREF
  void *SecurityDescriptor[2]; // [rsp+50h] [rbp-20h]
  __int64 v15; // [rsp+60h] [rbp-10h]
  RPC_WSTR PrincName; // [rsp+A8h] [rbp+38h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+B0h] [rbp+40h] BYREF
  RPC_WSTR String; // [rsp+B8h] [rbp+48h] BYREF

  v13 = &AutoSecurityAttributes::`vftable';
  v15 = 0;
  BindingVector = 0;
  PrincName = 0;
  *(_OWORD *)SecurityDescriptor = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      150,
      (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      v3,
      (__int64)L"D:(A;;GRGWGX;;;IU)(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;S-1-15-3-3845273463-13"
                "31427702-1186551195-1148109977)");
  v4 = AutoSecurityAttributes::Set(
         (AutoSecurityAttributes *)&v13,
         L"D:(A;;GRGWGX;;;IU)(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;S-1-15-3-3845273463-13314277"
          "02-1186551195-1148109977)");
  if ( v4 >= 0 )
  {
    if ( !(unsigned __int8)IsContainerFlagSet() )
      goto LABEL_15;
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 152, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this);
    v5 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_hvsocket", 0xAu, (RPC_WSTR)L"A04F35B6-3FB9-4AD0-951C-EDBB8D431FFB", 0);
    v6 = v5;
    if ( !v5 )
      goto LABEL_15;
    if ( v5 == 1740 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 153, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this);
      v6 = 0;
    }
    v4 = v6 != 0 ? v6 | 0x80010000 : 0;
    if ( v4 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 154;
LABEL_36:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v4);
      }
    }
    else
    {
LABEL_15:
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 155, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this);
      if ( RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor[1]) )
      {
        v4 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor[1]) | 0x80010000;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v7 = 156;
          goto LABEL_36;
        }
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(
          &BindingVector,
          0);
        if ( RpcServerInqBindings(&BindingVector) )
        {
          wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(
            &BindingVector,
            0);
          v4 = RpcServerInqBindings(&BindingVector) | 0x80010000;
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v7 = 157;
            goto LABEL_36;
          }
        }
        else
        {
          v8 = PrincName;
          if ( PrincName )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v12);
            String = v8;
            RpcStringFreeW(&String);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v12);
          }
          PrincName = 0;
          if ( RpcServerInqDefaultPrincNameW(9u, &PrincName) )
          {
            v9 = PrincName;
            if ( PrincName )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v12);
              String = v9;
              RpcStringFreeW(&String);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v12);
            }
            PrincName = 0;
            v4 = RpcServerInqDefaultPrincNameW(9u, &PrincName) | 0x80010000;
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v7 = 158;
              goto LABEL_36;
            }
          }
          else if ( RpcServerRegisterAuthInfoW(PrincName, 9u, 0, 0) )
          {
            v4 = RpcServerRegisterAuthInfoW(PrincName, 9u, 0, 0) | 0x80010000;
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v7 = 159;
              goto LABEL_36;
            }
          }
          else if ( (unsigned int)RpcServerRegisterIf3(qword_1800500A0, 0, 0, 9, 1234, -1, 0, SecurityDescriptor[1]) )
          {
            v4 = RpcServerRegisterIf3(qword_1800500A0, 0, 0, 9, 1234, -1, 0, SecurityDescriptor[1]) | 0x80010000;
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v7 = 160;
              goto LABEL_36;
            }
          }
          else if ( RpcEpRegisterW(qword_1800500A0, BindingVector, 0, 0) )
          {
            v4 = RpcEpRegisterW(qword_1800500A0, BindingVector, 0, 0) | 0x80010000;
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                161,
                &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
                this,
                v4);
            RpcServerUnregisterIfEx(qword_1800500A0, 0, 1);
          }
          else
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>>::swap(
              (char *)this + 96,
              &BindingVector);
            v4 = 0;
            if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
            {
              v10 = L"nullptr";
              if ( PrincName )
                v10 = PrincName;
              WPP_SF_qDS(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                162,
                (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
                (_DWORD)this,
                0,
                (__int64)v10);
            }
          }
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&PrincName);
  wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(&BindingVector);
  v13 = &AutoSecurityAttributes::`vftable';
  AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009090  mov     [rsp-28h+arg_0], rbx
0x180009095  mov     [rsp-28h+PrincName], rdx
0x18000909a  push    rbp
0x18000909b  push    rdi
0x18000909c  push    r13
0x18000909e  push    r14
0x1800090a0  push    r15
0x1800090a2  mov     rbp, rsp
0x1800090a5  sub     rsp, 70h
0x1800090a9  lea     rax, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x1800090b0  xorps   xmm0, xmm0
0x1800090b3  mov     [rbp+var_28], rax
0x1800090b7  mov     rdi, rcx
0x1800090ba  xor     eax, eax
0x1800090bc  mov     [rbp+var_10], rax
0x1800090c0  mov     [rbp+BindingVector], rax
0x1800090c4  mov     [rbp+PrincName], rax
0x1800090c8  movups  xmmword ptr [rbp+SecurityDescriptor], xmm0
0x1800090cc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800090d1  lea     rbx, aDAGrgwgxIuAGrg; "D:(A;;GRGWGX;;;IU)(A;;GRGWGX;;;WD)(A;;G"...
0x1800090d8  lea     r14, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800090df  cmp     al, 8
0x1800090e1  jb      short loc_180009106
0x1800090e3  mov     r9, rcx
0x1800090e6  mov     [rsp+70h+var_50], rbx
0x1800090eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090f2  mov     edx, 96h
0x1800090f7  mov     r8, r14
0x1800090fa  mov     rcx, [rcx+0D8h]
0x180009101  call    WPP_SF_qS
0x180009106  mov     rdx, rbx; StringSecurityDescriptor
0x180009109  lea     rcx, [rbp+var_28]; this
0x18000910d  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x180009112  mov     ebx, eax
0x180009114  test    eax, eax
0x180009116  js      loc_1800094C8
0x18000911c  call    ?IsContainerFlagSet@@YA_NW4FSRequestorType@@@Z; IsContainerFlagSet(FSRequestorType)
0x180009121  mov     r13d, 80010000h
0x180009127  mov     r15d, 0Ah
0x18000912d  test    al, al
0x18000912f  jz      loc_1800091D0
0x180009135  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000913a  cmp     al, 8
0x18000913c  jb      short loc_18000915C
0x18000913e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009145  mov     edx, 98h
0x18000914a  mov     r9, rdi
0x18000914d  mov     r8, r14
0x180009150  mov     rcx, [rcx+0D8h]
0x180009157  call    WPP_SF_q
0x18000915c  xor     r9d, r9d; SecurityDescriptor
0x18000915f  lea     r8, Endpoint; "A04F35B6-3FB9-4AD0-951C-EDBB8D431FFB"
0x180009166  mov     edx, r15d; MaxCalls
0x180009169  lea     rcx, Protseq; "ncacn_hvsocket"
0x180009170  call    cs:__imp_RpcServerUseProtseqEpW
0x180009176  mov     ecx, eax
0x180009178  test    eax, eax
0x18000917a  jz      short loc_1800091D0
0x18000917c  cmp     eax, 6CCh
0x180009181  jnz     short loc_1800091AC
0x180009183  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180009188  cmp     al, 8
0x18000918a  jb      short loc_1800091AA
0x18000918c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009193  mov     edx, 99h
0x180009198  mov     r9, rdi
0x18000919b  mov     r8, r14
0x18000919e  mov     rcx, [rcx+0D8h]
0x1800091a5  call    WPP_SF_q
0x1800091aa  xor     ecx, ecx
0x1800091ac  mov     eax, ecx
0x1800091ae  or      eax, r13d
0x1800091b1  neg     ecx
0x1800091b3  sbb     ebx, ebx
0x1800091b5  and     ebx, eax
0x1800091b7  jge     short loc_1800091D0
0x1800091b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800091be  cmp     al, 1
0x1800091c0  jb      loc_1800094C8
0x1800091c6  mov     edx, 9Ah
0x1800091cb  jmp     loc_1800093F2
0x1800091d0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800091d5  cmp     al, 8
0x1800091d7  jb      short loc_1800091F7
0x1800091d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091e0  mov     edx, 9Bh
0x1800091e5  mov     r9, rdi
0x1800091e8  mov     r8, r14
0x1800091eb  mov     rcx, [rcx+0D8h]
0x1800091f2  call    WPP_SF_q
0x1800091f7  mov     r8, [rbp+SecurityDescriptor+8]; SecurityDescriptor
0x1800091fb  lea     rcx, aNcalrpc; "ncalrpc"
0x180009202  mov     edx, r15d; MaxCalls
0x180009205  call    cs:__imp_RpcServerUseProtseqW
0x18000920b  test    eax, eax
0x18000920d  jz      short loc_18000923F
0x18000920f  mov     r8, [rbp+SecurityDescriptor+8]; SecurityDescriptor
0x180009213  lea     rcx, aNcalrpc; "ncalrpc"
0x18000921a  mov     edx, r15d; MaxCalls
0x18000921d  call    cs:__imp_RpcServerUseProtseqW
0x180009223  mov     ebx, eax
0x180009225  or      ebx, r13d
0x180009228  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000922d  cmp     al, 1
0x18000922f  jb      loc_1800094C8
0x180009235  mov     edx, 9Ch
0x18000923a  jmp     loc_1800093F2
0x18000923f  xor     edx, edx
0x180009241  lea     rcx, [rbp+BindingVector]
0x180009245  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RPC_BINDING_VECTOR@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(_RPC_BINDING_VECTOR *)
0x18000924a  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000924e  call    cs:__imp_RpcServerInqBindings
0x180009254  test    eax, eax
0x180009256  jz      short loc_180009289
0x180009258  xor     edx, edx
0x18000925a  lea     rcx, [rbp+BindingVector]
0x18000925e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RPC_BINDING_VECTOR@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(_RPC_BINDING_VECTOR *)
0x180009263  lea     rcx, [rbp+BindingVector]; BindingVector
0x180009267  call    cs:__imp_RpcServerInqBindings
0x18000926d  mov     ebx, eax
0x18000926f  or      ebx, r13d
0x180009272  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009277  cmp     al, 1
0x180009279  jb      loc_1800094C8
0x18000927f  mov     edx, 9Dh
0x180009284  jmp     loc_1800093F2
0x180009289  mov     rbx, [rbp+PrincName]
0x18000928d  test    rbx, rbx
0x180009290  jz      short loc_1800092B2
0x180009292  lea     rcx, [rbp+var_30]; this
0x180009296  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000929b  lea     rcx, [rbp+String]; String
0x18000929f  mov     [rbp+String], rbx
0x1800092a3  call    cs:__imp_RpcStringFreeW
0x1800092a9  lea     rcx, [rbp+var_30]; this
0x1800092ad  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800092b2  mov     r15d, 9
0x1800092b8  mov     [rbp+PrincName], 0
0x1800092c0  mov     ecx, r15d; AuthnSvc
0x1800092c3  lea     rdx, [rbp+PrincName]; PrincName
0x1800092c7  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x1800092cd  test    eax, eax
0x1800092cf  jz      short loc_18000932B
0x1800092d1  mov     rbx, [rbp+PrincName]
0x1800092d5  test    rbx, rbx
0x1800092d8  jz      short loc_1800092FA
0x1800092da  lea     rcx, [rbp+var_30]; this
0x1800092de  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800092e3  lea     rcx, [rbp+String]; String
0x1800092e7  mov     [rbp+String], rbx
0x1800092eb  call    cs:__imp_RpcStringFreeW
0x1800092f1  lea     rcx, [rbp+var_30]; this
0x1800092f5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800092fa  lea     rdx, [rbp+PrincName]; PrincName
0x1800092fe  mov     [rbp+PrincName], 0
0x180009306  mov     ecx, r15d; AuthnSvc
0x180009309  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18000930f  mov     ebx, eax
0x180009311  or      ebx, r13d
0x180009314  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180009319  cmp     al, 1
0x18000931b  jb      loc_1800094C8
0x180009321  mov     edx, 9Eh
0x180009326  jmp     loc_1800093F2
0x18000932b  mov     rcx, [rbp+PrincName]; ServerPrincName
0x18000932f  xor     r9d, r9d; Arg
0x180009332  xor     r8d, r8d; GetKeyFn
0x180009335  mov     edx, r15d; AuthnSvc
0x180009338  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18000933e  xor     r8d, r8d; GetKeyFn
0x180009341  test    eax, eax
0x180009343  jz      short loc_180009371
0x180009345  mov     rcx, [rbp+PrincName]; ServerPrincName
0x180009349  xor     r9d, r9d; Arg
0x18000934c  mov     edx, r15d; AuthnSvc
0x18000934f  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180009355  mov     ebx, eax
0x180009357  or      ebx, r13d
0x18000935a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000935f  cmp     al, 1
0x180009361  jb      loc_1800094C8
0x180009367  mov     edx, 9Fh
0x18000936c  jmp     loc_1800093F2
0x180009371  mov     rax, [rbp+SecurityDescriptor+8]
0x180009375  lea     rbx, qword_1800500A0
0x18000937c  mov     [rsp+70h+var_38], rax
0x180009381  mov     r9d, r15d
0x180009384  mov     [rsp+70h+var_40], 0
0x18000938d  xor     edx, edx
0x18000938f  mov     dword ptr [rsp+70h+var_48], 0FFFFFFFFh
0x180009397  mov     rcx, rbx
0x18000939a  mov     dword ptr [rsp+70h+var_50], 4D2h
0x1800093a2  call    cs:__imp_RpcServerRegisterIf3
0x1800093a8  xor     r8d, r8d; UuidVector
0x1800093ab  mov     rcx, rbx; IfSpec
0x1800093ae  test    eax, eax
0x1800093b0  jz      short loc_180009411
0x1800093b2  mov     rax, [rbp+SecurityDescriptor+8]
0x1800093b6  mov     r9d, r15d
0x1800093b9  mov     [rsp+70h+var_38], rax
0x1800093be  xor     edx, edx
0x1800093c0  mov     [rsp+70h+var_40], r8
0x1800093c5  mov     dword ptr [rsp+70h+var_48], 0FFFFFFFFh
0x1800093cd  mov     dword ptr [rsp+70h+var_50], 4D2h
0x1800093d5  call    cs:__imp_RpcServerRegisterIf3
0x1800093db  mov     ebx, eax
0x1800093dd  or      ebx, r13d
0x1800093e0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800093e5  cmp     al, 1
0x1800093e7  jb      loc_1800094C8
0x1800093ed  mov     edx, 0A0h
0x1800093f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093f9  mov     r9, rdi
0x1800093fc  mov     r8, r14
0x1800093ff  mov     dword ptr [rsp+70h+var_50], ebx
0x180009403  mov     rcx, [rcx+10h]
0x180009407  call    WPP_SF_qD
0x18000940c  jmp     loc_1800094C8
0x180009411  mov     rdx, [rbp+BindingVector]; BindingVector
0x180009415  xor     r9d, r9d; Annotation
0x180009418  call    cs:__imp_RpcEpRegisterW
0x18000941e  test    eax, eax
0x180009420  jz      short loc_180009477
0x180009422  mov     rdx, [rbp+BindingVector]; BindingVector
0x180009426  xor     r9d, r9d; Annotation
0x180009429  xor     r8d, r8d; UuidVector
0x18000942c  mov     rcx, rbx; IfSpec
0x18000942f  call    cs:__imp_RpcEpRegisterW
0x180009435  mov     ebx, eax
0x180009437  or      ebx, r13d
0x18000943a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000943f  cmp     al, 1
0x180009441  jb      short loc_180009462
0x180009443  mov     rcx, cs:WPP_GLOBAL_Control
0x18000944a  mov     edx, 0A1h
0x18000944f  mov     r9, rdi
0x180009452  mov     dword ptr [rsp+70h+var_50], ebx
0x180009456  mov     r8, r14
0x180009459  mov     rcx, [rcx+10h]
0x18000945d  call    WPP_SF_qD
0x180009462  xor     edx, edx; MgrTypeUuid
0x180009464  lea     rcx, qword_1800500A0; IfSpec
0x18000946b  lea     r8d, [rdx+1]; RundownContextHandles
0x18000946f  call    cs:__imp_RpcServerUnregisterIfEx
0x180009475  jmp     short loc_1800094C8
0x180009477  lea     rcx, [rdi+60h]
0x18000947b  lea     rdx, [rbp+BindingVector]
0x18000947f  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>> &)
0x180009484  xor     ebx, ebx
0x180009486  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000948b  cmp     al, 8
0x18000948d  jb      short loc_1800094C8
0x18000948f  mov     rax, [rbp+PrincName]
0x180009493  lea     rcx, aNullptr_0; "nullptr"
0x18000949a  test    rax, rax
0x18000949d  mov     edx, 0A2h
0x1800094a2  mov     r9, rdi
0x1800094a5  mov     r8, r14
0x1800094a8  cmovnz  rcx, rax
0x1800094ac  mov     [rsp+70h+var_48], rcx
0x1800094b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094b8  mov     dword ptr [rsp+70h+var_50], ebx
0x1800094bc  mov     rcx, [rcx+0D8h]
0x1800094c3  call    WPP_SF_qDS
0x1800094c8  lea     rcx, [rbp+PrincName]
0x1800094cc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800094d1  lea     rcx, [rbp+BindingVector]
0x1800094d5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(void)
0x1800094da  lea     rax, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x1800094e1  lea     rcx, [rbp+var_28]; this
0x1800094e5  mov     [rbp+var_28], rax
0x1800094e9  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x1800094ee  mov     eax, ebx
0x1800094f0  mov     rbx, [rsp+70h+arg_0]
0x1800094f8  add     rsp, 70h
0x1800094fc  pop     r15
0x1800094fe  pop     r14
0x180009500  pop     r13
0x180009502  pop     rdi
0x180009503  pop     rbp
0x180009504  retn
```
