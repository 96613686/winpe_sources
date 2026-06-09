# SqliteDatabase::BuildHandler(Statement *,INotificationHandler * *)

- ea: `0x180011e90`
- end: `0x18001328b`
- name: `?BuildHandler@SqliteDatabase@@AEAA_NPEAVStatement@@PEAPEAUINotificationHandler@@@Z`
- size: `5115`
- prototype: `bool __fastcall(SqliteDatabase *__hidden this, struct Statement *, struct INotificationHandler **)`
- caller_count: `5`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008530`
- `0x1800087d0`
- `0x180008920`
- `0x1800aa120`
- `0x1800b5b90`

## callees

- `0x18000522c`
- `0x18000de40`
- `0x18000e090`
- `0x18000e5f4`
- `0x18000f8d8`
- `0x18000f9d4`
- `0x180011618`
- `0x180011800`
- `0x180011970`
- `0x180011b10`
- `0x180011e6c`
- `0x180011e90`
- `0x1800132a0`
- `0x180013360`
- `0x1800a4810`
- `0x1800b99f0`
- `0x1800b9a20`
- `0x1800b9ecc`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001250e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012b6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012c53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001250e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012b6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012c53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012e77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012f90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001301f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012e77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012f90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001301f`
- `winsqlite3!sqlite3_column_int64` at `0x18001211f`
- `winsqlite3!sqlite3_column_int64` at `0x1800123d2`
- `winsqlite3!sqlite3_column_int64` at `0x18001211f`
- `winsqlite3!sqlite3_column_int64` at `0x1800123d2`
- `winsqlite3!sqlite3_column_int` at `0x180011fca`
- `winsqlite3!sqlite3_column_int` at `0x180011fca`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800125c8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800125c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall SqliteDatabase::BuildHandler(
        SqliteDatabase *this,
        struct sqlite3_stmt **a2,
        struct INotificationHandler **a3)
{
  struct sqlite3_stmt **v3; // r14
  __int128 v4; // xmm0
  __int64 v5; // rdx
  __int64 v6; // rdx
  void *v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  unsigned int v10; // r12d
  unsigned int v11; // edx
  unsigned int v12; // r15d
  __m128i si128; // xmm6
  _BYTE *v14; // rdi
  _BYTE *v15; // rsi
  int v16; // eax
  __int64 ColumnText16; // rbx
  int v18; // r15d
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 ColumnBlob; // rbx
  void *v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // rbx
  __int16 *v25; // rbx
  NotificationSettings *v26; // rcx
  void *v27; // rax
  NotificationSettings *v28; // rax
  NotificationSettings *v29; // r13
  unsigned __int64 v30; // r14
  unsigned __int64 v31; // rdi
  unsigned __int64 v32; // r8
  __int64 (__fastcall *v33)(char *, _QWORD *, BOOL); // rsi
  BOOL v34; // edi
  _QWORD *v35; // rax
  int v36; // eax
  _WORD *v37; // rax
  _WORD *v38; // rdx
  unsigned __int64 v39; // rcx
  __int16 v40; // ax
  _WORD *v41; // rcx
  __int16 *v42; // rsi
  __int16 *v43; // r13
  __int16 *v44; // rbx
  unsigned __int8 v45; // di
  IStream *v46; // r12
  struct Statement *v47; // rax
  __int16 *v48; // r14
  void (__stdcall *v49)(GUID, void *); // rdi
  __int16 *v50; // r15
  __int16 *v51; // rsi
  __int16 *v52; // rbx
  NotificationHandler *v53; // rax
  NotificationHandler *v54; // rax
  NotificationHandler *v55; // r13
  _QWORD *v56; // r12
  unsigned __int64 v57; // r13
  unsigned __int64 v58; // rdi
  unsigned __int64 v59; // r8
  __int64 v60; // r9
  int v61; // ebx
  void *v62; // rax
  NotificationSettings *v63; // rcx
  NotificationHandler v65; // rcx
  NotificationHandler v66; // rcx
  void (__stdcall *v67)(GUID, void *); // rbx
  NotificationHandler v68; // rcx
  NotificationHandler *v69; // r12
  unsigned __int64 v70; // r13
  unsigned __int64 v71; // rbx
  unsigned __int64 v72; // r8
  __int64 v73; // r9
  unsigned __int64 v74; // rsi
  unsigned __int64 v75; // rbx
  unsigned __int64 v76; // r8
  __int64 v77; // r9
  LPVOID *v78; // r15
  unsigned __int64 v79; // rsi
  unsigned __int64 v80; // rbx
  unsigned __int64 v81; // r8
  __int64 v82; // rdx
  unsigned __int64 v83; // rsi
  LPVOID v84; // rax
  _WORD *v85; // rax
  _WORD *v86; // rdx
  unsigned __int64 v87; // rcx
  __int16 v88; // ax
  _WORD *v89; // rcx
  int v90; // eax
  void (__stdcall *v91)(GUID, void *); // rax
  _WORD *v92; // rdx
  unsigned __int64 v93; // rcx
  __int16 v94; // ax
  _WORD *v95; // rcx
  void (__stdcall *v96)(GUID, void *); // rax
  _WORD *v97; // rdx
  unsigned __int64 v98; // rcx
  __int16 v99; // ax
  _WORD *v100; // rcx
  _WORD *v101; // rax
  int v102; // edx
  _WORD *v103; // rdx
  unsigned __int64 v104; // rcx
  __int16 v105; // ax
  _WORD *v106; // rcx
  unsigned __int64 v107; // r12
  void (__stdcall *v108)(GUID, void *); // rax
  NotificationHandler *v109; // rcx
  unsigned __int64 v110; // rdi
  void (__stdcall *v111)(GUID, void *); // rax
  unsigned __int64 v112; // rdi
  void (__stdcall *v113)(GUID, void *); // rax
  unsigned __int64 v114; // rdi
  LPVOID v115; // rax
  int v116; // [rsp+20h] [rbp-E0h]
  void *v117; // [rsp+28h] [rbp-D8h] BYREF
  NotificationHandler *v118; // [rsp+30h] [rbp-D0h]
  NotificationSettings *v119; // [rsp+38h] [rbp-C8h]
  BYTE *pInit; // [rsp+40h] [rbp-C0h] BYREF
  IStream *v121; // [rsp+48h] [rbp-B8h]
  void *v122; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v123; // [rsp+58h] [rbp-A8h] BYREF
  void (__stdcall *v124)(GUID, void *); // [rsp+60h] [rbp-A0h]
  unsigned __int64 v125; // [rsp+68h] [rbp-98h] BYREF
  void *v126; // [rsp+70h] [rbp-90h] BYREF
  struct Statement *v127; // [rsp+78h] [rbp-88h]
  IStream *v128; // [rsp+80h] [rbp-80h]
  void *Block; // [rsp+88h] [rbp-78h] BYREF
  void (__stdcall *v130)(GUID, void *); // [rsp+90h] [rbp-70h]
  _BYTE *v131; // [rsp+98h] [rbp-68h]
  void *v132[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v133; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v134; // [rsp+B8h] [rbp-48h]
  __int128 v135; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v136; // [rsp+D0h] [rbp-30h]
  __int128 v137; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v138; // [rsp+F0h] [rbp-10h]
  __int128 v139; // [rsp+100h] [rbp+0h] BYREF
  __int128 v140; // [rsp+110h] [rbp+10h]
  __int128 v141; // [rsp+120h] [rbp+20h] BYREF
  __int128 v142; // [rsp+130h] [rbp+30h]
  __int128 v143; // [rsp+140h] [rbp+40h] BYREF
  __int128 v144; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v125 = (unsigned __int64)a3;
  v3 = a2;
  v127 = (struct Statement *)a2;
  *a3 = 0;
  v119 = 0;
  v4 = 0;
  v135 = 0;
  v136 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v135, 0);
  v143 = v4;
  v144 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v143, v5);
  v137 = v4;
  v138 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v137, v6);
  v117 = v7;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(&Block);
  v141 = v4;
  v142 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v141, v8);
  v139 = v4;
  v140 = 0;
  std::wstring::_Construct_empty(&v139, v9);
  v10 = 1;
  LOBYTE(v116) = v11;
  v12 = v11;
  LODWORD(v118) = v11;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v14 = v131;
  v122 = v131;
  v124 = v130;
  v15 = Block;
  for ( pInit = (BYTE *)Block; ; v15 = pInit )
  {
    if ( !*v3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        v116);
    v16 = Statement::dal_step(*v3);
    if ( v16 != -2018574236 )
      break;
    if ( v10 != 1 )
      goto LABEL_64;
    LOBYTE(v116) = 1;
    v10 = sqlite3_column_int(*v3, 9);
    LODWORD(v121) = v10;
    ColumnText16 = Statement::GetColumnText16(v3, v132, 0);
    if ( &v135 == (__int128 *)ColumnText16 )
    {
      v18 = 0;
    }
    else
    {
      if ( v136.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>((void *)v135, 2 * v136.m128i_i64[1] + 2);
      v136 = si128;
      v18 = 0;
      LOWORD(v135) = 0;
      v135 = *(_OWORD *)ColumnText16;
      v136 = *(__m128i *)(ColumnText16 + 16);
      *(_QWORD *)(ColumnText16 + 16) = 0;
      *(_QWORD *)(ColumnText16 + 24) = 7;
      *(_WORD *)ColumnText16 = 0;
    }
    if ( v134 > 7 )
      std::_Deallocate<16>(v132[0], 2 * v134 + 2);
    v19 = Statement::GetColumnText16(v3, v132, 1);
    if ( &v143 != (__int128 *)v19 )
    {
      if ( *((_QWORD *)&v144 + 1) > 7u )
        std::_Deallocate<16>((void *)v143, 2LL * *((_QWORD *)&v144 + 1) + 2);
      v143 = *(_OWORD *)v19;
      v144 = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
    }
    if ( v134 > 7 )
      std::_Deallocate<16>(v132[0], 2 * v134 + 2);
    v20 = Statement::GetColumnText16(v3, v132, 2);
    if ( &v137 != (__int128 *)v20 )
    {
      if ( *((_QWORD *)&v138 + 1) > 7u )
        std::_Deallocate<16>((void *)v137, 2LL * *((_QWORD *)&v138 + 1) + 2);
      v137 = *(_OWORD *)v20;
      v138 = *(_OWORD *)(v20 + 16);
      *(_QWORD *)(v20 + 16) = 0;
      *(_QWORD *)(v20 + 24) = 7;
      *(_WORD *)v20 = 0;
    }
    if ( v134 > 7 )
      std::_Deallocate<16>(v132[0], 2 * v134 + 2);
    v117 = (void *)sqlite3_column_int64(*v3, 3);
    ColumnBlob = Statement::GetColumnBlob(v3, v132, 4);
    if ( &Block != (void **)ColumnBlob )
    {
      if ( v15 )
      {
        pInit = (BYTE *)(v14 - v15);
        v122 = v15;
        if ( (unsigned __int64)(v14 - v15) >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v122, (unsigned __int64 *)&pInit);
          v15 = v122;
        }
        operator delete(v15);
      }
      pInit = *(BYTE **)ColumnBlob;
      Block = pInit;
      v124 = *(void (__stdcall **)(GUID, void *))(ColumnBlob + 8);
      v130 = v124;
      v122 = *(void **)(ColumnBlob + 16);
      v131 = v122;
      *(_QWORD *)ColumnBlob = 0;
      *(_QWORD *)(ColumnBlob + 8) = 0;
      *(_QWORD *)(ColumnBlob + 16) = 0;
    }
    v22 = v132[0];
    if ( v132[0] )
    {
      v123 = v133 - (unsigned __int64)v132[0];
      v126 = v132[0];
      if ( v133 - (unsigned __int64)v132[0] >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v126, &v123);
        v22 = v126;
      }
      operator delete(v22);
    }
    v23 = Statement::GetColumnText16(v3, v132, 5);
    if ( &v141 != (__int128 *)v23 )
    {
      if ( *((_QWORD *)&v142 + 1) > 7u )
        std::_Deallocate<16>((void *)v141, 2LL * *((_QWORD *)&v142 + 1) + 2);
      v141 = *(_OWORD *)v23;
      v142 = *(_OWORD *)(v23 + 16);
      *(_QWORD *)(v23 + 16) = 0;
      *(_QWORD *)(v23 + 24) = 7;
      *(_WORD *)v23 = 0;
    }
    if ( v134 > 7 )
      std::_Deallocate<16>(v132[0], 2 * v134 + 2);
    v24 = Statement::GetColumnText16(v3, v132, 6);
    if ( &v139 != (__int128 *)v24 )
    {
      if ( *((_QWORD *)&v140 + 1) > 7u )
        std::_Deallocate<16>((void *)v139, 2LL * *((_QWORD *)&v140 + 1) + 2);
      v139 = *(_OWORD *)v24;
      v140 = *(_OWORD *)(v24 + 16);
      *(_QWORD *)(v24 + 16) = 0;
      *(_QWORD *)(v24 + 24) = 7;
      *(_WORD *)v24 = 0;
    }
    if ( v134 > 7 )
      std::_Deallocate<16>(v132[0], 2 * v134 + 2);
    v25 = (__int16 *)&v135;
    if ( v136.m128i_i64[1] > 7uLL )
      v25 = (__int16 *)v135;
    v26 = v119;
    if ( v119 )
    {
      v119 = 0;
      (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v119 = 0;
    v27 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v123 = (unsigned __int64)v27;
    v126 = v27;
    if ( !v27 )
    {
      v18 = -2147024882;
      goto LABEL_62;
    }
    v128 = (IStream *)v27;
    v28 = NotificationSettings::NotificationSettings((NotificationSettings *)v27);
    v29 = v28;
    v123 = 0;
    if ( !v25 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)v28 + 48);
      goto LABEL_194;
    }
    v30 = -1;
    do
      ++v30;
    while ( v25[v30] );
    v31 = v30 + 1;
    if ( v30 + 1 < v30 )
    {
LABEL_57:
      v18 = -2147024362;
      goto LABEL_58;
    }
    v32 = *((_QWORD *)v28 + 8);
    if ( v32 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)v28 + 48);
      if ( *((_QWORD *)v29 + 6) )
        v32 = *((_QWORD *)v29 + 7) + 1LL;
      else
        v32 = 0;
      *((_QWORD *)v29 + 8) = v32;
    }
    if ( v32 )
    {
      if ( v31 > v32 )
      {
        v128 = 0;
        v83 = 2 * v32;
        if ( !is_mul_ok(v32, 2u) )
          goto LABEL_57;
        if ( v32 > 0x800 )
          v83 = v32 + 2048;
        if ( v31 > v83 )
          v83 = v30 + 1;
        v84 = CoTaskMemRealloc(*((LPVOID *)v29 + 6), 2 * v83);
        if ( !v84 )
        {
          v18 = -2147024882;
          goto LABEL_59;
        }
        v18 = 0;
        *((_QWORD *)v29 + 8) = v83;
        *((_QWORD *)v29 + 6) = v84;
      }
    }
    else
    {
      v128 = 0;
      if ( !is_mul_ok(v31, 2u) )
        goto LABEL_57;
      v37 = CoTaskMemAlloc(2 * v31);
      if ( v37 )
      {
        *((_QWORD *)v29 + 8) = v31;
        *((_QWORD *)v29 + 6) = v37;
        *v37 = 0;
      }
      else
      {
        v18 = -2147024882;
      }
      if ( v18 < 0 )
        goto LABEL_59;
    }
    if ( v30 == -1 )
      goto LABEL_88;
    v38 = (_WORD *)*((_QWORD *)v29 + 6);
    if ( v31 > 0x7FFFFFFF )
    {
      *v38 = 0;
LABEL_88:
      *((_QWORD *)v29 + 7) = v30;
      goto LABEL_58;
    }
    if ( v30 <= 0x7FFFFFFE )
    {
      v39 = v30;
      do
      {
        if ( !v39 )
          break;
        v40 = *v25;
        if ( !*v25 )
          break;
        ++v25;
        *v38++ = v40;
        --v39;
        --v31;
      }
      while ( v31 );
      v41 = v38 - 1;
      if ( v31 )
        v41 = v38;
      *v41 = 0;
      goto LABEL_88;
    }
    *v38 = 0;
    *((_QWORD *)v29 + 7) = v30;
LABEL_58:
    if ( v18 >= 0 )
    {
      v18 = 0;
LABEL_194:
      if ( v29 )
        (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v29 + 8LL))(v29);
      v119 = v29;
      if ( v29 )
        (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v29 + 16LL))(v29);
      goto LABEL_61;
    }
LABEL_59:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationsettings.cpp",
      (const char *)(unsigned int)v18,
      v116);
    if ( v29 )
      (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v29 + 16LL))(v29);
LABEL_61:
    v10 = (unsigned int)v121;
LABEL_62:
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB8C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v18,
        v116);
    v3 = (struct sqlite3_stmt **)v127;
    v12 = (unsigned int)v118;
LABEL_64:
    if ( v10 )
    {
      v33 = *(__int64 (__fastcall **)(char *, _QWORD *, BOOL))(*((_QWORD *)v119 + 4) + 40LL);
      v34 = sqlite3_column_int64(*v3, 8) != 0;
      v35 = (_QWORD *)Statement::GetColumnText16(v3, v132, 7);
      if ( v35[3] > 7u )
        v35 = (_QWORD *)*v35;
      v36 = v33((char *)v119 + 32, v35, v34);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB93,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v36,
          v116);
      if ( v134 > 7 )
        std::_Deallocate<16>(v132[0], 2 * v134 + 2);
    }
    LODWORD(v118) = ++v12;
    if ( v12 >= v10 )
      goto LABEL_90;
    v14 = v122;
  }
  if ( v16 != -2018574235 && v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v16,
      v116);
LABEL_90:
  v42 = (__int16 *)v143;
  v43 = (__int16 *)v137;
  v44 = (__int16 *)v141;
  v45 = v116;
  if ( !(_BYTE)v116 )
    goto LABEL_121;
  v46 = SHCreateMemStream(pInit, (int)v124 - (int)pInit);
  v121 = v46;
  v128 = v46;
  v47 = (struct Statement *)&v139;
  if ( *((_QWORD *)&v140 + 1) > 7u )
    v47 = (struct Statement *)v139;
  v127 = v47;
  v48 = (__int16 *)&v141;
  if ( *((_QWORD *)&v142 + 1) > 7u )
    v48 = v44;
  v49 = (void (__stdcall *)(GUID, void *))v119;
  v50 = (__int16 *)&v143;
  if ( *((_QWORD *)&v144 + 1) > 7u )
    v50 = v42;
  v51 = (__int16 *)&v137;
  if ( *((_QWORD *)&v138 + 1) > 7u )
    v51 = v43;
  v52 = (__int16 *)&v135;
  if ( v136.m128i_i64[1] > 7uLL )
    v52 = (__int16 *)v135;
  *(_QWORD *)v125 = 0;
  v53 = (NotificationHandler *)operator new(0xE0u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v53 )
  {
    v61 = -2147024882;
    goto LABEL_117;
  }
  v54 = NotificationHandler::NotificationHandler(v53);
  v55 = v54;
  v118 = v54;
  if ( v49 )
    v49 = (void (__stdcall *)(GUID, void *))((char *)v49 + 32);
  v124 = v49;
  v56 = v54 + 6;
  if ( !v52 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v54 + 6);
LABEL_142:
    if ( v55[9] != v49 )
    {
      if ( v49 )
        (*(void (__fastcall **)(void (__stdcall *)(GUID *__struct_ptr, void *)))(*(_QWORD *)v49 + 8LL))(v49);
      v65 = v55[9];
      v55[9] = v49;
      if ( v65 )
        (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v65 + 16LL))(v65);
    }
    v66 = v55[10];
    if ( v66 )
    {
      v55[10] = 0;
      (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v66 + 16LL))(v66);
    }
    v67 = (void (__stdcall *)(GUID, void *))v121;
    if ( (char *)v55[11] != (char *)v121 )
    {
      if ( v121 )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v121 + 8LL))(v121);
      v68 = v55[11];
      v55[11] = v67;
      if ( v68 )
        (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v68 + 16LL))(v68);
    }
    v55[21] = (NotificationHandler)v117;
    v69 = v55 + 12;
    if ( !v51 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v55 + 12);
LABEL_164:
      if ( !v50 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v55 + 15);
LABEL_173:
        v78 = (LPVOID *)(v55 + 18);
        if ( !v48 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v55 + 18);
          goto LABEL_219;
        }
        v79 = -1;
        do
          ++v79;
        while ( v48[v79] );
        v80 = v79 + 1;
        if ( v79 + 1 < v79 )
          goto LABEL_180;
        v81 = (unsigned __int64)v55[20];
        if ( v81 == -1 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v55 + 18);
          if ( *v78 )
            v81 = (unsigned __int64)v55[19] + 1;
          else
            v81 = 0;
          v55[20] = (NotificationHandler)v81;
        }
        if ( v81 )
        {
          v77 = 0;
          if ( v80 > v81 )
          {
            v117 = 0;
            v114 = 2 * v81;
            if ( !is_mul_ok(v81, 2u) )
              goto LABEL_180;
            if ( v81 > 0x800 )
              v114 = v81 + 2048;
            if ( v80 > v114 )
              v114 = v79 + 1;
            v115 = CoTaskMemRealloc(*v78, 2 * v114);
            if ( !v115 )
            {
              v77 = 2147942414LL;
              goto LABEL_182;
            }
            v77 = 0;
            v55[20] = (NotificationHandler)v114;
            *v78 = v115;
          }
        }
        else
        {
          v117 = 0;
          if ( !is_mul_ok(v80, 2u) )
          {
LABEL_180:
            v77 = 2147942934LL;
            goto LABEL_181;
          }
          v101 = CoTaskMemAlloc(2 * v80);
          if ( v101 )
          {
            v102 = 0;
            v55[20] = (NotificationHandler)v80;
            *v78 = v101;
            *v101 = 0;
          }
          else
          {
            v102 = -2147024882;
          }
          v77 = (unsigned int)v102;
          if ( v102 < 0 )
            goto LABEL_182;
        }
        if ( v79 != -1 )
        {
          v103 = *v78;
          if ( v80 > 0x7FFFFFFF )
          {
            *v103 = 0;
          }
          else
          {
            if ( v79 > 0x7FFFFFFE )
            {
              *v103 = 0;
              v55[19] = (NotificationHandler)v79;
LABEL_181:
              if ( (int)v77 < 0 )
              {
LABEL_182:
                v61 = v77;
                v82 = 42;
                goto LABEL_183;
              }
LABEL_219:
              v90 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                      v55 + 22,
                      v127,
                      -1);
              v61 = v90;
              if ( v90 >= 0 )
              {
                v61 = (*(__int64 (__fastcall **)(NotificationHandler *, GUID *, unsigned __int64))*v55)(
                        v55,
                        &GUID_23eb7394_4610_4807_baec_9a72f86ffa0b,
                        v125);
                (*((void (__fastcall **)(NotificationHandler *))*v55 + 2))(v55);
                goto LABEL_116;
              }
              v77 = (unsigned int)v90;
              v82 = 43;
LABEL_183:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v82,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
                (const char *)v77,
                v116);
              goto LABEL_114;
            }
            v104 = v79;
            do
            {
              if ( !v104 )
                break;
              v105 = *v48;
              if ( !*v48 )
                break;
              ++v48;
              *v103++ = v105;
              --v104;
              --v80;
            }
            while ( v80 );
            v106 = v103 - 1;
            if ( v80 )
              v106 = v103;
            *v106 = 0;
          }
        }
        v55[19] = (NotificationHandler)v79;
        goto LABEL_181;
      }
      v74 = -1;
      do
        ++v74;
      while ( v50[v74] );
      v75 = v74 + 1;
      if ( v74 + 1 < v74 )
        goto LABEL_171;
      v76 = (unsigned __int64)v55[17];
      if ( v76 == -1 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v55 + 15);
        if ( v55[15] )
          v76 = (unsigned __int64)v55[16] + 1;
        else
          v76 = 0;
        v55[17] = (NotificationHandler)v76;
      }
      if ( v76 )
      {
        v77 = 0;
        if ( v75 > v76 )
        {
          v117 = 0;
          v112 = 2 * v76;
          if ( !is_mul_ok(v76, 2u) )
            goto LABEL_171;
          if ( v76 > 0x800 )
            v112 = v76 + 2048;
          if ( v75 > v112 )
            v112 = v74 + 1;
          v113 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(v55[15], 2 * v112);
          if ( !v113 )
          {
            v77 = 2147942414LL;
            goto LABEL_318;
          }
          v77 = 0;
          v55[17] = (NotificationHandler)v112;
          v55[15] = v113;
        }
      }
      else
      {
        v117 = 0;
        if ( !is_mul_ok(v75, 2u) )
        {
LABEL_171:
          v77 = 2147942934LL;
          goto LABEL_172;
        }
        v96 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v75);
        if ( v96 )
        {
          v77 = 0;
          v55[17] = (NotificationHandler)v75;
          v55[15] = v96;
          *(_WORD *)v96 = 0;
        }
        else
        {
          v77 = 2147942414LL;
        }
        if ( (int)v77 < 0 )
          goto LABEL_318;
      }
      if ( v74 != -1 )
      {
        v97 = v55[15];
        if ( v75 > 0x7FFFFFFF )
        {
          *v97 = 0;
        }
        else
        {
          if ( v74 > 0x7FFFFFFE )
          {
            *v97 = 0;
            v55[16] = (NotificationHandler)v74;
LABEL_172:
            if ( (int)v77 >= 0 )
              goto LABEL_173;
LABEL_318:
            v61 = v77;
            v82 = 41;
            goto LABEL_183;
          }
          v98 = v74;
          do
          {
            if ( !v98 )
              break;
            v99 = *v50;
            if ( !*v50 )
              break;
            ++v50;
            *v97++ = v99;
            --v98;
            --v75;
          }
          while ( v75 );
          v100 = v97 - 1;
          if ( v75 )
            v100 = v97;
          *v100 = 0;
        }
      }
      v55[16] = (NotificationHandler)v74;
      goto LABEL_172;
    }
    v70 = -1;
    do
      ++v70;
    while ( v51[v70] );
    v71 = v70 + 1;
    if ( v70 + 1 < v70 )
      goto LABEL_161;
    v72 = (unsigned __int64)v69[2];
    if ( v72 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v69);
      if ( *v69 )
        v72 = (unsigned __int64)v69[1] + 1;
      else
        v72 = 0;
      v69[2] = (NotificationHandler)v72;
    }
    if ( v72 )
    {
      v73 = 0;
      if ( v71 > v72 )
      {
        v117 = 0;
        v110 = 2 * v72;
        if ( !is_mul_ok(v72, 2u) )
          goto LABEL_161;
        if ( v72 > 0x800 )
          v110 = v72 + 2048;
        if ( v71 > v110 )
          v110 = v70 + 1;
        v111 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(*v69, 2 * v110);
        if ( !v111 )
        {
          v73 = 2147942414LL;
          goto LABEL_315;
        }
        v73 = 0;
        v69[2] = (NotificationHandler)v110;
        *v69 = v111;
      }
    }
    else
    {
      v117 = 0;
      if ( !is_mul_ok(v71, 2u) )
      {
LABEL_161:
        v73 = 2147942934LL;
        goto LABEL_162;
      }
      v91 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v71);
      if ( v91 )
      {
        v73 = 0;
        v69[2] = (NotificationHandler)v71;
        *v69 = v91;
        *(_WORD *)v91 = 0;
      }
      else
      {
        v73 = 2147942414LL;
      }
      if ( (int)v73 < 0 )
        goto LABEL_315;
    }
    if ( v70 != -1 )
    {
      v92 = *v69;
      if ( v71 > 0x7FFFFFFF )
      {
        *v92 = 0;
      }
      else
      {
        if ( v70 > 0x7FFFFFFE )
        {
          *v92 = 0;
          v69[1] = (NotificationHandler)v70;
LABEL_162:
          if ( (int)v73 >= 0 )
          {
            v55 = v118;
            goto LABEL_164;
          }
LABEL_315:
          v61 = v73;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x28,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
            (const char *)v73,
            v116);
          v55 = v118;
          goto LABEL_114;
        }
        v93 = v70;
        do
        {
          if ( !v93 )
            break;
          v94 = *v51;
          if ( !*v51 )
            break;
          ++v51;
          *v92++ = v94;
          --v93;
          --v71;
        }
        while ( v71 );
        v95 = v92 - 1;
        if ( v71 )
          v95 = v92;
        *v95 = 0;
      }
    }
    v69[1] = (NotificationHandler)v70;
    goto LABEL_162;
  }
  v57 = -1;
  do
    ++v57;
  while ( v52[v57] );
  v58 = v57 + 1;
  if ( v57 + 1 < v57 )
  {
LABEL_111:
    v60 = 2147942934LL;
    goto LABEL_112;
  }
  v59 = (unsigned __int64)v54[8];
  if ( v59 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v54 + 6);
    if ( *v56 )
      v59 = v56[1] + 1LL;
    else
      v59 = 0;
    v56[2] = v59;
  }
  if ( v59 )
  {
    v60 = 0;
    if ( v58 <= v59 )
      goto LABEL_205;
    v107 = 2 * v59;
    if ( is_mul_ok(v59, 2u) )
    {
      if ( v59 > 0x800 )
        v107 = v59 + 2048;
      if ( v58 > v107 )
        v107 = v57 + 1;
      v108 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(v118[6], 2 * v107);
      if ( v108 )
      {
        v60 = 0;
        v109 = v118;
        v118[8] = (NotificationHandler)v107;
        v56 = v109 + 6;
        v109[6] = v108;
        goto LABEL_205;
      }
      v60 = 2147942414LL;
      goto LABEL_113;
    }
    goto LABEL_111;
  }
  v123 = 0;
  if ( !is_mul_ok(v58, 2u) )
    goto LABEL_111;
  v85 = CoTaskMemAlloc(2 * v58);
  if ( v85 )
  {
    v60 = 0;
    v56[2] = v58;
    *v56 = v85;
    *v85 = 0;
  }
  else
  {
    v60 = 2147942414LL;
  }
  if ( (int)v60 < 0 )
    goto LABEL_113;
LABEL_205:
  if ( v57 == -1 )
    goto LABEL_215;
  v86 = (_WORD *)*v56;
  if ( v58 > 0x7FFFFFFF )
  {
    *v86 = 0;
    goto LABEL_215;
  }
  if ( v57 > 0x7FFFFFFE )
  {
    *v86 = 0;
    v56[1] = v57;
  }
  else
  {
    v87 = v57;
    do
    {
      if ( !v87 )
        break;
      v88 = *v52;
      if ( !*v52 )
        break;
      ++v52;
      *v86++ = v88;
      --v87;
      --v58;
    }
    while ( v58 );
    v89 = v86 - 1;
    if ( v58 )
      v89 = v86;
    *v89 = 0;
LABEL_215:
    v56[1] = v57;
  }
LABEL_112:
  if ( (int)v60 >= 0 )
  {
    v49 = v124;
    v55 = v118;
    goto LABEL_142;
  }
LABEL_113:
  v61 = v60;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
    (const char *)v60,
    v116);
  v55 = v118;
LABEL_114:
  if ( v55 )
    (*((void (__fastcall **)(NotificationHandler *))*v55 + 2))(v55);
LABEL_116:
  v43 = (__int16 *)v137;
  v46 = v121;
LABEL_117:
  if ( v61 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v61,
      v116);
  if ( v46 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v46 + 16LL))(v46);
  v44 = (__int16 *)v141;
  v42 = (__int16 *)v143;
  v45 = v116;
LABEL_121:
  if ( *((_QWORD *)&v140 + 1) > 7u )
    std::_Deallocate<16>((void *)v139, 2LL * *((_QWORD *)&v140 + 1) + 2);
  if ( *((_QWORD *)&v142 + 1) > 7u )
    std::_Deallocate<16>(v44, 2LL * *((_QWORD *)&v142 + 1) + 2);
  v62 = pInit;
  if ( pInit )
  {
    v125 = (_BYTE *)v122 - pInit;
    v117 = pInit;
    if ( (unsigned __int64)((_BYTE *)v122 - pInit) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v117, &v125);
      v62 = v117;
    }
    operator delete(v62);
  }
  if ( *((_QWORD *)&v138 + 1) > 7u )
    std::_Deallocate<16>(v43, 2LL * *((_QWORD *)&v138 + 1) + 2);
  if ( *((_QWORD *)&v144 + 1) > 7u )
    std::_Deallocate<16>(v42, 2LL * *((_QWORD *)&v144 + 1) + 2);
  if ( v136.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>((void *)v135, 2 * v136.m128i_i64[1] + 2);
  v136 = si128;
  LOWORD(v135) = 0;
  v63 = v119;
  if ( v119 )
  {
    v119 = 0;
    (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v63 + 16LL))(v63);
  }
  return v45;
}

```

## disassembly

```asm
0x180011e90  mov     [rsp-8+arg_0], rbx
0x180011e95  push    rbp
0x180011e96  push    rsi
0x180011e97  push    rdi
0x180011e98  push    r12
0x180011e9a  push    r13
0x180011e9c  push    r14
0x180011e9e  push    r15
0x180011ea0  lea     rbp, [rsp-80h]
0x180011ea5  sub     rsp, 180h
0x180011eac  movaps  [rsp+1B0h+var_40], xmm6
0x180011eb4  mov     rax, cs:__security_cookie
0x180011ebb  xor     rax, rsp
0x180011ebe  mov     [rbp+0B0h+var_50], rax
0x180011ec2  mov     [rsp+1B0h+var_148], r8
0x180011ec7  mov     r14, rdx
0x180011eca  mov     [rsp+1B0h+var_138], rdx
0x180011ecf  xor     edx, edx
0x180011ed1  mov     [r8], rdx
0x180011ed4  mov     [rsp+1B0h+var_178], rdx
0x180011ed9  xorps   xmm0, xmm0
0x180011edc  movups  [rbp+0B0h+var_F0], xmm0
0x180011ee0  xorps   xmm1, xmm1
0x180011ee3  movdqu  [rbp+0B0h+var_E0], xmm1
0x180011ee8  lea     rcx, [rbp+0B0h+var_F0]
0x180011eec  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011ef1  nop
0x180011ef2  movups  [rbp+0B0h+var_70], xmm0
0x180011ef6  movdqu  [rbp+0B0h+var_60], xmm1
0x180011efb  lea     rcx, [rbp+0B0h+var_70]
0x180011eff  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011f04  nop
0x180011f05  movups  [rbp+0B0h+var_D0], xmm0
0x180011f09  movdqu  [rbp+0B0h+var_C0], xmm1
0x180011f0e  lea     rcx, [rbp+0B0h+var_D0]
0x180011f12  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011f17  nop
0x180011f18  mov     [rsp+1B0h+var_188], rdx
0x180011f1d  lea     rcx, [rbp+0B0h+Block]
0x180011f21  call    ??$?0AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>(std::allocator<std::pair<ulong const,std::shared_ptr<TileSession>>> const &)
0x180011f26  nop
0x180011f27  movups  [rbp+0B0h+var_90], xmm0
0x180011f2b  movdqu  [rbp+0B0h+var_80], xmm1
0x180011f30  lea     rcx, [rbp+0B0h+var_90]
0x180011f34  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011f39  nop
0x180011f3a  movups  [rbp+0B0h+var_B0], xmm0
0x180011f3e  movdqu  [rbp+0B0h+var_A0], xmm1
0x180011f43  lea     rcx, [rbp+0B0h+var_B0]
0x180011f47  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011f4c  nop
0x180011f4d  mov     r12d, 1
0x180011f53  mov     byte ptr [rsp+1B0h+var_190], dl; int
0x180011f57  mov     r15d, edx
0x180011f5a  mov     dword ptr [rsp+1B0h+var_180], edx
0x180011f5e  mov     r13d, 8007000Eh
0x180011f64  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180011f6c  mov     rdi, [rbp+0B0h+var_118]
0x180011f70  mov     [rsp+1B0h+var_160], rdi
0x180011f75  mov     rdx, [rbp+0B0h+var_120]
0x180011f79  mov     [rsp+1B0h+var_150], rdx
0x180011f7e  mov     rsi, [rbp+0B0h+Block]
0x180011f82  mov     [rsp+1B0h+pInit], rsi
0x180011f87  nop     word ptr [rax+rax+00000000h]
0x180011f90  mov     rcx, [r14]; struct sqlite3_stmt *
0x180011f93  mov     rax, [rbp+0B8h]
0x180011f9a  test    rcx, rcx
0x180011f9d  jz      loc_180012458
0x180011fa3  call    ?dal_step@Statement@@SAJPEAUsqlite3_stmt@@@Z; Statement::dal_step(sqlite3_stmt *)
0x180011fa8  cmp     eax, 87AF0064h
0x180011fad  jnz     loc_180012849
0x180011fb3  cmp     r12d, 1
0x180011fb7  jnz     loc_1800123B8
0x180011fbd  mov     byte ptr [rsp+1B0h+var_190], r12b; int
0x180011fc2  mov     edx, 9
0x180011fc7  mov     rcx, [r14]
0x180011fca  call    cs:__imp_sqlite3_column_int
0x180011fd0  mov     r12d, eax
0x180011fd3  mov     dword ptr [rsp+1B0h+var_168], eax
0x180011fd7  xor     r8d, r8d
0x180011fda  lea     rdx, [rbp+0B0h+var_110]
0x180011fde  mov     rcx, r14
0x180011fe1  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x180011fe6  mov     rbx, rax
0x180011fe9  lea     rax, [rbp+0B0h+var_F0]
0x180011fed  cmp     rax, rbx
0x180011ff0  jz      loc_180013192
0x180011ff6  mov     rdx, qword ptr [rbp+0B0h+var_E0+8]
0x180011ffa  cmp     rdx, 7
0x180011ffe  jbe     short loc_180012011
0x180012000  lea     rdx, ds:2[rdx*2]
0x180012008  mov     rcx, qword ptr [rbp+0B0h+var_F0]
0x18001200c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012011  movdqu  [rbp+0B0h+var_E0], xmm6
0x180012016  xor     r15d, r15d
0x180012019  mov     word ptr [rbp+0B0h+var_F0], r15w
0x18001201e  movups  xmm0, xmmword ptr [rbx]
0x180012021  movups  [rbp+0B0h+var_F0], xmm0
0x180012025  movups  xmm1, xmmword ptr [rbx+10h]
0x180012029  movups  [rbp+0B0h+var_E0], xmm1
0x18001202d  mov     [rbx+10h], r15
0x180012031  mov     qword ptr [rbx+18h], 7
0x180012039  mov     [rbx], r15w
0x18001203d  mov     rdx, [rbp+0B0h+var_F8]
0x180012041  cmp     rdx, 7
0x180012045  ja      loc_180012488
0x18001204b  mov     r8d, 1
0x180012051  lea     rdx, [rbp+0B0h+var_110]
0x180012055  mov     rcx, r14
0x180012058  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x18001205d  mov     rbx, rax
0x180012060  lea     rax, [rbp+0B0h+var_70]
0x180012064  cmp     rax, rbx
0x180012067  jz      short loc_1800120A3
0x180012069  mov     rdx, qword ptr [rbp+0B0h+var_60+8]
0x18001206d  cmp     rdx, 7
0x180012071  jbe     short loc_180012084
0x180012073  lea     rdx, ds:2[rdx*2]
0x18001207b  mov     rcx, qword ptr [rbp+0B0h+var_70]
0x18001207f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012084  movups  xmm0, xmmword ptr [rbx]
0x180012087  movups  [rbp+0B0h+var_70], xmm0
0x18001208b  movups  xmm1, xmmword ptr [rbx+10h]
0x18001208f  movups  [rbp+0B0h+var_60], xmm1
0x180012093  mov     [rbx+10h], r15
0x180012097  mov     qword ptr [rbx+18h], 7
0x18001209f  mov     [rbx], r15w
0x1800120a3  mov     rdx, [rbp+0B0h+var_F8]
0x1800120a7  cmp     rdx, 7
0x1800120ab  ja      loc_18001249E
0x1800120b1  mov     r8d, 2
0x1800120b7  lea     rdx, [rbp+0B0h+var_110]
0x1800120bb  mov     rcx, r14
0x1800120be  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x1800120c3  mov     rbx, rax
0x1800120c6  lea     rax, [rbp+0B0h+var_D0]
0x1800120ca  cmp     rax, rbx
0x1800120cd  jz      short loc_180012109
0x1800120cf  mov     rdx, qword ptr [rbp+0B0h+var_C0+8]
0x1800120d3  cmp     rdx, 7
0x1800120d7  jbe     short loc_1800120EA
0x1800120d9  lea     rdx, ds:2[rdx*2]
0x1800120e1  mov     rcx, qword ptr [rbp+0B0h+var_D0]
0x1800120e5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800120ea  movups  xmm0, xmmword ptr [rbx]
0x1800120ed  movups  [rbp+0B0h+var_D0], xmm0
0x1800120f1  movups  xmm1, xmmword ptr [rbx+10h]
0x1800120f5  movups  [rbp+0B0h+var_C0], xmm1
0x1800120f9  mov     [rbx+10h], r15
0x1800120fd  mov     qword ptr [rbx+18h], 7
0x180012105  mov     [rbx], r15w
0x180012109  mov     rdx, [rbp+0B0h+var_F8]
0x18001210d  cmp     rdx, 7
0x180012111  ja      loc_1800124B4
0x180012117  mov     edx, 3
0x18001211c  mov     rcx, [r14]
0x18001211f  call    cs:__imp_sqlite3_column_int64
0x180012125  mov     [rsp+1B0h+var_188], rax
0x18001212a  mov     r8d, 4
0x180012130  lea     rdx, [rbp+0B0h+var_110]
0x180012134  mov     rcx, r14
0x180012137  call    ?GetColumnBlob@Statement@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@H@Z; Statement::GetColumnBlob(int)
0x18001213c  mov     rbx, rax
0x18001213f  lea     rax, [rbp+0B0h+Block]
0x180012143  cmp     rax, rbx
0x180012146  jz      short loc_1800121A3
0x180012148  test    rsi, rsi
0x18001214b  jz      short loc_180012172
0x18001214d  sub     rdi, rsi
0x180012150  mov     [rsp+1B0h+pInit], rdi
0x180012155  mov     [rsp+1B0h+var_160], rsi
0x18001215a  cmp     rdi, 1000h
0x180012161  jnb     loc_18001319A
0x180012167  mov     rdx, rdi
0x18001216a  mov     rcx, rsi; Block
0x18001216d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012172  mov     rax, [rbx]
0x180012175  mov     [rsp+1B0h+pInit], rax
0x18001217a  mov     [rbp+0B0h+Block], rax
0x18001217e  mov     rdi, [rbx+8]
0x180012182  mov     [rsp+1B0h+var_150], rdi
0x180012187  mov     [rbp+0B0h+var_120], rdi
0x18001218b  mov     rax, [rbx+10h]
0x18001218f  mov     [rsp+1B0h+var_160], rax
0x180012194  mov     [rbp+0B0h+var_118], rax
0x180012198  mov     [rbx], r15
0x18001219b  mov     [rbx+8], r15
0x18001219f  mov     [rbx+10h], r15
0x1800121a3  mov     rcx, [rbp+0B0h+var_110]; Block
0x1800121a7  test    rcx, rcx
0x1800121aa  jz      short loc_1800121CF
0x1800121ac  mov     rdx, [rbp+0B0h+var_100]
0x1800121b0  sub     rdx, rcx
0x1800121b3  mov     [rsp+1B0h+var_158], rdx
0x1800121b8  mov     [rsp+1B0h+var_140], rcx
0x1800121bd  cmp     rdx, 1000h
0x1800121c4  jnb     loc_1800131B8
0x1800121ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800121cf  mov     r8d, 5
0x1800121d5  lea     rdx, [rbp+0B0h+var_110]
0x1800121d9  mov     rcx, r14
0x1800121dc  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x1800121e1  mov     rbx, rax
0x1800121e4  lea     rax, [rbp+0B0h+var_90]
0x1800121e8  cmp     rax, rbx
0x1800121eb  jz      short loc_180012227
0x1800121ed  mov     rdx, qword ptr [rbp+0B0h+var_80+8]
0x1800121f1  cmp     rdx, 7
0x1800121f5  jbe     short loc_180012208
0x1800121f7  lea     rdx, ds:2[rdx*2]
0x1800121ff  mov     rcx, qword ptr [rbp+0B0h+var_90]
0x180012203  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012208  movups  xmm0, xmmword ptr [rbx]
0x18001220b  movups  [rbp+0B0h+var_90], xmm0
0x18001220f  movups  xmm1, xmmword ptr [rbx+10h]
0x180012213  movups  [rbp+0B0h+var_80], xmm1
0x180012217  mov     [rbx+10h], r15
0x18001221b  mov     qword ptr [rbx+18h], 7
0x180012223  mov     [rbx], r15w
0x180012227  mov     rdx, [rbp+0B0h+var_F8]
0x18001222b  cmp     rdx, 7
0x18001222f  ja      loc_1800124CA
0x180012235  mov     r8d, 6
0x18001223b  lea     rdx, [rbp+0B0h+var_110]
0x18001223f  mov     rcx, r14
0x180012242  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x180012247  mov     rbx, rax
0x18001224a  lea     rax, [rbp+0B0h+var_B0]
0x18001224e  cmp     rax, rbx
0x180012251  jz      short loc_18001228D
0x180012253  mov     rdx, qword ptr [rbp+0B0h+var_A0+8]
0x180012257  cmp     rdx, 7
0x18001225b  jbe     short loc_18001226E
0x18001225d  lea     rdx, ds:2[rdx*2]
0x180012265  mov     rcx, qword ptr [rbp+0B0h+var_B0]
0x180012269  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001226e  movups  xmm0, xmmword ptr [rbx]
0x180012271  movups  [rbp+0B0h+var_B0], xmm0
0x180012275  movups  xmm1, xmmword ptr [rbx+10h]
0x180012279  movups  [rbp+0B0h+var_A0], xmm1
0x18001227d  mov     [rbx+10h], r15
0x180012281  mov     qword ptr [rbx+18h], 7
0x180012289  mov     [rbx], r15w
0x18001228d  mov     rdx, [rbp+0B0h+var_F8]
0x180012291  cmp     rdx, 7
0x180012295  ja      loc_1800124E0
0x18001229b  lea     rbx, [rbp+0B0h+var_F0]
0x18001229f  cmp     qword ptr [rbp+0B0h+var_E0+8], 7
0x1800122a4  cmova   rbx, qword ptr [rbp+0B0h+var_F0]
0x1800122a9  mov     rcx, [rsp+1B0h+var_178]
0x1800122ae  test    rcx, rcx
0x1800122b1  jz      short loc_1800122C5
0x1800122b3  mov     [rsp+1B0h+var_178], r15
0x1800122b8  mov     rax, [rcx]
0x1800122bb  mov     rax, [rax+10h]
0x1800122bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122c4  nop
0x1800122c5  mov     [rsp+1B0h+var_178], r15
0x1800122ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800122d1  mov     ecx, 90h; unsigned __int64
0x1800122d6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800122db  mov     [rsp+1B0h+var_158], rax
0x1800122e0  mov     [rsp+1B0h+var_140], rax
0x1800122e5  test    rax, rax
0x1800122e8  jz      loc_18001259A
0x1800122ee  mov     [rbp+0B0h+var_130], rax
0x1800122f2  mov     rcx, rax; this
0x1800122f5  call    ??0NotificationSettings@@QEAA@XZ; NotificationSettings::NotificationSettings(void)
0x1800122fa  mov     r13, rax
0x1800122fd  mov     [rsp+1B0h+var_158], r15
0x180012302  test    rbx, rbx
0x180012305  jz      loc_180012EC0
0x18001230b  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180012312  inc     r14
0x180012315  cmp     word ptr [rbx+r14*2], 0
0x18001231b  jnz     short loc_180012312
0x18001231d  lea     rdi, [r14+1]
0x180012321  cmp     rdi, r14
0x180012324  jb      short loc_180012352
0x180012326  mov     r8, [rax+40h]
0x18001232a  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001232e  jz      loc_180012B46
0x180012334  test    r8, r8
0x180012337  jnz     loc_180012A90
0x18001233d  mov     [rbp+0B0h+var_130], r15
0x180012341  mov     eax, 2
0x180012346  mul     rdi
0x180012349  test    rdx, rdx
0x18001234c  jz      loc_18001250B
0x180012352  mov     r15d, 80070216h
0x180012358  test    r15d, r15d
0x18001235b  jns     loc_180012B0D
0x180012361  mov     rcx, [rbp+0B8h]; this
0x180012368  mov     r9d, r15d; char *
0x18001236b  lea     r8, aOnecoreuapBase_151; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180012372  mov     edx, 10h; void *
0x180012377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001237c  nop
0x18001237d  test    r13, r13
0x180012380  jz      short loc_180012393
  ... truncated ...
```
