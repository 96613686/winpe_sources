# _lambda_e2bb78ea8b9906cda6c064936181aa51_::operator()

- ea: `0x18003dc2c`
- end: `0x18003df78`
- name: `_lambda_e2bb78ea8b9906cda6c064936181aa51_::operator()`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003e06c`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180022930`
- `0x180022dd8`
- `0x180029070`
- `0x18003bfac`
- `0x18003ccc0`
- `0x18003d484`
- `0x18003dc2c`
- `0x18003f9c4`
- `0x180051f98`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003dcba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003dcba`

## string_xrefs

- `0x18003dd2c`: `AssignedAccess_`
- `0x18003dea6`: `AssignedAccess_`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall lambda_e2bb78ea8b9906cda6c064936181aa51_::operator()(__int64 a1, _QWORD *a2)
{
  int v3; // r14d
  __int64 v4; // rsi
  _QWORD **v5; // r15
  _QWORD *v6; // rbx
  const WCHAR *v7; // rax
  LPWSTR FileNameW; // rax
  _WORD *v9; // r9
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  _QWORD **v13; // r15
  _QWORD *i; // rbx
  _WORD *v15; // r9
  unsigned __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rdx
  _QWORD **v21; // [rsp+28h] [rbp-D8h]
  _QWORD **v22; // [rsp+30h] [rbp-D0h]
  __int128 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  _BYTE v26[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[32]; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+C0h] [rbp-40h]
  _BYTE v30[32]; // [rsp+C8h] [rbp-38h] BYREF
  const wchar_t *v31; // [rsp+E8h] [rbp-18h]
  _BYTE v32[6]; // [rsp+11Ah] [rbp+1Ah] BYREF

  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v3 = 1;
  v4 = 1;
  v5 = *(_QWORD ***)(*(_QWORD *)a1 + 32LL);
  v22 = v5;
  v6 = *v5;
  while ( v6 != v5 )
  {
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 2);
    FileNameW = PathFindFileNameW(v7);
    std::wstring::wstring(v27, FileNameW);
    v9 = v32;
    v10 = v4;
    do
    {
      *--v9 = v10 % 0xA + 48;
      v10 /= 0xAu;
    }
    while ( v10 );
    std::wstring::wstring(&v23, v9, v32);
    std::operator+<unsigned short>(v26, L"AssignedAccess_", &v23);
    std::wstring::_Tidy_deallocate(&v23);
    std::wstring::wstring(v28, v27);
    v29 = 0x7FFFFFFF;
    std::wstring::wstring(v30, v26);
    v31 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\RestrictRun";
    v3 |= 0xEu;
    v12 = a2[1];
    if ( v12 == a2[2] )
    {
      std::vector<std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>>::_Emplace_reallocate<std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &>(
        a2,
        v12,
        (__int64)v28);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>>>::construct<std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>,std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &>(
        v11,
        v12,
        v28);
      a2[1] += 80LL;
    }
    ++v4;
    std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>::~tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>(v28);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate(v27);
    v6 = (_QWORD *)*v6;
    v5 = v22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTAllowUWPsThroughRestrictRun>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinIoTAllowUWPsThroughRestrictRun>::GetImpl'::`2'::impl) )
  {
    v13 = *(_QWORD ***)(*(_QWORD *)a1 + 96LL);
    v21 = v13;
    for ( i = *v13; i != v13; i = (_QWORD *)*i )
    {
      v23 = 0;
      v24 = 0;
      v25 = 7;
      LOWORD(v23) = 0;
      if ( (int)Windows::Internal::AssignedAccess::PackageManagerHelper::FindExeFromAumid(i + 2, &v23) >= 0 && v24 )
      {
        v15 = v32;
        v16 = v4;
        do
        {
          *--v15 = v16 % 0xA + 48;
          v16 /= 0xAu;
        }
        while ( v16 );
        std::wstring::wstring(v27, v15, v32);
        std::operator+<unsigned short>(v26, L"AssignedAccess_", v27);
        std::wstring::_Tidy_deallocate(v27);
        std::wstring::wstring(v28, &v23);
        v29 = 0x7FFFFFFF;
        std::wstring::wstring(v30, v26);
        v31 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\RestrictRun";
        v3 |= 0x70u;
        v18 = a2[1];
        if ( v18 == a2[2] )
        {
          std::vector<std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>>::_Emplace_reallocate<std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &>(
            a2,
            v18,
            (__int64)v28);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>>>::construct<std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>,std::tuple<unsigned short const *,std::wstring,enum Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &>(
            v17,
            v18,
            v28);
          a2[1] += 80LL;
        }
        ++v4;
        std::tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>::~tuple<std::wstring,enum Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>(v28);
        std::wstring::_Tidy_deallocate(v26);
        v13 = v21;
      }
      std::wstring::_Tidy_deallocate(&v23);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18003dc2c  mov     [rsp-8+arg_0], rbx
0x18003dc31  mov     [rsp-8+arg_10], rsi
0x18003dc36  push    rbp
0x18003dc37  push    rdi
0x18003dc38  push    r12
0x18003dc3a  push    r14
0x18003dc3c  push    r15
0x18003dc3e  lea     rbp, [rsp-30h]
0x18003dc43  sub     rsp, 130h
0x18003dc4a  mov     rax, cs:__security_cookie
0x18003dc51  xor     rax, rsp
0x18003dc54  mov     [rbp+50h+var_30], rax
0x18003dc58  mov     rdi, rdx
0x18003dc5b  mov     [rsp+150h+var_128], rcx
0x18003dc60  mov     [rsp+150h+var_118], rdx
0x18003dc65  mov     [rsp+150h+var_130], 0
0x18003dc6d  mov     qword ptr [rdx], 0
0x18003dc74  mov     qword ptr [rdx+8], 0
0x18003dc7c  mov     qword ptr [rdx+10h], 0
0x18003dc84  mov     eax, 1
0x18003dc89  mov     r14d, eax
0x18003dc8c  mov     [rsp+150h+var_130], eax
0x18003dc90  mov     esi, eax
0x18003dc92  mov     rax, [rcx]
0x18003dc95  mov     r15, [rax+20h]
0x18003dc99  mov     [rsp+150h+var_120], r15
0x18003dc9e  mov     rbx, [r15]
0x18003dca1  lea     r12d, [rsi+2Fh]
0x18003dca5  cmp     rbx, r15
0x18003dca8  jz      loc_18003DDCF
0x18003dcae  lea     rcx, [rbx+10h]
0x18003dcb2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dcb7  mov     rcx, rax; pszPath
0x18003dcba  call    cs:__imp_PathFindFileNameW
0x18003dcc0  mov     rdx, rax
0x18003dcc3  lea     rcx, [rbp+50h+var_D0]
0x18003dcc7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003dccc  nop
0x18003dccd  lea     r9, [rbp+50h+var_36]
0x18003dcd1  mov     r8, rsi
0x18003dcd4  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18003dcde  sub     r9, 2
0x18003dce2  mov     rax, r15
0x18003dce5  mul     r8
0x18003dce8  shr     rdx, 3
0x18003dcec  movzx   eax, dx
0x18003dcef  shl     ax, 2
0x18003dcf3  lea     ecx, [rax+rdx]
0x18003dcf6  add     cx, cx
0x18003dcf9  sub     r8w, cx
0x18003dcfd  add     r8w, r12w
0x18003dd01  mov     [r9], r8w
0x18003dd05  mov     r8, rdx
0x18003dd08  test    rdx, rdx
0x18003dd0b  jnz     short loc_18003DCDE
0x18003dd0d  lea     r8, [rbp+50h+var_36]
0x18003dd11  mov     rdx, r9
0x18003dd14  lea     rcx, [rsp+150h+var_110]
0x18003dd19  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18003dd1e  or      r14d, 6
0x18003dd22  mov     [rsp+150h+var_130], r14d
0x18003dd27  lea     r8, [rsp+150h+var_110]
0x18003dd2c  lea     rdx, aAssignedaccess_1; "AssignedAccess_"
0x18003dd33  lea     rcx, [rsp+150h+var_F0]
0x18003dd38  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18003dd3d  nop
0x18003dd3e  lea     rcx, [rsp+150h+var_110]
0x18003dd43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dd48  lea     rdx, [rbp+50h+var_D0]
0x18003dd4c  lea     rcx, [rbp+50h+var_B0]
0x18003dd50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003dd55  mov     [rbp+50h+var_90], 7FFFFFFFh
0x18003dd5c  lea     rdx, [rsp+150h+var_F0]
0x18003dd61  lea     rcx, [rbp+50h+var_88]
0x18003dd65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003dd6a  nop
0x18003dd6b  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003dd72  mov     [rbp+50h+var_68], rax
0x18003dd76  or      r14d, 8
0x18003dd7a  mov     [rsp+150h+var_130], r14d
0x18003dd7f  mov     rdx, [rdi+8]
0x18003dd83  lea     r8, [rbp+50h+var_B0]
0x18003dd87  cmp     rdx, [rdi+10h]
0x18003dd8b  jz      short loc_18003DD99
0x18003dd8d  call    ??$construct@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@@std@@@std@@SAXAEAV?$allocator@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@@1@QEAV?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>>>::construct<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>,std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &>(std::allocator<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>> &,std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> * const,std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &)
0x18003dd92  add     qword ptr [rdi+8], 50h ; 'P'
0x18003dd97  jmp     short loc_18003DDA1
0x18003dd99  mov     rcx, rdi
0x18003dd9c  call    ??$_Emplace_reallocate@AEBV?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@@?$vector@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@V?$allocator@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@@2@@std@@AEAAPEAV?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@1@QEAV21@AEBV21@@Z; std::vector<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>>::_Emplace_reallocate<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &>(std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> * const,std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &)
0x18003dda1  inc     rsi
0x18003dda4  lea     rcx, [rbp+50h+var_B0]
0x18003dda8  call    ??1?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@QEAA@XZ; std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>::~tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>(void)
0x18003ddad  nop
0x18003ddae  lea     rcx, [rsp+150h+var_F0]
0x18003ddb3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ddb8  nop
0x18003ddb9  lea     rcx, [rbp+50h+var_D0]
0x18003ddbd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ddc2  mov     rbx, [rbx]
0x18003ddc5  mov     r15, [rsp+150h+var_120]
0x18003ddca  jmp     loc_18003DCA5
0x18003ddcf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinIoTAllowUWPsThroughRestrictRun@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTAllowUWPsThroughRestrictRun@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTAllowUWPsThroughRestrictRun> `wil::Feature<__WilFeatureTraits_Feature_WinIoTAllowUWPsThroughRestrictRun>::GetImpl(void)'::`2'::impl
0x18003ddd6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTAllowUWPsThroughRestrictRun@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTAllowUWPsThroughRestrictRun>::__private_IsEnabled(void)
0x18003dddb  test    al, al
0x18003dddd  mov     r12, [rsp+150h+var_128]
0x18003dde2  jz      loc_18003DF4C
0x18003dde8  mov     rax, [r12]
0x18003ddec  mov     r15, [rax+60h]
0x18003ddf0  mov     [rsp+150h+var_128], r15
0x18003ddf5  mov     rbx, [r15]
0x18003ddf8  cmp     rbx, r15
0x18003ddfb  jz      loc_18003DF4C
0x18003de01  xorps   xmm0, xmm0
0x18003de04  movups  [rsp+150h+var_110], xmm0
0x18003de09  mov     [rsp+150h+var_100], 0
0x18003de12  mov     [rsp+150h+var_F8], 7
0x18003de1b  xor     eax, eax
0x18003de1d  mov     word ptr [rsp+150h+var_110], ax
0x18003de22  lea     rcx, [rbx+10h]
0x18003de26  lea     rdx, [rsp+150h+var_110]
0x18003de2b  call    ?FindExeFromAumid@PackageManagerHelper@AssignedAccess@Internal@Windows@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Windows::Internal::AssignedAccess::PackageManagerHelper::FindExeFromAumid(std::wstring const &,std::wstring &)
0x18003de30  test    eax, eax
0x18003de32  js      loc_18003DF3A
0x18003de38  cmp     [rsp+150h+var_100], 0
0x18003de3e  jz      loc_18003DF3A
0x18003de44  lea     r9, [rbp+50h+var_36]
0x18003de48  mov     r8, rsi
0x18003de4b  mov     r12d, 30h ; '0'
0x18003de51  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18003de5b  sub     r9, 2
0x18003de5f  mov     rax, r15
0x18003de62  mul     r8
0x18003de65  shr     rdx, 3
0x18003de69  movzx   eax, dx
0x18003de6c  shl     ax, 2
0x18003de70  lea     ecx, [rax+rdx]
0x18003de73  add     cx, cx
0x18003de76  sub     r8w, cx
0x18003de7a  add     r8w, r12w
0x18003de7e  mov     [r9], r8w
0x18003de82  mov     r8, rdx
0x18003de85  test    rdx, rdx
0x18003de88  jnz     short loc_18003DE5B
0x18003de8a  lea     r8, [rbp+50h+var_36]
0x18003de8e  mov     rdx, r9
0x18003de91  lea     rcx, [rbp+50h+var_D0]
0x18003de95  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18003de9a  or      r14d, r12d
0x18003de9d  mov     [rsp+150h+var_130], r14d
0x18003dea2  lea     r8, [rbp+50h+var_D0]
0x18003dea6  lea     rdx, aAssignedaccess_1; "AssignedAccess_"
0x18003dead  lea     rcx, [rsp+150h+var_F0]
0x18003deb2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18003deb7  nop
0x18003deb8  lea     rcx, [rbp+50h+var_D0]
0x18003debc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dec1  lea     rdx, [rsp+150h+var_110]
0x18003dec6  lea     rcx, [rbp+50h+var_B0]
0x18003deca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003decf  mov     [rbp+50h+var_90], 7FFFFFFFh
0x18003ded6  lea     rdx, [rsp+150h+var_F0]
0x18003dedb  lea     rcx, [rbp+50h+var_88]
0x18003dedf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003dee4  nop
0x18003dee5  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003deec  mov     [rbp+50h+var_68], rax
0x18003def0  or      r14d, 40h
0x18003def4  mov     [rsp+150h+var_130], r14d
0x18003def9  mov     rdx, [rdi+8]
0x18003defd  lea     r8, [rbp+50h+var_B0]
0x18003df01  cmp     rdx, [rdi+10h]
0x18003df05  jz      short loc_18003DF13
0x18003df07  call    ??$construct@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@@std@@@std@@SAXAEAV?$allocator@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@@1@QEAV?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>>>::construct<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>,std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &>(std::allocator<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>> &,std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> * const,std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &)
0x18003df0c  add     qword ptr [rdi+8], 50h ; 'P'
0x18003df11  jmp     short loc_18003DF1B
0x18003df13  mov     rcx, rdi
0x18003df16  call    ??$_Emplace_reallocate@AEBV?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@@?$vector@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@V?$allocator@V?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@std@@@2@@std@@AEAAPEAV?$tuple@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4DefinitionVersion@AssignedAccess@Internal@Windows@@V12@@1@QEAV21@AEBV21@@Z; std::vector<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring>>::_Emplace_reallocate<std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &>(std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> * const,std::tuple<ushort const *,std::wstring,Windows::Internal::AssignedAccess::DefinitionVersion,std::wstring> const &)
0x18003df1b  inc     rsi
0x18003df1e  lea     rcx, [rbp+50h+var_B0]
0x18003df22  call    ??1?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EtwWinEventLevel@AssignedAccess@Internal@Windows@@V12@@std@@QEAA@XZ; std::tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>::~tuple<std::wstring,Windows::Internal::AssignedAccess::EtwWinEventLevel,std::wstring>(void)
0x18003df27  nop
0x18003df28  lea     rcx, [rsp+150h+var_F0]
0x18003df2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003df32  nop
0x18003df33  mov     r15, [rsp+150h+var_128]
0x18003df38  jmp     short $+2
0x18003df3a  lea     rcx, [rsp+150h+var_110]
0x18003df3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003df44  mov     rbx, [rbx]
0x18003df47  jmp     loc_18003DDF8
0x18003df4c  mov     rax, rdi
0x18003df4f  mov     rcx, [rbp+50h+var_30]
0x18003df53  xor     rcx, rsp; StackCookie
0x18003df56  call    __security_check_cookie
0x18003df5b  lea     r11, [rsp+150h+var_20]
0x18003df63  mov     rbx, [r11+30h]
0x18003df67  mov     rsi, [r11+40h]
0x18003df6b  mov     rsp, r11
0x18003df6e  pop     r15
0x18003df70  pop     r14
0x18003df72  pop     r12
0x18003df74  pop     rdi
0x18003df75  pop     rbp
0x18003df76  retn
```
