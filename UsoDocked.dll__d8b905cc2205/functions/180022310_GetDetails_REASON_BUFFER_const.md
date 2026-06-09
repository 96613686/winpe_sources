# GetDetails(_REASON_BUFFER const *)

- ea: `0x180022310`
- end: `0x1800225af`
- name: `?GetDetails@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_REASON_BUFFER@@@Z`
- size: `671`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180022198`
- `0x180023790`

## callees

- `0x180007660`
- `0x180008560`
- `0x18001ee04`
- `0x180020b58`
- `0x18002127c`
- `0x18002178c`
- `0x180021a34`
- `0x180022310`
- `0x1800239c4`
- `0x180024030`
- `0x180071010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180022582`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180022582`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x180022413`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180022578`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180022578`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800223e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800223e3`

## string_xrefs

- `0x1800224dd`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int128 *__fastcall GetDetails(__int128 *a1, __int64 a2, __int64 a3)
{
  _WORD *v5; // r9
  unsigned __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rax
  LPWSTR FileNameW; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  _WORD *v13; // rsi
  int v14; // r14d
  __int64 v15; // rax
  __int64 v16; // rdx
  _WORD *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  __int128 v21; // [rsp+28h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+38h] [rbp-C8h]
  __int128 *v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v26[120]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[104]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v23 = a1;
  *a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 7;
  *(_WORD *)a1 = 0;
  if ( (*(_BYTE *)a2 & 1) != 0 )
  {
    v5 = (_WORD *)(a2 + *(_QWORD *)(a2 + 8));
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    if ( v6 > 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1, v6, a3, v5);
    }
    else
    {
      *((_QWORD *)a1 + 2) = v6;
      v7 = 2 * v6;
      memmove_0(a1, v5, 2 * v6);
      *(_WORD *)((char *)a1 + v7) = 0;
    }
    return a1;
  }
  if ( (*(_BYTE *)a2 & 2) == 0 )
    return a1;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v24);
  v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v24, L"Module:");
  v9 = *(_QWORD *)(a2 + 8);
  if ( v9 )
    FileNameW = PathFindFileNameW((LPCWSTR)(v9 + a2));
  else
    FileNameW = L"??";
  v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, FileNameW);
  v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"-StringID:");
  ((void (__fastcall *)(__int64, _QWORD))std::basic_ostream<unsigned short>::operator<<)(
    v12,
    *(unsigned __int16 *)(a2 + 16));
  if ( !*(_DWORD *)(a2 + 20) )
    goto LABEL_25;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v24, L"-Parameters:");
  v13 = (_WORD *)(a2 + *(_QWORD *)(a2 + 24));
  v14 = 0;
  if ( !*(_DWORD *)(a2 + 20) )
    goto LABEL_25;
  while ( 1 )
  {
    v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v24, v13);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, L",");
    if ( !v13 )
    {
      v19 = 2147942487LL;
LABEL_20:
      v18 = 0;
      goto LABEL_21;
    }
    v16 = 260;
    v17 = v13;
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v16;
    }
    while ( v16 );
    v18 = (260 - v16) & -(__int64)(v16 != 0);
    v19 = v16 == 0 ? 0x80070057 : 0;
    if ( !v16 )
      goto LABEL_20;
LABEL_21:
    if ( (int)v19 < 0 )
      break;
    if ( (unsigned int)++v14 >= *(_DWORD *)(a2 + 20) )
      goto LABEL_25;
    v13 += v18 + 1;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x148,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
    (const char *)v19,
    1);
LABEL_25:
  std::basic_stringbuf<unsigned short>::str(v25, &v21);
  if ( a1 != &v21 )
  {
    std::wstring::_Tidy_deallocate(a1);
    *a1 = v21;
    a1[1] = (__int128)si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v21) = 0;
  }
  std::wstring::_Tidy_deallocate(&v21);
  *(_QWORD *)&v25[*(int *)(v24 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v23 + *(int *)(v24 + 4) + 4) = *(_DWORD *)(v24 + 4) - 136;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v25);
  std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v26);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v27);
  return a1;
}

```

## disassembly

```asm
0x180022310  mov     [rsp-8+arg_10], rbx
0x180022315  push    rbp
0x180022316  push    rsi
0x180022317  push    rdi
0x180022318  push    r14
0x18002231a  push    r15
0x18002231c  lea     rbp, [rsp-50h]
0x180022321  sub     rsp, 150h
0x180022328  mov     rax, cs:__security_cookie
0x18002232f  xor     rax, rsp
0x180022332  mov     [rbp+70h+var_30], rax
0x180022336  mov     rbx, rdx
0x180022339  mov     rdi, rcx
0x18002233c  mov     [rsp+170h+var_128], rcx
0x180022341  xor     r15d, r15d
0x180022344  mov     [rsp+170h+var_150], r15d
0x180022349  xorps   xmm0, xmm0
0x18002234c  movups  xmmword ptr [rcx], xmm0
0x18002234f  mov     [rcx+10h], r15
0x180022353  mov     qword ptr [rcx+18h], 7
0x18002235b  mov     [rcx], r15w
0x18002235f  mov     [rsp+170h+var_150], 1; int
0x180022367  test    byte ptr [rdx], 1
0x18002236a  jz      short loc_1800223AE
0x18002236c  mov     r9, [rdx+8]
0x180022370  add     r9, rdx
0x180022373  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180022377  inc     rdx
0x18002237a  cmp     [r9+rdx*2], r15w
0x18002237f  jnz     short loc_180022377
0x180022381  cmp     rdx, 7
0x180022385  ja      short loc_1800223A4
0x180022387  mov     [rcx+10h], rdx
0x18002238b  lea     rbx, [rdx+rdx]
0x18002238f  mov     r8, rbx; Size
0x180022392  mov     rdx, r9; Src
0x180022395  call    memmove_0
0x18002239a  mov     [rbx+rdi], r15w
0x18002239f  jmp     loc_180022588
0x1800223a4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800223a9  jmp     loc_180022588
0x1800223ae  test    byte ptr [rdx], 2
0x1800223b1  jz      loc_180022588
0x1800223b7  lea     rcx, [rsp+170h+var_120]
0x1800223bc  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800223c1  nop
0x1800223c2  lea     rdx, aModule; "Module:"
0x1800223c9  lea     rcx, [rsp+170h+var_120]
0x1800223ce  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800223d3  mov     rsi, rax
0x1800223d6  mov     rax, [rbx+8]
0x1800223da  test    rax, rax
0x1800223dd  jz      short loc_1800223EB
0x1800223df  lea     rcx, [rax+rbx]; pszPath
0x1800223e3  call    cs:__imp_PathFindFileNameW
0x1800223e9  jmp     short loc_1800223F2
0x1800223eb  lea     rax, asc_180079C20; "??"
0x1800223f2  mov     rdx, rax
0x1800223f5  mov     rcx, rsi
0x1800223f8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800223fd  mov     rcx, rax
0x180022400  lea     rdx, aStringid; "-StringID:"
0x180022407  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002240c  movzx   edx, word ptr [rbx+10h]
0x180022410  mov     rcx, rax
0x180022413  mov     rax, cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18002241a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002241f  cmp     [rbx+14h], r15d
0x180022423  jbe     loc_1800224EE
0x180022429  lea     rdx, aParameters; "-Parameters:"
0x180022430  lea     rcx, [rsp+170h+var_120]
0x180022435  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002243a  mov     rsi, [rbx+18h]
0x18002243e  add     rsi, rbx
0x180022441  mov     r14d, r15d
0x180022444  cmp     [rbx+14h], r15d
0x180022448  jbe     loc_1800224EE
0x18002244e  mov     rdx, rsi
0x180022451  lea     rcx, [rsp+170h+var_120]
0x180022456  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002245b  mov     rcx, rax
0x18002245e  lea     rdx, asc_180079E2C; ","
0x180022465  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002246a  test    rsi, rsi
0x18002246d  jz      short loc_1800224B5
0x18002246f  mov     edx, 104h
0x180022474  mov     rax, rsi
0x180022477  cmp     [rax], r15w
0x18002247b  jz      short loc_180022487
0x18002247d  add     rax, 2
0x180022481  sub     rdx, 1
0x180022485  jnz     short loc_180022477
0x180022487  mov     rax, rdx
0x18002248a  mov     ecx, 104h
0x18002248f  sub     rcx, rdx
0x180022492  neg     rax
0x180022495  sbb     r8, r8
0x180022498  and     r8, rcx
0x18002249b  mov     rax, rdx
0x18002249e  neg     rax
0x1800224a1  sbb     r9d, r9d
0x1800224a4  not     r9d
0x1800224a7  and     r9d, 80070057h
0x1800224ae  test    rdx, rdx
0x1800224b1  jz      short loc_1800224BB
0x1800224b3  jmp     short loc_1800224BE
0x1800224b5  mov     r9d, 80070057h; char *
0x1800224bb  mov     r8, r15
0x1800224be  mov     rcx, [rbp+78h]; this
0x1800224c2  test    r9d, r9d
0x1800224c5  js      short loc_1800224DD
0x1800224c7  inc     r14d
0x1800224ca  cmp     r14d, [rbx+14h]
0x1800224ce  jnb     short loc_1800224EE
0x1800224d0  lea     rsi, [rsi+r8*2]
0x1800224d4  add     rsi, 2
0x1800224d8  jmp     loc_18002244E
0x1800224dd  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800224e4  mov     edx, 148h; void *
0x1800224e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800224ee  lea     rdx, [rsp+170h+var_148]
0x1800224f3  lea     rcx, [rsp+170h+var_118]
0x1800224f8  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800224fd  lea     rax, [rsp+170h+var_148]
0x180022502  cmp     rdi, rax
0x180022505  jz      short loc_180022534
0x180022507  mov     rcx, rdi
0x18002250a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002250f  movups  xmm0, [rsp+170h+var_148]
0x180022514  movups  xmmword ptr [rdi], xmm0
0x180022517  movups  xmm1, [rsp+170h+var_138]
0x18002251c  movups  xmmword ptr [rdi+10h], xmm1
0x180022520  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180022528  movdqu  [rsp+170h+var_138], xmm0
0x18002252e  mov     word ptr [rsp+170h+var_148], r15w
0x180022534  lea     rcx, [rsp+170h+var_148]
0x180022539  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002253e  nop
0x18002253f  mov     rax, [rsp+170h+var_120]
0x180022544  movsxd  rcx, dword ptr [rax+4]
0x180022548  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x18002254f  mov     [rsp+rcx+170h+var_120], rax
0x180022554  mov     rcx, [rsp+170h+var_120]
0x180022559  movsxd  rdx, dword ptr [rcx+4]
0x18002255d  lea     r8d, [rdx-88h]
0x180022564  mov     dword ptr [rsp+rdx+170h+var_128+4], r8d
0x180022569  lea     rcx, [rsp+170h+var_118]
0x18002256e  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x180022573  lea     rcx, [rsp+170h+var_110]
0x180022578  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x18002257e  lea     rcx, [rbp+70h+var_98]
0x180022582  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180022588  mov     rax, rdi
0x18002258b  mov     rcx, [rbp+70h+var_30]
0x18002258f  xor     rcx, rsp; StackCookie
0x180022592  call    __security_check_cookie
0x180022597  mov     rbx, [rsp+170h+arg_10]
0x18002259f  add     rsp, 150h
0x1800225a6  pop     r15
0x1800225a8  pop     r14
0x1800225aa  pop     rdi
0x1800225ab  pop     rsi
0x1800225ac  pop     rbp
0x1800225ad  retn
```
