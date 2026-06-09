# sub_1400BB6FC

- ea: `0x1400bb6fc`
- end: `0x1400bbfbd`
- name: `sub_1400BB6FC`
- size: `2241`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1401758a0`
- `0x14024f930`

## callees

- `0x14001e270`
- `0x1400453c0`
- `0x140051cd0`
- `0x1400bad58`
- `0x1400bb178`
- `0x1400bb6fc`
- `0x1400bbfc0`
- `0x1400bc164`
- `0x1400bc1b4`
- `0x1400bc230`
- `0x1400bc3ec`
- `0x1400bcae0`
- `0x1400bcbc0`
- `0x1400bcc90`
- `0x1400bce24`
- `0x1400bd4c4`
- `0x1400ece80`
- `0x14014ff8c`
- `0x14015d3c8`
- `0x140262184`
- `0x1402621d4`
- `0x140355bb0`
- `0x1403e1680`
- `0x1403e2e76`
- `0x1403e4ee0`
- `0x1407b0e20`

## import_xrefs

- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1400bb96d`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1400bb96d`
- `MSVCP140!_Mtx_unlock` at `0x1400bbfb1`
- `MSVCP140!_Mtx_unlock` at `0x1400bbfb1`

## string_xrefs

- `0x1400bb874`: `PRAGMA temp_store_directory = '`
- `0x1400bbb2f`: `CREATE TABLE IF NOT EXISTS settings (name TEXT,value TEXT, PRIMARY KEY (name))`
- `0x1400bba41`: `CREATE TABLE IF NOT EXISTS events (record_id TEXT,tenant_token TEXT NOT NULL,latency INTEGER,persistence INTEGER,timestamp INTEGER,retry_count INTEGER DEFAULT 0,reserved_until INTEGER DEFAULT 0,payload BLOB)`
- `0x1400bbab8`: `CREATE INDEX IF NOT EXISTS k_latency_timestamp ON events (latency DESC, persistence DESC, timestamp ASC)`
- `0x1400bbcc3`: `DELETE FROM events WHERE record_id IN (SELECT record_id FROM events ORDER BY persistence ASC, timestamp ASC LIMIT MAX(1,(SELECT COUNT(record_id) FROM events)* ? / 100))`
- `0x1400bbd7b`: `WITH RECURSIVE ids(id) AS (SELECT 0 UNION ALL SELECT tokenize(?) FROM ids WHERE id IS NOT NULL LIMIT 10000 OFFSET 1) UPDATE events SET reserved_until=0, retry_count=retry_count+? WHERE record_id IN ids AND reserved_until>0`
- `0x1400bbd36`: `SELECT record_id,tenant_token,latency,timestamp,retry_count,reserved_until,payload FROM events WHERE latency>=? ORDER BY latency DESC,persistence DESC, timestamp ASC LIMIT ?`
- `0x1400bbdc0`: `REPLACE INTO events (record_id,tenant_token,latency,persistence,timestamp,payload) VALUES (?,?,?,?,?,?)`
- `0x1400bbd08`: `UPDATE events SET reserved_until=0, retry_count=retry_count+1 WHERE reserved_until<>0 AND reserved_until<=?`
- `0x1400bbd4d`: `SELECT record_id,tenant_token,latency,timestamp,retry_count,reserved_until,payload FROM events WHERE latency=(SELECT MIN(latency) FROM events WHERE reserved_until=0 AND latency>=?) AND reserved_until=0 ORDER BY timestamp ASC LIMIT ?`
- `0x1400bbda9`: `DELETE FROM events WHERE retry_count>?`
- `0x1400bbe47`: `DELETE FROM packages`
- `0x1400bbcf1`: `WITH RECURSIVE ids(id) AS (SELECT 0 UNION ALL SELECT tokenize(?) FROM ids WHERE id IS NOT NULL LIMIT 10000 OFFSET 1) DELETE FROM events WHERE record_id IN ids`
- `0x1400bbcda`: `WITH RECURSIVE ids(id) AS (SELECT 0 UNION ALL SELECT tokenize(?) FROM ids WHERE id IS NOT NULL LIMIT 10000 OFFSET 1) DELETE FROM events WHERE tenant_token IN ids`
- `0x1400bbdee`: `DELETE FROM settings WHERE name=?`
- `0x1400bbd64`: `WITH RECURSIVE ids(id) AS (SELECT 0 UNION ALL SELECT tokenize(?) FROM ids WHERE id IS NOT NULL LIMIT 10000 OFFSET 1) UPDATE events SET reserved_until=? WHERE record_id IN ids`
- `0x1400bbd92`: `SELECT tenant_token FROM events WHERE retry_count>?`
- `0x1400bbcac`: `SELECT tenant_token FROM events ORDER BY persistence ASC, timestamp ASC LIMIT MAX(1,(SELECT COUNT(record_id) FROM events)* ? / 100)`
- `0x1400bbd1f`: `SELECT record_id,tenant_token,latency,timestamp,retry_count,reserved_until,payload FROM events WHERE latency>=? AND reserved_until=0 ORDER BY latency DESC,persistence DESC, timestamp ASC LIMIT ?`
- `0x1400bbdd7`: `REPLACE INTO settings (name,value) VALUES (?,?)`
- `0x1400bbc50`: `ROLLBACK`
- `0x1400bbc39`: `COMMIT`

## pseudocode

```c
char __fastcall sub_1400BB6FC(__int64 a1)
{
  struct _Mtx_internal_imp_t *v2; // rsi
  __int64 v3; // rbx
  char v4; // r14
  struct _Mtx_internal_imp_t *v5; // rsi
  __int64 v6; // rbx
  char v7; // r14
  struct _Mtx_internal_imp_t *v8; // rsi
  __int64 v9; // rbx
  char v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  struct _Mtx_internal_imp_t *v14; // rsi
  __int64 v15; // rbx
  char v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rsi
  char v19; // al
  int v20; // ebx
  struct _Mtx_internal_imp_t *v21; // rsi
  __int64 v22; // rbx
  char v23; // r14
  char v24; // r15
  struct _Mtx_internal_imp_t *v25; // rsi
  __int64 v26; // rbx
  char v27; // r14
  char v28; // r15
  struct _Mtx_internal_imp_t *v29; // rsi
  __int64 v30; // rbx
  char v31; // r14
  char v32; // r15
  _Mtx_t v33; // rbx
  __int64 v34; // rsi
  char v35; // al
  void (__fastcall *v36)(__int64, __int128 *); // rbx
  _QWORD *v38; // rax
  __int64 v39; // rax
  char v40; // bl
  __int64 v41; // rax
  __int64 v42; // r8
  _BYTE v43[40]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v44[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v45[128]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v46[104]; // [rsp+D8h] [rbp-28h] BYREF
  _Mtx_t v47; // [rsp+140h] [rbp+40h] BYREF
  __int64 v48; // [rsp+148h] [rbp+48h]
  __int64 v49; // [rsp+150h] [rbp+50h]
  __int64 v50; // [rsp+158h] [rbp+58h]
  int v51; // [rsp+160h] [rbp+60h]
  __int128 v52; // [rsp+168h] [rbp+68h] BYREF
  __int64 v53; // [rsp+178h] [rbp+78h]
  unsigned __int64 v54; // [rsp+180h] [rbp+80h]

  v2 = *(struct _Mtx_internal_imp_t **)(a1 + 112);
  v47 = v2;
  v3 = sub_1400BBFC0(v2);
  v48 = v3;
  v49 = v3;
  v50 = 0;
  v4 = 1;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v3 )
  {
    sub_1400BC230(&v47, 0);
    v4 = v51;
    v3 = v48;
    v2 = v47;
  }
  if ( v4 )
    sub_1400BC1B4(v2, v3);
  v5 = *(struct _Mtx_internal_imp_t **)(a1 + 112);
  v47 = v5;
  v6 = sub_1400BBFC0(v5);
  v48 = v6;
  v49 = v6;
  v50 = 0;
  v7 = 1;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v6 )
  {
    sub_1400BC230(&v47, 0);
    v7 = v51;
    v6 = v48;
    v5 = v47;
  }
  if ( v7 )
    sub_1400BC1B4(v5, v6);
  v8 = *(struct _Mtx_internal_imp_t **)(a1 + 112);
  v47 = v8;
  v9 = sub_1400BBFC0(v8);
  v48 = v9;
  v49 = v9;
  v50 = 0;
  v10 = 1;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v9 )
  {
    sub_1400BC230(&v47, 0);
    v10 = v51;
    v9 = v48;
    v8 = v47;
  }
  if ( v10 )
    sub_1400BC1B4(v8, v9);
  sub_1400BCBC0(v44);
  v11 = sub_1400BB178(v44, "PRAGMA temp_store_directory = '");
  v12 = sub_1400BD4C4(&v52);
  v13 = unknown_libname_8(v11, v12);
  sub_1400BB178(v13, &dword_14083971C);
  if ( v54 > 0xF )
    sub_14001E270((_QWORD *)v52, v54 + 1);
  sub_1400BCE24(v45, &v52);
  v14 = *(struct _Mtx_internal_imp_t **)(a1 + 112);
  v47 = v14;
  v15 = sub_1400BBFC0(v14);
  v48 = v15;
  v49 = v15;
  v50 = 0;
  v16 = 1;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v15 )
  {
    sub_1400BC230(&v47, 0);
    v16 = v51;
    v15 = v48;
    v14 = v47;
  }
  if ( v16 )
    sub_1400BC1B4(v14, v15);
  if ( v54 > 0xF )
    sub_14001E270((_QWORD *)v52, v54 + 1);
  sub_1400BCC90(v46);
  std::ios::~ios<char,std::char_traits<char>>(v46);
  v47 = *(_Mtx_t *)(a1 + 112);
  v17 = sub_1400BBFC0(v47);
  v48 = v17;
  v18 = v17;
  v49 = v17;
  v50 = 0;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v17 )
  {
    v19 = sub_1400BC230(&v47, 0);
    v18 = v49;
    v17 = v48;
  }
  else
  {
    v19 = 0;
  }
  if ( !v19 || !v18 )
    goto LABEL_25;
  if ( !(unsigned __int8)sub_1402621D4(&v47) )
  {
    v17 = v48;
LABEL_25:
    if ( (_BYTE)v51 )
      sub_1400BC1B4(v47, v17);
    return 0;
  }
  v20 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(), __int64, _QWORD))off_140BEACF8[11])(&off_140BEACF8, v49, 0);
  if ( (_BYTE)v51 )
    sub_1400BC1B4(v47, v48);
  if ( v20 != 1 )
  {
    if ( v20 > 0 )
      return 0;
    sub_1400ECE80(&v52, 1);
    v38 = (_QWORD *)sub_14014FF8C(&v47, "PRAGMA user_version=", &v52);
    if ( v38[3] > 0xFu )
      v38 = (_QWORD *)*v38;
    v39 = sub_140355BB0(v43, *(_QWORD *)(a1 + 112), v38);
    v40 = *(_QWORD *)(v39 + 16) ? sub_1400BCAE0(v39, 0) : 0;
    sub_1400BC3EC(v43);
    sub_1400453C0(&v47);
    sub_1400453C0(&v52);
    if ( !v40 )
      return 0;
  }
  v21 = *(struct _Mtx_internal_imp_t **)(a1 + 112);
  v47 = v21;
  v22 = sub_1400BBFC0(v21);
  v48 = v22;
  v49 = v22;
  v50 = 0;
  v23 = 1;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v22 )
  {
    v24 = sub_1400BCAE0(&v47, 0);
    v23 = v51;
    v22 = v48;
    v21 = v47;
  }
  else
  {
    v24 = 0;
  }
  if ( v23 )
    sub_1400BC1B4(v21, v22);
  if ( !v24 )
    return 0;
  v25 = *(struct _Mtx_internal_imp_t **)(a1 + 112);
  v47 = v25;
  v26 = sub_1400BBFC0(v25);
  v48 = v26;
  v49 = v26;
  v50 = 0;
  v27 = 1;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v26 )
  {
    v28 = sub_1400BCAE0(&v47, 0);
    v27 = v51;
    v26 = v48;
    v25 = v47;
  }
  else
  {
    v28 = 0;
  }
  if ( v27 )
    sub_1400BC1B4(v25, v26);
  if ( !v28 )
    return 0;
  v29 = *(struct _Mtx_internal_imp_t **)(a1 + 112);
  v47 = v29;
  v30 = sub_1400BBFC0(v29);
  v48 = v30;
  v49 = v30;
  v50 = 0;
  v31 = 1;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v30 )
  {
    v32 = sub_1400BCAE0(&v47, 0);
    v31 = v51;
    v30 = v48;
    v29 = v47;
  }
  else
  {
    v32 = 0;
  }
  if ( v31 )
    sub_1400BC1B4(v29, v30);
  if ( !v32 )
    return 0;
  v33 = *(_Mtx_t *)(a1 + 112);
  v47 = v33;
  v34 = sub_1400BBFC0(v33);
  v48 = v34;
  v49 = v34;
  v50 = 0;
  v51 = 1;
  sub_1400BC164(&v47);
  if ( v34 )
  {
    v35 = sub_1400BC230(&v47, 0);
    v34 = v48;
    v33 = v47;
  }
  else
  {
    v35 = 0;
  }
  if ( !v35 )
  {
LABEL_70:
    if ( (_BYTE)v51 )
    {
      sub_140051CD0((__int64)v33);
      v41 = sub_1403E4EE0(*((_QWORD *)v33 + 11), *((_QWORD *)v33 + 12), v34);
      v42 = *((_QWORD *)v33 + 12);
      if ( v41 != v42 )
      {
        memmove((void *)v41, (const void *)(v41 + 8), v42 - (v41 + 8));
        *((_QWORD *)v33 + 12) -= 8LL;
        ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64))off_140BEACF8[17])(&off_140BEACF8, v34);
      }
      Mtx_unlock(v33);
    }
    return 0;
  }
  if ( !(unsigned __int8)sub_140262184(&v47, a1 + 120) )
  {
    v34 = v48;
    v33 = v47;
    goto LABEL_70;
  }
  if ( (_BYTE)v51 )
    sub_1400BC1B4(v47, v48);
  *(_QWORD *)(a1 + 216) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 224) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 232) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 240) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 248) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 256) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 264) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 272) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 296) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 280) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 288) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 304) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 312) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 320) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 328) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 336) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 352) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 344) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 360) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 368) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 376) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  *(_QWORD *)(a1 + 384) = sub_1400BBFC0(*(_Mtx_t *)(a1 + 112));
  v36 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 168LL);
  v52 = 0;
  v53 = 0;
  v54 = 0;
  sub_14015D3C8(&v52, "DELETE FROM packages", 20);
  v36(a1, &v52);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 152LL))(a1);
  return 1;
}

```

## disassembly

```asm
0x1400bb6fc  mov     [rsp-8+arg_8], rbx
0x1400bb701  mov     [rsp-8+arg_10], rsi
0x1400bb706  push    rbp
0x1400bb707  push    rdi
0x1400bb708  push    r12
0x1400bb70a  push    r14
0x1400bb70c  push    r15
0x1400bb70e  lea     rbp, [rsp-90h]
0x1400bb716  sub     rsp, 190h
0x1400bb71d  mov     rax, cs:__security_cookie
0x1400bb724  xor     rax, rsp
0x1400bb727  mov     [rbp+0B0h+var_28], rax
0x1400bb72e  mov     rdi, rcx
0x1400bb731  xor     r12d, r12d
0x1400bb734  mov     rsi, [rcx+70h]
0x1400bb738  mov     [rbp+0B0h+var_70], rsi
0x1400bb73c  lea     rdx, aPragmaAutoVacu; "PRAGMA auto_vacuum=FULL"
0x1400bb743  mov     rcx, rsi; _Mtx_t
0x1400bb746  call    sub_1400BBFC0
0x1400bb74b  mov     rbx, rax
0x1400bb74e  mov     [rbp+0B0h+var_68], rax
0x1400bb752  mov     [rbp+0B0h+var_60], rax
0x1400bb756  mov     [rbp+0B0h+var_58], r12
0x1400bb75a  mov     r14b, 1
0x1400bb75d  mov     [rbp+0B0h+var_50], 1
0x1400bb764  lea     rcx, [rbp+0B0h+var_70]
0x1400bb768  call    sub_1400BC164
0x1400bb76d  nop
0x1400bb76e  test    rbx, rbx
0x1400bb771  jz      short loc_1400BB78A
0x1400bb773  xor     edx, edx
0x1400bb775  lea     rcx, [rbp+0B0h+var_70]
0x1400bb779  call    sub_1400BC230
0x1400bb77e  mov     r14b, byte ptr [rbp+0B0h+var_50]
0x1400bb782  mov     rbx, [rbp+0B0h+var_68]
0x1400bb786  mov     rsi, [rbp+0B0h+var_70]
0x1400bb78a  test    r14b, r14b
0x1400bb78d  jz      short loc_1400BB79B
0x1400bb78f  mov     rdx, rbx
0x1400bb792  mov     rcx, rsi
0x1400bb795  call    sub_1400BC1B4
0x1400bb79a  nop
0x1400bb79b  mov     rsi, [rdi+70h]
0x1400bb79f  mov     [rbp+0B0h+var_70], rsi
0x1400bb7a3  lea     rdx, aPragmaJournalM; "PRAGMA journal_mode=WAL"
0x1400bb7aa  mov     rcx, rsi; _Mtx_t
0x1400bb7ad  call    sub_1400BBFC0
0x1400bb7b2  mov     rbx, rax
0x1400bb7b5  mov     [rbp+0B0h+var_68], rax
0x1400bb7b9  mov     [rbp+0B0h+var_60], rax
0x1400bb7bd  mov     [rbp+0B0h+var_58], r12
0x1400bb7c1  mov     r14b, 1
0x1400bb7c4  mov     [rbp+0B0h+var_50], 1
0x1400bb7cb  lea     rcx, [rbp+0B0h+var_70]
0x1400bb7cf  call    sub_1400BC164
0x1400bb7d4  nop
0x1400bb7d5  test    rbx, rbx
0x1400bb7d8  jz      short loc_1400BB7F1
0x1400bb7da  xor     edx, edx
0x1400bb7dc  lea     rcx, [rbp+0B0h+var_70]
0x1400bb7e0  call    sub_1400BC230
0x1400bb7e5  mov     r14b, byte ptr [rbp+0B0h+var_50]
0x1400bb7e9  mov     rbx, [rbp+0B0h+var_68]
0x1400bb7ed  mov     rsi, [rbp+0B0h+var_70]
0x1400bb7f1  test    r14b, r14b
0x1400bb7f4  jz      short loc_1400BB802
0x1400bb7f6  mov     rdx, rbx
0x1400bb7f9  mov     rcx, rsi
0x1400bb7fc  call    sub_1400BC1B4
0x1400bb801  nop
0x1400bb802  mov     rsi, [rdi+70h]
0x1400bb806  mov     [rbp+0B0h+var_70], rsi
0x1400bb80a  lea     rdx, aPragmaSynchron; "PRAGMA synchronous=NORMAL"
0x1400bb811  mov     rcx, rsi; _Mtx_t
0x1400bb814  call    sub_1400BBFC0
0x1400bb819  mov     rbx, rax
0x1400bb81c  mov     [rbp+0B0h+var_68], rax
0x1400bb820  mov     [rbp+0B0h+var_60], rax
0x1400bb824  mov     [rbp+0B0h+var_58], r12
0x1400bb828  mov     r14b, 1
0x1400bb82b  mov     [rbp+0B0h+var_50], 1
0x1400bb832  lea     rcx, [rbp+0B0h+var_70]
0x1400bb836  call    sub_1400BC164
0x1400bb83b  nop
0x1400bb83c  test    rbx, rbx
0x1400bb83f  jz      short loc_1400BB858
0x1400bb841  xor     edx, edx
0x1400bb843  lea     rcx, [rbp+0B0h+var_70]
0x1400bb847  call    sub_1400BC230
0x1400bb84c  mov     r14b, byte ptr [rbp+0B0h+var_50]
0x1400bb850  mov     rbx, [rbp+0B0h+var_68]
0x1400bb854  mov     rsi, [rbp+0B0h+var_70]
0x1400bb858  test    r14b, r14b
0x1400bb85b  jz      short loc_1400BB869
0x1400bb85d  mov     rdx, rbx
0x1400bb860  mov     rcx, rsi
0x1400bb863  call    sub_1400BC1B4
0x1400bb868  nop
0x1400bb869  lea     rcx, [rsp+1B0h+var_160]
0x1400bb86e  call    sub_1400BCBC0
0x1400bb873  nop
0x1400bb874  lea     rdx, aPragmaTempStor; "PRAGMA temp_store_directory = '"
0x1400bb87b  lea     rcx, [rsp+1B0h+var_160]
0x1400bb880  call    sub_1400BB178
0x1400bb885  mov     rbx, rax
0x1400bb888  lea     rcx, [rbp+0B0h+var_48]
0x1400bb88c  call    sub_1400BD4C4
0x1400bb891  nop
0x1400bb892  mov     rdx, rax
0x1400bb895  mov     rcx, rbx
0x1400bb898  call    unknown_libname_8; Microsoft VisualC v14 64bit runtime
0x1400bb89d  mov     rcx, rax
0x1400bb8a0  lea     rdx, dword_14083971C
0x1400bb8a7  call    sub_1400BB178
0x1400bb8ac  nop
0x1400bb8ad  mov     rdx, [rbp+0B0h+var_30]
0x1400bb8b4  cmp     rdx, 0Fh
0x1400bb8b8  jbe     short loc_1400BB8C6
0x1400bb8ba  inc     rdx
0x1400bb8bd  mov     rcx, qword ptr [rbp+0B0h+var_48]
0x1400bb8c1  call    sub_14001E270
0x1400bb8c6  lea     rdx, [rbp+0B0h+var_48]
0x1400bb8ca  lea     rcx, [rsp+1B0h+var_158]
0x1400bb8cf  call    sub_1400BCE24
0x1400bb8d4  nop
0x1400bb8d5  lea     rdx, [rbp+0B0h+var_48]
0x1400bb8d9  cmp     [rbp+0B0h+var_30], 0Fh
0x1400bb8e1  cmova   rdx, qword ptr [rbp+0B0h+var_48]
0x1400bb8e6  mov     rsi, [rdi+70h]
0x1400bb8ea  mov     [rbp+0B0h+var_70], rsi
0x1400bb8ee  mov     rcx, rsi; _Mtx_t
0x1400bb8f1  call    sub_1400BBFC0
0x1400bb8f6  mov     rbx, rax
0x1400bb8f9  mov     [rbp+0B0h+var_68], rax
0x1400bb8fd  mov     [rbp+0B0h+var_60], rax
0x1400bb901  mov     [rbp+0B0h+var_58], r12
0x1400bb905  mov     r14b, 1
0x1400bb908  mov     [rbp+0B0h+var_50], 1
0x1400bb90f  lea     rcx, [rbp+0B0h+var_70]
0x1400bb913  call    sub_1400BC164
0x1400bb918  nop
0x1400bb919  test    rbx, rbx
0x1400bb91c  jz      short loc_1400BB935
0x1400bb91e  xor     edx, edx
0x1400bb920  lea     rcx, [rbp+0B0h+var_70]
0x1400bb924  call    sub_1400BC230
0x1400bb929  mov     r14b, byte ptr [rbp+0B0h+var_50]
0x1400bb92d  mov     rbx, [rbp+0B0h+var_68]
0x1400bb931  mov     rsi, [rbp+0B0h+var_70]
0x1400bb935  test    r14b, r14b
0x1400bb938  jz      short loc_1400BB946
0x1400bb93a  mov     rdx, rbx
0x1400bb93d  mov     rcx, rsi
0x1400bb940  call    sub_1400BC1B4
0x1400bb945  nop
0x1400bb946  mov     rdx, [rbp+0B0h+var_30]
0x1400bb94d  cmp     rdx, 0Fh
0x1400bb951  jbe     short loc_1400BB960
0x1400bb953  inc     rdx
0x1400bb956  mov     rcx, qword ptr [rbp+0B0h+var_48]
0x1400bb95a  call    sub_14001E270
0x1400bb95f  nop
0x1400bb960  lea     rcx, [rbp+0B0h+var_D8]
0x1400bb964  call    sub_1400BCC90
0x1400bb969  lea     rcx, [rbp+0B0h+var_D8]
0x1400bb96d  call    cs:??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x1400bb973  mov     rcx, [rdi+70h]; _Mtx_t
0x1400bb977  mov     [rbp+0B0h+var_70], rcx
0x1400bb97b  lea     rdx, aPragmaUserVers; "PRAGMA user_version"
0x1400bb982  call    sub_1400BBFC0
0x1400bb987  mov     rbx, rax
0x1400bb98a  mov     [rbp+0B0h+var_68], rax
0x1400bb98e  mov     rsi, rax
0x1400bb991  mov     [rbp+0B0h+var_60], rax
0x1400bb995  mov     [rbp+0B0h+var_58], r12
0x1400bb999  mov     [rbp+0B0h+var_50], 1
0x1400bb9a0  lea     rcx, [rbp+0B0h+var_70]
0x1400bb9a4  call    sub_1400BC164
0x1400bb9a9  nop
0x1400bb9aa  test    rbx, rbx
0x1400bb9ad  jz      short loc_1400BB9E3
0x1400bb9af  xor     edx, edx
0x1400bb9b1  lea     rcx, [rbp+0B0h+var_70]
0x1400bb9b5  call    sub_1400BC230
0x1400bb9ba  mov     rsi, [rbp+0B0h+var_60]
0x1400bb9be  mov     rbx, [rbp+0B0h+var_68]
0x1400bb9c2  test    al, al
0x1400bb9c4  jz      short loc_1400BB9CB
0x1400bb9c6  test    rsi, rsi
0x1400bb9c9  jnz     short loc_1400BB9E8
0x1400bb9cb  cmp     byte ptr [rbp+0B0h+var_50], r12b
0x1400bb9cf  jz      short loc_1400BB9DE
0x1400bb9d1  mov     rdx, rbx
0x1400bb9d4  mov     rcx, [rbp+0B0h+var_70]
0x1400bb9d8  call    sub_1400BC1B4
0x1400bb9dd  nop
0x1400bb9de  jmp     loc_1400BBECC
0x1400bb9e3  mov     al, r12b
0x1400bb9e6  jmp     short loc_1400BB9C2
0x1400bb9e8  lea     rcx, [rbp+0B0h+var_70]
0x1400bb9ec  call    sub_1402621D4
0x1400bb9f1  test    al, al
0x1400bb9f3  jnz     short loc_1400BB9FB
0x1400bb9f5  mov     rbx, [rbp+0B0h+var_68]
0x1400bb9f9  jmp     short loc_1400BB9CB
0x1400bb9fb  mov     rax, cs:off_140BEACF8
0x1400bba02  xor     r8d, r8d
0x1400bba05  mov     rdx, [rbp+0B0h+var_60]
0x1400bba09  lea     rcx, off_140BEACF8
0x1400bba10  mov     rax, [rax+58h]
0x1400bba14  call    cs:__guard_dispatch_icall_fptr
0x1400bba1a  mov     ebx, eax
0x1400bba1c  cmp     byte ptr [rbp+0B0h+var_50], r12b
0x1400bba20  jz      short loc_1400BBA30
0x1400bba22  mov     rdx, [rbp+0B0h+var_68]
0x1400bba26  mov     rcx, [rbp+0B0h+var_70]
0x1400bba2a  call    sub_1400BC1B4
0x1400bba2f  nop
0x1400bba30  cmp     ebx, 1
0x1400bba33  jnz     loc_1400BBEC8
0x1400bba39  mov     rsi, [rdi+70h]
0x1400bba3d  mov     [rbp+0B0h+var_70], rsi
0x1400bba41  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS events (reco"...
0x1400bba48  mov     rcx, rsi; _Mtx_t
0x1400bba4b  call    sub_1400BBFC0
0x1400bba50  mov     rbx, rax
0x1400bba53  mov     [rbp+0B0h+var_68], rax
0x1400bba57  mov     [rbp+0B0h+var_60], rax
0x1400bba5b  mov     [rbp+0B0h+var_58], r12
0x1400bba5f  mov     r14b, 1
0x1400bba62  mov     [rbp+0B0h+var_50], 1
0x1400bba69  lea     rcx, [rbp+0B0h+var_70]
0x1400bba6d  call    sub_1400BC164
0x1400bba72  nop
0x1400bba73  test    rbx, rbx
0x1400bba76  jz      loc_1400BBEA8
0x1400bba7c  xor     edx, edx
0x1400bba7e  lea     rcx, [rbp+0B0h+var_70]
0x1400bba82  call    sub_1400BCAE0
0x1400bba87  mov     r15b, al
0x1400bba8a  mov     r14b, byte ptr [rbp+0B0h+var_50]
0x1400bba8e  mov     rbx, [rbp+0B0h+var_68]
0x1400bba92  mov     rsi, [rbp+0B0h+var_70]
0x1400bba96  test    r14b, r14b
0x1400bba99  jz      short loc_1400BBAA7
0x1400bba9b  mov     rdx, rbx
0x1400bba9e  mov     rcx, rsi
0x1400bbaa1  call    sub_1400BC1B4
0x1400bbaa6  nop
0x1400bbaa7  test    r15b, r15b
0x1400bbaaa  jz      loc_1400BBECC
0x1400bbab0  mov     rsi, [rdi+70h]
0x1400bbab4  mov     [rbp+0B0h+var_70], rsi
0x1400bbab8  lea     rdx, aCreateIndexIfN; "CREATE INDEX IF NOT EXISTS k_latency_ti"...
0x1400bbabf  mov     rcx, rsi; _Mtx_t
0x1400bbac2  call    sub_1400BBFC0
0x1400bbac7  mov     rbx, rax
0x1400bbaca  mov     [rbp+0B0h+var_68], rax
0x1400bbace  mov     [rbp+0B0h+var_60], rax
0x1400bbad2  mov     [rbp+0B0h+var_58], r12
0x1400bbad6  mov     r14b, 1
0x1400bbad9  mov     [rbp+0B0h+var_50], 1
0x1400bbae0  lea     rcx, [rbp+0B0h+var_70]
0x1400bbae4  call    sub_1400BC164
0x1400bbae9  nop
0x1400bbaea  test    rbx, rbx
0x1400bbaed  jz      loc_1400BBEB0
0x1400bbaf3  xor     edx, edx
0x1400bbaf5  lea     rcx, [rbp+0B0h+var_70]
0x1400bbaf9  call    sub_1400BCAE0
0x1400bbafe  mov     r15b, al
0x1400bbb01  mov     r14b, byte ptr [rbp+0B0h+var_50]
0x1400bbb05  mov     rbx, [rbp+0B0h+var_68]
0x1400bbb09  mov     rsi, [rbp+0B0h+var_70]
0x1400bbb0d  test    r14b, r14b
0x1400bbb10  jz      short loc_1400BBB1E
0x1400bbb12  mov     rdx, rbx
0x1400bbb15  mov     rcx, rsi
0x1400bbb18  call    sub_1400BC1B4
0x1400bbb1d  nop
0x1400bbb1e  test    r15b, r15b
0x1400bbb21  jz      loc_1400BBECC
0x1400bbb27  mov     rsi, [rdi+70h]
0x1400bbb2b  mov     [rbp+0B0h+var_70], rsi
0x1400bbb2f  lea     rdx, aCreateTableIfN_0; "CREATE TABLE IF NOT EXISTS settings (na"...
0x1400bbb36  mov     rcx, rsi; _Mtx_t
0x1400bbb39  call    sub_1400BBFC0
0x1400bbb3e  mov     rbx, rax
0x1400bbb41  mov     [rbp+0B0h+var_68], rax
0x1400bbb45  mov     [rbp+0B0h+var_60], rax
0x1400bbb49  mov     [rbp+0B0h+var_58], r12
0x1400bbb4d  mov     r14b, 1
0x1400bbb50  mov     [rbp+0B0h+var_50], 1
0x1400bbb57  lea     rcx, [rbp+0B0h+var_70]
0x1400bbb5b  call    sub_1400BC164
0x1400bbb60  nop
0x1400bbb61  test    rbx, rbx
0x1400bbb64  jz      loc_1400BBEB8
0x1400bbb6a  xor     edx, edx
0x1400bbb6c  lea     rcx, [rbp+0B0h+var_70]
  ... truncated ...
```
