# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>(void)

- ea: `0x140007e20`
- end: `0x14000821d`
- name: `??0?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAA@XZ`
- size: `1021`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140011850`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140007e20`
- `0x140008e64`
- `0x14003c034`
- `0x14003c258`
- `0x140049250`
- `0x14004b680`
- `0x140055cec`
- `0x14006a010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x140007ec0`
- `KERNEL32!InitializeCriticalSection` at `0x140007f9d`
- `KERNEL32!InitializeCriticalSection` at `0x140007ec0`
- `KERNEL32!InitializeCriticalSection` at `0x140007f9d`

## string_xrefs

- `0x140008162`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ClientServiceT`
- `0x14000818e`: `ClientService object created`

## pseudocode

```c
__int64 __fastcall AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>(
        __int64 a1)
{
  char *v2; // rsi
  __int64 v3; // rdx
  volatile signed __int32 *v4; // rbx
  _QWORD *v5; // rax
  _DWORD *v6; // rax
  volatile signed __int32 *v7; // rbx
  __int64 *Instance; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rbx
  _DWORD *v14; // rax
  volatile signed __int32 *v15; // rbx
  _DWORD *v17; // [rsp+20h] [rbp-69h]
  char *v18; // [rsp+20h] [rbp-69h]
  __int128 v19; // [rsp+30h] [rbp-59h] BYREF
  __int64 v20; // [rsp+40h] [rbp-49h]
  __int64 v21; // [rsp+48h] [rbp-41h]
  __int128 v22; // [rsp+50h] [rbp-39h] BYREF
  __int64 v23; // [rsp+60h] [rbp-29h]
  __int64 v24; // [rsp+68h] [rbp-21h]
  _QWORD v25[4]; // [rsp+70h] [rbp-19h] BYREF
  int v26; // [rsp+90h] [rbp+7h]

  *(_QWORD *)a1 = &AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_DWORD *)(a1 + 104) = 2;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  v2 = (char *)operator new(0x78u);
  *(_QWORD *)v2 = &AppV::Client::Host::ClientManagerImpl::`vftable';
  *((_QWORD *)v2 + 1) = v2 + 104;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
  *((_QWORD *)v2 + 7) = 0;
  v2[64] = 0;
  *((_QWORD *)v2 + 9) = 0;
  *((_QWORD *)v2 + 10) = 0;
  *((_QWORD *)v2 + 11) = 0;
  *((_QWORD *)v2 + 12) = 0;
  *(_QWORD *)v2 = &AppV::Client::Host::EnterpriseClientManager::`vftable';
  std::map<enum AppV::Client::ComponentType,std::wstring>::map<enum AppV::Client::ComponentType,std::wstring>(
    (_QWORD *)v2 + 13,
    v3,
    g_header_init_InitializeResultHeader);
  v17 = operator new(0x18u);
  *(_OWORD *)v17 = 0;
  v17[2] = 1;
  v17[3] = 1;
  *(_QWORD *)v17 = &std::_Ref_count<AppV::Client::Host::EnterpriseClientManager>::`vftable';
  *((_QWORD *)v17 + 2) = v2;
  *(_QWORD *)(a1 + 8) = v2;
  v4 = *(volatile signed __int32 **)(a1 + 16);
  *(_QWORD *)(a1 + 16) = v17;
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v18 = (char *)operator new(0x58u);
  *(_QWORD *)v18 = &AppV::Client::Service::NotificationManagerImpl::`vftable'{for `AppV::Client::Service::NotificationManager'};
  *((_QWORD *)v18 + 1) = &AppV::Client::Service::NotificationManagerImpl::`vftable'{for `AppV::Client::ClientEventSink'};
  InitializeCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
  *((_QWORD *)v18 + 7) = 0;
  v18[64] = 0;
  *((_QWORD *)v18 + 9) = 0;
  *((_QWORD *)v18 + 10) = 0;
  v5 = operator new(0x38u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *((_QWORD *)v18 + 9) = v5;
  v6 = operator new(0x18u);
  *(_QWORD *)&v19 = v6;
  *(_OWORD *)v6 = 0;
  v6[2] = 1;
  v6[3] = 1;
  *(_QWORD *)v6 = &std::_Ref_count<AppV::Client::Service::NotificationManagerImpl>::`vftable';
  *((_QWORD *)v6 + 2) = v18;
  *(_QWORD *)(a1 + 24) = v18;
  v7 = *(volatile signed __int32 **)(a1 + 32);
  *(_QWORD *)(a1 + 32) = v6;
  if ( v7 )
  {
    if ( !_InterlockedDecrement(v7 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( !_InterlockedDecrement(v7 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  Instance = (__int64 *)AppV::Client::Host::UserManagerImpl::GetInstance(&v19);
  v9 = *Instance;
  v10 = Instance[1];
  *Instance = 0;
  Instance[1] = 0;
  *(_QWORD *)(a1 + 40) = v9;
  v11 = *(volatile signed __int32 **)(a1 + 48);
  *(_QWORD *)(a1 + 48) = v10;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v12 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
  if ( *((_QWORD *)&v19 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  *(_QWORD *)&v19 = operator new(0x78u);
  v13 = AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>(v19);
  *(_QWORD *)&v19 = v13;
  v14 = operator new(0x18u);
  *(_QWORD *)&v19 = v14;
  *(_OWORD *)v14 = 0;
  v14[2] = 1;
  v14[3] = 1;
  *(_QWORD *)v14 = &std::_Ref_count<AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>>::`vftable';
  *((_QWORD *)v14 + 2) = v13;
  *(_QWORD *)(a1 + 56) = v13;
  v15 = *(volatile signed __int32 **)(a1 + 64);
  *(_QWORD *)(a1 + 64) = v14;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  std::string::string(
    v25,
    "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ClientServiceT");
  v26 = 335;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v22, L"ClientService object created", 0x1Cu);
  v19 = 0;
  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"Client", 6u);
  AppV::DecoratedLog::operator()(v25, 8, &v19, &v22);
  std::wstring::~wstring(&v19);
  std::wstring::~wstring(&v22);
  std::string::~string(v25);
  return a1;
}

```

## disassembly

```asm
0x140007e20  push    rbp
0x140007e22  push    rbx
0x140007e23  push    rsi
0x140007e24  push    rdi
0x140007e25  push    r12
0x140007e27  push    r13
0x140007e29  push    r14
0x140007e2b  push    r15
0x140007e2d  lea     rbp, [rsp-1Fh]
0x140007e32  sub     rsp, 0A8h
0x140007e39  mov     rax, cs:__security_cookie
0x140007e40  xor     rax, rsp
0x140007e43  mov     [rbp+57h+var_48], rax
0x140007e47  mov     r14, rcx
0x140007e4a  mov     [rbp+57h+var_B8], rcx
0x140007e4e  lea     rax, ??_7?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@6B@; const AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::`vftable'
0x140007e55  mov     [rcx], rax
0x140007e58  xor     r15d, r15d
0x140007e5b  mov     [rcx+8], r15
0x140007e5f  mov     [rcx+10h], r15
0x140007e63  mov     [rcx+18h], r15
0x140007e67  mov     [rcx+20h], r15
0x140007e6b  mov     [rcx+28h], r15
0x140007e6f  mov     [rcx+30h], r15
0x140007e73  mov     [rcx+38h], r15
0x140007e77  mov     [rcx+40h], r15
0x140007e7b  mov     [rcx+48h], r15d
0x140007e7f  mov     [rcx+50h], r15
0x140007e83  mov     [rcx+58h], r15
0x140007e87  mov     [rcx+60h], r15
0x140007e8b  mov     dword ptr [rcx+68h], 2
0x140007e92  mov     [rcx+70h], r15
0x140007e96  mov     [rcx+78h], r15
0x140007e9a  lea     ecx, [r15+78h]; Size
0x140007e9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007ea3  mov     rsi, rax
0x140007ea6  mov     [rbp+57h+var_C0], rax
0x140007eaa  lea     rax, ??_7ClientManagerImpl@Host@Client@AppV@@6B@; const AppV::Client::Host::ClientManagerImpl::`vftable'
0x140007eb1  mov     [rsi], rax
0x140007eb4  lea     rdi, [rsi+68h]
0x140007eb8  mov     [rsi+8], rdi
0x140007ebc  lea     rcx, [rsi+10h]; lpCriticalSection
0x140007ec0  call    cs:__imp_InitializeCriticalSection
0x140007ec6  mov     [rsi+38h], r15
0x140007eca  mov     [rsi+40h], r15b
0x140007ece  mov     [rsi+48h], r15
0x140007ed2  mov     [rsi+50h], r15
0x140007ed6  mov     [rsi+58h], r15
0x140007eda  mov     [rsi+60h], r15
0x140007ede  lea     rax, ??_7EnterpriseClientManager@Host@Client@AppV@@6B@; const AppV::Client::Host::EnterpriseClientManager::`vftable'
0x140007ee5  mov     [rsi], rax
0x140007ee8  lea     r8, g_header_init_InitializeResultHeader
0x140007eef  mov     rcx, rdi
0x140007ef2  call    ??$?0PEBU?$pair@W4ComponentType@Client@AppV@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@?$map@W4ComponentType@Client@AppV@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4ComponentType@Client@AppV@@@5@V?$allocator@U?$pair@$$CBW4ComponentType@Client@AppV@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@5@@std@@QEAA@PEBU?$pair@W4ComponentType@Client@AppV@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@0@Z; std::map<AppV::Client::ComponentType,std::wstring>::map<AppV::Client::ComponentType,std::wstring>(std::pair<AppV::Client::ComponentType,std::wstring> const *,std::pair<AppV::Client::ComponentType,std::wstring> const *)
0x140007ef7  nop
0x140007ef8  mov     [rbp+57h+var_C0], rsi
0x140007efc  lea     r13d, [r15+18h]
0x140007f00  mov     ecx, r13d; Size
0x140007f03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007f08  mov     [rbp+57h+var_C0], rax
0x140007f0c  xorps   xmm0, xmm0
0x140007f0f  movups  xmmword ptr [rax], xmm0
0x140007f12  lea     r12d, [r15+1]
0x140007f16  mov     [rax+8], r12d
0x140007f1a  mov     [rax+0Ch], r12d
0x140007f1e  lea     rcx, ??_7?$_Ref_count@VEnterpriseClientManager@Host@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Host::EnterpriseClientManager>::`vftable'
0x140007f25  mov     [rax], rcx
0x140007f28  mov     [rax+10h], rsi
0x140007f2c  mov     [r14+8], rsi
0x140007f30  mov     rbx, [r14+10h]
0x140007f34  mov     [r14+10h], rax
0x140007f38  or      esi, 0FFFFFFFFh
0x140007f3b  test    rbx, rbx
0x140007f3e  jz      short loc_140007F73
0x140007f40  mov     eax, esi
0x140007f42  lock xadd [rbx+8], eax
0x140007f47  add     eax, esi
0x140007f49  jnz     short loc_140007F73
0x140007f4b  mov     rax, [rbx]
0x140007f4e  mov     rcx, rbx
0x140007f51  mov     rax, [rax]
0x140007f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f59  mov     eax, esi
0x140007f5b  lock xadd [rbx+0Ch], eax
0x140007f60  add     eax, esi
0x140007f62  jnz     short loc_140007F73
0x140007f64  mov     rax, [rbx]
0x140007f67  mov     rcx, rbx
0x140007f6a  mov     rax, [rax+8]
0x140007f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f73  mov     ecx, 58h ; 'X'; Size
0x140007f78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007f7d  mov     rdi, rax
0x140007f80  mov     [rbp+57h+var_C0], rax
0x140007f84  lea     rax, ??_7NotificationManagerImpl@Service@Client@AppV@@6BNotificationManager@123@@; const AppV::Client::Service::NotificationManagerImpl::`vftable'{for `AppV::Client::Service::NotificationManager'}
0x140007f8b  mov     [rdi], rax
0x140007f8e  lea     rax, ??_7NotificationManagerImpl@Service@Client@AppV@@6BClientEventSink@23@@; const AppV::Client::Service::NotificationManagerImpl::`vftable'{for `AppV::Client::ClientEventSink'}
0x140007f95  mov     [rdi+8], rax
0x140007f99  lea     rcx, [rdi+10h]; lpCriticalSection
0x140007f9d  call    cs:__imp_InitializeCriticalSection
0x140007fa3  mov     [rdi+38h], r15
0x140007fa7  mov     [rdi+40h], r15b
0x140007fab  mov     [rdi+48h], r15
0x140007faf  mov     [rdi+50h], r15
0x140007fb3  mov     ecx, 38h ; '8'; Size
0x140007fb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007fbd  mov     [rax], rax
0x140007fc0  mov     [rax+8], rax
0x140007fc4  mov     [rax+10h], rax
0x140007fc8  mov     word ptr [rax+18h], 101h
0x140007fce  mov     [rdi+48h], rax
0x140007fd2  mov     qword ptr [rbp+57h+var_B0], rdi
0x140007fd6  mov     rcx, r13; Size
0x140007fd9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007fde  mov     qword ptr [rbp+57h+var_B0], rax
0x140007fe2  xorps   xmm0, xmm0
0x140007fe5  movups  xmmword ptr [rax], xmm0
0x140007fe8  mov     [rax+8], r12d
0x140007fec  mov     [rax+0Ch], r12d
0x140007ff0  lea     rcx, ??_7?$_Ref_count@VNotificationManagerImpl@Service@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Service::NotificationManagerImpl>::`vftable'
0x140007ff7  mov     [rax], rcx
0x140007ffa  mov     [rax+10h], rdi
0x140007ffe  mov     [r14+18h], rdi
0x140008002  mov     rbx, [r14+20h]
0x140008006  mov     [r14+20h], rax
0x14000800a  test    rbx, rbx
0x14000800d  jz      short loc_140008042
0x14000800f  mov     eax, esi
0x140008011  lock xadd [rbx+8], eax
0x140008016  add     eax, esi
0x140008018  jnz     short loc_140008042
0x14000801a  mov     rax, [rbx]
0x14000801d  mov     rcx, rbx
0x140008020  mov     rax, [rax]
0x140008023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008028  mov     eax, esi
0x14000802a  lock xadd [rbx+0Ch], eax
0x14000802f  add     eax, esi
0x140008031  jnz     short loc_140008042
0x140008033  mov     rax, [rbx]
0x140008036  mov     rcx, rbx
0x140008039  mov     rax, [rax+8]
0x14000803d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008042  lea     rcx, [rbp+57h+var_B0]
0x140008046  call    ?GetInstance@UserManagerImpl@Host@Client@AppV@@CA?AV?$shared_ptr@VUserManagerImpl@Host@Client@AppV@@@std@@XZ; AppV::Client::Host::UserManagerImpl::GetInstance(void)
0x14000804b  mov     rcx, [rax]
0x14000804e  mov     rdx, [rax+8]
0x140008052  mov     [rax], r15
0x140008055  mov     [rax+8], r15
0x140008059  mov     [r14+28h], rcx
0x14000805d  mov     rbx, [r14+30h]
0x140008061  mov     [r14+30h], rdx
0x140008065  test    rbx, rbx
0x140008068  jz      short loc_14000809D
0x14000806a  mov     eax, esi
0x14000806c  lock xadd [rbx+8], eax
0x140008071  add     eax, esi
0x140008073  jnz     short loc_14000809D
0x140008075  mov     rax, [rbx]
0x140008078  mov     rcx, rbx
0x14000807b  mov     rax, [rax]
0x14000807e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008083  mov     eax, esi
0x140008085  lock xadd [rbx+0Ch], eax
0x14000808a  add     eax, esi
0x14000808c  jnz     short loc_14000809D
0x14000808e  mov     rax, [rbx]
0x140008091  mov     rcx, rbx
0x140008094  mov     rax, [rax+8]
0x140008098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000809d  mov     rbx, qword ptr [rbp+57h+var_B0+8]
0x1400080a1  test    rbx, rbx
0x1400080a4  jz      short loc_1400080D9
0x1400080a6  mov     eax, esi
0x1400080a8  lock xadd [rbx+8], eax
0x1400080ad  add     eax, esi
0x1400080af  jnz     short loc_1400080D9
0x1400080b1  mov     rax, [rbx]
0x1400080b4  mov     rcx, rbx
0x1400080b7  mov     rax, [rax]
0x1400080ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080bf  mov     eax, esi
0x1400080c1  lock xadd [rbx+0Ch], eax
0x1400080c6  add     eax, esi
0x1400080c8  jnz     short loc_1400080D9
0x1400080ca  mov     rax, [rbx]
0x1400080cd  mov     rcx, rbx
0x1400080d0  mov     rax, [rax+8]
0x1400080d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080d9  mov     ecx, 78h ; 'x'; Size
0x1400080de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400080e3  mov     qword ptr [rbp+57h+var_B0], rax
0x1400080e7  mov     rcx, rax
0x1400080ea  call    ??0?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@QEAA@XZ; AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>(void)
0x1400080ef  mov     rbx, rax
0x1400080f2  mov     qword ptr [rbp+57h+var_B0], rax
0x1400080f6  mov     rcx, r13; Size
0x1400080f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400080fe  mov     qword ptr [rbp+57h+var_B0], rax
0x140008102  xorps   xmm0, xmm0
0x140008105  movups  xmmword ptr [rax], xmm0
0x140008108  mov     [rax+8], r12d
0x14000810c  mov     [rax+0Ch], r12d
0x140008110  lea     rcx, ??_7?$_Ref_count@V?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>>::`vftable'
0x140008117  mov     [rax], rcx
0x14000811a  mov     [rax+10h], rbx
0x14000811e  mov     [r14+38h], rbx
0x140008122  mov     rbx, [r14+40h]
0x140008126  mov     [r14+40h], rax
0x14000812a  test    rbx, rbx
0x14000812d  jz      short loc_140008162
0x14000812f  mov     eax, esi
0x140008131  lock xadd [rbx+8], eax
0x140008136  add     eax, esi
0x140008138  jnz     short loc_140008162
0x14000813a  mov     rax, [rbx]
0x14000813d  mov     rcx, rbx
0x140008140  mov     rax, [rax]
0x140008143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008148  mov     eax, esi
0x14000814a  lock xadd [rbx+0Ch], eax
0x14000814f  add     eax, esi
0x140008151  jnz     short loc_140008162
0x140008153  mov     rax, [rbx]
0x140008156  mov     rcx, rbx
0x140008159  mov     rax, [rax+8]
0x14000815d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008162  lea     rdx, aAppvClientServ_31; "AppV::Client::Service::ClientServiceT<s"...
0x140008169  lea     rcx, [rbp+57h+var_70]
0x14000816d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140008172  mov     [rbp+57h+var_50], 14Fh
0x140008179  xorps   xmm0, xmm0
0x14000817c  movups  [rbp+57h+var_90], xmm0
0x140008180  mov     [rbp+57h+var_80], r15
0x140008184  mov     [rbp+57h+var_78], r15
0x140008188  mov     r8d, 1Ch
0x14000818e  lea     rdx, aClientserviceO; "ClientService object created"
0x140008195  lea     rcx, [rbp+57h+var_90]
0x140008199  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000819e  nop
0x14000819f  xorps   xmm0, xmm0
0x1400081a2  movups  [rbp+57h+var_B0], xmm0
0x1400081a6  mov     [rbp+57h+var_A0], r15
0x1400081aa  mov     [rbp+57h+var_98], r15
0x1400081ae  mov     r8d, 6
0x1400081b4  lea     rdx, aClient; "Client"
0x1400081bb  lea     rcx, [rbp+57h+var_B0]
0x1400081bf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400081c4  nop
0x1400081c5  lea     r9, [rbp+57h+var_90]
0x1400081c9  lea     r8, [rbp+57h+var_B0]
0x1400081cd  mov     edx, 8
0x1400081d2  lea     rcx, [rbp+57h+var_70]
0x1400081d6  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x1400081db  nop
0x1400081dc  lea     rcx, [rbp+57h+var_B0]
0x1400081e0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400081e5  nop
0x1400081e6  lea     rcx, [rbp+57h+var_90]
0x1400081ea  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400081ef  nop
0x1400081f0  lea     rcx, [rbp+57h+var_70]
0x1400081f4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400081f9  nop
0x1400081fa  mov     rax, r14
0x1400081fd  mov     rcx, [rbp+57h+var_48]
0x140008201  xor     rcx, rsp; StackCookie
0x140008204  call    __security_check_cookie
0x140008209  add     rsp, 0A8h
0x140008210  pop     r15
0x140008212  pop     r14
0x140008214  pop     r13
0x140008216  pop     r12
0x140008218  pop     rdi
0x140008219  pop     rsi
0x14000821a  pop     rbx
0x14000821b  pop     rbp
0x14000821c  retn
```
