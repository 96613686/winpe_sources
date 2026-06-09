# Roaming::RoamingProxy::InitWithOptics(Mso::Authentication::IOfficeIdentity *,Mso::MemoryPtr<wchar_t,0> &,ulong &,Mso::StringLiterals::StringLiteral<char> const &,Mso::TCntPtr<Storage::TelemetryAccumulator> const &)

- ea: `0x18009a4e0`
- end: `0x18009ac64`
- name: `?InitWithOptics@RoamingProxy@Roaming@@QEAAJPEAUIOfficeIdentity@Authentication@Mso@@AEAV?$MemoryPtr@_W$0A@@5@AEAKAEBV?$StringLiteral@D@StringLiterals@5@AEBV?$TCntPtr@VTelemetryAccumulator@Storage@@@5@@Z`
- size: `1924`
- prototype: `__int64 __usercall@<rax>(WS_ERROR **error@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009ad08`
- `0x1801fc5c0`
- `0x1802f5524`

## callees

- `0x18003a8d0`
- `0x18003b080`
- `0x18003b330`
- `0x18003b498`
- `0x180099c84`
- `0x18009a4e0`
- `0x18009ac64`
- `0x1800a8784`
- `0x1801907f4`
- `0x1801924d8`
- `0x180192520`
- `0x180192560`
- `0x1801fe4fc`
- `0x1801fe5a0`
- `0x1801fe614`
- `0x1801fe968`
- `0x1801fea88`
- `0x1803cbb48`

## import_xrefs

- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x18009a651`
- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x18009a651`
- `Mso20Win32Client!__imp_?Set@TelemetryAccumulator@Storage@@QEAAXPEBD_J@Z` at `0x18009ac2f`
- `Mso20Win32Client!__imp_?Set@TelemetryAccumulator@Storage@@QEAAXPEBD_J@Z` at `0x18009ac58`
- `Mso20Win32Client!__imp_?Set@TelemetryAccumulator@Storage@@QEAAXPEBD_J@Z` at `0x18009ac2f`
- `Mso20Win32Client!__imp_?Set@TelemetryAccumulator@Storage@@QEAAXPEBD_J@Z` at `0x18009ac58`
- `Mso20Win32Client!__imp_?Set@TelemetryAccumulator@Storage@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x18009a664`
- `Mso20Win32Client!__imp_?Set@TelemetryAccumulator@Storage@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x18009a664`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x18009a7c1`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x18009a868`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x18009a7c1`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x18009a868`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x18009a560`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x18009a560`
- `Mso20Win32Client!__imp_?Create@OGuid@@YA?AU_GUID@@XZ` at `0x18009a628`
- `Mso20Win32Client!__imp_?Create@OGuid@@YA?AU_GUID@@XZ` at `0x18009a628`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18009a6c9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18009a6c9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18009a7b6`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18009a85c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18009a9cd`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18009a7b6`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18009a85c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18009a9cd`
- `MSVCP140!_Mtx_unlock` at `0x18009a78b`
- `MSVCP140!_Mtx_unlock` at `0x18009a78b`
- `webservices!WsOpenServiceProxy` at `0x18009a79f`
- `webservices!WsOpenServiceProxy` at `0x18009a79f`
- `webservices!WsCreateServiceProxyFromTemplate` at `0x18009a74a`
- `webservices!WsCreateServiceProxyFromTemplate` at `0x18009a74a`
- `webservices!WsCreateHeap` at `0x18009a6b4`
- `webservices!WsCreateHeap` at `0x18009a6b4`
- `webservices!WsCreateError` at `0x18009a683`
- `webservices!WsCreateError` at `0x18009a683`

## string_xrefs

- `0x18009a8a4`: `failed to get service url`
- `0x18009ab1e`: `failed to get token for identity`
- `0x18009ac4e`: `ConfigServiceStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Roaming::RoamingProxy::InitWithOptics(
        WS_ERROR **error,
        WS_ERROR *a2,
        Mso::Memory *a3,
        _DWORD *a4,
        __int64 a5,
        WS_ERROR **a6)
{
  const char *v8; // rcx
  unsigned int v9; // edi
  __int64 v10; // r8
  WS_ERROR *v11; // rbx
  _DWORD *v12; // rbx
  Mso::Memory *v13; // r12
  struct _GUID *v14; // rdx
  int v15; // r9d
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rax
  HRESULT Heap; // ebx
  int v20; // r9d
  unsigned int v21; // r8d
  Mso::Memory *v22; // rax
  Mso::Memory *v23; // r15
  WS_ERROR **v24; // r13
  int v25; // r9d
  std::_Mutex_base *v26; // rbx
  __int64 v27; // rax
  void *v28; // rdx
  int v29; // r9d
  int v31; // edi
  int v32; // r9d
  void *v33; // rdx
  void *v34; // rdx
  int v35; // edi
  char CurrentUserIdentity; // al
  __int64 v37; // rdx
  unsigned int v38; // eax
  __int64 v39; // rax
  int v40; // edx
  int v41; // r8d
  int v42; // r9d
  Storage::TelemetryAccumulator *v43; // rbx
  unsigned int *v44; // rax
  Storage::TelemetryAccumulator *v45; // rbx
  __int64 v46; // rax
  const char *v47; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h]
  char v50[8]; // [rsp+68h] [rbp-98h] BYREF
  char v51; // [rsp+70h] [rbp-90h]
  Mso::Memory *v52; // [rsp+78h] [rbp-88h]
  _OWORD templateValue[3]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h]
  WS_ENDPOINT_ADDRESS address; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v56[48]; // [rsp+E0h] [rbp-20h] BYREF
  void **v57; // [rsp+110h] [rbp+10h] BYREF
  const char *v58; // [rsp+118h] [rbp+18h]
  const wchar_t *v59; // [rsp+120h] [rbp+20h]
  __int16 v60; // [rsp+128h] [rbp+28h]
  __int128 v61; // [rsp+130h] [rbp+30h] BYREF
  __m128i si128; // [rsp+140h] [rbp+40h]
  __int128 v63; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v64[2]; // [rsp+160h] [rbp+60h] BYREF
  char v65[32]; // [rsp+180h] [rbp+80h] BYREF

  v48 = a4;
  v52 = a3;
  v49 = a5;
  v8 = *(const char **)std::chrono::steady_clock::now(&v47);
  v9 = 0;
  v57 = 0;
  v58 = v8;
  v59 = (const wchar_t *)v8;
  LOBYTE(v60) = 1;
  LOBYTE(v10) = 1;
  Measurements::MeasureElapsedTime::MeasureElapsedTime(
    v56,
    Measurements::MeasurementId::FetchIdentityServiceTicket,
    v10,
    &v57);
  v47 = "RoamingProxy::Init";
  if ( *((_BYTE *)error + 149) )
  {
    *((_BYTE *)error + 24) = 1;
    goto LABEL_22;
  }
  error[19] = a2;
  v11 = *a6;
  if ( error[20] != *a6 )
  {
    if ( v11 )
      (**(void (__fastcall ***)(WS_ERROR *))v11)(*a6);
    Mso::TCntPtr<Mso::OfficeWebServiceApi::IAuthTicket>::Clear(error + 20);
    error[20] = v11;
  }
  memset(&address.headers, 0, 24);
  memset(templateValue, 0, sizeof(templateValue));
  v54 = 0;
  v12 = v48;
  v13 = v52;
  Roaming::RoamingProxy::GetServerUrlWithErrorInfo(v50, a2, v52, v48);
  if ( v51 || *v12 <= 1u )
  {
    v58 = "Message";
    v59 = L"failed to get service url";
    v60 = 4;
    v61 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v61) = 0;
    v57 = &Mso::Authentication::Logging::Structured::Email::`vftable';
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
      6029667,
      226,
      50,
      v15,
      (__int64)&v47,
      (__int64)&v57);
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v61);
    if ( *a6 && v51 )
    {
      v43 = (Storage::TelemetryAccumulator *)Mso::TCntPtr<Csi::IWopiContainerMetadata>::operator->(a6);
      v44 = (unsigned int *)std::optional<_FILETIME>::operator->(v50);
      Storage::TelemetryAccumulator::Set(v43, "SubStatusTag", *v44);
      v45 = (Storage::TelemetryAccumulator *)Mso::TCntPtr<Csi::IWopiContainerMetadata>::operator->(a6);
      v46 = std::optional<_FILETIME>::operator->(v50);
      Storage::TelemetryAccumulator::Set(v45, "ConfigServiceStatus", *(unsigned int *)(v46 + 4));
    }
    Heap = -2143485920;
    Roaming::LoggingOptics(a5, (_DWORD)a6, -2143485920, 1022, 6029667);
    goto LABEL_18;
  }
  *(_QWORD *)&v64[0] = (unsigned int)(*v12 - 1);
  *((_QWORD *)&v64[0] + 1) = *(_QWORD *)v13;
  address.url = (WS_STRING)v64[0];
  v63 = (__int128)*OGuid::Create((OGuid *)v64, v14);
  if ( *a6 )
  {
    v16 = Mso::TCntPtr<Csi::IWopiContainerMetadata>::operator->(a6);
    LOBYTE(v17) = 1;
    v18 = OGuid::ToString(v64, &v63, v17);
    Storage::TelemetryAccumulator::Set(v16, "CorrelationId", v18);
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v64);
  }
  if ( a2 )
  {
    CurrentUserIdentity = Roaming::RoamingProxy::GetCurrentUserIdentity(error + 4, a2, &v63);
    v37 = *(_QWORD *)a2;
    if ( !CurrentUserIdentity )
    {
      v58 = "Message";
      v59 = L"failed to get token for identity";
      v60 = 4;
      v61 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v61) = 0;
      v57 = &Mso::Authentication::Logging::Structured::Email::`vftable';
      v38 = (*(__int64 (__fastcall **)(WS_ERROR *))(v37 + 40))(a2);
      v39 = Mso::Authentication::Logging::Structured::IdentityProvider::IdentityProvider(v64, v38);
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Authentication::Logging::Structured::IdentityProvider,Mso::Authentication::Logging::Structured::Message>(
        6029696,
        v40,
        v41,
        v42,
        (__int64)&v47,
        v39,
        (__int64)&v57);
      Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v65);
      Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v61);
      v9 = -2144337661;
      Roaming::LoggingOptics(a5, (_DWORD)a6, -2144337661, 1023, 6029696);
      goto LABEL_22;
    }
    *((_DWORD *)error + 16) = (*(__int64 (__fastcall **)(WS_ERROR *))(v37 + 40))(a2);
  }
  Heap = WsCreateError(0, 0, error);
  if ( Heap < 0 )
  {
    v61 = 0;
    LOWORD(v61) = 0;
    v35 = 1651336;
  }
  else
  {
    Heap = WsCreateHeap(0x500000u, 0x200u, 0, 0, error + 1, *error);
    if ( Heap >= 0 )
    {
      v22 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v21);
      v23 = v22;
      if ( !v22 )
      {
        v9 = -2147024882;
        Roaming::LoggingOptics(a5, (_DWORD)a6, -2147024882, 1021, 508379285);
        goto LABEL_22;
      }
      v52 = v22;
      LODWORD(v48) = 0x800000;
      *(_DWORD *)v22 = 0;
      *((_QWORD *)v22 + 1) = &v48;
      *((_DWORD *)v22 + 4) = 4;
      *(_QWORD *)&templateValue[0] = v22;
      DWORD2(templateValue[0]) = 1;
      v24 = error + 2;
      Heap = WsCreateServiceProxyFromTemplate(
               WS_CHANNEL_TYPE_REQUEST,
               0,
               0,
               WS_HTTP_SSL_BINDING_TEMPLATE_TYPE,
               templateValue,
               0x38u,
               &off_180BD6F10,
               0x30u,
               error + 2,
               *error);
      if ( Heap < 0 )
      {
        v58 = "Message";
        v59 = L"Not reached";
        v60 = 4;
        v61 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v61) = 0;
        v57 = &Mso::Authentication::Logging::Structured::Email::`vftable';
        v31 = 1651338;
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
          1651338,
          226,
          10,
          v25,
          (__int64)&v47,
          (__int64)&v57);
        Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v61);
        v32 = 1025;
      }
      else
      {
        if ( !*v24 )
        {
          v58 = "Message";
          v59 = L"Not reached";
          v60 = 4;
          v61 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v61) = 0;
          v57 = &Mso::Authentication::Logging::Structured::Email::`vftable';
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
            1651340,
            226,
            10,
            v25,
            (__int64)&v47,
            (__int64)&v57);
          Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v61);
          v9 = -2147467259;
          Roaming::LoggingOptics(v49, (_DWORD)a6, -2147467259, 1021, 1651340);
          Mso::Memory::Free(v23, v34);
          goto LABEL_22;
        }
        v26 = (std::_Mutex_base *)sub_1801FE5A0();
        *(_QWORD *)&v64[0] = v26;
        std::_Mutex_base::lock(v26);
        v27 = sub_1801FE614();
        std::_Tree<std::_Tset_traits<_WS_SERVICE_PROXY *,std::less<_WS_SERVICE_PROXY *>,std::allocator<_WS_SERVICE_PROXY *>,0>>::_Emplace<_WS_SERVICE_PROXY * const &>(
          v27,
          &v57,
          error + 2);
        _Mtx_unlock(v26);
        Heap = WsOpenServiceProxy(*v24, &address, 0, *error);
        if ( Heap >= 0 )
        {
          *((_BYTE *)error + 24) = 1;
          Mso::Memory::Free(v23, v28);
LABEL_18:
          Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v56);
          return (unsigned int)Heap;
        }
        v58 = "Message";
        v59 = L"Not reached";
        v60 = 4;
        v61 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v61) = 0;
        v57 = &Mso::Authentication::Logging::Structured::Email::`vftable';
        v31 = 1651339;
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
          1651339,
          226,
          10,
          v29,
          (__int64)&v47,
          (__int64)&v57);
        Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v61);
        v32 = 1026;
      }
      Roaming::LoggingOptics(v49, (_DWORD)a6, Heap, v32, v31);
      Mso::Memory::Free(v23, v33);
      goto LABEL_21;
    }
    v61 = 0;
    LOWORD(v61) = 0;
    v35 = 1651337;
  }
  v58 = "Message";
  v57 = &Mso::Authentication::Logging::Structured::Email::`vftable';
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v60 = 4;
  v59 = L"Not reached";
  Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
    v35,
    226,
    10,
    v20,
    (__int64)&v47,
    (__int64)&v57);
  Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v61);
  Roaming::LoggingOptics(a5, (_DWORD)a6, Heap, 1021, v35);
LABEL_21:
  v9 = Heap;
LABEL_22:
  Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v56);
  return v9;
}

```

## disassembly

```asm
0x18009a4e0  push    rbp
0x18009a4e2  push    rbx
0x18009a4e3  push    rsi
0x18009a4e4  push    rdi
0x18009a4e5  push    r12
0x18009a4e7  push    r13
0x18009a4e9  push    r14
0x18009a4eb  push    r15
0x18009a4ed  lea     rbp, [rsp-0B8h]
0x18009a4f5  sub     rsp, 1B8h
0x18009a4fc  mov     rax, cs:__security_cookie
0x18009a503  xor     rax, rsp
0x18009a506  mov     [rbp+0F0h+var_50], rax
0x18009a50d  mov     [rsp+1F0h+var_198], r9
0x18009a512  mov     [rsp+1F0h+var_178], r8
0x18009a517  mov     r15, rdx
0x18009a51a  mov     rsi, rcx
0x18009a51d  mov     r14, [rbp+0F0h+arg_28]
0x18009a524  mov     r13, [rbp+0F0h+arg_20]
0x18009a52b  mov     [rsp+1F0h+var_190], r13
0x18009a530  lea     rcx, [rsp+1F0h+var_1A0]
0x18009a535  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18009a53a  mov     rcx, [rax]
0x18009a53d  xor     edi, edi
0x18009a53f  mov     [rbp+0F0h+var_E0], rdi
0x18009a543  mov     [rbp+0F0h+var_D8], rcx
0x18009a547  mov     [rbp+0F0h+var_D0], rcx
0x18009a54b  mov     byte ptr [rbp+0F0h+var_C8], 1
0x18009a54f  lea     r9, [rbp+0F0h+var_E0]
0x18009a553  mov     r8b, 1
0x18009a556  mov     edx, cs:?FetchIdentityServiceTicket@MeasurementId@Measurements@@3UMeasurementIdType@2@B; Measurements::MeasurementIdType const Measurements::MeasurementId::FetchIdentityServiceTicket
0x18009a55c  lea     rcx, [rbp+0F0h+var_110]
0x18009a560  call    cs:__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z; Measurements::MeasureElapsedTime::MeasureElapsedTime(Measurements::MeasurementIdType,bool,Measurements::Stopwatch &&)
0x18009a566  lea     rax, aRoamingproxyIn; "RoamingProxy::Init"
0x18009a56d  mov     [rsp+1F0h+var_1A0], rax
0x18009a572  cmp     [rsi+95h], dil
0x18009a579  jnz     loc_18009A893
0x18009a57f  nop
0x18009a580  mov     [rsi+98h], r15
0x18009a587  lea     r12, [rsi+0A0h]
0x18009a58e  mov     rbx, [r14]
0x18009a591  cmp     [r12], rbx
0x18009a595  jz      short loc_18009A5B7
0x18009a597  test    rbx, rbx
0x18009a59a  jz      short loc_18009A5AB
0x18009a59c  mov     rax, [rbx]
0x18009a59f  mov     rcx, rbx
0x18009a5a2  mov     rax, [rax]
0x18009a5a5  call    cs:__guard_dispatch_icall_fptr
0x18009a5ab  mov     rcx, r12
0x18009a5ae  call    ?Clear@?$TCntPtr@UIAuthTicket@OfficeWebServiceApi@Mso@@@Mso@@QEAAXXZ; Mso::TCntPtr<Mso::OfficeWebServiceApi::IAuthTicket>::Clear(void)
0x18009a5b3  mov     [r12], rbx
0x18009a5b7  xorps   xmm0, xmm0
0x18009a5ba  movdqu  xmmword ptr [rbp+0F0h+address.headers], xmm0
0x18009a5bf  mov     [rbp+0F0h+address.identity], rdi
0x18009a5c3  xorps   xmm1, xmm1
0x18009a5c6  xor     eax, eax
0x18009a5c8  movups  [rbp+0F0h+templateValue], xmm1
0x18009a5cc  movups  [rbp+0F0h+var_160], xmm1
0x18009a5d0  movups  [rbp+0F0h+var_150], xmm1
0x18009a5d4  mov     [rbp+0F0h+var_140], rax
0x18009a5d8  mov     rbx, [rsp+1F0h+var_198]
0x18009a5dd  mov     r9, rbx
0x18009a5e0  mov     r12, [rsp+1F0h+var_178]
0x18009a5e5  mov     r8, r12
0x18009a5e8  mov     rdx, r15
0x18009a5eb  lea     rcx, [rsp+1F0h+var_188]
0x18009a5f0  call    ?GetServerUrlWithErrorInfo@RoamingProxy@Roaming@@SA?AV?$optional@UErrorInfo@Roaming@@@std@@PEBUIOfficeIdentity@Authentication@Mso@@AEAV?$MemoryPtr@_W$0A@@7@AEAK@Z; Roaming::RoamingProxy::GetServerUrlWithErrorInfo(Mso::Authentication::IOfficeIdentity const *,Mso::MemoryPtr<wchar_t,0> &,ulong &)
0x18009a5f5  cmp     [rsp+1F0h+var_180], dil
0x18009a5fa  jnz     loc_18009A899
0x18009a600  mov     eax, [rbx]
0x18009a602  cmp     eax, 1
0x18009a605  jbe     loc_18009A899
0x18009a60b  mov     dword ptr [rbp+0F0h+var_90+4], edi
0x18009a60e  dec     eax
0x18009a610  mov     dword ptr [rbp+0F0h+var_90], eax
0x18009a613  mov     rax, [r12]
0x18009a617  mov     qword ptr [rbp+0F0h+var_90+8], rax
0x18009a61b  movups  xmm0, [rbp+0F0h+var_90]
0x18009a61f  movdqu  xmmword ptr [rbp+0F0h+address.url.length], xmm0
0x18009a624  lea     rcx, [rbp+0F0h+var_90]
0x18009a628  call    cs:__imp_?Create@OGuid@@YA?AU_GUID@@XZ; OGuid::Create(void)
0x18009a62e  movups  xmm0, xmmword ptr [rax]
0x18009a631  movdqu  [rbp+0F0h+var_A0], xmm0
0x18009a636  cmp     [r14], rdi
0x18009a639  jz      short loc_18009A673
0x18009a63b  mov     rcx, r14
0x18009a63e  call    ??C?$TCntPtr@UIWopiContainerMetadata@Csi@@@Mso@@QEBAPEAUIWopiContainerMetadata@Csi@@XZ; Mso::TCntPtr<Csi::IWopiContainerMetadata>::operator->(void)
0x18009a643  mov     rbx, rax
0x18009a646  mov     r8b, 1
0x18009a649  lea     rdx, [rbp+0F0h+var_A0]
0x18009a64d  lea     rcx, [rbp+0F0h+var_90]
0x18009a651  call    cs:__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; OGuid::ToString(_GUID const &,bool)
0x18009a657  mov     r8, rax
0x18009a65a  lea     rdx, aCorrelationid; "CorrelationId"
0x18009a661  mov     rcx, rbx
0x18009a664  call    cs:__imp_?Set@TelemetryAccumulator@Storage@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Storage::TelemetryAccumulator::Set(char const *,std::wstring const &)
0x18009a66a  lea     rcx, [rbp+0F0h+var_90]; void *
0x18009a66e  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x18009a673  test    r15, r15
0x18009a676  jnz     loc_18009AAE7
0x18009a67c  mov     r8, rsi; error
0x18009a67f  xor     edx, edx; propertyCount
0x18009a681  xor     ecx, ecx; properties
0x18009a683  call    cs:__imp_WsCreateError
0x18009a689  mov     ebx, eax
0x18009a68b  test    eax, eax
0x18009a68d  js      loc_18009A9D8
0x18009a693  lea     rcx, [rsi+8]
0x18009a697  mov     rax, [rsi]
0x18009a69a  mov     [rsp+1F0h+error], rax; error
0x18009a69f  mov     [rsp+1F0h+heap], rcx; heap
0x18009a6a4  xor     r9d, r9d; propertyCount
0x18009a6a7  xor     r8d, r8d; properties
0x18009a6aa  mov     edx, 200h; trimSize
0x18009a6af  mov     ecx, 500000h; maxSize
0x18009a6b4  call    cs:__imp_WsCreateHeap
0x18009a6ba  mov     ebx, eax
0x18009a6bc  test    eax, eax
0x18009a6be  js      loc_18009ABED
0x18009a6c4  xor     edx, edx
0x18009a6c6  lea     ecx, [rdx+18h]
0x18009a6c9  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18009a6cf  mov     r15, rax
0x18009a6d2  test    rax, rax
0x18009a6d5  jz      loc_18009ABC7
0x18009a6db  mov     [rsp+1F0h+var_178], rax
0x18009a6e0  mov     dword ptr [rsp+1F0h+var_198], 800000h
0x18009a6e8  mov     [rax], edi
0x18009a6ea  lea     rax, [rsp+1F0h+var_198]
0x18009a6ef  mov     [r15+8], rax
0x18009a6f3  mov     r12d, 4
0x18009a6f9  mov     [r15+10h], r12d
0x18009a6fd  mov     qword ptr [rbp+0F0h+templateValue], r15
0x18009a701  lea     edx, [r12-3]
0x18009a706  mov     dword ptr [rbp+0F0h+templateValue+8], edx
0x18009a709  mov     rcx, [rsi]
0x18009a70c  lea     r13, [rsi+10h]
0x18009a710  mov     [rsp+1F0h+var_1A8], rcx; error
0x18009a715  mov     [rsp+1F0h+serviceProxy], r13; serviceProxy
0x18009a71a  mov     [rsp+1F0h+templateDescriptionSize], 30h ; '0'; templateDescriptionSize
0x18009a722  lea     rax, off_180BD6F10
0x18009a729  mov     [rsp+1F0h+templateDescription], rax; templateDescription
0x18009a72e  mov     dword ptr [rsp+1F0h+error], 38h ; '8'; templateSize
0x18009a736  lea     rax, [rbp+0F0h+templateValue]
0x18009a73a  mov     [rsp+1F0h+heap], rax; templateValue
0x18009a73f  mov     r9d, edx; templateType
0x18009a742  xor     r8d, r8d; propertyCount
0x18009a745  xor     edx, edx; properties
0x18009a747  lea     ecx, [rdx+8]; channelType
0x18009a74a  call    cs:__imp_WsCreateServiceProxyFromTemplate
0x18009a750  mov     ebx, eax
0x18009a752  test    eax, eax
0x18009a754  js      short loc_18009A7CE
0x18009a756  cmp     [r13+0], rdi
0x18009a75a  jz      loc_18009A93A
0x18009a760  call    sub_1801FE5A0
0x18009a765  mov     rbx, rax
0x18009a768  mov     qword ptr [rbp+0F0h+var_90], rax
0x18009a76c  mov     rcx, rax; this
0x18009a76f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18009a774  call    sub_1801FE614
0x18009a779  mov     r8, r13
0x18009a77c  lea     rdx, [rbp+0F0h+var_E0]
0x18009a780  mov     rcx, rax
0x18009a783  call    ??$_Emplace@AEBQEAU_WS_SERVICE_PROXY@@@?$_Tree@V?$_Tset_traits@PEAU_WS_SERVICE_PROXY@@U?$less@PEAU_WS_SERVICE_PROXY@@@std@@V?$allocator@PEAU_WS_SERVICE_PROXY@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@PEAU_WS_SERVICE_PROXY@@PEAX@std@@_N@1@AEBQEAU_WS_SERVICE_PROXY@@@Z; std::_Tree<std::_Tset_traits<_WS_SERVICE_PROXY *,std::less<_WS_SERVICE_PROXY *>,std::allocator<_WS_SERVICE_PROXY *>,0>>::_Emplace<_WS_SERVICE_PROXY * const &>(_WS_SERVICE_PROXY * const &)
0x18009a788  mov     rcx, rbx; _Mtx_t
0x18009a78b  call    cs:__imp__Mtx_unlock
0x18009a791  mov     r9, [rsi]; error
0x18009a794  xor     r8d, r8d; asyncContext
0x18009a797  lea     rdx, [rbp+0F0h+address]; address
0x18009a79b  mov     rcx, [r13+0]; serviceProxy
0x18009a79f  call    cs:__imp_WsOpenServiceProxy
0x18009a7a5  mov     ebx, eax
0x18009a7a7  test    eax, eax
0x18009a7a9  js      loc_18009AA6B
0x18009a7af  mov     byte ptr [rsi+18h], 1
0x18009a7b3  mov     rcx, r15
0x18009a7b6  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18009a7bc  nop
0x18009a7bd  lea     rcx, [rbp+0F0h+var_110]
0x18009a7c1  call    cs:__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ; Measurements::MeasureElapsedTime::~MeasureElapsedTime(void)
0x18009a7c7  mov     eax, ebx
0x18009a7c9  jmp     loc_18009A870
0x18009a7ce  lea     rax, aMessage; "Message"
0x18009a7d5  mov     [rbp+0F0h+var_D8], rax
0x18009a7d9  lea     rcx, aNotReached; "Not reached"
0x18009a7e0  mov     [rbp+0F0h+var_D0], rcx
0x18009a7e4  mov     [rbp+0F0h+var_C8], r12w
0x18009a7e9  xorps   xmm0, xmm0
0x18009a7ec  movups  [rbp+0F0h+var_C0], xmm0
0x18009a7f0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18009a7f8  movdqa  [rbp+0F0h+var_B0], xmm1
0x18009a7fd  mov     word ptr [rbp+0F0h+var_C0], di
0x18009a801  lea     rax, ??_7Email@Structured@Logging@Authentication@Mso@@6B@; const Mso::Authentication::Logging::Structured::Email::`vftable'
0x18009a808  mov     [rbp+0F0h+var_E0], rax
0x18009a80c  lea     rax, [rbp+0F0h+var_E0]
0x18009a810  mov     [rsp+1F0h+error], rax
0x18009a815  lea     rax, [rsp+1F0h+var_1A0]
0x18009a81a  mov     [rsp+1F0h+heap], rax
0x18009a81f  mov     edx, 0E2h
0x18009a824  mov     edi, 19328Ah
0x18009a829  mov     r8d, 0Ah
0x18009a82f  mov     ecx, edi
0x18009a831  call    ??$SendDiagnosticTrace@V?$ToClassifiedStructured@VServiceParams@Authentication@Mso@@@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAV?$ToClassifiedStructured@VServiceParams@Authentication@Mso@@@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams> &&)
0x18009a836  lea     rcx, [rbp+0F0h+var_C0]; void *
0x18009a83a  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x18009a83f  mov     r9d, 401h
0x18009a845  mov     dword ptr [rsp+1F0h+heap], edi
0x18009a849  mov     r8d, ebx
0x18009a84c  mov     rdx, r14
0x18009a84f  mov     rcx, [rsp+1F0h+var_190]
0x18009a854  call    ?LoggingOptics@Roaming@@YAXAEBV?$StringLiteral@D@StringLiterals@Mso@@AEBV?$TCntPtr@VTelemetryAccumulator@Storage@@@4@JHI@Z; Roaming::LoggingOptics(Mso::StringLiterals::StringLiteral<char> const &,Mso::TCntPtr<Storage::TelemetryAccumulator> const &,long,int,uint)
0x18009a859  mov     rcx, r15
0x18009a85c  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18009a862  mov     edi, ebx
0x18009a864  lea     rcx, [rbp+0F0h+var_110]
0x18009a868  call    cs:__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ; Measurements::MeasureElapsedTime::~MeasureElapsedTime(void)
0x18009a86e  mov     eax, edi
0x18009a870  mov     rcx, [rbp+0F0h+var_50]
0x18009a877  xor     rcx, rsp; StackCookie
0x18009a87a  call    __security_check_cookie
0x18009a87f  add     rsp, 1B8h
0x18009a886  pop     r15
0x18009a888  pop     r14
0x18009a88a  pop     r13
0x18009a88c  pop     r12
0x18009a88e  pop     rdi
0x18009a88f  pop     rsi
0x18009a890  pop     rbx
0x18009a891  pop     rbp
0x18009a892  retn
0x18009a893  mov     byte ptr [rsi+18h], 1
0x18009a897  jmp     short loc_18009A864
0x18009a899  lea     rax, aMessage; "Message"
0x18009a8a0  mov     [rbp+0F0h+var_D8], rax
0x18009a8a4  lea     rax, aFailedToGetSer_0; "failed to get service url"
0x18009a8ab  mov     [rbp+0F0h+var_D0], rax
0x18009a8af  mov     r12d, 4
0x18009a8b5  mov     [rbp+0F0h+var_C8], r12w
0x18009a8ba  xorps   xmm0, xmm0
0x18009a8bd  movups  [rbp+0F0h+var_C0], xmm0
0x18009a8c1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18009a8c9  movdqa  [rbp+0F0h+var_B0], xmm1
0x18009a8ce  mov     word ptr [rbp+0F0h+var_C0], di
0x18009a8d2  lea     rax, ??_7Email@Structured@Logging@Authentication@Mso@@6B@; const Mso::Authentication::Logging::Structured::Email::`vftable'
0x18009a8d9  mov     [rbp+0F0h+var_E0], rax
0x18009a8dd  lea     rax, [rbp+0F0h+var_E0]
0x18009a8e1  mov     [rsp+1F0h+error], rax
0x18009a8e6  lea     rax, [rsp+1F0h+var_1A0]
0x18009a8eb  mov     [rsp+1F0h+heap], rax
0x18009a8f0  mov     edx, 0E2h
0x18009a8f5  mov     esi, 5C0163h
0x18009a8fa  lea     r8d, [r12+2Eh]
0x18009a8ff  mov     ecx, esi
0x18009a901  call    ??$SendDiagnosticTrace@V?$ToClassifiedStructured@VServiceParams@Authentication@Mso@@@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAV?$ToClassifiedStructured@VServiceParams@Authentication@Mso@@@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams> &&)
0x18009a906  lea     rcx, [rbp+0F0h+var_C0]; void *
0x18009a90a  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x18009a90f  cmp     [r14], rdi
0x18009a912  jnz     loc_18009AC02
0x18009a918  mov     dword ptr [rsp+1F0h+heap], esi
0x18009a91c  mov     ebx, 803D0020h
0x18009a921  mov     r9d, 3FEh
0x18009a927  mov     r8d, ebx
0x18009a92a  mov     rdx, r14
0x18009a92d  mov     rcx, r13
0x18009a930  call    ?LoggingOptics@Roaming@@YAXAEBV?$StringLiteral@D@StringLiterals@Mso@@AEBV?$TCntPtr@VTelemetryAccumulator@Storage@@@4@JHI@Z; Roaming::LoggingOptics(Mso::StringLiterals::StringLiteral<char> const &,Mso::TCntPtr<Storage::TelemetryAccumulator> const &,long,int,uint)
0x18009a935  jmp     loc_18009A7BD
0x18009a93a  lea     rax, aMessage; "Message"
0x18009a941  mov     [rbp+0F0h+var_D8], rax
0x18009a945  lea     rcx, aNotReached; "Not reached"
0x18009a94c  mov     [rbp+0F0h+var_D0], rcx
0x18009a950  mov     [rbp+0F0h+var_C8], r12w
0x18009a955  xorps   xmm0, xmm0
0x18009a958  movups  [rbp+0F0h+var_C0], xmm0
0x18009a95c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18009a964  movdqa  [rbp+0F0h+var_B0], xmm1
0x18009a969  mov     word ptr [rbp+0F0h+var_C0], di
0x18009a96d  lea     rax, ??_7Email@Structured@Logging@Authentication@Mso@@6B@; const Mso::Authentication::Logging::Structured::Email::`vftable'
0x18009a974  mov     [rbp+0F0h+var_E0], rax
0x18009a978  lea     rax, [rbp+0F0h+var_E0]
0x18009a97c  mov     [rsp+1F0h+error], rax
0x18009a981  lea     rax, [rsp+1F0h+var_1A0]
0x18009a986  mov     [rsp+1F0h+heap], rax
0x18009a98b  mov     edx, 0E2h
0x18009a990  mov     ebx, 19328Ch
0x18009a995  mov     r8d, 0Ah
0x18009a99b  mov     ecx, ebx
0x18009a99d  call    ??$SendDiagnosticTrace@V?$ToClassifiedStructured@VServiceParams@Authentication@Mso@@@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAV?$ToClassifiedStructured@VServiceParams@Authentication@Mso@@@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams> &&)
0x18009a9a2  lea     rcx, [rbp+0F0h+var_C0]; void *
0x18009a9a6  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x18009a9ab  mov     dword ptr [rsp+1F0h+heap], ebx
0x18009a9af  mov     edi, 80004005h
0x18009a9b4  mov     r9d, 3FDh
0x18009a9ba  mov     r8d, edi
0x18009a9bd  mov     rdx, r14
0x18009a9c0  mov     rcx, [rsp+1F0h+var_190]
0x18009a9c5  call    ?LoggingOptics@Roaming@@YAXAEBV?$StringLiteral@D@StringLiterals@Mso@@AEBV?$TCntPtr@VTelemetryAccumulator@Storage@@@4@JHI@Z; Roaming::LoggingOptics(Mso::StringLiterals::StringLiteral<char> const &,Mso::TCntPtr<Storage::TelemetryAccumulator> const &,long,int,uint)
0x18009a9ca  mov     rcx, r15
0x18009a9cd  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
  ... truncated ...
```
