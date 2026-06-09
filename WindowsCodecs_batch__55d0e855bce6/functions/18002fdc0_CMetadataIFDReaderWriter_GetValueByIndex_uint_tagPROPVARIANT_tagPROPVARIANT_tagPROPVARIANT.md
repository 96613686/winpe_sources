# CMetadataIFDReaderWriter::GetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x18002fdc0`
- end: `0x18003024a`
- name: `?GetValueByIndex@CMetadataIFDReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `1162`
- prototype: `__int64 __usercall@<rax>(CMetadataIFDReaderWriter *__hidden this@<rcx>, unsigned int@<edx>, struct tagPROPVARIANT *@<r8>, struct tagPROPVARIANT *@<r9>, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800df4d0`

## callees

- `0x18002fdc0`
- `0x1800319d0`
- `0x1800319f0`
- `0x18003573c`
- `0x180039480`
- `0x180042ae8`
- `0x180049c00`
- `0x180064b00`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800300be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003013f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800301ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800300be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003013f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800301ef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ffa4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ffb8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ffd1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ffa4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ffb8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ffd1`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetValueByIndex(
        CMetadataIFDReaderWriter *this,
        unsigned int a2,
        PROPVARIANT *a3,
        PROPVARIANT *a4,
        PROPVARIANT *pvarSrc)
{
  CMTALock *v5; // rbx
  unsigned int i; // edx
  __int64 v10; // r12
  int v11; // edi
  bool v13; // zf
  int v14; // ecx
  int Value; // eax
  int v16; // ecx
  PROPVARIANT *v17; // rcx
  bool v18; // zf
  HRESULT v19; // eax
  int v20; // r11d
  unsigned __int64 v21; // rdi
  unsigned __int16 *v22; // rax
  PROPVARIANT *v23; // rcx
  int v24; // r11d
  ULONGLONG v25; // rcx
  ULONGLONG v26; // rdi
  unsigned __int16 *v27; // rax
  const unsigned __int16 *v28; // r8
  ULONGLONG v29; // rcx
  ULONGLONG v30; // rdi
  unsigned __int16 *v31; // rax
  PROPVARIANT *v32; // rcx
  ULONGLONG v33; // rcx
  ULONGLONG pullResult; // [rsp+60h] [rbp+40h] BYREF
  UINT puResult; // [rsp+68h] [rbp+48h] BYREF
  PROPVARIANT *pvar; // [rsp+70h] [rbp+50h]

  pvar = a3;
  v5 = (CMetadataIFDReaderWriter *)((char *)this + 40);
  CMTALock::Enter((CMetadataIFDReaderWriter *)((char *)this + 40));
  if ( a2 >= *((_DWORD *)this + 372) || a4 && *(_WORD *)a4 || pvarSrc && *(_WORD *)pvarSrc )
  {
    v11 = -2147024809;
LABEL_22:
    v13 = (_DWORD)g_doStackCaptures == 0;
LABEL_23:
    if ( v13 )
      goto LABEL_47;
    v14 = v11;
    goto LABEL_25;
  }
  if ( pvar && *(_WORD *)pvar )
  {
    v11 = -2147024809;
LABEL_56:
    v18 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_39;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 50) )
    {
      v11 = -2003292352;
      goto LABEL_47;
    }
    v10 = *((_QWORD *)this + 22) + 80LL * i;
    if ( (*(_BYTE *)(v10 + 16) & 8) == 0 )
      break;
LABEL_11:
    ;
  }
  if ( a2 )
  {
    --a2;
    goto LABEL_11;
  }
  v11 = 0;
  if ( !pvarSrc
    || (Value = CMetadataIFDReaderWriter::GetValue(
                  (CStreamBase **)this,
                  (struct IFD::FieldEntry *)(*((_QWORD *)this + 22) + 80LL * i),
                  pvarSrc),
        v11 = Value,
        Value >= 0) )
  {
    if ( *(_WORD *)v10 != 0xEA1C )
    {
      if ( *(_WORD *)v10 != 0xEA1D )
      {
        if ( a4 )
        {
          *(_WORD *)a4 = 18;
          *((_WORD *)a4 + 4) = *(_WORD *)v10;
        }
LABEL_17:
        if ( v11 < 0 )
          goto LABEL_47;
        goto LABEL_18;
      }
      if ( !pvar )
        goto LABEL_74;
      pullResult = 0;
      v19 = StringCchLengthW(L"OffsetSchema", 0x7FFFFFFFu, &pullResult);
      v11 = v19;
      if ( v19 >= 0 )
      {
        v29 = pullResult + 1;
        if ( pullResult + 1 < pullResult )
        {
          v11 = -2147024362;
          v18 = v20 == 0;
LABEL_39:
          if ( v18 )
            goto LABEL_37;
          v16 = v11;
LABEL_36:
          DoStackCapture(v16);
LABEL_37:
          v17 = pvar;
          goto LABEL_48;
        }
        ++pullResult;
        v19 = ULongLongMult(v29, 2u, &pullResult);
        v11 = v19;
        if ( v19 >= 0 )
        {
          v30 = pullResult;
          v31 = (unsigned __int16 *)CoTaskMemAlloc(pullResult);
          if ( v31 )
          {
            v32 = pvar;
            *(_WORD *)pvar = 31;
            v32[1] = v31;
            v19 = StringCchCopyW(v31, v30 >> 1, L"OffsetSchema");
            v11 = v19;
            if ( v19 < 0 )
            {
              if ( !(_DWORD)g_doStackCaptures )
                goto LABEL_37;
LABEL_35:
              v16 = v19;
              goto LABEL_36;
            }
LABEL_74:
            if ( !a4 )
              goto LABEL_17;
            pullResult = 0;
            Value = StringCchLengthW(L"offset", 0x7FFFFFFFu, &pullResult);
            v11 = Value;
            if ( Value < 0 )
              goto LABEL_41;
            v33 = pullResult + 1;
            if ( pullResult + 1 >= pullResult )
            {
              ++pullResult;
              Value = ULongLongMult(v33, 2u, &pullResult);
              v11 = Value;
              if ( Value >= 0 )
              {
                v26 = pullResult;
                v27 = (unsigned __int16 *)CoTaskMemAlloc(pullResult);
                if ( v27 )
                {
                  v28 = L"offset";
                  goto LABEL_45;
                }
                goto LABEL_82;
              }
              goto LABEL_41;
            }
            goto LABEL_66;
          }
LABEL_55:
          v11 = -2147024882;
          goto LABEL_56;
        }
      }
LABEL_43:
      if ( !v20 )
        goto LABEL_37;
      goto LABEL_35;
    }
    if ( pvar )
    {
      puResult = 0;
      v19 = ULongLongToUInt(0x1Cu, &puResult);
      v11 = v19;
      if ( v19 < 0 )
        goto LABEL_43;
      v21 = puResult;
      v22 = (unsigned __int16 *)CoTaskMemAlloc(puResult);
      if ( !v22 )
        goto LABEL_55;
      v23 = pvar;
      *(_WORD *)pvar = 31;
      v23[1] = v22;
      v19 = StringCchCopyW(v22, v21 >> 1, L"PaddingSchema");
      v11 = v19;
      if ( v19 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_37;
        goto LABEL_35;
      }
    }
    if ( !a4 )
      goto LABEL_17;
    pullResult = 0;
    Value = StringCchLengthW(L"padding", 0x7FFFFFFFu, &pullResult);
    v11 = Value;
    if ( Value < 0 )
      goto LABEL_41;
    v25 = pullResult + 1;
    if ( pullResult + 1 >= pullResult )
    {
      ++pullResult;
      Value = ULongLongMult(v25, 2u, &pullResult);
      v11 = Value;
      if ( Value >= 0 )
      {
        v26 = pullResult;
        v27 = (unsigned __int16 *)CoTaskMemAlloc(pullResult);
        if ( v27 )
        {
          v28 = L"padding";
LABEL_45:
          *(_WORD *)a4 = 31;
          a4[1] = v27;
          Value = StringCchCopyW(v27, v26 >> 1, v28);
          v11 = Value;
          if ( Value >= 0 )
            goto LABEL_17;
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_47;
LABEL_29:
          v14 = Value;
LABEL_25:
          DoStackCapture(v14);
          goto LABEL_47;
        }
LABEL_82:
        v11 = -2147024882;
        goto LABEL_22;
      }
LABEL_41:
      if ( !v24 )
        goto LABEL_47;
      goto LABEL_29;
    }
LABEL_66:
    v11 = -2147024362;
    v13 = v24 == 0;
    goto LABEL_23;
  }
  if ( (_DWORD)g_doStackCaptures )
    goto LABEL_29;
LABEL_47:
  v17 = pvar;
  if ( pvar )
LABEL_48:
    PropVariantClear(v17);
  if ( a4 )
    PropVariantClear(a4);
  if ( pvarSrc )
    PropVariantClear(pvarSrc);
LABEL_18:
  if ( v5 )
    CMTALock::Leave(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002fdc0  mov     [rsp-38h+arg_18], rbx
0x18002fdc5  mov     [rsp-38h+pvar], r8
0x18002fdca  push    rbp
0x18002fdcb  push    rsi
0x18002fdcc  push    rdi
0x18002fdcd  push    r12
0x18002fdcf  push    r13
0x18002fdd1  push    r14
0x18002fdd3  push    r15
0x18002fdd5  mov     rbp, rsp
0x18002fdd8  sub     rsp, 20h
0x18002fddc  lea     rbx, [rcx+28h]
0x18002fde0  mov     r15, rcx
0x18002fde3  mov     rcx, rbx; this
0x18002fde6  mov     r14, r9
0x18002fde9  mov     edi, edx
0x18002fdeb  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002fdf0  xor     esi, esi
0x18002fdf2  cmp     edi, [r15+5D0h]
0x18002fdf9  jnb     loc_18002FECE
0x18002fdff  test    r14, r14
0x18002fe02  jz      short loc_18002FE0E
0x18002fe04  cmp     [r14], si
0x18002fe08  jnz     loc_18002FECE
0x18002fe0e  mov     r8, [rbp+pvarSrc]; pvarSrc
0x18002fe12  test    r8, r8
0x18002fe15  jnz     loc_18002FF1A
0x18002fe1b  mov     rdx, [rbp+pvar]
0x18002fe1f  test    rdx, rdx
0x18002fe22  jnz     loc_18002FF26
0x18002fe28  mov     edx, esi
0x18002fe2a  cmp     edx, [r15+0C8h]
0x18002fe31  jnb     loc_18002FEEB
0x18002fe37  mov     eax, edx
0x18002fe39  lea     r12, [rax+rax*4]
0x18002fe3d  shl     r12, 4
0x18002fe41  add     r12, [r15+0B0h]
0x18002fe48  test    byte ptr [r12+10h], 8
0x18002fe4e  jnz     short loc_18002FE56
0x18002fe50  test    edi, edi
0x18002fe52  jz      short loc_18002FE5A
0x18002fe54  dec     edi
0x18002fe56  inc     edx
0x18002fe58  jmp     short loc_18002FE2A
0x18002fe5a  mov     edi, esi
0x18002fe5c  test    r8, r8
0x18002fe5f  jnz     loc_18002FEF5
0x18002fe65  mov     r11d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18002fe6c  mov     eax, 0EA1Ch
0x18002fe71  cmp     [r12], ax
0x18002fe76  jz      loc_18003020C
0x18002fe7c  mov     eax, 0EA1Dh
0x18002fe81  cmp     [r12], ax
0x18002fe86  jz      loc_18003022B
0x18002fe8c  test    r14, r14
0x18002fe8f  jz      short loc_18002FEA1
0x18002fe91  mov     word ptr [r14], 12h
0x18002fe97  movzx   eax, word ptr [r12]
0x18002fe9c  mov     [r14+8], ax
0x18002fea1  test    edi, edi
0x18002fea3  js      loc_18002FF9B
0x18002fea9  test    rbx, rbx
0x18002feac  jz      short loc_18002FEB6
0x18002feae  mov     rcx, rbx; this
0x18002feb1  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x18002feb6  mov     rbx, [rsp+20h+arg_18]
0x18002febb  mov     eax, edi
0x18002febd  add     rsp, 20h
0x18002fec1  pop     r15
0x18002fec3  pop     r14
0x18002fec5  pop     r13
0x18002fec7  pop     r12
0x18002fec9  pop     rdi
0x18002feca  pop     rsi
0x18002fecb  pop     rbp
0x18002fecc  retn
0x18002fece  mov     edi, 80070057h
0x18002fed3  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18002fed9  jz      loc_18002FF9B
0x18002fedf  mov     ecx, edi; int
0x18002fee1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002fee6  jmp     loc_18002FF9B
0x18002feeb  mov     edi, 88982F40h
0x18002fef0  jmp     loc_18002FF9B
0x18002fef5  mov     rdx, r12; struct IFD::FieldEntry *
0x18002fef8  mov     rcx, r15; this
0x18002fefb  call    ?GetValue@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetValue(IFD::FieldEntry *,tagPROPVARIANT *)
0x18002ff00  mov     r11d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18002ff07  mov     edi, eax
0x18002ff09  test    eax, eax
0x18002ff0b  jns     loc_18002FE6C
0x18002ff11  test    r11d, r11d
0x18002ff14  jz      short loc_18002FF39
0x18002ff16  mov     ecx, eax
0x18002ff18  jmp     short loc_18002FEE1
0x18002ff1a  cmp     [r8], si
0x18002ff1e  jz      loc_18002FE1B
0x18002ff24  jmp     short loc_18002FECE
0x18002ff26  cmp     [rdx], si
0x18002ff29  jz      loc_18002FE28
0x18002ff2f  mov     edi, 80070057h
0x18002ff34  jmp     loc_180030018
0x18002ff39  test    eax, eax
0x18002ff3b  js      short loc_18002FF9B
0x18002ff3d  jmp     loc_18002FE6C
0x18002ff42  mov     ecx, eax; int
0x18002ff44  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002ff49  mov     rcx, [rbp+pvar]
0x18002ff4d  jmp     short loc_18002FFA4
0x18002ff4f  mov     edi, 80070216h
0x18002ff54  test    r11d, r11d
0x18002ff57  jz      short loc_18002FF49
0x18002ff59  mov     ecx, edi
0x18002ff5b  jmp     short loc_18002FF44
0x18002ff5d  test    r11d, r11d
0x18002ff60  jz      short loc_18002FF9B
0x18002ff62  jmp     short loc_18002FF16
0x18002ff64  test    r11d, r11d
0x18002ff67  jz      short loc_18002FF49
0x18002ff69  jmp     short loc_18002FF42
0x18002ff6b  shr     rdi, 1
0x18002ff6e  mov     rcx, rax; unsigned __int16 *
0x18002ff71  mov     rdx, rdi; unsigned __int64
0x18002ff74  mov     [r14], r13w
0x18002ff78  mov     [r14+8], rax
0x18002ff7c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ff81  mov     edi, eax
0x18002ff83  test    eax, eax
0x18002ff85  jns     loc_18002FEA1
0x18002ff8b  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18002ff91  jnz     short loc_18002FF16
0x18002ff93  test    eax, eax
0x18002ff95  jns     loc_18002FEA1
0x18002ff9b  mov     rcx, [rbp+pvar]; pvar
0x18002ff9f  test    rcx, rcx
0x18002ffa2  jz      short loc_18002FFB0
0x18002ffa4  call    cs:__imp_PropVariantClear
0x18002ffab  nop     dword ptr [rax+rax+00h]
0x18002ffb0  test    r14, r14
0x18002ffb3  jz      short loc_18002FFC4
0x18002ffb5  mov     rcx, r14; pvar
0x18002ffb8  call    cs:__imp_PropVariantClear
0x18002ffbf  nop     dword ptr [rax+rax+00h]
0x18002ffc4  mov     rcx, [rbp+pvarSrc]; pvar
0x18002ffc8  test    rcx, rcx
0x18002ffcb  jz      loc_18002FEA9
0x18002ffd1  call    cs:__imp_PropVariantClear
0x18002ffd8  nop     dword ptr [rax+rax+00h]
0x18002ffdd  jmp     loc_18002FEA9
0x18002ffe2  lea     rdx, [rbp+puResult]; puResult
0x18002ffe6  mov     [rbp+puResult], esi
0x18002ffe9  mov     ecx, 1Ch; ullOperand
0x18002ffee  call    ULongLongToUInt
0x18002fff3  mov     edi, eax
0x18002fff5  test    eax, eax
0x18002fff7  js      loc_18002FF64
0x18002fffd  mov     edi, [rbp+puResult]
0x180030000  mov     ecx, edi; cb
0x180030002  call    cs:__imp_CoTaskMemAlloc
0x180030009  nop     dword ptr [rax+rax+00h]
0x18003000e  test    rax, rax
0x180030011  jnz     short loc_180030023
0x180030013  mov     edi, 8007000Eh
0x180030018  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18003001e  jmp     loc_18002FF57
0x180030023  mov     rcx, [rbp+pvar]
0x180030027  lea     r8, aPaddingschema; "PaddingSchema"
0x18003002e  shr     rdi, 1
0x180030031  mov     rdx, rdi; unsigned __int64
0x180030034  mov     [rcx], r13w
0x180030038  mov     [rcx+8], rax
0x18003003c  mov     rcx, rax; unsigned __int16 *
0x18003003f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030044  mov     r11d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18003004b  mov     edi, eax
0x18003004d  test    eax, eax
0x18003004f  jns     short loc_180030062
0x180030051  test    r11d, r11d
0x180030054  jnz     loc_18002FF42
0x18003005a  test    eax, eax
0x18003005c  js      loc_18002FF49
0x180030062  test    r14, r14
0x180030065  jz      loc_18002FEA1
0x18003006b  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x18003006f  mov     [rbp+pullResult], rsi
0x180030073  mov     edx, 7FFFFFFFh; unsigned __int64
0x180030078  lea     rcx, aPadding; "padding"
0x18003007f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180030084  mov     edi, eax
0x180030086  test    eax, eax
0x180030088  js      loc_18002FF5D
0x18003008e  mov     rax, [rbp+pullResult]
0x180030092  lea     rcx, [rax+1]; ullMultiplicand
0x180030096  cmp     rcx, rax
0x180030099  jb      short loc_1800300DF
0x18003009b  lea     r8, [rbp+pullResult]; pullResult
0x18003009f  mov     [rbp+pullResult], rcx
0x1800300a3  mov     edx, 2; ullMultiplier
0x1800300a8  call    ULongLongMult
0x1800300ad  mov     edi, eax
0x1800300af  test    eax, eax
0x1800300b1  js      loc_18002FF5D
0x1800300b7  mov     rdi, [rbp+pullResult]
0x1800300bb  mov     rcx, rdi; cb
0x1800300be  call    cs:__imp_CoTaskMemAlloc
0x1800300c5  nop     dword ptr [rax+rax+00h]
0x1800300ca  test    rax, rax
0x1800300cd  jz      loc_180030221
0x1800300d3  lea     r8, aPadding; "padding"
0x1800300da  jmp     loc_18002FF6B
0x1800300df  mov     edi, 80070216h
0x1800300e4  test    r11d, r11d
0x1800300e7  jmp     loc_18002FED9
0x1800300ec  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800300f0  mov     [rbp+pullResult], rsi
0x1800300f4  mov     rdx, r15; unsigned __int64
0x1800300f7  lea     rcx, aOffsetschema; "OffsetSchema"
0x1800300fe  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180030103  mov     edi, eax
0x180030105  test    eax, eax
0x180030107  js      loc_18002FF64
0x18003010d  mov     rax, [rbp+pullResult]
0x180030111  lea     rcx, [rax+1]; ullMultiplicand
0x180030115  cmp     rcx, rax
0x180030118  jb      loc_18002FF4F
0x18003011e  lea     r8, [rbp+pullResult]; pullResult
0x180030122  mov     [rbp+pullResult], rcx
0x180030126  mov     rdx, r12; ullMultiplier
0x180030129  call    ULongLongMult
0x18003012e  mov     edi, eax
0x180030130  test    eax, eax
0x180030132  js      loc_18002FF64
0x180030138  mov     rdi, [rbp+pullResult]
0x18003013c  mov     rcx, rdi; cb
0x18003013f  call    cs:__imp_CoTaskMemAlloc
0x180030146  nop     dword ptr [rax+rax+00h]
0x18003014b  test    rax, rax
0x18003014e  jz      loc_180030013
0x180030154  mov     rcx, [rbp+pvar]
0x180030158  lea     r8, aOffsetschema; "OffsetSchema"
0x18003015f  shr     rdi, 1
0x180030162  mov     rdx, rdi; unsigned __int64
0x180030165  mov     [rcx], r13w
0x180030169  mov     [rcx+8], rax
0x18003016d  mov     rcx, rax; unsigned __int16 *
0x180030170  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030175  mov     r11d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18003017c  mov     edi, eax
0x18003017e  test    eax, eax
0x180030180  jns     short loc_180030193
0x180030182  test    r11d, r11d
0x180030185  jnz     loc_18002FF42
0x18003018b  test    eax, eax
0x18003018d  js      loc_18002FF49
0x180030193  test    r14, r14
0x180030196  jz      loc_18002FEA1
0x18003019c  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x1800301a0  mov     [rbp+pullResult], rsi
0x1800301a4  mov     rdx, r15; unsigned __int64
0x1800301a7  lea     rcx, aOffset; "offset"
0x1800301ae  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800301b3  mov     edi, eax
0x1800301b5  test    eax, eax
0x1800301b7  js      loc_18002FF5D
0x1800301bd  mov     rax, [rbp+pullResult]
0x1800301c1  lea     rcx, [rax+1]; ullMultiplicand
0x1800301c5  cmp     rcx, rax
0x1800301c8  jb      loc_1800300DF
0x1800301ce  lea     r8, [rbp+pullResult]; pullResult
0x1800301d2  mov     [rbp+pullResult], rcx
0x1800301d6  mov     rdx, r12; ullMultiplier
0x1800301d9  call    ULongLongMult
0x1800301de  mov     edi, eax
0x1800301e0  test    eax, eax
0x1800301e2  js      loc_18002FF5D
0x1800301e8  mov     rdi, [rbp+pullResult]
0x1800301ec  mov     rcx, rdi; cb
0x1800301ef  call    cs:__imp_CoTaskMemAlloc
0x1800301f6  nop     dword ptr [rax+rax+00h]
0x1800301fb  test    rax, rax
0x1800301fe  jz      short loc_180030221
0x180030200  lea     r8, aOffset; "offset"
0x180030207  jmp     loc_18002FF6B
0x18003020c  mov     r13d, 1Fh
0x180030212  cmp     [rbp+pvar], rsi
0x180030216  jz      loc_180030062
0x18003021c  jmp     loc_18002FFE2
0x180030221  mov     edi, 8007000Eh
0x180030226  jmp     loc_18002FED3
0x18003022b  mov     r13d, 1Fh
0x180030231  mov     r15d, 7FFFFFFFh
0x180030237  lea     r12d, [r13-1Dh]
0x18003023b  cmp     [rbp+pvar], rsi
0x18003023f  jz      loc_180030193
0x180030245  jmp     loc_1800300EC
```
