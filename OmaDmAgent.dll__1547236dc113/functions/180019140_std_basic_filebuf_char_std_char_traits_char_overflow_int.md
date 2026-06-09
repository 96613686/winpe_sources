# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x180019140`
- end: `0x18001937e`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `574`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006244`
- `0x180018050`
- `0x180019050`
- `0x180019098`
- `0x180019140`
- `0x18001f420`

## import_xrefs

- `msvcp110_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x1800191b2`
- `msvcp110_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x1800191b2`
- `msvcp110_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x180019178`
- `msvcp110_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18001919e`
- `msvcp110_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x180019178`
- `msvcp110_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18001919e`
- `msvcp110_win!?out@?$codecvt@DDH@std@@QEBAHAEAHPEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x180019275`
- `msvcp110_win!?out@?$codecvt@DDH@std@@QEBAHAEAHPEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x180019275`
- `msvcp110_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18001918c`
- `msvcp110_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18001918c`
- `msvcrt!fwrite` at `0x1800192c6`
- `msvcrt!fwrite` at `0x1800192c6`
- `msvcrt!fputc` at `0x1800191f1`
- `msvcrt!fputc` at `0x180019324`
- `msvcrt!fputc` at `0x1800191f1`
- `msvcrt!fputc` at `0x180019324`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned int v4; // esi
  unsigned __int64 v6; // rbx
  void **v7; // r10
  unsigned __int64 v8; // r9
  void **v9; // r8
  void **v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  void **v14; // rax
  signed __int64 v15; // rbx
  void **v16; // rcx
  char v17; // [rsp+40h] [rbp-40h] BYREF
  char v18[7]; // [rsp+41h] [rbp-3Fh] BYREF
  void **v19; // [rsp+48h] [rbp-38h] BYREF
  char *v20; // [rsp+50h] [rbp-30h] BYREF
  void *Buffer[2]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-18h]
  unsigned __int64 v23; // [rsp+70h] [rbp-10h]

  v4 = -1;
  if ( a2 == -1 )
    return 0;
  if ( ((__int64 (*)(void))std::streambuf::pptr)() )
  {
    v6 = std::streambuf::epptr(a1);
    if ( std::streambuf::pptr(a1) < v6 )
    {
      *(_BYTE *)std::streambuf::_Pninc(a1) = a2;
      return a2;
    }
  }
  if ( !*(_QWORD *)(a1 + 144) )
    return v4;
  std::filebuf::_Reset_back(a1);
  if ( !*(_QWORD *)(a1 + 120) )
  {
    if ( fputc((char)a2, *(FILE **)(a1 + 144)) != -1 )
      return a2;
    return v4;
  }
  v17 = a2;
  v20 = 0;
  v19 = 0;
  std::string::string(Buffer);
LABEL_13:
  v7 = (void **)Buffer[0];
  v8 = v23;
  while ( 1 )
  {
    v9 = Buffer;
    if ( v8 >= 0x10 )
      v9 = v7;
    v10 = Buffer;
    if ( v8 >= 0x10 )
      v10 = v7;
    v11 = std::codecvt<char,char,int>::out(
            *(_QWORD *)(a1 + 120),
            a1 + 132,
            &v17,
            v18,
            &v20,
            v10,
            (char *)v9 + v22,
            &v19);
    if ( v11 )
    {
      v13 = v11 - 1;
      if ( v13 )
      {
        if ( v13 == 2 && fputc(v17, *(FILE **)(a1 + 144)) != -1 )
          v4 = a2;
LABEL_34:
        LOBYTE(v12) = 1;
        std::string::_Tidy(Buffer, v12, 0);
        return v4;
      }
    }
    v14 = Buffer;
    v7 = (void **)Buffer[0];
    v8 = v23;
    if ( v23 >= 0x10 )
      v14 = (void **)Buffer[0];
    v15 = (char *)v19 - (char *)v14;
    if ( v19 != v14 )
    {
      v16 = Buffer;
      if ( v23 >= 0x10 )
        v16 = (void **)Buffer[0];
      if ( v15 != fwrite(v16, 1u, (char *)v19 - (char *)v14, *(FILE **)(a1 + 144)) )
        goto LABEL_34;
      v8 = v23;
      v7 = (void **)Buffer[0];
    }
    *(_BYTE *)(a1 + 129) = 1;
    if ( v20 != &v17 )
      break;
    if ( !v15 )
    {
      if ( v22 < 0x20 )
      {
        std::string::append(Buffer, 8, 0);
        goto LABEL_13;
      }
      goto LABEL_34;
    }
  }
  LOBYTE(v12) = 1;
  std::string::_Tidy(Buffer, v12, 0);
  return a2;
}

```

## disassembly

```asm
0x180019140  mov     [rsp-28h+arg_10], rbx
0x180019145  push    rbp
0x180019146  push    rsi
0x180019147  push    rdi
0x180019148  push    r14
0x18001914a  push    r15
0x18001914c  mov     rbp, rsp
0x18001914f  sub     rsp, 80h
0x180019156  mov     rax, cs:__security_cookie
0x18001915d  xor     rax, rsp
0x180019160  mov     [rbp+var_8], rax
0x180019164  mov     r14d, edx
0x180019167  mov     rdi, rcx
0x18001916a  or      esi, 0FFFFFFFFh
0x18001916d  cmp     edx, esi
0x18001916f  jnz     short loc_180019178
0x180019171  xor     eax, eax
0x180019173  jmp     loc_18001935A
0x180019178  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x18001917f  nop     dword ptr [rax+rax+00h]
0x180019184  test    rax, rax
0x180019187  jz      short loc_1800191C6
0x180019189  mov     rcx, rdi
0x18001918c  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x180019193  nop     dword ptr [rax+rax+00h]
0x180019198  mov     rbx, rax
0x18001919b  mov     rcx, rdi
0x18001919e  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800191a5  nop     dword ptr [rax+rax+00h]
0x1800191aa  cmp     rax, rbx
0x1800191ad  jnb     short loc_1800191C6
0x1800191af  mov     rcx, rdi
0x1800191b2  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x1800191b9  nop     dword ptr [rax+rax+00h]
0x1800191be  mov     [rax], r14b
0x1800191c1  jmp     loc_180019357
0x1800191c6  cmp     qword ptr [rdi+90h], 0
0x1800191ce  jnz     short loc_1800191D7
0x1800191d0  mov     eax, esi
0x1800191d2  jmp     loc_18001935A
0x1800191d7  mov     rcx, rdi
0x1800191da  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800191df  cmp     qword ptr [rdi+78h], 0
0x1800191e4  jnz     short loc_180019205
0x1800191e6  movsx   ecx, r14b; Character
0x1800191ea  mov     rdx, [rdi+90h]; Stream
0x1800191f1  call    cs:__imp_fputc
0x1800191f8  nop     dword ptr [rax+rax+00h]
0x1800191fd  cmp     eax, esi
0x1800191ff  cmovnz  esi, r14d
0x180019203  jmp     short loc_1800191D0
0x180019205  mov     [rbp+var_40], r14b
0x180019209  mov     [rbp+var_30], 0
0x180019211  mov     [rbp+var_38], 0
0x180019219  lea     rcx, [rbp+Buffer]
0x18001921d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x180019222  nop
0x180019223  mov     r10, [rbp+Buffer]
0x180019227  mov     r9, [rbp+var_10]
0x18001922b  lea     r8, [rbp+Buffer]
0x18001922f  cmp     r9, 10h
0x180019233  cmovnb  r8, r10
0x180019237  mov     rax, [rbp+var_18]
0x18001923b  lea     rdx, [rbp+Buffer]
0x18001923f  cmovnb  rdx, r10
0x180019243  add     rax, r8
0x180019246  lea     rcx, [rbp+var_38]
0x18001924a  mov     [rsp+80h+var_48], rcx
0x18001924f  mov     [rsp+80h+var_50], rax
0x180019254  mov     [rsp+80h+var_58], rdx
0x180019259  lea     rax, [rbp+var_30]
0x18001925d  mov     [rsp+80h+var_60], rax
0x180019262  lea     r9, [rbp+var_3F]
0x180019266  lea     r8, [rbp+var_40]
0x18001926a  lea     rdx, [rdi+84h]
0x180019271  mov     rcx, [rdi+78h]
0x180019275  call    cs:__imp_?out@?$codecvt@DDH@std@@QEBAHAEAHPEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,int>::out(int &,char const *,char const *,char const * &,char *,char *,char * &)
0x18001927c  nop     dword ptr [rax+rax+00h]
0x180019281  test    eax, eax
0x180019283  jz      short loc_18001928E
0x180019285  sub     eax, 1
0x180019288  jnz     loc_180019314
0x18001928e  lea     rax, [rbp+Buffer]
0x180019292  mov     r10, [rbp+Buffer]
0x180019296  mov     r9, [rbp+var_10]
0x18001929a  cmp     r9, 10h
0x18001929e  cmovnb  rax, r10
0x1800192a2  mov     rbx, [rbp+var_38]
0x1800192a6  sub     rbx, rax
0x1800192a9  jz      short loc_1800192DF
0x1800192ab  lea     rcx, [rbp+Buffer]
0x1800192af  cmp     r9, 10h
0x1800192b3  cmovnb  rcx, r10; Buffer
0x1800192b7  mov     r9, [rdi+90h]; Stream
0x1800192be  mov     r8, rbx; ElementCount
0x1800192c1  mov     edx, 1; ElementSize
0x1800192c6  call    cs:__imp_fwrite
0x1800192cd  nop     dword ptr [rax+rax+00h]
0x1800192d2  cmp     rbx, rax
0x1800192d5  jnz     short loc_180019336
0x1800192d7  mov     r9, [rbp+var_10]
0x1800192db  mov     r10, [rbp+Buffer]
0x1800192df  mov     byte ptr [rdi+81h], 1
0x1800192e6  lea     rax, [rbp+var_40]
0x1800192ea  cmp     [rbp+var_30], rax
0x1800192ee  jnz     short loc_180019349
0x1800192f0  test    rbx, rbx
0x1800192f3  jnz     loc_18001922B
0x1800192f9  cmp     [rbp+var_18], 20h ; ' '
0x1800192fe  jnb     short loc_180019336
0x180019300  xor     r8d, r8d
0x180019303  lea     edx, [rbx+8]
0x180019306  lea     rcx, [rbp+Buffer]
0x18001930a  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x18001930f  jmp     loc_180019223
0x180019314  cmp     eax, 2
0x180019317  jnz     short loc_180019336
0x180019319  movsx   ecx, [rbp+var_40]; Character
0x18001931d  mov     rdx, [rdi+90h]; Stream
0x180019324  call    cs:__imp_fputc
0x18001932b  nop     dword ptr [rax+rax+00h]
0x180019330  cmp     eax, esi
0x180019332  cmovnz  esi, r14d
0x180019336  xor     r8d, r8d
0x180019339  mov     dl, 1
0x18001933b  lea     rcx, [rbp+Buffer]
0x18001933f  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180019344  jmp     loc_1800191D0
0x180019349  xor     r8d, r8d
0x18001934c  mov     dl, 1
0x18001934e  lea     rcx, [rbp+Buffer]
0x180019352  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180019357  mov     eax, r14d
0x18001935a  mov     rcx, [rbp+var_8]
0x18001935e  xor     rcx, rsp; StackCookie
0x180019361  call    __security_check_cookie
0x180019366  mov     rbx, [rsp+80h+arg_10]
0x18001936e  add     rsp, 80h
0x180019375  pop     r15
0x180019377  pop     r14
0x180019379  pop     rdi
0x18001937a  pop     rsi
0x18001937b  pop     rbp
0x18001937c  retn
```
