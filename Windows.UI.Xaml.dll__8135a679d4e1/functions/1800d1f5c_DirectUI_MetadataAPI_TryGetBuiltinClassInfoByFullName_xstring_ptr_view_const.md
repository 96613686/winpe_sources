# DirectUI::MetadataAPI::TryGetBuiltinClassInfoByFullName(xstring_ptr_view const &)

- ea: `0x1800d1f5c`
- end: `0x1800d2488`
- name: `?TryGetBuiltinClassInfoByFullName@MetadataAPI@DirectUI@@CAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z`
- size: `1324`
- prototype: `const CClassInfo *__fastcall(const xstring_ptr_view *strTypeFullName)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800d0c0c`
- `0x1800d0fc4`
- `0x1800d13d4`
- `0x1800d1d80`
- `0x1801e67c4`

## callees

- `0x1800aabf0`
- `0x1800ab600`
- `0x1800af8e0`
- `0x1800d1f5c`
- `0x1800d2524`
- `0x1800d2fdc`
- `0x1800fe130`
- `0x1806877a8`
- `0x180687890`
- `0x18076d6e0`

## import_xrefs

- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2472`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1800d2472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2131`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2131`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d233c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d23bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d23de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d233c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d23bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d23de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d22ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2384`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d22ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d2384`

## pseudocode

```c
const MetaDataType *__fastcall DirectUI::MetadataAPI::TryGetBuiltinClassInfoByFullName(
        xstring_ptr_view *strTypeFullName)
{
  xstring_ptr_storage *v1; // rbx
  const MetaDataType *BuiltinClassInfoByName; // r15
  char v4; // si
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  int v6; // edi
  UINT32 StringLen; // edi
  int v8; // eax
  unsigned int v9; // eax
  bool v10; // r13
  char v11; // al
  unsigned __int64 v12; // rcx
  int v13; // edi
  int v14; // eax
  PCWSTR v15; // r8
  int Storage; // eax
  _WORD *i; // r14
  __int64 v18; // r14
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  int v21; // edi
  unsigned int v22; // edi
  unsigned __int64 v23; // rcx
  __int64 v24; // r14
  int v25; // eax
  PCWSTR v26; // r15
  unsigned int v27; // eax
  unsigned int v28; // edi
  const wchar_t *v29; // rcx
  UINT32 v30; // edi
  unsigned __int64 v31; // rcx
  int v32; // ebx
  UINT32 v33; // ebx
  xstring_ptr_storage *p_m_strFullNameStorage; // rcx
  unsigned __int64 v36; // rcx
  int v37; // eax
  PCWSTR StringRawBuffer; // r14
  __int64 RuntimeStringHandleMarker_low; // rax
  const wchar_t *v40; // rdi
  const wchar_t *trivial_2; // rax
  __int64 v42; // rax
  int v43; // eax
  UINT32 v44; // eax
  int v45; // eax
  HSTRING v46; // rcx
  HSTRING Handle; // rcx
  HSTRING v48; // rcx
  HSTRING v49; // rcx
  wchar_t *v50; // rcx
  HSTRING v51; // rcx
  HSTRING Buffer; // rcx
  HSTRING v53; // rcx
  xephemeral_string_ptr strTypeName; // [rsp+30h] [rbp-38h] BYREF
  xstring_ptr_storage *v55; // [rsp+48h] [rbp-20h]
  const wchar_t *v56; // [rsp+50h] [rbp-18h] BYREF
  UINT32 v57; // [rsp+58h] [rbp-10h]
  xstring_ptr v58; // [rsp+B0h] [rbp+48h] BYREF
  UINT32 length; // [rsp+B8h] [rbp+50h] BYREF
  int v60; // [rsp+C0h] [rbp+58h]
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+C8h] [rbp+60h] BYREF

  LODWORD(v58.m_encodedStorage.Storage) = 0;
  v1 = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  BuiltinClassInfoByName = 0;
  strTypeName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  *((_DWORD *)&strTypeName.m_ephemeralStorage + 2) = 1073741832;
  strTypeName.m_ephemeralStorage.Buffer = L"Windows.";
  v4 = 1;
  if ( ((unsigned __int8)&xstring_ptr_constants::c_xstring_ptr_storage_null & 1) != 0 )
    WindowsDeleteString((HSTRING)((unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null
                                & 0xFFFFFFFFFFFFFFFEuLL));
  RuntimeStringHandleMarker = strTypeFullName->m_encodedStorage.RuntimeStringHandleMarker;
  strTypeName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&strTypeName.m_ephemeralStorage;
  if ( (RuntimeStringHandleMarker & 1) != 0 )
  {
    v46 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v6 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
    if ( v6 >= 0 )
    {
      StringLen = v6 & 0x3FFFFFFF;
      goto LABEL_6;
    }
    v46 = *(HSTRING *)RuntimeStringHandleMarker;
  }
  StringLen = WindowsGetStringLen(v46);
LABEL_6:
  if ( ((__int64)strTypeName.m_encodedStorage.Storage & 1) != 0 )
  {
    Handle = (HSTRING)(strTypeName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_72:
    v9 = WindowsGetStringLen(Handle);
    goto LABEL_9;
  }
  v8 = *(_DWORD *)(strTypeName.m_encodedStorage.RuntimeStringHandleMarker + 8);
  if ( v8 < 0 )
  {
    Handle = strTypeName.m_encodedStorage.Storage->Handle;
    goto LABEL_72;
  }
  v9 = v8 & 0x3FFFFFFF;
LABEL_9:
  if ( StringLen >= v9 )
  {
    v10 = 0;
    if ( !xstring_ptr_view::Compare(strTypeFullName, &strTypeName, 0, v9, xstrCompareCaseSensitive) )
      goto LABEL_11;
  }
  v36 = strTypeFullName->m_encodedStorage.RuntimeStringHandleMarker;
  LODWORD(v58.m_encodedStorage.Storage) = 0;
  if ( (v36 & 1) != 0 )
  {
    v53 = (HSTRING)(v36 & 0xFFFFFFFFFFFFFFFEuLL);
LABEL_86:
    StringRawBuffer = WindowsGetStringRawBuffer(v53, (UINT32 *)&v58);
    RuntimeStringHandleMarker_low = LODWORD(v58.m_encodedStorage.RuntimeStringHandleMarker);
    goto LABEL_55;
  }
  v37 = *(_DWORD *)(v36 + 8);
  StringRawBuffer = *(PCWSTR *)v36;
  if ( v37 < 0 )
  {
    v53 = *(HSTRING *)v36;
    goto LABEL_86;
  }
  RuntimeStringHandleMarker_low = v37 & 0x3FFFFFFF;
  LODWORD(v58.m_encodedStorage.Storage) = RuntimeStringHandleMarker_low;
LABEL_55:
  if ( !(_DWORD)RuntimeStringHandleMarker_low
    || (v40 = &StringRawBuffer[RuntimeStringHandleMarker_low],
        trivial_2 = (const wchar_t *)_std_find_trivial_2(StringRawBuffer, v40, 0x2Eu),
        trivial_2 == v40) )
  {
    v10 = 1;
    goto LABEL_11;
  }
  v42 = trivial_2 - StringRawBuffer;
  v10 = (_DWORD)v42 == -1;
  if ( (_DWORD)v42 == -1 )
  {
LABEL_11:
    v11 = 1;
    goto LABEL_12;
  }
  v11 = 0;
LABEL_12:
  if ( !v11 )
    return BuiltinClassInfoByName;
  v12 = strTypeFullName->m_encodedStorage.RuntimeStringHandleMarker;
  v13 = 0;
  v60 = 0;
  strTypeName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&xstring_ptr_constants::c_xstring_ptr_storage_null;
  LODWORD(v58.m_encodedStorage.Storage) = 0;
  if ( (v12 & 1) != 0 )
  {
    v48 = (HSTRING)(v12 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v14 = *(_DWORD *)(v12 + 8);
    v15 = *(PCWSTR *)v12;
    if ( v14 >= 0 )
    {
      Storage = v14 & 0x3FFFFFFF;
      LODWORD(v58.m_encodedStorage.Storage) = Storage;
      goto LABEL_16;
    }
    v48 = *(HSTRING *)v12;
  }
  v15 = WindowsGetStringRawBuffer(v48, (UINT32 *)&v58);
  Storage = (int)v58.m_encodedStorage.Storage;
LABEL_16:
  if ( Storage )
  {
    for ( i = &v15[Storage - 1]; *i != 46; --i )
    {
      if ( i == v15 )
        goto LABEL_79;
    }
    v18 = i - v15;
  }
  else
  {
LABEL_79:
    LODWORD(v18) = -1;
  }
  v19 = strTypeFullName->m_encodedStorage.RuntimeStringHandleMarker;
  v20 = strTypeFullName->m_encodedStorage.RuntimeStringHandleMarker & 1;
  if ( (_DWORD)v18 == -1 )
  {
    if ( v20 )
    {
      LODWORD(v58.m_encodedStorage.Storage) = 0;
      strTypeName.m_ephemeralStorage.Buffer = WindowsGetStringRawBuffer(
                                                (HSTRING)(v19 & 0xFFFFFFFFFFFFFFFEuLL),
                                                (UINT32 *)&v58);
      v45 = (__int64)v58.m_encodedStorage.Storage & 0x3FFFFFFF;
    }
    else
    {
      strTypeName.m_ephemeralStorage.Buffer = *(const wchar_t **)v19;
      v45 = *(_DWORD *)(v19 + 8);
    }
    *((_DWORD *)&strTypeName.m_ephemeralStorage + 2) = v45 & 0x3FFFFFFF | 0x40000000;
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&strTypeName);
    goto LABEL_41;
  }
  if ( v20 )
  {
    v50 = (wchar_t *)(v19 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v21 = *(_DWORD *)(v19 + 8);
    if ( v21 >= 0 )
    {
      v22 = v21 & 0x3FFFFFFF;
      goto LABEL_26;
    }
    v50 = *(wchar_t **)v19;
  }
  v22 = WindowsGetStringLen((HSTRING)v50);
LABEL_26:
  v23 = strTypeFullName->m_encodedStorage.RuntimeStringHandleMarker;
  v24 = (unsigned int)(v18 + 1);
  LODWORD(v58.m_encodedStorage.Storage) = 0;
  if ( (v23 & 1) != 0 )
  {
    v49 = (HSTRING)(v23 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v25 = *(_DWORD *)(v23 + 8);
    v26 = *(PCWSTR *)v23;
    if ( v25 >= 0 )
    {
      v27 = v25 & 0x3FFFFFFF;
      LODWORD(v58.m_encodedStorage.Storage) = v27;
      goto LABEL_29;
    }
    v49 = *(HSTRING *)v23;
  }
  v26 = WindowsGetStringRawBuffer(v49, (UINT32 *)&v58);
  v27 = (unsigned int)v58.m_encodedStorage.Storage;
LABEL_29:
  if ( (unsigned int)v24 > v22 || v22 > v27 || (unsigned int)v24 > v27 )
  {
    xencoded_string_ptr::Reset((xruntime_string_ptr *)&strTypeName);
    v13 = v60;
    goto LABEL_42;
  }
  v28 = v22 - v24;
  v55 = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  if ( v28 > 0x3FFFFFFF )
  {
    pppStowedExceptions = 0;
    length = 0;
    TraceForFailFast(-2147418113);
    OnNewFailureEncountered(-2147418113, 0, 0);
    GetStowedExceptionsForFailFast(&pppStowedExceptions, &length);
    RoFailFastWithErrorContextInternal2(-2147418113, length, pppStowedExceptions);
    v1 = v55;
  }
  v29 = &v26[v24];
  v56 = v29;
  v30 = v28 & 0x3FFFFFFF | 0x40000000;
  v57 = v30;
  if ( ((unsigned __int8)v1 & 1) != 0 )
  {
    WindowsDeleteString((HSTRING)((unsigned __int64)v1 & 0xFFFFFFFFFFFFFFFEuLL));
    v29 = v56;
    v30 = v57;
  }
  v55 = (xstring_ptr_storage *)&v56;
  if ( ((unsigned __int8)&v56 & 1) != 0 )
  {
    length = 0;
    strTypeName.m_ephemeralStorage.Buffer = WindowsGetStringRawBuffer((HSTRING)&v56, &length);
    v30 = length & 0x3FFFFFFF;
  }
  else
  {
    strTypeName.m_ephemeralStorage.Buffer = v29;
  }
  *((_DWORD *)&strTypeName.m_ephemeralStorage + 2) = v30 & 0x3FFFFFFF | 0x40000000;
  if ( ((__int64)strTypeName.m_encodedStorage.Storage & 1) != 0 )
    WindowsDeleteString((HSTRING)(strTypeName.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL));
  v13 = v60;
LABEL_41:
  strTypeName.m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&strTypeName.m_ephemeralStorage;
LABEL_42:
  BuiltinClassInfoByName = DirectUI::MetadataAPI::GetBuiltinClassInfoByName(&strTypeName);
  if ( !BuiltinClassInfoByName || v10 )
  {
LABEL_49:
    v4 = 0;
    if ( v13 )
      goto LABEL_50;
    return BuiltinClassInfoByName;
  }
  v31 = strTypeFullName->m_encodedStorage.RuntimeStringHandleMarker;
  v13 = 1;
  if ( (strTypeFullName->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
  {
    v51 = (HSTRING)(v31 & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v32 = *(_DWORD *)(v31 + 8);
    if ( v32 >= 0 )
    {
      v33 = v32 & 0x3FFFFFFF;
      goto LABEL_47;
    }
    v51 = *(HSTRING *)v31;
  }
  v33 = WindowsGetStringLen(v51);
LABEL_47:
  if ( BuiltinClassInfoByName->m_nIndex < (XYFocusNavigationStrategy|IVectorOfUri) )
  {
    p_m_strFullNameStorage = &c_aTypeNameInfos[(unsigned __int16)BuiltinClassInfoByName->m_nIndex].m_strFullNameStorage;
    v58.m_encodedStorage.Storage = p_m_strFullNameStorage;
  }
  else
  {
    xstring_ptr::xstring_ptr(&v58, (const xstring_ptr *)&BuiltinClassInfoByName[4]);
    p_m_strFullNameStorage = v58.m_encodedStorage.Storage;
  }
  if ( ((unsigned __int8)p_m_strFullNameStorage & 1) != 0 )
  {
    Buffer = (HSTRING)((unsigned __int64)p_m_strFullNameStorage & 0xFFFFFFFFFFFFFFFEuLL);
  }
  else
  {
    v43 = *((_DWORD *)p_m_strFullNameStorage + 2);
    if ( v43 >= 0 )
    {
      v44 = v43 & 0x3FFFFFFF;
      goto LABEL_64;
    }
    Buffer = (HSTRING)p_m_strFullNameStorage->Buffer;
  }
  v44 = WindowsGetStringLen(Buffer);
LABEL_64:
  if ( v44 == v33 )
    goto LABEL_49;
LABEL_50:
  xstring_ptr::~xstring_ptr(&v58);
  if ( !v4 )
    return BuiltinClassInfoByName;
  return 0;
}

```

## disassembly

```asm
0x1800d1f5c  push    rbp
0x1800d1f5e  push    rbx
0x1800d1f5f  push    rsi
0x1800d1f60  push    rdi
0x1800d1f61  push    r12
0x1800d1f63  push    r13
0x1800d1f65  push    r14
0x1800d1f67  push    r15
0x1800d1f69  mov     rbp, rsp
0x1800d1f6c  sub     rsp, 68h
0x1800d1f70  mov     dword ptr [rbp+arg_0.m_encodedStorage.___u0], 0
0x1800d1f77  lea     rbx, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800d1f7e  xor     r15d, r15d
0x1800d1f81  mov     qword ptr [rbp+strTypeName.m_encodedStorage.___u0], rbx
0x1800d1f85  lea     rax, aWindows_0; "Windows."
0x1800d1f8c  mov     dword ptr [rbp+strTypeName.m_ephemeralStorage.Count], 40000008h
0x1800d1f93  mov     r12, strTypeFullName
0x1800d1f96  mov     qword ptr [rbp+strTypeName.m_ephemeralStorage.___u0], rax
0x1800d1f9a  lea     esi, [r15+1]
0x1800d1f9e  test    sil, bl
0x1800d1fa1  jz      short loc_1800D1FB0
0x1800d1fa3  mov     strTypeFullName, rbx
0x1800d1fa6  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d1faa  call    cs:__imp_WindowsDeleteString
0x1800d1fb0  mov     strTypeFullName, [r12]
0x1800d1fb4  lea     rax, [rbp+strTypeName.m_ephemeralStorage]
0x1800d1fb8  mov     qword ptr [rbp+strTypeName.m_encodedStorage.___u0], rax
0x1800d1fbc  mov     r13d, 3FFFFFFFh
0x1800d1fc2  test    sil, cl
0x1800d1fc5  jnz     loc_1800D22FB
0x1800d1fcb  mov     edi, [strTypeFullName+8]
0x1800d1fce  test    edi, edi
0x1800d1fd0  js      loc_1800D2405
0x1800d1fd6  and     edi, r13d
0x1800d1fd9  mov     strTypeFullName, qword ptr [rbp+strTypeName.m_encodedStorage.___u0]
0x1800d1fdd  test    sil, cl
0x1800d1fe0  jnz     loc_1800D230C
0x1800d1fe6  mov     eax, [strTypeFullName+8]
0x1800d1fe9  test    eax, eax
0x1800d1feb  js      loc_1800D240D
0x1800d1ff1  and     eax, r13d
0x1800d1ff4  cmp     edi, eax
0x1800d1ff6  jb      loc_1800D2209
0x1800d1ffc  mov     r9d, eax; cchCompare
0x1800d1fff  mov     [rsp+68h+eCompareBehavior], r15d; eCompareBehavior
0x1800d2004  xor     r8d, r8d; ichStartingIndex
0x1800d2007  lea     rdx, [rbp+strTypeName]; other
0x1800d200b  mov     strTypeFullName, r12; this
0x1800d200e  xor     r13b, r13b
0x1800d2011  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@IIW4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,uint,uint,xstrCompareBehavior)
0x1800d2016  test    eax, eax
0x1800d2018  jnz     loc_1800D2203
0x1800d201e  mov     al, sil
0x1800d2021  test    al, al
0x1800d2023  jz      loc_1800D21EF
0x1800d2029  mov     strTypeFullName, [r12]
0x1800d202d  xor     edi, edi
0x1800d202f  mov     [rbp+arg_10], edi
0x1800d2032  mov     qword ptr [rbp+strTypeName.m_encodedStorage.___u0], rbx
0x1800d2036  mov     dword ptr [rbp+arg_0.m_encodedStorage.___u0], edi
0x1800d2039  test    sil, cl
0x1800d203c  jnz     loc_1800D231B
0x1800d2042  mov     eax, [strTypeFullName+8]
0x1800d2045  mov     r8, [strTypeFullName]
0x1800d2048  test    eax, eax
0x1800d204a  js      loc_1800D23F5
0x1800d2050  and     eax, 3FFFFFFFh
0x1800d2055  mov     dword ptr [rbp+arg_0.m_encodedStorage.___u0], eax
0x1800d2058  test    eax, eax
0x1800d205a  jz      loc_1800D235E
0x1800d2060  dec     eax
0x1800d2062  lea     r14, [r8+rax*2]
0x1800d2066  mov     eax, 2Eh ; '.'
0x1800d206b  cmp     [r14], ax
0x1800d206f  jz      short loc_1800D2080
0x1800d2071  cmp     r14, r8
0x1800d2074  jz      loc_1800D235E
0x1800d207a  sub     r14, 2
0x1800d207e  jmp     short loc_1800D206B
0x1800d2080  sub     r14, r8
0x1800d2083  sar     r14, 1
0x1800d2086  mov     strTypeFullName, [r12]
0x1800d208a  mov     rax, strTypeFullName
0x1800d208d  and     rax, rsi
0x1800d2090  cmp     r14d, 0FFFFFFFFh
0x1800d2094  jz      loc_1800D22CE
0x1800d209a  test    rax, rax
0x1800d209d  jnz     loc_1800D234D
0x1800d20a3  mov     edi, [strTypeFullName+8]
0x1800d20a6  test    edi, edi
0x1800d20a8  js      loc_1800D241D
0x1800d20ae  and     edi, 3FFFFFFFh
0x1800d20b4  mov     strTypeFullName, [r12]
0x1800d20b8  inc     r14d
0x1800d20bb  mov     dword ptr [rbp+arg_0.m_encodedStorage.___u0], r15d
0x1800d20bf  test    sil, cl
0x1800d20c2  jnz     loc_1800D2334
0x1800d20c8  mov     eax, [strTypeFullName+8]
0x1800d20cb  mov     r15, [strTypeFullName]
0x1800d20ce  test    eax, eax
0x1800d20d0  js      loc_1800D23FD
0x1800d20d6  and     eax, 3FFFFFFFh
0x1800d20db  mov     dword ptr [rbp+arg_0.m_encodedStorage.___u0], eax
0x1800d20de  cmp     r14d, edi
0x1800d20e1  ja      loc_1800D2272
0x1800d20e7  cmp     edi, eax
0x1800d20e9  ja      loc_1800D2272
0x1800d20ef  cmp     r14d, eax
0x1800d20f2  ja      loc_1800D2272
0x1800d20f8  sub     edi, r14d
0x1800d20fb  mov     [rbp+var_20], rbx
0x1800d20ff  cmp     edi, 3FFFFFFFh
0x1800d2105  ja      loc_1800D2435
0x1800d210b  lea     strTypeFullName, [r15+r14*2]
0x1800d210f  and     edi, 3FFFFFFFh
0x1800d2115  mov     r14d, 40000000h
0x1800d211b  mov     [rbp+var_18], strTypeFullName
0x1800d211f  or      edi, r14d
0x1800d2122  mov     [rbp+var_10], edi
0x1800d2125  test    sil, bl
0x1800d2128  jz      short loc_1800D213E
0x1800d212a  and     rbx, 0FFFFFFFFFFFFFFFEh
0x1800d212e  mov     strTypeFullName, rbx; string
0x1800d2131  call    cs:__imp_WindowsDeleteString
0x1800d2137  mov     strTypeFullName, [rbp+var_18]
0x1800d213b  mov     edi, [rbp+var_10]
0x1800d213e  lea     rax, [rbp+var_18]
0x1800d2142  mov     [rbp+var_20], rax
0x1800d2146  lea     rax, [rbp+var_18]
0x1800d214a  test    sil, al
0x1800d214d  jnz     loc_1800D23A8
0x1800d2153  mov     qword ptr [rbp+strTypeName.m_ephemeralStorage.___u0], strTypeFullName
0x1800d2157  mov     strTypeFullName, qword ptr [rbp+strTypeName.m_encodedStorage.___u0]
0x1800d215b  and     edi, 3FFFFFFFh
0x1800d2161  or      edi, r14d
0x1800d2164  mov     dword ptr [rbp+strTypeName.m_ephemeralStorage.Count], edi
0x1800d2167  test    sil, cl
0x1800d216a  jnz     loc_1800D2283
0x1800d2170  mov     edi, [rbp+arg_10]
0x1800d2173  lea     rax, [rbp+strTypeName.m_ephemeralStorage]
0x1800d2177  mov     qword ptr [rbp+strTypeName.m_encodedStorage.___u0], rax
0x1800d217b  lea     strTypeFullName, [rbp+strTypeName]; strTypeName
0x1800d217f  call    ?GetBuiltinClassInfoByName@MetadataAPI@DirectUI@@SAPEBVCClassInfo@@AEBVxstring_ptr_view@@@Z; DirectUI::MetadataAPI::GetBuiltinClassInfoByName(xstring_ptr_view const &)
0x1800d2184  mov     r15, rax
0x1800d2187  test    rax, rax
0x1800d218a  jz      short loc_1800D21D6
0x1800d218c  test    r13b, r13b
0x1800d218f  jnz     short loc_1800D21D6
0x1800d2191  mov     strTypeFullName, [r12]
0x1800d2195  mov     edi, esi
0x1800d2197  test    sil, cl
0x1800d219a  jnz     loc_1800D236F
0x1800d21a0  mov     ebx, [strTypeFullName+8]
0x1800d21a3  test    ebx, ebx
0x1800d21a5  js      loc_1800D2425
0x1800d21ab  and     ebx, 3FFFFFFFh
0x1800d21b1  mov     eax, 43Ch
0x1800d21b6  cmp     [r15], ax
0x1800d21ba  jb      loc_1800D2292
0x1800d21c0  lea     rdx, [r15+20h]; other
0x1800d21c4  lea     strTypeFullName, [rbp+arg_0]; this
0x1800d21c8  call    ??0xstring_ptr@@QEAA@AEBV0@@Z; xstring_ptr::xstring_ptr(xstring_ptr const &)
0x1800d21cd  mov     strTypeFullName, qword ptr [rbp+arg_0.m_encodedStorage.___u0]
0x1800d21d1  jmp     loc_1800D22A8
0x1800d21d6  xor     sil, sil
0x1800d21d9  test    edi, edi
0x1800d21db  jz      short loc_1800D21EF
0x1800d21dd  lea     strTypeFullName, [rbp+arg_0]; this
0x1800d21e1  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800d21e6  test    sil, sil
0x1800d21e9  jnz     loc_1800D2481
0x1800d21ef  mov     rax, r15
0x1800d21f2  add     rsp, 68h
0x1800d21f6  pop     r15
0x1800d21f8  pop     r14
0x1800d21fa  pop     r13
0x1800d21fc  pop     r12
0x1800d21fe  pop     rdi
0x1800d21ff  pop     rsi
0x1800d2200  pop     rbx
0x1800d2201  pop     rbp
0x1800d2202  retn
0x1800d2203  mov     r13d, 3FFFFFFFh
0x1800d2209  mov     strTypeFullName, [r12]
0x1800d220d  mov     dword ptr [rbp+arg_0.m_encodedStorage.___u0], r15d
0x1800d2211  test    sil, cl
0x1800d2214  jnz     loc_1800D238F
0x1800d221a  mov     eax, [strTypeFullName+8]
0x1800d221d  mov     r14, [strTypeFullName]
0x1800d2220  test    eax, eax
0x1800d2222  js      loc_1800D2415
0x1800d2228  and     eax, r13d
0x1800d222b  mov     dword ptr [rbp+arg_0.m_encodedStorage.___u0], eax
0x1800d222e  test    eax, eax
0x1800d2230  jz      loc_1800D2367
0x1800d2236  lea     rdi, [r14+rax*2]
0x1800d223a  mov     r8d, 2Eh ; '.'; _Val
0x1800d2240  mov     rdx, rdi; _Last
0x1800d2243  mov     strTypeFullName, r14; _First
0x1800d2246  call    __std_find_trivial_2
0x1800d224b  cmp     rax, rdi
0x1800d224e  jz      loc_1800D2367
0x1800d2254  sub     rax, r14
0x1800d2257  or      r14d, 0FFFFFFFFh
0x1800d225b  sar     rax, 1
0x1800d225e  cmp     eax, r14d
0x1800d2261  setz    r13b
0x1800d2265  jz      loc_1800D201E
0x1800d226b  xor     al, al
0x1800d226d  jmp     loc_1800D2021
0x1800d2272  lea     strTypeFullName, [rbp+strTypeName]; this
0x1800d2276  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800d227b  mov     edi, [rbp+arg_10]
0x1800d227e  jmp     loc_1800D217B
0x1800d2283  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d2287  call    cs:__imp_WindowsDeleteString
0x1800d228d  jmp     loc_1800D2170
0x1800d2292  movzx   eax, word ptr [r15]
0x1800d2296  imul    strTypeFullName, rax, 1Ch
0x1800d229a  lea     rax, ?c_aTypeNameInfos@@3QBUMetaDataTypeNameInfo@@B.m_strFullNameStorage; MetaDataTypeNameInfo const near * const c_aTypeNameInfos ...
0x1800d22a1  add     strTypeFullName, rax
0x1800d22a4  mov     qword ptr [rbp+arg_0.m_encodedStorage.___u0], strTypeFullName
0x1800d22a8  test    sil, cl
0x1800d22ab  jnz     loc_1800D2380
0x1800d22b1  mov     eax, [strTypeFullName+8]
0x1800d22b4  test    eax, eax
0x1800d22b6  js      loc_1800D242D
0x1800d22bc  and     eax, 3FFFFFFFh
0x1800d22c1  cmp     eax, ebx
0x1800d22c3  jnz     loc_1800D21DD
0x1800d22c9  jmp     loc_1800D21D6
0x1800d22ce  test    rax, rax
0x1800d22d1  jnz     loc_1800D23D3
0x1800d22d7  mov     rax, [strTypeFullName]
0x1800d22da  mov     qword ptr [rbp+strTypeName.m_ephemeralStorage.___u0], rax
0x1800d22de  mov     eax, [strTypeFullName+8]
0x1800d22e1  and     eax, 3FFFFFFFh
0x1800d22e6  lea     strTypeFullName, [rbp+strTypeName]; this
0x1800d22ea  bts     eax, 1Eh
0x1800d22ee  mov     dword ptr [rbp+strTypeName.m_ephemeralStorage.Count], eax
0x1800d22f1  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800d22f6  jmp     loc_1800D2173
0x1800d22fb  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d22ff  call    cs:__imp_WindowsGetStringLen
0x1800d2305  mov     edi, eax
0x1800d2307  jmp     loc_1800D1FD9
0x1800d230c  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d2310  call    cs:__imp_WindowsGetStringLen
0x1800d2316  jmp     loc_1800D1FF4
0x1800d231b  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d231f  lea     rdx, [rbp+arg_0]; length
0x1800d2323  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d2329  mov     r8, rax
0x1800d232c  mov     eax, dword ptr [rbp+arg_0.m_encodedStorage.___u0]
0x1800d232f  jmp     loc_1800D2058
0x1800d2334  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d2338  lea     rdx, [rbp+arg_0]; length
0x1800d233c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d2342  mov     r15, rax
0x1800d2345  mov     eax, dword ptr [rbp+arg_0.m_encodedStorage.___u0]
0x1800d2348  jmp     loc_1800D20DE
0x1800d234d  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d2351  call    cs:__imp_WindowsGetStringLen
0x1800d2357  mov     edi, eax
0x1800d2359  jmp     loc_1800D20B4
0x1800d235e  or      r14d, 0FFFFFFFFh
0x1800d2362  jmp     loc_1800D2086
0x1800d2367  mov     r13b, sil
0x1800d236a  jmp     loc_1800D201E
0x1800d236f  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d2373  call    cs:__imp_WindowsGetStringLen
0x1800d2379  mov     ebx, eax
0x1800d237b  jmp     loc_1800D21B1
0x1800d2380  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d2384  call    cs:__imp_WindowsGetStringLen
0x1800d238a  jmp     loc_1800D22C1
0x1800d238f  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d2393  lea     rdx, [rbp+arg_0]; length
0x1800d2397  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d239d  mov     r14, rax
0x1800d23a0  mov     eax, dword ptr [rbp+arg_0.m_encodedStorage.___u0]
0x1800d23a3  jmp     loc_1800D222E
0x1800d23a8  lea     strTypeFullName, [rbp+var_18]
0x1800d23ac  mov     [rbp+length], 0
0x1800d23b3  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d23b7  lea     rdx, [rbp+length]; length
0x1800d23bb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d23c1  mov     edi, [rbp+length]
0x1800d23c4  mov     qword ptr [rbp+strTypeName.m_ephemeralStorage.___u0], rax
0x1800d23c8  and     edi, 3FFFFFFFh
0x1800d23ce  jmp     loc_1800D2157
0x1800d23d3  and     strTypeFullName, 0FFFFFFFFFFFFFFFEh; string
0x1800d23d7  mov     dword ptr [rbp+arg_0.m_encodedStorage.___u0], edi
0x1800d23da  lea     rdx, [rbp+arg_0]; length
0x1800d23de  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d23e4  mov     qword ptr [rbp+strTypeName.m_ephemeralStorage.___u0], rax
0x1800d23e8  mov     eax, dword ptr [rbp+arg_0.m_encodedStorage.___u0]
0x1800d23eb  and     eax, 3FFFFFFFh
0x1800d23f0  jmp     loc_1800D22E1
0x1800d23f5  mov     strTypeFullName, r8
  ... truncated ...
```
