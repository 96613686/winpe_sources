# CMetadataIPTCReaderWriter::GetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x18004e420`
- end: `0x18004e5d8`
- name: `?GetValue@CMetadataIPTCReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0PEAU2@@Z`
- size: `440`
- prototype: `__int64 __fastcall(CMetadataIPTCReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800319d0`
- `0x1800319f0`
- `0x18004e420`
- `0x18004e5e0`
- `0x18004eb0c`
- `0x18004f390`
- `0x18004fb38`
- `0x1800ac94c`
- `0x1800bd9d4`
- `0x1801cce3d`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004e4ec`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004e4ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e540`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e540`

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
0x18004e420  push    rbx
0x18004e422  push    rbp
0x18004e423  push    rsi
0x18004e424  push    rdi
0x18004e425  push    r14
0x18004e427  push    r15
0x18004e429  sub     rsp, 38h
0x18004e42d  lea     r14, [rcx+28h]
0x18004e431  mov     rdi, rcx
0x18004e434  xor     r15d, r15d
0x18004e437  mov     rcx, r14; this
0x18004e43a  mov     rsi, r9
0x18004e43d  mov     [rsp+68h+arg_0], r15
0x18004e442  mov     rbp, r8
0x18004e445  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18004e44a  test    rbp, rbp
0x18004e44d  jz      loc_18004E5BA
0x18004e453  mov     rcx, rdi; this
0x18004e456  call    ?EnsureLoadedValues@CMetadataIPTCReaderWriter@@EEAAJXZ; CMetadataIPTCReaderWriter::EnsureLoadedValues(void)
0x18004e45b  mov     ebx, eax
0x18004e45d  test    eax, eax
0x18004e45f  js      loc_18004E567
0x18004e465  cmp     word ptr [rbp+0], 1Fh
0x18004e46a  jnz     short loc_18004E489
0x18004e46c  mov     rcx, [rbp+8]; String1
0x18004e470  test    rcx, rcx
0x18004e473  jz      short loc_18004E489
0x18004e475  lea     rdx, aMd5hash; "MD5Hash"
0x18004e47c  call    wcscmp_0
0x18004e481  test    eax, eax
0x18004e483  jz      loc_18004E509
0x18004e489  xor     r9d, r9d; struct CMetadataIPTCReaderWriter::RecordSet **
0x18004e48c  mov     [rsp+68h+var_48], r15; unsigned int *
0x18004e491  lea     r8, [rsp+68h+arg_0]; struct CMetadataIPTCReaderWriter::DataSet **
0x18004e496  mov     rdx, rbp; struct tagPROPVARIANT *
0x18004e499  mov     rcx, rdi; this
0x18004e49c  call    ?FindDataSet@CMetadataIPTCReaderWriter@@AEAAJPEBUtagPROPVARIANT@@PEAPEAUDataSet@1@PEAPEAURecordSet@1@PEAI@Z; CMetadataIPTCReaderWriter::FindDataSet(tagPROPVARIANT const *,CMetadataIPTCReaderWriter::DataSet * *,CMetadataIPTCReaderWriter::RecordSet * *,uint *)
0x18004e4a1  mov     ebx, eax
0x18004e4a3  test    eax, eax
0x18004e4a5  js      short loc_18004E4FE
0x18004e4a7  mov     rbp, [rsp+68h+arg_0]
0x18004e4ac  mov     rcx, rdi; this
0x18004e4af  mov     rdx, rbp; struct CMetadataIPTCReaderWriter::DataSet *
0x18004e4b2  call    ?EnsureDataSetLoaded@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@@Z; CMetadataIPTCReaderWriter::EnsureDataSetLoaded(CMetadataIPTCReaderWriter::DataSet *)
0x18004e4b7  mov     ebx, eax
0x18004e4b9  test    eax, eax
0x18004e4bb  jns     short loc_18004E4D2
0x18004e4bd  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18004e4c4  jnz     loc_18004E570
0x18004e4ca  test    eax, eax
0x18004e4cc  js      loc_18004E577
0x18004e4d2  test    rsi, rsi
0x18004e4d5  jz      loc_18004E577
0x18004e4db  cmp     [rbp+38h], r15
0x18004e4df  jnz     loc_18004E5C8
0x18004e4e5  lea     rdx, [rbp+8]; pvarSrc
0x18004e4e9  mov     rcx, rsi; pvarDest
0x18004e4ec  call    cs:__imp_PropVariantCopy
0x18004e4f3  nop     dword ptr [rax+rax+00h]
0x18004e4f8  mov     ebx, eax
0x18004e4fa  test    eax, eax
0x18004e4fc  jns     short loc_18004E577
0x18004e4fe  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18004e505  jnz     short loc_18004E570
0x18004e507  jmp     short loc_18004E577
0x18004e509  test    rsi, rsi
0x18004e50c  jz      short loc_18004E577
0x18004e50e  lea     rbp, [rdi+0F4h]
0x18004e515  cmp     [rdi+104h], r15d
0x18004e51c  jnz     short loc_18004E539
0x18004e51e  mov     rdx, rbp; unsigned __int8 *
0x18004e521  mov     rcx, rdi; this
0x18004e524  call    ?CalculateIPTCHash@CMetadataIPTCReaderWriter@@AEAAJPEAE@Z; CMetadataIPTCReaderWriter::CalculateIPTCHash(uchar *)
0x18004e529  mov     ebx, eax
0x18004e52b  test    eax, eax
0x18004e52d  js      short loc_18004E59E
0x18004e52f  mov     dword ptr [rdi+104h], 1
0x18004e539  mov     edi, 10h
0x18004e53e  mov     ecx, edi; cb
0x18004e540  call    cs:__imp_CoTaskMemAlloc
0x18004e547  nop     dword ptr [rax+rax+00h]
0x18004e54c  mov     [rsi+10h], rax
0x18004e550  test    rax, rax
0x18004e553  jz      short loc_18004E5C1
0x18004e555  mov     [rsi+8], edi
0x18004e558  mov     word ptr [rsi], 41h ; 'A'
0x18004e55d  movups  xmm0, xmmword ptr [rbp+0]
0x18004e561  movdqu  xmmword ptr [rax], xmm0
0x18004e565  jmp     short loc_18004E577
0x18004e567  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18004e56e  jz      short loc_18004E594
0x18004e570  mov     ecx, eax; int
0x18004e572  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004e577  test    r14, r14
0x18004e57a  jz      short loc_18004E584
0x18004e57c  mov     rcx, r14; this
0x18004e57f  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x18004e584  mov     eax, ebx
0x18004e586  add     rsp, 38h
0x18004e58a  pop     r15
0x18004e58c  pop     r14
0x18004e58e  pop     rdi
0x18004e58f  pop     rsi
0x18004e590  pop     rbp
0x18004e591  pop     rbx
0x18004e592  retn
0x18004e594  test    eax, eax
0x18004e596  jns     loc_18004E465
0x18004e59c  jmp     short loc_18004E577
0x18004e59e  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18004e5a5  jnz     short loc_18004E570
0x18004e5a7  test    eax, eax
0x18004e5a9  jns     short loc_18004E52F
0x18004e5ab  jmp     short loc_18004E577
0x18004e5ad  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18004e5b4  jz      short loc_18004E577
0x18004e5b6  mov     ecx, ebx
0x18004e5b8  jmp     short loc_18004E572
0x18004e5ba  mov     ebx, 80070057h
0x18004e5bf  jmp     short loc_18004E5AD
0x18004e5c1  mov     ebx, 8007000Eh
0x18004e5c6  jmp     short loc_18004E5AD
0x18004e5c8  mov     r8, rsi; struct tagPROPVARIANT *
0x18004e5cb  mov     rdx, rbp; struct CMetadataIPTCReaderWriter::DataSet *
0x18004e5ce  call    ?CreateVectorFromVariants@CMetadataIPTCReaderWriter@@AEAAJPEAUDataSet@1@PEAUtagPROPVARIANT@@@Z; CMetadataIPTCReaderWriter::CreateVectorFromVariants(CMetadataIPTCReaderWriter::DataSet *,tagPROPVARIANT *)
0x18004e5d3  jmp     loc_18004E4F8
```
