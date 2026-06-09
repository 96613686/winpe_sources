# NDXGI::CUMDAdapter::CUMDAdapter(std::shared_ptr<VersionedDXCoreAdapterFactory> &,std::shared_ptr<VersionedDXCoreAdapter> &,_LUID,_D3D12_DEVICE_SINGLE_ADAPTER_HYBRID_MODE,APPLICATION_DESC)

- ea: `0x180119ad8`
- end: `0x180119e8e`
- name: `??0CUMDAdapter@NDXGI@@QEAA@AEAV?$shared_ptr@VVersionedDXCoreAdapterFactory@@@std@@AEAV?$shared_ptr@VVersionedDXCoreAdapter@@@3@U_LUID@@W4_D3D12_DEVICE_SINGLE_ADAPTER_HYBRID_MODE@@UAPPLICATION_DESC@@@Z`
- size: `950`
- prototype: `__int64 __usercall@<rax>(NDXGI::CUMDAdapter *this@<rcx>, int, APPLICATION_DESC *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800bdd2c`

## callees

- `0x180004a38`
- `0x180007f20`
- `0x18000ac4c`
- `0x18000b010`
- `0x1800174a8`
- `0x180029b30`
- `0x18002a664`
- `0x18005fc0c`
- `0x180064f2c`
- `0x1800670f0`
- `0x18007f054`
- `0x180085970`
- `0x1800bb480`
- `0x1800bc094`
- `0x1800c2ffc`
- `0x1800c8cb4`
- `0x1801197d8`
- `0x180119ad8`
- `0x18011b6d0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180119e2c`
- `msvcp_win!_Mtx_unlock` at `0x180119e2c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180119d23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180119d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119d68`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180119d48`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180119d48`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x180119cf0`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x180119dc2`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCloseAdapter` at `0x180119e53`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCloseAdapter` at `0x180119e53`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenAdapterFromLuid` at `0x180119c5f`

## string_xrefs

- `0x180119de8`: `Driver update in progress.`
- `0x180119dbb`: `QAI (CHECKDRIVERUPDATESTATUS)`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
NDXGI::CUMDAdapter *__fastcall NDXGI::CUMDAdapter::CUMDAdapter(
        NDXGI::CUMDAdapter *this,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        int a5,
        APPLICATION_DESC *a6)
{
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  HINSTANCE *v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // edx
  int v21; // eax
  HMODULE Library; // rax
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  __int64 v25; // rcx
  __int64 v26; // r9
  bool v27; // sf
  __int64 v28; // rcx
  __int64 v29; // r9
  int v30; // eax
  __int64 *v32; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+38h] [rbp-C8h] BYREF
  int v34; // [rsp+3Ch] [rbp-C4h]
  __int64 **v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  NDXGI::CUMDAdapter *v37; // [rsp+50h] [rbp-B0h]
  NDXGI::CUMDAdapter *v38; // [rsp+58h] [rbp-A8h]
  APPLICATION_DESC *v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+70h] [rbp-90h]
  int v42; // [rsp+80h] [rbp-80h] BYREF
  WCHAR LibFileName[262]; // [rsp+84h] [rbp-7Ch] BYREF

  v37 = this;
  v39 = a6;
  APPLICATION_DESC::APPLICATION_DESC(this, a6);
  APPLICATION_DESC::APPLICATION_DESC((APPLICATION_DESC *)(v10 + 136));
  std::wstring::wstring((char *)this + 272);
  std::wstring::wstring((char *)this + 304);
  std::wstring::wstring((char *)this + 336);
  *((_QWORD *)this + 46) = a4;
  *((_DWORD *)this + 94) = 0;
  *((_DWORD *)this + 95) = -2147418113;
  v13 = (HINSTANCE *)((char *)this + 384);
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  v14 = a2[1];
  if ( v14 )
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
  *((_QWORD *)this + 52) = *a2;
  *((_QWORD *)this + 53) = a2[1];
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  v15 = a3[1];
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  *((_QWORD *)this + 54) = *a3;
  *((_QWORD *)this + 55) = a3[1];
  *((_DWORD *)this + 112) = 0;
  *(_OWORD *)((char *)this + 456) = NDXGI::CUMDAdapter::UMDAdapterCallbacks;
  *(_OWORD *)((char *)this + 472) = *(_OWORD *)&off_180278438;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_DWORD *)this + 142) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_DWORD *)this + 148) = a5;
  v41 = 0;
  v40 = a4;
  v16 = CallAndLogImpl<long (*)(_D3DKMT_OPENADAPTERFROMLUID const *),_D3DKMT_OPENADAPTERFROMLUID *>(
          D3DKMTOpenAdapterFromLuid,
          v11,
          v12,
          &v40);
  v17 = NDXGI::CUMDAdapter::NTStatusToHResult(v16, 1);
  *((_DWORD *)this + 95) = v17;
  ThrowFailure(v17);
  *((_DWORD *)this + 112) = v41;
  v38 = this;
  NDXGI::CUMDAdapter::InitDriverVerifier(this);
  NDXGI::CUMDAdapter::InitApplicationDesc(this);
  v36 = 524;
  memset_0(LibFileName, 0, 0x208u);
  v34 = 1;
  v33 = *((_DWORD *)this + 112);
  v35 = (__int64 **)&v42;
  v42 = 3;
  v18 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
          D3DKMTQueryAdapterInfo,
          "QAI (UMDRIVERNAME)",
          CLayeredObject<CCommandAllocator>::AddRef,
          &v33);
  v19 = NDXGI::CUMDAdapter::NTStatusToHResult(v18, 1);
  v21 = NDXGI::UnsupportedOrDeviceRemoved((NDXGI *)v19, v20);
  *((_DWORD *)this + 95) = v21;
  ThrowFailure(v21);
  Library = LoadLibraryExW(LibFileName, 0, 8u);
  D3DXPlat::unique_module::reset((NDXGI::CUMDAdapter *)((char *)this + 384), Library);
  if ( !*v13 )
  {
    if ( GetLastError() == 87 )
    {
      LibraryW = LoadLibraryW(LibFileName);
      D3DXPlat::unique_module::reset((NDXGI::CUMDAdapter *)((char *)this + 384), LibraryW);
    }
    if ( !*v13 )
    {
      *((_DWORD *)this + 95) = -2005270524;
      LastError = GetLastError();
      v27 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v27 = LastError < 0;
      }
      if ( v27 )
        CJournal::RecordJournal(v25, LastError, (__int64)"LoadUMD", v26, 0);
    }
  }
  LODWORD(v32) = 1;
  v34 = 55;
  LODWORD(v36) = 4;
  v35 = &v32;
  if ( (int)CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
              D3DKMTQueryAdapterInfo,
              "QAI (CHECKDRIVERUPDATESTATUS)",
              CLayeredObject<CCommandAllocator>::AddRef,
              &v33) < 0
    || (_DWORD)v32 )
  {
    *((_DWORD *)this + 95) = -2005270523;
    CJournal::RecordJournal(v28, -2005270523, (__int64)"Driver update in progress.", v29, 0);
  }
  ThrowFailure(*((_DWORD *)this + 95));
  v32 = &qword_180339898;
  std::_Mutex_base::lock((std::_Mutex_base *)&qword_180339898);
  UMDRef::AddUMD((UMDRef *)((char *)&qword_1803398E4 + 4), *v13);
  _Mtx_unlock((_Mtx_t)&qword_180339898);
  v30 = NDXGI::CUMDAdapter::OpenAdapter<0>(this);
  *((_DWORD *)this + 95) = v30;
  if ( v30 < 0 )
  {
    LODWORD(v32) = *((_DWORD *)this + 112);
    D3DKMTCloseAdapter(&v32);
    *((_DWORD *)this + 112) = 0;
  }
  APPLICATION_DESC::~APPLICATION_DESC(a6);
  return this;
}

```

## disassembly

```asm
0x180119ad8  push    rbp
0x180119ada  push    rbx
0x180119adb  push    rsi
0x180119adc  push    rdi
0x180119add  push    r12
0x180119adf  push    r13
0x180119ae1  push    r14
0x180119ae3  push    r15
0x180119ae5  lea     rbp, [rsp-1A8h]
0x180119aed  sub     rsp, 2A8h
0x180119af4  mov     rax, cs:__security_cookie
0x180119afb  xor     rax, rsp
0x180119afe  mov     [rbp+1E0h+var_50], rax
0x180119b05  mov     rbx, r9
0x180119b08  mov     r12, r8
0x180119b0b  mov     r14, rdx
0x180119b0e  mov     rdi, rcx
0x180119b11  mov     [rsp+2E0h+var_290], rcx
0x180119b16  mov     r15, [rbp+1E0h+arg_28]
0x180119b1d  mov     [rsp+2E0h+var_280], r15
0x180119b22  mov     rdx, r15
0x180119b25  call    ??0APPLICATION_DESC@@QEAA@$$QEAU0@@Z; APPLICATION_DESC::APPLICATION_DESC(APPLICATION_DESC &&)
0x180119b2a  nop
0x180119b2b  add     rcx, 88h; this
0x180119b32  call    ??0APPLICATION_DESC@@QEAA@XZ; APPLICATION_DESC::APPLICATION_DESC(void)
0x180119b37  nop
0x180119b38  lea     rcx, [rdi+110h]; void *
0x180119b3f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180119b44  nop
0x180119b45  lea     rcx, [rdi+130h]; void *
0x180119b4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180119b51  nop
0x180119b52  lea     rcx, [rdi+150h]; void *
0x180119b59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180119b5e  nop
0x180119b5f  mov     [rdi+170h], rbx
0x180119b66  xor     r13d, r13d
0x180119b69  mov     [rdi+178h], r13d
0x180119b70  mov     dword ptr [rdi+17Ch], 8000FFFFh
0x180119b7a  lea     rsi, [rdi+180h]
0x180119b81  mov     [rsi], r13
0x180119b84  mov     [rdi+188h], r13
0x180119b8b  mov     [rdi+190h], r13
0x180119b92  mov     [rdi+198h], r13
0x180119b99  mov     [rdi+1A0h], r13
0x180119ba0  mov     [rdi+1A8h], r13
0x180119ba7  mov     rax, [r14+8]
0x180119bab  test    rax, rax
0x180119bae  jz      short loc_180119BB4
0x180119bb0  lock inc dword ptr [rax+8]
0x180119bb4  mov     rax, [r14]
0x180119bb7  mov     [rdi+1A0h], rax
0x180119bbe  mov     rax, [r14+8]
0x180119bc2  mov     [rdi+1A8h], rax
0x180119bc9  mov     [rdi+1B0h], r13
0x180119bd0  mov     [rdi+1B8h], r13
0x180119bd7  mov     rax, [r12+8]
0x180119bdc  test    rax, rax
0x180119bdf  jz      short loc_180119BE5
0x180119be1  lock inc dword ptr [rax+8]
0x180119be5  mov     rax, [r12]
0x180119be9  mov     [rdi+1B0h], rax
0x180119bf0  mov     rax, [r12+8]
0x180119bf5  mov     [rdi+1B8h], rax
0x180119bfc  mov     [rdi+1C0h], r13d
0x180119c03  movups  xmm0, xmmword ptr cs:?UMDAdapterCallbacks@CUMDAdapter@NDXGI@@2U_D3DDDI_ADAPTERCALLBACKS@@B; _D3DDDI_ADAPTERCALLBACKS const NDXGI::CUMDAdapter::UMDAdapterCallbacks
0x180119c0a  movups  xmmword ptr [rdi+1C8h], xmm0
0x180119c11  movups  xmm1, xmmword ptr cs:off_180278438
0x180119c18  movups  xmmword ptr [rdi+1D8h], xmm1
0x180119c1f  xor     eax, eax
0x180119c21  mov     [rdi+228h], rax
0x180119c28  mov     [rdi+230h], r13
0x180119c2f  mov     [rdi+238h], r13d
0x180119c36  mov     [rdi+240h], r13
0x180119c3d  mov     [rdi+248h], r13
0x180119c44  mov     eax, [rbp+1E0h+arg_20]
0x180119c4a  mov     [rdi+250h], eax
0x180119c50  mov     [rsp+2E0h+var_270], r13d
0x180119c55  mov     [rsp+2E0h+var_278], rbx
0x180119c5a  lea     r9, [rsp+2E0h+var_278]
0x180119c5f  mov     rcx, cs:__imp_D3DKMTOpenAdapterFromLuid
0x180119c66  call    ??$CallAndLogImpl@P6AJPEBU_D3DKMT_OPENADAPTERFROMLUID@@@ZPEAU1@@@YAJP6AJPEBU_D3DKMT_OPENADAPTERFROMLUID@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@ZPEAU0@@Z; CallAndLogImpl<long (*)(_D3DKMT_OPENADAPTERFROMLUID const *),_D3DKMT_OPENADAPTERFROMLUID *>(long (*)(_D3DKMT_OPENADAPTERFROMLUID const *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_OPENADAPTERFROMLUID *)
0x180119c6b  mov     ebx, 1
0x180119c70  mov     edx, ebx
0x180119c72  mov     ecx, eax
0x180119c74  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180119c79  mov     [rdi+17Ch], eax
0x180119c7f  mov     ecx, eax; int
0x180119c81  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180119c86  mov     eax, [rsp+2E0h+var_270]
0x180119c8a  mov     [rdi+1C0h], eax
0x180119c90  mov     [rsp+2E0h+var_288], rdi
0x180119c95  mov     rcx, rdi; this
0x180119c98  call    ?InitDriverVerifier@CUMDAdapter@NDXGI@@IEAAXXZ; NDXGI::CUMDAdapter::InitDriverVerifier(void)
0x180119c9d  mov     rcx, rdi; this
0x180119ca0  call    ?InitApplicationDesc@CUMDAdapter@NDXGI@@IEAAXXZ; NDXGI::CUMDAdapter::InitApplicationDesc(void)
0x180119ca5  mov     [rsp+2E0h+var_298], 20Ch
0x180119cae  xor     edx, edx; Val
0x180119cb0  mov     r8d, 208h; Size
0x180119cb6  lea     rcx, [rbp+1E0h+LibFileName]; void *
0x180119cba  call    memset_0
0x180119cbf  mov     [rsp+2E0h+var_2A4], ebx
0x180119cc3  mov     eax, [rdi+1C0h]
0x180119cc9  mov     [rsp+2E0h+var_2A8], eax
0x180119ccd  lea     rax, [rbp+1E0h+var_260]
0x180119cd1  mov     [rsp+2E0h+var_2A0], rax
0x180119cd6  mov     [rbp+1E0h+var_260], 3
0x180119cdd  lea     r9, [rsp+2E0h+var_2A8]
0x180119ce2  lea     r8, ?AddRef@?$CLayeredObject@VCCommandAllocator@@@@UEAAKXZ; CLayeredObject<CCommandAllocator>::AddRef(void)
0x180119ce9  lea     rdx, aQaiUmdrivernam; "QAI (UMDRIVERNAME)"
0x180119cf0  mov     rcx, cs:__imp_D3DKMTQueryAdapterInfo
0x180119cf7  call    ??$CallAndLogImpl@P6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEAU1@@@YAJP6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(long (*)(D3DDDI_DESTROYPAGINGQUEUE *),char const *,RecordStatusFilterResult (*)(long),D3DDDI_DESTROYPAGINGQUEUE *)
0x180119cfc  mov     edx, ebx
0x180119cfe  mov     ecx, eax
0x180119d00  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180119d05  mov     ecx, eax; this
0x180119d07  call    ?UnsupportedOrDeviceRemoved@NDXGI@@YAJJ@Z; NDXGI::UnsupportedOrDeviceRemoved(long)
0x180119d0c  mov     [rdi+17Ch], eax
0x180119d12  mov     ecx, eax; int
0x180119d14  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180119d19  xor     edx, edx; hFile
0x180119d1b  lea     r8d, [rbx+7]; dwFlags
0x180119d1f  lea     rcx, [rbp+1E0h+LibFileName]; lpLibFileName
0x180119d23  call    cs:__imp_LoadLibraryExW
0x180119d29  mov     rdx, rax; HINSTANCE
0x180119d2c  mov     rcx, rsi; this
0x180119d2f  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x180119d34  cmp     [rsi], r13
0x180119d37  jnz     short loc_180119D91
0x180119d39  call    cs:__imp_GetLastError
0x180119d3f  cmp     eax, 57h ; 'W'
0x180119d42  jnz     short loc_180119D59
0x180119d44  lea     rcx, [rbp+1E0h+LibFileName]; lpLibFileName
0x180119d48  call    cs:__imp_LoadLibraryW
0x180119d4e  mov     rdx, rax; HINSTANCE
0x180119d51  mov     rcx, rsi; this
0x180119d54  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x180119d59  cmp     [rsi], r13
0x180119d5c  jnz     short loc_180119D91
0x180119d5e  mov     dword ptr [rdi+17Ch], 887A0004h
0x180119d68  call    cs:__imp_GetLastError
0x180119d6e  test    eax, eax
0x180119d70  jle     short loc_180119D7C
0x180119d72  movzx   eax, ax
0x180119d75  or      eax, 80070000h
0x180119d7a  test    eax, eax
0x180119d7c  jns     short loc_180119D91
0x180119d7e  mov     [rsp+2E0h+var_2C0], r13d
0x180119d83  lea     r8, aLoadumd; "LoadUMD"
0x180119d8a  mov     edx, eax
0x180119d8c  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x180119d91  mov     dword ptr [rsp+2E0h+var_2B0], ebx
0x180119d95  mov     [rsp+2E0h+var_2A4], 37h ; '7'
0x180119d9d  mov     dword ptr [rsp+2E0h+var_298], 4
0x180119da5  lea     rax, [rsp+2E0h+var_2B0]
0x180119daa  mov     [rsp+2E0h+var_2A0], rax
0x180119daf  lea     r9, [rsp+2E0h+var_2A8]
0x180119db4  lea     r8, ?AddRef@?$CLayeredObject@VCCommandAllocator@@@@UEAAKXZ; CLayeredObject<CCommandAllocator>::AddRef(void)
0x180119dbb  lea     rdx, aQaiCheckdriver; "QAI (CHECKDRIVERUPDATESTATUS)"
0x180119dc2  mov     rcx, cs:__imp_D3DKMTQueryAdapterInfo
0x180119dc9  call    ??$CallAndLogImpl@P6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEAU1@@@YAJP6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(long (*)(D3DDDI_DESTROYPAGINGQUEUE *),char const *,RecordStatusFilterResult (*)(long),D3DDDI_DESTROYPAGINGQUEUE *)
0x180119dce  test    eax, eax
0x180119dd0  js      short loc_180119DD9
0x180119dd2  cmp     dword ptr [rsp+2E0h+var_2B0], r13d
0x180119dd7  jz      short loc_180119DF9
0x180119dd9  mov     dword ptr [rdi+17Ch], 887A0005h
0x180119de3  mov     [rsp+2E0h+var_2C0], r13d
0x180119de8  lea     r8, aDriverUpdateIn; "Driver update in progress."
0x180119def  mov     edx, 887A0005h
0x180119df4  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x180119df9  mov     ecx, [rdi+17Ch]; int
0x180119dff  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180119e04  lea     rbx, qword_180339898
0x180119e0b  mov     [rsp+2E0h+var_2B0], rbx
0x180119e10  mov     rcx, rbx; this
0x180119e13  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180119e18  nop
0x180119e19  mov     rdx, [rsi]; HINSTANCE
0x180119e1c  lea     rcx, qword_1803398E4+4; this
0x180119e23  call    ?AddUMD@UMDRef@@QEAAXPEAUHINSTANCE__@@@Z; UMDRef::AddUMD(HINSTANCE__ *)
0x180119e28  nop
0x180119e29  mov     rcx, rbx; _Mtx_t
0x180119e2c  call    cs:__imp__Mtx_unlock
0x180119e32  mov     rcx, rdi
0x180119e35  call    ??$OpenAdapter@$0A@@CUMDAdapter@NDXGI@@IEAAJXZ; NDXGI::CUMDAdapter::OpenAdapter<0>(void)
0x180119e3a  mov     [rdi+17Ch], eax
0x180119e40  test    eax, eax
0x180119e42  jns     short loc_180119E60
0x180119e44  mov     edx, [rdi+1C0h]
0x180119e4a  mov     dword ptr [rsp+2E0h+var_2B0], edx
0x180119e4e  lea     rcx, [rsp+2E0h+var_2B0]
0x180119e53  call    cs:__imp_D3DKMTCloseAdapter
0x180119e59  mov     [rdi+1C0h], r13d
0x180119e60  mov     rcx, r15; this
0x180119e63  call    ??1APPLICATION_DESC@@QEAA@XZ; APPLICATION_DESC::~APPLICATION_DESC(void)
0x180119e68  mov     rax, rdi
0x180119e6b  mov     rcx, [rbp+1E0h+var_50]
0x180119e72  xor     rcx, rsp; StackCookie
0x180119e75  call    __security_check_cookie
0x180119e7a  add     rsp, 2A8h
0x180119e81  pop     r15
0x180119e83  pop     r14
0x180119e85  pop     r13
0x180119e87  pop     r12
0x180119e89  pop     rdi
0x180119e8a  pop     rsi
0x180119e8b  pop     rbx
0x180119e8c  pop     rbp
0x180119e8d  retn
```
