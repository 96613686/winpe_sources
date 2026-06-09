# PendingRequest::ThreadProc(void)

- ea: `0x180029664`
- end: `0x180029b17`
- name: `?ThreadProc@PendingRequest@@QEAAXXZ`
- size: `1203`
- prototype: `void __fastcall(PendingRequest *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029620`

## callees

- `0x180004738`
- `0x18000b7fc`
- `0x180013b50`
- `0x180029664`
- `0x180048760`
- `0x180054a54`
- `0x180056c58`
- `0x180056ca8`
- `0x1800593bc`
- `0x180059764`
- `0x180069b80`
- `0x18006a3b0`
- `0x180075e60`
- `0x180076e64`
- `0x18008ea14`
- `0x180090f34`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800298cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800298cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029a21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029a21`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029ae4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029ae4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800296a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029ac2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800296a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029ac2`
- `ext-ms-win-core-licensemanager-l1-1-0!LicenseInstanceRequiredWhileActive` at `0x1800298ed`
- `ext-ms-win-core-licensemanager-l1-1-0!LicenseInstanceRequiredWhileActive` at `0x1800298ed`

## string_xrefs

- `0x180029788`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18002981b`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180029865`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800298aa`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18002991e`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180029a76`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180029a69`: `PendingRequest::ThreadProc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall PendingRequest::ThreadProc(PendingRequest *this)
{
  PendingRequest *v1; // rdi
  char v2; // r12
  ULONGLONG TickCount64; // rax
  __int64 v4; // rcx
  unsigned int *v5; // r13
  __int64 v6; // r8
  _QWORD *v7; // rdx
  __int128 *v8; // rcx
  unsigned int v9; // eax
  _QWORD *v10; // r15
  __int128 *v11; // rdx
  int v12; // eax
  const char *v13; // r9
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  _QWORD *v18; // r8
  unsigned __int16 *v19; // rsi
  unsigned __int16 *v20; // rcx
  const WCHAR *v21; // rdx
  const WCHAR *v22; // rax
  PackageLicense *v23; // r9
  __int64 v24; // rcx
  _QWORD *v25; // rax
  ULONGLONG v26; // rax
  wil *v27; // rcx
  int v28; // eax
  unsigned int Format; // [rsp+20h] [rbp-B8h]
  int Formata; // [rsp+20h] [rbp-B8h]
  char v31; // [rsp+40h] [rbp-98h]
  __int64 v32; // [rsp+48h] [rbp-90h] BYREF
  int v33; // [rsp+50h] [rbp-88h] BYREF
  __int64 v34; // [rsp+58h] [rbp-80h] BYREF
  PendingRequest *v35; // [rsp+60h] [rbp-78h]
  unsigned int *v36; // [rsp+68h] [rbp-70h]
  ULONGLONG v37; // [rsp+70h] [rbp-68h]
  char *v38; // [rsp+78h] [rbp-60h]
  __int128 v39; // [rsp+80h] [rbp-58h] BYREF
  __m128i si128; // [rsp+90h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v1 = this;
  v35 = this;
  v2 = 0;
  v31 = 0;
  TickCount64 = GetTickCount64();
  try
  {
    v37 = TickCount64;
    v5 = (unsigned int *)((char *)v1 + 256);
    v36 = (unsigned int *)((char *)v1 + 256);
    *((_DWORD *)v1 + 64) = 0;
    v39 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v39) = 0;
    v6 = *((_QWORD *)v1 + 15);
    if ( v6 )
    {
      v7 = (_QWORD *)((char *)v1 + 104);
      if ( &v39 == (__int128 *)((char *)v1 + 104) )
        goto LABEL_11;
      if ( *((_QWORD *)v1 + 16) > 7u )
        v7 = (_QWORD *)*v7;
    }
    else
    {
      v7 = (_QWORD *)((char *)v1 + 72);
      if ( &v39 == (__int128 *)((char *)v1 + 72) )
        goto LABEL_11;
      v6 = *((_QWORD *)v1 + 11);
      if ( *((_QWORD *)v1 + 12) > 7u )
        v7 = (_QWORD *)*v7;
    }
    std::wstring::_Assign<unsigned short>(&v39, v7, v6);
LABEL_11:
    v33 = 0;
    if ( (unsigned __int8)IsCompareContentIdPresent(v4) )
    {
      v33 = 3;
    }
    else
    {
      v8 = &v39;
      if ( si128.m128i_i64[1] > 7uLL )
        v8 = (__int128 *)v39;
      v9 = ((__int64 (__fastcall *)(__int128 *, int *))_GetStagedPackageOrigin)(v8, &v33);
      if ( v9 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x6FD,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          (const char *)v9,
          Format);
      if ( v33 != 3 )
      {
        v25 = (_QWORD *)((char *)v1 + 72);
        if ( *((_QWORD *)v1 + 12) > 7u )
          v25 = (_QWORD *)*v25;
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          0x731u,
          "PendingRequest::ThreadProc",
          (wchar_t *)L"Ignoring license request for package %s with origin %d",
          v25,
          v33);
        goto LABEL_63;
      }
    }
    v2 = 1;
    v31 = 1;
    CreateApplicationLicenseManager(&v34);
    v10 = (_QWORD *)((char *)v1 + 64);
    v11 = &v39;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (__int128 *)v39;
    Formata = (_DWORD)v1 + 64;
    v12 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v34 + 48LL))(
            v34,
            v11,
            0,
            *((_BYTE *)v1 + 260) != 0 ? 0x10000000 : 0x20000000);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x704,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v12,
        Formata);
    if ( *v10 )
    {
      if ( *((_QWORD *)v1 + 23) )
      {
        v32 = 0;
        v14 = Microsoft::WRL::ComPtr<IApplicationLicenseManager>::As<IAppLicenseManagerInternal>(&v34, &v32);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x70A,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v14,
            Formata);
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 48LL))(v32, *v10);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x70B,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v15,
            Formata);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
      v38 = (char *)v1 + 16;
      if ( !*((_BYTE *)v1 + 261) )
      {
        if ( (unsigned __int8)IsCompareContentIdPresent(v16) && (unsigned int)LicenseInstanceRequiredWhileActive() )
          goto LABEL_76;
        LODWORD(v32) = 0;
        v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v10 + 96LL))(*v10, &v32);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x71B,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            (const char *)(unsigned int)v17,
            Formata);
        if ( (int)v32 >= 1 )
        {
LABEL_76:
          if ( *((_QWORD *)v1 + 15) )
            goto LABEL_47;
          v32 = *v10;
          Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v32);
          v18 = (_QWORD *)((char *)v1 + 136);
          if ( *((_QWORD *)v1 + 20) > 7u )
            v18 = (_QWORD *)*v18;
          v19 = (unsigned __int16 *)((char *)v1 + 72);
          v20 = (unsigned __int16 *)((char *)v1 + 72);
          if ( *((_QWORD *)v1 + 12) > 7u )
            v20 = *(unsigned __int16 **)v19;
          if ( (unsigned __int8)ShouldPublishWnfForTrialLicense(v20, *((unsigned int *)v1 + 54), v18, &v32) )
          {
            v32 = *v10;
            Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v32);
            if ( *((_QWORD *)v1 + 12) > 7u )
              v19 = *(unsigned __int16 **)v19;
            PublishWnfForTrialLicense(v19, &v32);
          }
          if ( *((_QWORD *)v1 + 15) )
          {
LABEL_47:
            v22 = (const WCHAR *)((char *)v1 + 104);
            if ( *((_QWORD *)v1 + 16) > 7u )
              v22 = *(const WCHAR **)v22;
            v21 = (const WCHAR *)((char *)v1 + 72);
          }
          else
          {
            v21 = (const WCHAR *)((char *)v1 + 72);
            v22 = (const WCHAR *)((char *)v1 + 72);
            if ( *((_QWORD *)v1 + 12) > 7u )
              v22 = *(const WCHAR **)v21;
          }
          v23 = (PendingRequest *)((char *)v1 + 136);
          if ( *((_QWORD *)v1 + 20) > 7u )
            v23 = *(PackageLicense **)v23;
          if ( *((_QWORD *)v21 + 3) > 7u )
            v21 = *(const WCHAR **)v21;
          AddLicense((_BYTE *)v1 + 200, v21, *((_DWORD *)v1 + 54), v23, v22, (_QWORD *)v1 + 8);
        }
      }
      if ( v1 != (PendingRequest *)-16LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
    }
    v24 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
LABEL_63:
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v39, 2 * si128.m128i_i64[1] + 2);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x736,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      v13);
    v28 = wil::ResultFromCaughtException(v27);
    *((_DWORD *)v35 + 64) = v28;
    v2 = v31;
    v5 = v36;
    v1 = v35;
  }
  if ( v2 )
  {
    v26 = GetTickCount64();
    LogReactiveLicensingResult(*v5, (char *)v1 + 72, v26 - v37);
  }
  SetEvent(*((HANDLE *)v1 + 29));
}

```

## disassembly

```asm
0x180029664  mov     [rsp+arg_8], rbx
0x180029669  mov     [rsp+arg_10], rsi
0x18002966e  push    rdi
0x18002966f  push    r12
0x180029671  push    r13
0x180029673  push    r14
0x180029675  push    r15
0x180029677  sub     rsp, 0B0h
0x18002967e  mov     rax, cs:__security_cookie
0x180029685  xor     rax, rsp
0x180029688  mov     [rsp+0D8h+var_38], rax
0x180029690  mov     rdi, rcx
0x180029693  mov     [rsp+0D8h+var_78], rcx
0x180029698  xor     ebx, ebx
0x18002969a  mov     r12b, bl
0x18002969d  mov     [rsp+0D8h+var_98], bl
0x1800296a1  call    cs:__imp_GetTickCount64
0x1800296a7  mov     [rsp+0D8h+var_68], rax
0x1800296ac  lea     r13, [rdi+100h]
0x1800296b3  mov     [rsp+0D8h+var_70], r13
0x1800296b8  mov     [r13+0], ebx
0x1800296bc  xorps   xmm0, xmm0
0x1800296bf  movups  [rsp+0D8h+var_58], xmm0
0x1800296c7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800296cf  movdqu  [rsp+0D8h+var_48], xmm1
0x1800296d8  mov     word ptr [rsp+0D8h+var_58], bx
0x1800296e0  mov     r8, [rdi+78h]
0x1800296e4  lea     rax, [rsp+0D8h+var_58]
0x1800296ec  test    r8, r8
0x1800296ef  jz      short loc_180029713
0x1800296f1  lea     rdx, [rdi+68h]
0x1800296f5  cmp     rax, rdx
0x1800296f8  jz      short loc_180029737
0x1800296fa  cmp     qword ptr [rdx+18h], 7
0x1800296ff  jbe     short loc_180029704
0x180029701  mov     rdx, [rdx]
0x180029704  lea     rcx, [rsp+0D8h+var_58]
0x18002970c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180029711  jmp     short loc_180029737
0x180029713  lea     rdx, [rdi+48h]
0x180029717  cmp     rax, rdx
0x18002971a  jz      short loc_180029737
0x18002971c  mov     r8, [rdx+10h]
0x180029720  cmp     qword ptr [rdx+18h], 7
0x180029725  jbe     short loc_18002972A
0x180029727  mov     rdx, [rdx]
0x18002972a  lea     rcx, [rsp+0D8h+var_58]
0x180029732  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180029737  mov     [rsp+0D8h+var_88], ebx
0x18002973b  call    IsCompareContentIdPresent
0x180029740  test    al, al
0x180029742  jz      short loc_18002974E
0x180029744  mov     [rsp+0D8h+var_88], 3
0x18002974c  jmp     short loc_1800297A6
0x18002974e  lea     rcx, [rsp+0D8h+var_58]
0x180029756  cmp     qword ptr [rsp+0D8h+var_48+8], 7
0x18002975f  cmova   rcx, qword ptr [rsp+0D8h+var_58]
0x180029768  lea     rdx, [rsp+0D8h+var_88]
0x18002976d  mov     rax, cs:?_GetStagedPackageOrigin@@3P6AJPEBGPEAW4_PackageOrigin@@@ZEA; long (*_GetStagedPackageOrigin)(ushort const *,_PackageOrigin *)
0x180029774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029779  mov     rcx, [rsp+0D8h]; this
0x180029781  test    eax, eax
0x180029783  jz      short loc_180029799
0x180029785  mov     r9d, eax; char *
0x180029788  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002978f  mov     edx, 6FDh; void *
0x180029794  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180029799  mov     ecx, [rsp+0D8h+var_88]
0x18002979d  cmp     ecx, 3
0x1800297a0  jnz     loc_180029A46
0x1800297a6  mov     r12b, 1
0x1800297a9  mov     [rsp+0D8h+var_98], r12b
0x1800297ae  lea     rcx, [rsp+0D8h+var_80]
0x1800297b3  call    ?CreateApplicationLicenseManager@@YA?AV?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@XZ; CreateApplicationLicenseManager(void)
0x1800297b8  nop
0x1800297b9  mov     rcx, [rsp+0D8h+var_80]
0x1800297be  mov     rax, [rcx]
0x1800297c1  mov     r10, [rax+30h]
0x1800297c5  lea     r15, [rdi+40h]
0x1800297c9  mov     al, [rdi+104h]
0x1800297cf  neg     al
0x1800297d1  sbb     r9d, r9d
0x1800297d4  and     r9d, 0F0000000h
0x1800297db  add     r9d, 20000000h
0x1800297e2  lea     rdx, [rsp+0D8h+var_58]
0x1800297ea  cmp     qword ptr [rsp+0D8h+var_48+8], 7
0x1800297f3  cmova   rdx, qword ptr [rsp+0D8h+var_58]
0x1800297fc  mov     [rsp+0D8h+Format], r15; int
0x180029801  xor     r8d, r8d
0x180029804  mov     rax, r10
0x180029807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002980c  mov     rcx, [rsp+0D8h]; this
0x180029814  test    eax, eax
0x180029816  jns     short loc_18002982C
0x180029818  mov     r9d, eax; char *
0x18002981b  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180029822  mov     edx, 704h; void *
0x180029827  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002982c  cmp     [r15], rbx
0x18002982f  jz      loc_180029A28
0x180029835  cmp     [rdi+0B8h], rbx
0x18002983c  jz      loc_1800298C6
0x180029842  mov     [rsp+0D8h+var_90], rbx
0x180029847  lea     rdx, [rsp+0D8h+var_90]
0x18002984c  lea     rcx, [rsp+0D8h+var_80]
0x180029851  call    ??$As@UIAppLicenseManagerInternal@@@?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppLicenseManagerInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IApplicationLicenseManager>::As<IAppLicenseManagerInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppLicenseManagerInternal>>)
0x180029856  mov     rcx, [rsp+0D8h]; this
0x18002985e  test    eax, eax
0x180029860  jns     short loc_180029876
0x180029862  mov     r9d, eax; char *
0x180029865  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002986c  mov     edx, 70Ah; void *
0x180029871  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029876  mov     rcx, [rsp+0D8h+var_90]
0x18002987b  mov     rax, [rcx]
0x18002987e  lea     r8, [rdi+0A8h]
0x180029885  cmp     qword ptr [r8+18h], 7
0x18002988a  jbe     short loc_18002988F
0x18002988c  mov     r8, [r8]
0x18002988f  mov     rdx, [r15]
0x180029892  mov     rax, [rax+30h]
0x180029896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002989b  mov     rcx, [rsp+0D8h]; this
0x1800298a3  test    eax, eax
0x1800298a5  jns     short loc_1800298BC
0x1800298a7  mov     r9d, eax; char *
0x1800298aa  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800298b1  mov     edx, 70Bh; void *
0x1800298b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800298bc  lea     rcx, [rsp+0D8h+var_90]
0x1800298c1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800298c6  lea     r14, [rdi+10h]
0x1800298ca  mov     rcx, r14; lpCriticalSection
0x1800298cd  call    cs:__imp_EnterCriticalSection
0x1800298d3  mov     [rsp+0D8h+var_60], r14
0x1800298d8  cmp     [rdi+105h], bl
0x1800298de  jnz     loc_180029A19
0x1800298e4  call    IsCompareContentIdPresent
0x1800298e9  test    al, al
0x1800298eb  jz      short loc_1800298F7
0x1800298ed  call    cs:__imp_LicenseInstanceRequiredWhileActive
0x1800298f3  test    eax, eax
0x1800298f5  jnz     short loc_18002993A
0x1800298f7  mov     dword ptr [rsp+0D8h+var_90], ebx
0x1800298fb  mov     rcx, [r15]
0x1800298fe  mov     rax, [rcx]
0x180029901  lea     rdx, [rsp+0D8h+var_90]
0x180029906  mov     rax, [rax+60h]
0x18002990a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002990f  mov     rcx, [rsp+0D8h]; this
0x180029917  test    eax, eax
0x180029919  jns     short loc_18002992F
0x18002991b  mov     r9d, eax; char *
0x18002991e  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180029925  mov     edx, 71Bh; void *
0x18002992a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002992f  cmp     dword ptr [rsp+0D8h+var_90], 1
0x180029934  jl      loc_180029A19
0x18002993a  cmp     [rdi+78h], rbx
0x18002993e  jnz     loc_1800299CE
0x180029944  mov     rax, [r15]
0x180029947  mov     [rsp+0D8h+var_90], rax
0x18002994c  lea     rcx, [rsp+0D8h+var_90]
0x180029951  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x180029956  lea     r8, [rdi+88h]
0x18002995d  cmp     qword ptr [r8+18h], 7
0x180029962  jbe     short loc_180029967
0x180029964  mov     r8, [r8]
0x180029967  lea     rsi, [rdi+48h]
0x18002996b  mov     rcx, rsi
0x18002996e  cmp     qword ptr [rsi+18h], 7
0x180029973  jbe     short loc_180029978
0x180029975  mov     rcx, [rsi]
0x180029978  lea     r9, [rsp+0D8h+var_90]
0x18002997d  mov     edx, [rdi+0D8h]
0x180029983  call    ?ShouldPublishWnfForTrialLicense@@YA_NPEBGK0V?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z; ShouldPublishWnfForTrialLicense(ushort const *,ulong,ushort const *,Microsoft::WRL::ComPtr<ILicenseInstance>)
0x180029988  test    al, al
0x18002998a  jz      short loc_1800299B5
0x18002998c  mov     rax, [r15]
0x18002998f  mov     [rsp+0D8h+var_90], rax
0x180029994  lea     rcx, [rsp+0D8h+var_90]
0x180029999  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18002999e  cmp     qword ptr [rsi+18h], 7
0x1800299a3  jbe     short loc_1800299A8
0x1800299a5  mov     rsi, [rsi]
0x1800299a8  lea     rdx, [rsp+0D8h+var_90]
0x1800299ad  mov     rcx, rsi; unsigned __int16 *
0x1800299b0  call    ?PublishWnfForTrialLicense@@YAXPEBGV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z; PublishWnfForTrialLicense(ushort const *,Microsoft::WRL::ComPtr<ILicenseInstance>)
0x1800299b5  cmp     [rdi+78h], rbx
0x1800299b9  jnz     short loc_1800299CE
0x1800299bb  lea     rdx, [rdi+48h]
0x1800299bf  mov     rax, rdx
0x1800299c2  cmp     qword ptr [rdx+18h], 7
0x1800299c7  jbe     short loc_1800299E0
0x1800299c9  mov     rax, [rdx]
0x1800299cc  jmp     short loc_1800299E0
0x1800299ce  lea     rax, [rdi+68h]
0x1800299d2  cmp     qword ptr [rax+18h], 7
0x1800299d7  jbe     short loc_1800299DC
0x1800299d9  mov     rax, [rax]
0x1800299dc  lea     rdx, [rdi+48h]
0x1800299e0  lea     r9, [rdi+88h]
0x1800299e7  cmp     qword ptr [r9+18h], 7
0x1800299ec  jbe     short loc_1800299F1
0x1800299ee  mov     r9, [r9]
0x1800299f1  cmp     qword ptr [rdx+18h], 7
0x1800299f6  jbe     short loc_1800299FB
0x1800299f8  mov     rdx, [rdx]
0x1800299fb  lea     rcx, [rdi+0C8h]
0x180029a02  mov     [rsp+0D8h+var_B0], r15
0x180029a07  mov     [rsp+0D8h+Format], rax
0x180029a0c  mov     r8d, [rdi+0D8h]
0x180029a13  call    ?AddLicense@@YAXAEBV?$set@UPsmKeyCompat@@U?$less@UPsmKeyCompat@@@std@@V?$allocator@UPsmKeyCompat@@@3@@std@@PEBGK11AEAV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z; AddLicense(std::set<PsmKeyCompat> const &,ushort const *,ulong,ushort const *,ushort const *,Microsoft::WRL::ComPtr<ILicenseInstance> &)
0x180029a18  nop
0x180029a19  test    r14, r14
0x180029a1c  jz      short loc_180029A28
0x180029a1e  mov     rcx, r14; lpCriticalSection
0x180029a21  call    cs:__imp_LeaveCriticalSection
0x180029a27  nop
0x180029a28  mov     rcx, [rsp+0D8h+var_80]
0x180029a2d  test    rcx, rcx
0x180029a30  jz      short loc_180029A44
0x180029a32  mov     [rsp+0D8h+var_80], rbx
0x180029a37  mov     rax, [rcx]
0x180029a3a  mov     rax, [rax+10h]
0x180029a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a43  nop
0x180029a44  jmp     short loc_180029A88
0x180029a46  lea     rax, [rdi+48h]
0x180029a4a  cmp     qword ptr [rax+18h], 7
0x180029a4f  jbe     short loc_180029A54
0x180029a51  mov     rax, [rax]
0x180029a54  mov     [rsp+0D8h+var_A8], ecx
0x180029a58  mov     [rsp+0D8h+var_B0], rax
0x180029a5d  lea     rax, aIgnoringLicens; "Ignoring license request for package %s"...
0x180029a64  mov     [rsp+0D8h+Format], rax; Format
0x180029a69  lea     r9, aPendingrequest; "PendingRequest::ThreadProc"
0x180029a70  mov     r8d, 731h; unsigned int
0x180029a76  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180029a7d  mov     ecx, 1; unsigned int
0x180029a82  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180029a87  nop
0x180029a88  mov     rdx, qword ptr [rsp+0D8h+var_48+8]
0x180029a90  cmp     rdx, 7
0x180029a94  jbe     short loc_180029AAC
0x180029a96  lea     rdx, ds:2[rdx*2]
0x180029a9e  mov     rcx, qword ptr [rsp+0D8h+var_58]
0x180029aa6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180029aab  nop
0x180029aac  jmp     short loc_180029ABD
0x180029aae  mov     r12b, [rsp+0D8h+var_98]
0x180029ab3  mov     r13, [rsp+0D8h+var_70]
0x180029ab8  mov     rdi, [rsp+0D8h+var_78]
0x180029abd  test    r12b, r12b
0x180029ac0  jz      short loc_180029ADD
0x180029ac2  call    cs:__imp_GetTickCount64
0x180029ac8  sub     rax, [rsp+0D8h+var_68]
0x180029acd  lea     rdx, [rdi+48h]
0x180029ad1  mov     r8, rax
0x180029ad4  mov     ecx, [r13+0]
0x180029ad8  call    ?LogReactiveLicensingResult@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; LogReactiveLicensingResult(long,std::wstring const &,unsigned __int64)
0x180029add  mov     rcx, [rdi+0E8h]; hEvent
0x180029ae4  call    cs:__imp_SetEvent
0x180029aea  mov     rcx, [rsp+0D8h+var_38]
0x180029af2  xor     rcx, rsp; StackCookie
0x180029af5  call    __security_check_cookie
0x180029afa  lea     r11, [rsp+0D8h+var_28]
0x180029b02  mov     rbx, [r11+38h]
0x180029b06  mov     rsi, [r11+40h]
0x180029b0a  mov     rsp, r11
0x180029b0d  pop     r15
0x180029b0f  pop     r14
0x180029b11  pop     r13
0x180029b13  pop     r12
0x180029b15  pop     rdi
0x180029b16  retn
```
