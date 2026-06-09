# DeclaredConfigurationStore_GetOutOfBoxMergeRulesFromCspSchema(CspSchema *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,int *,ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800759e4`
- end: `0x180075ee0`
- name: `?DeclaredConfigurationStore_GetOutOfBoxMergeRulesFromCspSchema@@YAXPEAVCspSchema@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAHPEAKAEAV23@@Z`
- size: `1276`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800758d4`

## callees

- `0x18000b9e0`
- `0x180014348`
- `0x18001440c`
- `0x180018a70`
- `0x180018ac0`
- `0x180019d38`
- `0x18001bc98`
- `0x18004abf8`
- `0x18004b500`
- `0x18004babc`
- `0x18004bc88`
- `0x180055540`
- `0x1800759e4`
- `0x18009ad08`
- `0x1800a093c`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180103cc4`
- `0x180104de0`
- `0x180104fc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180075a79`
- `OLEAUT32!__imp_VariantInit` at `0x180075c57`
- `OLEAUT32!__imp_VariantInit` at `0x180075cf6`
- `OLEAUT32!__imp_VariantInit` at `0x180075d9b`
- `OLEAUT32!__imp_VariantInit` at `0x180075c57`
- `OLEAUT32!__imp_VariantInit` at `0x180075cf6`
- `OLEAUT32!__imp_VariantInit` at `0x180075d9b`
- `OLEAUT32!__imp_VariantClear` at `0x180075ce1`
- `OLEAUT32!__imp_VariantClear` at `0x180075d7f`
- `OLEAUT32!__imp_VariantClear` at `0x180075ce1`
- `OLEAUT32!__imp_VariantClear` at `0x180075d7f`

## string_xrefs

- `0x180075e91`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180075e7b`: `DeclaredConfigurationStore_GetInboxMergeAlgorithmFromCspSchema`
- `0x180075b46`: `DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema`
- `0x180075c9c`: `DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema`
- `0x180075d2d`: `DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema`
- `0x180075dd4`: `DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema`
- `0x180075e3e`: `DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema`
- `0x180075ebf`: `DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DeclaredConfigurationStore_GetOutOfBoxMergeRulesFromCspSchema(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        LONG *a4,
        char **a5)
{
  _QWORD *v9; // rdx
  _DWORD *v10; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  _QWORD *v13; // r9
  _QWORD *v14; // rax
  int v15; // r9d
  _QWORD *v16; // rdx
  _QWORD *v17; // rdx
  unsigned __int64 i; // rdi
  char *v19; // rbx
  char *v20; // rdx
  CDeclaredConfigurationLogger *v21; // rax
  unsigned int v22; // r8d
  std::_Ref_count_base *v23; // rcx
  std::_Ref_count_base *llVal; // rdi
  NodeSchema *v25; // r14
  NodeSchema *v26; // r13
  char *v27; // rdx
  std::_Ref_count_base *v28; // rcx
  int v30; // ebx
  CDeclaredConfigurationLogger *v31; // rax
  unsigned int v32; // r8d
  unsigned int Lo; // eax
  int v34; // ebx
  CDeclaredConfigurationLogger *v35; // rax
  unsigned int v36; // r8d
  __int64 v37; // r8
  int v38; // r14d
  CDeclaredConfigurationLogger *v39; // rax
  unsigned int v40; // r8d
  __int64 v41; // r8
  CDeclaredConfigurationLogger *v42; // rax
  unsigned int v43; // r8d
  CDeclaredConfigurationLogger *v44; // rax
  CDeclaredConfigurationLogger *Logger; // rax
  unsigned int v46; // r8d
  int v47; // [rsp+20h] [rbp-91h]
  int v48; // [rsp+20h] [rbp-91h]
  int v49; // [rsp+20h] [rbp-91h]
  int v50; // [rsp+20h] [rbp-91h]
  int v51; // [rsp+20h] [rbp-91h]
  int v52; // [rsp+20h] [rbp-91h]
  int v53; // [rsp+20h] [rbp-91h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-81h] BYREF
  std::_Ref_count_base *v55[2]; // [rsp+48h] [rbp-69h] BYREF
  char *v56; // [rsp+58h] [rbp-59h] BYREF
  char *v57; // [rsp+60h] [rbp-51h]
  VARIANTARG v58; // [rsp+70h] [rbp-41h] BYREF
  char **v59; // [rsp+88h] [rbp-29h]
  __int64 v60; // [rsp+90h] [rbp-21h]
  _QWORD v61[3]; // [rsp+98h] [rbp-19h] BYREF
  unsigned __int64 v62; // [rsp+B0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v60 = a2;
  v59 = a5;
  std::vector<ConfigDoc>::vector<ConfigDoc>(&v56);
  if ( !v11 || !v10 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      Logger,
      L"DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema",
      &word_180142E98,
      L"mergeRuleType is nullptr",
      -2147024809);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x6D17, v46, (const char *)0x80070057LL, v53);
  }
  *v10 = 0;
  std::wstring::wstring((__int64)v61, v9);
  v13 = v61;
  if ( v62 > 7 )
    v13 = (_QWORD *)v61[0];
  v14 = (_QWORD *)std::wstring::end(v61, &pvarg, v12, v13);
  v16 = v61;
  if ( v62 > 7 )
    LODWORD(v16) = v61[0];
  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
    (unsigned int)v55,
    (_DWORD)v16,
    *v14,
    v15,
    *(__int64 *)&_o_towlower);
  v17 = v61;
  if ( v62 > 7 )
    v17 = (_QWORD *)v61[0];
  dmtl::split<std::back_insert_iterator<std::vector<std::wstring>>,unsigned short>(v55, v17, 47, &v56);
  for ( i = 0; ; ++i )
  {
    v19 = v56;
    if ( i >= (v57 - v56) >> 5 )
      break;
    if ( !(unsigned int)std::wstring::compare(&v56[32 * i], L"vendor") )
    {
      if ( i + 3 >= (v57 - v56) >> 5 )
      {
        v21 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v21,
          L"DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema",
          &word_180142E98,
          L"cspNodeIndex index out of bounds",
          -2147418113);
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x6D32, v22, (const char *)0x8000FFFFLL, v47);
      }
      std::vector<std::wstring>::erase(&v56, v55, v56, &v56[32 * i + 96]);
      v19 = v56;
      break;
    }
  }
  *(_OWORD *)v55 = 0;
  if ( *((_QWORD *)v19 + 3) <= 7u )
    v20 = v19;
  else
    v20 = *(char **)v19;
  if ( (int)CspSchema::GetChildNodeByName(a1, v20, 0, v55) >= 0 )
  {
    llVal = v55[1];
    v25 = v55[0];
    while ( 1 )
    {
      v19 += 32;
      if ( v19 == v57 )
        break;
      *(_OWORD *)&pvarg.vt = 0;
      v26 = v25;
      if ( *((_QWORD *)v19 + 3) <= 7u )
        v27 = v19;
      else
        v27 = *(char **)v19;
      if ( (int)NodeSchema::GetChildNodeByName(v25, v27, &pvarg) < 0 )
      {
        if ( pvarg.llVal )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)pvarg.llVal);
        goto LABEL_32;
      }
      v25 = *(NodeSchema **)&pvarg.vt;
      *(_OWORD *)v55 = *(_OWORD *)&pvarg.vt;
      *(_QWORD *)&pvarg.vt = v26;
      v28 = llVal;
      llVal = (std::_Ref_count_base *)pvarg.llVal;
      if ( v28 )
        std::_Ref_count_base::_Decref(v28);
    }
    VariantInit(&pvarg);
    v30 = NodeSchema::CheckNodeProperty(v25, L"mergeRule", &pvarg);
    if ( v30 == -2147024894 )
    {
      *a4 = 0;
    }
    else
    {
      if ( v30 < 0 )
      {
        v31 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v31,
          L"DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema",
          &word_180142E98,
          L"CheckNodeProperty failed",
          v30);
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x6D64, v32, (const char *)(unsigned int)v30, v48);
      }
      if ( pvarg.vt != 3 )
      {
        v44 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v44,
          L"DeclaredConfigurationStore_GetInboxMergeAlgorithmFromCspSchema",
          &word_180142E98,
          L"mergeRuleType has unexpected variant type. Expected type is: VT_I4",
          -2147418113);
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x6DAD,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8000FFFFLL,
          v52);
      }
      Lo = pvarg.cyVal.Lo;
      *a4 = pvarg.lVal;
      if ( Lo >= 7 )
      {
        if ( Lo == 7 )
        {
          VariantInit(&v58);
          v34 = NodeSchema::CheckNodeProperty(v25, L"delimiter", &v58);
          if ( v34 < 0 )
          {
            v35 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v35,
              L"DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema",
              &word_180142E98,
              L"CheckNodeProperty failed",
              v34);
            wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x6D7C, v36, (const char *)(unsigned int)v34, v49);
          }
          if ( v58.vt == 8 )
          {
            v37 = -1;
            do
              ++v37;
            while ( *(_WORD *)(v58.llVal + 2 * v37) );
            std::wstring::_Assign<unsigned short>(v59, v58.bstrVal, (char *)v37);
            *a3 = 1;
          }
        }
        else
        {
          if ( Lo != 8 )
          {
            v42 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v42,
              L"DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema",
              &word_180142E98,
              L"Invalid MergeRule",
              -2147024809);
            wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x6DA2, v43, (const char *)0x80070057LL, v51);
          }
          VariantInit(&v58);
          v38 = NodeSchema::CheckNodeProperty(v25, L"admxPayload", &v58);
          if ( v38 < 0 )
          {
            v39 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v39,
              L"DeclaredConfigurationStore_GetOutOfBoxMergeAlgorithmFromCspSchema",
              &word_180142E98,
              L"CheckNodeProperty failed",
              v38);
            wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x6D91, v40, (const char *)(unsigned int)v38, v50);
          }
          if ( v58.vt == 8 )
          {
            v41 = -1;
            do
              ++v41;
            while ( *(_WORD *)(v58.llVal + 2 * v41) );
            std::wstring::_Assign<unsigned short>(v59, v58.bstrVal, (char *)v41);
            *a3 = 1;
          }
        }
        VariantClear(&v58);
      }
      else
      {
        *a3 = 1;
      }
    }
    VariantClear(&pvarg);
LABEL_32:
    if ( llVal )
    {
      v23 = llVal;
LABEL_34:
      std::_Ref_count_base::_Decref(v23);
    }
  }
  else
  {
    v23 = v55[1];
    if ( v55[1] )
      goto LABEL_34;
  }
  std::wstring::_Tidy_deallocate(v61);
  std::vector<std::wstring>::_Tidy(&v56);
  return std::wstring::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x1800759e4  push    rbp
0x1800759e6  push    rbx
0x1800759e7  push    rsi
0x1800759e8  push    rdi
0x1800759e9  push    r12
0x1800759eb  push    r13
0x1800759ed  push    r14
0x1800759ef  push    r15
0x1800759f1  lea     rbp, [rsp-17h]
0x1800759f6  sub     rsp, 0C8h
0x1800759fd  mov     rax, cs:__security_cookie
0x180075a04  xor     rax, rsp
0x180075a07  mov     [rbp+4Fh+var_48], rax
0x180075a0b  mov     r12, r9
0x180075a0e  mov     r15, r8
0x180075a11  mov     rsi, rdx
0x180075a14  mov     r14, rcx
0x180075a17  mov     [rbp+4Fh+var_70], rdx
0x180075a1b  mov     r13, [rbp+4Fh+arg_20]
0x180075a1f  mov     [rbp+4Fh+var_78], r13
0x180075a23  lea     rcx, [rbp+4Fh+var_A8]
0x180075a27  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x180075a2c  nop
0x180075a2d  xor     r13d, r13d
0x180075a30  test    r9, r9
0x180075a33  jz      loc_180075EA3
0x180075a39  test    r8, r8
0x180075a3c  jz      loc_180075EA3
0x180075a42  mov     [r8], r13d
0x180075a45  lea     rcx, [rbp+4Fh+var_68]
0x180075a49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180075a4e  nop
0x180075a4f  lea     r9, [rbp+4Fh+var_68]
0x180075a53  cmp     [rbp+4Fh+var_50], 7
0x180075a58  cmova   r9, [rbp+4Fh+var_68]
0x180075a5d  lea     rdx, [rsp+100h+pvarg]
0x180075a62  lea     rcx, [rbp+4Fh+var_68]
0x180075a66  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180075a6b  lea     rdx, [rbp+4Fh+var_68]
0x180075a6f  cmp     [rbp+4Fh+var_50], 7
0x180075a74  cmova   rdx, [rbp+4Fh+var_68]
0x180075a79  mov     rcx, cs:__imp__o_towlower
0x180075a80  mov     qword ptr [rsp+100h+var_E0], rcx
0x180075a85  mov     r8, [rax]
0x180075a88  lea     rcx, [rbp+4Fh+var_B8]
0x180075a8c  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x180075a91  lea     rdx, [rbp+4Fh+var_68]
0x180075a95  cmp     [rbp+4Fh+var_50], 7
0x180075a9a  cmova   rdx, [rbp+4Fh+var_68]
0x180075a9f  lea     r8d, [r13+2Fh]
0x180075aa3  lea     r9, [rbp+4Fh+var_A8]
0x180075aa7  lea     rcx, [rbp+4Fh+var_B8]
0x180075aab  call    ??$split@V?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@G@dmtl@@YA?AV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEBGGV12@@Z; dmtl::split<std::back_insert_iterator<std::vector<std::wstring>>,ushort>(ushort const *,ushort,std::back_insert_iterator<std::vector<std::wstring>>)
0x180075ab0  mov     edi, r13d
0x180075ab3  mov     rbx, [rbp+4Fh+var_A8]
0x180075ab7  mov     rax, [rbp+4Fh+var_A0]
0x180075abb  sub     rax, rbx
0x180075abe  sar     rax, 5
0x180075ac2  cmp     rdi, rax
0x180075ac5  jnb     short loc_180075B16
0x180075ac7  mov     rcx, rdi
0x180075aca  shl     rcx, 5
0x180075ace  add     rcx, rbx
0x180075ad1  lea     rdx, aVendor_0; "vendor"
0x180075ad8  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180075add  test    eax, eax
0x180075adf  jz      short loc_180075AE6
0x180075ae1  inc     rdi
0x180075ae4  jmp     short loc_180075AB3
0x180075ae6  lea     r9, [rdi+3]
0x180075aea  mov     rax, [rbp+4Fh+var_A0]
0x180075aee  mov     r8, [rbp+4Fh+var_A8]
0x180075af2  sub     rax, r8
0x180075af5  sar     rax, 5
0x180075af9  cmp     r9, rax
0x180075afc  jnb     short loc_180075B2A
0x180075afe  shl     r9, 5
0x180075b02  add     r9, r8
0x180075b05  lea     rdx, [rbp+4Fh+var_B8]
0x180075b09  lea     rcx, [rbp+4Fh+var_A8]
0x180075b0d  call    ?erase@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@0@Z; std::vector<std::wstring>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>)
0x180075b12  mov     rbx, [rbp+4Fh+var_A8]
0x180075b16  xorps   xmm0, xmm0
0x180075b19  movdqu  xmmword ptr [rbp+4Fh+var_B8], xmm0
0x180075b1e  cmp     qword ptr [rbx+18h], 7
0x180075b23  jbe     short loc_180075B67
0x180075b25  mov     rdx, [rbx]
0x180075b28  jmp     short loc_180075B6A
0x180075b2a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180075b2f  mov     ebx, 8000FFFFh
0x180075b34  mov     [rsp+100h+var_E0], ebx; int
0x180075b38  lea     r9, aCspnodeindexIn; "cspNodeIndex index out of bounds"
0x180075b3f  lea     r8, word_180142E98; unsigned __int16 *
0x180075b46  lea     rdx, aDeclaredconfig_144; "DeclaredConfigurationStore_GetOutOfBoxM"...
0x180075b4d  mov     rcx, rax; this
0x180075b50  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180075b55  mov     rcx, [rbp+57h]; this
0x180075b59  mov     r9d, ebx; char *
0x180075b5c  mov     edx, 6D32h; void *
0x180075b61  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075b67  mov     rdx, rbx
0x180075b6a  lea     r9, [rbp+4Fh+var_B8]
0x180075b6e  xor     r8d, r8d
0x180075b71  mov     rcx, r14
0x180075b74  call    ?GetChildNodeByName@CspSchema@@QEAAJPEBG_NPEAV?$shared_ptr@VNodeSchema@@@std@@@Z; CspSchema::GetChildNodeByName(ushort const *,bool,std::shared_ptr<NodeSchema> *)
0x180075b79  test    eax, eax
0x180075b7b  jns     short loc_180075B8F
0x180075b7d  mov     rcx, [rbp+4Fh+var_B8+8]
0x180075b81  test    rcx, rcx
0x180075b84  jz      loc_180075C16
0x180075b8a  jmp     loc_180075C10
0x180075b8f  mov     rdi, [rbp+4Fh+var_B8+8]
0x180075b93  mov     r14, [rbp+4Fh+var_B8]
0x180075b97  add     rbx, 20h ; ' '
0x180075b9b  cmp     rbx, [rbp+4Fh+var_A0]
0x180075b9f  jz      loc_180075C52
0x180075ba5  xorps   xmm0, xmm0
0x180075ba8  movdqu  xmmword ptr [rsp+100h+pvarg], xmm0
0x180075bae  mov     r13, r14
0x180075bb1  cmp     qword ptr [rbx+18h], 7
0x180075bb6  jbe     short loc_180075BBD
0x180075bb8  mov     rdx, [rbx]
0x180075bbb  jmp     short loc_180075BC0
0x180075bbd  mov     rdx, rbx
0x180075bc0  lea     r8, [rsp+100h+pvarg]
0x180075bc5  mov     rcx, r13
0x180075bc8  call    ?GetChildNodeByName@NodeSchema@@QEAAJPEBGPEAV?$shared_ptr@VNodeSchema@@@std@@@Z; NodeSchema::GetChildNodeByName(ushort const *,std::shared_ptr<NodeSchema> *)
0x180075bcd  test    eax, eax
0x180075bcf  js      short loc_180075BF9
0x180075bd1  mov     r14, qword ptr [rsp+100h+pvarg]
0x180075bd6  mov     [rbp+4Fh+var_B8], r14
0x180075bda  mov     qword ptr [rsp+100h+pvarg], r13
0x180075bdf  mov     rcx, rdi; this
0x180075be2  mov     rdi, qword ptr [rbp+4Fh+pvarg+8]
0x180075be6  mov     [rbp+4Fh+var_B8+8], rdi
0x180075bea  xor     r13d, r13d
0x180075bed  test    rcx, rcx
0x180075bf0  jz      short loc_180075B97
0x180075bf2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180075bf7  jmp     short loc_180075B97
0x180075bf9  mov     rcx, qword ptr [rbp+4Fh+pvarg+8]; this
0x180075bfd  test    rcx, rcx
0x180075c00  jz      short loc_180075C08
0x180075c02  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180075c07  nop
0x180075c08  test    rdi, rdi
0x180075c0b  jz      short loc_180075C16
0x180075c0d  mov     rcx, rdi; this
0x180075c10  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180075c15  nop
0x180075c16  lea     rcx, [rbp+4Fh+var_68]
0x180075c1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075c1f  nop
0x180075c20  lea     rcx, [rbp+4Fh+var_A8]
0x180075c24  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180075c29  nop
0x180075c2a  mov     rcx, rsi
0x180075c2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075c32  mov     rcx, [rbp+4Fh+var_48]
0x180075c36  xor     rcx, rsp; StackCookie
0x180075c39  call    __security_check_cookie
0x180075c3e  add     rsp, 0C8h
0x180075c45  pop     r15
0x180075c47  pop     r14
0x180075c49  pop     r13
0x180075c4b  pop     r12
0x180075c4d  pop     rdi
0x180075c4e  pop     rsi
0x180075c4f  pop     rbx
0x180075c50  pop     rbp
0x180075c51  retn
0x180075c52  lea     rcx, [rsp+100h+pvarg]; pvarg
0x180075c57  call    cs:__imp_VariantInit
0x180075c5d  nop
0x180075c5e  lea     r8, [rsp+100h+pvarg]; struct tagVARIANT *
0x180075c63  lea     rdx, aMergerule; "mergeRule"
0x180075c6a  mov     rcx, r14; this
0x180075c6d  call    ?CheckNodeProperty@NodeSchema@@QEAAJPEBGPEAUtagVARIANT@@@Z; NodeSchema::CheckNodeProperty(ushort const *,tagVARIANT *)
0x180075c72  mov     ebx, eax
0x180075c74  cmp     eax, 80070002h
0x180075c79  jnz     short loc_180075C81
0x180075c7b  mov     [r12], r13d
0x180075c7f  jmp     short loc_180075CDC
0x180075c81  test    ebx, ebx
0x180075c83  jns     short loc_180075CBD
0x180075c85  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180075c8a  mov     [rsp+100h+var_E0], ebx; int
0x180075c8e  lea     r9, aChecknodeprope; "CheckNodeProperty failed"
0x180075c95  lea     r8, word_180142E98; unsigned __int16 *
0x180075c9c  lea     rdx, aDeclaredconfig_144; "DeclaredConfigurationStore_GetOutOfBoxM"...
0x180075ca3  mov     rcx, rax; this
0x180075ca6  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180075cab  mov     rcx, [rbp+57h]; this
0x180075caf  mov     r9d, ebx; char *
0x180075cb2  mov     edx, 6D64h; void *
0x180075cb7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075cbd  cmp     word ptr [rsp+100h+pvarg], 3
0x180075cc3  jnz     loc_180075E5F
0x180075cc9  mov     eax, dword ptr [rbp+4Fh+pvarg+8]
0x180075ccc  mov     [r12], eax
0x180075cd0  cmp     eax, 7
0x180075cd3  jnb     short loc_180075CEC
0x180075cd5  mov     dword ptr [r15], 1
0x180075cdc  lea     rcx, [rsp+100h+pvarg]; pvarg
0x180075ce1  call    cs:__imp_VariantClear
0x180075ce7  jmp     loc_180075C08
0x180075cec  jnz     loc_180075D8A
0x180075cf2  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x180075cf6  call    cs:__imp_VariantInit
0x180075cfc  nop
0x180075cfd  lea     r8, [rbp+4Fh+var_90]; struct tagVARIANT *
0x180075d01  lea     rdx, aDelimiter; "delimiter"
0x180075d08  mov     rcx, r14; this
0x180075d0b  call    ?CheckNodeProperty@NodeSchema@@QEAAJPEBGPEAUtagVARIANT@@@Z; NodeSchema::CheckNodeProperty(ushort const *,tagVARIANT *)
0x180075d10  mov     ebx, eax
0x180075d12  test    eax, eax
0x180075d14  jns     short loc_180075D4E
0x180075d16  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180075d1b  mov     [rsp+100h+var_E0], ebx; int
0x180075d1f  lea     r9, aChecknodeprope; "CheckNodeProperty failed"
0x180075d26  lea     r8, word_180142E98; unsigned __int16 *
0x180075d2d  lea     rdx, aDeclaredconfig_144; "DeclaredConfigurationStore_GetOutOfBoxM"...
0x180075d34  mov     rcx, rax; this
0x180075d37  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180075d3c  mov     rcx, [rbp+57h]; this
0x180075d40  mov     r9d, ebx; char *
0x180075d43  mov     edx, 6D7Ch; void *
0x180075d48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075d4e  mov     ebx, 8
0x180075d53  cmp     word ptr [rbp+4Fh+var_90], bx
0x180075d57  jnz     short loc_180075D7B
0x180075d59  mov     rdx, qword ptr [rbp+4Fh+var_90+8]
0x180075d5d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180075d61  inc     r8
0x180075d64  cmp     [rdx+r8*2], r13w
0x180075d69  jnz     short loc_180075D61
0x180075d6b  mov     rcx, [rbp+4Fh+var_78]
0x180075d6f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180075d74  mov     dword ptr [r15], 1
0x180075d7b  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x180075d7f  call    cs:__imp_VariantClear
0x180075d85  jmp     loc_180075CDC
0x180075d8a  mov     ebx, 8
0x180075d8f  cmp     eax, ebx
0x180075d91  jnz     loc_180075E22
0x180075d97  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x180075d9b  call    cs:__imp_VariantInit
0x180075da1  nop
0x180075da2  lea     r8, [rbp+4Fh+var_90]; struct tagVARIANT *
0x180075da6  lea     rdx, aAdmxpayload_0; "admxPayload"
0x180075dad  mov     rcx, r14; this
0x180075db0  call    ?CheckNodeProperty@NodeSchema@@QEAAJPEBGPEAUtagVARIANT@@@Z; NodeSchema::CheckNodeProperty(ushort const *,tagVARIANT *)
0x180075db5  mov     r14d, eax
0x180075db8  test    eax, eax
0x180075dba  jns     short loc_180075DF5
0x180075dbc  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180075dc1  mov     [rsp+100h+var_E0], r14d; int
0x180075dc6  lea     r9, aChecknodeprope; "CheckNodeProperty failed"
0x180075dcd  lea     r8, word_180142E98; unsigned __int16 *
0x180075dd4  lea     rdx, aDeclaredconfig_144; "DeclaredConfigurationStore_GetOutOfBoxM"...
0x180075ddb  mov     rcx, rax; this
0x180075dde  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180075de3  mov     rcx, [rbp+57h]; this
0x180075de7  mov     r9d, r14d; char *
0x180075dea  mov     edx, 6D91h; void *
0x180075def  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075df5  cmp     word ptr [rbp+4Fh+var_90], bx
0x180075df9  jnz     short loc_180075E1D
0x180075dfb  mov     rdx, qword ptr [rbp+4Fh+var_90+8]
0x180075dff  or      r8, 0FFFFFFFFFFFFFFFFh
0x180075e03  inc     r8
0x180075e06  cmp     [rdx+r8*2], r13w
0x180075e0b  jnz     short loc_180075E03
0x180075e0d  mov     rcx, [rbp+4Fh+var_78]
0x180075e11  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180075e16  mov     dword ptr [r15], 1
0x180075e1d  jmp     loc_180075D7B
0x180075e22  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180075e27  mov     ebx, 80070057h
0x180075e2c  mov     [rsp+100h+var_E0], ebx; int
0x180075e30  lea     r9, aInvalidMergeru; "Invalid MergeRule"
0x180075e37  lea     r8, word_180142E98; unsigned __int16 *
0x180075e3e  lea     rdx, aDeclaredconfig_144; "DeclaredConfigurationStore_GetOutOfBoxM"...
0x180075e45  mov     rcx, rax; this
0x180075e48  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180075e4d  mov     rcx, [rbp+57h]; this
0x180075e51  mov     r9d, ebx; char *
0x180075e54  mov     edx, 6DA2h; void *
0x180075e59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075e5f  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180075e64  mov     ebx, 8000FFFFh
0x180075e69  mov     [rsp+100h+var_E0], ebx; int
0x180075e6d  lea     r9, aMergeruletypeH; "mergeRuleType has unexpected variant ty"...
0x180075e74  lea     r8, word_180142E98; unsigned __int16 *
0x180075e7b  lea     rdx, aDeclaredconfig_236; "DeclaredConfigurationStore_GetInboxMerg"...
0x180075e82  mov     rcx, rax; this
0x180075e85  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180075e8a  mov     rcx, [rbp+57h]; this
0x180075e8e  mov     r9d, ebx; char *
0x180075e91  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
  ... truncated ...
```
