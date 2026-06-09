# CDbCmdTreeNode::Clone(int)

- ea: `0x180182364`
- end: `0x180182c6b`
- name: `?Clone@CDbCmdTreeNode@@QEBAPEAV1@H@Z`
- size: `2311`
- prototype: `struct CDbCmdTreeNode *__fastcall(CDbCmdTreeNode *__hidden this, int)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180182280`
- `0x180182364`
- `0x18020e180`

## callees

- `0x180038f08`
- `0x18006c484`
- `0x18006c7bc`
- `0x18006e204`
- `0x18006e248`
- `0x18006e7b0`
- `0x180100938`
- `0x180103240`
- `0x18010b4f4`
- `0x180182364`
- `0x18018a0e1`
- `0x18018e8cb`
- `0x1801b7c8c`
- `0x1801b7ee4`
- `0x1801b7f94`
- `0x1801b8020`
- `0x1801b81a8`
- `0x1801b81f8`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182a2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182a2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801825a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018267a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801826f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018279f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018281d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018285d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801828a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801828e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801829dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182a84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182add`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182b46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182bc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182c2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801825a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182637`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018267a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801826f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018279f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018281d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018285d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801828a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801828e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801829dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182a84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182add`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182b46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182bc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180182c2c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1801824b4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1801824b4`
- `OLEAUT32!__imp_SysStringLen` at `0x1801824a8`
- `OLEAUT32!__imp_SysStringLen` at `0x1801824a8`

## string_xrefs

- `0x180182521`: `onecoreuap\base\appmodel\search\common\stgvar\dbcmdbas.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct CDbCmdTreeNode *__fastcall CDbCmdTreeNode::Clone(CDbCmdTreeNode *this, int a2)
{
  _OWORD *v4; // rbx
  unsigned __int16 v5; // ax
  int v7; // eax
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  CDbCmdTreeNode *v18; // rcx
  CDbCmdTreeNode *v19; // rcx
  OLECHAR *v20; // rcx
  UINT v21; // eax
  BSTR v22; // rax
  int v23; // edi
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  const struct CStorageVariant *v31; // rdi
  CStorageVariant *v32; // rax
  CAllocStorageVariant *v33; // r10
  unsigned int v34; // edx
  CStorageVariant *v35; // r10
  CDbColId *v36; // rcx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  _QWORD *v42; // rax
  LPVOID v43; // rdi
  __int64 v44; // r14
  __int64 v45; // rax
  void *v46; // rax
  const wchar_t *v47; // rcx
  const char *v48; // rcx
  SIZE_T v49; // rbp
  _BYTE *v50; // rax
  _BYTE *v51; // rcx
  __int64 v52; // rax
  char *v53; // r8
  _BYTE *v54; // rdx
  char v55; // r9
  _BYTE *v56; // rax
  signed int v57; // eax
  CDbColId *v58; // rax
  CDbColId *v59; // rcx
  unsigned int v60; // edx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  _OWORD *v65; // rax
  const struct tagDBPROPSET *v66; // rdx
  const struct tagDBPARAMETER *v67; // rdx
  _DWORD *v68; // rdx
  _QWORD *v69; // rax
  unsigned int v70; // edx
  __int64 v71; // rax
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  __int64 v75; // rax
  __int64 v76; // rcx
  _OWORD *v77; // rax
  __int64 v78; // rcx
  const wchar_t *v79; // rcx
  __int64 v80; // rax
  unsigned int v81; // ecx
  unsigned int v82; // ecx
  unsigned int v83; // ecx
  unsigned int v84; // ecx
  _OWORD *v85; // rax
  unsigned int v86; // edx
  const wchar_t **v87; // r14
  wchar_t *v88; // rax
  unsigned int v89; // edx
  __int64 v90; // rax
  const wchar_t *v91; // rcx
  __int64 v92; // rax
  int v93; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int64 v95; // [rsp+50h] [rbp+8h] BYREF
  _OWORD *v96; // [rsp+60h] [rbp+18h]

  if ( (*((_WORD *)this + 1) & 0x3000) != 0 )
    return 0;
  v4 = WINRT_IMPL_CoTaskMemAlloc(0x28u);
  v95 = (unsigned __int64)v4;
  if ( v4 )
  {
    v5 = *(_WORD *)this;
    *v4 = 0;
    v4[1] = 0;
    *((_QWORD *)v4 + 4) = 0;
    *(_DWORD *)v4 = v5;
  }
  else
  {
    v4 = 0;
  }
  v96 = v4;
  if ( !v4 )
    return 0;
  if ( a2 )
    v7 = *((_DWORD *)this + 8);
  else
    v7 = 0;
  *((_DWORD *)v4 + 8) = v7;
  *((_WORD *)v4 + 1) = *((_WORD *)this + 1);
  v8 = *((unsigned __int16 *)this + 1);
  if ( v8 > 0x48 )
  {
    if ( v8 <= 0x109 )
    {
      if ( v8 == 265 )
        goto LABEL_27;
      if ( v8 <= 0x102 )
      {
        if ( v8 != 258 )
        {
          v37 = v8 - 128;
          if ( !v37 )
            goto LABEL_27;
          v38 = v37 - 1;
          if ( v38 )
          {
            v39 = v38 - 1;
            if ( !v39 )
            {
              v47 = (const wchar_t *)*((_QWORD *)this + 3);
              if ( !v47 )
                goto LABEL_27;
              v22 = CDbCmdTreeNode::AllocAndCopyWString(v47);
LABEL_34:
              *((_QWORD *)v4 + 3) = v22;
              if ( v22 )
                goto LABEL_27;
              goto LABEL_35;
            }
            v40 = v39 - 1;
            if ( !v40 )
              goto LABEL_27;
            v41 = v40 - 125;
            if ( v41 )
            {
              if ( v41 == 1 )
                goto LABEL_45;
              goto LABEL_44;
            }
            if ( !*((_QWORD *)this + 3) )
              goto LABEL_27;
            v42 = CoTaskMemAlloc(0x20u);
            v43 = v42;
            v95 = (unsigned __int64)v42;
            if ( !v42 )
              goto LABEL_35;
            v44 = *((_QWORD *)this + 3);
            v42[1] = 0;
            *v42 = 0;
            CDbByGuid::_Cleanup((CDbByGuid *)v42);
            *((_OWORD *)v43 + 1) = *(_OWORD *)(v44 + 16);
            v45 = *(_QWORD *)(v44 + 8);
            *((_QWORD *)v43 + 1) = v45;
            if ( v45 )
            {
              v46 = CoTaskMemAlloc((unsigned int)v45);
              *(_QWORD *)v43 = v46;
              if ( v46 )
                memcpy_0(v46, *(const void **)v44, *((_QWORD *)v43 + 1));
            }
            goto LABEL_75;
          }
          v48 = (const char *)*((_QWORD *)this + 3);
          if ( !v48 )
            goto LABEL_27;
          v95 = 0;
          v23 = StringCchLengthA(v48, 0xFFFFu, &v95);
          if ( v23 >= 0 )
          {
            v49 = (unsigned int)(v95 + 1);
            v50 = CoTaskMemAlloc(v49);
            v51 = v50;
            if ( v50 )
            {
              v23 = -2147024809;
              if ( v49 )
              {
                if ( v49 > 0x7FFFFFFF )
                {
                  *v50 = 0;
                  goto LABEL_92;
                }
                v52 = 2147483646;
                v53 = (char *)*((_QWORD *)this + 3);
                v54 = v51;
                do
                {
                  if ( !v52 )
                    break;
                  v55 = *v53;
                  if ( !*v53 )
                    break;
                  ++v53;
                  *v54++ = v55;
                  --v52;
                  --v49;
                }
                while ( v49 );
                v56 = v54 - 1;
                if ( v49 )
                  v56 = v54;
                *v56 = 0;
                v57 = v49 == 0 ? 0x8007007A : 0;
              }
              else
              {
                v57 = -2147024809;
              }
              v23 = v57;
              if ( v57 < 0 )
              {
LABEL_92:
                CoTaskMemFree(v51);
                goto LABEL_46;
              }
              *((_QWORD *)v4 + 3) = v51;
            }
            else
            {
              v23 = -2147024882;
            }
            if ( v23 >= 0 )
              goto LABEL_27;
          }
LABEL_46:
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4E7,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\stgvar\\dbcmdbas.cxx",
            (const char *)(unsigned int)v23,
            v93);
        }
        if ( !*((_QWORD *)this + 3) )
          goto LABEL_27;
        v58 = (CDbColId *)CoTaskMemAlloc(0x20u);
        v95 = (unsigned __int64)v58;
        if ( !v58 )
          goto LABEL_35;
        v59 = CDbColId::CDbColId(v58, *((const struct tagDBID **)this + 3));
        if ( !v59 )
          goto LABEL_35;
        if ( !(unsigned int)CDbColId::IsValid(v59) )
        {
          CDbColId::`scalar deleting destructor'(v36, v60);
          goto LABEL_35;
        }
LABEL_58:
        *((_QWORD *)v4 + 3) = v36;
        goto LABEL_27;
      }
      v61 = v8 - 259;
      if ( !v61 )
      {
        if ( !*((_QWORD *)this + 3) )
          goto LABEL_27;
        v43 = CoTaskMemAlloc(0x18u);
        v95 = (unsigned __int64)v43;
        if ( !v43 )
          goto LABEL_35;
        v71 = *((_QWORD *)this + 3);
        *(_OWORD *)v43 = *(_OWORD *)v71;
        *((_QWORD *)v43 + 2) = *(_QWORD *)(v71 + 16);
        *(_QWORD *)v43 = 0;
        if ( *(_QWORD *)v71 )
          *(_QWORD *)v43 = CDbCmdTreeNode::AllocAndCopyWString(*(const wchar_t **)v71);
        if ( !*(_QWORD *)v43 )
        {
          CDbContent::`scalar deleting destructor'((CDbContent *)v43, v70);
          goto LABEL_35;
        }
        goto LABEL_76;
      }
      v62 = v61 - 1;
      if ( !v62 )
      {
        if ( !*((_QWORD *)this + 3) )
          goto LABEL_27;
        v36 = (CDbColId *)CoTaskMemAlloc(8u);
        v95 = (unsigned __int64)v36;
        if ( !v36 )
          goto LABEL_35;
        v69 = (_QWORD *)*((_QWORD *)this + 3);
        *(_DWORD *)v36 = 0;
        *(_QWORD *)v36 = *v69;
        goto LABEL_58;
      }
      v63 = v62 - 1;
      if ( !v63 )
      {
        if ( !*((_QWORD *)this + 3) )
          goto LABEL_27;
        v68 = CoTaskMemAlloc(4u);
        v95 = (unsigned __int64)v68;
        if ( v68 )
        {
          *v68 = **((_DWORD **)this + 3);
          *((_QWORD *)v4 + 3) = v68;
          goto LABEL_27;
        }
        goto LABEL_35;
      }
      v64 = v63 - 2;
      if ( !v64 )
      {
        if ( !*((_QWORD *)this + 3) )
          goto LABEL_27;
        v43 = CoTaskMemAlloc(0x28u);
        v95 = (unsigned __int64)v43;
        if ( v43 )
        {
          v67 = (const struct tagDBPARAMETER *)*((_QWORD *)this + 3);
          *(_OWORD *)v43 = 0;
          *((_OWORD *)v43 + 1) = 0;
          *((_QWORD *)v43 + 4) = 0;
          CDbParameter::Copy((CDbParameter *)v43, v67);
        }
        else
        {
          v43 = 0;
        }
        goto LABEL_75;
      }
      if ( v64 == 1 )
      {
        if ( !*((_QWORD *)this + 3) )
          goto LABEL_27;
        v65 = CoTaskMemAlloc(0x20u);
        v43 = v65;
        v95 = (unsigned __int64)v65;
        if ( v65 )
        {
          v66 = (const struct tagDBPROPSET *)*((_QWORD *)this + 3);
          *v65 = 0;
          v65[1] = 0;
          CDbPropSet::Copy((CDbPropSet *)v65, v66);
        }
        else
        {
          v43 = 0;
        }
        goto LABEL_75;
      }
LABEL_44:
      *((_WORD *)v4 + 1) = 0;
LABEL_45:
      v23 = -2147215870;
      goto LABEL_46;
    }
    if ( (unsigned __int16)v8 > 0x4000u )
      goto LABEL_44;
    if ( (_WORD)v8 == 0x4000 )
      goto LABEL_27;
    if ( (unsigned __int16)v8 > 0x10Fu )
    {
      v81 = v8 - 272;
      if ( !v81 )
        goto LABEL_23;
      v82 = v81 - 1;
      if ( !v82 )
      {
        if ( !*((_QWORD *)this + 3) )
          goto LABEL_27;
        v36 = (CDbColId *)CoTaskMemAlloc(0x14u);
        v95 = (unsigned __int64)v36;
        if ( !v36 )
          goto LABEL_35;
        v92 = *((_QWORD *)this + 3);
        *(_OWORD *)v36 = *(_OWORD *)v92;
        *((_DWORD *)v36 + 4) = *(_DWORD *)(v92 + 16);
        if ( *(int *)v36 >= 0 )
          goto LABEL_58;
        goto LABEL_143;
      }
      v83 = v82 - 1;
      if ( v83 )
      {
        v84 = v83 - 1;
        if ( !v84 )
        {
          if ( !*((_QWORD *)this + 3) )
            goto LABEL_27;
          v43 = CoTaskMemAlloc(0x18u);
          v95 = (unsigned __int64)v43;
          if ( !v43 )
            goto LABEL_35;
          v90 = *((_QWORD *)this + 3);
          *(_OWORD *)v43 = *(_OWORD *)v90;
          *((_QWORD *)v43 + 2) = 0;
          v91 = *(const wchar_t **)(v90 + 16);
          if ( v91 )
            *((_QWORD *)v43 + 2) = CDbCmdTreeNode::AllocAndCopyWString(v91);
          if ( !*((_QWORD *)v43 + 2) )
          {
            CDbContentScope::`scalar deleting destructor'((CDbContentScope *)v43, v89);
            goto LABEL_35;
          }
          goto LABEL_76;
        }
        if ( v84 == 1 )
        {
          if ( !*((_QWORD *)this + 3) )
            goto LABEL_27;
          v85 = CoTaskMemAlloc(0x10u);
          v43 = v85;
          v95 = (unsigned __int64)v85;
          if ( !v85 )
            goto LABEL_35;
          v87 = (const wchar_t **)*((_QWORD *)this + 3);
          *v85 = *(_OWORD *)v87;
          *(_QWORD *)v85 = 0;
          *((_QWORD *)v85 + 1) = 0;
          if ( *v87 )
          {
            v88 = CDbCmdTreeNode::AllocAndCopyWString(*v87);
            *(_QWORD *)v43 = v88;
            if ( v88 )
              *((_QWORD *)v43 + 1) = CDbCmdTreeNode::AllocAndCopyWString(v87[1]);
          }
          if ( !v43 )
            goto LABEL_35;
          if ( !*(_QWORD *)v43 || !*((_QWORD *)v43 + 1) )
          {
            CDbContentTable::`scalar deleting destructor'((CDbContentTable *)v43, v86);
            goto LABEL_35;
          }
          goto LABEL_76;
        }
        goto LABEL_44;
      }
    }
    else
    {
      if ( (_WORD)v8 == 271 )
        goto LABEL_23;
      v72 = v8 - 266;
      if ( v72 )
      {
        v73 = v72 - 1;
        if ( !v73 )
        {
          if ( !*((_QWORD *)this + 3) )
            goto LABEL_27;
          v77 = CoTaskMemAlloc(0x18u);
          v43 = v77;
          v95 = (unsigned __int64)v77;
          if ( !v77 )
            goto LABEL_35;
          v78 = *((_QWORD *)this + 3);
          *v77 = *(_OWORD *)v78;
          *((_QWORD *)v77 + 2) = *(_QWORD *)(v78 + 16);
          *((_QWORD *)v77 + 1) = 0;
          v79 = *(const wchar_t **)(v78 + 8);
          if ( v79 )
            *((_QWORD *)v77 + 1) = CDbCmdTreeNode::AllocAndCopyWString(v79);
LABEL_75:
          if ( !v43 )
            goto LABEL_35;
          goto LABEL_76;
        }
        v74 = v73 - 1;
        if ( !v74 )
        {
          if ( !*((_QWORD *)this + 3) )
            goto LABEL_27;
          v17 = CoTaskMemAlloc(0x18u);
          v95 = (unsigned __int64)v17;
          if ( v17 )
          {
            v76 = *((_QWORD *)this + 3);
            *(_OWORD *)v17 = *(_OWORD *)v76;
            v17[2] = *(_QWORD *)(v76 + 16);
            goto LABEL_26;
          }
          goto LABEL_35;
        }
        v15 = v74 - 1;
        if ( v15 )
          goto LABEL_22;
        if ( !*((_QWORD *)this + 3) )
          goto LABEL_27;
        v43 = CoTaskMemAlloc(0x20u);
        v95 = (unsigned __int64)v43;
        if ( !v43 )
          goto LABEL_35;
        v75 = *((_QWORD *)this + 3);
        *(_OWORD *)v43 = *(_OWORD *)v75;
        *((_OWORD *)v43 + 1) = *(_OWORD *)(v75 + 16);
        *(_QWORD *)v43 = 0;
        if ( *(_QWORD *)v75 )
          *(_QWORD *)v43 = CDbCmdTreeNode::AllocAndCopyWString(*(const wchar_t **)v75);
        if ( *(_QWORD *)v43 )
        {
LABEL_76:
          *((_QWORD *)v4 + 3) = v43;
          goto LABEL_27;
        }
        v36 = (CDbColId *)v43;
LABEL_143:
        CoTaskMemFree(v36);
        goto LABEL_35;
      }
    }
    if ( !*((_QWORD *)this + 3) )
      goto LABEL_27;
    v36 = (CDbColId *)CoTaskMemAlloc(0xCu);
    v95 = (unsigned __int64)v36;
    if ( !v36 )
      goto LABEL_35;
    v80 = *((_QWORD *)this + 3);
    *(_QWORD *)v36 = *(_QWORD *)v80;
    *((_DWORD *)v36 + 2) = *(_DWORD *)(v80 + 8);
    goto LABEL_58;
  }
  if ( v8 == 72 )
  {
    if ( !*((_QWORD *)this + 3) )
      goto LABEL_27;
    v36 = (CDbColId *)CoTaskMemAlloc(0x10u);
    if ( !v36 )
      goto LABEL_35;
    *(_OWORD *)v36 = *(_OWORD *)*((_QWORD *)this + 3);
    goto LABEL_58;
  }
  if ( v8 > 0xA )
  {
    v24 = v8 - 11;
    if ( !v24 )
      goto LABEL_25;
    v25 = v24 - 1;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 3;
        if ( !v27 )
          goto LABEL_25;
        v28 = v27 - 1;
        if ( !v28 )
          goto LABEL_25;
        v29 = v28 - 1;
        if ( !v29 )
          goto LABEL_25;
        v30 = v29 - 1;
        if ( !v30 || v30 - 1 < 2 )
          goto LABEL_25;
        goto LABEL_44;
      }
LABEL_23:
      v16 = *((_QWORD *)this + 3);
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
        goto LABEL_25;
      }
      goto LABEL_27;
    }
    v31 = (const struct CStorageVariant *)*((_QWORD *)this + 3);
    if ( !v31 )
      goto LABEL_27;
    v32 = (CStorageVariant *)CoTaskMemAlloc(0x18u);
    v95 = (unsigned __int64)v32;
    if ( v32 )
      v33 = CStorageVariant::CStorageVariant(v32, v31);
    else
      v33 = 0;
    if ( v33 )
    {
      if ( (unsigned int)CAllocStorageVariant::IsValid(v33) )
      {
        *((_QWORD *)v4 + 3) = v35;
        goto LABEL_27;
      }
      CStorageVariant::`scalar deleting destructor'(v35, v34);
    }
LABEL_35:
    v23 = -2147024882;
    goto LABEL_46;
  }
  if ( v8 == 10 )
  {
LABEL_25:
    v17 = (_QWORD *)*((_QWORD *)this + 3);
LABEL_26:
    *((_QWORD *)v4 + 3) = v17;
    goto LABEL_27;
  }
  if ( *((_WORD *)this + 1) )
  {
    v9 = v8 - 2;
    if ( !v9 )
      goto LABEL_25;
    v10 = v9 - 1;
    if ( !v10 )
      goto LABEL_25;
    v11 = v10 - 1;
    if ( !v11 )
      goto LABEL_25;
    v12 = v11 - 1;
    if ( !v12 )
      goto LABEL_25;
    v13 = v12 - 1;
    if ( !v13 )
      goto LABEL_25;
    v14 = v13 - 1;
    if ( !v14 )
      goto LABEL_25;
    v15 = v14 - 1;
    if ( v15 )
    {
LABEL_22:
      if ( v15 == 1 )
        goto LABEL_23;
      goto LABEL_44;
    }
    v20 = (OLECHAR *)*((_QWORD *)this + 3);
    if ( !v20 )
      goto LABEL_27;
    v21 = SysStringLen(v20);
    v22 = SysAllocStringLen(*((const OLECHAR **)this + 3), v21);
    goto LABEL_34;
  }
LABEL_27:
  v18 = (CDbCmdTreeNode *)*((_QWORD *)this + 1);
  if ( v18 )
    *((_QWORD *)v4 + 1) = CDbCmdTreeNode::Clone(v18, a2);
  v19 = (CDbCmdTreeNode *)*((_QWORD *)this + 2);
  if ( v19 )
    *((_QWORD *)v4 + 2) = CDbCmdTreeNode::Clone(v19, a2);
  return (struct CDbCmdTreeNode *)v4;
}

```

## disassembly

```asm
0x180182364  mov     [rsp+arg_8], rbx
0x180182369  mov     [rsp+arg_18], rbp
0x18018236e  push    rsi
0x18018236f  push    rdi
0x180182370  push    r12
0x180182372  push    r14
0x180182374  push    r15; int
0x180182376  sub     rsp, 20h
0x18018237a  mov     r15d, edx
0x18018237d  mov     rsi, rcx
0x180182380  mov     eax, 3000h
0x180182385  test    [rcx+2], ax
0x180182389  jnz     short loc_1801823D1
0x18018238b  mov     edi, 28h ; '('
0x180182390  mov     ecx, edi; cb
0x180182392  call    WINRT_IMPL_CoTaskMemAlloc
0x180182397  mov     rbx, rax
0x18018239a  mov     [rsp+48h+arg_0], rax
0x18018239f  xor     r12d, r12d
0x1801823a2  test    rax, rax
0x1801823a5  jz      short loc_1801823C4
0x1801823a7  movzx   eax, word ptr [rsi]
0x1801823aa  xorps   xmm0, xmm0
0x1801823ad  xor     ecx, ecx
0x1801823af  movups  xmmword ptr [rbx], xmm0
0x1801823b2  movups  xmmword ptr [rbx+10h], xmm0
0x1801823b6  mov     [rbx+20h], rcx
0x1801823ba  mov     [rbx], ax
0x1801823bd  mov     [rbx+2], r12w
0x1801823c2  jmp     short loc_1801823C7
0x1801823c4  mov     rbx, r12
0x1801823c7  mov     [rsp+48h+arg_10], rbx
0x1801823cc  test    rbx, rbx
0x1801823cf  jnz     short loc_1801823EA
0x1801823d1  xor     eax, eax
0x1801823d3  mov     rbx, [rsp+48h+arg_8]
0x1801823d8  mov     rbp, [rsp+48h+arg_18]
0x1801823dd  add     rsp, 20h
0x1801823e1  pop     r15
0x1801823e3  pop     r14
0x1801823e5  pop     r12
0x1801823e7  pop     rdi
0x1801823e8  pop     rsi
0x1801823e9  retn
0x1801823ea  test    r15d, r15d
0x1801823ed  jz      short loc_1801823F4
0x1801823ef  mov     eax, [rsi+20h]
0x1801823f2  jmp     short loc_1801823F7
0x1801823f4  mov     eax, r12d
0x1801823f7  mov     [rbx+20h], eax
0x1801823fa  movzx   eax, word ptr [rsi+2]
0x1801823fe  mov     [rbx+2], ax
0x180182402  movzx   ecx, word ptr [rsi+2]
0x180182406  cmp     ecx, 48h ; 'H'
0x180182409  ja      loc_1801825C8
0x18018240f  jz      loc_180182593
0x180182415  cmp     ecx, 0Ah
0x180182418  ja      loc_1801824CA
0x18018241e  jz      short loc_180182465
0x180182420  test    ecx, ecx
0x180182422  jz      short loc_18018246D
0x180182424  sub     ecx, 2
0x180182427  jz      short loc_180182465
0x180182429  sub     ecx, 1
0x18018242c  jz      short loc_180182465
0x18018242e  sub     ecx, 1
0x180182431  jz      short loc_180182465
0x180182433  sub     ecx, 1
0x180182436  jz      short loc_180182465
0x180182438  sub     ecx, 1
0x18018243b  jz      short loc_180182465
0x18018243d  sub     ecx, 1
0x180182440  jz      short loc_180182465
0x180182442  sub     ecx, 1
0x180182445  jz      short loc_18018249F
0x180182447  cmp     ecx, 1
0x18018244a  jnz     loc_18018250F
0x180182450  mov     rcx, [rsi+18h]
0x180182454  test    rcx, rcx
0x180182457  jz      short loc_18018246D
0x180182459  mov     rax, [rcx]
0x18018245c  mov     rax, [rax+8]
0x180182460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182465  mov     rax, [rsi+18h]
0x180182469  mov     [rbx+18h], rax
0x18018246d  mov     rcx, [rsi+8]; this
0x180182471  test    rcx, rcx
0x180182474  jz      short loc_180182482
0x180182476  mov     edx, r15d; int
0x180182479  call    ?Clone@CDbCmdTreeNode@@QEBAPEAV1@H@Z; CDbCmdTreeNode::Clone(int)
0x18018247e  mov     [rbx+8], rax
0x180182482  mov     rcx, [rsi+10h]; this
0x180182486  test    rcx, rcx
0x180182489  jz      short loc_180182497
0x18018248b  mov     edx, r15d; int
0x18018248e  call    ?Clone@CDbCmdTreeNode@@QEBAPEAV1@H@Z; CDbCmdTreeNode::Clone(int)
0x180182493  mov     [rbx+10h], rax
0x180182497  mov     rax, rbx
0x18018249a  jmp     loc_1801823D3
0x18018249f  mov     rcx, [rsi+18h]; pbstr
0x1801824a3  test    rcx, rcx
0x1801824a6  jz      short loc_18018246D
0x1801824a8  call    cs:__imp_SysStringLen
0x1801824ae  mov     edx, eax; ui
0x1801824b0  mov     rcx, [rsi+18h]; strIn
0x1801824b4  call    cs:__imp_SysAllocStringLen
0x1801824ba  mov     [rbx+18h], rax
0x1801824be  test    rax, rax
0x1801824c1  jnz     short loc_18018246D
0x1801824c3  mov     edi, 8007000Eh
0x1801824c8  jmp     short loc_180182519
0x1801824ca  sub     ecx, 0Bh
0x1801824cd  jz      short loc_180182465
0x1801824cf  sub     ecx, 1
0x1801824d2  jz      short loc_180182533
0x1801824d4  sub     ecx, 1
0x1801824d7  jz      loc_180182450
0x1801824dd  sub     ecx, 3
0x1801824e0  jz      short loc_180182465
0x1801824e2  sub     ecx, 1
0x1801824e5  jz      loc_180182465
0x1801824eb  sub     ecx, 1
0x1801824ee  jz      loc_180182465
0x1801824f4  sub     ecx, 1
0x1801824f7  jz      loc_180182465
0x1801824fd  sub     ecx, 1
0x180182500  jz      loc_180182465
0x180182506  cmp     ecx, 1
0x180182509  jz      loc_180182465
0x18018250f  mov     [rbx+2], r12w
0x180182514  mov     edi, 80041602h
0x180182519  mov     rcx, [rsp+48h]; this
0x18018251e  mov     r9d, edi; char *
0x180182521  lea     r8, aOnecoreuapBase_108; "onecoreuap\\base\\appmodel\\search\\com"...
0x180182528  mov     edx, 4E7h; void *
0x18018252d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180182533  mov     rdi, [rsi+18h]
0x180182537  test    rdi, rdi
0x18018253a  jz      loc_18018246D
0x180182540  mov     ecx, 18h; cb
0x180182545  call    cs:__imp_CoTaskMemAlloc
0x18018254b  mov     [rsp+48h+arg_0], rax
0x180182550  test    rax, rax
0x180182553  jz      short loc_180182565
0x180182555  mov     rdx, rdi; struct CStorageVariant *
0x180182558  mov     rcx, rax; this
0x18018255b  call    ??0CStorageVariant@@QEAA@AEBV0@@Z; CStorageVariant::CStorageVariant(CStorageVariant const &)
0x180182560  mov     r10, rax
0x180182563  jmp     short loc_180182568
0x180182565  mov     r10, r12
0x180182568  test    r10, r10
0x18018256b  jz      loc_1801824C3
0x180182571  mov     rcx, r10; this
0x180182574  call    ?IsValid@CAllocStorageVariant@@QEBAHXZ; CAllocStorageVariant::IsValid(void)
0x180182579  test    eax, eax
0x18018257b  jz      short loc_180182586
0x18018257d  mov     [rbx+18h], r10
0x180182581  jmp     loc_18018246D
0x180182586  mov     rcx, r10; this
0x180182589  call    ??_GCStorageVariant@@QEAAPEAXI@Z; CStorageVariant::`scalar deleting destructor'(uint)
0x18018258e  jmp     loc_1801824C3
0x180182593  cmp     [rsi+18h], r12
0x180182597  jz      loc_18018246D
0x18018259d  mov     ecx, 10h; cb
0x1801825a2  call    cs:__imp_CoTaskMemAlloc
0x1801825a8  mov     rcx, rax
0x1801825ab  test    rax, rax
0x1801825ae  jz      loc_1801824C3
0x1801825b4  mov     rax, [rsi+18h]
0x1801825b8  movups  xmm0, xmmword ptr [rax]
0x1801825bb  movdqu  xmmword ptr [rcx], xmm0
0x1801825bf  mov     [rbx+18h], rcx
0x1801825c3  jmp     loc_18018246D
0x1801825c8  mov     eax, 109h
0x1801825cd  cmp     ecx, eax
0x1801825cf  ja      loc_180182983
0x1801825d5  jz      loc_18018246D
0x1801825db  mov     eax, 102h
0x1801825e0  cmp     ecx, eax
0x1801825e2  ja      loc_1801827E2
0x1801825e8  jz      loc_180182790
0x1801825ee  sub     ecx, 80h
0x1801825f4  jz      loc_18018246D
0x1801825fa  sub     ecx, 1
0x1801825fd  jz      loc_1801826C0
0x180182603  sub     ecx, 1
0x180182606  jz      loc_1801826A9
0x18018260c  sub     ecx, 1
0x18018260f  jz      loc_18018246D
0x180182615  sub     ecx, 7Dh ; '}'
0x180182618  jz      short loc_180182628
0x18018261a  cmp     ecx, 1
0x18018261d  jnz     loc_18018250F
0x180182623  jmp     loc_180182514
0x180182628  cmp     [rsi+18h], r12
0x18018262c  jz      loc_18018246D
0x180182632  mov     ecx, 20h ; ' '; cb
0x180182637  call    cs:__imp_CoTaskMemAlloc
0x18018263d  mov     rdi, rax
0x180182640  mov     [rsp+48h+arg_0], rax
0x180182645  test    rax, rax
0x180182648  jz      loc_1801824C3
0x18018264e  mov     r14, [rsi+18h]
0x180182652  mov     [rax+8], r12
0x180182656  mov     [rax], r12
0x180182659  mov     rcx, rax; this
0x18018265c  call    ?_Cleanup@CDbByGuid@@AEAAXXZ; CDbByGuid::_Cleanup(void)
0x180182661  movups  xmm0, xmmword ptr [r14+10h]
0x180182666  movdqu  xmmword ptr [rdi+10h], xmm0
0x18018266b  mov     rax, [r14+8]
0x18018266f  mov     [rdi+8], rax
0x180182673  test    rax, rax
0x180182676  jz      short loc_180182697
0x180182678  mov     ecx, eax; cb
0x18018267a  call    cs:__imp_CoTaskMemAlloc
0x180182680  mov     [rdi], rax
0x180182683  test    rax, rax
0x180182686  jz      short loc_180182697
0x180182688  mov     r8, [rdi+8]; Size
0x18018268c  mov     rdx, [r14]; Src
0x18018268f  mov     rcx, rax; void *
0x180182692  call    memcpy_0
0x180182697  test    rdi, rdi
0x18018269a  jz      loc_1801824C3
0x1801826a0  mov     [rbx+18h], rdi
0x1801826a4  jmp     loc_18018246D
0x1801826a9  mov     rcx, [rsi+18h]; Src
0x1801826ad  test    rcx, rcx
0x1801826b0  jz      loc_18018246D
0x1801826b6  call    ?AllocAndCopyWString@CDbCmdTreeNode@@SAPEA_WPEB_W@Z; CDbCmdTreeNode::AllocAndCopyWString(wchar_t const *)
0x1801826bb  jmp     loc_1801824BA
0x1801826c0  mov     rcx, [rsi+18h]; char *
0x1801826c4  test    rcx, rcx
0x1801826c7  jz      loc_18018246D
0x1801826cd  mov     [rsp+48h+arg_0], r12
0x1801826d2  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x1801826d7  mov     edx, 0FFFFh; unsigned __int64
0x1801826dc  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1801826e1  mov     edi, eax
0x1801826e3  test    eax, eax
0x1801826e5  js      loc_180182519
0x1801826eb  mov     eax, dword ptr [rsp+48h+arg_0]
0x1801826ef  inc     eax
0x1801826f1  mov     ebp, eax
0x1801826f3  mov     ecx, eax; cb
0x1801826f5  call    cs:__imp_CoTaskMemAlloc
0x1801826fb  mov     rcx, rax; pv
0x1801826fe  test    rax, rax
0x180182701  jz      short loc_18018277E
0x180182703  mov     edi, 80070057h
0x180182708  test    rbp, rbp
0x18018270b  jz      short loc_18018276C
0x18018270d  cmp     rbp, 7FFFFFFFh
0x180182714  ja      short loc_180182773
0x180182716  mov     eax, 7FFFFFFEh
0x18018271b  mov     r8, [rsi+18h]
0x18018271f  mov     rdx, rcx
0x180182722  test    rax, rax
0x180182725  jz      short loc_180182741
0x180182727  mov     r9b, [r8]
0x18018272a  test    r9b, r9b
0x18018272d  jz      short loc_180182741
0x18018272f  inc     r8
0x180182732  mov     [rdx], r9b
0x180182735  inc     rdx
0x180182738  dec     rax
0x18018273b  sub     rbp, 1
0x18018273f  jnz     short loc_180182722
0x180182741  lea     rax, [rdx-1]
0x180182745  test    rbp, rbp
0x180182748  cmovnz  rax, rdx
0x18018274c  mov     [rax], r12b
0x18018274f  neg     rbp
0x180182752  sbb     eax, eax
0x180182754  not     eax
0x180182756  and     eax, 8007007Ah
0x18018275b  mov     edi, eax
0x18018275d  test    eax, eax
0x18018275f  jns     short loc_180182778
0x180182761  call    cs:__imp_CoTaskMemFree
0x180182767  jmp     loc_180182519
0x18018276c  mov     eax, edi
0x18018276e  test    rbp, rbp
0x180182771  jz      short loc_18018275B
0x180182773  mov     [rcx], r12b
0x180182776  jmp     short loc_180182761
0x180182778  mov     [rbx+18h], rcx
0x18018277c  jmp     short loc_180182783
0x18018277e  mov     edi, 8007000Eh
0x180182783  test    edi, edi
0x180182785  jns     loc_18018246D
0x18018278b  jmp     loc_180182519
0x180182790  cmp     [rsi+18h], r12
0x180182794  jz      loc_18018246D
0x18018279a  mov     ecx, 20h ; ' '; cb
0x18018279f  call    cs:__imp_CoTaskMemAlloc
0x1801827a5  mov     [rsp+48h+arg_0], rax
0x1801827aa  test    rax, rax
0x1801827ad  jz      loc_1801824C3
0x1801827b3  mov     rdx, [rsi+18h]; struct tagDBID *
  ... truncated ...
```
