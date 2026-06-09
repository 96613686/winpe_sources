# CVarTypeLoader::HrHandleInnerElements(void)

- ea: `0x18015ce8c`
- end: `0x18015d57d`
- name: `?HrHandleInnerElements@CVarTypeLoader@@AEAAJXZ`
- size: `1777`
- prototype: `__int64 __fastcall(CVarTypeLoader *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18015c700`

## callees

- `0x1801420b4`
- `0x18015ce8c`
- `0x18015d580`
- `0x180760900`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18015d4e3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18015d4e3`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015cfe8`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d0b2`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d185`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d240`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d344`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d3ff`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d4c3`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d527`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015cfe8`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d0b2`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d185`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d240`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d344`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d3ff`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d4c3`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18015d527`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18015cf64`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18015cf64`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18015d112`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18015d112`
- `ole32!PropVariantClear` at `0x18015cf28`
- `ole32!PropVariantClear` at `0x18015d460`
- `ole32!PropVariantClear` at `0x18015cf28`
- `ole32!PropVariantClear` at `0x18015d460`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18015d2ea`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18015d2ea`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18015d46d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18015d571`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18015d46d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18015d571`

## string_xrefs

- `0x18015d2c2`: `Failed: ::SafeArrayUnaccessData(m_varprop.parray)`
- `0x18015d439`: `Failed: PropVariantCopyCore(((PROPVARIANT*)pData) + m_cInnerElems, pvarprop)`
- `0x18015d37e`: `Failed: ::SafeArrayAccessData(m_varprop.parray, &pData)`
- `0x18015d1bf`: `Failed: PropVariantCopyCore(&(m_varprop.capropvar.pElems[m_cInnerElems]), pvarprop)`

## pseudocode

```c
__int64 __fastcall CVarTypeLoader::HrHandleInnerElements(
        CVarTypeLoader *this,
        __int64 a2,
        __int64 a3,
        struct tagPROPVARIANT *a4)
{
  HRESULT v5; // r14d
  __int64 v6; // rcx
  const struct tagPROPVARIANT *v7; // rdx
  __int16 v8; // bx
  struct tagPROPVARIANT *v9; // rdi
  PROPVARIANT *v10; // rdi
  VARTYPE vt; // bx
  unsigned int v13; // edi
  const wchar_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned int v17; // edi
  unsigned int v18; // r15d
  void *v19; // r9
  const struct tagPROPVARIANT *v20; // rdx
  PROPVARIANT *v21; // rdi
  VARTYPE v22; // bx
  void ***v23; // [rsp+30h] [rbp-49h] BYREF
  void ***v24; // [rsp+38h] [rbp-41h]
  void ***v25; // [rsp+40h] [rbp-39h]
  void **v26; // [rsp+48h] [rbp-31h] BYREF
  void ***v27; // [rsp+50h] [rbp-29h]
  void ***v28; // [rsp+58h] [rbp-21h]
  void **v29; // [rsp+60h] [rbp-19h] BYREF
  void ***v30; // [rsp+68h] [rbp-11h]
  void ***v31; // [rsp+70h] [rbp-9h]
  void **v32; // [rsp+78h] [rbp-1h] BYREF
  const wchar_t *v33; // [rsp+80h] [rbp+7h]
  char v34; // [rsp+88h] [rbp+Fh]
  __int16 v35; // [rsp+8Ah] [rbp+11h]
  void **v36; // [rsp+90h] [rbp+17h] BYREF
  const wchar_t *v37; // [rsp+98h] [rbp+1Fh]
  char v38; // [rsp+A0h] [rbp+27h]
  __int16 v39; // [rsp+A2h] [rbp+29h]
  void *ppvData; // [rsp+E0h] [rbp+67h] BYREF
  void ****v41; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v42; // [rsp+F0h] [rbp+77h] BYREF

  v5 = 0;
  ppvData = 0;
  v6 = *((_QWORD *)this + 8);
  if ( !v6 )
  {
    CrashWithRecovery(0x1CA0DCu, 0);
    __debugbreak();
  }
  v7 = (const struct tagPROPVARIANT *)*((unsigned int *)this + 9);
  if ( (unsigned int)v7 >= *((_DWORD *)this + 10) )
  {
    v5 = -2134192109;
    v36 = &Mso::ProofingTelemetry::IsOverrideToolOption::`vftable';
    v37 = L"IsCorruption";
    v38 = 0;
    v39 = 0;
    v32 = &Mso::ProofingTelemetry::IsOverrideToolOption::`vftable';
    v33 = L"ReportCorruption";
    v34 = 0;
    v35 = 0;
    v30 = (void ***)L"SH_ErrorCode";
    LODWORD(v31) = -2134192109;
    WORD2(v31) = 0;
    v29 = &Mso::Resources::StructuredPathOrigin::`vftable';
    v13 = 1876189;
    if ( !(unsigned __int8)Mso::Logging::MsoShouldTrace(1876189, 1196, 10) )
      goto LABEL_9;
    v23 = &v29;
    v24 = &v32;
    v25 = &v36;
    v26 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v27 = (void ***)&v23;
    v28 = &v26;
    v14 = L"False: m_cInnerElems < m_cElems";
    goto LABEL_18;
  }
  v8 = *(_WORD *)this & 0xFFF;
  if ( v8 != 12 && *(_WORD *)v6 != v8 )
  {
    v5 = -2134142672;
    v32 = &Mso::ProofingTelemetry::IsOverrideToolOption::`vftable';
    v33 = L"IsCorruption";
    v34 = 1;
    v35 = 0;
    v36 = &Mso::ProofingTelemetry::IsOverrideToolOption::`vftable';
    v37 = L"ReportCorruption";
    v38 = 0;
    v39 = 0;
    v24 = (void ***)L"SH_ErrorCode";
    LODWORD(v25) = -2134142672;
    WORD2(v25) = 0;
    v23 = (void ***)&Mso::Resources::StructuredPathOrigin::`vftable';
    v13 = 1876190;
    if ( !(unsigned __int8)Mso::Logging::MsoShouldTrace(1876190, 1196, 10) )
      goto LABEL_9;
    v29 = (void **)&v23;
    v30 = &v36;
    v31 = &v32;
    v26 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v27 = &v29;
    v28 = &v32;
    v14 = L"False: vt == VT_VARIANT || m_pvtEmbLoader->GetVartype() == vt";
    goto LABEL_18;
  }
  v9 = (struct tagPROPVARIANT *)(v6 & -(__int64)(*(_DWORD *)(v6 + 24) != 0));
  if ( !v9 )
  {
    v5 = -2147418113;
    v32 = &Mso::ProofingTelemetry::IsOverrideToolOption::`vftable';
    v33 = L"IsCorruption";
    v34 = 0;
    v35 = 0;
    v36 = &Mso::ProofingTelemetry::IsOverrideToolOption::`vftable';
    v37 = L"ReportCorruption";
    v38 = 0;
    v39 = 0;
    v24 = (void ***)L"SH_ErrorCode";
    LODWORD(v25) = -2147418113;
    WORD2(v25) = 0;
    v23 = (void ***)&Mso::Resources::StructuredPathOrigin::`vftable';
    v13 = 1876191;
    if ( !(unsigned __int8)Mso::Logging::MsoShouldTrace(1876191, 1196, 10) )
      goto LABEL_9;
    v29 = (void **)&v23;
    v30 = &v36;
    v31 = &v32;
    v26 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v27 = &v29;
    v28 = &v32;
    v14 = L"False: pvarprop != nullptr";
    goto LABEL_18;
  }
  if ( (*(_WORD *)this & 0x1000) != 0 )
  {
    if ( v8 != 12 )
    {
      Mso::ComUtil::AssignVectorElement(
        (Mso::ComUtil *)(v6 & -(__int64)(*(_DWORD *)(v6 + 24) != 0)),
        v7,
        (unsigned int)this,
        a4);
      v10 = (PROPVARIANT *)*((_QWORD *)this + 8);
      vt = v10->vt;
      v10->vt = 14;
      PropVariantClear(v10);
      v10->vt = vt;
LABEL_8:
      ++*((_DWORD *)this + 9);
      goto LABEL_9;
    }
    v5 = PropVariantCopyCore((struct tagPROPVARIANT *)(*((_QWORD *)this + 2) + 24LL * (_QWORD)v7), v9);
    if ( v5 >= 0 )
      goto LABEL_8;
    v24 = (void ***)L"SH_ErrorCode";
    LODWORD(v25) = v5;
    WORD2(v25) = 0;
    v23 = (void ***)&Mso::Resources::StructuredPathOrigin::`vftable';
    v17 = 50;
    if ( v5 != -2147467260 )
      v17 = 10;
    v18 = 1876192;
    if ( !(unsigned __int8)Mso::Logging::MsoShouldTrace(1876192, 1196, v17) )
      goto LABEL_9;
    v41 = &v23;
    v26 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v27 = (void ***)&v41;
    v28 = (void ***)&v42;
    v14 = L"Failed: PropVariantCopyCore(&(m_varprop.capropvar.pElems[m_cInnerElems]), pvarprop)";
LABEL_27:
    v15 = v17;
    v16 = v18;
    goto LABEL_19;
  }
  if ( (*(_WORD *)this & 0x2000) == 0 )
  {
    MsoShipAssertTagProc(1876224);
    v5 = -2147418113;
    v24 = (void ***)L"SH_ErrorCode";
    LODWORD(v25) = -2147418113;
    WORD2(v25) = 0;
    v23 = (void ***)&Mso::Resources::StructuredPathOrigin::`vftable';
    v13 = 1876225;
    if ( !(unsigned __int8)Mso::Logging::MsoShouldTrace(1876225, 1196, 10) )
      goto LABEL_9;
    v41 = &v23;
    v26 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v27 = (void ***)&v41;
    v28 = (void ***)&v42;
    v14 = L"Failed: ((HRESULT)0x8000FFFFL)";
LABEL_18:
    v15 = 10;
    v16 = v13;
LABEL_19:
    Mso::Logging::MsoSendStructuredTraceTag(v16, 1196, v15, 0, v14, &v26);
    goto LABEL_9;
  }
  v5 = SafeArrayAccessData(*((SAFEARRAY **)this + 1), &ppvData);
  if ( v5 < 0 )
  {
    v24 = (void ***)L"SH_ErrorCode";
    LODWORD(v25) = v5;
    WORD2(v25) = 0;
    v23 = (void ***)&Mso::Resources::StructuredPathOrigin::`vftable';
    v17 = 50;
    if ( v5 != -2147467260 )
      v17 = 10;
    v18 = 1876193;
    if ( !(unsigned __int8)Mso::Logging::MsoShouldTrace(1876193, 1196, v17) )
      goto LABEL_9;
    v41 = &v23;
    v26 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v27 = (void ***)&v41;
    v28 = (void ***)&v42;
    v14 = L"Failed: ::SafeArrayAccessData(m_varprop.parray, &pData)";
    goto LABEL_27;
  }
  v20 = (const struct tagPROPVARIANT *)*((unsigned int *)this + 9);
  if ( v8 == 12 )
  {
    v5 = PropVariantCopyCore((struct tagPROPVARIANT *)ppvData + (_QWORD)v20, v9);
    if ( v5 < 0 )
    {
      v24 = (void ***)L"SH_ErrorCode";
      LODWORD(v25) = v5;
      WORD2(v25) = 0;
      v23 = (void ***)&Mso::Resources::StructuredPathOrigin::`vftable';
      v17 = 50;
      if ( v5 != -2147467260 )
        v17 = 10;
      v18 = 1876194;
      if ( !(unsigned __int8)Mso::Logging::MsoShouldTrace(1876194, 1196, v17) )
        goto LABEL_9;
      v41 = &v23;
      v26 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v27 = (void ***)&v41;
      v28 = (void ***)&v42;
      v14 = L"Failed: PropVariantCopyCore(((PROPVARIANT*)pData) + m_cInnerElems, pvarprop)";
      goto LABEL_27;
    }
  }
  else
  {
    Mso::ComUtil::AssignArrayElement((Mso::ComUtil *)v9, v20, (unsigned int)ppvData, v19);
    v21 = (PROPVARIANT *)*((_QWORD *)this + 8);
    v22 = v21->vt;
    v21->vt = 14;
    PropVariantClear(v21);
    v21->vt = v22;
  }
  v5 = SafeArrayUnaccessData(*((SAFEARRAY **)this + 1));
  if ( v5 >= 0 )
  {
    ++*((_DWORD *)this + 9);
    return (unsigned int)v5;
  }
  v24 = (void ***)L"SH_ErrorCode";
  LODWORD(v25) = v5;
  WORD2(v25) = 0;
  v23 = (void ***)&Mso::Resources::StructuredPathOrigin::`vftable';
  v17 = 50;
  if ( v5 != -2147467260 )
    v17 = 10;
  v18 = 1876195;
  if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(1876195, 1196, v17) )
  {
    v41 = &v23;
    v26 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v27 = (void ***)&v41;
    v28 = (void ***)&v42;
    v14 = L"Failed: ::SafeArrayUnaccessData(m_varprop.parray)";
    goto LABEL_27;
  }
LABEL_9:
  if ( ppvData )
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 1));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18015ce8c  mov     [rsp-8+arg_10], rbx
0x18015ce91  mov     [rsp-8+arg_18], rsi
0x18015ce96  push    rbp
0x18015ce97  push    rdi
0x18015ce98  push    r12
0x18015ce9a  push    r14
0x18015ce9c  push    r15
0x18015ce9e  lea     rbp, [rsp-37h]
0x18015cea3  sub     rsp, 0B0h
0x18015ceaa  mov     rsi, rcx
0x18015cead  xor     r12d, r12d
0x18015ceb0  mov     r14d, r12d
0x18015ceb3  mov     [rbp+57h+ppvData], r12
0x18015ceb7  mov     rcx, [rcx+40h]
0x18015cebb  test    rcx, rcx
0x18015cebe  jz      loc_18015CF5D
0x18015cec4  mov     edx, [rsi+24h]; struct tagPROPVARIANT *
0x18015cec7  cmp     edx, [rsi+28h]
0x18015ceca  jnb     loc_18015D03E
0x18015ced0  movzx   ebx, word ptr [rsi]
0x18015ced3  mov     eax, 0FFFh
0x18015ced8  and     bx, ax
0x18015cedb  cmp     bx, 0Ch
0x18015cedf  jnz     loc_18015CF6B
0x18015cee5  mov     eax, [rcx+18h]
0x18015cee8  neg     eax
0x18015ceea  sbb     rdi, rdi
0x18015ceed  and     rdi, rcx
0x18015cef0  jz      loc_18015D1CB
0x18015cef6  mov     eax, 1000h
0x18015cefb  test    [rsi], ax
0x18015cefe  jz      loc_18015D2D4
0x18015cf04  cmp     bx, 0Ch
0x18015cf08  jz      loc_18015D11D
0x18015cf0e  mov     r8, rsi; unsigned int
0x18015cf11  mov     rcx, rdi; this
0x18015cf14  call    ?AssignVectorElement@ComUtil@Mso@@YAXAEBUtagPROPVARIANT@@IAEAU3@@Z; Mso::ComUtil::AssignVectorElement(tagPROPVARIANT const &,uint,tagPROPVARIANT &)
0x18015cf19  mov     rdi, [rsi+40h]
0x18015cf1d  movzx   ebx, word ptr [rdi]
0x18015cf20  mov     word ptr [rdi], 0Eh
0x18015cf25  mov     rcx, rdi; pvar
0x18015cf28  call    cs:__imp_PropVariantClear
0x18015cf2e  mov     [rdi], bx
0x18015cf31  inc     dword ptr [rsi+24h]
0x18015cf34  cmp     [rbp+57h+ppvData], r12
0x18015cf38  jnz     loc_18015D56D
0x18015cf3e  mov     eax, r14d
0x18015cf41  lea     r11, [rsp+0D0h+var_20]
0x18015cf49  mov     rbx, [r11+40h]
0x18015cf4d  mov     rsi, [r11+48h]
0x18015cf51  mov     rsp, r11
0x18015cf54  pop     r15
0x18015cf56  pop     r14
0x18015cf58  pop     r12
0x18015cf5a  pop     rdi
0x18015cf5b  pop     rbp
0x18015cf5c  retn
0x18015cf5d  xor     edx, edx
0x18015cf5f  mov     ecx, 1CA0DCh
0x18015cf64  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18015cf6a  int     3; Trap to Debugger
0x18015cf6b  cmp     [rcx], bx
0x18015cf6e  jz      loc_18015CEE5
0x18015cf74  mov     r14d, 80CB9130h
0x18015cf7a  lea     rax, ??_7IsOverrideToolOption@ProofingTelemetry@Mso@@6B@; const Mso::ProofingTelemetry::IsOverrideToolOption::`vftable'
0x18015cf81  mov     [rbp+57h+var_58], rax
0x18015cf85  lea     rdx, aIscorruption; "IsCorruption"
0x18015cf8c  mov     [rbp+57h+var_50], rdx
0x18015cf90  mov     [rbp+57h+var_48], 1
0x18015cf94  mov     [rbp+57h+var_46], r12w
0x18015cf99  mov     [rbp+57h+var_40], rax
0x18015cf9d  lea     rax, aReportcorrupti; "ReportCorruption"
0x18015cfa4  mov     [rbp+57h+var_38], rax
0x18015cfa8  mov     [rbp+57h+var_30], r12b
0x18015cfac  mov     [rbp+57h+var_2E], r12w
0x18015cfb1  lea     rax, aShErrorcode_0; "SH_ErrorCode"
0x18015cfb8  mov     [rbp+57h+var_98], rax
0x18015cfbc  mov     dword ptr [rbp+57h+var_90], r14d
0x18015cfc0  mov     word ptr [rbp+57h+var_90+4], r12w
0x18015cfc5  lea     rax, ??_7StructuredPathOrigin@Resources@Mso@@6B@; const Mso::Resources::StructuredPathOrigin::`vftable'
0x18015cfcc  mov     [rbp+57h+var_A0], rax
0x18015cfd0  xor     r9d, r9d
0x18015cfd3  lea     r15d, [r9+0Ah]
0x18015cfd7  mov     r8d, r15d
0x18015cfda  mov     ebx, 4ACh
0x18015cfdf  mov     edx, ebx
0x18015cfe1  mov     edi, 1CA0DEh
0x18015cfe6  mov     ecx, edi
0x18015cfe8  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18015cfee  test    al, al
0x18015cff0  jz      loc_18015CF34
0x18015cff6  lea     rax, [rbp+57h+var_A0]
0x18015cffa  mov     [rbp+57h+var_70], rax
0x18015cffe  lea     rax, [rbp+57h+var_40]
0x18015d002  mov     [rbp+57h+var_68], rax
0x18015d006  lea     rax, [rbp+57h+var_58]
0x18015d00a  mov     [rbp+57h+var_60], rax
0x18015d00e  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18015d015  mov     [rbp+57h+var_88], rax
0x18015d019  lea     rax, [rbp+57h+var_70]
0x18015d01d  mov     [rbp+57h+var_80], rax
0x18015d021  lea     rax, [rbp+57h+var_58]
0x18015d025  mov     [rbp+57h+var_78], rax
0x18015d029  lea     rax, [rbp+57h+var_88]
0x18015d02d  mov     [rsp+0D0h+var_A8], rax
0x18015d032  lea     rax, aFalseVtVtVaria_0; "False: vt == VT_VARIANT || m_pvtEmbLoad"...
0x18015d039  jmp     loc_18015D103
0x18015d03e  mov     r14d, 80CAD013h
0x18015d044  lea     rax, ??_7IsOverrideToolOption@ProofingTelemetry@Mso@@6B@; const Mso::ProofingTelemetry::IsOverrideToolOption::`vftable'
0x18015d04b  mov     [rbp+57h+var_40], rax
0x18015d04f  lea     rdx, aIscorruption; "IsCorruption"
0x18015d056  mov     [rbp+57h+var_38], rdx
0x18015d05a  mov     [rbp+57h+var_30], r12b
0x18015d05e  mov     [rbp+57h+var_2E], r12w
0x18015d063  mov     [rbp+57h+var_58], rax
0x18015d067  lea     rax, aReportcorrupti; "ReportCorruption"
0x18015d06e  mov     [rbp+57h+var_50], rax
0x18015d072  mov     [rbp+57h+var_48], r12b
0x18015d076  mov     [rbp+57h+var_46], r12w
0x18015d07b  lea     rax, aShErrorcode_0; "SH_ErrorCode"
0x18015d082  mov     [rbp+57h+var_68], rax
0x18015d086  mov     dword ptr [rbp+57h+var_60], r14d
0x18015d08a  mov     word ptr [rbp+57h+var_60+4], r12w
0x18015d08f  lea     rax, ??_7StructuredPathOrigin@Resources@Mso@@6B@; const Mso::Resources::StructuredPathOrigin::`vftable'
0x18015d096  mov     [rbp+57h+var_70], rax
0x18015d09a  xor     r9d, r9d
0x18015d09d  lea     r15d, [r9+0Ah]
0x18015d0a1  mov     r8d, r15d
0x18015d0a4  mov     ebx, 4ACh
0x18015d0a9  mov     edx, ebx
0x18015d0ab  mov     edi, 1CA0DDh
0x18015d0b0  mov     ecx, edi
0x18015d0b2  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18015d0b8  test    al, al
0x18015d0ba  jz      loc_18015CF34
0x18015d0c0  lea     rax, [rbp+57h+var_70]
0x18015d0c4  mov     [rbp+57h+var_A0], rax
0x18015d0c8  lea     rax, [rbp+57h+var_58]
0x18015d0cc  mov     [rbp+57h+var_98], rax
0x18015d0d0  lea     rax, [rbp+57h+var_40]
0x18015d0d4  mov     [rbp+57h+var_90], rax
0x18015d0d8  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18015d0df  mov     [rbp+57h+var_88], rax
0x18015d0e3  lea     rax, [rbp+57h+var_A0]
0x18015d0e7  mov     [rbp+57h+var_80], rax
0x18015d0eb  lea     rax, [rbp+57h+var_88]
0x18015d0ef  mov     [rbp+57h+var_78], rax
0x18015d0f3  lea     rax, [rbp+57h+var_88]
0x18015d0f7  mov     [rsp+0D0h+var_A8], rax
0x18015d0fc  lea     rax, aFalseMCinnerel; "False: m_cInnerElems < m_cElems"
0x18015d103  mov     r8d, r15d
0x18015d106  mov     ecx, edi
0x18015d108  mov     [rsp+0D0h+var_B0], rax
0x18015d10d  xor     r9d, r9d
0x18015d110  mov     edx, ebx
0x18015d112  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x18015d118  jmp     loc_18015CF34
0x18015d11d  lea     rcx, [rdx+rdx*2]
0x18015d121  mov     rax, [rsi+10h]
0x18015d125  lea     rcx, [rax+rcx*8]; struct tagPROPVARIANT *
0x18015d129  mov     rdx, rdi; struct tagPROPVARIANT *
0x18015d12c  call    ?PropVariantCopyCore@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; PropVariantCopyCore(tagPROPVARIANT *,tagPROPVARIANT const *)
0x18015d131  mov     r14d, eax
0x18015d134  test    eax, eax
0x18015d136  jns     loc_18015CF31
0x18015d13c  lea     rax, aShErrorcode_0; "SH_ErrorCode"
0x18015d143  mov     [rbp+57h+var_98], rax
0x18015d147  mov     dword ptr [rbp+57h+var_90], r14d
0x18015d14b  mov     word ptr [rbp+57h+var_90+4], r12w
0x18015d150  lea     rax, ??_7StructuredPathOrigin@Resources@Mso@@6B@; const Mso::Resources::StructuredPathOrigin::`vftable'
0x18015d157  mov     [rbp+57h+var_A0], rax
0x18015d15b  mov     edi, 32h ; '2'
0x18015d160  lea     r15d, [rdi-28h]
0x18015d164  cmp     r14d, 80004004h
0x18015d16b  cmovnz  edi, r15d
0x18015d16f  xor     r9d, r9d
0x18015d172  mov     r8d, edi
0x18015d175  mov     ebx, 4ACh
0x18015d17a  mov     edx, ebx
0x18015d17c  mov     r15d, 1CA0E0h
0x18015d182  mov     ecx, r15d
0x18015d185  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18015d18b  test    al, al
0x18015d18d  jz      loc_18015CF34
0x18015d193  lea     rax, [rbp+57h+var_A0]
0x18015d197  mov     [rbp+57h+arg_8], rax
0x18015d19b  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18015d1a2  mov     [rbp+57h+var_88], rax
0x18015d1a6  lea     rax, [rbp+57h+arg_8]
0x18015d1aa  mov     [rbp+57h+var_80], rax
0x18015d1ae  lea     rax, [rbp+57h+arg_10]
0x18015d1b2  mov     [rbp+57h+var_78], rax
0x18015d1b6  lea     rax, [rbp+57h+var_88]
0x18015d1ba  mov     [rsp+0D0h+var_A8], rax
0x18015d1bf  lea     rax, aFailedPropvari_7; "Failed: PropVariantCopyCore(&(m_varprop"...
0x18015d1c6  jmp     loc_18015D2C9
0x18015d1cb  mov     ecx, 8000FFFFh
0x18015d1d0  mov     r14d, ecx
0x18015d1d3  lea     rax, ??_7IsOverrideToolOption@ProofingTelemetry@Mso@@6B@; const Mso::ProofingTelemetry::IsOverrideToolOption::`vftable'
0x18015d1da  mov     [rbp+57h+var_58], rax
0x18015d1de  lea     rdx, aIscorruption; "IsCorruption"
0x18015d1e5  mov     [rbp+57h+var_50], rdx
0x18015d1e9  mov     [rbp+57h+var_48], r12b
0x18015d1ed  mov     [rbp+57h+var_46], r12w
0x18015d1f2  mov     [rbp+57h+var_40], rax
0x18015d1f6  lea     rax, aReportcorrupti; "ReportCorruption"
0x18015d1fd  mov     [rbp+57h+var_38], rax
0x18015d201  mov     [rbp+57h+var_30], r12b
0x18015d205  mov     [rbp+57h+var_2E], r12w
0x18015d20a  lea     rax, aShErrorcode_0; "SH_ErrorCode"
0x18015d211  mov     [rbp+57h+var_98], rax
0x18015d215  mov     dword ptr [rbp+57h+var_90], ecx
0x18015d218  mov     word ptr [rbp+57h+var_90+4], r12w
0x18015d21d  lea     rax, ??_7StructuredPathOrigin@Resources@Mso@@6B@; const Mso::Resources::StructuredPathOrigin::`vftable'
0x18015d224  mov     [rbp+57h+var_A0], rax
0x18015d228  xor     r9d, r9d
0x18015d22b  lea     r15d, [r9+0Ah]
0x18015d22f  mov     r8d, r15d
0x18015d232  mov     ebx, 4ACh
0x18015d237  mov     edx, ebx
0x18015d239  mov     edi, 1CA0DFh
0x18015d23e  mov     ecx, edi
0x18015d240  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18015d246  test    al, al
0x18015d248  jz      loc_18015CF34
0x18015d24e  lea     rax, [rbp+57h+var_A0]
0x18015d252  mov     [rbp+57h+var_70], rax
0x18015d256  lea     rax, [rbp+57h+var_40]
0x18015d25a  mov     [rbp+57h+var_68], rax
0x18015d25e  lea     rax, [rbp+57h+var_58]
0x18015d262  mov     [rbp+57h+var_60], rax
0x18015d266  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18015d26d  mov     [rbp+57h+var_88], rax
0x18015d271  lea     rax, [rbp+57h+var_70]
0x18015d275  mov     [rbp+57h+var_80], rax
0x18015d279  lea     rax, [rbp+57h+var_58]
0x18015d27d  mov     [rbp+57h+var_78], rax
0x18015d281  lea     rax, [rbp+57h+var_88]
0x18015d285  mov     [rsp+0D0h+var_A8], rax
0x18015d28a  lea     rax, aFalsePvarpropN_0; "False: pvarprop != nullptr"
0x18015d291  jmp     loc_18015D103
0x18015d296  lea     rax, [rbp+57h+var_A0]
0x18015d29a  mov     [rbp+57h+arg_8], rax
0x18015d29e  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18015d2a5  mov     [rbp+57h+var_88], rax
0x18015d2a9  lea     rax, [rbp+57h+arg_8]
0x18015d2ad  mov     [rbp+57h+var_80], rax
0x18015d2b1  lea     rax, [rbp+57h+arg_10]
0x18015d2b5  mov     [rbp+57h+var_78], rax
0x18015d2b9  lea     rax, [rbp+57h+var_88]
0x18015d2bd  mov     [rsp+0D0h+var_A8], rax
0x18015d2c2  lea     rax, aFailedSafearra_11; "Failed: ::SafeArrayUnaccessData(m_varpr"...
0x18015d2c9  mov     r8d, edi
0x18015d2cc  mov     ecx, r15d
0x18015d2cf  jmp     loc_18015D108
0x18015d2d4  mov     eax, 2000h
0x18015d2d9  test    [rsi], ax
0x18015d2dc  jz      loc_18015D4DE
0x18015d2e2  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18015d2e6  mov     rcx, [rsi+8]; psa
0x18015d2ea  call    cs:__imp_SafeArrayAccessData
0x18015d2f0  mov     r14d, eax
0x18015d2f3  test    eax, eax
0x18015d2f5  jns     loc_18015D38A
0x18015d2fb  lea     rax, aShErrorcode_0; "SH_ErrorCode"
0x18015d302  mov     [rbp+57h+var_98], rax
0x18015d306  mov     dword ptr [rbp+57h+var_90], r14d
0x18015d30a  mov     word ptr [rbp+57h+var_90+4], r12w
0x18015d30f  lea     rax, ??_7StructuredPathOrigin@Resources@Mso@@6B@; const Mso::Resources::StructuredPathOrigin::`vftable'
0x18015d316  mov     [rbp+57h+var_A0], rax
0x18015d31a  mov     edi, 32h ; '2'
0x18015d31f  lea     r15d, [rdi-28h]
0x18015d323  cmp     r14d, 80004004h
0x18015d32a  cmovnz  edi, r15d
0x18015d32e  xor     r9d, r9d
0x18015d331  mov     r8d, edi
0x18015d334  mov     ebx, 4ACh
0x18015d339  mov     edx, ebx
0x18015d33b  mov     r15d, 1CA0E1h
0x18015d341  mov     ecx, r15d
0x18015d344  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18015d34a  test    al, al
0x18015d34c  jz      loc_18015CF34
0x18015d352  lea     rax, [rbp+57h+var_A0]
0x18015d356  mov     [rbp+57h+arg_8], rax
0x18015d35a  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18015d361  mov     [rbp+57h+var_88], rax
0x18015d365  lea     rax, [rbp+57h+arg_8]
0x18015d369  mov     [rbp+57h+var_80], rax
0x18015d36d  lea     rax, [rbp+57h+arg_10]
0x18015d371  mov     [rbp+57h+var_78], rax
0x18015d375  lea     rax, [rbp+57h+var_88]
0x18015d379  mov     [rsp+0D0h+var_A8], rax
0x18015d37e  lea     rax, aFailedSafearra; "Failed: ::SafeArrayAccessData(m_varprop"...
0x18015d385  jmp     loc_18015D2C9
0x18015d38a  mov     edx, [rsi+24h]; struct tagPROPVARIANT *
0x18015d38d  cmp     bx, 0Ch
0x18015d391  jnz     loc_18015D445
0x18015d397  lea     rcx, [rdx+rdx*2]
0x18015d39b  mov     rax, [rbp+57h+ppvData]
  ... truncated ...
```
