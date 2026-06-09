# CInstallAppServer::EnableFeature(void *,ushort const *,int)

- ea: `0x18002fa78`
- end: `0x18002fde3`
- name: `?EnableFeature@CInstallAppServer@@AEAAJPEAXPEBGH@Z`
- size: `875`
- prototype: `int(CInstallAppServer *__hidden this, void *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002fdf0`

## callees

- `0x180001008`
- `0x1800013a4`
- `0x18002d878`
- `0x18002fa78`
- `0x1800304f0`
- `0x18004325c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002fb46`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002fc2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002fb46`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002fc2a`
- `DismApi!DismEnableFeature` at `0x18002fcad`
- `DismApi!DismEnableFeature` at `0x18002fcad`
- `DismApi!DismInitialize` at `0x18002faa9`
- `DismApi!DismInitialize` at `0x18002faa9`
- `DismApi!DismOpenSession` at `0x18002fbdc`
- `DismApi!DismOpenSession` at `0x18002fbdc`
- `DismApi!DismDisableFeature` at `0x18002fd3e`
- `DismApi!DismDisableFeature` at `0x18002fd3e`
- `DismApi!DismShutdown` at `0x18002fdc1`
- `DismApi!DismShutdown` at `0x18002fdc1`

## string_xrefs

- `0x18002fc18`: `DismOpenSession`

## pseudocode

```c
__int64 __fastcall CInstallAppServer::EnableFeature(
        CInstallAppServer *this,
        void *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  char *v9; // rdx
  const char *v10; // rax
  int v11; // eax
  int v12; // eax
  const char *v13; // rax
  __int16 *v14; // rdx
  int v15; // eax
  int v17; // [rsp+60h] [rbp+7h] BYREF
  const char *v18; // [rsp+68h] [rbp+Fh] BYREF
  const char *v19; // [rsp+70h] [rbp+17h] BYREF
  const unsigned __int16 *v20[7]; // [rsp+78h] [rbp+1Fh] BYREF
  unsigned int v21; // [rsp+D0h] [rbp+77h] BYREF
  int v22; // [rsp+D4h] [rbp+7Bh]

  v22 = HIDWORD(a3);
  v21 = -1073479676;
  v7 = DismInitialize(2, 0, 0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( !WaitForSingleObject(a2, 1u) )
    {
      v8 = -2147467260;
      if ( (unsigned int)dword_180084170 <= 3 )
      {
LABEL_31:
        DismShutdown();
        goto LABEL_32;
      }
      v9 = (char *)&dword_18007A40C;
      goto LABEL_7;
    }
    v11 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v21);
    v8 = v11;
    if ( v11 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v11, 0);
      if ( (unsigned int)dword_180084170 <= 3 )
        goto LABEL_31;
      v17 = v8;
      v20[0] = (const unsigned __int16 *)"EnableFeature";
      v9 = byte_18007A3CB;
      v10 = "DismOpenSession";
      goto LABEL_8;
    }
    if ( !WaitForSingleObject(a2, 1u) )
    {
      v8 = -2147467260;
      if ( (unsigned int)dword_180084170 <= 3 )
        goto LABEL_31;
      v9 = (char *)word_18007A38A;
LABEL_7:
      v17 = -2147467260;
      v20[0] = (const unsigned __int16 *)"EnableFeature";
      v10 = "Abort was signalled";
LABEL_8:
      v19 = v10;
      v18 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&dword_180084170,
        (__int64)v9,
        0,
        0,
        (const unsigned __int16 **)&v18,
        (const unsigned __int16 **)&v19,
        (__int64)&v17,
        v20);
      goto LABEL_31;
    }
    if ( a4 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SessEnvDismEnableFeatureWU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SessEnvDismEnableFeatureWU>::GetImpl'::`2'::impl) )
        v12 = DismEnableFeature(v21, L"AppServerClient", 0, 0, 0, 0, 0, 1, a2, 0, 0);
      else
        v12 = DismEnableFeature(v21, L"AppServerClient", 0, 0, 1, 0, 0, 1, a2, 0, 0);
      v8 = v12;
      if ( v12 < 0 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v12, 0);
        if ( (unsigned int)dword_180084170 <= 3 )
          goto LABEL_31;
        v17 = v8;
        v20[0] = (const unsigned __int16 *)"EnableFeature";
        v9 = byte_18007A349;
        v10 = "DismEnableFeature";
        goto LABEL_8;
      }
      if ( (unsigned int)dword_180084170 > 4 )
      {
        v13 = "DismEnableFeature() enabled AppServerClient";
        v14 = word_18007A322;
LABEL_29:
        v20[0] = (const unsigned __int16 *)v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (__int64)&dword_180084170,
          (__int64)v14,
          0,
          0,
          v20);
      }
    }
    else
    {
      v15 = DismDisableFeature(v21, L"AppServerClient", 0, 0, a2, 0, 0);
      v8 = v15;
      if ( v15 < 0 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v15, 0);
        if ( (unsigned int)dword_180084170 <= 3 )
          goto LABEL_31;
        v17 = v8;
        v20[0] = (const unsigned __int16 *)"EnableFeature";
        v9 = byte_18007A2E1;
        v10 = "DismDisableFeature";
        goto LABEL_8;
      }
      if ( (unsigned int)dword_180084170 > 4 )
      {
        v13 = "DismEnableFeature() disabled AppServerClient";
        v14 = word_18007A2BA;
        goto LABEL_29;
      }
    }
    *((_DWORD *)this + 398) = 1;
    goto LABEL_31;
  }
  MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v7, 0);
  if ( (unsigned int)dword_180084170 > 3 )
  {
    v17 = v8;
    v18 = "EnableFeature";
    v19 = "DismInitialize";
    v20[0] = (const unsigned __int16 *)"Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)&dword_180084170,
      (__int64)byte_18007A44D,
      0,
      0,
      v20,
      (const unsigned __int16 **)&v19,
      (__int64)&v17,
      (const unsigned __int16 **)&v18);
  }
LABEL_32:
  TraceLoggingWriteInstallEvent(v8, a4);
  return v8;
}

```

## disassembly

```asm
0x18002fa78  mov     [rsp-8+arg_10], r8
0x18002fa7d  push    rbp
0x18002fa7e  push    rbx
0x18002fa7f  push    rsi
0x18002fa80  push    rdi
0x18002fa81  push    r12
0x18002fa83  push    r14
0x18002fa85  lea     rbp, [rsp-2Fh]
0x18002fa8a  sub     rsp, 88h
0x18002fa91  mov     rdi, rdx
0x18002fa94  mov     dword ptr [rbp+57h+arg_10], 0C0040004h
0x18002fa9b  xor     edx, edx
0x18002fa9d  mov     rsi, rcx
0x18002faa0  xor     r8d, r8d
0x18002faa3  mov     r14d, r9d
0x18002faa6  lea     ecx, [rdx+2]
0x18002faa9  call    cs:__imp_DismInitialize
0x18002faaf  mov     ebx, eax
0x18002fab1  test    eax, eax
0x18002fab3  jns     loc_18002FB3A
0x18002fab9  xor     r8d, r8d
0x18002fabc  mov     edx, eax
0x18002fabe  xor     ecx, ecx
0x18002fac0  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002fac5  mov     ecx, cs:dword_180084170
0x18002facb  cmp     ecx, 3
0x18002face  jbe     loc_18002FDC7
0x18002fad4  lea     rax, aEnablefeature; "EnableFeature"
0x18002fadb  mov     [rbp+57h+var_50], ebx
0x18002fade  mov     [rbp+57h+var_48], rax
0x18002fae2  lea     rdx, byte_18007A44D
0x18002fae9  lea     rax, aDisminitialize_0; "DismInitialize"
0x18002faf0  xor     r9d, r9d
0x18002faf3  mov     [rbp+57h+var_40], rax
0x18002faf7  lea     rcx, dword_180084170
0x18002fafe  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002fb05  xor     r8d, r8d
0x18002fb08  mov     [rbp+57h+var_38], rax
0x18002fb0c  lea     rax, [rbp+57h+var_48]
0x18002fb10  mov     [rsp+0B0h+var_78], rax
0x18002fb15  lea     rax, [rbp+57h+var_50]
0x18002fb19  mov     [rsp+0B0h+var_80], rax
0x18002fb1e  lea     rax, [rbp+57h+var_40]
0x18002fb22  mov     [rsp+0B0h+var_88], rax
0x18002fb27  lea     rax, [rbp+57h+var_38]
0x18002fb2b  mov     [rsp+0B0h+var_90], rax
0x18002fb30  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002fb35  jmp     loc_18002FDC7
0x18002fb3a  mov     r12d, 1
0x18002fb40  mov     rcx, rdi; hHandle
0x18002fb43  mov     edx, r12d; dwMilliseconds
0x18002fb46  call    cs:__imp_WaitForSingleObject
0x18002fb4c  test    eax, eax
0x18002fb4e  jnz     short loc_18002FBCC
0x18002fb50  mov     eax, cs:dword_180084170
0x18002fb56  mov     ecx, 80004004h
0x18002fb5b  mov     ebx, ecx
0x18002fb5d  cmp     eax, 3
0x18002fb60  jbe     loc_18002FDC1
0x18002fb66  lea     rdx, dword_18007A40C
0x18002fb6d  lea     rax, aEnablefeature; "EnableFeature"
0x18002fb74  mov     [rbp+57h+var_50], ecx
0x18002fb77  mov     [rbp+57h+var_38], rax
0x18002fb7b  lea     rax, aAbortWasSignal_0; "Abort was signalled"
0x18002fb82  mov     [rbp+57h+var_40], rax
0x18002fb86  lea     rcx, dword_180084170
0x18002fb8d  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002fb94  xor     r9d, r9d
0x18002fb97  mov     [rbp+57h+var_48], rax
0x18002fb9b  xor     r8d, r8d
0x18002fb9e  lea     rax, [rbp+57h+var_38]
0x18002fba2  mov     [rsp+0B0h+var_78], rax
0x18002fba7  lea     rax, [rbp+57h+var_50]
0x18002fbab  mov     [rsp+0B0h+var_80], rax
0x18002fbb0  lea     rax, [rbp+57h+var_40]
0x18002fbb4  mov     [rsp+0B0h+var_88], rax
0x18002fbb9  lea     rax, [rbp+57h+var_48]
0x18002fbbd  mov     [rsp+0B0h+var_90], rax
0x18002fbc2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002fbc7  jmp     loc_18002FDC1
0x18002fbcc  lea     r9, [rbp+57h+arg_10]
0x18002fbd0  xor     r8d, r8d
0x18002fbd3  xor     edx, edx
0x18002fbd5  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x18002fbdc  call    cs:__imp_DismOpenSession
0x18002fbe2  mov     ebx, eax
0x18002fbe4  test    eax, eax
0x18002fbe6  jns     short loc_18002FC24
0x18002fbe8  xor     r8d, r8d
0x18002fbeb  mov     edx, eax
0x18002fbed  xor     ecx, ecx
0x18002fbef  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002fbf4  mov     eax, cs:dword_180084170
0x18002fbfa  cmp     eax, 3
0x18002fbfd  jbe     loc_18002FDC1
0x18002fc03  lea     rax, aEnablefeature; "EnableFeature"
0x18002fc0a  mov     [rbp+57h+var_50], ebx
0x18002fc0d  mov     [rbp+57h+var_38], rax
0x18002fc11  lea     rdx, byte_18007A3CB
0x18002fc18  lea     rax, aDismopensessio_0; "DismOpenSession"
0x18002fc1f  jmp     loc_18002FB82
0x18002fc24  mov     edx, r12d; dwMilliseconds
0x18002fc27  mov     rcx, rdi; hHandle
0x18002fc2a  call    cs:__imp_WaitForSingleObject
0x18002fc30  test    eax, eax
0x18002fc32  jnz     short loc_18002FC56
0x18002fc34  mov     eax, cs:dword_180084170
0x18002fc3a  mov     ecx, 80004004h
0x18002fc3f  mov     ebx, ecx
0x18002fc41  cmp     eax, 3
0x18002fc44  jbe     loc_18002FDC1
0x18002fc4a  lea     rdx, word_18007A38A
0x18002fc51  jmp     loc_18002FB6D
0x18002fc56  test    r14d, r14d
0x18002fc59  jz      loc_18002FD17
0x18002fc5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SessEnvDismEnableFeatureWU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SessEnvDismEnableFeatureWU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SessEnvDismEnableFeatureWU> `wil::Feature<__WilFeatureTraits_Feature_SessEnvDismEnableFeatureWU>::GetImpl(void)'::`2'::impl
0x18002fc66  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SessEnvDismEnableFeatureWU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SessEnvDismEnableFeatureWU>::__private_IsEnabled(void)
0x18002fc6b  mov     ecx, dword ptr [rbp+57h+arg_10]
0x18002fc6e  lea     rdx, aAppserverclien; "AppServerClient"
0x18002fc75  mov     [rsp+0B0h+var_60], 0
0x18002fc7e  xor     r8d, r8d
0x18002fc81  mov     [rsp+0B0h+var_68], r8
0x18002fc86  xor     r9d, r9d
0x18002fc89  mov     [rsp+0B0h+var_70], rdi
0x18002fc8e  mov     dword ptr [rsp+0B0h+var_78], r12d
0x18002fc93  mov     dword ptr [rsp+0B0h+var_80], r8d
0x18002fc98  mov     [rsp+0B0h+var_88], r8
0x18002fc9d  test    al, al
0x18002fc9f  jz      short loc_18002FCA8
0x18002fca1  mov     dword ptr [rsp+0B0h+var_90], r8d
0x18002fca6  jmp     short loc_18002FCAD
0x18002fca8  mov     dword ptr [rsp+0B0h+var_90], r12d
0x18002fcad  call    cs:__imp_DismEnableFeature
0x18002fcb3  mov     ebx, eax
0x18002fcb5  test    eax, eax
0x18002fcb7  jns     short loc_18002FCF5
0x18002fcb9  xor     r8d, r8d
0x18002fcbc  mov     edx, eax
0x18002fcbe  xor     ecx, ecx
0x18002fcc0  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002fcc5  mov     eax, cs:dword_180084170
0x18002fccb  cmp     eax, 3
0x18002fcce  jbe     loc_18002FDC1
0x18002fcd4  lea     rax, aEnablefeature; "EnableFeature"
0x18002fcdb  mov     [rbp+57h+var_50], ebx
0x18002fcde  mov     [rbp+57h+var_38], rax
0x18002fce2  lea     rdx, byte_18007A349
0x18002fce9  lea     rax, aDismenablefeat_1; "DismEnableFeature"
0x18002fcf0  jmp     loc_18002FB82
0x18002fcf5  mov     eax, cs:dword_180084170
0x18002fcfb  cmp     eax, 4
0x18002fcfe  jbe     loc_18002FDBA
0x18002fd04  lea     rax, aDismenablefeat_0; "DismEnableFeature() enabled AppServerCl"...
0x18002fd0b  lea     rdx, word_18007A322
0x18002fd12  jmp     loc_18002FD9B
0x18002fd17  mov     ecx, dword ptr [rbp+57h+arg_10]
0x18002fd1a  lea     rdx, aAppserverclien; "AppServerClient"
0x18002fd21  mov     [rsp+0B0h+var_80], 0
0x18002fd2a  xor     r9d, r9d
0x18002fd2d  mov     [rsp+0B0h+var_88], 0
0x18002fd36  xor     r8d, r8d
0x18002fd39  mov     [rsp+0B0h+var_90], rdi
0x18002fd3e  call    cs:__imp_DismDisableFeature
0x18002fd44  mov     ebx, eax
0x18002fd46  test    eax, eax
0x18002fd48  jns     short loc_18002FD82
0x18002fd4a  xor     r8d, r8d
0x18002fd4d  mov     edx, eax
0x18002fd4f  xor     ecx, ecx
0x18002fd51  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002fd56  mov     eax, cs:dword_180084170
0x18002fd5c  cmp     eax, 3
0x18002fd5f  jbe     short loc_18002FDC1
0x18002fd61  lea     rax, aEnablefeature; "EnableFeature"
0x18002fd68  mov     [rbp+57h+var_50], ebx
0x18002fd6b  mov     [rbp+57h+var_38], rax
0x18002fd6f  lea     rdx, byte_18007A2E1
0x18002fd76  lea     rax, aDismdisablefea_0; "DismDisableFeature"
0x18002fd7d  jmp     loc_18002FB82
0x18002fd82  mov     eax, cs:dword_180084170
0x18002fd88  cmp     eax, 4
0x18002fd8b  jbe     short loc_18002FDBA
0x18002fd8d  lea     rax, aDismenablefeat_2; "DismEnableFeature() disabled AppServerC"...
0x18002fd94  lea     rdx, word_18007A2BA
0x18002fd9b  mov     [rbp+57h+var_38], rax
0x18002fd9f  lea     rcx, dword_180084170
0x18002fda6  lea     rax, [rbp+57h+var_38]
0x18002fdaa  xor     r9d, r9d
0x18002fdad  xor     r8d, r8d
0x18002fdb0  mov     [rsp+0B0h+var_90], rax
0x18002fdb5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002fdba  mov     [rsi+638h], r12d
0x18002fdc1  call    cs:__imp_DismShutdown
0x18002fdc7  mov     edx, r14d; unsigned int
0x18002fdca  mov     ecx, ebx; unsigned int
0x18002fdcc  call    ?TraceLoggingWriteInstallEvent@@YAXKK@Z; TraceLoggingWriteInstallEvent(ulong,ulong)
0x18002fdd1  mov     eax, ebx
0x18002fdd3  add     rsp, 88h
0x18002fdda  pop     r14
0x18002fddc  pop     r12
0x18002fdde  pop     rdi
0x18002fddf  pop     rsi
0x18002fde0  pop     rbx
0x18002fde1  pop     rbp
0x18002fde2  retn
```
