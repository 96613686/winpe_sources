# ModernDeployment::Autopilot::Core::TpmOperations::CreatePrimaryKeyInternal(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18013e0e8`
- end: `0x18013e79d`
- name: `?CreatePrimaryKeyInternal@TpmOperations@Core@Autopilot@ModernDeployment@@IEAAJW4IdkKeyType@TpmKeyTypes@234@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1717`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x18013c784`

## callees

- `0x18000b8f0`
- `0x18000be20`
- `0x18000c504`
- `0x180067e54`
- `0x1800694e8`
- `0x180077de0`
- `0x180080c10`
- `0x180084574`
- `0x1800b3da0`
- `0x180138180`
- `0x18013b2b4`
- `0x18013e0e8`
- `0x18013f800`
- `0x1801403c4`
- `0x1801407d8`
- `0x180149c84`
- `0x180163e54`
- `0x1801645d0`
- `0x18016ab88`
- `0x18016c6c4`
- `0x180171160`
- `0x1801712b4`

## string_xrefs

- `0x18013e13e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e178`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e1f1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e262`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e2f1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e334`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e3a1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e3e7`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e428`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e473`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e4d8`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e50d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e57c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e5ea`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e64f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e6e4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e751`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e12a`: `Feature_AutopilotDeviceTagging is not enabled — CreatePrimaryKeyInternal skipped.`

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
0x18013e0e8  mov     [rsp+arg_18], rbx
0x18013e0ed  push    rsi
0x18013e0ee  push    rdi
0x18013e0ef  push    r14
0x18013e0f1  sub     rsp, 330h
0x18013e0f8  mov     rax, cs:__security_cookie
0x18013e0ff  xor     rax, rsp
0x18013e102  mov     [rsp+348h+var_28], rax
0x18013e10a  mov     rdi, r8
0x18013e10d  mov     esi, edx
0x18013e10f  mov     r14, rcx
0x18013e112  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18013e119  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18013e11e  test    al, al
0x18013e120  jnz     short loc_18013E156
0x18013e122  mov     rcx, [rsp+348h]; this
0x18013e12a  lea     rax, aFeatureAutopil; "Feature_AutopilotDeviceTagging is not e"...
0x18013e131  mov     qword ptr [rsp+348h+var_328], rax; int
0x18013e136  mov     ebx, 80004001h
0x18013e13b  mov     r9d, ebx; char *
0x18013e13e  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e145  mov     edx, 2EFh; void *
0x18013e14a  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18013e14f  mov     eax, ebx
0x18013e151  jmp     loc_18013E778
0x18013e156  mov     [rsp+348h+var_318], 0
0x18013e15b  lea     rdx, [rsp+348h+var_318]
0x18013e160  mov     ecx, esi
0x18013e162  call    ?IsEccKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJW4IdkKeyType@1234@AEA_N@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::IsEccKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,bool &)
0x18013e167  mov     ebx, eax
0x18013e169  test    eax, eax
0x18013e16b  jns     short loc_18013E190
0x18013e16d  mov     rcx, [rsp+348h]; this
0x18013e175  mov     r9d, eax; char *
0x18013e178  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e17f  mov     edx, 2FBh; void *
0x18013e184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e189  mov     eax, ebx
0x18013e18b  jmp     loc_18013E778
0x18013e190  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e198  call    ??0TPMW8_CreatePrimary@tpm12class@@QEAA@XZ; tpm12class::TPMW8_CreatePrimary::TPMW8_CreatePrimary(void)
0x18013e19d  nop
0x18013e19e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18013e1a5  mov     ecx, 340h; unsigned __int64
0x18013e1aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18013e1af  mov     qword ptr [rsp+348h+var_310], rax
0x18013e1b4  test    rax, rax
0x18013e1b7  jz      loc_18013E735
0x18013e1bd  mov     rcx, rax; this
0x18013e1c0  call    ??0TPMW8T_PUBLIC@tpm12class@@QEAA@XZ; tpm12class::TPMW8T_PUBLIC::TPMW8T_PUBLIC(void)
0x18013e1c5  mov     [rsp+348h+var_1A8], rax
0x18013e1cd  test    rax, rax
0x18013e1d0  jz      loc_18013E741
0x18013e1d6  mov     rdx, rax
0x18013e1d9  mov     ecx, esi
0x18013e1db  call    ?GetIdkTemplate@TpmClassHelpers@Core@Autopilot@ModernDeployment@@SAJW4IdkKeyType@TpmKeyTypes@234@AEAVTPMW8T_PUBLIC@tpm12class@@@Z; ModernDeployment::Autopilot::Core::TpmClassHelpers::GetIdkTemplate(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,tpm12class::TPMW8T_PUBLIC &)
0x18013e1e0  mov     ebx, eax
0x18013e1e2  test    eax, eax
0x18013e1e4  jns     short loc_18013E217
0x18013e1e6  mov     rcx, [rsp+348h]; this
0x18013e1ee  mov     r9d, eax; char *
0x18013e1f1  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e1f8  mov     edx, 303h; void *
0x18013e1fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e202  nop
0x18013e203  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e20b  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e210  mov     eax, ebx
0x18013e212  jmp     loc_18013E778
0x18013e217  mov     [rsp+348h+var_200], 4000000Bh
0x18013e222  mov     rax, [rdi+8]
0x18013e226  cmp     [rdi], rax
0x18013e229  jz      loc_18013E3C7
0x18013e22f  sub     rax, [rdi]
0x18013e232  mov     rcx, [rsp+348h+var_1A8]
0x18013e23a  cmp     [rsp+348h+var_318], 0
0x18013e23f  jz      loc_18013E317
0x18013e245  movzx   r8d, word ptr [rcx+220h]; Size
0x18013e24d  cmp     rax, r8
0x18013e250  jbe     short loc_18013E288
0x18013e252  mov     rcx, [rsp+348h]; this
0x18013e25a  mov     ebx, 80070057h
0x18013e25f  mov     r9d, ebx; char *
0x18013e262  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e269  mov     edx, 314h; void *
0x18013e26e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e273  nop
0x18013e274  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e27c  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e281  mov     eax, ebx
0x18013e283  jmp     loc_18013E778
0x18013e288  xor     edx, edx; Val
0x18013e28a  mov     rcx, [rcx+228h]; void *
0x18013e291  call    memset_0
0x18013e296  mov     rcx, [rsp+348h+var_1A8]
0x18013e29e  movzx   r8d, word ptr [rcx+268h]; Size
0x18013e2a6  xor     edx, edx; Val
0x18013e2a8  mov     rcx, [rcx+270h]; void *
0x18013e2af  call    memset_0
0x18013e2b4  mov     r9, [rdi+8]
0x18013e2b8  sub     r9, [rdi]; SourceSize
0x18013e2bb  mov     rcx, [rsp+348h+var_1A8]
0x18013e2c3  movzx   edx, word ptr [rcx+220h]; DestinationSize
0x18013e2ca  mov     r8, [rdi]; Source
0x18013e2cd  mov     rcx, [rcx+228h]; Destination
0x18013e2d4  call    memcpy_s
0x18013e2d9  test    eax, eax
0x18013e2db  jz      loc_18013E3C7
0x18013e2e1  mov     rcx, [rsp+348h]; this
0x18013e2e9  mov     ebx, 8007006Fh
0x18013e2ee  mov     r9d, ebx; char *
0x18013e2f1  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e2f8  mov     edx, 31Dh; void *
0x18013e2fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e302  nop
0x18013e303  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e30b  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e310  mov     eax, ebx
0x18013e312  jmp     loc_18013E778
0x18013e317  movzx   r8d, word ptr [rcx+330h]; Size
0x18013e31f  cmp     rax, r8
0x18013e322  jbe     short loc_18013E35A
0x18013e324  mov     rcx, [rsp+348h]; this
0x18013e32c  mov     ebx, 80070057h
0x18013e331  mov     r9d, ebx; char *
0x18013e334  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e33b  mov     edx, 323h; void *
0x18013e340  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e345  nop
0x18013e346  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e34e  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e353  mov     eax, ebx
0x18013e355  jmp     loc_18013E778
0x18013e35a  xor     edx, edx; Val
0x18013e35c  mov     rcx, [rcx+338h]; void *
0x18013e363  call    memset_0
0x18013e368  mov     r9, [rdi+8]
0x18013e36c  sub     r9, [rdi]; SourceSize
0x18013e36f  mov     rcx, [rsp+348h+var_1A8]
0x18013e377  movzx   edx, word ptr [rcx+330h]; DestinationSize
0x18013e37e  mov     r8, [rdi]; Source
0x18013e381  mov     rcx, [rcx+338h]; Destination
0x18013e388  call    memcpy_s
0x18013e38d  test    eax, eax
0x18013e38f  jz      short loc_18013E3C7
0x18013e391  mov     rcx, [rsp+348h]; this
0x18013e399  mov     ebx, 8007006Fh
0x18013e39e  mov     r9d, ebx; char *
0x18013e3a1  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e3a8  mov     edx, 32Ah; void *
0x18013e3ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e3b2  nop
0x18013e3b3  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e3bb  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e3c0  mov     eax, ebx
0x18013e3c2  jmp     loc_18013E778
0x18013e3c7  xor     edx, edx; void *
0x18013e3c9  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e3d1  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x18013e3d6  mov     ebx, eax
0x18013e3d8  test    eax, eax
0x18013e3da  jns     short loc_18013E40D
0x18013e3dc  mov     rcx, [rsp+348h]; this
0x18013e3e4  mov     r9d, eax; char *
0x18013e3e7  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e3ee  mov     edx, 32Fh; void *
0x18013e3f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e3f8  nop
0x18013e3f9  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e401  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e406  mov     eax, ebx
0x18013e408  jmp     loc_18013E778
0x18013e40d  cmp     [rsp+348h+var_108], 0
0x18013e416  jnz     short loc_18013E44E
0x18013e418  mov     rcx, [rsp+348h]; this
0x18013e420  mov     ebx, 0D00000E5h
0x18013e425  mov     r9d, ebx; char *
0x18013e428  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e42f  mov     edx, 330h; void *
0x18013e434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e439  nop
0x18013e43a  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e442  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e447  mov     eax, ebx
0x18013e449  jmp     loc_18013E778
0x18013e44e  mov     [rsp+348h+var_314], 0
0x18013e456  lea     rdx, [rsp+348h+var_314]
0x18013e45b  mov     ecx, esi
0x18013e45d  call    ?GetHandleIdFromKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJW4IdkKeyType@1234@AEAW4IdkHandleId@1234@@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::GetHandleIdFromKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkHandleId &)
0x18013e462  mov     ebx, eax
0x18013e464  test    eax, eax
0x18013e466  jns     short loc_18013E499
0x18013e468  mov     rcx, [rsp+348h]; this
0x18013e470  mov     r9d, eax; char *
0x18013e473  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e47a  mov     edx, 333h; void *
0x18013e47f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e484  nop
0x18013e485  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e48d  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e492  mov     eax, ebx
0x18013e494  jmp     loc_18013E778
0x18013e499  mov     eax, [rsp+348h+var_110]
0x18013e4a0  mov     [r14+118h], eax
0x18013e4a7  mov     [r14+11Ch], eax
0x18013e4ae  mov     edx, [rsp+348h+var_314]; unsigned int
0x18013e4b2  lea     rcx, [rsp+348h+var_2C8]; struct tpm12class::TPMW8_CreatePrimary *
0x18013e4ba  call    ?PersistKeyToStorage@TpmClassHelpers@Core@Autopilot@ModernDeployment@@SAJPEAVTPMW8_CreatePrimary@tpm12class@@I@Z; ModernDeployment::Autopilot::Core::TpmClassHelpers::PersistKeyToStorage(tpm12class::TPMW8_CreatePrimary *,uint)
0x18013e4bf  mov     ebx, eax
0x18013e4c1  cmp     eax, 8028014Bh
0x18013e4c6  jnz     short loc_18013E4FE
0x18013e4c8  mov     rcx, [rsp+348h]; this
0x18013e4d0  mov     ebx, 8103C00Ah
0x18013e4d5  mov     r9d, ebx; char *
0x18013e4d8  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e4df  mov     edx, 33Dh; void *
0x18013e4e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e4e9  nop
0x18013e4ea  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e4f2  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e4f7  mov     eax, ebx
0x18013e4f9  jmp     loc_18013E778
0x18013e4fe  test    ebx, ebx
0x18013e500  jns     short loc_18013E533
0x18013e502  mov     rcx, [rsp+348h]; this
0x18013e50a  mov     r9d, ebx; char *
0x18013e50d  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e514  mov     edx, 33Fh; void *
0x18013e519  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e51e  nop
0x18013e51f  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e527  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e52c  mov     eax, ebx
0x18013e52e  jmp     loc_18013E778
0x18013e533  mov     rax, [rsp+348h+var_108]
0x18013e53b  mov     qword ptr [rsp+348h+var_310], rax
0x18013e540  movzx   r9d, [rsp+348h+var_70]
0x18013e549  mov     dword ptr [rsp+348h+var_320], esi
0x18013e54d  lea     rax, [rsp+348h+var_310]
0x18013e552  mov     qword ptr [rsp+348h+var_328], rax; int
0x18013e557  mov     r8, [rsp+348h+var_68]
0x18013e55f  mov     edx, [rsp+348h+var_314]
0x18013e563  mov     rcx, r14
0x18013e566  call    ?PopulateIdkKeyWrapper@TpmOperations@Core@Autopilot@ModernDeployment@@IEAAJW4IdkHandleId@TpmKeyTypes@234@PEBEKAEBQEAXW4IdkKeyType@6234@@Z; ModernDeployment::Autopilot::Core::TpmOperations::PopulateIdkKeyWrapper(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkHandleId,uchar const *,ulong,void * const &,ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType)
0x18013e56b  mov     ebx, eax
0x18013e56d  test    eax, eax
0x18013e56f  jns     short loc_18013E5A2
0x18013e571  mov     rcx, [rsp+348h]; this
0x18013e579  mov     r9d, eax; char *
0x18013e57c  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e583  mov     edx, 346h; void *
0x18013e588  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e58d  nop
0x18013e58e  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e596  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e59b  mov     eax, ebx
0x18013e59d  jmp     loc_18013E778
0x18013e5a2  xorps   xmm0, xmm0
0x18013e5a5  movups  [rsp+348h+var_58], xmm0
0x18013e5ad  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18013e5b5  movdqu  [rsp+348h+var_48], xmm1
0x18013e5be  xor     eax, eax
0x18013e5c0  mov     word ptr [rsp+348h+var_58], ax
0x18013e5c8  lea     rcx, [r14+8]
0x18013e5cc  lea     rdx, [rsp+348h+var_58]
0x18013e5d4  call    ?GetPublicKeyId@TpmKeyWrapper@Core@Autopilot@ModernDeployment@@QEBAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::TpmKeyWrapper::GetPublicKeyId(std::wstring &)
0x18013e5d9  mov     ebx, eax
0x18013e5db  test    eax, eax
0x18013e5dd  jns     short loc_18013E61E
0x18013e5df  mov     rcx, [rsp+348h]; this
0x18013e5e7  mov     r9d, eax; char *
0x18013e5ea  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e5f1  mov     edx, 34Ah; void *
0x18013e5f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e5fb  nop
0x18013e5fc  lea     rcx, [rsp+348h+var_58]
0x18013e604  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013e609  nop
0x18013e60a  lea     rcx, [rsp+348h+var_2C8]; this
0x18013e612  call    ??1TPMW8_CreatePrimary@tpm12class@@UEAA@XZ; tpm12class::TPMW8_CreatePrimary::~TPMW8_CreatePrimary(void)
0x18013e617  mov     eax, ebx
0x18013e619  jmp     loc_18013E778
0x18013e61e  xorps   xmm0, xmm0
0x18013e621  movups  [rsp+348h+var_38], xmm0
0x18013e629  lea     rdx, [rsp+348h+var_38]
0x18013e631  lea     rcx, [rsp+348h+var_58]
0x18013e639  call    ?GetGuidFromGuidString@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidFromGuidString(std::wstring const &,_GUID &)
0x18013e63e  mov     ebx, eax
0x18013e640  test    eax, eax
0x18013e642  jns     short loc_18013E683
0x18013e644  mov     rcx, [rsp+348h]; this
0x18013e64c  mov     r9d, eax; char *
0x18013e64f  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013e656  mov     edx, 34Dh; void *
0x18013e65b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e660  nop
0x18013e661  lea     rcx, [rsp+348h+var_58]
0x18013e669  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013e66e  nop
0x18013e66f  lea     rcx, [rsp+348h+var_2C8]; this
  ... truncated ...
```
