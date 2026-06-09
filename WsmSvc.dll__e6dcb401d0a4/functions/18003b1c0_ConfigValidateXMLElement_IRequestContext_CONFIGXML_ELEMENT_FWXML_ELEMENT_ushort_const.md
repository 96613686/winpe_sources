# ConfigValidateXMLElement(IRequestContext *,_CONFIGXML_ELEMENT *,_FWXML_ELEMENT *,ushort const *)

- ea: `0x18003b1c0`
- end: `0x18003ba9d`
- name: `?ConfigValidateXMLElement@@YAHPEAVIRequestContext@@PEAU_CONFIGXML_ELEMENT@@PEAU_FWXML_ELEMENT@@PEBG@Z`
- size: `2269`
- prototype: `__int64 __fastcall(struct IRequestContext *, struct _CONFIGXML_ELEMENT *, struct _FWXML_ELEMENT *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b1c0`
- `0x180048db0`
- `0x1800cc11c`
- `0x180199c88`

## callees

- `0x180005d10`
- `0x180007fb0`
- `0x1800089e0`
- `0x18000d780`
- `0x180035fe0`
- `0x18003b1c0`
- `0x18003c640`
- `0x180084a20`
- `0x180112380`
- `0x1801133b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18003b2bd`
- `msvcrt!_wcsnicmp` at `0x18003b31a`
- `msvcrt!_wcsnicmp` at `0x18003b46b`
- `msvcrt!_wcsnicmp` at `0x18003b2bd`
- `msvcrt!_wcsnicmp` at `0x18003b31a`
- `msvcrt!_wcsnicmp` at `0x18003b46b`
- `msvcrt!iswspace` at `0x18003b81e`
- `msvcrt!iswspace` at `0x18003b81e`

## string_xrefs

- `0x18003b4af`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x18003b6c5`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x18003b703`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x18003b72d`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x18003b757`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x18003b980`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x18003b699`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003b7ef`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`

## pseudocode

```c
__int64 __fastcall ConfigValidateXMLElement(
        struct IRequestContext *a1,
        struct _CONFIGXML_ELEMENT *a2,
        struct _FWXML_ELEMENT *a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rax
  __int64 v9; // rbx
  void (__fastcall *v10)(struct IRequestContext *, __int64, __int64, __int64, __int64); // rdi
  __int64 ElementName; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  const wchar_t *v14; // rax
  size_t v15; // r8
  const wchar_t *v16; // r9
  const wchar_t *v17; // rbx
  __int64 v18; // rax
  const wchar_t *v19; // rax
  size_t v20; // r8
  unsigned int v22; // edi
  _QWORD *v23; // r15
  unsigned int v24; // ecx
  struct _CONFIGXML_ELEMENT *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // r13
  const wchar_t *v28; // rax
  size_t v29; // r8
  const wchar_t *v30; // r9
  _QWORD *v31; // rcx
  unsigned int v32; // ecx
  __int64 v33; // rdx
  _QWORD *v34; // rcx
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 ElementNamespaceUrl; // rax
  __int64 v38; // rcx
  __int64 v39; // r15
  __int64 i; // rdi
  int v41; // eax
  __int64 v42; // rax
  struct IRequestContext *v43; // rax
  void (__fastcall *v44)(struct IRequestContext *, __int64, __int64, __int64); // rbx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rbx
  void (__fastcall *v48)(struct IRequestContext *, __int64, __int64, __int64, __int64); // rdi
  __int64 v49; // rax
  struct IRequestContext *Child; // rdi
  void (__fastcall *v51)(struct IRequestContext *, __int64, __int64, __int64); // rbx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 *v54; // rbx
  unsigned int v55; // [rsp+30h] [rbp-38h]
  struct _CONFIGXML_ELEMENT *v56; // [rsp+38h] [rbp-30h]
  int v57; // [rsp+70h] [rbp+8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 406, L"406", 0x54Fu, 0);
    return 0;
  }
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 407, L"407", 0x54Fu, a1);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 408, L"408", 0x54Fu, a1);
    return 0;
  }
  if ( !*(_QWORD *)a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 411, L"411", 0x54Fu, a1);
    return 0;
  }
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v8) );
  if ( *((_DWORD *)a3 + 4) != (_DWORD)v8
    || (v14 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3),
        _wcsnicmp(v14, v16, v15)) )
  {
    v9 = *(_QWORD *)a2;
    v10 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL);
    ElementName = FwXmlGetElementNameEx(a3);
    v10(a1, 2150858819LL, 1077134516, ElementName, v9);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      return 0;
    v13 = 14;
    goto LABEL_12;
  }
  v17 = (const wchar_t *)*((_QWORD *)a2 + 1);
  if ( v17 )
    goto LABEL_17;
  if ( a4 )
  {
    v17 = a4;
LABEL_17:
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    if ( a3 == (struct _FWXML_ELEMENT *)-48LL )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
LABEL_22:
      (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)a1 + 64LL))(
        a1,
        2150858819LL,
        1077134518,
        *(_QWORD *)a2);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
        return 0;
      v13 = 16;
      goto LABEL_12;
    }
    if ( *((_DWORD *)a3 + 16) != (_DWORD)v18 )
      goto LABEL_22;
    v19 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *((char *)a3 + 48);
    if ( _wcsnicmp(v19, v17, v20) )
      goto LABEL_22;
    goto LABEL_24;
  }
  ElementNamespaceUrl = FwXmlGetElementNamespaceUrl(a3);
  v38 = -1;
  do
    ++v38;
  while ( *(_WORD *)(ElementNamespaceUrl + 2 * v38) );
  if ( v38 )
  {
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)a1 + 64LL))(
      a1,
      2150858819LL,
      1077134518,
      *(_QWORD *)a2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      return 0;
    v13 = 15;
LABEL_12:
    WPP_SF_(v12[2], v13, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
    return 0;
  }
  v17 = 0;
LABEL_24:
  if ( *((_DWORD *)a2 + 11) )
  {
LABEL_46:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 448, L"448", 0x54Fu, a1);
    return 0;
  }
  if ( !(unsigned int)FwXmlIsSimpleContent(a3) )
  {
    if ( !*((_DWORD *)a3 + 18) )
      goto LABEL_27;
    goto LABEL_68;
  }
  v39 = *((_QWORD *)a3 + 10);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v41 = 0;
    if ( (unsigned int)i >= *(_DWORD *)(v39 + 16) )
      break;
    v42 = OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v39);
    if ( !iswspace(*(_WORD *)(v42 + 2 * i)) )
    {
      v41 = 1;
      break;
    }
  }
  if ( v41 )
  {
LABEL_68:
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)a1 + 64LL))(
      a1,
      2150858819LL,
      1077134521,
      *(_QWORD *)a2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      return 0;
    v13 = 17;
    goto LABEL_12;
  }
LABEL_27:
  if ( *((_DWORD *)a2 + 11) )
    goto LABEL_46;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids, *(_QWORD *)a2);
  if ( !(unsigned int)ConfigValidateXMLElementAttributes(a1, a2, a3, v17) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      return 0;
    v13 = 19;
    goto LABEL_12;
  }
  if ( *((_DWORD *)a2 + 10) )
  {
    v22 = 0;
    v23 = (_QWORD *)((char *)a2 + 32);
    v24 = 0;
    v57 = 0;
LABEL_34:
    v55 = v24;
    while ( 1 )
    {
      if ( v24 >= *((_DWORD *)a3 + 32) )
      {
        if ( v57 )
          v23 = (_QWORD *)((char *)a2 + 32);
        v32 = v22 + 1;
        if ( !v57 )
          v32 = v22;
        while ( 1 )
        {
          if ( v32 >= *((_DWORD *)a2 + 10) )
          {
            v31 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              v33 = 27;
              goto LABEL_65;
            }
            return 1;
          }
          if ( *(_DWORD *)(*v23 + 16LL * v32 + 8) )
            break;
          ++v32;
        }
        _mm_lfence();
        v54 = *(__int64 **)(*v23 + 16LL * v32);
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL))(
          a1,
          2150858819LL,
          1077134520,
          *v54);
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        {
          v35 = *v54;
          v36 = 26;
          goto LABEL_103;
        }
        return 0;
      }
      if ( v22 >= *((_DWORD *)a2 + 10) )
      {
        Child = (struct IRequestContext *)FwXmlGetChild(a3, v24);
        v51 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL);
        v52 = FwXmlGetElementNameEx(Child);
        v51(a1, 2150858819LL, 1077134517, v52);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        {
          v53 = FwXmlGetElementNameEx(Child);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids, v53);
        }
        return 0;
      }
      v23 = (_QWORD *)((char *)a2 + 32);
      v25 = *(struct _CONFIGXML_ELEMENT **)(*((_QWORD *)a2 + 4) + 16LL * v22);
      v56 = v25;
      if ( !*(_QWORD *)v25 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 519, L"519", 0x54Fu, a1);
        return 0;
      }
      v26 = -1;
      v27 = *((_QWORD *)a3 + 17) + 152LL * v24;
      do
        ++v26;
      while ( *(_WORD *)(*(_QWORD *)v25 + 2 * v26) );
      if ( !v27 )
        break;
      if ( *(_DWORD *)(v27 + 16) == (_DWORD)v26 )
      {
        v28 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v27);
        if ( !_wcsnicmp(v28, v30, v29) )
        {
          if ( (unsigned int)++v57 > *(_DWORD *)(*v23 + 16LL * v22 + 12) )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)a1 + 64LL))(
              a1,
              2150858819LL,
              1077134519,
              *(_QWORD *)v56);
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              v35 = *(_QWORD *)v56;
              v36 = 23;
              goto LABEL_103;
            }
          }
          else
          {
            if ( (unsigned int)ConfigValidateXMLElement(a1, v56, (struct _FWXML_ELEMENT *)v27, v17) )
            {
              v24 = v55 + 1;
              goto LABEL_34;
            }
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              v13 = 24;
              goto LABEL_12;
            }
          }
          return 0;
        }
        goto LABEL_43;
      }
LABEL_44:
      if ( v57 )
      {
        v24 = v55;
        ++v22;
        v57 = 0;
      }
      else
      {
        if ( *(_DWORD *)(*v23 + 16LL * v22 + 8) )
        {
          v47 = *(_QWORD *)v25;
          v48 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL);
          v49 = FwXmlGetElementNameEx((struct IRequestContext *)v27);
          v48(a1, 2150858819LL, 1077134516, v49, v47);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          {
            v46 = FwXmlGetElementNameEx((struct IRequestContext *)v27);
            v34 = WPP_GLOBAL_Control;
            v36 = 25;
            v35 = v46;
            goto LABEL_103;
          }
          return 0;
        }
        v24 = v55;
        ++v22;
      }
    }
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2060, L"2060", 0x80070057, 0);
LABEL_43:
    v25 = v56;
    goto LABEL_44;
  }
  if ( *((_DWORD *)a3 + 32) )
  {
    v43 = (struct IRequestContext *)FwXmlGetChild(a3, 0);
    v44 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL);
    v45 = FwXmlGetElementNameEx(v43);
    v44(a1, 2150858819LL, 1077134517, v45);
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      v35 = *(_QWORD *)a2;
      v36 = 21;
LABEL_103:
      WPP_SF_S(v34[2], v36, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids, v35);
    }
    return 0;
  }
  else
  {
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      v33 = 20;
LABEL_65:
      WPP_SF_(v31[2], v33, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18003b1c0  push    rbp
0x18003b1c2  push    rsi
0x18003b1c3  push    rdi
0x18003b1c4  push    r12
0x18003b1c6  push    r14
0x18003b1c8  sub     rsp, 40h
0x18003b1cc  mov     rdi, r9
0x18003b1cf  mov     rbp, r8
0x18003b1d2  mov     rsi, rdx
0x18003b1d5  mov     r14, rcx
0x18003b1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b1df  lea     r12, WPP_GLOBAL_Control
0x18003b1e6  cmp     rcx, r12
0x18003b1e9  jnz     loc_18003B5A7
0x18003b1ef  test    r14, r14
0x18003b1f2  jz      loc_18003B6AA
0x18003b1f8  test    rsi, rsi
0x18003b1fb  jz      loc_18003B6EC
0x18003b201  test    rbp, rbp
0x18003b204  jz      loc_18003B716
0x18003b20a  mov     r9, [rsi]
0x18003b20d  test    r9, r9
0x18003b210  jz      loc_18003B740
0x18003b216  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003b21d  nop     dword ptr [rax]
0x18003b220  inc     rax
0x18003b223  cmp     word ptr [r9+rax*2], 0
0x18003b229  jnz     short loc_18003B220
0x18003b22b  mov     [rsp+68h+arg_8], rbx
0x18003b230  mov     [rsp+68h+arg_10], r13
0x18003b238  mov     [rsp+68h+arg_18], r15
0x18003b240  cmp     [rbp+10h], eax
0x18003b243  jz      short loc_18003B2AC
0x18003b245  mov     rax, [r14]
0x18003b248  mov     rcx, rbp; struct IRequestContext *
0x18003b24b  mov     rbx, [rsi]
0x18003b24e  mov     rdi, [rax+40h]
0x18003b252  call    FwXmlGetElementNameEx
0x18003b257  mov     r9, rax
0x18003b25a  mov     [rsp+68h+var_48], rbx
0x18003b25f  mov     rax, rdi
0x18003b262  mov     edx, 80338043h
0x18003b267  mov     r8d, 4033C4B4h
0x18003b26d  mov     rcx, r14
0x18003b270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b275  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b27c  cmp     rcx, r12
0x18003b27f  jz      loc_18003B351
0x18003b285  test    dword ptr [rcx+1Ch], 200000h
0x18003b28c  jz      loc_18003B351
0x18003b292  mov     edx, 0Eh
0x18003b297  mov     rcx, [rcx+10h]
0x18003b29b  lea     r8, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids
0x18003b2a2  call    WPP_SF_
0x18003b2a7  jmp     loc_18003B351
0x18003b2ac  mov     rcx, rbp
0x18003b2af  mov     r8d, eax
0x18003b2b2  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003b2b7  mov     rcx, rax; String1
0x18003b2ba  mov     rdx, r9; String2
0x18003b2bd  call    cs:__imp__wcsnicmp
0x18003b2c3  test    eax, eax
0x18003b2c5  jnz     loc_18003B245
0x18003b2cb  mov     rbx, [rsi+8]
0x18003b2cf  test    rbx, rbx
0x18003b2d2  jnz     short loc_18003B2E0
0x18003b2d4  test    rdi, rdi
0x18003b2d7  jz      loc_18003B76A
0x18003b2dd  mov     rbx, rdi
0x18003b2e0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003b2e7  nop     word ptr [rax+rax+00000000h]
0x18003b2f0  inc     rax
0x18003b2f3  cmp     word ptr [rbx+rax*2], 0
0x18003b2f8  jnz     short loc_18003B2F0
0x18003b2fa  lea     rcx, [rbp+30h]
0x18003b2fe  test    rcx, rcx
0x18003b301  jz      loc_18003B7D4
0x18003b307  cmp     [rcx+10h], eax
0x18003b30a  jnz     short loc_18003B324
0x18003b30c  mov     r8d, eax
0x18003b30f  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003b314  mov     rcx, rax; String1
0x18003b317  mov     rdx, rbx; String2
0x18003b31a  call    cs:__imp__wcsnicmp
0x18003b320  test    eax, eax
0x18003b322  jz      short loc_18003B374
0x18003b324  mov     rax, [r14]
0x18003b327  mov     edx, 80338043h
0x18003b32c  mov     r9, [rsi]
0x18003b32f  mov     r8d, 4033C4B6h
0x18003b335  mov     rcx, r14
0x18003b338  mov     rax, [rax+40h]
0x18003b33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b341  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b348  cmp     rcx, r12
0x18003b34b  jnz     loc_18003BA86
0x18003b351  xor     eax, eax
0x18003b353  mov     r13, [rsp+68h+arg_10]
0x18003b35b  mov     rbx, [rsp+68h+arg_8]
0x18003b360  mov     r15, [rsp+68h+arg_18]
0x18003b368  add     rsp, 40h
0x18003b36c  pop     r14
0x18003b36e  pop     r12
0x18003b370  pop     rdi
0x18003b371  pop     rsi
0x18003b372  pop     rbp
0x18003b373  retn
0x18003b374  cmp     dword ptr [rsi+2Ch], 0
0x18003b378  jnz     loc_18003B498
0x18003b37e  mov     rcx, rbp
0x18003b381  call    FwXmlIsSimpleContent
0x18003b386  test    eax, eax
0x18003b388  jnz     loc_18003B800
0x18003b38e  cmp     [rbp+48h], eax
0x18003b391  ja      loc_18003B5CE
0x18003b397  cmp     dword ptr [rsi+2Ch], 0
0x18003b39b  jnz     loc_18003B498
0x18003b3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3a8  cmp     rcx, r12
0x18003b3ab  jz      short loc_18003B3BA
0x18003b3ad  test    dword ptr [rcx+1Ch], 200000h
0x18003b3b4  jnz     loc_18003B836
0x18003b3ba  mov     r9, rbx; unsigned __int16 *
0x18003b3bd  mov     r8, rbp; struct _FWXML_ELEMENT *
0x18003b3c0  mov     rdx, rsi; struct _CONFIGXML_ELEMENT *
0x18003b3c3  mov     rcx, r14; struct IRequestContext *
0x18003b3c6  call    ?ConfigValidateXMLElementAttributes@@YAHPEAVIRequestContext@@PEAU_CONFIGXML_ELEMENT@@PEAU_FWXML_ELEMENT@@PEBG@Z; ConfigValidateXMLElementAttributes(IRequestContext *,_CONFIGXML_ELEMENT *,_FWXML_ELEMENT *,ushort const *)
0x18003b3cb  test    eax, eax
0x18003b3cd  jz      loc_18003B4C0
0x18003b3d3  cmp     dword ptr [rsi+28h], 0
0x18003b3d7  jz      loc_18003B525
0x18003b3dd  xor     edi, edi
0x18003b3df  lea     r15, [rsi+20h]
0x18003b3e3  xor     ecx, ecx
0x18003b3e5  mov     [rsp+68h+arg_0], ecx
0x18003b3e9  mov     [rsp+68h+var_38], ecx
0x18003b3ed  cmp     ecx, [rbp+80h]
0x18003b3f3  jnb     loc_18003B555
0x18003b3f9  cmp     edi, [rsi+28h]
0x18003b3fc  jnb     loc_18003B991
0x18003b402  mov     rax, [rsi+20h]
0x18003b406  lea     r15, [rsi+20h]
0x18003b40a  mov     r12d, edi
0x18003b40d  add     r12, r12
0x18003b410  mov     rdx, [rax+r12*8]
0x18003b414  mov     [rsp+68h+var_30], rdx
0x18003b419  mov     r9, [rdx]
0x18003b41c  test    r9, r9
0x18003b41f  jz      loc_18003B969
0x18003b425  mov     eax, ecx
0x18003b427  imul    r13, rax, 98h
0x18003b42e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003b435  add     r13, [rbp+88h]
0x18003b43c  nop     dword ptr [rax+00h]
0x18003b440  inc     rax
0x18003b443  cmp     word ptr [r9+rax*2], 0
0x18003b449  jnz     short loc_18003B440
0x18003b44b  test    r13, r13
0x18003b44e  jz      loc_18003B67E
0x18003b454  cmp     [r13+10h], eax
0x18003b458  jnz     short loc_18003B47A
0x18003b45a  mov     rcx, r13
0x18003b45d  mov     r8d, eax
0x18003b460  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003b465  mov     rcx, rax; String1
0x18003b468  mov     rdx, r9; String2
0x18003b46b  call    cs:__imp__wcsnicmp
0x18003b471  test    eax, eax
0x18003b473  jz      short loc_18003B4E7
0x18003b475  mov     rdx, [rsp+68h+var_30]
0x18003b47a  cmp     [rsp+68h+arg_0], 0
0x18003b47f  jbe     loc_18003B612
0x18003b485  mov     ecx, [rsp+68h+var_38]
0x18003b489  inc     edi
0x18003b48b  mov     [rsp+68h+arg_0], 0
0x18003b493  jmp     loc_18003B3ED
0x18003b498  mov     r9d, 54Fh; unsigned int
0x18003b49e  mov     [rsp+68h+var_48], r14; struct IRequestContext *
0x18003b4a3  lea     r8, a448; "448"
0x18003b4aa  mov     edx, 1C0h; unsigned int
0x18003b4af  lea     rcx, aOnecoreAdminWm_113; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x18003b4b6  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003b4bb  jmp     loc_18003B351
0x18003b4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4c7  cmp     rcx, r12
0x18003b4ca  jz      loc_18003B351
0x18003b4d0  test    dword ptr [rcx+1Ch], 200000h
0x18003b4d7  jz      loc_18003B351
0x18003b4dd  mov     edx, 13h
0x18003b4e2  jmp     loc_18003B297
0x18003b4e7  mov     ecx, [rsp+68h+arg_0]
0x18003b4eb  mov     rax, [r15]
0x18003b4ee  inc     ecx
0x18003b4f0  mov     [rsp+68h+arg_0], ecx
0x18003b4f4  cmp     ecx, [rax+r12*8+0Ch]
0x18003b4f9  mov     rcx, r14; struct IRequestContext *
0x18003b4fc  ja      loc_18003B62C
0x18003b502  mov     rdx, [rsp+68h+var_30]; struct _CONFIGXML_ELEMENT *
0x18003b507  mov     r9, rbx; unsigned __int16 *
0x18003b50a  mov     r8, r13; struct _FWXML_ELEMENT *
0x18003b50d  call    ?ConfigValidateXMLElement@@YAHPEAVIRequestContext@@PEAU_CONFIGXML_ELEMENT@@PEAU_FWXML_ELEMENT@@PEBG@Z; ConfigValidateXMLElement(IRequestContext *,_CONFIGXML_ELEMENT *,_FWXML_ELEMENT *,ushort const *)
0x18003b512  test    eax, eax
0x18003b514  jz      loc_18003B8B6
0x18003b51a  mov     ecx, [rsp+68h+var_38]
0x18003b51e  inc     ecx
0x18003b520  jmp     loc_18003B3E9
0x18003b525  cmp     dword ptr [rbp+80h], 0
0x18003b52c  jnz     loc_18003B85D
0x18003b532  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b539  cmp     rcx, r12
0x18003b53c  jz      short loc_18003B54B
0x18003b53e  test    dword ptr [rcx+1Ch], 200000h
0x18003b545  jnz     loc_18003B853
0x18003b54b  mov     eax, 1
0x18003b550  jmp     loc_18003B353
0x18003b555  mov     eax, [rsp+68h+arg_0]
0x18003b559  lea     rcx, [rsi+20h]
0x18003b55d  mov     edx, [rsi+28h]
0x18003b560  test    eax, eax
0x18003b562  cmovnz  r15, rcx
0x18003b566  lea     ecx, [rdi+1]
0x18003b569  cmovz   ecx, edi
0x18003b56c  cmp     ecx, edx
0x18003b56e  jb      loc_18003BA16
0x18003b574  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b57b  lea     rdx, WPP_GLOBAL_Control
0x18003b582  cmp     rcx, rdx
0x18003b585  jz      short loc_18003B54B
0x18003b587  test    dword ptr [rcx+1Ch], 200000h
0x18003b58e  jz      short loc_18003B54B
0x18003b590  mov     edx, 1Bh
0x18003b595  mov     rcx, [rcx+10h]
0x18003b599  lea     r8, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids
0x18003b5a0  call    WPP_SF_
0x18003b5a5  jmp     short loc_18003B54B
0x18003b5a7  test    dword ptr [rcx+1Ch], 200000h
0x18003b5ae  jz      loc_18003B1EF
0x18003b5b4  mov     rcx, [rcx+10h]
0x18003b5b8  lea     r8, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids
0x18003b5bf  mov     edx, 0Dh
0x18003b5c4  call    WPP_SF_
0x18003b5c9  jmp     loc_18003B1EF
0x18003b5ce  mov     rax, [r14]
0x18003b5d1  mov     edx, 80338043h
0x18003b5d6  mov     r9, [rsi]
0x18003b5d9  mov     r8d, 4033C4B9h
0x18003b5df  mov     rcx, r14
0x18003b5e2  mov     rax, [rax+40h]
0x18003b5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b5f2  cmp     rcx, r12
0x18003b5f5  jz      loc_18003B351
0x18003b5fb  test    dword ptr [rcx+1Ch], 200000h
0x18003b602  jz      loc_18003B351
0x18003b608  mov     edx, 11h
0x18003b60d  jmp     loc_18003B297
0x18003b612  mov     rax, [r15]
0x18003b615  cmp     dword ptr [rax+r12*8+8], 0
0x18003b61b  jnz     loc_18003B910
0x18003b621  mov     ecx, [rsp+68h+var_38]
0x18003b625  inc     edi
0x18003b627  jmp     loc_18003B3ED
0x18003b62c  mov     rax, [r14]
0x18003b62f  mov     edx, 80338043h
0x18003b634  mov     r12, [rsp+68h+var_30]
0x18003b639  mov     r8d, 4033C4B7h
0x18003b63f  mov     rax, [rax+40h]
0x18003b643  mov     r9, [r12]
0x18003b647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b64c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b653  lea     rdx, WPP_GLOBAL_Control
0x18003b65a  cmp     rcx, rdx
0x18003b65d  jz      loc_18003B351
0x18003b663  test    dword ptr [rcx+1Ch], 200000h
0x18003b66a  jz      loc_18003B351
0x18003b670  mov     r9, [r12]
0x18003b674  mov     edx, 17h
0x18003b679  jmp     loc_18003B8FB
0x18003b67e  mov     r9d, 80070057h; unsigned int
0x18003b684  mov     [rsp+68h+var_48], 0; struct IRequestContext *
0x18003b68d  lea     r8, a2060; "2060"
0x18003b694  mov     edx, 80Ch; unsigned int
0x18003b699  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18003b6a0  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003b6a5  jmp     loc_18003B475
0x18003b6aa  mov     r9d, 54Fh; unsigned int
0x18003b6b0  mov     [rsp+68h+var_48], 0; struct IRequestContext *
0x18003b6b9  lea     r8, a406; "406"
0x18003b6c0  mov     edx, 196h; unsigned int
0x18003b6c5  lea     rcx, aOnecoreAdminWm_113; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x18003b6cc  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003b6d1  xor     eax, eax
0x18003b6d3  add     rsp, 40h
0x18003b6d7  pop     r14
0x18003b6d9  pop     r12
0x18003b6db  pop     rdi
0x18003b6dc  pop     rsi
0x18003b6dd  pop     rbp
0x18003b6de  retn
0x18003b6df  test    eax, eax
  ... truncated ...
```
