# PushSubscribeOperation::BuildRequestBody(BufferFormatter &)

- ea: `0x1801379c0`
- end: `0x1801387d6`
- name: `?BuildRequestBody@PushSubscribeOperation@@MEAAHAEAVBufferFormatter@@@Z`
- size: `3606`
- prototype: `__int64 __fastcall(PushSubscribeOperation *__hidden this, struct BufferFormatter *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005d10`
- `0x1800119e0`
- `0x1800159e0`
- `0x180035ee0`
- `0x1800ccd94`
- `0x1800d2fa0`
- `0x1800d3050`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801379c0`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180137ed3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801383b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801386d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180137ed3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801383b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801386d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801386c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801386c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18013853d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18013853d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013854b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013855d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013854b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013855d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18013856b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18013856b`

## string_xrefs

- `0x1801383e5`: `<p:DataLocale xml:lang="`
- `0x180138309`: `<w:Locale xml:lang="`
- `0x180137a9b`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/DeliveryModes/Push`
- `0x180137dc7`: `</e:Identifier></a:ReferenceProperties><c:Policy xmlns:c="http://schemas.xmlsoap.org/ws/2002/12/policy" xmlns:auth="http://schemas.microsoft.com/wbem/wsman/1/authentication"><c:ExactlyOne>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall PushSubscribeOperation::BuildRequestBody(const wchar_t **this, struct BufferFormatter *a2)
{
  const wchar_t *v4; // rax
  int v5; // r13d
  const wchar_t *v6; // r12
  const wchar_t *v7; // rbx
  const wchar_t *v8; // r14
  const wchar_t *v9; // rax
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64, const wchar_t **); // r8
  __int64 v12; // r15
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 (__fastcall *v15)(__int64, const wchar_t **); // rax
  __int64 v16; // r8
  __int64 (__fastcall *v17)(__int64, const wchar_t **); // r9
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 (__fastcall *v20)(__int64, const wchar_t **); // rax
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64, const wchar_t **); // r8
  __int64 v23; // rcx
  __int64 v24; // r8
  void (__fastcall *v25)(__int64, struct _SYSTEMTIME *); // rax
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 (__fastcall *v28)(__int64, const wchar_t **); // rax
  __int64 v29; // rax
  __int64 (__fastcall *v30)(__int64, const wchar_t **); // r9
  __int64 v31; // r8
  void (__fastcall *v32)(__int64, const wchar_t **); // rax
  __int64 v33; // rax
  __int64 (__fastcall *v34)(__int64, const wchar_t **); // r8
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 (__fastcall *v37)(__int64, const wchar_t **); // rax
  __int64 v38; // r8
  __int64 (__fastcall *v39)(__int64, const wchar_t **); // r9
  __int64 v40; // rcx
  __int64 v41; // r8
  void (__fastcall *v42)(__int64, const wchar_t **); // rax
  __int64 v43; // r8
  const wchar_t *v44; // rax
  __int64 v46; // rax
  __int64 (__fastcall *v47)(__int64, const wchar_t **); // r9
  __int64 v48; // rcx
  __int64 v49; // r8
  void (__fastcall *v50)(__int64, const wchar_t **); // rax
  __int64 v51; // rax
  __int64 v52; // r8
  __int64 (__fastcall *v53)(__int64, const wchar_t **); // rax
  __int64 v54; // rax
  __int64 v55; // r8
  void (__fastcall *v56)(__int64, const wchar_t **); // rax
  __int64 v57; // rax
  __int64 v58; // r8
  void (__fastcall *v59)(__int64, const wchar_t **); // rax
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 (__fastcall *v62)(__int64, const wchar_t **); // rax
  __int64 v63; // rax
  __int64 (__fastcall *v64)(__int64, const wchar_t **); // r9
  __int64 v65; // r8
  void (__fastcall *v66)(__int64, const wchar_t **); // rax
  const wchar_t *v67; // rbx
  __int64 v68; // rax
  __int64 (__fastcall *v69)(__int64, const wchar_t **); // r8
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 (__fastcall *v72)(__int64, const wchar_t **); // rax
  __int64 v73; // rax
  __int64 v74; // r8
  void (__fastcall *v75)(__int64, const wchar_t **); // rax
  DWORD v76; // ebx
  _QWORD *v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 (__fastcall *v80)(__int64, const wchar_t **); // r8
  __int64 v81; // rcx
  __int64 v82; // r8
  void (__fastcall *v83)(__int64, const wchar_t **); // rax
  unsigned __int128 v84; // rax
  const unsigned __int16 *v85; // r8
  unsigned __int64 v86; // rcx
  unsigned __int64 v87; // rbx
  int v88; // r12d
  __int64 v89; // rax
  unsigned __int64 v90; // rbx
  __int64 v91; // r8
  __int64 (__fastcall *v92)(__int64, const wchar_t **); // rax
  __int64 v93; // r8
  __int64 (__fastcall *v94)(__int64, const wchar_t **); // rax
  __int64 v95; // r8
  void (__fastcall *v96)(__int64, const wchar_t **); // rax
  __int64 v97; // rax
  __int64 (__fastcall *v98)(__int64, const wchar_t **); // r8
  __int64 v99; // r8
  void (__fastcall *v100)(__int64, const wchar_t **); // rax
  const wchar_t *v101; // [rsp+30h] [rbp-89h] BYREF
  int v102; // [rsp+38h] [rbp-81h]
  const wchar_t *v103; // [rsp+40h] [rbp-79h] BYREF
  const unsigned __int16 *v104; // [rsp+48h] [rbp-71h]
  const wchar_t *v105; // [rsp+50h] [rbp-69h] BYREF
  int v106; // [rsp+58h] [rbp-61h]
  __int64 v107; // [rsp+60h] [rbp-59h]
  FILETIME FileTime2; // [rsp+68h] [rbp-51h] BYREF
  struct _FILETIME FileTime; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int64 v110; // [rsp+78h] [rbp-41h]
  int v111; // [rsp+80h] [rbp-39h]
  const wchar_t *v112; // [rsp+88h] [rbp-31h] BYREF
  int v113; // [rsp+90h] [rbp-29h]
  const wchar_t *v114; // [rsp+98h] [rbp-21h]
  const wchar_t *v115; // [rsp+A0h] [rbp-19h] BYREF
  int v116; // [rsp+A8h] [rbp-11h]
  const wchar_t *v117; // [rsp+B0h] [rbp-9h] BYREF
  int v118; // [rsp+B8h] [rbp-1h]
  struct _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp+7h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4c11128532643e2e66ed7e3cc1393343_Traceguids, this);
  v4 = this[6829];
  v5 = *((_DWORD *)v4 + 20);
  FileTime2 = (FILETIME)(v4 + 60);
  v6 = this[6834];
  if ( !v6 )
    v6 = v4 + 97;
  FileTime.dwLowDateTime = v5 & 0x80;
  if ( (v5 & 0x80) != 0 )
  {
    v7 = L"http://schemas.dmtf.org/wbem/wsman/1/wsman/Events";
    goto LABEL_13;
  }
  if ( (v5 & 0x20) == 0 )
  {
    if ( (v5 & 0x40) != 0 )
    {
      v7 = L"http://schemas.dmtf.org/wbem/wsman/1/wsman/PushWithAck";
      goto LABEL_13;
    }
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\pushsubscription.cpp", 1714, L"1714", 0x54Fu, 0);
  }
  v7 = L"http://schemas.xmlsoap.org/ws/2004/08/eventing/DeliveryModes/Push";
LABEL_13:
  v8 = this[6829];
  v9 = L"UTF-8";
  if ( !*((_BYTE *)v8 + 8747) )
    v9 = L"UTF-16";
  v114 = v9;
  v111 = 0;
  v110 = 0;
  v115 = L"<e:Subscribe><e:EndTo><a:Address>";
  v116 = 33;
  v10 = (*(__int64 (__fastcall **)(struct BufferFormatter *, const wchar_t **))(*(_QWORD *)a2 + 128LL))(a2, &v115);
  v11 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v10 + 128LL);
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( v6[v13] );
  v117 = v6;
  v118 = v13;
  v14 = v11(v10, &v117);
  v15 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v14 + 128LL);
  v112 = L"</a:Address><a:ReferenceProperties><e:Identifier>";
  v113 = 49;
  v16 = v15(v14, &v112);
  v17 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v16 + 128LL);
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(*(_QWORD *)&FileTime2 + 2 * v18) );
  v105 = (const wchar_t *)FileTime2;
  v106 = v18;
  v19 = v17(v16, &v105);
  v20 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v19 + 128LL);
  v103 = L"</e:Identifier></a:ReferenceProperties></e:EndTo><e:Delivery Mode=\"";
  LODWORD(v104) = 67;
  v21 = v20(v19, &v103);
  v22 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v21 + 128LL);
  v23 = -1;
  do
    ++v23;
  while ( v7[v23] );
  v101 = v7;
  v102 = v23;
  v24 = v22(v21, &v101);
  v25 = *(void (__fastcall **)(__int64, struct _SYSTEMTIME *))(*(_QWORD *)v24 + 128LL);
  *(_QWORD *)&SystemTime.wYear = L"\">";
  *(_DWORD *)&SystemTime.wHour = 2;
  v25(v24, &SystemTime);
  if ( *((_DWORD *)v8 + 19) != -1 )
  {
    *(_QWORD *)&SystemTime.wYear = L"<w:Heartbeats>PT";
    *(_DWORD *)&SystemTime.wHour = 16;
    v26 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
            a2,
            &SystemTime);
    v27 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 104LL))(v26, *((_DWORD *)v8 + 19) / 0x3E8u);
    v28 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v27 + 128LL);
    v101 = L".";
    v102 = 1;
    v29 = v28(v27, &v101);
    v30 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v29 + 96LL);
    LODWORD(v103) = *((_DWORD *)v8 + 19) % 0x3E8u;
    v104 = L"%03lu";
    v31 = v30(v29, &v103);
    v32 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v31 + 128LL);
    v105 = L"S</w:Heartbeats>";
    v106 = 16;
    v32(v31, &v105);
  }
  *(_QWORD *)&SystemTime.wYear = L"<e:NotifyTo><a:Address>";
  *(_DWORD *)&SystemTime.wHour = 23;
  v33 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
          a2,
          &SystemTime);
  v34 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v33 + 128LL);
  v35 = -1;
  do
    ++v35;
  while ( v6[v35] );
  v101 = v6;
  v102 = v35;
  v36 = v34(v33, &v101);
  v37 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v36 + 128LL);
  v103 = L"</a:Address><a:ReferenceProperties><e:Identifier>";
  LODWORD(v104) = 49;
  v38 = v37(v36, &v103);
  v39 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v38 + 128LL);
  v40 = -1;
  do
    ++v40;
  while ( *(_WORD *)(*(_QWORD *)&FileTime2 + 2 * v40) );
  v105 = (const wchar_t *)FileTime2;
  v106 = v40;
  v41 = v39(v38, &v105);
  v42 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v41 + 128LL);
  v112 = L"</e:Identifier></a:ReferenceProperties><c:Policy xmlns:c=\"http://schemas.xmlsoap.org/ws/2002/12/policy\" xmlns"
          ":auth=\"http://schemas.microsoft.com/wbem/wsman/1/authentication\"><c:ExactlyOne>";
  v113 = 188;
  v42(v41, &v112);
  if ( (*(unsigned __int8 (__fastcall **)(const wchar_t *))(*(_QWORD *)this[6829] + 144LL))(this[6829]) )
  {
    if ( (unsigned int)StringCchEqualsCI(*((wchar_t **)v8 + 1050), (wchar_t *)L"HTTP") )
    {
      v44 = L"<c:All><auth:Authentication Profile=\"http://schemas.dmtf.org/wbem/wsman/1/wsman/secprofile/http/spnego-kerb"
             "eros\"></auth:Authentication></c:All>";
      *(_DWORD *)&SystemTime.wHour = 143;
    }
    else
    {
      if ( !(unsigned int)StringCchEqualsCI(*((wchar_t **)v8 + 1050), (wchar_t *)L"HTTPS") )
        goto LABEL_33;
      v44 = L"<c:All><auth:Authentication Profile=\"http://schemas.dmtf.org/wbem/wsman/1/wsman/secprofile/https/spnego-ker"
             "beros\"></auth:Authentication></c:All>";
      *(_DWORD *)&SystemTime.wHour = 144;
    }
    *(_QWORD *)&SystemTime.wYear = v44;
    (*(void (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(a2, &SystemTime);
  }
LABEL_33:
  LOBYTE(v43) = 1;
  SafeMap_Iterator<StringKeyCI,Empty>::SafeMap_Iterator<StringKeyCI,Empty>(&v105, this[6829] + 4292, v43);
  if ( !v107 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4c11128532643e2e66ed7e3cc1393343_Traceguids);
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)this[76] + 24LL))(this[76]);
    SetLastError(0xEu);
    SafeMap_Iterator<StringKeyCI,WSManHttpListener::USER_CONTEXT_INFO>::~SafeMap_Iterator<StringKeyCI,WSManHttpListener::USER_CONTEXT_INFO>(&v105);
    return 0;
  }
  while ( (unsigned __int8)SafeMap_Iterator<CShellUriSettings *,Empty>::operator bool(&v105) )
  {
    *(_QWORD *)&SystemTime.wYear = L"<c:All><auth:Authentication Profile=\"http://schemas.dmtf.org/wbem/wsman/1/wsman/secp"
                                    "rofile/https/mutual\"><auth:ClientCertificate><auth:Thumbprint Role=\"issuer\">";
    *(_DWORD *)&SystemTime.wHour = 160;
    v46 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
            a2,
            &SystemTime);
    v47 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v46 + 128LL);
    v48 = -1;
    do
      ++v48;
    while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)v107 + 32LL) + 2 * v48) );
    v101 = *(const wchar_t **)(*(_QWORD *)v107 + 32LL);
    v102 = v48;
    v49 = v47(v46, &v101);
    v50 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v49 + 128LL);
    v103 = L"</auth:Thumbprint></auth:ClientCertificate></auth:Authentication></c:All>";
    LODWORD(v104) = 73;
    v50(v49, &v103);
    SafeMap_Iterator<StringKeyCI,Empty>::operator++(&v105, 0);
  }
  SafeMap_Iterator<StringKeyCI,WSManHttpListener::USER_CONTEXT_INFO>::~SafeMap_Iterator<StringKeyCI,WSManHttpListener::USER_CONTEXT_INFO>(&v105);
  *(_QWORD *)&SystemTime.wYear = L"</c:ExactlyOne></c:Policy></e:NotifyTo>";
  *(_DWORD *)&SystemTime.wHour = 39;
  (*(void (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(a2, &SystemTime);
  if ( *((_DWORD *)v8 + 2103) && *((_DWORD *)v8 + 2102) )
  {
    *(_QWORD *)&SystemTime.wYear = L"<w:ConnectionRetry Total=\"";
    *(_DWORD *)&SystemTime.wHour = 26;
    v51 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
            a2,
            &SystemTime);
    v52 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 104LL))(v51, *((unsigned int *)v8 + 2103));
    v53 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v52 + 128LL);
    v101 = L"\">PT";
    v102 = 4;
    v54 = v53(v52, &v101);
    v55 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v54 + 104LL))(v54, *((unsigned int *)v8 + 2102));
    v56 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v55 + 128LL);
    v103 = L".0S</w:ConnectionRetry>";
    LODWORD(v104) = 23;
    v56(v55, &v103);
  }
  if ( FileTime.dwLowDateTime )
  {
    if ( *((_DWORD *)v8 + 13) != -1 )
    {
      *(_QWORD *)&SystemTime.wYear = L"<w:MaxElements>";
      *(_DWORD *)&SystemTime.wHour = 15;
      v57 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
              a2,
              &SystemTime);
      v58 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 104LL))(v57, *((unsigned int *)v8 + 13));
      v59 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v58 + 128LL);
      v101 = L"</w:MaxElements>";
      v102 = 16;
      v59(v58, &v101);
    }
    if ( *((_DWORD *)v8 + 14) != -1 )
    {
      *(_QWORD *)&SystemTime.wYear = L"<w:MaxTime>PT";
      *(_DWORD *)&SystemTime.wHour = 13;
      v60 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
              a2,
              &SystemTime);
      v61 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v60 + 104LL))(v60, *((_DWORD *)v8 + 14) / 0x3E8u);
      v62 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v61 + 128LL);
      v101 = L".";
      v102 = 1;
      v63 = v62(v61, &v101);
      v64 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v63 + 96LL);
      LODWORD(v103) = *((_DWORD *)v8 + 14) % 0x3E8u;
      v104 = L"%03lu";
      v65 = v64(v63, &v103);
      v66 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v65 + 128LL);
      v105 = L"S</w:MaxTime>";
      v106 = 13;
      v66(v65, &v105);
    }
  }
  if ( *((_DWORD *)v8 + 12) != -1 )
  {
    if ( (v5 & 0x10000) != 0 )
    {
      v67 = L"CancelSubscription";
    }
    else
    {
      v67 = L"Skip";
      if ( (v5 & 0x20000) == 0 )
        v67 = L"Notify";
    }
    *(_QWORD *)&SystemTime.wYear = L"<w:MaxEnvelopeSize Policy=\"";
    *(_DWORD *)&SystemTime.wHour = 27;
    v68 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
            a2,
            &SystemTime);
    v69 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v68 + 128LL);
    v101 = v67;
    v70 = -1;
    do
      ++v70;
    while ( v67[v70] );
    v102 = v70;
    v71 = v69(v68, &v101);
    v72 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v71 + 128LL);
    v103 = L"\">";
    LODWORD(v104) = 2;
    v73 = v72(v71, &v103);
    v74 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 104LL))(v73, *((unsigned int *)v8 + 12));
    v75 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v74 + 128LL);
    v105 = L"</w:MaxEnvelopeSize>";
    v106 = 20;
    v75(v74, &v105);
  }
  *(_QWORD *)&SystemTime.wYear = L"<w:Locale xml:lang=\"";
  *(_DWORD *)&SystemTime.wHour = 20;
  (*(void (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(a2, &SystemTime);
  (*((void (__fastcall **)(const wchar_t **, const wchar_t *, struct BufferFormatter *))*this + 14))(this, this[76], a2);
  if ( !(*(unsigned int (__fastcall **)(const wchar_t *))(*(_QWORD *)this[76] + 144LL))(this[76]) )
  {
    v76 = (*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)this[76] + 152LL))(this[76]);
    v77 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_64;
    v78 = 18;
LABEL_63:
    WPP_SF_d(v77[2], v78, WPP_4c11128532643e2e66ed7e3cc1393343_Traceguids, v76);
LABEL_64:
    SetLastError(v76);
    return 0;
  }
  *(_QWORD *)&SystemTime.wYear = L"\" s:mustUnderstand=\"false\" />";
  *(_DWORD *)&SystemTime.wHour = 29;
  (*(void (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(a2, &SystemTime);
  *(_QWORD *)&SystemTime.wYear = L"<p:DataLocale xml:lang=\"";
  *(_DWORD *)&SystemTime.wHour = 24;
  (*(void (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(a2, &SystemTime);
  (*((void (__fastcall **)(const wchar_t **, const wchar_t *, struct BufferFormatter *))*this + 15))(this, this[76], a2);
  if ( !(*(unsigned int (__fastcall **)(const wchar_t *))(*(_QWORD *)this[76] + 144LL))(this[76]) )
  {
    v76 = (*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)this[76] + 152LL))(this[76]);
    v77 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_64;
    v78 = 19;
    goto LABEL_63;
  }
  *(_QWORD *)&SystemTime.wYear = L"\" s:mustUnderstand=\"false\" />";
  *(_DWORD *)&SystemTime.wHour = 29;
  (*(void (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(a2, &SystemTime);
  *(_QWORD *)&SystemTime.wYear = L"<w:ContentEncoding>";
  *(_DWORD *)&SystemTime.wHour = 19;
  v79 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
          a2,
          &SystemTime);
  v80 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v79 + 128LL);
  v101 = v114;
  v81 = -1;
  do
    ++v81;
  while ( v114[v81] );
  v102 = v81;
  v82 = v80(v79, &v101);
  v83 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v82 + 128LL);
  v103 = L"</w:ContentEncoding></e:Delivery>";
  LODWORD(v104) = 33;
  v83(v82, &v103);
  FileTime = 0;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  FileTime2 = 0;
  SystemTimeToFileTime((const SYSTEMTIME *)(v8 + 30), &FileTime2);
  if ( CompareFileTime(&FileTime, &FileTime2) == -1 )
  {
    v86 = FileTime2.dwLowDateTime
        + ((FileTime2.dwHighDateTime - (unsigned __int64)FileTime.dwHighDateTime) << 32)
        - FileTime.dwLowDateTime;
    v84 = v86 * (unsigned __int128)0x346DC5D63886594BuLL;
    v87 = v86 / 0x2710;
    v110 = v86 / 0x2710;
    v88 = v86 / 0x2710;
  }
  else
  {
    v87 = v110;
    v88 = v111;
  }
  if ( v87 )
  {
    *(_QWORD *)&SystemTime.wYear = L"<e:Expires>PT";
    *(_DWORD *)&SystemTime.wHour = 13;
    v89 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
            a2,
            &SystemTime);
    v90 = v87 / 0x3E8;
    v91 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v89 + 104LL))(v89, (unsigned int)v90);
    v92 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v91 + 128LL);
    v101 = L".";
    v102 = 1;
    v93 = v92(v91, &v101);
    v94 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v93 + 96LL);
    LODWORD(v103) = v88 - 1000 * v90;
    v104 = L"%03lu";
    v95 = v94(v93, &v103);
    v96 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v95 + 128LL);
    v105 = L"S</e:Expires>";
    v106 = 13;
    v96(v95, &v105);
  }
  *(_QWORD *)&v84 = *((_QWORD *)v8 + 4);
  if ( ((_QWORD)v84 || *((_QWORD *)v8 + 3))
    && !(unsigned int)CRemoteFilteredOperation::AddFilter(
                        (CRemoteFilteredOperation *)this,
                        *((const unsigned __int16 **)&v84 + 1),
                        v85,
                        *((const unsigned __int16 **)v8 + 3),
                        (const unsigned __int16 *)v84,
                        a2) )
  {
    if ( GetLastError() != 122 )
      return 0;
    SetLastError(0);
  }
  if ( this[6830] )
  {
    *(_QWORD *)&SystemTime.wYear = L"<w:Bookmark>";
    *(_DWORD *)&SystemTime.wHour = 12;
    v97 = (*(__int64 (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(
            a2,
            &SystemTime);
    v98 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v97 + 128LL);
    do
      ++v12;
    while ( this[6830][v12] );
    v101 = this[6830];
    v102 = v12;
    v99 = v98(v97, &v101);
    v100 = *(void (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v99 + 128LL);
    v103 = L"</w:Bookmark>";
    LODWORD(v104) = 13;
    v100(v99, &v103);
  }
  if ( (v5 & 0x200) != 0 )
  {
    *(_QWORD *)&SystemTime.wYear = L"<w:SendBookmarks/>";
    *(_DWORD *)&SystemTime.wHour = 18;
    (*(void (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(a2, &SystemTime);
  }
  *(_QWORD *)&SystemTime.wYear = L"</e:Subscribe>";
  *(_DWORD *)&SystemTime.wHour = 14;
  (*(void (__fastcall **)(struct BufferFormatter *, struct _SYSTEMTIME *))(*(_QWORD *)a2 + 128LL))(a2, &SystemTime);
  return *((_DWORD *)a2 + 19) == 0;
}

```

## disassembly

```asm
0x1801379c0  mov     [rsp-8+arg_10], rbx
0x1801379c5  push    rbp
0x1801379c6  push    rsi
0x1801379c7  push    rdi
0x1801379c8  push    r12
0x1801379ca  push    r13
0x1801379cc  push    r14
0x1801379ce  push    r15
0x1801379d0  lea     rbp, [rsp-27h]
0x1801379d5  sub     rsp, 0E0h
0x1801379dc  mov     rax, cs:__security_cookie
0x1801379e3  xor     rax, rsp
0x1801379e6  mov     [rbp+57h+var_40], rax
0x1801379ea  mov     rdi, rdx
0x1801379ed  mov     rsi, rcx
0x1801379f0  lea     rax, WPP_GLOBAL_Control
0x1801379f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801379fe  cmp     rcx, rax
0x180137a01  jz      short loc_180137A24
0x180137a03  test    dword ptr [rcx+1Ch], 10000h
0x180137a0a  jz      short loc_180137A24
0x180137a0c  mov     edx, 10h
0x180137a11  mov     r9, rsi
0x180137a14  lea     r8, WPP_4c11128532643e2e66ed7e3cc1393343_Traceguids
0x180137a1b  mov     rcx, [rcx+10h]
0x180137a1f  call    WPP_SF_q
0x180137a24  mov     rax, [rsi+0D568h]
0x180137a2b  mov     r13d, [rax+50h]
0x180137a2f  lea     rcx, [rax+78h]
0x180137a33  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rcx
0x180137a37  mov     r12, [rsi+0D590h]
0x180137a3e  xor     r15d, r15d
0x180137a41  test    r12, r12
0x180137a44  jnz     short loc_180137A4D
0x180137a46  lea     r12, [rax+0C2h]
0x180137a4d  mov     eax, r13d
0x180137a50  and     eax, 80h
0x180137a55  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180137a58  jz      short loc_180137A63
0x180137a5a  lea     rbx, aHttpSchemasDmt_30; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x180137a61  jmp     short loc_180137AA2
0x180137a63  test    r13b, 20h
0x180137a67  jnz     short loc_180137A9B
0x180137a69  test    r13b, 40h
0x180137a6d  jz      short loc_180137A78
0x180137a6f  lea     rbx, aHttpSchemasDmt_73; "http://schemas.dmtf.org/wbem/wsman/1/ws"...
0x180137a76  jmp     short loc_180137AA2
0x180137a78  mov     [rsp+110h+var_F0], r15; struct IRequestContext *
0x180137a7d  mov     r9d, 54Fh; unsigned int
0x180137a83  lea     r8, a1714; "1714"
0x180137a8a  mov     edx, 6B2h; unsigned int
0x180137a8f  lea     rcx, aOnecoreAdminWm_153; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x180137a96  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180137a9b  lea     rbx, aHttpSchemasXml_9; "http://schemas.xmlsoap.org/ws/2004/08/e"...
0x180137aa2  mov     r14, [rsi+0D568h]
0x180137aa9  lea     rcx, aUtf16; "UTF-16"
0x180137ab0  lea     rax, aUtf8_0; "UTF-8"
0x180137ab7  cmp     [r14+222Bh], r15b
0x180137abe  cmovz   rax, rcx
0x180137ac2  mov     [rbp+57h+var_78], rax
0x180137ac6  mov     eax, r15d
0x180137ac9  mov     [rbp+57h+var_90], eax
0x180137acc  mov     dword ptr [rbp+57h+var_98], eax
0x180137acf  mov     dword ptr [rbp+57h+var_98+4], r15d
0x180137ad3  lea     rax, aESubscribeEEnd; "<e:Subscribe><e:EndTo><a:Address>"
0x180137ada  mov     [rbp+57h+var_70], rax
0x180137ade  mov     [rbp+57h+var_68], 21h ; '!'
0x180137ae5  mov     rax, [rdi]
0x180137ae8  lea     rdx, [rbp+57h+var_70]
0x180137aec  mov     rcx, rdi
0x180137aef  mov     rax, [rax+80h]
0x180137af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137afb  mov     rcx, [rax]
0x180137afe  mov     r8, [rcx+80h]
0x180137b05  or      r15, 0FFFFFFFFFFFFFFFFh
0x180137b09  mov     rcx, r15
0x180137b0c  xor     edx, edx
0x180137b0e  inc     rcx
0x180137b11  cmp     [r12+rcx*2], dx
0x180137b16  jnz     short loc_180137B0E
0x180137b18  mov     [rbp+57h+var_60], r12
0x180137b1c  mov     [rbp+57h+var_58], ecx
0x180137b1f  lea     rdx, [rbp+57h+var_60]
0x180137b23  mov     rcx, rax
0x180137b26  mov     rax, r8
0x180137b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137b2e  mov     r8, rax
0x180137b31  mov     rcx, [rax]
0x180137b34  mov     rax, [rcx+80h]
0x180137b3b  lea     rcx, aAAddressARefer_1; "</a:Address><a:ReferenceProperties><e:I"...
0x180137b42  mov     [rbp+57h+var_88], rcx
0x180137b46  mov     [rbp+57h+var_80], 31h ; '1'
0x180137b4d  lea     rdx, [rbp+57h+var_88]
0x180137b51  mov     rcx, r8
0x180137b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137b59  mov     r8, rax
0x180137b5c  mov     rcx, [rax]
0x180137b5f  mov     r9, [rcx+80h]
0x180137b66  mov     rcx, r15
0x180137b69  mov     rax, qword ptr [rbp+57h+FileTime2.dwLowDateTime]
0x180137b6d  xor     edx, edx
0x180137b6f  inc     rcx
0x180137b72  cmp     [rax+rcx*2], dx
0x180137b76  jnz     short loc_180137B6F
0x180137b78  mov     [rbp+57h+var_C0], rax
0x180137b7c  mov     [rbp+57h+var_B8], ecx
0x180137b7f  lea     rdx, [rbp+57h+var_C0]
0x180137b83  mov     rcx, r8
0x180137b86  mov     rax, r9
0x180137b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137b8e  mov     r8, rax
0x180137b91  mov     rcx, [rax]
0x180137b94  mov     rax, [rcx+80h]
0x180137b9b  lea     rcx, aEIdentifierARe_0; "</e:Identifier></a:ReferenceProperties>"...
0x180137ba2  mov     [rbp+57h+var_D0], rcx
0x180137ba6  mov     dword ptr [rbp+57h+var_C8], 43h ; 'C'
0x180137bad  lea     rdx, [rbp+57h+var_D0]
0x180137bb1  mov     rcx, r8
0x180137bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137bb9  mov     rcx, [rax]
0x180137bbc  mov     r8, [rcx+80h]
0x180137bc3  mov     rcx, r15
0x180137bc6  xor     edx, edx
0x180137bc8  inc     rcx
0x180137bcb  cmp     [rbx+rcx*2], dx
0x180137bcf  jnz     short loc_180137BC8
0x180137bd1  mov     [rsp+110h+var_E0], rbx
0x180137bd6  mov     [rsp+110h+var_D8], ecx
0x180137bda  lea     rdx, [rsp+110h+var_E0]
0x180137bdf  mov     rcx, rax
0x180137be2  mov     rax, r8
0x180137be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137bea  mov     r8, rax
0x180137bed  mov     rcx, [rax]
0x180137bf0  mov     rax, [rcx+80h]
0x180137bf7  lea     rcx, asc_1801D96B0; "\">"
0x180137bfe  mov     qword ptr [rbp+57h+SystemTime.wYear], rcx
0x180137c02  mov     dword ptr [rbp+57h+SystemTime.wHour], 2
0x180137c09  lea     rdx, [rbp+57h+SystemTime]
0x180137c0d  mov     rcx, r8
0x180137c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137c15  or      ebx, 0FFFFFFFFh
0x180137c18  cmp     [r14+4Ch], ebx
0x180137c1c  jz      loc_180137CFE
0x180137c22  lea     rax, aWHeartbeatsPt; "<w:Heartbeats>PT"
0x180137c29  mov     qword ptr [rbp+57h+SystemTime.wYear], rax
0x180137c2d  mov     dword ptr [rbp+57h+SystemTime.wHour], 10h
0x180137c34  mov     rax, [rdi]
0x180137c37  lea     rdx, [rbp+57h+SystemTime]
0x180137c3b  mov     rcx, rdi
0x180137c3e  mov     rax, [rax+80h]
0x180137c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137c4a  mov     rcx, rax
0x180137c4d  mov     r8, [rax]
0x180137c50  mov     eax, 10624DD3h
0x180137c55  mul     dword ptr [r14+4Ch]
0x180137c59  shr     edx, 6
0x180137c5c  mov     rax, [r8+68h]
0x180137c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137c65  mov     r8, rax
0x180137c68  mov     rcx, [rax]
0x180137c6b  mov     rax, [rcx+80h]
0x180137c72  lea     rcx, asc_1801D9F5C; "."
0x180137c79  mov     [rsp+110h+var_E0], rcx
0x180137c7e  mov     [rsp+110h+var_D8], 1
0x180137c86  lea     rdx, [rsp+110h+var_E0]
0x180137c8b  mov     rcx, r8
0x180137c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137c93  mov     r10, rax
0x180137c96  mov     rcx, [rax]
0x180137c99  mov     r9, [rcx+60h]
0x180137c9d  mov     r8d, [r14+4Ch]
0x180137ca1  mov     eax, 10624DD3h
0x180137ca6  mul     r8d
0x180137ca9  shr     edx, 6
0x180137cac  imul    ecx, edx, 3E8h
0x180137cb2  sub     r8d, ecx
0x180137cb5  mov     dword ptr [rbp+57h+var_D0], r8d
0x180137cb9  lea     rax, a03lu; "%03lu"
0x180137cc0  mov     [rbp+57h+var_C8], rax
0x180137cc4  lea     rdx, [rbp+57h+var_D0]
0x180137cc8  mov     rcx, r10
0x180137ccb  mov     rax, r9
0x180137cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137cd3  mov     r8, rax
0x180137cd6  mov     rcx, [rax]
0x180137cd9  mov     rax, [rcx+80h]
0x180137ce0  lea     rcx, aSWHeartbeats; "S</w:Heartbeats>"
0x180137ce7  mov     [rbp+57h+var_C0], rcx
0x180137ceb  mov     [rbp+57h+var_B8], 10h
0x180137cf2  lea     rdx, [rbp+57h+var_C0]
0x180137cf6  mov     rcx, r8
0x180137cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137cfe  lea     rax, aENotifytoAAddr; "<e:NotifyTo><a:Address>"
0x180137d05  mov     qword ptr [rbp+57h+SystemTime.wYear], rax
0x180137d09  mov     dword ptr [rbp+57h+SystemTime.wHour], 17h
0x180137d10  mov     rax, [rdi]
0x180137d13  lea     rdx, [rbp+57h+SystemTime]
0x180137d17  mov     rcx, rdi
0x180137d1a  mov     rax, [rax+80h]
0x180137d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137d26  mov     rcx, [rax]
0x180137d29  mov     r8, [rcx+80h]
0x180137d30  mov     rcx, r15
0x180137d33  xor     edx, edx
0x180137d35  inc     rcx
0x180137d38  cmp     [r12+rcx*2], dx
0x180137d3d  jnz     short loc_180137D35
0x180137d3f  mov     [rsp+110h+var_E0], r12
0x180137d44  mov     [rsp+110h+var_D8], ecx
0x180137d48  lea     rdx, [rsp+110h+var_E0]
0x180137d4d  mov     rcx, rax
0x180137d50  mov     rax, r8
0x180137d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137d58  mov     r8, rax
0x180137d5b  mov     rcx, [rax]
0x180137d5e  mov     rax, [rcx+80h]
0x180137d65  lea     rcx, aAAddressARefer_1; "</a:Address><a:ReferenceProperties><e:I"...
0x180137d6c  mov     [rbp+57h+var_D0], rcx
0x180137d70  mov     dword ptr [rbp+57h+var_C8], 31h ; '1'
0x180137d77  lea     rdx, [rbp+57h+var_D0]
0x180137d7b  mov     rcx, r8
0x180137d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137d83  mov     r8, rax
0x180137d86  mov     rcx, [rax]
0x180137d89  mov     r9, [rcx+80h]
0x180137d90  mov     rcx, r15
0x180137d93  mov     rax, qword ptr [rbp+57h+FileTime2.dwLowDateTime]
0x180137d97  xor     r12d, r12d
0x180137d9a  inc     rcx
0x180137d9d  cmp     [rax+rcx*2], r12w
0x180137da2  jnz     short loc_180137D9A
0x180137da4  mov     [rbp+57h+var_C0], rax
0x180137da8  mov     [rbp+57h+var_B8], ecx
0x180137dab  lea     rdx, [rbp+57h+var_C0]
0x180137daf  mov     rcx, r8
0x180137db2  mov     rax, r9
0x180137db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137dba  mov     r8, rax
0x180137dbd  mov     rcx, [rax]
0x180137dc0  mov     rax, [rcx+80h]
0x180137dc7  lea     rcx, aEIdentifierARe; "</e:Identifier></a:ReferenceProperties>"...
0x180137dce  mov     [rbp+57h+var_88], rcx
0x180137dd2  mov     [rbp+57h+var_80], 0BCh
0x180137dd9  lea     rdx, [rbp+57h+var_88]
0x180137ddd  mov     rcx, r8
0x180137de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137de5  mov     rcx, [rsi+0D568h]
0x180137dec  mov     rax, [rcx]
0x180137def  mov     rax, [rax+90h]
0x180137df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137dfb  test    al, al
0x180137dfd  jz      short loc_180137E65
0x180137dff  lea     rdx, aHttp; "HTTP"
0x180137e06  mov     rcx, [r14+20D0h]; String1
0x180137e0d  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180137e12  test    eax, eax
0x180137e14  jz      short loc_180137E26
0x180137e16  lea     rax, aCAllAuthAuthen; "<c:All><auth:Authentication Profile=\"h"...
0x180137e1d  mov     dword ptr [rbp+57h+SystemTime.wHour], 8Fh
0x180137e24  jmp     short loc_180137E4B
0x180137e26  lea     rdx, aHttps_1; "HTTPS"
0x180137e2d  mov     rcx, [r14+20D0h]; String1
0x180137e34  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180137e39  test    eax, eax
0x180137e3b  jz      short loc_180137E65
0x180137e3d  lea     rax, aCAllAuthAuthen_0; "<c:All><auth:Authentication Profile=\"h"...
0x180137e44  mov     dword ptr [rbp+57h+SystemTime.wHour], 90h
0x180137e4b  mov     qword ptr [rbp+57h+SystemTime.wYear], rax
0x180137e4f  mov     rax, [rdi]
0x180137e52  lea     rdx, [rbp+57h+SystemTime]
0x180137e56  mov     rcx, rdi
0x180137e59  mov     rax, [rax+80h]
0x180137e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137e65  mov     rdx, [rsi+0D568h]
0x180137e6c  add     rdx, 2188h
0x180137e73  mov     r8b, 1
0x180137e76  lea     rcx, [rbp+57h+var_C0]
0x180137e7a  call    ??0?$SafeMap_Iterator@VStringKeyCI@@UEmpty@@@@QEAA@AEAV?$SafeMap@VStringKeyCI@@UEmpty@@V?$SafeMap_Iterator@VStringKeyCI@@UEmpty@@@@@@_N@Z; SafeMap_Iterator<StringKeyCI,Empty>::SafeMap_Iterator<StringKeyCI,Empty>(SafeMap<StringKeyCI,Empty,SafeMap_Iterator<StringKeyCI,Empty>> &,bool)
0x180137e7f  nop
0x180137e80  cmp     [rbp+57h+var_B0], r12
0x180137e84  jnz     loc_180137FA5
0x180137e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180137e91  lea     rax, WPP_GLOBAL_Control
0x180137e98  cmp     rcx, rax
0x180137e9b  jz      short loc_180137EBB
0x180137e9d  test    dword ptr [rcx+1Ch], 8000h
0x180137ea4  jz      short loc_180137EBB
0x180137ea6  mov     edx, 11h
0x180137eab  lea     r8, WPP_4c11128532643e2e66ed7e3cc1393343_Traceguids
0x180137eb2  mov     rcx, [rcx+10h]
0x180137eb6  call    WPP_SF_
0x180137ebb  mov     rcx, [rsi+260h]
0x180137ec2  mov     rax, [rcx]
0x180137ec5  mov     rax, [rax+18h]
0x180137ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137ece  mov     ecx, 0Eh; dwErrCode
0x180137ed3  call    cs:__imp_SetLastError
0x180137ed9  nop
0x180137eda  lea     rcx, [rbp+57h+var_C0]
  ... truncated ...
```
