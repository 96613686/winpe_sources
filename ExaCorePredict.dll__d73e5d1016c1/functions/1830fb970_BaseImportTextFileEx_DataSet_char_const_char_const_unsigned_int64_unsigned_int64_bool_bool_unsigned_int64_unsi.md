# BaseImportTextFileEx(DataSet &,char const *,char const *,unsigned __int64,unsigned __int64,bool,bool,unsigned __int64,unsigned __int64,StringMatrix)

- ea: `0x1830fb970`
- end: `0x1830fc3fd`
- name: `?BaseImportTextFileEx@@YA_NAEAVDataSet@@PEBD1_K2_N322VStringMatrix@@@Z`
- size: `2701`
- prototype: ``
- caller_count: `2`
- callee_count: `45`
- tags: ``

## callers

- `0x1830fb970`
- `0x1830ff000`

## callees

- `0x1815af950`
- `0x1815b0ef0`
- `0x1815b22a0`
- `0x1815b23f0`
- `0x1815ce290`
- `0x1815cfcc0`
- `0x182d3ec20`
- `0x182d40660`
- `0x182d40d20`
- `0x182da06d0`
- `0x182dcc6d0`
- `0x182dcca70`
- `0x1830169f0`
- `0x183036b90`
- `0x183036e20`
- `0x183052e40`
- `0x183052ed0`
- `0x183053010`
- `0x183053170`
- `0x183055940`
- `0x1830fb970`
- `0x1830fc400`
- `0x1830fc990`
- `0x1830fdb50`
- `0x183108cc0`
- `0x183292fd0`
- `0x183295b50`
- `0x183295c50`
- `0x183296350`
- `0x18329f7e0`
- `0x1832a9910`
- `0x1832aa590`
- `0x1832aae10`
- `0x1832ab550`
- `0x1832abf90`
- `0x1832b0840`
- `0x1832b0e70`
- `0x1832b10e0`
- `0x1832b1240`
- `0x1832b1880`
- `0x1832b43b0`
- `0x1832c3a50`
- `0x1832ce3b0`
- `0x1832ceb40`
- `0x1832dbeb0`

## import_xrefs

- `VCRUNTIME140!strrchr` at `0x1830fbfb6`
- `VCRUNTIME140!strrchr` at `0x1830fbfb6`
- `api-ms-win-crt-stdio-l1-1-0!feof` at `0x1830fbe2a`
- `api-ms-win-crt-stdio-l1-1-0!feof` at `0x1830fc106`
- `api-ms-win-crt-stdio-l1-1-0!feof` at `0x1830fbe2a`
- `api-ms-win-crt-stdio-l1-1-0!feof` at `0x1830fc106`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x1830fbef3`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x1830fc3c0`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x1830fbef3`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x1830fc3c0`
- `api-ms-win-crt-stdio-l1-1-0!ferror` at `0x1830fc0e1`
- `api-ms-win-crt-stdio-l1-1-0!ferror` at `0x1830fc0e1`
- `api-ms-win-crt-stdio-l1-1-0!fgets` at `0x1830fbee5`
- `api-ms-win-crt-stdio-l1-1-0!fgets` at `0x1830fbf9a`
- `api-ms-win-crt-stdio-l1-1-0!fgets` at `0x1830fbee5`
- `api-ms-win-crt-stdio-l1-1-0!fgets` at `0x1830fbf9a`

## string_xrefs

- `0x1830fbdca`: `The file %s could not be opened.`
- `0x1830fc0f3`: `There was an error reading the file: %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
char __fastcall BaseImportTextFileEx(
        struct DataSet *a1,
        __int64 a2,
        _BYTE *a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        char a6,
        char a7,
        unsigned __int64 a8,
        unsigned __int64 a9,
        StringMatrix *a10)
{
  StringMatrix *v11; // rbx
  unsigned __int64 v12; // rdi
  __int64 v13; // rax
  char v14; // si
  __int64 v15; // rax
  unsigned __int64 i; // rsi
  CxDataSetVector *v17; // rax
  struct Var *Var0; // rax
  int VarType; // edi
  CxIntVector *v20; // rax
  CxIntVector *v21; // rdi
  __int64 v22; // rdi
  CxDataSetVector *v23; // rax
  struct Var *v24; // rax
  unsigned __int64 v25; // rax
  struct CxVarHeader *v26; // rax
  __int64 v27; // rax
  StringMatrix *v28; // rax
  char v29; // bl
  const char *v31; // rax
  struct _iobuf *v32; // rdi
  char v33; // bl
  void *v34; // rax
  void *v35; // rbx
  unsigned __int64 v36; // rax
  unsigned __int64 j; // rbx
  bool v38; // di
  __int64 v39; // rax
  bool v40; // di
  unsigned __int64 k; // rbx
  char *v42; // rax
  unsigned __int64 Length; // rax
  int v44; // edx
  CxDataSetVector *v45; // rax
  VarBase *v46; // rbx
  const struct CxVector *v47; // rax
  unsigned __int64 v48; // rdi
  unsigned __int64 v49; // rbx
  unsigned __int64 v50; // rcx
  StringMatrix *v51; // rbx
  int v52; // eax
  char v53; // si
  CxDataSetVector *v54; // rax
  struct Var *v55; // rax
  unsigned __int64 v56; // rax
  unsigned __int64 m; // rsi
  __int64 v58; // rax
  __int64 v59; // rax
  unsigned int v60; // ebx
  const char *v61; // rdi
  __int64 v62; // rax
  int v63; // [rsp+20h] [rbp-2838h]
  int v64; // [rsp+28h] [rbp-2830h]
  int v65; // [rsp+28h] [rbp-2830h]
  int v66; // [rsp+28h] [rbp-2830h]
  int v67; // [rsp+30h] [rbp-2828h]
  int v68; // [rsp+30h] [rbp-2828h]
  char v69; // [rsp+50h] [rbp-2808h]
  char v70; // [rsp+51h] [rbp-2807h]
  char v71; // [rsp+52h] [rbp-2806h]
  unsigned __int8 v72; // [rsp+53h] [rbp-2805h]
  char v73; // [rsp+53h] [rbp-2805h]
  char v74; // [rsp+54h] [rbp-2804h]
  unsigned __int64 v76; // [rsp+68h] [rbp-27F0h] BYREF
  FILE *Stream; // [rsp+70h] [rbp-27E8h]
  unsigned __int64 v78; // [rsp+78h] [rbp-27E0h]
  __int64 v79; // [rsp+80h] [rbp-27D8h] BYREF
  unsigned __int64 *v80; // [rsp+88h] [rbp-27D0h] BYREF
  unsigned __int64 v81; // [rsp+90h] [rbp-27C8h]
  _BYTE *v82; // [rsp+98h] [rbp-27C0h]
  const char *CharPointer; // [rsp+A0h] [rbp-27B8h]
  __int64 v84; // [rsp+A8h] [rbp-27B0h]
  struct _iobuf *v85; // [rsp+B0h] [rbp-27A8h]
  unsigned __int64 v86; // [rsp+B8h] [rbp-27A0h]
  char v87[8]; // [rsp+C0h] [rbp-2798h] BYREF
  __int64 v88; // [rsp+C8h] [rbp-2790h]
  _BYTE v89[24]; // [rsp+D0h] [rbp-2788h] BYREF
  __int64 v90; // [rsp+E8h] [rbp-2770h]
  StringMatrix *v91; // [rsp+F0h] [rbp-2768h]
  __int64 v92; // [rsp+F8h] [rbp-2760h] BYREF
  __int64 v93; // [rsp+100h] [rbp-2758h] BYREF
  int v94[2]; // [rsp+108h] [rbp-2750h] BYREF
  __int64 v95; // [rsp+110h] [rbp-2748h] BYREF
  __int64 v96; // [rsp+118h] [rbp-2740h] BYREF
  char Buffer[10008]; // [rsp+120h] [rbp-2738h] BYREF

  v90 = -2;
  v81 = a4;
  v82 = a3;
  v96 = a2;
  v11 = a10;
  v91 = a10;
  v95 = 0;
  LOBYTE(a3) = 1;
  CheckAndFixTextFileName(&v95, a2, a3);
  CharPointer = CxString::GetCharPointer((CxString *)&v95);
  v85 = 0;
  v84 = -1;
  v88 = 0;
  v71 = 0;
  v70 = 1;
  if ( VarBase::operator CxVector *(a1) )
  {
    v13 = VarBase::operator CxVector *(a1);
    v12 = CxTemplateVector<CxWrapper<CxCustomAnalysis>>::SizeVM(v13);
    v78 = v12;
  }
  else
  {
    v12 = 0;
    v78 = 0;
  }
  v92 = 0;
  IntMatrix::IntMatrix((IntMatrix *)&v92);
  v14 = 0;
  v69 = 0;
  if ( v12 )
  {
    v69 = 1;
    v15 = TypelessValue::TypelessValue(v89, v72);
    IntMatrix::Resize(&v92, v12, 1, v15, 1);
    for ( i = 0; i < v12; ++i )
    {
      v17 = (CxDataSetVector *)VarBase::operator CxVector *(a1);
      Var0 = CxDataSetVector::GetVar0(v17, i);
      VarType = Var::GetVarType(Var0);
      if ( VarType == 7 )
      {
        v69 = 0;
        v20 = (CxIntVector *)operator new(0x88u);
        v21 = v20;
        v80 = (unsigned __int64 *)v20;
        if ( v20 )
        {
          memset_0(v20, 0, 0x88u);
          v94[0] = 0;
          v20 = CxIntVector::CxIntVector(v21, 0, 1u, v94);
        }
        VarBase::operator=(&v92, v20);
      }
      else
      {
        *(_DWORD *)UIntMatrix::operator[](&v92, i) = VarType;
        v80 = (unsigned __int64 *)v89;
        v22 = TypelessValue::TypelessValue(v89, v72);
        v23 = (CxDataSetVector *)VarBase::operator CxVector *(a1);
        v24 = CxDataSetVector::GetVar0(v23, i);
        LOBYTE(v63) = 1;
        Var::Resize(v24, 0, 1, v22, v63);
      }
      v12 = v78;
    }
    v14 = v69;
    v11 = a10;
  }
  v25 = a5;
  if ( a5 == -1 )
    v25 = a8;
  v86 = v25;
  if ( v14 || v81 <= 1 )
  {
    v31 = CxString::GetCharPointer((CxString *)&v95);
    v32 = CxFOpen(v31, "r");
    Stream = v32;
    v85 = v32;
    if ( !v32 )
    {
      CxReportError("The file %s could not be opened.", CharPointer);
      IntMatrix::~IntMatrix((IntMatrix *)&v92);
      CxString::~CxString((CxString *)&v95);
      StringMatrix::~StringMatrix(v11);
      return 0;
    }
    v78 = a9;
    v74 = a7;
    v73 = a6;
    while ( 1 )
    {
      v33 = v70;
      if ( feof(v32) || !v70 )
      {
LABEL_86:
        IntMatrix::~IntMatrix((IntMatrix *)&v92);
        fclose(v32);
        CxString::~CxString((CxString *)&v95);
        StringMatrix::~StringMatrix(a10);
        return v33;
      }
      v93 = 0;
      CxWrapper<CxDescriptiveStatsCubeVector>::CxWrapper<CxDescriptiveStatsCubeVector>(&v93);
      v34 = operator new(0xB8u);
      v35 = v34;
      v79 = (__int64)v34;
      if ( v34 )
      {
        memset_0(v34, 0, 0xB8u);
        v34 = (void *)CxDataSetVector::CxDataSetVector(v35, v86, 5);
      }
      v79 = (__int64)v34;
      VarBase::InitFromVector((VarBase *)&v93, (const struct CxVector *)v34);
      v36 = v81;
      if ( v81 > 1 )
      {
        for ( j = 1; j < v36; ++j )
        {
          if ( !fgets(Buffer, 10000, v32) )
          {
            fclose(v32);
            Var::~Var((Var *)&v93);
            IntMatrix::~IntMatrix((IntMatrix *)&v92);
            CxString::~CxString((CxString *)&v95);
            StringMatrix::~StringMatrix(a10);
            return 0;
          }
          v36 = v81;
        }
        v14 = v69;
      }
      v38 = 0;
      v39 = -1;
      do
        ++v39;
      while ( v82[v39] );
      if ( v39 == 1 )
        v38 = *v82 == 9;
      v40 = !v38;
      for ( k = 0; ; ++k )
      {
        v76 = k;
        if ( k >= v86 )
          break;
        if ( fgets(Buffer, 10000, Stream) )
        {
          v42 = strrchr(Buffer, 10);
          if ( v42 )
            *v42 = 0;
          v96 = 0;
          CxString::CxString((CxString *)v87, Buffer);
          LOBYTE(v67) = 0;
          LOBYTE(v64) = 1;
          LOBYTE(v63) = v40;
          ParseString(&v96, v87, v82, 0, v63, v64, v67);
          CxString::~CxString((CxString *)v87);
          Length = Var::GetLength((Var *)&v96);
          if ( Length )
          {
            v44 = ++v88;
            if ( v84 == -1 )
            {
              v84 = Length;
            }
            else if ( Length != v84 )
            {
              CxThrowError(
                "In the file '%s', line #%u has a different number of columns than previous lines: %u vs. %u",
                CharPointer,
                v44,
                Length,
                v84);
            }
            v45 = (CxDataSetVector *)VarBase::operator CxVector *(&v93);
            v46 = CxDataSetVector::GetVar0(v45, k);
            v47 = (const struct CxVector *)VarBase::operator CxVector *(&v96);
            VarBase::AssignFromVector(v46, v47);
            StringMatrix::~StringMatrix((StringMatrix *)&v96);
            k = v76;
          }
          else
          {
            StringMatrix::~StringMatrix((StringMatrix *)&v96);
          }
        }
        else
        {
          if ( ferror(Stream) )
            CxThrowError("There was an error reading the file: %s.", CharPointer);
          if ( feof(Stream) )
          {
            v70 = 0;
            break;
          }
        }
      }
      if ( !k || (v48 = v84) == 0 )
      {
        Var::~Var((Var *)&v93);
        v32 = Stream;
LABEL_85:
        v33 = v70;
        goto LABEL_86;
      }
      v49 = 0;
      v79 = 0;
      if ( !v14 )
        break;
LABEL_82:
      ConvertParsedRowsToData(a1, (struct DataSet *)&v93, v49, v76);
      Var::~Var((Var *)&v93);
      v32 = Stream;
      if ( a5 != -1 )
        goto LABEL_85;
    }
    v50 = v78;
    if ( v76 < v78 )
      v50 = v76;
    v78 = v50;
    v51 = a10;
    if ( Var::GetLength(a10) )
    {
      if ( Var::GetLength(a10) != v48 )
      {
        v52 = Var::GetLength(a10);
        CxThrowError(
          "The specified number of column names does not match the number of columns in the file %s: %u vs %u.",
          CharPointer,
          v52,
          v48);
      }
      v53 = 0;
      v74 = 0;
      v71 = 1;
    }
    else
    {
      v53 = v74;
    }
    v94[0] = 0;
    if ( (Var::IsEmpty((Var *)&v92) || v53)
      && (DetectDataTypes((struct DataSet *)&v93, (struct IntMatrix *)&v92, v78, v94), v53)
      && v94[0] > 1 )
    {
      v73 = 1;
    }
    else if ( !v73 )
    {
LABEL_76:
      v56 = Var::GetLength((Var *)&v92);
      Verify(v56 == v48, "ivMasterVarTypes.GetLength() == iNumCols", "..\\ExaCore\\DataSet.cpp", 3066);
      for ( m = 0; m < v48; ++m )
      {
        *(_QWORD *)v94 = 0;
        CxString::CxString((CxString *)v94);
        if ( v71 )
        {
          v58 = StringMatrix::operator[](v51, m);
          v59 = StripQuotes(&v80, v58);
          CxString::operator=(v94, v59);
          CxString::~CxString((CxString *)&v80);
        }
        v60 = *(_DWORD *)UIntMatrix::operator[](&v92, m);
        v61 = CxString::GetCharPointer((CxString *)v94);
        v62 = VarBase::operator CxVector *(a1);
        CxDataSetVector::CreateVar(v62, v61, v60, 0, 1);
        CxString::~CxString((CxString *)v94);
        v48 = v84;
        v51 = a10;
      }
      v14 = 1;
      v69 = 1;
      v49 = v79;
      goto LABEL_82;
    }
    if ( !v71 )
    {
      v79 = 1;
      v54 = (CxDataSetVector *)VarBase::operator CxVector *(&v93);
      v55 = CxDataSetVector::GetVar0(v54, 0);
      ShortMatrix::operator=(a10, v55);
      v71 = 1;
    }
    goto LABEL_76;
  }
  v80 = &v76;
  CxWrapper<CxDescriptiveStatsCubeVector>::CxWrapper<CxDescriptiveStatsCubeVector>(&v76);
  v26 = (struct CxVarHeader *)CxStr::operator char const *(v11);
  VarBase::InitFromHeader((VarBase *)&v76, v26, 1, 1, 0, 0);
  LOBYTE(v65) = a6;
  if ( (unsigned __int8)BaseImportTextFileEx(a1, v96, v82, 1, a9, v65, a7, a8, a9, &v76)
    && VarBase::operator CxVector *(a1)
    && (v27 = VarBase::operator CxVector *(a1), CxTemplateVector<CxWrapper<CxCustomAnalysis>>::SizeVM(v27)) )
  {
    v28 = StringMatrix::StringMatrix((StringMatrix *)&v79, a10);
    LOBYTE(v68) = a7;
    LOBYTE(v66) = a6;
    v29 = BaseImportTextFileEx(a1, v96, v82, v81, a5, v66, v68, a8, a9, v28);
    IntMatrix::~IntMatrix((IntMatrix *)&v92);
    CxString::~CxString((CxString *)&v95);
    StringMatrix::~StringMatrix(a10);
    return v29;
  }
  else
  {
    IntMatrix::~IntMatrix((IntMatrix *)&v92);
    CxString::~CxString((CxString *)&v95);
    StringMatrix::~StringMatrix(a10);
    return 0;
  }
}

```

## disassembly

```asm
0x1830fb970  push    rbx
0x1830fb972  push    rsi
0x1830fb973  push    rdi
0x1830fb974  mov     eax, 2840h
0x1830fb979  call    _alloca_probe
0x1830fb97e  sub     rsp, rax
0x1830fb981  mov     [rsp+2858h+var_2770], 0FFFFFFFFFFFFFFFEh
0x1830fb98d  mov     rax, cs:__security_cookie
0x1830fb994  xor     rax, rsp
0x1830fb997  mov     [rsp+2858h+var_20], rax
0x1830fb99f  mov     [rsp+2858h+var_27C8], r9
0x1830fb9a7  mov     [rsp+2858h+var_27C0], r8
0x1830fb9af  mov     [rsp+2858h+var_2740], rdx
0x1830fb9b7  mov     rdi, rcx
0x1830fb9ba  mov     [rsp+2858h+var_2800], rcx
0x1830fb9bf  mov     rbx, [rsp+2858h+arg_48]
0x1830fb9c7  mov     [rsp+2858h+var_27F8], rbx
0x1830fb9cc  mov     [rsp+2858h+var_2768], rbx
0x1830fb9d4  xor     ecx, ecx
0x1830fb9d6  mov     [rsp+2858h+var_2748], rcx
0x1830fb9de  mov     r8b, 1
0x1830fb9e1  lea     rcx, [rsp+2858h+var_2748]
0x1830fb9e9  call    CheckAndFixTextFileName
0x1830fb9ee  nop
0x1830fb9ef  lea     rcx, [rsp+2858h+var_2748]; this
0x1830fb9f7  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x1830fb9fc  mov     [rsp+2858h+var_27B8], rax
0x1830fba04  xor     esi, esi
0x1830fba06  mov     [rsp+2858h+var_27A8], rsi
0x1830fba0e  mov     [rsp+2858h+var_27B0], 0FFFFFFFFFFFFFFFFh
0x1830fba1a  mov     [rsp+2858h+var_2790], rsi
0x1830fba22  mov     [rsp+2858h+var_2806], sil
0x1830fba27  mov     [rsp+2858h+var_2807], 1
0x1830fba2c  mov     rcx, rdi
0x1830fba2f  call    ??BVarBase@@QEBAPEAVCxVector@@XZ; VarBase::operator CxVector *(void)
0x1830fba34  test    rax, rax
0x1830fba37  jnz     short loc_1830FBA42
0x1830fba39  mov     edi, esi
0x1830fba3b  mov     [rsp+2858h+var_27E0], rsi
0x1830fba40  jmp     short loc_1830FBA5A
0x1830fba42  mov     rcx, rdi
0x1830fba45  call    ??BVarBase@@QEBAPEAVCxVector@@XZ; VarBase::operator CxVector *(void)
0x1830fba4a  mov     rcx, rax
0x1830fba4d  call    ?SizeVM@?$CxTemplateVector@V?$CxWrapper@VCxCustomAnalysis@@@@@@UEBA_KXZ; CxTemplateVector<CxWrapper<CxCustomAnalysis>>::SizeVM(void)
0x1830fba52  mov     rdi, rax
0x1830fba55  mov     [rsp+2858h+var_27E0], rax
0x1830fba5a  xor     eax, eax
0x1830fba5c  mov     [rsp+2858h+var_2760], rax
0x1830fba64  lea     rcx, [rsp+2858h+var_2760]; this
0x1830fba6c  call    ??0IntMatrix@@QEAA@XZ; IntMatrix::IntMatrix(void)
0x1830fba71  nop
0x1830fba72  xor     sil, sil
0x1830fba75  mov     [rsp+2858h+var_2808], sil
0x1830fba7a  test    rdi, rdi
0x1830fba7d  jz      loc_1830FBBC9
0x1830fba83  mov     [rsp+2858h+var_2808], 1
0x1830fba88  movzx   edx, [rsp+2858h+var_2805]
0x1830fba8d  lea     rcx, [rsp+2858h+var_2788]
0x1830fba95  call    ??0TypelessValue@@QEAA@VTypelessDefault@@@Z; TypelessValue::TypelessValue(TypelessDefault)
0x1830fba9a  mov     [rsp+2858h+var_2838], 1
0x1830fba9f  mov     r9, rax
0x1830fbaa2  mov     r8d, 1
0x1830fbaa8  mov     rdx, rdi
0x1830fbaab  lea     rcx, [rsp+2858h+var_2760]
0x1830fbab3  call    ?Resize@IntMatrix@@QEAAX_K0VTypelessValue@@_N@Z; IntMatrix::Resize(unsigned __int64,unsigned __int64,TypelessValue,bool)
0x1830fbab8  xor     esi, esi
0x1830fbaba  movzx   ebx, [rsp+2858h+var_2805]
0x1830fbabf  nop
0x1830fbac0  cmp     rsi, rdi
0x1830fbac3  jnb     loc_1830FBBBF
0x1830fbac9  mov     rcx, [rsp+2858h+var_2800]
0x1830fbace  call    ??BVarBase@@QEBAPEAVCxVector@@XZ; VarBase::operator CxVector *(void)
0x1830fbad3  mov     rdx, rsi; unsigned __int64
0x1830fbad6  mov     rcx, rax; this
0x1830fbad9  call    ?GetVar0@CxDataSetVector@@QEAAAEAVVar@@_K@Z; CxDataSetVector::GetVar0(unsigned __int64)
0x1830fbade  mov     rcx, rax
0x1830fbae1  call    ?GetVarType@Var@@QEBA?AW4CxVarType@@XZ; Var::GetVarType(void)
0x1830fbae6  mov     edi, eax
0x1830fbae8  cmp     eax, 7
0x1830fbaeb  jnz     short loc_1830FBB51
0x1830fbaed  xor     al, al
0x1830fbaef  mov     [rsp+2858h+var_2808], al
0x1830fbaf3  mov     ecx, 88h; unsigned __int64
0x1830fbaf8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1830fbafd  mov     rdi, rax
0x1830fbb00  mov     [rsp+2858h+var_27D0], rax
0x1830fbb08  test    rax, rax
0x1830fbb0b  jz      short loc_1830FBB3F
0x1830fbb0d  xor     edx, edx; Val
0x1830fbb0f  mov     r8d, 88h; Size
0x1830fbb15  mov     rcx, rax; void *
0x1830fbb18  call    memset_0
0x1830fbb1d  mov     [rsp+2858h+var_2750], 0
0x1830fbb28  lea     r9, [rsp+2858h+var_2750]; int *
0x1830fbb30  xor     edx, edx; unsigned __int64
0x1830fbb32  lea     r8d, [rdx+1]; unsigned __int64
0x1830fbb36  mov     rcx, rdi; this
0x1830fbb39  call    ??0CxIntVector@@QEAA@_K0AEBH@Z; CxIntVector::CxIntVector(unsigned __int64,unsigned __int64,int const &)
0x1830fbb3e  nop
0x1830fbb3f  mov     rdx, rax
0x1830fbb42  lea     rcx, [rsp+2858h+var_2760]
0x1830fbb4a  call    ??4VarBase@@QEAAAEAV0@PEBVCxVector@@@Z; VarBase::operator=(CxVector const *)
0x1830fbb4f  jmp     short loc_1830FBBB2
0x1830fbb51  mov     rdx, rsi
0x1830fbb54  lea     rcx, [rsp+2858h+var_2760]
0x1830fbb5c  call    ??AUIntMatrix@@QEBAAEBI_J@Z; UIntMatrix::operator[](__int64)
0x1830fbb61  mov     [rax], edi
0x1830fbb63  lea     rax, [rsp+2858h+var_2788]
0x1830fbb6b  mov     [rsp+2858h+var_27D0], rax
0x1830fbb73  movzx   edx, bl
0x1830fbb76  lea     rcx, [rsp+2858h+var_2788]
0x1830fbb7e  call    ??0TypelessValue@@QEAA@VTypelessDefault@@@Z; TypelessValue::TypelessValue(TypelessDefault)
0x1830fbb83  mov     rdi, rax
0x1830fbb86  mov     rcx, [rsp+2858h+var_2800]
0x1830fbb8b  call    ??BVarBase@@QEBAPEAVCxVector@@XZ; VarBase::operator CxVector *(void)
0x1830fbb90  mov     rdx, rsi; unsigned __int64
0x1830fbb93  mov     rcx, rax; this
0x1830fbb96  call    ?GetVar0@CxDataSetVector@@QEAAAEAVVar@@_K@Z; CxDataSetVector::GetVar0(unsigned __int64)
0x1830fbb9b  nop
0x1830fbb9c  mov     [rsp+2858h+var_2838], 1
0x1830fbba1  mov     r9, rdi
0x1830fbba4  xor     edx, edx
0x1830fbba6  lea     r8d, [rdx+1]
0x1830fbbaa  mov     rcx, rax
0x1830fbbad  call    ?Resize@Var@@QEAAX_K0VTypelessValue@@_N@Z; Var::Resize(unsigned __int64,unsigned __int64,TypelessValue,bool)
0x1830fbbb2  inc     rsi
0x1830fbbb5  mov     rdi, [rsp+2858h+var_27E0]
0x1830fbbba  jmp     loc_1830FBAC0
0x1830fbbbf  movzx   esi, [rsp+2858h+var_2808]
0x1830fbbc4  mov     rbx, [rsp+2858h+var_27F8]
0x1830fbbc9  mov     rax, [rsp+2858h+arg_20]
0x1830fbbd1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1830fbbd5  mov     rdi, [rsp+2858h+arg_38]
0x1830fbbdd  cmovz   rax, rdi
0x1830fbbe1  mov     [rsp+2858h+var_27A0], rax
0x1830fbbe9  test    sil, sil
0x1830fbbec  jnz     loc_1830FBD91
0x1830fbbf2  cmp     [rsp+2858h+var_27C8], 1
0x1830fbbfb  jbe     loc_1830FBD91
0x1830fbc01  lea     rax, [rsp+2858h+var_27F0]
0x1830fbc06  mov     [rsp+2858h+var_27D0], rax
0x1830fbc0e  lea     rcx, [rsp+2858h+var_27F0]
0x1830fbc13  call    ??0?$CxWrapper@VCxDescriptiveStatsCubeVector@@@@QEAA@XZ; CxWrapper<CxDescriptiveStatsCubeVector>::CxWrapper<CxDescriptiveStatsCubeVector>(void)
0x1830fbc18  nop
0x1830fbc19  mov     rcx, rbx
0x1830fbc1c  call    ??BCxStr@@QEBAPEBDXZ; CxStr::operator char const *(void)
0x1830fbc21  mov     [rsp+2858h+var_2830], sil; bool
0x1830fbc26  mov     [rsp+2858h+var_2838], sil; bool
0x1830fbc2b  mov     r9b, 1; bool
0x1830fbc2e  movzx   r8d, r9b; bool
0x1830fbc32  mov     rdx, rax; struct CxVarHeader *
0x1830fbc35  lea     rcx, [rsp+2858h+var_27F0]; this
0x1830fbc3a  call    ?InitFromHeader@VarBase@@QEAAXPEAVCxVarHeader@@_N111@Z; VarBase::InitFromHeader(CxVarHeader *,bool,bool,bool,bool)
0x1830fbc3f  nop
0x1830fbc40  lea     rax, [rsp+2858h+var_27F0]
0x1830fbc45  mov     [rsp+2858h+var_2810], rax
0x1830fbc4a  mov     rbx, [rsp+2858h+arg_40]
0x1830fbc52  mov     [rsp+2858h+var_2818], rbx
0x1830fbc57  mov     [rsp+2858h+var_2820], rdi
0x1830fbc5c  movzx   edi, [rsp+2858h+arg_30]
0x1830fbc64  mov     [rsp+2858h+var_2828], dil
0x1830fbc69  movzx   esi, [rsp+2858h+arg_28]
0x1830fbc71  mov     [rsp+2858h+var_2830], sil
0x1830fbc76  mov     qword ptr [rsp+2858h+var_2838], rbx
0x1830fbc7b  mov     r9d, 1
0x1830fbc81  mov     r8, [rsp+2858h+var_27C0]
0x1830fbc89  mov     rdx, [rsp+2858h+var_2740]
0x1830fbc91  mov     rcx, [rsp+2858h+var_2800]
0x1830fbc96  call    ?BaseImportTextFileEx@@YA_NAEAVDataSet@@PEBD1_K2_N322VStringMatrix@@@Z; BaseImportTextFileEx(DataSet &,char const *,char const *,unsigned __int64,unsigned __int64,bool,bool,unsigned __int64,unsigned __int64,StringMatrix)
0x1830fbc9b  test    al, al
0x1830fbc9d  jz      loc_1830FBD64
0x1830fbca3  mov     rcx, [rsp+2858h+var_2800]
0x1830fbca8  call    ??BVarBase@@QEBAPEAVCxVector@@XZ; VarBase::operator CxVector *(void)
0x1830fbcad  test    rax, rax
0x1830fbcb0  jz      loc_1830FBD64
0x1830fbcb6  mov     rcx, [rsp+2858h+var_2800]
0x1830fbcbb  call    ??BVarBase@@QEBAPEAVCxVector@@XZ; VarBase::operator CxVector *(void)
0x1830fbcc0  mov     rcx, rax
0x1830fbcc3  call    ?SizeVM@?$CxTemplateVector@V?$CxWrapper@VCxCustomAnalysis@@@@@@UEBA_KXZ; CxTemplateVector<CxWrapper<CxCustomAnalysis>>::SizeVM(void)
0x1830fbcc8  test    rax, rax
0x1830fbccb  jz      loc_1830FBD64
0x1830fbcd1  mov     rdx, [rsp+2858h+var_27F8]; struct StringMatrix *
0x1830fbcd6  lea     rcx, [rsp+2858h+var_27D8]; this
0x1830fbcde  call    ??0StringMatrix@@QEAA@AEBV0@@Z; StringMatrix::StringMatrix(StringMatrix const &)
0x1830fbce3  mov     [rsp+2858h+var_2810], rax
0x1830fbce8  mov     [rsp+2858h+var_2818], rbx
0x1830fbced  mov     rax, [rsp+2858h+arg_38]
0x1830fbcf5  mov     [rsp+2858h+var_2820], rax
0x1830fbcfa  mov     [rsp+2858h+var_2828], dil
0x1830fbcff  mov     [rsp+2858h+var_2830], sil
0x1830fbd04  mov     rax, [rsp+2858h+arg_20]
0x1830fbd0c  mov     qword ptr [rsp+2858h+var_2838], rax
0x1830fbd11  mov     r9, [rsp+2858h+var_27C8]
0x1830fbd19  mov     r8, [rsp+2858h+var_27C0]
0x1830fbd21  mov     rdx, [rsp+2858h+var_2740]
0x1830fbd29  mov     rcx, [rsp+2858h+var_2800]
0x1830fbd2e  call    ?BaseImportTextFileEx@@YA_NAEAVDataSet@@PEBD1_K2_N322VStringMatrix@@@Z; BaseImportTextFileEx(DataSet &,char const *,char const *,unsigned __int64,unsigned __int64,bool,bool,unsigned __int64,unsigned __int64,StringMatrix)
0x1830fbd33  movzx   ebx, al
0x1830fbd36  lea     rcx, [rsp+2858h+var_2760]; this
0x1830fbd3e  call    ??1IntMatrix@@QEAA@XZ; IntMatrix::~IntMatrix(void)
0x1830fbd43  nop
0x1830fbd44  lea     rcx, [rsp+2858h+var_2748]; this
0x1830fbd4c  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x1830fbd51  nop
0x1830fbd52  mov     rcx, [rsp+2858h+var_27F8]; this
0x1830fbd57  call    ??1StringMatrix@@QEAA@XZ; StringMatrix::~StringMatrix(void)
0x1830fbd5c  movzx   eax, bl
0x1830fbd5f  jmp     loc_1830FC3E2
0x1830fbd64  lea     rcx, [rsp+2858h+var_2760]; this
0x1830fbd6c  call    ??1IntMatrix@@QEAA@XZ; IntMatrix::~IntMatrix(void)
0x1830fbd71  nop
0x1830fbd72  lea     rcx, [rsp+2858h+var_2748]; this
0x1830fbd7a  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x1830fbd7f  nop
0x1830fbd80  mov     rcx, [rsp+2858h+var_27F8]; this
0x1830fbd85  call    ??1StringMatrix@@QEAA@XZ; StringMatrix::~StringMatrix(void)
0x1830fbd8a  xor     al, al
0x1830fbd8c  jmp     loc_1830FC3E2
0x1830fbd91  lea     rcx, [rsp+2858h+var_2748]; this
0x1830fbd99  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x1830fbd9e  lea     rdx, aR_2; "r"
0x1830fbda5  mov     rcx, rax; char *
0x1830fbda8  call    ?CxFOpen@@YAPEAU_iobuf@@PEBD0@Z; CxFOpen(char const *,char const *)
0x1830fbdad  mov     rdi, rax
0x1830fbdb0  mov     [rsp+2858h+Stream], rax
0x1830fbdb5  mov     [rsp+2858h+var_27A8], rax
0x1830fbdbd  test    rax, rax
0x1830fbdc0  jnz     short loc_1830FBE02
0x1830fbdc2  mov     rdx, [rsp+2858h+var_27B8]
0x1830fbdca  lea     rcx, aTheFileSCouldN; "The file %s could not be opened."
0x1830fbdd1  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x1830fbdd6  nop
0x1830fbdd7  lea     rcx, [rsp+2858h+var_2760]; this
0x1830fbddf  call    ??1IntMatrix@@QEAA@XZ; IntMatrix::~IntMatrix(void)
0x1830fbde4  nop
0x1830fbde5  lea     rcx, [rsp+2858h+var_2748]; this
0x1830fbded  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x1830fbdf2  nop
0x1830fbdf3  mov     rcx, rbx; this
0x1830fbdf6  call    ??1StringMatrix@@QEAA@XZ; StringMatrix::~StringMatrix(void)
0x1830fbdfb  xor     al, al
0x1830fbdfd  jmp     loc_1830FC3E2
0x1830fbe02  mov     r8, [rsp+2858h+arg_40]
0x1830fbe0a  mov     [rsp+2858h+var_27E0], r8
0x1830fbe0f  movzx   eax, [rsp+2858h+arg_30]
0x1830fbe17  mov     [rsp+2858h+var_2804], al
0x1830fbe1b  movzx   eax, [rsp+2858h+arg_28]
0x1830fbe23  mov     [rsp+2858h+var_2805], al
0x1830fbe27  mov     rcx, rdi; Stream
0x1830fbe2a  call    cs:__imp_feof
0x1830fbe30  movzx   ebx, [rsp+2858h+var_2807]
0x1830fbe35  test    eax, eax
0x1830fbe37  jnz     loc_1830FC3AF
0x1830fbe3d  test    bl, bl
0x1830fbe3f  jz      loc_1830FC3AF
0x1830fbe45  xor     eax, eax
0x1830fbe47  mov     [rsp+2858h+var_2758], rax
0x1830fbe4f  lea     rcx, [rsp+2858h+var_2758]
0x1830fbe57  call    ??0?$CxWrapper@VCxDescriptiveStatsCubeVector@@@@QEAA@XZ; CxWrapper<CxDescriptiveStatsCubeVector>::CxWrapper<CxDescriptiveStatsCubeVector>(void)
0x1830fbe5c  nop
0x1830fbe5d  mov     ecx, 0B8h; unsigned __int64
0x1830fbe62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1830fbe67  mov     rbx, rax
0x1830fbe6a  mov     [rsp+2858h+var_27D8], rax
0x1830fbe72  test    rax, rax
0x1830fbe75  jz      short loc_1830FBE9E
0x1830fbe77  xor     edx, edx; Val
0x1830fbe79  mov     r8d, 0B8h; Size
0x1830fbe7f  mov     rcx, rax; void *
0x1830fbe82  call    memset_0
0x1830fbe87  mov     r8d, 5
0x1830fbe8d  mov     rdx, [rsp+2858h+var_27A0]
0x1830fbe95  mov     rcx, rbx
0x1830fbe98  call    ??0CxDataSetVector@@QEAA@_KW4CxVarType@@@Z; CxDataSetVector::CxDataSetVector(unsigned __int64,CxVarType)
0x1830fbe9d  nop
0x1830fbe9e  mov     [rsp+2858h+var_27D8], rax
0x1830fbea6  mov     rdx, rax; struct CxVector *
0x1830fbea9  lea     rcx, [rsp+2858h+var_2758]; this
0x1830fbeb1  call    ?InitFromVector@VarBase@@QEAAXPEBVCxVector@@@Z; VarBase::InitFromVector(CxVector const *)
0x1830fbeb6  nop
0x1830fbeb7  mov     rax, [rsp+2858h+var_27C8]
0x1830fbebf  cmp     rax, 1
0x1830fbec3  jbe     loc_1830FBF47
0x1830fbec9  mov     ebx, 1
0x1830fbece  xchg    ax, ax
0x1830fbed0  cmp     rbx, rax
0x1830fbed3  jnb     short loc_1830FBF42
0x1830fbed5  mov     r8, rdi; Stream
0x1830fbed8  mov     edx, 2710h; MaxCount
0x1830fbedd  lea     rcx, [rsp+2858h+Buffer]; Buffer
0x1830fbee5  call    cs:__imp_fgets
0x1830fbeeb  test    rax, rax
0x1830fbeee  jnz     short loc_1830FBF35
0x1830fbef0  mov     rcx, rdi; Stream
0x1830fbef3  call    cs:__imp_fclose
0x1830fbef9  nop
0x1830fbefa  lea     rcx, [rsp+2858h+var_2758]; this
0x1830fbf02  call    ??1Var@@QEAA@XZ; Var::~Var(void)
0x1830fbf07  nop
0x1830fbf08  lea     rcx, [rsp+2858h+var_2760]; this
  ... truncated ...
```
