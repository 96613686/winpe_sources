# CConfigManager::GetStringInternal(IRequestContext *,ConfigSetting,ulong,ulong,ushort *,ulong *,WSManConfigSource *)

- ea: `0x180043c10`
- end: `0x180045669`
- name: `?GetStringInternal@CConfigManager@@AEAAHPEAVIRequestContext@@W4ConfigSetting@@KKPEAGPEAKPEAW4WSManConfigSource@@@Z`
- size: `6745`
- prototype: `int __high(struct IRequestContext *, enum ConfigSetting, unsigned int, unsigned int, unsigned __int16 *, unsigned int *, enum WSManConfigSource *)`
- caller_count: `6`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024128`
- `0x1800438d0`
- `0x180043910`
- `0x18004697c`
- `0x18005eba0`
- `0x1800e7d50`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180010030`
- `0x18002c920`
- `0x1800418d0`
- `0x180041eb0`
- `0x1800436d0`
- `0x180043c10`
- `0x180046140`
- `0x180046200`
- `0x180047990`
- `0x18005f000`
- `0x1800621e0`
- `0x18006b200`
- `0x180077490`
- `0x1800eefe4`
- `0x1801004a0`
- `0x180103850`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x18011ff54`
- `0x18012352c`
- `0x180193af4`
- `0x180193bb8`
- `0x1801a2d30`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_scwprintf` at `0x18004496d`
- `msvcrt!_scwprintf` at `0x18004496d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800451d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045221`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800451d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800451e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004532d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800451e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004532d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045344`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x1800445b3`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x1800445b3`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x1800446ae`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x1800446ae`
- `miutils!RtlReleaseFastLockExclusive` at `0x18004465f`
- `miutils!RtlReleaseFastLockExclusive` at `0x18004465f`

## string_xrefs

- `0x180045647`: `onecore\admin\wmi\wmx\config\configregistry.cpp`
- `0x180043ea6`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x180044d97`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x1800450cd`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18004517b`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x180045289`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x180045319`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x180044e78`: `onecore\admin\wmi\wmx\config\configsetting.cpp`
- `0x180044359`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800449d7`: `StringCchCopyW`
- `0x180044a40`: `StringCchCopyW`
- `0x180044e22`: `StringCchCopyW`
- `0x1800447ac`: `onecore\admin\wmi\wmx\config\wsmangrouppolicysetting.cpp`
- `0x180044804`: `onecore\admin\wmi\wmx\config\wsmangrouppolicysetting.cpp`
- `0x1800448bb`: `onecore\admin\wmi\wmx\config\wsmangrouppolicysetting.cpp`
- `0x180045373`: `onecore\admin\wmi\wmx\config\wsmangrouppolicysetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CConfigManager::GetStringInternal(
        __int64 a1,
        struct IRequestContext *a2,
        unsigned int a3,
        int a4,
        DWORD a5,
        unsigned __int16 *a6,
        DWORD *a7,
        _DWORD *a8)
{
  struct IRequestContext *v10; // r11
  unsigned __int16 *v12; // rdi
  DWORD v13; // r14d
  DWORD *v14; // r12
  unsigned int v15; // edx
  __int16 *v16; // r8
  struct _CONFIG_INFO near **v17; // rsi
  int v18; // ecx
  __int64 i; // rdx
  const struct _WSMAN_POLICY_INFO near *const *v20; // rbx
  PVOID *v21; // rcx
  CWSManGroupPolicyManager *v22; // r14
  unsigned int v23; // ebx
  BOOL v24; // ebx
  PVOID *v25; // r9
  PVOID *v26; // r10
  struct _CONFIG_INFO near *v27; // rax
  __int64 v28; // rcx
  DWORD v29; // ecx
  const unsigned __int16 *v30; // r8
  __int64 v31; // rdx
  const unsigned __int16 *v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rcx
  unsigned __int16 v36; // dx
  unsigned __int16 *v37; // rax
  unsigned int v38; // eax
  DWORD PolicyValueForConfigSetting; // ebx
  __int64 v40; // rax
  unsigned int v41; // edx
  const struct _WSMAN_POLICY_INFO near *const *v42; // rbx
  struct CWSManGroupPolicyManager *v43; // r14
  unsigned int v44; // ebx
  BOOL v45; // ebx
  unsigned int v46; // edx
  const struct _WSMAN_POLICY_INFO near *const *v47; // rbx
  CWSManGroupPolicyManager *GroupPolicyManager; // rax
  _DWORD *v49; // rax
  unsigned int j; // edx
  const struct _WSMAN_POLICY_INFO near *const *v51; // rbx
  __int64 v52; // rbx
  struct CWSManGroupPolicyManager *v53; // rax
  __int64 v54; // rcx
  const unsigned __int16 *v55; // rbx
  __int64 v56; // rcx
  CWSManGroupPolicyManager *v57; // r14
  CWSManGroupPolicyManager *v58; // rax
  _QWORD *v59; // rcx
  __int64 v60; // r9
  __int64 v61; // rdx
  __int64 v62; // rcx
  const unsigned __int16 *v63; // rax
  unsigned __int16 v64; // r8
  unsigned __int16 *v65; // rax
  __int64 v66; // rax
  struct IRequestContext *v67; // rcx
  unsigned int *v68; // rsi
  int v69; // eax
  unsigned int v70; // ebx
  __int64 v71; // rdx
  __int64 v72; // rcx
  int v73; // eax
  unsigned int v74; // ebx
  _QWORD *v75; // rcx
  __int64 v76; // rcx
  int v77; // eax
  __int64 v78; // rcx
  int v79; // eax
  __int64 v80; // rax
  __int64 v81; // rcx
  int v82; // eax
  int v83; // eax
  struct IRequestContext *v84; // r11
  unsigned int v85; // ebx
  __int64 v86; // rdx
  const unsigned __int16 *v87; // r8
  __int64 v88; // rdx
  const unsigned __int16 *v89; // r8
  const unsigned __int16 *ComputerNameFQDN; // rbx
  unsigned __int16 *v91; // r8
  __int64 v92; // rcx
  int v93; // eax
  int v94; // eax
  DWORD LastError; // eax
  DWORD v96; // r14d
  PVOID *v97; // r10
  unsigned int v98; // ebx
  __int64 v99; // rdx
  const unsigned __int16 *v100; // r8
  __int64 v101; // rdx
  const unsigned __int16 *v102; // r8
  unsigned int v103; // [rsp+40h] [rbp-71h] BYREF
  unsigned int *v104; // [rsp+48h] [rbp-69h] BYREF
  unsigned __int16 *v105; // [rsp+50h] [rbp-61h] BYREF
  unsigned int v106; // [rsp+58h] [rbp-59h] BYREF
  void **v107; // [rsp+60h] [rbp-51h] BYREF
  signed __int32 v108[4]; // [rsp+68h] [rbp-49h] BYREF
  char v109; // [rsp+78h] [rbp-39h]
  const wchar_t *v110; // [rsp+80h] [rbp-31h]
  const wchar_t *v111; // [rsp+88h] [rbp-29h]
  const wchar_t *v112; // [rsp+90h] [rbp-21h]
  const wchar_t *v113; // [rsp+98h] [rbp-19h]
  CWSManGroupPolicyManager *v114; // [rsp+A0h] [rbp-11h]

  v10 = a2;
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 602, L"602", 0x54Fu, 0);
    return 0;
  }
  if ( !*(_DWORD *)(a1 + 11288) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 603, L"603", 0x54Fu, a2);
    return 0;
  }
  v12 = a6;
  v13 = a5;
  if ( a5 )
  {
    if ( !a6 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 605, L"605", 0x54Fu, a2);
      return 0;
    }
    v14 = a7;
    if ( !a7 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 606, L"606", 0x54Fu, a2);
      return 0;
    }
  }
  else
  {
    v14 = a7;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, a3);
    v10 = a2;
  }
  *v14 = 0;
  v15 = 0;
  v16 = _ImageBase;
  while ( 1 )
  {
    if ( v15 >= 0x45 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids);
      v101 = 661;
      v102 = L"661";
      goto LABEL_359;
    }
    v17 = &g_ConfigSettings + 6 * v15;
    v18 = *(_DWORD *)v17;
    if ( a3 == *(_DWORD *)v17 )
      break;
    ++v15;
  }
  if ( (a4 & *((_DWORD *)v17 + 5)) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids);
    v101 = 653;
    v102 = L"653";
LABEL_359:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", v101, v102, 0x54Fu, 0);
    v30 = L"616";
    v31 = 616;
    goto LABEL_44;
  }
  switch ( v18 )
  {
    case 3000:
      v52 = *(_QWORD *)(a1 + 11296);
      if ( !v52 || *(_DWORD *)(v52 + 8) != 1 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 620, L"620", 0x54Fu, v10);
        return 0;
      }
      v104 = 0;
      if ( !(unsigned int)ConvertListenerAddressTypeToPrefixString(v10, *(unsigned int *)(v52 + 16), &v104) )
        return 0;
      v68 = v104;
      *v14 = _scwprintf(L"%s%s", v104, *(_QWORD *)(v52 + 24)) + 1;
      if ( !a6 )
        goto LABEL_42;
      v69 = StringCchPrintfW(a6, a5, L"%s%s", v68, *(_QWORD *)(v52 + 24));
      v70 = v69;
      if ( v69 != -2147024774 )
      {
        if ( v69 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids,
              (unsigned int)v69);
          (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
            a2,
            1077134178,
            L"StringCchCopyW",
            v70);
          *v14 = 0;
          return 0;
        }
        goto LABEL_270;
      }
      v67 = a2;
      v66 = *(_QWORD *)a2;
      goto LABEL_189;
    case 6000:
      v16 = *(__int16 **)(a1 + 11296);
      if ( !v16 || *((_DWORD *)v16 + 2) != 2 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 672, L"672", 0x54Fu, v10);
        return 0;
      }
      v72 = -1;
      do
        ++v72;
      while ( *(_WORD *)(*((_QWORD *)v16 + 2) + 2 * v72) );
      *v14 = v72;
      if ( !a6 )
        goto LABEL_147;
      v73 = StringCchCopyW(a6, a5, *((const unsigned __int16 **)v16 + 2));
      v74 = v73;
      if ( v73 != -2147024774 )
      {
        if ( v73 >= 0 )
          goto LABEL_270;
        v75 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
          goto LABEL_201;
        v71 = 32;
        goto LABEL_200;
      }
      goto LABEL_188;
    case 6001:
      v16 = *(__int16 **)(a1 + 11296);
      if ( !v16 || *((_DWORD *)v16 + 2) != 2 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 712, L"712", 0x54Fu, v10);
        return 0;
      }
      v76 = -1;
      do
        ++v76;
      while ( *(_WORD *)(*((_QWORD *)v16 + 3) + 2 * v76) );
      *v14 = v76;
      if ( !a6 )
        goto LABEL_147;
      v77 = StringCchCopyW(a6, a5, *((const unsigned __int16 **)v16 + 3));
      v74 = v77;
      if ( v77 != -2147024774 )
      {
        if ( v77 >= 0 )
          goto LABEL_270;
        v75 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
          goto LABEL_201;
        v71 = 33;
        goto LABEL_200;
      }
      goto LABEL_188;
    case 6002:
      v16 = *(__int16 **)(a1 + 11296);
      if ( !v16 || *((_DWORD *)v16 + 2) != 2 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 753, L"753", 0x54Fu, v10);
        return 0;
      }
      v78 = -1;
      do
        ++v78;
      while ( *(_WORD *)(*((_QWORD *)v16 + 4) + 2 * v78) );
      *v14 = v78;
      if ( !a6 )
        goto LABEL_147;
      v79 = StringCchCopyW(a6, a5, *((const unsigned __int16 **)v16 + 4));
      v74 = v79;
      if ( v79 != -2147024774 )
      {
        if ( v79 >= 0 )
          goto LABEL_270;
        v75 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
          goto LABEL_201;
        v71 = 34;
        goto LABEL_200;
      }
      goto LABEL_188;
    case 6004:
      v80 = *(_QWORD *)(a1 + 11296);
      if ( !v80 || *(_DWORD *)(v80 + 8) != 2 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 797, L"797", 0x54Fu, v10);
        return 0;
      }
      *v14 = 1;
      if ( !a6 )
        goto LABEL_147;
      v61 = a5;
      if ( a5 )
      {
        if ( a5 <= 0x7FFFFFFFuLL )
        {
          v62 = 2147483646;
          v63 = L" ";
          do
          {
            if ( !v62 )
              break;
            v64 = *v63;
            if ( !*v63 )
              break;
            ++v63;
            *v12++ = v64;
            --v62;
            --v61;
          }
          while ( v61 );
          v65 = v12 - 1;
          if ( v61 )
            v65 = v12;
          *v65 = 0;
          if ( v61 )
            goto LABEL_270;
LABEL_188:
          v66 = *(_QWORD *)v10;
          v67 = v10;
LABEL_189:
          (*(void (__fastcall **)(struct IRequestContext *, __int64))(v66 + 72))(v67, 122);
LABEL_202:
          *v14 = 0;
          return 0;
        }
        v74 = -2147024809;
        *a6 = 0;
      }
      else
      {
        v74 = -2147024809;
      }
      v75 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
        goto LABEL_201;
      v71 = 35;
LABEL_200:
      WPP_SF_d(v75[2], v71, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, v74);
      v10 = a2;
LABEL_201:
      (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)v10 + 88LL))(
        v10,
        1077134178,
        L"StringCchCopyW",
        v74);
      goto LABEL_202;
    case 3015:
      v16 = *(__int16 **)(a1 + 11296);
      if ( !v16 || *((_DWORD *)v16 + 2) != 3 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 837, L"837", 0x54Fu, v10);
        return 0;
      }
      v81 = -1;
      do
        ++v81;
      while ( *(_WORD *)(*((_QWORD *)v16 + 2) + 2 * v81) );
      *v14 = v81;
      if ( !a6 )
        goto LABEL_147;
      v82 = StringCchCopyW(a6, a5, *((const unsigned __int16 **)v16 + 2));
      v74 = v82;
      if ( v82 != -2147024774 )
      {
        if ( v82 >= 0 )
          goto LABEL_270;
        v75 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
          goto LABEL_201;
        v71 = 36;
        goto LABEL_200;
      }
      goto LABEL_188;
    case 3001:
      v40 = *(_QWORD *)(a1 + 11296);
      if ( !v40 || *(_DWORD *)(v40 + 8) != 1 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 882, L"882", 0x54Fu, v10);
        return 0;
      }
      v54 = *(int *)(v40 + 32);
      if ( (_DWORD)v54 == -1 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 885, L"885", 0x54Fu, v10);
        return 0;
      }
      if ( (unsigned int)v54 > 1 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configsetting.cpp", 27, L"27", 0x54Fu, v10);
        return 0;
      }
      v55 = (const unsigned __int16 *)(&g_transport)[v54];
      if ( !v55 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 895, L"895", 0x54Fu, v10);
        v10 = a2;
      }
      v56 = -1;
      do
        ++v56;
      while ( v55[v56] );
      *a7 = v56 + 1;
      if ( !a6 )
      {
LABEL_147:
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int16 *))(*(_QWORD *)v10 + 72LL))(v10, 122, v16);
        return 0;
      }
      v83 = StringCchCopyW(a6, a5, v55);
      v85 = v83;
      if ( v83 == -2147024774 )
      {
        (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)v84 + 72LL))(v84, 122);
        *a7 = 0;
        return 0;
      }
      if ( v83 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids,
            (unsigned int)v83);
          v84 = a2;
        }
        (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)v84 + 88LL))(
          v84,
          1077134178,
          L"StringCchCopyW",
          v85);
        *a7 = 0;
        return 1359;
      }
LABEL_270:
      if ( a8 )
        *a8 = 2;
      return 1;
  }
  if ( (unsigned int)(v18 - 2018) <= 1 )
  {
    for ( i = 0; (unsigned int)i < 0x1B; i = (unsigned int)(i + 1) )
    {
      v20 = &g_GroupPolicySettings + 6 * (unsigned int)i;
      if ( *(_DWORD *)v20 == 1000 )
      {
        if ( ((_BYTE)v20[2] & 3) != 0 )
        {
          v21 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, 1000);
            v21 = (PVOID *)WPP_GLOBAL_Control;
            v10 = a2;
          }
          if ( ((_BYTE)v20[2] & 2) == 0 )
            goto LABEL_116;
          if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x200000) != 0 )
            WPP_SF_(v21[2], 16, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids);
          if ( CWSManGroupPolicyManager::s_policyManager )
          {
            (**(void (__fastcall ***)(CWSManGroupPolicyManager *, __int64, __int16 *))CWSManGroupPolicyManager::s_policyManager)(
              CWSManGroupPolicyManager::s_policyManager,
              i,
              v16);
            v22 = CWSManGroupPolicyManager::s_policyManager;
          }
          else
          {
            v105 = (unsigned __int16 *)&CWSManGroupPolicyManager::s_lock;
            if ( !(unsigned int)RtlTryAcquireFastLockExclusive(&CWSManGroupPolicyManager::s_lock) )
              RtlQueueAcquireFastLockExclusive(&CWSManGroupPolicyManager::s_lock);
            if ( CWSManGroupPolicyManager::s_policyManager )
            {
              (**(void (__fastcall ***)(CWSManGroupPolicyManager *))CWSManGroupPolicyManager::s_policyManager)(CWSManGroupPolicyManager::s_policyManager);
            }
            else
            {
              v57 = 0;
              v103 = 0;
              v104 = &v103;
              v58 = (CWSManGroupPolicyManager *)WSManMemory::Alloc(216, 0, 0);
              v114 = v58;
              if ( v58 )
                v57 = CWSManGroupPolicyManager::CWSManGroupPolicyManager(v58);
              v104 = (unsigned int *)v57;
              if ( v57 )
              {
                if ( CWSManGroupPolicyManager::Initialize(v57, a2, 0) )
                {
                  (**(void (__fastcall ***)(CWSManGroupPolicyManager *))v57)(v57);
                  v104 = 0;
                  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&CWSManGroupPolicyManager::s_policyManager);
                  CWSManGroupPolicyManager::s_policyManager = v57;
                }
                else
                {
                  LastError = GetLastError();
                  v96 = LastError;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      18,
                      WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
                      LastError);
                  }
                  SetLastError(v96);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids);
                (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
                SetLastError(0xEu);
              }
              AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v104);
            }
            v22 = CWSManGroupPolicyManager::s_policyManager;
            RtlReleaseFastLockExclusive(&CWSManGroupPolicyManager::s_lock);
          }
          v104 = (unsigned int *)v22;
          if ( !v22 )
            goto LABEL_310;
          v23 = *(_DWORD *)v20;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, v23);
          v103 = 0;
          if ( !(unsigned int)CWSManGroupPolicyManager::GetInt(v22, a2, v23, &v103, &v105) )
            goto LABEL_310;
          v24 = v103 != 0;
          AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v104);
          v13 = a5;
          if ( !v24 )
            goto LABEL_35;
          v103 = 0;
          if ( !a5 || a6 )
          {
            v26 = (PVOID *)WPP_GLOBAL_Control;
            v25 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
              {
                WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, a1);
                v26 = (PVOID *)WPP_GLOBAL_Control;
                v25 = &WPP_GLOBAL_Control;
              }
              if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x200000) != 0 )
              {
                WPP_SF_d(v26[2], 45, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, a3);
                v26 = (PVOID *)WPP_GLOBAL_Control;
                v25 = &WPP_GLOBAL_Control;
              }
            }
            v46 = 0;
            v16 = _ImageBase;
            while ( 1 )
            {
              if ( v46 >= 0x1B )
                goto LABEL_321;
              v47 = &g_GroupPolicySettings + 6 * v46;
              if ( a3 == *((_DWORD *)v47 + 1) )
                break;
              ++v46;
            }
            if ( ((_BYTE)v47[2] & 0x1E) == 0 )
            {
              WSManError(
                (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicysetting.cpp",
                347,
                L"347",
                0x54Fu,
                a2);
              v26 = (PVOID *)WPP_GLOBAL_Control;
              v25 = &WPP_GLOBAL_Control;
LABEL_321:
              if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x200000) != 0 )
              {
                WPP_SF_d(v26[2], 46, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, a3);
                goto LABEL_35;
              }
              goto LABEL_36;
            }
            if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x200000) != 0 )
              WPP_SF_d(v26[2], 47, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, a3);
            if ( ((_BYTE)v47[2] & 4) == 0 )
            {
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1304, L"1304", 0x54Fu, a2);
              PolicyValueForConfigSetting = 1359;
              goto LABEL_170;
            }
            GroupPolicyManager = CWSManGroupPolicyManager::GetGroupPolicyManager(a2, 0);
            v104 = (unsigned int *)GroupPolicyManager;
            if ( GroupPolicyManager
              && (unsigned int)CWSManGroupPolicyManager::GetStringInternal(
                                 GroupPolicyManager,
                                 a2,
                                 *(_DWORD *)v47,
                                 4,
                                 a5,
                                 (LPBYTE)a6,
                                 a7,
                                 &v103) )
            {
              AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v104);
            }
            else
            {
              PolicyValueForConfigSetting = GetLastError();
              AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v104);
              if ( PolicyValueForConfigSetting )
              {
                if ( PolicyValueForConfigSetting == 2 )
                  goto LABEL_35;
                goto LABEL_170;
              }
            }
            if ( !v103 )
              goto LABEL_35;
            v49 = a8;
            if ( !a8 )
              return 1;
            goto LABEL_114;
          }
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1281, L"1281", 0x54Fu, a2);
          PolicyValueForConfigSetting = 1359;
LABEL_170:
          if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
            return 0;
LABEL_171:
          (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(
            a2,
            PolicyValueForConfigSetting);
          return 0;
        }
        v99 = 307;
        v100 = L"307";
LABEL_172:
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicysetting.cpp", v99, v100, 0x54Fu, v10);
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        {
          v60 = 1000;
          goto LABEL_175;
        }
        return 0;
      }
    }
    v99 = 312;
    v100 = L"312";
    goto LABEL_172;
  }
  if ( v18 == 1107 )
  {
    v103 = 0;
    for ( j = 0; ; ++j )
    {
      if ( j >= 0x1B )
      {
        v86 = 312;
        v87 = L"312";
        goto LABEL_190;
      }
      v51 = &g_GroupPolicySettings + 6 * j;
      if ( *(_DWORD *)v51 == 1011 )
        break;
    }
    if ( ((_BYTE)v51[2] & 3) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, 1011);
        v10 = a2;
      }
      if ( ((_BYTE)v51[2] & 2) != 0 )
      {
        v53 = CWSManGroupPolicyManager::GetGroupPolicyManager(v10, 0);
        v104 = (unsigned int *)v53;
        if ( v53 )
        {
          if ( (unsigned int)CWSManGroupPolicyManager::GetBool(v53, a2, *(unsigned int *)v51, &v103, &v105) )
          {
            AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v104);
            if ( !v103 )
              goto LABEL_35;
            v103 = 0;
            PolicyValueForConfigSetting = CConfigManager::GetPolicyValueForConfigSetting(a1, a3, a5, a6, a7, &v103, a2);
            if ( PolicyValueForConfigSetting )
              goto LABEL_279;
LABEL_133:
            if ( !v103 )
              goto LABEL_35;
            v49 = a8;
            if ( a8 )
LABEL_114:
              *v49 = 1;
            return 1;
          }
LABEL_310:
          AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v104);
          return 0;
        }
LABEL_273:
        AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v104);
        return 0;
      }
LABEL_116:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 345, L"345", 0x54Fu, v10);
      goto LABEL_35;
    }
    v86 = 307;
    v87 = L"307";
LABEL_190:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicysetting.cpp", v86, v87, 0x54Fu, v10);
    v59 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      return 0;
    v60 = 1011;
LABEL_175:
    WPP_SF_d(v59[2], 22, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, v60);
    return 0;
  }
  if ( v18 != 2015 )
  {
    if ( v18 == 3006 )
    {
      if ( *(_DWORD *)(a1 + 11332) != 1 )
        goto LABEL_35;
      ComputerNameFQDN = GetComputerNameFQDN(v10);
      if ( !(*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
        return 0;
      v105 = 0;
      v108[0] = 0;
      v107 = &CErrorContext::`vftable';
      v108[2] = 0;
      v108[3] = -1;
      v110 = &Class;
      v111 = &Class;
      v112 = &Class;
      v113 = &Class;
      v109 = 1;
      _InterlockedIncrement(v108);
      if ( !(unsigned int)FindCertificate((struct IRequestContext *)&v107, (__int64)ComputerNameFQDN, &v105) )
      {
        v107 = &ILifeTimeMgmt::`vftable';
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v105);
        goto LABEL_35;
      }
      v91 = v105;
      v92 = -1;
      do
        ++v92;
      while ( v105[v92] );
      *a7 = v92 + 1;
      if ( !a6 )
      {
        (*(void (__fastcall **)(struct IRequestContext *, __int64, unsigned __int16 *))(*(_QWORD *)a2 + 72LL))(
          a2,
          122,
          v91);
        v107 = &ILifeTimeMgmt::`vftable';
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v105);
        return 0;
      }
      v93 = StringCchCopyW(a6, a5, v91);
      if ( v93 == -2147024774 )
      {
        (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 122);
        *a7 = 0;
        v107 = &ILifeTimeMgmt::`vftable';
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v105);
        return 0;
      }
      if ( v93 < 0 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1102, L"1102", 0x54Fu, a2);
        *a7 = 0;
        v107 = &ILifeTimeMgmt::`vftable';
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v105);
        return 0;
      }
      v107 = &ILifeTimeMgmt::`vftable';
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v105);
      return 1;
    }
    if ( v18 != 3003 || *(_DWORD *)(a1 + 11332) != 1 )
      goto LABEL_35;
    v33 = GetComputerNameFQDN(v10);
    if ( !(*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
      return 0;
    v34 = -1;
    do
      ++v34;
    while ( v33[v34] );
    *a7 = v34 + 1;
    if ( !a6 )
    {
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 122);
      return 0;
    }
    v94 = StringCchCopyW(a6, a5, v33);
    if ( v94 == -2147024774 )
    {
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 122);
      *a7 = 0;
      return 0;
    }
    if ( v94 < 0 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1137, L"1137", 0x54Fu, a2);
      *a7 = 0;
      return 0;
    }
    return 1;
  }
  v41 = 0;
  while ( 2 )
  {
    if ( v41 >= 0x1B )
    {
      v88 = 312;
      v89 = L"312";
LABEL_176:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicysetting.cpp", v88, v89, 0x54Fu, v10);
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
        return 0;
      v60 = 1018;
      goto LABEL_175;
    }
    v42 = &g_GroupPolicySettings + 6 * v41;
    if ( *(_DWORD *)v42 != 1018 )
    {
      ++v41;
      continue;
    }
    break;
  }
  if ( ((_BYTE)v42[2] & 3) == 0 )
  {
    v88 = 307;
    v89 = L"307";
    goto LABEL_176;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, 1018);
    v10 = a2;
  }
  if ( ((_BYTE)v42[2] & 2) == 0 )
    goto LABEL_116;
  v43 = CWSManGroupPolicyManager::GetGroupPolicyManager(v10, 0);
  v104 = (unsigned int *)v43;
  if ( !v43 )
    goto LABEL_273;
  v44 = *(_DWORD *)v42;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, v44);
  v103 = 0;
  if ( !(unsigned int)CWSManGroupPolicyManager::GetInt(v43, a2, v44, &v103, &v105) )
    goto LABEL_310;
  v45 = v103 != 0;
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v104);
  if ( !v45 )
  {
    v13 = a5;
    goto LABEL_35;
  }
  v103 = 0;
  v13 = a5;
  PolicyValueForConfigSetting = CConfigManager::GetPolicyValueForConfigSetting(a1, a3, a5, a6, a7, &v103, a2);
  if ( !PolicyValueForConfigSetting )
    goto LABEL_133;
LABEL_279:
  if ( PolicyValueForConfigSetting != 2 )
  {
    if ( !(*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
      goto LABEL_171;
    return 0;
  }
LABEL_35:
  v25 = &WPP_GLOBAL_Control;
  v26 = (PVOID *)WPP_GLOBAL_Control;
LABEL_36:
  v106 = 0;
  v103 = 0;
  if ( *(_DWORD *)(a1 + 11324) == 1 || *(_DWORD *)(a1 + 11328) == 1 || *(_DWORD *)(a1 + 11332) == 1 )
    goto LABEL_37;
  if ( (*(unsigned int (__fastcall **)(struct IRequestContext *, _QWORD, __int16 *, PVOID *))(*(_QWORD *)a2 + 192LL))(
         a2,
         0,
         v16,
         &WPP_GLOBAL_Control) )
  {
    goto LABEL_78;
  }
  v38 = CConfigManager::QueryRegValue(
          (CConfigManager *)a1,
          (struct _CONFIG_INFO *)v17,
          &v106,
          2 * v13,
          (unsigned __int8 *)a6,
          &v103);
  PolicyValueForConfigSetting = v38;
  if ( !v38 )
  {
    if ( v106 != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_dSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids,
          a3,
          (__int64)v17[1],
          v106);
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 2150858757LL);
      *a7 = 0;
      return 0;
    }
    v97 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v17[1], (__int64)a6);
      v97 = (PVOID *)WPP_GLOBAL_Control;
    }
    v98 = v103;
    if ( v103 >= 2 && *((_BYTE *)a6 + v103 - 1) && *((_BYTE *)a6 + v103 - 2) )
    {
      if ( v97 != &WPP_GLOBAL_Control && (*((_DWORD *)v97 + 7) & 0x400000) != 0 )
        WPP_SF_(v97[2], 39, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 122);
      *a7 = (v98 >> 1) + 1;
      return 0;
    }
    if ( !(unsigned int)ConfigRegistry::ValidateString((ConfigRegistry *)(a1 + 16), a2, (struct _CONFIG_INFO *)v17, a6) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v17[1], (__int64)a6);
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 2150858757LL);
      return 0;
    }
    *a7 = v98 >> 1;
    if ( a8 )
      *a8 = 2;
    return 1;
  }
  if ( v38 == 122 )
  {
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 122);
    *a7 = v103 >> 1;
    return 0;
  }
  if ( v38 != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, v38);
    goto LABEL_171;
  }
LABEL_78:
  v26 = (PVOID *)WPP_GLOBAL_Control;
  v25 = &WPP_GLOBAL_Control;
LABEL_37:
  if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x200000) != 0 )
    WPP_SF_SdS(
      (unsigned int)v26[2],
      42,
      (unsigned int)WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids,
      (unsigned int)v17[5],
      a3,
      (__int64)v17[1]);
  v27 = v17[5];
  v28 = -1;
  do
    ++v28;
  while ( *((_WORD *)v27 + v28) );
  if ( (unsigned int)v28 >= 0x2800 )
  {
    v30 = L"1227";
    v31 = 1227;
LABEL_44:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", v31, v30, 0x54Fu, a2);
    return 0;
  }
  v29 = v28 + 1;
  *a7 = v29;
  if ( v13 < v29 )
  {
LABEL_42:
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int16 *, PVOID *))(*(_QWORD *)a2 + 72LL))(
      a2,
      122,
      v16,
      v25);
    return 0;
  }
  v16 = (__int16 *)v13;
  if ( !v13 )
  {
LABEL_348:
    v30 = L"1245";
    v31 = 1245;
    goto LABEL_44;
  }
  if ( v13 > 0x7FFFFFFFuLL )
  {
    *a6 = 0;
    goto LABEL_348;
  }
  v35 = 2147483646;
  do
  {
    if ( !v35 )
      break;
    v36 = *(_WORD *)v27;
    if ( !*(_WORD *)v27 )
      break;
    v27 = (struct _CONFIG_INFO near *)((char *)v27 + 2);
    *v12++ = v36;
    --v35;
    v16 = (__int16 *)((char *)v16 - 1);
  }
  while ( v16 );
  v37 = v12 - 1;
  if ( v16 )
    v37 = v12;
  *v37 = 0;
  if ( !v16 )
    goto LABEL_42;
  if ( a8 )
    *a8 = 3;
  return 1;
}

```

## disassembly

```asm
0x180043c10  mov     [rsp-8+arg_8], rdx
0x180043c15  push    rbp
0x180043c16  push    rbx
0x180043c17  push    rsi
0x180043c18  push    rdi
0x180043c19  push    r12
0x180043c1b  push    r13
0x180043c1d  push    r14
0x180043c1f  push    r15
0x180043c21  lea     rbp, [rsp-7]
0x180043c26  sub     rsp, 0B8h
0x180043c2d  mov     ebx, r9d
0x180043c30  mov     r15d, r8d
0x180043c33  mov     r11, rdx
0x180043c36  mov     r13, rcx
0x180043c39  test    rdx, rdx
0x180043c3c  jz      loc_1800444C5
0x180043c42  cmp     dword ptr [rcx+2C18h], 0
0x180043c49  jz      loc_1800448FE
0x180043c4f  mov     rdi, [rbp+3Fh+arg_28]
0x180043c53  mov     r14d, dword ptr [rbp+3Fh+arg_20]
0x180043c57  test    r14d, r14d
0x180043c5a  jnz     loc_18004439A
0x180043c60  mov     r12, [rbp+3Fh+arg_30]
0x180043c64  lea     r9, WPP_GLOBAL_Control
0x180043c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c72  cmp     rcx, r9
0x180043c75  jnz     loc_180044103
0x180043c7b  xor     r10d, r10d
0x180043c7e  mov     [r12], r10d
0x180043c82  mov     edx, r10d
0x180043c85  lea     r8, __ImageBase
0x180043c8c  nop     dword ptr [rax+00h]
0x180043c90  cmp     edx, 45h ; 'E'
0x180043c93  jnb     loc_1800455FA
0x180043c99  mov     eax, edx
0x180043c9b  lea     rcx, [rax+rax*2]
0x180043c9f  shl     rcx, 4
0x180043ca3  lea     rsi, rva ?g_ConfigSettings@@3PAU_CONFIG_INFO@@A[r8]; _CONFIG_INFO near * g_ConfigSettings ...
0x180043caa  add     rsi, rcx
0x180043cad  mov     ecx, [rsi]
0x180043caf  cmp     r15d, ecx
0x180043cb2  jz      short loc_180043CB8
0x180043cb4  inc     edx
0x180043cb6  jmp     short loc_180043C90
0x180043cb8  test    [rsi+14h], ebx
0x180043cbb  jz      loc_1800455B8
0x180043cc1  cmp     ecx, 0BB8h
0x180043cc7  jz      loc_1800443CC
0x180043ccd  cmp     ecx, 1770h
0x180043cd3  jz      loc_180044A60
0x180043cd9  cmp     ecx, 1771h
0x180043cdf  jz      loc_180044AFE
0x180043ce5  cmp     ecx, 1772h
0x180043ceb  jz      loc_180044BA1
0x180043cf1  cmp     ecx, 1774h
0x180043cf7  jz      loc_180044C44
0x180043cfd  cmp     ecx, 0BC7h
0x180043d03  jz      loc_180044CC4
0x180043d09  cmp     ecx, 0BB9h
0x180043d0f  jz      loc_180044147
0x180043d15  lea     eax, [rcx-7E2h]
0x180043d1b  mov     r12d, 54Fh
0x180043d21  cmp     eax, 1
0x180043d24  ja      loc_180043F02
0x180043d2a  mov     edx, r10d
0x180043d2d  nop     dword ptr [rax]
0x180043d30  cmp     edx, 1Bh
0x180043d33  jnb     loc_1800455A7
0x180043d39  mov     eax, edx
0x180043d3b  lea     rcx, [rax+rax*2]
0x180043d3f  shl     rcx, 4
0x180043d43  lea     rbx, rva ?g_GroupPolicySettings@@3QBU_WSMAN_POLICY_INFO@@B[r8]; _WSMAN_POLICY_INFO const near * const g_GroupPolicySettings ...
0x180043d4a  add     rbx, rcx
0x180043d4d  cmp     dword ptr [rbx], 3E8h
0x180043d53  jz      short loc_180043D59
0x180043d55  inc     edx
0x180043d57  jmp     short loc_180043D30
0x180043d59  test    byte ptr [rbx+10h], 3
0x180043d5d  jz      loc_180045596
0x180043d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180043d6a  cmp     rcx, r9
0x180043d6d  jnz     loc_1800440C4
0x180043d73  test    byte ptr [rbx+10h], 2
0x180043d77  jz      loc_180044345
0x180043d7d  cmp     rcx, r9
0x180043d80  jnz     loc_18004401A
0x180043d86  mov     rcx, cs:?s_policyManager@CWSManGroupPolicyManager@@0V?$AutoRelease@VCWSManGroupPolicyManager@@@@A; AutoRelease<CWSManGroupPolicyManager> CWSManGroupPolicyManager::s_policyManager
0x180043d8d  test    rcx, rcx
0x180043d90  jz      loc_1800445A5
0x180043d96  mov     rax, [rcx]
0x180043d99  mov     rax, [rax]
0x180043d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043da1  mov     r14, cs:?s_policyManager@CWSManGroupPolicyManager@@0V?$AutoRelease@VCWSManGroupPolicyManager@@@@A; AutoRelease<CWSManGroupPolicyManager> CWSManGroupPolicyManager::s_policyManager
0x180043da8  mov     [rbp+3Fh+var_A8], r14
0x180043dac  test    r14, r14
0x180043daf  jz      loc_18004523C
0x180043db5  mov     ebx, [rbx]
0x180043db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180043dbe  lea     rax, WPP_GLOBAL_Control
0x180043dc5  cmp     rcx, rax
0x180043dc8  jz      short loc_180043DD7
0x180043dca  test    dword ptr [rcx+1Ch], 200000h
0x180043dd1  jnz     loc_18004524B
0x180043dd7  mov     [rbp+3Fh+var_B0], 0
0x180043dde  lea     rax, [rbp+3Fh+var_A0]
0x180043de2  mov     [rsp+0F0h+var_D0], rax
0x180043de7  lea     r9, [rbp+3Fh+var_B0]
0x180043deb  mov     r8d, ebx
0x180043dee  mov     rdx, [rbp+3Fh+arg_8]
0x180043df2  mov     rcx, r14
0x180043df5  call    ?GetInt@CWSManGroupPolicyManager@@QEAAHPEAVIRequestContext@@W4WSManGroupPolicySetting@@PEAKPEAW4WSManGroupPolicySettingState@@@Z; CWSManGroupPolicyManager::GetInt(IRequestContext *,WSManGroupPolicySetting,ulong *,WSManGroupPolicySettingState *)
0x180043dfa  test    eax, eax
0x180043dfc  jz      loc_180044138
0x180043e02  xor     ebx, ebx
0x180043e04  cmp     [rbp+3Fh+var_B0], ebx
0x180043e07  setnz   bl
0x180043e0a  lea     rcx, [rbp+3Fh+var_A8]
0x180043e0e  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x180043e13  nop
0x180043e14  mov     r14d, dword ptr [rbp+3Fh+arg_20]
0x180043e18  test    ebx, ebx
0x180043e1a  jnz     loc_18004424F
0x180043e20  lea     r9, WPP_GLOBAL_Control
0x180043e27  mov     r10, cs:WPP_GLOBAL_Control
0x180043e2e  xor     edx, edx
0x180043e30  mov     [rbp+3Fh+var_98], edx
0x180043e33  mov     [rbp+3Fh+var_B0], edx
0x180043e36  cmp     dword ptr [r13+2C3Ch], 1
0x180043e3e  jnz     loc_180044041
0x180043e44  cmp     r10, r9
0x180043e47  jnz     short loc_180043EC8
0x180043e49  mov     rax, [rsi+28h]
0x180043e4d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180043e54  inc     rcx
0x180043e57  cmp     word ptr [rax+rcx*2], 0
0x180043e5c  jnz     short loc_180043E54
0x180043e5e  cmp     ecx, 2800h
0x180043e64  jnb     short loc_180043E8E
0x180043e66  inc     ecx
0x180043e68  mov     rdx, [rbp+3Fh+arg_30]
0x180043e6c  mov     [rdx], ecx
0x180043e6e  cmp     r14d, ecx
0x180043e71  jnb     loc_180043FA6
0x180043e77  mov     rcx, [rbp+3Fh+arg_8]
0x180043e7b  mov     rax, [rcx]
0x180043e7e  mov     edx, 7Ah ; 'z'
0x180043e83  mov     rax, [rax+48h]
0x180043e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e8c  jmp     short loc_180043EB2
0x180043e8e  lea     r8, a1227; "1227"
0x180043e95  mov     edx, 4CBh; unsigned int
0x180043e9a  mov     rax, [rbp+3Fh+arg_8]
0x180043e9e  mov     [rsp+0F0h+var_D0], rax; struct IRequestContext *
0x180043ea3  mov     r9d, r12d; unsigned int
0x180043ea6  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x180043ead  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180043eb2  xor     eax, eax
0x180043eb4  add     rsp, 0B8h
0x180043ebb  pop     r15
0x180043ebd  pop     r14
0x180043ebf  pop     r13
0x180043ec1  pop     r12
0x180043ec3  pop     rdi
0x180043ec4  pop     rsi
0x180043ec5  pop     rbx
0x180043ec6  pop     rbp
0x180043ec7  retn
0x180043ec8  test    dword ptr [r10+1Ch], 200000h
0x180043ed0  jz      loc_180043E49
0x180043ed6  mov     edx, 2Ah ; '*'
0x180043edb  mov     rax, [rsi+8]
0x180043edf  mov     [rsp+0F0h+var_C8], rax
0x180043ee4  mov     dword ptr [rsp+0F0h+var_D0], r15d
0x180043ee9  mov     r9, [rsi+28h]
0x180043eed  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x180043ef4  mov     rcx, [r10+10h]
0x180043ef8  call    WPP_SF_SdS
0x180043efd  jmp     loc_180043E49
0x180043f02  cmp     ecx, 453h
0x180043f08  jz      loc_18004436A
0x180043f0e  cmp     ecx, 7DFh
0x180043f14  jz      loc_180044173
0x180043f1a  cmp     ecx, 0BBEh
0x180043f20  jz      loc_180044F8D
0x180043f26  cmp     ecx, 0BBBh
0x180043f2c  jnz     loc_180043E20
0x180043f32  cmp     dword ptr [r13+2C44h], 1
0x180043f3a  jnz     loc_180043E20
0x180043f40  mov     rcx, r11; struct IRequestContext *
0x180043f43  call    ?GetComputerNameFQDN@@YAPEBGAEAVIRequestContext@@@Z; GetComputerNameFQDN(IRequestContext &)
0x180043f48  mov     rbx, rax
0x180043f4b  mov     r15, [rbp+3Fh+arg_8]
0x180043f4f  mov     rcx, [r15]
0x180043f52  mov     rax, [rcx+90h]
0x180043f59  mov     rcx, r15
0x180043f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f61  test    eax, eax
0x180043f63  jz      loc_180043EB2
0x180043f69  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180043f70  lea     rcx, [rcx+1]
0x180043f74  cmp     word ptr [rbx+rcx*2], 0
0x180043f79  jnz     short loc_180043F70
0x180043f7b  lea     eax, [rcx+1]
0x180043f7e  mov     rsi, [rbp+3Fh+arg_30]
0x180043f82  mov     [rsi], eax
0x180043f84  test    rdi, rdi
0x180043f87  jnz     loc_18004512D
0x180043f8d  mov     rax, [r15]
0x180043f90  mov     edx, 7Ah ; 'z'
0x180043f95  mov     rcx, r15
0x180043f98  mov     rax, [rax+48h]
0x180043f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fa1  jmp     loc_180043EB2
0x180043fa6  mov     r8d, r14d
0x180043fa9  test    r14d, r14d
0x180043fac  jz      loc_180045585
0x180043fb2  cmp     r8, 7FFFFFFFh
0x180043fb9  ja      loc_180045580
0x180043fbf  mov     ecx, 7FFFFFFEh
0x180043fc4  test    rcx, rcx
0x180043fc7  jz      short loc_180043FE5
0x180043fc9  movzx   edx, word ptr [rax]
0x180043fcc  test    dx, dx
0x180043fcf  jz      short loc_180043FE5
0x180043fd1  add     rax, 2
0x180043fd5  mov     [rdi], dx
0x180043fd8  add     rdi, 2
0x180043fdc  dec     rcx
0x180043fdf  sub     r8, 1
0x180043fe3  jnz     short loc_180043FC4
0x180043fe5  lea     rax, [rdi-2]
0x180043fe9  test    r8, r8
0x180043fec  cmovnz  rax, rdi
0x180043ff0  xor     ecx, ecx
0x180043ff2  mov     [rax], cx
0x180043ff5  test    r8, r8
0x180043ff8  jz      loc_180043E77
0x180043ffe  mov     rax, [rbp+3Fh+arg_38]
0x180044005  test    rax, rax
0x180044008  jz      short loc_180044010
0x18004400a  mov     dword ptr [rax], 3
0x180044010  mov     eax, 1
0x180044015  jmp     loc_180043EB4
0x18004401a  test    dword ptr [rcx+1Ch], 200000h
0x180044021  jz      loc_180043D86
0x180044027  mov     edx, 10h
0x18004402c  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x180044033  mov     rcx, [rcx+10h]
0x180044037  call    WPP_SF_
0x18004403c  jmp     loc_180043D86
0x180044041  cmp     dword ptr [r13+2C40h], 1
0x180044049  jz      loc_180043E44
0x18004404f  cmp     dword ptr [r13+2C44h], 1
0x180044057  jz      loc_180043E44
0x18004405d  mov     rcx, [rbp+3Fh+arg_8]
0x180044061  mov     rax, [rcx]
0x180044064  mov     rax, [rax+0C0h]
0x18004406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044070  test    eax, eax
0x180044072  jnz     short loc_1800440B1
0x180044074  lea     r9d, [r14+r14]; unsigned int
0x180044078  lea     rax, [rbp+3Fh+var_B0]
0x18004407c  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x180044081  mov     [rsp+0F0h+var_D0], rdi; unsigned __int8 *
0x180044086  lea     r8, [rbp+3Fh+var_98]; unsigned int *
0x18004408a  mov     rdx, rsi; struct _CONFIG_INFO *
0x18004408d  mov     rcx, r13; this
0x180044090  call    ?QueryRegValue@CConfigManager@@AEAAJPEAU_CONFIG_INFO@@PEAKKPEAE1@Z; CConfigManager::QueryRegValue(_CONFIG_INFO *,ulong *,ulong,uchar *,ulong *)
0x180044095  mov     ebx, eax
0x180044097  test    eax, eax
0x180044099  jz      loc_1800446B9
0x18004409f  cmp     eax, 7Ah ; 'z'
0x1800440a2  jz      loc_1800446FE
0x1800440a8  cmp     eax, 2
0x1800440ab  jnz     loc_180045535
0x1800440b1  mov     r10, cs:WPP_GLOBAL_Control
0x1800440b8  lea     r9, WPP_GLOBAL_Control
0x1800440bf  jmp     loc_180043E44
0x1800440c4  test    dword ptr [rcx+1Ch], 200000h
0x1800440cb  jz      loc_180043D73
0x1800440d1  mov     edx, 17h
0x1800440d6  mov     r9d, 3E8h
0x1800440dc  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800440e3  mov     rcx, [rcx+10h]
0x1800440e7  call    WPP_SF_d
0x1800440ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800440f3  mov     r11, [rbp+3Fh+arg_8]
0x1800440f7  lea     r9, WPP_GLOBAL_Control
0x1800440fe  jmp     loc_180043D73
0x180044103  test    dword ptr [rcx+1Ch], 200000h
0x18004410a  jz      loc_180043C7B
0x180044110  mov     edx, 1Eh
0x180044115  mov     r9d, r15d
0x180044118  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18004411f  mov     rcx, [rcx+10h]
0x180044123  call    WPP_SF_d
0x180044128  mov     r11, [rbp+3Fh+arg_8]
0x18004412c  lea     r9, WPP_GLOBAL_Control
0x180044133  jmp     loc_180043C7B
  ... truncated ...
```
