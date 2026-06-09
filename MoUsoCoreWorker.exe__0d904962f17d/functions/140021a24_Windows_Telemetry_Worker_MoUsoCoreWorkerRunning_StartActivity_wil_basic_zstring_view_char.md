# Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::StartActivity(wil::basic_zstring_view<char>)

- ea: `0x140021a24`
- end: `0x1400220ad`
- name: `?StartActivity@MoUsoCoreWorkerRunning@Worker@Telemetry@Windows@@QEAAXV?$basic_zstring_view@D@wil@@@Z`
- size: `1673`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x1400230ec`

## callees

- `0x14000185c`
- `0x140001f74`
- `0x140021474`
- `0x140021a24`
- `0x14002a2a0`
- `0x14002cbcc`
- `0x14002cc08`
- `0x140040964`
- `0x140040d18`
- `0x140045404`
- `0x14007258c`
- `0x14012d7d8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140021bb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140021e39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140021fff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140021bb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140021e39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140021fff`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140021aa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140021aa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140021a95`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140021a95`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::StartActivity(__int64 a1, const CHAR **a2)
{
  __int64 v4; // r8
  int v5; // r12d
  const struct _tlgProvider_t *v6; // rax
  int v7; // r13d
  const OLECHAR *v8; // r15
  _QWORD *System; // rax
  _QWORD *v10; // rax
  __int64 v11; // rax
  const OLECHAR *v12; // rdi
  const OLECHAR *v13; // r12
  const CHAR *v14; // r14
  __int64 v15; // r8
  int v16; // r9d
  __int64 v17; // rax
  int v18; // ecx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  volatile signed __int32 *v25; // rdi
  volatile signed __int32 *v26; // rdi
  wil::details::ThreadFailureCallbackHolder *v27; // rcx
  const struct _tlgProvider_t *v28; // rax
  int v29; // r13d
  const OLECHAR *v30; // rdi
  const OLECHAR *v31; // r15
  const CHAR *v32; // r14
  __int64 v33; // r8
  int v34; // r9d
  __int64 v35; // rbx
  __int64 v36; // rax
  int v37; // ecx
  int v38; // eax
  __int64 v39; // rax
  const struct _tlgProvider_t *v40; // rax
  int v41; // ebx
  __int64 v42; // rbx
  const struct _tlgProvider_t *v43; // rdi
  __int64 v44; // [rsp+40h] [rbp-168h] BYREF
  __int64 v45; // [rsp+48h] [rbp-160h] BYREF
  __int64 v46[2]; // [rsp+50h] [rbp-158h] BYREF
  _BYTE v47[8]; // [rsp+60h] [rbp-148h] BYREF
  volatile signed __int32 *v48; // [rsp+68h] [rbp-140h]
  _BYTE v49[8]; // [rsp+70h] [rbp-138h] BYREF
  volatile signed __int32 *v50; // [rsp+78h] [rbp-130h]
  _BYTE v51[32]; // [rsp+80h] [rbp-128h] BYREF
  __int128 v52; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-F8h]
  __int128 v54; // [rsp+B8h] [rbp-F0h] BYREF
  __int64 v55; // [rsp+C8h] [rbp-E0h]
  _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-D8h] BYREF
  struct _SYSTEMTIME v57; // [rsp+E0h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v58; // [rsp+F0h] [rbp-B8h] BYREF
  __int64 *v59; // [rsp+110h] [rbp-98h]
  __int64 v60; // [rsp+118h] [rbp-90h]
  __int64 *v61; // [rsp+120h] [rbp-88h]
  __int64 v62; // [rsp+128h] [rbp-80h]
  const CHAR *v63; // [rsp+130h] [rbp-78h]
  int v64; // [rsp+138h] [rbp-70h]
  int v65; // [rsp+13Ch] [rbp-6Ch]
  const OLECHAR *v66; // [rsp+140h] [rbp-68h]
  int v67; // [rsp+148h] [rbp-60h]
  int v68; // [rsp+14Ch] [rbp-5Ch]
  const OLECHAR *v69; // [rsp+150h] [rbp-58h]
  int v70; // [rsp+158h] [rbp-50h]
  int v71; // [rsp+15Ch] [rbp-4Ch]
  const OLECHAR *v72; // [rsp+160h] [rbp-48h]
  int v73; // [rsp+168h] [rbp-40h]
  int v74; // [rsp+16Ch] [rbp-3Ch]

  v46[0] = a1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Feature_UTCLoggingforUpdateManager_57785634>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Feature_UTCLoggingforUpdateManager_57785634>::GetImpl'::`2'::impl) )
  {
    SystemTime = 0;
    v57 = 0;
    GetSystemTime(&SystemTime);
    GetLocalTime(&v57);
    try
    {
      v54 = 0;
      v55 = 0;
      v5 = 1;
      LOBYTE(v4) = 1;
      Windows::Time::to_iso8601_string(&v54, &SystemTime, v4);
      v52 = 0;
      v53 = 0;
      Windows::Time::to_iso8601_string(&v52, &v57, 0);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
      {
        wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
        v6 = Windows::Telemetry::Base::Provider();
        v7 = (int)v6;
        if ( *(_DWORD *)v6 > 5u
          && (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v6 + 3) & 0x400000000000LL) == *((_QWORD *)v6 + 3) )
        {
          v8 = (const OLECHAR *)v52;
          System = (_QWORD *)SystemInterface::Providers::GetSystem(v49);
          v10 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 40LL))(*System, v47);
          v11 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v10 + 440LL))(*v10, v51);
          v12 = (const OLECHAR *)v11;
          if ( *(_QWORD *)(v11 + 24) > 7u )
            v12 = *(const OLECHAR **)v11;
          v13 = (const OLECHAR *)v54;
          v14 = *a2;
          LODWORD(v44) = GetCurrentThreadId();
          v45 = 0x1000000;
          v15 = *(_QWORD *)(a1 + 272);
          if ( !*(_BYTE *)(v15 + 4)
            || (v16 = v15 + 24, !*(_DWORD *)(v15 + 24))
            && !*(_DWORD *)(v15 + 28)
            && !*(_DWORD *)(v15 + 32)
            && !*(_DWORD *)(v15 + 36) )
          {
            v16 = 0;
          }
          if ( v8 )
          {
            v17 = -1;
            do
              ++v17;
            while ( v8[v17] );
            v18 = 2 * v17 + 2;
            v19 = 2;
          }
          else
          {
            v8 = &psz;
            v19 = 2;
            v18 = 2;
          }
          v72 = v8;
          v73 = v18;
          v74 = 0;
          if ( v12 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v12[v20] );
            v21 = 2 * v20 + 2;
          }
          else
          {
            v12 = &psz;
            v21 = 2;
          }
          v69 = v12;
          v70 = v21;
          v71 = 0;
          if ( v13 )
          {
            v22 = -1;
            do
              ++v22;
            while ( v13[v22] );
            v19 = 2 * v22 + 2;
          }
          else
          {
            v13 = &psz;
          }
          v66 = v13;
          v67 = v19;
          v68 = 0;
          if ( v14 )
          {
            v23 = -1;
            do
              ++v23;
            while ( v14[v23] );
            v24 = v23 + 1;
          }
          else
          {
            v14 = &pszCabPath;
            v24 = 1;
          }
          v63 = v14;
          v64 = v24;
          v65 = 0;
          v61 = &v44;
          v62 = 4;
          v59 = &v45;
          v60 = 8;
          tlgWriteTransfer_EventWriteTransfer(v7, (int)&dword_140495C04, v15 + 8, v16, 8u, &v58);
          std::wstring::~wstring(v51);
          v25 = v48;
          if ( v48 )
          {
            if ( _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
              if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
            }
          }
          v26 = v50;
          if ( v50 )
          {
            if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
              if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
            }
          }
        }
        v27 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
        if ( *(_DWORD *)(a1 + 312) )
          goto LABEL_71;
      }
      else
      {
        wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
        v28 = Windows::Telemetry::Base::Provider();
        v29 = (int)v28;
        if ( *(_DWORD *)v28 > 5u
          && (*((_QWORD *)v28 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v28 + 3) & 0x400000000000LL) == *((_QWORD *)v28 + 3) )
        {
          v30 = (const OLECHAR *)v52;
          v31 = (const OLECHAR *)v54;
          v32 = *a2;
          LODWORD(v44) = GetCurrentThreadId();
          v45 = 0x1000000;
          v33 = *(_QWORD *)(a1 + 272);
          if ( !*(_BYTE *)(v33 + 4)
            || (v34 = v33 + 24, !*(_DWORD *)(v33 + 24))
            && !*(_DWORD *)(v33 + 28)
            && !*(_DWORD *)(v33 + 32)
            && !*(_DWORD *)(v33 + 36) )
          {
            v34 = 0;
          }
          v35 = -1;
          if ( v30 )
          {
            v36 = -1;
            do
              ++v36;
            while ( v30[v36] );
            v37 = 2 * v36 + 2;
            v38 = 2;
          }
          else
          {
            v30 = &psz;
            v38 = 2;
            v37 = 2;
          }
          v69 = v30;
          v70 = v37;
          v71 = 0;
          if ( v31 )
          {
            v39 = -1;
            do
              ++v39;
            while ( v31[v39] );
            v38 = 2 * v39 + 2;
          }
          else
          {
            v31 = &psz;
          }
          v66 = v31;
          v67 = v38;
          v68 = 0;
          if ( v32 )
          {
            do
              ++v35;
            while ( v32[v35] );
            v5 = v35 + 1;
          }
          else
          {
            v32 = &pszCabPath;
          }
          v63 = v32;
          v64 = v5;
          v65 = 0;
          v61 = &v44;
          v62 = 4;
          v59 = &v45;
          v60 = 8;
          tlgWriteTransfer_EventWriteTransfer(v29, (int)&dword_140495B96, v33 + 8, v34, 7u, &v58);
        }
        v27 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
        if ( *(_DWORD *)(a1 + 312) )
          goto LABEL_71;
      }
      wil::details::ThreadFailureCallbackHolder::StartWatching(v27);
LABEL_71:
      std::vector<wchar_t>::_Tidy(&v52);
      std::vector<wchar_t>::_Tidy(&v54);
    }
    catch ( ... )
    {
      v42 = v46[0];
      wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(v46[0]);
      v43 = Windows::Telemetry::Base::Provider();
      if ( *(_DWORD *)v43 > 5u
        && (*((_QWORD *)v43 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v43 + 3) & 0x400000000000LL) == *((_QWORD *)v43 + 3) )
      {
        v46[0] = (__int64)*a2;
        LODWORD(v44) = GetCurrentThreadId();
        v45 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v43,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)v46);
      }
      if ( !*(_DWORD *)(v42 + 312) )
        wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(v42 + 288));
      return;
    }
    return;
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
  v40 = Windows::Telemetry::Base::Provider();
  v41 = (int)v40;
  if ( *(_DWORD *)v40 > 5u
    && (*((_QWORD *)v40 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v40 + 3) & 0x400000000000LL) == *((_QWORD *)v40 + 3) )
  {
    v46[0] = (__int64)*a2;
    LODWORD(v44) = GetCurrentThreadId();
    v45 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v41,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)v46);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x140021a24  mov     [rsp+arg_10], rbx
0x140021a29  mov     [rsp+arg_18], rsi
0x140021a2e  mov     [rsp+arg_8], rdx
0x140021a33  push    rdi
0x140021a34  push    r12
0x140021a36  push    r13
0x140021a38  push    r14
0x140021a3a  push    r15
0x140021a3c  sub     rsp, 180h
0x140021a43  mov     rax, cs:__security_cookie
0x140021a4a  xor     rax, rsp
0x140021a4d  mov     [rsp+1A8h+var_38], rax
0x140021a55  mov     r14, rdx
0x140021a58  mov     rsi, rcx
0x140021a5b  mov     [rsp+1A8h+var_158], rcx
0x140021a60  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Feature_UTCLoggingforUpdateManager_57785634@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Feature_UTCLoggingforUpdateManager_57785634@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Feature_UTCLoggingforUpdateManager_57785634> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Feature_UTCLoggingforUpdateManager_57785634>::GetImpl(void)'::`2'::impl
0x140021a67  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Feature_UTCLoggingforUpdateManager_57785634@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Feature_UTCLoggingforUpdateManager_57785634>::__private_IsEnabled(void)
0x140021a6c  xor     r15d, r15d
0x140021a6f  test    al, al
0x140021a71  jz      loc_140021FBD
0x140021a77  xorps   xmm0, xmm0
0x140021a7a  movups  xmmword ptr [rsp+1A8h+SystemTime.wYear], xmm0
0x140021a82  xorps   xmm1, xmm1
0x140021a85  movups  xmmword ptr [rsp+1A8h+var_C8.wYear], xmm1
0x140021a8d  lea     rcx, [rsp+1A8h+SystemTime]; lpSystemTime
0x140021a95  call    cs:__imp_GetSystemTime
0x140021a9b  lea     rcx, [rsp+1A8h+var_C8]; lpSystemTime
0x140021aa3  call    cs:__imp_GetLocalTime
0x140021aa9  xorps   xmm0, xmm0
0x140021aac  xor     eax, eax
0x140021aae  movups  [rsp+1A8h+var_F0], xmm0
0x140021ab6  mov     [rsp+1A8h+var_E0], rax
0x140021abe  lea     r12d, [r15+1]
0x140021ac2  mov     r8b, r12b
0x140021ac5  lea     rdx, [rsp+1A8h+SystemTime]
0x140021acd  lea     rcx, [rsp+1A8h+var_F0]
0x140021ad5  call    ?to_iso8601_string@Time@Windows@@YA?AV?$vector@_WV?$allocator@_W@std@@@std@@AEBU_SYSTEMTIME@@_N@Z; Windows::Time::to_iso8601_string(_SYSTEMTIME const &,bool)
0x140021ada  nop
0x140021adb  xorps   xmm0, xmm0
0x140021ade  xor     eax, eax
0x140021ae0  movups  [rsp+1A8h+var_108], xmm0
0x140021ae8  mov     [rsp+1A8h+var_F8], rax
0x140021af0  xor     r8d, r8d
0x140021af3  lea     rdx, [rsp+1A8h+var_C8]
0x140021afb  lea     rcx, [rsp+1A8h+var_108]
0x140021b03  call    ?to_iso8601_string@Time@Windows@@YA?AV?$vector@_WV?$allocator@_W@std@@@std@@AEBU_SYSTEMTIME@@_N@Z; Windows::Time::to_iso8601_string(_SYSTEMTIME const &,bool)
0x140021b08  nop
0x140021b09  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x140021b10  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x140021b15  mov     rcx, rsi
0x140021b18  test    al, al
0x140021b1a  jz      loc_140021DEB
0x140021b20  call    ?zInternalStart@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140021b25  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x140021b2a  mov     r13, rax
0x140021b2d  cmp     dword ptr [rax], 5
0x140021b30  jbe     loc_140021DD0
0x140021b36  mov     rdx, 400000000000h
0x140021b40  test    [rax+10h], rdx
0x140021b44  jz      loc_140021DD0
0x140021b4a  mov     rcx, [rax+18h]
0x140021b4e  and     rcx, rdx
0x140021b51  cmp     rcx, [rax+18h]
0x140021b55  jnz     loc_140021DD0
0x140021b5b  mov     r15, qword ptr [rsp+1A8h+var_108]
0x140021b63  lea     rcx, [rsp+1A8h+var_138]
0x140021b68  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140021b6d  nop
0x140021b6e  mov     rcx, [rax]
0x140021b71  mov     rax, [rcx]
0x140021b74  lea     rdx, [rsp+1A8h+var_148]
0x140021b79  mov     rax, [rax+28h]
0x140021b7d  call    _guard_dispatch_icall
0x140021b82  nop
0x140021b83  mov     rcx, [rax]
0x140021b86  mov     rax, [rcx]
0x140021b89  lea     rdx, [rsp+1A8h+var_128]
0x140021b91  mov     rax, [rax+1B8h]
0x140021b98  call    _guard_dispatch_icall
0x140021b9d  mov     rdi, rax
0x140021ba0  cmp     qword ptr [rax+18h], 7
0x140021ba5  jbe     short loc_140021BAA
0x140021ba7  mov     rdi, [rax]
0x140021baa  mov     r12, qword ptr [rsp+1A8h+var_F0]
0x140021bb2  mov     r14, [r14]
0x140021bb5  call    cs:__imp_GetCurrentThreadId
0x140021bbb  mov     dword ptr [rsp+1A8h+var_168], eax
0x140021bbf  mov     [rsp+1A8h+var_160], 1000000h
0x140021bc8  mov     r8, [rsi+110h]
0x140021bcf  xor     edx, edx
0x140021bd1  cmp     [r8+4], dl
0x140021bd5  jz      short loc_140021BF2
0x140021bd7  lea     r9, [r8+18h]
0x140021bdb  cmp     [r9], edx
0x140021bde  jnz     short loc_140021BF5
0x140021be0  cmp     [r9+4], edx
0x140021be4  jnz     short loc_140021BF5
0x140021be6  cmp     [r9+8], edx
0x140021bea  jnz     short loc_140021BF5
0x140021bec  cmp     [r9+0Ch], edx
0x140021bf0  jnz     short loc_140021BF5
0x140021bf2  mov     r9, rdx; int
0x140021bf5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140021bf9  test    r15, r15
0x140021bfc  jz      short loc_140021C19
0x140021bfe  mov     rax, rbx
0x140021c01  inc     rax
0x140021c04  cmp     [r15+rax*2], dx
0x140021c09  jnz     short loc_140021C01
0x140021c0b  lea     ecx, ds:2[rax*2]
0x140021c12  mov     eax, 2
0x140021c17  jmp     short loc_140021C27
0x140021c19  lea     r15, psz
0x140021c20  mov     eax, 2
0x140021c25  mov     ecx, eax
0x140021c27  mov     [rsp+1A8h+var_48], r15
0x140021c2f  mov     [rsp+1A8h+var_40], ecx
0x140021c36  xor     r15d, r15d
0x140021c39  mov     [rsp+1A8h+var_3C], r15d
0x140021c41  test    rdi, rdi
0x140021c44  jz      short loc_140021C5C
0x140021c46  mov     rcx, rbx
0x140021c49  inc     rcx
0x140021c4c  cmp     [rdi+rcx*2], r15w
0x140021c51  jnz     short loc_140021C49
0x140021c53  lea     ecx, ds:2[rcx*2]
0x140021c5a  jmp     short loc_140021C65
0x140021c5c  lea     rdi, psz
0x140021c63  mov     ecx, eax
0x140021c65  mov     [rsp+1A8h+var_58], rdi
0x140021c6d  mov     [rsp+1A8h+var_50], ecx
0x140021c74  mov     [rsp+1A8h+var_4C], r15d
0x140021c7c  test    r12, r12
0x140021c7f  jz      short loc_140021C97
0x140021c81  mov     rax, rbx
0x140021c84  inc     rax
0x140021c87  cmp     [r12+rax*2], r15w
0x140021c8c  jnz     short loc_140021C84
0x140021c8e  lea     eax, ds:2[rax*2]
0x140021c95  jmp     short loc_140021C9E
0x140021c97  lea     r12, psz
0x140021c9e  mov     [rsp+1A8h+var_68], r12
0x140021ca6  mov     [rsp+1A8h+var_60], eax
0x140021cad  mov     [rsp+1A8h+var_5C], r15d
0x140021cb5  test    r14, r14
0x140021cb8  jz      short loc_140021CCA
0x140021cba  mov     rax, rbx
0x140021cbd  inc     rax
0x140021cc0  cmp     [r14+rax], r15b
0x140021cc4  jnz     short loc_140021CBD
0x140021cc6  inc     eax
0x140021cc8  jmp     short loc_140021CD6
0x140021cca  lea     r14, pszCabPath
0x140021cd1  mov     eax, 1
0x140021cd6  mov     [rsp+1A8h+var_78], r14
0x140021cde  mov     [rsp+1A8h+var_70], eax
0x140021ce5  mov     [rsp+1A8h+var_6C], r15d
0x140021ced  lea     rax, [rsp+1A8h+var_168]
0x140021cf2  mov     [rsp+1A8h+var_88], rax
0x140021cfa  mov     [rsp+1A8h+var_80], 4
0x140021d06  lea     rax, [rsp+1A8h+var_160]
0x140021d0b  mov     [rsp+1A8h+var_98], rax
0x140021d13  mov     [rsp+1A8h+var_90], 8
0x140021d1f  add     r8, 8; int
0x140021d23  lea     rax, [rsp+1A8h+var_B8]
0x140021d2b  mov     [rsp+1A8h+var_180], rax; PEVENT_DATA_DESCRIPTOR
0x140021d30  mov     [rsp+1A8h+var_188], 8; ULONG
0x140021d38  lea     rdx, dword_140495C04; int
0x140021d3f  mov     rcx, r13; int
0x140021d42  call    _tlgWriteTransfer_EventWriteTransfer
0x140021d47  lea     rcx, [rsp+1A8h+var_128]
0x140021d4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140021d54  nop
0x140021d55  mov     rdi, [rsp+1A8h+var_140]
0x140021d5a  test    rdi, rdi
0x140021d5d  jz      short loc_140021D93
0x140021d5f  mov     eax, ebx
0x140021d61  lock xadd [rdi+8], eax
0x140021d66  add     eax, ebx
0x140021d68  jnz     short loc_140021D93
0x140021d6a  mov     rax, [rdi]
0x140021d6d  mov     rcx, rdi
0x140021d70  mov     rax, [rax]
0x140021d73  call    _guard_dispatch_icall
0x140021d78  mov     eax, ebx
0x140021d7a  lock xadd [rdi+0Ch], eax
0x140021d7f  add     eax, ebx
0x140021d81  jnz     short loc_140021D93
0x140021d83  mov     rax, [rdi]
0x140021d86  mov     rcx, rdi
0x140021d89  mov     rax, [rax+8]
0x140021d8d  call    _guard_dispatch_icall
0x140021d92  nop
0x140021d93  mov     rdi, [rsp+1A8h+var_130]
0x140021d98  test    rdi, rdi
0x140021d9b  jz      short loc_140021DD0
0x140021d9d  mov     eax, ebx
0x140021d9f  lock xadd [rdi+8], eax
0x140021da4  add     eax, ebx
0x140021da6  jnz     short loc_140021DD0
0x140021da8  mov     rax, [rdi]
0x140021dab  mov     rcx, rdi
0x140021dae  mov     rax, [rax]
0x140021db1  call    _guard_dispatch_icall
0x140021db6  mov     eax, ebx
0x140021db8  lock xadd [rdi+0Ch], eax
0x140021dbd  add     eax, ebx
0x140021dbf  jnz     short loc_140021DD0
0x140021dc1  mov     rax, [rdi]
0x140021dc4  mov     rcx, rdi
0x140021dc7  mov     rax, [rax+8]
0x140021dcb  call    _guard_dispatch_icall
0x140021dd0  lea     rcx, [rsi+120h]; this
0x140021dd7  cmp     [rcx+18h], r15d
0x140021ddb  jnz     loc_140021F9C
0x140021de1  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140021de6  jmp     loc_140021F9C
0x140021deb  call    ?zInternalStart@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140021df0  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x140021df5  mov     r13, rax
0x140021df8  cmp     dword ptr [rax], 5
0x140021dfb  jbe     loc_140021F89
0x140021e01  mov     rdx, 400000000000h
0x140021e0b  test    [rax+10h], rdx
0x140021e0f  jz      loc_140021F89
0x140021e15  mov     rcx, [rax+18h]
0x140021e19  and     rcx, rdx
0x140021e1c  cmp     rcx, [rax+18h]
0x140021e20  jnz     loc_140021F89
0x140021e26  mov     rdi, qword ptr [rsp+1A8h+var_108]
0x140021e2e  mov     r15, qword ptr [rsp+1A8h+var_F0]
0x140021e36  mov     r14, [r14]
0x140021e39  call    cs:__imp_GetCurrentThreadId
0x140021e3f  mov     dword ptr [rsp+1A8h+var_168], eax
0x140021e43  mov     [rsp+1A8h+var_160], 1000000h
0x140021e4c  mov     r8, [rsi+110h]
0x140021e53  xor     edx, edx
0x140021e55  cmp     [r8+4], dl
0x140021e59  jz      short loc_140021E76
0x140021e5b  lea     r9, [r8+18h]
0x140021e5f  cmp     [r9], edx
0x140021e62  jnz     short loc_140021E79
0x140021e64  cmp     [r9+4], edx
0x140021e68  jnz     short loc_140021E79
0x140021e6a  cmp     [r9+8], edx
0x140021e6e  jnz     short loc_140021E79
0x140021e70  cmp     [r9+0Ch], edx
0x140021e74  jnz     short loc_140021E79
0x140021e76  mov     r9, rdx; int
0x140021e79  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140021e7d  test    rdi, rdi
0x140021e80  jz      short loc_140021E9C
0x140021e82  mov     rax, rbx
0x140021e85  inc     rax
0x140021e88  cmp     [rdi+rax*2], dx
0x140021e8c  jnz     short loc_140021E85
0x140021e8e  lea     ecx, ds:2[rax*2]
0x140021e95  mov     eax, 2
0x140021e9a  jmp     short loc_140021EAA
0x140021e9c  lea     rdi, psz
0x140021ea3  mov     eax, 2
0x140021ea8  mov     ecx, eax
0x140021eaa  mov     [rsp+1A8h+var_58], rdi
0x140021eb2  mov     [rsp+1A8h+var_50], ecx
0x140021eb9  mov     [rsp+1A8h+var_4C], edx
0x140021ec0  test    r15, r15
0x140021ec3  jz      short loc_140021EDB
0x140021ec5  mov     rax, rbx
0x140021ec8  inc     rax
0x140021ecb  cmp     [r15+rax*2], dx
0x140021ed0  jnz     short loc_140021EC8
0x140021ed2  lea     eax, ds:2[rax*2]
0x140021ed9  jmp     short loc_140021EE2
0x140021edb  lea     r15, psz
0x140021ee2  mov     [rsp+1A8h+var_68], r15
0x140021eea  mov     [rsp+1A8h+var_60], eax
0x140021ef1  xor     r15d, r15d
0x140021ef4  mov     [rsp+1A8h+var_5C], r15d
0x140021efc  test    r14, r14
0x140021eff  jz      short loc_140021F10
0x140021f01  inc     rbx
0x140021f04  cmp     [r14+rbx], r15b
0x140021f08  jnz     short loc_140021F01
0x140021f0a  lea     r12d, [rbx+1]
0x140021f0e  jmp     short loc_140021F17
0x140021f10  lea     r14, pszCabPath
0x140021f17  mov     [rsp+1A8h+var_78], r14
0x140021f1f  mov     [rsp+1A8h+var_70], r12d
0x140021f27  mov     [rsp+1A8h+var_6C], r15d
0x140021f2f  lea     rax, [rsp+1A8h+var_168]
0x140021f34  mov     [rsp+1A8h+var_88], rax
0x140021f3c  mov     [rsp+1A8h+var_80], 4
0x140021f48  lea     rax, [rsp+1A8h+var_160]
0x140021f4d  mov     [rsp+1A8h+var_98], rax
0x140021f55  mov     [rsp+1A8h+var_90], 8
0x140021f61  add     r8, 8; int
0x140021f65  lea     rax, [rsp+1A8h+var_B8]
0x140021f6d  mov     [rsp+1A8h+var_180], rax; PEVENT_DATA_DESCRIPTOR
0x140021f72  mov     [rsp+1A8h+var_188], 7; ULONG
0x140021f7a  lea     rdx, dword_140495B96; int
  ... truncated ...
```
