# Windows::Rtl::SystemImplementation::OffregRegistryProvider::MapPathToRoot(ulong,_LUNICODE_STRING const &,Windows::Rtl::SystemImplementation::OffregRegistryProvider::HandleWrapper *,wchar_t const * *,ulong *)

- ea: `0x18014cb70`
- end: `0x18014d046`
- name: `?MapPathToRoot@OffregRegistryProvider@SystemImplementation@Rtl@Windows@@AEAAJKAEBU_LUNICODE_STRING@@PEAVHandleWrapper@1234@PEAPEB_WPEAK@Z`
- size: `1238`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::OffregRegistryProvider *__hidden this, unsigned int, const struct _LUNICODE_STRING *, struct Windows::Rtl::SystemImplementation::OffregRegistryProvider::HandleWrapper *, const wchar_t **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18014d1c0`
- `0x18014f510`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x1800167d4`
- `0x18001684c`
- `0x1800497c0`
- `0x180049860`
- `0x18004ab40`
- `0x18012ef20`
- `0x18014c198`
- `0x18014cb70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014cc5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014cd05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014cdbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014cc5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014cd05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014cdbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014cc21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014ccc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014cd3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014cc21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014ccc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014cd3d`

## string_xrefs

- `0x18014cd6b`: `Windows::COM::CUnicodeStringBaseTraits::Duplicate`
- `0x18014cd80`: `ppszTemp = AllocateChars(cchTotal)`
- `0x18014cd51`: `onecore\base\wcp\inc\wcp_auto_com.h`
- `0x18014d013`: `Windows::Rtl::SystemImplementation::OffregRegistryProvider::MapPathToRoot`
- `0x18014ccd5`: `\Registry\Machine`
- `0x18014cc39`: `\Registry`
- `0x18014cd9a`: `\Registry\User`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::OffregRegistryProvider::MapPathToRoot(
        Windows::Rtl::SystemImplementation::OffregRegistryProvider *this,
        int a2,
        const struct _LUNICODE_STRING *a3,
        struct Windows::Rtl::SystemImplementation::OffregRegistryProvider::HandleWrapper *a4,
        const wchar_t **a5,
        unsigned int *a6)
{
  bool v6; // r13
  __int64 v10; // xmm1_8
  _WORD *v11; // rax
  _WORD *v12; // rbx
  void *v13; // rcx
  __int64 result; // rax
  _OWORD *v15; // rax
  _OWORD *v16; // rbx
  void *v17; // rcx
  char *v18; // rax
  char *v19; // rbx
  void *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  bool v23; // al
  unsigned __int64 v24; // rax
  _QWORD *v25; // r14
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rax
  int v30; // ebx
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // r8
  unsigned int v33; // ebx
  __int64 v34; // rdx
  bool v35[8]; // [rsp+20h] [rbp-59h] BYREF
  unsigned __int64 v36; // [rsp+28h] [rbp-51h] BYREF
  int v37; // [rsp+30h] [rbp-49h]
  __int64 v38; // [rsp+38h] [rbp-41h] BYREF
  __int128 v39; // [rsp+40h] [rbp-39h]
  unsigned __int64 v40; // [rsp+50h] [rbp-29h]
  _QWORD *v41; // [rsp+58h] [rbp-21h]
  __int128 v42; // [rsp+60h] [rbp-19h] BYREF
  __int64 v43; // [rsp+70h] [rbp-9h]
  const char *v44; // [rsp+78h] [rbp-1h]

  v6 = 0;
  v37 = a2;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( *((_QWORD *)a3 + 1) - *(_QWORD *)a3 < 2u || *(_WORD *)(*((_QWORD *)a3 + 2) + 2LL * (*(_QWORD *)a3 >> 1)) )
    goto LABEL_61;
  v10 = *((_QWORD *)a3 + 2);
  v42 = *(_OWORD *)a3;
  v43 = v10;
  Windows::StringUtil::DropTrailingNtPathSlashes<_LUNICODE_STRING *>(&v42);
  if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                          &v42,
                          ___LiteralObject__2U__BaseLiteralBuffer__09U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FM__0HC__0GF__0GH__0GJ__0HD__0HE__0HC__0HJ__0A_____0A__00_01_02_03_04_05_06_07_08_Details_RtlStringLiterals__3U_LUNICODE_STRING__B) )
  {
    v11 = CoTaskMemAlloc(0x14u);
    v12 = v11;
    if ( v11 )
    {
      *(_OWORD *)v11 = *(_OWORD *)L"\\Registry";
      v11[8] = aRegistry_0[8];
      v11[9] = 0;
      v13 = *(void **)a4;
      if ( *(_QWORD *)a4 )
      {
        *(_QWORD *)a4 = 0;
        CoTaskMemFree(v13);
      }
      *(_QWORD *)a4 = v12;
      *((_DWORD *)a4 + 26) = 1;
LABEL_12:
      *a5 = (const wchar_t *)&dword_1801CAD7C;
      return 0;
    }
    goto LABEL_22;
  }
  if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                          &v42,
                          ___LiteralObject__2U__BaseLiteralBuffer__0BC_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FM__0HC__0GF__0GH__0GJ__0HD__0HE__0HC__0HJ__0FM__0GN__0GB__0GD__0GI__0GJ__0GO__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__Details_RtlStringLiterals__3U_LUNICODE_STRING__B) )
  {
    v15 = CoTaskMemAlloc(0x24u);
    v16 = v15;
    if ( v15 )
    {
      *v15 = *(_OWORD *)L"\\Registry\\Machine";
      v15[1] = *(_OWORD *)L"y\\Machine";
      *((_WORD *)v15 + 16) = aRegistryMachin[16];
      *((_WORD *)v15 + 17) = 0;
      v17 = *(void **)a4;
      if ( *(_QWORD *)a4 )
      {
        *(_QWORD *)a4 = 0;
        CoTaskMemFree(v17);
      }
      *(_QWORD *)a4 = v16;
      *((_DWORD *)a4 + 26) = 2;
      goto LABEL_12;
    }
LABEL_22:
    v43 = 120;
    *(_QWORD *)&v42 = "onecore\\base\\wcp\\inc\\wcp_auto_com.h";
    *((_QWORD *)&v42 + 1) = "Windows::COM::CUnicodeStringBaseTraits::Duplicate";
    v44 = "ppszTemp = AllocateChars(cchTotal)";
    RtlReportErrorOrigination(&v42, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942414LL);
    return 2147942414LL;
  }
  if ( (unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                          &v42,
                          ___LiteralObject__2U__BaseLiteralBuffer__0P_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FM__0HC__0GF__0GH__0GJ__0HD__0HE__0HC__0HJ__0FM__0HF__0HD__0GF__0HC__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__Details_RtlStringLiterals__3U_LUNICODE_STRING__B) )
  {
    v18 = (char *)CoTaskMemAlloc(0x1Eu);
    v19 = v18;
    if ( v18 )
    {
      *(_OWORD *)v18 = *(_OWORD *)L"\\Registry\\User";
      *(_OWORD *)(v18 + 12) = *(_OWORD *)L"try\\User";
      *((_WORD *)v18 + 14) = 0;
      v20 = *(void **)a4;
      if ( *(_QWORD *)a4 )
      {
        *(_QWORD *)a4 = 0;
        CoTaskMemFree(v20);
      }
      *(_QWORD *)a4 = v19;
      *((_DWORD *)a4 + 26) = 3;
      goto LABEL_12;
    }
    goto LABEL_22;
  }
  v38 = 36;
  v39 = *(_OWORD *)byte_1801C6450;
  v23 = 0;
  if ( *(_QWORD *)a3 >= 0x24u )
  {
    v21 = *((_QWORD *)a3 + 2);
    *((_QWORD *)&v42 + 1) = 36;
    *(_QWORD *)&v42 = 36;
    v43 = v21;
    LODWORD(v36) = 0;
    v22 = Windows::StringUtil::Rtl::CompareStringsByOrdinalCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
            &v42,
            &v38,
            &v36);
    if ( !(_DWORD)v36 && v22 >= 0 )
      v23 = 1;
  }
  v24 = -(__int64)v23 & 0xFFFFFFFFFFFFFFE8uLL;
  v25 = *(_QWORD **)((char *)this + v24 + 40);
  v41 = *(_QWORD **)((char *)this + v24 + 48);
  if ( v25 != v41 )
  {
    while ( 2 )
    {
      v26 = v25[5];
      v27 = *((_QWORD *)a3 + 2);
      v28 = v26 + v25[3];
      v29 = v27 + *(_QWORD *)a3;
      v35[0] = 0;
      v36 = v29;
      v40 = v28;
      while ( v26 < v28 && v27 < v29 )
      {
        RtlDecodeUtf16LE(&v42, v26, v28);
        if ( (_DWORD)v42 == -1 )
        {
          v33 = DWORD2(v42);
          if ( (SDWORD2(v42) & 0x80000000) == 0 )
            goto LABEL_61;
          v43 = 3575;
LABEL_55:
          *(_QWORD *)&v42 = "OneCore\\Internal\\Base\\inc\\rtlstringutil.h";
          *((_QWORD *)&v42 + 1) = "Windows::StringUtil::Rtl::IsStringPrefixEqualByOrdinalCaseInvariant";
          v44 = "__rv.UcsCharacter != (0xffffffff)";
          RtlReportErrorOrigination(&v42, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v33);
          return v33;
        }
        RtlDecodeUtf16LE(&v38, v27, v36);
        if ( (_DWORD)v38 == -1 )
        {
          v33 = v39;
          if ( (int)v39 < 0 )
          {
            v43 = 3576;
            goto LABEL_55;
          }
LABEL_61:
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x18014D045LL);
        }
        v30 = RtlDowncaseUCSCharacter((unsigned int)v42);
        if ( v30 != (unsigned int)RtlDowncaseUCSCharacter((unsigned int)v38) )
          goto LABEL_40;
        v26 = *((_QWORD *)&v42 + 1);
        v27 = v39;
        v28 = v40;
        v29 = v36;
      }
      v6 = v26 == v28;
      v35[0] = v26 == v28;
LABEL_40:
      v31 = v25[3];
      v32 = v31 >> 1;
      if ( !v6 )
      {
        if ( v31 <= *(_QWORD *)a3 || v31 - *(_QWORD *)a3 != 2 )
        {
          v6 = 0;
          goto LABEL_47;
        }
        result = Windows::StringUtil::Rtl::IsStringPrefixEqualByOrdinalCaseInvariant<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>(
                   a3,
                   v25 + 3,
                   v35);
        v6 = 0;
        if ( (int)result < 0 )
          return result;
        v32 = *(_QWORD *)a3 >> 1;
        if ( !v35[0] )
        {
LABEL_47:
          v25 += 7;
          if ( v25 != v41 )
            continue;
          goto LABEL_48;
        }
      }
      break;
    }
    v34 = *((_QWORD *)a3 + 2);
    if ( v34 && (*((_QWORD *)a3 + 1) - *(_QWORD *)a3 < 2u || *(_WORD *)(v34 + 2LL * (*(_QWORD *)a3 >> 1))) )
      goto LABEL_61;
    *a5 = (const wchar_t *)(v34 + 2 * v32);
    *((_QWORD *)a4 + 2) = v25[6];
    return 0;
  }
LABEL_48:
  if ( (v37 & 4) == 0 )
  {
    v43 = 206;
    *(_QWORD *)&v42 = "onecore\\base\\wcp\\sil\\reg_offreg.cpp";
    v44 = 0;
    *((_QWORD *)&v42 + 1) = "Windows::Rtl::SystemImplementation::OffregRegistryProvider::MapPathToRoot";
    RtlReportErrorOrigination(&v42, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225529LL);
    return 3221225529LL;
  }
  if ( a6 )
    *a6 = 4;
  return 0;
}

```

## disassembly

```asm
0x18014cb70  mov     [rsp-8+arg_8], rbx
0x18014cb75  push    rbp
0x18014cb76  push    rsi
0x18014cb77  push    rdi
0x18014cb78  push    r12
0x18014cb7a  push    r13
0x18014cb7c  push    r14
0x18014cb7e  push    r15
0x18014cb80  lea     rbp, [rsp-17h]
0x18014cb85  sub     rsp, 90h
0x18014cb8c  mov     rax, cs:__security_cookie
0x18014cb93  xor     rax, rsp
0x18014cb96  mov     [rbp+47h+var_40], rax
0x18014cb9a  mov     r15, [rbp+47h+arg_20]
0x18014cb9e  xor     r13d, r13d
0x18014cba1  mov     r12, [rbp+47h+arg_28]
0x18014cba5  mov     rdi, r9
0x18014cba8  mov     [rbp+47h+var_90], edx
0x18014cbab  mov     rsi, r8
0x18014cbae  mov     rbx, rcx
0x18014cbb1  test    r15, r15
0x18014cbb4  jz      short loc_18014CBB9
0x18014cbb6  mov     [r15], r13
0x18014cbb9  test    r12, r12
0x18014cbbc  jz      short loc_18014CBC2
0x18014cbbe  mov     [r12], r13d
0x18014cbc2  mov     rcx, [r8]
0x18014cbc5  mov     rax, [r8+8]
0x18014cbc9  sub     rax, rcx
0x18014cbcc  cmp     rax, 2
0x18014cbd0  jb      loc_18014D03B
0x18014cbd6  mov     rax, [r8+10h]
0x18014cbda  shr     rcx, 1
0x18014cbdd  cmp     [rax+rcx*2], r13w
0x18014cbe2  jnz     loc_18014D03B
0x18014cbe8  movups  xmm0, xmmword ptr [r8]
0x18014cbec  lea     rcx, [rbp+47h+var_60]
0x18014cbf0  movsd   xmm1, qword ptr [r8+10h]
0x18014cbf6  movups  [rbp+47h+var_60], xmm0
0x18014cbfa  movsd   [rbp+47h+var_50], xmm1
0x18014cbff  call    ??$DropTrailingNtPathSlashes@PEAU_LUNICODE_STRING@@@StringUtil@Windows@@YAXPEAU_LUNICODE_STRING@@@Z; Windows::StringUtil::DropTrailingNtPathSlashes<_LUNICODE_STRING *>(_LUNICODE_STRING *)
0x18014cc04  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$09U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FM@@0HC@@0GF@@0GH@@0GJ@@0HD@@0HE@@0HC@@0HJ@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x18014cc0b  lea     rcx, [rbp+47h+var_60]
0x18014cc0f  call    ??$AreStringAndLowerCaseAsciiStringEqualCaseInvariant@U_LUNICODE_STRING@@U1@@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@0@Z; Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &)
0x18014cc14  test    al, al
0x18014cc16  jz      loc_18014CCA8
0x18014cc1c  mov     ecx, 14h; cb
0x18014cc21  call    cs:__imp_CoTaskMemAlloc
0x18014cc28  nop     dword ptr [rax+rax+00h]
0x18014cc2d  mov     rbx, rax
0x18014cc30  test    rax, rax
0x18014cc33  jz      loc_18014CD51
0x18014cc39  movups  xmm0, xmmword ptr cs:aRegistry_0; "\\Registry"
0x18014cc40  movups  xmmword ptr [rax], xmm0
0x18014cc43  movzx   eax, word ptr cs:aRegistry_0+10h; "y"
0x18014cc4a  mov     [rbx+10h], ax
0x18014cc4e  mov     [rbx+12h], r13w
0x18014cc53  mov     rcx, [rdi]; pv
0x18014cc56  test    rcx, rcx
0x18014cc59  jz      short loc_18014CC6A
0x18014cc5b  mov     [rdi], r13
0x18014cc5e  call    cs:__imp_CoTaskMemFree
0x18014cc65  nop     dword ptr [rax+rax+00h]
0x18014cc6a  mov     [rdi], rbx
0x18014cc6d  mov     dword ptr [rdi+68h], 1
0x18014cc74  lea     rax, dword_1801CAD7C
0x18014cc7b  mov     [r15], rax
0x18014cc7e  xor     eax, eax
0x18014cc80  mov     rcx, [rbp+47h+var_40]
0x18014cc84  xor     rcx, rsp; StackCookie
0x18014cc87  call    __security_check_cookie
0x18014cc8c  mov     rbx, [rsp+0C0h+arg_8]
0x18014cc94  add     rsp, 90h
0x18014cc9b  pop     r15
0x18014cc9d  pop     r14
0x18014cc9f  pop     r13
0x18014cca1  pop     r12
0x18014cca3  pop     rdi
0x18014cca4  pop     rsi
0x18014cca5  pop     rbp
0x18014cca6  retn
0x18014cca8  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0BC@U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FM@@0HC@@0GF@@0GH@@0GJ@@0HD@@0HE@@0HC@@0HJ@@0FM@@0GN@@0GB@@0GD@@0GI@@0GJ@@0GO@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x18014ccaf  lea     rcx, [rbp+47h+var_60]
0x18014ccb3  call    ??$AreStringAndLowerCaseAsciiStringEqualCaseInvariant@U_LUNICODE_STRING@@U1@@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@0@Z; Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &)
0x18014ccb8  test    al, al
0x18014ccba  jz      short loc_18014CD20
0x18014ccbc  mov     ecx, 24h ; '$'; cb
0x18014ccc1  call    cs:__imp_CoTaskMemAlloc
0x18014ccc8  nop     dword ptr [rax+rax+00h]
0x18014cccd  mov     rbx, rax
0x18014ccd0  test    rax, rax
0x18014ccd3  jz      short loc_18014CD51
0x18014ccd5  movups  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine"
0x18014ccdc  movups  xmmword ptr [rax], xmm0
0x18014ccdf  movups  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine"
0x18014cce6  movups  xmmword ptr [rax+10h], xmm1
0x18014ccea  movzx   eax, word ptr cs:aRegistryMachin+20h; "e"
0x18014ccf1  mov     [rbx+20h], ax
0x18014ccf5  mov     [rbx+22h], r13w
0x18014ccfa  mov     rcx, [rdi]; pv
0x18014ccfd  test    rcx, rcx
0x18014cd00  jz      short loc_18014CD11
0x18014cd02  mov     [rdi], r13
0x18014cd05  call    cs:__imp_CoTaskMemFree
0x18014cd0c  nop     dword ptr [rax+rax+00h]
0x18014cd11  mov     [rdi], rbx
0x18014cd14  mov     dword ptr [rdi+68h], 2
0x18014cd1b  jmp     loc_18014CC74
0x18014cd20  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0P@U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FM@@0HC@@0GF@@0GH@@0GJ@@0HD@@0HE@@0HC@@0HJ@@0FM@@0HF@@0HD@@0GF@@0HC@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x18014cd27  lea     rcx, [rbp+47h+var_60]
0x18014cd2b  call    ??$AreStringAndLowerCaseAsciiStringEqualCaseInvariant@U_LUNICODE_STRING@@U1@@StringUtil@Windows@@YA_NAEBU_LUNICODE_STRING@@0@Z; Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &)
0x18014cd30  test    al, al
0x18014cd32  jz      loc_18014CDDA
0x18014cd38  mov     ecx, 1Eh; cb
0x18014cd3d  call    cs:__imp_CoTaskMemAlloc
0x18014cd44  nop     dword ptr [rax+rax+00h]
0x18014cd49  mov     rbx, rax
0x18014cd4c  test    rax, rax
0x18014cd4f  jnz     short loc_18014CD9A
0x18014cd51  lea     rax, aOnecoreBaseWcp_3; "onecore\\base\\wcp\\inc\\wcp_auto_com.h"
0x18014cd58  mov     [rbp+47h+var_50], 78h ; 'x'
0x18014cd60  mov     qword ptr [rbp+47h+var_60], rax
0x18014cd64  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18014cd6b  lea     rax, aWindowsComCuni; "Windows::COM::CUnicodeStringBaseTraits:"...
0x18014cd72  mov     r8d, 8007000Eh
0x18014cd78  mov     qword ptr [rbp+47h+var_60+8], rax
0x18014cd7c  lea     rcx, [rbp+47h+var_60]
0x18014cd80  lea     rax, aPpsztempAlloca; "ppszTemp = AllocateChars(cchTotal)"
0x18014cd87  mov     [rbp+47h+var_48], rax
0x18014cd8b  call    RtlReportErrorOrigination
0x18014cd90  mov     eax, 8007000Eh
0x18014cd95  jmp     loc_18014CC80
0x18014cd9a  movups  xmm0, xmmword ptr cs:aRegistryUser; "\\Registry\\User"
0x18014cda1  movups  xmmword ptr [rax], xmm0
0x18014cda4  movups  xmm1, xmmword ptr cs:aRegistryUser+0Ch; "try\\User"
0x18014cdab  movups  xmmword ptr [rax+0Ch], xmm1
0x18014cdaf  mov     [rax+1Ch], r13w
0x18014cdb4  mov     rcx, [rdi]; pv
0x18014cdb7  test    rcx, rcx
0x18014cdba  jz      short loc_18014CDCB
0x18014cdbc  mov     [rdi], r13
0x18014cdbf  call    cs:__imp_CoTaskMemFree
0x18014cdc6  nop     dword ptr [rax+rax+00h]
0x18014cdcb  mov     [rdi], rbx
0x18014cdce  mov     dword ptr [rdi+68h], 3
0x18014cdd5  jmp     loc_18014CC74
0x18014cdda  movups  xmm0, xmmword ptr cs:byte_1801C6450
0x18014cde1  mov     ecx, 24h ; '$'
0x18014cde6  mov     [rbp+47h+var_88], rcx
0x18014cdea  movdqu  [rbp+47h+var_80], xmm0
0x18014cdef  cmp     [rsi], rcx
0x18014cdf2  jb      short loc_18014CE2A
0x18014cdf4  mov     rax, [rsi+10h]
0x18014cdf8  lea     r8, [rbp+47h+var_98]
0x18014cdfc  mov     qword ptr [rbp+47h+var_60+8], rcx
0x18014ce00  lea     rdx, [rbp+47h+var_88]
0x18014ce04  mov     qword ptr [rbp+47h+var_60], rcx
0x18014ce08  lea     rcx, [rbp+47h+var_60]
0x18014ce0c  mov     [rbp+47h+var_50], rax
0x18014ce10  mov     dword ptr [rbp+47h+var_98], r13d
0x18014ce14  call    ??$CompareStringsByOrdinalCaseInvariant@U_LUNICODE_STRING@@U1@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@0PEAH@Z; Windows::StringUtil::Rtl::CompareStringsByOrdinalCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &,int *)
0x18014ce19  cmp     dword ptr [rbp+47h+var_98], r13d
0x18014ce1d  jnz     short loc_18014CE2A
0x18014ce1f  test    eax, eax
0x18014ce21  js      short loc_18014CE2A
0x18014ce23  mov     eax, 1
0x18014ce28  jmp     short loc_18014CE2D
0x18014ce2a  mov     al, r13b
0x18014ce2d  neg     al
0x18014ce2f  sbb     rax, rax
0x18014ce32  and     rax, 0FFFFFFFFFFFFFFE8h
0x18014ce36  mov     r14, [rax+rbx+28h]
0x18014ce3b  mov     rax, [rax+rbx+30h]
0x18014ce40  mov     [rbp+47h+var_68], rax
0x18014ce44  cmp     r14, rax
0x18014ce47  jz      loc_18014CF3C
0x18014ce4d  mov     rcx, [r14+28h]
0x18014ce51  mov     rdx, [r14+18h]
0x18014ce55  mov     rbx, [rsi+10h]
0x18014ce59  add     rdx, rcx
0x18014ce5c  mov     rax, [rsi]
0x18014ce5f  add     rax, rbx
0x18014ce62  mov     [rbp+47h+var_A0], r13b
0x18014ce66  mov     [rbp+47h+var_98], rax
0x18014ce6a  mov     [rbp+47h+var_70], rdx
0x18014ce6e  jmp     short loc_18014CECE
0x18014ce70  cmp     rbx, rax
0x18014ce73  jnb     short loc_18014CED3
0x18014ce75  mov     r8, rdx
0x18014ce78  mov     rdx, rcx
0x18014ce7b  lea     rcx, [rbp+47h+var_60]
0x18014ce7f  call    RtlDecodeUtf16LE
0x18014ce84  cmp     dword ptr [rbp+47h+var_60], 0FFFFFFFFh
0x18014ce88  jz      loc_18014CF71
0x18014ce8e  mov     r8, [rbp+47h+var_98]
0x18014ce92  lea     rcx, [rbp+47h+var_88]
0x18014ce96  mov     rdx, rbx
0x18014ce99  call    RtlDecodeUtf16LE
0x18014ce9e  cmp     dword ptr [rbp+47h+var_88], 0FFFFFFFFh
0x18014cea2  jz      loc_18014CF5C
0x18014cea8  mov     ecx, dword ptr [rbp+47h+var_60]
0x18014ceab  call    RtlDowncaseUCSCharacter
0x18014ceb0  mov     ecx, dword ptr [rbp+47h+var_88]
0x18014ceb3  mov     ebx, eax
0x18014ceb5  call    RtlDowncaseUCSCharacter
0x18014ceba  cmp     ebx, eax
0x18014cebc  jnz     short loc_18014CEDE
0x18014cebe  mov     rcx, qword ptr [rbp+47h+var_60+8]
0x18014cec2  mov     rbx, qword ptr [rbp+47h+var_80]
0x18014cec6  mov     rdx, [rbp+47h+var_70]
0x18014ceca  mov     rax, [rbp+47h+var_98]
0x18014cece  cmp     rcx, rdx
0x18014ced1  jb      short loc_18014CE70
0x18014ced3  cmp     rcx, rdx
0x18014ced6  setz    r13b
0x18014ceda  mov     [rbp+47h+var_A0], r13b
0x18014cede  lea     rdx, [r14+18h]
0x18014cee2  mov     rax, [rdx]
0x18014cee5  mov     r8, rax
0x18014cee8  shr     r8, 1
0x18014ceeb  test    r13b, r13b
0x18014ceee  jnz     loc_18014CFBF
0x18014cef4  cmp     rax, [rsi]
0x18014cef7  jbe     short loc_18014CF2B
0x18014cef9  sub     rax, [rsi]
0x18014cefc  cmp     rax, 2
0x18014cf00  jnz     short loc_18014CF2B
0x18014cf02  lea     r8, [rbp+47h+var_A0]
0x18014cf06  mov     rcx, rsi
0x18014cf09  call    ??$IsStringPrefixEqualByOrdinalCaseInvariant@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@AEBV?$Auto@U_LUNICODE_STRING@@@2@PEA_N@Z; Windows::StringUtil::Rtl::IsStringPrefixEqualByOrdinalCaseInvariant<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>(_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> const &,bool *)
0x18014cf0e  xor     r13d, r13d
0x18014cf11  test    eax, eax
0x18014cf13  js      loc_18014CC80
0x18014cf19  mov     r8, [rsi]
0x18014cf1c  shr     r8, 1
0x18014cf1f  cmp     [rbp+47h+var_A0], r13b
0x18014cf23  jnz     loc_18014CFC2
0x18014cf29  jmp     short loc_18014CF2E
0x18014cf2b  xor     r13d, r13d
0x18014cf2e  add     r14, 38h ; '8'
0x18014cf32  cmp     r14, [rbp+47h+var_68]
0x18014cf36  jnz     loc_18014CE4D
0x18014cf3c  test    byte ptr [rbp+47h+var_90], 4
0x18014cf40  jz      loc_18014CFF9
0x18014cf46  test    r12, r12
0x18014cf49  jz      loc_18014CC7E
0x18014cf4f  mov     dword ptr [r12], 4
0x18014cf57  jmp     loc_18014CC7E
0x18014cf5c  mov     ebx, dword ptr [rbp+47h+var_80]
0x18014cf5f  test    ebx, ebx
0x18014cf61  jns     loc_18014D03B
0x18014cf67  mov     [rbp+47h+var_50], 0DF8h
0x18014cf6f  jmp     short loc_18014CF84
0x18014cf71  mov     ebx, dword ptr [rbp+47h+var_60+8]
0x18014cf74  test    ebx, ebx
0x18014cf76  jns     loc_18014D03B
0x18014cf7c  mov     [rbp+47h+var_50], 0DF7h
0x18014cf84  lea     rax, aOnecoreInterna_4; "OneCore\\Internal\\Base\\inc\\rtlstring"...
0x18014cf8b  mov     r8d, ebx
0x18014cf8e  mov     qword ptr [rbp+47h+var_60], rax
0x18014cf92  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18014cf99  lea     rax, aWindowsStringu; "Windows::StringUtil::Rtl::IsStringPrefi"...
0x18014cfa0  mov     qword ptr [rbp+47h+var_60+8], rax
0x18014cfa4  lea     rcx, [rbp+47h+var_60]
0x18014cfa8  lea     rax, aRvUcscharacter; "__rv.UcsCharacter != (0xffffffff)"
0x18014cfaf  mov     [rbp+47h+var_48], rax
0x18014cfb3  call    RtlReportErrorOrigination
0x18014cfb8  mov     eax, ebx
0x18014cfba  jmp     loc_18014CC80
0x18014cfbf  xor     r13d, r13d
0x18014cfc2  mov     rdx, [rsi+10h]
0x18014cfc6  test    rdx, rdx
0x18014cfc9  jz      short loc_18014CFE5
0x18014cfcb  mov     rcx, [rsi]
0x18014cfce  mov     rax, [rsi+8]
0x18014cfd2  sub     rax, rcx
0x18014cfd5  cmp     rax, 2
0x18014cfd9  jb      short loc_18014D03B
0x18014cfdb  shr     rcx, 1
0x18014cfde  cmp     [rdx+rcx*2], r13w
0x18014cfe3  jnz     short loc_18014D03B
0x18014cfe5  lea     rax, [rdx+r8*2]
0x18014cfe9  mov     [r15], rax
0x18014cfec  mov     rax, [r14+30h]
0x18014cff0  mov     [rdi+10h], rax
0x18014cff4  jmp     loc_18014CC7E
0x18014cff9  lea     rax, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\sil\\reg_offreg.cpp"
0x18014d000  mov     [rbp+47h+var_50], 0CEh
0x18014d008  mov     qword ptr [rbp+47h+var_60], rax
0x18014d00c  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18014d013  lea     rax, aWindowsRtlSyst_85; "Windows::Rtl::SystemImplementation::Off"...
0x18014d01a  mov     [rbp+47h+var_48], r13
0x18014d01e  mov     r8d, 0C0000039h
0x18014d024  mov     qword ptr [rbp+47h+var_60+8], rax
0x18014d028  lea     rcx, [rbp+47h+var_60]
0x18014d02c  call    RtlReportErrorOrigination
0x18014d031  mov     eax, 0C0000039h
0x18014d036  jmp     loc_18014CC80
0x18014d03b  mov     ecx, 0C00000E5h; int
0x18014d040  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
  ... truncated ...
```
