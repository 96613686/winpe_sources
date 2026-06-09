# Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize(void)

- ea: `0x180025a10`
- end: `0x180025b99`
- name: `?RuntimeClassInitialize@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJXZ`
- size: `393`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanMediaManager *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b42c`
- `0x1800257ec`

## callees

- `0x18000705c`
- `0x1800097b4`
- `0x18000d740`
- `0x180011210`
- `0x180012228`
- `0x1800150e0`
- `0x18001f124`
- `0x180020350`
- `0x1800240b0`
- `0x180025a10`
- `0x18007cbc0`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x180025a22`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x180025a22`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize(
        Windows::Networking::UX::Internal::WlanMediaManager *this)
{
  __int32 UniqueContext; // eax
  int *v3; // rax
  Windows::Networking::UX::Internal::NlmClient **v4; // rdi
  Windows::Networking::UX::Internal::NlmClient *v5; // rcx
  Windows::Networking::UX::Internal::NlmClient *v6; // rax
  __int64 v7; // rcx
  const char *v8; // r9
  __int64 result; // rax
  int v10; // eax
  unsigned int v11; // esi
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v16[32]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v18; // [rsp+50h] [rbp+8h] BYREF
  __int64 v19; // [rsp+58h] [rbp+10h] BYREF

  UniqueContext = SHTaskPoolGetUniqueContext();
  _InterlockedExchange((volatile __int32 *)this + 14, UniqueContext);
  try
  {
    Windows::Networking::UX::Internal::WlanMediaManager::ImpersonateCurrentUser((__int64)this, &v18);
    v3 = (int *)Microsoft::WRL::Details::Make<Windows::Networking::UX::Internal::NlmClient,>(&v19);
    v4 = (Windows::Networking::UX::Internal::NlmClient **)((char *)this + 944);
    v5 = 0;
    if ( &v15 != v3 )
    {
      v5 = *(Windows::Networking::UX::Internal::NlmClient **)v3;
      *(_QWORD *)v3 = 0;
    }
    v6 = *v4;
    *v4 = v5;
    if ( v6 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v6);
    v7 = v19;
    if ( v19 )
    {
      v19 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v7);
    }
    if ( *v4 )
    {
      v10 = Windows::Networking::UX::Internal::WlanClient::Init(
              (Windows::Networking::UX::Internal::WlanMediaManager *)((char *)this + 144),
              this,
              0);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v12 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v19, this);
        wil::scope_exit__Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize_::_3_::_lambda_1___(
          v16,
          v12);
        v13 = Windows::Networking::UX::Internal::NlmClient::Start(
                *v4,
                (struct Windows::Networking::UX::Internal::INlmListener *)(((unsigned __int64)this + 32)
                                                                         & -(__int64)(this != 0)));
        v14 = v13;
        if ( v13 >= 0 )
        {
          v16[8] = 0;
          wil::details::lambda_call__Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize_::_3_::_lambda_1___::_lambda_call__Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize_::_3_::_lambda_1___(v16);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v18);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3E,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanmediamanager.cpp",
            (const char *)(unsigned int)v13,
            v15);
          wil::details::lambda_call__Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize_::_3_::_lambda_1___::_lambda_call__Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize_::_3_::_lambda_1___(v16);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v18);
          result = v14;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanmediamanager.cpp",
          (const char *)(unsigned int)v10,
          v15);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v18);
        result = v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanmediamanager.cpp",
        (const char *)0x8007000ELL,
        v15);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v18);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x43,
                           (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanmediamanager.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180025a10  mov     [rsp+arg_10], rbx
0x180025a15  mov     [rsp+arg_18], rsi
0x180025a1a  push    rdi
0x180025a1b  sub     rsp, 40h
0x180025a1f  mov     rbx, rcx
0x180025a22  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180025a28  xchg    eax, [rbx+38h]
0x180025a2b  lea     rdx, [rsp+48h+arg_0]
0x180025a30  mov     rcx, rbx
0x180025a33  call    ?ImpersonateCurrentUser@WlanMediaManager@Internal@UX@Networking@Windows@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::WlanMediaManager::ImpersonateCurrentUser(void)
0x180025a38  lea     rcx, [rsp+48h+arg_8]
0x180025a3d  call    ??$Make@VNlmClient@Internal@UX@Networking@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VNlmClient@Internal@UX@Networking@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::Networking::UX::Internal::NlmClient,>(void)
0x180025a42  lea     rdi, [rbx+3B0h]
0x180025a49  xor     ecx, ecx
0x180025a4b  lea     rdx, [rsp+48h+var_28]
0x180025a50  cmp     rdx, rax
0x180025a53  jz      short loc_180025A5F
0x180025a55  mov     rcx, [rax]
0x180025a58  mov     qword ptr [rax], 0
0x180025a5f  mov     rax, [rdi]
0x180025a62  mov     [rdi], rcx
0x180025a65  test    rax, rax
0x180025a68  jz      short loc_180025A72
0x180025a6a  mov     rcx, rax
0x180025a6d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180025a72  mov     rcx, [rsp+48h+arg_8]
0x180025a77  test    rcx, rcx
0x180025a7a  jz      short loc_180025A8A
0x180025a7c  mov     [rsp+48h+arg_8], 0
0x180025a85  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180025a8a  cmp     qword ptr [rdi], 0
0x180025a8e  jnz     short loc_180025ABF
0x180025a90  mov     rcx, [rsp+48h]; this
0x180025a95  mov     ebx, 8007000Eh
0x180025a9a  mov     r9d, ebx; char *
0x180025a9d  lea     r8, aOnecoreuapNetU_17; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180025aa4  mov     edx, 36h ; '6'; void *
0x180025aa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025aae  lea     rcx, [rsp+48h+arg_0]
0x180025ab3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180025ab8  mov     eax, ebx
0x180025aba  jmp     loc_180025B88
0x180025abf  lea     rcx, [rbx+90h]; this
0x180025ac6  xor     r8d, r8d; bool
0x180025ac9  mov     rdx, rbx; struct Windows::Networking::UX::Internal::WlanMediaManager *
0x180025acc  call    ?Init@WlanClient@Internal@UX@Networking@Windows@@QEAAJPEAVWlanMediaManager@2345@_N@Z; Windows::Networking::UX::Internal::WlanClient::Init(Windows::Networking::UX::Internal::WlanMediaManager *,bool)
0x180025ad1  mov     esi, eax
0x180025ad3  test    eax, eax
0x180025ad5  jns     short loc_180025B01
0x180025ad7  mov     rcx, [rsp+48h]; this
0x180025adc  mov     r9d, eax; char *
0x180025adf  lea     r8, aOnecoreuapNetU_17; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180025ae6  mov     edx, 38h ; '8'; void *
0x180025aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025af0  lea     rcx, [rsp+48h+arg_0]
0x180025af5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180025afa  mov     eax, esi
0x180025afc  jmp     loc_180025B88
0x180025b01  mov     rdx, rbx
0x180025b04  lea     rcx, [rsp+48h+arg_8]
0x180025b09  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180025b0e  mov     rdx, rax
0x180025b11  lea     rcx, [rsp+48h+var_20]
0x180025b16  call    wil__scope_exit__Windows__Networking__UX__Internal__WlanMediaManager__RuntimeClassInitialize____3____lambda_1___
0x180025b1b  lea     rax, [rbx+20h]
0x180025b1f  neg     rbx
0x180025b22  sbb     rdx, rdx
0x180025b25  and     rdx, rax; struct Windows::Networking::UX::Internal::INlmListener *
0x180025b28  mov     rcx, [rdi]; this
0x180025b2b  call    ?Start@NlmClient@Internal@UX@Networking@Windows@@QEAAJPEAVINlmListener@2345@@Z; Windows::Networking::UX::Internal::NlmClient::Start(Windows::Networking::UX::Internal::INlmListener *)
0x180025b30  mov     ebx, eax
0x180025b32  test    eax, eax
0x180025b34  jns     short loc_180025B67
0x180025b36  mov     rcx, [rsp+48h]; this
0x180025b3b  mov     r9d, eax; char *
0x180025b3e  lea     r8, aOnecoreuapNetU_17; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180025b45  mov     edx, 3Eh ; '>'; void *
0x180025b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025b4f  lea     rcx, [rsp+48h+var_20]
0x180025b54  call    wil__details__lambda_call__Windows__Networking__UX__Internal__WlanMediaManager__RuntimeClassInitialize____3____lambda_1______lambda_call__Windows__Networking__UX__Internal__WlanMediaManager__RuntimeClassInitialize____3____lambda_1___
0x180025b59  lea     rcx, [rsp+48h+arg_0]
0x180025b5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180025b63  mov     eax, ebx
0x180025b65  jmp     short loc_180025B88
0x180025b67  mov     [rsp+48h+var_18], 0
0x180025b6c  lea     rcx, [rsp+48h+var_20]
0x180025b71  call    wil__details__lambda_call__Windows__Networking__UX__Internal__WlanMediaManager__RuntimeClassInitialize____3____lambda_1______lambda_call__Windows__Networking__UX__Internal__WlanMediaManager__RuntimeClassInitialize____3____lambda_1___
0x180025b76  lea     rcx, [rsp+48h+arg_0]
0x180025b7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180025b80  xor     eax, eax
0x180025b82  jmp     short loc_180025B88
0x180025b84  mov     eax, dword ptr [rsp+48h+arg_0]
0x180025b88  mov     rbx, [rsp+48h+arg_10]
0x180025b8d  mov     rsi, [rsp+48h+arg_18]
0x180025b92  add     rsp, 40h
0x180025b96  pop     rdi
0x180025b97  retn
```
