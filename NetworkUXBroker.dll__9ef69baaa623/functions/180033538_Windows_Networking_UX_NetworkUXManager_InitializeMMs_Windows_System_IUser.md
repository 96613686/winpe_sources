# Windows::Networking::UX::NetworkUXManager::_InitializeMMs(Windows::System::IUser *)

- ea: `0x180033538`
- end: `0x1800338b3`
- name: `?_InitializeMMs@NetworkUXManager@UX@Networking@Windows@@AEAAJPEAUIUser@System@4@@Z`
- size: `891`
- prototype: `__int64 __fastcall(Windows::Networking::UX::NetworkUXManager *__hidden this, struct Windows::System::IUser *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800333f8`

## callees

- `0x180001dfc`
- `0x180001e28`
- `0x180002520`
- `0x18000955c`
- `0x1800095ac`
- `0x18000a6e4`
- `0x18000a70c`
- `0x180011984`
- `0x180011dfc`
- `0x180016f18`
- `0x1800242ac`
- `0x180027ef0`
- `0x180028320`
- `0x180028374`
- `0x18002aa34`
- `0x18002aeb8`
- `0x18002cfe4`
- `0x18002d0ac`
- `0x1800305a4`
- `0x180030678`
- `0x180033538`
- `0x1800340a0`
- `0x1800356dc`
- `0x180037abc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033623`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033883`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033623`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033883`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800335c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800335c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800335f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800335f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033772`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003382f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033772`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003382f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::_InitializeMMs(
        Windows::Networking::UX::NetworkUXManager *this,
        struct Windows::System::IUser *a2)
{
  HKEY v4; // rsi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  char IsEnabled; // al
  __int64 v9; // r8
  _DWORD *v10; // r10
  __int64 v11; // r10
  __int64 *v12; // r14
  __int64 *i; // rsi
  PCWSTR StringRawBuffer; // rax
  PCWSTR v15; // rax
  __int64 v16; // rcx
  unsigned int NetworkMediaType; // eax
  void *v18; // rdx
  wil::details *v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rcx
  char v22; // bl
  unsigned int v23; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  wil::details **v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h]
  _QWORD v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v30[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[14]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v32[6]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_5fed7179ccee37279b073b10dffdff26_Traceguids);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 96);
  v4 = (HKEY)*((_QWORD *)this + 18);
  if ( v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v25);
    RegCloseKey(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v25);
  }
  *((_QWORD *)this + 18) = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\NetworkUXManager",
         0,
         0x20019u,
         (PHKEY)this + 18);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x2D6,
           (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
           (const char *)v5,
           phkResult);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_5fed7179ccee37279b073b10dffdff26_Traceguids);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58360275>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58360275>::GetImpl'::`2'::impl);
    v31[1] = this;
    v31[2] = a2;
    v31[0] = off_18004BEE0;
    v31[13] = v31;
    if ( IsEnabled )
      Windows::Networking::UX::NetworkUXManager::ForEachActiveMMKey(this, v30);
    else
      Windows::Networking::UX::NetworkUXManager::ForEachActiveMMKey_Old(this, v30);
    wistd::function<long (unsigned short const *)>::~function<long (unsigned short const *)>(v30);
    v10 = *(_DWORD **)(wil::details::static_lazy<NetworkUxLogging>::get() + 8);
    if ( *v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v9) )
    {
      v25 = (__int64)(*((_QWORD *)this + 10) - *((_QWORD *)this + 9)) >> 3;
      v32[4] = &v25;
      v32[5] = 8;
      tlgWriteTransfer_EventWriteTransfer(v11, &byte_1800749CF, 0, 0, 3, v32);
    }
    v12 = (__int64 *)*((_QWORD *)this + 10);
    for ( i = (__int64 *)*((_QWORD *)this + 9); i != v12; ++i )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*i + 96), 0);
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          &WPP_5fed7179ccee37279b073b10dffdff26_Traceguids,
          StringRawBuffer);
      }
      v15 = WindowsGetStringRawBuffer(*(HSTRING *)(*i + 96), 0);
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v29[0] = v15;
      v29[1] = v16;
      NetworkMediaType = Windows::Networking::UX::NetworkUXManager::GetNetworkMediaType(v16, v29);
      Windows::Networking::UX::NetworkUXManager::GetInitializationEventForMediaType(this, &v27, NetworkMediaType);
      if ( v27 )
        v19 = *v27;
      else
        v19 = 0;
      wil::details::ResetEvent(v19, v18);
      v25 = *i;
      v20 = v25;
      Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IMediaManager>::InternalAddRef(&v25);
      v32[0] = v20;
      Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IMediaManager>::InternalAddRef(v32);
      v21 = v28;
      if ( v28 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v28 + 8));
        v21 = v28;
      }
      v32[1] = v27;
      v32[2] = v21;
      v22 = Windows::Internal::ComTaskPool::QueueTask__Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2___(
              v21,
              v32);
      Windows::Networking::UX::NetworkUXManager::_InitializeMMs_::_23_::_lambda_2_::__lambda_2_(v32);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v23 = (unsigned int)WindowsGetStringRawBuffer(*(HSTRING *)(*i + 96), 0);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)&WPP_5fed7179ccee37279b073b10dffdff26_Traceguids,
          v23,
          v22);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(&v27);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 0;
  }
}

```

## disassembly

```asm
0x180033538  mov     [rsp-8+arg_8], rbx
0x18003353d  mov     [rsp-8+arg_10], rsi
0x180033542  push    rbp
0x180033543  push    rdi
0x180033544  push    r12
0x180033546  push    r14
0x180033548  push    r15
0x18003354a  lea     rbp, [rsp-10h]
0x18003354f  sub     rsp, 110h
0x180033556  mov     rax, cs:__security_cookie
0x18003355d  xor     rax, rsp
0x180033560  mov     [rbp+30h+var_28], rax
0x180033564  mov     r14, rdx
0x180033567  mov     rdi, rcx
0x18003356a  lea     r12, WPP_GLOBAL_Control
0x180033571  mov     rcx, cs:WPP_GLOBAL_Control
0x180033578  cmp     rcx, r12
0x18003357b  jz      short loc_180033598
0x18003357d  test    byte ptr [rcx+1Ch], 8
0x180033581  jz      short loc_180033598
0x180033583  mov     edx, 2Ch ; ','
0x180033588  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x18003358f  mov     rcx, [rcx+10h]
0x180033593  call    WPP_SF_
0x180033598  lea     rdx, [rdi+60h]
0x18003359c  lea     rcx, [rsp+130h+SRWLock]
0x1800335a1  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800335a6  nop
0x1800335a7  lea     rbx, [rdi+90h]
0x1800335ae  mov     rsi, [rbx]
0x1800335b1  xor     r15d, r15d
0x1800335b4  test    rsi, rsi
0x1800335b7  jz      short loc_1800335D6
0x1800335b9  lea     rcx, [rsp+130h+var_100]; this
0x1800335be  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800335c3  mov     rcx, rsi; hKey
0x1800335c6  call    cs:__imp_RegCloseKey
0x1800335cc  lea     rcx, [rsp+130h+var_100]; this
0x1800335d1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800335d6  mov     [rbx], r15
0x1800335d9  mov     [rsp+130h+phkResult], rbx; unsigned int
0x1800335de  mov     r9d, 20019h; samDesired
0x1800335e4  xor     r8d, r8d; ulOptions
0x1800335e7  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Net"...
0x1800335ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800335f5  call    cs:__imp_RegOpenKeyExW
0x1800335fb  test    eax, eax
0x1800335fd  jz      short loc_180033630
0x1800335ff  mov     rcx, [rbp+38h]; this
0x180033603  mov     r9d, eax; char *
0x180033606  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18003360d  mov     edx, 2D6h; void *
0x180033612  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033617  mov     ebx, eax
0x180033619  mov     rcx, [rsp+130h+SRWLock]; SRWLock
0x18003361e  test    rcx, rcx
0x180033621  jz      short loc_180033629
0x180033623  call    cs:__imp_ReleaseSRWLockExclusive
0x180033629  mov     eax, ebx
0x18003362b  jmp     loc_18003388B
0x180033630  mov     rcx, cs:WPP_GLOBAL_Control
0x180033637  cmp     rcx, r12
0x18003363a  jz      short loc_180033657
0x18003363c  test    byte ptr [rcx+1Ch], 8
0x180033640  jz      short loc_180033657
0x180033642  mov     edx, 2Dh ; '-'
0x180033647  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x18003364e  mov     rcx, [rcx+10h]
0x180033652  call    WPP_SF_
0x180033657  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58360275@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58360275@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58360275> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58360275>::GetImpl(void)'::`2'::impl
0x18003365e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58360275@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58360275>::__private_IsEnabled(void)
0x180033663  mov     [rsp+130h+var_C0], rdi
0x180033668  mov     [rsp+130h+var_B8], r14
0x18003366d  test    al, al
0x18003366f  lea     rax, off_18004BEE0
0x180033676  mov     [rsp+130h+var_C8], rax
0x18003367b  lea     rax, [rsp+130h+var_C8]
0x180033680  mov     [rbp+30h+var_60], rax
0x180033684  jz      short loc_180033695
0x180033686  lea     rdx, [rsp+130h+var_D0]
0x18003368b  mov     rcx, rdi
0x18003368e  call    ?ForEachActiveMMKey@NetworkUXManager@UX@Networking@Windows@@AEAAX$$QEAV?$function@$$A6AJPEBG@Z@wistd@@@Z; Windows::Networking::UX::NetworkUXManager::ForEachActiveMMKey(wistd::function<long (ushort const *)> &&)
0x180033693  jmp     short loc_1800336A3
0x180033695  lea     rdx, [rsp+130h+var_D0]
0x18003369a  mov     rcx, rdi
0x18003369d  call    ?ForEachActiveMMKey_Old@NetworkUXManager@UX@Networking@Windows@@AEAAX$$QEAV?$function@$$A6AJPEBG@Z@wistd@@@Z; Windows::Networking::UX::NetworkUXManager::ForEachActiveMMKey_Old(wistd::function<long (ushort const *)> &&)
0x1800336a2  nop
0x1800336a3  lea     rcx, [rsp+130h+var_D0]
0x1800336a8  call    ??1?$function@$$A6AJPEBG@Z@wistd@@QEAA@XZ; wistd::function<long (ushort const *)>::~function<long (ushort const *)>(void)
0x1800336ad  call    ?get@?$static_lazy@VNetworkUxLogging@@@details@wil@@QEAAPEAVNetworkUxLogging@@P6AXXZ@Z; wil::details::static_lazy<NetworkUxLogging>::get(void (*)(void))
0x1800336b2  mov     r10, [rax+8]
0x1800336b6  mov     eax, [r10]
0x1800336b9  cmp     eax, 5
0x1800336bc  jbe     short loc_18003371C
0x1800336be  mov     rdx, 400000000000h
0x1800336c8  mov     rcx, r10
0x1800336cb  call    _tlgKeywordOn
0x1800336d0  test    al, al
0x1800336d2  jz      short loc_18003371C
0x1800336d4  mov     rax, [rdi+50h]
0x1800336d8  sub     rax, [rdi+48h]
0x1800336dc  sar     rax, 3
0x1800336e0  mov     [rsp+130h+var_100], rax
0x1800336e5  lea     rax, [rsp+130h+var_100]
0x1800336ea  mov     [rbp+30h+var_38], rax
0x1800336ee  mov     [rbp+30h+var_30], 8
0x1800336f6  lea     rax, [rbp+30h+var_58]
0x1800336fa  mov     [rsp+130h+var_108], rax
0x1800336ff  mov     dword ptr [rsp+130h+phkResult], 3
0x180033707  xor     r9d, r9d
0x18003370a  xor     r8d, r8d
0x18003370d  lea     rdx, byte_1800749CF
0x180033714  mov     rcx, r10
0x180033717  call    _tlgWriteTransfer_EventWriteTransfer
0x18003371c  mov     r14, [rdi+50h]
0x180033720  mov     rsi, [rdi+48h]
0x180033724  jmp     loc_180033870
0x180033729  mov     rax, cs:WPP_GLOBAL_Control
0x180033730  cmp     rax, r12
0x180033733  jz      short loc_180033769
0x180033735  test    byte ptr [rax+1Ch], 8
0x180033739  jz      short loc_180033769
0x18003373b  mov     rcx, [rsi]
0x18003373e  xor     edx, edx; length
0x180033740  mov     rcx, [rcx+60h]; string
0x180033744  call    cs:__imp_WindowsGetStringRawBuffer
0x18003374a  mov     edx, 30h ; '0'
0x18003374f  mov     r9, rax
0x180033752  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x180033759  mov     rcx, cs:WPP_GLOBAL_Control
0x180033760  mov     rcx, [rcx+10h]
0x180033764  call    WPP_SF_S
0x180033769  mov     rcx, [rsi]
0x18003376c  xor     edx, edx; length
0x18003376e  mov     rcx, [rcx+60h]; string
0x180033772  call    cs:__imp_WindowsGetStringRawBuffer
0x180033778  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003377c  inc     rcx
0x18003377f  cmp     [rax+rcx*2], r15w
0x180033784  jnz     short loc_18003377C
0x180033786  mov     [rsp+130h+var_E0], rax
0x18003378b  mov     [rsp+130h+var_D8], rcx
0x180033790  lea     rdx, [rsp+130h+var_E0]
0x180033795  call    ?GetNetworkMediaType@NetworkUXManager@UX@Networking@Windows@@AEBA?AW4NetworkMediaType@234@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Windows::Networking::UX::NetworkUXManager::GetNetworkMediaType(std::basic_string_view<ushort>)
0x18003379a  mov     r8d, eax
0x18003379d  lea     rdx, [rsp+130h+var_F0]
0x1800337a2  mov     rcx, rdi
0x1800337a5  call    ?GetInitializationEventForMediaType@NetworkUXManager@UX@Networking@Windows@@AEBA?AV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@W4NetworkMediaType@234@@Z
0x1800337aa  mov     rcx, [rsp+130h+var_F0]
0x1800337af  test    rcx, rcx
0x1800337b2  jz      short loc_1800337B9
0x1800337b4  mov     rcx, [rcx]
0x1800337b7  jmp     short loc_1800337BC
0x1800337b9  mov     rcx, r15; this
0x1800337bc  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1800337c1  mov     rbx, [rsi]
0x1800337c4  mov     [rsp+130h+var_100], rbx
0x1800337c9  lea     rcx, [rsp+130h+var_100]
0x1800337ce  call    ?InternalAddRef@?$ComPtr@UIMediaManager@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IMediaManager>::InternalAddRef(void)
0x1800337d3  mov     [rbp+30h+var_58], rbx
0x1800337d7  lea     rcx, [rbp+30h+var_58]
0x1800337db  call    ?InternalAddRef@?$ComPtr@UIMediaManager@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IMediaManager>::InternalAddRef(void)
0x1800337e0  mov     rcx, [rsp+130h+var_E8]
0x1800337e5  test    rcx, rcx
0x1800337e8  jz      short loc_1800337F3
0x1800337ea  lock inc dword ptr [rcx+8]
0x1800337ee  mov     rcx, [rsp+130h+var_E8]
0x1800337f3  mov     rax, [rsp+130h+var_F0]
0x1800337f8  mov     [rbp+30h+var_50], rax
0x1800337fc  mov     [rbp+30h+var_48], rcx
0x180033800  lea     rdx, [rbp+30h+var_58]
0x180033804  call    Windows__Internal__ComTaskPool__QueueTask__Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2___
0x180033809  mov     ebx, eax
0x18003380b  lea     rcx, [rbp+30h+var_58]
0x18003380f  call    _Windows__Networking__UX__NetworkUXManager___InitializeMMs____23____lambda_2_____lambda_2_
0x180033814  mov     rcx, cs:WPP_GLOBAL_Control
0x18003381b  cmp     rcx, r12
0x18003381e  jz      short loc_180033858
0x180033820  test    byte ptr [rcx+1Ch], 8
0x180033824  jz      short loc_180033858
0x180033826  mov     rcx, [rsi]
0x180033829  xor     edx, edx; length
0x18003382b  mov     rcx, [rcx+60h]; string
0x18003382f  call    cs:__imp_WindowsGetStringRawBuffer
0x180033835  mov     edx, 31h ; '1'
0x18003383a  mov     dword ptr [rsp+130h+phkResult], ebx
0x18003383e  mov     r9, rax
0x180033841  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x180033848  mov     rcx, cs:WPP_GLOBAL_Control
0x18003384f  mov     rcx, [rcx+10h]
0x180033853  call    WPP_SF_Sd
0x180033858  lea     rcx, [rsp+130h+var_100]
0x18003385d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180033862  lea     rcx, [rsp+130h+var_F0]
0x180033867  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x18003386c  add     rsi, 8
0x180033870  cmp     rsi, r14
0x180033873  jnz     loc_180033729
0x180033879  mov     rcx, [rsp+130h+SRWLock]; SRWLock
0x18003387e  test    rcx, rcx
0x180033881  jz      short loc_180033889
0x180033883  call    cs:__imp_ReleaseSRWLockExclusive
0x180033889  xor     eax, eax
0x18003388b  mov     rcx, [rbp+30h+var_28]
0x18003388f  xor     rcx, rsp; StackCookie
0x180033892  call    __security_check_cookie
0x180033897  lea     r11, [rsp+130h+var_20]
0x18003389f  mov     rbx, [r11+38h]
0x1800338a3  mov     rsi, [r11+40h]
0x1800338a7  mov     rsp, r11
0x1800338aa  pop     r15
0x1800338ac  pop     r14
0x1800338ae  pop     r12
0x1800338b0  pop     rdi
0x1800338b1  pop     rbp
0x1800338b2  retn
```
