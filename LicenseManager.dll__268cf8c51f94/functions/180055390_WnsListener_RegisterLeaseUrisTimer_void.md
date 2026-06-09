# WnsListener::RegisterLeaseUrisTimer(void)

- ea: `0x180055390`
- end: `0x1800556df`
- name: `?RegisterLeaseUrisTimer@WnsListener@@EEAAXXZ`
- size: `847`
- prototype: `void __fastcall(WnsListener *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000b7a4`
- `0x180012dc0`
- `0x180013b50`
- `0x180017654`
- `0x1800369e4`
- `0x180055390`
- `0x1800556e8`
- `0x180055e28`
- `0x180065908`
- `0x1800721e0`
- `0x180075e60`
- `0x18008df08`
- `0x180090fac`
- `0x18009c848`
- `0x18009ccb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800553f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055434`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800554bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055528`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800553f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055434`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800554bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055528`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005540c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005547f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800554e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055625`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005540c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005547f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800554e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055625`

## string_xrefs

- `0x1800553c4`: `RegisterLeaseUrisTimer`
- `0x1800553d0`: `WnsListener::RegisterLeaseUrisTimer`
- `0x1800555f1`: `WnsListener::RegisterLeaseUrisTimer`
- `0x180055685`: `WnsListener::RegisterLeaseUrisTimer`
- `0x1800555e5`: `WNS lease registration completed with %d leases remaining, scheduling retry`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall WnsListener::RegisterLeaseUrisTimer(WnsListener *this)
{
  _QWORD *v2; // r14
  __int64 v3; // rsi
  __int64 v4; // r15
  char *i; // rsi
  __int64 v6; // r12
  __int64 v7; // r15
  __int64 j; // r13
  __int64 v9; // rax
  wil *v10; // rcx
  const char *v11; // r9
  __int64 v12; // [rsp+28h] [rbp-C0h]
  __int64 v13; // [rsp+30h] [rbp-B8h] BYREF
  char *v14; // [rsp+38h] [rbp-B0h]
  WnsListener *v15; // [rsp+40h] [rbp-A8h]
  __int128 v16; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-90h]
  __int128 v18; // [rsp+60h] [rbp-88h] BYREF
  __int64 v19; // [rsp+70h] [rbp-78h]
  _QWORD v20[4]; // [rsp+78h] [rbp-70h] BYREF
  _OWORD v21[2]; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v15 = this;
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
    0x2B3u,
    "WnsListener::RegisterLeaseUrisTimer",
    (wchar_t *)L"RegisterLeaseUrisTimer");
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close((char *)this + 72);
  if ( this != (WnsListener *)-16LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_BYTE *)this + 188) )
  {
    v18 = 0;
    v19 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    try
    {
      v14 = (char *)this + 16;
      v2 = (_QWORD *)((char *)this + 160);
      if ( &v18 != (__int128 *)((char *)this + 160) )
        std::vector<ActiveLease>::_Assign_counted_range<ActiveLease *>(
          &v18,
          *v2,
          0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 21) - *((_QWORD *)this + 20)) >> 3));
      if ( this != (WnsListener *)-16LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v16 = 0;
      v17 = 0;
      v21[0] = 0;
      v21[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v21[0]) = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v14 = (char *)this + 16;
      std::wstring::operator=(v21, (char *)this + 96);
      if ( this != (WnsListener *)-16LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      WnsListener::DoRegisterLeaseUris(v20, v21, &v18);
      v3 = v20[0];
      v4 = v20[1];
      while ( v3 != v4 )
      {
        std::vector<ActiveLease>::push_back(&v16, v3);
        v3 += 40;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v20[3] = (char *)this + 16;
      v14 = (char *)*((_QWORD *)&v16 + 1);
      for ( i = (char *)v16; i != v14; i += 40 )
      {
        std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ActiveLease>>>,ActiveLease>(
          &v13,
          *v2,
          *((_QWORD *)this + 21),
          i);
        v6 = *((_QWORD *)this + 21);
        v7 = v13;
        if ( v13 != v6 )
        {
          for ( j = v13 + 40; j != v6; j += 40 )
          {
            std::wstring::operator=(v7, j);
            Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::operator=(v7 + 32, j + 32);
            v7 += 40;
          }
          ActiveLease::`scalar deleting destructor'((ActiveLease *)(*((_QWORD *)this + 21) - 40LL), 0);
          *((_QWORD *)this + 21) -= 40LL;
        }
      }
      v9 = *((_QWORD *)this + 21);
      if ( *v2 != v9 )
      {
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          0x2EAu,
          "WnsListener::RegisterLeaseUrisTimer",
          (wchar_t *)L"WNS lease registration completed with %d leases remaining, scheduling retry",
          0xCCCCCCCCCCCCCCCDuLL * ((v9 - *v2) >> 3));
        WnsListener::ResetLeaseCallbackRegistrationTimer(this, 0xEA60u);
      }
      if ( this != (WnsListener *)-16LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      std::vector<ActiveLease>::_Tidy(v20);
      ContentIdString::~ContentIdString((ContentIdString *)v21);
      std::vector<ActiveLease>::_Tidy(&v16);
      std::vector<ActiveLease>::_Tidy(&v18);
    }
    catch ( ... )
    {
      LODWORD(v13) = wil::ResultFromCaughtException(v10);
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2F2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
        v11);
      if ( (int)(v13 + 0x80000000) >= 0 && (_DWORD)v13 != -2147467263 )
      {
        LODWORD(v12) = v13;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          0x2F7u,
          "WnsListener::RegisterLeaseUrisTimer",
          (wchar_t *)L"WNS lease registration failed 0x%08X, scheduling retry",
          v12);
        WnsListener::ResetLeaseCallbackRegistrationTimer(v15, 0xEA60u);
      }
    }
  }
}

```

## disassembly

```asm
0x180055390  mov     [rsp+arg_8], rbx
0x180055395  mov     [rsp+arg_10], rsi
0x18005539a  push    rdi
0x18005539b  push    r12
0x18005539d  push    r13
0x18005539f  push    r14
0x1800553a1  push    r15
0x1800553a3  sub     rsp, 0C0h
0x1800553aa  mov     rax, cs:__security_cookie
0x1800553b1  xor     rax, rsp
0x1800553b4  mov     [rsp+0E8h+var_30], rax
0x1800553bc  mov     rdi, rcx
0x1800553bf  mov     [rsp+0E8h+var_A8], rcx
0x1800553c4  lea     rax, aRegisterleaseu; "RegisterLeaseUrisTimer"
0x1800553cb  mov     [rsp+0E8h+Format], rax; Format
0x1800553d0  lea     r9, aWnslistenerReg; "WnsListener::RegisterLeaseUrisTimer"
0x1800553d7  mov     r8d, 2B3h; unsigned int
0x1800553dd  lea     rdx, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800553e4  mov     ecx, 3; unsigned int
0x1800553e9  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800553ee  lea     rbx, [rdi+10h]
0x1800553f2  mov     rcx, rbx; lpCriticalSection
0x1800553f5  call    cs:__imp_EnterCriticalSection
0x1800553fb  lea     rcx, [rdi+48h]
0x1800553ff  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180055404  test    rbx, rbx
0x180055407  jz      short loc_180055412
0x180055409  mov     rcx, rbx; lpCriticalSection
0x18005540c  call    cs:__imp_LeaveCriticalSection
0x180055412  cmp     byte ptr [rdi+0BCh], 0
0x180055419  jz      loc_1800556B2
0x18005541f  xorps   xmm0, xmm0
0x180055422  movdqu  [rsp+0E8h+var_88], xmm0
0x180055428  mov     [rsp+0E8h+var_78], 0
0x180055431  mov     rcx, rbx; lpCriticalSection
0x180055434  call    cs:__imp_EnterCriticalSection
0x18005543a  mov     [rsp+0E8h+var_B0], rbx
0x18005543f  lea     r14, [rdi+0A0h]
0x180055446  lea     rax, [rsp+0E8h+var_88]
0x18005544b  cmp     rax, r14
0x18005544e  jz      short loc_180055477
0x180055450  mov     r8, [r14+8]
0x180055454  sub     r8, [r14]
0x180055457  sar     r8, 3
0x18005545b  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x180055465  imul    r8, rsi
0x180055469  mov     rdx, [r14]
0x18005546c  lea     rcx, [rsp+0E8h+var_88]
0x180055471  call    ??$_Assign_counted_range@PEAVActiveLease@@@?$vector@VActiveLease@@V?$allocator@VActiveLease@@@std@@@std@@AEAAXPEAVActiveLease@@_K@Z; std::vector<ActiveLease>::_Assign_counted_range<ActiveLease *>(ActiveLease *,unsigned __int64)
0x180055476  nop
0x180055477  test    rbx, rbx
0x18005547a  jz      short loc_180055485
0x18005547c  mov     rcx, rbx; lpCriticalSection
0x18005547f  call    cs:__imp_LeaveCriticalSection
0x180055485  xorps   xmm0, xmm0
0x180055488  movdqu  [rsp+0E8h+var_A0], xmm0
0x18005548e  mov     [rsp+0E8h+var_90], 0
0x180055497  movups  [rsp+0E8h+var_50], xmm0
0x18005549f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800554a7  movdqu  [rsp+0E8h+var_40], xmm1
0x1800554b0  xor     eax, eax
0x1800554b2  mov     word ptr [rsp+0E8h+var_50], ax
0x1800554ba  mov     rcx, rbx; lpCriticalSection
0x1800554bd  call    cs:__imp_EnterCriticalSection
0x1800554c3  mov     [rsp+0E8h+var_B0], rbx
0x1800554c8  lea     rdx, [rdi+60h]
0x1800554cc  lea     rcx, [rsp+0E8h+var_50]
0x1800554d4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800554d9  nop
0x1800554da  test    rbx, rbx
0x1800554dd  jz      short loc_1800554E8
0x1800554df  mov     rcx, rbx; lpCriticalSection
0x1800554e2  call    cs:__imp_LeaveCriticalSection
0x1800554e8  lea     r8, [rsp+0E8h+var_88]
0x1800554ed  lea     rdx, [rsp+0E8h+var_50]
0x1800554f5  lea     rcx, [rsp+0E8h+var_70]
0x1800554fa  call    ?DoRegisterLeaseUris@WnsListener@@CA?AV?$vector@VActiveLease@@V?$allocator@VActiveLease@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV23@@Z; WnsListener::DoRegisterLeaseUris(std::wstring const &,std::vector<ActiveLease> const &)
0x1800554ff  nop
0x180055500  mov     rsi, [rsp+0E8h+var_70]
0x180055505  mov     r15, [rsp+0E8h+var_68]
0x18005550d  cmp     rsi, r15
0x180055510  jz      short loc_180055525
0x180055512  mov     rdx, rsi
0x180055515  lea     rcx, [rsp+0E8h+var_A0]
0x18005551a  call    ?push_back@?$vector@VActiveLease@@V?$allocator@VActiveLease@@@std@@@std@@QEAAX$$QEAVActiveLease@@@Z; std::vector<ActiveLease>::push_back(ActiveLease &&)
0x18005551f  add     rsi, 28h ; '('
0x180055523  jmp     short loc_18005550D
0x180055525  mov     rcx, rbx; lpCriticalSection
0x180055528  call    cs:__imp_EnterCriticalSection
0x18005552e  mov     [rsp+0E8h+var_58], rbx
0x180055536  mov     rsi, qword ptr [rsp+0E8h+var_A0]
0x18005553b  mov     rax, qword ptr [rsp+0E8h+var_A0+8]
0x180055540  mov     [rsp+0E8h+var_B0], rax
0x180055545  cmp     rsi, rax
0x180055548  jz      short loc_1800555C2
0x18005554a  mov     r9, rsi
0x18005554d  mov     r8, [rdi+0A8h]
0x180055554  mov     rdx, [r14]
0x180055557  lea     rcx, [rsp+0E8h+var_B8]
0x18005555c  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VActiveLease@@@std@@@std@@@std@@VActiveLease@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VActiveLease@@@std@@@std@@@0@V10@V10@AEBVActiveLease@@@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ActiveLease>>>,ActiveLease>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ActiveLease>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ActiveLease>>>,ActiveLease const &)
0x180055561  mov     r12, [rdi+0A8h]
0x180055568  mov     r15, [rsp+0E8h+var_B8]
0x18005556d  cmp     r15, r12
0x180055570  jz      short loc_1800555B7
0x180055572  lea     r13, [r15+28h]
0x180055576  jmp     short loc_180055598
0x180055578  mov     rdx, r13
0x18005557b  mov     rcx, r15
0x18005557e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180055583  lea     rdx, [r13+20h]
0x180055587  lea     rcx, [r15+20h]
0x18005558b  call    ??4?$ComPtr@UILicenseIdentityInternal@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::operator=(Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &&)
0x180055590  add     r15, 28h ; '('
0x180055594  add     r13, 28h ; '('
0x180055598  cmp     r13, r12
0x18005559b  jnz     short loc_180055578
0x18005559d  mov     rcx, [rdi+0A8h]
0x1800555a4  sub     rcx, 28h ; '('; this
0x1800555a8  xor     edx, edx; unsigned int
0x1800555aa  call    ??_GActiveLease@@QEAAPEAXI@Z; ActiveLease::`scalar deleting destructor'(uint)
0x1800555af  add     qword ptr [rdi+0A8h], 0FFFFFFFFFFFFFFD8h
0x1800555b7  add     rsi, 28h ; '('
0x1800555bb  cmp     rsi, [rsp+0E8h+var_B0]
0x1800555c0  jnz     short loc_18005554A
0x1800555c2  mov     rax, [r14+8]
0x1800555c6  cmp     [r14], rax
0x1800555c9  jz      short loc_18005561D
0x1800555cb  sub     rax, [r14]
0x1800555ce  sar     rax, 3
0x1800555d2  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800555dc  imul    rax, rcx
0x1800555e0  mov     [rsp+0E8h+var_C0], rax
0x1800555e5  lea     rax, aWnsLeaseRegist_1; "WNS lease registration completed with %"...
0x1800555ec  mov     [rsp+0E8h+Format], rax; Format
0x1800555f1  lea     r9, aWnslistenerReg; "WnsListener::RegisterLeaseUrisTimer"
0x1800555f8  mov     r8d, 2EAh; unsigned int
0x1800555fe  lea     rdx, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180055605  mov     ecx, 3; unsigned int
0x18005560a  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18005560f  mov     edx, 0EA60h; unsigned int
0x180055614  mov     rcx, rdi; this
0x180055617  call    ?ResetLeaseCallbackRegistrationTimer@WnsListener@@AEAAXK@Z; WnsListener::ResetLeaseCallbackRegistrationTimer(ulong)
0x18005561c  nop
0x18005561d  test    rbx, rbx
0x180055620  jz      short loc_18005562C
0x180055622  mov     rcx, rbx; lpCriticalSection
0x180055625  call    cs:__imp_LeaveCriticalSection
0x18005562b  nop
0x18005562c  lea     rcx, [rsp+0E8h+var_70]
0x180055631  call    ?_Tidy@?$vector@VActiveLease@@V?$allocator@VActiveLease@@@std@@@std@@AEAAXXZ; std::vector<ActiveLease>::_Tidy(void)
0x180055636  nop
0x180055637  lea     rcx, [rsp+0E8h+var_50]; this
0x18005563f  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180055644  nop
0x180055645  lea     rcx, [rsp+0E8h+var_A0]
0x18005564a  call    ?_Tidy@?$vector@VActiveLease@@V?$allocator@VActiveLease@@@std@@@std@@AEAAXXZ; std::vector<ActiveLease>::_Tidy(void)
0x18005564f  nop
0x180055650  lea     rcx, [rsp+0E8h+var_88]
0x180055655  call    ?_Tidy@?$vector@VActiveLease@@V?$allocator@VActiveLease@@@std@@@std@@AEAAXXZ; std::vector<ActiveLease>::_Tidy(void)
0x18005565a  nop
0x18005565b  jmp     short loc_1800556B2
0x18005565d  mov     edx, 80000000h
0x180055662  mov     ecx, dword ptr [rsp+0E8h+var_B8]
0x180055666  lea     eax, [rcx+rdx]
0x180055669  test    edx, eax
0x18005566b  jnz     short loc_1800556B2
0x18005566d  cmp     ecx, 80004001h
0x180055673  jz      short loc_1800556B2
0x180055675  mov     dword ptr [rsp+0E8h+var_C0], ecx
0x180055679  lea     rax, aWnsLeaseRegist; "WNS lease registration failed 0x%08X, s"...
0x180055680  mov     [rsp+0E8h+Format], rax; Format
0x180055685  lea     r9, aWnslistenerReg; "WnsListener::RegisterLeaseUrisTimer"
0x18005568c  mov     r8d, 2F7h; unsigned int
0x180055692  lea     rdx, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180055699  mov     ecx, 3; unsigned int
0x18005569e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800556a3  mov     edx, 0EA60h; unsigned int
0x1800556a8  mov     rcx, [rsp+0E8h+var_A8]; this
0x1800556ad  call    ?ResetLeaseCallbackRegistrationTimer@WnsListener@@AEAAXK@Z; WnsListener::ResetLeaseCallbackRegistrationTimer(ulong)
0x1800556b2  mov     rcx, [rsp+0E8h+var_30]
0x1800556ba  xor     rcx, rsp; StackCookie
0x1800556bd  call    __security_check_cookie
0x1800556c2  lea     r11, [rsp+0E8h+var_28]
0x1800556ca  mov     rbx, [r11+38h]
0x1800556ce  mov     rsi, [r11+40h]
0x1800556d2  mov     rsp, r11
0x1800556d5  pop     r15
0x1800556d7  pop     r14
0x1800556d9  pop     r13
0x1800556db  pop     r12
0x1800556dd  pop     rdi
0x1800556de  retn
```
