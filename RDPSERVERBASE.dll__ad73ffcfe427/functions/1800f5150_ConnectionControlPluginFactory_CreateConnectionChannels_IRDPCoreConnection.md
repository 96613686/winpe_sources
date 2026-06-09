# ConnectionControlPluginFactory::CreateConnectionChannels(IRDPCoreConnection *)

- ea: `0x1800f5150`
- end: `0x1800f5705`
- name: `?CreateConnectionChannels@ConnectionControlPluginFactory@@UEAAJPEAUIRDPCoreConnection@@@Z`
- size: `1461`
- prototype: `__int64 __fastcall(ConnectionControlPluginFactory *__hidden this, struct IRDPCoreConnection *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180001308`
- `0x18000202c`
- `0x18000ce04`
- `0x18004cde4`
- `0x1800f5150`
- `0x1800f570c`
- `0x1800f5cd0`
- `0x18019c010`

## string_xrefs

- `0x1800f51eb`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f5297`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f533d`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f53d5`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f546d`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f550c`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f559e`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f5634`: `onecore\termsrv\rdpplatform\rdpenc\enccore\connectioncontrolplugin.cpp`
- `0x1800f51e0`: `CreateConnectionChannels`
- `0x1800f528c`: `CreateConnectionChannels`
- `0x1800f5332`: `CreateConnectionChannels`
- `0x1800f53ca`: `CreateConnectionChannels`
- `0x1800f5462`: `CreateConnectionChannels`
- `0x1800f5501`: `CreateConnectionChannels`
- `0x1800f5593`: `CreateConnectionChannels`
- `0x1800f5629`: `CreateConnectionChannels`
- `0x1800f5319`: `Failed to create ConnectionControl channel`
- `0x1800f5610`: `Failed to init ConnectionControl Plugin`
- `0x1800f5449`: `Failed to create ConnectionControl plugin`
- `0x1800f557a`: `Failed to create ConnectionControl plugin`
- `0x1800f5685`: `Initialized ConnectionControl Plugin`

## pseudocode

```c
__int64 __fastcall ConnectionControlPluginFactory::CreateConnectionChannels(
        ConnectionControlPluginFactory *this,
        struct IRDPCoreConnection *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct IRDPCoreConnection *, _QWORD *); // rax
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  __int16 *v9; // rdx
  const char **v10; // rax
  __int64 v11; // rcx
  const char **v13; // [rsp+30h] [rbp-29h]
  const char **v14; // [rsp+40h] [rbp-19h]
  const char **v15; // [rsp+48h] [rbp-11h]
  const char *v16; // [rsp+50h] [rbp-9h] BYREF
  const char *v17; // [rsp+58h] [rbp-1h] BYREF
  const char *v18; // [rsp+60h] [rbp+7h] BYREF
  const char *v19; // [rsp+68h] [rbp+Fh] BYREF
  __int64 (__fastcall ***v20)(_QWORD, GUID *, struct IRDPWDUMX_StackEx **); // [rsp+70h] [rbp+17h] BYREF
  struct IRDPWDUMX_StackEx *v21; // [rsp+78h] [rbp+1Fh] BYREF
  struct IRDPCollection *v22; // [rsp+80h] [rbp+27h] BYREF
  ConnectionControlPlugin *v23; // [rsp+88h] [rbp+2Fh] BYREF
  struct IRDPCoreVirtualChannel *v24; // [rsp+90h] [rbp+37h] BYREF
  _QWORD v25[3]; // [rsp+98h] [rbp+3Fh] BYREF
  const char *v26; // [rsp+C8h] [rbp+6Fh] BYREF
  int v27; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+7Fh] BYREF

  v2 = *(_QWORD *)a2;
  v25[0] = 0;
  v28 = 0;
  v24 = 0;
  v4 = *(__int64 (__fastcall **)(struct IRDPCoreConnection *, _QWORD *))(v2 + 64);
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v5 = v4(a2, v25);
  if ( v5 < 0 )
  {
    v8 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_28;
    LODWORD(v26) = 1013;
    v16 = "Failed to get VC Mgr";
    v9 = (__int16 *)&unk_1802839D0;
    v17 = "CreateConnectionChannels";
    v18 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
    v19 = "Error HResult failed";
    v15 = &v16;
    v14 = &v17;
    v13 = &v18;
    v10 = &v19;
    goto LABEL_4;
  }
  v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v25[0])(v25[0], &IID_IRDPCoreChannelManagerEx, &v28);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, const char *, __int64, struct IRDPCoreVirtualChannel **))(*(_QWORD *)v28 + 24LL))(
           v28,
           "conctrl",
           6,
           &v24);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(struct IRDPCoreConnection *, struct IRDPCollection **))(*(_QWORD *)a2 + 80LL))(
             a2,
             &v22);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(struct IRDPCoreConnection *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IRDPWDUMX_StackEx **)))(*(_QWORD *)a2 + 88LL))(
               a2,
               &v20);
        if ( v5 >= 0 )
        {
          v5 = (**v20)(v20, &IID_IRDPWDUMX_StackEx, &v21);
          if ( v5 >= 0 )
          {
            v5 = ConnectionControlPlugin::CreateInstance(v21, &v23);
            if ( v5 >= 0 )
            {
              v5 = ConnectionControlPlugin::InitializeInstance(v23, v24, v22);
              if ( v5 >= 0 )
              {
                if ( (unsigned int)CallbackContext > 5 )
                {
                  v26 = "Initialized ConnectionControl Plugin";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                    v8,
                    (unsigned int)&word_180283786,
                    v6,
                    v7,
                    (__int64)&v26);
                }
              }
              else if ( (unsigned int)CallbackContext > 2 )
              {
                LODWORD(v26) = 1045;
                v19 = "Failed to init ConnectionControl Plugin";
                v9 = (__int16 *)&dword_18028372C;
                v18 = "CreateConnectionChannels";
                v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
                v16 = "Error HResult failed";
                v15 = &v19;
                v14 = &v18;
                v13 = &v17;
                v10 = &v16;
                goto LABEL_4;
              }
            }
            else if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v26) = 1042;
              v19 = "Failed to create ConnectionControl plugin";
              v9 = &word_18028380E;
              v18 = "CreateConnectionChannels";
              v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
              v16 = "Error HResult failed";
              v15 = &v19;
              v14 = &v18;
              v13 = &v17;
              v10 = &v16;
              goto LABEL_4;
            }
          }
          else if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v26) = 1036;
            v19 = "Failed to QI";
            v9 = (__int16 *)&dword_1802837B4;
            v18 = "CreateConnectionChannels";
            v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
            v16 = "Error HResult failed";
            v15 = &v19;
            v14 = &v18;
            v13 = &v17;
            v10 = &v16;
            goto LABEL_4;
          }
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v26) = 1033;
          v19 = "Failed to create ConnectionControl plugin";
          v9 = (__int16 *)&unk_180283868;
          v18 = "CreateConnectionChannels";
          v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
          v16 = "Error HResult failed";
          v15 = &v19;
          v14 = &v18;
          v13 = &v17;
          v10 = &v16;
          goto LABEL_4;
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v26) = 1030;
        v19 = "Failed to get IRDPCollection from Connection object";
        v9 = (__int16 *)&dword_18028391C;
        v18 = "CreateConnectionChannels";
        v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
        v16 = "Error HResult failed";
        v15 = &v19;
        v14 = &v18;
        v13 = &v17;
        v10 = &v16;
        goto LABEL_4;
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v26) = 1027;
      v19 = "Failed to create ConnectionControl channel";
      v9 = word_1802838C2;
      v18 = "CreateConnectionChannels";
      v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
      v16 = "Error HResult failed";
      v15 = &v19;
      v14 = &v18;
      v13 = &v17;
      v10 = &v16;
      goto LABEL_4;
    }
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v26) = 1016;
    v19 = "Failed to QI";
    v9 = &word_180283976;
    v18 = "CreateConnectionChannels";
    v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\connectioncontrolplugin.cpp";
    v16 = "Error HResult failed";
    v15 = &v19;
    v14 = &v18;
    v13 = &v17;
    v10 = &v16;
LABEL_4:
    v27 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v8,
      (_DWORD)v9,
      v6,
      v7,
      (__int64)v10,
      (__int64)&v27,
      (__int64)v13,
      (__int64)&v26,
      (__int64)v14,
      (__int64)v15);
  }
LABEL_28:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v20);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v21);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v22);
  TCntPtr<ConnectionControlPlugin>::SafeRelease(&v23);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v24);
  v11 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(v25);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800f5150  push    rbp
0x1800f5152  push    rbx
0x1800f5153  push    rdi
0x1800f5154  lea     rbp, [rsp-47h]
0x1800f5159  sub     rsp, 0A0h
0x1800f5160  mov     rax, [rdx]
0x1800f5163  mov     rdi, rdx
0x1800f5166  lea     rdx, [rbp+57h+var_18]
0x1800f516a  mov     [rbp+57h+var_18], 0
0x1800f5172  mov     rcx, rdi
0x1800f5175  mov     [rbp+57h+arg_18], 0
0x1800f517d  mov     [rbp+57h+var_20], 0
0x1800f5185  mov     rax, [rax+40h]
0x1800f5189  mov     [rbp+57h+var_28], 0
0x1800f5191  mov     [rbp+57h+var_30], 0
0x1800f5199  mov     [rbp+57h+var_38], 0
0x1800f51a1  mov     [rbp+57h+var_40], 0
0x1800f51a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f51ae  mov     ebx, eax
0x1800f51b0  test    eax, eax
0x1800f51b2  jns     loc_1800F5244
0x1800f51b8  mov     ecx, cs:CallbackContext
0x1800f51be  cmp     ecx, 2
0x1800f51c1  jbe     loc_1800F56A5
0x1800f51c7  lea     rax, aFailedToGetVcM; "Failed to get VC Mgr"
0x1800f51ce  mov     dword ptr [rbp+57h+arg_8], 3F5h
0x1800f51d5  mov     [rbp+57h+var_60], rax
0x1800f51d9  lea     rdx, unk_1802839D0
0x1800f51e0  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800f51e7  mov     [rbp+57h+var_58], rax
0x1800f51eb  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f51f2  mov     [rbp+57h+var_50], rax
0x1800f51f6  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f51fd  mov     [rbp+57h+var_48], rax
0x1800f5201  lea     rax, [rbp+57h+var_60]
0x1800f5205  mov     [rsp+0B0h+var_68], rax
0x1800f520a  lea     rax, [rbp+57h+var_58]
0x1800f520e  mov     [rsp+0B0h+var_70], rax
0x1800f5213  lea     rax, [rbp+57h+arg_8]
0x1800f5217  mov     [rsp+0B0h+var_78], rax
0x1800f521c  lea     rax, [rbp+57h+var_50]
0x1800f5220  mov     [rsp+0B0h+var_80], rax
0x1800f5225  lea     rax, [rbp+57h+arg_10]
0x1800f5229  mov     [rsp+0B0h+var_88], rax
0x1800f522e  lea     rax, [rbp+57h+var_48]
0x1800f5232  mov     [rsp+0B0h+var_90], rax
0x1800f5237  mov     [rbp+57h+arg_10], ebx
0x1800f523a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800f523f  jmp     loc_1800F56A5
0x1800f5244  mov     rcx, [rbp+57h+var_18]
0x1800f5248  lea     r8, [rbp+57h+arg_18]
0x1800f524c  lea     rdx, IID_IRDPCoreChannelManagerEx
0x1800f5253  mov     rax, [rcx]
0x1800f5256  mov     rax, [rax]
0x1800f5259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f525e  mov     ebx, eax
0x1800f5260  test    eax, eax
0x1800f5262  jns     short loc_1800F52E3
0x1800f5264  mov     eax, cs:CallbackContext
0x1800f526a  cmp     eax, 2
0x1800f526d  jbe     loc_1800F56A5
0x1800f5273  lea     rax, aFailedToQi; "Failed to QI"
0x1800f527a  mov     dword ptr [rbp+57h+arg_8], 3F8h
0x1800f5281  mov     [rbp+57h+var_48], rax
0x1800f5285  lea     rdx, word_180283976
0x1800f528c  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800f5293  mov     [rbp+57h+var_50], rax
0x1800f5297  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f529e  mov     [rbp+57h+var_58], rax
0x1800f52a2  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f52a9  mov     [rbp+57h+var_60], rax
0x1800f52ad  lea     rax, [rbp+57h+var_48]
0x1800f52b1  mov     [rsp+0B0h+var_68], rax
0x1800f52b6  lea     rax, [rbp+57h+var_50]
0x1800f52ba  mov     [rsp+0B0h+var_70], rax
0x1800f52bf  lea     rax, [rbp+57h+arg_8]
0x1800f52c3  mov     [rsp+0B0h+var_78], rax
0x1800f52c8  lea     rax, [rbp+57h+var_58]
0x1800f52cc  mov     [rsp+0B0h+var_80], rax
0x1800f52d1  lea     rax, [rbp+57h+arg_10]
0x1800f52d5  mov     [rsp+0B0h+var_88], rax
0x1800f52da  lea     rax, [rbp+57h+var_60]
0x1800f52de  jmp     loc_1800F5232
0x1800f52e3  mov     rcx, [rbp+57h+arg_18]
0x1800f52e7  lea     r9, [rbp+57h+var_20]
0x1800f52eb  mov     r8d, 6
0x1800f52f1  lea     rdx, String1; "conctrl"
0x1800f52f8  mov     rax, [rcx]
0x1800f52fb  mov     rax, [rax+18h]
0x1800f52ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5304  mov     ebx, eax
0x1800f5306  test    eax, eax
0x1800f5308  jns     short loc_1800F5389
0x1800f530a  mov     eax, cs:CallbackContext
0x1800f5310  cmp     eax, 2
0x1800f5313  jbe     loc_1800F56A5
0x1800f5319  lea     rax, aFailedToCreate_34; "Failed to create ConnectionControl chan"...
0x1800f5320  mov     dword ptr [rbp+57h+arg_8], 403h
0x1800f5327  mov     [rbp+57h+var_48], rax
0x1800f532b  lea     rdx, word_1802838C2
0x1800f5332  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800f5339  mov     [rbp+57h+var_50], rax
0x1800f533d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f5344  mov     [rbp+57h+var_58], rax
0x1800f5348  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f534f  mov     [rbp+57h+var_60], rax
0x1800f5353  lea     rax, [rbp+57h+var_48]
0x1800f5357  mov     [rsp+0B0h+var_68], rax
0x1800f535c  lea     rax, [rbp+57h+var_50]
0x1800f5360  mov     [rsp+0B0h+var_70], rax
0x1800f5365  lea     rax, [rbp+57h+arg_8]
0x1800f5369  mov     [rsp+0B0h+var_78], rax
0x1800f536e  lea     rax, [rbp+57h+var_58]
0x1800f5372  mov     [rsp+0B0h+var_80], rax
0x1800f5377  lea     rax, [rbp+57h+arg_10]
0x1800f537b  mov     [rsp+0B0h+var_88], rax
0x1800f5380  lea     rax, [rbp+57h+var_60]
0x1800f5384  jmp     loc_1800F5232
0x1800f5389  mov     rax, [rdi]
0x1800f538c  lea     rdx, [rbp+57h+var_30]
0x1800f5390  mov     rcx, rdi
0x1800f5393  mov     rax, [rax+50h]
0x1800f5397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f539c  mov     ebx, eax
0x1800f539e  test    eax, eax
0x1800f53a0  jns     short loc_1800F5421
0x1800f53a2  mov     eax, cs:CallbackContext
0x1800f53a8  cmp     eax, 2
0x1800f53ab  jbe     loc_1800F56A5
0x1800f53b1  lea     rax, aFailedToGetIrd_0; "Failed to get IRDPCollection from Conne"...
0x1800f53b8  mov     dword ptr [rbp+57h+arg_8], 406h
0x1800f53bf  mov     [rbp+57h+var_48], rax
0x1800f53c3  lea     rdx, dword_18028391C
0x1800f53ca  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800f53d1  mov     [rbp+57h+var_50], rax
0x1800f53d5  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f53dc  mov     [rbp+57h+var_58], rax
0x1800f53e0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f53e7  mov     [rbp+57h+var_60], rax
0x1800f53eb  lea     rax, [rbp+57h+var_48]
0x1800f53ef  mov     [rsp+0B0h+var_68], rax
0x1800f53f4  lea     rax, [rbp+57h+var_50]
0x1800f53f8  mov     [rsp+0B0h+var_70], rax
0x1800f53fd  lea     rax, [rbp+57h+arg_8]
0x1800f5401  mov     [rsp+0B0h+var_78], rax
0x1800f5406  lea     rax, [rbp+57h+var_58]
0x1800f540a  mov     [rsp+0B0h+var_80], rax
0x1800f540f  lea     rax, [rbp+57h+arg_10]
0x1800f5413  mov     [rsp+0B0h+var_88], rax
0x1800f5418  lea     rax, [rbp+57h+var_60]
0x1800f541c  jmp     loc_1800F5232
0x1800f5421  mov     rax, [rdi]
0x1800f5424  lea     rdx, [rbp+57h+var_40]
0x1800f5428  mov     rcx, rdi
0x1800f542b  mov     rax, [rax+58h]
0x1800f542f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5434  mov     ebx, eax
0x1800f5436  test    eax, eax
0x1800f5438  jns     short loc_1800F54B9
0x1800f543a  mov     eax, cs:CallbackContext
0x1800f5440  cmp     eax, 2
0x1800f5443  jbe     loc_1800F56A5
0x1800f5449  lea     rax, aFailedToCreate_39; "Failed to create ConnectionControl plug"...
0x1800f5450  mov     dword ptr [rbp+57h+arg_8], 409h
0x1800f5457  mov     [rbp+57h+var_48], rax
0x1800f545b  lea     rdx, unk_180283868
0x1800f5462  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800f5469  mov     [rbp+57h+var_50], rax
0x1800f546d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f5474  mov     [rbp+57h+var_58], rax
0x1800f5478  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f547f  mov     [rbp+57h+var_60], rax
0x1800f5483  lea     rax, [rbp+57h+var_48]
0x1800f5487  mov     [rsp+0B0h+var_68], rax
0x1800f548c  lea     rax, [rbp+57h+var_50]
0x1800f5490  mov     [rsp+0B0h+var_70], rax
0x1800f5495  lea     rax, [rbp+57h+arg_8]
0x1800f5499  mov     [rsp+0B0h+var_78], rax
0x1800f549e  lea     rax, [rbp+57h+var_58]
0x1800f54a2  mov     [rsp+0B0h+var_80], rax
0x1800f54a7  lea     rax, [rbp+57h+arg_10]
0x1800f54ab  mov     [rsp+0B0h+var_88], rax
0x1800f54b0  lea     rax, [rbp+57h+var_60]
0x1800f54b4  jmp     loc_1800F5232
0x1800f54b9  mov     rcx, [rbp+57h+var_40]
0x1800f54bd  lea     r8, [rbp+57h+var_38]
0x1800f54c1  lea     rdx, IID_IRDPWDUMX_StackEx
0x1800f54c8  mov     rax, [rcx]
0x1800f54cb  mov     rax, [rax]
0x1800f54ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f54d3  mov     ebx, eax
0x1800f54d5  test    eax, eax
0x1800f54d7  jns     short loc_1800F5558
0x1800f54d9  mov     eax, cs:CallbackContext
0x1800f54df  cmp     eax, 2
0x1800f54e2  jbe     loc_1800F56A5
0x1800f54e8  lea     rax, aFailedToQi; "Failed to QI"
0x1800f54ef  mov     dword ptr [rbp+57h+arg_8], 40Ch
0x1800f54f6  mov     [rbp+57h+var_48], rax
0x1800f54fa  lea     rdx, dword_1802837B4
0x1800f5501  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800f5508  mov     [rbp+57h+var_50], rax
0x1800f550c  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f5513  mov     [rbp+57h+var_58], rax
0x1800f5517  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f551e  mov     [rbp+57h+var_60], rax
0x1800f5522  lea     rax, [rbp+57h+var_48]
0x1800f5526  mov     [rsp+0B0h+var_68], rax
0x1800f552b  lea     rax, [rbp+57h+var_50]
0x1800f552f  mov     [rsp+0B0h+var_70], rax
0x1800f5534  lea     rax, [rbp+57h+arg_8]
0x1800f5538  mov     [rsp+0B0h+var_78], rax
0x1800f553d  lea     rax, [rbp+57h+var_58]
0x1800f5541  mov     [rsp+0B0h+var_80], rax
0x1800f5546  lea     rax, [rbp+57h+arg_10]
0x1800f554a  mov     [rsp+0B0h+var_88], rax
0x1800f554f  lea     rax, [rbp+57h+var_60]
0x1800f5553  jmp     loc_1800F5232
0x1800f5558  mov     rcx, [rbp+57h+var_38]; struct IRDPWDUMX_StackEx *
0x1800f555c  lea     rdx, [rbp+57h+var_28]; struct ConnectionControlPlugin **
0x1800f5560  call    ?CreateInstance@ConnectionControlPlugin@@SAJPEAUIRDPWDUMX_StackEx@@PEAPEAV1@@Z; ConnectionControlPlugin::CreateInstance(IRDPWDUMX_StackEx *,ConnectionControlPlugin * *)
0x1800f5565  mov     ebx, eax
0x1800f5567  test    eax, eax
0x1800f5569  jns     short loc_1800F55EA
0x1800f556b  mov     eax, cs:CallbackContext
0x1800f5571  cmp     eax, 2
0x1800f5574  jbe     loc_1800F56A5
0x1800f557a  lea     rax, aFailedToCreate_39; "Failed to create ConnectionControl plug"...
0x1800f5581  mov     dword ptr [rbp+57h+arg_8], 412h
0x1800f5588  mov     [rbp+57h+var_48], rax
0x1800f558c  lea     rdx, word_18028380E
0x1800f5593  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800f559a  mov     [rbp+57h+var_50], rax
0x1800f559e  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f55a5  mov     [rbp+57h+var_58], rax
0x1800f55a9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f55b0  mov     [rbp+57h+var_60], rax
0x1800f55b4  lea     rax, [rbp+57h+var_48]
0x1800f55b8  mov     [rsp+0B0h+var_68], rax
0x1800f55bd  lea     rax, [rbp+57h+var_50]
0x1800f55c1  mov     [rsp+0B0h+var_70], rax
0x1800f55c6  lea     rax, [rbp+57h+arg_8]
0x1800f55ca  mov     [rsp+0B0h+var_78], rax
0x1800f55cf  lea     rax, [rbp+57h+var_58]
0x1800f55d3  mov     [rsp+0B0h+var_80], rax
0x1800f55d8  lea     rax, [rbp+57h+arg_10]
0x1800f55dc  mov     [rsp+0B0h+var_88], rax
0x1800f55e1  lea     rax, [rbp+57h+var_60]
0x1800f55e5  jmp     loc_1800F5232
0x1800f55ea  mov     r8, [rbp+57h+var_30]; struct IRDPCollection *
0x1800f55ee  mov     rdx, [rbp+57h+var_20]; struct IRDPCoreVirtualChannel *
0x1800f55f2  mov     rcx, [rbp+57h+var_28]; this
0x1800f55f6  call    ?InitializeInstance@ConnectionControlPlugin@@UEAAJPEAUIRDPCoreVirtualChannel@@PEAUIRDPCollection@@@Z; ConnectionControlPlugin::InitializeInstance(IRDPCoreVirtualChannel *,IRDPCollection *)
0x1800f55fb  mov     ebx, eax
0x1800f55fd  test    eax, eax
0x1800f55ff  mov     eax, cs:CallbackContext
0x1800f5605  jns     short loc_1800F5680
0x1800f5607  cmp     eax, 2
0x1800f560a  jbe     loc_1800F56A5
0x1800f5610  lea     rax, aFailedToInitCo; "Failed to init ConnectionControl Plugin"
0x1800f5617  mov     dword ptr [rbp+57h+arg_8], 415h
0x1800f561e  mov     [rbp+57h+var_48], rax
0x1800f5622  lea     rdx, dword_18028372C
0x1800f5629  lea     rax, aCreateconnecti; "CreateConnectionChannels"
0x1800f5630  mov     [rbp+57h+var_50], rax
0x1800f5634  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f563b  mov     [rbp+57h+var_58], rax
0x1800f563f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800f5646  mov     [rbp+57h+var_60], rax
0x1800f564a  lea     rax, [rbp+57h+var_48]
0x1800f564e  mov     [rsp+0B0h+var_68], rax
0x1800f5653  lea     rax, [rbp+57h+var_50]
0x1800f5657  mov     [rsp+0B0h+var_70], rax
0x1800f565c  lea     rax, [rbp+57h+arg_8]
0x1800f5660  mov     [rsp+0B0h+var_78], rax
0x1800f5665  lea     rax, [rbp+57h+var_58]
0x1800f5669  mov     [rsp+0B0h+var_80], rax
0x1800f566e  lea     rax, [rbp+57h+arg_10]
0x1800f5672  mov     [rsp+0B0h+var_88], rax
0x1800f5677  lea     rax, [rbp+57h+var_60]
0x1800f567b  jmp     loc_1800F5232
0x1800f5680  cmp     eax, 5
0x1800f5683  jbe     short loc_1800F56A5
0x1800f5685  lea     rax, aInitializedCon; "Initialized ConnectionControl Plugin"
0x1800f568c  mov     [rbp+57h+arg_8], rax
0x1800f5690  lea     rdx, word_180283786
0x1800f5697  lea     rax, [rbp+57h+arg_8]
0x1800f569b  mov     [rsp+0B0h+var_90], rax
0x1800f56a0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800f56a5  lea     rcx, [rbp+57h+var_40]
0x1800f56a9  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f56ae  lea     rcx, [rbp+57h+var_38]
0x1800f56b2  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f56b7  lea     rcx, [rbp+57h+var_30]
0x1800f56bb  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f56c0  lea     rcx, [rbp+57h+var_28]
0x1800f56c4  call    ?SafeRelease@?$TCntPtr@VConnectionControlPlugin@@@@AEAAXXZ; TCntPtr<ConnectionControlPlugin>::SafeRelease(void)
0x1800f56c9  lea     rcx, [rbp+57h+var_20]
0x1800f56cd  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f56d2  mov     rcx, [rbp+57h+arg_18]
  ... truncated ...
```
