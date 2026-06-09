# RadioManager::CreateMediaManager(_GUID const &,RadioManager *)

- ea: `0x18001df88`
- end: `0x18001e72e`
- name: `?CreateMediaManager@RadioManager@@CAXAEBU_GUID@@PEAV1@@Z`
- size: `1958`
- prototype: `void __fastcall(const struct _GUID *, struct RadioManager *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d494`

## callees

- `0x180001290`
- `0x180001e6c`
- `0x180003fa0`
- `0x1800042b0`
- `0x18000521c`
- `0x180006200`
- `0x180006a2c`
- `0x18000760c`
- `0x180007cc0`
- `0x180009350`
- `0x18000b814`
- `0x18000c2a4`
- `0x18000c300`
- `0x18000d2a0`
- `0x18000d784`
- `0x1800199f8`
- `0x18001a3c0`
- `0x18001a7bc`
- `0x18001d408`
- `0x18001df88`
- `0x18001ff24`
- `0x18002195c`
- `0x180021d48`
- `0x1800222d0`
- `0x180022a80`
- `0x180023308`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e048`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e126`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e4d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e048`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e126`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e4d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e196`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e196`

## string_xrefs

- `0x18001e0b1`: `RadioManager::CreateMediaManager Exited - MediaRadioManager is already pended trying to be created`
- `0x18001e3de`: `RadioManager::CreateMediaManager Exited - MediaRadioManager is already in the list`
- `0x18001e6e2`: `Failed to CoCreateInstance for a new IMediaRadioManager`

## pseudocode

```c
void __fastcall RadioManager::CreateMediaManager(const struct _GUID *a1, struct RadioManager *a2)
{
  struct MEDIA_RADIO_MANAGER *v3; // rcx
  int v4; // r8d
  int v5; // r9d
  struct MEDIA_RADIO_MANAGER *v6; // r15
  const char *v7; // rbx
  char *v8; // rcx
  struct _GUID *v9; // r8
  struct _GUID *i; // rdx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  const char *v14; // rbx
  __int64 j; // rcx
  HRESULT v16; // ebx
  __int64 *v17; // rax
  const char *v18; // r9
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  unsigned int k; // r14d
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, const char **); // rbx
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  int v40; // eax
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  const char *v46; // rax
  char *v47; // rdx
  const char *v48; // rbx
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  int v52; // eax
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  char *v56; // rcx
  struct MEDIA_RADIO_MANAGER **v57; // rdx
  int v58; // ecx
  int v59; // r8d
  int v60; // r9d
  const char *v61; // rax
  __int64 v62; // rax
  __int64 v63; // r8
  int v64; // r9d
  unsigned int v65; // eax
  void *v66; // rdx
  unsigned int v67; // r8d
  int ppv; // [rsp+20h] [rbp-59h]
  int v69; // [rsp+28h] [rbp-51h]
  const char *v70; // [rsp+40h] [rbp-39h] BYREF
  const char *v71; // [rsp+48h] [rbp-31h] BYREF
  const char *v72; // [rsp+50h] [rbp-29h] BYREF
  bool v73; // [rsp+58h] [rbp-21h]
  char v74; // [rsp+5Ah] [rbp-1Fh]
  bool v75; // [rsp+5Bh] [rbp-1Eh]
  _QWORD v76[2]; // [rsp+60h] [rbp-19h] BYREF
  char v77; // [rsp+70h] [rbp-9h]
  RadioManager *v78; // [rsp+78h] [rbp-1h] BYREF
  const char *v79; // [rsp+80h] [rbp+7h] BYREF
  const char *v80; // [rsp+88h] [rbp+Fh] BYREF
  struct MEDIA_RADIO_MANAGER *v81; // [rsp+90h] [rbp+17h] BYREF
  __int64 v82; // [rsp+98h] [rbp+1Fh] BYREF
  LPVOID v83; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v78 = a2;
  if ( (unsigned int)dword_180037050 > 4 )
  {
    v79 = RmGuidToMediaTypeString(a1);
    v81 = v3;
    v70 = "Processing MediaRadioManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
      (_DWORD)v3,
      (unsigned int)byte_18002EAC3,
      v4,
      v5,
      (__int64)&v70,
      (__int64)&v81,
      (__int64)&v79);
  }
  v6 = (struct MEDIA_RADIO_MANAGER *)operator new(0x138u);
  v71 = (const char *)v6;
  *(_QWORD *)v6 = 0;
  *(_OWORD *)((char *)v6 + 8) = 0;
  WcmCommon::ThreadPoolProcessLatestWorkItem<2>::ThreadPoolProcessLatestWorkItem<2>((char *)v6 + 24);
  v81 = v6;
  *(struct _GUID *)((char *)v6 + 8) = *a1;
  v7 = (char *)v78 + 352;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v78 + 352));
  v79 = v7;
  v8 = (char *)v78 + 392;
  v9 = (struct _GUID *)*((_QWORD *)v78 + 50);
  for ( i = (struct _GUID *)*((_QWORD *)v78 + 49); i != v9; ++i )
  {
    if ( *(_QWORD *)&i->Data1 == *(_QWORD *)&a1->Data1 && *(_QWORD *)i->Data4 == *(_QWORD *)a1->Data4 )
    {
      if ( (unsigned int)dword_180037050 > 4 )
      {
        v70 = RmGuidToMediaTypeString(a1);
        v72 = (const char *)a1;
        v80 = "RadioManager::CreateMediaManager Exited - MediaRadioManager is already pended trying to be created";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)&word_18002EA6E,
          v12,
          v13,
          (__int64)&v80,
          (__int64)&v72,
          (__int64)&v70);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v79);
      goto LABEL_62;
    }
  }
  if ( v9 == *((struct _GUID **)v78 + 51) )
  {
    std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v8, *((_QWORD *)v78 + 50), a1);
  }
  else
  {
    *v9 = *a1;
    *((_QWORD *)v8 + 1) += 16LL;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v79);
  v76[0] = &v78;
  v76[1] = a1;
  v77 = 1;
  v14 = (char *)v78 + 240;
  EnterCriticalSection((LPCRITICAL_SECTION)v78 + 6);
  v79 = v14;
  for ( j = *((_QWORD *)v78 + 35); ; j += 8 )
  {
    if ( j == *((_QWORD *)v78 + 36) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v79);
      v83 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
      v16 = CoCreateInstance(a1, 0, 0x17u, &GUID_6cfdcab5_fc47_42a5_9241_074b58830e73, &v83);
      if ( v16 < 0 )
      {
        if ( (unsigned int)dword_180037050 > 2 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180037050, 0) )
        {
          LODWORD(v80) = v16;
          v61 = RmGuidToMediaTypeString(a1);
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v71, v61);
          v79 = (const char *)a1;
          v62 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                  &v70,
                  "Failed to CoCreateInstance for a new IMediaRadioManager");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&v79,
            (unsigned int)byte_18002E9BB,
            v63,
            v64,
            v62,
            (__int64)&v79,
            v63,
            (__int64)&v80);
        }
        v65 = wil::verify_hresult<long>((unsigned int)v16);
        wil::details::in1diag3::Throw_Hr(retaddr, v66, v67, (const char *)v65, ppv);
      }
      v70 = (const char *)v83;
      v17 = (__int64 *)Microsoft::WRL::Details::Make<MediaRadioManagerInternal,IMediaRadioManager *,RadioManager * &>(
                         &v79,
                         &v70,
                         &v78);
      v19 = *v17;
      *v17 = 0;
      v20 = *(_QWORD *)v6;
      v21 = v19 + 8;
      v22 = -v19;
      *(_QWORD *)v6 = v21 & -(__int64)(v22 != 0);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v79 )
      {
        v79 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMediaRadioManagerNotifySink,IMediaRadioManagerInternal>::Release();
      }
      if ( !*(_QWORD *)v6 && (unsigned int)dword_180037050 > 2 )
      {
        LODWORD(v80) = v16;
        v79 = RmGuidToMediaTypeString(a1);
        v70 = (const char *)a1;
        v72 = "NULL_ALLOC for internal Media Manager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v23,
          (unsigned int)byte_18002E95D,
          v24,
          v25,
          (__int64)&v72,
          (__int64)&v70,
          (__int64)&v79,
          (__int64)&v80);
      }
      if ( !*(_QWORD *)v6 )
        wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x76A, v22, v18);
      v82 = 0;
      v26 = *(_QWORD *)v6;
      v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v6 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      v28 = v27(v26, &v82);
      if ( v28 < 0 )
      {
        if ( (unsigned int)dword_180037050 > 2 )
        {
          v46 = "IMediaRadioManagerInternal::GetRadioInstances failed";
          v47 = byte_18002E7B5;
          goto LABEL_48;
        }
      }
      else
      {
        LODWORD(v80) = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, const char **))(*(_QWORD *)v82 + 24LL))(v82, &v80);
        if ( v28 >= 0 )
        {
          if ( (unsigned int)dword_180037050 > 4 )
          {
            LODWORD(v72) = (_DWORD)v80;
            v79 = RmGuidToMediaTypeString(a1);
            v70 = (const char *)a1;
            v71 = "Processing MediaRadioManager";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v31,
              (unsigned int)byte_18002E8E1,
              v32,
              v33,
              (__int64)&v71,
              (__int64)&v70,
              (__int64)&v79,
              (__int64)&v72);
          }
          for ( k = 0; k < (unsigned int)v80; ++k )
          {
            v79 = 0;
            v35 = v82;
            v36 = *(__int64 (__fastcall **)(__int64, _QWORD, const char **))(*(_QWORD *)v82 + 32LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
            v37 = v36(v35, k, &v79);
            if ( v37 < 0 )
            {
              if ( (unsigned int)dword_180037050 > 2 )
              {
                LODWORD(v72) = v37;
                LODWORD(v70) = k;
                v71 = "IRadioInstanceCollection::GetAt failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v37,
                  (unsigned int)byte_18002E841,
                  v38,
                  v39,
                  (__int64)&v71,
                  (__int64)&v70,
                  (__int64)&v72);
              }
            }
            else
            {
              LOBYTE(v69) = 0;
              v40 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, const char *, _QWORD, int, _DWORD))(*((_QWORD *)v78 + 4) + 24LL))(
                      (char *)v78 + 32,
                      0,
                      0,
                      v79,
                      0,
                      v69,
                      0);
              if ( v40 < 0 && (unsigned int)dword_180037050 > 2 )
              {
                LODWORD(v72) = v40;
                v71 = "IUIRadioManagerInternal::InsertJob(RM_JOB::INSTANCE_ADD) failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  dword_180037050,
                  (unsigned int)byte_18002E89B,
                  v41,
                  v42,
                  (__int64)&v71,
                  (__int64)&v72);
              }
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
          }
          goto LABEL_49;
        }
        if ( (unsigned int)dword_180037050 > 2 )
        {
          v46 = "IRadioInstanceCollection::GetCount failed";
          v47 = byte_18002E7FB;
LABEL_48:
          v71 = v46;
          LODWORD(v70) = v28;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v28,
            (_DWORD)v47,
            v29,
            v30,
            (__int64)&v71,
            (__int64)&v70);
        }
      }
LABEL_49:
      v48 = (char *)v78 + 240;
      EnterCriticalSection((LPCRITICAL_SECTION)v78 + 6);
      v80 = v48;
      ProtectedSystemState::GetSystemState((char *)v78 + 48, &v72);
      if ( v74 )
      {
        if ( (unsigned int)dword_180037050 > 4 )
        {
          v71 = RmGuidToMediaTypeString(a1);
          v79 = (const char *)a1;
          v70 = "Immediately queuing a workitem to change radio state on the MediaRadioManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
            v49,
            (unsigned int)&unk_18002E760,
            v50,
            v51,
            (__int64)&v70,
            (__int64)&v79,
            (__int64)&v71);
        }
        RadioManager::_RefreshPreferredMediaManager(v78, v75);
        v52 = RadioManager::_SetSysRadio(v78, v73, v75, v6);
        if ( v52 < 0 && (unsigned int)dword_180037050 > 2 )
        {
          LODWORD(v70) = v52;
          v71 = RmGuidToMediaTypeString(a1);
          v79 = (const char *)a1;
          v72 = "RadioManager::_SetSysRadio failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v53,
            (unsigned int)word_18002E702,
            v54,
            v55,
            (__int64)&v72,
            (__int64)&v79,
            (__int64)&v71,
            (__int64)&v70);
        }
      }
      v56 = (char *)v78 + 280;
      v57 = (struct MEDIA_RADIO_MANAGER **)*((_QWORD *)v78 + 36);
      if ( v57 == *((struct MEDIA_RADIO_MANAGER ***)v78 + 37) )
      {
        std::vector<std::unique_ptr<MEDIA_RADIO_MANAGER>>::_Emplace_reallocate<std::unique_ptr<MEDIA_RADIO_MANAGER>>(
          v56,
          v57,
          &v81);
      }
      else
      {
        v81 = 0;
        *v57 = v6;
        *((_QWORD *)v56 + 1) += 8LL;
      }
      if ( (unsigned int)dword_180037050 > 4 )
      {
        v71 = RmGuidToMediaTypeString(a1);
        v79 = (const char *)a1;
        v70 = "MediaRadioManager added to list of Media Managers";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          v58,
          (unsigned int)byte_18002E6AD,
          v59,
          v60,
          (__int64)&v70,
          (__int64)&v79,
          (__int64)&v71);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v80);
      RadioManager::_NotifySysRadioChanged(v78);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
      goto LABEL_61;
    }
    if ( *(_QWORD *)(*(_QWORD *)j + 8LL) == *(_QWORD *)&a1->Data1
      && *(_QWORD *)(*(_QWORD *)j + 16LL) == *(_QWORD *)a1->Data4 )
    {
      break;
    }
  }
  if ( (unsigned int)dword_180037050 > 4 )
  {
    v70 = RmGuidToMediaTypeString(a1);
    v72 = (const char *)a1;
    v80 = "RadioManager::CreateMediaManager Exited - MediaRadioManager is already in the list";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
      v43,
      (unsigned int)byte_18002EA19,
      v44,
      v45,
      (__int64)&v80,
      (__int64)&v72,
      (__int64)&v70);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v79);
LABEL_61:
  v77 = 0;
  RadioManager::CreateMediaManager_::_2_::_lambda_2_::operator()(v76);
LABEL_62:
  std::unique_ptr<MEDIA_RADIO_MANAGER>::~unique_ptr<MEDIA_RADIO_MANAGER>(&v81);
}

```

## disassembly

```asm
0x18001df88  mov     [rsp-8+arg_10], rbx
0x18001df8d  mov     [rsp-8+arg_18], rsi
0x18001df92  push    rbp
0x18001df93  push    rdi
0x18001df94  push    r12
0x18001df96  push    r14
0x18001df98  push    r15
0x18001df9a  lea     rbp, [rsp-37h]
0x18001df9f  sub     rsp, 0B0h
0x18001dfa6  mov     rax, cs:__security_cookie
0x18001dfad  xor     rax, rsp
0x18001dfb0  mov     [rbp+57h+var_28], rax
0x18001dfb4  mov     rsi, rcx
0x18001dfb7  mov     [rbp+57h+var_58], rdx
0x18001dfbb  mov     eax, cs:dword_180037050
0x18001dfc1  lea     r14, aProcessingMedi; "Processing MediaRadioManager"
0x18001dfc8  cmp     eax, 4
0x18001dfcb  jbe     short loc_18001E005
0x18001dfcd  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001dfd2  mov     [rbp+57h+var_50], rax
0x18001dfd6  mov     [rbp+57h+var_40], rcx
0x18001dfda  mov     [rbp+57h+var_90], r14
0x18001dfde  lea     rax, [rbp+57h+var_50]
0x18001dfe2  mov     [rsp+0D0h+var_A0], rax
0x18001dfe7  lea     rax, [rbp+57h+var_40]
0x18001dfeb  mov     [rsp+0D0h+var_A8], rax
0x18001dff0  lea     rax, [rbp+57h+var_90]
0x18001dff4  mov     [rsp+0D0h+ppv], rax
0x18001dff9  lea     rdx, byte_18002EAC3
0x18001e000  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18001e005  mov     ecx, 138h; Size
0x18001e00a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e00f  mov     r15, rax
0x18001e012  mov     [rbp+57h+var_88], rax
0x18001e016  xor     r12d, r12d
0x18001e019  mov     [rax], r12
0x18001e01c  xorps   xmm0, xmm0
0x18001e01f  movups  xmmword ptr [rax+8], xmm0
0x18001e023  lea     rcx, [rax+18h]
0x18001e027  call    ??0?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAA@K@Z; WcmCommon::ThreadPoolProcessLatestWorkItem<2>::ThreadPoolProcessLatestWorkItem<2>(ulong)
0x18001e02c  nop
0x18001e02d  mov     [rbp+57h+var_40], r15
0x18001e031  movups  xmm0, xmmword ptr [rsi]
0x18001e034  movdqu  xmmword ptr [r15+8], xmm0
0x18001e03a  mov     rbx, [rbp+57h+var_58]
0x18001e03e  add     rbx, 160h
0x18001e045  mov     rcx, rbx; lpCriticalSection
0x18001e048  call    cs:__imp_EnterCriticalSection
0x18001e04e  mov     [rbp+57h+var_50], rbx
0x18001e052  mov     rcx, [rbp+57h+var_58]
0x18001e056  add     rcx, 188h
0x18001e05d  mov     r8, [rcx+8]
0x18001e061  mov     rdx, [rcx]
0x18001e064  jmp     short loc_18001E07C
0x18001e066  mov     rax, [rdx]
0x18001e069  cmp     rax, [rsi]
0x18001e06c  jnz     short loc_18001E078
0x18001e06e  mov     rax, [rdx+8]
0x18001e072  cmp     rax, [rsi+8]
0x18001e076  jz      short loc_18001E096
0x18001e078  add     rdx, 10h
0x18001e07c  cmp     rdx, r8
0x18001e07f  jnz     short loc_18001E066
0x18001e081  cmp     r8, [rcx+10h]
0x18001e085  jz      short loc_18001E0F2
0x18001e087  movups  xmm0, xmmword ptr [rsi]
0x18001e08a  movdqu  xmmword ptr [r8], xmm0
0x18001e08f  add     qword ptr [rcx+8], 10h
0x18001e094  jmp     short loc_18001E0FF
0x18001e096  mov     eax, cs:dword_180037050
0x18001e09c  cmp     eax, 4
0x18001e09f  jbe     short loc_18001E0E4
0x18001e0a1  mov     rcx, rsi; struct _GUID *
0x18001e0a4  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001e0a9  mov     [rbp+57h+var_90], rax
0x18001e0ad  mov     [rbp+57h+var_80], rsi
0x18001e0b1  lea     rax, aRadiomanagerCr; "RadioManager::CreateMediaManager Exited"...
0x18001e0b8  mov     [rbp+57h+var_48], rax
0x18001e0bc  lea     rax, [rbp+57h+var_90]
0x18001e0c0  mov     [rsp+0D0h+var_A0], rax
0x18001e0c5  lea     rax, [rbp+57h+var_80]
0x18001e0c9  mov     [rsp+0D0h+var_A8], rax
0x18001e0ce  lea     rax, [rbp+57h+var_48]
0x18001e0d2  mov     [rsp+0D0h+ppv], rax
0x18001e0d7  lea     rdx, word_18002EA6E
0x18001e0de  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18001e0e3  nop
0x18001e0e4  lea     rcx, [rbp+57h+var_50]
0x18001e0e8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001e0ed  jmp     loc_18001E672
0x18001e0f2  mov     r8, rsi
0x18001e0f5  mov     rdx, [rcx+8]
0x18001e0f9  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x18001e0fe  nop
0x18001e0ff  lea     rcx, [rbp+57h+var_50]
0x18001e103  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001e108  lea     rax, [rbp+57h+var_58]
0x18001e10c  mov     [rbp+57h+var_70], rax
0x18001e110  mov     [rbp+57h+var_68], rsi
0x18001e114  mov     [rbp+57h+var_60], 1
0x18001e118  mov     rbx, [rbp+57h+var_58]
0x18001e11c  add     rbx, 0F0h
0x18001e123  mov     rcx, rbx; lpCriticalSection
0x18001e126  call    cs:__imp_EnterCriticalSection
0x18001e12c  mov     [rbp+57h+var_50], rbx
0x18001e130  mov     rax, [rbp+57h+var_58]
0x18001e134  mov     rcx, [rax+118h]
0x18001e13b  mov     r8, [rax+120h]
0x18001e142  jmp     short loc_18001E162
0x18001e144  mov     rdx, [rcx]
0x18001e147  mov     rax, [rdx+8]
0x18001e14b  cmp     rax, [rsi]
0x18001e14e  jnz     short loc_18001E15E
0x18001e150  mov     rax, [rdx+10h]
0x18001e154  cmp     rax, [rsi+8]
0x18001e158  jz      loc_18001E3C3
0x18001e15e  add     rcx, 8
0x18001e162  cmp     rcx, r8
0x18001e165  jnz     short loc_18001E144
0x18001e167  lea     rcx, [rbp+57h+var_50]
0x18001e16b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001e170  mov     [rbp+57h+var_30], r12
0x18001e174  lea     rcx, [rbp+57h+var_30]
0x18001e178  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e17d  lea     rax, [rbp+57h+var_30]
0x18001e181  mov     [rsp+0D0h+ppv], rax; ppv
0x18001e186  lea     r9, _GUID_6cfdcab5_fc47_42a5_9241_074b58830e73; riid
0x18001e18d  xor     edx, edx; pUnkOuter
0x18001e18f  lea     r8d, [rdx+17h]; dwClsContext
0x18001e193  mov     rcx, rsi; rclsid
0x18001e196  call    cs:__imp_CoCreateInstance
0x18001e19c  mov     ebx, eax
0x18001e19e  test    eax, eax
0x18001e1a0  js      loc_18001E6AE
0x18001e1a6  mov     rax, [rbp+57h+var_30]
0x18001e1aa  mov     [rbp+57h+var_90], rax
0x18001e1ae  lea     r8, [rbp+57h+var_58]
0x18001e1b2  lea     rdx, [rbp+57h+var_90]
0x18001e1b6  lea     rcx, [rbp+57h+var_50]
0x18001e1ba  call    ??$Make@VMediaRadioManagerInternal@@PEAUIMediaRadioManager@@AEAPEAVRadioManager@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VMediaRadioManagerInternal@@@12@$$QEAPEAUIMediaRadioManager@@AEAPEAVRadioManager@@@Z; Microsoft::WRL::Details::Make<MediaRadioManagerInternal,IMediaRadioManager *,RadioManager * &>(IMediaRadioManager * &&,RadioManager * &)
0x18001e1bf  mov     r8, [rax]
0x18001e1c2  mov     [rax], r12
0x18001e1c5  mov     rcx, [r15]
0x18001e1c8  lea     rdx, [r8+8]
0x18001e1cc  neg     r8
0x18001e1cf  sbb     rax, rax
0x18001e1d2  and     rax, rdx
0x18001e1d5  mov     [r15], rax
0x18001e1d8  test    rcx, rcx
0x18001e1db  jz      short loc_18001E1EA
0x18001e1dd  mov     rax, [rcx]
0x18001e1e0  mov     rax, [rax+10h]
0x18001e1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1e9  nop
0x18001e1ea  mov     rcx, [rbp+57h+var_50]
0x18001e1ee  test    rcx, rcx
0x18001e1f1  jz      short loc_18001E1FC
0x18001e1f3  mov     [rbp+57h+var_50], r12
0x18001e1f7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMediaRadioManagerNotifySink@@UIMediaRadioManagerInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMediaRadioManagerNotifySink,IMediaRadioManagerInternal>::Release(void)
0x18001e1fc  cmp     [r15], r12
0x18001e1ff  jnz     short loc_18001E25A
0x18001e201  mov     eax, cs:dword_180037050
0x18001e207  cmp     eax, 2
0x18001e20a  jbe     short loc_18001E25A
0x18001e20c  mov     dword ptr [rbp+57h+var_48], ebx
0x18001e20f  mov     rcx, rsi; struct _GUID *
0x18001e212  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001e217  mov     [rbp+57h+var_50], rax
0x18001e21b  mov     [rbp+57h+var_90], rsi
0x18001e21f  lea     rax, aNullAllocForIn; "NULL_ALLOC for internal Media Manager"
0x18001e226  mov     [rbp+57h+var_80], rax
0x18001e22a  lea     rax, [rbp+57h+var_48]
0x18001e22e  mov     [rsp+0D0h+var_98], rax
0x18001e233  lea     rax, [rbp+57h+var_50]
0x18001e237  mov     [rsp+0D0h+var_A0], rax
0x18001e23c  lea     rax, [rbp+57h+var_90]
0x18001e240  mov     [rsp+0D0h+var_A8], rax
0x18001e245  lea     rax, [rbp+57h+var_80]
0x18001e249  mov     [rsp+0D0h+ppv], rax
0x18001e24e  lea     rdx, byte_18002E95D
0x18001e255  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001e25a  mov     rcx, [rbp+5Fh]; this
0x18001e25e  cmp     [r15], r12
0x18001e261  jz      loc_18001E6A3
0x18001e267  mov     [rbp+57h+var_38], r12
0x18001e26b  mov     rdi, [r15]
0x18001e26e  mov     rax, [rdi]
0x18001e271  mov     rbx, [rax+18h]
0x18001e275  lea     rcx, [rbp+57h+var_38]
0x18001e279  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e27e  lea     rdx, [rbp+57h+var_38]
0x18001e282  mov     rcx, rdi
0x18001e285  mov     rax, rbx
0x18001e288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e28d  mov     ecx, eax
0x18001e28f  test    eax, eax
0x18001e291  js      loc_18001E490
0x18001e297  mov     dword ptr [rbp+57h+var_48], r12d
0x18001e29b  mov     rcx, [rbp+57h+var_38]
0x18001e29f  mov     rax, [rcx]
0x18001e2a2  lea     rdx, [rbp+57h+var_48]
0x18001e2a6  mov     rax, [rax+18h]
0x18001e2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2af  mov     ecx, eax
0x18001e2b1  test    eax, eax
0x18001e2b3  mov     eax, cs:dword_180037050
0x18001e2b9  js      loc_18001E47B
0x18001e2bf  cmp     eax, 4
0x18001e2c2  jbe     short loc_18001E30E
0x18001e2c4  mov     eax, dword ptr [rbp+57h+var_48]
0x18001e2c7  mov     dword ptr [rbp+57h+var_80], eax
0x18001e2ca  mov     rcx, rsi; struct _GUID *
0x18001e2cd  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001e2d2  mov     [rbp+57h+var_50], rax
0x18001e2d6  mov     [rbp+57h+var_90], rsi
0x18001e2da  mov     [rbp+57h+var_88], r14
0x18001e2de  lea     rax, [rbp+57h+var_80]
0x18001e2e2  mov     [rsp+0D0h+var_98], rax
0x18001e2e7  lea     rax, [rbp+57h+var_50]
0x18001e2eb  mov     [rsp+0D0h+var_A0], rax
0x18001e2f0  lea     rax, [rbp+57h+var_90]
0x18001e2f4  mov     [rsp+0D0h+var_A8], rax
0x18001e2f9  lea     rax, [rbp+57h+var_88]
0x18001e2fd  mov     [rsp+0D0h+ppv], rax
0x18001e302  lea     rdx, byte_18002E8E1
0x18001e309  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001e30e  mov     r14d, r12d
0x18001e311  cmp     dword ptr [rbp+57h+var_48], r12d
0x18001e315  jbe     loc_18001E4C7
0x18001e31b  mov     [rbp+57h+var_50], r12
0x18001e31f  mov     rdi, [rbp+57h+var_38]
0x18001e323  mov     rax, [rdi]
0x18001e326  mov     rbx, [rax+20h]
0x18001e32a  lea     rcx, [rbp+57h+var_50]
0x18001e32e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e333  lea     r8, [rbp+57h+var_50]
0x18001e337  mov     edx, r14d
0x18001e33a  mov     rcx, rdi
0x18001e33d  mov     rax, rbx
0x18001e340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e345  mov     ecx, eax
0x18001e347  test    eax, eax
0x18001e349  js      loc_18001E41E
0x18001e34f  mov     rcx, [rbp+57h+var_58]
0x18001e353  add     rcx, 20h ; ' '
0x18001e357  mov     rax, [rcx]
0x18001e35a  mov     dword ptr [rsp+0D0h+var_A0], r12d
0x18001e35f  mov     byte ptr [rsp+0D0h+var_A8], r12b
0x18001e364  mov     [rsp+0D0h+ppv], r12
0x18001e369  mov     r9, [rbp+57h+var_50]
0x18001e36d  xor     r8d, r8d
0x18001e370  xor     edx, edx
0x18001e372  mov     rax, [rax+18h]
0x18001e376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e37b  test    eax, eax
0x18001e37d  jns     loc_18001E463
0x18001e383  mov     ecx, cs:dword_180037050
0x18001e389  cmp     ecx, 2
0x18001e38c  jbe     loc_18001E463
0x18001e392  mov     dword ptr [rbp+57h+var_80], eax
0x18001e395  lea     rax, aIuiradiomanage; "IUIRadioManagerInternal::InsertJob(RM_J"...
0x18001e39c  mov     [rbp+57h+var_88], rax
0x18001e3a0  lea     rax, [rbp+57h+var_80]
0x18001e3a4  mov     [rsp+0D0h+var_A8], rax
0x18001e3a9  lea     rax, [rbp+57h+var_88]
0x18001e3ad  mov     [rsp+0D0h+ppv], rax
0x18001e3b2  lea     rdx, byte_18002E89B
0x18001e3b9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001e3be  jmp     loc_18001E463
0x18001e3c3  mov     eax, cs:dword_180037050
0x18001e3c9  cmp     eax, 4
0x18001e3cc  jbe     short loc_18001E410
0x18001e3ce  mov     rcx, rsi; struct _GUID *
0x18001e3d1  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001e3d6  mov     [rbp+57h+var_90], rax
0x18001e3da  mov     [rbp+57h+var_80], rsi
0x18001e3de  lea     rax, aRadiomanagerCr_0; "RadioManager::CreateMediaManager Exited"...
0x18001e3e5  mov     [rbp+57h+var_48], rax
0x18001e3e9  lea     rax, [rbp+57h+var_90]
0x18001e3ed  mov     [rsp+0D0h+var_A0], rax
0x18001e3f2  lea     rax, [rbp+57h+var_80]
0x18001e3f6  mov     [rsp+0D0h+var_A8], rax
0x18001e3fb  lea     rax, [rbp+57h+var_48]
0x18001e3ff  mov     [rsp+0D0h+ppv], rax
0x18001e404  lea     rdx, byte_18002EA19
0x18001e40b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18001e410  lea     rcx, [rbp+57h+var_50]
0x18001e414  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001e419  jmp     loc_18001E664
0x18001e41e  mov     eax, cs:dword_180037050
0x18001e424  cmp     eax, 2
0x18001e427  jbe     short loc_18001E463
0x18001e429  mov     dword ptr [rbp+57h+var_80], ecx
0x18001e42c  mov     dword ptr [rbp+57h+var_90], r14d
0x18001e430  lea     rax, aIradioinstance_5; "IRadioInstanceCollection::GetAt failed"
0x18001e437  mov     [rbp+57h+var_88], rax
0x18001e43b  lea     rax, [rbp+57h+var_80]
0x18001e43f  mov     [rsp+0D0h+var_A0], rax
0x18001e444  lea     rax, [rbp+57h+var_90]
0x18001e448  mov     [rsp+0D0h+var_A8], rax
  ... truncated ...
```
