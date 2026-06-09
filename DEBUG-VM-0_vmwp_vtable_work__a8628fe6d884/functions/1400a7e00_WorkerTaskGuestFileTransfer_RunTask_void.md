# WorkerTaskGuestFileTransfer::RunTask(void)

- ea: `0x1400a7e00`
- end: `0x1400a8a76`
- name: `?RunTask@WorkerTaskGuestFileTransfer@@UEAAXXZ`
- size: `3190`
- prototype: `void __fastcall(WorkerTaskGuestFileTransfer *__hidden this)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x14001e628`
- `0x14002ecd0`
- `0x140032f40`
- `0x1400535c4`
- `0x14005dbd0`
- `0x14006af38`
- `0x14009d7ac`
- `0x1400a7e00`
- `0x1400a8a7c`
- `0x1400a8ba8`
- `0x1400a8bf4`
- `0x1400a8e34`
- `0x1400a9ab8`
- `0x1400b0d40`
- `0x1400cf8a0`
- `0x1400dbe4c`
- `0x1400df13c`
- `0x1400eb528`
- `0x140122758`
- `0x140132940`
- `0x140132970`
- `0x1401335fc`
- `0x1401339fc`
- `0x14015b82c`
- `0x14018d2f0`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a803d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a84f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a803d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a84f7`
- `vmprox!GetVmErrInfo` at `0x1400a8a06`
- `vmprox!GetVmErrInfo` at `0x1400a8a06`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400a802d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400a802d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400a84e7`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400a84e7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1400a80f6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1400a80f6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400a80e4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1400a80e4`

## string_xrefs

- `0x1400a7eab`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a7eed`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a7f4b`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8060`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8114`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8264`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8420`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8729`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a87df`: `onecore\vm\worker\wpcore\workertaskguestfiletransfer.cpp`
- `0x1400a8522`: `onecore\vm\common/vml/VmFiles.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall WorkerTaskGuestFileTransfer::RunTask(WorkerTaskGuestFileTransfer *this)
{
  int v1; // r12d
  int VirtualDevice; // eax
  int v3; // eax
  struct _SECURITY_ATTRIBUTES *v4; // r9
  int v5; // eax
  unsigned int i; // r14d
  void **v7; // rsi
  _BYTE *v8; // rdx
  _BYTE *v9; // r15
  unsigned __int64 v10; // rcx
  char *v11; // rax
  size_t v12; // rbx
  __int64 v13; // r14
  __int64 v14; // r13
  __int64 v15; // rbx
  __int64 v16; // rsi
  signed int LastError; // eax
  union _LARGE_INTEGER v18; // rax
  GuestFileCopy *v19; // r15
  GuestFileCopy *v20; // rax
  __int64 *v21; // rsi
  void *v22; // rbx
  const WCHAR *v23; // r14
  const WCHAR *v24; // rcx
  const WCHAR *FileNameW; // r12
  _QWORD *v26; // rsi
  _QWORD *v27; // r8
  int v28; // eax
  unsigned int v29; // r12d
  unsigned int v30; // ebx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // r9
  __int64 v34; // r8
  int v35; // eax
  int v36; // eax
  unsigned int v37; // ebx
  __int64 v38; // rcx
  __int64 v39; // rcx
  void *v40; // rdx
  DWORD v41; // eax
  __int64 v42; // rcx
  unsigned __int64 v43; // rax
  void *v44; // rdx
  const char *v45; // r9
  WorkerAsyncTaskBase *v46; // r14
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 VmErrInfo; // rax
  void (*v51)(void *); // [rsp+20h] [rbp-1A8h]
  int v52; // [rsp+20h] [rbp-1A8h]
  unsigned int v53; // [rsp+20h] [rbp-1A8h]
  DWORD LowPart; // [rsp+20h] [rbp-1A8h]
  int v55; // [rsp+20h] [rbp-1A8h]
  int v56; // [rsp+20h] [rbp-1A8h]
  int v57; // [rsp+20h] [rbp-1A8h]
  const unsigned __int16 *v58; // [rsp+28h] [rbp-1A0h]
  _DWORD v59[3]; // [rsp+54h] [rbp-174h] BYREF
  __int64 v60; // [rsp+60h] [rbp-168h] BYREF
  __int64 v61; // [rsp+68h] [rbp-160h] BYREF
  int v62[2]; // [rsp+70h] [rbp-158h] BYREF
  __int64 v63; // [rsp+78h] [rbp-150h] BYREF
  __int64 v64; // [rsp+80h] [rbp-148h] BYREF
  __int64 *v65; // [rsp+88h] [rbp-140h]
  int v66; // [rsp+90h] [rbp-138h]
  __int64 VmName; // [rsp+98h] [rbp-130h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-128h] BYREF
  void *v69; // [rsp+A8h] [rbp-120h] BYREF
  void *v70; // [rsp+B0h] [rbp-118h] BYREF
  unsigned __int64 v71; // [rsp+B8h] [rbp-110h]
  GuestFileCopy *v72; // [rsp+C0h] [rbp-108h]
  __int64 v73; // [rsp+C8h] [rbp-100h] BYREF
  _QWORD *v74; // [rsp+D0h] [rbp-F8h]
  struct _OVERLAPPED Overlapped; // [rsp+D8h] [rbp-F0h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+F8h] [rbp-D0h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+100h] [rbp-C8h] BYREF
  DWORD v78; // [rsp+108h] [rbp-C0h] BYREF
  __int64 v79; // [rsp+110h] [rbp-B8h] BYREF
  struct IUnknown *v80; // [rsp+118h] [rbp-B0h] BYREF
  void *v81[6]; // [rsp+120h] [rbp-A8h] BYREF
  unsigned __int16 v82[16]; // [rsp+150h] [rbp-78h] BYREF
  unsigned __int16 v83[16]; // [rsp+170h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  try
  {
    *(_QWORD *)&v59[1] = this;
    v68 = (__int64)this;
    VmName = (__int64)this;
    v1 = 0;
    v79 = 0;
    v80 = 0;
    v73 = -1;
    v65 = (__int64 *)((char *)this + 16);
    v74 = (_QWORD *)((char *)this + 16);
    VirtualDevice = VirtualMotherboard::FindVirtualDevice(
                      *(VirtualMotherboard **)(*((_QWORD *)this + 2) + 984LL),
                      &g_ICVDevClassIdGuestInterface,
                      &IID_IUnknown,
                      &v80);
    if ( VirtualDevice < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)(unsigned int)VirtualDevice,
        (int)v51);
    v3 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v80->lpVtbl->QueryInterface)(
           v80,
           &IID_IICGuestInterface,
           &v79);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)(unsigned int)v3,
        (int)v51);
    v70 = 0;
    Vml::VmEvent::VmEvent((Vml::VmEvent *)&v70, 0, 0, v4, (const unsigned __int16 *)v51, v58);
    v78 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v79 + 32LL))(v79, &v78);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)(unsigned int)v5,
        v52);
    `eh vector constructor iterator'(
      v81,
      0x18u,
      2u,
      std::vector<std::atomic<bool>>::vector<std::atomic<bool>>,
      std::pair<std::vector<enum gsl::byte>,unsigned __int64>::~pair<std::vector<enum gsl::byte>,unsigned __int64>);
    for ( i = 0; i < 2; ++i )
    {
      v7 = &v81[3 * i];
      v8 = *v7;
      v9 = v7[1];
      v10 = v9 - (_BYTE *)*v7;
      if ( v78 >= v10 )
      {
        if ( v78 <= v10 )
          continue;
        if ( v78 > (unsigned __int64)((_BYTE *)v7[2] - v8) )
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v81[3 * i], v78);
          continue;
        }
        v12 = v78 - v10;
        memset_0(v7[1], 0, v12);
        v11 = &v9[v12];
      }
      else
      {
        v11 = &v8[v78];
      }
      v7[1] = v11;
    }
    v13 = 0;
    v61 = 0;
    v14 = *(_QWORD *)&v59[1] + 400LL;
    v15 = *(_QWORD *)(*(_QWORD *)&v59[1] + 400LL);
    v16 = *(_QWORD *)(*(_QWORD *)&v59[1] + 408LL);
    while ( v15 != v16 )
    {
      FileSize.QuadPart = 0;
      if ( !GetFileSizeEx(*(HANDLE *)v15, &FileSize) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
          (const char *)(unsigned int)LastError,
          v53);
      }
      v18 = FileSize;
      *(union _LARGE_INTEGER *)(v15 + 80) = FileSize;
      v13 += v18.QuadPart;
      v61 = v13;
      v15 += 88;
    }
    v60 = 0;
    v66 = 0;
    v19 = *(GuestFileCopy **)v14;
    v20 = *(GuestFileCopy **)(v14 + 8);
    v72 = v20;
    v21 = v65;
LABEL_26:
    if ( v19 == v20 )
    {
      `eh vector destructor iterator'(
        v81,
        0x18u,
        2u,
        std::pair<std::vector<enum gsl::byte>,unsigned __int64>::~pair<std::vector<enum gsl::byte>,unsigned __int64>);
      Vml::VmWaitable::~VmWaitable((Vml::VmWaitable *)&v70);
      Vml::VmFile::Reset((Vml::VmFile *)&v73, v44);
      Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(&v80);
      v46 = *(WorkerAsyncTaskBase **)&v59[1];
      goto LABEL_89;
    }
    v22 = *(void **)v19;
    *(_QWORD *)v19 = -1;
    v69 = v22;
    v23 = (const WCHAR *)((char *)v19 + 8);
    if ( *((_QWORD *)v19 + 4) <= 7u )
      v24 = (const WCHAR *)((char *)v19 + 8);
    else
      v24 = *(const WCHAR **)v23;
    FileNameW = PathFindFileNameW(v24);
    if ( !PathIsFileSpecW(FileNameW) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)0xA1,
        v53);
    v26 = (_QWORD *)((char *)v19 + 40);
    if ( *((_QWORD *)v19 + 8) <= 7u )
      v27 = (_QWORD *)((char *)v19 + 40);
    else
      v27 = (_QWORD *)*v26;
    LowPart = *((unsigned __int8 *)v19 + 73);
    v28 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, _QWORD *, _QWORD))(*(_QWORD *)v79 + 24LL))(
            v79,
            FileNameW,
            v27,
            *((unsigned __int8 *)v19 + 72));
    v29 = v28;
    if ( v28 < 0 )
    {
      v30 = v28 & 0xEFFFFFFF;
      _snwprintf_s<16>(v83, 16, L"%%%%%u", v28 & 0xEFFFFFFF);
      _snwprintf_s<16>(v82, 16, L"0x%08X", v30);
      if ( *((_QWORD *)v19 + 8) > 7u )
        v26 = (_QWORD *)*v26;
      v61 = (__int64)v26;
      if ( *((_QWORD *)v19 + 4) > 7u )
        v23 = *(const WCHAR **)v23;
      v60 = (__int64)v23;
      v31 = *v65;
      *(_QWORD *)&v59[1] = *v65 + 1152;
      FileSize.QuadPart = (LONGLONG)VirtualMachine::GetVmName((VirtualMachine *)(v31 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16],unsigned short const *,unsigned short const *>(
        (struct _EVENT_DESCRIPTOR *)&MSVML_FAILED_TO_START_GUEST_COPY,
        (__int64)&FileSize,
        (__int64)&v59[1],
        v83,
        v82,
        (__int64)&v60,
        (__int64)&v61);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
        (const char *)v29,
        v55);
    }
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = v70;
    NumberOfBytesTransferred = v78;
    v32 = Vml::VmFile::Read((Vml::VmFile *)&v69, v81[0], &NumberOfBytesTransferred, &Overlapped);
    FileSize.QuadPart = 0;
    v33 = 0;
    v63 = 0;
    v34 = 0;
    v59[0] = 0;
    v35 = v32 == 0;
    while ( 1 )
    {
      if ( v35 )
      {
        if ( !GetOverlappedResult(v22, &Overlapped, &NumberOfBytesTransferred, 1) )
        {
          v41 = GetLastError();
          if ( v41 != 996 )
          {
            if ( v41 != 38 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x4D6,
                (unsigned int)"onecore\\vm\\common/vml/VmFiles.h",
                (const char *)v41,
                LowPart);
            NumberOfBytesTransferred = 0;
          }
        }
        if ( !NumberOfBytesTransferred )
        {
          v35 = 0;
          goto LABEL_75;
        }
        LOBYTE(v34) = v59[0];
        v33 = v63;
      }
      else if ( !NumberOfBytesTransferred )
      {
        v36 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int64))(*(_QWORD *)v79 + 48LL))(
                v79,
                &GUID_NULL,
                v34,
                v33);
        v1 = v36;
        if ( v36 < 0 )
        {
          v37 = v36 & 0xEFFFFFFF;
          _snwprintf_s<16>(v82, 16, L"%%%%%u", v36 & 0xEFFFFFFF);
          _snwprintf_s<16>(v83, 16, L"0x%08X", v37);
          if ( *((_QWORD *)v19 + 8) > 7u )
            v26 = (_QWORD *)*v26;
          v61 = (__int64)v26;
          if ( *((_QWORD *)v19 + 4) > 7u )
            v23 = *(const WCHAR **)v23;
          v60 = (__int64)v23;
          v38 = *v65;
          *(_QWORD *)&v59[1] = *v65 + 1152;
          FileSize.QuadPart = (LONGLONG)VirtualMachine::GetVmName((VirtualMachine *)(v38 + 16));
          VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16],unsigned short const *,unsigned short const *>(
            (struct _EVENT_DESCRIPTOR *)&MSVML_FAILED_TO_COMPLETE_GUEST_COPY,
            (__int64)&FileSize,
            (__int64)&v59[1],
            v82,
            v83,
            (__int64)&v60,
            (__int64)&v61);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x183,
            (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
            (const char *)(unsigned int)v1,
            v56);
        }
        if ( *((_QWORD *)v19 + 8) > 7u )
          v26 = (_QWORD *)*v26;
        FileSize.QuadPart = (LONGLONG)v26;
        if ( *((_QWORD *)v19 + 4) > 7u )
          v23 = *(const WCHAR **)v23;
        v63 = (__int64)v23;
        v21 = v65;
        v39 = *v65;
        v64 = *v65 + 1152;
        *(_QWORD *)v62 = VirtualMachine::GetVmName((VirtualMachine *)(v39 + 16));
        VmEventWrite<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
          &MSVML_WP_SUCCEEDED_COPY_FILES_TO_GUEST,
          (__int64)&v64,
          (__int64)&v63,
          (__int64)&FileSize);
        Vml::VmFile::Reset((Vml::VmFile *)&v69, v40);
        v19 = (GuestFileCopy *)((char *)v19 + 88);
        v20 = v72;
        goto LABEL_26;
      }
      v62[0] = NumberOfBytesTransferred;
      v71 = ((_BYTE)v34 - 1) & 1;
      v63 = NumberOfBytesTransferred + v33;
      Overlapped.Pointer = (PVOID)v63;
      NumberOfBytesTransferred = v78;
      LODWORD(v64) = Vml::VmFile::Read((Vml::VmFile *)&v69, v81[3 * v71], &NumberOfBytesTransferred, &Overlapped) == 0;
      LowPart = FileSize.LowPart;
      v59[0] = (*(__int64 (__fastcall **)(__int64, GUID *, void *, _QWORD))(*(_QWORD *)v79 + 40LL))(
                 v79,
                 &GUID_NULL,
                 v81[3 * v59[0]],
                 (unsigned int)v62[0]);
      if ( v59[0] < 0 )
      {
        (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v79 + 56LL))(v79, &GUID_NULL);
        _snwprintf_s<16>(v82, 16, L"%%%%%u", v59[0] & 0xEFFFFFFF);
        _snwprintf_s<16>(v83, 16, L"0x%08X", v59[0] & 0xEFFFFFFF);
        if ( *((_QWORD *)v19 + 8) > 7u )
          v26 = (_QWORD *)*v26;
        v61 = (__int64)v26;
        if ( *((_QWORD *)v19 + 4) > 7u )
          v23 = *(const WCHAR **)v23;
        v60 = (__int64)v23;
        v42 = *v65;
        *(_QWORD *)&v59[1] = *v65 + 1152;
        FileSize.QuadPart = (LONGLONG)VirtualMachine::GetVmName((VirtualMachine *)(v42 + 16));
        VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16],unsigned short const *,unsigned short const *>(
          (struct _EVENT_DESCRIPTOR *)&MSVML_FAILED_TO_PERFORM_GUEST_COPY,
          (__int64)&FileSize,
          (__int64)&v59[1],
          v82,
          v83,
          (__int64)&v60,
          (__int64)&v61);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
          (const char *)v59[0],
          v57);
      }
      v34 = (unsigned int)v71;
      v59[0] = v71;
      FileSize.QuadPart += (unsigned int)v62[0];
      v60 += (unsigned int)v62[0];
      v43 = 100 * v60 / (unsigned __int64)v61;
      v71 = v43;
      if ( (_DWORD)v43 == v66 )
      {
        v35 = v64;
        goto LABEL_76;
      }
      v62[0] = 0;
      WorkerAsyncTaskBase::UpdateStatusProgress(*(WorkerAsyncTaskBase **)&v59[1], v43, v62);
      if ( v62[0] || *(_DWORD *)(*(_QWORD *)&v59[1] + 424LL) )
      {
        (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v79 + 56LL))(v79, &GUID_NULL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x168,
          (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
          (const char *)0x80042001LL,
          LowPart);
      }
      v66 = v71;
      v35 = v64;
LABEL_75:
      v34 = v59[0];
LABEL_76:
      v33 = v63;
    }
  }
  catch ( ... )
  {
    LODWORD(v64) = wil::details::in1diag3::Log_CaughtException(
                     retaddr,
                     (void *)0x193,
                     (unsigned int)"onecore\\vm\\worker\\wpcore\\workertaskguestfiletransfer.cpp",
                     v45);
    v14 = VmName + 400;
    v1 = v64;
    v46 = (WorkerAsyncTaskBase *)v68;
    v21 = v65;
  }
LABEL_89:
  if ( *(_QWORD *)v14 != *(_QWORD *)(v14 + 8) )
  {
    std::_Destroy_range<std::allocator<GuestFileCopy>>(*(GuestFileCopy **)v14);
    *(_QWORD *)(v14 + 8) = *(_QWORD *)v14;
  }
  if ( v1 >= 0 )
  {
    v49 = 40;
  }
  else
  {
    if ( v1 == -2147213311 )
    {
      v47 = *v21;
      v68 = *v21 + 1152;
      VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v47 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
        (struct _EVENT_DESCRIPTOR *)&MSVML_WP_CANCELLED_COPY_FILES_TO_GUEST,
        5u,
        (__int64)&VmName,
        (__int64)&v68);
    }
    else
    {
      _snwprintf_s<16>(v82, 16, L"%%%%%u", v1 & 0xEFFFFFFF);
      _snwprintf_s<16>(v83, 16, L"0x%08X", v1 & 0xEFFFFFFF);
      v48 = *v21;
      v68 = *v21 + 1152;
      VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v48 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
        (struct _EVENT_DESCRIPTOR *)&MSVML_WP_FAILED_COPY_FILES_TO_GUEST,
        5u,
        (__int64)&VmName,
        (__int64)&v68,
        (__int64)v82,
        (__int64)v83);
    }
    v49 = 41;
  }
  VirtualMachine::SetState(*v74, 2, v49);
  *(_QWORD *)&v59[1] = 0;
  VmErrInfo = GetVmErrInfo();
  Vml::VmComPtr<IVmSimpleTask>::Attach<IVmSimpleTask>(&v59[1], VmErrInfo);
  WorkerAsyncTaskBase::SetStatusComplete(v46, v1, *(struct IUnknown **)&v59[1]);
  Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(&v59[1]);
  Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(&v79);
}

```

## disassembly

```asm
0x1400a7e00  mov     r11, rsp
0x1400a7e03  mov     [r11+10h], rbx
0x1400a7e07  mov     [r11+18h], rsi
0x1400a7e0b  push    rdi
0x1400a7e0c  push    r12
0x1400a7e0e  push    r13
0x1400a7e10  push    r14
0x1400a7e12  push    r15
0x1400a7e14  sub     rsp, 1A0h
0x1400a7e1b  mov     rax, cs:__security_cookie
0x1400a7e22  xor     rax, rsp
0x1400a7e25  mov     [rsp+1C8h+var_38], rax
0x1400a7e2d  mov     qword ptr [rsp+1C8h+var_174+4], rcx
0x1400a7e32  mov     [rsp+1C8h+var_128], rcx
0x1400a7e3a  mov     [rsp+1C8h+var_130], rcx
0x1400a7e42  xor     edi, edi
0x1400a7e44  mov     r12d, edi
0x1400a7e47  mov     [r11-0B8h], rdi
0x1400a7e4e  mov     [rsp+1C8h+var_178], edi
0x1400a7e52  mov     [r11-0B0h], rdi
0x1400a7e59  mov     qword ptr [r11-100h], 0FFFFFFFFFFFFFFFFh
0x1400a7e64  lea     rsi, [rcx+10h]
0x1400a7e68  mov     [rsp+1C8h+var_140], rsi
0x1400a7e70  mov     [rsp+1C8h+var_F8], rsi
0x1400a7e78  mov     rcx, [rsi]
0x1400a7e7b  lea     r9, [r11-0B0h]; struct IUnknown **
0x1400a7e82  lea     r8, IID_IUnknown; struct _GUID *
0x1400a7e89  lea     rdx, g_ICVDevClassIdGuestInterface; struct _GUID *
0x1400a7e90  mov     rcx, [rcx+3D8h]; this
0x1400a7e97  call    ?FindVirtualDevice@VirtualMotherboard@@QEAAJAEBU_GUID@@0PEAPEAUIUnknown@@@Z; VirtualMotherboard::FindVirtualDevice(_GUID const &,_GUID const &,IUnknown * *)
0x1400a7e9c  mov     rcx, [rsp+1C8h]; this
0x1400a7ea4  test    eax, eax
0x1400a7ea6  jns     short loc_1400A7EBC
0x1400a7ea8  mov     r9d, eax; char *
0x1400a7eab  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a7eb2  mov     edx, 86h; void *
0x1400a7eb7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a7ebc  mov     rcx, [rsp+1C8h+var_B0]
0x1400a7ec4  mov     rax, [rcx]
0x1400a7ec7  lea     r8, [rsp+1C8h+var_B8]
0x1400a7ecf  lea     rdx, IID_IICGuestInterface
0x1400a7ed6  mov     rax, [rax]
0x1400a7ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a7ede  mov     rcx, [rsp+1C8h]; this
0x1400a7ee6  test    eax, eax
0x1400a7ee8  jns     short loc_1400A7EFE
0x1400a7eea  mov     r9d, eax; char *
0x1400a7eed  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a7ef4  mov     edx, 8Ah; void *
0x1400a7ef9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a7efe  mov     [rsp+1C8h+var_118], rdi
0x1400a7f06  xor     r8d, r8d; int
0x1400a7f09  xor     edx, edx; int
0x1400a7f0b  lea     rcx, [rsp+1C8h+var_118]; this
0x1400a7f13  call    ??0VmEvent@Vml@@QEAA@HHPEAU_SECURITY_ATTRIBUTES@@PEBG1@Z; Vml::VmEvent::VmEvent(int,int,_SECURITY_ATTRIBUTES *,ushort const *,ushort const *)
0x1400a7f18  nop
0x1400a7f19  mov     [rsp+1C8h+var_C0], edi
0x1400a7f20  mov     rcx, [rsp+1C8h+var_B8]
0x1400a7f28  mov     rax, [rcx]
0x1400a7f2b  lea     rdx, [rsp+1C8h+var_C0]
0x1400a7f33  mov     rax, [rax+20h]
0x1400a7f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a7f3c  mov     rcx, [rsp+1C8h]; this
0x1400a7f44  test    eax, eax
0x1400a7f46  jns     short loc_1400A7F5C
0x1400a7f48  mov     r9d, eax; char *
0x1400a7f4b  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a7f52  mov     edx, 98h; void *
0x1400a7f57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a7f5c  lea     rax, ??1?$pair@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@_K@std@@QEAA@XZ; std::pair<std::vector<gsl::byte>,unsigned __int64>::~pair<std::vector<gsl::byte>,unsigned __int64>(void)
0x1400a7f63  mov     [rsp+1C8h+var_1A8], rax; unsigned int
0x1400a7f68  lea     r9, ??0?$vector@U?$atomic@_N@std@@V?$allocator@U?$atomic@_N@std@@@2@@std@@QEAA@XZ; void (*)(void *)
0x1400a7f6f  mov     edx, 18h; unsigned __int64
0x1400a7f74  lea     r8d, [rdx-16h]; unsigned __int64
0x1400a7f78  lea     rcx, [rsp+1C8h+var_A8]; void *
0x1400a7f80  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400a7f85  nop
0x1400a7f86  mov     r14d, edi
0x1400a7f89  cmp     r14d, 2
0x1400a7f8d  jnb     short loc_1400A7FF9
0x1400a7f8f  mov     eax, r14d
0x1400a7f92  lea     rcx, [rax+rax*2]
0x1400a7f96  lea     rsi, [rsp+1C8h+var_A8]
0x1400a7f9e  lea     rsi, [rsi+rcx*8]
0x1400a7fa2  mov     ebx, [rsp+1C8h+var_C0]
0x1400a7fa9  mov     rdx, [rsi]
0x1400a7fac  mov     r15, [rsi+8]
0x1400a7fb0  mov     rcx, r15
0x1400a7fb3  sub     rcx, rdx
0x1400a7fb6  cmp     rbx, rcx
0x1400a7fb9  jnb     short loc_1400A7FC1
0x1400a7fbb  lea     rax, [rdx+rbx]
0x1400a7fbf  jmp     short loc_1400A7FF0
0x1400a7fc1  jbe     short loc_1400A7FF4
0x1400a7fc3  mov     rax, [rsi+10h]
0x1400a7fc7  sub     rax, rdx
0x1400a7fca  cmp     rbx, rax
0x1400a7fcd  jbe     short loc_1400A7FDC
0x1400a7fcf  mov     rdx, rbx
0x1400a7fd2  mov     rcx, rsi
0x1400a7fd5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1400a7fda  jmp     short loc_1400A7FF4
0x1400a7fdc  sub     rbx, rcx
0x1400a7fdf  mov     r8, rbx; Size
0x1400a7fe2  xor     edx, edx; Val
0x1400a7fe4  mov     rcx, r15; void *
0x1400a7fe7  call    memset_0
0x1400a7fec  lea     rax, [rbx+r15]
0x1400a7ff0  mov     [rsi+8], rax
0x1400a7ff4  inc     r14d
0x1400a7ff7  jmp     short loc_1400A7F89
0x1400a7ff9  mov     r14, rdi
0x1400a7ffc  mov     [rsp+1C8h+var_160], rdi
0x1400a8001  mov     r13, qword ptr [rsp+1C8h+var_174+4]
0x1400a8006  add     r13, 190h
0x1400a800d  mov     rbx, [r13+0]
0x1400a8011  mov     rsi, [r13+8]
0x1400a8015  cmp     rbx, rsi
0x1400a8018  jz      short loc_1400A808B
0x1400a801a  mov     qword ptr [rsp+1C8h+FileSize], rdi
0x1400a8022  lea     rdx, [rsp+1C8h+FileSize]; lpFileSize
0x1400a802a  mov     rcx, [rbx]; hFile
0x1400a802d  call    cs:__imp_GetFileSizeEx
0x1400a8034  nop     dword ptr [rax+rax+00h]
0x1400a8039  test    eax, eax
0x1400a803b  jnz     short loc_1400A8071
0x1400a803d  call    cs:__imp_GetLastError
0x1400a8044  nop     dword ptr [rax+rax+00h]
0x1400a8049  test    eax, eax
0x1400a804b  jle     short loc_1400A8055
0x1400a804d  movzx   eax, ax
0x1400a8050  or      eax, 80070000h
0x1400a8055  mov     rcx, [rsp+1C8h]; this
0x1400a805d  mov     r9d, eax; char *
0x1400a8060  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a8067  mov     edx, 0ABh; void *
0x1400a806c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a8071  mov     rax, qword ptr [rsp+1C8h+FileSize]
0x1400a8079  mov     [rbx+50h], rax
0x1400a807d  add     r14, rax
0x1400a8080  mov     [rsp+1C8h+var_160], r14
0x1400a8085  add     rbx, 58h ; 'X'
0x1400a8089  jmp     short loc_1400A8015
0x1400a808b  mov     [rsp+1C8h+var_168], rdi
0x1400a8090  mov     [rsp+1C8h+var_138], edi
0x1400a8097  mov     r15, [r13+0]
0x1400a809b  mov     rax, [r13+8]
0x1400a809f  mov     [rsp+1C8h+var_108], rax
0x1400a80a7  mov     rsi, [rsp+1C8h+var_140]
0x1400a80af  lea     rbx, GUID_NULL
0x1400a80b6  cmp     r15, rax
0x1400a80b9  jz      loc_1400A880E
0x1400a80bf  mov     rbx, [r15]
0x1400a80c2  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1400a80c9  mov     [rsp+1C8h+var_120], rbx
0x1400a80d1  lea     r14, [r15+8]
0x1400a80d5  cmp     qword ptr [r15+20h], 7
0x1400a80da  jbe     short loc_1400A80E1
0x1400a80dc  mov     rcx, [r14]
0x1400a80df  jmp     short loc_1400A80E4
0x1400a80e1  mov     rcx, r14; pszPath
0x1400a80e4  call    cs:__imp_PathFindFileNameW
0x1400a80eb  nop     dword ptr [rax+rax+00h]
0x1400a80f0  mov     r12, rax
0x1400a80f3  mov     rcx, rax; pszPath
0x1400a80f6  call    cs:__imp_PathIsFileSpecW
0x1400a80fd  nop     dword ptr [rax+rax+00h]
0x1400a8102  test    eax, eax
0x1400a8104  jnz     short loc_1400A8124
0x1400a8106  mov     rcx, [rsp+1C8h]; this
0x1400a810e  mov     r9d, 0A1h; char *
0x1400a8114  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a811b  lea     edx, [r9+20h]; void *
0x1400a811f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400a8124  mov     rcx, [rsp+1C8h+var_B8]
0x1400a812c  mov     rax, [rcx]
0x1400a812f  mov     r11, [rax+18h]
0x1400a8133  mov     rdx, [r15+50h]
0x1400a8137  movzx   r9d, byte ptr [r15+49h]
0x1400a813c  movzx   r10d, byte ptr [r15+48h]
0x1400a8141  lea     rsi, [r15+28h]
0x1400a8145  cmp     qword ptr [r15+40h], 7
0x1400a814a  jbe     short loc_1400A8151
0x1400a814c  mov     r8, [rsi]
0x1400a814f  jmp     short loc_1400A8154
0x1400a8151  mov     r8, rsi
0x1400a8154  lea     rax, GUID_NULL
0x1400a815b  mov     [rsp+1C8h+var_198], rax
0x1400a8160  mov     [rsp+1C8h+var_1A0], rdx
0x1400a8165  mov     dword ptr [rsp+1C8h+var_1A8], r9d; unsigned int
0x1400a816a  mov     r9d, r10d
0x1400a816d  mov     rdx, r12
0x1400a8170  mov     rax, r11
0x1400a8173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a8178  mov     r12d, eax
0x1400a817b  test    eax, eax
0x1400a817d  jns     loc_1400A8275
0x1400a8183  mov     ebx, eax
0x1400a8185  btr     ebx, 1Ch
0x1400a8189  mov     r9d, ebx
0x1400a818c  lea     r8, aU_0; "%%%%%u"
0x1400a8193  mov     r15d, 10h
0x1400a8199  mov     edx, r15d
0x1400a819c  lea     rcx, [rsp+1C8h+var_58]
0x1400a81a4  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400a81a9  mov     r9d, ebx
0x1400a81ac  lea     r8, a0x08x; "0x%08X"
0x1400a81b3  mov     edx, r15d
0x1400a81b6  lea     rcx, [rsp+1C8h+var_78]
0x1400a81be  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400a81c3  cmp     qword ptr [rsi+18h], 7
0x1400a81c8  jbe     short loc_1400A81CD
0x1400a81ca  mov     rsi, [rsi]
0x1400a81cd  mov     [rsp+1C8h+var_160], rsi
0x1400a81d2  cmp     qword ptr [r14+18h], 7
0x1400a81d7  jbe     short loc_1400A81DC
0x1400a81d9  mov     r14, [r14]
0x1400a81dc  mov     [rsp+1C8h+var_168], r14
0x1400a81e1  mov     rcx, [rsp+1C8h+var_140]
0x1400a81e9  mov     rcx, [rcx]
0x1400a81ec  lea     rax, [rcx+480h]
0x1400a81f3  mov     qword ptr [rsp+1C8h+var_174+4], rax
0x1400a81f8  add     rcx, r15; this
0x1400a81fb  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400a8200  mov     qword ptr [rsp+1C8h+FileSize], rax
0x1400a8208  lea     rax, [rsp+1C8h+var_160]
0x1400a820d  mov     [rsp+1C8h+var_180], rax; __int64
0x1400a8212  lea     rax, [rsp+1C8h+var_168]
0x1400a8217  mov     [rsp+1C8h+var_188], rax; __int64
0x1400a821c  lea     rax, [rsp+1C8h+var_78]
0x1400a8224  mov     [rsp+1C8h+var_190], rax; unsigned __int16 *
0x1400a8229  lea     rax, [rsp+1C8h+var_58]
0x1400a8231  mov     [rsp+1C8h+var_198], rax; unsigned __int16 *
0x1400a8236  lea     rax, [rsp+1C8h+var_174+4]
0x1400a823b  mov     [rsp+1C8h+var_1A0], rax; __int64
0x1400a8240  lea     rax, [rsp+1C8h+FileSize]
0x1400a8248  mov     [rsp+1C8h+var_1A8], rax; int
0x1400a824d  lea     rcx, MSVML_FAILED_TO_START_GUEST_COPY; struct _EVENT_DESCRIPTOR *
0x1400a8254  call    ??$VmEventWriteAndReport@PEBGPEBGAEAY0BA@GAEAY0BA@GPEBGPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3AEAY0BA@G433@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort (&)[16],ushort (&)[16],ushort const *,ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort (&)[16],ushort (&)[16],ushort const * &&,ushort const * &&)
0x1400a8259  mov     rcx, [rsp+1C8h]; this
0x1400a8261  mov     r9d, r12d; char *
0x1400a8264  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\wpcore\\workertask"...
0x1400a826b  mov     edx, 0DEh; void *
0x1400a8270  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a8275  mov     [rsp+1C8h+Overlapped.Internal], rdi
0x1400a827d  mov     [rsp+1C8h+Overlapped.InternalHigh], rdi
0x1400a8285  mov     qword ptr [rsp+1C8h+Overlapped.10h], rdi
0x1400a828d  mov     rax, [rsp+1C8h+var_118]
0x1400a8295  mov     [rsp+1C8h+Overlapped.hEvent], rax
0x1400a829d  mov     eax, [rsp+1C8h+var_C0]
0x1400a82a4  mov     [rsp+1C8h+NumberOfBytesTransferred], eax
0x1400a82ab  mov     [rsp+1C8h+var_178], 1
0x1400a82b3  lea     r9, [rsp+1C8h+Overlapped]; struct _OVERLAPPED *
0x1400a82bb  lea     r8, [rsp+1C8h+NumberOfBytesTransferred]; unsigned int *
0x1400a82c3  mov     rdx, [rsp+1C8h+var_A8]; void *
0x1400a82cb  lea     rcx, [rsp+1C8h+var_120]; this
0x1400a82d3  call    ?Read@VmFile@Vml@@QEAAHPEAXAEAKPEAU_OVERLAPPED@@@Z; Vml::VmFile::Read(void *,ulong &,_OVERLAPPED *)
0x1400a82d8  mov     ecx, eax
0x1400a82da  mov     qword ptr [rsp+1C8h+FileSize], rdi
0x1400a82e2  mov     r9, rdi
0x1400a82e5  mov     [rsp+1C8h+var_150], rdi
0x1400a82ea  mov     r8d, edi
0x1400a82ed  mov     dword ptr [rsp+1C8h+var_174], edi
0x1400a82f1  mov     [rsp+1C8h+var_178], edi
0x1400a82f5  mov     eax, edi
0x1400a82f7  test    ecx, ecx
0x1400a82f9  setz    al
0x1400a82fc  mov     r12, qword ptr [rsp+1C8h+var_174+4]
0x1400a8301  test    eax, eax
0x1400a8303  jnz     loc_1400A84CE
0x1400a8309  cmp     [rsp+1C8h+NumberOfBytesTransferred], edi
0x1400a8310  ja      loc_1400A8551
0x1400a8316  mov     rcx, [rsp+1C8h+var_B8]
0x1400a831e  mov     rax, [rcx]
0x1400a8321  lea     rbx, GUID_NULL
0x1400a8328  mov     rdx, rbx
0x1400a832b  mov     rax, [rax+30h]
0x1400a832f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a8334  mov     r12d, eax
0x1400a8337  test    eax, eax
0x1400a8339  jns     loc_1400A8431
0x1400a833f  mov     ebx, eax
0x1400a8341  btr     ebx, 1Ch
0x1400a8345  mov     r9d, ebx
0x1400a8348  lea     r8, aU_0; "%%%%%u"
0x1400a834f  mov     r15d, 10h
0x1400a8355  mov     edx, r15d
0x1400a8358  lea     rcx, [rsp+1C8h+var_78]
0x1400a8360  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400a8365  mov     r9d, ebx
0x1400a8368  lea     r8, a0x08x; "0x%08X"
0x1400a836f  mov     edx, r15d
0x1400a8372  lea     rcx, [rsp+1C8h+var_58]
0x1400a837a  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400a837f  cmp     qword ptr [rsi+18h], 7
0x1400a8384  jbe     short loc_1400A8389
0x1400a8386  mov     rsi, [rsi]
0x1400a8389  mov     [rsp+1C8h+var_160], rsi
0x1400a838e  cmp     qword ptr [r14+18h], 7
0x1400a8393  jbe     short loc_1400A8398
  ... truncated ...
```
