# FwXmlParser::RecognizeCDATA(void)

- ea: `0x180004d30`
- end: `0x180005be0`
- name: `?RecognizeCDATA@FwXmlParser@@QEAA_NXZ`
- size: `3760`
- prototype: `char __fastcall(FwXmlParser *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180002e50`

## callees

- `0x18000143c`
- `0x180004d30`
- `0x180005bf0`
- `0x180005c70`
- `0x180005d10`
- `0x18003c640`
- `0x18005eb30`
- `0x1801c2010`

## string_xrefs

- `0x1800057b6`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800057eb`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005813`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000583b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005863`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000588b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800058b3`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800058db`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005903`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000592b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005953`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000597b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800059a3`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800059cb`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800059f3`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005a1b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005a43`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005a6b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005a93`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005abb`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005ae3`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005b1a`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005b42`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005b6a`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180005bcf`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall FwXmlParser::RecognizeCDATA(FwXmlParser *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v12; // rdi
  __int64 v13; // rsi
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  _QWORD *v21; // rdi
  __int64 v22; // rsi
  __int64 v23; // rsi
  __int64 v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  _QWORD *v31; // rdi
  __int64 v32; // rsi
  __int64 v33; // rsi
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  _QWORD *v41; // rdi
  __int64 v42; // rsi
  __int64 v43; // rsi
  __int64 v44; // rcx
  _QWORD *v45; // rax
  __int64 v46; // rcx
  unsigned int v47; // eax
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  _QWORD *v51; // rdi
  __int64 v52; // rsi
  __int64 v53; // rsi
  __int64 v54; // rcx
  _QWORD *v55; // rax
  __int64 v56; // rcx
  unsigned int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  _QWORD *v61; // rdi
  __int64 v62; // rsi
  __int64 v63; // rsi
  __int64 v64; // rcx
  _QWORD *v65; // rax
  __int64 v66; // rcx
  unsigned int v67; // eax
  __int64 v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rax
  _QWORD *v71; // rdi
  __int64 v72; // rsi
  __int64 v73; // rsi
  __int64 v74; // rcx
  _QWORD *v75; // rax
  __int64 v76; // rcx
  unsigned int v77; // eax
  __int64 v78; // rax
  __int64 v79; // rcx
  __int64 v80; // rax
  _QWORD *v81; // rdi
  __int64 v82; // rsi
  __int64 v83; // rsi
  __int64 v84; // rcx
  _QWORD *v85; // rax
  __int64 v86; // rcx
  unsigned int v87; // eax
  __int64 v88; // rax
  __int64 v89; // rcx
  __int64 v90; // rax
  _QWORD *v91; // rdi
  __int64 v92; // rsi
  __int64 v93; // rsi
  __int64 v94; // rcx
  _QWORD *v95; // rax
  _QWORD *v96; // rdi
  __int64 v97; // rsi
  __int64 v98; // rsi
  __int64 v99; // rcx
  _QWORD *v100; // rax
  __int64 v101; // r9
  _QWORD *v102; // r8
  __int64 v103; // rax
  _WORD *v104; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rdx
  _BYTE v108[56]; // [rsp+30h] [rbp-38h] BYREF

  while ( 1 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v2 = (_QWORD *)*((_QWORD *)this + 2);
    v3 = *((_QWORD *)this + 3);
    if ( v2 )
    {
      if ( v3 == -1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
      else
        v2 = (_QWORD *)(*v2 + 2 * v3);
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
      if ( v3 != -1 )
        v2 = 0;
    }
    v4 = *((_QWORD *)this + 5);
    v5 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v4 == -1 )
      break;
    if ( v5 )
    {
      v5 = (_QWORD *)(*v5 + 2 * v4);
      break;
    }
LABEL_10:
    v6 = *((_QWORD *)this + 7);
    if ( !v6 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6) )
      return 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
    v8 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v7);
    OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v8);
  }
  if ( v2 >= v5 )
    goto LABEL_10;
  v9 = *((_QWORD *)this + 3);
  v10 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v9 != -1 )
  {
    if ( v10 )
      v10 = (_QWORD *)(*v10 + 2 * v9);
    else
      v10 = 0;
  }
  if ( *(_WORD *)v10 != 60 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v12 = (_QWORD *)*((_QWORD *)this + 2);
    v13 = *((_QWORD *)this + 3);
    if ( !v12 || v13 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    if ( v13 != -2 )
    {
      if ( v12 )
        v12 = (_QWORD *)(*v12 + 2 * (v13 + 1));
      else
        v12 = 0;
    }
    v14 = *((_QWORD *)this + 5);
    v15 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v14 != -1 )
    {
      if ( v15 )
      {
        v15 = (_QWORD *)(*v15 + 2 * v14);
        break;
      }
LABEL_29:
      v16 = *((_QWORD *)this + 7);
      if ( !v16 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16) )
        return 0;
      v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
      v18 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v17);
      OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v18);
      continue;
    }
    break;
  }
  if ( v12 >= v15 )
    goto LABEL_29;
  v19 = *((_QWORD *)this + 3);
  v20 = *((_QWORD *)this + 2);
  if ( v19 != -1 )
  {
    if ( v20 )
      v20 = *(_QWORD *)v20 + 2 * v19;
    else
      v20 = 0;
  }
  if ( *(_WORD *)(v20 + 2) != 33 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v21 = (_QWORD *)*((_QWORD *)this + 2);
    v22 = *((_QWORD *)this + 3);
    if ( !v21 || v22 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    v23 = v22 + 2;
    if ( v23 != -1 )
    {
      if ( v21 )
        v21 = (_QWORD *)(*v21 + 2 * v23);
      else
        v21 = 0;
    }
    v24 = *((_QWORD *)this + 5);
    v25 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v24 != -1 )
    {
      if ( v25 )
      {
        v25 = (_QWORD *)(*v25 + 2 * v24);
        break;
      }
LABEL_48:
      v26 = *((_QWORD *)this + 7);
      if ( !v26 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26) )
        return 0;
      v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
      v28 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v27);
      OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v28);
      continue;
    }
    break;
  }
  if ( v21 >= v25 )
    goto LABEL_48;
  v29 = *((_QWORD *)this + 3);
  v30 = *((_QWORD *)this + 2);
  if ( v29 != -1 )
  {
    if ( v30 )
      v30 = *(_QWORD *)v30 + 2 * v29;
    else
      v30 = 0;
  }
  if ( *(_WORD *)(v30 + 4) != 91 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v31 = (_QWORD *)*((_QWORD *)this + 2);
    v32 = *((_QWORD *)this + 3);
    if ( !v31 || v32 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    v33 = v32 + 3;
    if ( v33 != -1 )
    {
      if ( v31 )
        v31 = (_QWORD *)(*v31 + 2 * v33);
      else
        v31 = 0;
    }
    v34 = *((_QWORD *)this + 5);
    v35 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v34 != -1 )
    {
      if ( v35 )
      {
        v35 = (_QWORD *)(*v35 + 2 * v34);
        break;
      }
LABEL_67:
      v36 = *((_QWORD *)this + 7);
      if ( !v36 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36) )
        return 0;
      v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
      v38 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v37);
      OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v38);
      continue;
    }
    break;
  }
  if ( v31 >= v35 )
    goto LABEL_67;
  v39 = *((_QWORD *)this + 3);
  v40 = *((_QWORD *)this + 2);
  if ( v39 != -1 )
  {
    if ( v40 )
      v40 = *(_QWORD *)v40 + 2 * v39;
    else
      v40 = 0;
  }
  if ( *(_WORD *)(v40 + 6) != 67 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v41 = (_QWORD *)*((_QWORD *)this + 2);
    v42 = *((_QWORD *)this + 3);
    if ( !v41 || v42 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    v43 = v42 + 4;
    if ( v43 != -1 )
    {
      if ( v41 )
        v41 = (_QWORD *)(*v41 + 2 * v43);
      else
        v41 = 0;
    }
    v44 = *((_QWORD *)this + 5);
    v45 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v44 != -1 )
    {
      if ( v45 )
      {
        v45 = (_QWORD *)(*v45 + 2 * v44);
        break;
      }
LABEL_86:
      v46 = *((_QWORD *)this + 7);
      if ( !v46 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46) )
        return 0;
      v47 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
      v48 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v47);
      OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v48);
      continue;
    }
    break;
  }
  if ( v41 >= v45 )
    goto LABEL_86;
  v49 = *((_QWORD *)this + 3);
  v50 = *((_QWORD *)this + 2);
  if ( v49 != -1 )
  {
    if ( v50 )
      v50 = *(_QWORD *)v50 + 2 * v49;
    else
      v50 = 0;
  }
  if ( *(_WORD *)(v50 + 8) != 68 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v51 = (_QWORD *)*((_QWORD *)this + 2);
    v52 = *((_QWORD *)this + 3);
    if ( !v51 || v52 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    v53 = v52 + 5;
    if ( v53 != -1 )
    {
      if ( v51 )
        v51 = (_QWORD *)(*v51 + 2 * v53);
      else
        v51 = 0;
    }
    v54 = *((_QWORD *)this + 5);
    v55 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v54 != -1 )
    {
      if ( v55 )
      {
        v55 = (_QWORD *)(*v55 + 2 * v54);
        break;
      }
LABEL_105:
      v56 = *((_QWORD *)this + 7);
      if ( !v56 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56) )
        return 0;
      v57 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
      v58 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v57);
      OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v58);
      continue;
    }
    break;
  }
  if ( v51 >= v55 )
    goto LABEL_105;
  v59 = *((_QWORD *)this + 3);
  v60 = *((_QWORD *)this + 2);
  if ( v59 != -1 )
  {
    if ( v60 )
      v60 = *(_QWORD *)v60 + 2 * v59;
    else
      v60 = 0;
  }
  if ( *(_WORD *)(v60 + 10) != 65 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v61 = (_QWORD *)*((_QWORD *)this + 2);
    v62 = *((_QWORD *)this + 3);
    if ( !v61 || v62 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    v63 = v62 + 6;
    if ( v63 != -1 )
    {
      if ( v61 )
        v61 = (_QWORD *)(*v61 + 2 * v63);
      else
        v61 = 0;
    }
    v64 = *((_QWORD *)this + 5);
    v65 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v64 != -1 )
    {
      if ( v65 )
      {
        v65 = (_QWORD *)(*v65 + 2 * v64);
        break;
      }
LABEL_124:
      v66 = *((_QWORD *)this + 7);
      if ( !v66 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66) )
        return 0;
      v67 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
      v68 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v67);
      OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v68);
      continue;
    }
    break;
  }
  if ( v61 >= v65 )
    goto LABEL_124;
  v69 = *((_QWORD *)this + 3);
  v70 = *((_QWORD *)this + 2);
  if ( v69 != -1 )
  {
    if ( v70 )
      v70 = *(_QWORD *)v70 + 2 * v69;
    else
      v70 = 0;
  }
  if ( *(_WORD *)(v70 + 12) != 84 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v71 = (_QWORD *)*((_QWORD *)this + 2);
    v72 = *((_QWORD *)this + 3);
    if ( !v71 || v72 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    v73 = v72 + 7;
    if ( v73 != -1 )
    {
      if ( v71 )
        v71 = (_QWORD *)(*v71 + 2 * v73);
      else
        v71 = 0;
    }
    v74 = *((_QWORD *)this + 5);
    v75 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v74 != -1 )
    {
      if ( v75 )
      {
        v75 = (_QWORD *)(*v75 + 2 * v74);
        break;
      }
LABEL_143:
      v76 = *((_QWORD *)this + 7);
      if ( !v76 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76) )
        return 0;
      v77 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
      v78 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v77);
      OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v78);
      continue;
    }
    break;
  }
  if ( v71 >= v75 )
    goto LABEL_143;
  v79 = *((_QWORD *)this + 3);
  v80 = *((_QWORD *)this + 2);
  if ( v79 != -1 )
  {
    if ( v80 )
      v80 = *(_QWORD *)v80 + 2 * v79;
    else
      v80 = 0;
  }
  if ( *(_WORD *)(v80 + 14) != 65 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v81 = (_QWORD *)*((_QWORD *)this + 2);
    v82 = *((_QWORD *)this + 3);
    if ( !v81 || v82 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    v83 = v82 + 8;
    if ( v83 != -1 )
    {
      if ( v81 )
        v81 = (_QWORD *)(*v81 + 2 * v83);
      else
        v81 = 0;
    }
    v84 = *((_QWORD *)this + 5);
    v85 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v84 != -1 )
    {
      if ( v85 )
      {
        v85 = (_QWORD *)(*v85 + 2 * v84);
        break;
      }
LABEL_162:
      v86 = *((_QWORD *)this + 7);
      if ( !v86 || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86) )
        return 0;
      v87 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
      v88 = OffsetPtr<unsigned short,unsigned __int64>::operator+(this, v108, v87);
      OffsetPtr<unsigned short,unsigned __int64>::operator=((char *)this + 32, v88);
      continue;
    }
    break;
  }
  if ( v81 >= v85 )
    goto LABEL_162;
  v89 = *((_QWORD *)this + 3);
  v90 = *((_QWORD *)this + 2);
  if ( v89 != -1 )
  {
    if ( v90 )
      v90 = *(_QWORD *)v90 + 2 * v89;
    else
      v90 = 0;
  }
  if ( *(_WORD *)(v90 + 16) != 91 )
    return 0;
  while ( 2 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
    v91 = (_QWORD *)*((_QWORD *)this + 2);
    v92 = *((_QWORD *)this + 3);
    if ( !v91 || v92 == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
    v93 = v92 + 9;
    if ( v93 != -1 )
    {
      if ( v91 )
        v91 = (_QWORD *)(*v91 + 2 * v93);
      else
        v91 = 0;
    }
    v94 = *((_QWORD *)this + 5);
    v95 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v94 != -1 )
    {
      if ( v95 )
      {
        v95 = (_QWORD *)(*v95 + 2 * v94);
        break;
      }
LABEL_255:
      FwXmlParser::WaitForMore(this, 1);
      continue;
    }
    break;
  }
  if ( v91 >= v95 )
    goto LABEL_255;
  if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
  *((_QWORD *)this + 3) += 9LL;
  while ( 2 )
  {
    while ( 2 )
    {
      if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x83u, L"131", 0x54Fu, 0);
      v96 = (_QWORD *)*((_QWORD *)this + 2);
      v97 = *((_QWORD *)this + 3);
      if ( !v96 || v97 == -1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
      v98 = v97 + 3;
      if ( v98 != -1 )
      {
        if ( v96 )
          v96 = (_QWORD *)(*v96 + 2 * v98);
        else
          v96 = 0;
      }
      v99 = *((_QWORD *)this + 5);
      v100 = (_QWORD *)*((_QWORD *)this + 4);
      if ( v99 != -1 )
      {
        if ( v100 )
        {
          v100 = (_QWORD *)(*v100 + 2 * v99);
          break;
        }
LABEL_259:
        FwXmlParser::WaitForMore(this, 1);
        continue;
      }
      break;
    }
    if ( v96 >= v100 )
      goto LABEL_259;
    v101 = *((_QWORD *)this + 3);
    if ( v101 == -1 )
    {
      v103 = *((_QWORD *)this + 2);
      v102 = (_QWORD *)v103;
    }
    else
    {
      v102 = (_QWORD *)*((_QWORD *)this + 2);
      if ( v102 )
      {
        v103 = *v102 + 2 * v101;
      }
      else
      {
        v103 = 0;
        v102 = 0;
      }
    }
    if ( *(_WORD *)(v103 + 4) != 93
      && *(_WORD *)(OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *((char *)this + 16) + 4) != 62 )
    {
      v107 = 3;
LABEL_263:
      OffsetPtr<unsigned short,unsigned __int64>::operator+=((char *)this + 16, v107);
      continue;
    }
    break;
  }
  if ( v101 == -1 )
  {
    v104 = v102;
  }
  else if ( v102 )
  {
    v104 = (_WORD *)(*v102 + 2 * v101);
  }
  else
  {
    v104 = 0;
    v102 = 0;
  }
  if ( *v104 != 93
    || (v101 == -1 ? (v105 = (__int64)v102) : !v102 ? (v105 = 0) : (v105 = *v102 + 2 * v101),
        *(_WORD *)(v105 + 2) != 93
     || (v101 == -1 ? (v106 = (__int64)v102) : !v102 ? (v106 = 0) : (v106 = *v102 + 2 * v101), *(_WORD *)(v106 + 4) != 62)) )
  {
    v107 = 1;
    goto LABEL_263;
  }
  if ( !v102 || *((_QWORD *)this + 3) == -1 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 0x7Cu, L"124", 0x54Fu, 0);
  *((_QWORD *)this + 3) += 3LL;
  return 1;
}

```

## disassembly

```asm
0x180004d30  push    rbx
0x180004d32  push    rbp
0x180004d33  push    rsi
0x180004d34  push    rdi
0x180004d35  push    r14
0x180004d37  sub     rsp, 40h
0x180004d3b  mov     rbx, rcx
0x180004d3e  xor     ebp, ebp
0x180004d40  cmp     [rbx+10h], rbp
0x180004d44  jz      loc_1800057D4
0x180004d4a  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x180004d4f  jz      loc_1800057D4
0x180004d55  mov     rdi, [rbx+10h]
0x180004d59  mov     rsi, [rbx+18h]
0x180004d5d  test    rdi, rdi
0x180004d60  jz      loc_18000579F
0x180004d66  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180004d6a  jz      loc_1800057FC
0x180004d70  mov     rax, [rdi]
0x180004d73  lea     rdi, [rax+rsi*2]
0x180004d77  mov     rcx, [rbx+28h]
0x180004d7b  mov     rax, [rbx+20h]
0x180004d7f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004d83  jz      short loc_180004D91
0x180004d85  test    rax, rax
0x180004d88  jz      short loc_180004D96
0x180004d8a  mov     rax, [rax]
0x180004d8d  lea     rax, [rax+rcx*2]
0x180004d91  cmp     rdi, rax
0x180004d94  jb      short loc_180004DE0
0x180004d96  mov     rcx, [rbx+38h]
0x180004d9a  test    rcx, rcx
0x180004d9d  jz      short loc_180004E04
0x180004d9f  mov     rax, [rcx]
0x180004da2  mov     rax, [rax+10h]
0x180004da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dab  test    al, al
0x180004dad  jz      short loc_180004E04
0x180004daf  mov     rcx, [rbx+38h]
0x180004db3  mov     rax, [rcx]
0x180004db6  mov     rax, [rax+8]
0x180004dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dbf  mov     r8d, eax
0x180004dc2  lea     rdx, [rsp+68h+var_38]
0x180004dc7  mov     rcx, rbx
0x180004dca  call    ??H?$OffsetPtr@G_K@@QEAA?AV0@_K@Z; OffsetPtr<ushort,unsigned __int64>::operator+(unsigned __int64)
0x180004dcf  mov     rdx, rax
0x180004dd2  lea     rcx, [rbx+20h]
0x180004dd6  call    ??4?$OffsetPtr@G_K@@QEAAAEAV0@AEBV0@@Z; OffsetPtr<ushort,unsigned __int64>::operator=(OffsetPtr<ushort,unsigned __int64> const &)
0x180004ddb  jmp     loc_180004D40
0x180004de0  mov     rcx, [rbx+18h]
0x180004de4  mov     rax, [rbx+10h]
0x180004de8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004dec  jz      short loc_180004DFE
0x180004dee  test    rax, rax
0x180004df1  jz      loc_180005703
0x180004df7  mov     rax, [rax]
0x180004dfa  lea     rax, [rax+rcx*2]
0x180004dfe  cmp     word ptr [rax], 3Ch ; '<'
0x180004e02  jz      short loc_180004E11
0x180004e04  xor     al, al
0x180004e06  add     rsp, 40h
0x180004e0a  pop     r14
0x180004e0c  pop     rdi
0x180004e0d  pop     rsi
0x180004e0e  pop     rbp
0x180004e0f  pop     rbx
0x180004e10  retn
0x180004e11  cmp     [rbx+10h], rbp
0x180004e15  jz      loc_180005824
0x180004e1b  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x180004e20  jz      loc_180005824
0x180004e26  mov     rdi, [rbx+10h]
0x180004e2a  mov     rsi, [rbx+18h]
0x180004e2e  test    rdi, rdi
0x180004e31  jz      loc_18000584C
0x180004e37  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180004e3b  jz      loc_18000584C
0x180004e41  cmp     rsi, 0FFFFFFFFFFFFFFFEh
0x180004e45  jz      short loc_180004E57
0x180004e47  test    rdi, rdi
0x180004e4a  jz      short loc_180004EC4
0x180004e4c  mov     rax, [rdi]
0x180004e4f  lea     rdi, [rsi+1]
0x180004e53  lea     rdi, [rax+rdi*2]
0x180004e57  mov     rcx, [rbx+28h]
0x180004e5b  mov     rax, [rbx+20h]
0x180004e5f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004e63  jz      short loc_180004E71
0x180004e65  test    rax, rax
0x180004e68  jz      short loc_180004E76
0x180004e6a  mov     rax, [rax]
0x180004e6d  lea     rax, [rax+rcx*2]
0x180004e71  cmp     rdi, rax
0x180004e74  jb      short loc_180004EC9
0x180004e76  mov     rcx, [rbx+38h]
0x180004e7a  test    rcx, rcx
0x180004e7d  jz      short loc_180004E04
0x180004e7f  mov     rax, [rcx]
0x180004e82  mov     rax, [rax+10h]
0x180004e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e8b  test    al, al
0x180004e8d  jz      loc_180004E04
0x180004e93  mov     rcx, [rbx+38h]
0x180004e97  mov     rax, [rcx]
0x180004e9a  mov     rax, [rax+8]
0x180004e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ea3  mov     r8d, eax
0x180004ea6  lea     rdx, [rsp+68h+var_38]
0x180004eab  mov     rcx, rbx
0x180004eae  call    ??H?$OffsetPtr@G_K@@QEAA?AV0@_K@Z; OffsetPtr<ushort,unsigned __int64>::operator+(unsigned __int64)
0x180004eb3  mov     rdx, rax
0x180004eb6  lea     rcx, [rbx+20h]
0x180004eba  call    ??4?$OffsetPtr@G_K@@QEAAAEAV0@AEBV0@@Z; OffsetPtr<ushort,unsigned __int64>::operator=(OffsetPtr<ushort,unsigned __int64> const &)
0x180004ebf  jmp     loc_180004E11
0x180004ec4  mov     rdi, rbp
0x180004ec7  jmp     short loc_180004E57
0x180004ec9  mov     rcx, [rbx+18h]
0x180004ecd  mov     rax, [rbx+10h]
0x180004ed1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004ed5  jz      short loc_180004EE7
0x180004ed7  test    rax, rax
0x180004eda  jz      loc_18000570B
0x180004ee0  mov     rax, [rax]
0x180004ee3  lea     rax, [rax+rcx*2]
0x180004ee7  cmp     word ptr [rax+2], 21h ; '!'
0x180004eec  jnz     loc_180004E04
0x180004ef2  cmp     [rbx+10h], rbp
0x180004ef6  jz      loc_180005874
0x180004efc  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x180004f01  jz      loc_180005874
0x180004f07  mov     rdi, [rbx+10h]
0x180004f0b  mov     rsi, [rbx+18h]
0x180004f0f  test    rdi, rdi
0x180004f12  jz      loc_18000589C
0x180004f18  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180004f1c  jz      loc_18000589C
0x180004f22  add     rsi, 2
0x180004f26  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180004f2a  jz      short loc_180004F38
0x180004f2c  test    rdi, rdi
0x180004f2f  jz      short loc_180004FA9
0x180004f31  mov     rax, [rdi]
0x180004f34  lea     rdi, [rax+rsi*2]
0x180004f38  mov     rcx, [rbx+28h]
0x180004f3c  mov     rax, [rbx+20h]
0x180004f40  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004f44  jz      short loc_180004F52
0x180004f46  test    rax, rax
0x180004f49  jz      short loc_180004F57
0x180004f4b  mov     rax, [rax]
0x180004f4e  lea     rax, [rax+rcx*2]
0x180004f52  cmp     rdi, rax
0x180004f55  jb      short loc_180004FAE
0x180004f57  mov     rcx, [rbx+38h]
0x180004f5b  test    rcx, rcx
0x180004f5e  jz      loc_180004E04
0x180004f64  mov     rax, [rcx]
0x180004f67  mov     rax, [rax+10h]
0x180004f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f70  test    al, al
0x180004f72  jz      loc_180004E04
0x180004f78  mov     rcx, [rbx+38h]
0x180004f7c  mov     rax, [rcx]
0x180004f7f  mov     rax, [rax+8]
0x180004f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f88  mov     r8d, eax
0x180004f8b  lea     rdx, [rsp+68h+var_38]
0x180004f90  mov     rcx, rbx
0x180004f93  call    ??H?$OffsetPtr@G_K@@QEAA?AV0@_K@Z; OffsetPtr<ushort,unsigned __int64>::operator+(unsigned __int64)
0x180004f98  mov     rdx, rax
0x180004f9b  lea     rcx, [rbx+20h]
0x180004f9f  call    ??4?$OffsetPtr@G_K@@QEAAAEAV0@AEBV0@@Z; OffsetPtr<ushort,unsigned __int64>::operator=(OffsetPtr<ushort,unsigned __int64> const &)
0x180004fa4  jmp     loc_180004EF2
0x180004fa9  mov     rdi, rbp
0x180004fac  jmp     short loc_180004F38
0x180004fae  mov     rcx, [rbx+18h]
0x180004fb2  mov     rax, [rbx+10h]
0x180004fb6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004fba  jz      short loc_180004FCC
0x180004fbc  test    rax, rax
0x180004fbf  jz      loc_180005731
0x180004fc5  mov     rax, [rax]
0x180004fc8  lea     rax, [rax+rcx*2]
0x180004fcc  cmp     word ptr [rax+4], 5Bh ; '['
0x180004fd1  jnz     loc_180004E04
0x180004fd7  nop     word ptr [rax+rax+00000000h]
0x180004fe0  cmp     [rbx+10h], rbp
0x180004fe4  jz      loc_1800058C4
0x180004fea  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x180004fef  jz      loc_1800058C4
0x180004ff5  mov     rdi, [rbx+10h]
0x180004ff9  mov     rsi, [rbx+18h]
0x180004ffd  test    rdi, rdi
0x180005000  jz      loc_1800058EC
0x180005006  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000500a  jz      loc_1800058EC
0x180005010  add     rsi, 3
0x180005014  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180005018  jz      short loc_180005026
0x18000501a  test    rdi, rdi
0x18000501d  jz      short loc_180005097
0x18000501f  mov     rax, [rdi]
0x180005022  lea     rdi, [rax+rsi*2]
0x180005026  mov     rcx, [rbx+28h]
0x18000502a  mov     rax, [rbx+20h]
0x18000502e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005032  jz      short loc_180005040
0x180005034  test    rax, rax
0x180005037  jz      short loc_180005045
0x180005039  mov     rax, [rax]
0x18000503c  lea     rax, [rax+rcx*2]
0x180005040  cmp     rdi, rax
0x180005043  jb      short loc_18000509C
0x180005045  mov     rcx, [rbx+38h]
0x180005049  test    rcx, rcx
0x18000504c  jz      loc_180004E04
0x180005052  mov     rax, [rcx]
0x180005055  mov     rax, [rax+10h]
0x180005059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000505e  test    al, al
0x180005060  jz      loc_180004E04
0x180005066  mov     rcx, [rbx+38h]
0x18000506a  mov     rax, [rcx]
0x18000506d  mov     rax, [rax+8]
0x180005071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005076  mov     r8d, eax
0x180005079  lea     rdx, [rsp+68h+var_38]
0x18000507e  mov     rcx, rbx
0x180005081  call    ??H?$OffsetPtr@G_K@@QEAA?AV0@_K@Z; OffsetPtr<ushort,unsigned __int64>::operator+(unsigned __int64)
0x180005086  mov     rdx, rax
0x180005089  lea     rcx, [rbx+20h]
0x18000508d  call    ??4?$OffsetPtr@G_K@@QEAAAEAV0@AEBV0@@Z; OffsetPtr<ushort,unsigned __int64>::operator=(OffsetPtr<ushort,unsigned __int64> const &)
0x180005092  jmp     loc_180004FE0
0x180005097  mov     rdi, rbp
0x18000509a  jmp     short loc_180005026
0x18000509c  mov     rcx, [rbx+18h]
0x1800050a0  mov     rax, [rbx+10h]
0x1800050a4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800050a8  jz      short loc_1800050BA
0x1800050aa  test    rax, rax
0x1800050ad  jz      loc_180005739
0x1800050b3  mov     rax, [rax]
0x1800050b6  lea     rax, [rax+rcx*2]
0x1800050ba  cmp     word ptr [rax+6], 43h ; 'C'
0x1800050bf  jnz     loc_180004E04
0x1800050c5  cmp     [rbx+10h], rbp
0x1800050c9  jz      loc_180005914
0x1800050cf  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1800050d4  jz      loc_180005914
0x1800050da  mov     rdi, [rbx+10h]
0x1800050de  mov     rsi, [rbx+18h]
0x1800050e2  test    rdi, rdi
0x1800050e5  jz      loc_18000593C
0x1800050eb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800050ef  jz      loc_18000593C
0x1800050f5  add     rsi, 4
0x1800050f9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800050fd  jz      short loc_18000510B
0x1800050ff  test    rdi, rdi
0x180005102  jz      short loc_18000517C
0x180005104  mov     rax, [rdi]
0x180005107  lea     rdi, [rax+rsi*2]
0x18000510b  mov     rcx, [rbx+28h]
0x18000510f  mov     rax, [rbx+20h]
0x180005113  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005117  jz      short loc_180005125
0x180005119  test    rax, rax
0x18000511c  jz      short loc_18000512A
0x18000511e  mov     rax, [rax]
0x180005121  lea     rax, [rax+rcx*2]
0x180005125  cmp     rdi, rax
0x180005128  jb      short loc_180005181
0x18000512a  mov     rcx, [rbx+38h]
0x18000512e  test    rcx, rcx
0x180005131  jz      loc_180004E04
0x180005137  mov     rax, [rcx]
0x18000513a  mov     rax, [rax+10h]
0x18000513e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005143  test    al, al
0x180005145  jz      loc_180004E04
0x18000514b  mov     rcx, [rbx+38h]
0x18000514f  mov     rax, [rcx]
0x180005152  mov     rax, [rax+8]
0x180005156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000515b  mov     r8d, eax
0x18000515e  lea     rdx, [rsp+68h+var_38]
0x180005163  mov     rcx, rbx
0x180005166  call    ??H?$OffsetPtr@G_K@@QEAA?AV0@_K@Z; OffsetPtr<ushort,unsigned __int64>::operator+(unsigned __int64)
0x18000516b  mov     rdx, rax
0x18000516e  lea     rcx, [rbx+20h]
0x180005172  call    ??4?$OffsetPtr@G_K@@QEAAAEAV0@AEBV0@@Z; OffsetPtr<ushort,unsigned __int64>::operator=(OffsetPtr<ushort,unsigned __int64> const &)
0x180005177  jmp     loc_1800050C5
0x18000517c  mov     rdi, rbp
0x18000517f  jmp     short loc_18000510B
0x180005181  mov     rcx, [rbx+18h]
0x180005185  mov     rax, [rbx+10h]
0x180005189  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000518d  jz      short loc_18000519F
0x18000518f  test    rax, rax
  ... truncated ...
```
