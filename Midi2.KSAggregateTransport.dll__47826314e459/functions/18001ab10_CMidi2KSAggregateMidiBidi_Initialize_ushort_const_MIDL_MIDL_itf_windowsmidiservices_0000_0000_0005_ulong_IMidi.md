# CMidi2KSAggregateMidiBidi::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64,_GUID)

- ea: `0x18001ab10`
- end: `0x18001af0b`
- name: `?Initialize@CMidi2KSAggregateMidiBidi@@UEAAJPEBGPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_JU_GUID@@@Z`
- size: `1019`
- prototype: `int(CMidi2KSAggregateMidiBidi *__hidden this, const unsigned __int16 *, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *, unsigned int *, struct IMidiCallback *, __int64, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x1800017d0`
- `0x180005020`
- `0x180005044`
- `0x180005070`
- `0x180005e9c`
- `0x18000b394`
- `0x18000d430`
- `0x1800106c8`
- `0x1800117d8`
- `0x180012304`
- `0x180012380`
- `0x180013118`
- `0x180014194`
- `0x1800163a8`
- `0x18001aa6c`
- `0x18001ab10`
- `0x18001b160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae23`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae23`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001ad2a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001ad2a`

## string_xrefs

- `0x18001ae93`: `Initialization complete`

## pseudocode

```c
__int64 __fastcall CMidi2KSAggregateMidiBidi::Initialize(
        CMidi2KSAggregateMidiBidi *this,
        const unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *a3,
        unsigned int *a4,
        struct IMidiCallback *a5)
{
  int v5; // r12d
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v12; // rsi
  _DWORD *v13; // rcx
  __int64 v14; // rax
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rax
  const char *v19; // rsi
  struct _RTL_CRITICAL_SECTION *v20; // r14
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v23; // rax
  int v24; // eax
  struct _RTL_CRITICAL_SECTION *v25; // rbx
  _DWORD *v26; // rcx
  int v27; // r8d
  int v28; // r9d
  int v29; // [rsp+20h] [rbp-E0h]
  const wchar_t *v30; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v31; // [rsp+48h] [rbp-B8h] BYREF
  const char *v32; // [rsp+50h] [rbp-B0h] BYREF
  const char *v33; // [rsp+58h] [rbp-A8h] BYREF
  char v34[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v35; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  _BYTE v38[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v39[32]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  const wchar_t **v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  const wchar_t **v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v46; // [rsp+110h] [rbp+10h]
  int v47; // [rsp+118h] [rbp+18h]
  int v48; // [rsp+11Ch] [rbp+1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v5 = (int)a4;
  if ( !a5 )
  {
    v9 = 27;
LABEL_3:
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidibidi.cpp",
      (const char *)0x80070057LL,
      v29);
    return v10;
  }
  if ( !a4 )
  {
    v9 = 28;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v9 = 29;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v9 = 30;
    goto LABEL_3;
  }
  v12 = -1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
  {
    v13 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v13 > 4u )
    {
      v31 = (const wchar_t *)this;
      v30 = L"Enter";
      v14 = -1;
      do
        ++v14;
      while ( a2[v14] );
      v46 = a2;
      v47 = 2 * v14 + 2;
      v48 = 0;
      v44 = &v30;
      v45 = 8;
      v42 = &v31;
      v43 = 8;
      v40 = "CMidi2KSAggregateMidiBidi::Initialize";
      v41 = 38;
      tlgWriteTransfer_EventWriteTransfer(v13, &dword_180088E9C, 0, 0, 6, v39);
    }
  }
  else
  {
    v15 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v15 > 4u )
    {
      v31 = a2;
      v32 = "CMidi2KSAggregateMidiBidi::Initialize";
      v30 = (const wchar_t *)this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v15,
        (unsigned int)&byte_180088E4F,
        v16,
        v17,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v31);
    }
  }
  v36 = 0;
  v35 = 0;
  v37 = 0;
  do
    ++v12;
  while ( a2[v12] );
  std::wstring::_Construct<1,unsigned short const *>(&v35);
  v18 = std::wstring::wstring(v34, &v35);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v38, v18);
  v19 = (char *)this + 16;
  std::wstring::operator=((char *)this + 16, v38);
  std::wstring::~wstring(v38);
  std::wstring::~wstring(&v35);
  _InterlockedExchange64((volatile __int64 *)this + 6, 0);
  v20 = (struct _RTL_CRITICAL_SECTION *)operator new(0x60u);
  memset_0(v20, 0, 0x60u);
  InitializeCriticalSectionEx(v20, 0, 0);
  *(_QWORD *)&v20[1].LockCount = 0;
  v20[1].OwningThread = 0;
  v21 = operator new(0x30u);
  *v21 = v21;
  v21[1] = v21;
  v21[2] = v21;
  *((_WORD *)v21 + 12) = 257;
  *(_QWORD *)&v20[1].LockCount = v21;
  v20[1].LockSemaphore = 0;
  v20[1].SpinCount = 0;
  v22 = operator new(0x30u);
  *v22 = v22;
  v22[1] = v22;
  v22[2] = v22;
  *((_WORD *)v22 + 12) = 257;
  v20[1].LockSemaphore = v22;
  v20[2].DebugInfo = 0;
  *(_QWORD *)&v20[2].LockCount = 0;
  v23 = (struct _RTL_CRITICAL_SECTION_DEBUG *)operator new(0x48u);
  *(_QWORD *)&v23->Type = v23;
  v23->CriticalSection = (struct _RTL_CRITICAL_SECTION *)v23;
  v23->ProcessLocksList.Flink = (struct _LIST_ENTRY *)v23;
  LOWORD(v23->ProcessLocksList.Blink) = 257;
  v20[2].DebugInfo = v23;
  v24 = CMidi2KSAggregateMidi::Initialize(v20, a2, 2, a3);
  v10 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidibidi.cpp",
      (const char *)(unsigned int)v24,
      v5);
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>(&v20[2]);
    std::_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(&v20[1].LockSemaphore);
    std::_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(&v20[1].LockCount);
    DeleteCriticalSection(v20);
    operator delete(v20);
    return v10;
  }
  v25 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v20;
  if ( v25 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>(&v25[2]);
    std::_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(&v25[1].LockSemaphore);
    std::_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(&v25[1].LockCount);
    DeleteCriticalSection(v25);
    operator delete(v25);
  }
  v26 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v26 > 4u )
  {
    if ( *((_QWORD *)this + 5) > 7u )
      v19 = *(const char **)v19;
    v32 = v19;
    v31 = L"Initialization complete";
    v30 = (const wchar_t *)this;
    v33 = "CMidi2KSAggregateMidiBidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v26,
      (unsigned int)byte_180088DF9,
      v27,
      v28,
      (__int64)&v33,
      (__int64)&v30,
      (__int64)&v31,
      (__int64)&v32);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ab10  push    rbp
0x18001ab12  push    rbx
0x18001ab13  push    rsi
0x18001ab14  push    rdi
0x18001ab15  push    r12
0x18001ab17  push    r13
0x18001ab19  push    r14
0x18001ab1b  push    r15
0x18001ab1d  lea     rbp, [rsp-38h]
0x18001ab22  sub     rsp, 138h
0x18001ab29  mov     rax, cs:__security_cookie
0x18001ab30  xor     rax, rsp
0x18001ab33  mov     [rbp+70h+var_50], rax
0x18001ab37  mov     r13, [rbp+70h+arg_20]
0x18001ab3e  xor     r14d, r14d
0x18001ab41  mov     r12, r9
0x18001ab44  mov     r15, r8
0x18001ab47  mov     rbx, rdx
0x18001ab4a  mov     rdi, rcx
0x18001ab4d  test    r13, r13
0x18001ab50  jnz     short loc_18001AB75
0x18001ab52  lea     edx, [r13+1Bh]; void *
0x18001ab56  mov     rcx, [rbp+78h]; this
0x18001ab5a  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18001ab61  mov     ebx, 80070057h
0x18001ab66  mov     r9d, ebx; char *
0x18001ab69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ab6e  mov     eax, ebx
0x18001ab70  jmp     loc_18001AEEB
0x18001ab75  test    r12, r12
0x18001ab78  jnz     short loc_18001AB81
0x18001ab7a  lea     edx, [r12+1Ch]
0x18001ab7f  jmp     short loc_18001AB56
0x18001ab81  test    rbx, rbx
0x18001ab84  jnz     short loc_18001AB8B
0x18001ab86  lea     edx, [rbx+1Dh]
0x18001ab89  jmp     short loc_18001AB56
0x18001ab8b  test    r15, r15
0x18001ab8e  jnz     short loc_18001AB96
0x18001ab90  lea     edx, [r15+1Eh]
0x18001ab94  jmp     short loc_18001AB56
0x18001ab96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x18001ab9d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x18001aba2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001aba6  test    al, al
0x18001aba8  jz      loc_18001AC4C
0x18001abae  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001abb3  mov     rcx, [rax+8]
0x18001abb7  mov     eax, [rcx]
0x18001abb9  cmp     eax, 4
0x18001abbc  jbe     loc_18001AC9C
0x18001abc2  lea     rax, aEnter_0; "Enter"
0x18001abc9  mov     [rsp+170h+var_128], rdi
0x18001abce  mov     [rsp+170h+var_130], rax
0x18001abd3  mov     rax, rsi
0x18001abd6  inc     rax
0x18001abd9  cmp     [rbx+rax*2], r14w
0x18001abde  jnz     short loc_18001ABD6
0x18001abe0  lea     eax, ds:2[rax*2]
0x18001abe7  mov     [rbp+70h+var_60], rbx
0x18001abeb  mov     [rbp+70h+var_58], eax
0x18001abee  lea     rdx, dword_180088E9C
0x18001abf5  lea     rax, [rsp+170h+var_130]
0x18001abfa  mov     [rbp+70h+var_54], r14d
0x18001abfe  mov     [rbp+70h+var_70], rax
0x18001ac02  xor     r9d, r9d
0x18001ac05  lea     rax, [rsp+170h+var_128]
0x18001ac0a  mov     [rbp+70h+var_68], 8
0x18001ac12  mov     [rbp+70h+var_80], rax
0x18001ac16  xor     r8d, r8d
0x18001ac19  lea     rax, aCmidi2ksaggreg_2; "CMidi2KSAggregateMidiBidi::Initialize"
0x18001ac20  mov     [rbp+70h+var_78], 8
0x18001ac28  mov     [rbp+70h+var_90], rax
0x18001ac2c  lea     rax, [rbp+70h+var_B0]
0x18001ac30  mov     [rsp+170h+var_148], rax
0x18001ac35  mov     [rsp+170h+var_150], 6
0x18001ac3d  mov     [rbp+70h+var_88], 26h ; '&'
0x18001ac45  call    _tlgWriteTransfer_EventWriteTransfer
0x18001ac4a  jmp     short loc_18001AC9C
0x18001ac4c  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001ac51  mov     rcx, [rax+8]
0x18001ac55  mov     eax, [rcx]
0x18001ac57  cmp     eax, 4
0x18001ac5a  jbe     short loc_18001AC9C
0x18001ac5c  lea     rax, aCmidi2ksaggreg_2; "CMidi2KSAggregateMidiBidi::Initialize"
0x18001ac63  mov     [rsp+170h+var_128], rbx
0x18001ac68  mov     [rsp+170h+var_120], rax
0x18001ac6d  lea     rdx, byte_180088E4F
0x18001ac74  lea     rax, [rsp+170h+var_128]
0x18001ac79  mov     [rsp+170h+var_130], rdi
0x18001ac7e  mov     [rsp+170h+var_140], rax
0x18001ac83  lea     rax, [rsp+170h+var_130]
0x18001ac88  mov     [rsp+170h+var_148], rax
0x18001ac8d  lea     rax, [rsp+170h+var_120]
0x18001ac92  mov     qword ptr [rsp+170h+var_150], rax
0x18001ac97  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001ac9c  xorps   xmm0, xmm0
0x18001ac9f  mov     [rbp+70h+var_E0], r14
0x18001aca3  movups  [rbp+70h+var_F0], xmm0
0x18001aca7  mov     [rbp+70h+var_D8], r14
0x18001acab  inc     rsi
0x18001acae  cmp     [rbx+rsi*2], r14w
0x18001acb3  jnz     short loc_18001ACAB
0x18001acb5  mov     r8, rsi
0x18001acb8  lea     rcx, [rbp+70h+var_F0]
0x18001acbc  mov     rdx, rbx
0x18001acbf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001acc4  lea     rdx, [rbp+70h+var_F0]
0x18001acc8  lea     rcx, [rsp+170h+var_110]
0x18001accd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001acd2  mov     rdx, rax
0x18001acd5  lea     rcx, [rbp+70h+var_D0]
0x18001acd9  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x18001acde  lea     rsi, [rdi+10h]
0x18001ace2  mov     rcx, rsi
0x18001ace5  lea     rdx, [rbp+70h+var_D0]
0x18001ace9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001acee  lea     rcx, [rbp+70h+var_D0]; void *
0x18001acf2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001acf7  lea     rcx, [rbp+70h+var_F0]; void *
0x18001acfb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ad00  mov     rax, r14
0x18001ad03  mov     ecx, 60h ; '`'; Size
0x18001ad08  xchg    rax, [rdi+30h]
0x18001ad0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ad11  xor     edx, edx; Val
0x18001ad13  mov     rcx, rax; void *
0x18001ad16  mov     r14, rax
0x18001ad19  lea     r8d, [rdx+60h]; Size
0x18001ad1d  call    memset_0
0x18001ad22  xor     r8d, r8d; Flags
0x18001ad25  xor     edx, edx; dwSpinCount
0x18001ad27  mov     rcx, r14; lpCriticalSection
0x18001ad2a  call    cs:__imp_InitializeCriticalSectionEx
0x18001ad30  mov     ecx, 30h ; '0'; Size
0x18001ad35  mov     qword ptr [r14+30h], 0
0x18001ad3d  mov     qword ptr [r14+38h], 0
0x18001ad45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ad4a  mov     ecx, 30h ; '0'; Size
0x18001ad4f  mov     [rax], rax
0x18001ad52  mov     [rax+8], rax
0x18001ad56  mov     [rax+10h], rax
0x18001ad5a  mov     word ptr [rax+18h], 101h
0x18001ad60  mov     [r14+30h], rax
0x18001ad64  mov     qword ptr [r14+40h], 0
0x18001ad6c  mov     qword ptr [r14+48h], 0
0x18001ad74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ad79  mov     ecx, 48h ; 'H'; Size
0x18001ad7e  mov     [rax], rax
0x18001ad81  mov     [rax+8], rax
0x18001ad85  mov     [rax+10h], rax
0x18001ad89  mov     word ptr [rax+18h], 101h
0x18001ad8f  mov     [r14+40h], rax
0x18001ad93  mov     qword ptr [r14+50h], 0
0x18001ad9b  mov     qword ptr [r14+58h], 0
0x18001ada3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ada8  mov     r9, r15
0x18001adab  mov     r8d, 2
0x18001adb1  mov     rdx, rbx
0x18001adb4  mov     rcx, r14
0x18001adb7  mov     [rax], rax
0x18001adba  mov     [rax+8], rax
0x18001adbe  mov     [rax+10h], rax
0x18001adc2  mov     word ptr [rax+18h], 101h
0x18001adc8  mov     [r14+50h], rax
0x18001adcc  mov     rax, [rbp+70h+arg_28]
0x18001add3  mov     [rsp+170h+var_140], rax
0x18001add8  mov     [rsp+170h+var_148], r13
0x18001addd  mov     qword ptr [rsp+170h+var_150], r12; int
0x18001ade2  call    ?Initialize@CMidi2KSAggregateMidi@@QEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_J@Z; CMidi2KSAggregateMidi::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64)
0x18001ade7  mov     ebx, eax
0x18001ade9  test    eax, eax
0x18001adeb  jns     short loc_18001AE3B
0x18001aded  mov     rcx, [rbp+78h]; this
0x18001adf1  lea     r8, aAvcoreMidi2Tra_1; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18001adf8  mov     r9d, eax; char *
0x18001adfb  mov     edx, 49h ; 'I'; void *
0x18001ae00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae05  lea     rcx, [r14+50h]
0x18001ae09  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>(void)
0x18001ae0e  lea     rcx, [r14+40h]
0x18001ae12  call    ??1?$_Tree@V?$_Tmap_traits@EV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(void)
0x18001ae17  lea     rcx, [r14+30h]
0x18001ae1b  call    ??1?$_Tree@V?$_Tmap_traits@EV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(void)
0x18001ae20  mov     rcx, r14; lpCriticalSection
0x18001ae23  call    cs:__imp_DeleteCriticalSection
0x18001ae29  mov     edx, 60h ; '`'
0x18001ae2e  mov     rcx, r14; Block
0x18001ae31  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ae36  jmp     loc_18001AB6E
0x18001ae3b  mov     rbx, [rdi+38h]
0x18001ae3f  mov     [rdi+38h], r14
0x18001ae43  test    rbx, rbx
0x18001ae46  jz      short loc_18001AE79
0x18001ae48  lea     rcx, [rbx+50h]
0x18001ae4c  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>(void)
0x18001ae51  lea     rcx, [rbx+40h]
0x18001ae55  call    ??1?$_Tree@V?$_Tmap_traits@EV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(void)
0x18001ae5a  lea     rcx, [rbx+30h]
0x18001ae5e  call    ??1?$_Tree@V?$_Tmap_traits@EV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(void)
0x18001ae63  mov     rcx, rbx; lpCriticalSection
0x18001ae66  call    cs:__imp_DeleteCriticalSection
0x18001ae6c  mov     edx, 60h ; '`'
0x18001ae71  mov     rcx, rbx; Block
0x18001ae74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ae79  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001ae7e  mov     rcx, [rax+8]
0x18001ae82  mov     eax, [rcx]
0x18001ae84  cmp     eax, 4
0x18001ae87  jbe     short loc_18001AEE9
0x18001ae89  cmp     qword ptr [rsi+18h], 7
0x18001ae8e  jbe     short loc_18001AE93
0x18001ae90  mov     rsi, [rsi]
0x18001ae93  lea     rax, aInitialization; "Initialization complete"
0x18001ae9a  mov     [rsp+170h+var_120], rsi
0x18001ae9f  mov     [rsp+170h+var_128], rax
0x18001aea4  lea     rdx, byte_180088DF9
0x18001aeab  lea     rax, aCmidi2ksaggreg_2; "CMidi2KSAggregateMidiBidi::Initialize"
0x18001aeb2  mov     [rsp+170h+var_130], rdi
0x18001aeb7  mov     [rsp+170h+var_118], rax
0x18001aebc  lea     rax, [rsp+170h+var_120]
0x18001aec1  mov     [rsp+170h+var_138], rax
0x18001aec6  lea     rax, [rsp+170h+var_128]
0x18001aecb  mov     [rsp+170h+var_140], rax
0x18001aed0  lea     rax, [rsp+170h+var_130]
0x18001aed5  mov     [rsp+170h+var_148], rax
0x18001aeda  lea     rax, [rsp+170h+var_118]
0x18001aedf  mov     qword ptr [rsp+170h+var_150], rax
0x18001aee4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001aee9  xor     eax, eax
0x18001aeeb  mov     rcx, [rbp+70h+var_50]
0x18001aeef  xor     rcx, rsp; StackCookie
0x18001aef2  call    __security_check_cookie
0x18001aef7  add     rsp, 138h
0x18001aefe  pop     r15
0x18001af00  pop     r14
0x18001af02  pop     r13
0x18001af04  pop     r12
0x18001af06  pop     rdi
0x18001af07  pop     rsi
0x18001af08  pop     rbx
0x18001af09  pop     rbp
0x18001af0a  retn
```
