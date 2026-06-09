# Windows::Networking::UX::Internal::WlanClient::Init(Windows::Networking::UX::Internal::WlanMediaManager *,bool)

- ea: `0x1800150e0`
- end: `0x18001533f`
- name: `?Init@WlanClient@Internal@UX@Networking@Windows@@QEAAJPEAVWlanMediaManager@2345@_N@Z`
- size: `607`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanClient *__hidden this, struct Windows::Networking::UX::Internal::WlanMediaManager *, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015950`
- `0x180025a10`

## callees

- `0x18000705c`
- `0x1800097b4`
- `0x18000de4c`
- `0x18000e218`
- `0x180011210`
- `0x180012024`
- `0x1800127d8`
- `0x1800150e0`
- `0x180015348`
- `0x180016044`
- `0x18001668c`
- `0x180016b04`
- `0x18001ceb8`
- `0x18001d4d4`
- `0x1800743bc`
- `0x18007a4e8`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800151c2`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800151c2`

## pseudocode

```c
int __fastcall Windows::Networking::UX::Internal::WlanClient::Init(
        Windows::Networking::UX::Internal::WlanClient *this,
        struct Windows::Networking::UX::Internal::WlanMediaManager *a2,
        char a3)
{
  __int64 v6; // rax
  int v7; // eax
  int v8; // edi
  int result; // eax
  __int64 v10; // rcx
  DWORD v11; // edi
  const char *v12; // r9
  __int64 v13; // rax
  int v14; // eax
  int v15; // edi
  int v16; // eax
  int v17; // edi
  PVOID *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // [rsp+20h] [rbp-28h] BYREF
  char v21; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD pdwNegotiatedVersion; // [rsp+60h] [rbp+18h] BYREF
  void *v24; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  if ( !a3 )
  {
    v24 = (char *)this + 584;
    v6 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v24);
    v7 = Microsoft::WRL::AsWeak<Windows::Networking::UX::Internal::WlanMediaManager>(a2, v6);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
        (const char *)(unsigned int)v7,
        v20);
      return v8;
    }
    *((_OWORD *)this + 46) = 0;
    *((_OWORD *)this + 47) = 0;
    *((_OWORD *)this + 48) = 0;
    *(_OWORD *)((char *)this + 780) = 0;
  }
  try
  {
    if ( *((_QWORD *)this + 2) != -1 && !a3 )
      goto LABEL_19;
    pdwNegotiatedVersion = 2;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(
      (char *)this + 16,
      -1);
    v11 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, (PHANDLE)this + 2);
    if ( v11 == 1220 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v10);
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x85,
               (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
               (const char *)v11,
               v20);
    }
    if ( v11 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x85,
               (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
               (const char *)v11,
               v20);
    v13 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v24, this);
    wil::scope_exit__Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize_::_3_::_lambda_1___(
      &v20,
      v13);
    v14 = Windows::Networking::UX::Internal::WlanClient::RegisterNotifications(this);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
        (const char *)(unsigned int)v14,
        v20);
      wil::details::lambda_call__Windows::Networking::UX::Internal::WlanClient::Init_::_16_::_lambda_1___::_lambda_call__Windows::Networking::UX::Internal::WlanClient::Init_::_16_::_lambda_1___(&v20);
      return v15;
    }
    v24 = (void *)*((_QWORD *)this + 73);
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v24);
    v16 = Windows::Networking::UX::Internal::ProfileManager::Initialize((void **)this + 82, &v24);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
        (const char *)(unsigned int)v16,
        v20);
      wil::details::lambda_call__Windows::Networking::UX::Internal::WlanClient::Init_::_16_::_lambda_1___::_lambda_call__Windows::Networking::UX::Internal::WlanClient::Init_::_16_::_lambda_1___(&v20);
      return v17;
    }
    v21 = 0;
    wil::details::lambda_call__Windows::Networking::UX::Internal::WlanClient::Init_::_16_::_lambda_1___::_lambda_call__Windows::Networking::UX::Internal::WlanClient::Init_::_16_::_lambda_1___(&v20);
    if ( !a3 )
    {
LABEL_19:
      if ( (int)CServiceMonitor::Start((Windows::Networking::UX::Internal::WlanClient *)((char *)this + 24)) < 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return 0;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_24:
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 )
            WPP_SF_d(v18[2], 14, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, 0);
          return 0;
        }
        v19 = CServiceMonitor::Start((Windows::Networking::UX::Internal::WlanClient *)((char *)this + 24));
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v19);
      }
    }
    v18 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_24;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x99,
             (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanclient.cpp",
             v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800150e0  mov     [rsp+arg_0], rbx
0x1800150e5  push    rsi
0x1800150e6  push    rdi
0x1800150e7  push    r14
0x1800150e9  sub     rsp, 30h
0x1800150ed  mov     sil, r8b
0x1800150f0  mov     rdi, rdx
0x1800150f3  mov     rbx, rcx
0x1800150f6  lea     r14, WPP_GLOBAL_Control
0x1800150fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180015104  cmp     rcx, r14
0x180015107  jz      short loc_180015124
0x180015109  test    byte ptr [rcx+1Ch], 40h
0x18001510d  jz      short loc_180015124
0x18001510f  mov     edx, 0Ch
0x180015114  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001511b  mov     rcx, [rcx+10h]
0x18001511f  call    WPP_SF_
0x180015124  test    sil, sil
0x180015127  jnz     short loc_18001518F
0x180015129  lea     rax, [rbx+248h]
0x180015130  mov     [rsp+48h+arg_18], rax
0x180015135  lea     rcx, [rsp+48h+arg_18]
0x18001513a  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18001513f  mov     rdx, rax
0x180015142  mov     rcx, rdi
0x180015145  call    ??$AsWeak@VWlanMediaManager@Internal@UX@Networking@Windows@@@WRL@Microsoft@@YAJPEAVWlanMediaManager@Internal@UX@Networking@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::Networking::UX::Internal::WlanMediaManager>(Windows::Networking::UX::Internal::WlanMediaManager *,Microsoft::WRL::WeakRef *)
0x18001514a  mov     edi, eax
0x18001514c  test    eax, eax
0x18001514e  jns     short loc_180015170
0x180015150  mov     rcx, [rsp+48h]; this
0x180015155  mov     r9d, eax; char *
0x180015158  lea     r8, aOnecoreuapNetU_22; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18001515f  mov     edx, 77h ; 'w'; void *
0x180015164  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015169  mov     eax, edi
0x18001516b  jmp     loc_180015330
0x180015170  xorps   xmm0, xmm0
0x180015173  movups  xmmword ptr [rbx+2E0h], xmm0
0x18001517a  movups  xmmword ptr [rbx+2F0h], xmm0
0x180015181  movups  xmmword ptr [rbx+300h], xmm0
0x180015188  movups  xmmword ptr [rbx+30Ch], xmm0
0x18001518f  lea     rdi, [rbx+10h]
0x180015193  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015197  cmp     [rdi], rdx
0x18001519a  jz      short loc_1800151A5
0x18001519c  test    sil, sil
0x18001519f  jz      loc_1800152B7
0x1800151a5  mov     [rsp+48h+pdwNegotiatedVersion], 2
0x1800151ad  mov     rcx, rdi
0x1800151b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWlanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(void *)
0x1800151b5  mov     r9, rdi; phClientHandle
0x1800151b8  lea     r8, [rsp+48h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x1800151bd  xor     edx, edx; pReserved
0x1800151bf  lea     ecx, [rdx+2]; dwClientVersion
0x1800151c2  call    cs:__imp_WlanOpenHandle
0x1800151c8  mov     edi, eax
0x1800151ca  cmp     eax, 4C4h
0x1800151cf  jnz     short loc_1800151D8
0x1800151d1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800151d6  jmp     short loc_1800151DC
0x1800151d8  test    edi, edi
0x1800151da  jz      short loc_1800151FA
0x1800151dc  mov     rcx, [rsp+48h]; this
0x1800151e1  mov     r9d, edi; char *
0x1800151e4  lea     r8, aOnecoreuapNetU_22; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800151eb  mov     edx, 85h; void *
0x1800151f0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800151f5  jmp     loc_180015330
0x1800151fa  mov     rdx, rbx
0x1800151fd  lea     rcx, [rsp+48h+arg_18]
0x180015202  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180015207  mov     rdx, rax
0x18001520a  lea     rcx, [rsp+48h+var_28]
0x18001520f  call    wil__scope_exit__Windows__Networking__UX__Internal__WlanMediaManager__RuntimeClassInitialize____3____lambda_1___
0x180015214  mov     rcx, rbx; this
0x180015217  call    ?RegisterNotifications@WlanClient@Internal@UX@Networking@Windows@@QEAAJXZ; Windows::Networking::UX::Internal::WlanClient::RegisterNotifications(void)
0x18001521c  mov     edi, eax
0x18001521e  test    eax, eax
0x180015220  jns     short loc_18001524C
0x180015222  mov     rcx, [rsp+48h]; this
0x180015227  mov     r9d, eax; char *
0x18001522a  lea     r8, aOnecoreuapNetU_22; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180015231  mov     edx, 8Ch; void *
0x180015236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001523b  lea     rcx, [rsp+48h+var_28]
0x180015240  call    wil__details__lambda_call__Windows__Networking__UX__Internal__WlanClient__Init____16____lambda_1______lambda_call__Windows__Networking__UX__Internal__WlanClient__Init____16____lambda_1___
0x180015245  mov     eax, edi
0x180015247  jmp     loc_180015330
0x18001524c  mov     rax, [rbx+248h]
0x180015253  mov     [rsp+48h+arg_18], rax
0x180015258  lea     rcx, [rsp+48h+arg_18]
0x18001525d  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x180015262  lea     rcx, [rbx+290h]
0x180015269  lea     rdx, [rsp+48h+arg_18]
0x18001526e  call    ?Initialize@ProfileManager@Internal@UX@Networking@Windows@@QEAAJVWeakRef@WRL@Microsoft@@@Z; Windows::Networking::UX::Internal::ProfileManager::Initialize(Microsoft::WRL::WeakRef)
0x180015273  mov     edi, eax
0x180015275  test    eax, eax
0x180015277  jns     short loc_1800152A3
0x180015279  mov     rcx, [rsp+48h]; this
0x18001527e  mov     r9d, eax; char *
0x180015281  lea     r8, aOnecoreuapNetU_22; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180015288  mov     edx, 8Dh; void *
0x18001528d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015292  lea     rcx, [rsp+48h+var_28]
0x180015297  call    wil__details__lambda_call__Windows__Networking__UX__Internal__WlanClient__Init____16____lambda_1______lambda_call__Windows__Networking__UX__Internal__WlanClient__Init____16____lambda_1___
0x18001529c  mov     eax, edi
0x18001529e  jmp     loc_180015330
0x1800152a3  mov     [rsp+48h+var_20], 0
0x1800152a8  lea     rcx, [rsp+48h+var_28]
0x1800152ad  call    wil__details__lambda_call__Windows__Networking__UX__Internal__WlanClient__Init____16____lambda_1______lambda_call__Windows__Networking__UX__Internal__WlanClient__Init____16____lambda_1___
0x1800152b2  test    sil, sil
0x1800152b5  jnz     short loc_1800152FE
0x1800152b7  lea     rcx, [rbx+18h]; this
0x1800152bb  call    ?Start@CServiceMonitor@@QEAAJK@Z; CServiceMonitor::Start(ulong)
0x1800152c0  test    eax, eax
0x1800152c2  jns     short loc_1800152FE
0x1800152c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152cb  cmp     rcx, r14
0x1800152ce  jz      short loc_180015328
0x1800152d0  test    byte ptr [rcx+1Ch], 2
0x1800152d4  jz      short loc_180015305
0x1800152d6  lea     rcx, [rbx+18h]; this
0x1800152da  call    ?Start@CServiceMonitor@@QEAAJK@Z; CServiceMonitor::Start(ulong)
0x1800152df  mov     edx, 0Dh
0x1800152e4  mov     r9d, eax
0x1800152e7  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x1800152ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152f5  mov     rcx, [rcx+10h]
0x1800152f9  call    WPP_SF_d
0x1800152fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180015305  cmp     rcx, r14
0x180015308  jz      short loc_180015328
0x18001530a  test    byte ptr [rcx+1Ch], 40h
0x18001530e  jz      short loc_180015328
0x180015310  mov     edx, 0Eh
0x180015315  xor     r9d, r9d
0x180015318  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001531f  mov     rcx, [rcx+10h]
0x180015323  call    WPP_SF_d
0x180015328  xor     eax, eax
0x18001532a  jmp     short loc_180015330
0x18001532c  mov     eax, [rsp+48h+pdwNegotiatedVersion]
0x180015330  mov     rbx, [rsp+48h+arg_0]
0x180015335  add     rsp, 30h
0x180015339  pop     r14
0x18001533b  pop     rdi
0x18001533c  pop     rsi
0x18001533d  retn
```
