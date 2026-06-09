# WSMan::Client::ProxyCache::Initialize(IRequestContext *,WSMan::Client::ProxyManager *,ushort const *,WSManProxyAccessType)

- ea: `0x18015ab0c`
- end: `0x18015ae80`
- name: `?Initialize@ProxyCache@Client@WSMan@@QEAA_NPEAVIRequestContext@@PEAVProxyManager@23@PEBGW4WSManProxyAccessType@@@Z`
- size: `884`
- prototype: `bool __usercall@<al>(void **this@<rcx>, struct IRequestContext *@<rdx>, struct WSMan::Client::ProxyManager *@<r8>, const unsigned __int16 *@<r9>, enum WSManProxyAccessType)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18015ae88`

## callees

- `0x180005d10`
- `0x18000fc50`
- `0x180016410`
- `0x180019950`
- `0x18001e620`
- `0x180080980`
- `0x1800973c0`
- `0x1801123a8`
- `0x18011a6d4`
- `0x180159d14`
- `0x18015ab0c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ac0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ac70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ace4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ad2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015adcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ac0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ac70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ace4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ad2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015adcc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18015adc2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18015adc2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015ad14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015ad14`
- `WINHTTP!WinHttpConnect` at `0x18015acd2`
- `WINHTTP!WinHttpConnect` at `0x18015acd2`
- `WINHTTP!WinHttpOpen` at `0x18015abff`
- `WINHTTP!WinHttpOpen` at `0x18015abff`
- `WINHTTP!WinHttpSetTimeouts` at `0x18015ac66`
- `WINHTTP!WinHttpSetTimeouts` at `0x18015ac66`

## pseudocode

```c
char __fastcall WSMan::Client::ProxyCache::Initialize(
        void **this,
        struct IRequestContext *a2,
        struct WSMan::Client::ProxyManager *a3,
        const unsigned __int16 *a4,
        enum WSManProxyAccessType a5)
{
  const unsigned __int16 *v9; // r8
  __int64 v10; // rdx
  void *v11; // rax
  DWORD LastError; // eax
  DWORD v13; // ebx
  DWORD v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  WSMan::Client::ProxyCache *v17; // rcx
  void *v18; // rax
  HANDLE EventW; // rax
  DWORD v20; // eax
  DWORD v21; // ebx
  WSMan::Client::ProxyCache *v22; // rcx
  DWORD v23; // eax
  DWORD v24; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_6b47539da6a835fccef79b16f289f67f_Traceguids, this);
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanproxy.cpp", 287, L"287", 0x54Fu, 0);
    return 0;
  }
  if ( !a4 || !*a4 )
  {
    v9 = L"288";
    v10 = 288;
    goto LABEL_48;
  }
  if ( a5 != WSMAN_OPTION_PROXY_IE_PROXY_CONFIG && a5 != WSMAN_OPTION_PROXY_AUTO_DETECT )
  {
    v9 = L"290";
    v10 = 290;
LABEL_48:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanproxy.cpp", v10, v9, 0x54Fu, a2);
    return 0;
  }
  if ( !a3 )
  {
    v9 = L"291";
    v10 = 291;
    goto LABEL_48;
  }
  *((_DWORD *)this + 4) = a5;
  this[3] = (void *)a4;
  AutoRelease<CServiceConfigCache>::operator=(this + 8, a3);
  (**(void (__fastcall ***)(void *))this[8])(this[8]);
  v11 = WinHttpOpen(L"Microsoft WinRM Client - Proxy Autodetection", 0, 0, 0, 0);
  *this = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_6b47539da6a835fccef79b16f289f67f_Traceguids, LastError);
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v13);
    return 0;
  }
  if ( !WinHttpSetTimeouts(v11, 15000, 15000, 15000, 15000) )
  {
    v14 = GetLastError();
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_23;
    v16 = 26;
LABEL_22:
    WPP_SF_d(v15[2], v16, WPP_6b47539da6a835fccef79b16f289f67f_Traceguids, v14);
LABEL_23:
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v14);
LABEL_24:
    WSMan::Client::ProxyCache::CloseWinHttpHandle(v17, this);
    return 0;
  }
  v18 = WinHttpConnect(*this, L"127.0.0.1", 0x50u, 0);
  this[1] = v18;
  if ( !v18 )
  {
    v14 = GetLastError();
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_23;
    v16 = 27;
    goto LABEL_22;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  AutoHandle::operator=(this + 4, EventW);
  if ( !this[4] )
  {
    v20 = GetLastError();
    v21 = v20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_6b47539da6a835fccef79b16f289f67f_Traceguids, v20);
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v21);
LABEL_34:
    WSMan::Client::ProxyCache::CloseWinHttpHandle(v22, this + 1);
    goto LABEL_24;
  }
  if ( WSMan::EventHandler::IsEventProviderEnabled()
    && WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_TRANSFER_EVENT) )
  {
    WSMan::EventHandler::CreateActivityId((LPGUID)(this + 9));
    WSMan::EventHandler::GenerateTransferId(&LOG_WSMAN_AN_TRANSFER_EVENT, 0, (const struct _GUID *)(this + 9));
  }
  if ( !QueueUserWorkItem(WSMan::Client::ProxyCache::_ExecuteAutoDetection, this, 0x110u) )
  {
    v23 = GetLastError();
    v24 = v23;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_6b47539da6a835fccef79b16f289f67f_Traceguids, v23);
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v24);
    AutoHandle::operator=(this + 4, 0);
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_6b47539da6a835fccef79b16f289f67f_Traceguids, this);
  return 1;
}

```

## disassembly

```asm
0x18015ab0c  push    rbx
0x18015ab0e  push    rbp
0x18015ab0f  push    rsi
0x18015ab10  push    rdi
0x18015ab11  push    r12
0x18015ab13  push    r13
0x18015ab15  push    r14
0x18015ab17  push    r15
0x18015ab19  sub     rsp, 38h
0x18015ab1d  mov     rbx, r9
0x18015ab20  mov     rbp, r8
0x18015ab23  mov     rdi, rdx
0x18015ab26  mov     rsi, rcx
0x18015ab29  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ab30  lea     r12, WPP_GLOBAL_Control
0x18015ab37  lea     r13, WPP_6b47539da6a835fccef79b16f289f67f_Traceguids
0x18015ab3e  cmp     rcx, r12
0x18015ab41  jz      short loc_18015AB60
0x18015ab43  test    dword ptr [rcx+1Ch], 1000h
0x18015ab4a  jz      short loc_18015AB60
0x18015ab4c  mov     rcx, [rcx+10h]
0x18015ab50  mov     edx, 18h
0x18015ab55  mov     r9, rsi
0x18015ab58  mov     r8, r13
0x18015ab5b  call    WPP_SF_q
0x18015ab60  xor     r15d, r15d
0x18015ab63  test    rdi, rdi
0x18015ab66  jnz     short loc_18015AB7E
0x18015ab68  mov     qword ptr [rsp+78h+dwFlags], r15
0x18015ab6d  lea     r8, a287; "287"
0x18015ab74  mov     edx, 11Fh
0x18015ab79  jmp     loc_18015AE5B
0x18015ab7e  test    rbx, rbx
0x18015ab81  jz      loc_18015AE4A
0x18015ab87  cmp     [rbx], r15w
0x18015ab8b  jz      loc_18015AE4A
0x18015ab91  mov     eax, [rsp+78h+arg_20]
0x18015ab98  cmp     eax, 1
0x18015ab9b  jz      short loc_18015ABB3
0x18015ab9d  cmp     eax, 4
0x18015aba0  jz      short loc_18015ABB3
0x18015aba2  lea     r8, a290; "290"
0x18015aba9  mov     edx, 122h
0x18015abae  jmp     loc_18015AE56
0x18015abb3  test    rbp, rbp
0x18015abb6  jnz     short loc_18015ABC9
0x18015abb8  lea     r8, a291; "291"
0x18015abbf  mov     edx, 123h
0x18015abc4  jmp     loc_18015AE56
0x18015abc9  mov     rdx, rbp
0x18015abcc  mov     [rsi+10h], eax
0x18015abcf  lea     rcx, [rsi+40h]
0x18015abd3  mov     [rsi+18h], rbx
0x18015abd7  call    ??4?$AutoRelease@VCServiceConfigCache@@@@QEAAAEAV0@PEAVCServiceConfigCache@@@Z; AutoRelease<CServiceConfigCache>::operator=(CServiceConfigCache *)
0x18015abdc  mov     rcx, [rsi+40h]
0x18015abe0  mov     rax, [rcx]
0x18015abe3  mov     rax, [rax]
0x18015abe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015abeb  xor     r9d, r9d; pszProxyBypassW
0x18015abee  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x18015abf3  xor     r8d, r8d; pszProxyW
0x18015abf6  lea     rcx, aMicrosoftWinrm; "Microsoft WinRM Client - Proxy Autodete"...
0x18015abfd  xor     edx, edx; dwAccessType
0x18015abff  call    cs:__imp_WinHttpOpen
0x18015ac05  mov     [rsi], rax
0x18015ac08  test    rax, rax
0x18015ac0b  jnz     short loc_18015AC54
0x18015ac0d  call    cs:__imp_GetLastError
0x18015ac13  mov     ebx, eax
0x18015ac15  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ac1c  cmp     rcx, r12
0x18015ac1f  jz      short loc_18015AC3E
0x18015ac21  test    dword ptr [rcx+1Ch], 800h
0x18015ac28  jz      short loc_18015AC3E
0x18015ac2a  mov     rcx, [rcx+10h]
0x18015ac2e  mov     edx, 19h
0x18015ac33  mov     r9d, eax
0x18015ac36  mov     r8, r13
0x18015ac39  call    WPP_SF_d
0x18015ac3e  mov     rax, [rdi]
0x18015ac41  mov     edx, ebx
0x18015ac43  mov     rcx, rdi
0x18015ac46  mov     rax, [rax+48h]
0x18015ac4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ac4f  jmp     loc_18015AE6D
0x18015ac54  mov     edx, 3A98h; nResolveTimeout
0x18015ac59  mov     rcx, rax; hInternet
0x18015ac5c  mov     r9d, edx; nSendTimeout
0x18015ac5f  mov     [rsp+78h+dwFlags], edx; nReceiveTimeout
0x18015ac63  mov     r8d, edx; nConnectTimeout
0x18015ac66  call    cs:__imp_WinHttpSetTimeouts
0x18015ac6c  test    eax, eax
0x18015ac6e  jnz     short loc_18015ACBF
0x18015ac70  call    cs:__imp_GetLastError
0x18015ac76  mov     ebx, eax
0x18015ac78  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ac7f  cmp     rcx, r12
0x18015ac82  jz      short loc_18015ACA1
0x18015ac84  test    dword ptr [rcx+1Ch], 800h
0x18015ac8b  jz      short loc_18015ACA1
0x18015ac8d  mov     edx, 1Ah
0x18015ac92  mov     rcx, [rcx+10h]
0x18015ac96  mov     r9d, ebx
0x18015ac99  mov     r8, r13
0x18015ac9c  call    WPP_SF_d
0x18015aca1  mov     rax, [rdi]
0x18015aca4  mov     edx, ebx
0x18015aca6  mov     rcx, rdi
0x18015aca9  mov     rax, [rax+48h]
0x18015acad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015acb2  mov     rdx, rsi; void **
0x18015acb5  call    ?CloseWinHttpHandle@ProxyCache@Client@WSMan@@AEAAXAEAPEAX@Z; WSMan::Client::ProxyCache::CloseWinHttpHandle(void * &)
0x18015acba  jmp     loc_18015AE6D
0x18015acbf  mov     rcx, [rsi]; hSession
0x18015acc2  lea     rdx, pswzServerName; "127.0.0.1"
0x18015acc9  mov     r8d, 50h ; 'P'; nServerPort
0x18015accf  xor     r9d, r9d; dwReserved
0x18015acd2  call    cs:__imp_WinHttpConnect
0x18015acd8  lea     r14, [rsi+8]
0x18015acdc  mov     [r14], rax
0x18015acdf  test    rax, rax
0x18015ace2  jnz     short loc_18015AD08
0x18015ace4  call    cs:__imp_GetLastError
0x18015acea  mov     ebx, eax
0x18015acec  mov     rcx, cs:WPP_GLOBAL_Control
0x18015acf3  cmp     rcx, r12
0x18015acf6  jz      short loc_18015ACA1
0x18015acf8  test    dword ptr [rcx+1Ch], 800h
0x18015acff  jz      short loc_18015ACA1
0x18015ad01  mov     edx, 1Bh
0x18015ad06  jmp     short loc_18015AC92
0x18015ad08  xor     r9d, r9d; lpName
0x18015ad0b  xor     r8d, r8d; bInitialState
0x18015ad0e  xor     ecx, ecx; lpEventAttributes
0x18015ad10  lea     edx, [r9+1]; bManualReset
0x18015ad14  call    cs:__imp_CreateEventW
0x18015ad1a  lea     rbp, [rsi+20h]
0x18015ad1e  mov     rdx, rax
0x18015ad21  mov     rcx, rbp
0x18015ad24  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x18015ad29  cmp     [rbp+0], r15
0x18015ad2d  jnz     short loc_18015AD7E
0x18015ad2f  call    cs:__imp_GetLastError
0x18015ad35  mov     ebx, eax
0x18015ad37  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ad3e  cmp     rcx, r12
0x18015ad41  jz      short loc_18015AD60
0x18015ad43  test    dword ptr [rcx+1Ch], 800h
0x18015ad4a  jz      short loc_18015AD60
0x18015ad4c  mov     rcx, [rcx+10h]
0x18015ad50  mov     edx, 1Ch
0x18015ad55  mov     r9d, eax
0x18015ad58  mov     r8, r13
0x18015ad5b  call    WPP_SF_d
0x18015ad60  mov     rax, [rdi]
0x18015ad63  mov     edx, ebx
0x18015ad65  mov     rcx, rdi
0x18015ad68  mov     rax, [rax+48h]
0x18015ad6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ad71  mov     rdx, r14; void **
0x18015ad74  call    ?CloseWinHttpHandle@ProxyCache@Client@WSMan@@AEAAXAEAPEAX@Z; WSMan::Client::ProxyCache::CloseWinHttpHandle(void * &)
0x18015ad79  jmp     loc_18015ACB2
0x18015ad7e  call    ?IsEventProviderEnabled@EventHandler@WSMan@@SA_NXZ; WSMan::EventHandler::IsEventProviderEnabled(void)
0x18015ad83  test    al, al
0x18015ad85  jz      short loc_18015ADB2
0x18015ad87  lea     rcx, LOG_WSMAN_AN_TRANSFER_EVENT; struct _EVENT_DESCRIPTOR *
0x18015ad8e  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x18015ad93  test    al, al
0x18015ad95  jz      short loc_18015ADB2
0x18015ad97  lea     rcx, [rsi+48h]; ActivityId
0x18015ad9b  call    ?CreateActivityId@EventHandler@WSMan@@SAXAEAU_GUID@@@Z; WSMan::EventHandler::CreateActivityId(_GUID &)
0x18015ada0  lea     r8, [rsi+48h]; struct _GUID *
0x18015ada4  xor     edx, edx; struct _GUID *
0x18015ada6  lea     rcx, LOG_WSMAN_AN_TRANSFER_EVENT; struct _EVENT_DESCRIPTOR *
0x18015adad  call    ?GenerateTransferId@EventHandler@WSMan@@SAXAEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@1@Z; WSMan::EventHandler::GenerateTransferId(_EVENT_DESCRIPTOR const &,_GUID const *,_GUID const *)
0x18015adb2  mov     r8d, 110h; Flags
0x18015adb8  lea     rcx, ?_ExecuteAutoDetection@ProxyCache@Client@WSMan@@CAKPEAX@Z; Function
0x18015adbf  mov     rdx, rsi; Context
0x18015adc2  call    cs:__imp_QueueUserWorkItem
0x18015adc8  test    eax, eax
0x18015adca  jnz     short loc_18015AE1D
0x18015adcc  call    cs:__imp_GetLastError
0x18015add2  mov     ebx, eax
0x18015add4  mov     rcx, cs:WPP_GLOBAL_Control
0x18015addb  cmp     rcx, r12
0x18015adde  jz      short loc_18015ADFD
0x18015ade0  test    dword ptr [rcx+1Ch], 800h
0x18015ade7  jz      short loc_18015ADFD
0x18015ade9  mov     rcx, [rcx+10h]
0x18015aded  mov     edx, 1Dh
0x18015adf2  mov     r9d, eax
0x18015adf5  mov     r8, r13
0x18015adf8  call    WPP_SF_d
0x18015adfd  mov     rax, [rdi]
0x18015ae00  mov     edx, ebx
0x18015ae02  mov     rcx, rdi
0x18015ae05  mov     rax, [rax+48h]
0x18015ae09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ae0e  xor     edx, edx
0x18015ae10  mov     rcx, rbp
0x18015ae13  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x18015ae18  jmp     loc_18015AD71
0x18015ae1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18015ae24  cmp     rcx, r12
0x18015ae27  jz      short loc_18015AE46
0x18015ae29  test    dword ptr [rcx+1Ch], 1000h
0x18015ae30  jz      short loc_18015AE46
0x18015ae32  mov     rcx, [rcx+10h]
0x18015ae36  mov     edx, 1Eh
0x18015ae3b  mov     r9, rsi
0x18015ae3e  mov     r8, r13
0x18015ae41  call    WPP_SF_q
0x18015ae46  mov     al, 1
0x18015ae48  jmp     short loc_18015AE6F
0x18015ae4a  lea     r8, a288; "288"
0x18015ae51  mov     edx, 120h; unsigned int
0x18015ae56  mov     qword ptr [rsp+78h+dwFlags], rdi; struct IRequestContext *
0x18015ae5b  mov     r9d, 54Fh; unsigned int
0x18015ae61  lea     rcx, aOnecoreAdminWm_24; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x18015ae68  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18015ae6d  xor     al, al
0x18015ae6f  add     rsp, 38h
0x18015ae73  pop     r15
0x18015ae75  pop     r14
0x18015ae77  pop     r13
0x18015ae79  pop     r12
0x18015ae7b  pop     rdi
0x18015ae7c  pop     rsi
0x18015ae7d  pop     rbp
0x18015ae7e  pop     rbx
0x18015ae7f  retn
```
