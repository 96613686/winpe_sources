# ESESession::EnsureIndexInfoTable(void)

- ea: `0x18001706c`
- end: `0x1800173bd`
- name: `?EnsureIndexInfoTable@ESESession@@QEAAJXZ`
- size: `849`
- prototype: `__int64 __fastcall(ESESession *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x180011f70`
- `0x180013768`
- `0x18001626c`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180010638`
- `0x180016860`
- `0x18001706c`
- `0x180017a34`
- `0x180017d74`
- `0x1800183b4`
- `0x180021240`

## import_xrefs

- `ESENT!JetCreateTableA` at `0x18001712c`
- `ESENT!JetCreateTableA` at `0x18001712c`
- `ESENT!JetGetTableColumnInfoA` at `0x1800172eb`
- `ESENT!JetGetTableColumnInfoA` at `0x1800172eb`
- `ESENT!JetAddColumnA` at `0x1800171d4`
- `ESENT!JetAddColumnA` at `0x1800171d4`
- `ESENT!JetOpenTableA` at `0x1800170ff`
- `ESENT!JetOpenTableA` at `0x180017241`
- `ESENT!JetOpenTableA` at `0x1800170ff`
- `ESENT!JetOpenTableA` at `0x180017241`
- `ESENT!JetCloseTable` at `0x1800171f8`
- `ESENT!JetCloseTable` at `0x1800171f8`

## string_xrefs

- `0x18001720b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180017271`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x18001729e`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x18001730c`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::EnsureIndexInfoTable(ESESession *this)
{
  int HresultFromJetError; // eax
  unsigned int v3; // edi
  __int64 v4; // r9
  __int64 v5; // rdx
  JET_TABLEID *v6; // rdi
  JET_ERR v7; // eax
  JET_ERR TableA; // eax
  __int64 j; // rsi
  JET_TABLEID v10; // rdx
  __int64 v11; // r8
  JET_GRBIT v12; // eax
  const char *v13; // r8
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  unsigned int v16; // eax
  JET_ERR v17; // eax
  __int64 v18; // rcx
  __int64 i; // rsi
  JET_TABLEID v20; // rdx
  JET_SESID v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  int v25; // [rsp+40h] [rbp-49h] BYREF
  __int64 v26; // [rsp+48h] [rbp-41h] BYREF
  int v27; // [rsp+50h] [rbp-39h]
  char *v28; // [rsp+58h] [rbp-31h]
  JET_COLUMNDEF pcolumndef; // [rsp+60h] [rbp-29h] BYREF
  _DWORD pvResult[8]; // [rsp+80h] [rbp-9h] BYREF

  v26 = *((_QWORD *)this + 7);
  v28 = (char *)this + 64;
  v27 = 0;
  HresultFromJetError = auto_SessionContext::SetContext((auto_SessionContext *)&v26);
  v3 = HresultFromJetError;
  if ( HresultFromJetError < 0 )
  {
    v4 = 936;
LABEL_3:
    v5 = 1;
    goto LABEL_18;
  }
  v6 = (JET_TABLEID *)((char *)this + 40);
  if ( *((_QWORD *)this + 5) != -1 )
  {
LABEL_39:
    v3 = 0;
    goto LABEL_40;
  }
  v7 = JetOpenTableA(*((_QWORD *)this + 7), *((_DWORD *)this + 6), "IndexingInfo", 0, 0, 0, (JET_TABLEID *)this + 5);
  if ( v7 != -1305 )
  {
    *((_QWORD *)this + 4) = *((_QWORD *)this + 7);
    if ( v7 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v7);
      v4 = 1011;
      goto LABEL_17;
    }
    if ( *v6 == -1 )
      Log_AssertionEvent(
        (unsigned int)v7,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        1013);
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      v20 = *v6;
      v21 = *((_QWORD *)this + 7);
      memset(pvResult, 0, 28);
      if ( JetGetTableColumnInfoA(v21, v20, (&off_180023CE8)[4 * (unsigned int)i], pvResult, 0x1Cu, 0) == -1507 )
      {
        v4 = 1037;
LABEL_30:
        v3 = -2147221202;
        v5 = 0;
        v18 = 2147746094LL;
        goto LABEL_19;
      }
      v23 = pvResult[1];
      *((_DWORD *)this + i + 86) = pvResult[1];
      if ( !v23 )
        Log_AssertionEvent(
          v22,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
          1041);
    }
    v25 = 0;
    HresultFromJetError = ESESession::HasOSVersionChanged(this, &v25);
    v3 = HresultFromJetError;
    if ( HresultFromJetError < 0 )
    {
      v4 = 1047;
      goto LABEL_3;
    }
    if ( v25 )
    {
      v4 = 1052;
      goto LABEL_30;
    }
LABEL_35:
    if ( *((_DWORD *)this + 89) )
    {
      HresultFromJetError = ESESession::WriteOSVersion(this);
      v3 = HresultFromJetError;
      if ( HresultFromJetError < 0 )
      {
        v4 = 1061;
        goto LABEL_3;
      }
    }
    goto LABEL_39;
  }
  TableA = JetCreateTableA(*((_QWORD *)this + 7), *((_DWORD *)this + 6), "IndexingInfo", 0, 0, (JET_TABLEID *)this + 5);
  if ( TableA < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(TableA);
    v4 = 962;
    goto LABEL_17;
  }
  *((_QWORD *)this + 4) = *((_QWORD *)this + 7);
  memset(&pcolumndef, 0, sizeof(pcolumndef));
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    v10 = *v6;
    if ( (unsigned int)j >= 2 )
      break;
    v11 = 4LL * (unsigned int)j;
    *(_QWORD *)&pcolumndef.cbStruct = 28;
    pcolumndef.coltyp = qword_180023CF0[v11];
    *(_QWORD *)&pcolumndef.wCountry = 0;
    pcolumndef.cbMax = HIDWORD(qword_180023CF0[v11]);
    v12 = qword_180023CF0[v11 + 1];
    v13 = (&off_180023CE8)[v11];
    pcolumndef.grbit = v12;
    v14 = JetAddColumnA(
            *((_QWORD *)this + 7),
            v10,
            v13,
            &pcolumndef,
            &dword_18002D304[2 * j],
            *((_DWORD *)&gc_pimIMIndex_IndexInfoDefaultValues + 2 * j),
            (JET_COLUMNID *)this + j + 86);
    if ( v14 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v14);
      v4 = 992;
      goto LABEL_17;
    }
  }
  v15 = JetCloseTable(*((_QWORD *)this + 7), v10);
  if ( v15 < 0 )
  {
    v16 = MakeHresultFromJetError(v15);
    Log_HREvent(
      v16,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      996);
  }
  v17 = JetOpenTableA(
          *((_QWORD *)this + 7),
          *((_DWORD *)this + 6),
          "IndexingInfo",
          0,
          0,
          0x10000u,
          (JET_TABLEID *)this + 5);
  if ( v17 >= 0 )
    goto LABEL_35;
  HresultFromJetError = MakeHresultFromJetError(v17);
  v4 = 1006;
LABEL_17:
  v3 = HresultFromJetError;
  v5 = 0;
LABEL_18:
  v18 = (unsigned int)HresultFromJetError;
LABEL_19:
  Log_HREvent(
    v18,
    v5,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    v4);
LABEL_40:
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v26);
  return v3;
}

```

## disassembly

```asm
0x18001706c  push    rbp
0x18001706e  push    rbx
0x18001706f  push    rsi
0x180017070  push    rdi
0x180017071  push    r14
0x180017073  push    r15
0x180017075  lea     rbp, [rsp-2Fh]
0x18001707a  sub     rsp, 0B8h
0x180017081  mov     rax, cs:__security_cookie
0x180017088  xor     rax, rsp
0x18001708b  mov     [rbp+57h+var_40], rax
0x18001708f  mov     rax, [rcx+38h]
0x180017093  mov     rbx, rcx
0x180017096  mov     [rbp+57h+var_98], rax
0x18001709a  lea     rax, [rcx+40h]
0x18001709e  lea     rcx, [rbp+57h+var_98]; this
0x1800170a2  mov     [rbp+57h+var_88], rax
0x1800170a6  mov     [rbp+57h+var_90], 0
0x1800170ad  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x1800170b2  mov     edi, eax
0x1800170b4  test    eax, eax
0x1800170b6  jns     short loc_1800170C8
0x1800170b8  mov     r9d, 3A8h
0x1800170be  mov     edx, 1
0x1800170c3  jmp     loc_18001726F
0x1800170c8  lea     rdi, [rbx+28h]
0x1800170cc  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800170d0  jnz     loc_180017394
0x1800170d6  mov     edx, [rbx+18h]; dbid
0x1800170d9  lea     r15, szTableName; "IndexingInfo"
0x1800170e0  mov     rcx, [rbx+38h]; sesid
0x1800170e4  mov     r8, r15; szTableName
0x1800170e7  mov     [rsp+0E0h+ptableid], rdi; ptableid
0x1800170ec  xor     r9d, r9d; pvParameters
0x1800170ef  mov     [rsp+0E0h+grbit], 0; grbit
0x1800170f7  mov     [rsp+0E0h+cbParameters], 0; cbParameters
0x1800170ff  call    cs:__imp_JetOpenTableA
0x180017105  mov     ecx, eax; int
0x180017107  cmp     eax, 0FFFFFAE7h
0x18001710c  jnz     loc_180017282
0x180017112  mov     edx, [rbx+18h]; dbid
0x180017115  xor     r9d, r9d; lPages
0x180017118  mov     rcx, [rbx+38h]; sesid
0x18001711c  mov     r8, r15; szTableName
0x18001711f  mov     qword ptr [rsp+0E0h+grbit], rdi; ptableid
0x180017124  mov     [rsp+0E0h+cbParameters], 0; lDensity
0x18001712c  call    cs:__imp_JetCreateTableA
0x180017132  test    eax, eax
0x180017134  js      loc_18001725E
0x18001713a  mov     rax, [rbx+38h]
0x18001713e  lea     r14, __ImageBase
0x180017145  xorps   xmm0, xmm0
0x180017148  mov     [rbx+20h], rax
0x18001714c  movups  xmmword ptr [rbp+57h+pcolumndef.cbStruct], xmm0
0x180017150  xor     esi, esi
0x180017152  movups  xmmword ptr [rbp+57h+pcolumndef.wCountry], xmm0
0x180017156  mov     rdx, [rdi]; tableid
0x180017159  cmp     esi, 2
0x18001715c  jnb     loc_1800171F4
0x180017162  mov     r8d, esi
0x180017165  lea     rcx, rva dword_18002D304[r14]
0x18001716c  shl     r8, 5
0x180017170  lea     rcx, [rcx+rsi*8]
0x180017174  lea     r9, [rbp+57h+pcolumndef]; pcolumndef
0x180017178  mov     qword ptr [rbp+57h+pcolumndef.cbStruct], 1Ch
0x180017180  mov     eax, [r8+r14+23CF0h]
0x180017188  mov     [rbp+57h+pcolumndef.coltyp], eax
0x18001718b  xor     eax, eax
0x18001718d  mov     qword ptr [rbp+57h+pcolumndef.wCountry], rax
0x180017191  mov     eax, [r8+r14+23CF4h]
0x180017199  mov     [rbp+57h+pcolumndef.cbMax], eax
0x18001719c  mov     eax, [r8+r14+23CF8h]
0x1800171a4  mov     r8, [r8+r14+23CE8h]; szColumnName
0x1800171ac  mov     [rbp+57h+pcolumndef.grbit], eax
0x1800171af  lea     rax, [rbx+158h]
0x1800171b6  lea     rax, [rax+rsi*4]
0x1800171ba  mov     [rsp+0E0h+ptableid], rax; pcolumnid
0x1800171bf  mov     eax, rva ?gc_pimIMIndex_IndexInfoDefaultValues@@3QBUIndexInfoDefaultValue@@B[r14+rsi*8]; IndexInfoDefaultValue const near * const gc_pimIMIndex_IndexInfoDefaultValues ...
0x1800171c7  mov     [rsp+0E0h+grbit], eax; cbDefault
0x1800171cb  mov     qword ptr [rsp+0E0h+cbParameters], rcx; pvDefault
0x1800171d0  mov     rcx, [rbx+38h]; sesid
0x1800171d4  call    cs:__imp_JetAddColumnA
0x1800171da  test    eax, eax
0x1800171dc  js      short loc_1800171E5
0x1800171de  inc     esi
0x1800171e0  jmp     loc_180017156
0x1800171e5  mov     ecx, eax; int
0x1800171e7  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800171ec  mov     r9d, 3E0h
0x1800171f2  jmp     short loc_18001726B
0x1800171f4  mov     rcx, [rbx+38h]; sesid
0x1800171f8  call    cs:__imp_JetCloseTable
0x1800171fe  test    eax, eax
0x180017200  jns     short loc_18001721F
0x180017202  mov     ecx, eax; int
0x180017204  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017209  mov     ecx, eax
0x18001720b  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017212  mov     r9d, 3E4h
0x180017218  xor     edx, edx
0x18001721a  call    Log_HREvent
0x18001721f  mov     edx, [rbx+18h]; dbid
0x180017222  xor     r9d, r9d; pvParameters
0x180017225  mov     rcx, [rbx+38h]; sesid
0x180017229  mov     r8, r15; szTableName
0x18001722c  mov     [rsp+0E0h+ptableid], rdi; ptableid
0x180017231  mov     [rsp+0E0h+grbit], 10000h; grbit
0x180017239  mov     [rsp+0E0h+cbParameters], 0; cbParameters
0x180017241  call    cs:__imp_JetOpenTableA
0x180017247  test    eax, eax
0x180017249  jns     loc_180017362
0x18001724f  mov     ecx, eax; int
0x180017251  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017256  mov     r9d, 3EEh
0x18001725c  jmp     short loc_18001726B
0x18001725e  mov     ecx, eax; int
0x180017260  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017265  mov     r9d, 3C2h
0x18001726b  mov     edi, eax
0x18001726d  xor     edx, edx
0x18001726f  mov     ecx, eax
0x180017271  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017278  call    Log_HREvent
0x18001727d  jmp     loc_180017396
0x180017282  mov     rax, [rbx+38h]
0x180017286  mov     [rbx+20h], rax
0x18001728a  test    ecx, ecx
0x18001728c  js      loc_180017384
0x180017292  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180017296  jnz     short loc_1800172AA
0x180017298  mov     r8d, 3F5h
0x18001729e  lea     rdx, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800172a5  call    Log_AssertionEvent
0x1800172aa  xor     esi, esi
0x1800172ac  lea     r14, __ImageBase
0x1800172b3  cmp     esi, 2
0x1800172b6  jnb     short loc_180017330
0x1800172b8  mov     rdx, [rdi]; tableid
0x1800172bb  lea     r9, [rbp+57h+pvResult]; pvResult
0x1800172bf  mov     rcx, [rbx+38h]; sesid
0x1800172c3  xorps   xmm0, xmm0
0x1800172c6  xor     eax, eax
0x1800172c8  mov     r8d, esi
0x1800172cb  shl     r8, 5
0x1800172cf  movups  xmmword ptr [rbp+57h+pvResult], xmm0
0x1800172d3  mov     [rsp+0E0h+grbit], eax; InfoLevel
0x1800172d7  movups  xmmword ptr [rbp+57h+pvResult+0Ch], xmm0
0x1800172db  mov     r8, [r8+r14+23CE8h]; szColumnName
0x1800172e3  mov     [rsp+0E0h+cbParameters], 1Ch; cbMax
0x1800172eb  call    cs:__imp_JetGetTableColumnInfoA
0x1800172f1  cmp     eax, 0FFFFFA1Dh
0x1800172f6  jz      short loc_18001731C
0x1800172f8  mov     eax, [rbp+57h+pvResult+4]
0x1800172fb  mov     [rbx+rsi*4+158h], eax
0x180017302  test    eax, eax
0x180017304  jnz     short loc_180017318
0x180017306  mov     r8d, 411h
0x18001730c  lea     rdx, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017313  call    Log_AssertionEvent
0x180017318  inc     esi
0x18001731a  jmp     short loc_1800172B3
0x18001731c  mov     r9d, 40Dh
0x180017322  mov     edi, 8004012Eh
0x180017327  xor     edx, edx
0x180017329  mov     ecx, edi
0x18001732b  jmp     loc_180017271
0x180017330  lea     rdx, [rbp+57h+var_A0]; int *
0x180017334  mov     [rbp+57h+var_A0], 0
0x18001733b  mov     rcx, rbx; this
0x18001733e  call    ?HasOSVersionChanged@ESESession@@QEAAJPEAH@Z; ESESession::HasOSVersionChanged(int *)
0x180017343  mov     edi, eax
0x180017345  test    eax, eax
0x180017347  jns     short loc_180017354
0x180017349  mov     r9d, 417h
0x18001734f  jmp     loc_1800170BE
0x180017354  cmp     [rbp+57h+var_A0], 0
0x180017358  jz      short loc_180017362
0x18001735a  mov     r9d, 41Ch
0x180017360  jmp     short loc_180017322
0x180017362  cmp     dword ptr [rbx+164h], 0
0x180017369  jz      short loc_180017394
0x18001736b  mov     rcx, rbx; this
0x18001736e  call    ?WriteOSVersion@ESESession@@QEAAJXZ; ESESession::WriteOSVersion(void)
0x180017373  mov     edi, eax
0x180017375  test    eax, eax
0x180017377  jns     short loc_180017394
0x180017379  mov     r9d, 425h
0x18001737f  jmp     loc_1800170BE
0x180017384  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017389  mov     r9d, 3F3h
0x18001738f  jmp     loc_18001726B
0x180017394  xor     edi, edi
0x180017396  lea     rcx, [rbp+57h+var_98]; this
0x18001739a  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x18001739f  mov     eax, edi
0x1800173a1  mov     rcx, [rbp+57h+var_40]
0x1800173a5  xor     rcx, rsp; StackCookie
0x1800173a8  call    __security_check_cookie
0x1800173ad  add     rsp, 0B8h
0x1800173b4  pop     r15
0x1800173b6  pop     r14
0x1800173b8  pop     rdi
0x1800173b9  pop     rsi
0x1800173ba  pop     rbx
0x1800173bb  pop     rbp
0x1800173bc  retn
```
