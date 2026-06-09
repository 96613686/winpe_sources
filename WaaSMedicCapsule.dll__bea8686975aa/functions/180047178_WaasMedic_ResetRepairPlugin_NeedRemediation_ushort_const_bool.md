# WaasMedic::ResetRepairPlugin::NeedRemediation(ushort const *,bool *)

- ea: `0x180047178`
- end: `0x180047574`
- name: `?NeedRemediation@ResetRepairPlugin@WaasMedic@@AEAAJPEBGPEA_N@Z`
- size: `1020`
- prototype: `__int64 __fastcall(WaasMedic::ResetRepairPlugin *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180045370`
- `0x180047580`

## callees

- `0x180003bb0`
- `0x180007590`
- `0x18000ab8c`
- `0x180017a64`
- `0x1800231d0`
- `0x18002543c`
- `0x18002acd8`
- `0x180045d60`
- `0x180046c94`
- `0x180047178`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800474b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800474b7`

## string_xrefs

- `0x1800471cb`: `ResetRepairPlugin: NeedRemediation start`
- `0x18004726e`: `\ResetConfig.xml`
- `0x1800473a2`: `Failed to load xml [%s]. Err=0x%08x`
- `0x180047362`: `Config XML and target cmd file exist`
- `0x180047440`: `Failed to check phase [%s] from config file. Err=0x%08x`
- `0x1800474c1`: `ResetConfig.xml points to target CMD file for Reset End`
- `0x18004750f`: `ResetRepairPlugin: Need remediation [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WaasMedic::ResetRepairPlugin::NeedRemediation(
        WaasMedic::ResetRepairPlugin *this,
        const unsigned __int16 *a2,
        bool *a3)
{
  __int64 v6; // rax
  __int64 v7; // xmm6_8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int128 *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  __int128 *v13; // r9
  __int64 v14; // rax
  unsigned __int16 **v15; // rax
  struct WaasMedic::XmlDocument *v16; // rax
  const unsigned __int16 *v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  unsigned __int16 **v20; // r8
  __int64 v21; // rcx
  struct WaasMedic::XmlDocument *v22; // rbx
  int CommandForPhase; // eax
  unsigned int v24; // esi
  __int64 v25; // rcx
  __int128 *p_Src; // rcx
  __int64 v27; // rcx
  const wchar_t *v28; // r8
  unsigned __int16 v29; // [rsp+48h] [rbp-79h] BYREF
  struct WaasMedic::XmlDocument *v30; // [rsp+50h] [rbp-71h] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-69h]
  __int128 Src; // [rsp+60h] [rbp-61h] BYREF
  __m128i si128; // [rsp+70h] [rbp-51h]
  unsigned __int16 *v34[3]; // [rsp+80h] [rbp-41h] BYREF
  unsigned __int64 v35; // [rsp+98h] [rbp-29h]
  __int128 v36; // [rsp+A0h] [rbp-21h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-11h]
  __int128 v38; // [rsp+C0h] [rbp-1h] BYREF
  __int128 v39; // [rsp+D0h] [rbp+Fh]

  if ( !a3 )
  {
    LogLevelW(2u, L"pfNeedRemediation cannot be null");
    return 2147942487LL;
  }
  LogLevelW(5u, L"ResetRepairPlugin: NeedRemediation start");
  *a3 = 1;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(Src) = *a2;
  v6 = std::wstring::append(&Src, L":\\Recovery\\OEM");
  v38 = *(_OWORD *)v6;
  v39 = *(_OWORD *)(v6 + 16);
  v7 = v39;
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 7;
  *(_WORD *)v6 = 0;
  std::wstring::~wstring(&Src);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v7) < 0x10 )
    std::_Xlen_string();
  v10 = &v38;
  if ( *((_QWORD *)&v39 + 1) > 7u )
    v10 = (__int128 *)v38;
  std::wstring::wstring(v34, v8, v9, v10, v7, L"\\ResetConfig.xml", 16);
  if ( 0x7FFFFFFFFFFFFFFELL == (_QWORD)v39 )
    std::_Xlen_string();
  v13 = &v38;
  if ( *((_QWORD *)&v39 + 1) > 7u )
    v13 = (__int128 *)v38;
  std::wstring::wstring(&Src, v11, v12, v13, v39, L"\\", 1);
  v14 = std::wstring::append(&Src, (void *)L"AfterImageApply_BDB0C1E8-6951-46C4-AB7F-C07B29F462FD.cmd");
  v36 = 0;
  v37 = 0u;
  v36 = *(_OWORD *)v14;
  v37 = *(_OWORD *)(v14 + 16);
  *(_QWORD *)(v14 + 16) = 0;
  *(_QWORD *)(v14 + 24) = 7;
  *(_WORD *)v14 = 0;
  std::wstring::~wstring(&Src);
  v15 = v34;
  if ( v35 > 7 )
    v15 = (unsigned __int16 **)v34[0];
  v30 = (struct WaasMedic::XmlDocument *)v15;
  v31 = v34[2];
  if ( (unsigned __int8)WaasMedic::FileExists(&v30) )
  {
    v16 = (struct WaasMedic::XmlDocument *)&v36;
    if ( *((_QWORD *)&v37 + 1) > 7u )
      v16 = (struct WaasMedic::XmlDocument *)v36;
    v30 = v16;
    v31 = (unsigned __int16 *)v37;
    if ( (unsigned __int8)WaasMedic::FileExists(&v30) )
    {
      LogLevelW(4u, L"Config XML and target cmd file exist");
      v30 = 0;
      v17 = (const unsigned __int16 *)v34;
      if ( v35 > 7 )
        v17 = v34[0];
      v18 = WaasMedic::XmlDocument::LoadFile(v17, &v30);
      v19 = v18;
      if ( v18 < 0 )
      {
        v20 = v34;
        if ( v35 > 7 )
          v20 = (unsigned __int16 **)v34[0];
        LogLevelW(2u, L"Failed to load xml [%s]. Err=0x%08x", v20, (unsigned int)v18);
        if ( v30 )
        {
          v21 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
        }
        std::wstring::~wstring(&v36);
        std::wstring::~wstring(v34);
        std::wstring::~wstring(&v38);
        return v19;
      }
      LOBYTE(v29) = 0;
      Src = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Src) = 0;
      v22 = v30;
      CommandForPhase = WaasMedic::GetCommandForPhase(
                          v30,
                          (struct WaasMedic::XmlDocument *)L"FactoryReset_AfterImageApply",
                          &v29);
      v24 = CommandForPhase;
      if ( CommandForPhase < 0 )
      {
        LogLevelW(
          2u,
          L"Failed to check phase [%s] from config file. Err=0x%08x",
          L"FactoryReset_AfterImageApply",
          (unsigned int)CommandForPhase);
        std::wstring::~wstring(&Src);
        if ( v22 )
        {
          v25 = *(_QWORD *)v22;
          if ( *(_QWORD *)v22 )
          {
            *(_QWORD *)v22 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
        }
        std::wstring::~wstring(&v36);
        std::wstring::~wstring(v34);
        std::wstring::~wstring(&v38);
        return v24;
      }
      if ( (_BYTE)v29 )
      {
        p_Src = &Src;
        if ( si128.m128i_i64[1] > 7uLL )
          p_Src = (__int128 *)Src;
        if ( !(unsigned int)_o__wcsicmp(p_Src, L"AfterImageApply_BDB0C1E8-6951-46C4-AB7F-C07B29F462FD.cmd") )
        {
          LogLevelW(5u, L"ResetConfig.xml points to target CMD file for Reset End");
          *a3 = 0;
        }
      }
      std::wstring::~wstring(&Src);
      if ( v22 )
      {
        v27 = *(_QWORD *)v22;
        if ( *(_QWORD *)v22 )
        {
          *(_QWORD *)v22 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
      }
    }
  }
  v28 = L"True";
  if ( !*a3 )
    v28 = L"False";
  LogLevelW(4u, L"ResetRepairPlugin: Need remediation [%s]", v28);
  std::wstring::~wstring(&v36);
  std::wstring::~wstring(v34);
  std::wstring::~wstring(&v38);
  return 0;
}

```

## disassembly

```asm
0x180047178  mov     rax, rsp
0x18004717b  mov     [rax+8], rbx
0x18004717f  push    rbp
0x180047180  push    rsi
0x180047181  push    rdi
0x180047182  push    r14
0x180047184  push    r15
0x180047186  lea     rbp, [rax-5Fh]
0x18004718a  sub     rsp, 0F0h
0x180047191  movaps  xmmword ptr [rax-38h], xmm6
0x180047195  mov     rax, cs:__security_cookie
0x18004719c  xor     rax, rsp
0x18004719f  mov     [rbp+57h+var_38], rax
0x1800471a3  mov     rdi, r8
0x1800471a6  mov     rbx, rdx
0x1800471a9  xor     r14d, r14d
0x1800471ac  test    r8, r8
0x1800471af  jnz     short loc_1800471CB
0x1800471b1  lea     rdx, aPfneedremediat; "pfNeedRemediation cannot be null"
0x1800471b8  lea     ecx, [r8+2]; unsigned __int8
0x1800471bc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800471c1  mov     eax, 80070057h
0x1800471c6  jmp     loc_180047540
0x1800471cb  lea     rdx, aResetrepairplu_8; "ResetRepairPlugin: NeedRemediation star"...
0x1800471d2  mov     ecx, 5; unsigned __int8
0x1800471d7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800471dc  mov     byte ptr [rdi], 1
0x1800471df  xorps   xmm0, xmm0
0x1800471e2  movups  [rbp+57h+Src], xmm0
0x1800471e6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000001
0x1800471ee  movdqu  [rbp+57h+var_A8], xmm1
0x1800471f3  movzx   eax, word ptr [rbx]
0x1800471f6  mov     word ptr [rbp+57h+Src], ax
0x1800471fa  mov     word ptr [rbp+57h+Src+2], r14w
0x1800471ff  lea     rdx, aRecoveryOem; ":\\Recovery\\OEM"
0x180047206  lea     rcx, [rbp+57h+Src]; Src
0x18004720a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004720f  movups  xmm0, xmmword ptr [rax]
0x180047212  movups  [rbp+57h+var_58], xmm0
0x180047216  movups  xmm6, xmmword ptr [rax+10h]
0x18004721a  movups  [rbp+57h+var_48], xmm6
0x18004721e  mov     [rax+10h], r14
0x180047222  mov     r15d, 7
0x180047228  mov     [rax+18h], r15
0x18004722c  mov     [rax], r14w
0x180047230  lea     rcx, [rbp+57h+Src]; void *
0x180047234  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047239  movq    rcx, xmm6
0x18004723e  mov     rbx, 7FFFFFFFFFFFFFFEh
0x180047248  mov     rax, rbx
0x18004724b  sub     rax, rcx
0x18004724e  cmp     rax, 10h
0x180047252  jb      loc_18004756E
0x180047258  lea     r9, [rbp+57h+var_58]
0x18004725c  cmp     qword ptr [rbp+57h+var_48+8], r15
0x180047260  cmova   r9, qword ptr [rbp+57h+var_58]
0x180047265  mov     [rsp+110h+var_E0], 10h
0x18004726e  lea     rax, aResetconfigXml_0; "\\ResetConfig.xml"
0x180047275  mov     [rsp+110h+var_E8], rax
0x18004727a  mov     [rsp+110h+var_F0], rcx
0x18004727f  lea     rcx, [rbp+57h+var_98]
0x180047283  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180047288  nop
0x180047289  mov     rax, qword ptr [rbp+57h+var_48]
0x18004728d  sub     rbx, rax
0x180047290  cmp     rbx, 1
0x180047294  jb      loc_180047568
0x18004729a  lea     r9, [rbp+57h+var_58]
0x18004729e  cmp     qword ptr [rbp+57h+var_48+8], r15
0x1800472a2  cmova   r9, qword ptr [rbp+57h+var_58]
0x1800472a7  mov     [rsp+110h+var_E0], 1
0x1800472b0  lea     rcx, asc_18006E878; "\\"
0x1800472b7  mov     [rsp+110h+var_E8], rcx
0x1800472bc  mov     [rsp+110h+var_F0], rax
0x1800472c1  lea     rcx, [rbp+57h+Src]
0x1800472c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800472ca  nop
0x1800472cb  lea     rdx, aAfterimageappl; "AfterImageApply_BDB0C1E8-6951-46C4-AB7F"...
0x1800472d2  lea     rcx, [rbp+57h+Src]; Src
0x1800472d6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800472db  xorps   xmm0, xmm0
0x1800472de  movups  [rbp+57h+var_78], xmm0
0x1800472e2  mov     qword ptr [rbp+57h+var_68], r14
0x1800472e6  mov     qword ptr [rbp+57h+var_68+8], r14
0x1800472ea  movups  xmm0, xmmword ptr [rax]
0x1800472ed  movups  [rbp+57h+var_78], xmm0
0x1800472f1  movups  xmm1, xmmword ptr [rax+10h]
0x1800472f5  movups  [rbp+57h+var_68], xmm1
0x1800472f9  mov     [rax+10h], r14
0x1800472fd  mov     [rax+18h], r15
0x180047301  mov     [rax], r14w
0x180047305  lea     rcx, [rbp+57h+Src]; void *
0x180047309  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004730e  lea     rax, [rbp+57h+var_98]
0x180047312  cmp     [rbp+57h+var_80], r15
0x180047316  cmova   rax, [rbp+57h+var_98]
0x18004731b  mov     [rbp+57h+var_C8], rax
0x18004731f  mov     rax, [rbp+57h+var_88]
0x180047323  mov     [rbp+57h+var_C0], rax
0x180047327  lea     rcx, [rbp+57h+var_C8]
0x18004732b  call    ?FileExists@WaasMedic@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; WaasMedic::FileExists(std::basic_string_view<ushort> const &)
0x180047330  test    al, al
0x180047332  jz      loc_1800474FA
0x180047338  lea     rax, [rbp+57h+var_78]
0x18004733c  cmp     qword ptr [rbp+57h+var_68+8], r15
0x180047340  cmova   rax, qword ptr [rbp+57h+var_78]
0x180047345  mov     [rbp+57h+var_C8], rax
0x180047349  mov     rax, qword ptr [rbp+57h+var_68]
0x18004734d  mov     [rbp+57h+var_C0], rax
0x180047351  lea     rcx, [rbp+57h+var_C8]
0x180047355  call    ?FileExists@WaasMedic@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; WaasMedic::FileExists(std::basic_string_view<ushort> const &)
0x18004735a  test    al, al
0x18004735c  jz      loc_1800474FA
0x180047362  lea     rdx, aConfigXmlAndTa; "Config XML and target cmd file exist"
0x180047369  lea     ecx, [r15-3]; unsigned __int8
0x18004736d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180047372  mov     [rbp+57h+var_C8], r14
0x180047376  lea     rcx, [rbp+57h+var_98]
0x18004737a  cmp     [rbp+57h+var_80], r15
0x18004737e  cmova   rcx, [rbp+57h+var_98]; unsigned __int16 *
0x180047383  lea     rdx, [rbp+57h+var_C8]; struct WaasMedic::XmlDocument **
0x180047387  call    ?LoadFile@XmlDocument@WaasMedic@@SAJPEBGPEAPEAV12@@Z; WaasMedic::XmlDocument::LoadFile(ushort const *,WaasMedic::XmlDocument * *)
0x18004738c  mov     ebx, eax
0x18004738e  test    eax, eax
0x180047390  jns     short loc_1800473F8
0x180047392  lea     r8, [rbp+57h+var_98]
0x180047396  cmp     [rbp+57h+var_80], r15
0x18004739a  cmova   r8, [rbp+57h+var_98]
0x18004739f  mov     r9d, eax
0x1800473a2  lea     rdx, aFailedToLoadXm; "Failed to load xml [%s]. Err=0x%08x"
0x1800473a9  lea     ecx, [r15-5]; unsigned __int8
0x1800473ad  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800473b2  nop
0x1800473b3  mov     rax, [rbp+57h+var_C8]
0x1800473b7  test    rax, rax
0x1800473ba  jz      short loc_1800473D4
0x1800473bc  mov     rcx, [rax]
0x1800473bf  test    rcx, rcx
0x1800473c2  jz      short loc_1800473D4
0x1800473c4  mov     [rax], r14
0x1800473c7  mov     rax, [rcx]
0x1800473ca  mov     rax, [rax+10h]
0x1800473ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473d3  nop
0x1800473d4  lea     rcx, [rbp+57h+var_78]; void *
0x1800473d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800473dd  nop
0x1800473de  lea     rcx, [rbp+57h+var_98]; void *
0x1800473e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800473e7  nop
0x1800473e8  lea     rcx, [rbp+57h+var_58]; void *
0x1800473ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800473f1  mov     eax, ebx
0x1800473f3  jmp     loc_180047540
0x1800473f8  mov     byte ptr [rbp+57h+var_D0], r14b
0x1800473fc  xorps   xmm0, xmm0
0x1800473ff  movups  [rbp+57h+Src], xmm0
0x180047403  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004740b  movdqu  [rbp+57h+var_A8], xmm1
0x180047410  mov     word ptr [rbp+57h+Src], r14w
0x180047415  lea     r9, [rbp+57h+Src]
0x180047419  lea     r8, [rbp+57h+var_D0]; unsigned __int16 *
0x18004741d  lea     rdx, aFactoryresetAf; "FactoryReset_AfterImageApply"
0x180047424  mov     rbx, [rbp+57h+var_C8]
0x180047428  mov     rcx, rbx; this
0x18004742b  call    ?GetCommandForPhase@WaasMedic@@YAJPEAVXmlDocument@1@PEBGAEA_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@33@Z; WaasMedic::GetCommandForPhase(WaasMedic::XmlDocument *,ushort const *,bool &,std::wstring *,std::wstring *,std::wstring *)
0x180047430  mov     esi, eax
0x180047432  test    eax, eax
0x180047434  jns     short loc_18004749D
0x180047436  mov     r9d, eax
0x180047439  lea     r8, aFactoryresetAf; "FactoryReset_AfterImageApply"
0x180047440  lea     rdx, aFailedToCheckP; "Failed to check phase [%s] from config "...
0x180047447  mov     ecx, 2; unsigned __int8
0x18004744c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180047451  nop
0x180047452  lea     rcx, [rbp+57h+Src]; void *
0x180047456  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004745b  nop
0x18004745c  test    rbx, rbx
0x18004745f  jz      short loc_180047479
0x180047461  mov     rcx, [rbx]
0x180047464  test    rcx, rcx
0x180047467  jz      short loc_180047479
0x180047469  mov     [rbx], r14
0x18004746c  mov     rax, [rcx]
0x18004746f  mov     rax, [rax+10h]
0x180047473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047478  nop
0x180047479  lea     rcx, [rbp+57h+var_78]; void *
0x18004747d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047482  nop
0x180047483  lea     rcx, [rbp+57h+var_98]; void *
0x180047487  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004748c  nop
0x18004748d  lea     rcx, [rbp+57h+var_58]; void *
0x180047491  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047496  mov     eax, esi
0x180047498  jmp     loc_180047540
0x18004749d  cmp     byte ptr [rbp+57h+var_D0], r14b
0x1800474a1  jz      short loc_1800474D3
0x1800474a3  lea     rcx, [rbp+57h+Src]
0x1800474a7  cmp     qword ptr [rbp+57h+var_A8+8], r15
0x1800474ab  cmova   rcx, qword ptr [rbp+57h+Src]
0x1800474b0  lea     rdx, aAfterimageappl; "AfterImageApply_BDB0C1E8-6951-46C4-AB7F"...
0x1800474b7  call    cs:__imp__o__wcsicmp
0x1800474bd  test    eax, eax
0x1800474bf  jnz     short loc_1800474D3
0x1800474c1  lea     rdx, aResetconfigXml; "ResetConfig.xml points to target CMD fi"...
0x1800474c8  lea     ecx, [rax+5]; unsigned __int8
0x1800474cb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800474d0  mov     [rdi], r14b
0x1800474d3  lea     rcx, [rbp+57h+Src]; void *
0x1800474d7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800474dc  nop
0x1800474dd  test    rbx, rbx
0x1800474e0  jz      short loc_1800474FA
0x1800474e2  mov     rcx, [rbx]
0x1800474e5  test    rcx, rcx
0x1800474e8  jz      short loc_1800474FA
0x1800474ea  mov     [rbx], r14
0x1800474ed  mov     rax, [rcx]
0x1800474f0  mov     rax, [rax+10h]
0x1800474f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474f9  nop
0x1800474fa  lea     rax, aFalse_2; "False"
0x180047501  lea     r8, aTrue_0; "True"
0x180047508  cmp     [rdi], r14b
0x18004750b  cmovz   r8, rax
0x18004750f  lea     rdx, aResetrepairplu_5; "ResetRepairPlugin: Need remediation [%s"...
0x180047516  mov     ecx, 4; unsigned __int8
0x18004751b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180047520  nop
0x180047521  lea     rcx, [rbp+57h+var_78]; void *
0x180047525  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004752a  nop
0x18004752b  lea     rcx, [rbp+57h+var_98]; void *
0x18004752f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047534  nop
0x180047535  lea     rcx, [rbp+57h+var_58]; void *
0x180047539  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004753e  xor     eax, eax
0x180047540  mov     rcx, [rbp+57h+var_38]
0x180047544  xor     rcx, rsp; StackCookie
0x180047547  call    __security_check_cookie
0x18004754c  lea     r11, [rsp+110h+var_20]
0x180047554  mov     rbx, [r11+30h]
0x180047558  movaps  xmm6, xmmword ptr [r11-10h]
0x18004755d  mov     rsp, r11
0x180047560  pop     r15
0x180047562  pop     r14
0x180047564  pop     rdi
0x180047565  pop     rsi
0x180047566  pop     rbp
0x180047567  retn
0x180047568  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18004756e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
