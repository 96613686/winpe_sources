# UnDecorator::composeDeclaration(DName const &)

- ea: `0x1801fe248`
- end: `0x1801ff459`
- name: `?composeDeclaration@UnDecorator@@AEAA?AVDName@@AEBV2@@Z`
- size: `4625`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18020121c`

## callees

- `0x1801fd834`
- `0x1801fdab4`
- `0x1801fdaf0`
- `0x1801fdba4`
- `0x1801fde38`
- `0x1801fdec4`
- `0x1801fdef8`
- `0x1801fdf2c`
- `0x1801fe00c`
- `0x1801fe248`
- `0x1801ff700`
- `0x1801ffc80`
- `0x1802004d8`
- `0x180200618`
- `0x180201558`
- `0x1802016c0`
- `0x180201d4c`
- `0x1802026a0`
- `0x180202730`
- `0x180203b50`
- `0x180203db0`
- `0x1802053e8`
- `0x180205414`
- `0x180205a0c`
- `0x180205c64`
- `0x180205cfc`

## string_xrefs

- `0x1801fef65`: ``template static data member constructor helper'`
- `0x1801ff008`: ``template static data member destructor helper'`

## pseudocode

```c
__int64 __fastcall UnDecorator::composeDeclaration(_DWORD *a1, __int64 a2, __int64 a3)
{
  const char *v3; // r13
  unsigned int v4; // ebx
  int TypeEncoding; // eax
  BOOL v9; // r15d
  int v10; // edi
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // ecx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rbx
  DName *v17; // rax
  __int64 BasedType; // rax
  int v19; // ecx
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r8
  _BYTE *v25; // rbx
  DName *v26; // rax
  __int64 v27; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  _QWORD *MemoryWithBuffer; // rdx
  DName *v31; // rax
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 ExternalDataType; // rax
  unsigned int v35; // ebx
  int v36; // ecx
  __int64 v37; // r8
  char v38; // al
  unsigned int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  _DWORD *v43; // rax
  __int64 CallingConvention; // rax
  __int64 v45; // r8
  unsigned int v46; // ebx
  DName *v47; // rax
  __int64 v48; // r8
  __int64 v49; // r9
  char v50; // bl
  unsigned int v51; // eax
  const char **v52; // r14
  __int64 v53; // rbx
  DName *v54; // rax
  __int64 v55; // r8
  __int64 v56; // r9
  const char **v57; // rax
  __int64 ReturnType; // rax
  const char *v59; // rcx
  int v60; // ecx
  DName *v61; // rax
  __int64 v62; // r8
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // r8
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // r8
  _BYTE *v69; // rdx
  _QWORD *v70; // rcx
  DName *v71; // rax
  __int64 v72; // rax
  __int64 v73; // r8
  __int64 v74; // r9
  _DWORD *v75; // rax
  _DWORD *v76; // rdx
  __int64 v77; // rax
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 ArgumentTypes; // rbx
  DName *v81; // rax
  __int64 v82; // r8
  __int64 v83; // rax
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 v88; // rax
  __int64 v89; // r8
  __int64 v90; // r9
  __int64 RestrictionSpec; // rax
  int v92; // eax
  __int64 Noexcept; // rax
  __int64 v94; // r8
  __int64 v95; // r9
  __int64 v96; // rax
  __int64 v97; // r8
  __int64 v98; // r9
  char v99; // r13
  __int64 ThrowTypes; // rax
  __int64 DispatchTarget; // rax
  const char *v102; // rax
  __int64 v103; // r8
  __int64 v104; // rbx
  __int64 v105; // rax
  BOOL v106; // eax
  int v107; // edx
  _QWORD *v108; // rdx
  const char *v109; // rbx
  int v110; // r14d
  _QWORD *v111; // rdx
  struct UnDecorator *v112; // r14
  BOOL v113; // eax
  int v114; // edx
  DName *v115; // rax
  BOOL v116; // eax
  DName *v117; // rax
  DName *v118; // rax
  BOOL v119; // ecx
  const char *v120; // rax
  BOOL v121; // ecx
  BOOL v122; // eax
  DName *v123; // rax
  BOOL v124; // eax
  DName *v125; // rax
  DName *v126; // rax
  const char *v128; // [rsp+30h] [rbp-D0h] BYREF
  struct UnDecorator *v129; // [rsp+38h] [rbp-C8h]
  unsigned int v130; // [rsp+40h] [rbp-C0h]
  const char *v131; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v132; // [rsp+58h] [rbp-A8h]
  unsigned int v133; // [rsp+60h] [rbp-A0h]
  _QWORD v134[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v135; // [rsp+80h] [rbp-80h]
  const char *v136; // [rsp+90h] [rbp-70h] BYREF
  _DWORD *v137; // [rsp+98h] [rbp-68h]
  int v138; // [rsp+A0h] [rbp-60h]
  _BYTE v139[24]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v140; // [rsp+C8h] [rbp-38h] BYREF
  struct UnDecorator *v141; // [rsp+D0h] [rbp-30h]
  unsigned int v142; // [rsp+D8h] [rbp-28h]
  _QWORD v143[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v144; // [rsp+F0h] [rbp-10h]
  _QWORD v145[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v146; // [rsp+108h] [rbp+8h]
  _QWORD v147[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v148; // [rsp+120h] [rbp+20h]
  _QWORD v149[2]; // [rsp+128h] [rbp+28h] BYREF
  unsigned int v150; // [rsp+138h] [rbp+38h]
  _BYTE v151[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v152[24]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v153[24]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v154[24]; // [rsp+188h] [rbp+88h] BYREF
  char v155[80]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v156; // [rsp+200h] [rbp+100h]
  unsigned int v157; // [rsp+200h] [rbp+100h]
  unsigned int v158; // [rsp+200h] [rbp+100h]
  int v159; // [rsp+210h] [rbp+110h]
  int v160; // [rsp+218h] [rbp+118h]

  v3 = 0;
  v4 = 0;
  v160 = a1[64] - a1[66];
  v129 = (struct UnDecorator *)a1;
  v128 = 0;
  v130 = 0;
  TypeEncoding = UnDecorator::getTypeEncoding((UnDecorator *)a1);
  v9 = 1;
  v10 = TypeEncoding;
  if ( !*(_QWORD *)a3 || (v159 = 1, (*(_DWORD *)(a3 + 16) & 0x200) == 0) )
    v159 = 0;
  if ( TypeEncoding != 0xFFFF )
  {
    if ( TypeEncoding == 65534 )
    {
      v11 = DName::DName(v134, *(_QWORD *)(a3 + 8), 1);
      DName::operator+(v11, a2, a3);
      return a2;
    }
    if ( TypeEncoding == 65533 )
    {
      *(_QWORD *)(a2 + 8) = *(_QWORD *)(a3 + 8);
      *(_QWORD *)a2 = *(_QWORD *)a3;
      *(_DWORD *)(a2 + 16) = *(_DWORD *)(a3 + 16);
      return a2;
    }
    v12 = 6144;
    v156 = TypeEncoding & 0x8000;
    if ( (TypeEncoding & 0x8000) != 0 )
    {
      v13 = 4096;
      if ( (TypeEncoding & 0x1800) == 0x800 )
        v13 = 1024;
      if ( (v13 & TypeEncoding) == 0 || (v14 = TypeEncoding & 0x1B00, v14 != 4096) && ((v14 - 4352) & 0xFFFFFEFF) != 0 )
      {
        if ( (v10 & 0x4000) == 0 )
          goto LABEL_24;
        v15 = a1[68];
        if ( (v15 & 2) != 0 || (v15 & 8) != 0 )
        {
          BasedType = UnDecorator::getBasedType(a1, v134, 6144, 1024);
          if ( *(char *)(BasedType + 16) <= 1 )
          {
LABEL_23:
            v12 = 6144;
LABEL_24:
            v19 = 4096;
            if ( (v10 & 0x1800) == 0x800 )
              v19 = 1024;
            if ( (v19 & v10) != 0 && (v10 & 0x1800) == 0x1800 )
            {
              LOBYTE(v12) = 123;
              v20 = DName::operator+(a3, &v140, v12);
              UnDecorator::getDimension(a1, v134, 0);
              v21 = DName::operator+(v20, v143, v134);
              DName::operator+=(&v128, v21, v22, v23);
              UnDecorator::getVCallThunkType(a1, &v140);
              v25 = a1 + 68;
              if ( (a1[68] & 0x1000) == 0 )
              {
                v26 = DName::DName((DName *)v143, v141, 44);
                DName::operator+(v26, v134, &v140);
                LODWORD(v132) = 3;
                v131 = "}' ";
                v27 = DName::operator+(v134, v149, &v131);
                DName::operator+=(&v128, v27, v28, v29);
              }
              LODWORD(v132) = 2;
              v131 = "}'";
              if ( (char)v130 <= 1 )
              {
                if ( v128 )
                {
                  MemoryWithBuffer = _HeapManager::getMemoryWithBuffer(
                                       (struct UnDecorator *)((char *)v129 + 216),
                                       0x18u);
                  if ( MemoryWithBuffer )
                  {
                    MemoryWithBuffer[1] = "}'";
                    *MemoryWithBuffer = &pcharNode::`vftable';
                    *((_DWORD *)MemoryWithBuffer + 4) = 2;
                  }
                  else
                  {
                    MemoryWithBuffer = 0;
                  }
                  DName::append<pcharNode>(&v128, MemoryWithBuffer);
                  v25 = a1 + 68;
                }
                else
                {
                  DName::operator=(&v128, &v131, v24);
                }
              }
              UnDecorator::getCallingConvention(a1, &v140, v24);
              if ( (*v25 & 0x12) != 0 || (*(_DWORD *)v25 & 0x1000) != 0 )
              {
                if ( (_BYTE)v130 == 3 || (char)v142 <= 1 )
                {
                  v35 = v130;
LABEL_165:
                  v112 = v129;
LABEL_166:
                  v116 = (v10 & 0x6000) == 0;
                  if ( (v10 & 0x8000) != 0 )
                    v116 = (v10 & 0x1800) == 2048;
                  if ( !v116 )
                    goto LABEL_195;
                  if ( (a1[68] & 0x200) == 0 )
                  {
                    if ( (v10 & 0x8000) != 0 )
                      v9 = (v10 & 0x700) == 512;
                    if ( v9 )
                    {
                      LODWORD(v132) = 7;
                      v131 = "static ";
                      v117 = DName::DName((DName *)v139, v112, (const struct StringLiteral *)&v131);
                      DName::operator+(v117, v134, &v128);
                      v35 = v135;
                      v128 = (const char *)v134[0];
                      v130 = v135;
                    }
                    if ( (v10 & 0x8000) != 0 && (v10 & 0x700) == 0x100
                      || (v10 & 0x400) != 0
                      && ((v10 & 0x700) == 0x500 || (v10 & 0x700) == 0x600 || (v10 & 0x700) == 0x400) )
                    {
                      LODWORD(v132) = 8;
                      v131 = "virtual ";
                      v118 = DName::DName((DName *)v139, v112, (const struct StringLiteral *)&v131);
                      DName::operator+(v118, v134, &v128);
                      v35 = v135;
                      v128 = (const char *)v134[0];
                      v130 = v135;
                    }
                  }
                  if ( *((char *)a1 + 272) < 0 )
                    goto LABEL_195;
                  v119 = (v10 & 0x1800) == 2048;
                  if ( (v10 & 0x8000) != 0 )
                    v119 = (v10 & 0xC0) == 64;
                  if ( v119 )
                  {
                    v120 = "private: ";
                    LODWORD(v132) = 9;
                  }
                  else
                  {
                    v121 = (v10 & 0x1800) == 4096;
                    if ( (v10 & 0x8000) != 0 )
                      v121 = (v10 & 0xC0) == 0x80;
                    if ( v121 )
                    {
                      v120 = "protected: ";
                      LODWORD(v132) = 11;
                    }
                    else
                    {
                      v122 = (v10 & 0x1800) == 0;
                      if ( (v10 & 0x8000) != 0 )
                        v122 = (v10 & 0xC0) == 0;
                      if ( !v122 )
                        goto LABEL_195;
                      v120 = "public: ";
                      LODWORD(v132) = 8;
                    }
                  }
                  v131 = v120;
                  v123 = DName::DName((DName *)v139, v112, (const struct StringLiteral *)&v131);
                  DName::operator+(v123, v134, &v128);
                  v35 = v135;
                  v128 = (const char *)v134[0];
                  v130 = v135;
LABEL_195:
                  v124 = (v10 & 0x6000) == 0;
                  if ( (v10 & 0x8000) != 0 )
                    v124 = (v10 & 0x1800) == 2048;
                  if ( ((v124 ? 1024 : 4096) & v10) != 0 && (a1[68] & 0x1000) == 0 )
                  {
                    LODWORD(v132) = 8;
                    v131 = "[thunk]:";
                    v125 = DName::DName((DName *)v139, v112, (const struct StringLiteral *)&v131);
                    DName::operator+(v125, v134, &v128);
                    v35 = v135;
                    v128 = (const char *)v134[0];
                    v130 = v135;
                  }
                  if ( (v10 & 0x10000) != 0 )
                  {
                    LODWORD(v132) = 11;
                    v131 = "extern \"C\" ";
                    v126 = DName::DName((DName *)v139, v112, (const struct StringLiteral *)&v131);
                    DName::operator+(v126, v134, &v128);
                    v35 = v135;
                    v128 = (const char *)v134[0];
                  }
                  goto LABEL_202;
                }
                v35 = (unsigned __int8)v142 | v130 & 0xFFFFFF00;
                v128 = 0;
LABEL_164:
                v130 = v35;
                goto LABEL_165;
              }
              v31 = DName::DName((DName *)v143, v141, 32);
              DName::operator+(v31, v134, &v140);
              LOBYTE(v32) = 32;
              v33 = DName::operator+(v134, v149, v32);
              ExternalDataType = DName::operator+(v33, v147, &v128);
LABEL_163:
              v35 = *(_DWORD *)(ExternalDataType + 16);
              v128 = *(const char **)ExternalDataType;
              goto LABEL_164;
            }
            v149[1] = a1;
            v149[0] = 0;
            v150 = 0;
            v36 = 4096;
            v143[1] = a1;
            if ( (v10 & 0x1800) == 0x800 )
              v36 = 1024;
            v143[0] = 0;
            v144 = 0;
            v145[1] = a1;
            v145[0] = 0;
            v146 = 0;
            v141 = (struct UnDecorator *)a1;
            v140 = 0;
            v142 = 0;
            v147[1] = a1;
            v147[0] = 0;
            v148 = 0;
            if ( (v36 & v10) == 0 )
            {
LABEL_53:
              if ( (v10 & 0x1800) == 0x800 && (v10 & 0x700) != 0x200 )
              {
                v38 = a1[68] & 0x60;
                v131 = 0;
                v133 = 0;
                v136 = 0;
                v138 = 0;
                v132 = a1;
                v137 = a1;
                if ( v38 == 96 )
                {
                  UnDecorator::getDataIndirectType(a1, v134, &v136, 0, &v131, 1);
                  if ( (char)v135 <= 1 )
                    goto LABEL_60;
                  v39 = (unsigned __int8)v135;
                }
                else
                {
                  UnDecorator::getDataIndirectType(a1, v134, &v136, 0, &v131, 1);
                  v147[0] = v134[0];
                  v39 = v135;
                }
                v148 = v39;
              }
LABEL_60:
              if ( (a1[68] & 2) != 0 )
              {
                CallingConvention = UnDecorator::getCallingConvention(a1, v134, v12);
                v136 = (const char *)(a1 + 68);
                v45 = CallingConvention;
                LOBYTE(v157) = v4;
                v43 = a1 + 68;
                if ( (_BYTE)v4 != 3 )
                {
                  v136 = (const char *)(a1 + 68);
                  if ( *(char *)(v45 + 16) > 1 )
                  {
                    v46 = *(unsigned __int8 *)(v45 + 16) | v4 & 0xFFFFFF00;
                    v136 = (const char *)(a1 + 68);
                    v3 = 0;
                    v130 = v46;
                    v128 = 0;
                    LOBYTE(v157) = v46;
                    v43 = a1 + 68;
                  }
                }
                goto LABEL_71;
              }
              if ( (a1[68] & 0x10) != 0 )
              {
                v42 = UnDecorator::getCallingConvention(a1, v134, v12);
                LOBYTE(v157) = v4;
                if ( (_BYTE)v4 == 3 || *(char *)(v42 + 16) <= 1 )
                  goto LABEL_67;
                v130 = *(unsigned __int8 *)(v42 + 16) | v4 & 0xFFFFFF00;
                LOBYTE(v157) = v130;
                v3 = 0;
              }
              else
              {
                v40 = UnDecorator::getCallingConvention(a1, v134, v12);
                v41 = DName::operator+(v40, &v131, &v128);
                v3 = *(const char **)v41;
                v157 = *(_DWORD *)(v41 + 16);
                v130 = v157;
              }
              v128 = v3;
LABEL_67:
              v43 = a1 + 68;
              v136 = (const char *)(a1 + 68);
LABEL_71:
              if ( *(_QWORD *)a3 )
              {
                if ( !v3 || (*v43 & 0x1000) != 0 )
                {
                  v51 = *(_DWORD *)(a3 + 16);
                  v50 = v51;
                  v3 = *(const char **)a3;
                  v128 = *(const char **)a3;
                  v130 = v51;
                }
                else
                {
                  v47 = DName::DName((DName *)&v131, *(struct UnDecorator **)(a3 + 8), 32);
                  DName::operator+(v47, v134, a3);
                  DName::operator+=(&v128, v134, v48, v49);
                  v50 = v130;
                  v3 = v128;
                }
              }
              else
              {
                v50 = v157;
              }
              v52 = 0;
              v131 = 0;
              v158 = 0;
              if ( !v159 )
              {
                v57 = (const char **)_HeapManager::getMemoryWithBuffer((_HeapManager *)(a1 + 54), 0x18u);
                v52 = v57;
                if ( v57 )
                {
                  v57[1] = (const char *)a1;
                  *v57 = 0;
                  *((_DWORD *)v57 + 4) = 0;
                }
                else
                {
                  v52 = 0;
                }
                ReturnType = UnDecorator::getReturnType(a1, v152, v52);
                v59 = *(const char **)ReturnType;
                LODWORD(ReturnType) = *(_DWORD *)(ReturnType + 16);
                v131 = v59;
                v158 = ReturnType;
LABEL_84:
                v60 = 4096;
                if ( (v10 & 0x1800) == 0x800 )
                  v60 = 1024;
                if ( (v60 & v10) == 0 )
                  goto LABEL_101;
                if ( (v10 & 0x1800) == 0x800 )
                {
                  if ( (v10 & 0x700) == 0x600 )
                  {
                    LODWORD(v137) = 12;
                    v136 = "`vtordispex{";
                    v61 = DName::DName((DName *)v152, (struct UnDecorator *)a1, (const struct StringLiteral *)&v136);
                    DName::operator+(v61, v134, v149);
                    LOBYTE(v62) = 44;
                    v63 = DName::operator+(v134, v153, v62);
                    v64 = DName::operator+(v63, v155, v143);
                    LOBYTE(v65) = 44;
                    v66 = DName::operator+(v64, v154, v65);
                    v67 = DName::operator+(v66, v151, v145);
                    v69 = v139;
                    v70 = (_QWORD *)v67;
LABEL_92:
                    LOBYTE(v68) = 44;
                    v72 = DName::operator+(v70, v69, v68);
                    DName::operator+=(&v128, v72, v73, v74);
LABEL_100:
                    LODWORD(v137) = 3;
                    v136 = "}' ";
                    v77 = DName::operator+(&v140, v139, &v136);
                    DName::operator+=(&v128, v77, v78, v79);
LABEL_101:
                    if ( *((_QWORD *)a1 + 36) == 0x100000000LL )
                      a1[72] = v160;
                    ArgumentTypes = UnDecorator::getArgumentTypes(a1, v139);
                    v81 = DName::DName((DName *)v151, *(struct UnDecorator **)(ArgumentTypes + 8), 40);
                    DName::operator+(v81, v134, ArgumentTypes);
                    LOBYTE(v82) = 41;
                    v83 = DName::operator+(v134, v154, v82);
                    DName::operator+=(&v128, v83, v84, v85);
                    if ( (v10 & 0x1800) == 0x800 && (v10 & 0x700) != 0x200 )
                      DName::operator+=(&v128, v147, v86, v87);
                    if ( (a1[68] & 0x80000) != 0 )
                    {
                      RestrictionSpec = UnDecorator::getRestrictionSpec(a1, v139);
                      if ( (_BYTE)v130 != 3 && *(char *)(RestrictionSpec + 16) > 1 )
                      {
                        v92 = *(unsigned __int8 *)(RestrictionSpec + 16);
                        v128 = 0;
                        v130 = v92 | v130 & 0xFFFFFF00;
                      }
                    }
                    else
                    {
                      v88 = UnDecorator::getRestrictionSpec(a1, v139);
                      DName::operator+=(&v128, v88, v89, v90);
                    }
                    Noexcept = UnDecorator::getNoexcept(a1, v139);
                    DName::operator+=(&v128, Noexcept, v94, v95);
                    if ( (a1[68] & 0x100) != 0 )
                    {
                      ThrowTypes = UnDecorator::getThrowTypes(a1, v139);
                      v99 = v130;
                      if ( (_BYTE)v130 == 3 || *(char *)(ThrowTypes + 16) <= 1 )
                      {
                        v35 = v130;
                      }
                      else
                      {
                        v35 = *(unsigned __int8 *)(ThrowTypes + 16) | v130 & 0xFFFFFF00;
                        v128 = 0;
                        v130 = v35;
                        v99 = v35;
                      }
                    }
                    else
                    {
                      v96 = UnDecorator::getThrowTypes(a1, v139);
                      DName::operator+=(&v128, v96, v97, v98);
                      v35 = v130;
                      v99 = v130;
                    }
                    DispatchTarget = UnDecorator::getDispatchTarget(a1, v139);
                    if ( v99 != 3 && *(char *)(DispatchTarget + 16) > 1 )
                    {
                      v35 = *(unsigned __int8 *)(DispatchTarget + 16) | v35 & 0xFFFFFF00;
                      v128 = 0;
                      v130 = v35;
                    }
                    if ( (a1[68] & 4) != 0 || !v52 )
                      goto LABEL_165;
                    *v52 = v128;
                    v102 = v131;
                    *((_DWORD *)v52 + 4) = v35;
                    v35 = v158;
                    v128 = v102;
                    goto LABEL_164;
                  }
                  if ( (v10 & 0x700) == 0x500 )
                  {
                    LODWORD(v137) = 10;
                    v136 = "`vtordisp{";
                    v71 = DName::DName((DName *)v139, (struct UnDecorator *)a1, (const struct StringLiteral *)&v136);
                    DName::operator+(v71, v134, v145);
                    v69 = v151;
                    v70 = v134;
                    goto LABEL_92;
                  }
                }
                LODWORD(v137) = 10;
                v136 = "`adjustor{";
                if ( v50 <= 1 )
                {
                  if ( v3 )
                  {
                    v75 = _HeapManager::getMemoryWithBuffer((struct UnDecorator *)((char *)v129 + 216), 0x18u);
                    v76 = v75;
                    if ( v75 )
                    {
                      v75[4] = 10;
                      *(_QWORD *)v75 = &pcharNode::`vftable';
                      *((_QWORD *)v75 + 1) = "`adjustor{";
                    }
                    else
                    {
                      v76 = 0;
                    }
                    DName::append<pcharNode>(&v128, v76);
                  }
                  else
                  {
                    DName::operator=(&v128, &v136, 2048);
                  }
                }
                goto LABEL_100;
              }
              v53 = UnDecorator::getReturnType(a1, v153, 0);
              v54 = DName::DName((DName *)v152, *(struct UnDecorator **)(v53 + 8), 32);
              DName::operator+(v54, v134, v53);
              DName::operator+=(&v128, v134, v55, v56);
              if ( (*(_DWORD *)v136 & 0x1000) == 0 )
              {
                v50 = v130;
                v3 = v128;
                goto LABEL_84;
              }
LABEL_155:
              v35 = v130;
              v112 = v129;
LABEL_202:
              *(_QWORD *)a2 = v128;
              *(_QWORD *)(a2 + 8) = v112;
              *(_DWORD *)(a2 + 16) = v35;
              return a2;
            }
            if ( (v10 & 0x1800) == 0x800 )
            {
              if ( (v10 & 0x700) == 0x600 )
              {
                LOBYTE(v12) = 1;
                UnDecorator::getDimension(a1, &v131, v12);
                v149[0] = v131;
                LOBYTE(v37) = 1;
                v150 = v133;
                UnDecorator::getDimension(a1, &v131, v37);
                v143[0] = v131;
                v144 = v133;
LABEL_51:
                LOBYTE(v12) = 1;
                UnDecorator::getDimension(a1, &v131, v12);
                v145[0] = v131;
                v146 = v133;
                goto LABEL_52;
              }
              if ( (v10 & 0x700) == 0x500 )
                goto LABEL_51;
            }
LABEL_52:
            LOBYTE(v12) = 1;
            UnDecorator::getDimension(a1, &v131, v12);
            v140 = v131;
            v12 = 6144;
            v142 = v133;
            goto LABEL_53;
          }
          v4 = *(unsigned __int8 *)(BasedType + 16);
        }
        else
        {
          v16 = UnDecorator::getBasedType(a1, v134, 6144, 1024);
          v17 = DName::DName((DName *)v143, *(struct UnDecorator **)(v16 + 8), 32);
          DName::operator+(v17, &v140, v16);
          v3 = v140;
          v4 = v142;
          v128 = v140;
        }
        v130 = v4;
        goto LABEL_23;
      }
    }
    DName::operator+=(&v128, a3, 6144, 1024);
    v103 = 31744;
    if ( !v156 )
    {
      if ( (v10 & 0x7C00) == 0x6800 || (v10 & 0x7C00) == 0x7000 )
      {
        UnDecorator::getVfTableType(a1, a2, &v128);
        return a2;
      }
      if ( (v10 & 0x7C00) == 0x6000 )
      {
        LOBYTE(v103) = 123;
        v104 = DName::operator+(&v128, v139, v103);
        UnDecorator::getDimension(a1, v134, 0);
        v105 = DName::operator+(v104, v151, v134);
        LODWORD(v132) = 2;
        v131 = "}'";
        DName::operator+(v105, a2, &v131);
        return a2;
      }
    }
    if ( (v10 & 0xFC00) == 0x7C00 )
    {
      UnDecorator::getVdispMapType(a1, a2, &v128);
      return a2;
    }
    v106 = (v10 & 0x6000) == 0;
    if ( (v10 & 0x8000) != 0 )
      v106 = (v10 & 0x1800) == 2048;
    if ( ((v106 ? 1024 : 4096) & v10) != 0 )
    {
      v107 = v10 & 0x1B00;
      if ( (v10 & 0x8000) != 0 && v107 == 4096 )
      {
        LODWORD(v132) = 32;
        v131 = "`local static destructor helper'";
        if ( (char)v130 <= 1 )
        {
          if ( v128 )
          {
            v108 = _HeapManager::getMemoryWithBuffer((struct UnDecorator *)((char *)v129 + 216), 0x18u);
            if ( v108 )
            {
              v108[1] = "`local static destructor helper'";
              *v108 = &pcharNode::`vftable';
              *((_DWORD *)v108 + 4) = 32;
            }
            else
            {
              v108 = 0;
            }
            DName::append<pcharNode>(&v128, v108);
          }
          else
          {
            DName::operator=(&v128, &v131, 31744);
          }
        }
LABEL_159:
        v114 = v10 & 0x1B00;
        if ( (v10 & 0x8000) != 0 && v114 == 4352 || (v10 & 0x8000) != 0 && v114 == 4608 )
        {
LABEL_161:
          v112 = v129;
          v115 = DName::DName((DName *)v139, v129, 32);
          DName::operator+(v115, v134, &v128);
          v35 = v135;
          v128 = (const char *)v134[0];
          v130 = v135;
          goto LABEL_166;
        }
LABEL_162:
        ExternalDataType = UnDecorator::getExternalDataType(a1, v139, &v128);
        goto LABEL_163;
      }
      if ( (v10 & 0x8000) != 0 && v107 == 4352 )
      {
        v109 = "`template static data member constructor helper'";
        v110 = 48;
        goto LABEL_144;
      }
      if ( (v10 & 0x8000) != 0 && v107 == 4608 )
      {
        v109 = "`template static data member destructor helper'";
        v110 = 47;
LABEL_144:
        v131 = v109;
        LODWORD(v132) = v110;
        if ( (char)v130 <= 1 )
        {
          if ( v128 )
          {
            v111 = _HeapManager::getMemoryWithBuffer((struct UnDecorator *)((char *)v129 + 216), 0x18u);
            if ( v111 )
            {
              *v111 = &pcharNode::`vftable';
              v111[1] = v109;
              *((_DWORD *)v111 + 4) = v110;
            }
            else
            {
              v111 = 0;
            }
            DName::append<pcharNode>(&v128, v111);
          }
          else
          {
            DName::operator=(&v128, &v131, 31744);
          }
        }
        goto LABEL_161;
      }
    }
    if ( (v10 & 0x8000) == 0 && (v10 & 0x7C00) == 0x7800 )
      goto LABEL_155;
    v113 = (v10 & 0x6000) == 0;
    if ( (v10 & 0x8000) != 0 )
      v113 = (v10 & 0x1800) == 2048;
    if ( ((v113 ? 1024 : 4096) & v10) == 0 )
      goto LABEL_162;
    goto LABEL_159;
  }
  DName::DName(a2, a1, 2);
  return a2;
}

```

## disassembly

```asm
0x1801fe248  mov     [rsp-8+arg_8], rbx
0x1801fe24d  push    rbp
0x1801fe24e  push    rsi
0x1801fe24f  push    rdi
0x1801fe250  push    r12
0x1801fe252  push    r13
0x1801fe254  push    r14
0x1801fe256  push    r15
0x1801fe258  lea     rbp, [rsp-0C0h]
0x1801fe260  sub     rsp, 1C0h
0x1801fe267  mov     eax, [rcx+100h]
0x1801fe26d  xor     r13d, r13d
0x1801fe270  sub     eax, [rcx+108h]
0x1801fe276  xor     ebx, ebx
0x1801fe278  mov     [rbp+0F0h+arg_18], eax
0x1801fe27e  mov     r14, r8
0x1801fe281  mov     r12, rdx
0x1801fe284  mov     [rsp+1F0h+var_1B8], rcx
0x1801fe289  mov     rsi, rcx
0x1801fe28c  mov     [rsp+1F0h+var_1C0], r13
0x1801fe291  mov     [rsp+1F0h+var_1B0], ebx
0x1801fe295  call    ?getTypeEncoding@UnDecorator@@AEAAHXZ; UnDecorator::getTypeEncoding(void)
0x1801fe29a  xor     edx, edx
0x1801fe29c  lea     r15d, [r13+1]
0x1801fe2a0  mov     edi, eax
0x1801fe2a2  cmp     [r14], rdx
0x1801fe2a5  jz      short loc_1801FE2B8
0x1801fe2a7  test    dword ptr [r14+10h], 200h
0x1801fe2af  mov     [rbp+0F0h+arg_10], r15d
0x1801fe2b6  jnz     short loc_1801FE2BE
0x1801fe2b8  mov     [rbp+0F0h+arg_10], edx
0x1801fe2be  cmp     edi, 0FFFFh
0x1801fe2c4  jnz     short loc_1801FE2DC
0x1801fe2c6  mov     r8d, 2
0x1801fe2cc  mov     rdx, rsi
0x1801fe2cf  mov     rcx, r12
0x1801fe2d2  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x1801fe2d7  jmp     loc_1801FF43B
0x1801fe2dc  cmp     edi, 0FFFEh
0x1801fe2e2  jnz     short loc_1801FE308
0x1801fe2e4  mov     rdx, [r14+8]
0x1801fe2e8  lea     rcx, [rsp+1F0h+var_180]
0x1801fe2ed  mov     r8d, r15d
0x1801fe2f0  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x1801fe2f5  mov     r8, r14
0x1801fe2f8  mov     rdx, r12
0x1801fe2fb  mov     rcx, rax
0x1801fe2fe  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1801fe303  jmp     loc_1801FF43B
0x1801fe308  cmp     edi, 0FFFDh
0x1801fe30e  jnz     short loc_1801FE32E
0x1801fe310  mov     rax, [r14+8]
0x1801fe314  mov     [r12+8], rax
0x1801fe319  mov     rax, [r14]
0x1801fe31c  mov     [r12], rax
0x1801fe320  mov     eax, [r14+10h]
0x1801fe324  mov     [r12+10h], eax
0x1801fe329  jmp     loc_1801FF43B
0x1801fe32e  and     eax, 8000h
0x1801fe333  mov     r8d, 1800h
0x1801fe339  mov     [rbp+0F0h+arg_0], eax
0x1801fe33f  mov     r9d, 400h
0x1801fe345  jz      loc_1801FED60
0x1801fe34b  mov     eax, edi
0x1801fe34d  mov     ecx, 1000h
0x1801fe352  and     eax, r8d
0x1801fe355  cmp     eax, 800h
0x1801fe35a  cmovz   ecx, r9d
0x1801fe35e  test    edi, ecx
0x1801fe360  jz      short loc_1801FE384
0x1801fe362  mov     eax, edi
0x1801fe364  and     eax, 1B00h
0x1801fe369  cmp     eax, 1000h
0x1801fe36e  jz      loc_1801FED60
0x1801fe374  add     eax, 0FFFFEF00h
0x1801fe379  test    eax, 0FFFFFEFFh
0x1801fe37e  jz      loc_1801FED60
0x1801fe384  bt      edi, 0Eh
0x1801fe388  jnb     short loc_1801FE3F8
0x1801fe38a  mov     eax, [rsi+110h]
0x1801fe390  test    al, 2
0x1801fe392  jnz     short loc_1801FE3D5
0x1801fe394  test    al, 8
0x1801fe396  jnz     short loc_1801FE3D5
0x1801fe398  lea     rdx, [rsp+1F0h+var_180]
0x1801fe39d  mov     rcx, rsi
0x1801fe3a0  call    ?getBasedType@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getBasedType(void)
0x1801fe3a5  mov     r8b, 20h ; ' '; char
0x1801fe3a8  lea     rcx, [rbp+0F0h+var_110]; this
0x1801fe3ac  mov     rbx, rax
0x1801fe3af  mov     rdx, [rax+8]; struct UnDecorator *
0x1801fe3b3  call    ??0DName@@QEAA@PEAVUnDecorator@@D@Z; DName::DName(UnDecorator *,char)
0x1801fe3b8  mov     r8, rbx
0x1801fe3bb  lea     rdx, [rbp+0F0h+var_128]
0x1801fe3bf  mov     rcx, rax
0x1801fe3c2  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1801fe3c7  mov     r13, [rbp+0F0h+var_128]
0x1801fe3cb  mov     ebx, [rbp+0F0h+var_118]
0x1801fe3ce  mov     [rsp+1F0h+var_1C0], r13
0x1801fe3d3  jmp     short loc_1801FE3EC
0x1801fe3d5  lea     rdx, [rsp+1F0h+var_180]
0x1801fe3da  mov     rcx, rsi
0x1801fe3dd  call    ?getBasedType@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getBasedType(void)
0x1801fe3e2  cmp     [rax+10h], r15b
0x1801fe3e6  jle     short loc_1801FE3F0
0x1801fe3e8  movzx   ebx, byte ptr [rax+10h]
0x1801fe3ec  mov     [rsp+1F0h+var_1B0], ebx
0x1801fe3f0  xor     edx, edx
0x1801fe3f2  mov     r8d, 1800h
0x1801fe3f8  mov     eax, edi
0x1801fe3fa  mov     r10d, 800h
0x1801fe400  and     eax, r8d
0x1801fe403  mov     r9d, 1000h
0x1801fe409  cmp     eax, r10d
0x1801fe40c  mov     ecx, r9d
0x1801fe40f  mov     r11d, 400h
0x1801fe415  cmovz   ecx, r11d
0x1801fe419  test    edi, ecx
0x1801fe41b  jz      loc_1801FE606
0x1801fe421  mov     eax, edi
0x1801fe423  and     eax, r8d
0x1801fe426  cmp     eax, r8d
0x1801fe429  jnz     loc_1801FE606
0x1801fe42f  mov     r8b, 7Bh ; '{'
0x1801fe432  lea     rdx, [rbp+0F0h+var_128]
0x1801fe436  mov     rcx, r14
0x1801fe439  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x1801fe43e  xor     r8d, r8d
0x1801fe441  lea     rdx, [rsp+1F0h+var_180]
0x1801fe446  mov     rcx, rsi
0x1801fe449  mov     rbx, rax
0x1801fe44c  call    ?getDimension@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x1801fe451  lea     r8, [rsp+1F0h+var_180]
0x1801fe456  mov     rcx, rbx
0x1801fe459  lea     rdx, [rbp+0F0h+var_110]
0x1801fe45d  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1801fe462  mov     rdx, rax
0x1801fe465  lea     rcx, [rsp+1F0h+var_1C0]
0x1801fe46a  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1801fe46f  lea     rdx, [rbp+0F0h+var_128]
0x1801fe473  mov     rcx, rsi
0x1801fe476  call    ?getVCallThunkType@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getVCallThunkType(void)
0x1801fe47b  lea     rbx, [rsi+110h]
0x1801fe482  mov     r13d, 1000h
0x1801fe488  test    [rbx], r13d
0x1801fe48b  jnz     short loc_1801FE4ED
0x1801fe48d  mov     rdx, [rbp+0F0h+var_120]; struct UnDecorator *
0x1801fe491  lea     rcx, [rbp+0F0h+var_110]; this
0x1801fe495  mov     r8b, 2Ch ; ','; char
0x1801fe498  call    ??0DName@@QEAA@PEAVUnDecorator@@D@Z; DName::DName(UnDecorator *,char)
0x1801fe49d  lea     r8, [rbp+0F0h+var_128]
0x1801fe4a1  mov     rcx, rax
0x1801fe4a4  lea     rdx, [rsp+1F0h+var_180]
0x1801fe4a9  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1801fe4ae  mov     dword ptr [rsp+1F0h+var_1A0+8], 3
0x1801fe4b6  lea     rax, asc_18028EC1C; "}' "
0x1801fe4bd  mov     qword ptr [rsp+1F0h+var_1A0], rax
0x1801fe4c2  lea     r8, [rsp+1F0h+var_1A0]
0x1801fe4c7  movaps  xmm0, [rsp+1F0h+var_1A0]
0x1801fe4cc  lea     rdx, [rbp+0F0h+var_C8]
0x1801fe4d0  lea     rcx, [rsp+1F0h+var_180]
0x1801fe4d5  movdqa  [rsp+1F0h+var_1A0], xmm0
0x1801fe4db  call    ??HDName@@QEBA?AV0@AEBUStringLiteral@@@Z; DName::operator+(StringLiteral const &)
0x1801fe4e0  mov     rdx, rax
0x1801fe4e3  lea     rcx, [rsp+1F0h+var_1C0]
0x1801fe4e8  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1801fe4ed  lea     r14, asc_18028EC20; "}'"
0x1801fe4f4  mov     dword ptr [rsp+1F0h+var_1A0+8], 2
0x1801fe4fc  mov     qword ptr [rsp+1F0h+var_1A0], r14
0x1801fe501  movaps  xmm0, [rsp+1F0h+var_1A0]
0x1801fe506  movdqa  [rsp+1F0h+var_1A0], xmm0
0x1801fe50c  cmp     byte ptr [rsp+1F0h+var_1B0], r15b
0x1801fe511  jg      short loc_1801FE574
0x1801fe513  cmp     [rsp+1F0h+var_1C0], 0
0x1801fe519  jnz     short loc_1801FE52C
0x1801fe51b  lea     rdx, [rsp+1F0h+var_1A0]
0x1801fe520  lea     rcx, [rsp+1F0h+var_1C0]
0x1801fe525  call    ??4DName@@QEAAAEAV0@AEBUStringLiteral@@@Z; DName::operator=(StringLiteral const &)
0x1801fe52a  jmp     short loc_1801FE574
0x1801fe52c  mov     rcx, [rsp+1F0h+var_1B8]
0x1801fe531  mov     edx, 18h; unsigned __int64
0x1801fe536  add     rcx, 0D8h; this
0x1801fe53d  call    ?getMemoryWithBuffer@_HeapManager@@QEAAPEAX_K@Z; _HeapManager::getMemoryWithBuffer(unsigned __int64)
0x1801fe542  mov     rdx, rax
0x1801fe545  test    rax, rax
0x1801fe548  jz      short loc_1801FE561
0x1801fe54a  lea     rax, ??_7pcharNode@@6B@; const pcharNode::`vftable'
0x1801fe551  mov     [rdx+8], r14
0x1801fe555  mov     [rdx], rax
0x1801fe558  mov     dword ptr [rdx+10h], 2
0x1801fe55f  jmp     short loc_1801FE563
0x1801fe561  xor     edx, edx
0x1801fe563  lea     rcx, [rsp+1F0h+var_1C0]
0x1801fe568  call    ??$append@VpcharNode@@@DName@@AEAAXPEBVpcharNode@@@Z; DName::append<pcharNode>(pcharNode const *)
0x1801fe56d  lea     rbx, [rsi+110h]
0x1801fe574  lea     rdx, [rbp+0F0h+var_128]
0x1801fe578  mov     rcx, rsi
0x1801fe57b  call    ?getCallingConvention@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getCallingConvention(void)
0x1801fe580  test    byte ptr [rbx], 12h
0x1801fe583  jnz     short loc_1801FE5D2
0x1801fe585  test    [rbx], r13d
0x1801fe588  jnz     short loc_1801FE5D2
0x1801fe58a  mov     rdx, [rbp+0F0h+var_120]; struct UnDecorator *
0x1801fe58e  lea     rcx, [rbp+0F0h+var_110]; this
0x1801fe592  mov     r8b, 20h ; ' '; char
0x1801fe595  call    ??0DName@@QEAA@PEAVUnDecorator@@D@Z; DName::DName(UnDecorator *,char)
0x1801fe59a  lea     r8, [rbp+0F0h+var_128]
0x1801fe59e  mov     rcx, rax
0x1801fe5a1  lea     rdx, [rsp+1F0h+var_180]
0x1801fe5a6  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1801fe5ab  mov     r8b, 20h ; ' '
0x1801fe5ae  lea     rdx, [rbp+0F0h+var_C8]
0x1801fe5b2  lea     rcx, [rsp+1F0h+var_180]
0x1801fe5b7  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x1801fe5bc  lea     r8, [rsp+1F0h+var_1C0]
0x1801fe5c1  mov     rcx, rax
0x1801fe5c4  lea     rdx, [rbp+0F0h+var_E0]
0x1801fe5c8  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1801fe5cd  jmp     loc_1801FF0E3
0x1801fe5d2  cmp     byte ptr [rsp+1F0h+var_1B0], 3
0x1801fe5d7  jz      short loc_1801FE5FD
0x1801fe5d9  cmp     byte ptr [rbp+0F0h+var_118], r15b
0x1801fe5dd  jle     short loc_1801FE5FD
0x1801fe5df  mov     ebx, [rsp+1F0h+var_1B0]
0x1801fe5e3  movzx   eax, byte ptr [rbp+0F0h+var_118]
0x1801fe5e7  and     ebx, 0FFFFFF00h
0x1801fe5ed  or      ebx, eax
0x1801fe5ef  mov     [rsp+1F0h+var_1C0], 0
0x1801fe5f8  jmp     loc_1801FF0EE
0x1801fe5fd  mov     ebx, [rsp+1F0h+var_1B0]
0x1801fe601  jmp     loc_1801FF0F2
0x1801fe606  mov     eax, edi
0x1801fe608  mov     [rbp+0F0h+var_C0], rsi
0x1801fe60c  and     eax, r8d
0x1801fe60f  mov     [rbp+0F0h+var_C8], rdx
0x1801fe613  cmp     eax, r10d
0x1801fe616  mov     [rbp+0F0h+var_B8], edx
0x1801fe619  mov     ecx, r9d
0x1801fe61c  mov     [rbp+0F0h+var_108], rsi
0x1801fe620  cmovz   ecx, r11d
0x1801fe624  mov     [rbp+0F0h+var_110], rdx
0x1801fe628  mov     [rbp+0F0h+var_100], edx
0x1801fe62b  mov     [rbp+0F0h+var_F0], rsi
0x1801fe62f  mov     [rbp+0F0h+var_F8], rdx
0x1801fe633  mov     [rbp+0F0h+var_E8], edx
0x1801fe636  mov     [rbp+0F0h+var_120], rsi
0x1801fe63a  mov     [rbp+0F0h+var_128], rdx
0x1801fe63e  mov     [rbp+0F0h+var_118], edx
0x1801fe641  mov     [rbp+0F0h+var_D8], rsi
0x1801fe645  mov     [rbp+0F0h+var_E0], rdx
0x1801fe649  mov     [rbp+0F0h+var_D0], edx
0x1801fe64c  test    edi, ecx
0x1801fe64e  jz      loc_1801FE70A
0x1801fe654  mov     eax, edi
0x1801fe656  and     eax, r8d
0x1801fe659  cmp     eax, r10d
0x1801fe65c  jnz     short loc_1801FE6DC
0x1801fe65e  mov     eax, edi
0x1801fe660  and     eax, 700h
0x1801fe665  cmp     eax, 600h
0x1801fe66a  jnz     short loc_1801FE6AE
0x1801fe66c  mov     r8b, r15b
0x1801fe66f  lea     rdx, [rsp+1F0h+var_1A0]
0x1801fe674  mov     rcx, rsi
0x1801fe677  call    ?getDimension@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x1801fe67c  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x1801fe681  lea     rdx, [rsp+1F0h+var_1A0]
0x1801fe686  mov     [rbp+0F0h+var_C8], rax
0x1801fe68a  mov     r8b, r15b
0x1801fe68d  mov     eax, [rsp+1F0h+var_190]
0x1801fe691  mov     rcx, rsi
0x1801fe694  mov     [rbp+0F0h+var_B8], eax
0x1801fe697  call    ?getDimension@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x1801fe69c  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x1801fe6a1  mov     [rbp+0F0h+var_110], rax
0x1801fe6a5  mov     eax, [rsp+1F0h+var_190]
0x1801fe6a9  mov     [rbp+0F0h+var_100], eax
0x1801fe6ac  jmp     short loc_1801FE6BC
0x1801fe6ae  mov     eax, edi
0x1801fe6b0  and     eax, 700h
0x1801fe6b5  cmp     eax, 500h
0x1801fe6ba  jnz     short loc_1801FE6DC
0x1801fe6bc  mov     r8b, r15b
0x1801fe6bf  lea     rdx, [rsp+1F0h+var_1A0]
0x1801fe6c4  mov     rcx, rsi
0x1801fe6c7  call    ?getDimension@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x1801fe6cc  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x1801fe6d1  mov     [rbp+0F0h+var_F8], rax
0x1801fe6d5  mov     eax, [rsp+1F0h+var_190]
0x1801fe6d9  mov     [rbp+0F0h+var_E8], eax
0x1801fe6dc  mov     r8b, r15b
0x1801fe6df  lea     rdx, [rsp+1F0h+var_1A0]
0x1801fe6e4  mov     rcx, rsi
0x1801fe6e7  call    ?getDimension@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x1801fe6ec  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x1801fe6f1  xor     edx, edx
0x1801fe6f3  mov     [rbp+0F0h+var_128], rax
0x1801fe6f7  mov     r8d, 1800h
0x1801fe6fd  mov     eax, [rsp+1F0h+var_190]
0x1801fe701  mov     r10d, 800h
  ... truncated ...
```
