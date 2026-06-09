# SettingXmlParser::Update(void)

- ea: `0x180015800`
- end: `0x180015ef3`
- name: `?Update@SettingXmlParser@@UEAAKXZ`
- size: `1779`
- prototype: `unsigned int __fastcall(SettingXmlParser *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021e90`

## callees

- `0x1800059fc`
- `0x180015800`
- `0x180015fac`
- `0x18001648c`
- `0x18001666c`
- `0x1800167ac`
- `0x1800168e4`
- `0x180016984`
- `0x180016b30`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180015e88`
- `ntdll!RtlNtStatusToDosError` at `0x180015e88`
- `ServicingCommon!RtlFreeLUtf8String` at `0x180015eca`
- `ServicingCommon!RtlFreeLUtf8String` at `0x180015eca`

## string_xrefs

- `0x180015e65`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x18001584c`: `failed to write EOL`
- `0x1800158d3`: `failed to write EOL`
- `0x18001595a`: `failed to write EOL`
- `0x180015a90`: `failed to write EOL`
- `0x180015ae9`: `failed to write EOL`
- `0x180015b98`: `failed to write EOL`
- `0x180015d6c`: `failed to write EOL`
- `0x180015e02`: `failed to write EOL`
- `0x180015881`: `failed to begin open element`
- `0x180015908`: `failed to begin open element`
- `0x1800159c4`: `failed to begin open element`
- `0x180015bcd`: `failed to begin open element`
- `0x1800158af`: `failed to end open element`
- `0x180015936`: `failed to end open element`
- `0x180015a6c`: `failed to end open element`
- `0x180015d4d`: `failed to end open element`
- `0x180015b45`: `failed to write single node`
- `0x180015b74`: `failed to write single node`
- `0x180015e6f`: `SettingXmlParser::Update %s (0x%x) in file %S line %d`
- `0x18001598f`: `failed to write Indent`
- `0x1800159fc`: `failed to write wifi SSID attribute`
- `0x180015a3b`: `failed to write Total Wait Time attribute`
- `0x180015c88`: `failed to write Total Wait Time attribute`
- `0x180015cb0`: `failed to write Total Wait Time attribute`
- `0x180015c17`: `failed to write AutoRemediation State attribute`
- `0x180015c3f`: `failed to write AutoRemediation State attribute`
- `0x180015cf9`: `failed to write Wait Interval attribute`
- `0x180015d21`: `failed to write Wait Interval attribute`
- `0x180015dbc`: `failed to write Headless node`
- `0x180015de6`: `failed to write Headless node`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SettingXmlParser::Update(unsigned __int16 **this)
{
  NTSTATUS v2; // ebx
  const wchar_t *v3; // r8
  int v4; // eax
  const struct _LUTF8_STRING *v5; // r8
  const struct _LUTF8_STRING *v6; // r8
  const struct _LUTF8_STRING *v7; // r8
  const struct _LUTF8_STRING *v8; // r9
  unsigned __int16 *v9; // rax
  const struct _LUTF8_STRING *v10; // r8
  unsigned __int16 *v11; // rax
  const struct _LUTF8_STRING *v12; // r8
  unsigned __int16 *v13; // rax
  const struct _LUTF8_STRING *v14; // r8
  unsigned __int16 *v15; // rax
  const struct _LUTF8_STRING *v16; // r8
  const struct _LUTF8_STRING *v17; // r9
  unsigned __int16 *v18; // rax
  BasicXmlParser *v19; // rcx
  ULONG v20; // eax
  unsigned int v21; // ebx
  unsigned __int16 *v22; // rdx
  struct _GUID *v24; // [rsp+20h] [rbp-50h]
  struct _GUID *v25; // [rsp+20h] [rbp-50h]
  struct _GUID *v26; // [rsp+20h] [rbp-50h]
  struct _GUID *v27; // [rsp+20h] [rbp-50h]
  struct _GUID *v28; // [rsp+20h] [rbp-50h]
  struct _GUID *v29; // [rsp+28h] [rbp-48h]
  struct _GUID v30; // [rsp+40h] [rbp-30h] BYREF
  __int128 v31; // [rsp+50h] [rbp-20h] BYREF
  __int64 v32; // [rsp+60h] [rbp-10h]

  *(_QWORD *)v30.Data4 = -2;
  v31 = 0;
  v32 = 0;
  v2 = BasicXmlParser::WriteEOL((BasicXmlParser *)this);
  if ( v2 < 0 )
  {
    v3 = L"failed to write EOL";
    v4 = 3155;
LABEL_71:
    LODWORD(v29) = v4;
    UnattendLogW(
      2,
      L"SettingXmlParser::Update %s (0x%x) in file %S line %d",
      v3,
      (unsigned int)v2,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      v29);
    v20 = RtlNtStatusToDosError(v2);
LABEL_76:
    v21 = v20;
    goto LABEL_77;
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, void *))(*(_QWORD *)this[5] + 40LL))(
         this[5],
         0,
         &SettingXmlParser::Utf8ToplevelEntryTag);
  if ( v2 < 0 )
  {
    v3 = L"failed to begin open element";
    v4 = 3156;
    goto LABEL_71;
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)this[5] + 48LL))(this[5], 0);
  if ( v2 < 0 )
  {
    v3 = L"failed to end open element";
    v4 = 3157;
    goto LABEL_71;
  }
  v2 = BasicXmlParser::WriteEOLWithIndent((BasicXmlParser *)this);
  if ( v2 < 0 )
  {
    v3 = L"failed to write EOL";
    v4 = 3158;
    goto LABEL_71;
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, void *))(*(_QWORD *)this[5] + 40LL))(
         this[5],
         0,
         &SettingXmlParser::Utf8WifiCredentialTag);
  if ( v2 < 0 )
  {
    v3 = L"failed to begin open element";
    v4 = 3165;
    goto LABEL_71;
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)this[5] + 48LL))(this[5], 0);
  if ( v2 < 0 )
  {
    v3 = L"failed to end open element";
    v4 = 3166;
    goto LABEL_71;
  }
  v2 = BasicXmlParser::WriteEOLWithIndent((BasicXmlParser *)this);
  if ( v2 < 0 )
  {
    v3 = L"failed to write EOL";
    v4 = 3167;
    goto LABEL_71;
  }
  if ( (this[8][614] & 1) != 0 )
  {
    v2 = BasicXmlParser::WriteIndent((BasicXmlParser *)this);
    if ( v2 < 0 )
    {
      v3 = L"failed to write Indent";
      v4 = 3172;
      goto LABEL_71;
    }
    v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, void *))(*(_QWORD *)this[5] + 40LL))(
           this[5],
           0,
           &SettingXmlParser::Utf8WifiTag);
    if ( v2 < 0 )
    {
      v3 = L"failed to begin open element";
      v4 = 3173;
      goto LABEL_71;
    }
    v2 = BasicXmlParser::WriteAttribute(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8WifiSsidAttrTag,
           v5,
           this[8],
           v24,
           0);
    if ( v2 < 0 )
    {
      v3 = L"failed to write wifi SSID attribute";
      v4 = 3175;
      goto LABEL_71;
    }
    v2 = BasicXmlParser::WriteAttribute(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8WifiPasswordAttrTag,
           v6,
           this[8] + 302,
           v25,
           0);
    if ( v2 < 0 )
    {
      v3 = L"failed to write Total Wait Time attribute";
      v4 = 3177;
      goto LABEL_71;
    }
    v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)this[5] + 48LL))(this[5], 1);
    if ( v2 < 0 )
    {
      v3 = L"failed to end open element";
      v4 = 3178;
      goto LABEL_71;
    }
    v2 = BasicXmlParser::WriteEOLWithIndent((BasicXmlParser *)this);
    if ( v2 < 0 )
    {
      v3 = L"failed to write EOL";
      v4 = 3179;
      goto LABEL_71;
    }
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, void *))(*(_QWORD *)this[5] + 80LL))(
         this[5],
         0,
         &SettingXmlParser::Utf8WifiCredentialTag);
  if ( v2 < 0 )
  {
    v3 = L"failed to close element";
    v4 = 3183;
    goto LABEL_71;
  }
  v2 = BasicXmlParser::WriteEOLWithIndent((BasicXmlParser *)this);
  if ( v2 < 0 )
  {
    v3 = L"failed to write EOL";
    v4 = 3184;
    goto LABEL_71;
  }
  v9 = this[8];
  if ( (v9[614] & 0x20) != 0 )
  {
    *(_QWORD *)&v30.Data1 = *((int *)v9 + 305);
    v2 = BasicXmlParser::WriteSingleNode(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8CloudRemediationFixTag,
           v7,
           v8,
           0,
           v29,
           (unsigned __int64 *)&v30.Data1);
    if ( v2 < 0 )
    {
      v3 = L"failed to write single node";
      v4 = 3191;
      goto LABEL_71;
    }
  }
  else
  {
    v2 = BasicXmlParser::WriteSingleNode(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8CloudRemediationFixTag,
           v7,
           v8,
           L"default",
           v29,
           0);
    if ( v2 < 0 )
    {
      v3 = L"failed to write single node";
      v4 = 3196;
      goto LABEL_71;
    }
  }
  v2 = BasicXmlParser::WriteEOLWithIndent((BasicXmlParser *)this);
  if ( v2 < 0 )
  {
    v3 = L"failed to write EOL";
    v4 = 3198;
    goto LABEL_71;
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, void *))(*(_QWORD *)this[5] + 40LL))(
         this[5],
         0,
         &SettingXmlParser::Utf8AutoRemediationTag);
  if ( v2 < 0 )
  {
    v3 = L"failed to begin open element";
    v4 = 3201;
    goto LABEL_71;
  }
  v11 = this[8];
  if ( (v11[614] & 2) != 0 )
  {
    *(_QWORD *)&v30.Data1 = *((int *)v11 + 304);
    v2 = BasicXmlParser::WriteAttribute(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&BasicXmlParser::Utf8StateAttrTag,
           v10,
           0,
           v26,
           (unsigned __int64 *)&v30.Data1);
    if ( v2 < 0 )
    {
      v3 = L"failed to write AutoRemediation State attribute";
      v4 = 3208;
      goto LABEL_71;
    }
  }
  else
  {
    v2 = BasicXmlParser::WriteAttribute(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&BasicXmlParser::Utf8StateAttrTag,
           v10,
           L"default",
           v26,
           0);
    if ( v2 < 0 )
    {
      v3 = L"failed to write AutoRemediation State attribute";
      v4 = 3213;
      goto LABEL_71;
    }
  }
  v13 = this[8];
  if ( (v13[614] & 8) != 0 )
  {
    *(_QWORD *)&v30.Data1 = *((unsigned int *)v13 + 302);
    v2 = BasicXmlParser::WriteAttribute(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8TotalWaitTimeAttrTag,
           v12,
           0,
           v27,
           (unsigned __int64 *)&v30.Data1);
    if ( v2 < 0 )
    {
      v3 = L"failed to write Total Wait Time attribute";
      v4 = 3221;
      goto LABEL_71;
    }
  }
  else
  {
    v2 = BasicXmlParser::WriteAttribute(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8TotalWaitTimeAttrTag,
           v12,
           L"default",
           v27,
           0);
    if ( v2 < 0 )
    {
      v3 = L"failed to write Total Wait Time attribute";
      v4 = 3226;
      goto LABEL_71;
    }
  }
  v15 = this[8];
  if ( (v15[614] & 0x10) != 0 )
  {
    *(_QWORD *)&v30.Data1 = *((unsigned int *)v15 + 303);
    v2 = BasicXmlParser::WriteAttribute(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8WaitIntervalAttrTag,
           v14,
           0,
           v28,
           (unsigned __int64 *)&v30.Data1);
    if ( v2 < 0 )
    {
      v3 = L"failed to write Wait Interval attribute";
      v4 = 3234;
      goto LABEL_71;
    }
  }
  else
  {
    v2 = BasicXmlParser::WriteAttribute(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8WaitIntervalAttrTag,
           v14,
           L"default",
           v28,
           0);
    if ( v2 < 0 )
    {
      v3 = L"failed to write Wait Interval attribute";
      v4 = 3239;
      goto LABEL_71;
    }
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)this[5] + 48LL))(this[5], 1);
  if ( v2 < 0 )
  {
    v3 = L"failed to end open element";
    v4 = 3243;
    goto LABEL_71;
  }
  v2 = BasicXmlParser::WriteEOLWithIndent((BasicXmlParser *)this);
  if ( v2 < 0 )
  {
    v3 = L"failed to write EOL";
    v4 = 3244;
    goto LABEL_71;
  }
  v18 = this[8];
  if ( (v18[614] & 4) != 0 )
  {
    *(_QWORD *)&v30.Data1 = *((int *)v18 + 306);
    v2 = BasicXmlParser::WriteSingleNode(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8HeadlessTag,
           v16,
           v17,
           0,
           v29,
           (unsigned __int64 *)&v30.Data1);
    if ( v2 < 0 )
    {
      v3 = L"failed to write Headless node";
      v4 = 3251;
      goto LABEL_71;
    }
  }
  else
  {
    v2 = BasicXmlParser::WriteSingleNode(
           (BasicXmlParser *)this,
           (const struct _LUTF8_STRING *)&SettingXmlParser::Utf8HeadlessTag,
           v16,
           v17,
           L"default",
           v29,
           0);
    if ( v2 < 0 )
    {
      v3 = L"failed to write Headless node";
      v4 = 3256;
      goto LABEL_71;
    }
  }
  v2 = BasicXmlParser::WriteEOL((BasicXmlParser *)this);
  if ( v2 < 0 )
  {
    v3 = L"failed to write EOL";
    v4 = 3258;
    goto LABEL_71;
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, void *))(*(_QWORD *)this[5] + 80LL))(
         this[5],
         0,
         &SettingXmlParser::Utf8ToplevelEntryTag);
  if ( v2 < 0 )
  {
    v3 = L"failed to close element";
    v4 = 3264;
    goto LABEL_71;
  }
  v2 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, __int128 *))(*(_QWORD *)this[7] + 16LL))(this[7], 0, &v31);
  if ( v2 < 0 )
  {
    v3 = L"failed to get data and reset";
    v4 = 3269;
    goto LABEL_71;
  }
  v21 = 0;
  if ( this[1] )
    v21 = BasicXmlParser::WriteXMLFile((BasicXmlParser *)this, (struct _LUTF8_STRING *)&v31);
  v22 = this[9];
  if ( (unsigned __int64)v22 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v20 = BasicXmlParser::WriteConsoleOutputW(v19, v22, (struct _LUTF8_STRING *)&v31);
    goto LABEL_76;
  }
LABEL_77:
  if ( v32 )
    RtlFreeLUtf8String(&v31);
  return v21;
}

```

## disassembly

```asm
0x180015800  mov     rax, rsp
0x180015803  push    rbp
0x180015804  push    rdi
0x180015805  push    r15
0x180015807  mov     rbp, rsp
0x18001580a  sub     rsp, 70h
0x18001580e  mov     qword ptr [rbp+var_30.Data4], 0FFFFFFFFFFFFFFFEh
0x180015816  mov     [rax+10h], rbx
0x18001581a  mov     [rax+18h], rsi
0x18001581e  mov     rax, cs:__security_cookie
0x180015825  xor     rax, rsp
0x180015828  mov     [rbp+var_8], rax
0x18001582c  mov     rsi, rcx
0x18001582f  xorps   xmm0, xmm0
0x180015832  xor     eax, eax
0x180015834  movups  [rbp+var_20], xmm0
0x180015838  mov     [rbp+var_10], rax
0x18001583c  call    ?WriteEOL@BasicXmlParser@@IEAAJXZ; BasicXmlParser::WriteEOL(void)
0x180015841  mov     ebx, eax
0x180015843  test    eax, eax
0x180015845  jns     short loc_18001585D
0x180015847  mov     edi, 2
0x18001584c  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x180015853  mov     eax, 0C53h
0x180015858  jmp     loc_180015E65
0x18001585d  mov     rcx, [rsi+28h]
0x180015861  mov     rax, [rcx]
0x180015864  lea     r8, ?Utf8ToplevelEntryTag@SettingXmlParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const SettingXmlParser::Utf8ToplevelEntryTag
0x18001586b  xor     edx, edx
0x18001586d  mov     rax, [rax+28h]
0x180015871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015876  mov     ebx, eax
0x180015878  test    eax, eax
0x18001587a  jns     short loc_180015892
0x18001587c  mov     edi, 2
0x180015881  lea     r8, aFailedToBeginO_1; "failed to begin open element"
0x180015888  mov     eax, 0C54h
0x18001588d  jmp     loc_180015E65
0x180015892  mov     rcx, [rsi+28h]
0x180015896  mov     rax, [rcx]
0x180015899  xor     edx, edx
0x18001589b  mov     rax, [rax+30h]
0x18001589f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158a4  mov     ebx, eax
0x1800158a6  test    eax, eax
0x1800158a8  jns     short loc_1800158C0
0x1800158aa  mov     edi, 2
0x1800158af  lea     r8, aFailedToEndOpe; "failed to end open element"
0x1800158b6  mov     eax, 0C55h
0x1800158bb  jmp     loc_180015E65
0x1800158c0  mov     rcx, rsi; this
0x1800158c3  call    ?WriteEOLWithIndent@BasicXmlParser@@IEAAJXZ; BasicXmlParser::WriteEOLWithIndent(void)
0x1800158c8  mov     ebx, eax
0x1800158ca  test    eax, eax
0x1800158cc  jns     short loc_1800158E4
0x1800158ce  mov     edi, 2
0x1800158d3  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x1800158da  mov     eax, 0C56h
0x1800158df  jmp     loc_180015E65
0x1800158e4  mov     rcx, [rsi+28h]
0x1800158e8  mov     rax, [rcx]
0x1800158eb  lea     r8, ?Utf8WifiCredentialTag@SettingXmlParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const SettingXmlParser::Utf8WifiCredentialTag
0x1800158f2  xor     edx, edx
0x1800158f4  mov     rax, [rax+28h]
0x1800158f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158fd  mov     ebx, eax
0x1800158ff  test    eax, eax
0x180015901  jns     short loc_180015919
0x180015903  mov     edi, 2
0x180015908  lea     r8, aFailedToBeginO_1; "failed to begin open element"
0x18001590f  mov     eax, 0C5Dh
0x180015914  jmp     loc_180015E65
0x180015919  mov     rcx, [rsi+28h]
0x18001591d  mov     rax, [rcx]
0x180015920  xor     edx, edx
0x180015922  mov     rax, [rax+30h]
0x180015926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001592b  mov     ebx, eax
0x18001592d  test    eax, eax
0x18001592f  jns     short loc_180015947
0x180015931  mov     edi, 2
0x180015936  lea     r8, aFailedToEndOpe; "failed to end open element"
0x18001593d  mov     eax, 0C5Eh
0x180015942  jmp     loc_180015E65
0x180015947  mov     rcx, rsi; this
0x18001594a  call    ?WriteEOLWithIndent@BasicXmlParser@@IEAAJXZ; BasicXmlParser::WriteEOLWithIndent(void)
0x18001594f  mov     ebx, eax
0x180015951  test    eax, eax
0x180015953  jns     short loc_18001596B
0x180015955  mov     edi, 2
0x18001595a  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x180015961  mov     eax, 0C5Fh
0x180015966  jmp     loc_180015E65
0x18001596b  mov     rax, [rsi+40h]
0x18001596f  test    byte ptr [rax+4CCh], 1
0x180015976  jz      loc_180015AA1
0x18001597c  mov     rcx, rsi; this
0x18001597f  call    ?WriteIndent@BasicXmlParser@@IEAAJXZ; BasicXmlParser::WriteIndent(void)
0x180015984  mov     ebx, eax
0x180015986  test    eax, eax
0x180015988  jns     short loc_1800159A0
0x18001598a  mov     edi, 2
0x18001598f  lea     r8, aFailedToWriteI_2; "failed to write Indent"
0x180015996  mov     eax, 0C64h
0x18001599b  jmp     loc_180015E65
0x1800159a0  mov     rcx, [rsi+28h]
0x1800159a4  mov     rax, [rcx]
0x1800159a7  lea     r8, ?Utf8WifiTag@SettingXmlParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const SettingXmlParser::Utf8WifiTag
0x1800159ae  xor     edx, edx
0x1800159b0  mov     rax, [rax+28h]
0x1800159b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159b9  mov     ebx, eax
0x1800159bb  test    eax, eax
0x1800159bd  jns     short loc_1800159D5
0x1800159bf  mov     edi, 2
0x1800159c4  lea     r8, aFailedToBeginO_1; "failed to begin open element"
0x1800159cb  mov     eax, 0C65h
0x1800159d0  jmp     loc_180015E65
0x1800159d5  mov     [rsp+70h+var_48], 0; unsigned __int64 *
0x1800159de  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800159e2  lea     rdx, ?Utf8WifiSsidAttrTag@SettingXmlParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x1800159e9  mov     rcx, rsi; this
0x1800159ec  call    ?WriteAttribute@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x1800159f1  mov     ebx, eax
0x1800159f3  test    eax, eax
0x1800159f5  jns     short loc_180015A0D
0x1800159f7  mov     edi, 2
0x1800159fc  lea     r8, aFailedToWriteW_1; "failed to write wifi SSID attribute"
0x180015a03  mov     eax, 0C67h
0x180015a08  jmp     loc_180015E65
0x180015a0d  mov     r9, [rsi+40h]
0x180015a11  add     r9, 25Ch; unsigned __int16 *
0x180015a18  mov     [rsp+70h+var_48], 0; unsigned __int64 *
0x180015a21  lea     rdx, ?Utf8WifiPasswordAttrTag@SettingXmlParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180015a28  mov     rcx, rsi; this
0x180015a2b  call    ?WriteAttribute@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180015a30  mov     ebx, eax
0x180015a32  test    eax, eax
0x180015a34  jns     short loc_180015A4C
0x180015a36  mov     edi, 2
0x180015a3b  lea     r8, aFailedToWriteT; "failed to write Total Wait Time attribu"...
0x180015a42  mov     eax, 0C69h
0x180015a47  jmp     loc_180015E65
0x180015a4c  mov     rcx, [rsi+28h]
0x180015a50  mov     rax, [rcx]
0x180015a53  mov     edx, 1
0x180015a58  mov     rax, [rax+30h]
0x180015a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a61  mov     ebx, eax
0x180015a63  test    eax, eax
0x180015a65  jns     short loc_180015A7D
0x180015a67  mov     edi, 2
0x180015a6c  lea     r8, aFailedToEndOpe; "failed to end open element"
0x180015a73  mov     eax, 0C6Ah
0x180015a78  jmp     loc_180015E65
0x180015a7d  mov     rcx, rsi; this
0x180015a80  call    ?WriteEOLWithIndent@BasicXmlParser@@IEAAJXZ; BasicXmlParser::WriteEOLWithIndent(void)
0x180015a85  mov     ebx, eax
0x180015a87  test    eax, eax
0x180015a89  jns     short loc_180015AA1
0x180015a8b  mov     edi, 2
0x180015a90  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x180015a97  mov     eax, 0C6Bh
0x180015a9c  jmp     loc_180015E65
0x180015aa1  mov     rcx, [rsi+28h]
0x180015aa5  mov     rax, [rcx]
0x180015aa8  lea     r8, ?Utf8WifiCredentialTag@SettingXmlParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const SettingXmlParser::Utf8WifiCredentialTag
0x180015aaf  xor     edx, edx
0x180015ab1  mov     rax, [rax+50h]
0x180015ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aba  mov     ebx, eax
0x180015abc  test    eax, eax
0x180015abe  jns     short loc_180015AD6
0x180015ac0  mov     edi, 2
0x180015ac5  lea     r8, aFailedToCloseE; "failed to close element"
0x180015acc  mov     eax, 0C6Fh
0x180015ad1  jmp     loc_180015E65
0x180015ad6  mov     rcx, rsi; this
0x180015ad9  call    ?WriteEOLWithIndent@BasicXmlParser@@IEAAJXZ; BasicXmlParser::WriteEOLWithIndent(void)
0x180015ade  mov     ebx, eax
0x180015ae0  test    eax, eax
0x180015ae2  jns     short loc_180015AFA
0x180015ae4  mov     edi, 2
0x180015ae9  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x180015af0  mov     eax, 0C70h
0x180015af5  jmp     loc_180015E65
0x180015afa  mov     rax, [rsi+40h]
0x180015afe  lea     r15, aDefault; "default"
0x180015b05  lea     rdx, ?Utf8CloudRemediationFixTag@SettingXmlParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180015b0c  mov     rcx, rsi; this
0x180015b0f  test    byte ptr [rax+4CCh], 20h
0x180015b16  jz      short loc_180015B56
0x180015b18  movsxd  rax, dword ptr [rax+4C4h]
0x180015b1f  mov     qword ptr [rbp+var_30.Data1], rax
0x180015b23  lea     rax, [rbp+var_30]
0x180015b27  mov     [rsp+70h+var_40], rax; unsigned __int64 *
0x180015b2c  mov     [rsp+70h+var_50], 0; struct _GUID *
0x180015b35  call    ?WriteSingleNode@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@00PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteSingleNode(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180015b3a  mov     ebx, eax
0x180015b3c  test    eax, eax
0x180015b3e  jns     short loc_180015B85
0x180015b40  mov     edi, 2
0x180015b45  lea     r8, aFailedToWriteS_6; "failed to write single node"
0x180015b4c  mov     eax, 0C77h
0x180015b51  jmp     loc_180015E65
0x180015b56  mov     [rsp+70h+var_40], 0; unsigned __int64 *
0x180015b5f  mov     [rsp+70h+var_50], r15; unsigned __int16 *
0x180015b64  call    ?WriteSingleNode@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@00PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteSingleNode(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180015b69  mov     ebx, eax
0x180015b6b  test    eax, eax
0x180015b6d  jns     short loc_180015B85
0x180015b6f  mov     edi, 2
0x180015b74  lea     r8, aFailedToWriteS_6; "failed to write single node"
0x180015b7b  mov     eax, 0C7Ch
0x180015b80  jmp     loc_180015E65
0x180015b85  mov     rcx, rsi; this
0x180015b88  call    ?WriteEOLWithIndent@BasicXmlParser@@IEAAJXZ; BasicXmlParser::WriteEOLWithIndent(void)
0x180015b8d  mov     ebx, eax
0x180015b8f  test    eax, eax
0x180015b91  jns     short loc_180015BA9
0x180015b93  mov     edi, 2
0x180015b98  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x180015b9f  mov     eax, 0C7Eh
0x180015ba4  jmp     loc_180015E65
0x180015ba9  mov     rcx, [rsi+28h]
0x180015bad  mov     rax, [rcx]
0x180015bb0  lea     r8, ?Utf8AutoRemediationTag@SettingXmlParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const SettingXmlParser::Utf8AutoRemediationTag
0x180015bb7  xor     edx, edx
0x180015bb9  mov     rax, [rax+28h]
0x180015bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bc2  mov     ebx, eax
0x180015bc4  mov     edi, 2
0x180015bc9  test    eax, eax
0x180015bcb  jns     short loc_180015BDE
0x180015bcd  lea     r8, aFailedToBeginO_1; "failed to begin open element"
0x180015bd4  mov     eax, 0C81h
0x180015bd9  jmp     loc_180015E65
0x180015bde  mov     rax, [rsi+40h]
0x180015be2  lea     rdx, ?Utf8StateAttrTag@BasicXmlParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180015be9  mov     rcx, rsi; this
0x180015bec  test    [rax+4CCh], dil
0x180015bf3  jz      short loc_180015C28
0x180015bf5  movsxd  rax, dword ptr [rax+4C0h]
0x180015bfc  mov     qword ptr [rbp+var_30.Data1], rax
0x180015c00  lea     rax, [rbp+var_30]
0x180015c04  mov     [rsp+70h+var_48], rax; unsigned __int64 *
0x180015c09  xor     r9d, r9d; unsigned __int16 *
0x180015c0c  call    ?WriteAttribute@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180015c11  mov     ebx, eax
0x180015c13  test    eax, eax
0x180015c15  jns     short loc_180015C50
0x180015c17  lea     r8, aFailedToWriteA; "failed to write AutoRemediation State a"...
0x180015c1e  mov     eax, 0C88h
0x180015c23  jmp     loc_180015E65
0x180015c28  mov     [rsp+70h+var_48], 0; unsigned __int64 *
0x180015c31  mov     r9, r15; unsigned __int16 *
0x180015c34  call    ?WriteAttribute@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180015c39  mov     ebx, eax
0x180015c3b  test    eax, eax
0x180015c3d  jns     short loc_180015C50
0x180015c3f  lea     r8, aFailedToWriteA; "failed to write AutoRemediation State a"...
0x180015c46  mov     eax, 0C8Dh
0x180015c4b  jmp     loc_180015E65
0x180015c50  mov     rax, [rsi+40h]
0x180015c54  lea     rdx, ?Utf8TotalWaitTimeAttrTag@SettingXmlParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180015c5b  mov     rcx, rsi; this
0x180015c5e  test    byte ptr [rax+4CCh], 8
0x180015c65  jz      short loc_180015C99
0x180015c67  mov     eax, [rax+4B8h]
0x180015c6d  mov     qword ptr [rbp+var_30.Data1], rax
0x180015c71  lea     rax, [rbp+var_30]
0x180015c75  mov     [rsp+70h+var_48], rax; unsigned __int64 *
0x180015c7a  xor     r9d, r9d; unsigned __int16 *
0x180015c7d  call    ?WriteAttribute@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180015c82  mov     ebx, eax
0x180015c84  test    eax, eax
0x180015c86  jns     short loc_180015CC1
0x180015c88  lea     r8, aFailedToWriteT; "failed to write Total Wait Time attribu"...
0x180015c8f  mov     eax, 0C95h
0x180015c94  jmp     loc_180015E65
0x180015c99  mov     [rsp+70h+var_48], 0; unsigned __int64 *
0x180015ca2  mov     r9, r15; unsigned __int16 *
0x180015ca5  call    ?WriteAttribute@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180015caa  mov     ebx, eax
0x180015cac  test    eax, eax
0x180015cae  jns     short loc_180015CC1
0x180015cb0  lea     r8, aFailedToWriteT; "failed to write Total Wait Time attribu"...
0x180015cb7  mov     eax, 0C9Ah
0x180015cbc  jmp     loc_180015E65
0x180015cc1  mov     rax, [rsi+40h]
0x180015cc5  lea     rdx, ?Utf8WaitIntervalAttrTag@SettingXmlParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180015ccc  mov     rcx, rsi; this
0x180015ccf  test    byte ptr [rax+4CCh], 10h
0x180015cd6  jz      short loc_180015D0A
0x180015cd8  mov     eax, [rax+4BCh]
0x180015cde  mov     qword ptr [rbp+var_30.Data1], rax
0x180015ce2  lea     rax, [rbp+var_30]
0x180015ce6  mov     [rsp+70h+var_48], rax; struct _GUID *
0x180015ceb  xor     r9d, r9d; unsigned __int16 *
0x180015cee  call    ?WriteAttribute@BasicXmlParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; BasicXmlParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
  ... truncated ...
```
