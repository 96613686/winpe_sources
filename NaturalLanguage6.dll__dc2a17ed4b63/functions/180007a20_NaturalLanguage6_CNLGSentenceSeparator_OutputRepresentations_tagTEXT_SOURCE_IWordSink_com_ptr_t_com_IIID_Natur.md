# NaturalLanguage6::CNLGSentenceSeparator::OutputRepresentations(tagTEXT_SOURCE *,IWordSink *,_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,int &,NaturalLanguage6::STextRange *,int)

- ea: `0x180007a20`
- end: `0x1800083d6`
- name: `?OutputRepresentations@CNLGSentenceSeparator@NaturalLanguage6@@AEAAJPEAUtagTEXT_SOURCE@@PEAUIWordSink@@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@AEAHPEAUSTextRange@2@H@Z`
- size: `2486`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005b50`

## callees

- `0x180005160`
- `0x180007a20`
- `0x1800083e0`
- `0x180008460`
- `0x18002b720`
- `0x18002bf50`
- `0x180036b04`
- `0x180036b9c`
- `0x18003ebf4`
- `0x18003ec74`
- `0x18005a3e0`
- `0x18005c720`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `msvcrt!wcschr` at `0x180007ff5`
- `msvcrt!wcschr` at `0x180007ff5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NaturalLanguage6::CNLGSentenceSeparator::OutputRepresentations(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct IUnknown **a4,
        _DWORD *a5,
        __int64 *a6,
        int a7)
{
  __int64 *v7; // rdi
  signed __int64 v9; // r15
  __int64 v10; // rbx
  int v11; // esi
  int v13; // r14d
  __int64 i; // r14
  int v15; // r14d
  unsigned int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // r15
  unsigned int v19; // edi
  int v20; // r14d
  __int64 v21; // rsi
  unsigned int v22; // ecx
  int v23; // ebx
  int v24; // r9d
  __int64 v25; // r14
  int v26; // ecx
  int v27; // ecx
  int v28; // eax
  int v29; // eax
  unsigned int v30; // ecx
  int v31; // ecx
  struct IUnknown *v32; // r12
  int v33; // eax
  const unsigned __int16 *v34; // r8
  __int64 v35; // rdx
  __int64 ***v36; // rcx
  __int64 **v37; // rcx
  float v38; // xmm0_4
  const wchar_t *v39; // rax
  wchar_t *v40; // rax
  struct IUnknown *v41; // r12
  int v42; // eax
  int v43; // r12d
  __int64 k; // r14
  int v45; // r9d
  __int64 j; // r12
  const unsigned __int16 *v47; // r8
  __int64 v48; // rdx
  __int64 ***v49; // rcx
  __int64 **v50; // rcx
  int v51; // edx
  const wchar_t *v52; // rcx
  int v53; // eax
  __int64 v54; // rax
  int v55; // [rsp+20h] [rbp-E0h]
  __int64 v56; // [rsp+30h] [rbp-D0h]
  int v57; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v58; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v59; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v60; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v61; // [rsp+68h] [rbp-98h] BYREF
  __int64 v62; // [rsp+70h] [rbp-90h]
  __int64 v63; // [rsp+78h] [rbp-88h]
  __int64 v64; // [rsp+80h] [rbp-80h]
  signed __int64 v65; // [rsp+88h] [rbp-78h]
  _DWORD *v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+A0h] [rbp-60h]
  __int64 *v68; // [rsp+A8h] [rbp-58h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  struct IUnknown **v70; // [rsp+B8h] [rbp-48h]
  _BYTE v71[16]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t v72[96]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Str[1024]; // [rsp+190h] [rbp+90h] BYREF

  v69 = -2;
  v7 = (__int64 *)a4;
  v68 = (__int64 *)a4;
  v63 = a3;
  v67 = a2;
  v70 = a4;
  v66 = a5;
  LODWORD(v9) = 0;
  if ( !*a4 )
    _com_raise_error(-2147467261, 0);
  NaturalLanguage6::ITextSegment::GetRepresentations(*a4);
  if ( a6 )
  {
    v10 = *a6;
  }
  else
  {
    v54 = _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(v7);
    v10 = *(_QWORD *)NaturalLanguage6::ITextSegment::GetRange(v54, v71);
  }
  v62 = v10;
  v64 = v10;
  v11 = 0;
  if ( !v59 )
  {
LABEL_5:
    if ( v59 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    if ( *v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*v7 + 16LL))(*v7);
    return (unsigned int)v11;
  }
  `eh vector constructor iterator'(
    v72,
    0x18u,
    8u,
    (void (*)(void *))_variant_t::_variant_t,
    (void (*)(void *))_variant_t::~_variant_t);
  v58 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t *, unsigned int *))(*(_QWORD *)v59 + 24LL))(
          v59,
          8,
          v72,
          &v58);
  if ( v13 < 0 )
  {
    `eh vector destructor iterator'(v72, 0x18u, 8u, (void (*)(void *))_variant_t::~_variant_t);
    _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v59);
    _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v7);
    return (unsigned int)v13;
  }
  v65 = 0;
LABEL_12:
  while ( 2 )
  {
    while ( 2 )
    {
      while ( 2 )
      {
        if ( v11 < 0 || !v58 )
        {
          `eh vector destructor iterator'(v72, 0x18u, 8u, (void (*)(void *))_variant_t::~_variant_t);
          goto LABEL_5;
        }
        for ( i = 0; (unsigned int)i < v58; i = (unsigned int)(i + 1) )
        {
          v60 = 0;
          v27 = v72[12 * i];
          if ( v27 == 16402 )
          {
            v28 = StringCchPrintfExW(Str, 0x400u, &v60, &v61, 0x800u, L"%s", *(_QWORD *)&v72[12 * i + 4]);
LABEL_36:
            v11 = v28;
            goto LABEL_37;
          }
          v31 = v27 - 3;
          if ( v31 )
          {
            if ( v31 != 1 )
            {
              `eh vector destructor iterator'(v72, 0x18u, 8u, (void (*)(void *))_variant_t::~_variant_t);
              _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v59);
              _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v7);
              return 2147549183LL;
            }
            v32 = (struct IUnknown *)*v7;
            if ( !*v7 )
              goto LABEL_114;
            v57 = 0;
            v33 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v32->lpVtbl[5].Release)(v32, &v57);
            if ( v33 < 0 )
              _com_issue_errorex(v33, v32, &GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56);
            if ( v57 == 1 )
            {
              v34 = &byte_1800BCA00;
              v35 = *(_QWORD *)(*v7 + 40);
              if ( v35 )
              {
                v36 = *(__int64 ****)(*(int *)(*(_QWORD *)(v35 + 8) + 4LL) + v35 + 88);
                if ( v36 )
                {
                  v37 = *v36;
                  if ( v37 )
                  {
                    while ( v37 )
                    {
                      if ( ((_DWORD)v37[1] & 0xFFFFFF) == 0x111F )
                      {
                        v34 = (const unsigned __int16 *)v37[2];
                        break;
                      }
                      v37 = (__int64 **)*v37;
                    }
                  }
                }
              }
              v38 = *(float *)&v72[12 * i + 4];
              v39 = L"-";
              if ( v38 >= 0.0 )
                v39 = &byte_1800BCA00;
              v11 = StringCchPrintfExW(
                      Str,
                      0x400u,
                      &v60,
                      &v61,
                      0x800u,
                      L"NN%g%s%s",
                      COERCE_FLOAT(LODWORD(v38) & _xmm),
                      v39,
                      v34);
              v40 = wcschr(Str, 0x2Eu);
              if ( v40 )
                *v40 = 68;
            }
          }
          else
          {
            v41 = (struct IUnknown *)*v7;
            if ( !*v7 )
              goto LABEL_114;
            v57 = 0;
            v42 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v41->lpVtbl[5].Release)(v41, &v57);
            if ( v42 < 0 )
              _com_issue_errorex(v42, v41, &GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56);
            switch ( v57 )
            {
              case 5:
                LODWORD(v56) = *(_DWORD *)&v72[12 * i + 4];
                v28 = StringCchPrintfExW(Str, 0x400u, &v60, &v61, 0x800u, L"TT%.08d", v56);
                goto LABEL_36;
              case 1:
                v47 = &byte_1800BCA00;
                v48 = *(_QWORD *)(*v7 + 40);
                if ( v48 )
                {
                  v49 = *(__int64 ****)(*(int *)(*(_QWORD *)(v48 + 8) + 4LL) + v48 + 88);
                  if ( v49 )
                  {
                    v50 = *v49;
                    if ( v50 )
                    {
                      while ( v50 )
                      {
                        if ( ((_DWORD)v50[1] & 0xFFFFFF) == 0x111F )
                        {
                          v47 = (const unsigned __int16 *)v50[2];
                          break;
                        }
                        v50 = (__int64 **)*v50;
                      }
                    }
                  }
                }
                v51 = *(_DWORD *)&v72[12 * i + 4];
                v52 = L"-";
                if ( v51 >= 0 )
                  v52 = &byte_1800BCA00;
                v53 = -v51;
                if ( v51 > 0 )
                  v53 = *(_DWORD *)&v72[12 * i + 4];
                LODWORD(v56) = v53;
                v28 = StringCchPrintfExW(Str, 0x400u, &v60, &v61, 0x800u, L"NN%d%s%s", v56, v52, v47);
                goto LABEL_36;
              case 6:
                LODWORD(v56) = *(_DWORD *)&v72[12 * i + 4];
                v28 = StringCchPrintfExW(Str, 0x400u, &v60, &v61, 0x800u, L"DD%.08d", v56);
                goto LABEL_36;
            }
          }
LABEL_37:
          v29 = 0;
          if ( v11 != -2147024774 )
            v29 = v11;
          v11 = v29;
          if ( v29 < 0 )
          {
LABEL_92:
            `eh vector destructor iterator'(v72, 0x18u, 8u, (void (*)(void *))_variant_t::~_variant_t);
            _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v59);
            _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v7);
            return (unsigned int)v11;
          }
          v9 = v60 - Str;
          v65 = v9;
          if ( (int)v9 > 0 )
          {
            v30 = *(_DWORD *)(a1 + 44);
            if ( (unsigned int)v9 < v30 && (unsigned int)i < v58 - 1 )
            {
              v45 = v10 + *(_DWORD *)(a1 + 72);
              v57 = v45;
              v11 = 0;
              for ( j = 0; (unsigned int)j < (unsigned int)v9; j = v30 + (unsigned int)j )
              {
                if ( v30 != 1 || (unsigned __int16)(Str[j] + 10240) > 0x7FFu )
                {
                  v55 = j + v45;
                  v11 =  IWordFormSink::`vcall'{32,{flat}}(v63);
                  if ( v11 < 0 )
                    goto LABEL_92;
                  v45 = v57;
                }
                v30 = *(_DWORD *)(a1 + 44);
              }
            }
          }
        }
        if ( !v59 )
LABEL_114:
          _com_raise_error(-2147467261, 0);
        v15 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t *, unsigned int *, int))(*(_QWORD *)v59 + 24LL))(
                v59,
                8,
                v72,
                &v58,
                v55);
        if ( v15 < 0 )
        {
          `eh vector destructor iterator'(v72, 0x18u, 8u, (void (*)(void *))_variant_t::~_variant_t);
          _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v59);
          _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v7);
          return (unsigned int)v15;
        }
        if ( (int)v9 <= 0 )
          continue;
        break;
      }
      v16 = *(_DWORD *)(a1 + 44);
      LODWORD(v61) = v16;
      if ( (unsigned int)v9 >= v16 )
        continue;
      break;
    }
    if ( v58 || a7 )
    {
      v43 = v10 + *(_DWORD *)(a1 + 72);
      v11 = 0;
      for ( k = 0; ; k = v16 + (unsigned int)k )
      {
        if ( (unsigned int)k >= (unsigned int)v9 )
          goto LABEL_12;
        if ( v16 != 1 || (unsigned __int16)(Str[k] + 10240) > 0x7FFu )
        {
          v55 = k + v43;
          v11 =  IWordFormSink::`vcall'{32,{flat}}(v63);
          if ( v11 < 0 )
            break;
        }
        v16 = *(_DWORD *)(a1 + 44);
      }
      `eh vector destructor iterator'(v72, 0x18u, 8u, (void (*)(void *))_variant_t::~_variant_t);
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
LABEL_33:
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v7);
      return (unsigned int)v11;
    }
    v17 = *(unsigned int *)(a1 + 72);
    v57 = v17 + v10;
    v18 = *(_QWORD *)(v67 + 8) + 2 * ((int)v10 + v17);
    v19 = HIDWORD(v62);
    v20 = 0;
    v21 = 0;
    v22 = v16;
    v23 = v57;
    while ( (unsigned int)v21 < v19 )
    {
      if ( v22 != 1 || (unsigned __int16)(*(_WORD *)(v18 + 2 * v21) + 10240) > 0x7FFu )
      {
        v55 = v21 + v23;
        v20 =  IWordFormSink::`vcall'{32,{flat}}(v63);
        if ( v20 < 0 )
          break;
      }
      v22 = *(_DWORD *)(a1 + 44);
      v21 = v22 + (unsigned int)v21;
    }
    LODWORD(v10) = v64;
    v7 = v68;
    LODWORD(v9) = v65;
    if ( v20 >= 0 )
    {
      v24 = v64 + *(_DWORD *)(a1 + 72);
      LODWORD(v61) = v24;
      v11 = 0;
      LODWORD(v60) = *(_DWORD *)(a1 + 44);
      v25 = 0;
      v26 = (int)v60;
      while ( (unsigned int)v25 < (unsigned int)v9 )
      {
        if ( v26 != 1 || (unsigned __int16)(Str[v25] + 10240) > 0x7FFu )
        {
          v55 = v25 + v24;
          v11 =  IWordFormSink::`vcall'{24,{flat}}(v63);
          if ( v11 < 0 )
          {
            *v66 = 1;
            `eh vector destructor iterator'(v72, 0x18u, 8u, (void (*)(void *))_variant_t::~_variant_t);
            if ( v59 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
            goto LABEL_33;
          }
          v24 = v61;
        }
        v26 = *(_DWORD *)(a1 + 44);
        v25 = (unsigned int)(v26 + v25);
      }
      *v66 = 1;
      continue;
    }
    break;
  }
  `eh vector destructor iterator'(v72, 0x18u, 8u, (void (*)(void *))_variant_t::~_variant_t);
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  if ( *v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)*v7 + 16LL))(*v7);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180007a20  push    rbp
0x180007a22  push    rbx
0x180007a23  push    rsi
0x180007a24  push    rdi
0x180007a25  push    r12
0x180007a27  push    r13
0x180007a29  push    r14
0x180007a2b  push    r15
0x180007a2d  lea     rbp, [rsp-8B8h]
0x180007a35  sub     rsp, 9B8h
0x180007a3c  mov     [rbp+8F0h+var_940], 0FFFFFFFFFFFFFFFEh
0x180007a44  movaps  [rsp+9F0h+var_50], xmm6
0x180007a4c  mov     rax, cs:__security_cookie
0x180007a53  xor     rax, rsp
0x180007a56  mov     [rbp+8F0h+var_60], rax
0x180007a5d  mov     rdi, r9
0x180007a60  mov     [rbp+8F0h+var_948], r9
0x180007a64  mov     [rsp+9F0h+var_978], r8
0x180007a69  mov     [rbp+8F0h+var_950], rdx
0x180007a6d  mov     r13, rcx
0x180007a70  mov     [rbp+8F0h+var_938], r9
0x180007a74  mov     rax, [rbp+8F0h+arg_20]
0x180007a7b  mov     [rbp+8F0h+var_960], rax
0x180007a7f  mov     rbx, [rbp+8F0h+arg_28]
0x180007a86  xor     r15d, r15d
0x180007a89  mov     rcx, [r9]; struct IUnknown *
0x180007a8c  test    rcx, rcx
0x180007a8f  jz      loc_1800082D9
0x180007a95  lea     rdx, [rsp+9F0h+var_998]
0x180007a9a  call    ?GetRepresentations@ITextSegment@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIEnumVARIANT@@$1?_GUID_00020404_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@XZ; NaturalLanguage6::ITextSegment::GetRepresentations(void)
0x180007a9f  nop
0x180007aa0  test    rbx, rbx
0x180007aa3  jz      loc_1800082F3
0x180007aa9  mov     rbx, [rbx]
0x180007aac  mov     [rsp+9F0h+var_980], rbx
0x180007ab1  mov     [rbp+8F0h+var_970], rbx
0x180007ab5  mov     esi, r15d
0x180007ab8  cmp     [rsp+9F0h+var_998], rsi
0x180007abd  jnz     short loc_180007B17
0x180007abf  mov     rcx, [rsp+9F0h+var_998]
0x180007ac4  test    rcx, rcx
0x180007ac7  jz      short loc_180007AD6
0x180007ac9  mov     rax, [rcx]
0x180007acc  mov     rax, [rax+10h]
0x180007ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad5  nop
0x180007ad6  mov     rcx, [rdi]
0x180007ad9  test    rcx, rcx
0x180007adc  jz      short loc_180007AEA
0x180007ade  mov     rax, [rcx]
0x180007ae1  mov     rax, [rax+10h]
0x180007ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aea  mov     eax, esi
0x180007aec  mov     rcx, [rbp+8F0h+var_60]
0x180007af3  xor     rcx, rsp; StackCookie
0x180007af6  call    __security_check_cookie
0x180007afb  movaps  xmm6, [rsp+9F0h+var_50]
0x180007b03  add     rsp, 9B8h
0x180007b0a  pop     r15
0x180007b0c  pop     r14
0x180007b0e  pop     r13
0x180007b10  pop     r12
0x180007b12  pop     rdi
0x180007b13  pop     rsi
0x180007b14  pop     rbx
0x180007b15  pop     rbp
0x180007b16  retn
0x180007b17  lea     r12, ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180007b1e  mov     [rsp+9F0h+var_9D0], r12; void (*)(void *)
0x180007b23  lea     r9, ??0_variant_t@@QEAA@XZ; void (*)(void *)
0x180007b2a  mov     edx, 18h; unsigned __int64
0x180007b2f  mov     r8d, 8; unsigned __int64
0x180007b35  lea     rcx, [rbp+8F0h+var_920]; void *
0x180007b39  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180007b3e  nop
0x180007b3f  mov     [rsp+9F0h+var_99C], r15d
0x180007b44  mov     rcx, [rsp+9F0h+var_998]
0x180007b49  test    rcx, rcx
0x180007b4c  jz      loc_1800082E6
0x180007b52  mov     rax, [rcx]
0x180007b55  lea     r9, [rsp+9F0h+var_99C]
0x180007b5a  lea     r8, [rbp+8F0h+var_920]
0x180007b5e  mov     edx, 8
0x180007b63  mov     rax, [rax+18h]
0x180007b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b6c  mov     r14d, eax
0x180007b6f  test    eax, eax
0x180007b71  js      loc_18000830F
0x180007b77  mov     [rbp+8F0h+var_968], r15
0x180007b7b  xorps   xmm6, xmm6
0x180007b7e  lea     rdx, aS_0; "%s"
0x180007b85  test    esi, esi
0x180007b87  js      loc_180007E3E
0x180007b8d  cmp     [rsp+9F0h+var_99C], 0
0x180007b92  jz      loc_180007E3E
0x180007b98  xor     r14d, r14d
0x180007b9b  cmp     r14d, [rsp+9F0h+var_99C]
0x180007ba0  jb      loc_180007D55
0x180007ba6  mov     rcx, [rsp+9F0h+var_998]
0x180007bab  test    rcx, rcx
0x180007bae  jz      loc_1800082E6
0x180007bb4  mov     rax, [rcx]
0x180007bb7  lea     r9, [rsp+9F0h+var_99C]
0x180007bbc  lea     r8, [rbp+8F0h+var_920]
0x180007bc0  mov     edx, 8
0x180007bc5  mov     rax, [rax+18h]
0x180007bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bce  mov     r14d, eax
0x180007bd1  test    eax, eax
0x180007bd3  js      loc_18000839F
0x180007bd9  test    r15d, r15d
0x180007bdc  lea     rdx, aS_0; "%s"
0x180007be3  jle     short loc_180007B85
0x180007be5  mov     edx, [r13+2Ch]
0x180007be9  mov     dword ptr [rsp+9F0h+var_988], edx
0x180007bed  cmp     r15d, edx
0x180007bf0  jnb     short loc_180007B7E
0x180007bf2  cmp     [rsp+9F0h+var_99C], 0
0x180007bf7  ja      loc_18000806C
0x180007bfd  cmp     [rbp+8F0h+arg_30], 0
0x180007c04  jnz     loc_18000806C
0x180007c0a  mov     ecx, [r13+48h]
0x180007c0e  lea     eax, [rcx+rbx]
0x180007c11  mov     [rsp+9F0h+var_9A0], eax
0x180007c15  mov     r12d, dword ptr [rsp+9F0h+var_980+4]
0x180007c1a  mov     r8d, r12d
0x180007c1d  movsxd  rax, ebx
0x180007c20  add     rcx, rax
0x180007c23  mov     rax, [rbp+8F0h+var_950]
0x180007c27  mov     rax, [rax+8]
0x180007c2b  lea     r15, [rax+rcx*2]
0x180007c2f  mov     edi, r12d
0x180007c32  xor     r14d, r14d
0x180007c35  xor     esi, esi
0x180007c37  mov     ecx, edx
0x180007c39  mov     ebx, [rsp+9F0h+var_9A0]
0x180007c3d  cmp     esi, edi
0x180007c3f  jnb     short loc_180007C84
0x180007c41  mov     eax, edi
0x180007c43  sub     eax, esi
0x180007c45  mov     r10d, ecx
0x180007c48  cmp     eax, ecx
0x180007c4a  cmovbe  r10d, eax
0x180007c4e  cmp     r8d, edx
0x180007c51  cmova   r12d, r10d
0x180007c55  cmp     ecx, 1
0x180007c58  jz      loc_180007F47
0x180007c5e  lea     ecx, [rsi+rbx]
0x180007c61  lea     r8, [r15+rsi*2]
0x180007c65  mov     dword ptr [rsp+9F0h+var_9D0], ecx
0x180007c69  mov     r9d, r12d
0x180007c6c  mov     edx, r10d
0x180007c6f  mov     rcx, [rsp+9F0h+var_978]
0x180007c74  call    ??_9IWordFormSink@@$BCA@AA; [thunk]: IWordFormSink::`vcall'{32,{flat}}
0x180007c79  mov     r14d, eax
0x180007c7c  test    eax, eax
0x180007c7e  jns     loc_180007DFF
0x180007c84  test    r14d, r14d
0x180007c87  mov     rbx, [rbp+8F0h+var_970]
0x180007c8b  mov     rdi, [rbp+8F0h+var_948]
0x180007c8f  mov     r15, [rbp+8F0h+var_968]
0x180007c93  js      loc_180007E5E
0x180007c99  mov     r9d, [r13+48h]
0x180007c9d  add     r9d, ebx
0x180007ca0  mov     dword ptr [rsp+9F0h+var_988], r9d
0x180007ca5  mov     r12d, dword ptr [rsp+9F0h+var_980+4]
0x180007caa  xor     esi, esi
0x180007cac  mov     r8d, [r13+2Ch]
0x180007cb0  mov     dword ptr [rsp+9F0h+var_990], r8d
0x180007cb5  xor     r14d, r14d
0x180007cb8  mov     ecx, r8d
0x180007cbb  cmp     r14d, r15d
0x180007cbe  jnb     loc_180007E11
0x180007cc4  mov     eax, r15d
0x180007cc7  sub     eax, r14d
0x180007cca  mov     edx, ecx
0x180007ccc  cmp     eax, ecx
0x180007cce  cmovbe  edx, eax
0x180007cd1  cmp     r15d, r8d
0x180007cd4  cmova   r12d, edx
0x180007cd8  cmp     ecx, 1
0x180007cdb  jz      loc_180007F64
0x180007ce1  lea     r8, [rbp+8F0h+Str]
0x180007ce8  lea     r8, [r8+r14*2]
0x180007cec  lea     eax, [r14+r9]
0x180007cf0  mov     dword ptr [rsp+9F0h+var_9D0], eax
0x180007cf4  mov     r9d, r12d
0x180007cf7  mov     rcx, [rsp+9F0h+var_978]
0x180007cfc  call    ??_9IWordFormSink@@$BBI@AA; [thunk]: IWordFormSink::`vcall'{24,{flat}}
0x180007d01  mov     esi, eax
0x180007d03  test    eax, eax
0x180007d05  jns     loc_180007E28
0x180007d0b  mov     rax, [rbp+8F0h+var_960]
0x180007d0f  mov     dword ptr [rax], 1
0x180007d15  lea     r9, ??1_variant_t@@QEAA@XZ; void (*)(void *)
0x180007d1c  mov     edx, 18h; unsigned __int64
0x180007d21  mov     r8d, 8; unsigned __int64
0x180007d27  lea     rcx, [rbp+8F0h+var_920]; void *
0x180007d2b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007d30  nop
0x180007d31  mov     rcx, [rsp+9F0h+var_998]
0x180007d36  test    rcx, rcx
0x180007d39  jz      short loc_180007D48
0x180007d3b  mov     rax, [rcx]
0x180007d3e  mov     rax, [rax+10h]
0x180007d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d47  nop
0x180007d48  mov     rcx, rdi
0x180007d4b  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x180007d50  jmp     loc_180007AEA
0x180007d55  mov     [rsp+9F0h+var_990], 0
0x180007d5e  lea     r15, [r14+r14*2]
0x180007d62  movzx   ecx, [rbp+r15*8+8F0h+var_920]
0x180007d68  cmp     ecx, 4012h
0x180007d6e  jnz     loc_180007EAD
0x180007d74  mov     rax, [rbp+r15*8+8F0h+var_918]
0x180007d79  mov     [rsp+9F0h+var_9C0], rax
0x180007d7e  mov     [rsp+9F0h+var_9C8], rdx; unsigned __int16 *
0x180007d83  mov     dword ptr [rsp+9F0h+var_9D0], 800h; unsigned int
0x180007d8b  lea     r9, [rsp+9F0h+var_988]; unsigned __int64 *
0x180007d90  lea     r8, [rsp+9F0h+var_990]; unsigned __int16 **
0x180007d95  mov     edx, 400h; unsigned __int64
0x180007d9a  lea     rcx, [rbp+8F0h+Str]; pszDest
0x180007da1  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180007da6  mov     esi, eax
0x180007da8  xor     eax, eax
0x180007daa  cmp     esi, 8007007Ah
0x180007db0  cmovnz  eax, esi
0x180007db3  mov     esi, eax
0x180007db5  test    eax, eax
0x180007db7  js      loc_18000818C
0x180007dbd  lea     rax, [rbp+8F0h+Str]
0x180007dc4  mov     r15, [rsp+9F0h+var_990]
0x180007dc9  sub     r15, rax
0x180007dcc  sar     r15, 1
0x180007dcf  mov     [rbp+8F0h+var_968], r15
0x180007dd3  test    r15d, r15d
0x180007dd6  jle     short loc_180007DF0
0x180007dd8  mov     ecx, [r13+2Ch]
0x180007ddc  cmp     r15d, ecx
0x180007ddf  jnb     short loc_180007DF0
0x180007de1  mov     eax, [rsp+9F0h+var_99C]
0x180007de5  dec     eax
0x180007de7  cmp     r14d, eax
0x180007dea  jb      loc_180008134
0x180007df0  inc     r14d
0x180007df3  lea     rdx, aS_0; "%s"
0x180007dfa  jmp     loc_180007B9B
0x180007dff  mov     edx, dword ptr [rsp+9F0h+var_988]
0x180007e03  mov     r8d, edi
0x180007e06  mov     ecx, [r13+2Ch]
0x180007e0a  add     esi, ecx
0x180007e0c  jmp     loc_180007C3D
0x180007e11  mov     rax, [rbp+8F0h+var_960]
0x180007e15  mov     dword ptr [rax], 1
0x180007e1b  test    esi, esi
0x180007e1d  jns     loc_180007B7E
0x180007e23  jmp     loc_180007D15
0x180007e28  mov     r8d, dword ptr [rsp+9F0h+var_990]
0x180007e2d  mov     r9d, dword ptr [rsp+9F0h+var_988]
0x180007e32  mov     ecx, [r13+2Ch]
0x180007e36  add     r14d, ecx
0x180007e39  jmp     loc_180007CBB
0x180007e3e  lea     r9, ??1_variant_t@@QEAA@XZ; void (*)(void *)
0x180007e45  mov     edx, 18h; unsigned __int64
0x180007e4a  mov     r8d, 8; unsigned __int64
0x180007e50  lea     rcx, [rbp+8F0h+var_920]; void *
0x180007e54  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007e59  jmp     loc_180007ABF
0x180007e5e  lea     r9, ??1_variant_t@@QEAA@XZ; void (*)(void *)
0x180007e65  mov     edx, 18h; unsigned __int64
0x180007e6a  mov     r8d, 8; unsigned __int64
0x180007e70  lea     rcx, [rbp+8F0h+var_920]; void *
0x180007e74  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007e79  nop
0x180007e7a  mov     rcx, [rsp+9F0h+var_998]
0x180007e7f  test    rcx, rcx
0x180007e82  jz      short loc_180007E91
0x180007e84  mov     rax, [rcx]
0x180007e87  mov     rax, [rax+10h]
0x180007e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e90  nop
0x180007e91  mov     rcx, [rdi]
0x180007e94  test    rcx, rcx
0x180007e97  jz      short loc_180007EA5
0x180007e99  mov     rax, [rcx]
0x180007e9c  mov     rax, [rax+10h]
0x180007ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea5  mov     eax, r14d
0x180007ea8  jmp     loc_180007AEC
0x180007ead  sub     ecx, 3
0x180007eb0  jz      loc_180008011
0x180007eb6  cmp     ecx, 1
0x180007eb9  jnz     loc_180008354
0x180007ebf  mov     r12, [rdi]
0x180007ec2  test    r12, r12
0x180007ec5  jz      loc_1800082E6
0x180007ecb  mov     [rsp+9F0h+var_9A0], 0
0x180007ed3  mov     rax, [r12]
0x180007ed7  lea     rdx, [rsp+9F0h+var_9A0]
  ... truncated ...
```
