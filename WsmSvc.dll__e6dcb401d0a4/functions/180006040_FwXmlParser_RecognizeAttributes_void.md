# FwXmlParser::RecognizeAttributes(void)

- ea: `0x180006040`
- end: `0x180007378`
- name: `?RecognizeAttributes@FwXmlParser@@QEAAXXZ`
- size: `4920`
- prototype: `void __fastcall(FwXmlParser *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002524`
- `0x180002b38`

## callees

- `0x18000143c`
- `0x180005d10`
- `0x180006040`
- `0x18010d8ac`
- `0x1801c2010`

## import_xrefs

- `msvcrt!iswspace` at `0x1800060e3`
- `msvcrt!iswspace` at `0x18000655d`
- `msvcrt!iswspace` at `0x180006928`
- `msvcrt!iswspace` at `0x180006b4d`
- `msvcrt!iswspace` at `0x1800060e3`
- `msvcrt!iswspace` at `0x18000655d`
- `msvcrt!iswspace` at `0x180006928`
- `msvcrt!iswspace` at `0x180006b4d`

## string_xrefs

- `0x180006369`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000676b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800067ac`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000695b`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180006d44`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180006eb4`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180006ee6`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180006f18`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180006f4e`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180006f80`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180006fb2`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180006fe4`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007016`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000704c`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x18000707e`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800070b0`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800070d8`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007100`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007128`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007150`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007178`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800071a0`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800071c8`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800071f0`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007218`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007240`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007268`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007294`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800072cf`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x1800072fb`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`
- `0x180007327`: `onecore\admin\wmi\wmx\fwxml\OffsetPtr.h`

## pseudocode

```c
void __fastcall FwXmlParser::RecognizeAttributes(FwXmlParser *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rax
  wint_t *v8; // rcx
  _QWORD *v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int16 *v15; // rcx
  __int16 v16; // cx
  _QWORD *v17; // rdi
  __int64 v18; // rsi
  __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rax
  unsigned __int16 *v23; // rcx
  unsigned __int16 v24; // cx
  __int64 v25; // r13
  char v26; // bp
  __int64 v27; // r14
  int v28; // r12d
  _QWORD *v29; // rsi
  __int64 v30; // rdi
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rcx
  _QWORD *v34; // rax
  __int16 *v35; // rcx
  __int16 v36; // cx
  _QWORD *v37; // rsi
  __int64 v38; // rdi
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  _QWORD *v42; // rax
  wint_t *v43; // rcx
  bool v44; // zf
  __int64 v45; // rax
  unsigned __int64 v46; // rax
  __int64 v47; // rdx
  _QWORD *v48; // rdi
  __int64 v49; // rsi
  __int64 v50; // rcx
  _QWORD *v51; // rax
  __int64 v52; // rdx
  _QWORD *v53; // rcx
  _WORD *v54; // rax
  _QWORD *v55; // rsi
  __int64 v56; // rdi
  __int64 v57; // rcx
  _QWORD *v58; // rax
  __int64 v59; // rcx
  _QWORD *v60; // rax
  wint_t *v61; // rcx
  _QWORD *v62; // rdi
  __int64 v63; // rsi
  __int64 v64; // rcx
  _QWORD *v65; // rax
  __int64 v66; // rdx
  _QWORD *v67; // rcx
  _WORD *v68; // rax
  __int16 v69; // si
  __int64 v70; // rax
  __int64 v71; // r15
  __int64 v72; // r14
  __int64 v73; // rdx
  __int64 v74; // rcx
  _QWORD *v75; // rax
  __int64 v76; // rdi
  __int64 v77; // rax
  _QWORD *v78; // rcx
  __int64 v79; // rbp
  _QWORD *v80; // rsi
  __int64 v81; // rdi
  __int64 v82; // rcx
  _QWORD *v83; // rax
  __int64 v84; // rcx
  _QWORD *v85; // rax
  wint_t *v86; // rcx
  __int64 *v87; // rcx
  __int64 v88; // rax
  void (__fastcall *v89)(__int64 *, _QWORD *, _QWORD, _QWORD *, int, _QWORD *, _DWORD); // rax
  _QWORD *v90; // rdi
  __int64 v91; // rsi
  __int64 v92; // rcx
  _QWORD *v93; // rax
  __int64 v94; // rcx
  _QWORD *v95; // rax
  _QWORD v96[2]; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v97[2]; // [rsp+50h] [rbp-68h] BYREF
  _QWORD v98[11]; // [rsp+60h] [rbp-58h] BYREF
  unsigned int pExceptionObject; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v100; // [rsp+C8h] [rbp+10h]
  __int64 v101; // [rsp+D0h] [rbp+18h]
  __int64 v102; // [rsp+D8h] [rbp+20h]

  while ( 1 )
  {
    while ( 1 )
    {
      if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 131, L"131", 0x54Fu, 0);
      v2 = (_QWORD *)*((_QWORD *)this + 2);
      v3 = *((_QWORD *)this + 3);
      if ( v2 && v3 != -1 )
      {
LABEL_5:
        v2 = (_QWORD *)(*v2 + 2 * v3);
        goto LABEL_6;
      }
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 124, L"124", 0x54Fu, 0);
      if ( v3 != -1 )
      {
        if ( v2 )
          goto LABEL_5;
        v2 = 0;
      }
LABEL_6:
      v4 = *((_QWORD *)this + 5);
      v5 = (_QWORD *)*((_QWORD *)this + 4);
      if ( v4 != -1 )
      {
        if ( !v5 )
          goto LABEL_267;
        v5 = (_QWORD *)(*v5 + 2 * v4);
      }
      if ( v2 < v5 )
        break;
LABEL_267:
      FwXmlParser::WaitForMore(this, 1);
    }
    v6 = *((_QWORD *)this + 3);
    if ( v6 == -1 )
    {
      v8 = (wint_t *)*((_QWORD *)this + 2);
    }
    else
    {
      v7 = (_QWORD *)*((_QWORD *)this + 2);
      v8 = v7 ? (wint_t *)(*v7 + 2 * v6) : 0LL;
    }
    if ( !iswspace(*v8) )
      break;
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 118, L"118", 0x54Fu, 0);
    ++*((_QWORD *)this + 3);
  }
  while ( 1 )
  {
    if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 131, L"131", 0x54Fu, 0);
    v9 = (_QWORD *)*((_QWORD *)this + 2);
    v10 = *((_QWORD *)this + 3);
    if ( v9 && v10 != -1 )
    {
LABEL_21:
      v9 = (_QWORD *)(*v9 + 2 * v10);
      goto LABEL_22;
    }
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 124, L"124", 0x54Fu, 0);
    if ( v10 != -1 )
    {
      if ( v9 )
        goto LABEL_21;
      v9 = 0;
    }
LABEL_22:
    v11 = *((_QWORD *)this + 5);
    v12 = (_QWORD *)*((_QWORD *)this + 4);
    if ( v11 != -1 )
    {
      if ( !v12 )
        goto LABEL_268;
      v12 = (_QWORD *)(*v12 + 2 * v11);
    }
    if ( v9 < v12 )
      break;
LABEL_268:
    FwXmlParser::WaitForMore(this, 1);
  }
  v13 = *((_QWORD *)this + 3);
  if ( v13 == -1 )
  {
    v15 = (__int16 *)*((_QWORD *)this + 2);
  }
  else
  {
    v14 = (_QWORD *)*((_QWORD *)this + 2);
    if ( v14 )
      v15 = (__int16 *)(*v14 + 2 * v13);
    else
      v15 = 0;
  }
LABEL_29:
  v16 = *v15;
  if ( (unsigned __int16)(v16 - 62) > 1u && v16 != 47 )
  {
    while ( 2 )
    {
      if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 131, L"131", 0x54Fu, 0);
      v17 = (_QWORD *)*((_QWORD *)this + 2);
      v18 = *((_QWORD *)this + 3);
      if ( v17 && v18 != -1
        || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 124, L"124", 0x54Fu, 0), v18 != -1) )
      {
        if ( v17 )
          v17 = (_QWORD *)(*v17 + 2 * v18);
        else
          v17 = 0;
      }
      v19 = *((_QWORD *)this + 5);
      v20 = (_QWORD *)*((_QWORD *)this + 4);
      if ( v19 != -1 )
      {
        if ( v20 )
        {
          v20 = (_QWORD *)(*v20 + 2 * v19);
          break;
        }
LABEL_269:
        FwXmlParser::WaitForMore(this, 1);
        continue;
      }
      break;
    }
    if ( v17 >= v20 )
      goto LABEL_269;
    v21 = *((_QWORD *)this + 3);
    if ( v21 == -1 )
    {
      v23 = (unsigned __int16 *)*((_QWORD *)this + 2);
    }
    else
    {
      v22 = (_QWORD *)*((_QWORD *)this + 2);
      if ( v22 )
        v23 = (unsigned __int16 *)(*v22 + 2 * v21);
      else
        v23 = 0;
    }
    v24 = *v23;
    if ( (unsigned __int16)(v24 - 97) > 0x19u
      && (unsigned __int16)(v24 - 8204) > 1u
      && (unsigned __int16)(v24 - 65) > 0x19u )
    {
      v46 = v24;
      if ( (unsigned __int16)(v24 - 192) > 0x36u
        || (v47 = 0x7FFFFFFF7FFFFFLL, LOWORD(v46) = v24 - 192, !_bittest64(&v47, v46)) )
      {
        if ( (unsigned __int16)(v24 - 248) > 0x207u
          && (unsigned __int16)(v24 - 880) > 0xDu
          && (unsigned __int16)(v24 - 895) > 0x1C80u
          && (unsigned __int16)(v24 - 11264) > 0x3EFu
          && (unsigned __int16)(v24 - 12289) > 0xA7FEu
          && (unsigned __int16)(v24 + 1792) > 0x4CFu
          && v24 != 95
          && (unsigned __int16)(v24 + 528) > 0x20Du
          && (unsigned __int16)(v24 - 8304) > 0x11Fu )
        {
          pExceptionObject = 5;
          throw (int *)&pExceptionObject;
        }
      }
    }
    v25 = *((_QWORD *)this + 2);
    v26 = 0;
    v27 = *((_QWORD *)this + 3);
    v28 = 1;
    v100 = 0;
    v101 = 0;
    pExceptionObject = 0;
    v102 = v27;
    if ( !v25 || v27 == -1 )
      goto LABEL_66;
LABEL_48:
    ++*((_QWORD *)this + 3);
    while ( 1 )
    {
      if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 131, L"131", 0x54Fu, 0);
      v29 = (_QWORD *)*((_QWORD *)this + 2);
      v30 = *((_QWORD *)this + 3);
      if ( v29 && v30 != -1
        || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 124, L"124", 0x54Fu, 0), v30 != -1) )
      {
        if ( v29 )
          v29 = (_QWORD *)(*v29 + 2 * v30);
        else
          v29 = 0;
      }
      v31 = *((_QWORD *)this + 5);
      v32 = (_QWORD *)*((_QWORD *)this + 4);
      if ( v31 != -1 )
      {
        if ( !v32 )
          goto LABEL_263;
        v32 = (_QWORD *)(*v32 + 2 * v31);
      }
      if ( v29 >= v32 )
      {
LABEL_263:
        FwXmlParser::WaitForMore(this, 1);
        continue;
      }
      v33 = *((_QWORD *)this + 3);
      if ( v33 == -1 )
      {
        v35 = (__int16 *)*((_QWORD *)this + 2);
      }
      else
      {
        v34 = (_QWORD *)*((_QWORD *)this + 2);
        if ( v34 )
          v35 = (__int16 *)(*v34 + 2 * v33);
        else
          v35 = 0;
      }
      v36 = *v35;
      if ( v36 != 58 )
      {
        if ( (unsigned __int16)(v36 - 97) > 0x19u
          && (unsigned __int16)(v36 - 65) > 0x19u
          && v36 != 95
          && (unsigned __int16)(v36 - 48) > 9u
          && (unsigned __int16)(v36 - 45) > 1u
          && (unsigned __int16)(v36 - 768) > 0x6Fu
          && (unsigned __int16)(v36 - 8255) > 1u
          && v36 != 183
          && (unsigned __int16)(v36 - 192) > 0x16u
          && (unsigned __int16)(v36 - 216) > 0x1Eu
          && (unsigned __int16)(v36 - 248) > 0x207u
          && (unsigned __int16)(v36 - 880) > 0xDu
          && (unsigned __int16)(v36 - 895) > 0x1C80u
          && (unsigned __int16)(v36 - 8204) > 1u
          && (unsigned __int16)(v36 - 8304) > 0x11Fu
          && (unsigned __int16)(v36 - 11264) > 0x3EFu
          && (unsigned __int16)(v36 - 12289) > 0xA7FEu
          && (unsigned __int16)(v36 + 1792) > 0x4CFu
          && (unsigned __int16)(v36 + 528) > 0x20Du )
        {
          if ( v26 && !v28 )
          {
            pExceptionObject = 7;
            throw (int *)&pExceptionObject;
          }
          while ( 1 )
          {
            if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 131, L"131", 0x54Fu, 0);
            v37 = (_QWORD *)*((_QWORD *)this + 2);
            v38 = *((_QWORD *)this + 3);
            if ( v37 && v38 != -1
              || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 124, L"124", 0x54Fu, 0),
                  v38 != -1) )
            {
              if ( v37 )
                v37 = (_QWORD *)(*v37 + 2 * v38);
              else
                v37 = 0;
            }
            v39 = *((_QWORD *)this + 5);
            v40 = (_QWORD *)*((_QWORD *)this + 4);
            if ( v39 != -1 )
            {
              if ( !v40 )
                goto LABEL_264;
              v40 = (_QWORD *)(*v40 + 2 * v39);
            }
            if ( v37 >= v40 )
            {
LABEL_264:
              FwXmlParser::WaitForMore(this, 1);
              continue;
            }
            v41 = *((_QWORD *)this + 3);
            if ( v41 == -1 )
            {
              v43 = (wint_t *)*((_QWORD *)this + 2);
            }
            else
            {
              v42 = (_QWORD *)*((_QWORD *)this + 2);
              v43 = v42 ? (wint_t *)(*v42 + 2 * v41) : 0LL;
            }
            if ( !iswspace(*v43) )
              break;
            if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 118, L"118", 0x54Fu, 0);
            ++*((_QWORD *)this + 3);
          }
          while ( 2 )
          {
            if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 131, L"131", 0x54Fu, 0);
            v48 = (_QWORD *)*((_QWORD *)this + 2);
            v49 = *((_QWORD *)this + 3);
            if ( v48 && v49 != -1
              || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 124, L"124", 0x54Fu, 0),
                  v49 != -1) )
            {
              if ( v48 )
                v48 = (_QWORD *)(*v48 + 2 * v49);
              else
                v48 = 0;
            }
            v50 = *((_QWORD *)this + 5);
            v51 = (_QWORD *)*((_QWORD *)this + 4);
            if ( v50 == -1 )
            {
LABEL_145:
              if ( v48 < v51 )
              {
                v52 = *((_QWORD *)this + 3);
                if ( v52 == -1 )
                {
                  v54 = (_WORD *)*((_QWORD *)this + 2);
                  v53 = v54;
                }
                else
                {
                  v53 = (_QWORD *)*((_QWORD *)this + 2);
                  if ( v53 )
                  {
                    v54 = (_WORD *)(*v53 + 2 * v52);
                  }
                  else
                  {
                    v54 = 0;
                    v53 = 0;
                  }
                }
                if ( *v54 != 61 )
                {
                  pExceptionObject = 6;
                  throw (int *)&pExceptionObject;
                }
                if ( !v53 || v52 == -1 )
LABEL_169:
                  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 118, L"118", 0x54Fu, 0);
                while ( 2 )
                {
                  ++*((_QWORD *)this + 3);
LABEL_153:
                  if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
                    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 131, L"131", 0x54Fu, 0);
                  v55 = (_QWORD *)*((_QWORD *)this + 2);
                  v56 = *((_QWORD *)this + 3);
                  if ( v55 && v56 != -1
                    || (WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 124, L"124", 0x54Fu, 0),
                        v56 != -1) )
                  {
                    if ( v55 )
                      v55 = (_QWORD *)(*v55 + 2 * v56);
                    else
                      v55 = 0;
                  }
                  v57 = *((_QWORD *)this + 5);
                  v58 = (_QWORD *)*((_QWORD *)this + 4);
                  if ( v57 == -1 )
                  {
LABEL_162:
                    if ( v55 < v58 )
                    {
                      v59 = *((_QWORD *)this + 3);
                      if ( v59 == -1 )
                      {
                        v61 = (wint_t *)*((_QWORD *)this + 2);
                      }
                      else
                      {
                        v60 = (_QWORD *)*((_QWORD *)this + 2);
                        if ( v60 )
                          v61 = (wint_t *)(*v60 + 2 * v59);
                        else
                          v61 = 0;
                      }
                      if ( iswspace(*v61) )
                      {
                        if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
                          goto LABEL_169;
                        continue;
                      }
                      while ( 2 )
                      {
                        if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
                          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 131, L"131", 0x54Fu, 0);
                        v62 = (_QWORD *)*((_QWORD *)this + 2);
                        v63 = *((_QWORD *)this + 3);
                        if ( v62 && v63 != -1
                          || (WSManError(
                                (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                                124,
                                L"124",
                                0x54Fu,
                                0),
                              v63 != -1) )
                        {
                          if ( v62 )
                            v62 = (_QWORD *)(*v62 + 2 * v63);
                          else
                            v62 = 0;
                        }
                        v64 = *((_QWORD *)this + 5);
                        v65 = (_QWORD *)*((_QWORD *)this + 4);
                        if ( v64 == -1 )
                        {
LABEL_179:
                          if ( v62 < v65 )
                          {
                            v66 = *((_QWORD *)this + 3);
                            if ( v66 == -1 )
                            {
                              v68 = (_WORD *)*((_QWORD *)this + 2);
                              v67 = v68;
                            }
                            else
                            {
                              v67 = (_QWORD *)*((_QWORD *)this + 2);
                              if ( v67 )
                              {
                                v68 = (_WORD *)(*v67 + 2 * v66);
                              }
                              else
                              {
                                v68 = 0;
                                v67 = 0;
                              }
                            }
                            v69 = *v68;
                            if ( *v68 != 34 && v69 != 39 )
                            {
                              pExceptionObject = 6;
                              throw (int *)&pExceptionObject;
                            }
                            if ( !v67 || v66 == -1 )
                              WSManError(
                                (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                                118,
                                L"118",
                                0x54Fu,
                                0);
                            v70 = *((_QWORD *)this + 3) + 1LL;
                            *((_QWORD *)this + 3) = v70;
                            v71 = v70;
                            v72 = *((_QWORD *)this + 2);
                            while ( 1 )
                            {
                              if ( *((_QWORD *)this + 4) != *((_QWORD *)this + 2) || *((_QWORD *)this + 5) == -1 )
                                WSManError(
                                  (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                                  140,
                                  L"140",
                                  0x54Fu,
                                  0);
                              v73 = *((_QWORD *)this + 3);
                              v74 = *((_QWORD *)this + 5) - v73;
                              if ( v73 == -1 )
                              {
                                v76 = *((_QWORD *)this + 2);
                              }
                              else
                              {
                                v75 = (_QWORD *)*((_QWORD *)this + 2);
                                v76 = v75 ? *v75 + 2 * v73 : 0LL;
                              }
                              while ( 1 )
                              {
                                if ( !v74 )
                                  goto LABEL_310;
                                if ( *(_WORD *)v76 == v69 )
                                  break;
                                v76 += 2;
                                --v74;
                              }
                              if ( v76 )
                                break;
LABEL_310:
                              FwXmlParser::WaitForMore(this, 1);
                            }
                            v77 = *((_QWORD *)this + 3);
                            if ( v77 == -1 )
                            {
                              v76 = (v76 - *((_QWORD *)this + 2)) >> 1;
                              LODWORD(v79) = v76;
                            }
                            else
                            {
                              v78 = (_QWORD *)*((_QWORD *)this + 2);
                              if ( v78 )
                              {
                                v76 = (v76 - 2 * v77 - *v78) >> 1;
                                LODWORD(v79) = v76;
                                goto LABEL_199;
                              }
                              v79 = v76 >> 1;
                              LODWORD(v76) = v76 >> 1;
                            }
                            WSManError(
                              (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                              124,
                              L"124",
                              0x54Fu,
                              0);
LABEL_199:
                            for ( *((_QWORD *)this + 3) += (unsigned int)(v76 + 1); ; ++*((_QWORD *)this + 3) )
                            {
                              while ( 2 )
                              {
                                if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
                                  WSManError(
                                    (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                                    131,
                                    L"131",
                                    0x54Fu,
                                    0);
                                v80 = (_QWORD *)*((_QWORD *)this + 2);
                                v81 = *((_QWORD *)this + 3);
                                if ( v80 && v81 != -1
                                  || (WSManError(
                                        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                                        124,
                                        L"124",
                                        0x54Fu,
                                        0),
                                      v81 != -1) )
                                {
                                  if ( v80 )
                                    v80 = (_QWORD *)(*v80 + 2 * v81);
                                }
                                v82 = *((_QWORD *)this + 5);
                                v83 = (_QWORD *)*((_QWORD *)this + 4);
                                if ( v82 != -1 )
                                {
                                  if ( !v83 )
                                    goto LABEL_266;
                                  v83 = (_QWORD *)(*v83 + 2 * v82);
                                }
                                if ( v80 >= v83 )
                                {
LABEL_266:
                                  FwXmlParser::WaitForMore(this, 1);
                                  continue;
                                }
                                break;
                              }
                              v84 = *((_QWORD *)this + 3);
                              if ( v84 == -1 )
                              {
                                v86 = (wint_t *)*((_QWORD *)this + 2);
                              }
                              else
                              {
                                v85 = (_QWORD *)*((_QWORD *)this + 2);
                                if ( v85 )
                                  v86 = (wint_t *)(*v85 + 2 * v84);
                                else
                                  v86 = 0;
                              }
                              if ( !iswspace(*v86) )
                              {
                                v87 = (__int64 *)*((_QWORD *)this + 9);
                                v88 = *v87;
                                v97[1] = v102;
                                v98[0] = v100;
                                v89 = *(void (__fastcall **)(__int64 *, _QWORD *, _QWORD, _QWORD *, int, _QWORD *, _DWORD))(v88 + 16);
                                v98[1] = v101;
                                v96[0] = v72;
                                v96[1] = v71;
                                v97[0] = v25;
                                v89(v87, v98, pExceptionObject, v97, v28, v96, v79);
                                while ( 2 )
                                {
                                  if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
                                    WSManError(
                                      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                                      131,
                                      L"131",
                                      0x54Fu,
                                      0);
                                  v90 = (_QWORD *)*((_QWORD *)this + 2);
                                  v91 = *((_QWORD *)this + 3);
                                  if ( v90 && v91 != -1
                                    || (WSManError(
                                          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                                          124,
                                          L"124",
                                          0x54Fu,
                                          0),
                                        v91 != -1) )
                                  {
                                    if ( v90 )
                                      v90 = (_QWORD *)(*v90 + 2 * v91);
                                  }
                                  v92 = *((_QWORD *)this + 5);
                                  v93 = (_QWORD *)*((_QWORD *)this + 4);
                                  if ( v92 == -1 )
                                  {
LABEL_227:
                                    if ( v90 < v93 )
                                    {
                                      v94 = *((_QWORD *)this + 3);
                                      if ( v94 == -1 )
                                      {
                                        v15 = (__int16 *)*((_QWORD *)this + 2);
                                      }
                                      else
                                      {
                                        v95 = (_QWORD *)*((_QWORD *)this + 2);
                                        if ( v95 )
                                          v15 = (__int16 *)(*v95 + 2 * v94);
                                        else
                                          v15 = 0;
                                      }
                                      goto LABEL_29;
                                    }
                                  }
                                  else if ( v93 )
                                  {
                                    v93 = (_QWORD *)(*v93 + 2 * v92);
                                    goto LABEL_227;
                                  }
                                  FwXmlParser::WaitForMore(this, 1);
                                  continue;
                                }
                              }
                              if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
                                WSManError(
                                  (wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h",
                                  118,
                                  L"118",
                                  0x54Fu,
                                  0);
                            }
                          }
                        }
                        else if ( v65 )
                        {
                          v65 = (_QWORD *)(*v65 + 2 * v64);
                          goto LABEL_179;
                        }
                        FwXmlParser::WaitForMore(this, 1);
                        continue;
                      }
                    }
                  }
                  else if ( v58 )
                  {
                    v58 = (_QWORD *)(*v58 + 2 * v57);
                    goto LABEL_162;
                  }
                  break;
                }
                FwXmlParser::WaitForMore(this, 1);
                goto LABEL_153;
              }
            }
            else if ( v51 )
            {
              v51 = (_QWORD *)(*v51 + 2 * v50);
              goto LABEL_145;
            }
            FwXmlParser::WaitForMore(this, 1);
            continue;
          }
        }
        ++v28;
        if ( !*((_QWORD *)this + 2) || *((_QWORD *)this + 3) == -1 )
LABEL_66:
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 118, L"118", 0x54Fu, 0);
        goto LABEL_48;
      }
      if ( v26 )
      {
        pExceptionObject = 7;
        throw (int *)&pExceptionObject;
      }
      v26 = 1;
      if ( v100 && v100 != v25 && (v101 != -1 || v27 != -1) )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 71, L"71", 0x54Fu, 0);
      v44 = *((_QWORD *)this + 2) == 0;
      pExceptionObject = v28;
      v28 = 0;
      v100 = v25;
      v101 = v27;
      if ( v44 || *((_QWORD *)this + 3) == -1 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 118, L"118", 0x54Fu, 0);
      v45 = *((_QWORD *)this + 3) + 1LL;
      *((_QWORD *)this + 3) = v45;
      if ( v25 && v25 != *((_QWORD *)this + 2) && (v27 != -1 || v45 != -1) )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\OffsetPtr.h", 71, L"71", 0x54Fu, 0);
      v27 = *((_QWORD *)this + 3);
      v25 = *((_QWORD *)this + 2);
      v102 = v27;
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 24LL))(*((_QWORD *)this + 9));
}

```

## disassembly

```asm
0x180006040  push    rbx
0x180006042  push    rbp
0x180006043  push    rsi
0x180006044  push    rdi
0x180006045  push    r12
0x180006047  push    r13
0x180006049  push    r14
0x18000604b  push    r15
0x18000604d  sub     rsp, 78h
0x180006051  mov     rbx, rcx
0x180006054  xor     r15d, r15d
0x180006057  nop     word ptr [rax+rax+00000000h]
0x180006060  cmp     [rbx+10h], r15
0x180006064  jz      loc_180007099
0x18000606a  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18000606f  jz      loc_180007099
0x180006075  mov     rdi, [rbx+10h]
0x180006079  mov     rsi, [rbx+18h]
0x18000607d  test    rdi, rdi
0x180006080  jz      loc_180006F69
0x180006086  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000608a  jz      loc_180006F69
0x180006090  mov     rax, [rdi]
0x180006093  lea     rdi, [rax+rsi*2]
0x180006097  mov     rcx, [rbx+28h]
0x18000609b  mov     rax, [rbx+20h]
0x18000609f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800060a3  jz      short loc_1800060B5
0x1800060a5  test    rax, rax
0x1800060a8  jz      loc_180006E21
0x1800060ae  mov     rax, [rax]
0x1800060b1  lea     rax, [rax+rcx*2]
0x1800060b5  cmp     rdi, rax
0x1800060b8  jnb     loc_180006E21
0x1800060be  mov     rcx, [rbx+18h]
0x1800060c2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800060c6  jz      loc_1800067D6
0x1800060cc  mov     rax, [rbx+10h]
0x1800060d0  test    rax, rax
0x1800060d3  jz      loc_1800067DF
0x1800060d9  mov     rax, [rax]
0x1800060dc  lea     rcx, [rax+rcx*2]
0x1800060e0  movzx   ecx, word ptr [rcx]; C
0x1800060e3  call    cs:__imp_iswspace
0x1800060e9  test    eax, eax
0x1800060eb  jz      short loc_180006110
0x1800060ed  cmp     [rbx+10h], r15
0x1800060f1  jz      loc_1800070C1
0x1800060f7  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1800060fc  jz      loc_1800070C1
0x180006102  inc     qword ptr [rbx+18h]
0x180006106  jmp     loc_180006060
0x180006110  cmp     [rbx+10h], r15
0x180006114  jz      loc_1800070E9
0x18000611a  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18000611f  jz      loc_1800070E9
0x180006125  mov     rdi, [rbx+10h]
0x180006129  mov     rsi, [rbx+18h]
0x18000612d  test    rdi, rdi
0x180006130  jz      loc_180007067
0x180006136  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000613a  jz      loc_180007067
0x180006140  mov     rax, [rdi]
0x180006143  lea     rdi, [rax+rsi*2]
0x180006147  mov     rcx, [rbx+28h]
0x18000614b  mov     rax, [rbx+20h]
0x18000614f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006153  jz      short loc_180006165
0x180006155  test    rax, rax
0x180006158  jz      loc_180006E30
0x18000615e  mov     rax, [rax]
0x180006161  lea     rax, [rax+rcx*2]
0x180006165  cmp     rdi, rax
0x180006168  jnb     loc_180006E30
0x18000616e  mov     rcx, [rbx+18h]
0x180006172  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006176  jz      loc_180006DD4
0x18000617c  mov     rax, [rbx+10h]
0x180006180  test    rax, rax
0x180006183  jz      loc_180006DDD
0x180006189  mov     rax, [rax]
0x18000618c  lea     rcx, [rax+rcx*2]
0x180006190  movzx   ecx, word ptr [rcx]
0x180006193  lea     eax, [rcx-3Eh]
0x180006196  cmp     ax, 1
0x18000619a  jbe     loc_180006601
0x1800061a0  cmp     cx, 2Fh ; '/'
0x1800061a4  jz      loc_180006601
0x1800061aa  cmp     qword ptr [rbx+10h], 0
0x1800061af  jz      loc_180007111
0x1800061b5  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1800061ba  jz      loc_180007111
0x1800061c0  mov     rdi, [rbx+10h]
0x1800061c4  mov     rsi, [rbx+18h]
0x1800061c8  test    rdi, rdi
0x1800061cb  jz      loc_180006F9B
0x1800061d1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800061d5  jz      loc_180006F9B
0x1800061db  test    rdi, rdi
0x1800061de  jz      loc_180006D82
0x1800061e4  mov     rax, [rdi]
0x1800061e7  lea     rdi, [rax+rsi*2]
0x1800061eb  mov     rcx, [rbx+28h]
0x1800061ef  mov     rax, [rbx+20h]
0x1800061f3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800061f7  jz      short loc_180006209
0x1800061f9  test    rax, rax
0x1800061fc  jz      loc_180006E3F
0x180006202  mov     rax, [rax]
0x180006205  lea     rax, [rax+rcx*2]
0x180006209  cmp     rdi, rax
0x18000620c  jnb     loc_180006E3F
0x180006212  mov     rcx, [rbx+18h]
0x180006216  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000621a  jz      loc_180006D55
0x180006220  mov     rax, [rbx+10h]
0x180006224  test    rax, rax
0x180006227  jz      loc_180006D8A
0x18000622d  mov     rax, [rax]
0x180006230  lea     rcx, [rax+rcx*2]
0x180006234  movzx   ecx, word ptr [rcx]
0x180006237  lea     eax, [rcx-61h]
0x18000623a  cmp     ax, 19h
0x18000623e  jbe     short loc_180006255
0x180006240  movzx   eax, cx
0x180006243  mov     edx, 200Ch
0x180006248  sub     ax, dx
0x18000624b  cmp     ax, 1
0x18000624f  ja      loc_180006621
0x180006255  mov     r13, [rbx+10h]
0x180006259  xor     bpl, bpl
0x18000625c  mov     r14, [rbx+18h]
0x180006260  mov     r12d, 1
0x180006266  mov     [rsp+0B8h+arg_8], r15
0x18000626e  mov     [rsp+0B8h+arg_10], r15
0x180006276  mov     [rsp+0B8h+pExceptionObject], r15d
0x18000627e  mov     [rsp+0B8h+arg_18], r14
0x180006286  test    r13, r13
0x180006289  jz      loc_180006352
0x18000628f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180006293  jz      loc_180006352
0x180006299  inc     qword ptr [rbx+18h]
0x18000629d  cmp     qword ptr [rbx+10h], 0
0x1800062a2  jz      loc_180007139
0x1800062a8  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1800062ad  jz      loc_180007139
0x1800062b3  mov     rsi, [rbx+10h]
0x1800062b7  mov     rdi, [rbx+18h]
0x1800062bb  test    rsi, rsi
0x1800062be  jz      loc_180006E9D
0x1800062c4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800062c8  jz      loc_180006E9D
0x1800062ce  test    rsi, rsi
0x1800062d1  jz      loc_1800067C6
0x1800062d7  mov     rax, [rsi]
0x1800062da  lea     rsi, [rax+rdi*2]
0x1800062de  mov     rcx, [rbx+28h]
0x1800062e2  mov     rax, [rbx+20h]
0x1800062e6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800062ea  jz      short loc_1800062FC
0x1800062ec  test    rax, rax
0x1800062ef  jz      loc_180006DE5
0x1800062f5  mov     rax, [rax]
0x1800062f8  lea     rax, [rax+rcx*2]
0x1800062fc  cmp     rsi, rax
0x1800062ff  jnb     loc_180006DE5
0x180006305  mov     rcx, [rbx+18h]
0x180006309  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000630d  jz      loc_1800067BD
0x180006313  mov     rax, [rbx+10h]
0x180006317  test    rax, rax
0x18000631a  jz      loc_1800067CE
0x180006320  mov     rax, [rax]
0x180006323  lea     rcx, [rax+rcx*2]
0x180006327  movzx   ecx, word ptr [rcx]
0x18000632a  cmp     cx, 3Ah ; ':'
0x18000632e  jz      loc_18000658A
0x180006334  lea     eax, [rcx-61h]
0x180006337  cmp     ax, 19h
0x18000633b  ja      short loc_18000637A
0x18000633d  inc     r12d
0x180006340  cmp     qword ptr [rbx+10h], 0
0x180006345  jz      short loc_180006352
0x180006347  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18000634c  jnz     loc_180006299
0x180006352  mov     r9d, 54Fh; unsigned int
0x180006358  mov     [rsp+0B8h+var_98], r15; struct IRequestContext *
0x18000635d  lea     r8, a118; "118"
0x180006364  mov     edx, 76h ; 'v'; unsigned int
0x180006369  lea     rcx, aOnecoreAdminWm_23; "onecore\\admin\\wmi\\wmx\\fwxml\\Offset"...
0x180006370  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180006375  jmp     loc_180006299
0x18000637a  lea     eax, [rcx-41h]
0x18000637d  cmp     ax, 19h
0x180006381  jbe     short loc_18000633D
0x180006383  cmp     cx, 5Fh ; '_'
0x180006387  jz      short loc_18000633D
0x180006389  lea     eax, [rcx-30h]
0x18000638c  cmp     ax, 9
0x180006390  jbe     short loc_18000633D
0x180006392  lea     eax, [rcx-2Dh]
0x180006395  cmp     ax, 1
0x180006399  jbe     short loc_18000633D
0x18000639b  movzx   eax, cx
0x18000639e  mov     edx, 300h
0x1800063a3  sub     ax, dx
0x1800063a6  cmp     ax, 6Fh ; 'o'
0x1800063aa  jbe     short loc_18000633D
0x1800063ac  movzx   eax, cx
0x1800063af  mov     edx, 203Fh
0x1800063b4  sub     ax, dx
0x1800063b7  cmp     ax, 1
0x1800063bb  jbe     short loc_18000633D
0x1800063bd  mov     eax, 0B7h
0x1800063c2  cmp     cx, ax
0x1800063c5  jz      loc_18000633D
0x1800063cb  movzx   eax, cx
0x1800063ce  mov     edx, 0C0h
0x1800063d3  sub     ax, dx
0x1800063d6  cmp     ax, 16h
0x1800063da  jbe     loc_18000633D
0x1800063e0  movzx   eax, cx
0x1800063e3  mov     edx, 0D8h
0x1800063e8  sub     ax, dx
0x1800063eb  cmp     ax, 1Eh
0x1800063ef  jbe     loc_18000633D
0x1800063f5  mov     edx, 0F8h
0x1800063fa  movzx   eax, cx
0x1800063fd  sub     ax, dx
0x180006400  mov     edx, 207h
0x180006405  cmp     ax, dx
0x180006408  jbe     loc_18000633D
0x18000640e  movzx   eax, cx
0x180006411  mov     edx, 370h
0x180006416  sub     ax, dx
0x180006419  cmp     ax, 0Dh
0x18000641d  jbe     loc_18000633D
0x180006423  mov     edx, 37Fh
0x180006428  movzx   eax, cx
0x18000642b  sub     ax, dx
0x18000642e  mov     edx, 1C80h
0x180006433  cmp     ax, dx
0x180006436  jbe     loc_18000633D
0x18000643c  movzx   eax, cx
0x18000643f  mov     edx, 200Ch
0x180006444  sub     ax, dx
0x180006447  cmp     ax, 1
0x18000644b  jbe     loc_18000633D
0x180006451  mov     edx, 2070h
0x180006456  movzx   eax, cx
0x180006459  sub     ax, dx
0x18000645c  mov     edx, 11Fh
0x180006461  cmp     ax, dx
0x180006464  jbe     loc_18000633D
0x18000646a  mov     edx, 2C00h
0x18000646f  movzx   eax, cx
0x180006472  sub     ax, dx
0x180006475  mov     edx, 3EFh
0x18000647a  cmp     ax, dx
0x18000647d  jbe     loc_18000633D
0x180006483  mov     edx, 3001h
0x180006488  movzx   eax, cx
0x18000648b  sub     ax, dx
0x18000648e  mov     edx, 0A7FEh
0x180006493  cmp     ax, dx
0x180006496  jbe     loc_18000633D
0x18000649c  mov     eax, 700h
0x1800064a1  mov     edx, 4CFh
0x1800064a6  add     eax, ecx
0x1800064a8  cmp     ax, dx
0x1800064ab  jbe     loc_18000633D
0x1800064b1  mov     eax, 210h
0x1800064b6  add     cx, ax
0x1800064b9  mov     eax, 20Dh
0x1800064be  cmp     cx, ax
0x1800064c1  jbe     loc_18000633D
0x1800064c7  test    bpl, bpl
0x1800064ca  jnz     loc_180006C73
0x1800064d0  cmp     qword ptr [rbx+10h], 0
0x1800064d5  jz      loc_180007189
0x1800064db  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1800064e0  jz      loc_180007189
0x1800064e6  mov     rsi, [rbx+10h]
0x1800064ea  mov     rdi, [rbx+18h]
0x1800064ee  test    rsi, rsi
0x1800064f1  jz      loc_180006ECF
0x1800064f7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800064fb  jz      loc_180006ECF
0x180006501  test    rsi, rsi
0x180006504  jz      loc_180006CE1
0x18000650a  mov     rax, [rsi]
0x18000650d  lea     rsi, [rax+rdi*2]
0x180006511  mov     rcx, [rbx+28h]
0x180006515  mov     rax, [rbx+20h]
0x180006519  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000651d  jz      short loc_18000652F
0x18000651f  test    rax, rax
0x180006522  jz      loc_180006DF4
0x180006528  mov     rax, [rax]
0x18000652b  lea     rax, [rax+rcx*2]
  ... truncated ...
```
