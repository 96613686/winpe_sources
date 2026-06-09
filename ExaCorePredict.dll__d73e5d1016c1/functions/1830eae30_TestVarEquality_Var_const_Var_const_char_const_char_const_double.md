# TestVarEquality(Var const &,Var const &,char const *,char const *,double)

- ea: `0x1830eae30`
- end: `0x1830eb25f`
- name: `?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z`
- size: `1071`
- prototype: `bool __fastcall(const struct Var *, const struct Var *, const char *, const char *, double)`
- caller_count: `18`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1815c1d30`
- `0x1815c2160`
- `0x1815cda70`
- `0x182d46010`
- `0x182d48e80`
- `0x182d48ef0`
- `0x182dbbfd0`
- `0x182fe4fc0`
- `0x18303cd10`
- `0x183059d20`
- `0x183059e30`
- `0x183059f50`
- `0x1830650c0`
- `0x1830ea7f0`
- `0x1830ec370`
- `0x1830ec400`
- `0x1830ec5b0`
- `0x1830ec750`

## callees

- `0x182d41620`
- `0x182dc4440`
- `0x182dcc5d0`
- `0x1830501a0`
- `0x183053010`
- `0x183055940`
- `0x1830e91b0`
- `0x1830e94d0`
- `0x1830ea7f0`
- `0x1830eae30`
- `0x1830f9ed0`
- `0x183292f20`
- `0x183295b50`
- `0x1832aa590`
- `0x1832ab550`
- `0x1832ab5f0`
- `0x1832b0350`
- `0x1832b0990`
- `0x1832b09f0`
- `0x1832b0a10`
- `0x1832b0e70`
- `0x1832b1c00`
- `0x1832ce3b0`

## string_xrefs

- `0x1830eaedb`: `Comparing: %s vs %s: `
- `0x1830eafe2`: `Cannot compare Vars of VarType_FixedRaw!\n`
- `0x1830eb0ba`: `Cannot compare data of DataType_FixedRaw!\n`
- `0x1830eb1e4`: `The Vars are different. There are %d non-identical terms out of %d. Any significant differences will already have been displayed.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_BOOL8 __fastcall TestVarEquality(
        const struct Var *a1,
        const struct Var *a2,
        const char *CharPointer,
        const char *a4,
        double X)
{
  const char *v9; // r12
  const char *v10; // r13
  bool v11; // r14
  unsigned __int64 NumRows; // rbx
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned __int64 NumCols; // rbx
  __int64 v16; // rbx
  __int64 v17; // rax
  bool IsValid; // bl
  bool v19; // al
  unsigned int VarType; // eax
  unsigned int v21; // eax
  int DataType; // ebx
  int v23; // eax
  __int64 *v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // rax
  const struct CxVector *v27; // rax
  __int64 v28; // rax
  int v29; // esi
  __int64 v30; // rax
  int v31; // ebx
  int v33; // [rsp+30h] [rbp-88h]
  int v34; // [rsp+38h] [rbp-80h] BYREF
  __int64 v35; // [rsp+40h] [rbp-78h]
  __int64 v36; // [rsp+48h] [rbp-70h] BYREF
  __int64 v37; // [rsp+50h] [rbp-68h] BYREF
  __int64 v38; // [rsp+58h] [rbp-60h] BYREF

  v35 = -2;
  v38 = 0;
  Var::GetName(a1, &v38);
  v37 = 0;
  Var::GetName(a2, &v37);
  if ( !CharPointer )
    CharPointer = CxString::GetCharPointer((CxString *)&v38);
  if ( !a4 )
    a4 = CxString::GetCharPointer((CxString *)&v37);
  v9 = &Src;
  v10 = &Src;
  if ( CharPointer )
    v10 = CharPointer;
  if ( a4 )
    v9 = a4;
  v11 = 1;
  if ( GetDisplayFlag() )
    CxPrintf("Comparing: %s vs %s: ", v10, v9);
  NumRows = Var::GetNumRows(a1);
  if ( NumRows != Var::GetNumRows(a2) )
  {
    if ( GetDisplayFlag() )
    {
      v13 = *(_QWORD *)(Var::operator->(a2) + 16);
      v14 = Var::operator->(a1);
      CxPrintf("The Vars have different NumRows. %d vs %d\n", *(_QWORD *)(v14 + 16), v13);
    }
    v11 = 0;
  }
  NumCols = Var::GetNumCols(a1);
  if ( NumCols != Var::GetNumCols(a2) )
  {
    if ( GetDisplayFlag() )
    {
      v16 = *(_QWORD *)(Var::operator->(a2) + 24);
      v17 = Var::operator->(a1);
      CxPrintf("The Vars have different NumCols. %d vs %d\n", *(_QWORD *)(v17 + 24), v16);
    }
    v11 = 0;
  }
  IsValid = VarBase::IsValid(a1);
  v19 = VarBase::IsValid(a2);
  if ( !IsValid )
  {
    if ( !v19 )
    {
      v11 = 1;
      goto LABEL_52;
    }
    goto LABEL_23;
  }
  if ( !v19 )
  {
LABEL_23:
    if ( GetDisplayFlag() )
      CxPrintf("One of the Vars has a NULL pointer.\n");
    goto LABEL_26;
  }
  if ( !v11 )
  {
LABEL_26:
    v11 = 0;
    goto LABEL_52;
  }
  if ( (unsigned int)Var::GetVarType(a1) == 22 && (unsigned int)Var::GetVarType(a2) == 22 )
  {
    CxPrintf("Cannot compare Vars of VarType_FixedRaw!\n");
  }
  else
  {
    VarType = Var::GetVarType(a1);
    if ( (unsigned __int8)IsKindOfDataSet(VarType) && (v21 = Var::GetVarType(a2), (unsigned __int8)IsKindOfDataSet(v21)) )
    {
      DataSet::DataSet((DataSet *)&v34, a2);
      DataSet::DataSet((DataSet *)&v36, a1);
      v11 = TestDSEquality((const struct DataSet *)&v36, (const struct DataSet *)&v34, v10, v9, X);
      Var::~Var((Var *)&v36);
      Var::~Var((Var *)&v34);
    }
    else
    {
      DataType = Var::GetDataType(a1);
      v34 = DataType;
      v23 = Var::GetDataType(a2);
      v33 = v23;
      if ( DataType != v23 )
      {
        if ( GetDisplayFlag() )
          CxPrintf("The Vars have different data types.\n");
        v11 = 0;
        v23 = v33;
      }
      if ( DataType == 22 && v23 == 22 )
      {
        CxPrintf("Cannot compare data of DataType_FixedRaw!\n");
      }
      else
      {
        v36 = 0;
        v24 = (__int64 *)Var::operator->(a1);
        v25 = *v24;
        v26 = VarBase::operator CxVector *(a2);
        v27 = (const struct CxVector *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v25 + 816))(v24, v26);
        IntMatrix::IntMatrix((IntMatrix *)&v36, v27);
        v28 = VarBase::operator CxVector *(&v36);
        v29 = (int)(*(double (__fastcall **)(__int64))(*(_QWORD *)v28 + 1000LL))(v28);
        v30 = Var::operator->(a1);
        v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 448LL))(v30);
        if ( v31 == v29 )
        {
          if ( GetDisplayFlag() )
            CxPrintf("The variables '%s' and '%s' are identical.\n", v10, v9);
        }
        else
        {
          v11 = 0;
          if ( (unsigned int)(v34 - 17) <= 1 || v33 == 18 )
          {
            v11 = DisplayDoubleVarDiffs((struct IntMatrix *)&v36, a1, a2, v10, v9, X);
          }
          else if ( (unsigned int)Var::GetVarType(a1) == 24 || (int)Var::GetDataType(a1) < 7 )
          {
            if ( GetDisplayFlag() )
              CxPrintf(
                "The Vars are different. There are %d non-identical terms out of %d. Any significant differences will alr"
                "eady have been displayed.\n",
                v31 - v29,
                v31);
          }
          else
          {
            DisplayDiffs((struct IntMatrix *)&v36, a1, a2, v10, v9);
          }
        }
        IntMatrix::~IntMatrix((IntMatrix *)&v36);
      }
    }
  }
LABEL_52:
  CxString::~CxString((CxString *)&v37);
  CxString::~CxString((CxString *)&v38);
  return v11;
}

```

## disassembly

```asm
0x1830eae30  push    rbx
0x1830eae32  push    rbp
0x1830eae33  push    rsi
0x1830eae34  push    rdi
0x1830eae35  push    r12
0x1830eae37  push    r13
0x1830eae39  push    r14
0x1830eae3b  push    r15
0x1830eae3d  sub     rsp, 78h
0x1830eae41  mov     [rsp+0B8h+var_78], 0FFFFFFFFFFFFFFFEh
0x1830eae4a  mov     rax, cs:__security_cookie
0x1830eae51  xor     rax, rsp
0x1830eae54  mov     [rsp+0B8h+var_58], rax
0x1830eae59  mov     rbx, r9
0x1830eae5c  mov     rdi, r8
0x1830eae5f  mov     r15, rdx
0x1830eae62  mov     rbp, rcx
0x1830eae65  xor     eax, eax
0x1830eae67  mov     [rsp+0B8h+var_60], rax
0x1830eae6c  lea     rdx, [rsp+0B8h+var_60]
0x1830eae71  call    ?GetName@Var@@QEBA?AVCxString@@XZ
0x1830eae76  nop
0x1830eae77  xor     eax, eax
0x1830eae79  mov     [rsp+0B8h+var_68], rax
0x1830eae7e  lea     rdx, [rsp+0B8h+var_68]
0x1830eae83  mov     rcx, r15
0x1830eae86  call    ?GetName@Var@@QEBA?AVCxString@@XZ
0x1830eae8b  nop
0x1830eae8c  test    rdi, rdi
0x1830eae8f  jnz     short loc_1830EAE9E
0x1830eae91  lea     rcx, [rsp+0B8h+var_60]; this
0x1830eae96  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x1830eae9b  mov     rdi, rax
0x1830eae9e  test    rbx, rbx
0x1830eaea1  jnz     short loc_1830EAEB0
0x1830eaea3  lea     rcx, [rsp+0B8h+var_68]; this
0x1830eaea8  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x1830eaead  mov     rbx, rax
0x1830eaeb0  lea     r12, Src
0x1830eaeb7  mov     r13, r12
0x1830eaeba  test    rdi, rdi
0x1830eaebd  cmovnz  r13, rdi
0x1830eaec1  test    rbx, rbx
0x1830eaec4  cmovnz  r12, rbx
0x1830eaec8  mov     r14b, 1
0x1830eaecb  call    ?GetDisplayFlag@@YA_NXZ
0x1830eaed0  cmp     al, r14b
0x1830eaed3  jnz     short loc_1830EAEE7
0x1830eaed5  mov     r8, r12
0x1830eaed8  mov     rdx, r13
0x1830eaedb  lea     rcx, aComparingSVsS
0x1830eaee2  call    ?CxPrintf@@YAXPEBDZZ
0x1830eaee7  mov     rcx, rbp; this
0x1830eaeea  call    ?GetNumRows@Var@@QEBA_KXZ
0x1830eaeef  mov     rbx, rax
0x1830eaef2  mov     rcx, r15; this
0x1830eaef5  call    ?GetNumRows@Var@@QEBA_KXZ
0x1830eaefa  cmp     rbx, rax
0x1830eaefd  jz      short loc_1830EAF32
0x1830eaeff  call    ?GetDisplayFlag@@YA_NXZ
0x1830eaf04  cmp     al, 1
0x1830eaf06  jnz     short loc_1830EAF2F
0x1830eaf08  mov     rcx, r15
0x1830eaf0b  call    ??CVar@@QEBAPEAVCxVector@@XZ
0x1830eaf10  mov     rbx, [rax+10h]
0x1830eaf14  mov     rcx, rbp
0x1830eaf17  call    ??CVar@@QEBAPEAVCxVector@@XZ
0x1830eaf1c  mov     r8, rbx
0x1830eaf1f  mov     rdx, [rax+10h]
0x1830eaf23  lea     rcx, aTheVarsHaveDif
0x1830eaf2a  call    ?CxPrintf@@YAXPEBDZZ
0x1830eaf2f  xor     r14b, r14b
0x1830eaf32  mov     rcx, rbp; this
0x1830eaf35  call    ?GetNumCols@Var@@QEBA_KXZ
0x1830eaf3a  mov     rbx, rax
0x1830eaf3d  mov     rcx, r15; this
0x1830eaf40  call    ?GetNumCols@Var@@QEBA_KXZ
0x1830eaf45  cmp     rbx, rax
0x1830eaf48  jz      short loc_1830EAF7D
0x1830eaf4a  call    ?GetDisplayFlag@@YA_NXZ
0x1830eaf4f  cmp     al, 1
0x1830eaf51  jnz     short loc_1830EAF7A
0x1830eaf53  mov     rcx, r15
0x1830eaf56  call    ??CVar@@QEBAPEAVCxVector@@XZ
0x1830eaf5b  mov     rbx, [rax+18h]
0x1830eaf5f  mov     rcx, rbp
0x1830eaf62  call    ??CVar@@QEBAPEAVCxVector@@XZ
0x1830eaf67  mov     r8, rbx
0x1830eaf6a  mov     rdx, [rax+18h]
0x1830eaf6e  lea     rcx, aTheVarsHaveDif_1
0x1830eaf75  call    ?CxPrintf@@YAXPEBDZZ
0x1830eaf7a  xor     r14b, r14b
0x1830eaf7d  mov     rcx, rbp; this
0x1830eaf80  call    ?IsValid@VarBase@@QEBA_NXZ
0x1830eaf85  movzx   ebx, al
0x1830eaf88  mov     rcx, r15; this
0x1830eaf8b  call    ?IsValid@VarBase@@QEBA_NXZ
0x1830eaf90  test    bl, bl
0x1830eaf92  jnz     short loc_1830EAFA0
0x1830eaf94  test    al, al
0x1830eaf96  jnz     short loc_1830EAFA4
0x1830eaf98  mov     r14b, 1
0x1830eaf9b  jmp     loc_1830EB228
0x1830eafa0  test    al, al
0x1830eafa2  jnz     short loc_1830EAFBB
0x1830eafa4  call    ?GetDisplayFlag@@YA_NXZ
0x1830eafa9  cmp     al, 1
0x1830eafab  jnz     short loc_1830EAFC0
0x1830eafad  lea     rcx, aOneOfTheVarsHa
0x1830eafb4  call    ?CxPrintf@@YAXPEBDZZ
0x1830eafb9  jmp     short loc_1830EAFC0
0x1830eafbb  test    r14b, r14b
0x1830eafbe  jnz     short loc_1830EAFC8
0x1830eafc0  xor     r14b, r14b
0x1830eafc3  jmp     loc_1830EB228
0x1830eafc8  mov     rcx, rbp
0x1830eafcb  call    ?GetVarType@Var@@QEBA?AW4CxVarType@@XZ
0x1830eafd0  cmp     eax, 16h
0x1830eafd3  jnz     short loc_1830EAFF3
0x1830eafd5  mov     rcx, r15
0x1830eafd8  call    ?GetVarType@Var@@QEBA?AW4CxVarType@@XZ
0x1830eafdd  cmp     eax, 16h
0x1830eafe0  jnz     short loc_1830EAFF3
0x1830eafe2  lea     rcx, aCannotCompareV
0x1830eafe9  call    ?CxPrintf@@YAXPEBDZZ
0x1830eafee  jmp     loc_1830EB228
0x1830eaff3  mov     rcx, rbp
0x1830eaff6  call    ?GetVarType@Var@@QEBA?AW4CxVarType@@XZ
0x1830eaffb  mov     ecx, eax
0x1830eaffd  call    ?IsKindOfDataSet@@YA_NW4CxVarType@@@Z
0x1830eb002  test    al, al
0x1830eb004  jz      short loc_1830EB077
0x1830eb006  mov     rcx, r15
0x1830eb009  call    ?GetVarType@Var@@QEBA?AW4CxVarType@@XZ
0x1830eb00e  mov     ecx, eax
0x1830eb010  call    ?IsKindOfDataSet@@YA_NW4CxVarType@@@Z
0x1830eb015  test    al, al
0x1830eb017  jz      short loc_1830EB077
0x1830eb019  mov     rdx, r15; struct Var *
0x1830eb01c  lea     rcx, [rsp+0B8h+var_80]; this
0x1830eb021  call    ??0DataSet@@QEAA@AEBVVar@@@Z
0x1830eb026  nop
0x1830eb027  mov     rdx, rbp; struct Var *
0x1830eb02a  lea     rcx, [rsp+0B8h+var_70]; this
0x1830eb02f  call    ??0DataSet@@QEAA@AEBVVar@@@Z
0x1830eb034  nop
0x1830eb035  movsd   xmm0, [rsp+0B8h+arg_20]
0x1830eb03e  movsd   [rsp+0B8h+var_98], xmm0; double
0x1830eb044  mov     r9, r12; char *
0x1830eb047  mov     r8, r13; char *
0x1830eb04a  lea     rdx, [rsp+0B8h+var_80]; struct DataSet *
0x1830eb04f  lea     rcx, [rsp+0B8h+var_70]; this
0x1830eb054  call    ?TestDSEquality@@YA_NAEBVDataSet@@0PEBD1N@Z
0x1830eb059  movzx   r14d, al
0x1830eb05d  lea     rcx, [rsp+0B8h+var_70]; this
0x1830eb062  call    ??1Var@@QEAA@XZ
0x1830eb067  nop
0x1830eb068  lea     rcx, [rsp+0B8h+var_80]; this
0x1830eb06d  call    ??1Var@@QEAA@XZ
0x1830eb072  jmp     loc_1830EB228
0x1830eb077  mov     rcx, rbp
0x1830eb07a  call    ?GetDataType@Var@@QEBA?AW4CxDataType@@XZ
0x1830eb07f  mov     ebx, eax
0x1830eb081  mov     [rsp+0B8h+var_80], eax
0x1830eb085  mov     rcx, r15
0x1830eb088  call    ?GetDataType@Var@@QEBA?AW4CxDataType@@XZ
0x1830eb08d  mov     [rsp+0B8h+var_88], eax
0x1830eb091  cmp     ebx, eax
0x1830eb093  jz      short loc_1830EB0B1
0x1830eb095  call    ?GetDisplayFlag@@YA_NXZ
0x1830eb09a  cmp     al, 1
0x1830eb09c  jnz     short loc_1830EB0AA
0x1830eb09e  lea     rcx, aTheVarsHaveDif_0
0x1830eb0a5  call    ?CxPrintf@@YAXPEBDZZ
0x1830eb0aa  xor     r14b, r14b
0x1830eb0ad  mov     eax, [rsp+0B8h+var_88]
0x1830eb0b1  cmp     ebx, 16h
0x1830eb0b4  jnz     short loc_1830EB0CB
0x1830eb0b6  cmp     eax, ebx
0x1830eb0b8  jnz     short loc_1830EB0CB
0x1830eb0ba  lea     rcx, aCannotCompareD
0x1830eb0c1  call    ?CxPrintf@@YAXPEBDZZ
0x1830eb0c6  jmp     loc_1830EB228
0x1830eb0cb  xor     eax, eax
0x1830eb0cd  mov     [rsp+0B8h+var_70], rax
0x1830eb0d2  mov     rcx, rbp
0x1830eb0d5  call    ??CVar@@QEBAPEAVCxVector@@XZ
0x1830eb0da  mov     rsi, rax
0x1830eb0dd  mov     rdi, [rax]
0x1830eb0e0  mov     rcx, r15
0x1830eb0e3  call    ??BVarBase@@QEBAPEAVCxVector@@XZ
0x1830eb0e8  mov     rbx, rax
0x1830eb0eb  mov     rdi, [rdi+330h]
0x1830eb0f2  mov     rcx, rdi; this
0x1830eb0f5  call    cs:__guard_check_icall_fptr
0x1830eb0fb  mov     rdx, rbx
0x1830eb0fe  mov     rcx, rsi
0x1830eb101  call    rdi
0x1830eb103  mov     rdx, rax; struct CxVector *
0x1830eb106  lea     rcx, [rsp+0B8h+var_70]; this
0x1830eb10b  call    ??0IntMatrix@@QEAA@PEBVCxVector@@@Z
0x1830eb110  nop
0x1830eb111  lea     rcx, [rsp+0B8h+var_70]
0x1830eb116  call    ??BVarBase@@QEBAPEAVCxVector@@XZ
0x1830eb11b  mov     rdi, rax
0x1830eb11e  mov     rcx, [rax]
0x1830eb121  mov     rbx, [rcx+3E8h]
0x1830eb128  mov     rcx, rbx; this
0x1830eb12b  call    cs:__guard_check_icall_fptr
0x1830eb131  mov     rcx, rdi
0x1830eb134  call    rbx
0x1830eb136  cvttsd2si esi, xmm0
0x1830eb13a  mov     rcx, rbp
0x1830eb13d  call    ??CVar@@QEBAPEAVCxVector@@XZ
0x1830eb142  mov     rdi, rax
0x1830eb145  mov     rcx, [rax]
0x1830eb148  mov     rbx, [rcx+1C0h]
0x1830eb14f  mov     rcx, rbx; this
0x1830eb152  call    cs:__guard_check_icall_fptr
0x1830eb158  mov     rcx, rdi
0x1830eb15b  call    rbx
0x1830eb15d  mov     rbx, rax
0x1830eb160  mov     edi, eax
0x1830eb162  sub     edi, esi
0x1830eb164  cmp     eax, esi
0x1830eb166  jnz     short loc_1830EB18C
0x1830eb168  call    ?GetDisplayFlag@@YA_NXZ
0x1830eb16d  cmp     al, 1
0x1830eb16f  jnz     loc_1830EB21D
0x1830eb175  mov     r8, r12
0x1830eb178  mov     rdx, r13
0x1830eb17b  lea     rcx, aTheVariablesSA
0x1830eb182  call    ?CxPrintf@@YAXPEBDZZ
0x1830eb187  jmp     loc_1830EB21D
0x1830eb18c  xor     r14b, r14b
0x1830eb18f  mov     eax, [rsp+0B8h+var_80]
0x1830eb193  add     eax, 0FFFFFFEFh
0x1830eb196  cmp     eax, 1
0x1830eb199  jbe     short loc_1830EB1F2
0x1830eb19b  cmp     [rsp+0B8h+var_88], 12h
0x1830eb1a0  jz      short loc_1830EB1F2
0x1830eb1a2  mov     rcx, rbp
0x1830eb1a5  call    ?GetVarType@Var@@QEBA?AW4CxVarType@@XZ
0x1830eb1aa  cmp     eax, 18h
0x1830eb1ad  jz      short loc_1830EB1D6
0x1830eb1af  mov     rcx, rbp
0x1830eb1b2  call    ?GetDataType@Var@@QEBA?AW4CxDataType@@XZ
0x1830eb1b7  cmp     eax, 7
0x1830eb1ba  jl      short loc_1830EB1D6
0x1830eb1bc  mov     [rsp+0B8h+var_98], r12; char *
0x1830eb1c1  mov     r9, r13; char *
0x1830eb1c4  mov     r8, r15; struct Var *
0x1830eb1c7  mov     rdx, rbp; struct Var *
0x1830eb1ca  lea     rcx, [rsp+0B8h+var_70]; struct IntMatrix *
0x1830eb1cf  call    ?DisplayDiffs@@YAXAEAVIntMatrix@@AEBVVar@@1PEBD2@Z
0x1830eb1d4  jmp     short loc_1830EB21D
0x1830eb1d6  call    ?GetDisplayFlag@@YA_NXZ
0x1830eb1db  cmp     al, 1
0x1830eb1dd  jnz     short loc_1830EB21D
0x1830eb1df  mov     r8d, ebx
0x1830eb1e2  mov     edx, edi
0x1830eb1e4  lea     rcx, aTheVarsAreDiff
0x1830eb1eb  call    ?CxPrintf@@YAXPEBDZZ
0x1830eb1f0  jmp     short loc_1830EB21D
0x1830eb1f2  movsd   xmm0, [rsp+0B8h+arg_20]
0x1830eb1fb  movsd   [rsp+0B8h+X], xmm0; X
0x1830eb201  mov     [rsp+0B8h+var_98], r12; char *
0x1830eb206  mov     r9, r13; char *
0x1830eb209  mov     r8, r15; struct Var *
0x1830eb20c  mov     rdx, rbp; struct Var *
0x1830eb20f  lea     rcx, [rsp+0B8h+var_70]; struct IntMatrix *
0x1830eb214  call    ?DisplayDoubleVarDiffs@@YA_NAEAVIntMatrix@@AEBVVar@@1PEBD2N@Z
0x1830eb219  movzx   r14d, al
0x1830eb21d  lea     rcx, [rsp+0B8h+var_70]; this
0x1830eb222  call    ??1IntMatrix@@QEAA@XZ
0x1830eb227  nop
0x1830eb228  lea     rcx, [rsp+0B8h+var_68]; this
0x1830eb22d  call    ??1CxString@@QEAA@XZ
0x1830eb232  nop
0x1830eb233  lea     rcx, [rsp+0B8h+var_60]; this
0x1830eb238  call    ??1CxString@@QEAA@XZ
0x1830eb23d  movzx   eax, r14b
0x1830eb241  mov     rcx, [rsp+0B8h+var_58]
0x1830eb246  xor     rcx, rsp; StackCookie
0x1830eb249  call    __security_check_cookie
0x1830eb24e  add     rsp, 78h
0x1830eb252  pop     r15
0x1830eb254  pop     r14
0x1830eb256  pop     r13
0x1830eb258  pop     r12
0x1830eb25a  pop     rdi
0x1830eb25b  pop     rsi
0x1830eb25c  pop     rbp
0x1830eb25d  pop     rbx
0x1830eb25e  retn
```
