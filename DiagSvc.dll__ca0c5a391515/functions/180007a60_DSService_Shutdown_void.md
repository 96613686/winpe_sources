# DSService::Shutdown(void)

- ea: `0x180007a60`
- end: `0x180007e32`
- name: `?Shutdown@DSService@@UEAAJXZ`
- size: `978`
- prototype: `__int64 __fastcall(DSService *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180001178`
- `0x180001720`
- `0x180007a60`

## import_xrefs

- `RPCRT4!RpcBindingVectorFree` at `0x180007cfb`
- `RPCRT4!RpcBindingVectorFree` at `0x180007cfb`
- `RPCRT4!RpcServerUnregisterIf` at `0x180007c67`
- `RPCRT4!RpcServerUnregisterIf` at `0x180007c67`
- `RPCRT4!RpcEpUnregister` at `0x180007bc0`
- `RPCRT4!RpcEpUnregister` at `0x180007bc0`
- `RPCRT4!RpcServerInqBindings` at `0x180007b0d`
- `RPCRT4!RpcServerInqBindings` at `0x180007b0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d95`

## string_xrefs

- `0x180007a77`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180007a7e`: `DSService::Shutdown`
- `0x180007a96`: `Shutting down DSService`

## pseudocode

```c
__int64 __fastcall DSService::Shutdown(DSService *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  RPC_STATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  signed int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  RPC_STATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  RPC_STATUS v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  RPC_STATUS v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  void *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  const char *v44; // [rsp+50h] [rbp-28h] BYREF
  const char *v45; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v46[3]; // [rsp+60h] [rbp-18h] BYREF
  int v47; // [rsp+B8h] [rbp+40h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+C0h] [rbp+48h] BYREF
  const char *v49; // [rsp+C8h] [rbp+50h] BYREF

  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(this, a2, a3) )
  {
    v45 = "Shutting down DSService";
    v49 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v46[0] = (char *)this + 104;
    v44 = "DSService::Shutdown";
    v47 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v4,
      (__int64)byte_18002F4F5,
      v5,
      v6,
      v46,
      (__int64)&v47,
      &v45,
      &v44,
      &v49);
  }
  BindingVector = 0;
  v7 = RpcServerInqBindings(&BindingVector);
  v11 = v7;
  if ( v7 > 0 )
    v11 = (unsigned __int16)v7 | 0x80070000;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v9, v8, v10) )
  {
    v45 = "RPC Inquire binding vector";
    v49 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v44 = (char *)this + 104;
    v46[0] = "DSService::Shutdown";
    v47 = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v12,
      (__int64)&dword_18002F48C,
      v13,
      v14,
      &v44,
      (__int64)&v47,
      &v45,
      v46,
      &v49);
  }
  if ( v11 >= 0 )
  {
    if ( *((_BYTE *)this + 57) )
    {
      v15 = RpcEpUnregister(qword_180029820, BindingVector, 0);
      v18 = (unsigned int)v15;
      if ( v15 > 0 )
        v18 = (unsigned __int16)v15 | 0x80070000;
      if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v17, v16, v18) )
      {
        v45 = "Unregister RPC Endpoint";
        v49 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
        v44 = (char *)this + 104;
        v46[0] = "DSService::Shutdown";
        v47 = v20;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (__int64)byte_18002F423,
          v20,
          v21,
          &v44,
          (__int64)&v47,
          &v45,
          v46,
          &v49);
      }
    }
    if ( *((_BYTE *)this + 56) )
    {
      v22 = RpcServerUnregisterIf(qword_180029820, 0, 1u);
      v25 = (unsigned int)v22;
      if ( v22 > 0 )
        v25 = (unsigned __int16)v22 | 0x80070000;
      if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v24, v23, v25) )
      {
        v45 = "Unregister RPC Interface";
        v49 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
        v44 = (char *)this + 104;
        v46[0] = "DSService::Shutdown";
        v47 = v27;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v26,
          (__int64)word_18002F3BA,
          v27,
          v28,
          &v44,
          (__int64)&v47,
          &v45,
          v46,
          &v49);
      }
    }
    v29 = RpcBindingVectorFree(&BindingVector);
    v11 = v29;
    if ( v29 > 0 )
      v11 = (unsigned __int16)v29 | 0x80070000;
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v31, v30, v32) )
    {
      v45 = "Free RPC Binding Vector";
      v49 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
      v44 = (char *)this + 104;
      v46[0] = "DSService::Shutdown";
      v47 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v33,
        (__int64)byte_18002F351,
        v34,
        v35,
        &v44,
        (__int64)&v47,
        &v45,
        v46,
        &v49);
    }
  }
  v36 = (void *)*((_QWORD *)this + 9);
  if ( v36 )
  {
    CloseHandle(v36);
    if ( (unsigned int)dword_180039000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(v38, v37, v39) )
      {
        v45 = "Close Handle Shutdown Event";
        v49 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
        v44 = (char *)this + 104;
        v46[0] = "DSService::Shutdown";
        v47 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v40,
          (__int64)&unk_18002F2E8,
          v41,
          v42,
          &v44,
          (__int64)&v47,
          &v45,
          v46,
          &v49);
      }
    }
  }
  *((_QWORD *)this + 9) = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180007a60  push    rbp
0x180007a62  push    rbx
0x180007a63  push    rdi
0x180007a64  push    r12
0x180007a66  push    r13
0x180007a68  push    r15
0x180007a6a  mov     rbp, rsp
0x180007a6d  sub     rsp, 78h
0x180007a71  mov     eax, cs:dword_180039000
0x180007a77  lea     r12, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180007a7e  lea     r13, aDsserviceShutd; "DSService::Shutdown"
0x180007a85  mov     rdi, rcx
0x180007a88  cmp     eax, 5
0x180007a8b  jbe     short loc_180007B01
0x180007a8d  call    _tlgKeywordOn
0x180007a92  test    al, al
0x180007a94  jz      short loc_180007B01
0x180007a96  lea     rax, aShuttingDownDs; "Shutting down DSService"
0x180007a9d  mov     [rbp+arg_0], 18Dh
0x180007aa4  mov     [rbp+var_20], rax
0x180007aa8  lea     rdx, byte_18002F4F5
0x180007aaf  lea     rax, [rdi+68h]
0x180007ab3  mov     [rbp+arg_18], r12
0x180007ab7  mov     [rbp+var_18], rax
0x180007abb  lea     rax, [rbp+arg_0]
0x180007abf  mov     [rsp+78h+var_30], rax
0x180007ac4  lea     rax, [rbp+arg_18]
0x180007ac8  mov     [rsp+78h+var_38], rax
0x180007acd  lea     rax, [rbp+var_28]
0x180007ad1  mov     [rsp+78h+var_40], rax
0x180007ad6  lea     rax, [rbp+var_20]
0x180007ada  mov     [rsp+78h+var_48], rax
0x180007adf  lea     rax, [rbp+arg_8]
0x180007ae3  mov     [rsp+78h+var_50], rax
0x180007ae8  lea     rax, [rbp+var_18]
0x180007aec  mov     [rsp+78h+var_58], rax
0x180007af1  mov     [rbp+var_28], r13
0x180007af5  mov     [rbp+arg_8], 0
0x180007afc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007b01  lea     rcx, [rbp+BindingVector]; BindingVector
0x180007b05  mov     [rbp+BindingVector], 0
0x180007b0d  call    cs:__imp_RpcServerInqBindings
0x180007b13  mov     ebx, eax
0x180007b15  mov     r15d, 80070000h
0x180007b1b  test    eax, eax
0x180007b1d  jle     short loc_180007B25
0x180007b1f  movzx   ebx, ax
0x180007b22  or      ebx, r15d
0x180007b25  mov     eax, cs:dword_180039000
0x180007b2b  cmp     eax, 5
0x180007b2e  jbe     short loc_180007BA0
0x180007b30  call    _tlgKeywordOn
0x180007b35  test    al, al
0x180007b37  jz      short loc_180007BA0
0x180007b39  lea     rax, aRpcInquireBind; "RPC Inquire binding vector"
0x180007b40  mov     [rbp+arg_0], 196h
0x180007b47  mov     [rbp+var_20], rax
0x180007b4b  lea     rdx, dword_18002F48C
0x180007b52  lea     rax, [rdi+68h]
0x180007b56  mov     [rbp+arg_18], r12
0x180007b5a  mov     [rbp+var_28], rax
0x180007b5e  lea     rax, [rbp+arg_0]
0x180007b62  mov     [rsp+78h+var_30], rax
0x180007b67  lea     rax, [rbp+arg_18]
0x180007b6b  mov     [rsp+78h+var_38], rax
0x180007b70  lea     rax, [rbp+var_18]
0x180007b74  mov     [rsp+78h+var_40], rax
0x180007b79  lea     rax, [rbp+var_20]
0x180007b7d  mov     [rsp+78h+var_48], rax
0x180007b82  lea     rax, [rbp+arg_8]
0x180007b86  mov     [rsp+78h+var_50], rax
0x180007b8b  lea     rax, [rbp+var_28]
0x180007b8f  mov     [rsp+78h+var_58], rax
0x180007b94  mov     [rbp+var_18], r13
0x180007b98  mov     [rbp+arg_8], ebx
0x180007b9b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007ba0  test    ebx, ebx
0x180007ba2  js      loc_180007D88
0x180007ba8  cmp     byte ptr [rdi+39h], 0
0x180007bac  jz      loc_180007C50
0x180007bb2  mov     rdx, [rbp+BindingVector]; BindingVector
0x180007bb6  lea     rcx, qword_180029820; IfSpec
0x180007bbd  xor     r8d, r8d; UuidVector
0x180007bc0  call    cs:__imp_RpcEpUnregister
0x180007bc6  mov     r8d, eax
0x180007bc9  test    eax, eax
0x180007bcb  jle     short loc_180007BD4
0x180007bcd  movzx   r8d, ax
0x180007bd1  or      r8d, r15d
0x180007bd4  mov     eax, cs:dword_180039000
0x180007bda  cmp     eax, 5
0x180007bdd  jbe     short loc_180007C50
0x180007bdf  call    _tlgKeywordOn
0x180007be4  test    al, al
0x180007be6  jz      short loc_180007C50
0x180007be8  lea     rax, aUnregisterRpcE; "Unregister RPC Endpoint"
0x180007bef  mov     [rbp+arg_0], 1A2h
0x180007bf6  mov     [rbp+var_20], rax
0x180007bfa  lea     rdx, byte_18002F423
0x180007c01  lea     rax, [rdi+68h]
0x180007c05  mov     [rbp+arg_18], r12
0x180007c09  mov     [rbp+var_28], rax
0x180007c0d  lea     rax, [rbp+arg_0]
0x180007c11  mov     [rsp+78h+var_30], rax
0x180007c16  lea     rax, [rbp+arg_18]
0x180007c1a  mov     [rsp+78h+var_38], rax
0x180007c1f  lea     rax, [rbp+var_18]
0x180007c23  mov     [rsp+78h+var_40], rax
0x180007c28  lea     rax, [rbp+var_20]
0x180007c2c  mov     [rsp+78h+var_48], rax
0x180007c31  lea     rax, [rbp+arg_8]
0x180007c35  mov     [rsp+78h+var_50], rax
0x180007c3a  lea     rax, [rbp+var_28]
0x180007c3e  mov     [rsp+78h+var_58], rax
0x180007c43  mov     [rbp+var_18], r13
0x180007c47  mov     [rbp+arg_8], r8d
0x180007c4b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007c50  cmp     byte ptr [rdi+38h], 0
0x180007c54  jz      loc_180007CF7
0x180007c5a  xor     edx, edx; MgrTypeUuid
0x180007c5c  lea     rcx, qword_180029820; IfSpec
0x180007c63  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x180007c67  call    cs:__imp_RpcServerUnregisterIf
0x180007c6d  mov     r8d, eax
0x180007c70  test    eax, eax
0x180007c72  jle     short loc_180007C7B
0x180007c74  movzx   r8d, ax
0x180007c78  or      r8d, r15d
0x180007c7b  mov     eax, cs:dword_180039000
0x180007c81  cmp     eax, 5
0x180007c84  jbe     short loc_180007CF7
0x180007c86  call    _tlgKeywordOn
0x180007c8b  test    al, al
0x180007c8d  jz      short loc_180007CF7
0x180007c8f  lea     rax, aUnregisterRpcI; "Unregister RPC Interface"
0x180007c96  mov     [rbp+arg_0], 1ACh
0x180007c9d  mov     [rbp+var_20], rax
0x180007ca1  lea     rdx, word_18002F3BA
0x180007ca8  lea     rax, [rdi+68h]
0x180007cac  mov     [rbp+arg_18], r12
0x180007cb0  mov     [rbp+var_28], rax
0x180007cb4  lea     rax, [rbp+arg_0]
0x180007cb8  mov     [rsp+78h+var_30], rax
0x180007cbd  lea     rax, [rbp+arg_18]
0x180007cc1  mov     [rsp+78h+var_38], rax
0x180007cc6  lea     rax, [rbp+var_18]
0x180007cca  mov     [rsp+78h+var_40], rax
0x180007ccf  lea     rax, [rbp+var_20]
0x180007cd3  mov     [rsp+78h+var_48], rax
0x180007cd8  lea     rax, [rbp+arg_8]
0x180007cdc  mov     [rsp+78h+var_50], rax
0x180007ce1  lea     rax, [rbp+var_28]
0x180007ce5  mov     [rsp+78h+var_58], rax
0x180007cea  mov     [rbp+var_18], r13
0x180007cee  mov     [rbp+arg_8], r8d
0x180007cf2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007cf7  lea     rcx, [rbp+BindingVector]; BindingVector
0x180007cfb  call    cs:__imp_RpcBindingVectorFree
0x180007d01  mov     ebx, eax
0x180007d03  test    eax, eax
0x180007d05  jle     short loc_180007D0D
0x180007d07  movzx   ebx, ax
0x180007d0a  or      ebx, r15d
0x180007d0d  mov     eax, cs:dword_180039000
0x180007d13  cmp     eax, 5
0x180007d16  jbe     short loc_180007D88
0x180007d18  call    _tlgKeywordOn
0x180007d1d  test    al, al
0x180007d1f  jz      short loc_180007D88
0x180007d21  lea     rax, aFreeRpcBinding; "Free RPC Binding Vector"
0x180007d28  mov     [rbp+arg_0], 1B5h
0x180007d2f  mov     [rbp+var_20], rax
0x180007d33  lea     rdx, byte_18002F351
0x180007d3a  lea     rax, [rdi+68h]
0x180007d3e  mov     [rbp+arg_18], r12
0x180007d42  mov     [rbp+var_28], rax
0x180007d46  lea     rax, [rbp+arg_0]
0x180007d4a  mov     [rsp+78h+var_30], rax
0x180007d4f  lea     rax, [rbp+arg_18]
0x180007d53  mov     [rsp+78h+var_38], rax
0x180007d58  lea     rax, [rbp+var_18]
0x180007d5c  mov     [rsp+78h+var_40], rax
0x180007d61  lea     rax, [rbp+var_20]
0x180007d65  mov     [rsp+78h+var_48], rax
0x180007d6a  lea     rax, [rbp+arg_8]
0x180007d6e  mov     [rsp+78h+var_50], rax
0x180007d73  lea     rax, [rbp+var_28]
0x180007d77  mov     [rsp+78h+var_58], rax
0x180007d7c  mov     [rbp+var_18], r13
0x180007d80  mov     [rbp+arg_8], ebx
0x180007d83  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007d88  mov     rcx, [rdi+48h]; hObject
0x180007d8c  test    rcx, rcx
0x180007d8f  jz      loc_180007E1A
0x180007d95  call    cs:__imp_CloseHandle
0x180007d9b  mov     eax, cs:dword_180039000
0x180007da1  cmp     eax, 5
0x180007da4  jbe     short loc_180007E1A
0x180007da6  call    _tlgKeywordOn
0x180007dab  test    al, al
0x180007dad  jz      short loc_180007E1A
0x180007daf  lea     rax, aCloseHandleShu; "Close Handle Shutdown Event"
0x180007db6  mov     [rbp+arg_0], 1BFh
0x180007dbd  mov     [rbp+var_20], rax
0x180007dc1  lea     rdx, unk_18002F2E8
0x180007dc8  lea     rax, [rdi+68h]
0x180007dcc  mov     [rbp+arg_18], r12
0x180007dd0  mov     [rbp+var_28], rax
0x180007dd4  lea     rax, [rbp+arg_0]
0x180007dd8  mov     [rsp+78h+var_30], rax
0x180007ddd  lea     rax, [rbp+arg_18]
0x180007de1  mov     [rsp+78h+var_38], rax
0x180007de6  lea     rax, [rbp+var_18]
0x180007dea  mov     [rsp+78h+var_40], rax
0x180007def  lea     rax, [rbp+var_20]
0x180007df3  mov     [rsp+78h+var_48], rax
0x180007df8  lea     rax, [rbp+arg_8]
0x180007dfc  mov     [rsp+78h+var_50], rax
0x180007e01  lea     rax, [rbp+var_28]
0x180007e05  mov     [rsp+78h+var_58], rax
0x180007e0a  mov     [rbp+var_18], r13
0x180007e0e  mov     [rbp+arg_8], 0
0x180007e15  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180007e1a  mov     qword ptr [rdi+48h], 0
0x180007e22  mov     eax, ebx
0x180007e24  add     rsp, 78h
0x180007e28  pop     r15
0x180007e2a  pop     r13
0x180007e2c  pop     r12
0x180007e2e  pop     rdi
0x180007e2f  pop     rbx
0x180007e30  pop     rbp
0x180007e31  retn
```
