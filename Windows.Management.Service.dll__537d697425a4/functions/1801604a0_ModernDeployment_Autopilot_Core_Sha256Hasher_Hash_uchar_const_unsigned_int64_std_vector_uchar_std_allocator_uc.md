# ModernDeployment::Autopilot::Core::Sha256Hasher::Hash(uchar const *,unsigned __int64,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1801604a0`
- end: `0x180160897`
- name: `?Hash@Sha256Hasher@Core@Autopilot@ModernDeployment@@QEBAJPEBE_KAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1015`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180136b5c`
- `0x180161d64`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180080c10`
- `0x18008c30c`
- `0x1800a1600`
- `0x180135ea0`
- `0x1801365e8`
- `0x18016042c`
- `0x1801604a0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1801607ca`
- `bcrypt!BCryptFinishHash` at `0x1801607ca`
- `bcrypt!BCryptHashData` at `0x180160699`
- `bcrypt!BCryptHashData` at `0x180160699`
- `bcrypt!BCryptCreateHash` at `0x18016062b`
- `bcrypt!BCryptCreateHash` at `0x18016062b`
- `bcrypt!BCryptGetProperty` at `0x18016057a`
- `bcrypt!BCryptGetProperty` at `0x18016071c`
- `bcrypt!BCryptGetProperty` at `0x18016057a`
- `bcrypt!BCryptGetProperty` at `0x18016071c`

## string_xrefs

- `0x180160501`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18016052e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x180160595`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x1801605d9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x180160646`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x1801606b4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x180160737`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18016078f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x1801607e5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18016083a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`
- `0x18016085f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\sha256hasher.cpp`

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
0x1801604a0  push    rbx
0x1801604a2  push    rsi
0x1801604a3  push    rdi
0x1801604a4  push    r12
0x1801604a6  push    r14
0x1801604a8  push    r15
0x1801604aa  sub     rsp, 88h
0x1801604b1  mov     rax, cs:__security_cookie
0x1801604b8  xor     rax, rsp
0x1801604bb  mov     [rsp+0B8h+var_48], rax
0x1801604c0  mov     r14, r9
0x1801604c3  mov     rbx, r8
0x1801604c6  mov     r12, rdx
0x1801604c9  mov     r15, rcx
0x1801604cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801604d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801604d8  test    al, al
0x1801604da  jz      loc_18016084F
0x1801604e0  mov     rcx, [r15]; hObject
0x1801604e3  test    rcx, rcx
0x1801604e6  jz      loc_18016082A
0x1801604ec  test    r12, r12
0x1801604ef  jnz     short loc_180160519
0x1801604f1  mov     rcx, [rsp+0B8h]; this
0x1801604f9  mov     ebx, 80004003h
0x1801604fe  mov     r9d, ebx; char *
0x180160501  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160508  lea     edx, [r12+23h]; void *
0x18016050d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160512  mov     eax, ebx
0x180160514  jmp     loc_180160878
0x180160519  test    rbx, rbx
0x18016051c  jnz     short loc_180160546
0x18016051e  mov     rcx, [rsp+0B8h]; this
0x180160526  mov     ebx, 80070057h
0x18016052b  mov     r9d, ebx; char *
0x18016052e  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160535  mov     edx, 24h ; '$'; void *
0x18016053a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016053f  mov     eax, ebx
0x180160541  jmp     loc_180160878
0x180160546  mov     dword ptr [rsp+0B8h+pbOutput], 0
0x18016054e  mov     [rsp+0B8h+var_74], 0
0x180160556  mov     [rsp+0B8h+dwFlags], 0; dwFlags
0x18016055e  lea     rax, [rsp+0B8h+var_74]
0x180160563  mov     [rsp+0B8h+pcbResult], rax; int
0x180160568  mov     r9d, 4; cbOutput
0x18016056e  lea     r8, [rsp+0B8h+pbOutput]; pbOutput
0x180160573  lea     rdx, aObjectlength; "ObjectLength"
0x18016057a  call    cs:__imp_BCryptGetProperty
0x180160581  nop     dword ptr [rax+rax+00h]
0x180160586  test    eax, eax
0x180160588  jns     short loc_1801605AB
0x18016058a  mov     rcx, [rsp+0B8h]; this
0x180160592  mov     r9d, eax; char *
0x180160595  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016059c  mov     edx, 2Ah ; '*'; void *
0x1801605a1  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801605a6  jmp     loc_180160878
0x1801605ab  mov     edx, dword ptr [rsp+0B8h+pbOutput]
0x1801605af  lea     r8, [rsp+0B8h+var_78]
0x1801605b4  lea     rcx, [rsp+0B8h+pbHashObject]
0x1801605b9  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1801605be  nop
0x1801605bf  mov     r8, [rsp+0B8h+pbHashObject]; pbHashObject
0x1801605c4  test    r8, r8
0x1801605c7  jnz     short loc_1801605FC
0x1801605c9  mov     rcx, [rsp+0B8h]; this
0x1801605d1  mov     ebx, 8007000Eh
0x1801605d6  mov     r9d, ebx; char *
0x1801605d9  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801605e0  mov     edx, 2Eh ; '.'; void *
0x1801605e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801605ea  nop
0x1801605eb  lea     rcx, [rsp+0B8h+pbHashObject]
0x1801605f0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801605f5  mov     eax, ebx
0x1801605f7  jmp     loc_180160878
0x1801605fc  mov     [rsp+0B8h+phHash], 0
0x180160605  mov     [rsp+0B8h+var_88], 0; dwFlags
0x18016060d  mov     [rsp+0B8h+dwFlags], 0; cbSecret
0x180160615  mov     [rsp+0B8h+pcbResult], 0; int
0x18016061e  mov     r9d, dword ptr [rsp+0B8h+pbOutput]; cbHashObject
0x180160623  lea     rdx, [rsp+0B8h+phHash]; phHash
0x180160628  mov     rcx, [r15]; hAlgorithm
0x18016062b  call    cs:__imp_BCryptCreateHash
0x180160632  nop     dword ptr [rax+rax+00h]
0x180160637  test    eax, eax
0x180160639  jns     short loc_180160675
0x18016063b  mov     rcx, [rsp+0B8h]; this
0x180160643  mov     r9d, eax; char *
0x180160646  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016064d  mov     edx, 38h ; '8'; void *
0x180160652  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180160657  mov     ebx, eax
0x180160659  lea     rcx, [rsp+0B8h+phHash]
0x18016065e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180160663  nop
0x180160664  lea     rcx, [rsp+0B8h+pbHashObject]
0x180160669  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18016066e  mov     eax, ebx
0x180160670  jmp     loc_180160878
0x180160675  xor     esi, esi
0x180160677  mov     eax, 0FFFFFFFFh
0x18016067c  test    rbx, rbx
0x18016067f  jz      short loc_1801606ED
0x180160681  cmp     rbx, rax
0x180160684  mov     edi, ebx
0x180160686  jb      short loc_18016068A
0x180160688  mov     edi, eax
0x18016068a  lea     rdx, [r12+rsi]; pbInput
0x18016068e  xor     r9d, r9d; dwFlags
0x180160691  mov     r8d, edi; cbInput
0x180160694  mov     rcx, [rsp+0B8h+phHash]; hHash
0x180160699  call    cs:__imp_BCryptHashData
0x1801606a0  nop     dword ptr [rax+rax+00h]
0x1801606a5  test    eax, eax
0x1801606a7  jns     short loc_1801606E3
0x1801606a9  mov     rcx, [rsp+0B8h]; this
0x1801606b1  mov     r9d, eax; char *
0x1801606b4  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801606bb  mov     edx, 44h ; 'D'; void *
0x1801606c0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801606c5  mov     ebx, eax
0x1801606c7  lea     rcx, [rsp+0B8h+phHash]
0x1801606cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801606d1  nop
0x1801606d2  lea     rcx, [rsp+0B8h+pbHashObject]
0x1801606d7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801606dc  mov     eax, ebx
0x1801606de  jmp     loc_180160878
0x1801606e3  mov     eax, edi
0x1801606e5  sub     rbx, rax
0x1801606e8  add     rsi, rax
0x1801606eb  jmp     short loc_180160677
0x1801606ed  mov     dword ptr [rsp+0B8h+var_64], 0
0x1801606f5  mov     [rsp+0B8h+dwFlags], 0; dwFlags
0x1801606fd  lea     rax, [rsp+0B8h+var_74]
0x180160702  mov     [rsp+0B8h+pcbResult], rax; int
0x180160707  mov     r9d, 4; cbOutput
0x18016070d  lea     r8, [rsp+0B8h+var_64]; pbOutput
0x180160712  lea     rdx, pszProperty; "HashDigestLength"
0x180160719  mov     rcx, [r15]; hObject
0x18016071c  call    cs:__imp_BCryptGetProperty
0x180160723  nop     dword ptr [rax+rax+00h]
0x180160728  test    eax, eax
0x18016072a  jns     short loc_180160766
0x18016072c  mov     rcx, [rsp+0B8h]; this
0x180160734  mov     r9d, eax; char *
0x180160737  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016073e  mov     edx, 52h ; 'R'; void *
0x180160743  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180160748  mov     ebx, eax
0x18016074a  lea     rcx, [rsp+0B8h+phHash]
0x18016074f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180160754  nop
0x180160755  lea     rcx, [rsp+0B8h+pbHashObject]
0x18016075a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18016075f  mov     eax, ebx
0x180160761  jmp     loc_180160878
0x180160766  mov     edx, dword ptr [rsp+0B8h+var_64]
0x18016076a  lea     r8, [rsp+0B8h+var_78]
0x18016076f  mov     rcx, r14
0x180160772  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180160777  mov     rdx, [r14]; pbOutput
0x18016077a  test    rdx, rdx
0x18016077d  jnz     short loc_1801607BD
0x18016077f  mov     rcx, [rsp+0B8h]; this
0x180160787  mov     ebx, 8007000Eh
0x18016078c  mov     r9d, ebx; char *
0x18016078f  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160796  mov     edx, 55h ; 'U'; void *
0x18016079b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801607a0  nop
0x1801607a1  lea     rcx, [rsp+0B8h+phHash]
0x1801607a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801607ab  nop
0x1801607ac  lea     rcx, [rsp+0B8h+pbHashObject]
0x1801607b1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801607b6  mov     eax, ebx
0x1801607b8  jmp     loc_180160878
0x1801607bd  xor     r9d, r9d; dwFlags
0x1801607c0  mov     r8d, dword ptr [rsp+0B8h+var_64]; cbOutput
0x1801607c5  mov     rcx, [rsp+0B8h+phHash]; hHash
0x1801607ca  call    cs:__imp_BCryptFinishHash
0x1801607d1  nop     dword ptr [rax+rax+00h]
0x1801607d6  test    eax, eax
0x1801607d8  jns     short loc_180160811
0x1801607da  mov     rcx, [rsp+0B8h]; this
0x1801607e2  mov     r9d, eax; char *
0x1801607e5  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801607ec  mov     edx, 58h ; 'X'; void *
0x1801607f1  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801607f6  mov     ebx, eax
0x1801607f8  lea     rcx, [rsp+0B8h+phHash]
0x1801607fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180160802  nop
0x180160803  lea     rcx, [rsp+0B8h+pbHashObject]
0x180160808  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18016080d  mov     eax, ebx
0x18016080f  jmp     short loc_180160878
0x180160811  lea     rcx, [rsp+0B8h+phHash]
0x180160816  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18016081b  nop
0x18016081c  lea     rcx, [rsp+0B8h+pbHashObject]
0x180160821  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180160826  xor     eax, eax
0x180160828  jmp     short loc_180160878
0x18016082a  mov     rcx, [rsp+0B8h]; this
0x180160832  mov     ebx, 8000FFFFh
0x180160837  mov     r9d, ebx; char *
0x18016083a  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160841  mov     edx, 22h ; '"'; void *
0x180160846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016084b  mov     eax, ebx
0x18016084d  jmp     short loc_180160878
0x18016084f  mov     rcx, [rsp+0B8h]; this
0x180160857  mov     ebx, 80004001h
0x18016085c  mov     r9d, ebx; char *
0x18016085f  lea     r8, aOnecoreuapAdmi_117; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160866  mov     edx, 20h ; ' '; void *
0x18016086b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160870  mov     eax, ebx
0x180160872  jmp     short loc_180160878
0x180160874  mov     eax, [rsp+0B8h+var_74]
0x180160878  mov     rcx, [rsp+0B8h+var_48]
0x18016087d  xor     rcx, rsp; StackCookie
0x180160880  call    __security_check_cookie
0x180160885  add     rsp, 88h
0x18016088c  pop     r15
0x18016088e  pop     r14
0x180160890  pop     r12
0x180160892  pop     rdi
0x180160893  pop     rsi
0x180160894  pop     rbx
0x180160895  retn
```
