# FileExplorerTelemetry::CommandHandlerInvoke_(EXPLORER_COMMAND_SQM_ID,EXPLORER_COMMAND_SQM_INVOCATION_LOCATION,ulong,int,IShellItem *,IUnknown *,ulong)

- ea: `0x18001399c`
- end: `0x180013d61`
- name: `?CommandHandlerInvoke_@FileExplorerTelemetry@@QEBAXW4EXPLORER_COMMAND_SQM_ID@@W4EXPLORER_COMMAND_SQM_INVOCATION_LOCATION@@KHPEAUIShellItem@@PEAUIUnknown@@K@Z`
- size: `965`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f158`

## callees

- `0x180001b7c`
- `0x180001c48`
- `0x180004a10`
- `0x180005374`
- `0x180005f98`
- `0x180006900`
- `0x1800116bc`
- `0x180012498`
- `0x1800127d0`
- `0x18001296c`
- `0x18001399c`
- `0x180014770`
- `0x180014c0c`
- `0x1800189f8`
- `0x18001db8c`
- `0x1800217a8`
- `0x180021ad4`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d20`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall FileExplorerTelemetry::CommandHandlerInvoke_(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        struct IShellItem *a6,
        struct IUnknown *punk,
        int a8)
{
  unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rdx
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  struct IShellItem *v14; // r8
  FileExplorerTelemetryDesktop *v15; // rcx
  enum _SIGDN v16; // r8d
  __int64 v17; // rcx
  _DWORD *v18; // rbx
  __int64 v19; // r8
  __int64 v20; // r9
  struct IShellItem *v21; // [rsp+E0h] [rbp-80h] BYREF
  int v22; // [rsp+E8h] [rbp-78h] BYREF
  int v23; // [rsp+ECh] [rbp-74h] BYREF
  int v24; // [rsp+F0h] [rbp-70h] BYREF
  int v25; // [rsp+F4h] [rbp-6Ch] BYREF
  int v26; // [rsp+F8h] [rbp-68h] BYREF
  int v27; // [rsp+FCh] [rbp-64h] BYREF
  int v28; // [rsp+100h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+108h] [rbp-58h] BYREF
  unsigned __int16 *v30; // [rsp+110h] [rbp-50h] BYREF
  char v31; // [rsp+118h] [rbp-48h]
  LPVOID v32; // [rsp+120h] [rbp-40h] BYREF
  char v33; // [rsp+128h] [rbp-38h]
  GUID *p_value; // [rsp+130h] [rbp-30h] BYREF
  const wchar_t *v35; // [rsp+138h] [rbp-28h] BYREF
  __int64 v36; // [rsp+140h] [rbp-20h] BYREF
  const wchar_t *v37; // [rsp+148h] [rbp-18h] BYREF
  const wchar_t *v38; // [rsp+150h] [rbp-10h] BYREF
  __int64 v39; // [rsp+158h] [rbp-8h] BYREF
  __int64 v40; // [rsp+160h] [rbp+0h] BYREF
  const wchar_t *v41; // [rsp+168h] [rbp+8h] BYREF
  const wchar_t *v42; // [rsp+170h] [rbp+10h] BYREF
  __int64 v43; // [rsp+178h] [rbp+18h] BYREF
  const wchar_t *v44; // [rsp+180h] [rbp+20h] BYREF
  const wchar_t *v45; // [rsp+188h] [rbp+28h] BYREF
  __int64 v46; // [rsp+190h] [rbp+30h] BYREF
  __int64 v47; // [rsp+198h] [rbp+38h] BYREF
  const wchar_t *v48; // [rsp+1A0h] [rbp+40h] BYREF
  const CHAR *v49; // [rsp+1A8h] [rbp+48h] BYREF
  char v50; // [rsp+1B0h] [rbp+50h]
  _QWORD v51[10]; // [rsp+1C0h] [rbp+60h] BYREF
  int v52; // [rsp+214h] [rbp+B4h]
  _QWORD v53[10]; // [rsp+240h] [rbp+E0h] BYREF
  int v54; // [rsp+294h] [rbp+134h]
  GUID value; // [rsp+2C0h] [rbp+160h] BYREF
  _BYTE v56[336]; // [rsp+2D0h] [rbp+170h] BYREF

  FileExplorerPerf::CommandHandlerInvokePerf::CommandHandlerInvokePerf((FileExplorerPerf::CommandHandlerInvokePerf *)v56);
  v49 = v56;
  v50 = 1;
  PiiSafeShellitemParsingName::PiiSafeShellitemParsingName((PiiSafeShellitemParsingName *)&v32, v11);
  PiiSafeShellitemParsingName::PiiSafeShellitemParsingName((PiiSafeShellitemParsingName *)&v30, v12);
  value = 0;
  TelemetryCorrelationVectorServiceProvider::Increment(&pv, punk);
  if ( pv )
  {
    if ( a6 )
    {
      GetDisplayName = a6->lpVtbl->GetDisplayName;
      v33 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v32,
        0);
      ((void (__fastcall *)(struct IShellItem *, __int64, LPVOID *))GetDisplayName)(a6, 2147647488LL, &v32);
    }
    v14 = 0;
    v21 = 0;
    if ( punk )
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v21);
      v31 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v30,
        0);
      FileExplorerTelemetryDesktop::GetItemAndFolderInViewName(v15, punk, v16, &v30, &v21);
      FileExplorerTelemetryDesktop::GetBrowserSessionId(punk, &value);
      v14 = v21;
    }
    PiiSafeShellitemParsingNameProperties::PiiSafeShellitemParsingNameProperties(
      (PiiSafeShellitemParsingNameProperties *)v53,
      (const struct PiiSafeShellitemParsingName *)&v30,
      v14);
    PiiSafeShellitemParsingNameProperties::PiiSafeShellitemParsingNameProperties(
      (PiiSafeShellitemParsingNameProperties *)v51,
      (const struct PiiSafeShellitemParsingName *)&v32,
      a6);
    v18 = *(_DWORD **)(wil::details::static_lazy<FileExplorerLogging>::get(
                         v17,
                         _lambda_ef118433b3637342f6c5dfe6692936b5_::_lambda_invoker_cdecl_)
                     + 8);
    if ( *v18 > 5u && (unsigned __int8)tlgKeywordOn(v18, 0x400000000000LL) )
    {
      p_value = &value;
      v22 = a8;
      v23 = a4;
      v24 = a5;
      v25 = a3;
      v26 = a2;
      v35 = (const wchar_t *)v51[4];
      v36 = v51[9];
      v37 = (const wchar_t *)v51[3];
      v27 = v52;
      v38 = (const wchar_t *)v51[2];
      v39 = v51[1];
      v40 = v51[0];
      v41 = PiiSafeShellitemParsingName::Get((PiiSafeShellitemParsingName *)&v32);
      v42 = (const wchar_t *)v53[4];
      v43 = v53[9];
      v44 = (const wchar_t *)v53[3];
      v28 = v54;
      v45 = (const wchar_t *)v53[2];
      v46 = v53[1];
      v47 = v53[0];
      v48 = PiiSafeShellitemParsingName::Get((PiiSafeShellitemParsingName *)&v30);
      v49 = (const CHAR *)pv;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (int)v18,
        (int)&byte_18005F2E7,
        v19,
        v20,
        &v49,
        &v48,
        (__int64)&v47,
        (__int64)&v46,
        &v45,
        (__int64)&v28,
        &v44,
        (__int64)&v43,
        &v42,
        &v41,
        (__int64)&v40,
        (__int64)&v39,
        &v38,
        (__int64)&v27,
        &v37,
        (__int64)&v36,
        &v35,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        (__int64 *)&p_value);
    }
    PiiSafeShellitemParsingNameProperties::~PiiSafeShellitemParsingNameProperties((PiiSafeShellitemParsingNameProperties *)v51);
    PiiSafeShellitemParsingNameProperties::~PiiSafeShellitemParsingNameProperties((PiiSafeShellitemParsingNameProperties *)v53);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v21);
    if ( pv )
      CoTaskMemFree(pv);
  }
  if ( v30 )
    CoTaskMemFree(v30);
  if ( v32 )
    CoTaskMemFree(v32);
  wil::ActivityBase<FileExplorerPerf,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v56);
  FileExplorerPerf::CommandHandlerInvokePerf::~CommandHandlerInvokePerf((FileExplorerPerf::CommandHandlerInvokePerf *)v56);
}

```

## disassembly

```asm
0x18001399c  push    rbp
0x18001399e  push    rbx
0x18001399f  push    rsi
0x1800139a0  push    rdi
0x1800139a1  push    r12
0x1800139a3  push    r14
0x1800139a5  push    r15
0x1800139a7  lea     rbp, [rsp-2D0h]
0x1800139af  sub     rsp, 430h
0x1800139b6  mov     rax, cs:__security_cookie
0x1800139bd  xor     rax, rsp
0x1800139c0  mov     [rbp+300h+var_40], rax
0x1800139c7  mov     r14d, r9d
0x1800139ca  mov     r15d, r8d
0x1800139cd  mov     r12d, edx
0x1800139d0  mov     rsi, [rbp+300h+arg_28]
0x1800139d7  mov     rdi, [rbp+300h+punk]
0x1800139de  lea     rcx, [rbp+300h+var_190]; this
0x1800139e5  call    ??$?0$$V@CommandHandlerInvokePerf@FileExplorerPerf@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; FileExplorerPerf::CommandHandlerInvokePerf::CommandHandlerInvokePerf(wistd::integral_constant<char,0>)
0x1800139ea  nop
0x1800139eb  lea     rax, [rbp+300h+var_190]
0x1800139f2  mov     [rbp+300h+var_2B8], rax
0x1800139f6  mov     [rbp+300h+var_2B0], 1
0x1800139fa  lea     rcx, [rbp+300h+var_340]; this
0x1800139fe  call    ??0PiiSafeShellitemParsingName@@QEAA@PEBG@Z; PiiSafeShellitemParsingName::PiiSafeShellitemParsingName(ushort const *)
0x180013a03  nop
0x180013a04  lea     rcx, [rbp+300h+var_350]; this
0x180013a08  call    ??0PiiSafeShellitemParsingName@@QEAA@PEBG@Z; PiiSafeShellitemParsingName::PiiSafeShellitemParsingName(ushort const *)
0x180013a0d  nop
0x180013a0e  xorps   xmm0, xmm0
0x180013a11  movups  xmmword ptr [rbp+300h+value.Data1], xmm0
0x180013a18  mov     rdx, rdi
0x180013a1b  lea     rcx, [rbp+300h+pv]
0x180013a1f  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x180013a24  nop
0x180013a25  cmp     [rbp+300h+pv], 0
0x180013a2a  jnz     short loc_180013A31
0x180013a2c  jmp     loc_180013D07
0x180013a31  test    rsi, rsi
0x180013a34  jz      short loc_180013A60
0x180013a36  mov     rax, [rsi]
0x180013a39  mov     rbx, [rax+28h]
0x180013a3d  mov     [rbp+300h+var_338], 0
0x180013a41  xor     edx, edx
0x180013a43  lea     rcx, [rbp+300h+var_340]
0x180013a47  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013a4c  lea     r8, [rbp+300h+var_340]
0x180013a50  mov     edx, 80028000h
0x180013a55  mov     rcx, rsi
0x180013a58  mov     rax, rbx
0x180013a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a60  xor     r8d, r8d
0x180013a63  mov     [rbp+300h+var_380], r8
0x180013a67  test    rdi, rdi
0x180013a6a  jz      short loc_180013AAC
0x180013a6c  lea     rcx, [rbp+300h+var_380]
0x180013a70  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180013a75  mov     [rbp+300h+var_348], 0
0x180013a79  xor     edx, edx
0x180013a7b  lea     rcx, [rbp+300h+var_350]
0x180013a7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013a84  lea     rax, [rbp+300h+var_380]
0x180013a88  mov     [rsp+460h+var_440], rax; struct IShellItem **
0x180013a8d  lea     r9, [rbp+300h+var_350]; unsigned __int16 **
0x180013a91  mov     rdx, rdi; struct IUnknown *
0x180013a94  call    ?GetItemAndFolderInViewName@FileExplorerTelemetryDesktop@@IEBAJPEAUIUnknown@@W4_SIGDN@@PEAPEAGPEAPEAUIShellItem@@@Z; FileExplorerTelemetryDesktop::GetItemAndFolderInViewName(IUnknown *,_SIGDN,ushort * *,IShellItem * *)
0x180013a99  lea     rdx, [rbp+300h+value]; value
0x180013aa0  mov     rcx, rdi; punk
0x180013aa3  call    ?GetBrowserSessionId@FileExplorerTelemetryDesktop@@SAJPEAUIUnknown@@PEAU_GUID@@@Z; FileExplorerTelemetryDesktop::GetBrowserSessionId(IUnknown *,_GUID *)
0x180013aa8  mov     r8, [rbp+300h+var_380]; struct IShellItem *
0x180013aac  lea     rdx, [rbp+300h+var_350]; struct PiiSafeShellitemParsingName *
0x180013ab0  lea     rcx, [rbp+300h+var_220]; this
0x180013ab7  call    ??0PiiSafeShellitemParsingNameProperties@@QEAA@AEBVPiiSafeShellitemParsingName@@PEAUIShellItem@@@Z; PiiSafeShellitemParsingNameProperties::PiiSafeShellitemParsingNameProperties(PiiSafeShellitemParsingName const &,IShellItem *)
0x180013abc  nop
0x180013abd  mov     r8, rsi; struct IShellItem *
0x180013ac0  lea     rdx, [rbp+300h+var_340]; struct PiiSafeShellitemParsingName *
0x180013ac4  lea     rcx, [rbp+300h+var_2A0]; this
0x180013ac8  call    ??0PiiSafeShellitemParsingNameProperties@@QEAA@AEBVPiiSafeShellitemParsingName@@PEAUIShellItem@@@Z; PiiSafeShellitemParsingNameProperties::PiiSafeShellitemParsingNameProperties(PiiSafeShellitemParsingName const &,IShellItem *)
0x180013acd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ef118433b3637342f6c5dfe6692936b5_@@CA@XZ; _lambda_ef118433b3637342f6c5dfe6692936b5_::_lambda_invoker_cdecl_(void)
0x180013ad4  call    ?get@?$static_lazy@VFileExplorerLogging@@@details@wil@@QEAAPEAVFileExplorerLogging@@P6AXXZ@Z; wil::details::static_lazy<FileExplorerLogging>::get(void (*)(void))
0x180013ad9  mov     rbx, [rax+8]
0x180013add  mov     eax, [rbx]
0x180013adf  cmp     eax, 5
0x180013ae2  jbe     loc_180013CD6
0x180013ae8  mov     rdx, 400000000000h
0x180013af2  mov     rcx, rbx
0x180013af5  call    _tlgKeywordOn
0x180013afa  test    al, al
0x180013afc  jz      loc_180013CD6
0x180013b02  lea     rax, [rbp+300h+value]
0x180013b09  mov     [rbp+300h+var_330], rax
0x180013b0d  mov     eax, [rbp+300h+arg_38]
0x180013b13  mov     [rbp+300h+var_378], eax
0x180013b16  mov     [rbp+300h+var_374], r14d
0x180013b1a  mov     eax, [rbp+300h+arg_20]
0x180013b20  mov     [rbp+300h+var_370], eax
0x180013b23  mov     [rbp+300h+var_36C], r15d
0x180013b27  mov     [rbp+300h+var_368], r12d
0x180013b2b  mov     rax, [rbp+300h+var_280]
0x180013b32  mov     [rbp+300h+var_328], rax
0x180013b36  mov     rax, [rbp+300h+var_258]
0x180013b3d  mov     [rbp+300h+var_320], rax
0x180013b41  mov     rax, [rbp+300h+var_288]
0x180013b45  mov     [rbp+300h+var_318], rax
0x180013b49  mov     eax, [rbp+300h+var_24C]
0x180013b4f  mov     [rbp+300h+var_364], eax
0x180013b52  mov     rax, [rbp+300h+var_290]
0x180013b56  mov     [rbp+300h+var_310], rax
0x180013b5a  mov     rax, [rbp+300h+var_298]
0x180013b5e  mov     [rbp+300h+var_308], rax
0x180013b62  mov     rax, [rbp+300h+var_2A0]
0x180013b66  mov     [rbp+300h+var_300], rax
0x180013b6a  lea     rcx, [rbp+300h+var_340]; this
0x180013b6e  call    ?Get@PiiSafeShellitemParsingName@@QEBAPEBGXZ; PiiSafeShellitemParsingName::Get(void)
0x180013b73  mov     [rbp+300h+var_2F8], rax
0x180013b77  mov     rax, [rbp+300h+var_200]
0x180013b7e  mov     [rbp+300h+var_2F0], rax
0x180013b82  mov     rax, [rbp+300h+var_1D8]
0x180013b89  mov     [rbp+300h+var_2E8], rax
0x180013b8d  mov     rax, [rbp+300h+var_208]
0x180013b94  mov     [rbp+300h+var_2E0], rax
0x180013b98  mov     eax, [rbp+300h+var_1CC]
0x180013b9e  mov     [rbp+300h+var_360], eax
0x180013ba1  mov     rax, [rbp+300h+var_210]
0x180013ba8  mov     [rbp+300h+var_2D8], rax
0x180013bac  mov     rax, [rbp+300h+var_218]
0x180013bb3  mov     [rbp+300h+var_2D0], rax
0x180013bb7  mov     rax, [rbp+300h+var_220]
0x180013bbe  mov     [rbp+300h+var_2C8], rax
0x180013bc2  lea     rcx, [rbp+300h+var_350]; this
0x180013bc6  call    ?Get@PiiSafeShellitemParsingName@@QEBAPEBGXZ; PiiSafeShellitemParsingName::Get(void)
0x180013bcb  mov     [rbp+300h+var_2C0], rax
0x180013bcf  mov     rax, [rbp+300h+pv]
0x180013bd3  mov     [rbp+300h+var_2B8], rax
0x180013bd7  lea     rax, [rbp+300h+var_330]
0x180013bdb  mov     [rsp+460h+var_390], rax
0x180013be3  lea     rax, [rbp+300h+var_378]
0x180013be7  mov     [rsp+460h+var_398], rax
0x180013bef  lea     rax, [rbp+300h+var_374]
0x180013bf3  mov     [rsp+460h+var_3A0], rax
0x180013bfb  lea     rax, [rbp+300h+var_370]
0x180013bff  mov     [rsp+460h+var_3A8], rax
0x180013c07  lea     rax, [rbp+300h+var_36C]
0x180013c0b  mov     [rsp+460h+var_3B0], rax
0x180013c13  lea     rax, [rbp+300h+var_368]
0x180013c17  mov     [rsp+460h+var_3B8], rax
0x180013c1f  lea     rax, [rbp+300h+var_328]
0x180013c23  mov     [rsp+460h+var_3C0], rax
0x180013c2b  lea     rax, [rbp+300h+var_320]
0x180013c2f  mov     [rsp+460h+var_3C8], rax
0x180013c37  lea     rax, [rbp+300h+var_318]
0x180013c3b  mov     [rsp+460h+var_3D0], rax
0x180013c43  lea     rax, [rbp+300h+var_364]
0x180013c47  mov     [rsp+460h+var_3D8], rax
0x180013c4f  lea     rax, [rbp+300h+var_310]
0x180013c53  mov     [rsp+460h+var_3E0], rax
0x180013c5b  lea     rax, [rbp+300h+var_308]
0x180013c5f  mov     [rsp+460h+var_3E8], rax
0x180013c64  lea     rax, [rbp+300h+var_300]
0x180013c68  mov     [rsp+460h+var_3F0], rax
0x180013c6d  lea     rax, [rbp+300h+var_2F8]
0x180013c71  mov     [rsp+460h+var_3F8], rax
0x180013c76  lea     rax, [rbp+300h+var_2F0]
0x180013c7a  mov     [rsp+460h+var_400], rax
0x180013c7f  lea     rax, [rbp+300h+var_2E8]
0x180013c83  mov     [rsp+460h+var_408], rax
0x180013c88  lea     rax, [rbp+300h+var_2E0]
0x180013c8c  mov     [rsp+460h+var_410], rax
0x180013c91  lea     rax, [rbp+300h+var_360]
0x180013c95  mov     [rsp+460h+var_418], rax
0x180013c9a  lea     rax, [rbp+300h+var_2D8]
0x180013c9e  mov     [rsp+460h+var_420], rax
0x180013ca3  lea     rax, [rbp+300h+var_2D0]
0x180013ca7  mov     [rsp+460h+var_428], rax
0x180013cac  lea     rax, [rbp+300h+var_2C8]
0x180013cb0  mov     [rsp+460h+var_430], rax
0x180013cb5  lea     rax, [rbp+300h+var_2C0]
0x180013cb9  mov     [rsp+460h+var_438], rax
0x180013cbe  lea     rax, [rbp+300h+var_2B8]
0x180013cc2  mov     [rsp+460h+var_440], rax
0x180013cc7  lea     rdx, byte_18005F2E7
0x180013cce  mov     rcx, rbx
0x180013cd1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U3@U2@U?$_tlgWrapperByVal@$03@@U2@U3@U2@U2@U3@U3@U2@U4@U2@U3@U2@U4@U4@U4@U4@U4@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@54AEBU?$_tlgWrapperByVal@$03@@4544554645466666AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180013cd6  lea     rcx, [rbp+300h+var_2A0]; this
0x180013cda  call    ??1PiiSafeShellitemParsingNameProperties@@QEAA@XZ; PiiSafeShellitemParsingNameProperties::~PiiSafeShellitemParsingNameProperties(void)
0x180013cdf  nop
0x180013ce0  lea     rcx, [rbp+300h+var_220]; this
0x180013ce7  call    ??1PiiSafeShellitemParsingNameProperties@@QEAA@XZ; PiiSafeShellitemParsingNameProperties::~PiiSafeShellitemParsingNameProperties(void)
0x180013cec  nop
0x180013ced  lea     rcx, [rbp+300h+var_380]
0x180013cf1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180013cf6  nop
0x180013cf7  mov     rcx, [rbp+300h+pv]; pv
0x180013cfb  test    rcx, rcx
0x180013cfe  jz      short loc_180013D07
0x180013d00  call    cs:__imp_CoTaskMemFree
0x180013d06  nop
0x180013d07  mov     rcx, [rbp+300h+var_350]; pv
0x180013d0b  test    rcx, rcx
0x180013d0e  jz      short loc_180013D17
0x180013d10  call    cs:__imp_CoTaskMemFree
0x180013d16  nop
0x180013d17  mov     rcx, [rbp+300h+var_340]; pv
0x180013d1b  test    rcx, rcx
0x180013d1e  jz      short loc_180013D27
0x180013d20  call    cs:__imp_CoTaskMemFree
0x180013d26  nop
0x180013d27  lea     rcx, [rbp+300h+var_190]
0x180013d2e  call    ?Stop@?$ActivityBase@VFileExplorerPerf@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FileExplorerPerf,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180013d33  nop
0x180013d34  lea     rcx, [rbp+300h+var_190]; this
0x180013d3b  call    ??1CommandHandlerInvokePerf@FileExplorerPerf@@QEAA@XZ; FileExplorerPerf::CommandHandlerInvokePerf::~CommandHandlerInvokePerf(void)
0x180013d40  mov     rcx, [rbp+300h+var_40]
0x180013d47  xor     rcx, rsp; StackCookie
0x180013d4a  call    __security_check_cookie
0x180013d4f  add     rsp, 430h
0x180013d56  pop     r15
0x180013d58  pop     r14
0x180013d5a  pop     r12
0x180013d5c  pop     rdi
0x180013d5d  pop     rsi
0x180013d5e  pop     rbx
0x180013d5f  pop     rbp
0x180013d60  retn
```
