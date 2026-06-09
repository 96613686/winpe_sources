# RoutePolicyOnDemand::UpdateRequestsWithExistingSession(std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &,std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &)

- ea: `0x1800a8c40`
- end: `0x1800a8f09`
- name: `?UpdateRequestsWithExistingSession@RoutePolicyOnDemand@@AEAAXAEBV?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@0@Z`
- size: `713`
- prototype: `__int64 __fastcall(RoutePolicyOnDemand *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a54d8`

## callees

- `0x180003f44`
- `0x18003a08c`
- `0x18003a55c`
- `0x1800612c8`
- `0x18006db98`
- `0x180084f50`
- `0x1800a28f4`
- `0x1800a7830`
- `0x1800a8c40`
- `0x1800a9884`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a8e40`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800a8e40`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a8e1e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a8e1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a8e75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a8e75`

## string_xrefs

- `0x1800a8ece`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`

## pseudocode

```c
void __fastcall RoutePolicyOnDemand::UpdateRequestsWithExistingSession(
        RoutePolicyOnDemand *this,
        _QWORD *a2,
        PVOID *a3,
        int a4)
{
  struct Request **v7; // rdi
  struct Request **v8; // r15
  __int16 v9; // cx
  _BYTE *v10; // rax
  _QWORD *v11; // rcx
  union _NET_LUID_LH v12; // r9
  int v13; // r8d
  _QWORD *v14; // rcx
  _QWORD *v15; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v17; // r9
  __int64 v18; // rbx
  unsigned __int64 v19; // rax
  int v20; // eax
  int v21; // ebx
  __int16 v22; // [rsp+50h] [rbp-19h] BYREF
  __int16 v23; // [rsp+52h] [rbp-17h] BYREF
  int v24; // [rsp+54h] [rbp-15h] BYREF
  int v25; // [rsp+58h] [rbp-11h] BYREF
  struct Request *v26; // [rsp+60h] [rbp-9h] BYREF
  struct Request *v27; // [rsp+68h] [rbp-1h] BYREF
  __int64 v28; // [rsp+70h] [rbp+7h] BYREF
  __int64 v29; // [rsp+78h] [rbp+Fh] BYREF
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v7 = (struct Request **)*((_QWORD *)this + 3);
  v8 = (struct Request **)*((_QWORD *)this + 4);
  if ( v7 != v8 )
  {
    while ( *((_QWORD *)*v7 + 14) != *a2 )
    {
LABEL_24:
      v7 += 2;
      if ( v7 == v8 )
        return;
    }
    v9 = *((_WORD *)*v7 + 52);
    if ( v9 == 2 )
    {
      if ( *((_BYTE *)*a3 + 123) )
      {
LABEL_7:
        if ( (unsigned int)dword_18013A120 > 5 )
        {
          v26 = *v7;
          v11 = *a3;
          v24 = *((_DWORD *)*a3 + 4);
          v28 = v11[3];
          v27 = (struct Request *)(v11 + 4);
          v22 = *((_WORD *)v26 + 52);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (_DWORD)v11,
            (unsigned int)byte_180118AF9,
            (_DWORD)a3,
            a4,
            (__int64)&v22,
            (__int64)&v27,
            (__int64)&v28,
            (__int64)&v24,
            (__int64)&v26);
        }
        std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=((char *)*v7 + 112, a3);
        std::_Erase_remove_if_std::vector_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect____std::allocator_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect__________RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1_::operator()_::_73_::_lambda_6___(
          (char *)this + 48,
          v7);
        if ( !*((_QWORD *)*v7 + 16) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v12.Value = *(_QWORD *)((ULONG64)*a3 + 24);
        v13 = 0;
LABEL_12:
        RoutePolicyOnDemand::CompleteRequest(this, *v7, v13, v12);
        goto LABEL_24;
      }
    }
    else if ( v9 == 23 )
    {
      v10 = *a3;
      goto LABEL_15;
    }
    if ( v9 )
      goto LABEL_16;
    v10 = *a3;
    if ( *((_BYTE *)*a3 + 123) )
      goto LABEL_7;
LABEL_15:
    if ( v10[124] )
      goto LABEL_7;
LABEL_16:
    if ( *((_QWORD *)*a3 + 10) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v27 = *v7;
      v14 = *a3;
      v25 = *((_DWORD *)*a3 + 4);
      v29 = v14[3];
      v26 = (struct Request *)(v14 + 4);
      v23 = *((_WORD *)v27 + 52);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v14,
        (unsigned int)&word_180118BA6,
        (_DWORD)a3,
        a4,
        (__int64)&v23,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v27);
    }
    v15 = (char *)*a3 + 88;
    if ( *v15 )
      goto LABEL_23;
    ThreadpoolTimer = CreateThreadpoolTimer(RoutePolicyOnDemand::ReadyTimeoutCallback, *a3, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v15,
      ThreadpoolTimer);
    if ( *((_QWORD *)*a3 + 11) )
    {
      v18 = *((_QWORD *)*a3 + 14);
      v19 = GetTickCount64() - v18;
      pftDueTime = (struct _FILETIME)(-10000LL * ((20000 - (_DWORD)v19) & (unsigned int)-(v19 < 0x4E20)));
      SetThreadpoolTimer(*((PTP_TIMER *)*a3 + 11), &pftDueTime, 0, 0);
LABEL_23:
      std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=((char *)*v7 + 112, a3);
      std::_Erase_remove_if_std::vector_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect____std::allocator_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect__________RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1_::operator()_::_73_::_lambda_6___(
        (char *)this + 48,
        v7);
      goto LABEL_24;
    }
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x393,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      v17);
    v21 = v20;
    if ( !*((_QWORD *)*v7 + 16) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::reset((char *)*v7 + 112);
    v12.Value = 0;
    v13 = v21;
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x1800a8c40  mov     [rsp-8+arg_8], rbx
0x1800a8c45  push    rbp
0x1800a8c46  push    rsi
0x1800a8c47  push    rdi
0x1800a8c48  push    r12
0x1800a8c4a  push    r13
0x1800a8c4c  push    r14
0x1800a8c4e  push    r15
0x1800a8c50  lea     rbp, [rsp-27h]
0x1800a8c55  sub     rsp, 90h
0x1800a8c5c  mov     rax, cs:__security_cookie
0x1800a8c63  xor     rax, rsp
0x1800a8c66  mov     [rbp+57h+var_38], rax
0x1800a8c6a  mov     rsi, r8
0x1800a8c6d  mov     r12, rdx
0x1800a8c70  mov     r14, rcx
0x1800a8c73  mov     rdi, [rcx+18h]
0x1800a8c77  mov     r15, [rcx+20h]
0x1800a8c7b  cmp     rdi, r15
0x1800a8c7e  jz      loc_1800A8EA3
0x1800a8c84  xor     r13d, r13d
0x1800a8c87  mov     rcx, [rdi]
0x1800a8c8a  mov     rax, [r12]
0x1800a8c8e  cmp     [rcx+70h], rax
0x1800a8c92  jnz     loc_1800A8E96
0x1800a8c98  movzx   ecx, word ptr [rcx+68h]
0x1800a8c9c  cmp     cx, 2
0x1800a8ca0  jnz     loc_1800A8D77
0x1800a8ca6  mov     rax, [rsi]
0x1800a8ca9  cmp     [rax+7Bh], r13b
0x1800a8cad  jnz     short loc_1800A8CC5
0x1800a8caf  test    cx, cx
0x1800a8cb2  jnz     loc_1800A8D8E
0x1800a8cb8  mov     rax, [rsi]
0x1800a8cbb  cmp     [rax+7Bh], r13b
0x1800a8cbf  jz      loc_1800A8D84
0x1800a8cc5  mov     eax, cs:dword_18013A120
0x1800a8ccb  cmp     eax, 5
0x1800a8cce  jbe     short loc_1800A8D31
0x1800a8cd0  mov     rdx, [rdi]
0x1800a8cd3  mov     [rbp+57h+var_60], rdx
0x1800a8cd7  mov     rcx, [rsi]
0x1800a8cda  mov     eax, [rcx+10h]
0x1800a8cdd  mov     [rbp+57h+var_6C], eax
0x1800a8ce0  mov     rax, [rcx+18h]
0x1800a8ce4  mov     [rbp+57h+var_50], rax
0x1800a8ce8  lea     rax, [rcx+20h]
0x1800a8cec  mov     [rbp+57h+var_58], rax
0x1800a8cf0  movzx   eax, word ptr [rdx+68h]
0x1800a8cf4  mov     [rbp+57h+var_70], ax
0x1800a8cf8  lea     rax, [rbp+57h+var_60]
0x1800a8cfc  mov     [rsp+0C0h+var_80], rax
0x1800a8d01  lea     rax, [rbp+57h+var_6C]
0x1800a8d05  mov     [rsp+0C0h+var_88], rax
0x1800a8d0a  lea     rax, [rbp+57h+var_50]
0x1800a8d0e  mov     [rsp+0C0h+var_90], rax
0x1800a8d13  lea     rax, [rbp+57h+var_58]
0x1800a8d17  mov     [rsp+0C0h+var_98], rax
0x1800a8d1c  lea     rax, [rbp+57h+var_70]
0x1800a8d20  mov     [rsp+0C0h+var_A0], rax
0x1800a8d25  lea     rdx, byte_180118AF9
0x1800a8d2c  call    ??$Write@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800a8d31  mov     rcx, [rdi]
0x1800a8d34  add     rcx, 70h ; 'p'
0x1800a8d38  mov     rdx, rsi
0x1800a8d3b  call    ??4?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=(std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &)
0x1800a8d40  lea     rcx, [r14+30h]
0x1800a8d44  mov     rdx, rdi
0x1800a8d47  call    std___Erase_remove_if_std__vector_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect____std__allocator_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect__________RoutePolicyOnDemand__StartConnectionInternal____3____lambda_1___operator______73____lambda_6___
0x1800a8d4c  mov     rax, [rdi]
0x1800a8d4f  cmp     [rax+80h], r13
0x1800a8d56  jnz     short loc_1800A8D5D
0x1800a8d58  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a8d5d  mov     r9, [rsi]
0x1800a8d60  mov     r9, [r9+18h]; union _NET_LUID_LH
0x1800a8d64  xor     r8d, r8d; int
0x1800a8d67  mov     rdx, [rdi]; struct Request *
0x1800a8d6a  mov     rcx, r14; this
0x1800a8d6d  call    ?CompleteRequest@RoutePolicyOnDemand@@AEAAXAEAURequest@1@JT_NET_LUID_LH@@@Z; RoutePolicyOnDemand::CompleteRequest(RoutePolicyOnDemand::Request &,long,_NET_LUID_LH)
0x1800a8d72  jmp     loc_1800A8E96
0x1800a8d77  cmp     cx, 17h
0x1800a8d7b  jnz     loc_1800A8CAF
0x1800a8d81  mov     rax, [rsi]
0x1800a8d84  cmp     [rax+7Ch], r13b
0x1800a8d88  jnz     loc_1800A8CC5
0x1800a8d8e  mov     rax, [rsi]
0x1800a8d91  cmp     [rax+50h], r13
0x1800a8d95  jz      short loc_1800A8D9C
0x1800a8d97  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a8d9c  mov     eax, cs:dword_18013A120
0x1800a8da2  cmp     eax, 5
0x1800a8da5  jbe     short loc_1800A8E08
0x1800a8da7  mov     rdx, [rdi]
0x1800a8daa  mov     [rbp+57h+var_58], rdx
0x1800a8dae  mov     rcx, [rsi]
0x1800a8db1  mov     eax, [rcx+10h]
0x1800a8db4  mov     [rbp+57h+var_68], eax
0x1800a8db7  mov     rax, [rcx+18h]
0x1800a8dbb  mov     [rbp+57h+var_48], rax
0x1800a8dbf  lea     rax, [rcx+20h]
0x1800a8dc3  mov     [rbp+57h+var_60], rax
0x1800a8dc7  movzx   eax, word ptr [rdx+68h]
0x1800a8dcb  mov     [rbp+57h+var_6E], ax
0x1800a8dcf  lea     rax, [rbp+57h+var_58]
0x1800a8dd3  mov     [rsp+0C0h+var_80], rax
0x1800a8dd8  lea     rax, [rbp+57h+var_68]
0x1800a8ddc  mov     [rsp+0C0h+var_88], rax
0x1800a8de1  lea     rax, [rbp+57h+var_48]
0x1800a8de5  mov     [rsp+0C0h+var_90], rax
0x1800a8dea  lea     rax, [rbp+57h+var_60]
0x1800a8dee  mov     [rsp+0C0h+var_98], rax
0x1800a8df3  lea     rax, [rbp+57h+var_6E]
0x1800a8df7  mov     [rsp+0C0h+var_A0], rax
0x1800a8dfc  lea     rdx, word_180118BA6
0x1800a8e03  call    ??$Write@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800a8e08  mov     rdx, [rsi]; pv
0x1800a8e0b  lea     rbx, [rdx+58h]
0x1800a8e0f  cmp     [rbx], r13
0x1800a8e12  jnz     short loc_1800A8E7B
0x1800a8e14  xor     r8d, r8d; pcbe
0x1800a8e17  lea     rcx, ?ReadyTimeoutCallback@RoutePolicyOnDemand@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800a8e1e  call    cs:__imp_CreateThreadpoolTimer
0x1800a8e24  mov     rdx, rax
0x1800a8e27  mov     rcx, rbx
0x1800a8e2a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800a8e2f  mov     rbx, [rsi]
0x1800a8e32  cmp     [rbx+58h], r13
0x1800a8e36  jz      loc_1800A8ECA
0x1800a8e3c  mov     rbx, [rbx+70h]
0x1800a8e40  call    cs:__imp_GetTickCount64
0x1800a8e46  sub     rax, rbx
0x1800a8e49  mov     ebx, 4E20h
0x1800a8e4e  mov     ecx, ebx
0x1800a8e50  sub     ecx, eax
0x1800a8e52  cmp     rax, rbx
0x1800a8e55  sbb     eax, eax
0x1800a8e57  and     eax, ecx
0x1800a8e59  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1800a8e60  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rcx
0x1800a8e64  mov     rcx, [rsi]
0x1800a8e67  xor     r9d, r9d; msWindowLength
0x1800a8e6a  xor     r8d, r8d; msPeriod
0x1800a8e6d  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x1800a8e71  mov     rcx, [rcx+58h]; pti
0x1800a8e75  call    cs:__imp_SetThreadpoolTimer
0x1800a8e7b  mov     rcx, [rdi]
0x1800a8e7e  add     rcx, 70h ; 'p'
0x1800a8e82  mov     rdx, rsi
0x1800a8e85  call    ??4?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::operator=(std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &)
0x1800a8e8a  lea     rcx, [r14+30h]
0x1800a8e8e  mov     rdx, rdi
0x1800a8e91  call    std___Erase_remove_if_std__vector_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect____std__allocator_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect__________RoutePolicyOnDemand__StartConnectionInternal____3____lambda_1___operator______73____lambda_6___
0x1800a8e96  add     rdi, 10h
0x1800a8e9a  cmp     rdi, r15
0x1800a8e9d  jnz     loc_1800A8C87
0x1800a8ea3  mov     rcx, [rbp+57h+var_38]
0x1800a8ea7  xor     rcx, rsp; StackCookie
0x1800a8eaa  call    __security_check_cookie
0x1800a8eaf  mov     rbx, [rsp+0C0h+arg_8]
0x1800a8eb7  add     rsp, 90h
0x1800a8ebe  pop     r15
0x1800a8ec0  pop     r14
0x1800a8ec2  pop     r13
0x1800a8ec4  pop     r12
0x1800a8ec6  pop     rdi
0x1800a8ec7  pop     rsi
0x1800a8ec8  pop     rbp
0x1800a8ec9  retn
0x1800a8eca  mov     rcx, [rbp+5Fh]; this
0x1800a8ece  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a8ed5  mov     edx, 393h; void *
0x1800a8eda  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800a8edf  mov     ebx, eax
0x1800a8ee1  mov     rcx, [rdi]
0x1800a8ee4  cmp     [rcx+80h], r13
0x1800a8eeb  jnz     short loc_1800A8EF2
0x1800a8eed  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a8ef2  mov     rcx, [rdi]
0x1800a8ef5  add     rcx, 70h ; 'p'
0x1800a8ef9  call    ?reset@?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAXXZ; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::reset(void)
0x1800a8efe  mov     r9, r13
0x1800a8f01  mov     r8d, ebx
0x1800a8f04  jmp     loc_1800A8D67
```
