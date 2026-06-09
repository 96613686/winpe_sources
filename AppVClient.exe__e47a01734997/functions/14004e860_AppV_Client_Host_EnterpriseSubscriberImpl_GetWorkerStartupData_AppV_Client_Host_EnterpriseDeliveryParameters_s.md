# AppV::Client::Host::EnterpriseSubscriberImpl::GetWorkerStartupData(AppV::Client::Host::EnterpriseDeliveryParameters &,std::unique_ptr<AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::WorkerStartupData,std::default_delete<AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::WorkerStartupData>> &)

- ea: `0x14004e860`
- end: `0x14004ec42`
- name: `?GetWorkerStartupData@EnterpriseSubscriberImpl@Host@Client@AppV@@MEAA_KAEAUEnterpriseDeliveryParameters@234@AEAV?$unique_ptr@VWorkerStartupData@?$SubscriberImpl@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@VEnterpriseWorkerStateManager@345@@Host@Client@AppV@@U?$default_delete@VWorkerStartupData@?$SubscriberImpl@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@VEnterpriseWorkerStateManager@345@@Host@Client@AppV@@@std@@@std@@@Z`
- size: `994`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14004df14`
- `0x14004e860`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004e8ba`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004ea40`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004eaca`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004e8ba`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004ea40`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004eaca`
- `ole32!CoMarshalInterface` at `0x14004e940`
- `ole32!CoMarshalInterface` at `0x14004e940`
- `ole32!CreateStreamOnHGlobal` at `0x14004e8a0`
- `ole32!CreateStreamOnHGlobal` at `0x14004e8a0`

## string_xrefs

- `0x14004e8b3`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004e8ca`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004ea39`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004ea50`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004eac3`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004eada`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004e98c`: `Failed to marshal a Client event subscriber interface to a stream for use by other threads, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AppV::Client::Host::EnterpriseSubscriberImpl::GetWorkerStartupData(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  char *v6; // rax
  const char *v7; // rax
  unsigned __int64 v8; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  char *v13; // rax
  const char *v14; // rax
  unsigned __int64 FileId; // rax
  char *v16; // rax
  const char *v17; // rax
  void *v18; // rax
  int v19; // r10d
  __int64 v20; // rdx
  LPSTREAM v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  void (__fastcall ***v27)(_QWORD, __int64); // rcx
  HRESULT v28; // [rsp+40h] [rbp-C0h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  __int128 v35; // [rsp+90h] [rbp-70h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  char *v38[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v39; // [rsp+D0h] [rbp-30h]
  void **v40; // [rsp+D8h] [rbp-28h] BYREF
  char *v41; // [rsp+E8h] [rbp-18h] BYREF

  ppstm = 0;
  v28 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v28 < 0 )
  {
    v6 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v6 )
      v7 = v6 + 1;
    else
      v7 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    v8 = (unsigned int)v28
       | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v7) << 52)
       | 0x512E00000000LL;
    if ( ppstm )
      ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    return v8;
  }
  v28 = CoMarshalInterface(ppstm, &GUID_57bb7098_daee_48c6_8c1a_ea12cd2db64e, *(LPUNKNOWN *)a2, 3u, 0, 0);
  if ( v28 < 0 )
  {
    std::string::string(v38, "AppV::Client::Host::EnterpriseSubscriberImpl::GetWorkerStartupData");
    v39 = 662;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v32 = 0;
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v32,
      L"Failed to marshal a Client event subscriber interface to a stream for use by other threads, error = %1%",
      0x67u);
    v11 = AppV::Log::fmt(v10, &v40, &v32);
    v12 = AppV::LogFormatter::operator%<long>(v11, (__int64)&v28);
    v35 = 0;
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v35, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v38, 8, (int)&v35, v12);
    std::wstring::~wstring((char **)&v35);
    v40 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v41);
    std::wstring::~wstring((char **)&v32);
    std::string::~string(v38);
    v13 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v13 )
      v14 = v13 + 1;
    else
      v14 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v14);
    v8 = (unsigned int)v28 | (FileId << 52) | 0x522E00000000LL;
    if ( ppstm )
      ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    return v8;
  }
  v28 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
  if ( v28 < 0 )
  {
    v16 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v16 )
      v17 = v16 + 1;
    else
      v17 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    v8 = (unsigned int)v28
       | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v17) << 52)
       | 0x532E00000000LL;
    if ( ppstm )
      ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    return v8;
  }
  v18 = operator new(0x60u);
  v19 = (int)v18;
  v30[0] = v18;
  v20 = *(_QWORD *)(a2 + 8);
  v21 = ppstm;
  v22 = *(_QWORD *)(a1 + 104);
  if ( v22 )
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
  v31[0] = *(_QWORD *)(a1 + 96);
  v31[1] = *(_QWORD *)(a1 + 104);
  v23 = *(_QWORD *)(a1 + 88);
  if ( v23 )
    _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
  v32 = *(_OWORD *)(a1 + 80);
  v24 = *(_QWORD *)(a1 + 72);
  if ( v24 )
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
  v35 = *(_OWORD *)(a1 + 64);
  v25 = *(_QWORD *)(a1 + 56);
  if ( v25 )
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
  v30[0] = *(_QWORD *)(a1 + 48);
  v30[1] = *(_QWORD *)(a1 + 56);
  v26 = AppV::Client::Host::EnterpriseSubscriberImpl::EnterpriseWorkerStartupData::EnterpriseWorkerStartupData(
          v19,
          (unsigned int)v30,
          (unsigned int)&v35,
          (unsigned int)&v32,
          (__int64)v31,
          (__int64)v21,
          v20);
  v27 = (void (__fastcall ***)(_QWORD, __int64))*a3;
  *a3 = v26;
  if ( v27 )
    (**v27)(v27, 1);
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14004e860  mov     [rsp-8+arg_18], rbx
0x14004e865  push    rbp
0x14004e866  push    rsi
0x14004e867  push    rdi
0x14004e868  lea     rbp, [rsp-10h]
0x14004e86d  sub     rsp, 110h
0x14004e874  mov     rax, cs:__security_cookie
0x14004e87b  xor     rax, rsp
0x14004e87e  mov     [rbp+20h+var_18], rax
0x14004e882  mov     rsi, r8
0x14004e885  mov     rdi, rdx
0x14004e888  mov     rbx, rcx
0x14004e88b  mov     [rsp+120h+ppstm], 0
0x14004e894  lea     r8, [rsp+120h+ppstm]; ppstm
0x14004e899  mov     edx, 1; fDeleteOnRelease
0x14004e89e  xor     ecx, ecx; hGlobal
0x14004e8a0  call    cs:__imp_CreateStreamOnHGlobal
0x14004e8a6  mov     [rsp+120h+var_E0], eax
0x14004e8aa  test    eax, eax
0x14004e8ac  jns     short loc_14004E91A
0x14004e8ae  mov     edx, 5Ch ; '\'; Ch
0x14004e8b3  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004e8ba  call    cs:__imp_strrchr
0x14004e8c0  test    rax, rax
0x14004e8c3  jz      short loc_14004E8CA
0x14004e8c5  inc     rax
0x14004e8c8  jmp     short loc_14004E8D1
0x14004e8ca  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004e8d1  mov     rdx, rax; char *
0x14004e8d4  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004e8db  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004e8e0  mov     rbx, rax
0x14004e8e3  shl     rbx, 34h
0x14004e8e7  mov     ecx, [rsp+120h+var_E0]
0x14004e8eb  or      rbx, rcx
0x14004e8ee  mov     rax, 512E00000000h
0x14004e8f8  or      rbx, rax
0x14004e8fb  mov     rcx, [rsp+120h+ppstm]
0x14004e900  test    rcx, rcx
0x14004e903  jz      short loc_14004E912
0x14004e905  mov     rax, [rcx]
0x14004e908  mov     rax, [rax+10h]
0x14004e90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e911  nop
0x14004e912  mov     rax, rbx
0x14004e915  jmp     loc_14004EC23
0x14004e91a  mov     [rsp+120h+mshlflags], 0; mshlflags
0x14004e922  mov     [rsp+120h+pvDestContext], 0; pvDestContext
0x14004e92b  mov     r9d, 3; dwDestContext
0x14004e931  mov     r8, [rdi]; pUnk
0x14004e934  lea     rdx, _GUID_57bb7098_daee_48c6_8c1a_ea12cd2db64e; riid
0x14004e93b  mov     rcx, [rsp+120h+ppstm]; pStm
0x14004e940  call    cs:__imp_CoMarshalInterface
0x14004e946  mov     [rsp+120h+var_E0], eax
0x14004e94a  test    eax, eax
0x14004e94c  jns     loc_14004EA9D
0x14004e952  lea     rdx, aAppvClientHost; "AppV::Client::Host::EnterpriseSubscribe"...
0x14004e959  lea     rcx, [rbp+20h+var_70]
0x14004e95d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004e962  mov     [rbp+20h+var_50], 296h
0x14004e969  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004e96e  xorps   xmm0, xmm0
0x14004e971  movups  [rsp+120h+var_B0], xmm0
0x14004e976  mov     [rbp+20h+var_A0], 0
0x14004e97e  mov     [rbp+20h+var_98], 0
0x14004e986  mov     r8d, 67h ; 'g'
0x14004e98c  lea     rdx, aFailedToMarsha; "Failed to marshal a Client event subscr"...
0x14004e993  lea     rcx, [rsp+120h+var_B0]
0x14004e998  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004e99d  nop
0x14004e99e  lea     r8, [rsp+120h+var_B0]
0x14004e9a3  lea     rdx, [rbp+20h+var_48]
0x14004e9a7  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004e9ac  nop
0x14004e9ad  lea     rdx, [rsp+120h+var_E0]
0x14004e9b2  mov     rcx, rax
0x14004e9b5  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14004e9ba  mov     rbx, rax
0x14004e9bd  xorps   xmm0, xmm0
0x14004e9c0  movups  [rbp+20h+var_90], xmm0
0x14004e9c4  mov     [rbp+20h+var_80], 0
0x14004e9cc  mov     [rbp+20h+var_78], 0
0x14004e9d4  mov     r8d, 6
0x14004e9da  lea     rdx, aClient; "Client"
0x14004e9e1  lea     rcx, [rbp+20h+var_90]
0x14004e9e5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004e9ea  nop
0x14004e9eb  mov     r9, rbx
0x14004e9ee  lea     r8, [rbp+20h+var_90]
0x14004e9f2  mov     edx, 8
0x14004e9f7  lea     rcx, [rbp+20h+var_70]
0x14004e9fb  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004ea00  nop
0x14004ea01  lea     rcx, [rbp+20h+var_90]
0x14004ea05  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ea0a  nop
0x14004ea0b  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004ea12  mov     [rbp+20h+var_48], rax
0x14004ea16  lea     rcx, [rbp+20h+var_38]
0x14004ea1a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ea1f  nop
0x14004ea20  lea     rcx, [rsp+120h+var_B0]
0x14004ea25  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ea2a  nop
0x14004ea2b  lea     rcx, [rbp+20h+var_70]
0x14004ea2f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004ea34  mov     edx, 5Ch ; '\'; Ch
0x14004ea39  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004ea40  call    cs:__imp_strrchr
0x14004ea46  test    rax, rax
0x14004ea49  jz      short loc_14004EA50
0x14004ea4b  inc     rax
0x14004ea4e  jmp     short loc_14004EA57
0x14004ea50  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004ea57  mov     rdx, rax; char *
0x14004ea5a  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004ea61  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004ea66  mov     rbx, rax
0x14004ea69  shl     rbx, 34h
0x14004ea6d  mov     ecx, [rsp+120h+var_E0]
0x14004ea71  or      rbx, rcx
0x14004ea74  mov     rax, 522E00000000h
0x14004ea7e  or      rbx, rax
0x14004ea81  mov     rcx, [rsp+120h+ppstm]
0x14004ea86  test    rcx, rcx
0x14004ea89  jz      short loc_14004EA98
0x14004ea8b  mov     rax, [rcx]
0x14004ea8e  mov     rax, [rax+10h]
0x14004ea92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ea97  nop
0x14004ea98  jmp     loc_14004E912
0x14004ea9d  mov     rcx, [rsp+120h+ppstm]
0x14004eaa2  xor     edx, edx
0x14004eaa4  mov     rax, [rcx]
0x14004eaa7  xor     r9d, r9d
0x14004eaaa  xor     r8d, r8d
0x14004eaad  mov     rax, [rax+28h]
0x14004eab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eab6  mov     [rsp+120h+var_E0], eax
0x14004eaba  test    eax, eax
0x14004eabc  jns     short loc_14004EB27
0x14004eabe  mov     edx, 5Ch ; '\'; Ch
0x14004eac3  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004eaca  call    cs:__imp_strrchr
0x14004ead0  test    rax, rax
0x14004ead3  jz      short loc_14004EADA
0x14004ead5  inc     rax
0x14004ead8  jmp     short loc_14004EAE1
0x14004eada  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004eae1  mov     rdx, rax; char *
0x14004eae4  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004eaeb  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004eaf0  mov     rbx, rax
0x14004eaf3  shl     rbx, 34h
0x14004eaf7  mov     ecx, [rsp+120h+var_E0]
0x14004eafb  or      rbx, rcx
0x14004eafe  mov     rax, 532E00000000h
0x14004eb08  or      rbx, rax
0x14004eb0b  mov     rcx, [rsp+120h+ppstm]
0x14004eb10  test    rcx, rcx
0x14004eb13  jz      short loc_14004EB22
0x14004eb15  mov     rax, [rcx]
0x14004eb18  mov     rax, [rax+10h]
0x14004eb1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eb21  nop
0x14004eb22  jmp     loc_14004E912
0x14004eb27  mov     ecx, 60h ; '`'; Size
0x14004eb2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004eb31  mov     r10, rax
0x14004eb34  mov     [rsp+120h+var_D0], rax
0x14004eb39  mov     rdx, [rdi+8]
0x14004eb3d  mov     r8, [rsp+120h+ppstm]
0x14004eb42  mov     rcx, [rbx+68h]
0x14004eb46  test    rcx, rcx
0x14004eb49  jz      short loc_14004EB4F
0x14004eb4b  lock inc dword ptr [rcx+8]
0x14004eb4f  mov     rax, [rbx+60h]
0x14004eb53  mov     [rsp+120h+var_C0], rax
0x14004eb58  mov     rax, [rbx+68h]
0x14004eb5c  mov     [rsp+120h+var_B8], rax
0x14004eb61  mov     rax, [rbx+58h]
0x14004eb65  test    rax, rax
0x14004eb68  jz      short loc_14004EB6E
0x14004eb6a  lock inc dword ptr [rax+8]
0x14004eb6e  mov     rax, [rbx+50h]
0x14004eb72  mov     qword ptr [rsp+120h+var_B0], rax
0x14004eb77  mov     rax, [rbx+58h]
0x14004eb7b  mov     qword ptr [rsp+120h+var_B0+8], rax
0x14004eb80  mov     rax, [rbx+48h]
0x14004eb84  test    rax, rax
0x14004eb87  jz      short loc_14004EB8D
0x14004eb89  lock inc dword ptr [rax+8]
0x14004eb8d  mov     rax, [rbx+40h]
0x14004eb91  mov     qword ptr [rbp+20h+var_90], rax
0x14004eb95  mov     rax, [rbx+48h]
0x14004eb99  mov     qword ptr [rbp+20h+var_90+8], rax
0x14004eb9d  mov     rax, [rbx+38h]
0x14004eba1  test    rax, rax
0x14004eba4  jz      short loc_14004EBAA
0x14004eba6  lock inc dword ptr [rax+8]
0x14004ebaa  mov     rax, [rbx+30h]
0x14004ebae  mov     [rsp+120h+var_D0], rax
0x14004ebb3  mov     rax, [rbx+38h]
0x14004ebb7  mov     [rsp+120h+var_C8], rax
0x14004ebbc  mov     [rsp+120h+var_F0], rdx
0x14004ebc1  mov     qword ptr [rsp+120h+mshlflags], r8
0x14004ebc6  lea     rax, [rsp+120h+var_C0]
0x14004ebcb  mov     [rsp+120h+pvDestContext], rax
0x14004ebd0  lea     r9, [rsp+120h+var_B0]
0x14004ebd5  lea     r8, [rbp+20h+var_90]
0x14004ebd9  lea     rdx, [rsp+120h+var_D0]
0x14004ebde  mov     rcx, r10
0x14004ebe1  call    ??0EnterpriseWorkerStartupData@EnterpriseSubscriberImpl@Host@Client@AppV@@QEAA@V?$shared_ptr@Vcritical_section@shared@softricity@@@std@@V?$shared_ptr@Vevent@shared@softricity@@@6@V?$shared_ptr@V?$deque@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@2@@std@@@6@1PEAUIStream@@PEAX@Z; AppV::Client::Host::EnterpriseSubscriberImpl::EnterpriseWorkerStartupData::EnterpriseWorkerStartupData(std::shared_ptr<softricity::shared::critical_section>,std::shared_ptr<softricity::shared::event>,std::shared_ptr<std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>>,std::shared_ptr<softricity::shared::event>,IStream *,void *)
0x14004ebe6  mov     rcx, [rsi]
0x14004ebe9  mov     [rsi], rax
0x14004ebec  test    rcx, rcx
0x14004ebef  jz      short loc_14004EC02
0x14004ebf1  mov     rax, [rcx]
0x14004ebf4  mov     edx, 1
0x14004ebf9  mov     rax, [rax]
0x14004ebfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ec01  nop
0x14004ec02  mov     rcx, [rsp+120h+ppstm]
0x14004ec07  test    rcx, rcx
0x14004ec0a  jz      short loc_14004EC19
0x14004ec0c  mov     rax, [rcx]
0x14004ec0f  mov     rax, [rax+10h]
0x14004ec13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ec18  nop
0x14004ec19  mov     rax, 8000000000h
0x14004ec23  mov     rcx, [rbp+20h+var_18]
0x14004ec27  xor     rcx, rsp; StackCookie
0x14004ec2a  call    __security_check_cookie
0x14004ec2f  mov     rbx, [rsp+120h+arg_18]
0x14004ec37  add     rsp, 110h
0x14004ec3e  pop     rdi
0x14004ec3f  pop     rsi
0x14004ec40  pop     rbp
0x14004ec41  retn
```
