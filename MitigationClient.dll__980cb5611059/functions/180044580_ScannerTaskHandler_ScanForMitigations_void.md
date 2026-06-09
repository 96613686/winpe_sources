# ScannerTaskHandler::ScanForMitigations(void)

- ea: `0x180044580`
- end: `0x180044861`
- name: `?ScanForMitigations@ScannerTaskHandler@@AEAAJXZ`
- size: `737`
- prototype: `__int64 __fastcall(ScannerTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180044db0`

## callees

- `0x18000a6e0`
- `0x18000cecc`
- `0x18001055c`
- `0x18001208c`
- `0x180017670`
- `0x180017c84`
- `0x180017cb4`
- `0x180019764`
- `0x18002d4fc`
- `0x180044320`
- `0x180044394`
- `0x180044494`
- `0x180044580`
- `0x180044868`
- `0x180044944`
- `0x18004530c`
- `0x180045510`
- `0x180047020`
- `0x180048b20`
- `0x180049000`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180044616`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180044616`

## string_xrefs

- `0x180044662`: `onecore\base\diagnosis\mitigation\client\libs\scanner\scannertaskhandler.cpp`
- `0x1800446fc`: `onecore\base\diagnosis\mitigation\client\libs\scanner\scannertaskhandler.cpp`
- `0x1800447c3`: `onecore\base\diagnosis\mitigation\client\libs\scanner\scannertaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall ScannerTaskHandler::ScanForMitigations(ScannerTaskHandler *this)
{
  unsigned int v2; // edx
  HRESULT ClassObject; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, _QWORD, GUID *, __int64 *); // rbx
  int started; // eax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  unsigned int v11; // ebx
  bool v12; // di
  unsigned int v13; // r14d
  unsigned int v14; // r15d
  unsigned __int64 v15; // rdx
  unsigned __int8 v16; // cl
  __int64 v17; // rcx
  MitigationTelemetryClass *v18; // rax
  unsigned int v19; // edx
  int v20; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v24; // [rsp+48h] [rbp-B8h] BYREF
  void **v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  unsigned int v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+94h] [rbp-6Ch]
  bool v32[4]; // [rsp+9Ch] [rbp-64h]
  _QWORD v33[42]; // [rsp+A0h] [rbp-60h] BYREF
  char v34; // [rsp+1F0h] [rbp+F0h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "MitigationScannerMainActivity");
  v33[0] = &MitigationTelemetryClass::MitigationScannerMainActivity::`vftable';
  v34 = 0;
  MitigationTelemetryClass::MitigationScannerMainActivity::StartActivity(
    (MitigationTelemetryClass::MitigationScannerMainActivity *)v33,
    v2);
  v23 = 0;
  v24 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  ClassObject = CoGetClassObject(&CLSID_MitigationAPIBroker, 4u, 0, &GUID_00000001_0000_0000_c000_000000000046, &v24);
  v4 = ClassObject;
  if ( ClassObject < 0 )
  {
    v5 = 36;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\scanner\\scannertaskhandler.cpp",
      (const char *)(unsigned int)ClassObject,
      ppv);
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    MitigationTelemetryClass::MitigationScannerMainActivity::~MitigationScannerMainActivity((MitigationTelemetryClass::MitigationScannerMainActivity *)v33);
    return v4;
  }
  v6 = v24;
  v7 = *(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)v24 + 24LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
  ClassObject = v7(v6, 0, &GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe, &v23);
  v4 = ClassObject;
  if ( ClassObject < 0 )
  {
    v5 = 37;
    goto LABEL_5;
  }
  v25 = &IClientTriggerHandler::`vftable';
  v26 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>>>>>>(v27);
  wil::com_ptr_t<IMitigationManager,wil::err_exception_policy>::operator=(&v26, v23);
  v28 = xmmword_180065168;
  v25 = &ClientTriggerHandlerWnf::`vftable';
  v29 = 0;
  *(_WORD *)v32 = 0;
  v31 = WNF_RTSC_INVOKE_TROUBLESHOOTER;
  v30 = -1;
  started = ClientTriggerHandlerWnf::InitAndStartTriggerHandler((ClientTriggerHandlerWnf *)&v25);
  if ( started < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\scanner\\scannertaskhandler.cpp",
      (const char *)(unsigned int)started,
      ppv);
  v9 = (_QWORD *)v27[0];
  v10 = (_QWORD *)v27[1];
  while ( v9 != v10 )
  {
    if ( !(unsigned __int8)std::_State_manager<int>::valid(v9) )
      std::_Throw_future_error2(4);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
    v9 += 2;
  }
  ScannerTaskHandler::QueryScanningTriggerPublished(this);
  v11 = v30;
  v12 = v32[0];
  v13 = *((_DWORD *)this + 16);
  v14 = *((_DWORD *)this + 15);
  if ( MitigationTelemetryClass::IsEnabled(v16, v15) )
  {
    v18 = (MitigationTelemetryClass *)wil::details::static_lazy<MitigationTelemetryClass>::get(
                                        v17,
                                        _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
    MitigationTelemetryClass::MitigationWNFTriggered_(
      v18,
      *((_BYTE *)this + 56),
      v14,
      *((_BYTE *)this + 57),
      v13,
      v12,
      v11);
  }
  if ( *((_BYTE *)this + 56) || *((_BYTE *)this + 57) || MitigationRestartUtils::IsScheduledRestartComplete() )
  {
    v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    v4 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\scanner\\scannertaskhandler.cpp",
        (const char *)(unsigned int)v20,
        ppv);
      ClientTriggerHandlerWnf::~ClientTriggerHandlerWnf((ClientTriggerHandlerWnf *)&v25);
      goto LABEL_19;
    }
  }
  MitigationTelemetryClass::MitigationScannerMainActivity::Stop(
    (MitigationTelemetryClass::MitigationScannerMainActivity *)v33,
    v19);
  ClientTriggerHandlerWnf::~ClientTriggerHandlerWnf((ClientTriggerHandlerWnf *)&v25);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
  MitigationTelemetryClass::MitigationScannerMainActivity::~MitigationScannerMainActivity((MitigationTelemetryClass::MitigationScannerMainActivity *)v33);
  return 0;
}

```

## disassembly

```asm
0x180044580  push    rbp
0x180044582  push    rbx
0x180044583  push    rsi
0x180044584  push    rdi
0x180044585  push    r14
0x180044587  push    r15
0x180044589  lea     rbp, [rsp-118h]
0x180044591  sub     rsp, 218h
0x180044598  mov     rax, cs:__security_cookie
0x18004459f  xor     rax, rsp
0x1800445a2  mov     [rbp+140h+var_40], rax
0x1800445a9  mov     rsi, rcx
0x1800445ac  lea     rdx, aMitigationscan; "MitigationScannerMainActivity"
0x1800445b3  lea     rcx, [rbp+140h+var_1A0]
0x1800445b7  call    ??0?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800445bc  lea     rax, ??_7MitigationScannerMainActivity@MitigationTelemetryClass@@6B@; const MitigationTelemetryClass::MitigationScannerMainActivity::`vftable'
0x1800445c3  mov     [rbp+140h+var_1A0], rax
0x1800445c7  mov     [rbp+140h+var_50], 0
0x1800445ce  lea     rcx, [rbp+140h+var_1A0]; this
0x1800445d2  call    ?StartActivity@MitigationScannerMainActivity@MitigationTelemetryClass@@QEAAXK@Z; MitigationTelemetryClass::MitigationScannerMainActivity::StartActivity(ulong)
0x1800445d7  nop
0x1800445d8  mov     [rsp+240h+var_200], 0
0x1800445e1  mov     [rsp+240h+var_1F8], 0
0x1800445ea  lea     rcx, [rsp+240h+var_1F8]
0x1800445ef  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800445f4  lea     rax, [rsp+240h+var_1F8]
0x1800445f9  mov     [rsp+240h+ppv], rax; int
0x1800445fe  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180044605  xor     r8d, r8d; pvReserved
0x180044608  lea     r14d, [r8+4]
0x18004460c  mov     edx, r14d; dwClsContext
0x18004460f  lea     rcx, CLSID_MitigationAPIBroker; rclsid
0x180044616  call    cs:__imp_CoGetClassObject
0x18004461c  mov     ebx, eax
0x18004461e  test    eax, eax
0x180044620  jns     short loc_180044628
0x180044622  lea     edx, [r14+20h]
0x180044626  jmp     short loc_180044662
0x180044628  mov     rdi, [rsp+240h+var_1F8]
0x18004462d  mov     rax, [rdi]
0x180044630  mov     rbx, [rax+18h]
0x180044634  lea     rcx, [rsp+240h+var_200]
0x180044639  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004463e  lea     r9, [rsp+240h+var_200]
0x180044643  lea     r8, _GUID_c79a68dd_baba_4cab_bc48_b0af313ea5fe
0x18004464a  xor     edx, edx
0x18004464c  mov     rcx, rdi
0x18004464f  mov     rax, rbx
0x180044652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044657  mov     ebx, eax
0x180044659  test    eax, eax
0x18004465b  jns     short loc_18004467D
0x18004465d  mov     edx, 25h ; '%'; void *
0x180044662  lea     r8, aOnecoreBaseDia_8; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180044669  mov     r9d, eax; char *
0x18004466c  mov     rcx, [rbp+148h]; this
0x180044673  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044678  jmp     loc_1800447E0
0x18004467d  lea     rax, ??_7IClientTriggerHandler@@6B@; const IClientTriggerHandler::`vftable'
0x180044684  mov     [rsp+240h+var_1F0], rax
0x180044689  mov     [rsp+240h+var_1E8], 0
0x180044692  lea     rcx, [rsp+240h+var_1E0]
0x180044697  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>>>>>>(std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>> const &)
0x18004469c  mov     rdx, [rsp+240h+var_200]
0x1800446a1  lea     rcx, [rsp+240h+var_1E8]
0x1800446a6  call    ??4?$com_ptr_t@UIMitigationManager@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIMitigationManager@@@Z; wil::com_ptr_t<IMitigationManager,wil::err_exception_policy>::operator=(IMitigationManager *)
0x1800446ab  movups  xmm0, cs:xmmword_180065168
0x1800446b2  movdqu  [rsp+240h+var_1C8], xmm0
0x1800446b8  lea     rax, ??_7ClientTriggerHandlerWnf@@6B@; const ClientTriggerHandlerWnf::`vftable'
0x1800446bf  mov     [rsp+240h+var_1F0], rax
0x1800446c4  mov     [rbp+140h+var_1B8], 0
0x1800446cc  mov     word ptr [rbp+140h+var_1A4], 0
0x1800446d2  mov     rax, cs:WNF_RTSC_INVOKE_TROUBLESHOOTER
0x1800446d9  mov     [rbp+140h+var_1AC], rax
0x1800446dd  mov     [rbp+140h+var_1B0], 0FFFFFFFFh
0x1800446e4  lea     rcx, [rsp+240h+var_1F0]; this
0x1800446e9  call    ?InitAndStartTriggerHandler@ClientTriggerHandlerWnf@@UEAAJXZ; ClientTriggerHandlerWnf::InitAndStartTriggerHandler(void)
0x1800446ee  mov     rcx, [rbp+148h]; this
0x1800446f5  test    eax, eax
0x1800446f7  jns     short loc_18004470D
0x1800446f9  mov     r9d, eax; char *
0x1800446fc  lea     r8, aOnecoreBaseDia_8; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180044703  mov     edx, 29h ; ')'; void *
0x180044708  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004470d  mov     rbx, [rsp+240h+var_1E0]
0x180044712  mov     rdi, [rsp+240h+var_1D8]
0x180044717  jmp     short loc_18004473C
0x180044719  mov     rcx, rbx
0x18004471c  call    ?valid@?$_State_manager@H@std@@QEBA_NXZ; std::_State_manager<int>::valid(void)
0x180044721  test    al, al
0x180044723  jz      loc_180044803
0x180044729  mov     rcx, [rbx]
0x18004472c  mov     rax, [rcx]
0x18004472f  mov     rax, [rax+8]
0x180044733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044738  add     rbx, 10h
0x18004473c  cmp     rbx, rdi
0x18004473f  jnz     short loc_180044719
0x180044741  mov     rcx, rsi; this
0x180044744  call    ?QueryScanningTriggerPublished@ScannerTaskHandler@@AEAAXXZ; ScannerTaskHandler::QueryScanningTriggerPublished(void)
0x180044749  mov     ebx, [rbp+140h+var_1B0]
0x18004474c  mov     dil, [rbp+140h+var_1A4]
0x180044750  mov     r14d, [rsi+40h]
0x180044754  mov     r15d, [rsi+3Ch]
0x180044758  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18004475d  test    al, al
0x18004475f  jz      short loc_18004478D
0x180044761  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x180044768  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18004476d  mov     [rsp+240h+var_210], ebx; unsigned int
0x180044771  mov     [rsp+240h+var_218], dil; bool
0x180044776  mov     dword ptr [rsp+240h+ppv], r14d; int
0x18004477b  mov     r9b, [rsi+39h]; bool
0x18004477f  mov     r8d, r15d; unsigned int
0x180044782  mov     dl, [rsi+38h]; bool
0x180044785  mov     rcx, rax; this
0x180044788  call    ?MitigationWNFTriggered_@MitigationTelemetryClass@@QEAAX_NK0K0K@Z; MitigationTelemetryClass::MitigationWNFTriggered_(bool,ulong,bool,ulong,bool,ulong)
0x18004478d  cmp     byte ptr [rsi+38h], 0
0x180044791  jnz     short loc_1800447A2
0x180044793  cmp     byte ptr [rsi+39h], 0
0x180044797  jnz     short loc_1800447A2
0x180044799  call    ?IsScheduledRestartComplete@MitigationRestartUtils@@SA_NXZ; MitigationRestartUtils::IsScheduledRestartComplete(void)
0x18004479e  test    al, al
0x1800447a0  jz      short loc_18004480C
0x1800447a2  mov     rcx, [rsp+240h+var_200]
0x1800447a7  mov     rax, [rcx]
0x1800447aa  mov     rax, [rax+18h]
0x1800447ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447b3  mov     ebx, eax
0x1800447b5  test    eax, eax
0x1800447b7  jns     short loc_18004480C
0x1800447b9  mov     rcx, [rbp+148h]; this
0x1800447c0  mov     r9d, eax; char *
0x1800447c3  lea     r8, aOnecoreBaseDia_8; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800447ca  mov     edx, 3Dh ; '='; void *
0x1800447cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800447d4  nop
0x1800447d5  lea     rcx, [rsp+240h+var_1F0]; this
0x1800447da  call    ??1ClientTriggerHandlerWnf@@QEAA@XZ; ClientTriggerHandlerWnf::~ClientTriggerHandlerWnf(void)
0x1800447df  nop
0x1800447e0  lea     rcx, [rsp+240h+var_1F8]
0x1800447e5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800447ea  nop
0x1800447eb  lea     rcx, [rsp+240h+var_200]
0x1800447f0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800447f5  nop
0x1800447f6  lea     rcx, [rbp+140h+var_1A0]; this
0x1800447fa  call    ??1MitigationScannerMainActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::MitigationScannerMainActivity::~MitigationScannerMainActivity(void)
0x1800447ff  mov     eax, ebx
0x180044801  jmp     short loc_180044842
0x180044803  mov     ecx, r14d
0x180044806  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18004480c  lea     rcx, [rbp+140h+var_1A0]; this
0x180044810  call    ?Stop@MitigationScannerMainActivity@MitigationTelemetryClass@@QEAAXK@Z; MitigationTelemetryClass::MitigationScannerMainActivity::Stop(ulong)
0x180044815  nop
0x180044816  lea     rcx, [rsp+240h+var_1F0]; this
0x18004481b  call    ??1ClientTriggerHandlerWnf@@QEAA@XZ; ClientTriggerHandlerWnf::~ClientTriggerHandlerWnf(void)
0x180044820  nop
0x180044821  lea     rcx, [rsp+240h+var_1F8]
0x180044826  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004482b  nop
0x18004482c  lea     rcx, [rsp+240h+var_200]
0x180044831  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180044836  nop
0x180044837  lea     rcx, [rbp+140h+var_1A0]; this
0x18004483b  call    ??1MitigationScannerMainActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::MitigationScannerMainActivity::~MitigationScannerMainActivity(void)
0x180044840  xor     eax, eax
0x180044842  mov     rcx, [rbp+140h+var_40]
0x180044849  xor     rcx, rsp; StackCookie
0x18004484c  call    __security_check_cookie
0x180044851  add     rsp, 218h
0x180044858  pop     r15
0x18004485a  pop     r14
0x18004485c  pop     rdi
0x18004485d  pop     rsi
0x18004485e  pop     rbx
0x18004485f  pop     rbp
0x180044860  retn
```
