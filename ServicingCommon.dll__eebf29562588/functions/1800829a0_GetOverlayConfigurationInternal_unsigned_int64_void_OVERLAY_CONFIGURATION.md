# GetOverlayConfigurationInternal(unsigned __int64,void *,OVERLAY_CONFIGURATION * *)

- ea: `0x1800829a0`
- end: `0x180082cc4`
- name: `?GetOverlayConfigurationInternal@@YAJ_KPEAXPEAPEAUOVERLAY_CONFIGURATION@@@Z`
- size: `804`
- prototype: `int(unsigned __int64, void *, struct OVERLAY_CONFIGURATION **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x18008287c`

## callees

- `0x18001f5d4`
- `0x180024120`
- `0x1800293a0`
- `0x18002979c`
- `0x18007efac`
- `0x180081130`
- `0x180081470`
- `0x180081544`
- `0x180081dcc`
- `0x180081e1c`
- `0x180081e78`
- `0x1800829a0`
- `0x180083d74`
- `0x1800840f8`
- `0x180084f48`
- `0x1800856c4`

## string_xrefs

- `0x180082a99`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082b69`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082bc1`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082c4d`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082ab0`: `GetOverlayConfigurationInternal`
- `0x180082b80`: `GetOverlayConfigurationInternal`
- `0x180082bd8`: `GetOverlayConfigurationInternal`
- `0x180082c64`: `GetOverlayConfigurationInternal`
- `0x180082c75`: `ConfigOut`

## pseudocode

```c
__int64 __fastcall GetOverlayConfigurationInternal(__int64 a1, void *a2, wchar_t *a3)
{
  __int64 result; // rax
  __int64 v6; // rdx
  const wchar_t *v7; // r8
  __int64 v8; // rdx
  const wchar_t *v9; // r8
  bool *v10; // rcx
  int v11; // edi
  struct OVERLAY_CONFIGURATION *v12; // rax
  int v13; // edi
  __m128i *v14; // rdx
  __int64 v15; // r8
  int v16; // ebx
  int v17; // edi
  const wchar_t **v18; // rdi
  _QWORD *v19; // rdx
  const wchar_t *v20; // rdx
  char v21; // [rsp+30h] [rbp-89h] BYREF
  void *v22; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v24[4]; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v25[4]; // [rsp+68h] [rbp-51h] BYREF
  _QWORD v26[4]; // [rsp+88h] [rbp-31h] BYREF
  int v27; // [rsp+A8h] [rbp-11h] BYREF
  struct OVERLAY_CONFIGURATION *v28; // [rsp+B0h] [rbp-9h] BYREF
  int v29[2]; // [rsp+B8h] [rbp-1h] BYREF
  __m128i si128; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v31; // [rsp+D0h] [rbp+17h]
  __int64 v32; // [rsp+D8h] [rbp+1Fh]

  v27 = 0;
  v21 = 0;
  v23 = 0;
  result = OuGetAndValidateRegistryEnum<enum ConfigurationVersion>(a2, (__int64)a2, a3, &v23);
  if ( (int)result >= 0 )
  {
    LODWORD(v22) = 0;
    result = OuGetAndValidateRegistryEnum<enum OverlayType>(a2, v6, v7, &v22);
    if ( (int)result >= 0 )
    {
      v29[0] = 0;
      v10 = (bool *)&v21;
      if ( v23 != 1 )
        v10 = 0;
      result = OuGetAndValidateRegistryEnum<enum OverlayLoadType>(a2, v8, v9, (unsigned int *)v29, v10);
      if ( (int)result >= 0 )
      {
        v11 = v29[0];
        if ( v21 )
          v11 = 1;
        v28 = 0;
        v12 = (struct OVERLAY_CONFIGURATION *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
        *(_QWORD *)v29 = 0;
        if ( !v12 )
        {
          v26[2] = 1188;
          v26[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v14 = (__m128i *)v26;
          v15 = 3221225495LL;
          v26[1] = "GetOverlayConfigurationInternal";
          v26[3] = "ConfigOut";
          goto LABEL_30;
        }
        v28 = v12;
        *(_OWORD *)v12 = 0;
        *((_OWORD *)v12 + 1) = 0;
        *((_QWORD *)v12 + 4) = 0;
        *(_DWORD *)v28 = (_DWORD)v22;
        *((_DWORD *)v28 + 1) = v11;
        v13 = v11 - 1;
        if ( v13 )
        {
          if ( v13 != 1 )
          {
            v31 = 1228;
            si128.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\overlayutil\\read.cpp";
            v14 = &si128;
            v32 = 0;
            si128.m128i_i64[1] = (__int64)"GetOverlayConfigurationInternal";
            v15 = 3221225659LL;
LABEL_30:
            v16 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                    &v27,
                    v14,
                    v15);
            goto LABEL_31;
          }
          v22 = 0;
          v16 = OuOpenKey(a2, L"Hashes", &v22);
          if ( v16 >= 0 )
          {
            v16 = LoadHashEntries(v23, &v28, v22);
            if ( v16 >= 0 )
            {
              AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v22);
LABEL_28:
              v16 = 0;
              *(_QWORD *)a3 = v28;
              v28 = 0;
              goto LABEL_31;
            }
          }
          AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v22);
LABEL_31:
          utl::unique_ptr<OVERLAY_CONFIGURATION,utl::default_delete<OVERLAY_CONFIGURATION>>::~unique_ptr<OVERLAY_CONFIGURATION,utl::default_delete<OVERLAY_CONFIGURATION>>((void **)v29);
          AutoOverlayConfigurationPtr::~AutoOverlayConfigurationPtr(&v28);
          return (unsigned int)v16;
        }
        v31 = -1;
        si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        v17 = OuEnumerateSubKeys(a2, &si128);
        if ( v17 < 0 )
        {
          utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
          v16 = v17;
          goto LABEL_31;
        }
        v18 = (const wchar_t **)si128.m128i_i64[0];
        if ( (unsigned __int64)((si128.m128i_i64[1] - si128.m128i_i64[0]) >> 5) <= 1 )
        {
          if ( !wcsicmp(*(const wchar_t **)si128.m128i_i64[0], L"osdevice") )
          {
            v20 = *v18;
            v22 = 0;
            v16 = OuOpenKey(a2, v20, &v22);
            if ( v16 >= 0 )
            {
              v16 = LoadDeviceEntries(v23, &v28, v18, v22);
              if ( v16 >= 0 )
              {
                AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v22);
                utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
                goto LABEL_28;
              }
            }
            AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v22);
            goto LABEL_21;
          }
          v25[2] = 1210;
          v25[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v19 = v25;
          v25[3] = 0;
          v25[1] = "GetOverlayConfigurationInternal";
        }
        else
        {
          v24[2] = 1205;
          v24[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v19 = v24;
          v24[3] = 0;
          v24[1] = "GetOverlayConfigurationInternal";
        }
        v16 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                &v27,
                v19,
                3221225659LL);
LABEL_21:
        utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
        goto LABEL_31;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800829a0  mov     [rsp-8+arg_0], rbx
0x1800829a5  push    rbp
0x1800829a6  push    rdi
0x1800829a7  push    r12
0x1800829a9  push    r14
0x1800829ab  push    r15
0x1800829ad  lea     rbp, [rsp-37h]
0x1800829b2  sub     rsp, 0F0h
0x1800829b9  mov     rax, cs:__security_cookie
0x1800829c0  xor     rax, rsp
0x1800829c3  mov     [rbp+57h+var_30], rax
0x1800829c7  xor     r15d, r15d
0x1800829ca  lea     r9, [rbp+57h+var_D0]
0x1800829ce  mov     rcx, rdx
0x1800829d1  mov     [rbp+57h+var_68], r15d
0x1800829d5  mov     [rsp+110h+var_E0], r15b
0x1800829da  mov     r14, r8
0x1800829dd  mov     [rbp+57h+var_D0], r15d
0x1800829e1  mov     rbx, rdx
0x1800829e4  call    ??$OuGetAndValidateRegistryEnum@W4ConfigurationVersion@@@@YAJPEAXPEB_W1PEAW4ConfigurationVersion@@PEA_N@Z; OuGetAndValidateRegistryEnum<ConfigurationVersion>(void *,wchar_t const *,wchar_t const *,ConfigurationVersion *,bool *)
0x1800829e9  test    eax, eax
0x1800829eb  js      loc_180082C9F
0x1800829f1  lea     r9, [rsp+110h+var_D8]
0x1800829f6  mov     dword ptr [rsp+110h+var_D8], r15d
0x1800829fb  mov     rcx, rbx
0x1800829fe  call    ??$OuGetAndValidateRegistryEnum@W4OverlayType@@@@YAJPEAXPEB_W1PEAW4OverlayType@@PEA_N@Z; OuGetAndValidateRegistryEnum<OverlayType>(void *,wchar_t const *,wchar_t const *,OverlayType *,bool *)
0x180082a03  test    eax, eax
0x180082a05  js      loc_180082C9F
0x180082a0b  lea     r12d, [r15+1]
0x180082a0f  mov     [rbp+57h+var_58], r15d
0x180082a13  cmp     [rbp+57h+var_D0], r12d
0x180082a17  lea     rcx, [rsp+110h+var_E0]
0x180082a1c  lea     r9, [rbp+57h+var_58]; int
0x180082a20  cmovnz  rcx, r15
0x180082a24  mov     [rsp+110h+var_F0], rcx; bool *
0x180082a29  mov     rcx, rbx; int
0x180082a2c  call    ??$OuGetAndValidateRegistryEnum@W4OverlayLoadType@@@@YAJPEAXPEB_W1PEAW4OverlayLoadType@@PEA_N@Z; OuGetAndValidateRegistryEnum<OverlayLoadType>(void *,wchar_t const *,wchar_t const *,OverlayLoadType *,bool *)
0x180082a31  test    eax, eax
0x180082a33  js      loc_180082C9F
0x180082a39  cmp     [rsp+110h+var_E0], r15b
0x180082a3e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180082a45  mov     edi, [rbp+57h+var_58]
0x180082a48  lea     ecx, [r15+28h]; unsigned __int64
0x180082a4c  cmovnz  edi, r12d
0x180082a50  mov     [rbp+57h+var_60], r15
0x180082a54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180082a59  mov     qword ptr [rbp+57h+var_58], r15
0x180082a5d  test    rax, rax
0x180082a60  jz      loc_180082C4D
0x180082a66  mov     [rbp+57h+var_60], rax
0x180082a6a  xor     ecx, ecx
0x180082a6c  xorps   xmm0, xmm0
0x180082a6f  movups  xmmword ptr [rax], xmm0
0x180082a72  movups  xmmword ptr [rax+10h], xmm0
0x180082a76  mov     [rax+20h], rcx
0x180082a7a  mov     rax, [rbp+57h+var_60]
0x180082a7e  mov     ecx, dword ptr [rsp+110h+var_D8]
0x180082a82  mov     [rax], ecx
0x180082a84  mov     rax, [rbp+57h+var_60]
0x180082a88  mov     [rax+4], edi
0x180082a8b  sub     edi, r12d
0x180082a8e  jz      loc_180082B1E
0x180082a94  cmp     edi, r12d
0x180082a97  jz      short loc_180082ACA
0x180082a99  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082aa0  mov     [rbp+57h+var_40], 4CCh
0x180082aa8  mov     qword ptr [rbp+57h+var_50], rax
0x180082aac  lea     rdx, [rbp+57h+var_50]
0x180082ab0  lea     rax, aGetoverlayconf_1; "GetOverlayConfigurationInternal"
0x180082ab7  mov     [rbp+57h+var_38], r15
0x180082abb  mov     qword ptr [rbp+57h+var_50+8], rax
0x180082abf  mov     r8d, 0C00000BBh
0x180082ac5  jmp     loc_180082C80
0x180082aca  lea     r8, [rsp+110h+var_D8]; void **
0x180082acf  mov     [rsp+110h+var_D8], r15
0x180082ad4  lea     rdx, aHashes; "Hashes"
0x180082adb  mov     rcx, rbx; void *
0x180082ade  call    ?OuOpenKey@@YAJPEAXPEB_WPEAPEAX@Z; OuOpenKey(void *,wchar_t const *,void * *)
0x180082ae3  mov     ebx, eax
0x180082ae5  test    eax, eax
0x180082ae7  jns     short loc_180082AF8
0x180082ae9  lea     rcx, [rsp+110h+var_D8]; this
0x180082aee  call    ??1AutoOuKeyHandle@@QEAA@XZ; AutoOuKeyHandle::~AutoOuKeyHandle(void)
0x180082af3  jmp     loc_180082C8B
0x180082af8  mov     r8, [rsp+110h+var_D8]
0x180082afd  lea     rdx, [rbp+57h+var_60]
0x180082b01  mov     ecx, [rbp+57h+var_D0]
0x180082b04  call    ?LoadHashEntries@@YAJW4ConfigurationVersion@@AEAVAutoOverlayConfigurationPtr@@PEAX@Z; LoadHashEntries(ConfigurationVersion,AutoOverlayConfigurationPtr &,void *)
0x180082b09  lea     rcx, [rsp+110h+var_D8]; this
0x180082b0e  mov     ebx, eax
0x180082b10  test    eax, eax
0x180082b12  js      short loc_180082AEE
0x180082b14  call    ??1AutoOuKeyHandle@@QEAA@XZ; AutoOuKeyHandle::~AutoOuKeyHandle(void)
0x180082b19  jmp     loc_180082C3D
0x180082b1e  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180082b26  lea     rdx, [rbp+57h+var_50]
0x180082b2a  mov     rcx, rbx
0x180082b2d  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x180082b35  movdqu  [rbp+57h+var_50], xmm0
0x180082b3a  call    ?OuEnumerateSubKeys@@YAJPEAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@@Z; OuEnumerateSubKeys(void *,utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &)
0x180082b3f  mov     edi, eax
0x180082b41  test    eax, eax
0x180082b43  jns     short loc_180082B55
0x180082b45  lea     rcx, [rbp+57h+var_50]
0x180082b49  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180082b4e  mov     ebx, edi
0x180082b50  jmp     loc_180082C8B
0x180082b55  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180082b59  mov     rdi, qword ptr [rbp+57h+var_50]
0x180082b5d  sub     rax, rdi
0x180082b60  sar     rax, 5
0x180082b64  cmp     rax, r12
0x180082b67  jbe     short loc_180082BAE
0x180082b69  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082b70  mov     [rbp+57h+var_B8], 4B5h
0x180082b78  mov     [rbp+57h+var_C8], rax
0x180082b7c  lea     rdx, [rbp+57h+var_C8]
0x180082b80  lea     rax, aGetoverlayconf_1; "GetOverlayConfigurationInternal"
0x180082b87  mov     [rbp+57h+var_B0], r15
0x180082b8b  mov     [rbp+57h+var_C0], rax
0x180082b8f  mov     r8d, 0C00000BBh
0x180082b95  lea     rcx, [rbp+57h+var_68]
0x180082b99  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180082b9e  mov     ebx, eax
0x180082ba0  lea     rcx, [rbp+57h+var_50]
0x180082ba4  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180082ba9  jmp     loc_180082C8B
0x180082bae  mov     rcx, [rdi]; String1
0x180082bb1  lea     rdx, aOsdevice; "osdevice"
0x180082bb8  call    _wcsicmp
0x180082bbd  test    eax, eax
0x180082bbf  jz      short loc_180082BE9
0x180082bc1  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082bc8  mov     [rbp+57h+var_98], 4BAh
0x180082bd0  mov     [rbp+57h+var_A8], rax
0x180082bd4  lea     rdx, [rbp+57h+var_A8]
0x180082bd8  lea     rax, aGetoverlayconf_1; "GetOverlayConfigurationInternal"
0x180082bdf  mov     [rbp+57h+var_90], r15
0x180082be3  mov     [rbp+57h+var_A0], rax
0x180082be7  jmp     short loc_180082B8F
0x180082be9  mov     rdx, [rdi]; wchar_t *
0x180082bec  lea     r8, [rsp+110h+var_D8]; void **
0x180082bf1  mov     rcx, rbx; void *
0x180082bf4  mov     [rsp+110h+var_D8], r15
0x180082bf9  call    ?OuOpenKey@@YAJPEAXPEB_WPEAPEAX@Z; OuOpenKey(void *,wchar_t const *,void * *)
0x180082bfe  mov     ebx, eax
0x180082c00  test    eax, eax
0x180082c02  jns     short loc_180082C10
0x180082c04  lea     rcx, [rsp+110h+var_D8]; this
0x180082c09  call    ??1AutoOuKeyHandle@@QEAA@XZ; AutoOuKeyHandle::~AutoOuKeyHandle(void)
0x180082c0e  jmp     short loc_180082BA0
0x180082c10  mov     r9, [rsp+110h+var_D8]
0x180082c15  lea     rdx, [rbp+57h+var_60]
0x180082c19  mov     ecx, [rbp+57h+var_D0]
0x180082c1c  mov     r8, rdi
0x180082c1f  call    ?LoadDeviceEntries@@YAJW4ConfigurationVersion@@AEAVAutoOverlayConfigurationPtr@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; LoadDeviceEntries(ConfigurationVersion,AutoOverlayConfigurationPtr &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,void *)
0x180082c24  lea     rcx, [rsp+110h+var_D8]; this
0x180082c29  mov     ebx, eax
0x180082c2b  test    eax, eax
0x180082c2d  js      short loc_180082C09
0x180082c2f  call    ??1AutoOuKeyHandle@@QEAA@XZ; AutoOuKeyHandle::~AutoOuKeyHandle(void)
0x180082c34  lea     rcx, [rbp+57h+var_50]
0x180082c38  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180082c3d  mov     rax, [rbp+57h+var_60]
0x180082c41  mov     ebx, r15d
0x180082c44  mov     [r14], rax
0x180082c47  mov     [rbp+57h+var_60], r15
0x180082c4b  jmp     short loc_180082C8B
0x180082c4d  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082c54  mov     [rbp+57h+var_78], 4A4h
0x180082c5c  mov     [rbp+57h+var_88], rax
0x180082c60  lea     rdx, [rbp+57h+var_88]
0x180082c64  lea     rax, aGetoverlayconf_1; "GetOverlayConfigurationInternal"
0x180082c6b  mov     r8d, 0C0000017h
0x180082c71  mov     [rbp+57h+var_80], rax
0x180082c75  lea     rax, aConfigout; "ConfigOut"
0x180082c7c  mov     [rbp+57h+var_70], rax
0x180082c80  lea     rcx, [rbp+57h+var_68]
0x180082c84  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180082c89  mov     ebx, eax
0x180082c8b  lea     rcx, [rbp+57h+var_58]
0x180082c8f  call    ??1?$unique_ptr@UOVERLAY_CONFIGURATION@@U?$default_delete@UOVERLAY_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CONFIGURATION,utl::default_delete<OVERLAY_CONFIGURATION>>::~unique_ptr<OVERLAY_CONFIGURATION,utl::default_delete<OVERLAY_CONFIGURATION>>(void)
0x180082c94  lea     rcx, [rbp+57h+var_60]; this
0x180082c98  call    ??1AutoOverlayConfigurationPtr@@QEAA@XZ; AutoOverlayConfigurationPtr::~AutoOverlayConfigurationPtr(void)
0x180082c9d  mov     eax, ebx
0x180082c9f  mov     rcx, [rbp+57h+var_30]
0x180082ca3  xor     rcx, rsp; StackCookie
0x180082ca6  call    __security_check_cookie
0x180082cab  mov     rbx, [rsp+110h+arg_0]
0x180082cb3  add     rsp, 0F0h
0x180082cba  pop     r15
0x180082cbc  pop     r14
0x180082cbe  pop     r12
0x180082cc0  pop     rdi
0x180082cc1  pop     rbp
0x180082cc2  retn
```
