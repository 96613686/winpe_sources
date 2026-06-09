# ProcessingOptions6::OptionsBase::put_Item(tagVARIANT,tagVARIANT)

- ea: `0x180019b10`
- end: `0x180019e88`
- name: `?put_Item@OptionsBase@ProcessingOptions6@@UEAAJUtagVARIANT@@0@Z`
- size: `888`
- prototype: `__int64 __fastcall(ProcessingOptions6::OptionsBase *__hidden this, VARIANTARG *pvargSrc, VARIANTARG *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001a260`

## callees

- `0x1800034a4`
- `0x180003704`
- `0x180005190`
- `0x180019a50`
- `0x180019b10`
- `0x18001a07c`
- `0x18001a0d8`
- `0x18001a110`
- `0x18001a168`
- `0x18001a5f4`
- `0x18002ed80`
- `0x18002ee48`
- `0x180037018`
- `0x18003707c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180019b52`
- `OLEAUT32!__imp_VariantInit` at `0x180019c44`
- `OLEAUT32!__imp_VariantInit` at `0x180019b52`
- `OLEAUT32!__imp_VariantInit` at `0x180019c44`
- `OLEAUT32!__imp_VariantClear` at `0x180019c86`
- `OLEAUT32!__imp_VariantClear` at `0x180019cbb`
- `OLEAUT32!__imp_VariantClear` at `0x180019d38`
- `OLEAUT32!__imp_VariantClear` at `0x180019c86`
- `OLEAUT32!__imp_VariantClear` at `0x180019cbb`
- `OLEAUT32!__imp_VariantClear` at `0x180019d38`
- `OLEAUT32!__imp_VariantCopy` at `0x180019b60`
- `OLEAUT32!__imp_VariantCopy` at `0x180019c52`
- `OLEAUT32!__imp_VariantCopy` at `0x180019c73`
- `OLEAUT32!__imp_VariantCopy` at `0x180019b60`
- `OLEAUT32!__imp_VariantCopy` at `0x180019c52`
- `OLEAUT32!__imp_VariantCopy` at `0x180019c73`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ProcessingOptions6::OptionsBase::put_Item(
        struct IUnknown *this,
        VARIANTARG *pvargSrc,
        VARIANTARG *a3)
{
  HRESULT v7; // eax
  unsigned int v8; // edx
  int uiVal; // ebx
  volatile signed __int32 *v10; // rdi
  const unsigned __int16 *bstrVal; // rsi
  __int64 v12; // rax
  _bstr_t::Data_t *v13; // rcx
  struct IUnknownVtbl *lpVtbl; // rsi
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  unsigned int v18; // edx
  HRESULT v19; // eax
  __int64 result; // rax
  HRESULT v21; // eax
  VARIANTARG *v22; // rbx
  _bstr_t *v23; // rax
  __int64 v24; // rax
  unsigned int v25; // edx
  _com_error *v26; // rbx
  _bstr_t::Data_t *v27; // [rsp+28h] [rbp-B0h] BYREF
  _bstr_t::Data_t *p_pvargDest; // [rsp+30h] [rbp-A8h] BYREF
  const unsigned __int16 *v29; // [rsp+38h] [rbp-A0h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-98h] BYREF
  VARIANTARG pvargDest; // [rsp+58h] [rbp-80h] BYREF
  __int64 v32; // [rsp+70h] [rbp-68h]
  __int64 *v33; // [rsp+78h] [rbp-60h]
  _com_error *v34; // [rsp+80h] [rbp-58h] BYREF
  volatile signed __int32 *v35; // [rsp+88h] [rbp-50h] BYREF
  VARIANTARG v36; // [rsp+90h] [rbp-48h] BYREF
  void *retaddr; // [rsp+D8h] [rbp+0h]
  __int64 v38; // [rsp+F8h] [rbp+20h] BYREF

  v32 = -2;
  if ( ProcessingOptions6::IProcessingOptions::GetIsReadOnly(this) )
    return 2147500037LL;
  try
  {
    VariantInit(&pvarg);
    v7 = VariantCopy(&pvarg, pvargSrc);
    _com_util::CheckError(v7);
    uiVal = -1;
    v10 = 0;
    v27 = 0;
    bstrVal = 0;
    v29 = 0;
    switch ( pvargSrc->vt )
    {
      case 2u:
      case 3u:
        uiVal = _variant_t::operator long((struct _variant_t *)&pvarg);
        if ( uiVal >= 0 )
          goto LABEL_15;
        break;
      case 8u:
        v12 = _variant_t::operator _bstr_t((struct _variant_t *)&pvarg, (_bstr_t *)&p_pvargDest);
        _bstr_t::operator=(&v27, v12);
        v13 = p_pvargDest;
        if ( p_pvargDest )
        {
          LODWORD(v38) = _InterlockedDecrement((volatile signed __int32 *)p_pvargDest + 4);
          if ( !(_DWORD)v38 && v13 )
            _bstr_t::Data_t::`scalar deleting destructor'(v13, v8);
          p_pvargDest = 0;
        }
        v10 = (volatile signed __int32 *)v27;
        if ( v27 )
          bstrVal = *(const unsigned __int16 **)v27;
        else
          bstrVal = 0;
        v29 = bstrVal;
LABEL_12:
        if ( !bstrVal )
        {
          bstrVal = pvargSrc->bstrVal;
          v29 = bstrVal;
          if ( !bstrVal )
            goto LABEL_39;
        }
        uiVal = ProcessingOptions6::OptionsBase::IndexFor((ProcessingOptions6::OptionsBase *)this, bstrVal);
LABEL_14:
        if ( uiVal < 0 )
        {
          if ( !bstrVal )
          {
LABEL_39:
            _bstr_t::_Free((volatile signed __int32 **)&v27, v8);
            _variant_t::~_variant_t(&pvarg);
            return 2147942487LL;
          }
          p_pvargDest = (_bstr_t::Data_t *)&pvargDest;
          v22 = _variant_t::_variant_t(&pvargDest, a3);
          v33 = &v38;
          v23 = _bstr_t::_bstr_t((_bstr_t *)&v38, bstrVal);
          v24 = ProcessingOptions6::OptionsBase::Option::Option(&v35, v23, v22);
          std::vector<ProcessingOptions6::OptionsBase::Option>::push_back(&this[3], v24);
          _variant_t::~_variant_t(&v36);
          _bstr_t::_Free(&v35, v25);
LABEL_17:
          if ( v10 )
          {
            LODWORD(v38) = _InterlockedDecrement(v10 + 4);
            if ( !(_DWORD)v38 )
              _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v10, v18);
            v27 = 0;
          }
          v19 = VariantClear(&pvarg);
          _com_util::CheckError(v19);
          return 0;
        }
LABEL_15:
        lpVtbl = this[3].lpVtbl;
        v38 = ((char *)this[4].lpVtbl - (char *)lpVtbl) >> 5;
        if ( uiVal >= (int)v38 )
        {
          if ( v10 )
          {
            LODWORD(v38) = _InterlockedDecrement(v10 + 4);
            if ( !(_DWORD)v38 )
              _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v10, v8);
            v27 = 0;
          }
          v21 = VariantClear(&pvarg);
          _com_util::CheckError(v21);
          return 2147942487LL;
        }
        VariantInit(&pvargDest);
        v15 = VariantCopy(&pvargDest, a3);
        _com_util::CheckError(v15);
        v16 = VariantCopy((VARIANTARG *)(&lpVtbl->AddRef + 4 * uiVal), &pvargDest);
        _com_util::CheckError(v16);
        v17 = VariantClear(&pvargDest);
        _com_util::CheckError(v17);
        goto LABEL_17;
      case 0x12u:
        uiVal = pvargSrc->uiVal;
        goto LABEL_14;
      case 0x13u:
        break;
      case 0x4012u:
        goto LABEL_12;
      default:
        goto LABEL_14;
    }
    uiVal = pvargSrc->lVal;
    goto LABEL_14;
  }
  catch ( _com_error *v34 )
  {
    v26 = v34;
    ImxTraceCatch(1, *((unsigned int *)v34 + 2), retaddr);
    LODWORD(v38) = *((_DWORD *)v26 + 2);
    return (unsigned int)v38;
  }
  catch ( exception )
  {
    ImxTraceCatch(2, 2147549183LL, retaddr);
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x180019b10  mov     rax, rsp
0x180019b13  push    rdi
0x180019b14  push    r12
0x180019b16  push    r13
0x180019b18  push    r14
0x180019b1a  push    r15
0x180019b1c  sub     rsp, 0B0h
0x180019b23  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x180019b2b  mov     [rax+8], rbx
0x180019b2f  mov     [rax+10h], rsi
0x180019b33  mov     r12, r8
0x180019b36  mov     r14, rdx
0x180019b39  mov     r15, rcx
0x180019b3c  call    ?GetIsReadOnly@IProcessingOptions@ProcessingOptions6@@QEAAFXZ; ProcessingOptions6::IProcessingOptions::GetIsReadOnly(void)
0x180019b41  xor     r13d, r13d
0x180019b44  test    ax, ax
0x180019b47  jnz     loc_180019D0A
0x180019b4d  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180019b52  call    cs:__imp_VariantInit
0x180019b58  mov     rdx, r14; pvargSrc
0x180019b5b  lea     rcx, [rsp+0D8h+pvarg]; pvargDest
0x180019b60  call    cs:__imp_VariantCopy
0x180019b66  mov     ecx, eax; int
0x180019b68  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x180019b6d  nop
0x180019b6e  or      ebx, 0FFFFFFFFh
0x180019b71  mov     [rsp+0D8h+var_B8], ebx
0x180019b75  mov     edi, r13d
0x180019b78  mov     [rsp+0D8h+var_B0], r13
0x180019b7d  mov     esi, r13d
0x180019b80  mov     [rsp+0D8h+var_A0], r13
0x180019b85  movzx   ecx, word ptr [r14]
0x180019b89  sub     ecx, 2
0x180019b8c  jz      loc_180019E59
0x180019b92  sub     ecx, 1
0x180019b95  jz      loc_180019E59
0x180019b9b  sub     ecx, 5
0x180019b9e  jnz     loc_180019CE7
0x180019ba4  lea     rdx, [rsp+0D8h+var_A8]; this
0x180019ba9  lea     rcx, [rsp+0D8h+pvarg]; struct _variant_t *
0x180019bae  call    ??B_variant_t@@QEBA?AV_bstr_t@@XZ; _variant_t::operator _bstr_t(void)
0x180019bb3  nop
0x180019bb4  mov     rdx, rax
0x180019bb7  lea     rcx, [rsp+0D8h+var_B0]
0x180019bbc  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180019bc1  nop
0x180019bc2  mov     rcx, [rsp+0D8h+var_A8]; this
0x180019bc7  test    rcx, rcx
0x180019bca  jz      short loc_180019BE8
0x180019bcc  or      eax, ebx
0x180019bce  lock xadd [rcx+10h], eax
0x180019bd3  sub     eax, 1
0x180019bd6  mov     dword ptr [rsp+0D8h+arg_18], eax
0x180019bdd  jz      loc_180019DE7
0x180019be3  mov     [rsp+0D8h+var_A8], r13
0x180019be8  mov     rdi, [rsp+0D8h+var_B0]
0x180019bed  test    rdi, rdi
0x180019bf0  jz      loc_180019E10
0x180019bf6  mov     rsi, [rdi]
0x180019bf9  mov     [rsp+0D8h+var_A0], rsi
0x180019bfe  test    rsi, rsi
0x180019c01  jz      loc_180019E1F
0x180019c07  mov     rdx, rsi; unsigned __int16 *
0x180019c0a  mov     rcx, r15; this
0x180019c0d  call    ?IndexFor@OptionsBase@ProcessingOptions6@@IEAAJPEBG@Z; ProcessingOptions6::OptionsBase::IndexFor(ushort const *)
0x180019c12  mov     ebx, eax
0x180019c14  mov     [rsp+0D8h+var_B8], eax
0x180019c18  test    ebx, ebx
0x180019c1a  js      loc_180019D4F
0x180019c20  mov     rsi, [r15+18h]
0x180019c24  mov     rax, [r15+20h]
0x180019c28  sub     rax, rsi
0x180019c2b  sar     rax, 5
0x180019c2f  mov     [rsp+0D8h+arg_18], rax
0x180019c37  cmp     ebx, eax
0x180019c39  jge     loc_180019D11
0x180019c3f  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180019c44  call    cs:__imp_VariantInit
0x180019c4a  mov     rdx, r12; pvargSrc
0x180019c4d  lea     rcx, [rsp+0D8h+pvargDest]; pvargDest
0x180019c52  call    cs:__imp_VariantCopy
0x180019c58  mov     ecx, eax; int
0x180019c5a  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x180019c5f  nop
0x180019c60  movsxd  rcx, ebx
0x180019c63  shl     rcx, 5
0x180019c67  add     rcx, 8
0x180019c6b  add     rcx, rsi; pvargDest
0x180019c6e  lea     rdx, [rsp+0D8h+pvargDest]; pvargSrc
0x180019c73  call    cs:__imp_VariantCopy
0x180019c79  mov     ecx, eax; int
0x180019c7b  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x180019c80  nop
0x180019c81  lea     rcx, [rsp+0D8h+pvargDest]; pvarg
0x180019c86  call    cs:__imp_VariantClear
0x180019c8c  mov     ecx, eax; int
0x180019c8e  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x180019c93  nop
0x180019c94  test    rdi, rdi
0x180019c97  jz      short loc_180019CB6
0x180019c99  or      eax, 0FFFFFFFFh
0x180019c9c  lock xadd [rdi+10h], eax
0x180019ca1  sub     eax, 1
0x180019ca4  mov     dword ptr [rsp+0D8h+arg_18], eax
0x180019cab  jz      loc_180019DD1
0x180019cb1  mov     [rsp+0D8h+var_B0], r13
0x180019cb6  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180019cbb  call    cs:__imp_VariantClear
0x180019cc1  mov     ecx, eax; int
0x180019cc3  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x180019cc8  xor     eax, eax
0x180019cca  lea     r11, [rsp+0D8h+var_28]
0x180019cd2  mov     rbx, [r11+30h]
0x180019cd6  mov     rsi, [r11+38h]
0x180019cda  mov     rsp, r11
0x180019cdd  pop     r15
0x180019cdf  pop     r14
0x180019ce1  pop     r13
0x180019ce3  pop     r12
0x180019ce5  pop     rdi
0x180019ce6  retn
0x180019ce7  sub     ecx, 0Ah
0x180019cea  jz      loc_180019E18
0x180019cf0  sub     ecx, 1
0x180019cf3  jz      loc_180019E71
0x180019cf9  cmp     ecx, 3FFFh
0x180019cff  jz      loc_180019BFE
0x180019d05  jmp     loc_180019C18
0x180019d0a  mov     eax, 80004005h
0x180019d0f  jmp     short loc_180019CCA
0x180019d11  test    rdi, rdi
0x180019d14  jz      short loc_180019D33
0x180019d16  or      eax, 0FFFFFFFFh
0x180019d19  lock xadd [rdi+10h], eax
0x180019d1e  sub     eax, 1
0x180019d21  mov     dword ptr [rsp+0D8h+arg_18], eax
0x180019d28  jz      loc_180019DFA
0x180019d2e  mov     [rsp+0D8h+var_B0], r13
0x180019d33  lea     rcx, [rsp+0D8h+pvarg]; pvarg
0x180019d38  call    cs:__imp_VariantClear
0x180019d3e  mov     ecx, eax; int
0x180019d40  call    ?CheckError@_com_util@@YAXJ@Z; _com_util::CheckError(long)
0x180019d45  mov     eax, 80070057h
0x180019d4a  jmp     loc_180019CCA
0x180019d4f  test    rsi, rsi
0x180019d52  jz      loc_180019E31
0x180019d58  lea     rax, [rsp+0D8h+pvargDest]
0x180019d5d  mov     [rsp+0D8h+var_A8], rax
0x180019d62  mov     rdx, r12; pvargSrc
0x180019d65  lea     rcx, [rsp+0D8h+pvargDest]; pvargDest
0x180019d6a  call    ??0_variant_t@@QEAA@AEBUtagVARIANT@@@Z; _variant_t::_variant_t(tagVARIANT const &)
0x180019d6f  mov     rbx, rax
0x180019d72  lea     rax, [rsp+0D8h+arg_18]
0x180019d7a  mov     [rsp+0D8h+var_60], rax
0x180019d7f  mov     rdx, rsi; unsigned __int16 *
0x180019d82  lea     rcx, [rsp+0D8h+arg_18]; this
0x180019d8a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180019d8f  nop
0x180019d90  mov     r8, rbx
0x180019d93  mov     rdx, rax
0x180019d96  lea     rcx, [rsp+0D8h+var_50]
0x180019d9e  call    ??0Option@OptionsBase@ProcessingOptions6@@QEAA@V_bstr_t@@V_variant_t@@@Z; ProcessingOptions6::OptionsBase::Option::Option(_bstr_t,_variant_t)
0x180019da3  nop
0x180019da4  lea     rcx, [r15+18h]
0x180019da8  mov     rdx, rax
0x180019dab  call    ?push_back@?$vector@VOption@OptionsBase@ProcessingOptions6@@V?$allocator@VOption@OptionsBase@ProcessingOptions6@@@std@@@std@@QEAAX$$QEAVOption@OptionsBase@ProcessingOptions6@@@Z; std::vector<ProcessingOptions6::OptionsBase::Option>::push_back(ProcessingOptions6::OptionsBase::Option &&)
0x180019db0  nop
0x180019db1  lea     rcx, [rsp+0D8h+var_48]; this
0x180019db9  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180019dbe  nop
0x180019dbf  lea     rcx, [rsp+0D8h+var_50]; this
0x180019dc7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180019dcc  jmp     loc_180019C94
0x180019dd1  test    rdi, rdi
0x180019dd4  jz      loc_180019CB1
0x180019dda  mov     rcx, rdi; this
0x180019ddd  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x180019de2  jmp     loc_180019CB1
0x180019de7  test    rcx, rcx
0x180019dea  jz      loc_180019BE3
0x180019df0  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x180019df5  jmp     loc_180019BE3
0x180019dfa  test    rdi, rdi
0x180019dfd  jz      loc_180019D2E
0x180019e03  mov     rcx, rdi; this
0x180019e06  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x180019e0b  jmp     loc_180019D2E
0x180019e10  mov     rsi, r13
0x180019e13  jmp     loc_180019BF9
0x180019e18  movzx   ebx, word ptr [r14+8]
0x180019e1d  jmp     short loc_180019E75
0x180019e1f  mov     rsi, [r14+8]
0x180019e23  mov     [rsp+0D8h+var_A0], rsi
0x180019e28  test    rsi, rsi
0x180019e2b  jnz     loc_180019C07
0x180019e31  lea     rcx, [rsp+0D8h+var_B0]; this
0x180019e36  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180019e3b  nop
0x180019e3c  lea     rcx, [rsp+0D8h+pvarg]; this
0x180019e41  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180019e46  mov     eax, 80070057h
0x180019e4b  jmp     loc_180019CCA
0x180019e50  mov     eax, dword ptr [rsp+0D8h+arg_18]
0x180019e57  jmp     short loc_180019E83
0x180019e59  lea     rcx, [rsp+0D8h+pvarg]; struct _variant_t *
0x180019e5e  call    ??B_variant_t@@QEBAJXZ; _variant_t::operator long(void)
0x180019e63  mov     ebx, eax
0x180019e65  mov     [rsp+0D8h+var_B8], eax
0x180019e69  test    eax, eax
0x180019e6b  jns     loc_180019C20
0x180019e71  mov     ebx, [r14+8]
0x180019e75  mov     [rsp+0D8h+var_B8], ebx
0x180019e79  jmp     loc_180019C18
0x180019e7e  mov     eax, 8000FFFFh
0x180019e83  jmp     loc_180019CCA
```
