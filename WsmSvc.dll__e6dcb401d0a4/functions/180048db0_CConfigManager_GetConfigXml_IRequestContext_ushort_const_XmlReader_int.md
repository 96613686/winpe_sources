# CConfigManager::GetConfigXml(IRequestContext *,ushort const * *,XmlReader * *,int *)

- ea: `0x180048db0`
- end: `0x18004971b`
- name: `?GetConfigXml@CConfigManager@@QEAAHPEAVIRequestContext@@PEAPEBGPEAPEAVXmlReader@@PEAH@Z`
- size: `2411`
- prototype: `__int64 __usercall@<rax>(CConfigManager *__hidden this@<rcx>, struct IRequestContext *@<rdx>, const unsigned __int16 **@<r8>, struct XmlReader **@<r9>, int *)`
- caller_count: `6`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180033e34`
- `0x180036de0`
- `0x18003eae0`
- `0x18003f8c8`
- `0x180109990`
- `0x180173484`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18001e900`
- `0x1800232f0`
- `0x180024ae0`
- `0x180036de0`
- `0x18003b1c0`
- `0x180047990`
- `0x180048db0`
- `0x18004a900`
- `0x18005d800`
- `0x18005f000`
- `0x1800e5510`
- `0x180103850`
- `0x180112380`
- `0x1801123a8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048ed2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f76`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048fef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048ed2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f76`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048fef`

## string_xrefs

- `0x1800493a1`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180049418`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180049440`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180049465`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004969e`: `onecore\admin\wmi\wmx\config\configregistry.cpp`
- `0x18004956e`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18004970a`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x180049489`: `StringCchCopy`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CConfigManager::GetConfigXml(
        CConfigManager *this,
        struct IRequestContext *a2,
        const unsigned __int16 **a3,
        struct XmlReader **a4,
        int *a5)
{
  PVOID *v7; // r10
  unsigned __int16 *v8; // r13
  __int64 v9; // r8
  unsigned int i; // edx
  struct _CONFIG_INFO near **v11; // rsi
  __int64 v12; // r14
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // r15d
  SIZE_T v16; // rbx
  CHeap *v17; // rcx
  void *Handle; // rax
  unsigned int v19; // eax
  CHeap *v20; // rcx
  unsigned int v21; // ebx
  CHeap *v22; // rcx
  void *v23; // rax
  XmlReader *v24; // rax
  CHeap *v25; // rcx
  XmlReader *v26; // r15
  XmlReader *v27; // r12
  CHeap *v28; // rcx
  void *v29; // rax
  XmlReader *v30; // rax
  XmlReader *v31; // rsi
  __int64 v32; // rax
  SIZE_T v33; // rbx
  CHeap *v34; // rcx
  unsigned __int16 *v35; // r13
  void *v36; // rax
  unsigned __int64 v37; // rdx
  CConfigManager *v38; // r13
  unsigned __int16 *v40; // rbx
  int v41; // eax
  __int64 v42; // r9
  __int64 v43; // rax
  struct _FWXML_ELEMENT *v44; // r8
  int v45; // edx
  const unsigned __int16 *v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rax
  unsigned int v49; // eax
  __int64 v50; // rdx
  const unsigned __int16 *v51; // r8
  unsigned int v52; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v53; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int16 *v54; // [rsp+40h] [rbp-28h]
  XmlReader *v55; // [rsp+48h] [rbp-20h] BYREF
  XmlReader *v56; // [rsp+50h] [rbp-18h] BYREF
  __int64 v57; // [rsp+58h] [rbp-10h]
  unsigned __int64 v59; // [rsp+B8h] [rbp+50h] BYREF
  const unsigned __int16 **v60; // [rsp+C0h] [rbp+58h]
  struct XmlReader **v61; // [rsp+C8h] [rbp+60h]

  v61 = a4;
  v60 = a3;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = 0;
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1538, L"1538", 0x54Fu, 0);
    return 0;
  }
  v9 = *((_QWORD *)this + 1412);
  if ( !v9 )
  {
    v46 = L"1541";
    v47 = 1541;
LABEL_117:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", v47, v46, 0x54Fu, a2);
    return 0;
  }
  if ( *(_DWORD *)(v9 + 8) != 4 )
  {
    v46 = L"1542";
    v47 = 1542;
    goto LABEL_117;
  }
  LODWORD(v59) = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x45 )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400000) != 0 )
        WPP_SF_Dd(v7[2], 11, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids);
      v50 = 661;
      v51 = L"661";
      goto LABEL_113;
    }
    v11 = &g_ConfigSettings + 6 * i;
    if ( *(_DWORD *)v11 == 6007 )
      break;
  }
  if ( (*((_BYTE *)v11 + 20) & 0x3F) == 0 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400000) != 0 )
      WPP_SF_Dd(v7[2], 10, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids);
    v50 = 653;
    v51 = L"653";
LABEL_113:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", v50, v51, 0x54Fu, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
    (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, __int64))(*(_QWORD *)a2 + 88LL))(
      a2,
      1077134176,
      L"FindSetting",
      1);
    v46 = L"1554";
    v47 = 1554;
    goto LABEL_117;
  }
  v12 = *(_QWORD *)(v9 + 16);
  v57 = v12;
  v52 = 0;
  v13 = CConfigManager::QueryRegValue(
          this,
          (struct _CONFIG_INFO *)(&g_ConfigSettings + 6 * i),
          &v52,
          0,
          0,
          (unsigned int *)&v59);
  v14 = v13;
  if ( v13 != 122 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, v13);
    v48 = *(_QWORD *)a2;
    if ( v14 == 2 )
      (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64))(v48 + 64))(
        a2,
        2150859152LL,
        1077134541,
        v12);
    else
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(v48 + 72))(a2, v14);
    return 0;
  }
  v15 = ((unsigned int)v59 >> 1) + 1;
  v16 = 2LL * v15;
  if ( !is_mul_ok(v15, 2u) )
    v16 = -1;
  if ( CHeap::GetHandle((CHeap *)(((unsigned int)v59 >> 1) + 1)) )
  {
    Handle = CHeap::GetHandle(v17);
    v8 = (unsigned __int16 *)HeapAlloc(Handle, 0, v16);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
  }
  v54 = v8;
  v53 = v8;
  if ( !v8 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    goto LABEL_37;
  }
  v19 = CConfigManager::QueryRegValue(
          this,
          (struct _CONFIG_INFO *)v11,
          &v52,
          2 * v15,
          (unsigned __int8 *)v8,
          (unsigned int *)&v59);
  v21 = v19;
  if ( v19 )
  {
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v19);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, v21);
    goto LABEL_37;
  }
  if ( CHeap::GetHandle(v20) )
  {
    v23 = CHeap::GetHandle(v22);
    v24 = (XmlReader *)HeapAlloc(v23, 0, 0x20u);
    v26 = v24;
    if ( v24 )
    {
      *(_QWORD *)v24 = 0;
      *((_QWORD *)v24 + 1) = 0;
      *((_QWORD *)v24 + 2) = 0;
      goto LABEL_20;
    }
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
  }
  v26 = 0;
LABEL_20:
  v27 = v26;
  v55 = v26;
  if ( !CHeap::GetHandle(v25) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    goto LABEL_39;
  }
  v29 = CHeap::GetHandle(v28);
  v30 = (XmlReader *)HeapAlloc(v29, 0, 0x20u);
  v31 = v30;
  if ( !v30 )
  {
LABEL_39:
    v31 = 0;
    goto LABEL_23;
  }
  *(_QWORD *)v30 = 0;
  *((_QWORD *)v30 + 1) = 0;
  *((_QWORD *)v30 + 2) = 0;
LABEL_23:
  v56 = v31;
  if ( !v26 || !v31 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
    if ( v31 )
    {
      XmlReader::~XmlReader(v31);
      WSManMemory::Free(v31, 0);
    }
    if ( v26 )
    {
      XmlReader::~XmlReader(v26);
      WSManMemory::Free(v26, 0);
    }
    goto LABEL_37;
  }
  v32 = -1;
  do
    ++v32;
  while ( v8[v32] );
  v59 = (unsigned int)(v32 + 1);
  v33 = 2 * v59;
  if ( !is_mul_ok(v59, 2u) )
    v33 = -1;
  v35 = 0;
  if ( CHeap::GetHandle((CHeap *)(unsigned int)(v32 + 1)) )
  {
    v36 = CHeap::GetHandle(v34);
    v35 = (unsigned __int16 *)HeapAlloc(v36, 0, v33);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
  }
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr((char *)v26 + 16);
  *((_QWORD *)v26 + 2) = v35;
  v37 = v59;
  *((_QWORD *)v26 + 3) = v59;
  if ( !v35 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    goto LABEL_33;
  }
  v40 = v54;
  v41 = StringCchCopyW(v35, v37, v54);
  v42 = (unsigned int)v41;
  if ( v41 < 0 )
  {
    if ( (v41 & 0x1FFF0000) == 0x70000 )
      v42 = (unsigned __int16)v41;
    (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, __int64))(*(_QWORD *)a2 + 88LL))(
      a2,
      1077134180,
      L"StringCchCopy",
      v42);
    goto LABEL_33;
  }
  if ( !(unsigned int)XmlReader::Parse(v26, a2) || !XmlReader::Init(v31, a2, v40) )
  {
LABEL_33:
    v38 = this;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
  v43 = *((_QWORD *)v31 + 1);
  if ( v43 )
    v44 = *(struct _FWXML_ELEMENT **)(v43 + 16);
  else
    v44 = 0;
  if ( !(unsigned int)ConfigValidateXMLElement(a2, (struct _CONFIGXML_ELEMENT *)&g_pluginConfigurationElement, v44, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
    v38 = this;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
  LODWORD(v59) = 0;
  v38 = this;
  v45 = ConfigValidatePluginXml(a2, v31, *(wchar_t **)(*((_QWORD *)this + 1412) + 16LL), (XmlReader *)&v59, 0);
  if ( a5 )
    *a5 = v59;
  if ( !v45 )
  {
LABEL_34:
    if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2) != -2144108477 )
    {
LABEL_35:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      {
        v49 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, v49);
      }
      XmlReader::~XmlReader(v31);
      WSManMemory::Free(v31, 0);
      XmlReader::~XmlReader(v26);
      WSManMemory::Free(v26, 0);
      goto LABEL_37;
    }
    if ( *(_DWORD *)(*((_QWORD *)v38 + 1412) + 8LL) == 4 )
    {
      (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64))(*(_QWORD *)a2 + 64LL))(
        a2,
        2150859152LL,
        1077134541,
        v57);
      goto LABEL_35;
    }
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1631, L"1631", 0x54Fu, a2);
    AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v56);
    AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v55);
LABEL_37:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v53);
    return 0;
  }
  if ( v60 )
  {
    v53 = 0;
    *v60 = v40;
  }
  if ( v61 )
  {
    v27 = 0;
    v55 = 0;
    *v61 = v26;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
  XmlReader::~XmlReader(v31);
  WSManMemory::Free(v31, 0);
  if ( v27 )
  {
    XmlReader::~XmlReader(v27);
    WSManMemory::Free(v27, 0);
  }
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v53);
  return 1;
}

```

## disassembly

```asm
0x180048db0  mov     [rsp-40h+arg_18], r9
0x180048db5  mov     [rsp-40h+arg_10], r8
0x180048dba  mov     [rsp-40h+arg_0], rcx
0x180048dbf  push    rbp
0x180048dc0  push    rbx
0x180048dc1  push    rsi
0x180048dc2  push    rdi
0x180048dc3  push    r12
0x180048dc5  push    r13
0x180048dc7  push    r14
0x180048dc9  push    r15
0x180048dcb  mov     rbp, rsp
0x180048dce  sub     rsp, 68h
0x180048dd2  mov     rdi, rdx
0x180048dd5  mov     r12, rcx
0x180048dd8  lea     r15, WPP_GLOBAL_Control
0x180048ddf  mov     ebx, 200000h
0x180048de4  mov     r10, cs:WPP_GLOBAL_Control
0x180048deb  cmp     r10, r15
0x180048dee  jnz     loc_1800492B4
0x180048df4  xor     r13d, r13d
0x180048df7  test    rdi, rdi
0x180048dfa  jz      loc_1800492DF
0x180048e00  mov     r8, [r12+2C20h]
0x180048e08  test    r8, r8
0x180048e0b  jz      loc_1800492FB
0x180048e11  cmp     dword ptr [r8+8], 4
0x180048e16  jnz     loc_180049312
0x180048e1c  mov     dword ptr [rbp+arg_8], r13d
0x180048e20  mov     edx, r13d
0x180048e23  mov     r9d, 1777h
0x180048e29  cmp     edx, 45h ; 'E'
0x180048e2c  jnb     loc_18004965A
0x180048e32  mov     eax, edx
0x180048e34  lea     rsi, [rax+rax*2]
0x180048e38  shl     rsi, 4
0x180048e3c  lea     rax, ?g_ConfigSettings@@3PAU_CONFIG_INFO@@A; _CONFIG_INFO near * g_ConfigSettings
0x180048e43  add     rsi, rax
0x180048e46  cmp     [rsi], r9d
0x180048e49  jz      short loc_180048E4F
0x180048e4b  inc     edx
0x180048e4d  jmp     short loc_180048E29
0x180048e4f  test    byte ptr [rsi+14h], 3Fh
0x180048e53  jz      loc_180049620
0x180048e59  mov     r14, [r8+10h]
0x180048e5d  mov     [rbp+var_10], r14
0x180048e61  mov     [rbp+var_38], r13d
0x180048e65  lea     rax, [rbp+arg_8]
0x180048e69  mov     [rsp+68h+var_40], rax; unsigned int *
0x180048e6e  mov     [rsp+68h+var_48], r13; unsigned __int8 *
0x180048e73  xor     r9d, r9d; unsigned int
0x180048e76  lea     r8, [rbp+var_38]; unsigned int *
0x180048e7a  mov     rdx, rsi; struct _CONFIG_INFO *
0x180048e7d  mov     rcx, r12; this
0x180048e80  call    ?QueryRegValue@CConfigManager@@AEAAJPEAU_CONFIG_INFO@@PEAKKPEAE1@Z; CConfigManager::QueryRegValue(_CONFIG_INFO *,ulong *,ulong,uchar *,ulong *)
0x180048e85  mov     ebx, eax
0x180048e87  cmp     eax, 7Ah ; 'z'
0x180048e8a  jnz     loc_180049329
0x180048e90  mov     r15d, dword ptr [rbp+arg_8]
0x180048e94  shr     r15d, 1
0x180048e97  inc     r15d
0x180048e9a  mov     ecx, r15d; this
0x180048e9d  lea     eax, [rbx-78h]
0x180048ea0  mul     rcx
0x180048ea3  mov     rbx, rax
0x180048ea6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180048ead  cmovb   rbx, rax
0x180048eb1  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180048eb6  mov     r14d, 54Fh
0x180048ebc  test    rax, rax
0x180048ebf  jz      loc_18004938D
0x180048ec5  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180048eca  mov     r8, rbx; dwBytes
0x180048ecd  xor     edx, edx; dwFlags
0x180048ecf  mov     rcx, rax; hHeap
0x180048ed2  call    cs:__imp_HeapAlloc
0x180048ed8  mov     r13, rax
0x180048edb  mov     [rbp+var_28], r13
0x180048edf  mov     [rbp+var_30], r13
0x180048ee3  test    r13, r13
0x180048ee6  jz      loc_1800490A9
0x180048eec  lea     r9d, [r15+r15]; unsigned int
0x180048ef0  lea     rax, [rbp+arg_8]
0x180048ef4  mov     [rsp+68h+var_40], rax; unsigned int *
0x180048ef9  mov     [rsp+68h+var_48], r13; unsigned __int8 *
0x180048efe  lea     r8, [rbp+var_38]; unsigned int *
0x180048f02  mov     rdx, rsi; struct _CONFIG_INFO *
0x180048f05  mov     rcx, r12; this
0x180048f08  call    ?QueryRegValue@CConfigManager@@AEAAJPEAU_CONFIG_INFO@@PEAKKPEAE1@Z; CConfigManager::QueryRegValue(_CONFIG_INFO *,ulong *,ulong,uchar *,ulong *)
0x180048f0d  mov     ebx, eax
0x180048f0f  test    eax, eax
0x180048f11  jnz     loc_1800493B2
0x180048f17  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180048f1c  lea     esi, [rbx+20h]
0x180048f1f  xor     ebx, ebx
0x180048f21  test    rax, rax
0x180048f24  jz      loc_180049404
0x180048f2a  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180048f2f  mov     r8d, esi; dwBytes
0x180048f32  xor     edx, edx; dwFlags
0x180048f34  mov     rcx, rax; hHeap
0x180048f37  call    cs:__imp_HeapAlloc
0x180048f3d  mov     r15, rax
0x180048f40  test    rax, rax
0x180048f43  jz      loc_180049424
0x180048f49  mov     [rax], rbx
0x180048f4c  mov     [rax+8], rbx
0x180048f50  mov     [rax+10h], rbx
0x180048f54  mov     r12, r15
0x180048f57  mov     [rbp+var_20], r15
0x180048f5b  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180048f60  test    rax, rax
0x180048f63  jz      loc_18004942C
0x180048f69  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180048f6e  mov     r8, rsi; dwBytes
0x180048f71  xor     edx, edx; dwFlags
0x180048f73  mov     rcx, rax; hHeap
0x180048f76  call    cs:__imp_HeapAlloc
0x180048f7c  mov     rsi, rax
0x180048f7f  test    rax, rax
0x180048f82  jz      loc_1800490A1
0x180048f88  mov     [rax], rbx
0x180048f8b  mov     [rax+8], rbx
0x180048f8f  mov     [rax+10h], rbx
0x180048f93  mov     [rbp+var_18], rsi
0x180048f97  test    r15, r15
0x180048f9a  jz      loc_180049238
0x180048fa0  test    rsi, rsi
0x180048fa3  jz      loc_180049238
0x180048fa9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180048fad  mov     rax, r8
0x180048fb0  inc     rax
0x180048fb3  cmp     [r13+rax*2+0], bx
0x180048fb9  jnz     short loc_180048FB0
0x180048fbb  lea     ecx, [rax+1]; this
0x180048fbe  mov     [rbp+arg_8], rcx
0x180048fc2  mov     eax, 2
0x180048fc7  mul     rcx
0x180048fca  mov     rbx, rax
0x180048fcd  cmovb   rbx, r8
0x180048fd1  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180048fd6  xor     r13d, r13d
0x180048fd9  test    rax, rax
0x180048fdc  jz      loc_180049451
0x180048fe2  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180048fe7  mov     r8, rbx; dwBytes
0x180048fea  xor     edx, edx; dwFlags
0x180048fec  mov     rcx, rax; hHeap
0x180048fef  call    cs:__imp_HeapAlloc
0x180048ff5  mov     r13, rax
0x180048ff8  lea     rcx, [r15+10h]
0x180048ffc  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180049001  mov     [r15+10h], r13
0x180049005  mov     rdx, [rbp+arg_8]; unsigned __int64
0x180049009  mov     [r15+18h], rdx
0x18004900d  test    r13, r13
0x180049010  jnz     loc_1800490BA
0x180049016  mov     rax, [rdi]
0x180049019  mov     rcx, rdi
0x18004901c  mov     rax, [rax+18h]
0x180049020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049025  mov     r13, [rbp+arg_0]
0x180049029  lea     rbx, WPP_GLOBAL_Control
0x180049030  mov     rax, [rdi]
0x180049033  mov     rcx, rdi
0x180049036  mov     rax, [rax+98h]
0x18004903d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049042  cmp     eax, 80338043h
0x180049047  jz      loc_18004954D
0x18004904d  mov     rax, cs:WPP_GLOBAL_Control
0x180049054  cmp     rax, rbx
0x180049057  jnz     loc_1800495B6
0x18004905d  mov     rcx, rsi; this
0x180049060  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x180049065  nop
0x180049066  xor     edx, edx; int
0x180049068  mov     rcx, rsi; void *
0x18004906b  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180049070  nop
0x180049071  mov     rcx, r15; this
0x180049074  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x180049079  nop
0x18004907a  xor     edx, edx; int
0x18004907c  mov     rcx, r15; void *
0x18004907f  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180049084  nop
0x180049085  lea     rcx, [rbp+var_30]
0x180049089  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x18004908e  xor     eax, eax
0x180049090  add     rsp, 68h
0x180049094  pop     r15
0x180049096  pop     r14
0x180049098  pop     r13
0x18004909a  pop     r12
0x18004909c  pop     rdi
0x18004909d  pop     rsi
0x18004909e  pop     rbx
0x18004909f  pop     rbp
0x1800490a0  retn
0x1800490a1  mov     rsi, rbx
0x1800490a4  jmp     loc_180048F93
0x1800490a9  mov     rax, [rdi]
0x1800490ac  mov     rcx, rdi
0x1800490af  mov     rax, [rax+18h]
0x1800490b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800490b8  jmp     short loc_180049085
0x1800490ba  mov     rbx, [rbp+var_28]
0x1800490be  mov     r8, rbx; unsigned __int16 *
0x1800490c1  mov     rcx, r13; unsigned __int16 *
0x1800490c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800490c9  mov     r9d, eax
0x1800490cc  xor     r13d, r13d
0x1800490cf  test    eax, eax
0x1800490d1  js      loc_180049476
0x1800490d7  mov     rdx, rdi; struct IRequestContext *
0x1800490da  mov     rcx, r15; this
0x1800490dd  call    ?Parse@XmlReader@@AEAAHPEAVIRequestContext@@@Z; XmlReader::Parse(IRequestContext *)
0x1800490e2  test    eax, eax
0x1800490e4  jz      loc_180049025
0x1800490ea  mov     r8, rbx; unsigned __int16 *
0x1800490ed  mov     rdx, rdi; struct IRequestContext *
0x1800490f0  mov     rcx, rsi; this
0x1800490f3  call    ?Init@XmlReader@@QEAAHPEAVIRequestContext@@PEBG@Z; XmlReader::Init(IRequestContext *,ushort const *)
0x1800490f8  test    eax, eax
0x1800490fa  jz      loc_180049025
0x180049100  mov     rcx, cs:WPP_GLOBAL_Control
0x180049107  lea     rax, WPP_GLOBAL_Control
0x18004910e  cmp     rcx, rax
0x180049111  jz      short loc_180049120
0x180049113  test    dword ptr [rcx+1Ch], 200000h
0x18004911a  jnz     loc_1800494A6
0x180049120  mov     rax, [rsi+8]
0x180049124  test    rax, rax
0x180049127  jz      loc_180049230
0x18004912d  mov     r8, [rax+10h]; struct _FWXML_ELEMENT *
0x180049131  xor     r9d, r9d; unsigned __int16 *
0x180049134  lea     rdx, ?g_pluginConfigurationElement@@3U_CONFIGXML_ELEMENT@@A; struct _CONFIGXML_ELEMENT *
0x18004913b  mov     rcx, rdi; struct IRequestContext *
0x18004913e  call    ?ConfigValidateXMLElement@@YAHPEAVIRequestContext@@PEAU_CONFIGXML_ELEMENT@@PEAU_FWXML_ELEMENT@@PEBG@Z; ConfigValidateXMLElement(IRequestContext *,_CONFIGXML_ELEMENT *,_FWXML_ELEMENT *,ushort const *)
0x180049143  test    eax, eax
0x180049145  jz      loc_180049210
0x18004914b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049152  lea     rax, WPP_GLOBAL_Control
0x180049159  cmp     rcx, rax
0x18004915c  jz      short loc_18004916B
0x18004915e  test    dword ptr [rcx+1Ch], 200000h
0x180049165  jnz     loc_1800494E7
0x18004916b  mov     dword ptr [rbp+arg_8], r13d
0x18004916f  mov     r13, [rbp+arg_0]
0x180049173  mov     r8, [r13+2C20h]
0x18004917a  mov     dword ptr [rsp+68h+var_48], 0; int
0x180049182  lea     r9, [rbp+arg_8]; int *
0x180049186  mov     r8, [r8+10h]; unsigned __int16 *
0x18004918a  mov     rdx, rsi; struct XmlReader *
0x18004918d  mov     rcx, rdi; struct IRequestContext *
0x180049190  call    ?ConfigValidatePluginXml@@YAHPEAVIRequestContext@@PEAVXmlReader@@PEBGPEAHH@Z; ConfigValidatePluginXml(IRequestContext *,XmlReader *,ushort const *,int *,int)
0x180049195  mov     edx, eax
0x180049197  mov     rcx, [rbp+arg_20]
0x18004919b  xor     r8d, r8d
0x18004919e  test    rcx, rcx
0x1800491a1  jnz     loc_180049501
0x1800491a7  test    edx, edx
0x1800491a9  jz      loc_180049029
0x1800491af  mov     rax, [rbp+arg_10]
0x1800491b3  test    rax, rax
0x1800491b6  jnz     loc_18004950B
0x1800491bc  mov     rax, [rbp+arg_18]
0x1800491c0  test    rax, rax
0x1800491c3  jnz     loc_180049517
0x1800491c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800491d0  lea     rax, WPP_GLOBAL_Control
0x1800491d7  cmp     rcx, rax
0x1800491da  jnz     loc_180049526
0x1800491e0  mov     rcx, rsi; this
0x1800491e3  call    ??1XmlReader@@QEAA@XZ; XmlReader::~XmlReader(void)
0x1800491e8  nop
0x1800491e9  xor     edx, edx; int
0x1800491eb  mov     rcx, rsi; void *
0x1800491ee  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x1800491f3  nop
0x1800491f4  test    r12, r12
0x1800491f7  jnz     loc_180049285
0x1800491fd  lea     rcx, [rbp+var_30]
0x180049201  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180049206  mov     eax, 1
0x18004920b  jmp     loc_180049090
0x180049210  mov     rcx, cs:WPP_GLOBAL_Control
0x180049217  lea     rbx, WPP_GLOBAL_Control
0x18004921e  cmp     rcx, rbx
0x180049221  jnz     loc_1800494C0
0x180049227  mov     r13, [rbp+arg_0]
0x18004922b  jmp     loc_180049030
0x180049230  mov     r8, r13
0x180049233  jmp     loc_180049131
0x180049238  mov     rax, [rdi]
0x18004923b  mov     rcx, rdi
0x18004923e  mov     rax, [rax+18h]
0x180049242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049247  mov     rcx, cs:WPP_GLOBAL_Control
0x18004924e  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
