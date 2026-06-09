# CxString::WriteToFile(CxString const &,bool)

- ea: `0x1830569f0`
- end: `0x183056dd5`
- name: `?WriteToFile@CxString@@QEBA_NAEBV1@_N@Z`
- size: `997`
- prototype: `bool __fastcall(CxString *__hidden this, const struct CxString *, bool)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x182d3efe0`
- `0x182d46e30`
- `0x182d47420`
- `0x182dcc6d0`
- `0x18303bef0`
- `0x18303bf50`
- `0x18304feb0`
- `0x1830569f0`
- `0x183056fc0`
- `0x1830e8d10`
- `0x1832c3a50`
- `0x1832ce3b0`
- `0x1832dbeb0`

## import_xrefs

- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183056c96`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183056d2c`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183056c96`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183056d2c`
- `MSVCP140!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x183056ab3`
- `MSVCP140!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x183056ab3`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x183056da0`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x183056da0`
- `MSVCP140!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x183056a5c`
- `MSVCP140!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x183056a5c`
- `MSVCP140!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x183056a79`
- `MSVCP140!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x183056a79`
- `MSVCP140!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x183056d96`
- `MSVCP140!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x183056d96`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x183056cb8`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x183056cb8`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x183056ad1`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x183056ad1`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183056ca3`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183056ca3`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x183056d02`
- `MSVCP140!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x183056d02`

## string_xrefs

- `0x183056cd9`: `Cannot open file '%s'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CxString::WriteToFile(CxString *this, CxRefCount **a2, char a3)
{
  __int64 v6; // rsi
  CxRefCount *v7; // rax
  CxRefCount *v8; // rbx
  CxRefCount *v9; // rdi
  const char *DefaultDataDir; // rax
  CxRefCount **v11; // rax
  CxRefCount *v12; // rdi
  CxRefCount *v13; // rcx
  CxRefCount *v14; // rdi
  _QWORD *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  const char *v18; // rdx
  unsigned __int8 v19; // di
  _QWORD *v20; // rdx
  CxRefCount *v22; // [rsp+78h] [rbp-90h] BYREF
  CxRefCount *v23[3]; // [rsp+80h] [rbp-88h] BYREF
  int *v24; // [rsp+98h] [rbp-70h] BYREF
  void **v25; // [rsp+A0h] [rbp-68h] BYREF
  char v26[96]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v27; // [rsp+108h] [rbp+0h]
  char v28; // [rsp+111h] [rbp+9h]
  __int64 v29; // [rsp+114h] [rbp+Ch]
  char v30; // [rsp+11Ch] [rbp+14h]
  __int64 v31; // [rsp+120h] [rbp+18h]
  _BYTE v32[104]; // [rsp+140h] [rbp+38h] BYREF

  v23[1] = (CxRefCount *)-2LL;
  memset_0(&v24, 0, 0x108u);
  v24 = (int *)&std::ofstream::`vbtable';
  std::ios::ios(v32);
  LODWORD(v22) = 1;
  std::ostream::ostream(&v24, &v25, 0, 0);
  *(int **)((char *)&v24 + v24[1]) = (int *)&std::ofstream::`vftable';
  *(_DWORD *)((char *)&v23[2] + v24[1] + 4) = v24[1] - 168;
  v23[0] = (CxRefCount *)&v25;
  std::streambuf::streambuf(&v25);
  v25 = &std::filebuf::`vftable';
  v30 = 0;
  v28 = 0;
  std::streambuf::_Init(&v25);
  v31 = 0;
  v29 = `std::filebuf::_Init'::`2'::_Stinit;
  v27 = 0;
  if ( !*(_QWORD *)this || (v6 = *(_QWORD *)(*(_QWORD *)this + 32LL)) == 0 )
  {
    v19 = 1;
    goto LABEL_53;
  }
  if ( !*a2 || !*((_QWORD *)*a2 + 4) )
  {
    CxReportError("No file name was specified.");
    v19 = 0;
    goto LABEL_53;
  }
  v7 = (CxRefCount *)operator new(0x30u);
  v23[0] = v7;
  if ( v7 )
    v7 = CxStringBase::CxStringBase(v7);
  v8 = 0;
  v22 = 0;
  if ( v7 )
  {
    v8 = v7;
    v22 = v7;
    CxRefCount::AddRef(v7);
  }
  if ( a3 )
  {
    v9 = *a2;
    if ( v9 )
    {
      v9 = (CxRefCount *)((char *)v9 + 16);
      if ( *((_QWORD *)v9 + 3) >= 0x10u )
        v9 = *(CxRefCount **)v9;
    }
    DefaultDataDir = GetDefaultDataDir();
    v11 = (CxRefCount **)CheckAndFixDataFileName(v23, v9, ".txt", DefaultDataDir, 1, 0, 0, 1, 0, 0, 0, 1, 0);
    if ( &v22 != v11 )
    {
      v12 = *v11;
      if ( v8 != *v11 )
      {
        if ( v8 )
          CxRefCount::Release(v8);
        v8 = v12;
        v22 = v12;
        if ( v12 )
          CxRefCount::AddRef(v12);
      }
    }
    v13 = v23[0];
    if ( v23[0] )
    {
      CxRefCount::Release(v23[0]);
      v13 = 0;
      v23[0] = 0;
    }
    if ( v13 )
      CxRefCount::Release(v13);
  }
  else if ( &v22 != a2 )
  {
    v14 = *a2;
    if ( v8 != v14 )
    {
      if ( v8 )
        CxRefCount::Release(v8);
      v8 = v14;
      v22 = v14;
      if ( !v14 )
        goto LABEL_33;
      CxRefCount::AddRef(v14);
    }
  }
  if ( v8 )
  {
    v15 = (_QWORD *)((char *)v8 + 16);
    if ( *((_QWORD *)v8 + 5) >= 0x10u )
      v15 = (_QWORD *)*v15;
    goto LABEL_34;
  }
LABEL_33:
  v15 = 0;
LABEL_34:
  v16 = std::filebuf::open(&v25, v15, 2);
  v17 = v24[1];
  if ( v16 )
    std::ios::clear((char *)&v24 + v17, 0, 0);
  else
    std::ios::setstate((char *)&v24 + v17, 2);
  if ( (unsigned __int8)std::ios_base::operator!((char *)&v24 + v24[1]) )
  {
    if ( v8 )
    {
      v18 = (char *)v8 + 16;
      if ( *((_QWORD *)v8 + 5) >= 0x10u )
        v18 = *(const char **)v18;
    }
    else
    {
      v18 = 0;
    }
    CxReportError("Cannot open file '%s'.", v18);
    v19 = 0;
  }
  else
  {
    v20 = (_QWORD *)(*(_QWORD *)this + 16LL);
    if ( *(_QWORD *)(*(_QWORD *)this + 40LL) >= 0x10u )
      v20 = (_QWORD *)*v20;
    std::ostream::write(&v24, v20, v6);
    if ( !std::filebuf::close(&v25) )
      std::ios::setstate((char *)&v24 + v24[1], 2);
    v19 = 1;
  }
  if ( v8 )
    CxRefCount::Release(v8);
LABEL_53:
  *(int **)((char *)&v24 + v24[1]) = (int *)&std::ofstream::`vftable';
  *(_DWORD *)((char *)&v23[2] + v24[1] + 4) = v24[1] - 168;
  std::filebuf::~filebuf<char,std::char_traits<char>>(&v25);
  std::ostream::~ostream<char,std::char_traits<char>>(v26);
  std::ios::~ios<char,std::char_traits<char>>(v32);
  return v19;
}

```

## disassembly

```asm
0x1830569f0  mov     rax, rsp
0x1830569f3  push    rbp
0x1830569f4  push    rdi
0x1830569f5  push    r13
0x1830569f7  push    r14
0x1830569f9  push    r15
0x1830569fb  lea     rbp, [rax-0D8h]
0x183056a02  sub     rsp, 1B0h
0x183056a09  mov     [rbp+0D0h+var_150], 0FFFFFFFFFFFFFFFEh
0x183056a11  mov     [rax+18h], rbx
0x183056a15  mov     [rax+20h], rsi
0x183056a19  mov     rax, cs:__security_cookie
0x183056a20  xor     rax, rsp
0x183056a23  mov     [rbp+0D0h+var_30], rax
0x183056a2a  movzx   r14d, r8b
0x183056a2e  mov     rdi, rdx
0x183056a31  mov     r15, rcx
0x183056a34  mov     dword ptr [rsp+1D0h+var_160], 0
0x183056a3c  xor     edx, edx; Val
0x183056a3e  mov     r8d, 108h; Size
0x183056a44  lea     rcx, [rbp+0D0h+var_140]; void *
0x183056a48  call    memset_0
0x183056a4d  lea     rax, ??_8?$basic_ofstream@DU?$char_traits@D@std@@@std@@7B@; const std::ofstream::`vbtable'
0x183056a54  mov     [rbp+0D0h+var_140], rax
0x183056a58  lea     rcx, [rbp+0D0h+var_98]
0x183056a5c  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x183056a62  nop
0x183056a63  mov     dword ptr [rsp+1D0h+var_160], 1
0x183056a6b  xor     r9d, r9d
0x183056a6e  xor     r8d, r8d
0x183056a71  lea     rdx, [rbp+0D0h+var_138]
0x183056a75  lea     rcx, [rbp+0D0h+var_140]
0x183056a79  call    cs:__imp_??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::ostream::ostream(std::streambuf *,bool)
0x183056a7f  nop
0x183056a80  mov     rax, [rbp+0D0h+var_140]
0x183056a84  movsxd  rcx, dword ptr [rax+4]
0x183056a88  lea     r13, ??_7?$basic_ofstream@DU?$char_traits@D@std@@@std@@6B@; const std::ofstream::`vftable'
0x183056a8f  mov     [rbp+rcx+0D0h+var_140], r13
0x183056a94  mov     rax, [rbp+0D0h+var_140]
0x183056a98  movsxd  rcx, dword ptr [rax+4]
0x183056a9c  lea     edx, [rcx-0A8h]
0x183056aa2  mov     [rbp+rcx+0D0h+var_144], edx
0x183056aa6  lea     rax, [rbp+0D0h+var_138]
0x183056aaa  mov     [rsp+1D0h+var_158], rax
0x183056aaf  lea     rcx, [rbp+0D0h+var_138]
0x183056ab3  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x183056ab9  nop
0x183056aba  lea     rax, ??_7?$basic_filebuf@DU?$char_traits@D@std@@@std@@6B@; const std::filebuf::`vftable'
0x183056ac1  mov     [rbp+0D0h+var_138], rax
0x183056ac5  mov     [rbp+0D0h+var_BC], 0
0x183056ac9  mov     [rbp+0D0h+var_C7], 0
0x183056acd  lea     rcx, [rbp+0D0h+var_138]
0x183056ad1  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x183056ad7  mov     [rbp+0D0h+var_B8], 0
0x183056adf  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)'::`2'::_Stinit
0x183056ae6  mov     [rbp+0D0h+var_C4], rax
0x183056aea  mov     [rbp+0D0h+var_D0], 0
0x183056af2  mov     rsi, [r15]
0x183056af5  test    rsi, rsi
0x183056af8  jz      loc_183056D65
0x183056afe  mov     rsi, [rsi+20h]
0x183056b02  test    rsi, rsi
0x183056b05  jz      loc_183056D65
0x183056b0b  mov     rax, [rdi]
0x183056b0e  test    rax, rax
0x183056b11  jz      loc_183056D54
0x183056b17  cmp     qword ptr [rax+20h], 0
0x183056b1c  jz      loc_183056D54
0x183056b22  mov     ecx, 30h ; '0'; unsigned __int64
0x183056b27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x183056b2c  mov     [rsp+1D0h+var_158], rax
0x183056b31  test    rax, rax
0x183056b34  jz      short loc_183056B3F
0x183056b36  mov     rcx, rax; this
0x183056b39  call    ??0CxStringBase@@QEAA@XZ; CxStringBase::CxStringBase(void)
0x183056b3e  nop
0x183056b3f  xor     ebx, ebx
0x183056b41  mov     [rsp+1D0h+var_160], rbx
0x183056b46  test    rax, rax
0x183056b49  jz      short loc_183056B5C
0x183056b4b  mov     rbx, rax
0x183056b4e  mov     [rsp+1D0h+var_160], rax
0x183056b53  mov     rcx, rax; this
0x183056b56  call    ?AddRef@CxRefCount@@QEAAJXZ; CxRefCount::AddRef(void)
0x183056b5b  nop
0x183056b5c  test    r14b, r14b
0x183056b5f  jz      loc_183056C1D
0x183056b65  mov     rdi, [rdi]
0x183056b68  test    rdi, rdi
0x183056b6b  jz      short loc_183056B7B
0x183056b6d  add     rdi, 10h
0x183056b71  cmp     qword ptr [rdi+18h], 10h
0x183056b76  jb      short loc_183056B7B
0x183056b78  mov     rdi, [rdi]
0x183056b7b  call    ?GetDefaultDataDir@@YAPEBDXZ; GetDefaultDataDir(void)
0x183056b80  mov     r9, rax
0x183056b83  mov     [rsp+1D0h+var_170], 0
0x183056b88  mov     [rsp+1D0h+var_178], 1
0x183056b8d  mov     [rsp+1D0h+var_180], 0
0x183056b92  mov     [rsp+1D0h+var_188], 0
0x183056b97  mov     [rsp+1D0h+var_190], 0
0x183056b9c  mov     [rsp+1D0h+var_198], 1
0x183056ba1  mov     [rsp+1D0h+var_1A0], 0
0x183056ba6  mov     [rsp+1D0h+var_1A8], 0
0x183056bab  mov     [rsp+1D0h+var_1B0], 1
0x183056bb0  lea     r8, aTxt; ".txt"
0x183056bb7  mov     rdx, rdi
0x183056bba  lea     rcx, [rsp+1D0h+var_158]
0x183056bbf  call    ?CheckAndFixDataFileName@@YA?AVCxString@@PEBD_N11111@Z; CheckAndFixDataFileName(char const *,bool,bool,bool,bool,bool,bool)
0x183056bc4  nop
0x183056bc5  lea     rcx, [rsp+1D0h+var_160]
0x183056bca  cmp     rcx, rax
0x183056bcd  jz      short loc_183056BFA
0x183056bcf  mov     rdi, [rax]
0x183056bd2  cmp     rbx, rdi
0x183056bd5  jz      short loc_183056BFA
0x183056bd7  test    rbx, rbx
0x183056bda  jz      short loc_183056BE4
0x183056bdc  mov     rcx, rbx; this
0x183056bdf  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x183056be4  mov     rbx, rdi
0x183056be7  mov     [rsp+1D0h+var_160], rbx
0x183056bec  test    rdi, rdi
0x183056bef  jz      short loc_183056BFA
0x183056bf1  mov     rcx, rdi; this
0x183056bf4  call    ?AddRef@CxRefCount@@QEAAJXZ; CxRefCount::AddRef(void)
0x183056bf9  nop
0x183056bfa  mov     rcx, [rsp+1D0h+var_158]; this
0x183056bff  test    rcx, rcx
0x183056c02  jz      short loc_183056C10
0x183056c04  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x183056c09  xor     ecx, ecx; this
0x183056c0b  mov     [rsp+1D0h+var_158], rcx
0x183056c10  test    rcx, rcx
0x183056c13  jz      short loc_183056C1B
0x183056c15  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x183056c1a  nop
0x183056c1b  jmp     short loc_183056C51
0x183056c1d  lea     rax, [rsp+1D0h+var_160]
0x183056c22  cmp     rax, rdi
0x183056c25  jz      short loc_183056C51
0x183056c27  mov     rdi, [rdi]
0x183056c2a  cmp     rbx, rdi
0x183056c2d  jz      short loc_183056C51
0x183056c2f  test    rbx, rbx
0x183056c32  jz      short loc_183056C3C
0x183056c34  mov     rcx, rbx; this
0x183056c37  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x183056c3c  mov     rbx, rdi
0x183056c3f  mov     [rsp+1D0h+var_160], rbx
0x183056c44  test    rdi, rdi
0x183056c47  jz      short loc_183056C66
0x183056c49  mov     rcx, rdi; this
0x183056c4c  call    ?AddRef@CxRefCount@@QEAAJXZ; CxRefCount::AddRef(void)
0x183056c51  test    rbx, rbx
0x183056c54  jz      short loc_183056C66
0x183056c56  lea     rdx, [rbx+10h]
0x183056c5a  cmp     qword ptr [rdx+18h], 10h
0x183056c5f  jb      short loc_183056C68
0x183056c61  mov     rdx, [rdx]
0x183056c64  jmp     short loc_183056C68
0x183056c66  xor     edx, edx
0x183056c68  mov     r9d, 40h ; '@'
0x183056c6e  lea     r8d, [r9-3Eh]
0x183056c72  lea     rcx, [rbp+0D0h+var_138]
0x183056c76  call    ?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBDHH@Z; std::filebuf::open(char const *,int,int)
0x183056c7b  xor     r8d, r8d
0x183056c7e  test    rax, rax
0x183056c81  mov     rax, [rbp+0D0h+var_140]
0x183056c85  movsxd  rcx, dword ptr [rax+4]
0x183056c89  lea     rax, [rbp+0D0h+var_140]
0x183056c8d  jnz     short loc_183056C9E
0x183056c8f  add     rcx, rax
0x183056c92  lea     edx, [r8+2]
0x183056c96  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x183056c9c  jmp     short loc_183056CA9
0x183056c9e  add     rcx, rax
0x183056ca1  xor     edx, edx
0x183056ca3  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x183056ca9  mov     rax, [rbp+0D0h+var_140]
0x183056cad  movsxd  rcx, dword ptr [rax+4]
0x183056cb1  lea     rax, [rbp+0D0h+var_140]
0x183056cb5  add     rcx, rax
0x183056cb8  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x183056cbe  test    al, al
0x183056cc0  jz      short loc_183056CEA
0x183056cc2  test    rbx, rbx
0x183056cc5  jz      short loc_183056CD7
0x183056cc7  lea     rdx, [rbx+10h]
0x183056ccb  cmp     qword ptr [rdx+18h], 10h
0x183056cd0  jb      short loc_183056CD9
0x183056cd2  mov     rdx, [rdx]
0x183056cd5  jmp     short loc_183056CD9
0x183056cd7  xor     edx, edx
0x183056cd9  lea     rcx, aCannotOpenFile; "Cannot open file '%s'."
0x183056ce0  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x183056ce5  xor     dil, dil
0x183056ce8  jmp     short loc_183056D35
0x183056cea  mov     rdx, [r15]
0x183056ced  add     rdx, 10h
0x183056cf1  cmp     qword ptr [rdx+18h], 10h
0x183056cf6  jb      short loc_183056CFB
0x183056cf8  mov     rdx, [rdx]
0x183056cfb  mov     r8, rsi
0x183056cfe  lea     rcx, [rbp+0D0h+var_140]
0x183056d02  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x183056d08  lea     rcx, [rbp+0D0h+var_138]
0x183056d0c  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x183056d11  test    rax, rax
0x183056d14  jnz     short loc_183056D32
0x183056d16  mov     rax, [rbp+0D0h+var_140]
0x183056d1a  movsxd  rcx, dword ptr [rax+4]
0x183056d1e  lea     rax, [rbp+0D0h+var_140]
0x183056d22  add     rcx, rax
0x183056d25  xor     r8d, r8d
0x183056d28  lea     edx, [r8+2]
0x183056d2c  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x183056d32  mov     dil, 1
0x183056d35  test    rbx, rbx
0x183056d38  jz      short loc_183056D44
0x183056d3a  mov     rcx, rbx; this
0x183056d3d  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x183056d42  xor     ebx, ebx
0x183056d44  test    rbx, rbx
0x183056d47  jz      short loc_183056D52
0x183056d49  mov     rcx, rbx; this
0x183056d4c  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x183056d51  nop
0x183056d52  jmp     short loc_183056D68
0x183056d54  lea     rcx, aNoFileNameWasS_3; "No file name was specified."
0x183056d5b  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x183056d60  xor     dil, dil
0x183056d63  jmp     short loc_183056D68
0x183056d65  mov     dil, 1
0x183056d68  mov     rcx, [rbp+0D0h+var_140]
0x183056d6c  movsxd  rdx, dword ptr [rcx+4]
0x183056d70  mov     [rbp+rdx+0D0h+var_140], r13
0x183056d75  mov     rcx, [rbp+0D0h+var_140]
0x183056d79  movsxd  rdx, dword ptr [rcx+4]
0x183056d7d  lea     r8d, [rdx-0A8h]
0x183056d84  mov     [rbp+rdx+0D0h+var_144], r8d
0x183056d89  lea     rcx, [rbp+0D0h+var_138]
0x183056d8d  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x183056d92  lea     rcx, [rbp+0D0h+var_130]
0x183056d96  call    cs:__imp_??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ostream::~ostream<char,std::char_traits<char>>(void)
0x183056d9c  lea     rcx, [rbp+0D0h+var_98]
0x183056da0  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x183056da6  movzx   eax, dil
0x183056daa  mov     rcx, [rbp+0D0h+var_30]
0x183056db1  xor     rcx, rsp; StackCookie
0x183056db4  call    __security_check_cookie
0x183056db9  lea     r11, [rsp+1D0h+var_20]
0x183056dc1  mov     rbx, [r11+40h]
0x183056dc5  mov     rsi, [r11+48h]
0x183056dc9  mov     rsp, r11
0x183056dcc  pop     r15
0x183056dce  pop     r14
0x183056dd0  pop     r13
0x183056dd2  pop     rdi
0x183056dd3  pop     rbp
0x183056dd4  retn
```
