# HandlerManager::StartHandlers(ulong,void (*)(void *,void *,ulong))

- ea: `0x18001de28`
- end: `0x18001e11f`
- name: `?StartHandlers@HandlerManager@@QEAAJKP6AXPEAX0K@Z@Z`
- size: `759`
- prototype: `__int64 __fastcall(__int64 ***this, unsigned int, void (*)(void *, void *, unsigned int))`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022b70`

## callees

- `0x180018194`
- `0x1800193b0`
- `0x180019c94`
- `0x18001de28`
- `0x180037410`
- `0x180037f14`
- `0x1800386b0`
- `0x18005e2c8`
- `0x18005e3b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001df1a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001df1a`

## pseudocode

```c
__int64 __fastcall HandlerManager::StartHandlers(
        __int64 ***this,
        unsigned int a2,
        void (*a3)(void *, void *, unsigned int))
{
  unsigned int v5; // ebx
  __int64 *v6; // rax
  __int64 **v7; // rdx
  __int64 *i; // rcx
  __int64 *j; // rdx
  DWORD LastError; // eax
  signed int v12; // ebx
  __int64 *v13; // rbx
  __int64 **v14; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  int v17; // eax
  __int16 *v18; // rdx
  unsigned int v19; // [rsp+28h] [rbp-49h]
  void (*v20)(void *, void *, unsigned int); // [rsp+38h] [rbp-39h]
  void *v21; // [rsp+40h] [rbp-31h]
  HandlerManager *v22; // [rsp+48h] [rbp-29h] BYREF
  __int16 v23; // [rsp+50h] [rbp-21h]
  void **v24; // [rsp+58h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-11h] BYREF
  struct RPC_INTERFACE_TEMPLATEW *v26[2]; // [rsp+68h] [rbp-9h] BYREF
  __int64 v27; // [rsp+78h] [rbp+7h]
  int v28; // [rsp+80h] [rbp+Fh] BYREF
  const unsigned __int16 *v29; // [rsp+88h] [rbp+17h]
  __int64 v30; // [rsp+90h] [rbp+1Fh]
  PSECURITY_DESCRIPTOR v31; // [rsp+98h] [rbp+27h]
  int v32; // [rsp+A0h] [rbp+2Fh]
  void (*v33)(void *, void *, unsigned int); // [rsp+E8h] [rbp+77h] BYREF

  v33 = a3;
  v5 = 0;
  v6 = **this;
  while ( !*((_BYTE *)v6 + 25) )
  {
    v5 += *(_DWORD *)(v6[5] + 120);
    v7 = (__int64 **)v6[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  if ( v5 )
  {
    v24 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
    SecurityDescriptor = 0;
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v24);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:LSD:(A;;GR;;;WD)(A;;GR;;;AC)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v33) = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)&byte_1800A8CD7,
          0,
          0,
          (__int64)&v33);
      }
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
LABEL_42:
      v24 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v24);
      return (unsigned int)v12;
    }
    *(_OWORD *)v26 = 0;
    v27 = 0;
    std::vector<RPC_INTERFACE_TEMPLATEW>::reserve(v26, v5);
    v13 = **this;
    while ( !*((_BYTE *)v13 + 25) )
    {
      std::vector<RPC_INTERFACE_TEMPLATEW>::_Insert_counted_range<RPC_INTERFACE_TEMPLATEW *>(
        v26,
        v26[1],
        *(_QWORD *)(v13[5] + 112),
        *(unsigned int *)(v13[5] + 120));
      v14 = (__int64 **)v13[2];
      if ( *((_BYTE *)v14 + 25) )
      {
        for ( k = (__int64 *)v13[1]; !*((_BYTE *)k + 25) && v13 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v13 = k;
        v13 = k;
      }
      else
      {
        v13 = (__int64 *)v13[2];
        for ( m = *v14; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v13 = m;
      }
    }
    v28 = 0;
    v29 = L"ncalrpc";
    v30 = 0;
    v31 = SecurityDescriptor;
    v32 = 10;
    v22 = (HandlerManager *)this;
    v23 = 258;
    v17 = NgcUtils::RpcServer::Create(
            (NgcUtils::RpcServer *)(this + 2),
            v26[0],
            -858993459 * (unsigned int)((v26[1] - v26[0]) >> 4),
            (struct RPC_ENDPOINT_TEMPLATEW *)&v28,
            v19,
            a2,
            v20,
            v21);
    v12 = v17;
    if ( v17 < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 <= 2 )
        goto LABEL_40;
      v18 = (__int16 *)qword_1800A8CB0;
      goto LABEL_35;
    }
    v17 = NgcUtils::RpcServer::Start((NgcUtils::RpcServer *)(this + 2));
    v12 = v17;
    if ( v17 >= 0 )
    {
      HIBYTE(v23) = 0;
    }
    else if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v18 = word_1800A8C8A;
LABEL_35:
      LODWORD(v33) = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (_DWORD)v18,
        0,
        0,
        (__int64)&v33);
    }
LABEL_40:
    wil::details::ScopeExitFnGuard__lambda_f74cc1db97316ec4b3f3112de3f331cb___::operator()(&v22);
    if ( v26[0] )
    {
      std::_Deallocate<16>(v26[0], 16 * ((signed __int64)(v27 - (unsigned __int64)v26[0]) >> 4));
      *(_OWORD *)v26 = 0;
      v27 = 0;
    }
    goto LABEL_42;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    LODWORD(v33) = -2147467260;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (unsigned int)&word_1800A8D16,
      0,
      0,
      (__int64)&v33);
  }
  return 2147500036LL;
}

```

## disassembly

```asm
0x18001de28  mov     rax, rsp
0x18001de2b  mov     [rax+8], rbx
0x18001de2f  mov     [rax+10h], rsi
0x18001de33  mov     [rax+18h], r8
0x18001de37  push    rbp
0x18001de38  push    rdi
0x18001de39  push    r12
0x18001de3b  push    r14
0x18001de3d  push    r15
0x18001de3f  lea     rbp, [rax-5Fh]
0x18001de43  sub     rsp, 0A0h
0x18001de4a  mov     esi, edx
0x18001de4c  mov     rdi, rcx
0x18001de4f  xor     r14d, r14d
0x18001de52  mov     ebx, r14d
0x18001de55  mov     rax, [rcx]
0x18001de58  mov     rax, [rax]
0x18001de5b  cmp     [rax+19h], r14b
0x18001de5f  jnz     short loc_18001DEAE
0x18001de61  mov     r8, [rax+28h]
0x18001de65  add     ebx, [r8+78h]
0x18001de69  mov     rdx, [rax+10h]
0x18001de6d  cmp     [rdx+19h], r14b
0x18001de71  jz      short loc_18001DE91
0x18001de73  mov     rcx, [rax+8]
0x18001de77  jmp     short loc_18001DE86
0x18001de79  cmp     rax, [rcx+10h]
0x18001de7d  jnz     short loc_18001DE8C
0x18001de7f  mov     rax, rcx
0x18001de82  mov     rcx, [rcx+8]
0x18001de86  cmp     [rcx+19h], r14b
0x18001de8a  jz      short loc_18001DE79
0x18001de8c  mov     rax, rcx
0x18001de8f  jmp     short loc_18001DE5B
0x18001de91  mov     rax, rdx
0x18001de94  mov     rdx, [rdx]
0x18001de97  cmp     [rdx+19h], r14b
0x18001de9b  jnz     short loc_18001DE5B
0x18001de9d  mov     rax, rdx
0x18001dea0  mov     rcx, [rdx]
0x18001dea3  mov     rdx, rcx
0x18001dea6  cmp     [rcx+19h], r14b
0x18001deaa  jz      short loc_18001DE9D
0x18001deac  jmp     short loc_18001DE5B
0x18001deae  test    ebx, ebx
0x18001deb0  jnz     short loc_18001DEF0
0x18001deb2  mov     eax, cs:dword_1800BE0B8
0x18001deb8  cmp     eax, 2
0x18001debb  jbe     short loc_18001DEE6
0x18001debd  mov     dword ptr [rbp+57h+arg_10], 80004004h
0x18001dec4  lea     rax, [rbp+57h+arg_10]
0x18001dec8  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001decd  xor     r9d, r9d
0x18001ded0  xor     r8d, r8d
0x18001ded3  lea     rdx, word_1800A8D16
0x18001deda  lea     rcx, dword_1800BE0B8
0x18001dee1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001dee6  mov     eax, 80004004h
0x18001deeb  jmp     loc_18001E102
0x18001def0  lea     r12, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x18001def7  mov     [rbp+57h+var_70], r12
0x18001defb  mov     [rbp+57h+SecurityDescriptor], r14
0x18001deff  lea     rcx, [rbp+57h+var_70]
0x18001df03  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001df08  xor     r9d, r9d; SecurityDescriptorSize
0x18001df0b  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001df0f  lea     edx, [r9+1]; StringSDRevision
0x18001df13  lea     rcx, aOLsdAGrWdAGrAc; "O:LSD:(A;;GR;;;WD)(A;;GR;;;AC)"
0x18001df1a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001df21  nop     dword ptr [rax+rax+00h]
0x18001df26  test    eax, eax
0x18001df28  jnz     short loc_18001DF7E
0x18001df2a  call    cs:__imp_GetLastError
0x18001df31  nop     dword ptr [rax+rax+00h]
0x18001df36  mov     ebx, eax
0x18001df38  mov     ecx, cs:dword_1800BE0B8
0x18001df3e  cmp     ecx, 2
0x18001df41  jbe     short loc_18001DF68
0x18001df43  mov     dword ptr [rbp+57h+arg_10], eax
0x18001df46  lea     rax, [rbp+57h+arg_10]
0x18001df4a  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001df4f  xor     r9d, r9d
0x18001df52  xor     r8d, r8d
0x18001df55  lea     rdx, byte_1800A8CD7
0x18001df5c  lea     rcx, dword_1800BE0B8
0x18001df63  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001df68  test    ebx, ebx
0x18001df6a  jle     loc_18001E0F3
0x18001df70  movzx   ebx, bx
0x18001df73  or      ebx, 80070000h
0x18001df79  jmp     loc_18001E0F3
0x18001df7e  xorps   xmm0, xmm0
0x18001df81  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18001df86  mov     [rbp+57h+var_50], r14
0x18001df8a  mov     edx, ebx
0x18001df8c  lea     rcx, [rbp+57h+var_60]
0x18001df90  call    ?reserve@?$vector@URPC_INTERFACE_TEMPLATEW@@V?$allocator@URPC_INTERFACE_TEMPLATEW@@@std@@@std@@QEAAX_K@Z; std::vector<RPC_INTERFACE_TEMPLATEW>::reserve(unsigned __int64)
0x18001df95  mov     rbx, [rdi]
0x18001df98  mov     rbx, [rbx]
0x18001df9b  cmp     [rbx+19h], r14b
0x18001df9f  jnz     short loc_18001DFFF
0x18001dfa1  mov     r8, [rbx+28h]
0x18001dfa5  mov     r9d, [r8+78h]
0x18001dfa9  mov     r8, [r8+70h]
0x18001dfad  mov     rdx, [rbp+57h+var_60+8]
0x18001dfb1  lea     rcx, [rbp+57h+var_60]
0x18001dfb5  call    ??$_Insert_counted_range@PEAURPC_INTERFACE_TEMPLATEW@@@?$vector@URPC_INTERFACE_TEMPLATEW@@V?$allocator@URPC_INTERFACE_TEMPLATEW@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@URPC_INTERFACE_TEMPLATEW@@@std@@@std@@@1@PEAURPC_INTERFACE_TEMPLATEW@@_K@Z; std::vector<RPC_INTERFACE_TEMPLATEW>::_Insert_counted_range<RPC_INTERFACE_TEMPLATEW *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<RPC_INTERFACE_TEMPLATEW>>>,RPC_INTERFACE_TEMPLATEW *,unsigned __int64)
0x18001dfba  mov     rcx, [rbx+10h]
0x18001dfbe  cmp     [rcx+19h], r14b
0x18001dfc2  jz      short loc_18001DFE2
0x18001dfc4  mov     rax, [rbx+8]
0x18001dfc8  jmp     short loc_18001DFD7
0x18001dfca  cmp     rbx, [rax+10h]
0x18001dfce  jnz     short loc_18001DFDD
0x18001dfd0  mov     rbx, rax
0x18001dfd3  mov     rax, [rax+8]
0x18001dfd7  cmp     [rax+19h], r14b
0x18001dfdb  jz      short loc_18001DFCA
0x18001dfdd  mov     rbx, rax
0x18001dfe0  jmp     short loc_18001DF9B
0x18001dfe2  mov     rbx, rcx
0x18001dfe5  mov     rcx, [rcx]
0x18001dfe8  cmp     [rcx+19h], r14b
0x18001dfec  jnz     short loc_18001DF9B
0x18001dfee  mov     rbx, rcx
0x18001dff1  mov     rax, [rcx]
0x18001dff4  mov     rcx, rax
0x18001dff7  cmp     [rax+19h], r14b
0x18001dffb  jz      short loc_18001DFEE
0x18001dffd  jmp     short loc_18001DF9B
0x18001dfff  mov     [rbp+57h+var_48], r14d
0x18001e003  lea     rax, ProtSeq; "ncalrpc"
0x18001e00a  mov     [rbp+57h+var_40], rax
0x18001e00e  mov     [rbp+57h+var_38], r14
0x18001e012  mov     rax, [rbp+57h+SecurityDescriptor]
0x18001e016  mov     [rbp+57h+var_30], rax
0x18001e01a  mov     [rbp+57h+var_28], 0Ah
0x18001e021  mov     [rbp+57h+var_80], rdi
0x18001e025  mov     [rbp+57h+var_78], 102h
0x18001e02b  mov     rdx, [rbp+57h+var_60]; struct RPC_INTERFACE_TEMPLATEW *
0x18001e02f  mov     r8, [rbp+57h+var_60+8]
0x18001e033  sub     r8, rdx
0x18001e036  sar     r8, 4
0x18001e03a  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18001e044  imul    r8, r15; unsigned int
0x18001e048  mov     [rsp+0C0h+var_98], esi; unsigned int
0x18001e04c  lea     r9, [rbp+57h+var_48]; struct RPC_ENDPOINT_TEMPLATEW *
0x18001e050  lea     rcx, [rdi+10h]; this
0x18001e054  call    ?Create@RpcServer@NgcUtils@@QEAAJPEAURPC_INTERFACE_TEMPLATEW@@KPEAURPC_ENDPOINT_TEMPLATEW@@KKP6AXPEAX2K@Z2@Z; NgcUtils::RpcServer::Create(RPC_INTERFACE_TEMPLATEW *,ulong,RPC_ENDPOINT_TEMPLATEW *,ulong,ulong,void (*)(void *,void *,ulong),void *)
0x18001e059  mov     ebx, eax
0x18001e05b  test    eax, eax
0x18001e05d  jns     short loc_18001E091
0x18001e05f  mov     ecx, cs:dword_1800BE0B8
0x18001e065  cmp     ecx, 2
0x18001e068  jbe     short loc_18001E0B8
0x18001e06a  lea     rdx, qword_1800A8CB0
0x18001e071  mov     dword ptr [rbp+57h+arg_10], eax
0x18001e074  xor     r9d, r9d
0x18001e077  lea     rax, [rbp+57h+arg_10]
0x18001e07b  xor     r8d, r8d
0x18001e07e  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001e083  lea     rcx, dword_1800BE0B8
0x18001e08a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001e08f  jmp     short loc_18001E0B8
0x18001e091  lea     rcx, [rdi+10h]; this
0x18001e095  call    ?Start@RpcServer@NgcUtils@@QEAAJXZ; NgcUtils::RpcServer::Start(void)
0x18001e09a  mov     ebx, eax
0x18001e09c  test    eax, eax
0x18001e09e  jns     short loc_18001E0B4
0x18001e0a0  mov     ecx, cs:dword_1800BE0B8
0x18001e0a6  cmp     ecx, 2
0x18001e0a9  jbe     short loc_18001E0B8
0x18001e0ab  lea     rdx, word_1800A8C8A
0x18001e0b2  jmp     short loc_18001E071
0x18001e0b4  mov     byte ptr [rbp+57h+var_78+1], r14b
0x18001e0b8  lea     rcx, [rbp+57h+var_80]
0x18001e0bc  call    wil__details__ScopeExitFnGuard__lambda_f74cc1db97316ec4b3f3112de3f331cb_____operator__
0x18001e0c1  nop
0x18001e0c2  mov     rcx, [rbp+57h+var_60]
0x18001e0c6  test    rcx, rcx
0x18001e0c9  jz      short loc_18001E0F3
0x18001e0cb  mov     rax, [rbp+57h+var_50]
0x18001e0cf  sub     rax, rcx
0x18001e0d2  sar     rax, 4
0x18001e0d6  imul    rax, r15
0x18001e0da  lea     rdx, [rax+rax*4]
0x18001e0de  shl     rdx, 4
0x18001e0e2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e0e7  xorps   xmm0, xmm0
0x18001e0ea  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18001e0ef  mov     [rbp+57h+var_50], r14
0x18001e0f3  mov     [rbp+57h+var_70], r12
0x18001e0f7  lea     rcx, [rbp+57h+var_70]
0x18001e0fb  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001e100  mov     eax, ebx
0x18001e102  lea     r11, [rsp+0C0h+var_20]
0x18001e10a  mov     rbx, [r11+30h]
0x18001e10e  mov     rsi, [r11+38h]
0x18001e112  mov     rsp, r11
0x18001e115  pop     r15
0x18001e117  pop     r14
0x18001e119  pop     r12
0x18001e11b  pop     rdi
0x18001e11c  pop     rbp
0x18001e11d  retn
```
