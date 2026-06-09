# Microsoft::Applications::Events::_dynamic_initializer_for__defaultRuntimeConfig___2

- ea: `0x1400098e0`
- end: `0x14000a60c`
- name: `Microsoft::Applications::Events::_dynamic_initializer_for__defaultRuntimeConfig___2`
- size: `3372`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14003a360`
- `0x14003a680`
- `0x14003aab0`
- `0x14007e088`
- `0x14007e14c`
- `0x140084a18`
- `0x1400a9648`
- `0x1400aa604`
- `0x140103b14`
- `0x140103c00`
- `0x1401041f0`
- `0x140109eec`
- `0x140109f88`

## string_xrefs

- `0x140009c11`: `eventCollectorUri`
- `0x140009a25`: `cacheMemorySizeLimitInBytes`
- `0x140009c25`: `https://mobile.events.data.microsoft.com/OneCollector/1.0/`
- `0x1400099e6`: `cacheFileSizeLimitInBytes`
- `0x140009cd0`: `cacheMemoryFullNotificationPercentage`
- `0x140009c52`: `cacheFileFullNotificationPercentage`
- `0x140009c91`: `cacheFullNotificationIntervalTime`
- `0x14000a2c3`: `compat`
- `0x14000a211`: `backoffConfig`
- `0x14000a008`: `compress`
- `0x140009e69`: `tokenInt`
- `0x140009e29`: `tokenProd`

## pseudocode

```c
int Microsoft::Applications::Events::_dynamic_initializer_for__defaultRuntimeConfig___2()
{
  __int128 *v0; // rdx
  __int128 *v1; // rdx
  __int128 *v2; // rdx
  _OWORD *v3; // rdx
  _OWORD *v4; // rdx
  _OWORD *v5; // rdx
  _QWORD v7[3]; // [rsp+18h] [rbp-E8h] BYREF
  unsigned __int64 v8; // [rsp+30h] [rbp-D0h]
  _QWORD v9[3]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v10; // [rsp+50h] [rbp-B0h]
  _QWORD v11[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v12; // [rsp+70h] [rbp-90h]
  unsigned __int64 v13; // [rsp+78h] [rbp-88h]
  __int128 v14; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v15; // [rsp+90h] [rbp-70h]
  unsigned __int64 v16; // [rsp+98h] [rbp-68h]
  __int128 v17; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v18; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v19; // [rsp+B8h] [rbp-48h]
  __int128 v20; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v21; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v22; // [rsp+D8h] [rbp-28h]
  _QWORD v23[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v24[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v25[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v26[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v27[2]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v28[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v29[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v30[2]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v31[96]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v32[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v33[96]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v34[2]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v35[96]; // [rsp+270h] [rbp+170h] BYREF
  _OWORD v36[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v37[96]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _OWORD v38[2]; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v39[96]; // [rsp+370h] [rbp+270h] BYREF
  _OWORD v40[2]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v41[96]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _OWORD v42[2]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v43[96]; // [rsp+470h] [rbp+370h] BYREF
  _OWORD v44[2]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v45[96]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _OWORD v46[2]; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v47[96]; // [rsp+570h] [rbp+470h] BYREF
  _OWORD v48[2]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v49[96]; // [rsp+5F0h] [rbp+4F0h] BYREF
  _OWORD v50[2]; // [rsp+650h] [rbp+550h] BYREF
  _BYTE v51[96]; // [rsp+670h] [rbp+570h] BYREF
  _OWORD v52[2]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v53[96]; // [rsp+6F0h] [rbp+5F0h] BYREF
  _OWORD v54[2]; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v55[96]; // [rsp+770h] [rbp+670h] BYREF
  _OWORD v56[2]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _BYTE v57[96]; // [rsp+7F0h] [rbp+6F0h] BYREF
  _OWORD v58[2]; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v59[96]; // [rsp+870h] [rbp+770h] BYREF
  _OWORD v60[2]; // [rsp+8D0h] [rbp+7D0h] BYREF
  _BYTE v61[96]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _OWORD v62[2]; // [rsp+950h] [rbp+850h] BYREF
  _BYTE v63[96]; // [rsp+970h] [rbp+870h] BYREF
  _OWORD v64[2]; // [rsp+9D0h] [rbp+8D0h] BYREF
  _BYTE v65[96]; // [rsp+9F0h] [rbp+8F0h] BYREF
  _OWORD v66[2]; // [rsp+A50h] [rbp+950h] BYREF
  _BYTE v67[96]; // [rsp+A70h] [rbp+970h] BYREF
  _OWORD v68[2]; // [rsp+AD0h] [rbp+9D0h] BYREF
  _BYTE v69[96]; // [rsp+AF0h] [rbp+9F0h] BYREF
  _OWORD v70[2]; // [rsp+B50h] [rbp+A50h] BYREF
  _BYTE v71[96]; // [rsp+B70h] [rbp+A70h] BYREF
  _OWORD v72[2]; // [rsp+BD0h] [rbp+AD0h] BYREF
  _BYTE v73[96]; // [rsp+BF0h] [rbp+AF0h] BYREF
  _OWORD v74[2]; // [rsp+C50h] [rbp+B50h] BYREF
  _BYTE v75[96]; // [rsp+C70h] [rbp+B70h] BYREF
  _OWORD v76[2]; // [rsp+CD0h] [rbp+BD0h] BYREF
  _BYTE v77[96]; // [rsp+CF0h] [rbp+BF0h] BYREF
  _OWORD v78[2]; // [rsp+D50h] [rbp+C50h] BYREF
  _BYTE v79[96]; // [rsp+D70h] [rbp+C70h] BYREF
  _OWORD v80[2]; // [rsp+DD0h] [rbp+CD0h] BYREF
  _BYTE v81[96]; // [rsp+DF0h] [rbp+CF0h] BYREF
  _OWORD v82[2]; // [rsp+E50h] [rbp+D50h] BYREF
  _BYTE v83[96]; // [rsp+E70h] [rbp+D70h] BYREF
  _OWORD v84[2]; // [rsp+ED0h] [rbp+DD0h] BYREF
  _BYTE v85[96]; // [rsp+EF0h] [rbp+DF0h] BYREF
  _OWORD v86[2]; // [rsp+F50h] [rbp+E50h] BYREF
  _BYTE v87[96]; // [rsp+F70h] [rbp+E70h] BYREF
  _OWORD v88[2]; // [rsp+FD0h] [rbp+ED0h] BYREF
  _BYTE v89[96]; // [rsp+FF0h] [rbp+EF0h] BYREF
  _OWORD v90[2]; // [rsp+1050h] [rbp+F50h] BYREF
  _BYTE v91[96]; // [rsp+1070h] [rbp+F70h] BYREF
  _OWORD v92[2]; // [rsp+10D0h] [rbp+FD0h] BYREF
  _BYTE v93[96]; // [rsp+10F0h] [rbp+FF0h] BYREF
  _OWORD v94[2]; // [rsp+1150h] [rbp+1050h] BYREF
  _BYTE v95[96]; // [rsp+1170h] [rbp+1070h] BYREF
  _OWORD v96[2]; // [rsp+11D0h] [rbp+10D0h] BYREF
  _BYTE v97[96]; // [rsp+11F0h] [rbp+10F0h] BYREF
  _OWORD v98[2]; // [rsp+1250h] [rbp+1150h] BYREF
  _BYTE v99[96]; // [rsp+1270h] [rbp+1170h] BYREF
  _OWORD v100[2]; // [rsp+12D0h] [rbp+11D0h] BYREF
  _BYTE v101[96]; // [rsp+12F0h] [rbp+11F0h] BYREF
  _OWORD v102[2]; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v103[96]; // [rsp+1370h] [rbp+1270h] BYREF
  _OWORD v104[2]; // [rsp+13D0h] [rbp+12D0h] BYREF
  _BYTE v105[96]; // [rsp+13F0h] [rbp+12F0h] BYREF
  _OWORD v106[2]; // [rsp+1450h] [rbp+1350h] BYREF
  _BYTE v107[96]; // [rsp+1470h] [rbp+1370h] BYREF
  _BYTE v108[96]; // [rsp+14D0h] [rbp+13D0h] BYREF
  _BYTE v109[96]; // [rsp+1530h] [rbp+1430h] BYREF
  _BYTE v110[96]; // [rsp+1590h] [rbp+1490h] BYREF
  _BYTE v111[96]; // [rsp+15F0h] [rbp+14F0h] BYREF
  _BYTE v112[96]; // [rsp+1650h] [rbp+1550h] BYREF
  _BYTE v113[96]; // [rsp+16B0h] [rbp+15B0h] BYREF

  memset(v60, 0, sizeof(v60));
  std::string::_Construct<1,char const *>(v60, "minimumTraceLevel", 0x11u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v61, 4);
  memset(v62, 0, sizeof(v62));
  std::string::_Construct<1,char const *>(v62, "sdkmode", 7u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v63, 0);
  memset(v64, 0, sizeof(v64));
  std::string::_Construct<1,char const *>(v64, "enableLifecycleSession", 0x16u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v65, 0);
  memset(v66, 0, sizeof(v66));
  std::string::_Construct<1,char const *>(v66, "cacheFileSizeLimitInBytes", 0x19u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v67, 3145728);
  memset(v68, 0, sizeof(v68));
  std::string::_Construct<1,char const *>(v68, "cacheMemorySizeLimitInBytes", 0x1Bu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v69, 0x80000);
  memset(v70, 0, sizeof(v70));
  std::string::_Construct<1,char const *>(v70, "multiTenantEnabled", 0x12u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v71, 1);
  memset(v72, 0, sizeof(v72));
  std::string::_Construct<1,char const *>(v72, "enableDbDropIfFull", 0x12u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v73, 0);
  memset(v74, 0, sizeof(v74));
  std::string::_Construct<1,char const *>(v74, "maxTeardownUploadTimeInSec", 0x1Au);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v75, 1);
  memset(v76, 0, sizeof(v76));
  std::string::_Construct<1,char const *>(v76, "maxPendingHTTPRequests", 0x16u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v77, 4);
  memset(v78, 0, sizeof(v78));
  std::string::_Construct<1,char const *>(v78, "maxDBFlushQueues", 0x10u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v79, 3);
  memset(v80, 0, sizeof(v80));
  std::string::_Construct<1,char const *>(v80, "traceLevelMask", 0xEu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v81, 0);
  memset(v82, 0, sizeof(v82));
  std::string::_Construct<1,char const *>(v82, "enableTrace", 0xBu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v83, 1);
  memset(v84, 0, sizeof(v84));
  std::string::_Construct<1,char const *>(v84, "eventCollectorUri", 0x11u);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v85,
    "https://mobile.events.data.microsoft.com/OneCollector/1.0/");
  memset(v86, 0, sizeof(v86));
  std::string::_Construct<1,char const *>(v86, "cacheFileFullNotificationPercentage", 0x23u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v87, 75);
  memset(v88, 0, sizeof(v88));
  std::string::_Construct<1,char const *>(v88, "cacheFullNotificationIntervalTime", 0x21u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v89, 5000);
  memset(v90, 0, sizeof(v90));
  std::string::_Construct<1,char const *>(v90, "cacheMemoryFullNotificationPercentage", 0x25u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v91, 75);
  memset(v92, 0, sizeof(v92));
  std::string::_Construct<1,char const *>(v92, "enableNetworkDetector", 0x15u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v93, 1);
  memset(v94, 0, sizeof(v94));
  std::string::_Construct<1,char const *>(v94, "sessionResetEnabled", 0x13u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v95, 0);
  v20 = 0;
  v21 = 0;
  v22 = 0;
  std::string::_Construct<1,char const *>(&v20, "stats", 5u);
  memset(v52, 0, sizeof(v52));
  std::string::_Construct<1,char const *>(v52, "split", 5u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v53, 0);
  memset(v54, 0, sizeof(v54));
  std::string::_Construct<1,char const *>(v54, "interval", 8u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v55, 1800);
  memset(v56, 0, sizeof(v56));
  std::string::_Construct<1,char const *>(v56, "tokenProd", 9u);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v57,
    "4bb4d6f7cafc4e9292f972dca2dcde42-bd019ee8-e59c-4b0f-a02c-84e72157a3ef-7485");
  memset(v58, 0, sizeof(v58));
  std::string::_Construct<1,char const *>(v58, "tokenInt", 8u);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v59,
    "8130ef8ff472405d89d6f420038927ea-0c0d561e-cca5-4c81-90ed-0aa9ad786a03-7166");
  v23[0] = v52;
  v23[1] = v60;
  Microsoft::Applications::Events::Variant::Variant(v113, v23);
  memset(v96, 0, sizeof(v96));
  v0 = &v20;
  if ( v22 > 0xF )
    v0 = (__int128 *)v20;
  std::string::_Construct<2,char const *>((__int64)v96, v0, v21);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v97,
    (const struct Microsoft::Applications::Events::Variant *)v113);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  std::string::_Construct<1,char const *>(&v17, "utc", 3u);
  memset(v32, 0, sizeof(v32));
  std::string::_Construct<1,char const *>(v32, "enabled", 7u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v33, 0);
  v24[0] = v32;
  v24[1] = v34;
  Microsoft::Applications::Events::Variant::Variant(v112, v24);
  memset(v98, 0, sizeof(v98));
  v1 = &v17;
  if ( v19 > 0xF )
    v1 = (__int128 *)v17;
  std::string::_Construct<2,char const *>((__int64)v98, v1, v18);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v99,
    (const struct Microsoft::Applications::Events::Variant *)v112);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  std::string::_Construct<1,char const *>(&v14, "http", 4u);
  memset(v38, 0, sizeof(v38));
  std::string::_Construct<1,char const *>(v38, "compress", 8u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v39, 1);
  memset(v40, 0, sizeof(v40));
  std::string::_Construct<1,char const *>(v40, "contentEncoding", 0xFu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v41, "deflate");
  memset(v42, 0, sizeof(v42));
  std::string::_Construct<1,char const *>(v42, "msRootCheck", 0xBu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v43, 0);
  v25[0] = v38;
  v25[1] = v44;
  Microsoft::Applications::Events::Variant::Variant(v111, v25);
  memset(v100, 0, sizeof(v100));
  v2 = &v14;
  if ( v16 > 0xF )
    v2 = (__int128 *)v14;
  std::string::_Construct<2,char const *>((__int64)v100, v2, v15);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v101,
    (const struct Microsoft::Applications::Events::Variant *)v111);
  *(_OWORD *)&v11[1] = 0;
  v12 = 0;
  v13 = 0;
  std::string::_Construct<1,char const *>(&v11[1], "tpm", 3u);
  memset(v44, 0, sizeof(v44));
  std::string::_Construct<1,char const *>(v44, "maxBlobSize", 0xBu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v45, 0x200000);
  memset(v46, 0, sizeof(v46));
  std::string::_Construct<1,char const *>(v46, "maxRetryCount", 0xDu);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v47, 5);
  memset(v48, 0, sizeof(v48));
  std::string::_Construct<1,char const *>(v48, "clockSkewEnabled", 0x10u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v49, 1);
  memset(v50, 0, sizeof(v50));
  std::string::_Construct<1,char const *>(v50, "backoffConfig", 0xDu);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v51,
    "E,3000,300000,2,1");
  v26[0] = v44;
  v26[1] = v52;
  Microsoft::Applications::Events::Variant::Variant(v110, v26);
  memset(v102, 0, sizeof(v102));
  v3 = &v11[1];
  if ( v13 > 0xF )
    v3 = (_OWORD *)v11[1];
  std::string::_Construct<2,char const *>((__int64)v102, v3, v12);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v103,
    (const struct Microsoft::Applications::Events::Variant *)v110);
  *(_OWORD *)&v9[1] = 0;
  v10 = 0;
  v11[0] = 0;
  std::string::_Construct<1,char const *>(&v9[1], "compat", 6u);
  memset(v34, 0, sizeof(v34));
  std::string::_Construct<1,char const *>(v34, "dotType", 7u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v35, 1);
  memset(v36, 0, sizeof(v36));
  std::string::_Construct<1,char const *>(v36, "customTypePrefix", 0x10u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v37, "custom");
  v27[0] = v34;
  v27[1] = v38;
  Microsoft::Applications::Events::Variant::Variant(v109, v27);
  memset(v104, 0, sizeof(v104));
  v4 = &v9[1];
  if ( v11[0] > 0xFu )
    v4 = (_OWORD *)v9[1];
  std::string::_Construct<2,char const *>((__int64)v104, v4, v10);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v105,
    (const struct Microsoft::Applications::Events::Variant *)v109);
  *(_OWORD *)&v7[1] = 0;
  v8 = 0;
  v9[0] = 0;
  std::string::_Construct<1,char const *>(&v7[1], "sample", 6u);
  memset(v30, 0, sizeof(v30));
  std::string::_Construct<1,char const *>(v30, "rate", 4u);
  Microsoft::Applications::Events::Variant::Variant((Microsoft::Applications::Events::Variant *)v31, 0);
  v28[0] = v30;
  v28[1] = v32;
  Microsoft::Applications::Events::Variant::Variant(v108, v28);
  memset(v106, 0, sizeof(v106));
  v5 = &v7[1];
  if ( v9[0] > 0xFu )
    v5 = (_OWORD *)v7[1];
  std::string::_Construct<2,char const *>((__int64)v106, v5, v8);
  Microsoft::Applications::Events::Variant::Variant(
    (Microsoft::Applications::Events::Variant *)v107,
    (const struct Microsoft::Applications::Events::Variant *)v108);
  v29[0] = v60;
  v29[1] = v108;
  Microsoft::Applications::Events::ILogConfiguration::ILogConfiguration(qword_1401E6ED0, v29);
  `eh vector destructor iterator'(
    v60,
    0x80u,
    0x18u,
    std::pair<std::string const,Microsoft::Applications::Events::Variant>::~pair<std::string const,Microsoft::Applications::Events::Variant>);
  Microsoft::Applications::Events::Variant::~Variant((Microsoft::Applications::Events::Variant *)v108);
  `eh vector destructor iterator'(
    v30,
    0x80u,
    1u,
    std::pair<std::string const,Microsoft::Applications::Events::Variant>::~pair<std::string const,Microsoft::Applications::Events::Variant>);
  std::string::_Tidy_deallocate(&v7[1]);
  Microsoft::Applications::Events::Variant::~Variant((Microsoft::Applications::Events::Variant *)v109);
  `eh vector destructor iterator'(
    v34,
    0x80u,
    2u,
    std::pair<std::string const,Microsoft::Applications::Events::Variant>::~pair<std::string const,Microsoft::Applications::Events::Variant>);
  std::string::_Tidy_deallocate(&v9[1]);
  Microsoft::Applications::Events::Variant::~Variant((Microsoft::Applications::Events::Variant *)v110);
  `eh vector destructor iterator'(
    v44,
    0x80u,
    4u,
    std::pair<std::string const,Microsoft::Applications::Events::Variant>::~pair<std::string const,Microsoft::Applications::Events::Variant>);
  std::string::_Tidy_deallocate(&v11[1]);
  Microsoft::Applications::Events::Variant::~Variant((Microsoft::Applications::Events::Variant *)v111);
  `eh vector destructor iterator'(
    v38,
    0x80u,
    3u,
    std::pair<std::string const,Microsoft::Applications::Events::Variant>::~pair<std::string const,Microsoft::Applications::Events::Variant>);
  std::string::_Tidy_deallocate(&v14);
  Microsoft::Applications::Events::Variant::~Variant((Microsoft::Applications::Events::Variant *)v112);
  `eh vector destructor iterator'(
    v32,
    0x80u,
    1u,
    std::pair<std::string const,Microsoft::Applications::Events::Variant>::~pair<std::string const,Microsoft::Applications::Events::Variant>);
  std::string::_Tidy_deallocate(&v17);
  Microsoft::Applications::Events::Variant::~Variant((Microsoft::Applications::Events::Variant *)v113);
  `eh vector destructor iterator'(
    v52,
    0x80u,
    4u,
    std::pair<std::string const,Microsoft::Applications::Events::Variant>::~pair<std::string const,Microsoft::Applications::Events::Variant>);
  std::string::_Tidy_deallocate(&v20);
  return atexit((void (__cdecl *)())Microsoft::Applications::Events::_dynamic_atexit_destructor_for__defaultRuntimeConfig___2);
}

```

## disassembly

```asm
0x1400098e0  mov     rax, rsp
0x1400098e3  mov     [rax+8], rbx
0x1400098e7  mov     [rax+10h], rdi
0x1400098eb  mov     [rax+18h], r12
0x1400098ef  mov     [rax+20h], r13
0x1400098f3  push    rbp
0x1400098f4  push    r14
0x1400098f6  push    r15
0x1400098f8  lea     rbp, [rax-1628h]
0x1400098ff  mov     eax, 1710h
0x140009904  call    _alloca_probe
0x140009909  sub     rsp, rax
0x14000990c  xorps   xmm0, xmm0
0x14000990f  movups  [rbp+1620h+var_E50], xmm0
0x140009916  xorps   xmm1, xmm1
0x140009919  movdqa  [rbp+1620h+var_E40], xmm1
0x140009921  mov     r8d, 11h
0x140009927  lea     rdx, aMinimumtracele; "minimumTraceLevel"
0x14000992e  lea     rcx, [rbp+1620h+var_E50]
0x140009935  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14000993a  nop
0x14000993b  mov     edx, 4; int
0x140009940  lea     rcx, [rbp+1620h+var_E30]; this
0x140009947  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x14000994c  nop
0x14000994d  xorps   xmm0, xmm0
0x140009950  movups  [rbp+1620h+var_DD0], xmm0
0x140009957  xorps   xmm1, xmm1
0x14000995a  movdqa  [rbp+1620h+var_DC0], xmm1
0x140009962  mov     r13d, 7
0x140009968  mov     r8d, r13d
0x14000996b  lea     rdx, aSdkmode; "sdkmode"
0x140009972  lea     rcx, [rbp+1620h+var_DD0]
0x140009979  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14000997e  nop
0x14000997f  xor     edx, edx; int
0x140009981  lea     rcx, [rbp+1620h+var_DB0]; this
0x140009988  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x14000998d  nop
0x14000998e  xorps   xmm0, xmm0
0x140009991  movups  [rbp+1620h+var_D50], xmm0
0x140009998  xorps   xmm1, xmm1
0x14000999b  movdqa  [rbp+1620h+var_D40], xmm1
0x1400099a3  lea     edi, [r13+0Fh]
0x1400099a7  mov     r8d, edi
0x1400099aa  lea     rdx, aEnablelifecycl; "enableLifecycleSession"
0x1400099b1  lea     rcx, [rbp+1620h+var_D50]
0x1400099b8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400099bd  nop
0x1400099be  xor     edx, edx; bool
0x1400099c0  lea     rcx, [rbp+1620h+var_D30]; this
0x1400099c7  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x1400099cc  nop
0x1400099cd  xorps   xmm0, xmm0
0x1400099d0  movups  [rbp+1620h+var_CD0], xmm0
0x1400099d7  xorps   xmm1, xmm1
0x1400099da  movdqa  [rbp+1620h+var_CC0], xmm1
0x1400099e2  lea     r8d, [r13+12h]
0x1400099e6  lea     rdx, aCachefilesizel; "cacheFileSizeLimitInBytes"
0x1400099ed  lea     rcx, [rbp+1620h+var_CD0]
0x1400099f4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400099f9  nop
0x1400099fa  mov     edx, 300000h; int
0x1400099ff  lea     rcx, [rbp+1620h+var_CB0]; this
0x140009a06  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009a0b  nop
0x140009a0c  xorps   xmm0, xmm0
0x140009a0f  movups  [rbp+1620h+var_C50], xmm0
0x140009a16  xorps   xmm1, xmm1
0x140009a19  movdqa  [rbp+1620h+var_C40], xmm1
0x140009a21  lea     r8d, [r13+14h]
0x140009a25  lea     rdx, aCachememorysiz; "cacheMemorySizeLimitInBytes"
0x140009a2c  lea     rcx, [rbp+1620h+var_C50]
0x140009a33  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009a38  nop
0x140009a39  mov     edx, 80000h; int
0x140009a3e  lea     rcx, [rbp+1620h+var_C30]; this
0x140009a45  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009a4a  nop
0x140009a4b  xorps   xmm0, xmm0
0x140009a4e  movups  [rbp+1620h+var_BD0], xmm0
0x140009a55  xorps   xmm1, xmm1
0x140009a58  movdqa  [rbp+1620h+var_BC0], xmm1
0x140009a60  lea     ebx, [rdi-4]
0x140009a63  mov     r8d, ebx
0x140009a66  lea     rdx, aMultitenantena; "multiTenantEnabled"
0x140009a6d  lea     rcx, [rbp+1620h+var_BD0]
0x140009a74  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009a79  nop
0x140009a7a  mov     dl, 1; bool
0x140009a7c  lea     rcx, [rbp+1620h+var_BB0]; this
0x140009a83  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x140009a88  nop
0x140009a89  xorps   xmm0, xmm0
0x140009a8c  movups  [rbp+1620h+var_B50], xmm0
0x140009a93  xorps   xmm1, xmm1
0x140009a96  movdqa  [rbp+1620h+var_B40], xmm1
0x140009a9e  mov     r8d, ebx
0x140009aa1  lea     rdx, aEnabledbdropif; "enableDbDropIfFull"
0x140009aa8  lea     rcx, [rbp+1620h+var_B50]
0x140009aaf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009ab4  nop
0x140009ab5  xor     edx, edx; bool
0x140009ab7  lea     rcx, [rbp+1620h+var_B30]; this
0x140009abe  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x140009ac3  nop
0x140009ac4  xorps   xmm0, xmm0
0x140009ac7  movups  [rbp+1620h+var_AD0], xmm0
0x140009ace  xorps   xmm1, xmm1
0x140009ad1  movdqa  [rbp+1620h+var_AC0], xmm1
0x140009ad9  lea     r8d, [r13+13h]
0x140009add  lea     rdx, aMaxteardownupl; "maxTeardownUploadTimeInSec"
0x140009ae4  lea     rcx, [rbp+1620h+var_AD0]
0x140009aeb  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009af0  nop
0x140009af1  lea     edx, [rdi-15h]; int
0x140009af4  lea     rcx, [rbp+1620h+var_AB0]; this
0x140009afb  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009b00  nop
0x140009b01  xorps   xmm0, xmm0
0x140009b04  movups  [rbp+1620h+var_A50], xmm0
0x140009b0b  xorps   xmm1, xmm1
0x140009b0e  movdqa  [rbp+1620h+var_A40], xmm1
0x140009b16  mov     r8d, edi
0x140009b19  lea     rdx, aMaxpendinghttp; "maxPendingHTTPRequests"
0x140009b20  lea     rcx, [rbp+1620h+var_A50]
0x140009b27  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009b2c  nop
0x140009b2d  lea     edx, [rdi-12h]; int
0x140009b30  lea     rcx, [rbp+1620h+var_A30]; this
0x140009b37  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009b3c  nop
0x140009b3d  xorps   xmm0, xmm0
0x140009b40  movups  [rbp+1620h+var_9D0], xmm0
0x140009b47  xorps   xmm1, xmm1
0x140009b4a  movdqa  [rbp+1620h+var_9C0], xmm1
0x140009b52  lea     r12d, [r13+9]
0x140009b56  mov     r8d, r12d
0x140009b59  lea     rdx, aMaxdbflushqueu; "maxDBFlushQueues"
0x140009b60  lea     rcx, [rbp+1620h+var_9D0]
0x140009b67  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009b6c  nop
0x140009b6d  lea     edx, [rdi-13h]; int
0x140009b70  lea     rcx, [rbp+1620h+var_9B0]; this
0x140009b77  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009b7c  nop
0x140009b7d  xorps   xmm0, xmm0
0x140009b80  movups  [rbp+1620h+var_950], xmm0
0x140009b87  xorps   xmm1, xmm1
0x140009b8a  movdqa  [rbp+1620h+var_940], xmm1
0x140009b92  lea     r8d, [r13+7]
0x140009b96  lea     rdx, aTracelevelmask; "traceLevelMask"
0x140009b9d  lea     rcx, [rbp+1620h+var_950]
0x140009ba4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009ba9  nop
0x140009baa  xor     edx, edx; int
0x140009bac  lea     rcx, [rbp+1620h+var_930]; this
0x140009bb3  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009bb8  nop
0x140009bb9  xorps   xmm0, xmm0
0x140009bbc  movups  [rbp+1620h+var_8D0], xmm0
0x140009bc3  xorps   xmm1, xmm1
0x140009bc6  movdqa  [rbp+1620h+var_8C0], xmm1
0x140009bce  lea     r14d, [r13+4]
0x140009bd2  mov     r8d, r14d
0x140009bd5  lea     rdx, aEnabletrace; "enableTrace"
0x140009bdc  lea     rcx, [rbp+1620h+var_8D0]
0x140009be3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009be8  nop
0x140009be9  mov     dl, 1; bool
0x140009beb  lea     rcx, [rbp+1620h+var_8B0]; this
0x140009bf2  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x140009bf7  nop
0x140009bf8  xorps   xmm0, xmm0
0x140009bfb  movups  [rbp+1620h+var_850], xmm0
0x140009c02  xorps   xmm1, xmm1
0x140009c05  movdqa  [rbp+1620h+var_840], xmm1
0x140009c0d  lea     r8d, [r13+0Ah]
0x140009c11  lea     rdx, aEventcollector; "eventCollectorUri"
0x140009c18  lea     rcx, [rbp+1620h+var_850]
0x140009c1f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009c24  nop
0x140009c25  lea     rdx, aHttpsMobileEve_0; "https://mobile.events.data.microsoft.co"...
0x140009c2c  lea     rcx, [rbp+1620h+var_830]; this
0x140009c33  call    ??0Variant@Events@Applications@Microsoft@@QEAA@PEBD@Z; Microsoft::Applications::Events::Variant::Variant(char const *)
0x140009c38  nop
0x140009c39  xorps   xmm0, xmm0
0x140009c3c  movups  [rbp+1620h+var_7D0], xmm0
0x140009c43  xorps   xmm1, xmm1
0x140009c46  movdqa  [rbp+1620h+var_7C0], xmm1
0x140009c4e  lea     r8d, [r13+1Ch]
0x140009c52  lea     rdx, aCachefilefulln; "cacheFileFullNotificationPercentage"
0x140009c59  lea     rcx, [rbp+1620h+var_7D0]
0x140009c60  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009c65  nop
0x140009c66  lea     ebx, [rdi+35h]
0x140009c69  mov     edx, ebx; int
0x140009c6b  lea     rcx, [rbp+1620h+var_7B0]; this
0x140009c72  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009c77  nop
0x140009c78  xorps   xmm0, xmm0
0x140009c7b  movups  [rbp+1620h+var_750], xmm0
0x140009c82  xorps   xmm1, xmm1
0x140009c85  movdqa  [rbp+1620h+var_740], xmm1
0x140009c8d  lea     r8d, [r13+1Ah]
0x140009c91  lea     rdx, aCachefullnotif; "cacheFullNotificationIntervalTime"
0x140009c98  lea     rcx, [rbp+1620h+var_750]
0x140009c9f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009ca4  nop
0x140009ca5  mov     edx, 1388h; int
0x140009caa  lea     rcx, [rbp+1620h+var_730]; this
0x140009cb1  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009cb6  nop
0x140009cb7  xorps   xmm0, xmm0
0x140009cba  movups  [rbp+1620h+var_6D0], xmm0
0x140009cc1  xorps   xmm1, xmm1
0x140009cc4  movdqa  [rbp+1620h+var_6C0], xmm1
0x140009ccc  lea     r8d, [r13+1Eh]
0x140009cd0  lea     rdx, aCachememoryful; "cacheMemoryFullNotificationPercentage"
0x140009cd7  lea     rcx, [rbp+1620h+var_6D0]
0x140009cde  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009ce3  nop
0x140009ce4  mov     edx, ebx; int
0x140009ce6  lea     rcx, [rbp+1620h+var_6B0]; this
0x140009ced  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009cf2  nop
0x140009cf3  xorps   xmm0, xmm0
0x140009cf6  movups  [rbp+1620h+var_650], xmm0
0x140009cfd  xorps   xmm1, xmm1
0x140009d00  movdqa  [rbp+1620h+var_640], xmm1
0x140009d08  lea     r8d, [r13+0Eh]
0x140009d0c  lea     rdx, aEnablenetworkd; "enableNetworkDetector"
0x140009d13  lea     rcx, [rbp+1620h+var_650]
0x140009d1a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009d1f  nop
0x140009d20  mov     dl, 1; bool
0x140009d22  lea     rcx, [rbp+1620h+var_630]; this
0x140009d29  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x140009d2e  nop
0x140009d2f  xorps   xmm0, xmm0
0x140009d32  movups  [rbp+1620h+var_5D0], xmm0
0x140009d39  xorps   xmm1, xmm1
0x140009d3c  movdqa  [rbp+1620h+var_5C0], xmm1
0x140009d44  lea     r8d, [r13+0Ch]
0x140009d48  lea     rdx, aSessionreseten; "sessionResetEnabled"
0x140009d4f  lea     rcx, [rbp+1620h+var_5D0]
0x140009d56  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009d5b  nop
0x140009d5c  xor     edx, edx; bool
0x140009d5e  lea     rcx, [rbp+1620h+var_5B0]; this
0x140009d65  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x140009d6a  nop
0x140009d6b  xorps   xmm0, xmm0
0x140009d6e  movups  [rbp+1620h+var_1660], xmm0
0x140009d72  xor     r15d, r15d
0x140009d75  mov     [rbp+1620h+var_1650], r15
0x140009d79  mov     [rbp+1620h+var_1648], r15
0x140009d7d  lea     edi, [rbx-46h]
0x140009d80  mov     r8d, edi
0x140009d83  lea     rdx, aStats; "stats"
0x140009d8a  lea     rcx, [rbp+1620h+var_1660]
0x140009d8e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009d93  nop
0x140009d94  xorps   xmm0, xmm0
0x140009d97  movups  [rbp+1620h+var_1050], xmm0
0x140009d9e  xorps   xmm1, xmm1
0x140009da1  movdqa  [rbp+1620h+var_1040], xmm1
0x140009da9  mov     r8d, edi
0x140009dac  lea     rdx, aSplit; "split"
0x140009db3  lea     rcx, [rbp+1620h+var_1050]
0x140009dba  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009dbf  nop
0x140009dc0  xor     edx, edx; bool
0x140009dc2  lea     rcx, [rbp+1620h+var_1030]; this
0x140009dc9  call    ??0Variant@Events@Applications@Microsoft@@QEAA@_N@Z; Microsoft::Applications::Events::Variant::Variant(bool)
0x140009dce  nop
0x140009dcf  xorps   xmm0, xmm0
0x140009dd2  movups  [rbp+1620h+var_FD0], xmm0
0x140009dd9  xorps   xmm1, xmm1
0x140009ddc  movdqa  [rbp+1620h+var_FC0], xmm1
0x140009de4  lea     ebx, [rdi+3]
0x140009de7  mov     r8d, ebx
0x140009dea  lea     rdx, aInterval; "interval"
0x140009df1  lea     rcx, [rbp+1620h+var_FD0]
0x140009df8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009dfd  nop
0x140009dfe  mov     edx, 708h; int
0x140009e03  lea     rcx, [rbp+1620h+var_FB0]; this
0x140009e0a  call    ??0Variant@Events@Applications@Microsoft@@QEAA@H@Z; Microsoft::Applications::Events::Variant::Variant(int)
0x140009e0f  nop
0x140009e10  xorps   xmm0, xmm0
0x140009e13  movups  [rbp+1620h+var_F50], xmm0
0x140009e1a  xorps   xmm1, xmm1
0x140009e1d  movdqa  [rbp+1620h+var_F40], xmm1
0x140009e25  lea     r8d, [r13+2]
0x140009e29  lea     rdx, aTokenprod; "tokenProd"
0x140009e30  lea     rcx, [rbp+1620h+var_F50]
0x140009e37  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140009e3c  nop
0x140009e3d  lea     rdx, a4bb4d6f7cafc4e; "4bb4d6f7cafc4e9292f972dca2dcde42-bd019e"...
  ... truncated ...
```
