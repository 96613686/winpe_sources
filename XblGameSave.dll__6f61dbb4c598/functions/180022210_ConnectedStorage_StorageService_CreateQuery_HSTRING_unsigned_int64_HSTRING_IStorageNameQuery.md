# ConnectedStorage::StorageService::CreateQuery(HSTRING__ *,unsigned __int64,HSTRING__ *,IStorageNameQuery * *)

- ea: `0x180022210`
- end: `0x18002262a`
- name: `?CreateQuery@StorageService@ConnectedStorage@@MEAAJPEAUHSTRING__@@_K0PEAPEAUIStorageNameQuery@@@Z`
- size: `1050`
- prototype: `int(ConnectedStorage::StorageService *__hidden this, HSTRING, unsigned __int64, HSTRING, struct IStorageNameQuery **)`
- caller_count: `0`
- callee_count: `25`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x180004760`
- `0x180007bd0`
- `0x18000a040`
- `0x18000aae4`
- `0x18000ca18`
- `0x18000cb9c`
- `0x180011bd0`
- `0x1800125ec`
- `0x180012bd4`
- `0x180012ed8`
- `0x180013e1c`
- `0x180014198`
- `0x180014a88`
- `0x180015008`
- `0x1800160c8`
- `0x1800170d4`
- `0x18001d58c`
- `0x180020e68`
- `0x180022210`
- `0x180022dec`
- `0x1800235c0`
- `0x1800268dc`
- `0x18004ae14`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800222e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800222e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800223b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800223c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800223b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800223c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800223d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800223e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800223f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002253d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002254d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800223d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800223e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800223f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002253d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002254d`

## string_xrefs

- `0x1800222b3`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall ConnectedStorage::StorageService::CreateQuery(
        ConnectedStorage::StorageService *this,
        HSTRING a2,
        char *a3,
        HSTRING a4,
        struct IStorageNameQuery **a5)
{
  unsigned int v7; // r15d
  char *v8; // r8
  const unsigned __int16 *v9; // r8
  ConnectedStorage::Service *v10; // rdi
  unsigned int *v11; // r13
  HSTRING *AddressOf; // rsi
  HSTRING *v13; // rbx
  HSTRING *v14; // rax
  char *v15; // r8
  __int64 v16; // rax
  PCWSTR StringRawBuffer; // rsi
  unsigned int v18; // ebx
  unsigned int v19; // eax
  int v20; // ecx
  __int64 Query; // rax
  struct IStorageNameQuery *v22; // rbx
  unsigned __int8 v23; // di
  char v24; // si
  const unsigned __int16 *v25; // rbx
  ConnectedStorage *v26; // rax
  const unsigned __int16 *v27; // r8
  int v28; // edx
  __int64 v29; // rcx
  unsigned int v30; // ebx
  HSTRING *v32; // [rsp+20h] [rbp-178h]
  unsigned int v33; // [rsp+28h] [rbp-170h]
  unsigned __int16 *v34; // [rsp+40h] [rbp-158h] BYREF
  HSTRING string; // [rsp+48h] [rbp-150h] BYREF
  HSTRING v36; // [rsp+50h] [rbp-148h] BYREF
  HSTRING v37; // [rsp+58h] [rbp-140h] BYREF
  HSTRING v38; // [rsp+60h] [rbp-138h] BYREF
  HSTRING newString; // [rsp+68h] [rbp-130h] BYREF
  HSTRING v40; // [rsp+70h] [rbp-128h] BYREF
  HSTRING v41; // [rsp+78h] [rbp-120h] BYREF
  unsigned __int64 v42; // [rsp+80h] [rbp-118h]
  struct IStorageNameQuery **v43; // [rsp+88h] [rbp-110h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+90h] [rbp-108h] BYREF
  __int64 v45[6]; // [rsp+A0h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+D0h] [rbp-C8h] BYREF

  newString = a4;
  v42 = (unsigned __int64)a3;
  v43 = a5;
  v38 = 0;
  v41 = 0;
  v40 = 0;
  v37 = 0;
  v36 = 0;
  LOBYTE(v34) = 0;
  v7 = 0;
  if ( !ConnectedStorage::gShutdown )
  {
    ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
    ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, &CriticalSection, v8);
    if ( !ConnectedStorage::gServiceRef )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v9);
    ++ConnectedStorage::gServiceRef;
    ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
    LeaveCriticalSection(lpCriticalSection[0]);
  }
  v10 = qword_1800C0858;
  lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
  v11 = (unsigned int *)ConnectedStorage::CallerInfoWithResult::Get(
                          (ConnectedStorage::StorageService *)((char *)this + 64),
                          (__int64)a2,
                          a3);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, a2);
  ConnectedStorage::SimpleHStringWrapper::operator=(&v38);
  WindowsDeleteString(string);
  AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v37);
  v13 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v40);
  v14 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v41);
  LOBYTE(v15) = 1;
  ConnectedStorage::Service::GetUserInfoFromUserContextToken(v10, v42, v15, v14, v13, AddressOf, (bool *)&v34);
  v16 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, newString);
  ConnectedStorage::NormalizeScid(&string, v16);
  ConnectedStorage::SimpleHStringWrapper::operator=(&v36);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString);
  if ( (ConnectedStorageEnableBits & 8) != 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
    v18 = (unsigned int)WindowsGetStringRawBuffer(v37, 0);
    v19 = (unsigned int)WindowsGetStringRawBuffer(v36, 0);
    McTemplateU0zzz_EventWriteTransfer(
      v20,
      (unsigned int)ConnectedStorageServiceCreateQueryStart,
      v19,
      v18,
      (__int64)StringRawBuffer);
  }
  if ( !a5 )
  {
    ConnectedStorage::ComError::ComError((ConnectedStorage::ComError *)pExceptionObject);
    throw (ConnectedStorage::ComError *)pExceptionObject;
  }
  *a5 = 0;
  string = 0;
  ConnectedStorage::ContextDesc::ContextDesc(
    (ConnectedStorage::ContextDesc *)v45,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v41,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v40,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v37,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v36,
    (const struct ConnectedStorage::SimpleHStringWrapper *)v11,
    v11[6],
    (bool)v34);
  Query = ConnectedStorage::Service::CreateQuery(v10, (__int64)v45, (__int64)&v38);
  Microsoft::WRL::ComPtr<IStorageContainerSyncData>::operator=(&string, Query);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&newString);
  v22 = (struct IStorageNameQuery *)string;
  if ( string )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 8LL))(string);
  *a5 = v22;
  ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
  if ( v10 )
    ConnectedStorage::Service::ReturnInstance();
  if ( !*a5 )
    v7 = -2147467259;
  LODWORD(string) = v7;
  v23 = (unsigned __int8)WindowsGetStringRawBuffer(v38, 0);
  v24 = (char)v34;
  v25 = WindowsGetStringRawBuffer(v37, 0);
  v26 = (ConnectedStorage *)WindowsGetStringRawBuffer(v36, 0);
  LODWORD(v32) = v7;
  LOBYTE(v27) = v24;
  ConnectedStorage::EventWriteCreateQuery(v26, v25, v27, v23, (const unsigned __int16 *const)v32, v33);
  if ( (ConnectedStorageEnableBits & 8) != 0 )
    McTemplateU0d_EventWriteTransfer(v29, ConnectedStorageServiceCreateQueryStop, v7);
  v30 = ConnectedStorage::FilterHresult((ConnectedStorage *)v7, v28);
  WindowsDeleteString(v36);
  v36 = 0;
  WindowsDeleteString(v37);
  v37 = 0;
  WindowsDeleteString(v40);
  v40 = 0;
  WindowsDeleteString(v41);
  v41 = 0;
  WindowsDeleteString(v38);
  return v30;
}

```

## disassembly

```asm
0x180022210  push    rbx
0x180022212  push    rsi
0x180022213  push    rdi
0x180022214  push    r12
0x180022216  push    r13
0x180022218  push    r14
0x18002221a  push    r15
0x18002221c  sub     rsp, 160h
0x180022223  mov     rax, cs:__security_cookie
0x18002222a  xor     rax, rsp
0x18002222d  mov     [rsp+198h+var_48], rax
0x180022235  mov     [rsp+198h+newString], r9
0x18002223a  mov     [rsp+198h+var_118], r8
0x180022242  mov     rsi, rdx
0x180022245  mov     rbx, rcx
0x180022248  mov     r12, [rsp+198h+arg_20]
0x180022250  mov     [rsp+198h+var_110], r12
0x180022258  xor     r14d, r14d
0x18002225b  mov     [rsp+198h+var_138], r14
0x180022260  mov     [rsp+198h+var_120], r14
0x180022265  mov     [rsp+198h+var_128], r14
0x18002226a  mov     [rsp+198h+var_140], r14
0x18002226f  mov     [rsp+198h+var_148], r14
0x180022274  mov     byte ptr [rsp+198h+var_158], r14b
0x180022279  mov     r15d, r14d
0x18002227c  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, r14b; bool ConnectedStorage::gShutdown
0x180022283  jnz     short loc_1800222EC
0x180022285  or      edx, 0FFFFFFFFh; unsigned int
0x180022288  lea     rcx, qword_1800C0998; this
0x18002228f  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x180022294  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x18002229b  lea     rcx, [rsp+198h+lpCriticalSection]; this
0x1800222a3  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800222a8  nop
0x1800222a9  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x1800222af  test    eax, eax
0x1800222b1  jnz     short loc_1800222C4
0x1800222b3  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x1800222ba  mov     ecx, 80004005h; this
0x1800222bf  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x1800222c4  inc     eax
0x1800222c6  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x1800222cc  mov     edx, 2
0x1800222d1  mov     rcx, cs:qword_1800C0858
0x1800222d8  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x1800222dd  nop
0x1800222de  mov     rcx, [rsp+198h+lpCriticalSection]; lpCriticalSection
0x1800222e6  call    cs:__imp_LeaveCriticalSection
0x1800222ec  mov     rdi, cs:qword_1800C0858
0x1800222f3  mov     [rsp+198h+lpCriticalSection], rdi
0x1800222fb  lea     rcx, [rbx+40h]; this
0x1800222ff  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x180022304  mov     r13, rax
0x180022307  mov     rdx, rsi; string
0x18002230a  lea     rcx, [rsp+198h+string]; newString
0x18002230f  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180022314  nop
0x180022315  mov     rdx, rax
0x180022318  lea     rcx, [rsp+198h+var_138]; newString
0x18002231d  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180022322  nop
0x180022323  mov     rcx, [rsp+198h+string]; string
0x180022328  call    cs:__imp_WindowsDeleteString
0x18002232e  lea     rcx, [rsp+198h+var_140]; this
0x180022333  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180022338  mov     rsi, rax
0x18002233b  lea     rcx, [rsp+198h+var_128]; this
0x180022340  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180022345  mov     rbx, rax
0x180022348  lea     rcx, [rsp+198h+var_120]; this
0x18002234d  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180022352  lea     rcx, [rsp+198h+var_158]
0x180022357  mov     [rsp+198h+var_168], rcx; bool *
0x18002235c  mov     [rsp+198h+var_170], rsi; HSTRING *
0x180022361  mov     [rsp+198h+var_178], rbx; HSTRING *
0x180022366  mov     r9, rax; HSTRING *
0x180022369  mov     r8b, 1; bool
0x18002236c  mov     rbx, [rsp+198h+var_118]
0x180022374  mov     rdx, rbx; unsigned __int64
0x180022377  mov     rcx, rdi; this
0x18002237a  call    ?GetUserInfoFromUserContextToken@Service@ConnectedStorage@@QEAAX_K_NPEAPEAUHSTRING__@@22PEA_N@Z; ConnectedStorage::Service::GetUserInfoFromUserContextToken(unsigned __int64,bool,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,bool *)
0x18002237f  mov     rdx, [rsp+198h+newString]; string
0x180022384  lea     rcx, [rsp+198h+newString]; newString
0x180022389  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x18002238e  nop
0x18002238f  mov     rdx, rax
0x180022392  lea     rcx, [rsp+198h+string]
0x180022397  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x18002239c  nop
0x18002239d  mov     rdx, rax
0x1800223a0  lea     rcx, [rsp+198h+var_148]; newString
0x1800223a5  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x1800223aa  nop
0x1800223ab  mov     rcx, [rsp+198h+string]; string
0x1800223b0  call    cs:__imp_WindowsDeleteString
0x1800223b6  mov     [rsp+198h+string], r14
0x1800223bb  mov     rcx, [rsp+198h+newString]; string
0x1800223c0  call    cs:__imp_WindowsDeleteString
0x1800223c6  test    cs:ConnectedStorageEnableBits, 8
0x1800223cd  jz      short loc_18002241B
0x1800223cf  xor     edx, edx; length
0x1800223d1  mov     rcx, [rsp+198h+var_138]; string
0x1800223d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800223dc  mov     rsi, rax
0x1800223df  xor     edx, edx; length
0x1800223e1  mov     rcx, [rsp+198h+var_140]; string
0x1800223e6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800223ec  mov     rbx, rax
0x1800223ef  xor     edx, edx; length
0x1800223f1  mov     rcx, [rsp+198h+var_148]; string
0x1800223f6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800223fc  mov     [rsp+198h+var_178], rsi
0x180022401  mov     r9, rbx
0x180022404  mov     r8, rax
0x180022407  lea     rdx, ConnectedStorageServiceCreateQueryStart
0x18002240e  call    McTemplateU0zzz_EventWriteTransfer
0x180022413  mov     rbx, [rsp+198h+var_118]
0x18002241b  test    r12, r12
0x18002241e  jnz     short loc_180022446
0x180022420  mov     edx, 80004003h; int
0x180022425  lea     rcx, [rsp+198h+pExceptionObject]; this
0x18002242d  call    ??0ComError@ConnectedStorage@@QEAA@J@Z; ConnectedStorage::ComError::ComError(long)
0x180022432  lea     rdx, _TI2?AVComError@ConnectedStorage@@; pThrowInfo
0x180022439  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x180022441  call    _CxxThrowException_0
0x180022446  mov     [r12], r14
0x18002244a  mov     [rsp+198h+string], r14
0x18002244f  mov     al, byte ptr [rsp+198h+var_158]
0x180022453  mov     [rsp+198h+var_160], al; bool
0x180022457  mov     eax, [r13+18h]
0x18002245b  mov     dword ptr [rsp+198h+var_168], eax; unsigned int
0x18002245f  mov     [rsp+198h+var_170], r13; struct ConnectedStorage::SimpleHStringWrapper *
0x180022464  lea     rax, [rsp+198h+var_148]
0x180022469  mov     [rsp+198h+var_178], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x18002246e  lea     r9, [rsp+198h+var_140]; struct ConnectedStorage::SimpleHStringWrapper *
0x180022473  lea     r8, [rsp+198h+var_128]; struct ConnectedStorage::SimpleHStringWrapper *
0x180022478  lea     rdx, [rsp+198h+var_120]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002247d  lea     rcx, [rsp+198h+var_F8]; this
0x180022485  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x18002248a  nop
0x18002248b  lea     rax, [rsp+198h+var_138]
0x180022490  mov     [rsp+198h+var_170], rax; unsigned int
0x180022495  lea     rax, [rsp+198h+var_F8]
0x18002249d  mov     [rsp+198h+var_178], rax; __int64
0x1800224a2  mov     r9, rbx
0x1800224a5  mov     r8, r13
0x1800224a8  lea     rdx, [rsp+198h+newString]
0x1800224ad  mov     rcx, rdi; struct ConnectedStorage::Mutex *
0x1800224b0  call    ?CreateQuery@Service@ConnectedStorage@@QEAA?AV?$ComPtr@UIStorageNameQuery@@@WRL@Microsoft@@AEBVCallerInfo@2@_KAEBVContextDesc@2@AEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::Service::CreateQuery(ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &)
0x1800224b5  mov     rdx, rax
0x1800224b8  lea     rcx, [rsp+198h+string]
0x1800224bd  call    ??4?$ComPtr@UIStorageContainerSyncData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IStorageContainerSyncData>::operator=(Microsoft::WRL::ComPtr<IStorageContainerSyncData> &&)
0x1800224c2  lea     rcx, [rsp+198h+newString]
0x1800224c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800224cc  nop
0x1800224cd  mov     rbx, [rsp+198h+string]
0x1800224d2  test    rbx, rbx
0x1800224d5  jz      short loc_1800224E7
0x1800224d7  mov     rax, [rbx]
0x1800224da  mov     rcx, rbx
0x1800224dd  mov     rax, [rax+8]
0x1800224e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224e6  nop
0x1800224e7  mov     [r12], rbx
0x1800224eb  lea     rcx, [rsp+198h+var_F8]; this
0x1800224f3  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x1800224f8  nop
0x1800224f9  lea     rcx, [rsp+198h+string]
0x1800224fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022503  nop
0x180022504  test    rdi, rdi
0x180022507  jz      short loc_18002250F
0x180022509  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x18002250e  nop
0x18002250f  mov     eax, 80004005h
0x180022514  cmp     [r12], r14
0x180022518  cmovz   r15d, eax
0x18002251c  mov     dword ptr [rsp+198h+string], r15d
0x180022521  xor     edx, edx; length
0x180022523  mov     rcx, [rsp+198h+var_138]; string
0x180022528  call    cs:__imp_WindowsGetStringRawBuffer
0x18002252e  mov     rdi, rax
0x180022531  mov     sil, byte ptr [rsp+198h+var_158]
0x180022536  xor     edx, edx; length
0x180022538  mov     rcx, [rsp+198h+var_140]; string
0x18002253d  call    cs:__imp_WindowsGetStringRawBuffer
0x180022543  mov     rbx, rax
0x180022546  xor     edx, edx; length
0x180022548  mov     rcx, [rsp+198h+var_148]; string
0x18002254d  call    cs:__imp_WindowsGetStringRawBuffer
0x180022553  mov     dword ptr [rsp+198h+var_178], r15d; unsigned __int16 *
0x180022558  mov     r9, rdi; bool
0x18002255b  mov     r8b, sil; unsigned __int16 *
0x18002255e  mov     rdx, rbx; unsigned __int16 *
0x180022561  mov     rcx, rax; this
0x180022564  call    ?EventWriteCreateQuery@ConnectedStorage@@YAXQEBG0_N0I@Z; ConnectedStorage::EventWriteCreateQuery(ushort const * const,ushort const * const,bool,ushort const * const,uint)
0x180022569  nop
0x18002256a  jmp     short loc_180022598
0x18002256c  jmp     short loc_180022570
0x18002256e  jmp     short $+2
0x180022570  mov     r12, [rsp+198h+var_110]
0x180022578  xor     r14d, r14d
0x18002257b  mov     r15d, dword ptr [rsp+198h+string]
0x180022580  test    r12, r12
0x180022583  jz      short loc_180022521
0x180022585  test    r15d, r15d
0x180022588  jns     short loc_18002250F
0x18002258a  mov     [r12], r14
0x18002258e  jmp     short loc_180022521
0x180022590  xor     r14d, r14d
0x180022593  mov     r15d, dword ptr [rsp+198h+string]
0x180022598  test    cs:ConnectedStorageEnableBits, 8
0x18002259f  jz      short loc_1800225B0
0x1800225a1  mov     r8d, r15d
0x1800225a4  lea     rdx, ConnectedStorageServiceCreateQueryStop
0x1800225ab  call    McTemplateU0d_EventWriteTransfer
0x1800225b0  mov     ecx, r15d; this
0x1800225b3  call    ?FilterHresult@ConnectedStorage@@YAJJ@Z; ConnectedStorage::FilterHresult(long)
0x1800225b8  mov     ebx, eax
0x1800225ba  mov     rcx, [rsp+198h+var_148]; string
0x1800225bf  call    cs:__imp_WindowsDeleteString
0x1800225c5  mov     [rsp+198h+var_148], r14
0x1800225ca  mov     rcx, [rsp+198h+var_140]; string
0x1800225cf  call    cs:__imp_WindowsDeleteString
0x1800225d5  mov     [rsp+198h+var_140], r14
0x1800225da  mov     rcx, [rsp+198h+var_128]; string
0x1800225df  call    cs:__imp_WindowsDeleteString
0x1800225e5  mov     [rsp+198h+var_128], r14
0x1800225ea  mov     rcx, [rsp+198h+var_120]; string
0x1800225ef  call    cs:__imp_WindowsDeleteString
0x1800225f5  mov     [rsp+198h+var_120], r14
0x1800225fa  mov     rcx, [rsp+198h+var_138]; string
0x1800225ff  call    cs:__imp_WindowsDeleteString
0x180022605  mov     eax, ebx
0x180022607  mov     rcx, [rsp+198h+var_48]
0x18002260f  xor     rcx, rsp; StackCookie
0x180022612  call    __security_check_cookie
0x180022617  add     rsp, 160h
0x18002261e  pop     r15
0x180022620  pop     r14
0x180022622  pop     r13
0x180022624  pop     r12
0x180022626  pop     rdi
0x180022627  pop     rsi
0x180022628  pop     rbx
0x180022629  retn
```
