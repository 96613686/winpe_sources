# CSmsJetDB::Seek(char const *,char const *,SmsJetDBRecord *,int)

- ea: `0x180025430`
- end: `0x18002563a`
- name: `?Seek@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@H@Z`
- size: `522`
- prototype: `__int64 __fastcall(CSmsJetDB *__hidden this, const char *, const char *, struct SmsJetDBRecord *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18001d3c8`
- `0x1800233e0`

## callees

- `0x1800205b8`
- `0x180022678`
- `0x1800237f4`
- `0x180023a58`
- `0x180023b2c`
- `0x180023c24`
- `0x180023f9c`
- `0x180025430`
- `0x1800261a0`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800254d9`
- `ESENT!JetSetCurrentIndexA` at `0x1800254d9`
- `ESENT!JetSeek` at `0x1800255b7`
- `ESENT!JetSeek` at `0x1800255b7`
- `ESENT!JetMove` at `0x180025511`
- `ESENT!JetMove` at `0x180025511`
- `ESENT!JetMakeKey` at `0x18002557c`
- `ESENT!JetMakeKey` at `0x18002557c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsJetDB::Seek(JET_SESID *this, const char *a2, const char *a3, struct SmsJetDBRecord *a4, int a5)
{
  unsigned int TableIndex; // eax
  unsigned __int64 v10; // rdi
  unsigned int IndexIndex; // eax
  JET_SESID v12; // rdx
  JET_ERR Key; // eax
  JET_ERR v14; // ecx
  unsigned int CurrentRecord; // ebx
  unsigned int v16; // esi
  __int64 v17; // rdx
  __int64 v18; // r12
  __int64 v19; // rax
  const char *v20; // rdx
  __int64 v21; // r15
  int v22; // eax
  __int128 v24; // [rsp+30h] [rbp-38h] BYREF
  __int64 v25; // [rsp+40h] [rbp-28h]
  _QWORD v26[4]; // [rsp+48h] [rbp-20h] BYREF

  TableIndex = CSmsJetDB::GetTableIndex((CSmsJetDB *)this, a2);
  if ( TableIndex == this[5] )
    return 2147943568LL;
  v10 = (unsigned __int64)TableIndex << 7;
  IndexIndex = TableDefinition::GetIndexIndex((TableDefinition *)(v10 + this[1]), a3);
  v12 = this[1];
  if ( IndexIndex == (__int64)(*(_QWORD *)(v10 + v12 + 72) - *(_QWORD *)(v10 + v12 + 64)) >> 6 )
    return 2147943568LL;
  v24 = 0;
  v25 = 0;
  IndexDefinition::GetKeyColumns(*(_QWORD *)(v10 + v12 + 64) + ((unsigned __int64)IndexIndex << 6), &v24);
  std::vector<SmsJetDBValue>::vector<SmsJetDBValue>(v26, (__int64)(*((_QWORD *)&v24 + 1) - v24) >> 5);
  Key = JetSetCurrentIndexA(this[6], *(_QWORD *)(v10 + this[1] + 88), a3);
  v14 = Key;
  if ( Key < 0 || (Key = JetMove(this[6], *(_QWORD *)(v10 + this[1] + 88), 0x80000000, 0), v14 = Key, Key < 0) )
  {
LABEL_4:
    if ( v14 == -1011 )
    {
      CurrentRecord = -2147024882;
    }
    else
    {
      v22 = -Key;
      if ( v22 < 0 )
        LOWORD(v22) = v14;
      CurrentRecord = v14 & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
    }
    goto LABEL_20;
  }
  v16 = 0;
  v17 = v24;
  if ( (__int64)(*((_QWORD *)&v24 + 1) - v24) >> 5 )
  {
    v18 = v26[0];
    do
    {
      v19 = 32LL * v16;
      v20 = (const char *)(v19 + v17);
      v21 = v19 + v18;
      if ( *((_QWORD *)v20 + 3) > 0xFu )
        v20 = *(const char **)v20;
      SmsJetDBRecord::GetFieldValue(a4, v20, (struct SmsJetDBValue *)(v19 + v18));
      Key = JetMakeKey(
              this[6],
              *(_QWORD *)(this[1] + v10 + 88),
              *(const void **)(v21 + 8),
              *(_DWORD *)(v21 + 16) - *(_QWORD *)(v21 + 8),
              v16 == 0);
      v14 = Key;
      if ( Key < 0 )
        goto LABEL_4;
      ++v16;
      v17 = v24;
    }
    while ( v16 < (unsigned __int64)((__int64)(*((_QWORD *)&v24 + 1) - v24) >> 5) );
  }
  if ( JetSeek(this[6], *(_QWORD *)(v10 + this[1] + 88), 0x21u) )
  {
    CurrentRecord = -1906440639;
LABEL_20:
    std::vector<SmsJetDBValue>::_Tidy(v26);
    std::vector<std::string>::_Tidy(&v24);
    return CurrentRecord;
  }
  if ( a5 )
  {
    CurrentRecord = CSmsJetDB::GetCurrentRecord((CSmsJetDB *)this, a2, a4);
    goto LABEL_20;
  }
  std::vector<SmsJetDBValue>::_Tidy(v26);
  std::vector<std::string>::_Tidy(&v24);
  return 0;
}

```

## disassembly

```asm
0x180025430  push    rbp
0x180025432  push    rbx
0x180025433  push    rsi
0x180025434  push    rdi
0x180025435  push    r12
0x180025437  push    r13
0x180025439  push    r14
0x18002543b  push    r15
0x18002543d  mov     rbp, rsp
0x180025440  sub     rsp, 68h
0x180025444  mov     r13, r9
0x180025447  mov     rsi, r8
0x18002544a  mov     r14, rdx
0x18002544d  mov     rbx, rcx
0x180025450  call    ?GetTableIndex@CSmsJetDB@@AEAAKPEBD@Z; CSmsJetDB::GetTableIndex(char const *)
0x180025455  mov     edi, eax
0x180025457  cmp     rdi, [rbx+28h]
0x18002545b  jz      loc_180025624
0x180025461  shl     rdi, 7
0x180025465  mov     rcx, [rbx+8]
0x180025469  add     rcx, rdi; this
0x18002546c  mov     rdx, rsi; char *
0x18002546f  call    ?GetIndexIndex@TableDefinition@@QEAAKPEBD@Z; TableDefinition::GetIndexIndex(char const *)
0x180025474  mov     rdx, [rbx+8]
0x180025478  mov     ecx, eax
0x18002547a  mov     rax, [rdi+rdx+48h]
0x18002547f  sub     rax, [rdi+rdx+40h]
0x180025484  sar     rax, 6
0x180025488  cmp     rcx, rax
0x18002548b  jz      loc_180025624
0x180025491  xorps   xmm0, xmm0
0x180025494  movdqu  [rbp+var_38], xmm0
0x180025499  mov     [rbp+var_28], 0
0x1800254a1  shl     rcx, 6
0x1800254a5  add     rcx, [rdi+rdx+40h]
0x1800254aa  lea     rdx, [rbp+var_38]
0x1800254ae  call    ?GetKeyColumns@IndexDefinition@@QEAAXAEAV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z; IndexDefinition::GetKeyColumns(std::vector<std::string> &)
0x1800254b3  mov     rdx, qword ptr [rbp+var_38+8]
0x1800254b7  sub     rdx, qword ptr [rbp+var_38]
0x1800254bb  sar     rdx, 5
0x1800254bf  lea     rcx, [rbp+var_20]
0x1800254c3  call    ??0?$vector@VSmsJetDBValue@@V?$allocator@VSmsJetDBValue@@@std@@@std@@QEAA@_KAEBV?$allocator@VSmsJetDBValue@@@1@@Z; std::vector<SmsJetDBValue>::vector<SmsJetDBValue>(unsigned __int64,std::allocator<SmsJetDBValue> const &)
0x1800254c8  nop
0x1800254c9  mov     rdx, [rbx+8]
0x1800254cd  mov     r8, rsi; szIndexName
0x1800254d0  mov     rdx, [rdi+rdx+58h]; tableid
0x1800254d5  mov     rcx, [rbx+30h]; sesid
0x1800254d9  call    cs:__imp_JetSetCurrentIndexA
0x1800254df  mov     ecx, eax
0x1800254e1  test    eax, eax
0x1800254e3  jns     short loc_1800254FB
0x1800254e5  cmp     ecx, 0FFFFFC0Dh
0x1800254eb  jnz     loc_1800255C8
0x1800254f1  mov     ebx, 8007000Eh
0x1800254f6  jmp     loc_1800255F6
0x1800254fb  mov     rdx, [rbx+8]
0x1800254ff  xor     r9d, r9d; grbit
0x180025502  mov     r8d, 80000000h; cRow
0x180025508  mov     rdx, [rdi+rdx+58h]; tableid
0x18002550d  mov     rcx, [rbx+30h]; sesid
0x180025511  call    cs:__imp_JetMove
0x180025517  mov     ecx, eax
0x180025519  test    eax, eax
0x18002551b  js      short loc_1800254E5
0x18002551d  xor     esi, esi
0x18002551f  mov     rax, qword ptr [rbp+var_38+8]
0x180025523  mov     rdx, qword ptr [rbp+var_38]
0x180025527  sub     rax, rdx
0x18002552a  sar     rax, 5
0x18002552e  test    rax, rax
0x180025531  jz      short loc_1800255A4
0x180025533  mov     r12, [rbp+var_20]
0x180025537  mov     eax, esi
0x180025539  shl     rax, 5
0x18002553d  add     rdx, rax
0x180025540  lea     r15, [rax+r12]
0x180025544  cmp     qword ptr [rdx+18h], 0Fh
0x180025549  jbe     short loc_18002554E
0x18002554b  mov     rdx, [rdx]; char *
0x18002554e  mov     r8, r15; struct SmsJetDBValue *
0x180025551  mov     rcx, r13; this
0x180025554  call    ?GetFieldValue@SmsJetDBRecord@@QEAAHPEBDPEAVSmsJetDBValue@@@Z; SmsJetDBRecord::GetFieldValue(char const *,SmsJetDBValue *)
0x180025559  mov     r8, [r15+8]; pvData
0x18002555d  xor     eax, eax
0x18002555f  test    esi, esi
0x180025561  setz    al
0x180025564  mov     r9d, [r15+10h]
0x180025568  sub     r9d, r8d; cbData
0x18002556b  mov     rdx, [rbx+8]
0x18002556f  mov     [rsp+68h+grbit], eax; grbit
0x180025573  mov     rdx, [rdx+rdi+58h]; tableid
0x180025578  mov     rcx, [rbx+30h]; sesid
0x18002557c  call    cs:__imp_JetMakeKey
0x180025582  mov     ecx, eax
0x180025584  test    eax, eax
0x180025586  js      loc_1800254E5
0x18002558c  inc     esi
0x18002558e  mov     rcx, qword ptr [rbp+var_38+8]
0x180025592  mov     rdx, qword ptr [rbp+var_38]
0x180025596  sub     rcx, rdx
0x180025599  sar     rcx, 5
0x18002559d  mov     eax, esi
0x18002559f  cmp     rax, rcx
0x1800255a2  jb      short loc_180025537
0x1800255a4  mov     rdx, [rbx+8]
0x1800255a8  mov     r8d, 21h ; '!'; grbit
0x1800255ae  mov     rdx, [rdi+rdx+58h]; tableid
0x1800255b3  mov     rcx, [rbx+30h]; sesid
0x1800255b7  call    cs:__imp_JetSeek
0x1800255bd  test    eax, eax
0x1800255bf  jz      short loc_1800255E0
0x1800255c1  mov     ebx, 8E5E0641h
0x1800255c6  jmp     short loc_1800255F6
0x1800255c8  neg     eax
0x1800255ca  cmovs   eax, ecx
0x1800255cd  movzx   ebx, ax
0x1800255d0  and     ecx, 8E5E0000h
0x1800255d6  or      ebx, ecx
0x1800255d8  or      ebx, 0E5E0000h
0x1800255de  jmp     short loc_1800255F6
0x1800255e0  cmp     [rbp+arg_20], 0
0x1800255e4  jz      short loc_18002560D
0x1800255e6  mov     r8, r13; struct SmsJetDBRecord *
0x1800255e9  mov     rdx, r14; char *
0x1800255ec  mov     rcx, rbx; this
0x1800255ef  call    ?GetCurrentRecord@CSmsJetDB@@QEAAJPEBDPEAVSmsJetDBRecord@@@Z; CSmsJetDB::GetCurrentRecord(char const *,SmsJetDBRecord *)
0x1800255f4  mov     ebx, eax
0x1800255f6  lea     rcx, [rbp+var_20]
0x1800255fa  call    ?_Tidy@?$vector@VSmsJetDBValue@@V?$allocator@VSmsJetDBValue@@@std@@@std@@AEAAXXZ; std::vector<SmsJetDBValue>::_Tidy(void)
0x1800255ff  nop
0x180025600  lea     rcx, [rbp+var_38]
0x180025604  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x180025609  mov     eax, ebx
0x18002560b  jmp     short loc_180025629
0x18002560d  lea     rcx, [rbp+var_20]
0x180025611  call    ?_Tidy@?$vector@VSmsJetDBValue@@V?$allocator@VSmsJetDBValue@@@std@@@std@@AEAAXXZ; std::vector<SmsJetDBValue>::_Tidy(void)
0x180025616  nop
0x180025617  lea     rcx, [rbp+var_38]
0x18002561b  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x180025620  xor     eax, eax
0x180025622  jmp     short loc_180025629
0x180025624  mov     eax, 80070490h
0x180025629  add     rsp, 68h
0x18002562d  pop     r15
0x18002562f  pop     r14
0x180025631  pop     r13
0x180025633  pop     r12
0x180025635  pop     rdi
0x180025636  pop     rsi
0x180025637  pop     rbx
0x180025638  pop     rbp
0x180025639  retn
```
