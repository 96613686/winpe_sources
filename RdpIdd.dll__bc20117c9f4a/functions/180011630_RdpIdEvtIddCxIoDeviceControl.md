# RdpIdEvtIddCxIoDeviceControl

- ea: `0x180011630`
- end: `0x180011a57`
- name: `RdpIdEvtIddCxIoDeviceControl`
- size: `1063`
- prototype: `__int64 __fastcall(int, int, int, int, char *)`
- caller_count: `0`
- callee_count: `19`
- tags: ``

## callees

- `0x180001cec`
- `0x180006970`
- `0x180006ad0`
- `0x180006f60`
- `0x18000d614`
- `0x18000dbd8`
- `0x18000e978`
- `0x180010e48`
- `0x180010e74`
- `0x180010ec0`
- `0x180010ef4`
- `0x180010f88`
- `0x180010fc4`
- `0x180010ff8`
- `0x180011044`
- `0x180011088`
- `0x1800115e4`
- `0x180011630`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800116a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800119db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800116a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800119db`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011a2a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011a2a`

## pseudocode

```c
ULONG __fastcall RdpIdEvtIddCxIoDeviceControl(const void *a1, const void *a2, __int64 a3, __int64 a4, char *a5)
{
  char v9; // di
  bool v10; // bl
  bool v11; // si
  char CurrentThreadId; // al
  int v13; // r8d
  int v14; // edx
  unsigned __int64 v15; // rdx
  _DWORD *v16; // rcx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rax
  __int64 v20; // rbx
  unsigned __int64 v21; // rdx
  _DWORD *v22; // rcx
  int v23; // r9d
  unsigned int v24; // eax
  bool v25; // bl
  char v26; // al
  int v27; // r8d
  int v28; // edx
  int v30; // [rsp+20h] [rbp-91h]
  char *v31; // [rsp+28h] [rbp-89h]
  int v32; // [rsp+50h] [rbp-61h] BYREF
  char *v33; // [rsp+58h] [rbp-59h] BYREF
  const char *v34; // [rsp+60h] [rbp-51h] BYREF
  const char *v35; // [rsp+68h] [rbp-49h] BYREF
  char *Buffer; // [rsp+70h] [rbp-41h] BYREF
  __int64 v37; // [rsp+78h] [rbp-39h]
  char *v38[3]; // [rsp+88h] [rbp-29h] BYREF
  GUID ActivityId; // [rsp+A0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v9 = 1;
  v10 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v13) = v11;
    LOBYTE(v14) = v10;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      v13,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v30,
      (int)v31,
      12,
      &WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids,
      CurrentThreadId);
  }
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  if ( RdpIddLoggingProvider::IsEnabled(5u, v15) )
  {
    std::vector<char>::vector<char>(&Buffer);
    snprintf(
      Buffer,
      v37 - (_QWORD)Buffer,
      "Device 0x%p, Request 0x%p OutputBufferLength %zu InputBufferLength %zu IoControlCode %x",
      a1,
      a2,
      a3,
      a4,
      (_DWORD)a5);
    v16 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v16 > 5u )
    {
      v33 = Buffer;
      v34 = "RdpIdEvtIddCxIoDeviceControl";
      v32 = 303;
      v35 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v16,
        (unsigned int)word_18004C512,
        v17,
        v18,
        (__int64)&v35,
        (__int64)&v32,
        (__int64)&v34,
        (__int64)&v33);
    }
    std::vector<char>::_Tidy(&Buffer);
  }
  v19 = (*(__int64 (__fastcall **)(__int64, const void *, __int64 *))(WdfFunctions_02025 + 984))(
          WdfDriverGlobals,
          a1,
          off_180057078);
  v20 = v19;
  if ( byte_180057E4D )
    __debugbreak();
  std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    &Buffer,
    *(_QWORD *)(v19 + 24));
  if ( (_BYTE)v37 )
  {
    if ( (const GUID *)_std_find_trivial_4(
                         qword_180043620,
                         &WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids,
                         (unsigned int)a5) == &WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids )
    {
      LODWORD(v31) = (_DWORD)a5;
      wil::details::in1diag3::Log_NtStatusMsg(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp",
        (const char *)0xC00000BBLL,
        (int)"Unsupported Ioctl: %#x",
        v31);
    }
    else if ( !CRdpIdAdapter::IsReady(*(CRdpIdAdapter **)v20)
           && (((_DWORD)a5 + 2147483584) & 0xFFFFFFF7) != 0
           && *(_QWORD *)(v20 + 16) )
    {
      v24 = (*(__int64 (__fastcall **)(__int64, const void *))(WdfFunctions_02025 + 1392))(WdfDriverGlobals, a2);
      wil::details::in1diag3::Log_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp",
        (const char *)v24,
        (int)"Failed to queue request to pending Ioctl queue",
        v31);
    }
    else
    {
      ProcessIoDeviceControl(a1, a2);
      if ( *(_QWORD *)(v20 + 16) && CRdpIdAdapter::IsReady(*(CRdpIdAdapter **)v20) )
        DrainPendingIoctlQueue(a1);
    }
  }
  else
  {
    if ( RdpIddLoggingProvider::IsEnabled(4u, v21) )
    {
      std::vector<char>::vector<char>(v38);
      snprintf(v38[0], v38[1] - v38[0], "Device is not accepting IOCTLs anymore. IoControlCode %x", (_DWORD)a5);
      v22 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v22 > 4u )
      {
        v35 = v38[0];
        v34 = "RdpIdEvtIddCxIoDeviceControl";
        v32 = 336;
        v33 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v22,
          (unsigned int)byte_18004C4DB,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp",
          v23,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v34,
          (__int64)&v35);
      }
      std::vector<char>::_Tidy(v38);
    }
    (*(void (__fastcall **)(__int64, const void *, __int64))(WdfFunctions_02025 + 1304))(
      WdfDriverGlobals,
      a2,
      3221225860LL);
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v9 = 0;
  }
  v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v26 = GetCurrentThreadId();
    LOBYTE(v27) = v25;
    LOBYTE(v28) = v9;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v28,
      v27,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v30,
      (int)v31,
      13,
      &WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids,
      v26);
  }
  std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(&Buffer);
  return EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x180011630  push    rbp
0x180011632  push    rbx
0x180011633  push    rsi
0x180011634  push    rdi
0x180011635  push    r12
0x180011637  push    r13
0x180011639  push    r14
0x18001163b  push    r15
0x18001163d  lea     rbp, [rsp-17h]
0x180011642  sub     rsp, 0C8h
0x180011649  mov     rax, cs:__security_cookie
0x180011650  xor     rax, rsp
0x180011653  mov     [rbp+4Fh+var_50], rax
0x180011657  mov     r13, r9
0x18001165a  mov     r12, r8
0x18001165d  mov     r15, rdx
0x180011660  mov     r14, rcx
0x180011663  mov     rax, cs:WPP_GLOBAL_Control
0x18001166a  lea     rcx, WPP_GLOBAL_Control
0x180011671  mov     dil, 1
0x180011674  cmp     rax, rcx
0x180011677  jz      short loc_18001168A
0x180011679  test    [rax+1Ch], dil
0x18001167d  jz      short loc_18001168A
0x18001167f  cmp     byte ptr [rax+19h], 4
0x180011683  jb      short loc_18001168A
0x180011685  mov     bl, dil
0x180011688  jmp     short loc_18001168C
0x18001168a  xor     bl, bl
0x18001168c  lea     rax, WPP_RECORDER_INITIALIZED
0x180011693  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001169a  setnz   sil
0x18001169e  test    bl, bl
0x1800116a0  jnz     short loc_1800116A7
0x1800116a2  test    sil, sil
0x1800116a5  jz      short loc_1800116E3
0x1800116a7  call    cs:__imp_GetCurrentThreadId
0x1800116ae  nop     dword ptr [rax+rax+00h]
0x1800116b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116ba  mov     r8b, sil; int
0x1800116bd  mov     dword ptr [rsp+100h+var_C0], eax; char
0x1800116c1  mov     dl, bl; int
0x1800116c3  lea     rax, WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids
0x1800116ca  mov     [rsp+100h+MessageGuid], rax; MessageGuid
0x1800116cf  mov     r9, [rcx+28h]; int
0x1800116d3  mov     rcx, [rcx+10h]; int
0x1800116d7  mov     [rsp+100h+var_D0], 0Ch; __int16
0x1800116de  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800116e3  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x1800116ea  lea     rcx, [rbp+4Fh+ActivityId]; ActivityId
0x1800116ee  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x1800116f3  mov     cl, 5; unsigned __int8
0x1800116f5  call    ?IsEnabled@RdpIddLoggingProvider@@SA_NE_K@Z; RdpIddLoggingProvider::IsEnabled(uchar,unsigned __int64)
0x1800116fa  mov     esi, dword ptr [rbp+4Fh+arg_20]
0x1800116fd  lea     rbx, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180011704  test    al, al
0x180011706  jz      loc_1800117B4
0x18001170c  lea     rcx, [rbp+4Fh+Buffer]
0x180011710  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x180011715  mov     rdx, [rbp+4Fh+var_88]
0x180011719  lea     r8, Format; "Device 0x%p, Request 0x%p OutputBufferL"...
0x180011720  mov     rcx, [rbp+4Fh+Buffer]; Buffer
0x180011724  mov     r9, r14
0x180011727  mov     dword ptr [rsp+100h+MessageGuid], esi
0x18001172b  sub     rdx, rcx; BufferCount
0x18001172e  mov     qword ptr [rsp+100h+var_D0], r13
0x180011733  mov     [rsp+100h+var_D8], r12
0x180011738  mov     qword ptr [rsp+100h+var_E0], r15
0x18001173d  call    snprintf
0x180011742  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180011747  mov     rcx, [rax+8]
0x18001174b  mov     eax, [rcx]
0x18001174d  cmp     eax, 5
0x180011750  jbe     short loc_1800117A2
0x180011752  mov     rax, [rbp+4Fh+Buffer]
0x180011756  lea     r12, aRdpidevtiddcxi; "RdpIdEvtIddCxIoDeviceControl"
0x18001175d  mov     [rbp+4Fh+var_A8], rax
0x180011761  lea     rdx, word_18004C512
0x180011768  lea     rax, [rbp+4Fh+var_A8]
0x18001176c  mov     [rbp+4Fh+var_A0], r12
0x180011770  mov     [rsp+100h+MessageGuid], rax
0x180011775  lea     rax, [rbp+4Fh+var_A0]
0x180011779  mov     qword ptr [rsp+100h+var_D0], rax
0x18001177e  lea     rax, [rbp+4Fh+var_B0]
0x180011782  mov     [rsp+100h+var_D8], rax
0x180011787  lea     rax, [rbp+4Fh+var_98]
0x18001178b  mov     qword ptr [rsp+100h+var_E0], rax
0x180011790  mov     [rbp+4Fh+var_B0], 12Fh
0x180011797  mov     [rbp+4Fh+var_98], rbx
0x18001179b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800117a0  jmp     short loc_1800117A9
0x1800117a2  lea     r12, aRdpidevtiddcxi; "RdpIdEvtIddCxIoDeviceControl"
0x1800117a9  lea     rcx, [rbp+4Fh+Buffer]
0x1800117ad  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x1800117b2  jmp     short loc_1800117BB
0x1800117b4  lea     r12, aRdpidevtiddcxi; "RdpIdEvtIddCxIoDeviceControl"
0x1800117bb  mov     rax, cs:WdfFunctions_02025
0x1800117c2  mov     rdx, r14
0x1800117c5  mov     r8, cs:off_180057078
0x1800117cc  mov     rcx, cs:WdfDriverGlobals
0x1800117d3  mov     rax, [rax+3D8h]
0x1800117da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117df  xor     r13d, r13d
0x1800117e2  mov     rbx, rax
0x1800117e5  cmp     cs:byte_180057E4D, r13b
0x1800117ec  jz      short loc_1800117EF
0x1800117ee  int     3; Trap to Debugger
0x1800117ef  mov     rdx, [rax+18h]
0x1800117f3  lea     rcx, [rbp+4Fh+Buffer]
0x1800117f7  call    ??0?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@Utry_to_lock_t@1@@Z; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &,std::try_to_lock_t)
0x1800117fc  cmp     byte ptr [rbp+4Fh+var_88], r13b
0x180011800  jnz     loc_1800118C7
0x180011806  mov     cl, 4; unsigned __int8
0x180011808  call    ?IsEnabled@RdpIddLoggingProvider@@SA_NE_K@Z; RdpIddLoggingProvider::IsEnabled(uchar,unsigned __int64)
0x18001180d  test    al, al
0x18001180f  jz      loc_18001189F
0x180011815  lea     rcx, [rbp+4Fh+var_78]
0x180011819  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x18001181e  mov     rdx, [rbp+4Fh+var_70]
0x180011822  lea     r8, aDeviceIsNotAcc; "Device is not accepting IOCTLs anymore."...
0x180011829  mov     rcx, [rbp+4Fh+var_78]; Buffer
0x18001182d  mov     r9d, esi
0x180011830  sub     rdx, rcx; BufferCount
0x180011833  call    snprintf
0x180011838  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001183d  mov     rcx, [rax+8]
0x180011841  mov     eax, [rcx]
0x180011843  cmp     eax, 4
0x180011846  jbe     short loc_180011896
0x180011848  mov     rax, [rbp+4Fh+var_78]
0x18001184c  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180011853  mov     [rbp+4Fh+var_98], rax
0x180011857  lea     rdx, byte_18004C4DB
0x18001185e  lea     rax, [rbp+4Fh+var_98]
0x180011862  mov     [rbp+4Fh+var_A0], r12
0x180011866  mov     [rsp+100h+MessageGuid], rax
0x18001186b  lea     rax, [rbp+4Fh+var_A0]
0x18001186f  mov     qword ptr [rsp+100h+var_D0], rax
0x180011874  lea     rax, [rbp+4Fh+var_B0]
0x180011878  mov     [rsp+100h+var_D8], rax
0x18001187d  lea     rax, [rbp+4Fh+var_A8]
0x180011881  mov     qword ptr [rsp+100h+var_E0], rax
0x180011886  mov     [rbp+4Fh+var_B0], 150h
0x18001188d  mov     [rbp+4Fh+var_A8], r8
0x180011891  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180011896  lea     rcx, [rbp+4Fh+var_78]
0x18001189a  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x18001189f  mov     rax, cs:WdfFunctions_02025
0x1800118a6  mov     r8d, 0C0000184h
0x1800118ac  mov     rcx, cs:WdfDriverGlobals
0x1800118b3  mov     rdx, r15
0x1800118b6  mov     rax, [rax+518h]
0x1800118bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c2  jmp     loc_18001199F
0x1800118c7  lea     r12, WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids
0x1800118ce  mov     r8d, esi
0x1800118d1  mov     rdx, r12
0x1800118d4  lea     rcx, qword_180043620
0x1800118db  call    __std_find_trivial_4
0x1800118e0  cmp     rax, r12
0x1800118e3  jnz     short loc_180011915
0x1800118e5  mov     rcx, [rbp+57h]; this
0x1800118e9  lea     rax, aUnsupportedIoc; "Unsupported Ioctl: %#x"
0x1800118f0  mov     dword ptr [rsp+100h+var_D8], esi; char *
0x1800118f4  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800118fb  mov     r9d, 0C00000BBh; char *
0x180011901  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180011906  mov     edx, 15Ah; void *
0x18001190b  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180011910  jmp     loc_18001199F
0x180011915  mov     rcx, [rbx]; this
0x180011918  call    ?IsReady@CRdpIdAdapter@@QEBA_NXZ; CRdpIdAdapter::IsReady(void)
0x18001191d  test    al, al
0x18001191f  jnz     short loc_18001197A
0x180011921  lea     eax, [rsi+7FFFFFC0h]
0x180011927  test    eax, 0FFFFFFF7h
0x18001192c  jz      short loc_18001197A
0x18001192e  mov     r8, [rbx+10h]
0x180011932  test    r8, r8
0x180011935  jz      short loc_18001197A
0x180011937  mov     rax, cs:WdfFunctions_02025
0x18001193e  mov     rdx, r15
0x180011941  mov     rcx, cs:WdfDriverGlobals
0x180011948  mov     rax, [rax+570h]
0x18001194f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011954  mov     rcx, [rbp+57h]; this
0x180011958  lea     rdx, aFailedToQueueR_0; "Failed to queue request to pending Ioct"...
0x18001195f  mov     qword ptr [rsp+100h+var_E0], rdx; int
0x180011964  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001196b  mov     edx, 168h; void *
0x180011970  mov     r9d, eax; char *
0x180011973  call    ?Log_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011978  jmp     short loc_18001199F
0x18001197a  mov     rdx, r15
0x18001197d  mov     rcx, r14
0x180011980  call    ProcessIoDeviceControl
0x180011985  cmp     [rbx+10h], r13
0x180011989  jz      short loc_18001199F
0x18001198b  mov     rcx, [rbx]; this
0x18001198e  call    ?IsReady@CRdpIdAdapter@@QEBA_NXZ; CRdpIdAdapter::IsReady(void)
0x180011993  test    al, al
0x180011995  jz      short loc_18001199F
0x180011997  mov     rcx, r14
0x18001199a  call    DrainPendingIoctlQueue
0x18001199f  mov     rax, cs:WPP_GLOBAL_Control
0x1800119a6  lea     rcx, WPP_GLOBAL_Control
0x1800119ad  cmp     rax, rcx
0x1800119b0  jz      short loc_1800119BE
0x1800119b2  test    [rax+1Ch], dil
0x1800119b6  jz      short loc_1800119BE
0x1800119b8  cmp     byte ptr [rax+19h], 4
0x1800119bc  jnb     short loc_1800119C1
0x1800119be  mov     dil, r13b
0x1800119c1  lea     rax, WPP_RECORDER_INITIALIZED
0x1800119c8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800119cf  setnz   bl
0x1800119d2  test    dil, dil
0x1800119d5  jnz     short loc_1800119DB
0x1800119d7  test    bl, bl
0x1800119d9  jz      short loc_180011A18
0x1800119db  call    cs:__imp_GetCurrentThreadId
0x1800119e2  nop     dword ptr [rax+rax+00h]
0x1800119e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119ee  mov     r8b, bl; int
0x1800119f1  mov     dword ptr [rsp+100h+var_C0], eax; char
0x1800119f5  mov     dl, dil; int
0x1800119f8  lea     rax, WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids
0x1800119ff  mov     [rsp+100h+MessageGuid], rax; MessageGuid
0x180011a04  mov     r9, [rcx+28h]; int
0x180011a08  mov     rcx, [rcx+10h]; int
0x180011a0c  mov     [rsp+100h+var_D0], 0Dh; __int16
0x180011a13  call    WPP_RECORDER_AND_TRACE_SF_D
0x180011a18  lea     rcx, [rbp+4Fh+Buffer]
0x180011a1c  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x180011a21  lea     rdx, [rbp+4Fh+ActivityId]; ActivityId
0x180011a25  mov     ecx, 2; ControlCode
0x180011a2a  call    cs:__imp_EventActivityIdControl
0x180011a31  nop     dword ptr [rax+rax+00h]
0x180011a36  mov     rcx, [rbp+4Fh+var_50]
0x180011a3a  xor     rcx, rsp; StackCookie
0x180011a3d  call    __security_check_cookie
0x180011a42  add     rsp, 0C8h
0x180011a49  pop     r15
0x180011a4b  pop     r14
0x180011a4d  pop     r13
0x180011a4f  pop     r12
0x180011a51  pop     rdi
0x180011a52  pop     rsi
0x180011a53  pop     rbx
0x180011a54  pop     rbp
0x180011a55  retn
```
