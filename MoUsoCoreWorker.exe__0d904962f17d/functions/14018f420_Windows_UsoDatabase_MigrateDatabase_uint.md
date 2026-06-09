# Windows::UsoDatabase::MigrateDatabase(uint)

- ea: `0x14018f420`
- end: `0x14018fb6e`
- name: `?MigrateDatabase@UsoDatabase@Windows@@AEAAXI@Z`
- size: `1870`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14018ede0`

## callees

- `0x140040184`
- `0x140057920`
- `0x140057a20`
- `0x14018d304`
- `0x14018d4b4`
- `0x14018f26c`
- `0x14018f420`

## string_xrefs

- `0x14018f9fc`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fa12`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fa28`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fa3e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fa54`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fa6a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fa80`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fa96`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018faac`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fac2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fad8`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018faee`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fb04`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fb1a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fb30`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fb46`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fb5c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018f461`: `CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            VARIABLE              TEXT NOT NULL COLLATE NOCASE CHECK(VALUE <> ''),            VALUE                 TEXT,            TYPE                  INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME, VARIABLE)            FOREIGN`
- `0x14018f628`: `CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            VARIABLE              TEXT NOT NULL COLLATE NOCASE CHECK(VALUE <> ''),            VALUE                 TEXT,            TYPE                  INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME, VARIABLE)            FOREIGN`
- `0x14018f468`: `ALTER TABLE COMPLETEDUPDATES ADD COLUMN WASREBOOTREQUIRED INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUMN FOROS INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUMN METADATA TEXT;`
- `0x14018f925`: `ALTER TABLE COMPLETEDUPDATES ADD COLUMN WASREBOOTREQUIRED INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUMN FOROS INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUMN METADATA TEXT;`
- `0x14018f5da`: `CREATE TABLE IF NOT EXISTS SIGNALUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE                 INTEGER,            PRIMARY KEY(UNIQUEID));`
- `0x14018f47d`: `CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            PRIMARY KEY(UPDATEID));`
- `0x14018f5ae`: `CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            PRIMARY KEY(UPDATEID));`
- `0x14018f453`: `CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            TIMESTAMP             TEXT,            REALLABEL             INTEGER,            UPDATEMETADATA        TEXT,            PRIMARY KEY(UNIQUEID));`
- `0x14018f45a`: `CREATE TABLE IF NOT EXISTS WSXPACKUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE                 INTEGER,            PRIMARY KEY(UNIQUEID));`
- `0x14018f46f`: `CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,            TREATMENTBUCKET TEXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));`
- `0x14018f6f5`: `CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,            TREATMENTBUCKET TEXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));`
- `0x14018f6d7`: `UPDATE DEFERRALHISTORY SET ISPRIMARYDEFERRAL = NULL;`
- `0x14018f7f9`: `UPDATE DEFERRALHISTORY SET ISPRIMARYDEFERRAL = NULL;`
- `0x14018f9b3`: `CREATE TABLE IF NOT EXISTS UPDATEEVENTHISTORYDIAGNOSTICS (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            STARTTIME             TEXT,            ENDTIME               TEXT,            EVENT                 TEXT,            CATEGORY              TEXT,            TITLE                 TEXT,            RESULT                INTEGER,            REASON               `
- `0x14018f71e`: `CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORYSTATUS (            REBOOTATTEMPTTIMESTAMP TEXT,            DEFERRALREASON         TEXT,            REBOOTREQUIREDTIMEUTC  TEXT,            PRIMARY KEY(REBOOTATTEMPTTIMESTAMP, DEFERRALREASON));`
- `0x14018f88a`: `CREATE TRIGGER IF NOT EXISTS UpdateDeferralEndTimeBeforeInsert BEFORE INSERT ON DEFERRALHISTORY FOR EACH ROW BEGIN     UPDATE DEFERRALHISTORY     SET DEFERRALENDTIME = NEW.DEFERRALSTARTTIME     WHERE PROVIDERID = NEW.PROVIDERID       AND UPDATEID = NEW.UPDATEID       AND ACTION = NEW.ACTION       AND DEFERRALENDTIME IS NULL; END;`
- `0x14018f84d`: `CREATE TABLE IF NOT EXISTS DEFERRALHISTORY (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            UPDATEGROUP           TEXT,            ACTION                TEXT,            ACTIONATTEMPT         INTEGER DEFAULT 1,            DEFERRALREASON        TEXT,            TAG                   TEXT,            DEFERRALSTARTTIME     TEXT,            DEFERRALENDTIME       TEX`
- `0x14018f7af`: `DROP TRIGGER IF EXISTS UpdateDeferralEndTimeBeforeInsert;`
- `0x14018f843`: `DROP TRIGGER IF EXISTS UpdateDeferralEndTimeBeforeInsert;`
- `0x14018f76f`: `ALTER TABLE DEFERRALHISTORY RENAME COLUMN TAG TO ISPRIMARYDEFERRAL;`

## pseudocode

```c
void __fastcall Windows::UsoDatabase::MigrateDatabase(Windows::UsoDatabase *this, unsigned int a2)
{
  unsigned int i; // ebx
  _BYTE *v4; // rax
  const char *v5; // r9
  signed __int64 v6; // rax
  const char **v7; // rdx
  __int64 v8; // rax
  const char *v9; // r9
  __int64 v10; // r11
  __int64 v11; // rax
  __int64 v12; // rax
  const char *v13; // r9
  __int64 v14; // r11
  __int64 v15; // rax
  __int64 v16; // rax
  const char *v17; // r9
  __int64 v18; // r11
  __int64 v19; // rax
  char *v20; // rax
  const char *v21; // r9
  __int64 v22; // r11
  char *v23; // rax
  _QWORD *v24; // rdx
  char *v25; // rcx
  char *traits_1_unsigned_char; // rax
  const char *v27; // r9
  __int64 v28; // r11
  char *v29; // rax
  __int64 v30; // rax
  const char *v31; // r9
  __int64 v32; // r11
  __int64 v33; // rax
  char *v34; // rax
  const char *v35; // r9
  __int64 v36; // r11
  char *v37; // rax
  char *v38; // rax
  const char *v39; // r9
  __int64 v40; // r11
  char *v41; // rax
  char *v42; // rax
  const char *v43; // r9
  __int64 v44; // r11
  char *v45; // rax
  char *v46; // rax
  const char *v47; // r9
  __int64 v48; // r11
  char *v49; // rax
  char *v50; // rax
  const char *v51; // r9
  __int64 v52; // r11
  char *v53; // rax
  char *v54; // rax
  const char *v55; // r9
  __int64 v56; // r11
  char *v57; // rax
  __int64 v58; // rax
  const char *v59; // r9
  __int64 v60; // r11
  __int64 v61; // rax
  __int64 v62; // rax
  const char *v63; // r9
  __int64 v64; // r11
  __int64 v65; // rax
  __int64 traits_2_unsigned_short; // rax
  const char *v67; // r9
  __int64 v68; // r11
  __int64 v69; // rax
  __int64 v70; // rax
  const char *v71; // r9
  __int64 v72; // r11
  __int64 v73; // rax
  const char *v74; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v75; // [rsp+28h] [rbp-D8h]
  _QWORD v76[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v77[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v78[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v79[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v80[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v81[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v82[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v83[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v84[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v85[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v86[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v87[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v88[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v89[2]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  for ( i = a2; i < 0xE; ++i )
  {
    while ( i <= 7 )
    {
      if ( i == 7 )
      {
        traits_1_unsigned_char = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                                           "ALTER TABLE DOWNTIMEHISTORY ADD COLUMN REALLABELSECONDS INTEGER;",
                                           &unk_14041B161,
                                           0);
        if ( traits_1_unsigned_char == (char *)&unk_14041B161
          || (v29 = &traits_1_unsigned_char[-v28], v29 == (char *)-1LL) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v27);
        }
        v81[0] = v28;
        v7 = (const char **)v81;
        v81[1] = v29;
      }
      else
      {
        if ( i <= 2 )
        {
          traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                      L"Version change",
                                      &unk_14041B096,
                                      0);
          if ( traits_2_unsigned_short == v68
            || (v69 = (traits_2_unsigned_short - (__int64)L"Version change") >> 1, v69 == -1) )
          {
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v67);
          }
          v74 = (const char *)L"Version change";
          v75 = v69;
          Windows::UsoDatabase::ResetDatabase(this);
          return;
        }
        switch ( i )
        {
          case 3u:
            v16 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                    "CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT NULL COLLATE "
                    "NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            PRIMARY KEY(UPDATEID));",
                    &unk_14041B69C,
                    0);
            if ( v16 == v18
              || (v19 = v16
                      - (_QWORD)"CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT N"
                                "ULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,        "
                                "    PRIMARY KEY(UPDATEID));",
                  v19 == -1) )
            {
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xC9,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                v17);
            }
            v79[0] = "CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT NULL COLLATE"
                     " NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            PRIMARY KEY(UPDATEID));";
            v79[1] = v19;
            Windows::SqlExec((char *)this + 40, v79);
            v20 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                            "CREATE TABLE IF NOT EXISTS SIGNALUPDATES (            UNIQUEID              TEXT NOT NULL CO"
                            "LLATE NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE "
                            "                INTEGER,            PRIMARY KEY(UNIQUEID));",
                            &unk_14041B5C4,
                            0);
            if ( v20 == (char *)&unk_14041B5C4 || (v23 = &v20[-v22], v23 == (char *)-1LL) )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xC9,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                v21);
            v80[0] = v22;
            v24 = v80;
            v80[1] = v23;
            goto LABEL_22;
          case 4u:
            v12 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                    "CREATE TABLE IF NOT EXISTS WSXPACKUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE N"
                    "OCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE                "
                    " INTEGER,            PRIMARY KEY(UNIQUEID));",
                    &unk_14041B8E5,
                    0);
            if ( v12 == v14
              || (v15 = v12
                      - (_QWORD)"CREATE TABLE IF NOT EXISTS WSXPACKUPDATES (            UNIQUEID              TEXT NOT NU"
                                "LL COLLATE NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,         "
                                "   STATE                 INTEGER,            PRIMARY KEY(UNIQUEID));",
                  v15 == -1) )
            {
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xC9,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                v13);
            }
            v78[0] = "CREATE TABLE IF NOT EXISTS WSXPACKUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE "
                     "NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE              "
                     "   INTEGER,            PRIMARY KEY(UNIQUEID));";
            v7 = (const char **)v78;
            v78[1] = v15;
            break;
          case 5u:
            v8 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                   "CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLATE N"
                   "OCASE CHECK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            TIMESTAMP          "
                   "   TEXT,            REALLABEL             INTEGER,            UPDATEMETADATA        TEXT,            "
                   "PRIMARY KEY(UNIQUEID));",
                   &unk_14041B7E7,
                   0);
            if ( v8 == v10
              || (v11 = v8
                      - (_QWORD)"CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT N"
                                "ULL COLLATE NOCASE CHECK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,     "
                                "       TIMESTAMP             TEXT,            REALLABEL             INTEGER,            "
                                "UPDATEMETADATA        TEXT,            PRIMARY KEY(UNIQUEID));",
                  v11 == -1) )
            {
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xC9,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                v9);
            }
            v77[0] = "CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLATE"
                     " NOCASE CHECK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            TIMESTAMP      "
                     "       TEXT,            REALLABEL             INTEGER,            UPDATEMETADATA        TEXT,      "
                     "      PRIMARY KEY(UNIQUEID));";
            v7 = (const char **)v77;
            v77[1] = v11;
            break;
          default:
            v4 = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                            "ALTER TABLE DOWNTIMEHISTORY ADD COLUMN ESTIMATEDTIMEHIGH INTEGER;",
                            &unk_14041B1B2,
                            0);
            if ( v4 == (_BYTE *)&unk_14041B1B2
              || (v6 = v4 - "ALTER TABLE DOWNTIMEHISTORY ADD COLUMN ESTIMATEDTIMEHIGH INTEGER;", v6 == -1) )
            {
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xC9,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                v5);
            }
            v76[0] = "ALTER TABLE DOWNTIMEHISTORY ADD COLUMN ESTIMATEDTIMEHIGH INTEGER;";
            v7 = (const char **)v76;
            v76[1] = v6;
            break;
        }
      }
LABEL_58:
      Windows::SqlExec((char *)this + 40, v7);
LABEL_59:
      ++i;
    }
    switch ( i )
    {
      case 8u:
        v62 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                "ALTER TABLE COMPLETEDUPDATES ADD COLUMN WASREBOOTREQUIRED INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUM"
                "N FOROS INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUMN METADATA TEXT;",
                &unk_14041B4CF,
                0);
        if ( v62 == v64
          || (v65 = v62
                  - (_QWORD)"ALTER TABLE COMPLETEDUPDATES ADD COLUMN WASREBOOTREQUIRED INTEGER;ALTER TABLE COMPLETEDUPDAT"
                            "ES ADD COLUMN FOROS INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUMN METADATA TEXT;",
              v65 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v63);
        }
        v74 = "ALTER TABLE COMPLETEDUPDATES ADD COLUMN WASREBOOTREQUIRED INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUMN "
              "FOROS INTEGER;ALTER TABLE COMPLETEDUPDATES ADD COLUMN METADATA TEXT;";
        v7 = &v74;
        v75 = v65;
        goto LABEL_58;
      case 9u:
        v58 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                "CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NULL COLLATE NO"
                "CASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATE"
                "ID <> ''),            TIME                  TEXT,            VARIABLE              TEXT NOT NULL COLLATE"
                " NOCASE CHECK(VALUE <> ''),            VALUE                 TEXT,            TYPE                  INTE"
                "GER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME, VARIABLE)            FOREIGN KEY(PROVIDERID, UPD"
                "ATEID, TIME) REFERENCES ACTIONRECORDS(PROVIDERID, UPDATEID, TIME) ON DELETE CASCADE);",
                &unk_14041B41E,
                0);
        if ( v58 == v60
          || (v61 = v58
                  - (_QWORD)"CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NUL"
                            "L COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COL"
                            "LATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            VARIABL"
                            "E              TEXT NOT NULL COLLATE NOCASE CHECK(VALUE <> ''),            VALUE            "
                            "     TEXT,            TYPE                  INTEGER,            PRIMARY KEY(PROVIDERID, UPDA"
                            "TEID, TIME, VARIABLE)            FOREIGN KEY(PROVIDERID, UPDATEID, TIME) REFERENCES ACTIONRE"
                            "CORDS(PROVIDERID, UPDATEID, TIME) ON DELETE CASCADE);",
              v61 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v59);
        }
        v89[0] = "CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NULL COLLATE N"
                 "OCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDA"
                 "TEID <> ''),            TIME                  TEXT,            VARIABLE              TEXT NOT NULL COLL"
                 "ATE NOCASE CHECK(VALUE <> ''),            VALUE                 TEXT,            TYPE                  "
                 "INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME, VARIABLE)            FOREIGN KEY(PROVIDERID"
                 ", UPDATEID, TIME) REFERENCES ACTIONRECORDS(PROVIDERID, UPDATEID, TIME) ON DELETE CASCADE);";
        v7 = (const char **)v89;
        v89[1] = v61;
        goto LABEL_58;
      case 0xAu:
        v50 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                        "CREATE TABLE IF NOT EXISTS DEFERRALHISTORY (            PROVIDERID            TEXT NOT NULL COLL"
                        "ATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCAS"
                        "E CHECK(UPDATEID <> ''),            UPDATEGROUP           TEXT,            ACTION               "
                        " TEXT,            ACTIONATTEMPT         INTEGER DEFAULT 1,            DEFERRALREASON        TEXT"
                        ",            TAG                   TEXT,            DEFERRALSTARTTIME     TEXT,            DEFER"
                        "RALENDTIME       TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID, ACTION, ACTIONATTEMPT, DEFER"
                        "RALREASON, DEFERRALSTARTTIME));",
                        "DROP TRIGGER IF EXISTS UpdateDeferralEndTimeBeforeInsert;",
                        0);
        if ( v50 == "DROP TRIGGER IF EXISTS UpdateDeferralEndTimeBeforeInsert;"
          || (v53 = &v50[-v52], v53 == (char *)-1LL) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v51);
        }
        v87[0] = v52;
        v87[1] = v53;
        Windows::SqlExec((char *)this + 40, v87);
        v54 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                        "CREATE TRIGGER IF NOT EXISTS UpdateDeferralEndTimeBeforeInsert BEFORE INSERT ON DEFERRALHISTORY "
                        "FOR EACH ROW BEGIN     UPDATE DEFERRALHISTORY     SET DEFERRALENDTIME = NEW.DEFERRALSTARTTIME   "
                        "  WHERE PROVIDERID = NEW.PROVIDERID       AND UPDATEID = NEW.UPDATEID       AND ACTION = NEW.ACT"
                        "ION       AND DEFERRALENDTIME IS NULL; END;",
                        &unk_14041BF3C,
                        0);
        if ( v54 == (char *)&unk_14041BF3C || (v57 = &v54[-v56], v57 == (char *)-1LL) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v55);
        v88[0] = v56;
        v24 = v88;
        v88[1] = v57;
LABEL_22:
        v25 = (char *)this + 40;
LABEL_23:
        Windows::SqlExec(v25, v24);
        goto LABEL_59;
      case 0xBu:
        v38 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                        "ALTER TABLE DEFERRALHISTORY RENAME COLUMN TAG TO ISPRIMARYDEFERRAL;",
                        &unk_14041C224,
                        0);
        if ( v38 == (char *)&unk_14041C224 || (v41 = &v38[-v40], v41 == (char *)-1LL) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v39);
        v84[0] = v40;
        v84[1] = v41;
        Windows::SqlExec((char *)this + 40, v84);
        v42 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                        "DROP TRIGGER IF EXISTS UpdateDeferralEndTimeBeforeInsert;",
                        &unk_14041C1DA,
                        0);
        if ( v42 == (char *)&unk_14041C1DA || (v45 = &v42[-v44], v45 == (char *)-1LL) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v43);
        v85[0] = v44;
        v85[1] = v45;
        Windows::SqlExec((char *)this + 40, v85);
        v46 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                        "UPDATE DEFERRALHISTORY SET ISPRIMARYDEFERRAL = NULL;",
                        &unk_14041B9D5,
                        0);
        if ( v46 == (char *)&unk_14041B9D5 || (v49 = &v46[-v48], v49 == (char *)-1LL) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v47);
        v86[0] = v48;
        v24 = v86;
        v86[1] = v49;
        v25 = (char *)this + 40;
        goto LABEL_23;
      case 0xCu:
        v30 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                "CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,            TREATMENT"
                "BUCKET TEXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));",
                "UPDATE DEFERRALHISTORY SET ISPRIMARYDEFERRAL = NULL;",
                0);
        if ( v30 == v32
          || (v33 = v30
                  - (_QWORD)"CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,         "
                            "   TREATMENTBUCKET TEXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));",
              v33 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v31);
        }
        v82[0] = "CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,            TREATMEN"
                 "TBUCKET TEXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));";
        v82[1] = v33;
        Windows::SqlExec((char *)this + 40, v82);
        v34 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                        "CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORYSTATUS (            REBOOTATTEMPTTIMESTAMP TEXT,"
                        "            DEFERRALREASON         TEXT,            REBOOTREQUIREDTIMEUTC  TEXT,            PRIM"
                        "ARY KEY(REBOOTATTEMPTTIMESTAMP, DEFERRALREASON));",
                        &unk_14041BDE2,
                        0);
        if ( v34 == (char *)&unk_14041BDE2 || (v37 = &v34[-v36], v37 == (char *)-1LL) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v35);
        v83[0] = v36;
        v24 = v83;
        v83[1] = v37;
        goto LABEL_22;
      case 0xDu:
        v70 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                "CREATE TABLE IF NOT EXISTS UPDATEEVENTHISTORYDIAGNOSTICS (            PROVIDERID            TEXT NOT NUL"
                "L COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE "
                "CHECK(UPDATEID <> ''),            STARTTIME             TEXT,            ENDTIME               TEXT,    "
                "        EVENT                 TEXT,            CATEGORY              TEXT,            TITLE             "
                "    TEXT,            RESULT                INTEGER,            REASON                TEXT,            AP"
                "PROVALS             TEXT,            ISSEEKER              INTEGER,            FLIGHTID              TEX"
                "T,            UPDATEMETADATA        TEXT,            OTHER                 TEXT,            PRIMARY KEY("
                "PROVIDERID, UPDATEID, STARTTIME, EVENT));",
                &unk_14041BCE2,
                0);
        if ( v70 == v72
          || (v73 = v70
                  - (_QWORD)"CREATE TABLE IF NOT EXISTS UPDATEEVENTHISTORYDIAGNOSTICS (            PROVIDERID            "
                            "TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT "
                            "NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            STARTTIME             TEXT,       "
                            "     ENDTIME               TEXT,            EVENT                 TEXT,            CATEGORY "
                            "             TEXT,            TITLE                 TEXT,            RESULT                I"
                            "NTEGER,            REASON                TEXT,            APPROVALS             TEXT,       "
                            "     ISSEEKER              INTEGER,            FLIGHTID              TEXT,            UPDATE"
                            "METADATA        TEXT,            OTHER                 TEXT,            PRIMARY KEY(PROVIDER"
                            "ID, UPDATEID, STARTTIME, EVENT));",
              v73 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v71);
        }
        v74 = "CREATE TABLE IF NOT EXISTS UPDATEEVENTHISTORYDIAGNOSTICS (            PROVIDERID            TEXT NOT NULL "
              "COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHEC"
              "K(UPDATEID <> ''),            STARTTIME             TEXT,            ENDTIME               TEXT,          "
              "  EVENT                 TEXT,            CATEGORY              TEXT,            TITLE                 TEXT"
              ",            RESULT                INTEGER,            REASON                TEXT,            APPROVALS   "
              "          TEXT,            ISSEEKER              INTEGER,            FLIGHTID              TEXT,          "
              "  UPDATEMETADATA        TEXT,            OTHER                 TEXT,            PRIMARY KEY(PROVIDERID, UP"
              "DATEID, STARTTIME, EVENT));";
        v75 = v73;
        Windows::SqlExec((char *)this + 40, &v74);
        goto LABEL_34;
    }
  }
LABEL_34:
  Windows::UsoDatabase::InsertVersion(this);
}

```

## disassembly

```asm
0x14018f420  mov     [rsp-8+arg_8], rbx
0x14018f425  mov     [rsp-8+arg_10], rsi
0x14018f42a  push    rbp
0x14018f42b  push    rdi
0x14018f42c  push    r12
0x14018f42e  push    r13
0x14018f430  push    r15
0x14018f432  lea     rbp, [rsp-10h]
0x14018f437  sub     rsp, 110h
0x14018f43e  mov     ebx, edx
0x14018f440  mov     rdi, rcx
0x14018f443  cmp     edx, 0Eh
0x14018f446  jnb     loc_14018F6B3
0x14018f44c  lea     r15, aAlterTableDown_0; "ALTER TABLE DOWNTIMEHISTORY ADD COLUMN "...
0x14018f453  lea     r12, aCreateTableIfN_9; "CREATE TABLE IF NOT EXISTS DOWNTIMEHIST"...
0x14018f45a  lea     r13, aCreateTableIfN_8; "CREATE TABLE IF NOT EXISTS WSXPACKUPDAT"...
0x14018f461  lea     rsi, aCreateTableIfN_2; "CREATE TABLE IF NOT EXISTS ACTIONRECORD"...
0x14018f468  lea     rcx, aAlterTableComp; "ALTER TABLE COMPLETEDUPDATES ADD COLUMN"...
0x14018f46f  lea     r10, aCreateTableIfN_0; "CREATE TABLE IF NOT EXISTS REBOOTDEFERR"...
0x14018f476  lea     r11, aAlterTableDown; "ALTER TABLE DOWNTIMEHISTORY ADD COLUMN "...
0x14018f47d  lea     r9, aCreateTableIfN_6; "CREATE TABLE IF NOT EXISTS APPROVEDUPDA"...
0x14018f484  lea     rdx, unk_14041B1B2
0x14018f48b  cmp     ebx, 7
0x14018f48e  ja      loc_14018F674
0x14018f494  jz      loc_14018F634
0x14018f49a  mov     eax, ebx
0x14018f49c  test    ebx, ebx
0x14018f49e  jz      loc_14018F958
0x14018f4a4  sub     eax, 1
0x14018f4a7  jz      loc_14018F958
0x14018f4ad  sub     eax, 1
0x14018f4b0  jz      loc_14018F958
0x14018f4b6  sub     eax, 1
0x14018f4b9  jz      loc_14018F590
0x14018f4bf  sub     eax, 1
0x14018f4c2  jz      loc_14018F551
0x14018f4c8  sub     eax, 1
0x14018f4cb  jz      short loc_14018F512
0x14018f4cd  cmp     eax, 1
0x14018f4d0  jnz     loc_14018F6A8
0x14018f4d6  xor     r8d, r8d
0x14018f4d9  mov     rcx, r15
0x14018f4dc  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f4e1  lea     rcx, unk_14041B1B2
0x14018f4e8  cmp     rax, rcx
0x14018f4eb  jz      loc_14018FA24
0x14018f4f1  sub     rax, r15
0x14018f4f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f4f8  jz      loc_14018FA24
0x14018f4fe  mov     [rsp+130h+var_100], r15
0x14018f503  lea     rdx, [rsp+130h+var_100]
0x14018f508  mov     [rsp+130h+var_F8], rax
0x14018f50d  jmp     loc_14018F948
0x14018f512  lea     r11, unk_14041B7E7
0x14018f519  xor     r8d, r8d
0x14018f51c  mov     rdx, r11
0x14018f51f  mov     rcx, r12
0x14018f522  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f527  cmp     rax, r11
0x14018f52a  jz      loc_14018FA3A
0x14018f530  sub     rax, r12
0x14018f533  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f537  jz      loc_14018FA3A
0x14018f53d  mov     [rsp+130h+var_F0], r12
0x14018f542  lea     rdx, [rsp+130h+var_F0]
0x14018f547  mov     [rsp+130h+var_E8], rax
0x14018f54c  jmp     loc_14018F948
0x14018f551  lea     r11, unk_14041B8E5
0x14018f558  xor     r8d, r8d
0x14018f55b  mov     rdx, r11
0x14018f55e  mov     rcx, r13
0x14018f561  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f566  cmp     rax, r11
0x14018f569  jz      loc_14018FA50
0x14018f56f  sub     rax, r13
0x14018f572  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f576  jz      loc_14018FA50
0x14018f57c  mov     [rsp+130h+var_E0], r13
0x14018f581  lea     rdx, [rsp+130h+var_E0]
0x14018f586  mov     [rsp+130h+var_D8], rax
0x14018f58b  jmp     loc_14018F948
0x14018f590  lea     r11, unk_14041B69C
0x14018f597  xor     r8d, r8d
0x14018f59a  mov     rdx, r11
0x14018f59d  mov     rcx, r9
0x14018f5a0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f5a5  cmp     rax, r11
0x14018f5a8  jz      loc_14018FA7C
0x14018f5ae  lea     rcx, aCreateTableIfN_6; "CREATE TABLE IF NOT EXISTS APPROVEDUPDA"...
0x14018f5b5  sub     rax, rcx
0x14018f5b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f5bc  jz      loc_14018FA7C
0x14018f5c2  mov     [rsp+130h+var_D0], rcx
0x14018f5c7  lea     rdx, [rsp+130h+var_D0]
0x14018f5cc  lea     rcx, [rdi+28h]
0x14018f5d0  mov     [rsp+130h+var_C8], rax
0x14018f5d5  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018f5da  lea     r11, aCreateTableIfN_15; "CREATE TABLE IF NOT EXISTS SIGNALUPDATE"...
0x14018f5e1  xor     r8d, r8d
0x14018f5e4  mov     rcx, r11
0x14018f5e7  lea     rdx, unk_14041B5C4
0x14018f5ee  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f5f3  lea     rcx, unk_14041B5C4
0x14018f5fa  cmp     rax, rcx
0x14018f5fd  jz      loc_14018FA66
0x14018f603  sub     rax, r11
0x14018f606  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f60a  jz      loc_14018FA66
0x14018f610  mov     [rsp+130h+var_C0], r11
0x14018f615  lea     rdx, [rsp+130h+var_C0]
0x14018f61a  mov     [rsp+130h+var_B8], rax
0x14018f61f  lea     rcx, [rdi+28h]
0x14018f623  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018f628  lea     rsi, aCreateTableIfN_2; "CREATE TABLE IF NOT EXISTS ACTIONRECORD"...
0x14018f62f  jmp     loc_14018F951
0x14018f634  xor     r8d, r8d
0x14018f637  lea     rdx, unk_14041B161
0x14018f63e  mov     rcx, r11
0x14018f641  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f646  lea     rcx, unk_14041B161
0x14018f64d  cmp     rax, rcx
0x14018f650  jz      loc_14018FAA8
0x14018f656  sub     rax, r11
0x14018f659  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f65d  jz      loc_14018FAA8
0x14018f663  mov     [rbp+30h+var_B0], r11
0x14018f667  lea     rdx, [rbp+30h+var_B0]
0x14018f66b  mov     [rbp+30h+var_A8], rax
0x14018f66f  jmp     loc_14018F948
0x14018f674  mov     eax, ebx
0x14018f676  sub     eax, 8
0x14018f679  jz      loc_14018F90A
0x14018f67f  sub     eax, 1
0x14018f682  jz      loc_14018F8D1
0x14018f688  sub     eax, 1
0x14018f68b  jz      loc_14018F843
0x14018f691  sub     eax, 1
0x14018f694  jz      loc_14018F765
0x14018f69a  sub     eax, 1
0x14018f69d  jz      short loc_14018F6D7
0x14018f69f  cmp     eax, 1
0x14018f6a2  jz      loc_14018F9A9
0x14018f6a8  inc     ebx
0x14018f6aa  cmp     ebx, 0Eh
0x14018f6ad  jb      loc_14018F48B
0x14018f6b3  mov     rcx, rdi; this
0x14018f6b6  call    ?InsertVersion@UsoDatabase@Windows@@AEAAXXZ; Windows::UsoDatabase::InsertVersion(void)
0x14018f6bb  lea     r11, [rsp+130h+var_20]
0x14018f6c3  mov     rbx, [r11+38h]
0x14018f6c7  mov     rsi, [r11+40h]
0x14018f6cb  mov     rsp, r11
0x14018f6ce  pop     r15
0x14018f6d0  pop     r13
0x14018f6d2  pop     r12
0x14018f6d4  pop     rdi
0x14018f6d5  pop     rbp
0x14018f6d6  retn
0x14018f6d7  lea     r11, aUpdateDeferral_3; "UPDATE DEFERRALHISTORY SET ISPRIMARYDEF"...
0x14018f6de  xor     r8d, r8d
0x14018f6e1  mov     rdx, r11
0x14018f6e4  mov     rcx, r10
0x14018f6e7  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f6ec  cmp     rax, r11
0x14018f6ef  jz      loc_14018FAEA
0x14018f6f5  lea     rcx, aCreateTableIfN_0; "CREATE TABLE IF NOT EXISTS REBOOTDEFERR"...
0x14018f6fc  sub     rax, rcx
0x14018f6ff  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f703  jz      loc_14018FAEA
0x14018f709  mov     [rbp+30h+var_A0], rcx
0x14018f70d  lea     rdx, [rbp+30h+var_A0]
0x14018f711  lea     rcx, [rdi+28h]
0x14018f715  mov     [rbp+30h+var_98], rax
0x14018f719  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018f71e  lea     r11, aCreateTableIfN_7; "CREATE TABLE IF NOT EXISTS REBOOTDEFERR"...
0x14018f725  xor     r8d, r8d
0x14018f728  mov     rcx, r11
0x14018f72b  lea     rdx, unk_14041BDE2
0x14018f732  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f737  lea     rcx, unk_14041BDE2
0x14018f73e  cmp     rax, rcx
0x14018f741  jz      loc_14018FAD4
0x14018f747  sub     rax, r11
0x14018f74a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f74e  jz      loc_14018FAD4
0x14018f754  mov     [rbp+30h+var_90], r11
0x14018f758  lea     rdx, [rbp+30h+var_90]
0x14018f75c  mov     [rbp+30h+var_88], rax
0x14018f760  jmp     loc_14018F61F
0x14018f765  lea     rsi, unk_14041C224
0x14018f76c  xor     r8d, r8d
0x14018f76f  lea     r11, aAlterTableDefe; "ALTER TABLE DEFERRALHISTORY RENAME COLU"...
0x14018f776  mov     rdx, rsi
0x14018f779  mov     rcx, r11
0x14018f77c  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f781  cmp     rax, rsi
0x14018f784  jz      loc_14018FB2C
0x14018f78a  sub     rax, r11
0x14018f78d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f791  jz      loc_14018FB2C
0x14018f797  lea     rsi, [rdi+28h]
0x14018f79b  mov     [rbp+30h+var_80], r11
0x14018f79f  mov     rcx, rsi
0x14018f7a2  mov     [rbp+30h+var_78], rax
0x14018f7a6  lea     rdx, [rbp+30h+var_80]
0x14018f7aa  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018f7af  lea     r11, aDropTriggerIfE; "DROP TRIGGER IF EXISTS UpdateDeferralEn"...
0x14018f7b6  xor     r8d, r8d
0x14018f7b9  mov     rcx, r11
0x14018f7bc  lea     rdx, unk_14041C1DA
0x14018f7c3  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f7c8  lea     rcx, unk_14041C1DA
0x14018f7cf  cmp     rax, rcx
0x14018f7d2  jz      loc_14018FB16
0x14018f7d8  sub     rax, r11
0x14018f7db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f7df  jz      loc_14018FB16
0x14018f7e5  lea     rdx, [rbp+30h+var_70]
0x14018f7e9  mov     [rbp+30h+var_70], r11
0x14018f7ed  mov     rcx, rsi
0x14018f7f0  mov     [rbp+30h+var_68], rax
0x14018f7f4  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018f7f9  lea     r11, aUpdateDeferral_3; "UPDATE DEFERRALHISTORY SET ISPRIMARYDEF"...
0x14018f800  xor     r8d, r8d
0x14018f803  mov     rcx, r11
0x14018f806  lea     rdx, unk_14041B9D5
0x14018f80d  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f812  lea     rcx, unk_14041B9D5
0x14018f819  cmp     rax, rcx
0x14018f81c  jz      loc_14018FB00
0x14018f822  sub     rax, r11
0x14018f825  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f829  jz      loc_14018FB00
0x14018f82f  mov     [rbp+30h+var_60], r11
0x14018f833  lea     rdx, [rbp+30h+var_60]
0x14018f837  mov     [rbp+30h+var_58], rax
0x14018f83b  mov     rcx, rsi
0x14018f83e  jmp     loc_14018F623
0x14018f843  lea     rsi, aDropTriggerIfE; "DROP TRIGGER IF EXISTS UpdateDeferralEn"...
0x14018f84a  xor     r8d, r8d
0x14018f84d  lea     r11, aCreateTableIfN_3; "CREATE TABLE IF NOT EXISTS DEFERRALHIST"...
0x14018f854  mov     rdx, rsi
0x14018f857  mov     rcx, r11
0x14018f85a  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f85f  cmp     rax, rsi
0x14018f862  jz      loc_14018FB58
0x14018f868  sub     rax, r11
0x14018f86b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f86f  jz      loc_14018FB58
0x14018f875  lea     rdx, [rbp+30h+var_50]
0x14018f879  mov     [rbp+30h+var_50], r11
0x14018f87d  lea     rcx, [rdi+28h]
0x14018f881  mov     [rbp+30h+var_48], rax
0x14018f885  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018f88a  lea     r11, aCreateTriggerI; "CREATE TRIGGER IF NOT EXISTS UpdateDefe"...
0x14018f891  xor     r8d, r8d
0x14018f894  mov     rcx, r11
0x14018f897  lea     rdx, unk_14041BF3C
0x14018f89e  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f8a3  lea     rcx, unk_14041BF3C
0x14018f8aa  cmp     rax, rcx
0x14018f8ad  jz      loc_14018FB42
0x14018f8b3  sub     rax, r11
0x14018f8b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f8ba  jz      loc_14018FB42
0x14018f8c0  mov     [rbp+30h+var_40], r11
0x14018f8c4  lea     rdx, [rbp+30h+var_40]
0x14018f8c8  mov     [rbp+30h+var_38], rax
0x14018f8cc  jmp     loc_14018F61F
0x14018f8d1  lea     r11, unk_14041B41E
0x14018f8d8  xor     r8d, r8d
0x14018f8db  mov     rdx, r11
0x14018f8de  mov     rcx, rsi
0x14018f8e1  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f8e6  cmp     rax, r11
0x14018f8e9  jz      loc_14018F9F8
0x14018f8ef  sub     rax, rsi
0x14018f8f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f8f6  jz      loc_14018F9F8
0x14018f8fc  mov     [rbp+30h+var_30], rsi
0x14018f900  lea     rdx, [rbp+30h+var_30]
0x14018f904  mov     [rbp+30h+var_28], rax
0x14018f908  jmp     short loc_14018F948
0x14018f90a  lea     r11, unk_14041B4CF
0x14018f911  xor     r8d, r8d
0x14018f914  mov     rdx, r11
0x14018f917  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018f91c  cmp     rax, r11
0x14018f91f  jz      loc_14018FA0E
0x14018f925  lea     rcx, aAlterTableComp; "ALTER TABLE COMPLETEDUPDATES ADD COLUMN"...
0x14018f92c  sub     rax, rcx
0x14018f92f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018f933  jz      loc_14018FA0E
0x14018f939  mov     [rsp+130h+var_110], rcx
0x14018f93e  lea     rdx, [rsp+130h+var_110]
0x14018f943  mov     [rsp+130h+var_108], rax
0x14018f948  lea     rcx, [rdi+28h]
0x14018f94c  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018f951  inc     ebx
0x14018f953  jmp     loc_14018F468
0x14018f958  lea     r11, unk_14041B096
  ... truncated ...
```
