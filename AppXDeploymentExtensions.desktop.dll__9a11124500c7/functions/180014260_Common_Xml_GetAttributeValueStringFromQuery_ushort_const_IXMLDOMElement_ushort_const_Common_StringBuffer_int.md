# Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)

- ea: `0x180014260`
- end: `0x180014854`
- name: `?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@0AEAVStringBuffer@2@PEAH@Z`
- size: `1524`
- prototype: `__int64 __usercall@<rax>(OLECHAR *strIn@<rcx>, const unsigned __int16 *@<rdx>, struct IXMLDOMElement *@<r8>, const unsigned __int16 *@<r9>, struct Common::StringBuffer *, int *)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d6dc`
- `0x18001c400`
- `0x18001db48`
- `0x180042560`
- `0x1800598f0`
- `0x180089a70`
- `0x18008a1b0`
- `0x18009acb0`
- `0x1800e0950`
- `0x1800e9d90`
- `0x1800ec6f4`

## callees

- `0x180012fc8`
- `0x180014260`
- `0x1800207a0`
- `0x1800ba45d`
- `0x1801ac010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180014305`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800144b4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180014305`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800144b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800143e1`
- `OLEAUT32!__imp_SysFreeString` at `0x180014463`
- `OLEAUT32!__imp_SysFreeString` at `0x180014528`
- `OLEAUT32!__imp_SysFreeString` at `0x1800142b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800143e1`
- `OLEAUT32!__imp_SysFreeString` at `0x180014463`
- `OLEAUT32!__imp_SysFreeString` at `0x180014528`
- `OLEAUT32!__imp_VariantClear` at `0x180014539`
- `OLEAUT32!__imp_VariantClear` at `0x180014539`

## string_xrefs

- `0x180014584`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800145c6`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800145df`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800146dc`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800146f5`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18001470e`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180014731`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18001483d`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18001474a`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180014763`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800147a6`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800147f9`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180014812`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Common::Xml::GetAttributeValueStringFromQuery(
        OLECHAR *strIn,
        const unsigned __int16 *a2,
        const OLECHAR *a3,
        unsigned __int16 *a4,
        struct Common::StringBuffer *a5)
{
  OLECHAR *v9; // rdi
  struct Common::StringBuffer *v10; // r15
  __int64 v11; // rcx
  OLECHAR *v12; // rax
  int v13; // esi
  int v14; // eax
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v16)(_QWORD, GUID *, OLECHAR **); // rsi
  OLECHAR *v17; // rcx
  int v18; // eax
  OLECHAR *v19; // rax
  OLECHAR *v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rcx
  OLECHAR *v22; // rdi
  OLECHAR *v23; // rbx
  __int64 v24; // rcx
  const OLECHAR *v25; // rax
  int v26; // eax
  BSTR bstrVal; // r14
  __int64 v28; // rax
  bool v29; // zf
  __int64 v30; // rax
  _BYTE *v31; // rcx
  OLECHAR *v32; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  _BYTE *v36; // rcx
  __int64 v37; // rdx
  BSTR v38; // rax
  unsigned int v39; // edi
  int v40; // ecx
  unsigned int v41; // eax
  int v42; // ecx
  unsigned int v43; // edx
  unsigned int i; // edx
  int v45; // eax
  int v46; // eax
  __int64 (__fastcall ***v47)(_QWORD, GUID *, OLECHAR **); // [rsp+20h] [rbp-38h] BYREF
  OLECHAR *v48; // [rsp+28h] [rbp-30h]
  OLECHAR *v49; // [rsp+30h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  OLECHAR *v52; // [rsp+A8h] [rbp+50h] BYREF

  v9 = 0;
  v48 = 0;
  if ( a2 && strIn && a3 )
  {
    v10 = a5;
    if ( a5 )
      *(_DWORD *)a5 = 0;
    v47 = 0;
    v52 = 0;
    SysFreeString(0);
    v49 = 0;
    v11 = 0x7FFFFFFF;
    v12 = strIn;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    v13 = -2147024809;
    if ( v11 )
    {
      if ( (unsigned int)(0x7FFFFFFF - v11) > 0x3FFFFFFF )
      {
        v13 = -2147024809;
      }
      else
      {
        v9 = SysAllocStringLen(strIn, 0x7FFFFFFF - (int)v11);
        v49 = v9;
        v13 = 0;
        if ( !v9 )
          v13 = -2147024882;
      }
    }
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v13,
        (int)v47);
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(const unsigned __int16 *, OLECHAR *, _QWORD))(*(_QWORD *)a2 + 296LL))(
              a2,
              v9,
              &v47);
      v13 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v14,
          (int)v47);
      }
      else
      {
        v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
        if ( v47 )
        {
          v16 = **v47;
          v17 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v17 + 16LL))(v17);
          }
          v18 = v16(v15, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v52);
          v13 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x89,
              (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
              (const char *)(unsigned int)v18,
              (int)v47);
          }
          else
          {
            v19 = v52;
            v52 = 0;
            v48 = v19;
          }
        }
        else
        {
          v48 = 0;
        }
      }
    }
    SysFreeString(v9);
    v20 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
    if ( v47 )
    {
      v47 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[2])(v21);
    }
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2DA,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v13,
        (int)v47);
    }
    else
    {
      v22 = v48;
      if ( v48 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        pvarg.vt = 0;
        if ( v10 )
          *(_DWORD *)v10 = 0;
        SysFreeString(0);
        v23 = 0;
        v52 = 0;
        v24 = 0x7FFFFFFF;
        v25 = a3;
        do
        {
          if ( !*v25 )
            break;
          ++v25;
          --v24;
        }
        while ( v24 );
        v13 = -2147024809;
        if ( v24 )
        {
          if ( (unsigned int)(0x7FFFFFFF - v24) > 0x3FFFFFFF )
          {
            v13 = -2147024809;
          }
          else
          {
            v23 = SysAllocStringLen(a3, 0x7FFFFFFF - (int)v24);
            v52 = v23;
            v13 = 0;
            if ( !v23 )
              v13 = -2147024882;
          }
        }
        if ( v13 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x134,
            (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
            (const char *)(unsigned int)v13,
            (int)v47);
        }
        else
        {
          v26 = (*(__int64 (__fastcall **)(OLECHAR *, OLECHAR *, VARIANTARG *))(*(_QWORD *)v22 + 352LL))(
                  v22,
                  v23,
                  &pvarg);
          v13 = v26;
          if ( v26 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x135,
              (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
              (const char *)(unsigned int)v26,
              (int)v47);
          }
          else
          {
            bstrVal = pvarg.bstrVal;
            if ( pvarg.llVal )
            {
              v37 = 1073741822;
              v38 = pvarg.bstrVal;
              do
              {
                if ( !*v38 )
                  break;
                ++v38;
                --v37;
              }
              while ( v37 );
              v13 = -2147024809;
              if ( v37 )
              {
                v39 = 1073741822 - v37;
                v13 = 0;
                if ( (unsigned int)(1073741822 - v37) > 0x7FFFFFFF )
                  v13 = -2147024362;
                if ( v13 < 0 )
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x22F,
                    (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                    (const char *)(unsigned int)v13,
                    (int)v47);
                }
                else
                {
                  v40 = *((_DWORD *)a4 + 4);
                  v41 = 0;
                  if ( v40 )
                    v41 = v40 - 1;
                  if ( v39 <= v41 && (!v40 || (unsigned int)(v40 - 1) <= 0x20) )
                    goto LABEL_63;
                  if ( v39 > 0x20 )
                  {
                    i = 1073741822 - v37;
                  }
                  else
                  {
                    for ( i = 8; i < v39; i *= 2 )
                      ;
                  }
                  v45 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)a4, i);
                  v13 = v45;
                  if ( v45 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x232,
                      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                      (const char *)(unsigned int)v45,
                      (int)v47);
                  }
                  else
                  {
LABEL_63:
                    v42 = *((_DWORD *)a4 + 4);
                    v43 = 0;
                    if ( v42 )
                      v43 = v42 - 1;
                    if ( v39 <= v43
                      || (v46 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)a4, v39), v13 = v46, v46 >= 0) )
                    {
                      *(_DWORD *)a4 = v39;
                      if ( v39 )
                        *(_WORD *)(*((_QWORD *)a4 + 1) + 2LL * v39) = 0;
                      v13 = 0;
                    }
                    else
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x20C,
                        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                        (const char *)(unsigned int)v46,
                        (int)v47);
                    }
                    if ( v13 < 0 )
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x235,
                        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                        (const char *)(unsigned int)v13,
                        (int)v47);
                    }
                    else
                    {
                      memcpy_0(*((void **)a4 + 1), bstrVal, 2 * v39);
                      v13 = 0;
                    }
                  }
                }
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x249,
                  (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                  (const char *)0x80070057LL,
                  (int)v47);
              }
              if ( v13 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x13D,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
                  (const char *)(unsigned int)v13,
                  (int)v47);
              }
              else if ( v10 )
              {
                *(_DWORD *)v10 = 1;
              }
            }
            else
            {
              v28 = *(unsigned int *)a4;
              v29 = 2 * v28 == 0;
              v30 = 2 * v28;
              v31 = (_BYTE *)*((_QWORD *)a4 + 1);
              if ( !v29 )
              {
                do
                {
                  *v31++ = 0;
                  --v30;
                }
                while ( v30 );
              }
            }
          }
        }
        SysFreeString(v23);
        VariantClear(&pvarg);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2E3,
            (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
            (const char *)(unsigned int)v13,
            (int)v47);
      }
      else
      {
        v34 = *(unsigned int *)a4;
        v29 = 2 * v34 == 0;
        v35 = 2 * v34;
        v36 = (_BYTE *)*((_QWORD *)a4 + 1);
        if ( !v29 )
        {
          do
          {
            *v36++ = 0;
            --v35;
          }
          while ( v35 );
        }
      }
    }
  }
  else
  {
    v13 = -2147024809;
  }
  v32 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v32 + 16LL))(v32);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180014260  push    rbp
0x180014262  push    rbx
0x180014263  push    rsi
0x180014264  push    rdi
0x180014265  push    r12
0x180014267  push    r13
0x180014269  push    r14
0x18001426b  push    r15
0x18001426d  mov     rbp, rsp
0x180014270  sub     rsp, 58h
0x180014274  mov     r13, r9
0x180014277  mov     r12, r8
0x18001427a  mov     r14, rdx
0x18001427d  mov     rbx, rcx
0x180014280  xor     edi, edi
0x180014282  mov     [rbp+var_30], rdi
0x180014286  test    rdx, rdx
0x180014289  jz      loc_180014724
0x18001428f  test    rcx, rcx
0x180014292  jz      loc_180014724
0x180014298  test    r8, r8
0x18001429b  jz      loc_180014724
0x1800142a1  mov     r15, [rbp+arg_20]
0x1800142a5  test    r15, r15
0x1800142a8  jz      short loc_1800142AD
0x1800142aa  mov     [r15], edi
0x1800142ad  mov     [rbp+var_38], rdi
0x1800142b1  mov     [rbp+arg_8], rdi
0x1800142b5  xor     ecx, ecx; bstrString
0x1800142b7  call    cs:__imp_SysFreeString
0x1800142be  nop     dword ptr [rax+rax+00h]
0x1800142c3  mov     [rbp+var_28], rdi
0x1800142c7  mov     ecx, 7FFFFFFFh
0x1800142cc  mov     rax, rbx
0x1800142cf  nop
0x1800142d0  cmp     word ptr [rax], 0
0x1800142d4  jz      short loc_1800142E0
0x1800142d6  add     rax, 2
0x1800142da  sub     rcx, 1
0x1800142de  jnz     short loc_1800142D0
0x1800142e0  mov     esi, 80070057h
0x1800142e5  xor     eax, eax
0x1800142e7  test    rcx, rcx
0x1800142ea  cmovnz  esi, eax
0x1800142ed  jz      short loc_180014325
0x1800142ef  mov     edx, 7FFFFFFFh
0x1800142f4  sub     edx, ecx; ui
0x1800142f6  cmp     edx, 3FFFFFFFh
0x1800142fc  ja      loc_1800147C6
0x180014302  mov     rcx, rbx; strIn
0x180014305  call    cs:__imp_SysAllocStringLen
0x18001430c  nop     dword ptr [rax+rax+00h]
0x180014311  mov     rdi, rax
0x180014314  mov     [rbp+var_28], rax
0x180014318  xor     esi, esi
0x18001431a  test    rax, rax
0x18001431d  mov     eax, 8007000Eh
0x180014322  cmovz   esi, eax
0x180014325  mov     rcx, [rbp+40h]; this
0x180014329  test    esi, esi
0x18001432b  js      loc_180014581
0x180014331  mov     rax, [r14]
0x180014334  mov     rbx, [rax+128h]
0x18001433b  mov     rcx, [rbp+var_38]
0x18001433f  test    rcx, rcx
0x180014342  jz      short loc_180014359
0x180014344  mov     [rbp+var_38], 0
0x18001434c  mov     rax, [rcx]
0x18001434f  mov     rax, [rax+10h]
0x180014353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014358  nop
0x180014359  lea     r8, [rbp+var_38]
0x18001435d  mov     rdx, rdi
0x180014360  mov     rcx, r14
0x180014363  mov     rax, rbx
0x180014366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001436b  mov     esi, eax
0x18001436d  mov     rcx, [rbp+40h]; this
0x180014371  test    eax, eax
0x180014373  js      loc_1800145DC
0x180014379  mov     rbx, [rbp+var_38]
0x18001437d  test    rbx, rbx
0x180014380  jz      loc_18001459A
0x180014386  mov     rax, [rbx]
0x180014389  mov     rsi, [rax]
0x18001438c  mov     rcx, [rbp+arg_8]
0x180014390  test    rcx, rcx
0x180014393  jz      short loc_1800143AA
0x180014395  mov     [rbp+arg_8], 0
0x18001439d  mov     rdx, [rcx]
0x1800143a0  mov     rax, [rdx+10h]
0x1800143a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143a9  nop
0x1800143aa  lea     r8, [rbp+arg_8]
0x1800143ae  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800143b5  mov     rcx, rbx
0x1800143b8  mov     rax, rsi
0x1800143bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143c0  mov     esi, eax
0x1800143c2  mov     rcx, [rbp+40h]; this
0x1800143c6  test    eax, eax
0x1800143c8  js      loc_1800146F2
0x1800143ce  mov     rax, [rbp+arg_8]
0x1800143d2  mov     [rbp+arg_8], 0
0x1800143da  mov     [rbp+var_30], rax
0x1800143de  mov     rcx, rdi; bstrString
0x1800143e1  call    cs:__imp_SysFreeString
0x1800143e8  nop     dword ptr [rax+rax+00h]
0x1800143ed  nop
0x1800143ee  mov     rcx, [rbp+arg_8]
0x1800143f2  xor     edi, edi
0x1800143f4  test    rcx, rcx
0x1800143f7  jz      short loc_18001440A
0x1800143f9  mov     [rbp+arg_8], rdi
0x1800143fd  mov     rax, [rcx]
0x180014400  mov     rax, [rax+10h]
0x180014404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014409  nop
0x18001440a  mov     rcx, [rbp+var_38]
0x18001440e  test    rcx, rcx
0x180014411  jz      short loc_180014424
0x180014413  mov     [rbp+var_38], rdi
0x180014417  mov     rax, [rcx]
0x18001441a  mov     rax, [rax+10h]
0x18001441e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014423  nop
0x180014424  mov     rcx, [rbp+40h]; this
0x180014428  test    esi, esi
0x18001442a  js      loc_1800145C3
0x180014430  mov     rdi, [rbp+var_30]
0x180014434  test    rdi, rdi
0x180014437  jz      loc_1800145A7
0x18001443d  xorps   xmm0, xmm0
0x180014440  xor     eax, eax
0x180014442  movups  xmmword ptr [rbp+pvarg], xmm0
0x180014446  mov     qword ptr [rbp+pvarg+10h], rax
0x18001444a  mov     word ptr [rbp+pvarg], ax
0x18001444e  xor     ebx, ebx
0x180014450  test    rdi, rdi
0x180014453  jz      loc_1800147BC
0x180014459  test    r15, r15
0x18001445c  jz      short loc_180014461
0x18001445e  mov     [r15], ebx
0x180014461  xor     ecx, ecx; bstrString
0x180014463  call    cs:__imp_SysFreeString
0x18001446a  nop     dword ptr [rax+rax+00h]
0x18001446f  xor     ebx, ebx
0x180014471  mov     [rbp+arg_8], rbx
0x180014475  mov     ecx, 7FFFFFFFh
0x18001447a  mov     rax, r12
0x18001447d  nop     dword ptr [rax]
0x180014480  cmp     [rax], bx
0x180014483  jz      short loc_18001448F
0x180014485  add     rax, 2
0x180014489  sub     rcx, 1
0x18001448d  jnz     short loc_180014480
0x18001448f  mov     esi, 80070057h
0x180014494  xor     eax, eax
0x180014496  test    rcx, rcx
0x180014499  cmovnz  esi, eax
0x18001449c  jz      short loc_1800144D4
0x18001449e  mov     edx, 7FFFFFFFh
0x1800144a3  sub     edx, ecx; ui
0x1800144a5  cmp     edx, 3FFFFFFFh
0x1800144ab  ja      loc_1800147D4
0x1800144b1  mov     rcx, r12; strIn
0x1800144b4  call    cs:__imp_SysAllocStringLen
0x1800144bb  nop     dword ptr [rax+rax+00h]
0x1800144c0  mov     rbx, rax
0x1800144c3  mov     [rbp+arg_8], rax
0x1800144c7  xor     esi, esi
0x1800144c9  test    rax, rax
0x1800144cc  mov     eax, 8007000Eh
0x1800144d1  cmovz   esi, eax
0x1800144d4  mov     rcx, [rbp+40h]; this
0x1800144d8  test    esi, esi
0x1800144da  js      loc_1800146D9
0x1800144e0  mov     rax, [rdi]
0x1800144e3  lea     r8, [rbp+pvarg]
0x1800144e7  mov     rdx, rbx
0x1800144ea  mov     rcx, rdi
0x1800144ed  mov     rax, [rax+160h]
0x1800144f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144f9  mov     esi, eax
0x1800144fb  mov     rcx, [rbp+40h]; this
0x1800144ff  test    eax, eax
0x180014501  js      loc_18001470B
0x180014507  mov     r14, qword ptr [rbp+pvarg+8]
0x18001450b  test    r14, r14
0x18001450e  jnz     loc_1800145F5
0x180014514  mov     eax, [r13+0]
0x180014518  add     rax, rax
0x18001451b  mov     rcx, [r13+8]
0x18001451f  jnz     loc_180014828
0x180014525  mov     rcx, rbx; bstrString
0x180014528  call    cs:__imp_SysFreeString
0x18001452f  nop     dword ptr [rax+rax+00h]
0x180014534  nop
0x180014535  lea     rcx, [rbp+pvarg]; pvarg
0x180014539  call    cs:__imp_VariantClear
0x180014540  nop     dword ptr [rax+rax+00h]
0x180014545  mov     rcx, [rbp+40h]; this
0x180014549  test    esi, esi
0x18001454b  js      loc_18001483A
0x180014551  xor     edi, edi
0x180014553  mov     rcx, [rbp+var_30]
0x180014557  test    rcx, rcx
0x18001455a  jz      short loc_18001456D
0x18001455c  mov     [rbp+var_30], rdi
0x180014560  mov     rdx, [rcx]
0x180014563  mov     rax, [rdx+10h]
0x180014567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001456c  nop
0x18001456d  mov     eax, esi
0x18001456f  add     rsp, 58h
0x180014573  pop     r15
0x180014575  pop     r14
0x180014577  pop     r13
0x180014579  pop     r12
0x18001457b  pop     rdi
0x18001457c  pop     rsi
0x18001457d  pop     rbx
0x18001457e  pop     rbp
0x18001457f  retn
0x180014581  mov     r9d, esi; char *
0x180014584  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x18001458b  mov     edx, 7Fh; void *
0x180014590  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014595  jmp     loc_1800143DE
0x18001459a  mov     [rbp+var_30], 0
0x1800145a2  jmp     loc_1800143DE
0x1800145a7  mov     eax, [r13+0]
0x1800145ab  add     rax, rax
0x1800145ae  mov     rcx, [r13+8]
0x1800145b2  jz      short loc_180014551
0x1800145b4  mov     byte ptr [rcx], 0
0x1800145b7  lea     rcx, [rcx+1]
0x1800145bb  sub     rax, 1
0x1800145bf  jnz     short loc_1800145B4
0x1800145c1  jmp     short loc_180014551
0x1800145c3  mov     r9d, esi; char *
0x1800145c6  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x1800145cd  mov     edx, 2DAh; void *
0x1800145d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800145d7  jmp     loc_180014553
0x1800145dc  mov     r9d, eax; char *
0x1800145df  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x1800145e6  mov     edx, 83h; void *
0x1800145eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800145f0  jmp     loc_1800143DE
0x1800145f5  mov     ecx, 3FFFFFFEh
0x1800145fa  mov     edx, ecx
0x1800145fc  mov     rax, r14
0x1800145ff  nop
0x180014600  cmp     word ptr [rax], 0
0x180014604  jz      short loc_180014610
0x180014606  add     rax, 2
0x18001460a  sub     rdx, 1
0x18001460e  jnz     short loc_180014600
0x180014610  mov     esi, 80070057h
0x180014615  xor     eax, eax
0x180014617  test    rdx, rdx
0x18001461a  cmovnz  esi, eax
0x18001461d  sub     rcx, rdx
0x180014620  xor     edi, edi
0x180014622  test    rdx, rdx
0x180014625  cmovnz  rdi, rcx
0x180014629  mov     rcx, [rbp+40h]; this
0x18001462d  jz      loc_18001480F
0x180014633  mov     eax, 80070216h
0x180014638  xor     esi, esi
0x18001463a  cmp     edi, 7FFFFFFFh
0x180014640  cmova   esi, eax
0x180014643  mov     rcx, [rbp+40h]; this
0x180014647  test    esi, esi
0x180014649  js      loc_180014747
0x18001464f  mov     ecx, [r13+10h]
0x180014653  lea     edx, [rcx-1]
0x180014656  xor     eax, eax
0x180014658  test    ecx, ecx
0x18001465a  cmovnz  eax, edx
0x18001465d  cmp     edi, eax
0x18001465f  ja      loc_180014779
0x180014665  test    ecx, ecx
0x180014667  jz      short loc_180014672
0x180014669  cmp     edx, 20h ; ' '
0x18001466c  ja      loc_180014779
0x180014672  mov     ecx, [r13+10h]
0x180014676  lea     eax, [rcx-1]
0x180014679  xor     edx, edx
0x18001467b  test    ecx, ecx
0x18001467d  cmovnz  edx, eax
0x180014680  cmp     edi, edx
0x180014682  ja      loc_1800147DE
0x180014688  mov     [r13+0], edi
0x18001468c  test    edi, edi
0x18001468e  jz      short loc_18001469C
0x180014690  mov     edx, edi
0x180014692  mov     rcx, [r13+8]
0x180014696  xor     eax, eax
  ... truncated ...
```
