# NgcHandler::RsaDecryptWithPkcs1(void *,_GUID const &,unsigned __int64,ushort const *,ushort const *,ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180015810`
- end: `0x180016548`
- name: `?RsaDecryptWithPkcs1@NgcHandler@@QEAAJPEAXAEBU_GUID@@_KPEBG33PEBEKPEAPEAEPEAK@Z`
- size: `3384`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015700`

## callees

- `0x18000a8e0`
- `0x18000b490`
- `0x18000c740`
- `0x18000c7e0`
- `0x180015810`
- `0x18002c640`
- `0x18002d500`
- `0x180047fe0`
- `0x180080010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800158d4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800158f1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015bb4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015cc7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015ef0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800160c5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001643f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800158d4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800158f1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015bb4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015cc7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015ef0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800160c5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001643f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015a5d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015b67`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015e48`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001605c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016357`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001650f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015a5d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015b67`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015e48`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001605c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016357`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001650f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180015a9a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180015a9a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015b84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015c97`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015ec0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016095`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001640f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015b84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015c97`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015ec0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016095`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001640f`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall NgcHandler::RsaDecryptWithPkcs1(
        __int64 (__fastcall **this)(EVENT_DESCRIPTOR *, __int64 **),
        void *a2,
        EVENT_DESCRIPTOR *a3,
        __int64 a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 **a10,
        unsigned int *a11)
{
  GUID *v13; // r9
  HRESULT v14; // eax
  bool v15; // bl
  int v16; // esi
  unsigned int v17; // edi
  __int64 *v18; // rcx
  __int64 *v19; // rcx
  __int64 *v20; // rcx
  __int64 *v21; // rcx
  __int64 v22; // rax
  __int128 *v23; // r9
  __int64 v24; // rcx
  _BYTE *v25; // rdx
  _BYTE *v26; // rdx
  __int64 *v27; // rcx
  unsigned __int8 *v28; // rax
  __int64 v29; // rcx
  unsigned __int8 *v30; // rsi
  _BYTE *v31; // rdx
  __int64 *v32; // rcx
  __int64 v33; // rcx
  _BYTE *v34; // rdx
  __int64 *v35; // rcx
  unsigned int v37; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+54h] [rbp-ACh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v41; // [rsp+78h] [rbp-88h] BYREF
  size_t size; // [rsp+80h] [rbp-80h] BYREF
  void *Src; // [rsp+88h] [rbp-78h] BYREF
  bool v44; // [rsp+90h] [rbp-70h]
  int v45; // [rsp+94h] [rbp-6Ch] BYREF
  int v46; // [rsp+98h] [rbp-68h] BYREF
  int v47; // [rsp+9Ch] [rbp-64h] BYREF
  int v48; // [rsp+A0h] [rbp-60h] BYREF
  int v49; // [rsp+A4h] [rbp-5Ch] BYREF
  const unsigned __int8 *v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+B0h] [rbp-50h]
  unsigned __int8 **v52; // [rsp+B8h] [rbp-48h]
  unsigned int *v53; // [rsp+C0h] [rbp-40h]
  int v54; // [rsp+C8h] [rbp-38h] BYREF
  char v55; // [rsp+CCh] [rbp-34h]
  GUID ActivityId; // [rsp+D0h] [rbp-30h] BYREF
  GUID v57; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v58; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h]
  struct _EVENT_DATA_DESCRIPTOR v60; // [rsp+110h] [rbp+10h] BYREF
  __int16 *v61; // [rsp+120h] [rbp+20h]
  int v62; // [rsp+128h] [rbp+28h]
  int v63; // [rsp+12Ch] [rbp+2Ch]
  unsigned int *v64; // [rsp+130h] [rbp+30h]
  __int64 v65; // [rsp+138h] [rbp+38h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+140h] [rbp+40h] BYREF
  __int16 *v67; // [rsp+150h] [rbp+50h]
  __int64 v68; // [rsp+158h] [rbp+58h]
  unsigned int *v69; // [rsp+160h] [rbp+60h]
  __int64 v70; // [rsp+168h] [rbp+68h]
  EVENT_DESCRIPTOR *v71; // [rsp+170h] [rbp+70h]
  __int64 v72; // [rsp+178h] [rbp+78h]
  int *v73; // [rsp+180h] [rbp+80h]
  __int64 v74; // [rsp+188h] [rbp+88h]
  int *v75; // [rsp+190h] [rbp+90h]
  __int64 v76; // [rsp+198h] [rbp+98h]

  v51 = a4;
  v50 = a8;
  v52 = a10;
  v53 = a11;
  v38 = 0;
  v46 = 0;
  v45 = 0;
  v54 = 0;
  v55 = 0;
  if ( (unsigned int)dword_1800BE0B8 > 5
    && (qword_1800BE0C8 & 0x400000000000LL) != 0
    && (qword_1800BE0D0 & 0x400000000000LL) == qword_1800BE0D0 )
  {
    EventActivityIdControl(3u, &ActivityId);
    v57 = ActivityId;
    EventActivityIdControl(4u, &v57);
    v55 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v54 = 1;
  if ( (unsigned int)dword_1800BE0B8 > 5
    && (qword_1800BE0C8 & 0x400000000000LL) != 0
    && (qword_1800BE0D0 & 0x400000000000LL) == qword_1800BE0D0 )
  {
    v48 = v45;
    v49 = v46;
    v40 = v38;
    if ( v55 && (v57.Data1 || *(_DWORD *)&v57.Data2 || *(_DWORD *)v57.Data4 || *(_DWORD *)&v57.Data4[4]) )
      v13 = &v57;
    else
      v13 = 0;
    v75 = &v48;
    v76 = 4;
    v73 = &v49;
    v74 = 4;
    v71 = a3;
    v72 = 16;
    v69 = &v40;
    v70 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0x400000000000LL;
    UserData.Ptr = (ULONGLONG)off_1800BE0C0;
    UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
    UserData.Reserved = 2;
    v67 = word_1800AAE82;
    v68 = 0x100000043LL;
    v37 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, v13, 6u, &UserData);
  }
  UserData.Ptr = (ULONGLONG)&v54;
  *(_QWORD *)&UserData.Size = &v38;
  v67 = (__int16 *)a3;
  v68 = (__int64)&v46;
  v69 = (unsigned int *)&v45;
  LOWORD(v70) = 256;
  v14 = CoInitializeEx(0, 0);
  v15 = v14 >= 0;
  v44 = v14 >= 0;
  v38 = v14;
  if ( v14 >= 0 )
  {
    v41 = 0;
    EventDescriptor = *a3;
    v16 = (*this)(&EventDescriptor, &v41);
    v38 = v16;
    if ( v16 < 0 )
    {
      v18 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
      }
      if ( v15 )
        CoUninitialize();
      wil::details::ScopeExitFnGuard__lambda_49869a5909320b9759bf59d026fb03af___::operator()(&UserData);
      if ( v54 != 1 )
        return (unsigned int)v16;
      if ( v55 )
        EventActivityIdControl(4u, &v57);
      v54 = 2;
      if ( (unsigned int)dword_1800BE0B8 <= 5
        || (qword_1800BE0C8 & 0x400000000000LL) == 0
        || (qword_1800BE0D0 & 0x400000000000LL) != qword_1800BE0D0 )
      {
        return (unsigned int)v16;
      }
      goto LABEL_40;
    }
    v38 = (*(__int64 (__fastcall **)(__int64 *, int *, int *))(*v41 + 72))(v41, &v46, &v45);
    if ( v38 < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 3 )
      {
        v37 = v38;
        v64 = &v37;
        v65 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 3;
        EventDescriptor.Keyword = 0;
        v60.Ptr = (ULONGLONG)off_1800BE0C0;
        v60.Size = *(unsigned __int16 *)off_1800BE0C0;
        v60.Reserved = 2;
        v61 = (__int16 *)&unk_1800AAF20;
        v62 = 38;
        v63 = 1;
        v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v60);
      }
      v38 = 0;
    }
    v47 = 0;
    EventDescriptor = (EVENT_DESCRIPTOR)xmmword_18008F2D8;
    v16 = (*(__int64 (__fastcall **)(__int64 *, EVENT_DESCRIPTOR *, int *))(*v41 + 88))(v41, &EventDescriptor, &v47);
    v38 = v16;
    if ( v16 < 0 )
    {
      v19 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
      }
      goto LABEL_49;
    }
    if ( !v47 )
    {
      v38 = -2147024809;
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v37 = v38;
        v64 = &v37;
        v65 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        v60.Ptr = (ULONGLONG)off_1800BE0C0;
        v60.Size = *(unsigned __int16 *)off_1800BE0C0;
        v60.Reserved = 2;
        v61 = (__int16 *)byte_1800AADF9;
        v62 = 27;
        v63 = 1;
        v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v60);
      }
      v16 = v38;
      v20 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
      }
      goto LABEL_63;
    }
    v58 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v58) = 0;
    v16 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(a6);
    v38 = v16;
    if ( v16 < 0 )
    {
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v58);
      v21 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      }
LABEL_49:
      if ( v15 )
        CoUninitialize();
      wil::details::ScopeExitFnGuard__lambda_49869a5909320b9759bf59d026fb03af___::operator()(&UserData);
      if ( v54 != 1 )
        return (unsigned int)v16;
      if ( v55 )
        EventActivityIdControl(4u, &v57);
      v54 = 2;
      if ( (unsigned int)dword_1800BE0B8 <= 5
        || (qword_1800BE0C8 & 0x400000000000LL) == 0
        || (qword_1800BE0D0 & 0x400000000000LL) != qword_1800BE0D0 )
      {
        return (unsigned int)v16;
      }
LABEL_40:
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 517;
      EventDescriptor.Keyword = 0x400000000000LL;
      v60.Ptr = (ULONGLONG)off_1800BE0C0;
      v60.Size = *(unsigned __int16 *)off_1800BE0C0;
      v60.Reserved = 2;
      v61 = (__int16 *)byte_1800A77D5;
      v62 = 32;
      v63 = 1;
      v37 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_110:
      EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v60);
      return (unsigned int)v16;
    }
    Src = 0;
    LODWORD(size) = 0;
    v22 = *v41;
    v60.Ptr = (ULONGLONG)&Src;
    *(_QWORD *)&v60.Size = 0;
    LOBYTE(v61) = 1;
    v23 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v23 = (__int128 *)v58;
    EventDescriptor = (EVENT_DESCRIPTOR)xmmword_18008F2D8;
    v16 = (*(__int64 (__fastcall **)(__int64 *, EVENT_DESCRIPTOR *, __int64, __int128 *, const unsigned __int8 *, unsigned int, ULONG *, size_t *))(v22 + 392))(
            v41,
            &EventDescriptor,
            v51,
            v23,
            v50,
            a9,
            &v60.Size,
            &size);
    v38 = v16;
    if ( (_BYTE)v61 )
    {
      v24 = *(_QWORD *)&v60.Size;
      v25 = *(_BYTE **)v60.Ptr;
      *(_QWORD *)v60.Ptr = *(_QWORD *)&v60.Size;
      if ( v25 )
        wil::cotaskmem_secure_deleter::operator()<unsigned char>(v24, v25);
      v16 = v38;
    }
    if ( v16 >= 0 )
    {
      v28 = (unsigned __int8 *)MIDL_user_allocate((unsigned int)size);
      v30 = v28;
      if ( !v28 )
      {
        v38 = -2147024882;
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          v37 = v38;
          v64 = &v37;
          v65 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          v60.Ptr = (ULONGLONG)off_1800BE0C0;
          v60.Size = *(unsigned __int16 *)off_1800BE0C0;
          v60.Reserved = 2;
          v61 = &word_1800AADC6;
          v62 = 39;
          v63 = 1;
          v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v60);
        }
        v16 = v38;
        v31 = Src;
        Src = 0;
        if ( v31 )
          wil::cotaskmem_secure_deleter::operator()<unsigned char>(v29, v31);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v58);
        v32 = v41;
        if ( v41 )
        {
          v41 = 0;
          (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
        }
LABEL_63:
        if ( v15 )
          CoUninitialize();
        wil::details::ScopeExitFnGuard__lambda_49869a5909320b9759bf59d026fb03af___::operator()(&UserData);
        if ( v54 == 1 )
        {
          if ( v55 )
            EventActivityIdControl(4u, &v57);
          v54 = 2;
          if ( (unsigned int)dword_1800BE0B8 > 5
            && (qword_1800BE0C8 & 0x400000000000LL) != 0
            && (qword_1800BE0D0 & 0x400000000000LL) == qword_1800BE0D0 )
          {
            goto LABEL_28;
          }
        }
        return (unsigned int)v16;
      }
      memcpy_0(v28, Src, (unsigned int)size);
      *v52 = v30;
      v33 = (__int64)v53;
      *v53 = size;
      v16 = v38;
      v34 = Src;
      Src = 0;
      if ( v34 )
        wil::cotaskmem_secure_deleter::operator()<unsigned char>(v33, v34);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v58);
      v35 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
      }
    }
    else
    {
      v26 = Src;
      Src = 0;
      if ( v26 )
        wil::cotaskmem_secure_deleter::operator()<unsigned char>(v24, v26);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v58);
      v27 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
      }
    }
    if ( v15 )
      CoUninitialize();
    wil::details::ScopeExitFnGuard__lambda_49869a5909320b9759bf59d026fb03af___::operator()(&UserData);
    if ( v54 == 1 )
    {
      if ( v55 )
        EventActivityIdControl(4u, &v57);
      v54 = 2;
      if ( (unsigned int)dword_1800BE0B8 > 5
        && (qword_1800BE0C8 & 0x400000000000LL) != 0
        && (qword_1800BE0D0 & 0x400000000000LL) == qword_1800BE0D0 )
      {
        *(_DWORD *)&EventDescriptor.Level = 517;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x400000000000LL;
        v60.Ptr = (ULONGLONG)off_1800BE0C0;
        v60.Size = *(unsigned __int16 *)off_1800BE0C0;
        v61 = (__int16 *)byte_1800A77D5;
        v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        goto LABEL_109;
      }
    }
    return (unsigned int)v16;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v37 = v38;
    v64 = &v37;
    v65 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    v60.Ptr = (ULONGLONG)off_1800BE0C0;
    v60.Size = *(unsigned __int16 *)off_1800BE0C0;
    v60.Reserved = 2;
    v61 = word_1800AAF52;
    v62 = 47;
    v63 = 1;
    v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v60);
  }
  v16 = v38;
  if ( v15 )
    CoUninitialize();
  wil::details::ScopeExitFnGuard__lambda_49869a5909320b9759bf59d026fb03af___::operator()(&UserData);
  if ( v54 == 1 )
  {
    if ( v55 )
      EventActivityIdControl(4u, &v57);
    v54 = 2;
    if ( (unsigned int)dword_1800BE0B8 > 5
      && (qword_1800BE0C8 & 0x400000000000LL) != 0
      && (qword_1800BE0D0 & 0x400000000000LL) == qword_1800BE0D0 )
    {
LABEL_28:
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 517;
      EventDescriptor.Keyword = 0x400000000000LL;
      v60.Ptr = (ULONGLONG)off_1800BE0C0;
      v60.Size = *(unsigned __int16 *)off_1800BE0C0;
      v61 = (__int16 *)byte_1800A77D5;
      v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_109:
      v60.Reserved = 2;
      v62 = 32;
      v63 = 1;
      v37 = v17;
      goto LABEL_110;
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180015810  mov     [rsp-8+arg_8], rbx
0x180015815  push    rbp
0x180015816  push    rsi
0x180015817  push    rdi
0x180015818  push    r12
0x18001581a  push    r13
0x18001581c  push    r14
0x18001581e  push    r15
0x180015820  lea     rbp, [rsp-0B0h]
0x180015828  sub     rsp, 1B0h
0x18001582f  mov     rax, cs:__security_cookie
0x180015836  xor     rax, rsp
0x180015839  mov     [rbp+0E0h+var_40], rax
0x180015840  mov     [rbp+0E0h+var_130], r9
0x180015844  mov     rsi, r8
0x180015847  mov     r14, rcx
0x18001584a  mov     r15, [rbp+0E0h+arg_20]
0x180015851  mov     r12, [rbp+0E0h+arg_28]
0x180015858  mov     r13, [rbp+0E0h+arg_30]
0x18001585f  mov     rax, [rbp+0E0h+arg_38]
0x180015866  mov     [rbp+0E0h+var_138], rax
0x18001586a  mov     rax, [rbp+0E0h+arg_48]
0x180015871  mov     [rbp+0E0h+var_128], rax
0x180015875  mov     rax, [rbp+0E0h+arg_50]
0x18001587c  mov     [rbp+0E0h+var_120], rax
0x180015880  xor     r8d, r8d
0x180015883  mov     [rsp+1E0h+var_18C], r8d
0x180015888  mov     [rbp+0E0h+var_148], r8d
0x18001588c  mov     [rbp+0E0h+var_14C], r8d
0x180015890  mov     [rbp+0E0h+var_118], r8d
0x180015894  mov     [rbp+0E0h+var_114], r8b
0x180015898  mov     eax, cs:dword_1800BE0B8
0x18001589e  mov     rdx, 400000000000h
0x1800158a8  cmp     eax, 5
0x1800158ab  jbe     short loc_180015910
0x1800158ad  mov     rcx, cs:qword_1800BE0D0
0x1800158b4  mov     rax, cs:qword_1800BE0C8
0x1800158bb  test    rdx, rax
0x1800158be  jz      short loc_180015910
0x1800158c0  mov     rax, rcx
0x1800158c3  and     rax, rdx
0x1800158c6  cmp     rax, rcx
0x1800158c9  jnz     short loc_180015910
0x1800158cb  lea     rdx, [rbp+0E0h+ActivityId]; ActivityId
0x1800158cf  mov     ecx, 3; ControlCode
0x1800158d4  call    cs:__imp_EventActivityIdControl
0x1800158db  nop     dword ptr [rax+rax+00h]
0x1800158e0  movups  xmm0, xmmword ptr [rbp+0E0h+ActivityId.Data1]
0x1800158e4  movups  xmmword ptr [rbp+0E0h+var_100.Data1], xmm0
0x1800158e8  lea     rdx, [rbp+0E0h+var_100]; ActivityId
0x1800158ec  mov     ecx, 4; ControlCode
0x1800158f1  call    cs:__imp_EventActivityIdControl
0x1800158f8  nop     dword ptr [rax+rax+00h]
0x1800158fd  mov     [rbp+0E0h+var_114], 1
0x180015901  mov     rdx, 400000000000h
0x18001590b  xor     r8d, r8d
0x18001590e  jmp     short loc_180015917
0x180015910  xorps   xmm0, xmm0
0x180015913  movups  xmmword ptr [rbp+0E0h+ActivityId.Data1], xmm0
0x180015917  mov     r10d, 1
0x18001591d  mov     [rbp+0E0h+var_118], r10d
0x180015921  mov     eax, cs:dword_1800BE0B8
0x180015927  lea     rdi, _TraceLoggingMetadataEnd
0x18001592e  lea     r11, _TraceLoggingMetadata
0x180015935  cmp     eax, 5
0x180015938  jbe     loc_180015A69
0x18001593e  mov     rcx, cs:qword_1800BE0D0
0x180015945  mov     rax, cs:qword_1800BE0C8
0x18001594c  test    rdx, rax
0x18001594f  jz      loc_180015A69
0x180015955  mov     rax, rcx
0x180015958  and     rax, rdx
0x18001595b  cmp     rax, rcx
0x18001595e  jnz     loc_180015A69
0x180015964  mov     eax, [rbp+0E0h+var_14C]
0x180015967  mov     [rbp+0E0h+var_140], eax
0x18001596a  mov     eax, [rbp+0E0h+var_148]
0x18001596d  mov     [rbp+0E0h+var_13C], eax
0x180015970  mov     eax, [rsp+1E0h+var_18C]
0x180015974  mov     [rsp+1E0h+var_170], eax
0x180015978  cmp     [rbp+0E0h+var_114], 0
0x18001597c  jz      short loc_18001599C
0x18001597e  cmp     [rbp+0E0h+var_100.Data1], 0
0x180015982  jnz     short loc_180015996
0x180015984  cmp     dword ptr [rbp+0E0h+var_100.Data2], 0
0x180015988  jnz     short loc_180015996
0x18001598a  cmp     dword ptr [rbp+0E0h+var_100.Data4], 0
0x18001598e  jnz     short loc_180015996
0x180015990  cmp     dword ptr [rbp+0E0h+var_100.Data4+4], 0
0x180015994  jz      short loc_18001599C
0x180015996  lea     r9, [rbp+0E0h+var_100]
0x18001599a  jmp     short loc_18001599F
0x18001599c  mov     r9, r8; RelatedActivityId
0x18001599f  lea     rax, [rbp+0E0h+var_140]
0x1800159a3  mov     [rbp+0E0h+var_50], rax
0x1800159aa  mov     [rbp+0E0h+var_48], 4
0x1800159b5  lea     rax, [rbp+0E0h+var_13C]
0x1800159b9  mov     [rbp+0E0h+var_60], rax
0x1800159c0  mov     [rbp+0E0h+var_58], 4
0x1800159cb  mov     [rbp+0E0h+var_70], rsi
0x1800159cf  mov     [rbp+0E0h+var_68], 10h
0x1800159d7  lea     rax, [rsp+1E0h+var_170]
0x1800159dc  mov     [rbp+0E0h+var_80], rax
0x1800159e0  mov     [rbp+0E0h+var_78], 4
0x1800159e8  mov     dword ptr [rsp+1E0h+EventDescriptor.Id], 0B000000h
0x1800159f0  movzx   eax, cs:word_1800AAE78
0x1800159f7  mov     dword ptr [rsp+1E0h+EventDescriptor.Level], eax
0x1800159fb  mov     [rsp+1E0h+EventDescriptor.Keyword], rdx
0x180015a00  mov     rax, cs:off_1800BE0C0
0x180015a07  mov     [rbp+0E0h+var_A0.Ptr], rax
0x180015a0b  movzx   eax, word ptr [rax]
0x180015a0e  mov     [rbp+0E0h+var_A0.Size], eax
0x180015a11  mov     dword ptr [rbp+0E0h+var_A0.0Ch], 2
0x180015a18  lea     rax, word_1800AAE82
0x180015a1f  mov     [rbp+0E0h+var_90], rax
0x180015a23  mov     dword ptr [rbp+0E0h+var_88], 43h ; 'C'
0x180015a2a  mov     dword ptr [rbp+0E0h+var_88+4], r10d
0x180015a2e  mov     rax, rdi
0x180015a31  sub     eax, r11d
0x180015a34  mov     [rsp+1E0h+var_190], eax
0x180015a38  mov     eax, [rsp+1E0h+var_190]
0x180015a3c  lea     rax, [rbp+0E0h+var_A0]
0x180015a40  mov     [rsp+1E0h+UserData], rax; UserData
0x180015a45  mov     [rsp+1E0h+UserDataCount], 6; UserDataCount
0x180015a4d  lea     r8, [rbp+0E0h+ActivityId]; ActivityId
0x180015a51  lea     rdx, [rsp+1E0h+EventDescriptor]; EventDescriptor
0x180015a56  mov     rcx, cs:RegHandle; RegHandle
0x180015a5d  call    cs:__imp_EventWriteTransfer
0x180015a64  nop     dword ptr [rax+rax+00h]
0x180015a69  lea     rax, [rbp+0E0h+var_118]
0x180015a6d  mov     [rbp+0E0h+var_A0.Ptr], rax
0x180015a71  lea     rax, [rsp+1E0h+var_18C]
0x180015a76  mov     qword ptr [rbp+0E0h+var_A0.Size], rax
0x180015a7a  mov     [rbp+0E0h+var_90], rsi
0x180015a7e  lea     rax, [rbp+0E0h+var_148]
0x180015a82  mov     [rbp+0E0h+var_88], rax
0x180015a86  lea     rax, [rbp+0E0h+var_14C]
0x180015a8a  mov     [rbp+0E0h+var_80], rax
0x180015a8e  mov     word ptr [rbp+0E0h+var_78], 100h
0x180015a94  xor     bl, bl
0x180015a96  xor     edx, edx; dwCoInit
0x180015a98  xor     ecx, ecx; pvReserved
0x180015a9a  call    cs:__imp_CoInitializeEx
0x180015aa1  nop     dword ptr [rax+rax+00h]
0x180015aa6  movzx   ebx, bl
0x180015aa9  test    eax, eax
0x180015aab  mov     edx, 1
0x180015ab0  cmovns  ebx, edx
0x180015ab3  mov     [rbp+0E0h+var_150], bl
0x180015ab6  mov     [rsp+1E0h+var_18C], eax
0x180015aba  jns     loc_180015C42
0x180015ac0  mov     eax, cs:dword_1800BE0B8
0x180015ac6  cmp     eax, 2
0x180015ac9  jbe     loc_180015B75
0x180015acf  mov     eax, [rsp+1E0h+var_18C]
0x180015ad3  mov     [rsp+1E0h+var_190], eax
0x180015ad7  lea     rax, [rsp+1E0h+var_190]
0x180015adc  mov     [rbp+0E0h+var_B0], rax
0x180015ae0  mov     [rbp+0E0h+var_A8], 4
0x180015ae8  xor     ecx, ecx
0x180015aea  mov     dword ptr [rsp+1E0h+EventDescriptor.Id], 0B000000h
0x180015af2  movzx   eax, cs:word_1800AAF48
0x180015af9  mov     dword ptr [rsp+1E0h+EventDescriptor.Level], eax
0x180015afd  mov     [rsp+1E0h+EventDescriptor.Keyword], rcx
0x180015b02  mov     rax, cs:off_1800BE0C0
0x180015b09  mov     [rbp+0E0h+var_D0.Ptr], rax
0x180015b0d  movzx   eax, word ptr [rax]
0x180015b10  mov     [rbp+0E0h+var_D0.Size], eax
0x180015b13  mov     dword ptr [rbp+0E0h+var_D0.0Ch], 2
0x180015b1a  lea     rax, word_1800AAF52
0x180015b21  mov     [rbp+0E0h+var_C0], rax
0x180015b25  mov     [rbp+0E0h+var_B8], 2Fh ; '/'
0x180015b2c  mov     [rbp+0E0h+var_B4], edx
0x180015b2f  mov     rax, rdi
0x180015b32  lea     r14, _TraceLoggingMetadata
0x180015b39  sub     eax, r14d
0x180015b3c  mov     [rsp+1E0h+var_170], eax
0x180015b40  mov     eax, [rsp+1E0h+var_170]
0x180015b44  lea     rax, [rbp+0E0h+var_D0]
0x180015b48  mov     [rsp+1E0h+UserData], rax; UserData
0x180015b4d  mov     [rsp+1E0h+UserDataCount], 3; UserDataCount
0x180015b55  xor     r9d, r9d; RelatedActivityId
0x180015b58  xor     r8d, r8d; ActivityId
0x180015b5b  lea     rdx, [rsp+1E0h+EventDescriptor]; EventDescriptor
0x180015b60  mov     rcx, cs:RegHandle; RegHandle
0x180015b67  call    cs:__imp_EventWriteTransfer
0x180015b6e  nop     dword ptr [rax+rax+00h]
0x180015b73  jmp     short loc_180015B7C
0x180015b75  lea     r14, _TraceLoggingMetadata
0x180015b7c  mov     esi, [rsp+1E0h+var_18C]
0x180015b80  test    bl, bl
0x180015b82  jz      short loc_180015B91
0x180015b84  call    cs:__imp_CoUninitialize
0x180015b8b  nop     dword ptr [rax+rax+00h]
0x180015b90  nop
0x180015b91  lea     rcx, [rbp+0E0h+var_A0]
0x180015b95  call    wil__details__ScopeExitFnGuard__lambda_49869a5909320b9759bf59d026fb03af_____operator__
0x180015b9a  nop
0x180015b9b  cmp     [rbp+0E0h+var_118], 1
0x180015b9f  jnz     loc_18001651B
0x180015ba5  cmp     [rbp+0E0h+var_114], 0
0x180015ba9  jz      short loc_180015BC0
0x180015bab  lea     rdx, [rbp+0E0h+var_100]; ActivityId
0x180015baf  mov     ecx, 4; ControlCode
0x180015bb4  call    cs:__imp_EventActivityIdControl
0x180015bbb  nop     dword ptr [rax+rax+00h]
0x180015bc0  mov     [rbp+0E0h+var_118], 2
0x180015bc7  mov     eax, cs:dword_1800BE0B8
0x180015bcd  cmp     eax, 5
0x180015bd0  jbe     loc_18001651B
0x180015bd6  mov     rcx, cs:qword_1800BE0D0
0x180015bdd  mov     rax, cs:qword_1800BE0C8
0x180015be4  mov     rdx, 400000000000h
0x180015bee  test    rdx, rax
0x180015bf1  jz      loc_18001651B
0x180015bf7  mov     rax, rcx
0x180015bfa  and     rax, rdx
0x180015bfd  cmp     rax, rcx
0x180015c00  jnz     loc_18001651B
0x180015c06  mov     dword ptr [rsp+1E0h+EventDescriptor.Id], 0B000000h
0x180015c0e  movzx   eax, cs:word_1800A77CB
0x180015c15  mov     dword ptr [rsp+1E0h+EventDescriptor.Level], eax
0x180015c19  mov     [rsp+1E0h+EventDescriptor.Keyword], rdx
0x180015c1e  mov     rax, cs:off_1800BE0C0
0x180015c25  mov     [rbp+0E0h+var_D0.Ptr], rax
0x180015c29  movzx   eax, word ptr [rax]
0x180015c2c  mov     [rbp+0E0h+var_D0.Size], eax
0x180015c2f  lea     rax, byte_1800A77D5
0x180015c36  mov     [rbp+0E0h+var_C0], rax
0x180015c3a  sub     edi, r14d
0x180015c3d  jmp     loc_1800164CE
0x180015c42  mov     [rsp+1E0h+var_168], 0
0x180015c4b  movups  xmm0, xmmword ptr [rsi]
0x180015c4e  movaps  xmmword ptr [rsp+1E0h+EventDescriptor.Id], xmm0
0x180015c53  lea     rdx, [rsp+1E0h+var_168]
0x180015c58  lea     rcx, [rsp+1E0h+EventDescriptor]
0x180015c5d  mov     rax, [r14]
0x180015c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c65  mov     esi, eax
0x180015c67  mov     [rsp+1E0h+var_18C], eax
0x180015c6b  test    eax, eax
0x180015c6d  jns     loc_180015D78
0x180015c73  mov     rcx, [rsp+1E0h+var_168]
0x180015c78  test    rcx, rcx
0x180015c7b  jz      short loc_180015C93
0x180015c7d  mov     [rsp+1E0h+var_168], 0
0x180015c86  mov     rdx, [rcx]
0x180015c89  mov     rax, [rdx+10h]
0x180015c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c92  nop
0x180015c93  test    bl, bl
0x180015c95  jz      short loc_180015CA4
0x180015c97  call    cs:__imp_CoUninitialize
0x180015c9e  nop     dword ptr [rax+rax+00h]
0x180015ca3  nop
0x180015ca4  lea     rcx, [rbp+0E0h+var_A0]
0x180015ca8  call    wil__details__ScopeExitFnGuard__lambda_49869a5909320b9759bf59d026fb03af_____operator__
0x180015cad  nop
0x180015cae  cmp     [rbp+0E0h+var_118], 1
0x180015cb2  jnz     loc_18001651B
0x180015cb8  cmp     [rbp+0E0h+var_114], 0
0x180015cbc  jz      short loc_180015CD3
0x180015cbe  lea     rdx, [rbp+0E0h+var_100]; ActivityId
0x180015cc2  mov     ecx, 4; ControlCode
0x180015cc7  call    cs:__imp_EventActivityIdControl
0x180015cce  nop     dword ptr [rax+rax+00h]
0x180015cd3  mov     [rbp+0E0h+var_118], 2
0x180015cda  mov     eax, cs:dword_1800BE0B8
0x180015ce0  cmp     eax, 5
0x180015ce3  jbe     loc_18001651B
0x180015ce9  mov     rcx, cs:qword_1800BE0D0
0x180015cf0  mov     rax, cs:qword_1800BE0C8
0x180015cf7  mov     rdx, 400000000000h
0x180015d01  test    rdx, rax
0x180015d04  jz      loc_18001651B
0x180015d0a  mov     rax, rcx
0x180015d0d  and     rax, rdx
0x180015d10  cmp     rax, rcx
0x180015d13  jnz     loc_18001651B
0x180015d19  mov     dword ptr [rsp+1E0h+EventDescriptor.Id], 0B000000h
0x180015d21  movzx   eax, cs:word_1800A77CB
0x180015d28  mov     dword ptr [rsp+1E0h+EventDescriptor.Level], eax
0x180015d2c  mov     [rsp+1E0h+EventDescriptor.Keyword], rdx
0x180015d31  mov     rax, cs:off_1800BE0C0
0x180015d38  mov     [rbp+0E0h+var_D0.Ptr], rax
0x180015d3c  movzx   eax, word ptr [rax]
0x180015d3f  mov     [rbp+0E0h+var_D0.Size], eax
0x180015d42  mov     dword ptr [rbp+0E0h+var_D0.0Ch], 2
0x180015d49  lea     rax, byte_1800A77D5
0x180015d50  mov     [rbp+0E0h+var_C0], rax
0x180015d54  mov     [rbp+0E0h+var_B8], 20h ; ' '
0x180015d5b  mov     [rbp+0E0h+var_B4], 1
0x180015d62  lea     rcx, _TraceLoggingMetadata
0x180015d69  sub     edi, ecx
0x180015d6b  mov     [rsp+1E0h+var_190], edi
0x180015d6f  mov     eax, [rsp+1E0h+var_190]
0x180015d73  jmp     loc_1800164EB
0x180015d78  mov     rcx, [rsp+1E0h+var_168]
0x180015d7d  mov     rax, [rcx]
0x180015d80  lea     r8, [rbp+0E0h+var_14C]
  ... truncated ...
```
