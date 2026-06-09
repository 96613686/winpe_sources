# UnDecorator::composeDeclaration(DName const &)

- ea: `0x18032defc`
- end: `0x18032ecaf`
- name: `?composeDeclaration@UnDecorator@@CA?AVDName@@AEBV2@@Z`
- size: `3507`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1803300dc`

## callees

- `0x18032d94c`
- `0x18032dbc4`
- `0x18032dbf0`
- `0x18032dc1c`
- `0x18032dc74`
- `0x18032dcb8`
- `0x18032dd38`
- `0x18032defc`
- `0x18032ecb0`
- `0x18032ee84`
- `0x18032f1cc`
- `0x18032f6fc`
- `0x18032f83c`
- `0x180330384`
- `0x180330500`
- `0x1803309bc`
- `0x1803310f8`
- `0x1803311a4`
- `0x180331ebc`
- `0x180331ffc`
- `0x180332030`
- `0x1803331dc`
- `0x180333200`
- `0x18033366c`

## string_xrefs

- `0x18032e980`: ``template static data member constructor helper'`
- `0x18032e9a0`: ``template static data member destructor helper'`

## pseudocode

```c
_DWORD *__fastcall UnDecorator::composeDeclaration(_DWORD *a1, __int64 *a2)
{
  unsigned int v2; // ebx
  __int64 v5; // rdx
  int TypeEncoding; // esi
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  bool v10; // zf
  unsigned int v11; // eax
  int v12; // r14d
  int v13; // r13d
  int v14; // r12d
  int v15; // r13d
  int v16; // ecx
  __int64 BasedType; // rax
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 ExternalDataType; // rax
  BOOL v27; // r15d
  int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rax
  void ***v33; // rcx
  __int64 CallingConvention; // rax
  _DWORD *v35; // r15
  __int64 ReturnType; // rbx
  DName *v37; // rax
  _DWORD *Memory; // rax
  __int64 v39; // rax
  void ***v40; // rcx
  int v41; // eax
  DName *v42; // rax
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // r9
  _BYTE *v53; // rdx
  _QWORD *v54; // rcx
  DName *v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  unsigned int v58; // eax
  __int64 ArgumentTypes; // rax
  __int64 v60; // rbx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rax
  __int64 RestrictionSpec; // rax
  __int64 v65; // rax
  __int64 Noexcept; // rax
  __int64 ThrowTypes; // rax
  __int64 v68; // rax
  __int64 DispatchTarget; // rax
  unsigned int v70; // eax
  __int64 v71; // r8
  __int64 v72; // rbx
  __int64 v73; // rax
  __int64 Scope; // rax
  BOOL v75; // eax
  int v76; // ebx
  int v77; // edx
  char *v78; // rdx
  int v79; // edx
  DName *v80; // rax
  void ***v81; // rcx
  BOOL v82; // ecx
  int v83; // ecx
  int v84; // ebx
  int v85; // eax
  DName *v86; // rax
  DName *v87; // rax
  int v88; // edx
  const char *v89; // rdx
  BOOL v90; // ecx
  BOOL v91; // eax
  BOOL v92; // ecx
  BOOL v93; // eax
  DName *v94; // rax
  DName *v95; // rax
  DName *v96; // rax
  void ***v98; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v99; // [rsp+38h] [rbp-C8h]
  void ***v100; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v101; // [rsp+48h] [rbp-B8h]
  void ***v102; // [rsp+50h] [rbp-B0h] BYREF
  int v103; // [rsp+58h] [rbp-A8h]
  void ***v104; // [rsp+60h] [rbp-A0h] BYREF
  int v105; // [rsp+68h] [rbp-98h]
  _BYTE v106[16]; // [rsp+70h] [rbp-90h] BYREF
  void ***v107; // [rsp+80h] [rbp-80h] BYREF
  int v108; // [rsp+88h] [rbp-78h]
  __int64 v109; // [rsp+90h] [rbp-70h] BYREF
  int v110; // [rsp+98h] [rbp-68h]
  int v111; // [rsp+A0h] [rbp-60h]
  unsigned int v112; // [rsp+A4h] [rbp-5Ch]
  void ***v113; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v114; // [rsp+B0h] [rbp-50h]
  int v115; // [rsp+B8h] [rbp-48h]
  void ***v116; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v117; // [rsp+C8h] [rbp-38h]
  void ***v118; // [rsp+D0h] [rbp-30h] BYREF
  int v119; // [rsp+D8h] [rbp-28h]
  _BYTE v120[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v121[16]; // [rsp+F0h] [rbp-10h] BYREF
  char v122[16]; // [rsp+100h] [rbp+0h] BYREF
  char v123[64]; // [rsp+110h] [rbp+10h] BYREF
  char v124; // [rsp+168h] [rbp+68h] BYREF
  BOOL v125; // [rsp+170h] [rbp+70h]
  BOOL v126; // [rsp+178h] [rbp+78h]

  v2 = 0;
  v99 = 0;
  v115 = (_DWORD)UnDecorator::gName - (_DWORD)UnDecorator::name;
  v98 = 0;
  TypeEncoding = UnDecorator::getTypeEncoding();
  v9 = *a2;
  if ( !*a2 || (v10 = (a2[1] & 0x200) == 0, v111 = 1, v10) )
    v111 = 0;
  switch ( TypeEncoding )
  {
    case 0xFFFF:
      a1[2] = 0;
      *((_BYTE *)a1 + 8) = 2;
      *(_QWORD *)a1 = 0;
      return a1;
    case 0xFFFE:
      v105 = 0;
      v104 = &off_1803FB120;
      DName::operator+(&v104, a1, a2);
      return a1;
    case 0xFFFD:
      *(_QWORD *)a1 = v9;
      v11 = *((_DWORD *)a2 + 2);
LABEL_163:
      a1[2] = v11;
      return a1;
  }
  v12 = TypeEncoding & 0x8000;
  if ( (TypeEncoding & 0x8000) != 0 )
  {
    v13 = 4096;
    v14 = TypeEncoding & 0x1800;
    v125 = v14 == 2048;
    v126 = (TypeEncoding & 0x6000) == 0;
    if ( v14 == 2048 )
      v13 = 1024;
    v15 = TypeEncoding & v13;
    if ( !v15 || (v16 = TypeEncoding & 0x1B00, ((v16 - 4096) & 0xFFFFFCFF) != 0) || v16 == 4864 )
    {
      if ( (TypeEncoding & 0x4000) != 0 )
      {
        if ( ((UnDecorator::disableFlags | (UnDecorator::disableFlags >> 2)) & 2) == 0 )
        {
          BasedType = UnDecorator::getBasedType(&v100);
          v104 = 0;
          v105 = 0;
          v124 = 32;
          v18 = BasedType;
          DName::doPchar((DName *)&v104, &v124, 1);
          DName::operator+(&v104, &v113, v18);
          v2 = v114;
          v98 = v113;
LABEL_21:
          v99 = v2;
          goto LABEL_22;
        }
        v19 = UnDecorator::getBasedType(&v100);
        if ( *(char *)(v19 + 8) > 1 )
        {
          v2 = *(unsigned __int8 *)(v19 + 8);
          goto LABEL_21;
        }
      }
LABEL_22:
      if ( v15 && v14 == 6144 )
      {
        LOBYTE(v7) = 123;
        v20 = DName::operator+(a2, &v109, v7, v8);
        UnDecorator::getDimension(&v100, 0);
        v21 = DName::operator+(v20, &v104, &v100);
        DName::operator+=(&v98, v21);
        if ( *UnDecorator::gName )
        {
          if ( *UnDecorator::gName == 65 )
          {
            ++UnDecorator::gName;
            DName::DName((DName *)&v107, "{flat}");
          }
          else
          {
            v108 = 2;
            v107 = 0;
          }
        }
        else
        {
          v108 = 0;
          v107 = &off_1803FB120;
        }
        if ( (UnDecorator::disableFlags & 0x1000) == 0 )
        {
          v124 = 44;
          v104 = 0;
          v105 = 0;
          DName::doPchar((DName *)&v104, &v124, 1);
          DName::operator+(&v104, &v100, &v107);
          v22 = DName::operator+(&v100, &v109, "}' ");
          DName::operator+=(&v98, v22);
        }
        DName::operator+=((DName *)&v98, "}'");
        UnDecorator::getCallingConvention(&v100);
        if ( (~(UnDecorator::disableFlags >> 1) & 1) != 0
          && (~(UnDecorator::disableFlags >> 4) & 1) != 0
          && (UnDecorator::disableFlags & 0x1000) == 0 )
        {
          v124 = 32;
          v104 = 0;
          v105 = 0;
          DName::doPchar((DName *)&v104, &v124, 1);
          DName::operator+(&v104, &v109, &v100);
          LOBYTE(v23) = 32;
          v25 = DName::operator+(&v109, &v113, v23, v24);
          ExternalDataType = DName::operator+(v25, &v118, &v98);
          v27 = v126;
LABEL_126:
          v81 = *(void ****)ExternalDataType;
          v70 = *(_DWORD *)(ExternalDataType + 8);
          v98 = v81;
          goto LABEL_127;
        }
LABEL_35:
        v27 = v126;
        goto LABEL_128;
      }
      v118 = 0;
      v119 = 0;
      v113 = 0;
      v114 = 0;
      v107 = 0;
      v108 = 0;
      v104 = 0;
      v105 = 0;
      v116 = 0;
      v117 = 0;
      if ( !v15 )
      {
LABEL_43:
        if ( v14 == 2048 && (TypeEncoding & 0x700) != 0x200 )
        {
          v109 = 0;
          v110 = 0;
          if ( (UnDecorator::disableFlags & 0x60) != 0x60 )
          {
            v102 = 0;
            v103 = 0;
            UnDecorator::getDataIndirectType(&v100, &v109, Src, &v102, 1);
            v116 = v100;
            v30 = v101;
LABEL_49:
            v117 = v30;
            goto LABEL_50;
          }
          v100 = 0;
          v101 = 0;
          UnDecorator::getDataIndirectType(&v102, &v109, Src, &v100, 1);
          if ( (char)v103 > 1 )
          {
            v30 = (unsigned __int8)v103;
            goto LABEL_49;
          }
        }
LABEL_50:
        if ( (~(UnDecorator::disableFlags >> 1) & 1) == 0 || (UnDecorator::disableFlags & 0x10) != 0 )
        {
          CallingConvention = UnDecorator::getCallingConvention(&v100);
          v33 = v98;
          if ( (_BYTE)v99 != 3 && *(char *)(CallingConvention + 8) > 1 )
            v99 = *(unsigned __int8 *)(CallingConvention + 8) | v2 & 0xFFFFFF00;
        }
        else
        {
          v31 = UnDecorator::getCallingConvention(&v100);
          v32 = DName::operator+(v31, &v109, &v98);
          v33 = *(void ****)v32;
          LODWORD(v32) = *(_DWORD *)(v32 + 8);
          v98 = v33;
          v99 = v32;
        }
        if ( *a2 )
        {
          if ( !v33 || (UnDecorator::disableFlags & 0x1000) != 0 )
          {
            v98 = (void ***)*a2;
            v99 = *((_DWORD *)a2 + 2);
          }
          else
          {
            v124 = 32;
            v102 = 0;
            v103 = 0;
            DName::doPchar((DName *)&v102, &v124, 1);
            DName::operator+(&v102, &v100, a2);
            DName::operator+=(&v98, &v100);
          }
        }
        v35 = 0;
        v102 = 0;
        v112 = 0;
        if ( v111 )
        {
          ReturnType = UnDecorator::getReturnType(&v109, 0);
          v37 = DName::DName((DName *)v121, " ");
          DName::operator+(v37, &v100, ReturnType);
          DName::operator+=(&v98, &v100);
          if ( (UnDecorator::disableFlags & 0x1000) != 0 )
          {
LABEL_162:
            *(_QWORD *)a1 = v98;
            v11 = v99;
            goto LABEL_163;
          }
        }
        else
        {
          Memory = _HeapManager::getMemory((_HeapManager *)&qword_1804C7190, 0x10u, 0);
          v35 = Memory;
          if ( Memory )
          {
            *(_QWORD *)Memory = 0;
            Memory[2] = 0;
          }
          else
          {
            v35 = 0;
          }
          v39 = UnDecorator::getReturnType(v121, v35);
          v40 = *(void ****)v39;
          LODWORD(v39) = *(_DWORD *)(v39 + 8);
          v102 = v40;
          v112 = v39;
        }
        if ( !v15 )
          goto LABEL_78;
        if ( v14 == 2048 )
        {
          v41 = TypeEncoding & 0x700;
          if ( v41 == 1536 )
          {
            v42 = DName::DName((DName *)v121, "`vtordispex{");
            DName::operator+(v42, &v100, &v118);
            LOBYTE(v43) = 44;
            v45 = DName::operator+(&v100, &v109, v43, v44);
            v46 = DName::operator+(v45, v122, &v113);
            LOBYTE(v47) = 44;
            v49 = DName::operator+(v46, v123, v47, v48);
            v50 = DName::operator+(v49, v120, &v107);
            v53 = v106;
            v54 = (_QWORD *)v50;
LABEL_75:
            LOBYTE(v51) = 44;
            v56 = DName::operator+(v54, v53, v51, v52);
            DName::operator+=(&v98, v56);
LABEL_77:
            v57 = DName::operator+(&v104, v106, "}' ");
            DName::operator+=(&v98, v57);
LABEL_78:
            if ( UnDecorator::m_recursionLevel == 1 )
            {
              v58 = UnDecorator::m_CHPENameOffset;
              if ( !UnDecorator::m_CHPENameOffset )
                v58 = v115;
              UnDecorator::m_CHPENameOffset = v58;
            }
            ArgumentTypes = UnDecorator::getArgumentTypes(v106);
            v124 = 40;
            v104 = 0;
            v105 = 0;
            v60 = ArgumentTypes;
            DName::doPchar((DName *)&v104, &v124, 1);
            DName::operator+(&v104, &v100, v60);
            LOBYTE(v61) = 41;
            v63 = DName::operator+(&v100, v120, v61, v62);
            DName::operator+=(&v98, v63);
            if ( v14 == 2048 && (TypeEncoding & 0x700) != 0x200 )
              DName::operator+=(&v98, &v116);
            if ( (~(UnDecorator::disableFlags >> 19) & 1) != 0 )
            {
              RestrictionSpec = UnDecorator::getRestrictionSpec(v106);
              DName::operator+=(&v98, RestrictionSpec);
            }
            else
            {
              v65 = UnDecorator::getRestrictionSpec(v106);
              if ( (_BYTE)v99 != 3 && *(char *)(v65 + 8) > 1 )
                v99 = *(unsigned __int8 *)(v65 + 8) | v99 & 0xFFFFFF00;
            }
            Noexcept = UnDecorator::getNoexcept(v106);
            DName::operator+=(&v98, Noexcept);
            if ( (~(UnDecorator::disableFlags >> 8) & 1) != 0 )
            {
              ThrowTypes = UnDecorator::getThrowTypes(v106);
              DName::operator+=(&v98, ThrowTypes);
            }
            else
            {
              v68 = UnDecorator::getThrowTypes(v106);
              if ( (_BYTE)v99 != 3 && *(char *)(v68 + 8) > 1 )
                v99 = *(unsigned __int8 *)(v68 + 8) | v99 & 0xFFFFFF00;
            }
            DispatchTarget = UnDecorator::getDispatchTarget(v106);
            if ( (_BYTE)v99 != 3 && *(char *)(DispatchTarget + 8) > 1 )
              v99 = *(unsigned __int8 *)(DispatchTarget + 8) | v99 & 0xFFFFFF00;
            if ( (~(UnDecorator::disableFlags >> 2) & 1) == 0 || !v35 )
              goto LABEL_35;
            *(_QWORD *)v35 = v98;
            v35[2] = v99;
            v27 = v126;
            v98 = v102;
            v70 = v112;
LABEL_127:
            v99 = v70;
LABEL_128:
            v82 = v125;
            if ( (TypeEncoding & 0x8000) != 0 )
              v27 = v125;
            if ( !v27 )
              goto LABEL_157;
            if ( (~(UnDecorator::disableFlags >> 9) & 1) != 0 )
            {
              v83 = 0;
              v84 = TypeEncoding & 0x700;
              v85 = 1;
              if ( (TypeEncoding & 0x8000) != 0 )
              {
                LOBYTE(v83) = v84 == 512;
                v85 = v83;
              }
              if ( v85 )
              {
                v86 = DName::DName((DName *)v106, "static ");
                DName::operator+(v86, &v100, &v98);
                v98 = v100;
                v99 = v101;
              }
              if ( (TypeEncoding & 0x8000) != 0 && v84 == 256
                || ((v27 ? 1024 : 4096) & TypeEncoding) != 0 && ((v84 - 1024) & 0xFFFFFCFF) == 0 && v84 != 1792 )
              {
                v87 = DName::DName((DName *)v106, "virtual ");
                DName::operator+(v87, &v100, &v98);
                v98 = v100;
                v99 = v101;
              }
              v82 = v125;
            }
            if ( (~(UnDecorator::disableFlags >> 7) & 1) == 0 )
              goto LABEL_157;
            v88 = TypeEncoding & 0xC0;
            if ( (TypeEncoding & 0x8000) != 0 )
              v82 = v88 == 64;
            if ( v82 )
            {
              v89 = "private: ";
            }
            else
            {
              v90 = 0;
              v91 = v14 == 4096;
              if ( (TypeEncoding & 0x8000) != 0 )
              {
                LOBYTE(v90) = v88 == 128;
                v91 = v90;
              }
              if ( v91 )
              {
                v89 = "protected: ";
              }
              else
              {
                v92 = 0;
                v93 = v14 == 0;
                if ( (TypeEncoding & 0x8000) != 0 )
                {
                  LOBYTE(v92) = v88 == 0;
                  v93 = v92;
                }
                if ( !v93 )
                  goto LABEL_157;
                v89 = "public: ";
              }
            }
            v94 = DName::DName((DName *)v106, v89);
            DName::operator+(v94, &v100, &v98);
            v98 = v100;
            v99 = v101;
LABEL_157:
            if ( ((v27 ? 1024 : 4096) & TypeEncoding) != 0 && (UnDecorator::disableFlags & 0x1000) == 0 )
            {
              v95 = DName::DName((DName *)v106, "[thunk]:");
              DName::operator+(v95, &v100, &v98);
              v98 = v100;
              v99 = v101;
            }
            if ( (TypeEncoding & 0x10000) != 0 )
            {
              v96 = DName::DName((DName *)v106, "extern \"C\" ");
              DName::operator+(v96, &v100, &v98);
              v98 = v100;
              v99 = v101;
            }
            goto LABEL_162;
          }
          if ( v41 == 1280 )
          {
            v55 = DName::DName((DName *)v106, "`vtordisp{");
            DName::operator+(v55, &v100, &v107);
            v53 = v120;
            v54 = &v100;
            goto LABEL_75;
          }
        }
        DName::operator+=((DName *)&v98, "`adjustor{");
        goto LABEL_77;
      }
      if ( v14 == 2048 )
      {
        v28 = TypeEncoding & 0x700;
        if ( v28 == 1536 )
        {
          LOBYTE(v5) = 1;
          UnDecorator::getDimension(&v102, v5);
          v118 = v102;
          LOBYTE(v29) = 1;
          v119 = v103;
          UnDecorator::getDimension(&v102, v29);
          v113 = v102;
          v114 = v103;
LABEL_41:
          LOBYTE(v5) = 1;
          UnDecorator::getDimension(&v102, v5);
          v107 = v102;
          v108 = v103;
          goto LABEL_42;
        }
        if ( v28 == 1280 )
          goto LABEL_41;
      }
LABEL_42:
      LOBYTE(v5) = 1;
      UnDecorator::getDimension(&v102, v5);
      v104 = v102;
      v105 = v103;
      goto LABEL_43;
    }
  }
  DName::operator+=(&v98, a2);
  if ( (TypeEncoding & 0x8000) == 0 )
  {
    if ( (((TypeEncoding & 0x7C00) - 26624) & 0xFFFFF7FF) == 0 )
    {
      UnDecorator::getVfTableType(a1, &v98, v71, 31744);
      return a1;
    }
    if ( (TypeEncoding & 0x7C00) == 0x6000 )
    {
      LOBYTE(v71) = 123;
      v72 = DName::operator+(&v98, v106, v71, 31744);
      UnDecorator::getDimension(&v100, 0);
      v73 = DName::operator+(v72, v120, &v100);
      DName::operator+(v73, a1, "}'");
      return a1;
    }
  }
  if ( (TypeEncoding & 0xFC00) != 0x7C00 )
  {
    v14 = TypeEncoding & 0x1800;
    v125 = v14 == 2048;
    v27 = (TypeEncoding & 0x6000) == 0;
    v75 = v27;
    if ( (TypeEncoding & 0x8000) != 0 )
      v75 = v14 == 2048;
    v76 = TypeEncoding & (v75 ? 1024 : 4096);
    if ( v76 )
    {
      v77 = TypeEncoding & 0x1B00;
      if ( v12 != 0 && v77 == 4096 )
      {
        v78 = "`local static destructor helper'";
LABEL_118:
        DName::operator+=((DName *)&v98, v78);
LABEL_121:
        if ( !v76 || (v79 = TypeEncoding & 0x1B00, v12 == 0 || v79 != 4352) && (v12 == 0 || v79 != 4608) )
        {
          ExternalDataType = UnDecorator::getExternalDataType(v106, &v98);
          goto LABEL_126;
        }
        v80 = DName::DName((DName *)v106, " ");
        DName::operator+(v80, &v100, &v98);
        v98 = v100;
        v70 = v101;
        goto LABEL_127;
      }
      if ( v12 != 0 && v77 == 4352 )
      {
        v78 = "`template static data member constructor helper'";
        goto LABEL_118;
      }
      if ( v12 != 0 && v77 == 4608 )
      {
        v78 = "`template static data member destructor helper'";
        goto LABEL_118;
      }
    }
    if ( (TypeEncoding & 0x8000) == 0 && (TypeEncoding & 0x7C00) == 0x7800 )
      goto LABEL_162;
    goto LABEL_121;
  }
  *(_QWORD *)a1 = v98;
  a1[2] = v99;
  DName::operator+=((DName *)a1, "{for ");
  Scope = UnDecorator::getScope(v106);
  DName::operator+=(a1, Scope);
  DName::operator+=((DName *)a1);
  if ( *UnDecorator::gName == 64 )
    ++UnDecorator::gName;
  return a1;
}

```

## disassembly

```asm
0x18032defc  mov     [rsp-8+arg_0], rbx
0x18032df01  push    rbp
0x18032df02  push    rsi
0x18032df03  push    rdi
0x18032df04  push    r12
0x18032df06  push    r13
0x18032df08  push    r14
0x18032df0a  push    r15
0x18032df0c  lea     rbp, [rsp-20h]
0x18032df11  sub     rsp, 120h
0x18032df18  mov     eax, dword ptr cs:?gName@UnDecorator@@0PEBDEB
0x18032df1e  xor     r13d, r13d
0x18032df21  sub     eax, dword ptr cs:?name@UnDecorator@@0PEBDEB
0x18032df27  mov     ebx, r13d
0x18032df2a  mov     [rsp+150h+var_118], ebx
0x18032df2e  mov     r15, rdx
0x18032df31  mov     [rbp+50h+var_98], eax
0x18032df34  mov     rdi, rcx
0x18032df37  mov     [rsp+150h+var_120], r13
0x18032df3c  call    ?getTypeEncoding@UnDecorator@@CAHXZ
0x18032df41  mov     esi, eax
0x18032df43  mov     rax, [r15]
0x18032df46  test    rax, rax
0x18032df49  jz      short loc_18032DF5C
0x18032df4b  test    dword ptr [r15+8], 200h
0x18032df53  mov     [rbp+50h+var_B0], 1
0x18032df5a  jnz     short loc_18032DF60
0x18032df5c  mov     [rbp+50h+var_B0], r13d
0x18032df60  cmp     esi, 0FFFFh
0x18032df66  jnz     short loc_18032DF78
0x18032df68  mov     [rdi+8], r13d
0x18032df6c  mov     byte ptr [rdi+8], 2
0x18032df70  mov     [rdi], r13
0x18032df73  jmp     loc_18032EC91
0x18032df78  cmp     esi, 0FFFEh
0x18032df7e  jnz     short loc_18032DFA6
0x18032df80  lea     rax, off_1803FB120
0x18032df87  mov     [rsp+150h+var_E8], r13d
0x18032df8c  mov     r8, r15
0x18032df8f  mov     [rsp+150h+var_F0], rax
0x18032df94  mov     rdx, rdi
0x18032df97  lea     rcx, [rsp+150h+var_F0]
0x18032df9c  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x18032dfa1  jmp     loc_18032EC91
0x18032dfa6  cmp     esi, 0FFFDh
0x18032dfac  jnz     short loc_18032DFBA
0x18032dfae  mov     [rdi], rax
0x18032dfb1  mov     eax, [r15+8]
0x18032dfb5  jmp     loc_18032EC8E
0x18032dfba  mov     r14d, esi
0x18032dfbd  and     r14d, 8000h
0x18032dfc4  jz      loc_18032E808
0x18032dfca  mov     eax, r13d
0x18032dfcd  mov     ecx, r13d
0x18032dfd0  mov     r12d, esi
0x18032dfd3  mov     r13d, 1000h
0x18032dfd9  and     r12d, 1800h
0x18032dfe0  cmp     r12d, 800h
0x18032dfe7  setz    cl
0x18032dfea  test    esi, 6000h
0x18032dff0  mov     [rbp+50h+arg_10], ecx
0x18032dff3  setz    al
0x18032dff6  cmp     r12d, 800h
0x18032dffd  mov     [rbp+50h+arg_18], eax
0x18032e000  mov     eax, 400h
0x18032e005  cmovz   r13d, eax
0x18032e009  and     r13d, esi
0x18032e00c  jz      short loc_18032E02F
0x18032e00e  mov     ecx, esi
0x18032e010  and     ecx, 1B00h
0x18032e016  lea     eax, [rcx-1000h]
0x18032e01c  test    eax, 0FFFFFCFFh
0x18032e021  jnz     short loc_18032E02F
0x18032e023  cmp     ecx, 1300h
0x18032e029  jnz     loc_18032E805
0x18032e02f  bt      esi, 0Eh
0x18032e033  jnb     short loc_18032E0AF
0x18032e035  mov     ecx, cs:?disableFlags@UnDecorator@@0KA
0x18032e03b  shr     ecx, 2
0x18032e03e  or      ecx, cs:?disableFlags@UnDecorator@@0KA
0x18032e044  shr     ecx, 1
0x18032e046  not     ecx
0x18032e048  test    cl, 1
0x18032e04b  lea     rcx, [rsp+150h+var_110]
0x18032e050  jz      short loc_18032E09C
0x18032e052  call    ?getBasedType@UnDecorator@@CA?AVDName@@XZ
0x18032e057  and     [rsp+150h+var_F0], 0
0x18032e05d  lea     rdx, [rbp+50h+arg_8]; char *
0x18032e061  and     [rsp+150h+var_E8], 0
0x18032e066  lea     rcx, [rsp+150h+var_F0]; this
0x18032e06b  mov     r8d, 1; int
0x18032e071  mov     [rbp+50h+arg_8], 20h ; ' '
0x18032e075  mov     rbx, rax
0x18032e078  call    ?doPchar@DName@@AEAAXPEBDH@Z
0x18032e07d  mov     r8, rbx
0x18032e080  lea     rdx, [rbp+50h+var_A8]
0x18032e084  lea     rcx, [rsp+150h+var_F0]
0x18032e089  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x18032e08e  mov     rax, [rbp+50h+var_A8]
0x18032e092  mov     ebx, [rbp+50h+var_A0]
0x18032e095  mov     [rsp+150h+var_120], rax
0x18032e09a  jmp     short loc_18032E0AB
0x18032e09c  call    ?getBasedType@UnDecorator@@CA?AVDName@@XZ
0x18032e0a1  cmp     byte ptr [rax+8], 1
0x18032e0a5  jle     short loc_18032E0AF
0x18032e0a7  movzx   ebx, byte ptr [rax+8]
0x18032e0ab  mov     [rsp+150h+var_118], ebx
0x18032e0af  xor     ecx, ecx
0x18032e0b1  test    r13d, r13d
0x18032e0b4  jz      loc_18032E256
0x18032e0ba  cmp     r12d, 1800h
0x18032e0c1  jnz     loc_18032E256
0x18032e0c7  mov     r8b, 7Bh ; '{'
0x18032e0ca  lea     rdx, [rbp+50h+var_C0]
0x18032e0ce  mov     rcx, r15
0x18032e0d1  call    ??HDName@@QEBA?AV0@D@Z
0x18032e0d6  xor     edx, edx
0x18032e0d8  lea     rcx, [rsp+150h+var_110]
0x18032e0dd  mov     rbx, rax
0x18032e0e0  call    ?getDimension@UnDecorator@@CA?AVDName@@_N@Z
0x18032e0e5  lea     r8, [rsp+150h+var_110]
0x18032e0ea  mov     rcx, rbx
0x18032e0ed  lea     rdx, [rsp+150h+var_F0]
0x18032e0f2  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x18032e0f7  mov     rdx, rax
0x18032e0fa  lea     rcx, [rsp+150h+var_120]
0x18032e0ff  call    ??YDName@@QEAAAEAV0@AEBV0@@Z
0x18032e104  mov     rax, cs:?gName@UnDecorator@@0PEBDEB
0x18032e10b  xor     r13d, r13d
0x18032e10e  cmp     [rax], r13b
0x18032e111  jz      short loc_18032E141
0x18032e113  cmp     byte ptr [rax], 41h ; 'A'
0x18032e116  jz      short loc_18032E125
0x18032e118  mov     [rbp+50h+var_C8], 2
0x18032e11f  mov     [rbp+50h+var_D0], r13
0x18032e123  jmp     short loc_18032E150
0x18032e125  inc     rax
0x18032e128  lea     rdx, aFlat
0x18032e12f  lea     rcx, [rbp+50h+var_D0]; this
0x18032e133  mov     cs:?gName@UnDecorator@@0PEBDEB, rax
0x18032e13a  call    ??0DName@@QEAA@PEBD@Z
0x18032e13f  jmp     short loc_18032E150
0x18032e141  lea     rax, off_1803FB120
0x18032e148  mov     [rbp+50h+var_C8], r13d
0x18032e14c  mov     [rbp+50h+var_D0], rax
0x18032e150  mov     ebx, 1000h
0x18032e155  test    cs:?disableFlags@UnDecorator@@0KA, ebx
0x18032e15b  jnz     short loc_18032E1B4
0x18032e15d  mov     r8d, 1; int
0x18032e163  mov     [rbp+50h+arg_8], 2Ch ; ','
0x18032e167  lea     rdx, [rbp+50h+arg_8]; char *
0x18032e16b  mov     [rsp+150h+var_F0], r13
0x18032e170  lea     rcx, [rsp+150h+var_F0]; this
0x18032e175  mov     [rsp+150h+var_E8], r13d
0x18032e17a  call    ?doPchar@DName@@AEAAXPEBDH@Z
0x18032e17f  lea     r8, [rbp+50h+var_D0]
0x18032e183  lea     rdx, [rsp+150h+var_110]
0x18032e188  lea     rcx, [rsp+150h+var_F0]
0x18032e18d  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x18032e192  lea     r8, asc_1803FAD34
0x18032e199  lea     rdx, [rbp+50h+var_C0]
0x18032e19d  lea     rcx, [rsp+150h+var_110]
0x18032e1a2  call    ??HDName@@QEBA?AV0@PEBD@Z
0x18032e1a7  mov     rdx, rax
0x18032e1aa  lea     rcx, [rsp+150h+var_120]
0x18032e1af  call    ??YDName@@QEAAAEAV0@AEBV0@@Z
0x18032e1b4  lea     rdx, asc_1803FAD38
0x18032e1bb  lea     rcx, [rsp+150h+var_120]; this
0x18032e1c0  call    ??YDName@@QEAAAEAV0@PEBD@Z
0x18032e1c5  lea     rcx, [rsp+150h+var_110]
0x18032e1ca  call    ?getCallingConvention@UnDecorator@@CA?AVDName@@XZ
0x18032e1cf  mov     ecx, cs:?disableFlags@UnDecorator@@0KA
0x18032e1d5  mov     eax, ecx
0x18032e1d7  shr     eax, 1
0x18032e1d9  not     eax
0x18032e1db  test    al, 1
0x18032e1dd  jz      short loc_18032E24D
0x18032e1df  mov     eax, ecx
0x18032e1e1  shr     eax, 4
0x18032e1e4  not     eax
0x18032e1e6  test    al, 1
0x18032e1e8  jz      short loc_18032E24D
0x18032e1ea  test    ebx, ecx
0x18032e1ec  jnz     short loc_18032E24D
0x18032e1ee  mov     r8d, 1; int
0x18032e1f4  mov     [rbp+50h+arg_8], 20h ; ' '
0x18032e1f8  lea     rdx, [rbp+50h+arg_8]; char *
0x18032e1fc  mov     [rsp+150h+var_F0], r13
0x18032e201  lea     rcx, [rsp+150h+var_F0]; this
0x18032e206  mov     [rsp+150h+var_E8], r13d
0x18032e20b  call    ?doPchar@DName@@AEAAXPEBDH@Z
0x18032e210  lea     r8, [rsp+150h+var_110]
0x18032e215  lea     rdx, [rbp+50h+var_C0]
0x18032e219  lea     rcx, [rsp+150h+var_F0]
0x18032e21e  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x18032e223  mov     r8b, 20h ; ' '
0x18032e226  lea     rdx, [rbp+50h+var_A8]
0x18032e22a  lea     rcx, [rbp+50h+var_C0]
0x18032e22e  call    ??HDName@@QEBA?AV0@D@Z
0x18032e233  lea     r8, [rsp+150h+var_120]
0x18032e238  mov     rcx, rax
0x18032e23b  lea     rdx, [rbp+50h+var_80]
0x18032e23f  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x18032e244  mov     r15d, [rbp+50h+arg_18]
0x18032e248  jmp     loc_18032EA44
0x18032e24d  mov     r15d, [rbp+50h+arg_18]
0x18032e251  jmp     loc_18032EA53
0x18032e256  mov     [rbp+50h+var_80], rcx
0x18032e25a  mov     [rbp+50h+var_78], ecx
0x18032e25d  mov     [rbp+50h+var_A8], rcx
0x18032e261  mov     [rbp+50h+var_A0], ecx
0x18032e264  mov     [rbp+50h+var_D0], rcx
0x18032e268  mov     [rbp+50h+var_C8], ecx
0x18032e26b  mov     [rsp+150h+var_F0], rcx
0x18032e270  mov     [rsp+150h+var_E8], ecx
0x18032e274  mov     [rbp+50h+var_90], rcx
0x18032e278  mov     [rbp+50h+var_88], ecx
0x18032e27b  test    r13d, r13d
0x18032e27e  jz      loc_18032E318
0x18032e284  cmp     r12d, 800h
0x18032e28b  jnz     short loc_18032E2F8
0x18032e28d  mov     eax, esi
0x18032e28f  and     eax, 700h
0x18032e294  cmp     eax, 600h
0x18032e299  jnz     short loc_18032E2D5
0x18032e29b  mov     dl, 1
0x18032e29d  lea     rcx, [rsp+150h+var_100]
0x18032e2a2  call    ?getDimension@UnDecorator@@CA?AVDName@@_N@Z
0x18032e2a7  mov     rax, [rsp+150h+var_100]
0x18032e2ac  lea     rcx, [rsp+150h+var_100]
0x18032e2b1  mov     [rbp+50h+var_80], rax
0x18032e2b5  mov     dl, 1
0x18032e2b7  mov     eax, [rsp+150h+var_F8]
0x18032e2bb  mov     [rbp+50h+var_78], eax
0x18032e2be  call    ?getDimension@UnDecorator@@CA?AVDName@@_N@Z
0x18032e2c3  mov     rax, [rsp+150h+var_100]
0x18032e2c8  mov     [rbp+50h+var_A8], rax
0x18032e2cc  mov     eax, [rsp+150h+var_F8]
0x18032e2d0  mov     [rbp+50h+var_A0], eax
0x18032e2d3  jmp     short loc_18032E2DC
0x18032e2d5  cmp     eax, 500h
0x18032e2da  jnz     short loc_18032E2F8
0x18032e2dc  mov     dl, 1
0x18032e2de  lea     rcx, [rsp+150h+var_100]
0x18032e2e3  call    ?getDimension@UnDecorator@@CA?AVDName@@_N@Z
0x18032e2e8  mov     rax, [rsp+150h+var_100]
0x18032e2ed  mov     [rbp+50h+var_D0], rax
0x18032e2f1  mov     eax, [rsp+150h+var_F8]
0x18032e2f5  mov     [rbp+50h+var_C8], eax
0x18032e2f8  mov     dl, 1
0x18032e2fa  lea     rcx, [rsp+150h+var_100]
0x18032e2ff  call    ?getDimension@UnDecorator@@CA?AVDName@@_N@Z
0x18032e304  mov     rax, [rsp+150h+var_100]
0x18032e309  xor     ecx, ecx
0x18032e30b  mov     [rsp+150h+var_F0], rax
0x18032e310  mov     eax, [rsp+150h+var_F8]
0x18032e314  mov     [rsp+150h+var_E8], eax
0x18032e318  cmp     r12d, 800h
0x18032e31f  jnz     loc_18032E3A8
0x18032e325  mov     eax, esi
0x18032e327  and     eax, 700h
0x18032e32c  cmp     eax, 200h
0x18032e331  jz      short loc_18032E3A8
0x18032e333  mov     eax, cs:?disableFlags@UnDecorator@@0KA
0x18032e339  lea     r8, Src
0x18032e340  and     eax, 60h
0x18032e343  mov     [rbp+50h+var_C0], rcx
0x18032e347  mov     [rbp+50h+var_B8], ecx
0x18032e34a  lea     rdx, [rbp+50h+var_C0]
0x18032e34e  mov     [rsp+150h+var_130], 1
0x18032e356  cmp     al, 60h ; '`'
0x18032e358  jz      short loc_18032E381
0x18032e35a  mov     [rsp+150h+var_100], rcx
0x18032e35f  lea     r9, [rsp+150h+var_100]
0x18032e364  mov     [rsp+150h+var_F8], ecx
0x18032e368  lea     rcx, [rsp+150h+var_110]
0x18032e36d  call    ?getDataIndirectType@UnDecorator@@CA?AVDName@@AEBV2@PEBD0H@Z
0x18032e372  mov     rax, [rsp+150h+var_110]
0x18032e377  mov     [rbp+50h+var_90], rax
0x18032e37b  mov     eax, [rsp+150h+var_108]
0x18032e37f  jmp     short loc_18032E3A5
0x18032e381  mov     [rsp+150h+var_110], rcx
0x18032e386  lea     r9, [rsp+150h+var_110]
0x18032e38b  mov     [rsp+150h+var_108], ecx
0x18032e38f  lea     rcx, [rsp+150h+var_100]
0x18032e394  call    ?getDataIndirectType@UnDecorator@@CA?AVDName@@AEBV2@PEBD0H@Z
0x18032e399  cmp     byte ptr [rsp+150h+var_F8], 1
0x18032e39e  jle     short loc_18032E3A8
0x18032e3a0  movzx   eax, byte ptr [rsp+150h+var_F8]
0x18032e3a5  mov     [rbp+50h+var_88], eax
0x18032e3a8  mov     ecx, cs:?disableFlags@UnDecorator@@0KA
0x18032e3ae  mov     eax, ecx
0x18032e3b0  shr     eax, 1
0x18032e3b2  not     eax
0x18032e3b4  test    al, 1
0x18032e3b6  jz      loc_18032E485
0x18032e3bc  shr     ecx, 4
0x18032e3bf  not     ecx
0x18032e3c1  test    cl, 1
0x18032e3c4  lea     rcx, [rsp+150h+var_110]
  ... truncated ...
```
