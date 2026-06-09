# CloudServiceController::_RetryDownloadMessage(ISmMessage *)

- ea: `0x18007bd90`
- end: `0x18007c26e`
- name: `?_RetryDownloadMessage@CloudServiceController@@AEAAJPEAUISmMessage@@@Z`
- size: `1246`
- prototype: `__int64 __fastcall(CloudServiceController *__hidden this, struct ISmMessage *)`
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800016a0`
- `0x180005c50`
- `0x180008870`
- `0x1800088c4`
- `0x18000b7fc`
- `0x180015050`
- `0x180036e84`
- `0x1800761a4`
- `0x180077498`
- `0x1800774d0`
- `0x1800795d0`
- `0x18007aa78`
- `0x18007bd90`
- `0x180082a2c`
- `0x18008be74`
- `0x180092644`
- `0x1800964ec`
- `0x18009a588`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## string_xrefs

- `0x18007be74`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007bef7`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007bf4b`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007bf90`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007bfd9`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c02f`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c0f6`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c124`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c142`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007c1c1`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007bdd1`: `CloudServiceController::_RetryDownloadMessage`

## pseudocode

```c
__int64 __fastcall CloudServiceController::_RetryDownloadMessage(AsyncMediaServiceClient **this, struct ISmMessage *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int SyncState; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  struct ChatServiceMessage *v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  struct CloudServiceAccountProvider *v26; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  struct ChatServiceParticipant *v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v30; // [rsp+68h] [rbp-98h] BYREF
  struct ISmEntryId *v31; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v32[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v33; // [rsp+88h] [rbp-78h] BYREF
  __int64 v34; // [rsp+8Ah] [rbp-76h]
  int v35; // [rsp+92h] [rbp-6Eh]
  __int16 v36; // [rsp+96h] [rbp-6Ah]
  __m128i si128; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v39[256]; // [rsp+B0h] [rbp-50h] BYREF

  StringCchPrintfW(v39, 0x100u, L"%S(%d):%s", "CloudServiceController::_RetryDownloadMessage", 1837, L"Enter");
  if ( (unsigned int)dword_1800FD5F0 > 5 )
  {
    v28 = (struct ChatServiceParticipant *)v39;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v4,
      (int)byte_1800EE4FB,
      v5,
      v6,
      (const OLECHAR **)&v28);
  }
  v29 = 0;
  ATL::CComQIPtr<ISmMessagePriv,&__s_GUID const _GUID_5f8637bb_473a_4af0_91bf_6b0ecd96fbe1>::CComQIPtr<ISmMessagePriv,&__s_GUID const _GUID_5f8637bb_473a_4af0_91bf_6b0ecd96fbe1>(
    &v29,
    a2);
  SyncState = CloudServiceController::_GetSyncState(this);
  if ( SyncState == 4 )
  {
    v8 = -2147024875;
    v9 = -2147024875;
LABEL_12:
    Log_HREvent_58(v9);
    goto LABEL_44;
  }
  if ( !SyncState )
  {
    v26 = 0;
    v10 = CloudServiceAccountProvider::CreateInstance(&v26);
    v8 = v10;
    if ( v10 < 0 || (v10 = AsyncMediaServiceClient::SignIn(this[7], v26), v8 = v10, v10 < 0) )
    {
      Log_HREvent_58(v10);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
      goto LABEL_44;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  }
  v30 = 0;
  v24 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v29 + 912LL))(v29, &v24, &v30);
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = v11;
    goto LABEL_12;
  }
  v32[0] = (unsigned __int16 *)&v33;
  v32[1] = (unsigned __int16 *)&v33;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          v32,
                          v24,
                          (unsigned __int64)v30 >> 1) )
  {
    v23 = 0;
    v12 = ChatServiceMessage::CreateInstance(v32[0], &v23);
    v8 = v12;
    if ( v12 >= 0 )
    {
      v25 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 168LL))(v29, &v25);
      v8 = v13;
      if ( v13 < 0
        || (v27 = 0,
            v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 56LL))(v25, &v27),
            v8 = v13,
            v13 < 0) )
      {
        Log_HREvent_58(v13);
      }
      else
      {
        v15 = v27;
        if ( !v27 )
        {
          Log_AssertionEvent_43(
            v14,
            "onecoreuap\\base\\appmodel\\messagingom\\cloudservices\\cloudservicecontroller.cpp",
            1875);
          v15 = v27;
          if ( !v27 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            v15 = v27;
          }
        }
        v16 = 0;
        v38 = -1;
        si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        if ( v15 )
        {
          while ( 1 )
          {
            v26 = 0;
            v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct CloudServiceAccountProvider **))(*(_QWORD *)v25 + 48LL))(
                    v25,
                    v16,
                    &v26);
            v8 = v17;
            if ( v17 < 0 )
              break;
            v28 = 0;
            v18 = ChatServiceParticipant::CreateInstance(v26, &v28);
            v8 = v18;
            if ( v18 < 0 )
            {
              v20 = v18;
              goto LABEL_35;
            }
            if ( !utl::vector<ATL::CComPtr<MessageChangeItem>,utl::allocator<ATL::CComPtr<MessageChangeItem>>>::emplace_back<ATL::CComPtr<MessageChangeItem> &,0>(
                    (__int64)&si128,
                    &v28) )
            {
              v8 = -2147024882;
              v20 = -2147024882;
LABEL_35:
              Log_HREvent_58(v20);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
              goto LABEL_37;
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
            if ( ++v16 >= v27 )
              goto LABEL_31;
          }
          Log_HREvent_58(v17);
LABEL_37:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
        }
        else
        {
LABEL_31:
          v19 = ChatServiceMessage::put_Participants(v23, &si128);
          v8 = v19;
          if ( v19 < 0
            || (v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 552LL))(v29, 1), v8 = v19, v19 < 0) )
          {
            Log_HREvent_58(v19);
          }
          else
          {
            v31 = 0;
            v21 = (*(__int64 (__fastcall **)(__int64, struct ISmEntryId **))(*(_QWORD *)v29 + 184LL))(v29, &v31);
            v8 = v21;
            if ( v21 >= 0 )
            {
              v21 = CloudServiceController::_DownloadOneMessage((CloudServiceController *)this, v23, v31, 0);
              v8 = v21;
              if ( v21 >= 0 )
              {
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
                utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&si128);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
                v8 = 0;
                goto LABEL_44;
              }
            }
            Log_HREvent_58(v21);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
          }
        }
        utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(&si128);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    }
    else
    {
      Log_HREvent_58(v12);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  }
  else
  {
    v8 = -2147024882;
    Log_HREvent_58(-2147024882);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
LABEL_44:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  return v8;
}

```

## disassembly

```asm
0x18007bd90  mov     [rsp-8+arg_10], rbx
0x18007bd95  mov     [rsp-8+arg_18], rsi
0x18007bd9a  push    rbp
0x18007bd9b  push    r14
0x18007bd9d  push    r15
0x18007bd9f  lea     rbp, [rsp-1C0h]
0x18007bda7  sub     rsp, 2C0h
0x18007bdae  mov     rax, cs:__security_cookie
0x18007bdb5  xor     rax, rsp
0x18007bdb8  mov     [rbp+1D0h+var_20], rax
0x18007bdbf  lea     rax, aEnter; "Enter"
0x18007bdc6  mov     rbx, rdx
0x18007bdc9  mov     r14, rcx
0x18007bdcc  mov     [rsp+2D0h+var_2A8], rax
0x18007bdd1  lea     r9, aCloudserviceco_17; "CloudServiceController::_RetryDownloadM"...
0x18007bdd8  mov     dword ptr [rsp+2D0h+var_2B0], 72Dh
0x18007bde0  lea     r8, aSDS; "%S(%d):%s"
0x18007bde7  mov     edx, 100h; unsigned __int64
0x18007bdec  lea     rcx, [rbp+1D0h+var_220]; unsigned __int16 *
0x18007bdf0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007bdf5  mov     eax, cs:dword_1800FD5F0
0x18007bdfb  cmp     eax, 5
0x18007bdfe  jbe     short loc_18007BE1F
0x18007be00  lea     rax, [rbp+1D0h+var_220]
0x18007be04  mov     [rsp+2D0h+var_278], rax
0x18007be09  lea     rdx, byte_1800EE4FB
0x18007be10  lea     rax, [rsp+2D0h+var_278]
0x18007be15  mov     [rsp+2D0h+var_2B0], rax
0x18007be1a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007be1f  xor     r15d, r15d
0x18007be22  lea     rcx, [rsp+2D0h+var_270]
0x18007be27  mov     rdx, rbx
0x18007be2a  mov     [rsp+2D0h+var_270], r15
0x18007be2f  call    ??0?$CComQIPtr@UISmMessagePriv@@$1?_GUID_5f8637bb_473a_4af0_91bf_6b0ecd96fbe1@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmMessagePriv,&__s_GUID const _GUID_5f8637bb_473a_4af0_91bf_6b0ecd96fbe1>::CComQIPtr<ISmMessagePriv,&__s_GUID const _GUID_5f8637bb_473a_4af0_91bf_6b0ecd96fbe1>(IUnknown *)
0x18007be34  mov     rcx, r14
0x18007be37  call    ?_GetSyncState@CloudServiceController@@AEAA?AW4SyncState@1@XZ; CloudServiceController::_GetSyncState(void)
0x18007be3c  cmp     eax, 4
0x18007be3f  jnz     short loc_18007BE55
0x18007be41  mov     ebx, 80070015h
0x18007be46  mov     r9d, 735h
0x18007be4c  mov     ecx, ebx
0x18007be4e  xor     edx, edx
0x18007be50  jmp     loc_18007BEF7
0x18007be55  test    eax, eax
0x18007be57  jnz     short loc_18007BEBC
0x18007be59  lea     rcx, [rsp+2D0h+var_288]; struct CloudServiceAccountProvider **
0x18007be5e  mov     [rsp+2D0h+var_288], r15
0x18007be63  call    ?CreateInstance@CloudServiceAccountProvider@@SAJPEAPEAV1@@Z; CloudServiceAccountProvider::CreateInstance(CloudServiceAccountProvider * *)
0x18007be68  mov     ebx, eax
0x18007be6a  test    eax, eax
0x18007be6c  jns     short loc_18007BE96
0x18007be6e  mov     r9d, 73Ch
0x18007be74  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007be7b  mov     edx, 1
0x18007be80  mov     ecx, eax; int
0x18007be82  call    Log_HREvent_58
0x18007be87  lea     rcx, [rsp+2D0h+var_288]
0x18007be8c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007be91  jmp     loc_18007C23A
0x18007be96  mov     rdx, [rsp+2D0h+var_288]; struct CloudServiceAccountProvider *
0x18007be9b  mov     rcx, [r14+38h]; this
0x18007be9f  call    ?SignIn@AsyncMediaServiceClient@@QEAAJPEAVCloudServiceAccountProvider@@@Z; AsyncMediaServiceClient::SignIn(CloudServiceAccountProvider *)
0x18007bea4  mov     ebx, eax
0x18007bea6  test    eax, eax
0x18007bea8  jns     short loc_18007BEB2
0x18007beaa  mov     r9d, 73Fh
0x18007beb0  jmp     short loc_18007BE74
0x18007beb2  lea     rcx, [rsp+2D0h+var_288]
0x18007beb7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007bebc  mov     rcx, [rsp+2D0h+var_270]
0x18007bec1  lea     r8, [rsp+2D0h+var_268]
0x18007bec6  mov     [rsp+2D0h+var_268], r15d
0x18007becb  lea     rdx, [rsp+2D0h+var_298]
0x18007bed0  mov     [rsp+2D0h+var_298], r15
0x18007bed5  mov     rax, [rcx]
0x18007bed8  mov     rax, [rax+390h]
0x18007bedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bee4  mov     ebx, eax
0x18007bee6  test    eax, eax
0x18007bee8  jns     short loc_18007BF08
0x18007beea  mov     r9d, 745h
0x18007bef0  mov     edx, 1
0x18007bef5  mov     ecx, eax; int
0x18007bef7  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007befe  call    Log_HREvent_58
0x18007bf03  jmp     loc_18007C23A
0x18007bf08  mov     r8d, [rsp+2D0h+var_268]
0x18007bf0d  lea     rax, [rbp+1D0h+var_248]
0x18007bf11  mov     rdx, [rsp+2D0h+var_298]
0x18007bf16  lea     rcx, [rsp+2D0h+var_258]
0x18007bf1b  mov     [rsp+2D0h+var_258], rax
0x18007bf20  lea     rax, [rbp+1D0h+var_248]
0x18007bf24  shr     r8, 1
0x18007bf27  mov     [rbp+1D0h+var_250], rax
0x18007bf2b  mov     [rbp+1D0h+var_246], r15
0x18007bf2f  mov     [rbp+1D0h+var_23E], r15d
0x18007bf33  mov     [rbp+1D0h+var_23A], r15w
0x18007bf38  mov     [rbp+1D0h+var_248], r15w
0x18007bf3d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18007bf42  test    al, al
0x18007bf44  jnz     short loc_18007BF70
0x18007bf46  mov     ebx, 8007000Eh
0x18007bf4b  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007bf52  mov     ecx, ebx; int
0x18007bf54  mov     r9d, 749h
0x18007bf5a  xor     edx, edx
0x18007bf5c  call    Log_HREvent_58
0x18007bf61  lea     rcx, [rsp+2D0h+var_258]
0x18007bf66  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18007bf6b  jmp     loc_18007C23A
0x18007bf70  mov     rcx, [rsp+2D0h+var_258]; unsigned __int16 *
0x18007bf75  lea     rdx, [rsp+2D0h+var_2A0]; struct ChatServiceMessage **
0x18007bf7a  mov     [rsp+2D0h+var_2A0], r15
0x18007bf7f  call    ?CreateInstance@ChatServiceMessage@@SAJPEBGPEAPEAV1@@Z; ChatServiceMessage::CreateInstance(ushort const *,ChatServiceMessage * *)
0x18007bf84  mov     ebx, eax
0x18007bf86  test    eax, eax
0x18007bf88  jns     short loc_18007BFAF
0x18007bf8a  mov     r9d, 74Ch
0x18007bf90  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007bf97  mov     edx, 1
0x18007bf9c  mov     ecx, eax; int
0x18007bf9e  call    Log_HREvent_58
0x18007bfa3  lea     rcx, [rsp+2D0h+var_2A0]
0x18007bfa8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007bfad  jmp     short loc_18007BF61
0x18007bfaf  mov     rcx, [rsp+2D0h+var_270]
0x18007bfb4  lea     rdx, [rsp+2D0h+var_290]
0x18007bfb9  mov     [rsp+2D0h+var_290], r15
0x18007bfbe  mov     rax, [rcx]
0x18007bfc1  mov     rax, [rax+0A8h]
0x18007bfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfcd  mov     ebx, eax
0x18007bfcf  test    eax, eax
0x18007bfd1  jns     short loc_18007BFF8
0x18007bfd3  mov     r9d, 750h
0x18007bfd9  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007bfe0  mov     edx, 1
0x18007bfe5  mov     ecx, eax; int
0x18007bfe7  call    Log_HREvent_58
0x18007bfec  lea     rcx, [rsp+2D0h+var_290]
0x18007bff1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007bff6  jmp     short loc_18007BFA3
0x18007bff8  mov     rcx, [rsp+2D0h+var_290]
0x18007bffd  lea     rdx, [rsp+2D0h+var_280]
0x18007c002  mov     [rsp+2D0h+var_280], r15d
0x18007c007  mov     rax, [rcx]
0x18007c00a  mov     rax, [rax+38h]
0x18007c00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c013  mov     ebx, eax
0x18007c015  test    eax, eax
0x18007c017  jns     short loc_18007C021
0x18007c019  mov     r9d, 752h
0x18007c01f  jmp     short loc_18007BFD9
0x18007c021  mov     eax, [rsp+2D0h+var_280]
0x18007c025  test    eax, eax
0x18007c027  jnz     short loc_18007C04C
0x18007c029  mov     r8d, 753h
0x18007c02f  lea     rdx, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c036  call    Log_AssertionEvent_43
0x18007c03b  mov     eax, [rsp+2D0h+var_280]
0x18007c03f  test    eax, eax
0x18007c041  jnz     short loc_18007C04C
0x18007c043  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007c048  mov     eax, [rsp+2D0h+var_280]
0x18007c04c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18007c054  mov     esi, r15d
0x18007c057  mov     [rbp+1D0h+var_228], 0FFFFFFFFFFFFFFFFh
0x18007c05f  movdqu  [rbp+1D0h+var_238], xmm0
0x18007c064  test    eax, eax
0x18007c066  jz      short loc_18007C0D7
0x18007c068  mov     rcx, [rsp+2D0h+var_290]
0x18007c06d  lea     r8, [rsp+2D0h+var_288]
0x18007c072  mov     [rsp+2D0h+var_288], r15
0x18007c077  mov     edx, esi
0x18007c079  mov     rax, [rcx]
0x18007c07c  mov     rax, [rax+30h]
0x18007c080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c085  mov     ebx, eax
0x18007c087  test    eax, eax
0x18007c089  js      loc_18007C13C
0x18007c08f  mov     rcx, [rsp+2D0h+var_288]; struct ISmRecipient *
0x18007c094  lea     rdx, [rsp+2D0h+var_278]; struct ChatServiceParticipant **
0x18007c099  mov     [rsp+2D0h+var_278], r15
0x18007c09e  call    ?CreateInstance@ChatServiceParticipant@@SAJPEAUISmRecipient@@PEAPEAV1@@Z; ChatServiceParticipant::CreateInstance(ISmRecipient *,ChatServiceParticipant * *)
0x18007c0a3  mov     ebx, eax
0x18007c0a5  test    eax, eax
0x18007c0a7  js      short loc_18007C117
0x18007c0a9  lea     rdx, [rsp+2D0h+var_278]
0x18007c0ae  lea     rcx, [rbp+1D0h+var_238]
0x18007c0b2  call    ??$emplace_back@AEAV?$CComPtr@VMessageChangeItem@@@ATL@@$0A@@?$vector@V?$CComPtr@VMessageChangeItem@@@ATL@@V?$allocator@V?$CComPtr@VMessageChangeItem@@@ATL@@@utl@@@utl@@QEAA_NAEAV?$CComPtr@VMessageChangeItem@@@ATL@@@Z; utl::vector<ATL::CComPtr<MessageChangeItem>,utl::allocator<ATL::CComPtr<MessageChangeItem>>>::emplace_back<ATL::CComPtr<MessageChangeItem> &,0>(ATL::CComPtr<MessageChangeItem> &)
0x18007c0b7  test    al, al
0x18007c0b9  jz      short loc_18007C106
0x18007c0bb  lea     rcx, [rsp+2D0h+var_278]
0x18007c0c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c0c5  lea     rcx, [rsp+2D0h+var_288]
0x18007c0ca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c0cf  inc     esi
0x18007c0d1  cmp     esi, [rsp+2D0h+var_280]
0x18007c0d5  jb      short loc_18007C068
0x18007c0d7  mov     rcx, [rsp+2D0h+var_2A0]
0x18007c0dc  lea     rdx, [rbp+1D0h+var_238]
0x18007c0e0  call    ?put_Participants@ChatServiceMessage@@QEAAJPEBV?$vector@V?$CComPtr@VChatServiceParticipant@@@ATL@@V?$allocator@V?$CComPtr@VChatServiceParticipant@@@ATL@@@utl@@@utl@@@Z; ChatServiceMessage::put_Participants(utl::vector<ATL::CComPtr<ChatServiceParticipant>,utl::allocator<ATL::CComPtr<ChatServiceParticipant>>> const *)
0x18007c0e5  mov     ebx, eax
0x18007c0e7  mov     edx, 1
0x18007c0ec  test    eax, eax
0x18007c0ee  jns     short loc_18007C16D
0x18007c0f0  mov     r9d, 761h
0x18007c0f6  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c0fd  mov     ecx, eax; int
0x18007c0ff  call    Log_HREvent_58
0x18007c104  jmp     short loc_18007C15F
0x18007c106  mov     ebx, 8007000Eh
0x18007c10b  mov     r9d, 75Eh
0x18007c111  mov     ecx, ebx
0x18007c113  xor     edx, edx
0x18007c115  jmp     short loc_18007C124
0x18007c117  mov     r9d, 75Ch
0x18007c11d  mov     edx, 1
0x18007c122  mov     ecx, eax; int
0x18007c124  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c12b  call    Log_HREvent_58
0x18007c130  lea     rcx, [rsp+2D0h+var_278]
0x18007c135  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c13a  jmp     short loc_18007C155
0x18007c13c  mov     r9d, 759h
0x18007c142  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c149  mov     edx, 1
0x18007c14e  mov     ecx, eax; int
0x18007c150  call    Log_HREvent_58
0x18007c155  lea     rcx, [rsp+2D0h+var_288]
0x18007c15a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c15f  lea     rcx, [rbp+1D0h+var_238]
0x18007c163  call    ?_Uninit@?$vector@V?$CComPtr@VSlideInfo@@@ATL@@V?$allocator@V?$CComPtr@VSlideInfo@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(void)
0x18007c168  jmp     loc_18007BFEC
0x18007c16d  mov     rcx, [rsp+2D0h+var_270]
0x18007c172  mov     rax, [rcx]
0x18007c175  mov     rax, [rax+228h]
0x18007c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c181  mov     ebx, eax
0x18007c183  test    eax, eax
0x18007c185  jns     short loc_18007C197
0x18007c187  mov     r9d, 764h
0x18007c18d  mov     edx, 1
0x18007c192  jmp     loc_18007C0F6
0x18007c197  mov     rcx, [rsp+2D0h+var_270]
0x18007c19c  lea     rdx, [rsp+2D0h+var_260]
0x18007c1a1  mov     [rsp+2D0h+var_260], r15
0x18007c1a6  mov     rax, [rcx]
0x18007c1a9  mov     rax, [rax+0B8h]
0x18007c1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c1b5  mov     ebx, eax
0x18007c1b7  test    eax, eax
0x18007c1b9  jns     short loc_18007C1E3
0x18007c1bb  mov     r9d, 768h
0x18007c1c1  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007c1c8  mov     edx, 1
0x18007c1cd  mov     ecx, eax; int
0x18007c1cf  call    Log_HREvent_58
0x18007c1d4  lea     rcx, [rsp+2D0h+var_260]
0x18007c1d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c1de  jmp     loc_18007C15F
0x18007c1e3  mov     r8, [rsp+2D0h+var_260]; struct ISmEntryId *
0x18007c1e8  xor     r9d, r9d; unsigned __int64
0x18007c1eb  mov     rdx, [rsp+2D0h+var_2A0]; struct ChatServiceMessage *
0x18007c1f0  mov     rcx, r14; this
0x18007c1f3  call    ?_DownloadOneMessage@CloudServiceController@@AEAAJPEAVChatServiceMessage@@PEAUISmEntryId@@_K@Z; CloudServiceController::_DownloadOneMessage(ChatServiceMessage *,ISmEntryId *,unsigned __int64)
0x18007c1f8  mov     ebx, eax
0x18007c1fa  test    eax, eax
0x18007c1fc  jns     short loc_18007C206
0x18007c1fe  mov     r9d, 76Ch
0x18007c204  jmp     short loc_18007C1C1
0x18007c206  lea     rcx, [rsp+2D0h+var_260]
0x18007c20b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c210  lea     rcx, [rbp+1D0h+var_238]
0x18007c214  call    ?_Uninit@?$vector@V?$CComPtr@VSlideInfo@@@ATL@@V?$allocator@V?$CComPtr@VSlideInfo@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<SlideInfo>,utl::allocator<ATL::CComPtr<SlideInfo>>>::_Uninit(void)
0x18007c219  lea     rcx, [rsp+2D0h+var_290]
0x18007c21e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c223  lea     rcx, [rsp+2D0h+var_2A0]
0x18007c228  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c22d  lea     rcx, [rsp+2D0h+var_258]
0x18007c232  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18007c237  mov     ebx, r15d
0x18007c23a  lea     rcx, [rsp+2D0h+var_270]
0x18007c23f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007c244  mov     eax, ebx
0x18007c246  mov     rcx, [rbp+1D0h+var_20]
0x18007c24d  xor     rcx, rsp; StackCookie
0x18007c250  call    __security_check_cookie
0x18007c255  lea     r11, [rsp+2D0h+var_10]
0x18007c25d  mov     rbx, [r11+30h]
0x18007c261  mov     rsi, [r11+38h]
0x18007c265  mov     rsp, r11
0x18007c268  pop     r15
0x18007c26a  pop     r14
0x18007c26c  pop     rbp
0x18007c26d  retn
```
