# Windows::Internal::Spelling::TaskConsumer::UpdateMtf(bool,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x1800405d4`
- end: `0x180040c5c`
- name: `?UpdateMtf@TaskConsumer@Spelling@Internal@Windows@@AEAAX_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z`
- size: `1672`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ff68`
- `0x180040d88`
- `0x180046920`

## callees

- `0x180022e88`
- `0x18003feb4`
- `0x18003fec8`
- `0x18003ff20`
- `0x18003ff50`
- `0x1800405d4`
- `0x180040c64`
- `0x180040cc4`
- `0x180040ce8`
- `0x180040d08`
- `0x180040d34`
- `0x1800411b4`
- `0x180046ef8`
- `0x180057f7c`
- `0x18005ac5c`
- `0x180061320`
- `0x180062314`
- `0x180070530`
- `0x180080490`
- `0x1800c0010`

## string_xrefs

- `0x1800406c3`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040712`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x18004075d`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x1800407ba`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040812`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040847`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x1800408b9`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x1800408f4`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040930`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x18004096f`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040adb`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040af0`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040beb`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040c00`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040636`: `ActivityUpdateMtf`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Windows::Internal::Spelling::TaskConsumer::UpdateMtf(__int64 a1, bool a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rbx
  LPVOID *v10; // rax
  LPVOID v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  _BYTE *v26; // rax
  LPVOID v27; // rbx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  unsigned __int64 v31; // rax
  int v32; // eax
  int v33; // eax
  int v34; // [rsp+20h] [rbp-E0h]
  _WORD v35[2]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v36[2]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v41; // [rsp+58h] [rbp-A8h]
  __int128 v42; // [rsp+60h] [rbp-A0h]
  __int128 v43; // [rsp+70h] [rbp-90h]
  __int64 v44; // [rsp+80h] [rbp-80h]
  _BYTE v45[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v46[24]; // [rsp+A0h] [rbp-60h] BYREF
  char v47[16]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v48; // [rsp+C8h] [rbp-38h] BYREF
  int v49; // [rsp+D8h] [rbp-28h]
  int v50; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v51; // [rsp+E4h] [rbp-1Ch]
  _QWORD v52[42]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  if ( *(_BYTE *)(a1 + 8) && (a2 || *(_QWORD *)(a3 + 8) || *(_QWORD *)(a4 + 8)) )
  {
    v8 = *(_QWORD *)(a4 + 8);
    v9 = *(_QWORD *)(a3 + 8);
    wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v52,
      "ActivityUpdateMtf");
    v52[0] = &SpellingTelemetry::ActivityUpdateMtf::`vftable';
    SpellingTelemetry::ActivityUpdateMtf::StartActivity((SpellingTelemetry::ActivityUpdateMtf *)v52, a2, v9, v8);
    if ( !*(_QWORD *)(a1 + 64) )
    {
      v10 = wil::CoCreateInstance<IMtfSuggestionClient,wil::err_exception_policy>((LPVOID *)&v37);
      v11 = *v10;
      *v10 = 0;
      v12 = *(_QWORD *)(a1 + 64);
      *(_QWORD *)(a1 + 64) = v11;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 64) + 24LL))(*(_QWORD *)(a1 + 64), 1);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdi"
                        "ctionarymanager.cpp",
          (const char *)(unsigned int)v13,
          v34);
    }
    memset_0(&v50, 0, 0x50u);
    v50 = 1;
    v51 = 1033;
    v14 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 64) + 48LL))(*(_QWORD *)(a1 + 64), &v50);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24D,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdict"
                      "ionarymanager.cpp",
        (const char *)(unsigned int)v14,
        v34);
    v35[0] = 0;
    v36[0] = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD, _WORD *))(**(_QWORD **)(a1 + 64) + 56LL))(
            *(_QWORD *)(a1 + 64),
            &GUID_65fa40bd_3ed5_4631_ba9f_68df9a7d9ae6,
            0,
            v35);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdict"
                      "ionarymanager.cpp",
        (const char *)(unsigned int)v15,
        v34);
    v16 = lambda_fd3ca70b521fed0005ae73169376e3df_::_lambda_fd3ca70b521fed0005ae73169376e3df_(&v48, a1, v35);
    wil::scope_exit__lambda_97672074d3269d860949cefbd2b63e15___(v46, v16);
    v17 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD, _WORD *))(**(_QWORD **)(a1 + 64) + 56LL))(
            *(_QWORD *)(a1 + 64),
            &GUID_285e403a_14ce_41c9_8e55_92921ca0dfb3,
            0,
            v36);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x253,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdict"
                      "ionarymanager.cpp",
        (const char *)(unsigned int)v17,
        v34);
    v18 = lambda_fd3ca70b521fed0005ae73169376e3df_::_lambda_fd3ca70b521fed0005ae73169376e3df_(v47, a1, v36);
    wil::scope_exit__lambda_97672074d3269d860949cefbd2b63e15___(v45, v18);
    if ( a2 )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 96LL))(*(_QWORD *)(a1 + 64), v35[0]);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x258,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdi"
                        "ctionarymanager.cpp",
          (const char *)(unsigned int)v19,
          v34);
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 96LL))(*(_QWORD *)(a1 + 64), v36[0]);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x259,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdi"
                        "ctionarymanager.cpp",
          (const char *)(unsigned int)v20,
          v34);
    }
    if ( *(_QWORD *)(a3 + 8) )
    {
      if ( *(_QWORD *)(a3 + 8) <= 1u )
      {
        v26 = **(_BYTE ***)a3;
        v37 = (unsigned __int64)v26;
        while ( !v26[25] )
        {
          wil::make_bstr(&v38);
          v43 = 0;
          v44 = 0;
          v40 = 139;
          v41 = v38;
          v42 = v38;
          DWORD1(v43) = 1;
          wil::CoCreateInstance<IMtfPropertyBag,wil::err_exception_policy>(&v39);
          v27 = v39;
          *(_QWORD *)&v48 = v39;
          if ( v39 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 8LL))(v39);
          else
            v27 = 0;
          v28 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, __int64))(*(_QWORD *)v27 + 24LL))(
                  v27,
                  qword_1800DE600,
                  &qword_1800DE610,
                  4);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD4,
              (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\MtfHelper.h",
              (const char *)(unsigned int)v28,
              v34);
          *((_QWORD *)&v42 + 1) = v39;
          v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD))(**(_QWORD **)(a1 + 64) + 80LL))(
                  *(_QWORD *)(a1 + 64),
                  v35[0],
                  &v40,
                  0);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x27B,
              (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roami"
                            "ngdictionarymanager.cpp",
              (const char *)(unsigned int)v29,
              0);
          v34 = 0;
          v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD))(**(_QWORD **)(a1 + 64) + 80LL))(
                  *(_QWORD *)(a1 + 64),
                  v36[0],
                  &v40,
                  0);
          if ( v30 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x27C,
              (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roami"
                            "ngdictionarymanager.cpp",
              (const char *)(unsigned int)v30,
              0);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,EventRegistrationToken>>>,std::_Iterator_base0>::operator++(&v37);
          v26 = (_BYTE *)v37;
        }
      }
      else
      {
        SpellingTelemetry::AddWordsInBulk();
        v21 = *(_DWORD *)(a1 + 72);
        *(_DWORD *)(a1 + 72) = v21 + 1;
        v48 = xmmword_1800DB680;
        v49 = v21;
        v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 64) + 72LL))(
                *(_QWORD *)(a1 + 64),
                v35[0],
                &v48,
                20);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x265,
            (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roaming"
                          "dictionarymanager.cpp",
            (const char *)(unsigned int)v22,
            v34);
        v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 72LL))(
                *(_QWORD *)(a1 + 64),
                v35[0],
                0,
                0);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x266,
            (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roaming"
                          "dictionarymanager.cpp",
            (const char *)(unsigned int)v23,
            v34);
        v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 64) + 72LL))(
                *(_QWORD *)(a1 + 64),
                v36[0],
                &v48,
                20);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x267,
            (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roaming"
                          "dictionarymanager.cpp",
            (const char *)(unsigned int)v24,
            v34);
        v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 72LL))(
                *(_QWORD *)(a1 + 64),
                v36[0],
                0,
                0);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x268,
            (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roaming"
                          "dictionarymanager.cpp",
            (const char *)(unsigned int)v25,
            v34);
      }
    }
    if ( *(_QWORD *)(a4 + 8) )
    {
      v31 = **(_QWORD **)a4;
      v38 = v31;
      while ( !*(_BYTE *)(v31 + 25) )
      {
        wil::make_bstr(&v37);
        v43 = 0;
        v44 = 0;
        v40 = 3;
        v41 = v37;
        v42 = v37;
        v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(a1 + 64) + 88LL))(
                *(_QWORD *)(a1 + 64),
                v35[0],
                &v40);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x28D,
            (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roaming"
                          "dictionarymanager.cpp",
            (const char *)(unsigned int)v32,
            v34);
        v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(a1 + 64) + 88LL))(
                *(_QWORD *)(a1 + 64),
                v36[0],
                &v40);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x28E,
            (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roaming"
                          "dictionarymanager.cpp",
            (const char *)(unsigned int)v33,
            v34);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,EventRegistrationToken>>>,std::_Iterator_base0>::operator++(&v38);
        v31 = v38;
      }
    }
    wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v52);
    wil::details::lambda_call__lambda_97672074d3269d860949cefbd2b63e15___::_lambda_call__lambda_97672074d3269d860949cefbd2b63e15___(v45);
    wil::details::lambda_call__lambda_2c8c9a5459fcf1395e08ab04b7e15079___::_lambda_call__lambda_2c8c9a5459fcf1395e08ab04b7e15079___(v46);
    SpellingTelemetry::ActivityUpdateMtf::~ActivityUpdateMtf((SpellingTelemetry::ActivityUpdateMtf *)v52);
  }
}

```

## disassembly

```asm
0x1800405d4  push    rbp
0x1800405d6  push    rbx
0x1800405d7  push    rsi
0x1800405d8  push    rdi
0x1800405d9  push    r12
0x1800405db  push    r13
0x1800405dd  push    r14
0x1800405df  push    r15
0x1800405e1  lea     rbp, [rsp-198h]
0x1800405e9  sub     rsp, 298h
0x1800405f0  mov     rax, cs:__security_cookie
0x1800405f7  xor     rax, rsp
0x1800405fa  mov     [rbp+1D0h+var_50], rax
0x180040601  mov     r12, r9
0x180040604  mov     r14, r8
0x180040607  mov     r15b, dl
0x18004060a  mov     rsi, rcx
0x18004060d  xor     r13d, r13d
0x180040610  cmp     [rcx+8], r13b
0x180040614  jz      loc_180040C39
0x18004061a  test    dl, dl
0x18004061c  jnz     short loc_18004062E
0x18004061e  cmp     [r8+8], r13
0x180040622  jnz     short loc_18004062E
0x180040624  cmp     [r9+8], r13
0x180040628  jz      loc_180040C39
0x18004062e  mov     rdi, [r9+8]
0x180040632  mov     rbx, [r8+8]
0x180040636  lea     rdx, aActivityupdate; "ActivityUpdateMtf"
0x18004063d  lea     rcx, [rbp+1D0h+var_1A0]
0x180040641  call    ??0?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180040646  lea     rax, ??_7ActivityUpdateMtf@SpellingTelemetry@@6B@; const SpellingTelemetry::ActivityUpdateMtf::`vftable'
0x18004064d  mov     [rbp+1D0h+var_1A0], rax
0x180040651  mov     r9, rdi; unsigned __int64
0x180040654  mov     r8, rbx; unsigned __int64
0x180040657  mov     dl, r15b; bool
0x18004065a  lea     rcx, [rbp+1D0h+var_1A0]; this
0x18004065e  call    ?StartActivity@ActivityUpdateMtf@SpellingTelemetry@@QEAAX_N_K1@Z; SpellingTelemetry::ActivityUpdateMtf::StartActivity(bool,unsigned __int64,unsigned __int64)
0x180040663  nop
0x180040664  mov     edi, 1
0x180040669  cmp     [rsi+40h], r13
0x18004066d  jnz     short loc_1800406D5
0x18004066f  lea     rcx, [rsp+2D0h+var_298]
0x180040674  call    ??$CoCreateInstance@UIMtfSuggestionClient@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMtfSuggestionClient@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IMtfSuggestionClient,wil::err_exception_policy>(_GUID const &,ulong)
0x180040679  mov     rdx, [rax]
0x18004067c  mov     [rax], r13
0x18004067f  mov     rcx, [rsi+40h]
0x180040683  mov     [rsi+40h], rdx
0x180040687  test    rcx, rcx
0x18004068a  jz      short loc_180040699
0x18004068c  mov     rax, [rcx]
0x18004068f  mov     rax, [rax+10h]
0x180040693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040698  nop
0x180040699  lea     rcx, [rsp+2D0h+var_298]
0x18004069e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800406a3  mov     rcx, [rsi+40h]
0x1800406a7  mov     rax, [rcx]
0x1800406aa  mov     edx, edi
0x1800406ac  mov     rax, [rax+18h]
0x1800406b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406b5  mov     rcx, [rbp+1D8h]; this
0x1800406bc  test    eax, eax
0x1800406be  jns     short loc_1800406D5
0x1800406c0  mov     r9d, eax; char *
0x1800406c3  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800406ca  mov     edx, 246h; void *
0x1800406cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800406d5  xor     edx, edx; Val
0x1800406d7  lea     r8d, [rdx+50h]; Size
0x1800406db  lea     rcx, [rbp+1D0h+var_1F0]; void *
0x1800406df  call    memset_0
0x1800406e4  mov     [rbp+1D0h+var_1F0], edi
0x1800406e7  mov     eax, 409h
0x1800406ec  mov     [rbp+1D0h+var_1EC], ax
0x1800406f0  mov     rcx, [rsi+40h]
0x1800406f4  mov     rax, [rcx]
0x1800406f7  lea     rdx, [rbp+1D0h+var_1F0]
0x1800406fb  mov     rax, [rax+30h]
0x1800406ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040704  mov     rcx, [rbp+1D8h]; this
0x18004070b  test    eax, eax
0x18004070d  jns     short loc_180040724
0x18004070f  mov     r9d, eax; char *
0x180040712  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180040719  mov     edx, 24Dh; void *
0x18004071e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040724  mov     [rsp+2D0h+var_2A0], r13w
0x18004072a  mov     [rsp+2D0h+var_29C], r13w
0x180040730  mov     rcx, [rsi+40h]
0x180040734  mov     rax, [rcx]
0x180040737  lea     r9, [rsp+2D0h+var_2A0]
0x18004073c  xor     r8d, r8d
0x18004073f  lea     rdx, _GUID_65fa40bd_3ed5_4631_ba9f_68df9a7d9ae6
0x180040746  mov     rax, [rax+38h]
0x18004074a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004074f  mov     rcx, [rbp+1D8h]; this
0x180040756  test    eax, eax
0x180040758  jns     short loc_18004076F
0x18004075a  mov     r9d, eax; char *
0x18004075d  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180040764  mov     edx, 250h; void *
0x180040769  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004076f  lea     r8, [rsp+2D0h+var_2A0]
0x180040774  mov     rdx, rsi
0x180040777  lea     rcx, [rbp+1D0h+var_208]
0x18004077b  call    _lambda_fd3ca70b521fed0005ae73169376e3df____lambda_fd3ca70b521fed0005ae73169376e3df_
0x180040780  mov     rdx, rax
0x180040783  lea     rcx, [rbp+1D0h+var_230]
0x180040787  call    wil__scope_exit__lambda_97672074d3269d860949cefbd2b63e15___
0x18004078c  nop
0x18004078d  mov     rcx, [rsi+40h]
0x180040791  mov     rax, [rcx]
0x180040794  lea     r9, [rsp+2D0h+var_29C]
0x180040799  xor     r8d, r8d
0x18004079c  lea     rdx, _GUID_285e403a_14ce_41c9_8e55_92921ca0dfb3
0x1800407a3  mov     rax, [rax+38h]
0x1800407a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407ac  mov     rcx, [rbp+1D8h]; this
0x1800407b3  test    eax, eax
0x1800407b5  jns     short loc_1800407CC
0x1800407b7  mov     r9d, eax; char *
0x1800407ba  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800407c1  mov     edx, 253h; void *
0x1800407c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800407cc  lea     r8, [rsp+2D0h+var_29C]
0x1800407d1  mov     rdx, rsi
0x1800407d4  lea     rcx, [rbp+1D0h+var_218]
0x1800407d8  call    _lambda_fd3ca70b521fed0005ae73169376e3df____lambda_fd3ca70b521fed0005ae73169376e3df_
0x1800407dd  mov     rdx, rax
0x1800407e0  lea     rcx, [rbp+1D0h+var_248]
0x1800407e4  call    wil__scope_exit__lambda_97672074d3269d860949cefbd2b63e15___
0x1800407e9  nop
0x1800407ea  test    r15b, r15b
0x1800407ed  jz      short loc_180040859
0x1800407ef  mov     rcx, [rsi+40h]
0x1800407f3  mov     rax, [rcx]
0x1800407f6  movzx   edx, [rsp+2D0h+var_2A0]
0x1800407fb  mov     rax, [rax+60h]
0x1800407ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040804  mov     rcx, [rbp+1D8h]; this
0x18004080b  test    eax, eax
0x18004080d  jns     short loc_180040824
0x18004080f  mov     r9d, eax; char *
0x180040812  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180040819  mov     edx, 258h; void *
0x18004081e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040824  mov     rcx, [rsi+40h]
0x180040828  mov     rax, [rcx]
0x18004082b  movzx   edx, [rsp+2D0h+var_29C]
0x180040830  mov     rax, [rax+60h]
0x180040834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040839  mov     rcx, [rbp+1D8h]; this
0x180040840  test    eax, eax
0x180040842  jns     short loc_180040859
0x180040844  mov     r9d, eax; char *
0x180040847  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x18004084e  mov     edx, 259h; void *
0x180040853  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040859  cmp     [r14+8], r13
0x18004085d  jz      loc_180040B17
0x180040863  cmp     [r14+8], rdi
0x180040867  jbe     loc_180040981
0x18004086d  call    ?AddWordsInBulk@SpellingTelemetry@@SAXXZ; SpellingTelemetry::AddWordsInBulk(void)
0x180040872  mov     ecx, [rsi+48h]
0x180040875  lea     eax, [rcx+1]
0x180040878  mov     [rsi+48h], eax
0x18004087b  movups  xmm0, cs:xmmword_1800DB680
0x180040882  movdqu  [rbp+1D0h+var_208], xmm0
0x180040887  mov     [rbp+1D0h+var_1F8], ecx
0x18004088a  mov     rcx, [rsi+40h]
0x18004088e  mov     rax, [rcx]
0x180040891  mov     ebx, 14h
0x180040896  mov     r9d, ebx
0x180040899  lea     r8, [rbp+1D0h+var_208]
0x18004089d  movzx   edx, [rsp+2D0h+var_2A0]
0x1800408a2  mov     rax, [rax+48h]
0x1800408a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408ab  mov     rcx, [rbp+1D8h]; this
0x1800408b2  test    eax, eax
0x1800408b4  jns     short loc_1800408CB
0x1800408b6  mov     r9d, eax; char *
0x1800408b9  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800408c0  mov     edx, 265h; void *
0x1800408c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800408cb  mov     rcx, [rsi+40h]
0x1800408cf  mov     rax, [rcx]
0x1800408d2  xor     r9d, r9d
0x1800408d5  xor     r8d, r8d
0x1800408d8  movzx   edx, [rsp+2D0h+var_2A0]
0x1800408dd  mov     rax, [rax+48h]
0x1800408e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408e6  mov     rcx, [rbp+1D8h]; this
0x1800408ed  test    eax, eax
0x1800408ef  jns     short loc_180040906
0x1800408f1  mov     r9d, eax; char *
0x1800408f4  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800408fb  mov     edx, 266h; void *
0x180040900  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040906  mov     rcx, [rsi+40h]
0x18004090a  mov     rax, [rcx]
0x18004090d  mov     r9d, ebx
0x180040910  lea     r8, [rbp+1D0h+var_208]
0x180040914  movzx   edx, [rsp+2D0h+var_29C]
0x180040919  mov     rax, [rax+48h]
0x18004091d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040922  mov     rcx, [rbp+1D8h]; this
0x180040929  test    eax, eax
0x18004092b  jns     short loc_180040942
0x18004092d  mov     r9d, eax; char *
0x180040930  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180040937  mov     edx, 267h; void *
0x18004093c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040942  mov     rcx, [rsi+40h]
0x180040946  mov     rax, [rcx]
0x180040949  xor     r9d, r9d
0x18004094c  xor     r8d, r8d
0x18004094f  movzx   edx, [rsp+2D0h+var_29C]
0x180040954  mov     rax, [rax+48h]
0x180040958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004095d  mov     rcx, [rbp+1D8h]; this
0x180040964  test    eax, eax
0x180040966  jns     loc_180040B17
0x18004096c  mov     r9d, eax; char *
0x18004096f  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180040976  mov     edx, 268h; void *
0x18004097b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040981  mov     rax, [r14]
0x180040984  mov     rax, [rax]
0x180040987  mov     [rsp+2D0h+var_298], rax
0x18004098c  cmp     [rax+19h], r13b
0x180040990  jnz     loc_180040B17
0x180040996  lea     rdx, [rax+20h]
0x18004099a  cmp     qword ptr [rdx+18h], 7
0x18004099f  jbe     short loc_1800409A4
0x1800409a1  mov     rdx, [rdx]
0x1800409a4  lea     rcx, [rsp+2D0h+var_290]
0x1800409a9  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800409ae  nop
0x1800409af  xorps   xmm0, xmm0
0x1800409b2  xor     eax, eax
0x1800409b4  movups  [rsp+2D0h+var_280], xmm0
0x1800409b9  movups  [rsp+2D0h+var_270], xmm0
0x1800409be  movups  [rsp+2D0h+var_260], xmm0
0x1800409c3  mov     [rbp+1D0h+var_250], rax
0x1800409c7  mov     dword ptr [rsp+2D0h+var_280], 8Bh
0x1800409cf  mov     rax, [rsp+2D0h+var_290]
0x1800409d4  mov     qword ptr [rsp+2D0h+var_280+8], rax
0x1800409d9  mov     qword ptr [rsp+2D0h+var_270], rax
0x1800409de  mov     dword ptr [rsp+2D0h+var_260+4], edi
0x1800409e2  lea     rcx, [rsp+2D0h+var_288]
0x1800409e7  call    ??$CoCreateInstance@UIMtfPropertyBag@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMtfPropertyBag@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IMtfPropertyBag,wil::err_exception_policy>(_GUID const &,ulong)
0x1800409ec  nop
0x1800409ed  mov     rbx, [rsp+2D0h+var_288]
0x1800409f2  mov     qword ptr [rbp+1D0h+var_208], rbx
0x1800409f6  test    rbx, rbx
0x1800409f9  jz      short loc_180040A0C
0x1800409fb  mov     rax, [rbx]
0x1800409fe  mov     rcx, rbx
0x180040a01  mov     rax, [rax+8]
0x180040a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a0a  jmp     short loc_180040A0F
0x180040a0c  mov     rbx, r13
0x180040a0f  mov     rax, [rbx]
0x180040a12  mov     r9d, 4
0x180040a18  lea     r8, qword_1800DE610
0x180040a1f  lea     rdx, qword_1800DE600
0x180040a26  mov     rcx, rbx
0x180040a29  mov     rax, [rax+18h]
0x180040a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a32  mov     rcx, [rbp+1D8h]; this
0x180040a39  test    eax, eax
0x180040a3b  js      loc_180040B02
0x180040a41  mov     rax, [rsp+2D0h+var_288]
0x180040a46  mov     qword ptr [rsp+2D0h+var_270+8], rax
0x180040a4b  mov     rcx, [rsi+40h]
0x180040a4f  mov     rax, [rcx]
0x180040a52  mov     [rsp+2D0h+var_2B0], r13d; int
0x180040a57  xor     r9d, r9d
0x180040a5a  lea     r8, [rsp+2D0h+var_280]
0x180040a5f  movzx   edx, [rsp+2D0h+var_2A0]
0x180040a64  mov     rax, [rax+50h]
0x180040a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a6d  mov     rcx, [rbp+1D8h]; this
0x180040a74  test    eax, eax
0x180040a76  js      short loc_180040AED
0x180040a78  mov     rcx, [rsi+40h]
0x180040a7c  mov     rax, [rcx]
0x180040a7f  mov     [rsp+2D0h+var_2B0], r13d; int
0x180040a84  xor     r9d, r9d
0x180040a87  lea     r8, [rsp+2D0h+var_280]
0x180040a8c  movzx   edx, [rsp+2D0h+var_29C]
0x180040a91  mov     rax, [rax+50h]
0x180040a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a9a  mov     rcx, [rbp+1D8h]; this
0x180040aa1  test    eax, eax
0x180040aa3  js      short loc_180040AD8
0x180040aa5  lea     rcx, [rbp+1D0h+var_208]
0x180040aa9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180040aae  nop
  ... truncated ...
```
