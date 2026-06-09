# ConfigProvider::DoEnumerate(CRequestContext *,_WSMAN_PLUGIN_REQUEST *,ulong,ushort const *,ushort const *,void *)

- ea: `0x180035734`
- end: `0x180035ed9`
- name: `?DoEnumerate@ConfigProvider@@QEAA_NPEAVCRequestContext@@PEAU_WSMAN_PLUGIN_REQUEST@@KPEBG2PEAX@Z`
- size: `1957`
- prototype: `bool __usercall@<al>(ConfigProvider *__hidden this@<rcx>, struct CRequestContext *@<rdx>, struct _WSMAN_PLUGIN_REQUEST *@<r8>, unsigned int@<r9d>, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010a510`

## callees

- `0x180005d10`
- `0x18000fc50`
- `0x180022c00`
- `0x180033dd0`
- `0x180033e10`
- `0x180034850`
- `0x180035010`
- `0x1800352ac`
- `0x1800355c0`
- `0x180035734`
- `0x180035ee0`
- `0x180035f80`
- `0x1800405d0`
- `0x18005d800`
- `0x1800621e0`
- `0x1800ce6a0`
- `0x180110190`
- `0x180112380`
- `0x180113270`
- `0x1801133b0`
- `0x18011a6d4`
- `0x18011db90`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003587d`
- `msvcrt!_wcsicmp` at `0x180035a9c`
- `msvcrt!_wcsicmp` at `0x18003587d`
- `msvcrt!_wcsicmp` at `0x180035a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035dfa`

## string_xrefs

- `0x180035a92`: `http://schemas.microsoft.com/wbem/wsman/1/config/listener`
- `0x180035b69`: `http://schemas.microsoft.com/wbem/wsman/1/config/listener`
- `0x180035baf`: `http://schemas.microsoft.com/wbem/wsman/1/config/listener`
- `0x180035873`: `http://schemas.microsoft.com/wbem/wsman/1/config/resource`
- `0x180035773`: `onecore\admin\wmi\wmx\providers\config\configprovider.cpp`
- `0x180035acc`: `onecore\admin\wmi\wmx\providers\config\configprovider.cpp`
- `0x180035c16`: `http://schemas.microsoft.com/wbem/wsman/1/config/plugin`
- `0x180035c33`: `http://schemas.microsoft.com/wbem/wsman/1/config/plugin`
- `0x180035bd2`: `http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping`
- `0x180035beb`: `http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping`
- `0x180035bf4`: `http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell`
- `0x180035c0d`: `http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell`
- `0x180035cb8`: `ConfigProvider::Pull`
- `0x180035e0d`: `CConfigManager::NextListener`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall ConfigProvider::DoEnumerate(
        ConfigProvider *this,
        struct CRequestContext *a2,
        struct _WSMAN_PLUGIN_REQUEST *a3,
        int a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        int *a7)
{
  RBUFFER *v11; // r12
  char v12; // r14
  const wchar_t *resourceUri; // rbx
  RBUFFER *v14; // rax
  int *v15; // rsi
  void *v16; // rcx
  void *v17; // rbx
  const wchar_t *v18; // rbx
  unsigned int v19; // esi
  bool v20; // bl
  PVOID *v21; // rcx
  unsigned int i; // ebx
  struct _CONFIG_NODE * near *v23; // rax
  wchar_t *v24; // r8
  CConfigManager *FirstConfigManagerForTable; // rax
  DWORD v26; // eax
  __int64 v28; // r10
  __int64 v29; // rax
  SBUFFER *v30; // rsi
  RBUFFER *v31; // rax
  RBUFFER *v32; // rbx
  RBUFFER *v33; // rbx
  DWORD LastError; // eax
  struct _CONFIG_NODE *v35; // [rsp+30h] [rbp-48h] BYREF
  RBUFFER *v36; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v37[3]; // [rsp+40h] [rbp-38h] BYREF
  void *v38[2]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v39; // [rsp+68h] [rbp-10h]
  int v40; // [rsp+C8h] [rbp+50h] BYREF

  v11 = 0;
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp", 357, L"357", 0x54Fu, 0);
    return 0;
  }
  if ( *(_DWORD *)this )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp", 358, L"358", 0x54Fu, a2);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp", 359, L"359", 0x54Fu, a2);
    return 0;
  }
  if ( (a4 & 0xFFFFFFCC) != 0 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp", 360, L"360", 0x54Fu, a2);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, this);
  *((_DWORD *)this + 4) = 5;
  v12 = 1;
  if ( !(unsigned int)ConfigProvider::ValidateUri(this, a2, a3, 1) )
    return 0;
  if ( a5 || a6 )
  {
    (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 72LL))(a2);
    return 0;
  }
  *((_DWORD *)this + 1) = a4;
  *(_DWORD *)this = 1;
  resourceUri = a3->resourceUri;
  if ( !resourceUri )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 139, L"139", 0x54Fu, 0);
  if ( _wcsicmp(resourceUri, L"http://schemas.microsoft.com/wbem/wsman/1/config/resource") )
  {
    v35 = 0;
    v18 = a3->resourceUri;
    if ( !v18 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 139, L"139", 0x54Fu, 0);
    if ( _wcsicmp(v18, L"http://schemas.microsoft.com/wbem/wsman/1/config/listener") )
    {
      if ( (unsigned int)StringCchEqualsCI(
                           (wchar_t *)a3->resourceUri,
                           (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping") )
      {
        v19 = 2;
        v24 = (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/service/certmapping";
      }
      else if ( (unsigned int)StringCchEqualsCI(
                                (wchar_t *)a3->resourceUri,
                                (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell") )
      {
        v19 = 3;
        v24 = (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/winrs/customremoteshell";
      }
      else
      {
        if ( !(unsigned int)StringCchEqualsCI(
                              (wchar_t *)a3->resourceUri,
                              (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/plugin") )
        {
          (*(void (__fastcall **)(struct CRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
            a2,
            2150858801LL,
            1077134173,
            L"Enumerate");
          return 0;
        }
        v19 = 4;
        v24 = (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/plugin";
      }
      v40 = v19;
      v20 = (unsigned int)ConfigProvider::LookupUri(this, a2, v24, &v35) == 1;
    }
    else
    {
      v19 = 1;
      v40 = 1;
      if ( *(_DWORD *)this )
      {
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, this);
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        for ( i = 0; i < 0xC; ++i )
        {
          v23 = (&g_cfgNodes)[i];
          a7 = (int *)v23;
          if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x200000) != 0 )
          {
            WPP_SF_S(v21[2], 33, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids, *v23);
            v23 = (struct _CONFIG_NODE * near *)a7;
          }
          if ( (unsigned int)StringCchEqualsCI(
                               (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/config/listener",
                               (wchar_t *)*v23) )
          {
            v35 = (struct _CONFIG_NODE *)(&g_cfgNodes)[i];
            v20 = 1;
            v11 = 0;
            goto LABEL_68;
          }
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        v11 = 0;
        v20 = 0;
        (*(void (__fastcall **)(struct CRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 64LL))(
          a2,
          2150858811LL,
          1077134222,
          L"http://schemas.microsoft.com/wbem/wsman/1/config/listener");
      }
      else
      {
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\configprovider.cpp",
          1477,
          L"1477",
          0x54Fu,
          0);
        v20 = 0;
      }
    }
LABEL_68:
    if ( v20 )
    {
      FirstConfigManagerForTable = CConfigManager::GetFirstConfigManagerForTable(v19, 0);
      AutoRelease<CServiceConfigCache>::operator=((char *)this + 8, FirstConfigManagerForTable);
      if ( *((_QWORD *)this + 1) )
      {
        LODWORD(a7) = 0;
        v37[0] = &a7;
        v29 = WSManMemory::Alloc(2592, 0, 0);
        v30 = (SBUFFER *)v29;
        v37[0] = v29;
        if ( v29 )
        {
          *(_DWORD *)(v29 + 2576) &= ~1u;
          *(_DWORD *)(v29 + 2576) |= 2u;
          *(_QWORD *)v29 = v29 + 12;
          *(_WORD *)(v29 + 12) = 0;
          *(_DWORD *)(v29 + 8) = 2560;
          *(_DWORD *)(v29 + 2584) = 0;
        }
        else
        {
          v30 = 0;
        }
        v37[0] = v30;
        v36 = 0;
        if ( !v30 )
          goto LABEL_95;
        LODWORD(a7) = 0;
        v37[1] = &a7;
        v31 = (RBUFFER *)WSManMemory::Alloc(2592, 0, 0);
        v32 = v31;
        v37[2] = v31;
        if ( v31 )
        {
          RBUFFER::RBUFFER(v31, 0);
          *((_DWORD *)v32 + 646) = 0;
        }
        else
        {
          v32 = 0;
        }
        AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::operator=(&v36, v32);
        v33 = v36;
        if ( v36 )
        {
          if ( v40 == 1 )
            v11 = v36;
          while ( 1 )
          {
            SBUFFER::SetSizeInUse(v30, 0);
            **(_WORD **)v30 = 0;
            SBUFFER::SetSizeInUse(v33, 0);
            **(_WORD **)v33 = 0;
            if ( !ConfigProvider::GenerateItem(this, v35, a2, v30, v11) )
              break;
            if ( !ConfigProvider::DeliverItem(this, a2, a3, v30, v11) )
              goto LABEL_92;
            if ( !(unsigned int)CConfigManager::NextRow(*((CConfigManager **)this + 1)) )
            {
              LastError = GetLastError();
              if ( LastError != 259 )
              {
                (*(void (__fastcall **)(struct CRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
                  a2,
                  1077134176,
                  L"CConfigManager::NextListener",
                  LastError);
LABEL_92:
                v12 = 0;
              }
              AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&v36);
              AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(v37);
              return v12;
            }
          }
          RBUFFER::~RBUFFER(v33);
          WSManMemory::Free(v33, 0);
          RBUFFER::~RBUFFER(v30);
          WSManMemory::Free(v30, 0);
        }
        else
        {
LABEL_95:
          (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
          AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&v36);
          AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(v37);
        }
      }
      else
      {
        v26 = GetLastError();
        if ( v26 == 259 )
          return v12;
        v28 = *(_QWORD *)a2;
        if ( v26 == 5 )
        {
          (*(void (__fastcall **)(struct CRequestContext *))(v28 + 32))(a2);
        }
        else if ( v26 == -2144108539 )
        {
          (*(void (__fastcall **)(struct CRequestContext *))(v28 + 72))(a2);
        }
        else
        {
          (*(void (__fastcall **)(struct CRequestContext *, __int64, const wchar_t *, _QWORD))(v28 + 88))(
            a2,
            1077134176,
            L"ConfigProvider::Pull",
            v26);
        }
      }
    }
  }
  else
  {
    *(_OWORD *)v38 = 0;
    v39 = 0;
    if ( !(unsigned __int8)EnumServiceUserResources(0, v38, a2) )
    {
      v16 = v38[0];
      if ( !v38[0] )
        return 0;
      goto LABEL_27;
    }
    v40 = 0;
    a7 = &v40;
    v14 = (RBUFFER *)WSManMemory::Alloc(2592, 0, 0);
    v15 = (int *)v14;
    v37[0] = v14;
    if ( v14 )
    {
      RBUFFER::RBUFFER(v14, 0);
      v15[646] = 0;
    }
    else
    {
      v15 = 0;
    }
    a7 = v15;
    if ( v15 )
    {
      v17 = v38[0];
      while ( 1 )
      {
        if ( (unsigned __int64)v11 >= ((char *)v38[1] - (char *)v17) >> 3 )
        {
          AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&a7);
          if ( v17 )
            WSManMemory::Free(v17, 0);
          return v12;
        }
        if ( (int)TSTRBUFFER::Copy((TSTRBUFFER *)v15, *((const unsigned __int16 **)v17 + (_QWORD)v11)) < 0 )
          break;
        if ( !ConfigProvider::DeliverItem(this, a2, a3, (struct TSTRBUFFER *)v15, 0) )
        {
          AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&a7);
          if ( !v17 )
            return 0;
          goto LABEL_34;
        }
        v11 = (RBUFFER *)((char *)v11 + 1);
      }
      (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids);
      AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&a7);
      if ( v17 )
      {
LABEL_34:
        WSManMemory::Free(v17, 0);
        return 0;
      }
      return 0;
    }
    (*(void (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids);
    AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(&a7);
    v16 = v38[0];
    if ( v38[0] )
LABEL_27:
      WSManMemory::Free(v16, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180035734  push    rbp
0x180035736  push    rbx
0x180035737  push    rsi
0x180035738  push    rdi
0x180035739  push    r12
0x18003573b  push    r13
0x18003573d  push    r14
0x18003573f  push    r15
0x180035741  mov     rbp, rsp
0x180035744  sub     rsp, 78h
0x180035748  mov     ebx, r9d
0x18003574b  mov     r13, r8
0x18003574e  mov     rdi, rdx
0x180035751  mov     r15, rcx
0x180035754  xor     r12d, r12d
0x180035757  test    rdx, rdx
0x18003575a  jnz     short loc_180035784
0x18003575c  mov     [rsp+78h+var_58], r12; struct IRequestContext *
0x180035761  lea     r8, a357; "357"
0x180035768  mov     edx, 165h; unsigned int
0x18003576d  mov     r9d, 54Fh; unsigned int
0x180035773  lea     rcx, aOnecoreAdminWm_139; "onecore\\admin\\wmi\\wmx\\providers\\co"...
0x18003577a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003577f  jmp     loc_180035EC6
0x180035784  cmp     [rcx], r12d
0x180035787  jz      short loc_18003579C
0x180035789  mov     [rsp+78h+var_58], rdi
0x18003578e  lea     r8, a358; "358"
0x180035795  mov     edx, 166h
0x18003579a  jmp     short loc_18003576D
0x18003579c  test    r13, r13
0x18003579f  jnz     short loc_1800357B4
0x1800357a1  mov     [rsp+78h+var_58], rdi
0x1800357a6  lea     r8, a359; "359"
0x1800357ad  mov     edx, 167h
0x1800357b2  jmp     short loc_18003576D
0x1800357b4  test    ebx, 0FFFFFFCCh
0x1800357ba  jz      short loc_1800357CF
0x1800357bc  mov     [rsp+78h+var_58], rdi
0x1800357c1  lea     r8, a360; "360"
0x1800357c8  mov     edx, 168h
0x1800357cd  jmp     short loc_18003576D
0x1800357cf  lea     rax, WPP_GLOBAL_Control
0x1800357d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357dd  cmp     rcx, rax
0x1800357e0  jz      short loc_180035803
0x1800357e2  test    dword ptr [rcx+1Ch], 200000h
0x1800357e9  jz      short loc_180035803
0x1800357eb  mov     edx, 0Dh
0x1800357f0  mov     r9, r15
0x1800357f3  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x1800357fa  mov     rcx, [rcx+10h]
0x1800357fe  call    WPP_SF_q
0x180035803  mov     dword ptr [r15+10h], 5
0x18003580b  mov     r14d, 1
0x180035811  mov     r9d, r14d; int
0x180035814  mov     r8, r13; struct _WSMAN_PLUGIN_REQUEST *
0x180035817  mov     rdx, rdi; struct IRequestContext *
0x18003581a  mov     rcx, r15; this
0x18003581d  call    ?ValidateUri@ConfigProvider@@AEAAHPEAVIRequestContext@@PEAU_WSMAN_PLUGIN_REQUEST@@H@Z; ConfigProvider::ValidateUri(IRequestContext *,_WSMAN_PLUGIN_REQUEST *,int)
0x180035822  test    eax, eax
0x180035824  jz      loc_180035EC6
0x18003582a  cmp     [rbp+arg_20], r12
0x18003582e  jnz     loc_180035EB2
0x180035834  cmp     [rbp+arg_28], r12
0x180035838  jnz     loc_180035EB2
0x18003583e  mov     [r15+4], ebx
0x180035842  mov     [r15], r14d
0x180035845  mov     rbx, [r13+10h]
0x180035849  mov     esi, 8Bh
0x18003584e  test    rbx, rbx
0x180035851  jnz     short loc_180035873
0x180035853  mov     [rsp+78h+var_58], r12; struct IRequestContext *
0x180035858  mov     r9d, 54Fh; unsigned int
0x18003585e  lea     r8, a139; "139"
0x180035865  mov     edx, esi; unsigned int
0x180035867  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x18003586e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180035873  lea     rdx, aHttpSchemasMic_24; "http://schemas.microsoft.com/wbem/wsman"...
0x18003587a  mov     rcx, rbx; String1
0x18003587d  call    cs:__imp__wcsicmp
0x180035883  test    eax, eax
0x180035885  jnz     loc_180035A65
0x18003588b  xorps   xmm0, xmm0
0x18003588e  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180035893  mov     [rbp+var_10], r12
0x180035897  mov     r8, rdi
0x18003589a  lea     rdx, [rbp+var_20]
0x18003589e  xor     ecx, ecx
0x1800358a0  call    EnumServiceUserResources
0x1800358a5  test    al, al
0x1800358a7  jz      loc_180035A4B
0x1800358ad  mov     [rbp+arg_8], r12d
0x1800358b1  lea     rax, [rbp+arg_8]
0x1800358b5  mov     [rbp+arg_30], rax
0x1800358b9  xor     r8d, r8d
0x1800358bc  xor     edx, edx
0x1800358be  mov     ecx, 0A20h
0x1800358c3  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800358c8  mov     rsi, rax
0x1800358cb  mov     [rbp+var_38], rax
0x1800358cf  test    rax, rax
0x1800358d2  jz      short loc_1800358E7
0x1800358d4  xor     edx, edx; unsigned int
0x1800358d6  mov     rcx, rax; this
0x1800358d9  call    ??0RBUFFER@@QEAA@I@Z; RBUFFER::RBUFFER(uint)
0x1800358de  mov     [rsi+0A18h], r12d
0x1800358e5  jmp     short loc_1800358EA
0x1800358e7  mov     rsi, r12
0x1800358ea  mov     [rbp+arg_30], rsi
0x1800358ee  test    rsi, rsi
0x1800358f1  jnz     short loc_180035956
0x1800358f3  mov     rax, [rdi]
0x1800358f6  mov     rcx, rdi
0x1800358f9  mov     rax, [rax+18h]
0x1800358fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035902  mov     rcx, cs:WPP_GLOBAL_Control
0x180035909  lea     rax, WPP_GLOBAL_Control
0x180035910  cmp     rcx, rax
0x180035913  jz      short loc_180035932
0x180035915  test    dword ptr [rcx+1Ch], 400000h
0x18003591c  jz      short loc_180035932
0x18003591e  lea     edx, [rsi+0Eh]
0x180035921  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x180035928  mov     rcx, [rcx+10h]
0x18003592c  call    WPP_SF_
0x180035931  nop
0x180035932  lea     rcx, [rbp+arg_30]
0x180035936  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VTSTRBUFFER@@@@PEAVTSTRBUFFER@@@@AEAAXXZ; AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(void)
0x18003593b  nop
0x18003593c  mov     rcx, [rbp+var_20]; void *
0x180035940  test    rcx, rcx
0x180035943  jz      loc_180035EC6
0x180035949  xor     edx, edx; int
0x18003594b  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180035950  nop
0x180035951  jmp     loc_180035EC6
0x180035956  mov     rbx, [rbp+var_20]
0x18003595a  mov     rax, [rbp+var_20+8]
0x18003595e  sub     rax, rbx
0x180035961  sar     rax, 3
0x180035965  cmp     r12, rax
0x180035968  jnb     loc_180035A28
0x18003596e  mov     rdx, [rbx+r12*8]; Src
0x180035972  mov     rcx, rsi; this
0x180035975  call    ?Copy@TSTRBUFFER@@QEAAJPEBG@Z; TSTRBUFFER::Copy(ushort const *)
0x18003597a  test    eax, eax
0x18003597c  js      short loc_1800359C4
0x18003597e  mov     [rsp+78h+var_58], 0; struct TSTRBUFFER *
0x180035987  mov     r9, rsi; struct TSTRBUFFER *
0x18003598a  mov     r8, r13; struct _WSMAN_PLUGIN_REQUEST *
0x18003598d  mov     rdx, rdi; struct IRequestContext *
0x180035990  mov     rcx, r15; this
0x180035993  call    ?DeliverItem@ConfigProvider@@AEAA_NPEAVIRequestContext@@PEAU_WSMAN_PLUGIN_REQUEST@@PEAVTSTRBUFFER@@2@Z; ConfigProvider::DeliverItem(IRequestContext *,_WSMAN_PLUGIN_REQUEST *,TSTRBUFFER *,TSTRBUFFER *)
0x180035998  test    al, al
0x18003599a  jz      short loc_1800359A1
0x18003599c  add     r12, r14
0x18003599f  jmp     short loc_18003595A
0x1800359a1  lea     rcx, [rbp+arg_30]
0x1800359a5  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VTSTRBUFFER@@@@PEAVTSTRBUFFER@@@@AEAAXXZ; AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(void)
0x1800359aa  nop
0x1800359ab  test    rbx, rbx
0x1800359ae  jz      loc_180035EC6
0x1800359b4  xor     edx, edx; int
0x1800359b6  mov     rcx, rbx; void *
0x1800359b9  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x1800359be  nop
0x1800359bf  jmp     loc_180035EC6
0x1800359c4  mov     rax, [rdi]
0x1800359c7  mov     rcx, rdi
0x1800359ca  mov     rax, [rax+18h]
0x1800359ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800359da  lea     rax, WPP_GLOBAL_Control
0x1800359e1  cmp     rcx, rax
0x1800359e4  jz      short loc_180035A05
0x1800359e6  test    dword ptr [rcx+1Ch], 400000h
0x1800359ed  jz      short loc_180035A05
0x1800359ef  mov     edx, 0Fh
0x1800359f4  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x1800359fb  mov     rcx, [rcx+10h]
0x1800359ff  call    WPP_SF_
0x180035a04  nop
0x180035a05  lea     rcx, [rbp+arg_30]
0x180035a09  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VTSTRBUFFER@@@@PEAVTSTRBUFFER@@@@AEAAXXZ; AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(void)
0x180035a0e  nop
0x180035a0f  test    rbx, rbx
0x180035a12  jz      loc_180035EC6
0x180035a18  xor     edx, edx; int
0x180035a1a  mov     rcx, rbx; void *
0x180035a1d  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180035a22  nop
0x180035a23  jmp     loc_180035EC6
0x180035a28  lea     rcx, [rbp+arg_30]
0x180035a2c  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDelete@VTSTRBUFFER@@@@PEAVTSTRBUFFER@@@@AEAAXXZ; AutoCleanup<AutoDelete<TSTRBUFFER>,TSTRBUFFER *>::ReleasePtr(void)
0x180035a31  nop
0x180035a32  test    rbx, rbx
0x180035a35  jz      loc_180035C82
0x180035a3b  xor     edx, edx; int
0x180035a3d  mov     rcx, rbx; void *
0x180035a40  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180035a45  nop
0x180035a46  jmp     loc_180035C82
0x180035a4b  mov     rcx, [rbp+var_20]; void *
0x180035a4f  test    rcx, rcx
0x180035a52  jz      loc_180035EC6
0x180035a58  xor     edx, edx; int
0x180035a5a  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x180035a5f  nop
0x180035a60  jmp     loc_180035EC6
0x180035a65  mov     [rbp+var_48], r12
0x180035a69  mov     rbx, [r13+10h]
0x180035a6d  test    rbx, rbx
0x180035a70  jnz     short loc_180035A92
0x180035a72  mov     [rsp+78h+var_58], r12; struct IRequestContext *
0x180035a77  mov     r9d, 54Fh; unsigned int
0x180035a7d  lea     r8, a139; "139"
0x180035a84  mov     edx, esi; unsigned int
0x180035a86  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x180035a8d  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180035a92  lea     rdx, aHttpSchemasMic_3; "http://schemas.microsoft.com/wbem/wsman"...
0x180035a99  mov     rcx, rbx; String1
0x180035a9c  call    cs:__imp__wcsicmp
0x180035aa2  test    eax, eax
0x180035aa4  jnz     loc_180035BD2
0x180035aaa  mov     esi, r14d
0x180035aad  mov     [rbp+arg_8], r14d
0x180035ab1  cmp     [r15], r12d
0x180035ab4  jnz     short loc_180035AE0
0x180035ab6  mov     [rsp+78h+var_58], r12; struct IRequestContext *
0x180035abb  mov     r9d, 54Fh; unsigned int
0x180035ac1  lea     r8, a1477; "1477"
0x180035ac8  lea     edx, [r9+76h]; unsigned int
0x180035acc  lea     rcx, aOnecoreAdminWm_139; "onecore\\admin\\wmi\\wmx\\providers\\co"...
0x180035ad3  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180035ad8  mov     ebx, r12d
0x180035adb  jmp     loc_180035C52
0x180035ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ae7  lea     rdx, WPP_GLOBAL_Control
0x180035aee  cmp     rcx, rdx
0x180035af1  jz      short loc_180035B22
0x180035af3  test    dword ptr [rcx+1Ch], 200000h
0x180035afa  jz      short loc_180035B22
0x180035afc  mov     edx, 20h ; ' '
0x180035b01  mov     r9, r15
0x180035b04  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x180035b0b  mov     rcx, [rcx+10h]
0x180035b0f  call    WPP_SF_q
0x180035b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b1b  lea     rdx, WPP_GLOBAL_Control
0x180035b22  mov     ebx, r12d
0x180035b25  cmp     ebx, 0Ch
0x180035b28  jnb     short loc_180035BA6
0x180035b2a  mov     r12d, ebx
0x180035b2d  lea     rax, ?g_cfgNodes@@3PAPEAU_CONFIG_NODE@@A; _CONFIG_NODE * near * g_cfgNodes
0x180035b34  mov     rax, [rax+r12*8]
0x180035b38  mov     [rbp+arg_30], rax
0x180035b3c  cmp     rcx, rdx
0x180035b3f  jz      short loc_180035B66
0x180035b41  test    dword ptr [rcx+1Ch], 200000h
0x180035b48  jz      short loc_180035B66
0x180035b4a  mov     edx, 21h ; '!'
0x180035b4f  mov     r9, [rax]
0x180035b52  lea     r8, WPP_868caef4ad22380d860e92f3669fb8c6_Traceguids
0x180035b59  mov     rcx, [rcx+10h]
0x180035b5d  call    WPP_SF_S
0x180035b62  mov     rax, [rbp+arg_30]
0x180035b66  mov     rdx, [rax]; String2
0x180035b69  lea     rcx, aHttpSchemasMic_3; "http://schemas.microsoft.com/wbem/wsman"...
0x180035b70  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180035b75  test    eax, eax
0x180035b77  jnz     short loc_180035B8C
0x180035b79  add     ebx, r14d
0x180035b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b83  lea     rdx, WPP_GLOBAL_Control
0x180035b8a  jmp     short loc_180035B25
0x180035b8c  lea     rax, ?g_cfgNodes@@3PAPEAU_CONFIG_NODE@@A; _CONFIG_NODE * near * g_cfgNodes
0x180035b93  mov     rax, [rax+r12*8]
0x180035b97  mov     [rbp+var_48], rax
0x180035b9b  mov     ebx, r14d
0x180035b9e  xor     r12d, r12d
0x180035ba1  jmp     loc_180035C52
0x180035ba6  xor     r12d, r12d
0x180035ba9  mov     ebx, r12d
0x180035bac  mov     rax, [rdi]
0x180035baf  lea     r9, aHttpSchemasMic_3; "http://schemas.microsoft.com/wbem/wsman"...
0x180035bb6  mov     edx, 8033803Bh
0x180035bbb  mov     r8d, 4033C38Eh
0x180035bc1  mov     rcx, rdi
0x180035bc4  mov     rax, [rax+40h]
0x180035bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bcd  jmp     loc_180035C52
0x180035bd2  lea     rdx, aHttpSchemasMic_45; "http://schemas.microsoft.com/wbem/wsman"...
0x180035bd9  mov     rcx, [r13+10h]; String1
0x180035bdd  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180035be2  test    eax, eax
0x180035be4  jz      short loc_180035BF4
0x180035be6  mov     esi, 2
0x180035beb  lea     r8, aHttpSchemasMic_45; "http://schemas.microsoft.com/wbem/wsman"...
0x180035bf2  jmp     short loc_180035C3A
  ... truncated ...
```
