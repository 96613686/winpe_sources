# ServiceEnsureLicenseForOptionalPackageUsageImpl(void *,ushort const *,ulong,ushort const *,ushort const *,_GUID)

- ea: `0x18008f7d8`
- end: `0x18008fbaa`
- name: `?ServiceEnsureLicenseForOptionalPackageUsageImpl@@YAJPEAXPEBGK11U_GUID@@@Z`
- size: `978`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *Src, struct _GUID *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800842e0`

## callees

- `0x180004738`
- `0x18000a110`
- `0x18000b14c`
- `0x18000c70c`
- `0x18000cca0`
- `0x180012dc0`
- `0x180013b50`
- `0x18002bc9c`
- `0x1800397ac`
- `0x18003af60`
- `0x18003bdf8`
- `0x18003f518`
- `0x180042188`
- `0x180046f88`
- `0x180055d34`
- `0x1800593bc`
- `0x180066bac`
- `0x18006ad98`
- `0x180075e60`
- `0x18008a17c`
- `0x18008e1f4`
- `0x18008f7d8`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f887`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008fb1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008f887`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008fb1e`

## string_xrefs

- `0x18008f8b8`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008faa2`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008fb98`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f89f`: `ServiceEnsureLicenseForOptionalPackageUsageImpl PackageFullName:%s, OptionalPackageName:%s`
- `0x18008f8ab`: `ServiceEnsureLicenseForOptionalPackageUsageImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ServiceEnsureLicenseForOptionalPackageUsageImpl(
        void *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 *Src,
        struct _GUID *a6)
{
  const unsigned __int16 *v6; // r14
  char v8; // bl
  ULONGLONG TickCount64; // r12
  __int64 v11; // rcx
  __int64 Existing; // rax
  __int64 v13; // rcx
  PendingRequest *v14; // rbx
  unsigned __int16 *v15; // r13
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rcx
  const unsigned __int16 *v19; // rdx
  int v20; // eax
  unsigned int v21; // esi
  const char *v22; // r9
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  wil *v26; // rcx
  int Format; // [rsp+20h] [rbp-128h]
  int Formata; // [rsp+20h] [rbp-128h]
  __int64 v29; // [rsp+28h] [rbp-120h]
  unsigned int v30; // [rsp+50h] [rbp-F8h] BYREF
  int v31[2]; // [rsp+58h] [rbp-F0h] BYREF
  PendingRequest *v32; // [rsp+60h] [rbp-E8h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-E0h]
  ULONGLONG v34; // [rsp+70h] [rbp-D8h] BYREF
  const unsigned __int16 *v35; // [rsp+78h] [rbp-D0h] BYREF
  _BYTE v36[8]; // [rsp+80h] [rbp-C8h] BYREF
  _BYTE v37[8]; // [rsp+88h] [rbp-C0h] BYREF
  _BYTE v38[16]; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v39[2]; // [rsp+A0h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-98h]
  unsigned __int16 *v41[4]; // [rsp+C0h] [rbp-88h] BYREF
  int v42[8]; // [rsp+E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v33 = a4;
  v30 = a3;
  v6 = a2;
  v35 = a2;
  ProcessReference(v36);
  if ( !v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)0x80004003LL,
      Format);
  std::wstring::wstring(v39, v6);
  v8 = SkipForAppCompat(v39);
  ContentIdString::~ContentIdString((ContentIdString *)v39);
  if ( v8 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v36);
    return 0;
  }
  else
  {
    TickCount64 = GetTickCount64();
    v34 = TickCount64;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x9C5u,
      "ServiceEnsureLicenseForOptionalPackageUsageImpl",
      (wchar_t *)L"ServiceEnsureLicenseForOptionalPackageUsageImpl PackageFullName:%s, OptionalPackageName:%s",
      v6);
    try
    {
      GetAppSessionIds(v41, 1, a6);
      v32 = 0;
      PendingRequestManager::PendingRequestManager((PendingRequestManager *)v37);
      std::wstring::wstring(v39, Src);
      LODWORD(v29) = v30;
      Existing = PendingRequestManager::FindExisting(v11, v31, v39, 0, v33, v29, (_DWORD)Src);
      Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(&v32, Existing);
      v13 = *(_QWORD *)v31;
      if ( *(_QWORD *)v31 )
      {
        *(_QWORD *)v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      ContentIdString::~ContentIdString((ContentIdString *)v39);
      v14 = v32;
      if ( v32 )
      {
        v15 = v33;
      }
      else
      {
        ImpersonationScope<RpcImpersonateClientTraits>::ImpersonationScope<RpcImpersonateClientTraits>(v38, a1);
        *(_OWORD *)v39 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v39[0]) = 0;
        std::wstring::wstring(v42, v6);
        v15 = v33;
        v17 = PendingRequestManager::AddRequest(v16, (int)v31, (int)v42, 0, Src, (__int64)v33, v30, 0, (__int64)v39, 0);
        Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(&v32, v17);
        v18 = *(_QWORD *)v31;
        if ( *(_QWORD *)v31 )
        {
          *(_QWORD *)v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        ContentIdString::~ContentIdString((ContentIdString *)v42);
        ContentIdString::~ContentIdString((ContentIdString *)v39);
        ImpersonationScope<RpcImpersonateClientTraits>::~ImpersonationScope<RpcImpersonateClientTraits>(v38);
        v14 = v32;
      }
      PendingRequestManager::~PendingRequestManager((PendingRequestManager *)v37);
      if ( v41[2] )
      {
        v19 = (const unsigned __int16 *)v41;
        if ( v41[3] > (unsigned __int16 *)7 )
          v19 = v41[0];
      }
      else
      {
        v19 = 0;
      }
      v20 = PendingRequest::WaitForResult(v14, v19);
      v21 = v20;
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x9D6,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          (const char *)(unsigned int)v20,
          Formata);
      RemovePendingRequest(0, Src, v30, v15);
      if ( v14 )
        (*(void (__fastcall **)(PendingRequest *))(*(_QWORD *)v14 + 16LL))(v14);
      ContentIdString::~ContentIdString((ContentIdString *)v41);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x9DD,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        v22);
      v30 = wil::ResultFromCaughtException(v26);
      v21 = v30;
      TickCount64 = v34;
      v6 = v35;
    }
    if ( (unsigned int)dword_1800F11D0 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
      {
        v35 = (const unsigned __int16 *)(GetTickCount64() - TickCount64);
        v30 = v21;
        v34 = (ULONGLONG)v6;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v23,
          (unsigned int)byte_1800D71BD,
          v24,
          v25,
          (__int64)&v34,
          (__int64)&v30,
          (__int64)&v35);
      }
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v36);
    return v21;
  }
}

```

## disassembly

```asm
0x18008f7d8  push    rbx
0x18008f7da  push    rsi
0x18008f7db  push    rdi
0x18008f7dc  push    r12
0x18008f7de  push    r13
0x18008f7e0  push    r14
0x18008f7e2  push    r15
0x18008f7e4  sub     rsp, 110h
0x18008f7eb  mov     rax, cs:__security_cookie
0x18008f7f2  xor     rax, rsp
0x18008f7f5  mov     [rsp+148h+var_48], rax
0x18008f7fd  mov     [rsp+148h+var_E0], r9
0x18008f802  mov     [rsp+148h+var_F8], r8d
0x18008f807  mov     r14, rdx
0x18008f80a  mov     r13, rcx
0x18008f80d  mov     [rsp+148h+var_D0], rdx
0x18008f812  mov     r15, [rsp+148h+Src]
0x18008f81a  mov     rsi, [rsp+148h+arg_28]
0x18008f822  lea     rcx, [rsp+148h+var_C8]
0x18008f82a  call    ?ProcessReference@@YA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; ProcessReference(void)
0x18008f82f  nop
0x18008f830  mov     rcx, [rsp+148h]; this
0x18008f838  xor     edi, edi
0x18008f83a  test    r14, r14
0x18008f83d  jz      loc_18008FB92
0x18008f843  mov     rdx, r14
0x18008f846  lea     rcx, [rsp+148h+var_A8]
0x18008f84e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f853  lea     rcx, [rsp+148h+var_A8]
0x18008f85b  call    ?SkipForAppCompat@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SkipForAppCompat(std::wstring const &)
0x18008f860  mov     bl, al
0x18008f862  lea     rcx, [rsp+148h+var_A8]; this
0x18008f86a  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008f86f  test    bl, bl
0x18008f871  jz      short loc_18008F887
0x18008f873  lea     rcx, [rsp+148h+var_C8]
0x18008f87b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008f880  xor     eax, eax
0x18008f882  jmp     loc_18008FB6F
0x18008f887  call    cs:__imp_GetTickCount64
0x18008f88d  mov     r12, rax
0x18008f890  mov     [rsp+148h+var_D8], rax
0x18008f895  mov     qword ptr [rsp+148h+var_118], r15
0x18008f89a  mov     [rsp+148h+var_120], r14
0x18008f89f  lea     rax, aServiceensurel_1; "ServiceEnsureLicenseForOptionalPackageU"...
0x18008f8a6  mov     [rsp+148h+Format], rax; Format
0x18008f8ab  lea     r9, aServiceensurel_4; "ServiceEnsureLicenseForOptionalPackageU"...
0x18008f8b2  mov     r8d, 9C5h; unsigned int
0x18008f8b8  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008f8bf  mov     ecx, 3; unsigned int
0x18008f8c4  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008f8c9  nop
0x18008f8ca  mov     r8, rsi
0x18008f8cd  mov     edx, 1
0x18008f8d2  lea     rcx, [rsp+148h+var_88]
0x18008f8da  call    ?GetAppSessionIds@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEBU_GUID@@@Z; GetAppSessionIds(ulong,_GUID const * const)
0x18008f8df  nop
0x18008f8e0  mov     [rsp+148h+var_E8], rdi
0x18008f8e5  lea     rcx, [rsp+148h+var_C0]; this
0x18008f8ed  call    ??0PendingRequestManager@@QEAA@XZ; PendingRequestManager::PendingRequestManager(void)
0x18008f8f2  nop
0x18008f8f3  mov     rdx, r15
0x18008f8f6  lea     rcx, [rsp+148h+var_A8]
0x18008f8fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f903  nop
0x18008f904  mov     esi, [rsp+148h+var_F8]
0x18008f908  mov     dword ptr [rsp+148h+var_120], esi
0x18008f90c  mov     rax, [rsp+148h+var_E0]
0x18008f911  mov     [rsp+148h+Format], rax; int
0x18008f916  xor     r9d, r9d
0x18008f919  lea     r8, [rsp+148h+var_A8]
0x18008f921  lea     rdx, [rsp+148h+var_F0]
0x18008f926  call    ?FindExisting@PendingRequestManager@@QEAA?AV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1K@Z; PendingRequestManager::FindExisting(std::wstring const &,ushort const *,ushort const *,ulong)
0x18008f92b  mov     rdx, rax
0x18008f92e  lea     rcx, [rsp+148h+var_E8]
0x18008f933  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18008f938  nop
0x18008f939  mov     rcx, qword ptr [rsp+148h+var_F0]
0x18008f93e  test    rcx, rcx
0x18008f941  jz      short loc_18008F955
0x18008f943  mov     qword ptr [rsp+148h+var_F0], rdi
0x18008f948  mov     rax, [rcx]
0x18008f94b  mov     rax, [rax+10h]
0x18008f94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f954  nop
0x18008f955  lea     rcx, [rsp+148h+var_A8]; this
0x18008f95d  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008f962  mov     rbx, [rsp+148h+var_E8]
0x18008f967  test    rbx, rbx
0x18008f96a  jnz     loc_18008FA4E
0x18008f970  mov     rdx, r13
0x18008f973  lea     rcx, [rsp+148h+var_B8]
0x18008f97b  call    ??0?$ImpersonationScope@URpcImpersonateClientTraits@@@@QEAA@PEAX@Z; ImpersonationScope<RpcImpersonateClientTraits>::ImpersonationScope<RpcImpersonateClientTraits>(void *)
0x18008f980  nop
0x18008f981  xorps   xmm0, xmm0
0x18008f984  movups  xmmword ptr [rsp+148h+var_A8], xmm0
0x18008f98c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008f994  movdqu  [rsp+148h+var_98], xmm1
0x18008f99d  mov     word ptr [rsp+148h+var_A8], di
0x18008f9a5  mov     rdx, r14
0x18008f9a8  lea     rcx, [rsp+148h+var_68]
0x18008f9b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008f9b5  nop
0x18008f9b6  mov     [rsp+148h+var_100], dil; char
0x18008f9bb  lea     rax, [rsp+148h+var_A8]
0x18008f9c3  mov     [rsp+148h+var_108], rax; __int64
0x18008f9c8  mov     [rsp+148h+var_110], edi; int
0x18008f9cc  mov     [rsp+148h+var_118], esi; int
0x18008f9d0  mov     r13, [rsp+148h+var_E0]
0x18008f9d5  mov     [rsp+148h+var_120], r13; __int64
0x18008f9da  mov     [rsp+148h+Format], r15; Src
0x18008f9df  xor     r9d, r9d; int
0x18008f9e2  lea     r8, [rsp+148h+var_68]; int
0x18008f9ea  lea     rdx, [rsp+148h+var_F0]; int
0x18008f9ef  call    ?AddRequest@PendingRequestManager@@QEAA?AV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG11KH0_N@Z; PendingRequestManager::AddRequest(std::wstring const &,ushort const *,ushort const *,ushort const *,ulong,int,std::wstring const &,bool)
0x18008f9f4  mov     rdx, rax
0x18008f9f7  lea     rcx, [rsp+148h+var_E8]
0x18008f9fc  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18008fa01  nop
0x18008fa02  mov     rcx, qword ptr [rsp+148h+var_F0]
0x18008fa07  test    rcx, rcx
0x18008fa0a  jz      short loc_18008FA1E
0x18008fa0c  mov     qword ptr [rsp+148h+var_F0], rdi
0x18008fa11  mov     rax, [rcx]
0x18008fa14  mov     rax, [rax+10h]
0x18008fa18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa1d  nop
0x18008fa1e  lea     rcx, [rsp+148h+var_68]; this
0x18008fa26  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008fa2b  nop
0x18008fa2c  lea     rcx, [rsp+148h+var_A8]; this
0x18008fa34  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008fa39  nop
0x18008fa3a  lea     rcx, [rsp+148h+var_B8]
0x18008fa42  call    ??1?$ImpersonationScope@URpcImpersonateClientTraits@@@@QEAA@XZ; ImpersonationScope<RpcImpersonateClientTraits>::~ImpersonationScope<RpcImpersonateClientTraits>(void)
0x18008fa47  mov     rbx, [rsp+148h+var_E8]
0x18008fa4c  jmp     short loc_18008FA53
0x18008fa4e  mov     r13, [rsp+148h+var_E0]
0x18008fa53  lea     rcx, [rsp+148h+var_C0]; this
0x18008fa5b  call    ??1PendingRequestManager@@QEAA@XZ; PendingRequestManager::~PendingRequestManager(void)
0x18008fa60  cmp     [rsp+148h+var_78], rdi
0x18008fa68  jnz     short loc_18008FA6F
0x18008fa6a  mov     rdx, rdi
0x18008fa6d  jmp     short loc_18008FA89
0x18008fa6f  lea     rdx, [rsp+148h+var_88]
0x18008fa77  cmp     [rsp+148h+var_70], 7
0x18008fa80  cmova   rdx, [rsp+148h+var_88]; unsigned __int16 *
0x18008fa89  mov     rcx, rbx; this
0x18008fa8c  call    ?WaitForResult@PendingRequest@@QEBAJPEBG@Z; PendingRequest::WaitForResult(ushort const *)
0x18008fa91  mov     esi, eax
0x18008fa93  mov     rcx, [rsp+148h]; this
0x18008fa9b  test    eax, eax
0x18008fa9d  jns     short loc_18008FAB3
0x18008fa9f  mov     r9d, eax; char *
0x18008faa2  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008faa9  mov     edx, 9D6h; void *
0x18008faae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008fab3  mov     r9, r13; unsigned __int16 *
0x18008fab6  mov     r8d, [rsp+148h+var_F8]; unsigned int
0x18008fabb  mov     rdx, r15; Src
0x18008fabe  xor     ecx, ecx; unsigned __int16 *
0x18008fac0  call    ?RemovePendingRequest@@YAXPEBG0K0@Z; RemovePendingRequest(ushort const *,ushort const *,ulong,ushort const *)
0x18008fac5  nop
0x18008fac6  test    rbx, rbx
0x18008fac9  jz      short loc_18008FADB
0x18008facb  mov     rax, [rbx]
0x18008face  mov     rcx, rbx
0x18008fad1  mov     rax, [rax+10h]
0x18008fad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fada  nop
0x18008fadb  lea     rcx, [rsp+148h+var_88]; this
0x18008fae3  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008fae8  nop
0x18008fae9  jmp     short loc_18008FAF9
0x18008faeb  mov     esi, [rsp+148h+var_F8]
0x18008faef  mov     r12, [rsp+148h+var_D8]
0x18008faf4  mov     r14, [rsp+148h+var_D0]
0x18008faf9  mov     eax, cs:dword_1800F11D0
0x18008faff  cmp     eax, 5
0x18008fb02  jbe     short loc_18008FB60
0x18008fb04  mov     rdx, 200000000000h
0x18008fb0e  lea     rcx, dword_1800F11D0
0x18008fb15  call    _tlgKeywordOn
0x18008fb1a  test    al, al
0x18008fb1c  jz      short loc_18008FB60
0x18008fb1e  call    cs:__imp_GetTickCount64
0x18008fb24  sub     rax, r12
0x18008fb27  mov     [rsp+148h+var_D0], rax
0x18008fb2c  mov     [rsp+148h+var_F8], esi
0x18008fb30  mov     [rsp+148h+var_D8], r14
0x18008fb35  lea     rax, [rsp+148h+var_D0]
0x18008fb3a  mov     qword ptr [rsp+148h+var_118], rax
0x18008fb3f  lea     rax, [rsp+148h+var_F8]
0x18008fb44  mov     [rsp+148h+var_120], rax
0x18008fb49  lea     rax, [rsp+148h+var_D8]
0x18008fb4e  mov     [rsp+148h+Format], rax
0x18008fb53  lea     rdx, byte_1800D71BD
0x18008fb5a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18008fb5f  nop
0x18008fb60  lea     rcx, [rsp+148h+var_C8]
0x18008fb68  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008fb6d  mov     eax, esi
0x18008fb6f  mov     rcx, [rsp+148h+var_48]
0x18008fb77  xor     rcx, rsp; StackCookie
0x18008fb7a  call    __security_check_cookie
0x18008fb7f  add     rsp, 110h
0x18008fb86  pop     r15
0x18008fb88  pop     r14
0x18008fb8a  pop     r13
0x18008fb8c  pop     r12
0x18008fb8e  pop     rdi
0x18008fb8f  pop     rsi
0x18008fb90  pop     rbx
0x18008fb91  retn
0x18008fb92  mov     r9d, 80004003h; char *
0x18008fb98  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008fb9f  mov     edx, 9C1h; void *
0x18008fba4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
