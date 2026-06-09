# Catalog::InitHostPluginXml(IRequestContext *)

- ea: `0x18003f8c8`
- end: `0x1800405c3`
- name: `?InitHostPluginXml@Catalog@@AEAAHPEAVIRequestContext@@@Z`
- size: `3323`
- prototype: `__int64 __fastcall(Catalog *this, struct IRequestContext *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003eae0`
- `0x18012eb10`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180010030`
- `0x180013760`
- `0x180022c00`
- `0x1800232f0`
- `0x18003f8c8`
- `0x1800405d0`
- `0x180041270`
- `0x180048db0`
- `0x18004a900`
- `0x18005d800`
- `0x1800621e0`
- `0x1800c8c68`
- `0x1800d42a8`
- `0x1800e5510`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x18011a6d4`
- `0x1801ba152`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003f9bf`
- `msvcrt!_wcsicmp` at `0x18003f9e0`
- `msvcrt!_wcsicmp` at `0x18003fa01`
- `msvcrt!_wcsicmp` at `0x18003f9bf`
- `msvcrt!_wcsicmp` at `0x18003f9e0`
- `msvcrt!_wcsicmp` at `0x18003fa01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fbbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003faff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fbbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fed6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fb74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fea3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fb74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fea3`

## string_xrefs

- `0x18003f9f7`: `SEL Plugin`
- `0x18003f9d6`: `Event Forwarding Plugin`
- `0x180040374`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180040536`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004056c`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18003fc98`: `<OperationsConfiguration>`
- `0x18003fd6b`: `</OperationsConfiguration>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Catalog::InitHostPluginXml(Catalog *this, struct IRequestContext *a2)
{
  __int64 FirstConfigManagerForTable; // rbx
  int v4; // r12d
  unsigned int v5; // r13d
  unsigned int v6; // esi
  void **v7; // rax
  wchar_t *v8; // r15
  int ConfigXml; // eax
  Catalog *v10; // rcx
  XmlReader *v11; // r14
  WCHAR *v12; // r12
  unsigned int v13; // ecx
  DWORD v14; // eax
  __int64 v15; // r14
  _QWORD *v16; // rbx
  CHeap *v17; // rcx
  CHeap *v18; // rcx
  void *Handle; // rax
  void *v21; // rcx
  __int64 v22; // rbx
  unsigned __int64 v23; // r14
  unsigned __int64 v24; // rbx
  __int64 v25; // rax
  wchar_t *v26; // rax
  wchar_t *v27; // r15
  __int64 v28; // r12
  __int64 v29; // rax
  const wchar_t *v30; // rcx
  wchar_t *v31; // rdx
  wchar_t v32; // r8
  unsigned int v33; // r9d
  wchar_t *v34; // rcx
  __int64 v35; // rdx
  wchar_t *v36; // rbx
  unsigned int v37; // r13d
  __int64 v38; // rdx
  const wchar_t *v39; // rax
  wchar_t v40; // cx
  unsigned int v41; // r9d
  wchar_t *v42; // rcx
  __int16 *v43; // rcx
  __int64 v44; // r9
  wchar_t *v45; // rax
  _WORD *v46; // r15
  wchar_t v47; // r8
  wchar_t *v48; // rcx
  unsigned int v49; // r9d
  __int64 v50; // rax
  DWORD LastError; // eax
  DWORD v52; // ebx
  unsigned int v53; // eax
  unsigned int v54; // r15d
  _QWORD *v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // rdx
  unsigned int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // rdx
  unsigned int v61; // eax
  const unsigned __int16 *v62; // r8
  unsigned int v63; // edx
  unsigned __int16 *v64; // [rsp+30h] [rbp-50h] BYREF
  __int64 v65; // [rsp+38h] [rbp-48h] BYREF
  XmlReader *v66; // [rsp+40h] [rbp-40h] BYREF
  WCHAR *v67; // [rsp+48h] [rbp-38h] BYREF
  __int64 v68; // [rsp+50h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-28h]
  void **v70; // [rsp+60h] [rbp-20h] BYREF
  int v71; // [rsp+68h] [rbp-18h]
  wchar_t *String1; // [rsp+70h] [rbp-10h]
  int v73; // [rsp+78h] [rbp-8h]
  wchar_t *v75; // [rsp+D0h] [rbp+50h] BYREF
  wchar_t *v76; // [rsp+D8h] [rbp+58h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
  FirstConfigManagerForTable = CConfigManager::GetFirstConfigManagerForTable(4, 0);
  v65 = FirstConfigManagerForTable;
  if ( !FirstConfigManagerForTable )
  {
    LastError = GetLastError();
    v52 = LastError;
    if ( LastError == 259 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
    }
    else
    {
      if ( LastError != -2144108539 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, LastError);
        (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v52);
        AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v65);
        return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
    }
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v65);
    return 1;
  }
  v4 = 0;
  LODWORD(v76) = 0;
  v5 = 0;
  v68 = 0;
  lpMem = 0;
  v6 = 1;
LABEL_4:
  v7 = &PLUGIN_IDENTITY::`vftable';
  while ( 1 )
  {
    v70 = &PLUGIN_IDENTITY::`vftable';
    String1 = 0;
    v73 = 0;
    v71 = 4;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids,
        FirstConfigManagerForTable);
      v7 = v70;
    }
    if ( !*(_DWORD *)(FirstConfigManagerForTable + 11288) )
    {
      v62 = L"2250";
      v63 = 2250;
LABEL_163:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", v63, v62, 0x54Fu, 0);
LABEL_164:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\catalog\\catalog.cpp", 0xD8Eu, L"3470", 0x54Fu, a2);
      PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v70);
      WSManMemory::Free(lpMem, 0);
      AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v65);
      return 0;
    }
    if ( !*(_QWORD *)(FirstConfigManagerForTable + 11296) )
    {
      v62 = L"2251";
      v63 = 2251;
      goto LABEL_163;
    }
    if ( !((unsigned int (__fastcall *)(void ***))v7[2])(&v70) )
      goto LABEL_164;
    v8 = String1;
    if ( !String1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
    if ( _wcsicmp(v8, L"WMI Provider") )
    {
      if ( !v8 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
      if ( _wcsicmp(v8, L"Event Forwarding Plugin") )
      {
        if ( !v8 )
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
        if ( _wcsicmp(v8, L"SEL Plugin") )
        {
          v66 = 0;
          v64 = 0;
          ConfigXml = CConfigManager::GetConfigXml(
                        (CConfigManager *)FirstConfigManagerForTable,
                        a2,
                        (const unsigned __int16 **)&v64,
                        &v66,
                        0);
          v11 = v66;
          if ( ConfigXml )
          {
            LODWORD(v75) = 0;
            v12 = Catalog::ResolveConfigXml(v10, v64, v66, (unsigned int *)&v75);
            v67 = v12;
            if ( !v12 )
            {
              v6 = 0;
              v22 = GetLastError();
              (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v22);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  90,
                  &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids,
                  (unsigned int)v22);
              AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v67);
              AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
              if ( v11 )
              {
                XmlReader::~XmlReader(v11);
                WSManMemory::Free(v11, 0);
              }
              goto LABEL_46;
            }
            v13 = HIDWORD(v68);
            if ( v5 <= HIDWORD(v68) )
            {
              v53 = SimpleStack<CListenerOperation>::SetSize(&v68, (unsigned int)(HIDWORD(v68) + 5));
              v54 = v53;
              if ( v53 )
              {
                v6 = 0;
                (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v53);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    91,
                    &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids,
                    v54);
                AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v67);
                AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
                AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v66);
                PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v70);
                goto LABEL_33;
              }
              v5 = v68;
              v13 = HIDWORD(v68);
            }
            *((_QWORD *)lpMem + v13) = v12;
            HIDWORD(v68) = v13 + 1;
            v67 = 0;
            v4 = (_DWORD)v75 + (_DWORD)v76;
            LODWORD(v76) = (_DWORD)v75 + (_DWORD)v76;
            AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v67);
          }
          else
          {
            if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2) == 14 )
            {
              v6 = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
              AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
              AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v66);
LABEL_46:
              PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v70);
LABEL_33:
              LODWORD(v15) = HIDWORD(v68);
              goto LABEL_34;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v8);
            (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 200LL))(a2, 1);
          }
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v64);
          if ( v11 )
          {
            XmlReader::~XmlReader(v11);
            WSManMemory::Free(v11, 0);
          }
        }
      }
    }
    if ( !(unsigned int)CConfigManager::NextRow((CConfigManager *)FirstConfigManagerForTable) )
      break;
    v7 = &PLUGIN_IDENTITY::`vftable';
    v70 = &PLUGIN_IDENTITY::`vftable';
    if ( v73 )
    {
      WSManMemory::Free(String1, 0);
      goto LABEL_4;
    }
  }
  v14 = GetLastError();
  if ( v14 != 259 )
  {
    v6 = 0;
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v14);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
    goto LABEL_46;
  }
  v70 = &PLUGIN_IDENTITY::`vftable';
  if ( v73 )
    WSManMemory::Free(String1, 0);
  if ( !v4 )
    goto LABEL_33;
  v23 = (unsigned int)(v4 + 52);
  v24 = v23;
  v25 = 2 * v23;
  if ( !is_mul_ok(v23, 2u) )
    v25 = -1;
  v26 = (wchar_t *)WSManMemory::Alloc(v25, 0, 0);
  v27 = v26;
  v76 = v26;
  v75 = v26;
  if ( !v26 )
  {
    v6 = 0;
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
LABEL_62:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v75);
    goto LABEL_33;
  }
  memset_0(v26, 0, 2 * v23);
  if ( v4 == -52 )
  {
    v33 = -2147024809;
    goto LABEL_59;
  }
  if ( v23 > 0x7FFFFFFF )
  {
    v33 = -2147024809;
    *v27 = 0;
    goto LABEL_59;
  }
  v28 = 2147483646;
  v29 = 2147483646;
  v30 = L"<OperationsConfiguration>";
  v31 = v27;
  do
  {
    if ( !v29 )
      break;
    v32 = *v30;
    if ( !*v30 )
      break;
    ++v30;
    *v31++ = v32;
    --v29;
    --v24;
  }
  while ( v24 );
  v33 = v24 == 0 ? 0x8007007A : 0;
  v34 = v31 - 1;
  if ( v24 )
    v34 = v31;
  *v34 = 0;
  if ( !v24 )
  {
LABEL_59:
    v6 = 0;
    v35 = (unsigned __int16)v33;
    if ( (v33 & 0x1FFF0000) != 0x70000 )
      v35 = v33;
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v35);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v61 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v61);
    }
    goto LABEL_62;
  }
  v36 = v27 + 25;
  v37 = v23 - 25;
  while ( 1 )
  {
    LODWORD(v15) = HIDWORD(v68);
    v38 = v37;
    if ( !HIDWORD(v68) )
      break;
    LODWORD(v15) = --HIDWORD(v68);
    v43 = (__int16 *)*((_QWORD *)lpMem + HIDWORD(v68));
    if ( !v43 )
      break;
    if ( v37 - 1 > 0x7FFFFFFE )
    {
      v49 = -2147024809;
      if ( v37 )
        *v36 = 0;
LABEL_142:
      v6 = 0;
      v57 = (unsigned __int16)v49;
      if ( (v49 & 0x1FFF0000) != 0x70000 )
        v57 = v49;
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v57);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v58 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
        v59 = 94;
LABEL_147:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v59, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v58);
        goto LABEL_75;
      }
      goto LABEL_75;
    }
    v44 = 2147483646;
    v45 = v36;
    v46 = (_WORD *)*((_QWORD *)lpMem + HIDWORD(v68));
    do
    {
      if ( !v44 )
        break;
      v47 = *v43;
      if ( !*v43 )
        break;
      ++v43;
      *v45++ = v47;
      --v44;
      --v38;
    }
    while ( v38 );
    v48 = v45 - 1;
    if ( v38 )
      v48 = v45;
    *v48 = 0;
    v49 = v38 == 0 ? 0x8007007A : 0;
    if ( !v38 )
      goto LABEL_142;
    v50 = -1;
    do
      ++v50;
    while ( v46[v50] );
    v36 += v50;
    v37 -= v50;
    if ( dword_18027FBEC != 2 )
    {
      if ( dword_18027FBEC == 4 )
      {
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) != 0 )
        {
          v56 = 10;
          goto LABEL_138;
        }
      }
      else
      {
        if ( dword_18027FBEC == 8 )
        {
          v55 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) == 0 )
            goto LABEL_139;
          v56 = 11;
        }
        else
        {
          v55 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000000) == 0 )
            goto LABEL_139;
          v56 = 12;
        }
LABEL_138:
        WPP_SF_(v55[2], v56, WPP_9bd13fd0c4ba3d813d171a602a744429_Traceguids);
      }
LABEL_139:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0x105u, L"261", 0x54Fu, 0);
      continue;
    }
    if ( !g_wsManHeap )
      goto LABEL_139;
    HeapFree(g_wsManHeap, 0, v46);
  }
  if ( v37 )
  {
    if ( v37 > 0x7FFFFFFFuLL )
    {
      v41 = -2147024809;
      *v36 = 0;
    }
    else
    {
      v39 = L"</OperationsConfiguration>";
      do
      {
        if ( !v28 )
          break;
        v40 = *v39;
        if ( !*v39 )
          break;
        ++v39;
        *v36++ = v40;
        --v28;
        --v38;
      }
      while ( v38 );
      v41 = v38 == 0 ? 0x8007007A : 0;
      v42 = v36 - 1;
      if ( v38 )
        v42 = v36;
      *v42 = 0;
      if ( v38 )
      {
        v75 = 0;
        AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=((char *)this + 304, v76);
        goto LABEL_75;
      }
    }
  }
  else
  {
    v41 = -2147024809;
  }
  v6 = 0;
  v60 = (unsigned __int16)v41;
  if ( (v41 & 0x1FFF0000) != 0x70000 )
    v60 = v41;
  (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v60);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    v58 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v59 = 95;
    goto LABEL_147;
  }
LABEL_75:
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v75);
LABEL_34:
  v16 = lpMem;
  while ( (_DWORD)v15 )
  {
    v15 = (unsigned int)(v15 - 1);
    HIDWORD(v68) = v15;
    v21 = (void *)v16[v15];
    if ( !v21 )
      break;
    WSManMemory::Free(v21, 0);
  }
  v17 = (CHeap *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v6);
  if ( CHeap::GetHandle(v17) )
  {
    if ( v16 )
    {
      Handle = CHeap::GetHandle(v18);
      HeapFree(Handle, 0, v16);
    }
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0x105u, L"261", 0x54Fu, 0);
  }
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v65);
  return v6;
}

```

## disassembly

```asm
0x18003f8c8  mov     [rsp-38h+arg_8], rbx
0x18003f8cd  mov     [rsp-38h+arg_0], rcx
0x18003f8d2  push    rbp
0x18003f8d3  push    rsi
0x18003f8d4  push    rdi
0x18003f8d5  push    r12
0x18003f8d7  push    r13
0x18003f8d9  push    r14
0x18003f8db  push    r15
0x18003f8dd  mov     rbp, rsp
0x18003f8e0  sub     rsp, 80h
0x18003f8e7  mov     rdi, rdx
0x18003f8ea  lea     r14, WPP_GLOBAL_Control
0x18003f8f1  mov     esi, 400h
0x18003f8f6  lea     r12, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18003f8fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f904  cmp     rcx, r14
0x18003f907  jnz     loc_18003FEB7
0x18003f90d  xor     edx, edx
0x18003f90f  lea     ecx, [rdx+4]
0x18003f912  call    ?GetFirstConfigManagerForTable@CConfigManager@@SAPEAV1@W4WSMANTableConfigType@@PEBG@Z; CConfigManager::GetFirstConfigManagerForTable(WSMANTableConfigType,ushort const *)
0x18003f917  mov     rbx, rax
0x18003f91a  mov     [rbp+var_48], rax
0x18003f91e  xor     r15d, r15d
0x18003f921  test    rax, rax
0x18003f924  jz      loc_18003FED6
0x18003f92a  mov     r12d, r15d
0x18003f92d  mov     dword ptr [rbp+arg_18], r15d
0x18003f931  mov     r13d, r15d
0x18003f934  mov     [rbp+var_30], r15
0x18003f938  mov     [rbp+lpMem], r15
0x18003f93c  lea     esi, [r15+1]
0x18003f940  lea     rax, ??_7PLUGIN_IDENTITY@@6B@; const PLUGIN_IDENTITY::`vftable'
0x18003f947  mov     [rbp+var_20], rax
0x18003f94b  mov     [rbp+String1], r15
0x18003f94f  mov     [rbp+var_8], r15d
0x18003f953  mov     [rbp+var_18], 4
0x18003f95a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f961  cmp     rcx, r14
0x18003f964  jz      short loc_18003F973
0x18003f966  test    dword ptr [rcx+1Ch], 200000h
0x18003f96d  jnz     loc_18003FF9B
0x18003f973  cmp     [rbx+2C18h], r15d
0x18003f97a  jz      loc_180040555
0x18003f980  mov     rdx, [rbx+2C20h]
0x18003f987  test    rdx, rdx
0x18003f98a  jz      loc_180040547
0x18003f990  lea     rcx, [rbp+var_20]
0x18003f994  mov     rax, [rax+10h]
0x18003f998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f99d  test    eax, eax
0x18003f99f  jz      loc_180040578
0x18003f9a5  mov     r15, [rbp+String1]
0x18003f9a9  xor     r14d, r14d
0x18003f9ac  test    r15, r15
0x18003f9af  jz      loc_18003FFBC
0x18003f9b5  lea     rdx, aWmiProvider; "WMI Provider"
0x18003f9bc  mov     rcx, r15; String1
0x18003f9bf  call    cs:__imp__wcsicmp
0x18003f9c5  test    eax, eax
0x18003f9c7  jz      loc_18003FABC
0x18003f9cd  test    r15, r15
0x18003f9d0  jz      loc_18003FFE4
0x18003f9d6  lea     rdx, aEventForwardin; "Event Forwarding Plugin"
0x18003f9dd  mov     rcx, r15; String1
0x18003f9e0  call    cs:__imp__wcsicmp
0x18003f9e6  test    eax, eax
0x18003f9e8  jz      loc_18003FABC
0x18003f9ee  test    r15, r15
0x18003f9f1  jz      loc_18004000C
0x18003f9f7  lea     rdx, aSelPlugin; "SEL Plugin"
0x18003f9fe  mov     rcx, r15; String1
0x18003fa01  call    cs:__imp__wcsicmp
0x18003fa07  test    eax, eax
0x18003fa09  jz      loc_18003FABC
0x18003fa0f  mov     [rbp+var_40], r14
0x18003fa13  mov     [rbp+var_50], r14
0x18003fa17  mov     [rsp+80h+var_60], r14; int *
0x18003fa1c  lea     r9, [rbp+var_40]; struct XmlReader **
0x18003fa20  lea     r8, [rbp+var_50]; unsigned __int16 **
0x18003fa24  mov     rdx, rdi; struct IRequestContext *
0x18003fa27  mov     rcx, rbx; this
0x18003fa2a  call    ?GetConfigXml@CConfigManager@@QEAAHPEAVIRequestContext@@PEAPEBGPEAPEAVXmlReader@@PEAH@Z; CConfigManager::GetConfigXml(IRequestContext *,ushort const * *,XmlReader * *,int *)
0x18003fa2f  mov     r14, [rbp+var_40]
0x18003fa33  test    eax, eax
0x18003fa35  jz      loc_180040034
0x18003fa3b  xor     r15d, r15d
0x18003fa3e  mov     dword ptr [rbp+arg_10], r15d
0x18003fa42  lea     r9, [rbp+arg_10]; unsigned int *
0x18003fa46  mov     r8, r14; struct XmlReader *
0x18003fa49  mov     rdx, [rbp+var_50]; unsigned __int16 *
0x18003fa4d  call    ?ResolveConfigXml@Catalog@@AEAAPEBGPEBGPEAVXmlReader@@AEAK@Z; Catalog::ResolveConfigXml(ushort const *,XmlReader *,ulong &)
0x18003fa52  mov     r12, rax
0x18003fa55  mov     [rbp+var_38], rax
0x18003fa59  test    rax, rax
0x18003fa5c  jz      loc_18003FBBC
0x18003fa62  mov     ecx, dword ptr [rbp+var_30+4]
0x18003fa65  cmp     r13d, ecx
0x18003fa68  jbe     loc_18004009B
0x18003fa6e  mov     eax, ecx
0x18003fa70  mov     rdx, [rbp+lpMem]
0x18003fa74  mov     [rdx+rax*8], r12
0x18003fa78  add     ecx, esi
0x18003fa7a  mov     dword ptr [rbp+var_30+4], ecx
0x18003fa7d  mov     [rbp+var_38], r15
0x18003fa81  mov     r12d, dword ptr [rbp+arg_18]
0x18003fa85  add     r12d, dword ptr [rbp+arg_10]
0x18003fa89  mov     dword ptr [rbp+arg_18], r12d
0x18003fa8d  lea     rcx, [rbp+var_38]
0x18003fa91  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18003fa96  nop
0x18003fa97  lea     rcx, [rbp+var_50]
0x18003fa9b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18003faa0  nop
0x18003faa1  test    r14, r14
0x18003faa4  jz      short loc_18003FABF
0x18003faa6  mov     rcx, r14; this
0x18003faa9  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x18003faae  nop
0x18003faaf  xor     edx, edx; int
0x18003fab1  mov     rcx, r14; void *
0x18003fab4  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x18003fab9  nop
0x18003faba  jmp     short loc_18003FABF
0x18003fabc  xor     r15d, r15d
0x18003fabf  mov     rcx, rbx; this
0x18003fac2  call    ?NextRow@CConfigManager@@QEAAHXZ; CConfigManager::NextRow(void)
0x18003fac7  test    eax, eax
0x18003fac9  jz      short loc_18003FAFF
0x18003facb  lea     rax, ??_7PLUGIN_IDENTITY@@6B@; const PLUGIN_IDENTITY::`vftable'
0x18003fad2  mov     [rbp+var_20], rax
0x18003fad6  cmp     [rbp+var_8], r15d
0x18003fada  lea     r14, WPP_GLOBAL_Control
0x18003fae1  jz      loc_18003F947
0x18003fae7  xor     edx, edx; int
0x18003fae9  mov     rcx, [rbp+String1]; void *
0x18003faed  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x18003faf2  nop
0x18003faf3  lea     r14, WPP_GLOBAL_Control
0x18003fafa  jmp     loc_18003F940
0x18003faff  call    cs:__imp_GetLastError
0x18003fb05  mov     edx, eax
0x18003fb07  cmp     eax, 103h
0x18003fb0c  jnz     loc_1800401B2
0x18003fb12  lea     rax, ??_7PLUGIN_IDENTITY@@6B@; const PLUGIN_IDENTITY::`vftable'
0x18003fb19  mov     [rbp+var_20], rax
0x18003fb1d  cmp     [rbp+var_8], r15d
0x18003fb21  jnz     loc_180040202
0x18003fb27  test    r12d, r12d
0x18003fb2a  jnz     loc_18003FC2C
0x18003fb30  lea     rdi, WPP_GLOBAL_Control
0x18003fb37  mov     r14d, dword ptr [rbp+var_30+4]
0x18003fb3b  mov     rbx, [rbp+lpMem]
0x18003fb3f  test    r14d, r14d
0x18003fb42  jnz     short loc_18003FBA2
0x18003fb44  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18003fb4b  cmp     rcx, rdi
0x18003fb4e  jnz     loc_1800404F5
0x18003fb54  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18003fb59  test    rax, rax
0x18003fb5c  jz      loc_18004051F
0x18003fb62  test    rbx, rbx
0x18003fb65  jz      short loc_18003FB7B
0x18003fb67  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18003fb6c  mov     r8, rbx; lpMem
0x18003fb6f  xor     edx, edx; dwFlags
0x18003fb71  mov     rcx, rax; hHeap
0x18003fb74  call    cs:__imp_HeapFree
0x18003fb7a  nop
0x18003fb7b  lea     rcx, [rbp+var_48]
0x18003fb7f  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18003fb84  nop
0x18003fb85  mov     eax, esi
0x18003fb87  mov     rbx, [rsp+80h+arg_8]
0x18003fb8f  add     rsp, 80h
0x18003fb96  pop     r15
0x18003fb98  pop     r14
0x18003fb9a  pop     r13
0x18003fb9c  pop     r12
0x18003fb9e  pop     rdi
0x18003fb9f  pop     rsi
0x18003fba0  pop     rbp
0x18003fba1  retn
0x18003fba2  dec     r14d
0x18003fba5  mov     dword ptr [rbp+var_30+4], r14d
0x18003fba9  mov     rcx, [rbx+r14*8]; void *
0x18003fbad  test    rcx, rcx
0x18003fbb0  jz      short loc_18003FB44
0x18003fbb2  xor     edx, edx; int
0x18003fbb4  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x18003fbb9  nop
0x18003fbba  jmp     short loc_18003FB3F
0x18003fbbc  mov     esi, r15d
0x18003fbbf  call    cs:__imp_GetLastError
0x18003fbc5  mov     ebx, eax
0x18003fbc7  mov     rcx, [rdi]
0x18003fbca  mov     rax, [rcx+48h]
0x18003fbce  mov     edx, ebx
0x18003fbd0  mov     rcx, rdi
0x18003fbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fbdf  lea     rdi, WPP_GLOBAL_Control
0x18003fbe6  cmp     rcx, rdi
0x18003fbe9  jnz     loc_180040188
0x18003fbef  lea     rcx, [rbp+var_38]
0x18003fbf3  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18003fbf8  nop
0x18003fbf9  lea     rcx, [rbp+var_50]
0x18003fbfd  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18003fc02  nop
0x18003fc03  test    r14, r14
0x18003fc06  jnz     short loc_18003FC16
0x18003fc08  lea     rcx, [rbp+var_20]; this
0x18003fc0c  call    ??1PLUGIN_IDENTITY@@UEAA@XZ; PLUGIN_IDENTITY::~PLUGIN_IDENTITY(void)
0x18003fc11  jmp     loc_18003FB37
0x18003fc16  mov     rcx, r14; this
0x18003fc19  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x18003fc1e  nop
0x18003fc1f  xor     edx, edx; int
0x18003fc21  mov     rcx, r14; void *
0x18003fc24  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x18003fc29  nop
0x18003fc2a  jmp     short loc_18003FC08
0x18003fc2c  lea     r14d, [r12+34h]
0x18003fc31  mov     ebx, r14d
0x18003fc34  mov     eax, 2
0x18003fc39  mul     rbx
0x18003fc3c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003fc43  cmovb   rax, rcx
0x18003fc47  xor     r8d, r8d
0x18003fc4a  xor     edx, edx
0x18003fc4c  mov     rcx, rax
0x18003fc4f  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18003fc54  mov     r15, rax
0x18003fc57  mov     [rbp+arg_18], rax
0x18003fc5b  mov     [rbp+arg_10], rax
0x18003fc5f  xor     r13d, r13d
0x18003fc62  test    rax, rax
0x18003fc65  jz      loc_180040213
0x18003fc6b  lea     r8, [r14+r14]; Size
0x18003fc6f  xor     edx, edx; Val
0x18003fc71  mov     rcx, rax; void *
0x18003fc74  call    memset_0
0x18003fc79  test    r14d, r14d
0x18003fc7c  jz      loc_18004049A
0x18003fc82  cmp     rbx, 7FFFFFFFh
0x18003fc89  ja      loc_18004022D
0x18003fc8f  mov     r12d, 7FFFFFFEh
0x18003fc95  mov     eax, r12d
0x18003fc98  lea     rcx, aOperationsconf; "<OperationsConfiguration>"
0x18003fc9f  mov     rdx, r15
0x18003fca2  test    rax, rax
0x18003fca5  jz      short loc_18003FCC5
0x18003fca7  movzx   r8d, word ptr [rcx]
0x18003fcab  test    r8w, r8w
0x18003fcaf  jz      short loc_18003FCC5
0x18003fcb1  add     rcx, 2
0x18003fcb5  mov     [rdx], r8w
0x18003fcb9  add     rdx, 2
0x18003fcbd  sub     rax, rsi
0x18003fcc0  sub     rbx, rsi
0x18003fcc3  jnz     short loc_18003FCA2
0x18003fcc5  mov     rax, rbx
0x18003fcc8  neg     rax
0x18003fccb  sbb     r9d, r9d
0x18003fcce  not     r9d
0x18003fcd1  mov     r11d, 8007007Ah
0x18003fcd7  and     r9d, r11d
0x18003fcda  lea     rcx, [rdx-2]
0x18003fcde  test    rbx, rbx
0x18003fce1  cmovnz  rcx, rdx
0x18003fce5  mov     [rcx], r13w
0x18003fce9  jnz     short loc_18003FD3A
0x18003fceb  xor     r15d, r15d
0x18003fcee  mov     esi, r15d
0x18003fcf1  mov     r8, [rdi]
0x18003fcf4  mov     eax, r9d
0x18003fcf7  and     eax, 1FFF0000h
0x18003fcfc  movzx   edx, r9w
0x18003fd00  cmp     eax, 70000h
0x18003fd05  cmovnz  edx, r9d
0x18003fd09  mov     rcx, rdi
0x18003fd0c  mov     rax, [r8+48h]
0x18003fd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd15  mov     rax, cs:WPP_GLOBAL_Control
0x18003fd1c  lea     rcx, WPP_GLOBAL_Control
0x18003fd23  cmp     rax, rcx
0x18003fd26  jnz     loc_1800404B2
0x18003fd2c  lea     rcx, [rbp+arg_10]
0x18003fd30  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18003fd35  jmp     loc_18003FB30
0x18003fd3a  lea     rbx, [r15+32h]
0x18003fd3e  lea     r13d, [r14-19h]
0x18003fd42  xor     r15d, r15d
0x18003fd45  mov     r14d, dword ptr [rbp+var_30+4]
0x18003fd49  mov     edx, r13d
0x18003fd4c  test    r14d, r14d
0x18003fd4f  jnz     loc_18003FDE4
0x18003fd55  test    rdx, rdx
0x18003fd58  jz      loc_18004043B
  ... truncated ...
```
