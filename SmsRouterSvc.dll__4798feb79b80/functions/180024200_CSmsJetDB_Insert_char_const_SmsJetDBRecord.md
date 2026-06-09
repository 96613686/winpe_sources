# CSmsJetDB::Insert(char const *,SmsJetDBRecord *)

- ea: `0x180024200`
- end: `0x1800245f7`
- name: `?Insert@CSmsJetDB@@QEAAJPEBDPEAVSmsJetDBRecord@@@Z`
- size: `1015`
- prototype: `__int64 __fastcall(CSmsJetDB *__hidden this, const char *, struct SmsJetDBRecord *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001bbbc`
- `0x18001eec0`
- `0x18001f194`
- `0x18001f378`

## callees

- `0x180003a60`
- `0x18000b07c`
- `0x18000ba3c`
- `0x18000e7ac`
- `0x180021bb0`
- `0x180022678`
- `0x180022d04`
- `0x1800235f0`
- `0x180023a58`
- `0x180023f9c`
- `0x180024200`
- `0x180025844`
- `0x1800261a0`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180024274`
- `ESENT!JetPrepareUpdate` at `0x180024274`
- `ESENT!JetGotoBookmark` at `0x1800244e1`
- `ESENT!JetGotoBookmark` at `0x1800244e1`
- `ESENT!JetSetColumns` at `0x180024488`
- `ESENT!JetSetColumns` at `0x180024488`
- `ESENT!JetUpdate` at `0x1800244c5`
- `ESENT!JetUpdate` at `0x1800244c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSmsJetDB::Insert(JET_SESID *this, const char *a2, struct SmsJetDBRecord *a3)
{
  struct SmsJetDBRecord *v3; // r13
  unsigned int TableIndex; // eax
  unsigned int v6; // r12d
  unsigned __int64 v8; // rdi
  JET_TABLEID v9; // r15
  JET_ERR v10; // ecx
  unsigned int v11; // ebx
  unsigned int v12; // r14d
  JET_SESID v13; // rdx
  unsigned __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // r15
  __int64 v17; // r12
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r13
  __int64 v21; // rdx
  JET_SETCOLUMN *v22; // rdx
  JET_ERR v23; // eax
  JET_ERR v24; // ecx
  unsigned int v25; // r14d
  __int64 v26; // rdx
  int v27; // eax
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int cbBookmark; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v30; // [rsp+38h] [rbp-C8h]
  _BYTE v31[40]; // [rsp+40h] [rbp-C0h] BYREF
  JET_SETCOLUMN *psetcolumn[2]; // [rsp+68h] [rbp-98h] BYREF
  JET_SETCOLUMN *v33; // [rsp+78h] [rbp-88h]
  SmsJetDBRecord *v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+98h] [rbp-68h]
  JET_TABLEID v37; // [rsp+A0h] [rbp-60h]
  _QWORD v38[3]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE pvBookmark[2000]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = a3;
  v34 = a3;
  TableIndex = CSmsJetDB::GetTableIndex((CSmsJetDB *)this, a2);
  v6 = TableIndex;
  v30 = TableIndex;
  if ( TableIndex >= this[5] )
    return 2147943568LL;
  v8 = (unsigned __int64)TableIndex << 7;
  v9 = *(_QWORD *)(this[1] + v8 + 88);
  v37 = v9;
  v10 = JetPrepareUpdate(this[6], v9, 0);
  if ( v10 >= 0 )
  {
    *(_OWORD *)psetcolumn = 0;
    v33 = 0;
    v35 = 0;
    v36 = 0;
    cbBookmark = 0;
    std::vector<SmsJetDBValue>::vector<SmsJetDBValue>(
      v38,
      0x6DB6DB6DB6DB6DB7LL * ((__int64)(*(_QWORD *)(v8 + this[1] + 48) - *(_QWORD *)(v8 + this[1] + 40)) >> 3));
    v12 = 0;
    v28 = 0;
    v13 = this[1];
    v14 = v8 + 40;
    if ( 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*(_QWORD *)(v8 + v13 + 48) - *(_QWORD *)(v8 + v13 + 40)) >> 3) )
    {
      v15 = 0;
      v16 = v38[0];
      do
      {
        v17 = 56 * v15;
        v18 = *(_QWORD *)(v14 + v13);
        if ( (*(_DWORD *)(v18 + 56 * v15 + 44) & 0x10) != 0 )
        {
          if ( *((_QWORD *)&v35 + 1) == v36 )
          {
            std::vector<unsigned long>::_Emplace_reallocate<unsigned long>(&v35, *((_QWORD *)&v35 + 1), &v28);
            v12 = v28;
          }
          else
          {
            **((_DWORD **)&v35 + 1) = v12;
            *((_QWORD *)&v35 + 1) += 4LL;
          }
        }
        else
        {
          v19 = 32 * v15;
          v20 = v19 + v16;
          v21 = v17 + v18 + 8;
          if ( *(_QWORD *)(v21 + 24) > 0xFu )
            v21 = *(_QWORD *)v21;
          if ( (unsigned int)SmsJetDBRecord::GetFieldValue(v34, (const char *)v21, (struct SmsJetDBValue *)(v19 + v16)) )
          {
            *(_DWORD *)&v31[4] = 0;
            memset(&v31[20], 0, 20);
            *(_DWORD *)v31 = *(_DWORD *)(*(_QWORD *)(v8 + this[1] + 40) + v17 + 48);
            *(_QWORD *)&v31[8] = *(_QWORD *)(v20 + 8);
            *(_DWORD *)&v31[16] = *(_DWORD *)(v20 + 16) - *(_DWORD *)&v31[8];
            v22 = psetcolumn[1];
            if ( psetcolumn[1] == v33 )
            {
              std::vector<JET_SETCOLUMN>::_Emplace_reallocate<JET_SETCOLUMN const &>(psetcolumn, psetcolumn[1], v31);
            }
            else
            {
              *(_OWORD *)psetcolumn[1] = *(_OWORD *)v31;
              *(_OWORD *)&v22->cbData = *(_OWORD *)&v31[16];
              *(_QWORD *)&v22->err = *(_QWORD *)&v31[32];
              ++psetcolumn[1];
            }
          }
        }
        v28 = ++v12;
        v15 = v12;
        v13 = this[1];
      }
      while ( v12 < (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL
                                     * ((__int64)(*(_QWORD *)(v14 + v13 + 8) - *(_QWORD *)(v14 + v13)) >> 3)) );
      v9 = v37;
      v6 = v30;
      v3 = v34;
    }
    v23 = JetSetColumns(this[6], v9, psetcolumn[0], -858993459 * (((char *)psetcolumn[1] - (char *)psetcolumn[0]) >> 3));
    v24 = v23;
    if ( v23 < 0
      || (v23 = JetUpdate(this[6], v9, pvBookmark, 0x7D0u, &cbBookmark), v24 = v23, v23 < 0)
      || (v23 = JetGotoBookmark(this[6], v9, pvBookmark, cbBookmark), v24 = v23, v23 < 0) )
    {
      if ( v24 == -1011 )
      {
        v11 = -2147024882;
      }
      else
      {
        v27 = -v23;
        if ( v27 < 0 )
          LOWORD(v27) = v24;
        v11 = v24 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
      }
    }
    else
    {
      v25 = 0;
      if ( 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*(_QWORD *)(v8 + this[1] + 48) - *(_QWORD *)(v8 + this[1] + 40)) >> 3) )
      {
        do
        {
          memset(&v31[8], 0, 24);
          CSmsJetDB::GetColumnValue((CSmsJetDB *)this, v6, v25, (struct SmsJetDBValue *)v31);
          v26 = *(_QWORD *)(v14 + this[1]) + 8LL + 56LL * v25;
          if ( *(_QWORD *)(v26 + 24) > 0xFu )
            v26 = *(_QWORD *)v26;
          SmsJetDBRecord::SetFieldValue(v3, (const char *)v26, (struct SmsJetDBValue *)v31);
          std::vector<unsigned char>::~vector<unsigned char>((char **)&v31[8]);
          ++v25;
        }
        while ( v25 < (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL
                                       * ((__int64)(*(_QWORD *)(v14 + this[1] + 8) - *(_QWORD *)(v14 + this[1])) >> 3)) );
      }
      v11 = 0;
    }
    std::vector<SmsJetDBValue>::_Tidy(v38);
    std::vector<enum SMS_BROADCAST_TYPES>::~vector<enum SMS_BROADCAST_TYPES>(&v35);
    std::vector<JET_SETCOLUMN>::~vector<JET_SETCOLUMN>(psetcolumn);
  }
  else if ( v10 == -1011 )
  {
    return (unsigned int)-2147024882;
  }
  else
  {
    return v10 & 0x8E5E0000 | (unsigned __int16)-(__int16)v10 | 0xE5E0000;
  }
  return v11;
}

```

## disassembly

```asm
0x180024200  mov     [rsp-8+arg_18], rbx
0x180024205  push    rbp
0x180024206  push    rsi
0x180024207  push    rdi
0x180024208  push    r12
0x18002420a  push    r13
0x18002420c  push    r14
0x18002420e  push    r15
0x180024210  lea     rbp, [rsp-7A0h]
0x180024218  sub     rsp, 8A0h
0x18002421f  mov     rax, cs:__security_cookie
0x180024226  xor     rax, rsp
0x180024229  mov     [rbp+7D0h+var_40], rax
0x180024230  mov     r13, r8
0x180024233  mov     [rbp+7D0h+var_850], r8
0x180024237  mov     rbx, rcx
0x18002423a  call    ?GetTableIndex@CSmsJetDB@@AEAAKPEBD@Z; CSmsJetDB::GetTableIndex(char const *)
0x18002423f  mov     r12d, eax
0x180024242  mov     [rsp+8D0h+var_898], r12d
0x180024247  mov     edi, eax
0x180024249  cmp     r12, [rbx+28h]
0x18002424d  jb      short loc_180024259
0x18002424f  mov     eax, 80070490h
0x180024254  jmp     loc_1800245B4
0x180024259  shl     rdi, 7
0x18002425d  mov     rax, [rbx+8]
0x180024261  mov     r15, [rax+rdi+58h]
0x180024266  mov     [rbp+7D0h+var_830], r15
0x18002426a  xor     r8d, r8d; prep
0x18002426d  mov     rdx, r15; tableid
0x180024270  mov     rcx, [rbx+30h]; sesid
0x180024274  call    cs:__imp_JetPrepareUpdate
0x18002427a  mov     ecx, eax
0x18002427c  xor     eax, eax
0x18002427e  test    ecx, ecx
0x180024280  jns     short loc_1800242B1
0x180024282  cmp     ecx, 0FFFFFC0Dh
0x180024288  jnz     short loc_180024294
0x18002428a  mov     ebx, 8007000Eh
0x18002428f  jmp     loc_1800245B2
0x180024294  mov     eax, ecx
0x180024296  neg     eax
0x180024298  cmovs   eax, ecx
0x18002429b  movzx   ebx, ax
0x18002429e  and     ecx, 8E5E0000h
0x1800242a4  or      ebx, ecx
0x1800242a6  or      ebx, 0E5E0000h
0x1800242ac  jmp     loc_1800245B2
0x1800242b1  xorps   xmm0, xmm0
0x1800242b4  movdqu  xmmword ptr [rsp+8D0h+psetcolumn], xmm0
0x1800242ba  mov     [rsp+8D0h+var_858], rax
0x1800242bf  movdqu  [rbp+7D0h+var_848], xmm0
0x1800242c4  mov     [rbp+7D0h+var_838], rax
0x1800242c8  mov     [rsp+8D0h+cbBookmark], eax
0x1800242cc  mov     rax, [rbx+8]
0x1800242d0  mov     rdx, [rdi+rax+30h]
0x1800242d5  sub     rdx, [rdi+rax+28h]
0x1800242da  sar     rdx, 3
0x1800242de  mov     rax, 6DB6DB6DB6DB6DB7h
0x1800242e8  imul    rdx, rax
0x1800242ec  lea     rcx, [rbp+7D0h+var_828]
0x1800242f0  call    ??0?$vector@VSmsJetDBValue@@V?$allocator@VSmsJetDBValue@@@std@@@std@@QEAA@_KAEBV?$allocator@VSmsJetDBValue@@@1@@Z; std::vector<SmsJetDBValue>::vector<SmsJetDBValue>(unsigned __int64,std::allocator<SmsJetDBValue> const &)
0x1800242f5  nop
0x1800242f6  xor     r14d, r14d
0x1800242f9  mov     [rsp+8D0h+var_8A0], r14d
0x1800242fe  mov     rdx, [rbx+8]
0x180024302  lea     rsi, [rdi+28h]
0x180024306  mov     rax, [rdi+rdx+30h]
0x18002430b  sub     rax, [rdi+rdx+28h]
0x180024310  sar     rax, 3
0x180024314  mov     rcx, 6DB6DB6DB6DB6DB7h
0x18002431e  imul    rax, rcx
0x180024322  test    rax, rax
0x180024325  jz      loc_180024462
0x18002432b  xor     ecx, ecx
0x18002432d  mov     r15, [rbp+7D0h+var_828]
0x180024331  imul    r12, rcx, 38h ; '8'
0x180024335  mov     r8, [rsi+rdx]
0x180024339  mov     eax, [r8+r12+2Ch]
0x18002433e  test    al, 10h
0x180024340  jnz     loc_1800243FB
0x180024346  shl     rcx, 5
0x18002434a  lea     r13, [rcx+r15]
0x18002434e  lea     rdx, [r8+8]
0x180024352  add     rdx, r12
0x180024355  cmp     qword ptr [rdx+18h], 0Fh
0x18002435a  jbe     short loc_18002435F
0x18002435c  mov     rdx, [rdx]; char *
0x18002435f  mov     r8, r13; struct SmsJetDBValue *
0x180024362  mov     rcx, [rbp+7D0h+var_850]; this
0x180024366  call    ?GetFieldValue@SmsJetDBRecord@@QEAAHPEBDPEAVSmsJetDBValue@@@Z; SmsJetDBRecord::GetFieldValue(char const *,SmsJetDBValue *)
0x18002436b  test    eax, eax
0x18002436d  jz      loc_180024422
0x180024373  mov     dword ptr [rsp+8D0h+var_890+4], 0
0x18002437b  mov     qword ptr [rsp+8D0h+var_880+4], 0
0x180024384  mov     qword ptr [rsp+8D0h+var_880+0Ch], 0
0x18002438d  mov     [rsp+8D0h+var_86C], 0
0x180024395  mov     rax, [rbx+8]
0x180024399  mov     rcx, [rdi+rax+28h]
0x18002439e  mov     eax, [rcx+r12+30h]
0x1800243a3  mov     dword ptr [rsp+8D0h+var_890], eax
0x1800243a7  mov     rcx, [r13+8]
0x1800243ab  mov     qword ptr [rsp+8D0h+var_890+8], rcx
0x1800243b0  mov     eax, [r13+10h]
0x1800243b4  sub     eax, ecx
0x1800243b6  mov     dword ptr [rsp+8D0h+var_880], eax
0x1800243ba  mov     rdx, [rsp+8D0h+psetcolumn+8]
0x1800243bf  cmp     rdx, [rsp+8D0h+var_858]
0x1800243c4  jz      short loc_1800243EA
0x1800243c6  movups  xmm0, [rsp+8D0h+var_890]
0x1800243cb  movups  xmmword ptr [rdx], xmm0
0x1800243ce  movups  xmm1, xmmword ptr [rsp+8D0h+var_880]
0x1800243d3  movups  xmmword ptr [rdx+10h], xmm1
0x1800243d7  movsd   xmm0, qword ptr [rsp+60h]
0x1800243dd  movsd   qword ptr [rdx+20h], xmm0
0x1800243e2  add     [rsp+8D0h+psetcolumn+8], 28h ; '('
0x1800243e8  jmp     short loc_180024422
0x1800243ea  lea     r8, [rsp+8D0h+var_890]
0x1800243ef  lea     rcx, [rsp+8D0h+psetcolumn]
0x1800243f4  call    ??$_Emplace_reallocate@AEBUJET_SETCOLUMN@@@?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@std@@@std@@AEAAPEAUJET_SETCOLUMN@@QEAU2@AEBU2@@Z; std::vector<JET_SETCOLUMN>::_Emplace_reallocate<JET_SETCOLUMN const &>(JET_SETCOLUMN * const,JET_SETCOLUMN const &)
0x1800243f9  jmp     short loc_180024422
0x1800243fb  mov     rdx, qword ptr [rbp+7D0h+var_848+8]
0x1800243ff  cmp     rdx, [rbp+7D0h+var_838]
0x180024403  jz      short loc_18002440F
0x180024405  mov     [rdx], r14d
0x180024408  add     qword ptr [rbp+7D0h+var_848+8], 4
0x18002440d  jmp     short loc_180024422
0x18002440f  lea     r8, [rsp+8D0h+var_8A0]
0x180024414  lea     rcx, [rbp+7D0h+var_848]
0x180024418  call    ??$_Emplace_reallocate@K@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAK$$QEAK@Z; std::vector<ulong>::_Emplace_reallocate<ulong>(ulong * const,ulong &&)
0x18002441d  mov     r14d, [rsp+8D0h+var_8A0]
0x180024422  inc     r14d
0x180024425  mov     [rsp+8D0h+var_8A0], r14d
0x18002442a  mov     ecx, r14d
0x18002442d  mov     rdx, [rbx+8]
0x180024431  mov     rax, [rsi+rdx+8]
0x180024436  sub     rax, [rsi+rdx]
0x18002443a  sar     rax, 3
0x18002443e  mov     r8, 6DB6DB6DB6DB6DB7h
0x180024448  imul    rax, r8
0x18002444c  cmp     rcx, rax
0x18002444f  jb      loc_180024331
0x180024455  mov     r15, [rbp+7D0h+var_830]
0x180024459  mov     r12d, [rsp+8D0h+var_898]
0x18002445e  mov     r13, [rbp+7D0h+var_850]
0x180024462  mov     r9, [rsp+8D0h+psetcolumn+8]
0x180024467  mov     r8, [rsp+8D0h+psetcolumn]; psetcolumn
0x18002446c  sub     r9, r8
0x18002446f  sar     r9, 3
0x180024473  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002447d  imul    r9, rax; csetcolumn
0x180024481  mov     rdx, r15; tableid
0x180024484  mov     rcx, [rbx+30h]; sesid
0x180024488  call    cs:__imp_JetSetColumns
0x18002448e  mov     ecx, eax
0x180024490  test    eax, eax
0x180024492  jns     short loc_1800244AA
0x180024494  cmp     ecx, 0FFFFFC0Dh
0x18002449a  jnz     loc_1800245DE
0x1800244a0  mov     ebx, 8007000Eh
0x1800244a5  jmp     loc_180024594
0x1800244aa  lea     rax, [rsp+8D0h+cbBookmark]
0x1800244af  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x1800244b4  mov     r9d, 7D0h; cbBookmark
0x1800244ba  lea     r8, [rbp+7D0h+pvBookmark]; pvBookmark
0x1800244be  mov     rdx, r15; tableid
0x1800244c1  mov     rcx, [rbx+30h]; sesid
0x1800244c5  call    cs:__imp_JetUpdate
0x1800244cb  mov     ecx, eax
0x1800244cd  test    eax, eax
0x1800244cf  js      short loc_180024494
0x1800244d1  mov     r9d, [rsp+8D0h+cbBookmark]; cbBookmark
0x1800244d6  lea     r8, [rbp+7D0h+pvBookmark]; pvBookmark
0x1800244da  mov     rdx, r15; tableid
0x1800244dd  mov     rcx, [rbx+30h]; sesid
0x1800244e1  call    cs:__imp_JetGotoBookmark
0x1800244e7  mov     ecx, eax
0x1800244e9  test    eax, eax
0x1800244eb  js      short loc_180024494
0x1800244ed  xor     r14d, r14d
0x1800244f0  mov     rax, [rbx+8]
0x1800244f4  mov     rcx, [rdi+rax+30h]
0x1800244f9  sub     rcx, [rdi+rax+28h]
0x1800244fe  sar     rcx, 3
0x180024502  mov     rdi, 6DB6DB6DB6DB6DB7h
0x18002450c  imul    rcx, rdi
0x180024510  test    rcx, rcx
0x180024513  jz      short loc_180024592
0x180024515  xorps   xmm0, xmm0
0x180024518  movdqu  [rsp+8D0h+var_890+8], xmm0
0x18002451e  mov     qword ptr [rsp+8D0h+var_880+8], 0
0x180024527  lea     r9, [rsp+8D0h+var_890]; struct SmsJetDBValue *
0x18002452c  mov     r8d, r14d; unsigned int
0x18002452f  mov     edx, r12d; unsigned int
0x180024532  mov     rcx, rbx; this
0x180024535  call    ?GetColumnValue@CSmsJetDB@@AEAAJKKPEAVSmsJetDBValue@@@Z; CSmsJetDB::GetColumnValue(ulong,ulong,SmsJetDBValue *)
0x18002453a  mov     eax, r14d
0x18002453d  imul    rdx, rax, 38h ; '8'
0x180024541  mov     rax, [rbx+8]
0x180024545  mov     rcx, [rsi+rax]
0x180024549  add     rcx, 8
0x18002454d  add     rdx, rcx
0x180024550  cmp     qword ptr [rdx+18h], 0Fh
0x180024555  jbe     short loc_18002455A
0x180024557  mov     rdx, [rdx]; char *
0x18002455a  lea     r8, [rsp+8D0h+var_890]; struct SmsJetDBValue *
0x18002455f  mov     rcx, r13; this
0x180024562  call    ?SetFieldValue@SmsJetDBRecord@@QEAAXPEBDPEAVSmsJetDBValue@@@Z; SmsJetDBRecord::SetFieldValue(char const *,SmsJetDBValue *)
0x180024567  nop
0x180024568  lea     rcx, [rsp+8D0h+var_890+8]
0x18002456d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180024572  inc     r14d
0x180024575  mov     rax, [rbx+8]
0x180024579  mov     rcx, [rsi+rax+8]
0x18002457e  sub     rcx, [rsi+rax]
0x180024582  sar     rcx, 3
0x180024586  imul    rcx, rdi
0x18002458a  mov     eax, r14d
0x18002458d  cmp     rax, rcx
0x180024590  jb      short loc_180024515
0x180024592  xor     ebx, ebx
0x180024594  lea     rcx, [rbp+7D0h+var_828]
0x180024598  call    ?_Tidy@?$vector@VSmsJetDBValue@@V?$allocator@VSmsJetDBValue@@@std@@@std@@AEAAXXZ; std::vector<SmsJetDBValue>::_Tidy(void)
0x18002459d  nop
0x18002459e  lea     rcx, [rbp+7D0h+var_848]
0x1800245a2  call    ??1?$vector@W4SMS_BROADCAST_TYPES@@V?$allocator@W4SMS_BROADCAST_TYPES@@@std@@@std@@QEAA@XZ; std::vector<SMS_BROADCAST_TYPES>::~vector<SMS_BROADCAST_TYPES>(void)
0x1800245a7  nop
0x1800245a8  lea     rcx, [rsp+8D0h+psetcolumn]
0x1800245ad  call    ??1?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@std@@@std@@QEAA@XZ; std::vector<JET_SETCOLUMN>::~vector<JET_SETCOLUMN>(void)
0x1800245b2  mov     eax, ebx
0x1800245b4  mov     rcx, [rbp+7D0h+var_40]
0x1800245bb  xor     rcx, rsp; StackCookie
0x1800245be  call    __security_check_cookie
0x1800245c3  mov     rbx, [rsp+8D0h+arg_18]
0x1800245cb  add     rsp, 8A0h
0x1800245d2  pop     r15
0x1800245d4  pop     r14
0x1800245d6  pop     r13
0x1800245d8  pop     r12
0x1800245da  pop     rdi
0x1800245db  pop     rsi
0x1800245dc  pop     rbp
0x1800245dd  retn
0x1800245de  neg     eax
0x1800245e0  cmovs   eax, ecx
0x1800245e3  movzx   ebx, ax
0x1800245e6  and     ecx, 8E5E0000h
0x1800245ec  or      ebx, ecx
0x1800245ee  or      ebx, 0E5E0000h
0x1800245f4  jmp     short loc_180024594
```
