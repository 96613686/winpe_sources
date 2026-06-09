# CxSummaryObject::AddDescriptorStrings(CxAnalysisItem *,DataSet &,bool,bool,bool)

- ea: `0x18305aa20`
- end: `0x18305ad6b`
- name: `?AddDescriptorStrings@CxSummaryObject@@QEAA_NPEAVCxAnalysisItem@@AEAVDataSet@@_N22@Z`
- size: `843`
- prototype: `bool __usercall@<al>(CxSummaryObject *__hidden this@<rcx>, struct CxAnalysisItem *@<rdx>, struct DataSet *@<r8>, bool@<r9b>, bool, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1815c72b0`

## callees

- `0x182dc4440`
- `0x182dcc6d0`
- `0x1830529a0`
- `0x183052ed0`
- `0x183053010`
- `0x183053170`
- `0x1830536a0`
- `0x183055940`
- `0x183055970`
- `0x183056430`
- `0x18305a500`
- `0x18305aa20`
- `0x18305afb0`
- `0x1830627f0`
- `0x1830fa520`
- `0x183108cc0`
- `0x183293fb0`
- `0x183295c50`
- `0x1832b0a10`
- `0x1832ce3b0`

## import_xrefs

- `VCRUNTIME140!strchr` at `0x18305ab30`
- `VCRUNTIME140!strchr` at `0x18305ab4d`
- `VCRUNTIME140!strchr` at `0x18305ab6b`
- `VCRUNTIME140!strchr` at `0x18305ab30`
- `VCRUNTIME140!strchr` at `0x18305ab4d`
- `VCRUNTIME140!strchr` at `0x18305ab6b`

## string_xrefs

- `0x18305aceb`: `The '*' operator cannot be used with the '-' operator in formulas to remove an interaction.`
- `0x18305ad05`: `The descriptor string '%s' is invalid in a formula; the '*' operator cannot be mixed with interaction ':'  or power '^' terms.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CxSummaryObject::AddDescriptorStrings(
        CxSummaryObject *this,
        struct CxAnalysisItem *a2,
        struct DataSet *a3,
        bool a4,
        bool a5,
        bool a6)
{
  bool v6; // di
  const struct Var *v10; // rax
  const struct Var *v11; // rax
  __int64 v12; // r14
  const struct CxString *v13; // rax
  const struct CxString *v14; // rax
  const char *CharPointer; // rax
  bool v16; // bl
  const char *v17; // rax
  bool v18; // si
  const char *v19; // rax
  bool v20; // si
  __int64 v21; // rdi
  __int64 v22; // rax
  const char *v23; // rax
  const char *v24; // rax
  bool v25; // zf
  const char *v26; // rax
  const char *v27; // rax
  unsigned __int8 v28; // bl
  bool v31; // [rsp+31h] [rbp-48h]
  _BYTE v32[8]; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int64 NumRows; // [rsp+40h] [rbp-39h]
  __int64 v34; // [rsp+48h] [rbp-31h]
  __int64 v35; // [rsp+50h] [rbp-29h] BYREF
  __int64 v36; // [rsp+58h] [rbp-21h] BYREF
  __int64 v37; // [rsp+60h] [rbp-19h] BYREF
  __int64 v38; // [rsp+68h] [rbp-11h] BYREF
  __int64 v39; // [rsp+70h] [rbp-9h] BYREF

  v34 = -2;
  v6 = a4;
  v37 = 0;
  v10 = (const struct Var *)DataSet::operator[](a3, 0);
  StringMatrix::StringMatrix((StringMatrix *)&v37, v10);
  v38 = 0;
  v11 = (const struct Var *)DataSet::operator[](a3, 1);
  StringMatrix::StringMatrix((StringMatrix *)&v38, v11);
  NumRows = Var::GetNumRows((Var *)&v37);
  v39 = 0;
  CxString::CxString((CxString *)&v39);
  v12 = 0;
  if ( !NumRows )
  {
LABEL_24:
    v28 = 1;
    goto LABEL_25;
  }
  while ( 1 )
  {
    v35 = 0;
    v13 = (const struct CxString *)StringMatrix::operator[](&v37, v12);
    CxString::CxString((CxString *)&v35, v13);
    if ( !CxString::IsEmpty((CxString *)&v35) )
      break;
LABEL_18:
    CxString::~CxString((CxString *)&v35);
LABEL_19:
    if ( ++v12 >= NumRows )
      goto LABEL_24;
  }
  v36 = 0;
  v14 = (const struct CxString *)StringMatrix::operator[](&v38, v12);
  CxString::CxString((CxString *)&v36, v14);
  CharPointer = CxString::GetCharPointer((CxString *)&v35);
  v16 = strchr(CharPointer, 42) != 0;
  v17 = CxString::GetCharPointer((CxString *)&v35);
  v18 = strchr(v17, 58) != 0;
  v19 = CxString::GetCharPointer((CxString *)&v35);
  v31 = strchr(v19, 94) != 0;
  if ( (unsigned __int8)operator==(&v35, "1") )
  {
    v20 = (unsigned __int8)operator==(&v36, "-") == 0;
    v21 = *((_QWORD *)a2 + 16);
    if ( v21 )
      (*(void (__fastcall **)(_QWORD, bool))(*(_QWORD *)v21 + 80LL))(*((_QWORD *)a2 + 16), v20);
    CxString::~CxString((CxString *)&v36);
    CxString::~CxString((CxString *)&v35);
    v6 = a4;
    goto LABEL_19;
  }
  v22 = CxString::Replace(&v35, v32, "rxMinus", "-");
  CxString::operator=(&v35, v22);
  CxString::~CxString((CxString *)v32);
  if ( (unsigned __int8)operator==(&v36, "-") )
  {
    if ( v16 )
    {
      CxReportError("The '*' operator cannot be used with the '-' operator in formulas to remove an interaction.");
      goto LABEL_23;
    }
    if ( !a5 )
    {
      v23 = CxString::GetCharPointer((CxString *)&v35);
      CxSummaryObject::RemoveInteraction(this, v23, a2, v6);
    }
    goto LABEL_17;
  }
  if ( !v16 )
  {
    v26 = CxString::GetCharPointer((CxString *)&v35);
    v25 = CxSummaryObject::AddInteraction(this, v26, a2, v6, a5, a6) == -1;
LABEL_16:
    if ( v25 )
      goto LABEL_23;
LABEL_17:
    CxString::~CxString((CxString *)&v36);
    goto LABEL_18;
  }
  if ( !v18 && !v31 )
  {
    v24 = CxString::GetCharPointer((CxString *)&v35);
    v25 = !CxSummaryObject::AddCombination(this, v24, a2, v6, a5);
    goto LABEL_16;
  }
  v27 = CxString::GetCharPointer((CxString *)&v36);
  CxReportError(
    "The descriptor string '%s' is invalid in a formula; the '*' operator cannot be mixed with interaction ':'  or power '^' terms.",
    v27);
LABEL_23:
  CxString::~CxString((CxString *)&v36);
  CxString::~CxString((CxString *)&v35);
  v28 = 0;
LABEL_25:
  CxString::~CxString((CxString *)&v39);
  StringMatrix::~StringMatrix((StringMatrix *)&v38);
  StringMatrix::~StringMatrix((StringMatrix *)&v37);
  return v28;
}

```

## disassembly

```asm
0x18305aa20  push    rbp
0x18305aa22  push    rbx
0x18305aa23  push    rsi
0x18305aa24  push    rdi
0x18305aa25  push    r12
0x18305aa27  push    r13
0x18305aa29  push    r14
0x18305aa2b  push    r15
0x18305aa2d  lea     rbp, [rsp-0Fh]
0x18305aa32  sub     rsp, 88h
0x18305aa39  mov     [rbp+47h+var_78], 0FFFFFFFFFFFFFFFEh
0x18305aa41  mov     rax, cs:__security_cookie
0x18305aa48  xor     rax, rsp
0x18305aa4b  mov     [rbp+47h+var_48], rax
0x18305aa4f  movzx   edi, r9b
0x18305aa53  mov     [rbp+47h+var_90], r9b
0x18305aa57  mov     rbx, r8
0x18305aa5a  mov     r15, rdx
0x18305aa5d  mov     r13, rcx
0x18305aa60  xor     eax, eax
0x18305aa62  mov     [rbp+47h+var_60], rax
0x18305aa66  xor     edx, edx
0x18305aa68  mov     rcx, r8
0x18305aa6b  call    ??ADataSet@@QEAAAEAVVar@@H@Z
0x18305aa70  mov     rdx, rax; struct Var *
0x18305aa73  lea     rcx, [rbp+47h+var_60]; this
0x18305aa77  call    ??0StringMatrix@@QEAA@AEBVVar@@@Z
0x18305aa7c  nop
0x18305aa7d  xor     eax, eax
0x18305aa7f  mov     [rbp+47h+var_58], rax
0x18305aa83  lea     edx, [rax+1]
0x18305aa86  mov     rcx, rbx
0x18305aa89  call    ??ADataSet@@QEAAAEAVVar@@H@Z
0x18305aa8e  mov     rdx, rax; struct Var *
0x18305aa91  lea     rcx, [rbp+47h+var_58]; this
0x18305aa95  call    ??0StringMatrix@@QEAA@AEBVVar@@@Z
0x18305aa9a  nop
0x18305aa9b  lea     rcx, [rbp+47h+var_60]; this
0x18305aa9f  call    ?GetNumRows@Var@@QEBA_KXZ
0x18305aaa4  mov     r12, rax
0x18305aaa7  mov     [rbp+47h+var_80], rax
0x18305aaab  xor     eax, eax
0x18305aaad  mov     [rbp+47h+var_50], rax
0x18305aab1  lea     rcx, [rbp+47h+var_50]; this
0x18305aab5  call    ??0CxString@@QEAA@XZ
0x18305aaba  nop
0x18305aabb  xor     eax, eax
0x18305aabd  mov     r14d, eax
0x18305aac0  test    r12, r12
0x18305aac3  jz      loc_18305AD29
0x18305aac9  movzx   r12d, [rbp+47h+arg_20]
0x18305aace  xchg    ax, ax
0x18305aad0  xor     eax, eax
0x18305aad2  mov     [rbp+47h+var_70], rax
0x18305aad6  mov     rdx, r14
0x18305aad9  lea     rcx, [rbp+47h+var_60]
0x18305aadd  call    ??AStringMatrix@@QEBAAEBVCxString@@_K@Z
0x18305aae2  mov     rdx, rax; struct CxString *
0x18305aae5  lea     rcx, [rbp+47h+var_70]; this
0x18305aae9  call    ??0CxString@@QEAA@AEBV0@@Z
0x18305aaee  nop
0x18305aaef  lea     rcx, [rbp+47h+var_70]; this
0x18305aaf3  call    ?IsEmpty@CxString@@QEBA_NXZ
0x18305aaf8  test    al, al
0x18305aafa  jnz     loc_18305ACD4
0x18305ab00  xor     eax, eax
0x18305ab02  mov     [rbp+47h+var_68], rax
0x18305ab06  mov     rdx, r14
0x18305ab09  lea     rcx, [rbp+47h+var_58]
0x18305ab0d  call    ??AStringMatrix@@QEBAAEBVCxString@@_K@Z
0x18305ab12  mov     rdx, rax; struct CxString *
0x18305ab15  lea     rcx, [rbp+47h+var_68]; this
0x18305ab19  call    ??0CxString@@QEAA@AEBV0@@Z
0x18305ab1e  nop
0x18305ab1f  lea     rcx, [rbp+47h+var_70]; this
0x18305ab23  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x18305ab28  mov     rcx, rax; Str
0x18305ab2b  mov     edx, 2Ah ; '*'; Val
0x18305ab30  call    cs:__imp_strchr
0x18305ab36  test    rax, rax
0x18305ab39  setnz   bl
0x18305ab3c  lea     rcx, [rbp+47h+var_70]; this
0x18305ab40  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x18305ab45  mov     rcx, rax; Str
0x18305ab48  mov     edx, 3Ah ; ':'; Val
0x18305ab4d  call    cs:__imp_strchr
0x18305ab53  test    rax, rax
0x18305ab56  setnz   sil
0x18305ab5a  lea     rcx, [rbp+47h+var_70]; this
0x18305ab5e  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x18305ab63  mov     rcx, rax; Str
0x18305ab66  mov     edx, 5Eh ; '^'; Val
0x18305ab6b  call    cs:__imp_strchr
0x18305ab71  test    rax, rax
0x18305ab74  setnz   [rbp+47h+var_8F]
0x18305ab78  lea     rdx, a1_0
0x18305ab7f  lea     rcx, [rbp+47h+var_70]
0x18305ab83  call    ??8@YA_NAEBVCxString@@PEBD@Z
0x18305ab88  test    al, al
0x18305ab8a  jz      short loc_18305ABED
0x18305ab8c  mov     bl, 1
0x18305ab8e  lea     rdx, asc_18338C068
0x18305ab95  lea     rcx, [rbp+47h+var_68]
0x18305ab99  call    ??8@YA_NAEBVCxString@@PEBD@Z
0x18305ab9e  movzx   esi, bl
0x18305aba1  test    al, al
0x18305aba3  mov     eax, 0
0x18305aba8  cmovnz  esi, eax
0x18305abab  mov     rdi, [r15+80h]
0x18305abb2  test    rdi, rdi
0x18305abb5  jz      short loc_18305ABD1
0x18305abb7  mov     rax, [rdi]
0x18305abba  mov     rbx, [rax+50h]
0x18305abbe  mov     rcx, rbx; this
0x18305abc1  call    cs:__guard_check_icall_fptr
0x18305abc7  movzx   edx, sil
0x18305abcb  mov     rcx, rdi
0x18305abce  call    rbx
0x18305abd0  nop
0x18305abd1  lea     rcx, [rbp+47h+var_68]; this
0x18305abd5  call    ??1CxString@@QEAA@XZ
0x18305abda  nop
0x18305abdb  lea     rcx, [rbp+47h+var_70]; this
0x18305abdf  call    ??1CxString@@QEAA@XZ
0x18305abe4  movzx   edi, [rbp+47h+var_90]
0x18305abe8  jmp     loc_18305ACDD
0x18305abed  lea     r9, asc_18338C068
0x18305abf4  lea     r8, aRxminus
0x18305abfb  lea     rdx, [rbp+47h+var_88]
0x18305abff  lea     rcx, [rbp+47h+var_70]
0x18305ac03  call    ?Replace@CxString@@QEBA?AV1@PEBD0@Z
0x18305ac08  nop
0x18305ac09  mov     rdx, rax
0x18305ac0c  lea     rcx, [rbp+47h+var_70]
0x18305ac10  call    ??4CxString@@QEAAAEAV0@AEBV0@@Z
0x18305ac15  nop
0x18305ac16  lea     rcx, [rbp+47h+var_88]; this
0x18305ac1a  call    ??1CxString@@QEAA@XZ
0x18305ac1f  lea     rdx, asc_18338C068
0x18305ac26  lea     rcx, [rbp+47h+var_68]
0x18305ac2a  call    ??8@YA_NAEBVCxString@@PEBD@Z
0x18305ac2f  test    al, al
0x18305ac31  jz      short loc_18305AC61
0x18305ac33  test    bl, bl
0x18305ac35  jnz     loc_18305ACEB
0x18305ac3b  test    r12b, r12b
0x18305ac3e  jnz     loc_18305ACCA
0x18305ac44  lea     rcx, [rbp+47h+var_70]; this
0x18305ac48  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x18305ac4d  mov     rdx, rax; char *
0x18305ac50  movzx   r9d, dil; bool
0x18305ac54  mov     r8, r15; struct CxAnalysisItem *
0x18305ac57  mov     rcx, r13; this
0x18305ac5a  call    ?RemoveInteraction@CxSummaryObject@@QEAA_KPEBDPEAVCxAnalysisItem@@_N@Z
0x18305ac5f  jmp     short loc_18305ACCA
0x18305ac61  test    bl, bl
0x18305ac63  jz      short loc_18305AC9C
0x18305ac65  test    sil, sil
0x18305ac68  jnz     loc_18305ACF9
0x18305ac6e  cmp     [rbp+47h+var_8F], sil
0x18305ac72  jnz     loc_18305ACF9
0x18305ac78  lea     rcx, [rbp+47h+var_70]; this
0x18305ac7c  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x18305ac81  mov     rdx, rax; char *
0x18305ac84  mov     [rsp+0C0h+var_A0], r12b; bool
0x18305ac89  movzx   r9d, dil; bool
0x18305ac8d  mov     r8, r15; struct CxAnalysisItem *
0x18305ac90  mov     rcx, r13; this
0x18305ac93  call    ?AddCombination@CxSummaryObject@@QEAA_NPEBDPEAVCxAnalysisItem@@_N2@Z
0x18305ac98  test    al, al
0x18305ac9a  jmp     short loc_18305ACC8
0x18305ac9c  lea     rcx, [rbp+47h+var_70]; this
0x18305aca0  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x18305aca5  mov     rdx, rax; char *
0x18305aca8  movzx   eax, [rbp+47h+arg_28]
0x18305acac  mov     [rsp+0C0h+var_98], al; bool
0x18305acb0  mov     [rsp+0C0h+var_A0], r12b; bool
0x18305acb5  movzx   r9d, dil; bool
0x18305acb9  mov     r8, r15; struct CxAnalysisItem *
0x18305acbc  mov     rcx, r13; this
0x18305acbf  call    ?AddInteraction@CxSummaryObject@@QEAA_KPEBDPEAVCxAnalysisItem@@_N22@Z
0x18305acc4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18305acc8  jz      short loc_18305AD12
0x18305acca  lea     rcx, [rbp+47h+var_68]; this
0x18305acce  call    ??1CxString@@QEAA@XZ
0x18305acd3  nop
0x18305acd4  lea     rcx, [rbp+47h+var_70]; this
0x18305acd8  call    ??1CxString@@QEAA@XZ
0x18305acdd  inc     r14
0x18305ace0  cmp     r14, [rbp+47h+var_80]
0x18305ace4  jnb     short loc_18305AD29
0x18305ace6  jmp     loc_18305AAD0
0x18305aceb  lea     rcx, aTheOperatorCan
0x18305acf2  call    ?CxReportError@@YAXPEBDZZ
0x18305acf7  jmp     short loc_18305AD12
0x18305acf9  lea     rcx, [rbp+47h+var_68]; this
0x18305acfd  call    ?GetCharPointer@CxString@@QEBAPEBDXZ
0x18305ad02  mov     rdx, rax
0x18305ad05  lea     rcx, aTheDescriptorS
0x18305ad0c  call    ?CxReportError@@YAXPEBDZZ
0x18305ad11  nop
0x18305ad12  lea     rcx, [rbp+47h+var_68]; this
0x18305ad16  call    ??1CxString@@QEAA@XZ
0x18305ad1b  nop
0x18305ad1c  lea     rcx, [rbp+47h+var_70]; this
0x18305ad20  call    ??1CxString@@QEAA@XZ
0x18305ad25  xor     bl, bl
0x18305ad27  jmp     short loc_18305AD2B
0x18305ad29  mov     bl, 1
0x18305ad2b  lea     rcx, [rbp+47h+var_50]; this
0x18305ad2f  call    ??1CxString@@QEAA@XZ
0x18305ad34  nop
0x18305ad35  lea     rcx, [rbp+47h+var_58]; this
0x18305ad39  call    ??1StringMatrix@@QEAA@XZ
0x18305ad3e  nop
0x18305ad3f  lea     rcx, [rbp+47h+var_60]; this
0x18305ad43  call    ??1StringMatrix@@QEAA@XZ
0x18305ad48  movzx   eax, bl
0x18305ad4b  mov     rcx, [rbp+47h+var_48]
0x18305ad4f  xor     rcx, rsp; StackCookie
0x18305ad52  call    __security_check_cookie
0x18305ad57  add     rsp, 88h
0x18305ad5e  pop     r15
0x18305ad60  pop     r14
0x18305ad62  pop     r13
0x18305ad64  pop     r12
0x18305ad66  pop     rdi
0x18305ad67  pop     rsi
0x18305ad68  pop     rbx
0x18305ad69  pop     rbp
0x18305ad6a  retn
```
