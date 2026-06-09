# CCbsStoreRepairExecutionObject::CheckCsiStore(void)

- ea: `0x180186630`
- end: `0x18018764a`
- name: `?CheckCsiStore@CCbsStoreRepairExecutionObject@@IEAAJXZ`
- size: `4122`
- prototype: `__int64 __fastcall(CCbsStoreRepairExecutionObject *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180189b14`

## callees

- `0x180010cc0`
- `0x180012fe4`
- `0x180015420`
- `0x18001de20`
- `0x18002e0d0`
- `0x18004854c`
- `0x18004a920`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800c3370`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800f19ec`
- `0x180177464`
- `0x180184a08`
- `0x180186630`
- `0x1801888dc`
- `0x18018d710`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180186771`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180186771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018753b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018753b`

## string_xrefs

- `0x1801868d3`: `Failed to convert ICSIStore to a service provider.`
- `0x18018671e`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018680c`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180186b05`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180186f96`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x1801873c8`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x1801875b4`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180186ccf`: `Repr: Non CBS installed component found, ignore it since it is not repairble`
- `0x180186c3f`: `Rept: Failed to enumerate corrupted components.`
- `0x180186b35`: `Repr: CSI meta data corruption found, will commit repair transaction if repair is asked.`
- `0x180186ec7`: `Repr: Non CBS installed component found when attempting to find owner for corrupt file: {}, ignore it since it is not repairble`
- `0x180187210`: `Repr: Non CBS installed component found when attempting to find owner for corrupt file: {}, ignore it since it is not repairble`
- `0x180186d49`: `Invalid component corruption type {}`
- `0x180186d9f`: `Failed to create a new corrupted component entry.`
- `0x1801870e8`: `Failed to create a new corrupted component entry.`
- `0x180187458`: `Failed to create a new corrupted component entry.`
- `0x18018755a`: `Repr: Failed to create cancel event.`
- `0x1801866df`: `Repair transaction is already active`
- `0x1801869e2`: `Repr: Failed to get repair transaction.`

## pseudocode

```c
__int64 __fastcall CCbsStoreRepairExecutionObject::CheckCsiStore(CCbsStoreRepairExecutionObject *this)
{
  _QWORD *v2; // r15
  signed int CorruptComponentEntry; // ebx
  void (*v4)(void); // rax
  char *EventW; // rbx
  CCbsSession *v6; // rdi
  struct ICSIStore **InitPointer; // rax
  signed int Store; // eax
  int v9; // edi
  __int64 v10; // rdx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64); // rdi
  __int64 v14; // rax
  signed int v15; // eax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, GUID *, GUID *, __int64); // rdi
  __int64 v18; // rax
  signed int v19; // eax
  signed int v20; // eax
  unsigned int v21; // edi
  signed int v22; // eax
  __int64 v23; // rdx
  int v24; // ecx
  bool v25; // zf
  __int64 v26; // rax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, _QWORD, __int64, int *); // rbx
  __int64 v29; // rax
  signed int v30; // eax
  struct CorruptPackage::CorruptComponent *v31; // rcx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, _QWORD, __int64, int *); // rbx
  __int64 v34; // rax
  int v35; // eax
  CorruptPackage::CorruptComponent::CorruptedFile *v36; // rbx
  struct CorruptPackage::CorruptComponent *v37; // r13
  __int64 v38; // rdx
  unsigned int v39; // edx
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, _QWORD, __int64, int *); // rbx
  __int64 v42; // rax
  int v43; // eax
  struct CorruptPackage::CorruptComponent *v44; // rcx
  __int64 v45; // rdx
  void (*v46)(void); // rax
  signed int LastError; // ebx
  unsigned int v48; // eax
  unsigned int v49; // [rsp+20h] [rbp-99h]
  char v50[8]; // [rsp+30h] [rbp-89h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-81h] BYREF
  CorruptPackage::CorruptComponent::CorruptedFile *v52; // [rsp+40h] [rbp-79h] BYREF
  __int64 v53; // [rsp+48h] [rbp-71h] BYREF
  char *v54; // [rsp+50h] [rbp-69h] BYREF
  struct IDefinitionIdentity *v55[2]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v56; // [rsp+68h] [rbp-51h] BYREF
  __int128 v57; // [rsp+78h] [rbp-41h]
  __int64 v58; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v59; // [rsp+90h] [rbp-29h] BYREF
  __int64 v60; // [rsp+98h] [rbp-21h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-19h] BYREF
  struct CorruptPackage::CorruptComponent *v62; // [rsp+A8h] [rbp-11h] BYREF
  int v63; // [rsp+B0h] [rbp-9h] BYREF
  int v64; // [rsp+B4h] [rbp-5h] BYREF
  __int64 v65; // [rsp+B8h] [rbp-1h] BYREF
  int v66; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v61 = 0;
  v51 = 0;
  v58 = 0;
  v66 = 0;
  v50[0] = 1;
  v60 = 0;
  v64 = 0;
  v53 = 0;
  v65 = 0;
  v52 = 0;
  v59 = 0;
  v63 = 0;
  *(_OWORD *)v55 = 0;
  v56 = 0;
  v57 = 0;
  if ( vpfnTiLockProcess )
    vpfnTiLockProcess(0);
  v2 = (_QWORD *)((char *)this + 344);
  if ( *((_QWORD *)this + 43) )
  {
    CorruptComponentEntry = -2146498560;
    v59 = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Repair transaction is already active");
      v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v52);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
      (const char *)0x800F0800LL,
      v49);
LABEL_7:
    AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v50);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v53);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v60);
    if ( v58 )
    {
      v4 = *(void (**)(void))(*(_QWORD *)v58 + 16LL);
LABEL_165:
      v4();
      v58 = 0;
      goto LABEL_166;
    }
    goto LABEL_166;
  }
  EventW = (char *)CreateEventW(0, 0, 0, 0);
  v54 = EventW;
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Repr: Failed to create cancel event.");
      if ( LastError > 0 )
        v48 = (unsigned __int16)LastError | 0x80070000;
      else
        v48 = LastError;
      LODWORD(v62) = v48;
      v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)&v52);
    }
    if ( LastError )
    {
      CorruptComponentEntry = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x422,
                                (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
                                (const char *)(unsigned int)LastError,
                                v49);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v54);
      AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v50);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v53);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v60);
      if ( v58 )
      {
        v4 = *(void (**)(void))(*(_QWORD *)v58 + 16LL);
        goto LABEL_165;
      }
LABEL_166:
      if ( v51 )
      {
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v51)[2])(v51);
        v51 = 0;
      }
      if ( v61 )
      {
        v46 = *(void (**)(void))(*(_QWORD *)v61 + 16LL);
LABEL_170:
        v46();
      }
      return (unsigned int)CorruptComponentEntry;
    }
    goto LABEL_150;
  }
  v6 = (CCbsSession *)*((_QWORD *)this + 6);
  InitPointer = (struct ICSIStore **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v51);
  Store = CCbsSession::GetStore(v6, InitPointer);
  v9 = Store;
  if ( Store < 0 )
  {
    v59 = Store;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get CSI session store.");
      v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v52);
    }
    v10 = 1060;
    goto LABEL_14;
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
  v13 = **v51;
  v14 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v58);
  v15 = v13(v12, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, v14);
  v9 = v15;
  if ( v15 < 0 )
  {
    v59 = v15;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert ICSIStore to a service provider.");
      v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v52);
    }
    v10 = 1064;
    goto LABEL_14;
  }
  v16 = v58;
  v17 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64))(*(_QWORD *)v58 + 24LL);
  v18 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v61);
  v19 = v17(v16, &GUID_a817521b_2b43_489f_8b84_67aceeab24a8, &GUID_a817521b_2b43_489f_8b84_67aceeab24a8, v18);
  v9 = v19;
  if ( v19 < 0 )
  {
    v59 = v19;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Repr: Failed to get store2.");
      v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v52);
    }
    v10 = 1067;
    goto LABEL_14;
  }
  if ( *v2 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180187649LL);
  }
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, char *))(*(_QWORD *)v61 + 328LL))(
          v61,
          0,
          &v66,
          (char *)this + 344);
  v9 = v20;
  if ( v20 >= 0 )
  {
    if ( *((_DWORD *)this + 92) )
    {
      v21 = 4;
      if ( !CbsRegQueryDWORDValue(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\Servicing",
              1u,
              L"IgnorePayloadCorruption",
              &v59)
        && v59 )
      {
        LogAdapter::TraceAtLevel<>(
          1,
          "Repr: GPO ignore payload corruption is set, detection will only check for payload missing.");
        v21 = 12;
      }
    }
    else
    {
      v21 = 20;
    }
    if ( *((_BYTE *)this + 365) )
      v21 = 32;
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, int *))(*(_QWORD *)*v2 + 24LL))(*v2, v21, EventW, &v63);
    CorruptComponentEntry = v22;
    if ( v22 < 0 )
    {
      v59 = v22;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Rept: Failed to call CSI detect.");
        v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v52);
      }
      v23 = 1103;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)(unsigned int)CorruptComponentEntry,
        v49);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v54);
      goto LABEL_7;
    }
    v24 = v63;
    v25 = (v63 & 0x10000) == 0;
    *((_DWORD *)this + 101) = v63 & 0x10000;
    if ( !v25 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Repr: CSI meta data corruption found, will commit repair transaction if repair is asked.");
      v24 = v63;
    }
    if ( (unsigned __int16)v24 == 3 )
    {
      *((_DWORD *)this + 88) = 1;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v54);
      AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v50);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v53);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v60);
      if ( v58 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v58 = 0;
      }
      if ( v51 )
      {
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v51)[2])(v51);
        v51 = 0;
      }
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      return 2148468769LL;
    }
    if ( (v24 & 0xFFFF0000) != 0x20000 )
    {
      v26 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v53);
      GetTaskAllocator(v26);
      v27 = *v2;
      v62 = 0;
      v28 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)v27 + 32LL);
      v29 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v60);
      v30 = v28(v27, 0, v29, &v64);
      CorruptComponentEntry = v30;
      if ( v30 >= 0 )
      {
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct IDefinitionIdentity **, __int64 *))(*(_QWORD *)v60 + 24LL))(
                   v60,
                   1,
                   v55,
                   &v65)
             && v65 )
        {
          CorruptComponentEntry = CCbsStoreRepairExecutionObject::GetCorruptComponentEntry(this, v55[1], &v62);
          if ( CorruptComponentEntry == -2146498292 )
          {
            LogAdapter::TraceAtLevel<>(
              1,
              "Repr: Non CBS installed component found, ignore it since it is not repairble");
          }
          else
          {
            if ( CorruptComponentEntry < 0 )
            {
              LODWORD(v62) = CorruptComponentEntry;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create a new corrupted component entry.");
                v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v52);
              }
              v23 = 1154;
              goto LABEL_46;
            }
            if ( LODWORD(v55[0]) == 1 )
            {
              v31 = v62;
              *((_BYTE *)v62 + 92) = 1;
            }
            else
            {
              if ( LODWORD(v55[0]) != 3 )
              {
                CorruptComponentEntry = -2146498560;
                v59 = -2146498560;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<unsigned long>(
                    (_DWORD)LogAdapter::g_Logger,
                    0,
                    3,
                    (unsigned int)"Invalid component corruption type {}",
                    (__int64)v55);
                  v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v52);
                }
                v23 = 1166;
                goto LABEL_46;
              }
              v31 = v62;
              ++*((_DWORD *)v62 + 22);
            }
            *((_BYTE *)v31 + 100) = (_DWORD)v57 != 0;
            *((_DWORD *)v31 + 24) = DWORD1(v57);
            *((_BYTE *)v31 + 101) = DWORD2(v57) != 0;
          }
          ClearCorruptComponentStructure(v53, v55);
        }
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v60);
        v32 = *v2;
        v33 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)*v2 + 40LL);
        v34 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v60);
        v35 = v33(v32, 0, v34, &v64);
        CorruptComponentEntry = v35;
        if ( v35 >= 0 )
        {
          while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct IDefinitionIdentity **, __int64 *))(*(_QWORD *)v60 + 24LL))(
                     v60,
                     1,
                     v55,
                     &v65)
               && v65 )
          {
            CorruptComponentEntry = CCbsStoreRepairExecutionObject::GetCorruptComponentEntry(this, v55[1], &v62);
            if ( CorruptComponentEntry == -2146498292 )
            {
              if ( LogAdapter::g_Logger )
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  1,
                  (__int64)"Repr: Non CBS installed component found when attempting to find owner for corrupt file: {}, i"
                           "gnore it since it is not repairble",
                  (__int64)&v56);
              ClearCorruptComponentStructure(v53, v55);
            }
            else
            {
              if ( CorruptComponentEntry < 0 )
              {
                v59 = CorruptComponentEntry;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create a new corrupted component entry.");
                  v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v52);
                }
                v23 = 1198;
                goto LABEL_46;
              }
              if ( LODWORD(v55[0]) != 2 )
              {
                CorruptComponentEntry = -2146498560;
                LODWORD(v62) = -2146498560;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Expecting payload corruption");
                  v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v52);
                }
                v23 = 1203;
                goto LABEL_46;
              }
              if ( !(_QWORD)v56 )
              {
                CorruptComponentEntry = -2146498560;
                LODWORD(v62) = -2146498560;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Expecting valid file name");
                  v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v52);
                }
                v23 = 1204;
                goto LABEL_46;
              }
              Windows::AutoNewPtr<CorruptPackage::CorruptComponent::CorruptedFile>::Allocate<>(&v52);
              v36 = v52;
              if ( !v52 )
              {
                CorruptComponentEntry = -2147024882;
                LODWORD(v62) = -2147024882;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate corruption file structure");
                  v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v52);
                }
                v23 = 1207;
                goto LABEL_46;
              }
              v9 = SczAllocFromSz(v52, v56);
              if ( v9 < 0 )
              {
                v38 = 1209;
LABEL_98:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v38,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
                  (const char *)(unsigned int)v9,
                  v49);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v54);
                AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v50);
                if ( v36 )
                  CorruptPackage::CorruptComponent::CorruptedFile::`scalar deleting destructor'(v36, v39);
                goto LABEL_15;
              }
              v37 = v62;
              *((_DWORD *)v36 + 6) = 2;
              v52 = v36;
              *((_BYTE *)v36 + 12) = (_DWORD)v57 != 0;
              *((_DWORD *)v36 + 2) = DWORD1(v57);
              v9 = CCbsArrayBase<CCbsTask *,CCbsPointerArray<CCbsTask *>>::Add(v37, &v52);
              if ( v9 < 0 )
              {
                v38 = 1215;
                goto LABEL_98;
              }
              v52 = 0;
              *((_BYTE *)v37 + 101) = DWORD2(v57) != 0;
              ClearCorruptComponentStructure(v53, v55);
            }
          }
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v60);
          v40 = *v2;
          v41 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)*v2 + 48LL);
          v42 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v60);
          v43 = v41(v40, 0, v42, &v64);
          CorruptComponentEntry = v43;
          if ( v43 >= 0 )
          {
            while ( 1 )
            {
              if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct IDefinitionIdentity **, __int64 *))(*(_QWORD *)v60 + 24LL))(
                     v60,
                     1,
                     v55,
                     &v65)
                || !v65 )
              {
                goto LABEL_149;
              }
              CorruptComponentEntry = CCbsStoreRepairExecutionObject::GetCorruptComponentEntry(this, v55[1], &v62);
              if ( CorruptComponentEntry == -2146498292 )
              {
                if ( LogAdapter::g_Logger )
                  LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    1,
                    (__int64)"Repr: Non CBS installed component found when attempting to find owner for corrupt file: {},"
                             " ignore it since it is not repairble",
                    (__int64)&v56);
              }
              else
              {
                if ( CorruptComponentEntry < 0 )
                {
                  v59 = CorruptComponentEntry;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create a new corrupted component entry.");
                    v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)&v52);
                  }
                  v23 = 1245;
                  goto LABEL_46;
                }
                if ( LODWORD(v55[0]) != 4 )
                {
                  CorruptComponentEntry = -2146498560;
                  LODWORD(v62) = -2146498560;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Expecting payload delta corruption");
                    v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)&v52);
                  }
                  v45 = 1250;
LABEL_140:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v45,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
                    (const char *)(unsigned int)CorruptComponentEntry,
                    v49);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v54);
                  AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v50);
                  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v53);
                  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v60);
                  if ( v58 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
                    v58 = 0;
                  }
                  if ( v51 )
                  {
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v51)[2])(v51);
                    v51 = 0;
                  }
                  if ( v61 )
                  {
                    v46 = *(void (**)(void))(*(_QWORD *)v61 + 16LL);
                    goto LABEL_170;
                  }
                  return (unsigned int)CorruptComponentEntry;
                }
                if ( !(_QWORD)v56 )
                {
                  CorruptComponentEntry = -2146498560;
                  LODWORD(v62) = -2146498560;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Expecting valid file name");
                    v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)&v52);
                  }
                  v23 = 1251;
                  goto LABEL_46;
                }
                Windows::AutoNewPtr<CorruptPackage::CorruptComponent::CorruptedFile>::Allocate<>(&v52);
                v36 = v52;
                if ( !v52 )
                {
                  CorruptComponentEntry = -2147024882;
                  LODWORD(v62) = -2147024882;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate corruption file structure");
                    v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)&v52);
                  }
                  v45 = 1254;
                  goto LABEL_140;
                }
                v9 = SczAllocFromSz(v52, v56);
                if ( v9 < 0 )
                {
                  v38 = 1256;
                  goto LABEL_98;
                }
                v44 = v62;
                *((_DWORD *)v36 + 6) = 4;
                v52 = v36;
                *((_BYTE *)v36 + 12) = (_DWORD)v57 != 0;
                *((_DWORD *)v36 + 2) = DWORD1(v57);
                v9 = CCbsArrayBase<CCbsTask *,CCbsPointerArray<CCbsTask *>>::Add(v44, &v52);
                if ( v9 < 0 )
                {
                  v38 = 1262;
                  goto LABEL_98;
                }
                v52 = 0;
              }
              ClearCorruptComponentStructure(v53, v55);
            }
          }
          LODWORD(v62) = v43;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Rept: Failed to enumerate corrupted files.");
            v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v52);
          }
          v23 = 1229;
        }
        else
        {
          LODWORD(v62) = v35;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Rept: Failed to enumerate corrupted files.");
            v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v62;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v52);
          }
          v23 = 1182;
        }
      }
      else
      {
        v59 = v30;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Rept: Failed to enumerate corrupted components.");
          v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v52);
        }
        v23 = 1141;
      }
      goto LABEL_46;
    }
LABEL_149:
    ClearCorruptComponentStructure(v53, v55);
LABEL_150:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v54);
    AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v50);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v53);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v60);
    if ( v58 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      v58 = 0;
    }
    if ( v51 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v51)[2])(v51);
      v51 = 0;
    }
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    return 0;
  }
  v59 = v20;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Repr: Failed to get repair transaction.");
    v52 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v59;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&v52);
  }
  v10 = 1070;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
    (const char *)(unsigned int)v9,
    v49);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v54);
  AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v50);
LABEL_15:
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v53);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v60);
  if ( v58 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
  }
  if ( v51 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v51)[2])(v51);
    v51 = 0;
  }
  if ( v61 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180186630  push    rbp
0x180186632  push    rbx
0x180186633  push    rsi
0x180186634  push    rdi
0x180186635  push    r12
0x180186637  push    r13
0x180186639  push    r14
0x18018663b  push    r15
0x18018663d  lea     rbp, [rsp-1Fh]
0x180186642  sub     rsp, 0D8h
0x180186649  mov     rax, cs:__security_cookie
0x180186650  xor     rax, rsp
0x180186653  mov     [rbp+57h+var_48], rax
0x180186657  mov     rax, cs:?vpfnTiLockProcess@@3P6AHH@ZEA; int (*vpfnTiLockProcess)(int)
0x18018665e  xor     r12d, r12d
0x180186661  mov     [rbp+57h+var_70], r12
0x180186665  xorps   xmm0, xmm0
0x180186668  mov     [rsp+110h+var_D8], r12
0x18018666d  mov     r14, rcx
0x180186670  mov     [rbp+57h+var_88], r12
0x180186674  mov     [rbp+57h+var_50], r12d
0x180186678  lea     r13d, [r12+1]
0x18018667d  mov     [rsp+110h+var_E0], r13b
0x180186682  mov     [rbp+57h+var_78], r12
0x180186686  mov     [rbp+57h+var_5C], r12d
0x18018668a  mov     [rbp+57h+var_C8], r12
0x18018668e  mov     [rbp+57h+var_58], r12
0x180186692  mov     [rbp+57h+var_D0], r12
0x180186696  mov     [rbp+57h+var_80], r12d
0x18018669a  mov     [rbp+57h+var_60], r12d
0x18018669e  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x1801866a2  movups  [rbp+57h+var_A8], xmm0
0x1801866a6  movups  [rbp+57h+var_98], xmm0
0x1801866aa  test    rax, rax
0x1801866ad  jz      short loc_1801866B6
0x1801866af  xor     ecx, ecx
0x1801866b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801866b6  lea     r15, [r14+158h]
0x1801866bd  cmp     [r15], r12
0x1801866c0  jz      loc_180186767
0x1801866c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801866cd  mov     ebx, 800F0800h
0x1801866d2  mov     [rbp+57h+var_80], ebx
0x1801866d5  test    rcx, rcx
0x1801866d8  jz      short loc_18018671A
0x1801866da  mov     esi, 3
0x1801866df  lea     r9, aRepairTransact; "Repair transaction is already active"
0x1801866e6  mov     r8d, esi
0x1801866e9  xor     edx, edx
0x1801866eb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801866f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801866f7  lea     rax, [rbp+57h+var_80]
0x1801866fb  mov     [rbp+57h+var_D0], rax
0x1801866ff  lea     r9, asc_1802EE7AC; ": {}"
0x180186706  lea     rax, [rbp+57h+var_D0]
0x18018670a  mov     r8d, esi
0x18018670d  mov     dl, r13b
0x180186710  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180186715  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018671a  mov     rcx, [rbp+5Fh]; this
0x18018671e  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x180186725  mov     r9d, ebx; char *
0x180186728  mov     edx, 41Fh; void *
0x18018672d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180186732  lea     rcx, [rsp+110h+var_E0]; this
0x180186737  call    ??1AutoCsiStoreLock@@QEAA@XZ; AutoCsiStoreLock::~AutoCsiStoreLock(void)
0x18018673c  lea     rcx, [rbp+57h+var_C8]
0x180186740  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180186745  lea     rcx, [rbp+57h+var_78]
0x180186749  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x18018674e  mov     rcx, [rbp+57h+var_88]
0x180186752  test    rcx, rcx
0x180186755  jz      loc_180187608
0x18018675b  mov     rax, [rcx]
0x18018675e  mov     rax, [rax+10h]
0x180186762  jmp     loc_1801875FF
0x180186767  xor     r9d, r9d; lpName
0x18018676a  xor     r8d, r8d; bInitialState
0x18018676d  xor     edx, edx; bManualReset
0x18018676f  xor     ecx, ecx; lpEventAttributes
0x180186771  call    cs:__imp_CreateEventW
0x180186778  nop     dword ptr [rax+rax+00h]
0x18018677d  mov     rbx, rax
0x180186780  mov     [rbp+57h+var_C0], rax
0x180186784  dec     rax
0x180186787  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18018678b  ja      loc_18018753B
0x180186791  mov     rdi, [r14+30h]
0x180186795  lea     rcx, [rsp+110h+var_D8]
0x18018679a  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018679f  mov     rdx, rax; struct ICSIStore **
0x1801867a2  mov     rcx, rdi; this
0x1801867a5  call    ?GetStore@CCbsSession@@QEAAJPEAPEAUICSIStore@@@Z; CCbsSession::GetStore(ICSIStore * *)
0x1801867aa  mov     edi, eax
0x1801867ac  test    eax, eax
0x1801867ae  jns     loc_180186890
0x1801867b4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801867bb  mov     [rbp+57h+var_80], eax
0x1801867be  test    rcx, rcx
0x1801867c1  jz      short loc_180186803
0x1801867c3  mov     esi, 3
0x1801867c8  lea     r9, aFailedToGetCsi_2; "Failed to get CSI session store."
0x1801867cf  mov     r8d, esi
0x1801867d2  xor     edx, edx
0x1801867d4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801867d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801867e0  lea     rax, [rbp+57h+var_80]
0x1801867e4  mov     [rbp+57h+var_D0], rax
0x1801867e8  lea     r9, asc_1802EE7AC; ": {}"
0x1801867ef  lea     rax, [rbp+57h+var_D0]
0x1801867f3  mov     r8d, esi
0x1801867f6  mov     dl, r13b
0x1801867f9  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1801867fe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180186803  mov     edx, 424h; void *
0x180186808  mov     rcx, [rbp+5Fh]; this
0x18018680c  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x180186813  mov     r9d, edi; char *
0x180186816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018681b  lea     rcx, [rbp+57h+var_C0]
0x18018681f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180186824  lea     rcx, [rsp+110h+var_E0]; this
0x180186829  call    ??1AutoCsiStoreLock@@QEAA@XZ; AutoCsiStoreLock::~AutoCsiStoreLock(void)
0x18018682e  lea     rcx, [rbp+57h+var_C8]
0x180186832  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180186837  lea     rcx, [rbp+57h+var_78]
0x18018683b  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180186840  mov     rcx, [rbp+57h+var_88]
0x180186844  test    rcx, rcx
0x180186847  jz      short loc_180186859
0x180186849  mov     rax, [rcx]
0x18018684c  mov     rax, [rax+10h]
0x180186850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186855  mov     [rbp+57h+var_88], r12
0x180186859  mov     rcx, [rsp+110h+var_D8]
0x18018685e  test    rcx, rcx
0x180186861  jz      short loc_180186874
0x180186863  mov     rax, [rcx]
0x180186866  mov     rax, [rax+10h]
0x18018686a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018686f  mov     [rsp+110h+var_D8], r12
0x180186874  mov     rcx, [rbp+57h+var_70]
0x180186878  test    rcx, rcx
0x18018687b  jz      short loc_180186889
0x18018687d  mov     rax, [rcx]
0x180186880  mov     rax, [rax+10h]
0x180186884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186889  mov     eax, edi
0x18018688b  jmp     loc_18018751A
0x180186890  mov     rsi, [rsp+110h+var_D8]
0x180186895  lea     rcx, [rbp+57h+var_88]
0x180186899  mov     rax, [rsi]
0x18018689c  mov     rdi, [rax]
0x18018689f  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801868a4  mov     r8, rax
0x1801868a7  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x1801868ae  mov     rax, rdi
0x1801868b1  mov     rcx, rsi
0x1801868b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801868b9  mov     edi, eax
0x1801868bb  test    eax, eax
0x1801868bd  jns     short loc_180186918
0x1801868bf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801868c6  mov     [rbp+57h+var_80], eax
0x1801868c9  test    rcx, rcx
0x1801868cc  jz      short loc_18018690E
0x1801868ce  mov     esi, 3
0x1801868d3  lea     r9, aFailedToConver_16; "Failed to convert ICSIStore to a servic"...
0x1801868da  mov     r8d, esi
0x1801868dd  xor     edx, edx
0x1801868df  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801868e4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801868eb  lea     rax, [rbp+57h+var_80]
0x1801868ef  mov     [rbp+57h+var_D0], rax
0x1801868f3  lea     r9, asc_1802EE7AC; ": {}"
0x1801868fa  lea     rax, [rbp+57h+var_D0]
0x1801868fe  mov     r8d, esi
0x180186901  mov     dl, r13b
0x180186904  mov     qword ptr [rsp+110h+var_F0], rax
0x180186909  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018690e  mov     edx, 428h
0x180186913  jmp     loc_180186808
0x180186918  mov     rsi, [rbp+57h+var_88]
0x18018691c  lea     rcx, [rbp+57h+var_70]
0x180186920  mov     rax, [rsi]
0x180186923  mov     rdi, [rax+18h]
0x180186927  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018692c  lea     rdx, _GUID_a817521b_2b43_489f_8b84_67aceeab24a8
0x180186933  mov     r9, rax
0x180186936  mov     r8, rdx
0x180186939  mov     rcx, rsi
0x18018693c  mov     rax, rdi
0x18018693f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186944  mov     edi, eax
0x180186946  test    eax, eax
0x180186948  jns     short loc_1801869A3
0x18018694a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180186951  mov     [rbp+57h+var_80], eax
0x180186954  test    rcx, rcx
0x180186957  jz      short loc_180186999
0x180186959  mov     esi, 3
0x18018695e  lea     r9, aReprFailedToGe; "Repr: Failed to get store2."
0x180186965  mov     r8d, esi
0x180186968  xor     edx, edx
0x18018696a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018696f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180186976  lea     rax, [rbp+57h+var_80]
0x18018697a  mov     [rbp+57h+var_D0], rax
0x18018697e  lea     r9, asc_1802EE7AC; ": {}"
0x180186985  lea     rax, [rbp+57h+var_D0]
0x180186989  mov     r8d, esi
0x18018698c  mov     dl, r13b
0x18018698f  mov     qword ptr [rsp+110h+var_F0], rax
0x180186994  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180186999  mov     edx, 42Bh
0x18018699e  jmp     loc_180186808
0x1801869a3  cmp     [r15], r12
0x1801869a6  jnz     loc_18018763F
0x1801869ac  mov     rcx, [rbp+57h+var_70]
0x1801869b0  lea     r8, [rbp+57h+var_50]
0x1801869b4  mov     r9, r15
0x1801869b7  xor     edx, edx
0x1801869b9  mov     rax, [rcx]
0x1801869bc  mov     rax, [rax+148h]
0x1801869c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801869c8  mov     edi, eax
0x1801869ca  test    eax, eax
0x1801869cc  jns     short loc_180186A27
0x1801869ce  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801869d5  mov     [rbp+57h+var_80], eax
0x1801869d8  test    rcx, rcx
0x1801869db  jz      short loc_180186A1D
0x1801869dd  mov     esi, 3
0x1801869e2  lea     r9, aReprFailedToGe_0; "Repr: Failed to get repair transaction."
0x1801869e9  mov     r8d, esi
0x1801869ec  xor     edx, edx
0x1801869ee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801869f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801869fa  lea     rax, [rbp+57h+var_80]
0x1801869fe  mov     [rbp+57h+var_D0], rax
0x180186a02  lea     r9, asc_1802EE7AC; ": {}"
0x180186a09  lea     rax, [rbp+57h+var_D0]
0x180186a0d  mov     r8d, esi
0x180186a10  mov     dl, r13b
0x180186a13  mov     qword ptr [rsp+110h+var_F0], rax
0x180186a18  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180186a1d  mov     edx, 42Eh
0x180186a22  jmp     loc_180186808
0x180186a27  cmp     [r14+170h], r12d
0x180186a2e  jz      short loc_180186A7B
0x180186a30  lea     rax, [rbp+57h+var_80]
0x180186a34  mov     r8d, r13d; unsigned int
0x180186a37  lea     r9, aIgnorepayloadc; "IgnorePayloadCorruption"
0x180186a3e  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int *
0x180186a43  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180186a4a  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180186a51  mov     edi, 4
0x180186a56  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x180186a5b  test    eax, eax
0x180186a5d  jnz     short loc_180186A80
0x180186a5f  cmp     [rbp+57h+var_80], r12d
0x180186a63  jz      short loc_180186A80
0x180186a65  lea     rdx, aReprGpoIgnoreP; "Repr: GPO ignore payload corruption is "...
0x180186a6c  mov     ecx, r13d
0x180186a6f  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180186a74  mov     edi, 0Ch
0x180186a79  jmp     short loc_180186A80
0x180186a7b  mov     edi, 14h
0x180186a80  mov     rcx, [r15]
0x180186a83  lea     r9, [rbp+57h+var_60]
0x180186a87  cmp     [r14+16Dh], r12b
0x180186a8e  mov     eax, 20h ; ' '
0x180186a93  mov     r8, rbx
0x180186a96  cmovnz  edi, eax
0x180186a99  mov     rax, [rcx]
0x180186a9c  mov     edx, edi
0x180186a9e  mov     rax, [rax+18h]
0x180186aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186aa7  mov     ebx, eax
0x180186aa9  test    eax, eax
0x180186aab  jns     short loc_180186B22
0x180186aad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180186ab4  mov     [rbp+57h+var_80], eax
0x180186ab7  test    rcx, rcx
0x180186aba  jz      short loc_180186AFC
0x180186abc  mov     esi, 3
0x180186ac1  lea     r9, aReptFailedToCa_0; "Rept: Failed to call CSI detect."
0x180186ac8  mov     r8d, esi
0x180186acb  xor     edx, edx
0x180186acd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180186ad2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180186ad9  lea     rax, [rbp+57h+var_80]
0x180186add  mov     [rbp+57h+var_D0], rax
0x180186ae1  lea     r9, asc_1802EE7AC; ": {}"
0x180186ae8  lea     rax, [rbp+57h+var_D0]
0x180186aec  mov     r8d, esi
0x180186aef  mov     dl, r13b
0x180186af2  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180186af7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180186afc  mov     edx, 44Fh; void *
  ... truncated ...
```
