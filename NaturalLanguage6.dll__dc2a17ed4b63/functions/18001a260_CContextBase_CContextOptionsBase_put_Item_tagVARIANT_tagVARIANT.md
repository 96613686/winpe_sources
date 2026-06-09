# CContextBase::CContextOptionsBase::put_Item(tagVARIANT,tagVARIANT)

- ea: `0x18001a260`
- end: `0x18001a5ed`
- name: `?put_Item@CContextOptionsBase@CContextBase@@UEAAJUtagVARIANT@@0@Z`
- size: `909`
- prototype: `__int64 __fastcall(CContextBase::CContextOptionsBase *__hidden this, VARIANTARG *pvargSrc, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180003894`
- `0x180005190`
- `0x180019a50`
- `0x180019b10`
- `0x18001a0d8`
- `0x18001a110`
- `0x18001a168`
- `0x18001a260`
- `0x18001a5f4`
- `0x18001a640`
- `0x1800330a4`
- `0x180037018`
- `0x18005e260`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001a2ad`
- `OLEAUT32!__imp_VariantInit` at `0x18001a2ad`
- `OLEAUT32!__imp_VariantClear` at `0x18001a3a2`
- `OLEAUT32!__imp_VariantClear` at `0x18001a496`
- `OLEAUT32!__imp_VariantClear` at `0x18001a3a2`
- `OLEAUT32!__imp_VariantClear` at `0x18001a496`
- `OLEAUT32!__imp_VariantCopy` at `0x18001a2bb`
- `OLEAUT32!__imp_VariantCopy` at `0x18001a2bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CContextBase::CContextOptionsBase::put_Item(
        CContextBase::CContextOptionsBase *this,
        VARIANTARG *pvargSrc,
        struct tagVARIANT *a3)
{
  HRESULT v7; // eax
  unsigned int v8; // edx
  int lVal; // edi
  volatile signed __int32 *v10; // rbx
  char v11; // r14
  __int64 v12; // rax
  unsigned int v13; // edx
  _bstr_t::Data_t *v14; // rcx
  const unsigned __int16 *bstrVal; // rdx
  HRESULT v16; // eax
  __int64 result; // rax
  CContextBase *v18; // rcx
  unsigned int v19; // edi
  HRESULT v20; // eax
  const unsigned __int16 *APIName; // rax
  __int128 v22; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  unsigned int v24; // ebx
  unsigned int v25; // edx
  _com_error *v26; // rbx
  volatile signed __int32 *v27; // [rsp+28h] [rbp-130h] BYREF
  _bstr_t::Data_t *v28; // [rsp+30h] [rbp-128h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-120h] BYREF
  VARIANTARG pvargSrca; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v31; // [rsp+80h] [rbp-D8h]
  _com_error *v32; // [rsp+88h] [rbp-D0h] BYREF
  VARIANTARG v33; // [rsp+90h] [rbp-C8h] BYREF
  VARIANTARG v34; // [rsp+B0h] [rbp-A8h] BYREF
  VARIANTARG v35; // [rsp+D0h] [rbp-88h] BYREF
  VARIANTARG v36; // [rsp+F0h] [rbp-68h]
  void *retaddr; // [rsp+158h] [rbp+0h]

  v31 = -2;
  if ( ProcessingOptions6::IProcessingOptions::GetIsReadOnly((struct IUnknown *)this) )
    return 2147500037LL;
  try
  {
    VariantInit(&pvarg);
    v7 = VariantCopy(&pvarg, pvargSrc);
    if ( v7 < 0 )
      _com_issue_error(v7);
    lVal = -1;
    v10 = 0;
    v27 = 0;
    LOBYTE(v8) = 0;
    v11 = 0;
    if ( pvargSrc->vt == 2 || pvargSrc->vt == 3 )
    {
      lVal = _variant_t::operator long((struct _variant_t *)&pvarg);
      if ( lVal < 0 )
LABEL_41:
        lVal = pvargSrc->lVal;
    }
    else
    {
      if ( pvargSrc->vt == 8 )
      {
        v12 = _variant_t::operator _bstr_t((struct _variant_t *)&pvarg, (_bstr_t *)&v28);
        if ( *(_QWORD *)v12 )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v12 + 16LL));
        v10 = *(volatile signed __int32 **)v12;
        v27 = *(volatile signed __int32 **)v12;
        v14 = v28;
        if ( v28 )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)v28 + 4) && v14 )
            _bstr_t::Data_t::`scalar deleting destructor'(v14, v13);
          v28 = 0;
        }
        if ( v10 )
          bstrVal = *(const unsigned __int16 **)v10;
        else
          bstrVal = 0;
        if ( bstrVal )
        {
LABEL_15:
          LOBYTE(v8) = CContextBase::SetAPIVal(*((CContextBase **)this + 6), bstrVal, (struct _variant_t *)a3);
          goto LABEL_16;
        }
LABEL_26:
        bstrVal = pvargSrc->bstrVal;
        if ( !bstrVal )
          goto LABEL_31;
        goto LABEL_15;
      }
      v18 = (CContextBase *)((unsigned int)pvargSrc->vt - 18);
      if ( pvargSrc->vt != 18 )
      {
        v18 = (CContextBase *)((unsigned int)pvargSrc->vt - 19);
        if ( pvargSrc->vt != 19 )
        {
          if ( pvargSrc->vt != 16402 )
          {
LABEL_16:
            if ( (_BYTE)v8 )
            {
              if ( v10 )
              {
                if ( !_InterlockedDecrement(v10 + 4) )
                  _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v10, v8);
                v27 = 0;
              }
              v16 = VariantClear(&pvarg);
              if ( v16 < 0 )
                _com_issue_error(v16);
              return 0;
            }
            if ( !v11 )
            {
LABEL_31:
              v33 = *a3;
              pvargSrca = *pvargSrc;
              v19 = ProcessingOptions6::OptionsBase::put_Item((struct IUnknown *)this, &pvargSrca, &v33);
              if ( v10 )
              {
                if ( !_InterlockedDecrement(v10 + 4) )
                  _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v10, 0);
                v27 = 0;
              }
              v20 = VariantClear(&pvarg);
              _com_util::CheckError(v20);
              return v19;
            }
            goto LABEL_46;
          }
          goto LABEL_26;
        }
        goto LABEL_41;
      }
    }
    v11 = 1;
    if ( lVal < 0 )
      lVal = pvargSrc->uiVal;
    APIName = CContextBase::GetAPIName(v18, lVal);
    if ( !APIName )
    {
LABEL_46:
      if ( lVal < 52 )
      {
        _bstr_t::_Free(&v27, v8);
        _variant_t::~_variant_t(&pvarg);
        return 2147500037LL;
      }
      else
      {
        v22 = *(_OWORD *)&a3->vt;
        pRecInfo = a3->pRecInfo;
        v36 = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)&pvargSrca, lVal - 52, 3u);
        *(_OWORD *)&v34.vt = v22;
        v34.pRecInfo = pRecInfo;
        v35 = v36;
        v24 = ProcessingOptions6::OptionsBase::put_Item((struct IUnknown *)this, &v35, &v34);
        _variant_t::~_variant_t(&pvargSrca);
        _bstr_t::_Free(&v27, v25);
        _variant_t::~_variant_t(&pvarg);
        return v24;
      }
    }
    bstrVal = APIName;
    goto LABEL_15;
  }
  catch ( _com_error *v32 )
  {
    v26 = v32;
    ImxTraceCatch(1, *((unsigned int *)v32 + 2), retaddr);
    return *((unsigned int *)v26 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x18001a260  mov     rax, rsp
0x18001a263  push    rdi
0x18001a264  push    r12
0x18001a266  push    r13
0x18001a268  push    r14
0x18001a26a  push    r15
0x18001a26c  sub     rsp, 130h
0x18001a273  mov     qword ptr [rax-0D8h], 0FFFFFFFFFFFFFFFEh
0x18001a27e  mov     [rax+8], rbx
0x18001a282  mov     [rax+10h], rsi
0x18001a286  movaps  xmmword ptr [rax-38h], xmm6
0x18001a28a  movaps  xmmword ptr [rax-48h], xmm7
0x18001a28e  mov     r12, r8
0x18001a291  mov     rsi, rdx
0x18001a294  mov     r15, rcx
0x18001a297  xor     r13d, r13d
0x18001a29a  call    ?GetIsReadOnly@IProcessingOptions@ProcessingOptions6@@QEAAFXZ; ProcessingOptions6::IProcessingOptions::GetIsReadOnly(void)
0x18001a29f  test    ax, ax
0x18001a2a2  jnz     loc_18001A4AA
0x18001a2a8  lea     rcx, [rsp+158h+pvarg]; pvarg
0x18001a2ad  call    cs:__imp_VariantInit
0x18001a2b3  mov     rdx, rsi; pvargSrc
0x18001a2b6  lea     rcx, [rsp+158h+pvarg]; pvargDest
0x18001a2bb  call    cs:__imp_VariantCopy
0x18001a2c1  test    eax, eax
0x18001a2c3  js      loc_18001A4B4
0x18001a2c9  or      edi, 0FFFFFFFFh
0x18001a2cc  mov     [rsp+158h+var_134], edi
0x18001a2d0  mov     ebx, r13d
0x18001a2d3  mov     [rsp+158h+var_130], rbx
0x18001a2d8  mov     dl, r13b
0x18001a2db  mov     [rsp+158h+var_138], dl
0x18001a2df  mov     r14b, r13b
0x18001a2e2  mov     [rsp+158h+var_137], r13b
0x18001a2e7  movzx   ecx, word ptr [rsi]
0x18001a2ea  sub     ecx, 2
0x18001a2ed  jz      loc_18001A4DA
0x18001a2f3  sub     ecx, 1
0x18001a2f6  jz      loc_18001A4DA
0x18001a2fc  sub     ecx, 5
0x18001a2ff  jnz     loc_18001A3D9
0x18001a305  lea     rdx, [rsp+158h+var_128]; this
0x18001a30a  lea     rcx, [rsp+158h+pvarg]; struct _variant_t *
0x18001a30f  call    ??B_variant_t@@QEBA?AV_bstr_t@@XZ; _variant_t::operator _bstr_t(void)
0x18001a314  nop
0x18001a315  mov     rcx, [rax]
0x18001a318  test    rcx, rcx
0x18001a31b  jz      short loc_18001A321
0x18001a31d  lock inc dword ptr [rcx+10h]
0x18001a321  mov     rbx, [rax]
0x18001a324  mov     [rsp+158h+var_130], rbx
0x18001a329  mov     rcx, [rsp+158h+var_128]; this
0x18001a32e  test    rcx, rcx
0x18001a331  jz      short loc_18001A350
0x18001a333  or      eax, 0FFFFFFFFh
0x18001a336  lock xadd [rcx+10h], eax
0x18001a33b  sub     eax, 1
0x18001a33e  mov     [rsp+158h+arg_18], eax
0x18001a345  jz      loc_18001A410
0x18001a34b  mov     [rsp+158h+var_128], r13
0x18001a350  test    rbx, rbx
0x18001a353  jz      loc_18001A4D2
0x18001a359  mov     rdx, [rbx]; unsigned __int16 *
0x18001a35c  test    rdx, rdx
0x18001a35f  jz      loc_18001A3F3
0x18001a365  mov     r8, r12; struct _variant_t *
0x18001a368  mov     rcx, [r15+30h]; this
0x18001a36c  call    ?SetAPIVal@CContextBase@@QEAA_NPEBGAEAV_variant_t@@@Z; CContextBase::SetAPIVal(ushort const *,_variant_t &)
0x18001a371  mov     [rsp+158h+var_138], al
0x18001a375  mov     dl, al; unsigned int
0x18001a377  test    dl, dl
0x18001a379  jz      loc_18001A423
0x18001a37f  test    rbx, rbx
0x18001a382  jz      short loc_18001A39D
0x18001a384  or      eax, 0FFFFFFFFh
0x18001a387  lock xadd [rbx+10h], eax
0x18001a38c  sub     eax, 1
0x18001a38f  mov     [rsp+158h+arg_18], eax
0x18001a396  jz      short loc_18001A401
0x18001a398  mov     [rsp+158h+var_130], r13
0x18001a39d  lea     rcx, [rsp+158h+pvarg]; pvarg
0x18001a3a2  call    cs:__imp_VariantClear
0x18001a3a8  test    eax, eax
0x18001a3aa  js      loc_18001A4BB
0x18001a3b0  xor     eax, eax
0x18001a3b2  lea     r11, [rsp+158h+var_28]
0x18001a3ba  mov     rbx, [r11+30h]
0x18001a3be  mov     rsi, [r11+38h]
0x18001a3c2  movaps  xmm6, xmmword ptr [r11-10h]
0x18001a3c7  movaps  xmm7, xmmword ptr [r11-20h]
0x18001a3cc  mov     rsp, r11
0x18001a3cf  pop     r15
0x18001a3d1  pop     r14
0x18001a3d3  pop     r13
0x18001a3d5  pop     r12
0x18001a3d7  pop     rdi
0x18001a3d8  retn
0x18001a3d9  sub     ecx, 0Ah
0x18001a3dc  jz      loc_18001A4F5
0x18001a3e2  sub     ecx, 1
0x18001a3e5  jz      loc_18001A4EE
0x18001a3eb  cmp     ecx, 3FFFh
0x18001a3f1  jnz     short loc_18001A377
0x18001a3f3  mov     rdx, [rsi+8]
0x18001a3f7  test    rdx, rdx
0x18001a3fa  jz      short loc_18001A42C
0x18001a3fc  jmp     loc_18001A365
0x18001a401  test    rbx, rbx
0x18001a404  jz      short loc_18001A398
0x18001a406  mov     rcx, rbx; this
0x18001a409  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x18001a40e  jmp     short loc_18001A398
0x18001a410  test    rcx, rcx
0x18001a413  jz      loc_18001A34B
0x18001a419  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x18001a41e  jmp     loc_18001A34B
0x18001a423  test    r14b, r14b
0x18001a426  jnz     loc_18001A51D
0x18001a42c  movups  xmm0, xmmword ptr [r12]
0x18001a431  movaps  xmmword ptr [rsp+158h+var_C8], xmm0
0x18001a439  movsd   xmm1, qword ptr [r12+10h]
0x18001a440  movsd   qword ptr [rsp+158h+var_C8+10h], xmm1
0x18001a449  movups  xmm0, xmmword ptr [rsi]
0x18001a44c  movaps  xmmword ptr [rsp+158h+pvargSrc], xmm0
0x18001a451  movsd   xmm1, qword ptr [rsi+10h]
0x18001a456  movsd   qword ptr [rsp+158h+pvargSrc+10h], xmm1
0x18001a45c  lea     r8, [rsp+158h+var_C8]; VARIANTARG *
0x18001a464  lea     rdx, [rsp+158h+pvargSrc]; pvargSrc
0x18001a469  mov     rcx, r15; this
0x18001a46c  call    ?put_Item@OptionsBase@ProcessingOptions6@@UEAAJUtagVARIANT@@0@Z; ProcessingOptions6::OptionsBase::put_Item(tagVARIANT,tagVARIANT)
0x18001a471  mov     edi, eax
0x18001a473  test    rbx, rbx
0x18001a476  jz      short loc_18001A491
0x18001a478  or      edx, 0FFFFFFFFh
0x18001a47b  lock xadd [rbx+10h], edx
0x18001a480  sub     edx, 1; unsigned int
0x18001a483  mov     [rsp+158h+arg_18], edx
0x18001a48a  jz      short loc_18001A4C3
0x18001a48c  mov     [rsp+158h+var_130], r13
0x18001a491  lea     rcx, [rsp+158h+pvarg]; pvarg
0x18001a496  call    cs:__imp_VariantClear
0x18001a49c  mov     ecx, eax; int
0x18001a49e  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x18001a4a3  mov     eax, edi
0x18001a4a5  jmp     loc_18001A3B2
0x18001a4aa  mov     eax, 80004005h
0x18001a4af  jmp     loc_18001A3B2
0x18001a4b4  mov     ecx, eax; int
0x18001a4b6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001a4bb  mov     ecx, eax; int
0x18001a4bd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001a4c3  test    rbx, rbx
0x18001a4c6  jz      short loc_18001A48C
0x18001a4c8  mov     rcx, rbx; this
0x18001a4cb  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x18001a4d0  jmp     short loc_18001A48C
0x18001a4d2  mov     rdx, r13
0x18001a4d5  jmp     loc_18001A35C
0x18001a4da  lea     rcx, [rsp+158h+pvarg]; struct _variant_t *
0x18001a4df  call    ??B_variant_t@@QEBAJXZ; _variant_t::operator long(void)
0x18001a4e4  mov     edi, eax
0x18001a4e6  mov     [rsp+158h+var_134], eax
0x18001a4ea  test    eax, eax
0x18001a4ec  jns     short loc_18001A4F5
0x18001a4ee  mov     edi, [rsi+8]
0x18001a4f1  mov     [rsp+158h+var_134], edi
0x18001a4f5  mov     r14b, 1
0x18001a4f8  mov     [rsp+158h+var_137], r14b
0x18001a4fd  test    edi, edi
0x18001a4ff  jns     short loc_18001A509
0x18001a501  movzx   edi, word ptr [rsi+8]
0x18001a505  mov     [rsp+158h+var_134], edi
0x18001a509  mov     edx, edi; int
0x18001a50b  call    ?GetAPIName@CContextBase@@QEBAPEBGJ@Z; CContextBase::GetAPIName(long)
0x18001a510  test    rax, rax
0x18001a513  jz      short loc_18001A51D
0x18001a515  mov     rdx, rax
0x18001a518  jmp     loc_18001A365
0x18001a51d  cmp     edi, 34h ; '4'
0x18001a520  jl      loc_18001A5C2
0x18001a526  movups  xmm6, xmmword ptr [r12]
0x18001a52b  movsd   xmm7, qword ptr [r12+10h]
0x18001a532  mov     r8d, 3; unsigned __int16
0x18001a538  lea     edx, [rdi-34h]; int
0x18001a53b  lea     rcx, [rsp+158h+pvargSrc]; this
0x18001a540  call    ??0_variant_t@@QEAA@JG@Z; _variant_t::_variant_t(long,ushort)
0x18001a545  nop
0x18001a546  movups  xmm0, xmmword ptr [rax]
0x18001a549  movups  [rsp+158h+var_68], xmm0
0x18001a551  movsd   xmm1, qword ptr [rax+10h]
0x18001a556  movsd   [rsp+158h+var_58], xmm1
0x18001a55f  movaps  xmmword ptr [rsp+158h+var_A8], xmm6
0x18001a567  movsd   qword ptr [rsp+158h+var_A8+10h], xmm7
0x18001a570  movaps  xmmword ptr [rsp+158h+var_88], xmm0
0x18001a578  movsd   qword ptr [rsp+158h+var_88+10h], xmm1
0x18001a581  lea     r8, [rsp+158h+var_A8]; VARIANTARG *
0x18001a589  lea     rdx, [rsp+158h+var_88]; pvargSrc
0x18001a591  mov     rcx, r15; this
0x18001a594  call    ?put_Item@OptionsBase@ProcessingOptions6@@UEAAJUtagVARIANT@@0@Z; ProcessingOptions6::OptionsBase::put_Item(tagVARIANT,tagVARIANT)
0x18001a599  mov     ebx, eax
0x18001a59b  lea     rcx, [rsp+158h+pvargSrc]; this
0x18001a5a0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18001a5a5  nop
0x18001a5a6  lea     rcx, [rsp+158h+var_130]; this
0x18001a5ab  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001a5b0  nop
0x18001a5b1  lea     rcx, [rsp+158h+pvarg]; this
0x18001a5b6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18001a5bb  mov     eax, ebx
0x18001a5bd  jmp     loc_18001A3B2
0x18001a5c2  lea     rcx, [rsp+158h+var_130]; this
0x18001a5c7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001a5cc  nop
0x18001a5cd  lea     rcx, [rsp+158h+pvarg]; this
0x18001a5d2  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18001a5d7  mov     eax, 80004005h
0x18001a5dc  jmp     loc_18001A3B2
0x18001a5e1  mov     eax, [rsp+158h+arg_18]
0x18001a5e8  jmp     loc_18001A3B2
```
