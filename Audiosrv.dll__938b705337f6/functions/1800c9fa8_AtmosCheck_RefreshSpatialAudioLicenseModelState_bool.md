# AtmosCheck::RefreshSpatialAudioLicenseModelState(bool *)

- ea: `0x1800c9fa8`
- end: `0x1800ca4b6`
- name: `?RefreshSpatialAudioLicenseModelState@AtmosCheck@@AEAAJPEA_N@Z`
- size: `1294`
- prototype: `__int64 __fastcall(AtmosCheck *__hidden this, bool *)`
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c9b9c`
- `0x1800c9d0c`
- `0x1800c9e60`
- `0x180155d24`

## callees

- `0x180001b94`
- `0x18000ca50`
- `0x18000cb50`
- `0x1800126bc`
- `0x18008db24`
- `0x1800c9fa8`
- `0x1800cf8c0`
- `0x1800cf8e4`
- `0x1800cfdc0`
- `0x180155440`
- `0x180155c3c`
- `0x180156880`
- `0x180156930`
- `0x180158154`
- `0x180158228`
- `0x180158750`
- `0x1801587c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c9fe3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c9fe3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca05d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca0ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca165`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca399`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca481`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca05d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca0ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca165`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca399`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca481`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca11c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca231`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca256`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca11c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca231`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ca256`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AtmosCheck::RefreshSpatialAudioLicenseModelState(AtmosCheck *this, bool *a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  int v4; // r14d
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r9d
  signed int i; // eax
  __int64 v11; // r13
  __int64 v12; // r14
  int updated; // edi
  __int64 v14; // rdx
  LPCWCH *v15; // r14
  __int64 v16; // rcx
  __int64 v17; // rdx
  const WCHAR *v18; // r9
  const WCHAR *v19; // rcx
  const WCHAR *v20; // rax
  LPCWCH v21; // rax
  const WCHAR *v22; // r8
  const WCHAR *v23; // r13
  const WCHAR *v24; // r13
  const WCHAR *v25; // rax
  LPCWCH v26; // r14
  __int64 v27; // rdx
  __int64 v28; // rdx
  char *v29; // r13
  int bIgnoreCase; // [rsp+20h] [rbp-1A8h]
  int bIgnoreCasea; // [rsp+20h] [rbp-1A8h]
  char v32; // [rsp+30h] [rbp-198h] BYREF
  char v33[3]; // [rsp+31h] [rbp-197h] BYREF
  signed int v34; // [rsp+34h] [rbp-194h]
  LPCWCH v35; // [rsp+38h] [rbp-190h]
  LPCWCH lpString2[2]; // [rsp+40h] [rbp-188h] BYREF
  unsigned __int64 v37; // [rsp+50h] [rbp-178h]
  unsigned __int64 v38; // [rsp+58h] [rbp-170h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-168h]
  bool *v40; // [rsp+68h] [rbp-160h]
  _BYTE v41[8]; // [rsp+70h] [rbp-158h] BYREF
  LPCWCH lpString1[35]; // [rsp+78h] [rbp-150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v40 = a2;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  lpCriticalSection = v3;
  v33[0] = *((_BYTE *)this + 217);
  `eh vector constructor iterator'(
    v41,
    0x28u,
    7u,
    (void (*)(void *))SpatialAudioFormatSubtypeInfo::SpatialAudioFormatSubtypeInfo,
    (void (*)(void *))SpatialAudioFormatSubtypeInfo::~SpatialAudioFormatSubtypeInfo);
  v4 = InitializeSpatialAudioFormatSubtypeInfoArray((struct SpatialAudioFormatSubtypeInfo *)v41);
  if ( v4 == 19 )
  {
    `eh vector destructor iterator'(
      v41,
      0x28u,
      7u,
      (void (*)(void *))SpatialAudioFormatSubtypeInfo::~SpatialAudioFormatSubtypeInfo);
    if ( v3 )
      LeaveCriticalSection(v3);
    return 19;
  }
  if ( v4 < 0 )
  {
    v6 = 2650;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\published\\audiocore\\lib\\atmoscheck\\atmoscheck.cpp",
      (const char *)(unsigned int)v4,
      bIgnoreCasea);
    `eh vector destructor iterator'(
      v41,
      0x28u,
      7u,
      (void (*)(void *))SpatialAudioFormatSubtypeInfo::~SpatialAudioFormatSubtypeInfo);
    if ( v3 )
      LeaveCriticalSection(v3);
    return (unsigned int)v4;
  }
  v4 = ScanForInstalledSpatialAudioSubtypeAppServices(
         (struct SpatialAudioFormatSubtypeInfo *)v41,
         7,
         (bool *)this + 217,
         (const struct _tlgProvider_t *)&CallbackContext);
  if ( v4 < 0 )
  {
    v6 = 2652;
    goto LABEL_7;
  }
  LOBYTE(v7) = 0;
  v32 = 0;
  for ( i = 0; ; i = v34 + 1 )
  {
    v34 = i;
    if ( (unsigned int)i >= 7 )
      break;
    v38 = i;
    v11 = 56LL * i;
    v12 = 5LL * i;
    if ( CompareStringOrdinal(lpString1[5 * i], -1, *(LPCWCH *)((char *)this + v11 + 296), -1, 1) != 2 )
    {
      updated = -2147418113;
      v14 = 2668;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"avcore\\published\\audiocore\\lib\\atmoscheck\\atmoscheck.cpp",
        (const char *)(unsigned int)updated,
        bIgnoreCasea);
      `eh vector destructor iterator'(
        v41,
        0x28u,
        7u,
        (void (*)(void *))SpatialAudioFormatSubtypeInfo::~SpatialAudioFormatSubtypeInfo);
      if ( v3 )
        LeaveCriticalSection(v3);
      return (unsigned int)updated;
    }
    v15 = &lpString1[v12 + 1];
    if ( *((_BYTE *)this + v11 + 272) != v41[40 * v38] )
      goto LABEL_36;
    v8 = *(_QWORD *)((char *)this + v11 + 304);
    v16 = *(_QWORD *)((char *)this + v11 + 312) - v8;
    if ( v16 != (char *)lpString1[5 * v38 + 2] - (char *)*v15 )
      goto LABEL_36;
    v7 = v16 >> 4;
    if ( v7 )
    {
      v7 = 0;
      v37 = 0;
      while ( 1 )
      {
        v17 = 2 * v7;
        v18 = &LocaleName;
        v19 = &LocaleName;
        if ( *(_QWORD *)(v8 + 8 * v17) )
          v19 = *(const WCHAR **)(v8 + 8 * v17);
        v20 = &LocaleName;
        if ( *(_QWORD *)(v8 + 8 * v17 + 8) )
          v20 = *(const WCHAR **)(v8 + 8 * v17 + 8);
        v35 = v20;
        v21 = *v15;
        v22 = &LocaleName;
        if ( *(_QWORD *)&(*v15)[4 * v17] )
          v22 = *(const WCHAR **)&v21[4 * v17];
        if ( *(_QWORD *)&v21[4 * v17 + 4] )
          v18 = *(const WCHAR **)&v21[4 * v17 + 4];
        lpString2[0] = v18;
        if ( CompareStringOrdinal(v19, -1, v22, -1, 1) != 2 || CompareStringOrdinal(v35, -1, lpString2[0], -1, 1) != 2 )
          break;
        v7 = v37 + 1;
        v37 = v7;
        v8 = *(_QWORD *)((char *)this + v11 + 304);
        if ( v7 >= (*(_QWORD *)((char *)this + v11 + 312) - v8) >> 4 )
          goto LABEL_34;
      }
LABEL_36:
      v32 = 1;
LABEL_37:
      v7 = v38;
      *((_BYTE *)this + v11 + 272) = v41[40 * v38];
      v23 = (const WCHAR *)((char *)this + v11 + 304);
      lpString2[0] = v23;
      v35 = (LPCWCH)(56 * v7);
      if ( *(_QWORD *)v23 != *((_QWORD *)this + 7 * v7 + 39) )
      {
        std::_Destroy_range<std::allocator<SpatialAudioAppDetails>>(*(SpatialAudioAppDetails **)v23);
        LODWORD(v7) = (_DWORD)v35;
        *(_QWORD *)((char *)this + (_QWORD)v35 + 312) = *(_QWORD *)v23;
      }
      v24 = *v15;
      v25 = v15[1];
      v35 = v25;
      v26 = lpString2[0];
      while ( 1 )
      {
        if ( v24 == v25 )
        {
          LOBYTE(v7) = v32;
          goto LABEL_46;
        }
        *(_OWORD *)lpString2 = 0;
        v27 = *(_QWORD *)v24;
        *(_QWORD *)v24 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          lpString2,
          v27);
        v28 = *((_QWORD *)v24 + 1);
        *((_QWORD *)v24 + 1) = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &lpString2[1],
          v28);
        try
        {
          std::vector<AtmosCheck::CommonSpatialTechInfo::SpatialTechAppDetails>::push_back(v26, lpString2);
          SpatialAudioAppDetails::~SpatialAudioAppDetails((SpatialAudioAppDetails *)lpString2);
          v24 += 8;
          v25 = v35;
        }
        catch ( std::exception )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAAF,
            (unsigned int)"avcore\\published\\audiocore\\lib\\atmoscheck\\atmoscheck.cpp",
            (const char *)0x8007000ELL,
            bIgnoreCase);
          SpatialAudioAppDetails::~SpatialAudioAppDetails((SpatialAudioAppDetails *)lpString2);
          `eh vector destructor iterator'(
            v41,
            0x28u,
            7u,
            (void (*)(void *))SpatialAudioFormatSubtypeInfo::~SpatialAudioFormatSubtypeInfo);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          return 2147942414LL;
        }
      }
    }
LABEL_34:
    LOBYTE(v7) = v32;
    if ( v32 )
      goto LABEL_37;
LABEL_46:
    ;
  }
  v29 = (char *)this + 217;
  if ( v33[0] != *((_BYTE *)this + 217) )
  {
    if ( *v29 )
    {
      std::_Hash<std::_Umap_traits<std::wstring,wistd::unique_ptr<AtmosCheck::EndpointSpecificSpatialTechInfo [0],wistd::default_delete<AtmosCheck::EndpointSpecificSpatialTechInfo [0]>>,std::_Uhash_compare<std::wstring,case_insensitive_hash,case_insensitive_equality>,std::allocator<std::pair<std::wstring const,wistd::unique_ptr<AtmosCheck::EndpointSpecificSpatialTechInfo [0],wistd::default_delete<AtmosCheck::EndpointSpecificSpatialTechInfo [0]>>>>,0>>::clear((char *)this + 664);
      v4 = AtmosCheck::InitializeAppServiceMode(this);
      if ( v4 < 0 )
      {
        v6 = 2748;
        goto LABEL_7;
      }
      updated = AtmosCheck::UpdateLicenseMapForAllEndpoints(this);
      if ( updated < 0 )
      {
        v14 = 2749;
        goto LABEL_16;
      }
    }
    else
    {
      AtmosCheck::InitializeLicenseMapLegacy(this);
      AtmosCheck::UninitializeAppServiceMode(this);
    }
    LOBYTE(v7) = v32;
  }
  if ( v40 )
    *v40 = v7;
  if ( CallbackContext > 5u )
  {
    v33[0] = *v29;
    v32 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
      v7,
      (unsigned int)&unk_1801AD503,
      v8,
      v9,
      (__int64)&v32,
      (__int64)v33);
  }
  `eh vector destructor iterator'(
    v41,
    0x28u,
    7u,
    (void (*)(void *))SpatialAudioFormatSubtypeInfo::~SpatialAudioFormatSubtypeInfo);
  if ( v3 )
    LeaveCriticalSection(v3);
  return 0;
}

```

## disassembly

```asm
0x1800c9fa8  mov     [rsp+arg_10], rbx
0x1800c9fad  mov     [rsp+arg_18], rsi
0x1800c9fb2  push    rdi
0x1800c9fb3  push    r12
0x1800c9fb5  push    r13
0x1800c9fb7  push    r14
0x1800c9fb9  push    r15
0x1800c9fbb  sub     rsp, 1A0h
0x1800c9fc2  mov     rax, cs:__security_cookie
0x1800c9fc9  xor     rax, rsp
0x1800c9fcc  mov     [rsp+1C8h+var_38], rax
0x1800c9fd4  mov     [rsp+1C8h+var_160], rdx
0x1800c9fd9  mov     rdi, rcx
0x1800c9fdc  lea     rbx, [rcx+38h]
0x1800c9fe0  mov     rcx, rbx; lpCriticalSection
0x1800c9fe3  call    cs:__imp_EnterCriticalSection
0x1800c9fe9  mov     [rsp+1C8h+lpCriticalSection], rbx
0x1800c9fee  lea     r13, [rdi+0D9h]
0x1800c9ff5  mov     al, [r13+0]
0x1800c9ff9  mov     [rsp+1C8h+var_197], al
0x1800c9ffd  lea     r15, ??1SpatialAudioFormatSubtypeInfo@@QEAA@XZ; SpatialAudioFormatSubtypeInfo::~SpatialAudioFormatSubtypeInfo(void)
0x1800ca004  mov     qword ptr [rsp+1C8h+bIgnoreCase], r15; int
0x1800ca009  lea     r9, ??0SpatialAudioFormatSubtypeInfo@@QEAA@XZ; void (*)(void *)
0x1800ca010  mov     esi, 7
0x1800ca015  mov     r8d, esi; unsigned __int64
0x1800ca018  lea     r12d, [rsi+21h]
0x1800ca01c  mov     edx, r12d; unsigned __int64
0x1800ca01f  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800ca024  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800ca029  nop
0x1800ca02a  mov     r8b, 1; bool
0x1800ca02d  mov     edx, esi; int
0x1800ca02f  lea     rcx, [rsp+1C8h+var_158]; struct SpatialAudioFormatSubtypeInfo *
0x1800ca034  call    ?InitializeSpatialAudioFormatSubtypeInfoArray@@YAJPEAUSpatialAudioFormatSubtypeInfo@@H_N@Z; InitializeSpatialAudioFormatSubtypeInfoArray(SpatialAudioFormatSubtypeInfo *,int,bool)
0x1800ca039  mov     r14d, eax
0x1800ca03c  cmp     eax, 13h
0x1800ca03f  jnz     short loc_1800CA06D
0x1800ca041  mov     r9, r15; void (*)(void *)
0x1800ca044  mov     r8d, esi; unsigned __int64
0x1800ca047  mov     edx, r12d; unsigned __int64
0x1800ca04a  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800ca04f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800ca054  nop
0x1800ca055  test    rbx, rbx
0x1800ca058  jz      short loc_1800CA063
0x1800ca05a  mov     rcx, rbx; lpCriticalSection
0x1800ca05d  call    cs:__imp_LeaveCriticalSection
0x1800ca063  mov     eax, 13h
0x1800ca068  jmp     loc_1800CA489
0x1800ca06d  test    r14d, r14d
0x1800ca070  jns     short loc_1800CA0B9
0x1800ca072  mov     edx, 0A5Ah; void *
0x1800ca077  mov     rcx, [rsp+1C8h]; this
0x1800ca07f  mov     r9d, r14d; char *
0x1800ca082  lea     r8, aAvcorePublishe; "avcore\\published\\audiocore\\lib\\atmo"...
0x1800ca089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca08e  nop
0x1800ca08f  mov     r9, r15; void (*)(void *)
0x1800ca092  mov     r8, rsi; unsigned __int64
0x1800ca095  mov     rdx, r12; unsigned __int64
0x1800ca098  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800ca09d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800ca0a2  nop
0x1800ca0a3  test    rbx, rbx
0x1800ca0a6  jz      short loc_1800CA0B1
0x1800ca0a8  mov     rcx, rbx; lpCriticalSection
0x1800ca0ab  call    cs:__imp_LeaveCriticalSection
0x1800ca0b1  mov     eax, r14d
0x1800ca0b4  jmp     loc_1800CA489
0x1800ca0b9  lea     r9, CallbackContext; struct _tlgProvider_t *
0x1800ca0c0  mov     r8, r13; bool *
0x1800ca0c3  mov     edx, esi; int
0x1800ca0c5  lea     rcx, [rsp+1C8h+var_158]; struct SpatialAudioFormatSubtypeInfo *
0x1800ca0ca  call    ?ScanForInstalledSpatialAudioSubtypeAppServices@@YAJPEAUSpatialAudioFormatSubtypeInfo@@HPEA_NPEBU_tlgProvider_t@@@Z; ScanForInstalledSpatialAudioSubtypeAppServices(SpatialAudioFormatSubtypeInfo *,int,bool *,_tlgProvider_t const *)
0x1800ca0cf  mov     r14d, eax
0x1800ca0d2  test    eax, eax
0x1800ca0d4  jns     short loc_1800CA0DD
0x1800ca0d6  mov     edx, 0A5Ch
0x1800ca0db  jmp     short loc_1800CA077
0x1800ca0dd  xor     cl, cl
0x1800ca0df  mov     [rsp+1C8h+var_198], cl
0x1800ca0e3  xor     eax, eax
0x1800ca0e5  mov     [rsp+1C8h+var_194], eax
0x1800ca0e9  cmp     eax, esi
0x1800ca0eb  jnb     loc_1800CA3B8
0x1800ca0f1  cdqe
0x1800ca0f3  mov     [rsp+1C8h+var_170], rax
0x1800ca0f8  imul    r13, rax, 38h ; '8'
0x1800ca0fc  lea     r14, [rax+rax*4]
0x1800ca100  mov     [rsp+1C8h+bIgnoreCase], 1; int
0x1800ca108  or      r9d, 0FFFFFFFFh; cchCount2
0x1800ca10c  mov     r8, [rdi+r13+128h]; lpString2
0x1800ca114  or      edx, r9d; cchCount1
0x1800ca117  mov     rcx, [rsp+r14*8+1C8h+lpString1]; lpString1
0x1800ca11c  call    cs:__imp_CompareStringOrdinal
0x1800ca122  cmp     eax, 2
0x1800ca125  jz      short loc_1800CA172
0x1800ca127  mov     edi, 8000FFFFh
0x1800ca12c  mov     edx, 0A6Ch; void *
0x1800ca131  lea     r8, aAvcorePublishe; "avcore\\published\\audiocore\\lib\\atmo"...
0x1800ca138  mov     r9d, edi; char *
0x1800ca13b  mov     rcx, [rsp+1C8h]; this
0x1800ca143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca148  nop
0x1800ca149  mov     r9, r15; void (*)(void *)
0x1800ca14c  mov     r8, rsi; unsigned __int64
0x1800ca14f  mov     rdx, r12; unsigned __int64
0x1800ca152  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800ca157  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800ca15c  nop
0x1800ca15d  test    rbx, rbx
0x1800ca160  jz      short loc_1800CA16B
0x1800ca162  mov     rcx, rbx; lpCriticalSection
0x1800ca165  call    cs:__imp_LeaveCriticalSection
0x1800ca16b  mov     eax, edi
0x1800ca16d  jmp     loc_1800CA489
0x1800ca172  lea     rax, [rsp+1C8h+var_148]
0x1800ca17a  lea     r14, [rax+r14*8]
0x1800ca17e  mov     rax, [rsp+1C8h+var_170]
0x1800ca183  lea     rdx, [rax+rax*4]
0x1800ca187  mov     al, [rsp+rdx*8+1C8h+var_158]
0x1800ca18b  cmp     [rdi+r13+110h], al
0x1800ca193  jnz     loc_1800CA29C
0x1800ca199  mov     r8, [rdi+r13+130h]
0x1800ca1a1  mov     rcx, [rdi+r13+138h]
0x1800ca1a9  sub     rcx, r8
0x1800ca1ac  mov     rax, [rsp+rdx*8+1C8h+var_140]
0x1800ca1b4  sub     rax, [r14]
0x1800ca1b7  cmp     rcx, rax
0x1800ca1ba  jnz     loc_1800CA29C
0x1800ca1c0  sar     rcx, 4
0x1800ca1c4  test    rcx, rcx
0x1800ca1c7  jz      loc_1800CA28E
0x1800ca1cd  xor     ecx, ecx
0x1800ca1cf  mov     [rsp+1C8h+var_178], rcx
0x1800ca1d4  mov     rdx, rcx
0x1800ca1d7  add     rdx, rdx
0x1800ca1da  lea     r9, LocaleName
0x1800ca1e1  mov     rcx, r9
0x1800ca1e4  cmp     qword ptr [r8+rdx*8], 0
0x1800ca1e9  cmovnz  rcx, [r8+rdx*8]; lpString1
0x1800ca1ee  mov     rax, r9
0x1800ca1f1  cmp     qword ptr [r8+rdx*8+8], 0
0x1800ca1f7  cmovnz  rax, [r8+rdx*8+8]
0x1800ca1fd  mov     [rsp+1C8h+var_190], rax
0x1800ca202  mov     rax, [r14]
0x1800ca205  mov     r8, r9
0x1800ca208  cmp     qword ptr [rax+rdx*8], 0
0x1800ca20d  cmovnz  r8, [rax+rdx*8]; lpString2
0x1800ca212  cmp     qword ptr [rax+rdx*8+8], 0
0x1800ca218  cmovnz  r9, [rax+rdx*8+8]
0x1800ca21e  mov     [rsp+1C8h+lpString2], r9
0x1800ca223  mov     [rsp+1C8h+bIgnoreCase], 1; bIgnoreCase
0x1800ca22b  or      edx, 0FFFFFFFFh; cchCount1
0x1800ca22e  mov     r9d, edx; cchCount2
0x1800ca231  call    cs:__imp_CompareStringOrdinal
0x1800ca237  cmp     eax, 2
0x1800ca23a  jnz     short loc_1800CA29C
0x1800ca23c  mov     [rsp+1C8h+bIgnoreCase], 1; bIgnoreCase
0x1800ca244  or      eax, 0FFFFFFFFh
0x1800ca247  mov     r9d, eax; cchCount2
0x1800ca24a  mov     r8, [rsp+1C8h+lpString2]; lpString2
0x1800ca24f  mov     edx, eax; cchCount1
0x1800ca251  mov     rcx, [rsp+1C8h+var_190]; lpString1
0x1800ca256  call    cs:__imp_CompareStringOrdinal
0x1800ca25c  cmp     eax, 2
0x1800ca25f  jnz     short loc_1800CA29C
0x1800ca261  mov     rcx, [rsp+1C8h+var_178]
0x1800ca266  inc     rcx
0x1800ca269  mov     [rsp+1C8h+var_178], rcx
0x1800ca26e  mov     r8, [rdi+r13+130h]
0x1800ca276  mov     rax, [rdi+r13+138h]
0x1800ca27e  sub     rax, r8
0x1800ca281  sar     rax, 4
0x1800ca285  cmp     rcx, rax
0x1800ca288  jb      loc_1800CA1D4
0x1800ca28e  mov     cl, [rsp+1C8h+var_198]
0x1800ca292  test    cl, cl
0x1800ca294  jz      loc_1800CA3AD
0x1800ca29a  jmp     short loc_1800CA2A1
0x1800ca29c  mov     [rsp+1C8h+var_198], 1
0x1800ca2a1  mov     rcx, [rsp+1C8h+var_170]
0x1800ca2a6  lea     rax, [rcx+rcx*4]
0x1800ca2aa  mov     al, [rsp+rax*8+1C8h+var_158]
0x1800ca2ae  mov     [rdi+r13+110h], al
0x1800ca2b6  add     r13, 130h
0x1800ca2bd  add     r13, rdi
0x1800ca2c0  mov     [rsp+1C8h+lpString2], r13
0x1800ca2c5  imul    rax, rcx, 38h ; '8'
0x1800ca2c9  mov     [rsp+1C8h+var_190], rax
0x1800ca2ce  mov     rdx, [rax+rdi+138h]
0x1800ca2d6  cmp     [r13+0], rdx
0x1800ca2da  jz      short loc_1800CA2F6
0x1800ca2dc  mov     rcx, [r13+0]; this
0x1800ca2e0  call    ??$_Destroy_range@V?$allocator@USpatialAudioAppDetails@@@std@@@std@@YAXPEAUSpatialAudioAppDetails@@QEAU1@AEAV?$allocator@USpatialAudioAppDetails@@@0@@Z; std::_Destroy_range<std::allocator<SpatialAudioAppDetails>>(SpatialAudioAppDetails *,SpatialAudioAppDetails * const,std::allocator<SpatialAudioAppDetails> &)
0x1800ca2e5  mov     rax, [r13+0]
0x1800ca2e9  mov     rcx, [rsp+1C8h+var_190]
0x1800ca2ee  mov     [rcx+rdi+138h], rax
0x1800ca2f6  mov     r13, [r14]
0x1800ca2f9  mov     rax, [r14+8]
0x1800ca2fd  mov     [rsp+1C8h+var_190], rax
0x1800ca302  mov     r14, [rsp+1C8h+lpString2]
0x1800ca307  cmp     r13, rax
0x1800ca30a  jz      loc_1800CA3A9
0x1800ca310  xorps   xmm0, xmm0
0x1800ca313  movdqu  xmmword ptr [rsp+1C8h+lpString2], xmm0
0x1800ca319  mov     rdx, [r13+0]
0x1800ca31d  mov     qword ptr [r13+0], 0
0x1800ca325  lea     rcx, [rsp+1C8h+lpString2]
0x1800ca32a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ca32f  mov     rdx, [r13+8]
0x1800ca333  mov     qword ptr [r13+8], 0
0x1800ca33b  lea     rcx, [rsp+1C8h+lpString2+8]
0x1800ca340  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ca345  nop
0x1800ca346  lea     rdx, [rsp+1C8h+lpString2]
0x1800ca34b  mov     rcx, r14
0x1800ca34e  call    ?push_back@?$vector@USpatialTechAppDetails@CommonSpatialTechInfo@AtmosCheck@@V?$allocator@USpatialTechAppDetails@CommonSpatialTechInfo@AtmosCheck@@@std@@@std@@QEAAX$$QEAUSpatialTechAppDetails@CommonSpatialTechInfo@AtmosCheck@@@Z; std::vector<AtmosCheck::CommonSpatialTechInfo::SpatialTechAppDetails>::push_back(AtmosCheck::CommonSpatialTechInfo::SpatialTechAppDetails &&)
0x1800ca353  nop
0x1800ca354  lea     rcx, [rsp+1C8h+lpString2]; this
0x1800ca359  call    ??1SpatialAudioAppDetails@@QEAA@XZ; SpatialAudioAppDetails::~SpatialAudioAppDetails(void)
0x1800ca35e  add     r13, 10h
0x1800ca362  mov     rax, [rsp+1C8h+var_190]
0x1800ca367  jmp     short loc_1800CA307
0x1800ca369  lea     rcx, [rsp+1C8h+lpString2]; this
0x1800ca36e  call    ??1SpatialAudioAppDetails@@QEAA@XZ; SpatialAudioAppDetails::~SpatialAudioAppDetails(void)
0x1800ca373  nop
0x1800ca374  lea     r9, ??1SpatialAudioFormatSubtypeInfo@@QEAA@XZ; void (*)(void *)
0x1800ca37b  mov     edx, 28h ; '('; unsigned __int64
0x1800ca380  lea     r8d, [rdx-21h]; unsigned __int64
0x1800ca384  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800ca389  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800ca38e  nop
0x1800ca38f  mov     rcx, [rsp+1C8h+lpCriticalSection]; lpCriticalSection
0x1800ca394  test    rcx, rcx
0x1800ca397  jz      short loc_1800CA39F
0x1800ca399  call    cs:__imp_LeaveCriticalSection
0x1800ca39f  mov     eax, 8007000Eh
0x1800ca3a4  jmp     loc_1800CA489
0x1800ca3a9  mov     cl, [rsp+1C8h+var_198]
0x1800ca3ad  mov     eax, [rsp+1C8h+var_194]
0x1800ca3b1  inc     eax
0x1800ca3b3  jmp     loc_1800CA0E5
0x1800ca3b8  lea     r13, [rdi+0D9h]
0x1800ca3bf  mov     al, [rsp+1C8h+var_197]
0x1800ca3c3  cmp     al, [r13+0]
0x1800ca3c7  jz      short loc_1800CA421
0x1800ca3c9  cmp     byte ptr [r13+0], 0
0x1800ca3ce  jz      short loc_1800CA40D
0x1800ca3d0  lea     rcx, [rdi+298h]
0x1800ca3d7  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@$$BY0A@UEndpointSpecificSpatialTechInfo@AtmosCheck@@U?$default_delete@$$BY0A@UEndpointSpecificSpatialTechInfo@AtmosCheck@@@wistd@@@wistd@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Ucase_insensitive_hash@@Ucase_insensitive_equality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@$$BY0A@UEndpointSpecificSpatialTechInfo@AtmosCheck@@U?$default_delete@$$BY0A@UEndpointSpecificSpatialTechInfo@AtmosCheck@@@wistd@@@wistd@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,wistd::unique_ptr<AtmosCheck::EndpointSpecificSpatialTechInfo [0],wistd::default_delete<AtmosCheck::EndpointSpecificSpatialTechInfo [0]>>,std::_Uhash_compare<std::wstring,case_insensitive_hash,case_insensitive_equality>,std::allocator<std::pair<std::wstring const,wistd::unique_ptr<AtmosCheck::EndpointSpecificSpatialTechInfo [0],wistd::default_delete<AtmosCheck::EndpointSpecificSpatialTechInfo [0]>>>>,0>>::clear(void)
0x1800ca3dc  mov     rcx, rdi; this
0x1800ca3df  call    ?InitializeAppServiceMode@AtmosCheck@@AEAAJXZ; AtmosCheck::InitializeAppServiceMode(void)
0x1800ca3e4  mov     r14d, eax
0x1800ca3e7  test    eax, eax
0x1800ca3e9  jns     short loc_1800CA3F5
0x1800ca3eb  mov     edx, 0ABCh
0x1800ca3f0  jmp     loc_1800CA077
0x1800ca3f5  mov     rcx, rdi; this
0x1800ca3f8  call    ?UpdateLicenseMapForAllEndpoints@AtmosCheck@@AEAAJXZ; AtmosCheck::UpdateLicenseMapForAllEndpoints(void)
0x1800ca3fd  mov     edi, eax
0x1800ca3ff  test    eax, eax
0x1800ca401  jns     short loc_1800CA41D
0x1800ca403  mov     edx, 0ABDh
0x1800ca408  jmp     loc_1800CA131
0x1800ca40d  mov     rcx, rdi; this
0x1800ca410  call    ?InitializeLicenseMapLegacy@AtmosCheck@@AEAAXXZ; AtmosCheck::InitializeLicenseMapLegacy(void)
0x1800ca415  mov     rcx, rdi; pv
0x1800ca418  call    ?UninitializeAppServiceMode@AtmosCheck@@AEAAXXZ; AtmosCheck::UninitializeAppServiceMode(void)
0x1800ca41d  mov     cl, [rsp+1C8h+var_198]
0x1800ca421  mov     rax, [rsp+1C8h+var_160]
0x1800ca426  test    rax, rax
0x1800ca429  jz      short loc_1800CA42D
0x1800ca42b  mov     [rax], cl
0x1800ca42d  mov     eax, cs:CallbackContext
0x1800ca433  cmp     eax, 5
0x1800ca436  jbe     short loc_1800CA465
0x1800ca438  mov     al, [r13+0]
0x1800ca43c  mov     [rsp+1C8h+var_197], al
0x1800ca440  mov     [rsp+1C8h+var_198], cl
0x1800ca444  lea     rax, [rsp+1C8h+var_197]
0x1800ca449  mov     [rsp+1C8h+var_1A0], rax
0x1800ca44e  lea     rax, [rsp+1C8h+var_198]
0x1800ca453  mov     qword ptr [rsp+1C8h+bIgnoreCase], rax
0x1800ca458  lea     rdx, unk_1801AD503
0x1800ca45f  call    ??$Write@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x1800ca464  nop
0x1800ca465  mov     r9, r15; void (*)(void *)
0x1800ca468  mov     r8, rsi; unsigned __int64
0x1800ca46b  mov     rdx, r12; unsigned __int64
0x1800ca46e  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800ca473  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800ca478  nop
0x1800ca479  test    rbx, rbx
0x1800ca47c  jz      short loc_1800CA487
0x1800ca47e  mov     rcx, rbx; lpCriticalSection
0x1800ca481  call    cs:__imp_LeaveCriticalSection
0x1800ca487  xor     eax, eax
0x1800ca489  mov     rcx, [rsp+1C8h+var_38]
0x1800ca491  xor     rcx, rsp; StackCookie
  ... truncated ...
```
