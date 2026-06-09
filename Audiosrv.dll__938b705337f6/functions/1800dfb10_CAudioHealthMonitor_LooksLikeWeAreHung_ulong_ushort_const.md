# CAudioHealthMonitor::LooksLikeWeAreHung(ulong,ushort const *)

- ea: `0x1800dfb10`
- end: `0x1800dfde8`
- name: `?LooksLikeWeAreHung@CAudioHealthMonitor@@UEAAXKPEBG@Z`
- size: `728`
- prototype: `void __fastcall(CAudioHealthMonitor *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800021e0`
- `0x1800022ac`
- `0x18001b3d0`
- `0x180060eec`
- `0x180063460`
- `0x180073310`
- `0x1800cdfbc`
- `0x1800dc3e4`
- `0x1800df890`
- `0x1800dfb10`
- `0x1800dfdf0`
- `0x18016b010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1800dfdba`
- `ntdll!RtlPublishWnfStateData` at `0x1800dfdba`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800dfc1d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800dfc1d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800dfc38`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800dfc38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dfb5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dfb5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dfdc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dfdc9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800dfc6c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800dfc6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dfd38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dfd38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800dfd6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800dfd6a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800dfd75`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800dfd75`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800dfd64`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800dfd64`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800dfd98`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800dfd98`
- `faultrep!ReportCoreHang` at `0x1800dfd59`
- `faultrep!ReportCoreHang` at `0x1800dfd59`

## string_xrefs

- `0x1800dfc58`: `avcore\audiocore\server\audiosrv\dll\audiohealthmonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CAudioHealthMonitor::LooksLikeWeAreHung(
        CAudioHealthMonitor *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ecx
  _DWORD *v8; // r8
  int v9; // r8d
  int v10; // r9d
  char *v11; // rbx
  CAudioHealthMonitor *v12; // rcx
  int v13; // eax
  _DWORD *v14; // r8
  int v15; // r8d
  int v16; // r9d
  int v17; // ebx
  struct AudioSrvTelemetryProvider *v18; // rax
  int v19; // r8d
  int v20; // r9d
  HANDLE CurrentProcess; // rax
  int v22; // [rsp+20h] [rbp-50h]
  char *v23; // [rsp+40h] [rbp-30h] BYREF
  char *v24; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v25[2]; // [rsp+50h] [rbp-20h] BYREF
  int v26[2]; // [rsp+58h] [rbp-18h] BYREF
  char *v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  unsigned int v29; // [rsp+B8h] [rbp+48h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v27 = (char *)this + 24;
    v6 = *((_DWORD *)this + 2);
    v7 = v6 + 1;
    if ( v6 + 1 >= v6 )
    {
      *((_DWORD *)this + 2) = v7;
      if ( v7 < *((_DWORD *)this + 3) )
      {
        if ( !*((_DWORD *)this + 17) )
        {
          *((_DWORD *)this + 17) = 1;
          CoCreateGuid((GUID *)((char *)this + 72));
          RtlPublishWnfStateData(WNF_AUDC_HEALTH_PROBLEM, 0, (char *)this + 72, 16);
        }
      }
      else if ( *((_DWORD *)this + 4) == 16 && !*((_DWORD *)this + 16) )
      {
        v8 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
        if ( *v8 > 4u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000001LL) )
        {
          v29 = *((_DWORD *)this + 3);
          LODWORD(v23) = *((_DWORD *)this + 2);
          LODWORD(v24) = 0;
          *(_QWORD *)v26 = a3;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v9,
            (unsigned int)&unk_1801A0F10,
            v9,
            v10,
            (__int64)v26,
            (__int64)&v24,
            (__int64)&v23,
            (__int64)&v29);
        }
        *((_DWORD *)this + 16) = 1;
        v11 = (char *)OpenEventW(0x100002u, 0, L"Local\\AudioDrvCallHang");
        v23 = v11;
        if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !WaitForSingleObject(v11, 0) )
        {
          v13 = CAudioHealthMonitor::CollectLiveKernelDump(v12, a2, a3);
          if ( v13 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x106,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiohealthmonitor.cpp",
              (const char *)(unsigned int)v13,
              v22);
          ResetEvent(v11);
        }
        v14 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
        if ( *v14 > 2u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000001LL) )
        {
          v29 = a2;
          *(_QWORD *)v26 = a3;
          v24 = (char *)this + 72;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v15,
            (unsigned int)&unk_1801A0EE2,
            v15,
            v16,
            (__int64)&v24,
            (__int64)v26,
            (__int64)&v29);
        }
        v17 = (*(__int64 (__fastcall **)(CAudioHealthMonitor *))(*(_QWORD *)this + 16LL))(this);
        if ( v17 )
        {
          v18 = AudioSrvTelemetryProvider::Instance();
          if ( **((_DWORD **)v18 + 1) > 4u )
          {
            if ( (unsigned __int8)tlgKeywordOn(*((_QWORD *)v18 + 1), 1) )
            {
              v29 = a2;
              *(_QWORD *)v26 = a3;
              LODWORD(v24) = v17;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                v19,
                (unsigned int)&unk_1801A0E94,
                v19,
                v20,
                (__int64)&v24,
                (__int64)v26,
                (__int64)&v29);
            }
          }
        }
        v25[0] = GetCurrentProcessId();
        v25[1] = v17;
        ReportCoreHang(v25, (unsigned int)(v17 != 0) + 1, a2, 1048609);
        Sleep(0xEA60u);
        CurrentProcess = GetCurrentProcess();
        TerminateProcess(CurrentProcess, 0);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
      }
    }
    if ( this != (CAudioHealthMonitor *)-24LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
  else
  {
    CAudioHealthMonitor::LooksLikeWeAreHung_Old(this, a2, a3);
  }
}

```

## disassembly

```asm
0x1800dfb10  mov     [rsp-28h+arg_0], rbx
0x1800dfb15  mov     [rsp-28h+arg_8], rsi
0x1800dfb1a  push    rbp
0x1800dfb1b  push    rdi
0x1800dfb1c  push    r13
0x1800dfb1e  push    r14
0x1800dfb20  push    r15
0x1800dfb22  mov     rbp, rsp
0x1800dfb25  sub     rsp, 70h
0x1800dfb29  mov     r14, r8
0x1800dfb2c  mov     r15d, edx
0x1800dfb2f  mov     rdi, rcx
0x1800dfb32  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x1800dfb39  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x1800dfb3e  test    al, al
0x1800dfb40  jnz     short loc_1800DFB55
0x1800dfb42  mov     r8, r14; unsigned __int16 *
0x1800dfb45  mov     edx, r15d; unsigned int
0x1800dfb48  mov     rcx, rdi; this
0x1800dfb4b  call    ?LooksLikeWeAreHung_Old@CAudioHealthMonitor@@AEAAXKPEBG@Z; CAudioHealthMonitor::LooksLikeWeAreHung_Old(ulong,ushort const *)
0x1800dfb50  jmp     loc_1800DFDCF
0x1800dfb55  lea     rsi, [rdi+18h]
0x1800dfb59  mov     rcx, rsi; lpCriticalSection
0x1800dfb5c  call    cs:__imp_EnterCriticalSection
0x1800dfb62  mov     [rbp+var_10], rsi
0x1800dfb66  mov     eax, [rdi+8]
0x1800dfb69  lea     ecx, [rax+1]
0x1800dfb6c  cmp     ecx, eax
0x1800dfb6e  jb      loc_1800DFDC1
0x1800dfb74  mov     [rdi+8], ecx
0x1800dfb77  cmp     ecx, [rdi+0Ch]
0x1800dfb7a  jb      loc_1800DFD87
0x1800dfb80  cmp     dword ptr [rdi+10h], 10h
0x1800dfb84  jnz     loc_1800DFDC1
0x1800dfb8a  cmp     dword ptr [rdi+40h], 0
0x1800dfb8e  jnz     loc_1800DFDC1
0x1800dfb94  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800dfb99  mov     r8, [rax+8]
0x1800dfb9d  mov     eax, [r8]
0x1800dfba0  mov     r13, 400000000001h
0x1800dfbaa  cmp     eax, 4
0x1800dfbad  jbe     short loc_1800DFC08
0x1800dfbaf  mov     rdx, r13
0x1800dfbb2  mov     rcx, r8
0x1800dfbb5  call    _tlgKeywordOn
0x1800dfbba  test    al, al
0x1800dfbbc  jz      short loc_1800DFC08
0x1800dfbbe  mov     eax, [rdi+0Ch]
0x1800dfbc1  mov     [rbp+arg_18], eax
0x1800dfbc4  mov     eax, [rdi+8]
0x1800dfbc7  mov     dword ptr [rbp+var_30], eax
0x1800dfbca  mov     dword ptr [rbp+var_28], 0
0x1800dfbd1  mov     qword ptr [rbp+var_18], r14
0x1800dfbd5  lea     rax, [rbp+arg_18]
0x1800dfbd9  mov     [rsp+70h+var_38], rax
0x1800dfbde  lea     rax, [rbp+var_30]
0x1800dfbe2  mov     [rsp+70h+var_40], rax
0x1800dfbe7  lea     rax, [rbp+var_28]
0x1800dfbeb  mov     [rsp+70h+var_48], rax
0x1800dfbf0  lea     rax, [rbp+var_18]
0x1800dfbf4  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800dfbf9  lea     rdx, unk_1801A0F10
0x1800dfc00  mov     rcx, r8
0x1800dfc03  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800dfc08  mov     dword ptr [rdi+40h], 1
0x1800dfc0f  lea     r8, aLocalAudiodrvc; "Local\\AudioDrvCallHang"
0x1800dfc16  xor     edx, edx; bInheritHandle
0x1800dfc18  mov     ecx, 100002h; dwDesiredAccess
0x1800dfc1d  call    cs:__imp_OpenEventW
0x1800dfc23  mov     rbx, rax
0x1800dfc26  mov     [rbp+var_30], rax
0x1800dfc2a  dec     rax
0x1800dfc2d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800dfc31  ja      short loc_1800DFC72
0x1800dfc33  xor     edx, edx; dwMilliseconds
0x1800dfc35  mov     rcx, rbx; hHandle
0x1800dfc38  call    cs:__imp_WaitForSingleObject
0x1800dfc3e  test    eax, eax
0x1800dfc40  jnz     short loc_1800DFC72
0x1800dfc42  mov     r8, r14; unsigned __int16 *
0x1800dfc45  mov     edx, r15d; unsigned int
0x1800dfc48  call    ?CollectLiveKernelDump@CAudioHealthMonitor@@AEAAJKPEBG@Z; CAudioHealthMonitor::CollectLiveKernelDump(ulong,ushort const *)
0x1800dfc4d  mov     rcx, [rbp+28h]; this
0x1800dfc51  test    eax, eax
0x1800dfc53  jns     short loc_1800DFC69
0x1800dfc55  mov     r9d, eax; char *
0x1800dfc58  lea     r8, aAvcoreAudiocor_32; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800dfc5f  mov     edx, 106h; void *
0x1800dfc64  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dfc69  mov     rcx, rbx; hEvent
0x1800dfc6c  call    cs:__imp_ResetEvent
0x1800dfc72  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800dfc77  mov     r8, [rax+8]
0x1800dfc7b  mov     eax, [r8]
0x1800dfc7e  cmp     eax, 2
0x1800dfc81  jbe     short loc_1800DFCCC
0x1800dfc83  mov     rdx, r13
0x1800dfc86  mov     rcx, r8
0x1800dfc89  call    _tlgKeywordOn
0x1800dfc8e  test    al, al
0x1800dfc90  jz      short loc_1800DFCCC
0x1800dfc92  mov     [rbp+arg_18], r15d
0x1800dfc96  mov     qword ptr [rbp+var_18], r14
0x1800dfc9a  lea     rax, [rdi+48h]
0x1800dfc9e  mov     [rbp+var_28], rax
0x1800dfca2  lea     rax, [rbp+arg_18]
0x1800dfca6  mov     [rsp+70h+var_40], rax
0x1800dfcab  lea     rax, [rbp+var_18]
0x1800dfcaf  mov     [rsp+70h+var_48], rax
0x1800dfcb4  lea     rax, [rbp+var_28]
0x1800dfcb8  mov     qword ptr [rsp+70h+var_50], rax
0x1800dfcbd  lea     rdx, unk_1801A0EE2
0x1800dfcc4  mov     rcx, r8
0x1800dfcc7  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800dfccc  mov     rax, [rdi]
0x1800dfccf  mov     rcx, rdi
0x1800dfcd2  mov     rax, [rax+10h]
0x1800dfcd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfcdb  mov     ebx, eax
0x1800dfcdd  test    eax, eax
0x1800dfcdf  jz      short loc_1800DFD38
0x1800dfce1  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800dfce6  mov     r8, [rax+8]
0x1800dfcea  mov     ecx, [r8]
0x1800dfced  cmp     ecx, 4
0x1800dfcf0  jbe     short loc_1800DFD38
0x1800dfcf2  mov     edx, 1
0x1800dfcf7  mov     rcx, r8
0x1800dfcfa  call    _tlgKeywordOn
0x1800dfcff  test    al, al
0x1800dfd01  jz      short loc_1800DFD38
0x1800dfd03  mov     [rbp+arg_18], r15d
0x1800dfd07  mov     qword ptr [rbp+var_18], r14
0x1800dfd0b  mov     dword ptr [rbp+var_28], ebx
0x1800dfd0e  lea     rax, [rbp+arg_18]
0x1800dfd12  mov     [rsp+70h+var_40], rax
0x1800dfd17  lea     rax, [rbp+var_18]
0x1800dfd1b  mov     [rsp+70h+var_48], rax
0x1800dfd20  lea     rax, [rbp+var_28]
0x1800dfd24  mov     qword ptr [rsp+70h+var_50], rax
0x1800dfd29  lea     rdx, unk_1801A0E94
0x1800dfd30  mov     rcx, r8
0x1800dfd33  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800dfd38  call    cs:__imp_GetCurrentProcessId
0x1800dfd3e  mov     [rbp+var_20], eax
0x1800dfd41  mov     [rbp+var_1C], ebx
0x1800dfd44  neg     ebx
0x1800dfd46  sbb     edx, edx
0x1800dfd48  neg     edx
0x1800dfd4a  inc     edx
0x1800dfd4c  mov     r9d, 100021h
0x1800dfd52  mov     r8d, r15d
0x1800dfd55  lea     rcx, [rbp+var_20]
0x1800dfd59  call    cs:__imp_ReportCoreHang
0x1800dfd5f  mov     ecx, 0EA60h; dwMilliseconds
0x1800dfd64  call    cs:__imp_Sleep
0x1800dfd6a  call    cs:__imp_GetCurrentProcess
0x1800dfd70  mov     rcx, rax; hProcess
0x1800dfd73  xor     edx, edx; uExitCode
0x1800dfd75  call    cs:__imp_TerminateProcess
0x1800dfd7b  nop
0x1800dfd7c  lea     rcx, [rbp+var_30]
0x1800dfd80  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800dfd85  jmp     short loc_1800DFDC1
0x1800dfd87  cmp     dword ptr [rdi+44h], 0
0x1800dfd8b  jnz     short loc_1800DFDC1
0x1800dfd8d  mov     dword ptr [rdi+44h], 1
0x1800dfd94  lea     rcx, [rdi+48h]; pguid
0x1800dfd98  call    cs:__imp_CoCreateGuid
0x1800dfd9e  mov     qword ptr [rsp+70h+var_50], 0
0x1800dfda7  mov     r9d, 10h
0x1800dfdad  lea     r8, [rdi+48h]
0x1800dfdb1  xor     edx, edx
0x1800dfdb3  mov     rcx, cs:WNF_AUDC_HEALTH_PROBLEM
0x1800dfdba  call    cs:__imp_RtlPublishWnfStateData
0x1800dfdc0  nop
0x1800dfdc1  test    rsi, rsi
0x1800dfdc4  jz      short loc_1800DFDCF
0x1800dfdc6  mov     rcx, rsi; lpCriticalSection
0x1800dfdc9  call    cs:__imp_LeaveCriticalSection
0x1800dfdcf  lea     r11, [rsp+70h+var_s0]
0x1800dfdd4  mov     rbx, [r11+30h]
0x1800dfdd8  mov     rsi, [r11+38h]
0x1800dfddc  mov     rsp, r11
0x1800dfddf  pop     r15
0x1800dfde1  pop     r14
0x1800dfde3  pop     r13
0x1800dfde5  pop     rdi
0x1800dfde6  pop     rbp
0x1800dfde7  retn
```
