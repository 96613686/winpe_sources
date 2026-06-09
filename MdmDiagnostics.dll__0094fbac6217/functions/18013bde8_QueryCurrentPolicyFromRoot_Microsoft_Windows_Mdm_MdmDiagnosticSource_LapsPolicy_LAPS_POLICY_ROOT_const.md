# QueryCurrentPolicyFromRoot(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy &,LAPS_POLICY_ROOT const *)

- ea: `0x18013bde8`
- end: `0x18013c292`
- name: `?QueryCurrentPolicyFromRoot@@YAJAEAVLapsPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEBULAPS_POLICY_ROOT@@@Z`
- size: `1194`
- prototype: `int(struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy *, const struct LAPS_POLICY_ROOT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18013bd58`

## callees

- `0x1800e4348`
- `0x1800e5594`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x18011129c`
- `0x18013b2d4`
- `0x18013b410`
- `0x18013b6dc`
- `0x18013bde8`
- `0x18013c298`
- `0x18013c438`
- `0x18013c62c`
- `0x18013c828`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013be72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013be72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013be42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013be42`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall QueryCurrentPolicyFromRoot(
        struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy *a1,
        LPCWSTR *a2)
{
  Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy *v3; // rdx
  HKEY v4; // rbx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  void *v9; // rcx
  BOOL v10; // r15d
  unsigned int v11; // edi
  _DWORD *v12; // r12
  __int64 v13; // rcx
  bool v14; // zf
  int v15; // eax
  unsigned int i; // edi
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  unsigned int j; // edi
  __int64 v21; // rcx
  bool v22; // zf
  int v23; // eax
  unsigned int v24; // edi
  unsigned int k; // esi
  _QWORD *v26; // r8
  unsigned int m; // esi
  _QWORD *v28; // r8
  int phkResult; // [rsp+20h] [rbp-48h]
  __int128 v31; // [rsp+30h] [rbp-38h] BYREF
  __int64 v32; // [rsp+40h] [rbp-28h]
  void *v33; // [rsp+48h] [rbp-20h] BYREF
  __int128 v34; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *v37; // [rsp+B8h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp+58h] BYREF
  char v39; // [rsp+C8h] [rbp+60h] BYREF

  hKey = 0;
  v37 = 0;
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v31);
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v33);
  Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy::Clear(v3);
  v4 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v39);
    RegCloseKey(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v39);
  }
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *a2, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
    v10 = 0;
    v11 = 0;
    v12 = a2 + 2;
    while ( v11 < 7 )
    {
      v12 = a2 + 2;
      v13 = 3LL * v11;
      if ( *((_DWORD *)a2 + 4) )
        v14 = (qword_18019AF68[v13] & 0x100000000LL) == 0;
      else
        v14 = (qword_18019AF68[v13] & 0x200000000LL) == 0;
      if ( v14 )
      {
        v15 = QueryPolicyDwordValue(
                hKey,
                (const struct LAPS_POLICY_ROOT *)a2,
                (const struct LAPS_DWORD_SETTING *)&(&off_18019AF60)[v13],
                &v37);
        v6 = v15;
        if ( v15 < 0 )
        {
          v7 = (unsigned int)v15;
          v8 = 797;
          goto LABEL_7;
        }
        if ( !v10 )
          v10 = *((_DWORD *)v37 + 32) == 0;
        if ( *((_QWORD *)&v31 + 1) == v32 )
        {
          std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
            &v31,
            *((_QWORD *)&v31 + 1),
            &v37);
        }
        else
        {
          **((_QWORD **)&v31 + 1) = v37;
          *((_QWORD *)&v31 + 1) += 8LL;
        }
      }
      ++v11;
    }
    for ( i = 0; i < 3; ++i )
    {
      v17 = 4LL * i;
      if ( *v12 )
        v18 = (qword_18019AF10[v17] & 1) == 0;
      else
        v18 = (qword_18019AF10[v17] & 2) == 0;
      if ( v18 )
      {
        v19 = QueryPolicySzValue(
                hKey,
                (const struct LAPS_POLICY_ROOT *)a2,
                (const struct LAPS_SZ_SETTING *)&(&off_18019AF00)[v17],
                &v37);
        v6 = v19;
        if ( v19 < 0 )
        {
          v7 = (unsigned int)v19;
          v8 = 817;
          goto LABEL_7;
        }
        if ( !v10 )
          v10 = *((_DWORD *)v37 + 32) == 0;
        if ( *((_QWORD *)&v31 + 1) == v32 )
        {
          std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
            &v31,
            *((_QWORD *)&v31 + 1),
            &v37);
        }
        else
        {
          **((_QWORD **)&v31 + 1) = v37;
          *((_QWORD *)&v31 + 1) += 8LL;
        }
      }
      v12 = a2 + 2;
    }
    for ( j = 0; j < 5; ++j )
    {
      v21 = 3LL * j;
      if ( *v12 )
        v22 = (qword_18019AE88[v21] & 0x100000000LL) == 0;
      else
        v22 = (qword_18019AE88[v21] & 0x200000000LL) == 0;
      if ( v22 )
      {
        v23 = QueryPolicyBoolValue(
                hKey,
                (const struct LAPS_POLICY_ROOT *)a2,
                (const struct LAPS_BOOL_SETTING *)&(&off_18019AE80)[v21],
                &v37);
        v6 = v23;
        if ( v23 < 0 )
        {
          v7 = (unsigned int)v23;
          v8 = 837;
          goto LABEL_7;
        }
        if ( !v10 )
          v10 = *((_DWORD *)v37 + 32) == 0;
        if ( *((_QWORD *)&v31 + 1) == v32 )
        {
          std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
            &v31,
            *((_QWORD *)&v31 + 1),
            &v37);
        }
        else
        {
          **((_QWORD **)&v31 + 1) = v37;
          *((_QWORD *)&v31 + 1) += 8LL;
        }
      }
    }
    v24 = 0;
    if ( *v12 )
    {
      do
      {
        for ( k = 0; k < (unsigned __int64)((__int64)(*((_QWORD *)&v31 + 1) - v31) >> 3); ++k )
        {
          if ( (unsigned __int8)std::wstring::_Equal(*(_QWORD *)(v31 + 8LL * k), off_18019BC10[v24]) )
          {
            v26 = (_QWORD *)(v31 + 8LL * k);
            if ( (_QWORD)v34 == *((_QWORD *)&v34 + 1) )
            {
              std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
                &v33,
                v34,
                v26);
            }
            else
            {
              *(_QWORD *)v34 = *v26;
              *(_QWORD *)&v34 = v34 + 8;
            }
            break;
          }
        }
        ++v24;
      }
      while ( v24 < 0xC );
    }
    else
    {
      do
      {
        for ( m = 0; m < (unsigned __int64)((__int64)(*((_QWORD *)&v31 + 1) - v31) >> 3); ++m )
        {
          if ( (unsigned __int8)std::wstring::_Equal(*(_QWORD *)(v31 + 8LL * m), off_18019BC10[v24]) )
          {
            v28 = (_QWORD *)(v31 + 8LL * m);
            if ( (_QWORD)v34 == *((_QWORD *)&v34 + 1) )
            {
              std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
                &v33,
                v34,
                v28);
            }
            else
            {
              *(_QWORD *)v34 = *v28;
              *(_QWORD *)&v34 = v34 + 8;
            }
            break;
          }
        }
        ++v24;
      }
      while ( v24 < 6 );
    }
    std::wstring::assign(a1, a2[1]);
    *((_DWORD *)a1 + 8) = *v12;
    *((_DWORD *)a1 + 9) = v10;
    if ( (void **)((char *)a1 + 40) != &v33 )
      std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Assign_counted_range<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *>(
        (char *)a1 + 40,
        v33,
        (__int64)(v34 - (_QWORD)v33) >> 3);
    if ( v33 )
    {
      std::_Deallocate<16>(v33, (*((_QWORD *)&v34 + 1) - (_QWORD)v33) & 0xFFFFFFFFFFFFFFF8uLL);
      v33 = 0;
      v34 = 0;
    }
    v9 = (void *)v31;
    if ( (_QWORD)v31 )
      goto LABEL_76;
  }
  else
  {
    v7 = v6;
    v8 = 780;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\laps.cpp",
      (const char *)v7,
      phkResult);
    if ( v33 )
    {
      std::_Deallocate<16>(v33, (*((_QWORD *)&v34 + 1) - (_QWORD)v33) & 0xFFFFFFFFFFFFFFF8uLL);
      v33 = 0;
      v34 = 0;
    }
    v9 = (void *)v31;
    if ( (_QWORD)v31 )
    {
LABEL_76:
      std::_Deallocate<16>(v9, (v32 - v31) & 0xFFFFFFFFFFFFFFF8uLL);
      v32 = 0;
      v31 = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x18013bde8  mov     [rsp-40h+arg_0], rcx
0x18013bded  push    rbp
0x18013bdee  push    rbx
0x18013bdef  push    rsi
0x18013bdf0  push    rdi
0x18013bdf1  push    r12
0x18013bdf3  push    r13
0x18013bdf5  push    r14
0x18013bdf7  push    r15
0x18013bdf9  mov     rbp, rsp
0x18013bdfc  sub     rsp, 68h
0x18013be00  mov     r13, rdx
0x18013be03  mov     rdx, rcx
0x18013be06  xor     r14d, r14d
0x18013be09  mov     [rbp+hKey], r14
0x18013be0d  mov     [rbp+arg_8], r14
0x18013be11  lea     rcx, [rbp+var_38]
0x18013be15  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18013be1a  nop
0x18013be1b  lea     rcx, [rbp+var_20]
0x18013be1f  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18013be24  nop
0x18013be25  mov     rcx, rdx; this
0x18013be28  call    ?Clear@LapsPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy::Clear(void)
0x18013be2d  mov     rbx, [rbp+hKey]
0x18013be31  test    rbx, rbx
0x18013be34  jz      short loc_18013BE51
0x18013be36  lea     rcx, [rbp+arg_18]; this
0x18013be3a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18013be3f  mov     rcx, rbx; hKey
0x18013be42  call    cs:__imp_RegCloseKey
0x18013be48  lea     rcx, [rbp+arg_18]; this
0x18013be4c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18013be51  mov     [rbp+hKey], r14
0x18013be55  lea     rax, [rbp+hKey]
0x18013be59  mov     qword ptr [rsp+68h+phkResult], rax; int
0x18013be5e  mov     r9d, 20019h; samDesired
0x18013be64  xor     r8d, r8d; ulOptions
0x18013be67  mov     rdx, [r13+0]; lpSubKey
0x18013be6b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013be72  call    cs:__imp_RegOpenKeyExW
0x18013be78  mov     ebx, eax
0x18013be7a  test    eax, eax
0x18013be7c  jle     short loc_18013BE87
0x18013be7e  movzx   ebx, ax
0x18013be81  or      ebx, 80070000h
0x18013be87  test    ebx, ebx
0x18013be89  jns     short loc_18013BEEF
0x18013be8b  mov     r9d, ebx; char *
0x18013be8e  mov     edx, 30Ch; void *
0x18013be93  mov     rcx, [rbp+40h]; this
0x18013be97  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013be9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013bea3  nop
0x18013bea4  mov     rcx, [rbp+var_20]
0x18013bea8  test    rcx, rcx
0x18013beab  jz      short loc_18013BEC9
0x18013bead  mov     rdx, qword ptr [rbp+var_18+8]
0x18013beb1  sub     rdx, rcx
0x18013beb4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18013beb8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013bebd  mov     [rbp+var_20], r14
0x18013bec1  xorps   xmm0, xmm0
0x18013bec4  movdqu  xmmword ptr [rbp-18h], xmm0
0x18013bec9  mov     rcx, qword ptr [rbp+var_38]
0x18013becd  test    rcx, rcx
0x18013bed0  jz      loc_18013C276
0x18013bed6  mov     rdx, [rbp+var_28]
0x18013beda  sub     rdx, rcx
0x18013bedd  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18013bee1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013bee6  mov     [rbp+var_28], r14
0x18013beea  jmp     loc_18013C26E
0x18013beef  mov     r15d, r14d
0x18013bef2  mov     edi, r14d
0x18013bef5  lea     r12, [r13+10h]
0x18013bef9  lea     r8, __ImageBase
0x18013bf00  cmp     edi, 7
0x18013bf03  jnb     loc_18013BFA6
0x18013bf09  lea     r12, [r13+10h]
0x18013bf0d  mov     eax, edi
0x18013bf0f  lea     rcx, [rax+rax*2]
0x18013bf13  shl     rcx, 3
0x18013bf17  cmp     [r12], r14d
0x18013bf1b  jz      short loc_18013BF28
0x18013bf1d  test    byte ptr [rcx+r8+19AF6Ch], 1
0x18013bf26  jmp     short loc_18013BF31
0x18013bf28  test    byte ptr [rcx+r8+19AF6Ch], 2
0x18013bf31  jnz     short loc_18013BF92
0x18013bf33  lea     r8, rva off_18019AF60[r8]; "BackupDirectory" ...
0x18013bf3a  add     r8, rcx; struct LAPS_DWORD_SETTING *
0x18013bf3d  lea     r9, [rbp+arg_8]; struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting **
0x18013bf41  mov     rdx, r13; struct LAPS_POLICY_ROOT *
0x18013bf44  mov     rcx, [rbp+hKey]; HKEY
0x18013bf48  call    ?QueryPolicyDwordValue@@YAJPEAUHKEY__@@PEBULAPS_POLICY_ROOT@@PEBULAPS_DWORD_SETTING@@PEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@Z; QueryPolicyDwordValue(HKEY__ *,LAPS_POLICY_ROOT const *,LAPS_DWORD_SETTING const *,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *)
0x18013bf4d  mov     ebx, eax
0x18013bf4f  test    eax, eax
0x18013bf51  js      short loc_18013BF99
0x18013bf53  mov     rax, [rbp+arg_8]
0x18013bf57  test    r15d, r15d
0x18013bf5a  jnz     short loc_18013BF6A
0x18013bf5c  mov     r15d, r14d
0x18013bf5f  cmp     [rax+80h], r14d
0x18013bf66  setz    r15b
0x18013bf6a  mov     rdx, qword ptr [rbp+var_38+8]
0x18013bf6e  cmp     rdx, [rbp+var_28]
0x18013bf72  jz      short loc_18013BF7E
0x18013bf74  mov     [rdx], rax
0x18013bf77  add     qword ptr [rbp+var_38+8], 8
0x18013bf7c  jmp     short loc_18013BF8B
0x18013bf7e  lea     r8, [rbp+arg_8]
0x18013bf82  lea     rcx, [rbp+var_38]
0x18013bf86  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013bf8b  lea     r8, __ImageBase
0x18013bf92  inc     edi
0x18013bf94  jmp     loc_18013BF00
0x18013bf99  mov     r9d, eax
0x18013bf9c  mov     edx, 31Dh
0x18013bfa1  jmp     loc_18013BE93
0x18013bfa6  mov     edi, r14d
0x18013bfa9  cmp     edi, 3
0x18013bfac  jnb     loc_18013C04B
0x18013bfb2  mov     eax, edi
0x18013bfb4  shl     rax, 5
0x18013bfb8  cmp     [r12], r14d
0x18013bfbc  jz      short loc_18013BFC9
0x18013bfbe  test    byte ptr [rax+r8+19AF10h], 1
0x18013bfc7  jmp     short loc_18013BFD2
0x18013bfc9  test    byte ptr [rax+r8+19AF10h], 2
0x18013bfd2  jnz     short loc_18013C033
0x18013bfd4  lea     r8, rva off_18019AF00[r8]; "AdministratorAccountName" ...
0x18013bfdb  add     r8, rax; struct LAPS_SZ_SETTING *
0x18013bfde  lea     r9, [rbp+arg_8]; struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting **
0x18013bfe2  mov     rdx, r13; struct LAPS_POLICY_ROOT *
0x18013bfe5  mov     rcx, [rbp+hKey]; HKEY
0x18013bfe9  call    ?QueryPolicySzValue@@YAJPEAUHKEY__@@PEBULAPS_POLICY_ROOT@@PEBULAPS_SZ_SETTING@@PEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@Z; QueryPolicySzValue(HKEY__ *,LAPS_POLICY_ROOT const *,LAPS_SZ_SETTING const *,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *)
0x18013bfee  mov     ebx, eax
0x18013bff0  test    eax, eax
0x18013bff2  js      short loc_18013C03E
0x18013bff4  mov     rax, [rbp+arg_8]
0x18013bff8  test    r15d, r15d
0x18013bffb  jnz     short loc_18013C00B
0x18013bffd  mov     r15d, r14d
0x18013c000  cmp     [rax+80h], r14d
0x18013c007  setz    r15b
0x18013c00b  mov     rdx, qword ptr [rbp+var_38+8]
0x18013c00f  cmp     rdx, [rbp+var_28]
0x18013c013  jz      short loc_18013C01F
0x18013c015  mov     [rdx], rax
0x18013c018  add     qword ptr [rbp+var_38+8], 8
0x18013c01d  jmp     short loc_18013C02C
0x18013c01f  lea     r8, [rbp+arg_8]
0x18013c023  lea     rcx, [rbp+var_38]
0x18013c027  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013c02c  lea     r8, __ImageBase
0x18013c033  inc     edi
0x18013c035  lea     r12, [r13+10h]
0x18013c039  jmp     loc_18013BFA9
0x18013c03e  mov     r9d, eax
0x18013c041  mov     edx, 331h
0x18013c046  jmp     loc_18013BE93
0x18013c04b  mov     edi, r14d
0x18013c04e  cmp     edi, 5
0x18013c051  jnb     loc_18013C0F0
0x18013c057  mov     eax, edi
0x18013c059  lea     rcx, [rax+rax*2]
0x18013c05d  shl     rcx, 3
0x18013c061  cmp     [r12], r14d
0x18013c065  jz      short loc_18013C072
0x18013c067  test    byte ptr [rcx+r8+19AE8Ch], 1
0x18013c070  jmp     short loc_18013C07B
0x18013c072  test    byte ptr [rcx+r8+19AE8Ch], 2
0x18013c07b  jnz     short loc_18013C0DC
0x18013c07d  lea     r8, rva off_18019AE80[r8]; "PasswordExpirationProtectionEnabled" ...
0x18013c084  add     r8, rcx; struct LAPS_BOOL_SETTING *
0x18013c087  lea     r9, [rbp+arg_8]; struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting **
0x18013c08b  mov     rdx, r13; struct LAPS_POLICY_ROOT *
0x18013c08e  mov     rcx, [rbp+hKey]; HKEY
0x18013c092  call    ?QueryPolicyBoolValue@@YAJPEAUHKEY__@@PEBULAPS_POLICY_ROOT@@PEBULAPS_BOOL_SETTING@@PEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@Z; QueryPolicyBoolValue(HKEY__ *,LAPS_POLICY_ROOT const *,LAPS_BOOL_SETTING const *,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *)
0x18013c097  mov     ebx, eax
0x18013c099  test    eax, eax
0x18013c09b  js      short loc_18013C0E3
0x18013c09d  mov     rax, [rbp+arg_8]
0x18013c0a1  test    r15d, r15d
0x18013c0a4  jnz     short loc_18013C0B4
0x18013c0a6  mov     r15d, r14d
0x18013c0a9  cmp     [rax+80h], r14d
0x18013c0b0  setz    r15b
0x18013c0b4  mov     rdx, qword ptr [rbp+var_38+8]
0x18013c0b8  cmp     rdx, [rbp+var_28]
0x18013c0bc  jz      short loc_18013C0C8
0x18013c0be  mov     [rdx], rax
0x18013c0c1  add     qword ptr [rbp+var_38+8], 8
0x18013c0c6  jmp     short loc_18013C0D5
0x18013c0c8  lea     r8, [rbp+arg_8]
0x18013c0cc  lea     rcx, [rbp+var_38]
0x18013c0d0  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013c0d5  lea     r8, __ImageBase
0x18013c0dc  inc     edi
0x18013c0de  jmp     loc_18013C04E
0x18013c0e3  mov     r9d, eax
0x18013c0e6  mov     edx, 345h
0x18013c0eb  jmp     loc_18013BE93
0x18013c0f0  mov     edi, r14d
0x18013c0f3  cmp     [r12], r14d
0x18013c0f7  jz      short loc_18013C175
0x18013c0f9  jmp     short loc_18013C0FE
0x18013c0fb  xor     r14d, r14d
0x18013c0fe  mov     esi, r14d
0x18013c101  mov     r14d, esi
0x18013c104  mov     rax, qword ptr [rbp+var_38+8]
0x18013c108  mov     rcx, qword ptr [rbp+var_38]
0x18013c10c  sub     rax, rcx
0x18013c10f  sar     rax, 3
0x18013c113  cmp     r14, rax
0x18013c116  jnb     short loc_18013C169
0x18013c118  mov     edx, edi
0x18013c11a  mov     rdx, ds:rva off_18019BC10[r8+rdx*8]; "BackupDirectory" ...
0x18013c122  mov     rcx, [rcx+r14*8]
0x18013c126  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x18013c12b  test    al, al
0x18013c12d  jnz     short loc_18013C13A
0x18013c12f  inc     esi
0x18013c131  lea     r8, __ImageBase
0x18013c138  jmp     short loc_18013C101
0x18013c13a  mov     rax, qword ptr [rbp+var_38]
0x18013c13e  lea     r8, [rax+r14*8]
0x18013c142  mov     rdx, qword ptr [rbp+var_18]
0x18013c146  cmp     rdx, qword ptr [rbp+var_18+8]
0x18013c14a  jz      short loc_18013C159
0x18013c14c  mov     rax, [r8]
0x18013c14f  mov     [rdx], rax
0x18013c152  add     qword ptr [rbp+var_18], 8
0x18013c157  jmp     short loc_18013C162
0x18013c159  lea     rcx, [rbp+var_20]
0x18013c15d  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013c162  lea     r8, __ImageBase
0x18013c169  inc     edi
0x18013c16b  cmp     edi, 0Ch
0x18013c16e  jb      short loc_18013C0FB
0x18013c170  jmp     short loc_18013C1E7
0x18013c172  xor     r14d, r14d
0x18013c175  mov     esi, r14d
0x18013c178  mov     r14d, esi
0x18013c17b  mov     rax, qword ptr [rbp+var_38+8]
0x18013c17f  mov     rcx, qword ptr [rbp+var_38]
0x18013c183  sub     rax, rcx
0x18013c186  sar     rax, 3
0x18013c18a  cmp     r14, rax
0x18013c18d  jnb     short loc_18013C1E0
0x18013c18f  mov     edx, edi
0x18013c191  mov     rdx, ds:rva off_18019BC10[r8+rdx*8]; "BackupDirectory" ...
0x18013c199  mov     rcx, [rcx+r14*8]
0x18013c19d  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x18013c1a2  test    al, al
0x18013c1a4  jnz     short loc_18013C1B1
0x18013c1a6  inc     esi
0x18013c1a8  lea     r8, __ImageBase
0x18013c1af  jmp     short loc_18013C178
0x18013c1b1  mov     rax, qword ptr [rbp+var_38]
0x18013c1b5  lea     r8, [rax+r14*8]
0x18013c1b9  mov     rdx, qword ptr [rbp+var_18]
0x18013c1bd  cmp     rdx, qword ptr [rbp+var_18+8]
0x18013c1c1  jz      short loc_18013C1D0
0x18013c1c3  mov     rax, [r8]
0x18013c1c6  mov     [rdx], rax
0x18013c1c9  add     qword ptr [rbp+var_18], 8
0x18013c1ce  jmp     short loc_18013C1D9
0x18013c1d0  lea     rcx, [rbp+var_20]
0x18013c1d4  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013c1d9  lea     r8, __ImageBase
0x18013c1e0  inc     edi
0x18013c1e2  cmp     edi, 6
0x18013c1e5  jb      short loc_18013C172
0x18013c1e7  mov     rdx, [r13+8]
0x18013c1eb  mov     rdi, [rbp+arg_0]
0x18013c1ef  mov     rcx, rdi
0x18013c1f2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18013c1f7  mov     eax, [r12]
0x18013c1fb  mov     [rdi+20h], eax
0x18013c1fe  mov     [rdi+24h], r15d
0x18013c202  lea     rcx, [rdi+28h]
0x18013c206  lea     rax, [rbp+var_20]
0x18013c20a  cmp     rcx, rax
0x18013c20d  jz      short loc_18013C224
0x18013c20f  mov     rdx, [rbp+var_20]
0x18013c213  mov     r8, qword ptr [rbp+var_18]
0x18013c217  sub     r8, rdx
0x18013c21a  sar     r8, 3
0x18013c21e  call    ??$_Assign_counted_range@PEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAXPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@_K@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Assign_counted_range<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *,unsigned __int64)
0x18013c223  nop
0x18013c224  mov     rcx, [rbp+var_20]
0x18013c228  test    rcx, rcx
0x18013c22b  jz      short loc_18013C24D
0x18013c22d  mov     rdx, qword ptr [rbp+var_18+8]
0x18013c231  sub     rdx, rcx
0x18013c234  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18013c238  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013c23d  mov     [rbp+var_20], 0
0x18013c245  xorps   xmm0, xmm0
  ... truncated ...
```
