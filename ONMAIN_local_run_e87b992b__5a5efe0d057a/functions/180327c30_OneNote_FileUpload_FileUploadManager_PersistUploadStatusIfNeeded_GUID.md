# OneNote::FileUpload::FileUploadManager::PersistUploadStatusIfNeeded(_GUID)

- ea: `0x180327c30`
- end: `0x1803284c1`
- name: `?PersistUploadStatusIfNeeded@FileUploadManager@FileUpload@OneNote@@UEAAXU_GUID@@@Z`
- size: `2193`
- prototype: `void __fastcall(OneNote::FileUpload::FileUploadManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18006eaec`
- `0x1800769c0`
- `0x18009414c`
- `0x1800982ed`
- `0x180167860`
- `0x1801765e8`
- `0x1801adc70`
- `0x1801ae61c`
- `0x18023c350`
- `0x1802903f0`
- `0x18029ced0`
- `0x1802ad2b0`
- `0x1802ad37c`
- `0x1802e0c78`
- `0x1802e2190`
- `0x1802e2210`
- `0x1802e5170`
- `0x1802e5190`
- `0x180327c30`
- `0x18032b490`
- `0x180330d4c`
- `0x18033145c`
- `0x180389390`
- `0x18039a2f0`
- `0x1808d7d20`
- `0x180e9a714`
- `0x180e9cde4`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x18032848a`
- `MSVCP140!_Mtx_unlock` at `0x18032848a`
- `Mso30Win32Client!__imp_?GetTime64@Time@MsoCF@@QEBA_KXZ` at `0x1803280f4`
- `Mso30Win32Client!__imp_?GetTime64@Time@MsoCF@@QEBA_KXZ` at `0x1803280f4`
- `Mso20Win32Client!__imp_?FRegSetInt64@Orapi@Mso@@YA_NPEBU_msoreg@@_J@Z` at `0x180328112`
- `Mso20Win32Client!__imp_?FRegSetInt64@Orapi@Mso@@YA_NPEBU_msoreg@@_J@Z` at `0x180328112`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180328447`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180328447`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x180327d51`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x180327d51`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180327ccd`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180327ecf`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180327f4e`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180327fa6`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180328002`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x18032805b`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x1803280b4`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x18032816b`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x1803281be`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180327ccd`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180327ecf`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180327f4e`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180327fa6`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x180328002`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x18032805b`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x1803280b4`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x18032816b`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x1803281be`

## string_xrefs

- `0x180327f05`: `NotebookGOSID`
- `0x180327f71`: `FilePath`
- `0x1803280da`: `CreateDateTime`
- `0x180328354`: `PersistUploadStatusFailedToWriteToRegistry`

## pseudocode

```c
void __fastcall OneNote::FileUpload::FileUploadManager::PersistUploadStatusIfNeeded(
        OneNote::FileUpload::FileUploadManager *this,
        struct _GUID *a2)
{
  struct _Mtx_internal_imp_t *v3; // rbx
  OneNote::FileUpload *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r15
  unsigned __int64 v7; // r12
  unsigned __int64 v8; // r15
  const struct Mso::Telemetry::EventName *v9; // r8
  const struct Mso::Telemetry::EventName *v10; // r8
  bool v11; // zf
  char *v12; // rdi
  __int64 v13; // r14
  __int64 *v14; // r13
  __int64 v15; // rax
  __int64 v16; // r14
  bool v17; // di
  __int64 v18; // rax
  _QWORD *v19; // r8
  const wchar_t *v20; // rdx
  const wchar_t *v21; // rdx
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rdx
  const wchar_t *v24; // rdx
  const wchar_t *v25; // rdx
  const struct _msoreg *Time64; // rax
  __int64 v27; // r8
  const wchar_t *v28; // rdx
  const wchar_t *v29; // rdx
  __int64 v30; // rax
  _QWORD *v31; // r14
  __int64 v32; // rax
  char v33; // al
  const struct Mso::Telemetry::EventName *v34; // r8
  char v35; // [rsp+28h] [rbp-E0h] BYREF
  char v36; // [rsp+29h] [rbp-DFh] BYREF
  __int64 v37; // [rsp+30h] [rbp-D8h]
  struct Mso::Telemetry::IDetachedActivity *v38; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v39[2]; // [rsp+40h] [rbp-C8h] BYREF
  const char *v40; // [rsp+48h] [rbp-C0h]
  unsigned int v41[2]; // [rsp+50h] [rbp-B8h] BYREF
  const char *v42; // [rsp+58h] [rbp-B0h]
  _BYTE v43[24]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v44[32]; // [rsp+80h] [rbp-88h] BYREF
  char v45; // [rsp+A0h] [rbp-68h]
  _BYTE v46[8]; // [rsp+A8h] [rbp-60h] BYREF
  void *Buf1; // [rsp+B0h] [rbp-58h]
  _QWORD v48[2]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v49[24]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v50[32]; // [rsp+E0h] [rbp-28h] BYREF
  char v51; // [rsp+100h] [rbp-8h]
  _BYTE v52[24]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v53[40]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v54[24]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v55[40]; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v56[24]; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v57[40]; // [rsp+1A0h] [rbp+98h] BYREF
  _BYTE v58[24]; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v59[40]; // [rsp+1E0h] [rbp+D8h] BYREF
  _BYTE v60[24]; // [rsp+208h] [rbp+100h] BYREF
  _BYTE v61[40]; // [rsp+220h] [rbp+118h] BYREF
  _BYTE v62[24]; // [rsp+248h] [rbp+140h] BYREF
  _BYTE v63[40]; // [rsp+260h] [rbp+158h] BYREF
  _BYTE v64[24]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v65[40]; // [rsp+2A0h] [rbp+198h] BYREF
  _BYTE v66[24]; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE v67[40]; // [rsp+2E0h] [rbp+1D8h] BYREF
  _BYTE v68[24]; // [rsp+308h] [rbp+200h] BYREF
  _BYTE v69[40]; // [rsp+320h] [rbp+218h] BYREF
  _BYTE v70[24]; // [rsp+348h] [rbp+240h] BYREF
  _BYTE v71[40]; // [rsp+360h] [rbp+258h] BYREF
  _BYTE v72[448]; // [rsp+388h] [rbp+280h] BYREF
  _QWORD v73[4]; // [rsp+548h] [rbp+440h] BYREF
  _QWORD v74[4]; // [rsp+568h] [rbp+460h] BYREF
  _QWORD v75[4]; // [rsp+588h] [rbp+480h] BYREF
  _BYTE v76[32]; // [rsp+5A8h] [rbp+4A0h] BYREF
  _BYTE v77[32]; // [rsp+5C8h] [rbp+4C0h] BYREF
  _BYTE v78[32]; // [rsp+5E8h] [rbp+4E0h] BYREF
  void **v79; // [rsp+608h] [rbp+500h] BYREF
  void **v80; // [rsp+610h] [rbp+508h]
  const wchar_t *v81; // [rsp+618h] [rbp+510h]
  __int64 v82; // [rsp+620h] [rbp+518h]
  char *v83; // [rsp+628h] [rbp+520h]
  __int16 v84; // [rsp+630h] [rbp+528h]
  _BYTE v85[6]; // [rsp+632h] [rbp+52Ah] BYREF

  Buf1 = a2;
  v3 = (OneNote::FileUpload::FileUploadManager *)((char *)this + 8);
  std::_Mutex_base::lock((OneNote::FileUpload::FileUploadManager *)((char *)this + 8));
  if ( *((_QWORD *)this + 14) )
  {
    Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->((_QWORD *)this + 14);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 48LL))(v5);
    Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>((char *)this + 112);
  }
  v6 = *((_QWORD *)this + 24);
  if ( v6 )
  {
    v7 = OneNote::FileUpload::CountRegistryEntriesForPendingUploads(v4);
    v8 = v7 + v6;
    if ( MsoFRegSetWz((const struct _msoreg *)&vmsoridFileUploadsSchemaVersion, L"2.5") )
    {
      Mso::Orapi::InitForKey(v49, &vmsoridFileUploadsInProgressItem, L"Files");
      Mso::Orapi::InitForValue(v52, (unsigned __int64)v50 & -(__int64)(v51 != 0), L"Count", 4);
      if ( MsoFRegSetDw((const struct _msoreg *)((unsigned __int64)v53 & -(__int64)(v53[32] != 0)), v8) )
      {
        v11 = (OneNote::FileUpload::FileUploadManager *)((char *)this + 160) == 0;
        v12 = (char *)this + 160;
        v13 = *((_QWORD *)v12 + 3);
        v37 = v13;
        if ( v11 )
          v14 = 0;
        else
          v14 = *(__int64 **)v12;
        while ( v7 < v8 )
        {
          if ( v14 )
            v15 = *v14;
          else
            v15 = 0;
          v16 = *(_QWORD *)(*(_QWORD *)(v15 + 8) + 8 * (v13 & (*(_QWORD *)(v15 + 16) - 1LL)));
          *(_QWORD *)v41 = v16 + 192;
          v17 = !OneNote::FileUpload::NodeIdentifier::EnsureInit(
                   (OneNote::FileUpload::NodeIdentifier *)(v16 + 192),
                   *(struct OneNote::FileUpload::AFileUploadContext **)(v16 + 280));
          v18 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v85, v7);
          std::wstring::wstring(v76, v18, v85);
          std::operator+<wchar_t>(v75, L"File ", v76);
          std::wstring::~wstring(v76);
          v19 = v75;
          if ( v75[3] > 7u )
            v19 = (_QWORD *)v75[0];
          Mso::Orapi::InitForKey(v43, (unsigned __int64)v50 & -(__int64)(v51 != 0), v19);
          OneNote::FileUpload::NodeIdentifier::ToStrings(v16 + 192, v77);
          std::wstring::wstring(v74, v78);
          Mso::Orapi::InitForValue(v70, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"GUIDS", 1);
          if ( !v74[2] )
            goto LABEL_20;
          v20 = (const wchar_t *)v74;
          if ( v74[3] > 7u )
            v20 = (const wchar_t *)v74[0];
          if ( !MsoFRegSetWz((const struct _msoreg *)((unsigned __int64)v71 & -(__int64)(v71[32] != 0)), v20) )
LABEL_20:
            v17 = 1;
          std::wstring::wstring(v73, v77);
          Mso::Orapi::InitForValue(v68, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"NotebookGOSID", 1);
          if ( !v73[2] )
            goto LABEL_25;
          v21 = (const wchar_t *)v73;
          if ( v73[3] > 7u )
            v21 = (const wchar_t *)v73[0];
          if ( !MsoFRegSetWz((const struct _msoreg *)((unsigned __int64)v69 & -(__int64)(v69[32] != 0)), v21) )
LABEL_25:
            v17 = 1;
          Mso::Orapi::InitForValue(v66, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"FilePath", 1);
          v22 = (const wchar_t *)v16;
          if ( *(_QWORD *)(v16 + 24) > 7u )
            v22 = *(const wchar_t **)v16;
          if ( !MsoFRegSetWz((const struct _msoreg *)((unsigned __int64)v67 & -(__int64)(v67[32] != 0)), v22) )
            v17 = 1;
          Mso::Orapi::InitForValue(v64, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"OnedriveName", 1);
          v23 = (const wchar_t *)(v16 + 128);
          if ( *(_QWORD *)(v16 + 152) > 7u )
            v23 = *(const wchar_t **)v23;
          if ( !MsoFRegSetWz((const struct _msoreg *)((unsigned __int64)v65 & -(__int64)(v65[32] != 0)), v23) )
            v17 = 1;
          Mso::Orapi::InitForValue(v62, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"NotebookUrl", 1);
          v24 = (const wchar_t *)(v16 + 32);
          if ( *(_QWORD *)(v16 + 56) > 7u )
            v24 = *(const wchar_t **)v24;
          if ( !MsoFRegSetWz((const struct _msoreg *)((unsigned __int64)v63 & -(__int64)(v63[32] != 0)), v24) )
            v17 = 1;
          Mso::Orapi::InitForValue(v60, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"FallbackUrl", 1);
          v25 = (const wchar_t *)(v16 + 64);
          if ( *(_QWORD *)(v16 + 88) > 7u )
            v25 = *(const wchar_t **)v25;
          if ( !MsoFRegSetWz((const struct _msoreg *)((unsigned __int64)v61 & -(__int64)(v61[32] != 0)), v25) )
            v17 = 1;
          Mso::Orapi::InitForValue(v58, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"CreateDateTime", 11);
          Time64 = (const struct _msoreg *)MsoCF::Time::GetTime64((MsoCF::Time *)(v16 + 312));
          if ( !Mso::Orapi::FRegSetInt64((Mso::Orapi *)((unsigned __int64)v59 & -(__int64)(v59[32] != 0)), Time64, v27) )
            v17 = 1;
          Mso::Orapi::InitForValue(v56, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"SessionUrl", 1);
          v28 = (const wchar_t *)(v16 + 96);
          if ( *(_QWORD *)(v16 + 120) > 7u )
            v28 = *(const wchar_t **)v28;
          if ( !MsoFRegSetWz((const struct _msoreg *)((unsigned __int64)v57 & -(__int64)(v57[32] != 0)), v28) )
            v17 = 1;
          Mso::Orapi::InitForValue(v54, (unsigned __int64)v44 & -(__int64)(v45 != 0), L"OneDriveItemId", 1);
          v29 = (const wchar_t *)(v16 + 160);
          if ( *(_QWORD *)(v16 + 184) > 7u )
            v29 = *(const wchar_t **)v29;
          if ( !MsoFRegSetWz((const struct _msoreg *)((unsigned __int64)v55 & -(__int64)(v55[32] != 0)), v29) )
            v17 = 1;
          Mso::TCntPtr<FastAcc::Abstract::IElement>::TCntPtr<FastAcc::Abstract::IElement>(&v38, v16 + 304);
          if ( !v38 )
          {
            CrashWithRecovery(0x24CF584u, 0);
            __debugbreak();
          }
          Jot::Logging::Activity::Activity((Jot::Logging::Activity *)v72, v38);
          v35 = 1;
          v79 = &Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Logging::IStructuredTrace'};
          v80 = &Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Telemetry::IDataField'};
          v81 = L"UploadPaused";
          v82 = -1;
          v83 = &v35;
          v84 = 4;
          Jot::Logging::Activity::SetContext<Mso::Logging::StructuredObject<wchar_t const *,1>>(v72, &v79);
          v30 = Jot::Logging::Activity::Detach(v72, v46);
          Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=(v16 + 304, v30);
          Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v46);
          v31 = Buf1;
          if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
            goto LABEL_58;
          v32 = *(_QWORD *)(*(_QWORD *)v41 + 36LL) - *v31;
          if ( !v32 )
            v32 = *(_QWORD *)(*(_QWORD *)v41 + 44LL) - v31[1];
          if ( v32 )
LABEL_58:
            v33 = 0;
          else
            v33 = 1;
          v36 = v33;
          v79 = &Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Logging::IStructuredTrace'};
          v80 = &Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Telemetry::IDataField'};
          v81 = L"WasUploadOnActivePage";
          v82 = -1;
          v83 = &v36;
          v84 = 4;
          v48[0] = &off_1811DD080;
          v48[1] = "CloudFilesPersistedUpload";
          Jot::Logging::LogTraceTag<Jot::Logging::details::StructuredTraceImplementation<_GUID>>(
            587792709,
            v48,
            50,
            &v79);
          if ( v17 )
          {
            *(_QWORD *)v39 = &off_1811DD080;
            v40 = "PersistUploadStatusFailedToWriteToRegistry";
            Jot::Logging::LogUnexpectedTag((Jot::Logging *)0x3150419, (unsigned int)v39, v34);
          }
          v13 = ++v37;
          Jot::Logging::Activity::~Activity((Jot::Logging::Activity *)v72);
          Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(&v38);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v54);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v56);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v58);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v60);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v62);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v64);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v66);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v68);
          std::wstring::~wstring(v73);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v70);
          std::wstring::~wstring(v74);
          Jot::Memory::Reka::FeedbackCompositeString::~FeedbackCompositeString((Jot::Memory::Reka::FeedbackCompositeString *)v77);
          DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v43);
          std::wstring::~wstring(v75);
          ++v7;
        }
      }
      else
      {
        *(_QWORD *)v39 = &off_1811DD080;
        v40 = "UnableToPersistCountOfFiles";
        Jot::Logging::LogUnexpectedTag((Jot::Logging *)0x24D374D, (unsigned int)v39, v10);
      }
      DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v52);
      DynamicMsorid::~DynamicMsorid((DynamicMsorid *)v49);
    }
    else
    {
      *(_QWORD *)v41 = &off_1811DD080;
      v42 = "UnableToPersistSchemaVersion";
      Jot::Logging::LogUnexpectedTag((Jot::Logging *)0x24D374B, (unsigned int)v41, v9);
    }
  }
  _Mtx_unlock(v3);
}

```

## disassembly

```asm
0x180327c30  mov     rax, rsp
0x180327c33  mov     [rax+10h], rbx
0x180327c37  mov     [rax+18h], rsi
0x180327c3b  mov     [rax+20h], rdi
0x180327c3f  push    rbp
0x180327c40  push    r12
0x180327c42  push    r13
0x180327c44  push    r14
0x180327c46  push    r15
0x180327c48  lea     rbp, [rax-568h]
0x180327c4f  sub     rsp, 640h
0x180327c56  mov     rax, cs:__security_cookie
0x180327c5d  xor     rax, rsp
0x180327c60  mov     [rbp+560h+var_30], rax
0x180327c67  mov     [rbp+560h+Buf1], rdx
0x180327c6b  mov     rdi, rcx
0x180327c6e  lea     rbx, [rcx+8]
0x180327c72  mov     rcx, rbx; this
0x180327c75  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180327c7a  lea     rsi, [rdi+70h]
0x180327c7e  cmp     qword ptr [rsi], 0
0x180327c82  jz      short loc_180327CA4
0x180327c84  mov     rcx, rsi
0x180327c87  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180327c8c  mov     rdx, [rax]
0x180327c8f  mov     rcx, rax
0x180327c92  mov     rax, [rdx+30h]
0x180327c96  call    cs:__guard_dispatch_icall_fptr
0x180327c9c  mov     rcx, rsi
0x180327c9f  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x180327ca4  mov     r15, [rdi+0C0h]
0x180327cab  test    r15, r15
0x180327cae  jz      loc_180328487
0x180327cb4  call    ?CountRegistryEntriesForPendingUploads@FileUpload@OneNote@@YAIXZ; OneNote::FileUpload::CountRegistryEntriesForPendingUploads(void)
0x180327cb9  mov     r12d, eax
0x180327cbc  add     r15, r12
0x180327cbf  lea     rdx, a25; "2.5"
0x180327cc6  lea     rcx, ?vmsoridFileUploadsSchemaVersion@@3U_msoreg@@B; _msoreg const vmsoridFileUploadsSchemaVersion
0x180327ccd  call    cs:__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z; MsoFRegSetWz(_msoreg const *,wchar_t const *)
0x180327cd3  test    eax, eax
0x180327cd5  jnz     short loc_180327D03
0x180327cd7  lea     rsi, off_1811DD080
0x180327cde  mov     qword ptr [rsp+660h+var_618], rsi
0x180327ce3  lea     rax, aUnabletopersis_0; "UnableToPersistSchemaVersion"
0x180327cea  mov     [rsp+660h+var_610], rax
0x180327cef  lea     rdx, [rsp+660h+var_618]; unsigned int
0x180327cf4  mov     ecx, 24D374Bh; this
0x180327cf9  call    ?LogUnexpectedTag@Logging@Jot@@YAXKAEBUEventName@Telemetry@Mso@@@Z; Jot::Logging::LogUnexpectedTag(ulong,Mso::Telemetry::EventName const &)
0x180327cfe  jmp     loc_180328487
0x180327d03  lea     r8, aFiles; "Files"
0x180327d0a  lea     rdx, ?vmsoridFileUploadsInProgressItem@@3U_msoreg@@B; _msoreg const vmsoridFileUploadsInProgressItem
0x180327d11  lea     rcx, [rbp+560h+var_5A0]
0x180327d15  call    ?InitForKey@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_W@Z; Mso::Orapi::InitForKey(_msoreg const &,wchar_t const *)
0x180327d1a  mov     al, [rbp+560h+var_568]
0x180327d1d  neg     al
0x180327d1f  sbb     rdx, rdx
0x180327d22  lea     rax, [rbp+560h+var_588]
0x180327d26  and     rdx, rax
0x180327d29  mov     r9d, 4
0x180327d2f  lea     r8, aCount_1; "Count"
0x180327d36  lea     rcx, [rbp+560h+var_560]
0x180327d3a  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x180327d3f  mov     al, [rbp+560h+var_528]
0x180327d42  neg     al
0x180327d44  sbb     rcx, rcx
0x180327d47  lea     rax, [rbp+560h+var_548]
0x180327d4b  and     rcx, rax
0x180327d4e  mov     edx, r15d
0x180327d51  call    cs:__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z; MsoFRegSetDw(_msoreg const *,ulong)
0x180327d57  test    eax, eax
0x180327d59  jz      loc_18032844E
0x180327d5f  add     rdi, 0A0h
0x180327d66  mov     r14, [rdi+18h]
0x180327d6a  mov     [rsp+660h+var_638], r14
0x180327d6f  jz      short loc_180327D76
0x180327d71  mov     r13, [rdi]
0x180327d74  jmp     short loc_180327D79
0x180327d76  xor     r13d, r13d
0x180327d79  lea     rsi, off_1811DD080
0x180327d80  mov     edi, 1
0x180327d85  cmp     r12, r15
0x180327d88  jnb     loc_180328475
0x180327d8e  test    r13, r13
0x180327d91  jz      short loc_180327D99
0x180327d93  mov     rax, [r13+0]
0x180327d97  jmp     short loc_180327D9B
0x180327d99  xor     eax, eax
0x180327d9b  mov     rcx, [rax+10h]
0x180327d9f  sub     rcx, rdi
0x180327da2  and     rcx, r14
0x180327da5  mov     rax, [rax+8]
0x180327da9  mov     r14, [rax+rcx*8]
0x180327dad  lea     rax, [r14+0C0h]
0x180327db4  mov     qword ptr [rsp+660h+var_618], rax
0x180327db9  mov     rdx, [r14+118h]; struct OneNote::FileUpload::AFileUploadContext *
0x180327dc0  mov     rcx, rax; this
0x180327dc3  call    ?EnsureInit@NodeIdentifier@FileUpload@OneNote@@QEAA_NAEAUAFileUploadContext@23@@Z; OneNote::FileUpload::NodeIdentifier::EnsureInit(OneNote::FileUpload::AFileUploadContext &)
0x180327dc8  mov     dil, al
0x180327dcb  xor     dil, 1
0x180327dcf  mov     rdx, r12
0x180327dd2  lea     rcx, [rbp+560h+var_36]
0x180327dd9  call    ??$_UIntegral_to_buff@_W_K@std@@YAPEA_WPEA_W_K@Z; std::_UIntegral_to_buff<wchar_t,unsigned __int64>(wchar_t *,unsigned __int64)
0x180327dde  lea     r8, [rbp+560h+var_36]
0x180327de5  mov     rdx, rax
0x180327de8  lea     rcx, [rbp+560h+var_C0]
0x180327def  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x180327df4  lea     r8, [rbp+560h+var_C0]
0x180327dfb  lea     rdx, aFile_2; "File "
0x180327e02  lea     rcx, [rbp+560h+var_E0]
0x180327e09  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x180327e0e  lea     rcx, [rbp+560h+var_C0]; void *
0x180327e15  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180327e1a  lea     r8, [rbp+560h+var_E0]
0x180327e21  cmp     [rbp+560h+var_C8], 7
0x180327e29  cmova   r8, [rbp+560h+var_E0]
0x180327e31  mov     al, [rbp+560h+var_568]
0x180327e34  neg     al
0x180327e36  sbb     rdx, rdx
0x180327e39  lea     rax, [rbp+560h+var_588]
0x180327e3d  and     rdx, rax
0x180327e40  lea     rcx, [rsp+660h+var_600]
0x180327e45  call    ?InitForKey@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_W@Z; Mso::Orapi::InitForKey(_msoreg const &,wchar_t const *)
0x180327e4a  lea     rdx, [rbp+560h+var_A0]
0x180327e51  lea     rcx, [r14+0C0h]
0x180327e58  call    ?ToStrings@NodeIdentifier@FileUpload@OneNote@@QEAA?AV?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@XZ; OneNote::FileUpload::NodeIdentifier::ToStrings(void)
0x180327e5d  lea     rdx, [rbp+560h+var_80]
0x180327e64  lea     rcx, [rbp+560h+var_100]
0x180327e6b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180327e70  mov     al, [rbp+560h+var_5C8]
0x180327e73  neg     al
0x180327e75  sbb     rdx, rdx
0x180327e78  lea     rax, [rsp+660h+var_5E8]
0x180327e7d  and     rdx, rax
0x180327e80  mov     r9d, 1
0x180327e86  lea     r8, aGuids; "GUIDS"
0x180327e8d  lea     rcx, [rbp+560h+var_320]
0x180327e94  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x180327e99  cmp     [rbp+560h+var_F0], 0
0x180327ea1  jz      short loc_180327ED9
0x180327ea3  lea     rdx, [rbp+560h+var_100]
0x180327eaa  cmp     [rbp+560h+var_E8], 7
0x180327eb2  cmova   rdx, [rbp+560h+var_100]
0x180327eba  mov     al, [rbp+560h+var_2E8]
0x180327ec0  neg     al
0x180327ec2  sbb     rcx, rcx
0x180327ec5  lea     rax, [rbp+560h+var_308]
0x180327ecc  and     rcx, rax
0x180327ecf  call    cs:__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z; MsoFRegSetWz(_msoreg const *,wchar_t const *)
0x180327ed5  test    eax, eax
0x180327ed7  jnz     short loc_180327EDC
0x180327ed9  mov     dil, 1
0x180327edc  lea     rdx, [rbp+560h+var_A0]
0x180327ee3  lea     rcx, [rbp+560h+var_120]
0x180327eea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180327eef  mov     al, [rbp+560h+var_5C8]
0x180327ef2  neg     al
0x180327ef4  sbb     rdx, rdx
0x180327ef7  lea     rax, [rsp+660h+var_5E8]
0x180327efc  and     rdx, rax
0x180327eff  mov     r9d, 1
0x180327f05  lea     r8, aNotebookgosid_1; "NotebookGOSID"
0x180327f0c  lea     rcx, [rbp+560h+var_360]
0x180327f13  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x180327f18  cmp     [rbp+560h+var_110], 0
0x180327f20  jz      short loc_180327F58
0x180327f22  lea     rdx, [rbp+560h+var_120]
0x180327f29  cmp     [rbp+560h+var_108], 7
0x180327f31  cmova   rdx, [rbp+560h+var_120]
0x180327f39  mov     al, [rbp+560h+var_328]
0x180327f3f  neg     al
0x180327f41  sbb     rcx, rcx
0x180327f44  lea     rax, [rbp+560h+var_348]
0x180327f4b  and     rcx, rax
0x180327f4e  call    cs:__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z; MsoFRegSetWz(_msoreg const *,wchar_t const *)
0x180327f54  test    eax, eax
0x180327f56  jnz     short loc_180327F5B
0x180327f58  mov     dil, 1
0x180327f5b  mov     al, [rbp+560h+var_5C8]
0x180327f5e  neg     al
0x180327f60  sbb     rdx, rdx
0x180327f63  lea     rax, [rsp+660h+var_5E8]
0x180327f68  and     rdx, rax
0x180327f6b  mov     r9d, 1
0x180327f71  lea     r8, aFilepath_0; "FilePath"
0x180327f78  lea     rcx, [rbp+560h+var_3A0]
0x180327f7f  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x180327f84  mov     rdx, r14
0x180327f87  cmp     qword ptr [r14+18h], 7
0x180327f8c  jbe     short loc_180327F91
0x180327f8e  mov     rdx, [r14]
0x180327f91  mov     al, [rbp+560h+var_368]
0x180327f97  neg     al
0x180327f99  sbb     rcx, rcx
0x180327f9c  lea     rax, [rbp+560h+var_388]
0x180327fa3  and     rcx, rax
0x180327fa6  call    cs:__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z; MsoFRegSetWz(_msoreg const *,wchar_t const *)
0x180327fac  test    eax, eax
0x180327fae  mov     ecx, 1
0x180327fb3  cmovz   edi, ecx
0x180327fb6  mov     al, [rbp+560h+var_5C8]
0x180327fb9  neg     al
0x180327fbb  sbb     rdx, rdx
0x180327fbe  lea     rax, [rsp+660h+var_5E8]
0x180327fc3  and     rdx, rax
0x180327fc6  mov     r9d, ecx
0x180327fc9  lea     r8, aOnedrivename; "OnedriveName"
0x180327fd0  lea     rcx, [rbp+560h+var_3E0]
0x180327fd7  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x180327fdc  lea     rdx, [r14+80h]
0x180327fe3  cmp     qword ptr [rdx+18h], 7
0x180327fe8  jbe     short loc_180327FED
0x180327fea  mov     rdx, [rdx]
0x180327fed  mov     al, [rbp+560h+var_3A8]
0x180327ff3  neg     al
0x180327ff5  sbb     rcx, rcx
0x180327ff8  lea     rax, [rbp+560h+var_3C8]
0x180327fff  and     rcx, rax
0x180328002  call    cs:__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z; MsoFRegSetWz(_msoreg const *,wchar_t const *)
0x180328008  test    eax, eax
0x18032800a  mov     ecx, 1
0x18032800f  cmovz   edi, ecx
0x180328012  mov     al, [rbp+560h+var_5C8]
0x180328015  neg     al
0x180328017  sbb     rdx, rdx
0x18032801a  lea     rax, [rsp+660h+var_5E8]
0x18032801f  and     rdx, rax
0x180328022  mov     r9d, ecx
0x180328025  lea     r8, aNotebookurl_0; "NotebookUrl"
0x18032802c  lea     rcx, [rbp+560h+var_420]
0x180328033  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x180328038  lea     rdx, [r14+20h]
0x18032803c  cmp     qword ptr [rdx+18h], 7
0x180328041  jbe     short loc_180328046
0x180328043  mov     rdx, [rdx]
0x180328046  mov     al, [rbp+560h+var_3E8]
0x18032804c  neg     al
0x18032804e  sbb     rcx, rcx
0x180328051  lea     rax, [rbp+560h+var_408]
0x180328058  and     rcx, rax
0x18032805b  call    cs:__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z; MsoFRegSetWz(_msoreg const *,wchar_t const *)
0x180328061  test    eax, eax
0x180328063  mov     ecx, 1
0x180328068  cmovz   edi, ecx
0x18032806b  mov     al, [rbp+560h+var_5C8]
0x18032806e  neg     al
0x180328070  sbb     rdx, rdx
0x180328073  lea     rax, [rsp+660h+var_5E8]
0x180328078  and     rdx, rax
0x18032807b  mov     r9d, ecx
0x18032807e  lea     r8, aFallbackurl; "FallbackUrl"
0x180328085  lea     rcx, [rbp+560h+var_460]
0x18032808c  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x180328091  lea     rdx, [r14+40h]
0x180328095  cmp     qword ptr [rdx+18h], 7
0x18032809a  jbe     short loc_18032809F
0x18032809c  mov     rdx, [rdx]
0x18032809f  mov     al, [rbp+560h+var_428]
0x1803280a5  neg     al
0x1803280a7  sbb     rcx, rcx
0x1803280aa  lea     rax, [rbp+560h+var_448]
0x1803280b1  and     rcx, rax
0x1803280b4  call    cs:__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z; MsoFRegSetWz(_msoreg const *,wchar_t const *)
0x1803280ba  test    eax, eax
0x1803280bc  mov     eax, 1
0x1803280c1  cmovz   edi, eax
0x1803280c4  mov     al, [rbp+560h+var_5C8]
0x1803280c7  neg     al
0x1803280c9  sbb     rdx, rdx
0x1803280cc  lea     rax, [rsp+660h+var_5E8]
0x1803280d1  and     rdx, rax
0x1803280d4  mov     r9d, 0Bh
0x1803280da  lea     r8, aCreatedatetime; "CreateDateTime"
0x1803280e1  lea     rcx, [rbp+560h+var_4A0]
0x1803280e8  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x1803280ed  lea     rcx, [r14+138h]
0x1803280f4  call    cs:__imp_?GetTime64@Time@MsoCF@@QEBA_KXZ; MsoCF::Time::GetTime64(void)
0x1803280fa  mov     cl, [rbp+560h+var_468]
0x180328100  neg     cl
0x180328102  sbb     rcx, rcx
0x180328105  lea     rdx, [rbp+560h+var_488]
0x18032810c  and     rcx, rdx
0x18032810f  mov     rdx, rax
0x180328112  call    cs:__imp_?FRegSetInt64@Orapi@Mso@@YA_NPEBU_msoreg@@_J@Z; Mso::Orapi::FRegSetInt64(_msoreg const *,__int64)
0x180328118  test    al, al
0x18032811a  mov     ecx, 1
0x18032811f  cmovz   edi, ecx
0x180328122  mov     al, [rbp+560h+var_5C8]
0x180328125  neg     al
0x180328127  sbb     rdx, rdx
0x18032812a  lea     rax, [rsp+660h+var_5E8]
0x18032812f  and     rdx, rax
0x180328132  mov     r9d, ecx
0x180328135  lea     r8, aSessionurl; "SessionUrl"
0x18032813c  lea     rcx, [rbp+560h+var_4E0]
0x180328143  call    ?InitForValue@Orapi@Mso@@YA?AVDynamicMsorid@@AEBU_msoreg@@PEB_WW4RegValueType@@@Z; Mso::Orapi::InitForValue(_msoreg const &,wchar_t const *,RegValueType)
0x180328148  lea     rdx, [r14+60h]
0x18032814c  cmp     qword ptr [rdx+18h], 7
0x180328151  jbe     short loc_180328156
0x180328153  mov     rdx, [rdx]
0x180328156  mov     al, [rbp+560h+var_4A8]
  ... truncated ...
```
