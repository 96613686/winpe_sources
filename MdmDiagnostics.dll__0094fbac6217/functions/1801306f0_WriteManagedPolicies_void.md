# WriteManagedPolicies(void)

- ea: `0x1801306f0`
- end: `0x180130eb4`
- name: `?WriteManagedPolicies@@YAJXZ`
- size: `1988`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e6664`
- `0x1800e691c`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800ee898`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x1800f89d8`
- `0x1800f9320`
- `0x1800f94a0`
- `0x1800f9a0c`
- `0x180104270`
- `0x180104c54`
- `0x180104c80`
- `0x18010589c`
- `0x1801058cc`
- `0x180105b28`
- `0x180105c40`
- `0x180120ce0`
- `0x180126a14`
- `0x180126a64`
- `0x180126b20`
- `0x1801279ac`
- `0x180127fa8`
- `0x1801283b0`
- `0x180128e28`
- `0x1801306f0`
- `0x1801312d0`
- `0x180135ef4`
- `0x18013b0f4`
- `0x18013b118`

## string_xrefs

- `0x18013082c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18013088d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801308f3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180130d37`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18013077e`: `Config Source`
- `0x1801307f2`: `Policies that are not set to the default value or have a configuration source applied`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 WriteManagedPolicies(void)
{
  int v0; // edi
  __int64 v1; // rbx
  __int64 v2; // rax
  int v3; // ebx
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v5; // rax
  int EnrollmentId; // eax
  unsigned int v7; // ebx
  int ManagedPolicies; // eax
  unsigned int v9; // ebx
  __int64 *v10; // rbx
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // r14
  _BYTE *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // esi
  __int64 **v23; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v26[4]; // [rsp+20h] [rbp-248h] BYREF
  __int64 v27; // [rsp+30h] [rbp-238h]
  int v28; // [rsp+38h] [rbp-230h]
  __int128 v29; // [rsp+40h] [rbp-228h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-218h] BYREF
  __int64 v31; // [rsp+60h] [rbp-208h] BYREF
  std::_Ref_count_base *v32; // [rsp+68h] [rbp-200h]
  _BYTE v33[16]; // [rsp+78h] [rbp-1F0h] BYREF
  __int64 v34; // [rsp+88h] [rbp-1E0h]
  __int128 v35; // [rsp+98h] [rbp-1D0h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-1C0h]
  __int64 v37; // [rsp+B0h] [rbp-1B8h]
  _BYTE v38[40]; // [rsp+B8h] [rbp-1B0h] BYREF
  _QWORD v39[10]; // [rsp+E0h] [rbp-188h] BYREF
  _BYTE v40[32]; // [rsp+130h] [rbp-138h] BYREF
  _BYTE v41[32]; // [rsp+150h] [rbp-118h] BYREF
  _BYTE v42[32]; // [rsp+170h] [rbp-F8h] BYREF
  _BYTE v43[32]; // [rsp+190h] [rbp-D8h] BYREF
  _BYTE v44[32]; // [rsp+1B0h] [rbp-B8h] BYREF
  _BYTE v45[32]; // [rsp+1D0h] [rbp-98h] BYREF
  __m128i si128; // [rsp+1F0h] [rbp-78h] BYREF
  int v47; // [rsp+200h] [rbp-68h]
  int v48; // [rsp+204h] [rbp-64h]
  _QWORD v49[6]; // [rsp+208h] [rbp-60h] BYREF
  _QWORD v50[6]; // [rsp+238h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v0 = 0;
  v28 = 0;
  Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders *)v39,
    L"Managed policies",
    L"ManagedPoliciesTable");
  v49[0] = L"Area";
  v49[1] = L"Policy";
  v49[2] = L"Default Value";
  v49[3] = L"Current Value";
  v49[4] = L"Target";
  v49[5] = L"Config Source";
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v47 = 8;
  v48 = 28;
  v1 = std::vector<int>::vector<int>(&v31, &si128, v49);
  v2 = std::vector<std::wstring>::vector<std::wstring>(v26, v49, v50);
  v3 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
         v39,
         L"Policies that are not set to the default value or have a configuration source applied",
         v2,
         v1);
  std::vector<std::wstring>::_Tidy(v26);
  std::vector<enum TpmCapabilityPT>::_Tidy(&v31);
  if ( v3 >= 0 )
  {
    v29 = 0;
    v5 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v5, &v29);
    v7 = EnrollmentId;
    if ( EnrollmentId >= 0 )
    {
      std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>(v30);
      ManagedPolicies = Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveManagedPolicies(v30);
      v9 = ManagedPolicies;
      if ( ManagedPolicies >= 0 )
      {
        v10 = *(__int64 **)v30[0];
        while ( 1 )
        {
          if ( *((_BYTE *)v10 + 25) )
          {
            std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>(v30);
            std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v29);
            v39[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
            Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v39);
            return 0;
          }
          std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
            &v31,
            v10 + 5);
          *(_OWORD *)v26 = 0;
          v27 = 0;
          v11 = v31;
          std::wstring::wstring(v33, v31);
          if ( *(_QWORD *)&v26[2] == v27 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v26, *(_QWORD *)&v26[2], v33);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v26, v33);
          std::wstring::_Tidy_deallocate(v33);
          std::wstring::wstring(v33, v11 + 32);
          if ( *(_QWORD *)&v26[2] == v27 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v26, *(_QWORD *)&v26[2], v33);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v26, v33);
          std::wstring::_Tidy_deallocate(v33);
          std::wstring::wstring(v33, v11 + 128);
          if ( *(_QWORD *)&v26[2] == v27 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v26, *(_QWORD *)&v26[2], v33);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v26, v33);
          std::wstring::_Tidy_deallocate(v33);
          std::wstring::wstring(v33, v11 + 96);
          if ( *(_QWORD *)&v26[2] == v27 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v26, *(_QWORD *)&v26[2], v33);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v26, v33);
          std::wstring::_Tidy_deallocate(v33);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetTargetIdForReport(v11 + 64, v33);
          if ( *(_QWORD *)&v26[2] == v27 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v26, *(_QWORD *)&v26[2], v33);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v26, v33);
          std::wstring::_Tidy_deallocate(v33);
          std::wstring::wstring(v38, v11 + 32);
          std::wstring::wstring(v33, v11);
          v12 = std::operator+<unsigned short>(v41, L"/", v33);
          v13 = std::operator+<unsigned short>(v40, v12, L"/");
          v14 = std::operator+<unsigned short>(v45, v13, v38);
          std::operator+<unsigned short>(v44, v14, L"/");
          std::wstring::_Tidy_deallocate(v45);
          std::wstring::_Tidy_deallocate(v40);
          std::wstring::_Tidy_deallocate(v41);
          std::wstring::_Tidy_deallocate(v33);
          std::wstring::_Tidy_deallocate(v38);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetRawTargetId(v11 + 64, v43);
          v0 |= 0xFFu;
          v35 = 0;
          v15 = 0;
          v36 = 0;
          v37 = 7;
          LOWORD(v35) = 0;
          v16 = *(_QWORD *)(v11 + 168);
          v17 = *(_QWORD *)(v11 + 176);
          while ( v16 != v17 )
          {
            if ( v15 )
              std::wstring::append(&v35, L",<br/>");
            std::wstring::wstring(v33, v16 + 32);
            if ( v34 )
            {
              std::wstring::wstring(v38, v16);
              v0 |= 0x500u;
              v19 = std::operator+<unsigned short>(v40, v38, L"=");
              v20 = std::operator+<unsigned short>(v41, v19, v33);
              std::wstring::append(&v35, v20);
              std::wstring::_Tidy_deallocate(v41);
              std::wstring::_Tidy_deallocate(v40);
              v18 = v38;
            }
            else
            {
              std::wstring::wstring(v42, v16);
              v0 |= 0x300u;
              std::wstring::append(&v35, v42);
              v18 = v42;
            }
            std::wstring::_Tidy_deallocate(v18);
            std::wstring::_Tidy_deallocate(v33);
            v16 += 64;
            v15 = v36;
          }
          if ( *(_QWORD *)&v26[2] == v27 )
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v26, *(_QWORD *)&v26[2], &v35);
          else
            std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v26, &v35);
          v21 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v39, v26);
          v22 = v21;
          if ( v21 < 0 )
            break;
          std::wstring::_Tidy_deallocate(&v35);
          std::wstring::_Tidy_deallocate(v43);
          std::wstring::_Tidy_deallocate(v44);
          std::vector<std::wstring>::_Tidy(v26);
          if ( v32 )
            std::_Ref_count_base::_Decref(v32);
          v23 = (__int64 **)v10[2];
          if ( *((_BYTE *)v23 + 25) )
          {
            for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25) && v10 == (__int64 *)i[2]; i = (__int64 *)i[1] )
              v10 = i;
            v10 = i;
          }
          else
          {
            v10 = (__int64 *)v10[2];
            for ( j = *v23; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v10 = j;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v21,
          v26[0]);
        std::wstring::_Tidy_deallocate(&v35);
        std::wstring::_Tidy_deallocate(v43);
        std::wstring::_Tidy_deallocate(v44);
        std::vector<std::wstring>::_Tidy(v26);
        if ( v32 )
          std::_Ref_count_base::_Decref(v32);
        std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>(v30);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v29);
        v39[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v39);
        return v22;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x875,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)ManagedPolicies,
          v26[0]);
        std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>(v30);
        std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v29);
        v39[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v39);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x872,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)EnrollmentId,
        v26[0]);
      std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v29);
      v39[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
      Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v39);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v3,
      v26[0]);
    v39[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
    Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v39);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x1801306f0  push    rbx
0x1801306f2  push    rsi
0x1801306f3  push    rdi
0x1801306f4  push    r14
0x1801306f6  push    r15
0x1801306f8  sub     rsp, 240h
0x1801306ff  mov     rax, cs:__security_cookie
0x180130706  xor     rax, rsp
0x180130709  mov     [rsp+268h+var_30], rax
0x180130711  xor     edi, edi
0x180130713  mov     [rsp+268h+var_230], edi
0x180130717  lea     r8, aManagedpolicie; "ManagedPoliciesTable"
0x18013071e  lea     rdx, aManagedPolicie; "Managed policies"
0x180130725  lea     rcx, [rsp+268h+var_188]; this
0x18013072d  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x180130732  nop
0x180130733  lea     rax, aArea; "Area"
0x18013073a  mov     [rsp+268h+var_60], rax
0x180130742  lea     rax, aPolicy_0; "Policy"
0x180130749  mov     [rsp+268h+var_58], rax
0x180130751  lea     rax, aDefaultValue; "Default Value"
0x180130758  mov     [rsp+268h+var_50], rax
0x180130760  lea     rax, aCurrentValue; "Current Value"
0x180130767  mov     [rsp+268h+var_48], rax
0x18013076f  lea     rax, aTarget; "Target"
0x180130776  mov     [rsp+268h+var_40], rax
0x18013077e  lea     rax, aConfigSource; "Config Source"
0x180130785  mov     [rsp+268h+var_38], rax
0x18013078d  movdqa  xmm0, cs:__xmm@0000000c0000000b0000001200000012
0x180130795  movdqu  [rsp+268h+var_78], xmm0
0x18013079e  mov     [rsp+268h+var_68], 8
0x1801307a9  mov     [rsp+268h+var_64], 1Ch
0x1801307b4  lea     r8, [rsp+268h+var_60]
0x1801307bc  lea     rdx, [rsp+268h+var_78]
0x1801307c4  lea     rcx, [rsp+268h+var_208]
0x1801307c9  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x1801307ce  mov     rbx, rax
0x1801307d1  lea     r8, [rsp+268h+var_30]
0x1801307d9  lea     rdx, [rsp+268h+var_60]
0x1801307e1  lea     rcx, [rsp+268h+var_248]
0x1801307e6  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x1801307eb  nop
0x1801307ec  mov     r9, rbx
0x1801307ef  mov     r8, rax
0x1801307f2  lea     rdx, aPoliciesThatAr; "Policies that are not set to the defaul"...
0x1801307f9  lea     rcx, [rsp+268h+var_188]
0x180130801  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x180130806  mov     ebx, eax
0x180130808  lea     rcx, [rsp+268h+var_248]
0x18013080d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180130812  nop
0x180130813  lea     rcx, [rsp+268h+var_208]
0x180130818  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x18013081d  test    ebx, ebx
0x18013081f  jns     short loc_180130861
0x180130821  mov     rcx, [rsp+268h]; this
0x180130829  mov     r9d, ebx; char *
0x18013082c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180130833  mov     edx, 86Fh; void *
0x180130838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013083d  nop
0x18013083e  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180130845  mov     [rsp+268h+var_188], rax
0x18013084d  lea     rcx, [rsp+268h+var_188]; this
0x180130855  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x18013085a  mov     eax, ebx
0x18013085c  jmp     loc_180130E94
0x180130861  xorps   xmm1, xmm1
0x180130864  movdqu  [rsp+268h+var_228], xmm1
0x18013086a  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013086f  lea     rdx, [rsp+268h+var_228]
0x180130874  mov     rcx, rax
0x180130877  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x18013087c  mov     ebx, eax
0x18013087e  test    eax, eax
0x180130880  jns     short loc_1801308CD
0x180130882  mov     rcx, [rsp+268h]; this
0x18013088a  mov     r9d, eax; char *
0x18013088d  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180130894  mov     edx, 872h; void *
0x180130899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013089e  nop
0x18013089f  lea     rcx, [rsp+268h+var_228]
0x1801308a4  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1801308a9  nop
0x1801308aa  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x1801308b1  mov     [rsp+268h+var_188], rax
0x1801308b9  lea     rcx, [rsp+268h+var_188]; this
0x1801308c1  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x1801308c6  mov     eax, ebx
0x1801308c8  jmp     loc_180130E94
0x1801308cd  lea     rcx, [rsp+268h+var_218]
0x1801308d2  call    ??0?$map@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@@std@@QEAA@XZ; std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>(void)
0x1801308d7  nop
0x1801308d8  lea     rcx, [rsp+268h+var_218]
0x1801308dd  call    ?RetrieveManagedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$map@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveManagedPolicies(std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x1801308e2  mov     ebx, eax
0x1801308e4  test    eax, eax
0x1801308e6  jns     short loc_18013093E
0x1801308e8  mov     rcx, [rsp+268h]; this
0x1801308f0  mov     r9d, eax; char *
0x1801308f3  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801308fa  mov     edx, 875h; void *
0x1801308ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130904  nop
0x180130905  lea     rcx, [rsp+268h+var_218]
0x18013090a  call    ??1?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>(void)
0x18013090f  nop
0x180130910  lea     rcx, [rsp+268h+var_228]
0x180130915  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18013091a  nop
0x18013091b  lea     rax, ??_7TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@6B@; const Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable'
0x180130922  mov     [rsp+268h+var_188], rax
0x18013092a  lea     rcx, [rsp+268h+var_188]; this
0x180130932  call    ??1SimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable(void)
0x180130937  mov     eax, ebx
0x180130939  jmp     loc_180130E94
0x18013093e  mov     rbx, [rsp+268h+var_218]
0x180130943  mov     rbx, [rbx]
0x180130946  cmp     byte ptr [rbx+19h], 0
0x18013094a  jnz     loc_180130E5A
0x180130950  lea     rdx, [rbx+28h]
0x180130954  lea     rcx, [rsp+268h+var_208]
0x180130959  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18013095e  nop
0x18013095f  xorps   xmm0, xmm0
0x180130962  movdqu  xmmword ptr [rsp+268h+var_248], xmm0; int
0x180130968  mov     [rsp+268h+var_238], 0
0x180130971  mov     r14, [rsp+268h+var_208]
0x180130976  mov     rdx, r14
0x180130979  lea     rcx, [rsp+268h+var_1F0]
0x18013097e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130983  nop
0x180130984  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x180130989  lea     rcx, [rsp+268h+var_248]
0x18013098e  cmp     rdx, [rsp+268h+var_238]
0x180130993  jz      short loc_1801309A1
0x180130995  lea     rdx, [rsp+268h+var_1F0]
0x18013099a  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18013099f  jmp     short loc_1801309AC
0x1801309a1  lea     r8, [rsp+268h+var_1F0]
0x1801309a6  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801309ab  nop
0x1801309ac  lea     rcx, [rsp+268h+var_1F0]
0x1801309b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801309b6  lea     rdx, [r14+20h]
0x1801309ba  lea     rcx, [rsp+268h+var_1F0]
0x1801309bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801309c4  nop
0x1801309c5  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x1801309ca  lea     rcx, [rsp+268h+var_248]
0x1801309cf  cmp     rdx, [rsp+268h+var_238]
0x1801309d4  jz      short loc_1801309E2
0x1801309d6  lea     rdx, [rsp+268h+var_1F0]
0x1801309db  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x1801309e0  jmp     short loc_1801309ED
0x1801309e2  lea     r8, [rsp+268h+var_1F0]
0x1801309e7  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801309ec  nop
0x1801309ed  lea     rcx, [rsp+268h+var_1F0]
0x1801309f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801309f7  lea     rdx, [r14+80h]
0x1801309fe  lea     rcx, [rsp+268h+var_1F0]
0x180130a03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130a08  nop
0x180130a09  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x180130a0e  lea     rcx, [rsp+268h+var_248]
0x180130a13  cmp     rdx, [rsp+268h+var_238]
0x180130a18  jz      short loc_180130A26
0x180130a1a  lea     rdx, [rsp+268h+var_1F0]
0x180130a1f  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180130a24  jmp     short loc_180130A31
0x180130a26  lea     r8, [rsp+268h+var_1F0]
0x180130a2b  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130a30  nop
0x180130a31  lea     rcx, [rsp+268h+var_1F0]
0x180130a36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130a3b  lea     rdx, [r14+60h]
0x180130a3f  lea     rcx, [rsp+268h+var_1F0]
0x180130a44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130a49  nop
0x180130a4a  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x180130a4f  lea     rcx, [rsp+268h+var_248]
0x180130a54  cmp     rdx, [rsp+268h+var_238]
0x180130a59  jz      short loc_180130A67
0x180130a5b  lea     rdx, [rsp+268h+var_1F0]
0x180130a60  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180130a65  jmp     short loc_180130A72
0x180130a67  lea     r8, [rsp+268h+var_1F0]
0x180130a6c  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130a71  nop
0x180130a72  lea     rcx, [rsp+268h+var_1F0]
0x180130a77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130a7c  lea     rdx, [rsp+268h+var_1F0]
0x180130a81  lea     rcx, [r14+40h]
0x180130a85  call    ?GetTargetIdForReport@DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetTargetIdForReport(void)
0x180130a8a  nop
0x180130a8b  mov     rdx, qword ptr [rsp+268h+var_248+8]
0x180130a90  lea     rcx, [rsp+268h+var_248]
0x180130a95  cmp     rdx, [rsp+268h+var_238]
0x180130a9a  jz      short loc_180130AA8
0x180130a9c  lea     rdx, [rsp+268h+var_1F0]
0x180130aa1  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180130aa6  jmp     short loc_180130AB3
0x180130aa8  lea     r8, [rsp+268h+var_1F0]
0x180130aad  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130ab2  nop
0x180130ab3  or      edi, 1
0x180130ab6  lea     rcx, [rsp+268h+var_1F0]
0x180130abb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130ac0  lea     rdx, [r14+20h]
0x180130ac4  lea     rcx, [rsp+268h+var_1B0]
0x180130acc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130ad1  nop
0x180130ad2  mov     rdx, r14
0x180130ad5  lea     rcx, [rsp+268h+var_1F0]
0x180130ada  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130adf  nop
0x180130ae0  lea     r8, [rsp+268h+var_1F0]
0x180130ae5  lea     rdx, asc_1801D0CA8; "/"
0x180130aec  lea     rcx, [rsp+268h+var_118]
0x180130af4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180130af9  nop
0x180130afa  lea     r8, asc_1801D0CA8; "/"
0x180130b01  mov     rdx, rax
0x180130b04  lea     rcx, [rsp+268h+var_138]
0x180130b0c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180130b11  nop
0x180130b12  lea     r8, [rsp+268h+var_1B0]
0x180130b1a  mov     rdx, rax
0x180130b1d  lea     rcx, [rsp+268h+var_98]
0x180130b25  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180130b2a  nop
0x180130b2b  lea     r8, asc_1801D0CA8; "/"
0x180130b32  mov     rdx, rax
0x180130b35  lea     rcx, [rsp+268h+var_B8]
0x180130b3d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180130b42  nop
0x180130b43  lea     rcx, [rsp+268h+var_98]
0x180130b4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130b50  nop
0x180130b51  lea     rcx, [rsp+268h+var_138]
0x180130b59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130b5e  nop
0x180130b5f  lea     rcx, [rsp+268h+var_118]
0x180130b67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130b6c  nop
0x180130b6d  lea     rcx, [rsp+268h+var_1F0]
0x180130b72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130b77  nop
0x180130b78  lea     rcx, [rsp+268h+var_1B0]
0x180130b80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130b85  lea     rdx, [rsp+268h+var_D8]
0x180130b8d  lea     rcx, [r14+40h]
0x180130b91  call    ?GetRawTargetId@DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::GetRawTargetId(void)
0x180130b96  or      edi, 0FEh
0x180130b9c  xorps   xmm0, xmm0
0x180130b9f  movups  [rsp+268h+var_1D0], xmm0
0x180130ba7  xor     ecx, ecx
0x180130ba9  mov     [rsp+268h+var_1C0], rcx
0x180130bb1  mov     [rsp+268h+var_1B8], 7
0x180130bbd  xor     eax, eax
0x180130bbf  mov     word ptr [rsp+268h+var_1D0], ax
0x180130bc7  mov     rsi, [r14+0A8h]
0x180130bce  mov     r14, [r14+0B0h]
0x180130bd5  cmp     rsi, r14
0x180130bd8  jz      loc_180130CE3
0x180130bde  test    rcx, rcx
0x180130be1  jz      short loc_180130BF7
0x180130be3  lea     rdx, aBr; ",<br/>"
0x180130bea  lea     rcx, [rsp+268h+var_1D0]
0x180130bf2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180130bf7  lea     rdx, [rsi+20h]
0x180130bfb  lea     rcx, [rsp+268h+var_1F0]
0x180130c00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130c05  nop
0x180130c06  mov     rdx, rsi
0x180130c09  cmp     [rsp+268h+var_1E0], 0
0x180130c12  jnz     short loc_180130C47
0x180130c14  lea     rcx, [rsp+268h+var_F8]
0x180130c1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130c21  or      edi, 300h
0x180130c27  lea     rdx, [rsp+268h+var_F8]
0x180130c2f  lea     rcx, [rsp+268h+var_1D0]
0x180130c37  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180130c3c  nop
0x180130c3d  lea     rcx, [rsp+268h+var_F8]
0x180130c45  jmp     short loc_180130CC2
0x180130c47  lea     rcx, [rsp+268h+var_1B0]
0x180130c4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180130c54  or      edi, 500h
0x180130c5a  lea     r8, asc_1801EDBE8; "="
0x180130c61  lea     rdx, [rsp+268h+var_1B0]
0x180130c69  lea     rcx, [rsp+268h+var_138]
0x180130c71  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180130c76  nop
0x180130c77  lea     r8, [rsp+268h+var_1F0]
0x180130c7c  mov     rdx, rax
0x180130c7f  lea     rcx, [rsp+268h+var_118]
0x180130c87  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
  ... truncated ...
```
