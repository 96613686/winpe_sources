# CMidiClientManager::GetMidiProtocolDownscalerTransform(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &)

- ea: `0x140019aac`
- end: `0x14001a07d`
- name: `?GetMidiProtocolDownscalerTransform@CMidiClientManager@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@AEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@11@Z`
- size: `1489`
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
- `0x140019aac`
- `0x14001e990`
- `0x14001ea58`
- `0x14003f730`
- `0x14005a010`

## string_xrefs

- `0x140019afb`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140019cfe`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140019d33`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140019dbc`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140019e54`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140019ecf`: `avcore\midi2\service\exe\midiclientmanager.cpp`
- `0x140019b1e`: `CMidiClientManager::GetMidiProtocolDownscalerTransform`
- `0x140019ff2`: `CMidiClientManager::GetMidiProtocolDownscalerTransform`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMidiClientManager::GetMidiProtocolDownscalerTransform(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 *a5)
{
  unsigned int v8; // ebx
  _DWORD *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r9
  char **v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 *i; // rdi
  char IsEnabled; // al
  __int64 v18; // rsi
  __int64 *v19; // rax
  __int64 *v20; // rcx
  const wchar_t *v21; // rdi
  int v22; // eax
  char **v23; // rdx
  unsigned int v24; // esi
  int v25; // eax
  __int64 v26; // rdi
  _DWORD *v27; // rdi
  __int64 v28; // r8
  __int64 v29; // r9
  char **v30; // rax
  int v31; // [rsp+28h] [rbp-81h]
  int v32; // [rsp+28h] [rbp-81h]
  const char *v33; // [rsp+48h] [rbp-61h] BYREF
  __int128 Buf1; // [rsp+50h] [rbp-59h] BYREF
  GUID Buf2; // [rsp+60h] [rbp-49h] BYREF
  int v36; // [rsp+70h] [rbp-39h]
  int v37; // [rsp+74h] [rbp-35h]
  int v38; // [rsp+78h] [rbp-31h]
  char v39; // [rsp+7Ch] [rbp-2Dh]
  __int16 v40; // [rsp+7Dh] [rbp-2Ch]
  char v41; // [rsp+7Fh] [rbp-2Ah]
  int v42[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 **v43; // [rsp+88h] [rbp-21h]
  char *v44[3]; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v45; // [rsp+A8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+57h]

  if ( !*a3 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x80070057LL,
      v31);
    return v8;
  }
  v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v10 > 4u )
  {
    std::wstring::wstring((__int64)v44, *a3 + 16LL);
    v13 = v44;
    if ( v45 > 7 )
      v13 = (char **)v44[0];
    v33 = (const char *)v13;
    *(_QWORD *)&Buf1 = L"Enter";
    *(_QWORD *)&Buf2.Data1 = a1;
    *(_QWORD *)v42 = "CMidiClientManager::GetMidiProtocolDownscalerTransform";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v10,
      (__int64)&dword_14008770C,
      v11,
      v12,
      v42,
      (__int64)&Buf2,
      &Buf1,
      &v33);
    std::wstring::~wstring(v44);
  }
  v14 = 0;
  v33 = 0;
  Buf2 = GUID_dc638b31_cf31_48ed_9e79_02740bf5d013;
  std::wstring::wstring((__int64)v44, *a3 + 16LL);
  std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>>,1>>::equal_range(
    a1 + 104,
    v42,
    v44);
  std::wstring::~wstring(v44);
  i = *(__int64 **)v42;
  while ( i != (__int64 *)v43 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                  v15);
    v18 = i[8];
    if ( IsEnabled )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                               `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                               v15) )
        goto LABEL_22;
      if ( *(_QWORD *)(v18 + 120) != *a3 )
        goto LABEL_22;
      v18 = i[8];
      if ( *(_DWORD *)(v18 + 56) != 1 )
        goto LABEL_22;
      Buf1 = *(_OWORD *)(v18 + 136);
      if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
        goto LABEL_22;
      if ( v14 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x230,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)0x8000FFFFLL,
          v31);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        return 2147549183LL;
      }
    }
    else
    {
      if ( *(_DWORD *)(v18 + 56) != 1 )
        goto LABEL_22;
      Buf1 = *(_OWORD *)(v18 + 136);
      if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
        goto LABEL_22;
      if ( v14 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x239,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
          (const char *)0x8000FFFFLL,
          v31);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        return 2147549183LL;
      }
    }
    v14 = v18;
    v33 = (const char *)v18;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
LABEL_22:
    v19 = i;
    i = (__int64 *)i[2];
    if ( *((_BYTE *)i + 25) )
    {
      for ( i = (__int64 *)v19[1]; !*((_BYTE *)i + 25) && v19 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v19 = i;
    }
    else
    {
      v20 = (__int64 *)*i;
      if ( !*(_BYTE *)(*i + 25) )
      {
        do
        {
          i = v20;
          v20 = (__int64 *)*v20;
        }
        while ( !*((_BYTE *)v20 + 25) );
      }
    }
  }
  if ( v14 )
    goto LABEL_63;
  v40 = 0;
  v41 = 0;
  v38 = 1;
  v36 = 2;
  v37 = 2;
  Buf2 = GUID_dc638b31_cf31_48ed_9e79_02740bf5d013;
  v39 = -1;
  *(_QWORD *)&Buf1 = 0;
  v21 = *(const wchar_t **)(a1 + 40);
  *(_QWORD *)v42 = v21;
  if ( v21 )
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v21 + 8LL))(v21);
  *(_QWORD *)&Buf1 = 0;
  v22 = Microsoft::WRL::Details::MakeAndInitialize<CMidiTransformPipe,CMidiTransformPipe,>(&Buf1);
  v8 = v22;
  if ( v22 >= 0 )
  {
    v14 = Buf1;
    std::wstring::wstring((__int64)v44, *a3 + 16LL);
    v23 = v44;
    if ( v45 > 7 )
      v23 = (char **)v44[0];
    v24 = CMidiTransformPipe::Initialize(v14, (__int64)v23, (__int64)a3, (__int64)&Buf2, a1 + 120, v21);
    std::wstring::~wstring(v44);
    if ( (v24 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x252,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)v24,
        v32);
      if ( v21 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return v24;
    }
    v33 = (const char *)v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 56LL))(v14, a4);
    v24 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
        (const char *)(unsigned int)v25,
        v32);
      if ( v21 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return v24;
    }
    std::wstring::wstring((__int64)v44, *a3 + 16LL);
    std::multimap<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>::emplace<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy> &>(
      (__int64 *)(a1 + 104),
      &Buf2,
      (__int64)v44,
      (__int64 *)&Buf1);
    std::wstring::~wstring(v44);
    if ( v21 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_63:
    v26 = *a5;
    *a5 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v27 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v27 > 4u )
    {
      std::wstring::wstring((__int64)v44, *a3 + 16LL);
      v30 = v44;
      if ( v45 > 7 )
        v30 = (char **)v44[0];
      *(_QWORD *)v42 = v30;
      *(_QWORD *)&Buf2.Data1 = L"Exit success";
      *(_QWORD *)&Buf1 = a1;
      v33 = "CMidiClientManager::GetMidiProtocolDownscalerTransform";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v27,
        (__int64)byte_140087521,
        v28,
        v29,
        &v33,
        (__int64)&Buf1,
        &Buf2,
        v42);
      std::wstring::~wstring(v44);
    }
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x250,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
    (const char *)(unsigned int)v22,
    v31);
  if ( v21 )
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
  if ( (_QWORD)Buf1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Buf1 + 16LL))(Buf1);
  return v8;
}

```

## disassembly

```asm
0x140019aac  mov     rax, rsp
0x140019aaf  mov     [rax+10h], rbx
0x140019ab3  push    rbp
0x140019ab4  push    rsi
0x140019ab5  push    rdi
0x140019ab6  push    r12
0x140019ab8  push    r13
0x140019aba  push    r14
0x140019abc  push    r15
0x140019abe  lea     rbp, [rax-57h]
0x140019ac2  sub     rsp, 0C0h
0x140019ac9  movaps  xmmword ptr [rax-48h], xmm6
0x140019acd  mov     rax, cs:__security_cookie
0x140019ad4  xor     rax, rsp
0x140019ad7  mov     [rbp+4Fh+var_48], rax
0x140019adb  mov     r13, r9
0x140019ade  mov     r14, r8
0x140019ae1  mov     r15, rcx
0x140019ae4  mov     r12, [rbp+4Fh+arg_20]
0x140019ae8  xor     esi, esi
0x140019aea  cmp     [r8], rsi
0x140019aed  jnz     short loc_140019B13
0x140019aef  mov     rcx, [rbp+57h]; this
0x140019af3  mov     ebx, 80070057h
0x140019af8  mov     r9d, ebx; char *
0x140019afb  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140019b02  mov     edx, 213h; void *
0x140019b07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019b0c  mov     eax, ebx
0x140019b0e  jmp     loc_14001A051
0x140019b13  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140019b18  mov     rbx, [rax+8]
0x140019b1c  mov     eax, [rbx]
0x140019b1e  lea     rdi, aCmidiclientman; "CMidiClientManager::GetMidiProtocolDown"...
0x140019b25  cmp     eax, 4
0x140019b28  jbe     short loc_140019B9B
0x140019b2a  mov     rdx, [r14]
0x140019b2d  add     rdx, 10h
0x140019b31  lea     rcx, [rbp+4Fh+var_68]
0x140019b35  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140019b3a  lea     rax, [rbp+4Fh+var_68]
0x140019b3e  cmp     [rbp+4Fh+var_50], 7
0x140019b43  cmova   rax, [rbp+4Fh+var_68]
0x140019b48  mov     [rbp+4Fh+var_B0], rax
0x140019b4c  lea     rax, aEnter; "Enter"
0x140019b53  mov     qword ptr [rbp+4Fh+Buf1], rax
0x140019b57  mov     qword ptr [rbp+4Fh+Buf2], r15
0x140019b5b  mov     qword ptr [rbp+4Fh+var_78], rdi
0x140019b5f  lea     rax, [rbp+4Fh+var_B0]
0x140019b63  mov     [rsp+0F0h+var_B8], rax
0x140019b68  lea     rax, [rbp+4Fh+Buf1]
0x140019b6c  mov     [rsp+0F0h+var_C0], rax
0x140019b71  lea     rax, [rbp+4Fh+Buf2]
0x140019b75  mov     [rsp+0F0h+var_C8], rax
0x140019b7a  lea     rax, [rbp+4Fh+var_78]
0x140019b7e  mov     [rsp+0F0h+var_D0], rax; int
0x140019b83  lea     rdx, dword_14008770C
0x140019b8a  mov     rcx, rbx
0x140019b8d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140019b92  lea     rcx, [rbp+4Fh+var_68]; void *
0x140019b96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140019b9b  mov     rbx, rsi
0x140019b9e  mov     [rbp+4Fh+var_B0], rbx
0x140019ba2  movups  xmm6, xmmword ptr cs:_GUID_dc638b31_cf31_48ed_9e79_02740bf5d013.Data1
0x140019ba9  movups  [rbp+4Fh+Buf2], xmm6
0x140019bad  mov     rdx, [r14]
0x140019bb0  add     rdx, 10h
0x140019bb4  lea     rcx, [rbp+4Fh+var_68]
0x140019bb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140019bbd  lea     r8, [rbp+4Fh+var_68]
0x140019bc1  lea     rdx, [rbp+4Fh+var_78]
0x140019bc5  lea     rcx, [r15+68h]
0x140019bc9  call    ?equal_range@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@VCMidiTransformPipe@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@@std@@V12@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CMidiTransformPipe,wil::err_returncode_policy>>>,1>>::equal_range(std::wstring const &)
0x140019bce  lea     rcx, [rbp+4Fh+var_68]; void *
0x140019bd2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140019bd7  mov     rdi, qword ptr [rbp+4Fh+var_78]
0x140019bdb  cmp     rdi, [rbp+4Fh+var_70]
0x140019bdf  jz      loc_140019D57
0x140019be5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x140019bec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x140019bf1  mov     rsi, [rdi+40h]
0x140019bf5  test    al, al
0x140019bf7  jz      short loc_140019C52
0x140019bf9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x140019c00  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x140019c05  test    al, al
0x140019c07  jz      loc_140019CA0
0x140019c0d  mov     rax, [r14]
0x140019c10  cmp     [rsi+78h], rax
0x140019c14  jnz     loc_140019CA0
0x140019c1a  mov     rsi, [rdi+40h]
0x140019c1e  cmp     dword ptr [rsi+38h], 1
0x140019c22  jnz     short loc_140019CA0
0x140019c24  movups  xmm0, xmmword ptr [rsi+88h]
0x140019c2b  movdqu  [rbp+4Fh+Buf1], xmm0
0x140019c30  mov     r8d, 10h; Size
0x140019c36  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x140019c3a  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x140019c3e  call    memcmp_0
0x140019c43  test    eax, eax
0x140019c45  jnz     short loc_140019CA0
0x140019c47  test    rbx, rbx
0x140019c4a  jnz     loc_140019CF2
0x140019c50  jmp     short loc_140019C84
0x140019c52  cmp     dword ptr [rsi+38h], 1
0x140019c56  jnz     short loc_140019CA0
0x140019c58  movups  xmm0, xmmword ptr [rsi+88h]
0x140019c5f  movdqu  [rbp+4Fh+Buf1], xmm0
0x140019c64  mov     r8d, 10h; Size
0x140019c6a  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x140019c6e  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x140019c72  call    memcmp_0
0x140019c77  test    eax, eax
0x140019c79  jnz     short loc_140019CA0
0x140019c7b  test    rbx, rbx
0x140019c7e  jnz     loc_140019D27
0x140019c84  mov     rbx, rsi
0x140019c87  test    rsi, rsi
0x140019c8a  mov     [rbp+4Fh+var_B0], rbx
0x140019c8e  jz      short loc_140019CA0
0x140019c90  mov     rax, [rsi]
0x140019c93  mov     rcx, rbx
0x140019c96  mov     rax, [rax+8]
0x140019c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019c9f  nop
0x140019ca0  mov     rax, rdi
0x140019ca3  mov     rdi, [rdi+10h]
0x140019ca7  xor     esi, esi
0x140019ca9  cmp     [rdi+19h], sil
0x140019cad  jz      short loc_140019CD1
0x140019caf  mov     rdi, [rax+8]
0x140019cb3  jmp     short loc_140019CC6
0x140019cb5  cmp     rax, [rdi+10h]
0x140019cb9  jnz     loc_140019BDB
0x140019cbf  mov     rax, rdi
0x140019cc2  mov     rdi, [rdi+8]
0x140019cc6  cmp     [rdi+19h], sil
0x140019cca  jz      short loc_140019CB5
0x140019ccc  jmp     loc_140019BDB
0x140019cd1  mov     rcx, [rdi]
0x140019cd4  cmp     [rcx+19h], sil
0x140019cd8  jnz     loc_140019BDB
0x140019cde  mov     rdi, rcx
0x140019ce1  mov     rax, [rcx]
0x140019ce4  mov     rcx, rax
0x140019ce7  cmp     [rax+19h], sil
0x140019ceb  jz      short loc_140019CDE
0x140019ced  jmp     loc_140019BDB
0x140019cf2  mov     rcx, [rbp+57h]; this
0x140019cf6  mov     edi, 8000FFFFh
0x140019cfb  mov     r9d, edi; char *
0x140019cfe  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140019d05  mov     edx, 230h; void *
0x140019d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019d0f  nop
0x140019d10  mov     rdx, [rbx]
0x140019d13  mov     rcx, rbx
0x140019d16  mov     rax, [rdx+10h]
0x140019d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019d1f  nop
0x140019d20  mov     eax, edi
0x140019d22  jmp     loc_14001A051
0x140019d27  mov     rcx, [rbp+57h]; this
0x140019d2b  mov     edi, 8000FFFFh
0x140019d30  mov     r9d, edi; char *
0x140019d33  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140019d3a  mov     edx, 239h; void *
0x140019d3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019d44  nop
0x140019d45  mov     rax, [rbx]
0x140019d48  mov     rcx, rbx
0x140019d4b  mov     rax, [rax+10h]
0x140019d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019d54  nop
0x140019d55  jmp     short loc_140019D20
0x140019d57  test    rbx, rbx
0x140019d5a  jnz     loc_140019F80
0x140019d60  mov     [rbp+4Fh+var_7B], si
0x140019d64  mov     [rbp+4Fh+var_79], sil
0x140019d68  mov     [rbp+4Fh+var_80], 1
0x140019d6f  lea     eax, [rbx+2]
0x140019d72  mov     [rbp+4Fh+var_88], eax
0x140019d75  mov     [rbp+4Fh+var_84], eax
0x140019d78  movdqu  [rbp+4Fh+Buf2], xmm6
0x140019d7d  mov     [rbp+4Fh+var_7C], 0FFh
0x140019d81  mov     qword ptr [rbp+4Fh+Buf1], rsi
0x140019d85  mov     rdi, [r15+28h]
0x140019d89  mov     qword ptr [rbp+4Fh+var_78], rdi
0x140019d8d  test    rdi, rdi
0x140019d90  jz      short loc_140019DA2
0x140019d92  mov     rax, [rdi]
0x140019d95  mov     rcx, rdi
0x140019d98  mov     rax, [rax+8]
0x140019d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019da1  nop
0x140019da2  mov     qword ptr [rbp+4Fh+Buf1], rsi
0x140019da6  lea     rcx, [rbp+4Fh+Buf1]
0x140019daa  call    ??$MakeAndInitialize@VCMidiTransformPipe@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCMidiTransformPipe@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMidiTransformPipe,CMidiTransformPipe,>(CMidiTransformPipe * *)
0x140019daf  mov     ebx, eax
0x140019db1  test    eax, eax
0x140019db3  jns     short loc_140019DFE
0x140019db5  mov     rcx, [rbp+57h]; this
0x140019db9  mov     r9d, eax; char *
0x140019dbc  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140019dc3  mov     edx, 250h; void *
0x140019dc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019dcd  nop
0x140019dce  test    rdi, rdi
0x140019dd1  jz      short loc_140019DE3
0x140019dd3  mov     rax, [rdi]
0x140019dd6  mov     rcx, rdi
0x140019dd9  mov     rax, [rax+10h]
0x140019ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019de2  nop
0x140019de3  mov     rcx, qword ptr [rbp+4Fh+Buf1]
0x140019de7  test    rcx, rcx
0x140019dea  jz      short loc_140019DF9
0x140019dec  mov     rax, [rcx]
0x140019def  mov     rax, [rax+10h]
0x140019df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019df8  nop
0x140019df9  jmp     loc_140019B0C
0x140019dfe  mov     rbx, qword ptr [rbp+4Fh+Buf1]
0x140019e02  mov     rdx, [r14]
0x140019e05  add     rdx, 10h
0x140019e09  lea     rcx, [rbp+4Fh+var_68]
0x140019e0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140019e12  nop
0x140019e13  lea     rdx, [rbp+4Fh+var_68]
0x140019e17  cmp     [rbp+4Fh+var_50], 7
0x140019e1c  cmova   rdx, [rbp+4Fh+var_68]
0x140019e21  lea     rax, [r15+78h]
0x140019e25  mov     [rsp+0F0h+var_C8], rdi; __int64
0x140019e2a  mov     [rsp+0F0h+var_D0], rax; int
0x140019e2f  lea     r9, [rbp+4Fh+Buf2]
0x140019e33  mov     r8, r14
0x140019e36  mov     rcx, rbx; int
0x140019e39  call    ?Initialize@CMidiTransformPipe@@QEAAJPEBGAEAV?$com_ptr_t@VCMidiPipe@@Uerr_returncode_policy@wil@@@wil@@PEAUMIDISRV_TRANSFORMCREATION_PARAMS@@PEAKPEAUIMidiDeviceManager@@@Z; CMidiTransformPipe::Initialize(ushort const *,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy> &,MIDISRV_TRANSFORMCREATION_PARAMS *,ulong *,IMidiDeviceManager *)
0x140019e3e  mov     esi, eax
0x140019e40  lea     rcx, [rbp+4Fh+var_68]; void *
0x140019e44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140019e49  test    esi, esi
0x140019e4b  jns     short loc_140019E97
0x140019e4d  mov     rcx, [rbp+57h]; this
0x140019e51  mov     r9d, esi; char *
0x140019e54  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140019e5b  mov     edx, 252h; void *
0x140019e60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019e65  nop
0x140019e66  test    rdi, rdi
0x140019e69  jz      short loc_140019E7B
0x140019e6b  mov     rax, [rdi]
0x140019e6e  mov     rcx, rdi
0x140019e71  mov     rax, [rax+10h]
0x140019e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e7a  nop
0x140019e7b  test    rbx, rbx
0x140019e7e  jz      short loc_140019E90
0x140019e80  mov     rax, [rbx]
0x140019e83  mov     rcx, rbx
0x140019e86  mov     rax, [rax+10h]
0x140019e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e8f  nop
0x140019e90  mov     eax, esi
0x140019e92  jmp     loc_14001A051
0x140019e97  mov     [rbp+4Fh+var_B0], rbx
0x140019e9b  test    rbx, rbx
0x140019e9e  jz      short loc_140019EB0
0x140019ea0  mov     rax, [rbx]
0x140019ea3  mov     rcx, rbx
0x140019ea6  mov     rax, [rax+8]
0x140019eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019eaf  nop
0x140019eb0  mov     rax, [rbx]
0x140019eb3  mov     rdx, r13
0x140019eb6  mov     rcx, rbx
0x140019eb9  mov     rax, [rax+38h]
0x140019ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019ec2  mov     esi, eax
0x140019ec4  test    eax, eax
0x140019ec6  jns     short loc_140019F25
0x140019ec8  mov     rcx, [rbp+57h]; this
0x140019ecc  mov     r9d, eax; char *
0x140019ecf  lea     r8, aAvcoreMidi2Ser_1; "avcore\\midi2\\service\\exe\\midiclient"...
0x140019ed6  mov     edx, 256h; void *
0x140019edb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019ee0  nop
0x140019ee1  test    rdi, rdi
0x140019ee4  jz      short loc_140019EF6
0x140019ee6  mov     rax, [rdi]
0x140019ee9  mov     rcx, rdi
0x140019eec  mov     rax, [rax+10h]
0x140019ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019ef5  nop
0x140019ef6  test    rbx, rbx
0x140019ef9  jz      short loc_140019F0B
0x140019efb  mov     rax, [rbx]
0x140019efe  mov     rcx, rbx
0x140019f01  mov     rax, [rax+10h]
0x140019f05  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
