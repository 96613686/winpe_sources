# CMidi2SchedulerMidiTransform::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *,ulong *,IMidiCallback *,__int64,IMidiDeviceManager *)

- ea: `0x18000abe0`
- end: `0x18000af73`
- name: `?Initialize@CMidi2SchedulerMidiTransform@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001@@PEAKPEAUIMidiCallback@@_JPEAUIMidiDeviceManager@@@Z`
- size: `915`
- prototype: `int(CMidi2SchedulerMidiTransform *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *, unsigned int *, struct IMidiCallback *, __int64, struct IMidiDeviceManager *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task`

## callees

- `0x1800016dc`
- `0x180002024`
- `0x180002050`
- `0x1800096d8`
- `0x18000a2a0`
- `0x18000a8d4`
- `0x18000abe0`
- `0x18000c040`
- `0x18000cc6c`

## import_xrefs

- `msvcp_win!_Thrd_detach` at `0x18000aeba`
- `msvcp_win!_Thrd_detach` at `0x18000aeba`
- `msvcp_win!_Thrd_id` at `0x18000adaf`
- `msvcp_win!_Thrd_id` at `0x18000adaf`
- `msvcp_win!_Thrd_join` at `0x18000add3`
- `msvcp_win!_Thrd_join` at `0x18000add3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000ada5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000adbe`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000ade2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000af5c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000af6c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000ada5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000adbe`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000ade2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000af5c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000af6c`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000ae01`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000ae01`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000ad5c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000ad5c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000acc9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000acc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2SchedulerMidiTransform::Initialize(
        CMidi2SchedulerMidiTransform *this,
        const unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0008_0001 *a3,
        unsigned int *a4,
        struct IMidiCallback *a5,
        const wchar_t *a6)
{
  char *v8; // rsi
  unsigned __int64 v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  LARGE_INTEGER v15; // rax
  _DWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  _Thrd_t *v21; // rdi
  std::_Stop_state *v22; // rcx
  int v23; // ebx
  int v24; // edx
  int v25; // eax
  _DWORD *v26; // rax
  volatile signed __int32 *v27; // rcx
  volatile signed __int32 *v28; // rax
  void *v29; // rcx
  _DWORD *v30; // rcx
  int v31; // r8d
  int v32; // r9d
  const wchar_t *v34; // [rsp+40h] [rbp-40h] BYREF
  CMidi2SchedulerMidiTransform *v35; // [rsp+48h] [rbp-38h] BYREF
  _Thrd_t v36; // [rsp+50h] [rbp-30h] BYREF
  __int128 v37; // [rsp+60h] [rbp-20h] BYREF
  _DWORD *v38; // [rsp+70h] [rbp-10h]
  LARGE_INTEGER Frequency; // [rsp+B0h] [rbp+30h] BYREF

  v8 = (char *)this + 16;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( v9 > *((_QWORD *)this + 5) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      (char *)this + 16,
      v9,
      a3);
  }
  else
  {
    if ( *((_QWORD *)this + 5) <= 7u )
      v10 = (char *)this + 16;
    else
      v10 = *(char **)v8;
    *((_QWORD *)this + 4) = v9;
    v11 = 2 * v9;
    memmove_0(v10, a2, 2 * v9);
    *(_WORD *)&v10[v11] = 0;
  }
  v12 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
  if ( *v12 > 4u )
  {
    if ( *((_QWORD *)v8 + 3) <= 7u )
      v15.QuadPart = (LONGLONG)v8;
    else
      v15 = *(LARGE_INTEGER *)v8;
    Frequency = v15;
    v34 = L"Enter";
    v35 = this;
    v36._Hnd = "CMidi2SchedulerMidiTransform::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v12,
      (unsigned int)&byte_180011B3F,
      v13,
      v14,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&Frequency);
  }
  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  *((_QWORD *)this + 13) = 300 * Frequency.QuadPart;
  *((_QWORD *)this + 15) = a5;
  *((_QWORD *)this + 16) = a6;
  v37 = 0;
  v16 = operator new(0x20u);
  *v16 = 1;
  v16[1] = 2;
  *((_QWORD *)v16 + 1) = 0;
  *((_QWORD *)v16 + 2) = 0;
  v16[6] = 0;
  v38 = v16;
  v17 = operator new(0x18u);
  *v17 = this;
  v17[1] = CMidi2SchedulerMidiTransform::QueueWorker;
  *((_DWORD *)v17 + 4) = 0;
  *((_DWORD *)v17 + 5) = *(&v36._Id + 1);
  v20 = _o__beginthreadex(
          0,
          0,
          std::thread::_Invoke<std::tuple<void (CMidi2SchedulerMidiTransform::*)(void),CMidi2SchedulerMidiTransform *>,0,1>,
          v17,
          0,
          (char *)&v37 + 8);
  *(_QWORD *)&v37 = v20;
  if ( !v20 )
  {
    DWORD2(v37) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18000AF72LL);
  }
  v21 = (_Thrd_t *)((char *)this + 224);
  if ( (__int128 *)((char *)this + 224) != &v37 )
  {
    if ( *((_DWORD *)this + 58) )
    {
      v22 = (std::_Stop_state *)*((_QWORD *)this + 30);
      if ( v22 )
        std::_Stop_state::_Request_stop(v22);
      if ( !*((_DWORD *)this + 58) )
      {
        std::_Throw_Cpp_error(1);
        __debugbreak();
      }
      v23 = *((_DWORD *)this + 58);
      if ( v23 == _Thrd_id() )
      {
        std::_Throw_Cpp_error(5);
        __debugbreak();
      }
      v36 = *v21;
      if ( _Thrd_join(&v36, 0) )
      {
        std::_Throw_Cpp_error(2);
        __debugbreak();
      }
      *v21 = 0;
      v20 = v37;
    }
    if ( *((_DWORD *)this + 58) )
    {
      _o_terminate(v19, v18, v20);
      __debugbreak();
    }
    v36 = 0;
    v24 = DWORD2(v37);
    v25 = HIDWORD(v37);
    *(_QWORD *)&v37 = 0;
    *((_QWORD *)&v37 + 1) = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v21->_Hnd = (void *)v20;
    *((_DWORD *)this + 58) = v24;
    *((_DWORD *)this + 59) = v25;
    v26 = v38;
    v38 = 0;
    v27 = (volatile signed __int32 *)*((_QWORD *)this + 30);
    *((_QWORD *)this + 30) = v26;
    if ( v27
      && (_InterlockedExchangeAdd(v27 + 1, 0xFFFFFFFE) & 0xFFFFFFFE) == 2
      && _InterlockedExchangeAdd(v27, 0xFFFFFFFF) == 1 )
    {
      operator delete((void *)v27);
    }
  }
  v28 = (volatile signed __int32 *)*((_QWORD *)this + 30);
  if ( v28 )
    _InterlockedIncrement(v28);
  v29 = (void *)*((_QWORD *)this + 31);
  *((_QWORD *)this + 31) = v28;
  if ( v29 && _InterlockedExchangeAdd((volatile signed __int32 *)v29, 0xFFFFFFFF) == 1 )
    operator delete(v29);
  if ( !*((_DWORD *)this + 58) || (v36 = *v21, _Thrd_detach(&v36)) )
  {
    std::_Throw_Cpp_error(1);
    __debugbreak();
  }
  *v21 = 0;
  v30 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
  if ( *v30 > 4u )
  {
    if ( *((_QWORD *)v8 + 3) > 7u )
      v8 = *(char **)v8;
    a5 = (struct IMidiCallback *)v8;
    a6 = L"Exit";
    Frequency.QuadPart = (LONGLONG)this;
    v36._Hnd = "CMidi2SchedulerMidiTransform::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v30,
      (unsigned int)byte_180011AE9,
      v31,
      v32,
      (__int64)&v36,
      (__int64)&Frequency,
      (__int64)&a6,
      (__int64)&a5);
  }
  std::jthread::~jthread((std::jthread *)&v37);
  return 0;
}

```

## disassembly

```asm
0x18000abe0  mov     [rsp-28h+arg_8], rbx
0x18000abe5  mov     [rsp-28h+arg_10], rsi
0x18000abea  push    rbp
0x18000abeb  push    rdi
0x18000abec  push    r12
0x18000abee  push    r14
0x18000abf0  push    r15
0x18000abf2  mov     rbp, rsp
0x18000abf5  sub     rsp, 80h
0x18000abfc  mov     r9, rdx
0x18000abff  mov     r14, rcx
0x18000ac02  lea     rsi, [rcx+10h]
0x18000ac06  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000ac0a  mov     rdx, r15
0x18000ac0d  xor     r12d, r12d
0x18000ac10  inc     rdx
0x18000ac13  cmp     [r9+rdx*2], r12w
0x18000ac18  jnz     short loc_18000AC10
0x18000ac1a  cmp     rdx, [rsi+18h]
0x18000ac1e  ja      short loc_18000AC4C
0x18000ac20  cmp     qword ptr [rsi+18h], 7
0x18000ac25  jbe     short loc_18000AC2C
0x18000ac27  mov     rdi, [rsi]
0x18000ac2a  jmp     short loc_18000AC2F
0x18000ac2c  mov     rdi, rsi
0x18000ac2f  mov     [rsi+10h], rdx
0x18000ac33  lea     rbx, [rdx+rdx]
0x18000ac37  mov     r8, rbx; Size
0x18000ac3a  mov     rdx, r9; Src
0x18000ac3d  mov     rcx, rdi; void *
0x18000ac40  call    memmove_0
0x18000ac45  mov     [rbx+rdi], r12w
0x18000ac4a  jmp     short loc_18000AC54
0x18000ac4c  mov     rcx, rsi
0x18000ac4f  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18000ac54  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000ac59  mov     rcx, [rax+8]
0x18000ac5d  mov     eax, [rcx]
0x18000ac5f  lea     rbx, aCmidi2schedule_4; "CMidi2SchedulerMidiTransform::Initializ"...
0x18000ac66  cmp     eax, 4
0x18000ac69  jbe     short loc_18000ACC1
0x18000ac6b  cmp     qword ptr [rsi+18h], 7
0x18000ac70  jbe     short loc_18000AC77
0x18000ac72  mov     rax, [rsi]
0x18000ac75  jmp     short loc_18000AC7A
0x18000ac77  mov     rax, rsi
0x18000ac7a  mov     qword ptr [rbp+Frequency], rax
0x18000ac7e  lea     rax, aEnter; "Enter"
0x18000ac85  mov     [rbp+var_40], rax
0x18000ac89  mov     [rbp+var_38], r14
0x18000ac8d  mov     [rbp+var_30._Hnd], rbx
0x18000ac91  lea     rax, [rbp+Frequency]
0x18000ac95  mov     [rsp+80h+var_48], rax
0x18000ac9a  lea     rax, [rbp+var_40]
0x18000ac9e  mov     [rsp+80h+var_50], rax
0x18000aca3  lea     rax, [rbp+var_38]
0x18000aca7  mov     [rsp+80h+var_58], rax
0x18000acac  lea     rax, [rbp+var_30]
0x18000acb0  mov     [rsp+80h+var_60], rax
0x18000acb5  lea     rdx, byte_180011B3F
0x18000acbc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000acc1  mov     qword ptr [rbp+Frequency], r12
0x18000acc5  lea     rcx, [rbp+Frequency]; lpFrequency
0x18000acc9  call    cs:__imp_QueryPerformanceFrequency
0x18000accf  imul    rax, qword ptr [rbp+Frequency], 12Ch
0x18000acd7  mov     [r14+68h], rax
0x18000acdb  mov     rax, [rbp+arg_20]
0x18000acdf  mov     [r14+78h], rax
0x18000ace3  mov     rax, [rbp+arg_28]
0x18000ace7  mov     [r14+80h], rax
0x18000acee  xorps   xmm0, xmm0
0x18000acf1  movups  [rbp+var_20], xmm0
0x18000acf5  mov     ecx, 20h ; ' '; Size
0x18000acfa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000acff  mov     dword ptr [rax], 1
0x18000ad05  mov     dword ptr [rax+4], 2
0x18000ad0c  xor     ecx, ecx
0x18000ad0e  mov     [rax+8], rcx
0x18000ad12  mov     [rax+10h], r12
0x18000ad16  mov     [rax+18h], r12d
0x18000ad1a  mov     [rbp+var_10], rax
0x18000ad1e  mov     ecx, 18h; Size
0x18000ad23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ad28  mov     [rax], r14
0x18000ad2b  lea     rcx, ?QueueWorker@CMidi2SchedulerMidiTransform@@AEAAXXZ; CMidi2SchedulerMidiTransform::QueueWorker(void)
0x18000ad32  mov     [rax+8], rcx
0x18000ad36  mov     [rax+10h], r12d
0x18000ad3a  mov     ecx, dword ptr [rbp+var_30+0Ch]
0x18000ad3d  mov     [rax+14h], ecx
0x18000ad40  lea     rcx, [rbp+var_20+8]
0x18000ad44  mov     [rsp+80h+var_58], rcx
0x18000ad49  mov     dword ptr [rsp+80h+var_60], r12d
0x18000ad4e  mov     r9, rax
0x18000ad51  lea     r8, ??$_Invoke@V?$tuple@P8CMidi2SchedulerMidiTransform@@EAAXXZPEAV1@@std@@$0A@$00@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (CMidi2SchedulerMidiTransform::*)(void),CMidi2SchedulerMidiTransform *>,0,1>(void *)
0x18000ad58  xor     edx, edx
0x18000ad5a  xor     ecx, ecx
0x18000ad5c  call    cs:__imp__o__beginthreadex
0x18000ad62  mov     r8, rax
0x18000ad65  mov     qword ptr [rbp+var_20], rax
0x18000ad69  test    rax, rax
0x18000ad6c  jz      loc_18000AF63
0x18000ad72  lea     rdi, [r14+0E0h]
0x18000ad79  lea     rax, [rbp+var_20]
0x18000ad7d  cmp     rdi, rax
0x18000ad80  jz      loc_18000AE6E
0x18000ad86  cmp     [rdi+8], r12d
0x18000ad8a  jz      short loc_18000ADFB
0x18000ad8c  mov     rcx, [rdi+10h]; this
0x18000ad90  test    rcx, rcx
0x18000ad93  jz      short loc_18000AD9A
0x18000ad95  call    ?_Request_stop@_Stop_state@std@@QEAA_NXZ; std::_Stop_state::_Request_stop(void)
0x18000ad9a  cmp     [rdi+8], r12d
0x18000ad9e  jnz     short loc_18000ADAC
0x18000ada0  mov     ecx, 1
0x18000ada5  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000adab  int     3; Trap to Debugger
0x18000adac  mov     ebx, [rdi+8]
0x18000adaf  call    cs:__imp__Thrd_id
0x18000adb5  cmp     ebx, eax
0x18000adb7  jnz     short loc_18000ADC5
0x18000adb9  mov     ecx, 5
0x18000adbe  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000adc4  int     3; Trap to Debugger
0x18000adc5  movups  xmm0, xmmword ptr [rdi]
0x18000adc8  movdqu  xmmword ptr [rbp+var_30._Hnd], xmm0
0x18000adcd  xor     edx, edx; int *
0x18000adcf  lea     rcx, [rbp+var_30]; _Thrd_t
0x18000add3  call    cs:__imp__Thrd_join
0x18000add9  test    eax, eax
0x18000addb  jz      short loc_18000ADE9
0x18000addd  mov     ecx, 2
0x18000ade2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000ade8  int     3; Trap to Debugger
0x18000ade9  xorps   xmm0, xmm0
0x18000adec  movdqu  xmmword ptr [rdi], xmm0
0x18000adf0  mov     r8, qword ptr [rbp+var_20]
0x18000adf4  lea     rbx, aCmidi2schedule_4; "CMidi2SchedulerMidiTransform::Initializ"...
0x18000adfb  cmp     [rdi+8], r12d
0x18000adff  jz      short loc_18000AE08
0x18000ae01  call    cs:__imp__o_terminate
0x18000ae07  int     3; Trap to Debugger
0x18000ae08  xorps   xmm0, xmm0
0x18000ae0b  movups  xmmword ptr [rbp+var_30._Hnd], xmm0
0x18000ae0f  mov     edx, dword ptr [rbp+var_20+8]
0x18000ae12  mov     eax, dword ptr [rbp+var_20+0Ch]
0x18000ae15  movsd   qword ptr [rbp+var_20], xmm0
0x18000ae1a  psrldq  xmm0, 8
0x18000ae1f  movd    dword ptr [rbp+var_20+8], xmm0
0x18000ae24  mov     ecx, dword ptr [rbp+var_30+0Ch]
0x18000ae27  mov     dword ptr [rbp+var_20+0Ch], ecx
0x18000ae2a  mov     [rdi], r8
0x18000ae2d  mov     [rdi+8], edx
0x18000ae30  mov     [rdi+0Ch], eax
0x18000ae33  mov     rax, [rbp+var_10]
0x18000ae37  mov     [rbp+var_10], r12
0x18000ae3b  mov     rcx, [rdi+10h]; Block
0x18000ae3f  mov     [rdi+10h], rax
0x18000ae43  test    rcx, rcx
0x18000ae46  jz      short loc_18000AE6E
0x18000ae48  mov     eax, 0FFFFFFFEh
0x18000ae4d  lock xadd [rcx+4], eax
0x18000ae52  and     eax, 0FFFFFFFEh
0x18000ae55  cmp     eax, 2
0x18000ae58  jnz     short loc_18000AE6E
0x18000ae5a  mov     eax, r15d
0x18000ae5d  lock xadd [rcx], eax
0x18000ae61  cmp     eax, 1
0x18000ae64  jnz     short loc_18000AE6E
0x18000ae66  lea     edx, [rax+1Fh]
0x18000ae69  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ae6e  mov     rax, [r14+0F0h]
0x18000ae75  test    rax, rax
0x18000ae78  jz      short loc_18000AE7D
0x18000ae7a  lock inc dword ptr [rax]
0x18000ae7d  mov     rcx, [r14+0F8h]; Block
0x18000ae84  mov     [r14+0F8h], rax
0x18000ae8b  test    rcx, rcx
0x18000ae8e  jz      short loc_18000AEA4
0x18000ae90  lock xadd [rcx], r15d
0x18000ae95  cmp     r15d, 1
0x18000ae99  jnz     short loc_18000AEA4
0x18000ae9b  lea     edx, [r15+1Fh]
0x18000ae9f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aea4  cmp     [rdi+8], r12d
0x18000aea8  jz      loc_18000AF57
0x18000aeae  movups  xmm0, xmmword ptr [rdi]
0x18000aeb1  movdqu  xmmword ptr [rbp+var_30._Hnd], xmm0
0x18000aeb6  lea     rcx, [rbp+var_30]; _Thrd_t
0x18000aeba  call    cs:__imp__Thrd_detach
0x18000aec0  test    eax, eax
0x18000aec2  jnz     loc_18000AF57
0x18000aec8  xorps   xmm0, xmm0
0x18000aecb  movdqu  xmmword ptr [rdi], xmm0
0x18000aecf  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000aed4  mov     rcx, [rax+8]
0x18000aed8  mov     eax, [rcx]
0x18000aeda  cmp     eax, 4
0x18000aedd  jbe     short loc_18000AF30
0x18000aedf  cmp     qword ptr [rsi+18h], 7
0x18000aee4  jbe     short loc_18000AEE9
0x18000aee6  mov     rsi, [rsi]
0x18000aee9  mov     [rbp+arg_20], rsi
0x18000aeed  lea     rax, aExit; "Exit"
0x18000aef4  mov     [rbp+arg_28], rax
0x18000aef8  mov     qword ptr [rbp+Frequency], r14
0x18000aefc  mov     [rbp+var_30._Hnd], rbx
0x18000af00  lea     rax, [rbp+arg_20]
0x18000af04  mov     [rsp+80h+var_48], rax
0x18000af09  lea     rax, [rbp+arg_28]
0x18000af0d  mov     [rsp+80h+var_50], rax
0x18000af12  lea     rax, [rbp+Frequency]
0x18000af16  mov     [rsp+80h+var_58], rax
0x18000af1b  lea     rax, [rbp+var_30]
0x18000af1f  mov     [rsp+80h+var_60], rax
0x18000af24  lea     rdx, byte_180011AE9
0x18000af2b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000af30  lea     rcx, [rbp+var_20]; this
0x18000af34  call    ??1jthread@std@@QEAA@XZ; std::jthread::~jthread(void)
0x18000af39  xor     eax, eax
0x18000af3b  lea     r11, [rsp+80h+var_s0]
0x18000af43  mov     rbx, [r11+38h]
0x18000af47  mov     rsi, [r11+40h]
0x18000af4b  mov     rsp, r11
0x18000af4e  pop     r15
0x18000af50  pop     r14
0x18000af52  pop     r12
0x18000af54  pop     rdi
0x18000af55  pop     rbp
0x18000af56  retn
0x18000af57  mov     ecx, 1
0x18000af5c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000af62  int     3; Trap to Debugger
0x18000af63  mov     dword ptr [rbp+var_20+8], r12d
0x18000af67  mov     ecx, 6
0x18000af6c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
