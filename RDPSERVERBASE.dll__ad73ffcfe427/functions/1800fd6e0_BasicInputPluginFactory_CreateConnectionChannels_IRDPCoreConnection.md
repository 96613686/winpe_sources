# BasicInputPluginFactory::CreateConnectionChannels(IRDPCoreConnection *)

- ea: `0x1800fd6e0`
- end: `0x1800fdbce`
- name: `?CreateConnectionChannels@BasicInputPluginFactory@@UEAAJPEAUIRDPCoreConnection@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(BasicInputPluginFactory *__hidden this, struct IRDPCoreConnection *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001308`
- `0x18000202c`
- `0x18000ce04`
- `0x180075ee8`
- `0x1800fd6e0`
- `0x1800fdbd4`
- `0x1800fe360`
- `0x18019c010`

## string_xrefs

- `0x1800fd768`: `CreateConnectionChannels`
- `0x1800fd80d`: `CreateConnectionChannels`
- `0x1800fd8b0`: `CreateConnectionChannels`
- `0x1800fd948`: `CreateConnectionChannels`
- `0x1800fd9e7`: `CreateConnectionChannels`
- `0x1800fda79`: `CreateConnectionChannels`
- `0x1800fdb0f`: `CreateConnectionChannels`
- `0x1800fd773`: `onecore\termsrv\rdpplatform\rdpenc\enccore\basicinputplugin.cpp`
- `0x1800fd818`: `onecore\termsrv\rdpplatform\rdpenc\enccore\basicinputplugin.cpp`
- `0x1800fd8bb`: `onecore\termsrv\rdpplatform\rdpenc\enccore\basicinputplugin.cpp`
- `0x1800fd953`: `onecore\termsrv\rdpplatform\rdpenc\enccore\basicinputplugin.cpp`
- `0x1800fd9f2`: `onecore\termsrv\rdpplatform\rdpenc\enccore\basicinputplugin.cpp`
- `0x1800fda84`: `onecore\termsrv\rdpplatform\rdpenc\enccore\basicinputplugin.cpp`
- `0x1800fdb1a`: `onecore\termsrv\rdpplatform\rdpenc\enccore\basicinputplugin.cpp`
- `0x1800fd92f`: `Failed to create BasicInput plugin`
- `0x1800fda60`: `Failed to create BasicInput plugin`
- `0x1800fd897`: `Failed to create BasicInput channel`
- `0x1800fdb6b`: `Initialized BasicInput Plugin`
- `0x1800fdaf6`: `Failed to init BasicInput Plugin`

## pseudocode

```c
__int64 __fastcall BasicInputPluginFactory::CreateConnectionChannels(
        BasicInputPluginFactory *this,
        struct IRDPCoreConnection *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct IRDPCoreConnection *, _QWORD *); // rax
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  char *v9; // rdx
  const char **v10; // rax
  const char **v12; // [rsp+30h] [rbp-29h]
  const char **v13; // [rsp+40h] [rbp-19h]
  const char **v14; // [rsp+48h] [rbp-11h]
  const char *v15; // [rsp+50h] [rbp-9h] BYREF
  const char *v16; // [rsp+58h] [rbp-1h] BYREF
  const char *v17; // [rsp+60h] [rbp+7h] BYREF
  const char *v18; // [rsp+68h] [rbp+Fh] BYREF
  struct IRDPWDUMX_StackEx *v19; // [rsp+70h] [rbp+17h] BYREF
  struct IRDPCollection *v20; // [rsp+78h] [rbp+1Fh] BYREF
  BasicInputPlugin *v21; // [rsp+80h] [rbp+27h] BYREF
  struct IRDPCoreVirtualChannel *v22; // [rsp+88h] [rbp+2Fh] BYREF
  _QWORD v23[4]; // [rsp+90h] [rbp+37h] BYREF
  const char *v24; // [rsp+C8h] [rbp+6Fh] BYREF
  int v25; // [rsp+D0h] [rbp+77h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, GUID *, struct IRDPWDUMX_StackEx **); // [rsp+D8h] [rbp+7Fh] BYREF

  v2 = *(_QWORD *)a2;
  v23[0] = 0;
  v22 = 0;
  v21 = 0;
  v4 = *(__int64 (__fastcall **)(struct IRDPCoreConnection *, _QWORD *))(v2 + 64);
  v20 = 0;
  v19 = 0;
  v26 = 0;
  v5 = v4(a2, v23);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(struct IRDPCoreConnection *, struct IRDPCollection **))(*(_QWORD *)a2 + 80LL))(
           a2,
           &v20);
    if ( v5 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_25;
      LODWORD(v24) = 315;
      v18 = "Failed to get IRDPCollection from Connection object";
      v9 = byte_1802858F1;
      v17 = "CreateConnectionChannels";
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\basicinputplugin.cpp";
      v15 = "Error HResult failed";
      v14 = &v18;
      v13 = &v17;
      v12 = &v16;
      v10 = &v15;
      goto LABEL_4;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD, struct IRDPCoreVirtualChannel **))(*(_QWORD *)v23[0] + 24LL))(
           v23[0],
           "Microsoft::Windows::RDS::CoreInput",
           0,
           &v22);
    if ( v5 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_25;
      LODWORD(v24) = 321;
      v18 = "Failed to create BasicInput channel";
      v9 = (char *)&dword_180285944;
      v17 = "CreateConnectionChannels";
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\basicinputplugin.cpp";
      v15 = "Error HResult failed";
      v14 = &v18;
      v13 = &v17;
      v12 = &v16;
      v10 = &v15;
      goto LABEL_4;
    }
    v5 = (*(__int64 (__fastcall **)(struct IRDPCoreConnection *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IRDPWDUMX_StackEx **)))(*(_QWORD *)a2 + 88LL))(
           a2,
           &v26);
    if ( v5 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_25;
      LODWORD(v24) = 324;
      v18 = "Failed to create BasicInput plugin";
      v9 = (char *)&word_18028589E;
      v17 = "CreateConnectionChannels";
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\basicinputplugin.cpp";
      v15 = "Error HResult failed";
      v14 = &v18;
      v13 = &v17;
      v12 = &v16;
      v10 = &v15;
      goto LABEL_4;
    }
    v5 = (**v26)(v26, &IID_IRDPWDUMX_StackEx, &v19);
    if ( v5 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_25;
      LODWORD(v24) = 327;
      v18 = "Failed to QI";
      v9 = (char *)&unk_1802857F8;
      v17 = "CreateConnectionChannels";
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\basicinputplugin.cpp";
      v15 = "Error HResult failed";
      v14 = &v18;
      v13 = &v17;
      v12 = &v16;
      v10 = &v15;
      goto LABEL_4;
    }
    v5 = BasicInputPlugin::CreateInstance(v19, &v21);
    if ( v5 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_25;
      LODWORD(v24) = 333;
      v18 = "Failed to create BasicInput plugin";
      v9 = byte_18028584B;
      v17 = "CreateConnectionChannels";
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\basicinputplugin.cpp";
      v15 = "Error HResult failed";
      v14 = &v18;
      v13 = &v17;
      v12 = &v16;
      v10 = &v15;
      goto LABEL_4;
    }
    v5 = BasicInputPlugin::InitializeInstance(v21, v22, v20);
    if ( v5 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_25;
      LODWORD(v24) = 336;
      v18 = "Failed to init BasicInput Plugin";
      v9 = (char *)&word_18028577E;
      v17 = "CreateConnectionChannels";
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\basicinputplugin.cpp";
      v15 = "Error HResult failed";
      v14 = &v18;
      v13 = &v17;
      v12 = &v16;
      v10 = &v15;
      goto LABEL_4;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v24 = "Initialized BasicInput Plugin";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v8,
        (unsigned int)byte_1802857D1,
        v6,
        v7,
        (__int64)&v24);
    }
  }
  else
  {
    v8 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v24) = 312;
      v15 = "Failed to get VC Mgr";
      v9 = &byte_180285997;
      v16 = "CreateConnectionChannels";
      v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\basicinputplugin.cpp";
      v18 = "Error HResult failed";
      v14 = &v15;
      v13 = &v16;
      v12 = &v17;
      v10 = &v18;
LABEL_4:
      v25 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v8,
        (_DWORD)v9,
        v6,
        v7,
        (__int64)v10,
        (__int64)&v25,
        (__int64)v12,
        (__int64)&v24,
        (__int64)v13,
        (__int64)v14);
    }
  }
LABEL_25:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v26);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v19);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v20);
  TCntPtr<PipeETWEvents>::SafeRelease(&v21);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v22);
  TCntPtr<IRdpVCMgr>::SafeRelease(v23);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800fd6e0  push    rbp
0x1800fd6e2  push    rbx
0x1800fd6e3  push    rdi
0x1800fd6e4  lea     rbp, [rsp-47h]
0x1800fd6e9  sub     rsp, 0A0h
0x1800fd6f0  mov     rax, [rdx]
0x1800fd6f3  mov     rdi, rdx
0x1800fd6f6  lea     rdx, [rbp+57h+var_20]
0x1800fd6fa  mov     [rbp+57h+var_20], 0
0x1800fd702  mov     rcx, rdi
0x1800fd705  mov     [rbp+57h+var_28], 0
0x1800fd70d  mov     [rbp+57h+var_30], 0
0x1800fd715  mov     rax, [rax+40h]
0x1800fd719  mov     [rbp+57h+var_38], 0
0x1800fd721  mov     [rbp+57h+var_40], 0
0x1800fd729  mov     [rbp+57h+arg_18], 0
0x1800fd731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd736  mov     ebx, eax
0x1800fd738  test    eax, eax
0x1800fd73a  jns     loc_1800FD7CC
0x1800fd740  mov     ecx, cs:CallbackContext
0x1800fd746  cmp     ecx, 2
0x1800fd749  jbe     loc_1800FDB8B
0x1800fd74f  lea     rax, aFailedToGetVcM; "Failed to get VC Mgr"
0x1800fd756  mov     dword ptr [rbp+57h+arg_8], 138h
0x1800fd75d  mov     [rbp+57h+var_60], rax
0x1800fd761  lea     rdx, byte_180285997
0x1800fd768  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800fd76f  mov     [rbp+57h+var_58], rax
0x1800fd773  lea     rax, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fd77a  mov     [rbp+57h+var_50], rax
0x1800fd77e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800fd785  mov     [rbp+57h+var_48], rax
0x1800fd789  lea     rax, [rbp+57h+var_60]
0x1800fd78d  mov     [rsp+0B0h+var_68], rax
0x1800fd792  lea     rax, [rbp+57h+var_58]
0x1800fd796  mov     [rsp+0B0h+var_70], rax
0x1800fd79b  lea     rax, [rbp+57h+arg_8]
0x1800fd79f  mov     [rsp+0B0h+var_78], rax
0x1800fd7a4  lea     rax, [rbp+57h+var_50]
0x1800fd7a8  mov     [rsp+0B0h+var_80], rax
0x1800fd7ad  lea     rax, [rbp+57h+arg_10]
0x1800fd7b1  mov     [rsp+0B0h+var_88], rax
0x1800fd7b6  lea     rax, [rbp+57h+var_48]
0x1800fd7ba  mov     [rbp+57h+arg_10], ebx
0x1800fd7bd  mov     [rsp+0B0h+var_90], rax
0x1800fd7c2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800fd7c7  jmp     loc_1800FDB8B
0x1800fd7cc  mov     rax, [rdi]
0x1800fd7cf  lea     rdx, [rbp+57h+var_38]
0x1800fd7d3  mov     rcx, rdi
0x1800fd7d6  mov     rax, [rax+50h]
0x1800fd7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd7df  mov     ebx, eax
0x1800fd7e1  test    eax, eax
0x1800fd7e3  jns     short loc_1800FD864
0x1800fd7e5  mov     eax, cs:CallbackContext
0x1800fd7eb  cmp     eax, 2
0x1800fd7ee  jbe     loc_1800FDB8B
0x1800fd7f4  lea     rax, aFailedToGetIrd_0; "Failed to get IRDPCollection from Conne"...
0x1800fd7fb  mov     dword ptr [rbp+57h+arg_8], 13Bh
0x1800fd802  mov     [rbp+57h+var_48], rax
0x1800fd806  lea     rdx, byte_1802858F1
0x1800fd80d  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800fd814  mov     [rbp+57h+var_50], rax
0x1800fd818  lea     rax, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fd81f  mov     [rbp+57h+var_58], rax
0x1800fd823  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800fd82a  mov     [rbp+57h+var_60], rax
0x1800fd82e  lea     rax, [rbp+57h+var_48]
0x1800fd832  mov     [rsp+0B0h+var_68], rax
0x1800fd837  lea     rax, [rbp+57h+var_50]
0x1800fd83b  mov     [rsp+0B0h+var_70], rax
0x1800fd840  lea     rax, [rbp+57h+arg_8]
0x1800fd844  mov     [rsp+0B0h+var_78], rax
0x1800fd849  lea     rax, [rbp+57h+var_58]
0x1800fd84d  mov     [rsp+0B0h+var_80], rax
0x1800fd852  lea     rax, [rbp+57h+arg_10]
0x1800fd856  mov     [rsp+0B0h+var_88], rax
0x1800fd85b  lea     rax, [rbp+57h+var_60]
0x1800fd85f  jmp     loc_1800FD7BA
0x1800fd864  mov     rcx, [rbp+57h+var_20]
0x1800fd868  lea     r9, [rbp+57h+var_28]
0x1800fd86c  xor     r8d, r8d
0x1800fd86f  lea     rdx, aMicrosoftWindo_1; "Microsoft::Windows::RDS::CoreInput"
0x1800fd876  mov     rax, [rcx]
0x1800fd879  mov     rax, [rax+18h]
0x1800fd87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd882  mov     ebx, eax
0x1800fd884  test    eax, eax
0x1800fd886  jns     short loc_1800FD907
0x1800fd888  mov     eax, cs:CallbackContext
0x1800fd88e  cmp     eax, 2
0x1800fd891  jbe     loc_1800FDB8B
0x1800fd897  lea     rax, aFailedToCreate_44; "Failed to create BasicInput channel"
0x1800fd89e  mov     dword ptr [rbp+57h+arg_8], 141h
0x1800fd8a5  mov     [rbp+57h+var_48], rax
0x1800fd8a9  lea     rdx, dword_180285944
0x1800fd8b0  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800fd8b7  mov     [rbp+57h+var_50], rax
0x1800fd8bb  lea     rax, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fd8c2  mov     [rbp+57h+var_58], rax
0x1800fd8c6  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800fd8cd  mov     [rbp+57h+var_60], rax
0x1800fd8d1  lea     rax, [rbp+57h+var_48]
0x1800fd8d5  mov     [rsp+0B0h+var_68], rax
0x1800fd8da  lea     rax, [rbp+57h+var_50]
0x1800fd8de  mov     [rsp+0B0h+var_70], rax
0x1800fd8e3  lea     rax, [rbp+57h+arg_8]
0x1800fd8e7  mov     [rsp+0B0h+var_78], rax
0x1800fd8ec  lea     rax, [rbp+57h+var_58]
0x1800fd8f0  mov     [rsp+0B0h+var_80], rax
0x1800fd8f5  lea     rax, [rbp+57h+arg_10]
0x1800fd8f9  mov     [rsp+0B0h+var_88], rax
0x1800fd8fe  lea     rax, [rbp+57h+var_60]
0x1800fd902  jmp     loc_1800FD7BA
0x1800fd907  mov     rax, [rdi]
0x1800fd90a  lea     rdx, [rbp+57h+arg_18]
0x1800fd90e  mov     rcx, rdi
0x1800fd911  mov     rax, [rax+58h]
0x1800fd915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd91a  mov     ebx, eax
0x1800fd91c  test    eax, eax
0x1800fd91e  jns     short loc_1800FD99F
0x1800fd920  mov     eax, cs:CallbackContext
0x1800fd926  cmp     eax, 2
0x1800fd929  jbe     loc_1800FDB8B
0x1800fd92f  lea     rax, aFailedToCreate_19; "Failed to create BasicInput plugin"
0x1800fd936  mov     dword ptr [rbp+57h+arg_8], 144h
0x1800fd93d  mov     [rbp+57h+var_48], rax
0x1800fd941  lea     rdx, word_18028589E
0x1800fd948  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800fd94f  mov     [rbp+57h+var_50], rax
0x1800fd953  lea     rax, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fd95a  mov     [rbp+57h+var_58], rax
0x1800fd95e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800fd965  mov     [rbp+57h+var_60], rax
0x1800fd969  lea     rax, [rbp+57h+var_48]
0x1800fd96d  mov     [rsp+0B0h+var_68], rax
0x1800fd972  lea     rax, [rbp+57h+var_50]
0x1800fd976  mov     [rsp+0B0h+var_70], rax
0x1800fd97b  lea     rax, [rbp+57h+arg_8]
0x1800fd97f  mov     [rsp+0B0h+var_78], rax
0x1800fd984  lea     rax, [rbp+57h+var_58]
0x1800fd988  mov     [rsp+0B0h+var_80], rax
0x1800fd98d  lea     rax, [rbp+57h+arg_10]
0x1800fd991  mov     [rsp+0B0h+var_88], rax
0x1800fd996  lea     rax, [rbp+57h+var_60]
0x1800fd99a  jmp     loc_1800FD7BA
0x1800fd99f  mov     rcx, [rbp+57h+arg_18]
0x1800fd9a3  lea     r8, [rbp+57h+var_40]
0x1800fd9a7  lea     rdx, IID_IRDPWDUMX_StackEx
0x1800fd9ae  mov     rax, [rcx]
0x1800fd9b1  mov     rax, [rax]
0x1800fd9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd9b9  mov     ebx, eax
0x1800fd9bb  test    eax, eax
0x1800fd9bd  jns     short loc_1800FDA3E
0x1800fd9bf  mov     eax, cs:CallbackContext
0x1800fd9c5  cmp     eax, 2
0x1800fd9c8  jbe     loc_1800FDB8B
0x1800fd9ce  lea     rax, aFailedToQi; "Failed to QI"
0x1800fd9d5  mov     dword ptr [rbp+57h+arg_8], 147h
0x1800fd9dc  mov     [rbp+57h+var_48], rax
0x1800fd9e0  lea     rdx, unk_1802857F8
0x1800fd9e7  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800fd9ee  mov     [rbp+57h+var_50], rax
0x1800fd9f2  lea     rax, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fd9f9  mov     [rbp+57h+var_58], rax
0x1800fd9fd  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800fda04  mov     [rbp+57h+var_60], rax
0x1800fda08  lea     rax, [rbp+57h+var_48]
0x1800fda0c  mov     [rsp+0B0h+var_68], rax
0x1800fda11  lea     rax, [rbp+57h+var_50]
0x1800fda15  mov     [rsp+0B0h+var_70], rax
0x1800fda1a  lea     rax, [rbp+57h+arg_8]
0x1800fda1e  mov     [rsp+0B0h+var_78], rax
0x1800fda23  lea     rax, [rbp+57h+var_58]
0x1800fda27  mov     [rsp+0B0h+var_80], rax
0x1800fda2c  lea     rax, [rbp+57h+arg_10]
0x1800fda30  mov     [rsp+0B0h+var_88], rax
0x1800fda35  lea     rax, [rbp+57h+var_60]
0x1800fda39  jmp     loc_1800FD7BA
0x1800fda3e  mov     rcx, [rbp+57h+var_40]; struct IRDPWDUMX_StackEx *
0x1800fda42  lea     rdx, [rbp+57h+var_30]; struct BasicInputPlugin **
0x1800fda46  call    ?CreateInstance@BasicInputPlugin@@SAJPEAUIRDPWDUMX_StackEx@@PEAPEAV1@@Z; BasicInputPlugin::CreateInstance(IRDPWDUMX_StackEx *,BasicInputPlugin * *)
0x1800fda4b  mov     ebx, eax
0x1800fda4d  test    eax, eax
0x1800fda4f  jns     short loc_1800FDAD0
0x1800fda51  mov     eax, cs:CallbackContext
0x1800fda57  cmp     eax, 2
0x1800fda5a  jbe     loc_1800FDB8B
0x1800fda60  lea     rax, aFailedToCreate_19; "Failed to create BasicInput plugin"
0x1800fda67  mov     dword ptr [rbp+57h+arg_8], 14Dh
0x1800fda6e  mov     [rbp+57h+var_48], rax
0x1800fda72  lea     rdx, byte_18028584B
0x1800fda79  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800fda80  mov     [rbp+57h+var_50], rax
0x1800fda84  lea     rax, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fda8b  mov     [rbp+57h+var_58], rax
0x1800fda8f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800fda96  mov     [rbp+57h+var_60], rax
0x1800fda9a  lea     rax, [rbp+57h+var_48]
0x1800fda9e  mov     [rsp+0B0h+var_68], rax
0x1800fdaa3  lea     rax, [rbp+57h+var_50]
0x1800fdaa7  mov     [rsp+0B0h+var_70], rax
0x1800fdaac  lea     rax, [rbp+57h+arg_8]
0x1800fdab0  mov     [rsp+0B0h+var_78], rax
0x1800fdab5  lea     rax, [rbp+57h+var_58]
0x1800fdab9  mov     [rsp+0B0h+var_80], rax
0x1800fdabe  lea     rax, [rbp+57h+arg_10]
0x1800fdac2  mov     [rsp+0B0h+var_88], rax
0x1800fdac7  lea     rax, [rbp+57h+var_60]
0x1800fdacb  jmp     loc_1800FD7BA
0x1800fdad0  mov     r8, [rbp+57h+var_38]; struct IRDPCollection *
0x1800fdad4  mov     rdx, [rbp+57h+var_28]; struct IRDPCoreVirtualChannel *
0x1800fdad8  mov     rcx, [rbp+57h+var_30]; this
0x1800fdadc  call    ?InitializeInstance@BasicInputPlugin@@UEAAJPEAUIRDPCoreVirtualChannel@@PEAUIRDPCollection@@@Z; BasicInputPlugin::InitializeInstance(IRDPCoreVirtualChannel *,IRDPCollection *)
0x1800fdae1  mov     ebx, eax
0x1800fdae3  test    eax, eax
0x1800fdae5  mov     eax, cs:CallbackContext
0x1800fdaeb  jns     short loc_1800FDB66
0x1800fdaed  cmp     eax, 2
0x1800fdaf0  jbe     loc_1800FDB8B
0x1800fdaf6  lea     rax, aFailedToInitBa; "Failed to init BasicInput Plugin"
0x1800fdafd  mov     dword ptr [rbp+57h+arg_8], 150h
0x1800fdb04  mov     [rbp+57h+var_48], rax
0x1800fdb08  lea     rdx, word_18028577E
0x1800fdb0f  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800fdb16  mov     [rbp+57h+var_50], rax
0x1800fdb1a  lea     rax, aOnecoreTermsrv_15; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fdb21  mov     [rbp+57h+var_58], rax
0x1800fdb25  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800fdb2c  mov     [rbp+57h+var_60], rax
0x1800fdb30  lea     rax, [rbp+57h+var_48]
0x1800fdb34  mov     [rsp+0B0h+var_68], rax
0x1800fdb39  lea     rax, [rbp+57h+var_50]
0x1800fdb3d  mov     [rsp+0B0h+var_70], rax
0x1800fdb42  lea     rax, [rbp+57h+arg_8]
0x1800fdb46  mov     [rsp+0B0h+var_78], rax
0x1800fdb4b  lea     rax, [rbp+57h+var_58]
0x1800fdb4f  mov     [rsp+0B0h+var_80], rax
0x1800fdb54  lea     rax, [rbp+57h+arg_10]
0x1800fdb58  mov     [rsp+0B0h+var_88], rax
0x1800fdb5d  lea     rax, [rbp+57h+var_60]
0x1800fdb61  jmp     loc_1800FD7BA
0x1800fdb66  cmp     eax, 4
0x1800fdb69  jbe     short loc_1800FDB8B
0x1800fdb6b  lea     rax, aInitializedBas; "Initialized BasicInput Plugin"
0x1800fdb72  mov     [rbp+57h+arg_8], rax
0x1800fdb76  lea     rdx, byte_1802857D1
0x1800fdb7d  lea     rax, [rbp+57h+arg_8]
0x1800fdb81  mov     [rsp+0B0h+var_90], rax
0x1800fdb86  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800fdb8b  lea     rcx, [rbp+57h+arg_18]
0x1800fdb8f  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800fdb94  lea     rcx, [rbp+57h+var_40]
0x1800fdb98  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800fdb9d  lea     rcx, [rbp+57h+var_38]
0x1800fdba1  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800fdba6  lea     rcx, [rbp+57h+var_30]
0x1800fdbaa  call    ?SafeRelease@?$TCntPtr@VPipeETWEvents@@@@AEAAXXZ; TCntPtr<PipeETWEvents>::SafeRelease(void)
0x1800fdbaf  lea     rcx, [rbp+57h+var_28]
0x1800fdbb3  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800fdbb8  lea     rcx, [rbp+57h+var_20]
0x1800fdbbc  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800fdbc1  mov     eax, ebx
0x1800fdbc3  add     rsp, 0A0h
0x1800fdbca  pop     rdi
0x1800fdbcb  pop     rbx
0x1800fdbcc  pop     rbp
0x1800fdbcd  retn
```
