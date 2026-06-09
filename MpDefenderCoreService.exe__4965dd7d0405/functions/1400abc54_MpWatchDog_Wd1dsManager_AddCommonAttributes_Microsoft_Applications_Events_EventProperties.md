# MpWatchDog::Wd1dsManager::AddCommonAttributes(Microsoft::Applications::Events::EventProperties *)

- ea: `0x1400abc54`
- end: `0x1400ac5be`
- name: `?AddCommonAttributes@Wd1dsManager@MpWatchDog@@QEAAXPEAVEventProperties@Events@Applications@Microsoft@@@Z`
- size: `2410`
- prototype: `void __fastcall(MpWatchDog::Wd1dsManager *__hidden this, struct Microsoft::Applications::Events::EventProperties *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400ac9b0`
- `0x1400acd00`
- `0x1400b0620`

## callees

- `0x140014ac8`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d210`
- `0x14007e088`
- `0x140084a18`
- `0x14008e7c0`
- `0x14009cbe8`
- `0x1400abc54`
- `0x1401288b0`
- `0x1401289f0`
- `0x140128a24`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x1400abc9b`
- `KERNEL32!AcquireSRWLockShared` at `0x1400abc9b`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400abcbe`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400abcbe`

## string_xrefs

- `0x1400abcdc`: `Defender.Common.EngineRing`
- `0x1400abd25`: `Defender.Common.PlatformRing`
- `0x1400abd70`: `Defender.Common.SignatureRing`
- `0x1400abe35`: `Defender.Common.EngineVersion`
- `0x1400abe81`: `Defender.Common.EngineVersion`
- `0x1400abf4a`: `Defender.Common.SignatureVersion`
- `0x1400abf9c`: `Defender.Common.SignatureVersion`
- `0x1400ac062`: `Defender.Common.PlatformVersion`
- `0x1400ac0b1`: `Defender.Common.PlatformVersion`
- `0x1400ac106`: `Defender.Common.IsBeta`
- `0x1400ac156`: `Defender.Common.IsManaged`
- `0x1400ac1a6`: `Defender.Common.IsSense`
- `0x1400ac1ea`: `Defender.Common.IsEcsEnabled`
- `0x1400ac23f`: `Defender.Common.IsMsft`
- `0x1400ac283`: `Defender.Common.IsTestMachine`
- `0x1400ac2cc`: `Defender.Common.IsServer`
- `0x1400ac33a`: `Defender.Common.OrgId`
- `0x1400ac3a3`: `Defender.Common.MachineGuid`
- `0x1400ac40c`: `Defender.Common.PlatformUFcStudyId`
- `0x1400ac475`: `Defender.Common.PlatformKFcStudyId`
- `0x1400ac4de`: `Defender.Common.EngineFcStudyId`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
void __fastcall MpWatchDog::Wd1dsManager::AddCommonAttributes(
        MpWatchDog::Wd1dsManager *this,
        struct Microsoft::Applications::Events::EventProperties *a2)
{
  MpWatchDog::WdConfigManager *v3; // rbx
  RTL_SRWLOCK *v4; // rdi
  int v5; // eax
  void *v6; // rsi
  int v7; // eax
  void *v8; // rdi
  int v9; // eax
  int v10; // r13d
  void *v11; // rbx
  bool v12; // r12
  __int64 v13; // r8
  bool v14; // r12
  __int64 v15; // r8
  bool v16; // r12
  __int64 v17; // r8
  __int64 v18; // r8
  bool v19; // r12
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  const struct std::nothrow_t *v23; // rdx
  _QWORD *v24; // r12
  _QWORD *v25; // r12
  _QWORD *v26; // r12
  _QWORD *v27; // r12
  _QWORD *v28; // r12
  __int128 v29; // [rsp+30h] [rbp-268h] BYREF
  __int128 v30; // [rsp+40h] [rbp-258h]
  void *v31[2]; // [rsp+58h] [rbp-240h] BYREF
  __int128 v32; // [rsp+68h] [rbp-230h]
  void *v33; // [rsp+78h] [rbp-220h] BYREF
  void *v34; // [rsp+80h] [rbp-218h] BYREF
  unsigned __int64 v35; // [rsp+90h] [rbp-208h] BYREF
  unsigned __int64 v36; // [rsp+98h] [rbp-200h]
  unsigned __int64 v37; // [rsp+A0h] [rbp-1F8h]
  unsigned int v38; // [rsp+A8h] [rbp-1F0h]
  unsigned int v39; // [rsp+ACh] [rbp-1ECh]
  unsigned int v40; // [rsp+B0h] [rbp-1E8h]
  int v41; // [rsp+B4h] [rbp-1E4h]
  int v42; // [rsp+B8h] [rbp-1E0h]
  int v43; // [rsp+C0h] [rbp-1D8h]
  int v44; // [rsp+C4h] [rbp-1D4h]
  char v45; // [rsp+F0h] [rbp-1A8h]
  char v46; // [rsp+F1h] [rbp-1A7h]
  char v47; // [rsp+F2h] [rbp-1A6h]
  _QWORD v48[4]; // [rsp+118h] [rbp-180h] BYREF
  _QWORD v49[25]; // [rsp+138h] [rbp-160h] BYREF
  _QWORD v50[4]; // [rsp+200h] [rbp-98h] BYREF
  _QWORD v51[4]; // [rsp+220h] [rbp-78h] BYREF
  _QWORD v52[6]; // [rsp+240h] [rbp-58h] BYREF

  v3 = MpWatchDog::gMpWdConfigManager;
  v4 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
  AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
  MpWatchDog::DefenderCampConfigs::DefenderCampConfigs(
    (MpWatchDog::DefenderCampConfigs *)&v35,
    (MpWatchDog::WdConfigManager *)((char *)v3 + 192));
  ReleaseSRWLockShared(v4);
  *(_OWORD *)v31 = 0;
  v32 = 0;
  std::string::_Construct<1,char const *>(v31, "Defender.Common.EngineRing", 0x1Au);
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, v31, v38);
  std::string::_Tidy_deallocate(v31);
  *(_OWORD *)v31 = 0;
  v32 = 0;
  std::string::_Construct<1,char const *>(v31, "Defender.Common.PlatformRing", 0x1Cu);
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, v31, v39);
  std::string::_Tidy_deallocate(v31);
  *(_OWORD *)v31 = 0;
  v32 = 0;
  std::string::_Construct<1,char const *>(v31, "Defender.Common.SignatureRing", 0x1Du);
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, v31, v40);
  std::string::_Tidy_deallocate(v31);
  v33 = 0;
  v5 = CommonUtil::NewSprintfA(
         (CommonUtil *)&v33,
         (char **)"%llu.%llu.%llu.%llu",
         (const char *)HIWORD(v35),
         WORD2(v35),
         WORD1(v35),
         (unsigned __int16)v35);
  if ( v5 >= 0 )
  {
    *(_OWORD *)v31 = 0;
    v32 = 0;
    std::string::_Construct<1,char const *>(v31, "Defender.Common.EngineVersion", 0x1Du);
    v6 = v33;
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, v31, v33);
    std::string::_Tidy_deallocate(v31);
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        72,
        &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
        (unsigned int)v5);
    *(_OWORD *)v31 = 0;
    v32 = 0;
    std::string::_Construct<1,char const *>(v31, "Defender.Common.EngineVersion", 0x1Du);
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, v31, "0.0.0.0");
    std::string::_Tidy_deallocate(v31);
    v6 = v33;
  }
  v34 = 0;
  v7 = CommonUtil::NewSprintfA(
         (CommonUtil *)&v34,
         (char **)"%llu.%llu.%llu.%llu",
         (const char *)HIWORD(v37),
         WORD2(v37),
         WORD1(v37),
         (unsigned __int16)v37);
  if ( v7 >= 0 )
  {
    *(_OWORD *)v31 = 0;
    v32 = 0;
    std::string::_Construct<1,char const *>(v31, "Defender.Common.SignatureVersion", 0x20u);
    v8 = v34;
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, v31, v34);
    std::string::_Tidy_deallocate(v31);
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        73,
        &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
        (unsigned int)v7);
    *(_OWORD *)v31 = 0;
    v32 = 0;
    std::string::_Construct<1,char const *>(v31, "Defender.Common.SignatureVersion", 0x20u);
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, v31, "0.0.0.0");
    std::string::_Tidy_deallocate(v31);
    v8 = v34;
  }
  v31[0] = 0;
  v9 = CommonUtil::NewSprintfA(
         (CommonUtil *)v31,
         (char **)"%llu.%llu.%llu.%llu",
         (const char *)HIWORD(v36),
         WORD2(v36),
         WORD1(v36),
         (unsigned __int16)v36);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v29 = 0;
    v30 = 0;
    std::string::_Construct<1,char const *>(&v29, "Defender.Common.PlatformVersion", 0x1Fu);
    v11 = v31[0];
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v31[0]);
    std::string::_Tidy_deallocate(&v29);
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        74,
        &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
        (unsigned int)v9);
    v10 = 0;
    v29 = 0;
    v30 = 0;
    std::string::_Construct<1,char const *>(&v29, "Defender.Common.PlatformVersion", 0x1Fu);
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, "0.0.0.0");
    std::string::_Tidy_deallocate(&v29);
    v11 = v31[0];
  }
  v12 = v41 != 0;
  v29 = 0;
  v30 = 0;
  std::string::_Construct<1,char const *>(&v29, "Defender.Common.IsBeta", 0x16u);
  LOBYTE(v13) = v12;
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v13);
  std::string::_Tidy_deallocate(&v29);
  v14 = v43 != 0;
  v29 = 0;
  v30 = 0;
  std::string::_Construct<1,char const *>(&v29, "Defender.Common.IsManaged", 0x19u);
  LOBYTE(v15) = v14;
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v15);
  std::string::_Tidy_deallocate(&v29);
  v16 = v44 != 0;
  v29 = 0;
  v30 = 0;
  std::string::_Construct<1,char const *>(&v29, "Defender.Common.IsSense", 0x17u);
  LOBYTE(v17) = v16;
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v17);
  std::string::_Tidy_deallocate(&v29);
  v29 = 0;
  v30 = 0;
  std::string::_Construct<1,char const *>(&v29, "Defender.Common.IsEcsEnabled", 0x1Cu);
  LOBYTE(v18) = v45;
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v18);
  std::string::_Tidy_deallocate(&v29);
  v19 = v42 != 0;
  v29 = 0;
  v30 = 0;
  std::string::_Construct<1,char const *>(&v29, "Defender.Common.IsMsft", 0x16u);
  LOBYTE(v20) = v19;
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v20);
  std::string::_Tidy_deallocate(&v29);
  v29 = 0;
  v30 = 0;
  std::string::_Construct<1,char const *>(&v29, "Defender.Common.IsTestMachine", 0x1Du);
  LOBYTE(v21) = v46;
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v21);
  std::string::_Tidy_deallocate(&v29);
  v29 = 0;
  v30 = 0;
  std::string::_Construct<1,char const *>(&v29, "Defender.Common.IsServer", 0x18u);
  LOBYTE(v22) = v47;
  Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v22);
  std::string::_Tidy_deallocate(&v29);
  if ( v49[2] )
  {
    v24 = v49;
    if ( v49[3] > 0xFu )
      v24 = (_QWORD *)v49[0];
    v29 = 0;
    v30 = 0;
    std::string::_Construct<1,char const *>(&v29, "Defender.Common.OrgId", 0x15u);
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v24);
    std::string::_Tidy_deallocate(&v29);
  }
  if ( v48[2] )
  {
    v25 = v48;
    if ( v48[3] > 0xFu )
      v25 = (_QWORD *)v48[0];
    v29 = 0;
    v30 = 0;
    std::string::_Construct<1,char const *>(&v29, "Defender.Common.MachineGuid", 0x1Bu);
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v25);
    std::string::_Tidy_deallocate(&v29);
  }
  if ( v50[2] )
  {
    v26 = v50;
    if ( v50[3] > 0xFu )
      v26 = (_QWORD *)v50[0];
    v29 = 0;
    v30 = 0;
    std::string::_Construct<1,char const *>(&v29, "Defender.Common.PlatformUFcStudyId", 0x22u);
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v26);
    std::string::_Tidy_deallocate(&v29);
  }
  if ( v51[2] )
  {
    v27 = v51;
    if ( v51[3] > 0xFu )
      v27 = (_QWORD *)v51[0];
    v29 = 0;
    v30 = 0;
    std::string::_Construct<1,char const *>(&v29, "Defender.Common.PlatformKFcStudyId", 0x22u);
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v27);
    std::string::_Tidy_deallocate(&v29);
  }
  if ( v52[2] )
  {
    v28 = v52;
    if ( v52[3] > 0xFu )
      v28 = (_QWORD *)v52[0];
    v29 = 0;
    v30 = 0;
    std::string::_Construct<1,char const *>(&v29, "Defender.Common.EngineFcStudyId", 0x1Fu);
    Microsoft::Applications::Events::EventProperties::SetProperty(a2, &v29, v28);
    std::string::_Tidy_deallocate(&v29);
  }
  if ( v11 )
    operator delete(v11, v23);
  if ( v8 )
    operator delete(v8, v23);
  if ( v6 )
    operator delete(v6, v23);
  MpWatchDog::DefenderCampConfigs::~DefenderCampConfigs((MpWatchDog::DefenderCampConfigs *)&v35);
  if ( v10 < 0
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      75,
      &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
      (unsigned int)v10);
  }
}

```

## disassembly

```asm
0x1400abc54  mov     [rsp+arg_0], rbx
0x1400abc59  mov     [rsp+arg_10], rsi
0x1400abc5e  mov     [rsp+arg_18], rdi
0x1400abc63  push    r12
0x1400abc65  push    r13
0x1400abc67  push    r14
0x1400abc69  sub     rsp, 280h
0x1400abc70  mov     rax, cs:__security_cookie
0x1400abc77  xor     rax, rsp
0x1400abc7a  mov     [rsp+298h+var_28], rax
0x1400abc82  mov     r14, rdx
0x1400abc85  mov     rbx, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400abc8c  lea     rdi, [rbx+350h]
0x1400abc93  mov     [rsp+298h+var_240], rdi
0x1400abc98  mov     rcx, rdi; SRWLock
0x1400abc9b  call    cs:__imp_AcquireSRWLockShared
0x1400abca1  mov     byte ptr [rsp+298h+var_240+8], 1
0x1400abca6  lea     rdx, [rbx+0C0h]; struct MpWatchDog::DefenderCampConfigs *
0x1400abcad  lea     rcx, [rsp+298h+var_208]; this
0x1400abcb5  call    ??0DefenderCampConfigs@MpWatchDog@@QEAA@AEBU01@@Z; MpWatchDog::DefenderCampConfigs::DefenderCampConfigs(MpWatchDog::DefenderCampConfigs const &)
0x1400abcba  nop
0x1400abcbb  mov     rcx, rdi; SRWLock
0x1400abcbe  call    cs:__imp_ReleaseSRWLockShared
0x1400abcc4  nop
0x1400abcc5  xorps   xmm0, xmm0
0x1400abcc8  movups  xmmword ptr [rsp+298h+var_240], xmm0
0x1400abccd  xorps   xmm1, xmm1
0x1400abcd0  movdqu  [rsp+298h+var_230], xmm1
0x1400abcd6  mov     r8d, 1Ah
0x1400abcdc  lea     rdx, aDefenderCommon_8; "Defender.Common.EngineRing"
0x1400abce3  lea     rcx, [rsp+298h+var_240]
0x1400abce8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400abced  nop
0x1400abcee  mov     r8d, [rsp+298h+var_1F0]
0x1400abcf6  lea     rdx, [rsp+298h+var_240]
0x1400abcfb  mov     rcx, r14
0x1400abcfe  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_JW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,__int64,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400abd03  nop
0x1400abd04  lea     rcx, [rsp+298h+var_240]
0x1400abd09  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400abd0e  xorps   xmm0, xmm0
0x1400abd11  movups  xmmword ptr [rsp+298h+var_240], xmm0
0x1400abd16  xorps   xmm1, xmm1
0x1400abd19  movdqu  [rsp+298h+var_230], xmm1
0x1400abd1f  mov     r8d, 1Ch
0x1400abd25  lea     rdx, aDefenderCommon_10; "Defender.Common.PlatformRing"
0x1400abd2c  lea     rcx, [rsp+298h+var_240]
0x1400abd31  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400abd36  nop
0x1400abd37  mov     r8d, [rsp+298h+var_1EC]
0x1400abd3f  lea     rdx, [rsp+298h+var_240]
0x1400abd44  mov     rcx, r14
0x1400abd47  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_JW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,__int64,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400abd4c  nop
0x1400abd4d  lea     rcx, [rsp+298h+var_240]
0x1400abd52  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400abd57  xorps   xmm0, xmm0
0x1400abd5a  movups  xmmword ptr [rsp+298h+var_240], xmm0
0x1400abd5f  xorps   xmm1, xmm1
0x1400abd62  movdqu  [rsp+298h+var_230], xmm1
0x1400abd68  mov     edi, 1Dh
0x1400abd6d  mov     r8d, edi
0x1400abd70  lea     rdx, aDefenderCommon_9; "Defender.Common.SignatureRing"
0x1400abd77  lea     rcx, [rsp+298h+var_240]
0x1400abd7c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400abd81  nop
0x1400abd82  mov     r8d, [rsp+298h+var_1E8]
0x1400abd8a  lea     rdx, [rsp+298h+var_240]
0x1400abd8f  mov     rcx, r14
0x1400abd92  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_JW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,__int64,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400abd97  nop
0x1400abd98  lea     rcx, [rsp+298h+var_240]
0x1400abd9d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400abda2  mov     [rsp+298h+var_220], 0
0x1400abdab  mov     r8, [rsp+298h+var_208]
0x1400abdb3  movzx   edx, r8w
0x1400abdb7  mov     rax, r8
0x1400abdba  shr     rax, 10h
0x1400abdbe  movzx   ecx, ax
0x1400abdc1  mov     rax, r8
0x1400abdc4  shr     rax, 20h
0x1400abdc8  movzx   r9d, ax
0x1400abdcc  shr     r8, 30h; char *
0x1400abdd0  mov     [rsp+298h+var_270], rdx
0x1400abdd5  mov     [rsp+298h+var_278], rcx
0x1400abdda  lea     r12, aLluLluLluLlu; "%llu.%llu.%llu.%llu"
0x1400abde1  mov     rdx, r12; char **
0x1400abde4  lea     rcx, [rsp+298h+var_220]; this
0x1400abde9  call    ?NewSprintfA@CommonUtil@@YAJPEAPEADPEBDZZ; CommonUtil::NewSprintfA(char * *,char const *,...)
0x1400abdee  test    eax, eax
0x1400abdf0  jns     short loc_1400ABE6D
0x1400abdf2  lea     rbx, WPP_GLOBAL_Control
0x1400abdf9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abe00  cmp     rcx, rbx
0x1400abe03  jz      short loc_1400ABE21
0x1400abe05  test    byte ptr [rcx+1Ch], 1
0x1400abe09  jz      short loc_1400ABE21
0x1400abe0b  lea     edx, [rdi+2Bh]
0x1400abe0e  mov     r9d, eax
0x1400abe11  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400abe18  mov     rcx, [rcx+10h]
0x1400abe1c  call    WPP_SF_d
0x1400abe21  xorps   xmm0, xmm0
0x1400abe24  movups  xmmword ptr [rsp+298h+var_240], xmm0
0x1400abe29  xorps   xmm1, xmm1
0x1400abe2c  movdqu  [rsp+298h+var_230], xmm1
0x1400abe32  mov     r8, rdi
0x1400abe35  lea     rdx, aDefenderCommon_5; "Defender.Common.EngineVersion"
0x1400abe3c  lea     rcx, [rsp+298h+var_240]
0x1400abe41  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400abe46  nop
0x1400abe47  lea     r8, a0000; "0.0.0.0"
0x1400abe4e  lea     rdx, [rsp+298h+var_240]
0x1400abe53  mov     rcx, r14
0x1400abe56  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,char const *,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400abe5b  nop
0x1400abe5c  lea     rcx, [rsp+298h+var_240]
0x1400abe61  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400abe66  mov     rsi, [rsp+298h+var_220]
0x1400abe6b  jmp     short loc_1400ABEBA
0x1400abe6d  xorps   xmm0, xmm0
0x1400abe70  movups  xmmword ptr [rsp+298h+var_240], xmm0
0x1400abe75  xorps   xmm1, xmm1
0x1400abe78  movdqu  [rsp+298h+var_230], xmm1
0x1400abe7e  mov     r8, rdi
0x1400abe81  lea     rdx, aDefenderCommon_5; "Defender.Common.EngineVersion"
0x1400abe88  lea     rcx, [rsp+298h+var_240]
0x1400abe8d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400abe92  nop
0x1400abe93  mov     rsi, [rsp+298h+var_220]
0x1400abe98  mov     r8, rsi
0x1400abe9b  lea     rdx, [rsp+298h+var_240]
0x1400abea0  mov     rcx, r14
0x1400abea3  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,char const *,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400abea8  nop
0x1400abea9  lea     rcx, [rsp+298h+var_240]
0x1400abeae  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400abeb3  lea     rbx, WPP_GLOBAL_Control
0x1400abeba  mov     [rsp+298h+var_218], 0
0x1400abec6  mov     r8, [rsp+298h+var_1F8]
0x1400abece  movzx   edx, r8w
0x1400abed2  mov     rax, r8
0x1400abed5  shr     rax, 10h
0x1400abed9  movzx   ecx, ax
0x1400abedc  mov     rax, r8
0x1400abedf  shr     rax, 20h
0x1400abee3  movzx   r9d, ax
0x1400abee7  shr     r8, 30h; char *
0x1400abeeb  mov     [rsp+298h+var_270], rdx
0x1400abef0  mov     [rsp+298h+var_278], rcx
0x1400abef5  mov     rdx, r12; char **
0x1400abef8  lea     rcx, [rsp+298h+var_218]; this
0x1400abf00  call    ?NewSprintfA@CommonUtil@@YAJPEAPEADPEBDZZ; CommonUtil::NewSprintfA(char * *,char const *,...)
0x1400abf05  test    eax, eax
0x1400abf07  jns     short loc_1400ABF85
0x1400abf09  mov     rcx, cs:WPP_GLOBAL_Control
0x1400abf10  cmp     rcx, rbx
0x1400abf13  jz      short loc_1400ABF33
0x1400abf15  test    byte ptr [rcx+1Ch], 1
0x1400abf19  jz      short loc_1400ABF33
0x1400abf1b  mov     edx, 49h ; 'I'
0x1400abf20  mov     r9d, eax
0x1400abf23  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400abf2a  mov     rcx, [rcx+10h]
0x1400abf2e  call    WPP_SF_d
0x1400abf33  xorps   xmm0, xmm0
0x1400abf36  movups  xmmword ptr [rsp+298h+var_240], xmm0
0x1400abf3b  xorps   xmm1, xmm1
0x1400abf3e  movdqu  [rsp+298h+var_230], xmm1
0x1400abf44  mov     r8d, 20h ; ' '
0x1400abf4a  lea     rdx, aDefenderCommon_2; "Defender.Common.SignatureVersion"
0x1400abf51  lea     rcx, [rsp+298h+var_240]
0x1400abf56  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400abf5b  nop
0x1400abf5c  lea     r8, a0000; "0.0.0.0"
0x1400abf63  lea     rdx, [rsp+298h+var_240]
0x1400abf68  mov     rcx, r14
0x1400abf6b  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,char const *,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400abf70  nop
0x1400abf71  lea     rcx, [rsp+298h+var_240]
0x1400abf76  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400abf7b  mov     rdi, [rsp+298h+var_218]
0x1400abf83  jmp     short loc_1400ABFD1
0x1400abf85  xorps   xmm0, xmm0
0x1400abf88  movups  xmmword ptr [rsp+298h+var_240], xmm0
0x1400abf8d  xorps   xmm1, xmm1
0x1400abf90  movdqu  [rsp+298h+var_230], xmm1
0x1400abf96  mov     r8d, 20h ; ' '
0x1400abf9c  lea     rdx, aDefenderCommon_2; "Defender.Common.SignatureVersion"
0x1400abfa3  lea     rcx, [rsp+298h+var_240]
0x1400abfa8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400abfad  nop
0x1400abfae  mov     rdi, [rsp+298h+var_218]
0x1400abfb6  mov     r8, rdi
0x1400abfb9  lea     rdx, [rsp+298h+var_240]
0x1400abfbe  mov     rcx, r14
0x1400abfc1  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,char const *,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400abfc6  nop
0x1400abfc7  lea     rcx, [rsp+298h+var_240]
0x1400abfcc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400abfd1  mov     [rsp+298h+var_240], 0
0x1400abfda  mov     r10, [rsp+298h+var_200]
0x1400abfe2  movzx   r8d, r10w
0x1400abfe6  mov     rax, r10
0x1400abfe9  shr     rax, 10h
0x1400abfed  movzx   ecx, ax
0x1400abff0  mov     rax, r10
0x1400abff3  shr     rax, 20h
0x1400abff7  movzx   r9d, ax
0x1400abffb  shr     r10, 30h
0x1400abfff  mov     [rsp+298h+var_270], r8
0x1400ac004  mov     [rsp+298h+var_278], rcx
0x1400ac009  mov     r8, r10; char *
0x1400ac00c  mov     rdx, r12; char **
0x1400ac00f  lea     rcx, [rsp+298h+var_240]; this
0x1400ac014  call    ?NewSprintfA@CommonUtil@@YAJPEAPEADPEBDZZ; CommonUtil::NewSprintfA(char * *,char const *,...)
0x1400ac019  mov     r13d, eax
0x1400ac01c  test    eax, eax
0x1400ac01e  jns     short loc_1400AC09A
0x1400ac020  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ac027  cmp     rcx, rbx
0x1400ac02a  jz      short loc_1400AC04A
0x1400ac02c  test    byte ptr [rcx+1Ch], 1
0x1400ac030  jz      short loc_1400AC04A
0x1400ac032  mov     edx, 4Ah ; 'J'
0x1400ac037  mov     r9d, eax
0x1400ac03a  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400ac041  mov     rcx, [rcx+10h]
0x1400ac045  call    WPP_SF_d
0x1400ac04a  xor     r13d, r13d
0x1400ac04d  xorps   xmm0, xmm0
0x1400ac050  movups  [rsp+298h+var_268], xmm0
0x1400ac055  xorps   xmm1, xmm1
0x1400ac058  movdqu  [rsp+298h+var_258], xmm1
0x1400ac05e  lea     r8d, [r13+1Fh]
0x1400ac062  lea     rdx, aDefenderCommon_0; "Defender.Common.PlatformVersion"
0x1400ac069  lea     rcx, [rsp+298h+var_268]
0x1400ac06e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400ac073  nop
0x1400ac074  lea     r8, a0000; "0.0.0.0"
0x1400ac07b  lea     rdx, [rsp+298h+var_268]
0x1400ac080  mov     rcx, r14
0x1400ac083  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,char const *,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400ac088  nop
0x1400ac089  lea     rcx, [rsp+298h+var_268]
0x1400ac08e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400ac093  mov     rbx, [rsp+298h+var_240]
0x1400ac098  jmp     short loc_1400AC0E3
0x1400ac09a  xorps   xmm0, xmm0
0x1400ac09d  movups  [rsp+298h+var_268], xmm0
0x1400ac0a2  xorps   xmm1, xmm1
0x1400ac0a5  movdqu  [rsp+298h+var_258], xmm1
0x1400ac0ab  mov     r8d, 1Fh
0x1400ac0b1  lea     rdx, aDefenderCommon_0; "Defender.Common.PlatformVersion"
0x1400ac0b8  lea     rcx, [rsp+298h+var_268]
0x1400ac0bd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400ac0c2  nop
0x1400ac0c3  mov     rbx, [rsp+298h+var_240]
0x1400ac0c8  mov     r8, rbx
0x1400ac0cb  lea     rdx, [rsp+298h+var_268]
0x1400ac0d0  mov     rcx, r14
0x1400ac0d3  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,char const *,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400ac0d8  nop
0x1400ac0d9  lea     rcx, [rsp+298h+var_268]
0x1400ac0de  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400ac0e3  cmp     [rsp+298h+var_1E4], 0
0x1400ac0eb  setnz   r12b
0x1400ac0ef  xorps   xmm0, xmm0
0x1400ac0f2  movups  [rsp+298h+var_268], xmm0
0x1400ac0f7  xorps   xmm1, xmm1
0x1400ac0fa  movdqu  [rsp+298h+var_258], xmm1
0x1400ac100  mov     r8d, 16h
0x1400ac106  lea     rdx, aDefenderCommon_4; "Defender.Common.IsBeta"
0x1400ac10d  lea     rcx, [rsp+298h+var_268]
0x1400ac112  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400ac117  nop
0x1400ac118  mov     r8b, r12b
0x1400ac11b  lea     rdx, [rsp+298h+var_268]
0x1400ac120  mov     rcx, r14
0x1400ac123  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_NW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,bool,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400ac128  nop
0x1400ac129  lea     rcx, [rsp+298h+var_268]
0x1400ac12e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400ac133  cmp     [rsp+298h+var_1D8], 0
0x1400ac13b  setnz   r12b
0x1400ac13f  xorps   xmm0, xmm0
0x1400ac142  movups  [rsp+298h+var_268], xmm0
0x1400ac147  xorps   xmm1, xmm1
0x1400ac14a  movdqu  [rsp+298h+var_258], xmm1
0x1400ac150  mov     r8d, 19h
0x1400ac156  lea     rdx, aDefenderCommon_13; "Defender.Common.IsManaged"
0x1400ac15d  lea     rcx, [rsp+298h+var_268]
0x1400ac162  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400ac167  nop
0x1400ac168  mov     r8b, r12b
0x1400ac16b  lea     rdx, [rsp+298h+var_268]
0x1400ac170  mov     rcx, r14
0x1400ac173  call    ?SetProperty@EventProperties@Events@Applications@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_NW4PiiKind@234@W4DataCategory@234@@Z; Microsoft::Applications::Events::EventProperties::SetProperty(std::string const &,bool,Microsoft::Applications::Events::PiiKind,Microsoft::Applications::Events::DataCategory)
0x1400ac178  nop
0x1400ac179  lea     rcx, [rsp+298h+var_268]
  ... truncated ...
```
