# GetOverlayConfigurationInternal(unsigned __int64,void *,OVERLAY_CONFIGURATION * *)

- ea: `0x180081a38`
- end: `0x180081d5c`
- name: `?GetOverlayConfigurationInternal@@YAJ_KPEAXPEAPEAUOVERLAY_CONFIGURATION@@@Z`
- size: `804`
- prototype: `int(unsigned __int64, void *, struct OVERLAY_CONFIGURATION **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180081914`

## callees

- `0x18001f840`
- `0x180028030`
- `0x18002d2b0`
- `0x18002d6ac`
- `0x18007e020`
- `0x1800801c8`
- `0x180080508`
- `0x1800805dc`
- `0x180080e64`
- `0x180080eb4`
- `0x180080f10`
- `0x180081a38`
- `0x180082e0c`
- `0x180083190`
- `0x180083fe0`
- `0x18008475c`

## string_xrefs

- `0x180081b31`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081c01`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081c59`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081ce5`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081b48`: `GetOverlayConfigurationInternal`
- `0x180081c18`: `GetOverlayConfigurationInternal`
- `0x180081c70`: `GetOverlayConfigurationInternal`
- `0x180081cfc`: `GetOverlayConfigurationInternal`
- `0x180081d0d`: `ConfigOut`

## pseudocode

```c
__int64 __fastcall GetOverlayConfigurationInternal(__int64 a1, void *a2, struct OVERLAY_CONFIGURATION **a3)
{
  __int64 result; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // edx
  int v9; // r8d
  bool *v10; // rcx
  int v11; // edi
  _OWORD *v12; // rax
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
  _OWORD *v28; // [rsp+B0h] [rbp-9h] BYREF
  int v29[2]; // [rsp+B8h] [rbp-1h] BYREF
  __m128i si128; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v31; // [rsp+D0h] [rbp+17h]
  __int64 v32; // [rsp+D8h] [rbp+1Fh]

  v27 = 0;
  v21 = 0;
  v23 = 0;
  result = OuGetAndValidateRegistryEnum<enum ConfigurationVersion>(a2, a2, a3, &v23);
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
      result = OuGetAndValidateRegistryEnum<enum OverlayLoadType>((int)a2, v8, v9, (int)v29, v10);
      if ( (int)result >= 0 )
      {
        v11 = v29[0];
        if ( v21 )
          v11 = 1;
        v28 = 0;
        v12 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
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
        *v12 = 0;
        v12[1] = 0;
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
              *a3 = (struct OVERLAY_CONFIGURATION *)v28;
              v28 = 0;
              goto LABEL_31;
            }
          }
          AutoOuKeyHandle::~AutoOuKeyHandle((AutoOuKeyHandle *)&v22);
LABEL_31:
          utl::unique_ptr<OVERLAY_CONFIGURATION,utl::default_delete<OVERLAY_CONFIGURATION>>::~unique_ptr<OVERLAY_CONFIGURATION,utl::default_delete<OVERLAY_CONFIGURATION>>(v29);
          AutoOverlayConfigurationPtr::~AutoOverlayConfigurationPtr((AutoOverlayConfigurationPtr *)&v28);
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
0x180081a38  mov     [rsp-8+arg_0], rbx
0x180081a3d  push    rbp
0x180081a3e  push    rdi
0x180081a3f  push    r12
0x180081a41  push    r14
0x180081a43  push    r15
0x180081a45  lea     rbp, [rsp-37h]
0x180081a4a  sub     rsp, 0F0h
0x180081a51  mov     rax, cs:__security_cookie
0x180081a58  xor     rax, rsp
0x180081a5b  mov     [rbp+57h+var_30], rax
0x180081a5f  xor     r15d, r15d
0x180081a62  lea     r9, [rbp+57h+var_D0]
0x180081a66  mov     rcx, rdx
0x180081a69  mov     [rbp+57h+var_68], r15d
0x180081a6d  mov     [rsp+110h+var_E0], r15b
0x180081a72  mov     r14, r8
0x180081a75  mov     [rbp+57h+var_D0], r15d
0x180081a79  mov     rbx, rdx
0x180081a7c  call    ??$OuGetAndValidateRegistryEnum@W4ConfigurationVersion@@@@YAJPEAXPEB_W1PEAW4ConfigurationVersion@@PEA_N@Z; OuGetAndValidateRegistryEnum<ConfigurationVersion>(void *,wchar_t const *,wchar_t const *,ConfigurationVersion *,bool *)
0x180081a81  test    eax, eax
0x180081a83  js      loc_180081D37
0x180081a89  lea     r9, [rsp+110h+var_D8]
0x180081a8e  mov     dword ptr [rsp+110h+var_D8], r15d
0x180081a93  mov     rcx, rbx
0x180081a96  call    ??$OuGetAndValidateRegistryEnum@W4OverlayType@@@@YAJPEAXPEB_W1PEAW4OverlayType@@PEA_N@Z; OuGetAndValidateRegistryEnum<OverlayType>(void *,wchar_t const *,wchar_t const *,OverlayType *,bool *)
0x180081a9b  test    eax, eax
0x180081a9d  js      loc_180081D37
0x180081aa3  lea     r12d, [r15+1]
0x180081aa7  mov     [rbp+57h+var_58], r15d
0x180081aab  cmp     [rbp+57h+var_D0], r12d
0x180081aaf  lea     rcx, [rsp+110h+var_E0]
0x180081ab4  lea     r9, [rbp+57h+var_58]; int
0x180081ab8  cmovnz  rcx, r15
0x180081abc  mov     [rsp+110h+var_F0], rcx; bool *
0x180081ac1  mov     rcx, rbx; int
0x180081ac4  call    ??$OuGetAndValidateRegistryEnum@W4OverlayLoadType@@@@YAJPEAXPEB_W1PEAW4OverlayLoadType@@PEA_N@Z; OuGetAndValidateRegistryEnum<OverlayLoadType>(void *,wchar_t const *,wchar_t const *,OverlayLoadType *,bool *)
0x180081ac9  test    eax, eax
0x180081acb  js      loc_180081D37
0x180081ad1  cmp     [rsp+110h+var_E0], r15b
0x180081ad6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180081add  mov     edi, [rbp+57h+var_58]
0x180081ae0  lea     ecx, [r15+28h]; unsigned __int64
0x180081ae4  cmovnz  edi, r12d
0x180081ae8  mov     [rbp+57h+var_60], r15
0x180081aec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180081af1  mov     qword ptr [rbp+57h+var_58], r15
0x180081af5  test    rax, rax
0x180081af8  jz      loc_180081CE5
0x180081afe  mov     [rbp+57h+var_60], rax
0x180081b02  xor     ecx, ecx
0x180081b04  xorps   xmm0, xmm0
0x180081b07  movups  xmmword ptr [rax], xmm0
0x180081b0a  movups  xmmword ptr [rax+10h], xmm0
0x180081b0e  mov     [rax+20h], rcx
0x180081b12  mov     rax, [rbp+57h+var_60]
0x180081b16  mov     ecx, dword ptr [rsp+110h+var_D8]
0x180081b1a  mov     [rax], ecx
0x180081b1c  mov     rax, [rbp+57h+var_60]
0x180081b20  mov     [rax+4], edi
0x180081b23  sub     edi, r12d
0x180081b26  jz      loc_180081BB6
0x180081b2c  cmp     edi, r12d
0x180081b2f  jz      short loc_180081B62
0x180081b31  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081b38  mov     [rbp+57h+var_40], 4CCh
0x180081b40  mov     qword ptr [rbp+57h+var_50], rax
0x180081b44  lea     rdx, [rbp+57h+var_50]
0x180081b48  lea     rax, aGetoverlayconf_1; "GetOverlayConfigurationInternal"
0x180081b4f  mov     [rbp+57h+var_38], r15
0x180081b53  mov     qword ptr [rbp+57h+var_50+8], rax
0x180081b57  mov     r8d, 0C00000BBh
0x180081b5d  jmp     loc_180081D18
0x180081b62  lea     r8, [rsp+110h+var_D8]; void **
0x180081b67  mov     [rsp+110h+var_D8], r15
0x180081b6c  lea     rdx, aHashes; "Hashes"
0x180081b73  mov     rcx, rbx; void *
0x180081b76  call    ?OuOpenKey@@YAJPEAXPEB_WPEAPEAX@Z; OuOpenKey(void *,wchar_t const *,void * *)
0x180081b7b  mov     ebx, eax
0x180081b7d  test    eax, eax
0x180081b7f  jns     short loc_180081B90
0x180081b81  lea     rcx, [rsp+110h+var_D8]; this
0x180081b86  call    ??1AutoOuKeyHandle@@QEAA@XZ; AutoOuKeyHandle::~AutoOuKeyHandle(void)
0x180081b8b  jmp     loc_180081D23
0x180081b90  mov     r8, [rsp+110h+var_D8]
0x180081b95  lea     rdx, [rbp+57h+var_60]
0x180081b99  mov     ecx, [rbp+57h+var_D0]
0x180081b9c  call    ?LoadHashEntries@@YAJW4ConfigurationVersion@@AEAVAutoOverlayConfigurationPtr@@PEAX@Z; LoadHashEntries(ConfigurationVersion,AutoOverlayConfigurationPtr &,void *)
0x180081ba1  lea     rcx, [rsp+110h+var_D8]; this
0x180081ba6  mov     ebx, eax
0x180081ba8  test    eax, eax
0x180081baa  js      short loc_180081B86
0x180081bac  call    ??1AutoOuKeyHandle@@QEAA@XZ; AutoOuKeyHandle::~AutoOuKeyHandle(void)
0x180081bb1  jmp     loc_180081CD5
0x180081bb6  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180081bbe  lea     rdx, [rbp+57h+var_50]
0x180081bc2  mov     rcx, rbx
0x180081bc5  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x180081bcd  movdqu  [rbp+57h+var_50], xmm0
0x180081bd2  call    ?OuEnumerateSubKeys@@YAJPEAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@@Z; OuEnumerateSubKeys(void *,utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &)
0x180081bd7  mov     edi, eax
0x180081bd9  test    eax, eax
0x180081bdb  jns     short loc_180081BED
0x180081bdd  lea     rcx, [rbp+57h+var_50]
0x180081be1  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180081be6  mov     ebx, edi
0x180081be8  jmp     loc_180081D23
0x180081bed  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180081bf1  mov     rdi, qword ptr [rbp+57h+var_50]
0x180081bf5  sub     rax, rdi
0x180081bf8  sar     rax, 5
0x180081bfc  cmp     rax, r12
0x180081bff  jbe     short loc_180081C46
0x180081c01  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081c08  mov     [rbp+57h+var_B8], 4B5h
0x180081c10  mov     [rbp+57h+var_C8], rax
0x180081c14  lea     rdx, [rbp+57h+var_C8]
0x180081c18  lea     rax, aGetoverlayconf_1; "GetOverlayConfigurationInternal"
0x180081c1f  mov     [rbp+57h+var_B0], r15
0x180081c23  mov     [rbp+57h+var_C0], rax
0x180081c27  mov     r8d, 0C00000BBh
0x180081c2d  lea     rcx, [rbp+57h+var_68]
0x180081c31  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081c36  mov     ebx, eax
0x180081c38  lea     rcx, [rbp+57h+var_50]
0x180081c3c  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180081c41  jmp     loc_180081D23
0x180081c46  mov     rcx, [rdi]; String1
0x180081c49  lea     rdx, aOsdevice; "osdevice"
0x180081c50  call    _wcsicmp
0x180081c55  test    eax, eax
0x180081c57  jz      short loc_180081C81
0x180081c59  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081c60  mov     [rbp+57h+var_98], 4BAh
0x180081c68  mov     [rbp+57h+var_A8], rax
0x180081c6c  lea     rdx, [rbp+57h+var_A8]
0x180081c70  lea     rax, aGetoverlayconf_1; "GetOverlayConfigurationInternal"
0x180081c77  mov     [rbp+57h+var_90], r15
0x180081c7b  mov     [rbp+57h+var_A0], rax
0x180081c7f  jmp     short loc_180081C27
0x180081c81  mov     rdx, [rdi]; wchar_t *
0x180081c84  lea     r8, [rsp+110h+var_D8]; void **
0x180081c89  mov     rcx, rbx; void *
0x180081c8c  mov     [rsp+110h+var_D8], r15
0x180081c91  call    ?OuOpenKey@@YAJPEAXPEB_WPEAPEAX@Z; OuOpenKey(void *,wchar_t const *,void * *)
0x180081c96  mov     ebx, eax
0x180081c98  test    eax, eax
0x180081c9a  jns     short loc_180081CA8
0x180081c9c  lea     rcx, [rsp+110h+var_D8]; this
0x180081ca1  call    ??1AutoOuKeyHandle@@QEAA@XZ; AutoOuKeyHandle::~AutoOuKeyHandle(void)
0x180081ca6  jmp     short loc_180081C38
0x180081ca8  mov     r9, [rsp+110h+var_D8]
0x180081cad  lea     rdx, [rbp+57h+var_60]
0x180081cb1  mov     ecx, [rbp+57h+var_D0]
0x180081cb4  mov     r8, rdi
0x180081cb7  call    ?LoadDeviceEntries@@YAJW4ConfigurationVersion@@AEAVAutoOverlayConfigurationPtr@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; LoadDeviceEntries(ConfigurationVersion,AutoOverlayConfigurationPtr &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,void *)
0x180081cbc  lea     rcx, [rsp+110h+var_D8]; this
0x180081cc1  mov     ebx, eax
0x180081cc3  test    eax, eax
0x180081cc5  js      short loc_180081CA1
0x180081cc7  call    ??1AutoOuKeyHandle@@QEAA@XZ; AutoOuKeyHandle::~AutoOuKeyHandle(void)
0x180081ccc  lea     rcx, [rbp+57h+var_50]
0x180081cd0  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180081cd5  mov     rax, [rbp+57h+var_60]
0x180081cd9  mov     ebx, r15d
0x180081cdc  mov     [r14], rax
0x180081cdf  mov     [rbp+57h+var_60], r15
0x180081ce3  jmp     short loc_180081D23
0x180081ce5  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081cec  mov     [rbp+57h+var_78], 4A4h
0x180081cf4  mov     [rbp+57h+var_88], rax
0x180081cf8  lea     rdx, [rbp+57h+var_88]
0x180081cfc  lea     rax, aGetoverlayconf_1; "GetOverlayConfigurationInternal"
0x180081d03  mov     r8d, 0C0000017h
0x180081d09  mov     [rbp+57h+var_80], rax
0x180081d0d  lea     rax, aConfigout; "ConfigOut"
0x180081d14  mov     [rbp+57h+var_70], rax
0x180081d18  lea     rcx, [rbp+57h+var_68]
0x180081d1c  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081d21  mov     ebx, eax
0x180081d23  lea     rcx, [rbp+57h+var_58]
0x180081d27  call    ??1?$unique_ptr@UOVERLAY_CONFIGURATION@@U?$default_delete@UOVERLAY_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CONFIGURATION,utl::default_delete<OVERLAY_CONFIGURATION>>::~unique_ptr<OVERLAY_CONFIGURATION,utl::default_delete<OVERLAY_CONFIGURATION>>(void)
0x180081d2c  lea     rcx, [rbp+57h+var_60]; this
0x180081d30  call    ??1AutoOverlayConfigurationPtr@@QEAA@XZ; AutoOverlayConfigurationPtr::~AutoOverlayConfigurationPtr(void)
0x180081d35  mov     eax, ebx
0x180081d37  mov     rcx, [rbp+57h+var_30]
0x180081d3b  xor     rcx, rsp; StackCookie
0x180081d3e  call    __security_check_cookie
0x180081d43  mov     rbx, [rsp+110h+arg_0]
0x180081d4b  add     rsp, 0F0h
0x180081d52  pop     r15
0x180081d54  pop     r14
0x180081d56  pop     r12
0x180081d58  pop     rdi
0x180081d59  pop     rbp
0x180081d5a  retn
```
