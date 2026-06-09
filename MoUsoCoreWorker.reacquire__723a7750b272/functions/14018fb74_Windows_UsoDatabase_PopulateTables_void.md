# Windows::UsoDatabase::PopulateTables(void)

- ea: `0x14018fb74`
- end: `0x1401900f9`
- name: `?PopulateTables@UsoDatabase@Windows@@AEAAXXZ`
- size: `1413`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14018d3d8`
- `0x14018d4b4`
- `0x1401901cc`

## callees

- `0x140040184`
- `0x140057920`
- `0x14018d304`
- `0x14018fb74`

## string_xrefs

- `0x14018ffb3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018ffc9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018ffdf`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fff5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14019000b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140190021`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140190037`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14019004d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140190063`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140190079`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14019008f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1401900a5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1401900bb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1401900d1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1401900e7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14018fb90`: `CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            VARIABLE              TEXT NOT NULL COLLATE NOCASE CHECK(VALUE <> ''),            VALUE                 TEXT,            TYPE                  INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME, VARIABLE)            FOREIGN`
- `0x14018fdc7`: `CREATE TABLE IF NOT EXISTS SIGNALUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE                 INTEGER,            PRIMARY KEY(UNIQUEID));`
- `0x14018fd81`: `CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            PRIMARY KEY(UPDATEID));`
- `0x14018fe0d`: `CREATE TABLE IF NOT EXISTS WSXPACKUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE                 INTEGER,            PRIMARY KEY(UNIQUEID));`
- `0x14018fedf`: `CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,            TREATMENTBUCKET TEXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));`
- `0x14018fed5`: `UPDATE DEFERRALHISTORY SET ISPRIMARYDEFERRAL = NULL;`
- `0x14018ff6b`: `CREATE TABLE IF NOT EXISTS UPDATEEVENTHISTORYDIAGNOSTICS (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            STARTTIME             TEXT,            ENDTIME               TEXT,            EVENT                 TEXT,            CATEGORY              TEXT,            TITLE                 TEXT,            RESULT                INTEGER,            REASON               `
- `0x14018ff25`: `CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORYSTATUS (            REBOOTATTEMPTTIMESTAMP TEXT,            DEFERRALREASON         TEXT,            REBOOTREQUIREDTIMEUTC  TEXT,            PRIMARY KEY(REBOOTATTEMPTTIMESTAMP, DEFERRALREASON));`
- `0x14018fd3b`: `CREATE TABLE IF NOT EXISTS PROVIDERSPROP (            PROVIDERID TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            VARIABLE   TEXT NOT NULL COLLATE NOCASE CHECK(VARIABLE <> ''),            VALUE      TEXT,            TYPE       INTEGER,            PRIMARY KEY(PROVIDERID, VARIABLE));`
- `0x14018fcf5`: `CREATE TABLE IF NOT EXISTS ACTIONRECORDS (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            ACTION                TEXT,            ACTIONCLASS           TEXT,            RESULT                INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME)            FOREIGN KEY(PROVIDERID, UPDATEID) REFERENCES UPDATES(PROVIDERID,`
- `0x14018fe99`: `CREATE TABLE IF NOT EXISTS DEFERRALHISTORY (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            UPDATEGROUP           TEXT,            ACTION                TEXT,            ACTIONATTEMPT         INTEGER DEFAULT 1,            DEFERRALREASON        TEXT,            ISPRIMARYDEFERRAL     TEXT,            DEFERRALSTARTTIME     TEXT,            DEFERRALENDTIME       TEX`
- `0x14018fe53`: `CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            ESTIMATEDTIMEHIGH     INTEGER,            TIMESTAMP             TEXT,            REALLABEL             INTEGER,            REALLABELSECONDS      INTEGER,            UPDATEMETADATA        TEXT,            PRIMARY KEY(UNIQUEID));`
- `0x14018fe8f`: `CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            ESTIMATEDTIMEHIGH     INTEGER,            TIMESTAMP             TEXT,            REALLABEL             INTEGER,            REALLABELSECONDS      INTEGER,            UPDATEMETADATA        TEXT,            PRIMARY KEY(UNIQUEID));`
- `0x14018fc23`: `CREATE TABLE IF NOT EXISTS VARIABLES (            KEY        TEXT NOT NULL COLLATE NOCASE CHECK(KEY <> ''),            VALUE      TEXT,            TYPE       INTEGER,            PRIMARY KEY(KEY));`
- `0x14018fbdd`: `CREATE TABLE IF NOT EXISTS COMPLETEDUPDATES (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            TITLE                 TEXT,            DESCRIPTION           TEXT,            MOREINFOURL           TEXT,            HISTORYCATEGORY       TEXT,            UNINSTALL             INTEGER,            WASREBOOTREQUIRED     INTEGER,    `
- `0x14018fcaf`: `CREATE TABLE IF NOT EXISTS UPDATESPROP (            PROVIDERID TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID   TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            VARIABLE   TEXT NOT NULL COLLATE NOCASE CHECK(VARIABLE <> ''),            VALUE      TEXT,            TYPE       INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, VARIABLE)            FOREIGN KEY(PROVIDERID, UPDATEID) REFERENCES UPDATES(PROVIDERID, UPDATEID) ON DELETE CASCADE);`
- `0x14018fc69`: `CREATE TABLE IF NOT EXISTS UPDATES (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            SERIALIZEDUPDATE      BLOB,            PRIMARY KEY(PROVIDERID, UPDATEID));`

## pseudocode

```c
void __fastcall Windows::UsoDatabase::PopulateTables(Windows::UsoDatabase *this)
{
  __int64 traits_1_unsigned_char; // rax
  const char *v3; // r9
  __int64 v4; // r11
  __int64 v5; // rax
  char *v6; // rbx
  __int64 v7; // rax
  const char *v8; // r9
  __int64 v9; // r11
  __int64 v10; // rax
  __int64 v11; // rax
  const char *v12; // r9
  __int64 v13; // r11
  __int64 v14; // rax
  __int64 v15; // rax
  const char *v16; // r9
  __int64 v17; // r11
  __int64 v18; // rax
  __int64 v19; // rax
  const char *v20; // r9
  __int64 v21; // r11
  __int64 v22; // rax
  __int64 v23; // rax
  const char *v24; // r9
  __int64 v25; // r11
  __int64 v26; // rax
  __int64 v27; // rax
  const char *v28; // r9
  __int64 v29; // r11
  __int64 v30; // rax
  __int64 v31; // rax
  const char *v32; // r9
  __int64 v33; // r11
  __int64 v34; // rax
  __int64 v35; // rax
  const char *v36; // r9
  __int64 v37; // r11
  __int64 v38; // rax
  __int64 v39; // rax
  const char *v40; // r9
  __int64 v41; // r11
  __int64 v42; // rax
  __int64 v43; // rax
  const char *v44; // r9
  __int64 v45; // r11
  __int64 v46; // rax
  __int64 v47; // rax
  const char *v48; // r9
  __int64 v49; // r11
  __int64 v50; // rax
  __int64 v51; // rax
  const char *v52; // r9
  __int64 v53; // r11
  __int64 v54; // rax
  __int64 v55; // rax
  const char *v56; // r9
  __int64 v57; // r11
  __int64 v58; // rax
  __int64 v59; // rax
  const char *v60; // r9
  __int64 v61; // r11
  __int64 v62; // rax
  const char *v63; // [rsp+20h] [rbp-10h] BYREF
  __int64 v64; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]

  traits_1_unsigned_char = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                             "CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NU"
                             "LL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL C"
                             "OLLATE NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            VARI"
                             "ABLE              TEXT NOT NULL COLLATE NOCASE CHECK(VALUE <> ''),            VALUE        "
                             "         TEXT,            TYPE                  INTEGER,            PRIMARY KEY(PROVIDERID,"
                             " UPDATEID, TIME, VARIABLE)            FOREIGN KEY(PROVIDERID, UPDATEID, TIME) REFERENCES AC"
                             "TIONRECORDS(PROVIDERID, UPDATEID, TIME) ON DELETE CASCADE);",
                             &word_14041B41E,
                             0);
  if ( traits_1_unsigned_char == v4
    || (v5 = traits_1_unsigned_char
           - (_QWORD)"CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NULL COLLA"
                     "TE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CH"
                     "ECK(UPDATEID <> ''),            TIME                  TEXT,            VARIABLE              TEXT N"
                     "OT NULL COLLATE NOCASE CHECK(VALUE <> ''),            VALUE                 TEXT,            TYPE  "
                     "                INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME, VARIABLE)            FO"
                     "REIGN KEY(PROVIDERID, UPDATEID, TIME) REFERENCES ACTIONRECORDS(PROVIDERID, UPDATEID, TIME) ON DELETE CASCADE);",
        v5 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v3);
  }
  v6 = (char *)this + 40;
  v63 = "CREATE TABLE IF NOT EXISTS ACTIONRECORDSPROP (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHE"
        "CK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),      "
        "      TIME                  TEXT,            VARIABLE              TEXT NOT NULL COLLATE NOCASE CHECK(VALUE <> '"
        "'),            VALUE                 TEXT,            TYPE                  INTEGER,            PRIMARY KEY(PROV"
        "IDERID, UPDATEID, TIME, VARIABLE)            FOREIGN KEY(PROVIDERID, UPDATEID, TIME) REFERENCES ACTIONRECORDS(PR"
        "OVIDERID, UPDATEID, TIME) ON DELETE CASCADE);";
  v64 = v5;
  Windows::SqlExec(v6, &v63);
  v7 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
         "CREATE TABLE IF NOT EXISTS COMPLETEDUPDATES (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHE"
         "CK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),     "
         "       TIME                  TEXT,            TITLE                 TEXT,            DESCRIPTION           TEXT"
         ",            MOREINFOURL           TEXT,            HISTORYCATEGORY       TEXT,            UNINSTALL           "
         "  INTEGER,            WASREBOOTREQUIRED     INTEGER,            FOROS                 INTEGER,            METAD"
         "ATA              TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID));",
         byte_14041CCC1,
         0);
  if ( v7 == v9
    || (v10 = v7
            - (_QWORD)"CREATE TABLE IF NOT EXISTS COMPLETEDUPDATES (            PROVIDERID            TEXT NOT NULL COLLA"
                      "TE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE C"
                      "HECK(UPDATEID <> ''),            TIME                  TEXT,            TITLE                 TEXT"
                      ",            DESCRIPTION           TEXT,            MOREINFOURL           TEXT,            HISTORY"
                      "CATEGORY       TEXT,            UNINSTALL             INTEGER,            WASREBOOTREQUIRED     IN"
                      "TEGER,            FOROS                 INTEGER,            METADATA              TEXT,           "
                      " PRIMARY KEY(PROVIDERID, UPDATEID));",
        v10 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v8);
  }
  v63 = "CREATE TABLE IF NOT EXISTS COMPLETEDUPDATES (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHEC"
        "K(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),       "
        "     TIME                  TEXT,            TITLE                 TEXT,            DESCRIPTION           TEXT,  "
        "          MOREINFOURL           TEXT,            HISTORYCATEGORY       TEXT,            UNINSTALL             IN"
        "TEGER,            WASREBOOTREQUIRED     INTEGER,            FOROS                 INTEGER,            METADATA  "
        "            TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID));";
  v64 = v10;
  Windows::SqlExec(v6, &v63);
  v11 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS VARIABLES (            KEY        TEXT NOT NULL COLLATE NOCASE CHECK(KEY <> ''),   "
          "         VALUE      TEXT,            TYPE       INTEGER,            PRIMARY KEY(KEY));",
          byte_14041CA45,
          0);
  if ( v11 == v13
    || (v14 = v11
            - (_QWORD)"CREATE TABLE IF NOT EXISTS VARIABLES (            KEY        TEXT NOT NULL COLLATE NOCASE CHECK(KE"
                      "Y <> ''),            VALUE      TEXT,            TYPE       INTEGER,            PRIMARY KEY(KEY));",
        v14 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v12);
  }
  v63 = "CREATE TABLE IF NOT EXISTS VARIABLES (            KEY        TEXT NOT NULL COLLATE NOCASE CHECK(KEY <> ''),     "
        "       VALUE      TEXT,            TYPE       INTEGER,            PRIMARY KEY(KEY));";
  v64 = v14;
  Windows::SqlExec(v6, &v63);
  v15 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS UPDATES (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVI"
          "DERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            "
          "SERIALIZEDUPDATE      BLOB,            PRIMARY KEY(PROVIDERID, UPDATEID));",
          &byte_14041CFE7,
          0);
  if ( v15 == v17
    || (v18 = v15
            - (_QWORD)"CREATE TABLE IF NOT EXISTS UPDATES (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE"
                      " CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDA"
                      "TEID <> ''),            SERIALIZEDUPDATE      BLOB,            PRIMARY KEY(PROVIDERID, UPDATEID));",
        v18 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v16);
  }
  v63 = "CREATE TABLE IF NOT EXISTS UPDATES (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDE"
        "RID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            SERI"
        "ALIZEDUPDATE      BLOB,            PRIMARY KEY(PROVIDERID, UPDATEID));";
  v64 = v18;
  Windows::SqlExec(v6, &v63);
  v19 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS UPDATESPROP (            PROVIDERID TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <"
          "> ''),            UPDATEID   TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            VARIABLE   TEXT NO"
          "T NULL COLLATE NOCASE CHECK(VARIABLE <> ''),            VALUE      TEXT,            TYPE       INTEGER,       "
          "     PRIMARY KEY(PROVIDERID, UPDATEID, VARIABLE)            FOREIGN KEY(PROVIDERID, UPDATEID) REFERENCES UPDAT"
          "ES(PROVIDERID, UPDATEID) ON DELETE CASCADE);",
          byte_14041CEB5,
          0);
  if ( v19 == v21
    || (v22 = v19
            - (_QWORD)"CREATE TABLE IF NOT EXISTS UPDATESPROP (            PROVIDERID TEXT NOT NULL COLLATE NOCASE CHECK("
                      "PROVIDERID <> ''),            UPDATEID   TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),      "
                      "      VARIABLE   TEXT NOT NULL COLLATE NOCASE CHECK(VARIABLE <> ''),            VALUE      TEXT,  "
                      "          TYPE       INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, VARIABLE)            FO"
                      "REIGN KEY(PROVIDERID, UPDATEID) REFERENCES UPDATES(PROVIDERID, UPDATEID) ON DELETE CASCADE);",
        v22 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v20);
  }
  v63 = "CREATE TABLE IF NOT EXISTS UPDATESPROP (            PROVIDERID TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <> "
        "''),            UPDATEID   TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),            VARIABLE   TEXT NOT NU"
        "LL COLLATE NOCASE CHECK(VARIABLE <> ''),            VALUE      TEXT,            TYPE       INTEGER,            P"
        "RIMARY KEY(PROVIDERID, UPDATEID, VARIABLE)            FOREIGN KEY(PROVIDERID, UPDATEID) REFERENCES UPDATES(PROVI"
        "DERID, UPDATEID) ON DELETE CASCADE);";
  v64 = v22;
  Windows::SqlExec(v6, &v63);
  v23 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS ACTIONRECORDS (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK"
          "(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),      "
          "      TIME                  TEXT,            ACTION                TEXT,            ACTIONCLASS           TEXT"
          ",            RESULT                INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME)            FORE"
          "IGN KEY(PROVIDERID, UPDATEID) REFERENCES UPDATES(PROVIDERID, UPDATEID) ON DELETE CASCADE);",
          byte_14041C573,
          0);
  if ( v23 == v25
    || (v26 = v23
            - (_QWORD)"CREATE TABLE IF NOT EXISTS ACTIONRECORDS (            PROVIDERID            TEXT NOT NULL COLLATE "
                      "NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHEC"
                      "K(UPDATEID <> ''),            TIME                  TEXT,            ACTION                TEXT,  "
                      "          ACTIONCLASS           TEXT,            RESULT                INTEGER,            PRIMARY"
                      " KEY(PROVIDERID, UPDATEID, TIME)            FOREIGN KEY(PROVIDERID, UPDATEID) REFERENCES UPDATES(P"
                      "ROVIDERID, UPDATEID) ON DELETE CASCADE);",
        v26 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v24);
  }
  v63 = "CREATE TABLE IF NOT EXISTS ACTIONRECORDS (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK(P"
        "ROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),          "
        "  TIME                  TEXT,            ACTION                TEXT,            ACTIONCLASS           TEXT,     "
        "       RESULT                INTEGER,            PRIMARY KEY(PROVIDERID, UPDATEID, TIME)            FOREIGN KEY("
        "PROVIDERID, UPDATEID) REFERENCES UPDATES(PROVIDERID, UPDATEID) ON DELETE CASCADE);";
  v64 = v26;
  Windows::SqlExec(v6, &v63);
  v27 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS PROVIDERSPROP (            PROVIDERID TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID"
          " <> ''),            VARIABLE   TEXT NOT NULL COLLATE NOCASE CHECK(VARIABLE <> ''),            VALUE      TEXT,"
          "            TYPE       INTEGER,            PRIMARY KEY(PROVIDERID, VARIABLE));",
          byte_14041C35B,
          0);
  if ( v27 == v29
    || (v30 = v27
            - (_QWORD)"CREATE TABLE IF NOT EXISTS PROVIDERSPROP (            PROVIDERID TEXT NOT NULL COLLATE NOCASE CHEC"
                      "K(PROVIDERID <> ''),            VARIABLE   TEXT NOT NULL COLLATE NOCASE CHECK(VARIABLE <> ''),    "
                      "        VALUE      TEXT,            TYPE       INTEGER,            PRIMARY KEY(PROVIDERID, VARIABLE));",
        v30 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v28);
  }
  v63 = "CREATE TABLE IF NOT EXISTS PROVIDERSPROP (            PROVIDERID TEXT NOT NULL COLLATE NOCASE CHECK(PROVIDERID <"
        "> ''),            VARIABLE   TEXT NOT NULL COLLATE NOCASE CHECK(VARIABLE <> ''),            VALUE      TEXT,    "
        "        TYPE       INTEGER,            PRIMARY KEY(PROVIDERID, VARIABLE));";
  v64 = v30;
  Windows::SqlExec(v6, &v63);
  v31 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHE"
          "CK(UPDATEID <> ''),            TIME                  TEXT,            PRIMARY KEY(UPDATEID));",
          &dword_14041B69C,
          0);
  if ( v31 == v33
    || (v34 = v31
            - (_QWORD)"CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT NULL COLLAT"
                      "E NOCASE CHECK(UPDATEID <> ''),            TIME                  TEXT,            PRIMARY KEY(UPDATEID));",
        v34 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v32);
  }
  v63 = "CREATE TABLE IF NOT EXISTS APPROVEDUPDATES (            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK"
        "(UPDATEID <> ''),            TIME                  TEXT,            PRIMARY KEY(UPDATEID));";
  v64 = v34;
  Windows::SqlExec(v6, &v63);
  v35 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS SIGNALUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK"
          "(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE                 INTEGER,            "
          "PRIMARY KEY(UNIQUEID));",
          &dword_14041B5C4,
          0);
  if ( v35 == v37
    || (v38 = v35
            - (_QWORD)"CREATE TABLE IF NOT EXISTS SIGNALUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE "
                      "NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE             "
                      "    INTEGER,            PRIMARY KEY(UNIQUEID));",
        v38 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v36);
  }
  v63 = "CREATE TABLE IF NOT EXISTS SIGNALUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK(U"
        "NIQUEID <> ''),            PAYLOADID             TEXT,            STATE                 INTEGER,            PRIM"
        "ARY KEY(UNIQUEID));";
  v64 = v38;
  Windows::SqlExec(v6, &v63);
  v39 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS WSXPACKUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHEC"
          "K(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE                 INTEGER,           "
          " PRIMARY KEY(UNIQUEID));",
          byte_14041B8E5,
          0);
  if ( v39 == v41
    || (v42 = v39
            - (_QWORD)"CREATE TABLE IF NOT EXISTS WSXPACKUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE"
                      " NOCASE CHECK(UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE            "
                      "     INTEGER,            PRIMARY KEY(UNIQUEID));",
        v42 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v40);
  }
  v63 = "CREATE TABLE IF NOT EXISTS WSXPACKUPDATES (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK("
        "UNIQUEID <> ''),            PAYLOADID             TEXT,            STATE                 INTEGER,            PRI"
        "MARY KEY(UNIQUEID));";
  v64 = v42;
  Windows::SqlExec(v6, &v63);
  v43 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHE"
          "CK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            ESTIMATEDTIMEHIGH     INTEGER,       "
          "     TIMESTAMP             TEXT,            REALLABEL             INTEGER,            REALLABELSECONDS      IN"
          "TEGER,            UPDATEMETADATA        TEXT,            PRIMARY KEY(UNIQUEID));",
          byte_14041C97B,
          0);
  if ( v43 == v45
    || (v46 = v43
            - (_QWORD)"CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLAT"
                      "E NOCASE CHECK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            ESTIMATEDTIME"
                      "HIGH     INTEGER,            TIMESTAMP             TEXT,            REALLABEL             INTEGER,"
                      "            REALLABELSECONDS      INTEGER,            UPDATEMETADATA        TEXT,            PRIMA"
                      "RY KEY(UNIQUEID));",
        v46 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v44);
  }
  v63 = "CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHECK"
        "(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            ESTIMATEDTIMEHIGH     INTEGER,           "
        " TIMESTAMP             TEXT,            REALLABEL             INTEGER,            REALLABELSECONDS      INTEGER,"
        "            UPDATEMETADATA        TEXT,            PRIMARY KEY(UNIQUEID));";
  v64 = v46;
  Windows::SqlExec(v6, &v63);
  v47 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS DEFERRALHISTORY (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHE"
          "CK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),    "
          "        UPDATEGROUP           TEXT,            ACTION                TEXT,            ACTIONATTEMPT         IN"
          "TEGER DEFAULT 1,            DEFERRALREASON        TEXT,            ISPRIMARYDEFERRAL     TEXT,            DEFE"
          "RRALSTARTTIME     TEXT,            DEFERRALENDTIME       TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID, AC"
          "TION, ACTIONATTEMPT, DEFERRALREASON, DEFERRALSTARTTIME));",
          "CREATE TABLE IF NOT EXISTS DOWNTIMEHISTORY (            UNIQUEID              TEXT NOT NULL COLLATE NOCASE CHE"
          "CK(UNIQUEID <> ''),            ESTIMATEDTIME         INTEGER,            ESTIMATEDTIMEHIGH     INTEGER,       "
          "     TIMESTAMP             TEXT,            REALLABEL             INTEGER,            REALLABELSECONDS      IN"
          "TEGER,            UPDATEMETADATA        TEXT,            PRIMARY KEY(UNIQUEID));",
          0);
  if ( v47 == v49
    || (v50 = v47
            - (_QWORD)"CREATE TABLE IF NOT EXISTS DEFERRALHISTORY (            PROVIDERID            TEXT NOT NULL COLLAT"
                      "E NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CH"
                      "ECK(UPDATEID <> ''),            UPDATEGROUP           TEXT,            ACTION                TEXT,"
                      "            ACTIONATTEMPT         INTEGER DEFAULT 1,            DEFERRALREASON        TEXT,       "
                      "     ISPRIMARYDEFERRAL     TEXT,            DEFERRALSTARTTIME     TEXT,            DEFERRALENDTIME"
                      "       TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID, ACTION, ACTIONATTEMPT, DEFERRALREASON, D"
                      "EFERRALSTARTTIME));",
        v50 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v48);
  }
  v63 = "CREATE TABLE IF NOT EXISTS DEFERRALHISTORY (            PROVIDERID            TEXT NOT NULL COLLATE NOCASE CHECK"
        "(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <> ''),        "
        "    UPDATEGROUP           TEXT,            ACTION                TEXT,            ACTIONATTEMPT         INTEGER "
        "DEFAULT 1,            DEFERRALREASON        TEXT,            ISPRIMARYDEFERRAL     TEXT,            DEFERRALSTAR"
        "TTIME     TEXT,            DEFERRALENDTIME       TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID, ACTION, ACTI"
        "ONATTEMPT, DEFERRALREASON, DEFERRALSTARTTIME));";
  v64 = v50;
  Windows::SqlExec(v6, &v63);
  v51 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,            TREATMENTBUCKET"
          " TEXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));",
          "UPDATE DEFERRALHISTORY SET ISPRIMARYDEFERRAL = NULL;",
          0);
  if ( v51 == v53
    || (v54 = v51
            - (_QWORD)"CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,            TRE"
                      "ATMENTBUCKET TEXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));",
        v54 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v52);
  }
  v63 = "CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORY (            DATETIMECHECKED TEXT,            TREATMENTBUCKET T"
        "EXT,            PRIMARY KEY(DATETIMECHECKED, TREATMENTBUCKET));";
  v64 = v54;
  Windows::SqlExec(v6, &v63);
  v55 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORYSTATUS (            REBOOTATTEMPTTIMESTAMP TEXT,            DE"
          "FERRALREASON         TEXT,            REBOOTREQUIREDTIMEUTC  TEXT,            PRIMARY KEY(REBOOTATTEMPTTIMESTA"
          "MP, DEFERRALREASON));",
          word_14041BDE2,
          0);
  if ( v55 == v57
    || (v58 = v55
            - (_QWORD)"CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORYSTATUS (            REBOOTATTEMPTTIMESTAMP TEXT,  "
                      "          DEFERRALREASON         TEXT,            REBOOTREQUIREDTIMEUTC  TEXT,            PRIMARY "
                      "KEY(REBOOTATTEMPTTIMESTAMP, DEFERRALREASON));",
        v58 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v56);
  }
  v63 = "CREATE TABLE IF NOT EXISTS REBOOTDEFERRALHISTORYSTATUS (            REBOOTATTEMPTTIMESTAMP TEXT,            DEFE"
        "RRALREASON         TEXT,            REBOOTREQUIREDTIMEUTC  TEXT,            PRIMARY KEY(REBOOTATTEMPTTIMESTAMP, "
        "DEFERRALREASON));";
  v64 = v58;
  Windows::SqlExec(v6, &v63);
  v59 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
          "CREATE TABLE IF NOT EXISTS UPDATEEVENTHISTORYDIAGNOSTICS (            PROVIDERID            TEXT NOT NULL COLL"
          "ATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATE"
          "ID <> ''),            STARTTIME             TEXT,            ENDTIME               TEXT,            EVENT     "
          "            TEXT,            CATEGORY              TEXT,            TITLE                 TEXT,            RES"
          "ULT                INTEGER,            REASON                TEXT,            APPROVALS             TEXT,     "
          "       ISSEEKER              INTEGER,            FLIGHTID              TEXT,            UPDATEMETADATA        "
          "TEXT,            OTHER                 TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID, STARTTIME, EVENT));",
          word_14041BCE2,
          0);
  if ( v59 == v61
    || (v62 = v59
            - (_QWORD)"CREATE TABLE IF NOT EXISTS UPDATEEVENTHISTORYDIAGNOSTICS (            PROVIDERID            TEXT N"
                      "OT NULL COLLATE NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COL"
                      "LATE NOCASE CHECK(UPDATEID <> ''),            STARTTIME             TEXT,            ENDTIME      "
                      "         TEXT,            EVENT                 TEXT,            CATEGORY              TEXT,      "
                      "      TITLE                 TEXT,            RESULT                INTEGER,            REASON     "
                      "           TEXT,            APPROVALS             TEXT,            ISSEEKER              INTEGER, "
                      "           FLIGHTID              TEXT,            UPDATEMETADATA        TEXT,            OTHER    "
                      "             TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID, STARTTIME, EVENT));",
        v62 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v60);
  }
  v63 = "CREATE TABLE IF NOT EXISTS UPDATEEVENTHISTORYDIAGNOSTICS (            PROVIDERID            TEXT NOT NULL COLLAT"
        "E NOCASE CHECK(PROVIDERID <> ''),            UPDATEID              TEXT NOT NULL COLLATE NOCASE CHECK(UPDATEID <"
        "> ''),            STARTTIME             TEXT,            ENDTIME               TEXT,            EVENT           "
        "      TEXT,            CATEGORY              TEXT,            TITLE                 TEXT,            RESULT     "
        "           INTEGER,            REASON                TEXT,            APPROVALS             TEXT,            ISS"
        "EEKER              INTEGER,            FLIGHTID              TEXT,            UPDATEMETADATA        TEXT,       "
        "     OTHER                 TEXT,            PRIMARY KEY(PROVIDERID, UPDATEID, STARTTIME, EVENT));";
  v64 = v62;
  Windows::SqlExec(v6, &v63);
}

```

## disassembly

```asm
0x14018fb74  mov     [rsp-8+arg_8], rbx
0x14018fb79  mov     [rsp-8+arg_10], rsi
0x14018fb7e  push    rbp
0x14018fb7f  mov     rbp, rsp
0x14018fb82  sub     rsp, 30h
0x14018fb86  mov     rbx, rcx
0x14018fb89  lea     r11, word_14041B41E
0x14018fb90  lea     rsi, aCreateTableIfN_2; "CREATE TABLE IF NOT EXISTS ACTIONRECORD"...
0x14018fb97  mov     rdx, r11
0x14018fb9a  mov     rcx, rsi
0x14018fb9d  xor     r8d, r8d
0x14018fba0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fba5  cmp     rax, r11
0x14018fba8  jz      loc_14018FFC5
0x14018fbae  sub     rax, rsi
0x14018fbb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fbb5  jz      loc_14018FFC5
0x14018fbbb  add     rbx, 28h ; '('
0x14018fbbf  mov     [rbp+var_10], rsi
0x14018fbc3  mov     rcx, rbx
0x14018fbc6  mov     [rbp+var_8], rax
0x14018fbca  lea     rdx, [rbp+var_10]
0x14018fbce  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fbd3  lea     r11, byte_14041CCC1
0x14018fbda  xor     r8d, r8d
0x14018fbdd  lea     rsi, aCreateTableIfN_11; "CREATE TABLE IF NOT EXISTS COMPLETEDUPD"...
0x14018fbe4  mov     rdx, r11
0x14018fbe7  mov     rcx, rsi
0x14018fbea  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fbef  cmp     rax, r11
0x14018fbf2  jz      loc_14018FFAF
0x14018fbf8  sub     rax, rsi
0x14018fbfb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fbff  jz      loc_14018FFAF
0x14018fc05  lea     rdx, [rbp+var_10]
0x14018fc09  mov     [rbp+var_10], rsi
0x14018fc0d  mov     rcx, rbx
0x14018fc10  mov     [rbp+var_8], rax
0x14018fc14  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fc19  lea     r11, byte_14041CA45
0x14018fc20  xor     r8d, r8d
0x14018fc23  lea     rsi, aCreateTableIfN_4; "CREATE TABLE IF NOT EXISTS VARIABLES ( "...
0x14018fc2a  mov     rdx, r11
0x14018fc2d  mov     rcx, rsi
0x14018fc30  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fc35  cmp     rax, r11
0x14018fc38  jz      loc_1401900E3
0x14018fc3e  sub     rax, rsi
0x14018fc41  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fc45  jz      loc_1401900E3
0x14018fc4b  lea     rdx, [rbp+var_10]
0x14018fc4f  mov     [rbp+var_10], rsi
0x14018fc53  mov     rcx, rbx
0x14018fc56  mov     [rbp+var_8], rax
0x14018fc5a  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fc5f  lea     r11, byte_14041CFE7
0x14018fc66  xor     r8d, r8d
0x14018fc69  lea     rsi, aCreateTableIfN_10; "CREATE TABLE IF NOT EXISTS UPDATES (   "...
0x14018fc70  mov     rdx, r11
0x14018fc73  mov     rcx, rsi
0x14018fc76  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fc7b  cmp     rax, r11
0x14018fc7e  jz      loc_1401900CD
0x14018fc84  sub     rax, rsi
0x14018fc87  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fc8b  jz      loc_1401900CD
0x14018fc91  lea     rdx, [rbp+var_10]
0x14018fc95  mov     [rbp+var_10], rsi
0x14018fc99  mov     rcx, rbx
0x14018fc9c  mov     [rbp+var_8], rax
0x14018fca0  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fca5  lea     r11, byte_14041CEB5
0x14018fcac  xor     r8d, r8d
0x14018fcaf  lea     rsi, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS UPDATESPROP "...
0x14018fcb6  mov     rdx, r11
0x14018fcb9  mov     rcx, rsi
0x14018fcbc  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fcc1  cmp     rax, r11
0x14018fcc4  jz      loc_1401900B7
0x14018fcca  sub     rax, rsi
0x14018fccd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fcd1  jz      loc_1401900B7
0x14018fcd7  lea     rdx, [rbp+var_10]
0x14018fcdb  mov     [rbp+var_10], rsi
0x14018fcdf  mov     rcx, rbx
0x14018fce2  mov     [rbp+var_8], rax
0x14018fce6  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fceb  lea     r11, byte_14041C573
0x14018fcf2  xor     r8d, r8d
0x14018fcf5  lea     rsi, aCreateTableIfN_13; "CREATE TABLE IF NOT EXISTS ACTIONRECORD"...
0x14018fcfc  mov     rdx, r11
0x14018fcff  mov     rcx, rsi
0x14018fd02  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fd07  cmp     rax, r11
0x14018fd0a  jz      loc_1401900A1
0x14018fd10  sub     rax, rsi
0x14018fd13  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fd17  jz      loc_1401900A1
0x14018fd1d  lea     rdx, [rbp+var_10]
0x14018fd21  mov     [rbp+var_10], rsi
0x14018fd25  mov     rcx, rbx
0x14018fd28  mov     [rbp+var_8], rax
0x14018fd2c  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fd31  lea     r11, byte_14041C35B
0x14018fd38  xor     r8d, r8d
0x14018fd3b  lea     rsi, aCreateTableIfN_14; "CREATE TABLE IF NOT EXISTS PROVIDERSPRO"...
0x14018fd42  mov     rdx, r11
0x14018fd45  mov     rcx, rsi
0x14018fd48  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fd4d  cmp     rax, r11
0x14018fd50  jz      loc_14019008B
0x14018fd56  sub     rax, rsi
0x14018fd59  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fd5d  jz      loc_14019008B
0x14018fd63  lea     rdx, [rbp+var_10]
0x14018fd67  mov     [rbp+var_10], rsi
0x14018fd6b  mov     rcx, rbx
0x14018fd6e  mov     [rbp+var_8], rax
0x14018fd72  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fd77  lea     r11, dword_14041B69C
0x14018fd7e  xor     r8d, r8d
0x14018fd81  lea     rsi, aCreateTableIfN_6; "CREATE TABLE IF NOT EXISTS APPROVEDUPDA"...
0x14018fd88  mov     rdx, r11
0x14018fd8b  mov     rcx, rsi
0x14018fd8e  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fd93  cmp     rax, r11
0x14018fd96  jz      loc_140190075
0x14018fd9c  sub     rax, rsi
0x14018fd9f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fda3  jz      loc_140190075
0x14018fda9  lea     rdx, [rbp+var_10]
0x14018fdad  mov     [rbp+var_10], rsi
0x14018fdb1  mov     rcx, rbx
0x14018fdb4  mov     [rbp+var_8], rax
0x14018fdb8  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fdbd  lea     r11, dword_14041B5C4
0x14018fdc4  xor     r8d, r8d
0x14018fdc7  lea     rsi, aCreateTableIfN_15; "CREATE TABLE IF NOT EXISTS SIGNALUPDATE"...
0x14018fdce  mov     rdx, r11
0x14018fdd1  mov     rcx, rsi
0x14018fdd4  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fdd9  cmp     rax, r11
0x14018fddc  jz      loc_14019005F
0x14018fde2  sub     rax, rsi
0x14018fde5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fde9  jz      loc_14019005F
0x14018fdef  lea     rdx, [rbp+var_10]
0x14018fdf3  mov     [rbp+var_10], rsi
0x14018fdf7  mov     rcx, rbx
0x14018fdfa  mov     [rbp+var_8], rax
0x14018fdfe  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fe03  lea     r11, byte_14041B8E5
0x14018fe0a  xor     r8d, r8d
0x14018fe0d  lea     rsi, aCreateTableIfN_8; "CREATE TABLE IF NOT EXISTS WSXPACKUPDAT"...
0x14018fe14  mov     rdx, r11
0x14018fe17  mov     rcx, rsi
0x14018fe1a  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fe1f  cmp     rax, r11
0x14018fe22  jz      loc_140190049
0x14018fe28  sub     rax, rsi
0x14018fe2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fe2f  jz      loc_140190049
0x14018fe35  lea     rdx, [rbp+var_10]
0x14018fe39  mov     [rbp+var_10], rsi
0x14018fe3d  mov     rcx, rbx
0x14018fe40  mov     [rbp+var_8], rax
0x14018fe44  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fe49  lea     r11, byte_14041C97B
0x14018fe50  xor     r8d, r8d
0x14018fe53  lea     rsi, aCreateTableIfN_1; "CREATE TABLE IF NOT EXISTS DOWNTIMEHIST"...
0x14018fe5a  mov     rdx, r11
0x14018fe5d  mov     rcx, rsi
0x14018fe60  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fe65  cmp     rax, r11
0x14018fe68  jz      loc_140190033
0x14018fe6e  sub     rax, rsi
0x14018fe71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018fe75  jz      loc_140190033
0x14018fe7b  lea     rdx, [rbp+var_10]
0x14018fe7f  mov     [rbp+var_10], rsi
0x14018fe83  mov     rcx, rbx
0x14018fe86  mov     [rbp+var_8], rax
0x14018fe8a  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fe8f  lea     r11, aCreateTableIfN_1; "CREATE TABLE IF NOT EXISTS DOWNTIMEHIST"...
0x14018fe96  xor     r8d, r8d
0x14018fe99  lea     rsi, aCreateTableIfN_5; "CREATE TABLE IF NOT EXISTS DEFERRALHIST"...
0x14018fea0  mov     rdx, r11
0x14018fea3  mov     rcx, rsi
0x14018fea6  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018feab  cmp     rax, r11
0x14018feae  jz      loc_14019001D
0x14018feb4  sub     rax, rsi
0x14018feb7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018febb  jz      loc_14019001D
0x14018fec1  lea     rdx, [rbp+var_10]
0x14018fec5  mov     [rbp+var_10], rsi
0x14018fec9  mov     rcx, rbx
0x14018fecc  mov     [rbp+var_8], rax
0x14018fed0  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018fed5  lea     r11, aUpdateDeferral_3; "UPDATE DEFERRALHISTORY SET ISPRIMARYDEF"...
0x14018fedc  xor     r8d, r8d
0x14018fedf  lea     rsi, aCreateTableIfN_0; "CREATE TABLE IF NOT EXISTS REBOOTDEFERR"...
0x14018fee6  mov     rdx, r11
0x14018fee9  mov     rcx, rsi
0x14018feec  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018fef1  cmp     rax, r11
0x14018fef4  jz      loc_140190007
0x14018fefa  sub     rax, rsi
0x14018fefd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018ff01  jz      loc_140190007
0x14018ff07  lea     rdx, [rbp+var_10]
0x14018ff0b  mov     [rbp+var_10], rsi
0x14018ff0f  mov     rcx, rbx
0x14018ff12  mov     [rbp+var_8], rax
0x14018ff16  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018ff1b  lea     r11, word_14041BDE2
0x14018ff22  xor     r8d, r8d
0x14018ff25  lea     rsi, aCreateTableIfN_7; "CREATE TABLE IF NOT EXISTS REBOOTDEFERR"...
0x14018ff2c  mov     rdx, r11
0x14018ff2f  mov     rcx, rsi
0x14018ff32  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018ff37  cmp     rax, r11
0x14018ff3a  jz      loc_14018FFF1
0x14018ff40  sub     rax, rsi
0x14018ff43  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018ff47  jz      loc_14018FFF1
0x14018ff4d  lea     rdx, [rbp+var_10]
0x14018ff51  mov     [rbp+var_10], rsi
0x14018ff55  mov     rcx, rbx
0x14018ff58  mov     [rbp+var_8], rax
0x14018ff5c  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018ff61  lea     r11, word_14041BCE2
0x14018ff68  xor     r8d, r8d
0x14018ff6b  lea     rsi, aCreateTableIfN_12; "CREATE TABLE IF NOT EXISTS UPDATEEVENTH"...
0x14018ff72  mov     rdx, r11
0x14018ff75  mov     rcx, rsi
0x14018ff78  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_1_unsigned_char_
0x14018ff7d  cmp     rax, r11
0x14018ff80  jz      short loc_14018FFDB
0x14018ff82  sub     rax, rsi
0x14018ff85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14018ff89  jz      short loc_14018FFDB
0x14018ff8b  lea     rdx, [rbp+var_10]
0x14018ff8f  mov     [rbp+var_10], rsi
0x14018ff93  mov     rcx, rbx
0x14018ff96  mov     [rbp+var_8], rax
0x14018ff9a  call    ?SqlExec@Windows@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@D@3@@Z; Windows::SqlExec(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,wil::basic_zstring_view<char>)
0x14018ff9f  mov     rbx, [rsp+30h+arg_8]
0x14018ffa4  mov     rsi, [rsp+30h+arg_10]
0x14018ffa9  add     rsp, 30h
0x14018ffad  pop     rbp
0x14018ffae  retn
0x14018ffaf  mov     rcx, [rbp+8]; this
0x14018ffb3  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14018ffba  mov     edx, 0C9h; void *
0x14018ffbf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14018ffc5  mov     rcx, [rbp+8]; this
0x14018ffc9  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14018ffd0  mov     edx, 0C9h; void *
0x14018ffd5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14018ffdb  mov     rcx, [rbp+8]; this
0x14018ffdf  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14018ffe6  mov     edx, 0C9h; void *
0x14018ffeb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14018fff1  mov     rcx, [rbp+8]; this
0x14018fff5  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14018fffc  mov     edx, 0C9h; void *
0x140190001  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140190007  mov     rcx, [rbp+8]; this
0x14019000b  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140190012  mov     edx, 0C9h; void *
0x140190017  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14019001d  mov     rcx, [rbp+8]; this
0x140190021  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140190028  mov     edx, 0C9h; void *
0x14019002d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140190033  mov     rcx, [rbp+8]; this
0x140190037  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14019003e  mov     edx, 0C9h; void *
0x140190043  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140190049  mov     rcx, [rbp+8]; this
0x14019004d  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140190054  mov     edx, 0C9h; void *
0x140190059  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14019005f  mov     rcx, [rbp+8]; this
0x140190063  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14019006a  mov     edx, 0C9h; void *
0x14019006f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140190075  mov     rcx, [rbp+8]; this
0x140190079  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140190080  mov     edx, 0C9h; void *
0x140190085  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14019008b  mov     rcx, [rbp+8]; this
0x14019008f  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140190096  mov     edx, 0C9h; void *
0x14019009b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1401900a1  mov     rcx, [rbp+8]; this
0x1401900a5  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1401900ac  mov     edx, 0C9h; void *
0x1401900b1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
  ... truncated ...
```
