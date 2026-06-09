# RadioManager::Advise(IUnknown *,ulong *)

- ea: `0x18001dac0`
- end: `0x18001df82`
- name: `?Advise@RadioManager@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `1218`
- prototype: `__int64 __fastcall(RadioManager *this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002510`
- `0x180003fa0`
- `0x1800042b0`
- `0x1800097f0`
- `0x18000be90`
- `0x18000c200`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18000d784`
- `0x18001aa6c`
- `0x18001b600`
- `0x18001be6c`
- `0x18001c654`
- `0x18001da90`
- `0x18001dac0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001de11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001de11`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001db63`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dc1c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dc79`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dd01`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dd96`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001df2d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001db63`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dc1c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dc79`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dd01`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001dd96`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001df2d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001db29`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001db29`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001dcc9`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001dcc9`

## string_xrefs

- `0x18001db90`: `CoImpersonateClient failed`
- `0x18001db57`: `RMAPI::SetProxySecurity(IUnknown) failed`
- `0x18001dd60`: `ICallingProcessInfo::OpenCallerProcessHandle failed`

## pseudocode

```c
__int64 __fastcall RadioManager::Advise(RadioManager *this, struct IUnknown *a2, unsigned int *a3)
{
  struct IUnknown *v6; // rdx
  HRESULT v7; // ebx
  int v9; // eax
  struct IUnknown *v10; // rdx
  struct RadioManager *v11; // rsi
  char *v12; // rax
  __int64 v13; // rax
  __int64 *v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  wil *v18; // rcx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // [rsp+30h] [rbp-B8h] BYREF
  char v23; // [rsp+39h] [rbp-AFh]
  const char *v24; // [rsp+40h] [rbp-A8h] BYREF
  const char *v25; // [rsp+48h] [rbp-A0h] BYREF
  RadioManager *v26; // [rsp+50h] [rbp-98h]
  char *v27; // [rsp+58h] [rbp-90h]
  unsigned int *v28; // [rsp+60h] [rbp-88h]
  __int64 v29; // [rsp+68h] [rbp-80h]
  const char *v30; // [rsp+70h] [rbp-78h] BYREF
  int v31; // [rsp+78h] [rbp-70h] BYREF
  struct IUnknown *v32; // [rsp+80h] [rbp-68h] BYREF
  unsigned int v33; // [rsp+88h] [rbp-60h] BYREF
  _QWORD v34[2]; // [rsp+90h] [rbp-58h] BYREF
  char v35; // [rsp+A0h] [rbp-48h]
  void *ppInterface; // [rsp+A8h] [rbp-40h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-38h] BYREF

  v26 = this;
  if ( a2 && a3 )
  {
    v31 = 0;
    v30 = (const char *)&byte_18002AE5D;
    v34[0] = &v31;
    v34[1] = &v30;
    v35 = 1;
    v7 = CoImpersonateClient();
    v31 = v7;
    if ( v7 == -2147417833 )
    {
      v31 = 0;
    }
    else if ( v7 < 0 )
    {
      v30 = "CoImpersonateClient failed";
      if ( v35 )
      {
        v35 = 0;
        RadioManager::Advise_::_2_::_lambda_1_::operator()(v34);
      }
      return (unsigned int)v7;
    }
    v23 = 1;
    v7 = RMAPI::SetProxyBlanket((RMAPI *)a2, v6);
    v31 = v7;
    if ( v7 >= 0 )
    {
      v32 = 0;
      v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_b453e674_f489_41c5_9955_983c9fc264b2,
             &v32);
      v7 = v9;
      v31 = v9;
      if ( v9 >= 0 )
      {
        v7 = RMAPI::SetProxyBlanket((RMAPI *)v32, v10);
        v31 = v7;
        if ( v7 >= 0 )
        {
          ppInterface = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInterface);
          v7 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
          v31 = v7;
          if ( v7 >= 0 )
          {
            v37 = 0;
            v7 = (*(__int64 (__fastcall **)(void *, __int64, __int64 *))(*(_QWORD *)ppInterface + 24LL))(
                   ppInterface,
                   0x100000,
                   &v37);
            v31 = v7;
            if ( v7 >= 0 )
            {
              try
              {
                v33 = ConnectionPointContainer::Add((LPCRITICAL_SECTION)this + 4, v32);
                v29 = 1;
                v11 = (RadioManager *)((char *)this - 8);
                v27 = (char *)this - 8;
                v28 = &v33;
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
                v24 = (char *)this + 232;
                v12 = (char *)operator new(0x20u);
                v25 = v12;
                *(_OWORD *)v12 = 0;
                *((_OWORD *)v12 + 1) = 0;
                v13 = AdviseInstance::AdviseInstance(v12);
                v22 = v13;
                v14 = (__int64 *)*((_QWORD *)this + 41);
                if ( v14 == *((__int64 **)this + 42) )
                {
                  std::vector<std::unique_ptr<AdviseInstance>>::_Emplace_reallocate<std::unique_ptr<AdviseInstance>>(
                    (char *)this + 320,
                    v14,
                    &v22);
                }
                else
                {
                  v22 = 0;
                  *v14 = v13;
                  *((_QWORD *)this + 41) += 8LL;
                }
                std::unique_ptr<AdviseInstance>::~unique_ptr<AdviseInstance>(&v22);
                *a3 = v33;
                if ( (unsigned int)dword_180037050 > 4 )
                {
                  LODWORD(v22) = *a3;
                  v25 = "Advise cookie tracked";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    v15,
                    (unsigned int)word_18003004A,
                    v16,
                    v17,
                    (__int64)&v25,
                    (__int64)&v22);
                }
                wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v24);
              }
              catch ( ... )
              {
                v31 = wil::ResultFromCaughtException(v18);
                if ( (unsigned int)dword_180037050 > 2 )
                {
                  LODWORD(v22) = v31;
                  v24 = "Exception thrown adding an advise cookie";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    v19,
                    (unsigned int)&unk_180030010,
                    v20,
                    v21,
                    (__int64)&v24,
                    (__int64)&v22);
                }
                v11 = (RadioManager *)((char *)v26 - 8);
              }
              v7 = v31;
              if ( v31 >= 0 )
              {
                AddRefSingleton(v11);
                v7 = v31;
              }
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInterface);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
              CoRevertToSelf();
              if ( v35 )
              {
                v35 = 0;
                RadioManager::Advise_::_2_::_lambda_1_::operator()(v34);
              }
            }
            else
            {
              v30 = "ICallingProcessInfo::OpenCallerProcessHandle failed";
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInterface);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
              CoRevertToSelf();
              if ( v35 )
              {
                v35 = 0;
                RadioManager::Advise_::_2_::_lambda_1_::operator()(v34);
              }
            }
          }
          else
          {
            v30 = "CoGetCallContext failed";
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInterface);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
            CoRevertToSelf();
            if ( v35 )
            {
              v35 = 0;
              RadioManager::Advise_::_2_::_lambda_1_::operator()(v34);
            }
          }
        }
        else
        {
          v30 = "RMAPI::SetProxyBlanket(IUIRadioManagerNotifySink) failed";
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          CoRevertToSelf();
          if ( v35 )
          {
            v35 = 0;
            RadioManager::Advise_::_2_::_lambda_1_::operator()(v34);
          }
        }
      }
      else
      {
        if ( v9 == -2147467262 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          v7 = v31;
        }
        v30 = "QueryInterface<IUIRadioManagerNotifySink> failed";
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        CoRevertToSelf();
        if ( v35 )
        {
          v35 = 0;
          RadioManager::Advise_::_2_::_lambda_1_::operator()(v34);
        }
      }
    }
    else
    {
      v30 = "RMAPI::SetProxySecurity(IUnknown) failed";
      CoRevertToSelf();
      if ( v35 )
      {
        v35 = 0;
        RadioManager::Advise_::_2_::_lambda_1_::operator()(v34);
      }
    }
    return (unsigned int)v7;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001dac0  mov     r11, rsp
0x18001dac3  push    rbx
0x18001dac4  push    rsi
0x18001dac5  push    rdi
0x18001dac6  push    r14
0x18001dac8  push    r15
0x18001daca  sub     rsp, 0C0h
0x18001dad1  mov     rax, cs:__security_cookie
0x18001dad8  xor     rax, rsp
0x18001dadb  mov     [rsp+0E8h+var_30], rax
0x18001dae3  mov     r15, r8
0x18001dae6  mov     rsi, rdx
0x18001dae9  mov     r14, rcx
0x18001daec  mov     [rsp+0E8h+var_98], rcx
0x18001daf1  xor     edi, edi
0x18001daf3  test    rdx, rdx
0x18001daf6  jz      loc_18001DF59
0x18001dafc  test    r8, r8
0x18001daff  jz      loc_18001DF59
0x18001db05  mov     [rsp+0E8h+var_70], edi
0x18001db09  lea     rax, byte_18002AE5D
0x18001db10  mov     [r11-78h], rax
0x18001db14  lea     rax, [r11-70h]
0x18001db18  mov     [r11-58h], rax
0x18001db1c  lea     rax, [r11-78h]
0x18001db20  mov     [r11-50h], rax
0x18001db24  mov     byte ptr [r11-48h], 1
0x18001db29  call    cs:__imp_CoImpersonateClient
0x18001db2f  mov     ebx, eax
0x18001db31  mov     [rsp+0E8h+var_70], eax
0x18001db35  cmp     eax, 80010117h
0x18001db3a  jnz     short loc_18001DB8C
0x18001db3c  mov     [rsp+0E8h+var_70], edi
0x18001db40  mov     [rsp+0E8h+var_AF], 1
0x18001db45  mov     rcx, rsi; this
0x18001db48  call    ?SetProxyBlanket@RMAPI@@YAJPEAUIUnknown@@@Z; RMAPI::SetProxyBlanket(IUnknown *)
0x18001db4d  mov     ebx, eax
0x18001db4f  mov     [rsp+0E8h+var_70], eax
0x18001db53  test    eax, eax
0x18001db55  jns     short loc_18001DBC3
0x18001db57  lea     rax, aRmapiSetproxys; "RMAPI::SetProxySecurity(IUnknown) faile"...
0x18001db5e  mov     [rsp+0E8h+var_78], rax
0x18001db63  call    cs:__imp_CoRevertToSelf
0x18001db69  nop
0x18001db6a  cmp     [rsp+0E8h+var_48], dil
0x18001db72  jz      short loc_18001DB8A
0x18001db74  mov     [rsp+0E8h+var_48], dil
0x18001db7c  lea     rcx, [rsp+0E8h+var_58]
0x18001db84  call    _RadioManager__Advise____2____lambda_1___operator__
0x18001db89  nop
0x18001db8a  jmp     short loc_18001DBBC
0x18001db8c  test    ebx, ebx
0x18001db8e  jns     short loc_18001DB40
0x18001db90  lea     rax, aCoimpersonatec; "CoImpersonateClient failed"
0x18001db97  mov     [rsp+0E8h+var_78], rax
0x18001db9c  cmp     [rsp+0E8h+var_48], dil
0x18001dba4  jz      short loc_18001DBBC
0x18001dba6  mov     [rsp+0E8h+var_48], dil
0x18001dbae  lea     rcx, [rsp+0E8h+var_58]
0x18001dbb6  call    _RadioManager__Advise____2____lambda_1___operator__
0x18001dbbb  nop
0x18001dbbc  mov     eax, ebx
0x18001dbbe  jmp     loc_18001DF63
0x18001dbc3  mov     [rsp+0E8h+var_68], rdi
0x18001dbcb  mov     rax, [rsi]
0x18001dbce  lea     r8, [rsp+0E8h+var_68]
0x18001dbd6  lea     rdx, _GUID_b453e674_f489_41c5_9955_983c9fc264b2
0x18001dbdd  mov     rcx, rsi
0x18001dbe0  mov     rax, [rax]
0x18001dbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbe8  mov     ebx, eax
0x18001dbea  mov     [rsp+0E8h+var_70], eax
0x18001dbee  test    eax, eax
0x18001dbf0  jns     short loc_18001DC48
0x18001dbf2  cmp     eax, 80004002h
0x18001dbf7  jnz     short loc_18001DC02
0x18001dbf9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001dbfe  mov     ebx, [rsp+0E8h+var_70]
0x18001dc02  lea     rax, aQueryinterface_0; "QueryInterface<IUIRadioManagerNotifySin"...
0x18001dc09  mov     [rsp+0E8h+var_78], rax
0x18001dc0e  lea     rcx, [rsp+0E8h+var_68]
0x18001dc16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dc1b  nop
0x18001dc1c  call    cs:__imp_CoRevertToSelf
0x18001dc22  nop
0x18001dc23  cmp     [rsp+0E8h+var_48], dil
0x18001dc2b  jz      short loc_18001DC43
0x18001dc2d  mov     [rsp+0E8h+var_48], dil
0x18001dc35  lea     rcx, [rsp+0E8h+var_58]
0x18001dc3d  call    _RadioManager__Advise____2____lambda_1___operator__
0x18001dc42  nop
0x18001dc43  jmp     loc_18001DBBC
0x18001dc48  mov     rcx, [rsp+0E8h+var_68]; this
0x18001dc50  call    ?SetProxyBlanket@RMAPI@@YAJPEAUIUnknown@@@Z; RMAPI::SetProxyBlanket(IUnknown *)
0x18001dc55  mov     ebx, eax
0x18001dc57  mov     [rsp+0E8h+var_70], eax
0x18001dc5b  test    eax, eax
0x18001dc5d  jns     short loc_18001DCA5
0x18001dc5f  lea     rax, aRmapiSetproxyb; "RMAPI::SetProxyBlanket(IUIRadioManagerN"...
0x18001dc66  mov     [rsp+0E8h+var_78], rax
0x18001dc6b  lea     rcx, [rsp+0E8h+var_68]
0x18001dc73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dc78  nop
0x18001dc79  call    cs:__imp_CoRevertToSelf
0x18001dc7f  nop
0x18001dc80  cmp     [rsp+0E8h+var_48], dil
0x18001dc88  jz      short loc_18001DCA0
0x18001dc8a  mov     [rsp+0E8h+var_48], dil
0x18001dc92  lea     rcx, [rsp+0E8h+var_58]
0x18001dc9a  call    _RadioManager__Advise____2____lambda_1___operator__
0x18001dc9f  nop
0x18001dca0  jmp     loc_18001DBBC
0x18001dca5  mov     [rsp+0E8h+ppInterface], rdi
0x18001dcad  lea     rcx, [rsp+0E8h+ppInterface]
0x18001dcb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dcba  lea     rdx, [rsp+0E8h+ppInterface]; ppInterface
0x18001dcc2  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18001dcc9  call    cs:__imp_CoGetCallContext
0x18001dccf  mov     ebx, eax
0x18001dcd1  mov     [rsp+0E8h+var_70], eax
0x18001dcd5  test    eax, eax
0x18001dcd7  jns     short loc_18001DD2D
0x18001dcd9  lea     rax, aCogetcallconte; "CoGetCallContext failed"
0x18001dce0  mov     [rsp+0E8h+var_78], rax
0x18001dce5  lea     rcx, [rsp+0E8h+ppInterface]
0x18001dced  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dcf2  nop
0x18001dcf3  lea     rcx, [rsp+0E8h+var_68]
0x18001dcfb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dd00  nop
0x18001dd01  call    cs:__imp_CoRevertToSelf
0x18001dd07  nop
0x18001dd08  cmp     [rsp+0E8h+var_48], dil
0x18001dd10  jz      short loc_18001DD28
0x18001dd12  mov     [rsp+0E8h+var_48], dil
0x18001dd1a  lea     rcx, [rsp+0E8h+var_58]
0x18001dd22  call    _RadioManager__Advise____2____lambda_1___operator__
0x18001dd27  nop
0x18001dd28  jmp     loc_18001DBBC
0x18001dd2d  mov     [rsp+0E8h+var_38], rdi
0x18001dd35  mov     rcx, [rsp+0E8h+ppInterface]
0x18001dd3d  mov     rax, [rcx]
0x18001dd40  lea     r8, [rsp+0E8h+var_38]
0x18001dd48  mov     edx, 100000h
0x18001dd4d  mov     rax, [rax+18h]
0x18001dd51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd56  mov     ebx, eax
0x18001dd58  mov     [rsp+0E8h+var_70], eax
0x18001dd5c  test    eax, eax
0x18001dd5e  jns     short loc_18001DDC2
0x18001dd60  lea     rax, aIcallingproces; "ICallingProcessInfo::OpenCallerProcessH"...
0x18001dd67  mov     [rsp+0E8h+var_78], rax
0x18001dd6c  lea     rcx, [rsp+0E8h+var_38]
0x18001dd74  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001dd79  nop
0x18001dd7a  lea     rcx, [rsp+0E8h+ppInterface]
0x18001dd82  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dd87  nop
0x18001dd88  lea     rcx, [rsp+0E8h+var_68]
0x18001dd90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dd95  nop
0x18001dd96  call    cs:__imp_CoRevertToSelf
0x18001dd9c  nop
0x18001dd9d  cmp     [rsp+0E8h+var_48], dil
0x18001dda5  jz      short loc_18001DDBD
0x18001dda7  mov     [rsp+0E8h+var_48], dil
0x18001ddaf  lea     rcx, [rsp+0E8h+var_58]
0x18001ddb7  call    _RadioManager__Advise____2____lambda_1___operator__
0x18001ddbc  nop
0x18001ddbd  jmp     loc_18001DBBC
0x18001ddc2  lea     rcx, [r14+0A0h]; lpCriticalSection
0x18001ddc9  mov     rdx, [rsp+0E8h+var_68]; struct IUnknown *
0x18001ddd1  call    ?Add@ConnectionPointContainer@@QEAAKPEAUIUnknown@@@Z; ConnectionPointContainer::Add(IUnknown *)
0x18001ddd6  mov     [rsp+0E8h+var_60], eax
0x18001dddd  xorps   xmm0, xmm0
0x18001dde0  xor     eax, eax
0x18001dde2  movups  [rsp+0E8h+var_90], xmm0
0x18001dde7  mov     [rsp+0E8h+var_80], rax
0x18001ddec  lea     rsi, [r14-8]
0x18001ddf0  mov     qword ptr [rsp+0E8h+var_90], rsi
0x18001ddf5  lea     rax, [rsp+0E8h+var_60]
0x18001ddfd  mov     qword ptr [rsp+0E8h+var_90+8], rax
0x18001de02  mov     byte ptr [rsp+0E8h+var_80], 1
0x18001de07  lea     rbx, [r14+0E8h]
0x18001de0e  mov     rcx, rbx; lpCriticalSection
0x18001de11  call    cs:__imp_EnterCriticalSection
0x18001de17  mov     [rsp+0E8h+var_A8], rbx
0x18001de1c  lea     rbx, [r14+140h]
0x18001de23  mov     ecx, 20h ; ' '; Size
0x18001de28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001de2d  mov     [rsp+0E8h+var_A0], rax
0x18001de32  xorps   xmm0, xmm0
0x18001de35  movups  xmmword ptr [rax], xmm0
0x18001de38  movups  xmmword ptr [rax+10h], xmm0
0x18001de3c  mov     r9d, [rsp+0E8h+var_60]
0x18001de44  lea     r8, [rsp+0E8h+var_38]
0x18001de4c  mov     rdx, rsi
0x18001de4f  mov     rcx, rax; pv
0x18001de52  call    ??0AdviseInstance@@QEAA@PEAVRadioManager@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z; AdviseInstance::AdviseInstance(RadioManager *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ulong)
0x18001de57  nop
0x18001de58  mov     [rsp+0E8h+var_B8], rax
0x18001de5d  mov     rdx, [rbx+8]
0x18001de61  cmp     rdx, [rbx+10h]
0x18001de65  jz      short loc_18001DE76
0x18001de67  mov     [rsp+0E8h+var_B8], rdi
0x18001de6c  mov     [rdx], rax
0x18001de6f  add     qword ptr [rbx+8], 8
0x18001de74  jmp     short loc_18001DE84
0x18001de76  lea     r8, [rsp+0E8h+var_B8]
0x18001de7b  mov     rcx, rbx
0x18001de7e  call    ??$_Emplace_reallocate@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@?$vector@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@V?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<AdviseInstance>>::_Emplace_reallocate<std::unique_ptr<AdviseInstance>>(std::unique_ptr<AdviseInstance> * const,std::unique_ptr<AdviseInstance> &&)
0x18001de83  nop
0x18001de84  lea     rcx, [rsp+0E8h+var_B8]
0x18001de89  call    ??1?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@QEAA@XZ; std::unique_ptr<AdviseInstance>::~unique_ptr<AdviseInstance>(void)
0x18001de8e  mov     eax, [rsp+0E8h+var_60]
0x18001de95  mov     [r15], eax
0x18001de98  mov     eax, cs:dword_180037050
0x18001de9e  cmp     eax, 4
0x18001dea1  jbe     short loc_18001DED7
0x18001dea3  mov     eax, [r15]
0x18001dea6  mov     dword ptr [rsp+0E8h+var_B8], eax
0x18001deaa  lea     rax, aAdviseCookieTr; "Advise cookie tracked"
0x18001deb1  mov     [rsp+0E8h+var_A0], rax
0x18001deb6  lea     rax, [rsp+0E8h+var_B8]
0x18001debb  mov     [rsp+0E8h+var_C0], rax
0x18001dec0  lea     rax, [rsp+0E8h+var_A0]
0x18001dec5  mov     [rsp+0E8h+var_C8], rax
0x18001deca  lea     rdx, word_18003004A
0x18001ded1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001ded6  nop
0x18001ded7  lea     rcx, [rsp+0E8h+var_A8]
0x18001dedc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001dee1  nop
0x18001dee2  jmp     short loc_18001DEEF
0x18001dee4  mov     rsi, [rsp+0E8h+var_98]
0x18001dee9  add     rsi, 0FFFFFFFFFFFFFFF8h
0x18001deed  xor     edi, edi
0x18001deef  mov     ebx, [rsp+0E8h+var_70]
0x18001def3  test    ebx, ebx
0x18001def5  js      short loc_18001DF03
0x18001def7  mov     rcx, rsi; struct RadioManager *
0x18001defa  call    ?AddRefSingleton@@YAXPEAVRadioManager@@@Z; AddRefSingleton(RadioManager *)
0x18001deff  mov     ebx, [rsp+0E8h+var_70]
0x18001df03  lea     rcx, [rsp+0E8h+var_38]
0x18001df0b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001df10  nop
0x18001df11  lea     rcx, [rsp+0E8h+ppInterface]
0x18001df19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001df1e  nop
0x18001df1f  lea     rcx, [rsp+0E8h+var_68]
0x18001df27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001df2c  nop
0x18001df2d  call    cs:__imp_CoRevertToSelf
0x18001df33  nop
0x18001df34  cmp     [rsp+0E8h+var_48], dil
0x18001df3c  jz      short loc_18001DF54
0x18001df3e  mov     [rsp+0E8h+var_48], dil
0x18001df46  lea     rcx, [rsp+0E8h+var_58]
0x18001df4e  call    _RadioManager__Advise____2____lambda_1___operator__
0x18001df53  nop
0x18001df54  jmp     loc_18001DBBC
0x18001df59  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001df5e  mov     eax, 80070057h
0x18001df63  mov     rcx, [rsp+0E8h+var_30]
0x18001df6b  xor     rcx, rsp; StackCookie
0x18001df6e  call    __security_check_cookie
0x18001df73  add     rsp, 0C0h
0x18001df7a  pop     r15
0x18001df7c  pop     r14
0x18001df7e  pop     rdi
0x18001df7f  pop     rsi
0x18001df80  pop     rbx
0x18001df81  retn
```
