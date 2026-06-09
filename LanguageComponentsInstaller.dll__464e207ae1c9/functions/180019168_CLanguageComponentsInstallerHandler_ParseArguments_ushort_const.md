# CLanguageComponentsInstallerHandler::ParseArguments(ushort const *)

- ea: `0x180019168`
- end: `0x180019469`
- name: `?ParseArguments@CLanguageComponentsInstallerHandler@@AEAAXPEBG@Z`
- size: `769`
- prototype: `void __fastcall(CLanguageComponentsInstallerHandler *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d0f0`

## callees

- `0x180003520`
- `0x180003544`
- `0x180004100`
- `0x180005954`
- `0x180006380`
- `0x18000a81c`
- `0x18000b218`
- `0x180012870`
- `0x180019168`

## import_xrefs

- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x1800193e9`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x1800193e9`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180019430`
- `msvcp_win!??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180019430`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18001943a`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18001943a`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1800191f2`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1800191f2`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800191d4`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800191d4`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18001922e`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18001922e`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x18001925f`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x18001925f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019341`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001936c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019397`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800193c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019341`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001936c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019397`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800193c2`

## string_xrefs

- `0x180019390`: `Uninstall`
- `0x180019365`: `Install`

## pseudocode

```c
void __fastcall CLanguageComponentsInstallerHandler::ParseArguments(
        CLanguageComponentsInstallerHandler *this,
        const unsigned __int16 *a2)
{
  __int64 v3; // r8
  void **v4; // r14
  size_t v5; // rbx
  _QWORD *v6; // rdi
  void *v7; // rax
  int v8; // eax
  __int128 *v9; // rdx
  __int128 *v10; // rdx
  __int128 *v11; // rdx
  __int128 *v12; // rdx
  __int64 v13; // rax
  void *Src[2]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v16; // [rsp+40h] [rbp-C0h]
  void ***v17; // [rsp+48h] [rbp-B8h]
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v20; // [rsp+68h] [rbp-98h]
  _QWORD v21[2]; // [rsp+70h] [rbp-90h] BYREF
  void **v22; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[16]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+98h] [rbp-68h]
  _QWORD *v25; // [rsp+B8h] [rbp-48h]
  _DWORD *v26; // [rsp+D0h] [rbp-30h]
  char *v27; // [rsp+E8h] [rbp-18h]
  int v28; // [rsp+F0h] [rbp-10h]
  _BYTE v29[96]; // [rsp+100h] [rbp+0h] BYREF

  *(_OWORD *)Src = 0;
  v15 = 0;
  v16 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  std::wstring::_Construct<1,unsigned short const *>(Src);
  v21[0] = &std::basic_istringstream<unsigned short>::`vbtable';
  std::basic_ios<unsigned short>::basic_ios<unsigned short>(v29);
  std::basic_istream<unsigned short>::basic_istream<unsigned short>(v21, &v22, 0, 0, 1);
  *(_QWORD *)((char *)v21 + *(int *)(v21[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v20 + *(int *)(v21[0] + 4LL) + 4) = *(_DWORD *)(v21[0] + 4LL) - 144;
  v17 = &v22;
  std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>(&v22);
  v22 = &std::basic_stringbuf<unsigned short>::`vftable';
  v4 = Src;
  if ( v16 > 7 )
    v4 = (void **)Src[0];
  if ( v15 > 0x7FFFFFFF )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  if ( v15 )
  {
    v5 = 2 * v15;
    if ( 2 * v15 )
    {
      if ( v5 < 0x1000 )
      {
        v6 = operator new(v5);
      }
      else
      {
        if ( v5 + 39 < v5 )
          __scrt_throw_std_bad_array_new_length();
        v7 = operator new(v5 + 39);
        if ( !v7 )
          __fastfail(5u);
        v6 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v6 - 1) = v7;
      }
    }
    else
    {
      v6 = 0;
    }
    memcpy_0(v6, v4, v5);
    v27 = (char *)v6 + v5;
    *v24 = v6;
    *v25 = v6;
    *v26 = (__int64)v5 >> 1;
    v8 = 3;
  }
  else
  {
    v8 = 2;
    v27 = 0;
  }
  v28 = v8;
  std::wstring::~wstring(Src);
  v18 = 0;
  v19 = 0;
  v20 = 7;
  LOWORD(v18) = 0;
  while ( 1 )
  {
    v13 = std::operator>><unsigned short>(v21, &v18);
    if ( !(unsigned __int8)std::ios_base::operator bool(v13 + *(int *)(*(_QWORD *)v13 + 4LL)) )
      break;
    v9 = &v18;
    if ( v20 > 7 )
      v9 = (__int128 *)v18;
    if ( (unsigned int)_o__wcsicmp(L"Periodic", v9) )
    {
      v10 = &v18;
      if ( v20 > 7 )
        v10 = (__int128 *)v18;
      if ( (unsigned int)_o__wcsicmp(L"Install", v10) )
      {
        v11 = &v18;
        if ( v20 > 7 )
          v11 = (__int128 *)v18;
        if ( (unsigned int)_o__wcsicmp(L"Uninstall", v11) )
        {
          v12 = &v18;
          if ( v20 > 7 )
            v12 = (__int128 *)v18;
          if ( !(unsigned int)_o__wcsicmp(L"OnDemandNoToast", v12) )
            *((_BYTE *)this + 64) = 1;
        }
        else
        {
          *((_DWORD *)this + 15) = 2;
        }
      }
      else
      {
        *((_DWORD *)this + 15) = 1;
      }
    }
    else
    {
      *((_DWORD *)this + 14) = 1;
    }
  }
  std::wstring::~wstring(&v18);
  *(_QWORD *)((char *)v21 + *(int *)(v21[0] + 4LL)) = &std::basic_istringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v20 + *(int *)(v21[0] + 4LL) + 4) = *(_DWORD *)(v21[0] + 4LL) - 144;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(&v22);
  std::basic_istream<unsigned short>::~basic_istream<unsigned short,std::char_traits<unsigned short>>(v23);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v29);
}

```

## disassembly

```asm
0x180019168  mov     [rsp-8+arg_10], rbx
0x18001916d  push    rbp
0x18001916e  push    rsi
0x18001916f  push    rdi
0x180019170  push    r14
0x180019172  push    r15
0x180019174  lea     rbp, [rsp-70h]
0x180019179  sub     rsp, 170h
0x180019180  mov     rax, cs:__security_cookie
0x180019187  xor     rax, rsp
0x18001918a  mov     [rbp+90h+var_30], rax
0x18001918e  mov     rsi, rcx
0x180019191  xor     r15d, r15d
0x180019194  mov     [rsp+190h+var_170], r15d
0x180019199  xorps   xmm0, xmm0
0x18001919c  movups  xmmword ptr [rsp+190h+Src], xmm0
0x1800191a1  mov     [rsp+190h+var_158], r15
0x1800191a6  mov     [rsp+190h+var_150], r15
0x1800191ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800191af  inc     r8
0x1800191b2  cmp     [rdx+r8*2], r15w
0x1800191b7  jnz     short loc_1800191AF
0x1800191b9  lea     rcx, [rsp+190h+Src]
0x1800191be  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800191c3  nop
0x1800191c4  lea     rax, ??_8?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B@; const std::basic_istringstream<ushort>::`vbtable'
0x1800191cb  mov     [rsp+190h+var_120], rax
0x1800191d0  lea     rcx, [rbp+90h+var_90]
0x1800191d4  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x1800191da  nop
0x1800191db  mov     [rsp+190h+var_170], 1
0x1800191e3  xor     r9d, r9d
0x1800191e6  xor     r8d, r8d
0x1800191e9  lea     rdx, [rbp+90h+var_110]
0x1800191ed  lea     rcx, [rsp+190h+var_120]
0x1800191f2  call    cs:__imp_??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_istream<ushort>::basic_istream<ushort>(std::basic_streambuf<ushort> *,bool)
0x1800191f8  nop
0x1800191f9  mov     rax, [rsp+190h+var_120]
0x1800191fe  movsxd  rcx, dword ptr [rax+4]
0x180019202  lea     rdi, ??_7?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_istringstream<ushort>::`vftable'
0x180019209  mov     [rsp+rcx+190h+var_120], rdi
0x18001920e  mov     rax, [rsp+190h+var_120]
0x180019213  movsxd  rcx, dword ptr [rax+4]
0x180019217  lea     edx, [rcx-90h]
0x18001921d  mov     [rsp+rcx+190h+var_124], edx
0x180019221  lea     rax, [rbp+90h+var_110]
0x180019225  mov     [rsp+190h+var_148], rax
0x18001922a  lea     rcx, [rbp+90h+var_110]
0x18001922e  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x180019234  nop
0x180019235  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x18001923c  mov     [rbp+90h+var_110], rax
0x180019240  mov     rbx, [rsp+190h+var_158]
0x180019245  lea     r14, [rsp+190h+Src]
0x18001924a  cmp     [rsp+190h+var_150], 7
0x180019250  cmova   r14, [rsp+190h+Src]
0x180019256  cmp     rbx, 7FFFFFFFh
0x18001925d  jbe     short loc_180019266
0x18001925f  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180019265  int     3; Trap to Debugger
0x180019266  test    rbx, rbx
0x180019269  jz      loc_1800192F2
0x18001926f  add     rbx, rbx
0x180019272  jnz     short loc_180019279
0x180019274  mov     rdi, r15
0x180019277  jmp     short loc_1800192B7
0x180019279  cmp     rbx, 1000h
0x180019280  jb      short loc_1800192AC
0x180019282  lea     rcx, [rbx+27h]; Size
0x180019286  cmp     rcx, rbx
0x180019289  jbe     loc_180019463
0x18001928f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019294  test    rax, rax
0x180019297  jnz     short loc_18001929E
0x180019299  lea     ecx, [rax+5]
0x18001929c  int     29h; Win8: RtlFailFast(ecx)
0x18001929e  lea     rdi, [rax+27h]
0x1800192a2  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1800192a6  mov     [rdi-8], rax
0x1800192aa  jmp     short loc_1800192B7
0x1800192ac  mov     rcx, rbx; Size
0x1800192af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800192b4  mov     rdi, rax
0x1800192b7  mov     r8, rbx; Size
0x1800192ba  mov     rdx, r14; Src
0x1800192bd  mov     rcx, rdi; void *
0x1800192c0  call    memcpy_0
0x1800192c5  lea     rcx, [rbx+rdi]
0x1800192c9  mov     [rbp+90h+var_A8], rcx
0x1800192cd  mov     rcx, [rbp+90h+var_F8]
0x1800192d1  mov     [rcx], rdi
0x1800192d4  mov     rcx, [rbp+90h+var_D8]
0x1800192d8  mov     [rcx], rdi
0x1800192db  sar     rbx, 1
0x1800192de  mov     rax, [rbp+90h+var_C0]
0x1800192e2  mov     [rax], ebx
0x1800192e4  mov     eax, 3
0x1800192e9  lea     rdi, ??_7?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_istringstream<ushort>::`vftable'
0x1800192f0  jmp     short loc_1800192FB
0x1800192f2  mov     eax, 2
0x1800192f7  mov     [rbp+90h+var_A8], r15
0x1800192fb  mov     [rbp+90h+var_A0], eax
0x1800192fe  lea     rcx, [rsp+190h+Src]; void *
0x180019303  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019308  xorps   xmm0, xmm0
0x18001930b  movups  [rsp+190h+var_140], xmm0
0x180019310  mov     [rsp+190h+var_130], r15
0x180019315  mov     qword ptr [rsp+68h], 7
0x18001931e  mov     word ptr [rsp+190h+var_140], r15w
0x180019324  jmp     loc_1800193D0
0x180019329  lea     rdx, [rsp+190h+var_140]
0x18001932e  cmp     qword ptr [rsp+68h], 7
0x180019334  cmova   rdx, qword ptr [rsp+190h+var_140]
0x18001933a  lea     rcx, aPeriodic; "Periodic"
0x180019341  call    cs:__imp__o__wcsicmp
0x180019347  test    eax, eax
0x180019349  jnz     short loc_180019354
0x18001934b  mov     dword ptr [rsi+38h], 1
0x180019352  jmp     short loc_1800193D0
0x180019354  lea     rdx, [rsp+190h+var_140]
0x180019359  cmp     qword ptr [rsp+68h], 7
0x18001935f  cmova   rdx, qword ptr [rsp+190h+var_140]
0x180019365  lea     rcx, aInstall; "Install"
0x18001936c  call    cs:__imp__o__wcsicmp
0x180019372  test    eax, eax
0x180019374  jnz     short loc_18001937F
0x180019376  mov     dword ptr [rsi+3Ch], 1
0x18001937d  jmp     short loc_1800193D0
0x18001937f  lea     rdx, [rsp+190h+var_140]
0x180019384  cmp     qword ptr [rsp+68h], 7
0x18001938a  cmova   rdx, qword ptr [rsp+190h+var_140]
0x180019390  lea     rcx, aUninstall; "Uninstall"
0x180019397  call    cs:__imp__o__wcsicmp
0x18001939d  test    eax, eax
0x18001939f  jnz     short loc_1800193AA
0x1800193a1  mov     dword ptr [rsi+3Ch], 2
0x1800193a8  jmp     short loc_1800193D0
0x1800193aa  lea     rdx, [rsp+190h+var_140]
0x1800193af  cmp     qword ptr [rsp+68h], 7
0x1800193b5  cmova   rdx, qword ptr [rsp+190h+var_140]
0x1800193bb  lea     rcx, aOndemandnotoas; "OnDemandNoToast"
0x1800193c2  call    cs:__imp__o__wcsicmp
0x1800193c8  test    eax, eax
0x1800193ca  jnz     short loc_1800193D0
0x1800193cc  mov     byte ptr [rsi+40h], 1
0x1800193d0  lea     rdx, [rsp+190h+var_140]
0x1800193d5  lea     rcx, [rsp+190h+var_120]
0x1800193da  call    ??$?5GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator>><ushort>(std::basic_istream<ushort> &,std::wstring &)
0x1800193df  mov     rcx, [rax]
0x1800193e2  movsxd  rcx, dword ptr [rcx+4]
0x1800193e6  add     rcx, rax
0x1800193e9  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x1800193ef  test    al, al
0x1800193f1  jnz     loc_180019329
0x1800193f7  lea     rcx, [rsp+190h+var_140]; void *
0x1800193fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019401  nop
0x180019402  mov     rax, [rsp+190h+var_120]
0x180019407  movsxd  rcx, dword ptr [rax+4]
0x18001940b  mov     [rsp+rcx+190h+var_120], rdi
0x180019410  mov     rax, [rsp+190h+var_120]
0x180019415  movsxd  rcx, dword ptr [rax+4]
0x180019419  lea     edx, [rcx-90h]
0x18001941f  mov     [rsp+rcx+190h+var_124], edx
0x180019423  lea     rcx, [rbp+90h+var_110]
0x180019427  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x18001942c  lea     rcx, [rbp+90h+var_108]
0x180019430  call    cs:__imp_??1?$basic_istream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_istream<ushort>::~basic_istream<ushort,std::char_traits<ushort>>(void)
0x180019436  lea     rcx, [rbp+90h+var_90]
0x18001943a  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180019440  mov     rcx, [rbp+90h+var_30]
0x180019444  xor     rcx, rsp; StackCookie
0x180019447  call    __security_check_cookie
0x18001944c  mov     rbx, [rsp+190h+arg_10]
0x180019454  add     rsp, 170h
0x18001945b  pop     r15
0x18001945d  pop     r14
0x18001945f  pop     rdi
0x180019460  pop     rsi
0x180019461  pop     rbp
0x180019462  retn
0x180019463  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
