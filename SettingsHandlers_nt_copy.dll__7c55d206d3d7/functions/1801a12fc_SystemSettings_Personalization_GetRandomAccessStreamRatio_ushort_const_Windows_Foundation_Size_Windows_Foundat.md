# SystemSettings::Personalization::GetRandomAccessStreamRatio(ushort const *,Windows::Foundation::Size,Windows::Foundation::Size *,ushort const *)

- ea: `0x1801a12fc`
- end: `0x1801a1628`
- name: `?GetRandomAccessStreamRatio@Personalization@SystemSettings@@YA?AV?$com_ptr_t@UIRandomAccessStream@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@PEBGUSize@Foundation@Windows@@PEAU567@0@Z`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801a1898`

## callees

- `0x18000d3bc`
- `0x1800236e0`
- `0x1800496fc`
- `0x180172410`
- `0x1801a12fc`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a13f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a13f0`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1801a13b7`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1801a13b7`
- `SHELL32!SHCreateItemFromParsingName` at `0x1801a1371`
- `SHELL32!SHCreateItemFromParsingName` at `0x1801a1371`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x1801a14f4`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x1801a14f4`

## string_xrefs

- `0x1801a1598`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1801a15ad`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a15c2`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a15d7`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a15ec`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1601`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1616`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall SystemSettings::Personalization::GetRandomAccessStreamRatio(
        _QWORD *a1,
        const WCHAR *a2,
        __int64 a3,
        float *a4,
        _WORD *a5)
{
  IBindCtx *v8; // rdx
  int v9; // eax
  HRESULT v10; // eax
  void *v11; // rcx
  HRESULT v12; // eax
  int v13; // eax
  int v14; // edi
  __int64 v15; // rcx
  int v16; // r14d
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 (__fastcall ***v20)(_QWORD, GUID *, _QWORD *); // rcx
  int v21; // eax
  int v23; // [rsp+28h] [rbp-81h]
  int v24; // [rsp+28h] [rbp-81h]
  void *ppv; // [rsp+58h] [rbp-51h] BYREF
  __int64 v26; // [rsp+60h] [rbp-49h] BYREF
  IBindCtx *pbc; // [rsp+68h] [rbp-41h] BYREF
  int v28; // [rsp+70h] [rbp-39h] BYREF
  int v29; // [rsp+74h] [rbp-35h] BYREF
  __int64 v30; // [rsp+78h] [rbp-31h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD *); // [rsp+80h] [rbp-29h] BYREF
  LPVOID v32; // [rsp+88h] [rbp-21h] BYREF
  __int64 v33; // [rsp+90h] [rbp-19h]
  __int64 v34; // [rsp+A0h] [rbp-9h]
  __int64 v35; // [rsp+A8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+57h]

  v34 = a3;
  v8 = 0;
  pbc = 0;
  if ( a5 && *a5 )
  {
    pbc = 0;
    v9 = _CreatePropertyBagBindCtx<unsigned short const *>(a1, 0, a5, &pbc);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3EE,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v9,
        v23);
    v8 = pbc;
  }
  ppv = 0;
  v10 = SHCreateItemFromParsingName(a2, v8, &GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc, &ppv);
  if ( v10 < 0 )
  {
    v11 = ppv;
    ppv = 0;
    if ( v11 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    v10 = SHCreateItemInKnownFolder(&FOLDERID_AppsFolder, 0, a2, &GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc, &ppv);
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F8,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalizationda"
                    "taaccesshelper.cpp",
      (const char *)(unsigned int)v10,
      v23);
  v32 = 0;
  v12 = CoCreateInstance(&CLSID_ImageSanitizationValidator, 0, 0x17u, &GUID_3a05b5ea_527e_4c9b_ba53_58aca78d0b56, &v32);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3FC,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalizationda"
                    "taaccesshelper.cpp",
      (const char *)(unsigned int)v12,
      v24);
  v30 = 0;
  v13 = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *, __int64 *))(*(_QWORD *)v32 + 24LL))(v32, a2, &v30);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalizationda"
                    "taaccesshelper.cpp",
      (const char *)(unsigned int)v13,
      v24);
  v14 = (int)o_ceil_0(retaddr);
  LODWORD(v33) = v14;
  v16 = (int)o_ceil_0(v15);
  HIDWORD(v33) = v16;
  v26 = 0;
  v35 = 0;
  v29 = 0;
  v28 = 0;
  v17 = *(_QWORD *)ppv;
  v26 = 0;
  v18 = (*(__int64 (__fastcall **)(void *, __int64, __int64, int *))(v17 + 48))(ppv, v33, 264, &v29);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40B,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalizationda"
                    "taaccesshelper.cpp",
      (const char *)(unsigned int)v18,
      (int)&v28);
  v31 = 0;
  v19 = CreateRandomAccessStreamOverStream(v26, 0, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v31);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40E,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalizationda"
                    "taaccesshelper.cpp",
      (const char *)(unsigned int)v19,
      (int)&v28);
  *a4 = (float)v14;
  a4[1] = (float)v16;
  v20 = v31;
  *a1 = 0;
  v21 = (**v20)(v20, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, a1);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v21,
      (int)&v28);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v31);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v26);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v32);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&ppv);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&pbc);
  return a1;
}

```

## disassembly

```asm
0x1801a12fc  mov     rax, rsp
0x1801a12ff  push    rbp
0x1801a1300  push    rbx
0x1801a1301  push    rsi
0x1801a1302  push    rdi
0x1801a1303  push    r14
0x1801a1305  push    r15
0x1801a1307  lea     rbp, [rax-57h]
0x1801a130b  sub     rsp, 0C8h
0x1801a1312  movaps  xmmword ptr [rax-48h], xmm6
0x1801a1316  mov     rsi, r9
0x1801a1319  mov     rdi, rdx
0x1801a131c  mov     rbx, rcx
0x1801a131f  movq    xmm6, r8
0x1801a1324  movsd   [rbp+4Fh+var_58], xmm6
0x1801a1329  xor     r15d, r15d
0x1801a132c  mov     edx, r15d
0x1801a132f  mov     [rbp+4Fh+pbc], rdx
0x1801a1333  mov     r8, [rbp+4Fh+arg_20]
0x1801a1337  test    r8, r8
0x1801a133a  jz      short loc_1801A135F
0x1801a133c  cmp     [r8], r15w
0x1801a1340  jz      short loc_1801A135F
0x1801a1342  mov     [rbp+4Fh+pbc], r15
0x1801a1346  lea     r9, [rbp+4Fh+pbc]
0x1801a134a  call    ??$_CreatePropertyBagBindCtx@PEBG@@YAJPEAUIBindCtx@@PEBG1PEAPEAU0@@Z; _CreatePropertyBagBindCtx<ushort const *>(IBindCtx *,ushort const *,ushort const *,IBindCtx * *)
0x1801a134f  mov     rcx, [rbp+57h]; this
0x1801a1353  test    eax, eax
0x1801a1355  js      loc_1801A15AA
0x1801a135b  mov     rdx, [rbp+4Fh+pbc]; pbc
0x1801a135f  mov     [rbp+4Fh+ppv], r15
0x1801a1363  lea     r9, [rbp+4Fh+ppv]; ppv
0x1801a1367  lea     r8, _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc; riid
0x1801a136e  mov     rcx, rdi; pszPath
0x1801a1371  call    cs:__imp_SHCreateItemFromParsingName
0x1801a1378  nop     dword ptr [rax+rax+00h]
0x1801a137d  test    eax, eax
0x1801a137f  jns     short loc_1801A13C3
0x1801a1381  mov     rcx, [rbp+4Fh+ppv]
0x1801a1385  mov     [rbp+4Fh+ppv], r15
0x1801a1389  test    rcx, rcx
0x1801a138c  jz      short loc_1801A139B
0x1801a138e  mov     rax, [rcx]
0x1801a1391  mov     rax, [rax+10h]
0x1801a1395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a139a  nop
0x1801a139b  lea     rax, [rbp+4Fh+ppv]
0x1801a139f  mov     [rsp+0F0h+var_D0], rax; int
0x1801a13a4  lea     r9, _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc; riid
0x1801a13ab  mov     r8, rdi; pszItem
0x1801a13ae  xor     edx, edx; dwKFFlags
0x1801a13b0  lea     rcx, FOLDERID_AppsFolder; kfid
0x1801a13b7  call    cs:__imp_SHCreateItemInKnownFolder
0x1801a13be  nop     dword ptr [rax+rax+00h]
0x1801a13c3  mov     rcx, [rbp+57h]; this
0x1801a13c7  test    eax, eax
0x1801a13c9  js      loc_1801A15BF
0x1801a13cf  mov     [rbp+4Fh+var_70], r15
0x1801a13d3  lea     rax, [rbp+4Fh+var_70]
0x1801a13d7  mov     [rsp+0F0h+var_D0], rax; int
0x1801a13dc  lea     r9, _GUID_3a05b5ea_527e_4c9b_ba53_58aca78d0b56; riid
0x1801a13e3  xor     edx, edx; pUnkOuter
0x1801a13e5  lea     r8d, [rdx+17h]; dwClsContext
0x1801a13e9  lea     rcx, CLSID_ImageSanitizationValidator; rclsid
0x1801a13f0  call    cs:__imp_CoCreateInstance
0x1801a13f7  nop     dword ptr [rax+rax+00h]
0x1801a13fc  mov     rcx, [rbp+57h]; this
0x1801a1400  test    eax, eax
0x1801a1402  js      loc_1801A15D4
0x1801a1408  mov     [rbp+4Fh+var_80], r15
0x1801a140c  mov     rcx, [rbp+4Fh+var_70]
0x1801a1410  mov     rax, [rcx]
0x1801a1413  lea     r8, [rbp+4Fh+var_80]
0x1801a1417  mov     rdx, rdi
0x1801a141a  mov     rax, [rax+18h]
0x1801a141e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1423  mov     rcx, [rbp+57h]; this
0x1801a1427  test    eax, eax
0x1801a1429  js      loc_1801A15E9
0x1801a142f  maxss   xmm6, dword ptr [rbp+4Fh+var_58+4]
0x1801a1434  cvtss2sd xmm6, xmm6
0x1801a1438  movd    xmm0, dword ptr [rbp+4Fh+var_80]
0x1801a143d  cvtdq2pd xmm0, xmm0
0x1801a1441  mulsd   xmm0, xmm6
0x1801a1445  call    _o_ceil_0
0x1801a144a  cvttsd2si rdi, xmm0
0x1801a144f  mov     dword ptr [rbp+4Fh+var_68], edi
0x1801a1452  movd    xmm0, dword ptr [rbp+4Fh+var_80+4]
0x1801a1457  cvtdq2pd xmm0, xmm0
0x1801a145b  mulsd   xmm0, xmm6
0x1801a145f  call    _o_ceil_0
0x1801a1464  cvttsd2si r14, xmm0
0x1801a1469  mov     dword ptr [rbp+4Fh+var_68+4], r14d
0x1801a146d  mov     [rbp+4Fh+var_98], r15
0x1801a1471  mov     [rbp+4Fh+var_50], r15
0x1801a1475  mov     [rbp+4Fh+var_84], r15d
0x1801a1479  mov     [rbp+4Fh+var_88], r15d
0x1801a147d  mov     dword ptr [rbp+4Fh+arg_20], r15d
0x1801a1481  mov     rcx, [rbp+4Fh+ppv]
0x1801a1485  mov     rax, [rcx]
0x1801a1488  mov     [rbp+4Fh+var_98], r15
0x1801a148c  lea     rdx, [rbp+4Fh+var_98]
0x1801a1490  mov     [rsp+40h], rdx
0x1801a1495  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1801a149c  mov     [rsp+0F0h+var_B8], rdx
0x1801a14a1  lea     rdx, [rbp+4Fh+var_50]
0x1801a14a5  mov     [rsp+0F0h+var_C0], rdx
0x1801a14aa  lea     rdx, [rbp+4Fh+arg_20]
0x1801a14ae  mov     [rsp+0F0h+var_C8], rdx
0x1801a14b3  lea     rdx, [rbp+4Fh+var_88]
0x1801a14b7  mov     [rsp+0F0h+var_D0], rdx; int
0x1801a14bc  lea     r9, [rbp+4Fh+var_84]
0x1801a14c0  mov     r8d, 108h
0x1801a14c6  mov     rdx, [rbp+4Fh+var_68]
0x1801a14ca  mov     rax, [rax+30h]
0x1801a14ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a14d3  mov     rcx, [rbp+57h]; this
0x1801a14d7  test    eax, eax
0x1801a14d9  js      loc_1801A15FE
0x1801a14df  mov     [rbp+4Fh+var_78], r15
0x1801a14e3  lea     r9, [rbp+4Fh+var_78]
0x1801a14e7  lea     r8, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1801a14ee  xor     edx, edx
0x1801a14f0  mov     rcx, [rbp+4Fh+var_98]
0x1801a14f4  call    cs:__imp_CreateRandomAccessStreamOverStream
0x1801a14fb  nop     dword ptr [rax+rax+00h]
0x1801a1500  mov     rcx, [rbp+57h]; this
0x1801a1504  test    eax, eax
0x1801a1506  js      loc_1801A1613
0x1801a150c  movd    xmm0, edi
0x1801a1510  cvtdq2ps xmm0, xmm0
0x1801a1513  movss   dword ptr [rsi], xmm0
0x1801a1517  movd    xmm1, r14d
0x1801a151c  cvtdq2ps xmm1, xmm1
0x1801a151f  movss   dword ptr [rsi+4], xmm1
0x1801a1524  mov     rcx, [rbp+4Fh+var_78]
0x1801a1528  mov     [rbx], r15
0x1801a152b  mov     rax, [rcx]
0x1801a152e  mov     r8, rbx
0x1801a1531  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1801a1538  mov     rax, [rax]
0x1801a153b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1540  mov     rcx, [rbp+57h]; this
0x1801a1544  test    eax, eax
0x1801a1546  js      short loc_1801A1595
0x1801a1548  lea     rcx, [rbp+4Fh+var_78]
0x1801a154c  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x1801a1551  nop
0x1801a1552  lea     rcx, [rbp+4Fh+var_98]
0x1801a1556  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x1801a155b  nop
0x1801a155c  lea     rcx, [rbp+4Fh+var_70]
0x1801a1560  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x1801a1565  nop
0x1801a1566  lea     rcx, [rbp+4Fh+ppv]
0x1801a156a  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x1801a156f  nop
0x1801a1570  lea     rcx, [rbp+4Fh+pbc]
0x1801a1574  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x1801a1579  mov     rax, rbx
0x1801a157c  movaps  xmm6, [rsp+0F0h+var_48+8]
0x1801a1584  add     rsp, 0C8h
0x1801a158b  pop     r15
0x1801a158d  pop     r14
0x1801a158f  pop     rdi
0x1801a1590  pop     rsi
0x1801a1591  pop     rbx
0x1801a1592  pop     rbp
0x1801a1593  retn
0x1801a1595  mov     r9d, eax; char *
0x1801a1598  lea     r8, aOnecoreInterna_15; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801a159f  mov     edx, 1CBEh; void *
0x1801a15a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a15aa  mov     r9d, eax; char *
0x1801a15ad  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a15b4  mov     edx, 3EEh; void *
0x1801a15b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a15bf  mov     r9d, eax; char *
0x1801a15c2  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a15c9  mov     edx, 3F8h; void *
0x1801a15ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a15d4  mov     r9d, eax; char *
0x1801a15d7  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a15de  mov     edx, 3FCh; void *
0x1801a15e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a15e9  mov     r9d, eax; char *
0x1801a15ec  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a15f3  mov     edx, 3FEh; void *
0x1801a15f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a15fe  mov     r9d, eax; char *
0x1801a1601  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1608  mov     edx, 40Bh; void *
0x1801a160d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a1613  mov     r9d, eax; char *
0x1801a1616  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a161d  mov     edx, 40Eh; void *
0x1801a1622  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
