# DSService::RegisterRpcInterface(void)

- ea: `0x1800074bc`
- end: `0x1800079e6`
- name: `?RegisterRpcInterface@DSService@@IEAAJXZ`
- size: `1322`
- prototype: `__int64 __fastcall(DSService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006730`

## callees

- `0x180001178`
- `0x18000140c`
- `0x180001720`
- `0x180001b88`
- `0x1800074bc`

## import_xrefs

- `RPCRT4!RpcEpRegisterA` at `0x180007804`
- `RPCRT4!RpcEpRegisterA` at `0x180007804`
- `RPCRT4!RpcServerRegisterIf3` at `0x180007726`
- `RPCRT4!RpcServerRegisterIf3` at `0x180007726`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000756f`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000756f`
- `RPCRT4!RpcBindingVectorFree` at `0x18000793f`
- `RPCRT4!RpcBindingVectorFree` at `0x18000793f`
- `RPCRT4!RpcServerInqBindings` at `0x180007657`
- `RPCRT4!RpcServerInqBindings` at `0x180007657`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180007500`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000753e`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180007500`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000753e`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000791f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000792e`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000791f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000792e`

## string_xrefs

- `0x180007518`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180007618`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180007644`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x1800074f9`: `DiagnosticInvokerRpcAccess`
- `0x180007537`: `IDSService\Interface`
- `0x18000751f`: `DSService::RegisterRpcInterface`
- `0x18000760d`: `DSService::RegisterRpcInterface`
- `0x18000763d`: `DSService::RegisterRpcInterface`
- `0x1800077bb`: `DSService::RegisterRpcInterface`
- `0x1800077e0`: `DSService::RegisterRpcInterface`
- `0x1800075aa`: `RPC Register Protocol Sequence`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DSService::RegisterRpcInterface(DSService *this)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  signed int v6; // ebx
  int v7; // eax
  RPC_STATUS v8; // eax
  int v9; // r9d
  RPC_STATUS v10; // eax
  int v11; // r9d
  int v12; // eax
  int v13; // r9d
  RPC_BINDING_VECTOR *v14; // rdx
  RPC_STATUS v15; // eax
  int v16; // r9d
  int v17; // ecx
  int v18; // r9d
  __int64 v19; // rcx
  RPC_STATUS v20; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  const char *v25; // [rsp+70h] [rbp-19h] BYREF
  const char *v26; // [rsp+78h] [rbp-11h] BYREF
  const char *v27; // [rsp+80h] [rbp-9h] BYREF
  signed int v28; // [rsp+88h] [rbp-1h] BYREF
  void *SecurityDescriptor; // [rsp+90h] [rbp+7h] BYREF
  __int64 v30; // [rsp+98h] [rbp+Fh] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+A0h] [rbp+17h] BYREF
  const char *v32; // [rsp+A8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v33; // [rsp+B0h] [rbp+27h] BYREF
  int v34; // [rsp+F8h] [rbp+6Fh] BYREF
  int v35; // [rsp+100h] [rbp+77h] BYREF
  const char *v36; // [rsp+108h] [rbp+7Fh] BYREF

  SecurityDescriptor = 0;
  v30 = 0;
  BindingVector = 0;
  v2 = QueryTransientObjectSecurityDescriptor(8, L"DiagnosticInvokerRpcAccess", &SecurityDescriptor);
  v6 = v2;
  if ( v2 > 0 )
    v6 = (unsigned __int16)v2 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_48;
  v7 = QueryTransientObjectSecurityDescriptor(9, L"IDSService\\Interface", &v30);
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_48;
  v8 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, v3, v5) )
  {
    v34 = (int)SecurityDescriptor;
    v26 = "RPC Register Protocol Sequence";
    v27 = (char *)this + 104;
    v35 = 10;
    v33 = L"ncalrpc";
    LODWORD(v36) = 496;
    v32 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v25 = "DSService::RegisterRpcInterface";
    v28 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)byte_18002F251,
      v5,
      v9,
      (__int64)&v27,
      (__int64)&v28,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v32,
      (__int64)&v36,
      (__int64)&v33,
      (__int64)&v35,
      (__int64)&v34);
  }
  if ( v6 < 0 )
    goto LABEL_48;
  v10 = RpcServerInqBindings(&BindingVector);
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, v3, v5) )
  {
    v34 = 507;
    v26 = "RPC Inquire binding vector";
    v36 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v25 = (char *)this + 104;
    v27 = "DSService::RegisterRpcInterface";
    v35 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&unk_18002F1E8,
      v5,
      v11,
      (__int64)&v25,
      (__int64)&v35,
      (__int64)&v26,
      (__int64)&v27,
      (__int64)&v36,
      (__int64)&v34);
  }
  if ( v6 < 0 )
    goto LABEL_48;
  v12 = RpcServerRegisterIf3(qword_180029820, 0, 0, 57, 1234, 0, SecurityCallBack, v30);
  v6 = v12;
  if ( v12 > 0 )
    v6 = (unsigned __int16)v12 | 0x80070000;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, v3, v5) )
  {
    v34 = v30;
    v25 = "RPC IDiagnosticServerRPC Interface";
    v32 = (char *)this + 104;
    v35 = 1234;
    LODWORD(v36) = 528;
    v27 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v26 = "DSService::RegisterRpcInterface";
    v28 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)byte_18002F161,
      v5,
      v13,
      (__int64)&v32,
      (__int64)&v28,
      (__int64)&v25,
      (__int64)&v26,
      (__int64)&v27,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34);
  }
  if ( v6 < 0 )
    goto LABEL_48;
  v14 = BindingVector;
  *((_BYTE *)this + 56) = 1;
  v15 = RpcEpRegisterA(qword_180029820, v14, 0, 0);
  v6 = v15;
  if ( v15 > 0 )
    v6 = (unsigned __int16)v15 | 0x80070000;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, v3, v5) )
  {
    v34 = 545;
    v26 = "RPC Endpoint";
    v36 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v25 = (char *)this + 104;
    v27 = "DSService::RegisterRpcInterface";
    v35 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&unk_18002F0F8,
      v5,
      v16,
      (__int64)&v25,
      (__int64)&v35,
      (__int64)&v26,
      (__int64)&v27,
      (__int64)&v36,
      (__int64)&v34);
  }
  if ( v6 < 0 )
  {
LABEL_48:
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, v3, v5) )
    {
      v34 = 559;
      v26 = "RPC Failed to register endpoint / interface";
      v36 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
      v25 = (char *)this + 104;
      v27 = "DSService::RegisterRpcInterface";
      v35 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)&byte_18002F08F,
        v5,
        v18,
        (__int64)&v25,
        (__int64)&v35,
        (__int64)&v26,
        (__int64)&v27,
        (__int64)&v36,
        (__int64)&v34);
    }
  }
  else
  {
    *((_BYTE *)this + 57) = 1;
  }
  if ( SecurityDescriptor )
    FreeTransientObjectSecurityDescriptor();
  v19 = v30;
  if ( v30 )
    FreeTransientObjectSecurityDescriptor();
  if ( BindingVector )
  {
    v20 = RpcBindingVectorFree(&BindingVector);
    v6 = v20;
    if ( v20 > 0 )
      v6 = (unsigned __int16)v20 | 0x80070000;
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v19, v3, v5) )
  {
    v34 = 581;
    v26 = "Free RPC Binding Vector";
    v36 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v25 = (char *)this + 104;
    v27 = "DSService::RegisterRpcInterface";
    v35 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)&word_18002F026,
      v22,
      v23,
      (__int64)&v25,
      (__int64)&v35,
      (__int64)&v26,
      (__int64)&v27,
      (__int64)&v36,
      (__int64)&v34);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800074bc  mov     [rsp-8+arg_0], rbx
0x1800074c1  push    rbp
0x1800074c2  push    rdi
0x1800074c3  push    r12
0x1800074c5  push    r13
0x1800074c7  push    r14
0x1800074c9  lea     rbp, [rsp-37h]
0x1800074ce  sub     rsp, 0C0h
0x1800074d5  mov     rdi, rcx
0x1800074d8  mov     [rbp+57h+SecurityDescriptor], 0
0x1800074e0  mov     ecx, 8
0x1800074e5  mov     [rbp+57h+var_48], 0
0x1800074ed  lea     r8, [rbp+57h+SecurityDescriptor]
0x1800074f1  mov     [rbp+57h+BindingVector], 0
0x1800074f9  lea     rdx, aDiagnosticinvo; "DiagnosticInvokerRpcAccess"
0x180007500  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180007506  mov     ebx, eax
0x180007508  mov     r14d, 80070000h
0x18000750e  test    eax, eax
0x180007510  jle     short loc_180007518
0x180007512  movzx   ebx, ax
0x180007515  or      ebx, r14d
0x180007518  lea     r13, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18000751f  lea     r12, aDsserviceRegis; "DSService::RegisterRpcInterface"
0x180007526  test    ebx, ebx
0x180007528  js      loc_18000789B
0x18000752e  lea     r8, [rbp+57h+var_48]
0x180007532  mov     ecx, 9
0x180007537  lea     rdx, aIdsserviceInte; "IDSService\\Interface"
0x18000753e  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180007544  mov     ebx, eax
0x180007546  test    eax, eax
0x180007548  jle     short loc_180007550
0x18000754a  movzx   ebx, ax
0x18000754d  or      ebx, r14d
0x180007550  test    ebx, ebx
0x180007552  js      loc_18000789B
0x180007558  mov     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000755c  lea     r13, Protseq; "ncalrpc"
0x180007563  mov     r12d, 0Ah
0x180007569  mov     rcx, r13; Protseq
0x18000756c  mov     edx, r12d; MaxCalls
0x18000756f  call    cs:__imp_RpcServerUseProtseqW
0x180007575  mov     ebx, eax
0x180007577  test    eax, eax
0x180007579  jle     short loc_180007581
0x18000757b  movzx   ebx, ax
0x18000757e  or      ebx, r14d
0x180007581  mov     eax, cs:dword_180039000
0x180007587  cmp     eax, 5
0x18000758a  jbe     loc_18000763D
0x180007590  call    _tlgKeywordOn
0x180007595  test    al, al
0x180007597  jz      loc_18000763D
0x18000759d  mov     eax, dword ptr [rbp+57h+SecurityDescriptor]
0x1800075a0  lea     rdx, byte_18002F251
0x1800075a7  mov     [rbp+57h+arg_8], eax
0x1800075aa  lea     rax, aRpcRegisterPro; "RPC Register Protocol Sequence"
0x1800075b1  mov     [rbp+57h+var_68], rax
0x1800075b5  lea     rax, [rdi+68h]
0x1800075b9  mov     [rbp+57h+var_60], rax
0x1800075bd  lea     rax, [rbp+57h+arg_8]
0x1800075c1  mov     [rsp+0E0h+var_80], rax
0x1800075c6  lea     rax, [rbp+57h+arg_10]
0x1800075ca  mov     [rsp+0E0h+var_88], rax
0x1800075cf  lea     rax, [rbp+57h+var_30]
0x1800075d3  mov     [rsp+0E0h+var_90], rax
0x1800075d8  lea     rax, [rbp+57h+arg_18]
0x1800075dc  mov     [rsp+0E0h+var_98], rax
0x1800075e1  lea     rax, [rbp+57h+var_38]
0x1800075e5  mov     [rsp+0E0h+var_A0], rax
0x1800075ea  lea     rax, [rbp+57h+var_70]
0x1800075ee  mov     [rsp+0E0h+var_A8], rax
0x1800075f3  lea     rax, [rbp+57h+var_68]
0x1800075f7  mov     [rsp+0E0h+var_B0], rax
0x1800075fc  lea     rax, [rbp+57h+var_58]
0x180007600  mov     [rsp+0E0h+var_B8], rax
0x180007605  lea     rax, [rbp+57h+var_60]
0x180007609  mov     [rbp+57h+arg_10], r12d
0x18000760d  lea     r12, aDsserviceRegis; "DSService::RegisterRpcInterface"
0x180007614  mov     [rbp+57h+var_30], r13
0x180007618  lea     r13, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18000761f  mov     [rsp+0E0h+var_C0], rax
0x180007624  mov     dword ptr [rbp+57h+arg_18], 1F0h
0x18000762b  mov     [rbp+57h+var_38], r13
0x18000762f  mov     [rbp+57h+var_70], r12
0x180007633  mov     [rbp+57h+var_58], ebx
0x180007636  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000763b  jmp     short loc_18000764B
0x18000763d  lea     r12, aDsserviceRegis; "DSService::RegisterRpcInterface"
0x180007644  lea     r13, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18000764b  test    ebx, ebx
0x18000764d  js      loc_18000789B
0x180007653  lea     rcx, [rbp+57h+BindingVector]; BindingVector
0x180007657  call    cs:__imp_RpcServerInqBindings
0x18000765d  mov     ebx, eax
0x18000765f  test    eax, eax
0x180007661  jle     short loc_180007669
0x180007663  movzx   ebx, ax
0x180007666  or      ebx, r14d
0x180007669  mov     eax, cs:dword_180039000
0x18000766f  cmp     eax, 5
0x180007672  jbe     short loc_1800076E4
0x180007674  call    _tlgKeywordOn
0x180007679  test    al, al
0x18000767b  jz      short loc_1800076E4
0x18000767d  lea     rax, aRpcInquireBind; "RPC Inquire binding vector"
0x180007684  mov     [rbp+57h+arg_8], 1FBh
0x18000768b  mov     [rbp+57h+var_68], rax
0x18000768f  lea     rdx, unk_18002F1E8
0x180007696  lea     rax, [rdi+68h]
0x18000769a  mov     [rbp+57h+arg_18], r13
0x18000769e  mov     [rbp+57h+var_70], rax
0x1800076a2  lea     rax, [rbp+57h+arg_8]
0x1800076a6  mov     [rsp+0E0h+var_98], rax
0x1800076ab  lea     rax, [rbp+57h+arg_18]
0x1800076af  mov     [rsp+0E0h+var_A0], rax
0x1800076b4  lea     rax, [rbp+57h+var_60]
0x1800076b8  mov     [rsp+0E0h+var_A8], rax
0x1800076bd  lea     rax, [rbp+57h+var_68]
0x1800076c1  mov     [rsp+0E0h+var_B0], rax
0x1800076c6  lea     rax, [rbp+57h+arg_10]
0x1800076ca  mov     [rsp+0E0h+var_B8], rax
0x1800076cf  lea     rax, [rbp+57h+var_70]
0x1800076d3  mov     [rsp+0E0h+var_C0], rax
0x1800076d8  mov     [rbp+57h+var_60], r12
0x1800076dc  mov     [rbp+57h+arg_10], ebx
0x1800076df  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800076e4  test    ebx, ebx
0x1800076e6  js      loc_18000789B
0x1800076ec  mov     rax, [rbp+57h+var_48]
0x1800076f0  lea     rcx, qword_180029820
0x1800076f7  mov     [rsp+0E0h+var_A8], rax
0x1800076fc  mov     r12d, 4D2h
0x180007702  lea     rax, ?SecurityCallBack@@YAJPEAX0@Z; SecurityCallBack(void *,void *)
0x180007709  mov     r9d, 39h ; '9'
0x18000770f  mov     [rsp+0E0h+var_B0], rax
0x180007714  xor     r8d, r8d
0x180007717  mov     dword ptr [rsp+0E0h+var_B8], 0
0x18000771f  xor     edx, edx
0x180007721  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x180007726  call    cs:__imp_RpcServerRegisterIf3
0x18000772c  mov     ebx, eax
0x18000772e  test    eax, eax
0x180007730  jle     short loc_180007738
0x180007732  movzx   ebx, ax
0x180007735  or      ebx, r14d
0x180007738  mov     eax, cs:dword_180039000
0x18000773e  cmp     eax, 5
0x180007741  jbe     loc_1800077E0
0x180007747  call    _tlgKeywordOn
0x18000774c  test    al, al
0x18000774e  jz      loc_1800077E0
0x180007754  mov     eax, dword ptr [rbp+57h+var_48]
0x180007757  lea     rdx, byte_18002F161
0x18000775e  mov     [rbp+57h+arg_8], eax
0x180007761  lea     rax, aRpcIdiagnostic; "RPC IDiagnosticServerRPC Interface"
0x180007768  mov     [rbp+57h+var_70], rax
0x18000776c  lea     rax, [rdi+68h]
0x180007770  mov     [rbp+57h+var_38], rax
0x180007774  lea     rax, [rbp+57h+arg_8]
0x180007778  mov     [rsp+0E0h+var_88], rax
0x18000777d  lea     rax, [rbp+57h+arg_10]
0x180007781  mov     [rsp+0E0h+var_90], rax
0x180007786  lea     rax, [rbp+57h+arg_18]
0x18000778a  mov     [rsp+0E0h+var_98], rax
0x18000778f  lea     rax, [rbp+57h+var_60]
0x180007793  mov     [rsp+0E0h+var_A0], rax
0x180007798  lea     rax, [rbp+57h+var_68]
0x18000779c  mov     [rsp+0E0h+var_A8], rax
0x1800077a1  lea     rax, [rbp+57h+var_70]
0x1800077a5  mov     [rsp+0E0h+var_B0], rax
0x1800077aa  lea     rax, [rbp+57h+var_58]
0x1800077ae  mov     [rsp+0E0h+var_B8], rax
0x1800077b3  lea     rax, [rbp+57h+var_38]
0x1800077b7  mov     [rbp+57h+arg_10], r12d
0x1800077bb  lea     r12, aDsserviceRegis; "DSService::RegisterRpcInterface"
0x1800077c2  mov     [rsp+0E0h+var_C0], rax
0x1800077c7  mov     dword ptr [rbp+57h+arg_18], 210h
0x1800077ce  mov     [rbp+57h+var_60], r13
0x1800077d2  mov     [rbp+57h+var_68], r12
0x1800077d6  mov     [rbp+57h+var_58], ebx
0x1800077d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@333444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800077de  jmp     short loc_1800077E7
0x1800077e0  lea     r12, aDsserviceRegis; "DSService::RegisterRpcInterface"
0x1800077e7  test    ebx, ebx
0x1800077e9  js      loc_18000789B
0x1800077ef  mov     rdx, [rbp+57h+BindingVector]; BindingVector
0x1800077f3  lea     rcx, qword_180029820; IfSpec
0x1800077fa  xor     r9d, r9d; Annotation
0x1800077fd  mov     byte ptr [rdi+38h], 1
0x180007801  xor     r8d, r8d; UuidVector
0x180007804  call    cs:__imp_RpcEpRegisterA
0x18000780a  mov     ebx, eax
0x18000780c  test    eax, eax
0x18000780e  jle     short loc_180007816
0x180007810  movzx   ebx, ax
0x180007813  or      ebx, r14d
0x180007816  mov     eax, cs:dword_180039000
0x18000781c  cmp     eax, 5
0x18000781f  jbe     short loc_180007891
0x180007821  call    _tlgKeywordOn
0x180007826  test    al, al
0x180007828  jz      short loc_180007891
0x18000782a  lea     rax, aRpcEndpoint; "RPC Endpoint"
0x180007831  mov     [rbp+57h+arg_8], 221h
0x180007838  mov     [rbp+57h+var_68], rax
0x18000783c  lea     rdx, unk_18002F0F8
0x180007843  lea     rax, [rdi+68h]
0x180007847  mov     [rbp+57h+arg_18], r13
0x18000784b  mov     [rbp+57h+var_70], rax
0x18000784f  lea     rax, [rbp+57h+arg_8]
0x180007853  mov     [rsp+0E0h+var_98], rax
0x180007858  lea     rax, [rbp+57h+arg_18]
0x18000785c  mov     [rsp+0E0h+var_A0], rax
0x180007861  lea     rax, [rbp+57h+var_60]
0x180007865  mov     [rsp+0E0h+var_A8], rax
0x18000786a  lea     rax, [rbp+57h+var_68]
0x18000786e  mov     [rsp+0E0h+var_B0], rax
0x180007873  lea     rax, [rbp+57h+arg_10]
0x180007877  mov     [rsp+0E0h+var_B8], rax
0x18000787c  lea     rax, [rbp+57h+var_70]
0x180007880  mov     [rsp+0E0h+var_C0], rax
0x180007885  mov     [rbp+57h+var_60], r12
0x180007889  mov     [rbp+57h+arg_10], ebx
0x18000788c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007891  test    ebx, ebx
0x180007893  js      short loc_18000789B
0x180007895  mov     byte ptr [rdi+39h], 1
0x180007899  jmp     short loc_180007916
0x18000789b  mov     eax, cs:dword_180039000
0x1800078a1  cmp     eax, 5
0x1800078a4  jbe     short loc_180007916
0x1800078a6  call    _tlgKeywordOn
0x1800078ab  test    al, al
0x1800078ad  jz      short loc_180007916
0x1800078af  lea     rax, aRpcFailedToReg; "RPC Failed to register endpoint / inter"...
0x1800078b6  mov     [rbp+57h+arg_8], 22Fh
0x1800078bd  mov     [rbp+57h+var_68], rax
0x1800078c1  lea     rdx, byte_18002F08F
0x1800078c8  lea     rax, [rdi+68h]
0x1800078cc  mov     [rbp+57h+arg_18], r13
0x1800078d0  mov     [rbp+57h+var_70], rax
0x1800078d4  lea     rax, [rbp+57h+arg_8]
0x1800078d8  mov     [rsp+0E0h+var_98], rax
0x1800078dd  lea     rax, [rbp+57h+arg_18]
0x1800078e1  mov     [rsp+0E0h+var_A0], rax
0x1800078e6  lea     rax, [rbp+57h+var_60]
0x1800078ea  mov     [rsp+0E0h+var_A8], rax
0x1800078ef  lea     rax, [rbp+57h+var_68]
0x1800078f3  mov     [rsp+0E0h+var_B0], rax
0x1800078f8  lea     rax, [rbp+57h+arg_10]
0x1800078fc  mov     [rsp+0E0h+var_B8], rax
0x180007901  lea     rax, [rbp+57h+var_70]
0x180007905  mov     [rsp+0E0h+var_C0], rax
0x18000790a  mov     [rbp+57h+var_60], r12
0x18000790e  mov     [rbp+57h+arg_10], ebx
0x180007911  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007916  mov     rcx, [rbp+57h+SecurityDescriptor]
0x18000791a  test    rcx, rcx
0x18000791d  jz      short loc_180007925
0x18000791f  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180007925  mov     rcx, [rbp+57h+var_48]
0x180007929  test    rcx, rcx
0x18000792c  jz      short loc_180007934
0x18000792e  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180007934  cmp     [rbp+57h+BindingVector], 0
0x180007939  jz      short loc_180007951
0x18000793b  lea     rcx, [rbp+57h+BindingVector]; BindingVector
0x18000793f  call    cs:__imp_RpcBindingVectorFree
0x180007945  mov     ebx, eax
0x180007947  test    eax, eax
0x180007949  jle     short loc_180007951
0x18000794b  movzx   ebx, ax
0x18000794e  or      ebx, r14d
0x180007951  mov     eax, cs:dword_180039000
0x180007957  cmp     eax, 5
0x18000795a  jbe     short loc_1800079CC
0x18000795c  call    _tlgKeywordOn
0x180007961  test    al, al
0x180007963  jz      short loc_1800079CC
0x180007965  lea     rax, aFreeRpcBinding; "Free RPC Binding Vector"
0x18000796c  mov     [rbp+57h+arg_8], 245h
0x180007973  mov     [rbp+57h+var_68], rax
0x180007977  lea     rdx, word_18002F026
0x18000797e  lea     rax, [rdi+68h]
0x180007982  mov     [rbp+57h+arg_18], r13
0x180007986  mov     [rbp+57h+var_70], rax
0x18000798a  lea     rax, [rbp+57h+arg_8]
0x18000798e  mov     [rsp+0E0h+var_98], rax
0x180007993  lea     rax, [rbp+57h+arg_18]
0x180007997  mov     [rsp+0E0h+var_A0], rax
0x18000799c  lea     rax, [rbp+57h+var_60]
0x1800079a0  mov     [rsp+0E0h+var_A8], rax
0x1800079a5  lea     rax, [rbp+57h+var_68]
0x1800079a9  mov     [rsp+0E0h+var_B0], rax
0x1800079ae  lea     rax, [rbp+57h+arg_10]
0x1800079b2  mov     [rsp+0E0h+var_B8], rax
0x1800079b7  lea     rax, [rbp+57h+var_70]
0x1800079bb  mov     [rsp+0E0h+var_C0], rax
  ... truncated ...
```
