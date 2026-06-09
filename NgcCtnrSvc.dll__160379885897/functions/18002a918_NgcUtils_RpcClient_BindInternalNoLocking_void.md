# NgcUtils::RpcClient::BindInternalNoLocking(void)

- ea: `0x18002a918`
- end: `0x18002aba8`
- name: `?BindInternalNoLocking@RpcClient@NgcUtils@@AEAAJXZ`
- size: `656`
- prototype: `__int64 __fastcall(NgcUtils::RpcClient *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002a878`
- `0x18002a8cc`

## callees

- `0x180002424`
- `0x180016888`
- `0x180018194`
- `0x180019c94`
- `0x18001ced8`
- `0x18002a918`
- `0x18002c640`
- `0x18005e888`

## import_xrefs

- `RPCRT4!RpcBindingBind` at `0x18002aae2`
- `RPCRT4!RpcBindingBind` at `0x18002aae2`
- `RPCRT4!RpcBindingCreateW` at `0x18002aa6d`
- `RPCRT4!RpcBindingCreateW` at `0x18002aa6d`

## pseudocode

```c
__int64 __fastcall NgcUtils::RpcClient::BindInternalNoLocking(NgcUtils::RpcClient *this)
{
  char *v2; // rcx
  RPC_BINDING_HANDLE *v3; // rbx
  RPC_STATUS v5; // eax
  signed int v6; // ebx
  int v7; // esi
  RPC_STATUS v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // ecx
  __int64 v12; // [rsp+30h] [rbp-89h] BYREF
  NgcUtils::RpcClient *v13; // [rsp+38h] [rbp-81h] BYREF
  __int16 v14; // [rsp+40h] [rbp-79h]
  _DWORD v15[4]; // [rsp+48h] [rbp-71h] BYREF
  __int64 v16; // [rsp+58h] [rbp-61h]
  __int64 v17; // [rsp+60h] [rbp-59h]
  __int64 v18; // [rsp+68h] [rbp-51h]
  __int64 v19; // [rsp+70h] [rbp-49h]
  __int64 v20; // [rsp+78h] [rbp-41h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+80h] [rbp-39h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+A8h] [rbp-11h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+E0h] [rbp+27h] BYREF

  v2 = (char *)this + 8;
  v3 = (RPC_BINDING_HANDLE *)(v2 + 8);
  if ( *((_QWORD *)v2 + 1) )
  {
    if ( (unsigned int)dword_1800BE0B8 > 3 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&byte_1800AE9DF,
        0);
    return 0;
  }
  else if ( *((int *)this + 12) >= 0 )
  {
    Template.ProtocolSequence = *((_DWORD *)this + 6);
    *(_QWORD *)&Template.Version = 1;
    memset(&Template.ProtocolSequence + 1, 0, 44);
    v15[1] = *((_DWORD *)this + 7);
    v15[2] = *((_DWORD *)this + 8);
    v15[3] = *((_DWORD *)this + 9);
    v18 = *((_QWORD *)this + 7);
    v20 = *((_QWORD *)this + 11);
    Security.SecurityQos = (RPC_SECURITY_QOS *)v15;
    v15[0] = 5;
    v16 = 0;
    v17 = 0;
    v19 = 1;
    *(_QWORD *)&Security.Version = 1;
    Security.ServerPrincName = 0;
    Security.AuthnLevel = 6;
    Security.AuthnSvc = 10;
    Security.AuthIdentity = 0;
    Options.Version = 1;
    Options.Flags = 1;
    *(_QWORD *)&Options.ComTimeout = 5;
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(v2);
    v5 = RpcBindingCreateW(&Template, &Security, &Options, v3);
    if ( v5 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = v5;
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v12) = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)&word_1800AE966,
          0,
          0,
          (__int64)&v12);
      }
    }
    else
    {
      v13 = this;
      v7 = 0;
      v14 = 258;
      while ( 1 )
      {
        v8 = RpcBindingBind(0, *((RPC_BINDING_HANDLE *)this + 2), *((RPC_IF_HANDLE *)this + 5));
        v6 = v8;
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        if ( v6 >= 0 )
          break;
        if ( (unsigned int)dword_1800BE0B8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800BE0B8, 0x200000000000LL) )
        {
          v12 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            (__int64)&dword_1800BE0B8,
            (__int64)&byte_1800AE8FF,
            v9,
            v10,
            (__int64)&v12);
        }
        if ( (unsigned int)(v6 + 2147023179) > 0xA || (v11 = 1601, !_bittest(&v11, v6 + 2147023179)) )
        {
          *((_DWORD *)this + 12) = v6;
          goto LABEL_28;
        }
        if ( (unsigned int)++v7 >= 0x14 )
          goto LABEL_28;
      }
      HIBYTE(v14) = 0;
LABEL_28:
      wil::details::ScopeExitFnGuard__lambda_22ea034c96aed9483165fa2d3e8cbb87___::operator()(&v13);
    }
    return (unsigned int)v6;
  }
  else
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v12) = *((_DWORD *)this + 12);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AE929,
        0,
        0,
        (__int64)&v12);
    }
    return *((unsigned int *)this + 12);
  }
}

```

## disassembly

```asm
0x18002a918  mov     [rsp-8+arg_8], rbx
0x18002a91d  mov     [rsp-8+arg_10], rsi
0x18002a922  push    rbp
0x18002a923  push    rdi
0x18002a924  push    r15
0x18002a926  lea     rbp, [rsp-47h]
0x18002a92b  sub     rsp, 100h
0x18002a932  mov     rax, cs:__security_cookie
0x18002a939  xor     rax, rsp
0x18002a93c  mov     [rbp+57h+var_20], rax
0x18002a940  mov     rdi, rcx
0x18002a943  add     rcx, 8
0x18002a947  lea     rbx, [rcx+8]
0x18002a94b  cmp     qword ptr [rbx], 0
0x18002a94f  jz      short loc_18002A979
0x18002a951  mov     eax, cs:dword_1800BE0B8
0x18002a957  cmp     eax, 3
0x18002a95a  jbe     short loc_18002A972
0x18002a95c  xor     r8d, r8d
0x18002a95f  lea     rdx, byte_1800AE9DF
0x18002a966  lea     rcx, dword_1800BE0B8
0x18002a96d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18002a972  xor     eax, eax
0x18002a974  jmp     loc_18002AB83
0x18002a979  cmp     dword ptr [rdi+30h], 0
0x18002a97d  jge     short loc_18002A9BC
0x18002a97f  mov     eax, cs:dword_1800BE0B8
0x18002a985  cmp     eax, 2
0x18002a988  jbe     short loc_18002A9B4
0x18002a98a  mov     eax, [rdi+30h]
0x18002a98d  lea     rdx, byte_1800AE929
0x18002a994  mov     dword ptr [rsp+110h+var_E0], eax
0x18002a998  lea     rcx, dword_1800BE0B8
0x18002a99f  lea     rax, [rsp+110h+var_E0]
0x18002a9a4  xor     r9d, r9d
0x18002a9a7  xor     r8d, r8d
0x18002a9aa  mov     [rsp+110h+var_F0], rax
0x18002a9af  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002a9b4  mov     eax, [rdi+30h]
0x18002a9b7  jmp     loc_18002AB83
0x18002a9bc  mov     eax, [rdi+18h]
0x18002a9bf  mov     r15d, 1
0x18002a9c5  mov     [rbp+57h+Template.ProtocolSequence], eax
0x18002a9c8  xorps   xmm0, xmm0
0x18002a9cb  xor     eax, eax
0x18002a9cd  mov     qword ptr [rbp+57h+Template.Version], r15
0x18002a9d1  mov     dword ptr [rbp+57h+Template+0Ch], eax
0x18002a9d4  mov     qword ptr [rbp+57h+Template.u1], rax
0x18002a9d8  mov     [rbp+57h+Template.ObjectUuid.Data1], eax
0x18002a9db  lea     edx, [rax+5]
0x18002a9de  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data2], rax
0x18002a9e2  mov     dword ptr [rbp+57h+Template.ObjectUuid.Data4+4], eax
0x18002a9e5  mov     eax, [rdi+1Ch]
0x18002a9e8  mov     [rbp+57h+var_C4], eax
0x18002a9eb  mov     eax, [rdi+20h]
0x18002a9ee  mov     [rbp+57h+var_C0], eax
0x18002a9f1  mov     eax, [rdi+24h]
0x18002a9f4  mov     [rbp+57h+var_BC], eax
0x18002a9f7  mov     rax, [rdi+38h]
0x18002a9fb  mov     [rbp+57h+var_A8], rax
0x18002a9ff  mov     rax, [rdi+58h]
0x18002aa03  mov     [rbp+57h+var_98], rax
0x18002aa07  lea     rax, [rbp+57h+var_C8]
0x18002aa0b  mov     [rbp+57h+Security.SecurityQos], rax
0x18002aa0f  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x18002aa14  mov     [rbp+57h+var_C8], edx
0x18002aa17  mov     [rbp+57h+var_B8], 0
0x18002aa1f  mov     [rbp+57h+var_B0], 0
0x18002aa27  mov     [rbp+57h+var_A0], r15
0x18002aa2b  mov     qword ptr [rbp+57h+Security.Version], r15
0x18002aa2f  mov     [rbp+57h+Security.ServerPrincName], 0
0x18002aa37  mov     [rbp+57h+Security.AuthnLevel], 6
0x18002aa3e  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18002aa45  mov     [rbp+57h+Security.AuthIdentity], 0
0x18002aa4d  mov     [rbp+57h+Options.Version], r15d
0x18002aa51  mov     [rbp+57h+Options.Flags], r15d
0x18002aa55  mov     qword ptr [rbp+57h+Options.ComTimeout], rdx
0x18002aa59  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18002aa5e  mov     r9, rbx; Binding
0x18002aa61  lea     r8, [rbp+57h+Options]; Options
0x18002aa65  lea     rdx, [rbp+57h+Security]; Security
0x18002aa69  lea     rcx, [rbp+57h+Template]; Template
0x18002aa6d  call    cs:__imp_RpcBindingCreateW
0x18002aa74  nop     dword ptr [rax+rax+00h]
0x18002aa79  mov     ecx, eax
0x18002aa7b  test    eax, eax
0x18002aa7d  jz      short loc_18002AACB
0x18002aa7f  test    eax, eax
0x18002aa81  jg      short loc_18002AA87
0x18002aa83  mov     ebx, eax
0x18002aa85  jmp     short loc_18002AA90
0x18002aa87  movzx   ebx, cx
0x18002aa8a  or      ebx, 80070000h
0x18002aa90  mov     eax, cs:dword_1800BE0B8
0x18002aa96  cmp     eax, 2
0x18002aa99  jbe     loc_18002AB81
0x18002aa9f  mov     dword ptr [rsp+110h+var_E0], ecx
0x18002aaa3  lea     rax, [rsp+110h+var_E0]
0x18002aaa8  lea     rcx, dword_1800BE0B8
0x18002aaaf  mov     [rsp+110h+var_F0], rax
0x18002aab4  xor     r9d, r9d
0x18002aab7  lea     rdx, word_1800AE966
0x18002aabe  xor     r8d, r8d
0x18002aac1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002aac6  jmp     loc_18002AB81
0x18002aacb  mov     [rsp+110h+var_D8], rdi
0x18002aad0  xor     esi, esi
0x18002aad2  mov     [rbp+57h+var_D0], 102h
0x18002aad8  mov     r8, [rdi+28h]; IfSpec
0x18002aadc  xor     ecx, ecx; pAsync
0x18002aade  mov     rdx, [rdi+10h]; Binding
0x18002aae2  call    cs:__imp_RpcBindingBind
0x18002aae9  nop     dword ptr [rax+rax+00h]
0x18002aaee  mov     ebx, eax
0x18002aaf0  test    eax, eax
0x18002aaf2  jle     short loc_18002AAFD
0x18002aaf4  movzx   ebx, ax
0x18002aaf7  or      ebx, 80070000h
0x18002aafd  test    ebx, ebx
0x18002aaff  jns     short loc_18002AB73
0x18002ab01  mov     eax, cs:dword_1800BE0B8
0x18002ab07  cmp     eax, 2
0x18002ab0a  jbe     short loc_18002AB4B
0x18002ab0c  mov     rdx, 200000000000h
0x18002ab16  lea     rcx, dword_1800BE0B8
0x18002ab1d  call    _tlgKeywordOn
0x18002ab22  test    al, al
0x18002ab24  jz      short loc_18002AB4B
0x18002ab26  movsxd  rax, ebx
0x18002ab29  lea     rdx, byte_1800AE8FF
0x18002ab30  mov     [rsp+110h+var_E0], rax
0x18002ab35  lea     rcx, dword_1800BE0B8
0x18002ab3c  lea     rax, [rsp+110h+var_E0]
0x18002ab41  mov     [rsp+110h+var_F0], rax
0x18002ab46  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18002ab4b  lea     eax, [rbx+7FF8F94Bh]
0x18002ab51  cmp     eax, 0Ah
0x18002ab54  ja      short loc_18002AB6E
0x18002ab56  mov     ecx, 641h
0x18002ab5b  bt      ecx, eax
0x18002ab5e  jnb     short loc_18002AB6E
0x18002ab60  add     esi, r15d
0x18002ab63  cmp     esi, 14h
0x18002ab66  jb      loc_18002AAD8
0x18002ab6c  jmp     short loc_18002AB77
0x18002ab6e  mov     [rdi+30h], ebx
0x18002ab71  jmp     short loc_18002AB77
0x18002ab73  mov     byte ptr [rbp+57h+var_D0+1], 0
0x18002ab77  lea     rcx, [rsp+110h+var_D8]
0x18002ab7c  call    wil__details__ScopeExitFnGuard__lambda_22ea034c96aed9483165fa2d3e8cbb87_____operator__
0x18002ab81  mov     eax, ebx
0x18002ab83  mov     rcx, [rbp+57h+var_20]
0x18002ab87  xor     rcx, rsp; StackCookie
0x18002ab8a  call    __security_check_cookie
0x18002ab8f  lea     r11, [rsp+110h+var_10]
0x18002ab97  mov     rbx, [r11+28h]
0x18002ab9b  mov     rsi, [r11+30h]
0x18002ab9f  mov     rsp, r11
0x18002aba2  pop     r15
0x18002aba4  pop     rdi
0x18002aba5  pop     rbp
0x18002aba6  retn
```
