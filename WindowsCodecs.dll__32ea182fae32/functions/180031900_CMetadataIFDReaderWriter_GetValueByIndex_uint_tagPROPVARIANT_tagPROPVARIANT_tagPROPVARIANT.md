# CMetadataIFDReaderWriter::GetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180031900`
- end: `0x180031d5f`
- name: `?GetValueByIndex@CMetadataIFDReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `1119`
- prototype: `__int64 __usercall@<rax>(CMetadataIFDReaderWriter *__hidden this@<rcx>, unsigned int@<edx>, struct tagPROPVARIANT *@<r8>, struct tagPROPVARIANT *@<r9>, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800dc840`

## callees

- `0x18001dd10`
- `0x180031900`
- `0x180032d50`
- `0x180032d70`
- `0x180041dec`
- `0x180054d54`
- `0x180067e88`
- `0x18006ac40`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031be5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031c60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031d0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031be5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031c60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031d0a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031ae3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031af1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031b04`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031ae3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031af1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031b04`

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
  HRESULT Value; // eax
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
                  this,
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
0x180031900  mov     [rsp-38h+arg_18], rbx
0x180031905  mov     [rsp-38h+pvar], r8
0x18003190a  push    rbp
0x18003190b  push    rsi
0x18003190c  push    rdi
0x18003190d  push    r12
0x18003190f  push    r13
0x180031911  push    r14
0x180031913  push    r15
0x180031915  mov     rbp, rsp
0x180031918  sub     rsp, 20h
0x18003191c  lea     rbx, [rcx+28h]
0x180031920  mov     r15, rcx
0x180031923  mov     rcx, rbx; this
0x180031926  mov     r14, r9
0x180031929  mov     edi, edx
0x18003192b  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180031930  xor     esi, esi
0x180031932  cmp     edi, [r15+5D0h]
0x180031939  jnb     loc_180031A0D
0x18003193f  test    r14, r14
0x180031942  jz      short loc_18003194E
0x180031944  cmp     [r14], si
0x180031948  jnz     loc_180031A0D
0x18003194e  mov     r8, [rbp+pvarSrc]; pvarSrc
0x180031952  test    r8, r8
0x180031955  jnz     loc_180031A59
0x18003195b  mov     rdx, [rbp+pvar]
0x18003195f  test    rdx, rdx
0x180031962  jnz     loc_180031A65
0x180031968  mov     edx, esi
0x18003196a  cmp     edx, [r15+0C8h]
0x180031971  jnb     loc_180031A2A
0x180031977  mov     eax, edx
0x180031979  lea     r12, [rax+rax*4]
0x18003197d  shl     r12, 4
0x180031981  add     r12, [r15+0B0h]
0x180031988  test    byte ptr [r12+10h], 8
0x18003198e  jnz     short loc_180031996
0x180031990  test    edi, edi
0x180031992  jz      short loc_18003199A
0x180031994  dec     edi
0x180031996  inc     edx
0x180031998  jmp     short loc_18003196A
0x18003199a  mov     edi, esi
0x18003199c  test    r8, r8
0x18003199f  jnz     loc_180031A34
0x1800319a5  mov     r11d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800319ac  mov     eax, 0EA1Ch
0x1800319b1  cmp     [r12], ax
0x1800319b6  jz      loc_180031D21
0x1800319bc  mov     eax, 0EA1Dh
0x1800319c1  cmp     [r12], ax
0x1800319c6  jz      loc_180031D40
0x1800319cc  test    r14, r14
0x1800319cf  jz      short loc_1800319E1
0x1800319d1  mov     word ptr [r14], 12h
0x1800319d7  movzx   eax, word ptr [r12]
0x1800319dc  mov     [r14+8], ax
0x1800319e1  test    edi, edi
0x1800319e3  js      loc_180031ADA
0x1800319e9  test    rbx, rbx
0x1800319ec  jz      short loc_1800319F6
0x1800319ee  mov     rcx, rbx; this
0x1800319f1  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x1800319f6  mov     rbx, [rsp+20h+arg_18]
0x1800319fb  mov     eax, edi
0x1800319fd  add     rsp, 20h
0x180031a01  pop     r15
0x180031a03  pop     r14
0x180031a05  pop     r13
0x180031a07  pop     r12
0x180031a09  pop     rdi
0x180031a0a  pop     rsi
0x180031a0b  pop     rbp
0x180031a0c  retn
0x180031a0d  mov     edi, 80070057h
0x180031a12  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180031a18  jz      loc_180031ADA
0x180031a1e  mov     ecx, edi; int
0x180031a20  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180031a25  jmp     loc_180031ADA
0x180031a2a  mov     edi, 88982F40h
0x180031a2f  jmp     loc_180031ADA
0x180031a34  mov     rdx, r12; struct IFD::FieldEntry *
0x180031a37  mov     rcx, r15; this
0x180031a3a  call    ?GetValue@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEAUtagPROPVARIANT@@@Z; CMetadataIFDReaderWriter::GetValue(IFD::FieldEntry *,tagPROPVARIANT *)
0x180031a3f  mov     r11d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180031a46  mov     edi, eax
0x180031a48  test    eax, eax
0x180031a4a  jns     loc_1800319AC
0x180031a50  test    r11d, r11d
0x180031a53  jz      short loc_180031A78
0x180031a55  mov     ecx, eax
0x180031a57  jmp     short loc_180031A20
0x180031a59  cmp     [r8], si
0x180031a5d  jz      loc_18003195B
0x180031a63  jmp     short loc_180031A0D
0x180031a65  cmp     [rdx], si
0x180031a68  jz      loc_180031968
0x180031a6e  mov     edi, 80070057h
0x180031a73  jmp     loc_180031B3F
0x180031a78  test    eax, eax
0x180031a7a  js      short loc_180031ADA
0x180031a7c  jmp     loc_1800319AC
0x180031a81  mov     ecx, eax; int
0x180031a83  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180031a88  mov     rcx, [rbp+pvar]
0x180031a8c  jmp     short loc_180031AE3
0x180031a8e  mov     edi, 80070216h
0x180031a93  test    r11d, r11d
0x180031a96  jz      short loc_180031A88
0x180031a98  mov     ecx, edi
0x180031a9a  jmp     short loc_180031A83
0x180031a9c  test    r11d, r11d
0x180031a9f  jz      short loc_180031ADA
0x180031aa1  jmp     short loc_180031A55
0x180031aa3  test    r11d, r11d
0x180031aa6  jz      short loc_180031A88
0x180031aa8  jmp     short loc_180031A81
0x180031aaa  shr     rdi, 1
0x180031aad  mov     rcx, rax; unsigned __int16 *
0x180031ab0  mov     rdx, rdi; unsigned __int64
0x180031ab3  mov     [r14], r13w
0x180031ab7  mov     [r14+8], rax
0x180031abb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031ac0  mov     edi, eax
0x180031ac2  test    eax, eax
0x180031ac4  jns     loc_1800319E1
0x180031aca  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180031ad0  jnz     short loc_180031A55
0x180031ad2  test    eax, eax
0x180031ad4  jns     loc_1800319E1
0x180031ada  mov     rcx, [rbp+pvar]; pvar
0x180031ade  test    rcx, rcx
0x180031ae1  jz      short loc_180031AE9
0x180031ae3  call    cs:__imp_PropVariantClear
0x180031ae9  test    r14, r14
0x180031aec  jz      short loc_180031AF7
0x180031aee  mov     rcx, r14; pvar
0x180031af1  call    cs:__imp_PropVariantClear
0x180031af7  mov     rcx, [rbp+pvarSrc]; pvar
0x180031afb  test    rcx, rcx
0x180031afe  jz      loc_1800319E9
0x180031b04  call    cs:__imp_PropVariantClear
0x180031b0a  jmp     loc_1800319E9
0x180031b0f  lea     rdx, [rbp+puResult]; puResult
0x180031b13  mov     [rbp+puResult], esi
0x180031b16  mov     ecx, 1Ch; ullOperand
0x180031b1b  call    ULongLongToUInt
0x180031b20  mov     edi, eax
0x180031b22  test    eax, eax
0x180031b24  js      loc_180031AA3
0x180031b2a  mov     edi, [rbp+puResult]
0x180031b2d  mov     ecx, edi; cb
0x180031b2f  call    cs:__imp_CoTaskMemAlloc
0x180031b35  test    rax, rax
0x180031b38  jnz     short loc_180031B4A
0x180031b3a  mov     edi, 8007000Eh
0x180031b3f  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180031b45  jmp     loc_180031A96
0x180031b4a  mov     rcx, [rbp+pvar]
0x180031b4e  lea     r8, aPaddingschema; "PaddingSchema"
0x180031b55  shr     rdi, 1
0x180031b58  mov     rdx, rdi; unsigned __int64
0x180031b5b  mov     [rcx], r13w
0x180031b5f  mov     [rcx+8], rax
0x180031b63  mov     rcx, rax; unsigned __int16 *
0x180031b66  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031b6b  mov     r11d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180031b72  mov     edi, eax
0x180031b74  test    eax, eax
0x180031b76  jns     short loc_180031B89
0x180031b78  test    r11d, r11d
0x180031b7b  jnz     loc_180031A81
0x180031b81  test    eax, eax
0x180031b83  js      loc_180031A88
0x180031b89  test    r14, r14
0x180031b8c  jz      loc_1800319E1
0x180031b92  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x180031b96  mov     [rbp+pullResult], rsi
0x180031b9a  mov     edx, 7FFFFFFFh; unsigned __int64
0x180031b9f  lea     rcx, aPadding; "padding"
0x180031ba6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031bab  mov     edi, eax
0x180031bad  test    eax, eax
0x180031baf  js      loc_180031A9C
0x180031bb5  mov     rax, [rbp+pullResult]
0x180031bb9  lea     rcx, [rax+1]; ullMultiplicand
0x180031bbd  cmp     rcx, rax
0x180031bc0  jb      short loc_180031C00
0x180031bc2  lea     r8, [rbp+pullResult]; pullResult
0x180031bc6  mov     [rbp+pullResult], rcx
0x180031bca  mov     edx, 2; ullMultiplier
0x180031bcf  call    ULongLongMult
0x180031bd4  mov     edi, eax
0x180031bd6  test    eax, eax
0x180031bd8  js      loc_180031A9C
0x180031bde  mov     rdi, [rbp+pullResult]
0x180031be2  mov     rcx, rdi; cb
0x180031be5  call    cs:__imp_CoTaskMemAlloc
0x180031beb  test    rax, rax
0x180031bee  jz      loc_180031D36
0x180031bf4  lea     r8, aPadding; "padding"
0x180031bfb  jmp     loc_180031AAA
0x180031c00  mov     edi, 80070216h
0x180031c05  test    r11d, r11d
0x180031c08  jmp     loc_180031A18
0x180031c0d  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x180031c11  mov     [rbp+pullResult], rsi
0x180031c15  mov     rdx, r15; unsigned __int64
0x180031c18  lea     rcx, aOffsetschema; "OffsetSchema"
0x180031c1f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031c24  mov     edi, eax
0x180031c26  test    eax, eax
0x180031c28  js      loc_180031AA3
0x180031c2e  mov     rax, [rbp+pullResult]
0x180031c32  lea     rcx, [rax+1]; ullMultiplicand
0x180031c36  cmp     rcx, rax
0x180031c39  jb      loc_180031A8E
0x180031c3f  lea     r8, [rbp+pullResult]; pullResult
0x180031c43  mov     [rbp+pullResult], rcx
0x180031c47  mov     rdx, r12; ullMultiplier
0x180031c4a  call    ULongLongMult
0x180031c4f  mov     edi, eax
0x180031c51  test    eax, eax
0x180031c53  js      loc_180031AA3
0x180031c59  mov     rdi, [rbp+pullResult]
0x180031c5d  mov     rcx, rdi; cb
0x180031c60  call    cs:__imp_CoTaskMemAlloc
0x180031c66  test    rax, rax
0x180031c69  jz      loc_180031B3A
0x180031c6f  mov     rcx, [rbp+pvar]
0x180031c73  lea     r8, aOffsetschema; "OffsetSchema"
0x180031c7a  shr     rdi, 1
0x180031c7d  mov     rdx, rdi; unsigned __int64
0x180031c80  mov     [rcx], r13w
0x180031c84  mov     [rcx+8], rax
0x180031c88  mov     rcx, rax; unsigned __int16 *
0x180031c8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031c90  mov     r11d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180031c97  mov     edi, eax
0x180031c99  test    eax, eax
0x180031c9b  jns     short loc_180031CAE
0x180031c9d  test    r11d, r11d
0x180031ca0  jnz     loc_180031A81
0x180031ca6  test    eax, eax
0x180031ca8  js      loc_180031A88
0x180031cae  test    r14, r14
0x180031cb1  jz      loc_1800319E1
0x180031cb7  lea     r8, [rbp+pullResult]; unsigned __int64 *
0x180031cbb  mov     [rbp+pullResult], rsi
0x180031cbf  mov     rdx, r15; unsigned __int64
0x180031cc2  lea     rcx, aOffset; "offset"
0x180031cc9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031cce  mov     edi, eax
0x180031cd0  test    eax, eax
0x180031cd2  js      loc_180031A9C
0x180031cd8  mov     rax, [rbp+pullResult]
0x180031cdc  lea     rcx, [rax+1]; ullMultiplicand
0x180031ce0  cmp     rcx, rax
0x180031ce3  jb      loc_180031C00
0x180031ce9  lea     r8, [rbp+pullResult]; pullResult
0x180031ced  mov     [rbp+pullResult], rcx
0x180031cf1  mov     rdx, r12; ullMultiplier
0x180031cf4  call    ULongLongMult
0x180031cf9  mov     edi, eax
0x180031cfb  test    eax, eax
0x180031cfd  js      loc_180031A9C
0x180031d03  mov     rdi, [rbp+pullResult]
0x180031d07  mov     rcx, rdi; cb
0x180031d0a  call    cs:__imp_CoTaskMemAlloc
0x180031d10  test    rax, rax
0x180031d13  jz      short loc_180031D36
0x180031d15  lea     r8, aOffset; "offset"
0x180031d1c  jmp     loc_180031AAA
0x180031d21  mov     r13d, 1Fh
0x180031d27  cmp     [rbp+pvar], rsi
0x180031d2b  jz      loc_180031B89
0x180031d31  jmp     loc_180031B0F
0x180031d36  mov     edi, 8007000Eh
0x180031d3b  jmp     loc_180031A12
0x180031d40  mov     r13d, 1Fh
0x180031d46  mov     r15d, 7FFFFFFFh
0x180031d4c  lea     r12d, [r13-1Dh]
0x180031d50  cmp     [rbp+pvar], rsi
0x180031d54  jz      loc_180031CAE
0x180031d5a  jmp     loc_180031C0D
```
