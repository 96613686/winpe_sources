# NgcUtils::NgcKeyName::BuildNgcKeyNameString(std::vector<uchar,std::allocator<uchar>> const &,_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180026f30`
- end: `0x180027e92`
- name: `?BuildNgcKeyNameString@NgcKeyName@NgcUtils@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@22PEAV64@@Z`
- size: `3938`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180026db0`
- `0x18002c024`
- `0x18008f210`
- `0x18008f2dc`

## callees

- `0x18000bce0`
- `0x18000e960`
- `0x180016350`
- `0x180026ba0`
- `0x180026f30`
- `0x18002c9ac`
- `0x180053188`
- `0x180053618`
- `0x18005cee0`
- `0x18005d2b0`
- `0x18005dd2c`
- `0x18005dd38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f96`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180027053`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180027e1c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180027053`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180027e1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027064`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027064`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e76`
- `RPCRT4!UuidToStringW` at `0x180027097`
- `RPCRT4!UuidToStringW` at `0x180027097`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026f88`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026f88`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::NgcKeyName::BuildNgcKeyNameString(
        PSID *a1,
        const UUID *a2,
        size_t *a3,
        size_t *a4,
        unsigned __int64 *a5,
        __int64 a6)
{
  signed int LastError; // eax
  unsigned int v10; // ebx
  RPC_STATUS v12; // eax
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  LPWSTR v19; // r15
  unsigned __int64 v20; // r14
  __int16 *v21; // rcx
  unsigned __int64 v22; // r13
  unsigned __int64 v23; // rsi
  char *v24; // rdi
  ULONGLONG p_Src; // rbx
  unsigned __int64 v26; // rdi
  __int16 *v27; // r12
  struct _EVENT_DATA_DESCRIPTOR *v28; // rbx
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  size_t v31; // r8
  size_t v32; // r14
  void *Ptr; // r14
  unsigned __int64 v34; // rdx
  _BYTE *v35; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v36; // rax
  unsigned __int64 v37; // r13
  __int16 *v38; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v39; // r15
  __int16 *v40; // r14
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  size_t v43; // r12
  unsigned __int64 v44; // rdx
  _BYTE *v45; // rcx
  unsigned __int64 v46; // r14
  char *v47; // rdi
  struct _EVENT_DATA_DESCRIPTOR *v48; // rbx
  unsigned __int64 v49; // rdi
  __int16 *v50; // r12
  struct _EVENT_DATA_DESCRIPTOR *v51; // rbx
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rdx
  size_t v54; // r8
  size_t v55; // r14
  unsigned __int64 v56; // rdx
  _BYTE *v57; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v58; // rcx
  unsigned __int64 v59; // r15
  __int16 *v60; // r13
  struct _EVENT_DATA_DESCRIPTOR *v61; // r14
  unsigned __int64 v62; // rcx
  unsigned __int64 v63; // rdx
  size_t v64; // r12
  unsigned __int64 v65; // rdx
  _BYTE *v66; // rcx
  unsigned __int64 v67; // rcx
  const void *v68; // rdx
  char *v69; // rdi
  struct _EVENT_DATA_DESCRIPTOR *v70; // rbx
  unsigned __int64 v71; // rdi
  __int16 *v72; // r12
  struct _EVENT_DATA_DESCRIPTOR *v73; // rbx
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // rdx
  size_t v76; // r8
  size_t v77; // r13
  unsigned __int64 v78; // rdx
  _BYTE *v79; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v80; // rcx
  unsigned __int64 v81; // r15
  __int16 *v82; // r13
  struct _EVENT_DATA_DESCRIPTOR *v83; // r14
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // rdx
  size_t v86; // r12
  unsigned __int64 v87; // rdx
  _BYTE *v88; // rcx
  unsigned __int64 v89; // rcx
  const void *v90; // rdx
  char *v91; // rdi
  struct _EVENT_DATA_DESCRIPTOR *v92; // rbx
  unsigned __int64 v93; // rdi
  __int16 *v94; // r12
  struct _EVENT_DATA_DESCRIPTOR *v95; // rbx
  unsigned __int64 v96; // rcx
  unsigned __int64 v97; // rdx
  size_t v98; // r8
  size_t v99; // r13
  unsigned __int64 v100; // rdx
  _BYTE *v101; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v102; // rcx
  unsigned __int64 v103; // r15
  __int16 *v104; // r13
  struct _EVENT_DATA_DESCRIPTOR *v105; // r14
  unsigned __int64 v106; // rcx
  unsigned __int64 v107; // rdx
  size_t v108; // r12
  unsigned __int64 v109; // rdx
  _BYTE *v110; // rcx
  unsigned __int64 v111; // r12
  const void *v112; // rdx
  struct _EVENT_DATA_DESCRIPTOR *v113; // rbx
  unsigned __int64 v114; // rdi
  char *v115; // rbx
  unsigned __int64 v116; // rcx
  unsigned __int64 v117; // rdx
  size_t v118; // r8
  size_t v119; // r12
  char *v120; // r13
  unsigned __int64 v121; // rdx
  _BYTE *v122; // rcx
  unsigned __int64 v123; // rdx
  unsigned __int64 v124; // rax
  unsigned __int64 v125; // rdx
  _BYTE *v126; // rcx
  void *v127; // [rsp+30h] [rbp-A9h] BYREF
  size_t Size; // [rsp+38h] [rbp-A1h]
  void *v129; // [rsp+40h] [rbp-99h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-91h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-89h] BYREF
  RPC_WSTR StringUuid; // [rsp+60h] [rbp-79h] BYREF
  void *v133; // [rsp+68h] [rbp-71h]
  void *v134; // [rsp+70h] [rbp-69h]
  size_t *v135; // [rsp+78h] [rbp-61h]
  size_t *v136; // [rsp+80h] [rbp-59h]
  unsigned __int64 *v137; // [rsp+88h] [rbp-51h]
  EVENT_DESCRIPTOR v138; // [rsp+90h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR Src; // [rsp+A0h] [rbp-39h] BYREF
  __int16 *v140; // [rsp+B0h] [rbp-29h]
  unsigned __int64 v141; // [rsp+B8h] [rbp-21h]
  void **v142; // [rsp+C0h] [rbp-19h]
  __int64 v143; // [rsp+C8h] [rbp-11h]

  v133 = a4;
  v129 = a3;
  v134 = a5;
  *(_QWORD *)&v138.Id = a6;
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*a1, &StringSid) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_7;
    LODWORD(v129) = v10;
    v142 = &v129;
    v143 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    Src.Ptr = (ULONGLONG)off_180122078;
    Src.Size = *(unsigned __int16 *)off_180122078;
    Src.Reserved = 2;
    v140 = (__int16 *)&unk_180107C38;
    v141 = 0x10000002BLL;
    LODWORD(v127) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_6:
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &Src);
LABEL_7:
    if ( StringSid )
      LocalFree(StringSid);
    return v10;
  }
  StringUuid = 0;
  v12 = UuidToStringW(a2, &StringUuid);
  v10 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_7;
    LODWORD(v127) = v10;
    v142 = &v127;
    v143 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    Src.Ptr = (ULONGLONG)off_180122078;
    Src.Size = *(unsigned __int16 *)off_180122078;
    Src.Reserved = 2;
    v140 = (__int16 *)&byte_180107BBF;
    v141 = 0x100000033LL;
    LODWORD(v129) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    goto LABEL_6;
  }
  *(_QWORD *)&EventDescriptor.Id = &StringUuid;
  LOWORD(EventDescriptor.Keyword) = 256;
  v13 = -1;
  do
    ++v13;
  while ( StringSid[v13] );
  v14 = -1;
  do
    ++v14;
  while ( StringUuid[v14] );
  v15 = v14 + v13;
  if ( v14 + v13 < v13
    || (v135 = a3 + 2, v16 = v15 + a3[2], v16 < v15)
    || (v136 = a4 + 2, v17 = v16 + a4[2], v17 < v16)
    || (v137 = a5 + 2, v18 = v17 + a5[2], v18 < v17)
    || v18 + 4 < v18 )
  {
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  }
  Src = 0;
  v140 = 0;
  v141 = 7;
  LOWORD(Src.Ptr) = 0;
  std::wstring::reserve(&Src);
  v19 = StringSid;
  v20 = -1;
  do
    ++v20;
  while ( StringSid[v20] );
  v21 = v140;
  Size = (size_t)v140;
  v22 = v141;
  v23 = 0x7FFFFFFFFFFFFFFELL;
  if ( v20 > v141 - (unsigned __int64)v140 )
  {
    if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v140 < v20 )
      goto LABEL_219;
    v27 = (__int16 *)((char *)v140 + v20);
    v29 = ((unsigned __int64)v140 + v20) | 7;
    if ( v29 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v30 = v141 >> 1;
      if ( v141 <= 0x7FFFFFFFFFFFFFFELL - (v141 >> 1) )
      {
        v26 = v30 + v141;
        if ( v29 >= v30 + v141 )
          v26 = ((unsigned __int64)v140 + v20) | 7;
      }
      else
      {
        v26 = 0x7FFFFFFFFFFFFFFELL;
      }
    }
    else
    {
      v26 = 0x7FFFFFFFFFFFFFFELL;
    }
    v28 = (struct _EVENT_DATA_DESCRIPTOR *)std::allocator<unsigned short>::allocate(v29, v26 + 1);
    v140 = v27;
    v141 = v26;
    v31 = 2 * Size;
    v32 = 2 * v20;
    Size = v32;
    v127 = (char *)v28 + v31;
    if ( v22 <= 7 )
    {
      memcpy_0(v28, &Src, v31);
      memcpy_0(v127, v19, v32);
      *((_WORD *)&v28->Ptr + (_QWORD)v27) = 0;
    }
    else
    {
      Ptr = (void *)Src.Ptr;
      memcpy_0(v28, (const void *)Src.Ptr, v31);
      memcpy_0(v127, v19, Size);
      *((_WORD *)&v28->Ptr + (_QWORD)v27) = 0;
      v34 = 2 * v22 + 2;
      if ( v34 < 0x1000 )
      {
        operator delete(Ptr, v34);
      }
      else
      {
        v35 = (_BYTE *)*((_QWORD *)Ptr - 1);
        if ( (unsigned __int64)((_BYTE *)Ptr - v35 - 8) > 0x1F )
          goto LABEL_191;
        operator delete(v35, 2 * v22 + 41);
      }
    }
    Src.Ptr = (ULONGLONG)v28;
  }
  else
  {
    v24 = (char *)v140 + v20;
    v140 = (__int16 *)((char *)v140 + v20);
    p_Src = (ULONGLONG)&Src;
    if ( v141 > 7 )
      p_Src = Src.Ptr;
    memmove_0((void *)(p_Src + 2LL * (_QWORD)v21), StringSid, 2 * v20);
    *(_WORD *)(p_Src + 2LL * (_QWORD)v24) = 0;
    v26 = v141;
    v27 = v140;
    v28 = (struct _EVENT_DATA_DESCRIPTOR *)Src.Ptr;
  }
  if ( (unsigned __int64)v27 >= v26 )
  {
    if ( v27 == (__int16 *)0x7FFFFFFFFFFFFFFELL )
      goto LABEL_219;
    v40 = (__int16 *)((char *)v27 + 1);
    v127 = (char *)v27 + 1;
    v41 = ((unsigned __int64)v27 + 1) | 7;
    if ( v41 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v42 = v26 >> 1;
      if ( v26 <= 0x7FFFFFFFFFFFFFFELL - (v26 >> 1) )
      {
        v37 = v42 + v26;
        if ( v41 >= v42 + v26 )
          v37 = ((unsigned __int64)v27 + 1) | 7;
      }
      else
      {
        v37 = 0x7FFFFFFFFFFFFFFELL;
      }
    }
    else
    {
      v37 = 0x7FFFFFFFFFFFFFFELL;
    }
    v39 = (struct _EVENT_DATA_DESCRIPTOR *)std::allocator<unsigned short>::allocate(v41, v37 + 1);
    v140 = (__int16 *)((char *)v27 + 1);
    v141 = v37;
    v43 = 2LL * (_QWORD)v27;
    if ( v26 <= 7 )
    {
      memcpy_0(v39, &Src, v43);
      *(_DWORD *)((char *)&v39->Ptr + v43) = 47;
    }
    else
    {
      memcpy_0(v39, v28, v43);
      *(_DWORD *)((char *)&v39->Ptr + v43) = 47;
      v44 = 2 * v26 + 2;
      if ( v44 < 0x1000 )
      {
        operator delete(v28, v44);
      }
      else
      {
        v45 = *(_BYTE **)&v28[-1].Size;
        if ( (unsigned __int64)((char *)v28 - v45 - 8) > 0x1F )
          goto LABEL_191;
        operator delete(v45, 2 * v26 + 41);
      }
    }
    v38 = v40;
    Src.Ptr = (ULONGLONG)v39;
  }
  else
  {
    v140 = (__int16 *)((char *)v27 + 1);
    v36 = &Src;
    if ( v26 > 7 )
      v36 = v28;
    *(_DWORD *)((char *)&v36->Ptr + 2 * (_QWORD)v27) = 47;
    v37 = v141;
    v38 = v140;
    v127 = v140;
    v39 = (struct _EVENT_DATA_DESCRIPTOR *)Src.Ptr;
  }
  Size = (size_t)StringUuid;
  v46 = -1;
  do
    ++v46;
  while ( StringUuid[v46] );
  if ( v46 > v37 - (unsigned __int64)v38 )
  {
    if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v38 < v46 )
      goto LABEL_219;
    v50 = (__int16 *)((char *)v38 + v46);
    v52 = ((unsigned __int64)v38 + v46) | 7;
    if ( v52 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v53 = v37 >> 1;
      if ( v37 <= 0x7FFFFFFFFFFFFFFELL - (v37 >> 1) )
      {
        v49 = v53 + v37;
        if ( v52 >= v53 + v37 )
          v49 = v52;
      }
      else
      {
        v49 = 0x7FFFFFFFFFFFFFFELL;
      }
    }
    else
    {
      v49 = 0x7FFFFFFFFFFFFFFELL;
    }
    v51 = (struct _EVENT_DATA_DESCRIPTOR *)std::allocator<unsigned short>::allocate(v52, v49 + 1);
    v140 = v50;
    v141 = v49;
    v54 = 2LL * (_QWORD)v127;
    v55 = 2 * v46;
    v127 = (char *)v51 + 2 * (_QWORD)v127;
    if ( v37 <= 7 )
    {
      memcpy_0(v51, &Src, v54);
      memcpy_0(v127, (const void *)Size, v55);
      *((_WORD *)&v51->Ptr + (_QWORD)v50) = 0;
    }
    else
    {
      memcpy_0(v51, v39, v54);
      memcpy_0(v127, (const void *)Size, v55);
      *((_WORD *)&v51->Ptr + (_QWORD)v50) = 0;
      v56 = 2 * v37 + 2;
      if ( v56 < 0x1000 )
      {
        operator delete(v39, v56);
      }
      else
      {
        v57 = *(_BYTE **)&v39[-1].Size;
        if ( (unsigned __int64)((char *)v39 - v57 - 8) > 0x1F )
          goto LABEL_191;
        operator delete(v57, 2 * v37 + 41);
      }
    }
    Src.Ptr = (ULONGLONG)v51;
  }
  else
  {
    v47 = (char *)v38 + v46;
    v140 = (__int16 *)((char *)v38 + v46);
    v48 = &Src;
    if ( v37 > 7 )
      v48 = v39;
    memmove_0((char *)v48 + 2 * (_QWORD)v38, StringUuid, 2 * v46);
    *((_WORD *)&v48->Ptr + (_QWORD)v47) = 0;
    v49 = v141;
    v50 = v140;
    v51 = (struct _EVENT_DATA_DESCRIPTOR *)Src.Ptr;
  }
  if ( (unsigned __int64)v50 >= v49 )
  {
    if ( v50 == (__int16 *)0x7FFFFFFFFFFFFFFELL )
      goto LABEL_219;
    v60 = (__int16 *)((char *)v50 + 1);
    v62 = ((unsigned __int64)v50 + 1) | 7;
    if ( v62 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v63 = v49 >> 1;
      if ( v49 <= 0x7FFFFFFFFFFFFFFELL - (v49 >> 1) )
      {
        v59 = v63 + v49;
        if ( v62 >= v63 + v49 )
          v59 = ((unsigned __int64)v50 + 1) | 7;
      }
      else
      {
        v59 = 0x7FFFFFFFFFFFFFFELL;
      }
    }
    else
    {
      v59 = 0x7FFFFFFFFFFFFFFELL;
    }
    v61 = (struct _EVENT_DATA_DESCRIPTOR *)std::allocator<unsigned short>::allocate(v62, v59 + 1);
    v140 = (__int16 *)((char *)v50 + 1);
    v141 = v59;
    v64 = 2LL * (_QWORD)v50;
    if ( v49 <= 7 )
    {
      memcpy_0(v61, &Src, v64);
      *(_DWORD *)((char *)&v61->Ptr + v64) = 47;
    }
    else
    {
      memcpy_0(v61, v51, v64);
      *(_DWORD *)((char *)&v61->Ptr + v64) = 47;
      v65 = 2 * v49 + 2;
      if ( v65 < 0x1000 )
      {
        operator delete(v51, v65);
      }
      else
      {
        v66 = *(_BYTE **)&v51[-1].Size;
        if ( (unsigned __int64)((char *)v51 - v66 - 8) > 0x1F )
          goto LABEL_191;
        operator delete(v66, 2 * v49 + 41);
      }
    }
    Src.Ptr = (ULONGLONG)v61;
  }
  else
  {
    v140 = (__int16 *)((char *)v50 + 1);
    v58 = &Src;
    if ( v49 > 7 )
      v58 = v51;
    *(_DWORD *)((char *)&v58->Ptr + 2 * (_QWORD)v50) = 47;
    v59 = v141;
    v60 = v140;
    v61 = (struct _EVENT_DATA_DESCRIPTOR *)Src.Ptr;
  }
  v67 = *v135;
  Size = *v135;
  v68 = v129;
  if ( *((_QWORD *)v129 + 3) > 7u )
  {
    v68 = *(const void **)v129;
    v129 = *(void **)v129;
  }
  if ( v67 > v59 - (unsigned __int64)v60 )
  {
    if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v60 < v67 )
      goto LABEL_219;
    v72 = (__int16 *)((char *)v60 + v67);
    v74 = ((unsigned __int64)v60 + v67) | 7;
    if ( v74 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v75 = v59 >> 1;
      if ( v59 <= 0x7FFFFFFFFFFFFFFELL - (v59 >> 1) )
      {
        v71 = v59 + v75;
        if ( v74 >= v59 + v75 )
          v71 = v74;
      }
      else
      {
        v71 = 0x7FFFFFFFFFFFFFFELL;
      }
    }
    else
    {
      v71 = 0x7FFFFFFFFFFFFFFELL;
    }
    v73 = (struct _EVENT_DATA_DESCRIPTOR *)std::allocator<unsigned short>::allocate(v74, v71 + 1);
    v140 = v72;
    v141 = v71;
    v76 = 2LL * (_QWORD)v60;
    v77 = 2 * Size;
    Size = (size_t)v73 + v76;
    if ( v59 <= 7 )
    {
      memcpy_0(v73, &Src, v76);
      memcpy_0((void *)Size, v129, v77);
      *((_WORD *)&v73->Ptr + (_QWORD)v72) = 0;
    }
    else
    {
      memcpy_0(v73, v61, v76);
      memcpy_0((void *)Size, v129, v77);
      *((_WORD *)&v73->Ptr + (_QWORD)v72) = 0;
      v78 = 2 * v59 + 2;
      if ( v78 < 0x1000 )
      {
        operator delete(v61, v78);
      }
      else
      {
        v79 = *(_BYTE **)&v61[-1].Size;
        if ( (unsigned __int64)((char *)v61 - v79 - 8) > 0x1F )
          goto LABEL_191;
        operator delete(v79, 2 * v59 + 41);
      }
    }
    Src.Ptr = (ULONGLONG)v73;
  }
  else
  {
    v69 = (char *)v60 + v67;
    v140 = (__int16 *)((char *)v60 + v67);
    v70 = &Src;
    if ( v59 > 7 )
      v70 = v61;
    memmove_0((char *)v70 + 2 * (_QWORD)v60, v68, 2 * v67);
    *((_WORD *)&v70->Ptr + (_QWORD)v69) = 0;
    v71 = v141;
    v72 = v140;
    v73 = (struct _EVENT_DATA_DESCRIPTOR *)Src.Ptr;
  }
  if ( (unsigned __int64)v72 >= v71 )
  {
    if ( v72 == (__int16 *)0x7FFFFFFFFFFFFFFELL )
      goto LABEL_219;
    v82 = (__int16 *)((char *)v72 + 1);
    v84 = ((unsigned __int64)v72 + 1) | 7;
    if ( v84 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v85 = v71 >> 1;
      if ( v71 <= 0x7FFFFFFFFFFFFFFELL - (v71 >> 1) )
      {
        v81 = v71 + v85;
        if ( v84 >= v71 + v85 )
          v81 = ((unsigned __int64)v72 + 1) | 7;
      }
      else
      {
        v81 = 0x7FFFFFFFFFFFFFFELL;
      }
    }
    else
    {
      v81 = 0x7FFFFFFFFFFFFFFELL;
    }
    v83 = (struct _EVENT_DATA_DESCRIPTOR *)std::allocator<unsigned short>::allocate(v84, v81 + 1);
    v140 = (__int16 *)((char *)v72 + 1);
    v141 = v81;
    v86 = 2LL * (_QWORD)v72;
    if ( v71 <= 7 )
    {
      memcpy_0(v83, &Src, v86);
      *(_DWORD *)((char *)&v83->Ptr + v86) = 47;
    }
    else
    {
      memcpy_0(v83, v73, v86);
      *(_DWORD *)((char *)&v83->Ptr + v86) = 47;
      v87 = 2 * v71 + 2;
      if ( v87 < 0x1000 )
      {
        operator delete(v73, v87);
      }
      else
      {
        v88 = *(_BYTE **)&v73[-1].Size;
        if ( (unsigned __int64)((char *)v73 - v88 - 8) > 0x1F )
          goto LABEL_191;
        operator delete(v88, 2 * v71 + 41);
      }
    }
    Src.Ptr = (ULONGLONG)v83;
  }
  else
  {
    v140 = (__int16 *)((char *)v72 + 1);
    v80 = &Src;
    if ( v71 > 7 )
      v80 = v73;
    *(_DWORD *)((char *)&v80->Ptr + 2 * (_QWORD)v72) = 47;
    v81 = v141;
    v82 = v140;
    v83 = (struct _EVENT_DATA_DESCRIPTOR *)Src.Ptr;
  }
  v89 = *v136;
  Size = *v136;
  v90 = v133;
  if ( *((_QWORD *)v133 + 3) > 7u )
  {
    v90 = *(const void **)v133;
    v133 = *(void **)v133;
  }
  if ( v89 > v81 - (unsigned __int64)v82 )
  {
    if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v82 < v89 )
      goto LABEL_219;
    v94 = (__int16 *)((char *)v82 + v89);
    v96 = ((unsigned __int64)v82 + v89) | 7;
    if ( v96 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v97 = v81 >> 1;
      if ( v81 <= 0x7FFFFFFFFFFFFFFELL - (v81 >> 1) )
      {
        v93 = v81 + v97;
        if ( v96 >= v81 + v97 )
          v93 = v96;
      }
      else
      {
        v93 = 0x7FFFFFFFFFFFFFFELL;
      }
    }
    else
    {
      v93 = 0x7FFFFFFFFFFFFFFELL;
    }
    v95 = (struct _EVENT_DATA_DESCRIPTOR *)std::allocator<unsigned short>::allocate(v96, v93 + 1);
    v140 = v94;
    v141 = v93;
    v98 = 2LL * (_QWORD)v82;
    v99 = 2 * Size;
    Size = (size_t)v95 + v98;
    if ( v81 <= 7 )
    {
      memcpy_0(v95, &Src, v98);
      memcpy_0((void *)Size, v133, v99);
      *((_WORD *)&v95->Ptr + (_QWORD)v94) = 0;
    }
    else
    {
      memcpy_0(v95, v83, v98);
      memcpy_0((void *)Size, v133, v99);
      *((_WORD *)&v95->Ptr + (_QWORD)v94) = 0;
      v100 = 2 * v81 + 2;
      if ( v100 < 0x1000 )
      {
        operator delete(v83, v100);
      }
      else
      {
        v101 = *(_BYTE **)&v83[-1].Size;
        if ( (unsigned __int64)((char *)v83 - v101 - 8) > 0x1F )
          goto LABEL_191;
        operator delete(v101, 2 * v81 + 41);
      }
    }
    Src.Ptr = (ULONGLONG)v95;
  }
  else
  {
    v91 = (char *)v82 + v89;
    v140 = (__int16 *)((char *)v82 + v89);
    v92 = &Src;
    if ( v81 > 7 )
      v92 = v83;
    memmove_0((char *)v92 + 2 * (_QWORD)v82, v90, 2 * v89);
    *((_WORD *)&v92->Ptr + (_QWORD)v91) = 0;
    v93 = v141;
    v94 = v140;
    v95 = (struct _EVENT_DATA_DESCRIPTOR *)Src.Ptr;
  }
  if ( (unsigned __int64)v94 >= v93 )
  {
    if ( v94 == (__int16 *)0x7FFFFFFFFFFFFFFELL )
      goto LABEL_219;
    v104 = (__int16 *)((char *)v94 + 1);
    v106 = ((unsigned __int64)v94 + 1) | 7;
    if ( v106 <= 0x7FFFFFFFFFFFFFFELL )
    {
      v107 = v93 >> 1;
      if ( v93 <= 0x7FFFFFFFFFFFFFFELL - (v93 >> 1) )
      {
        v103 = v107 + v93;
        if ( v106 >= v107 + v93 )
          v103 = ((unsigned __int64)v94 + 1) | 7;
      }
      else
      {
        v103 = 0x7FFFFFFFFFFFFFFELL;
      }
    }
    else
    {
      v103 = 0x7FFFFFFFFFFFFFFELL;
    }
    v105 = (struct _EVENT_DATA_DESCRIPTOR *)std::allocator<unsigned short>::allocate(v106, v103 + 1);
    v140 = (__int16 *)((char *)v94 + 1);
    v141 = v103;
    v108 = 2LL * (_QWORD)v94;
    if ( v93 <= 7 )
    {
      memcpy_0(v105, &Src, v108);
      *(_DWORD *)((char *)&v105->Ptr + v108) = 47;
    }
    else
    {
      memcpy_0(v105, v95, v108);
      *(_DWORD *)((char *)&v105->Ptr + v108) = 47;
      v109 = 2 * v93 + 2;
      if ( v109 < 0x1000 )
      {
        operator delete(v95, v109);
      }
      else
      {
        v110 = *(_BYTE **)&v95[-1].Size;
        if ( (unsigned __int64)((char *)v95 - v110 - 8) > 0x1F )
          goto LABEL_191;
        operator delete(v110, 2 * v93 + 41);
      }
    }
    Src.Ptr = (ULONGLONG)v105;
  }
  else
  {
    v140 = (__int16 *)((char *)v94 + 1);
    v102 = &Src;
    if ( v93 > 7 )
      v102 = v95;
    *(_DWORD *)((char *)&v102->Ptr + 2 * (_QWORD)v94) = 47;
    v103 = v141;
    v104 = v140;
    v105 = (struct _EVENT_DATA_DESCRIPTOR *)Src.Ptr;
  }
  v111 = *v137;
  v112 = v134;
  if ( *((_QWORD *)v134 + 3) > 7u )
  {
    v112 = *(const void **)v134;
    v134 = *(void **)v134;
  }
  if ( v111 <= v103 - (unsigned __int64)v104 )
  {
    v140 = (__int16 *)((char *)v104 + v111);
    v113 = &Src;
    if ( v103 > 7 )
      v113 = v105;
    memmove_0((char *)v113 + 2 * (_QWORD)v104, v112, 2 * v111);
    *((_WORD *)&v113->Ptr + (_QWORD)v104 + v111) = 0;
    v23 = v141;
    v114 = (unsigned __int64)v140;
    v115 = (char *)Src.Ptr;
    goto LABEL_195;
  }
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v104 < v111 )
LABEL_219:
    std::_Xlen_string();
  v114 = (unsigned __int64)v104 + v111;
  v116 = ((unsigned __int64)v104 + v111) | 7;
  if ( v116 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v117 = v103 >> 1;
    if ( v103 <= 0x7FFFFFFFFFFFFFFELL - (v103 >> 1) )
    {
      v23 = v117 + v103;
      if ( v116 >= v117 + v103 )
        v23 = ((unsigned __int64)v104 + v111) | 7;
    }
  }
  v115 = (char *)std::allocator<unsigned short>::allocate(v116, v23 + 1);
  v140 = (__int16 *)((char *)v104 + v111);
  v141 = v23;
  v118 = 2LL * (_QWORD)v104;
  v119 = 2 * v111;
  v120 = &v115[2 * (_QWORD)v104];
  if ( v103 <= 7 )
  {
    memcpy_0(v115, &Src, v118);
    memcpy_0(v120, v134, v119);
    *(_WORD *)&v115[2 * v114] = 0;
    goto LABEL_194;
  }
  memcpy_0(v115, v105, v118);
  memcpy_0(v120, v134, v119);
  *(_WORD *)&v115[2 * v114] = 0;
  v121 = 2 * v103 + 2;
  if ( v121 < 0x1000 )
  {
    operator delete(v105, v121);
    goto LABEL_194;
  }
  v122 = *(_BYTE **)&v105[-1].Size;
  if ( (unsigned __int64)((char *)v105 - v122 - 8) > 0x1F )
LABEL_191:
    __fastfail(5u);
  operator delete(v122, 2 * v103 + 41);
LABEL_194:
  Src.Ptr = (ULONGLONG)v115;
LABEL_195:
  v123 = -1;
  v124 = -1;
  do
    ++v124;
  while ( StringSid[v124] );
  if ( v124 > 0xFF )
    goto LABEL_207;
  do
    ++v123;
  while ( StringUuid[v123] );
  if ( v123 > 0x24 || *v135 > 0x104 || *v136 > 0x104 || *v137 > 0x104 || v114 > 0x433 )
  {
LABEL_207:
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v127) = -2147024809;
      v142 = &v127;
      v143 = 4;
      *(_DWORD *)&v138.Id = 184549376;
      *(_DWORD *)&v138.Level = 2;
      v138.Keyword = 0;
      Src.Ptr = (ULONGLONG)off_180122078;
      Src.Size = *(unsigned __int16 *)off_180122078;
      Src.Reserved = 2;
      v140 = &word_180107BFE;
      v141 = 0x10000002ELL;
      LODWORD(v129) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v138, 0, 0, 3u, &Src);
    }
    if ( v23 > 7 )
    {
      v125 = 2 * v23 + 2;
      if ( v125 < 0x1000 )
      {
        v126 = v115;
      }
      else
      {
        v126 = (_BYTE *)*((_QWORD *)v115 - 1);
        if ( (unsigned __int64)(v115 - v126 - 8) > 0x1F )
          __fastfail(5u);
        v125 = 2 * v23 + 41;
      }
      operator delete(v126, v125);
    }
    wil::details::ScopeExitFnGuard__lambda_47662b00bdbf2f665ead014a30a3fc65___::operator()(&EventDescriptor);
    if ( StringSid )
      LocalFree(StringSid);
    return 2147942487LL;
  }
  else
  {
    std::wstring::operator=(*(_QWORD *)&v138.Id, &Src);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&Src);
    wil::details::ScopeExitFnGuard__lambda_47662b00bdbf2f665ead014a30a3fc65___::operator()(&EventDescriptor);
    if ( StringSid )
      LocalFree(StringSid);
    return 0;
  }
}

```

## disassembly

```asm
0x180026f30  push    rbp
0x180026f32  push    rbx
0x180026f33  push    rsi
0x180026f34  push    rdi
0x180026f35  push    r12
0x180026f37  push    r13
0x180026f39  push    r14
0x180026f3b  push    r15
0x180026f3d  lea     rbp, [rsp-0Fh]
0x180026f42  sub     rsp, 0E8h
0x180026f49  mov     rax, cs:__security_cookie
0x180026f50  xor     rax, rsp
0x180026f53  mov     [rbp+47h+var_50], rax
0x180026f57  mov     rdi, r9
0x180026f5a  mov     [rbp+47h+var_B8], r9
0x180026f5e  mov     r13, r8
0x180026f61  mov     [rsp+120h+var_E0], r8
0x180026f66  mov     rbx, rdx
0x180026f69  mov     r12, [rbp+47h+arg_20]
0x180026f6d  mov     [rbp+47h+var_B0], r12
0x180026f71  mov     rax, [rbp+47h+arg_28]
0x180026f75  mov     qword ptr [rbp+47h+var_90.Id], rax
0x180026f79  xor     esi, esi
0x180026f7b  mov     [rsp+120h+StringSid], rsi
0x180026f80  lea     rdx, [rsp+120h+StringSid]; StringSid
0x180026f85  mov     rcx, [rcx]; Sid
0x180026f88  call    cs:__imp_ConvertSidToStringSidW
0x180026f8e  test    eax, eax
0x180026f90  jnz     loc_18002708C
0x180026f96  call    cs:__imp_GetLastError
0x180026f9c  mov     ebx, eax
0x180026f9e  test    eax, eax
0x180026fa0  jle     short loc_180026FAB
0x180026fa2  movzx   ebx, ax
0x180026fa5  or      ebx, 80070000h
0x180026fab  mov     eax, cs:dword_180122070
0x180026fb1  cmp     eax, 2
0x180026fb4  jbe     loc_18002705A
0x180026fba  mov     dword ptr [rsp+120h+var_E0], ebx
0x180026fbe  lea     rax, [rsp+120h+var_E0]
0x180026fc3  mov     [rbp+47h+var_60], rax
0x180026fc7  mov     [rbp+47h+var_58], 4
0x180026fcf  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x180026fd7  movzx   eax, cs:word_180107C2E
0x180026fde  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x180026fe2  mov     [rsp+120h+EventDescriptor.Keyword], rsi
0x180026fe7  mov     rax, cs:off_180122078
0x180026fee  mov     [rbp+47h+Src.Ptr], rax
0x180026ff2  movzx   eax, word ptr [rax]
0x180026ff5  mov     [rbp+47h+Src.Size], eax
0x180026ff8  mov     dword ptr [rbp+47h+Src.0Ch], 2
0x180026fff  lea     rax, unk_180107C38
0x180027006  mov     [rbp+47h+var_70], rax
0x18002700a  mov     dword ptr [rbp+47h+var_68], 2Bh ; '+'
0x180027011  mov     dword ptr [rbp+47h+var_68+4], 1
0x180027018  lea     rax, _TraceLoggingMetadataEnd
0x18002701f  lea     rcx, _TraceLoggingMetadata
0x180027026  sub     eax, ecx
0x180027028  mov     dword ptr [rsp+120h+var_F0], eax
0x18002702c  mov     eax, dword ptr [rsp+120h+var_F0]
0x180027030  lea     rax, [rbp+47h+Src]
0x180027034  mov     [rsp+120h+UserData], rax; UserData
0x180027039  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x180027041  xor     r9d, r9d; RelatedActivityId
0x180027044  xor     r8d, r8d; ActivityId
0x180027047  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x18002704c  mov     rcx, cs:RegHandle; RegHandle
0x180027053  call    cs:__imp_EventWriteTransfer
0x180027059  nop
0x18002705a  mov     rcx, [rsp+120h+StringSid]; hMem
0x18002705f  test    rcx, rcx
0x180027062  jz      short loc_18002706A
0x180027064  call    cs:__imp_LocalFree
0x18002706a  mov     eax, ebx
0x18002706c  mov     rcx, [rbp+47h+var_50]
0x180027070  xor     rcx, rsp; StackCookie
0x180027073  call    __security_check_cookie
0x180027078  add     rsp, 0E8h
0x18002707f  pop     r15
0x180027081  pop     r14
0x180027083  pop     r13
0x180027085  pop     r12
0x180027087  pop     rdi
0x180027088  pop     rsi
0x180027089  pop     rbx
0x18002708a  pop     rbp
0x18002708b  retn
0x18002708c  mov     [rbp+47h+StringUuid], rsi
0x180027090  lea     rdx, [rbp+47h+StringUuid]; StringUuid
0x180027094  mov     rcx, rbx; Uuid
0x180027097  call    cs:__imp_UuidToStringW
0x18002709d  mov     ebx, eax
0x18002709f  test    eax, eax
0x1800270a1  jz      loc_180027138
0x1800270a7  jle     short loc_1800270B2
0x1800270a9  movzx   ebx, ax
0x1800270ac  or      ebx, 80070000h
0x1800270b2  mov     eax, cs:dword_180122070
0x1800270b8  cmp     eax, 2
0x1800270bb  jbe     short loc_18002705A
0x1800270bd  mov     dword ptr [rsp+120h+var_F0], ebx
0x1800270c1  lea     rax, [rsp+120h+var_F0]
0x1800270c6  mov     [rbp+47h+var_60], rax
0x1800270ca  mov     [rbp+47h+var_58], 4
0x1800270d2  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x1800270da  movzx   eax, cs:word_180107BB5
0x1800270e1  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x1800270e5  mov     [rsp+120h+EventDescriptor.Keyword], rsi
0x1800270ea  mov     rax, cs:off_180122078
0x1800270f1  mov     [rbp+47h+Src.Ptr], rax
0x1800270f5  movzx   eax, word ptr [rax]
0x1800270f8  mov     [rbp+47h+Src.Size], eax
0x1800270fb  mov     dword ptr [rbp+47h+Src.0Ch], 2
0x180027102  lea     rax, byte_180107BBF
0x180027109  mov     [rbp+47h+var_70], rax
0x18002710d  mov     dword ptr [rbp+47h+var_68], 33h ; '3'
0x180027114  mov     dword ptr [rbp+47h+var_68+4], 1
0x18002711b  lea     rax, _TraceLoggingMetadataEnd
0x180027122  lea     rcx, _TraceLoggingMetadata
0x180027129  sub     eax, ecx
0x18002712b  mov     dword ptr [rsp+120h+var_E0], eax
0x18002712f  mov     eax, dword ptr [rsp+120h+var_E0]
0x180027133  jmp     loc_180027030
0x180027138  lea     rax, [rbp+47h+StringUuid]
0x18002713c  mov     qword ptr [rsp+120h+EventDescriptor.Id], rax
0x180027141  mov     word ptr [rsp+120h+EventDescriptor.Keyword], 100h
0x180027148  mov     rcx, [rsp+120h+StringSid]
0x18002714d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180027154  mov     rax, rbx
0x180027157  nop     word ptr [rax+rax+00000000h]
0x180027160  inc     rax
0x180027163  cmp     word ptr [rcx+rax*2], 0
0x180027168  jnz     short loc_180027160
0x18002716a  mov     rdx, [rbp+47h+StringUuid]
0x18002716e  mov     rcx, rbx
0x180027171  lea     rcx, [rcx+1]
0x180027175  cmp     word ptr [rdx+rcx*2], 0
0x18002717a  jnz     short loc_180027171
0x18002717c  lea     rdx, [rcx+rax]
0x180027180  cmp     rdx, rax
0x180027183  jb      loc_180027E8C
0x180027189  lea     rax, [r13+10h]
0x18002718d  mov     [rbp+47h+var_A8], rax
0x180027191  mov     rcx, [rax]
0x180027194  add     rcx, rdx
0x180027197  cmp     rcx, rdx
0x18002719a  jb      loc_180027E8C
0x1800271a0  lea     rax, [rdi+10h]
0x1800271a4  mov     [rbp+47h+var_A0], rax
0x1800271a8  mov     rdx, [rax]
0x1800271ab  add     rdx, rcx
0x1800271ae  cmp     rdx, rcx
0x1800271b1  jb      loc_180027E8C
0x1800271b7  lea     rax, [r12+10h]
0x1800271bc  mov     [rbp+47h+var_98], rax
0x1800271c0  mov     rcx, [rax]
0x1800271c3  add     rcx, rdx
0x1800271c6  cmp     rcx, rdx
0x1800271c9  jb      loc_180027E8C
0x1800271cf  lea     rdx, [rcx+4]
0x1800271d3  cmp     rdx, rcx
0x1800271d6  jb      loc_180027E8C
0x1800271dc  xorps   xmm0, xmm0
0x1800271df  movups  xmmword ptr [rbp+47h+Src.Ptr], xmm0
0x1800271e3  mov     [rbp+47h+var_70], rsi
0x1800271e7  mov     [rbp+47h+var_68], 7
0x1800271ef  mov     word ptr [rbp+47h+Src.Ptr], si
0x1800271f3  lea     rcx, [rbp+47h+Src]; Src
0x1800271f7  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x1800271fc  mov     r15, [rsp+120h+StringSid]
0x180027201  mov     r14, rbx
0x180027204  inc     r14
0x180027207  cmp     word ptr [r15+r14*2], 0
0x18002720d  jnz     short loc_180027204
0x18002720f  mov     rcx, [rbp+47h+var_70]
0x180027213  mov     [rsp+120h+Size], rcx
0x180027218  mov     r13, [rbp+47h+var_68]
0x18002721c  mov     rax, r13
0x18002721f  sub     rax, rcx
0x180027222  mov     rsi, 7FFFFFFFFFFFFFFEh
0x18002722c  cmp     r14, rax
0x18002722f  ja      short loc_18002726D
0x180027231  lea     rdi, [r14+rcx]
0x180027235  mov     [rbp+47h+var_70], rdi
0x180027239  lea     rbx, [rbp+47h+Src]
0x18002723d  cmp     r13, 7
0x180027241  cmova   rbx, [rbp+47h+Src.Ptr]
0x180027246  lea     r8, [r14+r14]; Size
0x18002724a  lea     rcx, [rbx+rcx*2]; void *
0x18002724e  mov     rdx, r15; Src
0x180027251  call    memmove_0
0x180027256  xor     eax, eax
0x180027258  mov     [rbx+rdi*2], ax
0x18002725c  mov     rdi, [rbp+47h+var_68]
0x180027260  mov     r12, [rbp+47h+var_70]
0x180027264  mov     rbx, [rbp+47h+Src.Ptr]
0x180027268  jmp     loc_18002736D
0x18002726d  mov     rax, rsi
0x180027270  sub     rax, rcx
0x180027273  cmp     rax, r14
0x180027276  jb      loc_180027E86
0x18002727c  lea     r12, [r14+rcx]
0x180027280  mov     rcx, r12
0x180027283  or      rcx, 7
0x180027287  cmp     rcx, rsi
0x18002728a  jbe     short loc_180027291
0x18002728c  mov     rdi, rsi
0x18002728f  jmp     short loc_1800272B2
0x180027291  mov     rdx, r13
0x180027294  shr     rdx, 1
0x180027297  mov     rax, rsi
0x18002729a  sub     rax, rdx
0x18002729d  cmp     r13, rax
0x1800272a0  jbe     short loc_1800272A7
0x1800272a2  mov     rdi, rsi
0x1800272a5  jmp     short loc_1800272B2
0x1800272a7  lea     rdi, [rdx+r13]
0x1800272ab  cmp     rcx, rdi
0x1800272ae  cmovnb  rdi, rcx
0x1800272b2  lea     rdx, [rdi+1]
0x1800272b6  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x1800272bb  mov     rbx, rax
0x1800272be  mov     [rbp+47h+var_70], r12
0x1800272c2  mov     [rbp+47h+var_68], rdi
0x1800272c6  mov     rax, [rsp+120h+Size]
0x1800272cb  lea     r8, [rax+rax]; Size
0x1800272cf  add     r14, r14
0x1800272d2  mov     [rsp+120h+Size], r14
0x1800272d7  lea     rax, [r8+rbx]
0x1800272db  mov     [rsp+120h+var_F0], rax
0x1800272e0  mov     rcx, rbx; void *
0x1800272e3  cmp     r13, 7
0x1800272e7  jbe     short loc_180027349
0x1800272e9  mov     r14, [rbp+47h+Src.Ptr]
0x1800272ed  mov     rdx, r14; Src
0x1800272f0  call    memcpy_0
0x1800272f5  mov     r8, [rsp+120h+Size]; Size
0x1800272fa  mov     rdx, r15; Src
0x1800272fd  mov     rcx, [rsp+120h+var_F0]; void *
0x180027302  call    memcpy_0
0x180027307  xor     eax, eax
0x180027309  mov     [rbx+r12*2], ax
0x18002730e  lea     rdx, ds:2[r13*2]; unsigned __int64
0x180027316  cmp     rdx, 1000h
0x18002731d  jb      short loc_18002733F
0x18002731f  mov     rcx, [r14-8]; void *
0x180027323  sub     r14, rcx
0x180027326  sub     r14, 8
0x18002732a  cmp     r14, 1Fh
0x18002732e  ja      loc_180027C9A
0x180027334  add     rdx, 27h ; '''; unsigned __int64
0x180027338  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002733d  jmp     short loc_180027369
0x18002733f  mov     rcx, r14; void *
0x180027342  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027347  jmp     short loc_180027369
0x180027349  lea     rdx, [rbp+47h+Src]; Src
0x18002734d  call    memcpy_0
0x180027352  mov     r8, r14; Size
0x180027355  mov     rdx, r15; Src
0x180027358  mov     rcx, [rsp+120h+var_F0]; void *
0x18002735d  call    memcpy_0
0x180027362  xor     eax, eax
0x180027364  mov     [rbx+r12*2], ax
0x180027369  mov     [rbp+47h+Src.Ptr], rbx
0x18002736d  cmp     r12, rdi
0x180027370  jnb     short loc_1800273A7
0x180027372  lea     rax, [r12+1]
0x180027377  mov     [rbp+47h+var_70], rax
0x18002737b  lea     rax, [rbp+47h+Src]
0x18002737f  cmp     rdi, 7
0x180027383  cmova   rax, rbx
0x180027387  lea     rcx, [rax+r12*2]
0x18002738b  mov     dword ptr [rcx], 2Fh ; '/'
0x180027391  mov     r13, [rbp+47h+var_68]
0x180027395  mov     rcx, [rbp+47h+var_70]
0x180027399  mov     [rsp+120h+var_F0], rcx
0x18002739e  mov     r15, [rbp+47h+Src.Ptr]
0x1800273a2  jmp     loc_180027479
0x1800273a7  mov     rax, rsi
0x1800273aa  sub     rax, r12
0x1800273ad  cmp     rax, 1
0x1800273b1  jb      loc_180027E86
0x1800273b7  lea     r14, [r12+1]
0x1800273bc  mov     [rsp+120h+var_F0], r14
0x1800273c1  mov     rcx, r14
0x1800273c4  or      rcx, 7
0x1800273c8  cmp     rcx, rsi
0x1800273cb  jbe     short loc_1800273D2
0x1800273cd  mov     r13, rsi
0x1800273d0  jmp     short loc_1800273F3
0x1800273d2  mov     rdx, rdi
0x1800273d5  shr     rdx, 1
0x1800273d8  mov     rax, rsi
0x1800273db  sub     rax, rdx
0x1800273de  cmp     rdi, rax
0x1800273e1  jbe     short loc_1800273E8
0x1800273e3  mov     r13, rsi
0x1800273e6  jmp     short loc_1800273F3
0x1800273e8  lea     r13, [rdx+rdi]
  ... truncated ...
```
