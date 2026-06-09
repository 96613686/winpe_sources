# ServiceEnsureLicenseForPackageActivationImpl(void *,ushort const *,ulong,ushort const *,ulong,_GUID const * const)

- ea: `0x18008fbb0`
- end: `0x18008ffe7`
- name: `?ServiceEnsureLicenseForPackageActivationImpl@@YAJPEAXPEBGK1KQEBU_GUID@@@Z`
- size: `1079`
- prototype: `int(void *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const struct _GUID *const)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180084320`

## callees

- `0x18000295c`
- `0x180004738`
- `0x18000a110`
- `0x18000b14c`
- `0x18000c70c`
- `0x18000cca0`
- `0x180012dc0`
- `0x180013b50`
- `0x180017740`
- `0x18002bc9c`
- `0x1800397ac`
- `0x18003af60`
- `0x18003bdf8`
- `0x18003f518`
- `0x180046f88`
- `0x180055d34`
- `0x180056848`
- `0x1800593bc`
- `0x180066bac`
- `0x18006ad98`
- `0x180075e60`
- `0x18008e1f4`
- `0x18008fbb0`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008fc7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008fee1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008feec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008fc7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008fee1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008feec`

## string_xrefs

- `0x18008fcb9`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008ffbf`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008ffd4`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008fca0`: `ServiceEnsureLicenseForPackageActivationImpl %s, sid:%s`
- `0x18008fcac`: `ServiceEnsureLicenseForPackageActivationImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ServiceEnsureLicenseForPackageActivationImpl(
        void *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        const struct _GUID *const a6)
{
  unsigned __int16 **v10; // rdx
  char v11; // bl
  ULONGLONG TickCount64; // r13
  const WCHAR *v14; // rcx
  __int64 v15; // rcx
  __int64 Existing; // rax
  __int64 v17; // rcx
  PendingRequest *v18; // rbx
  int v19; // ecx
  __int64 v20; // rax
  __int64 v21; // rcx
  const unsigned __int16 *v22; // rdx
  int v23; // edi
  const unsigned __int16 *v24; // rdx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  unsigned __int16 **v28; // rax
  const char *v29; // r9
  wil *v30; // rcx
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  unsigned __int16 **v34; // rax
  int Format; // [rsp+20h] [rbp-108h]
  int Formata; // [rsp+20h] [rbp-108h]
  __int64 v37; // [rsp+28h] [rbp-100h]
  int v38; // [rsp+30h] [rbp-F8h]
  PendingRequest *v39; // [rsp+50h] [rbp-D8h] BYREF
  int v40[2]; // [rsp+58h] [rbp-D0h] BYREF
  _BYTE v41[8]; // [rsp+60h] [rbp-C8h] BYREF
  ULONGLONG v42; // [rsp+68h] [rbp-C0h] BYREF
  _QWORD v43[2]; // [rsp+70h] [rbp-B8h] BYREF
  unsigned __int16 *Src[3]; // [rsp+80h] [rbp-A8h] BYREF
  unsigned __int64 v45; // [rsp+98h] [rbp-90h]
  __int64 v46[2]; // [rsp+A0h] [rbp-88h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-78h]
  unsigned __int16 *v48[4]; // [rsp+C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  ProcessReference(v41);
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x98B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)0x80004003LL,
      Format);
  GetPackageFullNameFromPsmKey(Src);
  v10 = Src;
  if ( v45 > 7 )
    v10 = (unsigned __int16 **)Src[0];
  std::wstring::wstring(v46, v10);
  v11 = SkipForAppCompat(v46);
  ContentIdString::~ContentIdString((ContentIdString *)v46);
  if ( !v11 )
  {
    TickCount64 = GetTickCount64();
    LODWORD(v14) = (_DWORD)a4;
    if ( !a4 )
      v14 = &LocaleName;
    v38 = (int)v14;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x990u,
      "ServiceEnsureLicenseForPackageActivationImpl",
      (wchar_t *)L"ServiceEnsureLicenseForPackageActivationImpl %s, sid:%s",
      a2);
    try
    {
      GetAppSessionIds(v48, a5, a6);
      v39 = 0;
      PendingRequestManager::PendingRequestManager((PendingRequestManager *)&v42);
      LODWORD(v37) = a3;
      Existing = PendingRequestManager::FindExisting(v15, v40, Src, a2, a4, v37, v38);
      Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(&v39, Existing);
      v17 = *(_QWORD *)v40;
      if ( *(_QWORD *)v40 )
      {
        *(_QWORD *)v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = v39;
      if ( !v39 && !(unsigned __int8)LeaseRunningPackage(a2, (__int64)v48) )
      {
        ImpersonationScope<RpcImpersonateClientTraits>::ImpersonationScope<RpcImpersonateClientTraits>(v43, a1);
        *(_OWORD *)v46 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v46[0]) = 0;
        v20 = PendingRequestManager::AddRequest(
                v19,
                (int)v40,
                (int)Src,
                (int)a2,
                0,
                (__int64)a4,
                a3,
                0,
                (__int64)v46,
                0);
        Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(&v39, v20);
        v21 = *(_QWORD *)v40;
        if ( *(_QWORD *)v40 )
        {
          *(_QWORD *)v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        ContentIdString::~ContentIdString((ContentIdString *)v46);
        ImpersonationScope<RpcImpersonateClientTraits>::~ImpersonationScope<RpcImpersonateClientTraits>(v43);
        v18 = v39;
      }
      PendingRequestManager::~PendingRequestManager((PendingRequestManager *)&v42);
      if ( v18 )
      {
        if ( v48[2] )
        {
          v22 = (const unsigned __int16 *)v48;
          if ( v48[3] > (unsigned __int16 *)7 )
            v22 = v48[0];
        }
        else
        {
          v22 = 0;
        }
        v23 = PendingRequest::WaitForResult(v18, v22);
        v24 = (const unsigned __int16 *)Src;
        if ( v45 > 7 )
          v24 = Src[0];
        RemovePendingRequest(a2, v24, a3, a4);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x9AB,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v23,
            Formata);
      }
      if ( (unsigned int)dword_1800F11D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
      {
        v42 = GetTickCount64();
        *(_QWORD *)v40 = GetTickCount64() - TickCount64;
        LODWORD(v39) = 0;
        v28 = Src;
        if ( v45 > 7 )
          v28 = (unsigned __int16 **)Src[0];
        v43[0] = v28;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v25,
          (unsigned int)&byte_1800D7287,
          v26,
          v27,
          (__int64)v43,
          (__int64)&v39,
          (__int64)v40,
          (__int64)&v42);
      }
      if ( v18 )
        (*(void (__fastcall **)(PendingRequest *))(*(_QWORD *)v18 + 16LL))(v18);
      ContentIdString::~ContentIdString((ContentIdString *)v48);
    }
    catch ( ... )
    {
      if ( (unsigned int)dword_1800F11D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
      {
        LODWORD(v39) = wil::ResultFromCaughtException(v30);
        v34 = Src;
        if ( v45 > 7 )
          v34 = (unsigned __int16 **)Src[0];
        v43[0] = v34;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v31,
          (unsigned int)&word_1800D7236,
          v32,
          v33,
          (__int64)v43,
          (__int64)&v39);
      }
      LODWORD(v39) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x9B5,
                       (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                       v29);
      ContentIdString::~ContentIdString((ContentIdString *)Src);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v41);
      return (unsigned int)v39;
    }
  }
  ContentIdString::~ContentIdString((ContentIdString *)Src);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v41);
  return 0;
}

```

## disassembly

```asm
0x18008fbb0  push    rbx
0x18008fbb2  push    rsi
0x18008fbb3  push    rdi
0x18008fbb4  push    r12
0x18008fbb6  push    r13
0x18008fbb8  push    r14
0x18008fbba  push    r15
0x18008fbbc  sub     rsp, 0F0h
0x18008fbc3  mov     rax, cs:__security_cookie
0x18008fbca  xor     rax, rsp
0x18008fbcd  mov     [rsp+128h+var_48], rax
0x18008fbd5  mov     r14, r9
0x18008fbd8  mov     r15d, r8d
0x18008fbdb  mov     rsi, rdx
0x18008fbde  mov     r12, rcx
0x18008fbe1  mov     rdi, [rsp+128h+arg_28]
0x18008fbe9  lea     rcx, [rsp+128h+var_C8]
0x18008fbee  call    ?ProcessReference@@YA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; ProcessReference(void)
0x18008fbf3  nop
0x18008fbf4  mov     rcx, [rsp+128h]; this
0x18008fbfc  test    rsi, rsi
0x18008fbff  jz      loc_18008FFB9
0x18008fc05  mov     rdx, rsi
0x18008fc08  lea     rcx, [rsp+128h+Src]
0x18008fc10  call    ?GetPackageFullNameFromPsmKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetPackageFullNameFromPsmKey(ushort const *)
0x18008fc15  nop
0x18008fc16  lea     rdx, [rsp+128h+Src]
0x18008fc1e  cmp     [rsp+128h+var_90], 7
0x18008fc27  cmova   rdx, [rsp+128h+Src]
0x18008fc30  lea     rcx, [rsp+128h+var_88]
0x18008fc38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008fc3d  lea     rcx, [rsp+128h+var_88]
0x18008fc45  call    ?SkipForAppCompat@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SkipForAppCompat(std::wstring const &)
0x18008fc4a  mov     bl, al
0x18008fc4c  lea     rcx, [rsp+128h+var_88]; this
0x18008fc54  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008fc59  test    bl, bl
0x18008fc5b  jz      short loc_18008FC7C
0x18008fc5d  lea     rcx, [rsp+128h+Src]; this
0x18008fc65  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008fc6a  nop
0x18008fc6b  lea     rcx, [rsp+128h+var_C8]
0x18008fc70  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008fc75  xor     eax, eax
0x18008fc77  jmp     loc_18008FF96
0x18008fc7c  call    cs:__imp_GetTickCount64
0x18008fc82  mov     r13, rax
0x18008fc85  lea     rax, LocaleName
0x18008fc8c  mov     rcx, r14
0x18008fc8f  test    r14, r14
0x18008fc92  cmovz   rcx, rax
0x18008fc96  mov     qword ptr [rsp+128h+var_F8], rcx
0x18008fc9b  mov     [rsp+128h+var_100], rsi
0x18008fca0  lea     rax, aServiceensurel_3; "ServiceEnsureLicenseForPackageActivatio"...
0x18008fca7  mov     [rsp+128h+Format], rax; Format
0x18008fcac  lea     r9, aServiceensurel_2; "ServiceEnsureLicenseForPackageActivatio"...
0x18008fcb3  mov     r8d, 990h; unsigned int
0x18008fcb9  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008fcc0  mov     ecx, 3; unsigned int
0x18008fcc5  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008fcca  nop
0x18008fccb  mov     r8, rdi
0x18008fcce  mov     edx, [rsp+128h+arg_20]
0x18008fcd5  lea     rcx, [rsp+128h+var_68]
0x18008fcdd  call    ?GetAppSessionIds@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEBU_GUID@@@Z; GetAppSessionIds(ulong,_GUID const * const)
0x18008fce2  nop
0x18008fce3  xor     edi, edi
0x18008fce5  mov     [rsp+128h+var_D8], rdi
0x18008fcea  lea     rcx, [rsp+128h+var_C0]; this
0x18008fcef  call    ??0PendingRequestManager@@QEAA@XZ; PendingRequestManager::PendingRequestManager(void)
0x18008fcf4  nop
0x18008fcf5  mov     dword ptr [rsp+128h+var_100], r15d
0x18008fcfa  mov     [rsp+128h+Format], r14
0x18008fcff  mov     r9, rsi
0x18008fd02  lea     r8, [rsp+128h+Src]
0x18008fd0a  lea     rdx, [rsp+128h+var_D0]
0x18008fd0f  call    ?FindExisting@PendingRequestManager@@QEAA?AV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1K@Z; PendingRequestManager::FindExisting(std::wstring const &,ushort const *,ushort const *,ulong)
0x18008fd14  mov     rdx, rax
0x18008fd17  lea     rcx, [rsp+128h+var_D8]
0x18008fd1c  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18008fd21  nop
0x18008fd22  mov     rcx, qword ptr [rsp+128h+var_D0]
0x18008fd27  test    rcx, rcx
0x18008fd2a  jz      short loc_18008FD3E
0x18008fd2c  mov     qword ptr [rsp+128h+var_D0], rdi
0x18008fd31  mov     rax, [rcx]
0x18008fd34  mov     rax, [rax+10h]
0x18008fd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd3d  nop
0x18008fd3e  mov     rbx, [rsp+128h+var_D8]
0x18008fd43  test    rbx, rbx
0x18008fd46  jnz     loc_18008FE3C
0x18008fd4c  lea     rdx, [rsp+128h+Src]
0x18008fd54  cmp     [rsp+128h+var_90], 7
0x18008fd5d  cmova   rdx, [rsp+128h+Src]
0x18008fd66  lea     rax, [rsp+128h+var_68]
0x18008fd6e  mov     [rsp+128h+Format], rax; __int64
0x18008fd73  mov     r9, r14
0x18008fd76  mov     r8d, r15d
0x18008fd79  mov     rcx, rsi; unsigned __int16 *
0x18008fd7c  call    ?LeaseRunningPackage@@YA_NPEBG0K0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LeaseRunningPackage(ushort const *,ushort const *,ulong,ushort const *,std::wstring const &)
0x18008fd81  test    al, al
0x18008fd83  jnz     loc_18008FE3C
0x18008fd89  mov     rdx, r12
0x18008fd8c  lea     rcx, [rsp+128h+var_B8]
0x18008fd91  call    ??0?$ImpersonationScope@URpcImpersonateClientTraits@@@@QEAA@PEAX@Z; ImpersonationScope<RpcImpersonateClientTraits>::ImpersonationScope<RpcImpersonateClientTraits>(void *)
0x18008fd96  nop
0x18008fd97  xorps   xmm0, xmm0
0x18008fd9a  movups  xmmword ptr [rsp+128h+var_88], xmm0
0x18008fda2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008fdaa  movdqu  [rsp+128h+var_78], xmm1
0x18008fdb3  mov     word ptr [rsp+128h+var_88], di
0x18008fdbb  mov     [rsp+128h+var_E0], dil; char
0x18008fdc0  lea     rax, [rsp+128h+var_88]
0x18008fdc8  mov     [rsp+128h+var_E8], rax; __int64
0x18008fdcd  mov     [rsp+128h+var_F0], edi; int
0x18008fdd1  mov     [rsp+128h+var_F8], r15d; int
0x18008fdd6  mov     [rsp+128h+var_100], r14; __int64
0x18008fddb  mov     [rsp+128h+Format], rdi; int
0x18008fde0  mov     r9, rsi; int
0x18008fde3  lea     r8, [rsp+128h+Src]; int
0x18008fdeb  lea     rdx, [rsp+128h+var_D0]; int
0x18008fdf0  call    ?AddRequest@PendingRequestManager@@QEAA?AV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG11KH0_N@Z; PendingRequestManager::AddRequest(std::wstring const &,ushort const *,ushort const *,ushort const *,ulong,int,std::wstring const &,bool)
0x18008fdf5  mov     rdx, rax
0x18008fdf8  lea     rcx, [rsp+128h+var_D8]
0x18008fdfd  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18008fe02  nop
0x18008fe03  mov     rcx, qword ptr [rsp+128h+var_D0]
0x18008fe08  test    rcx, rcx
0x18008fe0b  jz      short loc_18008FE1F
0x18008fe0d  mov     qword ptr [rsp+128h+var_D0], rdi
0x18008fe12  mov     rax, [rcx]
0x18008fe15  mov     rax, [rax+10h]
0x18008fe19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe1e  nop
0x18008fe1f  lea     rcx, [rsp+128h+var_88]; this
0x18008fe27  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008fe2c  nop
0x18008fe2d  lea     rcx, [rsp+128h+var_B8]
0x18008fe32  call    ??1?$ImpersonationScope@URpcImpersonateClientTraits@@@@QEAA@XZ; ImpersonationScope<RpcImpersonateClientTraits>::~ImpersonationScope<RpcImpersonateClientTraits>(void)
0x18008fe37  mov     rbx, [rsp+128h+var_D8]
0x18008fe3c  lea     rcx, [rsp+128h+var_C0]; this
0x18008fe41  call    ??1PendingRequestManager@@QEAA@XZ; PendingRequestManager::~PendingRequestManager(void)
0x18008fe46  test    rbx, rbx
0x18008fe49  jz      short loc_18008FEB8
0x18008fe4b  cmp     [rsp+128h+var_58], rdi
0x18008fe53  jnz     short loc_18008FE5A
0x18008fe55  mov     rdx, rdi
0x18008fe58  jmp     short loc_18008FE74
0x18008fe5a  lea     rdx, [rsp+128h+var_68]
0x18008fe62  cmp     [rsp+128h+var_50], 7
0x18008fe6b  cmova   rdx, [rsp+128h+var_68]; unsigned __int16 *
0x18008fe74  mov     rcx, rbx; this
0x18008fe77  call    ?WaitForResult@PendingRequest@@QEBAJPEBG@Z; PendingRequest::WaitForResult(ushort const *)
0x18008fe7c  mov     edi, eax
0x18008fe7e  lea     rdx, [rsp+128h+Src]
0x18008fe86  cmp     [rsp+128h+var_90], 7
0x18008fe8f  cmova   rdx, [rsp+128h+Src]; Src
0x18008fe98  mov     r9, r14; unsigned __int16 *
0x18008fe9b  mov     r8d, r15d; unsigned int
0x18008fe9e  mov     rcx, rsi; unsigned __int16 *
0x18008fea1  call    ?RemovePendingRequest@@YAXPEBG0K0@Z; RemovePendingRequest(ushort const *,ushort const *,ulong,ushort const *)
0x18008fea6  mov     rcx, [rsp+128h]; this
0x18008feae  test    edi, edi
0x18008feb0  js      loc_18008FFD1
0x18008feb6  xor     edi, edi
0x18008feb8  mov     eax, cs:dword_1800F11D0
0x18008febe  cmp     eax, 5
0x18008fec1  jbe     loc_18008FF52
0x18008fec7  mov     rdx, 200000000000h
0x18008fed1  lea     rcx, dword_1800F11D0
0x18008fed8  call    _tlgKeywordOn
0x18008fedd  test    al, al
0x18008fedf  jz      short loc_18008FF52
0x18008fee1  call    cs:__imp_GetTickCount64
0x18008fee7  mov     [rsp+128h+var_C0], rax
0x18008feec  call    cs:__imp_GetTickCount64
0x18008fef2  sub     rax, r13
0x18008fef5  mov     qword ptr [rsp+128h+var_D0], rax
0x18008fefa  mov     dword ptr [rsp+128h+var_D8], edi
0x18008fefe  lea     rax, [rsp+128h+Src]
0x18008ff06  cmp     [rsp+128h+var_90], 7
0x18008ff0f  cmova   rax, [rsp+128h+Src]
0x18008ff18  mov     [rsp+128h+var_B8], rax
0x18008ff1d  lea     rax, [rsp+128h+var_C0]
0x18008ff22  mov     qword ptr [rsp+128h+var_F0], rax
0x18008ff27  lea     rax, [rsp+128h+var_D0]
0x18008ff2c  mov     qword ptr [rsp+128h+var_F8], rax
0x18008ff31  lea     rax, [rsp+128h+var_D8]
0x18008ff36  mov     [rsp+128h+var_100], rax
0x18008ff3b  lea     rax, [rsp+128h+var_B8]
0x18008ff40  mov     [rsp+128h+Format], rax
0x18008ff45  lea     rdx, byte_1800D7287
0x18008ff4c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18008ff51  nop
0x18008ff52  test    rbx, rbx
0x18008ff55  jz      short loc_18008FF67
0x18008ff57  mov     rax, [rbx]
0x18008ff5a  mov     rcx, rbx
0x18008ff5d  mov     rax, [rax+10h]
0x18008ff61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ff66  nop
0x18008ff67  lea     rcx, [rsp+128h+var_68]; this
0x18008ff6f  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008ff74  nop
0x18008ff75  jmp     loc_18008FC5D
0x18008ff7a  lea     rcx, [rsp+128h+Src]; this
0x18008ff82  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008ff87  nop
0x18008ff88  lea     rcx, [rsp+128h+var_C8]
0x18008ff8d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008ff92  mov     eax, dword ptr [rsp+128h+var_D8]
0x18008ff96  mov     rcx, [rsp+128h+var_48]
0x18008ff9e  xor     rcx, rsp; StackCookie
0x18008ffa1  call    __security_check_cookie
0x18008ffa6  add     rsp, 0F0h
0x18008ffad  pop     r15
0x18008ffaf  pop     r14
0x18008ffb1  pop     r13
0x18008ffb3  pop     r12
0x18008ffb5  pop     rdi
0x18008ffb6  pop     rsi
0x18008ffb7  pop     rbx
0x18008ffb8  retn
0x18008ffb9  mov     r9d, 80004003h; char *
0x18008ffbf  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008ffc6  mov     edx, 98Bh; void *
0x18008ffcb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008ffd1  mov     r9d, edi; char *
0x18008ffd4  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008ffdb  mov     edx, 9ABh; void *
0x18008ffe0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
