# SystemSettings::Speech::CTextToSpeechVoiceSetting::_initializeChoicesAndDefault(void)

- ea: `0x1800cdc30`
- end: `0x1800ce0ce`
- name: `?_initializeChoicesAndDefault@CTextToSpeechVoiceSetting@Speech@SystemSettings@@MEAAJXZ`
- size: `1182`
- prototype: `__int64 __fastcall(SystemSettings::Speech::CTextToSpeechVoiceSetting *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000c840`
- `0x18001098c`
- `0x180011bb0`
- `0x180019a20`
- `0x18001ecfc`
- `0x18002012c`
- `0x18002373c`
- `0x180065f28`
- `0x1800869cc`
- `0x1800cbdb8`
- `0x1800cdc30`
- `0x1800da8ec`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800cdf0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800cdf0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cde5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cde90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdeca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cde5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cde90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdeca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cdf28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cdf28`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::Speech::CTextToSpeechVoiceSetting::_initializeChoicesAndDefault(
        SystemSettings::Speech::CTextToSpeechVoiceSetting *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, char *); // rsi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // r15d
  HSTRING *v14; // rax
  HSTRING *v15; // rsi
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  unsigned int v29; // edi
  HSTRING **v30; // rdx
  __int64 v32; // rdx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-49h] BYREF
  __int64 v34; // [rsp+38h] [rbp-31h]
  __int64 v35; // [rsp+40h] [rbp-29h] BYREF
  __int64 v36; // [rsp+48h] [rbp-21h] BYREF
  __int64 v37; // [rsp+50h] [rbp-19h] BYREF
  HSTRING *v38; // [rsp+58h] [rbp-11h] BYREF
  unsigned int v39; // [rsp+60h] [rbp-9h] BYREF
  INT32 result; // [rsp+64h] [rbp-5h] BYREF
  __int64 v41; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( *((_BYTE *)this + 248) )
    return 0;
  v41 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Media.SpeechSynthesis.SpeechSynthesizer",
    0x30u,
    0x2Fu);
  v2 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IInstalledVoicesStatic>>(
         v34,
         &v41);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v36 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 56LL))(v41, &v36);
    v3 = v4;
    if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147024894 )
    {
      v5 = 434;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
        (const char *)(unsigned int)v4,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_47:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      goto LABEL_48;
    }
    v6 = v36;
    if ( v36 )
    {
      v7 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v36 + 56LL);
      WindowsDeleteString(*((HSTRING *)this + 30));
      *((_QWORD *)this + 30) = 0;
      v4 = v7(v6, (char *)this + 240);
      v3 = v4;
      if ( v4 < 0 )
      {
        v5 = 438;
        goto LABEL_7;
      }
    }
    v35 = 0;
    v8 = v41;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v10 = v9(v8, &v35);
    v3 = v10;
    if ( ((v10 + 0x80000000) & 0x80000000) == 0 && v10 != -2147024894 )
    {
      v11 = 443;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
        (const char *)(unsigned int)v10,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_46:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      goto LABEL_47;
    }
    v12 = 0;
    v39 = 0;
    if ( v35 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 56LL))(v35, &v39);
      v3 = v10;
      if ( v10 < 0 )
      {
        v11 = 449;
        goto LABEL_14;
      }
      v12 = v39;
    }
    v13 = 0;
    if ( v12 )
    {
      while ( 1 )
      {
        v14 = (HSTRING *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        v15 = v14;
        if ( v14 )
        {
          *v14 = 0;
          v14[1] = 0;
          v14[2] = 0;
        }
        else
        {
          v15 = 0;
        }
        v38 = v15;
        if ( !v15 )
          break;
        v37 = 0;
        v16 = v35;
        v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        v18 = v17(v16, v13, &v37);
        v3 = v18;
        if ( v18 < 0 )
        {
          v32 = 458;
          goto LABEL_40;
        }
        v19 = v37;
        v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 56LL);
        WindowsDeleteString(v15[1]);
        v15[1] = 0;
        v18 = v20(v19, v15 + 1);
        v3 = v18;
        if ( v18 < 0 )
        {
          v32 = 459;
          goto LABEL_40;
        }
        v21 = v37;
        v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
        WindowsDeleteString(*v15);
        *v15 = 0;
        v18 = v22(v21, v15);
        v3 = v18;
        if ( v18 < 0 )
        {
          v32 = 460;
          goto LABEL_40;
        }
        v23 = v37;
        v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 64LL);
        WindowsDeleteString(v15[2]);
        v15[2] = 0;
        v18 = v24(v23, v15 + 2);
        v3 = v18;
        if ( v18 < 0 )
        {
          v32 = 461;
LABEL_40:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v32,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
            (const char *)(unsigned int)v18,
            (int)hstringHeader.Reserved.Reserved1);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
          goto LABEL_45;
        }
        result = 0;
        if ( WindowsCompareStringOrdinal(*((HSTRING *)this + 30), v15[1], &result) >= 0 && !result )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(v15[2], 0);
          std::wstring::wstring(&hstringHeader, StringRawBuffer);
          SystemSettings::Speech::AddVoicesSingleton::SetDefaultVoiceLanguage(v26, &hstringHeader);
          std::wstring::_Tidy_deallocate(&hstringHeader);
        }
        v27 = *((_QWORD *)this + 27);
        if ( v27 == *((_QWORD *)this + 29) )
        {
          v28 = CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(
                  (char *)this + 208,
                  v27 + 1);
          v29 = v28;
          if ( v28 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D9,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
              (const char *)(unsigned int)v28,
              (int)hstringHeader.Reserved.Reserved1);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
            std::unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>::~unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>(&v38);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
            v3 = v29;
            goto LABEL_48;
          }
        }
        v30 = (HSTRING **)(*((_QWORD *)this + 26) + 8 * (*((_QWORD *)this + 27))++);
        if ( v30 )
        {
          v38 = 0;
          *v30 = v15;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        std::unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>::~unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>(&v38);
        if ( ++v13 >= v39 )
          goto LABEL_37;
      }
      v3 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
        (const char *)0x8007000ELL,
        (int)hstringHeader.Reserved.Reserved1);
LABEL_45:
      std::unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>::~unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>(&v38);
      goto LABEL_46;
    }
LABEL_37:
    *((_BYTE *)this + 248) = 1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1AE,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
    (const char *)(unsigned int)v2,
    (int)hstringHeader.Reserved.Reserved1);
LABEL_48:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  return v3;
}

```

## disassembly

```asm
0x1800cdc30  push    rbp
0x1800cdc32  push    rbx
0x1800cdc33  push    rsi
0x1800cdc34  push    rdi
0x1800cdc35  push    r12
0x1800cdc37  push    r13
0x1800cdc39  push    r14
0x1800cdc3b  push    r15
0x1800cdc3d  lea     rbp, [rsp-1Fh]
0x1800cdc42  sub     rsp, 88h
0x1800cdc49  mov     rax, cs:__security_cookie
0x1800cdc50  xor     rax, rsp
0x1800cdc53  mov     [rbp+57h+var_50], rax
0x1800cdc57  mov     r14, rcx
0x1800cdc5a  xor     r13d, r13d
0x1800cdc5d  cmp     [rcx+0F8h], r13b
0x1800cdc64  jnz     loc_1800CE026
0x1800cdc6a  mov     [rbp+57h+var_58], r13
0x1800cdc6e  mov     [rbp+57h+var_88], r13
0x1800cdc72  lea     r9d, [r13+2Fh]; unsigned int
0x1800cdc76  lea     r8d, [r13+30h]; unsigned int
0x1800cdc7a  lea     rdx, ?RuntimeClass_Windows_Media_SpeechSynthesis_SpeechSynthesizer@@3QBGB; "Windows.Media.SpeechSynthesis.SpeechSyn"...
0x1800cdc81  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800cdc85  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800cdc8a  lea     rdx, [rbp+57h+var_58]
0x1800cdc8e  mov     rcx, [rbp+57h+var_88]
0x1800cdc92  call    ??$GetActivationFactory@V?$ComPtr@UIInstalledVoicesStatic@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInstalledVoicesStatic@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IInstalledVoicesStatic>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IInstalledVoicesStatic>>)
0x1800cdc97  mov     ebx, eax
0x1800cdc99  test    eax, eax
0x1800cdc9b  jns     short loc_1800CDCBA
0x1800cdc9d  mov     rcx, [rbp+5Fh]; this
0x1800cdca1  mov     r9d, eax; char *
0x1800cdca4  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800cdcab  mov     edx, 1AEh; void *
0x1800cdcb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdcb5  jmp     loc_1800CE0BE
0x1800cdcba  mov     [rbp+57h+var_78], r13
0x1800cdcbe  mov     rcx, [rbp+57h+var_58]
0x1800cdcc2  mov     rax, [rcx]
0x1800cdcc5  lea     rdx, [rbp+57h+var_78]
0x1800cdcc9  mov     rax, [rax+38h]
0x1800cdccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdcd2  mov     ebx, eax
0x1800cdcd4  mov     r12d, 80000000h
0x1800cdcda  lea     ecx, [rax+r12]
0x1800cdcde  mov     r15d, 80070002h
0x1800cdce4  test    r12d, ecx
0x1800cdce7  jnz     short loc_1800CDD0B
0x1800cdce9  cmp     eax, r15d
0x1800cdcec  jz      short loc_1800CDD0B
0x1800cdcee  mov     edx, 1B2h; void *
0x1800cdcf3  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800cdcfa  mov     r9d, eax; char *
0x1800cdcfd  mov     rcx, [rbp+5Fh]; this
0x1800cdd01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdd06  jmp     loc_1800CE0B4
0x1800cdd0b  mov     rbx, [rbp+57h+var_78]
0x1800cdd0f  test    rbx, rbx
0x1800cdd12  jz      short loc_1800CDD4F
0x1800cdd14  mov     rax, [rbx]
0x1800cdd17  mov     rsi, [rax+38h]
0x1800cdd1b  lea     rdi, [r14+0F0h]
0x1800cdd22  mov     rcx, [rdi]; string
0x1800cdd25  call    cs:__imp_WindowsDeleteString
0x1800cdd2c  nop     dword ptr [rax+rax+00h]
0x1800cdd31  mov     [rdi], r13
0x1800cdd34  mov     rdx, rdi
0x1800cdd37  mov     rcx, rbx
0x1800cdd3a  mov     rax, rsi
0x1800cdd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdd42  mov     ebx, eax
0x1800cdd44  test    eax, eax
0x1800cdd46  jns     short loc_1800CDD4F
0x1800cdd48  mov     edx, 1B6h
0x1800cdd4d  jmp     short loc_1800CDCF3
0x1800cdd4f  mov     [rbp+57h+var_80], r13
0x1800cdd53  mov     rdi, [rbp+57h+var_58]
0x1800cdd57  mov     rax, [rdi]
0x1800cdd5a  mov     rbx, [rax+30h]
0x1800cdd5e  lea     rcx, [rbp+57h+var_80]
0x1800cdd62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cdd67  lea     rdx, [rbp+57h+var_80]
0x1800cdd6b  mov     rcx, rdi
0x1800cdd6e  mov     rax, rbx
0x1800cdd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdd76  mov     ebx, eax
0x1800cdd78  lea     ecx, [rax+r12]
0x1800cdd7c  test    r12d, ecx
0x1800cdd7f  jnz     short loc_1800CDDA3
0x1800cdd81  cmp     eax, r15d
0x1800cdd84  jz      short loc_1800CDDA3
0x1800cdd86  mov     edx, 1BBh; void *
0x1800cdd8b  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800cdd92  mov     r9d, eax; char *
0x1800cdd95  mov     rcx, [rbp+5Fh]; this
0x1800cdd99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdd9e  jmp     loc_1800CE0AA
0x1800cdda3  mov     eax, r13d
0x1800cdda6  mov     [rbp+57h+var_60], eax
0x1800cdda9  mov     rcx, [rbp+57h+var_80]
0x1800cddad  test    rcx, rcx
0x1800cddb0  jz      short loc_1800CDDD2
0x1800cddb2  mov     rax, [rcx]
0x1800cddb5  lea     rdx, [rbp+57h+var_60]
0x1800cddb9  mov     rax, [rax+38h]
0x1800cddbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cddc2  mov     ebx, eax
0x1800cddc4  test    eax, eax
0x1800cddc6  jns     short loc_1800CDDCF
0x1800cddc8  mov     edx, 1C1h
0x1800cddcd  jmp     short loc_1800CDD8B
0x1800cddcf  mov     eax, [rbp+57h+var_60]
0x1800cddd2  mov     r15d, r13d
0x1800cddd5  test    eax, eax
0x1800cddd7  jz      loc_1800CE001
0x1800cdddd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cdde4  mov     ecx, 18h; unsigned __int64
0x1800cdde9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800cddee  mov     rsi, rax
0x1800cddf1  test    rax, rax
0x1800cddf4  jz      short loc_1800CDE03
0x1800cddf6  mov     [rax], r13
0x1800cddf9  mov     [rax+8], r13
0x1800cddfd  mov     [rax+10h], r13
0x1800cde01  jmp     short loc_1800CDE06
0x1800cde03  mov     rsi, r13
0x1800cde06  mov     [rbp+57h+var_68], rsi
0x1800cde0a  test    rsi, rsi
0x1800cde0d  jz      loc_1800CE082
0x1800cde13  mov     [rbp+57h+var_70], r13
0x1800cde17  mov     rdi, [rbp+57h+var_80]
0x1800cde1b  mov     rax, [rdi]
0x1800cde1e  mov     rbx, [rax+30h]
0x1800cde22  lea     rcx, [rbp+57h+var_70]
0x1800cde26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cde2b  lea     r8, [rbp+57h+var_70]
0x1800cde2f  mov     edx, r15d
0x1800cde32  mov     rcx, rdi
0x1800cde35  mov     rax, rbx
0x1800cde38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cde3d  mov     ebx, eax
0x1800cde3f  test    eax, eax
0x1800cde41  js      loc_1800CE07B
0x1800cde47  mov     rdi, [rbp+57h+var_70]
0x1800cde4b  mov     rax, [rdi]
0x1800cde4e  mov     rbx, [rax+38h]
0x1800cde52  lea     r12, [rsi+8]
0x1800cde56  mov     rcx, [r12]; string
0x1800cde5a  call    cs:__imp_WindowsDeleteString
0x1800cde61  nop     dword ptr [rax+rax+00h]
0x1800cde66  mov     [r12], r13
0x1800cde6a  mov     rdx, r12
0x1800cde6d  mov     rcx, rdi
0x1800cde70  mov     rax, rbx
0x1800cde73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cde78  mov     ebx, eax
0x1800cde7a  test    eax, eax
0x1800cde7c  js      loc_1800CE074
0x1800cde82  mov     rdi, [rbp+57h+var_70]
0x1800cde86  mov     rax, [rdi]
0x1800cde89  mov     rbx, [rax+30h]
0x1800cde8d  mov     rcx, [rsi]; string
0x1800cde90  call    cs:__imp_WindowsDeleteString
0x1800cde97  nop     dword ptr [rax+rax+00h]
0x1800cde9c  mov     [rsi], r13
0x1800cde9f  mov     rdx, rsi
0x1800cdea2  mov     rcx, rdi
0x1800cdea5  mov     rax, rbx
0x1800cdea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdead  mov     ebx, eax
0x1800cdeaf  test    eax, eax
0x1800cdeb1  js      loc_1800CE06D
0x1800cdeb7  mov     rdi, [rbp+57h+var_70]
0x1800cdebb  mov     rax, [rdi]
0x1800cdebe  mov     rbx, [rax+40h]
0x1800cdec2  lea     r13, [rsi+10h]
0x1800cdec6  mov     rcx, [r13+0]; string
0x1800cdeca  call    cs:__imp_WindowsDeleteString
0x1800cded1  nop     dword ptr [rax+rax+00h]
0x1800cded6  mov     qword ptr [r13+0], 0
0x1800cdede  mov     rdx, r13
0x1800cdee1  mov     rcx, rdi
0x1800cdee4  mov     rax, rbx
0x1800cdee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdeec  mov     ebx, eax
0x1800cdeee  test    eax, eax
0x1800cdef0  js      loc_1800CE049
0x1800cdef6  mov     [rbp+57h+result], 0
0x1800cdefd  lea     r8, [rbp+57h+result]; result
0x1800cdf01  mov     rdx, [r12]; string2
0x1800cdf05  mov     rcx, [r14+0F0h]; string1
0x1800cdf0c  call    cs:__imp_WindowsCompareStringOrdinal
0x1800cdf13  nop     dword ptr [rax+rax+00h]
0x1800cdf18  test    eax, eax
0x1800cdf1a  js      short loc_1800CDF54
0x1800cdf1c  cmp     [rbp+57h+result], 0
0x1800cdf20  jnz     short loc_1800CDF54
0x1800cdf22  xor     edx, edx; length
0x1800cdf24  mov     rcx, [r13+0]; string
0x1800cdf28  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cdf2f  nop     dword ptr [rax+rax+00h]
0x1800cdf34  mov     rdx, rax
0x1800cdf37  lea     rcx, [rbp+57h+hstringHeader]
0x1800cdf3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cdf40  nop
0x1800cdf41  lea     rdx, [rbp+57h+hstringHeader]
0x1800cdf45  call    ?SetDefaultVoiceLanguage@AddVoicesSingleton@Speech@SystemSettings@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::Speech::AddVoicesSingleton::SetDefaultVoiceLanguage(std::wstring const &)
0x1800cdf4a  nop
0x1800cdf4b  lea     rcx, [rbp+57h+hstringHeader]
0x1800cdf4f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cdf54  lea     rbx, [r14+0D0h]
0x1800cdf5b  mov     rdx, [rbx+8]
0x1800cdf5f  cmp     rdx, [rbx+18h]
0x1800cdf63  jnz     short loc_1800CDFC0
0x1800cdf65  inc     rdx
0x1800cdf68  mov     rcx, rbx
0x1800cdf6b  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardCompareHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardMergeHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@@@QEAAJ_K0@Z; CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800cdf70  mov     edi, eax
0x1800cdf72  xor     r13d, r13d
0x1800cdf75  test    eax, eax
0x1800cdf77  jns     short loc_1800CDFC3
0x1800cdf79  mov     rcx, [rbp+5Fh]; this
0x1800cdf7d  mov     r9d, eax; char *
0x1800cdf80  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800cdf87  mov     edx, 1D9h; void *
0x1800cdf8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdf91  nop
0x1800cdf92  lea     rcx, [rbp+57h+var_70]
0x1800cdf96  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cdf9b  nop
0x1800cdf9c  lea     rcx, [rbp+57h+var_68]
0x1800cdfa0  call    ??1?$unique_ptr@USChoice@?$CHStringTaggedSpeechPlatformListSetting@UVoice@TextToSpeech@Settings@SpeechPlatform@@@Speech@SystemSettings@@U?$default_delete@USChoice@?$CHStringTaggedSpeechPlatformListSetting@UVoice@TextToSpeech@Settings@SpeechPlatform@@@Speech@SystemSettings@@@std@@@std@@QEAA@XZ; std::unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>::~unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>(void)
0x1800cdfa5  nop
0x1800cdfa6  lea     rcx, [rbp+57h+var_80]
0x1800cdfaa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cdfaf  nop
0x1800cdfb0  lea     rcx, [rbp+57h+var_78]
0x1800cdfb4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cdfb9  mov     ebx, edi
0x1800cdfbb  jmp     loc_1800CE0BE
0x1800cdfc0  xor     r13d, r13d
0x1800cdfc3  inc     qword ptr [rbx+8]
0x1800cdfc7  mov     rdx, [rbx+8]
0x1800cdfcb  mov     rax, [rbx]
0x1800cdfce  dec     rdx
0x1800cdfd1  lea     rdx, [rax+rdx*8]
0x1800cdfd5  test    rdx, rdx
0x1800cdfd8  jz      short loc_1800CDFE1
0x1800cdfda  mov     [rbp+57h+var_68], r13
0x1800cdfde  mov     [rdx], rsi
0x1800cdfe1  lea     rcx, [rbp+57h+var_70]
0x1800cdfe5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cdfea  nop
0x1800cdfeb  lea     rcx, [rbp+57h+var_68]
0x1800cdfef  call    ??1?$unique_ptr@USChoice@?$CHStringTaggedSpeechPlatformListSetting@UVoice@TextToSpeech@Settings@SpeechPlatform@@@Speech@SystemSettings@@U?$default_delete@USChoice@?$CHStringTaggedSpeechPlatformListSetting@UVoice@TextToSpeech@Settings@SpeechPlatform@@@Speech@SystemSettings@@@std@@@std@@QEAA@XZ; std::unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>::~unique_ptr<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice,std::default_delete<SystemSettings::Speech::CHStringTaggedSpeechPlatformListSetting<SpeechPlatform::Settings::TextToSpeech::Voice>::SChoice>>(void)
0x1800cdff4  inc     r15d
0x1800cdff7  cmp     r15d, [rbp+57h+var_60]
0x1800cdffb  jb      loc_1800CDDDD
0x1800ce001  mov     byte ptr [r14+0F8h], 1
0x1800ce009  lea     rcx, [rbp+57h+var_80]
0x1800ce00d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce012  nop
0x1800ce013  lea     rcx, [rbp+57h+var_78]
0x1800ce017  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce01c  nop
0x1800ce01d  lea     rcx, [rbp+57h+var_58]
0x1800ce021  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce026  xor     eax, eax
0x1800ce028  mov     rcx, [rbp+57h+var_50]
0x1800ce02c  xor     rcx, rsp; StackCookie
0x1800ce02f  call    __security_check_cookie
0x1800ce034  add     rsp, 88h
0x1800ce03b  pop     r15
0x1800ce03d  pop     r14
0x1800ce03f  pop     r13
0x1800ce041  pop     r12
0x1800ce043  pop     rdi
0x1800ce044  pop     rsi
0x1800ce045  pop     rbx
0x1800ce046  pop     rbp
0x1800ce047  retn
0x1800ce049  mov     edx, 1CDh; void *
0x1800ce04e  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800ce055  mov     r9d, eax; char *
0x1800ce058  mov     rcx, [rbp+5Fh]; this
0x1800ce05c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce061  nop
0x1800ce062  lea     rcx, [rbp+57h+var_70]
0x1800ce066  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce06b  jmp     short loc_1800CE0A0
0x1800ce06d  mov     edx, 1CCh
0x1800ce072  jmp     short loc_1800CE04E
0x1800ce074  mov     edx, 1CBh
0x1800ce079  jmp     short loc_1800CE04E
0x1800ce07b  mov     edx, 1CAh
0x1800ce080  jmp     short loc_1800CE04E
0x1800ce082  mov     rcx, [rbp+5Fh]; this
0x1800ce086  mov     ebx, 8007000Eh
0x1800ce08b  mov     r9d, ebx; char *
0x1800ce08e  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
  ... truncated ...
```
