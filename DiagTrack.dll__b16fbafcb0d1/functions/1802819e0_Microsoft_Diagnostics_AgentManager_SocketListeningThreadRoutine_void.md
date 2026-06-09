# Microsoft::Diagnostics::AgentManager::SocketListeningThreadRoutine(void)

- ea: `0x1802819e0`
- end: `0x1802820c8`
- name: `?SocketListeningThreadRoutine@AgentManager@Diagnostics@Microsoft@@AEAAJXZ`
- size: `1768`
- prototype: `int __fastcall(const struct _GUID *this, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180282480`

## callees

- `0x1800029a8`
- `0x180003fe0`
- `0x180024558`
- `0x18004702c`
- `0x180049bec`
- `0x180052240`
- `0x180064e6c`
- `0x180064e8c`
- `0x18008035c`
- `0x18008a4ec`
- `0x18008abf4`
- `0x18009c8c0`
- `0x1800a346c`
- `0x1800a34b0`
- `0x1800ab56c`
- `0x1800b6204`
- `0x1800be65c`
- `0x180102bbc`
- `0x180142fcc`
- `0x1801bbc78`
- `0x1801d7508`
- `0x1801db1f4`
- `0x1801deac8`
- `0x1801f1710`
- `0x18020aac0`
- `0x18020bab8`
- `0x180279c88`
- `0x1802819e0`
- `0x1802820d0`
- `0x180282240`
- `0x1802824c4`
- `0x18029ec80`
- `0x18029f784`
- `0x1802fe908`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180281d5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180281f60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180281d5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180281f60`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180281b72`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180281b72`
- `WS2_32!__imp_WSAStartup` at `0x180281aa2`
- `WS2_32!__imp_WSAStartup` at `0x180281aa2`

## string_xrefs

- `0x180281ab7`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180281aef`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180281b2f`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180281c6d`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180281d2f`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180281f00`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x18028205e`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1802820a2`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1802820b2`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
int __fastcall Microsoft::Diagnostics::AgentManager::SocketListeningThreadRoutine(
        const struct _GUID *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  Microsoft::Diagnostics::ScenarioManager *v5; // rcx
  unsigned int InitialSettingsReadyMaxWait; // edi
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  const char *v8; // r9
  unsigned int v9; // eax
  int started; // eax
  int v12; // ebx
  int v13; // eax
  DWORD v14; // eax
  __int64 v15; // r8
  const char *v16; // r9
  __int64 **v17; // rdi
  __int64 **j; // rbx
  __int64 v19; // r8
  __int64 v20; // rbx
  int v21; // eax
  Microsoft::Diagnostics::HeartBeat *v22; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  const struct _GUID *v27; // rbx
  unsigned __int8 *Data4; // rdi
  __int64 v29; // r15
  __int64 *v30; // r12
  __int64 v31; // r8
  std::_Ref_count_base *v32; // r12
  unsigned int v33; // edi
  int v34; // ecx
  int v35; // r9d
  PTP_IO *v36; // rbx
  __int64 v37; // r8
  int v38; // eax
  __int64 v39; // r8
  __int64 *v40; // r8
  __int64 *v41; // rax
  __int64 *v42; // rcx
  __int64 *i; // rdx
  Microsoft::Diagnostics::HeartBeat *HeartbeatManager; // rax
  unsigned int v45; // [rsp+20h] [rbp-2B8h]
  int v46[2]; // [rsp+30h] [rbp-2A8h] BYREF
  __int64 *v47; // [rsp+38h] [rbp-2A0h] BYREF
  __int128 v48; // [rsp+40h] [rbp-298h] BYREF
  std::_Ref_count_base *v49[2]; // [rsp+50h] [rbp-288h] BYREF
  __int128 v50; // [rsp+60h] [rbp-278h] BYREF
  __int64 v51; // [rsp+70h] [rbp-268h]
  __int128 v52; // [rsp+80h] [rbp-258h] BYREF
  __int128 v53; // [rsp+90h] [rbp-248h] BYREF
  HANDLE Handles[2]; // [rsp+A0h] [rbp-238h] BYREF
  _BYTE v55[16]; // [rsp+B0h] [rbp-228h] BYREF
  __int128 v56; // [rsp+C0h] [rbp-218h] BYREF
  _BYTE v57[16]; // [rsp+D0h] [rbp-208h] BYREF
  _BYTE v58[16]; // [rsp+E0h] [rbp-1F8h] BYREF
  _BYTE v59[16]; // [rsp+F0h] [rbp-1E8h] BYREF
  struct WSAData WSAData; // [rsp+100h] [rbp-1D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( (unsigned __int16)(qword_1804632CA - 3) > 1u )
  {
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_180463150, 0, 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        a4);
    Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    InitialSettingsReadyMaxWait = Microsoft::Diagnostics::ScenarioManager::GetInitialSettingsReadyMaxWait(v5);
    ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    if ( !Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(*((void **)ScenarioManager + 4), InitialSettingsReadyMaxWait) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        v8);
  }
  memset_0(&WSAData, 0, sizeof(WSAData));
  v9 = WSAStartup(0x202u, &WSAData);
  if ( v9 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x82,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
             (const char *)v9,
             v45);
  wil::details::unique_storage<wil::details::resource_policy<bool,void (bool),&void wilp::CleanupWinsock(bool),wistd::integral_constant<unsigned __int64,0>,bool,bool,0,std::nullptr_t>>::reset(this[7].Data4);
  started = Microsoft::Diagnostics::AgentManager::StartAcceptingWindowsConnections(this);
  v12 = started;
  if ( started >= 0 )
  {
    if ( (unsigned __int16)(qword_1804632CA - 3) > 1u )
    {
      v13 = Microsoft::Diagnostics::AgentManager::StartAcceptingLinuxConnections(this);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v13,
          v45);
    }
    Handles[0] = *(HANDLE *)this[6].Data4;
    Handles[1] = *(HANDLE *)&this[7].Data1;
    while ( 1 )
    {
      v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !v14 )
        break;
      if ( v14 != 1 )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x102,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
                 v16);
      v50 = 0;
      v51 = 0;
      std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v55, &this[14], v15);
      v27 = this + 19;
      Data4 = this[19].Data4;
      if ( &v50 == (__int128 *)&this[19] )
      {
        v30 = 0;
        v29 = 0;
      }
      else
      {
        std::vector<std::wstring_view>::~vector<std::wstring_view>(&v50);
        v29 = *(_QWORD *)&v27->Data1;
        *(_QWORD *)&v50 = *(_QWORD *)&v27->Data1;
        v30 = *(__int64 **)Data4;
        *((_QWORD *)&v50 + 1) = *(_QWORD *)Data4;
        v51 = *(_QWORD *)&this[20].Data1;
        *(_QWORD *)&v27->Data1 = 0;
        *(_QWORD *)Data4 = 0;
        *(_QWORD *)&this[20].Data1 = 0;
      }
      v47 = v30;
      if ( *(_QWORD *)&v27->Data1 != *(_QWORD *)Data4 )
        *(_QWORD *)Data4 = *(_QWORD *)&v27->Data1;
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v55);
      while ( (__int64 *)v29 != v30 )
      {
        v32 = *(std::_Ref_count_base **)v29;
        *(_QWORD *)&v48 = *(_QWORD *)v29;
        v33 = *(_DWORD *)(v29 + 8);
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 32784) )
        {
          v46[0] = v33;
          v49[0] = v32;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            v34,
            (unsigned int)word_1803EB33A,
            v31,
            v35,
            (__int64)v49,
            (__int64)v46);
        }
        *(_OWORD *)v49 = 0;
        std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v57, &this[8], v31);
        std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned long,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned long>>,0>>::find(
          &this[13],
          &v52,
          &v48);
        if ( (_QWORD)v52 == *(_QWORD *)&this[13].Data1 )
        {
          v36 = (PTP_IO *)v49[0];
        }
        else
        {
          std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(v49);
          v36 = (PTP_IO *)v49[0];
          std::wstring::operator std::wstring_view((char *)v49[0] + 264, &v56, v37);
          v48 = v56;
          Microsoft::Diagnostics::AgentManager::LogConnectionTerminatedSynthetic(&v48, v33);
          v38 = Microsoft::Diagnostics::AgentTransport::Disconnect(
                  (Microsoft::Diagnostics::AgentTransport *)v36,
                  1,
                  v33,
                  1);
          if ( v38 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xEB,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
              (const char *)(unsigned int)v38,
              v45);
        }
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v57);
        if ( v36 )
        {
          v48 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v36, v59);
          Microsoft::Diagnostics::AgentWatsonCrashManager::ClearWatsonCrashRequestForAgent(this[50].Data4, &v48);
          WaitForThreadpoolIoCallbacks(v36[32], 1);
        }
        if ( v49[1] )
          std::_Ref_count_base::_Decref(v49[1]);
        std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v58, &this[8], v39);
        v40 = *(__int64 **)&this[13].Data1;
        v41 = (__int64 *)v40[1];
        v42 = v41;
        for ( i = v40; !*((_BYTE *)v42 + 25); v42 = (__int64 *)*v42 )
        {
          if ( v42[4] >= (unsigned __int64)v32 )
          {
            if ( *((_BYTE *)i + 25) && (unsigned __int64)v32 < v42[4] )
              i = v42;
            v40 = v42;
          }
          else
          {
            v42 += 2;
          }
        }
        if ( !*((_BYTE *)i + 25) )
          v41 = (__int64 *)*i;
        while ( !*((_BYTE *)v41 + 25) )
        {
          if ( (unsigned __int64)v32 >= v41[4] )
          {
            v41 = (__int64 *)v41[2];
          }
          else
          {
            i = v41;
            v41 = (__int64 *)*v41;
          }
        }
        *(_QWORD *)&v53 = v40;
        *((_QWORD *)&v53 + 1) = i;
        std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Diagnostics::AgentTransport>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Diagnostics::AgentTransport>>>,0>>::_Erase(
          &this[13],
          &v53);
        HeartbeatManager = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        Microsoft::Diagnostics::HeartBeat::DecreaseActiveAgentConnectionCount(HeartbeatManager);
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v58);
        v29 += 16;
        v30 = v47;
      }
      std::vector<std::wstring_view>::~vector<std::wstring_view>(&v50);
    }
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 32784) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1804543B0,
        word_1803EB37A);
    v17 = *(__int64 ***)&this[21].Data1;
    for ( j = (__int64 **)*v17; j != v17; j = (__int64 **)*j )
    {
      if ( j[4] )
      {
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 32784) )
        {
          v47 = j[3];
          *(_QWORD *)v46 = j[4];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v23,
            (unsigned int)byte_1803EB3A3,
            v24,
            v25,
            (__int64)v46,
            (__int64)&v47);
        }
        v26 = Microsoft::Diagnostics::AgentTransport::Disconnect(
                (Microsoft::Diagnostics::AgentTransport *)j[4],
                0,
                0,
                0);
        if ( v26 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAC,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)(unsigned int)v26,
            v45);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(
          j + 3,
          -1);
        WaitForThreadpoolIoCallbacks((PTP_IO)j[4][32], 1);
      }
    }
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 32784) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1804543B0,
        byte_1803EB30D);
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v48, &this[8], v15);
    v20 = **(_QWORD **)&this[13].Data1;
    *(_QWORD *)v46 = v20;
    while ( !*(_BYTE *)(v20 + 25) )
    {
      std::wstring::operator std::wstring_view(*(_QWORD *)(v20 + 40) + 264LL, &v53, v19);
      v52 = v53;
      Microsoft::Diagnostics::AgentManager::LogConnectionTerminatedSynthetic(&v52, 0);
      v21 = Microsoft::Diagnostics::AgentTransport::Disconnect(
              *(Microsoft::Diagnostics::AgentTransport **)(v20 + 40),
              1,
              0,
              1);
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v21,
          v45);
      v22 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::HeartBeat::DecreaseActiveAgentConnectionCount(v22);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>>>>,std::_Iterator_base0>::operator++(v46);
      v20 = *(_QWORD *)v46;
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v48);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)(unsigned int)started,
      v45);
    return v12;
  }
}

```

## disassembly

```asm
0x1802819e0  mov     [rsp+arg_8], rbx
0x1802819e5  mov     [rsp+arg_10], rsi
0x1802819ea  push    rdi
0x1802819eb  push    r12
0x1802819ed  push    r13
0x1802819ef  push    r14
0x1802819f1  push    r15
0x1802819f3  sub     rsp, 2B0h
0x1802819fa  mov     rax, cs:__security_cookie
0x180281a01  xor     rax, rsp
0x180281a04  mov     [rsp+2D8h+var_38], rax
0x180281a0c  mov     r14, rcx
0x180281a0f  movzx   eax, word ptr cs:qword_1804632CA
0x180281a16  sub     ax, 3
0x180281a1a  mov     r12d, 1
0x180281a20  xor     esi, esi
0x180281a22  cmp     ax, r12w
0x180281a26  jbe     short loc_180281A80
0x180281a28  xor     eax, eax
0x180281a2a  lock cmpxchg qword ptr cs:xmmword_180463150, rsi
0x180281a33  setz    al
0x180281a36  mov     rcx, [rsp+2D8h]; this
0x180281a3e  test    al, al
0x180281a40  jnz     loc_1802820A2
0x180281a46  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180281a4d  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x180281a52  call    ?GetInitialSettingsReadyMaxWait@ScenarioManager@Diagnostics@Microsoft@@QEAAKXZ; Microsoft::Diagnostics::ScenarioManager::GetInitialSettingsReadyMaxWait(void)
0x180281a57  mov     edi, eax
0x180281a59  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180281a60  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x180281a65  mov     rbx, [rsp+2D8h]
0x180281a6d  mov     edx, edi; unsigned int
0x180281a6f  mov     rcx, [rax+20h]; void *
0x180281a73  call    ?WaitOrTimeout@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXK@Z; Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(void *,ulong)
0x180281a78  test    al, al
0x180281a7a  jz      loc_1802820B2
0x180281a80  xor     edx, edx; Val
0x180281a82  mov     r8d, 198h; Size
0x180281a88  lea     rcx, [rsp+2D8h+WSAData]; void *
0x180281a90  call    memset_0
0x180281a95  mov     ecx, 202h; wVersionRequested
0x180281a9a  lea     rdx, [rsp+2D8h+WSAData]; lpWSAData
0x180281aa2  call    cs:__imp_WSAStartup
0x180281aa8  test    eax, eax
0x180281aaa  jz      short loc_180281ACD
0x180281aac  mov     rcx, [rsp+2D8h]; this
0x180281ab4  mov     r9d, eax; char *
0x180281ab7  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180281abe  mov     edx, 82h; void *
0x180281ac3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180281ac8  jmp     loc_180282075
0x180281acd  lea     rcx, [r14+78h]
0x180281ad1  call    ?reset@?$unique_storage@U?$resource_policy@_N$$A6AX_N@Z$1?CleanupWinsock@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_N_N$0A@$$T@details@wil@@@details@wil@@QEAAX_N@Z; wil::details::unique_storage<wil::details::resource_policy<bool,void (bool),&wilp::CleanupWinsock(bool),wistd::integral_constant<unsigned __int64,0>,bool,bool,0,std::nullptr_t>>::reset(bool)
0x180281ad6  mov     rcx, r14; this
0x180281ad9  call    ?StartAcceptingWindowsConnections@AgentManager@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::AgentManager::StartAcceptingWindowsConnections(void)
0x180281ade  mov     ebx, eax
0x180281ae0  test    eax, eax
0x180281ae2  jns     short loc_180281B07
0x180281ae4  mov     rcx, [rsp+2D8h]; this
0x180281aec  mov     r9d, eax; char *
0x180281aef  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180281af6  mov     edx, 86h; void *
0x180281afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180281b00  mov     eax, ebx
0x180281b02  jmp     loc_180282075
0x180281b07  movzx   eax, word ptr cs:qword_1804632CA
0x180281b0e  sub     ax, 3
0x180281b12  cmp     ax, r12w
0x180281b16  jbe     short loc_180281B40
0x180281b18  mov     rcx, r14; this
0x180281b1b  call    ?StartAcceptingLinuxConnections@AgentManager@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::AgentManager::StartAcceptingLinuxConnections(void)
0x180281b20  mov     rcx, [rsp+2D8h]; this
0x180281b28  test    eax, eax
0x180281b2a  jns     short loc_180281B40
0x180281b2c  mov     r9d, eax; char *
0x180281b2f  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180281b36  mov     edx, 8Ah; void *
0x180281b3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180281b40  mov     rax, [r14+68h]
0x180281b44  mov     [rsp+2D8h+Handles], rax
0x180281b4c  mov     rax, [r14+70h]
0x180281b50  mov     [rsp+2D8h+var_230], rax
0x180281b58  lea     r13, dword_1804543B0
0x180281b5f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180281b63  xor     r8d, r8d; bWaitAll
0x180281b66  lea     rdx, [rsp+2D8h+Handles]; lpHandles
0x180281b6e  lea     ecx, [r8+2]; nCount
0x180281b72  call    cs:__imp_WaitForMultipleObjects
0x180281b78  test    eax, eax
0x180281b7a  jnz     loc_180281D69
0x180281b80  mov     eax, cs:dword_1804543B0
0x180281b86  cmp     eax, 4
0x180281b89  jbe     short loc_180281BAB
0x180281b8b  mov     edx, 8010h
0x180281b90  mov     rcx, r13
0x180281b93  call    _tlgKeywordOn
0x180281b98  test    al, al
0x180281b9a  jz      short loc_180281BAB
0x180281b9c  lea     rdx, word_1803EB37A
0x180281ba3  mov     rcx, r13
0x180281ba6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180281bab  mov     rdi, [r14+150h]
0x180281bb2  mov     rbx, [rdi]
0x180281bb5  cmp     rbx, rdi
0x180281bb8  jnz     loc_180281CB7
0x180281bbe  mov     eax, cs:dword_1804543B0
0x180281bc4  cmp     eax, 4
0x180281bc7  jbe     short loc_180281BE9
0x180281bc9  mov     edx, 8010h
0x180281bce  mov     rcx, r13
0x180281bd1  call    _tlgKeywordOn
0x180281bd6  test    al, al
0x180281bd8  jz      short loc_180281BE9
0x180281bda  lea     rdx, byte_1803EB30D
0x180281be1  mov     rcx, r13
0x180281be4  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180281be9  lea     rdx, [r14+80h]
0x180281bf0  lea     rcx, [rsp+2D8h+var_298]
0x180281bf5  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180281bfa  nop
0x180281bfb  mov     rbx, [r14+0D0h]
0x180281c02  mov     rbx, [rbx]
0x180281c05  mov     qword ptr [rsp+2D8h+var_2A8], rbx
0x180281c0a  cmp     [rbx+19h], sil
0x180281c0e  jnz     loc_180281CA6
0x180281c14  mov     rcx, [rbx+28h]
0x180281c18  add     rcx, 108h
0x180281c1f  lea     rdx, [rsp+2D8h+var_248]
0x180281c27  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180281c2c  movaps  xmm0, [rsp+2D8h+var_248]
0x180281c34  movdqa  [rsp+2D8h+var_258], xmm0
0x180281c3d  xor     edx, edx
0x180281c3f  lea     rcx, [rsp+2D8h+var_258]
0x180281c47  call    ?LogConnectionTerminatedSynthetic@AgentManager@Diagnostics@Microsoft@@CAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@J@Z; Microsoft::Diagnostics::AgentManager::LogConnectionTerminatedSynthetic(std::wstring_view,long)
0x180281c4c  mov     r9b, r12b; bool
0x180281c4f  xor     r8d, r8d; int
0x180281c52  mov     dl, r12b; bool
0x180281c55  mov     rcx, [rbx+28h]; this
0x180281c59  call    ?Disconnect@AgentTransport@Diagnostics@Microsoft@@QEAAJ_NJ0@Z; Microsoft::Diagnostics::AgentTransport::Disconnect(bool,long,bool)
0x180281c5e  mov     rcx, [rsp+2D8h]; this
0x180281c66  test    eax, eax
0x180281c68  jns     short loc_180281C7E
0x180281c6a  mov     r9d, eax; char *
0x180281c6d  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180281c74  mov     edx, 0BEh; void *
0x180281c79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180281c7e  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180281c85  call    ?GetHeartbeatManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVHeartbeatManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(void)
0x180281c8a  mov     rcx, rax; this
0x180281c8d  call    ?DecreaseActiveAgentConnectionCount@HeartBeat@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::HeartBeat::DecreaseActiveAgentConnectionCount(void)
0x180281c92  lea     rcx, [rsp+2D8h+var_2A8]
0x180281c97  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>>>>,std::_Iterator_base0>::operator++(void)
0x180281c9c  mov     rbx, qword ptr [rsp+2D8h+var_2A8]
0x180281ca1  jmp     loc_180281C0A
0x180281ca6  lea     rcx, [rsp+2D8h+var_298]
0x180281cab  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180281cb0  xor     eax, eax
0x180281cb2  jmp     loc_180282075
0x180281cb7  cmp     [rbx+20h], rsi
0x180281cbb  jz      loc_180281D61
0x180281cc1  mov     eax, cs:dword_1804543B0
0x180281cc7  cmp     eax, 4
0x180281cca  jbe     short loc_180281D0F
0x180281ccc  mov     edx, 8010h
0x180281cd1  mov     rcx, r13
0x180281cd4  call    _tlgKeywordOn
0x180281cd9  test    al, al
0x180281cdb  jz      short loc_180281D0F
0x180281cdd  mov     rax, [rbx+18h]
0x180281ce1  mov     [rsp+2D8h+var_2A0], rax
0x180281ce6  mov     rax, [rbx+20h]
0x180281cea  mov     qword ptr [rsp+2D8h+var_2A8], rax
0x180281cef  lea     rax, [rsp+2D8h+var_2A0]
0x180281cf4  mov     [rsp+2D8h+var_2B0], rax
0x180281cf9  lea     rax, [rsp+2D8h+var_2A8]
0x180281cfe  mov     qword ptr [rsp+2D8h+var_2B8], rax; int
0x180281d03  lea     rdx, byte_1803EB3A3
0x180281d0a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180281d0f  xor     r9d, r9d; bool
0x180281d12  xor     r8d, r8d; int
0x180281d15  xor     edx, edx; bool
0x180281d17  mov     rcx, [rbx+20h]; this
0x180281d1b  call    ?Disconnect@AgentTransport@Diagnostics@Microsoft@@QEAAJ_NJ0@Z; Microsoft::Diagnostics::AgentTransport::Disconnect(bool,long,bool)
0x180281d20  test    eax, eax
0x180281d22  jns     short loc_180281D40
0x180281d24  mov     rcx, [rsp+2D8h]; this
0x180281d2c  mov     r9d, eax; char *
0x180281d2f  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180281d36  mov     edx, 0ACh; void *
0x180281d3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180281d40  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180281d44  lea     rcx, [rbx+18h]
0x180281d48  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(unsigned __int64)
0x180281d4d  mov     rcx, [rbx+20h]
0x180281d51  mov     edx, r12d; fCancelPendingCallbacks
0x180281d54  mov     rcx, [rcx+100h]; pio
0x180281d5b  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180281d61  mov     rbx, [rbx]
0x180281d64  jmp     loc_180281BB5
0x180281d69  cmp     eax, r12d
0x180281d6c  jnz     loc_180282056
0x180281d72  xorps   xmm0, xmm0
0x180281d75  movdqu  [rsp+2D8h+var_278], xmm0
0x180281d7b  mov     [rsp+2D8h+var_268], rsi
0x180281d80  lea     rdx, [r14+0E0h]
0x180281d87  lea     rcx, [rsp+2D8h+var_228]
0x180281d8f  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180281d94  lea     rbx, [r14+130h]
0x180281d9b  lea     rdi, [rbx+8]
0x180281d9f  lea     rax, [rsp+2D8h+var_278]
0x180281da4  cmp     rax, rbx
0x180281da7  jz      short loc_180281DD8
0x180281da9  lea     rcx, [rsp+2D8h+var_278]
0x180281dae  call    ??1?$vector@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring_view>::~vector<std::wstring_view>(void)
0x180281db3  mov     r15, [rbx]
0x180281db6  mov     qword ptr [rsp+2D8h+var_278], r15
0x180281dbb  mov     r12, [rdi]
0x180281dbe  mov     qword ptr [rsp+2D8h+var_278+8], r12
0x180281dc3  mov     rax, [rbx+10h]
0x180281dc7  mov     [rsp+2D8h+var_268], rax
0x180281dcc  mov     [rbx], rsi
0x180281dcf  mov     [rdi], rsi
0x180281dd2  mov     [rbx+10h], rsi
0x180281dd6  jmp     short loc_180281DDE
0x180281dd8  mov     r12, rsi
0x180281ddb  mov     r15, rsi
0x180281dde  mov     [rsp+2D8h+var_2A0], r12
0x180281de3  mov     rax, [rbx]
0x180281de6  cmp     rax, [rdi]
0x180281de9  jz      short loc_180281DEE
0x180281deb  mov     [rdi], rax
0x180281dee  lea     rcx, [rsp+2D8h+var_228]
0x180281df6  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180281dfb  cmp     r15, r12
0x180281dfe  jz      loc_180282041
0x180281e04  mov     r12, [r15]
0x180281e07  mov     qword ptr [rsp+2D8h+var_298], r12
0x180281e0c  mov     edi, [r15+8]
0x180281e10  mov     eax, cs:dword_1804543B0
0x180281e16  cmp     eax, 4
0x180281e19  jbe     short loc_180281E55
0x180281e1b  mov     edx, 8010h
0x180281e20  mov     rcx, r13
0x180281e23  call    _tlgKeywordOn
0x180281e28  test    al, al
0x180281e2a  jz      short loc_180281E55
0x180281e2c  mov     [rsp+2D8h+var_2A8], edi
0x180281e30  mov     [rsp+2D8h+var_288], r12
0x180281e35  lea     rax, [rsp+2D8h+var_2A8]
0x180281e3a  mov     [rsp+2D8h+var_2B0], rax
0x180281e3f  lea     rax, [rsp+2D8h+var_288]
0x180281e44  mov     qword ptr [rsp+2D8h+var_2B8], rax; int
0x180281e49  lea     rdx, word_1803EB33A
0x180281e50  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180281e55  xorps   xmm0, xmm0
0x180281e58  movdqu  xmmword ptr [rsp+2D8h+var_288], xmm0
0x180281e5e  lea     r13, [r14+80h]
0x180281e65  mov     rdx, r13
0x180281e68  lea     rcx, [rsp+2D8h+var_208]
0x180281e70  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180281e75  nop
0x180281e76  lea     rbx, [r14+0D0h]
0x180281e7d  lea     r8, [rsp+2D8h+var_298]
0x180281e82  lea     rdx, [rsp+2D8h+var_258]
0x180281e8a  mov     rcx, rbx
0x180281e8d  call    ?find@?$_Tree@V?$_Tmap_traits@_KKU?$less@_K@std@@V?$allocator@U?$pair@$$CB_KK@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KK@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,ulong,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,ulong>>,0>>::find(unsigned __int64 const &)
0x180281e92  mov     rdx, qword ptr [rsp+2D8h+var_258]
0x180281e9a  cmp     rdx, [rbx]
0x180281e9d  jz      short loc_180281F13
0x180281e9f  add     rdx, 28h ; '('
0x180281ea3  lea     rcx, [rsp+2D8h+var_288]
0x180281ea8  call    ??4?$shared_ptr@VITriggerInst@Diagnostics@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(std::shared_ptr<Microsoft::Diagnostics::ITriggerInst> const &)
0x180281ead  mov     rbx, [rsp+2D8h+var_288]
0x180281eb2  lea     rcx, [rbx+108h]
0x180281eb9  lea     rdx, [rsp+2D8h+var_218]
0x180281ec1  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180281ec6  movaps  xmm0, [rsp+2D8h+var_218]
0x180281ece  movdqa  [rsp+2D8h+var_298], xmm0
0x180281ed4  mov     edx, edi
0x180281ed6  lea     rcx, [rsp+2D8h+var_298]
0x180281edb  call    ?LogConnectionTerminatedSynthetic@AgentManager@Diagnostics@Microsoft@@CAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@J@Z; Microsoft::Diagnostics::AgentManager::LogConnectionTerminatedSynthetic(std::wstring_view,long)
0x180281ee0  mov     r9b, 1; bool
0x180281ee3  mov     r8d, edi; int
0x180281ee6  mov     dl, r9b; bool
0x180281ee9  mov     rcx, rbx; this
0x180281eec  call    ?Disconnect@AgentTransport@Diagnostics@Microsoft@@QEAAJ_NJ0@Z; Microsoft::Diagnostics::AgentTransport::Disconnect(bool,long,bool)
0x180281ef1  mov     rcx, [rsp+2D8h]; this
0x180281ef9  test    eax, eax
0x180281efb  jns     short loc_180281F18
0x180281efd  mov     r9d, eax; char *
0x180281f00  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180281f07  mov     edx, 0EBh; void *
0x180281f0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180281f11  jmp     short loc_180281F18
0x180281f13  mov     rbx, [rsp+2D8h+var_288]
0x180281f18  lea     rcx, [rsp+2D8h+var_208]
0x180281f20  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180281f25  test    rbx, rbx
0x180281f28  jz      short loc_180281F67
0x180281f2a  lea     rdx, [rsp+2D8h+var_1E8]
  ... truncated ...
```
