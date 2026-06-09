# ConnectedStorage::StorageService::CreateBlobQuery(HSTRING__ *,HSTRING__ *,unsigned __int64,HSTRING__ *,IStorageBlobNameQuery * *)

- ea: `0x180021dd0`
- end: `0x180022205`
- name: `?CreateBlobQuery@StorageService@ConnectedStorage@@MEAAJPEAUHSTRING__@@0_K0PEAPEAUIStorageBlobNameQuery@@@Z`
- size: `1077`
- prototype: `int(ConnectedStorage::StorageService *__hidden this, HSTRING, HSTRING, unsigned __int64, HSTRING, struct IStorageBlobNameQuery **)`
- caller_count: `0`
- callee_count: `23`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x180004760`
- `0x180007bd0`
- `0x18000a040`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180011bd0`
- `0x1800125ec`
- `0x180012bd4`
- `0x180012ed8`
- `0x180013e1c`
- `0x1800140ac`
- `0x180014a88`
- `0x180015008`
- `0x1800160c8`
- `0x1800170d4`
- `0x18001d4e8`
- `0x180020e68`
- `0x180021dd0`
- `0x180022dec`
- `0x1800235c0`
- `0x18004ae14`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021ebe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021f03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021fa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022187`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021f03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021fa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022187`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800220ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800220fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800220ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800220fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022122`

## string_xrefs

- `0x180021e8b`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall ConnectedStorage::StorageService::CreateBlobQuery(
        ConnectedStorage::StorageService *this,
        HSTRING a2,
        char *a3,
        unsigned __int64 a4,
        HSTRING a5,
        struct IStorageBlobNameQuery **a6)
{
  unsigned int v8; // r12d
  char *v9; // r8
  const unsigned __int16 *v10; // r8
  ConnectedStorage::Service *v11; // rdi
  unsigned int *v12; // r13
  HSTRING *AddressOf; // r14
  HSTRING *v14; // rbx
  HSTRING *v15; // rax
  char *v16; // r8
  __int64 v17; // rax
  __int64 BlobQuery; // rax
  struct IStorageBlobNameQuery *v19; // rbx
  const unsigned __int16 *StringRawBuffer; // r14
  unsigned __int8 v21; // di
  char v22; // si
  const unsigned __int16 *v23; // rbx
  ConnectedStorage *v24; // rax
  const unsigned __int16 *v25; // r8
  int v26; // edx
  HSTRING *v28; // [rsp+28h] [rbp-180h]
  unsigned int v29; // [rsp+30h] [rbp-178h]
  unsigned __int16 *v30; // [rsp+40h] [rbp-168h] BYREF
  HSTRING string; // [rsp+48h] [rbp-160h] BYREF
  HSTRING v32; // [rsp+50h] [rbp-158h] BYREF
  HSTRING v33; // [rsp+58h] [rbp-150h] BYREF
  HSTRING v34; // [rsp+60h] [rbp-148h] BYREF
  HSTRING v35; // [rsp+68h] [rbp-140h] BYREF
  HSTRING v36; // [rsp+70h] [rbp-138h] BYREF
  HSTRING v37; // [rsp+78h] [rbp-130h] BYREF
  HSTRING v38; // [rsp+80h] [rbp-128h] BYREF
  HSTRING newString; // [rsp+88h] [rbp-120h] BYREF
  unsigned __int64 v40; // [rsp+90h] [rbp-118h]
  struct IStorageBlobNameQuery **v41; // [rsp+98h] [rbp-110h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v43[6]; // [rsp+B0h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+E0h] [rbp-C8h] BYREF

  v40 = a4;
  v35 = (HSTRING)a3;
  newString = a5;
  v41 = a6;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  LOBYTE(v30) = 0;
  v8 = 0;
  if ( !ConnectedStorage::gShutdown )
  {
    ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
    ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, &CriticalSection, v9);
    if ( !ConnectedStorage::gServiceRef )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v10);
    ++ConnectedStorage::gServiceRef;
    ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
    LeaveCriticalSection(lpCriticalSection[0]);
  }
  v11 = qword_1800C0858;
  lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
  v12 = (unsigned int *)ConnectedStorage::CallerInfoWithResult::Get(
                          (ConnectedStorage::StorageService *)((char *)this + 64),
                          (__int64)a2,
                          a3);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, a2);
  ConnectedStorage::SimpleHStringWrapper::operator=(&v38);
  WindowsDeleteString(string);
  AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v34);
  v14 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v36);
  v15 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v37);
  LOBYTE(v16) = 1;
  ConnectedStorage::Service::GetUserInfoFromUserContextToken(v11, v40, v16, v15, v14, AddressOf, (bool *)&v30);
  v17 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, newString);
  ConnectedStorage::NormalizeScid(&string, v17);
  ConnectedStorage::SimpleHStringWrapper::operator=(&v33);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v35, v35);
  ConnectedStorage::SimpleHStringWrapper::operator=(&v32);
  WindowsDeleteString(v35);
  if ( !a6 )
  {
    ConnectedStorage::ComError::ComError((ConnectedStorage::ComError *)pExceptionObject);
    throw (ConnectedStorage::ComError *)pExceptionObject;
  }
  *a6 = 0;
  string = 0;
  ConnectedStorage::ContextDesc::ContextDesc(
    (ConnectedStorage::ContextDesc *)v43,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v37,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v36,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v34,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v33,
    (const struct ConnectedStorage::SimpleHStringWrapper *)v12,
    v12[6],
    (bool)v30);
  BlobQuery = ConnectedStorage::Service::CreateBlobQuery(v11, (__int64)v43, (__int64)&v38, (__int64)&v32);
  Microsoft::WRL::ComPtr<IStorageContainerSyncData>::operator=(&string, BlobQuery);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v19 = (struct IStorageBlobNameQuery *)string;
  if ( string )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 8LL))(string);
  *a6 = v19;
  ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
  if ( v11 )
    ConnectedStorage::Service::ReturnInstance();
  if ( !*a6 )
    v8 = -2147467259;
  LODWORD(string) = v8;
  StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
  v21 = (unsigned __int8)WindowsGetStringRawBuffer(v32, 0);
  v22 = (char)v30;
  v23 = WindowsGetStringRawBuffer(v34, 0);
  v24 = (ConnectedStorage *)WindowsGetStringRawBuffer(v33, 0);
  LODWORD(v28) = v8;
  LOBYTE(v25) = v22;
  ConnectedStorage::EventWriteCreateBlobQuery(
    v24,
    v23,
    v25,
    v21,
    StringRawBuffer,
    (const unsigned __int16 *const)v28,
    v29);
  LODWORD(v23) = ConnectedStorage::FilterHresult((ConnectedStorage *)v8, v26);
  WindowsDeleteString(v32);
  v32 = 0;
  WindowsDeleteString(v33);
  v33 = 0;
  WindowsDeleteString(v34);
  v34 = 0;
  WindowsDeleteString(v36);
  v36 = 0;
  WindowsDeleteString(v37);
  v37 = 0;
  WindowsDeleteString(v38);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180021dd0  push    rbx
0x180021dd2  push    rsi
0x180021dd3  push    rdi
0x180021dd4  push    r12
0x180021dd6  push    r13
0x180021dd8  push    r14
0x180021dda  push    r15
0x180021ddc  sub     rsp, 170h
0x180021de3  mov     rax, cs:__security_cookie
0x180021dea  xor     rax, rsp
0x180021ded  mov     [rsp+1A8h+var_48], rax
0x180021df5  mov     [rsp+1A8h+var_118], r9
0x180021dfd  mov     [rsp+1A8h+var_140], r8
0x180021e02  mov     r14, rdx
0x180021e05  mov     rbx, rcx
0x180021e08  mov     rax, [rsp+1A8h+arg_20]
0x180021e10  mov     [rsp+1A8h+newString], rax
0x180021e18  mov     rsi, [rsp+1A8h+arg_28]
0x180021e20  mov     [rsp+1A8h+var_110], rsi
0x180021e28  xor     r15d, r15d
0x180021e2b  mov     [rsp+1A8h+var_128], r15
0x180021e33  mov     [rsp+1A8h+var_130], r15
0x180021e38  mov     [rsp+1A8h+var_138], r15
0x180021e3d  mov     [rsp+1A8h+var_148], r15
0x180021e42  mov     [rsp+1A8h+var_150], r15
0x180021e47  mov     [rsp+1A8h+var_158], r15
0x180021e4c  mov     byte ptr [rsp+1A8h+var_168], r15b
0x180021e51  mov     r12d, r15d
0x180021e54  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, r15b; bool ConnectedStorage::gShutdown
0x180021e5b  jnz     short loc_180021EC4
0x180021e5d  or      edx, 0FFFFFFFFh; unsigned int
0x180021e60  lea     rcx, qword_1800C0998; this
0x180021e67  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x180021e6c  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x180021e73  lea     rcx, [rsp+1A8h+lpCriticalSection]; this
0x180021e7b  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180021e80  nop
0x180021e81  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x180021e87  test    eax, eax
0x180021e89  jnz     short loc_180021E9C
0x180021e8b  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x180021e92  mov     ecx, 80004005h; this
0x180021e97  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180021e9c  inc     eax
0x180021e9e  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180021ea4  mov     edx, 2
0x180021ea9  mov     rcx, cs:qword_1800C0858
0x180021eb0  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x180021eb5  nop
0x180021eb6  mov     rcx, [rsp+1A8h+lpCriticalSection]; lpCriticalSection
0x180021ebe  call    cs:__imp_LeaveCriticalSection
0x180021ec4  mov     rdi, cs:qword_1800C0858
0x180021ecb  mov     [rsp+1A8h+lpCriticalSection], rdi
0x180021ed3  lea     rcx, [rbx+40h]; this
0x180021ed7  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x180021edc  mov     r13, rax
0x180021edf  mov     rdx, r14; string
0x180021ee2  lea     rcx, [rsp+1A8h+string]; newString
0x180021ee7  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180021eec  nop
0x180021eed  mov     rdx, rax
0x180021ef0  lea     rcx, [rsp+1A8h+var_128]; newString
0x180021ef8  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180021efd  nop
0x180021efe  mov     rcx, [rsp+1A8h+string]; string
0x180021f03  call    cs:__imp_WindowsDeleteString
0x180021f09  lea     rcx, [rsp+1A8h+var_148]; this
0x180021f0e  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180021f13  mov     r14, rax
0x180021f16  lea     rcx, [rsp+1A8h+var_138]; this
0x180021f1b  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180021f20  mov     rbx, rax
0x180021f23  lea     rcx, [rsp+1A8h+var_130]; this
0x180021f28  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180021f2d  lea     rcx, [rsp+1A8h+var_168]
0x180021f32  mov     [rsp+1A8h+var_178], rcx; bool *
0x180021f37  mov     [rsp+1A8h+var_180], r14; HSTRING *
0x180021f3c  mov     [rsp+1A8h+var_188], rbx; HSTRING *
0x180021f41  mov     r9, rax; HSTRING *
0x180021f44  mov     r8b, 1; bool
0x180021f47  mov     rbx, [rsp+1A8h+var_118]
0x180021f4f  mov     rdx, rbx; unsigned __int64
0x180021f52  mov     rcx, rdi; this
0x180021f55  call    ?GetUserInfoFromUserContextToken@Service@ConnectedStorage@@QEAAX_K_NPEAPEAUHSTRING__@@22PEA_N@Z; ConnectedStorage::Service::GetUserInfoFromUserContextToken(unsigned __int64,bool,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,bool *)
0x180021f5a  mov     rdx, [rsp+1A8h+newString]; string
0x180021f62  lea     rcx, [rsp+1A8h+newString]; newString
0x180021f6a  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180021f6f  nop
0x180021f70  mov     rdx, rax
0x180021f73  lea     rcx, [rsp+1A8h+string]
0x180021f78  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x180021f7d  nop
0x180021f7e  mov     rdx, rax
0x180021f81  lea     rcx, [rsp+1A8h+var_150]; newString
0x180021f86  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180021f8b  nop
0x180021f8c  mov     rcx, [rsp+1A8h+string]; string
0x180021f91  call    cs:__imp_WindowsDeleteString
0x180021f97  mov     [rsp+1A8h+string], r15
0x180021f9c  mov     rcx, [rsp+1A8h+newString]; string
0x180021fa4  call    cs:__imp_WindowsDeleteString
0x180021faa  mov     rdx, [rsp+1A8h+var_140]; string
0x180021faf  lea     rcx, [rsp+1A8h+var_140]; newString
0x180021fb4  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180021fb9  nop
0x180021fba  mov     rdx, rax
0x180021fbd  lea     rcx, [rsp+1A8h+var_158]; newString
0x180021fc2  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180021fc7  nop
0x180021fc8  mov     rcx, [rsp+1A8h+var_140]; string
0x180021fcd  call    cs:__imp_WindowsDeleteString
0x180021fd3  test    rsi, rsi
0x180021fd6  jnz     short loc_180021FFE
0x180021fd8  mov     edx, 80004003h; int
0x180021fdd  lea     rcx, [rsp+1A8h+pExceptionObject]; this
0x180021fe5  call    ??0ComError@ConnectedStorage@@QEAA@J@Z; ConnectedStorage::ComError::ComError(long)
0x180021fea  lea     rdx, _TI2?AVComError@ConnectedStorage@@; pThrowInfo
0x180021ff1  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x180021ff9  call    _CxxThrowException_0
0x180021ffe  mov     [rsi], r15
0x180022001  mov     [rsp+1A8h+string], r15
0x180022006  mov     al, byte ptr [rsp+1A8h+var_168]
0x18002200a  mov     [rsp+1A8h+var_170], al; bool
0x18002200e  mov     eax, [r13+18h]
0x180022012  mov     dword ptr [rsp+1A8h+var_178], eax; unsigned int
0x180022016  mov     [rsp+1A8h+var_180], r13; struct ConnectedStorage::SimpleHStringWrapper *
0x18002201b  lea     rax, [rsp+1A8h+var_150]
0x180022020  mov     [rsp+1A8h+var_188], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x180022025  lea     r9, [rsp+1A8h+var_148]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002202a  lea     r8, [rsp+1A8h+var_138]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002202f  lea     rdx, [rsp+1A8h+var_130]; struct ConnectedStorage::SimpleHStringWrapper *
0x180022034  lea     rcx, [rsp+1A8h+var_F8]; this
0x18002203c  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x180022041  nop
0x180022042  lea     rax, [rsp+1A8h+var_158]
0x180022047  mov     [rsp+1A8h+var_178], rax; unsigned int
0x18002204c  lea     rax, [rsp+1A8h+var_128]
0x180022054  mov     [rsp+1A8h+var_180], rax; __int64
0x180022059  lea     rax, [rsp+1A8h+var_F8]
0x180022061  mov     [rsp+1A8h+var_188], rax; __int64
0x180022066  mov     r9, rbx
0x180022069  mov     r8, r13
0x18002206c  lea     rdx, [rsp+1A8h+var_140]
0x180022071  mov     rcx, rdi; struct ConnectedStorage::Mutex *
0x180022074  call    ?CreateBlobQuery@Service@ConnectedStorage@@QEAA?AV?$ComPtr@UIStorageBlobNameQuery@@@WRL@Microsoft@@AEBVCallerInfo@2@_KAEBVContextDesc@2@AEBVSimpleHStringWrapper@2@3@Z; ConnectedStorage::Service::CreateBlobQuery(ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180022079  mov     rdx, rax
0x18002207c  lea     rcx, [rsp+1A8h+string]
0x180022081  call    ??4?$ComPtr@UIStorageContainerSyncData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IStorageContainerSyncData>::operator=(Microsoft::WRL::ComPtr<IStorageContainerSyncData> &&)
0x180022086  lea     rcx, [rsp+1A8h+var_140]
0x18002208b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022090  nop
0x180022091  mov     rbx, [rsp+1A8h+string]
0x180022096  test    rbx, rbx
0x180022099  jz      short loc_1800220AB
0x18002209b  mov     rax, [rbx]
0x18002209e  mov     rcx, rbx
0x1800220a1  mov     rax, [rax+8]
0x1800220a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220aa  nop
0x1800220ab  mov     [rsi], rbx
0x1800220ae  lea     rcx, [rsp+1A8h+var_F8]; this
0x1800220b6  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x1800220bb  nop
0x1800220bc  lea     rcx, [rsp+1A8h+string]
0x1800220c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800220c6  nop
0x1800220c7  test    rdi, rdi
0x1800220ca  jz      short loc_1800220D2
0x1800220cc  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x1800220d1  nop
0x1800220d2  mov     eax, 80004005h
0x1800220d7  cmp     [rsi], r15
0x1800220da  cmovz   r12d, eax
0x1800220de  mov     dword ptr [rsp+1A8h+string], r12d
0x1800220e3  xor     edx, edx; length
0x1800220e5  mov     rcx, [rsp+1A8h+var_128]; string
0x1800220ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800220f3  mov     r14, rax
0x1800220f6  xor     edx, edx; length
0x1800220f8  mov     rcx, [rsp+1A8h+var_158]; string
0x1800220fd  call    cs:__imp_WindowsGetStringRawBuffer
0x180022103  mov     rdi, rax
0x180022106  mov     sil, byte ptr [rsp+1A8h+var_168]
0x18002210b  xor     edx, edx; length
0x18002210d  mov     rcx, [rsp+1A8h+var_148]; string
0x180022112  call    cs:__imp_WindowsGetStringRawBuffer
0x180022118  mov     rbx, rax
0x18002211b  xor     edx, edx; length
0x18002211d  mov     rcx, [rsp+1A8h+var_150]; string
0x180022122  call    cs:__imp_WindowsGetStringRawBuffer
0x180022128  mov     dword ptr [rsp+1A8h+var_180], r12d; unsigned __int16 *
0x18002212d  mov     [rsp+1A8h+var_188], r14; unsigned __int16 *
0x180022132  mov     r9, rdi; bool
0x180022135  mov     r8b, sil; unsigned __int16 *
0x180022138  mov     rdx, rbx; unsigned __int16 *
0x18002213b  mov     rcx, rax; this
0x18002213e  call    ?EventWriteCreateBlobQuery@ConnectedStorage@@YAXQEBG0_N00I@Z; ConnectedStorage::EventWriteCreateBlobQuery(ushort const * const,ushort const * const,bool,ushort const * const,ushort const * const,uint)
0x180022143  nop
0x180022144  jmp     short loc_180022178
0x180022146  jmp     short loc_18002214A
0x180022148  jmp     short $+2
0x18002214a  mov     rsi, [rsp+1A8h+var_110]
0x180022152  xor     r15d, r15d
0x180022155  mov     r12d, dword ptr [rsp+1A8h+string]
0x18002215a  test    rsi, rsi
0x18002215d  jz      short loc_1800220E3
0x18002215f  test    r12d, r12d
0x180022162  jns     loc_1800220D2
0x180022168  mov     [rsi], r15
0x18002216b  jmp     loc_1800220E3
0x180022170  xor     r15d, r15d
0x180022173  mov     r12d, dword ptr [rsp+1A8h+string]
0x180022178  mov     ecx, r12d; this
0x18002217b  call    ?FilterHresult@ConnectedStorage@@YAJJ@Z; ConnectedStorage::FilterHresult(long)
0x180022180  mov     ebx, eax
0x180022182  mov     rcx, [rsp+1A8h+var_158]; string
0x180022187  call    cs:__imp_WindowsDeleteString
0x18002218d  mov     [rsp+1A8h+var_158], r15
0x180022192  mov     rcx, [rsp+1A8h+var_150]; string
0x180022197  call    cs:__imp_WindowsDeleteString
0x18002219d  mov     [rsp+1A8h+var_150], r15
0x1800221a2  mov     rcx, [rsp+1A8h+var_148]; string
0x1800221a7  call    cs:__imp_WindowsDeleteString
0x1800221ad  mov     [rsp+1A8h+var_148], r15
0x1800221b2  mov     rcx, [rsp+1A8h+var_138]; string
0x1800221b7  call    cs:__imp_WindowsDeleteString
0x1800221bd  mov     [rsp+1A8h+var_138], r15
0x1800221c2  mov     rcx, [rsp+1A8h+var_130]; string
0x1800221c7  call    cs:__imp_WindowsDeleteString
0x1800221cd  mov     [rsp+1A8h+var_130], r15
0x1800221d2  mov     rcx, [rsp+1A8h+var_128]; string
0x1800221da  call    cs:__imp_WindowsDeleteString
0x1800221e0  mov     eax, ebx
0x1800221e2  mov     rcx, [rsp+1A8h+var_48]
0x1800221ea  xor     rcx, rsp; StackCookie
0x1800221ed  call    __security_check_cookie
0x1800221f2  add     rsp, 170h
0x1800221f9  pop     r15
0x1800221fb  pop     r14
0x1800221fd  pop     r13
0x1800221ff  pop     r12
0x180022201  pop     rdi
0x180022202  pop     rsi
0x180022203  pop     rbx
0x180022204  retn
```
