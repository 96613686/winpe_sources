# DirectUI::MetadataAPI::GetBuiltinClassInfoByName(xstring_ptr_view const &)

- ea: `0x1800d2fdc`
- end: `0x1800d36df`
- name: `?GetBuiltinClassInfoByName@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z`
- size: `1795`
- prototype: `const CClassInfo *__fastcall(const xstring_ptr_view *strTypeName)`
- caller_count: `7`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800d0fc4`
- `0x1800d1f5c`
- `0x1800d260c`
- `0x1800d4598`
- `0x180195524`
- `0x180289320`
- `0x180a22270`

## callees

- `0x1800ab600`
- `0x1800adbb0`
- `0x1800d2fdc`
- `0x1806877a8`
- `0x180687890`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d366d`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d366d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d313c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3222`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d32fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d313c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d3222`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d32fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d33f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d347b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d3381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d33f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d347b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d316d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d3328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d316d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d3328`

## pseudocode

```c
const MetaDataType *__fastcall DirectUI::MetadataAPI::GetBuiltinClassInfoByName(const xstring_ptr_view *strTypeName)
{
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  int v3; // ebx
  UINT32 StringLen; // ebx
  unsigned __int64 v5; // rax
  PCWSTR StringRawBuffer; // r8
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  int v9; // eax
  unsigned __int64 p_m_ephemeralStorage; // rcx
  UINT32 v11; // ebx
  UINT32 v12; // ebx
  unsigned int v13; // edi
  unsigned int v14; // ebx
  __int64 m_nTypeIndex; // r14
  const wchar_t *Buffer; // r15
  int v17; // esi
  int v18; // eax
  UINT32 v19; // eax
  HSTRING v20; // rcx
  UINT32 v22; // ebx
  int v23; // edx
  const wchar_t *v24; // rdi
  UINT32 v25; // edx
  xstring_ptr_storage *v26; // rcx
  const wchar_t *v27; // rdi
  UINT32 v28; // ebx
  UINT32 v29; // ebx
  UINT32 v30; // ebx
  UINT32 v31; // ebx
  UINT32 v32; // ebx
  UINT32 v33; // ebx
  UINT32 v34; // ebx
  UINT32 v35; // ebx
  UINT32 v36; // ebx
  HSTRING v37; // rcx
  HSTRING v38; // rcx
  UINT32 v39; // ebx
  UINT32 v40; // ebx
  UINT32 v41; // ebx
  UINT32 v42; // eax
  UINT32 v43; // ebx
  UINT32 v44; // ebx
  UINT32 v45; // ebx
  UINT32 v46; // ebx
  HSTRING v47; // rcx
  PCWSTR v48; // rax
  UINT32 v49; // ebx
  UINT32 v50; // ebx
  UINT32 v51; // ebx
  UINT32 v52; // ebx
  UINT32 v53; // ebx
  UINT32 v54; // ebx
  UINT32 v55; // ebx
  UINT32 v56; // ebx
  UINT32 v57; // ebx
  UINT32 v58; // ebx
  UINT32 v59; // ebx
  xephemeral_string_ptr strNormalizedTypeName; // [rsp+20h] [rbp-50h] BYREF
  xstring_ptr_storage *v61; // [rsp+38h] [rbp-38h]
  const wchar_t *v62; // [rsp+40h] [rbp-30h] BYREF
  int v63; // [rsp+48h] [rbp-28h]
  xstring_ptr_view other; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v65; // [rsp+58h] [rbp-18h] BYREF
  int v66; // [rsp+60h] [rbp-10h]
  UINT32 length; // [rsp+A0h] [rbp+30h] BYREF
  UINT32 pcStowedExceptions; // [rsp+A8h] [rbp+38h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+B0h] [rbp+40h] BYREF

  RuntimeStringHandleMarker = strTypeName->m_encodedStorage.RuntimeStringHandleMarker;
  strNormalizedTypeName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( (RuntimeStringHandleMarker & 1) != 0 )
  {
    v38 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v3 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
    if ( v3 >= 0 )
    {
      StringLen = v3 & 0x3FFFFFFF;
      goto LABEL_4;
    }
    v38 = *(HSTRING *)RuntimeStringHandleMarker;
  }
  StringLen = WindowsGetStringLen(v38);
LABEL_4:
  v5 = strTypeName->m_encodedStorage.RuntimeStringHandleMarker;
  if ( (strTypeName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v37 = (HSTRING)(v5 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    StringRawBuffer = *(PCWSTR *)v5;
    if ( *(int *)(v5 + 8) >= 0 )
      goto LABEL_6;
    v37 = *(HSTRING *)v5;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v37, 0);
LABEL_6:
  v7 = strTypeName->m_encodedStorage.RuntimeStringHandleMarker;
  v8 = strTypeName->m_encodedStorage.RuntimeStringHandleMarker & 1;
  if ( *StringRawBuffer == 33 )
  {
    length = 0;
    if ( v8 )
    {
      v47 = (HSTRING)(v7 & 0xFFFFFFFFFFFFFFFEuLL);
    }
    else
    {
      v23 = *(_DWORD *)(v7 + 8);
      v24 = *(const wchar_t **)v7;
      if ( v23 >= 0 )
      {
        v25 = v23 & 0x3FFFFFFF;
        length = v25;
        goto LABEL_39;
      }
      v47 = *(HSTRING *)v7;
    }
    v48 = WindowsGetStringRawBuffer(v47, &length);
    v25 = length;
    v24 = v48;
LABEL_39:
    if ( !StringLen || StringLen > v25 || !v25 )
    {
      if ( ((__int64)strNormalizedTypeName.m_encodedStorage.Storage & 1) != 0 )
        WindowsDeleteString((HSTRING)(strNormalizedTypeName.m_encodedStorage.RuntimeStringHandleMarker
                                    & 0xFFFFFFFFFFFFFFFEuLL));
      p_m_ephemeralStorage = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
      --StringLen;
      goto LABEL_12;
    }
    --StringLen;
    v26 = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    v61 = &xstring_ptr_constants::c_xstring_ptr_storage_null;
    if ( StringLen > 0x3FFFFFFF )
    {
      pppStowedExceptions = 0;
      pcStowedExceptions = 0;
      TraceForFailFast(-2147418113);
      OnNewFailureEncountered(-2147418113, 0, 0);
      GetStowedExceptionsForFailFast(&pppStowedExceptions, &pcStowedExceptions);
      RoFailFastWithErrorContextInternal2(-2147418113, pcStowedExceptions, pppStowedExceptions);
      v26 = v61;
    }
    v27 = v24 + 1;
    v62 = v27;
    v9 = StringLen & 0x3FFFFFFF | 0x40000000;
    v63 = v9;
    if ( ((unsigned __int8)v26 & 1) != 0 )
    {
      WindowsDeleteString((HSTRING)((unsigned __int64)v26 & 0xFFFFFFFFFFFFFFFEuLL));
      v9 = v63;
      v27 = v62;
    }
    v61 = (xstring_ptr_storage *)&v62;
    if ( ((unsigned __int8)&v62 & 1) == 0 )
    {
      strNormalizedTypeName.m_ephemeralStorage.Buffer = v27;
      goto LABEL_9;
    }
    pcStowedExceptions = 0;
    strNormalizedTypeName.m_ephemeralStorage.Buffer = WindowsGetStringRawBuffer((HSTRING)&v62, &pcStowedExceptions);
    v42 = pcStowedExceptions;
LABEL_81:
    v9 = v42 & 0x3FFFFFFF;
    goto LABEL_9;
  }
  if ( v8 )
  {
    length = 0;
    strNormalizedTypeName.m_ephemeralStorage.Buffer = WindowsGetStringRawBuffer(
                                                        (HSTRING)(v7 & 0xFFFFFFFFFFFFFFFEuLL),
                                                        &length);
    v42 = length;
    goto LABEL_81;
  }
  strNormalizedTypeName.m_ephemeralStorage.Buffer = *(const wchar_t **)v7;
  v9 = *(_DWORD *)(v7 + 8);
LABEL_9:
  *((_DWORD *)&strNormalizedTypeName.m_ephemeralStorage + 2) = v9 & 0x3FFFFFFF | 0x40000000;
  if ( ((__int64)strNormalizedTypeName.m_encodedStorage.Storage & 1) != 0 )
    WindowsDeleteString((HSTRING)(strNormalizedTypeName.m_encodedStorage.RuntimeStringHandleMarker
                                & 0xFFFFFFFFFFFFFFFEuLL));
  p_m_ephemeralStorage = (unsigned __int64)&strNormalizedTypeName.m_ephemeralStorage;
LABEL_12:
  strNormalizedTypeName.m_encodedStorage.RuntimeStringHandleMarker = p_m_ephemeralStorage;
  if ( StringLen <= 0x19 )
  {
    if ( StringLen == 25 )
    {
      v13 = 796;
      v14 = 759;
      goto LABEL_20;
    }
    if ( StringLen > 0xE )
    {
      if ( StringLen > 0x14 )
      {
        v39 = StringLen - 21;
        if ( !v39 )
        {
          v13 = 625;
          v14 = 587;
          goto LABEL_20;
        }
        v40 = v39 - 1;
        if ( !v40 )
        {
          v13 = 679;
          v14 = 625;
          goto LABEL_20;
        }
        v41 = v40 - 1;
        if ( !v41 )
        {
          v13 = 722;
          v14 = 679;
          goto LABEL_20;
        }
        if ( v41 == 1 )
        {
          v13 = 759;
          v14 = 722;
          goto LABEL_20;
        }
      }
      else
      {
        if ( StringLen == 20 )
        {
          v13 = 587;
          v14 = 537;
          goto LABEL_20;
        }
        v35 = StringLen - 15;
        if ( !v35 )
        {
          v13 = 362;
          v14 = 312;
          goto LABEL_20;
        }
        v36 = v35 - 1;
        if ( !v36 )
        {
          v13 = 403;
          v14 = 362;
          goto LABEL_20;
        }
        v53 = v36 - 1;
        if ( !v53 )
        {
          v13 = 439;
          v14 = 403;
          goto LABEL_20;
        }
        v54 = v53 - 1;
        if ( !v54 )
        {
          v13 = 480;
          v14 = 439;
          goto LABEL_20;
        }
        if ( v54 == 1 )
        {
          v13 = 537;
          v14 = 480;
          goto LABEL_20;
        }
      }
    }
    else
    {
      if ( StringLen == 14 )
      {
        v13 = 312;
        v14 = 271;
        goto LABEL_20;
      }
      if ( StringLen <= 8 )
      {
        if ( StringLen == 8 )
        {
          v13 = 92;
          v14 = 67;
          goto LABEL_20;
        }
        v28 = StringLen - 3;
        if ( !v28 )
        {
          v13 = 4;
          v14 = 1;
          goto LABEL_20;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          v13 = 14;
          v14 = 4;
          goto LABEL_20;
        }
        v30 = v29 - 1;
        if ( !v30 )
        {
          v13 = 28;
          v14 = 14;
          goto LABEL_20;
        }
        v31 = v30 - 1;
        if ( !v31 )
        {
          v13 = 50;
          v14 = 28;
          goto LABEL_20;
        }
        if ( v31 == 1 )
        {
          v13 = 67;
          v14 = 50;
          goto LABEL_20;
        }
      }
      else
      {
        v11 = StringLen - 9;
        if ( !v11 )
        {
          v13 = 123;
          v14 = 92;
          goto LABEL_20;
        }
        v12 = v11 - 1;
        if ( !v12 )
        {
          v13 = 164;
          v14 = 123;
          goto LABEL_20;
        }
        v22 = v12 - 1;
        if ( !v22 )
        {
          v13 = 199;
          v14 = 164;
          goto LABEL_20;
        }
        v49 = v22 - 1;
        if ( !v49 )
        {
          v13 = 239;
          v14 = 199;
          goto LABEL_20;
        }
        if ( v49 == 1 )
        {
          v13 = 271;
          v14 = 239;
          goto LABEL_20;
        }
      }
    }
    goto LABEL_61;
  }
  if ( StringLen <= 0x25 )
  {
    if ( StringLen == 37 )
    {
      v13 = 1003;
      v14 = 997;
      goto LABEL_20;
    }
    if ( StringLen <= 0x1F )
    {
      if ( StringLen == 31 )
      {
        v13 = 932;
        v14 = 917;
        goto LABEL_20;
      }
      v50 = StringLen - 26;
      if ( !v50 )
      {
        v13 = 828;
        v14 = 796;
        goto LABEL_20;
      }
      v51 = v50 - 1;
      if ( !v51 )
      {
        v13 = 845;
        v14 = 828;
        goto LABEL_20;
      }
      v52 = v51 - 1;
      if ( !v52 )
      {
        v13 = 869;
        v14 = 845;
        goto LABEL_20;
      }
      v55 = v52 - 1;
      if ( !v55 )
      {
        v13 = 893;
        v14 = 869;
        goto LABEL_20;
      }
      if ( v55 == 1 )
      {
        v13 = 917;
        v14 = 893;
        goto LABEL_20;
      }
    }
    else
    {
      v43 = StringLen - 32;
      if ( !v43 )
      {
        v13 = 953;
        v14 = 932;
        goto LABEL_20;
      }
      v44 = v43 - 1;
      if ( !v44 )
      {
        v13 = 965;
        v14 = 953;
        goto LABEL_20;
      }
      v45 = v44 - 1;
      if ( !v45 )
      {
        v13 = 981;
        v14 = 965;
        goto LABEL_20;
      }
      v46 = v45 - 1;
      if ( !v46 )
      {
        v13 = 990;
        v14 = 981;
        goto LABEL_20;
      }
      if ( v46 == 1 )
      {
        v13 = 997;
        v14 = 990;
        goto LABEL_20;
      }
    }
    goto LABEL_61;
  }
  if ( StringLen <= 0x2B )
  {
    if ( StringLen == 43 )
    {
      v13 = 1022;
      v14 = 1019;
      goto LABEL_20;
    }
    v56 = StringLen - 38;
    if ( !v56 )
    {
      v13 = 1007;
      v14 = 1003;
      goto LABEL_20;
    }
    v57 = v56 - 1;
    if ( !v57 )
    {
      v13 = 1012;
      v14 = 1007;
      goto LABEL_20;
    }
    v58 = v57 - 1;
    if ( !v58 )
    {
      v13 = 1015;
      v14 = 1012;
      goto LABEL_20;
    }
    v59 = v58 - 1;
    if ( !v59 )
    {
      v13 = 1018;
      v14 = 1015;
      goto LABEL_20;
    }
    if ( v59 == 1 )
    {
      v13 = 1019;
      v14 = 1018;
      goto LABEL_20;
    }
    goto LABEL_61;
  }
  v32 = StringLen - 44;
  if ( v32 )
  {
    v33 = v32 - 2;
    if ( !v33 )
    {
      v13 = 1024;
      v14 = 1023;
      goto LABEL_20;
    }
    v34 = v33 - 3;
    if ( !v34 )
    {
      v13 = 1025;
      v14 = 1024;
      goto LABEL_20;
    }
    if ( v34 == 1 )
    {
      v13 = 1026;
      v14 = 1025;
      goto LABEL_20;
    }
LABEL_61:
    v13 = 0;
    v14 = 0;
    goto LABEL_20;
  }
  v13 = 1023;
  v14 = 1022;
LABEL_20:
  while ( v14 < v13 )
  {
    m_nTypeIndex = (unsigned __int16)c_aTypeNames[v14].m_nTypeIndex;
    Buffer = c_aTypeNameInfos[m_nTypeIndex].m_strNameStorage.Buffer;
    v17 = *((_DWORD *)&c_aTypeNameInfos[m_nTypeIndex].m_strNameStorage + 2) & 0x3FFFFFFF;
    if ( ((__int64)strNormalizedTypeName.m_encodedStorage.Storage & 1) != 0 )
    {
      v20 = (HSTRING)(p_m_ephemeralStorage & 0xFFFFFFFFFFFFFFFEuLL);
    }
    else
    {
      v18 = *(_DWORD *)(p_m_ephemeralStorage + 8);
      if ( v18 >= 0 )
      {
        v19 = v18 & 0x3FFFFFFF;
        goto LABEL_24;
      }
      v20 = *(HSTRING *)p_m_ephemeralStorage;
    }
    v19 = WindowsGetStringLen(v20);
    p_m_ephemeralStorage = strNormalizedTypeName.m_encodedStorage.RuntimeStringHandleMarker;
LABEL_24:
    if ( v19 == v17 )
    {
      v65 = Buffer;
      v66 = v17 | 0x40000000;
      other.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
      if ( ((unsigned __int8)&xstring_ptr_constants::c_xstring_ptr_storage_null & 1) != 0 )
        WindowsDeleteString((HSTRING)((unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null
                                    & 0xFFFFFFFFFFFFFFFEuLL));
      other.m_encodedStorage.Storage = (const xstring_ptr_storage *)&v65;
      if ( !xstring_ptr_view::Compare(&strNormalizedTypeName.xstring_ptr_view, &other, xstrCompareCaseSensitive) )
        return &c_aTypes[m_nTypeIndex];
      p_m_ephemeralStorage = strNormalizedTypeName.m_encodedStorage.RuntimeStringHandleMarker;
    }
    ++v14;
  }
  return 0;
}

```

## disassembly

```asm
0x1800d2fdc  mov     [rsp-28h+arg_18], rbx
0x1800d2fe1  push    rbp
0x1800d2fe2  push    rsi
0x1800d2fe3  push    rdi
0x1800d2fe4  push    r14
0x1800d2fe6  push    r15
0x1800d2fe8  mov     rbp, rsp
0x1800d2feb  sub     rsp, 70h
0x1800d2fef  mov     rdi, strTypeName
0x1800d2ff2  lea     r15, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d2ff9  mov     strTypeName, [strTypeName]
0x1800d2ffc  xor     esi, esi
0x1800d2ffe  mov     qword ptr [rbp+strNormalizedTypeName.m_encodedStorage.___u0], r15
0x1800d3002  mov     r14d, 3FFFFFFFh
0x1800d3008  test    cl, 1
0x1800d300b  jnz     loc_1800D3324
0x1800d3011  mov     ebx, [strTypeName+8]
0x1800d3014  test    ebx, ebx
0x1800d3016  js      loc_1800D35CD
0x1800d301c  and     ebx, r14d
0x1800d301f  mov     rax, [rdi]
0x1800d3022  test    al, 1
0x1800d3024  jnz     loc_1800D330D
0x1800d302a  mov     r8, [rax]
0x1800d302d  cmp     [rax+8], esi
0x1800d3030  jl      loc_1800D34E8
0x1800d3036  mov     strTypeName, [rdi]
0x1800d3039  mov     rax, strTypeName
0x1800d303c  and     eax, 1
0x1800d303f  cmp     word ptr [r8], 21h ; '!'
0x1800d3044  jz      loc_1800D31B9
0x1800d304a  test    rax, rax
0x1800d304d  jnz     loc_1800D3376
0x1800d3053  mov     rax, [strTypeName]
0x1800d3056  mov     qword ptr [rbp+strNormalizedTypeName.m_ephemeralStorage.___u0], rax
0x1800d305a  mov     eax, [strTypeName+8]
0x1800d305d  mov     strTypeName, qword ptr [rbp+strNormalizedTypeName.m_encodedStorage.___u0]
0x1800d3061  and     eax, r14d
0x1800d3064  bts     eax, 1Eh
0x1800d3068  mov     dword ptr [rbp+strNormalizedTypeName.m_ephemeralStorage.Count], eax
0x1800d306b  test    cl, 1
0x1800d306e  jz      short loc_1800D307A
0x1800d3070  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d3074  call    cs:__imp_WindowsDeleteString
0x1800d307a  lea     strTypeName, [rbp+strNormalizedTypeName.m_ephemeralStorage]
0x1800d307e  mov     qword ptr [rbp+strNormalizedTypeName.m_encodedStorage.___u0], strTypeName
0x1800d3082  cmp     ebx, 19h
0x1800d3085  ja      loc_1800D3287
0x1800d308b  jz      loc_1800D3562
0x1800d3091  mov     eax, 0Eh
0x1800d3096  cmp     ebx, eax
0x1800d3098  ja      loc_1800D32C6
0x1800d309e  jz      loc_1800D34C1
0x1800d30a4  cmp     ebx, 8
0x1800d30a7  jbe     loc_1800D324D
0x1800d30ad  sub     ebx, 9
0x1800d30b0  jz      loc_1800D3369
0x1800d30b6  sub     ebx, 1
0x1800d30b9  jnz     loc_1800D31A3
0x1800d30bf  mov     edi, 0A4h
0x1800d30c4  lea     ebx, [rax+6Dh]
0x1800d30c7  lea     rdx, std__nothrow
0x1800d30ce  cmp     ebx, edi
0x1800d30d0  jnb     loc_1800D319F
0x1800d30d6  mov     eax, ebx
0x1800d30d8  movzx   r14d, word ptr ds:rva ?c_aTypeNames@@3QBUMetaDataTypeName@@B.m_nTypeIndex[rdx+rax*2]; MetaDataTypeName const near * const c_aTypeNames ...
0x1800d30e1  imul    rax, r14, 1Ch
0x1800d30e5  mov     esi, [rax+rdx+0C1F918h]
0x1800d30ec  mov     r15, [rax+rdx+0C1F910h]
0x1800d30f4  mov     edx, 3FFFFFFFh
0x1800d30f9  and     esi, edx
0x1800d30fb  test    byte ptr [rbp+strNormalizedTypeName.m_encodedStorage.___u0], 1
0x1800d30ff  jnz     short loc_1800D3169
0x1800d3101  mov     eax, [strTypeName+8]
0x1800d3104  test    eax, eax
0x1800d3106  js      loc_1800D3417
0x1800d310c  and     eax, edx
0x1800d310e  cmp     eax, esi
0x1800d3110  jnz     short loc_1800D3162
0x1800d3112  bts     esi, 1Eh
0x1800d3116  mov     [rbp+var_18], r15
0x1800d311a  lea     r15, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d3121  mov     [rbp+var_10], esi
0x1800d3124  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d312b  mov     qword ptr [rbp+other.m_encodedStorage.___u0], rax
0x1800d312f  test    r15b, 1
0x1800d3133  jz      short loc_1800D3142
0x1800d3135  mov     strTypeName, r15
0x1800d3138  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d313c  call    cs:__imp_WindowsDeleteString
0x1800d3142  lea     rax, [rbp+var_18]
0x1800d3146  xor     r8d, r8d; eCompareBehavior
0x1800d3149  lea     rdx, [rbp+other]; other
0x1800d314d  mov     qword ptr [rbp+other.m_encodedStorage.___u0], rax
0x1800d3151  lea     strTypeName, [rbp+strNormalizedTypeName]; this
0x1800d3155  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,xstrCompareBehavior)
0x1800d315a  test    eax, eax
0x1800d315c  jz      short loc_1800D3179
0x1800d315e  mov     strTypeName, qword ptr [rbp+strNormalizedTypeName.m_encodedStorage.___u0]
0x1800d3162  inc     ebx
0x1800d3164  jmp     loc_1800D30C7
0x1800d3169  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d316d  call    cs:__imp_WindowsGetStringLen
0x1800d3173  mov     strTypeName, qword ptr [rbp+strNormalizedTypeName.m_encodedStorage.___u0]
0x1800d3177  jmp     short loc_1800D310E
0x1800d3179  lea     rax, std__nothrow
0x1800d3180  lea     rax, [rax+r14*8]
0x1800d3184  lea     rax, [rax+0E5B450h]
0x1800d318b  mov     rbx, [rsp+70h+arg_18]
0x1800d3193  add     rsp, 70h
0x1800d3197  pop     r15
0x1800d3199  pop     r14
0x1800d319b  pop     rdi
0x1800d319c  pop     rsi
0x1800d319d  pop     rbp
0x1800d319e  retn
0x1800d319f  xor     eax, eax
0x1800d31a1  jmp     short loc_1800D318B
0x1800d31a3  sub     ebx, 1
0x1800d31a6  jnz     loc_1800D3401
0x1800d31ac  mov     edi, 0C7h
0x1800d31b1  lea     ebx, [rdi-23h]
0x1800d31b4  jmp     loc_1800D30C7
0x1800d31b9  mov     [rbp+length], esi
0x1800d31bc  test    rax, rax
0x1800d31bf  jnz     loc_1800D33E8
0x1800d31c5  mov     edx, [strTypeName+8]
0x1800d31c8  mov     rdi, [strTypeName]
0x1800d31cb  test    edx, edx
0x1800d31cd  js      loc_1800D3609
0x1800d31d3  and     edx, r14d
0x1800d31d6  mov     [rbp+length], edx
0x1800d31d9  cmp     ebx, 1
0x1800d31dc  jb      loc_1800D32F0
0x1800d31e2  cmp     ebx, edx
0x1800d31e4  ja      loc_1800D32F0
0x1800d31ea  cmp     edx, 1
0x1800d31ed  jb      loc_1800D32F0
0x1800d31f3  dec     ebx
0x1800d31f5  mov     strTypeName, r15
0x1800d31f8  mov     [rbp+var_38], strTypeName
0x1800d31fc  cmp     ebx, r14d
0x1800d31ff  ja      loc_1800D3638
0x1800d3205  add     rdi, 2
0x1800d3209  mov     eax, ebx
0x1800d320b  and     eax, r14d
0x1800d320e  mov     [rbp+var_30], rdi
0x1800d3212  bts     eax, 1Eh
0x1800d3216  mov     [rbp+var_28], eax
0x1800d3219  test    cl, 1
0x1800d321c  jz      short loc_1800D322F
0x1800d321e  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d3222  call    cs:__imp_WindowsDeleteString
0x1800d3228  mov     eax, [rbp+var_28]
0x1800d322b  mov     rdi, [rbp+var_30]
0x1800d322f  lea     strTypeName, [rbp+var_30]
0x1800d3233  mov     [rbp+var_38], strTypeName
0x1800d3237  lea     strTypeName, [rbp+var_30]
0x1800d323b  test    cl, 1
0x1800d323e  jnz     loc_1800D346C
0x1800d3244  mov     qword ptr [rbp+strNormalizedTypeName.m_ephemeralStorage.___u0], rdi
0x1800d3248  jmp     loc_1800D305D
0x1800d324d  jz      loc_1800D34DB
0x1800d3253  sub     ebx, 3
0x1800d3256  jz      loc_1800D35D5
0x1800d325c  sub     ebx, 1
0x1800d325f  jz      loc_1800D350B
0x1800d3265  sub     ebx, 1
0x1800d3268  jz      loc_1800D3335
0x1800d326e  sub     ebx, 1
0x1800d3271  jz      loc_1800D33DB
0x1800d3277  cmp     ebx, 1
0x1800d327a  jnz     short loc_1800D32BD
0x1800d327c  lea     edi, [rbx+42h]
0x1800d327f  lea     ebx, [rdi-11h]
0x1800d3282  jmp     loc_1800D30C7
0x1800d3287  cmp     ebx, 25h ; '%'
0x1800d328a  jbe     loc_1800D3396
0x1800d3290  cmp     ebx, 2Bh ; '+'
0x1800d3293  jbe     loc_1800D35AC
0x1800d3299  sub     ebx, 2Ch ; ','
0x1800d329c  jz      loc_1800D36D2
0x1800d32a2  sub     ebx, 2
0x1800d32a5  jz      loc_1800D361E
0x1800d32ab  sub     ebx, 3
0x1800d32ae  jz      loc_1800D35FC
0x1800d32b4  cmp     ebx, 1
0x1800d32b7  jz      loc_1800D36C5
0x1800d32bd  mov     edi, esi
0x1800d32bf  mov     ebx, esi
0x1800d32c1  jmp     loc_1800D30C7
0x1800d32c6  cmp     ebx, 14h
0x1800d32c9  ja      short loc_1800D3341
0x1800d32cb  jz      loc_1800D34B4
0x1800d32d1  sub     ebx, 0Fh
0x1800d32d4  jz      loc_1800D34CE
0x1800d32da  sub     ebx, 1
0x1800d32dd  jnz     loc_1800D3449
0x1800d32e3  mov     edi, 193h
0x1800d32e8  lea     ebx, [rdi-29h]
0x1800d32eb  jmp     loc_1800D30C7
0x1800d32f0  mov     strTypeName, qword ptr [rbp+strNormalizedTypeName.m_encodedStorage.___u0]
0x1800d32f4  test    cl, 1
0x1800d32f7  jz      short loc_1800D3303
0x1800d32f9  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d32fd  call    cs:__imp_WindowsDeleteString
0x1800d3303  mov     strTypeName, r15
0x1800d3306  dec     ebx
0x1800d3308  jmp     loc_1800D307E
0x1800d330d  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800d3311  mov     strTypeName, rax; string
0x1800d3314  xor     edx, edx; length
0x1800d3316  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d331c  mov     r8, rax
0x1800d331f  jmp     loc_1800D3036
0x1800d3324  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d3328  call    cs:__imp_WindowsGetStringLen
0x1800d332e  mov     ebx, eax
0x1800d3330  jmp     loc_1800D301F
0x1800d3335  mov     edi, 1Ch
0x1800d333a  mov     ebx, eax
0x1800d333c  jmp     loc_1800D30C7
0x1800d3341  sub     ebx, 15h
0x1800d3344  jz      loc_1800D345F
0x1800d334a  sub     ebx, 1
0x1800d334d  jz      loc_1800D3548
0x1800d3353  sub     ebx, 1
0x1800d3356  jnz     loc_1800D356F
0x1800d335c  mov     edi, 2D2h
0x1800d3361  lea     ebx, [rdi-2Bh]
0x1800d3364  jmp     loc_1800D30C7
0x1800d3369  mov     edi, 7Bh ; '{'
0x1800d336e  lea     ebx, [rdi-1Fh]
0x1800d3371  jmp     loc_1800D30C7
0x1800d3376  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d337a  mov     [rbp+length], esi
0x1800d337d  lea     rdx, [rbp+length]; length
0x1800d3381  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d3387  mov     qword ptr [rbp+strNormalizedTypeName.m_ephemeralStorage.___u0], rax
0x1800d338b  mov     eax, [rbp+length]
0x1800d338e  and     eax, r14d
0x1800d3391  jmp     loc_1800D305D
0x1800d3396  jz      loc_1800D3611
0x1800d339c  cmp     ebx, 1Fh
0x1800d339f  jbe     short loc_1800D341F
0x1800d33a1  sub     ebx, 20h ; ' '
0x1800d33a4  jz      loc_1800D34A7
0x1800d33aa  sub     ebx, 1
0x1800d33ad  jz      loc_1800D359F
0x1800d33b3  sub     ebx, 1
0x1800d33b6  jz      loc_1800D35E2
0x1800d33bc  sub     ebx, 1
0x1800d33bf  jz      loc_1800D348D
0x1800d33c5  cmp     ebx, 1
0x1800d33c8  jnz     loc_1800D32BD
0x1800d33ce  mov     edi, 3E5h
0x1800d33d3  lea     ebx, [rdi-7]
0x1800d33d6  jmp     loc_1800D30C7
0x1800d33db  mov     edi, 32h ; '2'
0x1800d33e0  lea     ebx, [rdi-16h]
0x1800d33e3  jmp     loc_1800D30C7
0x1800d33e8  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d33ec  lea     rdx, [rbp+length]; length
0x1800d33f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d33f6  mov     edx, [rbp+length]
0x1800d33f9  mov     rdi, rax
0x1800d33fc  jmp     loc_1800D31D9
0x1800d3401  sub     ebx, 1
0x1800d3404  jnz     loc_1800D3532
0x1800d340a  mov     edi, 0EFh
0x1800d340f  lea     ebx, [rdi-28h]
0x1800d3412  jmp     loc_1800D30C7
0x1800d3417  mov     strTypeName, [strTypeName]
0x1800d341a  jmp     loc_1800D316D
0x1800d341f  jz      loc_1800D3585
0x1800d3425  sub     ebx, 1Ah
0x1800d3428  jz      loc_1800D35EF
0x1800d342e  sub     ebx, 1
0x1800d3431  jz      short loc_1800D349A
0x1800d3433  sub     ebx, 1
0x1800d3436  jnz     loc_1800D3517
0x1800d343c  mov     edi, 365h
0x1800d3441  lea     ebx, [rdi-18h]
0x1800d3444  jmp     loc_1800D30C7
0x1800d3449  sub     ebx, 1
0x1800d344c  jnz     loc_1800D34F0
0x1800d3452  mov     edi, 1B7h
0x1800d3457  lea     ebx, [rdi-24h]
0x1800d345a  jmp     loc_1800D30C7
0x1800d345f  mov     edi, 271h
0x1800d3464  lea     ebx, [rdi-26h]
0x1800d3467  jmp     loc_1800D30C7
0x1800d346c  lea     strTypeName, [rbp+var_30]
0x1800d3470  mov     [rbp+pcStowedExceptions], esi
0x1800d3473  and     strTypeName, 0FFFFFFFFFFFFFFFEh; string
0x1800d3477  lea     rdx, [rbp+pcStowedExceptions]; length
0x1800d347b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d3481  mov     qword ptr [rbp+strNormalizedTypeName.m_ephemeralStorage.___u0], rax
0x1800d3485  mov     eax, [rbp+pcStowedExceptions]
0x1800d3488  jmp     loc_1800D338E
  ... truncated ...
```
