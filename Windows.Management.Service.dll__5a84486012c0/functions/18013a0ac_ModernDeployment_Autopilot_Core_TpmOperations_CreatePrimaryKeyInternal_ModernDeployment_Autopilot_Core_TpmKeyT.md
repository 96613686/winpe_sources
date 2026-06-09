# ModernDeployment::Autopilot::Core::TpmOperations::CreatePrimaryKeyInternal(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18013a0ac`
- end: `0x18013a761`
- name: `?CreatePrimaryKeyInternal@TpmOperations@Core@Autopilot@ModernDeployment@@IEAAJW4IdkKeyType@TpmKeyTypes@234@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1717`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x18013878c`

## callees

- `0x18000b820`
- `0x18000bd50`
- `0x18000c414`
- `0x180067a54`
- `0x180068ff8`
- `0x18007755c`
- `0x1800801fc`
- `0x1800839bc`
- `0x1800b2220`
- `0x1801342f4`
- `0x180137338`
- `0x18013a0ac`
- `0x18013b794`
- `0x18013c348`
- `0x18013c750`
- `0x180145d90`
- `0x18015faac`
- `0x180160224`
- `0x180166688`
- `0x1801681a4`
- `0x18016cbf0`
- `0x18016cd44`

## string_xrefs

- `0x18013a102`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a13c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a1b5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a226`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a2b5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a2f8`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a365`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a3ab`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a3ec`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a437`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a49c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a4d1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a540`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a5ae`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a613`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a6a8`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a715`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a0ee`: `Feature_AutopilotDeviceTagging is not enabled — CreatePrimaryKeyInternal skipped.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::TpmOperations::CreatePrimaryKeyInternal(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  int IsEccKeyType; // eax
  unsigned int v8; // ebx
  tpm12class::TPMW8T_PUBLIC *v9; // rax
  __int64 v10; // rax
  int IdkTemplate; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  size_t v14; // rax
  size_t v15; // r8
  size_t v16; // r8
  int v17; // eax
  unsigned int v18; // ebx
  int HandleIdFromKeyType; // eax
  unsigned int v20; // ebx
  int v21; // eax
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  int PublicKeyId; // eax
  unsigned int v27; // ebx
  int GuidFromGuidString; // eax
  unsigned int v29; // ebx
  int v30; // ebx
  int v31; // [rsp+20h] [rbp-328h]
  const char *v32; // [rsp+28h] [rbp-320h]
  _BYTE v33[4]; // [rsp+30h] [rbp-318h] BYREF
  unsigned int v34; // [rsp+34h] [rbp-314h] BYREF
  int v35[2]; // [rsp+38h] [rbp-310h] BYREF
  _BYTE v36[32]; // [rsp+40h] [rbp-308h] BYREF
  _BYTE v37[32]; // [rsp+60h] [rbp-2E8h] BYREF
  _BYTE v38[200]; // [rsp+80h] [rbp-2C8h] BYREF
  int v39; // [rsp+148h] [rbp-200h]
  __int64 v40; // [rsp+1A0h] [rbp-1A8h]
  int v41; // [rsp+238h] [rbp-110h]
  __int64 v42; // [rsp+240h] [rbp-108h]
  unsigned __int16 v43; // [rsp+2D8h] [rbp-70h]
  __int64 v44; // [rsp+2E0h] [rbp-68h]
  _OWORD v45[2]; // [rsp+2F0h] [rbp-58h] BYREF
  __int128 v46; // [rsp+310h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)0x80004001LL,
      (int)"Feature_AutopilotDeviceTagging is not enabled — CreatePrimaryKeyInternal skipped.",
      v32);
    return 2147500033LL;
  }
  v33[0] = 0;
  IsEccKeyType = ModernDeployment::Autopilot::Core::TpmKeyTypes::IsEccKeyType(a2, v33);
  v8 = IsEccKeyType;
  if ( IsEccKeyType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)(unsigned int)IsEccKeyType,
      v31);
    return v8;
  }
  tpm12class::TPMW8_CreatePrimary::TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
  v9 = (tpm12class::TPMW8T_PUBLIC *)operator new(0x340u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)v35 = v9;
  if ( !v9 )
  {
    v40 = 0;
    goto LABEL_39;
  }
  v10 = tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(v9);
  v40 = v10;
  if ( !v10 )
  {
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x301,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)0x8007000ELL,
      v31);
    tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
    return 2147942414LL;
  }
  IdkTemplate = ModernDeployment::Autopilot::Core::TpmClassHelpers::GetIdkTemplate(a2, v10);
  v12 = IdkTemplate;
  if ( IdkTemplate < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x303,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)(unsigned int)IdkTemplate,
      v31);
    tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
    return v12;
  }
  v39 = 1073741835;
  v13 = *(_QWORD *)(a3 + 8);
  if ( *(_QWORD *)a3 != v13 )
  {
    v14 = v13 - *(_QWORD *)a3;
    if ( v33[0] )
    {
      v15 = *(unsigned __int16 *)(v40 + 544);
      if ( v14 > v15 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x314,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
          (const char *)0x80070057LL,
          v31);
        tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
        return 2147942487LL;
      }
      memset_0(*(void **)(v40 + 552), 0, v15);
      memset_0(*(void **)(v40 + 624), 0, *(unsigned __int16 *)(v40 + 616));
      if ( memcpy_s(
             *(void *const *)(v40 + 552),
             *(unsigned __int16 *)(v40 + 544),
             *(const void *const *)a3,
             *(_QWORD *)(a3 + 8) - *(_QWORD *)a3) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31D,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
          (const char *)0x8007006FLL,
          v31);
        tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
        return 2147942511LL;
      }
    }
    else
    {
      v16 = *(unsigned __int16 *)(v40 + 816);
      if ( v14 > v16 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x323,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
          (const char *)0x80070057LL,
          v31);
        tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
        return 2147942487LL;
      }
      memset_0(*(void **)(v40 + 824), 0, v16);
      if ( memcpy_s(
             *(void *const *)(v40 + 824),
             *(unsigned __int16 *)(v40 + 816),
             *(const void *const *)a3,
             *(_QWORD *)(a3 + 8) - *(_QWORD *)a3) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32A,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
          (const char *)0x8007006FLL,
          v31);
        tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
        return 2147942511LL;
      }
    }
  }
  v17 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v38, 0);
  v18 = v17;
  if ( v17 >= 0 )
  {
    if ( v42 )
    {
      v34 = 0;
      HandleIdFromKeyType = ModernDeployment::Autopilot::Core::TpmKeyTypes::GetHandleIdFromKeyType(a2, &v34);
      v20 = HandleIdFromKeyType;
      if ( HandleIdFromKeyType >= 0 )
      {
        v21 = v41;
        *(_DWORD *)(a1 + 280) = v41;
        *(_DWORD *)(a1 + 284) = v21;
        v22 = ModernDeployment::Autopilot::Core::TpmClassHelpers::PersistKeyToStorage(
                (struct tpm12class::TPMW8_CreatePrimary *)v38,
                v34);
        v23 = v22;
        if ( v22 == -2144861877 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x33D,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)0x8103C00ALL,
            v31);
          tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
          return 2164506634LL;
        }
        else if ( v22 >= 0 )
        {
          *(_QWORD *)v35 = v42;
          v24 = ModernDeployment::Autopilot::Core::TpmOperations::PopulateIdkKeyWrapper(a1, v34, v44, v43);
          v25 = v24;
          if ( v24 >= 0 )
          {
            v45[0] = 0;
            v45[1] = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v45[0]) = 0;
            PublicKeyId = ModernDeployment::Autopilot::Core::TpmKeyWrapper::GetPublicKeyId(a1 + 8, v45);
            v27 = PublicKeyId;
            if ( PublicKeyId >= 0 )
            {
              v46 = 0;
              GuidFromGuidString = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidFromGuidString(
                                     v45,
                                     &v46);
              v29 = GuidFromGuidString;
              if ( GuidFromGuidString >= 0 )
              {
                std::wstring::wstring(v37, L"{B3DE75DA-819C-4FD5-9F01-C3D49E8CBBD7}");
                std::wstring::wstring(v36, L"IdkKeyId");
                v30 = ModernDeployment::Autopilot::Core::DeviceLinkUefi::StoreGuidToUefi(v36, v37, &v46);
                std::wstring::_Tidy_deallocate(v36);
                std::wstring::_Tidy_deallocate(v37);
                if ( v30 >= 0 )
                {
                  std::wstring::_Tidy_deallocate(v45);
                  tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x352,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
                    (const char *)(unsigned int)v30,
                    (int)v35);
                  std::wstring::_Tidy_deallocate(v45);
                  tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
                  return (unsigned int)v30;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x34D,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
                  (const char *)(unsigned int)GuidFromGuidString,
                  (int)v35);
                std::wstring::_Tidy_deallocate(v45);
                tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
                return v29;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x34A,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
                (const char *)(unsigned int)PublicKeyId,
                (int)v35);
              std::wstring::_Tidy_deallocate(v45);
              tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
              return v27;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x346,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
              (const char *)(unsigned int)v24,
              (int)v35);
            tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
            return v25;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x33F,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)v22,
            v31);
          tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
          return v23;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x333,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
          (const char *)(unsigned int)HandleIdFromKeyType,
          v31);
        tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
        return v20;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x330,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
        (const char *)0xD00000E5LL,
        v31);
      tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
      return 3489661157LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)(unsigned int)v17,
      v31);
    tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary((tpm12class::TPMW8_CreatePrimary *)v38);
    return v18;
  }
}

```

## disassembly

```asm
0x18013a0ac  mov     [rsp+arg_18], rbx
0x18013a0b1  push    rsi
0x18013a0b2  push    rdi
0x18013a0b3  push    r14
0x18013a0b5  sub     rsp, 330h
0x18013a0bc  mov     rax, cs:__security_cookie
0x18013a0c3  xor     rax, rsp
0x18013a0c6  mov     [rsp+348h+var_28], rax
0x18013a0ce  mov     rdi, r8
0x18013a0d1  mov     esi, edx
0x18013a0d3  mov     r14, rcx
0x18013a0d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18013a0dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18013a0e2  test    al, al
0x18013a0e4  jnz     short loc_18013A11A
0x18013a0e6  mov     rcx, [rsp+348h]; this
0x18013a0ee  lea     rax, aFeatureAutopil; "Feature_AutopilotDeviceTagging is not e"...
0x18013a0f5  mov     qword ptr [rsp+348h+var_328], rax; int
0x18013a0fa  mov     ebx, 80004001h
0x18013a0ff  mov     r9d, ebx; char *
0x18013a102  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a109  mov     edx, 2EFh; void *
0x18013a10e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18013a113  mov     eax, ebx
0x18013a115  jmp     loc_18013A73C
0x18013a11a  mov     [rsp+348h+var_318], 0
0x18013a11f  lea     rdx, [rsp+348h+var_318]
0x18013a124  mov     ecx, esi
0x18013a126  call    ?IsEccKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJW4IdkKeyType@1234@AEA_N@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::IsEccKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,bool &)
0x18013a12b  mov     ebx, eax
0x18013a12d  test    eax, eax
0x18013a12f  jns     short loc_18013A154
0x18013a131  mov     rcx, [rsp+348h]; this
0x18013a139  mov     r9d, eax; char *
0x18013a13c  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a143  mov     edx, 2FBh; void *
0x18013a148  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a14d  mov     eax, ebx
0x18013a14f  jmp     loc_18013A73C
0x18013a154  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a15c  call    ??0TPMW8_CreatePrimary@tpm12class@@QEAA@XZ; tpm12class::TPMW8_CreatePrimary::TPMW8_CreatePrimary(void)
0x18013a161  nop
0x18013a162  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18013a169  mov     ecx, 340h; unsigned __int64
0x18013a16e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18013a173  mov     qword ptr [rsp+348h+var_310], rax
0x18013a178  test    rax, rax
0x18013a17b  jz      loc_18013A6F9
0x18013a181  mov     rcx, rax; this
0x18013a184  call    ??0TPMW8T_PUBLIC@tpm12class@@QEAA@XZ; tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(void)
0x18013a189  mov     [rsp+348h+var_1A8], rax
0x18013a191  test    rax, rax
0x18013a194  jz      loc_18013A705
0x18013a19a  mov     rdx, rax
0x18013a19d  mov     ecx, esi
0x18013a19f  call    ?GetIdkTemplate@TpmClassHelpers@Core@Autopilot@ModernDeployment@@SAJW4IdkKeyType@TpmKeyTypes@234@AEAVTPMW8T_PUBLIC@tpm12class@@@Z; ModernDeployment::Autopilot::Core::TpmClassHelpers::GetIdkTemplate(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,tpm12class::TPMW8T_PUBLIC &)
0x18013a1a4  mov     ebx, eax
0x18013a1a6  test    eax, eax
0x18013a1a8  jns     short loc_18013A1DB
0x18013a1aa  mov     rcx, [rsp+348h]; this
0x18013a1b2  mov     r9d, eax; char *
0x18013a1b5  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a1bc  mov     edx, 303h; void *
0x18013a1c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a1c6  nop
0x18013a1c7  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a1cf  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a1d4  mov     eax, ebx
0x18013a1d6  jmp     loc_18013A73C
0x18013a1db  mov     [rsp+348h+var_200], 4000000Bh
0x18013a1e6  mov     rax, [rdi+8]
0x18013a1ea  cmp     [rdi], rax
0x18013a1ed  jz      loc_18013A38B
0x18013a1f3  sub     rax, [rdi]
0x18013a1f6  mov     rcx, [rsp+348h+var_1A8]
0x18013a1fe  cmp     [rsp+348h+var_318], 0
0x18013a203  jz      loc_18013A2DB
0x18013a209  movzx   r8d, word ptr [rcx+220h]; Size
0x18013a211  cmp     rax, r8
0x18013a214  jbe     short loc_18013A24C
0x18013a216  mov     rcx, [rsp+348h]; this
0x18013a21e  mov     ebx, 80070057h
0x18013a223  mov     r9d, ebx; char *
0x18013a226  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a22d  mov     edx, 314h; void *
0x18013a232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a237  nop
0x18013a238  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a240  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a245  mov     eax, ebx
0x18013a247  jmp     loc_18013A73C
0x18013a24c  xor     edx, edx; Val
0x18013a24e  mov     rcx, [rcx+228h]; void *
0x18013a255  call    memset_0
0x18013a25a  mov     rcx, [rsp+348h+var_1A8]
0x18013a262  movzx   r8d, word ptr [rcx+268h]; Size
0x18013a26a  xor     edx, edx; Val
0x18013a26c  mov     rcx, [rcx+270h]; void *
0x18013a273  call    memset_0
0x18013a278  mov     r9, [rdi+8]
0x18013a27c  sub     r9, [rdi]; SourceSize
0x18013a27f  mov     rcx, [rsp+348h+var_1A8]
0x18013a287  movzx   edx, word ptr [rcx+220h]; DestinationSize
0x18013a28e  mov     r8, [rdi]; Source
0x18013a291  mov     rcx, [rcx+228h]; Destination
0x18013a298  call    memcpy_s
0x18013a29d  test    eax, eax
0x18013a29f  jz      loc_18013A38B
0x18013a2a5  mov     rcx, [rsp+348h]; this
0x18013a2ad  mov     ebx, 8007006Fh
0x18013a2b2  mov     r9d, ebx; char *
0x18013a2b5  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a2bc  mov     edx, 31Dh; void *
0x18013a2c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a2c6  nop
0x18013a2c7  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a2cf  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a2d4  mov     eax, ebx
0x18013a2d6  jmp     loc_18013A73C
0x18013a2db  movzx   r8d, word ptr [rcx+330h]; Size
0x18013a2e3  cmp     rax, r8
0x18013a2e6  jbe     short loc_18013A31E
0x18013a2e8  mov     rcx, [rsp+348h]; this
0x18013a2f0  mov     ebx, 80070057h
0x18013a2f5  mov     r9d, ebx; char *
0x18013a2f8  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a2ff  mov     edx, 323h; void *
0x18013a304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a309  nop
0x18013a30a  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a312  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a317  mov     eax, ebx
0x18013a319  jmp     loc_18013A73C
0x18013a31e  xor     edx, edx; Val
0x18013a320  mov     rcx, [rcx+338h]; void *
0x18013a327  call    memset_0
0x18013a32c  mov     r9, [rdi+8]
0x18013a330  sub     r9, [rdi]; SourceSize
0x18013a333  mov     rcx, [rsp+348h+var_1A8]
0x18013a33b  movzx   edx, word ptr [rcx+330h]; DestinationSize
0x18013a342  mov     r8, [rdi]; Source
0x18013a345  mov     rcx, [rcx+338h]; Destination
0x18013a34c  call    memcpy_s
0x18013a351  test    eax, eax
0x18013a353  jz      short loc_18013A38B
0x18013a355  mov     rcx, [rsp+348h]; this
0x18013a35d  mov     ebx, 8007006Fh
0x18013a362  mov     r9d, ebx; char *
0x18013a365  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a36c  mov     edx, 32Ah; void *
0x18013a371  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a376  nop
0x18013a377  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a37f  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a384  mov     eax, ebx
0x18013a386  jmp     loc_18013A73C
0x18013a38b  xor     edx, edx; void *
0x18013a38d  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a395  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x18013a39a  mov     ebx, eax
0x18013a39c  test    eax, eax
0x18013a39e  jns     short loc_18013A3D1
0x18013a3a0  mov     rcx, [rsp+348h]; this
0x18013a3a8  mov     r9d, eax; char *
0x18013a3ab  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a3b2  mov     edx, 32Fh; void *
0x18013a3b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a3bc  nop
0x18013a3bd  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a3c5  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a3ca  mov     eax, ebx
0x18013a3cc  jmp     loc_18013A73C
0x18013a3d1  cmp     [rsp+348h+var_108], 0
0x18013a3da  jnz     short loc_18013A412
0x18013a3dc  mov     rcx, [rsp+348h]; this
0x18013a3e4  mov     ebx, 0D00000E5h
0x18013a3e9  mov     r9d, ebx; char *
0x18013a3ec  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a3f3  mov     edx, 330h; void *
0x18013a3f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a3fd  nop
0x18013a3fe  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a406  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a40b  mov     eax, ebx
0x18013a40d  jmp     loc_18013A73C
0x18013a412  mov     [rsp+348h+var_314], 0
0x18013a41a  lea     rdx, [rsp+348h+var_314]
0x18013a41f  mov     ecx, esi
0x18013a421  call    ?GetHandleIdFromKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJW4IdkKeyType@1234@AEAW4IdkHandleId@1234@@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::GetHandleIdFromKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkHandleId &)
0x18013a426  mov     ebx, eax
0x18013a428  test    eax, eax
0x18013a42a  jns     short loc_18013A45D
0x18013a42c  mov     rcx, [rsp+348h]; this
0x18013a434  mov     r9d, eax; char *
0x18013a437  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a43e  mov     edx, 333h; void *
0x18013a443  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a448  nop
0x18013a449  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a451  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a456  mov     eax, ebx
0x18013a458  jmp     loc_18013A73C
0x18013a45d  mov     eax, [rsp+348h+var_110]
0x18013a464  mov     [r14+118h], eax
0x18013a46b  mov     [r14+11Ch], eax
0x18013a472  mov     edx, [rsp+348h+var_314]; unsigned int
0x18013a476  lea     rcx, [rsp+348h+var_2C8]; struct tpm12class::TPMW8_CreatePrimary *
0x18013a47e  call    ?PersistKeyToStorage@TpmClassHelpers@Core@Autopilot@ModernDeployment@@SAJPEAVTPMW8_CreatePrimary@tpm12class@@I@Z; ModernDeployment::Autopilot::Core::TpmClassHelpers::PersistKeyToStorage(tpm12class::TPMW8_CreatePrimary *,uint)
0x18013a483  mov     ebx, eax
0x18013a485  cmp     eax, 8028014Bh
0x18013a48a  jnz     short loc_18013A4C2
0x18013a48c  mov     rcx, [rsp+348h]; this
0x18013a494  mov     ebx, 8103C00Ah
0x18013a499  mov     r9d, ebx; char *
0x18013a49c  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a4a3  mov     edx, 33Dh; void *
0x18013a4a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a4ad  nop
0x18013a4ae  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a4b6  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a4bb  mov     eax, ebx
0x18013a4bd  jmp     loc_18013A73C
0x18013a4c2  test    ebx, ebx
0x18013a4c4  jns     short loc_18013A4F7
0x18013a4c6  mov     rcx, [rsp+348h]; this
0x18013a4ce  mov     r9d, ebx; char *
0x18013a4d1  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a4d8  mov     edx, 33Fh; void *
0x18013a4dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a4e2  nop
0x18013a4e3  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a4eb  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a4f0  mov     eax, ebx
0x18013a4f2  jmp     loc_18013A73C
0x18013a4f7  mov     rax, [rsp+348h+var_108]
0x18013a4ff  mov     qword ptr [rsp+348h+var_310], rax
0x18013a504  movzx   r9d, [rsp+348h+var_70]
0x18013a50d  mov     dword ptr [rsp+348h+var_320], esi
0x18013a511  lea     rax, [rsp+348h+var_310]
0x18013a516  mov     qword ptr [rsp+348h+var_328], rax; int
0x18013a51b  mov     r8, [rsp+348h+var_68]
0x18013a523  mov     edx, [rsp+348h+var_314]
0x18013a527  mov     rcx, r14
0x18013a52a  call    ?PopulateIdkKeyWrapper@TpmOperations@Core@Autopilot@ModernDeployment@@IEAAJW4IdkHandleId@TpmKeyTypes@234@PEBEKAEBQEAXW4IdkKeyType@6234@@Z; ModernDeployment::Autopilot::Core::TpmOperations::PopulateIdkKeyWrapper(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkHandleId,uchar const *,ulong,void * const &,ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType)
0x18013a52f  mov     ebx, eax
0x18013a531  test    eax, eax
0x18013a533  jns     short loc_18013A566
0x18013a535  mov     rcx, [rsp+348h]; this
0x18013a53d  mov     r9d, eax; char *
0x18013a540  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a547  mov     edx, 346h; void *
0x18013a54c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a551  nop
0x18013a552  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a55a  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a55f  mov     eax, ebx
0x18013a561  jmp     loc_18013A73C
0x18013a566  xorps   xmm0, xmm0
0x18013a569  movups  [rsp+348h+var_58], xmm0
0x18013a571  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18013a579  movdqu  [rsp+348h+var_48], xmm1
0x18013a582  xor     eax, eax
0x18013a584  mov     word ptr [rsp+348h+var_58], ax
0x18013a58c  lea     rcx, [r14+8]
0x18013a590  lea     rdx, [rsp+348h+var_58]
0x18013a598  call    ?GetPublicKeyId@TpmKeyWrapper@Core@Autopilot@ModernDeployment@@QEBAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::TpmKeyWrapper::GetPublicKeyId(std::wstring &)
0x18013a59d  mov     ebx, eax
0x18013a59f  test    eax, eax
0x18013a5a1  jns     short loc_18013A5E2
0x18013a5a3  mov     rcx, [rsp+348h]; this
0x18013a5ab  mov     r9d, eax; char *
0x18013a5ae  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a5b5  mov     edx, 34Ah; void *
0x18013a5ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a5bf  nop
0x18013a5c0  lea     rcx, [rsp+348h+var_58]
0x18013a5c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a5cd  nop
0x18013a5ce  lea     rcx, [rsp+348h+var_2C8]; this
0x18013a5d6  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013a5db  mov     eax, ebx
0x18013a5dd  jmp     loc_18013A73C
0x18013a5e2  xorps   xmm0, xmm0
0x18013a5e5  movups  [rsp+348h+var_38], xmm0
0x18013a5ed  lea     rdx, [rsp+348h+var_38]
0x18013a5f5  lea     rcx, [rsp+348h+var_58]
0x18013a5fd  call    ?GetGuidFromGuidString@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidFromGuidString(std::wstring const &,_GUID &)
0x18013a602  mov     ebx, eax
0x18013a604  test    eax, eax
0x18013a606  jns     short loc_18013A647
0x18013a608  mov     rcx, [rsp+348h]; this
0x18013a610  mov     r9d, eax; char *
0x18013a613  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013a61a  mov     edx, 34Dh; void *
0x18013a61f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a624  nop
0x18013a625  lea     rcx, [rsp+348h+var_58]
0x18013a62d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a632  nop
0x18013a633  lea     rcx, [rsp+348h+var_2C8]; this
  ... truncated ...
```
