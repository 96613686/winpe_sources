# CMetadataPngTextReaderWriter::SetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1801adb50`
- end: `0x1801ade04`
- name: `?SetValueByIndex@CMetadataPngTextReaderWriter@@UEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `692`
- prototype: `__int64 __usercall@<rax>(CMetadataPngTextReaderWriter *__hidden this@<rcx>, unsigned int@<edx>, const struct tagPROPVARIANT *@<r8>, const struct tagPROPVARIANT *@<r9>, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800b8090`

## callees

- `0x1800319d0`
- `0x18003c670`
- `0x18004f1e0`
- `0x1800a5864`
- `0x1800bd9d4`
- `0x1801adb50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801add4c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801add7b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801add4c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801add7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801adc6f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801adc8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801add1a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801add34`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801adc6f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801adc8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801add1a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801add34`

## pseudocode

```c
__int64 __fastcall CMetadataPngTextReaderWriter::SetValueByIndex(
        CMetadataPngTextReaderWriter *this,
        int a2,
        const struct tagPROPVARIANT *a3,
        const struct tagPROPVARIANT *a4,
        const struct tagPROPVARIANT *a5)
{
  unsigned int v8; // ebx
  int v9; // ecx
  const struct tagPROPVARIANT *v10; // rsi
  HRESULT v11; // eax
  int v12; // ecx
  BYTE *pData; // xmm1_8
  BYTE *v14; // xmm1_8
  _QWORD *v15; // r8
  unsigned __int64 v16; // r11
  HRESULT v17; // eax
  HRESULT v18; // eax
  _QWORD *v19; // r8
  int v21; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v22; // [rsp+28h] [rbp-48h] BYREF
  char *v23; // [rsp+30h] [rbp-40h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+38h] [rbp-38h] BYREF
  struct tagPROPVARIANT pvarSrc; // [rsp+50h] [rbp-20h] BYREF
  int v26; // [rsp+A0h] [rbp+30h] BYREF

  v23 = (char *)this + 40;
  CMTALock::Enter((CMetadataPngTextReaderWriter *)((char *)this + 40));
  v26 = 0;
  v21 = 0;
  memset(&pvar, 0, sizeof(pvar));
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  if ( a2 || !a4 || (v10 = a5) == 0 )
  {
    v8 = -2147024809;
    goto LABEL_3;
  }
  if ( (unsigned __int16)(a5->vt - 30) <= 1u )
  {
    v11 = CMetadataPngTextReaderWriter::CoerceVariantToPSZSTR(this, a4, &pvar, &v26);
    v8 = v11;
    if ( v11 < 0 )
      goto LABEL_25;
    v11 = CMetadataPngTextReaderWriter::CoerceVariantToPSZSTR(this, v10, &pvarSrc, &v21);
    v8 = v11;
    if ( v11 < 0 )
      goto LABEL_25;
    v22 = 0;
    if ( (int)StringCchLengthA(pvar.pszVal, 0x50u, &v22) < 0 )
    {
      v8 = -2003292334;
LABEL_14:
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_28;
      v12 = v8;
      goto LABEL_27;
    }
    if ( !v22 )
    {
      v8 = -2147024809;
      goto LABEL_14;
    }
    v11 = PropVariantClear((PROPVARIANT *)this + 19);
    v8 = v11;
    if ( v11 < 0 || (v11 = PropVariantClear((PROPVARIANT *)this + 23), v8 = v11, v11 < 0) )
    {
LABEL_25:
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_28;
      v12 = v11;
LABEL_27:
      DoStackCapture(v12);
LABEL_28:
      if ( v26 )
        PropVariantClear((PROPVARIANT *)&pvar);
LABEL_30:
      if ( v21 )
        PropVariantClear((PROPVARIANT *)&pvarSrc);
      goto LABEL_42;
    }
    if ( v26 )
    {
      v26 = 0;
      pData = pvar.bstrblobVal.pData;
      *(_OWORD *)((char *)this + 152) = *(_OWORD *)&pvar.vt;
      *((_QWORD *)this + 21) = pData;
    }
    else
    {
      v17 = PropVariantCopy((PROPVARIANT *)this + 19, (const PROPVARIANT *)&pvar);
      v8 = v17;
      if ( v17 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v17);
        goto LABEL_30;
      }
    }
    if ( v21 )
    {
      v21 = 0;
      v14 = pvarSrc.bstrblobVal.pData;
      *(_OWORD *)((char *)this + 184) = *(_OWORD *)&pvarSrc.vt;
      *((_QWORD *)this + 25) = v14;
    }
    else
    {
      v18 = PropVariantCopy((PROPVARIANT *)this + 23, (const PROPVARIANT *)&pvarSrc);
      v8 = v18;
      if ( v18 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_42;
        goto LABEL_37;
      }
    }
    v11 = StringCchLengthA(pvar.pszVal, 0x7FFFFFFFu, (unsigned __int64 *)this + 22);
    v8 = v11;
    if ( v11 < 0 )
      goto LABEL_25;
    ++*v15;
    v18 = StringCchLengthA(pvarSrc.pszVal, v16, (unsigned __int64 *)this + 26);
    v8 = v18;
    if ( v18 >= 0 )
    {
      ++*v19;
      *((_DWORD *)this + 24) = 1;
      *((_DWORD *)this + 55) = 1;
      *((_DWORD *)this + 54) = 0;
      goto LABEL_42;
    }
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_42;
LABEL_37:
    v9 = v18;
    goto LABEL_5;
  }
  v8 = -2003292271;
LABEL_3:
  if ( (_DWORD)g_doStackCaptures )
  {
    v9 = v8;
LABEL_5:
    DoStackCapture(v9);
  }
LABEL_42:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v23);
  return v8;
}

```

## disassembly

```asm
0x1801adb50  mov     [rsp-28h+arg_8], rbx
0x1801adb55  mov     [rsp-28h+arg_10], rsi
0x1801adb5a  push    rbp
0x1801adb5b  push    rdi
0x1801adb5c  push    r12
0x1801adb5e  push    r14
0x1801adb60  push    r15
0x1801adb62  mov     rbp, rsp
0x1801adb65  sub     rsp, 70h
0x1801adb69  mov     rdi, rcx
0x1801adb6c  mov     r14, r9
0x1801adb6f  add     rcx, 28h ; '('; this
0x1801adb73  mov     ebx, edx
0x1801adb75  mov     [rbp+var_40], rcx
0x1801adb79  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1801adb7e  xor     eax, eax
0x1801adb80  xor     r15d, r15d
0x1801adb83  mov     [rbp+var_28], rax
0x1801adb87  xorps   xmm0, xmm0
0x1801adb8a  mov     [rbp+var_10], rax
0x1801adb8e  xorps   xmm1, xmm1
0x1801adb91  mov     [rbp+arg_0], r15d
0x1801adb95  mov     [rbp+var_50], r15d
0x1801adb99  movups  xmmword ptr [rbp+pvar], xmm0
0x1801adb9d  movups  xmmword ptr [rbp+pvarSrc], xmm1
0x1801adba1  test    ebx, ebx
0x1801adba3  jz      short loc_1801ADBC3
0x1801adba5  mov     ebx, 80070057h
0x1801adbaa  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801adbb1  jz      loc_1801ADDDF
0x1801adbb7  mov     ecx, ebx; int
0x1801adbb9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801adbbe  jmp     loc_1801ADDDF
0x1801adbc3  test    r14, r14
0x1801adbc6  jz      short loc_1801ADBA5
0x1801adbc8  mov     rsi, [rbp+arg_20]
0x1801adbcc  test    rsi, rsi
0x1801adbcf  jz      short loc_1801ADBA5
0x1801adbd1  movzx   eax, word ptr [rsi]
0x1801adbd4  mov     r12d, 1
0x1801adbda  sub     ax, 1Eh
0x1801adbde  cmp     ax, r12w
0x1801adbe2  jbe     short loc_1801ADBEB
0x1801adbe4  mov     ebx, 88982F91h
0x1801adbe9  jmp     short loc_1801ADBAA
0x1801adbeb  lea     r9, [rbp+arg_0]; int *
0x1801adbef  mov     rdx, r14; struct tagPROPVARIANT *
0x1801adbf2  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1801adbf6  mov     rcx, rdi; this
0x1801adbf9  call    ?CoerceVariantToPSZSTR@CMetadataPngTextReaderWriter@@EEAAJPEBUtagPROPVARIANT@@PEAU2@PEAH@Z; CMetadataPngTextReaderWriter::CoerceVariantToPSZSTR(tagPROPVARIANT const *,tagPROPVARIANT *,int *)
0x1801adbfe  mov     ebx, eax
0x1801adc00  test    eax, eax
0x1801adc02  js      loc_1801ADD00
0x1801adc08  lea     r9, [rbp+var_50]; int *
0x1801adc0c  mov     rdx, rsi; struct tagPROPVARIANT *
0x1801adc0f  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x1801adc13  mov     rcx, rdi; this
0x1801adc16  call    ?CoerceVariantToPSZSTR@CMetadataPngTextReaderWriter@@EEAAJPEBUtagPROPVARIANT@@PEAU2@PEAH@Z; CMetadataPngTextReaderWriter::CoerceVariantToPSZSTR(tagPROPVARIANT const *,tagPROPVARIANT *,int *)
0x1801adc1b  mov     ebx, eax
0x1801adc1d  test    eax, eax
0x1801adc1f  js      loc_1801ADD00
0x1801adc25  mov     rcx, [rbp+pvar+8]; char *
0x1801adc29  lea     r8, [rbp+var_48]; unsigned __int64 *
0x1801adc2d  mov     edx, 50h ; 'P'; unsigned __int64
0x1801adc32  mov     [rbp+var_48], r15
0x1801adc36  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801adc3b  test    eax, eax
0x1801adc3d  jns     short loc_1801ADC58
0x1801adc3f  mov     ebx, 88982F52h
0x1801adc44  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801adc4b  jz      loc_1801ADD10
0x1801adc51  mov     ecx, ebx
0x1801adc53  jmp     loc_1801ADD0B
0x1801adc58  cmp     [rbp+var_48], r12
0x1801adc5c  jnb     short loc_1801ADC65
0x1801adc5e  mov     ebx, 80070057h
0x1801adc63  jmp     short loc_1801ADC44
0x1801adc65  lea     rsi, [rdi+98h]
0x1801adc6c  mov     rcx, rsi; pvar
0x1801adc6f  call    cs:__imp_PropVariantClear
0x1801adc76  nop     dword ptr [rax+rax+00h]
0x1801adc7b  mov     ebx, eax
0x1801adc7d  test    eax, eax
0x1801adc7f  js      short loc_1801ADD00
0x1801adc81  lea     r14, [rdi+0B8h]
0x1801adc88  mov     rcx, r14; pvar
0x1801adc8b  call    cs:__imp_PropVariantClear
0x1801adc92  nop     dword ptr [rax+rax+00h]
0x1801adc97  mov     ebx, eax
0x1801adc99  test    eax, eax
0x1801adc9b  js      short loc_1801ADD00
0x1801adc9d  cmp     [rbp+arg_0], r15d
0x1801adca1  jz      loc_1801ADD45
0x1801adca7  movups  xmm0, xmmword ptr [rbp+pvar]
0x1801adcab  mov     [rbp+arg_0], r15d
0x1801adcaf  movsd   xmm1, [rbp+var_28]
0x1801adcb4  movups  xmmword ptr [rsi], xmm0
0x1801adcb7  movsd   qword ptr [rsi+10h], xmm1
0x1801adcbc  cmp     [rbp+var_50], r15d
0x1801adcc0  jz      loc_1801ADD74
0x1801adcc6  movups  xmm0, xmmword ptr [rbp+pvarSrc]
0x1801adcca  mov     [rbp+var_50], r15d
0x1801adcce  movsd   xmm1, [rbp+var_10]
0x1801adcd3  movups  xmmword ptr [r14], xmm0
0x1801adcd7  movsd   qword ptr [r14+10h], xmm1
0x1801adcdd  mov     rcx, [rbp+pvar+8]; char *
0x1801adce1  lea     r8, [rdi+0B0h]; unsigned __int64 *
0x1801adce8  mov     r11d, 7FFFFFFFh
0x1801adcee  mov     edx, r11d; unsigned __int64
0x1801adcf1  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801adcf6  mov     ebx, eax
0x1801adcf8  test    eax, eax
0x1801adcfa  jns     loc_1801ADDA1
0x1801add00  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801add07  jz      short loc_1801ADD10
0x1801add09  mov     ecx, eax; int
0x1801add0b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801add10  cmp     [rbp+arg_0], r15d
0x1801add14  jz      short loc_1801ADD26
0x1801add16  lea     rcx, [rbp+pvar]; pvar
0x1801add1a  call    cs:__imp_PropVariantClear
0x1801add21  nop     dword ptr [rax+rax+00h]
0x1801add26  cmp     [rbp+var_50], r15d
0x1801add2a  jz      loc_1801ADDDF
0x1801add30  lea     rcx, [rbp+pvarSrc]; pvar
0x1801add34  call    cs:__imp_PropVariantClear
0x1801add3b  nop     dword ptr [rax+rax+00h]
0x1801add40  jmp     loc_1801ADDDF
0x1801add45  lea     rdx, [rbp+pvar]; pvarSrc
0x1801add49  mov     rcx, rsi; pvarDest
0x1801add4c  call    cs:__imp_PropVariantCopy
0x1801add53  nop     dword ptr [rax+rax+00h]
0x1801add58  mov     ebx, eax
0x1801add5a  test    eax, eax
0x1801add5c  jns     loc_1801ADCBC
0x1801add62  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801add69  jz      short loc_1801ADD26
0x1801add6b  mov     ecx, eax; int
0x1801add6d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801add72  jmp     short loc_1801ADD26
0x1801add74  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x1801add78  mov     rcx, r14; pvarDest
0x1801add7b  call    cs:__imp_PropVariantCopy
0x1801add82  nop     dword ptr [rax+rax+00h]
0x1801add87  mov     ebx, eax
0x1801add89  test    eax, eax
0x1801add8b  jns     loc_1801ADCDD
0x1801add91  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801add98  jz      short loc_1801ADDDF
0x1801add9a  mov     ecx, eax
0x1801add9c  jmp     loc_1801ADBB9
0x1801adda1  add     [r8], r12
0x1801adda4  mov     rdx, r11; unsigned __int64
0x1801adda7  mov     rcx, [rbp+pvarSrc+8]; char *
0x1801addab  lea     r8, [rdi+0D0h]; unsigned __int64 *
0x1801addb2  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801addb7  mov     ebx, eax
0x1801addb9  test    eax, eax
0x1801addbb  jns     short loc_1801ADDCA
0x1801addbd  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801addc4  jnz     short loc_1801ADD9A
0x1801addc6  test    eax, eax
0x1801addc8  js      short loc_1801ADDDF
0x1801addca  add     [r8], r12
0x1801addcd  mov     [rdi+60h], r12d
0x1801addd1  mov     [rdi+0DCh], r12d
0x1801addd8  mov     [rdi+0D8h], r15d
0x1801adddf  lea     rcx, [rbp+var_40]
0x1801adde3  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1801adde8  lea     r11, [rsp+70h+var_s0]
0x1801added  mov     eax, ebx
0x1801addef  mov     rbx, [r11+38h]
0x1801addf3  mov     rsi, [r11+40h]
0x1801addf7  mov     rsp, r11
0x1801addfa  pop     r15
0x1801addfc  pop     r14
0x1801addfe  pop     r12
0x1801ade00  pop     rdi
0x1801ade01  pop     rbp
0x1801ade02  retn
```
