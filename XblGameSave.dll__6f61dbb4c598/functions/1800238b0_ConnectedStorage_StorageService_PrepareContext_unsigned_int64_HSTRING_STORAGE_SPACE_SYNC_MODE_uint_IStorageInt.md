# ConnectedStorage::StorageService::PrepareContext(unsigned __int64,HSTRING__ *,STORAGE_SPACE_SYNC_MODE,uint,IStorageInterruptHandler *,IStorageSpaceHandler *,_GUID)

- ea: `0x1800238b0`
- end: `0x180023c23`
- name: `?PrepareContext@StorageService@ConnectedStorage@@MEAAJ_KPEAUHSTRING__@@W4STORAGE_SPACE_SYNC_MODE@@IPEAUIStorageInterruptHandler@@PEAUIStorageSpaceHandler@@U_GUID@@@Z`
- size: `883`
- prototype: `int __high(unsigned __int64, HSTRING, enum STORAGE_SPACE_SYNC_MODE, unsigned int, struct IStorageInterruptHandler *, struct IStorageSpaceHandler *, struct _GUID)`
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x180011bd0`
- `0x1800125ec`
- `0x180012ed8`
- `0x180013e1c`
- `0x180014a88`
- `0x180015008`
- `0x180015b14`
- `0x1800160c8`
- `0x1800170d4`
- `0x18001dafc`
- `0x180020e68`
- `0x180022dec`
- `0x1800235c0`
- `0x1800238b0`
- `0x18004ae14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023983`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023983`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023b99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023b99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023b62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023b62`

## string_xrefs

- `0x180023c10`: `The service has shutdown.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ConnectedStorage::StorageService::PrepareContext(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        int a4,
        __int64 a5,
        HSTRING a6,
        __int64 a7,
        __int64 a8)
{
  char *v11; // r8
  const unsigned __int16 *v12; // r8
  ConnectedStorage::Service *v13; // rbx
  HSTRING *AddressOf; // r14
  HSTRING *v15; // rdi
  HSTRING *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  char *v19; // r8
  unsigned int *v20; // rdi
  bool v21; // di
  const unsigned __int16 *StringRawBuffer; // rbx
  ConnectedStorage *v23; // rax
  const unsigned __int16 *v24; // r8
  int v25; // edx
  HSTRING *v27; // [rsp+28h] [rbp-130h]
  bool v28; // [rsp+40h] [rbp-118h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-114h]
  HSTRING v30; // [rsp+48h] [rbp-110h] BYREF
  HSTRING v31; // [rsp+50h] [rbp-108h] BYREF
  HSTRING v32; // [rsp+58h] [rbp-100h] BYREF
  HSTRING v33; // [rsp+60h] [rbp-F8h] BYREF
  HSTRING v34; // [rsp+68h] [rbp-F0h] BYREF
  struct _GUID *v35; // [rsp+70h] [rbp-E8h]
  HSTRING newString[2]; // [rsp+80h] [rbp-D8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+90h] [rbp-C8h] BYREF
  _BYTE v38[48]; // [rsp+A0h] [rbp-B8h] BYREF
  unsigned int v39[4]; // [rsp+D0h] [rbp-88h]
  _DWORD v40[16]; // [rsp+E0h] [rbp-78h] BYREF

  try
  {
    LODWORD(v35) = a4;
    *(_QWORD *)v39 = a8;
    v34 = 0;
    v33 = 0;
    v32 = 0;
    v31 = 0;
    v28 = 0;
    v29 = 0;
    if ( !ConnectedStorage::gShutdown )
    {
      ConnectedStorage::Event::Wait((ConnectedStorage::Event *)&qword_1800C0998, 0xFFFFFFFF);
      ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, &CriticalSection, v11);
      if ( !ConnectedStorage::gServiceRef )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80004005LL, (int)L"The service has shutdown.", v12);
      ++ConnectedStorage::gServiceRef;
      ConnectedStorage::Service::AddServiceActivity(qword_1800C0858, 2);
      LeaveCriticalSection(lpCriticalSection[0]);
    }
    v13 = qword_1800C0858;
    lpCriticalSection[0] = (LPCRITICAL_SECTION)qword_1800C0858;
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v31);
    v15 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v32);
    v16 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v33);
    ConnectedStorage::Service::GetUserInfoFromUserContextToken(v13, a2, 0, v16, v15, AddressOf, &v28);
    v17 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(newString, a3);
    ConnectedStorage::NormalizeScid(&v30, v17);
    ConnectedStorage::SimpleHStringWrapper::operator=(&v34);
    WindowsDeleteString(v30);
    v30 = 0;
    WindowsDeleteString(newString[0]);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    if ( *(HSTRING *)(a1 + 136) != a6 )
    {
      v30 = a6;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&v30);
      v30 = *(HSTRING *)(a1 + 136);
      *(_QWORD *)(a1 + 136) = a6;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    }
    if ( a1 != -24 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    v20 = (unsigned int *)ConnectedStorage::CallerInfoWithResult::Get(
                            (ConnectedStorage::CallerInfoWithResult *)(a1 + 64),
                            v18,
                            v19);
    ConnectedStorage::ContextDesc::ContextDesc(
      (ConnectedStorage::ContextDesc *)v38,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v33,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v32,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v31,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v34,
      (const struct ConnectedStorage::SimpleHStringWrapper *)v20,
      v20[6],
      v28);
    *(_OWORD *)newString = **(_OWORD **)v39;
    LODWORD(v27) = (_DWORD)v35;
    ConnectedStorage::Service::PrepareContext(v13, newString, v20, a2, v38);
    ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v38);
    if ( v13 )
      ConnectedStorage::Service::ReturnInstance();
  }
  catch ( ConnectedStorage::ComError v40 )
  {
    v29 = v40[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v40);
  }
  catch ( std::bad_alloc )
  {
    v29 = -2147024882;
  }
  catch ( ... )
  {
    v29 = -2147467259;
  }
  v21 = v28;
  StringRawBuffer = WindowsGetStringRawBuffer(v31, 0);
  v23 = (ConnectedStorage *)WindowsGetStringRawBuffer(v34, 0);
  LOBYTE(v24) = v21;
  ConnectedStorage::EventWritePrepareContext(v23, StringRawBuffer, v24, v29, v39[0], (const struct _GUID *const)v27);
  LODWORD(StringRawBuffer) = ConnectedStorage::FilterHresult((ConnectedStorage *)v29, v25);
  WindowsDeleteString(v31);
  v31 = 0;
  WindowsDeleteString(v32);
  v32 = 0;
  WindowsDeleteString(v33);
  v33 = 0;
  WindowsDeleteString(v34);
  return (unsigned int)StringRawBuffer;
}

```

## disassembly

```asm
0x1800238b0  mov     [rsp+arg_18], rbx
0x1800238b5  push    rdi
0x1800238b6  push    r12
0x1800238b8  push    r13
0x1800238ba  push    r14
0x1800238bc  push    r15
0x1800238be  sub     rsp, 130h
0x1800238c5  mov     rax, cs:__security_cookie
0x1800238cc  xor     rax, rsp
0x1800238cf  mov     [rsp+158h+var_38], rax
0x1800238d7  mov     dword ptr [rsp+158h+var_E8], r9d
0x1800238dc  mov     r12, r8
0x1800238df  mov     r13, rdx
0x1800238e2  mov     r15, rcx
0x1800238e5  mov     rax, [rsp+158h+arg_38]
0x1800238ed  mov     qword ptr [rsp+158h+var_88], rax
0x1800238f5  mov     [rsp+158h+var_F0], 0
0x1800238fe  mov     [rsp+158h+var_F8], 0
0x180023907  mov     [rsp+158h+var_100], 0
0x180023910  mov     [rsp+158h+var_108], 0
0x180023919  mov     byte ptr [rsp+158h+var_118], 0
0x18002391e  mov     dword ptr [rsp+158h+var_118+4], 0
0x180023926  cmp     cs:?gShutdown@ConnectedStorage@@3_NA, 0; bool ConnectedStorage::gShutdown
0x18002392d  jnz     short loc_180023989
0x18002392f  or      edx, 0FFFFFFFFh; unsigned int
0x180023932  lea     rcx, qword_1800C0998; this
0x180023939  call    ?Wait@Event@ConnectedStorage@@QEAA_NK@Z; ConnectedStorage::Event::Wait(ulong)
0x18002393e  lea     rdx, CriticalSection; struct ConnectedStorage::Mutex *
0x180023945  lea     rcx, [rsp+158h+lpCriticalSection]; this
0x18002394d  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180023952  nop
0x180023953  mov     eax, cs:?gServiceRef@ConnectedStorage@@3IA; uint ConnectedStorage::gServiceRef
0x180023959  test    eax, eax
0x18002395b  jz      loc_180023C10
0x180023961  inc     eax
0x180023963  mov     cs:?gServiceRef@ConnectedStorage@@3IA, eax; uint ConnectedStorage::gServiceRef
0x180023969  mov     edx, 2
0x18002396e  mov     rcx, cs:qword_1800C0858
0x180023975  call    ?AddServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z; ConnectedStorage::Service::AddServiceActivity(ConnectedStorage::Service::ServiceActivity)
0x18002397a  nop
0x18002397b  mov     rcx, [rsp+158h+lpCriticalSection]; lpCriticalSection
0x180023983  call    cs:__imp_LeaveCriticalSection
0x180023989  mov     rbx, cs:qword_1800C0858
0x180023990  mov     [rsp+158h+lpCriticalSection], rbx
0x180023998  lea     rcx, [rsp+158h+var_108]; this
0x18002399d  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x1800239a2  mov     r14, rax
0x1800239a5  lea     rcx, [rsp+158h+var_100]; this
0x1800239aa  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x1800239af  mov     rdi, rax
0x1800239b2  lea     rcx, [rsp+158h+var_F8]; this
0x1800239b7  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x1800239bc  lea     rcx, [rsp+158h+var_118]
0x1800239c1  mov     [rsp+158h+var_128], rcx; bool *
0x1800239c6  mov     [rsp+158h+var_130], r14; HSTRING *
0x1800239cb  mov     [rsp+158h+var_138], rdi; HSTRING *
0x1800239d0  mov     r9, rax; HSTRING *
0x1800239d3  xor     r8d, r8d; bool
0x1800239d6  mov     rdx, r13; unsigned __int64
0x1800239d9  mov     rcx, rbx; this
0x1800239dc  call    ?GetUserInfoFromUserContextToken@Service@ConnectedStorage@@QEAAX_K_NPEAPEAUHSTRING__@@22PEA_N@Z; ConnectedStorage::Service::GetUserInfoFromUserContextToken(unsigned __int64,bool,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,bool *)
0x1800239e1  mov     rdx, r12; string
0x1800239e4  lea     rcx, [rsp+158h+newString]; newString
0x1800239ec  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(HSTRING__ *)
0x1800239f1  nop
0x1800239f2  mov     rdx, rax
0x1800239f5  lea     rcx, [rsp+158h+var_110]
0x1800239fa  call    ?NormalizeScid@ConnectedStorage@@YA?AVSimpleHStringWrapper@1@AEBV21@@Z; ConnectedStorage::NormalizeScid(ConnectedStorage::SimpleHStringWrapper const &)
0x1800239ff  nop
0x180023a00  mov     rdx, rax
0x180023a03  lea     rcx, [rsp+158h+var_F0]; newString
0x180023a08  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180023a0d  nop
0x180023a0e  mov     rcx, [rsp+158h+var_110]; string
0x180023a13  call    cs:__imp_WindowsDeleteString
0x180023a19  mov     [rsp+158h+var_110], 0
0x180023a22  mov     rcx, [rsp+158h+newString]; string
0x180023a2a  call    cs:__imp_WindowsDeleteString
0x180023a30  lea     rdi, [r15+18h]
0x180023a34  mov     rcx, rdi; lpCriticalSection
0x180023a37  call    cs:__imp_EnterCriticalSection
0x180023a3d  mov     r14, [rsp+158h+arg_28]
0x180023a45  cmp     [r15+88h], r14
0x180023a4c  jz      short loc_180023A7A
0x180023a4e  mov     [rsp+158h+var_110], r14
0x180023a53  lea     rcx, [rsp+158h+var_110]
0x180023a58  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x180023a5d  mov     rax, [r15+88h]
0x180023a64  mov     [rsp+158h+var_110], rax
0x180023a69  mov     [r15+88h], r14
0x180023a70  lea     rcx, [rsp+158h+var_110]
0x180023a75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023a7a  test    rdi, rdi
0x180023a7d  jz      short loc_180023A88
0x180023a7f  mov     rcx, rdi; lpCriticalSection
0x180023a82  call    cs:__imp_LeaveCriticalSection
0x180023a88  lea     rcx, [r15+40h]; this
0x180023a8c  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x180023a91  mov     rdi, rax
0x180023a94  mov     r14b, [rsp+158h+arg_20]
0x180023a9c  and     r14b, 1
0x180023aa0  mov     cl, byte ptr [rsp+158h+var_118]
0x180023aa4  mov     [rsp+158h+var_120], cl; bool
0x180023aa8  mov     ecx, [rax+18h]
0x180023aab  mov     dword ptr [rsp+158h+var_128], ecx; unsigned int
0x180023aaf  mov     [rsp+158h+var_130], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x180023ab4  lea     rax, [rsp+158h+var_F0]
0x180023ab9  mov     [rsp+158h+var_138], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x180023abe  lea     r9, [rsp+158h+var_108]; struct ConnectedStorage::SimpleHStringWrapper *
0x180023ac3  lea     r8, [rsp+158h+var_100]; struct ConnectedStorage::SimpleHStringWrapper *
0x180023ac8  lea     rdx, [rsp+158h+var_F8]; struct ConnectedStorage::SimpleHStringWrapper *
0x180023acd  lea     rcx, [rsp+158h+var_B8]; this
0x180023ad5  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x180023ada  nop
0x180023adb  mov     rax, qword ptr [rsp+158h+var_88]
0x180023ae3  movups  xmm0, xmmword ptr [rax]
0x180023ae6  movdqu  xmmword ptr [rsp+158h+newString], xmm0
0x180023aef  mov     rax, [rsp+158h+arg_30]
0x180023af7  mov     qword ptr [rsp+158h+var_120], rax
0x180023afc  mov     byte ptr [rsp+158h+var_128], r14b
0x180023b01  mov     eax, dword ptr [rsp+158h+var_E8]
0x180023b05  mov     dword ptr [rsp+158h+var_130], eax; struct _GUID *
0x180023b09  lea     rax, [rsp+158h+var_B8]
0x180023b11  mov     [rsp+158h+var_138], rax
0x180023b16  mov     r9, r13
0x180023b19  mov     r8, rdi
0x180023b1c  lea     rdx, [rsp+158h+newString]
0x180023b24  mov     rcx, rbx
0x180023b27  call    ?PrepareContext@Service@ConnectedStorage@@QEAAXU_GUID@@AEBVCallerInfo@2@_KAEBVContextDesc@2@W4STORAGE_SPACE_SYNC_MODE@@_NPEAUIStorageSpaceHandler@@@Z; ConnectedStorage::Service::PrepareContext(_GUID,ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,STORAGE_SPACE_SYNC_MODE,bool,IStorageSpaceHandler *)
0x180023b2c  nop
0x180023b2d  lea     rcx, [rsp+158h+var_B8]; this
0x180023b35  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180023b3a  nop
0x180023b3b  test    rbx, rbx
0x180023b3e  jz      short loc_180023B46
0x180023b40  call    ?ReturnInstance@Service@ConnectedStorage@@CAXXZ; ConnectedStorage::Service::ReturnInstance(void)
0x180023b45  nop
0x180023b46  mov     dil, byte ptr [rsp+158h+var_118]
0x180023b4b  xor     edx, edx; length
0x180023b4d  mov     rcx, [rsp+158h+var_108]; string
0x180023b52  call    cs:__imp_WindowsGetStringRawBuffer
0x180023b58  mov     rbx, rax
0x180023b5b  xor     edx, edx; length
0x180023b5d  mov     rcx, [rsp+158h+var_F0]; string
0x180023b62  call    cs:__imp_WindowsGetStringRawBuffer
0x180023b68  mov     rcx, qword ptr [rsp+158h+var_88]
0x180023b70  mov     [rsp+158h+var_138], rcx; unsigned int
0x180023b75  mov     r9d, dword ptr [rsp+158h+var_118+4]; bool
0x180023b7a  mov     r8b, dil; unsigned __int16 *
0x180023b7d  mov     rdx, rbx; unsigned __int16 *
0x180023b80  mov     rcx, rax; this
0x180023b83  call    ?EventWritePrepareContext@ConnectedStorage@@YAXQEBG0_NIQEBU_GUID@@@Z; ConnectedStorage::EventWritePrepareContext(ushort const * const,ushort const * const,bool,uint,_GUID const * const)
0x180023b88  nop
0x180023b89  mov     ecx, dword ptr [rsp+158h+var_118+4]; this
0x180023b8d  call    ?FilterHresult@ConnectedStorage@@YAJJ@Z; ConnectedStorage::FilterHresult(long)
0x180023b92  mov     ebx, eax
0x180023b94  mov     rcx, [rsp+158h+var_108]; string
0x180023b99  call    cs:__imp_WindowsDeleteString
0x180023b9f  mov     [rsp+158h+var_108], 0
0x180023ba8  mov     rcx, [rsp+158h+var_100]; string
0x180023bad  call    cs:__imp_WindowsDeleteString
0x180023bb3  mov     [rsp+158h+var_100], 0
0x180023bbc  mov     rcx, [rsp+158h+var_F8]; string
0x180023bc1  call    cs:__imp_WindowsDeleteString
0x180023bc7  mov     [rsp+158h+var_F8], 0
0x180023bd0  mov     rcx, [rsp+158h+var_F0]; string
0x180023bd5  call    cs:__imp_WindowsDeleteString
0x180023bdb  mov     eax, ebx
0x180023bdd  mov     rcx, [rsp+158h+var_38]
0x180023be5  xor     rcx, rsp; StackCookie
0x180023be8  call    __security_check_cookie
0x180023bed  mov     rbx, [rsp+158h+arg_18]
0x180023bf5  add     rsp, 130h
0x180023bfc  pop     r15
0x180023bfe  pop     r14
0x180023c00  pop     r13
0x180023c02  pop     r12
0x180023c04  pop     rdi
0x180023c05  retn
0x180023c06  jmp     loc_180023B46
0x180023c0b  jmp     loc_180023B46
0x180023c10  lea     rdx, aTheServiceHasS; "The service has shutdown."
0x180023c17  mov     ecx, 80004005h; this
0x180023c1c  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
