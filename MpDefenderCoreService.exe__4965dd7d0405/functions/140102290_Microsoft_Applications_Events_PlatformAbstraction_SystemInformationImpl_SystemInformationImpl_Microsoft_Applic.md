# Microsoft::Applications::Events::PlatformAbstraction::SystemInformationImpl::SystemInformationImpl(Microsoft::Applications::Events::IRuntimeConfig &)

- ea: `0x140102290`
- end: `0x14010282c`
- name: `??0SystemInformationImpl@PlatformAbstraction@Events@Applications@Microsoft@@QEAA@AEAVIRuntimeConfig@234@@Z`
- size: `1436`
- prototype: `__int64 __fastcall(Microsoft::Applications::Events::PlatformAbstraction::SystemInformationImpl *__hidden this, struct Microsoft::Applications::Events::IRuntimeConfig *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400feeb8`

## callees

- `0x14003a130`
- `0x14003a5c0`
- `0x14003a7b8`
- `0x14007e088`
- `0x140084a18`
- `0x140084a8c`
- `0x14008d900`
- `0x14009d4d0`
- `0x140102290`
- `0x140102a04`
- `0x140102c48`
- `0x140102f64`
- `0x140103358`
- `0x14015ffb0`
- `0x140166250`
- `0x1401662d0`
- `0x140166990`

## import_xrefs

- `KERNEL32!GetTimeZoneInformation` at `0x140102450`
- `KERNEL32!GetTimeZoneInformation` at `0x140102450`
- `KERNEL32!GetProcAddress` at `0x14010257f`
- `KERNEL32!GetProcAddress` at `0x14010257f`
- `KERNEL32!GetModuleHandleW` at `0x140102566`
- `KERNEL32!GetModuleHandleW` at `0x140102566`
- `ADVAPI32!RegGetValueA` at `0x140102745`
- `ADVAPI32!RegGetValueA` at `0x140102780`
- `ADVAPI32!RegGetValueA` at `0x140102745`
- `ADVAPI32!RegGetValueA` at `0x140102780`

## string_xrefs

- `0x14010255f`: `ntdll.dll`
- `0x14010272d`: `CommercialId`
- `0x14010276f`: `CommercialId`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
Microsoft::Applications::Events::PlatformAbstraction::SystemInformationImpl *__fastcall Microsoft::Applications::Events::PlatformAbstraction::SystemInformationImpl::SystemInformationImpl(
        Microsoft::Applications::Events::PlatformAbstraction::SystemInformationImpl *this,
        struct Microsoft::Applications::Events::IRuntimeConfig *a2)
{
  _OWORD *v3; // r14
  _OWORD *v4; // rdi
  __int128 *v5; // rbx
  _OWORD *v6; // r12
  void **v7; // r15
  size_t v8; // rsi
  DWORD v9; // eax
  LONG DaylightBias; // edx
  __int64 AppId; // rbx
  __int64 AppVersion; // rbx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  void (__fastcall *v15)(DWORD *, unsigned int *, void *, void *); // r14
  unsigned __int64 v16; // rbx
  void *v17; // rdi
  unsigned __int64 v18; // rbx
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rbx
  __int64 v22; // rbx
  const struct std::nothrow_t *v23; // rdx
  const struct std::nothrow_t *v24; // rdx
  void *v26; // [rsp+48h] [rbp-C0h]
  void *v27[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A8h]
  __int128 v29; // [rsp+70h] [rbp-98h] BYREF
  __int128 v30; // [rsp+80h] [rbp-88h]
  Microsoft::Applications::Events::PlatformAbstraction::SystemInformationImpl *v31; // [rsp+90h] [rbp-78h]
  void *v32; // [rsp+98h] [rbp-70h]
  void *v33; // [rsp+A0h] [rbp-68h]
  CHAR MultiByteStr[32]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v35; // [rsp+C8h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+CCh] [rbp-3Ch] BYREF
  WCHAR WideCharStr[8]; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int64 v38; // [rsp+E0h] [rbp-28h]
  __int64 v39; // [rsp+E8h] [rbp-20h]
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+F8h] [rbp-10h] BYREF

  v31 = this;
  *(_QWORD *)this = &Microsoft::Applications::Events::PlatformAbstraction::SystemInformationImpl::`vftable';
  v3 = (_OWORD *)((char *)this + 8);
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 15;
  *((_BYTE *)this + 8) = 0;
  v4 = (_OWORD *)((char *)this + 40);
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 15;
  *((_BYTE *)this + 40) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 15;
  *((_BYTE *)this + 72) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 15;
  *((_BYTE *)this + 104) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 15;
  *((_BYTE *)this + 136) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 15;
  *((_BYTE *)this + 168) = 0;
  *(_OWORD *)((char *)this + 200) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 15;
  *((_BYTE *)this + 200) = 0;
  v5 = (__int128 *)((char *)this + 232);
  *(_OWORD *)((char *)this + 232) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 15;
  *((_BYTE *)this + 232) = 0;
  *(_OWORD *)((char *)this + 264) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 15;
  *((_BYTE *)this + 264) = 0;
  v6 = (_OWORD *)((char *)this + 296);
  *(_OWORD *)((char *)this + 296) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 15;
  *((_BYTE *)this + 296) = 0;
  v7 = (void **)((char *)this + 328);
  *(_OWORD *)((char *)this + 328) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 15;
  *((_BYTE *)this + 328) = 0;
  *((_QWORD *)this + 45) = &Microsoft::Applications::Events::PlatformAbstraction::InformatonProviderImpl::`vftable';
  *((_QWORD *)this + 46) = 2;
  *(_OWORD *)((char *)this + 392) = 0;
  *(_OWORD *)((char *)this + 408) = 0;
  *(_OWORD *)((char *)this + 424) = 0;
  *(_OWORD *)((char *)this + 376) = 0;
  v8 = -1;
  *((_DWORD *)this + 110) = -1;
  *((_DWORD *)this + 111) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_DWORD *)this + 118) = 0;
  memset(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  v9 = GetTimeZoneInformation(&TimeZoneInformation);
  DaylightBias = TimeZoneInformation.DaylightBias;
  if ( v9 != 2 )
    DaylightBias = TimeZoneInformation.StandardBias;
  Microsoft::Applications::Events::WindowsEnvironmentInfo::TimeZoneBiasToISO8601(
    &v29,
    (unsigned int)(TimeZoneInformation.Bias + DaylightBias));
  if ( v5 != &v29 )
  {
    std::string::_Tidy_deallocate(v5);
    *v5 = v29;
    v5[1] = v30;
    *(_QWORD *)&v30 = 0;
    *((_QWORD *)&v30 + 1) = 15;
    LOBYTE(v29) = 0;
  }
  std::string::_Tidy_deallocate(&v29);
  std::string::operator=((char *)this + 168);
  AppId = Microsoft::Applications::Events::PlatformAbstraction::getAppId(WideCharStr);
  if ( v3 != (_OWORD *)AppId )
  {
    std::string::_Tidy_deallocate(v3);
    *v3 = *(_OWORD *)AppId;
    v3[1] = *(_OWORD *)(AppId + 16);
    *(_QWORD *)(AppId + 16) = 0;
    *(_QWORD *)(AppId + 24) = 15;
    *(_BYTE *)AppId = 0;
  }
  std::string::_Tidy_deallocate(WideCharStr);
  AppVersion = Microsoft::Applications::Events::PlatformAbstraction::getAppVersion(WideCharStr);
  if ( v4 != (_OWORD *)AppVersion )
  {
    std::string::_Tidy_deallocate(v4);
    *v4 = *(_OWORD *)AppVersion;
    v4[1] = *(_OWORD *)(AppVersion + 16);
    *(_QWORD *)(AppVersion + 16) = 0;
    *(_QWORD *)(AppVersion + 24) = 15;
    *(_BYTE *)AppVersion = 0;
  }
  std::string::_Tidy_deallocate(WideCharStr);
  Microsoft::Applications::Events::PlatformAbstraction::getOsVersion((char *)this + 104, (char *)this + 136);
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlConvertDeviceFamilyInfoToString");
    v15 = (void (__fastcall *)(DWORD *, unsigned int *, void *, void *))ProcAddress;
    if ( ProcAddress )
    {
      pcbData = 0;
      v35 = 0;
      if ( ((unsigned int (__fastcall *)(DWORD *, unsigned int *, _QWORD, _QWORD))ProcAddress)(&pcbData, &v35, 0, 0) == -1073741789 )
      {
        v16 = saturated_mul(pcbData, 2u);
        v17 = operator new[](v16);
        memset(v17, 0, v16);
        v32 = v17;
        v18 = saturated_mul(v35, 2u);
        v26 = operator new[](v18);
        memset(v26, 0, v18);
        v33 = v26;
        v15(&pcbData, &v35, v17, v26);
        *(_OWORD *)WideCharStr = 0;
        v38 = 0;
        v39 = 7;
        WideCharStr[0] = 0;
        v20 = -1;
        do
          ++v20;
        while ( *((_WORD *)v17 + v20) );
        _mm_lfence();
        if ( v20 > 7 )
        {
          std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(
            WideCharStr,
            v20,
            v19,
            v17);
        }
        else
        {
          v38 = v20;
          v21 = v20;
          memmove(WideCharStr, v17, 2 * v20);
          WideCharStr[v21] = 0;
        }
        v22 = Microsoft::Applications::Events::to_utf8_string(MultiByteStr, WideCharStr);
        if ( v6 != (_OWORD *)v22 )
        {
          std::string::_Tidy_deallocate(v6);
          *v6 = *(_OWORD *)v22;
          v6[1] = *(_OWORD *)(v22 + 16);
          *(_QWORD *)(v22 + 16) = 0;
          *(_QWORD *)(v22 + 24) = 15;
          *(_BYTE *)v22 = 0;
        }
        std::string::_Tidy_deallocate(MultiByteStr);
        std::wstring::_Tidy_deallocate(WideCharStr);
        operator delete(v26, v23);
        operator delete(v17, v24);
      }
    }
  }
  memset(&TimeZoneInformation, 0, 0x104u);
  pcbData = 260;
  if ( RegGetValueA(
         HKEY_LOCAL_MACHINE,
         "SOFTWARE\\Policies\\Microsoft\\Windows\\DataCollection",
         "CommercialId",
         2u,
         0,
         &TimeZoneInformation,
         &pcbData) )
  {
    pcbData = 260;
    RegGetValueA(
      HKEY_LOCAL_MACHINE,
      "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
      "CommercialId",
      2u,
      0,
      &TimeZoneInformation,
      &pcbData);
  }
  *(_OWORD *)v27 = 0;
  v28 = 0u;
  do
    ++v8;
  while ( *((_BYTE *)&TimeZoneInformation.Bias + v8) );
  std::string::_Construct<1,char const *>(v27, &TimeZoneInformation, v8);
  if ( v7 != v27 )
  {
    std::string::_Tidy_deallocate(v7);
    *(_OWORD *)v7 = *(_OWORD *)v27;
    *((_OWORD *)v7 + 1) = v28;
    *(_QWORD *)&v28 = 0;
    *((_QWORD *)&v28 + 1) = 15;
    LOBYTE(v27[0]) = 0;
  }
  std::string::_Tidy_deallocate(v27);
  return this;
}

```

## disassembly

```asm
0x140102290  mov     rax, rsp
0x140102293  mov     [rax+10h], rbx
0x140102297  mov     [rax+18h], rsi
0x14010229b  mov     [rax+20h], rdi
0x14010229f  push    rbp
0x1401022a0  push    r12
0x1401022a2  push    r13
0x1401022a4  push    r14
0x1401022a6  push    r15
0x1401022a8  lea     rbp, [rax-138h]
0x1401022af  sub     rsp, 210h
0x1401022b6  mov     rax, cs:__security_cookie
0x1401022bd  xor     rax, rsp
0x1401022c0  mov     [rbp+130h+var_30], rax
0x1401022c7  mov     r13, rcx
0x1401022ca  mov     [rbp+130h+var_1A8], rcx
0x1401022ce  xor     ecx, ecx
0x1401022d0  lea     rax, ??_7SystemInformationImpl@PlatformAbstraction@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::PlatformAbstraction::SystemInformationImpl::`vftable'
0x1401022d7  mov     [r13+0], rax
0x1401022db  lea     r14, [r13+8]
0x1401022df  xorps   xmm0, xmm0
0x1401022e2  movups  xmmword ptr [r14], xmm0
0x1401022e6  mov     [r14+10h], rcx
0x1401022ea  lea     edx, [rcx+0Fh]
0x1401022ed  mov     [r14+18h], rdx
0x1401022f1  mov     [r14], cl
0x1401022f4  lea     rdi, [r13+28h]
0x1401022f8  movups  xmmword ptr [rdi], xmm0
0x1401022fb  mov     [rdi+10h], rcx
0x1401022ff  mov     [rdi+18h], rdx
0x140102303  mov     [rdi], cl
0x140102305  movups  xmmword ptr [r13+48h], xmm0
0x14010230a  mov     [r13+58h], rcx
0x14010230e  mov     [r13+60h], rdx
0x140102312  mov     [r13+48h], cl
0x140102316  movups  xmmword ptr [r13+68h], xmm0
0x14010231b  mov     [r13+78h], rcx
0x14010231f  mov     [r13+80h], rdx
0x140102326  mov     [r13+68h], cl
0x14010232a  lea     rax, [r13+88h]
0x140102331  movups  xmmword ptr [rax], xmm0
0x140102334  mov     [rax+10h], rcx
0x140102338  mov     [rax+18h], rdx
0x14010233c  mov     [rax], cl
0x14010233e  lea     rax, [r13+0A8h]
0x140102345  movups  xmmword ptr [rax], xmm0
0x140102348  mov     [rax+10h], rcx
0x14010234c  mov     [rax+18h], rdx
0x140102350  mov     [rax], cl
0x140102352  movups  xmmword ptr [r13+0C8h], xmm0
0x14010235a  mov     [r13+0D8h], rcx
0x140102361  mov     [r13+0E0h], rdx
0x140102368  mov     [r13+0C8h], cl
0x14010236f  lea     rbx, [r13+0E8h]
0x140102376  movups  xmmword ptr [rbx], xmm0
0x140102379  mov     [rbx+10h], rcx
0x14010237d  mov     [rbx+18h], rdx
0x140102381  mov     [rbx], cl
0x140102383  movups  xmmword ptr [r13+108h], xmm0
0x14010238b  mov     [r13+118h], rcx
0x140102392  mov     [r13+120h], rdx
0x140102399  mov     [r13+108h], cl
0x1401023a0  lea     r12, [r13+128h]
0x1401023a7  movups  xmmword ptr [r12], xmm0
0x1401023ac  mov     [r12+10h], rcx
0x1401023b1  mov     [r12+18h], rdx
0x1401023b6  mov     [r12], cl
0x1401023ba  lea     r15, [r13+148h]
0x1401023c1  movups  xmmword ptr [r15], xmm0
0x1401023c5  mov     [r15+10h], rcx
0x1401023c9  mov     [r15+18h], rdx
0x1401023cd  mov     [r15], cl
0x1401023d0  lea     rax, ??_7InformatonProviderImpl@PlatformAbstraction@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::PlatformAbstraction::InformatonProviderImpl::`vftable'
0x1401023d7  mov     [r13+168h], rax
0x1401023de  mov     qword ptr [r13+170h], 2
0x1401023e9  movups  xmmword ptr [r13+188h], xmm0
0x1401023f1  movups  xmmword ptr [r13+198h], xmm0
0x1401023f9  movups  xmmword ptr [r13+1A8h], xmm0
0x140102401  xorps   xmm1, xmm1
0x140102404  movdqu  xmmword ptr [r13+178h], xmm1
0x14010240d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140102411  mov     [r13+1B8h], esi
0x140102418  mov     [r13+1BCh], ecx
0x14010241f  mov     [r13+1C0h], rcx
0x140102426  mov     [r13+1C8h], rcx
0x14010242d  mov     [r13+1D0h], rcx
0x140102434  mov     [r13+1D8h], ecx
0x14010243b  xor     edx, edx; Val
0x14010243d  mov     r8d, 0ACh; Size
0x140102443  lea     rcx, [rbp+130h+TimeZoneInformation]; void *
0x140102447  call    memset
0x14010244c  lea     rcx, [rbp+130h+TimeZoneInformation]; lpTimeZoneInformation
0x140102450  call    cs:__imp_GetTimeZoneInformation
0x140102456  cmp     eax, 2
0x140102459  mov     edx, [rbp+130h+TimeZoneInformation.DaylightBias]
0x14010245f  jz      short loc_140102464
0x140102461  mov     edx, [rbp+130h+TimeZoneInformation.StandardBias]
0x140102464  add     edx, [rbp+130h+TimeZoneInformation.Bias]
0x140102467  lea     rcx, [rsp+230h+var_1D0+8]
0x14010246c  call    ?TimeZoneBiasToISO8601@WindowsEnvironmentInfo@Events@Applications@Microsoft@@KA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; Microsoft::Applications::Events::WindowsEnvironmentInfo::TimeZoneBiasToISO8601(long)
0x140102471  lea     rax, [rsp+230h+var_1D0+8]
0x140102476  cmp     rbx, rax
0x140102479  jz      short loc_1401024AA
0x14010247b  mov     rcx, rbx
0x14010247e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140102483  movups  xmm0, [rsp+230h+var_1D0+8]
0x140102488  movups  xmmword ptr [rbx], xmm0
0x14010248b  movups  xmm1, [rsp+230h+var_1C0+8]
0x140102490  movups  xmmword ptr [rbx+10h], xmm1
0x140102494  mov     qword ptr [rsp+230h+var_1C0+8], 0
0x14010249d  mov     [rbp+130h+var_1B0], 0Fh
0x1401024a5  mov     byte ptr [rsp+230h+var_1D0+8], 0
0x1401024aa  lea     rcx, [rsp+230h+var_1D0+8]
0x1401024af  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401024b4  lea     rdx, qword_1401E60D0
0x1401024bb  lea     rcx, [r13+0A8h]; void *
0x1401024c2  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1401024c7  lea     rcx, [rbp+130h+WideCharStr]; void *
0x1401024cb  call    ?getAppId@PlatformAbstraction@Events@Applications@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Microsoft::Applications::Events::PlatformAbstraction::getAppId(void)
0x1401024d0  mov     rbx, rax
0x1401024d3  cmp     r14, rax
0x1401024d6  jz      short loc_140102504
0x1401024d8  mov     rcx, r14
0x1401024db  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401024e0  movups  xmm0, xmmword ptr [rbx]
0x1401024e3  movups  xmmword ptr [r14], xmm0
0x1401024e7  movups  xmm1, xmmword ptr [rbx+10h]
0x1401024eb  movups  xmmword ptr [r14+10h], xmm1
0x1401024f0  xor     r14d, r14d
0x1401024f3  mov     [rbx+10h], r14
0x1401024f7  mov     qword ptr [rbx+18h], 0Fh
0x1401024ff  mov     [rbx], r14b
0x140102502  jmp     short loc_140102507
0x140102504  xor     r14d, r14d
0x140102507  lea     rcx, [rbp+130h+WideCharStr]
0x14010250b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140102510  lea     rcx, [rbp+130h+WideCharStr]
0x140102514  call    ?getAppVersion@PlatformAbstraction@Events@Applications@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Microsoft::Applications::Events::PlatformAbstraction::getAppVersion(void)
0x140102519  mov     rbx, rax
0x14010251c  cmp     rdi, rax
0x14010251f  jz      short loc_140102546
0x140102521  mov     rcx, rdi
0x140102524  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140102529  movups  xmm0, xmmword ptr [rbx]
0x14010252c  movups  xmmword ptr [rdi], xmm0
0x14010252f  movups  xmm1, xmmword ptr [rbx+10h]
0x140102533  movups  xmmword ptr [rdi+10h], xmm1
0x140102537  mov     [rbx+10h], r14
0x14010253b  mov     qword ptr [rbx+18h], 0Fh
0x140102543  mov     [rbx], r14b
0x140102546  lea     rcx, [rbp+130h+WideCharStr]
0x14010254a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14010254f  lea     rdx, [r13+88h]
0x140102556  lea     rcx, [r13+68h]
0x14010255a  call    ?getOsVersion@PlatformAbstraction@Events@Applications@Microsoft@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; Microsoft::Applications::Events::PlatformAbstraction::getOsVersion(std::string &,std::string &)
0x14010255f  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140102566  call    cs:__imp_GetModuleHandleW
0x14010256c  test    rax, rax
0x14010256f  jz      loc_1401026FA
0x140102575  lea     rdx, aRtlconvertdevi; "RtlConvertDeviceFamilyInfoToString"
0x14010257c  mov     rcx, rax; hModule
0x14010257f  call    cs:__imp_GetProcAddress
0x140102585  mov     r14, rax
0x140102588  test    rax, rax
0x14010258b  jz      loc_1401026F7
0x140102591  mov     [rbp+130h+var_16C], 0
0x140102598  mov     [rbp+130h+var_170], 0
0x14010259f  xor     r9d, r9d
0x1401025a2  xor     r8d, r8d
0x1401025a5  lea     rdx, [rbp+130h+var_170]
0x1401025a9  lea     rcx, [rbp+130h+var_16C]
0x1401025ad  call    cs:__guard_dispatch_icall_fptr
0x1401025b3  cmp     eax, 0C0000023h
0x1401025b8  jnz     loc_1401026F7
0x1401025be  mov     ecx, [rbp+130h+var_16C]
0x1401025c1  mov     eax, 2
0x1401025c6  mul     rcx
0x1401025c9  mov     rbx, rax
0x1401025cc  cmovb   rbx, rsi
0x1401025d0  mov     rcx, rbx; unsigned __int64
0x1401025d3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1401025d8  mov     rdi, rax
0x1401025db  mov     r8, rbx; Size
0x1401025de  xor     edx, edx; Val
0x1401025e0  mov     rcx, rax; void *
0x1401025e3  call    memset
0x1401025e8  mov     [rbp+130h+var_1A0], rdi
0x1401025ec  mov     ecx, [rbp+130h+var_170]
0x1401025ef  mov     eax, 2
0x1401025f4  mul     rcx
0x1401025f7  mov     rbx, rax
0x1401025fa  cmovb   rbx, rsi
0x1401025fe  mov     rcx, rbx; unsigned __int64
0x140102601  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140102606  mov     [rsp+230h+var_1F0], rax
0x14010260b  mov     r8, rbx; Size
0x14010260e  xor     edx, edx; Val
0x140102610  mov     rcx, rax; void *
0x140102613  call    memset
0x140102618  mov     rax, [rsp+230h+var_1F0]
0x14010261d  mov     [rbp+130h+var_198], rax
0x140102621  mov     r9, rax
0x140102624  mov     r8, rdi
0x140102627  lea     rdx, [rbp+130h+var_170]
0x14010262b  lea     rcx, [rbp+130h+var_16C]
0x14010262f  mov     rax, r14
0x140102632  call    cs:__guard_dispatch_icall_fptr
0x140102638  xorps   xmm0, xmm0
0x14010263b  movups  xmmword ptr [rbp+130h+WideCharStr], xmm0
0x14010263f  xor     r14d, r14d
0x140102642  mov     [rbp+130h+var_158], r14
0x140102646  mov     [rbp+130h+var_150], 7
0x14010264e  mov     [rbp+130h+WideCharStr], r14w
0x140102653  mov     rdx, rsi
0x140102656  inc     rdx
0x140102659  cmp     [rdi+rdx*2], r14w
0x14010265e  jnz     short loc_140102656
0x140102660  lfence
0x140102663  lea     rcx, [rbp+130h+WideCharStr]; void *
0x140102667  cmp     rdx, 7
0x14010266b  ja      short loc_140102688
0x14010266d  mov     [rbp+130h+var_158], rdx
0x140102671  lea     rbx, [rdx+rdx]
0x140102675  mov     r8, rbx; Size
0x140102678  mov     rdx, rdi; Src
0x14010267b  call    memmove
0x140102680  mov     [rbp+rbx+130h+WideCharStr], r14w
0x140102686  jmp     short loc_140102690
0x140102688  mov     r9, rdi
0x14010268b  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x140102690  lea     rdx, [rbp+130h+WideCharStr]; lpWideCharStr
0x140102694  lea     rcx, [rbp+130h+MultiByteStr]; lpMultiByteStr
0x140102698  call    ?to_utf8_string@Events@Applications@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Applications::Events::to_utf8_string(std::wstring const &)
0x14010269d  mov     rbx, rax
0x1401026a0  cmp     r12, rax
0x1401026a3  jz      short loc_1401026CE
0x1401026a5  mov     rcx, r12
0x1401026a8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401026ad  movups  xmm0, xmmword ptr [rbx]
0x1401026b0  movups  xmmword ptr [r12], xmm0
0x1401026b5  movups  xmm1, xmmword ptr [rbx+10h]
0x1401026b9  movups  xmmword ptr [r12+10h], xmm1
0x1401026bf  mov     [rbx+10h], r14
0x1401026c3  mov     qword ptr [rbx+18h], 0Fh
0x1401026cb  mov     [rbx], r14b
0x1401026ce  lea     rcx, [rbp+130h+MultiByteStr]
0x1401026d2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401026d7  nop
0x1401026d8  lea     rcx, [rbp+130h+WideCharStr]
0x1401026dc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401026e1  nop
0x1401026e2  mov     rcx, [rsp+230h+var_1F0]; void *
0x1401026e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1401026ec  nop
0x1401026ed  mov     rcx, rdi; void *
0x1401026f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1401026f5  jmp     short loc_1401026FA
0x1401026f7  xor     r14d, r14d
0x1401026fa  mov     ebx, 104h
0x1401026ff  mov     r8d, ebx; Size
0x140102702  xor     edx, edx; Val
0x140102704  lea     rcx, [rbp+130h+TimeZoneInformation]; void *
0x140102708  call    memset
0x14010270d  mov     [rbp+130h+var_16C], ebx
0x140102710  lea     rax, [rbp+130h+var_16C]
0x140102714  mov     [rsp+230h+pcbData], rax; pcbData
0x140102719  lea     rax, [rbp+130h+TimeZoneInformation]
0x14010271d  mov     [rsp+230h+pvData], rax; pvData
0x140102722  mov     [rsp+230h+pdwType], r14; pdwType
0x140102727  mov     r9d, 2; dwFlags
0x14010272d  lea     r8, aCommercialid; "CommercialId"
0x140102734  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x14010273b  mov     rdi, 0FFFFFFFF80000002h
0x140102742  mov     rcx, rdi; hkey
0x140102745  call    cs:__imp_RegGetValueA
0x14010274b  test    eax, eax
0x14010274d  jz      short loc_140102786
0x14010274f  mov     [rbp+130h+var_16C], ebx
0x140102752  lea     rax, [rbp+130h+var_16C]
0x140102756  mov     [rsp+230h+pcbData], rax; pcbData
0x14010275b  lea     rax, [rbp+130h+TimeZoneInformation]
0x14010275f  mov     [rsp+230h+pvData], rax; pvData
0x140102764  mov     [rsp+230h+pdwType], r14; pdwType
0x140102769  mov     r9d, 2; dwFlags
0x14010276f  lea     r8, aCommercialid; "CommercialId"
0x140102776  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14010277d  mov     rcx, rdi; hkey
0x140102780  call    cs:__imp_RegGetValueA
0x140102786  xorps   xmm0, xmm0
0x140102789  movups  xmmword ptr [rsp+230h+var_1F0+8], xmm0
0x14010278e  mov     qword ptr [rsp+230h+var_1E0+8], r14
0x140102793  mov     qword ptr [rsp+230h+var_1D0], r14
0x140102798  lea     rax, [rbp+130h+TimeZoneInformation]
0x14010279c  inc     rsi
0x14010279f  cmp     [rax+rsi], r14b
0x1401027a3  jnz     short loc_14010279C
0x1401027a5  mov     r8, rsi
0x1401027a8  lea     rdx, [rbp+130h+TimeZoneInformation]
0x1401027ac  lea     rcx, [rsp+230h+var_1F0+8]
0x1401027b1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
  ... truncated ...
```
