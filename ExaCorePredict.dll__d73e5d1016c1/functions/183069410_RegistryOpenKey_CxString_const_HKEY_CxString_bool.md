# RegistryOpenKey(CxString const &,HKEY__ * &,CxString &,bool)

- ea: `0x183069410`
- end: `0x1830695ec`
- name: `?RegistryOpenKey@@YA_NAEBVCxString@@AEAPEAUHKEY__@@AEAV1@_N@Z`
- size: `476`
- prototype: `bool __fastcall(const struct CxString *this, PHKEY phkResult, struct CxString *, bool)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1830690f0`
- `0x1830691e0`

## callees

- `0x1815cf5d0`
- `0x182dcc6d0`
- `0x183052ed0`
- `0x183053010`
- `0x183053170`
- `0x183053410`
- `0x183053560`
- `0x183055940`
- `0x183055f80`
- `0x1830689b0`
- `0x183069410`
- `0x183108cc0`
- `0x183293fb0`
- `0x183295c50`
- `0x1832aa590`
- `0x1832b0840`
- `0x1832ce3b0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x183069587`
- `ADVAPI32!RegOpenKeyExA` at `0x183069587`

## string_xrefs

- `0x1830694aa`: `An invalid registry key path was specified: %s.`
- `0x1830695a6`: `The value for the registry path '%s' could not be obtained.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BOOL8 __fastcall RegistryOpenKey(const struct CxString *this, PHKEY phkResult, struct CxString *a3, char a4)
{
  const struct Var *v8; // rax
  unsigned __int64 Length; // rdi
  const char *CharPointer; // rax
  unsigned __int64 v11; // rax
  const struct CxString *v12; // rax
  bool v13; // bl
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int64 i; // rbx
  unsigned __int64 v17; // rax
  __int64 v18; // rax
  const CHAR *v19; // rax
  LSTATUS v20; // eax
  const char *v21; // rax
  _BYTE v23[8]; // [rsp+40h] [rbp-58h] BYREF
  HKEY hKey[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v25; // [rsp+58h] [rbp-40h] BYREF
  __int64 v26; // [rsp+60h] [rbp-38h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v25 = 0;
  v8 = (const struct Var *)CxString::Parse(this, v23, "/\\", 0, 1, 1, 1);
  StringMatrix::StringMatrix((StringMatrix *)&v25, v8);
  Var::~Var((Var *)v23);
  Length = Var::GetLength((Var *)&v25);
  if ( Length < 3 )
  {
    if ( a4 )
    {
      CharPointer = CxString::GetCharPointer(this);
      CxReportError("An invalid registry key path was specified: %s.", CharPointer);
    }
    goto LABEL_5;
  }
  v11 = ConvertIndexToBase0(1u);
  v12 = (const struct CxString *)StringMatrix::operator[](&v25, v11);
  if ( !ConvertKeyNameToKeyValue(v12, hKey) )
  {
LABEL_5:
    v13 = 0;
    goto LABEL_14;
  }
  v14 = ConvertIndexToBase0(Length);
  v15 = StringMatrix::operator[](&v25, v14);
  CxString::operator=(a3, v15);
  v26 = 0;
  CxString::CxString((CxString *)&v26);
  for ( i = 2; i < Length; ++i )
  {
    v17 = ConvertIndexToBase0(i);
    v18 = StringMatrix::operator[](&v25, v17);
    operator<<(&v26, v18);
    if ( i < Length - 1 )
      operator<<(&v26, "\\");
  }
  v19 = CxString::GetCharPointer((CxString *)&v26);
  v20 = RegOpenKeyExA(hKey[0], v19, 0, 0x20019u, phkResult);
  v13 = v20 == 0;
  if ( v20 && a4 )
  {
    v21 = CxString::GetCharPointer(this);
    CxReportError("The value for the registry path '%s' could not be obtained.", v21);
  }
  CxString::~CxString((CxString *)&v26);
LABEL_14:
  StringMatrix::~StringMatrix((StringMatrix *)&v25);
  return v13;
}

```

## disassembly

```asm
0x183069410  mov     r11, rsp
0x183069413  push    rbp
0x183069414  push    rsi
0x183069415  push    rdi
0x183069416  push    r14
0x183069418  push    r15
0x18306941a  sub     rsp, 70h
0x18306941e  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x183069426  mov     [r11+20h], rbx
0x18306942a  mov     rax, cs:__security_cookie
0x183069431  xor     rax, rsp
0x183069434  mov     [rsp+98h+var_30], rax
0x183069439  movzx   ebp, r9b
0x18306943d  mov     rbx, r8
0x183069440  mov     r15, rdx
0x183069443  mov     r14, rcx
0x183069446  xor     eax, eax
0x183069448  mov     [r11-40h], rax
0x18306944c  mov     [rsp+98h+var_68], 1
0x183069451  mov     [rsp+98h+var_70], 1
0x183069456  mov     byte ptr [rsp+98h+phkResult], 1
0x18306945b  xor     r9d, r9d
0x18306945e  lea     r8, asc_1833CB74C; "/\\"
0x183069465  lea     rdx, [r11-58h]
0x183069469  call    ?Parse@CxString@@QEBA?AVVar@@PEBD_N111@Z; CxString::Parse(char const *,bool,bool,bool,bool)
0x18306946e  nop
0x18306946f  mov     rdx, rax; struct Var *
0x183069472  lea     rcx, [rsp+98h+var_40]; this
0x183069477  call    ??0StringMatrix@@QEAA@AEBVVar@@@Z; StringMatrix::StringMatrix(Var const &)
0x18306947c  nop
0x18306947d  lea     rcx, [rsp+98h+var_58]; this
0x183069482  call    ??1Var@@QEAA@XZ; Var::~Var(void)
0x183069487  lea     rcx, [rsp+98h+var_40]; this
0x18306948c  call    ?GetLength@Var@@QEBA_KXZ; Var::GetLength(void)
0x183069491  mov     rdi, rax
0x183069494  cmp     rax, 3
0x183069498  jnb     short loc_1830694B8
0x18306949a  test    bpl, bpl
0x18306949d  jz      short loc_1830694E0
0x18306949f  mov     rcx, r14; this
0x1830694a2  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x1830694a7  mov     rdx, rax
0x1830694aa  lea     rcx, aAnInvalidRegis; "An invalid registry key path was specif"...
0x1830694b1  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x1830694b6  jmp     short loc_1830694E0
0x1830694b8  mov     ecx, 1; unsigned __int64
0x1830694bd  call    ?ConvertIndexToBase0@@YA_K_K@Z; ConvertIndexToBase0(unsigned __int64)
0x1830694c2  mov     rdx, rax
0x1830694c5  lea     rcx, [rsp+98h+var_40]
0x1830694ca  call    ??AStringMatrix@@QEBAAEBVCxString@@_K@Z; StringMatrix::operator[](unsigned __int64)
0x1830694cf  lea     rdx, [rsp+98h+hKey]; HKEY *
0x1830694d4  mov     rcx, rax; struct CxString *
0x1830694d7  call    ?ConvertKeyNameToKeyValue@@YA_NAEBVCxString@@AEAPEAUHKEY__@@@Z; ConvertKeyNameToKeyValue(CxString const &,HKEY__ * &)
0x1830694dc  test    al, al
0x1830694de  jnz     short loc_1830694E7
0x1830694e0  xor     bl, bl
0x1830694e2  jmp     loc_1830695BE
0x1830694e7  mov     rcx, rdi; unsigned __int64
0x1830694ea  call    ?ConvertIndexToBase0@@YA_K_K@Z; ConvertIndexToBase0(unsigned __int64)
0x1830694ef  mov     rdx, rax
0x1830694f2  lea     rcx, [rsp+98h+var_40]
0x1830694f7  call    ??AStringMatrix@@QEBAAEBVCxString@@_K@Z; StringMatrix::operator[](unsigned __int64)
0x1830694fc  mov     rdx, rax
0x1830694ff  mov     rcx, rbx
0x183069502  call    ??4CxString@@QEAAAEAV0@AEBV0@@Z; CxString::operator=(CxString const &)
0x183069507  xor     eax, eax
0x183069509  mov     [rsp+98h+var_38], rax
0x18306950e  lea     rcx, [rsp+98h+var_38]; this
0x183069513  call    ??0CxString@@QEAA@XZ; CxString::CxString(void)
0x183069518  nop
0x183069519  mov     ebx, 2
0x18306951e  cmp     rbx, rdi
0x183069521  jnb     short loc_183069567
0x183069523  lea     rsi, [rdi-1]
0x183069527  mov     rcx, rbx; unsigned __int64
0x18306952a  call    ?ConvertIndexToBase0@@YA_K_K@Z; ConvertIndexToBase0(unsigned __int64)
0x18306952f  mov     rdx, rax
0x183069532  lea     rcx, [rsp+98h+var_40]
0x183069537  call    ??AStringMatrix@@QEBAAEBVCxString@@_K@Z; StringMatrix::operator[](unsigned __int64)
0x18306953c  mov     rdx, rax
0x18306953f  lea     rcx, [rsp+98h+var_38]
0x183069544  call    ??6@YAAEAVCxString@@AEAV0@AEBV0@@Z; operator<<(CxString &,CxString const &)
0x183069549  cmp     rbx, rsi
0x18306954c  jnb     short loc_18306955F
0x18306954e  lea     rdx, asc_1833A3FF4; "\\"
0x183069555  lea     rcx, [rsp+98h+var_38]
0x18306955a  call    ??6@YAAEAVCxString@@AEAV0@PEBD@Z; operator<<(CxString &,char const *)
0x18306955f  inc     rbx
0x183069562  cmp     rbx, rdi
0x183069565  jb      short loc_183069527
0x183069567  lea     rcx, [rsp+98h+var_38]; this
0x18306956c  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x183069571  mov     rdx, rax; lpSubKey
0x183069574  mov     [rsp+98h+phkResult], r15; phkResult
0x183069579  mov     r9d, 20019h; samDesired
0x18306957f  xor     r8d, r8d; ulOptions
0x183069582  mov     rcx, [rsp+98h+hKey]; hKey
0x183069587  call    cs:__imp_RegOpenKeyExA
0x18306958d  test    eax, eax
0x18306958f  setz    bl
0x183069592  test    bl, bl
0x183069594  jnz     short loc_1830695B3
0x183069596  test    bpl, bpl
0x183069599  jz      short loc_1830695B3
0x18306959b  mov     rcx, r14; this
0x18306959e  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x1830695a3  mov     rdx, rax
0x1830695a6  lea     rcx, aTheValueForThe; "The value for the registry path '%s' co"...
0x1830695ad  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x1830695b2  nop
0x1830695b3  lea     rcx, [rsp+98h+var_38]; this
0x1830695b8  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x1830695bd  nop
0x1830695be  lea     rcx, [rsp+98h+var_40]; this
0x1830695c3  call    ??1StringMatrix@@QEAA@XZ; StringMatrix::~StringMatrix(void)
0x1830695c8  movzx   eax, bl
0x1830695cb  mov     rcx, [rsp+98h+var_30]
0x1830695d0  xor     rcx, rsp; StackCookie
0x1830695d3  call    __security_check_cookie
0x1830695d8  mov     rbx, [rsp+98h+arg_18]
0x1830695e0  add     rsp, 70h
0x1830695e4  pop     r15
0x1830695e6  pop     r14
0x1830695e8  pop     rdi
0x1830695e9  pop     rsi
0x1830695ea  pop     rbp
0x1830695eb  retn
```
