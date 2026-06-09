# CxDataSetVector::WriteToTextFile(char const *,int,char const *,int,char const *,bool,bool,bool,bool,bool)

- ea: `0x182d463f0`
- end: `0x182d46784`
- name: `?WriteToTextFile@CxDataSetVector@@QEAA_NPEBDH0H0_N1111@Z`
- size: `916`
- prototype: `bool __usercall@<al>(CxDataSetVector *__hidden this@<rcx>, const char *@<rdx>, int@<r8d>, const char *@<r9>, int, const char *, bool, bool, bool, bool, bool)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x1832b8310`

## callees

- `0x182d3efe0`
- `0x182d41df0`
- `0x182d438c0`
- `0x182d463f0`
- `0x182d47420`
- `0x182dcc6d0`
- `0x18304feb0`
- `0x1830509c0`
- `0x183051f80`
- `0x183053010`
- `0x183055940`
- `0x1830e8d10`
- `0x1830f9f30`
- `0x1830fee50`
- `0x1830fee80`
- `0x1832aa590`
- `0x1832ab550`
- `0x1832ce3b0`
- `0x1832dbeb0`

## import_xrefs

- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x182d46594`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x182d46594`
- `MSVCP140!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x182d464bb`
- `MSVCP140!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x182d464bb`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x182d46758`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x182d46758`
- `MSVCP140!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x182d46466`
- `MSVCP140!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x182d46466`
- `MSVCP140!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x182d46482`
- `MSVCP140!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x182d46482`
- `MSVCP140!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x182d4674e`
- `MSVCP140!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x182d4674e`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x182d465b6`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x182d465b6`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x182d464d9`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x182d464d9`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x182d465a1`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x182d465a1`

## string_xrefs

- `0x182d4670b`: `A file name must be specified in 'WriteToTextFile()'.`
- `0x182d465cf`: `Cannot open the file '%s' for writing.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CxDataSetVector::WriteToTextFile(
        CxDataSetVector *this,
        const char *a2,
        int a3,
        const char *a4,
        int a5,
        const char *a6,
        bool a7,
        char a8,
        char a9,
        char a10,
        bool a11)
{
  const char *DefaultDataDir; // rax
  const char *CharPointer; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  const char *v19; // rax
  unsigned __int8 v20; // bl
  struct CxDataSetVector *v21; // rax
  __int64 NumVars; // rdi
  unsigned __int64 NumRows; // rbx
  unsigned __int64 RowDisplayMax; // rsi
  int v25; // eax
  char v27; // [rsp+20h] [rbp-F0h]
  char v28; // [rsp+28h] [rbp-E8h]
  char v29; // [rsp+30h] [rbp-E0h]
  char v30; // [rsp+38h] [rbp-D8h]
  char v31; // [rsp+40h] [rbp-D0h]
  char v32; // [rsp+48h] [rbp-C8h]
  char v33; // [rsp+50h] [rbp-C0h]
  char v34; // [rsp+58h] [rbp-B8h]
  char v35; // [rsp+60h] [rbp-B0h]
  bool v36; // [rsp+90h] [rbp-80h] BYREF
  bool v37; // [rsp+91h] [rbp-7Fh] BYREF
  int v38; // [rsp+94h] [rbp-7Ch]
  __int64 v39; // [rsp+98h] [rbp-78h]
  void ***v40; // [rsp+A0h] [rbp-70h]
  int v41; // [rsp+ACh] [rbp-64h]
  int *v42; // [rsp+B0h] [rbp-60h] BYREF
  void **v43; // [rsp+B8h] [rbp-58h] BYREF
  _BYTE v44[96]; // [rsp+C0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+120h] [rbp+10h]
  char v46; // [rsp+129h] [rbp+19h]
  __int64 v47; // [rsp+12Ch] [rbp+1Ch]
  char v48; // [rsp+134h] [rbp+24h]
  __int64 v49; // [rsp+138h] [rbp+28h]
  _BYTE v50[104]; // [rsp+158h] [rbp+48h] BYREF
  __int64 v51; // [rsp+1C0h] [rbp+B0h] BYREF
  __int64 v52; // [rsp+1C8h] [rbp+B8h] BYREF

  v39 = -2;
  memset_0(&v42, 0, 0x108u);
  v42 = (int *)&std::ofstream::`vbtable';
  std::ios::ios(v50);
  v38 = 1;
  std::ostream::ostream(&v42, &v43, 0, 0);
  *(int **)((char *)&v42 + v42[1]) = (int *)&std::ofstream::`vftable';
  *(int *)((char *)&v41 + v42[1]) = v42[1] - 168;
  v40 = &v43;
  std::streambuf::streambuf(&v43);
  v43 = &std::filebuf::`vftable';
  v48 = 0;
  v46 = 0;
  std::streambuf::_Init(&v43);
  v49 = 0;
  v47 = `std::filebuf::_Init'::`2'::_Stinit;
  v45 = 0;
  if ( a2 && *a2 )
  {
    v52 = 0;
    DefaultDataDir = GetDefaultDataDir();
    v35 = 0;
    v34 = 1;
    v33 = 0;
    v32 = 0;
    v31 = 0;
    v30 = 1;
    v29 = 0;
    v28 = 0;
    v27 = 0;
    CheckAndFixDataFileName(&v52, a2, ".txt", DefaultDataDir, v27, v28, v29, v30, v31, v32, v33, v34, v35);
    CharPointer = CxString::GetCharPointer((CxString *)&v52);
    v17 = std::filebuf::open((__int64)&v43, CharPointer, 34, 64);
    v18 = v42[1];
    if ( v17 )
      std::ios::clear((char *)&v42 + v18, 0, 0);
    else
      std::ios::setstate((char *)&v42 + v18, 2);
    if ( (unsigned __int8)std::ios_base::operator!((char *)&v42 + v42[1]) )
    {
      v19 = CxString::GetCharPointer((CxString *)&v52);
      CxReportError("Cannot open the file '%s' for writing.", v19);
      v20 = 0;
    }
    else
    {
      v37 = 0;
      v36 = 0;
      v51 = 0;
      v21 = CxDataSetVector::Rearrange(this, &v37, &v36, 1, a11);
      DataSet::DataSet((DataSet *)&v51, v21, 0, 0, 0, 0);
      NumVars = DataSet::GetNumVars((DataSet *)&v51);
      NumRows = DataSet::GetNumRows((DataSet *)&v51);
      RowDisplayMax = GetRowDisplayMax();
      SetRowDisplayMax(NumRows);
      v25 = VarBase::operator CxVector *(&v51);
      CxDataSetVector::PutCoutData(
        v25,
        (unsigned int)&v42,
        a7,
        a3,
        (__int64)a6,
        a5,
        a8,
        a9,
        (__int64)a4,
        a10,
        NumVars,
        -1,
        0,
        -1,
        7,
        0,
        -1);
      SetRowDisplayMax(RowDisplayMax);
      v20 = 1;
      Var::~Var((Var *)&v51);
    }
    CxString::~CxString((CxString *)&v52);
  }
  else
  {
    CxReportError("A file name must be specified in 'WriteToTextFile()'.");
    v20 = 0;
  }
  *(int **)((char *)&v42 + v42[1]) = (int *)&std::ofstream::`vftable';
  *(int *)((char *)&v41 + v42[1]) = v42[1] - 168;
  std::filebuf::~filebuf<char,std::char_traits<char>>(&v43);
  std::ostream::~ostream<char,std::char_traits<char>>(v44);
  std::ios::~ios<char,std::char_traits<char>>(v50);
  return v20;
}

```

## disassembly

```asm
0x182d463f0  push    rbp
0x182d463f2  push    rbx
0x182d463f3  push    rsi
0x182d463f4  push    rdi
0x182d463f5  push    r12
0x182d463f7  push    r13
0x182d463f9  push    r14
0x182d463fb  push    r15
0x182d463fd  lea     rbp, [rsp-0D8h]
0x182d46405  sub     rsp, 1E8h
0x182d4640c  mov     [rbp+110h+var_188], 0FFFFFFFFFFFFFFFEh
0x182d46414  mov     rax, cs:__security_cookie
0x182d4641b  xor     rax, rsp
0x182d4641e  mov     [rbp+110h+var_50], rax
0x182d46425  mov     r15, r9
0x182d46428  mov     r14d, r8d
0x182d4642b  mov     rbx, rdx
0x182d4642e  mov     rdi, rcx
0x182d46431  mov     r12, [rbp+110h+arg_28]
0x182d46438  movzx   esi, [rbp+110h+arg_50]
0x182d4643f  xor     r13d, r13d
0x182d46442  mov     [rbp+110h+var_18C], r13d
0x182d46446  xor     edx, edx; Val
0x182d46448  mov     r8d, 108h; Size
0x182d4644e  lea     rcx, [rbp+110h+var_170]; void *
0x182d46452  call    memset_0
0x182d46457  lea     rax, ??_8?$basic_ofstream@DU?$char_traits@D@std@@@std@@7B@; const std::ofstream::`vbtable'
0x182d4645e  mov     [rbp+110h+var_170], rax
0x182d46462  lea     rcx, [rbp+110h+var_C8]
0x182d46466  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x182d4646c  nop
0x182d4646d  mov     [rbp+110h+var_18C], 1
0x182d46474  xor     r9d, r9d
0x182d46477  xor     r8d, r8d
0x182d4647a  lea     rdx, [rbp+110h+var_168]
0x182d4647e  lea     rcx, [rbp+110h+var_170]
0x182d46482  call    cs:__imp_??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::ostream::ostream(std::streambuf *,bool)
0x182d46488  nop
0x182d46489  mov     rax, [rbp+110h+var_170]
0x182d4648d  movsxd  rcx, dword ptr [rax+4]
0x182d46491  lea     rax, ??_7?$basic_ofstream@DU?$char_traits@D@std@@@std@@6B@; const std::ofstream::`vftable'
0x182d46498  mov     [rbp+rcx+110h+var_170], rax
0x182d4649d  mov     rax, [rbp+110h+var_170]
0x182d464a1  movsxd  rcx, dword ptr [rax+4]
0x182d464a5  lea     edx, [rcx-0A8h]
0x182d464ab  mov     [rbp+rcx+110h+var_174], edx
0x182d464af  lea     rax, [rbp+110h+var_168]
0x182d464b3  mov     [rbp+110h+var_180], rax
0x182d464b7  lea     rcx, [rbp+110h+var_168]
0x182d464bb  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x182d464c1  nop
0x182d464c2  lea     rax, ??_7?$basic_filebuf@DU?$char_traits@D@std@@@std@@6B@; const std::filebuf::`vftable'
0x182d464c9  mov     [rbp+110h+var_168], rax
0x182d464cd  mov     [rbp+110h+var_EC], r13b
0x182d464d1  mov     [rbp+110h+var_F7], r13b
0x182d464d5  lea     rcx, [rbp+110h+var_168]
0x182d464d9  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x182d464df  mov     [rbp+110h+var_E8], r13
0x182d464e3  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)'::`2'::_Stinit
0x182d464ea  mov     [rbp+110h+var_F4], rax
0x182d464ee  mov     [rbp+110h+var_100], r13
0x182d464f2  test    rbx, rbx
0x182d464f5  jz      loc_182D4670B
0x182d464fb  cmp     [rbx], r13b
0x182d464fe  jz      loc_182D4670B
0x182d46504  xor     eax, eax
0x182d46506  mov     [rbp+110h+var_58], rax
0x182d4650d  call    ?GetDefaultDataDir@@YAPEBDXZ; GetDefaultDataDir(void)
0x182d46512  mov     r9, rax
0x182d46515  mov     byte ptr [rsp+220h+var_1C0], r13b
0x182d4651a  mov     byte ptr [rsp+220h+var_1C8], 1
0x182d4651f  mov     byte ptr [rsp+220h+var_1D0], r13b
0x182d46524  mov     [rsp+220h+var_1D8], r13b
0x182d46529  mov     byte ptr [rsp+220h+var_1E0], r13b
0x182d4652e  mov     [rsp+220h+var_1E8], 1
0x182d46533  mov     [rsp+220h+var_1F0], r13b
0x182d46538  mov     byte ptr [rsp+220h+var_1F8], r13b
0x182d4653d  mov     byte ptr [rsp+220h+var_200], r13b
0x182d46542  lea     r8, aTxt; ".txt"
0x182d46549  mov     rdx, rbx
0x182d4654c  lea     rcx, [rbp+110h+var_58]
0x182d46553  call    ?CheckAndFixDataFileName@@YA?AVCxString@@PEBD_N11111@Z; CheckAndFixDataFileName(char const *,bool,bool,bool,bool,bool,bool)
0x182d46558  nop
0x182d46559  lea     rcx, [rbp+110h+var_58]; this
0x182d46560  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x182d46565  lea     r9d, [r13+40h]
0x182d46569  lea     r8d, [r13+22h]
0x182d4656d  mov     rdx, rax
0x182d46570  lea     rcx, [rbp+110h+var_168]
0x182d46574  call    ?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBDHH@Z; std::filebuf::open(char const *,int,int)
0x182d46579  xor     r8d, r8d
0x182d4657c  test    rax, rax
0x182d4657f  mov     rax, [rbp+110h+var_170]
0x182d46583  movsxd  rcx, dword ptr [rax+4]
0x182d46587  lea     rax, [rbp+110h+var_170]
0x182d4658b  jnz     short loc_182D4659C
0x182d4658d  add     rcx, rax
0x182d46590  lea     edx, [r13+2]
0x182d46594  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x182d4659a  jmp     short loc_182D465A7
0x182d4659c  add     rcx, rax
0x182d4659f  xor     edx, edx
0x182d465a1  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x182d465a7  mov     rax, [rbp+110h+var_170]
0x182d465ab  movsxd  rcx, dword ptr [rax+4]
0x182d465af  lea     rax, [rbp+110h+var_170]
0x182d465b3  add     rcx, rax
0x182d465b6  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x182d465bc  test    al, al
0x182d465be  jz      short loc_182D465E2
0x182d465c0  lea     rcx, [rbp+110h+var_58]; this
0x182d465c7  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x182d465cc  mov     rdx, rax
0x182d465cf  lea     rcx, aCannotOpenTheF; "Cannot open the file '%s' for writing."
0x182d465d6  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182d465db  xor     bl, bl
0x182d465dd  jmp     loc_182D466FD
0x182d465e2  mov     [rbp+110h+var_18F], 0
0x182d465e6  mov     [rbp+110h+var_190], 0
0x182d465ea  xor     eax, eax
0x182d465ec  mov     [rbp+110h+var_60], rax
0x182d465f3  mov     byte ptr [rsp+220h+var_200], sil; bool
0x182d465f8  mov     r9b, 1; bool
0x182d465fb  lea     r8, [rbp+110h+var_190]; bool *
0x182d465ff  lea     rdx, [rbp+110h+var_18F]; bool *
0x182d46603  mov     rcx, rdi; this
0x182d46606  call    ?Rearrange@CxDataSetVector@@QEBAPEAV1@AEA_N0_N1@Z; CxDataSetVector::Rearrange(bool &,bool &,bool,bool)
0x182d4660b  mov     rdx, rax; struct CxDataSetVector *
0x182d4660e  mov     [rsp+220h+var_1F8], r13; struct CxStringVector *
0x182d46613  mov     [rsp+220h+var_200], r13; struct CxLogicalVector *
0x182d46618  xor     r9d, r9d; bool
0x182d4661b  xor     r8d, r8d; bool
0x182d4661e  lea     rcx, [rbp+110h+var_60]; this
0x182d46625  call    ??0DataSet@@QEAA@PEAVCxDataSetVector@@_N1PEBVCxLogicalVector@@PEBVCxStringVector@@@Z; DataSet::DataSet(CxDataSetVector *,bool,bool,CxLogicalVector const *,CxStringVector const *)
0x182d4662a  nop
0x182d4662b  lea     rcx, [rbp+110h+var_60]; this
0x182d46632  call    ?GetNumVars@DataSet@@QEBA_KXZ; DataSet::GetNumVars(void)
0x182d46637  mov     rdi, rax
0x182d4663a  lea     rcx, [rbp+110h+var_60]; this
0x182d46641  call    ?GetNumRows@DataSet@@QEBA_KXZ; DataSet::GetNumRows(void)
0x182d46646  mov     rbx, rax
0x182d46649  call    ?GetRowDisplayMax@@YA_KXZ; GetRowDisplayMax(void)
0x182d4664e  mov     rsi, rax
0x182d46651  mov     rcx, rbx; unsigned __int64
0x182d46654  call    ?SetRowDisplayMax@@YAX_K@Z; SetRowDisplayMax(unsigned __int64)
0x182d46659  lea     rcx, [rbp+110h+var_60]
0x182d46660  call    ??BVarBase@@QEBAPEAVCxVector@@XZ; VarBase::operator CxVector *(void)
0x182d46665  mov     rcx, rax
0x182d46668  mov     [rsp+220h+var_1A0], 0FFFFFFFFFFFFFFFFh
0x182d46674  mov     [rsp+220h+var_1A8], r13
0x182d46679  mov     [rsp+220h+var_1B0], 7
0x182d46681  mov     [rsp+220h+var_1B8], 0FFFFFFFFFFFFFFFFh
0x182d4668a  mov     [rsp+220h+var_1C0], r13
0x182d4668f  mov     [rsp+220h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x182d46698  mov     [rsp+220h+var_1D0], rdi
0x182d4669d  movzx   edx, [rbp+110h+arg_48]
0x182d466a4  mov     [rsp+220h+var_1D8], dl
0x182d466a8  mov     [rsp+220h+var_1E0], r15
0x182d466ad  movzx   eax, [rbp+110h+arg_40]
0x182d466b4  mov     [rsp+220h+var_1E8], al
0x182d466b8  movzx   eax, [rbp+110h+arg_38]
0x182d466bf  mov     [rsp+220h+var_1F0], al
0x182d466c3  mov     eax, [rbp+110h+arg_20]
0x182d466c9  mov     dword ptr [rsp+220h+var_1F8], eax
0x182d466cd  mov     [rsp+220h+var_200], r12
0x182d466d2  mov     r9d, r14d
0x182d466d5  movzx   r8d, [rbp+110h+arg_30]
0x182d466dd  lea     rdx, [rbp+110h+var_170]
0x182d466e1  call    ?PutCoutData@CxDataSetVector@@QEAAAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@AEAV23@_NHPEBDH1121_K33_JH44@Z; CxDataSetVector::PutCoutData(std::ostream &,bool,int,char const *,int,bool,bool,char const *,bool,unsigned __int64,unsigned __int64,unsigned __int64,__int64,int,__int64,__int64)
0x182d466e6  mov     rcx, rsi; unsigned __int64
0x182d466e9  call    ?SetRowDisplayMax@@YAX_K@Z; SetRowDisplayMax(unsigned __int64)
0x182d466ee  mov     bl, 1
0x182d466f0  lea     rcx, [rbp+110h+var_60]; this
0x182d466f7  call    ??1Var@@QEAA@XZ; Var::~Var(void)
0x182d466fc  nop
0x182d466fd  lea     rcx, [rbp+110h+var_58]; this
0x182d46704  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x182d46709  jmp     short loc_182D46719
0x182d4670b  lea     rcx, aAFileNameMustB; "A file name must be specified in 'Write"...
0x182d46712  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182d46717  xor     bl, bl
0x182d46719  mov     rcx, [rbp+110h+var_170]
0x182d4671d  movsxd  rdx, dword ptr [rcx+4]
0x182d46721  lea     rax, ??_7?$basic_ofstream@DU?$char_traits@D@std@@@std@@6B@; const std::ofstream::`vftable'
0x182d46728  mov     [rbp+rdx+110h+var_170], rax
0x182d4672d  mov     rcx, [rbp+110h+var_170]
0x182d46731  movsxd  rdx, dword ptr [rcx+4]
0x182d46735  lea     r8d, [rdx-0A8h]
0x182d4673c  mov     [rbp+rdx+110h+var_174], r8d
0x182d46741  lea     rcx, [rbp+110h+var_168]
0x182d46745  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x182d4674a  lea     rcx, [rbp+110h+var_160]
0x182d4674e  call    cs:__imp_??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ostream::~ostream<char,std::char_traits<char>>(void)
0x182d46754  lea     rcx, [rbp+110h+var_C8]
0x182d46758  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x182d4675e  movzx   eax, bl
0x182d46761  mov     rcx, [rbp+110h+var_50]
0x182d46768  xor     rcx, rsp; StackCookie
0x182d4676b  call    __security_check_cookie
0x182d46770  add     rsp, 1E8h
0x182d46777  pop     r15
0x182d46779  pop     r14
0x182d4677b  pop     r13
0x182d4677d  pop     r12
0x182d4677f  pop     rdi
0x182d46780  pop     rsi
0x182d46781  pop     rbx
0x182d46782  pop     rbp
0x182d46783  retn
```
