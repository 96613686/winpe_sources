# PrintDeviceCapabilitiesOM::Parser::GenericParser::CreateValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValueType const &)

- ea: `0x18003e1f8`
- end: `0x18003e535`
- name: `?CreateValue@GenericParser@Parser@PrintDeviceCapabilitiesOM@@IEAA?AV?$shared_ptr@$$CBVPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@AEBW4PrintDeviceCapabilitiesValueType@3@@Z`
- size: `829`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x18003f8f0`

## callees

- `0x180002d70`
- `0x18003874c`
- `0x18003aef0`
- `0x18003afc0`
- `0x18003b104`
- `0x18003b188`
- `0x18003b21c`
- `0x18003b2b8`
- `0x18003b324`
- `0x18003b394`
- `0x18003e1f8`
- `0x18003e614`
- `0x180040d3c`
- `0x180041024`
- `0x1800421e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x18003e409`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x18003e409`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003e465`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003e465`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e3f1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e420`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e42f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e44d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e472`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e47d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e3f1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e420`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e42f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e44d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e472`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e47d`

## string_xrefs

- `0x18003e262`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003e4f0`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003e51a`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall PrintDeviceCapabilitiesOM::Parser::GenericParser::CreateValue(
        __int64 a1,
        _QWORD *a2,
        const wchar_t *a3,
        _DWORD *a4)
{
  _QWORD *v7; // rax
  std::_Ref_count_base *v8; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  const wchar_t *v17; // rcx
  _QWORD *v18; // rax
  const wchar_t *v19; // rcx
  __int64 v20; // rcx
  unsigned int v22; // [rsp+20h] [rbp-60h]
  __int128 v23; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v24[8]; // [rsp+48h] [rbp-38h] BYREF
  std::_Ref_count_base *v25; // [rsp+50h] [rbp-30h]
  _BYTE v26[8]; // [rsp+58h] [rbp-28h] BYREF
  std::_Ref_count_base *v27; // [rsp+60h] [rbp-20h]
  _BYTE v28[8]; // [rsp+68h] [rbp-18h] BYREF
  std::_Ref_count_base *v29; // [rsp+70h] [rbp-10h]
  double v30; // [rsp+B8h] [rbp+38h] BYREF

  switch ( *a4 )
  {
    case 0:
      v18 = (_QWORD *)std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,std::wstring const &>(
                        v28,
                        a3);
LABEL_36:
      *a2 = *v18;
      v20 = v18[1];
      v18[1] = 0;
      a2[1] = v20;
      *v18 = 0;
      goto LABEL_37;
    case 1:
      *(_DWORD *)_o__errno() = 0;
      if ( *((_QWORD *)a3 + 3) <= 7u )
        v19 = a3;
      else
        v19 = *(const wchar_t **)a3;
      LODWORD(v30) = _o__wtol(v19);
      if ( !LODWORD(v30) && (*(_DWORD *)_o__errno() == 34 || *(_DWORD *)_o__errno() == 22) )
      {
        LODWORD(v30) = 7;
        PrintDeviceCapabilitiesOM::Exception::Throw::Error(
          (unsigned int)&v30,
          (_DWORD)a3,
          (unsigned int)L"Not a valid integer",
          (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
          462);
      }
      v18 = (_QWORD *)std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,int &>(v28, &v30);
      goto LABEL_36;
    case 2:
      *(_DWORD *)_o__errno() = 0;
      if ( *((_QWORD *)a3 + 3) <= 7u )
        v17 = a3;
      else
        v17 = *(const wchar_t **)a3;
      v30 = _wtof(v17);
      if ( v30 == 0.0 && (*(_DWORD *)_o__errno() == 34 || *(_DWORD *)_o__errno() == 22) )
      {
        LODWORD(v30) = 7;
        PrintDeviceCapabilitiesOM::Exception::Throw::Error(
          (unsigned int)&v30,
          (_DWORD)a3,
          (unsigned int)L"Not a valid decimal",
          (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
          474);
      }
      v18 = (_QWORD *)std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,double &>(v28, &v30);
      goto LABEL_36;
    case 3:
      v14 = std::make_shared<std::wstring,std::wstring const &>(v24, a3);
      v23 = 0;
      v23 = *(_OWORD *)v14;
      *(_QWORD *)v14 = 0;
      *(_QWORD *)(v14 + 8) = 0;
      v15 = (_QWORD *)PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(a1, v26, &v23);
      v16 = (_QWORD *)std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,PrintDeviceCapabilitiesOM::QualifiedName const &>(
                        v28,
                        *v15);
      *a2 = *v16;
      a2[1] = v16[1];
      *v16 = 0;
      v16[1] = 0;
      if ( v29 )
        std::_Ref_count_base::_Decref(v29);
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
      v8 = v25;
      goto LABEL_38;
    case 4:
      v12 = std::make_shared<PrintDeviceCapabilitiesOM::ImageableAreaValue,std::wstring const &>(v28, a3);
      v30 = COERCE_DOUBLE(operator new(0x58u));
      v13 = std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue>(
              *(_QWORD *)&v30,
              v12);
      *a2 = v13 + 16;
      a2[1] = v13;
LABEL_37:
      v8 = v29;
      goto LABEL_38;
    case 5:
      LOBYTE(v30) = 1;
      v9 = std::make_shared<std::wstring,std::wstring const &>(v28, a3);
      v23 = 0;
      v23 = *(_OWORD *)v9;
      *(_QWORD *)v9 = 0;
      *(_QWORD *)(v9 + 8) = 0;
      v10 = (_QWORD *)PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(a1, v26, &v23);
      v11 = (_QWORD *)std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,PrintDeviceCapabilitiesOM::QualifiedName const &,bool>(
                        v24,
                        *v10,
                        &v30);
      *a2 = *v11;
      a2[1] = v11[1];
      *v11 = 0;
      v11[1] = 0;
      if ( v25 )
        std::_Ref_count_base::_Decref(v25);
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
      goto LABEL_37;
  }
  if ( *a4 != 6 )
  {
    PrintCore::ThrowIfError(
      (PrintCore *)0x80070057LL,
      "Value has unrecognized xsi:type",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x1F0,
      v22);
    *a2 = 0;
    a2[1] = 0;
    return a2;
  }
  v7 = (_QWORD *)std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,>(&v23);
  *a2 = *v7;
  a2[1] = v7[1];
  *v7 = 0;
  v7[1] = 0;
  v8 = (std::_Ref_count_base *)*((_QWORD *)&v23 + 1);
LABEL_38:
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  return a2;
}

```

## disassembly

```asm
0x18003e1f8  mov     [rsp-18h+arg_0], rbx
0x18003e1fd  mov     [rsp-18h+arg_8], rsi
0x18003e202  push    rbp
0x18003e203  push    rdi
0x18003e204  push    r14
0x18003e206  mov     rbp, rsp
0x18003e209  sub     rsp, 80h
0x18003e210  mov     rbx, r8
0x18003e213  mov     rdi, rdx
0x18003e216  mov     rsi, rcx
0x18003e219  xor     r14d, r14d
0x18003e21c  mov     r10d, [r9]
0x18003e21f  test    r10d, r10d
0x18003e222  jz      loc_18003E497
0x18003e228  sub     r10d, 1
0x18003e22c  jz      loc_18003E44D
0x18003e232  sub     r10d, 1
0x18003e236  jz      loc_18003E3F1
0x18003e23c  sub     r10d, 1
0x18003e240  jz      loc_18003E36D
0x18003e246  sub     r10d, 1
0x18003e24a  jz      loc_18003E335
0x18003e250  sub     r10d, 1
0x18003e254  jz      short loc_18003E2AD
0x18003e256  cmp     r10d, 1
0x18003e25a  jz      short loc_18003E286
0x18003e25c  mov     r9d, 1F0h; char *
0x18003e262  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003e269  lea     rdx, aValueHasUnreco; "Value has unrecognized xsi:type"
0x18003e270  mov     ecx, 80070057h; this
0x18003e275  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003e27a  mov     [rdi], r14
0x18003e27d  mov     [rdi+8], r14
0x18003e281  jmp     loc_18003E4C6
0x18003e286  lea     rcx, [rbp+var_48]
0x18003e28a  call    ??$make_shared@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@$$V@std@@YA?AV?$shared_ptr@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@@0@XZ; std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,>(void)
0x18003e28f  mov     rcx, [rax]
0x18003e292  mov     [rdi], rcx
0x18003e295  mov     rcx, [rax+8]
0x18003e299  mov     [rdi+8], rcx
0x18003e29d  mov     [rax], r14
0x18003e2a0  mov     [rax+8], r14
0x18003e2a4  mov     rcx, qword ptr [rbp+var_48+8]
0x18003e2a8  jmp     loc_18003E4BC
0x18003e2ad  mov     byte ptr [rbp+arg_18], 1
0x18003e2b1  mov     rdx, rbx
0x18003e2b4  lea     rcx, [rbp+var_18]
0x18003e2b8  call    ??$make_shared@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@std@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_shared<std::wstring,std::wstring const &>(std::wstring const &)
0x18003e2bd  nop
0x18003e2be  xorps   xmm0, xmm0
0x18003e2c1  movdqu  [rbp+var_48], xmm0
0x18003e2c6  mov     rcx, [rax]
0x18003e2c9  mov     qword ptr [rbp+var_48], rcx
0x18003e2cd  mov     rcx, [rax+8]
0x18003e2d1  mov     qword ptr [rbp+var_48+8], rcx
0x18003e2d5  mov     [rax], r14
0x18003e2d8  mov     [rax+8], r14
0x18003e2dc  lea     r8, [rbp+var_48]
0x18003e2e0  lea     rdx, [rbp+var_28]
0x18003e2e4  mov     rcx, rsi
0x18003e2e7  call    ?ToQualifiedName@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@V?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@5@@Z; PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(std::shared_ptr<std::wstring const>)
0x18003e2ec  nop
0x18003e2ed  lea     r8, [rbp+arg_18]
0x18003e2f1  mov     rdx, [rax]
0x18003e2f4  lea     rcx, [rbp+var_38]
0x18003e2f8  call    ??$make_shared@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@AEBVQualifiedName@2@_N@std@@YA?AV?$shared_ptr@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@@0@AEBVQualifiedName@PrintDeviceCapabilitiesOM@@$$QEA_N@Z; std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,PrintDeviceCapabilitiesOM::QualifiedName const &,bool>(PrintDeviceCapabilitiesOM::QualifiedName const &,bool &&)
0x18003e2fd  mov     rcx, [rax]
0x18003e300  mov     [rdi], rcx
0x18003e303  mov     rcx, [rax+8]
0x18003e307  mov     [rdi+8], rcx
0x18003e30b  mov     [rax], r14
0x18003e30e  mov     [rax+8], r14
0x18003e312  mov     rcx, [rbp+var_30]; this
0x18003e316  test    rcx, rcx
0x18003e319  jz      short loc_18003E321
0x18003e31b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e320  nop
0x18003e321  mov     rcx, [rbp+var_20]; this
0x18003e325  test    rcx, rcx
0x18003e328  jz      short loc_18003E330
0x18003e32a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e32f  nop
0x18003e330  jmp     loc_18003E4B8
0x18003e335  mov     rdx, rbx
0x18003e338  lea     rcx, [rbp+var_18]
0x18003e33c  call    ??$make_shared@VImageableAreaValue@PrintDeviceCapabilitiesOM@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@YA?AV?$shared_ptr@VImageableAreaValue@PrintDeviceCapabilitiesOM@@@0@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_shared<PrintDeviceCapabilitiesOM::ImageableAreaValue,std::wstring const &>(std::wstring const &)
0x18003e341  mov     rbx, rax
0x18003e344  mov     ecx, 58h ; 'X'; Size
0x18003e349  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e34e  mov     [rbp+arg_18], rax
0x18003e352  mov     rdx, rbx
0x18003e355  mov     rcx, rax
0x18003e358  call    ??$?0V?$shared_ptr@VImageableAreaValue@PrintDeviceCapabilitiesOM@@@std@@@?$_Ref_count_obj2@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@@std@@QEAA@$$QEAV?$shared_ptr@VImageableAreaValue@PrintDeviceCapabilitiesOM@@@1@@Z; std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue>(std::shared_ptr<PrintDeviceCapabilitiesOM::ImageableAreaValue> &&)
0x18003e35d  lea     rcx, [rax+10h]
0x18003e361  mov     [rdi], rcx
0x18003e364  mov     [rdi+8], rax
0x18003e368  jmp     loc_18003E4B8
0x18003e36d  mov     rdx, rbx
0x18003e370  lea     rcx, [rbp+var_38]
0x18003e374  call    ??$make_shared@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@std@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_shared<std::wstring,std::wstring const &>(std::wstring const &)
0x18003e379  nop
0x18003e37a  xorps   xmm0, xmm0
0x18003e37d  movdqu  [rbp+var_48], xmm0
0x18003e382  mov     rcx, [rax]
0x18003e385  mov     qword ptr [rbp+var_48], rcx
0x18003e389  mov     rcx, [rax+8]
0x18003e38d  mov     qword ptr [rbp+var_48+8], rcx
0x18003e391  mov     [rax], r14
0x18003e394  mov     [rax+8], r14
0x18003e398  lea     r8, [rbp+var_48]
0x18003e39c  lea     rdx, [rbp+var_28]
0x18003e3a0  mov     rcx, rsi
0x18003e3a3  call    ?ToQualifiedName@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@V?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@5@@Z; PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(std::shared_ptr<std::wstring const>)
0x18003e3a8  nop
0x18003e3a9  mov     rdx, [rax]
0x18003e3ac  lea     rcx, [rbp+var_18]
0x18003e3b0  call    ??$make_shared@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@AEBVQualifiedName@2@@std@@YA?AV?$shared_ptr@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@@0@AEBVQualifiedName@PrintDeviceCapabilitiesOM@@@Z; std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,PrintDeviceCapabilitiesOM::QualifiedName const &>(PrintDeviceCapabilitiesOM::QualifiedName const &)
0x18003e3b5  mov     rcx, [rax]
0x18003e3b8  mov     [rdi], rcx
0x18003e3bb  mov     rcx, [rax+8]
0x18003e3bf  mov     [rdi+8], rcx
0x18003e3c3  mov     [rax], r14
0x18003e3c6  mov     [rax+8], r14
0x18003e3ca  mov     rcx, [rbp+var_10]; this
0x18003e3ce  test    rcx, rcx
0x18003e3d1  jz      short loc_18003E3D9
0x18003e3d3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e3d8  nop
0x18003e3d9  mov     rcx, [rbp+var_20]; this
0x18003e3dd  test    rcx, rcx
0x18003e3e0  jz      short loc_18003E3E8
0x18003e3e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e3e7  nop
0x18003e3e8  mov     rcx, [rbp+var_30]
0x18003e3ec  jmp     loc_18003E4BC
0x18003e3f1  call    cs:__imp__o__errno
0x18003e3f7  mov     [rax], r14d
0x18003e3fa  cmp     qword ptr [rbx+18h], 7
0x18003e3ff  jbe     short loc_18003E406
0x18003e401  mov     rcx, [rbx]
0x18003e404  jmp     short loc_18003E409
0x18003e406  mov     rcx, rbx; String
0x18003e409  call    cs:__imp__wtof
0x18003e40f  movsd   [rbp+arg_18], xmm0
0x18003e414  ucomisd xmm0, cs:__real@0000000000000000
0x18003e41c  jp      short loc_18003E43E
0x18003e41e  jnz     short loc_18003E43E
0x18003e420  call    cs:__imp__o__errno
0x18003e426  cmp     dword ptr [rax], 22h ; '"'
0x18003e429  jz      loc_18003E50B
0x18003e42f  call    cs:__imp__o__errno
0x18003e435  cmp     dword ptr [rax], 16h
0x18003e438  jz      loc_18003E50B
0x18003e43e  lea     rdx, [rbp+arg_18]
0x18003e442  lea     rcx, [rbp+var_18]
0x18003e446  call    ??$make_shared@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@AEAN@std@@YA?AV?$shared_ptr@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@@0@AEAN@Z; std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,double &>(double &)
0x18003e44b  jmp     short loc_18003E4A3
0x18003e44d  call    cs:__imp__o__errno
0x18003e453  mov     [rax], r14d
0x18003e456  cmp     qword ptr [rbx+18h], 7
0x18003e45b  jbe     short loc_18003E462
0x18003e45d  mov     rcx, [rbx]
0x18003e460  jmp     short loc_18003E465
0x18003e462  mov     rcx, rbx
0x18003e465  call    cs:__imp__o__wtol
0x18003e46b  mov     dword ptr [rbp+arg_18], eax
0x18003e46e  test    eax, eax
0x18003e470  jnz     short loc_18003E488
0x18003e472  call    cs:__imp__o__errno
0x18003e478  cmp     dword ptr [rax], 22h ; '"'
0x18003e47b  jz      short loc_18003E4E1
0x18003e47d  call    cs:__imp__o__errno
0x18003e483  cmp     dword ptr [rax], 16h
0x18003e486  jz      short loc_18003E4E1
0x18003e488  lea     rdx, [rbp+arg_18]
0x18003e48c  lea     rcx, [rbp+var_18]
0x18003e490  call    ??$make_shared@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@AEAH@std@@YA?AV?$shared_ptr@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@@0@AEAH@Z; std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,int &>(int &)
0x18003e495  jmp     short loc_18003E4A3
0x18003e497  mov     rdx, rbx
0x18003e49a  lea     rcx, [rbp+var_18]
0x18003e49e  call    ??$make_shared@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@YA?AV?$shared_ptr@VPrintDeviceCapabilitiesValue@PrintDeviceCapabilitiesOM@@@0@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_shared<PrintDeviceCapabilitiesOM::PrintDeviceCapabilitiesValue,std::wstring const &>(std::wstring const &)
0x18003e4a3  mov     rcx, [rax]
0x18003e4a6  mov     [rdi], rcx
0x18003e4a9  mov     rcx, [rax+8]
0x18003e4ad  mov     [rax+8], r14
0x18003e4b1  mov     [rdi+8], rcx
0x18003e4b5  mov     [rax], r14
0x18003e4b8  mov     rcx, [rbp+var_10]; this
0x18003e4bc  test    rcx, rcx
0x18003e4bf  jz      short loc_18003E4C6
0x18003e4c1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e4c6  mov     rax, rdi
0x18003e4c9  lea     r11, [rsp+80h+var_s0]
0x18003e4d1  mov     rbx, [r11+20h]
0x18003e4d5  mov     rsi, [r11+28h]
0x18003e4d9  mov     rsp, r11
0x18003e4dc  pop     r14
0x18003e4de  pop     rdi
0x18003e4df  pop     rbp
0x18003e4e0  retn
0x18003e4e1  mov     dword ptr [rbp+arg_18], 7
0x18003e4e8  mov     [rsp+80h+var_60], 1CEh
0x18003e4f0  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003e4f7  lea     r8, aNotAValidInteg; "Not a valid integer"
0x18003e4fe  mov     rdx, rbx
0x18003e501  lea     rcx, [rbp+arg_18]
0x18003e505  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
0x18003e50b  mov     dword ptr [rbp+arg_18], 7
0x18003e512  mov     [rsp+80h+var_60], 1DAh
0x18003e51a  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003e521  lea     r8, aNotAValidDecim; "Not a valid decimal"
0x18003e528  mov     rdx, rbx
0x18003e52b  lea     rcx, [rbp+arg_18]
0x18003e52f  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
