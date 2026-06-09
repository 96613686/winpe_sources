# Microsoft::Applications::Events::_dynamic_initializer_for__currentConfig__

- ea: `0x1400052c0`
- end: `0x140005729`
- name: `Microsoft::Applications::Events::_dynamic_initializer_for__currentConfig__`
- size: `1129`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14003a360`
- `0x14003a680`
- `0x14007e088`
- `0x140103c00`
- `0x1401041f0`
- `0x140109eec`
- `0x140109f88`

## string_xrefs

- `0x1400055ae`: `eventCollectorUri`
- `0x140005404`: `cacheMemorySizeLimitInBytes`
- `0x1400055c2`: `https://mobile.events.data.microsoft.com/OneCollector/1.0/`
- `0x1400053c5`: `cacheFileSizeLimitInBytes`
- `0x14000566c`: `cacheMemoryFullNotificationPercentage`
- `0x1400055ef`: `cacheFileFullNotificationPercentage`
- `0x14000562d`: `cacheFullNotificationIntervalTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
int Microsoft::Applications::Events::_dynamic_initializer_for__currentConfig__()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v2[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v3[96]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v4[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v5[96]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v6[2]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v7[96]; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v8[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v9[96]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v10[2]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v11[96]; // [rsp+250h] [rbp+150h] BYREF
  _OWORD v12[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v13[96]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _OWORD v14[2]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v15[96]; // [rsp+350h] [rbp+250h] BYREF
  _OWORD v16[2]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v17[96]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _OWORD v18[2]; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v19[96]; // [rsp+450h] [rbp+350h] BYREF
  _OWORD v20[2]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v21[96]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _OWORD v22[2]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v23[96]; // [rsp+550h] [rbp+450h] BYREF
  _OWORD v24[2]; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE v25[96]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _OWORD v26[2]; // [rsp+630h] [rbp+530h] BYREF
  _BYTE v27[96]; // [rsp+650h] [rbp+550h] BYREF
  _OWORD v28[2]; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE v29[96]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _OWORD v30[2]; // [rsp+730h] [rbp+630h] BYREF
  _BYTE v31[96]; // [rsp+750h] [rbp+650h] BYREF
  _OWORD v32[2]; // [rsp+7B0h] [rbp+6B0h] BYREF
  _BYTE v33[96]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _OWORD v34[2]; // [rsp+830h] [rbp+730h] BYREF
  _BYTE v35[96]; // [rsp+850h] [rbp+750h] BYREF
  char vars0; // [rsp+8B0h] [rbp+7B0h] BYREF

  memset(v2, 0, sizeof(v2));
  std::string::_Construct<1,char const *>(v2, "minimumTraceLevel", 0x11u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v3, 4);
  memset(v4, 0, sizeof(v4));
  std::string::_Construct<1,char const *>(v4, "enableTrace", 0xBu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v5, 1);
  memset(v6, 0, sizeof(v6));
  std::string::_Construct<1,char const *>(v6, "sdkmode", 7u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v7, 0);
  memset(v8, 0, sizeof(v8));
  std::string::_Construct<1,char const *>(v8, "enableLifecycleSession", 0x16u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v9, 0);
  memset(v10, 0, sizeof(v10));
  std::string::_Construct<1,char const *>(v10, "cacheFileSizeLimitInBytes", 0x19u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v11, 3145728);
  memset(v12, 0, sizeof(v12));
  std::string::_Construct<1,char const *>(v12, "cacheMemorySizeLimitInBytes", 0x1Bu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v13, 0x80000);
  memset(v14, 0, sizeof(v14));
  std::string::_Construct<1,char const *>(v14, "multiTenantEnabled", 0x12u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v15, 1);
  memset(v16, 0, sizeof(v16));
  std::string::_Construct<1,char const *>(v16, "enableDbDropIfFull", 0x12u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v17, 0);
  memset(v18, 0, sizeof(v18));
  std::string::_Construct<1,char const *>(v18, "maxTeardownUploadTimeInSec", 0x1Au);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v19, 0);
  memset(v20, 0, sizeof(v20));
  std::string::_Construct<1,char const *>(v20, "maxPendingHTTPRequests", 0x16u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v21, 4);
  memset(v22, 0, sizeof(v22));
  std::string::_Construct<1,char const *>(v22, "maxDBFlushQueues", 0x10u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v23, 3);
  memset(v24, 0, sizeof(v24));
  std::string::_Construct<1,char const *>(v24, "traceLevelMask", 0xEu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v25, 0);
  memset(v26, 0, sizeof(v26));
  std::string::_Construct<1,char const *>(v26, "eventCollectorUri", 0x11u);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v27,
    "https://mobile.events.data.microsoft.com/OneCollector/1.0/");
  memset(v28, 0, sizeof(v28));
  std::string::_Construct<1,char const *>(v28, "cacheFileFullNotificationPercentage", 0x23u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v29, 75);
  memset(v30, 0, sizeof(v30));
  std::string::_Construct<1,char const *>(v30, "cacheFullNotificationIntervalTime", 0x21u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v31, 5000);
  memset(v32, 0, sizeof(v32));
  std::string::_Construct<1,char const *>(v32, "cacheMemoryFullNotificationPercentage", 0x25u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v33, 75);
  memset(v34, 0, sizeof(v34));
  std::string::_Construct<1,char const *>(v34, "enableNetworkDetector", 0x15u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v35, 1);
  v1[0] = v2;
  v1[1] = &vars0;
  Microsoft::Applications::Events::ILogConfiguration::ILogConfiguration(qword_1401E6100, v1);
  `eh vector destructor iterator'(
    v2,
    0x80u,
    0x11u,
    std::pair<std::string const,Microsoft::Applications::Events::Variant>::~pair<std::string const,Microsoft::Applications::Events::Variant>);
  return atexit((void (__cdecl *)())Microsoft::Applications::Events::_dynamic_atexit_destructor_for__currentConfig__);
}

```

## disassembly

```asm
0x1400052c0  mov     [rsp-8+arg_0], r14
0x1400052c5  push    rbp
0x1400052c6  lea     rbp, [rsp-7B0h]
0x1400052ce  sub     rsp, 8B0h
0x1400052d5  xorps   xmm0, xmm0
0x1400052d8  movups  [rsp+8B0h+var_880], xmm0
0x1400052dd  xorps   xmm1, xmm1
0x1400052e0  movdqa  [rsp+8B0h+var_870], xmm1
0x1400052e6  mov     r14d, 11h
0x1400052ec  mov     r8d, r14d
0x1400052ef  lea     rdx, aMinimumtracele; "minimumTraceLevel"
0x1400052f6  lea     rcx, [rsp+8B0h+var_880]
0x1400052fb  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005300  nop
0x140005301  lea     edx, [r14-0Dh]; int
0x140005305  lea     rcx, [rsp+8B0h+var_860]; this
0x14000530a  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x14000530f  nop
0x140005310  xorps   xmm0, xmm0
0x140005313  movups  [rbp+7B0h+var_800], xmm0
0x140005317  xorps   xmm1, xmm1
0x14000531a  movdqa  [rbp+7B0h+var_7F0], xmm1
0x14000531f  lea     r8d, [r14-6]
0x140005323  lea     rdx, aEnabletrace; "enableTrace"
0x14000532a  lea     rcx, [rbp+7B0h+var_800]
0x14000532e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005333  nop
0x140005334  mov     dl, 1; bool
0x140005336  lea     rcx, [rbp+7B0h+var_7E0]; this
0x14000533a  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x14000533f  nop
0x140005340  xorps   xmm0, xmm0
0x140005343  movups  [rbp+7B0h+var_780], xmm0
0x140005347  xorps   xmm1, xmm1
0x14000534a  movdqa  [rbp+7B0h+var_770], xmm1
0x14000534f  lea     r8d, [r14-0Ah]
0x140005353  lea     rdx, aSdkmode; "sdkmode"
0x14000535a  lea     rcx, [rbp+7B0h+var_780]
0x14000535e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005363  nop
0x140005364  xor     edx, edx; int
0x140005366  lea     rcx, [rbp+7B0h+var_760]; this
0x14000536a  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x14000536f  nop
0x140005370  xorps   xmm0, xmm0
0x140005373  movups  [rbp+7B0h+var_700], xmm0
0x14000537a  xorps   xmm1, xmm1
0x14000537d  movdqa  [rbp+7B0h+var_6F0], xmm1
0x140005385  lea     r8d, [r14+5]
0x140005389  lea     rdx, aEnablelifecycl; "enableLifecycleSession"
0x140005390  lea     rcx, [rbp+7B0h+var_700]
0x140005397  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14000539c  nop
0x14000539d  xor     edx, edx; bool
0x14000539f  lea     rcx, [rbp+7B0h+var_6E0]; this
0x1400053a6  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x1400053ab  nop
0x1400053ac  xorps   xmm0, xmm0
0x1400053af  movups  [rbp+7B0h+var_680], xmm0
0x1400053b6  xorps   xmm1, xmm1
0x1400053b9  movdqa  [rbp+7B0h+var_670], xmm1
0x1400053c1  lea     r8d, [r14+8]
0x1400053c5  lea     rdx, aCachefilesizel; "cacheFileSizeLimitInBytes"
0x1400053cc  lea     rcx, [rbp+7B0h+var_680]
0x1400053d3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400053d8  nop
0x1400053d9  mov     edx, 300000h; int
0x1400053de  lea     rcx, [rbp+7B0h+var_660]; this
0x1400053e5  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x1400053ea  nop
0x1400053eb  xorps   xmm0, xmm0
0x1400053ee  movups  [rbp+7B0h+var_600], xmm0
0x1400053f5  xorps   xmm1, xmm1
0x1400053f8  movdqa  [rbp+7B0h+var_5F0], xmm1
0x140005400  lea     r8d, [r14+0Ah]
0x140005404  lea     rdx, aCachememorysiz; "cacheMemorySizeLimitInBytes"
0x14000540b  lea     rcx, [rbp+7B0h+var_600]
0x140005412  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005417  nop
0x140005418  mov     edx, 80000h; int
0x14000541d  lea     rcx, [rbp+7B0h+var_5E0]; this
0x140005424  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140005429  nop
0x14000542a  xorps   xmm0, xmm0
0x14000542d  movups  [rbp+7B0h+var_580], xmm0
0x140005434  xorps   xmm1, xmm1
0x140005437  movdqa  [rbp+7B0h+var_570], xmm1
0x14000543f  lea     r8d, [r14+1]
0x140005443  lea     rdx, aMultitenantena; "multiTenantEnabled"
0x14000544a  lea     rcx, [rbp+7B0h+var_580]
0x140005451  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005456  nop
0x140005457  mov     dl, 1; bool
0x140005459  lea     rcx, [rbp+7B0h+var_560]; this
0x140005460  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x140005465  nop
0x140005466  xorps   xmm0, xmm0
0x140005469  movups  [rbp+7B0h+var_500], xmm0
0x140005470  xorps   xmm1, xmm1
0x140005473  movdqa  [rbp+7B0h+var_4F0], xmm1
0x14000547b  lea     r8d, [r14+1]
0x14000547f  lea     rdx, aEnabledbdropif; "enableDbDropIfFull"
0x140005486  lea     rcx, [rbp+7B0h+var_500]
0x14000548d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005492  nop
0x140005493  xor     edx, edx; bool
0x140005495  lea     rcx, [rbp+7B0h+var_4E0]; this
0x14000549c  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x1400054a1  nop
0x1400054a2  xorps   xmm0, xmm0
0x1400054a5  movups  [rbp+7B0h+var_480], xmm0
0x1400054ac  xorps   xmm1, xmm1
0x1400054af  movdqa  [rbp+7B0h+var_470], xmm1
0x1400054b7  lea     r8d, [r14+9]
0x1400054bb  lea     rdx, aMaxteardownupl; "maxTeardownUploadTimeInSec"
0x1400054c2  lea     rcx, [rbp+7B0h+var_480]
0x1400054c9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400054ce  nop
0x1400054cf  xor     edx, edx; int
0x1400054d1  lea     rcx, [rbp+7B0h+var_460]; this
0x1400054d8  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x1400054dd  nop
0x1400054de  xorps   xmm0, xmm0
0x1400054e1  movups  [rbp+7B0h+var_400], xmm0
0x1400054e8  xorps   xmm1, xmm1
0x1400054eb  movdqa  [rbp+7B0h+var_3F0], xmm1
0x1400054f3  lea     r8d, [r14+5]
0x1400054f7  lea     rdx, aMaxpendinghttp; "maxPendingHTTPRequests"
0x1400054fe  lea     rcx, [rbp+7B0h+var_400]
0x140005505  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14000550a  nop
0x14000550b  lea     edx, [r14-0Dh]; int
0x14000550f  lea     rcx, [rbp+7B0h+var_3E0]; this
0x140005516  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x14000551b  nop
0x14000551c  xorps   xmm0, xmm0
0x14000551f  movups  [rbp+7B0h+var_380], xmm0
0x140005526  xorps   xmm1, xmm1
0x140005529  movdqa  [rbp+7B0h+var_370], xmm1
0x140005531  lea     r8d, [r14-1]
0x140005535  lea     rdx, aMaxdbflushqueu; "maxDBFlushQueues"
0x14000553c  lea     rcx, [rbp+7B0h+var_380]
0x140005543  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005548  nop
0x140005549  lea     edx, [r14-0Eh]; int
0x14000554d  lea     rcx, [rbp+7B0h+var_360]; this
0x140005554  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140005559  nop
0x14000555a  xorps   xmm0, xmm0
0x14000555d  movups  [rbp+7B0h+var_300], xmm0
0x140005564  xorps   xmm1, xmm1
0x140005567  movdqa  [rbp+7B0h+var_2F0], xmm1
0x14000556f  lea     r8d, [r14-3]
0x140005573  lea     rdx, aTracelevelmask; "traceLevelMask"
0x14000557a  lea     rcx, [rbp+7B0h+var_300]
0x140005581  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005586  nop
0x140005587  xor     edx, edx; int
0x140005589  lea     rcx, [rbp+7B0h+var_2E0]; this
0x140005590  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140005595  nop
0x140005596  xorps   xmm0, xmm0
0x140005599  movups  [rbp+7B0h+var_280], xmm0
0x1400055a0  xorps   xmm1, xmm1
0x1400055a3  movdqa  [rbp+7B0h+var_270], xmm1
0x1400055ab  mov     r8d, r14d
0x1400055ae  lea     rdx, aEventcollector; "eventCollectorUri"
0x1400055b5  lea     rcx, [rbp+7B0h+var_280]
0x1400055bc  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400055c1  nop
0x1400055c2  lea     rdx, aHttpsMobileEve_0; "https://mobile.events.data.microsoft.co"...
0x1400055c9  lea     rcx, [rbp+7B0h+var_260]; this
0x1400055d0  call    ??0Variant@Events@Applications@Microsoft@@QEAA@PEBD@Z; Microsoft::Applications::Events::Variant::Variant(char const *)
0x1400055d5  nop
0x1400055d6  xorps   xmm0, xmm0
0x1400055d9  movups  [rbp+7B0h+var_200], xmm0
0x1400055e0  xorps   xmm1, xmm1
0x1400055e3  movdqa  [rbp+7B0h+var_1F0], xmm1
0x1400055eb  lea     r8d, [r14+12h]
0x1400055ef  lea     rdx, aCachefilefulln; "cacheFileFullNotificationPercentage"
0x1400055f6  lea     rcx, [rbp+7B0h+var_200]
0x1400055fd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005602  nop
0x140005603  lea     edx, [r14+3Ah]; int
0x140005607  lea     rcx, [rbp+7B0h+var_1E0]; this
0x14000560e  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140005613  nop
0x140005614  xorps   xmm0, xmm0
0x140005617  movups  [rbp+7B0h+var_180], xmm0
0x14000561e  xorps   xmm1, xmm1
0x140005621  movdqa  [rbp+7B0h+var_170], xmm1
0x140005629  lea     r8d, [r14+10h]
0x14000562d  lea     rdx, aCachefullnotif; "cacheFullNotificationIntervalTime"
0x140005634  lea     rcx, [rbp+7B0h+var_180]
0x14000563b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140005640  nop
0x140005641  mov     edx, 1388h; int
0x140005646  lea     rcx, [rbp+7B0h+var_160]; this
0x14000564d  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140005652  nop
0x140005653  xorps   xmm0, xmm0
0x140005656  movups  [rbp+7B0h+var_100], xmm0
0x14000565d  xorps   xmm1, xmm1
0x140005660  movdqa  [rbp+7B0h+var_F0], xmm1
0x140005668  lea     r8d, [r14+14h]
0x14000566c  lea     rdx, aCachememoryful; "cacheMemoryFullNotificationPercentage"
0x140005673  lea     rcx, [rbp+7B0h+var_100]
0x14000567a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14000567f  nop
0x140005680  lea     edx, [r14+3Ah]; int
0x140005684  lea     rcx, [rbp+7B0h+var_E0]; this
0x14000568b  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140005690  nop
0x140005691  xorps   xmm0, xmm0
0x140005694  movups  [rbp+7B0h+var_80], xmm0
0x14000569b  xorps   xmm1, xmm1
0x14000569e  movdqa  [rbp+7B0h+var_70], xmm1
0x1400056a6  lea     r8d, [r14+4]
0x1400056aa  lea     rdx, aEnablenetworkd; "enableNetworkDetector"
0x1400056b1  lea     rcx, [rbp+7B0h+var_80]
0x1400056b8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400056bd  nop
0x1400056be  mov     dl, 1; bool
0x1400056c0  lea     rcx, [rbp+7B0h+var_60]; this
0x1400056c7  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x1400056cc  nop
0x1400056cd  lea     rax, [rsp+8B0h+var_880]
0x1400056d2  mov     [rsp+8B0h+var_890], rax
0x1400056d7  lea     rax, [rbp+7B0h+var_s0]
0x1400056de  mov     [rsp+8B0h+var_888], rax
0x1400056e3  lea     rdx, [rsp+8B0h+var_890]
0x1400056e8  lea     rcx, qword_1401E6100
0x1400056ef  call    ??0ILogConfiguration@Events@Applications@Microsoft@@QEAA@AEBV?$initializer_list@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VVariant@Events@Applications@Microsoft@@@std@@@std@@@Z; Microsoft::Applications::Events::ILogConfiguration::ILogConfiguration(std::initializer_list<std::pair<std::string const,Microsoft::Applications::Events::Variant>> const &)
0x1400056f4  nop
0x1400056f5  lea     r9, ??1?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VVariant@Events@Applications@Microsoft@@@std@@QEAA@XZ; void (*)(void *)
0x1400056fc  mov     r8d, r14d; unsigned __int64
0x1400056ff  lea     edx, [r14+6Fh]; unsigned __int64
0x140005703  lea     rcx, [rsp+8B0h+var_880]; void *
0x140005708  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14000570d  lea     rcx, Microsoft__Applications__Events___dynamic_atexit_destructor_for__currentConfig__
0x140005714  mov     r14, [rsp+8B0h+arg_0]
0x14000571c  add     rsp, 8B0h
0x140005723  pop     rbp
0x140005724  jmp     atexit
```
