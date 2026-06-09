# ConnectedStorage::StorageService::GetQuota(unsigned __int64,HSTRING__ *,IStorageQuotaHandler *,_GUID)

- ea: `0x180022e30`
- end: `0x18002316a`
- name: `?GetQuota@StorageService@ConnectedStorage@@MEAAJ_KPEAUHSTRING__@@PEAUIStorageQuotaHandler@@U_GUID@@@Z`
- size: `826`
- prototype: `int(ConnectedStorage::StorageService *__hidden this, unsigned __int64, HSTRING, struct IStorageQuotaHandler *, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000ca18`
- `0x18000cb9c`
- `0x180011bd0`
- `0x1800125ec`
- `0x180012ed8`
- `0x180013e1c`
- `0x180014a88`
- `0x180014d44`
- `0x180015008`
- `0x1800160c8`
- `0x1800170d4`
- `0x18001d8ec`
- `0x180020e68`
- `0x180022dec`
- `0x180022e30`
- `0x1800235c0`
- `0x180026820`
- `0x18004ae14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022f10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022f10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022fa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022fbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002312c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022fa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022fbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002312c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022fd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022fe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800230a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800230b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022fd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022fe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800230a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800230b1`

## string_xrefs

- `0x180022edd`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ConnectedStorage::StorageService::GetQuota(
        ConnectedStorage::StorageService *this,
        unsigned __int64 a2,
        char *a3,
        struct _GUID *a4,
        struct _GUID *a5)
{
  char *v8; // r8
  const unsigned __int16 *v9; // r8
  ConnectedStorage::Service *v10; // rbx
  unsigned int *v11; // r15
  HSTRING *AddressOf; // r14
  HSTRING *v13; // rdi
  HSTRING *v14; // rax
  char *v15; // r8
  __int64 v16; // rax
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v18; // rax
  __int64 v19; // rcx
  bool v20; // di
  const unsigned __int16 *v21; // rbx
  ConnectedStorage *v22; // rax
  const unsigned __int16 *v23; // r8
  int v24; // edx
  __int64 v25; // rcx
  unsigned int v26; // ebx
  HSTRING *v28; // [rsp+28h] [rbp-130h]
  bool v29; // [rsp+40h] [rbp-118h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-114h]
  HSTRING v31; // [rsp+48h] [rbp-110h] BYREF
  HSTRING v32; // [rsp+50h] [rbp-108h] BYREF
  HSTRING v33; // [rsp+58h] [rbp-100h] BYREF
  HSTRING v34; // [rsp+60h] [rbp-F8h] BYREF
  HSTRING string; // [rsp+68h] [rbp-F0h] BYREF
  HSTRING newString[2]; // [rsp+70h] [rbp-E8h] BYREF
  struct _GUID *v37; // [rsp+80h] [rbp-D8h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+88h] [rbp-D0h] BYREF
  _BYTE v39[48]; // [rsp+98h] [rbp-C0h] BYREF
  unsigned int v40[2]; // [rsp+C8h] [rbp-90h]
  _DWORD v41[16]; // [rsp+D0h] [rbp-88h] BYREF

  try
  {
    v37 = a4;
    *(_QWORD *)v40 = a5;
    v34 = 0;
    v33 = 0;
    v32 = 0;
    v31 = 0;
    v29 = 0;
    v30 = 0;
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
                            a2,
                            a3);
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v32);
    v13 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v33);
    v14 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v34);
    LOBYTE(v15) = 1;
    ConnectedStorage::Service::GetUserInfoFromUserContextToken(v10, a2, v15, v14, v13, AddressOf, &v29);
    v16 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(newString, (HSTRING)a3);
    ConnectedStorage::NormalizeScid(&string, v16);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v31);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(newString[0]);
    if ( (ConnectedStorageEnableBits & 8) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v31, 0);
      v18 = WindowsGetStringRawBuffer(v32, 0);
      McTemplateU0zz_EventWriteTransfer(v19, ConnectedStorageServiceGetQuotaStart, v18, StringRawBuffer);
    }
    ConnectedStorage::ContextDesc::ContextDesc(
      (ConnectedStorage::ContextDesc *)v39,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v34,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v33,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v32,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v31,
      (const struct ConnectedStorage::SimpleHStringWrapper *)v11,
      v11[6],
      v29);
    *(_OWORD *)newString = **(_OWORD **)v40;
    ConnectedStorage::Service::GetQuota(
      v10,
      (struct _GUID *)newString,
      (const struct ConnectedStorage::CallerInfo *)v11,
      a2,
      (const struct ConnectedStorage::ContextDesc *)v39,
      (struct IStorageQuotaHandler *)v37);
    ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v39);
    if ( v10 )
      ConnectedStorage::Service::ReturnInstance();
  }
  catch ( ConnectedStorage::ComError v41 )
  {
    v30 = v41[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v41);
  }
  catch ( std::bad_alloc )
  {
    v30 = -2147024882;
  }
  catch ( ... )
  {
    v30 = -2147467259;
  }
  v20 = v29;
  v21 = WindowsGetStringRawBuffer(v32, 0);
  v22 = (ConnectedStorage *)WindowsGetStringRawBuffer(v31, 0);
  LOBYTE(v23) = v20;
  ConnectedStorage::EventWriteGetQuota(v22, v21, v23, v30, v40[0], (const struct _GUID *const)v28);
  if ( (ConnectedStorageEnableBits & 8) != 0 )
    McTemplateU0d_EventWriteTransfer(v25, ConnectedStorageServiceGetQuotaStop, v30);
  v26 = ConnectedStorage::FilterHresult((ConnectedStorage *)v30, v24);
  WindowsDeleteString(v31);
  v31 = 0;
  WindowsDeleteString(v32);
  v32 = 0;
  WindowsDeleteString(v33);
  v33 = 0;
  WindowsDeleteString(v34);
  return v26;
}

```

## disassembly

```asm
0x180022e30  push    rbx
0x180022e32  push    rdi
0x180022e33  push    r12
0x180022e35  push    r13
0x180022e37  push    r14
0x180022e39  push    r15
0x180022e3b  sub     rsp, 128h
0x180022e42  mov     rax, cs:__security_cookie
0x180022e49  xor     rax, rsp
0x180022e4c  mov     [rsp+158h+var_48], rax
0x180022e54  mov     [rsp+158h+var_D8], r9
0x180022e5c  mov     r12, r8
0x180022e5f  mov     r13, rdx
0x180022e62  mov     rdi, rcx
0x180022e65  mov     rax, [rsp+158h+arg_20]
0x180022e6d  mov     qword ptr [rsp+158h+var_90], rax
0x180022e75  mov     [rsp+158h+var_F8], 0
0x180022e7e  mov     [rsp+158h+var_100], 0
0x180022e87  mov     [rsp+158h+var_108], 0
0x180022e90  mov     [rsp+158h+var_110], 0
0x180022e99  mov     byte ptr [rsp+158h+var_118], 0
0x180022e9e  mov     dword ptr [rsp+158h+var_118+4], 0
0x180022ea6  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x180022ead  jnz     short loc_180022F16
0x180022eaf  or      edx, 0FFFFFFFFh; unsigned int
0x180022eb2  lea     rcx, qword_1800C0998; this
0x180022eb9  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x180022ebe  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x180022ec5  lea     rcx, [rsp+158h+lpCriticalSection]; this
0x180022ecd  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180022ed2  nop
0x180022ed3  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x180022ed9  test    eax, eax
0x180022edb  jnz     short loc_180022EEE
0x180022edd  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x180022ee4  mov     ecx, 80004005h; this
0x180022ee9  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180022eee  inc     eax
0x180022ef0  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180022ef6  mov     edx, 2
0x180022efb  mov     rcx, cs:qword_1800C0858
0x180022f02  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x180022f07  nop
0x180022f08  mov     rcx, [rsp+158h+lpCriticalSection]; lpCriticalSection
0x180022f10  call    cs:__imp_LeaveCriticalSection
0x180022f16  mov     rbx, cs:qword_1800C0858
0x180022f1d  mov     [rsp+158h+lpCriticalSection], rbx
0x180022f25  lea     rcx, [rdi+40h]; this
0x180022f29  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x180022f2e  mov     r15, rax
0x180022f31  lea     rcx, [rsp+158h+var_108]; this
0x180022f36  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180022f3b  mov     r14, rax
0x180022f3e  lea     rcx, [rsp+158h+var_100]; this
0x180022f43  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180022f48  mov     rdi, rax
0x180022f4b  lea     rcx, [rsp+158h+var_F8]; this
0x180022f50  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180022f55  lea     rcx, [rsp+158h+var_118]
0x180022f5a  mov     [rsp+158h+var_128], rcx; bool *
0x180022f5f  mov     [rsp+158h+var_130], r14; HSTRING *
0x180022f64  mov     [rsp+158h+var_138], rdi; HSTRING *
0x180022f69  mov     r9, rax; HSTRING *
0x180022f6c  mov     r8b, 1; bool
0x180022f6f  mov     rdx, r13; unsigned __int64
0x180022f72  mov     rcx, rbx; this
0x180022f75  call    ?GetUserInfoFromUserContextToken@Service@ConnectedStorage@@QEAAX_K_NPEAPEAUHSTRING__@@22PEA_N@Z; ConnectedStorage::Service::GetUserInfoFromUserContextToken(unsigned __int64,bool,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,bool *)
0x180022f7a  mov     rdx, r12; string
0x180022f7d  lea     rcx, [rsp+158h+newString]; newString
0x180022f82  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180022f87  nop
0x180022f88  mov     rdx, rax
0x180022f8b  lea     rcx, [rsp+158h+string]
0x180022f90  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x180022f95  nop
0x180022f96  mov     rdx, rax
0x180022f99  lea     rcx, [rsp+158h+var_110]; newString
0x180022f9e  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180022fa3  nop
0x180022fa4  mov     rcx, [rsp+158h+string]; string
0x180022fa9  call    cs:__imp_WindowsDeleteString
0x180022faf  mov     [rsp+158h+string], 0
0x180022fb8  mov     rcx, [rsp+158h+newString]; string
0x180022fbd  call    cs:__imp_WindowsDeleteString
0x180022fc3  test    cs:ConnectedStorageEnableBits, 8
0x180022fca  jz      short loc_180022FFB
0x180022fcc  xor     edx, edx; length
0x180022fce  mov     rcx, [rsp+158h+var_110]; string
0x180022fd3  call    cs:__imp_WindowsGetStringRawBuffer
0x180022fd9  mov     rdi, rax
0x180022fdc  xor     edx, edx; length
0x180022fde  mov     rcx, [rsp+158h+var_108]; string
0x180022fe3  call    cs:__imp_WindowsGetStringRawBuffer
0x180022fe9  mov     r9, rdi
0x180022fec  mov     r8, rax
0x180022fef  lea     rdx, ConnectedStorageServiceGetQuotaStart
0x180022ff6  call    McTemplateU0zz_EventWriteTransfer
0x180022ffb  mov     al, byte ptr [rsp+158h+var_118]
0x180022fff  mov     [rsp+158h+var_120], al; bool
0x180023003  mov     eax, [r15+18h]
0x180023007  mov     dword ptr [rsp+158h+var_128], eax; unsigned int
0x18002300b  mov     [rsp+158h+var_130], r15; struct ConnectedStorage::SimpleHStringWrapper *
0x180023010  lea     rax, [rsp+158h+var_110]
0x180023015  mov     [rsp+158h+var_138], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x18002301a  lea     r9, [rsp+158h+var_108]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002301f  lea     r8, [rsp+158h+var_100]; struct ConnectedStorage::SimpleHStringWrapper *
0x180023024  lea     rdx, [rsp+158h+var_F8]; struct ConnectedStorage::SimpleHStringWrapper *
0x180023029  lea     rcx, [rsp+158h+var_C0]; this
0x180023031  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x180023036  nop
0x180023037  mov     rax, qword ptr [rsp+158h+var_90]
0x18002303f  movups  xmm0, xmmword ptr [rax]
0x180023042  movdqu  xmmword ptr [rsp+158h+newString], xmm0
0x180023048  mov     rax, [rsp+158h+var_D8]
0x180023050  mov     [rsp+158h+var_130], rax; struct _GUID *
0x180023055  lea     rax, [rsp+158h+var_C0]
0x18002305d  mov     [rsp+158h+var_138], rax; struct ConnectedStorage::ContextDesc *
0x180023062  mov     r9, r13; unsigned __int64
0x180023065  mov     r8, r15; struct ConnectedStorage::CallerInfo *
0x180023068  lea     rdx, [rsp+158h+newString]; struct _GUID
0x18002306d  mov     rcx, rbx; this
0x180023070  call    ?GetQuota@Service@ConnectedStorage@@QEAAXU_GUID@@AEBVCallerInfo@2@_KAEBVContextDesc@2@PEAUIStorageQuotaHandler@@@Z; ConnectedStorage::Service::GetQuota(_GUID,ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,IStorageQuotaHandler *)
0x180023075  nop
0x180023076  lea     rcx, [rsp+158h+var_C0]; this
0x18002307e  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180023083  nop
0x180023084  test    rbx, rbx
0x180023087  jz      short loc_18002308F
0x180023089  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x18002308e  nop
0x18002308f  jmp     short loc_180023095
0x180023091  jmp     short loc_180023095
0x180023093  jmp     short $+2
0x180023095  mov     dil, byte ptr [rsp+158h+var_118]
0x18002309a  xor     edx, edx; length
0x18002309c  mov     rcx, [rsp+158h+var_108]; string
0x1800230a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800230a7  mov     rbx, rax
0x1800230aa  xor     edx, edx; length
0x1800230ac  mov     rcx, [rsp+158h+var_110]; string
0x1800230b1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800230b7  mov     rcx, qword ptr [rsp+158h+var_90]
0x1800230bf  mov     [rsp+158h+var_138], rcx; unsigned int
0x1800230c4  mov     r9d, dword ptr [rsp+158h+var_118+4]; bool
0x1800230c9  mov     r8b, dil; unsigned __int16 *
0x1800230cc  mov     rdx, rbx; unsigned __int16 *
0x1800230cf  mov     rcx, rax; this
0x1800230d2  call    ?EventWriteGetQuota@ConnectedStorage@@YAXQEBG0_NIQEBU_GUID@@@Z; ConnectedStorage::EventWriteGetQuota(ushort const * const,ushort const * const,bool,uint,_GUID const * const)
0x1800230d7  nop
0x1800230d8  jmp     short $+2
0x1800230da  test    cs:ConnectedStorageEnableBits, 8
0x1800230e1  jz      short loc_1800230F4
0x1800230e3  mov     r8d, dword ptr [rsp+158h+var_118+4]
0x1800230e8  lea     rdx, ConnectedStorageServiceGetQuotaStop
0x1800230ef  call    McTemplateU0d_EventWriteTransfer
0x1800230f4  mov     ecx, dword ptr [rsp+158h+var_118+4]; this
0x1800230f8  call    ?FilterHresult@ConnectedStorage@@YAJJ@Z; ConnectedStorage::FilterHresult(long)
0x1800230fd  mov     ebx, eax
0x1800230ff  mov     rcx, [rsp+158h+var_110]; string
0x180023104  call    cs:__imp_WindowsDeleteString
0x18002310a  mov     [rsp+158h+var_110], 0
0x180023113  mov     rcx, [rsp+158h+var_108]; string
0x180023118  call    cs:__imp_WindowsDeleteString
0x18002311e  mov     [rsp+158h+var_108], 0
0x180023127  mov     rcx, [rsp+158h+var_100]; string
0x18002312c  call    cs:__imp_WindowsDeleteString
0x180023132  mov     [rsp+158h+var_100], 0
0x18002313b  mov     rcx, [rsp+158h+var_F8]; string
0x180023140  call    cs:__imp_WindowsDeleteString
0x180023146  mov     eax, ebx
0x180023148  mov     rcx, [rsp+158h+var_48]
0x180023150  xor     rcx, rsp; StackCookie
0x180023153  call    __security_check_cookie
0x180023158  add     rsp, 128h
0x18002315f  pop     r15
0x180023161  pop     r14
0x180023163  pop     r13
0x180023165  pop     r12
0x180023167  pop     rdi
0x180023168  pop     rbx
0x180023169  retn
```
