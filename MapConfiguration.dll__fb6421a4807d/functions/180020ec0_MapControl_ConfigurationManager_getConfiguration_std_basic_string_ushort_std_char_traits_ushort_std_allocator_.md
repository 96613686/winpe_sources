# MapControl::ConfigurationManager::getConfiguration(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180020ec0`
- end: `0x1800210a3`
- name: `?getConfiguration@ConfigurationManager@MapControl@@QEAA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `483`
- prototype: `__int64 __fastcall(MapControl::ConfigurationManager *this)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001ce90`
- `0x18001efcc`

## callees

- `0x1800094a0`
- `0x18000c354`
- `0x18000cb24`
- `0x18000fac4`
- `0x180010f34`
- `0x180011f48`
- `0x18001e804`
- `0x18001fa94`
- `0x180020158`
- `0x180020974`
- `0x180020ec0`
- `0x18002149c`
- `0x1800215d0`
- `0x1800222a4`
- `0x180022bc4`
- `0x180024650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020f1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020f1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021021`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021021`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char *__fastcall MapControl::ConfigurationManager::getConfiguration(
        MapControl::ConfigurationManager *this,
        char *a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 *v7; // r14
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  _QWORD *v9; // rsi
  _QWORD *v10; // r12
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  __int64 Value; // rax
  __int64 *v14; // rax
  _QWORD *v15; // rax
  _BYTE v17[24]; // [rsp+20h] [rbp-69h] BYREF
  __int64 v18; // [rsp+38h] [rbp-51h]
  char *v19; // [rsp+40h] [rbp-49h]
  _QWORD v20[2]; // [rsp+48h] [rbp-41h] BYREF
  char v21; // [rsp+58h] [rbp-31h]
  _BYTE v22[16]; // [rsp+60h] [rbp-29h] BYREF
  char v23; // [rsp+70h] [rbp-19h]
  _BYTE v24[32]; // [rsp+78h] [rbp-11h] BYREF

  v18 = a4;
  v19 = a2;
  v7 = MapControl::ChinaEndPoints::kDefaultRegion;
  if ( *((_DWORD *)this + 102) != 1 )
    v7 = a3;
  v21 = 0;
  v23 = 0;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  v19 = (char *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  MapControl::ConfigurationManager::getSanitizedLanguage(this, v24, a4);
  v9 = (_QWORD *)*((_QWORD *)this + 18);
  v10 = (_QWORD *)*((_QWORD *)this + 19);
  while ( v9 != v10 )
  {
    if ( !(unsigned int)MapControl::LocaleMapConfiguration::regionLanguageMatch(v7, v24, *v9 + 352LL, *v9 + 384LL) )
    {
      v11 = (_QWORD *)Core::requirePresent<MapControl::LocaleMapConfiguration>((__int64)v17, v9);
      v12 = v11;
      if ( v21 )
      {
        Value = Core::Optional<std::shared_ptr<std::vector<unsigned char>>>::getValue(v20);
        std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(Value, v12);
      }
      else
      {
        std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(v20, v11);
        v21 = 1;
      }
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v17);
      break;
    }
    v9 += 2;
  }
  if ( !v21 )
  {
    MapControl::ConfigurationManager::createNewConfiguration(this, v17, v7, v24);
    std::vector<std::shared_ptr<Utility::PrioritizableTask>>::emplace_back<std::shared_ptr<Utility::PrioritizableTask> const &>(
      (__int64 *)this + 18,
      (__int64)v17);
    if ( *((_QWORD *)this + 21) )
      Core::Optional<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::operator=(v22, v17);
    Core::Optional<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::operator=(v20, v17);
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v17);
  }
  MapControl::ConfigurationManager::updateMostRecent(this);
  std::wstring::_Tidy_deallocate(v24);
  LeaveCriticalSection(v8);
  if ( v23 )
  {
    MapControl::ConfigurationManager::stopTimer(this);
    v14 = (__int64 *)Core::Optional<std::shared_ptr<std::vector<unsigned char>>>::getValue(v22);
    MapControl::ConfigurationManager::beginGetConfigFile((__int64)this, *v14);
  }
  v15 = (_QWORD *)Core::Optional<std::shared_ptr<std::vector<unsigned char>>>::getValue(v20);
  std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(a2, v15);
  if ( v23 )
  {
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v22);
    v23 = 0;
  }
  if ( v21 )
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v20);
  return a2;
}

```

## disassembly

```asm
0x180020ec0  push    rbp
0x180020ec2  push    rbx
0x180020ec3  push    rsi
0x180020ec4  push    rdi
0x180020ec5  push    r12
0x180020ec7  push    r13
0x180020ec9  push    r14
0x180020ecb  push    r15
0x180020ecd  lea     rbp, [rsp-1Fh]
0x180020ed2  sub     rsp, 0A8h
0x180020ed9  mov     rax, cs:__security_cookie
0x180020ee0  xor     rax, rsp
0x180020ee3  mov     [rbp+57h+var_48], rax
0x180020ee7  mov     rsi, r9
0x180020eea  mov     [rbp+57h+var_A8], r9
0x180020eee  mov     r15, rdx
0x180020ef1  mov     rdi, rcx
0x180020ef4  mov     [rbp+57h+var_A0], rdx
0x180020ef8  xor     eax, eax
0x180020efa  lea     r14, ?kDefaultRegion@ChinaEndPoints@MapControl@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const MapControl::ChinaEndPoints::kDefaultRegion
0x180020f01  cmp     dword ptr [rcx+198h], 1
0x180020f08  cmovnz  r14, r8
0x180020f0c  mov     [rbp+57h+var_88], al
0x180020f0f  mov     [rbp+57h+var_70], al
0x180020f12  lea     rbx, [rcx+30h]
0x180020f16  mov     [rbp+57h+var_A0], rbx
0x180020f1a  mov     rcx, rbx; lpCriticalSection
0x180020f1d  call    cs:__imp_EnterCriticalSection
0x180020f23  nop
0x180020f24  mov     r8, rsi
0x180020f27  lea     rdx, [rbp+57h+var_68]
0x180020f2b  mov     rcx, rdi
0x180020f2e  call    ?getSanitizedLanguage@ConfigurationManager@MapControl@@AEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; MapControl::ConfigurationManager::getSanitizedLanguage(std::wstring const &)
0x180020f33  nop
0x180020f34  lea     r13, [rdi+90h]
0x180020f3b  mov     rsi, [r13+0]
0x180020f3f  mov     r12, [r13+8]
0x180020f43  cmp     rsi, r12
0x180020f46  jz      short loc_180020FAF
0x180020f48  mov     r8, [rsi]
0x180020f4b  lea     r9, [r8+180h]
0x180020f52  add     r8, 160h
0x180020f59  lea     rdx, [rbp+57h+var_68]
0x180020f5d  mov     rcx, r14
0x180020f60  call    ?regionLanguageMatch@LocaleMapConfiguration@MapControl@@SA?AW4RegionLanguageMatch@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z; MapControl::LocaleMapConfiguration::regionLanguageMatch(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180020f65  test    eax, eax
0x180020f67  jz      short loc_180020F6F
0x180020f69  add     rsi, 10h
0x180020f6d  jmp     short loc_180020F43
0x180020f6f  mov     rdx, rsi
0x180020f72  lea     rcx, [rbp+57h+var_C0]
0x180020f76  call    ??$requirePresent@VLocaleMapConfiguration@MapControl@@@Core@@YA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@0@AEBV?$shared_ptr@VLocaleMapConfiguration@MapControl@@@std@@@Z; Core::requirePresent<MapControl::LocaleMapConfiguration>(std::shared_ptr<MapControl::LocaleMapConfiguration> const &)
0x180020f7b  mov     rsi, rax
0x180020f7e  lea     rcx, [rbp+57h+var_98]
0x180020f82  cmp     [rbp+57h+var_88], 0
0x180020f86  jnz     short loc_180020F96
0x180020f88  mov     rdx, rax
0x180020f8b  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180020f90  mov     [rbp+57h+var_88], 1
0x180020f94  jmp     short loc_180020FA6
0x180020f96  call    ?getValue@?$Optional@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@QEAAAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@XZ; Core::Optional<std::shared_ptr<std::vector<uchar>>>::getValue(void)
0x180020f9b  mov     rdx, rsi
0x180020f9e  mov     rcx, rax
0x180020fa1  call    ??4?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>> const &)
0x180020fa6  lea     rcx, [rbp+57h+var_C0]
0x180020faa  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180020faf  xor     esi, esi
0x180020fb1  cmp     [rbp+57h+var_88], sil
0x180020fb5  jnz     short loc_180021004
0x180020fb7  lea     r9, [rbp+57h+var_68]
0x180020fbb  mov     r8, r14
0x180020fbe  lea     rdx, [rbp+57h+var_C0]
0x180020fc2  mov     rcx, rdi
0x180020fc5  call    ?createNewConfiguration@ConfigurationManager@MapControl@@AEAA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapControl::ConfigurationManager::createNewConfiguration(std::wstring const &,std::wstring const &)
0x180020fca  nop
0x180020fcb  lea     rdx, [rbp+57h+var_C0]
0x180020fcf  mov     rcx, r13
0x180020fd2  call    ??$emplace_back@AEBV?$shared_ptr@VPrioritizableTask@Utility@@@std@@@?$vector@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@V?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VPrioritizableTask@Utility@@@1@AEBV21@@Z; std::vector<std::shared_ptr<Utility::PrioritizableTask>>::emplace_back<std::shared_ptr<Utility::PrioritizableTask> const &>(std::shared_ptr<Utility::PrioritizableTask> const &)
0x180020fd7  cmp     [rdi+0A8h], rsi
0x180020fde  jz      short loc_180020FED
0x180020fe0  lea     rdx, [rbp+57h+var_C0]
0x180020fe4  lea     rcx, [rbp+57h+var_80]
0x180020fe8  call    ??4?$Optional@V?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Core@@QEAAAEAV01@AEBV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@1@@Z; Core::Optional<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::operator=(Core::PresentSharedPtr<MapControl::LocaleMapConfiguration> const &)
0x180020fed  lea     rdx, [rbp+57h+var_C0]
0x180020ff1  lea     rcx, [rbp+57h+var_98]
0x180020ff5  call    ??4?$Optional@V?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Core@@QEAAAEAV01@AEBV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@1@@Z; Core::Optional<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::operator=(Core::PresentSharedPtr<MapControl::LocaleMapConfiguration> const &)
0x180020ffa  nop
0x180020ffb  lea     rcx, [rbp+57h+var_C0]
0x180020fff  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180021004  mov     r8, [rbp+57h+var_A8]
0x180021008  mov     rdx, r14
0x18002100b  mov     rcx, rdi; this
0x18002100e  call    ?updateMostRecent@ConfigurationManager@MapControl@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; MapControl::ConfigurationManager::updateMostRecent(std::wstring const &,std::wstring const &)
0x180021013  nop
0x180021014  lea     rcx, [rbp+57h+var_68]
0x180021018  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002101d  nop
0x18002101e  mov     rcx, rbx; lpCriticalSection
0x180021021  call    cs:__imp_LeaveCriticalSection
0x180021027  cmp     [rbp+57h+var_70], sil
0x18002102b  jz      short loc_180021049
0x18002102d  mov     rcx, rdi; this
0x180021030  call    ?stopTimer@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::stopTimer(void)
0x180021035  lea     rcx, [rbp+57h+var_80]
0x180021039  call    ?getValue@?$Optional@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@QEAAAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@XZ; Core::Optional<std::shared_ptr<std::vector<uchar>>>::getValue(void)
0x18002103e  mov     rdx, [rax]
0x180021041  mov     rcx, rdi
0x180021044  call    ?beginGetConfigFile@ConfigurationManager@MapControl@@AEAAXAEBVLocaleMapConfiguration@2@W4NetworkRequestType@Pal@@@Z; MapControl::ConfigurationManager::beginGetConfigFile(MapControl::LocaleMapConfiguration const &,Pal::NetworkRequestType)
0x180021049  lea     rcx, [rbp+57h+var_98]
0x18002104d  call    ?getValue@?$Optional@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@QEAAAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@XZ; Core::Optional<std::shared_ptr<std::vector<uchar>>>::getValue(void)
0x180021052  mov     rdx, rax
0x180021055  mov     rcx, r15
0x180021058  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18002105d  nop
0x18002105e  cmp     [rbp+57h+var_70], sil
0x180021062  jz      short loc_180021071
0x180021064  lea     rcx, [rbp+57h+var_80]
0x180021068  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18002106d  mov     [rbp+57h+var_70], sil
0x180021071  cmp     [rbp+57h+var_88], sil
0x180021075  jz      short loc_180021080
0x180021077  lea     rcx, [rbp+57h+var_98]
0x18002107b  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180021080  mov     rax, r15
0x180021083  mov     rcx, [rbp+57h+var_48]
0x180021087  xor     rcx, rsp; StackCookie
0x18002108a  call    __security_check_cookie
0x18002108f  add     rsp, 0A8h
0x180021096  pop     r15
0x180021098  pop     r14
0x18002109a  pop     r13
0x18002109c  pop     r12
0x18002109e  pop     rdi
0x18002109f  pop     rsi
0x1800210a0  pop     rbx
0x1800210a1  pop     rbp
0x1800210a2  retn
```
