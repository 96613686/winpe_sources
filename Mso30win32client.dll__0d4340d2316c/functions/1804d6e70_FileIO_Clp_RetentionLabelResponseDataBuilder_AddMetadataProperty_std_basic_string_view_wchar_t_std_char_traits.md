# FileIO::Clp::RetentionLabelResponseDataBuilder::AddMetadataProperty(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1804d6e70`
- end: `0x1804d7b0a`
- name: `?AddMetadataProperty@RetentionLabelResponseDataBuilder@Clp@FileIO@@UEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z`
- size: `3226`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1804d6ce0`

## callees

- `0x18001cff0`
- `0x180021a90`
- `0x180036740`
- `0x18003afb0`
- `0x18003b330`
- `0x18008438a`
- `0x180192520`
- `0x1804d6e70`
- `0x1804d7b0c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804d75ad`
- `KERNEL32!GetLastError` at `0x1804d7646`
- `KERNEL32!GetLastError` at `0x1804d76d7`
- `KERNEL32!GetLastError` at `0x1804d7770`
- `KERNEL32!GetLastError` at `0x1804d7801`
- `KERNEL32!GetLastError` at `0x1804d789a`
- `KERNEL32!GetLastError` at `0x1804d792b`
- `KERNEL32!GetLastError` at `0x1804d79c4`
- `KERNEL32!GetLastError` at `0x1804d7a55`
- `KERNEL32!GetLastError` at `0x1804d75ad`
- `KERNEL32!GetLastError` at `0x1804d7646`
- `KERNEL32!GetLastError` at `0x1804d76d7`
- `KERNEL32!GetLastError` at `0x1804d7770`
- `KERNEL32!GetLastError` at `0x1804d7801`
- `KERNEL32!GetLastError` at `0x1804d789a`
- `KERNEL32!GetLastError` at `0x1804d792b`
- `KERNEL32!GetLastError` at `0x1804d79c4`
- `KERNEL32!GetLastError` at `0x1804d7a55`
- `KERNEL32!CompareStringEx` at `0x1804d6f45`
- `KERNEL32!CompareStringEx` at `0x1804d6fef`
- `KERNEL32!CompareStringEx` at `0x1804d7094`
- `KERNEL32!CompareStringEx` at `0x1804d7139`
- `KERNEL32!CompareStringEx` at `0x1804d71dd`
- `KERNEL32!CompareStringEx` at `0x1804d725b`
- `KERNEL32!CompareStringEx` at `0x1804d734c`
- `KERNEL32!CompareStringEx` at `0x1804d7496`
- `KERNEL32!CompareStringEx` at `0x1804d7529`
- `KERNEL32!CompareStringEx` at `0x1804d759f`
- `KERNEL32!CompareStringEx` at `0x1804d7638`
- `KERNEL32!CompareStringEx` at `0x1804d76c6`
- `KERNEL32!CompareStringEx` at `0x1804d7762`
- `KERNEL32!CompareStringEx` at `0x1804d77f0`
- `KERNEL32!CompareStringEx` at `0x1804d788c`
- `KERNEL32!CompareStringEx` at `0x1804d791a`
- `KERNEL32!CompareStringEx` at `0x1804d79b6`
- `KERNEL32!CompareStringEx` at `0x1804d7a44`
- `KERNEL32!CompareStringEx` at `0x1804d6f45`
- `KERNEL32!CompareStringEx` at `0x1804d6fef`
- `KERNEL32!CompareStringEx` at `0x1804d7094`
- `KERNEL32!CompareStringEx` at `0x1804d7139`
- `KERNEL32!CompareStringEx` at `0x1804d71dd`
- `KERNEL32!CompareStringEx` at `0x1804d725b`
- `KERNEL32!CompareStringEx` at `0x1804d734c`
- `KERNEL32!CompareStringEx` at `0x1804d7496`
- `KERNEL32!CompareStringEx` at `0x1804d7529`
- `KERNEL32!CompareStringEx` at `0x1804d759f`
- `KERNEL32!CompareStringEx` at `0x1804d7638`
- `KERNEL32!CompareStringEx` at `0x1804d76c6`
- `KERNEL32!CompareStringEx` at `0x1804d7762`
- `KERNEL32!CompareStringEx` at `0x1804d77f0`
- `KERNEL32!CompareStringEx` at `0x1804d788c`
- `KERNEL32!CompareStringEx` at `0x1804d791a`
- `KERNEL32!CompareStringEx` at `0x1804d79b6`
- `KERNEL32!CompareStringEx` at `0x1804d7a44`

## string_xrefs

- `0x1804d6f79`: `isContentReadOnly`
- `0x1804d6f94`: `isContentReadOnly`
- `0x1804d6fd1`: `isContentReadOnly`
- `0x1804d761b`: `isContentReadOnly`
- `0x1804d7ab1`: `isContentReadOnly`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
FileIO::Clp::RetentionLabelResponseDataBuilder *__fastcall FileIO::Clp::RetentionLabelResponseDataBuilder::AddMetadataProperty(
        FileIO::Clp::RetentionLabelResponseDataBuilder *a1,
        __int64 a2,
        void **a3)
{
  const WCHAR *v4; // rsi
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r15
  int cchCount2; // ebx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // r15
  int v14; // ebx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned __int64 v18; // r14
  unsigned __int64 v19; // r15
  int v20; // ebx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // r15
  int v26; // ebx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned __int64 v30; // r14
  unsigned __int64 v31; // r15
  int v32; // ebx
  int v33; // eax
  int v34; // eax
  int v35; // eax
  const WCHAR *v36; // r14
  int v37; // ebx
  int v38; // eax
  int v39; // eax
  bool v40; // bl
  FileIO::Clp::RetentionLabelResponseDataBuilder *v41; // rdi
  const WCHAR *v43; // r14
  int v44; // ebx
  int v45; // eax
  int v46; // eax
  bool v47; // bl
  struct FileIO::Clp::RetentionLabelData *v48; // rax
  const WCHAR *v49; // r14
  int v50; // ebx
  int v51; // eax
  int v52; // eax
  bool v53; // bl
  const WCHAR *v54; // r14
  int v55; // ebx
  int v56; // eax
  int v57; // eax
  bool v58; // bl
  int v59; // ebx
  int v60; // eax
  int v61; // ebx
  int v62; // eax
  int v63; // ebx
  int v64; // eax
  int v65; // ebx
  int v66; // eax
  int v67; // ebx
  int v68; // eax
  int v69; // ebx
  int v70; // eax
  int v71; // ebx
  int v72; // eax
  int v73; // ebx
  int v74; // eax
  int v75; // ebx
  int v76; // eax
  FileIO::Clp::RetentionLabelResponseDataBuilder *v77; // [rsp+50h] [rbp-B0h]
  const char *v78; // [rsp+58h] [rbp-A8h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v80; // [rsp+64h] [rbp-9Ch]
  DWORD LastError; // [rsp+264h] [rbp+164h]
  __int16 v82; // [rsp+268h] [rbp+168h]
  __int16 v83; // [rsp+368h] [rbp+268h]
  int v84; // [rsp+3E8h] [rbp+2E8h]
  _QWORD v85[3]; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int16 v86; // [rsp+408h] [rbp+308h]
  _OWORD v87[2]; // [rsp+410h] [rbp+310h] BYREF

  v77 = a1;
  if ( !*(_QWORD *)(a2 + 8) )
  {
    v78 = "RetentionLabelResponseDataBuilder::AddMetadataProperty is ignoring property with empty key";
    Mso::Diagnostics::SendDiagnosticTrace<>(508351324, 2213, 15, 2, (__int64)&v78);
    return v77;
  }
  v4 = *(const WCHAR **)a2;
  v5 = -1;
  if ( *(_QWORD *)a2 && *v4 )
  {
    if ( !aRetentionlabel_2[0] )
      goto LABEL_12;
    v6 = -1;
    do
      ++v6;
    while ( v4[v6] );
    v7 = -1;
    do
      ++v7;
    while ( aRetentionlabel_2[v7] );
    cchCount2 = OcfxInt32FromSize_t(v7);
    v9 = OcfxInt32FromSize_t(v6);
    v10 = CompareStringEx(&WindowName, 1u, v4, v9, aRetentionlabel_2, cchCount2, 0, 0, 0);
    if ( !v10 )
    {
      v59 = OcfxInt32FromSize_t(v7);
      v60 = OcfxInt32FromSize_t(v6);
      v10 = CompareStringEx(L"en-US", 1u, v4, v60, aRetentionlabel_2, v59, 0, 0, 0);
      if ( !v10 )
      {
        pExceptionObject = 15;
        LastError = GetLastError();
        v84 = 808464432;
        v83 = 0;
        v82 = 0;
        v80 = 0;
        throw (OException *)&pExceptionObject;
      }
    }
    v11 = v10 - 2;
    a1 = v77;
  }
  else
  {
    if ( aRetentionlabel_2[0] )
      goto LABEL_12;
    v11 = 0;
  }
  if ( !v11 )
  {
    v48 = FileIO::Clp::RetentionLabelResponseDataBuilder::EnsurePolicyData(a1);
    std::wstring::assign((char *)v48 + 104, *a3);
    return v77;
  }
LABEL_12:
  if ( v4 && *v4 )
  {
    if ( !aIscontentreado_0[0] )
      goto LABEL_22;
    v12 = -1;
    do
      ++v12;
    while ( v4[v12] );
    v13 = -1;
    do
      ++v13;
    while ( aIscontentreado_0[v13] );
    v14 = OcfxInt32FromSize_t(v13);
    v15 = OcfxInt32FromSize_t(v12);
    v16 = CompareStringEx(&WindowName, 1u, v4, v15, aIscontentreado_0, v14, 0, 0, 0);
    if ( !v16 )
    {
      v61 = OcfxInt32FromSize_t(v13);
      v62 = OcfxInt32FromSize_t(v12);
      v16 = CompareStringEx(L"en-US", 1u, v4, v62, aIscontentreado_0, v61, 0, 0, 0);
      if ( !v16 )
      {
        pExceptionObject = 15;
        LastError = GetLastError();
        v84 = 808464432;
        v83 = 0;
        v82 = 0;
        v80 = 0;
        throw (OException *)&pExceptionObject;
      }
    }
    v17 = v16 - 2;
  }
  else
  {
    if ( aIscontentreado_0[0] )
      goto LABEL_22;
    v17 = 0;
  }
  if ( !v17 )
  {
    v43 = (const WCHAR *)*a3;
    if ( *a3 && *v43 )
    {
      do
        ++v5;
      while ( v43[v5] );
      v44 = OcfxInt32FromSize_t(4u);
      v45 = OcfxInt32FromSize_t(v5);
      v46 = CompareStringEx(&WindowName, 1u, v43, v45, L"true", v44, 0, 0, 0);
      if ( !v46 )
      {
        v63 = OcfxInt32FromSize_t(4u);
        v64 = OcfxInt32FromSize_t(v5);
        v46 = CompareStringEx(L"en-US", 1u, v43, v64, L"true", v63, 0, 0, 0);
        if ( !v46 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v84 = 808464432;
          v83 = 0;
          v82 = 0;
          v80 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      LODWORD(v5) = v46 - 2;
    }
    v47 = (_DWORD)v5 == 0;
    v41 = v77;
    *((_BYTE *)FileIO::Clp::RetentionLabelResponseDataBuilder::EnsurePolicyData(v77) + 136) = v47;
    return v41;
  }
LABEL_22:
  if ( v4 && *v4 )
  {
    if ( aIsrecord_0[0] )
    {
      v18 = -1;
      do
        ++v18;
      while ( v4[v18] );
      v19 = -1;
      do
        ++v19;
      while ( aIsrecord_0[v19] );
      v20 = OcfxInt32FromSize_t(v19);
      v21 = OcfxInt32FromSize_t(v18);
      v22 = CompareStringEx(&WindowName, 1u, v4, v21, aIsrecord_0, v20, 0, 0, 0);
      if ( !v22 )
      {
        v65 = OcfxInt32FromSize_t(v19);
        v66 = OcfxInt32FromSize_t(v18);
        v22 = CompareStringEx(L"en-US", 1u, v4, v66, aIsrecord_0, v65, 0, 0, 0);
        if ( !v22 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v84 = 808464432;
          v83 = 0;
          v82 = 0;
          v80 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      v23 = v22 - 2;
LABEL_31:
      if ( !v23 )
      {
        v49 = (const WCHAR *)*a3;
        if ( *a3 && *v49 )
        {
          do
            ++v5;
          while ( v49[v5] );
          v50 = OcfxInt32FromSize_t(4u);
          v51 = OcfxInt32FromSize_t(v5);
          v52 = CompareStringEx(&WindowName, 1u, v49, v51, L"true", v50, 0, 0, 0);
          if ( !v52 )
          {
            v67 = OcfxInt32FromSize_t(4u);
            v68 = OcfxInt32FromSize_t(v5);
            v52 = CompareStringEx(L"en-US", 1u, v49, v68, L"true", v67, 0, 0, 0);
            if ( !v52 )
            {
              pExceptionObject = 15;
              LastError = GetLastError();
              v84 = 808464432;
              v83 = 0;
              v82 = 0;
              v80 = 0;
              throw (OException *)&pExceptionObject;
            }
          }
          LODWORD(v5) = v52 - 2;
        }
        v53 = (_DWORD)v5 == 0;
        v41 = v77;
        *((_BYTE *)FileIO::Clp::RetentionLabelResponseDataBuilder::EnsurePolicyData(v77) + 137) = v53;
        return v41;
      }
    }
  }
  else if ( !aIsrecord_0[0] )
  {
    v23 = 0;
    goto LABEL_31;
  }
  if ( v4 && *v4 )
  {
    if ( !aIslockedrecord_0[0] )
    {
LABEL_42:
      if ( v4 && *v4 )
      {
        if ( aIsregulatoryre_0[0] )
        {
          v30 = -1;
          do
            ++v30;
          while ( v4[v30] );
          v31 = -1;
          do
            ++v31;
          while ( aIsregulatoryre_0[v31] );
          v32 = OcfxInt32FromSize_t(v31);
          v33 = OcfxInt32FromSize_t(v30);
          v34 = CompareStringEx(&WindowName, 1u, v4, v33, aIsregulatoryre_0, v32, 0, 0, 0);
          if ( !v34 )
          {
            v73 = OcfxInt32FromSize_t(v31);
            v74 = OcfxInt32FromSize_t(v30);
            v34 = CompareStringEx(L"en-US", 1u, v4, v74, aIsregulatoryre_0, v73, 0, 0, 0);
            if ( !v34 )
            {
              pExceptionObject = 15;
              LastError = GetLastError();
              v84 = 808464432;
              v83 = 0;
              v82 = 0;
              v80 = 0;
              throw (OException *)&pExceptionObject;
            }
          }
          v35 = v34 - 2;
LABEL_51:
          if ( !v35 )
          {
            v36 = (const WCHAR *)*a3;
            if ( *a3 && *v36 )
            {
              do
                ++v5;
              while ( v36[v5] );
              v37 = OcfxInt32FromSize_t(4u);
              v38 = OcfxInt32FromSize_t(v5);
              v39 = CompareStringEx(&WindowName, 1u, v36, v38, L"true", v37, 0, 0, 0);
              if ( !v39 )
              {
                v75 = OcfxInt32FromSize_t(4u);
                v76 = OcfxInt32FromSize_t(v5);
                v39 = CompareStringEx(L"en-US", 1u, v36, v76, L"true", v75, 0, 0, 0);
                if ( !v39 )
                {
                  pExceptionObject = 15;
                  LastError = GetLastError();
                  v84 = 808464432;
                  v83 = 0;
                  v82 = 0;
                  v80 = 0;
                  throw (OException *)&pExceptionObject;
                }
              }
              LODWORD(v5) = v39 - 2;
            }
            v40 = (_DWORD)v5 == 0;
            v41 = v77;
            *((_BYTE *)FileIO::Clp::RetentionLabelResponseDataBuilder::EnsurePolicyData(v77) + 139) = v40;
            return v41;
          }
        }
      }
      else if ( !aIsregulatoryre_0[0] )
      {
        v35 = 0;
        goto LABEL_51;
      }
      v85[0] = &Mso::Authentication::Logging::Structured::Email::`vftable';
      v85[1] = "PropertyName";
      v85[2] = v4;
      v86 = 4;
      v87[0] = 0;
      v87[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v87[0]) = 0;
      v78 = "RetentionLabelResponseDataBuilder::AddMetadataProperty is ignoring unknown property.";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
        508351323,
        2213,
        15,
        2,
        (__int64)&v78,
        (__int64)v85);
      Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v87);
      return v77;
    }
    v24 = -1;
    do
      ++v24;
    while ( v4[v24] );
    v25 = -1;
    do
      ++v25;
    while ( aIslockedrecord_0[v25] );
    v26 = OcfxInt32FromSize_t(v25);
    v27 = OcfxInt32FromSize_t(v24);
    v28 = CompareStringEx(&WindowName, 1u, v4, v27, aIslockedrecord_0, v26, 0, 0, 0);
    if ( !v28 )
    {
      v69 = OcfxInt32FromSize_t(v25);
      v70 = OcfxInt32FromSize_t(v24);
      v28 = CompareStringEx(L"en-US", 1u, v4, v70, aIslockedrecord_0, v69, 0, 0, 0);
      if ( !v28 )
      {
        pExceptionObject = 15;
        LastError = GetLastError();
        v84 = 808464432;
        v83 = 0;
        v82 = 0;
        v80 = 0;
        throw (OException *)&pExceptionObject;
      }
    }
    v29 = v28 - 2;
  }
  else
  {
    if ( aIslockedrecord_0[0] )
      goto LABEL_42;
    v29 = 0;
  }
  if ( v29 )
    goto LABEL_42;
  v54 = (const WCHAR *)*a3;
  if ( *a3 && *v54 )
  {
    do
      ++v5;
    while ( v54[v5] );
    v55 = OcfxInt32FromSize_t(4u);
    v56 = OcfxInt32FromSize_t(v5);
    v57 = CompareStringEx(&WindowName, 1u, v54, v56, L"true", v55, 0, 0, 0);
    if ( !v57 )
    {
      v71 = OcfxInt32FromSize_t(4u);
      v72 = OcfxInt32FromSize_t(v5);
      v57 = CompareStringEx(L"en-US", 1u, v54, v72, L"true", v71, 0, 0, 0);
      if ( !v57 )
      {
        pExceptionObject = 15;
        LastError = GetLastError();
        v84 = 808464432;
        v83 = 0;
        v82 = 0;
        v80 = 0;
        throw (OException *)&pExceptionObject;
      }
    }
    LODWORD(v5) = v57 - 2;
  }
  v58 = (_DWORD)v5 == 0;
  v41 = v77;
  *((_BYTE *)FileIO::Clp::RetentionLabelResponseDataBuilder::EnsurePolicyData(v77) + 138) = v58;
  return v41;
}

```

## disassembly

```asm
0x1804d6e70  mov     [rsp-8+arg_18], rbx
0x1804d6e75  push    rbp
0x1804d6e76  push    rsi
0x1804d6e77  push    rdi
0x1804d6e78  push    r12
0x1804d6e7a  push    r13
0x1804d6e7c  push    r14
0x1804d6e7e  push    r15
0x1804d6e80  lea     rbp, [rsp-340h]
0x1804d6e88  sub     rsp, 440h
0x1804d6e8f  mov     rax, cs:__security_cookie
0x1804d6e96  xor     rax, rsp
0x1804d6e99  mov     [rbp+370h+var_40], rax
0x1804d6ea0  mov     r13, r8
0x1804d6ea3  mov     [rsp+470h+var_420], rcx
0x1804d6ea8  xor     r15d, r15d
0x1804d6eab  cmp     [rdx+8], r15
0x1804d6eaf  jz      loc_1804D7289
0x1804d6eb5  mov     rsi, [rdx]
0x1804d6eb8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1804d6ebc  test    rsi, rsi
0x1804d6ebf  jz      loc_1804D7A9B
0x1804d6ec5  cmp     r15w, [rsi]
0x1804d6ec9  jz      loc_1804D7A9B
0x1804d6ecf  cmp     r15w, word ptr cs:aRetentionlabel_2; "retentionLabelName"
0x1804d6ed7  jz      loc_1804D6F66
0x1804d6edd  mov     r14, rdi
0x1804d6ee0  inc     r14
0x1804d6ee3  cmp     [rsi+r14*2], r15w
0x1804d6ee8  jnz     short loc_1804D6EE0
0x1804d6eea  lea     rax, aRetentionlabel_2; "retentionLabelName"
0x1804d6ef1  mov     r15, rdi
0x1804d6ef4  xor     ecx, ecx
0x1804d6ef6  inc     r15
0x1804d6ef9  cmp     [rax+r15*2], cx
0x1804d6efe  jnz     short loc_1804D6EF6
0x1804d6f00  mov     rcx, r15; unsigned __int64
0x1804d6f03  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d6f08  mov     ebx, eax
0x1804d6f0a  mov     rcx, r14; unsigned __int64
0x1804d6f0d  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d6f12  xor     ecx, ecx
0x1804d6f14  mov     [rsp+470h+lParam], rcx; lParam
0x1804d6f19  mov     [rsp+470h+lpReserved], rcx; lpReserved
0x1804d6f1e  mov     [rsp+470h+lpVersionInformation], rcx; lpVersionInformation
0x1804d6f23  mov     [rsp+470h+cchCount2], ebx; cchCount2
0x1804d6f27  lea     rcx, aRetentionlabel_2; "retentionLabelName"
0x1804d6f2e  mov     [rsp+470h+lpString2], rcx; lpString2
0x1804d6f33  mov     r9d, eax; cchCount1
0x1804d6f36  mov     r8, rsi; lpString1
0x1804d6f39  mov     edx, 1; dwCmpFlags
0x1804d6f3e  lea     rcx, WindowName; lpLocaleName
0x1804d6f45  call    cs:__imp_CompareStringEx
0x1804d6f4b  test    eax, eax
0x1804d6f4d  jz      loc_1804D755A
0x1804d6f53  xor     r15d, r15d
0x1804d6f56  add     eax, 0FFFFFFFEh
0x1804d6f59  mov     rcx, [rsp+470h+var_420]; this
0x1804d6f5e  test    eax, eax
0x1804d6f60  jz      loc_1804D7418
0x1804d6f66  test    rsi, rsi
0x1804d6f69  jz      loc_1804D7AB1
0x1804d6f6f  cmp     r15w, [rsi]
0x1804d6f73  jz      loc_1804D7AB1
0x1804d6f79  cmp     r15w, word ptr cs:aIscontentreado_0; "isContentReadOnly"
0x1804d6f81  jz      loc_1804D700B
0x1804d6f87  mov     r14, rdi
0x1804d6f8a  inc     r14
0x1804d6f8d  cmp     [rsi+r14*2], r15w
0x1804d6f92  jnz     short loc_1804D6F8A
0x1804d6f94  lea     rax, aIscontentreado_0; "isContentReadOnly"
0x1804d6f9b  mov     r15, rdi
0x1804d6f9e  xor     ecx, ecx
0x1804d6fa0  inc     r15
0x1804d6fa3  cmp     [rax+r15*2], cx
0x1804d6fa8  jnz     short loc_1804D6FA0
0x1804d6faa  mov     rcx, r15; unsigned __int64
0x1804d6fad  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d6fb2  mov     ebx, eax
0x1804d6fb4  mov     rcx, r14; unsigned __int64
0x1804d6fb7  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d6fbc  xor     ecx, ecx
0x1804d6fbe  mov     [rsp+470h+lParam], rcx; lParam
0x1804d6fc3  mov     [rsp+470h+lpReserved], rcx; lpReserved
0x1804d6fc8  mov     [rsp+470h+lpVersionInformation], rcx; lpVersionInformation
0x1804d6fcd  mov     [rsp+470h+cchCount2], ebx; cchCount2
0x1804d6fd1  lea     rcx, aIscontentreado_0; "isContentReadOnly"
0x1804d6fd8  mov     [rsp+470h+lpString2], rcx; lpString2
0x1804d6fdd  mov     r9d, eax; cchCount1
0x1804d6fe0  mov     r8, rsi; lpString1
0x1804d6fe3  mov     edx, 1; dwCmpFlags
0x1804d6fe8  lea     rcx, WindowName; lpLocaleName
0x1804d6fef  call    cs:__imp_CompareStringEx
0x1804d6ff5  test    eax, eax
0x1804d6ff7  jz      loc_1804D75F3
0x1804d6ffd  xor     r15d, r15d
0x1804d7000  add     eax, 0FFFFFFFEh
0x1804d7003  test    eax, eax
0x1804d7005  jz      loc_1804D72EA
0x1804d700b  test    rsi, rsi
0x1804d700e  jz      loc_1804D7AC7
0x1804d7014  cmp     r15w, [rsi]
0x1804d7018  jz      loc_1804D7AC7
0x1804d701e  cmp     r15w, word ptr cs:aIsrecord_0; "isRecord"
0x1804d7026  jz      loc_1804D70B0
0x1804d702c  mov     r14, rdi
0x1804d702f  inc     r14
0x1804d7032  cmp     [rsi+r14*2], r15w
0x1804d7037  jnz     short loc_1804D702F
0x1804d7039  lea     rax, aIsrecord_0; "isRecord"
0x1804d7040  mov     r15, rdi
0x1804d7043  xor     ecx, ecx
0x1804d7045  inc     r15
0x1804d7048  cmp     [rax+r15*2], cx
0x1804d704d  jnz     short loc_1804D7045
0x1804d704f  mov     rcx, r15; unsigned __int64
0x1804d7052  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d7057  mov     ebx, eax
0x1804d7059  mov     rcx, r14; unsigned __int64
0x1804d705c  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d7061  xor     ecx, ecx
0x1804d7063  mov     [rsp+470h+lParam], rcx; lParam
0x1804d7068  mov     [rsp+470h+lpReserved], rcx; lpReserved
0x1804d706d  mov     [rsp+470h+lpVersionInformation], rcx; lpVersionInformation
0x1804d7072  mov     [rsp+470h+cchCount2], ebx; cchCount2
0x1804d7076  lea     rcx, aIsrecord_0; "isRecord"
0x1804d707d  mov     [rsp+470h+lpString2], rcx; lpString2
0x1804d7082  mov     r9d, eax; cchCount1
0x1804d7085  mov     r8, rsi; lpString1
0x1804d7088  mov     edx, 1; dwCmpFlags
0x1804d708d  lea     rcx, WindowName; lpLocaleName
0x1804d7094  call    cs:__imp_CompareStringEx
0x1804d709a  test    eax, eax
0x1804d709c  jz      loc_1804D771D
0x1804d70a2  xor     r15d, r15d
0x1804d70a5  add     eax, 0FFFFFFFEh
0x1804d70a8  test    eax, eax
0x1804d70aa  jz      loc_1804D7434
0x1804d70b0  test    rsi, rsi
0x1804d70b3  jz      loc_1804D7ADD
0x1804d70b9  cmp     r15w, [rsi]
0x1804d70bd  jz      loc_1804D7ADD
0x1804d70c3  cmp     r15w, word ptr cs:aIslockedrecord_0; "isLockedRecord"
0x1804d70cb  jz      loc_1804D7155
0x1804d70d1  mov     r14, rdi
0x1804d70d4  inc     r14
0x1804d70d7  cmp     [rsi+r14*2], r15w
0x1804d70dc  jnz     short loc_1804D70D4
0x1804d70de  lea     rax, aIslockedrecord_0; "isLockedRecord"
0x1804d70e5  mov     r15, rdi
0x1804d70e8  xor     ecx, ecx
0x1804d70ea  inc     r15
0x1804d70ed  cmp     [rax+r15*2], cx
0x1804d70f2  jnz     short loc_1804D70EA
0x1804d70f4  mov     rcx, r15; unsigned __int64
0x1804d70f7  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d70fc  mov     ebx, eax
0x1804d70fe  mov     rcx, r14; unsigned __int64
0x1804d7101  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d7106  xor     ecx, ecx
0x1804d7108  mov     [rsp+470h+lParam], rcx; lParam
0x1804d710d  mov     [rsp+470h+lpReserved], rcx; lpReserved
0x1804d7112  mov     [rsp+470h+lpVersionInformation], rcx; lpVersionInformation
0x1804d7117  mov     [rsp+470h+cchCount2], ebx; cchCount2
0x1804d711b  lea     rcx, aIslockedrecord_0; "isLockedRecord"
0x1804d7122  mov     [rsp+470h+lpString2], rcx; lpString2
0x1804d7127  mov     r9d, eax; cchCount1
0x1804d712a  mov     r8, rsi; lpString1
0x1804d712d  mov     edx, 1; dwCmpFlags
0x1804d7132  lea     rcx, WindowName; lpLocaleName
0x1804d7139  call    cs:__imp_CompareStringEx
0x1804d713f  test    eax, eax
0x1804d7141  jz      loc_1804D7847
0x1804d7147  xor     r15d, r15d
0x1804d714a  add     eax, 0FFFFFFFEh
0x1804d714d  test    eax, eax
0x1804d714f  jz      loc_1804D74C7
0x1804d7155  test    rsi, rsi
0x1804d7158  jz      loc_1804D7AF3
0x1804d715e  cmp     r15w, [rsi]
0x1804d7162  jz      loc_1804D7AF3
0x1804d7168  cmp     r15w, word ptr cs:aIsregulatoryre_0; "isRegulatoryRecord"
0x1804d7170  jz      loc_1804D737D
0x1804d7176  mov     r14, rdi
0x1804d7179  inc     r14
0x1804d717c  cmp     [rsi+r14*2], r15w
0x1804d7181  jnz     short loc_1804D7179
0x1804d7183  lea     rax, aIsregulatoryre_0; "isRegulatoryRecord"
0x1804d718a  mov     r15, rdi
0x1804d718d  xor     r12d, r12d
0x1804d7190  inc     r15
0x1804d7193  cmp     [rax+r15*2], r12w
0x1804d7198  jnz     short loc_1804D7190
0x1804d719a  mov     rcx, r15; unsigned __int64
0x1804d719d  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d71a2  mov     ebx, eax
0x1804d71a4  mov     rcx, r14; unsigned __int64
0x1804d71a7  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d71ac  mov     [rsp+470h+lParam], r12; lParam
0x1804d71b1  mov     [rsp+470h+lpReserved], r12; lpReserved
0x1804d71b6  mov     [rsp+470h+lpVersionInformation], r12; lpVersionInformation
0x1804d71bb  mov     [rsp+470h+cchCount2], ebx; cchCount2
0x1804d71bf  lea     rcx, aIsregulatoryre_0; "isRegulatoryRecord"
0x1804d71c6  mov     [rsp+470h+lpString2], rcx; lpString2
0x1804d71cb  mov     r9d, eax; cchCount1
0x1804d71ce  mov     r8, rsi; lpString1
0x1804d71d1  mov     edx, 1; dwCmpFlags
0x1804d71d6  lea     rcx, WindowName; lpLocaleName
0x1804d71dd  call    cs:__imp_CompareStringEx
0x1804d71e3  test    eax, eax
0x1804d71e5  jz      loc_1804D7971
0x1804d71eb  xor     r15d, r15d
0x1804d71ee  add     eax, 0FFFFFFFEh
0x1804d71f1  test    eax, eax
0x1804d71f3  jnz     loc_1804D737D
0x1804d71f9  mov     r14, [r13+0]
0x1804d71fd  test    r14, r14
0x1804d7200  jz      short loc_1804D726F
0x1804d7202  cmp     r15w, [r14]
0x1804d7206  jz      short loc_1804D726F
0x1804d7208  inc     rdi
0x1804d720b  cmp     [r14+rdi*2], r15w
0x1804d7210  jnz     short loc_1804D7208
0x1804d7212  mov     esi, 4
0x1804d7217  mov     ecx, esi; unsigned __int64
0x1804d7219  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d721e  mov     ebx, eax
0x1804d7220  mov     rcx, rdi; unsigned __int64
0x1804d7223  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d7228  mov     [rsp+470h+lParam], r15; lParam
0x1804d722d  mov     [rsp+470h+lpReserved], r15; lpReserved
0x1804d7232  mov     [rsp+470h+lpVersionInformation], r15; lpVersionInformation
0x1804d7237  mov     [rsp+470h+cchCount2], ebx; cchCount2
0x1804d723b  lea     r15, aTrue; "true"
0x1804d7242  mov     [rsp+470h+lpString2], r15; lpString2
0x1804d7247  mov     r9d, eax; cchCount1
0x1804d724a  mov     r8, r14; lpString1
0x1804d724d  lea     r13d, [rsi-3]
0x1804d7251  mov     edx, r13d; dwCmpFlags
0x1804d7254  lea     rcx, WindowName; lpLocaleName
0x1804d725b  call    cs:__imp_CompareStringEx
0x1804d7261  xor     r12d, r12d
0x1804d7264  test    eax, eax
0x1804d7266  jz      loc_1804D7A0A
0x1804d726c  lea     edi, [rax-2]
0x1804d726f  test    edi, edi
0x1804d7271  setz    bl
0x1804d7274  mov     rdi, [rsp+470h+var_420]
0x1804d7279  mov     rcx, rdi; this
0x1804d727c  call    ?EnsurePolicyData@RetentionLabelResponseDataBuilder@Clp@FileIO@@AEAAAEAURetentionLabelData@23@XZ; FileIO::Clp::RetentionLabelResponseDataBuilder::EnsurePolicyData(void)
0x1804d7281  mov     [rax+8Bh], bl
0x1804d7287  jmp     short loc_1804D72BD
0x1804d7289  lea     rax, aRetentionlabel_0; "RetentionLabelResponseDataBuilder::AddM"...
0x1804d7290  mov     [rsp+470h+var_418], rax
0x1804d7295  mov     r9d, 2
0x1804d729b  lea     rax, [rsp+470h+var_418]
0x1804d72a0  mov     [rsp+470h+lpString2], rax
0x1804d72a5  mov     edx, 8A5h
0x1804d72aa  mov     ecx, 1E4CD35Ch
0x1804d72af  lea     r8d, [r9+0Dh]
0x1804d72b3  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x1804d72b8  mov     rdi, [rsp+470h+var_420]
0x1804d72bd  mov     rax, rdi
0x1804d72c0  mov     rcx, [rbp+370h+var_40]
0x1804d72c7  xor     rcx, rsp; StackCookie
0x1804d72ca  call    __security_check_cookie
0x1804d72cf  mov     rbx, [rsp+470h+arg_18]
0x1804d72d7  add     rsp, 440h
0x1804d72de  pop     r15
0x1804d72e0  pop     r14
0x1804d72e2  pop     r13
0x1804d72e4  pop     r12
0x1804d72e6  pop     rdi
0x1804d72e7  pop     rsi
0x1804d72e8  pop     rbp
0x1804d72e9  retn
0x1804d72ea  mov     r14, [r13+0]
0x1804d72ee  test    r14, r14
0x1804d72f1  jz      short loc_1804D7360
0x1804d72f3  cmp     r15w, [r14]
0x1804d72f7  jz      short loc_1804D7360
0x1804d72f9  inc     rdi
0x1804d72fc  cmp     [r14+rdi*2], r15w
0x1804d7301  jnz     short loc_1804D72F9
0x1804d7303  mov     esi, 4
0x1804d7308  mov     ecx, esi; unsigned __int64
0x1804d730a  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d730f  mov     ebx, eax
0x1804d7311  mov     rcx, rdi; unsigned __int64
0x1804d7314  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1804d7319  mov     [rsp+470h+lParam], r15; lParam
0x1804d731e  mov     [rsp+470h+lpReserved], r15; lpReserved
0x1804d7323  mov     [rsp+470h+lpVersionInformation], r15; lpVersionInformation
0x1804d7328  mov     [rsp+470h+cchCount2], ebx; cchCount2
0x1804d732c  lea     r15, aTrue; "true"
0x1804d7333  mov     [rsp+470h+lpString2], r15; lpString2
0x1804d7338  mov     r9d, eax; cchCount1
0x1804d733b  mov     r8, r14; lpString1
0x1804d733e  lea     r13d, [rsi-3]
0x1804d7342  mov     edx, r13d; dwCmpFlags
  ... truncated ...
```
