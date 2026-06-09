# ConnectedStorage::StorageService::Read(HSTRING__ *,unsigned __int64,HSTRING__ *,uint,HSTRING__ * * const,IStorageReadHandler *,_GUID)

- ea: `0x180023e80`
- end: `0x1800242d4`
- name: `?Read@StorageService@ConnectedStorage@@MEAAJPEAUHSTRING__@@_K0IQEAPEAU3@PEAUIStorageReadHandler@@U_GUID@@@Z`
- size: `1108`
- prototype: `__int64 __fastcall(ConnectedStorage::StorageService *this, HSTRING, char *, HSTRING, unsigned int, HSTRING *const, struct IStorageReadHandler *, struct _GUID *)`
- caller_count: `0`
- callee_count: `24`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000ca18`
- `0x18000cb9c`
- `0x180011040`
- `0x180011bd0`
- `0x180012498`
- `0x1800125ec`
- `0x180012ed8`
- `0x180013e1c`
- `0x180014a88`
- `0x180015008`
- `0x180015d8c`
- `0x1800160c8`
- `0x1800170d4`
- `0x18001dd94`
- `0x180020e68`
- `0x180022dec`
- `0x1800235c0`
- `0x180023e80`
- `0x180026430`
- `0x180026504`
- `0x1800268dc`
- `0x18004ae14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023f73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023f73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023fb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024033`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800240f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002425b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002426f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800242ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023fb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024033`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800240f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002425b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002426f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800242ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002405d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002406d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002407d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800241d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800241e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800241f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002405d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002406d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002407d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800241d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800241e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800241f8`

## string_xrefs

- `0x180023f40`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall ConnectedStorage::StorageService::Read(
        ConnectedStorage::StorageService *this,
        HSTRING a2,
        char *a3,
        HSTRING a4,
        unsigned int a5,
        HSTRING *const a6,
        struct IStorageReadHandler *a7,
        struct _GUID *a8)
{
  char *v12; // r8
  const unsigned __int16 *v13; // r8
  ConnectedStorage::Service *v14; // rbx
  unsigned int *v15; // r15
  HSTRING *AddressOf; // rsi
  HSTRING *v17; // rdi
  HSTRING *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  PCWSTR StringRawBuffer; // rsi
  unsigned int v24; // edi
  unsigned int v25; // eax
  int v26; // ecx
  __int64 v27; // rdi
  __int64 v28; // rsi
  __int64 v29; // rax
  unsigned int v30; // edi
  bool v31; // si
  const unsigned __int16 *v32; // rbx
  ConnectedStorage *v33; // rax
  const unsigned __int16 *v34; // r8
  int v35; // edx
  __int64 v36; // rcx
  unsigned int v37; // ebx
  HSTRING *v39; // [rsp+28h] [rbp-150h]
  const struct _GUID *v40; // [rsp+38h] [rbp-140h]
  bool v41; // [rsp+40h] [rbp-138h] BYREF
  unsigned int v42; // [rsp+44h] [rbp-134h]
  HSTRING newString; // [rsp+48h] [rbp-130h] BYREF
  HSTRING v44; // [rsp+50h] [rbp-128h] BYREF
  HSTRING v45; // [rsp+58h] [rbp-120h] BYREF
  HSTRING v46; // [rsp+60h] [rbp-118h] BYREF
  HSTRING v47; // [rsp+68h] [rbp-110h] BYREF
  HSTRING v48; // [rsp+70h] [rbp-108h] BYREF
  HSTRING v49; // [rsp+78h] [rbp-100h] BYREF
  __int128 v50; // [rsp+80h] [rbp-F8h]
  __int64 v51[3]; // [rsp+90h] [rbp-E8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+A8h] [rbp-D0h] BYREF
  _BYTE v53[48]; // [rsp+B8h] [rbp-C0h] BYREF
  unsigned int v54[2]; // [rsp+E8h] [rbp-90h]
  _DWORD v55[16]; // [rsp+F0h] [rbp-88h] BYREF

  try
  {
    *(_QWORD *)&v50 = a6;
    *(_QWORD *)v54 = a8;
    v46 = 0;
    v48 = 0;
    v47 = 0;
    v45 = 0;
    v44 = 0;
    v41 = 0;
    v42 = 0;
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock(
        (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
        (struct ConnectedStorage::Mutex *)&CriticalSection,
        v12);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v13);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v14 = qword_1800C0858;
    lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
    v15 = (unsigned int *)ConnectedStorage::CallerInfoWithResult::Get(
                            (ConnectedStorage::StorageService *)((char *)this + 64),
                            (__int64)a2,
                            a3);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, a2);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v46);
    WindowsDeleteString(newString);
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v45);
    v17 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v47);
    v18 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v48);
    ConnectedStorage::Service::GetUserInfoFromUserContextToken(v14, (unsigned __int64)a3, 1, v18, v17, AddressOf, &v41);
    v19 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v49, a4);
    ConnectedStorage::NormalizeScid(&newString, v19);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v44);
    WindowsDeleteString(newString);
    newString = 0;
    WindowsDeleteString(v49);
    if ( (ConnectedStorageEnableBits & 8) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v46, 0);
      v24 = (unsigned int)WindowsGetStringRawBuffer(v45, 0);
      v25 = (unsigned int)WindowsGetStringRawBuffer(v44, 0);
      McTemplateU0zzz_EventWriteTransfer(
        v26,
        (unsigned int)ConnectedStorageServiceReadStart,
        v25,
        v24,
        (__int64)StringRawBuffer);
    }
    std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(
      v51,
      v20,
      v21,
      v22);
    std::vector<ConnectedStorage::SimpleHStringWrapper>::reserve(v51, a5);
    v27 = 0;
    v28 = v50;
    while ( (unsigned int)v27 < a5 )
    {
      v29 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, *(HSTRING *)(v28 + 8 * v27));
      std::vector<ConnectedStorage::SimpleHStringWrapper>::push_back(v51, v29);
      WindowsDeleteString(newString);
      newString = 0;
      v27 = (unsigned int)(v27 + 1);
    }
    ConnectedStorage::ContextDesc::ContextDesc(
      (ConnectedStorage::ContextDesc *)v53,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v48,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v47,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v45,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v44,
      (const struct ConnectedStorage::SimpleHStringWrapper *)v15,
      v15[6],
      v41);
    v50 = **(_OWORD **)v54;
    ConnectedStorage::Service::Read(
      v14,
      (struct ConnectedStorage::ContextDesc *)v53,
      (struct ConnectedStorage::SimpleHStringWrapper *)&v46,
      (__int64)v51,
      (HSTRING)a7);
    ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v53);
    std::vector<ConnectedStorage::SimpleHStringWrapper>::~vector<ConnectedStorage::SimpleHStringWrapper>(v51);
    if ( v14 )
      ConnectedStorage::Service::ReturnInstance();
  }
  catch ( ConnectedStorage::ComError v55 )
  {
    v42 = v55[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v55);
  }
  catch ( std::bad_alloc )
  {
    v42 = -2147024882;
  }
  catch ( ... )
  {
    v42 = -2147467259;
  }
  v30 = (unsigned int)WindowsGetStringRawBuffer(v46, 0);
  v31 = v41;
  v32 = WindowsGetStringRawBuffer(v45, 0);
  v33 = (ConnectedStorage *)WindowsGetStringRawBuffer(v44, 0);
  LODWORD(v39) = v42;
  LOBYTE(v34) = v31;
  ConnectedStorage::EventWriteRead(v33, v32, v34, a5, v30, (const unsigned __int16 *const)v39, v54[0], v40);
  if ( (ConnectedStorageEnableBits & 8) != 0 )
    McTemplateU0d_EventWriteTransfer(v36, ConnectedStorageServiceReadStop, v42);
  v37 = ConnectedStorage::FilterHresult((ConnectedStorage *)v42, v35);
  WindowsDeleteString(v44);
  v44 = 0;
  WindowsDeleteString(v45);
  v45 = 0;
  WindowsDeleteString(v47);
  v47 = 0;
  WindowsDeleteString(v48);
  v48 = 0;
  WindowsDeleteString(v46);
  return v37;
}

```

## disassembly

```asm
0x180023e80  push    rbx
0x180023e82  push    rsi
0x180023e83  push    rdi
0x180023e84  push    r12
0x180023e86  push    r13
0x180023e88  push    r15
0x180023e8a  sub     rsp, 148h
0x180023e91  mov     rax, cs:__security_cookie
0x180023e98  xor     rax, rsp
0x180023e9b  mov     [rsp+178h+var_48], rax
0x180023ea3  mov     r12, r9
0x180023ea6  mov     r13, r8
0x180023ea9  mov     rsi, rdx
0x180023eac  mov     rdi, rcx
0x180023eaf  mov     rax, [rsp+178h+arg_28]
0x180023eb7  mov     qword ptr [rsp+178h+var_F8], rax
0x180023ebf  mov     rax, [rsp+178h+arg_38]
0x180023ec7  mov     qword ptr [rsp+178h+var_90], rax
0x180023ecf  mov     [rsp+178h+var_118], 0
0x180023ed8  mov     [rsp+178h+var_108], 0
0x180023ee1  mov     [rsp+178h+var_110], 0
0x180023eea  mov     [rsp+178h+var_120], 0
0x180023ef3  mov     [rsp+178h+var_128], 0
0x180023efc  mov     byte ptr [rsp+178h+var_138], 0
0x180023f01  mov     dword ptr [rsp+178h+var_138+4], 0
0x180023f09  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x180023f10  jnz     short loc_180023F79
0x180023f12  or      edx, 0FFFFFFFFh; unsigned int
0x180023f15  lea     rcx, qword_1800C0998; this
0x180023f1c  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x180023f21  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x180023f28  lea     rcx, [rsp+178h+lpCriticalSection]; this
0x180023f30  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180023f35  nop
0x180023f36  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x180023f3c  test    eax, eax
0x180023f3e  jnz     short loc_180023F51
0x180023f40  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x180023f47  mov     ecx, 80004005h; this
0x180023f4c  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180023f51  inc     eax
0x180023f53  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180023f59  mov     edx, 2
0x180023f5e  mov     rcx, cs:qword_1800C0858
0x180023f65  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x180023f6a  nop
0x180023f6b  mov     rcx, [rsp+178h+lpCriticalSection]; lpCriticalSection
0x180023f73  call    cs:__imp_LeaveCriticalSection
0x180023f79  mov     rbx, cs:qword_1800C0858
0x180023f80  mov     [rsp+178h+lpCriticalSection], rbx
0x180023f88  lea     rcx, [rdi+40h]; this
0x180023f8c  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x180023f91  mov     r15, rax
0x180023f94  mov     rdx, rsi; string
0x180023f97  lea     rcx, [rsp+178h+newString]; newString
0x180023f9c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180023fa1  nop
0x180023fa2  mov     rdx, rax
0x180023fa5  lea     rcx, [rsp+178h+var_118]; newString
0x180023faa  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180023faf  nop
0x180023fb0  mov     rcx, [rsp+178h+newString]; string
0x180023fb5  call    cs:__imp_WindowsDeleteString
0x180023fbb  lea     rcx, [rsp+178h+var_120]; this
0x180023fc0  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180023fc5  mov     rsi, rax
0x180023fc8  lea     rcx, [rsp+178h+var_110]; this
0x180023fcd  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180023fd2  mov     rdi, rax
0x180023fd5  lea     rcx, [rsp+178h+var_108]; this
0x180023fda  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180023fdf  lea     rcx, [rsp+178h+var_138]
0x180023fe4  mov     [rsp+178h+var_148], rcx; bool *
0x180023fe9  mov     [rsp+178h+var_150], rsi; HSTRING *
0x180023fee  mov     [rsp+178h+var_158], rdi; HSTRING *
0x180023ff3  mov     r9, rax; HSTRING *
0x180023ff6  mov     r8b, 1; bool
0x180023ff9  mov     rdx, r13; unsigned __int64
0x180023ffc  mov     rcx, rbx; this
0x180023fff  call    ?GetUserInfoFromUserContextToken@Service@ConnectedStorage@@QEAAX_K_NPEAPEAUHSTRING__@@22PEA_N@Z; ConnectedStorage::Service::GetUserInfoFromUserContextToken(unsigned __int64,bool,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,bool *)
0x180024004  mov     rdx, r12; string
0x180024007  lea     rcx, [rsp+178h+var_100]; newString
0x18002400c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180024011  nop
0x180024012  mov     rdx, rax
0x180024015  lea     rcx, [rsp+178h+newString]
0x18002401a  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x18002401f  nop
0x180024020  mov     rdx, rax
0x180024023  lea     rcx, [rsp+178h+var_128]; newString
0x180024028  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18002402d  nop
0x18002402e  mov     rcx, [rsp+178h+newString]; string
0x180024033  call    cs:__imp_WindowsDeleteString
0x180024039  mov     [rsp+178h+newString], 0
0x180024042  mov     rcx, [rsp+178h+var_100]; string
0x180024047  call    cs:__imp_WindowsDeleteString
0x18002404d  test    cs:ConnectedStorageEnableBits, 8
0x180024054  jz      short loc_18002409A
0x180024056  xor     edx, edx; length
0x180024058  mov     rcx, [rsp+178h+var_118]; string
0x18002405d  call    cs:__imp_WindowsGetStringRawBuffer
0x180024063  mov     rsi, rax
0x180024066  xor     edx, edx; length
0x180024068  mov     rcx, [rsp+178h+var_120]; string
0x18002406d  call    cs:__imp_WindowsGetStringRawBuffer
0x180024073  mov     rdi, rax
0x180024076  xor     edx, edx; length
0x180024078  mov     rcx, [rsp+178h+var_128]; string
0x18002407d  call    cs:__imp_WindowsGetStringRawBuffer
0x180024083  mov     [rsp+178h+var_158], rsi
0x180024088  mov     r9, rdi
0x18002408b  mov     r8, rax
0x18002408e  lea     rdx, ConnectedStorageServiceReadStart
0x180024095  call    McTemplateU0zzz_EventWriteTransfer
0x18002409a  lea     rcx, [rsp+178h+var_E8]
0x1800240a2  call    ??0?$vector@UEntry@MultiFileWrite@ConnectedStorage@@V?$allocator@UEntry@MultiFileWrite@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::MultiFileWrite::Entry>::vector<ConnectedStorage::MultiFileWrite::Entry>(void)
0x1800240a7  nop
0x1800240a8  mov     edx, dword ptr [rsp+178h+arg_20]
0x1800240af  lea     rcx, [rsp+178h+var_E8]
0x1800240b7  call    ?reserve@?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@QEAAX_K@Z; std::vector<ConnectedStorage::SimpleHStringWrapper>::reserve(unsigned __int64)
0x1800240bc  xor     edi, edi
0x1800240be  mov     rsi, qword ptr [rsp+178h+var_F8]
0x1800240c6  cmp     edi, dword ptr [rsp+178h+arg_20]
0x1800240cd  jnb     short loc_180024107
0x1800240cf  mov     rdx, [rsi+rdi*8]; string
0x1800240d3  lea     rcx, [rsp+178h+newString]; newString
0x1800240d8  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x1800240dd  nop
0x1800240de  mov     rdx, rax
0x1800240e1  lea     rcx, [rsp+178h+var_E8]
0x1800240e9  call    ?push_back@?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@QEAAX$$QEAVSimpleHStringWrapper@ConnectedStorage@@@Z; std::vector<ConnectedStorage::SimpleHStringWrapper>::push_back(ConnectedStorage::SimpleHStringWrapper &&)
0x1800240ee  nop
0x1800240ef  mov     rcx, [rsp+178h+newString]; string
0x1800240f4  call    cs:__imp_WindowsDeleteString
0x1800240fa  mov     [rsp+178h+newString], 0
0x180024103  inc     edi
0x180024105  jmp     short loc_1800240C6
0x180024107  mov     al, byte ptr [rsp+178h+var_138]
0x18002410b  mov     byte ptr [rsp+178h+var_140], al; bool
0x18002410f  mov     eax, [r15+18h]
0x180024113  mov     dword ptr [rsp+178h+var_148], eax; unsigned int
0x180024117  mov     [rsp+178h+var_150], r15; struct ConnectedStorage::SimpleHStringWrapper *
0x18002411c  lea     rax, [rsp+178h+var_128]
0x180024121  mov     [rsp+178h+var_158], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x180024126  lea     r9, [rsp+178h+var_120]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002412b  lea     r8, [rsp+178h+var_110]; struct ConnectedStorage::SimpleHStringWrapper *
0x180024130  lea     rdx, [rsp+178h+var_108]; struct ConnectedStorage::SimpleHStringWrapper *
0x180024135  lea     rcx, [rsp+178h+var_C0]; this
0x18002413d  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x180024142  nop
0x180024143  mov     rax, qword ptr [rsp+178h+var_90]
0x18002414b  movups  xmm0, xmmword ptr [rax]
0x18002414e  movdqu  [rsp+178h+var_F8], xmm0
0x180024157  mov     rax, [rsp+178h+arg_30]
0x18002415f  mov     [rsp+178h+var_140], rax; struct _GUID *
0x180024164  lea     rax, [rsp+178h+var_E8]
0x18002416c  mov     [rsp+178h+var_148], rax; __int64
0x180024171  lea     rax, [rsp+178h+var_118]
0x180024176  mov     [rsp+178h+var_150], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x18002417b  lea     rax, [rsp+178h+var_C0]
0x180024183  mov     [rsp+178h+var_158], rax; struct ConnectedStorage::ContextDesc *
0x180024188  mov     r9, r13
0x18002418b  mov     r8, r15
0x18002418e  lea     rdx, [rsp+178h+var_F8]
0x180024196  mov     rcx, rbx; struct ConnectedStorage::Mutex *
0x180024199  call    ?Read@Service@ConnectedStorage@@QEAAXU_GUID@@AEBVCallerInfo@2@_KAEBVContextDesc@2@AEBVSimpleHStringWrapper@2@$$QEAV?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@PEAUIStorageReadHandler@@@Z; ConnectedStorage::Service::Read(_GUID,ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &,std::vector<ConnectedStorage::SimpleHStringWrapper> &&,IStorageReadHandler *)
0x18002419e  nop
0x18002419f  lea     rcx, [rsp+178h+var_C0]; this
0x1800241a7  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x1800241ac  nop
0x1800241ad  lea     rcx, [rsp+178h+var_E8]
0x1800241b5  call    ??1?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::SimpleHStringWrapper>::~vector<ConnectedStorage::SimpleHStringWrapper>(void)
0x1800241ba  nop
0x1800241bb  test    rbx, rbx
0x1800241be  jz      short loc_1800241C6
0x1800241c0  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x1800241c5  nop
0x1800241c6  jmp     short loc_1800241CC
0x1800241c8  jmp     short loc_1800241CC
0x1800241ca  jmp     short $+2
0x1800241cc  xor     edx, edx; length
0x1800241ce  mov     rcx, [rsp+178h+var_118]; string
0x1800241d3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800241d9  mov     rdi, rax
0x1800241dc  mov     sil, byte ptr [rsp+178h+var_138]
0x1800241e1  xor     edx, edx; length
0x1800241e3  mov     rcx, [rsp+178h+var_120]; string
0x1800241e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800241ee  mov     rbx, rax
0x1800241f1  xor     edx, edx; length
0x1800241f3  mov     rcx, [rsp+178h+var_128]; string
0x1800241f8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800241fe  mov     rcx, qword ptr [rsp+178h+var_90]
0x180024206  mov     [rsp+178h+var_148], rcx; unsigned int
0x18002420b  mov     ecx, dword ptr [rsp+178h+var_138+4]
0x18002420f  mov     dword ptr [rsp+178h+var_150], ecx; unsigned __int16 *
0x180024213  mov     [rsp+178h+var_158], rdi; unsigned int
0x180024218  mov     r9d, dword ptr [rsp+178h+arg_20]; bool
0x180024220  mov     r8b, sil; unsigned __int16 *
0x180024223  mov     rdx, rbx; unsigned __int16 *
0x180024226  mov     rcx, rax; this
0x180024229  call    ?EventWriteRead@ConnectedStorage@@YAXQEBG0_NI0IQEBU_GUID@@@Z; ConnectedStorage::EventWriteRead(ushort const * const,ushort const * const,bool,uint,ushort const * const,uint,_GUID const * const)
0x18002422e  nop
0x18002422f  jmp     short $+2
0x180024231  test    cs:ConnectedStorageEnableBits, 8
0x180024238  jz      short loc_18002424B
0x18002423a  mov     r8d, dword ptr [rsp+178h+var_138+4]
0x18002423f  lea     rdx, ConnectedStorageServiceReadStop
0x180024246  call    McTemplateU0d_EventWriteTransfer
0x18002424b  mov     ecx, dword ptr [rsp+178h+var_138+4]; this
0x18002424f  call    ?FilterHresult@ConnectedStorage@@YAJJ@Z; ConnectedStorage::FilterHresult(long)
0x180024254  mov     ebx, eax
0x180024256  mov     rcx, [rsp+178h+var_128]; string
0x18002425b  call    cs:__imp_WindowsDeleteString
0x180024261  mov     [rsp+178h+var_128], 0
0x18002426a  mov     rcx, [rsp+178h+var_120]; string
0x18002426f  call    cs:__imp_WindowsDeleteString
0x180024275  mov     [rsp+178h+var_120], 0
0x18002427e  mov     rcx, [rsp+178h+var_110]; string
0x180024283  call    cs:__imp_WindowsDeleteString
0x180024289  mov     [rsp+178h+var_110], 0
0x180024292  mov     rcx, [rsp+178h+var_108]; string
0x180024297  call    cs:__imp_WindowsDeleteString
0x18002429d  mov     [rsp+178h+var_108], 0
0x1800242a6  mov     rcx, [rsp+178h+var_118]; string
0x1800242ab  call    cs:__imp_WindowsDeleteString
0x1800242b1  mov     eax, ebx
0x1800242b3  mov     rcx, [rsp+178h+var_48]
0x1800242bb  xor     rcx, rsp; StackCookie
0x1800242be  call    __security_check_cookie
0x1800242c3  add     rsp, 148h
0x1800242ca  pop     r15
0x1800242cc  pop     r13
0x1800242ce  pop     r12
0x1800242d0  pop     rdi
0x1800242d1  pop     rsi
0x1800242d2  pop     rbx
0x1800242d3  retn
```
