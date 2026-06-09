# Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)

- ea: `0x180012710`
- end: `0x180012d97`
- name: `?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z`
- size: `1671`
- prototype: `__int64 __fastcall(OLECHAR *strIn, const unsigned __int16 *, const struct IXMLDOMElement *, struct Common::StringBuffer *, int *)`
- caller_count: `9`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800081ec`
- `0x1800571f0`
- `0x1800770b0`
- `0x18007f318`
- `0x180089a70`
- `0x18009acb0`
- `0x1800dd2dc`
- `0x1800de064`
- `0x1800e0950`

## callees

- `0x180012710`
- `0x180012fc8`
- `0x18001adb4`
- `0x1800207a0`
- `0x180040230`
- `0x1800807b4`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800ba45d`
- `0x1801ac010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800127dc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800127dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001278d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800128c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001278d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800128c4`
- `OLEAUT32!__imp_VariantClear` at `0x180012969`
- `OLEAUT32!__imp_VariantClear` at `0x180012969`

## string_xrefs

- `0x1800128af`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800129d9`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180012ae2`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180012afb`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180012b14`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180012b2d`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180012b46`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012b5f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012bf3`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012c30`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012c5e`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012c77`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012ce8`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012d3e`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012d5b`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Common::Xml::GetAttributeValueStringFromQuery(
        OLECHAR *strIn,
        const struct std::nothrow_t *a2,
        struct IXMLDOMElement *a3,
        struct Common::StringBuffer *a4)
{
  struct Common::StringBuffer *v4; // r15
  struct IXMLDOMElement *v5; // r12
  OLECHAR *v8; // rdi
  __int64 v9; // rcx
  OLECHAR *v10; // rax
  int v11; // esi
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, LONGLONG *); // rsi
  LONGLONG v15; // rcx
  int v16; // eax
  LONGLONG v17; // rax
  LONGLONG v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rcx
  int v20; // eax
  const void *bstrVal; // rdi
  void *v22; // rcx
  LONGLONG v23; // rcx
  __int64 v25; // rax
  bool v26; // zf
  __int64 v27; // rax
  struct IXMLDOMElementVtbl *v28; // rcx
  __int64 v29; // rdx
  BSTR v30; // rax
  unsigned int v31; // ebx
  __int64 lpVtbl_low; // rsi
  unsigned int v33; // ecx
  int v34; // edx
  unsigned int v35; // ecx
  unsigned int i; // edi
  __int64 v37; // r15
  struct IXMLDOMElementVtbl *v38; // r12
  struct IXMLDOMElementVtbl *v39; // r14
  unsigned int v40; // eax
  int v41; // eax
  struct IXMLDOMElementVtbl *lpVtbl; // rcx
  unsigned __int64 v43; // rax
  struct IXMLDOMElementVtbl *v44; // rax
  const struct std::nothrow_t *v45; // rdx
  errno_t v46; // esi
  int v47; // [rsp+28h] [rbp-49h]
  int v48; // [rsp+28h] [rbp-49h]
  const char *v49; // [rsp+30h] [rbp-41h]
  __int64 (__fastcall ***v50)(_QWORD, GUID *, LONGLONG *); // [rsp+38h] [rbp-39h] BYREF
  LONGLONG v51; // [rsp+40h] [rbp-31h]
  OLECHAR *v52; // [rsp+48h] [rbp-29h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-21h] BYREF
  __int128 v54; // [rsp+68h] [rbp-9h]
  int v55; // [rsp+78h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  LONGLONG llVal; // [rsp+E0h] [rbp+6Fh] BYREF
  const struct IXMLDOMElement *v58; // [rsp+E8h] [rbp+77h]
  struct Common::StringBuffer *v59; // [rsp+F0h] [rbp+7Fh]

  v59 = a4;
  v58 = a3;
  v4 = a4;
  v5 = a3;
  v51 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  v54 = 0;
  v55 = 0;
  if ( !a2 || !strIn )
  {
    v11 = -2147024809;
    goto LABEL_28;
  }
  if ( a4 )
    *(_DWORD *)a4 = 0;
  v50 = 0;
  llVal = 0;
  SysFreeString(0);
  v8 = 0;
  v52 = 0;
  v9 = 0x7FFFFFFF;
  v10 = strIn;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = -2147024809;
  if ( v9 )
  {
    if ( (unsigned int)(0x7FFFFFFF - v9) > 0x3FFFFFFF )
    {
      v11 = -2147024809;
    }
    else
    {
      v8 = SysAllocStringLen(strIn, 0x7FFFFFFF - (int)v9);
      v52 = v8;
      v11 = 0;
      if ( !v8 )
        v11 = -2147024882;
    }
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v11,
      v47);
  }
  else
  {
    v12 = (*(__int64 (__fastcall **)(const struct std::nothrow_t *, OLECHAR *, _QWORD))(*(_QWORD *)a2 + 296LL))(
            a2,
            v8,
            &v50);
    v11 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v12,
        v47);
    }
    else
    {
      v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
      if ( v50 )
      {
        v14 = **v50;
        v15 = llVal;
        if ( llVal )
        {
          llVal = 0;
          (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v15 + 16LL))(v15);
        }
        v16 = v14(v13, &GUID_2933bf85_7b36_11d2_b20e_00c04f983e60, &llVal);
        v11 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x53,
            (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
            (const char *)(unsigned int)v16,
            v47);
        }
        else
        {
          v17 = llVal;
          llVal = 0;
          v51 = v17;
        }
      }
      else
      {
        v51 = 0;
      }
    }
  }
  SysFreeString(v8);
  v18 = llVal;
  if ( llVal )
  {
    llVal = 0;
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
  if ( v50 )
  {
    v50 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v19)[2])(v19);
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A0,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v11,
      v47);
    goto LABEL_28;
  }
  if ( v51 )
  {
    v20 = (*(__int64 (__fastcall **)(LONGLONG, VARIANTARG *))(*(_QWORD *)v51 + 352LL))(v51, &pvarg);
    v11 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2A4,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v20,
        v47);
      goto LABEL_28;
    }
    bstrVal = pvarg.bstrVal;
    llVal = pvarg.llVal;
    if ( !pvarg.llVal )
      goto LABEL_28;
    v29 = 1073741822;
    v30 = pvarg.bstrVal;
    do
    {
      if ( !*v30 )
        break;
      ++v30;
      --v29;
    }
    while ( v29 );
    v11 = -2147024809;
    if ( !v29 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        v47);
      goto LABEL_57;
    }
    v31 = 1073741822 - v29;
    v11 = 0;
    if ( (unsigned int)(1073741822 - v29) > 0x7FFFFFFF )
      v11 = -2147024362;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22F,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v11,
        v47);
      goto LABEL_57;
    }
    lpVtbl_low = LODWORD(v5[2].lpVtbl);
    v33 = 0;
    if ( (_DWORD)lpVtbl_low )
      v33 = lpVtbl_low - 1;
    if ( v31 <= v33 && v33 <= 0x20 )
      goto LABEL_49;
    if ( v31 > 0x20 )
    {
      i = 1073741822 - v29;
    }
    else
    {
      for ( i = 8; i < v31; i *= 2 )
        ;
    }
    if ( i > 0x3FFFFFFF )
    {
      v11 = -2147023613;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070503LL,
        v47);
      goto LABEL_80;
    }
    if ( !i )
    {
      lpVtbl = v5[1].lpVtbl;
      if ( lpVtbl )
      {
        operator delete(lpVtbl, (const struct std::nothrow_t *)v29);
        v5[1].lpVtbl = 0;
        LODWORD(v5->lpVtbl) = 0;
      }
      LODWORD(v5[2].lpVtbl) = 0;
      goto LABEL_79;
    }
    v37 = i + 1;
    if ( (_DWORD)v37 == (_DWORD)lpVtbl_low )
    {
LABEL_78:
      v4 = v59;
LABEL_79:
      v11 = 0;
LABEL_80:
      if ( v11 >= 0 )
      {
        bstrVal = (const void *)llVal;
LABEL_49:
        v34 = (int)v5[2].lpVtbl;
        v35 = 0;
        if ( v34 )
          v35 = v34 - 1;
        if ( v31 <= v35
          || (v41 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)v5, v31), v11 = v41, v41 >= 0) )
        {
          LODWORD(v5->lpVtbl) = v31;
          if ( v31 )
            *((_WORD *)&v5[1].lpVtbl->QueryInterface + v31) = 0;
          v11 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v41,
            v47);
        }
        if ( v11 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x235,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v11,
            v47);
        }
        else
        {
          memcpy_0(v5[1].lpVtbl, bstrVal, 2 * v31);
          v11 = 0;
        }
        goto LABEL_57;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x232,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v11,
        v47);
LABEL_57:
      if ( v11 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2AB,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v11,
          v47);
      }
      else if ( v4 )
      {
        *(_DWORD *)v4 = 1;
      }
      goto LABEL_28;
    }
    v38 = v5[1].lpVtbl;
    if ( (unsigned int)v37 <= (unsigned int)lpVtbl_low )
    {
      v39 = v38;
      goto LABEL_74;
    }
    v43 = 2LL * (unsigned int)v37;
    if ( !is_mul_ok((unsigned int)v37, 2u) )
      v43 = -1;
    v44 = (struct IXMLDOMElementVtbl *)operator new[](v43, (const struct std::nothrow_t *)&std::nothrow);
    v39 = v44;
    if ( v44 )
    {
      v46 = memcpy_s(v44, 2 * v37, v38, 2 * lpVtbl_low);
      if ( !v46 )
      {
        operator delete(v38, v45);
LABEL_74:
        v5 = (struct IXMLDOMElement *)v58;
        LODWORD(v58[2].lpVtbl) = v37;
        v5[1].lpVtbl = v39;
        v40 = (unsigned int)v5->lpVtbl;
        if ( LODWORD(v5->lpVtbl) > i )
        {
          LODWORD(v5->lpVtbl) = i;
          *((_WORD *)&v39->QueryInterface + i) = 0;
        }
        else if ( v40 < i && !v40 )
        {
          LOWORD(v39->QueryInterface) = 0;
        }
        goto LABEL_78;
      }
      operator delete(v39, v45);
      LODWORD(v49) = v46;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        (int)"0x%08lx",
        v49);
      v11 = -2147024809;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x8007000ELL,
        v47);
      v11 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v11,
      v48);
    v4 = v59;
    v5 = (struct IXMLDOMElement *)v58;
    goto LABEL_80;
  }
  v25 = LODWORD(v5->lpVtbl);
  v26 = 2 * v25 == 0;
  v27 = 2 * v25;
  v28 = v5[1].lpVtbl;
  if ( !v26 )
  {
    do
    {
      LOBYTE(v28->QueryInterface) = 0;
      v28 = (struct IXMLDOMElementVtbl *)((char *)v28 + 1);
      --v27;
    }
    while ( v27 );
  }
LABEL_28:
  v22 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v22 )
    operator delete(v22, a2);
  VariantClear(&pvarg);
  v23 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180012710  mov     rax, rsp
0x180012713  mov     [rax+8], rbx
0x180012717  mov     [rax+20h], r9
0x18001271b  mov     [rax+18h], r8
0x18001271f  push    rbp
0x180012720  push    rsi
0x180012721  push    rdi
0x180012722  push    r12
0x180012724  push    r13
0x180012726  push    r14
0x180012728  push    r15
0x18001272a  lea     rbp, [rax-5Fh]
0x18001272e  sub     rsp, 90h
0x180012735  movaps  xmmword ptr [rax-48h], xmm6
0x180012739  mov     r15, r9
0x18001273c  mov     r12, r8
0x18001273f  mov     r14, rdx
0x180012742  mov     rbx, rcx
0x180012745  xor     r13d, r13d
0x180012748  mov     [rbp+57h+var_88], r13
0x18001274c  xorps   xmm0, xmm0
0x18001274f  xor     eax, eax
0x180012751  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180012755  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180012759  mov     word ptr [rbp+57h+pvarg], r13w
0x18001275e  xorps   xmm6, xmm6
0x180012761  movups  [rbp+57h+var_60], xmm6
0x180012765  mov     [rbp+57h+var_50], r13d
0x180012769  test    rdx, rdx
0x18001276c  jz      loc_180012D8C
0x180012772  test    rcx, rcx
0x180012775  jz      loc_180012D8C
0x18001277b  test    r9, r9
0x18001277e  jz      short loc_180012783
0x180012780  mov     [r9], r13d
0x180012783  mov     [rbp+57h+var_90], r13
0x180012787  mov     [rbp+57h+arg_8], r13
0x18001278b  xor     ecx, ecx; bstrString
0x18001278d  call    cs:__imp_SysFreeString
0x180012794  nop     dword ptr [rax+rax+00h]
0x180012799  mov     rdi, r13
0x18001279c  mov     [rbp+57h+var_80], r13
0x1800127a0  mov     ecx, 7FFFFFFFh
0x1800127a5  mov     rax, rbx
0x1800127a8  cmp     [rax], r13w
0x1800127ac  jz      short loc_1800127B8
0x1800127ae  add     rax, 2
0x1800127b2  sub     rcx, 1
0x1800127b6  jnz     short loc_1800127A8
0x1800127b8  mov     esi, 80070057h
0x1800127bd  test    rcx, rcx
0x1800127c0  cmovnz  esi, r13d
0x1800127c4  jz      short loc_1800127FD
0x1800127c6  mov     edx, 7FFFFFFFh
0x1800127cb  sub     edx, ecx; ui
0x1800127cd  cmp     edx, 3FFFFFFFh
0x1800127d3  ja      loc_180012C0D
0x1800127d9  mov     rcx, rbx; strIn
0x1800127dc  call    cs:__imp_SysAllocStringLen
0x1800127e3  nop     dword ptr [rax+rax+00h]
0x1800127e8  mov     rdi, rax
0x1800127eb  mov     [rbp+57h+var_80], rax
0x1800127ef  mov     esi, r13d
0x1800127f2  test    rax, rax
0x1800127f5  mov     eax, 8007000Eh
0x1800127fa  cmovz   esi, eax
0x1800127fd  mov     rcx, [rbp+5Fh]; this
0x180012801  test    esi, esi
0x180012803  js      loc_1800128AC
0x180012809  mov     rax, [r14]
0x18001280c  mov     rbx, [rax+128h]
0x180012813  mov     rcx, [rbp+57h+var_90]
0x180012817  test    rcx, rcx
0x18001281a  jz      short loc_18001282D
0x18001281c  mov     [rbp+57h+var_90], r13
0x180012820  mov     rax, [rcx]
0x180012823  mov     rax, [rax+10h]
0x180012827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001282c  nop
0x18001282d  lea     r8, [rbp+57h+var_90]
0x180012831  mov     rdx, rdi
0x180012834  mov     rcx, r14
0x180012837  mov     rax, rbx
0x18001283a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001283f  mov     esi, eax
0x180012841  mov     rcx, [rbp+5Fh]; this
0x180012845  test    eax, eax
0x180012847  js      loc_180012ADF
0x18001284d  mov     rbx, [rbp+57h+var_90]
0x180012851  test    rbx, rbx
0x180012854  jz      loc_1800129EF
0x18001285a  mov     rax, [rbx]
0x18001285d  mov     rsi, [rax]
0x180012860  mov     rcx, [rbp+57h+arg_8]
0x180012864  test    rcx, rcx
0x180012867  jz      short loc_18001287A
0x180012869  mov     [rbp+57h+arg_8], r13
0x18001286d  mov     rdx, [rcx]
0x180012870  mov     rax, [rdx+10h]
0x180012874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012879  nop
0x18001287a  lea     r8, [rbp+57h+arg_8]
0x18001287e  lea     rdx, _GUID_2933bf85_7b36_11d2_b20e_00c04f983e60
0x180012885  mov     rcx, rbx
0x180012888  mov     rax, rsi
0x18001288b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012890  mov     esi, eax
0x180012892  mov     rcx, [rbp+5Fh]; this
0x180012896  test    eax, eax
0x180012898  js      loc_180012B11
0x18001289e  mov     rax, [rbp+57h+arg_8]
0x1800128a2  mov     [rbp+57h+arg_8], r13
0x1800128a6  mov     [rbp+57h+var_88], rax
0x1800128aa  jmp     short loc_1800128C1
0x1800128ac  mov     r9d, esi; char *
0x1800128af  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x1800128b6  mov     edx, 49h ; 'I'; void *
0x1800128bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800128c0  nop
0x1800128c1  mov     rcx, rdi; bstrString
0x1800128c4  call    cs:__imp_SysFreeString
0x1800128cb  nop     dword ptr [rax+rax+00h]
0x1800128d0  nop
0x1800128d1  mov     rcx, [rbp+57h+arg_8]
0x1800128d5  test    rcx, rcx
0x1800128d8  jz      short loc_1800128EB
0x1800128da  mov     [rbp+57h+arg_8], r13
0x1800128de  mov     rax, [rcx]
0x1800128e1  mov     rax, [rax+10h]
0x1800128e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128ea  nop
0x1800128eb  mov     rcx, [rbp+57h+var_90]
0x1800128ef  test    rcx, rcx
0x1800128f2  jz      short loc_180012905
0x1800128f4  mov     [rbp+57h+var_90], r13
0x1800128f8  mov     rax, [rcx]
0x1800128fb  mov     rax, [rax+10h]
0x1800128ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012904  nop
0x180012905  mov     rcx, [rbp+5Fh]; this
0x180012909  test    esi, esi
0x18001290b  js      loc_1800129D6
0x180012911  mov     rcx, [rbp+57h+var_88]
0x180012915  test    rcx, rcx
0x180012918  jz      loc_1800129B6
0x18001291e  mov     rax, [rcx]
0x180012921  lea     rdx, [rbp+57h+pvarg]
0x180012925  mov     rax, [rax+160h]
0x18001292c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012931  mov     esi, eax
0x180012933  mov     rcx, [rbp+5Fh]; this
0x180012937  test    eax, eax
0x180012939  js      loc_180012AF8
0x18001293f  mov     rdi, qword ptr [rbp+57h+pvarg+8]
0x180012943  mov     [rbp+57h+arg_8], rdi
0x180012947  test    rdi, rdi
0x18001294a  jnz     loc_1800129F8
0x180012950  psrldq  xmm6, 8
0x180012955  movq    rcx, xmm6; void *
0x18001295a  test    rcx, rcx
0x18001295d  jz      short loc_180012965
0x18001295f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012964  nop
0x180012965  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180012969  call    cs:__imp_VariantClear
0x180012970  nop     dword ptr [rax+rax+00h]
0x180012975  nop
0x180012976  mov     rcx, [rbp+57h+var_88]
0x18001297a  test    rcx, rcx
0x18001297d  jz      short loc_180012990
0x18001297f  mov     [rbp+57h+var_88], r13
0x180012983  mov     rax, [rcx]
0x180012986  mov     rax, [rax+10h]
0x18001298a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001298f  nop
0x180012990  mov     eax, esi
0x180012992  mov     rbx, [rsp+0C0h+arg_0]
0x18001299a  movaps  xmm6, [rsp+0C0h+var_48+8]
0x1800129a2  add     rsp, 90h
0x1800129a9  pop     r15
0x1800129ab  pop     r14
0x1800129ad  pop     r13
0x1800129af  pop     r12
0x1800129b1  pop     rdi
0x1800129b2  pop     rsi
0x1800129b3  pop     rbp
0x1800129b4  retn
0x1800129b6  mov     eax, [r12]
0x1800129ba  add     rax, rax
0x1800129bd  mov     rcx, [r12+8]
0x1800129c2  jz      short loc_180012950
0x1800129c4  mov     byte ptr [rcx], 0
0x1800129c7  lea     rcx, [rcx+1]
0x1800129cb  sub     rax, 1
0x1800129cf  jnz     short loc_1800129C4
0x1800129d1  jmp     loc_180012950
0x1800129d6  mov     r9d, esi; char *
0x1800129d9  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x1800129e0  mov     edx, 2A0h; void *
0x1800129e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800129ea  jmp     loc_180012950
0x1800129ef  mov     [rbp+57h+var_88], r13
0x1800129f3  jmp     loc_1800128C1
0x1800129f8  mov     ecx, 3FFFFFFEh
0x1800129fd  mov     edx, ecx
0x1800129ff  mov     rax, rdi
0x180012a02  cmp     word ptr [rax], 0
0x180012a06  jz      short loc_180012A12
0x180012a08  add     rax, 2
0x180012a0c  sub     rdx, 1; struct std::nothrow_t *
0x180012a10  jnz     short loc_180012A02
0x180012a12  mov     esi, 80070057h
0x180012a17  test    rdx, rdx
0x180012a1a  cmovnz  esi, r13d
0x180012a1e  sub     rcx, rdx
0x180012a21  mov     rbx, r13
0x180012a24  test    rdx, rdx
0x180012a27  cmovnz  rbx, rcx
0x180012a2b  mov     rcx, [rbp+5Fh]; this
0x180012a2f  jz      loc_180012C74
0x180012a35  mov     eax, 80070216h
0x180012a3a  mov     esi, r13d
0x180012a3d  cmp     ebx, 7FFFFFFFh
0x180012a43  cmova   esi, eax
0x180012a46  mov     rcx, [rbp+5Fh]; this
0x180012a4a  test    esi, esi
0x180012a4c  js      loc_180012B43
0x180012a52  mov     esi, [r12+10h]
0x180012a57  lea     eax, [rsi-1]
0x180012a5a  mov     ecx, r13d
0x180012a5d  test    esi, esi
0x180012a5f  cmovnz  ecx, eax
0x180012a62  cmp     ebx, ecx
0x180012a64  ja      loc_180012B75
0x180012a6a  cmp     ecx, 20h ; ' '
0x180012a6d  ja      loc_180012B75
0x180012a73  mov     edx, [r12+10h]
0x180012a78  lea     eax, [rdx-1]
0x180012a7b  mov     ecx, r13d
0x180012a7e  test    edx, edx
0x180012a80  cmovnz  ecx, eax
0x180012a83  cmp     ebx, ecx
0x180012a85  ja      loc_180012C43
0x180012a8b  mov     [r12], ebx
0x180012a8f  test    ebx, ebx
0x180012a91  jz      short loc_180012A9F
0x180012a93  mov     edx, ebx
0x180012a95  mov     rcx, [r12+8]
0x180012a9a  mov     [rcx+rdx*2], r13w
0x180012a9f  mov     esi, r13d
0x180012aa2  mov     rcx, [rbp+5Fh]; this
0x180012aa6  test    esi, esi
0x180012aa8  js      loc_180012B5C
0x180012aae  lea     r8d, [rbx+rbx]; Size
0x180012ab2  mov     rdx, rdi; Src
0x180012ab5  mov     rcx, [r12+8]; void *
0x180012aba  call    memcpy_0
0x180012abf  mov     esi, r13d
0x180012ac2  mov     rcx, [rbp+5Fh]; this
0x180012ac6  test    esi, esi
0x180012ac8  js      short loc_180012B2A
0x180012aca  test    r15, r15
0x180012acd  jz      loc_180012950
0x180012ad3  mov     dword ptr [r15], 1
0x180012ada  jmp     loc_180012950
0x180012adf  mov     r9d, eax; char *
0x180012ae2  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180012ae9  mov     edx, 4Dh ; 'M'; void *
0x180012aee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012af3  jmp     loc_1800128C1
0x180012af8  mov     r9d, eax; char *
0x180012afb  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180012b02  mov     edx, 2A4h; void *
0x180012b07  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012b0c  jmp     loc_180012950
0x180012b11  mov     r9d, eax; char *
0x180012b14  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180012b1b  mov     edx, 53h ; 'S'; void *
0x180012b20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012b25  jmp     loc_1800128C1
0x180012b2a  mov     r9d, esi; char *
0x180012b2d  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180012b34  mov     edx, 2ABh; void *
0x180012b39  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012b3e  jmp     loc_180012950
0x180012b43  mov     r9d, esi; char *
0x180012b46  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x180012b4d  mov     edx, 22Fh; void *
0x180012b52  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012b57  jmp     loc_180012AC2
0x180012b5c  mov     r9d, esi; char *
0x180012b5f  lea     r8, aOnecoreBaseApp_67; "onecore\\base\\appmodel\\common\\widest"...
0x180012b66  mov     edx, 235h; void *
0x180012b6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012b70  jmp     loc_180012AC2
0x180012b75  cmp     ebx, 20h ; ' '
0x180012b78  ja      loc_180012C09
0x180012b7e  mov     edi, 8
0x180012b83  cmp     ebx, edi
0x180012b85  jbe     short loc_180012B8D
  ... truncated ...
```
