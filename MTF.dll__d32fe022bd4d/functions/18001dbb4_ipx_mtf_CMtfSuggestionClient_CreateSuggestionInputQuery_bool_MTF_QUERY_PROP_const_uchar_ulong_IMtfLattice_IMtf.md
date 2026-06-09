# ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(bool,_MTF_QUERY_PROP const *,uchar *,ulong,IMtfLattice *,IMtfPropertyBag *,IMtfSuggestionInputQuery * *,ulong *)

- ea: `0x18001dbb4`
- end: `0x18001e062`
- name: `?_CreateSuggestionInputQuery@CMtfSuggestionClient@mtf@ipx@@IEAAJ_NPEBU_MTF_QUERY_PROP@@PEAEKPEAUIMtfLattice@@PEAUIMtfPropertyBag@@PEAPEAUIMtfSuggestionInputQuery@@PEAK@Z`
- size: `1198`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *this, unsigned __int8, const struct _MTF_QUERY_PROP *, unsigned __int8 *, unsigned int, struct IMtfLattice *, struct IMtfPropertyBag *, struct IMtfSuggestionInputQuery **, unsigned int *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016cf0`
- `0x180017a40`
- `0x1800189d0`
- `0x18001a150`
- `0x18001a450`
- `0x18001a800`

## callees

- `0x1800046d4`
- `0x180006074`
- `0x18001dbb4`
- `0x18002bc62`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001ddb4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001ddb4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001de46`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ded9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dfc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e017`
- `OLEAUT32!__imp_SysFreeString` at `0x18001de46`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ded9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dfc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e017`

## string_xrefs

- `0x18001dd92`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\MtfPrecompile.h`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::_CreateSuggestionInputQuery(
        ipx::mtf::CMtfSuggestionClient *this,
        unsigned __int8 a2,
        const struct _MTF_QUERY_PROP *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        struct IMtfLattice *a6,
        struct IMtfPropertyBag *a7,
        struct IMtfSuggestionInputQuery **a8,
        unsigned int *a9)
{
  int v11; // ebx
  OLECHAR *v12; // rdi
  struct IMtfSuggestionInputQuery **v13; // r15
  struct IMtfPropertyBag *v14; // rbx
  struct IMtfPropertyBag *v15; // rsi
  struct IMtfPropertyBag *v16; // r12
  int v17; // eax
  int v18; // r15d
  unsigned __int64 v19; // r15
  BSTR v20; // rax
  bool v21; // sf
  unsigned int v22; // esi
  int v24; // eax
  ipx::mtf::CMtfSuggestionClient *v25; // rcx
  int v26; // eax
  const char *v27; // r9
  ipx::mtf::CMtfSuggestionClient *v28; // rcx
  int v29; // eax
  ipx::mtf::CMtfSuggestionClient *v30; // rcx
  int v31; // [rsp+20h] [rbp-79h]
  int v32; // [rsp+40h] [rbp-59h] BYREF
  int v33; // [rsp+44h] [rbp-55h] BYREF
  int v34; // [rsp+48h] [rbp-51h] BYREF
  __int128 v35; // [rsp+50h] [rbp-49h]
  _DWORD v36[3]; // [rsp+60h] [rbp-39h] BYREF
  int v37; // [rsp+6Ch] [rbp-2Dh] BYREF
  __int16 v38; // [rsp+70h] [rbp-29h]
  __int16 v39; // [rsp+72h] [rbp-27h]
  int v40; // [rsp+74h] [rbp-25h]
  __int16 v41; // [rsp+78h] [rbp-21h]
  int v42; // [rsp+7Ch] [rbp-1Dh]
  struct IMtfPropertyBag *v43; // [rsp+80h] [rbp-19h]
  OLECHAR *v44; // [rsp+88h] [rbp-11h]
  struct IMtfLattice *v45; // [rsp+90h] [rbp-9h]
  int v46; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+3Fh]
  ipx::mtf::CMtfSuggestionClient *v48; // [rsp+E0h] [rbp+47h] BYREF
  unsigned int v49; // [rsp+E8h] [rbp+4Fh] BYREF
  struct IMtfPropertyBag *v50; // [rsp+F0h] [rbp+57h]

  v48 = this;
  v11 = a2;
  v12 = 0;
  v13 = a8;
  *a8 = 0;
  memset_0(&v32, 0, 0x60u);
  v32 = *(_DWORD *)a3 | 0x10000;
  v33 = *((_DWORD *)a3 + 1);
  v34 = *((_DWORD *)a3 + 2);
  v35 = 0;
  v36[0] = *((_DWORD *)a3 + 3);
  v36[1] = 0;
  v36[2] = 0;
  v37 = *((_DWORD *)a3 + 4);
  v38 = *((_WORD *)a3 + 10);
  v39 = *((_WORD *)a3 + 11);
  v40 = *((_DWORD *)a3 + 6);
  v41 = 0;
  v42 = 0;
  v43 = (struct IMtfPropertyBag *)*((_QWORD *)a3 + 4);
  v44 = (OLECHAR *)*((_QWORD *)a3 + 5);
  v45 = (struct IMtfLattice *)*((_QWORD *)a3 + 6);
  v46 = v11;
  v14 = 0;
  v50 = 0;
  v15 = 0;
  v16 = a7;
  if ( a7 )
  {
    (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)a7 + 8LL))(a7);
    v14 = v16;
    v50 = v16;
    v15 = v16;
  }
  if ( v15 )
  {
    if ( (*(_BYTE *)a3 & 1) == 0
      && (*(int (__fastcall **)(struct IMtfPropertyBag *, __int64 *, int *, __int64))(*(_QWORD *)v15 + 40LL))(
           v15,
           qword_1800350A8,
           &v33,
           4) >= 0 )
    {
      v32 |= 1u;
    }
    if ( (*(_BYTE *)a3 & 2) == 0
      && (*(int (__fastcall **)(struct IMtfPropertyBag *, __int64 *, int *, __int64))(*(_QWORD *)v15 + 40LL))(
           v15,
           qword_180035108,
           &v34,
           4) >= 0 )
    {
      v32 |= 2u;
    }
    if ( (*(_BYTE *)a3 & 8) == 0
      && (*(int (__fastcall **)(struct IMtfPropertyBag *, __int64 *, _DWORD *, __int64))(*(_QWORD *)v15 + 40LL))(
           v15,
           qword_180035088,
           v36,
           4) >= 0 )
    {
      v32 |= 8u;
    }
    if ( (*(_BYTE *)a3 & 0x40) == 0
      && (*(int (__fastcall **)(struct IMtfPropertyBag *, __int64 *, int *, __int64))(*(_QWORD *)v15 + 40LL))(
           v15,
           qword_1800350B8,
           &v37,
           4) >= 0 )
    {
      v32 |= 0x40u;
    }
    if ( (*(_DWORD *)a3 & 0x4000) != 0 )
      goto LABEL_24;
    v49 = 0;
    v17 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, __int64 *, unsigned int *))(*(_QWORD *)v15 + 32LL))(
            v15,
            qword_180035118,
            &v49);
    v18 = v17;
    if ( v17 >= 0 )
    {
      v19 = ((unsigned __int64)v49 + 1) >> 1;
      v20 = SysAllocStringLen(0, v19);
      v12 = v20;
      if ( !v20 )
      {
        v13 = a8;
LABEL_24:
        if ( (*(_DWORD *)a3 & 0x2000) == 0 )
        {
          v32 |= 0x2000u;
          v43 = v16;
        }
        goto LABEL_26;
      }
      v18 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, __int64 *, BSTR, _QWORD))(*(_QWORD *)v15 + 40LL))(
              v15,
              qword_180035118,
              v20,
              (unsigned int)(2 * v19));
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\MtfPrecompile.h",
        (const char *)(unsigned int)v17,
        v31);
    }
    v21 = v18 < 0;
    v13 = a8;
    if ( !v21 )
    {
      v32 |= 0x4000u;
      v44 = v12;
    }
    goto LABEL_24;
  }
LABEL_26:
  if ( a6 )
  {
    if ( (*(_DWORD *)a3 & 0x8000) != 0 )
    {
      v22 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80F,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)0x80070057LL,
        v31);
      SysFreeString(v12);
      if ( v14 )
        (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v14 + 16LL))(v14);
      return v22;
    }
    v32 |= 0x8000u;
    v45 = a6;
  }
  v48 = 0;
  v24 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *))Hooked_CoCreateInstance)(
          &CLSID_MtfSuggestionInputQuery,
          0,
          1,
          &GUID_dc445657_5f76_4a1a_acdc_ed5ef1be4ac5);
  v22 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x819,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v24,
      (int)&v48);
    v25 = v48;
    v48 = 0;
    if ( v25 )
      (*(void (__fastcall **)(ipx::mtf::CMtfSuggestionClient *))(*(_QWORD *)v25 + 16LL))(v25);
    SysFreeString(v12);
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v14 + 16LL))(v14);
    return v22;
  }
  v26 = (*(__int64 (__fastcall **)(ipx::mtf::CMtfSuggestionClient *, int *))(*(_QWORD *)v48 + 32LL))(v48, &v32);
  v22 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81B,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v26,
      (int)&v48);
    v28 = v48;
    v48 = 0;
    if ( v28 )
      (*(void (__fastcall **)(ipx::mtf::CMtfSuggestionClient *))(*(_QWORD *)v28 + 16LL))(v28);
    SysFreeString(v12);
    if ( v14 )
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v14 + 16LL))(v14);
    return v22;
  }
  if ( a4 )
  {
    if ( a5 )
    {
      v29 = (*(__int64 (__fastcall **)(ipx::mtf::CMtfSuggestionClient *, unsigned __int8 *))(*(_QWORD *)v48 + 72LL))(
              v48,
              a4);
      v22 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x820,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v29,
          (int)&v48);
        v30 = v48;
        v48 = 0;
        if ( v30 )
          (*(void (__fastcall **)(ipx::mtf::CMtfSuggestionClient *))(*(_QWORD *)v30 + 16LL))(v30);
        SysFreeString(v12);
        if ( v14 )
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v14 + 16LL))(v14);
        return v22;
      }
    }
  }
  if ( (v32 & 0x4000) != 0 )
  {
    *a9 = 25;
    if ( !v44 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x827,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        v27);
  }
  *v13 = v48;
  v48 = 0;
  SysFreeString(v12);
  if ( v14 )
    (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v14 + 16LL))(v14);
  return 0;
}

```

## disassembly

```asm
0x18001dbb4  mov     [rsp-8+arg_18], rbx
0x18001dbb9  mov     [rsp-8+arg_0], rcx
0x18001dbbe  push    rbp
0x18001dbbf  push    rsi
0x18001dbc0  push    rdi
0x18001dbc1  push    r12
0x18001dbc3  push    r13
0x18001dbc5  push    r14
0x18001dbc7  push    r15
0x18001dbc9  lea     rbp, [rsp-7]
0x18001dbce  sub     rsp, 0A0h
0x18001dbd5  mov     r13, r9
0x18001dbd8  mov     r14, r8
0x18001dbdb  movzx   ebx, dl
0x18001dbde  xor     edi, edi
0x18001dbe0  mov     r15, [rbp+37h+arg_38]
0x18001dbe4  mov     [r15], rdi
0x18001dbe7  xor     edx, edx; Val
0x18001dbe9  lea     r8d, [rdi+60h]; Size
0x18001dbed  lea     rcx, [rbp+37h+var_90]; void *
0x18001dbf1  call    memset_0
0x18001dbf6  mov     eax, [r14]
0x18001dbf9  bts     eax, 10h
0x18001dbfd  mov     [rbp+37h+var_90], eax
0x18001dc00  mov     eax, [r14+4]
0x18001dc04  mov     [rbp+37h+var_8C], eax
0x18001dc07  mov     eax, [r14+8]
0x18001dc0b  mov     [rbp+37h+var_88], eax
0x18001dc0e  xorps   xmm0, xmm0
0x18001dc11  movdqa  [rbp+37h+var_80], xmm0
0x18001dc16  mov     eax, [r14+0Ch]
0x18001dc1a  mov     [rbp+37h+var_70], eax
0x18001dc1d  mov     [rbp+37h+var_6C], edi
0x18001dc20  mov     [rbp+37h+var_68], edi
0x18001dc23  mov     eax, [r14+10h]
0x18001dc27  mov     [rbp+37h+var_64], eax
0x18001dc2a  movzx   eax, word ptr [r14+14h]
0x18001dc2f  mov     [rbp+37h+var_60], ax
0x18001dc33  movzx   eax, word ptr [r14+16h]
0x18001dc38  mov     [rbp+37h+var_5E], ax
0x18001dc3c  mov     eax, [r14+18h]
0x18001dc40  mov     [rbp+37h+var_5C], eax
0x18001dc43  mov     [rbp+37h+var_58], di
0x18001dc47  mov     [rbp+37h+var_54], edi
0x18001dc4a  mov     rax, [r14+20h]
0x18001dc4e  mov     [rbp+37h+var_50], rax
0x18001dc52  mov     rax, [r14+28h]
0x18001dc56  mov     [rbp+37h+var_48], rax
0x18001dc5a  mov     rax, [r14+30h]
0x18001dc5e  mov     [rbp+37h+var_40], rax
0x18001dc62  mov     [rbp+37h+var_38], ebx
0x18001dc65  mov     ebx, edi
0x18001dc67  mov     [rbp+37h+arg_10], rbx
0x18001dc6b  mov     esi, edi
0x18001dc6d  mov     r12, [rbp+37h+arg_30]
0x18001dc71  test    r12, r12
0x18001dc74  jz      short loc_18001DC91
0x18001dc76  mov     rax, [r12]
0x18001dc7a  mov     rcx, r12
0x18001dc7d  mov     rax, [rax+8]
0x18001dc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc86  nop
0x18001dc87  mov     rbx, r12
0x18001dc8a  mov     [rbp+37h+arg_10], rbx
0x18001dc8e  mov     rsi, r12
0x18001dc91  mov     [rbp+37h+var_A0], rdi
0x18001dc95  test    rsi, rsi
0x18001dc98  jz      loc_18001DE0F
0x18001dc9e  test    byte ptr [r14], 1
0x18001dca2  jnz     short loc_18001DCCC
0x18001dca4  mov     rax, [rsi]
0x18001dca7  mov     r9d, 4
0x18001dcad  lea     r8, [rbp+37h+var_8C]
0x18001dcb1  lea     rdx, qword_1800350A8
0x18001dcb8  mov     rcx, rsi
0x18001dcbb  mov     rax, [rax+28h]
0x18001dcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcc4  test    eax, eax
0x18001dcc6  js      short loc_18001DCCC
0x18001dcc8  or      [rbp+37h+var_90], 1
0x18001dccc  test    byte ptr [r14], 2
0x18001dcd0  jnz     short loc_18001DCFA
0x18001dcd2  mov     rax, [rsi]
0x18001dcd5  mov     r9d, 4
0x18001dcdb  lea     r8, [rbp+37h+var_88]
0x18001dcdf  lea     rdx, qword_180035108
0x18001dce6  mov     rcx, rsi
0x18001dce9  mov     rax, [rax+28h]
0x18001dced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcf2  test    eax, eax
0x18001dcf4  js      short loc_18001DCFA
0x18001dcf6  or      [rbp+37h+var_90], 2
0x18001dcfa  test    byte ptr [r14], 8
0x18001dcfe  jnz     short loc_18001DD28
0x18001dd00  mov     rax, [rsi]
0x18001dd03  mov     r9d, 4
0x18001dd09  lea     r8, [rbp+37h+var_70]
0x18001dd0d  lea     rdx, qword_180035088
0x18001dd14  mov     rcx, rsi
0x18001dd17  mov     rax, [rax+28h]
0x18001dd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd20  test    eax, eax
0x18001dd22  js      short loc_18001DD28
0x18001dd24  or      [rbp+37h+var_90], 8
0x18001dd28  test    byte ptr [r14], 40h
0x18001dd2c  jnz     short loc_18001DD56
0x18001dd2e  mov     rax, [rsi]
0x18001dd31  mov     r9d, 4
0x18001dd37  lea     r8, [rbp+37h+var_64]
0x18001dd3b  lea     rdx, qword_1800350B8
0x18001dd42  mov     rcx, rsi
0x18001dd45  mov     rax, [rax+28h]
0x18001dd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd4e  test    eax, eax
0x18001dd50  js      short loc_18001DD56
0x18001dd52  or      [rbp+37h+var_90], 40h
0x18001dd56  test    dword ptr [r14], 4000h
0x18001dd5d  jnz     loc_18001DDFE
0x18001dd63  mov     [rbp+37h+arg_8], 0
0x18001dd6a  mov     rax, [rsi]
0x18001dd6d  lea     r8, [rbp+37h+arg_8]
0x18001dd71  lea     rdx, qword_180035118
0x18001dd78  mov     rcx, rsi
0x18001dd7b  mov     rax, [rax+20h]
0x18001dd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd84  mov     r15d, eax
0x18001dd87  test    eax, eax
0x18001dd89  jns     short loc_18001DDA5
0x18001dd8b  mov     rcx, [rbp+3Fh]; this
0x18001dd8f  mov     r9d, eax; char *
0x18001dd92  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001dd99  mov     edx, 0DAh; void *
0x18001dd9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dda3  jmp     short loc_18001DDE6
0x18001dda5  mov     r15d, [rbp+37h+arg_8]
0x18001dda9  inc     r15
0x18001ddac  shr     r15, 1
0x18001ddaf  mov     edx, r15d; ui
0x18001ddb2  xor     ecx, ecx; strIn
0x18001ddb4  call    cs:__imp_SysAllocStringLen
0x18001ddba  mov     rdi, rax
0x18001ddbd  mov     [rbp+37h+var_A0], rax
0x18001ddc1  test    rax, rax
0x18001ddc4  jz      short loc_18001DDFA
0x18001ddc6  mov     rax, [rsi]
0x18001ddc9  lea     r9d, [r15+r15]
0x18001ddcd  mov     r8, rdi
0x18001ddd0  lea     rdx, qword_180035118
0x18001ddd7  mov     rcx, rsi
0x18001ddda  mov     rax, [rax+28h]
0x18001ddde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dde3  mov     r15d, eax
0x18001dde6  test    r15d, r15d
0x18001dde9  mov     r15, [rbp+37h+arg_38]
0x18001dded  js      short loc_18001DDFE
0x18001ddef  bts     [rbp+37h+var_90], 0Eh
0x18001ddf4  mov     [rbp+37h+var_48], rdi
0x18001ddf8  jmp     short loc_18001DDFE
0x18001ddfa  mov     r15, [rbp+37h+arg_38]
0x18001ddfe  mov     eax, 2000h
0x18001de03  test    [r14], eax
0x18001de06  jnz     short loc_18001DE0F
0x18001de08  or      [rbp+37h+var_90], eax
0x18001de0b  mov     [rbp+37h+var_50], r12
0x18001de0f  mov     rax, [rbp+37h+arg_28]
0x18001de13  xor     r12d, r12d
0x18001de16  test    rax, rax
0x18001de19  jz      short loc_18001DE70
0x18001de1b  mov     ecx, 8000h
0x18001de20  test    [r14], ecx
0x18001de23  jz      short loc_18001DE69
0x18001de25  mov     rcx, [rbp+3Fh]; this
0x18001de29  mov     esi, 80070057h
0x18001de2e  mov     r9d, esi; char *
0x18001de31  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001de38  mov     edx, 80Fh; void *
0x18001de3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de42  nop
0x18001de43  mov     rcx, rdi; bstrString
0x18001de46  call    cs:__imp_SysFreeString
0x18001de4c  nop
0x18001de4d  test    rbx, rbx
0x18001de50  jz      short loc_18001DE62
0x18001de52  mov     rdx, [rbx]
0x18001de55  mov     rcx, rbx
0x18001de58  mov     rax, [rdx+10h]
0x18001de5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de61  nop
0x18001de62  mov     eax, esi
0x18001de64  jmp     loc_18001E035
0x18001de69  or      [rbp+37h+var_90], ecx
0x18001de6c  mov     [rbp+37h+var_40], rax
0x18001de70  mov     [rbp+37h+arg_0], r12
0x18001de74  lea     rax, [rbp+37h+arg_0]
0x18001de78  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18001de7d  lea     r9, _GUID_dc445657_5f76_4a1a_acdc_ed5ef1be4ac5
0x18001de84  xor     edx, edx
0x18001de86  lea     r8d, [rdx+1]
0x18001de8a  lea     rcx, CLSID_MtfSuggestionInputQuery
0x18001de91  mov     rax, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18001de98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de9d  mov     esi, eax
0x18001de9f  test    eax, eax
0x18001dea1  jns     short loc_18001DEFA
0x18001dea3  mov     rcx, [rbp+3Fh]; this
0x18001dea7  mov     r9d, eax; char *
0x18001deaa  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001deb1  mov     edx, 819h; void *
0x18001deb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001debb  nop
0x18001debc  mov     rcx, [rbp+37h+arg_0]
0x18001dec0  mov     [rbp+37h+arg_0], r12
0x18001dec4  test    rcx, rcx
0x18001dec7  jz      short loc_18001DED6
0x18001dec9  mov     rax, [rcx]
0x18001decc  mov     rax, [rax+10h]
0x18001ded0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ded5  nop
0x18001ded6  mov     rcx, rdi; bstrString
0x18001ded9  call    cs:__imp_SysFreeString
0x18001dedf  nop
0x18001dee0  test    rbx, rbx
0x18001dee3  jz      short loc_18001DEF5
0x18001dee5  mov     rax, [rbx]
0x18001dee8  mov     rcx, rbx
0x18001deeb  mov     rax, [rax+10h]
0x18001deef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001def4  nop
0x18001def5  jmp     loc_18001DE62
0x18001defa  mov     rcx, [rbp+37h+arg_0]
0x18001defe  mov     rax, [rcx]
0x18001df01  lea     rdx, [rbp+37h+var_90]
0x18001df05  mov     rax, [rax+20h]
0x18001df09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df0e  mov     esi, eax
0x18001df10  test    eax, eax
0x18001df12  jns     short loc_18001DF6B
0x18001df14  mov     rcx, [rbp+3Fh]; this
0x18001df18  mov     r9d, eax; char *
0x18001df1b  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001df22  mov     edx, 81Bh; void *
0x18001df27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df2c  nop
0x18001df2d  mov     rcx, [rbp+37h+arg_0]
0x18001df31  mov     [rbp+37h+arg_0], r12
0x18001df35  test    rcx, rcx
0x18001df38  jz      short loc_18001DF47
0x18001df3a  mov     rax, [rcx]
0x18001df3d  mov     rax, [rax+10h]
0x18001df41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df46  nop
0x18001df47  mov     rcx, rdi; bstrString
0x18001df4a  call    cs:__imp_SysFreeString
0x18001df50  nop
0x18001df51  test    rbx, rbx
0x18001df54  jz      short loc_18001DF66
0x18001df56  mov     rax, [rbx]
0x18001df59  mov     rcx, rbx
0x18001df5c  mov     rax, [rax+10h]
0x18001df60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df65  nop
0x18001df66  jmp     loc_18001DE62
0x18001df6b  test    r13, r13
0x18001df6e  jz      short loc_18001DFE9
0x18001df70  mov     r8d, [rbp+37h+arg_20]
0x18001df74  test    r8d, r8d
0x18001df77  jz      short loc_18001DFE9
0x18001df79  mov     rcx, [rbp+37h+arg_0]
0x18001df7d  mov     rax, [rcx]
0x18001df80  mov     rdx, r13
0x18001df83  mov     rax, [rax+48h]
0x18001df87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df8c  mov     esi, eax
0x18001df8e  test    eax, eax
0x18001df90  jns     short loc_18001DFE9
0x18001df92  mov     rcx, [rbp+3Fh]; this
0x18001df96  mov     r9d, eax; char *
0x18001df99  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18001dfa0  mov     edx, 820h; void *
0x18001dfa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dfaa  nop
0x18001dfab  mov     rcx, [rbp+37h+arg_0]
0x18001dfaf  mov     [rbp+37h+arg_0], r12
0x18001dfb3  test    rcx, rcx
0x18001dfb6  jz      short loc_18001DFC5
0x18001dfb8  mov     rax, [rcx]
0x18001dfbb  mov     rax, [rax+10h]
0x18001dfbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfc4  nop
0x18001dfc5  mov     rcx, rdi; bstrString
0x18001dfc8  call    cs:__imp_SysFreeString
0x18001dfce  nop
0x18001dfcf  test    rbx, rbx
0x18001dfd2  jz      short loc_18001DFE4
0x18001dfd4  mov     rax, [rbx]
0x18001dfd7  mov     rcx, rbx
0x18001dfda  mov     rax, [rax+10h]
0x18001dfde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfe3  nop
0x18001dfe4  jmp     loc_18001DE62
  ... truncated ...
```
