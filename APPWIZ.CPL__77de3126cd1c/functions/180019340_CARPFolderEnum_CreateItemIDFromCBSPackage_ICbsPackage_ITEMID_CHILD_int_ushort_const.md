# CARPFolderEnum::_CreateItemIDFromCBSPackage(ICbsPackage *,_ITEMID_CHILD * *,int,ushort const *)

- ea: `0x180019340`
- end: `0x1800198b3`
- name: `?_CreateItemIDFromCBSPackage@CARPFolderEnum@@AEAAJPEAUICbsPackage@@PEAPEAU_ITEMID_CHILD@@HPEBG@Z`
- size: `1395`
- prototype: `__int64 __fastcall(CARPFolderEnum *__hidden this, struct ICbsPackage *, struct _ITEMID_CHILD **, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800153d0`

## callees

- `0x18000791c`
- `0x180008cf8`
- `0x180014468`
- `0x18001778c`
- `0x180019340`
- `0x18001b000`
- `0x180050c74`
- `0x18005165c`
- `0x180051724`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180019701`
- `msvcrt!wcstoul` at `0x180019739`
- `msvcrt!wcstoul` at `0x180019701`
- `msvcrt!wcstoul` at `0x180019739`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180019399`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180019399`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019473`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019492`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001980b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019473`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019492`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001980b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001950e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019519`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019524`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001956c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001978e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800197ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001950e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019519`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019524`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001956c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800195fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001978e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800197ea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019403`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800197d6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019403`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800197d6`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18001974d`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18001974d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019760`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019760`

## pseudocode

```c
__int64 __fastcall CARPFolderEnum::_CreateItemIDFromCBSPackage(
        CARPFolderEnum *this,
        struct ICbsPackage *a2,
        struct _ITEMID_CHILD **a3,
        int a4,
        unsigned __int16 *a5)
{
  HRESULT ItemID; // edi
  __int64 v10; // rax
  int v11; // esi
  __int64 v12; // rax
  UINT UpdateReleaseTypeID; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // edx
  int v22; // r9d
  __int64 v23; // rax
  __int64 v24; // r9
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-B8h] BYREF
  PCNZWCH lpString1; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v32; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v33; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v34; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v35; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v36; // [rsp+80h] [rbp-80h] BYREF
  PCNZWCH v37; // [rsp+88h] [rbp-78h] BYREF
  _SYSTEMTIME v38; // [rsp+90h] [rbp-70h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t String[16]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v42; // [rsp+D4h] [rbp-2Ch]
  int v43; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v44[530]; // [rsp+DCh] [rbp-24h] BYREF
  WCHAR v45[264]; // [rsp+500h] [rbp+400h] BYREF
  WCHAR v46[264]; // [rsp+710h] [rbp+610h] BYREF

  *a3 = 0;
  ppv = 0;
  ItemID = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( ItemID >= 0 )
  {
    v10 = *(_QWORD *)a2;
    lpString1 = 0;
    v11 = 2;
    if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, PCNZWCH *))(v10 + 32))(a2, 2, &lpString1) >= 0
      && lpString1 )
    {
      if ( !*lpString1 || CompareStringW(0x7Fu, 1u, lpString1, -1, L"Default", 8) == 2 )
      {
        v12 = *(_QWORD *)a2;
        FileTime = 0;
        if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, FILETIME *))(v12 + 32))(a2, 8, &FileTime) >= 0 )
        {
          UpdateReleaseTypeID = GetUpdateReleaseTypeID(*(PCNZWCH *)&FileTime);
          if ( UpdateReleaseTypeID )
          {
            LoadStringW(g_hinst, UpdateReleaseTypeID, Buffer, 260);
            LoadStringW(g_hinst, 0x45u, v45, 260);
            v14 = *(_QWORD *)a2;
            pv = 0;
            if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(v14 + 32))(a2, 7, &pv) >= 0 )
            {
              EndPtr = 0;
              if ( (int)SHFormatResMessageArgAlloc(g_hinst, 68, &EndPtr, Buffer, v45, pv) >= 0 )
                IPropertyStore_SetString(ppv, &PKEY_ItemNameDisplay, EndPtr);
              CoTaskMemFree(pv);
            }
          }
          CoTaskMemFree(*(LPVOID *)&FileTime);
        }
      }
      else
      {
        IPropertyStore_SetString(ppv, &PKEY_ItemNameDisplay, lpString1);
      }
      CoTaskMemFree((LPVOID)lpString1);
    }
    v15 = *(_QWORD *)a2;
    v32 = 0;
    if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(v15 + 32))(a2, 10, &v32) >= 0 && v32 )
    {
      IPropertyStore_SetString(ppv, PKEY_Software_ProductVersion, v32);
      CoTaskMemFree(v32);
    }
    v16 = *(_QWORD *)a2;
    v33 = 0;
    if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(v16 + 32))(a2, 12, &v33) >= 0 && v33 )
    {
      IPropertyStore_SetString(ppv, PKEY_Software_Publisher, v33);
      CoTaskMemFree(v33);
    }
    v17 = *(_QWORD *)a2;
    v34 = 0;
    if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(v17 + 32))(a2, 9, &v34) >= 0 && v34 )
    {
      IPropertyStore_SetString(ppv, PKEY_Software_ProductID, v34);
      CoTaskMemFree(v34);
    }
    v18 = *(_QWORD *)a2;
    v35 = 0;
    if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(v18 + 32))(a2, 14, &v35) >= 0 && v35 )
    {
      IPropertyStore_SetString(ppv, PKEY_Software_SupportUrl, v35);
      CoTaskMemFree(v35);
    }
    v19 = *(_QWORD *)a2;
    v36 = 0;
    if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(v19 + 32))(a2, 19, &v36) >= 0 && v36 )
    {
      IPropertyStore_SetString(ppv, PKEY_Software_InstallLocation, v36);
      CoTaskMemFree(v36);
    }
    v20 = *(_QWORD *)a2;
    v31 = 0;
    if ( (*(int (__fastcall **)(struct ICbsPackage *, __int64, unsigned __int16 **))(v20 + 32))(a2, 17, &v31) >= 0
      && v31 )
    {
      FileTime = 0;
      pv = 0;
      EndPtr = 0;
      SystemTime = 0;
      if ( (int)StringCchCopyNW(String, 9u, v31, 8u) >= 0 )
      {
        FileTime.dwHighDateTime = wcstoul(String, &EndPtr, 16);
        if ( (int)StringCchCopyNW(String, 9u, v31 + 8, 8u) >= 0 )
        {
          FileTime.dwLowDateTime = wcstoul(String, &EndPtr, 16);
          if ( FileTimeToLocalFileTime(&FileTime, (LPFILETIME)&pv) )
          {
            if ( FileTimeToSystemTime((const FILETIME *)&pv, &SystemTime) )
            {
              v38 = SystemTime;
              IPropertyStore_SetSystemTime((_DWORD)ppv, v21, (unsigned int)&v38, v22, 259);
            }
          }
        }
      }
      CoTaskMemFree(v31);
    }
    v23 = *(_QWORD *)a2;
    v37 = 0;
    ItemID = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, PCNZWCH *))(v23 + 32))(a2, 11, &v37);
    if ( ItemID >= 0 )
    {
      v11 = CompareStringW(0x7Fu, 1u, v37, -1, L"1", -1) != 2 ? 2 : 0;
      CoTaskMemFree((LPVOID)v37);
    }
    LoadStringW(g_hinst, 0x45u, v46, 260);
    IPropertyStore_SetString(ppv, &PKEY_Software_ParentName, v46);
    if ( ItemID >= 0 )
    {
      memset_0(v44, 0, 0x418u);
      *(_DWORD *)Buffer = v11;
      v43 = 1;
      StringCchCopyW(v44, 0x104u, a5);
      v24 = *(_QWORD *)(*((_QWORD *)this + 4) + 104LL);
      v42 = (a4 != 0) + 1;
      ItemID = CItemIDFactory<tagARPITEM,1230000705>::s_CreateItemID(Buffer, ppv, a3, v24);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)ItemID;
}

```

## disassembly

```asm
0x180019340  mov     [rsp-8+arg_18], rbx
0x180019345  push    rbp
0x180019346  push    rsi
0x180019347  push    rdi
0x180019348  push    r12
0x18001934a  push    r13
0x18001934c  push    r14
0x18001934e  push    r15
0x180019350  lea     rbp, [rsp-830h]
0x180019358  sub     rsp, 930h
0x18001935f  mov     rax, cs:__security_cookie
0x180019366  xor     rax, rsp
0x180019369  mov     [rbp+860h+var_40], rax
0x180019370  mov     r12, [rbp+860h+arg_20]
0x180019377  mov     rbx, rdx
0x18001937a  mov     r13, rcx
0x18001937d  lea     rdx, [rsp+960h+ppv]; ppv
0x180019382  xor     esi, esi
0x180019384  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001938b  mov     [r8], rsi
0x18001938e  mov     r15d, r9d
0x180019391  mov     [rsp+960h+ppv], rsi
0x180019396  mov     r14, r8
0x180019399  call    cs:__imp_PSCreateMemoryPropertyStore
0x18001939f  mov     edi, eax
0x1800193a1  test    eax, eax
0x1800193a3  js      loc_18001987D
0x1800193a9  mov     rax, [rbx]
0x1800193ac  lea     r8, [rsp+960h+lpString1]
0x1800193b1  xor     edi, edi
0x1800193b3  mov     rcx, rbx
0x1800193b6  mov     [rsp+960h+lpString1], rdi
0x1800193bb  mov     rax, [rax+20h]
0x1800193bf  lea     esi, [rdi+2]
0x1800193c2  mov     edx, esi
0x1800193c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193c9  test    eax, eax
0x1800193cb  js      loc_18001952A
0x1800193d1  mov     r8, [rsp+960h+lpString1]; lpString1
0x1800193d6  test    r8, r8
0x1800193d9  jz      loc_18001952A
0x1800193df  cmp     [r8], di
0x1800193e3  jz      short loc_180019428
0x1800193e5  lea     rax, aDefault; "Default"
0x1800193ec  mov     [rsp+960h+cchCount2], 8; cchCount2
0x1800193f4  or      r9d, 0FFFFFFFFh; cchCount1
0x1800193f8  mov     [rsp+960h+lpString2], rax; lpString2
0x1800193fd  lea     edx, [rdi+1]; dwCmpFlags
0x180019400  lea     ecx, [rdi+7Fh]; Locale
0x180019403  call    cs:__imp_CompareStringW
0x180019409  cmp     eax, esi
0x18001940b  jz      short loc_180019428
0x18001940d  mov     r8, [rsp+960h+lpString1]
0x180019412  lea     rdx, PKEY_ItemNameDisplay
0x180019419  mov     rcx, [rsp+960h+ppv]
0x18001941e  call    IPropertyStore_SetString
0x180019423  jmp     loc_18001951F
0x180019428  mov     rax, [rbx]
0x18001942b  lea     r8, [rsp+960h+FileTime]
0x180019430  mov     edx, 8
0x180019435  mov     qword ptr [rsp+960h+FileTime.dwLowDateTime], rdi
0x18001943a  mov     rcx, rbx
0x18001943d  mov     rax, [rax+20h]
0x180019441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019446  test    eax, eax
0x180019448  js      loc_18001951F
0x18001944e  mov     rcx, qword ptr [rsp+960h+FileTime.dwLowDateTime]; lpString1
0x180019453  call    ?GetUpdateReleaseTypeID@@YAKPEBG@Z; GetUpdateReleaseTypeID(ushort const *)
0x180019458  test    eax, eax
0x18001945a  jz      loc_180019514
0x180019460  mov     rcx, cs:g_hinst; hInstance
0x180019467  lea     r8, [rbp+860h+Buffer]; lpBuffer
0x18001946b  mov     r9d, 104h; cchBufferMax
0x180019471  mov     edx, eax; uID
0x180019473  call    cs:__imp_LoadStringW
0x180019479  mov     rcx, cs:g_hinst; hInstance
0x180019480  lea     r8, [rbp+860h+var_460]; lpBuffer
0x180019487  mov     r9d, 104h; cchBufferMax
0x18001948d  mov     edx, 45h ; 'E'; uID
0x180019492  call    cs:__imp_LoadStringW
0x180019498  mov     rax, [rbx]
0x18001949b  lea     r8, [rsp+960h+pv]
0x1800194a0  mov     edx, 7
0x1800194a5  mov     [rsp+960h+pv], rdi
0x1800194aa  mov     rcx, rbx
0x1800194ad  mov     rax, [rax+20h]
0x1800194b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194b6  test    eax, eax
0x1800194b8  js      short loc_180019514
0x1800194ba  mov     rax, [rsp+960h+pv]
0x1800194bf  lea     r9, [rbp+860h+Buffer]
0x1800194c3  mov     rcx, cs:g_hinst
0x1800194ca  lea     r8, [rsp+960h+EndPtr]
0x1800194cf  mov     qword ptr [rsp+960h+cchCount2], rax
0x1800194d4  mov     edx, 44h ; 'D'
0x1800194d9  lea     rax, [rbp+860h+var_460]
0x1800194e0  mov     [rsp+960h+EndPtr], rdi
0x1800194e5  mov     [rsp+960h+lpString2], rax
0x1800194ea  call    SHFormatResMessageArgAlloc
0x1800194ef  test    eax, eax
0x1800194f1  js      short loc_180019509
0x1800194f3  mov     r8, [rsp+960h+EndPtr]
0x1800194f8  lea     rdx, PKEY_ItemNameDisplay
0x1800194ff  mov     rcx, [rsp+960h+ppv]
0x180019504  call    IPropertyStore_SetString
0x180019509  mov     rcx, [rsp+960h+pv]; pv
0x18001950e  call    cs:__imp_CoTaskMemFree
0x180019514  mov     rcx, qword ptr [rsp+960h+FileTime.dwLowDateTime]; pv
0x180019519  call    cs:__imp_CoTaskMemFree
0x18001951f  mov     rcx, [rsp+960h+lpString1]; pv
0x180019524  call    cs:__imp_CoTaskMemFree
0x18001952a  mov     rax, [rbx]
0x18001952d  lea     r8, [rsp+960h+var_900]
0x180019532  mov     edx, 0Ah
0x180019537  mov     [rsp+960h+var_900], rdi
0x18001953c  mov     rcx, rbx
0x18001953f  mov     rax, [rax+20h]
0x180019543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019548  test    eax, eax
0x18001954a  js      short loc_180019572
0x18001954c  mov     r8, [rsp+960h+var_900]
0x180019551  test    r8, r8
0x180019554  jz      short loc_180019572
0x180019556  mov     rcx, [rsp+960h+ppv]
0x18001955b  lea     rdx, PKEY_Software_ProductVersion
0x180019562  call    IPropertyStore_SetString
0x180019567  mov     rcx, [rsp+960h+var_900]; pv
0x18001956c  call    cs:__imp_CoTaskMemFree
0x180019572  mov     rax, [rbx]
0x180019575  lea     r8, [rsp+960h+var_8F8]
0x18001957a  mov     edx, 0Ch
0x18001957f  mov     [rsp+960h+var_8F8], rdi
0x180019584  mov     rcx, rbx
0x180019587  mov     rax, [rax+20h]
0x18001958b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019590  test    eax, eax
0x180019592  js      short loc_1800195BA
0x180019594  mov     r8, [rsp+960h+var_8F8]
0x180019599  test    r8, r8
0x18001959c  jz      short loc_1800195BA
0x18001959e  mov     rcx, [rsp+960h+ppv]
0x1800195a3  lea     rdx, PKEY_Software_Publisher
0x1800195aa  call    IPropertyStore_SetString
0x1800195af  mov     rcx, [rsp+960h+var_8F8]; pv
0x1800195b4  call    cs:__imp_CoTaskMemFree
0x1800195ba  mov     rax, [rbx]
0x1800195bd  lea     r8, [rsp+960h+var_8F0]
0x1800195c2  mov     edx, 9
0x1800195c7  mov     [rsp+960h+var_8F0], rdi
0x1800195cc  mov     rcx, rbx
0x1800195cf  mov     rax, [rax+20h]
0x1800195d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195d8  test    eax, eax
0x1800195da  js      short loc_180019602
0x1800195dc  mov     r8, [rsp+960h+var_8F0]
0x1800195e1  test    r8, r8
0x1800195e4  jz      short loc_180019602
0x1800195e6  mov     rcx, [rsp+960h+ppv]
0x1800195eb  lea     rdx, PKEY_Software_ProductID
0x1800195f2  call    IPropertyStore_SetString
0x1800195f7  mov     rcx, [rsp+960h+var_8F0]; pv
0x1800195fc  call    cs:__imp_CoTaskMemFree
0x180019602  mov     rax, [rbx]
0x180019605  lea     r8, [rsp+960h+var_8E8]
0x18001960a  mov     edx, 0Eh
0x18001960f  mov     [rsp+960h+var_8E8], rdi
0x180019614  mov     rcx, rbx
0x180019617  mov     rax, [rax+20h]
0x18001961b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019620  test    eax, eax
0x180019622  js      short loc_18001964A
0x180019624  mov     r8, [rsp+960h+var_8E8]
0x180019629  test    r8, r8
0x18001962c  jz      short loc_18001964A
0x18001962e  mov     rcx, [rsp+960h+ppv]
0x180019633  lea     rdx, PKEY_Software_SupportUrl
0x18001963a  call    IPropertyStore_SetString
0x18001963f  mov     rcx, [rsp+960h+var_8E8]; pv
0x180019644  call    cs:__imp_CoTaskMemFree
0x18001964a  mov     rax, [rbx]
0x18001964d  lea     r8, [rbp+860h+var_8E0]
0x180019651  mov     edx, 13h
0x180019656  mov     [rbp+860h+var_8E0], rdi
0x18001965a  mov     rcx, rbx
0x18001965d  mov     rax, [rax+20h]
0x180019661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019666  test    eax, eax
0x180019668  js      short loc_18001968E
0x18001966a  mov     r8, [rbp+860h+var_8E0]
0x18001966e  test    r8, r8
0x180019671  jz      short loc_18001968E
0x180019673  mov     rcx, [rsp+960h+ppv]
0x180019678  lea     rdx, PKEY_Software_InstallLocation
0x18001967f  call    IPropertyStore_SetString
0x180019684  mov     rcx, [rbp+860h+var_8E0]; pv
0x180019688  call    cs:__imp_CoTaskMemFree
0x18001968e  mov     rax, [rbx]
0x180019691  lea     r8, [rsp+960h+var_908]
0x180019696  mov     edx, 11h
0x18001969b  mov     [rsp+960h+var_908], rdi
0x1800196a0  mov     rcx, rbx
0x1800196a3  mov     rax, [rax+20h]
0x1800196a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196ac  test    eax, eax
0x1800196ae  js      loc_180019794
0x1800196b4  mov     r8, [rsp+960h+var_908]; unsigned __int16 *
0x1800196b9  test    r8, r8
0x1800196bc  jz      loc_180019794
0x1800196c2  mov     edx, 9; unsigned __int64
0x1800196c7  mov     qword ptr [rsp+960h+FileTime.dwLowDateTime], rdi
0x1800196cc  xorps   xmm0, xmm0
0x1800196cf  mov     [rsp+960h+pv], rdi
0x1800196d4  lea     rcx, [rbp+860h+String]; unsigned __int16 *
0x1800196d8  mov     [rsp+960h+EndPtr], rdi
0x1800196dd  movups  xmmword ptr [rbp+860h+SystemTime.wYear], xmm0
0x1800196e1  lea     r9d, [rdx-1]; unsigned __int64
0x1800196e5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800196ea  test    eax, eax
0x1800196ec  js      loc_180019789
0x1800196f2  mov     r8d, 10h; Radix
0x1800196f8  lea     rdx, [rsp+960h+EndPtr]; EndPtr
0x1800196fd  lea     rcx, [rbp+860h+String]; String
0x180019701  call    cs:__imp_wcstoul
0x180019707  mov     r8, [rsp+960h+var_908]
0x18001970c  lea     rcx, [rbp+860h+String]; unsigned __int16 *
0x180019710  mov     edx, 9; unsigned __int64
0x180019715  mov     [rsp+960h+FileTime.dwHighDateTime], eax
0x180019719  add     r8, 10h; unsigned __int16 *
0x18001971d  lea     r9d, [rdx-1]; unsigned __int64
0x180019721  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180019726  test    eax, eax
0x180019728  js      short loc_180019789
0x18001972a  mov     r8d, 10h; Radix
0x180019730  lea     rdx, [rsp+960h+EndPtr]; EndPtr
0x180019735  lea     rcx, [rbp+860h+String]; String
0x180019739  call    cs:__imp_wcstoul
0x18001973f  lea     rdx, [rsp+960h+pv]; lpLocalFileTime
0x180019744  mov     [rsp+960h+FileTime.dwLowDateTime], eax
0x180019748  lea     rcx, [rsp+960h+FileTime]; lpFileTime
0x18001974d  call    cs:__imp_FileTimeToLocalFileTime
0x180019753  test    eax, eax
0x180019755  jz      short loc_180019789
0x180019757  lea     rdx, [rbp+860h+SystemTime]; lpSystemTime
0x18001975b  lea     rcx, [rsp+960h+pv]; lpFileTime
0x180019760  call    cs:__imp_FileTimeToSystemTime
0x180019766  test    eax, eax
0x180019768  jz      short loc_180019789
0x18001976a  movaps  xmm0, xmmword ptr [rbp+860h+SystemTime.wYear]
0x18001976e  lea     r8, [rbp+860h+var_8D0]
0x180019772  mov     rcx, [rsp+960h+ppv]
0x180019777  movdqa  [rbp+860h+var_8D0], xmm0
0x18001977c  mov     dword ptr [rsp+960h+lpString2], 103h
0x180019784  call    IPropertyStore_SetSystemTime
0x180019789  mov     rcx, [rsp+960h+var_908]; pv
0x18001978e  call    cs:__imp_CoTaskMemFree
0x180019794  mov     rax, [rbx]
0x180019797  lea     r8, [rbp+860h+var_8D8]
0x18001979b  mov     edx, 0Bh
0x1800197a0  mov     [rbp+860h+var_8D8], rdi
0x1800197a4  mov     rcx, rbx
0x1800197a7  mov     rax, [rax+20h]
0x1800197ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197b0  mov     edi, eax
0x1800197b2  test    eax, eax
0x1800197b4  js      short loc_1800197F0
0x1800197b6  mov     r8, [rbp+860h+var_8D8]; lpString1
0x1800197ba  lea     rax, a1; "1"
0x1800197c1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800197c5  mov     [rsp+960h+cchCount2], r9d; cchCount2
0x1800197ca  mov     [rsp+960h+lpString2], rax; lpString2
0x1800197cf  lea     edx, [r9+2]; dwCmpFlags
0x1800197d3  lea     ecx, [rdx+7Eh]; Locale
0x1800197d6  call    cs:__imp_CompareStringW
0x1800197dc  mov     ecx, esi
0x1800197de  sub     ecx, eax
0x1800197e0  neg     ecx
0x1800197e2  mov     rcx, [rbp+860h+var_8D8]; pv
0x1800197e6  sbb     eax, eax
0x1800197e8  and     esi, eax
0x1800197ea  call    cs:__imp_CoTaskMemFree
0x1800197f0  mov     rcx, cs:g_hinst; hInstance
0x1800197f7  lea     r8, [rbp+860h+var_250]; lpBuffer
0x1800197fe  mov     ebx, 104h
0x180019803  mov     edx, 45h ; 'E'; uID
0x180019808  mov     r9d, ebx; cchBufferMax
0x18001980b  call    cs:__imp_LoadStringW
0x180019811  mov     rcx, [rsp+960h+ppv]
0x180019816  lea     r8, [rbp+860h+var_250]
0x18001981d  lea     rdx, PKEY_Software_ParentName
0x180019824  call    IPropertyStore_SetString
0x180019829  test    edi, edi
0x18001982b  js      short loc_18001987D
0x18001982d  xor     edx, edx; Val
0x18001982f  lea     rcx, [rbp+860h+var_884]; void *
0x180019833  mov     r8d, 418h; Size
0x180019839  call    memset_0
0x18001983e  mov     r8, r12; unsigned __int16 *
0x180019841  mov     dword ptr [rbp+860h+Buffer], esi
0x180019844  mov     edx, ebx; unsigned __int64
0x180019846  mov     [rbp+860h+var_888], 1
  ... truncated ...
```
