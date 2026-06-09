# Art::RichEditFunctions::RichEditFunctions(void)

- ea: `0x18066624c`
- end: `0x1806665ca`
- name: `??0RichEditFunctions@Art@@QEAA@XZ`
- size: `894`
- prototype: `__int64 __fastcall(Art::RichEditFunctions *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x18013b93c`

## callees

- `0x18006d0a0`
- `0x180071720`
- `0x18066624c`
- `0x18096d83c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1806662f7`
- `KERNEL32!GetProcAddress` at `0x180666321`
- `KERNEL32!GetProcAddress` at `0x18066634c`
- `KERNEL32!GetProcAddress` at `0x180666377`
- `KERNEL32!GetProcAddress` at `0x1806663a2`
- `KERNEL32!GetProcAddress` at `0x1806663cd`
- `KERNEL32!GetProcAddress` at `0x1806663f8`
- `KERNEL32!GetProcAddress` at `0x180666423`
- `KERNEL32!GetProcAddress` at `0x18066644e`
- `KERNEL32!GetProcAddress` at `0x180666479`
- `KERNEL32!GetProcAddress` at `0x1806664a4`
- `KERNEL32!GetProcAddress` at `0x1806664b8`
- `KERNEL32!GetProcAddress` at `0x1806664cf`
- `KERNEL32!GetProcAddress` at `0x1806664e6`
- `KERNEL32!GetProcAddress` at `0x180666511`
- `KERNEL32!GetProcAddress` at `0x180666596`
- `KERNEL32!GetProcAddress` at `0x1806662f7`
- `KERNEL32!GetProcAddress` at `0x180666321`
- `KERNEL32!GetProcAddress` at `0x18066634c`
- `KERNEL32!GetProcAddress` at `0x180666377`
- `KERNEL32!GetProcAddress` at `0x1806663a2`
- `KERNEL32!GetProcAddress` at `0x1806663cd`
- `KERNEL32!GetProcAddress` at `0x1806663f8`
- `KERNEL32!GetProcAddress` at `0x180666423`
- `KERNEL32!GetProcAddress` at `0x18066644e`
- `KERNEL32!GetProcAddress` at `0x180666479`
- `KERNEL32!GetProcAddress` at `0x1806664a4`
- `KERNEL32!GetProcAddress` at `0x1806664b8`
- `KERNEL32!GetProcAddress` at `0x1806664cf`
- `KERNEL32!GetProcAddress` at `0x1806664e6`
- `KERNEL32!GetProcAddress` at `0x180666511`
- `KERNEL32!GetProcAddress` at `0x180666596`
- `Mso30Win32Client!__imp_?MsoLoadRiched20@@YAPEAUHINSTANCE__@@XZ` at `0x1806662cd`
- `Mso30Win32Client!__imp_?MsoLoadRiched20@@YAPEAUHINSTANCE__@@XZ` at `0x1806662cd`

## string_xrefs

- `0x180666419`: `WriteMathPrSax`
- `0x1806662ed`: `CreateTextBoxLayout`
- `0x1806664be`: `FPreParseMathML`
- `0x18066649a`: `FCreateMathFromLaTeX`
- `0x180666398`: `CreateMathXmlHandler`
- `0x1806664fa`: `RegisterLanguageTag is not found in RichEdit dll.`
- `0x180666462`: `GetMathSpeechText is not found in RichEdit dll.`
- `0x18066648d`: `ConvertEquationFromStdVector is not found in RichEdit dll.`
- `0x18066640c`: `GetMathContextMenuItems is not found in RichEdit dll.`
- `0x180666437`: `WriteMathPrSax is not found in RichEdit dll.`
- `0x1806663b6`: `CreateMathXmlHandler is not found in RichEdit dll.`
- `0x1806663e1`: `ProcessMathMenuID is not found in RichEdit dll.`
- `0x180666525`: `GetLcidFromLang is not found in RichEdit dll.`
- `0x180666360`: `MathBuildDown is not found in RichEdit dll.`
- `0x18066638b`: `MathTranslate is not found in RichEdit dll.`
- `0x18066630a`: `CreateTextBoxLayout is not found in RichEdit dll.`
- `0x180666335`: `MathBuildUp is not found in RichEdit dll.`
- `0x1806665aa`: `ConvertEquationFromStorage is not found in RichEdit dll.`
- `0x1806662e0`: `MsoLoadModule failed to load RichEdit dll.`

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
  *((_QWORD *)this + 17) = 0;
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
  *((_QWORD *)this + 17) = GetProcAddress(v4, "FPreParseMathML");
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
0x18066624c  mov     [rsp+arg_0], rbx
0x180666251  mov     [rsp+arg_8], rsi
0x180666256  push    rdi
0x180666257  sub     rsp, 20h
0x18066625b  xor     esi, esi
0x18066625d  mov     rbx, rcx
0x180666260  mov     [rcx], rsi
0x180666263  mov     [rcx+8], rsi
0x180666267  mov     [rcx+10h], rsi
0x18066626b  mov     [rcx+18h], rsi
0x18066626f  mov     [rcx+20h], rsi
0x180666273  mov     [rcx+28h], rsi
0x180666277  mov     [rcx+30h], rsi
0x18066627b  mov     [rcx+38h], rsi
0x18066627f  mov     [rcx+40h], rsi
0x180666283  mov     [rcx+48h], rsi
0x180666287  mov     [rcx+50h], rsi
0x18066628b  mov     [rcx+58h], rsi
0x18066628f  mov     [rcx+60h], rsi
0x180666293  mov     [rcx+68h], rsi
0x180666297  mov     [rcx+70h], rsi
0x18066629b  mov     [rcx+78h], rsi
0x18066629f  mov     [rcx+80h], rsi
0x1806662a6  mov     [rcx+88h], rsi
0x1806662ad  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x1806662b2  mov     r8, rax
0x1806662b5  mov     edx, 9Ah
0x1806662ba  mov     rcx, [rax]
0x1806662bd  mov     rax, [rcx+0C8h]
0x1806662c4  mov     rcx, r8
0x1806662c7  call    cs:__guard_dispatch_icall_fptr
0x1806662cd  call    cs:__imp_?MsoLoadRiched20@@YAPEAUHINSTANCE__@@XZ; MsoLoadRiched20(void)
0x1806662d3  mov     rdi, rax
0x1806662d6  test    rax, rax
0x1806662d9  jnz     short loc_1806662ED
0x1806662db  mov     edx, 3938D6h; unsigned int
0x1806662e0  lea     rcx, aMsoloadmoduleF; "MsoLoadModule failed to load RichEdit d"...
0x1806662e7  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1806662ec  int     3; Trap to Debugger
0x1806662ed  lea     rdx, aCreatetextboxl_0; "CreateTextBoxLayout"
0x1806662f4  mov     rcx, rdi; hModule
0x1806662f7  call    cs:__imp_GetProcAddress
0x1806662fd  mov     [rbx], rax
0x180666300  test    rax, rax
0x180666303  jnz     short loc_180666317
0x180666305  mov     edx, 3938D7h; unsigned int
0x18066630a  lea     rcx, aCreatetextboxl; "CreateTextBoxLayout is not found in Ric"...
0x180666311  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666316  int     3; Trap to Debugger
0x180666317  lea     rdx, aMathbuildup; "MathBuildUp"
0x18066631e  mov     rcx, rdi; hModule
0x180666321  call    cs:__imp_GetProcAddress
0x180666327  mov     [rbx+8], rax
0x18066632b  test    rax, rax
0x18066632e  jnz     short loc_180666342
0x180666330  mov     edx, 3938D8h; unsigned int
0x180666335  lea     rcx, aMathbuildupIsN; "MathBuildUp is not found in RichEdit dl"...
0x18066633c  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666341  int     3; Trap to Debugger
0x180666342  lea     rdx, aMathbuilddown; "MathBuildDown"
0x180666349  mov     rcx, rdi; hModule
0x18066634c  call    cs:__imp_GetProcAddress
0x180666352  mov     [rbx+10h], rax
0x180666356  test    rax, rax
0x180666359  jnz     short loc_18066636D
0x18066635b  mov     edx, 3938D9h; unsigned int
0x180666360  lea     rcx, aMathbuilddownI; "MathBuildDown is not found in RichEdit "...
0x180666367  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x18066636c  int     3; Trap to Debugger
0x18066636d  lea     rdx, aMathtranslate; "MathTranslate"
0x180666374  mov     rcx, rdi; hModule
0x180666377  call    cs:__imp_GetProcAddress
0x18066637d  mov     [rbx+18h], rax
0x180666381  test    rax, rax
0x180666384  jnz     short loc_180666398
0x180666386  mov     edx, 3938DAh; unsigned int
0x18066638b  lea     rcx, aMathtranslateI; "MathTranslate is not found in RichEdit "...
0x180666392  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666397  int     3; Trap to Debugger
0x180666398  lea     rdx, aCreatemathxmlh_0; "CreateMathXmlHandler"
0x18066639f  mov     rcx, rdi; hModule
0x1806663a2  call    cs:__imp_GetProcAddress
0x1806663a8  mov     [rbx+20h], rax
0x1806663ac  test    rax, rax
0x1806663af  jnz     short loc_1806663C3
0x1806663b1  mov     edx, 3938DBh; unsigned int
0x1806663b6  lea     rcx, aCreatemathxmlh; "CreateMathXmlHandler is not found in Ri"...
0x1806663bd  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1806663c2  int     3; Trap to Debugger
0x1806663c3  lea     rdx, aProcessmathmen_0; "ProcessMathMenuID"
0x1806663ca  mov     rcx, rdi; hModule
0x1806663cd  call    cs:__imp_GetProcAddress
0x1806663d3  mov     [rbx+28h], rax
0x1806663d7  test    rax, rax
0x1806663da  jnz     short loc_1806663EE
0x1806663dc  mov     edx, 3938DCh; unsigned int
0x1806663e1  lea     rcx, aProcessmathmen; "ProcessMathMenuID is not found in RichE"...
0x1806663e8  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1806663ed  int     3; Trap to Debugger
0x1806663ee  lea     rdx, aGetmathcontext_0; "GetMathContextMenuItems"
0x1806663f5  mov     rcx, rdi; hModule
0x1806663f8  call    cs:__imp_GetProcAddress
0x1806663fe  mov     [rbx+30h], rax
0x180666402  test    rax, rax
0x180666405  jnz     short loc_180666419
0x180666407  mov     edx, 3938DDh; unsigned int
0x18066640c  lea     rcx, aGetmathcontext; "GetMathContextMenuItems is not found in"...
0x180666413  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666418  int     3; Trap to Debugger
0x180666419  lea     rdx, aWritemathprsax_0; "WriteMathPrSax"
0x180666420  mov     rcx, rdi; hModule
0x180666423  call    cs:__imp_GetProcAddress
0x180666429  mov     [rbx+38h], rax
0x18066642d  test    rax, rax
0x180666430  jnz     short loc_180666444
0x180666432  mov     edx, 3938DEh; unsigned int
0x180666437  lea     rcx, aWritemathprsax; "WriteMathPrSax is not found in RichEdit"...
0x18066643e  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666443  int     3; Trap to Debugger
0x180666444  lea     rdx, aGetmathspeecht; "GetMathSpeechText"
0x18066644b  mov     rcx, rdi; hModule
0x18066644e  call    cs:__imp_GetProcAddress
0x180666454  mov     [rbx+40h], rax
0x180666458  test    rax, rax
0x18066645b  jnz     short loc_18066646F
0x18066645d  mov     edx, 12DE1E2h; unsigned int
0x180666462  lea     rcx, aGetmathspeecht_0; "GetMathSpeechText is not found in RichE"...
0x180666469  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x18066646e  int     3; Trap to Debugger
0x18066646f  lea     rdx, aConvertequatio; "ConvertEquationFromStdVector"
0x180666476  mov     rcx, rdi; hModule
0x180666479  call    cs:__imp_GetProcAddress
0x18066647f  mov     [rbx+50h], rax
0x180666483  test    rax, rax
0x180666486  jnz     short loc_18066649A
0x180666488  mov     edx, 24D0593h; unsigned int
0x18066648d  lea     rcx, aConvertequatio_0; "ConvertEquationFromStdVector is not fou"...
0x180666494  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666499  int     3; Trap to Debugger
0x18066649a  lea     rdx, aFcreatemathfro; "FCreateMathFromLaTeX"
0x1806664a1  mov     rcx, rdi; hModule
0x1806664a4  call    cs:__imp_GetProcAddress
0x1806664aa  lea     rdx, aFnormalizelate; "FNormalizeLaTeX"
0x1806664b1  mov     rcx, rdi; hModule
0x1806664b4  mov     [rbx+78h], rax
0x1806664b8  call    cs:__imp_GetProcAddress
0x1806664be  lea     rdx, aFpreparsemathm; "FPreParseMathML"
0x1806664c5  mov     rcx, rdi; hModule
0x1806664c8  mov     [rbx+80h], rax
0x1806664cf  call    cs:__imp_GetProcAddress
0x1806664d5  lea     rdx, aRegisterlangua; "RegisterLanguageTag"
0x1806664dc  mov     rcx, rdi; hModule
0x1806664df  mov     [rbx+88h], rax
0x1806664e6  call    cs:__imp_GetProcAddress
0x1806664ec  mov     [rbx+58h], rax
0x1806664f0  test    rax, rax
0x1806664f3  jnz     short loc_180666507
0x1806664f5  mov     edx, 2375E1C9h; unsigned int
0x1806664fa  lea     rcx, aRegisterlangua_0; "RegisterLanguageTag is not found in Ric"...
0x180666501  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666506  int     3; Trap to Debugger
0x180666507  lea     rdx, aGetlcidfromlan; "GetLcidFromLang"
0x18066650e  mov     rcx, rdi; hModule
0x180666511  call    cs:__imp_GetProcAddress
0x180666517  mov     [rbx+60h], rax
0x18066651b  test    rax, rax
0x18066651e  jnz     short loc_180666532
0x180666520  mov     edx, 2375E1C8h; unsigned int
0x180666525  lea     rcx, aGetlcidfromlan_0; "GetLcidFromLang is not found in RichEdi"...
0x18066652c  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666531  int     3; Trap to Debugger
0x180666532  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x180666537  mov     r8, rax
0x18066653a  mov     edx, 9Ah
0x18066653f  mov     rcx, [rax]
0x180666542  mov     rax, [rcx+0C8h]
0x180666549  mov     rcx, r8
0x18066654c  call    cs:__guard_dispatch_icall_fptr
0x180666552  test    al, al
0x180666554  jz      short loc_180666568
0x180666556  mov     edx, 1E28C311h; unsigned int
0x18066655b  lea     rcx, aFailedToSetLan; "Failed to set language tag for session"
0x180666562  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x180666567  int     3; Trap to Debugger
0x180666568  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x18066656d  mov     r8, rax
0x180666570  mov     edx, 72h ; 'r'
0x180666575  mov     rcx, [rax]
0x180666578  mov     rax, [rcx+0C8h]
0x18066657f  mov     rcx, r8
0x180666582  call    cs:__guard_dispatch_icall_fptr
0x180666588  test    al, al
0x18066658a  jz      short loc_1806665B7
0x18066658c  lea     rdx, aConvertequatio_1; "ConvertEquationFromStorage"
0x180666593  mov     rcx, rdi; hModule
0x180666596  call    cs:__imp_GetProcAddress
0x18066659c  mov     [rbx+48h], rax
0x1806665a0  test    rax, rax
0x1806665a3  jnz     short loc_1806665B7
0x1806665a5  mov     edx, 23891D4h; unsigned int
0x1806665aa  lea     rcx, aConvertequatio_2; "ConvertEquationFromStorage is not found"...
0x1806665b1  call    ?ThrowTag@CTextLayoutException@Art@@SAXPEB_WK@Z; Art::CTextLayoutException::ThrowTag(wchar_t const *,ulong)
0x1806665b6  int     3; Trap to Debugger
0x1806665b7  mov     rsi, [rsp+28h+arg_8]
0x1806665bc  mov     rax, rbx
0x1806665bf  mov     rbx, [rsp+28h+arg_0]
0x1806665c4  add     rsp, 20h
0x1806665c8  pop     rdi
0x1806665c9  retn
```
