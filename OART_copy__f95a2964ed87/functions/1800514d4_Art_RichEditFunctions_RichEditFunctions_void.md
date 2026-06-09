# Art::RichEditFunctions::RichEditFunctions(void)

- ea: `0x1800514d4`
- end: `0x180051834`
- name: `??0RichEditFunctions@Art@@QEAA@XZ`
- size: `864`
- prototype: `__int64 __fastcall(Art::RichEditFunctions *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180051460`

## callees

- `0x1800514d4`
- `0x1802771a0`
- `0x180279050`
- `0x18097912c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180051578`
- `KERNEL32!GetProcAddress` at `0x1800515a2`
- `KERNEL32!GetProcAddress` at `0x1800515cd`
- `KERNEL32!GetProcAddress` at `0x1800515f8`
- `KERNEL32!GetProcAddress` at `0x180051623`
- `KERNEL32!GetProcAddress` at `0x18005164e`
- `KERNEL32!GetProcAddress` at `0x180051679`
- `KERNEL32!GetProcAddress` at `0x1800516a4`
- `KERNEL32!GetProcAddress` at `0x1800516cf`
- `KERNEL32!GetProcAddress` at `0x1800516fa`
- `KERNEL32!GetProcAddress` at `0x180051725`
- `KERNEL32!GetProcAddress` at `0x180051739`
- `KERNEL32!GetProcAddress` at `0x180051750`
- `KERNEL32!GetProcAddress` at `0x18005177b`
- `KERNEL32!GetProcAddress` at `0x180051800`
- `KERNEL32!GetProcAddress` at `0x180051578`
- `KERNEL32!GetProcAddress` at `0x1800515a2`
- `KERNEL32!GetProcAddress` at `0x1800515cd`
- `KERNEL32!GetProcAddress` at `0x1800515f8`
- `KERNEL32!GetProcAddress` at `0x180051623`
- `KERNEL32!GetProcAddress` at `0x18005164e`
- `KERNEL32!GetProcAddress` at `0x180051679`
- `KERNEL32!GetProcAddress` at `0x1800516a4`
- `KERNEL32!GetProcAddress` at `0x1800516cf`
- `KERNEL32!GetProcAddress` at `0x1800516fa`
- `KERNEL32!GetProcAddress` at `0x180051725`
- `KERNEL32!GetProcAddress` at `0x180051739`
- `KERNEL32!GetProcAddress` at `0x180051750`
- `KERNEL32!GetProcAddress` at `0x18005177b`
- `KERNEL32!GetProcAddress` at `0x180051800`
- `Mso30Win32Client!__imp_?MsoLoadRiched20@@YAPEAUHINSTANCE__@@XZ` at `0x18005154e`
- `Mso30Win32Client!__imp_?MsoLoadRiched20@@YAPEAUHINSTANCE__@@XZ` at `0x18005154e`

## string_xrefs

- `0x18005169a`: `WriteMathPrSax`
- `0x18005156e`: `CreateTextBoxLayout`
- `0x18005171b`: `FCreateMathFromLaTeX`
- `0x180051619`: `CreateMathXmlHandler`
- `0x18005160c`: `MathTranslate is not found in RichEdit dll.`
- `0x1800515e1`: `MathBuildDown is not found in RichEdit dll.`
- `0x180051662`: `ProcessMathMenuID is not found in RichEdit dll.`
- `0x180051637`: `CreateMathXmlHandler is not found in RichEdit dll.`
- `0x180051561`: `MsoLoadModule failed to load RichEdit dll.`
- `0x180051814`: `ConvertEquationFromStorage is not found in RichEdit dll.`
- `0x1800515b6`: `MathBuildUp is not found in RichEdit dll.`
- `0x18005158b`: `CreateTextBoxLayout is not found in RichEdit dll.`
- `0x180051764`: `RegisterLanguageTag is not found in RichEdit dll.`
- `0x18005178f`: `GetLcidFromLang is not found in RichEdit dll.`
- `0x1800516b8`: `WriteMathPrSax is not found in RichEdit dll.`
- `0x18005168d`: `GetMathContextMenuItems is not found in RichEdit dll.`
- `0x18005170e`: `ConvertEquationFromStdVector is not found in RichEdit dll.`
- `0x1800516e3`: `GetMathSpeechText is not found in RichEdit dll.`

## pseudocode

```c
Art::RichEditFunctions *__fastcall Art::RichEditFunctions::RichEditFunctions(Art::RichEditFunctions *this)
{
  struct Art::IAppHost *AppHost; // rax
  HMODULE Riched20; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  Art *v17; // rcx
  struct Art::IAppHost *v18; // rax
  Art *v19; // rcx
  struct Art::IAppHost *v20; // rax
  FARPROC v21; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  AppHost = Art::GetAppHost(this);
  (*(void (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)AppHost + 200LL))(AppHost, 154);
  Riched20 = MsoLoadRiched20();
  v4 = Riched20;
  if ( !Riched20 )
  {
    Art::CTextLayoutException::ThrowTag(L"MsoLoadModule failed to load RichEdit dll.", 0x3938D6u);
    __debugbreak();
  }
  ProcAddress = GetProcAddress(Riched20, "CreateTextBoxLayout");
  *(_QWORD *)this = ProcAddress;
  if ( !ProcAddress )
  {
    Art::CTextLayoutException::ThrowTag(L"CreateTextBoxLayout is not found in RichEdit dll.", 0x3938D7u);
    __debugbreak();
  }
  v6 = GetProcAddress(v4, "MathBuildUp");
  *((_QWORD *)this + 1) = v6;
  if ( !v6 )
  {
    Art::CTextLayoutException::ThrowTag(L"MathBuildUp is not found in RichEdit dll.", 0x3938D8u);
    __debugbreak();
  }
  v7 = GetProcAddress(v4, "MathBuildDown");
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
  {
    Art::CTextLayoutException::ThrowTag(L"MathBuildDown is not found in RichEdit dll.", 0x3938D9u);
    __debugbreak();
  }
  v8 = GetProcAddress(v4, "MathTranslate");
  *((_QWORD *)this + 3) = v8;
  if ( !v8 )
  {
    Art::CTextLayoutException::ThrowTag(L"MathTranslate is not found in RichEdit dll.", 0x3938DAu);
    __debugbreak();
  }
  v9 = GetProcAddress(v4, "CreateMathXmlHandler");
  *((_QWORD *)this + 4) = v9;
  if ( !v9 )
  {
    Art::CTextLayoutException::ThrowTag(L"CreateMathXmlHandler is not found in RichEdit dll.", 0x3938DBu);
    __debugbreak();
  }
  v10 = GetProcAddress(v4, "ProcessMathMenuID");
  *((_QWORD *)this + 5) = v10;
  if ( !v10 )
  {
    Art::CTextLayoutException::ThrowTag(L"ProcessMathMenuID is not found in RichEdit dll.", 0x3938DCu);
    __debugbreak();
  }
  v11 = GetProcAddress(v4, "GetMathContextMenuItems");
  *((_QWORD *)this + 6) = v11;
  if ( !v11 )
  {
    Art::CTextLayoutException::ThrowTag(L"GetMathContextMenuItems is not found in RichEdit dll.", 0x3938DDu);
    __debugbreak();
  }
  v12 = GetProcAddress(v4, "WriteMathPrSax");
  *((_QWORD *)this + 7) = v12;
  if ( !v12 )
  {
    Art::CTextLayoutException::ThrowTag(L"WriteMathPrSax is not found in RichEdit dll.", 0x3938DEu);
    __debugbreak();
  }
  v13 = GetProcAddress(v4, "GetMathSpeechText");
  *((_QWORD *)this + 8) = v13;
  if ( !v13 )
  {
    Art::CTextLayoutException::ThrowTag(L"GetMathSpeechText is not found in RichEdit dll.", 0x12DE1E2u);
    __debugbreak();
  }
  v14 = GetProcAddress(v4, "ConvertEquationFromStdVector");
  *((_QWORD *)this + 10) = v14;
  if ( !v14 )
  {
    Art::CTextLayoutException::ThrowTag(L"ConvertEquationFromStdVector is not found in RichEdit dll.", 0x24D0593u);
    __debugbreak();
  }
  *((_QWORD *)this + 15) = GetProcAddress(v4, "FCreateMathFromLaTeX");
  *((_QWORD *)this + 16) = GetProcAddress(v4, "FNormalizeLaTeX");
  v15 = GetProcAddress(v4, "RegisterLanguageTag");
  *((_QWORD *)this + 11) = v15;
  if ( !v15 )
  {
    Art::CTextLayoutException::ThrowTag(L"RegisterLanguageTag is not found in RichEdit dll.", 0x2375E1C9u);
    __debugbreak();
  }
  v16 = GetProcAddress(v4, "GetLcidFromLang");
  *((_QWORD *)this + 12) = v16;
  if ( !v16 )
  {
    Art::CTextLayoutException::ThrowTag(L"GetLcidFromLang is not found in RichEdit dll.", 0x2375E1C8u);
    __debugbreak();
  }
  v18 = Art::GetAppHost(v17);
  if ( (*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)v18 + 200LL))(v18, 154) )
  {
    Art::CTextLayoutException::ThrowTag(L"Failed to set language tag for session", 0x1E28C311u);
    __debugbreak();
  }
  v20 = Art::GetAppHost(v19);
  if ( (*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)v20 + 200LL))(v20, 114) )
  {
    v21 = GetProcAddress(v4, "ConvertEquationFromStorage");
    *((_QWORD *)this + 9) = v21;
    if ( !v21 )
    {
      Art::CTextLayoutException::ThrowTag(L"ConvertEquationFromStorage is not found in RichEdit dll.", 0x23891D4u);
      __debugbreak();
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800514d4  mov     [rsp+arg_0], rbx
0x1800514d9  mov     [rsp+arg_8], rsi
0x1800514de  push    rdi
0x1800514df  sub     rsp, 20h
0x1800514e3  xor     esi, esi
0x1800514e5  mov     rbx, rcx
0x1800514e8  mov     [rcx], rsi
0x1800514eb  mov     [rcx+8], rsi
0x1800514ef  mov     [rcx+10h], rsi
0x1800514f3  mov     [rcx+18h], rsi
0x1800514f7  mov     [rcx+20h], rsi
0x1800514fb  mov     [rcx+28h], rsi
0x1800514ff  mov     [rcx+30h], rsi
0x180051503  mov     [rcx+38h], rsi
0x180051507  mov     [rcx+40h], rsi
0x18005150b  mov     [rcx+48h], rsi
0x18005150f  mov     [rcx+50h], rsi
0x180051513  mov     [rcx+58h], rsi
0x180051517  mov     [rcx+60h], rsi
0x18005151b  mov     [rcx+68h], rsi
0x18005151f  mov     [rcx+70h], rsi
0x180051523  mov     [rcx+78h], rsi
0x180051527  mov     [rcx+80h], rsi
0x18005152e  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x180051533  mov     r8, rax
0x180051536  mov     edx, 9Ah
0x18005153b  mov     rcx, [rax]
0x18005153e  mov     rax, [rcx+0C8h]
0x180051545  mov     rcx, r8
0x180051548  call    cs:__guard_dispatch_icall_fptr
0x18005154e  call    cs:__imp_?MsoLoadRiched20@@YAPEAUHINSTANCE__@@XZ; MsoLoadRiched20(void)
0x180051554  mov     rdi, rax
0x180051557  test    rax, rax
0x18005155a  jnz     short loc_18005156E
0x18005155c  mov     edx, 3938D6h; unsigned int
0x180051561  lea     rcx, aMsoloadmoduleF; "MsoLoadModule failed to load RichEdit d"...
0x180051568  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x18005156d  int     3; Trap to Debugger
0x18005156e  lea     rdx, aCreatetextboxl_0; "CreateTextBoxLayout"
0x180051575  mov     rcx, rdi; hModule
0x180051578  call    cs:__imp_GetProcAddress
0x18005157e  mov     [rbx], rax
0x180051581  test    rax, rax
0x180051584  jnz     short loc_180051598
0x180051586  mov     edx, 3938D7h; unsigned int
0x18005158b  lea     rcx, aCreatetextboxl; "CreateTextBoxLayout is not found in Ric"...
0x180051592  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180051597  int     3; Trap to Debugger
0x180051598  lea     rdx, aMathbuildup; "MathBuildUp"
0x18005159f  mov     rcx, rdi; hModule
0x1800515a2  call    cs:__imp_GetProcAddress
0x1800515a8  mov     [rbx+8], rax
0x1800515ac  test    rax, rax
0x1800515af  jnz     short loc_1800515C3
0x1800515b1  mov     edx, 3938D8h; unsigned int
0x1800515b6  lea     rcx, aMathbuildupIsN; "MathBuildUp is not found in RichEdit dl"...
0x1800515bd  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1800515c2  int     3; Trap to Debugger
0x1800515c3  lea     rdx, aMathbuilddown; "MathBuildDown"
0x1800515ca  mov     rcx, rdi; hModule
0x1800515cd  call    cs:__imp_GetProcAddress
0x1800515d3  mov     [rbx+10h], rax
0x1800515d7  test    rax, rax
0x1800515da  jnz     short loc_1800515EE
0x1800515dc  mov     edx, 3938D9h; unsigned int
0x1800515e1  lea     rcx, aMathbuilddownI; "MathBuildDown is not found in RichEdit "...
0x1800515e8  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1800515ed  int     3; Trap to Debugger
0x1800515ee  lea     rdx, aMathtranslate; "MathTranslate"
0x1800515f5  mov     rcx, rdi; hModule
0x1800515f8  call    cs:__imp_GetProcAddress
0x1800515fe  mov     [rbx+18h], rax
0x180051602  test    rax, rax
0x180051605  jnz     short loc_180051619
0x180051607  mov     edx, 3938DAh; unsigned int
0x18005160c  lea     rcx, aMathtranslateI; "MathTranslate is not found in RichEdit "...
0x180051613  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180051618  int     3; Trap to Debugger
0x180051619  lea     rdx, aCreatemathxmlh_0; "CreateMathXmlHandler"
0x180051620  mov     rcx, rdi; hModule
0x180051623  call    cs:__imp_GetProcAddress
0x180051629  mov     [rbx+20h], rax
0x18005162d  test    rax, rax
0x180051630  jnz     short loc_180051644
0x180051632  mov     edx, 3938DBh; unsigned int
0x180051637  lea     rcx, aCreatemathxmlh; "CreateMathXmlHandler is not found in Ri"...
0x18005163e  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180051643  int     3; Trap to Debugger
0x180051644  lea     rdx, aProcessmathmen_0; "ProcessMathMenuID"
0x18005164b  mov     rcx, rdi; hModule
0x18005164e  call    cs:__imp_GetProcAddress
0x180051654  mov     [rbx+28h], rax
0x180051658  test    rax, rax
0x18005165b  jnz     short loc_18005166F
0x18005165d  mov     edx, 3938DCh; unsigned int
0x180051662  lea     rcx, aProcessmathmen; "ProcessMathMenuID is not found in RichE"...
0x180051669  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x18005166e  int     3; Trap to Debugger
0x18005166f  lea     rdx, aGetmathcontext_0; "GetMathContextMenuItems"
0x180051676  mov     rcx, rdi; hModule
0x180051679  call    cs:__imp_GetProcAddress
0x18005167f  mov     [rbx+30h], rax
0x180051683  test    rax, rax
0x180051686  jnz     short loc_18005169A
0x180051688  mov     edx, 3938DDh; unsigned int
0x18005168d  lea     rcx, aGetmathcontext; "GetMathContextMenuItems is not found in"...
0x180051694  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180051699  int     3; Trap to Debugger
0x18005169a  lea     rdx, aWritemathprsax_0; "WriteMathPrSax"
0x1800516a1  mov     rcx, rdi; hModule
0x1800516a4  call    cs:__imp_GetProcAddress
0x1800516aa  mov     [rbx+38h], rax
0x1800516ae  test    rax, rax
0x1800516b1  jnz     short loc_1800516C5
0x1800516b3  mov     edx, 3938DEh; unsigned int
0x1800516b8  lea     rcx, aWritemathprsax; "WriteMathPrSax is not found in RichEdit"...
0x1800516bf  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1800516c4  int     3; Trap to Debugger
0x1800516c5  lea     rdx, aGetmathspeecht; "GetMathSpeechText"
0x1800516cc  mov     rcx, rdi; hModule
0x1800516cf  call    cs:__imp_GetProcAddress
0x1800516d5  mov     [rbx+40h], rax
0x1800516d9  test    rax, rax
0x1800516dc  jnz     short loc_1800516F0
0x1800516de  mov     edx, 12DE1E2h; unsigned int
0x1800516e3  lea     rcx, aGetmathspeecht_0; "GetMathSpeechText is not found in RichE"...
0x1800516ea  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1800516ef  int     3; Trap to Debugger
0x1800516f0  lea     rdx, aConvertequatio; "ConvertEquationFromStdVector"
0x1800516f7  mov     rcx, rdi; hModule
0x1800516fa  call    cs:__imp_GetProcAddress
0x180051700  mov     [rbx+50h], rax
0x180051704  test    rax, rax
0x180051707  jnz     short loc_18005171B
0x180051709  mov     edx, 24D0593h; unsigned int
0x18005170e  lea     rcx, aConvertequatio_0; "ConvertEquationFromStdVector is not fou"...
0x180051715  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x18005171a  int     3; Trap to Debugger
0x18005171b  lea     rdx, aFcreatemathfro; "FCreateMathFromLaTeX"
0x180051722  mov     rcx, rdi; hModule
0x180051725  call    cs:__imp_GetProcAddress
0x18005172b  lea     rdx, aFnormalizelate; "FNormalizeLaTeX"
0x180051732  mov     rcx, rdi; hModule
0x180051735  mov     [rbx+78h], rax
0x180051739  call    cs:__imp_GetProcAddress
0x18005173f  lea     rdx, aRegisterlangua; "RegisterLanguageTag"
0x180051746  mov     rcx, rdi; hModule
0x180051749  mov     [rbx+80h], rax
0x180051750  call    cs:__imp_GetProcAddress
0x180051756  mov     [rbx+58h], rax
0x18005175a  test    rax, rax
0x18005175d  jnz     short loc_180051771
0x18005175f  mov     edx, 2375E1C9h; unsigned int
0x180051764  lea     rcx, aRegisterlangua_0; "RegisterLanguageTag is not found in Ric"...
0x18005176b  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180051770  int     3; Trap to Debugger
0x180051771  lea     rdx, aGetlcidfromlan; "GetLcidFromLang"
0x180051778  mov     rcx, rdi; hModule
0x18005177b  call    cs:__imp_GetProcAddress
0x180051781  mov     [rbx+60h], rax
0x180051785  test    rax, rax
0x180051788  jnz     short loc_18005179C
0x18005178a  mov     edx, 2375E1C8h; unsigned int
0x18005178f  lea     rcx, aGetlcidfromlan_0; "GetLcidFromLang is not found in RichEdi"...
0x180051796  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x18005179b  int     3; Trap to Debugger
0x18005179c  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x1800517a1  mov     r8, rax
0x1800517a4  mov     edx, 9Ah
0x1800517a9  mov     rcx, [rax]
0x1800517ac  mov     rax, [rcx+0C8h]
0x1800517b3  mov     rcx, r8
0x1800517b6  call    cs:__guard_dispatch_icall_fptr
0x1800517bc  test    al, al
0x1800517be  jz      short loc_1800517D2
0x1800517c0  mov     edx, 1E28C311h; unsigned int
0x1800517c5  lea     rcx, aFailedToSetLan; "Failed to set language tag for session"
0x1800517cc  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1800517d1  int     3; Trap to Debugger
0x1800517d2  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x1800517d7  mov     r8, rax
0x1800517da  mov     edx, 72h ; 'r'
0x1800517df  mov     rcx, [rax]
0x1800517e2  mov     rax, [rcx+0C8h]
0x1800517e9  mov     rcx, r8
0x1800517ec  call    cs:__guard_dispatch_icall_fptr
0x1800517f2  test    al, al
0x1800517f4  jz      short loc_180051821
0x1800517f6  lea     rdx, aConvertequatio_1; "ConvertEquationFromStorage"
0x1800517fd  mov     rcx, rdi; hModule
0x180051800  call    cs:__imp_GetProcAddress
0x180051806  mov     [rbx+48h], rax
0x18005180a  test    rax, rax
0x18005180d  jnz     short loc_180051821
0x18005180f  mov     edx, 23891D4h; unsigned int
0x180051814  lea     rcx, aConvertequatio_2; "ConvertEquationFromStorage is not found"...
0x18005181b  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180051820  int     3; Trap to Debugger
0x180051821  mov     rsi, [rsp+28h+arg_8]
0x180051826  mov     rax, rbx
0x180051829  mov     rbx, [rsp+28h+arg_0]
0x18005182e  add     rsp, 20h
0x180051832  pop     rdi
0x180051833  retn
```
