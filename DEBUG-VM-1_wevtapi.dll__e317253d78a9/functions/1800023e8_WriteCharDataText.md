# WriteCharDataText

- ea: `0x1800023e8`
- end: `0x180003144`
- name: `WriteCharDataText`
- size: `3420`
- prototype: `__int64 __fastcall(WriteBuffer *this)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800031f0`
- `0x180004070`

## callees

- `0x180001548`
- `0x180001d58`
- `0x1800020f0`
- `0x1800023e8`
- `0x180003780`
- `0x180008b20`
- `0x18000a724`
- `0x18000b864`
- `0x18000b9e0`
- `0x18000c404`
- `0x18000c44c`
- `0x18000c6f0`
- `0x18000e56c`
- `0x18000f378`
- `0x18001c6e4`
- `0x18001e754`
- `0x18001ecac`
- `0x180023548`
- `0x1800249f0`
- `0x180025514`
- `0x180038fb4`
- `0x180038fcc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000288d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000288d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002a20`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002e5d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002a20`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002e5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800028b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800028b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WriteCharDataText(WriteBuffer *this, float *a2, char a3, __int64 a4)
{
  WriteBuffer *v5; // rbx
  unsigned int v6; // edi
  unsigned __int64 v7; // rsi
  unsigned int v8; // edi
  unsigned int v9; // edi
  unsigned int v10; // edi
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // r9
  wchar_t *v14; // r13
  __int64 v15; // r14
  unsigned int v16; // edi
  unsigned int v17; // edi
  unsigned int v18; // edi
  unsigned int v19; // edi
  unsigned int v20; // edi
  unsigned int v21; // edi
  unsigned int v22; // edi
  unsigned int v23; // edi
  unsigned int v24; // edi
  unsigned int v25; // edi
  unsigned int v26; // edi
  unsigned int v27; // edi
  __int64 v28; // r14
  char *v29; // r8
  __int64 v30; // rdx
  char v31; // cl
  __int64 v32; // rax
  __int64 v33; // r9
  __int64 i; // rcx
  unsigned int v35; // edi
  HLOCAL v36; // rdx
  unsigned int v37; // r9d
  __int64 v38; // r9
  char *v39; // rcx
  __int64 v40; // rax
  wchar_t *p_Buffer; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  char *v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rax
  struct _FILETIME *p_FileTime; // rdx
  __int64 v48; // r8
  unsigned int v49; // ebx
  unsigned int v50; // edx
  int v51; // [rsp+30h] [rbp-D0h]
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  char v53; // [rsp+40h] [rbp-C0h]
  __int128 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h]
  int v56; // [rsp+60h] [rbp-A0h]
  int v57; // [rsp+64h] [rbp-9Ch]
  int v58; // [rsp+68h] [rbp-98h]
  struct _FILETIME FileTime; // [rsp+70h] [rbp-90h] BYREF
  WriteBuffer *v60; // [rsp+78h] [rbp-88h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  unsigned int v62[2]; // [rsp+88h] [rbp-78h]
  __int64 v63; // [rsp+90h] [rbp-70h] BYREF
  char v64; // [rsp+98h] [rbp-68h] BYREF
  char v65; // [rsp+A8h] [rbp-58h] BYREF
  char v66; // [rsp+B8h] [rbp-48h] BYREF
  char v67; // [rsp+C8h] [rbp-38h] BYREF
  char v68[16]; // [rsp+D8h] [rbp-28h] BYREF
  char v69[16]; // [rsp+E8h] [rbp-18h] BYREF
  char v70; // [rsp+F8h] [rbp-8h] BYREF
  char v71; // [rsp+108h] [rbp+8h] BYREF
  char v72[16]; // [rsp+118h] [rbp+18h] BYREF
  SYSTEMTIME v73; // [rsp+128h] [rbp+28h] BYREF
  __int128 v74; // [rsp+138h] [rbp+38h] BYREF
  SYSTEMTIME SystemTime; // [rsp+148h] [rbp+48h] BYREF
  __int128 pSid; // [rsp+158h] [rbp+58h] BYREF
  __int64 v77; // [rsp+168h] [rbp+68h]
  int v78; // [rsp+170h] [rbp+70h]
  int v79; // [rsp+174h] [rbp+74h]
  int v80; // [rsp+178h] [rbp+78h]
  wchar_t Buffer; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v82[72]; // [rsp+1A2h] [rbp+A2h] BYREF
  __int16 v83; // [rsp+1EAh] [rbp+EAh]

  *(_QWORD *)&SystemTime.wYear = a4;
  v53 = a3;
  v5 = this;
  v60 = this;
  v6 = *((_DWORD *)a2 + 3);
  v7 = 0;
  if ( (v6 & 0x80u) != 0 )
  {
    if ( !a4 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
      }
      pSid = 0;
      v77 = 0;
      v78 = 13;
      v79 = -1;
      v80 = 363;
      throw (EvtException *)&pSid;
    }
    v32 = *((_QWORD *)this + 1);
    v33 = *((unsigned int *)this + 4);
    for ( i = v33 - 2; ; i -= 2 )
    {
      v61 = i;
      if ( i <= 0 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
        }
        pSid = 0;
        v77 = 0;
        v78 = 13;
        v79 = -1;
        v80 = 384;
        throw (EvtException *)&pSid;
      }
      if ( *(_WORD *)(v32 + i) == 60 )
        break;
    }
    v35 = v6 & 0xFFFFFF7F;
    v36 = *(HLOCAL *)a2;
    hMem = v36;
    *(_QWORD *)v62 = (unsigned int)(v33 - i);
    v37 = 0;
    v51 = 0;
    while ( 1 )
    {
      if ( v37 >= *((_DWORD *)a2 + 2) )
        return;
      if ( v35 > 0xB )
      {
        switch ( v35 )
        {
          case 0xCu:
            if ( snwprintf_s(&Buffer, 0x28u, 0xFFFFFFFFFFFFFFFFuLL, L"%.32g", *(_QWORD *)(*(_QWORD *)a2 + 8LL * v37)) == -1 )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
              }
              pSid = 0;
              v77 = 0;
              v78 = 13;
              v79 = -1;
              v80 = 462;
              throw (EvtException *)&pSid;
            }
            v42 = -1;
            do
              ++v42;
            while ( *(_WORD *)&v82[2 * v42 - 2] );
LABEL_168:
            p_Buffer = &Buffer;
LABEL_169:
            v37 = v51;
            goto LABEL_170;
          case 0xDu:
            v42 = 5LL - (*(_DWORD *)(*(_QWORD *)a2 + 4LL * v37) != 0);
            p_Buffer = L"true";
            if ( !*(_DWORD *)(*(_QWORD *)a2 + 4LL * v37) )
              p_Buffer = L"false";
LABEL_170:
            if ( !v42 )
              goto LABEL_173;
            goto LABEL_171;
          case 0xFu:
            v74 = *(_OWORD *)(*(_QWORD *)a2 + 16LL * v37);
            Buffer = 123;
            tlx::guid_to_string_lower<wchar_t>(v82, &v74);
            v83 = 125;
            p_Buffer = &Buffer;
            LODWORD(v42) = 38;
            goto LABEL_171;
          case 0x10u:
            goto LABEL_173;
          case 0x11u:
            v63 = *(_QWORD *)(*(_QWORD *)a2 + 8LL * v37);
            p_FileTime = (struct _FILETIME *)&v63;
LABEL_159:
            tlx::filetime_to_string<wchar_t>(&Buffer, p_FileTime);
            p_Buffer = &Buffer;
            LODWORD(v42) = 28;
LABEL_171:
            WriteBuffer::Write(v5, p_Buffer, 2 * v42);
            goto LABEL_172;
          case 0x12u:
            v73 = *(SYSTEMTIME *)(*(_QWORD *)a2 + 16LL * v37);
            FileTime = 0;
            SystemTimeToFileTime(&v73, &FileTime);
            p_FileTime = &FileTime;
            goto LABEL_159;
          case 0x14u:
            v40 = ToWcharsHex<unsigned int>(
                    &pExceptionObject,
                    &Buffer,
                    40,
                    *(unsigned int *)(*(_QWORD *)a2 + 4LL * v37));
            goto LABEL_122;
          case 0x15u:
            v40 = ToWcharsHex<unsigned __int64>(v72, &Buffer, 40, *(_QWORD *)(*(_QWORD *)a2 + 8LL * v37));
            goto LABEL_122;
        }
        if ( v35 != 35 )
        {
LABEL_183:
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
          }
          pSid = 0;
          v77 = 0;
          v78 = 13;
          v79 = -1;
          v80 = 527;
          throw (EvtException *)&pSid;
        }
        v46 = -1;
        do
          ++v46;
        while ( *((_WORD *)v36 + v46) );
      }
      else
      {
        if ( v35 == 11 )
        {
          if ( snwprintf_s(&Buffer, 0x28u, 0xFFFFFFFFFFFFFFFFuLL, L"%.16g", *(float *)(*(_QWORD *)a2 + 4LL * v37)) == -1 )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
            }
            pSid = 0;
            v77 = 0;
            v78 = 13;
            v79 = -1;
            v80 = 452;
            throw (EvtException *)&pSid;
          }
          v42 = -1;
          do
            ++v42;
          while ( *(_WORD *)&v82[2 * v42 - 2] );
          goto LABEL_168;
        }
        if ( v35 > 6 )
        {
          if ( v35 != 7 )
          {
            if ( v35 != 8 )
            {
              if ( v35 == 9 )
                v40 = ToWchars<__int64,10>(v69, &Buffer, 40, *(_QWORD *)(*(_QWORD *)a2 + 8LL * v37));
              else
                v40 = ToWchars<unsigned __int64,10>(v68, &Buffer, 40, *(_QWORD *)(*(_QWORD *)a2 + 8LL * v37));
LABEL_122:
              p_Buffer = *(wchar_t **)v40;
              v42 = *(_QWORD *)(v40 + 8);
              goto LABEL_169;
            }
            v43 = *(unsigned int *)(*(_QWORD *)a2 + 4LL * v37);
            v44 = &v70;
            goto LABEL_124;
          }
          v38 = *(unsigned int *)(*(_QWORD *)a2 + 4LL * v37);
          v39 = &v71;
LABEL_121:
          v40 = ToWchars<int,10>(v39, &Buffer, 40, v38);
          goto LABEL_122;
        }
        if ( v35 == 6 )
        {
          v43 = *(unsigned __int16 *)(*(_QWORD *)a2 + 2LL * v37);
          v44 = &v67;
          goto LABEL_124;
        }
        if ( v35 != 1 )
        {
          if ( v35 == 2 )
          {
            v45 = -1;
            do
              ++v45;
            while ( *((_BYTE *)v36 + v45) );
            *(_QWORD *)&v74 = v45;
            WriteStringText_char_(v5);
            hMem = (char *)hMem + (unsigned int)v74 + 1;
            goto LABEL_172;
          }
          if ( v35 != 3 )
          {
            if ( v35 != 4 )
            {
              if ( v35 != 5 )
                goto LABEL_183;
              v38 = (unsigned int)*(__int16 *)(*(_QWORD *)a2 + 2LL * v37);
              v39 = &v64;
              goto LABEL_121;
            }
            v43 = *(unsigned __int8 *)(v37 + *(_QWORD *)a2);
            v44 = &v65;
LABEL_124:
            v40 = ToWchars<unsigned int,10>(v44, &Buffer, 40, v43);
            goto LABEL_122;
          }
          v38 = (unsigned int)*(char *)(v37 + *(_QWORD *)a2);
          v39 = &v66;
          goto LABEL_121;
        }
        v46 = -1;
        do
          ++v46;
        while ( *((_WORD *)v36 + v46) );
      }
      *(_QWORD *)&v74 = v46;
      WriteStringText_wchar_t_(v5);
      hMem = (char *)hMem + 2 * (unsigned int)v74 + 2;
LABEL_172:
      v37 = v51;
LABEL_173:
      v51 = ++v37;
      if ( v37 < *((_DWORD *)a2 + 2) )
      {
        WriteBuffer::Write(v5, L"</", 4u);
        v48 = -1;
        do
          ++v48;
        while ( *(_WORD *)(*(_QWORD *)&SystemTime.wYear + 2 * v48) );
        WriteBuffer::Write(v5, *(const void *const *)&SystemTime.wYear, 2 * v48);
        WriteBuffer::Write(v5, L">", 2u);
        v49 = *((_DWORD *)v5 + 4);
        WriteBuffer::SetCurrentIndex(v60, v49 + v62[0]);
        v50 = v49;
        v5 = v60;
        WriteBuffer::SetCurrentIndex(v60, v50);
        WriteBuffer::Write(v5, (const void *const)(*((_QWORD *)v5 + 1) + v61), v62[0]);
        v37 = v51;
      }
      v36 = hMem;
    }
  }
  if ( v6 <= 0xB )
  {
    if ( v6 != 11 )
    {
      if ( v6 > 5 )
      {
        v16 = v6 - 6;
        if ( !v16 )
        {
          v11 = *(unsigned __int16 *)a2;
          goto LABEL_12;
        }
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( !v18 )
          {
            v11 = *(unsigned int *)a2;
            goto LABEL_12;
          }
          v19 = v18 - 1;
          if ( !v19 )
          {
            v12 = ToWchars<__int64,10>(&v73, &Buffer, 40, *(_QWORD *)a2);
            goto LABEL_15;
          }
          if ( v19 == 1 )
          {
            v12 = ToWchars<unsigned __int64,10>(&v73, &Buffer, 40, *(_QWORD *)a2);
            goto LABEL_15;
          }
LABEL_64:
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
          }
          pExceptionObject = 0;
          v55 = 0;
          v56 = 13;
          v57 = -1;
          v58 = 351;
          throw (EvtException *)&pExceptionObject;
        }
        v13 = *(unsigned int *)a2;
LABEL_14:
        v12 = ToWchars<int,10>(&v73, &Buffer, 40, v13);
        goto LABEL_15;
      }
      if ( v6 == 5 )
      {
        v13 = (unsigned int)*(__int16 *)a2;
        goto LABEL_14;
      }
      if ( !v6 )
        return;
      v8 = v6 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( !v9 )
        {
          WriteStringText_char_(this);
          return;
        }
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 == 1 )
          {
            v11 = *(unsigned __int8 *)a2;
LABEL_12:
            v12 = ToWchars<unsigned int,10>(&v73, &Buffer, 40, v11);
LABEL_15:
            v14 = *(wchar_t **)v12;
            v15 = *(_QWORD *)(v12 + 8);
            goto LABEL_92;
          }
          goto LABEL_64;
        }
        v13 = (unsigned int)*(char *)a2;
        goto LABEL_14;
      }
LABEL_18:
      WriteStringText_wchar_t_(this);
      return;
    }
    v15 = -1;
    if ( snwprintf_s(&Buffer, 0x28u, 0xFFFFFFFFFFFFFFFFuLL, L"%.7g", *a2) == -1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
      }
      pExceptionObject = 0;
      v55 = 0;
      v56 = 13;
      v57 = -1;
      v58 = 249;
      throw (EvtException *)&pExceptionObject;
    }
    do
      ++v15;
    while ( *(_WORD *)&v82[2 * v15 - 2] );
    goto LABEL_91;
  }
  if ( v6 > 0x11 )
  {
    v24 = v6 - 18;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( !v26 )
        {
          v12 = ToWcharsHex<unsigned int>(&v73, &Buffer, 40, *(unsigned int *)a2);
          goto LABEL_15;
        }
        v27 = v26 - 1;
        if ( !v27 )
        {
          v12 = ToWcharsHex<unsigned __int64>(&v73, &Buffer, 40, *(_QWORD *)a2);
          goto LABEL_15;
        }
        if ( v27 != 14 )
          goto LABEL_64;
        goto LABEL_18;
      }
      if ( *((_DWORD *)a2 + 2) <= 0x44u )
      {
        memcpy_0(&pSid, *(const void **)a2, *((unsigned int *)a2 + 2));
        hMem = 0;
        if ( IsValidSid(&pSid) )
        {
          hMem = 0;
          if ( ConvertSidToStringSidW(&pSid, (LPWSTR *)&hMem) )
          {
            if ( hMem )
            {
              v28 = -1;
              do
                ++v28;
              while ( *((_WORD *)hMem + v28) );
              WriteBuffer::Write(v5, hMem, 2 * v28);
              if ( hMem )
                LocalFree(hMem);
              return;
            }
          }
        }
        __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&hMem);
      }
      goto LABEL_81;
    }
    SystemTime = *(SYSTEMTIME *)*(_QWORD *)a2;
    hMem = 0;
    SystemTimeToFileTime(&SystemTime, (LPFILETIME)&hMem);
    tlx::filetime_to_string<wchar_t>(&Buffer, &hMem);
    v15 = 28;
LABEL_91:
    v14 = &Buffer;
    goto LABEL_92;
  }
  if ( v6 == 17 )
  {
    tlx::filetime_to_string<wchar_t>(&Buffer, a2);
    v14 = &Buffer;
    LODWORD(v15) = 28;
    goto LABEL_93;
  }
  v20 = v6 - 12;
  if ( !v20 )
  {
    v15 = -1;
    if ( snwprintf_s(&Buffer, 0x28u, 0xFFFFFFFFFFFFFFFFuLL, L"%.15g", *(_QWORD *)a2) == -1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
      }
      pExceptionObject = 0;
      v55 = 0;
      v56 = 13;
      v57 = -1;
      v58 = 258;
      throw (EvtException *)&pExceptionObject;
    }
    do
      ++v15;
    while ( *(_WORD *)&v82[2 * v15 - 2] );
    goto LABEL_91;
  }
  v21 = v20 - 1;
  if ( v21 )
  {
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( v23 )
      {
        if ( v23 == 1 )
          return;
        goto LABEL_64;
      }
      SystemTime = *(SYSTEMTIME *)*(_QWORD *)a2;
      Buffer = 123;
      tlx::guid_to_string_lower<wchar_t>(v82, &SystemTime);
      v83 = 125;
      v14 = &Buffer;
      LODWORD(v15) = 38;
LABEL_93:
      WriteBuffer::Write(v5, v14, 2 * v15);
      return;
    }
LABEL_81:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                             &pExceptionObject,
                             (unsigned int)(2 * *((_DWORD *)a2 + 2))) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 14);
      }
      pSid = 0;
      v77 = 0;
      v78 = 14;
      v79 = -1;
      v80 = 338;
      throw (EvtException *)&pSid;
    }
    v29 = *(char **)a2;
    if ( 2LL * *((unsigned int *)a2 + 2) )
    {
      do
      {
        v30 = pExceptionObject;
        v31 = *v29;
        *(_WORD *)(pExceptionObject + 2 * v7) = a0123456789abcd_0[(unsigned __int64)(unsigned __int8)*v29 >> 4];
        *(_WORD *)(v30 + 2 * v7 + 2) = a0123456789abcd_0[v31 & 0xF];
        v7 += 2LL;
        ++v29;
      }
      while ( v7 < 2 * (unsigned __int64)*((unsigned int *)a2 + 2) );
    }
    WriteBuffer::Write(
      v5,
      (const void *const)pExceptionObject,
      2 * ((__int64)(*((_QWORD *)&pExceptionObject + 1) - pExceptionObject) >> 1));
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&pExceptionObject);
    return;
  }
  v14 = L"true";
  if ( !*(_DWORD *)a2 )
    v14 = L"false";
  v15 = 5LL - (*(_DWORD *)a2 != 0);
LABEL_92:
  if ( v15 )
    goto LABEL_93;
}

```

## disassembly

```asm
0x1800023e8  push    rbp
0x1800023ea  push    rbx
0x1800023eb  push    rsi
0x1800023ec  push    rdi
0x1800023ed  push    r12
0x1800023ef  push    r13
0x1800023f1  push    r14
0x1800023f3  push    r15
0x1800023f5  lea     rbp, [rsp-108h]
0x1800023fd  sub     rsp, 208h
0x180002404  mov     rax, cs:__security_cookie
0x18000240b  xor     rax, rsp
0x18000240e  mov     [rbp+140h+var_50], rax
0x180002415  mov     rax, r9
0x180002418  mov     qword ptr [rbp+140h+SystemTime.wYear], rax
0x18000241c  mov     [rsp+240h+var_200], r8b
0x180002421  mov     r15, rdx
0x180002424  mov     rbx, rcx
0x180002427  mov     [rsp+240h+var_1C8], rcx
0x18000242c  mov     edi, [rdx+0Ch]
0x18000242f  xor     esi, esi
0x180002431  test    dil, dil
0x180002434  js      loc_180002A61
0x18000243a  cmp     edi, 0Bh
0x18000243d  ja      loc_180002626
0x180002443  jz      loc_180002573
0x180002449  cmp     edi, 5
0x18000244c  ja      loc_180002503
0x180002452  jz      loc_1800024FD
0x180002458  test    edi, edi
0x18000245a  jz      short loc_1800024C9
0x18000245c  sub     edi, 1
0x18000245f  jz      loc_1800024EC
0x180002465  sub     edi, 1
0x180002468  jz      short loc_1800024BA
0x18000246a  sub     edi, 1
0x18000246d  jz      short loc_180002494
0x18000246f  cmp     edi, 1
0x180002472  jnz     loc_1800027B9
0x180002478  movzx   r9d, byte ptr [rdx]
0x18000247c  mov     r8d, 28h ; '('
0x180002482  lea     rdx, [rbp+140h+Buffer]
0x180002489  lea     rcx, [rbp+140h+var_118]
0x18000248d  call    ??$ToWchars@I$09@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_KI@Z; ToWchars<uint,10>(wchar_t *,unsigned __int64,uint)
0x180002492  jmp     short loc_1800024AE
0x180002494  movsx   r9d, byte ptr [rdx]
0x180002498  mov     r8d, 28h ; '('
0x18000249e  lea     rdx, [rbp+140h+Buffer]
0x1800024a5  lea     rcx, [rbp+140h+var_118]
0x1800024a9  call    ??$ToWchars@H$09@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_KH@Z; ToWchars<int,10>(wchar_t *,unsigned __int64,int)
0x1800024ae  mov     r13, [rax]
0x1800024b1  mov     r14, [rax+8]
0x1800024b5  jmp     loc_180002A44
0x1800024ba  mov     r9b, r8b
0x1800024bd  mov     r8d, [rdx+8]
0x1800024c1  mov     rdx, [rdx]
0x1800024c4  call    WriteStringText_char_
0x1800024c9  mov     rcx, [rbp+140h+var_50]
0x1800024d0  xor     rcx, rsp; StackCookie
0x1800024d3  call    __security_check_cookie
0x1800024d8  add     rsp, 208h
0x1800024df  pop     r15
0x1800024e1  pop     r14
0x1800024e3  pop     r13
0x1800024e5  pop     r12
0x1800024e7  pop     rdi
0x1800024e8  pop     rsi
0x1800024e9  pop     rbx
0x1800024ea  pop     rbp
0x1800024eb  retn
0x1800024ec  mov     r9b, r8b
0x1800024ef  mov     r8d, [rdx+8]
0x1800024f3  mov     rdx, [rdx]
0x1800024f6  call    WriteStringText_wchar_t_
0x1800024fb  jmp     short loc_1800024C9
0x1800024fd  movsx   r9d, word ptr [rdx]
0x180002501  jmp     short loc_180002498
0x180002503  sub     edi, 6
0x180002506  jz      short loc_18000256A
0x180002508  sub     edi, 1
0x18000250b  jz      short loc_180002562
0x18000250d  sub     edi, 1
0x180002510  jz      short loc_18000255A
0x180002512  sub     edi, 1
0x180002515  jz      short loc_18000253C
0x180002517  cmp     edi, 1
0x18000251a  jnz     loc_1800027B9
0x180002520  mov     r9, [rdx]
0x180002523  lea     r8d, [rdi+27h]
0x180002527  lea     rdx, [rbp+140h+Buffer]
0x18000252e  lea     rcx, [rbp+140h+var_118]
0x180002532  call    ??$ToWchars@_K$09@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_K1@Z; ToWchars<unsigned __int64,10>(wchar_t *,unsigned __int64,unsigned __int64)
0x180002537  jmp     loc_1800024AE
0x18000253c  mov     r9, [rdx]
0x18000253f  mov     r8d, 28h ; '('
0x180002545  lea     rdx, [rbp+140h+Buffer]
0x18000254c  lea     rcx, [rbp+140h+var_118]
0x180002550  call    ??$ToWchars@_J$09@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_K_J@Z; ToWchars<__int64,10>(wchar_t *,unsigned __int64,__int64)
0x180002555  jmp     loc_1800024AE
0x18000255a  mov     r9d, [rdx]
0x18000255d  jmp     loc_18000247C
0x180002562  mov     r9d, [rdx]
0x180002565  jmp     loc_180002498
0x18000256a  movzx   r9d, word ptr [rdx]
0x18000256e  jmp     loc_18000247C
0x180002573  movss   xmm0, dword ptr [rdx]
0x180002577  cvtps2pd xmm0, xmm0
0x18000257a  movsd   [rsp+240h+var_220], xmm0
0x180002580  lea     r9, a7g; "%.7g"
0x180002587  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000258b  mov     r8, r14; MaxCount
0x18000258e  lea     edx, [r14+29h]; BufferCount
0x180002592  lea     rcx, [rbp+140h+Buffer]; Buffer
0x180002599  call    _snwprintf_s
0x18000259e  cmp     eax, r14d
0x1800025a1  jnz     short loc_180002610
0x1800025a3  lea     rax, WPP_GLOBAL_Control
0x1800025aa  lea     ebx, [r14+0Eh]
0x1800025ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025b5  cmp     rcx, rax
0x1800025b8  jz      short loc_1800025DC
0x1800025ba  test    byte ptr [rcx+1Ch], 2
0x1800025be  jz      short loc_1800025DC
0x1800025c0  cmp     byte ptr [rcx+19h], 2
0x1800025c4  jb      short loc_1800025DC
0x1800025c6  lea     edx, [rbx-3]
0x1800025c9  mov     r9d, ebx
0x1800025cc  lea     r8, WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids
0x1800025d3  mov     rcx, [rcx+10h]
0x1800025d7  call    WPP_SF_D
0x1800025dc  xorps   xmm0, xmm0
0x1800025df  movdqu  [rsp+240h+pExceptionObject], xmm0
0x1800025e5  mov     [rsp+240h+var_1E8], rsi
0x1800025ea  mov     [rsp+240h+var_1E0], ebx
0x1800025ee  mov     [rsp+240h+var_1DC], 0FFFFFFFFh
0x1800025f6  mov     [rsp+240h+var_1D8], 0F9h
0x1800025fe  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180002605  lea     rcx, [rsp+240h+pExceptionObject]; pExceptionObject
0x18000260a  call    _CxxThrowException_0
0x180002610  lea     rax, [rbp+140h+Buffer]
0x180002617  inc     r14
0x18000261a  cmp     [rax+r14*2], si
0x18000261f  jnz     short loc_180002617
0x180002621  jmp     loc_180002A3D
0x180002626  cmp     edi, 11h
0x180002629  ja      loc_180002794
0x18000262f  jz      loc_180002776
0x180002635  sub     edi, 0Ch
0x180002638  jz      loc_1800026C6
0x18000263e  sub     edi, 1
0x180002641  jz      short loc_1800026A2
0x180002643  sub     edi, 1
0x180002646  jz      loc_180002907
0x18000264c  sub     edi, 1
0x18000264f  jz      short loc_18000265F
0x180002651  cmp     edi, 1
0x180002654  jnz     loc_1800027B9
0x18000265a  jmp     loc_1800024C9
0x18000265f  mov     rax, [rdx]
0x180002662  movups  xmm0, xmmword ptr [rax]
0x180002665  movdqu  xmmword ptr [rbp+140h+SystemTime.wYear], xmm0
0x18000266a  mov     eax, 7Bh ; '{'
0x18000266f  mov     [rbp+140h+Buffer], ax
0x180002676  lea     rdx, [rbp+140h+SystemTime]
0x18000267a  lea     rcx, [rbp+140h+var_9E]
0x180002681  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x180002686  mov     eax, 7Dh ; '}'
0x18000268b  mov     [rbp+140h+var_56], ax
0x180002692  lea     r13, [rbp+140h+Buffer]
0x180002699  lea     r14d, [rax-57h]
0x18000269d  jmp     loc_180002A4D
0x1800026a2  mov     eax, [rdx]
0x1800026a4  lea     rcx, aFalse; "false"
0x1800026ab  lea     r13, aTrue; "true"
0x1800026b2  test    eax, eax
0x1800026b4  cmovz   r13, rcx
0x1800026b8  neg     eax
0x1800026ba  sbb     r14, r14
0x1800026bd  add     r14, 5
0x1800026c1  jmp     loc_180002A44
0x1800026c6  movsd   xmm0, qword ptr [rdx]
0x1800026ca  movsd   [rsp+240h+var_220], xmm0
0x1800026d0  lea     r9, a15g; "%.15g"
0x1800026d7  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800026db  mov     r8, r14; MaxCount
0x1800026de  lea     edx, [r14+29h]; BufferCount
0x1800026e2  lea     rcx, [rbp+140h+Buffer]; Buffer
0x1800026e9  call    _snwprintf_s
0x1800026ee  cmp     eax, r14d
0x1800026f1  jnz     short loc_180002760
0x1800026f3  lea     rax, WPP_GLOBAL_Control
0x1800026fa  lea     ebx, [r14+0Eh]
0x1800026fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002705  cmp     rcx, rax
0x180002708  jz      short loc_18000272C
0x18000270a  test    byte ptr [rcx+1Ch], 2
0x18000270e  jz      short loc_18000272C
0x180002710  cmp     byte ptr [rcx+19h], 2
0x180002714  jb      short loc_18000272C
0x180002716  lea     edx, [rbx-2]
0x180002719  mov     r9d, ebx
0x18000271c  lea     r8, WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids
0x180002723  mov     rcx, [rcx+10h]
0x180002727  call    WPP_SF_D
0x18000272c  xorps   xmm0, xmm0
0x18000272f  movdqu  [rsp+240h+pExceptionObject], xmm0
0x180002735  mov     [rsp+240h+var_1E8], rsi
0x18000273a  mov     [rsp+240h+var_1E0], ebx
0x18000273e  mov     [rsp+240h+var_1DC], 0FFFFFFFFh
0x180002746  mov     [rsp+240h+var_1D8], 102h
0x18000274e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180002755  lea     rcx, [rsp+240h+pExceptionObject]; pExceptionObject
0x18000275a  call    _CxxThrowException_0
0x180002760  lea     rax, [rbp+140h+Buffer]
0x180002767  inc     r14
0x18000276a  cmp     [rax+r14*2], si
0x18000276f  jnz     short loc_180002767
0x180002771  jmp     loc_180002A3D
0x180002776  lea     rcx, [rbp+140h+Buffer]
0x18000277d  call    ??$filetime_to_string@_W@tlx@@YAXPEA_WAEBU_FILETIME@@_N@Z; tlx::filetime_to_string<wchar_t>(wchar_t *,_FILETIME const &,bool)
0x180002782  lea     r13, [rbp+140h+Buffer]
0x180002789  mov     r14d, 1Ch
0x18000278f  jmp     loc_180002A4D
0x180002794  sub     edi, 12h
0x180002797  jz      loc_180002A07
0x18000279d  sub     edi, 1
0x1800027a0  jz      loc_18000286A
0x1800027a6  sub     edi, 1
0x1800027a9  jz      loc_18000284C
0x1800027af  sub     edi, 1
0x1800027b2  jz      short loc_18000282E
0x1800027b4  cmp     edi, 0Eh
0x1800027b7  jz      short loc_180002826
0x1800027b9  lea     rax, WPP_GLOBAL_Control
0x1800027c0  mov     ebx, 0Dh
0x1800027c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027cc  cmp     rcx, rax
0x1800027cf  jz      short loc_1800027F2
0x1800027d1  test    byte ptr [rcx+1Ch], 2
0x1800027d5  jz      short loc_1800027F2
0x1800027d7  cmp     byte ptr [rcx+19h], 2
0x1800027db  jb      short loc_1800027F2
0x1800027dd  mov     edx, ebx
0x1800027df  mov     r9d, ebx
0x1800027e2  lea     r8, WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids
0x1800027e9  mov     rcx, [rcx+10h]
0x1800027ed  call    WPP_SF_D
0x1800027f2  xorps   xmm0, xmm0
0x1800027f5  movdqu  [rsp+240h+pExceptionObject], xmm0
0x1800027fb  mov     [rsp+240h+var_1E8], rsi
0x180002800  mov     [rsp+240h+var_1E0], ebx
0x180002804  mov     [rsp+240h+var_1DC], 0FFFFFFFFh
0x18000280c  mov     [rsp+240h+var_1D8], 15Fh
0x180002814  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000281b  lea     rcx, [rsp+240h+pExceptionObject]; pExceptionObject
0x180002820  call    _CxxThrowException_0
0x180002826  xor     r9d, r9d
0x180002829  jmp     loc_1800024EF
0x18000282e  mov     r9, [rdx]
0x180002831  mov     r8d, 28h ; '('
0x180002837  lea     rdx, [rbp+140h+Buffer]
0x18000283e  lea     rcx, [rbp+140h+var_118]
0x180002842  call    ??$ToWcharsHex@_K@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_K1@Z; ToWcharsHex<unsigned __int64>(wchar_t *,unsigned __int64,unsigned __int64)
0x180002847  jmp     loc_1800024AE
0x18000284c  mov     r9d, [rdx]
0x18000284f  mov     r8d, 28h ; '('
0x180002855  lea     rdx, [rbp+140h+Buffer]
0x18000285c  lea     rcx, [rbp+140h+var_118]
0x180002860  call    ??$ToWcharsHex@I@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEA_W_KI@Z; ToWcharsHex<uint>(wchar_t *,unsigned __int64,uint)
0x180002865  jmp     loc_1800024AE
0x18000286a  cmp     dword ptr [rdx+8], 44h ; 'D'
0x18000286e  ja      loc_180002907
0x180002874  mov     r8d, [rdx+8]; Size
0x180002878  mov     rdx, [rdx]; Src
0x18000287b  lea     rcx, [rbp+140h+pSid]; void *
0x18000287f  call    memcpy_0
0x180002884  mov     [rsp+240h+hMem], rsi
0x180002889  lea     rcx, [rbp+140h+pSid]; pSid
0x18000288d  call    cs:__imp_IsValidSid
0x180002893  test    eax, eax
0x180002895  jz      short loc_1800028FD
0x180002897  mov     rcx, [rsp+240h+hMem]; hMem
0x18000289c  mov     [rsp+240h+hMem], rsi
0x1800028a1  test    rcx, rcx
0x1800028a4  jz      short loc_1800028AC
0x1800028a6  call    cs:__imp_LocalFree
0x1800028ac  lea     rdx, [rsp+240h+hMem]; StringSid
0x1800028b1  lea     rcx, [rbp+140h+pSid]; Sid
0x1800028b5  call    cs:__imp_ConvertSidToStringSidW
0x1800028bb  test    eax, eax
0x1800028bd  jz      short loc_1800028FD
0x1800028bf  mov     rdx, [rsp+240h+hMem]; void *
0x1800028c4  test    rdx, rdx
0x1800028c7  jz      short loc_1800028FD
0x1800028c9  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800028cd  inc     r14
0x1800028d0  cmp     [rdx+r14*2], si
0x1800028d5  jnz     short loc_1800028CD
0x1800028d7  lea     r8d, [r14+r14]; unsigned int
0x1800028db  mov     rcx, rbx; this
  ... truncated ...
```
