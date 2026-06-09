# ModernDeployment::Autopilot::Core::Sha256Hasher::Hash(uchar const *,unsigned __int64,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18015c198`
- end: `0x18015c571`
- name: `?Hash@Sha256Hasher@Core@Autopilot@ModernDeployment@@QEBAJPEBE_KAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `985`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180132cec`
- `0x18015da34`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x1800801fc`
- `0x18008b3b4`
- `0x1800a0084`
- `0x1801320e0`
- `0x1801327d0`
- `0x18015c134`
- `0x18015c198`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18015c4aa`
- `bcrypt!BCryptFinishHash` at `0x18015c4aa`
- `bcrypt!BCryptHashData` at `0x18015c385`
- `bcrypt!BCryptHashData` at `0x18015c385`
- `bcrypt!BCryptCreateHash` at `0x18015c31d`
- `bcrypt!BCryptCreateHash` at `0x18015c31d`
- `bcrypt!BCryptGetProperty` at `0x18015c272`
- `bcrypt!BCryptGetProperty` at `0x18015c402`
- `bcrypt!BCryptGetProperty` at `0x18015c272`
- `bcrypt!BCryptGetProperty` at `0x18015c402`

## string_xrefs

- `0x18015c1f9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c226`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c287`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c2cb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c332`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c39a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c417`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c46f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c4bf`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c514`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18015c539`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
int __fastcall ModernDeployment::Autopilot::Core::Sha256Hasher::Hash(
        BCRYPT_ALG_HANDLE *a1,
        __int64 a2,
        unsigned __int64 a3,
        PUCHAR *a4)
{
  BCRYPT_ALG_HANDLE v8; // rcx
  NTSTATUS Property; // eax
  NTSTATUS v11; // eax
  int v12; // ebx
  __int64 v13; // rsi
  ULONG v14; // edi
  NTSTATUS v15; // eax
  int v16; // ebx
  NTSTATUS v17; // eax
  int v18; // ebx
  NTSTATUS v19; // eax
  int v20; // ebx
  int pcbResult; // [rsp+20h] [rbp-98h]
  int pcbResulta; // [rsp+20h] [rbp-98h]
  int pcbResultb; // [rsp+20h] [rbp-98h]
  int pcbResultc; // [rsp+20h] [rbp-98h]
  _BYTE v25[4]; // [rsp+40h] [rbp-78h] BYREF
  ULONG v26; // [rsp+44h] [rbp-74h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-70h] BYREF
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-68h] BYREF
  UCHAR v29[4]; // [rsp+54h] [rbp-64h] BYREF
  PUCHAR pbHashObject[3]; // [rsp+58h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v8 = *a1;
    if ( *a1 )
    {
      if ( a2 )
      {
        if ( a3 )
        {
          *(_DWORD *)pbOutput = 0;
          v26 = 0;
          Property = BCryptGetProperty(v8, L"ObjectLength", pbOutput, 4u, &v26, 0);
          if ( Property >= 0 )
          {
            std::vector<unsigned char>::vector<unsigned char>(pbHashObject, *(unsigned int *)pbOutput, v25);
            if ( pbHashObject[0] )
            {
              phHash = 0;
              v11 = BCryptCreateHash(*a1, &phHash, pbHashObject[0], *(ULONG *)pbOutput, 0, 0, 0);
              if ( v11 >= 0 )
              {
                v13 = 0;
                while ( a3 )
                {
                  v14 = a3;
                  if ( a3 >= 0xFFFFFFFF )
                    v14 = -1;
                  v15 = BCryptHashData(phHash, (PUCHAR)(a2 + v13), v14, 0);
                  if ( v15 < 0 )
                  {
                    v16 = wil::details::in1diag3::Return_NtStatus(
                            retaddr,
                            (void *)0x44,
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
                            (const char *)(unsigned int)v15,
                            pcbResultb);
                    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                    std::vector<unsigned char>::_Tidy(pbHashObject);
                    return v16;
                  }
                  a3 -= v14;
                  v13 += v14;
                }
                *(_DWORD *)v29 = 0;
                v17 = BCryptGetProperty(*a1, L"HashDigestLength", v29, 4u, &v26, 0);
                if ( v17 >= 0 )
                {
                  std::vector<unsigned char>::_Resize<std::_Value_init_tag>(a4, *(unsigned int *)v29, v25);
                  if ( *a4 )
                  {
                    v19 = BCryptFinishHash(phHash, *a4, *(ULONG *)v29, 0);
                    if ( v19 >= 0 )
                    {
                      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                      std::vector<unsigned char>::_Tidy(pbHashObject);
                      return 0;
                    }
                    else
                    {
                      v20 = wil::details::in1diag3::Return_NtStatus(
                              retaddr,
                              (void *)0x58,
                              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
                              (const char *)(unsigned int)v19,
                              pcbResultc);
                      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                      std::vector<unsigned char>::_Tidy(pbHashObject);
                      return v20;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x55,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
                      (const char *)0x8007000ELL,
                      pcbResultc);
                    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                    std::vector<unsigned char>::_Tidy(pbHashObject);
                    return -2147024882;
                  }
                }
                else
                {
                  v18 = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0x52,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
                          (const char *)(unsigned int)v17,
                          pcbResultc);
                  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                  std::vector<unsigned char>::_Tidy(pbHashObject);
                  return v18;
                }
              }
              else
              {
                v12 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x38,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
                        (const char *)(unsigned int)v11,
                        pcbResultb);
                wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
                std::vector<unsigned char>::_Tidy(pbHashObject);
                return v12;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2E,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
                (const char *)0x8007000ELL,
                pcbResulta);
              std::vector<unsigned char>::_Tidy(pbHashObject);
              return -2147024882;
            }
          }
          else
          {
            return wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x2A,
                     (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
                     (const char *)(unsigned int)Property,
                     pcbResulta);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
            (const char *)0x80070057LL,
            pcbResult);
          return -2147024809;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
          (const char *)0x80004003LL,
          pcbResult);
        return -2147467261;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
        (const char *)0x8000FFFFLL,
        pcbResult);
      return -2147418113;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\sha256hasher.cpp",
      (const char *)0x80004001LL,
      pcbResult);
    return -2147467263;
  }
}

```

## disassembly

```asm
0x18015c198  push    rbx
0x18015c19a  push    rsi
0x18015c19b  push    rdi
0x18015c19c  push    r12
0x18015c19e  push    r14
0x18015c1a0  push    r15
0x18015c1a2  sub     rsp, 88h
0x18015c1a9  mov     rax, cs:__security_cookie
0x18015c1b0  xor     rax, rsp
0x18015c1b3  mov     [rsp+0B8h+var_48], rax
0x18015c1b8  mov     r14, r9
0x18015c1bb  mov     rbx, r8
0x18015c1be  mov     r12, rdx
0x18015c1c1  mov     r15, rcx
0x18015c1c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18015c1cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18015c1d0  test    al, al
0x18015c1d2  jz      loc_18015C529
0x18015c1d8  mov     rcx, [r15]; hObject
0x18015c1db  test    rcx, rcx
0x18015c1de  jz      loc_18015C504
0x18015c1e4  test    r12, r12
0x18015c1e7  jnz     short loc_18015C211
0x18015c1e9  mov     rcx, [rsp+0B8h]; this
0x18015c1f1  mov     ebx, 80004003h
0x18015c1f6  mov     r9d, ebx; char *
0x18015c1f9  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c200  lea     edx, [r12+23h]; void *
0x18015c205  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015c20a  mov     eax, ebx
0x18015c20c  jmp     loc_18015C552
0x18015c211  test    rbx, rbx
0x18015c214  jnz     short loc_18015C23E
0x18015c216  mov     rcx, [rsp+0B8h]; this
0x18015c21e  mov     ebx, 80070057h
0x18015c223  mov     r9d, ebx; char *
0x18015c226  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c22d  mov     edx, 24h ; '$'; void *
0x18015c232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015c237  mov     eax, ebx
0x18015c239  jmp     loc_18015C552
0x18015c23e  mov     dword ptr [rsp+0B8h+pbOutput], 0
0x18015c246  mov     [rsp+0B8h+var_74], 0
0x18015c24e  mov     [rsp+0B8h+dwFlags], 0; dwFlags
0x18015c256  lea     rax, [rsp+0B8h+var_74]
0x18015c25b  mov     [rsp+0B8h+pcbResult], rax; int
0x18015c260  mov     r9d, 4; cbOutput
0x18015c266  lea     r8, [rsp+0B8h+pbOutput]; pbOutput
0x18015c26b  lea     rdx, aObjectlength; "ObjectLength"
0x18015c272  call    cs:__imp_BCryptGetProperty
0x18015c278  test    eax, eax
0x18015c27a  jns     short loc_18015C29D
0x18015c27c  mov     rcx, [rsp+0B8h]; this
0x18015c284  mov     r9d, eax; char *
0x18015c287  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c28e  mov     edx, 2Ah ; '*'; void *
0x18015c293  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18015c298  jmp     loc_18015C552
0x18015c29d  mov     edx, dword ptr [rsp+0B8h+pbOutput]
0x18015c2a1  lea     r8, [rsp+0B8h+var_78]
0x18015c2a6  lea     rcx, [rsp+0B8h+pbHashObject]
0x18015c2ab  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18015c2b0  nop
0x18015c2b1  mov     r8, [rsp+0B8h+pbHashObject]; pbHashObject
0x18015c2b6  test    r8, r8
0x18015c2b9  jnz     short loc_18015C2EE
0x18015c2bb  mov     rcx, [rsp+0B8h]; this
0x18015c2c3  mov     ebx, 8007000Eh
0x18015c2c8  mov     r9d, ebx; char *
0x18015c2cb  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c2d2  mov     edx, 2Eh ; '.'; void *
0x18015c2d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015c2dc  nop
0x18015c2dd  lea     rcx, [rsp+0B8h+pbHashObject]
0x18015c2e2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18015c2e7  mov     eax, ebx
0x18015c2e9  jmp     loc_18015C552
0x18015c2ee  mov     [rsp+0B8h+phHash], 0
0x18015c2f7  mov     [rsp+0B8h+var_88], 0; dwFlags
0x18015c2ff  mov     [rsp+0B8h+dwFlags], 0; cbSecret
0x18015c307  mov     [rsp+0B8h+pcbResult], 0; int
0x18015c310  mov     r9d, dword ptr [rsp+0B8h+pbOutput]; cbHashObject
0x18015c315  lea     rdx, [rsp+0B8h+phHash]; phHash
0x18015c31a  mov     rcx, [r15]; hAlgorithm
0x18015c31d  call    cs:__imp_BCryptCreateHash
0x18015c323  test    eax, eax
0x18015c325  jns     short loc_18015C361
0x18015c327  mov     rcx, [rsp+0B8h]; this
0x18015c32f  mov     r9d, eax; char *
0x18015c332  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c339  mov     edx, 38h ; '8'; void *
0x18015c33e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18015c343  mov     ebx, eax
0x18015c345  lea     rcx, [rsp+0B8h+phHash]
0x18015c34a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18015c34f  nop
0x18015c350  lea     rcx, [rsp+0B8h+pbHashObject]
0x18015c355  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18015c35a  mov     eax, ebx
0x18015c35c  jmp     loc_18015C552
0x18015c361  xor     esi, esi
0x18015c363  mov     eax, 0FFFFFFFFh
0x18015c368  test    rbx, rbx
0x18015c36b  jz      short loc_18015C3D3
0x18015c36d  cmp     rbx, rax
0x18015c370  mov     edi, ebx
0x18015c372  jb      short loc_18015C376
0x18015c374  mov     edi, eax
0x18015c376  lea     rdx, [r12+rsi]; pbInput
0x18015c37a  xor     r9d, r9d; dwFlags
0x18015c37d  mov     r8d, edi; cbInput
0x18015c380  mov     rcx, [rsp+0B8h+phHash]; hHash
0x18015c385  call    cs:__imp_BCryptHashData
0x18015c38b  test    eax, eax
0x18015c38d  jns     short loc_18015C3C9
0x18015c38f  mov     rcx, [rsp+0B8h]; this
0x18015c397  mov     r9d, eax; char *
0x18015c39a  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c3a1  mov     edx, 44h ; 'D'; void *
0x18015c3a6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18015c3ab  mov     ebx, eax
0x18015c3ad  lea     rcx, [rsp+0B8h+phHash]
0x18015c3b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18015c3b7  nop
0x18015c3b8  lea     rcx, [rsp+0B8h+pbHashObject]
0x18015c3bd  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18015c3c2  mov     eax, ebx
0x18015c3c4  jmp     loc_18015C552
0x18015c3c9  mov     eax, edi
0x18015c3cb  sub     rbx, rax
0x18015c3ce  add     rsi, rax
0x18015c3d1  jmp     short loc_18015C363
0x18015c3d3  mov     dword ptr [rsp+0B8h+var_64], 0
0x18015c3db  mov     [rsp+0B8h+dwFlags], 0; dwFlags
0x18015c3e3  lea     rax, [rsp+0B8h+var_74]
0x18015c3e8  mov     [rsp+0B8h+pcbResult], rax; int
0x18015c3ed  mov     r9d, 4; cbOutput
0x18015c3f3  lea     r8, [rsp+0B8h+var_64]; pbOutput
0x18015c3f8  lea     rdx, pszProperty; "HashDigestLength"
0x18015c3ff  mov     rcx, [r15]; hObject
0x18015c402  call    cs:__imp_BCryptGetProperty
0x18015c408  test    eax, eax
0x18015c40a  jns     short loc_18015C446
0x18015c40c  mov     rcx, [rsp+0B8h]; this
0x18015c414  mov     r9d, eax; char *
0x18015c417  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c41e  mov     edx, 52h ; 'R'; void *
0x18015c423  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18015c428  mov     ebx, eax
0x18015c42a  lea     rcx, [rsp+0B8h+phHash]
0x18015c42f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18015c434  nop
0x18015c435  lea     rcx, [rsp+0B8h+pbHashObject]
0x18015c43a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18015c43f  mov     eax, ebx
0x18015c441  jmp     loc_18015C552
0x18015c446  mov     edx, dword ptr [rsp+0B8h+var_64]
0x18015c44a  lea     r8, [rsp+0B8h+var_78]
0x18015c44f  mov     rcx, r14
0x18015c452  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18015c457  mov     rdx, [r14]; pbOutput
0x18015c45a  test    rdx, rdx
0x18015c45d  jnz     short loc_18015C49D
0x18015c45f  mov     rcx, [rsp+0B8h]; this
0x18015c467  mov     ebx, 8007000Eh
0x18015c46c  mov     r9d, ebx; char *
0x18015c46f  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c476  mov     edx, 55h ; 'U'; void *
0x18015c47b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015c480  nop
0x18015c481  lea     rcx, [rsp+0B8h+phHash]
0x18015c486  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18015c48b  nop
0x18015c48c  lea     rcx, [rsp+0B8h+pbHashObject]
0x18015c491  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18015c496  mov     eax, ebx
0x18015c498  jmp     loc_18015C552
0x18015c49d  xor     r9d, r9d; dwFlags
0x18015c4a0  mov     r8d, dword ptr [rsp+0B8h+var_64]; cbOutput
0x18015c4a5  mov     rcx, [rsp+0B8h+phHash]; hHash
0x18015c4aa  call    cs:__imp_BCryptFinishHash
0x18015c4b0  test    eax, eax
0x18015c4b2  jns     short loc_18015C4EB
0x18015c4b4  mov     rcx, [rsp+0B8h]; this
0x18015c4bc  mov     r9d, eax; char *
0x18015c4bf  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c4c6  mov     edx, 58h ; 'X'; void *
0x18015c4cb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18015c4d0  mov     ebx, eax
0x18015c4d2  lea     rcx, [rsp+0B8h+phHash]
0x18015c4d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18015c4dc  nop
0x18015c4dd  lea     rcx, [rsp+0B8h+pbHashObject]
0x18015c4e2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18015c4e7  mov     eax, ebx
0x18015c4e9  jmp     short loc_18015C552
0x18015c4eb  lea     rcx, [rsp+0B8h+phHash]
0x18015c4f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18015c4f5  nop
0x18015c4f6  lea     rcx, [rsp+0B8h+pbHashObject]
0x18015c4fb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18015c500  xor     eax, eax
0x18015c502  jmp     short loc_18015C552
0x18015c504  mov     rcx, [rsp+0B8h]; this
0x18015c50c  mov     ebx, 8000FFFFh
0x18015c511  mov     r9d, ebx; char *
0x18015c514  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c51b  mov     edx, 22h ; '"'; void *
0x18015c520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015c525  mov     eax, ebx
0x18015c527  jmp     short loc_18015C552
0x18015c529  mov     rcx, [rsp+0B8h]; this
0x18015c531  mov     ebx, 80004001h
0x18015c536  mov     r9d, ebx; char *
0x18015c539  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c540  mov     edx, 20h ; ' '; void *
0x18015c545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015c54a  mov     eax, ebx
0x18015c54c  jmp     short loc_18015C552
0x18015c54e  mov     eax, [rsp+0B8h+var_74]
0x18015c552  mov     rcx, [rsp+0B8h+var_48]
0x18015c557  xor     rcx, rsp; StackCookie
0x18015c55a  call    __security_check_cookie
0x18015c55f  add     rsp, 88h
0x18015c566  pop     r15
0x18015c568  pop     r14
0x18015c56a  pop     r12
0x18015c56c  pop     rdi
0x18015c56d  pop     rsi
0x18015c56e  pop     rbx
0x18015c56f  retn
```
