# ConnectedStorage::StorageService::Update(HSTRING__ *,HSTRING__ *,unsigned __int64,HSTRING__ *,uint,NamedBufferInfo const * const,uint,HSTRING__ * * const,ISequentialStream *,IStorageOperationHandler *,_GUID)

- ea: `0x180025610`
- end: `0x180025cca`
- name: `?Update@StorageService@ConnectedStorage@@MEAAJPEAUHSTRING__@@0_K0IQEBUNamedBufferInfo@@IQEAPEAU3@PEAUISequentialStream@@PEAUIStorageOperationHandler@@U_GUID@@@Z`
- size: `1722`
- prototype: `__int64 __fastcall(ConnectedStorage::StorageService *this, HSTRING, char *, unsigned __int64, HSTRING, unsigned int, const struct NamedBufferInfo *const, unsigned int, HSTRING *const, struct ISequentialStream *, struct IStorageOperationHandler *, struct _GUID *)`
- caller_count: `0`
- callee_count: `30`
- tags: `reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000ca18`
- `0x18000cb9c`
- `0x180010f88`
- `0x180011040`
- `0x180011bd0`
- `0x180012328`
- `0x180012498`
- `0x1800125ec`
- `0x1800129fc`
- `0x180012ed8`
- `0x180013e1c`
- `0x180014a88`
- `0x180015008`
- `0x1800160c8`
- `0x180016df0`
- `0x1800170d4`
- `0x18001df64`
- `0x180020e68`
- `0x180021114`
- `0x180022dec`
- `0x1800235c0`
- `0x180025610`
- `0x1800263f4`
- `0x180026430`
- `0x1800264c0`
- `0x180026504`
- `0x1800268dc`
- `0x18004ae14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002572f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002572f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18002593a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18002593a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002577f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025844`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002585e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002577f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025844`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002585e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025c87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002588a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002589a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025baa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002588a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002589a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025baa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025bba`

## string_xrefs

- `0x1800256fc`: `The service has shutdown.`
- `0x1800258eb`: `StorageService::Update`
- `0x180025944`: `WindowsCompareStringOrdinal(deletes[i], updates[j].Name, &result)`
- `0x18002595c`: `ConnectedStorageService::EnsureNamesOnlyAppearInUpdateOrDelete`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall ConnectedStorage::StorageService::Update(
        ConnectedStorage::StorageService *this,
        HSTRING a2,
        char *a3,
        unsigned __int64 a4,
        HSTRING a5,
        unsigned int a6,
        const struct NamedBufferInfo *const a7,
        unsigned int a8,
        HSTRING *const a9,
        struct ISequentialStream *a10,
        struct IStorageOperationHandler *a11,
        struct _GUID *a12)
{
  unsigned int v15; // r13d
  char *v16; // r8
  const unsigned __int16 *v17; // r8
  ConnectedStorage::Service *v18; // rbx
  HSTRING *AddressOf; // rsi
  HSTRING *v20; // rdi
  HSTRING *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  PCWSTR StringRawBuffer; // rsi
  unsigned int v26; // edi
  unsigned int v27; // eax
  int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // r15d
  HSTRING v31; // r9
  __int64 v32; // rsi
  unsigned int v33; // r12d
  unsigned int i; // edi
  HRESULT v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  unsigned int j; // edi
  __int64 v40; // rax
  __int64 k; // rdi
  __int64 v42; // rax
  unsigned int v43; // ebx
  bool v44; // si
  const unsigned __int16 *v45; // rdi
  ConnectedStorage *v46; // rax
  const unsigned __int16 *v47; // r8
  int v48; // edx
  __int64 v49; // rcx
  unsigned int v50; // ebx
  unsigned __int16 *v52; // [rsp+38h] [rbp-1D0h]
  const struct _GUID *v53; // [rsp+48h] [rbp-1C0h]
  bool v54; // [rsp+60h] [rbp-1A8h] BYREF
  unsigned int v55; // [rsp+64h] [rbp-1A4h]
  unsigned int v56; // [rsp+68h] [rbp-1A0h]
  HSTRING v57; // [rsp+70h] [rbp-198h] BYREF
  HSTRING v58; // [rsp+78h] [rbp-190h] BYREF
  HSTRING v59; // [rsp+80h] [rbp-188h] BYREF
  HSTRING string[2]; // [rsp+88h] [rbp-180h] BYREF
  HSTRING v61; // [rsp+98h] [rbp-170h] BYREF
  HSTRING v62; // [rsp+A0h] [rbp-168h] BYREF
  HSTRING v63; // [rsp+A8h] [rbp-160h] BYREF
  HSTRING v64; // [rsp+B0h] [rbp-158h] BYREF
  HSTRING *v65; // [rsp+B8h] [rbp-150h]
  unsigned __int64 v66; // [rsp+C0h] [rbp-148h]
  HSTRING newString; // [rsp+C8h] [rbp-140h] BYREF
  struct ConnectedStorage::SimpleHStringWrapper *v68[2]; // [rsp+D0h] [rbp-138h]
  __int64 v69; // [rsp+E0h] [rbp-128h]
  __int64 v70[3]; // [rsp+E8h] [rbp-120h] BYREF
  __int64 v71[3]; // [rsp+100h] [rbp-108h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+118h] [rbp-F0h] BYREF
  _BYTE v73[32]; // [rsp+128h] [rbp-E0h] BYREF
  _BYTE v74[48]; // [rsp+148h] [rbp-C0h] BYREF
  unsigned int v75[2]; // [rsp+178h] [rbp-90h]
  _DWORD v76[16]; // [rsp+180h] [rbp-88h] BYREF

  try
  {
    v66 = a4;
    v57 = (HSTRING)a7;
    v65 = a9;
    v69 = (__int64)a10;
    *(_QWORD *)v75 = a12;
    v15 = 0;
    v56 = 0;
    v61 = 0;
    v64 = 0;
    v63 = 0;
    v62 = 0;
    v59 = 0;
    v58 = 0;
    v54 = 0;
    v55 = 0;
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock(
        (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
        (struct ConnectedStorage::Mutex *)&CriticalSection,
        v16);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v17);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v18 = qword_1800C0858;
    lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
    v68[0] = ConnectedStorage::CallerInfoWithResult::Get(
               (ConnectedStorage::StorageService *)((char *)this + 64),
               (__int64)a2,
               a3);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(string, a2);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v61);
    WindowsDeleteString(string[0]);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(string, (HSTRING)a3);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v64);
    WindowsDeleteString(string[0]);
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v59);
    v20 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v62);
    v21 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v63);
    ConnectedStorage::Service::GetUserInfoFromUserContextToken(v18, v66, 1, v21, v20, AddressOf, &v54);
    v22 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, a5);
    ConnectedStorage::NormalizeScid(string, v22);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v58);
    WindowsDeleteString(string[0]);
    string[0] = 0;
    WindowsDeleteString(newString);
    if ( (ConnectedStorageEnableBits & 8) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v61, 0);
      v26 = (unsigned int)WindowsGetStringRawBuffer(v59, 0);
      v27 = (unsigned int)WindowsGetStringRawBuffer(v58, 0);
      McTemplateU0zzz_EventWriteTransfer(
        v28,
        (unsigned int)ConnectedStorageServiceUpdateStart,
        v27,
        v26,
        (__int64)StringRawBuffer);
    }
    v29 = 0;
    v30 = a6;
    v31 = v57;
    if ( a6 )
    {
      do
      {
        v15 += *((_DWORD *)v57 + 4 * v29 + 2);
        v56 = v15;
        ++v29;
      }
      while ( v29 < a6 );
      if ( v15 > 0x1000000 )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80830005LL, (int)L"StorageService::Update", v24);
    }
    v32 = 0;
    v33 = a8;
    while ( (unsigned int)v32 < a8 )
    {
      for ( i = 0; i < a6; ++i )
      {
        LODWORD(string[0]) = -1;
        v35 = WindowsCompareStringOrdinal(v65[v32], *((HSTRING *)v31 + 2 * i), (INT32 *)string);
        if ( v35 < 0 )
          ConnectedStorage::ReportErrorAndThrow(
            (ConnectedStorage *)(unsigned int)v35,
            (int)L"WindowsCompareStringOrdinal(deletes[i], updates[j].Name, &result)",
            v24);
        if ( !LODWORD(string[0]) )
          ConnectedStorage::ReportErrorAndThrow(
            (ConnectedStorage *)0x8000FFFFLL,
            (int)L"ConnectedStorageService::EnsureNamesOnlyAppearInUpdateOrDelete",
            v24);
        v31 = v57;
      }
      v32 = (unsigned int)(v32 + 1);
    }
    std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(
      v71,
      v23,
      v24,
      v31);
    std::vector<ConnectedStorage::UpdateDesc>::reserve(v71, a6);
    for ( j = 0; j < a6; ++j )
    {
      v40 = std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(string);
      ConnectedStorage::UpdateDesc::UpdateDesc(v73, *((_QWORD *)v57 + 2 * j), *((unsigned int *)v57 + 4 * j + 2), v40);
      std::vector<ConnectedStorage::UpdateDesc>::push_back(v71, v73);
      ConnectedStorage::UpdateDesc::~UpdateDesc((ConnectedStorage::UpdateDesc *)v73);
    }
    std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(
      v70,
      v36,
      v37,
      v38);
    std::vector<ConnectedStorage::SimpleHStringWrapper>::reserve(v70, a8);
    for ( k = 0; (unsigned int)k < a8; k = (unsigned int)(k + 1) )
    {
      v42 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v57, v65[k]);
      std::vector<ConnectedStorage::SimpleHStringWrapper>::push_back(v70, v42);
      WindowsDeleteString(v57);
      v57 = 0;
    }
    ConnectedStorage::ContextDesc::ContextDesc(
      (ConnectedStorage::ContextDesc *)v74,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v63,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v62,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v59,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v58,
      v68[0],
      *((_DWORD *)v68[0] + 6),
      v54);
    *(_OWORD *)v68 = **(_OWORD **)v75;
    ConnectedStorage::Service::Update(
      v18,
      (struct ConnectedStorage::ContextDesc *)v74,
      (__int64)&v61,
      (__int64)&v64,
      (__int64)v71,
      (__int64)v70,
      v69,
      v15,
      (__int64)a11);
    ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v74);
    std::vector<ConnectedStorage::SimpleHStringWrapper>::~vector<ConnectedStorage::SimpleHStringWrapper>(v70);
    std::vector<ConnectedStorage::UpdateDesc>::~vector<ConnectedStorage::UpdateDesc>(v71);
    if ( v18 )
      ConnectedStorage::Service::ReturnInstance();
  }
  catch ( ConnectedStorage::ComError v76 )
  {
    v55 = v76[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v76);
    v33 = a8;
    v30 = a6;
    LOBYTE(v15) = v56;
  }
  catch ( std::bad_alloc )
  {
    v55 = -2147024882;
    v33 = a8;
    v30 = a6;
    LOBYTE(v15) = v56;
  }
  catch ( ... )
  {
    v55 = -2147467259;
    v33 = a8;
    v30 = a6;
    LOBYTE(v15) = v56;
  }
  v43 = (unsigned int)WindowsGetStringRawBuffer(v61, 0);
  v44 = v54;
  v45 = WindowsGetStringRawBuffer(v59, 0);
  v46 = (ConnectedStorage *)WindowsGetStringRawBuffer(v58, 0);
  LODWORD(v52) = v55;
  LOBYTE(v47) = v44;
  ConnectedStorage::EventWriteUpdate(v46, v45, v47, v15, v30, v33, v43, v52, v75[0], v53);
  if ( (ConnectedStorageEnableBits & 8) != 0 )
    McTemplateU0d_EventWriteTransfer(v49, ConnectedStorageServiceUpdateStop, v55);
  v50 = ConnectedStorage::FilterHresult((ConnectedStorage *)v55, v48);
  WindowsDeleteString(v58);
  v58 = 0;
  WindowsDeleteString(v59);
  v59 = 0;
  WindowsDeleteString(v62);
  v62 = 0;
  WindowsDeleteString(v63);
  v63 = 0;
  WindowsDeleteString(v64);
  v64 = 0;
  WindowsDeleteString(v61);
  return v50;
}

```

## disassembly

```asm
0x180025610  mov     r11, rsp
0x180025613  push    rbx
0x180025614  push    rsi
0x180025615  push    rdi
0x180025616  push    r12
0x180025618  push    r13
0x18002561a  push    r15
0x18002561c  sub     rsp, 1D8h
0x180025623  mov     rax, cs:__security_cookie
0x18002562a  xor     rax, rsp
0x18002562d  mov     [rsp+208h+var_48], rax
0x180025635  mov     [rsp+208h+var_148], r9
0x18002563d  mov     r15, r8
0x180025640  mov     rsi, rdx
0x180025643  mov     rdi, rcx
0x180025646  mov     r12, [rsp+208h+arg_20]
0x18002564e  mov     rax, [rsp+208h+arg_30]
0x180025656  mov     [rsp+208h+var_198], rax
0x18002565b  mov     rax, [rsp+208h+arg_40]
0x180025663  mov     [rsp+208h+var_150], rax
0x18002566b  mov     rax, [rsp+208h+arg_48]
0x180025673  mov     [rsp+208h+var_128], rax
0x18002567b  mov     rax, [rsp+208h+arg_58]
0x180025683  mov     qword ptr [rsp+208h+var_90], rax
0x18002568b  xor     r13d, r13d
0x18002568e  mov     [rsp+208h+var_1A0], r13d
0x180025693  mov     [r11-170h], r13
0x18002569a  mov     [r11-158h], r13
0x1800256a1  mov     [r11-160h], r13
0x1800256a8  mov     [r11-168h], r13
0x1800256af  mov     [r11-188h], r13
0x1800256b6  mov     [rsp+208h+var_190], r13
0x1800256bb  mov     byte ptr [rsp+208h+var_1A8], r13b
0x1800256c0  mov     dword ptr [rsp+208h+var_1A8+4], r13d
0x1800256c5  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, r13b; bool ConnectedStorage::gShutdown
0x1800256cc  jnz     short loc_180025735
0x1800256ce  or      edx, 0FFFFFFFFh; unsigned int
0x1800256d1  lea     rcx, qword_1800C0998; this
0x1800256d8  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x1800256dd  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x1800256e4  lea     rcx, [rsp+208h+lpCriticalSection]; this
0x1800256ec  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800256f1  nop
0x1800256f2  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x1800256f8  test    eax, eax
0x1800256fa  jnz     short loc_18002570D
0x1800256fc  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x180025703  mov     ecx, 80004005h; this
0x180025708  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002570d  inc     eax
0x18002570f  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180025715  mov     edx, 2
0x18002571a  mov     rcx, cs:qword_1800C0858
0x180025721  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x180025726  nop
0x180025727  mov     rcx, [rsp+208h+lpCriticalSection]; lpCriticalSection
0x18002572f  call    cs:__imp_LeaveCriticalSection
0x180025735  mov     rbx, cs:qword_1800C0858
0x18002573c  mov     [rsp+208h+lpCriticalSection], rbx
0x180025744  lea     rcx, [rdi+40h]; this
0x180025748  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x18002574d  mov     [rsp+208h+var_138], rax
0x180025755  mov     rdx, rsi; string
0x180025758  lea     rcx, [rsp+208h+string]; newString
0x180025760  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180025765  nop
0x180025766  mov     rdx, rax
0x180025769  lea     rcx, [rsp+208h+var_170]; newString
0x180025771  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180025776  nop
0x180025777  mov     rcx, [rsp+208h+string]; string
0x18002577f  call    cs:__imp_WindowsDeleteString
0x180025785  mov     rdx, r15; string
0x180025788  lea     rcx, [rsp+208h+string]; newString
0x180025790  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180025795  nop
0x180025796  mov     rdx, rax
0x180025799  lea     rcx, [rsp+208h+var_158]; newString
0x1800257a1  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x1800257a6  nop
0x1800257a7  mov     rcx, [rsp+208h+string]; string
0x1800257af  call    cs:__imp_WindowsDeleteString
0x1800257b5  lea     rcx, [rsp+208h+var_188]; this
0x1800257bd  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x1800257c2  mov     rsi, rax
0x1800257c5  lea     rcx, [rsp+208h+var_168]; this
0x1800257cd  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x1800257d2  mov     rdi, rax
0x1800257d5  lea     rcx, [rsp+208h+var_160]; this
0x1800257dd  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x1800257e2  lea     rcx, [rsp+208h+var_1A8]
0x1800257e7  mov     [rsp+208h+var_1D8], rcx; bool *
0x1800257ec  mov     [rsp+208h+var_1E0], rsi; HSTRING *
0x1800257f1  mov     [rsp+208h+var_1E8], rdi; HSTRING *
0x1800257f6  mov     r9, rax; HSTRING *
0x1800257f9  mov     r8b, 1; bool
0x1800257fc  mov     rdx, [rsp+208h+var_148]; unsigned __int64
0x180025804  mov     rcx, rbx; this
0x180025807  call    ?GetUserInfoFromUserContextToken@Service@ConnectedStorage@@QEAAX_K_NPEAPEAUHSTRING__@@22PEA_N@Z; ConnectedStorage::Service::GetUserInfoFromUserContextToken(unsigned __int64,bool,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,bool *)
0x18002580c  mov     rdx, r12; string
0x18002580f  lea     rcx, [rsp+208h+newString]; newString
0x180025817  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x18002581c  nop
0x18002581d  mov     rdx, rax
0x180025820  lea     rcx, [rsp+208h+string]
0x180025828  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x18002582d  nop
0x18002582e  mov     rdx, rax
0x180025831  lea     rcx, [rsp+208h+var_190]; newString
0x180025836  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18002583b  nop
0x18002583c  mov     rcx, [rsp+208h+string]; string
0x180025844  call    cs:__imp_WindowsDeleteString
0x18002584a  mov     [rsp+208h+string], 0
0x180025856  mov     rcx, [rsp+208h+newString]; string
0x18002585e  call    cs:__imp_WindowsDeleteString
0x180025864  test    cs:ConnectedStorageEnableBits, 8
0x18002586b  jz      short loc_1800258B7
0x18002586d  xor     edx, edx; length
0x18002586f  mov     rcx, [rsp+208h+var_170]; string
0x180025877  call    cs:__imp_WindowsGetStringRawBuffer
0x18002587d  mov     rsi, rax
0x180025880  xor     edx, edx; length
0x180025882  mov     rcx, [rsp+208h+var_188]; string
0x18002588a  call    cs:__imp_WindowsGetStringRawBuffer
0x180025890  mov     rdi, rax
0x180025893  xor     edx, edx; length
0x180025895  mov     rcx, [rsp+208h+var_190]; string
0x18002589a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800258a0  mov     [rsp+208h+var_1E8], rsi
0x1800258a5  mov     r9, rdi
0x1800258a8  mov     r8, rax
0x1800258ab  lea     rdx, ConnectedStorageServiceUpdateStart
0x1800258b2  call    McTemplateU0zzz_EventWriteTransfer
0x1800258b7  xor     ecx, ecx
0x1800258b9  mov     r15d, [rsp+208h+arg_28]
0x1800258c1  mov     r9, [rsp+208h+var_198]
0x1800258c6  test    r15d, r15d
0x1800258c9  jz      short loc_1800258FC
0x1800258cb  mov     eax, ecx
0x1800258cd  shl     rax, 4
0x1800258d1  add     r13d, [rax+r9+8]
0x1800258d6  mov     [rsp+208h+var_1A0], r13d
0x1800258db  inc     ecx
0x1800258dd  cmp     ecx, r15d
0x1800258e0  jb      short loc_1800258CB
0x1800258e2  cmp     r13d, 1000000h
0x1800258e9  jbe     short loc_1800258FC
0x1800258eb  lea     rdx, aStorageservice; "StorageService::Update"
0x1800258f2  mov     ecx, 80830005h; this
0x1800258f7  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x1800258fc  xor     esi, esi
0x1800258fe  mov     r12d, [rsp+208h+arg_38]
0x180025906  cmp     esi, r12d
0x180025909  jnb     short loc_18002597A
0x18002590b  xor     edi, edi
0x18002590d  cmp     edi, r15d
0x180025910  jnb     short loc_180025976
0x180025912  mov     dword ptr [rsp+208h+string], 0FFFFFFFFh
0x18002591d  mov     edx, edi
0x18002591f  add     rdx, rdx
0x180025922  lea     r8, [rsp+208h+string]; result
0x18002592a  mov     rdx, [r9+rdx*8]; string2
0x18002592e  mov     rax, [rsp+208h+var_150]
0x180025936  mov     rcx, [rax+rsi*8]; string1
0x18002593a  call    cs:__imp_WindowsCompareStringOrdinal
0x180025940  test    eax, eax
0x180025942  jns     short loc_180025952
0x180025944  lea     rdx, aWindowscompare; "WindowsCompareStringOrdinal(deletes[i],"...
0x18002594b  mov     ecx, eax; this
0x18002594d  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180025952  cmp     dword ptr [rsp+208h+string], 0
0x18002595a  jnz     short loc_18002596D
0x18002595c  lea     rdx, aConnectedstora_2; "ConnectedStorageService::EnsureNamesOnl"...
0x180025963  mov     ecx, 8000FFFFh; this
0x180025968  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002596d  inc     edi
0x18002596f  mov     r9, [rsp+208h+var_198]
0x180025974  jmp     short loc_18002590D
0x180025976  inc     esi
0x180025978  jmp     short loc_180025906
0x18002597a  lea     rcx, [rsp+208h+var_108]
0x180025982  call    ??0?$vector@UEntry@MultiFileWrite@ConnectedStorage@@V?$allocator@UEntry@MultiFileWrite@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(void)
0x180025987  nop
0x180025988  mov     rdx, r15
0x18002598b  lea     rcx, [rsp+208h+var_108]
0x180025993  call    ?reserve@?$vector@UUpdateDesc@ConnectedStorage@@V?$allocator@UUpdateDesc@ConnectedStorage@@@std@@@std@@QEAAX_K@Z; std::vector<ConnectedStorage::UpdateDesc>::reserve(unsigned __int64)
0x180025998  xor     edi, edi
0x18002599a  cmp     edi, r15d
0x18002599d  jnb     short loc_1800259F7
0x18002599f  lea     rcx, [rsp+208h+string]
0x1800259a7  call    ??0?$weak_ptr@VAtomManager@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(void)
0x1800259ac  mov     edx, edi
0x1800259ae  add     rdx, rdx
0x1800259b1  mov     r9, rax
0x1800259b4  mov     rax, [rsp+208h+var_198]
0x1800259b9  mov     r8d, [rax+rdx*8+8]
0x1800259be  mov     rdx, [rax+rdx*8]
0x1800259c2  lea     rcx, [rsp+208h+var_E0]
0x1800259ca  call    ??0UpdateDesc@ConnectedStorage@@QEAA@PEAUHSTRING__@@IV?$shared_ptr@VCountedBytes@ConnectedStorage@@@std@@@Z; ConnectedStorage::UpdateDesc::UpdateDesc(HSTRING__ *,uint,std::shared_ptr<ConnectedStorage::CountedBytes>)
0x1800259cf  nop
0x1800259d0  lea     rdx, [rsp+208h+var_E0]
0x1800259d8  lea     rcx, [rsp+208h+var_108]
0x1800259e0  call    ?push_back@?$vector@UUpdateDesc@ConnectedStorage@@V?$allocator@UUpdateDesc@ConnectedStorage@@@std@@@std@@QEAAXAEBUUpdateDesc@ConnectedStorage@@@Z; std::vector<ConnectedStorage::UpdateDesc>::push_back(ConnectedStorage::UpdateDesc const &)
0x1800259e5  nop
0x1800259e6  lea     rcx, [rsp+208h+var_E0]; this
0x1800259ee  call    ??1UpdateDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::UpdateDesc::~UpdateDesc(void)
0x1800259f3  inc     edi
0x1800259f5  jmp     short loc_18002599A
0x1800259f7  lea     rcx, [rsp+208h+var_120]
0x1800259ff  call    ??0?$vector@UEntry@MultiFileWrite@ConnectedStorage@@V?$allocator@UEntry@MultiFileWrite@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(void)
0x180025a04  nop
0x180025a05  mov     rdx, r12
0x180025a08  lea     rcx, [rsp+208h+var_120]
0x180025a10  call    ?reserve@?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@QEAAX_K@Z; std::vector<ConnectedStorage::SimpleHStringWrapper>::reserve(unsigned __int64)
0x180025a15  xor     edi, edi
0x180025a17  cmp     edi, r12d
0x180025a1a  jnb     short loc_180025A5C
0x180025a1c  mov     rax, [rsp+208h+var_150]
0x180025a24  mov     rdx, [rax+rdi*8]; string
0x180025a28  lea     rcx, [rsp+208h+var_198]; newString
0x180025a2d  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180025a32  nop
0x180025a33  mov     rdx, rax
0x180025a36  lea     rcx, [rsp+208h+var_120]
0x180025a3e  call    ?push_back@?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@QEAAX$$QEAVSimpleHStringWrapper@ConnectedStorage@@@Z; std::vector<ConnectedStorage::SimpleHStringWrapper>::push_back(ConnectedStorage::SimpleHStringWrapper &&)
0x180025a43  nop
0x180025a44  mov     rcx, [rsp+208h+var_198]; string
0x180025a49  call    cs:__imp_WindowsDeleteString
0x180025a4f  mov     [rsp+208h+var_198], 0
0x180025a58  inc     edi
0x180025a5a  jmp     short loc_180025A17
0x180025a5c  mov     al, byte ptr [rsp+208h+var_1A8]
0x180025a60  mov     byte ptr [rsp+208h+var_1D0], al; bool
0x180025a64  mov     rdi, [rsp+208h+var_138]
0x180025a6c  mov     eax, [rdi+18h]
0x180025a6f  mov     dword ptr [rsp+208h+var_1D8], eax; unsigned int
0x180025a73  mov     [rsp+208h+var_1E0], rdi; struct ConnectedStorage::SimpleHStringWrapper *
0x180025a78  lea     rax, [rsp+208h+var_190]
0x180025a7d  mov     [rsp+208h+var_1E8], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x180025a82  lea     r9, [rsp+208h+var_188]; struct ConnectedStorage::SimpleHStringWrapper *
0x180025a8a  lea     r8, [rsp+208h+var_168]; struct ConnectedStorage::SimpleHStringWrapper *
0x180025a92  lea     rdx, [rsp+208h+var_160]; struct ConnectedStorage::SimpleHStringWrapper *
0x180025a9a  lea     rcx, [rsp+208h+var_C0]; this
0x180025aa2  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x180025aa7  nop
0x180025aa8  mov     rax, qword ptr [rsp+208h+var_90]
0x180025ab0  movups  xmm0, xmmword ptr [rax]
0x180025ab3  movdqu  xmmword ptr [rsp+208h+var_138], xmm0
0x180025abc  mov     rax, [rsp+208h+arg_50]
0x180025ac4  mov     [rsp+208h+var_1B0], rax; __int64
0x180025ac9  mov     [rsp+208h+var_1B8], r13d; int
0x180025ace  mov     rax, [rsp+208h+var_128]
0x180025ad6  mov     [rsp+208h+var_1C0], rax; __int64
0x180025adb  lea     rax, [rsp+208h+var_120]
0x180025ae3  mov     qword ptr [rsp+208h+var_1C8], rax; __int64
0x180025ae8  lea     rax, [rsp+208h+var_108]
0x180025af0  mov     [rsp+208h+var_1D0], rax; __int64
0x180025af5  lea     rax, [rsp+208h+var_158]
0x180025afd  mov     [rsp+208h+var_1D8], rax; __int64
0x180025b02  lea     rax, [rsp+208h+var_170]
0x180025b0a  mov     [rsp+208h+var_1E0], rax; __int64
0x180025b0f  lea     rax, [rsp+208h+var_C0]
0x180025b17  mov     [rsp+208h+var_1E8], rax; struct ConnectedStorage::ContextDesc *
0x180025b1c  mov     r9, [rsp+208h+var_148]
0x180025b24  mov     r8, rdi
0x180025b27  lea     rdx, [rsp+208h+var_138]
0x180025b2f  mov     rcx, rbx; struct ConnectedStorage::Mutex *
0x180025b32  call    ?Update@Service@ConnectedStorage@@QEAAXU_GUID@@AEBVCallerInfo@2@_KAEBVContextDesc@2@AEBVSimpleHStringWrapper@2@4$$QEAV?$vector@UUpdateDesc@ConnectedStorage@@V?$allocator@UUpdateDesc@ConnectedStorage@@@std@@@std@@$$QEAV?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@8@PEAUISequentialStream@@IPEAUIStorageOperationHandler@@@Z; ConnectedStorage::Service::Update(_GUID,ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::vector<ConnectedStorage::UpdateDesc> &&,std::vector<ConnectedStorage::SimpleHStringWrapper> &&,ISequentialStream *,uint,IStorageOperationHandler *)
0x180025b37  nop
0x180025b38  lea     rcx, [rsp+208h+var_C0]; this
0x180025b40  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180025b45  nop
0x180025b46  lea     rcx, [rsp+208h+var_120]
0x180025b4e  call    ??1?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::SimpleHStringWrapper>::~vector<ConnectedStorage::SimpleHStringWrapper>(void)
0x180025b53  nop
0x180025b54  lea     rcx, [rsp+208h+var_108]
0x180025b5c  call    ??1?$vector@UUpdateDesc@ConnectedStorage@@V?$allocator@UUpdateDesc@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::UpdateDesc>::~vector<ConnectedStorage::UpdateDesc>(void)
0x180025b61  nop
0x180025b62  test    rbx, rbx
0x180025b65  jz      short loc_180025B6D
0x180025b67  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x180025b6c  nop
0x180025b6d  jmp     short loc_180025B88
0x180025b6f  jmp     short loc_180025B73
0x180025b71  jmp     short $+2
0x180025b73  mov     r12d, [rsp+208h+arg_38]
0x180025b7b  mov     r15d, [rsp+208h+arg_28]
0x180025b83  mov     r13d, [rsp+208h+var_1A0]
0x180025b88  xor     edx, edx; length
0x180025b8a  mov     rcx, [rsp+208h+var_170]; string
0x180025b92  call    cs:__imp_WindowsGetStringRawBuffer
0x180025b98  mov     rbx, rax
0x180025b9b  mov     sil, byte ptr [rsp+208h+var_1A8]
0x180025ba0  xor     edx, edx; length
0x180025ba2  mov     rcx, [rsp+208h+var_188]; string
0x180025baa  call    cs:__imp_WindowsGetStringRawBuffer
0x180025bb0  mov     rdi, rax
0x180025bb3  xor     edx, edx; length
0x180025bb5  mov     rcx, [rsp+208h+var_190]; string
  ... truncated ...
```
