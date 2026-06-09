# CMetadataIPTCReaderWriter::GetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x1800224b0`
- end: `0x180022657`
- name: `?GetValue@CMetadataIPTCReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z`
- size: `423`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020740`
- `0x1800224b0`
- `0x180022660`
- `0x180022b84`
- `0x180023648`
- `0x180032d50`
- `0x180032d70`
- `0x1800aa990`
- `0x1800bb784`
- `0x1801c936d`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180022578`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180022578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800225c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800225c6`

## pseudocode

```c
__int64 __fastcall CMetadataIPTCReaderWriter::GetValue(
        CMetadataIPTCReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        PROPVARIANT *a4)
{
  CMTALock *v4; // r14
  int DataSet; // eax
  unsigned int v9; // ebx
  const wchar_t *bstrVal; // rcx
  struct CMetadataIPTCReaderWriter::DataSet *v11; // rbp
  CMetadataIPTCReaderWriter *v12; // rcx
  BYTE *v13; // rax
  int v14; // ecx
  struct CMetadataIPTCReaderWriter::DataSet *v16; // [rsp+70h] [rbp+8h] BYREF

  v4 = (CMetadataIPTCReaderWriter *)((char *)this + 40);
  v16 = 0;
  CMTALock::Enter((CMetadataIPTCReaderWriter *)((char *)this + 40));
  if ( !a3 )
  {
    v9 = -2147024809;
LABEL_31:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_25;
    v14 = v9;
LABEL_24:
    DoStackCapture(v14);
    goto LABEL_25;
  }
  DataSet = CMetadataIPTCReaderWriter::EnsureLoadedValues(this);
  v9 = DataSet;
  if ( DataSet < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_25;
    goto LABEL_23;
  }
  if ( a3->vt == 31 )
  {
    bstrVal = a3->bstrVal;
    if ( bstrVal )
    {
      if ( !wcscmp_0(bstrVal, L"MD5Hash") )
      {
        if ( !a4 )
          goto LABEL_25;
        if ( *((_DWORD *)this + 65) )
          goto LABEL_20;
        DataSet = CMetadataIPTCReaderWriter::CalculateIPTCHash(this, (unsigned __int8 *)this + 244);
        v9 = DataSet;
        if ( DataSet >= 0 )
        {
          *((_DWORD *)this + 65) = 1;
LABEL_20:
          v13 = (BYTE *)CoTaskMemAlloc(0x10u);
          a4[2] = v13;
          if ( v13 )
          {
            *((_DWORD *)a4 + 2) = 16;
            *(_WORD *)a4 = 65;
            *(_OWORD *)v13 = *(_OWORD *)((char *)this + 244);
            goto LABEL_25;
          }
          v9 = -2147024882;
          goto LABEL_31;
        }
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_25;
LABEL_23:
        v14 = DataSet;
        goto LABEL_24;
      }
    }
  }
  DataSet = CMetadataIPTCReaderWriter::FindDataSet(this, a3, &v16, 0, 0);
  v9 = DataSet;
  if ( DataSet >= 0 )
  {
    v11 = v16;
    DataSet = CMetadataIPTCReaderWriter::EnsureDataSetLoaded(this, v16);
    v9 = DataSet;
    if ( DataSet < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_25;
      goto LABEL_23;
    }
    if ( !a4 )
      goto LABEL_25;
    DataSet = *((_QWORD *)v11 + 7)
            ? CMetadataIPTCReaderWriter::CreateVectorFromVariants(v12, v11, a4)
            : PropVariantCopy(a4, (const PROPVARIANT *)v11 + 1);
    v9 = DataSet;
    if ( DataSet >= 0 )
      goto LABEL_25;
  }
  if ( (_DWORD)g_doStackCaptures )
    goto LABEL_23;
LABEL_25:
  if ( v4 )
    CMTALock::Leave(v4);
  return v9;
}

```

## disassembly

```asm
0x1800224b0  push    rbx
0x1800224b2  push    rbp
0x1800224b3  push    rsi
0x1800224b4  push    rdi
0x1800224b5  push    r14
0x1800224b7  push    r15
0x1800224b9  sub     rsp, 38h
0x1800224bd  lea     r14, [rcx+28h]
0x1800224c1  mov     rdi, rcx
0x1800224c4  xor     r15d, r15d
0x1800224c7  mov     rcx, r14; this
0x1800224ca  mov     rsi, r9
0x1800224cd  mov     [rsp+68h+arg_0], r15
0x1800224d2  mov     rbp, r8
0x1800224d5  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800224da  test    rbp, rbp
0x1800224dd  jz      loc_180022639
0x1800224e3  mov     rcx, rdi; this
0x1800224e6  call    ?EnsureLoadedValues@CMetadataIPTCReaderWriter@@EEAAJXZ; CMetadataIPTCReaderWriter::EnsureLoadedValues(void)
0x1800224eb  mov     ebx, eax
0x1800224ed  test    eax, eax
0x1800224ef  js      loc_1800225E7
0x1800224f5  cmp     word ptr [rbp+0], 1Fh
0x1800224fa  jnz     short loc_180022515
0x1800224fc  mov     rcx, [rbp+8]; String1
0x180022500  test    rcx, rcx
0x180022503  jz      short loc_180022515
0x180022505  lea     rdx, aMd5hash; "MD5Hash"
0x18002250c  call    wcscmp_0
0x180022511  test    eax, eax
0x180022513  jz      short loc_18002258F
0x180022515  xor     r9d, r9d; struct CMetadataIPTCReaderWriter::RecordSet **
0x180022518  mov     [rsp+68h+var_48], r15; unsigned int *
0x18002251d  lea     r8, [rsp+68h+arg_0]; struct CMetadataIPTCReaderWriter::DataSet **
0x180022522  mov     rdx, rbp; struct tagPROPVARIANT *
0x180022525  mov     rcx, rdi; this
0x180022528  call    ?FindDataSet@CMetadataIPTCReaderWriter@@AEAAJPEBUtagPROPVARIANT@@PEAPEAUDataSet@1@PEAPEAURecordSet@1@PEAI@Z; CMetadataIPTCReaderWriter::FindDataSet(tagPROPVARIANT const *,CMetadataIPTCReaderWriter::DataSet * *,CMetadataIPTCReaderWriter::RecordSet * *,uint *)
0x18002252d  mov     ebx, eax
0x18002252f  test    eax, eax
0x180022531  js      short loc_180022584
0x180022533  mov     rbp, [rsp+68h+arg_0]
0x180022538  mov     rcx, rdi; this
0x18002253b  mov     rdx, rbp; struct CMetadataIPTCReaderWriter::DataSet *
0x18002253e  call    ?EnsureDataSetLoaded@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@@Z; CMetadataIPTCReaderWriter::EnsureDataSetLoaded(CMetadataIPTCReaderWriter::DataSet *)
0x180022543  mov     ebx, eax
0x180022545  test    eax, eax
0x180022547  jns     short loc_18002255E
0x180022549  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180022550  jnz     loc_1800225F0
0x180022556  test    eax, eax
0x180022558  js      loc_1800225F7
0x18002255e  test    rsi, rsi
0x180022561  jz      loc_1800225F7
0x180022567  cmp     [rbp+38h], r15
0x18002256b  jnz     loc_180022647
0x180022571  lea     rdx, [rbp+8]; pvarSrc
0x180022575  mov     rcx, rsi; pvarDest
0x180022578  call    cs:__imp_PropVariantCopy
0x18002257e  mov     ebx, eax
0x180022580  test    eax, eax
0x180022582  jns     short loc_1800225F7
0x180022584  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18002258b  jnz     short loc_1800225F0
0x18002258d  jmp     short loc_1800225F7
0x18002258f  test    rsi, rsi
0x180022592  jz      short loc_1800225F7
0x180022594  lea     rbp, [rdi+0F4h]
0x18002259b  cmp     [rdi+104h], r15d
0x1800225a2  jnz     short loc_1800225BF
0x1800225a4  mov     rdx, rbp; unsigned __int8 *
0x1800225a7  mov     rcx, rdi; this
0x1800225aa  call    ?CalculateIPTCHash@CMetadataIPTCReaderWriter@@AEAAJPEAE@Z; CMetadataIPTCReaderWriter::CalculateIPTCHash(uchar *)
0x1800225af  mov     ebx, eax
0x1800225b1  test    eax, eax
0x1800225b3  js      short loc_18002261D
0x1800225b5  mov     dword ptr [rdi+104h], 1
0x1800225bf  mov     edi, 10h
0x1800225c4  mov     ecx, edi; cb
0x1800225c6  call    cs:__imp_CoTaskMemAlloc
0x1800225cc  mov     [rsi+10h], rax
0x1800225d0  test    rax, rax
0x1800225d3  jz      short loc_180022640
0x1800225d5  mov     [rsi+8], edi
0x1800225d8  mov     word ptr [rsi], 41h ; 'A'
0x1800225dd  movups  xmm0, xmmword ptr [rbp+0]
0x1800225e1  movdqu  xmmword ptr [rax], xmm0
0x1800225e5  jmp     short loc_1800225F7
0x1800225e7  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800225ee  jz      short loc_180022613
0x1800225f0  mov     ecx, eax; int
0x1800225f2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800225f7  test    r14, r14
0x1800225fa  jz      short loc_180022604
0x1800225fc  mov     rcx, r14; this
0x1800225ff  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180022604  mov     eax, ebx
0x180022606  add     rsp, 38h
0x18002260a  pop     r15
0x18002260c  pop     r14
0x18002260e  pop     rdi
0x18002260f  pop     rsi
0x180022610  pop     rbp
0x180022611  pop     rbx
0x180022612  retn
0x180022613  test    eax, eax
0x180022615  jns     loc_1800224F5
0x18002261b  jmp     short loc_1800225F7
0x18002261d  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180022624  jnz     short loc_1800225F0
0x180022626  test    eax, eax
0x180022628  jns     short loc_1800225B5
0x18002262a  jmp     short loc_1800225F7
0x18002262c  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180022633  jz      short loc_1800225F7
0x180022635  mov     ecx, ebx
0x180022637  jmp     short loc_1800225F2
0x180022639  mov     ebx, 80070057h
0x18002263e  jmp     short loc_18002262C
0x180022640  mov     ebx, 8007000Eh
0x180022645  jmp     short loc_18002262C
0x180022647  mov     r8, rsi; struct tagPROPVARIANT *
0x18002264a  mov     rdx, rbp; struct CMetadataIPTCReaderWriter::DataSet *
0x18002264d  call    ?CreateVectorFromVariants@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@PEAUtagPROPVARIANT@@@Z; CMetadataIPTCReaderWriter::CreateVectorFromVariants(CMetadataIPTCReaderWriter::DataSet *,tagPROPVARIANT *)
0x180022652  jmp     loc_18002257E
```
