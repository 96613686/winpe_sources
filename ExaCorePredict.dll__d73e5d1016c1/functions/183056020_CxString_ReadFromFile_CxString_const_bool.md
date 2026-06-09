# CxString::ReadFromFile(CxString const &,bool)

- ea: `0x183056020`
- end: `0x183056425`
- name: `?ReadFromFile@CxString@@QEAA_NAEBV1@_N@Z`
- size: `1029`
- prototype: `bool __fastcall(CxString *__hidden this, const struct CxString *, bool)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x182d3efe0`
- `0x182d46e30`
- `0x182d47420`
- `0x182dcc6d0`
- `0x18303bef0`
- `0x18303bf50`
- `0x18304feb0`
- `0x183056020`
- `0x1830566f0`
- `0x183056fc0`
- `0x1830e8d10`
- `0x1832c3a50`
- `0x1832ce3b0`
- `0x1832dbeb0`

## import_xrefs

- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x1830562ab`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183056386`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x1830562ab`
- `MSVCP140!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x183056386`
- `MSVCP140!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x1830560e1`
- `MSVCP140!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x1830560e1`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1830563f5`
- `MSVCP140!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1830563f5`
- `MSVCP140!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18305608a`
- `MSVCP140!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18305608a`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x1830562cd`
- `MSVCP140!??7ios_base@std@@QEBA_NXZ` at `0x1830562cd`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x1830560ff`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x1830560ff`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x1830562b8`
- `MSVCP140!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x1830562b8`
- `MSVCP140!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x1830560a7`
- `MSVCP140!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x1830560a7`
- `MSVCP140!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1830563eb`
- `MSVCP140!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x1830563eb`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18305635c`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18305635c`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18305630c`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x183056330`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18305630c`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x183056330`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18305631a`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18305631a`

## string_xrefs

- `0x1830562ee`: `Cannot open file '%s'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CxString::ReadFromFile(CxString *this, CxRefCount **a2, char a3)
{
  CxRefCount *v6; // rax
  CxRefCount *v7; // rbx
  CxRefCount *v8; // rdi
  const char *DefaultDataDir; // rax
  CxRefCount **v10; // rax
  CxRefCount *v11; // rdi
  CxRefCount *v12; // rcx
  CxRefCount *v13; // rdi
  _QWORD *v14; // rdx
  bool v15; // zf
  __int64 v16; // rcx
  const char *v17; // rdx
  unsigned __int8 v18; // di
  _QWORD *v19; // rax
  unsigned __int64 v20; // rdi
  _QWORD *v21; // rdx
  CxRefCount *v23; // [rsp+70h] [rbp-90h] BYREF
  CxRefCount *v24[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v25[24]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v26[2]; // [rsp+A0h] [rbp-60h] BYREF
  void **v27; // [rsp+B0h] [rbp-50h] BYREF
  char v28[96]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+118h] [rbp+18h]
  char v30; // [rsp+121h] [rbp+21h]
  __int64 v31; // [rsp+124h] [rbp+24h]
  char v32; // [rsp+12Ch] [rbp+2Ch]
  __int64 v33; // [rsp+130h] [rbp+30h]
  _BYTE v34[96]; // [rsp+150h] [rbp+50h] BYREF

  v24[1] = (CxRefCount *)-2LL;
  memset_0(v26, 0, 0x110u);
  v26[0] = &std::ifstream::`vbtable';
  std::ios::ios(v34);
  LODWORD(v23) = 1;
  std::istream::istream(v26, &v27, 0, 0);
  *(_QWORD *)((char *)v26 + *(int *)(v26[0] + 4LL)) = &std::ifstream::`vftable';
  *(_DWORD *)&v25[*(int *)(v26[0] + 4LL) + 20] = *(_DWORD *)(v26[0] + 4LL) - 176;
  v24[0] = (CxRefCount *)&v27;
  std::streambuf::streambuf(&v27);
  v27 = &std::filebuf::`vftable';
  v32 = 0;
  v30 = 0;
  std::streambuf::_Init(&v27);
  v33 = 0;
  v31 = `std::filebuf::_Init'::`2'::_Stinit;
  v29 = 0;
  if ( !*a2 || !*((_QWORD *)*a2 + 4) )
  {
    CxReportError("No file name was specified.");
    v18 = 0;
    goto LABEL_50;
  }
  v6 = (CxRefCount *)operator new(0x30u);
  v24[0] = v6;
  if ( v6 )
    v6 = CxStringBase::CxStringBase(v6);
  v7 = 0;
  v23 = 0;
  if ( v6 )
  {
    v7 = v6;
    v23 = v6;
    CxRefCount::AddRef(v6);
  }
  if ( a3 )
  {
    v8 = *a2;
    if ( v8 )
    {
      v8 = (CxRefCount *)((char *)v8 + 16);
      if ( *((_QWORD *)v8 + 3) >= 0x10u )
        v8 = *(CxRefCount **)v8;
    }
    DefaultDataDir = GetDefaultDataDir();
    v10 = (CxRefCount **)CheckAndFixDataFileName(v24, v8, ".txt", DefaultDataDir, 1, 0, 0, 1, 0, 0, 0, 1, 0);
    if ( &v23 != v10 )
    {
      v11 = *v10;
      if ( v7 != *v10 )
      {
        if ( v7 )
          CxRefCount::Release(v7);
        v7 = v11;
        v23 = v11;
        if ( v11 )
          CxRefCount::AddRef(v11);
      }
    }
    v12 = v24[0];
    if ( v24[0] )
    {
      CxRefCount::Release(v24[0]);
      v12 = 0;
      v24[0] = 0;
    }
    if ( v12 )
      CxRefCount::Release(v12);
  }
  else if ( &v23 != a2 )
  {
    v13 = *a2;
    if ( v7 != v13 )
    {
      if ( v7 )
        CxRefCount::Release(v7);
      v7 = v13;
      v23 = v13;
      if ( !v13 )
        goto LABEL_31;
      CxRefCount::AddRef(v13);
    }
  }
  if ( v7 )
  {
    v14 = (_QWORD *)((char *)v7 + 16);
    if ( *((_QWORD *)v7 + 5) >= 0x10u )
      v14 = (_QWORD *)*v14;
    goto LABEL_32;
  }
LABEL_31:
  v14 = 0;
LABEL_32:
  v15 = std::filebuf::open(&v27, v14, 33) == 0;
  v16 = *(int *)(v26[0] + 4LL);
  if ( v15 )
    std::ios::setstate((char *)v26 + v16, 2);
  else
    std::ios::clear((char *)v26 + v16, 0, 0);
  if ( (unsigned __int8)std::ios_base::operator!((char *)v26 + *(int *)(v26[0] + 4LL)) )
  {
    if ( v7 )
    {
      v17 = (char *)v7 + 16;
      if ( *((_QWORD *)v7 + 5) >= 0x10u )
        v17 = *(const char **)v17;
    }
    else
    {
      v17 = 0;
    }
    CxReportError("Cannot open file '%s'.", v17);
    v18 = 0;
  }
  else
  {
    std::istream::seekg(v26, 0, 2);
    v19 = (_QWORD *)std::istream::tellg(v26, v25);
    v20 = *v19 + v19[1];
    std::istream::seekg(v26, 0, 0);
    CxString::Resize(this, v20, 95);
    v21 = (_QWORD *)(*(_QWORD *)this + 16LL);
    if ( *(_QWORD *)(*(_QWORD *)this + 40LL) >= 0x10u )
      v21 = (_QWORD *)*v21;
    std::istream::read(v26, v21, v20);
    if ( !std::filebuf::close(&v27) )
      std::ios::setstate((char *)v26 + *(int *)(v26[0] + 4LL), 2);
    v18 = 1;
  }
  if ( v7 )
    CxRefCount::Release(v7);
LABEL_50:
  *(_QWORD *)((char *)v26 + *(int *)(v26[0] + 4LL)) = &std::ifstream::`vftable';
  *(_DWORD *)&v25[*(int *)(v26[0] + 4LL) + 20] = *(_DWORD *)(v26[0] + 4LL) - 176;
  std::filebuf::~filebuf<char,std::char_traits<char>>(&v27);
  std::istream::~istream<char,std::char_traits<char>>(v28);
  std::ios::~ios<char,std::char_traits<char>>(v34);
  return v18;
}

```

## disassembly

```asm
0x183056020  push    rbp
0x183056022  push    rsi
0x183056023  push    rdi
0x183056024  push    r12
0x183056026  push    r14
0x183056028  lea     rbp, [rsp-0C0h]
0x183056030  sub     rsp, 1C0h
0x183056037  mov     [rbp+0E0h+var_160], 0FFFFFFFFFFFFFFFEh
0x18305603f  mov     [rsp+1E0h+arg_10], rbx
0x183056047  mov     rax, cs:__security_cookie
0x18305604e  xor     rax, rsp
0x183056051  mov     [rbp+0E0h+var_30], rax
0x183056058  movzx   esi, r8b
0x18305605c  mov     rdi, rdx
0x18305605f  mov     r14, rcx
0x183056062  mov     dword ptr [rsp+1E0h+var_170], 0
0x18305606a  xor     edx, edx; Val
0x18305606c  mov     r8d, 110h; Size
0x183056072  lea     rcx, [rbp+0E0h+var_140]; void *
0x183056076  call    memset_0
0x18305607b  lea     rax, ??_8?$basic_ifstream@DU?$char_traits@D@std@@@std@@7B@; const std::ifstream::`vbtable'
0x183056082  mov     [rbp+0E0h+var_140], rax
0x183056086  lea     rcx, [rbp+0E0h+var_90]
0x18305608a  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x183056090  nop
0x183056091  mov     dword ptr [rsp+1E0h+var_170], 1
0x183056099  xor     r9d, r9d
0x18305609c  xor     r8d, r8d
0x18305609f  lea     rdx, [rbp+0E0h+var_130]
0x1830560a3  lea     rcx, [rbp+0E0h+var_140]
0x1830560a7  call    cs:__imp_??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::istream::istream(std::streambuf *,bool)
0x1830560ad  nop
0x1830560ae  mov     rax, [rbp+0E0h+var_140]
0x1830560b2  movsxd  rcx, dword ptr [rax+4]
0x1830560b6  lea     r12, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x1830560bd  mov     [rbp+rcx+0E0h+var_140], r12
0x1830560c2  mov     rax, [rbp+0E0h+var_140]
0x1830560c6  movsxd  rcx, dword ptr [rax+4]
0x1830560ca  lea     edx, [rcx-0B0h]
0x1830560d0  mov     [rbp+rcx+0E0h+var_144], edx
0x1830560d4  lea     rax, [rbp+0E0h+var_130]
0x1830560d8  mov     [rsp+1E0h+var_168], rax
0x1830560dd  lea     rcx, [rbp+0E0h+var_130]
0x1830560e1  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x1830560e7  nop
0x1830560e8  lea     rax, ??_7?$basic_filebuf@DU?$char_traits@D@std@@@std@@6B@; const std::filebuf::`vftable'
0x1830560ef  mov     [rbp+0E0h+var_130], rax
0x1830560f3  mov     [rbp+0E0h+var_B4], 0
0x1830560f7  mov     [rbp+0E0h+var_BF], 0
0x1830560fb  lea     rcx, [rbp+0E0h+var_130]
0x1830560ff  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x183056105  mov     [rbp+0E0h+var_B0], 0
0x18305610d  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)'::`2'::_Stinit
0x183056114  mov     [rbp+0E0h+var_BC], rax
0x183056118  mov     [rbp+0E0h+var_C8], 0
0x183056120  mov     rax, [rdi]
0x183056123  test    rax, rax
0x183056126  jz      loc_1830563AE
0x18305612c  cmp     qword ptr [rax+20h], 0
0x183056131  jz      loc_1830563AE
0x183056137  mov     ecx, 30h ; '0'; unsigned __int64
0x18305613c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x183056141  mov     [rsp+1E0h+var_168], rax
0x183056146  test    rax, rax
0x183056149  jz      short loc_183056154
0x18305614b  mov     rcx, rax; this
0x18305614e  call    ??0CxStringBase@@QEAA@XZ; CxStringBase::CxStringBase(void)
0x183056153  nop
0x183056154  xor     ebx, ebx
0x183056156  mov     [rsp+1E0h+var_170], rbx
0x18305615b  test    rax, rax
0x18305615e  jz      short loc_183056171
0x183056160  mov     rbx, rax
0x183056163  mov     [rsp+1E0h+var_170], rax
0x183056168  mov     rcx, rax; this
0x18305616b  call    ?AddRef@CxRefCount@@QEAAJXZ; CxRefCount::AddRef(void)
0x183056170  nop
0x183056171  test    sil, sil
0x183056174  jz      loc_183056232
0x18305617a  mov     rdi, [rdi]
0x18305617d  test    rdi, rdi
0x183056180  jz      short loc_183056190
0x183056182  add     rdi, 10h
0x183056186  cmp     qword ptr [rdi+18h], 10h
0x18305618b  jb      short loc_183056190
0x18305618d  mov     rdi, [rdi]
0x183056190  call    ?GetDefaultDataDir@@YAPEBDXZ; GetDefaultDataDir(void)
0x183056195  mov     r9, rax
0x183056198  mov     [rsp+1E0h+var_180], 0
0x18305619d  mov     [rsp+1E0h+var_188], 1
0x1830561a2  mov     [rsp+1E0h+var_190], 0
0x1830561a7  mov     [rsp+1E0h+var_198], 0
0x1830561ac  mov     [rsp+1E0h+var_1A0], 0
0x1830561b1  mov     [rsp+1E0h+var_1A8], 1
0x1830561b6  mov     [rsp+1E0h+var_1B0], 0
0x1830561bb  mov     [rsp+1E0h+var_1B8], 0
0x1830561c0  mov     [rsp+1E0h+var_1C0], 1
0x1830561c5  lea     r8, aTxt; ".txt"
0x1830561cc  mov     rdx, rdi
0x1830561cf  lea     rcx, [rsp+1E0h+var_168]
0x1830561d4  call    ?CheckAndFixDataFileName@@YA?AVCxString@@PEBD_N11111@Z; CheckAndFixDataFileName(char const *,bool,bool,bool,bool,bool,bool)
0x1830561d9  nop
0x1830561da  lea     rcx, [rsp+1E0h+var_170]
0x1830561df  cmp     rcx, rax
0x1830561e2  jz      short loc_18305620F
0x1830561e4  mov     rdi, [rax]
0x1830561e7  cmp     rbx, rdi
0x1830561ea  jz      short loc_18305620F
0x1830561ec  test    rbx, rbx
0x1830561ef  jz      short loc_1830561F9
0x1830561f1  mov     rcx, rbx; this
0x1830561f4  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x1830561f9  mov     rbx, rdi
0x1830561fc  mov     [rsp+1E0h+var_170], rbx
0x183056201  test    rdi, rdi
0x183056204  jz      short loc_18305620F
0x183056206  mov     rcx, rdi; this
0x183056209  call    ?AddRef@CxRefCount@@QEAAJXZ; CxRefCount::AddRef(void)
0x18305620e  nop
0x18305620f  mov     rcx, [rsp+1E0h+var_168]; this
0x183056214  test    rcx, rcx
0x183056217  jz      short loc_183056225
0x183056219  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x18305621e  xor     ecx, ecx; this
0x183056220  mov     [rsp+1E0h+var_168], rcx
0x183056225  test    rcx, rcx
0x183056228  jz      short loc_183056230
0x18305622a  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x18305622f  nop
0x183056230  jmp     short loc_183056266
0x183056232  lea     rax, [rsp+1E0h+var_170]
0x183056237  cmp     rax, rdi
0x18305623a  jz      short loc_183056266
0x18305623c  mov     rdi, [rdi]
0x18305623f  cmp     rbx, rdi
0x183056242  jz      short loc_183056266
0x183056244  test    rbx, rbx
0x183056247  jz      short loc_183056251
0x183056249  mov     rcx, rbx; this
0x18305624c  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x183056251  mov     rbx, rdi
0x183056254  mov     [rsp+1E0h+var_170], rbx
0x183056259  test    rdi, rdi
0x18305625c  jz      short loc_18305627B
0x18305625e  mov     rcx, rdi; this
0x183056261  call    ?AddRef@CxRefCount@@QEAAJXZ; CxRefCount::AddRef(void)
0x183056266  test    rbx, rbx
0x183056269  jz      short loc_18305627B
0x18305626b  lea     rdx, [rbx+10h]
0x18305626f  cmp     qword ptr [rdx+18h], 10h
0x183056274  jb      short loc_18305627D
0x183056276  mov     rdx, [rdx]
0x183056279  jmp     short loc_18305627D
0x18305627b  xor     edx, edx
0x18305627d  mov     r9d, 40h ; '@'
0x183056283  lea     r8d, [r9-1Fh]
0x183056287  lea     rcx, [rbp+0E0h+var_130]
0x18305628b  call    ?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBDHH@Z; std::filebuf::open(char const *,int,int)
0x183056290  xor     r8d, r8d
0x183056293  test    rax, rax
0x183056296  mov     rax, [rbp+0E0h+var_140]
0x18305629a  movsxd  rcx, dword ptr [rax+4]
0x18305629e  lea     rax, [rbp+0E0h+var_140]
0x1830562a2  jnz     short loc_1830562B3
0x1830562a4  add     rcx, rax
0x1830562a7  lea     edx, [r8+2]
0x1830562ab  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x1830562b1  jmp     short loc_1830562BE
0x1830562b3  add     rcx, rax
0x1830562b6  xor     edx, edx
0x1830562b8  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x1830562be  mov     rax, [rbp+0E0h+var_140]
0x1830562c2  movsxd  rcx, dword ptr [rax+4]
0x1830562c6  lea     rax, [rbp+0E0h+var_140]
0x1830562ca  add     rcx, rax
0x1830562cd  call    cs:__imp_??7ios_base@std@@QEBA_NXZ; std::ios_base::operator!(void)
0x1830562d3  test    al, al
0x1830562d5  jz      short loc_183056302
0x1830562d7  test    rbx, rbx
0x1830562da  jz      short loc_1830562EC
0x1830562dc  lea     rdx, [rbx+10h]
0x1830562e0  cmp     qword ptr [rdx+18h], 10h
0x1830562e5  jb      short loc_1830562EE
0x1830562e7  mov     rdx, [rdx]
0x1830562ea  jmp     short loc_1830562EE
0x1830562ec  xor     edx, edx
0x1830562ee  lea     rcx, aCannotOpenFile; "Cannot open file '%s'."
0x1830562f5  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x1830562fa  xor     dil, dil
0x1830562fd  jmp     loc_18305638F
0x183056302  xor     edx, edx
0x183056304  lea     r8d, [rdx+2]
0x183056308  lea     rcx, [rbp+0E0h+var_140]
0x18305630c  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x183056312  lea     rdx, [rbp+0E0h+var_158]
0x183056316  lea     rcx, [rbp+0E0h+var_140]
0x18305631a  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x183056320  mov     rdi, [rax+8]
0x183056324  add     rdi, [rax]
0x183056327  xor     r8d, r8d
0x18305632a  xor     edx, edx
0x18305632c  lea     rcx, [rbp+0E0h+var_140]
0x183056330  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x183056336  mov     r8b, 5Fh ; '_'; char
0x183056339  mov     rdx, rdi; unsigned __int64
0x18305633c  mov     rcx, r14; this
0x18305633f  call    ?Resize@CxString@@QEAAX_KD@Z; CxString::Resize(unsigned __int64,char)
0x183056344  mov     rdx, [r14]
0x183056347  add     rdx, 10h
0x18305634b  cmp     qword ptr [rdx+18h], 10h
0x183056350  jb      short loc_183056355
0x183056352  mov     rdx, [rdx]
0x183056355  mov     r8, rdi
0x183056358  lea     rcx, [rbp+0E0h+var_140]
0x18305635c  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x183056362  lea     rcx, [rbp+0E0h+var_130]
0x183056366  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x18305636b  test    rax, rax
0x18305636e  jnz     short loc_18305638C
0x183056370  mov     rax, [rbp+0E0h+var_140]
0x183056374  movsxd  rcx, dword ptr [rax+4]
0x183056378  lea     rax, [rbp+0E0h+var_140]
0x18305637c  add     rcx, rax
0x18305637f  xor     r8d, r8d
0x183056382  lea     edx, [r8+2]
0x183056386  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x18305638c  mov     dil, 1
0x18305638f  test    rbx, rbx
0x183056392  jz      short loc_18305639E
0x183056394  mov     rcx, rbx; this
0x183056397  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x18305639c  xor     ebx, ebx
0x18305639e  test    rbx, rbx
0x1830563a1  jz      short loc_1830563AC
0x1830563a3  mov     rcx, rbx; this
0x1830563a6  call    ?Release@CxRefCount@@QEAAJXZ; CxRefCount::Release(void)
0x1830563ab  nop
0x1830563ac  jmp     short loc_1830563BD
0x1830563ae  lea     rcx, aNoFileNameWasS_3; "No file name was specified."
0x1830563b5  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x1830563ba  xor     dil, dil
0x1830563bd  mov     rcx, [rbp+0E0h+var_140]
0x1830563c1  movsxd  rdx, dword ptr [rcx+4]
0x1830563c5  mov     [rbp+rdx+0E0h+var_140], r12
0x1830563ca  mov     rcx, [rbp+0E0h+var_140]
0x1830563ce  movsxd  rdx, dword ptr [rcx+4]
0x1830563d2  lea     r8d, [rdx-0B0h]
0x1830563d9  mov     [rbp+rdx+0E0h+var_144], r8d
0x1830563de  lea     rcx, [rbp+0E0h+var_130]
0x1830563e2  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x1830563e7  lea     rcx, [rbp+0E0h+var_128]
0x1830563eb  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x1830563f1  lea     rcx, [rbp+0E0h+var_90]
0x1830563f5  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x1830563fb  movzx   eax, dil
0x1830563ff  mov     rcx, [rbp+0E0h+var_30]
0x183056406  xor     rcx, rsp; StackCookie
0x183056409  call    __security_check_cookie
0x18305640e  mov     rbx, [rsp+1E0h+arg_10]
0x183056416  add     rsp, 1C0h
0x18305641d  pop     r14
0x18305641f  pop     r12
0x183056421  pop     rdi
0x183056422  pop     rsi
0x183056423  pop     rbp
0x183056424  retn
```
