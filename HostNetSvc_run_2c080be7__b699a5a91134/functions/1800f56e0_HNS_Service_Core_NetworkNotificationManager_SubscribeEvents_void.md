# HNS::Service::Core::NetworkNotificationManager::SubscribeEvents(void)

- ea: `0x1800f56e0`
- end: `0x1800f5bed`
- name: `?SubscribeEvents@NetworkNotificationManager@Core@Service@HNS@@EEAAXXZ`
- size: `1293`
- prototype: `void __fastcall(HNS::Service::Core::NetworkNotificationManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800f5540`

## callees

- `0x18005f0c0`
- `0x18005f560`
- `0x180067c00`
- `0x1800684d0`
- `0x18006c530`
- `0x18007f178`
- `0x18008a024`
- `0x1800f0d2c`
- `0x1800f0d9c`
- `0x1800f1074`
- `0x1800f11f0`
- `0x1800f56e0`
- `0x18023f548`
- `0x18023fa80`
- `0x18023fb48`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f5bbf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f5bbf`
- `NetMgmtIF!NetMgmtGetNetworkAdapterType` at `0x1800f5ad7`
- `NetMgmtIF!NetMgmtGetNetworkAdapterType` at `0x1800f5ad7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800f5a96`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800f5a96`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800f5745`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800f5745`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800f572a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800f572a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800f5753`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800f5764`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800f5753`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800f5764`

## string_xrefs

- `0x1800f570f`: `SharedAccess`
- `0x1800f57cf`: `SharedAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall HNS::Service::Core::NetworkNotificationManager::SubscribeEvents(
        HNS::Service::Core::NetworkNotificationManager *this)
{
  const WCHAR *v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rbx
  SC_HANDLE v5; // rax
  char v6; // di
  struct HNS::Service::Util::ServiceManager *Instance; // rbx
  __int64 *Monitor; // rax
  __int64 v9; // rdx
  HNS::Service::Util::details::CallbackStorage *v10; // rbx
  HNS::Service::Util::details::CallbackStorage *v11; // rbx
  _QWORD *v12; // rdx
  _OWORD *v13; // rax
  _OWORD *v14; // rdx
  _OWORD *v15; // rax
  _OWORD *v16; // rdx
  _OWORD *v17; // rax
  _OWORD *v18; // rdx
  _OWORD *v19; // rax
  _OWORD *v20; // rdx
  __int64 v21; // r14
  __m128i si128; // xmm6
  int v23; // ebx
  int v24; // edi
  const OLECHAR *v25; // rcx
  LPCOLESTR *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  HNS::Service::Util::details::CallbackStorage *v30; // [rsp+38h] [rbp-D0h] BYREF
  int v31; // [rsp+40h] [rbp-C8h]
  int v32; // [rsp+44h] [rbp-C4h]
  int v33; // [rsp+48h] [rbp-C0h]
  int v34; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v35; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v36; // [rsp+58h] [rbp-B0h] BYREF
  __int64 (__fastcall *v37)(); // [rsp+68h] [rbp-A0h] BYREF
  int v38; // [rsp+70h] [rbp-98h]
  int v39; // [rsp+74h] [rbp-94h]
  __int64 (__fastcall *v40)(); // [rsp+78h] [rbp-90h] BYREF
  int v41; // [rsp+80h] [rbp-88h]
  int v42; // [rsp+84h] [rbp-84h]
  GUID pclsid; // [rsp+88h] [rbp-80h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+98h] [rbp-70h] BYREF
  __m128i v45; // [rsp+A8h] [rbp-60h]
  _QWORD v46[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v47; // [rsp+C8h] [rbp-40h]
  int v48; // [rsp+CCh] [rbp-3Ch]
  char v49; // [rsp+D0h] [rbp-38h]
  char *v50; // [rsp+D8h] [rbp-30h]
  _QWORD *v51; // [rsp+F0h] [rbp-18h]
  char v52; // [rsp+F8h] [rbp-10h] BYREF
  char v53; // [rsp+108h] [rbp+0h] BYREF

  v2 = *(const WCHAR **)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(
                          &pclsid,
                          L"SharedAccess");
  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, v2, 0x15u);
    if ( v5 )
    {
      CloseServiceHandle(v5);
      v6 = 1;
    }
    else
    {
      v6 = 0;
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v6 = 0;
  }
  if ( v6 )
  {
    Instance = HNS::Service::Util::ServiceManager::GetInstance();
    v46[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (HNS::Service::Core::NetworkNotificationManager::*)(enum HNS::Service::Util::ServiceState),HNS::Service::Core::NetworkNotificationManager *,std::_Ph<1> const &>,void,enum HNS::Service::Util::ServiceState>::`vftable';
    v46[1] = &HNS::Service::Core::NetworkNotificationManager::OnSharedAccessServiceStateChange;
    v47 = 0;
    v48 = *(_DWORD *)&pclsid.Data4[4];
    v49 = v33;
    v50 = (char *)this - 1496;
    v51 = v46;
    *(_OWORD *)lpsz = 0;
    v45 = 0;
    std::wstring::_Construct<1,unsigned short const *>(lpsz, L"SharedAccess");
    Monitor = (__int64 *)HNS::Service::Util::ServiceManager::GetMonitor(Instance, &v30, lpsz, v46, 1);
    v9 = *Monitor;
    *Monitor = 0;
    v10 = (HNS::Service::Util::details::CallbackStorage *)*((_QWORD *)this + 34);
    *((_QWORD *)this + 34) = v9;
    if ( v10 )
    {
      HNS::Service::Util::details::CallbackStorage::~CallbackStorage(v10);
      operator delete(v10, (const struct std::nothrow_t *)0x18);
    }
    v11 = v30;
    if ( v30 )
    {
      HNS::Service::Util::details::CallbackStorage::~CallbackStorage(v30);
      operator delete(v11, (const struct std::nothrow_t *)0x18);
    }
    std::wstring::~wstring(lpsz);
    if ( v51 )
    {
      v12 = v46;
      LOBYTE(v12) = v51 != v46;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v51 + 32LL))(v51, v12);
    }
  }
  v30 = (HNS::Service::Util::details::CallbackStorage *)HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceChanged;
  v31 = 0;
  v32 = *(_DWORD *)&pclsid.Data4[4];
  v13 = (_OWORD *)HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                    (unsigned int)*((_QWORD *)this + 29) + 104,
                    (unsigned int)&pclsid,
                    25,
                    this != (HNS::Service::Core::NetworkNotificationManager *)1496 ? (unsigned int)this : 0,
                    (__int64)&v30,
                    0);
  v14 = (_OWORD *)*((_QWORD *)this + 5);
  if ( v14 == *((_OWORD **)this + 6) )
  {
    std::vector<_GUID>::_Emplace_reallocate<_GUID &>((char *)this + 32, v14, v13);
  }
  else
  {
    *v14 = *v13;
    *((_QWORD *)this + 5) += 16LL;
  }
  v30 = (HNS::Service::Util::details::CallbackStorage *)HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceChanged;
  v31 = 0;
  v32 = *(_DWORD *)&pclsid.Data4[4];
  v15 = (_OWORD *)HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                    (unsigned int)*((_QWORD *)this + 29) + 104,
                    (unsigned int)&pclsid,
                    34,
                    this != (HNS::Service::Core::NetworkNotificationManager *)1496 ? (unsigned int)this : 0,
                    (__int64)&v30,
                    0);
  v16 = (_OWORD *)*((_QWORD *)this + 5);
  if ( v16 == *((_OWORD **)this + 6) )
  {
    std::vector<_GUID>::_Emplace_reallocate<_GUID &>((char *)this + 32, v16, v15);
  }
  else
  {
    *v16 = *v15;
    *((_QWORD *)this + 5) += 16LL;
  }
  v30 = (HNS::Service::Util::details::CallbackStorage *)HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceChanged;
  v31 = 0;
  v32 = *(_DWORD *)&pclsid.Data4[4];
  v17 = (_OWORD *)HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                    (unsigned int)*((_QWORD *)this + 29) + 104,
                    (unsigned int)&pclsid,
                    35,
                    this != (HNS::Service::Core::NetworkNotificationManager *)1496 ? (unsigned int)this : 0,
                    (__int64)&v30,
                    0);
  v18 = (_OWORD *)*((_QWORD *)this + 5);
  if ( v18 == *((_OWORD **)this + 6) )
  {
    std::vector<_GUID>::_Emplace_reallocate<_GUID &>((char *)this + 32, v18, v17);
  }
  else
  {
    *v18 = *v17;
    *((_QWORD *)this + 5) += 16LL;
  }
  v36 = 0;
  v30 = (HNS::Service::Util::details::CallbackStorage *)HNS::Service::Core::NetworkNotificationManager::OnNetworkCreated;
  v31 = 0;
  v32 = *(_DWORD *)&pclsid.Data4[4];
  v19 = (_OWORD *)HNS::Service::Events::FilteredEventManager<_GUID,HNS::Service::Common::GuidLessThan>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                    (unsigned int)*((_QWORD *)this + 27) + 392,
                    (unsigned int)&pclsid,
                    13,
                    this != (HNS::Service::Core::NetworkNotificationManager *)1496 ? (unsigned int)this : 0,
                    (__int64)&v30,
                    (__int64)&v36);
  v20 = (_OWORD *)*((_QWORD *)this + 2);
  if ( v20 == *((_OWORD **)this + 3) )
  {
    std::vector<_GUID>::_Emplace_reallocate<_GUID &>((char *)this + 8, v20, v19);
  }
  else
  {
    *v20 = *v19;
    *((_QWORD *)this + 2) += 16LL;
  }
  IPHelper::GetAdapterAddresses(&v36, 2, 134);
  v21 = *((_QWORD *)&v36 + 1);
  if ( *((_QWORD *)&v36 + 1) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v23 = *(_DWORD *)&pclsid.Data4[4];
    v24 = *(_DWORD *)&pclsid.Data4[4];
    do
    {
      *(_OWORD *)lpsz = 0;
      v45 = si128;
      LOWORD(lpsz[0]) = 0;
      if ( (unsigned __int8)GetMultiByteString(*(LPCCH *)(v21 + 16)) )
      {
        pclsid = 0;
        v25 = (const OLECHAR *)lpsz;
        if ( v45.m128i_i64[1] > 7uLL )
          v25 = lpsz[0];
        CLSIDFromString(v25, &pclsid);
        v34 = 0;
        LODWORD(v30) = 0;
        v35 = 0;
        v26 = lpsz;
        if ( v45.m128i_i64[1] > 7uLL )
          v26 = (LPCOLESTR *)lpsz[0];
        if ( (int)NetMgmtGetNetworkAdapterType(v26, &v34, &v30, &v35, (char *)&v35 + 4) >= 0 && v34 != 1 && !(_DWORD)v35 )
        {
          v27 = *(_QWORD *)(v21 + 224);
          v37 = HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceRemoved;
          v38 = 0;
          v39 = v23;
          HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
            *((_QWORD *)this + 29) + 104,
            (unsigned int)&v52,
            26,
            this != (HNS::Service::Core::NetworkNotificationManager *)1496 ? (unsigned int)this : 0,
            (__int64)&v37,
            v27);
          v28 = *(_QWORD *)(v21 + 224);
          v40 = HNS::Service::Core::NetworkNotificationManager::OnNetworkAddressChanged;
          v41 = 0;
          v42 = v24;
          v29 = HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                  (unsigned int)*((_QWORD *)this + 29) + 104,
                  (unsigned int)&v53,
                  28,
                  this != (HNS::Service::Core::NetworkNotificationManager *)1496 ? (unsigned int)this : 0,
                  (__int64)&v40,
                  v28);
          HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Add<_GUID>(
            (char *)this + 176,
            v21 + 224,
            v29);
        }
      }
      v21 = *(_QWORD *)(v21 + 8);
      std::wstring::~wstring(lpsz);
    }
    while ( v21 );
    v21 = *((_QWORD *)&v36 + 1);
  }
  if ( v21 )
    free((void *)v21);
}

```

## disassembly

```asm
0x1800f56e0  mov     rax, rsp
0x1800f56e3  push    rbp
0x1800f56e4  push    rbx
0x1800f56e5  push    rsi
0x1800f56e6  push    rdi
0x1800f56e7  push    r12
0x1800f56e9  push    r13
0x1800f56eb  push    r14
0x1800f56ed  push    r15
0x1800f56ef  lea     rbp, [rax-78h]
0x1800f56f3  sub     rsp, 138h
0x1800f56fa  movaps  xmmword ptr [rax-58h], xmm6
0x1800f56fe  mov     rax, cs:__security_cookie
0x1800f5705  xor     rax, rsp
0x1800f5708  mov     [rbp+70h+var_60], rax
0x1800f570c  mov     r15, rcx
0x1800f570f  lea     rdx, aSharedaccess; "SharedAccess"
0x1800f5716  lea     rcx, [rbp+70h+pclsid]
0x1800f571a  call    ??$?0$0N@@?$basic_zstring_view@G@wil@@QEAA@AEAY0N@$$CBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const (&)[13])
0x1800f571f  mov     rdi, [rax]
0x1800f5722  xor     edx, edx; lpDatabaseName
0x1800f5724  xor     ecx, ecx; lpMachineName
0x1800f5726  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800f572a  call    cs:__imp_OpenSCManagerW
0x1800f5730  mov     rbx, rax
0x1800f5733  xor     r13d, r13d
0x1800f5736  test    rax, rax
0x1800f5739  jz      short loc_1800F576C
0x1800f573b  lea     r8d, [r13+15h]; dwDesiredAccess
0x1800f573f  mov     rdx, rdi; lpServiceName
0x1800f5742  mov     rcx, rax; hSCManager
0x1800f5745  call    cs:__imp_OpenServiceW
0x1800f574b  test    rax, rax
0x1800f574e  jz      short loc_1800F575E
0x1800f5750  mov     rcx, rax; hSCObject
0x1800f5753  call    cs:__imp_CloseServiceHandle
0x1800f5759  mov     dil, 1
0x1800f575c  jmp     short loc_1800F5761
0x1800f575e  mov     dil, r13b
0x1800f5761  mov     rcx, rbx; hSCObject
0x1800f5764  call    cs:__imp_CloseServiceHandle
0x1800f576a  jmp     short loc_1800F576F
0x1800f576c  mov     dil, r13b
0x1800f576f  test    dil, dil
0x1800f5772  jz      loc_1800F5871
0x1800f5778  call    ?GetInstance@ServiceManager@Util@Service@HNS@@SAAEAV1234@XZ; HNS::Service::Util::ServiceManager::GetInstance(void)
0x1800f577d  mov     rbx, rax
0x1800f5780  lea     r8, [r15-5D8h]
0x1800f5787  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8NetworkNotificationManager@Core@Service@HNS@@EAAXW4ServiceState@Util@56@@ZPEAV3456@AEBU?$_Ph@$00@2@@std@@XW4ServiceState@Util@Service@HNS@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (HNS::Service::Core::NetworkNotificationManager::*)(HNS::Service::Util::ServiceState),HNS::Service::Core::NetworkNotificationManager *,std::_Ph<1> const &>,void,HNS::Service::Util::ServiceState>::`vftable'
0x1800f578e  mov     [rbp+70h+var_C0], rax
0x1800f5792  lea     rax, ?OnSharedAccessServiceStateChange@NetworkNotificationManager@Core@Service@HNS@@AEAAXW4ServiceState@Util@34@@Z; HNS::Service::Core::NetworkNotificationManager::OnSharedAccessServiceStateChange(HNS::Service::Util::ServiceState)
0x1800f5799  mov     [rbp+70h+var_B8], rax
0x1800f579d  mov     [rbp+70h+var_B0], r13d
0x1800f57a1  mov     ecx, dword ptr [rbp+70h+pclsid.Data4+4]
0x1800f57a4  mov     [rbp+70h+var_AC], ecx
0x1800f57a7  mov     cl, byte ptr [rsp+170h+var_130]
0x1800f57ab  mov     [rbp+70h+var_A8], cl
0x1800f57ae  mov     [rbp+70h+var_A0], r8
0x1800f57b2  lea     rax, [rbp+70h+var_C0]
0x1800f57b6  mov     [rbp+70h+var_88], rax
0x1800f57ba  xorps   xmm0, xmm0
0x1800f57bd  movups  xmmword ptr [rbp+70h+lpsz], xmm0
0x1800f57c1  xorps   xmm1, xmm1
0x1800f57c4  movdqu  [rbp+70h+var_D0], xmm1
0x1800f57c9  mov     r8d, 0Ch
0x1800f57cf  lea     rdx, aSharedaccess; "SharedAccess"
0x1800f57d6  lea     rcx, [rbp+70h+lpsz]
0x1800f57da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800f57df  nop
0x1800f57e0  mov     byte ptr [rsp+170h+var_150], 1
0x1800f57e5  lea     r9, [rbp+70h+var_C0]
0x1800f57e9  lea     r8, [rbp+70h+lpsz]
0x1800f57ed  lea     rdx, [rsp+170h+var_140]
0x1800f57f2  mov     rcx, rbx
0x1800f57f5  call    ?GetMonitor@ServiceManager@Util@Service@HNS@@QEAA?AV?$unique_ptr@VCallbackStorage@details@Util@Service@HNS@@U?$default_delete@VCallbackStorage@details@Util@Service@HNS@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@AEBV?$function@$$A6AXW4ServiceState@Util@Service@HNS@@@Z@6@_N@Z; HNS::Service::Util::ServiceManager::GetMonitor(std::wstring const &,std::function<void (HNS::Service::Util::ServiceState)> const &,bool)
0x1800f57fa  mov     rdx, [rax]
0x1800f57fd  mov     [rax], r13
0x1800f5800  mov     rbx, [r15+110h]
0x1800f5807  mov     [r15+110h], rdx
0x1800f580e  mov     edi, 18h
0x1800f5813  test    rbx, rbx
0x1800f5816  jz      short loc_1800F582A
0x1800f5818  mov     rcx, rbx; this
0x1800f581b  call    ??1CallbackStorage@details@Util@Service@HNS@@QEAA@XZ; HNS::Service::Util::details::CallbackStorage::~CallbackStorage(void)
0x1800f5820  mov     edx, edi; struct std::nothrow_t *
0x1800f5822  mov     rcx, rbx; void *
0x1800f5825  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f582a  mov     rbx, [rsp+170h+var_140]
0x1800f582f  test    rbx, rbx
0x1800f5832  jz      short loc_1800F5848
0x1800f5834  mov     rcx, rbx; this
0x1800f5837  call    ??1CallbackStorage@details@Util@Service@HNS@@QEAA@XZ; HNS::Service::Util::details::CallbackStorage::~CallbackStorage(void)
0x1800f583c  mov     rdx, rdi; struct std::nothrow_t *
0x1800f583f  mov     rcx, rbx; void *
0x1800f5842  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f5847  nop
0x1800f5848  lea     rcx, [rbp+70h+lpsz]; void *
0x1800f584c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f5851  nop
0x1800f5852  mov     rcx, [rbp+70h+var_88]
0x1800f5856  test    rcx, rcx
0x1800f5859  jz      short loc_1800F5871
0x1800f585b  mov     rax, [rcx]
0x1800f585e  lea     rdx, [rbp+70h+var_C0]
0x1800f5862  cmp     rcx, rdx
0x1800f5865  setnz   dl
0x1800f5868  mov     rax, [rax+20h]
0x1800f586c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5871  lea     rbx, [r15+20h]
0x1800f5875  lea     rcx, [r15-5D8h]
0x1800f587c  neg     rcx
0x1800f587f  sbb     r12, r12
0x1800f5882  and     r12, r15
0x1800f5885  lea     rdi, ?OnNetworkInterfaceChanged@NetworkNotificationManager@Core@Service@HNS@@AEAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z; HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceChanged(std::shared_ptr<HNS::Service::Events::Event> const &)
0x1800f588c  mov     [rsp+170h+var_140], rdi
0x1800f5891  mov     [rsp+170h+var_138], r13d
0x1800f5896  mov     ecx, dword ptr [rbp+70h+pclsid.Data4+4]
0x1800f5899  mov     [rsp+170h+var_134], ecx
0x1800f589d  mov     rcx, [r15+0E8h]
0x1800f58a4  add     rcx, 68h ; 'h'
0x1800f58a8  mov     [rsp+170h+var_148], r13
0x1800f58ad  lea     rax, [rsp+170h+var_140]
0x1800f58b2  mov     [rsp+170h+var_150], rax
0x1800f58b7  mov     r9, r12
0x1800f58ba  mov     r8d, 19h
0x1800f58c0  lea     rdx, [rbp+70h+pclsid]
0x1800f58c4  call    ??$SubscribeEvent@P8NetworkNotificationManager@Core@Service@HNS@@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z@?$FilteredEventManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@123@PEAVIEventHandleable@123@P8NetworkNotificationManager@Core@23@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@ZT_NET_LUID_LH@@@Z; HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(HNS::Service::Events::EventType,HNS::Service::Events::IEventHandleable *,bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &),_NET_LUID_LH)
0x1800f58c9  mov     rdx, [rbx+8]
0x1800f58cd  cmp     rdx, [rbx+10h]
0x1800f58d1  jz      short loc_1800F58E1
0x1800f58d3  movups  xmm0, xmmword ptr [rax]
0x1800f58d6  movdqu  xmmword ptr [rdx], xmm0
0x1800f58da  add     qword ptr [rbx+8], 10h
0x1800f58df  jmp     short loc_1800F58EC
0x1800f58e1  mov     r8, rax
0x1800f58e4  mov     rcx, rbx
0x1800f58e7  call    ??$_Emplace_reallocate@AEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEAU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID &>(_GUID * const,_GUID &)
0x1800f58ec  mov     [rsp+170h+var_140], rdi
0x1800f58f1  mov     [rsp+170h+var_138], r13d
0x1800f58f6  mov     ecx, dword ptr [rbp+70h+pclsid.Data4+4]
0x1800f58f9  mov     [rsp+170h+var_134], ecx
0x1800f58fd  mov     rcx, [r15+0E8h]
0x1800f5904  add     rcx, 68h ; 'h'
0x1800f5908  mov     [rsp+170h+var_148], r13
0x1800f590d  lea     rax, [rsp+170h+var_140]
0x1800f5912  mov     [rsp+170h+var_150], rax
0x1800f5917  mov     r9, r12
0x1800f591a  mov     r8d, 22h ; '"'
0x1800f5920  lea     rdx, [rbp+70h+pclsid]
0x1800f5924  call    ??$SubscribeEvent@P8NetworkNotificationManager@Core@Service@HNS@@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z@?$FilteredEventManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@123@PEAVIEventHandleable@123@P8NetworkNotificationManager@Core@23@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@ZT_NET_LUID_LH@@@Z; HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(HNS::Service::Events::EventType,HNS::Service::Events::IEventHandleable *,bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &),_NET_LUID_LH)
0x1800f5929  mov     rdx, [rbx+8]
0x1800f592d  cmp     rdx, [rbx+10h]
0x1800f5931  jz      short loc_1800F5941
0x1800f5933  movups  xmm0, xmmword ptr [rax]
0x1800f5936  movdqu  xmmword ptr [rdx], xmm0
0x1800f593a  add     qword ptr [rbx+8], 10h
0x1800f593f  jmp     short loc_1800F594C
0x1800f5941  mov     r8, rax
0x1800f5944  mov     rcx, rbx
0x1800f5947  call    ??$_Emplace_reallocate@AEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEAU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID &>(_GUID * const,_GUID &)
0x1800f594c  mov     [rsp+170h+var_140], rdi
0x1800f5951  mov     [rsp+170h+var_138], r13d
0x1800f5956  mov     ecx, dword ptr [rbp+70h+pclsid.Data4+4]
0x1800f5959  mov     [rsp+170h+var_134], ecx
0x1800f595d  mov     rcx, [r15+0E8h]
0x1800f5964  add     rcx, 68h ; 'h'
0x1800f5968  mov     [rsp+170h+var_148], r13
0x1800f596d  lea     rax, [rsp+170h+var_140]
0x1800f5972  mov     [rsp+170h+var_150], rax
0x1800f5977  mov     r9, r12
0x1800f597a  mov     r8d, 23h ; '#'
0x1800f5980  lea     rdx, [rbp+70h+pclsid]
0x1800f5984  call    ??$SubscribeEvent@P8NetworkNotificationManager@Core@Service@HNS@@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z@?$FilteredEventManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@123@PEAVIEventHandleable@123@P8NetworkNotificationManager@Core@23@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@ZT_NET_LUID_LH@@@Z; HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(HNS::Service::Events::EventType,HNS::Service::Events::IEventHandleable *,bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &),_NET_LUID_LH)
0x1800f5989  mov     rdx, [rbx+8]
0x1800f598d  cmp     rdx, [rbx+10h]
0x1800f5991  jz      short loc_1800F59A1
0x1800f5993  movups  xmm0, xmmword ptr [rax]
0x1800f5996  movdqu  xmmword ptr [rdx], xmm0
0x1800f599a  add     qword ptr [rbx+8], 10h
0x1800f599f  jmp     short loc_1800F59AC
0x1800f59a1  mov     r8, rax
0x1800f59a4  mov     rcx, rbx
0x1800f59a7  call    ??$_Emplace_reallocate@AEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEAU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID &>(_GUID * const,_GUID &)
0x1800f59ac  xorps   xmm0, xmm0
0x1800f59af  movdqa  [rsp+170h+var_128+8], xmm0
0x1800f59b5  lea     rax, ?OnNetworkCreated@NetworkNotificationManager@Core@Service@HNS@@AEAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z; HNS::Service::Core::NetworkNotificationManager::OnNetworkCreated(std::shared_ptr<HNS::Service::Events::Event> const &)
0x1800f59bc  mov     [rsp+170h+var_140], rax
0x1800f59c1  mov     [rsp+170h+var_138], r13d
0x1800f59c6  mov     eax, dword ptr [rbp+70h+pclsid.Data4+4]
0x1800f59c9  mov     [rsp+170h+var_134], eax
0x1800f59cd  mov     rcx, [r15+0D8h]
0x1800f59d4  add     rcx, 188h
0x1800f59db  lea     rax, [rsp+170h+var_128+8]
0x1800f59e0  mov     [rsp+170h+var_148], rax
0x1800f59e5  lea     rax, [rsp+170h+var_140]
0x1800f59ea  mov     [rsp+170h+var_150], rax
0x1800f59ef  mov     r9, r12
0x1800f59f2  mov     r8d, 0Dh
0x1800f59f8  lea     rdx, [rbp+70h+pclsid]
0x1800f59fc  call    ??$SubscribeEvent@P8NetworkNotificationManager@Core@Service@HNS@@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z@?$FilteredEventManager@U_GUID@@UGuidLessThan@Common@Service@HNS@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@123@PEAVIEventHandleable@123@P8NetworkNotificationManager@Core@23@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@ZU4@@Z; HNS::Service::Events::FilteredEventManager<_GUID,HNS::Service::Common::GuidLessThan>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(HNS::Service::Events::EventType,HNS::Service::Events::IEventHandleable *,bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &),_GUID)
0x1800f5a01  mov     rdx, [r15+10h]
0x1800f5a05  cmp     rdx, [r15+18h]
0x1800f5a09  jz      short loc_1800F5A19
0x1800f5a0b  movups  xmm0, xmmword ptr [rax]
0x1800f5a0e  movdqu  xmmword ptr [rdx], xmm0
0x1800f5a12  add     qword ptr [r15+10h], 10h
0x1800f5a17  jmp     short loc_1800F5A25
0x1800f5a19  mov     r8, rax
0x1800f5a1c  lea     rcx, [r15+8]
0x1800f5a20  call    ??$_Emplace_reallocate@AEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEAU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID &>(_GUID * const,_GUID &)
0x1800f5a25  mov     edx, 2
0x1800f5a2a  mov     r8d, 86h
0x1800f5a30  lea     rcx, [rsp+170h+var_128+8]
0x1800f5a35  call    ?GetAdapterAddresses@IPHelper@@SA?AV?$unique_ptr@U_IP_ADAPTER_ADDRESSES_LH@@UAutoFree@@@std@@KK@Z; IPHelper::GetAdapterAddresses(ulong,ulong)
0x1800f5a3a  nop
0x1800f5a3b  mov     r14, [rsp+170h+Block]
0x1800f5a40  test    r14, r14
0x1800f5a43  jz      loc_1800F5BB7
0x1800f5a49  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800f5a51  mov     ebx, dword ptr [rbp+70h+pclsid.Data4+4]
0x1800f5a54  mov     edi, dword ptr [rbp+70h+pclsid.Data4+4]
0x1800f5a57  xorps   xmm0, xmm0
0x1800f5a5a  movups  xmmword ptr [rbp+70h+lpsz], xmm0
0x1800f5a5e  movdqu  [rbp+70h+var_D0], xmm6
0x1800f5a63  mov     word ptr [rbp+70h+lpsz], r13w
0x1800f5a68  lea     rdx, [rbp+70h+lpsz]
0x1800f5a6c  mov     rcx, [r14+10h]
0x1800f5a70  call    ?GetMultiByteString@@YA_NPEBDAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetMultiByteString(char const *,std::wstring &)
0x1800f5a75  test    al, al
0x1800f5a77  jz      loc_1800F5B9C
0x1800f5a7d  xorps   xmm0, xmm0
0x1800f5a80  movups  xmmword ptr [rbp+70h+pclsid.Data1], xmm0
0x1800f5a84  lea     rcx, [rbp+70h+lpsz]
0x1800f5a88  cmp     qword ptr [rbp+70h+var_D0+8], 7
0x1800f5a8d  cmova   rcx, [rbp+70h+lpsz]; lpsz
0x1800f5a92  lea     rdx, [rbp+70h+pclsid]; pclsid
0x1800f5a96  call    cs:__imp_CLSIDFromString
0x1800f5a9c  mov     [rsp+170h+var_12C], r13d
0x1800f5aa1  mov     dword ptr [rsp+170h+var_140], r13d
0x1800f5aa6  mov     dword ptr [rsp+170h+var_128], r13d
0x1800f5aab  mov     dword ptr [rsp+170h+var_128+4], r13d
0x1800f5ab0  lea     rcx, [rbp+70h+lpsz]
0x1800f5ab4  cmp     qword ptr [rbp+70h+var_D0+8], 7
0x1800f5ab9  cmova   rcx, [rbp+70h+lpsz]
0x1800f5abe  lea     rax, [rsp+170h+var_128+4]
0x1800f5ac3  mov     [rsp+170h+var_150], rax
0x1800f5ac8  lea     r9, [rsp+170h+var_128]
0x1800f5acd  lea     r8, [rsp+170h+var_140]
0x1800f5ad2  lea     rdx, [rsp+170h+var_12C]
0x1800f5ad7  call    cs:__imp_NetMgmtGetNetworkAdapterType
0x1800f5add  test    eax, eax
0x1800f5adf  js      loc_1800F5B9C
0x1800f5ae5  cmp     [rsp+170h+var_12C], 1
0x1800f5aea  jz      loc_1800F5B9C
0x1800f5af0  cmp     dword ptr [rsp+170h+var_128], r13d
0x1800f5af5  jnz     loc_1800F5B9C
0x1800f5afb  lea     rsi, [r14+0E0h]
0x1800f5b02  mov     rax, [rsi]
0x1800f5b05  lea     rcx, ?OnNetworkInterfaceRemoved@NetworkNotificationManager@Core@Service@HNS@@AEAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z; HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceRemoved(std::shared_ptr<HNS::Service::Events::Event> const &)
0x1800f5b0c  mov     qword ptr [rsp+170h+var_110], rcx
0x1800f5b11  mov     dword ptr [rsp+170h+var_108], r13d
0x1800f5b16  mov     dword ptr [rsp+170h+var_108+4], ebx
0x1800f5b1a  mov     rcx, [r15+0E8h]
0x1800f5b21  add     rcx, 68h ; 'h'
0x1800f5b25  mov     [rsp+170h+var_148], rax
0x1800f5b2a  lea     rax, [rsp+170h+var_110]
0x1800f5b2f  mov     [rsp+170h+var_150], rax
0x1800f5b34  mov     r9, r12
0x1800f5b37  mov     r8d, 1Ah
0x1800f5b3d  lea     rdx, [rbp+70h+var_80]
0x1800f5b41  call    ??$SubscribeEvent@P8NetworkNotificationManager@Core@Service@HNS@@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z@?$FilteredEventManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@123@PEAVIEventHandleable@123@P8NetworkNotificationManager@Core@23@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@ZT_NET_LUID_LH@@@Z; HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(HNS::Service::Events::EventType,HNS::Service::Events::IEventHandleable *,bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &),_NET_LUID_LH)
0x1800f5b46  mov     rax, [rsi]
0x1800f5b49  lea     rcx, ?OnNetworkAddressChanged@NetworkNotificationManager@Core@Service@HNS@@AEAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z; HNS::Service::Core::NetworkNotificationManager::OnNetworkAddressChanged(std::shared_ptr<HNS::Service::Events::Event> const &)
0x1800f5b50  mov     qword ptr [rsp+170h+var_100], rcx
0x1800f5b55  mov     [rsp+170h+var_F8], r13d
0x1800f5b5a  mov     [rsp+170h+var_F4], edi
0x1800f5b5e  mov     rcx, [r15+0E8h]
0x1800f5b65  add     rcx, 68h ; 'h'
0x1800f5b69  mov     [rsp+170h+var_148], rax
0x1800f5b6e  lea     rax, [rsp+170h+var_100]
0x1800f5b73  mov     [rsp+170h+var_150], rax
0x1800f5b78  mov     r9, r12
0x1800f5b7b  mov     r8d, 1Ch
0x1800f5b81  lea     rdx, [rbp+70h+var_70]
0x1800f5b85  call    ??$SubscribeEvent@P8NetworkNotificationManager@Core@Service@HNS@@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z@?$FilteredEventManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@123@PEAVIEventHandleable@123@P8NetworkNotificationManager@Core@23@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@ZT_NET_LUID_LH@@@Z; HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(HNS::Service::Events::EventType,HNS::Service::Events::IEventHandleable *,bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &),_NET_LUID_LH)
0x1800f5b8a  lea     rcx, [r15+0B0h]
0x1800f5b91  mov     r8, rax
0x1800f5b94  mov     rdx, rsi
0x1800f5b97  call    ??$Add@U_GUID@@@?$ConcurrentMap@T_NET_LUID_LH@@U_GUID@@UNET_LUID_Comparator@@@Common@Service@HNS@@QEAAXAEBT_NET_LUID_LH@@$$QEAU_GUID@@@Z; HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Add<_GUID>(_NET_LUID_LH const &,_GUID &&)
0x1800f5b9c  mov     r14, [r14+8]
0x1800f5ba0  lea     rcx, [rbp+70h+lpsz]; void *
0x1800f5ba4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f5ba9  test    r14, r14
0x1800f5bac  jnz     loc_1800F5A57
0x1800f5bb2  mov     r14, [rsp+170h+Block]
0x1800f5bb7  test    r14, r14
0x1800f5bba  jz      short loc_1800F5BC5
0x1800f5bbc  mov     rcx, r14; Block
0x1800f5bbf  call    cs:__imp_free
0x1800f5bc5  mov     rcx, [rbp+70h+var_60]
  ... truncated ...
```
