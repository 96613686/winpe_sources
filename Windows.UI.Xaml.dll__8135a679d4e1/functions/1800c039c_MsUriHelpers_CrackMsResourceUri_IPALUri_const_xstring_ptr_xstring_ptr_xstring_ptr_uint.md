# MsUriHelpers::CrackMsResourceUri(IPALUri const *,xstring_ptr *,xstring_ptr *,xstring_ptr *,uint *)

- ea: `0x1800c039c`
- end: `0x1800c09c6`
- name: `?CrackMsResourceUri@MsUriHelpers@@YAJPEBUIPALUri@@PEAVxstring_ptr@@11PEAI@Z`
- size: `1578`
- prototype: `HRESULT __fastcall(const IPALUri *pUri, xstring_ptr *pstrResourceMap, xstring_ptr *pstrResourcePath, xstring_ptr *pstrFilePath, unsigned int *pHadFilePath)`
- caller_count: `5`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180171860`
- `0x180172488`
- `0x1801e0a40`
- `0x18055ecf0`
- `0x1808456f0`

## callees

- `0x180004bc0`
- `0x180044930`
- `0x1800af8e0`
- `0x1800c039c`
- `0x1800c09d0`
- `0x1800c09f8`
- `0x1800c1484`
- `0x1800d2524`
- `0x1800fdd4c`
- `0x1800fe130`
- `0x18069f6ac`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800c0577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800c064f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800c0577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800c064f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c07ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c07ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800c0977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c08af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c08db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c08af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c08db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c08f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0885`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c08f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800c0905`

## pseudocode

```c
__int64 __fastcall MsUriHelpers::CrackMsResourceUri(
        IPALUri *pUri,
        xstring_ptr *pstrResourceMap,
        xruntime_string_ptr *pstrResourcePath,
        xruntime_string_ptr *pstrFilePath,
        unsigned int *pHadFilePath)
{
  xephemeral_string_ptr *v5; // rbx
  unsigned int v9; // r15d
  __int64 v10; // rdi
  int v11; // eax
  int v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // ecx
  unsigned int v15; // edi
  __int64 v16; // rbx
  wchar_t *m_pBuffer; // rdx
  unsigned int m_cBuffer; // eax
  int v19; // eax
  IPALUri_vtbl *v20; // rax
  HRESULT v21; // eax
  HRESULT v22; // ecx
  __int64 v23; // rbx
  wchar_t *m_inlineBuffer; // rcx
  int v25; // eax
  IPALUri_vtbl *v26; // rax
  __int64 v27; // r12
  const xstring_ptr_storage *Storage; // rbx
  unsigned __int64 i; // r14
  xephemeral_string_ptr *v30; // r15
  int v31; // esi
  UINT32 StringLen; // esi
  unsigned __int64 RuntimeStringHandleMarker; // rcx
  int v34; // eax
  unsigned int v35; // eax
  int v36; // ebx
  unsigned int v37; // ebx
  unsigned __int64 v38; // rcx
  int v39; // eax
  unsigned int v40; // eax
  HRESULT v41; // eax
  xstring_ptr **p_pstrDetachedString; // rbx
  HSTRING Buffer; // rcx
  HSTRING v45; // rcx
  HSTRING v46; // rcx
  HSTRING v47; // rcx
  unsigned int bufferLength; // [rsp+30h] [rbp-D0h] BYREF
  xstring_ptr strResourcePath; // [rsp+38h] [rbp-C8h] BYREF
  xruntime_string_ptr v50; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v51; // [rsp+48h] [rbp-B8h] BYREF
  int v52; // [rsp+50h] [rbp-B0h]
  xruntime_string_ptr v53; // [rsp+54h] [rbp-ACh] BYREF
  const wchar_t *v54; // [rsp+5Ch] [rbp-A4h] BYREF
  int v55; // [rsp+64h] [rbp-9Ch]
  xephemeral_string_ptr strPathPrefixes[2]; // [rsp+68h] [rbp-98h] BYREF
  xstring_ptr *pstrDetachedString; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v58; // [rsp+98h] [rbp-68h]
  TStringBuilder<96> stringBuilder; // [rsp+A0h] [rbp-60h] BYREF

  stringBuilder.m_pBuffer = stringBuilder.m_inlineBuffer;
  v5 = strPathPrefixes;
  pstrDetachedString = pstrResourceMap;
  v58 = pHadFilePath;
  stringBuilder.m_hPreallocatedBuffer = 0;
  bufferLength = 0;
  v9 = 96;
  *(_QWORD *)&stringBuilder.m_cBuffer = 96;
  v10 = 2;
  do
  {
    xstring_ptr::xstring_ptr(v5++);
    --v10;
  }
  while ( v10 );
  v52 = 1073741830;
  v50.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  v51 = L"Files/";
  xencoded_string_ptr::Reset(&v50);
  v50.m_encodedStorage.Storage = (const xstring_ptr_storage *)&v51;
  if ( ((unsigned __int8)&v51 & 1) != 0 )
  {
    LODWORD(strResourcePath.m_encodedStorage.Storage) = 0;
    strPathPrefixes[0].m_ephemeralStorage.Buffer = WindowsGetStringRawBuffer((HSTRING)&v51, (UINT32 *)&strResourcePath);
    v11 = (__int64)strResourcePath.m_encodedStorage.Storage & 0x3FFFFFFF;
  }
  else
  {
    strPathPrefixes[0].m_ephemeralStorage.Buffer = v51;
    v11 = v52;
  }
  *((_DWORD *)&strPathPrefixes[0].m_ephemeralStorage + 2) = v11 & 0x3FFFFFFF | 0x40000000;
  xencoded_string_ptr::Reset((xruntime_string_ptr *)strPathPrefixes);
  v55 = 1073741831;
  strPathPrefixes[0].m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&strPathPrefixes[0].m_ephemeralStorage;
  v53.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  v54 = L"/Files/";
  xencoded_string_ptr::Reset(&v53);
  v53.m_encodedStorage.Storage = (const xstring_ptr_storage *)&v54;
  if ( ((unsigned __int8)&v54 & 1) != 0 )
  {
    LODWORD(strResourcePath.m_encodedStorage.Storage) = 0;
    strPathPrefixes[1].m_ephemeralStorage.Buffer = WindowsGetStringRawBuffer((HSTRING)&v54, (UINT32 *)&strResourcePath);
    v12 = (__int64)strResourcePath.m_encodedStorage.Storage & 0x3FFFFFFF;
  }
  else
  {
    strPathPrefixes[1].m_ephemeralStorage.Buffer = v54;
    v12 = v55;
  }
  *((_DWORD *)&strPathPrefixes[1].m_ephemeralStorage + 2) = v12 & 0x3FFFFFFF | 0x40000000;
  xencoded_string_ptr::Reset((xruntime_string_ptr *)&strPathPrefixes[1]);
  strPathPrefixes[1].m_encodedStorage.RuntimeStringHandleMarker = (unsigned __int64)&strPathPrefixes[1].m_ephemeralStorage;
  if ( pstrResourcePath )
    xencoded_string_ptr::Reset(pstrResourcePath);
  if ( pstrFilePath )
    xencoded_string_ptr::Reset(pstrFilePath);
  if ( pHadFilePath )
    *pHadFilePath = 0;
  v13 = pUri->GetHost(pUri, &bufferLength, 0);
  v15 = v13;
  if ( v13 < 0 )
    goto LABEL_93;
  v16 = bufferLength + 1;
  bufferLength = v16;
  if ( (unsigned int)(v16 + 1) >= 0x7FFFFF9F )
  {
    v15 = -2147418113;
    OnNewFailure_2955_(v14);
    goto LABEL_65;
  }
  m_pBuffer = stringBuilder.m_pBuffer;
  if ( stringBuilder.m_pBuffer == stringBuilder.m_inlineBuffer )
  {
    m_cBuffer = stringBuilder.m_cBuffer;
  }
  else
  {
    WindowsDeleteStringBuffer(stringBuilder.m_hPreallocatedBuffer);
    m_pBuffer = stringBuilder.m_inlineBuffer;
    stringBuilder.m_hPreallocatedBuffer = 0;
    m_cBuffer = 96;
    stringBuilder.m_pBuffer = stringBuilder.m_inlineBuffer;
    stringBuilder.m_cBuffer = 96;
  }
  if ( (int)v16 + 2 > m_cBuffer )
  {
    v19 = WindowsPreallocateStringBuffer(v16 + 1, &stringBuilder.m_pBuffer, &stringBuilder.m_hPreallocatedBuffer);
    v15 = v19;
    if ( v19 >= 0 )
    {
      m_pBuffer = stringBuilder.m_pBuffer;
      stringBuilder.m_cBuffer = v16 + 2;
      goto LABEL_20;
    }
    OnFailure_2990_(v19);
LABEL_65:
    OnFailure_2990_(v15);
    OnFailure_2990_(v15);
LABEL_66:
    v27 = 2;
    goto $Cleanup_372;
  }
LABEL_20:
  m_pBuffer[v16] = 0;
  v20 = pUri->__vftable;
  stringBuilder.m_cActual = v16;
  v13 = v20->GetHost(pUri, &bufferLength, stringBuilder.m_pBuffer);
  v15 = v13;
  if ( v13 < 0
    || (stringBuilder.m_cActual = bufferLength,
        v13 = TStringBuilder<96>::DetachString(&stringBuilder, pstrDetachedString),
        v15 = v13,
        v13 < 0) )
  {
LABEL_93:
    OnFailure_2990_(v13);
    goto LABEL_66;
  }
  if ( !pstrResourcePath && !pstrFilePath )
    goto LABEL_66;
  strResourcePath.m_encodedStorage.Storage = &xstring_ptr_constants::c_xstring_ptr_storage_null;
  v21 = pUri->GetPath(pUri, &bufferLength, 0);
  v15 = v21;
  if ( v21 < 0 )
    goto LABEL_92;
  v23 = bufferLength + 1;
  bufferLength = v23;
  if ( (unsigned int)(v23 + 1) >= 0x7FFFFF9F )
  {
    v15 = -2147418113;
    OnNewFailure_2955_(v22);
    goto LABEL_68;
  }
  m_inlineBuffer = stringBuilder.m_pBuffer;
  if ( stringBuilder.m_pBuffer == stringBuilder.m_inlineBuffer )
  {
    v9 = stringBuilder.m_cBuffer;
  }
  else
  {
    WindowsDeleteStringBuffer(stringBuilder.m_hPreallocatedBuffer);
    m_inlineBuffer = stringBuilder.m_inlineBuffer;
    stringBuilder.m_hPreallocatedBuffer = 0;
    stringBuilder.m_pBuffer = stringBuilder.m_inlineBuffer;
    stringBuilder.m_cBuffer = 96;
  }
  if ( (int)v23 + 2 > v9 )
  {
    v25 = WindowsPreallocateStringBuffer(v23 + 1, &stringBuilder.m_pBuffer, &stringBuilder.m_hPreallocatedBuffer);
    v15 = v25;
    if ( v25 >= 0 )
    {
      m_inlineBuffer = stringBuilder.m_pBuffer;
      stringBuilder.m_cBuffer = v23 + 2;
      goto LABEL_30;
    }
    OnFailure_2990_(v25);
LABEL_68:
    OnFailure_2990_(v15);
    OnFailure_2990_(v15);
LABEL_69:
    xstring_ptr::~xstring_ptr(&strResourcePath);
    goto LABEL_66;
  }
LABEL_30:
  m_inlineBuffer[v23] = 0;
  v26 = pUri->__vftable;
  stringBuilder.m_cActual = v23;
  v21 = v26->GetPath(pUri, &bufferLength, stringBuilder.m_pBuffer);
  v15 = v21;
  if ( v21 < 0
    || (stringBuilder.m_cActual = bufferLength,
        v21 = TStringBuilder<96>::DetachString(&stringBuilder, &strResourcePath),
        v15 = v21,
        v21 < 0) )
  {
LABEL_92:
    OnFailure_2990_(v21);
    goto LABEL_69;
  }
  if ( pstrResourcePath )
    xstring_ptr::operator=((xstring_ptr *)pstrResourcePath, &strResourcePath);
  v27 = 2;
  if ( pstrFilePath )
  {
    Storage = strResourcePath.m_encodedStorage.Storage;
    for ( i = 0; i < 2; ++i )
    {
      v30 = &strPathPrefixes[i];
      if ( ((unsigned __int8)Storage & 1) != 0 )
      {
        Buffer = (HSTRING)((unsigned __int64)Storage & 0xFFFFFFFFFFFFFFFEuLL);
      }
      else
      {
        v31 = *((_DWORD *)Storage + 2);
        if ( v31 >= 0 )
        {
          StringLen = v31 & 0x3FFFFFFF;
          goto LABEL_40;
        }
        Buffer = (HSTRING)Storage->Buffer;
      }
      StringLen = WindowsGetStringLen(Buffer);
LABEL_40:
      RuntimeStringHandleMarker = v30->m_encodedStorage.RuntimeStringHandleMarker;
      if ( (v30->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
      {
        v45 = (HSTRING)(RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
      }
      else
      {
        v34 = *(_DWORD *)(RuntimeStringHandleMarker + 8);
        if ( v34 >= 0 )
        {
          v35 = v34 & 0x3FFFFFFF;
          goto LABEL_43;
        }
        v45 = *(HSTRING *)RuntimeStringHandleMarker;
      }
      v35 = WindowsGetStringLen(v45);
LABEL_43:
      if ( StringLen >= v35 )
      {
        if ( !xstring_ptr_view::Compare(&strResourcePath, &strPathPrefixes[i], 0, v35, xstrCompareCaseInsensitive) )
        {
          _mm_lfence();
          if ( ((__int64)strResourcePath.m_encodedStorage.Storage & 1) != 0 )
          {
            v46 = (HSTRING)(strResourcePath.m_encodedStorage.RuntimeStringHandleMarker & 0xFFFFFFFFFFFFFFFEuLL);
          }
          else
          {
            v36 = *((_DWORD *)strResourcePath.m_encodedStorage.Storage + 2);
            if ( v36 >= 0 )
            {
              v37 = v36 & 0x3FFFFFFF;
              goto LABEL_50;
            }
            v46 = *(HSTRING *)strResourcePath.m_encodedStorage.Handle;
          }
          v37 = WindowsGetStringLen(v46);
LABEL_50:
          v38 = v30->m_encodedStorage.RuntimeStringHandleMarker;
          if ( (v30->m_encodedStorage.RuntimeStringHandleMarker & 1) != 0 )
          {
            v47 = (HSTRING)(v38 & 0xFFFFFFFFFFFFFFFEuLL);
          }
          else
          {
            v39 = *(_DWORD *)(v38 + 8);
            if ( v39 >= 0 )
            {
              v40 = v39 & 0x3FFFFFFF;
              goto LABEL_53;
            }
            v47 = *(HSTRING *)v38;
          }
          v40 = WindowsGetStringLen(v47);
LABEL_53:
          v41 = xstring_ptr_view::SubString(&strResourcePath, v40, v37, (xstring_ptr *)pstrFilePath);
          v15 = v41;
          if ( v41 < 0 )
          {
            OnFailure_2990_(v41);
          }
          else if ( v58 )
          {
            *v58 = 1;
          }
          break;
        }
        Storage = strResourcePath.m_encodedStorage.Storage;
      }
    }
  }
  xstring_ptr::~xstring_ptr(&strResourcePath);
$Cleanup_372:
  p_pstrDetachedString = &pstrDetachedString;
  do
  {
    p_pstrDetachedString = (xstring_ptr **)((char *)p_pstrDetachedString - 20);
    xephemeral_string_ptr::~xephemeral_string_ptr((xephemeral_string_ptr *)p_pstrDetachedString);
    --v27;
  }
  while ( v27 );
  if ( stringBuilder.m_pBuffer != stringBuilder.m_inlineBuffer )
    WindowsDeleteStringBuffer(stringBuilder.m_hPreallocatedBuffer);
  return v15;
}

```

## disassembly

```asm
0x1800c039c  push    rbp
0x1800c039e  push    rbx
0x1800c039f  push    rsi
0x1800c03a0  push    rdi
0x1800c03a1  push    r12
0x1800c03a3  push    r13
0x1800c03a5  push    r14
0x1800c03a7  push    r15
0x1800c03a9  lea     rbp, [rsp-98h]
0x1800c03b1  sub     rsp, 198h
0x1800c03b8  mov     rax, cs:__security_cookie
0x1800c03bf  xor     rax, rsp
0x1800c03c2  mov     [rbp+0D0h+var_50], rax
0x1800c03c9  mov     rsi, [rbp+0D0h+arg_20]
0x1800c03d0  lea     rax, [rbp+0D0h+stringBuilder.m_inlineBuffer]
0x1800c03d4  mov     [rbp+0D0h+stringBuilder.m_pBuffer], rax
0x1800c03d8  lea     rbx, [rsp+1D0h+strPathPrefixes]
0x1800c03dd  xor     eax, eax
0x1800c03df  mov     [rbp+0D0h+pstrDetachedString], pstrResourceMap
0x1800c03e3  mov     r13, pstrFilePath
0x1800c03e6  mov     [rbp+0D0h+var_138], rsi
0x1800c03ea  mov     r14, pstrResourcePath
0x1800c03ed  mov     [rbp+0D0h+stringBuilder.m_hPreallocatedBuffer], rax
0x1800c03f1  mov     r12, pUri
0x1800c03f4  mov     [rsp+1D0h+bufferLength], eax
0x1800c03f8  lea     r15d, [rax+60h]
0x1800c03fc  mov     qword ptr [rbp+0D0h+stringBuilder.m_cBuffer], r15
0x1800c0400  lea     edi, [rax+2]
0x1800c0403  mov     pUri, rbx; this
0x1800c0406  call    ??0xstring_ptr@@QEAA@XZ; xstring_ptr::xstring_ptr(void)
0x1800c040b  add     rbx, 14h
0x1800c040f  sub     rdi, 1
0x1800c0413  jnz     short loc_1800C0403
0x1800c0415  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800c041c  mov     [rsp+1D0h+var_180], 40000006h
0x1800c0424  mov     qword ptr [rsp+1D0h+var_190.m_encodedStorage.___u0], rax
0x1800c0429  lea     pUri, [rsp+1D0h+var_190]; this
0x1800c042e  lea     rax, aFiles_1; "Files/"
0x1800c0435  mov     [rsp+1D0h+var_188], rax
0x1800c043a  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800c043f  lea     rax, [rsp+1D0h+var_188]
0x1800c0444  mov     ebx, 3FFFFFFFh
0x1800c0449  mov     qword ptr [rsp+1D0h+var_190.m_encodedStorage.___u0], rax
0x1800c044e  lea     rax, [rsp+1D0h+var_188]
0x1800c0453  test    al, 1
0x1800c0455  jnz     loc_1800C0899
0x1800c045b  mov     rax, [rsp+1D0h+var_188]
0x1800c0460  mov     qword ptr [rsp+1D0h+strPathPrefixes.m_ephemeralStorage.___u0], rax
0x1800c0465  mov     eax, [rsp+1D0h+var_180]
0x1800c0469  and     eax, ebx
0x1800c046b  lea     pUri, [rsp+1D0h+strPathPrefixes]; this
0x1800c0470  mov     edi, 40000000h
0x1800c0475  or      eax, edi
0x1800c0477  mov     dword ptr [rsp+1D0h+strPathPrefixes.m_ephemeralStorage.Count], eax
0x1800c047b  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800c0480  lea     rax, [rsp+1D0h+strPathPrefixes.m_ephemeralStorage]
0x1800c0485  mov     [rsp+1D0h+var_16C], 40000007h
0x1800c048d  mov     qword ptr [rsp+1D0h+strPathPrefixes.m_encodedStorage.___u0], rax
0x1800c0492  lea     pUri, [rsp+1D0h+var_17C]; this
0x1800c0497  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800c049e  mov     qword ptr [rsp+1D0h+var_17C.m_encodedStorage.___u0], rax
0x1800c04a3  lea     rax, aFiles_2; "/Files/"
0x1800c04aa  mov     [rsp+1D0h+var_174], rax
0x1800c04af  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800c04b4  lea     rax, [rsp+1D0h+var_174]
0x1800c04b9  mov     qword ptr [rsp+1D0h+var_17C.m_encodedStorage.___u0], rax
0x1800c04be  lea     rax, [rsp+1D0h+var_174]
0x1800c04c3  test    al, 1
0x1800c04c5  jnz     loc_1800C08C5
0x1800c04cb  mov     rax, [rsp+1D0h+var_174]
0x1800c04d0  mov     qword ptr [rbp+0D0h+strPathPrefixes.m_ephemeralStorage.Count+0Ch], rax
0x1800c04d4  mov     eax, [rsp+1D0h+var_16C]
0x1800c04d8  and     eax, ebx
0x1800c04da  lea     pUri, [rsp+1D0h+strPathPrefixes.m_encodedStorage.___u0+14h]; this
0x1800c04df  or      eax, edi
0x1800c04e1  mov     dword ptr [rbp+0D0h+strPathPrefixes.m_ephemeralStorage.___u0+1Ch], eax
0x1800c04e4  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800c04e9  lea     rax, [rbp+0D0h+strPathPrefixes.m_ephemeralStorage.Count+0Ch]
0x1800c04ed  mov     qword ptr [rsp+1D0h+strPathPrefixes.m_encodedStorage.___u0+14h], rax
0x1800c04f2  test    r14, r14
0x1800c04f5  jz      short loc_1800C04FF
0x1800c04f7  mov     pUri, r14; this
0x1800c04fa  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800c04ff  test    r13, r13
0x1800c0502  jz      short loc_1800C050C
0x1800c0504  mov     pUri, r13; this
0x1800c0507  call    ?Reset@xencoded_string_ptr@@QEAAXXZ; xencoded_string_ptr::Reset(void)
0x1800c050c  test    rsi, rsi
0x1800c050f  jz      short loc_1800C0517
0x1800c0511  mov     dword ptr [rsi], 0
0x1800c0517  mov     rax, [r12]
0x1800c051b  lea     pstrResourceMap, [rsp+1D0h+bufferLength]
0x1800c0520  xor     r8d, r8d
0x1800c0523  mov     pUri, r12
0x1800c0526  mov     rax, [rax+50h]
0x1800c052a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c052f  mov     edi, eax
0x1800c0531  test    eax, eax
0x1800c0533  js      loc_1800C0864
0x1800c0539  mov     ebx, [rsp+1D0h+bufferLength]
0x1800c053d  inc     ebx
0x1800c053f  mov     [rsp+1D0h+bufferLength], ebx
0x1800c0543  lea     edi, [rbx+1]
0x1800c0546  cmp     edi, 7FFFFF9Fh
0x1800c054c  jnb     loc_1800C0820
0x1800c0552  mov     pstrResourceMap, [rbp+0D0h+stringBuilder.m_pBuffer]
0x1800c0556  lea     rax, [rbp+0D0h+stringBuilder.m_inlineBuffer]
0x1800c055a  lea     esi, [rdi+1]
0x1800c055d  cmp     pstrResourceMap, rax
0x1800c0560  jnz     loc_1800C094E
0x1800c0566  mov     eax, [rbp+0D0h+stringBuilder.m_cBuffer]
0x1800c0569  cmp     esi, eax
0x1800c056b  jbe     short loc_1800C058E
0x1800c056d  lea     pstrResourcePath, [rbp+0D0h+stringBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800c0571  mov     ecx, edi; length
0x1800c0573  lea     pstrResourceMap, [rbp+0D0h+stringBuilder]; charBuffer
0x1800c0577  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800c057d  mov     edi, eax
0x1800c057f  test    eax, eax
0x1800c0581  js      loc_1800C0910
0x1800c0587  mov     pstrResourceMap, [rbp+0D0h+stringBuilder.m_pBuffer]
0x1800c058b  mov     [rbp+0D0h+stringBuilder.m_cBuffer], esi
0x1800c058e  xor     eax, eax
0x1800c0590  mov     pUri, r12
0x1800c0593  mov     [pstrResourceMap+rbx*2], ax
0x1800c0597  lea     pstrResourceMap, [rsp+1D0h+bufferLength]
0x1800c059c  mov     rax, [r12]
0x1800c05a0  mov     pstrResourcePath, [rbp+0D0h+stringBuilder.m_pBuffer]
0x1800c05a4  mov     [rbp+0D0h+stringBuilder.m_cActual], ebx
0x1800c05a7  mov     rax, [rax+50h]
0x1800c05ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c05b0  mov     edi, eax
0x1800c05b2  test    eax, eax
0x1800c05b4  js      loc_1800C09BA
0x1800c05ba  mov     eax, [rsp+1D0h+bufferLength]
0x1800c05be  lea     pUri, [rbp+0D0h+stringBuilder]; this
0x1800c05c2  mov     pstrResourceMap, [rbp+0D0h+pstrDetachedString]; pstrDetachedString
0x1800c05c6  mov     [rbp+0D0h+stringBuilder.m_cActual], eax
0x1800c05c9  call    ?DetachString@?$TStringBuilder@$0GA@@@QEAAJPEAVxstring_ptr@@@Z; TStringBuilder<96>::DetachString(xstring_ptr *)
0x1800c05ce  mov     edi, eax
0x1800c05d0  test    eax, eax
0x1800c05d2  js      loc_1800C09AE
0x1800c05d8  test    r14, r14
0x1800c05db  jz      loc_1800C0815
0x1800c05e1  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1800c05e8  xor     r8d, r8d
0x1800c05eb  mov     qword ptr [rsp+1D0h+strResourcePath.m_encodedStorage.___u0], rax
0x1800c05f0  lea     pstrResourceMap, [rsp+1D0h+bufferLength]
0x1800c05f5  mov     rax, [r12]
0x1800c05f9  mov     pUri, r12
0x1800c05fc  mov     rax, [rax+60h]
0x1800c0600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0605  mov     edi, eax
0x1800c0607  test    eax, eax
0x1800c0609  js      loc_1800C0928
0x1800c060f  mov     ebx, [rsp+1D0h+bufferLength]
0x1800c0613  inc     ebx
0x1800c0615  mov     [rsp+1D0h+bufferLength], ebx
0x1800c0619  lea     edi, [rbx+1]
0x1800c061c  cmp     edi, 7FFFFF9Fh
0x1800c0622  jnb     loc_1800C0840
0x1800c0628  mov     pUri, [rbp+0D0h+stringBuilder.m_pBuffer]
0x1800c062c  lea     rax, [rbp+0D0h+stringBuilder.m_inlineBuffer]
0x1800c0630  lea     esi, [rdi+1]
0x1800c0633  cmp     pUri, rax
0x1800c0636  jnz     loc_1800C0973
0x1800c063c  mov     r15d, [rbp+0D0h+stringBuilder.m_cBuffer]
0x1800c0640  cmp     esi, r15d
0x1800c0643  jbe     short loc_1800C0666
0x1800c0645  lea     pstrResourcePath, [rbp+0D0h+stringBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800c0649  mov     ecx, edi; length
0x1800c064b  lea     pstrResourceMap, [rbp+0D0h+stringBuilder]; charBuffer
0x1800c064f  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800c0655  mov     edi, eax
0x1800c0657  test    eax, eax
0x1800c0659  js      loc_1800C091C
0x1800c065f  mov     pUri, [rbp+0D0h+stringBuilder.m_pBuffer]
0x1800c0663  mov     [rbp+0D0h+stringBuilder.m_cBuffer], esi
0x1800c0666  xor     eax, eax
0x1800c0668  lea     pstrResourceMap, [rsp+1D0h+bufferLength]
0x1800c066d  mov     [pUri+rbx*2], ax
0x1800c0671  mov     pUri, r12
0x1800c0674  mov     rax, [r12]
0x1800c0678  mov     pstrResourcePath, [rbp+0D0h+stringBuilder.m_pBuffer]
0x1800c067c  mov     [rbp+0D0h+stringBuilder.m_cActual], ebx
0x1800c067f  mov     rax, [rax+60h]
0x1800c0683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0688  mov     edi, eax
0x1800c068a  test    eax, eax
0x1800c068c  js      loc_1800C0890
0x1800c0692  mov     eax, [rsp+1D0h+bufferLength]
0x1800c0696  lea     pstrResourceMap, [rsp+1D0h+strResourcePath]; pstrDetachedString
0x1800c069b  lea     pUri, [rbp+0D0h+stringBuilder]; this
0x1800c069f  mov     [rbp+0D0h+stringBuilder.m_cActual], eax
0x1800c06a2  call    ?DetachString@?$TStringBuilder@$0GA@@@QEAAJPEAVxstring_ptr@@@Z; TStringBuilder<96>::DetachString(xstring_ptr *)
0x1800c06a7  mov     edi, eax
0x1800c06a9  test    eax, eax
0x1800c06ab  js      loc_1800C09A2
0x1800c06b1  test    r14, r14
0x1800c06b4  jz      short loc_1800C06C3
0x1800c06b6  lea     pstrResourceMap, [rsp+1D0h+strResourcePath]; other
0x1800c06bb  mov     pUri, r14; this
0x1800c06be  call    ??4xstring_ptr@@QEAAAEAV0@AEBV0@@Z; xstring_ptr::operator=(xstring_ptr const &)
0x1800c06c3  mov     r12d, 2
0x1800c06c9  test    r13, r13
0x1800c06cc  jz      loc_1800C07BC
0x1800c06d2  mov     rbx, qword ptr [rsp+1D0h+strResourcePath.m_encodedStorage.___u0]
0x1800c06d7  xor     r14d, r14d
0x1800c06da  cmp     r14, r12
0x1800c06dd  jnb     loc_1800C07BC
0x1800c06e3  lea     rax, [r14+r14*4]
0x1800c06e7  lea     r15, [rsp+1D0h+strPathPrefixes]
0x1800c06ec  lea     r15, [r15+rax*4]
0x1800c06f0  test    bl, 1
0x1800c06f3  jnz     loc_1800C086D
0x1800c06f9  mov     esi, [rbx+8]
0x1800c06fc  test    esi, esi
0x1800c06fe  js      loc_1800C0934
0x1800c0704  and     esi, 3FFFFFFFh
0x1800c070a  mov     pUri, [r15]
0x1800c070d  test    cl, 1
0x1800c0710  jnz     loc_1800C0881
0x1800c0716  mov     eax, [pUri+8]
0x1800c0719  test    eax, eax
0x1800c071b  js      loc_1800C093C
0x1800c0721  and     eax, 3FFFFFFFh
0x1800c0726  cmp     esi, eax
0x1800c0728  jb      short loc_1800C074E
0x1800c072a  mov     r9d, eax; cchCompare
0x1800c072d  mov     [rsp+1D0h+eCompareBehavior], 1; eCompareBehavior
0x1800c0735  xor     r8d, r8d; ichStartingIndex
0x1800c0738  lea     pUri, [rsp+1D0h+strResourcePath]; this
0x1800c073d  mov     pstrResourceMap, r15; other
0x1800c0740  call    ?Compare@xstring_ptr_view@@QEBAHAEBV1@IIW4xstrCompareBehavior@@@Z; xstring_ptr_view::Compare(xstring_ptr_view const &,uint,uint,xstrCompareBehavior)
0x1800c0745  test    eax, eax
0x1800c0747  jz      short loc_1800C0753
0x1800c0749  mov     rbx, qword ptr [rsp+1D0h+strResourcePath.m_encodedStorage.___u0]
0x1800c074e  inc     r14
0x1800c0751  jmp     short loc_1800C06DA
0x1800c0753  lfence
0x1800c0756  mov     pUri, qword ptr [rsp+1D0h+strResourcePath.m_encodedStorage.___u0]
0x1800c075b  test    cl, 1
0x1800c075e  jnz     loc_1800C08F0
0x1800c0764  mov     ebx, [pUri+8]
0x1800c0767  test    ebx, ebx
0x1800c0769  js      loc_1800C0944
0x1800c076f  and     ebx, 3FFFFFFFh
0x1800c0775  mov     pUri, [r15]
0x1800c0778  test    cl, 1
0x1800c077b  jnz     loc_1800C0901
0x1800c0781  mov     eax, [pUri+8]
0x1800c0784  test    eax, eax
0x1800c0786  js      loc_1800C0949
0x1800c078c  and     eax, 3FFFFFFFh
0x1800c0791  mov     pstrFilePath, r13; pstrSubstring
0x1800c0794  lea     pUri, [rsp+1D0h+strResourcePath]; this
0x1800c0799  mov     r8d, ebx; endIndex
0x1800c079c  mov     edx, eax; startIndex
0x1800c079e  call    ?SubString@xstring_ptr_view@@QEBAJIIPEAVxstring_ptr@@@Z; xstring_ptr_view::SubString(uint,uint,xstring_ptr *)
0x1800c07a3  mov     edi, eax
0x1800c07a5  test    eax, eax
0x1800c07a7  js      loc_1800C0996
0x1800c07ad  mov     rax, [rbp+0D0h+var_138]
0x1800c07b1  test    rax, rax
0x1800c07b4  jz      short loc_1800C07BC
0x1800c07b6  mov     dword ptr [rax], 1
0x1800c07bc  lea     pUri, [rsp+1D0h+strResourcePath]; this
0x1800c07c1  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1800c07c6  lea     rbx, [rbp+0D0h+pstrDetachedString]
0x1800c07ca  sub     rbx, 14h
0x1800c07ce  mov     pUri, rbx; this
0x1800c07d1  call    ??1xephemeral_string_ptr@@QEAA@XZ; xephemeral_string_ptr::~xephemeral_string_ptr(void)
0x1800c07d6  sub     r12, 1
0x1800c07da  jnz     short loc_1800C07CA
0x1800c07dc  lea     rax, [rbp+0D0h+stringBuilder.m_inlineBuffer]
0x1800c07e0  cmp     [rbp+0D0h+stringBuilder.m_pBuffer], rax
0x1800c07e4  jz      short loc_1800C07F0
0x1800c07e6  mov     pUri, [rbp+0D0h+stringBuilder.m_hPreallocatedBuffer]; bufferHandle
0x1800c07ea  call    cs:__imp_WindowsDeleteStringBuffer
0x1800c07f0  mov     eax, edi
0x1800c07f2  mov     pUri, [rbp+0D0h+var_50]
0x1800c07f9  xor     pUri, rsp; StackCookie
0x1800c07fc  call    __security_check_cookie
0x1800c0801  add     rsp, 198h
0x1800c0808  pop     r15
0x1800c080a  pop     r14
0x1800c080c  pop     r13
0x1800c080e  pop     r12
0x1800c0810  pop     rdi
0x1800c0811  pop     rsi
0x1800c0812  pop     rbx
0x1800c0813  pop     rbp
0x1800c0814  retn
0x1800c0815  test    r13, r13
0x1800c0818  jnz     loc_1800C05E1
0x1800c081e  jmp     short loc_1800C0838
0x1800c0820  mov     edi, 8000FFFFh
0x1800c0825  call    OnNewFailure_2955_
0x1800c082a  mov     ecx, edi; failedFrameHR
0x1800c082c  call    OnFailure_2990_
  ... truncated ...
```
