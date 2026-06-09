# Windows::Networking::UX::Internal::StateDiscovery::EnterState(void)

- ea: `0x18006e3b0`
- end: `0x18006e79d`
- name: `?EnterState@StateDiscovery@Internal@UX@Networking@Windows@@UEAAXXZ`
- size: `1005`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::StateDiscovery *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ed0`
- `0x1800043bc`
- `0x180004a70`
- `0x180007a50`
- `0x180008e30`
- `0x18000bb20`
- `0x18000de4c`
- `0x18001be60`
- `0x18001d4d4`
- `0x180020d20`
- `0x1800359ac`
- `0x18006476c`
- `0x18006b280`
- `0x18006c174`
- `0x18006d27c`
- `0x18006d498`
- `0x18006d4fc`
- `0x18006e3b0`
- `0x1800724b8`
- `0x1800725f4`
- `0x1800728bc`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006e67f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006e67f`

## string_xrefs

- `0x18006e4b1`: `OpenNetwork`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Networking::UX::Internal::StateDiscovery::EnterState(
        Windows::Networking::UX::Internal::StateDiscovery *this)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  char v7; // si
  const unsigned __int16 *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  NetworkUxTelemetry::WlanConnectionFlow **v11; // rsi
  NetworkUxTelemetry::WlanConnectionFlow *v12; // rax
  NetworkUxTelemetry::WlanConnectionFlow *v13; // rdi
  NetworkUxTelemetry::WlanConnectionFlow *v14; // rax
  WcnDiscoveryQuery *v15; // r15
  WcnDiscoveryQuery *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  NetworkUxTelemetry::WlanConnectionFlow *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // [rsp+20h] [rbp-89h]
  char v34; // [rsp+30h] [rbp-79h] BYREF
  char v35; // [rsp+31h] [rbp-78h] BYREF
  char v36; // [rsp+32h] [rbp-77h] BYREF
  char v37; // [rsp+33h] [rbp-76h] BYREF
  char v38[4]; // [rsp+34h] [rbp-75h] BYREF
  NetworkUxTelemetry::WlanConnectionFlow *v39; // [rsp+38h] [rbp-71h] BYREF
  NetworkUxTelemetry::WlanConnectionFlow *v40; // [rsp+40h] [rbp-69h] BYREF
  __int64 v41; // [rsp+48h] [rbp-61h] BYREF
  __int64 v42; // [rsp+50h] [rbp-59h] BYREF
  _OWORD v43[2]; // [rsp+58h] [rbp-51h] BYREF
  int v44; // [rsp+78h] [rbp-31h]
  _BYTE v45[48]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  Windows::Networking::UX::Internal::StateBase::EnterState(this);
  v35 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 96LL))(*((_QWORD *)this + 2));
  v3 = v2;
  v42 = v2;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v3 + 120LL))(v3, &v35);
  if ( v4 >= 0 )
  {
    v34 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v3 + 136LL))(v3, &v34);
    if ( v4 >= 0 )
    {
      v7 = v34;
      v8 = L"SecuredNetwork";
      if ( !v35 )
        v8 = L"OpenNetwork";
      v39 = 0;
      (*(void (__fastcall **)(_QWORD, NetworkUxTelemetry::WlanConnectionFlow **))(**((_QWORD **)this + 2) + 184LL))(
        *((_QWORD *)this + 2),
        &v39);
      if ( v39 )
      {
        NetworkUxTelemetry::WlanConnectionFlow::SetNetworkType(v39, v8);
        NetworkUxTelemetry::WlanConnectionFlow::SetHasProfile(v39, v7 != 0);
      }
      if ( !v34 && v35 )
      {
        v11 = (NetworkUxTelemetry::WlanConnectionFlow **)((char *)this + 240);
        if ( *((_QWORD *)this + 30) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids);
          v12 = *v11;
          *((_BYTE *)v12 + 72) = 0;
          *((_QWORD *)v12 + 8) = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            (char *)this + 240,
            v9,
            v10);
        }
        v13 = 0;
        v39 = 0;
        v14 = (NetworkUxTelemetry::WlanConnectionFlow *)operator new(
                                                          0x50u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
        v15 = v14;
        v40 = v14;
        if ( v14 )
        {
          memset_0(v14, 0, 0x50u);
          v16 = WcnDiscoveryQuery::WcnDiscoveryQuery(v15);
          Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::CWiFiInProgressUIPrompt>::Attach(&v39, v16);
          v40 = 0;
          v13 = v39;
        }
        Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::NaiveSplitView<_GUID,unsigned int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<_GUID,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>>>::ChunkElementIterator>::~MakeAllocator<Windows::Foundation::Collections::Internal::NaiveSplitView<_GUID,unsigned int,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<_GUID,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>>>::ChunkElementIterator>(&v40);
        v39 = 0;
        v40 = *v11;
        *v11 = v13;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40, v17, v18);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39, v19, v20);
        if ( !*v11 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC4,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\statemachine\\lib\\wlanstates.cpp",
            (const char *)0x8007000ELL,
            v33);
        *((_QWORD *)this + 32) = *((_QWORD *)this + 2);
        v21 = *v11;
        *((_BYTE *)v21 + 72) = 1;
        *((_QWORD *)v21 + 8) = (char *)this + 248;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 120LL))(
               *((_QWORD *)this + 2),
               v3) )
        {
          v39 = 0;
          if ( (int)Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(
                      &v42,
                      &v39) >= 0 )
          {
            memset(v43, 0, sizeof(v43));
            v44 = 0;
            if ( (*(int (__fastcall **)(NetworkUxTelemetry::WlanConnectionFlow *, _OWORD *))(*(_QWORD *)v39 + 80LL))(
                   v39,
                   v43) >= 0 )
            {
              Windows::Networking::UX::Internal::StateBase::StartTimer(this, 0x2710u);
              v24 = Windows::Networking::UX::Internal::StateDiscovery::EnterState_::_34_::_lambda_1_::_lambda_1_(
                      v45,
                      (char *)this + 240,
                      v43);
              CurrentThreadId = GetCurrentThreadId();
              Windows::Networking::UX::Internal::ComTaskPoolForCurrentEffectiveUser::QueueTask__Windows::Networking::UX::Internal::StateDiscovery::EnterState_::_34_::_lambda_1___(
                v27,
                v26,
                CurrentThreadId,
                v24);
              Microsoft::WRL::WeakRef::~WeakRef((Microsoft::WRL::WeakRef *)v45);
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v39,
            v22,
            v23);
          goto LABEL_35;
        }
        v40 = 0;
        (*(void (__fastcall **)(_QWORD, NetworkUxTelemetry::WlanConnectionFlow **))(**((_QWORD **)this + 2) + 184LL))(
          *((_QWORD *)this + 2),
          &v40);
        if ( v40 )
          NetworkUxTelemetry::WlanConnectionFlow::SetWCNType(v40, L"NotSupported");
      }
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 8LL))(*((_QWORD *)this + 2), 6);
      goto LABEL_35;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 21;
      goto LABEL_11;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 20;
LABEL_11:
      WPP_SF_d(v5[2], v6, &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids, (unsigned int)v4);
    }
  }
LABEL_35:
  v41 = 0;
  v34 = 0;
  v36 = 0;
  v37 = 0;
  v38[0] = 1;
  v28 = ((__int64 (__fastcall *)(__int64 *, char *, char *, char *, char *, char *))Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiInProgressUIPrompt,Windows::Networking::UX::IUserInputType,bool,bool,bool,bool,bool>)(
          &v41,
          &v35,
          v38,
          &v37,
          &v36,
          &v34);
  if ( v28 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2), v41);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids,
      (unsigned int)v28);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41, v29, v30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42, v31, v32);
}

```

## disassembly

```asm
0x18006e3b0  push    rbp
0x18006e3b2  push    rbx
0x18006e3b3  push    rsi
0x18006e3b4  push    rdi
0x18006e3b5  push    r12
0x18006e3b7  push    r13
0x18006e3b9  push    r14
0x18006e3bb  push    r15
0x18006e3bd  lea     rbp, [rsp-1Fh]
0x18006e3c2  sub     rsp, 0C8h
0x18006e3c9  mov     rax, cs:__security_cookie
0x18006e3d0  xor     rax, rsp
0x18006e3d3  mov     [rbp+57h+var_50], rax
0x18006e3d7  mov     r14, rcx
0x18006e3da  call    ?EnterState@StateBase@Internal@UX@Networking@Windows@@UEAAXXZ; Windows::Networking::UX::Internal::StateBase::EnterState(void)
0x18006e3df  xor     r12d, r12d
0x18006e3e2  mov     [rbp+57h+var_CF], r12b
0x18006e3e6  mov     rcx, [r14+10h]
0x18006e3ea  mov     rax, [rcx]
0x18006e3ed  mov     rax, [rax+60h]
0x18006e3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3f6  mov     rbx, rax
0x18006e3f9  mov     [rbp+57h+var_B0], rax
0x18006e3fd  test    rax, rax
0x18006e400  jz      short loc_18006E412
0x18006e402  mov     rax, [rax]
0x18006e405  mov     rcx, rbx
0x18006e408  mov     rax, [rax+8]
0x18006e40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e411  nop
0x18006e412  mov     rax, [rbx]
0x18006e415  lea     rdx, [rbp+57h+var_CF]
0x18006e419  mov     rcx, rbx
0x18006e41c  mov     rax, [rax+78h]
0x18006e420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e425  lea     r13, WPP_GLOBAL_Control
0x18006e42c  test    eax, eax
0x18006e42e  jns     short loc_18006E451
0x18006e430  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e437  cmp     rcx, r13
0x18006e43a  jz      loc_18006E6EA
0x18006e440  test    byte ptr [rcx+1Ch], 2
0x18006e444  jz      loc_18006E6EA
0x18006e44a  mov     edx, 14h
0x18006e44f  jmp     short loc_18006E48E
0x18006e451  mov     [rbp+57h+var_D0], r12b
0x18006e455  mov     rax, [rbx]
0x18006e458  lea     rdx, [rbp+57h+var_D0]
0x18006e45c  mov     rcx, rbx
0x18006e45f  mov     rax, [rax+88h]
0x18006e466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e46b  test    eax, eax
0x18006e46d  jns     short loc_18006E4A6
0x18006e46f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e476  cmp     rcx, r13
0x18006e479  jz      loc_18006E6EA
0x18006e47f  test    byte ptr [rcx+1Ch], 2
0x18006e483  jz      loc_18006E6EA
0x18006e489  mov     edx, 15h
0x18006e48e  mov     r9d, eax
0x18006e491  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e498  mov     rcx, [rcx+10h]
0x18006e49c  call    WPP_SF_d
0x18006e4a1  jmp     loc_18006E6EA
0x18006e4a6  mov     sil, [rbp+57h+var_D0]
0x18006e4aa  lea     rdi, aSecurednetwork; "SecuredNetwork"
0x18006e4b1  lea     rax, aOpennetwork; "OpenNetwork"
0x18006e4b8  cmp     [rbp+57h+var_CF], r12b
0x18006e4bc  cmovz   rdi, rax
0x18006e4c0  mov     [rbp+57h+var_C8], r12
0x18006e4c4  mov     rcx, [r14+10h]
0x18006e4c8  mov     rax, [rcx]
0x18006e4cb  lea     rdx, [rbp+57h+var_C8]
0x18006e4cf  mov     rax, [rax+0B8h]
0x18006e4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4db  mov     rcx, [rbp+57h+var_C8]; this
0x18006e4df  test    rcx, rcx
0x18006e4e2  jz      short loc_18006E4FB
0x18006e4e4  mov     rdx, rdi; unsigned __int16 *
0x18006e4e7  call    ?SetNetworkType@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXPEBG@Z; NetworkUxTelemetry::WlanConnectionFlow::SetNetworkType(ushort const *)
0x18006e4ec  test    sil, sil
0x18006e4ef  setnz   dl; bool
0x18006e4f2  mov     rcx, [rbp+57h+var_C8]; this
0x18006e4f6  call    ?SetHasProfile@WlanConnectionFlow@NetworkUxTelemetry@@QEAAX_N@Z; NetworkUxTelemetry::WlanConnectionFlow::SetHasProfile(bool)
0x18006e4fb  cmp     [rbp+57h+var_D0], r12b
0x18006e4ff  jnz     loc_18006E6D5
0x18006e505  cmp     [rbp+57h+var_CF], r12b
0x18006e509  jz      loc_18006E6D5
0x18006e50f  lea     rsi, [r14+0F0h]
0x18006e516  cmp     [rsi], r12
0x18006e519  jz      short loc_18006E555
0x18006e51b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e522  cmp     rcx, r13
0x18006e525  jz      short loc_18006E542
0x18006e527  test    byte ptr [rcx+1Ch], 8
0x18006e52b  jz      short loc_18006E542
0x18006e52d  mov     edx, 16h
0x18006e532  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e539  mov     rcx, [rcx+10h]
0x18006e53d  call    WPP_SF_
0x18006e542  mov     rax, [rsi]
0x18006e545  mov     [rax+48h], r12b
0x18006e549  mov     [rax+40h], r12
0x18006e54d  mov     rcx, rsi
0x18006e550  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e555  mov     rdi, r12
0x18006e558  mov     [rbp+57h+var_C8], r12
0x18006e55c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006e563  mov     ecx, 50h ; 'P'; unsigned __int64
0x18006e568  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006e56d  mov     r15, rax
0x18006e570  mov     [rbp+57h+var_C0], rax
0x18006e574  test    rax, rax
0x18006e577  jz      short loc_18006E5A3
0x18006e579  xor     edx, edx; Val
0x18006e57b  lea     r8d, [rdx+50h]; Size
0x18006e57f  mov     rcx, rax; void *
0x18006e582  call    memset_0
0x18006e587  mov     rcx, r15; this
0x18006e58a  call    ??0WcnDiscoveryQuery@@QEAA@XZ; WcnDiscoveryQuery::WcnDiscoveryQuery(void)
0x18006e58f  mov     rdx, rax
0x18006e592  lea     rcx, [rbp+57h+var_C8]
0x18006e596  call    ?Attach@?$ComPtr@VCWiFiInProgressUIPrompt@Internal@UX@Networking@Windows@@@WRL@Microsoft@@QEAAXPEAVCWiFiInProgressUIPrompt@Internal@UX@Networking@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::CWiFiInProgressUIPrompt>::Attach(Windows::Networking::UX::Internal::CWiFiInProgressUIPrompt *)
0x18006e59b  mov     [rbp+57h+var_C0], r12
0x18006e59f  mov     rdi, [rbp+57h+var_C8]
0x18006e5a3  lea     rcx, [rbp+57h+var_C0]
0x18006e5a7  call    ??1?$MakeAllocator@VChunkElementIterator@?$NaiveSplitView@U_GUID@@IU?$DefaultEqualityPredicate@U_GUID@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@U_GUID@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@U_GUID@@IU?$DefaultLifetimeTraits@U_GUID@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::NaiveSplitView<_GUID,uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<_GUID,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>>>::ChunkElementIterator>::~MakeAllocator<Windows::Foundation::Collections::Internal::NaiveSplitView<_GUID,uint,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<_GUID,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>>>::ChunkElementIterator>(void)
0x18006e5ac  mov     [rbp+57h+var_C8], r12
0x18006e5b0  mov     rax, [rsi]
0x18006e5b3  mov     [rbp+57h+var_C0], rax
0x18006e5b7  mov     [rsi], rdi
0x18006e5ba  lea     rcx, [rbp+57h+var_C0]
0x18006e5be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e5c3  lea     rcx, [rbp+57h+var_C8]
0x18006e5c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e5cc  cmp     [rsi], r12
0x18006e5cf  jnz     short loc_18006E5ED
0x18006e5d1  mov     rcx, [rbp+5Fh]; this
0x18006e5d5  mov     r9d, 8007000Eh; char *
0x18006e5db  lea     r8, aOnecoreuapNetU_19; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18006e5e2  mov     edx, 0C4h; void *
0x18006e5e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006e5ed  lea     rcx, [r14+0F8h]
0x18006e5f4  mov     rax, [r14+10h]
0x18006e5f8  mov     [rcx+8], rax
0x18006e5fc  mov     rax, [rsi]
0x18006e5ff  mov     byte ptr [rax+48h], 1
0x18006e603  mov     [rax+40h], rcx
0x18006e607  mov     rcx, [r14+10h]
0x18006e60b  mov     rax, [rcx]
0x18006e60e  mov     rdx, rbx
0x18006e611  mov     rax, [rax+78h]
0x18006e615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e61a  test    al, al
0x18006e61c  jz      loc_18006E6A5
0x18006e622  mov     [rbp+57h+var_C8], r12
0x18006e626  lea     rdx, [rbp+57h+var_C8]
0x18006e62a  lea     rcx, [rbp+57h+var_B0]
0x18006e62e  call    ??$As@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IWlanAvailableNetwork>>)
0x18006e633  test    eax, eax
0x18006e635  js      short loc_18006E69A
0x18006e637  xorps   xmm0, xmm0
0x18006e63a  xor     eax, eax
0x18006e63c  movups  [rbp+57h+var_A8], xmm0
0x18006e640  movups  [rbp+57h+var_98], xmm0
0x18006e644  mov     [rbp+57h+var_88], eax
0x18006e647  mov     rcx, [rbp+57h+var_C8]
0x18006e64b  mov     rax, [rcx]
0x18006e64e  lea     rdx, [rbp+57h+var_A8]
0x18006e652  mov     rax, [rax+50h]
0x18006e656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e65b  test    eax, eax
0x18006e65d  js      short loc_18006E69A
0x18006e65f  mov     edx, 2710h; DueTime
0x18006e664  mov     rcx, r14; this
0x18006e667  call    ?StartTimer@StateBase@Internal@UX@Networking@Windows@@IEAAXK@Z; Windows::Networking::UX::Internal::StateBase::StartTimer(ulong)
0x18006e66c  lea     r8, [rbp+57h+var_A8]
0x18006e670  mov     rdx, rsi
0x18006e673  lea     rcx, [rbp+57h+var_80]
0x18006e677  call    _Windows__Networking__UX__Internal__StateDiscovery__EnterState____34____lambda_1____lambda_1_
0x18006e67c  mov     rbx, rax
0x18006e67f  call    cs:__imp_GetCurrentThreadId
0x18006e685  mov     r9, rbx
0x18006e688  mov     r8d, eax
0x18006e68b  call    Windows__Networking__UX__Internal__ComTaskPoolForCurrentEffectiveUser__QueueTask__Windows__Networking__UX__Internal__StateDiscovery__EnterState____34____lambda_1___
0x18006e690  lea     rcx, [rbp+57h+var_80]; this
0x18006e694  call    ??1WeakRef@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::WeakRef::~WeakRef(void)
0x18006e699  nop
0x18006e69a  lea     rcx, [rbp+57h+var_C8]
0x18006e69e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e6a3  jmp     short loc_18006E6EA
0x18006e6a5  mov     [rbp+57h+var_C0], r12
0x18006e6a9  mov     rcx, [r14+10h]
0x18006e6ad  mov     rax, [rcx]
0x18006e6b0  lea     rdx, [rbp+57h+var_C0]
0x18006e6b4  mov     rax, [rax+0B8h]
0x18006e6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6c0  mov     rcx, [rbp+57h+var_C0]; this
0x18006e6c4  test    rcx, rcx
0x18006e6c7  jz      short loc_18006E6D5
0x18006e6c9  lea     rdx, aNotsupported; "NotSupported"
0x18006e6d0  call    ?SetWCNType@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXPEBG@Z; NetworkUxTelemetry::WlanConnectionFlow::SetWCNType(ushort const *)
0x18006e6d5  mov     rcx, [r14+10h]
0x18006e6d9  mov     rax, [rcx]
0x18006e6dc  mov     edx, 6
0x18006e6e1  mov     rax, [rax+8]
0x18006e6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6ea  mov     [rbp+57h+var_B8], r12
0x18006e6ee  mov     [rbp+57h+var_D0], r12b
0x18006e6f2  mov     [rbp+57h+var_CE], r12b
0x18006e6f6  mov     [rbp+57h+var_CD], r12b
0x18006e6fa  mov     [rbp+57h+var_CC], 1
0x18006e6fe  lea     rax, [rbp+57h+var_D0]
0x18006e702  mov     [rsp+100h+var_D8], rax
0x18006e707  lea     rax, [rbp+57h+var_CE]
0x18006e70b  mov     [rsp+100h+var_E0], rax
0x18006e710  lea     r9, [rbp+57h+var_CD]
0x18006e714  lea     r8, [rbp+57h+var_CC]
0x18006e718  lea     rdx, [rbp+57h+var_CF]
0x18006e71c  lea     rcx, [rbp+57h+var_B8]
0x18006e720  call    ??$MakeAndInitialize@VCWiFiInProgressUIPrompt@Internal@UX@Networking@Windows@@UIUserInputType@345@_N_N_N_N_N@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@@012@$$QEA_N1111@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CWiFiInProgressUIPrompt,Windows::Networking::UX::IUserInputType,bool,bool,bool,bool,bool>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>>,bool &&,bool &&,bool &&,bool &&,bool &&)
0x18006e725  test    eax, eax
0x18006e727  jns     short loc_18006E755
0x18006e729  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e730  cmp     rcx, r13
0x18006e733  jz      short loc_18006E76A
0x18006e735  test    byte ptr [rcx+1Ch], 2
0x18006e739  jz      short loc_18006E76A
0x18006e73b  mov     edx, 17h
0x18006e740  mov     r9d, eax
0x18006e743  lea     r8, WPP_a797c7dc6893366bd5e69a838f894db7_Traceguids
0x18006e74a  mov     rcx, [rcx+10h]
0x18006e74e  call    WPP_SF_d
0x18006e753  jmp     short loc_18006E76A
0x18006e755  mov     rcx, [r14+10h]
0x18006e759  mov     rax, [rcx]
0x18006e75c  mov     rdx, [rbp+57h+var_B8]
0x18006e760  mov     rax, [rax+10h]
0x18006e764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e769  nop
0x18006e76a  lea     rcx, [rbp+57h+var_B8]
0x18006e76e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e773  nop
0x18006e774  lea     rcx, [rbp+57h+var_B0]
0x18006e778  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e77d  mov     rcx, [rbp+57h+var_50]
0x18006e781  xor     rcx, rsp; StackCookie
0x18006e784  call    __security_check_cookie
0x18006e789  add     rsp, 0C8h
0x18006e790  pop     r15
0x18006e792  pop     r14
0x18006e794  pop     r13
0x18006e796  pop     r12
0x18006e798  pop     rdi
0x18006e799  pop     rsi
0x18006e79a  pop     rbx
0x18006e79b  pop     rbp
0x18006e79c  retn
```
