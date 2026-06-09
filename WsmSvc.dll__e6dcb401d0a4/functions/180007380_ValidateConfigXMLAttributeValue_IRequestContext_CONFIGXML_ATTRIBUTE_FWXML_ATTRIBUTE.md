# ValidateConfigXMLAttributeValue(IRequestContext *,_CONFIGXML_ATTRIBUTE *,FWXML_ATTRIBUTE *)

- ea: `0x180007380`
- end: `0x180007faa`
- name: `?ValidateConfigXMLAttributeValue@@YAHPEAVIRequestContext@@PEAU_CONFIGXML_ATTRIBUTE@@PEAUFWXML_ATTRIBUTE@@@Z`
- size: `3114`
- prototype: `__int64 __fastcall(struct IRequestContext *, struct _CONFIGXML_ATTRIBUTE *, struct FWXML_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180007fb0`

## callees

- `0x180005d10`
- `0x180007380`
- `0x180035ee0`
- `0x18003c640`
- `0x180112380`
- `0x1801133b0`
- `0x18012a93c`
- `0x1801ba182`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180007853`
- `msvcrt!_itow_s` at `0x18000786d`
- `msvcrt!_itow_s` at `0x180007853`
- `msvcrt!_itow_s` at `0x18000786d`
- `msvcrt!_wtoi64` at `0x1800078f5`
- `msvcrt!_wtoi64` at `0x1800078f5`
- `msvcrt!_wcsnicmp` at `0x1800074e7`
- `msvcrt!_wcsnicmp` at `0x1800074e7`
- `msvcrt!wcschr` at `0x180007b0f`
- `msvcrt!wcschr` at `0x180007b26`
- `msvcrt!wcschr` at `0x180007b0f`
- `msvcrt!wcschr` at `0x180007b26`
- `msvcrt!_wcsicmp` at `0x18000766a`
- `msvcrt!_wcsicmp` at `0x180007682`
- `msvcrt!_wcsicmp` at `0x18000769a`
- `msvcrt!_wcsicmp` at `0x1800076b2`
- `msvcrt!_wcsicmp` at `0x1800076ca`
- `msvcrt!_wcsicmp` at `0x1800076e2`
- `msvcrt!_wcsicmp` at `0x1800076fa`
- `msvcrt!_wcsicmp` at `0x180007712`
- `msvcrt!_wcsicmp` at `0x1800077b6`
- `msvcrt!_wcsicmp` at `0x180007804`
- `msvcrt!_wcsicmp` at `0x18000798d`
- `msvcrt!_wcsicmp` at `0x180007bdc`
- `msvcrt!_wcsicmp` at `0x180007bf4`
- `msvcrt!_wcsicmp` at `0x180007c51`
- `msvcrt!_wcsicmp` at `0x18000766a`
- `msvcrt!_wcsicmp` at `0x180007682`
- `msvcrt!_wcsicmp` at `0x18000769a`
- `msvcrt!_wcsicmp` at `0x1800076b2`
- `msvcrt!_wcsicmp` at `0x1800076ca`
- `msvcrt!_wcsicmp` at `0x1800076e2`
- `msvcrt!_wcsicmp` at `0x1800076fa`
- `msvcrt!_wcsicmp` at `0x180007712`
- `msvcrt!_wcsicmp` at `0x1800077b6`
- `msvcrt!_wcsicmp` at `0x180007804`
- `msvcrt!_wcsicmp` at `0x18000798d`
- `msvcrt!_wcsicmp` at `0x180007bdc`
- `msvcrt!_wcsicmp` at `0x180007bf4`
- `msvcrt!_wcsicmp` at `0x180007c51`

## string_xrefs

- `0x180007434`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x1800075f4`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x180007cd6`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x180007d00`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x180007d2a`: `onecore\admin\wmi\wmx\config\configxmlvalidation.cpp`
- `0x1800075d1`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180007bb8`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180007d58`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180007690`: `Create`
- `0x1800076a8`: `Delete`
- `0x180007c5f`: `XmlReader`

## pseudocode

```c
__int64 __fastcall ValidateConfigXMLAttributeValue(
        struct IRequestContext *a1,
        struct _CONFIGXML_ATTRIBUTE *a2,
        struct FWXML_ATTRIBUTE *a3)
{
  struct _CONFIGXML_ATTRIBUTE *v4; // rbp
  struct IRequestContext *v5; // r13
  __int64 v6; // r9
  __int64 v7; // r12
  __int64 v8; // rax
  unsigned __int64 v10; // rax
  _QWORD *v11; // rcx
  const wchar_t *v12; // rax
  size_t v13; // r8
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  _QWORD *v16; // rax
  wchar_t *v17; // rbx
  __int64 v18; // r14
  unsigned int v19; // esi
  unsigned int v20; // ecx
  unsigned int v21; // r15d
  int v22; // edi
  wchar_t v23; // bp
  __int64 v24; // r12
  PVOID *v25; // r10
  int v26; // ecx
  int v27; // eax
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  int v30; // ecx
  wchar_t v31; // cx
  unsigned int v32; // ecx
  __int64 v33; // rax
  wchar_t *v35; // r9
  __int64 v36; // rdx
  int i; // r13d
  __int64 v38; // [rsp+40h] [rbp-98h]
  wchar_t v41[16]; // [rsp+58h] [rbp-80h] BYREF
  wchar_t Buffer[16]; // [rsp+78h] [rbp-60h] BYREF

  v4 = a2;
  v5 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
  if ( !v5 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 743, L"743", 0x54Fu, 0);
    return 0;
  }
  if ( !v4 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 744, L"744", 0x54Fu, v5);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 745, L"745", 0x54Fu, v5);
    return 0;
  }
  v6 = *(_QWORD *)v4;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(v6 + 2 * v8) );
  if ( !v6 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 2097, L"2097", 0x80070057, 0);
LABEL_9:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 748, L"748", 0x54Fu, v5);
    return 0;
  }
  if ( *((_DWORD *)a3 + 4) != (_DWORD)v8 )
    goto LABEL_9;
  v12 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(a3);
  if ( _wcsnicmp(v12, v14, v13) )
    goto LABEL_9;
  if ( *((_DWORD *)a3 + 24) != 1 )
  {
LABEL_28:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 753, L"753", 0x54Fu, v5);
    return 0;
  }
  v15 = *((_QWORD *)a3 + 10);
  if ( v15 == -1 )
  {
    v17 = (wchar_t *)*((_QWORD *)a3 + 9);
  }
  else
  {
    v16 = (_QWORD *)*((_QWORD *)a3 + 9);
    if ( !v16 )
    {
      *(_WORD *)(2LL * *((unsigned int *)a3 + 22)) = 0;
      goto LABEL_102;
    }
    v17 = (wchar_t *)(*v16 + 2 * v15);
  }
  v18 = *((unsigned int *)a3 + 22);
  v19 = 0;
  v17[v18] = 0;
  if ( !v17 )
  {
LABEL_102:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 1100, L"1100", 0x54Fu, 0);
LABEL_27:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 1410, L"1410", 0x54Fu, 0);
    goto LABEL_28;
  }
  v20 = v18 + 1;
  v21 = 0;
  v22 = 0;
  if ( (_DWORD)v18 )
  {
    do
    {
      v23 = v17[v22];
      v24 = v21;
      if ( v23 == 38 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i == 5 )
          {
            v20 = v18 + 1;
            goto LABEL_22;
          }
          v38 = 3LL * i;
          if ( !wcsncmp_0(&v17[v22], (&off_18027B038)[v38], LODWORD(qword_18027B040[v38])) )
            break;
        }
        v20 = v18 + 1;
        if ( ++v21 <= (int)v18 + 1 )
        {
          v20 = v18 + 1;
          v17[v24] = qword_18027B030[v38];
        }
        v22 = LODWORD(qword_18027B040[v38]) + v22 - 1;
      }
      else
      {
LABEL_22:
        if ( ++v21 <= v20 )
          v17[v24] = v23;
      }
      ++v22;
    }
    while ( v22 < (unsigned int)v18 );
    v5 = a1;
    v19 = 0;
    v4 = a2;
    v7 = -1;
  }
  if ( v21 + 1 > v20 )
    goto LABEL_27;
  v17[v21] = 0;
  v10 = -1;
  do
    ++v10;
  while ( v17[v10] );
  if ( v10 > 0x27FF )
  {
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)v5 + 64LL))(
      v5,
      2150858819LL,
      1077134525,
      *(_QWORD *)v4);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      v36 = 39;
LABEL_99:
      WPP_SF_(v11[2], v36, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
    }
    return 0;
  }
  v25 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids, v17);
    v25 = (PVOID *)WPP_GLOBAL_Control;
  }
  v26 = *((_DWORD *)v4 + 4);
  if ( v26 == 4 )
    goto LABEL_33;
  v30 = v26 - 1;
  if ( v30 )
  {
    if ( v30 != 1 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmlvalidation.cpp", 803, L"803", 0x54Fu, v5);
      return 0;
    }
    if ( !_wcsicmp(v17, L"true") || !_wcsicmp(v17, L"false") )
      goto LABEL_69;
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
      v5,
      2150858819LL,
      1077134527,
      v17);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      return 0;
    v29 = 42;
LABEL_80:
    v35 = v17;
LABEL_81:
    WPP_SF_S(v28[2], v29, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids, v35);
    return 0;
  }
  if ( !_wcsicmp(v17, &Class) )
    goto LABEL_82;
  while ( 1 )
  {
    v31 = v17[v19];
    if ( !v31 )
      break;
    if ( v19 > 0xA || (unsigned __int16)(v31 - 48) > 9u )
      goto LABEL_82;
    ++v19;
  }
  if ( v19 > 0xA || (v33 = _wtoi64(v17), v33 > 0xFFFFFFFFLL) )
  {
LABEL_82:
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
      v5,
      2150858819LL,
      1077134526,
      v17);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
      return 0;
    v29 = 41;
    goto LABEL_80;
  }
  v19 = v33;
LABEL_69:
  v25 = (PVOID *)WPP_GLOBAL_Control;
LABEL_33:
  v27 = *((_DWORD *)v4 + 5);
  if ( v27 != 26 )
  {
    switch ( v27 )
    {
      case 2:
        if ( !_wcsicmp(v17, L"Get")
          || !_wcsicmp(v17, L"Put")
          || !_wcsicmp(v17, L"Create")
          || !_wcsicmp(v17, L"Delete")
          || !_wcsicmp(v17, L"Invoke")
          || !_wcsicmp(v17, L"Enumerate")
          || !_wcsicmp(v17, L"Subscribe")
          || !_wcsicmp(v17, L"Shell")
          || (unsigned int)StringCchEqualsCI(v17, (wchar_t *)L"Identify") )
        {
          goto LABEL_56;
        }
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
          v5,
          2150858819LL,
          1077134528,
          v17);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
          return 0;
        v29 = 43;
        goto LABEL_80;
      case 4:
        while ( v17[++v7] != 0 )
          ;
        if ( (unsigned int)(v7 - 1) <= 0xFE )
        {
          if ( *v17 == 32 || *v17 == 9 )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
              v5,
              2150858819LL,
              1077134529,
              v17);
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              v29 = 45;
              goto LABEL_80;
            }
          }
          else if ( wcschr(v17, 0x5Cu) )
          {
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
              v5,
              2150858819LL,
              1077134529,
              v17);
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              v29 = 46;
              goto LABEL_80;
            }
          }
          else
          {
            if ( !wcschr(v17, 0x22u) )
            {
LABEL_56:
              v25 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_57;
            }
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)v5 + 64LL))(
              v5,
              2150858819LL,
              1077134529,
              *(_QWORD *)v4);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              v36 = 47;
              goto LABEL_99;
            }
          }
        }
        else
        {
          (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
            v5,
            2150858819LL,
            1077134529,
            v17);
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          {
            v29 = 44;
            goto LABEL_80;
          }
        }
        break;
      case 6:
        if ( v19 - 1 <= 1 )
          goto LABEL_57;
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
          v5,
          2150858819LL,
          1077134530,
          v17);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
          return 0;
        v29 = 48;
        goto LABEL_80;
      case 7:
        if ( !_wcsicmp(v17, L"text") || (unsigned int)StringCchEqualsCI(v17, (wchar_t *)L"XmlReader") )
          goto LABEL_56;
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
          v5,
          2150858819LL,
          1077134531,
          v17);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
          return 0;
        v29 = 49;
        goto LABEL_80;
      case 16:
      case 17:
        if ( _wcsicmp(v17, &Class) )
          goto LABEL_56;
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64))(*(_QWORD *)v5 + 64LL))(
          v5,
          2150858819LL,
          1077134556);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
          return 0;
        v35 = *(wchar_t **)v4;
        v29 = 50;
        goto LABEL_81;
      case 18:
        if ( ((v19 - 32) & 0xFFFFFFDF) == 0 )
          goto LABEL_57;
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *))(*(_QWORD *)v5 + 64LL))(
          v5,
          2150858819LL,
          1077134565,
          v17);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
          return 0;
        v29 = 51;
        goto LABEL_80;
      case 20:
        goto LABEL_61;
      case 27:
        if ( !_wcsicmp(v17, L"Block") || (unsigned int)StringCchEqualsCI(v17, (wchar_t *)L"Drop") )
          goto LABEL_56;
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v5 + 64LL))(
          v5,
          2150858819LL,
          1077134587,
          v17,
          L"Block",
          L"Drop");
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
          return 0;
        v29 = 53;
        goto LABEL_80;
      default:
        goto LABEL_57;
    }
    return 0;
  }
LABEL_61:
  v32 = *((_DWORD *)v4 + 7);
  if ( v19 < v32 || v19 > *((_DWORD *)v4 + 8) )
  {
    _itow_s(v32, Buffer, 0xFu, 10);
    _itow_s(*((_DWORD *)v4 + 8), v41, 0xFu, 10);
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD, wchar_t *, wchar_t *))(*(_QWORD *)v5 + 64LL))(
      v5,
      2150858819LL,
      1077134578,
      *(_QWORD *)v4,
      Buffer,
      v41);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        (unsigned int)WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids,
        v19,
        *(_QWORD *)v4);
    return 0;
  }
LABEL_57:
  if ( v25 != &WPP_GLOBAL_Control && (*((_DWORD *)v25 + 7) & 0x200000) != 0 )
    WPP_SF_(v25[2], 54, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x180007380  push    rbp
0x180007382  push    rdi
0x180007383  push    r13
0x180007385  sub     rsp, 0C0h
0x18000738c  mov     rax, cs:__security_cookie
0x180007393  xor     rax, rsp
0x180007396  mov     [rsp+0D8h+var_40], rax
0x18000739e  mov     rdi, r8
0x1800073a1  mov     [rsp+0D8h+var_88], rdx
0x1800073a6  mov     rbp, rdx
0x1800073a9  mov     [rsp+0D8h+var_90], rcx
0x1800073ae  mov     r13, rcx
0x1800073b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073b8  lea     rax, WPP_GLOBAL_Control
0x1800073bf  cmp     rcx, rax
0x1800073c2  jnz     loc_18000777C
0x1800073c8  test    r13, r13
0x1800073cb  jz      loc_180007CBB
0x1800073d1  test    rbp, rbp
0x1800073d4  jz      loc_180007CE9
0x1800073da  test    rdi, rdi
0x1800073dd  jz      loc_180007D13
0x1800073e3  mov     r9, [rbp+0]
0x1800073e7  mov     [rsp+0D8h+var_28], r12
0x1800073ef  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800073f6  mov     rax, r12
0x1800073f9  nop     dword ptr [rax+00000000h]
0x180007400  inc     rax
0x180007403  cmp     word ptr [r9+rax*2], 0
0x180007409  jnz     short loc_180007400
0x18000740b  test    r9, r9
0x18000740e  jz      loc_180007D3D
0x180007414  cmp     [rdi+10h], eax
0x180007417  jz      loc_1800074D6
0x18000741d  mov     r9d, 54Fh; unsigned int
0x180007423  mov     [rsp+0D8h+var_B8], r13; struct IRequestContext *
0x180007428  lea     r8, a748; "748"
0x18000742f  mov     edx, 2ECh; unsigned int
0x180007434  lea     rcx, aOnecoreAdminWm_113; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x18000743b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180007440  xor     eax, eax
0x180007442  jmp     short loc_1800074B2
0x180007444  inc     rax
0x180007447  cmp     word ptr [rbx+rax*2], 0
0x18000744c  jnz     short loc_180007444
0x18000744e  cmp     rax, 27FFh
0x180007454  jbe     loc_180007605
0x18000745a  mov     rax, [r13+0]
0x18000745e  mov     edx, 80338043h
0x180007463  mov     r9, [rbp+0]
0x180007467  mov     r8d, 4033C4BDh
0x18000746d  mov     rcx, r13
0x180007470  mov     rax, [rax+40h]
0x180007474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007479  mov     rcx, cs:WPP_GLOBAL_Control
0x180007480  lea     r14, WPP_GLOBAL_Control
0x180007487  cmp     rcx, r14
0x18000748a  jnz     loc_180007E14
0x180007490  xor     eax, eax
0x180007492  mov     r14, [rsp+0D8h+var_30]
0x18000749a  mov     rbx, [rsp+0D8h+arg_18]
0x1800074a2  mov     rsi, [rsp+0D8h+var_20]
0x1800074aa  mov     r15, [rsp+0D8h+var_38]
0x1800074b2  mov     r12, [rsp+0D8h+var_28]
0x1800074ba  mov     rcx, [rsp+0D8h+var_40]
0x1800074c2  xor     rcx, rsp; StackCookie
0x1800074c5  call    __security_check_cookie
0x1800074ca  add     rsp, 0C0h
0x1800074d1  pop     r13
0x1800074d3  pop     rdi
0x1800074d4  pop     rbp
0x1800074d5  retn
0x1800074d6  mov     rcx, rdi
0x1800074d9  mov     r8d, eax
0x1800074dc  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x1800074e1  mov     rcx, rax; String1
0x1800074e4  mov     rdx, r9; String2
0x1800074e7  call    cs:__imp__wcsnicmp
0x1800074ed  test    eax, eax
0x1800074ef  jnz     loc_18000741D
0x1800074f5  cmp     dword ptr [rdi+60h], 1
0x1800074f9  mov     [rsp+0D8h+arg_18], rbx
0x180007501  mov     [rsp+0D8h+var_20], rsi
0x180007509  mov     [rsp+0D8h+var_30], r14
0x180007511  mov     [rsp+0D8h+var_38], r15
0x180007519  jnz     loc_1800075DD
0x18000751f  mov     rcx, [rdi+50h]
0x180007523  cmp     rcx, r12
0x180007526  jz      loc_180007B8B
0x18000752c  mov     rax, [rdi+48h]
0x180007530  test    rax, rax
0x180007533  jz      loc_180007B94
0x180007539  mov     rax, [rax]
0x18000753c  lea     rbx, [rax+rcx*2]
0x180007540  mov     r14d, [rdi+58h]
0x180007544  xor     esi, esi
0x180007546  mov     [rbx+r14*2], si
0x18000754b  test    rbx, rbx
0x18000754e  jz      loc_180007BA1
0x180007554  lea     ecx, [r14+1]
0x180007558  mov     r15d, esi
0x18000755b  lea     rdx, __ImageBase
0x180007562  mov     edi, esi
0x180007564  test    r14d, r14d
0x180007567  jz      short loc_1800075AE
0x180007569  nop     dword ptr [rax+00000000h]
0x180007570  movsxd  rax, edi
0x180007573  movzx   ebp, word ptr [rbx+rax*2]
0x180007577  lea     rsi, [rbx+rax*2]
0x18000757b  mov     r12d, r15d
0x18000757e  cmp     bp, 26h ; '&'
0x180007582  jz      loc_180007D69
0x180007588  inc     r15d
0x18000758b  cmp     r15d, ecx
0x18000758e  jbe     loc_180007DFB
0x180007594  inc     edi
0x180007596  cmp     edi, r14d
0x180007599  jb      short loc_180007570
0x18000759b  mov     r13, [rsp+0D8h+var_90]
0x1800075a0  xor     esi, esi
0x1800075a2  mov     rbp, [rsp+0D8h+var_88]
0x1800075a7  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800075ae  lea     eax, [r15+1]
0x1800075b2  cmp     eax, ecx
0x1800075b4  jbe     loc_180007E05
0x1800075ba  mov     r9d, 54Fh; unsigned int
0x1800075c0  mov     [rsp+0D8h+var_B8], rsi; struct IRequestContext *
0x1800075c5  lea     r8, a1410; "1410"
0x1800075cc  mov     edx, 582h; unsigned int
0x1800075d1  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x1800075d8  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800075dd  mov     [rsp+0D8h+var_B8], r13; struct IRequestContext *
0x1800075e2  lea     r8, a753; "753"
0x1800075e9  mov     r9d, 54Fh; unsigned int
0x1800075ef  mov     edx, 2F1h; unsigned int
0x1800075f4  lea     rcx, aOnecoreAdminWm_113; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800075fb  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180007600  jmp     loc_180007490
0x180007605  mov     r10, cs:WPP_GLOBAL_Control
0x18000760c  lea     r14, WPP_GLOBAL_Control
0x180007613  cmp     r10, r14
0x180007616  jz      short loc_180007626
0x180007618  test    dword ptr [r10+1Ch], 200000h
0x180007620  jnz     loc_180007E2B
0x180007626  mov     ecx, [rbp+10h]
0x180007629  cmp     ecx, 4
0x18000762c  jnz     loc_1800077A3
0x180007632  mov     eax, [rbp+14h]
0x180007635  cmp     eax, 1Ah
0x180007638  jz      loc_180007836; jumptable 000000018000765E case 20
0x18000763e  add     eax, 0FFFFFFFEh; switch 26 cases
0x180007641  cmp     eax, 19h
0x180007644  ja      def_18000765E; jumptable 000000018000765E default case, cases 3,5,8-15,19,21-26
0x18000764a  cdqe
0x18000764c  movzx   eax, ds:(byte_180007F90 - 180000000h)[rdx+rax]
0x180007654  mov     ecx, ds:(jpt_18000765E - 180000000h)[rdx+rax*4]
0x18000765b  add     rcx, rdx
0x18000765e  jmp     rcx; switch jump
0x180007660  lea     rdx, aGet; jumptable 000000018000765E case 2
0x180007667  mov     rcx, rbx; String1
0x18000766a  call    cs:__imp__wcsicmp
0x180007670  test    eax, eax
0x180007672  jz      loc_180007812
0x180007678  lea     rdx, aPut; "Put"
0x18000767f  mov     rcx, rbx; String1
0x180007682  call    cs:__imp__wcsicmp
0x180007688  test    eax, eax
0x18000768a  jz      loc_180007812
0x180007690  lea     rdx, aCreate_0; "Create"
0x180007697  mov     rcx, rbx; String1
0x18000769a  call    cs:__imp__wcsicmp
0x1800076a0  test    eax, eax
0x1800076a2  jz      loc_180007812
0x1800076a8  lea     rdx, aDelete; "Delete"
0x1800076af  mov     rcx, rbx; String1
0x1800076b2  call    cs:__imp__wcsicmp
0x1800076b8  test    eax, eax
0x1800076ba  jz      loc_180007812
0x1800076c0  lea     rdx, aInvoke_0; "Invoke"
0x1800076c7  mov     rcx, rbx; String1
0x1800076ca  call    cs:__imp__wcsicmp
0x1800076d0  test    eax, eax
0x1800076d2  jz      loc_180007812
0x1800076d8  lea     rdx, aEnumerate; "Enumerate"
0x1800076df  mov     rcx, rbx; String1
0x1800076e2  call    cs:__imp__wcsicmp
0x1800076e8  test    eax, eax
0x1800076ea  jz      loc_180007812
0x1800076f0  lea     rdx, aSubscribe; "Subscribe"
0x1800076f7  mov     rcx, rbx; String1
0x1800076fa  call    cs:__imp__wcsicmp
0x180007700  test    eax, eax
0x180007702  jz      loc_180007812
0x180007708  lea     rdx, aShell; "Shell"
0x18000770f  mov     rcx, rbx; String1
0x180007712  call    cs:__imp__wcsicmp
0x180007718  test    eax, eax
0x18000771a  jz      loc_180007812
0x180007720  lea     rdx, aIdentify; "Identify"
0x180007727  mov     rcx, rbx; String1
0x18000772a  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x18000772f  test    eax, eax
0x180007731  jnz     loc_180007812
0x180007737  mov     rax, [r13+0]
0x18000773b  mov     r9, rbx
0x18000773e  mov     edx, 80338043h
0x180007743  mov     r8d, 4033C4C0h
0x180007749  mov     rcx, r13
0x18000774c  mov     rax, [rax+40h]
0x180007750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007755  mov     rcx, cs:WPP_GLOBAL_Control
0x18000775c  cmp     rcx, r14
0x18000775f  jz      loc_180007490
0x180007765  test    dword ptr [rcx+1Ch], 200000h
0x18000776c  jz      loc_180007490
0x180007772  mov     edx, 2Bh ; '+'
0x180007777  jmp     loc_1800079FF
0x18000777c  test    dword ptr [rcx+1Ch], 200000h
0x180007783  jz      loc_1800073C8
0x180007789  mov     rcx, [rcx+10h]
0x18000778d  lea     r8, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids
0x180007794  mov     edx, 26h ; '&'
0x180007799  call    WPP_SF_
0x18000779e  jmp     loc_1800073C8
0x1800077a3  sub     ecx, 1
0x1800077a6  jnz     loc_180007BC9
0x1800077ac  lea     rdx, Class; String2
0x1800077b3  mov     rcx, rbx; String1
0x1800077b6  call    cs:__imp__wcsicmp
0x1800077bc  test    eax, eax
0x1800077be  jz      loc_180007A17
0x1800077c4  nop     dword ptr [rax+00h]
0x1800077c8  nop     dword ptr [rax+rax+00000000h]
0x1800077d0  mov     eax, esi
0x1800077d2  movzx   ecx, word ptr [rbx+rax*2]
0x1800077d6  test    cx, cx
0x1800077d9  jz      loc_1800078E9
0x1800077df  cmp     esi, 0Ah
0x1800077e2  ja      loc_180007A17
0x1800077e8  sub     cx, 30h ; '0'
0x1800077ec  cmp     cx, 9
0x1800077f0  ja      loc_180007A17
0x1800077f6  inc     esi
0x1800077f8  jmp     short loc_1800077D0
0x1800077fa  lea     rdx, Class; jumptable 000000018000765E cases 16,17
0x180007801  mov     rcx, rbx; String1
0x180007804  call    cs:__imp__wcsicmp
0x18000780a  test    eax, eax
0x18000780c  jz      loc_180007A59
0x180007812  mov     r10, cs:WPP_GLOBAL_Control
0x180007819  cmp     r10, r14; jumptable 000000018000765E default case, cases 3,5,8-15,19,21-26
0x18000781c  jz      short loc_18000782C
0x18000781e  test    dword ptr [r10+1Ch], 200000h
0x180007826  jnz     loc_180007F4F
0x18000782c  mov     eax, 1
0x180007831  jmp     loc_180007492
0x180007836  mov     ecx, [rbp+1Ch]; jumptable 000000018000765E case 20
0x180007839  cmp     esi, ecx
0x18000783b  jb      short loc_180007842
0x18000783d  cmp     esi, [rbp+20h]
0x180007840  jbe     short def_18000765E; jumptable 000000018000765E default case, cases 3,5,8-15,19,21-26
0x180007842  mov     r9d, 0Ah; Radix
0x180007848  lea     rdx, [rsp+0D8h+Buffer]; Buffer
0x18000784d  mov     r8d, 0Fh; BufferCount
0x180007853  call    cs:__imp__itow_s
0x180007859  mov     ecx, [rbp+20h]; Value
0x18000785c  lea     rdx, [rsp+0D8h+var_80]; Buffer
0x180007861  mov     r9d, 0Ah; Radix
0x180007867  mov     r8d, 0Fh; BufferCount
0x18000786d  call    cs:__imp__itow_s
0x180007873  mov     rax, [r13+0]
0x180007877  lea     rcx, [rsp+0D8h+var_80]
0x18000787c  mov     r9, [rbp+0]
0x180007880  mov     edx, 80338043h
0x180007885  mov     [rsp+0D8h+var_B0], rcx
0x18000788a  mov     r8d, 4033C4F2h
0x180007890  lea     rcx, [rsp+0D8h+Buffer]
0x180007895  mov     rax, [rax+40h]
0x180007899  mov     [rsp+0D8h+var_B8], rcx
0x18000789e  mov     rcx, r13
0x1800078a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078ad  cmp     rcx, r14
0x1800078b0  jz      loc_180007490
0x1800078b6  test    dword ptr [rcx+1Ch], 200000h
0x1800078bd  jz      loc_180007490
0x1800078c3  mov     rax, [rbp+0]
0x1800078c7  lea     r8, WPP_23dc05a4f9a3381f034ef434d85c3ad0_Traceguids
0x1800078ce  mov     rcx, [rcx+10h]
0x1800078d2  mov     edx, 34h ; '4'
0x1800078d7  mov     r9d, esi
0x1800078da  mov     [rsp+0D8h+var_B8], rax
0x1800078df  call    WPP_SF_dS
0x1800078e4  jmp     loc_180007490
0x1800078e9  cmp     esi, 0Ah
0x1800078ec  ja      loc_180007A17
0x1800078f2  mov     rcx, rbx; String
0x1800078f5  call    cs:__imp__wtoi64
0x1800078fb  mov     ecx, 0FFFFFFFFh
0x180007900  cmp     rax, rcx
  ... truncated ...
```
