# CAVIFile::OpenInternal(ulong,int)

- ea: `0x18000a060`
- end: `0x18000acea`
- name: `?OpenInternal@CAVIFile@@QEAAJKH@Z`
- size: `3210`
- prototype: `__int64 __fastcall(CAVIFile *this, __int16, int)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180009ef0`

## callees

- `0x180001008`
- `0x180001460`
- `0x18000420c`
- `0x180005c14`
- `0x180006a44`
- `0x1800070ec`
- `0x180009110`
- `0x18000a060`
- `0x18000b25c`
- `0x18000ce28`
- `0x18000d0dc`
- `0x18000d24c`
- `0x180014468`
- `0x180014694`
- `0x180014880`
- `0x180015108`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000a797`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000a8fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000a797`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000a8fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000a5f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000a5f6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a78e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a8f4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a78e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a8f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a57a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a5e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a57a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000a5e6`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18000a62c`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18000a62c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a478`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a478`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a252`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a939`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aabb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aae3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000acbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000acdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a252`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a939`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aabb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aae3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000acbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000acdc`
- `USER32!SetRect` at `0x18000a85c`
- `USER32!SetRect` at `0x18000a85c`
- `USER32!IsRectEmpty` at `0x18000a81c`
- `USER32!IsRectEmpty` at `0x18000a81c`
- `WINMM!mmioSeek` at `0x18000ab1c`
- `WINMM!mmioSeek` at `0x18000ab1c`

## pseudocode

```c
__int64 __fastcall CAVIFile::OpenInternal(CAVIFile *this, __int16 a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  int v5; // r12d
  __int64 v7; // rcx
  unsigned int IntoExtra; // r13d
  __int64 v9; // rax
  __int64 v10; // rdx
  char *v11; // r14
  __int64 v12; // rdx
  unsigned int v13; // edi
  unsigned int v15; // r15d
  int v16; // ecx
  __int64 v17; // rax
  int v18; // edi
  _QWORD *v19; // rax
  _QWORD *v20; // r14
  _DWORD *v21; // r12
  unsigned int v22; // edi
  __int64 v23; // rcx
  unsigned int v24; // edi
  int v25; // ecx
  UINT v26; // edx
  int v27; // r15d
  int i; // edx
  int v29; // eax
  const WCHAR *v30; // rdi
  const WCHAR *v31; // r9
  unsigned __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r8
  CHAR *v35; // r9
  _WORD *v36; // rax
  __int64 v37; // rdx
  _WORD *v38; // rcx
  __int64 v39; // rax
  HGLOBAL v40; // rax
  LPVOID v41; // rax
  int v42; // eax
  __int64 v43; // rdi
  unsigned __int16 v44; // cx
  int v45; // r12d
  int v46; // r15d
  __int64 v47; // rcx
  _DWORD *v48; // rax
  HGLOBAL v49; // rax
  LPVOID v50; // rax
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rcx
  LONG v56; // edx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rcx
  int v60; // r9d
  int *v61; // r8
  int v62; // edx
  unsigned int v63; // eax
  __int16 v64; // r10
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // rcx
  unsigned int ProfileIntA; // eax
  unsigned int v69; // ecx
  __int64 cchWideChar; // [rsp+28h] [rbp-D8h]
  int v71; // [rsp+30h] [rbp-D0h]
  int v72; // [rsp+34h] [rbp-CCh]
  SIZE_T dwBytes[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v75; // [rsp+58h] [rbp-A8h]
  __int128 v76; // [rsp+60h] [rbp-A0h] BYREF
  int v77; // [rsp+70h] [rbp-90h]
  __int128 v78; // [rsp+78h] [rbp-88h] BYREF
  int v79; // [rsp+88h] [rbp-78h]
  __int128 v80; // [rsp+90h] [rbp-70h] BYREF
  int v81; // [rsp+A0h] [rbp-60h]
  __int128 v82; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v83; // [rsp+B8h] [rbp-48h]
  __int128 v84; // [rsp+C8h] [rbp-38h]
  __int64 v85; // [rsp+D8h] [rbp-28h]
  WCHAR Buffer[20]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pszFormat[20]; // [rsp+108h] [rbp+8h] BYREF
  wchar_t MultiByteStr[264]; // [rsp+130h] [rbp+30h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1264);
  v75 = 0;
  v79 = 0;
  v77 = 0;
  v5 = a3;
  v81 = 0;
  v85 = 0;
  *(_OWORD *)dwBytes = 0;
  v78 = 0;
  v76 = 0;
  v80 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1264));
  v7 = *((_QWORD *)this + 83);
  if ( !v7 )
  {
    IntoExtra = -2147205009;
LABEL_169:
    if ( v3 )
      LeaveCriticalSection(v3);
    return IntoExtra;
  }
  if ( (a2 & 0x1000) != 0 )
  {
    v9 = IndexCreate();
    *((_QWORD *)this + 156) = v9;
    if ( v9 )
    {
      *((_DWORD *)this + 176) = 0;
      *((_DWORD *)this + 34) = 100;
      *((_DWORD *)this + 23) = 2064;
LABEL_165:
      if ( v3 )
        LeaveCriticalSection(v3);
      return 0;
    }
    goto LABEL_128;
  }
  if ( (unsigned int)shfileDescend(v7, &v78, 0) )
    goto LABEL_109;
  if ( DWORD1(v78) == 1952539757 && (unsigned int)shfileDescend(*((_QWORD *)this + 83), &v78, 0)
    || (_DWORD)v78 != 1179011410
    || DWORD2(v78) != 541677121 )
  {
    goto LABEL_124;
  }
  v10 = *((_QWORD *)this + 83);
  v11 = (char *)this + 712;
  DWORD2(v76) = 1819436136;
  if ( (unsigned int)FindChunkAndKeepExtras((int)this + 712, v10, (unsigned int)&v76, (unsigned int)&v78, 64) )
    goto LABEL_19;
  v12 = *((_QWORD *)this + 83);
  LODWORD(dwBytes[0]) = 1751742049;
  *((_DWORD *)this + 34) = DWORD1(v76) + 32;
  if ( (unsigned int)FindChunkAndKeepExtras((int)this + 712, v12, (unsigned int)dwBytes, (unsigned int)&v76, 16) )
    goto LABEL_19;
  v13 = 56;
  if ( HIDWORD(dwBytes[0]) < 0x38 )
    v13 = HIDWORD(dwBytes[0]);
  if ( (unsigned int)shfileRead(*((_QWORD *)this + 83), (char *)this + 80, v13) == v13
    && !(unsigned int)shfileAscend(*((_QWORD *)this + 83), dwBytes) )
  {
    if ( *((_DWORD *)this + 26) > 0x40u )
    {
      *((_DWORD *)this + 26) = 0;
LABEL_19:
      if ( v3 )
        LeaveCriticalSection(v3);
      return 2147762375LL;
    }
    v15 = 0;
    v71 = 0;
    v16 = 0;
    if ( *((int *)this + 26) > 0 )
    {
      do
      {
        v17 = v16++;
        *((_QWORD *)this + v17 + 92) = 0;
      }
      while ( v16 < *((_DWORD *)this + 26) );
      v18 = 0;
      v72 = 0;
      if ( *((int *)this + 26) > 0 )
      {
        do
        {
          if ( (unsigned int)shfileDescend(*((_QWORD *)this + 83), &v80, &v76) )
            goto LABEL_109;
          if ( DWORD2(v80) == 1819440243 && (_DWORD)v80 == 1414744396 )
          {
            v19 = operator new(0x580u);
            v20 = v19;
            if ( v19 )
            {
              v19[1] = v19;
              *v19 = &CAVIStream::CUnknownImpl::`vftable';
              v19[3] = &CAVIStream::CS::`vftable';
              v19[5] = &CAVIStream::CStreamingImpl::`vftable';
              *((_DWORD *)v19 + 4) = 0;
              v19[4] = v19;
              v19[6] = v19;
              v19[7] = v19;
              v19[36] = 0;
              v19[37] = 0;
              v19[167] = 0;
              *((_DWORD *)v19 + 336) = 0;
              v19[169] = 0;
              *((_DWORD *)v19 + 340) = 0;
              v19[171] = 0;
              *((_DWORD *)v19 + 344) = 0;
              v19[175] = 0;
              *((_DWORD *)v19 + 76) = 0;
              v19[173] = 0;
              *((_DWORD *)v19 + 348) = 0;
            }
            else
            {
              v20 = 0;
            }
            *((_QWORD *)this + v18 + 92) = v20;
            if ( !v20 )
            {
LABEL_128:
              if ( v3 )
                LeaveCriticalSection(v3);
              return 2147762279LL;
            }
            v20[34] = this;
            v21 = v20 + 8;
            *((_DWORD *)v20 + 70) = v18;
            if ( !(unsigned int)shfileDescend(*((_QWORD *)this + 83), dwBytes, &v80) )
            {
              while ( 1 )
              {
                if ( LODWORD(dwBytes[0]) == 1263424842 || LODWORD(dwBytes[0]) == 1684300144 )
                  goto LABEL_73;
                if ( LODWORD(dwBytes[0]) == 1685222515 )
                {
                  if ( !v20[169] )
                  {
                    *((_DWORD *)v20 + 340) = HIDWORD(dwBytes[0]);
                    v49 = GlobalAlloc(0x2002u, HIDWORD(dwBytes[0]));
                    v50 = GlobalLock(v49);
                    v20[169] = v50;
                    if ( !v50 )
                      goto LABEL_128;
                    v51 = shfileRead(*((_QWORD *)this + 83), v50, HIDWORD(dwBytes[0]));
                    if ( v51 != HIDWORD(dwBytes[0]) )
                      goto LABEL_109;
                  }
                  goto LABEL_73;
                }
                if ( LODWORD(dwBytes[0]) != 1718776947 )
                  break;
                if ( !v20[167] )
                {
                  if ( HIDWORD(dwBytes[0]) > 0x7FFFFFFF )
                  {
                    *((_DWORD *)v20 + 336) = -1;
                    goto LABEL_109;
                  }
                  *((_DWORD *)v20 + 336) = HIDWORD(dwBytes[0]);
                  v40 = GlobalAlloc(0x2002u, HIDWORD(dwBytes[0]));
                  v41 = GlobalLock(v40);
                  v20[167] = v41;
                  if ( !v41 )
                    goto LABEL_128;
                  v42 = shfileRead(*((_QWORD *)this + 83), v41, HIDWORD(dwBytes[0]));
                  if ( v42 != HIDWORD(dwBytes[0]) )
                    goto LABEL_109;
                  if ( *v21 == 1935960438 )
                  {
                    v43 = v20[167];
                    if ( !(unsigned int)ValidateBitmapInfoHeader(v43) )
                      goto LABEL_109;
                    if ( !*(_DWORD *)(v43 + 32) )
                    {
                      v44 = *(_WORD *)(v43 + 14);
                      if ( v44 <= 8u )
                        *(_DWORD *)(v43 + 32) = 1 << v44;
                    }
                    v45 = *((_DWORD *)this + 29);
                    v46 = *((_DWORD *)this + 28);
                    if ( IsRectEmpty((const RECT *)((char *)v20 + 116))
                      || *((_DWORD *)v20 + 31) - *((_DWORD *)v20 + 29) > v46
                      || *((_DWORD *)v20 + 32) - *((_DWORD *)v20 + 30) > v45 )
                    {
                      SetRect(
                        (LPRECT)((char *)v20 + 116),
                        0,
                        0,
                        *(_DWORD *)(v20[167] + 4LL),
                        *(_DWORD *)(v20[167] + 8LL));
                    }
                    v47 = v20[167];
                    if ( !*(_DWORD *)(v47 + 16)
                      && *(_WORD *)(v47 + 14) == 8
                      && ((*((_DWORD *)v20 + 17) - 541412434) & 0xEFFFFFFF) == 0 )
                    {
                      *(_DWORD *)(v47 + 16) = 1;
                      v47 = v20[167];
                    }
                    v48 = (_DWORD *)(v47 + 16);
                    if ( (*((_DWORD *)v20 + 17) == 1162760014 || !*((_DWORD *)v20 + 17)) && !*v48 )
                      *((_DWORD *)v20 + 17) = 541215044;
                    v21 = v20 + 8;
                    if ( *v48 <= 1u )
                    {
                      v15 = 1;
                      v71 = 1;
                      goto LABEL_73;
                    }
                    goto LABEL_72;
                  }
                }
LABEL_73:
                if ( (unsigned int)shfileAscend(*((_QWORD *)this + 83), dwBytes) )
                  goto LABEL_109;
                if ( (unsigned int)shfileDescend(*((_QWORD *)this + 83), dwBytes, &v80) )
                {
                  v18 = v72;
                  goto LABEL_76;
                }
              }
              if ( LODWORD(dwBytes[0]) != 1752331379 )
              {
                if ( LODWORD(dwBytes[0]) == 1852994675 )
                {
                  v22 = HIDWORD(dwBytes[0]);
                  if ( (unsigned __int64)SHIDWORD(dwBytes[0]) >= 0x104 )
                    v22 = 260;
                  if ( (unsigned int)shfileRead(*((_QWORD *)this + 83), MultiByteStr, v22) != v22 )
                    goto LABEL_109;
                  MultiByteToWideChar(0, 0, (LPCCH)MultiByteStr, -1, (LPWSTR)v20 + 70, 64);
                }
                else
                {
                  IntoExtra = ReadIntoExtra(v20 + 171, *((_QWORD *)this + 83), dwBytes);
                  if ( IntoExtra )
                    goto LABEL_169;
                }
                goto LABEL_73;
              }
              v23 = *((_QWORD *)this + 83);
              v24 = 56;
              DWORD2(v84) = -1;
              v85 = 0;
              if ( HIDWORD(dwBytes[0]) < 0x38 )
                v24 = HIDWORD(dwBytes[0]);
              if ( (unsigned int)shfileRead(v23, &v82, v24) != v24 )
                goto LABEL_109;
              *v21 = v82;
              v25 = v82;
              *(_QWORD *)((char *)v20 + 68) = *(_QWORD *)((char *)&v82 + 4);
              *((_DWORD *)v20 + 19) = 0;
              *((_DWORD *)v20 + 20) = HIDWORD(v82);
              *(_QWORD *)((char *)v20 + 84) = *(_QWORD *)((char *)&v83 + 4);
              *((_DWORD *)v20 + 23) = HIDWORD(v83);
              *((_DWORD *)v20 + 24) = v84;
              *((_DWORD *)v20 + 26) = DWORD1(v84);
              *((_DWORD *)v20 + 25) = v83;
              *(_QWORD *)((char *)v20 + 108) = *((_QWORD *)&v84 + 1);
              *((_DWORD *)v20 + 29) = (__int16)v85;
              *((_DWORD *)v20 + 30) = SWORD1(v85);
              *((_DWORD *)v20 + 31) = SWORD2(v85);
              *((_DWORD *)v20 + 32) = SHIWORD(v85);
              *(_QWORD *)((char *)v20 + 132) = 0;
              if ( v25 == 1935960438 )
              {
                v26 = 189;
                goto LABEL_52;
              }
              if ( v25 == 1935963489 )
              {
                v26 = 190;
LABEL_52:
                LoadStringW(ghMod, v26, Buffer, 20);
              }
              else
              {
                StringCchPrintfW(Buffer, 0x14u, L"'%4.4hs'", v21);
              }
              v27 = 1;
              if ( v72 > 0 )
              {
                for ( i = 0; i < v72; ++i )
                {
                  v29 = v27 + 1;
                  if ( *(_DWORD *)(*((_QWORD *)this + (unsigned int)i + 92) + 64LL) != *v21 )
                    v29 = v27;
                  v27 = v29;
                }
              }
              LoadStringW(ghMod, 0xBFu, pszFormat, 20);
              v30 = (const WCHAR *)((char *)this + 140);
              v31 = (const WCHAR *)((char *)this + 2 * lstrlenW((LPCWSTR)this + 70) + 140);
              if ( v31 > (const WCHAR *)this + 70 )
              {
                do
                {
                  v32 = *v31;
                  LOWORD(v32) = v32 - 47;
                  if ( (unsigned __int16)v32 <= 0x2Du )
                  {
                    v33 = 0x200000000801LL;
                    if ( _bittest64(&v33, v32) )
                      break;
                  }
                  v31 = CharPrevW((LPCWSTR)this + 70, v31);
                }
                while ( v31 > v30 );
              }
              LODWORD(cchWideChar) = v27;
              if ( v31 != v30 )
                ++v31;
              StringCbPrintfW(MultiByteStr, 0x208u, pszFormat, v31, Buffer, cchWideChar);
              v34 = 63;
              v35 = (CHAR *)MultiByteStr;
              v36 = (_WORD *)v20 + 70;
              v37 = 64;
              do
              {
                if ( !v34 )
                  break;
                if ( !*(_WORD *)v35 )
                  break;
                *v36 = *(_WORD *)v35;
                v35 += 2;
                ++v36;
                --v34;
                --v37;
              }
              while ( v37 );
              v38 = v36 - 1;
              if ( v37 )
                v38 = v36;
              *v38 = 0;
              *((_WORD *)v20 + 133) = 0;
LABEL_72:
              v15 = v71;
              goto LABEL_73;
            }
LABEL_76:
            if ( (unsigned int)shfileAscend(*((_QWORD *)this + 83), &v80) )
              goto LABEL_109;
            if ( !*v21 )
              goto LABEL_124;
            v39 = v20[167];
            if ( !v39 )
              goto LABEL_124;
            if ( *v21 == 1935960438 )
            {
              *((_DWORD *)v20 + 28) = 0;
            }
            else if ( *v21 == 1935963489 )
            {
              if ( *((_DWORD *)v20 + 336) < 0xEu )
                goto LABEL_124;
              *((_DWORD *)v20 + 28) = *(unsigned __int16 *)(v39 + 12);
            }
            ++v18;
            *((_WORD *)v20 + 133) = 0;
            v72 = v18;
            v11 = (char *)this + 712;
          }
          else
          {
            IntoExtra = ReadIntoExtra(v11, *((_QWORD *)this + 83), &v80);
            if ( IntoExtra )
              goto LABEL_169;
            if ( (unsigned int)shfileAscend(*((_QWORD *)this + 83), &v80) )
              goto LABEL_109;
          }
        }
        while ( v18 < *((_DWORD *)this + 26) );
        v5 = a3;
      }
    }
    FindChunkAndKeepExtras((_DWORD)v11, *((_QWORD *)this + 83), (unsigned int)dwBytes, (unsigned int)&v76, 0);
    if ( (unsigned int)shfileAscend(*((_QWORD *)this + 83), &v76) )
      goto LABEL_109;
    v52 = *((_QWORD *)this + 83);
    DWORD2(v76) = 1769369453;
    if ( (unsigned int)FindChunkAndKeepExtras((_DWORD)v11, v52, (unsigned int)&v76, (unsigned int)&v78, 64) )
      goto LABEL_19;
    v53 = *((_QWORD *)this + 83);
    *((_DWORD *)this + 168) = HIDWORD(v76) - 8;
    if ( (unsigned int)shfileAscend(v53, &v76) )
      goto LABEL_109;
    v54 = *((_QWORD *)this + 83);
    *((_DWORD *)this + 176) = HIDWORD(v76) + DWORD1(v76);
    LODWORD(dwBytes[0]) = 829973609;
    if ( (unsigned int)FindChunkAndKeepExtras((_DWORD)v11, v54, (unsigned int)dwBytes, (unsigned int)&v78, 16)
      || !HIDWORD(dwBytes[0]) )
    {
      v55 = *((_QWORD *)this + 83);
      v56 = HIDWORD(v76) + 4;
      v57 = *(_QWORD *)(v55 + 16);
      if ( v57 )
        *(_DWORD *)(v57 + 372) = v56;
      else
        mmioSeek(*(HMMIO *)(v55 + 8), v56, 0);
      if ( v5 )
        goto LABEL_19;
      v58 = IndexCreate();
      *((_QWORD *)this + 156) = v58;
      if ( !v58 )
        goto LABEL_124;
      while ( !(unsigned int)shfileDescend(*((_QWORD *)this + 83), dwBytes, &v76) )
      {
        AddToIndex(this, dwBytes[0], HIDWORD(dwBytes[0]), HIDWORD(dwBytes[1]) - 8, 0);
        if ( LODWORD(dwBytes[0]) != 1414744396 && (unsigned int)shfileAscend(*((_QWORD *)this + 83), dwBytes) )
          goto LABEL_109;
      }
    }
    else if ( !(unsigned int)ReadInIndex(this, HIDWORD(dwBytes[0]), HIDWORD(v76), v15) )
    {
LABEL_124:
      if ( v3 )
        LeaveCriticalSection(v3);
      return 2147762278LL;
    }
    if ( **((_DWORD **)this + 156) )
    {
      FindChunkAndKeepExtras((_DWORD)v11, *((_QWORD *)this + 83), (unsigned int)dwBytes, (unsigned int)&v78, 0);
      v60 = *((_DWORD *)this + 23) & 0x100;
      if ( v60 )
      {
        v61 = (int *)*((_QWORD *)this + 156);
        *((_DWORD *)this + 27) = 0;
        v62 = 0;
        if ( *v61 > 0 )
        {
          while ( 1 )
          {
            v59 = 3LL * (unsigned int)v62;
            if ( HIWORD(v61[3 * v62 + 2]) == 127 )
              break;
            if ( ++v62 >= *v61 )
              goto LABEL_156;
          }
LABEL_146:
          v59 = 3LL * v62;
          v63 = v61[3 * v62 + 4];
          if ( *((_DWORD *)this + 27) < v63 )
            *((_DWORD *)this + 27) = v63;
          if ( v62 >= 0 && v62 < *v61 )
          {
            v64 = HIWORD(v61[3 * v62++ + 2]);
            while ( v62 < *v61 )
            {
              v59 = 3LL * v62;
              if ( HIWORD(v61[3 * v62 + 2]) == v64 )
              {
                if ( v62 != -1 )
                  goto LABEL_146;
                break;
              }
              ++v62;
            }
          }
        }
      }
LABEL_156:
      v65 = *((_QWORD *)this + 83);
      if ( *(_QWORD *)(v65 + 16) )
      {
        *((_QWORD *)this + 157) = 0;
      }
      else
      {
        if ( v60 && (v59 = *((unsigned int *)this + 25), (_DWORD)v59) )
        {
          v66 = *((unsigned int *)this + 27);
          v67 = (unsigned int)(2 * v59);
        }
        else
        {
          ProfileIntA = mmGetProfileIntA(v59, "buffers", 5);
          v66 = 0x8000;
          v65 = *((_QWORD *)this + 83);
          v69 = 2 * *((_DWORD *)this + 27);
          if ( v69 < 0x8000 )
            v66 = v69;
          v67 = ProfileIntA;
        }
        *((_QWORD *)this + 157) = InitBuffered(v67, v66, v65, *((_QWORD *)this + 156));
      }
      goto LABEL_165;
    }
    goto LABEL_124;
  }
LABEL_109:
  if ( v3 )
    LeaveCriticalSection(v3);
  return 2147762285LL;
}

```

## disassembly

```asm
0x18000a060  push    rbp
0x18000a062  push    rbx
0x18000a063  push    rsi
0x18000a064  push    rdi
0x18000a065  push    r12
0x18000a067  push    r13
0x18000a069  push    r14
0x18000a06b  push    r15
0x18000a06d  lea     rbp, [rsp-258h]
0x18000a075  sub     rsp, 358h
0x18000a07c  mov     rax, cs:__security_cookie
0x18000a083  xor     rax, rsp
0x18000a086  mov     [rbp+290h+var_50], rax
0x18000a08d  xorps   xmm0, xmm0
0x18000a090  mov     [rsp+390h+var_358], r8d
0x18000a095  xor     eax, eax
0x18000a097  lea     rbx, [rcx+4F0h]
0x18000a09e  xorps   xmm1, xmm1
0x18000a0a1  mov     [rsp+390h+var_338], eax
0x18000a0a5  mov     rsi, rcx
0x18000a0a8  mov     [rbp+290h+var_308], eax
0x18000a0ab  mov     rcx, rbx; lpCriticalSection
0x18000a0ae  mov     [rsp+390h+var_320], eax
0x18000a0b2  mov     r12d, r8d
0x18000a0b5  mov     [rbp+290h+var_2F0], eax
0x18000a0b8  mov     edi, edx
0x18000a0ba  mov     [rbp+290h+var_2B8], rax
0x18000a0be  movups  xmmword ptr [rsp+390h+dwBytes], xmm0
0x18000a0c3  movups  [rsp+390h+var_318], xmm1
0x18000a0c8  movups  [rsp+390h+var_330], xmm0
0x18000a0cd  movups  [rbp+290h+var_300], xmm1
0x18000a0d1  movups  [rbp+290h+var_2E8], xmm0
0x18000a0d5  movups  [rbp+290h+var_2D8], xmm0
0x18000a0d9  movups  [rbp+290h+var_2C8], xmm0
0x18000a0dd  call    cs:__imp_EnterCriticalSection
0x18000a0e3  mov     rcx, [rsi+298h]
0x18000a0ea  xor     r13d, r13d
0x18000a0ed  test    rcx, rcx
0x18000a0f0  jnz     short loc_18000A0FD
0x18000a0f2  mov     r13d, 8004406Fh
0x18000a0f8  jmp     loc_18000ACD4
0x18000a0fd  bt      edi, 0Ch
0x18000a101  jnb     short loc_18000A138
0x18000a103  call    IndexCreate
0x18000a108  xor     r11d, r11d
0x18000a10b  mov     [rsi+4E0h], rax
0x18000a112  test    rax, rax
0x18000a115  jz      loc_18000AADB
0x18000a11b  mov     [rsi+2C0h], r11d
0x18000a122  mov     dword ptr [rsi+88h], 64h ; 'd'
0x18000a12c  mov     dword ptr [rsi+5Ch], 810h
0x18000a133  jmp     loc_18000ACB6
0x18000a138  xor     r8d, r8d
0x18000a13b  lea     rdx, [rsp+390h+var_318]
0x18000a140  call    shfileDescend
0x18000a145  test    eax, eax
0x18000a147  jnz     loc_18000A931
0x18000a14d  cmp     dword ptr [rsp+390h+var_318+4], 7461646Dh
0x18000a155  jnz     short loc_18000A173
0x18000a157  mov     rcx, [rsi+298h]
0x18000a15e  lea     rdx, [rsp+390h+var_318]
0x18000a163  xor     r8d, r8d
0x18000a166  call    shfileDescend
0x18000a16b  test    eax, eax
0x18000a16d  jnz     loc_18000AAB3
0x18000a173  cmp     dword ptr [rsp+390h+var_318], 46464952h
0x18000a17b  jnz     loc_18000AAB3
0x18000a181  cmp     dword ptr [rbp+290h+var_318+8], 20495641h
0x18000a188  jnz     loc_18000AAB3
0x18000a18e  mov     rdx, [rsi+298h]
0x18000a195  lea     r14, [rsi+2C8h]
0x18000a19c  mov     rcx, r14
0x18000a19f  mov     dword ptr [rsp+390h+var_330+8], 6C726468h
0x18000a1a7  lea     r9, [rsp+390h+var_318]
0x18000a1ac  mov     dword ptr [rsp+390h+lpWideCharStr], 40h ; '@'
0x18000a1b4  lea     r8, [rsp+390h+var_330]
0x18000a1b9  call    FindChunkAndKeepExtras
0x18000a1be  test    eax, eax
0x18000a1c0  jnz     loc_18000A24A
0x18000a1c6  mov     eax, dword ptr [rsp+390h+var_330+4]
0x18000a1ca  lea     r9, [rsp+390h+var_330]
0x18000a1cf  mov     rdx, [rsi+298h]
0x18000a1d6  lea     r8, [rsp+390h+dwBytes]
0x18000a1db  add     eax, 20h ; ' '
0x18000a1de  mov     dword ptr [rsp+390h+dwBytes], 68697661h
0x18000a1e6  mov     rcx, r14
0x18000a1e9  mov     [rsi+88h], eax
0x18000a1ef  mov     dword ptr [rsp+390h+lpWideCharStr], 10h
0x18000a1f7  call    FindChunkAndKeepExtras
0x18000a1fc  test    eax, eax
0x18000a1fe  jnz     short loc_18000A24A
0x18000a200  mov     rcx, [rsi+298h]
0x18000a207  lea     edi, [rax+38h]
0x18000a20a  cmp     dword ptr [rsp+390h+dwBytes+4], edi
0x18000a20e  lea     rdx, [rsi+50h]
0x18000a212  cmovb   edi, dword ptr [rsp+390h+dwBytes+4]
0x18000a217  mov     r8d, edi
0x18000a21a  call    shfileRead
0x18000a21f  cmp     eax, edi
0x18000a221  jnz     loc_18000A931
0x18000a227  mov     rcx, [rsi+298h]
0x18000a22e  lea     rdx, [rsp+390h+dwBytes]
0x18000a233  call    shfileAscend
0x18000a238  test    eax, eax
0x18000a23a  jnz     loc_18000A931
0x18000a240  cmp     dword ptr [rsi+68h], 40h ; '@'
0x18000a244  jbe     short loc_18000A262
0x18000a246  mov     [rsi+68h], r13d
0x18000a24a  test    rbx, rbx
0x18000a24d  jz      short loc_18000A258
0x18000a24f  mov     rcx, rbx; lpCriticalSection
0x18000a252  call    cs:__imp_LeaveCriticalSection
0x18000a258  mov     eax, 800440C7h
0x18000a25d  jmp     loc_18000A944
0x18000a262  xor     eax, eax
0x18000a264  mov     r15d, eax
0x18000a267  mov     [rsp+390h+var_360], eax
0x18000a26b  mov     ecx, eax
0x18000a26d  cmp     [rsi+68h], eax
0x18000a270  jle     loc_18000A9C8
0x18000a276  xor     edx, edx
0x18000a278  movsxd  rax, ecx
0x18000a27b  inc     ecx
0x18000a27d  mov     [rsi+rax*8+2E0h], rdx
0x18000a285  cmp     ecx, [rsi+68h]
0x18000a288  jl      short loc_18000A278
0x18000a28a  xor     eax, eax
0x18000a28c  mov     edi, eax
0x18000a28e  mov     [rsp+390h+var_35C], eax
0x18000a292  cmp     [rsi+68h], eax
0x18000a295  jle     loc_18000A9C8
0x18000a29b  mov     rcx, [rsi+298h]
0x18000a2a2  lea     r8, [rsp+390h+var_330]
0x18000a2a7  lea     rdx, [rbp+290h+var_300]
0x18000a2ab  call    shfileDescend
0x18000a2b0  test    eax, eax
0x18000a2b2  jnz     loc_18000A931
0x18000a2b8  cmp     dword ptr [rbp+290h+var_300+8], 6C727473h
0x18000a2bf  jnz     loc_18000A982
0x18000a2c5  cmp     dword ptr [rbp+290h+var_300], 5453494Ch
0x18000a2cc  jnz     loc_18000A982
0x18000a2d2  mov     ecx, 580h; Size
0x18000a2d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a2dc  xor     r11d, r11d
0x18000a2df  mov     r14, rax
0x18000a2e2  test    rax, rax
0x18000a2e5  jz      loc_18000A375
0x18000a2eb  lea     rax, ??_7CUnknownImpl@CAVIStream@@6B@; const CAVIStream::CUnknownImpl::`vftable'
0x18000a2f2  mov     [r14+8], r14
0x18000a2f6  mov     [r14], rax
0x18000a2f9  lea     rax, ??_7CS@CAVIStream@@6B@; const CAVIStream::CS::`vftable'
0x18000a300  mov     [r14+18h], rax
0x18000a304  lea     rax, ??_7CStreamingImpl@CAVIStream@@6B@; const CAVIStream::CStreamingImpl::`vftable'
0x18000a30b  mov     [r14+28h], rax
0x18000a30f  mov     [r14+10h], r11d
0x18000a313  mov     [r14+20h], r14
0x18000a317  mov     [r14+30h], r14
0x18000a31b  mov     [r14+38h], r14
0x18000a31f  mov     [r14+120h], r11
0x18000a326  mov     [r14+128h], r11
0x18000a32d  mov     [r14+538h], r11
0x18000a334  mov     [r14+540h], r11d
0x18000a33b  mov     [r14+548h], r11
0x18000a342  mov     [r14+550h], r11d
0x18000a349  mov     [r14+558h], r11
0x18000a350  mov     [r14+560h], r11d
0x18000a357  mov     [r14+578h], r11
0x18000a35e  mov     [r14+130h], r11d
0x18000a365  mov     [r14+568h], r11
0x18000a36c  mov     [r14+570h], r11d
0x18000a373  jmp     short loc_18000A378
0x18000a375  mov     r14, r11
0x18000a378  movsxd  rax, edi
0x18000a37b  mov     [rsi+rax*8+2E0h], r14
0x18000a383  test    r14, r14
0x18000a386  jz      loc_18000AADB
0x18000a38c  mov     [r14+110h], rsi
0x18000a393  lea     r12, [r14+40h]
0x18000a397  mov     [r14+118h], edi
0x18000a39e  lea     r8, [rbp+290h+var_300]
0x18000a3a2  mov     rcx, [rsi+298h]
0x18000a3a9  lea     rdx, [rsp+390h+dwBytes]
0x18000a3ae  mov     [rsp+390h+var_350], r12
0x18000a3b3  call    shfileDescend
0x18000a3b8  xor     ecx, ecx
0x18000a3ba  test    eax, eax
0x18000a3bc  jnz     loc_18000A6F7
0x18000a3c2  mov     eax, dword ptr [rsp+390h+dwBytes]
0x18000a3c6  cmp     eax, 4B4E554Ah
0x18000a3cb  jz      loc_18000A6BB
0x18000a3d1  cmp     eax, 64646170h
0x18000a3d6  jz      loc_18000A6BB
0x18000a3dc  cmp     eax, 64727473h
0x18000a3e1  jz      loc_18000A8D3
0x18000a3e7  cmp     eax, 66727473h
0x18000a3ec  jz      loc_18000A762
0x18000a3f2  cmp     eax, 68727473h
0x18000a3f7  jz      loc_18000A483
0x18000a3fd  cmp     eax, 6E727473h
0x18000a402  jz      short loc_18000A42C
0x18000a404  mov     rdx, [rsi+298h]
0x18000a40b  lea     rcx, [r14+558h]
0x18000a412  lea     r8, [rsp+390h+dwBytes]
0x18000a417  call    ReadIntoExtra
0x18000a41c  mov     r13d, eax
0x18000a41f  test    eax, eax
0x18000a421  jnz     loc_18000ACD4
0x18000a427  jmp     loc_18000A6BB
0x18000a42c  movsxd  rdi, dword ptr [rsp+390h+dwBytes+4]
0x18000a431  mov     eax, 104h
0x18000a436  cmp     rdi, rax
0x18000a439  jb      short loc_18000A43D
0x18000a43b  mov     edi, eax
0x18000a43d  mov     rcx, [rsi+298h]
0x18000a444  lea     rdx, [rbp+290h+MultiByteStr]
0x18000a448  mov     r8d, edi
0x18000a44b  call    shfileRead
0x18000a450  cmp     eax, edi
0x18000a452  jnz     loc_18000A931
0x18000a458  lea     rax, [r14+8Ch]
0x18000a45f  mov     dword ptr [rsp+390h+cchWideChar], 40h ; '@'; cchWideChar
0x18000a467  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000a46b  mov     [rsp+390h+lpWideCharStr], rax; lpWideCharStr
0x18000a470  lea     r8, [rbp+290h+MultiByteStr]; lpMultiByteStr
0x18000a474  xor     edx, edx; dwFlags
0x18000a476  xor     ecx, ecx; CodePage
0x18000a478  call    cs:__imp_MultiByteToWideChar
0x18000a47e  jmp     loc_18000A6BB
0x18000a483  mov     rcx, [rsi+298h]
0x18000a48a  lea     rdx, [rbp+290h+var_2E8]
0x18000a48e  mov     edi, 38h ; '8'
0x18000a493  mov     dword ptr [rbp+290h+var_2C8+8], 0FFFFFFFFh
0x18000a49a  cmp     dword ptr [rsp+390h+dwBytes+4], edi
0x18000a49e  mov     [rbp+290h+var_2B8], 0
0x18000a4a6  cmovb   edi, dword ptr [rsp+390h+dwBytes+4]
0x18000a4ab  mov     r8d, edi
0x18000a4ae  call    shfileRead
0x18000a4b3  cmp     eax, edi
0x18000a4b5  jnz     loc_18000A931
0x18000a4bb  mov     eax, dword ptr [rbp+290h+var_2E8]
0x18000a4be  xor     edi, edi
0x18000a4c0  mov     [r12], eax
0x18000a4c4  mov     ecx, dword ptr [rbp+290h+var_2E8]
0x18000a4c7  mov     eax, dword ptr [rbp+290h+var_2E8+4]
0x18000a4ca  mov     [r14+44h], eax
0x18000a4ce  mov     eax, dword ptr [rbp+290h+var_2E8+8]
0x18000a4d1  mov     [r14+48h], eax
0x18000a4d5  mov     [r14+4Ch], edi
0x18000a4d9  movzx   eax, word ptr [rbp+290h+var_2E8+0Ch]
0x18000a4dd  mov     [r14+50h], ax
0x18000a4e2  movzx   eax, word ptr [rbp+290h+var_2E8+0Eh]
0x18000a4e6  mov     [r14+52h], ax
0x18000a4eb  mov     eax, dword ptr [rbp+290h+var_2D8+8]
0x18000a4ee  mov     [r14+58h], eax
0x18000a4f2  mov     eax, dword ptr [rbp+290h+var_2D8+4]
0x18000a4f5  mov     [r14+54h], eax
0x18000a4f9  mov     eax, dword ptr [rbp+290h+var_2D8+0Ch]
0x18000a4fc  mov     [r14+5Ch], eax
0x18000a500  mov     eax, dword ptr [rbp+290h+var_2C8]
0x18000a503  mov     [r14+60h], eax
0x18000a507  mov     eax, dword ptr [rbp+290h+var_2C8+4]
0x18000a50a  mov     [r14+68h], eax
0x18000a50e  mov     eax, dword ptr [rbp+290h+var_2D8]
0x18000a511  mov     [r14+64h], eax
0x18000a515  mov     eax, dword ptr [rbp+290h+var_2C8+8]
0x18000a518  mov     [r14+6Ch], eax
0x18000a51c  mov     eax, dword ptr [rbp+290h+var_2C8+0Ch]
0x18000a51f  mov     [r14+70h], eax
0x18000a523  movsx   eax, word ptr [rbp+290h+var_2B8]
0x18000a527  mov     [r14+74h], eax
0x18000a52b  movsx   eax, word ptr [rbp+290h+var_2B8+2]
0x18000a52f  mov     [r14+78h], eax
0x18000a533  movsx   eax, word ptr [rbp+290h+var_2B8+4]
0x18000a537  mov     [r14+7Ch], eax
0x18000a53b  movsx   eax, word ptr [rbp+290h+var_2B8+6]
0x18000a53f  mov     [r14+80h], eax
0x18000a546  mov     [r14+84h], rdi
0x18000a54d  cmp     ecx, 73646976h
0x18000a553  jnz     short loc_18000A55C
0x18000a555  mov     edx, 0BDh
0x18000a55a  jmp     short loc_18000A569
0x18000a55c  cmp     ecx, 73647561h
0x18000a562  jnz     short loc_18000A582
0x18000a564  mov     edx, 0BEh; uID
0x18000a569  mov     rcx, cs:ghMod; hInstance
0x18000a570  lea     r8, [rbp+290h+Buffer]; lpBuffer
0x18000a574  mov     r9d, 14h; cchBufferMax
0x18000a57a  call    cs:__imp_LoadStringW
0x18000a580  jmp     short loc_18000A59A
0x18000a582  mov     r9, r12
0x18000a585  lea     r8, a44hs; "'%4.4hs'"
0x18000a58c  mov     edx, 14h; unsigned __int64
0x18000a591  lea     rcx, [rbp+290h+Buffer]; unsigned __int16 *
0x18000a595  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a59a  mov     r9d, [rsp+390h+var_35C]
0x18000a59f  mov     r15d, 1
0x18000a5a5  test    r9d, r9d
0x18000a5a8  jle     short loc_18000A5D0
0x18000a5aa  mov     r8d, [r12]
0x18000a5ae  mov     edx, edi
  ... truncated ...
```
