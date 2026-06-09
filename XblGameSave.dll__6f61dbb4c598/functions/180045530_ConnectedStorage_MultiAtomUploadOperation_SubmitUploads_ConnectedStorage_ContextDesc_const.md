# ConnectedStorage::MultiAtomUploadOperation::SubmitUploads(ConnectedStorage::ContextDesc const &)

- ea: `0x180045530`
- end: `0x180045f1d`
- name: `?SubmitUploads@MultiAtomUploadOperation@ConnectedStorage@@QEBA?AV?$shared_ptr@VWebServiceCancelCallback@ConnectedStorage@@@std@@AEBVContextDesc@2@@Z`
- size: `2541`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800463e0`

## callees

- `0x180003c70`
- `0x180004754`
- `0x18000a040`
- `0x18000aae4`
- `0x18000b67c`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x18000d2b8`
- `0x18000d6bc`
- `0x1800113bc`
- `0x180011c0c`
- `0x180011c68`
- `0x180012bd4`
- `0x18001303c`
- `0x1800136a8`
- `0x1800190f0`
- `0x180019128`
- `0x18001a548`
- `0x18001c090`
- `0x18001c618`
- `0x18001eac0`
- `0x1800271ac`
- `0x1800296a4`
- `0x18003c8c4`
- `0x18003d190`
- `0x18003db48`
- `0x18003ea50`
- `0x18003ee9c`
- `0x18003f078`
- `0x18003f4c0`
- `0x180040c44`
- `0x180043070`
- `0x180043208`
- `0x180043580`
- `0x180043758`
- `0x180043cb0`
- `0x180045530`
- `0x1800486b0`
- `0x18004feb8`
- `0x180069350`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045644`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ce8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045644`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ce8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045c5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045c48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045c5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045db9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045dc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045db9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045dc8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004596d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004596d`

## string_xrefs

- `0x180045ec5`: `CoDisconnectableContext::MakeAndInitializeDisconnectableObject<CompressedFileUploadStream>(stream, std::move(file))`
- `0x180045ef0`: `CoDisconnectableContext::MakeDisconnectableObject<FileUploadStream>(uploadStream, atom.OpenForRead(), FileUploadStream_ReadMode_CloseAfterEachRead)`
- `0x1800459da`: `Content-Type: application/json\n`
- `0x180045f0d`: `StringCchPrintfW(additionalJsonPayload, _countof(additionalJsonPayload), jsonFormatString, uploadSize)`

## pseudocode

```c
// Hidden C++ exception states: #wind=30 #try_helpers=1
_OWORD *__fastcall ConnectedStorage::MultiAtomUploadOperation::SubmitUploads(
        __int64 a1,
        _OWORD *a2,
        struct ConnectedStorage::ContextDesc *a3)
{
  unsigned __int16 v6; // dx
  const struct ConnectedStorage::ContextDesc *v7; // rcx
  char *v8; // r8
  char *v9; // r8
  __int64 v10; // rdx
  ConnectedStorage::MultiAtomUploadOperation *v12; // rcx
  __int64 v13; // rax
  __m128i si128; // xmm7
  __int64 v15; // r13
  HSTRING v16; // r12
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rbx
  int v18; // edi
  const unsigned __int16 *v19; // r8
  __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // r8
  unsigned __int64 v23; // r15
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rdi
  int v25; // eax
  const unsigned __int16 *v26; // r8
  __int64 v27; // rax
  int v28; // ebx
  __int64 v29; // rax
  const unsigned __int16 *v30; // r8
  int v31; // eax
  const unsigned __int16 *v32; // r8
  HSTRING TickCount64; // rdi
  _QWORD *v34; // rbx
  int v35; // eax
  const unsigned __int16 *v36; // r8
  __int64 *v37; // r13
  __int64 v38; // rbx
  void (__fastcall *v39)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, _QWORD, unsigned int, HSTRING *, __int64 *, HSTRING *, HSTRING, void ***); // r12
  HSTRING *v40; // r15
  HSTRING *v41; // rbx
  HSTRING *v42; // rax
  __int64 v43; // rbx
  __int128 v44; // xmm6
  char *v45; // r8
  _OWORD *v46; // rdx
  __int64 v47; // r8
  unsigned int v48; // [rsp+20h] [rbp-4D8h]
  bool IsCompressionEnabled; // [rsp+60h] [rbp-498h]
  unsigned int v50[2]; // [rsp+68h] [rbp-490h] BYREF
  struct _GUID *v51; // [rsp+70h] [rbp-488h]
  __int64 v52; // [rsp+78h] [rbp-480h] BYREF
  __int128 v53; // [rsp+80h] [rbp-478h] BYREF
  HSTRING v54; // [rsp+90h] [rbp-468h]
  ConnectedStorage::File *v55; // [rsp+98h] [rbp-460h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-458h] BYREF
  struct ConnectedStorage::Atom *v57; // [rsp+A8h] [rbp-450h]
  struct ConnectedStorage::ContextDesc *v58; // [rsp+B0h] [rbp-448h]
  HSTRING string; // [rsp+B8h] [rbp-440h] BYREF
  HSTRING v60; // [rsp+C0h] [rbp-438h] BYREF
  HSTRING v61; // [rsp+C8h] [rbp-430h] BYREF
  _QWORD v62[2]; // [rsp+D0h] [rbp-428h] BYREF
  std::_Ref_count_base *v63[2]; // [rsp+E0h] [rbp-418h] BYREF
  std::_Ref_count_base *v64[2]; // [rsp+F0h] [rbp-408h] BYREF
  void **v65; // [rsp+100h] [rbp-3F8h] BYREF
  ConnectedStorage::File **v66; // [rsp+108h] [rbp-3F0h]
  void *v67; // [rsp+110h] [rbp-3E8h]
  std::_Ref_count_base **v68; // [rsp+118h] [rbp-3E0h]
  void ***v69; // [rsp+138h] [rbp-3C0h]
  _QWORD *v70; // [rsp+140h] [rbp-3B8h]
  __int64 v71; // [rsp+148h] [rbp-3B0h]
  struct ConnectedStorage::ContextDesc *v72; // [rsp+150h] [rbp-3A8h]
  __int64 v73; // [rsp+158h] [rbp-3A0h]
  char v74[8]; // [rsp+168h] [rbp-390h] BYREF
  char v75[8]; // [rsp+170h] [rbp-388h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+178h] [rbp-380h] BYREF
  char v77[8]; // [rsp+188h] [rbp-370h] BYREF
  __int64 v78; // [rsp+190h] [rbp-368h] BYREF
  std::_Ref_count_base *v79; // [rsp+198h] [rbp-360h]
  char v80[8]; // [rsp+1A0h] [rbp-358h] BYREF
  LPCRITICAL_SECTION v81[3]; // [rsp+1A8h] [rbp-350h] BYREF
  LPCRITICAL_SECTION v82[2]; // [rsp+1C0h] [rbp-338h] BYREF
  _OWORD v83[2]; // [rsp+1D0h] [rbp-328h] BYREF
  _QWORD v84[2]; // [rsp+1F0h] [rbp-308h] BYREF
  _BYTE Src[32]; // [rsp+210h] [rbp-2E8h] BYREF
  _QWORD v86[3]; // [rsp+230h] [rbp-2C8h] BYREF
  _BYTE v87[32]; // [rsp+250h] [rbp-2A8h] BYREF
  GUID v88; // [rsp+270h] [rbp-288h] BYREF
  unsigned __int64 v89[4]; // [rsp+280h] [rbp-278h] BYREF
  HSTRING v90[8]; // [rsp+2A0h] [rbp-258h] BYREF
  _BYTE v91[16]; // [rsp+2E0h] [rbp-218h] BYREF
  unsigned __int64 v92; // [rsp+2F0h] [rbp-208h]
  unsigned __int16 v93[16]; // [rsp+370h] [rbp-188h] BYREF
  WCHAR sourceString[128]; // [rsp+390h] [rbp-168h] BYREF

  v58 = a3;
  v73 = a1;
  v62[1] = a2;
  v72 = a3;
  std::make_shared<ConnectedStorage::NtmCancelCallback,>(&v53);
  if ( ConnectedStorage::Metered::UploadAllowed(v7, v6) )
  {
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)(a1 + 152),
      v8);
    v70 = (_QWORD *)(a1 + 24);
    v10 = *(_QWORD *)(a1 + 24);
    if ( *(_QWORD *)(v10 + 88) )
    {
      v71 = a1 + 24;
      LODWORD(v51) = 0;
      if ( !*(_QWORD *)(a1 + 208) )
      {
        ConnectedStorage::MultiAtomUploadOperation::AllTransfersCompleted(a1, 8);
        *a2 = v53;
        v53 = 0;
        LeaveCriticalSection(lpCriticalSection[0]);
        return a2;
      }
      ConnectedStorage::MakeUrl(v87, a3);
      ConnectedStorage::TypedNtmOperation<ConnectedStorage::MultiAtomUploadOperation>::weak_from_this(a1, &v78);
      v13 = **(_QWORD **)(a1 + 200);
      v62[0] = v13;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( !*(_BYTE *)(v13 + 25) )
      {
        v15 = v13 + 32;
        v57 = (struct ConnectedStorage::Atom *)(v13 + 32);
        v52 = 0;
        IsCompressionEnabled = ConnectedStorage::MultiAtomUploadOperation::IsCompressionEnabled(v12);
        if ( IsCompressionEnabled )
        {
          ConnectedStorage::Atom::OpenForRead(v15, &v55);
          v16 = (HSTRING)ConnectedStorage::File::Size(v55);
          v17 = 0;
          *(_QWORD *)v50 = 0;
          *(_OWORD *)v63 = 0;
          v65 = &std::_Func_impl_no_alloc<_lambda_83c4e2e1164131525f93064bd461a067_,long,>::`vftable';
          v66 = &v55;
          v67 = v63;
          v69 = &v65;
          v18 = ConnectedStorage::CoDisconnectableContext::_ExecuteInContext(&v65);
          if ( v18 >= 0 )
          {
            v20 = ConnectedStorage::GitPtr<IStream>::Get(v63, v74);
            Microsoft::WRL::ComPtr<IStorageContainerSyncData>::operator=(v50, v20);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v74);
            v17 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v50;
          }
          if ( v63[1] )
            std::_Ref_count_base::_Decref(v63[1]);
          if ( v18 < 0 )
            ConnectedStorage::ReportErrorAndThrow(
              (ConnectedStorage *)(unsigned int)v18,
              (int)L"CoDisconnectableContext::MakeAndInitializeDisconnectableObject<CompressedFileUploadStream>(stream, std::move(file))",
              v19);
          memset_0(&v88, 0, 0x50u);
          v21 = (*v17)[12](v17, &v88, (__int64 *)1);
          if ( v21 < 0 )
            ConnectedStorage::ReportErrorAndThrow(
              (ConnectedStorage *)(unsigned int)v21,
              (int)L"stream->Stat(&stats, STATFLAG_NONAME)",
              v22);
          v23 = v89[0];
          if ( v89[0] && (v54 = v16, v89[0] < (unsigned __int64)v16) )
          {
            v24 = **v17;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
            v25 = v24(v17, &GUID_0000000c_0000_0000_c000_000000000046, &v52);
            if ( v25 < 0 )
              ConnectedStorage::ReportErrorAndThrow(
                (ConnectedStorage *)(unsigned int)v25,
                (int)L"stream.As(&uploadStream)",
                v26);
          }
          else
          {
            IsCompressionEnabled = 0;
            v16 = 0;
            v54 = 0;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v50);
          std::_Temporary_owner<ConnectedStorage::File>::~_Temporary_owner<ConnectedStorage::File>(&v55);
        }
        else
        {
          v23 = 0;
          v16 = 0;
          v54 = 0;
        }
        if ( !v52 )
        {
          v50[0] = 1;
          v27 = ConnectedStorage::Atom::OpenForRead(v15, v77);
          *(_OWORD *)v64 = 0;
          v65 = &std::_Func_impl_no_alloc<_lambda_278fc9e9aac900f447bf51355f91d5cc_,long,>::`vftable';
          v66 = (ConnectedStorage::File **)v27;
          v67 = v50;
          v68 = v64;
          v69 = &v65;
          v28 = ConnectedStorage::CoDisconnectableContext::_ExecuteInContext(&v65);
          if ( v28 >= 0 )
          {
            v29 = ConnectedStorage::GitPtr<IStream>::Get(v64, v75);
            Microsoft::WRL::ComPtr<IStorageContainerSyncData>::operator=(&v52, v29);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v75);
          }
          if ( v64[1] )
            std::_Ref_count_base::_Decref(v64[1]);
          std::_Temporary_owner<ConnectedStorage::File>::~_Temporary_owner<ConnectedStorage::File>(v77);
          if ( v28 < 0 )
            ConnectedStorage::ReportErrorAndThrow(
              (ConnectedStorage *)(unsigned int)v28,
              (int)L"CoDisconnectableContext::MakeDisconnectableObject<FileUploadStream>(uploadStream, atom.OpenForRead(),"
                    " FileUploadStream_ReadMode_CloseAfterEachRead)",
              v30);
          memset_0(v91, 0, 0x50u);
          v31 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v52 + 96LL))(v52, v91, 1);
          if ( v31 < 0 )
            ConnectedStorage::ReportErrorAndThrow(
              (ConnectedStorage *)(unsigned int)v31,
              (int)L"uploadStream->Stat(&stats, STATFLAG_NONAME)",
              v32);
          v23 = v92;
        }
        TickCount64 = (HSTRING)GetTickCount64();
        ConnectedStorage::GuidToString(v86, v15 + 16);
        v83[0] = 0;
        v83[1] = si128;
        LOWORD(v83[0]) = 0;
        std::wstring::wstring(Src, v87);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::_Append<unsigned short>(v83);
        std::wstring::end(v86, v80);
        std::wstring::_Append<unsigned short>(Src);
        v34 = v70;
        ConnectedStorage::NtmWebService::MakeHeadersWithContext(*v70, v84, Src, v58);
        std::wstring::_Append<unsigned short>(v83);
        *(_OWORD *)v93 = *(_OWORD *)L"{size: %u}";
        *(_QWORD *)&v93[7] = *(_QWORD *)L"%u}";
        sourceString[0] = 0;
        v35 = StringCchPrintfW(sourceString, 0x80u, v93, v23);
        if ( v35 < 0 )
          ConnectedStorage::ReportErrorAndThrow(
            (ConnectedStorage *)(unsigned int)v35,
            (int)L"StringCchPrintfW(additionalJsonPayload, _countof(additionalJsonPayload), jsonFormatString, uploadSize)",
            v36);
        v37 = *(__int64 **)(*v34 + 88LL);
        v38 = *v37;
        v63[0] = (std::_Ref_count_base *)&v65;
        std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(&v88, &v78);
        ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v89, v57);
        ConnectedStorage::ContextDesc::ContextDesc(v90, v58);
        v90[6] = TickCount64;
        v90[7] = v16;
        v69 = 0;
        v69 = (void ***)std::_Global_new<std::_Func_impl_no_alloc<_lambda_85cb84e23cf7ec008948e976a1bfbf73_,void,_NTM_TRANSFER_STATUS const &,unsigned int,long>,_lambda_85cb84e23cf7ec008948e976a1bfbf73_>(&v88);
        v39 = *(void (__fastcall **)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, _QWORD, unsigned int, HSTRING *, __int64 *, HSTRING *, HSTRING, void ***))(v38 + 16);
        v40 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v61, sourceString);
        v57 = (struct ConnectedStorage::Atom *)&v56;
        v56 = v52;
        Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&v56);
        v41 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v60, (__int64)v83);
        v42 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, (__int64)Src);
        LOWORD(v48) = 95;
        v39(v37, v82, v42, ((unsigned __int8)IsCompressionEnabled << 22) + 98304, v48, v41, &v56, v40, v54, &v65);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v60);
        v60 = 0;
        WindowsDeleteString(v61);
        v61 = 0;
        _lambda_85cb84e23cf7ec008948e976a1bfbf73_::~_lambda_85cb84e23cf7ec008948e976a1bfbf73_((_lambda_85cb84e23cf7ec008948e976a1bfbf73_ *)&v88);
        v43 = v53;
        v44 = *(_OWORD *)v82;
        *(_OWORD *)v64 = *(_OWORD *)v82;
        ConnectedStorage::Mutex::Lock::Lock(
          (ConnectedStorage::Mutex::Lock *)v81,
          (struct _RTL_CRITICAL_SECTION *)(v53 + 32),
          v45);
        v46 = *(_OWORD **)(v43 + 16);
        if ( v46 == *(_OWORD **)(v43 + 24) )
        {
          std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v43 + 8, v46, v64);
        }
        else
        {
          *v46 = v44;
          *(_QWORD *)(v43 + 16) += 16LL;
        }
        LeaveCriticalSection(v81[0]);
        LODWORD(v51) = (_DWORD)v51 + 1;
        std::wstring::_Tidy_deallocate(v84);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(v83);
        std::wstring::_Tidy_deallocate(v86);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::ContainerIndexEntry const *>>>,std::_Iterator_base0>::operator++(v62);
        v13 = v62[0];
      }
      if ( v79 )
        std::_Ref_count_base::_Decwref(v79);
      std::wstring::_Tidy_deallocate(v87);
      *a2 = v53;
    }
    else
    {
      ConnectedStorage::Mutex::Unlock::Unlock(
        (ConnectedStorage::Mutex::Unlock *)v81,
        (struct ConnectedStorage::Mutex *)(v10 + 40),
        v9);
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        a1 + 32,
        1,
        v47);
      *a2 = v53;
      EnterCriticalSection(v81[0]);
    }
    LeaveCriticalSection(lpCriticalSection[0]);
  }
  else
  {
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      a1 + 32,
      18,
      v8);
    *a2 = v53;
  }
  return a2;
}

```

## disassembly

```asm
0x180045530  mov     rax, rsp
0x180045533  push    rbx
0x180045534  push    rsi
0x180045535  push    rdi
0x180045536  push    r12
0x180045538  push    r13
0x18004553a  push    r14
0x18004553c  push    r15
0x18004553e  sub     rsp, 4C0h
0x180045545  movaps  xmmword ptr [rax-48h], xmm6
0x180045549  movaps  xmmword ptr [rax-58h], xmm7
0x18004554d  mov     rax, cs:__security_cookie
0x180045554  xor     rax, rsp
0x180045557  mov     [rsp+4F8h+var_68], rax
0x18004555f  mov     rdi, r8
0x180045562  mov     [rsp+4F8h+var_448], r8
0x18004556a  mov     r14, rdx
0x18004556d  mov     rbx, rcx
0x180045570  mov     [rsp+4F8h+var_3A0], rcx
0x180045578  mov     [rsp+4F8h+var_420], rdx
0x180045580  mov     [rsp+4F8h+var_3A8], r8
0x180045588  xor     esi, esi
0x18004558a  lea     rcx, [rsp+4F8h+var_478]
0x180045592  call    ??$make_shared@VNtmCancelCallback@ConnectedStorage@@$$V@std@@YA?AV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@0@XZ; std::make_shared<ConnectedStorage::NtmCancelCallback,>(void)
0x180045597  nop
0x180045598  call    ?UploadAllowed@Metered@ConnectedStorage@@SAEAEBVContextDesc@2@G@Z; ConnectedStorage::Metered::UploadAllowed(ConnectedStorage::ContextDesc const &,ushort)
0x18004559d  test    al, al
0x18004559f  jnz     short loc_1800455C9
0x1800455a1  lea     rcx, [rbx+20h]
0x1800455a5  lea     edx, [rsi+12h]
0x1800455a8  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x1800455ad  mov     rcx, qword ptr [rsp+4F8h+var_478]
0x1800455b5  mov     [r14], rcx
0x1800455b8  mov     rcx, qword ptr [rsp+4F8h+var_478+8]
0x1800455c0  mov     [r14+8], rcx
0x1800455c4  jmp     loc_180045E91
0x1800455c9  lea     rdx, [rbx+98h]; struct ConnectedStorage::Mutex *
0x1800455d0  lea     rcx, [rsp+4F8h+lpCriticalSection]; this
0x1800455d8  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800455dd  nop
0x1800455de  lea     rax, [rbx+18h]
0x1800455e2  mov     [rsp+4F8h+var_3B8], rax
0x1800455ea  mov     rdx, [rax]
0x1800455ed  cmp     [rdx+58h], rsi
0x1800455f1  jz      loc_180045E3C
0x1800455f7  mov     [rsp+4F8h+var_3B0], rax
0x1800455ff  mov     dword ptr [rsp+4F8h+var_488], esi
0x180045603  cmp     [rbx+0D0h], rsi
0x18004560a  jnz     short loc_180045653
0x18004560c  mov     edx, 8
0x180045611  mov     rcx, rbx
0x180045614  call    ?AllTransfersCompleted@MultiAtomUploadOperation@ConnectedStorage@@AEBAXW4Status@WebService@2@@Z; ConnectedStorage::MultiAtomUploadOperation::AllTransfersCompleted(ConnectedStorage::WebService::Status)
0x180045619  mov     rax, qword ptr [rsp+4F8h+var_478]
0x180045621  mov     [r14], rax
0x180045624  mov     rax, qword ptr [rsp+4F8h+var_478+8]
0x18004562c  mov     [r14+8], rax
0x180045630  xorps   xmm0, xmm0
0x180045633  movdqu  [rsp+4F8h+var_478], xmm0
0x18004563c  mov     rcx, [rsp+4F8h+lpCriticalSection]; lpCriticalSection
0x180045644  call    cs:__imp_LeaveCriticalSection
0x18004564a  nop
0x18004564b  mov     rax, r14
0x18004564e  jmp     loc_180045E94
0x180045653  mov     rdx, rdi
0x180045656  lea     rcx, [rsp+4F8h+var_2A8]
0x18004565e  call    ?MakeUrl@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@@Z; ConnectedStorage::MakeUrl(ConnectedStorage::ContextDesc const &)
0x180045663  nop
0x180045664  lea     rdx, [rsp+4F8h+var_368]
0x18004566c  mov     rcx, rbx
0x18004566f  call    ?weak_from_this@?$TypedNtmOperation@VMultiAtomUploadOperation@ConnectedStorage@@@ConnectedStorage@@QEBA?AV?$weak_ptr@$$CBVMultiAtomUploadOperation@ConnectedStorage@@@std@@XZ; ConnectedStorage::TypedNtmOperation<ConnectedStorage::MultiAtomUploadOperation>::weak_from_this(void)
0x180045674  nop
0x180045675  mov     rax, [rbx+0C8h]
0x18004567c  mov     rax, [rax]
0x18004567f  mov     [rsp+4F8h+var_428], rax
0x180045687  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x18004568f  cmp     [rax+19h], sil
0x180045693  jnz     loc_180045D4E
0x180045699  lea     r13, [rax+20h]
0x18004569d  mov     [rsp+4F8h+var_450], r13
0x1800456a5  mov     [rsp+4F8h+var_480], rsi
0x1800456aa  call    ?IsCompressionEnabled@MultiAtomUploadOperation@ConnectedStorage@@AEBA_NXZ; ConnectedStorage::MultiAtomUploadOperation::IsCompressionEnabled(void)
0x1800456af  mov     [rsp+4F8h+var_498], al
0x1800456b3  test    al, al
0x1800456b5  jz      loc_18004583E
0x1800456bb  lea     rdx, [rsp+4F8h+var_460]
0x1800456c3  mov     rcx, r13
0x1800456c6  call    ?OpenForRead@Atom@ConnectedStorage@@QEBA?AV?$unique_ptr@VFile@ConnectedStorage@@U?$default_delete@VFile@ConnectedStorage@@@std@@@std@@XZ; ConnectedStorage::Atom::OpenForRead(void)
0x1800456cb  nop
0x1800456cc  mov     rcx, [rsp+4F8h+var_460]; this
0x1800456d4  call    ?Size@File@ConnectedStorage@@QEAAKXZ; ConnectedStorage::File::Size(void)
0x1800456d9  mov     r12d, eax
0x1800456dc  mov     rbx, rsi
0x1800456df  mov     qword ptr [rsp+4F8h+var_490], rbx
0x1800456e4  xorps   xmm0, xmm0
0x1800456e7  movdqu  xmmword ptr [rsp+4F8h+var_418], xmm0
0x1800456f0  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_83c4e2e1164131525f93064bd461a067_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_83c4e2e1164131525f93064bd461a067_,long,>::`vftable'
0x1800456f7  mov     [rsp+4F8h+var_3F8], rax
0x1800456ff  lea     rax, [rsp+4F8h+var_460]
0x180045707  mov     [rsp+4F8h+var_3F0], rax
0x18004570f  lea     rax, [rsp+4F8h+var_418]
0x180045717  mov     [rsp+4F8h+var_3E8], rax
0x18004571f  lea     rax, [rsp+4F8h+var_3F8]
0x180045727  mov     [rsp+4F8h+var_3C0], rax
0x18004572f  lea     rcx, [rsp+4F8h+var_3F8]
0x180045737  call    ?_ExecuteInContext@CoDisconnectableContext@ConnectedStorage@@CAJV?$function@$$A6AJXZ@std@@@Z; ConnectedStorage::CoDisconnectableContext::_ExecuteInContext(std::function<long (void)>)
0x18004573c  mov     edi, eax
0x18004573e  test    eax, eax
0x180045740  js      short loc_180045776
0x180045742  lea     rdx, [rsp+4F8h+var_390]
0x18004574a  lea     rcx, [rsp+4F8h+var_418]
0x180045752  call    ?Get@?$GitPtr@UIStream@@@ConnectedStorage@@QEBA?AV?$ComPtr@UIStream@@@WRL@Microsoft@@XZ; ConnectedStorage::GitPtr<IStream>::Get(void)
0x180045757  mov     rdx, rax
0x18004575a  lea     rcx, [rsp+4F8h+var_490]
0x18004575f  call    ??4?$ComPtr@UIStorageContainerSyncData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IStorageContainerSyncData>::operator=(Microsoft::WRL::ComPtr<IStorageContainerSyncData> &&)
0x180045764  lea     rcx, [rsp+4F8h+var_390]
0x18004576c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045771  mov     rbx, qword ptr [rsp+4F8h+var_490]
0x180045776  mov     rcx, [rsp+4F8h+var_418+8]; this
0x18004577e  test    rcx, rcx
0x180045781  jz      short loc_180045788
0x180045783  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180045788  test    edi, edi
0x18004578a  js      loc_180045EC5
0x180045790  xor     edx, edx; Val
0x180045792  lea     r8d, [rdx+50h]; Size
0x180045796  lea     rcx, [rsp+4F8h+var_288]; void *
0x18004579e  call    memset_0
0x1800457a3  mov     rax, [rbx]
0x1800457a6  mov     r8d, 1
0x1800457ac  lea     rdx, [rsp+4F8h+var_288]
0x1800457b4  mov     rcx, rbx
0x1800457b7  mov     rax, [rax+60h]
0x1800457bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457c0  test    eax, eax
0x1800457c2  js      loc_180045ED3
0x1800457c8  mov     r15, [rsp+4F8h+var_278]
0x1800457d0  test    r15, r15
0x1800457d3  jz      short loc_180045814
0x1800457d5  mov     [rsp+4F8h+var_468], r12
0x1800457dd  cmp     r15, r12
0x1800457e0  jnb     short loc_180045814
0x1800457e2  mov     rax, [rbx]
0x1800457e5  mov     rdi, [rax]
0x1800457e8  lea     rcx, [rsp+4F8h+var_480]
0x1800457ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800457f2  lea     r8, [rsp+4F8h+var_480]
0x1800457f7  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800457fe  mov     rcx, rbx
0x180045801  mov     rax, rdi
0x180045804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045809  nop
0x18004580a  test    eax, eax
0x18004580c  js      loc_180045EE1
0x180045812  jmp     short loc_180045824
0x180045814  mov     [rsp+4F8h+var_498], sil
0x180045819  mov     r12, rsi
0x18004581c  mov     [rsp+4F8h+var_468], rsi
0x180045824  lea     rcx, [rsp+4F8h+var_490]
0x180045829  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004582e  nop
0x18004582f  lea     rcx, [rsp+4F8h+var_460]
0x180045837  call    ??1?$_Temporary_owner@VFile@ConnectedStorage@@@std@@QEAA@XZ; std::_Temporary_owner<ConnectedStorage::File>::~_Temporary_owner<ConnectedStorage::File>(void)
0x18004583c  jmp     short loc_18004584C
0x18004583e  mov     r15, rsi
0x180045841  mov     r12, rsi
0x180045844  mov     [rsp+4F8h+var_468], rsi
0x18004584c  cmp     [rsp+4F8h+var_480], rsi
0x180045851  jnz     loc_18004596D
0x180045857  mov     [rsp+4F8h+var_490], 1
0x18004585f  lea     rdx, [rsp+4F8h+var_370]
0x180045867  mov     rcx, r13
0x18004586a  call    ?OpenForRead@Atom@ConnectedStorage@@QEBA?AV?$unique_ptr@VFile@ConnectedStorage@@U?$default_delete@VFile@ConnectedStorage@@@std@@@std@@XZ; ConnectedStorage::Atom::OpenForRead(void)
0x18004586f  nop
0x180045870  xorps   xmm0, xmm0
0x180045873  movdqu  xmmword ptr [rsp+4F8h+var_408], xmm0
0x18004587c  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_278fc9e9aac900f447bf51355f91d5cc_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_278fc9e9aac900f447bf51355f91d5cc_,long,>::`vftable'
0x180045883  mov     [rsp+4F8h+var_3F8], rcx
0x18004588b  mov     [rsp+4F8h+var_3F0], rax
0x180045893  lea     rax, [rsp+4F8h+var_490]
0x180045898  mov     [rsp+4F8h+var_3E8], rax
0x1800458a0  lea     rax, [rsp+4F8h+var_408]
0x1800458a8  mov     [rsp+4F8h+var_3E0], rax
0x1800458b0  lea     rax, [rsp+4F8h+var_3F8]
0x1800458b8  mov     [rsp+4F8h+var_3C0], rax
0x1800458c0  lea     rcx, [rsp+4F8h+var_3F8]
0x1800458c8  call    ?_ExecuteInContext@CoDisconnectableContext@ConnectedStorage@@CAJV?$function@$$A6AJXZ@std@@@Z; ConnectedStorage::CoDisconnectableContext::_ExecuteInContext(std::function<long (void)>)
0x1800458cd  mov     ebx, eax
0x1800458cf  test    eax, eax
0x1800458d1  js      short loc_180045903
0x1800458d3  lea     rdx, [rsp+4F8h+var_388]
0x1800458db  lea     rcx, [rsp+4F8h+var_408]
0x1800458e3  call    ?Get@?$GitPtr@UIStream@@@ConnectedStorage@@QEBA?AV?$ComPtr@UIStream@@@WRL@Microsoft@@XZ; ConnectedStorage::GitPtr<IStream>::Get(void)
0x1800458e8  mov     rdx, rax
0x1800458eb  lea     rcx, [rsp+4F8h+var_480]
0x1800458f0  call    ??4?$ComPtr@UIStorageContainerSyncData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IStorageContainerSyncData>::operator=(Microsoft::WRL::ComPtr<IStorageContainerSyncData> &&)
0x1800458f5  lea     rcx, [rsp+4F8h+var_388]
0x1800458fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045902  nop
0x180045903  mov     rcx, [rsp+4F8h+var_408+8]; this
0x18004590b  test    rcx, rcx
0x18004590e  jz      short loc_180045916
0x180045910  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180045915  nop
0x180045916  lea     rcx, [rsp+4F8h+var_370]
0x18004591e  call    ??1?$_Temporary_owner@VFile@ConnectedStorage@@@std@@QEAA@XZ; std::_Temporary_owner<ConnectedStorage::File>::~_Temporary_owner<ConnectedStorage::File>(void)
0x180045923  test    ebx, ebx
0x180045925  js      loc_180045EF0
0x18004592b  xor     edx, edx; Val
0x18004592d  lea     r8d, [rdx+50h]; Size
0x180045931  lea     rcx, [rsp+4F8h+var_218]; void *
0x180045939  call    memset_0
0x18004593e  mov     rcx, [rsp+4F8h+var_480]
0x180045943  mov     rax, [rcx]
0x180045946  mov     r8d, 1
0x18004594c  lea     rdx, [rsp+4F8h+var_218]
0x180045954  mov     rax, [rax+60h]
0x180045958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004595d  test    eax, eax
0x18004595f  js      loc_180045EFE
0x180045965  mov     r15, [rsp+4F8h+var_208]
0x18004596d  call    cs:__imp_GetTickCount64
0x180045973  mov     rdi, rax
0x180045976  lea     rdx, [r13+10h]
0x18004597a  lea     rcx, [rsp+4F8h+var_2C8]
0x180045982  call    ?GuidToString@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; ConnectedStorage::GuidToString(_GUID const &)
0x180045987  nop
0x180045988  xorps   xmm0, xmm0
0x18004598b  movups  [rsp+4F8h+var_328], xmm0
0x180045993  movdqu  [rsp+4F8h+var_318], xmm7
0x18004599c  mov     word ptr [rsp+4F8h+var_328], si
0x1800459a4  lea     rdx, [rsp+4F8h+var_2A8]
0x1800459ac  lea     rcx, [rsp+4F8h+Src]
0x1800459b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800459b9  nop
0x1800459ba  mov     r8d, 6
0x1800459c0  lea     rdx, aAtoms_0; "atoms/"
0x1800459c7  lea     rcx, [rsp+4F8h+Src]; Src
0x1800459cf  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800459d4  mov     r8d, 20h ; ' '
0x1800459da  lea     rdx, aContentTypeApp; "Content-Type: application/json\r\n"
0x1800459e1  lea     rcx, [rsp+4F8h+var_328]; Src
0x1800459e9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800459ee  lea     rdx, [rsp+4F8h+var_358]
0x1800459f6  lea     rcx, [rsp+4F8h+var_2C8]
0x1800459fe  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180045a03  mov     r8, [rax]
0x180045a06  add     r8, 0FFFFFFFFFFFFFFFEh
0x180045a0a  lea     rdx, [rsp+4F8h+var_2C8]
0x180045a12  cmp     [rsp+4F8h+var_2B0], 7
0x180045a1b  cmova   rdx, [rsp+4F8h+var_2C8]
0x180045a24  sub     r8, rdx
0x180045a27  sub     r8, 2
0x180045a2b  sar     r8, 1
0x180045a2e  add     rdx, 2
0x180045a32  lea     rcx, [rsp+4F8h+Src]; Src
0x180045a3a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180045a3f  mov     r9, [rsp+4F8h+var_448]
0x180045a47  lea     r8, [rsp+4F8h+Src]
0x180045a4f  lea     rdx, [rsp+4F8h+var_308]
0x180045a57  mov     rbx, [rsp+4F8h+var_3B8]
0x180045a5f  mov     rcx, [rbx]
0x180045a62  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x180045a67  nop
0x180045a68  lea     rdx, [rsp+4F8h+var_308]
0x180045a70  cmp     [rsp+4F8h+var_2F0], 7
0x180045a79  cmova   rdx, [rsp+4F8h+var_308]
0x180045a82  mov     r8, [rsp+4F8h+var_2F8]
0x180045a8a  lea     rcx, [rsp+4F8h+var_328]; Src
0x180045a92  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180045a97  movups  xmm0, xmmword ptr cs:aSizeU; "{size: %u}"
0x180045a9e  movups  xmmword ptr [rsp+4F8h+var_188], xmm0
0x180045aa6  movsd   xmm1, qword ptr cs:aSizeU+0Eh; "%u}"
0x180045aae  movsd   qword ptr [rsp+4F8h+var_188+0Eh], xmm1
0x180045ab7  mov     [rsp+4F8h+sourceString], si
0x180045abf  mov     r9, r15
0x180045ac2  lea     r8, [rsp+4F8h+var_188]; unsigned __int16 *
0x180045aca  mov     edx, 80h; unsigned __int64
0x180045acf  lea     rcx, [rsp+4F8h+sourceString]; unsigned __int16 *
0x180045ad7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045adc  test    eax, eax
0x180045ade  js      loc_180045F0D
0x180045ae4  mov     rax, [rbx]
0x180045ae7  mov     r13, [rax+58h]
0x180045aeb  mov     rbx, [r13+0]
0x180045aef  lea     rax, [rsp+4F8h+var_3F8]
0x180045af7  mov     [rsp+4F8h+var_418], rax
0x180045aff  lea     rdx, [rsp+4F8h+var_368]
0x180045b07  lea     rcx, [rsp+4F8h+var_288]
0x180045b0f  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x180045b14  nop
0x180045b15  mov     rdx, [rsp+4F8h+var_450]; struct ConnectedStorage::Atom *
0x180045b1d  lea     rcx, [rsp+4F8h+var_278]; this
0x180045b25  call    ??0Atom@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::Atom::Atom(ConnectedStorage::Atom const &)
0x180045b2a  nop
0x180045b2b  mov     rdx, [rsp+4F8h+var_448]; struct ConnectedStorage::ContextDesc *
0x180045b33  lea     rcx, [rsp+4F8h+var_258]; this
0x180045b3b  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x180045b40  mov     [rsp+4F8h+var_228], rdi
0x180045b48  mov     [rsp+4F8h+var_220], r12
0x180045b50  mov     [rsp+4F8h+var_3C0], rsi
  ... truncated ...
```
