# ConnectedStorage::StorageService::Delete(HSTRING__ *,unsigned __int64,HSTRING__ *,IStorageOperationHandler *,_GUID)

- ea: `0x180022630`
- end: `0x1800229f8`
- name: `?Delete@StorageService@ConnectedStorage@@MEAAJPEAUHSTRING__@@_K0PEAUIStorageOperationHandler@@U_GUID@@@Z`
- size: `968`
- prototype: `__int64 __fastcall(ConnectedStorage::StorageService *this, HSTRING, char *, HSTRING, struct IStorageOperationHandler *, struct _GUID *)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000ca18`
- `0x18000cb9c`
- `0x180011bd0`
- `0x1800125ec`
- `0x180012ed8`
- `0x180013e1c`
- `0x1800144a8`
- `0x180014a88`
- `0x180015008`
- `0x1800160c8`
- `0x1800170d4`
- `0x18001d614`
- `0x180020e68`
- `0x180022630`
- `0x180022dec`
- `0x1800235c0`
- `0x1800268dc`
- `0x18004ae14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002297f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022993`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800229a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800229bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800229cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002297f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022993`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800229a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800229bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800229cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022916`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022916`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022926`

## string_xrefs

- `0x1800226f0`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall ConnectedStorage::StorageService::Delete(
        ConnectedStorage::StorageService *this,
        HSTRING a2,
        char *a3,
        HSTRING a4,
        struct IStorageOperationHandler *a5,
        struct _GUID *a6)
{
  char *v10; // r8
  const unsigned __int16 *v11; // r8
  ConnectedStorage::Service *v12; // rbx
  unsigned int *v13; // r15
  HSTRING *AddressOf; // rsi
  HSTRING *v15; // rdi
  HSTRING *v16; // rax
  __int64 v17; // rax
  PCWSTR StringRawBuffer; // rsi
  unsigned int v19; // edi
  unsigned int v20; // eax
  int v21; // ecx
  unsigned __int8 v22; // di
  bool v23; // si
  const unsigned __int16 *v24; // rbx
  ConnectedStorage *v25; // rax
  const unsigned __int16 *v26; // r8
  int v27; // edx
  __int64 v28; // rcx
  unsigned int v29; // ebx
  HSTRING *v31; // [rsp+20h] [rbp-148h]
  struct _GUID *v32; // [rsp+30h] [rbp-138h]
  bool v33; // [rsp+40h] [rbp-128h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-124h]
  HSTRING v35; // [rsp+48h] [rbp-120h] BYREF
  HSTRING v36; // [rsp+50h] [rbp-118h] BYREF
  HSTRING v37; // [rsp+58h] [rbp-110h] BYREF
  HSTRING v38; // [rsp+60h] [rbp-108h] BYREF
  HSTRING v39; // [rsp+68h] [rbp-100h] BYREF
  HSTRING string[2]; // [rsp+70h] [rbp-F8h] BYREF
  HSTRING newString[2]; // [rsp+80h] [rbp-E8h] BYREF
  struct _GUID *v42; // [rsp+90h] [rbp-D8h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+98h] [rbp-D0h] BYREF
  _BYTE v44[48]; // [rsp+A8h] [rbp-C0h] BYREF
  unsigned int v45[2]; // [rsp+D8h] [rbp-90h]
  _DWORD v46[16]; // [rsp+E0h] [rbp-88h] BYREF

  try
  {
    v42 = (struct _GUID *)a5;
    *(_QWORD *)v45 = a6;
    v37 = 0;
    v39 = 0;
    v38 = 0;
    v36 = 0;
    v35 = 0;
    v33 = 0;
    v34 = 0;
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock(
        (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
        (struct ConnectedStorage::Mutex *)&CriticalSection,
        v10);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v11);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v12 = qword_1800C0858;
    lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
    v13 = (unsigned int *)ConnectedStorage::CallerInfoWithResult::Get(
                            (ConnectedStorage::StorageService *)((char *)this + 64),
                            (__int64)a2,
                            a3);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(string, a2);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v37);
    WindowsDeleteString(string[0]);
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v36);
    v15 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v38);
    v16 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v39);
    ConnectedStorage::Service::GetUserInfoFromUserContextToken(v12, (unsigned __int64)a3, 1, v16, v15, AddressOf, &v33);
    v17 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(newString, a4);
    ConnectedStorage::NormalizeScid(string, v17);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v35);
    WindowsDeleteString(string[0]);
    string[0] = 0;
    WindowsDeleteString(newString[0]);
    if ( (ConnectedStorageEnableBits & 8) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v37, 0);
      v19 = (unsigned int)WindowsGetStringRawBuffer(v36, 0);
      v20 = (unsigned int)WindowsGetStringRawBuffer(v35, 0);
      McTemplateU0zzz_EventWriteTransfer(
        v21,
        (unsigned int)ConnectedStorageServiceDeleteStart,
        v20,
        v19,
        (__int64)StringRawBuffer);
    }
    ConnectedStorage::ContextDesc::ContextDesc(
      (ConnectedStorage::ContextDesc *)v44,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v39,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v38,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v36,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v35,
      (const struct ConnectedStorage::SimpleHStringWrapper *)v13,
      v13[6],
      v33);
    *(_OWORD *)newString = **(_OWORD **)v45;
    ConnectedStorage::Service::DeleteContainer(
      v12,
      (struct _GUID *)newString,
      (const struct ConnectedStorage::CallerInfo *)v13,
      (unsigned __int64)a3,
      (const struct ConnectedStorage::ContextDesc *)v44,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v37,
      (struct IStorageOperationHandler *)v42);
    ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v44);
    if ( v12 )
      ConnectedStorage::Service::ReturnInstance();
  }
  catch ( ConnectedStorage::ComError v46 )
  {
    v34 = v46[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v46);
  }
  catch ( std::bad_alloc )
  {
    v34 = -2147024882;
  }
  catch ( ... )
  {
    v34 = -2147467259;
  }
  v22 = (unsigned __int8)WindowsGetStringRawBuffer(v37, 0);
  v23 = v33;
  v24 = WindowsGetStringRawBuffer(v36, 0);
  v25 = (ConnectedStorage *)WindowsGetStringRawBuffer(v35, 0);
  LODWORD(v31) = v34;
  LOBYTE(v26) = v23;
  ConnectedStorage::EventWriteDelete(v25, v24, v26, v22, (const unsigned __int16 *const)v31, v45[0], v32);
  if ( (ConnectedStorageEnableBits & 8) != 0 )
    McTemplateU0d_EventWriteTransfer(v28, ConnectedStorageServiceDeleteStop, v34);
  v29 = ConnectedStorage::FilterHresult((ConnectedStorage *)v34, v27);
  WindowsDeleteString(v35);
  v35 = 0;
  WindowsDeleteString(v36);
  v36 = 0;
  WindowsDeleteString(v38);
  v38 = 0;
  WindowsDeleteString(v39);
  v39 = 0;
  WindowsDeleteString(v37);
  return v29;
}

```

## disassembly

```asm
0x180022630  push    rbx
0x180022632  push    rsi
0x180022633  push    rdi
0x180022634  push    r12
0x180022636  push    r13
0x180022638  push    r15
0x18002263a  sub     rsp, 138h
0x180022641  mov     rax, cs:__security_cookie
0x180022648  xor     rax, rsp
0x18002264b  mov     [rsp+168h+var_48], rax
0x180022653  mov     r12, r9
0x180022656  mov     r13, r8
0x180022659  mov     rsi, rdx
0x18002265c  mov     rdi, rcx
0x18002265f  mov     rax, [rsp+168h+arg_20]
0x180022667  mov     [rsp+168h+var_D8], rax
0x18002266f  mov     rax, [rsp+168h+arg_28]
0x180022677  mov     qword ptr [rsp+168h+var_90], rax
0x18002267f  mov     [rsp+168h+var_110], 0
0x180022688  mov     [rsp+168h+var_100], 0
0x180022691  mov     [rsp+168h+var_108], 0
0x18002269a  mov     [rsp+168h+var_118], 0
0x1800226a3  mov     [rsp+168h+var_120], 0
0x1800226ac  mov     byte ptr [rsp+168h+var_128], 0
0x1800226b1  mov     dword ptr [rsp+168h+var_128+4], 0
0x1800226b9  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x1800226c0  jnz     short loc_180022729
0x1800226c2  or      edx, 0FFFFFFFFh; unsigned int
0x1800226c5  lea     rcx, qword_1800C0998; this
0x1800226cc  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x1800226d1  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x1800226d8  lea     rcx, [rsp+168h+lpCriticalSection]; this
0x1800226e0  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800226e5  nop
0x1800226e6  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x1800226ec  test    eax, eax
0x1800226ee  jnz     short loc_180022701
0x1800226f0  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x1800226f7  mov     ecx, 80004005h; this
0x1800226fc  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180022701  inc     eax
0x180022703  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180022709  mov     edx, 2
0x18002270e  mov     rcx, cs:qword_1800C0858
0x180022715  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x18002271a  nop
0x18002271b  mov     rcx, [rsp+168h+lpCriticalSection]; lpCriticalSection
0x180022723  call    cs:__imp_LeaveCriticalSection
0x180022729  mov     rbx, cs:qword_1800C0858
0x180022730  mov     [rsp+168h+lpCriticalSection], rbx
0x180022738  lea     rcx, [rdi+40h]; this
0x18002273c  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x180022741  mov     r15, rax
0x180022744  mov     rdx, rsi; string
0x180022747  lea     rcx, [rsp+168h+string]; newString
0x18002274c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x180022751  nop
0x180022752  mov     rdx, rax
0x180022755  lea     rcx, [rsp+168h+var_110]; newString
0x18002275a  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18002275f  nop
0x180022760  mov     rcx, [rsp+168h+string]; string
0x180022765  call    cs:__imp_WindowsDeleteString
0x18002276b  lea     rcx, [rsp+168h+var_118]; this
0x180022770  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180022775  mov     rsi, rax
0x180022778  lea     rcx, [rsp+168h+var_108]; this
0x18002277d  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180022782  mov     rdi, rax
0x180022785  lea     rcx, [rsp+168h+var_100]; this
0x18002278a  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002278f  lea     rcx, [rsp+168h+var_128]
0x180022794  mov     [rsp+168h+var_138], rcx; bool *
0x180022799  mov     [rsp+168h+var_140], rsi; HSTRING *
0x18002279e  mov     [rsp+168h+var_148], rdi; HSTRING *
0x1800227a3  mov     r9, rax; HSTRING *
0x1800227a6  mov     r8b, 1; bool
0x1800227a9  mov     rdx, r13; unsigned __int64
0x1800227ac  mov     rcx, rbx; this
0x1800227af  call    ?GetUserInfoFromUserContextToken@Service@ConnectedStorage@@QEAAX_K_NPEAPEAUHSTRING__@@22PEA_N@Z; ConnectedStorage::Service::GetUserInfoFromUserContextToken(unsigned __int64,bool,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,bool *)
0x1800227b4  mov     rdx, r12; string
0x1800227b7  lea     rcx, [rsp+168h+newString]; newString
0x1800227bf  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x1800227c4  nop
0x1800227c5  mov     rdx, rax
0x1800227c8  lea     rcx, [rsp+168h+string]
0x1800227cd  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x1800227d2  nop
0x1800227d3  mov     rdx, rax
0x1800227d6  lea     rcx, [rsp+168h+var_120]; newString
0x1800227db  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x1800227e0  nop
0x1800227e1  mov     rcx, [rsp+168h+string]; string
0x1800227e6  call    cs:__imp_WindowsDeleteString
0x1800227ec  mov     [rsp+168h+string], 0
0x1800227f5  mov     rcx, [rsp+168h+newString]; string
0x1800227fd  call    cs:__imp_WindowsDeleteString
0x180022803  test    cs:ConnectedStorageEnableBits, 8
0x18002280a  jz      short loc_180022850
0x18002280c  xor     edx, edx; length
0x18002280e  mov     rcx, [rsp+168h+var_110]; string
0x180022813  call    cs:__imp_WindowsGetStringRawBuffer
0x180022819  mov     rsi, rax
0x18002281c  xor     edx, edx; length
0x18002281e  mov     rcx, [rsp+168h+var_118]; string
0x180022823  call    cs:__imp_WindowsGetStringRawBuffer
0x180022829  mov     rdi, rax
0x18002282c  xor     edx, edx; length
0x18002282e  mov     rcx, [rsp+168h+var_120]; string
0x180022833  call    cs:__imp_WindowsGetStringRawBuffer
0x180022839  mov     [rsp+168h+var_148], rsi
0x18002283e  mov     r9, rdi
0x180022841  mov     r8, rax
0x180022844  lea     rdx, ConnectedStorageServiceDeleteStart
0x18002284b  call    McTemplateU0zzz_EventWriteTransfer
0x180022850  mov     al, byte ptr [rsp+168h+var_128]
0x180022854  mov     [rsp+168h+var_130], al; bool
0x180022858  mov     eax, [r15+18h]
0x18002285c  mov     dword ptr [rsp+168h+var_138], eax; unsigned int
0x180022860  mov     [rsp+168h+var_140], r15; struct ConnectedStorage::SimpleHStringWrapper *
0x180022865  lea     rax, [rsp+168h+var_120]
0x18002286a  mov     [rsp+168h+var_148], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x18002286f  lea     r9, [rsp+168h+var_118]; struct ConnectedStorage::SimpleHStringWrapper *
0x180022874  lea     r8, [rsp+168h+var_108]; struct ConnectedStorage::SimpleHStringWrapper *
0x180022879  lea     rdx, [rsp+168h+var_100]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002287e  lea     rcx, [rsp+168h+var_C0]; this
0x180022886  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x18002288b  nop
0x18002288c  mov     rax, qword ptr [rsp+168h+var_90]
0x180022894  movups  xmm0, xmmword ptr [rax]
0x180022897  movdqu  xmmword ptr [rsp+168h+newString], xmm0
0x1800228a0  mov     rax, [rsp+168h+var_D8]
0x1800228a8  mov     [rsp+168h+var_138], rax; struct _GUID *
0x1800228ad  lea     rax, [rsp+168h+var_110]
0x1800228b2  mov     [rsp+168h+var_140], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x1800228b7  lea     rax, [rsp+168h+var_C0]
0x1800228bf  mov     [rsp+168h+var_148], rax; struct ConnectedStorage::ContextDesc *
0x1800228c4  mov     r9, r13; unsigned __int64
0x1800228c7  mov     r8, r15; struct ConnectedStorage::CallerInfo *
0x1800228ca  lea     rdx, [rsp+168h+newString]; struct _GUID
0x1800228d2  mov     rcx, rbx; this
0x1800228d5  call    ?DeleteContainer@Service@ConnectedStorage@@QEAAXU_GUID@@AEBVCallerInfo@2@_KAEBVContextDesc@2@AEBVSimpleHStringWrapper@2@PEAUIStorageOperationHandler@@@Z; ConnectedStorage::Service::DeleteContainer(_GUID,ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &,IStorageOperationHandler *)
0x1800228da  nop
0x1800228db  lea     rcx, [rsp+168h+var_C0]; this
0x1800228e3  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x1800228e8  nop
0x1800228e9  test    rbx, rbx
0x1800228ec  jz      short loc_1800228F4
0x1800228ee  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x1800228f3  nop
0x1800228f4  jmp     short loc_1800228FA
0x1800228f6  jmp     short loc_1800228FA
0x1800228f8  jmp     short $+2
0x1800228fa  xor     edx, edx; length
0x1800228fc  mov     rcx, [rsp+168h+var_110]; string
0x180022901  call    cs:__imp_WindowsGetStringRawBuffer
0x180022907  mov     rdi, rax
0x18002290a  mov     sil, byte ptr [rsp+168h+var_128]
0x18002290f  xor     edx, edx; length
0x180022911  mov     rcx, [rsp+168h+var_118]; string
0x180022916  call    cs:__imp_WindowsGetStringRawBuffer
0x18002291c  mov     rbx, rax
0x18002291f  xor     edx, edx; length
0x180022921  mov     rcx, [rsp+168h+var_120]; string
0x180022926  call    cs:__imp_WindowsGetStringRawBuffer
0x18002292c  mov     rcx, qword ptr [rsp+168h+var_90]
0x180022934  mov     [rsp+168h+var_140], rcx; unsigned int
0x180022939  mov     ecx, dword ptr [rsp+168h+var_128+4]
0x18002293d  mov     dword ptr [rsp+168h+var_148], ecx; unsigned __int16 *
0x180022941  mov     r9, rdi; bool
0x180022944  mov     r8b, sil; unsigned __int16 *
0x180022947  mov     rdx, rbx; unsigned __int16 *
0x18002294a  mov     rcx, rax; this
0x18002294d  call    ?EventWriteDelete@ConnectedStorage@@YAXQEBG0_N0IQEBU_GUID@@@Z; ConnectedStorage::EventWriteDelete(ushort const * const,ushort const * const,bool,ushort const * const,uint,_GUID const * const)
0x180022952  nop
0x180022953  jmp     short $+2
0x180022955  test    cs:ConnectedStorageEnableBits, 8
0x18002295c  jz      short loc_18002296F
0x18002295e  mov     r8d, dword ptr [rsp+168h+var_128+4]
0x180022963  lea     rdx, ConnectedStorageServiceDeleteStop
0x18002296a  call    McTemplateU0d_EventWriteTransfer
0x18002296f  mov     ecx, dword ptr [rsp+168h+var_128+4]; this
0x180022973  call    ?FilterHresult@ConnectedStorage@@YAJJ@Z; ConnectedStorage::FilterHresult(long)
0x180022978  mov     ebx, eax
0x18002297a  mov     rcx, [rsp+168h+var_120]; string
0x18002297f  call    cs:__imp_WindowsDeleteString
0x180022985  mov     [rsp+168h+var_120], 0
0x18002298e  mov     rcx, [rsp+168h+var_118]; string
0x180022993  call    cs:__imp_WindowsDeleteString
0x180022999  mov     [rsp+168h+var_118], 0
0x1800229a2  mov     rcx, [rsp+168h+var_108]; string
0x1800229a7  call    cs:__imp_WindowsDeleteString
0x1800229ad  mov     [rsp+168h+var_108], 0
0x1800229b6  mov     rcx, [rsp+168h+var_100]; string
0x1800229bb  call    cs:__imp_WindowsDeleteString
0x1800229c1  mov     [rsp+168h+var_100], 0
0x1800229ca  mov     rcx, [rsp+168h+var_110]; string
0x1800229cf  call    cs:__imp_WindowsDeleteString
0x1800229d5  mov     eax, ebx
0x1800229d7  mov     rcx, [rsp+168h+var_48]
0x1800229df  xor     rcx, rsp; StackCookie
0x1800229e2  call    __security_check_cookie
0x1800229e7  add     rsp, 138h
0x1800229ee  pop     r15
0x1800229f0  pop     r13
0x1800229f2  pop     r12
0x1800229f4  pop     rdi
0x1800229f5  pop     rsi
0x1800229f6  pop     rbx
0x1800229f7  retn
```
