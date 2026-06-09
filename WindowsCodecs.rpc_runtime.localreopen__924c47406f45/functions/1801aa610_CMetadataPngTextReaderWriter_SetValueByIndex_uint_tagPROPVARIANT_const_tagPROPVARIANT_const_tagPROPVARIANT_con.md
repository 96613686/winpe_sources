# CMetadataPngTextReaderWriter::SetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1801aa610`
- end: `0x1801aa89f`
- name: `?SetValueByIndex@CMetadataPngTextReaderWriter@@UEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `655`
- prototype: `__int64 __fastcall(CMetadataPngTextReaderWriter *this, int, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800b5fc0`

## callees

- `0x180023220`
- `0x180032d50`
- `0x180045650`
- `0x1800787a0`
- `0x1800bb784`
- `0x1801aa610`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801aa7f4`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801aa81d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801aa7f4`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1801aa81d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa72f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa745`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa7ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa7e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa72f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa745`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa7ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801aa7e2`

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
0x1801aa610  mov     [rsp-28h+arg_8], rbx
0x1801aa615  mov     [rsp-28h+arg_10], rsi
0x1801aa61a  push    rbp
0x1801aa61b  push    rdi
0x1801aa61c  push    r12
0x1801aa61e  push    r14
0x1801aa620  push    r15
0x1801aa622  mov     rbp, rsp
0x1801aa625  sub     rsp, 70h
0x1801aa629  mov     rdi, rcx
0x1801aa62c  mov     r14, r9
0x1801aa62f  add     rcx, 28h ; '('; this
0x1801aa633  mov     ebx, edx
0x1801aa635  mov     [rbp+var_40], rcx
0x1801aa639  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1801aa63e  xor     eax, eax
0x1801aa640  xor     r15d, r15d
0x1801aa643  mov     [rbp+var_28], rax
0x1801aa647  xorps   xmm0, xmm0
0x1801aa64a  mov     [rbp+var_10], rax
0x1801aa64e  xorps   xmm1, xmm1
0x1801aa651  mov     [rbp+arg_0], r15d
0x1801aa655  mov     [rbp+var_50], r15d
0x1801aa659  movups  xmmword ptr [rbp+pvar], xmm0
0x1801aa65d  movups  xmmword ptr [rbp+pvarSrc], xmm1
0x1801aa661  test    ebx, ebx
0x1801aa663  jz      short loc_1801AA683
0x1801aa665  mov     ebx, 80070057h
0x1801aa66a  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801aa671  jz      loc_1801AA87B
0x1801aa677  mov     ecx, ebx; int
0x1801aa679  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801aa67e  jmp     loc_1801AA87B
0x1801aa683  test    r14, r14
0x1801aa686  jz      short loc_1801AA665
0x1801aa688  mov     rsi, [rbp+arg_20]
0x1801aa68c  test    rsi, rsi
0x1801aa68f  jz      short loc_1801AA665
0x1801aa691  movzx   eax, word ptr [rsi]
0x1801aa694  mov     r12d, 1
0x1801aa69a  sub     ax, 1Eh
0x1801aa69e  cmp     ax, r12w
0x1801aa6a2  jbe     short loc_1801AA6AB
0x1801aa6a4  mov     ebx, 88982F91h
0x1801aa6a9  jmp     short loc_1801AA66A
0x1801aa6ab  lea     r9, [rbp+arg_0]; int *
0x1801aa6af  mov     rdx, r14; struct tagPROPVARIANT *
0x1801aa6b2  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1801aa6b6  mov     rcx, rdi; this
0x1801aa6b9  call    ?CoerceVariantToPSZSTR@CMetadataPngTextReaderWriter@@EEAAJPEBUtagPROPVARIANT@@PEAU2@PEAH@Z; CMetadataPngTextReaderWriter::CoerceVariantToPSZSTR(tagPROPVARIANT const *,tagPROPVARIANT *,int *)
0x1801aa6be  mov     ebx, eax
0x1801aa6c0  test    eax, eax
0x1801aa6c2  js      loc_1801AA7B4
0x1801aa6c8  lea     r9, [rbp+var_50]; int *
0x1801aa6cc  mov     rdx, rsi; struct tagPROPVARIANT *
0x1801aa6cf  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x1801aa6d3  mov     rcx, rdi; this
0x1801aa6d6  call    ?CoerceVariantToPSZSTR@CMetadataPngTextReaderWriter@@EEAAJPEBUtagPROPVARIANT@@PEAU2@PEAH@Z; CMetadataPngTextReaderWriter::CoerceVariantToPSZSTR(tagPROPVARIANT const *,tagPROPVARIANT *,int *)
0x1801aa6db  mov     ebx, eax
0x1801aa6dd  test    eax, eax
0x1801aa6df  js      loc_1801AA7B4
0x1801aa6e5  mov     rcx, [rbp+pvar+8]; char *
0x1801aa6e9  lea     r8, [rbp+var_48]; unsigned __int64 *
0x1801aa6ed  mov     edx, 50h ; 'P'; unsigned __int64
0x1801aa6f2  mov     [rbp+var_48], r15
0x1801aa6f6  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801aa6fb  test    eax, eax
0x1801aa6fd  jns     short loc_1801AA718
0x1801aa6ff  mov     ebx, 88982F52h
0x1801aa704  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801aa70b  jz      loc_1801AA7C4
0x1801aa711  mov     ecx, ebx
0x1801aa713  jmp     loc_1801AA7BF
0x1801aa718  cmp     [rbp+var_48], r12
0x1801aa71c  jnb     short loc_1801AA725
0x1801aa71e  mov     ebx, 80070057h
0x1801aa723  jmp     short loc_1801AA704
0x1801aa725  lea     rsi, [rdi+98h]
0x1801aa72c  mov     rcx, rsi; pvar
0x1801aa72f  call    cs:__imp_PropVariantClear
0x1801aa735  mov     ebx, eax
0x1801aa737  test    eax, eax
0x1801aa739  js      short loc_1801AA7B4
0x1801aa73b  lea     r14, [rdi+0B8h]
0x1801aa742  mov     rcx, r14; pvar
0x1801aa745  call    cs:__imp_PropVariantClear
0x1801aa74b  mov     ebx, eax
0x1801aa74d  test    eax, eax
0x1801aa74f  js      short loc_1801AA7B4
0x1801aa751  cmp     [rbp+arg_0], r15d
0x1801aa755  jz      loc_1801AA7ED
0x1801aa75b  movups  xmm0, xmmword ptr [rbp+pvar]
0x1801aa75f  mov     [rbp+arg_0], r15d
0x1801aa763  movsd   xmm1, [rbp+var_28]
0x1801aa768  movups  xmmword ptr [rsi], xmm0
0x1801aa76b  movsd   qword ptr [rsi+10h], xmm1
0x1801aa770  cmp     [rbp+var_50], r15d
0x1801aa774  jz      loc_1801AA816
0x1801aa77a  movups  xmm0, xmmword ptr [rbp+pvarSrc]
0x1801aa77e  mov     [rbp+var_50], r15d
0x1801aa782  movsd   xmm1, [rbp+var_10]
0x1801aa787  movups  xmmword ptr [r14], xmm0
0x1801aa78b  movsd   qword ptr [r14+10h], xmm1
0x1801aa791  mov     rcx, [rbp+pvar+8]; char *
0x1801aa795  lea     r8, [rdi+0B0h]; unsigned __int64 *
0x1801aa79c  mov     r11d, 7FFFFFFFh
0x1801aa7a2  mov     edx, r11d; unsigned __int64
0x1801aa7a5  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801aa7aa  mov     ebx, eax
0x1801aa7ac  test    eax, eax
0x1801aa7ae  jns     loc_1801AA83D
0x1801aa7b4  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801aa7bb  jz      short loc_1801AA7C4
0x1801aa7bd  mov     ecx, eax; int
0x1801aa7bf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801aa7c4  cmp     [rbp+arg_0], r15d
0x1801aa7c8  jz      short loc_1801AA7D4
0x1801aa7ca  lea     rcx, [rbp+pvar]; pvar
0x1801aa7ce  call    cs:__imp_PropVariantClear
0x1801aa7d4  cmp     [rbp+var_50], r15d
0x1801aa7d8  jz      loc_1801AA87B
0x1801aa7de  lea     rcx, [rbp+pvarSrc]; pvar
0x1801aa7e2  call    cs:__imp_PropVariantClear
0x1801aa7e8  jmp     loc_1801AA87B
0x1801aa7ed  lea     rdx, [rbp+pvar]; pvarSrc
0x1801aa7f1  mov     rcx, rsi; pvarDest
0x1801aa7f4  call    cs:__imp_PropVariantCopy
0x1801aa7fa  mov     ebx, eax
0x1801aa7fc  test    eax, eax
0x1801aa7fe  jns     loc_1801AA770
0x1801aa804  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801aa80b  jz      short loc_1801AA7D4
0x1801aa80d  mov     ecx, eax; int
0x1801aa80f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801aa814  jmp     short loc_1801AA7D4
0x1801aa816  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x1801aa81a  mov     rcx, r14; pvarDest
0x1801aa81d  call    cs:__imp_PropVariantCopy
0x1801aa823  mov     ebx, eax
0x1801aa825  test    eax, eax
0x1801aa827  jns     loc_1801AA791
0x1801aa82d  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801aa834  jz      short loc_1801AA87B
0x1801aa836  mov     ecx, eax
0x1801aa838  jmp     loc_1801AA679
0x1801aa83d  add     [r8], r12
0x1801aa840  mov     rdx, r11; unsigned __int64
0x1801aa843  mov     rcx, [rbp+pvarSrc+8]; char *
0x1801aa847  lea     r8, [rdi+0D0h]; unsigned __int64 *
0x1801aa84e  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801aa853  mov     ebx, eax
0x1801aa855  test    eax, eax
0x1801aa857  jns     short loc_1801AA866
0x1801aa859  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1801aa860  jnz     short loc_1801AA836
0x1801aa862  test    eax, eax
0x1801aa864  js      short loc_1801AA87B
0x1801aa866  add     [r8], r12
0x1801aa869  mov     [rdi+60h], r12d
0x1801aa86d  mov     [rdi+0DCh], r12d
0x1801aa874  mov     [rdi+0D8h], r15d
0x1801aa87b  lea     rcx, [rbp+var_40]
0x1801aa87f  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1801aa884  lea     r11, [rsp+70h+var_s0]
0x1801aa889  mov     eax, ebx
0x1801aa88b  mov     rbx, [r11+38h]
0x1801aa88f  mov     rsi, [r11+40h]
0x1801aa893  mov     rsp, r11
0x1801aa896  pop     r15
0x1801aa898  pop     r14
0x1801aa89a  pop     r12
0x1801aa89c  pop     rdi
0x1801aa89d  pop     rbp
0x1801aa89e  retn
```
