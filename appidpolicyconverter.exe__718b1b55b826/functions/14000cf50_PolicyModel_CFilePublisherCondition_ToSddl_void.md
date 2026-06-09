# PolicyModel::CFilePublisherCondition::ToSddl(void)

- ea: `0x14000cf50`
- end: `0x14000d6b3`
- name: `?ToSddl@CFilePublisherCondition@PolicyModel@@MEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1891`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x14000863c`
- `0x1400091c0`
- `0x14000997c`
- `0x1400099b4`
- `0x14000a094`
- `0x14000a0d4`
- `0x14000b4f8`
- `0x14000b5c4`
- `0x14000bee4`
- `0x14000c138`
- `0x14000c308`
- `0x14000c454`
- `0x14000c56c`
- `0x14000c6f0`
- `0x14000c938`
- `0x14000cf50`
- `0x14000f344`
- `0x14000f390`
- `0x14000ff5c`
- `0x1400100b8`
- `0x140010120`
- `0x1400101fc`
- `0x140013b10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d047`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d047`

## string_xrefs

- `0x14000d039`: `System\CurrentControlSet\Control\AppID\Configuration`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFilePublisherCondition::ToSddl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  char v6; // al
  _QWORD *v7; // rdx
  __int64 v8; // rax
  PolicyModel::CFileVersionRange *v9; // rdi
  const struct PolicyModel::CFileVersion *LowSection; // rax
  void ***MinFileVersion; // rcx
  char v12; // bl
  const struct PolicyModel::CFileVersion *HighSection; // rax
  void ***MaxFileVersion; // rcx
  char v15; // bl
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // rdx
  __int64 Operator; // rax
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  void **v25; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v26; // [rsp+58h] [rbp-A8h]
  __int16 v27; // [rsp+5Ah] [rbp-A6h]
  __int16 v28; // [rsp+5Ch] [rbp-A4h]
  __int16 v29; // [rsp+5Eh] [rbp-A2h]
  void **v30; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v31; // [rsp+68h] [rbp-98h]
  __int16 v32; // [rsp+6Ah] [rbp-96h]
  __int16 v33; // [rsp+6Ch] [rbp-94h]
  __int16 v34; // [rsp+6Eh] [rbp-92h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  _QWORD v36[4]; // [rsp+78h] [rbp-88h] BYREF
  void **v37; // [rsp+98h] [rbp-68h] BYREF
  __int16 v38; // [rsp+A0h] [rbp-60h]
  __int16 v39; // [rsp+A2h] [rbp-5Eh]
  __int16 v40; // [rsp+A4h] [rbp-5Ch]
  __int16 v41; // [rsp+A6h] [rbp-5Ah]
  _QWORD v42[4]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v43[4]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v44[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v45[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v46[4]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v47[4]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v48[4]; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v49[4]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v50[4]; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD v51[4]; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v52[4]; // [rsp+1F8h] [rbp+F8h] BYREF
  _QWORD v53[4]; // [rsp+218h] [rbp+118h] BYREF

  v35 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f3cd61ca77c6343f41027d72af25da0d_Traceguids);
  v44[3] = 7;
  v44[2] = 0;
  LOWORD(v44[0]) = 0;
  if ( (unsigned __int8)std::operator==<unsigned short>(a1 + 2, L"*") )
  {
    std::wstring::operator=((__int64)v44, (__int64)(a1 + 2));
  }
  else
  {
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\AppID\\Configuration",
            L"UsePublisherId",
            0x10u,
            0,
            &pvData,
            &pcbData)
      && pcbData == 4
      && pvData == 1 )
    {
      PolicyModel::CFilePublisherCondition::ConvertToPublisherId(v36, a1 + 2);
      v4 = PolicyModel::CSddlCompiler::EncodeExpression((__int64)&v37, v36, 0);
      std::wstring::operator=(v44, v4);
      std::wstring::_Tidy(&v37, 1, 0);
    }
    else
    {
      v5 = PolicyModel::CSddlCompiler::EncodeExpression((__int64)v36, a1 + 2, 0);
      std::wstring::operator=(v44, v5);
    }
    std::wstring::_Tidy(v36, 1, 0);
  }
  v45[3] = 7;
  v45[2] = 0;
  LOWORD(v45[0]) = 0;
  v6 = std::operator==<unsigned short>(a1 + 6, L"*");
  v7 = a1 + 6;
  if ( v6 )
  {
    std::wstring::operator=((__int64)v45, (__int64)v7);
  }
  else
  {
    v8 = PolicyModel::CSddlCompiler::EncodeExpression((__int64)v36, v7, 0);
    std::wstring::operator=(v45, v8);
    std::wstring::_Tidy(v36, 1, 0);
  }
  PolicyModel::CSddlCompiler::EncodeExpression((__int64)v53, a1 + 10, 1u);
  v9 = (PolicyModel::CFileVersionRange *)(a1 + 14);
  if ( PolicyModel::CFileVersionRange::GetLowSection(v9) )
  {
    LowSection = PolicyModel::CFileVersionRange::GetLowSection(v9);
    v37 = &PolicyModel::CFileVersion::`vftable';
    v38 = *((_WORD *)LowSection + 4);
    v39 = *((_WORD *)LowSection + 5);
    v40 = *((_WORD *)LowSection + 6);
    v41 = *((_WORD *)LowSection + 7);
    MinFileVersion = &v37;
    v12 = 1;
  }
  else
  {
    MinFileVersion = (void ***)PolicyModel::CFileVersion::GetMinFileVersion(v36);
    v12 = 2;
  }
  v30 = &PolicyModel::CFileVersion::`vftable';
  v31 = *((_WORD *)MinFileVersion + 4);
  v32 = *((_WORD *)MinFileVersion + 5);
  v33 = *((_WORD *)MinFileVersion + 6);
  v34 = *((_WORD *)MinFileVersion + 7);
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    PolicyModel::CFileVersion::~CFileVersion((PolicyModel::CFileVersion *)v36);
  }
  if ( (v12 & 1) != 0 )
  {
    v12 &= ~1u;
    PolicyModel::CFileVersion::~CFileVersion((PolicyModel::CFileVersion *)&v37);
  }
  PolicyModel::CFileVersion::ToSddl(&v30, v52);
  if ( PolicyModel::CFileVersionRange::GetHighSection(v9) )
  {
    HighSection = PolicyModel::CFileVersionRange::GetHighSection(v9);
    v37 = &PolicyModel::CFileVersion::`vftable';
    v38 = *((_WORD *)HighSection + 4);
    v39 = *((_WORD *)HighSection + 5);
    v40 = *((_WORD *)HighSection + 6);
    v41 = *((_WORD *)HighSection + 7);
    MaxFileVersion = &v37;
    v15 = v12 | 4;
  }
  else
  {
    MaxFileVersion = (void ***)PolicyModel::CFileVersion::GetMaxFileVersion(v36);
    v15 = v12 | 8;
  }
  v25 = &PolicyModel::CFileVersion::`vftable';
  v26 = *((_WORD *)MaxFileVersion + 4);
  v27 = *((_WORD *)MaxFileVersion + 5);
  v28 = *((_WORD *)MaxFileVersion + 6);
  v29 = *((_WORD *)MaxFileVersion + 7);
  if ( (v15 & 8) != 0 )
  {
    v15 &= ~8u;
    PolicyModel::CFileVersion::~CFileVersion((PolicyModel::CFileVersion *)v36);
  }
  if ( (v15 & 4) != 0 )
    PolicyModel::CFileVersion::~CFileVersion((PolicyModel::CFileVersion *)&v37);
  PolicyModel::CFileVersion::ToSddl(&v25, v51);
  v42[3] = 7;
  v42[2] = 0;
  LOWORD(v42[0]) = 0;
  std::wstring::append(v42, v44, 0, 0xFFFFFFFFFFFFFFFFuLL);
  v16 = std::char_traits<unsigned short>::length(L"\\");
  std::wstring::append(v42, L"\\", v16);
  std::wstring::append(v42, v45, 0, 0xFFFFFFFFFFFFFFFFuLL);
  v17 = std::char_traits<unsigned short>::length(L"\\");
  std::wstring::append(v42, L"\\", v17);
  std::wstring::append(v42, v53, 0, 0xFFFFFFFFFFFFFFFFuLL);
  Sharp::Util::StringHandler::ToUppercase<std::wstring>(v42);
  PolicyModel::CSddlCompiler::WrapWithQuotes(v42);
  std::wstring::wstring((__int64)v47, (__int64)v42);
  v18 = std::char_traits<unsigned short>::length(L",");
  std::wstring::append(v47, L",", v18);
  std::wstring::append(v47, v52, 0, 0xFFFFFFFFFFFFFFFFuLL);
  PolicyModel::CSddlCompiler::WrapWithCurlyBrackets(v47);
  std::wstring::wstring((__int64)v46, (__int64)v42);
  v19 = std::char_traits<unsigned short>::length(L",");
  std::wstring::append(v46, L",", v19);
  std::wstring::append(v46, v51, 0, 0xFFFFFFFFFFFFFFFFuLL);
  PolicyModel::CSddlCompiler::WrapWithCurlyBrackets(v46);
  std::wstring::wstring((__int64)v36);
  PolicyModel::CSddlCompiler::CreateOperator((__int64)v49, 5, (__int64)v36, (__int64)v47, 1);
  std::wstring::_Tidy(v36, 1, 0);
  std::wstring::wstring((__int64)v36);
  PolicyModel::CSddlCompiler::CreateOperator((__int64)v48, 7, (__int64)v36, (__int64)v46, 1);
  std::wstring::_Tidy(v36, 1, 0);
  v43[3] = 7;
  v43[2] = 0;
  LOWORD(v43[0]) = 0;
  if ( (PolicyModel::CFileVersionRange::GetLowSection(v9) || PolicyModel::CFileVersionRange::GetHighSection(v9))
    && (!PolicyModel::CFileVersionRange::GetLowSection(v9) || PolicyModel::CFileVersionRange::GetHighSection(v9)) )
  {
    if ( PolicyModel::CFileVersionRange::GetLowSection(v9) || !PolicyModel::CFileVersionRange::GetHighSection(v9) )
    {
      Operator = PolicyModel::CSddlCompiler::CreateOperator((__int64)v36, 2, (__int64)v49, (__int64)v48, 1);
      std::wstring::operator=(v43, Operator);
      std::wstring::_Tidy(v36, 1, 0);
      goto LABEL_39;
    }
    v20 = v48;
  }
  else
  {
    v20 = v49;
  }
  std::wstring::operator=((__int64)v43, (__int64)v20);
LABEL_39:
  std::wstring::wstring((__int64)v36);
  PolicyModel::CSddlCompiler::CreateOperator((__int64)v50, 1, (__int64)v36, 0);
  std::wstring::_Tidy(v36, 1, 0);
  PolicyModel::CSddlCompiler::CreateOperator(a2, 2, (__int64)v50, (__int64)v43, 1);
  std::wstring::_Tidy(v50, 1, 0);
  std::wstring::_Tidy(v43, 1, 0);
  std::wstring::_Tidy(v48, 1, 0);
  std::wstring::_Tidy(v49, 1, 0);
  std::wstring::_Tidy(v46, 1, 0);
  std::wstring::_Tidy(v47, 1, 0);
  std::wstring::_Tidy(v42, 1, 0);
  std::wstring::_Tidy(v51, 1, 0);
  PolicyModel::CFileVersion::~CFileVersion((PolicyModel::CFileVersion *)&v25);
  std::wstring::_Tidy(v52, 1, 0);
  PolicyModel::CFileVersion::~CFileVersion((PolicyModel::CFileVersion *)&v30);
  std::wstring::_Tidy(v53, 1, 0);
  std::wstring::_Tidy(v45, 1, 0);
  std::wstring::_Tidy(v44, 1, 0);
  return a2;
}

```

## disassembly

```asm
0x14000cf50  mov     [rsp-8+arg_10], rbx
0x14000cf55  mov     [rsp-8+arg_18], rsi
0x14000cf5a  push    rbp
0x14000cf5b  push    rdi
0x14000cf5c  push    r12
0x14000cf5e  push    r14
0x14000cf60  push    r15
0x14000cf62  lea     rbp, [rsp-140h]
0x14000cf6a  sub     rsp, 240h
0x14000cf71  mov     rax, cs:__security_cookie
0x14000cf78  xor     rax, rsp
0x14000cf7b  mov     [rbp+160h+var_28], rax
0x14000cf82  mov     rsi, rdx
0x14000cf85  mov     rdi, rcx
0x14000cf88  mov     [rsp+260h+var_1F0], rdx
0x14000cf8d  xor     r12d, r12d
0x14000cf90  mov     [rsp+260h+var_220], r12d
0x14000cf95  lea     rax, WPP_GLOBAL_Control
0x14000cf9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cfa3  cmp     rcx, rax
0x14000cfa6  jz      short loc_14000CFC3
0x14000cfa8  test    byte ptr [rcx+1Ch], 8
0x14000cfac  jz      short loc_14000CFC3
0x14000cfae  lea     edx, [r12+0Fh]
0x14000cfb3  lea     r8, WPP_f3cd61ca77c6343f41027d72af25da0d_Traceguids
0x14000cfba  mov     rcx, [rcx+10h]
0x14000cfbe  call    WPP_SF_
0x14000cfc3  mov     [rbp+160h+var_158], r12
0x14000cfc7  mov     [rbp+160h+var_150], r12
0x14000cfcb  mov     r14d, 7
0x14000cfd1  mov     [rbp+160h+var_150], r14
0x14000cfd5  mov     [rbp+160h+var_158], r12
0x14000cfd9  mov     [rbp+160h+var_168], r12w
0x14000cfde  lea     rbx, [rdi+10h]
0x14000cfe2  lea     rdx, asc_140018D18; "*"
0x14000cfe9  mov     rcx, rbx
0x14000cfec  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x14000cff1  test    al, al
0x14000cff3  jz      short loc_14000D006
0x14000cff5  mov     rdx, rbx
0x14000cff8  lea     rcx, [rbp+160h+var_168]
0x14000cffc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000d001  jmp     loc_14000D0CA
0x14000d006  mov     [rsp+260h+var_218], r12d
0x14000d00b  mov     [rsp+260h+var_21C], 4
0x14000d013  lea     rax, [rsp+260h+var_21C]
0x14000d018  mov     [rsp+260h+pcbData], rax; pcbData
0x14000d01d  lea     rax, [rsp+260h+var_218]
0x14000d022  mov     [rsp+260h+pvData], rax; pvData
0x14000d027  mov     [rsp+260h+pdwType], r12; pdwType
0x14000d02c  mov     r9d, 10h; dwFlags
0x14000d032  lea     r8, aUsepublisherid; "UsePublisherId"
0x14000d039  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\App"...
0x14000d040  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000d047  call    cs:__imp_RegGetValueW
0x14000d04d  test    eax, eax
0x14000d04f  jnz     short loc_14000D09D
0x14000d051  cmp     [rsp+260h+var_21C], 4
0x14000d056  jnz     short loc_14000D09D
0x14000d058  cmp     [rsp+260h+var_218], 1
0x14000d05d  jnz     short loc_14000D09D
0x14000d05f  mov     rdx, rbx
0x14000d062  lea     rcx, [rsp+260h+var_1E8]
0x14000d067  call    ?ConvertToPublisherId@CFilePublisherCondition@PolicyModel@@KA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; PolicyModel::CFilePublisherCondition::ConvertToPublisherId(std::wstring const &)
0x14000d06c  nop
0x14000d06d  xor     r8d, r8d
0x14000d070  lea     rdx, [rsp+260h+var_1E8]
0x14000d075  lea     rcx, [rbp+160h+var_1C8]
0x14000d079  call    ?EncodeExpression@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@_N@Z; PolicyModel::CSddlCompiler::EncodeExpression(std::wstring const &,bool)
0x14000d07e  nop
0x14000d07f  mov     rdx, rax
0x14000d082  lea     rcx, [rbp+160h+var_168]
0x14000d086  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000d08b  nop
0x14000d08c  xor     r8d, r8d
0x14000d08f  mov     dl, 1
0x14000d091  lea     rcx, [rbp+160h+var_1C8]
0x14000d095  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d09a  nop
0x14000d09b  jmp     short loc_14000D0BB
0x14000d09d  xor     r8d, r8d
0x14000d0a0  mov     rdx, rbx
0x14000d0a3  lea     rcx, [rsp+260h+var_1E8]
0x14000d0a8  call    ?EncodeExpression@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@_N@Z; PolicyModel::CSddlCompiler::EncodeExpression(std::wstring const &,bool)
0x14000d0ad  nop
0x14000d0ae  mov     rdx, rax
0x14000d0b1  lea     rcx, [rbp+160h+var_168]
0x14000d0b5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000d0ba  nop
0x14000d0bb  xor     r8d, r8d
0x14000d0be  mov     dl, 1
0x14000d0c0  lea     rcx, [rsp+260h+var_1E8]
0x14000d0c5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d0ca  mov     [rbp+160h+var_138], r12
0x14000d0ce  mov     [rbp+160h+var_130], r12
0x14000d0d2  mov     [rbp+160h+var_130], r14
0x14000d0d6  mov     [rbp+160h+var_138], r12
0x14000d0da  mov     [rbp+160h+var_148], r12w
0x14000d0df  lea     rbx, [rdi+30h]
0x14000d0e3  lea     rdx, asc_140018D18; "*"
0x14000d0ea  mov     rcx, rbx
0x14000d0ed  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x14000d0f2  mov     rdx, rbx
0x14000d0f5  test    al, al
0x14000d0f7  jz      short loc_14000D104
0x14000d0f9  lea     rcx, [rbp+160h+var_148]
0x14000d0fd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000d102  jmp     short loc_14000D12E
0x14000d104  xor     r8d, r8d
0x14000d107  lea     rcx, [rsp+260h+var_1E8]
0x14000d10c  call    ?EncodeExpression@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@_N@Z; PolicyModel::CSddlCompiler::EncodeExpression(std::wstring const &,bool)
0x14000d111  nop
0x14000d112  mov     rdx, rax
0x14000d115  lea     rcx, [rbp+160h+var_148]
0x14000d119  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000d11e  nop
0x14000d11f  xor     r8d, r8d
0x14000d122  mov     dl, 1
0x14000d124  lea     rcx, [rsp+260h+var_1E8]
0x14000d129  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d12e  lea     rdx, [rdi+50h]
0x14000d132  mov     r8b, 1
0x14000d135  lea     rcx, [rbp+160h+var_48]
0x14000d13c  call    ?EncodeExpression@CSddlCompiler@PolicyModel@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@_N@Z; PolicyModel::CSddlCompiler::EncodeExpression(std::wstring const &,bool)
0x14000d141  nop
0x14000d142  add     rdi, 70h ; 'p'
0x14000d146  mov     rcx, rdi; this
0x14000d149  call    ?GetLowSection@CFileVersionRange@PolicyModel@@QEBAPEBVCFileVersion@2@XZ; PolicyModel::CFileVersionRange::GetLowSection(void)
0x14000d14e  lea     r14, ??_7CPolicyElement@PolicyModel@@6B@; const PolicyModel::CPolicyElement::`vftable'
0x14000d155  lea     r15, ??_7CFileVersion@PolicyModel@@6B@; const PolicyModel::CFileVersion::`vftable'
0x14000d15c  test    rax, rax
0x14000d15f  jz      short loc_14000D19F
0x14000d161  mov     rcx, rdi; this
0x14000d164  call    ?GetLowSection@CFileVersionRange@PolicyModel@@QEBAPEBVCFileVersion@2@XZ; PolicyModel::CFileVersionRange::GetLowSection(void)
0x14000d169  mov     rcx, rax
0x14000d16c  mov     [rbp+160h+var_1C8], r14
0x14000d170  mov     [rbp+160h+var_1C8], r15
0x14000d174  movzx   eax, word ptr [rax+8]
0x14000d178  mov     [rbp+160h+var_1C0], ax
0x14000d17c  movzx   eax, word ptr [rcx+0Ah]
0x14000d180  mov     [rbp+160h+var_1BE], ax
0x14000d184  movzx   eax, word ptr [rcx+0Ch]
0x14000d188  mov     [rbp+160h+var_1BC], ax
0x14000d18c  movzx   eax, word ptr [rcx+0Eh]
0x14000d190  mov     [rbp+160h+var_1BA], ax
0x14000d194  lea     rcx, [rbp+160h+var_1C8]
0x14000d198  mov     ebx, 1
0x14000d19d  jmp     short loc_14000D1B1
0x14000d19f  lea     rcx, [rsp+260h+var_1E8]
0x14000d1a4  call    ?GetMinFileVersion@CFileVersion@PolicyModel@@SA?AV12@XZ; PolicyModel::CFileVersion::GetMinFileVersion(void)
0x14000d1a9  mov     rcx, rax
0x14000d1ac  mov     ebx, 2
0x14000d1b1  mov     [rsp+260h+var_220], ebx
0x14000d1b5  mov     [rsp+260h+var_200], r14
0x14000d1ba  mov     [rsp+260h+var_200], r15
0x14000d1bf  movzx   eax, word ptr [rcx+8]
0x14000d1c3  mov     [rsp+260h+var_1F8], ax
0x14000d1c8  movzx   eax, word ptr [rcx+0Ah]
0x14000d1cc  mov     [rsp+260h+var_1F6], ax
0x14000d1d1  movzx   eax, word ptr [rcx+0Ch]
0x14000d1d5  mov     [rsp+260h+var_1F4], ax
0x14000d1da  movzx   eax, word ptr [rcx+0Eh]
0x14000d1de  mov     [rsp+260h+var_1F2], ax
0x14000d1e3  test    bl, 2
0x14000d1e6  jz      short loc_14000D1FA
0x14000d1e8  and     ebx, 0FFFFFFFDh
0x14000d1eb  mov     [rsp+260h+var_220], ebx
0x14000d1ef  lea     rcx, [rsp+260h+var_1E8]; this
0x14000d1f4  call    ??1CFileVersion@PolicyModel@@UEAA@XZ; PolicyModel::CFileVersion::~CFileVersion(void)
0x14000d1f9  nop
0x14000d1fa  test    bl, 1
0x14000d1fd  jz      short loc_14000D20F
0x14000d1ff  and     ebx, 0FFFFFFFEh
0x14000d202  mov     [rsp+260h+var_220], ebx
0x14000d206  lea     rcx, [rbp+160h+var_1C8]; this
0x14000d20a  call    ??1CFileVersion@PolicyModel@@UEAA@XZ; PolicyModel::CFileVersion::~CFileVersion(void)
0x14000d20f  lea     rdx, [rbp+160h+var_68]
0x14000d216  lea     rcx, [rsp+260h+var_200]
0x14000d21b  call    ?ToSddl@CFileVersion@PolicyModel@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; PolicyModel::CFileVersion::ToSddl(void)
0x14000d220  nop
0x14000d221  mov     rcx, rdi; this
0x14000d224  call    ?GetHighSection@CFileVersionRange@PolicyModel@@QEBAPEBVCFileVersion@2@XZ; PolicyModel::CFileVersionRange::GetHighSection(void)
0x14000d229  test    rax, rax
0x14000d22c  jz      short loc_14000D26A
0x14000d22e  mov     rcx, rdi; this
0x14000d231  call    ?GetHighSection@CFileVersionRange@PolicyModel@@QEBAPEBVCFileVersion@2@XZ; PolicyModel::CFileVersionRange::GetHighSection(void)
0x14000d236  mov     rcx, rax
0x14000d239  mov     [rbp+160h+var_1C8], r14
0x14000d23d  mov     [rbp+160h+var_1C8], r15
0x14000d241  movzx   eax, word ptr [rax+8]
0x14000d245  mov     [rbp+160h+var_1C0], ax
0x14000d249  movzx   eax, word ptr [rcx+0Ah]
0x14000d24d  mov     [rbp+160h+var_1BE], ax
0x14000d251  movzx   eax, word ptr [rcx+0Ch]
0x14000d255  mov     [rbp+160h+var_1BC], ax
0x14000d259  movzx   eax, word ptr [rcx+0Eh]
0x14000d25d  mov     [rbp+160h+var_1BA], ax
0x14000d261  lea     rcx, [rbp+160h+var_1C8]
0x14000d265  or      ebx, 4
0x14000d268  jmp     short loc_14000D27A
0x14000d26a  lea     rcx, [rsp+260h+var_1E8]
0x14000d26f  call    ?GetMaxFileVersion@CFileVersion@PolicyModel@@SA?AV12@XZ; PolicyModel::CFileVersion::GetMaxFileVersion(void)
0x14000d274  mov     rcx, rax
0x14000d277  or      ebx, 8
0x14000d27a  mov     [rsp+260h+var_220], ebx
0x14000d27e  mov     [rsp+260h+var_210], r14
0x14000d283  mov     [rsp+260h+var_210], r15
0x14000d288  movzx   eax, word ptr [rcx+8]
0x14000d28c  mov     [rsp+260h+var_208], ax
0x14000d291  movzx   eax, word ptr [rcx+0Ah]
0x14000d295  mov     [rsp+260h+var_206], ax
0x14000d29a  movzx   eax, word ptr [rcx+0Ch]
0x14000d29e  mov     [rsp+260h+var_204], ax
0x14000d2a3  movzx   eax, word ptr [rcx+0Eh]
0x14000d2a7  mov     [rsp+260h+var_202], ax
0x14000d2ac  test    bl, 8
0x14000d2af  jz      short loc_14000D2C3
0x14000d2b1  and     ebx, 0FFFFFFF7h
0x14000d2b4  mov     [rsp+260h+var_220], ebx
0x14000d2b8  lea     rcx, [rsp+260h+var_1E8]; this
0x14000d2bd  call    ??1CFileVersion@PolicyModel@@UEAA@XZ; PolicyModel::CFileVersion::~CFileVersion(void)
0x14000d2c2  nop
0x14000d2c3  test    bl, 4
0x14000d2c6  jz      short loc_14000D2D8
0x14000d2c8  and     ebx, 0FFFFFFFBh
0x14000d2cb  mov     [rsp+260h+var_220], ebx
0x14000d2cf  lea     rcx, [rbp+160h+var_1C8]; this
0x14000d2d3  call    ??1CFileVersion@PolicyModel@@UEAA@XZ; PolicyModel::CFileVersion::~CFileVersion(void)
0x14000d2d8  lea     rdx, [rbp+160h+var_88]
0x14000d2df  lea     rcx, [rsp+260h+var_210]
0x14000d2e4  call    ?ToSddl@CFileVersion@PolicyModel@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; PolicyModel::CFileVersion::ToSddl(void)
0x14000d2e9  nop
0x14000d2ea  mov     [rbp+160h+var_198], r12
0x14000d2ee  mov     [rbp+160h+var_190], r12
0x14000d2f2  mov     [rbp+160h+var_190], 7
0x14000d2fa  mov     [rbp+160h+var_198], r12
0x14000d2fe  mov     [rbp+160h+var_1A8], r12w
0x14000d303  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000d307  mov     r9, r15
0x14000d30a  xor     r8d, r8d
0x14000d30d  lea     rdx, [rbp+160h+var_168]
0x14000d311  lea     rcx, [rbp+160h+var_1A8]
0x14000d315  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000d31a  lea     r14, asc_140017ECC; "\\"
0x14000d321  mov     rcx, r14
0x14000d324  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000d329  mov     r8, rax
0x14000d32c  mov     rdx, r14
0x14000d32f  lea     rcx, [rbp+160h+var_1A8]
0x14000d333  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x14000d338  mov     r9, r15
0x14000d33b  xor     r8d, r8d
0x14000d33e  lea     rdx, [rbp+160h+var_148]
0x14000d342  lea     rcx, [rbp+160h+var_1A8]
0x14000d346  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000d34b  mov     rcx, r14
0x14000d34e  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000d353  mov     r8, rax
0x14000d356  mov     rdx, r14
0x14000d359  lea     rcx, [rbp+160h+var_1A8]
0x14000d35d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x14000d362  mov     r9, r15
0x14000d365  xor     r8d, r8d
0x14000d368  lea     rdx, [rbp+160h+var_48]
0x14000d36f  lea     rcx, [rbp+160h+var_1A8]
0x14000d373  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000d378  lea     rcx, [rbp+160h+var_1A8]
0x14000d37c  call    ??$ToUppercase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@StringHandler@Util@Sharp@@YAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; Sharp::Util::StringHandler::ToUppercase<std::wstring>(std::wstring &)
0x14000d381  lea     rcx, [rbp+160h+var_1A8]
0x14000d385  call    ?WrapWithQuotes@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CSddlCompiler::WrapWithQuotes(std::wstring &)
0x14000d38a  lea     rdx, [rbp+160h+var_1A8]
0x14000d38e  lea     rcx, [rbp+160h+var_108]
0x14000d392  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000d397  nop
0x14000d398  lea     r14, asc_140018EF8; ","
0x14000d39f  mov     rcx, r14
0x14000d3a2  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000d3a7  mov     r8, rax
0x14000d3aa  mov     rdx, r14
0x14000d3ad  lea     rcx, [rbp+160h+var_108]
0x14000d3b1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x14000d3b6  mov     r9, r15
0x14000d3b9  xor     r8d, r8d
0x14000d3bc  lea     rdx, [rbp+160h+var_68]
0x14000d3c3  lea     rcx, [rbp+160h+var_108]
0x14000d3c7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000d3cc  lea     rcx, [rbp+160h+var_108]
0x14000d3d0  call    ?WrapWithCurlyBrackets@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CSddlCompiler::WrapWithCurlyBrackets(std::wstring &)
0x14000d3d5  lea     rdx, [rbp+160h+var_1A8]
0x14000d3d9  lea     rcx, [rbp+160h+var_128]
0x14000d3dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000d3e2  nop
0x14000d3e3  mov     rcx, r14
0x14000d3e6  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000d3eb  mov     r8, rax
0x14000d3ee  mov     rdx, r14
0x14000d3f1  lea     rcx, [rbp+160h+var_128]
0x14000d3f5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x14000d3fa  mov     r9, r15
0x14000d3fd  xor     r8d, r8d
  ... truncated ...
```
