# AtmosCheck::RefreshSpatialAudioLicenseModelState(bool *)

- ea: `0x1800c7de8`
- end: `0x1800c82f6`
- name: `?RefreshSpatialAudioLicenseModelState@AtmosCheck@@AEAAJPEA_N@Z`
- size: `1294`
- prototype: `__int64 __fastcall(AtmosCheck *__hidden this, bool *)`
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c79dc`
- `0x1800c7b4c`
- `0x1800c7ca0`
- `0x180156a34`

## callees

- `0x180001b94`
- `0x18000cba0`
- `0x18000cca0`
- `0x18001280c`
- `0x18008dbd0`
- `0x1800c7de8`
- `0x1800cd8d0`
- `0x1800cd8f4`
- `0x1800cddd0`
- `0x180156150`
- `0x18015694c`
- `0x180157590`
- `0x180157640`
- `0x180158e64`
- `0x180158f38`
- `0x180159460`
- `0x1801594d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c7e23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c7e23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c7e9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c7eeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c7fa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c81d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c82c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c7e9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c7eeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c7fa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c81d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c82c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c7f5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c8071`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c8096`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c7f5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c8071`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c8096`

## pseudocode

```c
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
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          std::vector<AtmosCheck::CommonSpatialTechInfo::SpatialTechAppDetails>::push_back(v26, lpString2);
          SpatialAudioAppDetails::~SpatialAudioAppDetails((SpatialAudioAppDetails *)lpString2);
          v24 += 8;
          v25 = v35;
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xAAF,
              (unsigned int)"avcore\\published\\audiocore\\lib\\atmoscheck\\atmoscheck.cpp",
              (const char *)0x8007000ELL,
              bIgnoreCase);
            __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_1800C81A9);
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
      (int)byte_1801AE723,
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
0x1800c7de8  mov     [rsp+arg_10], rbx
0x1800c7ded  mov     [rsp+arg_18], rsi
0x1800c7df2  push    rdi
0x1800c7df3  push    r12
0x1800c7df5  push    r13
0x1800c7df7  push    r14
0x1800c7df9  push    r15
0x1800c7dfb  sub     rsp, 1A0h
0x1800c7e02  mov     rax, cs:__security_cookie
0x1800c7e09  xor     rax, rsp
0x1800c7e0c  mov     [rsp+1C8h+var_38], rax
0x1800c7e14  mov     [rsp+1C8h+var_160], rdx
0x1800c7e19  mov     rdi, rcx
0x1800c7e1c  lea     rbx, [rcx+38h]
0x1800c7e20  mov     rcx, rbx; lpCriticalSection
0x1800c7e23  call    cs:__imp_EnterCriticalSection
0x1800c7e29  mov     [rsp+1C8h+lpCriticalSection], rbx
0x1800c7e2e  lea     r13, [rdi+0D9h]
0x1800c7e35  mov     al, [r13+0]
0x1800c7e39  mov     [rsp+1C8h+var_197], al
0x1800c7e3d  lea     r15, ??1SpatialAudioFormatSubtypeInfo@@QEAA@XZ; SpatialAudioFormatSubtypeInfo::~SpatialAudioFormatSubtypeInfo(void)
0x1800c7e44  mov     qword ptr [rsp+1C8h+bIgnoreCase], r15; int
0x1800c7e49  lea     r9, ??0SpatialAudioFormatSubtypeInfo@@QEAA@XZ; void (*)(void *)
0x1800c7e50  mov     esi, 7
0x1800c7e55  mov     r8d, esi; unsigned __int64
0x1800c7e58  lea     r12d, [rsi+21h]
0x1800c7e5c  mov     edx, r12d; unsigned __int64
0x1800c7e5f  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800c7e64  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800c7e69  nop
0x1800c7e6a  mov     r8b, 1; bool
0x1800c7e6d  mov     edx, esi; int
0x1800c7e6f  lea     rcx, [rsp+1C8h+var_158]; struct SpatialAudioFormatSubtypeInfo *
0x1800c7e74  call    ?InitializeSpatialAudioFormatSubtypeInfoArray@@YAJPEAUSpatialAudioFormatSubtypeInfo@@H_N@Z; InitializeSpatialAudioFormatSubtypeInfoArray(SpatialAudioFormatSubtypeInfo *,int,bool)
0x1800c7e79  mov     r14d, eax
0x1800c7e7c  cmp     eax, 13h
0x1800c7e7f  jnz     short loc_1800C7EAD
0x1800c7e81  mov     r9, r15; void (*)(void *)
0x1800c7e84  mov     r8d, esi; unsigned __int64
0x1800c7e87  mov     edx, r12d; unsigned __int64
0x1800c7e8a  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800c7e8f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800c7e94  nop
0x1800c7e95  test    rbx, rbx
0x1800c7e98  jz      short loc_1800C7EA3
0x1800c7e9a  mov     rcx, rbx; lpCriticalSection
0x1800c7e9d  call    cs:__imp_LeaveCriticalSection
0x1800c7ea3  mov     eax, 13h
0x1800c7ea8  jmp     loc_1800C82C9
0x1800c7ead  test    r14d, r14d
0x1800c7eb0  jns     short loc_1800C7EF9
0x1800c7eb2  mov     edx, 0A5Ah; void *
0x1800c7eb7  mov     rcx, [rsp+1C8h]; this
0x1800c7ebf  mov     r9d, r14d; char *
0x1800c7ec2  lea     r8, aAvcorePublishe; "avcore\\published\\audiocore\\lib\\atmo"...
0x1800c7ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7ece  nop
0x1800c7ecf  mov     r9, r15; void (*)(void *)
0x1800c7ed2  mov     r8, rsi; unsigned __int64
0x1800c7ed5  mov     rdx, r12; unsigned __int64
0x1800c7ed8  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800c7edd  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800c7ee2  nop
0x1800c7ee3  test    rbx, rbx
0x1800c7ee6  jz      short loc_1800C7EF1
0x1800c7ee8  mov     rcx, rbx; lpCriticalSection
0x1800c7eeb  call    cs:__imp_LeaveCriticalSection
0x1800c7ef1  mov     eax, r14d
0x1800c7ef4  jmp     loc_1800C82C9
0x1800c7ef9  lea     r9, CallbackContext; struct _tlgProvider_t *
0x1800c7f00  mov     r8, r13; bool *
0x1800c7f03  mov     edx, esi; int
0x1800c7f05  lea     rcx, [rsp+1C8h+var_158]; struct SpatialAudioFormatSubtypeInfo *
0x1800c7f0a  call    ?ScanForInstalledSpatialAudioSubtypeAppServices@@YAJPEAUSpatialAudioFormatSubtypeInfo@@HPEA_NPEBU_tlgProvider_t@@@Z; ScanForInstalledSpatialAudioSubtypeAppServices(SpatialAudioFormatSubtypeInfo *,int,bool *,_tlgProvider_t const *)
0x1800c7f0f  mov     r14d, eax
0x1800c7f12  test    eax, eax
0x1800c7f14  jns     short loc_1800C7F1D
0x1800c7f16  mov     edx, 0A5Ch
0x1800c7f1b  jmp     short loc_1800C7EB7
0x1800c7f1d  xor     cl, cl
0x1800c7f1f  mov     [rsp+1C8h+var_198], cl
0x1800c7f23  xor     eax, eax
0x1800c7f25  mov     [rsp+1C8h+var_194], eax
0x1800c7f29  cmp     eax, esi
0x1800c7f2b  jnb     loc_1800C81F8
0x1800c7f31  cdqe
0x1800c7f33  mov     [rsp+1C8h+var_170], rax
0x1800c7f38  imul    r13, rax, 38h ; '8'
0x1800c7f3c  lea     r14, [rax+rax*4]
0x1800c7f40  mov     [rsp+1C8h+bIgnoreCase], 1; int
0x1800c7f48  or      r9d, 0FFFFFFFFh; cchCount2
0x1800c7f4c  mov     r8, [rdi+r13+128h]; lpString2
0x1800c7f54  or      edx, r9d; cchCount1
0x1800c7f57  mov     rcx, [rsp+r14*8+1C8h+lpString1]; lpString1
0x1800c7f5c  call    cs:__imp_CompareStringOrdinal
0x1800c7f62  cmp     eax, 2
0x1800c7f65  jz      short loc_1800C7FB2
0x1800c7f67  mov     edi, 8000FFFFh
0x1800c7f6c  mov     edx, 0A6Ch; void *
0x1800c7f71  lea     r8, aAvcorePublishe; "avcore\\published\\audiocore\\lib\\atmo"...
0x1800c7f78  mov     r9d, edi; char *
0x1800c7f7b  mov     rcx, [rsp+1C8h]; this
0x1800c7f83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7f88  nop
0x1800c7f89  mov     r9, r15; void (*)(void *)
0x1800c7f8c  mov     r8, rsi; unsigned __int64
0x1800c7f8f  mov     rdx, r12; unsigned __int64
0x1800c7f92  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800c7f97  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800c7f9c  nop
0x1800c7f9d  test    rbx, rbx
0x1800c7fa0  jz      short loc_1800C7FAB
0x1800c7fa2  mov     rcx, rbx; lpCriticalSection
0x1800c7fa5  call    cs:__imp_LeaveCriticalSection
0x1800c7fab  mov     eax, edi
0x1800c7fad  jmp     loc_1800C82C9
0x1800c7fb2  lea     rax, [rsp+1C8h+var_148]
0x1800c7fba  lea     r14, [rax+r14*8]
0x1800c7fbe  mov     rax, [rsp+1C8h+var_170]
0x1800c7fc3  lea     rdx, [rax+rax*4]
0x1800c7fc7  mov     al, [rsp+rdx*8+1C8h+var_158]
0x1800c7fcb  cmp     [rdi+r13+110h], al
0x1800c7fd3  jnz     loc_1800C80DC
0x1800c7fd9  mov     r8, [rdi+r13+130h]
0x1800c7fe1  mov     rcx, [rdi+r13+138h]
0x1800c7fe9  sub     rcx, r8
0x1800c7fec  mov     rax, [rsp+rdx*8+1C8h+var_140]
0x1800c7ff4  sub     rax, [r14]
0x1800c7ff7  cmp     rcx, rax
0x1800c7ffa  jnz     loc_1800C80DC
0x1800c8000  sar     rcx, 4
0x1800c8004  test    rcx, rcx
0x1800c8007  jz      loc_1800C80CE
0x1800c800d  xor     ecx, ecx
0x1800c800f  mov     [rsp+1C8h+var_178], rcx
0x1800c8014  mov     rdx, rcx
0x1800c8017  add     rdx, rdx
0x1800c801a  lea     r9, LocaleName
0x1800c8021  mov     rcx, r9
0x1800c8024  cmp     qword ptr [r8+rdx*8], 0
0x1800c8029  cmovnz  rcx, [r8+rdx*8]; lpString1
0x1800c802e  mov     rax, r9
0x1800c8031  cmp     qword ptr [r8+rdx*8+8], 0
0x1800c8037  cmovnz  rax, [r8+rdx*8+8]
0x1800c803d  mov     [rsp+1C8h+var_190], rax
0x1800c8042  mov     rax, [r14]
0x1800c8045  mov     r8, r9
0x1800c8048  cmp     qword ptr [rax+rdx*8], 0
0x1800c804d  cmovnz  r8, [rax+rdx*8]; lpString2
0x1800c8052  cmp     qword ptr [rax+rdx*8+8], 0
0x1800c8058  cmovnz  r9, [rax+rdx*8+8]
0x1800c805e  mov     [rsp+1C8h+lpString2], r9
0x1800c8063  mov     [rsp+1C8h+bIgnoreCase], 1; bIgnoreCase
0x1800c806b  or      edx, 0FFFFFFFFh; cchCount1
0x1800c806e  mov     r9d, edx; cchCount2
0x1800c8071  call    cs:__imp_CompareStringOrdinal
0x1800c8077  cmp     eax, 2
0x1800c807a  jnz     short loc_1800C80DC
0x1800c807c  mov     [rsp+1C8h+bIgnoreCase], 1; bIgnoreCase
0x1800c8084  or      eax, 0FFFFFFFFh
0x1800c8087  mov     r9d, eax; cchCount2
0x1800c808a  mov     r8, [rsp+1C8h+lpString2]; lpString2
0x1800c808f  mov     edx, eax; cchCount1
0x1800c8091  mov     rcx, [rsp+1C8h+var_190]; lpString1
0x1800c8096  call    cs:__imp_CompareStringOrdinal
0x1800c809c  cmp     eax, 2
0x1800c809f  jnz     short loc_1800C80DC
0x1800c80a1  mov     rcx, [rsp+1C8h+var_178]
0x1800c80a6  inc     rcx
0x1800c80a9  mov     [rsp+1C8h+var_178], rcx
0x1800c80ae  mov     r8, [rdi+r13+130h]
0x1800c80b6  mov     rax, [rdi+r13+138h]
0x1800c80be  sub     rax, r8
0x1800c80c1  sar     rax, 4
0x1800c80c5  cmp     rcx, rax
0x1800c80c8  jb      loc_1800C8014
0x1800c80ce  mov     cl, [rsp+1C8h+var_198]
0x1800c80d2  test    cl, cl
0x1800c80d4  jz      loc_1800C81ED
0x1800c80da  jmp     short loc_1800C80E1
0x1800c80dc  mov     [rsp+1C8h+var_198], 1
0x1800c80e1  mov     rcx, [rsp+1C8h+var_170]
0x1800c80e6  lea     rax, [rcx+rcx*4]
0x1800c80ea  mov     al, [rsp+rax*8+1C8h+var_158]
0x1800c80ee  mov     [rdi+r13+110h], al
0x1800c80f6  add     r13, 130h
0x1800c80fd  add     r13, rdi
0x1800c8100  mov     [rsp+1C8h+lpString2], r13
0x1800c8105  imul    rax, rcx, 38h ; '8'
0x1800c8109  mov     [rsp+1C8h+var_190], rax
0x1800c810e  mov     rdx, [rax+rdi+138h]
0x1800c8116  cmp     [r13+0], rdx
0x1800c811a  jz      short loc_1800C8136
0x1800c811c  mov     rcx, [r13+0]; this
0x1800c8120  call    ??$_Destroy_range@V?$allocator@USpatialAudioAppDetails@@@std@@@std@@YAXPEAUSpatialAudioAppDetails@@QEAU1@AEAV?$allocator@USpatialAudioAppDetails@@@0@@Z; std::_Destroy_range<std::allocator<SpatialAudioAppDetails>>(SpatialAudioAppDetails *,SpatialAudioAppDetails * const,std::allocator<SpatialAudioAppDetails> &)
0x1800c8125  mov     rax, [r13+0]
0x1800c8129  mov     rcx, [rsp+1C8h+var_190]
0x1800c812e  mov     [rcx+rdi+138h], rax
0x1800c8136  mov     r13, [r14]
0x1800c8139  mov     rax, [r14+8]
0x1800c813d  mov     [rsp+1C8h+var_190], rax
0x1800c8142  mov     r14, [rsp+1C8h+lpString2]
0x1800c8147  cmp     r13, rax
0x1800c814a  jz      loc_1800C81E9
0x1800c8150  xorps   xmm0, xmm0
0x1800c8153  movdqu  xmmword ptr [rsp+1C8h+lpString2], xmm0
0x1800c8159  mov     rdx, [r13+0]
0x1800c815d  mov     qword ptr [r13+0], 0
0x1800c8165  lea     rcx, [rsp+1C8h+lpString2]
0x1800c816a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c816f  mov     rdx, [r13+8]
0x1800c8173  mov     qword ptr [r13+8], 0
0x1800c817b  lea     rcx, [rsp+1C8h+lpString2+8]
0x1800c8180  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c8185  nop
0x1800c8186  lea     rdx, [rsp+1C8h+lpString2]
0x1800c818b  mov     rcx, r14
0x1800c818e  call    ?push_back@?$vector@USpatialTechAppDetails@CommonSpatialTechInfo@AtmosCheck@@V?$allocator@USpatialTechAppDetails@CommonSpatialTechInfo@AtmosCheck@@@std@@@std@@QEAAX$$QEAUSpatialTechAppDetails@CommonSpatialTechInfo@AtmosCheck@@@Z; std::vector<AtmosCheck::CommonSpatialTechInfo::SpatialTechAppDetails>::push_back(AtmosCheck::CommonSpatialTechInfo::SpatialTechAppDetails &&)
0x1800c8193  nop
0x1800c8194  lea     rcx, [rsp+1C8h+lpString2]; this
0x1800c8199  call    ??1SpatialAudioAppDetails@@QEAA@XZ; SpatialAudioAppDetails::~SpatialAudioAppDetails(void)
0x1800c819e  add     r13, 10h
0x1800c81a2  mov     rax, [rsp+1C8h+var_190]
0x1800c81a7  jmp     short loc_1800C8147
0x1800c81a9  lea     rcx, [rsp+1C8h+lpString2]; this
0x1800c81ae  call    ??1SpatialAudioAppDetails@@QEAA@XZ; SpatialAudioAppDetails::~SpatialAudioAppDetails(void)
0x1800c81b3  nop
0x1800c81b4  lea     r9, ??1SpatialAudioFormatSubtypeInfo@@QEAA@XZ; void (*)(void *)
0x1800c81bb  mov     edx, 28h ; '('; unsigned __int64
0x1800c81c0  lea     r8d, [rdx-21h]; unsigned __int64
0x1800c81c4  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800c81c9  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800c81ce  nop
0x1800c81cf  mov     rcx, [rsp+1C8h+lpCriticalSection]; lpCriticalSection
0x1800c81d4  test    rcx, rcx
0x1800c81d7  jz      short loc_1800C81DF
0x1800c81d9  call    cs:__imp_LeaveCriticalSection
0x1800c81df  mov     eax, 8007000Eh
0x1800c81e4  jmp     loc_1800C82C9
0x1800c81e9  mov     cl, [rsp+1C8h+var_198]
0x1800c81ed  mov     eax, [rsp+1C8h+var_194]
0x1800c81f1  inc     eax
0x1800c81f3  jmp     loc_1800C7F25
0x1800c81f8  lea     r13, [rdi+0D9h]
0x1800c81ff  mov     al, [rsp+1C8h+var_197]
0x1800c8203  cmp     al, [r13+0]
0x1800c8207  jz      short loc_1800C8261
0x1800c8209  cmp     byte ptr [r13+0], 0
0x1800c820e  jz      short loc_1800C824D
0x1800c8210  lea     rcx, [rdi+298h]
0x1800c8217  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@$$BY0A@UEndpointSpecificSpatialTechInfo@AtmosCheck@@U?$default_delete@$$BY0A@UEndpointSpecificSpatialTechInfo@AtmosCheck@@@wistd@@@wistd@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Ucase_insensitive_hash@@Ucase_insensitive_equality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@$$BY0A@UEndpointSpecificSpatialTechInfo@AtmosCheck@@U?$default_delete@$$BY0A@UEndpointSpecificSpatialTechInfo@AtmosCheck@@@wistd@@@wistd@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,wistd::unique_ptr<AtmosCheck::EndpointSpecificSpatialTechInfo [0],wistd::default_delete<AtmosCheck::EndpointSpecificSpatialTechInfo [0]>>,std::_Uhash_compare<std::wstring,case_insensitive_hash,case_insensitive_equality>,std::allocator<std::pair<std::wstring const,wistd::unique_ptr<AtmosCheck::EndpointSpecificSpatialTechInfo [0],wistd::default_delete<AtmosCheck::EndpointSpecificSpatialTechInfo [0]>>>>,0>>::clear(void)
0x1800c821c  mov     rcx, rdi; this
0x1800c821f  call    ?InitializeAppServiceMode@AtmosCheck@@AEAAJXZ; AtmosCheck::InitializeAppServiceMode(void)
0x1800c8224  mov     r14d, eax
0x1800c8227  test    eax, eax
0x1800c8229  jns     short loc_1800C8235
0x1800c822b  mov     edx, 0ABCh
0x1800c8230  jmp     loc_1800C7EB7
0x1800c8235  mov     rcx, rdi; this
0x1800c8238  call    ?UpdateLicenseMapForAllEndpoints@AtmosCheck@@AEAAJXZ; AtmosCheck::UpdateLicenseMapForAllEndpoints(void)
0x1800c823d  mov     edi, eax
0x1800c823f  test    eax, eax
0x1800c8241  jns     short loc_1800C825D
0x1800c8243  mov     edx, 0ABDh
0x1800c8248  jmp     loc_1800C7F71
0x1800c824d  mov     rcx, rdi; this
0x1800c8250  call    ?InitializeLicenseMapLegacy@AtmosCheck@@AEAAXXZ; AtmosCheck::InitializeLicenseMapLegacy(void)
0x1800c8255  mov     rcx, rdi; pv
0x1800c8258  call    ?UninitializeAppServiceMode@AtmosCheck@@AEAAXXZ; AtmosCheck::UninitializeAppServiceMode(void)
0x1800c825d  mov     cl, [rsp+1C8h+var_198]
0x1800c8261  mov     rax, [rsp+1C8h+var_160]
0x1800c8266  test    rax, rax
0x1800c8269  jz      short loc_1800C826D
0x1800c826b  mov     [rax], cl
0x1800c826d  mov     eax, cs:CallbackContext
0x1800c8273  cmp     eax, 5
0x1800c8276  jbe     short loc_1800C82A5
0x1800c8278  mov     al, [r13+0]
0x1800c827c  mov     [rsp+1C8h+var_197], al
0x1800c8280  mov     [rsp+1C8h+var_198], cl
0x1800c8284  lea     rax, [rsp+1C8h+var_197]
0x1800c8289  mov     [rsp+1C8h+var_1A0], rax
0x1800c828e  lea     rax, [rsp+1C8h+var_198]
0x1800c8293  mov     qword ptr [rsp+1C8h+bIgnoreCase], rax
0x1800c8298  lea     rdx, byte_1801AE723
0x1800c829f  call    ??$Write@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x1800c82a4  nop
0x1800c82a5  mov     r9, r15; void (*)(void *)
0x1800c82a8  mov     r8, rsi; unsigned __int64
0x1800c82ab  mov     rdx, r12; unsigned __int64
0x1800c82ae  lea     rcx, [rsp+1C8h+var_158]; void *
0x1800c82b3  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800c82b8  nop
0x1800c82b9  test    rbx, rbx
0x1800c82bc  jz      short loc_1800C82C7
0x1800c82be  mov     rcx, rbx; lpCriticalSection
0x1800c82c1  call    cs:__imp_LeaveCriticalSection
0x1800c82c7  xor     eax, eax
0x1800c82c9  mov     rcx, [rsp+1C8h+var_38]
0x1800c82d1  xor     rcx, rsp; StackCookie
  ... truncated ...
```
