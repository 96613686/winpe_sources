# ServicePrecacheLicenseForPackageResumeImpl(void *,ushort const *,ulong,ushort const *)

- ea: `0x1800901a4`
- end: `0x180090544`
- name: `?ServicePrecacheLicenseForPackageResumeImpl@@YAJPEAXPEBGK1@Z`
- size: `928`
- prototype: `int(void *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180084360`

## callees

- `0x18000295c`
- `0x180004738`
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
- `0x180055084`
- `0x180055d34`
- `0x1800593bc`
- `0x180066bac`
- `0x18006ad98`
- `0x180075e60`
- `0x18008e09c`
- `0x1800901a4`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090232`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009045e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090469`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090232`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009045e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180090469`

## string_xrefs

- `0x18009026f`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180090532`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180090256`: `ServicePrecacheLicenseForPackageResumeImpl PsmKey:%s, sid:%s`
- `0x180090262`: `ServicePrecacheLicenseForPackageResumeImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ServicePrecacheLicenseForPackageResumeImpl(
        void *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  ULONGLONG TickCount64; // r13
  const WCHAR *v10; // rcx
  __int64 v11; // rcx
  __int64 Existing; // rax
  __int64 v13; // rcx
  char v14; // si
  char *v15; // rbx
  const unsigned __int16 *v16; // rcx
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rcx
  const char *v20; // r9
  const unsigned __int16 *v21; // rdx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  unsigned __int16 **v25; // rax
  wil *v26; // rcx
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  unsigned __int16 **v30; // rax
  int Format; // [rsp+20h] [rbp-E8h]
  __int64 v32; // [rsp+28h] [rbp-E0h]
  int v33; // [rsp+30h] [rbp-D8h]
  void *Src; // [rsp+50h] [rbp-B8h] BYREF
  int v35[2]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v36[8]; // [rsp+60h] [rbp-A8h] BYREF
  ULONGLONG v37; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v38[2]; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 *v39[3]; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 v40; // [rsp+98h] [rbp-70h]
  __int64 v41[2]; // [rsp+A0h] [rbp-68h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  ProcessReference(v36);
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x94F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)0x80004003LL,
      Format);
  GetPackageFullNameFromPsmKey(v39);
  if ( !SkipForAppCompat((const WCHAR *)v39) )
  {
    TickCount64 = GetTickCount64();
    LODWORD(v10) = (_DWORD)a4;
    if ( !a4 )
      v10 = &LocaleName;
    v33 = (int)v10;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x955u,
      "ServicePrecacheLicenseForPackageResumeImpl",
      (wchar_t *)L"ServicePrecacheLicenseForPackageResumeImpl PsmKey:%s, sid:%s",
      a2);
    Src = 0;
    PendingRequestManager::PendingRequestManager((PendingRequestManager *)&v37);
    LODWORD(v32) = a3;
    try
    {
      Existing = PendingRequestManager::FindExisting(v11, v35, v39, a2, a4, v32, v33);
      Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(&Src, Existing);
      v13 = *(_QWORD *)v35;
      if ( *(_QWORD *)v35 )
      {
        *(_QWORD *)v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      v14 = 0;
      v15 = (char *)Src;
      if ( !Src )
      {
        v16 = (const unsigned __int16 *)v39;
        if ( v40 > 7 )
          v16 = v39[0];
        if ( !IsLicenseRunning(v16, a3, a4) )
        {
          ImpersonationScope<RpcImpersonateClientTraits>::ImpersonationScope<RpcImpersonateClientTraits>(v38, a1);
          *(_OWORD *)v41 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v41[0]) = 0;
          v14 = 1;
          v18 = PendingRequestManager::AddRequest(
                  v17,
                  (int)v35,
                  (int)v39,
                  (int)a2,
                  0,
                  (__int64)a4,
                  a3,
                  0,
                  (__int64)v41,
                  1);
          Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(&Src, v18);
          v19 = *(_QWORD *)v35;
          if ( *(_QWORD *)v35 )
          {
            *(_QWORD *)v35 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          ContentIdString::~ContentIdString((ContentIdString *)v41);
          ImpersonationScope<RpcImpersonateClientTraits>::~ImpersonationScope<RpcImpersonateClientTraits>(v38);
          v15 = (char *)Src;
        }
      }
      PendingRequestManager::~PendingRequestManager((PendingRequestManager *)&v37);
      if ( v15 )
      {
        if ( (int)PendingRequest::WaitForResult((PendingRequest *)v15, 0) < 0 )
        {
          v21 = (const unsigned __int16 *)v39;
          if ( v40 > 7 )
            v21 = v39[0];
          RemovePendingRequest(a2, v21, a3, a4);
        }
        else if ( v14 || v15[262] )
        {
          PendingRequest::CreateTimeoutTimer(v15);
        }
      }
      if ( (unsigned int)dword_1800F11D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
      {
        v37 = GetTickCount64();
        *(_QWORD *)v35 = GetTickCount64() - TickCount64;
        LODWORD(Src) = 0;
        v25 = v39;
        if ( v40 > 7 )
          v25 = (unsigned __int16 **)v39[0];
        v38[0] = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v22,
          (unsigned int)byte_1800D7359,
          v23,
          v24,
          (__int64)v38,
          (__int64)&Src,
          (__int64)v35,
          (__int64)&v37);
      }
      if ( v15 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    catch ( ... )
    {
      if ( (unsigned int)dword_1800F11D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x400000000000LL) )
      {
        LODWORD(Src) = wil::ResultFromCaughtException(v26);
        v30 = v39;
        if ( v40 > 7 )
          v30 = (unsigned __int16 **)v39[0];
        v38[0] = v30;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v27,
          (unsigned int)&byte_1800D7307,
          v28,
          v29,
          (__int64)v38,
          (__int64)&Src);
      }
      LODWORD(Src) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x981,
                       (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                       v20);
      ContentIdString::~ContentIdString((ContentIdString *)v39);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v36);
      return (unsigned int)Src;
    }
  }
  ContentIdString::~ContentIdString((ContentIdString *)v39);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v36);
  return 0;
}

```

## disassembly

```asm
0x1800901a4  push    rbx
0x1800901a6  push    rsi
0x1800901a7  push    rdi
0x1800901a8  push    r12
0x1800901aa  push    r13
0x1800901ac  push    r14
0x1800901ae  push    r15
0x1800901b0  sub     rsp, 0D0h
0x1800901b7  mov     rax, cs:__security_cookie
0x1800901be  xor     rax, rsp
0x1800901c1  mov     [rsp+108h+var_48], rax
0x1800901c9  mov     r14, r9
0x1800901cc  mov     r15d, r8d
0x1800901cf  mov     rdi, rdx
0x1800901d2  mov     r12, rcx
0x1800901d5  lea     rcx, [rsp+108h+var_A8]
0x1800901da  call    ?ProcessReference@@YA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; ProcessReference(void)
0x1800901df  nop
0x1800901e0  mov     rcx, [rsp+108h]; this
0x1800901e8  test    rdi, rdi
0x1800901eb  jz      loc_18009052C
0x1800901f1  mov     rdx, rdi
0x1800901f4  lea     rcx, [rsp+108h+var_88]
0x1800901fc  call    ?GetPackageFullNameFromPsmKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetPackageFullNameFromPsmKey(ushort const *)
0x180090201  nop
0x180090202  lea     rcx, [rsp+108h+var_88]
0x18009020a  call    ?SkipForAppCompat@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SkipForAppCompat(std::wstring const &)
0x18009020f  test    al, al
0x180090211  jz      short loc_180090232
0x180090213  lea     rcx, [rsp+108h+var_88]; this
0x18009021b  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180090220  nop
0x180090221  lea     rcx, [rsp+108h+var_A8]
0x180090226  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009022b  xor     eax, eax
0x18009022d  jmp     loc_180090509
0x180090232  call    cs:__imp_GetTickCount64
0x180090238  mov     r13, rax
0x18009023b  lea     rax, LocaleName
0x180090242  mov     rcx, r14
0x180090245  test    r14, r14
0x180090248  cmovz   rcx, rax
0x18009024c  mov     qword ptr [rsp+108h+var_D8], rcx
0x180090251  mov     [rsp+108h+var_E0], rdi
0x180090256  lea     rax, aServiceprecach_0; "ServicePrecacheLicenseForPackageResumeI"...
0x18009025d  mov     [rsp+108h+Format], rax; Format
0x180090262  lea     r9, aServiceprecach_1; "ServicePrecacheLicenseForPackageResumeI"...
0x180090269  mov     r8d, 955h; unsigned int
0x18009026f  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180090276  mov     ecx, 3; unsigned int
0x18009027b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180090280  nop
0x180090281  mov     [rsp+108h+Src], 0
0x18009028a  lea     rcx, [rsp+108h+var_A0]; this
0x18009028f  call    ??0PendingRequestManager@@QEAA@XZ; PendingRequestManager::PendingRequestManager(void)
0x180090294  nop
0x180090295  mov     dword ptr [rsp+108h+var_E0], r15d
0x18009029a  mov     [rsp+108h+Format], r14
0x18009029f  mov     r9, rdi
0x1800902a2  lea     r8, [rsp+108h+var_88]
0x1800902aa  lea     rdx, [rsp+108h+var_B0]
0x1800902af  call    ?FindExisting@PendingRequestManager@@QEAA?AV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG1K@Z; PendingRequestManager::FindExisting(std::wstring const &,ushort const *,ushort const *,ulong)
0x1800902b4  mov     rdx, rax
0x1800902b7  lea     rcx, [rsp+108h+Src]
0x1800902bc  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x1800902c1  nop
0x1800902c2  mov     rcx, qword ptr [rsp+108h+var_B0]
0x1800902c7  test    rcx, rcx
0x1800902ca  jz      short loc_1800902E2
0x1800902cc  mov     qword ptr [rsp+108h+var_B0], 0
0x1800902d5  mov     rax, [rcx]
0x1800902d8  mov     rax, [rax+10h]
0x1800902dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800902e1  nop
0x1800902e2  xor     sil, sil
0x1800902e5  mov     rbx, [rsp+108h+Src]
0x1800902ea  test    rbx, rbx
0x1800902ed  jnz     loc_1800903D8
0x1800902f3  lea     rcx, [rsp+108h+var_88]
0x1800902fb  cmp     [rsp+108h+var_70], 7
0x180090304  cmova   rcx, [rsp+108h+var_88]; unsigned __int16 *
0x18009030d  mov     r8, r14; unsigned __int16 *
0x180090310  mov     edx, r15d; unsigned int
0x180090313  call    ?IsLicenseRunning@@YA_NPEBGK0@Z; IsLicenseRunning(ushort const *,ulong,ushort const *)
0x180090318  test    al, al
0x18009031a  jnz     loc_1800903D8
0x180090320  mov     rdx, r12
0x180090323  lea     rcx, [rsp+108h+var_98]
0x180090328  call    ??0?$ImpersonationScope@URpcImpersonateClientTraits@@@@QEAA@PEAX@Z; ImpersonationScope<RpcImpersonateClientTraits>::ImpersonationScope<RpcImpersonateClientTraits>(void *)
0x18009032d  nop
0x18009032e  xorps   xmm0, xmm0
0x180090331  movups  xmmword ptr [rsp+108h+var_68], xmm0
0x180090339  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180090341  movdqu  [rsp+108h+var_58], xmm1
0x18009034a  xor     eax, eax
0x18009034c  mov     word ptr [rsp+108h+var_68], ax
0x180090354  mov     sil, 1
0x180090357  mov     [rsp+108h+var_C0], sil; char
0x18009035c  lea     rax, [rsp+108h+var_68]
0x180090364  mov     [rsp+108h+var_C8], rax; __int64
0x180090369  mov     [rsp+108h+var_D0], ebx; int
0x18009036d  mov     [rsp+108h+var_D8], r15d; int
0x180090372  mov     [rsp+108h+var_E0], r14; __int64
0x180090377  mov     [rsp+108h+Format], rbx; Src
0x18009037c  mov     r9, rdi; int
0x18009037f  lea     r8, [rsp+108h+var_88]; int
0x180090387  lea     rdx, [rsp+108h+var_B0]; int
0x18009038c  call    ?AddRequest@PendingRequestManager@@QEAA?AV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG11KH0_N@Z; PendingRequestManager::AddRequest(std::wstring const &,ushort const *,ushort const *,ushort const *,ulong,int,std::wstring const &,bool)
0x180090391  mov     rdx, rax
0x180090394  lea     rcx, [rsp+108h+Src]
0x180090399  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18009039e  nop
0x18009039f  mov     rcx, qword ptr [rsp+108h+var_B0]
0x1800903a4  test    rcx, rcx
0x1800903a7  jz      short loc_1800903BB
0x1800903a9  mov     qword ptr [rsp+108h+var_B0], rbx
0x1800903ae  mov     rax, [rcx]
0x1800903b1  mov     rax, [rax+10h]
0x1800903b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800903ba  nop
0x1800903bb  lea     rcx, [rsp+108h+var_68]; this
0x1800903c3  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800903c8  nop
0x1800903c9  lea     rcx, [rsp+108h+var_98]
0x1800903ce  call    ??1?$ImpersonationScope@URpcImpersonateClientTraits@@@@QEAA@XZ; ImpersonationScope<RpcImpersonateClientTraits>::~ImpersonationScope<RpcImpersonateClientTraits>(void)
0x1800903d3  mov     rbx, [rsp+108h+Src]
0x1800903d8  lea     rcx, [rsp+108h+var_A0]; this
0x1800903dd  call    ??1PendingRequestManager@@QEAA@XZ; PendingRequestManager::~PendingRequestManager(void)
0x1800903e2  test    rbx, rbx
0x1800903e5  jz      short loc_180090435
0x1800903e7  xor     edx, edx; unsigned __int16 *
0x1800903e9  mov     rcx, rbx; this
0x1800903ec  call    ?WaitForResult@PendingRequest@@QEBAJPEBG@Z; PendingRequest::WaitForResult(ushort const *)
0x1800903f1  test    eax, eax
0x1800903f3  js      short loc_18009040D
0x1800903f5  test    sil, sil
0x1800903f8  jnz     short loc_180090403
0x1800903fa  cmp     [rbx+106h], sil
0x180090401  jz      short loc_180090435
0x180090403  mov     rcx, rbx; Parameter
0x180090406  call    ?CreateTimeoutTimer@PendingRequest@@QEAAXXZ; PendingRequest::CreateTimeoutTimer(void)
0x18009040b  jmp     short loc_180090435
0x18009040d  lea     rdx, [rsp+108h+var_88]
0x180090415  cmp     [rsp+108h+var_70], 7
0x18009041e  cmova   rdx, [rsp+108h+var_88]; Src
0x180090427  mov     r9, r14; unsigned __int16 *
0x18009042a  mov     r8d, r15d; unsigned int
0x18009042d  mov     rcx, rdi; unsigned __int16 *
0x180090430  call    ?RemovePendingRequest@@YAXPEBG0K0@Z; RemovePendingRequest(ushort const *,ushort const *,ulong,ushort const *)
0x180090435  mov     eax, cs:dword_1800F11D0
0x18009043b  cmp     eax, 5
0x18009043e  jbe     loc_1800904D3
0x180090444  mov     rdx, 200000000000h
0x18009044e  lea     rcx, dword_1800F11D0
0x180090455  call    _tlgKeywordOn
0x18009045a  test    al, al
0x18009045c  jz      short loc_1800904D3
0x18009045e  call    cs:__imp_GetTickCount64
0x180090464  mov     [rsp+108h+var_A0], rax
0x180090469  call    cs:__imp_GetTickCount64
0x18009046f  sub     rax, r13
0x180090472  mov     qword ptr [rsp+108h+var_B0], rax
0x180090477  mov     dword ptr [rsp+108h+Src], 0
0x18009047f  lea     rax, [rsp+108h+var_88]
0x180090487  cmp     [rsp+108h+var_70], 7
0x180090490  cmova   rax, [rsp+108h+var_88]
0x180090499  mov     [rsp+108h+var_98], rax
0x18009049e  lea     rax, [rsp+108h+var_A0]
0x1800904a3  mov     qword ptr [rsp+108h+var_D0], rax
0x1800904a8  lea     rax, [rsp+108h+var_B0]
0x1800904ad  mov     qword ptr [rsp+108h+var_D8], rax
0x1800904b2  lea     rax, [rsp+108h+Src]
0x1800904b7  mov     [rsp+108h+var_E0], rax
0x1800904bc  lea     rax, [rsp+108h+var_98]
0x1800904c1  mov     [rsp+108h+Format], rax
0x1800904c6  lea     rdx, byte_1800D7359
0x1800904cd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800904d2  nop
0x1800904d3  test    rbx, rbx
0x1800904d6  jz      short loc_1800904E8
0x1800904d8  mov     rax, [rbx]
0x1800904db  mov     rcx, rbx
0x1800904de  mov     rax, [rax+10h]
0x1800904e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800904e7  nop
0x1800904e8  jmp     loc_180090213
0x1800904ed  lea     rcx, [rsp+108h+var_88]; this
0x1800904f5  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x1800904fa  nop
0x1800904fb  lea     rcx, [rsp+108h+var_A8]
0x180090500  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090505  mov     eax, dword ptr [rsp+108h+Src]
0x180090509  mov     rcx, [rsp+108h+var_48]
0x180090511  xor     rcx, rsp; StackCookie
0x180090514  call    __security_check_cookie
0x180090519  add     rsp, 0D0h
0x180090520  pop     r15
0x180090522  pop     r14
0x180090524  pop     r13
0x180090526  pop     r12
0x180090528  pop     rdi
0x180090529  pop     rsi
0x18009052a  pop     rbx
0x18009052b  retn
0x18009052c  mov     r9d, 80004003h; char *
0x180090532  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180090539  mov     edx, 94Fh; void *
0x18009053e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
