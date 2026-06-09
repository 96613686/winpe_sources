# CMidiClientManager::GetMidiScheduler(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &)

- ea: `0x14001a084`
- end: `0x14001a67a`
- name: `?GetMidiScheduler@CMidiClientManager@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@AEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@11@Z`
- size: `1526`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400152d0`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x1400060d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14001209c`
- `0x140012f48`
- `0x140013a38`
- `0x14001a084`
- `0x14001e990`
- `0x14001ea58`
- `0x14003f730`
- `0x14005a010`

## string_xrefs

- `0x14001a0ce`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001a3ba`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001a452`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x14001a4ce`: `avcore\midi2\service\exe\midiclientmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CMidiClientManager::GetMidiScheduler(__int64 a1, __int64 a2, _QWORD *a3, char **a4, __int64 *a5)
{
  unsigned int v7; // ebx
  _DWORD *v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r9
  int *v12; // rax
  __int64 v13; // rdx
  int *i; // rbx
  int *v15; // rdi
  char IsEnabled; // al
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 v19; // rbx
  int *v20; // rcx
  __int64 v21; // rdi
  _DWORD *v22; // rbx
  __int64 v23; // r8
  __int64 v24; // r9
  char **v25; // rax
  const wchar_t *v26; // rdi
  int v27; // eax
  char **v28; // rdx
  unsigned int v29; // esi
  int v30; // eax
  __int64 v31; // rsi
  _DWORD *v32; // rsi
  __int64 v33; // r8
  __int64 v34; // r9
  char **v35; // rax
  int v36; // [rsp+20h] [rbp-91h]
  int v37; // [rsp+20h] [rbp-91h]
  int v38[2]; // [rsp+40h] [rbp-71h] BYREF
  __int64 v39; // [rsp+48h] [rbp-69h] BYREF
  const char *v40; // [rsp+50h] [rbp-61h] BYREF
  char **v41; // [rsp+58h] [rbp-59h] BYREF
  GUID Buf1; // [rsp+60h] [rbp-51h] BYREF
  __int64 v43; // [rsp+70h] [rbp-41h]
  __int64 v44; // [rsp+78h] [rbp-39h]
  char *v45[3]; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int64 v46; // [rsp+98h] [rbp-19h]
  int v47[2]; // [rsp+A0h] [rbp-11h] BYREF
  int *v48; // [rsp+A8h] [rbp-9h]
  unsigned __int64 v49; // [rsp+B8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v41 = a4;
  if ( !*a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35A,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x80070057LL,
      v36);
    return v7;
  }
  v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    std::wstring::wstring((__int64)v47, *a3 + 16LL);
    v12 = v47;
    if ( v49 > 7 )
      v12 = *(int **)v47;
    v39 = (__int64)v12;
    *(_QWORD *)v38 = L"Enter";
    v40 = (const char *)a1;
    *(_QWORD *)&Buf1.Data1 = "CMidiClientManager::GetMidiScheduler";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v9,
      (__int64)word_1400879AA,
      v10,
      v11,
      &Buf1,
      (__int64)&v40,
      v38,
      &v39);
    std::wstring::~wstring((char **)v47);
  }
  v39 = 0;
  std::wstring::wstring((__int64)v45, *a3 + 16LL);
  std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>>,1>>::equal_range(
    a1 + 104,
    v47,
    v45);
  std::wstring::~wstring(v45);
  i = *(int **)v47;
  while ( 1 )
  {
    v15 = i;
    if ( i == v48 )
      goto LABEL_30;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                  v13);
    v18 = *((_QWORD *)i + 8);
    if ( !IsEnabled )
      break;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                            v17) )
    {
      if ( *(_QWORD *)(v18 + 120) == *a3 )
      {
        v19 = *((_QWORD *)i + 8);
        Buf1 = *(GUID *)(v19 + 136);
        if ( !memcmp_0(&Buf1, &GUID_a42cde44_7fa9_4597_a8ee_b40b96bcddb1, 0x10u) )
        {
          v39 = v19;
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
          goto LABEL_29;
        }
      }
    }
LABEL_18:
    i = (int *)*((_QWORD *)v15 + 2);
    if ( *((_BYTE *)i + 25) )
    {
      for ( i = (int *)*((_QWORD *)v15 + 1); !*((_BYTE *)i + 25) && v15 == *((int **)i + 2); i = (int *)*((_QWORD *)i + 1) )
        v15 = i;
    }
    else
    {
      v20 = *(int **)i;
      if ( !*(_BYTE *)(*(_QWORD *)i + 25LL) )
      {
        do
        {
          i = v20;
          v20 = *(int **)v20;
        }
        while ( !*((_BYTE *)v20 + 25) );
      }
    }
  }
  Buf1 = *(GUID *)(v18 + 136);
  if ( memcmp_0(&Buf1, &GUID_a42cde44_7fa9_4597_a8ee_b40b96bcddb1, 0x10u) )
    goto LABEL_18;
  v19 = *((_QWORD *)i + 8);
  v39 = v19;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
LABEL_29:
  v21 = v19;
  if ( v19 )
    goto LABEL_63;
LABEL_30:
  v22 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v22 > 4u )
  {
    std::wstring::wstring((__int64)v45, *a3 + 16LL);
    v25 = v45;
    if ( v46 > 7 )
      v25 = (char **)v45[0];
    *(_QWORD *)&Buf1.Data1 = v25;
    v40 = (const char *)L"Creating new scheduler";
    *(_QWORD *)v38 = a1;
    *(_QWORD *)v47 = "CMidiClientManager::GetMidiScheduler";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v22,
      (__int64)byte_140087ED5,
      v23,
      v24,
      v47,
      (__int64)v38,
      &v40,
      &Buf1);
    std::wstring::~wstring(v45);
  }
  v44 = 0xFF00000001LL;
  v43 = 0x200000002LL;
  Buf1 = GUID_a42cde44_7fa9_4597_a8ee_b40b96bcddb1;
  *(_QWORD *)v38 = 0;
  v26 = *(const wchar_t **)(a1 + 40);
  *(_QWORD *)v47 = v26;
  if ( v26 )
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v26 + 8LL))(v26);
  *(_QWORD *)v38 = 0;
  v27 = Microsoft::WRL::Details::MakeAndInitialize<CMidiTransformPipe,CMidiTransformPipe,>(v38);
  v7 = v27;
  if ( v27 >= 0 )
  {
    v19 = *(_QWORD *)v38;
    std::wstring::wstring((__int64)v45, *a3 + 16LL);
    v28 = v45;
    if ( v46 > 7 )
      v28 = (char **)v45[0];
    v29 = CMidiTransformPipe::Initialize(v19, (__int64)v28, (__int64)a3, (__int64)&Buf1, a1 + 120, v26);
    std::wstring::~wstring(v45);
    if ( (v29 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A8,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)v29,
        v37);
      if ( v26 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      return v29;
    }
    v39 = v19;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
    v30 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v19 + 56LL))(v19, v41);
    v29 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B3,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v30,
        v37);
      if ( v26 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return v29;
    }
    std::wstring::wstring((__int64)v45, *a3 + 16LL);
    std::multimap<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>::emplace<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy> &>(
      (__int64 *)(a1 + 104),
      &v41,
      (__int64)v45,
      (__int64 *)v38);
    std::wstring::~wstring(v45);
    if ( v26 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v21 = v19;
LABEL_63:
    v31 = *a5;
    *a5 = v21;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v32 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v32 > 4u )
    {
      std::wstring::wstring((__int64)v45, *a3 + 16LL);
      v35 = v45;
      if ( v46 > 7 )
        v35 = (char **)v45[0];
      v41 = v35;
      *(_QWORD *)v47 = L"Exit";
      *(_QWORD *)&Buf1.Data1 = a1;
      v40 = "CMidiClientManager::GetMidiScheduler";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v32,
        (__int64)byte_1400880FD,
        v33,
        v34,
        &v40,
        (__int64)&Buf1,
        v47,
        &v41);
      std::wstring::~wstring(v45);
    }
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A6,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
    (const char *)(unsigned int)v27,
    v36);
  if ( v26 )
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v26 + 16LL))(v26);
  if ( *(_QWORD *)v38 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v38 + 16LL))(*(_QWORD *)v38);
  return v7;
}

```

## disassembly

```asm
0x14001a084  mov     [rsp-8+arg_8], rbx
0x14001a089  push    rbp
0x14001a08a  push    rsi
0x14001a08b  push    rdi
0x14001a08c  push    r12
0x14001a08e  push    r13
0x14001a090  push    r14
0x14001a092  push    r15
0x14001a094  lea     rbp, [rsp-1Fh]
0x14001a099  sub     rsp, 0D0h
0x14001a0a0  mov     rax, cs:__security_cookie
0x14001a0a7  xor     rax, rsp
0x14001a0aa  mov     [rbp+4Fh+var_40], rax
0x14001a0ae  mov     [rbp+4Fh+var_A8], r9
0x14001a0b2  mov     r14, r8
0x14001a0b5  mov     r15, rcx
0x14001a0b8  mov     r12, [rbp+4Fh+arg_20]
0x14001a0bc  cmp     qword ptr [r8], 0
0x14001a0c0  jnz     short loc_14001A0E6
0x14001a0c2  mov     rcx, [rbp+57h]; this
0x14001a0c6  mov     ebx, 80070057h
0x14001a0cb  mov     r9d, ebx; char *
0x14001a0ce  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001a0d5  mov     edx, 35Ah; void *
0x14001a0da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a0df  mov     eax, ebx
0x14001a0e1  jmp     loc_14001A653
0x14001a0e6  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001a0eb  mov     rbx, [rax+8]
0x14001a0ef  mov     eax, [rbx]
0x14001a0f1  lea     rsi, aCmidiclientman_3; "CMidiClientManager::GetMidiScheduler"
0x14001a0f8  cmp     eax, 4
0x14001a0fb  jbe     short loc_14001A16E
0x14001a0fd  mov     rdx, [r14]
0x14001a100  add     rdx, 10h
0x14001a104  lea     rcx, [rbp+4Fh+var_60]
0x14001a108  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001a10d  lea     rax, [rbp+4Fh+var_60]
0x14001a111  cmp     [rbp+4Fh+var_48], 7
0x14001a116  cmova   rax, qword ptr [rbp+4Fh+var_60]
0x14001a11b  mov     [rbp+4Fh+var_B8], rax
0x14001a11f  lea     rax, aEnter; "Enter"
0x14001a126  mov     qword ptr [rbp+4Fh+var_C0], rax
0x14001a12a  mov     [rbp+4Fh+var_B0], r15
0x14001a12e  mov     qword ptr [rbp+4Fh+Buf1], rsi
0x14001a132  lea     rax, [rbp+4Fh+var_B8]
0x14001a136  mov     [rsp+100h+var_C8], rax
0x14001a13b  lea     rax, [rbp+4Fh+var_C0]
0x14001a13f  mov     [rsp+100h+var_D0], rax
0x14001a144  lea     rax, [rbp+4Fh+var_B0]
0x14001a148  mov     [rsp+100h+var_D8], rax
0x14001a14d  lea     rax, [rbp+4Fh+Buf1]
0x14001a151  mov     [rsp+100h+var_E0], rax
0x14001a156  lea     rdx, word_1400879AA
0x14001a15d  mov     rcx, rbx
0x14001a160  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001a165  lea     rcx, [rbp+4Fh+var_60]; void *
0x14001a169  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001a16e  mov     [rbp+4Fh+var_B8], 0
0x14001a176  mov     rdx, [r14]
0x14001a179  add     rdx, 10h
0x14001a17d  lea     rcx, [rbp+4Fh+var_80]
0x14001a181  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001a186  lea     r8, [rbp+4Fh+var_80]
0x14001a18a  lea     rdx, [rbp+4Fh+var_60]
0x14001a18e  lea     rcx, [r15+68h]
0x14001a192  call    ?equal_range@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>>,1>>::equal_range(std::wstring const &)
0x14001a197  lea     rcx, [rbp+4Fh+var_80]; void *
0x14001a19b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001a1a0  mov     rbx, qword ptr [rbp+4Fh+var_60]
0x14001a1a4  mov     rdi, rbx
0x14001a1a7  cmp     rbx, [rbp+4Fh+var_58]
0x14001a1ab  jz      loc_14001A2C2
0x14001a1b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x14001a1b8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x14001a1bd  mov     rsi, [rbx+40h]
0x14001a1c1  test    al, al
0x14001a1c3  jz      short loc_14001A226
0x14001a1c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x14001a1cc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x14001a1d1  test    al, al
0x14001a1d3  jz      short loc_14001A24C
0x14001a1d5  mov     rax, [r14]
0x14001a1d8  cmp     [rsi+78h], rax
0x14001a1dc  jnz     short loc_14001A24C
0x14001a1de  mov     rbx, [rbx+40h]
0x14001a1e2  movups  xmm0, xmmword ptr [rbx+88h]
0x14001a1e9  movdqu  [rbp+4Fh+Buf1], xmm0
0x14001a1ee  mov     r8d, 10h; Size
0x14001a1f4  lea     rdx, _GUID_a42cde44_7fa9_4597_a8ee_b40b96bcddb1; Buf2
0x14001a1fb  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x14001a1ff  call    memcmp_0
0x14001a204  test    eax, eax
0x14001a206  jnz     short loc_14001A24C
0x14001a208  mov     [rbp+4Fh+var_B8], rbx
0x14001a20c  test    rbx, rbx
0x14001a20f  jz      short loc_14001A221
0x14001a211  mov     rax, [rbx]
0x14001a214  mov     rcx, rbx
0x14001a217  mov     rax, [rax+8]
0x14001a21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a220  nop
0x14001a221  jmp     loc_14001A2B6
0x14001a226  movups  xmm0, xmmword ptr [rsi+88h]
0x14001a22d  movdqu  [rbp+4Fh+Buf1], xmm0
0x14001a232  mov     r8d, 10h; Size
0x14001a238  lea     rdx, _GUID_a42cde44_7fa9_4597_a8ee_b40b96bcddb1; Buf2
0x14001a23f  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x14001a243  call    memcmp_0
0x14001a248  test    eax, eax
0x14001a24a  jz      short loc_14001A299
0x14001a24c  mov     rbx, [rdi+10h]
0x14001a250  cmp     byte ptr [rbx+19h], 0
0x14001a254  jz      short loc_14001A278
0x14001a256  mov     rbx, [rdi+8]
0x14001a25a  jmp     short loc_14001A26D
0x14001a25c  cmp     rdi, [rbx+10h]
0x14001a260  jnz     loc_14001A1A4
0x14001a266  mov     rdi, rbx
0x14001a269  mov     rbx, [rbx+8]
0x14001a26d  cmp     byte ptr [rbx+19h], 0
0x14001a271  jz      short loc_14001A25C
0x14001a273  jmp     loc_14001A1A4
0x14001a278  mov     rcx, [rbx]
0x14001a27b  cmp     byte ptr [rcx+19h], 0
0x14001a27f  jnz     loc_14001A1A4
0x14001a285  mov     rbx, rcx
0x14001a288  mov     rax, [rcx]
0x14001a28b  mov     rcx, rax
0x14001a28e  cmp     byte ptr [rax+19h], 0
0x14001a292  jz      short loc_14001A285
0x14001a294  jmp     loc_14001A1A4
0x14001a299  mov     rbx, [rbx+40h]
0x14001a29d  mov     [rbp+4Fh+var_B8], rbx
0x14001a2a1  test    rbx, rbx
0x14001a2a4  jz      short loc_14001A2B6
0x14001a2a6  mov     rax, [rbx]
0x14001a2a9  mov     rcx, rbx
0x14001a2ac  mov     rax, [rax+8]
0x14001a2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a2b5  nop
0x14001a2b6  mov     rdi, rbx
0x14001a2b9  test    rbx, rbx
0x14001a2bc  jnz     loc_14001A582
0x14001a2c2  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001a2c7  mov     rbx, [rax+8]
0x14001a2cb  mov     eax, [rbx]
0x14001a2cd  cmp     eax, 4
0x14001a2d0  jbe     short loc_14001A34A
0x14001a2d2  mov     rdx, [r14]
0x14001a2d5  add     rdx, 10h
0x14001a2d9  lea     rcx, [rbp+4Fh+var_80]
0x14001a2dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001a2e2  lea     rax, [rbp+4Fh+var_80]
0x14001a2e6  cmp     [rbp+4Fh+var_68], 7
0x14001a2eb  cmova   rax, [rbp+4Fh+var_80]
0x14001a2f0  mov     qword ptr [rbp+4Fh+Buf1], rax
0x14001a2f4  lea     rax, aCreatingNewSch; "Creating new scheduler"
0x14001a2fb  mov     [rbp+4Fh+var_B0], rax
0x14001a2ff  mov     qword ptr [rbp+4Fh+var_C0], r15
0x14001a303  lea     rax, aCmidiclientman_3; "CMidiClientManager::GetMidiScheduler"
0x14001a30a  mov     qword ptr [rbp+4Fh+var_60], rax
0x14001a30e  lea     rax, [rbp+4Fh+Buf1]
0x14001a312  mov     [rsp+100h+var_C8], rax
0x14001a317  lea     rax, [rbp+4Fh+var_B0]
0x14001a31b  mov     [rsp+100h+var_D0], rax
0x14001a320  lea     rax, [rbp+4Fh+var_C0]
0x14001a324  mov     [rsp+100h+var_D8], rax
0x14001a329  lea     rax, [rbp+4Fh+var_60]
0x14001a32d  mov     [rsp+100h+var_E0], rax; int
0x14001a332  lea     rdx, byte_140087ED5
0x14001a339  mov     rcx, rbx
0x14001a33c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14001a341  lea     rcx, [rbp+4Fh+var_80]; void *
0x14001a345  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001a34a  xorps   xmm0, xmm0
0x14001a34d  movups  [rbp+4Fh+Buf1+4], xmm0
0x14001a351  movups  [rbp+4Fh+var_90], xmm0
0x14001a355  mov     dword ptr [rbp+4Fh+var_90+8], 1
0x14001a35c  mov     eax, 2
0x14001a361  mov     dword ptr [rbp+4Fh+var_90], eax
0x14001a364  mov     dword ptr [rbp+4Fh+var_90+4], eax
0x14001a367  movups  xmm0, xmmword ptr cs:_GUID_a42cde44_7fa9_4597_a8ee_b40b96bcddb1.Data1
0x14001a36e  movdqu  [rbp+4Fh+Buf1], xmm0
0x14001a373  mov     byte ptr [rbp+4Fh+var_90+0Ch], 0FFh
0x14001a377  mov     qword ptr [rbp+4Fh+var_C0], 0
0x14001a37f  mov     rdi, [r15+28h]
0x14001a383  mov     qword ptr [rbp+4Fh+var_60], rdi
0x14001a387  test    rdi, rdi
0x14001a38a  jz      short loc_14001A39C
0x14001a38c  mov     rax, [rdi]
0x14001a38f  mov     rcx, rdi
0x14001a392  mov     rax, [rax+8]
0x14001a396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a39b  nop
0x14001a39c  mov     qword ptr [rbp+4Fh+var_C0], 0
0x14001a3a4  lea     rcx, [rbp+4Fh+var_C0]
0x14001a3a8  call    ??$MakeAndInitialize@VCMidiTransformPipe@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCMidiTransformPipe@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMidiTransformPipe,CMidiTransformPipe,>(CMidiTransformPipe * *)
0x14001a3ad  mov     ebx, eax
0x14001a3af  test    eax, eax
0x14001a3b1  jns     short loc_14001A3FC
0x14001a3b3  mov     rcx, [rbp+57h]; this
0x14001a3b7  mov     r9d, eax; char *
0x14001a3ba  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001a3c1  mov     edx, 3A6h; void *
0x14001a3c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a3cb  nop
0x14001a3cc  test    rdi, rdi
0x14001a3cf  jz      short loc_14001A3E1
0x14001a3d1  mov     rax, [rdi]
0x14001a3d4  mov     rcx, rdi
0x14001a3d7  mov     rax, [rax+10h]
0x14001a3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a3e0  nop
0x14001a3e1  mov     rcx, qword ptr [rbp+4Fh+var_C0]
0x14001a3e5  test    rcx, rcx
0x14001a3e8  jz      short loc_14001A3F7
0x14001a3ea  mov     rax, [rcx]
0x14001a3ed  mov     rax, [rax+10h]
0x14001a3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a3f6  nop
0x14001a3f7  jmp     loc_14001A0DF
0x14001a3fc  mov     rbx, qword ptr [rbp+4Fh+var_C0]
0x14001a400  mov     rdx, [r14]
0x14001a403  add     rdx, 10h
0x14001a407  lea     rcx, [rbp+4Fh+var_80]
0x14001a40b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001a410  nop
0x14001a411  lea     rdx, [rbp+4Fh+var_80]
0x14001a415  cmp     [rbp+4Fh+var_68], 7
0x14001a41a  cmova   rdx, [rbp+4Fh+var_80]
0x14001a41f  lea     rax, [r15+78h]
0x14001a423  mov     [rsp+100h+var_D8], rdi; __int64
0x14001a428  mov     [rsp+100h+var_E0], rax; int
0x14001a42d  lea     r9, [rbp+4Fh+Buf1]
0x14001a431  mov     r8, r14
0x14001a434  mov     rcx, rbx; int
0x14001a437  call    ?Initialize@CMidiTransformPipe@@QEAAJPEBGAEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@PEAUMIDISRV_TRANSFORMCREATION_PARAMS@@PEAKPEAUIMidiDeviceManager@@@Z; CMidiTransformPipe::Initialize(ushort const *,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,MIDISRV_TRANSFORMCREATION_PARAMS *,ulong *,IMidiDeviceManager *)
0x14001a43c  mov     esi, eax
0x14001a43e  lea     rcx, [rbp+4Fh+var_80]; void *
0x14001a442  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001a447  test    esi, esi
0x14001a449  jns     short loc_14001A495
0x14001a44b  mov     rcx, [rbp+57h]; this
0x14001a44f  mov     r9d, esi; char *
0x14001a452  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001a459  mov     edx, 3A8h; void *
0x14001a45e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a463  nop
0x14001a464  test    rdi, rdi
0x14001a467  jz      short loc_14001A479
0x14001a469  mov     rax, [rdi]
0x14001a46c  mov     rcx, rdi
0x14001a46f  mov     rax, [rax+10h]
0x14001a473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a478  nop
0x14001a479  test    rbx, rbx
0x14001a47c  jz      short loc_14001A48E
0x14001a47e  mov     rax, [rbx]
0x14001a481  mov     rcx, rbx
0x14001a484  mov     rax, [rax+10h]
0x14001a488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a48d  nop
0x14001a48e  mov     eax, esi
0x14001a490  jmp     loc_14001A653
0x14001a495  mov     [rbp+4Fh+var_B8], rbx
0x14001a499  test    rbx, rbx
0x14001a49c  jz      short loc_14001A4AE
0x14001a49e  mov     rax, [rbx]
0x14001a4a1  mov     rcx, rbx
0x14001a4a4  mov     rax, [rax+8]
0x14001a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a4ad  nop
0x14001a4ae  mov     rax, [rbx]
0x14001a4b1  mov     rdx, [rbp+4Fh+var_A8]
0x14001a4b5  mov     rcx, rbx
0x14001a4b8  mov     rax, [rax+38h]
0x14001a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a4c1  mov     esi, eax
0x14001a4c3  test    eax, eax
0x14001a4c5  jns     short loc_14001A524
0x14001a4c7  mov     rcx, [rbp+57h]; this
0x14001a4cb  mov     r9d, eax; char *
0x14001a4ce  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x14001a4d5  mov     edx, 3B3h; void *
0x14001a4da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a4df  nop
0x14001a4e0  test    rdi, rdi
0x14001a4e3  jz      short loc_14001A4F5
0x14001a4e5  mov     rax, [rdi]
0x14001a4e8  mov     rcx, rdi
0x14001a4eb  mov     rax, [rax+10h]
0x14001a4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a4f4  nop
0x14001a4f5  test    rbx, rbx
0x14001a4f8  jz      short loc_14001A50A
0x14001a4fa  mov     rax, [rbx]
0x14001a4fd  mov     rcx, rbx
0x14001a500  mov     rax, [rax+10h]
0x14001a504  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
