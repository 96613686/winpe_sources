# ShaderDiskCacheSQLite::ShaderDiskCacheSQLite(ushort const *,ulong,uint,ShaderCacheStatistics &,ShaderDiskCacheSQLite::InitializeFlags)

- ea: `0x1800434e0`
- end: `0x1800444ee`
- name: `??0ShaderDiskCacheSQLite@@QEAA@PEBGKIAEAUShaderCacheStatistics@@W4InitializeFlags@0@@Z`
- size: `4110`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int, DWORD, __int64, int)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800432ec`
- `0x18004ffd8`

## callees

- `0x180001d30`
- `0x1800204f0`
- `0x180020b78`
- `0x18002ca78`
- `0x18002e150`
- `0x1800334f0`
- `0x1800337f4`
- `0x1800353e4`
- `0x180039508`
- `0x18003a894`
- `0x18003ab40`
- `0x18003aec0`
- `0x18003c13c`
- `0x18003c270`
- `0x1800415b0`
- `0x180041c88`
- `0x1800434e0`
- `0x1800449f0`
- `0x1800485d8`
- `0x180048684`
- `0x180048804`
- `0x1800490b0`
- `0x180049838`
- `0x18004ee78`
- `0x18004eff0`
- `0x180093590`
- `0x180093a00`
- `0x1800a6cd8`
- `0x1800a6d08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800435b5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800435b5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180043639`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800436ec`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180043639`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800436ec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180044458`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180044458`

## string_xrefs

- `0x180043c3a`: `DROP TABLE IF EXISTS vals;DROP TABLE IF EXISTS keys;DROP TABLE IF EXISTS cache;DROP TABLE IF EXISTS app_id;DROP TABLE IF EXISTS driver_id;DROP TABLE IF EXISTS compiler_id;DROP TABLE IF EXISTS groupkeys;DROP TABLE IF EXISTS groups;`
- `0x180043c59`: `PRAGMA journal_mode=WAL;CREATE TABLE keys(keyid INTEGER PRIMARY KEY, key BLOB, last_accessed REAL);CREATE UNIQUE INDEX key_index ON keys(key);CREATE INDEX lru ON keys(last_accessed DESC);CREATE TABLE vals(keyid INTEGER REFERENCES keys(keyid) ON DELETE CASCADE, type INTEGER, value BLOB);CREATE UNIQUE INDEX value_index ON vals(keyid, type);CREATE TABLE groupkeys(keyid INTEGER PRIMARY KEY, key BLOB, version INTEGER);CREATE UNIQUE INDEX groupkey_index ON groupkeys(key);CREATE TABLE groups(groupkeyid`

## pseudocode

```c
__int64 __fastcall ShaderDiskCacheSQLite::ShaderDiskCacheSQLite(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        DWORD a4,
        __int64 a5,
        int a6)
{
  int v6; // r12d
  _QWORD *v9; // r13
  wchar_t *v10; // rax
  const WCHAR *v11; // rax
  size_t v12; // r14
  unsigned __int64 cbMultiByte; // rbx
  LPSTR *v14; // rax
  CHAR *lpMultiByteStr; // rax
  LPSTR *v16; // rax
  unsigned __int8 v17; // r12
  size_t v18; // rdi
  __int64 v19; // rcx
  __m128i *v20; // rbx
  __int8 *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __m128i *v26; // rax
  LPSTR *v27; // rcx
  LPSTR *v28; // rdx
  LPSTR *v29; // rbx
  LPSTR *i; // r15
  __int64 v31; // r9
  __int64 v32; // rcx
  __m128i *v33; // rax
  __int64 v34; // rcx
  __m128i *v35; // rbx
  __int8 *v36; // rbx
  unsigned int v37; // ebx
  int v38; // eax
  char v39; // di
  LPSTR *v40; // rcx
  LPSTR *v41; // rcx
  int v42; // eax
  int busy; // eax
  __int64 v44; // rax
  struct IErrorInfo *v45; // r8
  bool v46; // r9
  __int64 v47; // r14
  int v48; // eax
  __m128i *v49; // rcx
  const char *v50; // rax
  __int64 v51; // rdx
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  __int64 v56; // rax
  int v57; // eax
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // rax
  int v61; // eax
  __int64 v62; // rax
  int v63; // eax
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rax
  int v67; // eax
  __int64 v68; // rax
  int v69; // eax
  __int64 v70; // rax
  int v71; // eax
  __int64 v72; // rax
  int v73; // eax
  __int64 v74; // rax
  int v75; // eax
  int v76; // eax
  char v77; // al
  __int64 v79; // rbx
  int InBuffer; // [rsp+40h] [rbp-448h] BYREF
  LPCWCH lpWideCharStr; // [rsp+48h] [rbp-440h]
  __int64 v82; // [rsp+50h] [rbp-438h]
  const unsigned __int16 *v83; // [rsp+60h] [rbp-428h]
  ShaderDiskCacheSQLite *v84; // [rsp+68h] [rbp-420h]
  _BYTE pExceptionObject[32]; // [rsp+70h] [rbp-418h] BYREF
  LPSTR v86[2]; // [rsp+90h] [rbp-3F8h] BYREF
  __m128i v87; // [rsp+A0h] [rbp-3E8h]
  __int64 Src; // [rsp+B0h] [rbp-3D8h] BYREF
  _QWORD v89[2]; // [rsp+B8h] [rbp-3D0h] BYREF
  DWORD BytesReturned[2]; // [rsp+C8h] [rbp-3C0h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-3B8h] BYREF
  char v92[16]; // [rsp+E0h] [rbp-3A8h] BYREF
  __m128i v93; // [rsp+F0h] [rbp-398h] BYREF
  __m128i v94; // [rsp+100h] [rbp-388h]
  __m128i v95; // [rsp+110h] [rbp-378h] BYREF
  __m128i v96; // [rsp+120h] [rbp-368h] BYREF
  __m128i v97; // [rsp+130h] [rbp-358h]
  char v98[48]; // [rsp+140h] [rbp-348h] BYREF
  _OWORD v99[7]; // [rsp+170h] [rbp-318h] BYREF
  char v100[16]; // [rsp+1E0h] [rbp-2A8h] BYREF
  __m128i v101; // [rsp+1F0h] [rbp-298h] BYREF
  __m128i v102; // [rsp+200h] [rbp-288h]
  __m128i v103; // [rsp+210h] [rbp-278h]
  __m128i v104; // [rsp+220h] [rbp-268h]
  __m128i v105; // [rsp+230h] [rbp-258h]
  __m128i v106; // [rsp+240h] [rbp-248h]
  __m128i v107; // [rsp+250h] [rbp-238h]
  __m128i v108; // [rsp+260h] [rbp-228h]
  __m128i v109; // [rsp+270h] [rbp-218h] BYREF
  __int16 v110; // [rsp+280h] [rbp-208h]

  BytesReturned[0] = a4;
  v6 = a3;
  InBuffer = a3;
  lpWideCharStr = a2;
  v89[0] = a5;
  v84 = (ShaderDiskCacheSQLite *)a1;
  v83 = a2;
  v82 = a5;
  *(_DWORD *)a1 = a6;
  v9 = (_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_BYTE *)(a1 + 160) = 0;
  v10 = wcsrchr(a2, 0x5Cu);
  if ( v10 )
    v11 = v10 + 1;
  else
    v11 = a2;
  *(_QWORD *)a5 = v11;
  *(_BYTE *)(a5 + 152) = (unsigned int)(v6 - 3) <= 1;
  *(_BYTE *)(a5 + 153) = 0;
  *(_BYTE *)(a5 + 154) = (a6 & 2) != 0;
  *(_BYTE *)(a5 + 155) = 0;
  if ( (*(_BYTE *)a1 & 1) != 0 && (v6 != 3 || (a6 & 2) != 0) )
    ThrowFailure(-2147024809);
  v12 = -1;
  cbMultiByte = WideCharToMultiByte(0xFDE9u, 0, a2, -1, 0, 0, 0, 0);
  std::string::string(v86);
  if ( !(_DWORD)cbMultiByte )
    ThrowFailure(-2147467259);
  if ( cbMultiByte > v87.m128i_i64[0] )
  {
    std::string::append(v86, cbMultiByte - v87.m128i_i64[0]);
  }
  else
  {
    v87.m128i_i64[0] = cbMultiByte;
    v14 = v86;
    if ( v87.m128i_i64[1] > 0xFuLL )
      v14 = (LPSTR *)v86[0];
    *((_BYTE *)v14 + cbMultiByte) = 0;
  }
  lpMultiByteStr = (CHAR *)v86;
  if ( v87.m128i_i64[1] > 0xFuLL )
    lpMultiByteStr = v86[0];
  WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( (a6 & 0x80u) == 0 )
  {
    if ( (a6 & 1) != 0 )
      v37 = 32769;
    else
      v37 = (v6 != 3 ? 4 : 0) | 0x8002;
  }
  else
  {
    std::string::string(&v93);
    strcpy((char *)&Src, "file:");
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(v92, "le=1");
    if ( (int)cbMultiByte <= 2 )
      goto LABEL_22;
    v16 = v86;
    if ( v87.m128i_i64[1] > 0xFuLL )
      v16 = (LPSTR *)v86[0];
    v17 = 1;
    if ( *((_BYTE *)v16 + 1) != 58 )
LABEL_22:
      v17 = 0;
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)&v89[-1] + v18) );
    do
      ++v12;
    while ( si128.m128i_i8[v12] );
    std::string::reserve(&v93, cbMultiByte + v17 + v12 + v18);
    v19 = v94.m128i_i64[0];
    if ( v18 > v94.m128i_i64[1] - v94.m128i_i64[0] )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        &v93,
        v18);
    }
    else
    {
      v94.m128i_i64[0] += v18;
      v20 = &v93;
      if ( v94.m128i_i64[1] > 0xFuLL )
        v20 = (__m128i *)v93.m128i_i64[0];
      v21 = &v20->m128i_i8[v19];
      memcpy_0(v21, &Src, v18);
      v21[v18] = 0;
    }
    if ( v17 )
    {
      v25 = v94.m128i_i64[0];
      if ( v94.m128i_i64[0] >= (unsigned __int64)v94.m128i_i64[1] )
      {
        LOBYTE(v24) = 47;
        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(&v93, v22, v23, v24);
      }
      else
      {
        ++v94.m128i_i64[0];
        v26 = &v93;
        if ( v94.m128i_i64[1] > 0xFuLL )
          v26 = (__m128i *)v93.m128i_i64[0];
        *(__int16 *)((char *)v26->m128i_i16 + v25) = 47;
      }
    }
    if ( v87.m128i_i64[1] <= 0xFuLL )
    {
      v27 = v86;
      v28 = v86;
    }
    else
    {
      v27 = (LPSTR *)v86[0];
      v28 = (LPSTR *)v86[0];
    }
    v29 = v27;
    for ( i = (LPSTR *)((char *)v28 + v87.m128i_i64[0]); v29 != i; v29 = (LPSTR *)((char *)v29 + 1) )
    {
      if ( *(_BYTE *)v29 )
      {
        v31 = *(unsigned __int8 *)v29;
        if ( *(_BYTE *)v29 == 92 )
          v31 = 47;
        v32 = v94.m128i_i64[0];
        if ( v94.m128i_i64[0] >= (unsigned __int64)v94.m128i_i64[1] )
        {
          std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(&v93, v28, v23, v31);
        }
        else
        {
          ++v94.m128i_i64[0];
          v33 = &v93;
          if ( v94.m128i_i64[1] > 0xFuLL )
            v33 = (__m128i *)v93.m128i_i64[0];
          v33->m128i_i8[v32] = v31;
          v33->m128i_i8[v32 + 1] = 0;
        }
      }
    }
    v34 = v94.m128i_i64[0];
    if ( v12 > v94.m128i_i64[1] - v94.m128i_i64[0] )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        &v93,
        v12);
    }
    else
    {
      v94.m128i_i64[0] += v12;
      v35 = &v93;
      if ( v94.m128i_i64[1] > 0xFuLL )
        v35 = (__m128i *)v93.m128i_i64[0];
      v36 = &v35->m128i_i8[v34];
      memcpy_0(v36, &si128, v12);
      v36[v12] = 0;
    }
    std::string::_Tidy_deallocate(v86);
    *(__m128i *)v86 = v93;
    v87 = v94;
    v94.m128i_i64[0] = 0;
    v94.m128i_i64[1] = 15;
    v93.m128i_i8[0] = 0;
    v37 = 32833;
    std::string::_Tidy_deallocate(&v93);
    v6 = InBuffer;
  }
  try
  {
    v38 = sqlite3_initialize();
    ThrowSQLiteFailure(v38);
    if ( ((v6 - 1) & 0xFFFFFFFA) != 0 || (v39 = 1, v6 == 6) )
      v39 = 0;
    if ( v6 == 4 )
    {
      wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,int (sqlite3 *),&int sqlite3_close_v2(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>::reset(
        v9,
        0);
      v40 = v86;
      if ( v87.m128i_i64[1] > 0xFuLL )
        v40 = (LPSTR *)v86[0];
      if ( (unsigned int)openDatabase(v40, v9, v37, 0) )
      {
        ShaderDiskCacheSQLite::DeleteCacheFiles((ShaderDiskCacheSQLite *)a1, lpWideCharStr);
        v39 = 1;
      }
    }
    if ( !*v9 )
    {
      wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,int (sqlite3 *),&int sqlite3_close_v2(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>::reset(
        v9,
        0);
      v41 = v86;
      if ( v87.m128i_i64[1] > 0xFuLL )
        v41 = (LPSTR *)v86[0];
      v42 = openDatabase(v41, v9, v37, 0);
      ThrowSQLiteFailure(v42);
    }
    busy = sqlite3_busy_timeout(*v9, 2000);
    ThrowSQLiteFailure(busy);
    if ( v39 )
    {
      v47 = v89[0];
    }
    else
    {
      Src = 0;
      v93 = _mm_load_si128((const __m128i *)&_xmm);
      v94 = _mm_load_si128((const __m128i *)&_xmm);
      v95 = _mm_load_si128((const __m128i *)&_xmm);
      v96 = _mm_load_si128((const __m128i *)&_xmm);
      v97 = _mm_load_si128((const __m128i *)&_xmm);
      strcpy(v98, "on_id()");
      v44 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(&Src);
      if ( (unsigned int)sqlite3LockAndPrepare(*v9, (unsigned int)&v93, 88, 128, 0, v44, 0)
        || (unsigned int)sqlite3_step(Src) != 100
        || (unsigned int)sqlite3_column_int(Src, 0) != 5
        || (unsigned int)sqlite3_column_int(Src, 1) != -741266213 )
      {
        if ( v6 == 3 )
        {
          _com_error::_com_error((_com_error *)pExceptionObject, -2005270477, v45, v46);
          throw (_com_error *)pExceptionObject;
        }
        v39 = 1;
      }
      v47 = v89[0];
      *(_BYTE *)(v89[0] + 153LL) = 1;
      wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(&Src);
      if ( !v39 )
        goto LABEL_85;
    }
    v48 = sqlite3_exec(
            *v9,
            (unsigned int)"DROP TABLE IF EXISTS vals;DROP TABLE IF EXISTS keys;DROP TABLE IF EXISTS cache;DROP TABLE IF E"
                          "XISTS app_id;DROP TABLE IF EXISTS driver_id;DROP TABLE IF EXISTS compiler_id;DROP TABLE IF EXI"
                          "STS groupkeys;DROP TABLE IF EXISTS groups;",
            0,
            0,
            0);
    ThrowSQLiteFailure(v48);
    v49 = &v101;
    v50 = "PRAGMA journal_mode=WAL;CREATE TABLE keys(keyid INTEGER PRIMARY KEY, key BLOB, last_accessed REAL);CREATE UNIQ"
          "UE INDEX key_index ON keys(key);CREATE INDEX lru ON keys(last_accessed DESC);CREATE TABLE vals(keyid INTEGER R"
          "EFERENCES keys(keyid) ON DELETE CASCADE, type INTEGER, value BLOB);CREATE UNIQUE INDEX value_index ON vals(key"
          "id, type);CREATE TABLE groupkeys(keyid INTEGER PRIMARY KEY, key BLOB, version INTEGER);CREATE UNIQUE INDEX gro"
          "upkey_index ON groupkeys(key);CREATE TABLE groups(groupkeyid INTEGER REFERENCES groupkeys(keyid) ON DELETE CAS"
          "CADE, valuekeyid INTEGER);";
    v51 = 4;
    do
    {
      *v49 = *(__m128i *)v50;
      v49[1] = *((__m128i *)v50 + 1);
      v49[2] = *((__m128i *)v50 + 2);
      v49[3] = *((__m128i *)v50 + 3);
      v49[4] = *((__m128i *)v50 + 4);
      v49[5] = *((__m128i *)v50 + 5);
      v49[6] = *((__m128i *)v50 + 6);
      v49[7] = *((__m128i *)v50 + 7);
      v49 += 8;
      v50 += 128;
      --v51;
    }
    while ( v51 );
    *v49 = *(__m128i *)v50;
    v49[1] = *((__m128i *)v50 + 1);
    v49[2] = *((__m128i *)v50 + 2);
    v49[3] = *((__m128i *)v50 + 3);
    v49[4].m128i_i8[0] = v50[64];
    v52 = sqlite3_exec(*v9, (unsigned int)&v101, 0, 0, 0);
    ThrowSQLiteFailure(v52);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(v92, "ion = 5");
    v53 = sqlite3_exec(*v9, (unsigned int)&si128, 0, 0, 0);
    ThrowSQLiteFailure(v53);
    v93 = _mm_load_si128((const __m128i *)&_xmm);
    v94 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(v95.m128i_i8, "13");
    v54 = sqlite3_exec(*v9, (unsigned int)&v93, 0, 0, 0);
    ThrowSQLiteFailure(v54);
    if ( BytesReturned[0] )
    {
      sprintf_s<128>(&v93, "PRAGMA max_page_count=%d", ((unsigned __int64)BytesReturned[0] + 4095) >> 12);
      sqlite3_exec(*v9, (unsigned int)&v93, 0, 0, 0);
    }
LABEL_85:
    v55 = sqlite3_exec(*v9, (unsigned int)"PRAGMA synchronous=NORMAL; PRAGMA foreign_keys=ON;", 0, 0, 0);
    ThrowSQLiteFailure(v55);
    if ( (*(_BYTE *)a1 & 1) != 0 || (*(_BYTE *)a1 & 0x40) == 0 )
    {
      v93 = _mm_load_si128((const __m128i *)&_xmm);
      v94 = _mm_load_si128((const __m128i *)&_xmm);
      v95 = _mm_load_si128((const __m128i *)&_xmm);
      v96 = _mm_load_si128((const __m128i *)&_xmm);
      v97 = _mm_load_si128((const __m128i *)&_xmm);
      strcpy(v98, " BY vals.keyid");
      v60 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 16);
      v61 = sqlite3LockAndPrepare(*v9, (unsigned int)&v93, 95, 129, 0, v60, 0);
      ThrowSQLiteFailure(v61);
    }
    else
    {
      v101 = _mm_load_si128((const __m128i *)&_xmm);
      v102 = _mm_load_si128((const __m128i *)&_xmm);
      v103 = _mm_load_si128((const __m128i *)&_xmm);
      v104 = _mm_load_si128((const __m128i *)&_xmm);
      v105 = _mm_load_si128((const __m128i *)&_xmm);
      v106 = _mm_load_si128((const __m128i *)&_xmm);
      v107 = _mm_load_si128((const __m128i *)&_xmm);
      v108 = _mm_load_si128((const __m128i *)&_xmm);
      strcpy(v109.m128i_i8, "yid)");
      v56 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 16);
      v57 = sqlite3LockAndPrepare(*v9, (unsigned int)&v101, 133, 129, 0, v56, 0);
      ThrowSQLiteFailure(v57);
      v93 = _mm_load_si128((const __m128i *)&_xmm);
      v94 = _mm_load_si128((const __m128i *)&_xmm);
      v95 = _mm_load_si128((const __m128i *)&_xmm);
      v96 = _mm_load_si128((const __m128i *)&_xmm);
      v97.m128i_i8[0] = 0;
      v58 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 24);
      v59 = sqlite3LockAndPrepare(*v9, (unsigned int)&v93, 65, 129, 0, v58, 0);
      ThrowSQLiteFailure(v59);
    }
    v99[0] = _mm_load_si128((const __m128i *)&_xmm);
    v99[1] = _mm_load_si128((const __m128i *)&_xmm);
    v99[2] = _mm_load_si128((const __m128i *)&_xmm);
    v99[3] = _mm_load_si128((const __m128i *)&_xmm);
    v99[4] = _mm_load_si128((const __m128i *)&_xmm);
    v99[5] = _mm_load_si128((const __m128i *)&_xmm);
    v99[6] = _mm_load_si128((const __m128i *)&_xmm);
    strcpy(v100, "s.keyid");
    v62 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 32);
    v63 = sqlite3LockAndPrepare(*v9, (unsigned int)v99, 120, 129, 0, v62, 0);
    ThrowSQLiteFailure(v63);
    if ( (*(_BYTE *)a1 & 1) == 0 )
    {
      strcpy((char *)&Src, "BEGIN");
      v64 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 40);
      v65 = sqlite3LockAndPrepare(*v9, (unsigned int)&Src, 6, 129, 0, v64, 0);
      ThrowSQLiteFailure(v65);
      v101 = _mm_load_si128((const __m128i *)&_xmm);
      v102 = _mm_load_si128((const __m128i *)&_xmm);
      v103 = _mm_load_si128((const __m128i *)&_xmm);
      v104 = _mm_load_si128((const __m128i *)&_xmm);
      v105 = _mm_load_si128((const __m128i *)&_xmm);
      v106 = _mm_load_si128((const __m128i *)&_xmm);
      v107 = _mm_load_si128((const __m128i *)&_xmm);
      v108 = _mm_load_si128((const __m128i *)&_xmm);
      v109 = _mm_load_si128((const __m128i *)&_xmm);
      v110 = 100;
      v66 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 48);
      v67 = sqlite3LockAndPrepare(*v9, (unsigned int)&v101, 146, 129, 0, v66, 0);
      ThrowSQLiteFailure(v67);
      v93 = _mm_load_si128((const __m128i *)&_xmm);
      v94 = _mm_load_si128((const __m128i *)&_xmm);
      v95 = _mm_load_si128((const __m128i *)&_xmm);
      strcpy(v96.m128i_i8, "?, ?)");
      v68 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 56);
      v69 = sqlite3LockAndPrepare(*v9, (unsigned int)&v93, 54, 129, 0, v68, 0);
      ThrowSQLiteFailure(v69);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      strcpy(v92, " WHERE key=?");
      v70 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 64);
      v71 = sqlite3LockAndPrepare(*v9, (unsigned int)&si128, 29, 129, 0, v70, 0);
      ThrowSQLiteFailure(v71);
      strcpy((char *)BytesReturned, "COMMIT");
      v72 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 72);
      v73 = sqlite3LockAndPrepare(*v9, (unsigned int)BytesReturned, 7, 129, 0, v72, 0);
      ThrowSQLiteFailure(v73);
      strcpy((char *)v89, "ROLLBACK");
      v74 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>>::put(a1 + 80);
      v75 = sqlite3LockAndPrepare(*v9, (unsigned int)v89, 9, 129, 0, v74, 0);
      ThrowSQLiteFailure(v75);
    }
    v76 = sqlite3_file_control(*v9, 0, 29, a1 + 152);
    if ( (int)TranslateSQLiteFailure(v76) >= 0 )
    {
      v89[0] = a1;
      v77 = lambda_7d3d93f4ce25d8cb9f083418059ced9a_::operator()(v89);
      *(_BYTE *)(a1 + 160) = v77;
      if ( (*(_BYTE *)a1 & 4) != 0 && !v77 && (*(_BYTE *)a1 & 1) == 0 )
      {
        LOWORD(InBuffer) = 1;
        BytesReturned[0] = 0;
        DeviceIoControl(*(HANDLE *)(a1 + 152), 0x9C040u, &InBuffer, 2u, 0, 0, BytesReturned, 0);
        *(_BYTE *)(a1 + 160) = lambda_7d3d93f4ce25d8cb9f083418059ced9a_::operator()(v89);
      }
    }
  }
  catch ( ... )
  {
    v79 = v82;
    if ( *(_BYTE *)(v82 + 154) )
    {
      ShaderDiskCacheSQLite::DeleteCacheFiles(v84, v83);
      *(_BYTE *)(v79 + 155) = 1;
    }
    throw;
  }
  ShaderDiskCacheSQLite::GetStatistics(
    (ShaderDiskCacheSQLite *)a1,
    (unsigned int *)(v47 + 48),
    (unsigned __int64 *)(v47 + 56),
    (unsigned __int64 *)(v47 + 64),
    (unsigned __int64 *)(v47 + 72),
    (int *)(v47 + 80));
  std::string::_Tidy_deallocate(v86);
  return a1;
}

```

## disassembly

```asm
0x1800434e0  push    rbx
0x1800434e2  push    rsi
0x1800434e3  push    rdi
0x1800434e4  push    r12
0x1800434e6  push    r13
0x1800434e8  push    r14
0x1800434ea  push    r15
0x1800434ec  sub     rsp, 450h
0x1800434f3  mov     rax, cs:__security_cookie
0x1800434fa  xor     rax, rsp
0x1800434fd  mov     [rsp+488h+var_48], rax
0x180043505  mov     [rsp+488h+BytesReturned], r9d
0x18004350d  mov     r12d, r8d
0x180043510  mov     [rsp+488h+InBuffer], r8d
0x180043515  mov     rbx, rdx
0x180043518  mov     [rsp+488h+lpWideCharStr], rdx
0x18004351d  mov     rsi, rcx
0x180043520  mov     r14, [rsp+488h+arg_20]
0x180043528  mov     qword ptr [rsp+488h+var_3D0], r14
0x180043530  mov     [rsp+488h+var_420], rcx
0x180043535  mov     [rsp+488h+var_428], rdx
0x18004353a  mov     [rsp+488h+var_438], r14
0x18004353f  mov     edi, [rsp+488h+arg_28]
0x180043546  mov     [rcx], edi
0x180043548  lea     r13, [rcx+8]
0x18004354c  xor     r15d, r15d
0x18004354f  mov     [r13+0], r15
0x180043553  mov     [rcx+10h], r15
0x180043557  mov     [rcx+18h], r15
0x18004355b  mov     [rcx+20h], r15
0x18004355f  mov     [rcx+28h], r15
0x180043563  mov     [rcx+30h], r15
0x180043567  mov     [rcx+38h], r15
0x18004356b  mov     [rcx+40h], r15
0x18004356f  mov     [rcx+48h], r15
0x180043573  mov     [rcx+50h], r15
0x180043577  mov     [rcx+58h], r15
0x18004357b  mov     [rcx+60h], r15
0x18004357f  mov     [rcx+68h], r15
0x180043583  mov     [rcx+70h], r15
0x180043587  mov     [rcx+78h], r15
0x18004358b  mov     [rcx+80h], r15
0x180043592  mov     [rcx+88h], r15
0x180043599  mov     [rcx+90h], r15
0x1800435a0  mov     [rcx+98h], r15
0x1800435a7  mov     [rcx+0A0h], r15b
0x1800435ae  lea     edx, [r15+5Ch]; Ch
0x1800435b2  mov     rcx, rbx; Str
0x1800435b5  call    cs:__imp_wcsrchr
0x1800435bb  test    rax, rax
0x1800435be  jz      short loc_1800435C6
0x1800435c0  add     rax, 2
0x1800435c4  jmp     short loc_1800435C9
0x1800435c6  mov     rax, rbx
0x1800435c9  mov     [r14], rax
0x1800435cc  lea     eax, [r12-3]
0x1800435d1  cmp     eax, 1
0x1800435d4  setbe   al
0x1800435d7  mov     [r14+98h], al
0x1800435de  mov     [r14+99h], r15b
0x1800435e5  mov     ecx, edi
0x1800435e7  and     ecx, 2
0x1800435ea  setnz   al
0x1800435ed  mov     [r14+9Ah], al
0x1800435f4  mov     [r14+9Bh], r15b
0x1800435fb  test    byte ptr [rsi], 1
0x1800435fe  jz      short loc_180043614
0x180043600  cmp     r12d, 3
0x180043604  jnz     short loc_18004360A
0x180043606  test    ecx, ecx
0x180043608  jz      short loc_180043614
0x18004360a  mov     ecx, 80070057h; int
0x18004360f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180043614  mov     [rsp+488h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180043619  mov     [rsp+488h+lpDefaultChar], r15; lpDefaultChar
0x18004361e  mov     [rsp+488h+cbMultiByte], r15d; cbMultiByte
0x180043623  mov     [rsp+488h+lpMultiByteStr], r15; lpMultiByteStr
0x180043628  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004362c  mov     r9d, r14d; cchWideChar
0x18004362f  mov     r8, rbx; lpWideCharStr
0x180043632  xor     edx, edx; dwFlags
0x180043634  mov     ecx, 0FDE9h; CodePage
0x180043639  call    cs:__imp_WideCharToMultiByte
0x18004363f  movsxd  rbx, eax
0x180043642  lea     rcx, [rsp+488h+var_3F8]
0x18004364a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18004364f  nop
0x180043650  test    ebx, ebx
0x180043652  jnz     short loc_18004365E
0x180043654  mov     ecx, 80004005h; int
0x180043659  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18004365e  cmp     rbx, qword ptr [rsp+488h+var_3E8]
0x180043666  ja      short loc_180043690
0x180043668  mov     qword ptr [rsp+488h+var_3E8], rbx
0x180043670  lea     rax, [rsp+488h+var_3F8]
0x180043678  cmp     qword ptr [rsp+488h+var_3E8+8], 0Fh
0x180043681  cmova   rax, [rsp+488h+var_3F8]
0x18004368a  mov     byte ptr [rax+rbx], 0
0x18004368e  jmp     short loc_1800436A8
0x180043690  mov     rdx, rbx
0x180043693  sub     rdx, qword ptr [rsp+488h+var_3E8]
0x18004369b  lea     rcx, [rsp+488h+var_3F8]
0x1800436a3  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x1800436a8  lea     rax, [rsp+488h+var_3F8]
0x1800436b0  cmp     qword ptr [rsp+488h+var_3E8+8], 0Fh
0x1800436b9  cmova   rax, [rsp+488h+var_3F8]
0x1800436c2  mov     [rsp+488h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800436cb  mov     [rsp+488h+lpDefaultChar], 0; lpDefaultChar
0x1800436d4  mov     [rsp+488h+cbMultiByte], ebx; cbMultiByte
0x1800436d8  mov     [rsp+488h+lpMultiByteStr], rax; lpMultiByteStr
0x1800436dd  mov     r9d, r14d; cchWideChar
0x1800436e0  mov     r8, [rsp+488h+lpWideCharStr]; lpWideCharStr
0x1800436e5  xor     edx, edx; dwFlags
0x1800436e7  mov     ecx, 0FDE9h; CodePage
0x1800436ec  call    cs:__imp_WideCharToMultiByte
0x1800436f2  test    dil, dil
0x1800436f5  jns     loc_180043A04
0x1800436fb  lea     rcx, [rsp+488h+var_398]
0x180043703  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180043708  nop
0x180043709  mov     dword ptr [rsp+488h+Src], 656C6966h
0x180043714  mov     word ptr [rsp+488h+Src+4], 3Ah ; ':'
0x18004371e  xor     ecx, ecx
0x180043720  movdqa  xmm0, cs:__xmm@626174756d6d69266f723d65646f6d3f
0x180043728  movdqu  [rsp+488h+var_3B8], xmm0
0x180043731  mov     dword ptr [rsp+488h+var_3A8], 313D656Ch
0x18004373c  mov     [rsp+488h+var_3A8+4], cl
0x180043743  cmp     ebx, 2
0x180043746  jle     short loc_18004376B
0x180043748  lea     rax, [rsp+488h+var_3F8]
0x180043750  cmp     qword ptr [rsp+488h+var_3E8+8], 0Fh
0x180043759  cmova   rax, [rsp+488h+var_3F8]
0x180043762  cmp     byte ptr [rax+1], 3Ah ; ':'
0x180043766  mov     r12b, 1
0x180043769  jz      short loc_18004376E
0x18004376b  mov     r12b, cl
0x18004376e  movzx   eax, r12b
0x180043772  lea     rdx, [rsp+488h+Src]
0x18004377a  mov     rdi, r14
0x18004377d  inc     rdi
0x180043780  cmp     [rdx+rdi], cl
0x180043783  jnz     short loc_18004377D
0x180043785  lea     rdx, [rsp+488h+var_3B8]
0x18004378d  inc     r14
0x180043790  cmp     [rdx+r14], cl
0x180043794  jnz     short loc_18004378D
0x180043796  lea     rdx, [r14+rdi]
0x18004379a  add     rdx, rax
0x18004379d  add     rdx, rbx
0x1800437a0  lea     rcx, [rsp+488h+var_398]
0x1800437a8  call    ?reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::reserve(unsigned __int64)
0x1800437ad  mov     rcx, qword ptr [rsp+488h+var_388]
0x1800437b5  mov     rax, qword ptr [rsp+488h+var_388+8]
0x1800437bd  sub     rax, rcx
0x1800437c0  cmp     rdi, rax
0x1800437c3  ja      short loc_180043807
0x1800437c5  lea     rax, [rcx+rdi]
0x1800437c9  mov     qword ptr [rsp+488h+var_388], rax
0x1800437d1  lea     rbx, [rsp+488h+var_398]
0x1800437d9  cmp     qword ptr [rsp+488h+var_388+8], 0Fh
0x1800437e2  cmova   rbx, qword ptr [rsp+488h+var_398]
0x1800437eb  add     rbx, rcx
0x1800437ee  mov     r8, rdi; Size
0x1800437f1  lea     rdx, [rsp+488h+Src]; Src
0x1800437f9  mov     rcx, rbx; void *
0x1800437fc  call    memcpy_0
0x180043801  mov     byte ptr [rbx+rdi], 0
0x180043805  jmp     short loc_180043824
0x180043807  mov     [rsp+488h+lpMultiByteStr], rdi; Size
0x18004380c  lea     r9, [rsp+488h+Src]
0x180043814  mov     rdx, rdi
0x180043817  lea     rcx, [rsp+488h+var_398]; Src
0x18004381f  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180043824  mov     edi, 2Fh ; '/'
0x180043829  test    r12b, r12b
0x18004382c  jz      short loc_18004387C
0x18004382e  mov     rcx, qword ptr [rsp+488h+var_388]
0x180043836  cmp     rcx, qword ptr [rsp+488h+var_388+8]
0x18004383e  jnb     short loc_18004386C
0x180043840  lea     rax, [rcx+1]
0x180043844  mov     qword ptr [rsp+488h+var_388], rax
0x18004384c  lea     rax, [rsp+488h+var_398]
0x180043854  cmp     qword ptr [rsp+488h+var_388+8], 0Fh
0x18004385d  cmova   rax, qword ptr [rsp+488h+var_398]
0x180043866  mov     [rax+rcx], di
0x18004386a  jmp     short loc_18004387C
0x18004386c  mov     r9b, dil
0x18004386f  lea     rcx, [rsp+488h+var_398]
0x180043877  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18004387c  cmp     qword ptr [rsp+488h+var_3E8+8], 0Fh
0x180043885  jbe     short loc_180043894
0x180043887  mov     rcx, [rsp+488h+var_3F8]
0x18004388f  mov     rdx, rcx
0x180043892  jmp     short loc_1800438A4
0x180043894  lea     rcx, [rsp+488h+var_3F8]
0x18004389c  lea     rdx, [rsp+488h+var_3F8]
0x1800438a4  mov     rbx, rcx
0x1800438a7  mov     r15, qword ptr [rsp+488h+var_3E8]
0x1800438af  add     r15, rdx
0x1800438b2  cmp     rcx, r15
0x1800438b5  jz      short loc_18004391F
0x1800438b7  movzx   eax, byte ptr [rbx]
0x1800438ba  test    al, al
0x1800438bc  jz      short loc_180043917
0x1800438be  mov     r9d, eax
0x1800438c1  cmp     al, 5Ch ; '\'
0x1800438c3  cmovz   r9d, edi
0x1800438c7  mov     rcx, qword ptr [rsp+488h+var_388]
0x1800438cf  cmp     rcx, qword ptr [rsp+488h+var_388+8]
0x1800438d7  jnb     short loc_18004390A
0x1800438d9  lea     rax, [rcx+1]
0x1800438dd  mov     qword ptr [rsp+488h+var_388], rax
0x1800438e5  lea     rax, [rsp+488h+var_398]
0x1800438ed  cmp     qword ptr [rsp+488h+var_388+8], 0Fh
0x1800438f6  cmova   rax, qword ptr [rsp+488h+var_398]
0x1800438ff  mov     [rax+rcx], r9b
0x180043903  mov     byte ptr [rax+rcx+1], 0
0x180043908  jmp     short loc_180043917
0x18004390a  lea     rcx, [rsp+488h+var_398]
0x180043912  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180043917  inc     rbx
0x18004391a  cmp     rbx, r15
0x18004391d  jnz     short loc_1800438B7
0x18004391f  mov     rcx, qword ptr [rsp+488h+var_388]
0x180043927  mov     rax, qword ptr [rsp+488h+var_388+8]
0x18004392f  sub     rax, rcx
0x180043932  cmp     r14, rax
0x180043935  ja      short loc_18004397C
0x180043937  lea     rax, [rcx+r14]
0x18004393b  mov     qword ptr [rsp+488h+var_388], rax
0x180043943  lea     rbx, [rsp+488h+var_398]
0x18004394b  cmp     qword ptr [rsp+488h+var_388+8], 0Fh
0x180043954  cmova   rbx, qword ptr [rsp+488h+var_398]
0x18004395d  add     rbx, rcx
0x180043960  mov     r8, r14; Size
0x180043963  lea     rdx, [rsp+488h+var_3B8]; Src
0x18004396b  mov     rcx, rbx; void *
0x18004396e  call    memcpy_0
0x180043973  xor     r15d, r15d
0x180043976  mov     [r14+rbx], r15b
0x18004397a  jmp     short loc_18004399C
0x18004397c  mov     [rsp+488h+lpMultiByteStr], r14; Size
0x180043981  lea     r9, [rsp+488h+var_3B8]
0x180043989  mov     rdx, r14
0x18004398c  lea     rcx, [rsp+488h+var_398]; Src
0x180043994  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180043999  xor     r15d, r15d
0x18004399c  lea     rcx, [rsp+488h+var_3F8]
0x1800439a4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800439a9  movups  xmm0, [rsp+488h+var_398]
0x1800439b1  movups  xmmword ptr [rsp+488h+var_3F8], xmm0
0x1800439b9  movups  xmm1, [rsp+488h+var_388]
0x1800439c1  movups  [rsp+488h+var_3E8], xmm1
0x1800439c9  mov     qword ptr [rsp+488h+var_388], r15
0x1800439d1  mov     qword ptr [rsp+488h+var_388+8], 0Fh
0x1800439dd  mov     byte ptr [rsp+488h+var_398], r15b
0x1800439e5  mov     ebx, 8041h
0x1800439ea  lea     rcx, [rsp+488h+var_398]
0x1800439f2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800439f7  mov     r12d, [rsp+488h+InBuffer]
0x1800439fc  mov     r14d, 1
0x180043a02  jmp     short loc_180043A2B
0x180043a04  mov     r14d, 1
0x180043a0a  test    r14b, dil
0x180043a0d  jz      short loc_180043A16
0x180043a0f  mov     ebx, 8001h
0x180043a14  jmp     short loc_180043A28
0x180043a16  lea     eax, [r12-3]
0x180043a1b  neg     eax
0x180043a1d  sbb     ebx, ebx
0x180043a1f  and     ebx, 4
0x180043a22  or      ebx, 8002h
0x180043a28  xor     r15d, r15d
0x180043a2b  call    sqlite3_initialize
0x180043a30  mov     ecx, eax; int
0x180043a32  call    ?ThrowSQLiteFailure@@YAXH@Z; ThrowSQLiteFailure(int)
0x180043a37  lea     eax, [r12-1]
0x180043a3c  test    eax, 0FFFFFFFAh
0x180043a41  jnz     short loc_180043A4C
0x180043a43  cmp     r12d, 6
0x180043a47  mov     dil, r14b
0x180043a4a  jnz     short loc_180043A4F
0x180043a4c  mov     dil, r15b
0x180043a4f  cmp     r12d, 4
0x180043a53  jnz     short loc_180043A9B
0x180043a55  xor     edx, edx
0x180043a57  mov     rcx, r13
0x180043a5a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AHPEAU1@@Z$1?sqlite3_close_v2@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUsqlite3@@@Z; wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,int (sqlite3 *),&sqlite3_close_v2(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>::reset(sqlite3 *)
0x180043a5f  lea     rcx, [rsp+488h+var_3F8]
0x180043a67  cmp     qword ptr [rsp+488h+var_3E8+8], 0Fh
0x180043a70  cmova   rcx, [rsp+488h+var_3F8]
0x180043a79  xor     r9d, r9d
0x180043a7c  mov     r8d, ebx
0x180043a7f  mov     rdx, r13
0x180043a82  call    openDatabase
0x180043a87  test    eax, eax
0x180043a89  jz      short loc_180043A9B
0x180043a8b  mov     rdx, [rsp+488h+lpWideCharStr]; unsigned __int16 *
0x180043a90  mov     rcx, rsi; this
0x180043a93  call    ?DeleteCacheFiles@ShaderDiskCacheSQLite@@QEAAJPEBG@Z; ShaderDiskCacheSQLite::DeleteCacheFiles(ushort const *)
  ... truncated ...
```
