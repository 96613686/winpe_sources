# Gryps::BufferOverflowException::BufferOverflowException(__int64,unsigned __int64,unsigned __int64,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,uint,bool)

- ea: `0x18003920c`
- end: `0x180039572`
- name: `??0BufferOverflowException@Gryps@@QEAA@_J_K1AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I_N@Z`
- size: `870`
- prototype: ``
- caller_count: `13`
- callee_count: `15`
- tags: ``

## callers

- `0x180038c0c`
- `0x180038cc4`
- `0x180038d7c`
- `0x180038e34`
- `0x18003b8a4`
- `0x18003b984`
- `0x18003e85c`
- `0x18003e910`
- `0x18003e9c8`
- `0x18003ea7c`
- `0x180043e10`
- `0x180055c80`
- `0x180055e34`

## callees

- `0x180002240`
- `0x180003345`
- `0x180003351`
- `0x180038134`
- `0x180038308`
- `0x1800383c8`
- `0x1800389a8`
- `0x180038eec`
- `0x180038fec`
- `0x18003920c`
- `0x180039678`
- `0x18003974c`
- `0x18003bfa4`
- `0x180056830`
- `0x180058010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180039356`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180039356`
- `msvcp_win!?setprecision@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x1800392ce`
- `msvcp_win!?setprecision@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x1800392ce`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18003929f`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18003929f`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18003934c`
- `msvcp_win!??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18003934c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z` at `0x1800392fc`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z` at `0x1800392fc`

## string_xrefs

- `0x180039376`: `Reading `

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall Gryps::BufferOverflowException::BufferOverflowException(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7)
{
  size_t v11; // r14
  __int64 v12; // rax
  __int64 v13; // rax
  void **v14; // rsi
  char *v15; // r15
  size_t Size; // rbx
  void *v17; // r8
  char *v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // eax
  __int64 v24; // [rsp+30h] [rbp-D0h]
  char v25[16]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  char v28[8]; // [rsp+68h] [rbp-98h] BYREF
  char v29[120]; // [rsp+70h] [rbp-90h] BYREF
  char v30[104]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v31; // [rsp+150h] [rbp+50h] BYREF
  __int128 v32; // [rsp+160h] [rbp+60h]
  _OWORD v33[2]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v34[32]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v35[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v36[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v37[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v38[32]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v39[32]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v40[32]; // [rsp+250h] [rbp+150h] BYREF

  v11 = 0;
  memset(v33, 0, sizeof(v33));
  std::string::_Construct<1,char const *>(v33, &byte_18006CCAB, 0);
  v24 = Gryps::toString<unsigned __int64>(v40, a4);
  std::ostringstream::ostringstream(&v27);
  v12 = std::setw(v25, 0);
  (*(void (__fastcall **)(char *, _QWORD))v12)(&v28[*(int *)(v27 + 4) - 8], *(_QWORD *)(v12 + 8));
  v13 = std::setprecision(v26, 6);
  (*(void (__fastcall **)(char *, _QWORD))v13)(&v28[*(int *)(v27 + 4) - 8], *(_QWORD *)(v13 + 8));
  std::ostream::operator<<(&v27, a2);
  std::stringbuf::str(v28, v34);
  *(_QWORD *)&v28[*(int *)(v27 + 4) - 8] = &std::ostringstream::`vftable';
  *(_DWORD *)&v26[*(int *)(v27 + 4) + 12] = *(_DWORD *)(v27 + 4) - 136;
  std::stringbuf::~stringbuf(v28);
  std::ostream::~ostream<char,std::char_traits<char>>(v29);
  std::ios::~ios<char,std::char_traits<char>>(v30);
  v14 = (void **)Gryps::toString<unsigned __int64>(v39, a3);
  v15 = "Reading ";
  if ( !a7 )
    v15 = "Writing ";
  Size = -1;
  do
    ++Size;
  while ( v15[Size] );
  v17 = v14[2];
  if ( Size > (_BYTE *)v14[3] - (_BYTE *)v17 )
  {
    v14 = (void **)std::string::_Reallocate_grow_by<_lambda_e9b99a188f9a316a73b83d1e72db26de_,unsigned __int64,char const *,unsigned __int64>(
                     v14,
                     v15,
                     Size);
  }
  else
  {
    v14[2] = (char *)v17 + Size;
    if ( (unsigned __int64)v14[3] <= 0xF )
      v18 = (char *)v14;
    else
      v18 = (char *)*v14;
    if ( &v15[Size] <= v18 || v15 > &v18[(_QWORD)v17] )
    {
      v11 = Size;
    }
    else if ( v18 > v15 )
    {
      v11 = v18 - v15;
    }
    memmove_0(&v18[Size], v18, (size_t)v17 + 1);
    memcpy_0(v18, v15, v11);
    memcpy_0(&v18[v11], &v15[Size + v11], Size - v11);
  }
  v31 = 0;
  v32 = 0;
  v31 = *(_OWORD *)v14;
  v32 = *((_OWORD *)v14 + 1);
  v14[2] = 0;
  v14[3] = (void *)15;
  *(_BYTE *)v14 = 0;
  v19 = std::operator+<char>(v38, &v31, " bytes of data at offset ");
  v20 = std::operator+<char>(v37, v19, v34);
  v21 = std::operator+<char>(v36, v20, " in a buffer of total size ");
  v22 = std::operator+<char>(v35, v21, v24);
  Gryps::Exception::Exception((_DWORD)a1, v22, a5, a6, (__int64)v33);
  std::string::~string(v35);
  std::string::~string(v36);
  std::string::~string(v37);
  std::string::~string(v38);
  std::string::~string(&v31);
  std::string::~string(v39);
  std::string::~string(v34);
  std::string::~string(v40);
  std::string::~string(v33);
  *a1 = &Gryps::BufferOverflowException::`vftable';
  return a1;
}

```

## disassembly

```asm
0x18003920c  push    rbp
0x18003920e  push    rbx
0x18003920f  push    rsi
0x180039210  push    rdi
0x180039211  push    r12
0x180039213  push    r13
0x180039215  push    r14
0x180039217  push    r15
0x180039219  lea     rbp, [rsp-188h]
0x180039221  sub     rsp, 288h
0x180039228  mov     rax, cs:__security_cookie
0x18003922f  xor     rax, rsp
0x180039232  mov     [rbp+1C0h+var_50], rax
0x180039239  mov     rbx, r9
0x18003923c  mov     rsi, r8
0x18003923f  mov     rdi, rdx
0x180039242  mov     r12, rcx
0x180039245  mov     [rsp+2C0h+var_290], rcx
0x18003924a  mov     r13, [rbp+1C0h+arg_20]
0x180039251  xor     r14d, r14d
0x180039254  xorps   xmm0, xmm0
0x180039257  movups  [rbp+1C0h+var_150], xmm0
0x18003925b  xorps   xmm1, xmm1
0x18003925e  movdqu  [rbp+1C0h+var_140], xmm1
0x180039266  xor     r8d, r8d
0x180039269  lea     rdx, byte_18006CCAB
0x180039270  lea     rcx, [rbp+1C0h+var_150]
0x180039274  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180039279  nop
0x18003927a  mov     rdx, rbx
0x18003927d  lea     rcx, [rbp+1C0h+var_70]
0x180039284  call    ??$toString@_K@Gryps@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KIIPEAX@Z; Gryps::toString<unsigned __int64>(unsigned __int64,uint,uint,void *)
0x180039289  mov     [rsp+2C0h+var_290], rax
0x18003928e  lea     rcx, [rsp+2C0h+var_260]
0x180039293  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180039298  xor     edx, edx
0x18003929a  lea     rcx, [rsp+2C0h+var_280]
0x18003929f  call    cs:__imp_?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x1800392a5  mov     r8, rax
0x1800392a8  mov     rax, [rsp+2C0h+var_260]
0x1800392ad  movsxd  rcx, dword ptr [rax+4]
0x1800392b1  lea     rax, [rsp+2C0h+var_260]
0x1800392b6  add     rcx, rax
0x1800392b9  mov     rdx, [r8+8]
0x1800392bd  mov     rax, [r8]
0x1800392c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392c5  lea     edx, [r14+6]
0x1800392c9  lea     rcx, [rsp+2C0h+var_270]
0x1800392ce  call    cs:__imp_?setprecision@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setprecision(__int64)
0x1800392d4  mov     r8, rax
0x1800392d7  mov     rax, [rsp+2C0h+var_260]
0x1800392dc  movsxd  rcx, dword ptr [rax+4]
0x1800392e0  lea     rax, [rsp+2C0h+var_260]
0x1800392e5  add     rcx, rax
0x1800392e8  mov     rdx, [r8+8]
0x1800392ec  mov     rax, [r8]
0x1800392ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392f4  mov     rdx, rdi
0x1800392f7  lea     rcx, [rsp+2C0h+var_260]
0x1800392fc  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@_J@Z; std::ostream::operator<<(__int64)
0x180039302  lea     rdx, [rbp+1C0h+var_130]
0x180039309  lea     rcx, [rsp+2C0h+var_258]
0x18003930e  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180039313  mov     rax, [rsp+2C0h+var_260]
0x180039318  movsxd  rcx, dword ptr [rax+4]
0x18003931c  lea     rax, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x180039323  mov     [rsp+rcx+2C0h+var_260], rax
0x180039328  mov     rax, [rsp+2C0h+var_260]
0x18003932d  movsxd  rcx, dword ptr [rax+4]
0x180039331  lea     r8d, [rcx-88h]
0x180039338  mov     [rsp+rcx+2C0h+var_264], r8d
0x18003933d  lea     rcx, [rsp+2C0h+var_258]
0x180039342  call    ??1?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::stringbuf::~stringbuf(void)
0x180039347  lea     rcx, [rsp+2C0h+var_250]
0x18003934c  call    cs:__imp_??1?$basic_ostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ostream::~ostream<char,std::char_traits<char>>(void)
0x180039352  lea     rcx, [rbp+1C0h+var_1D8]
0x180039356  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x18003935c  nop
0x18003935d  mov     rdx, rsi
0x180039360  lea     rcx, [rbp+1C0h+var_90]
0x180039367  call    ??$toString@_K@Gryps@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KIIPEAX@Z; Gryps::toString<unsigned __int64>(unsigned __int64,uint,uint,void *)
0x18003936c  mov     rsi, rax
0x18003936f  lea     rax, aWriting; "Writing "
0x180039376  lea     r15, aReading; "Reading "
0x18003937d  cmp     [rbp+1C0h+arg_30], r14b
0x180039384  cmovz   r15, rax
0x180039388  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003938c  inc     rbx
0x18003938f  cmp     [r15+rbx], r14b
0x180039393  jnz     short loc_18003938C
0x180039395  mov     r8, [rsi+10h]
0x180039399  mov     rax, [rsi+18h]
0x18003939d  sub     rax, r8
0x1800393a0  cmp     rbx, rax
0x1800393a3  ja      short loc_180039416
0x1800393a5  lea     rax, [rbx+r8]
0x1800393a9  mov     [rsi+10h], rax
0x1800393ad  cmp     qword ptr [rsi+18h], 0Fh
0x1800393b2  jbe     short loc_1800393B9
0x1800393b4  mov     rdi, [rsi]
0x1800393b7  jmp     short loc_1800393BC
0x1800393b9  mov     rdi, rsi
0x1800393bc  lea     rax, [rbx+r15]
0x1800393c0  cmp     rax, rdi
0x1800393c3  jbe     short loc_1800393DB
0x1800393c5  lea     rax, [r8+rdi]
0x1800393c9  cmp     r15, rax
0x1800393cc  ja      short loc_1800393DB
0x1800393ce  cmp     rdi, r15
0x1800393d1  jbe     short loc_1800393DE
0x1800393d3  mov     r14, rdi
0x1800393d6  sub     r14, r15
0x1800393d9  jmp     short loc_1800393DE
0x1800393db  mov     r14, rbx
0x1800393de  inc     r8; Size
0x1800393e1  lea     rcx, [rbx+rdi]; void *
0x1800393e5  mov     rdx, rdi; Src
0x1800393e8  call    memmove_0
0x1800393ed  mov     r8, r14; Size
0x1800393f0  mov     rdx, r15; Src
0x1800393f3  mov     rcx, rdi; void *
0x1800393f6  call    memcpy_0
0x1800393fb  mov     r8, rbx
0x1800393fe  sub     r8, r14; Size
0x180039401  lea     rdx, [rbx+r15]
0x180039405  add     rdx, r14; Src
0x180039408  lea     rcx, [rdi+r14]; void *
0x18003940c  call    memcpy_0
0x180039411  xor     r14d, r14d
0x180039414  jmp     short loc_18003942E
0x180039416  mov     [rsp+2C0h+Size], rbx; Size
0x18003941b  mov     [rsp+2C0h+var_2A0], r15; void *
0x180039420  mov     rdx, rbx
0x180039423  mov     rcx, rsi; Src
0x180039426  call    ??$_Reallocate_grow_by@V_lambda_e9b99a188f9a316a73b83d1e72db26de_@@_KPEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e9b99a188f9a316a73b83d1e72db26de_@@_KPEBD2@Z; std::string::_Reallocate_grow_by<_lambda_e9b99a188f9a316a73b83d1e72db26de_,unsigned __int64,char const *,unsigned __int64>(unsigned __int64,_lambda_e9b99a188f9a316a73b83d1e72db26de_,unsigned __int64,char const *,unsigned __int64)
0x18003942b  mov     rsi, rax
0x18003942e  xorps   xmm0, xmm0
0x180039431  movups  [rbp+1C0h+var_170], xmm0
0x180039435  xorps   xmm1, xmm1
0x180039438  movdqu  [rbp+1C0h+var_160], xmm1
0x18003943d  movups  xmm0, xmmword ptr [rsi]
0x180039440  movups  [rbp+1C0h+var_170], xmm0
0x180039444  movups  xmm1, xmmword ptr [rsi+10h]
0x180039448  movups  [rbp+1C0h+var_160], xmm1
0x18003944c  mov     [rsi+10h], r14
0x180039450  mov     qword ptr [rsi+18h], 0Fh
0x180039458  mov     [rsi], r14b
0x18003945b  lea     r8, aBytesOfDataAtO; " bytes of data at offset "
0x180039462  lea     rdx, [rbp+1C0h+var_170]
0x180039466  lea     rcx, [rbp+1C0h+var_B0]
0x18003946d  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180039472  nop
0x180039473  lea     r8, [rbp+1C0h+var_130]
0x18003947a  mov     rdx, rax
0x18003947d  lea     rcx, [rbp+1C0h+var_D0]
0x180039484  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x180039489  nop
0x18003948a  lea     r8, aInABufferOfTot; " in a buffer of total size "
0x180039491  mov     rdx, rax
0x180039494  lea     rcx, [rbp+1C0h+var_F0]
0x18003949b  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800394a0  nop
0x1800394a1  mov     r8, [rsp+2C0h+var_290]
0x1800394a6  mov     rdx, rax
0x1800394a9  lea     rcx, [rbp+1C0h+var_110]
0x1800394b0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1800394b5  lea     rcx, [rbp+1C0h+var_150]
0x1800394b9  mov     [rsp+2C0h+var_2A0], rcx
0x1800394be  mov     r9d, [rbp+1C0h+arg_28]
0x1800394c5  mov     r8, r13
0x1800394c8  mov     rdx, rax
0x1800394cb  mov     rcx, r12
0x1800394ce  call    ??0Exception@Gryps@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0I0@Z; Gryps::Exception::Exception(std::string const &,std::string const &,uint,std::string const &)
0x1800394d3  lea     rcx, [rbp+1C0h+var_110]
0x1800394da  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800394df  nop
0x1800394e0  lea     rcx, [rbp+1C0h+var_F0]
0x1800394e7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800394ec  nop
0x1800394ed  lea     rcx, [rbp+1C0h+var_D0]
0x1800394f4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800394f9  nop
0x1800394fa  lea     rcx, [rbp+1C0h+var_B0]
0x180039501  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039506  nop
0x180039507  lea     rcx, [rbp+1C0h+var_170]
0x18003950b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039510  nop
0x180039511  lea     rcx, [rbp+1C0h+var_90]
0x180039518  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003951d  nop
0x18003951e  lea     rcx, [rbp+1C0h+var_130]
0x180039525  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003952a  nop
0x18003952b  lea     rcx, [rbp+1C0h+var_70]
0x180039532  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039537  nop
0x180039538  lea     rcx, [rbp+1C0h+var_150]
0x18003953c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180039541  lea     rax, ??_7BufferOverflowException@Gryps@@6B@; const Gryps::BufferOverflowException::`vftable'
0x180039548  mov     [r12], rax
0x18003954c  mov     rax, r12
0x18003954f  mov     rcx, [rbp+1C0h+var_50]
0x180039556  xor     rcx, rsp; StackCookie
0x180039559  call    __security_check_cookie
0x18003955e  add     rsp, 288h
0x180039565  pop     r15
0x180039567  pop     r14
0x180039569  pop     r13
0x18003956b  pop     r12
0x18003956d  pop     rdi
0x18003956e  pop     rsi
0x18003956f  pop     rbx
0x180039570  pop     rbp
0x180039571  retn
```
