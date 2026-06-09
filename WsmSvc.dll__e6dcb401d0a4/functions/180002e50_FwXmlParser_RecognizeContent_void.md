# FwXmlParser::RecognizeContent(void)

- ea: `0x180002e50`
- end: `0x180003d68`
- name: `?RecognizeContent@FwXmlParser@@QEAAXXZ`
- size: `3864`
- prototype: `void __fastcall(FwXmlParser *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180002524`

## callees

- `0x18000143c`
- `0x180002d30`
- `0x180002e50`
- `0x180004d30`
- `0x180005bf0`
- `0x180005c70`
- `0x180005d10`
- `0x1800a75f0`
- `0x1800ec448`
- `0x18010d8ac`
- `0x1801ba182`
- `0x1801c2010`

## string_xrefs

- `0x180002fd7`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000343c`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000365c`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000381c`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003853`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003889`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800038bf`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800038f5`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000392b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000396d`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003ac3`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003aef`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003b1b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003b47`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003b73`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003b9f`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003bcb`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003bf7`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003c23`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003c4f`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003c7b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003ca7`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003cd3`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003cff`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003d2b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180003d57`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FwXmlParser::RecognizeContent(FwXmlParser *this)
{
  _QWORD *v1; // r15
  __int64 *v2; // r12
  __int64 v3; // r14
  __int128 v5; // xmm6
  __int64 v6; // rdx
  __int64 v7; // rcx
  _WORD *v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // esi
  __int64 v12; // r14
  unsigned int i; // ebx
  __int16 v14; // ax
  __int64 v15; // rsi
  __int64 v16; // r14
  _QWORD *v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rdi
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rcx
  _QWORD *v28; // rax
  _QWORD *v29; // rbx
  __int64 v30; // rdi
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  _QWORD *v35; // rbx
  __int64 v36; // rdi
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rax
  _QWORD *v41; // rbx
  __int64 v42; // rdi
  __int64 v43; // rcx
  _QWORD *v44; // rax
  __int64 v45; // rcx
  _QWORD *v46; // rax
  __int64 v47; // rcx
  unsigned __int16 v48; // cx
  _QWORD *v49; // rbx
  __int64 v50; // rdi
  __int64 v51; // rcx
  _QWORD *v52; // rax
  __int64 v53; // rcx
  _QWORD *v54; // rax
  _QWORD *v55; // rbx
  __int64 v56; // rdi
  __int64 v57; // rcx
  _QWORD *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  signed int v67; // r12d
  unsigned int j; // r15d
  signed int v69; // r13d
  __int64 *v70; // rcx
  __int64 v71; // rax
  int v72; // eax
  __int64 v73; // rsi
  int v74; // ebx
  void (__fastcall *v75)(__int64, __int64, __int64, __int64, int); // rdi
  __int64 v76; // rax
  __int128 v77; // [rsp+30h] [rbp-78h] BYREF
  __int128 v78; // [rsp+40h] [rbp-68h] BYREF
  char v79[16]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int pExceptionObject; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v81; // [rsp+B8h] [rbp+10h]
  _QWORD *v82; // [rsp+C0h] [rbp+18h]

  v1 = (_QWORD *)*((_QWORD *)this + 2);
  v2 = (__int64 *)((char *)this + 16);
  v3 = *((_QWORD *)this + 3);
  *(_QWORD *)&v77 = v1;
  *((_QWORD *)&v77 + 1) = v3;
  while ( 1 )
  {
    v5 = v77;
LABEL_3:
    v82 = v1;
    v81 = v3;
LABEL_4:
    if ( *((_QWORD *)this + 4) != *v2 || *((_QWORD *)this + 5) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x8Cu, L"140", 0x54Fu, 0);
    v6 = *((_QWORD *)this + 3);
    v7 = *((_QWORD *)this + 5) - v6;
    if ( v6 == -1 )
    {
      v8 = (_WORD *)*v2;
    }
    else if ( *v2 )
    {
      v8 = (_WORD *)(*(_QWORD *)*v2 + 2 * v6);
    }
    else
    {
      v8 = 0;
    }
    while ( 1 )
    {
      if ( !v7 )
      {
LABEL_217:
        FwXmlParser::WaitForMore(this, 1);
        goto LABEL_4;
      }
      if ( *v8 == 60 )
        break;
      ++v8;
      --v7;
    }
    if ( !v8 )
      goto LABEL_217;
    if ( v6 == -1 )
    {
      v9 = *v2;
LABEL_29:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
      goto LABEL_16;
    }
    if ( !*v2 )
    {
      v9 = 0;
      goto LABEL_29;
    }
    v9 = *(_QWORD *)*v2 + 2 * v6;
LABEL_16:
    v10 = (((__int64)v8 - v9) >> 1) + *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v10;
    if ( (_QWORD *)*v2 != v1 || v10 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x8Cu, L"140", 0x54Fu, 0);
    v11 = *((_DWORD *)this + 6) - v3;
    if ( v11 )
    {
      if ( v3 == -1 )
      {
        v12 = (__int64)v1;
      }
      else if ( v1 )
      {
        v12 = *v1 + 2 * v3;
      }
      else
      {
        v12 = 0;
      }
      for ( i = 0; i < v11; ++i )
      {
        v14 = *(_WORD *)(v12 + 2LL * (int)i);
        if ( v14 == 60 )
          goto LABEL_27;
        if ( v14 != 38 )
          continue;
        v67 = v11 - i;
        for ( j = 0; j < 5; ++j )
        {
          v69 = qword_18027B030[3 * (int)j + 2];
          if ( v67 >= v69
            && !wcsncmp_0(
                  (const wchar_t *)qword_18027B030[3 * (int)j + 1],
                  (const wchar_t *)(v12 + 2LL * (int)i),
                  (unsigned int)v69) )
          {
            i += v69;
            goto LABEL_26;
          }
        }
        pExceptionObject = 0;
        if ( !(unsigned int)IsXmlCharacterReference(
                              v67,
                              (const unsigned __int16 *)(v12 + 2LL * (int)i),
                              &pExceptionObject) )
        {
LABEL_27:
          pExceptionObject = 7;
          throw (int *)&pExceptionObject;
        }
        i += pExceptionObject;
LABEL_26:
        ;
      }
      v70 = (__int64 *)*((_QWORD *)this + 9);
      v71 = *v70;
      v78 = v5;
      (*(void (__fastcall **)(__int64 *, __int64, __int64, __int128 *, unsigned int))(v71 + 32))(v70, 1, 1, &v78, v11);
      v1 = v82;
      v2 = (__int64 *)((char *)this + 16);
      v3 = v81;
    }
    if ( v1 && v1 != (_QWORD *)*v2 && (v3 != -1 || v2[1] != -1) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x47u, L"71", 0x54Fu, 0);
    v15 = *v2;
    v16 = v2[1];
    *(_QWORD *)&v77 = *v2;
    *((_QWORD *)&v77 + 1) = v16;
    if ( !FwXmlParser::RecognizeCDATA(this) )
      break;
    v72 = OffsetPtr<unsigned short,unsigned __int64>::operator-(v2, &v77);
    v73 = *((_QWORD *)this + 9);
    v74 = v72 - 12;
    v75 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, int))(*(_QWORD *)v73 + 32LL);
    v76 = OffsetPtr<unsigned short,unsigned __int64>::operator+(&v77, v79, 9);
    v75(v73, 1, 22, v76, v74);
    OffsetPtr<unsigned short,unsigned __int64>::operator=(&v77, v2);
    v3 = *((_QWORD *)&v77 + 1);
    v1 = (_QWORD *)v77;
  }
  while ( 1 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v17 = (_QWORD *)*((_QWORD *)this + 2);
    v18 = *((_QWORD *)this + 3);
    if ( v17 && v18 != -1
      || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0), v18 != -1)
      && v17 )
    {
      v17 = (_QWORD *)(*v17 + 2 * v18);
    }
    v19 = *((_QWORD *)this + 5);
    v20 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v19 != -1 )
    {
      if ( !v20 )
        goto LABEL_183;
      v20 = (_QWORD *)(*v20 + 2 * v19);
    }
    if ( v17 < v20 )
      break;
LABEL_183:
    FwXmlParser::WaitForMore(this, 1);
  }
  v21 = *((_QWORD *)this + 3);
  v22 = (_QWORD *)*v2;
  if ( v21 != -1 && v22 )
    v22 = (_QWORD *)(*v22 + 2 * v21);
  if ( *(_WORD *)v22 == 60 )
  {
    while ( 2 )
    {
      if ( !*v2 || *((_QWORD *)this + 3) == -1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
      v23 = (_QWORD *)*v2;
      v24 = *((_QWORD *)this + 3);
      if ( *v2 && v24 != -1
        || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0), v24 != -1)
        && v23 )
      {
        v23 = (_QWORD *)(*v23 + 2 * v24);
      }
      v25 = *((_QWORD *)this + 5);
      v26 = (_QWORD *)*((_QWORD *)this + 4);
      if ( v25 == -1 )
        goto LABEL_57;
      if ( v26 )
      {
        v26 = (_QWORD *)(*v26 + 2 * v25);
LABEL_57:
        if ( v23 < v26 )
        {
          v27 = *((_QWORD *)this + 3);
          v28 = (_QWORD *)*((_QWORD *)this + 2);
          if ( v27 != -1 && v28 )
            v28 = (_QWORD *)(*v28 + 2 * v27);
          if ( *(_WORD *)v28 != 60 )
            break;
          while ( 2 )
          {
            if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
            v29 = (_QWORD *)*((_QWORD *)this + 2);
            v30 = *((_QWORD *)this + 3);
            if ( !v29 || v30 == -1 )
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
            if ( v30 != -2 && v29 )
              v29 = (_QWORD *)(*v29 + 2 * (v30 + 1));
            v31 = *((_QWORD *)this + 5);
            v32 = (_QWORD *)*((_QWORD *)this + 4);
            if ( v31 != -1 )
            {
              if ( v32 )
              {
                v32 = (_QWORD *)(*v32 + 2 * v31);
                break;
              }
LABEL_185:
              FwXmlParser::WaitForMore(this, 1);
              continue;
            }
            break;
          }
          if ( v29 >= v32 )
            goto LABEL_185;
          v33 = *((_QWORD *)this + 3);
          v34 = *((_QWORD *)this + 2);
          if ( v33 != -1 && v34 )
            v34 = *(_QWORD *)v34 + 2 * v33;
          if ( *(_WORD *)(v34 + 2) != 33 || FwXmlParser::Peek(this, 2) != 45 || FwXmlParser::Peek(this, 3) != 45 )
            break;
          if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x76u, L"118", 0x54Fu, 0);
          v61 = *((_QWORD *)this + 3) + 1LL;
          *((_QWORD *)this + 3) = v61;
          if ( !*((_QWORD *)this + 2) || v61 == -1 )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x76u, L"118", 0x54Fu, 0);
          v62 = *((_QWORD *)this + 3) + 1LL;
          *((_QWORD *)this + 3) = v62;
          if ( !*((_QWORD *)this + 2) || v62 == -1 )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x76u, L"118", 0x54Fu, 0);
          v63 = *((_QWORD *)this + 3) + 1LL;
          *((_QWORD *)this + 3) = v63;
          if ( !*((_QWORD *)this + 2) || v63 == -1 )
LABEL_166:
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x76u, L"118", 0x54Fu, 0);
          while ( 1 )
          {
            ++*((_QWORD *)this + 3);
            if ( FwXmlParser::Peek(this, 0) == 45
              && FwXmlParser::Peek(this, 1) == 45
              && FwXmlParser::Peek(this, 2) == 62 )
            {
              break;
            }
            if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
              goto LABEL_166;
          }
          if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x76u, L"118", 0x54Fu, 0);
          v64 = *((_QWORD *)this + 3) + 1LL;
          *((_QWORD *)this + 3) = v64;
          if ( !*((_QWORD *)this + 2) || v64 == -1 )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x76u, L"118", 0x54Fu, 0);
          v65 = *((_QWORD *)this + 3) + 1LL;
          *((_QWORD *)this + 3) = v65;
          if ( !*((_QWORD *)this + 2) || v65 == -1 )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x76u, L"118", 0x54Fu, 0);
          v66 = *((_QWORD *)this + 3) + 1LL;
          *((_QWORD *)this + 3) = v66;
          if ( v15 && v15 != *((_QWORD *)this + 2) && (v16 != -1 || v66 != -1) )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x47u, L"71", 0x54Fu, 0);
          v5 = *((_OWORD *)this + 1);
          v3 = *((_QWORD *)this + 3);
          v77 = v5;
          v1 = (_QWORD *)v5;
          goto LABEL_3;
        }
      }
      FwXmlParser::WaitForMore(this, 1);
      continue;
    }
  }
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v35 = (_QWORD *)*((_QWORD *)this + 2);
    v36 = *((_QWORD *)this + 3);
    if ( v35 && v36 != -1
      || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0), v36 != -1)
      && v35 )
    {
      v35 = (_QWORD *)(*v35 + 2 * v36);
    }
    v37 = *((_QWORD *)this + 5);
    v38 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v37 != -1 )
    {
      if ( v38 )
      {
        v38 = (_QWORD *)(*v38 + 2 * v37);
        break;
      }
LABEL_186:
      FwXmlParser::WaitForMore(this, 1);
      continue;
    }
    break;
  }
  if ( v35 >= v38 )
    goto LABEL_186;
  v39 = *((_QWORD *)this + 3);
  v40 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v39 != -1 && v40 )
    v40 = (_QWORD *)(*v40 + 2 * v39);
  if ( *(_WORD *)v40 != 60 )
    goto LABEL_124;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v41 = (_QWORD *)*((_QWORD *)this + 2);
    v42 = *((_QWORD *)this + 3);
    if ( !v41 || v42 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    if ( v42 != -2 && v41 )
      v41 = (_QWORD *)(*v41 + 2 * (v42 + 1));
    v43 = *((_QWORD *)this + 5);
    v44 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v43 != -1 )
    {
      if ( v44 )
      {
        v44 = (_QWORD *)(*v44 + 2 * v43);
        break;
      }
LABEL_187:
      FwXmlParser::WaitForMore(this, 1);
      continue;
    }
    break;
  }
  if ( v41 >= v44 )
    goto LABEL_187;
  v45 = *((_QWORD *)this + 3);
  if ( v45 == -1 )
  {
    v47 = *((_QWORD *)this + 2);
  }
  else
  {
    v46 = (_QWORD *)*((_QWORD *)this + 2);
    if ( v46 )
      v47 = *v46 + 2 * v45;
    else
      v47 = 0;
  }
  v48 = *(_WORD *)(v47 + 2);
  if ( (unsigned __int16)(v48 - 97) <= 0x19u
    || v48 > 0x40u
    && (unsigned __int16)(v48 - 91) > 3u
    && (unsigned __int16)(v48 - 96) > 0x5Fu
    && v48 != 215
    && v48 != 247
    && (unsigned __int16)(v48 - 768) > 0x6Fu
    && v48 != 894
    && (unsigned __int16)(v48 - 8206) > 0x61u
    && (unsigned __int16)(v48 - 8592) > 0xA6Fu
    && (unsigned __int16)(v48 - 12272) > 0x10u
    && (unsigned __int16)(v48 + 10240) > 0x20FFu
    && (unsigned __int16)(v48 + 560) > 0x1Fu
    && v48 < 0xFFFEu
    && (unsigned __int16)(v48 - 0x2000) > 0xBu )
  {
    return;
  }
LABEL_124:
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v49 = (_QWORD *)*((_QWORD *)this + 2);
    v50 = *((_QWORD *)this + 3);
    if ( v49 && v50 != -1
      || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0), v50 != -1) )
    {
      if ( v49 )
        v49 = (_QWORD *)(*v49 + 2 * v50);
    }
    v51 = *((_QWORD *)this + 5);
    v52 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v51 != -1 )
    {
      if ( v52 )
      {
        v52 = (_QWORD *)(*v52 + 2 * v51);
        break;
      }
LABEL_188:
      FwXmlParser::WaitForMore(this, 1);
      continue;
    }
    break;
  }
  if ( v49 >= v52 )
    goto LABEL_188;
  v53 = *((_QWORD *)this + 3);
  v54 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v53 != -1 && v54 )
    v54 = (_QWORD *)(*v54 + 2 * v53);
  if ( *(_WORD *)v54 != 60 )
  {
LABEL_153:
    pExceptionObject = 7;
    throw (int *)&pExceptionObject;
  }
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v55 = (_QWORD *)*((_QWORD *)this + 2);
    v56 = *((_QWORD *)this + 3);
    if ( !v55 || v56 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    if ( v56 != -2 && v55 )
      v55 = (_QWORD *)(*v55 + 2 * (v56 + 1));
    v57 = *((_QWORD *)this + 5);
    v58 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v57 != -1 )
    {
      if ( v58 )
      {
        v58 = (_QWORD *)(*v58 + 2 * v57);
        break;
      }
LABEL_189:
      FwXmlParser::WaitForMore(this, 1);
      continue;
    }
    break;
  }
  if ( v55 >= v58 )
    goto LABEL_189;
  v59 = *((_QWORD *)this + 3);
  v60 = *((_QWORD *)this + 2);
  if ( v59 != -1 && v60 )
    v60 = *(_QWORD *)v60 + 2 * v59;
  if ( *(_WORD *)(v60 + 2) != 47 )
    goto LABEL_153;
}

```

## disassembly

```asm
0x180002e50  mov     [rsp+arg_18], rbx
0x180002e55  push    rbp
0x180002e56  push    rsi
0x180002e57  push    rdi
0x180002e58  push    r12
0x180002e5a  push    r13
0x180002e5c  push    r14
0x180002e5e  push    r15
0x180002e60  sub     rsp, 70h
0x180002e64  mov     r15, [rcx+10h]
0x180002e68  lea     r12, [rcx+10h]
0x180002e6c  mov     r14, [r12+8]
0x180002e71  mov     rbp, rcx
0x180002e74  mov     qword ptr [rsp+0A8h+var_78], r15
0x180002e79  mov     qword ptr [rsp+0A8h+var_78+8], r14
0x180002e7e  movaps  [rsp+0A8h+var_48], xmm6
0x180002e83  movaps  xmm6, [rsp+0A8h+var_78]
0x180002e88  mov     [rsp+0A8h+arg_10], r15
0x180002e90  mov     [rsp+0A8h+arg_8], r14
0x180002e98  mov     rax, [r12]
0x180002e9c  cmp     [rbp+20h], rax
0x180002ea0  jnz     loc_180003910
0x180002ea6  cmp     qword ptr [rbp+28h], 0FFFFFFFFFFFFFFFFh
0x180002eab  jz      loc_180003910
0x180002eb1  mov     rdx, [rbp+18h]
0x180002eb5  mov     rcx, [rbp+28h]
0x180002eb9  sub     rcx, rdx
0x180002ebc  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180002ec0  jz      loc_180002FF8
0x180002ec6  mov     rax, [r12]
0x180002eca  test    rax, rax
0x180002ecd  jz      loc_180003001
0x180002ed3  mov     rax, [rax]
0x180002ed6  lea     rbx, [rax+rdx*2]
0x180002eda  nop     word ptr [rax+rax+00h]
0x180002ee0  test    rcx, rcx
0x180002ee3  jz      loc_18000393C
0x180002ee9  cmp     word ptr [rbx], 3Ch ; '<'
0x180002eed  jz      short loc_180002EF8
0x180002eef  add     rbx, 2
0x180002ef3  dec     rcx
0x180002ef6  jmp     short loc_180002EE0
0x180002ef8  test    rbx, rbx
0x180002efb  jz      loc_18000393C
0x180002f01  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180002f05  jz      loc_180002FB8
0x180002f0b  mov     rax, [r12]
0x180002f0f  test    rax, rax
0x180002f12  jz      loc_18000394B
0x180002f18  mov     rax, [rax]
0x180002f1b  lea     rdi, [rax+rdx*2]
0x180002f1f  mov     rcx, [rbp+18h]
0x180002f23  sub     rbx, rdi
0x180002f26  sar     rbx, 1
0x180002f29  add     rcx, rbx
0x180002f2c  mov     [rbp+18h], rcx
0x180002f30  cmp     [r12], r15
0x180002f34  jnz     loc_180003952
0x180002f3a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002f3e  jz      loc_180003952
0x180002f44  mov     esi, [rbp+18h]
0x180002f47  sub     esi, r14d
0x180002f4a  jz      loc_180003008
0x180002f50  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180002f54  jz      loc_180002FE8
0x180002f5a  test    r15, r15
0x180002f5d  jz      loc_180002FF0
0x180002f63  mov     rax, [r15]
0x180002f66  lea     r14, [rax+r14*2]
0x180002f6a  xor     ebx, ebx
0x180002f6c  nop     dword ptr [rax+00h]
0x180002f70  cmp     ebx, esi
0x180002f72  jnb     loc_1800039FF
0x180002f78  movsxd  rax, ebx
0x180002f7b  lea     rdi, [r14+rax*2]
0x180002f7f  movzx   eax, word ptr [r14+rax*2]
0x180002f84  cmp     ax, 3Ch ; '<'
0x180002f88  jz      short loc_180002F98
0x180002f8a  cmp     ax, 26h ; '&'
0x180002f8e  jz      loc_18000397E
0x180002f94  inc     ebx
0x180002f96  jmp     short loc_180002F70
0x180002f98  lea     rdx, _TI1H; pThrowInfo
0x180002f9f  mov     [rsp+0A8h+pExceptionObject], 7
0x180002faa  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180002fb2  call    _CxxThrowException_0
0x180002fb8  mov     rdi, [r12]
0x180002fbc  mov     r9d, 54Fh; unsigned int
0x180002fc2  mov     [rsp+0A8h+var_88], 0; struct IRequestContext *
0x180002fcb  lea     r8, a124; "124"
0x180002fd2  mov     edx, 7Ch ; '|'; unsigned int
0x180002fd7  lea     rcx, aOnecoreAdminWm_23; "onecore\\admin\\wmi\\wmx\\fwxml\\Offset"...
0x180002fde  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180002fe3  jmp     loc_180002F1F
0x180002fe8  mov     r14, r15
0x180002feb  jmp     loc_180002F6A
0x180002ff0  xor     r14d, r14d
0x180002ff3  jmp     loc_180002F6A
0x180002ff8  mov     rbx, [r12]
0x180002ffc  jmp     loc_180002EE0
0x180003001  xor     ebx, ebx
0x180003003  jmp     loc_180002EE0
0x180003008  test    r15, r15
0x18000300b  jnz     loc_180003406
0x180003011  mov     rsi, [r12]
0x180003015  mov     rcx, rbp; this
0x180003018  mov     r14, [r12+8]
0x18000301d  mov     qword ptr [rsp+0A8h+var_78], rsi
0x180003022  mov     qword ptr [rsp+0A8h+var_78+8], r14
0x180003027  call    ?RecognizeCDATA@FwXmlParser@@QEAA_NXZ; FwXmlParser::RecognizeCDATA(void)
0x18000302c  test    al, al
0x18000302e  jnz     loc_180003A3F
0x180003034  cmp     qword ptr [rbp+10h], 0
0x180003039  jz      loc_180003AA8
0x18000303f  cmp     qword ptr [rbp+18h], 0FFFFFFFFFFFFFFFFh
0x180003044  jz      loc_180003AA8
0x18000304a  mov     rbx, [rbp+10h]
0x18000304e  mov     rdi, [rbp+18h]
0x180003052  test    rbx, rbx
0x180003055  jz      loc_180003838
0x18000305b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000305f  jz      loc_180003838
0x180003065  mov     rax, [rbx]
0x180003068  lea     rbx, [rax+rdi*2]
0x18000306c  mov     rcx, [rbp+28h]
0x180003070  mov     rax, [rbp+20h]
0x180003074  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003078  jz      short loc_18000308A
0x18000307a  test    rax, rax
0x18000307d  jz      loc_1800036EE
0x180003083  mov     rax, [rax]
0x180003086  lea     rax, [rax+rcx*2]
0x18000308a  cmp     rbx, rax
0x18000308d  jnb     loc_1800036EE
0x180003093  mov     rcx, [rbp+18h]
0x180003097  mov     rax, [r12]
0x18000309b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000309f  jz      short loc_1800030B1
0x1800030a1  test    rax, rax
0x1800030a4  jz      loc_18000359B
0x1800030aa  mov     rax, [rax]
0x1800030ad  lea     rax, [rax+rcx*2]
0x1800030b1  cmp     word ptr [rax], 3Ch ; '<'
0x1800030b5  jnz     loc_1800031DD
0x1800030bb  cmp     qword ptr [r12], 0
0x1800030c0  jz      loc_180003AD4
0x1800030c6  cmp     qword ptr [rbp+18h], 0FFFFFFFFFFFFFFFFh
0x1800030cb  jz      loc_180003AD4
0x1800030d1  mov     rbx, [r12]
0x1800030d5  mov     rdi, [rbp+18h]
0x1800030d9  test    rbx, rbx
0x1800030dc  jz      loc_18000386E
0x1800030e2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800030e6  jz      loc_18000386E
0x1800030ec  mov     rax, [rbx]
0x1800030ef  lea     rbx, [rax+rdi*2]
0x1800030f3  mov     rcx, [rbp+28h]
0x1800030f7  mov     rax, [rbp+20h]
0x1800030fb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800030ff  jz      short loc_180003111
0x180003101  test    rax, rax
0x180003104  jz      loc_1800036FD
0x18000310a  mov     rax, [rax]
0x18000310d  lea     rax, [rax+rcx*2]
0x180003111  cmp     rbx, rax
0x180003114  jnb     loc_1800036FD
0x18000311a  mov     rcx, [rbp+18h]
0x18000311e  mov     rax, [rbp+10h]
0x180003122  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003126  jz      short loc_180003138
0x180003128  test    rax, rax
0x18000312b  jz      loc_1800035A0
0x180003131  mov     rax, [rax]
0x180003134  lea     rax, [rax+rcx*2]
0x180003138  cmp     word ptr [rax], 3Ch ; '<'
0x18000313c  jnz     loc_1800031DD
0x180003142  cmp     qword ptr [rbp+10h], 0
0x180003147  jz      loc_180003B00
0x18000314d  cmp     qword ptr [rbp+18h], 0FFFFFFFFFFFFFFFFh
0x180003152  jz      loc_180003B00
0x180003158  mov     rbx, [rbp+10h]
0x18000315c  mov     rdi, [rbp+18h]
0x180003160  test    rbx, rbx
0x180003163  jz      loc_180003B2C
0x180003169  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000316d  jz      loc_180003B2C
0x180003173  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180003177  jz      short loc_18000318D
0x180003179  test    rbx, rbx
0x18000317c  jz      loc_1800036B6
0x180003182  mov     rax, [rbx]
0x180003185  lea     rbx, [rdi+1]
0x180003189  lea     rbx, [rax+rbx*2]
0x18000318d  mov     rcx, [rbp+28h]
0x180003191  mov     rax, [rbp+20h]
0x180003195  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003199  jz      short loc_1800031AB
0x18000319b  test    rax, rax
0x18000319e  jz      loc_18000370C
0x1800031a4  mov     rax, [rax]
0x1800031a7  lea     rax, [rax+rcx*2]
0x1800031ab  cmp     rbx, rax
0x1800031ae  jnb     loc_18000370C
0x1800031b4  mov     rcx, [rbp+18h]
0x1800031b8  mov     rax, [rbp+10h]
0x1800031bc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800031c0  jz      short loc_1800031D2
0x1800031c2  test    rax, rax
0x1800031c5  jz      loc_1800036BB
0x1800031cb  mov     rax, [rax]
0x1800031ce  lea     rax, [rax+rcx*2]
0x1800031d2  cmp     word ptr [rax+2], 21h ; '!'
0x1800031d7  jz      loc_1800035A5
0x1800031dd  cmp     qword ptr [rbp+10h], 0
0x1800031e2  jz      loc_180003C60
0x1800031e8  cmp     qword ptr [rbp+18h], 0FFFFFFFFFFFFFFFFh
0x1800031ed  jz      loc_180003C60
0x1800031f3  mov     rbx, [rbp+10h]
0x1800031f7  mov     rdi, [rbp+18h]
0x1800031fb  test    rbx, rbx
0x1800031fe  jz      loc_1800038A4
0x180003204  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180003208  jz      loc_1800038A4
0x18000320e  mov     rax, [rbx]
0x180003211  lea     rbx, [rax+rdi*2]
0x180003215  mov     rcx, [rbp+28h]
0x180003219  mov     rax, [rbp+20h]
0x18000321d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003221  jz      short loc_180003233
0x180003223  test    rax, rax
0x180003226  jz      loc_18000371B
0x18000322c  mov     rax, [rax]
0x18000322f  lea     rax, [rax+rcx*2]
0x180003233  cmp     rbx, rax
0x180003236  jnb     loc_18000371B
0x18000323c  mov     rcx, [rbp+18h]
0x180003240  mov     rax, [rbp+10h]
0x180003244  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003248  jz      short loc_18000325A
0x18000324a  test    rax, rax
0x18000324d  jz      loc_1800036C9
0x180003253  mov     rax, [rax]
0x180003256  lea     rax, [rax+rcx*2]
0x18000325a  cmp     word ptr [rax], 3Ch ; '<'
0x18000325e  jnz     loc_180003450
0x180003264  cmp     qword ptr [rbp+10h], 0
0x180003269  jz      loc_180003C8C
0x18000326f  cmp     qword ptr [rbp+18h], 0FFFFFFFFFFFFFFFFh
0x180003274  jz      loc_180003C8C
0x18000327a  mov     rbx, [rbp+10h]
0x18000327e  mov     rdi, [rbp+18h]
0x180003282  test    rbx, rbx
0x180003285  jz      loc_180003CB8
0x18000328b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000328f  jz      loc_180003CB8
0x180003295  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180003299  jz      short loc_1800032AF
0x18000329b  test    rbx, rbx
0x18000329e  jz      loc_1800036CE
0x1800032a4  mov     rax, [rbx]
0x1800032a7  lea     rbx, [rdi+1]
0x1800032ab  lea     rbx, [rax+rbx*2]
0x1800032af  mov     rcx, [rbp+28h]
0x1800032b3  mov     rax, [rbp+20h]
0x1800032b7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800032bb  jz      short loc_1800032CD
0x1800032bd  test    rax, rax
0x1800032c0  jz      loc_18000372A
0x1800032c6  mov     rax, [rax]
0x1800032c9  lea     rax, [rax+rcx*2]
0x1800032cd  cmp     rbx, rax
0x1800032d0  jnb     loc_18000372A
0x1800032d6  mov     rcx, [rbp+18h]
0x1800032da  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800032de  jz      loc_1800036C0
0x1800032e4  mov     rax, [rbp+10h]
0x1800032e8  test    rax, rax
0x1800032eb  jz      loc_1800036D3
0x1800032f1  mov     rax, [rax]
0x1800032f4  lea     rcx, [rax+rcx*2]
0x1800032f8  movzx   ecx, word ptr [rcx+2]
0x1800032fc  lea     eax, [rcx-61h]
0x1800032ff  cmp     ax, 19h
0x180003303  jbe     loc_1800033E9
0x180003309  cmp     cx, 40h ; '@'
0x18000330d  jbe     loc_180003450
0x180003313  lea     eax, [rcx-5Bh]
0x180003316  cmp     ax, 3
0x18000331a  jbe     loc_180003450
0x180003320  lea     eax, [rcx-60h]
0x180003323  cmp     ax, 5Fh ; '_'
0x180003327  jbe     loc_180003450
0x18000332d  mov     eax, 0D7h
0x180003332  cmp     cx, ax
0x180003335  jz      loc_180003450
0x18000333b  mov     eax, 0F7h
0x180003340  cmp     cx, ax
0x180003343  jz      loc_180003450
0x180003349  mov     edx, 300h
0x18000334e  movzx   eax, cx
  ... truncated ...
```
