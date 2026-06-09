# CloudStoreTipTest::GetFailureReportMode

- ea: `0x1800f9d00`
- end: `0x1800fa08f`
- name: `CloudStoreTipTest::GetFailureReportMode`
- size: `911`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800438a4`
- `0x18008e164`
- `0x18009fbf4`
- `0x1800f5f78`
- `0x18010a170`
- `0x18010d024`
- `0x18011c5d0`
- `0x1801755e4`
- `0x180175970`

## callees

- `0x180076110`
- `0x180091700`
- `0x1800e0c20`
- `0x1800f9d00`
- `0x180160154`
- `0x180163d44`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9dbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9dfd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9e29`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9e6a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9e91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9eb8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9edf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9f25`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9f4c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9f73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9f9a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9fbd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9fe0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9dbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9dfd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9e29`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9e6a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9e91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9eb8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9edf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9f25`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9f4c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9f73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9f9a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9fbd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f9fe0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudStoreTipTest::GetFailureReportMode(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // esi
  char v4; // r15
  __int64 v5; // rdi
  __int64 v6; // r12
  unsigned int v7; // r14d
  char IsEnabled; // al
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF
  __int128 v11; // [rsp+40h] [rbp-28h]
  __int64 v12; // [rsp+50h] [rbp-18h]
  int v13; // [rsp+B0h] [rbp+48h] BYREF

  v2 = *(_QWORD *)(a1 + 80);
  if ( !v2 )
    return 1;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&v10);
  v3 = 0;
  v4 = 0;
  v5 = *(_QWORD *)(a1 + 64);
  v6 = v5 + 168LL * *(_QWORD *)(a1 + 80);
  v7 = 3;
  while ( v5 != v6 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DirectCloudSync>::GetImpl'::`2'::impl);
    if ( *(_DWORD *)(v5 + 8) == -2147319765 )
      goto LABEL_41;
    if ( IsEnabled )
    {
      if ( *(_QWORD *)(v5 + 24) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::GetImpl'::`2'::impl) )
        {
          if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipIgnore", -1, 0) == 2 )
            goto LABEL_9;
          if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipForceWarn", -1, 0) == 2 )
          {
LABEL_12:
            v13 = 1;
            goto LABEL_10;
          }
          if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipResume", -1, 0) == 2 )
            goto LABEL_14;
        }
        if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipPass", -1, 0) != 2 )
        {
          if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipWarn", -1, 0) != 2 )
          {
            if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipAfcTimeout", -1, 0) == 2 )
            {
LABEL_29:
              v4 = 1;
            }
            else if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), 13, L"**!!##!!**Log", -1, 0) != 2 )
            {
              goto LABEL_32;
            }
          }
LABEL_30:
          ++v3;
        }
LABEL_31:
        --v2;
      }
    }
    else if ( *(_QWORD *)(v5 + 24) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::GetImpl'::`2'::impl) )
      {
        if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipIgnore", -1, 0) == 2 )
        {
LABEL_9:
          v13 = 2;
LABEL_10:
          --v2;
          std::deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___::_Emplace_back_internal_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_(
            &v10,
            &v13);
          goto LABEL_36;
        }
        if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipForceWarn", -1, 0) == 2 )
          goto LABEL_12;
        if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipResume", -1, 0) == 2 )
        {
LABEL_14:
          --v2;
          if ( !--v12 )
            *((_QWORD *)&v11 + 1) = 0;
          goto LABEL_36;
        }
      }
      if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipPass", -1, 0) == 2 )
        goto LABEL_31;
      if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipWarn", -1, 0) == 2 )
        goto LABEL_30;
      if ( CompareStringOrdinal(*(LPCWCH *)(v5 + 24), -1, L"**!!##!!**NoLogTipAfcTimeout", -1, 0) == 2 )
        goto LABEL_29;
    }
LABEL_32:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::GetImpl'::`2'::impl) )
    {
      if ( v12 )
      {
        --v2;
        if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v10 + 1)
                                   + 8 * ((v11 - 1) & ((unsigned __int64)(v12 - 1 + *((_QWORD *)&v11 + 1)) >> 2)))
                       + 4 * ((v12 - 1 + *((_QWORD *)&v11 + 1)) & 3)) == 1 )
          ++v3;
      }
    }
LABEL_36:
    v5 += 168;
  }
  if ( v2 )
  {
LABEL_42:
    std::deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___::_deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___(&v10);
    return v7;
  }
  if ( v4 )
  {
    v7 = 0;
    goto LABEL_42;
  }
  if ( v3 )
  {
LABEL_41:
    v7 = 2;
    goto LABEL_42;
  }
  std::deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___::_deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___(&v10);
  return 1;
}

```

## disassembly

```asm
0x1800f9d00  push    rbp
0x1800f9d02  push    rbx
0x1800f9d03  push    rsi
0x1800f9d04  push    rdi
0x1800f9d05  push    r12
0x1800f9d07  push    r13
0x1800f9d09  push    r14
0x1800f9d0b  push    r15
0x1800f9d0d  mov     rbp, rsp
0x1800f9d10  sub     rsp, 68h
0x1800f9d14  mov     r14, rcx
0x1800f9d17  mov     rbx, [rcx+50h]
0x1800f9d1b  xor     r13d, r13d
0x1800f9d1e  test    rbx, rbx
0x1800f9d21  jz      loc_1800FA079
0x1800f9d27  xorps   xmm0, xmm0
0x1800f9d2a  movdqu  [rbp+var_38], xmm0
0x1800f9d2f  xorps   xmm1, xmm1
0x1800f9d32  movdqu  [rbp+var_28], xmm1
0x1800f9d37  mov     [rbp+var_18], r13
0x1800f9d3b  lea     rcx, [rbp+var_38]
0x1800f9d3f  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x1800f9d44  nop
0x1800f9d45  mov     esi, r13d
0x1800f9d48  mov     r15b, r13b
0x1800f9d4b  mov     rdi, [r14+40h]
0x1800f9d4f  imul    r12, [r14+50h], 0A8h
0x1800f9d57  add     r12, rdi
0x1800f9d5a  lea     r14d, [r13+3]
0x1800f9d5e  cmp     rdi, r12
0x1800f9d61  jz      loc_1800FA049
0x1800f9d67  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DirectCloudSync@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DirectCloudSync@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync> `wil::Feature<__WilFeatureTraits_Feature_DirectCloudSync>::GetImpl(void)'::`2'::impl
0x1800f9d6e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DirectCloudSync@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::__private_IsEnabled(void)
0x1800f9d73  cmp     dword ptr [rdi+8], 8002802Bh
0x1800f9d7a  jz      loc_1800FA05C
0x1800f9d80  test    al, al
0x1800f9d82  jz      loc_1800F9EF3
0x1800f9d88  cmp     [rdi+18h], r13
0x1800f9d8c  jz      loc_1800F9FF3
0x1800f9d92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad> `wil::Feature<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::GetImpl(void)'::`2'::impl
0x1800f9d99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::__private_IsEnabled(void)
0x1800f9d9e  test    al, al
0x1800f9da0  jz      loc_1800F9E52
0x1800f9da6  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9dab  or      eax, 0FFFFFFFFh
0x1800f9dae  mov     r9d, eax; cchCount2
0x1800f9db1  lea     r8, aNologtipignore; "**!!##!!**NoLogTipIgnore"
0x1800f9db8  mov     edx, eax; cchCount1
0x1800f9dba  mov     rcx, [rdi+18h]; lpString1
0x1800f9dbe  call    cs:__imp_CompareStringOrdinal
0x1800f9dc4  cmp     eax, 2
0x1800f9dc7  jnz     short loc_1800F9DE5
0x1800f9dc9  mov     [rbp+arg_0], 2
0x1800f9dd0  dec     rbx
0x1800f9dd3  lea     rdx, [rbp+arg_0]
0x1800f9dd7  lea     rcx, [rbp+var_38]
0x1800f9ddb  call    std__deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState______Emplace_back_internal_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_
0x1800f9de0  jmp     loc_1800FA03D
0x1800f9de5  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9dea  or      eax, 0FFFFFFFFh
0x1800f9ded  mov     r9d, eax; cchCount2
0x1800f9df0  lea     r8, aNologtipforcew_0; "**!!##!!**NoLogTipForceWarn"
0x1800f9df7  mov     edx, eax; cchCount1
0x1800f9df9  mov     rcx, [rdi+18h]; lpString1
0x1800f9dfd  call    cs:__imp_CompareStringOrdinal
0x1800f9e03  cmp     eax, 2
0x1800f9e06  jnz     short loc_1800F9E11
0x1800f9e08  mov     [rbp+arg_0], 1
0x1800f9e0f  jmp     short loc_1800F9DD0
0x1800f9e11  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9e16  or      eax, 0FFFFFFFFh
0x1800f9e19  mov     r9d, eax; cchCount2
0x1800f9e1c  lea     r8, aNologtipresume; "**!!##!!**NoLogTipResume"
0x1800f9e23  mov     edx, eax; cchCount1
0x1800f9e25  mov     rcx, [rdi+18h]; lpString1
0x1800f9e29  call    cs:__imp_CompareStringOrdinal
0x1800f9e2f  cmp     eax, 2
0x1800f9e32  jnz     short loc_1800F9E52
0x1800f9e34  dec     rbx
0x1800f9e37  mov     rax, [rbp+var_18]
0x1800f9e3b  sub     rax, 1
0x1800f9e3f  mov     [rbp+var_18], rax
0x1800f9e43  jnz     loc_1800FA03D
0x1800f9e49  mov     qword ptr [rbp+var_28+8], r13
0x1800f9e4d  jmp     loc_1800FA03D
0x1800f9e52  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9e57  or      eax, 0FFFFFFFFh
0x1800f9e5a  mov     r9d, eax; cchCount2
0x1800f9e5d  lea     r8, aNologtippass_0; "**!!##!!**NoLogTipPass"
0x1800f9e64  mov     edx, eax; cchCount1
0x1800f9e66  mov     rcx, [rdi+18h]; lpString1
0x1800f9e6a  call    cs:__imp_CompareStringOrdinal
0x1800f9e70  cmp     eax, 2
0x1800f9e73  jz      loc_1800F9FF0
0x1800f9e79  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9e7e  or      eax, 0FFFFFFFFh
0x1800f9e81  mov     r9d, eax; cchCount2
0x1800f9e84  lea     r8, aNologtipwarn_0; "**!!##!!**NoLogTipWarn"
0x1800f9e8b  mov     edx, eax; cchCount1
0x1800f9e8d  mov     rcx, [rdi+18h]; lpString1
0x1800f9e91  call    cs:__imp_CompareStringOrdinal
0x1800f9e97  cmp     eax, 2
0x1800f9e9a  jz      loc_1800F9FEE
0x1800f9ea0  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9ea5  or      eax, 0FFFFFFFFh
0x1800f9ea8  mov     r9d, eax; cchCount2
0x1800f9eab  lea     r8, aNologtipafctim_2; "**!!##!!**NoLogTipAfcTimeout"
0x1800f9eb2  mov     edx, eax; cchCount1
0x1800f9eb4  mov     rcx, [rdi+18h]; lpString1
0x1800f9eb8  call    cs:__imp_CompareStringOrdinal
0x1800f9ebe  cmp     eax, 2
0x1800f9ec1  jz      loc_1800F9FEB
0x1800f9ec7  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9ecc  or      r9d, 0FFFFFFFFh; cchCount2
0x1800f9ed0  lea     r8, aLog_1; "**!!##!!**Log"
0x1800f9ed7  lea     edx, [r9+0Eh]; cchCount1
0x1800f9edb  mov     rcx, [rdi+18h]; lpString1
0x1800f9edf  call    cs:__imp_CompareStringOrdinal
0x1800f9ee5  cmp     eax, 2
0x1800f9ee8  jz      loc_1800F9FEE
0x1800f9eee  jmp     loc_1800F9FF3
0x1800f9ef3  cmp     [rdi+18h], r13
0x1800f9ef7  jz      loc_1800F9FF3
0x1800f9efd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad> `wil::Feature<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::GetImpl(void)'::`2'::impl
0x1800f9f04  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::__private_IsEnabled(void)
0x1800f9f09  test    al, al
0x1800f9f0b  jz      short loc_1800F9F82
0x1800f9f0d  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9f12  or      eax, 0FFFFFFFFh
0x1800f9f15  mov     r9d, eax; cchCount2
0x1800f9f18  lea     r8, aNologtipignore; "**!!##!!**NoLogTipIgnore"
0x1800f9f1f  mov     edx, eax; cchCount1
0x1800f9f21  mov     rcx, [rdi+18h]; lpString1
0x1800f9f25  call    cs:__imp_CompareStringOrdinal
0x1800f9f2b  cmp     eax, 2
0x1800f9f2e  jz      loc_1800F9DC9
0x1800f9f34  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9f39  or      eax, 0FFFFFFFFh
0x1800f9f3c  mov     r9d, eax; cchCount2
0x1800f9f3f  lea     r8, aNologtipforcew_0; "**!!##!!**NoLogTipForceWarn"
0x1800f9f46  mov     edx, eax; cchCount1
0x1800f9f48  mov     rcx, [rdi+18h]; lpString1
0x1800f9f4c  call    cs:__imp_CompareStringOrdinal
0x1800f9f52  cmp     eax, 2
0x1800f9f55  jz      loc_1800F9E08
0x1800f9f5b  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9f60  or      eax, 0FFFFFFFFh
0x1800f9f63  mov     r9d, eax; cchCount2
0x1800f9f66  lea     r8, aNologtipresume; "**!!##!!**NoLogTipResume"
0x1800f9f6d  mov     edx, eax; cchCount1
0x1800f9f6f  mov     rcx, [rdi+18h]; lpString1
0x1800f9f73  call    cs:__imp_CompareStringOrdinal
0x1800f9f79  cmp     eax, 2
0x1800f9f7c  jz      loc_1800F9E34
0x1800f9f82  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9f87  or      eax, 0FFFFFFFFh
0x1800f9f8a  mov     r9d, eax; cchCount2
0x1800f9f8d  lea     r8, aNologtippass_0; "**!!##!!**NoLogTipPass"
0x1800f9f94  mov     edx, eax; cchCount1
0x1800f9f96  mov     rcx, [rdi+18h]; lpString1
0x1800f9f9a  call    cs:__imp_CompareStringOrdinal
0x1800f9fa0  cmp     eax, 2
0x1800f9fa3  jz      short loc_1800F9FF0
0x1800f9fa5  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9faa  or      eax, 0FFFFFFFFh
0x1800f9fad  mov     r9d, eax; cchCount2
0x1800f9fb0  lea     r8, aNologtipwarn_0; "**!!##!!**NoLogTipWarn"
0x1800f9fb7  mov     edx, eax; cchCount1
0x1800f9fb9  mov     rcx, [rdi+18h]; lpString1
0x1800f9fbd  call    cs:__imp_CompareStringOrdinal
0x1800f9fc3  cmp     eax, 2
0x1800f9fc6  jz      short loc_1800F9FEE
0x1800f9fc8  mov     [rsp+68h+bIgnoreCase], r13d; bIgnoreCase
0x1800f9fcd  or      eax, 0FFFFFFFFh
0x1800f9fd0  mov     r9d, eax; cchCount2
0x1800f9fd3  lea     r8, aNologtipafctim_2; "**!!##!!**NoLogTipAfcTimeout"
0x1800f9fda  mov     edx, eax; cchCount1
0x1800f9fdc  mov     rcx, [rdi+18h]; lpString1
0x1800f9fe0  call    cs:__imp_CompareStringOrdinal
0x1800f9fe6  cmp     eax, 2
0x1800f9fe9  jnz     short loc_1800F9FF3
0x1800f9feb  mov     r15b, 1
0x1800f9fee  inc     esi
0x1800f9ff0  dec     rbx
0x1800f9ff3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad> `wil::Feature<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::GetImpl(void)'::`2'::impl
0x1800f9ffa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AcknowledgeReceiptOnLoad>::__private_IsEnabled(void)
0x1800f9fff  test    al, al
0x1800fa001  jz      short loc_1800FA03D
0x1800fa003  mov     rcx, [rbp+var_18]
0x1800fa007  test    rcx, rcx
0x1800fa00a  jz      short loc_1800FA03D
0x1800fa00c  dec     rbx
0x1800fa00f  mov     rdx, qword ptr [rbp+var_28+8]
0x1800fa013  dec     rcx
0x1800fa016  add     rdx, rcx
0x1800fa019  mov     rcx, rdx
0x1800fa01c  shr     rcx, 2
0x1800fa020  mov     rax, qword ptr [rbp+var_28]
0x1800fa024  dec     rax
0x1800fa027  and     rcx, rax
0x1800fa02a  and     rdx, r14
0x1800fa02d  mov     rax, qword ptr [rbp+var_38+8]
0x1800fa031  mov     rcx, [rax+rcx*8]
0x1800fa035  cmp     dword ptr [rcx+rdx*4], 1
0x1800fa039  jnz     short loc_1800FA03D
0x1800fa03b  inc     esi
0x1800fa03d  add     rdi, 0A8h
0x1800fa044  jmp     loc_1800F9D5E
0x1800fa049  test    rbx, rbx
0x1800fa04c  jnz     short loc_1800FA062
0x1800fa04e  test    r15b, r15b
0x1800fa051  jz      short loc_1800FA058
0x1800fa053  mov     r14d, r13d
0x1800fa056  jmp     short loc_1800FA062
0x1800fa058  test    esi, esi
0x1800fa05a  jz      short loc_1800FA070
0x1800fa05c  mov     r14d, 2
0x1800fa062  lea     rcx, [rbp+var_38]
0x1800fa066  call    std__deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState______deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState___
0x1800fa06b  mov     eax, r14d
0x1800fa06e  jmp     short loc_1800FA07E
0x1800fa070  lea     rcx, [rbp+var_38]
0x1800fa074  call    std__deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState______deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState___
0x1800fa079  mov     eax, 1
0x1800fa07e  add     rsp, 68h
0x1800fa082  pop     r15
0x1800fa084  pop     r14
0x1800fa086  pop     r13
0x1800fa088  pop     r12
0x1800fa08a  pop     rdi
0x1800fa08b  pop     rsi
0x1800fa08c  pop     rbx
0x1800fa08d  pop     rbp
0x1800fa08e  retn
```
