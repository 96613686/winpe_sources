# _SqmWebAuthActivation

- ea: `0x1800154bc`
- end: `0x1800157ec`
- name: `_SqmWebAuthActivation`
- size: `816`
- prototype: `void __fastcall(const wchar_t *startUrl, void *clientTokenHandle, unsigned int brokerFlags, int useSsoAppContainer, unsigned int consentPageShown, unsigned int consentButtonState, unsigned int loginPageShown, unsigned int accountSwitchState)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013520`

## callees

- `0x18000102c`
- `0x1800011b4`
- `0x1800045c0`
- `0x180004f00`
- `0x180011cb0`
- `0x180011f00`
- `0x18001261c`
- `0x1800154bc`
- `0x1800204ee`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180015680`
- `ntdll!WinSqmAddToStream` at `0x180015680`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157b6`
- `urlmon!CreateUri` at `0x1800155be`
- `urlmon!CreateUri` at `0x1800155be`

## pseudocode

```c
void __fastcall SqmWebAuthActivation(
        const wchar_t *startUrl,
        void *clientTokenHandle,
        unsigned int brokerFlags,
        int useSsoAppContainer,
        unsigned int consentPageShown,
        unsigned int consentButtonState,
        unsigned int loginPageShown,
        unsigned int accountSwitchState)
{
  unsigned int v12; // edx
  int v13; // r8d
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  int v19; // esi
  wchar_t *v20; // rbx
  HRESULT Uri; // eax
  wchar_t *m_str; // rax
  const wchar_t *v23; // rcx
  const _tlgProvider_t *v24; // rcx
  const _GUID *v25; // r8
  const _GUID *v26; // r9
  ATL::CComBSTR sqmDomain; // [rsp+60h] [rbp-A0h] BYREF
  _tlgWrapperByVal<4> v28; // [rsp+68h] [rbp-98h] BYREF
  _tlgWrapperByVal<4> pEventMetadata; // [rsp+6Ch] [rbp-94h] BYREF
  _tlgWrapperByVal<4> hProvider; // [rsp+70h] [rbp-90h] BYREF
  _tlgWrapperByVal<4> v31; // [rsp+74h] [rbp-8Ch] BYREF
  _tlgWrapperByVal<4> v32; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *moniker; // [rsp+80h] [rbp-80h] BYREF
  ATL::CComPtr<IUri> startUri; // [rsp+88h] [rbp-78h] BYREF
  _tlgWrapSz<unsigned short> v35; // [rsp+90h] [rbp-70h] BYREF
  _tlgWrapSz<unsigned short> v36; // [rsp+98h] [rbp-68h] BYREF
  _SQM_STREAM_ENTRY streamEntries[7]; // [rsp+A0h] [rbp-60h] BYREF

  moniker = 0;
  startUri.p = 0;
  sqmDomain.m_str = 0;
  streamEntries[0].dwType = 0;
  memset_0(&streamEntries[0].val, 0, 0x68u);
  v12 = HIWORD(brokerFlags) & 1 | 2;
  if ( (brokerFlags & 0x20000) == 0 )
    v12 = HIWORD(brokerFlags) & 1;
  v13 = v12 | 4;
  if ( (brokerFlags & 0x80000) == 0 )
    v13 = v12;
  v14 = v13 | 8;
  if ( (brokerFlags & 0x100000) == 0 )
    v14 = v13;
  v15 = v14 | 0x10;
  if ( !useSsoAppContainer )
    v15 = v14;
  v16 = v15 | 0x20;
  if ( (brokerFlags & 1) == 0 )
    v16 = v15;
  v17 = v16 | 0x40;
  if ( (brokerFlags & 2) == 0 )
    v17 = v16;
  v18 = v17 | 0x80;
  if ( (brokerFlags & 4) == 0 )
    v18 = v17;
  v19 = v18 | 0x100;
  if ( (brokerFlags & 8) == 0 )
    v19 = v18;
  if ( clientTokenHandle )
  {
    if ( (int)GetAuthBrokerClientAppContainerStringInfo(1, clientTokenHandle, &moniker) < 0 )
      goto $Cleanup_3;
    v20 = moniker;
  }
  else
  {
    v20 = L"NoApplication";
  }
  Uri = CreateUri(startUrl, 0x2000u, 0, &startUri.p);
  if ( Uri < 0 || (Uri = startUri.p->GetHost(startUri.p, (wchar_t **)&sqmDomain), Uri < 0) )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_dS(
        WPP_GLOBAL_Control[1].Control.Logger,
        0x11u,
        WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids,
        Uri,
        startUrl);
    }
  }
  else
  {
    m_str = sqmDomain.m_str;
    v23 = L"(null)";
    if ( !sqmDomain.m_str || !*sqmDomain.m_str )
      m_str = L"(null)";
    streamEntries[0].val.pwszVal = m_str;
    streamEntries[0].dwType = 2;
    if ( v20 && *v20 )
      v23 = v20;
    streamEntries[1].val.pwszVal = v23;
    streamEntries[1].dwType = 2;
    streamEntries[2].val.dwVal = v19;
    streamEntries[2].dwType = 1;
    streamEntries[3].val.dwVal = consentPageShown;
    streamEntries[3].dwType = 1;
    streamEntries[4].val.dwVal = consentButtonState;
    streamEntries[4].dwType = 1;
    streamEntries[5].val.dwVal = loginPageShown;
    streamEntries[5].dwType = 1;
    streamEntries[6].val.dwVal = accountSwitchState;
    streamEntries[6].dwType = 1;
    WinSqmAddToStream(0, 11036, 7, streamEntries);
    if ( Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1 > 5
      && tlgKeywordOn(&Tlgg_hMyWABTraceLoggingProviderProv, 0x400000000000uLL) )
    {
      v36.Psz = sqmDomain.m_str;
      v28.Value = accountSwitchState;
      pEventMetadata.Value = loginPageShown;
      hProvider.Value = consentButtonState;
      v31.Value = consentPageShown;
      v32.Value = v19;
      v35.Psz = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v24,
        &tlgEvent_0._tlgChannel,
        v25,
        v26,
        &v36,
        &v35,
        &v32,
        &v31,
        &hProvider,
        &pEventMetadata,
        &v28);
    }
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 4u )
    {
      WPP_SF_SSD(
        WPP_GLOBAL_Control[1].Control.Logger,
        0x12u,
        WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids,
        sqmDomain.m_str,
        v20,
        v19);
    }
  }
$Cleanup_3:
  FreeAuthBrokerClientAppContainerString(ClientAppContainerMonikerInfo, moniker);
  SysFreeString(sqmDomain.m_str);
  ATL::CComPtrBase<IUri>::~CComPtrBase<IUri>(&startUri);
}

```

## disassembly

```asm
0x1800154bc  mov     [rsp-8+arg_10], rbx
0x1800154c1  push    rbp
0x1800154c2  push    rsi
0x1800154c3  push    rdi
0x1800154c4  push    r12
0x1800154c6  push    r13
0x1800154c8  push    r14
0x1800154ca  push    r15
0x1800154cc  lea     rbp, [rsp-20h]
0x1800154d1  sub     rsp, 120h
0x1800154d8  mov     rax, cs:__security_cookie
0x1800154df  xor     rax, rsp
0x1800154e2  mov     [rbp+50h+var_40], rax
0x1800154e6  xor     r13d, r13d
0x1800154e9  mov     edi, brokerFlags
0x1800154ec  mov     r15, clientTokenHandle
0x1800154ef  mov     [rbp+50h+moniker], r13
0x1800154f3  mov     r14, startUrl
0x1800154f6  mov     [rbp+50h+startUri.p], r13
0x1800154fa  xor     edx, edx; Val
0x1800154fc  mov     [rsp+150h+sqmDomain.m_str], r13
0x180015501  lea     brokerFlags, [r13+68h]; Size
0x180015505  mov     [rbp+50h+streamEntries.dwType], r13d
0x180015509  lea     startUrl, [rbp+50h+streamEntries.val]; void *
0x18001550d  mov     ebx, useSsoAppContainer
0x180015510  call    memset_0
0x180015515  lea     r12d, [r13+2]
0x180015519  mov     ecx, edi
0x18001551b  shr     ecx, 10h
0x18001551e  and     ecx, 1
0x180015521  mov     edx, ecx
0x180015523  or      edx, r12d
0x180015526  bt      edi, 11h
0x18001552a  cmovnb  edx, ecx
0x18001552d  mov     brokerFlags, edx
0x180015530  or      brokerFlags, 4
0x180015534  bt      edi, 13h
0x180015538  cmovnb  brokerFlags, edx
0x18001553c  mov     ecx, brokerFlags
0x18001553f  or      ecx, 8
0x180015542  bt      edi, 14h
0x180015546  cmovnb  ecx, brokerFlags
0x18001554a  mov     edx, ecx
0x18001554c  or      edx, 10h
0x18001554f  test    ebx, ebx
0x180015551  cmovz   edx, ecx
0x180015554  mov     ecx, edx
0x180015556  or      ecx, 20h
0x180015559  test    dil, 1
0x18001555d  cmovz   ecx, edx
0x180015560  mov     edx, ecx
0x180015562  or      edx, 40h
0x180015565  test    r12b, dil
0x180015568  cmovz   edx, ecx
0x18001556b  mov     ecx, edx
0x18001556d  bts     ecx, 7
0x180015571  test    dil, 4
0x180015575  cmovz   ecx, edx
0x180015578  mov     esi, ecx
0x18001557a  bts     esi, 8
0x18001557e  test    dil, 8
0x180015582  cmovz   esi, ecx
0x180015585  test    r15, r15
0x180015588  jz      short loc_1800155A8
0x18001558a  lea     r8, [rbp+50h+moniker]; string
0x18001558e  mov     clientTokenHandle, r15; clientTokenHandle
0x180015591  lea     ecx, [r13+1]; infoType
0x180015595  call    ?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z; GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)
0x18001559a  test    eax, eax
0x18001559c  js      $Cleanup_3
0x1800155a2  mov     rbx, [rbp+50h+moniker]
0x1800155a6  jmp     short loc_1800155AF
0x1800155a8  lea     rbx, aNoapplication; "NoApplication"
0x1800155af  lea     r9, [rbp+50h+startUri]; ppURI
0x1800155b3  xor     brokerFlags, brokerFlags; dwReserved
0x1800155b6  mov     edx, 2000h; dwFlags
0x1800155bb  mov     startUrl, r14; pwzURI
0x1800155be  call    cs:__imp_CreateUri
0x1800155c4  test    eax, eax
0x1800155c6  js      loc_180015767
0x1800155cc  mov     startUrl, [rbp+50h+startUri.p]
0x1800155d0  lea     clientTokenHandle, [rsp+150h+sqmDomain]
0x1800155d5  mov     rax, [startUrl]
0x1800155d8  mov     rax, [rax+68h]
0x1800155dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e1  test    eax, eax
0x1800155e3  js      loc_180015767
0x1800155e9  mov     rax, [rsp+150h+sqmDomain.m_str]
0x1800155ee  lea     startUrl, aNull; "(null)"
0x1800155f5  test    rax, rax
0x1800155f8  jz      short loc_180015600
0x1800155fa  cmp     [rax], r13w
0x1800155fe  jnz     short loc_180015603
0x180015600  mov     rax, startUrl
0x180015603  mov     qword ptr [rbp+50h+streamEntries.val], rax
0x180015607  mov     [rbp+50h+streamEntries.dwType], r12d
0x18001560b  test    rbx, rbx
0x18001560e  jz      short loc_180015619
0x180015610  cmp     [rbx], r13w
0x180015614  jz      short loc_180015619
0x180015616  mov     startUrl, rbx
0x180015619  mov     edi, [rbp+50h+arg_20]
0x18001561f  lea     r9, [rbp+50h+streamEntries]
0x180015623  mov     r14d, [rbp+50h+arg_28]
0x18001562a  mov     edx, 2B1Ch
0x18001562f  mov     r15d, [rbp+50h+arg_30]
0x180015636  mov     qword ptr [rbp+50h+streamEntries.val+10h], startUrl
0x18001563a  xor     ecx, ecx
0x18001563c  mov     [rbp+50h+streamEntries.dwType+10h], r12d
0x180015640  mov     r12d, [rbp+50h+arg_38]
0x180015647  mov     dword ptr [rbp+50h+streamEntries.val+20h], esi
0x18001564a  lea     brokerFlags, [startUrl+7]
0x18001564e  mov     [rbp+50h+streamEntries.dwType+20h], 1
0x180015655  mov     dword ptr [rbp+50h+streamEntries.val+30h], edi
0x180015658  mov     [rbp+50h+streamEntries.dwType+30h], 1
0x18001565f  mov     dword ptr [rbp+50h+streamEntries.val+40h], r14d
0x180015663  mov     [rbp+50h+streamEntries.dwType+40h], 1
0x18001566a  mov     dword ptr [rbp+50h+streamEntries.val+50h], r15d
0x18001566e  mov     [rbp+50h+streamEntries.dwType+50h], 1
0x180015675  mov     dword ptr [rbp+50h+streamEntries.val+60h], r12d
0x180015679  mov     [rbp+50h+streamEntries.dwType+60h], 1
0x180015680  call    cs:__imp_WinSqmAddToStream
0x180015686  mov     eax, cs:_Tlgg_hMyWABTraceLoggingProviderProv.LevelPlus1
0x18001568c  cmp     eax, 5
0x18001568f  jbe     loc_180015723
0x180015695  mov     clientTokenHandle, 400000000000h; keyword
0x18001569f  lea     startUrl, _Tlgg_hMyWABTraceLoggingProviderProv; hProvider
0x1800156a6  call    _tlgKeywordOn
0x1800156ab  test    al, al
0x1800156ad  jz      short loc_180015723
0x1800156af  mov     rax, [rsp+150h+sqmDomain.m_str]; __annotation("_TlgWrite:|341|g_hMyWABTraceLoggingProvider|"WABDataRelated"=|"Domain"=|"App"=|"Flags"=|"ConsentPageShown"=|"ConsentResult"=|"LoginPageShown"=|"AccountSwitch"=")
0x1800156b4  lea     clientTokenHandle, _tlgEvent_0._tlgChannel; <wrappedArgs_0>
0x1800156bb  mov     [rbp+50h+var_B8.Psz], rax
0x1800156bf  lea     rax, [rsp+150h+var_E8]
0x1800156c4  mov     [rsp+150h+var_100], rax; <writerArgs_0>
0x1800156c9  lea     rax, [rsp+150h+var_E4]
0x1800156ce  mov     [rsp+150h+pEventMetadata], rax; pEventMetadata
0x1800156d3  lea     rax, [rsp+150h+var_E0]
0x1800156d8  mov     [rsp+150h+hProvider], rax; hProvider
0x1800156dd  lea     rax, [rsp+150h+var_DC]
0x1800156e2  mov     [rsp+150h+var_118], rax; <wrappedArgs_6>
0x1800156e7  lea     rax, [rsp+150h+var_D8]
0x1800156ec  mov     [rsp+150h+var_120], rax; <wrappedArgs_5>
0x1800156f1  lea     rax, [rbp+50h+var_C0]
0x1800156f5  mov     [rsp+150h+var_128], rax; <wrappedArgs_4>
0x1800156fa  lea     rax, [rbp+50h+var_B8]
0x1800156fe  mov     [rsp+150h+var_130], rax; <wrappedArgs_3>
0x180015703  mov     [rsp+150h+var_E8.Value], r12d
0x180015708  mov     [rsp+150h+var_E4.Value], r15d
0x18001570d  mov     [rsp+150h+var_E0.Value], r14d
0x180015712  mov     [rsp+150h+var_DC.Value], edi
0x180015716  mov     [rsp+150h+var_D8.Value], esi
0x18001571a  mov     [rbp+50h+var_C0.Psz], rbx
0x18001571e  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180015723  mov     startUrl, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001572a  lea     clientTokenHandle, WPP_GLOBAL_Control
0x180015731  cmp     startUrl, clientTokenHandle
0x180015734  jz      short $Cleanup_3
0x180015736  test    byte ptr [startUrl+44h], 8
0x18001573a  jz      short $Cleanup_3
0x18001573c  cmp     byte ptr [startUrl+41h], 4
0x180015740  jb      short $Cleanup_3
0x180015742  mov     r9, [rsp+150h+sqmDomain.m_str]; _a1
0x180015747  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x18001574e  mov     startUrl, [startUrl+38h]; Logger
0x180015752  mov     edx, 12h; id
0x180015757  mov     dword ptr [rsp+150h+var_128], esi; _a3
0x18001575b  mov     [rsp+150h+var_130], rbx; _a2
0x180015760  call    WPP_SF_SSD
0x180015765  jmp     short $Cleanup_3
0x180015767  mov     startUrl, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001576e  lea     clientTokenHandle, WPP_GLOBAL_Control
0x180015775  cmp     startUrl, clientTokenHandle
0x180015778  jz      short $Cleanup_3
0x18001577a  test    byte ptr [startUrl+44h], 8
0x18001577e  jz      short $Cleanup_3
0x180015780  cmp     [startUrl+41h], r12b
0x180015784  jb      short $Cleanup_3
0x180015786  mov     startUrl, [startUrl+38h]; Logger
0x18001578a  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x180015791  mov     edx, 11h; id
0x180015796  mov     [rsp+150h+var_130], r14; _a2
0x18001579b  mov     useSsoAppContainer, eax; _a1
0x18001579e  call    WPP_SF_dS
0x1800157a3  mov     clientTokenHandle, [rbp+50h+moniker]; string
0x1800157a7  mov     ecx, 1; infoType
0x1800157ac  call    ?FreeAuthBrokerClientAppContainerString@@YAXW4ClientAppContainerStringInfoType@@PEAG@Z; FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType,ushort *)
0x1800157b1  mov     startUrl, [rsp+150h+sqmDomain.m_str]; bstrString
0x1800157b6  call    cs:__imp_SysFreeString
0x1800157bc  lea     startUrl, [rbp+50h+startUri]; this
0x1800157c0  call    ??1?$CComPtrBase@UIUri@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUri>::~CComPtrBase<IUri>(void)
0x1800157c5  mov     startUrl, [rbp+50h+var_40]
0x1800157c9  xor     startUrl, rsp; StackCookie
0x1800157cc  call    __security_check_cookie
0x1800157d1  mov     rbx, [rsp+150h+arg_10]
0x1800157d9  add     rsp, 120h
0x1800157e0  pop     r15
0x1800157e2  pop     r14
0x1800157e4  pop     r13
0x1800157e6  pop     r12
0x1800157e8  pop     rdi
0x1800157e9  pop     rsi
0x1800157ea  pop     rbp
0x1800157eb  retn
```
