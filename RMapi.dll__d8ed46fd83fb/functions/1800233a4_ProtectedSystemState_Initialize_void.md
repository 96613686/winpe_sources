# ProtectedSystemState::Initialize(void)

- ea: `0x1800233a4`
- end: `0x18002354f`
- name: `?Initialize@ProtectedSystemState@@QEAAXXZ`
- size: `427`
- prototype: `void __fastcall(ProtectedSystemState *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b69c`

## callees

- `0x180003d50`
- `0x180006a0c`
- `0x180006c2c`
- `0x180008278`
- `0x180008e1c`
- `0x180009120`
- `0x180009500`
- `0x18000970c`
- `0x18000a6a0`
- `0x18000aec8`
- `0x18000b744`
- `0x18000c0e0`
- `0x18000c15c`
- `0x18000c2a4`
- `0x1800233a4`
- `0x18002378c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800233ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800233ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002350c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002350c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ProtectedSystemState::Initialize(ProtectedSystemState *this)
{
  ProtectedSystemState *v1; // rbx
  __int64 PersistentRegPathRMRadioState; // rax
  __int64 v3; // r8
  __int64 v4; // rdx
  _QWORD *KeyRW; // rax
  _QWORD *v6; // rsi
  __int64 v7; // rcx
  unsigned int v8; // eax
  const wchar_t *v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // esi
  PTP_TIMER ThreadpoolTimer; // rax
  RMAPI *v13; // rcx
  unsigned int v14; // eax
  _BYTE v16[8]; // [rsp+28h] [rbp-80h] BYREF
  ProtectedSystemState *v17; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v18[3]; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int64 v19; // [rsp+50h] [rbp-58h]
  _QWORD *v20; // [rsp+70h] [rbp-38h]

  v1 = this;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)v1);
  v17 = v1;
  *((_DWORD *)v1 + 11) = RMAPI::GetHardwareRadioState();
  try
  {
    PersistentRegPathRMRadioState = RMAPI::GetPersistentRegPathRMRadioState();
    v3 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(PersistentRegPathRMRadioState);
    KeyRW = (_QWORD *)WcmCommon::Registry::CreateKeyRW(v16, v4, v3);
    v6 = KeyRW;
    if ( (_QWORD *)((char *)v1 + 112) != KeyRW )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        (char *)v1 + 112,
        *KeyRW);
      *v6 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v16);
    if ( v19 > 7 )
      std::_Deallocate<16>(v18[0], 2 * v19 + 2);
    v18[0] = ___7___Func_impl_no_alloc_V_lambda_1___1____TryGetDwordValue_H_Key_Registry_WcmCommon__QEBAKQEB_WAEBH_Z_K__V_std__6B_;
    v18[1] = (char *)v1 + 112;
    v18[2] = 0;
    v20 = v18;
    v8 = WcmCommon::Registry::Key::ThrowIfValueNotFound<unsigned long,int>(v7, v18, 0);
    v11 = v8;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_L(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v9, v10, v8);
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        *((_BYTE *)v1 + 48) = 0;
      }
      else
      {
        *((_BYTE *)v1 + 48) = 1;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids);
        WcmCommon::Registry::Key::SetDwordValue((HKEY *)v1 + 14, v9, 0);
      }
    }
    else
    {
      *((_BYTE *)v1 + 48) = 1;
    }
    ThreadpoolTimer = CreateThreadpoolTimer(ProtectedSystemState::SetSystemRadioStateTimerCallback, v1, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      (char *)v1 + 96,
      ThreadpoolTimer);
  }
  catch ( std::exception )
  {
    *((_BYTE *)this + 48) = 1;
    v13 = (RMAPI *)&WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v14 = wil::ResultFromCaughtException((wil *)&WPP_GLOBAL_Control);
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids, v14);
    }
    v1 = this;
  }
  LOBYTE(v13) = *((_BYTE *)v1 + 48);
  RMAPI::RefreshHID(v13);
  ProtectedSystemState::RefreshSysUIEnabled(v1);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
}

```

## disassembly

```asm
0x1800233a4  push    rbx
0x1800233a6  push    rsi
0x1800233a7  push    rdi
0x1800233a8  push    r14
0x1800233aa  sub     rsp, 88h
0x1800233b1  mov     rbx, rcx
0x1800233b4  mov     [rsp+0A8h+var_88], rcx
0x1800233b9  lea     r14, WPP_GLOBAL_Control
0x1800233c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233c7  cmp     rcx, r14
0x1800233ca  jz      short loc_1800233E7
0x1800233cc  test    byte ptr [rcx+1Ch], 4
0x1800233d0  jz      short loc_1800233E7
0x1800233d2  mov     edx, 0Ah
0x1800233d7  lea     r8, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids
0x1800233de  mov     rcx, [rcx+10h]
0x1800233e2  call    WPP_SF_
0x1800233e7  mov     rcx, rbx; lpCriticalSection
0x1800233ea  call    cs:__imp_EnterCriticalSection
0x1800233f0  mov     [rsp+0A8h+var_78], rbx
0x1800233f5  call    ?GetHardwareRadioState@RMAPI@@YA?AW4SliderPosition@@XZ; RMAPI::GetHardwareRadioState(void)
0x1800233fa  mov     [rbx+2Ch], eax
0x1800233fd  lea     rcx, [rsp+0A8h+var_70]
0x180023402  call    ?GetPersistentRegPathRMRadioState@RMAPI@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RMAPI::GetPersistentRegPathRMRadioState(void)
0x180023407  nop
0x180023408  mov     rcx, rax
0x18002340b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180023410  mov     r8, rax
0x180023413  lea     rcx, [rsp+0A8h+var_80]
0x180023418  call    ?CreateKeyRW@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z; WcmCommon::Registry::CreateKeyRW(HKEY__ * const,wchar_t const * const)
0x18002341d  mov     rsi, rax
0x180023420  lea     rdi, [rbx+70h]
0x180023424  cmp     rdi, rax
0x180023427  jz      short loc_18002343B
0x180023429  mov     rdx, [rax]
0x18002342c  mov     rcx, rdi
0x18002342f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180023434  mov     qword ptr [rsi], 0
0x18002343b  lea     rcx, [rsp+0A8h+var_80]
0x180023440  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023445  nop
0x180023446  mov     rdx, [rsp+0A8h+var_58]
0x18002344b  cmp     rdx, 7
0x18002344f  jbe     short loc_180023463
0x180023451  lea     rdx, ds:2[rdx*2]
0x180023459  mov     rcx, [rsp+0A8h+var_70]
0x18002345e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180023463  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1???$TryGetDwordValue@H@Key@Registry@WcmCommon@@QEBAKQEB_WAEBH@Z@K$$V@std@@6B@; const std::_Func_impl_no_alloc<`WcmCommon::Registry::Key::TryGetDwordValue<int>(wchar_t const * const,int const &)'::`2'::_lambda_1_,ulong,>::`vftable'
0x18002346a  mov     [rsp+0A8h+var_70], rax
0x18002346f  mov     [rsp+0A8h+var_68], rdi
0x180023474  mov     [rsp+0A8h+var_60], 0
0x18002347d  lea     rax, [rsp+0A8h+var_70]
0x180023482  mov     [rsp+0A8h+var_38], rax
0x180023487  xor     r8d, r8d
0x18002348a  lea     rdx, [rsp+0A8h+var_70]
0x18002348f  call    ??$ThrowIfValueNotFound@KH@Key@Registry@WcmCommon@@AEBAKV?$function@$$A6AKXZ@std@@H@Z; WcmCommon::Registry::Key::ThrowIfValueNotFound<ulong,int>(std::function<ulong (void)>,int)
0x180023494  mov     esi, eax
0x180023496  mov     rcx, cs:WPP_GLOBAL_Control
0x18002349d  cmp     rcx, r14
0x1800234a0  jz      short loc_1800234B4
0x1800234a2  test    byte ptr [rcx+1Ch], 4
0x1800234a6  jz      short loc_1800234B4
0x1800234a8  mov     r9d, eax
0x1800234ab  mov     rcx, [rcx+10h]
0x1800234af  call    WPP_SF_L
0x1800234b4  test    esi, esi
0x1800234b6  jnz     short loc_1800234BE
0x1800234b8  mov     byte ptr [rbx+30h], 1
0x1800234bc  jmp     short loc_1800234FF
0x1800234be  cmp     esi, 1
0x1800234c1  jnz     short loc_1800234C9
0x1800234c3  mov     byte ptr [rbx+30h], 0
0x1800234c7  jmp     short loc_1800234FF
0x1800234c9  mov     byte ptr [rbx+30h], 1
0x1800234cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234d4  cmp     rcx, r14
0x1800234d7  jz      short loc_1800234F4
0x1800234d9  test    byte ptr [rcx+1Ch], 4
0x1800234dd  jz      short loc_1800234F4
0x1800234df  mov     edx, 0Ch
0x1800234e4  lea     r8, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids
0x1800234eb  mov     rcx, [rcx+10h]
0x1800234ef  call    WPP_SF_
0x1800234f4  xor     r8d, r8d; unsigned int
0x1800234f7  mov     rcx, rdi; this
0x1800234fa  call    ?SetDwordValue@Key@Registry@WcmCommon@@QEAAXQEB_WK@Z; WcmCommon::Registry::Key::SetDwordValue(wchar_t const * const,ulong)
0x1800234ff  xor     r8d, r8d; pcbe
0x180023502  mov     rdx, rbx; pv
0x180023505  lea     rcx, ?SetSystemRadioStateTimerCallback@ProtectedSystemState@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002350c  call    cs:__imp_CreateThreadpoolTimer
0x180023512  mov     rdx, rax
0x180023515  lea     rcx, [rbx+60h]
0x180023519  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002351e  nop
0x18002351f  jmp     short loc_180023526
0x180023521  mov     rbx, [rsp+0A8h+var_88]
0x180023526  mov     cl, [rbx+30h]; this
0x180023529  call    ?RefreshHID@RMAPI@@YAX_N@Z; RMAPI::RefreshHID(bool)
0x18002352e  mov     rcx, rbx; this
0x180023531  call    ?RefreshSysUIEnabled@ProtectedSystemState@@AEAAXXZ; ProtectedSystemState::RefreshSysUIEnabled(void)
0x180023536  nop
0x180023537  lea     rcx, [rsp+0A8h+var_78]
0x18002353c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180023541  nop
0x180023542  add     rsp, 88h
0x180023549  pop     r14
0x18002354b  pop     rdi
0x18002354c  pop     rsi
0x18002354d  pop     rbx
0x18002354e  retn
```
