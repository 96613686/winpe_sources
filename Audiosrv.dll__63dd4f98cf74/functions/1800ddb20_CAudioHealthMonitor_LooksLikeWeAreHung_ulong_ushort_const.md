# CAudioHealthMonitor::LooksLikeWeAreHung(ulong,ushort const *)

- ea: `0x1800ddb20`
- end: `0x1800dddf8`
- name: `?LooksLikeWeAreHung@CAudioHealthMonitor@@UEAAXKPEBG@Z`
- size: `728`
- prototype: `void __fastcall(CAudioHealthMonitor *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800021e0`
- `0x1800022ac`
- `0x18001b520`
- `0x180060a5c`
- `0x180062fd0`
- `0x180072e10`
- `0x1800cbfcc`
- `0x1800da3f4`
- `0x1800dd8a0`
- `0x1800ddb20`
- `0x1800dde00`
- `0x18016c010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1800dddca`
- `ntdll!RtlPublishWnfStateData` at `0x1800dddca`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800ddc2d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800ddc2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ddc48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ddc48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddb6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddb6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dddd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dddd9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800ddc7c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800ddc7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ddd48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800ddd48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ddd7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ddd7a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800ddd85`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800ddd85`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ddd74`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ddd74`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800ddda8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800ddda8`
- `faultrep!ReportCoreHang` at `0x1800ddd69`
- `faultrep!ReportCoreHang` at `0x1800ddd69`

## string_xrefs

- `0x1800ddc68`: `avcore\audiocore\server\audiosrv\dll\audiohealthmonitor.cpp`

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

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
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
          RtlPublishWnfStateData(WNF_AUDC_HEALTH_PROBLEM, 0, (char *)this + 72, 16, 0);
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
            (unsigned int)&unk_1801A1FA8,
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
            (unsigned int)word_1801A1F7A,
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
                (unsigned int)&dword_1801A1F2C,
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
0x1800ddb20  mov     [rsp-28h+arg_0], rbx
0x1800ddb25  mov     [rsp-28h+arg_8], rsi
0x1800ddb2a  push    rbp
0x1800ddb2b  push    rdi
0x1800ddb2c  push    r13
0x1800ddb2e  push    r14
0x1800ddb30  push    r15
0x1800ddb32  mov     rbp, rsp
0x1800ddb35  sub     rsp, 70h
0x1800ddb39  mov     r14, r8
0x1800ddb3c  mov     r15d, edx
0x1800ddb3f  mov     rdi, rcx
0x1800ddb42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x1800ddb49  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x1800ddb4e  test    al, al
0x1800ddb50  jnz     short loc_1800DDB65
0x1800ddb52  mov     r8, r14; unsigned __int16 *
0x1800ddb55  mov     edx, r15d; unsigned int
0x1800ddb58  mov     rcx, rdi; this
0x1800ddb5b  call    ?LooksLikeWeAreHung_Old@CAudioHealthMonitor@@AEAAXKPEBG@Z; CAudioHealthMonitor::LooksLikeWeAreHung_Old(ulong,ushort const *)
0x1800ddb60  jmp     loc_1800DDDDF
0x1800ddb65  lea     rsi, [rdi+18h]
0x1800ddb69  mov     rcx, rsi; lpCriticalSection
0x1800ddb6c  call    cs:__imp_EnterCriticalSection
0x1800ddb72  mov     [rbp+var_10], rsi
0x1800ddb76  mov     eax, [rdi+8]
0x1800ddb79  lea     ecx, [rax+1]
0x1800ddb7c  cmp     ecx, eax
0x1800ddb7e  jb      loc_1800DDDD1
0x1800ddb84  mov     [rdi+8], ecx
0x1800ddb87  cmp     ecx, [rdi+0Ch]
0x1800ddb8a  jb      loc_1800DDD97
0x1800ddb90  cmp     dword ptr [rdi+10h], 10h
0x1800ddb94  jnz     loc_1800DDDD1
0x1800ddb9a  cmp     dword ptr [rdi+40h], 0
0x1800ddb9e  jnz     loc_1800DDDD1
0x1800ddba4  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800ddba9  mov     r8, [rax+8]
0x1800ddbad  mov     eax, [r8]
0x1800ddbb0  mov     r13, 400000000001h
0x1800ddbba  cmp     eax, 4
0x1800ddbbd  jbe     short loc_1800DDC18
0x1800ddbbf  mov     rdx, r13
0x1800ddbc2  mov     rcx, r8
0x1800ddbc5  call    _tlgKeywordOn
0x1800ddbca  test    al, al
0x1800ddbcc  jz      short loc_1800DDC18
0x1800ddbce  mov     eax, [rdi+0Ch]
0x1800ddbd1  mov     [rbp+arg_18], eax
0x1800ddbd4  mov     eax, [rdi+8]
0x1800ddbd7  mov     dword ptr [rbp+var_30], eax
0x1800ddbda  mov     dword ptr [rbp+var_28], 0
0x1800ddbe1  mov     qword ptr [rbp+var_18], r14
0x1800ddbe5  lea     rax, [rbp+arg_18]
0x1800ddbe9  mov     [rsp+70h+var_38], rax
0x1800ddbee  lea     rax, [rbp+var_30]
0x1800ddbf2  mov     [rsp+70h+var_40], rax
0x1800ddbf7  lea     rax, [rbp+var_28]
0x1800ddbfb  mov     [rsp+70h+var_48], rax
0x1800ddc00  lea     rax, [rbp+var_18]
0x1800ddc04  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800ddc09  lea     rdx, unk_1801A1FA8
0x1800ddc10  mov     rcx, r8
0x1800ddc13  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ddc18  mov     dword ptr [rdi+40h], 1
0x1800ddc1f  lea     r8, aLocalAudiodrvc; "Local\\AudioDrvCallHang"
0x1800ddc26  xor     edx, edx; bInheritHandle
0x1800ddc28  mov     ecx, 100002h; dwDesiredAccess
0x1800ddc2d  call    cs:__imp_OpenEventW
0x1800ddc33  mov     rbx, rax
0x1800ddc36  mov     [rbp+var_30], rax
0x1800ddc3a  dec     rax
0x1800ddc3d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ddc41  ja      short loc_1800DDC82
0x1800ddc43  xor     edx, edx; dwMilliseconds
0x1800ddc45  mov     rcx, rbx; hHandle
0x1800ddc48  call    cs:__imp_WaitForSingleObject
0x1800ddc4e  test    eax, eax
0x1800ddc50  jnz     short loc_1800DDC82
0x1800ddc52  mov     r8, r14; unsigned __int16 *
0x1800ddc55  mov     edx, r15d; unsigned int
0x1800ddc58  call    ?CollectLiveKernelDump@CAudioHealthMonitor@@AEAAJKPEBG@Z; CAudioHealthMonitor::CollectLiveKernelDump(ulong,ushort const *)
0x1800ddc5d  mov     rcx, [rbp+28h]; this
0x1800ddc61  test    eax, eax
0x1800ddc63  jns     short loc_1800DDC79
0x1800ddc65  mov     r9d, eax; char *
0x1800ddc68  lea     r8, aAvcoreAudiocor_32; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800ddc6f  mov     edx, 106h; void *
0x1800ddc74  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ddc79  mov     rcx, rbx; hEvent
0x1800ddc7c  call    cs:__imp_ResetEvent
0x1800ddc82  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800ddc87  mov     r8, [rax+8]
0x1800ddc8b  mov     eax, [r8]
0x1800ddc8e  cmp     eax, 2
0x1800ddc91  jbe     short loc_1800DDCDC
0x1800ddc93  mov     rdx, r13
0x1800ddc96  mov     rcx, r8
0x1800ddc99  call    _tlgKeywordOn
0x1800ddc9e  test    al, al
0x1800ddca0  jz      short loc_1800DDCDC
0x1800ddca2  mov     [rbp+arg_18], r15d
0x1800ddca6  mov     qword ptr [rbp+var_18], r14
0x1800ddcaa  lea     rax, [rdi+48h]
0x1800ddcae  mov     [rbp+var_28], rax
0x1800ddcb2  lea     rax, [rbp+arg_18]
0x1800ddcb6  mov     [rsp+70h+var_40], rax
0x1800ddcbb  lea     rax, [rbp+var_18]
0x1800ddcbf  mov     [rsp+70h+var_48], rax
0x1800ddcc4  lea     rax, [rbp+var_28]
0x1800ddcc8  mov     qword ptr [rsp+70h+var_50], rax
0x1800ddccd  lea     rdx, word_1801A1F7A
0x1800ddcd4  mov     rcx, r8
0x1800ddcd7  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800ddcdc  mov     rax, [rdi]
0x1800ddcdf  mov     rcx, rdi
0x1800ddce2  mov     rax, [rax+10h]
0x1800ddce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddceb  mov     ebx, eax
0x1800ddced  test    eax, eax
0x1800ddcef  jz      short loc_1800DDD48
0x1800ddcf1  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800ddcf6  mov     r8, [rax+8]
0x1800ddcfa  mov     ecx, [r8]
0x1800ddcfd  cmp     ecx, 4
0x1800ddd00  jbe     short loc_1800DDD48
0x1800ddd02  mov     edx, 1
0x1800ddd07  mov     rcx, r8
0x1800ddd0a  call    _tlgKeywordOn
0x1800ddd0f  test    al, al
0x1800ddd11  jz      short loc_1800DDD48
0x1800ddd13  mov     [rbp+arg_18], r15d
0x1800ddd17  mov     qword ptr [rbp+var_18], r14
0x1800ddd1b  mov     dword ptr [rbp+var_28], ebx
0x1800ddd1e  lea     rax, [rbp+arg_18]
0x1800ddd22  mov     [rsp+70h+var_40], rax
0x1800ddd27  lea     rax, [rbp+var_18]
0x1800ddd2b  mov     [rsp+70h+var_48], rax
0x1800ddd30  lea     rax, [rbp+var_28]
0x1800ddd34  mov     qword ptr [rsp+70h+var_50], rax
0x1800ddd39  lea     rdx, dword_1801A1F2C
0x1800ddd40  mov     rcx, r8
0x1800ddd43  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800ddd48  call    cs:__imp_GetCurrentProcessId
0x1800ddd4e  mov     [rbp+var_20], eax
0x1800ddd51  mov     [rbp+var_1C], ebx
0x1800ddd54  neg     ebx
0x1800ddd56  sbb     edx, edx
0x1800ddd58  neg     edx
0x1800ddd5a  inc     edx
0x1800ddd5c  mov     r9d, 100021h
0x1800ddd62  mov     r8d, r15d
0x1800ddd65  lea     rcx, [rbp+var_20]
0x1800ddd69  call    cs:__imp_ReportCoreHang
0x1800ddd6f  mov     ecx, 0EA60h; dwMilliseconds
0x1800ddd74  call    cs:__imp_Sleep
0x1800ddd7a  call    cs:__imp_GetCurrentProcess
0x1800ddd80  mov     rcx, rax; hProcess
0x1800ddd83  xor     edx, edx; uExitCode
0x1800ddd85  call    cs:__imp_TerminateProcess
0x1800ddd8b  nop
0x1800ddd8c  lea     rcx, [rbp+var_30]
0x1800ddd90  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ddd95  jmp     short loc_1800DDDD1
0x1800ddd97  cmp     dword ptr [rdi+44h], 0
0x1800ddd9b  jnz     short loc_1800DDDD1
0x1800ddd9d  mov     dword ptr [rdi+44h], 1
0x1800ddda4  lea     rcx, [rdi+48h]; pguid
0x1800ddda8  call    cs:__imp_CoCreateGuid
0x1800dddae  mov     qword ptr [rsp+70h+var_50], 0
0x1800dddb7  mov     r9d, 10h
0x1800dddbd  lea     r8, [rdi+48h]
0x1800dddc1  xor     edx, edx
0x1800dddc3  mov     rcx, cs:WNF_AUDC_HEALTH_PROBLEM
0x1800dddca  call    cs:__imp_RtlPublishWnfStateData
0x1800dddd0  nop
0x1800dddd1  test    rsi, rsi
0x1800dddd4  jz      short loc_1800DDDDF
0x1800dddd6  mov     rcx, rsi; lpCriticalSection
0x1800dddd9  call    cs:__imp_LeaveCriticalSection
0x1800ddddf  lea     r11, [rsp+70h+var_s0]
0x1800ddde4  mov     rbx, [r11+30h]
0x1800ddde8  mov     rsi, [r11+38h]
0x1800dddec  mov     rsp, r11
0x1800dddef  pop     r15
0x1800dddf1  pop     r14
0x1800dddf3  pop     r13
0x1800dddf5  pop     rdi
0x1800dddf6  pop     rbp
0x1800dddf7  retn
```
