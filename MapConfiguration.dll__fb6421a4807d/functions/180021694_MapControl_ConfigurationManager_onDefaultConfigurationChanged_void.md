# MapControl::ConfigurationManager::onDefaultConfigurationChanged(void)

- ea: `0x180021694`
- end: `0x1800217c9`
- name: `?onDefaultConfigurationChanged@ConfigurationManager@MapControl@@AEAAXXZ`
- size: `309`
- prototype: `void __fastcall(MapControl::ConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eaf0`

## callees

- `0x1800094a0`
- `0x18000ba50`
- `0x18000c354`
- `0x180010f34`
- `0x180011e18`
- `0x18001a79c`
- `0x18001d358`
- `0x180020158`
- `0x180021694`
- `0x1800221a8`
- `0x1800222a4`
- `0x180023a0c`
- `0x180023a4c`
- `0x180023a88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800216fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800216fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021747`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021747`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MapControl::ConfigurationManager::onDefaultConfigurationChanged(MapControl::ConfigurationManager *this)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  char v4; // si
  char v5; // di
  __int64 v6; // rdx
  double v7; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-30h] BYREF

  std::wstring::wstring((__int64)v9);
  MapControl::MapConfiguration::getValueString(*((_QWORD *)this + 21), v2, v9);
  v7 = 0.0;
  MapControl::MapConfiguration::getValuePalTimeInterval(*((_QWORD *)this + 21), v3, &v7);
  v4 = 0;
  v5 = 0;
  v8 = (__int64)this + 192;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  if ( (unsigned __int8)std::operator!=<unsigned short>((char *)this + 232, v9) )
  {
    std::wstring::operator=((char *)this + 232);
    v4 = 1;
  }
  if ( v7 != *((double *)this + 33) )
  {
    *((double *)this + 33) = v7;
    v5 = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  if ( v4 )
  {
    MapControl::ConfigurationManager::stopTimer(this);
    Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::get(*((LPCRITICAL_SECTION *)this + 21));
    MapControl::ConfigurationManager::beginGetConfigFile((__int64)this, v8);
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&v8);
  }
  else if ( v5 )
  {
    MapControl::ConfigurationManager::stopTimer(this);
    LOBYTE(v6) = 1;
    std::_Atomic_storage<bool,1>::store((char *)this + 564, v6);
    MapControl::ConfigurationManager::startTimer(this);
  }
  std::wstring::_Tidy_deallocate(v9);
}

```

## disassembly

```asm
0x180021694  push    rbp
0x180021696  push    rbx
0x180021697  push    rsi
0x180021698  push    rdi
0x180021699  push    r14
0x18002169b  push    r15
0x18002169d  mov     rbp, rsp
0x1800216a0  sub     rsp, 68h
0x1800216a4  mov     rax, cs:__security_cookie
0x1800216ab  xor     rax, rsp
0x1800216ae  mov     [rbp+var_10], rax
0x1800216b2  mov     rbx, rcx
0x1800216b5  lea     rcx, [rbp+var_30]
0x1800216b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800216be  nop
0x1800216bf  lea     r8, [rbp+var_30]
0x1800216c3  mov     rcx, [rbx+0A8h]
0x1800216ca  call    ?getValueString@MapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::MapConfiguration::getValueString(MapControl::ConfigurationKeys,std::wstring *)
0x1800216cf  xorps   xmm0, xmm0
0x1800216d2  movsd   [rbp+var_48], xmm0
0x1800216d7  lea     r8, [rbp+var_48]
0x1800216db  mov     rcx, [rbx+0A8h]
0x1800216e2  call    ?getValuePalTimeInterval@MapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEAN@Z; MapControl::MapConfiguration::getValuePalTimeInterval(MapControl::ConfigurationKeys,double *)
0x1800216e7  xor     sil, sil
0x1800216ea  xor     dil, dil
0x1800216ed  lea     r14, [rbx+0C0h]
0x1800216f4  mov     [rbp+var_40], r14
0x1800216f8  mov     rcx, r14; lpCriticalSection
0x1800216fb  call    cs:__imp_EnterCriticalSection
0x180021701  nop
0x180021702  lea     r15, [rbx+0E8h]
0x180021709  lea     rdx, [rbp+var_30]
0x18002170d  mov     rcx, r15
0x180021710  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x180021715  test    al, al
0x180021717  jz      short loc_180021728
0x180021719  lea     rdx, [rbp+var_30]
0x18002171d  mov     rcx, r15
0x180021720  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180021725  mov     sil, 1
0x180021728  movsd   xmm0, [rbp+var_48]
0x18002172d  ucomisd xmm0, qword ptr [rbx+108h]
0x180021735  jp      short loc_180021739
0x180021737  jz      short loc_180021744
0x180021739  movsd   qword ptr [rbx+108h], xmm0
0x180021741  mov     dil, 1
0x180021744  mov     rcx, r14; lpCriticalSection
0x180021747  call    cs:__imp_LeaveCriticalSection
0x18002174d  test    sil, sil
0x180021750  jz      short loc_180021783
0x180021752  mov     rcx, rbx; this
0x180021755  call    ?stopTimer@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::stopTimer(void)
0x18002175a  lea     rdx, [rbp+var_40]
0x18002175e  mov     rcx, [rbx+0A8h]; lpCriticalSection
0x180021765  call    ?get@?$Lockable@V?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Pal@@QEBA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@XZ; Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::get(void)
0x18002176a  nop
0x18002176b  mov     rdx, [rbp+var_40]
0x18002176f  mov     rcx, rbx
0x180021772  call    ?beginGetConfigFile@ConfigurationManager@MapControl@@AEAAXAEBVLocaleMapConfiguration@2@W4NetworkRequestType@Pal@@@Z; MapControl::ConfigurationManager::beginGetConfigFile(MapControl::LocaleMapConfiguration const &,Pal::NetworkRequestType)
0x180021777  nop
0x180021778  lea     rcx, [rbp+var_40]
0x18002177c  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180021781  jmp     short loc_1800217A7
0x180021783  test    dil, dil
0x180021786  jz      short loc_1800217A7
0x180021788  mov     rcx, rbx; this
0x18002178b  call    ?stopTimer@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::stopTimer(void)
0x180021790  lea     rcx, [rbx+234h]
0x180021797  mov     dl, 1
0x180021799  call    ?store@?$_Atomic_storage@_N$00@std@@QEAAX_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::store(bool,std::memory_order)
0x18002179e  mov     rcx, rbx; this
0x1800217a1  call    ?startTimer@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::startTimer(void)
0x1800217a6  nop
0x1800217a7  lea     rcx, [rbp+var_30]
0x1800217ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800217b0  mov     rcx, [rbp+var_10]
0x1800217b4  xor     rcx, rsp; StackCookie
0x1800217b7  call    __security_check_cookie
0x1800217bc  add     rsp, 68h
0x1800217c0  pop     r15
0x1800217c2  pop     r14
0x1800217c4  pop     rdi
0x1800217c5  pop     rsi
0x1800217c6  pop     rbx
0x1800217c7  pop     rbp
0x1800217c8  retn
```
