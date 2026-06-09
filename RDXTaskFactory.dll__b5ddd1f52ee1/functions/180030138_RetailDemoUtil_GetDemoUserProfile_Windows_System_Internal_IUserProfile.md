# RetailDemoUtil::GetDemoUserProfile(Windows::System::Internal::IUserProfile * *)

- ea: `0x180030138`
- end: `0x1800304e2`
- name: `?GetDemoUserProfile@RetailDemoUtil@@YAJPEAPEAUIUserProfile@Internal@System@Windows@@@Z`
- size: `938`
- prototype: `__int64 __fastcall(RetailDemoUtil *__hidden this, struct Windows::System::Internal::IUserProfile **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fd20`

## callees

- `0x180003390`
- `0x18000aa7c`
- `0x18000e330`
- `0x180025d04`
- `0x18002ed28`
- `0x180030138`
- `0x180031ca0`
- `0x180050010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003042d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003042d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003044d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800304c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003044d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800304c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003041f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003041f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800301ba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800301ba`

## string_xrefs

- `0x180030184`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800301d1`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030233`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030295`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800302ea`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x18003035a`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800303d2`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall RetailDemoUtil::GetDemoUserProfile(
        RetailDemoUtil *this,
        struct Windows::System::Internal::IUserProfile **a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  int v5; // eax
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // ebx
  HSTRING *v9; // rax
  int ActivationFactory; // eax
  unsigned int v11; // ebx
  __int64 *v12; // rdi
  __int64 (__fastcall *v13)(__int64 *, HSTRING, RetailDemoUtil *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  unsigned int i; // r14d
  __int64 v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  int v27; // eax
  unsigned int v28; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v30; // rax
  int v31[2]; // [rsp+20h] [rbp-288h] BYREF
  unsigned int v32; // [rsp+28h] [rbp-280h] BYREF
  HSTRING string; // [rsp+30h] [rbp-278h] BYREF
  __int64 v34; // [rsp+38h] [rbp-270h] BYREF
  __int64 *v35; // [rsp+40h] [rbp-268h] BYREF
  HSTRING v36[5]; // [rsp+48h] [rbp-260h] BYREF
  unsigned __int16 v37[264]; // [rsp+70h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  *(_QWORD *)this = 0;
  v5 = RetailDemoUtil::RDXRegGetString(this, (const unsigned __int16 *)a2, v37, a4, v31[0]);
  v7 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v5,
      v31[0]);
    return v7;
  }
  *(_QWORD *)v31 = 0;
  v9 = Windows::Internal::StringReference::StringReference(v36, (const unsigned __int16 (*)[36])v6);
  ActivationFactory = RoGetActivationFactory(*v9, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, v31);
  v11 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v31[0]);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v31);
    return v11;
  }
  v12 = *(__int64 **)v31;
  v13 = *(__int64 (__fastcall **)(__int64 *, HSTRING, RetailDemoUtil *))(**(_QWORD **)v31 + 104LL);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v36, v37);
  v14 = v13(v12, v36[0], this);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v14,
      v31[0]);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v31);
    return v15;
  }
  if ( *(_QWORD *)this )
    goto LABEL_22;
  v35 = 0;
  v32 = 0;
  v16 = **(_QWORD **)v31;
  v35 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(v16 + 88))(*(_QWORD *)v31, &v35);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v17,
      v31[0]);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v35);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v31);
    return v18;
  }
  v19 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v35 + 56))(v35, &v32);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)(unsigned int)v19,
      v31[0]);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v35);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v31);
    return v20;
  }
  for ( i = 0; i < v32; ++i )
  {
    v34 = 0;
    v22 = *v35;
    v34 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v22 + 48))(v35, i, &v34);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v23,
        v31[0]);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v34);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v35);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v31);
      return v24;
    }
    string = 0;
    v25 = v34;
    v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v27 = v26(v25, &string);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)v27,
        v31[0]);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v34);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v35);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v31);
      return v28;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !(unsigned int)_o__wcsicmp(v37, StringRawBuffer) )
    {
      v30 = v34;
      v34 = 0;
      *(_QWORD *)this = v30;
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v34);
      break;
    }
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v34);
  }
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v35);
  if ( *(_QWORD *)this )
  {
LABEL_22:
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v31);
    return 0;
  }
  else
  {
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v31);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x180030138  mov     [rsp+arg_8], rbx
0x18003013d  mov     [rsp+arg_10], rsi
0x180030142  push    rdi
0x180030143  push    r14
0x180030145  push    r15
0x180030147  sub     rsp, 290h
0x18003014e  mov     rax, cs:__security_cookie
0x180030155  xor     rax, rsp
0x180030158  mov     [rsp+2A8h+var_28], rax
0x180030160  mov     rsi, rcx
0x180030163  xor     r15d, r15d
0x180030166  mov     [rcx], r15
0x180030169  lea     r8, [rsp+2A8h+var_238]; unsigned __int16 *
0x18003016e  call    ?RDXRegGetString@RetailDemoUtil@@YAJPEBG0PEAGK@Z; RetailDemoUtil::RDXRegGetString(ushort const *,ushort const *,ushort *,ulong)
0x180030173  mov     ebx, eax
0x180030175  test    eax, eax
0x180030177  jns     short loc_18003019C
0x180030179  mov     rcx, [rsp+2A8h]; this
0x180030181  mov     r9d, eax; char *
0x180030184  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003018b  mov     edx, 12Dh; void *
0x180030190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030195  mov     eax, ebx
0x180030197  jmp     loc_180030495
0x18003019c  mov     qword ptr [rsp+2A8h+var_288], r15; int
0x1800301a1  lea     rcx, [rsp+2A8h+var_260]; string
0x1800301a6  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x1800301ab  lea     r8, [rsp+2A8h+var_288]
0x1800301b0  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x1800301b7  mov     rcx, [rax]
0x1800301ba  call    cs:__imp_RoGetActivationFactory
0x1800301c0  mov     ebx, eax
0x1800301c2  test    eax, eax
0x1800301c4  jns     short loc_1800301F4
0x1800301c6  mov     rcx, [rsp+2A8h]; this
0x1800301ce  mov     r9d, eax; char *
0x1800301d1  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800301d8  mov     edx, 130h; void *
0x1800301dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800301e2  nop
0x1800301e3  lea     rcx, [rsp+2A8h+var_288]
0x1800301e8  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800301ed  mov     eax, ebx
0x1800301ef  jmp     loc_180030495
0x1800301f4  mov     rdi, qword ptr [rsp+2A8h+var_288]
0x1800301f9  mov     rax, [rdi]
0x1800301fc  mov     rbx, [rax+68h]
0x180030200  lea     rdx, [rsp+2A8h+var_238]; unsigned __int16 *
0x180030205  lea     rcx, [rsp+2A8h+var_260]; this
0x18003020a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003020f  mov     r8, rsi
0x180030212  mov     rdx, [rsp+2A8h+var_260]
0x180030217  mov     rcx, rdi
0x18003021a  mov     rax, rbx
0x18003021d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030222  mov     ebx, eax
0x180030224  test    eax, eax
0x180030226  jns     short loc_180030256
0x180030228  mov     rcx, [rsp+2A8h]; this
0x180030230  mov     r9d, eax; char *
0x180030233  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003023a  mov     edx, 133h; void *
0x18003023f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030244  nop
0x180030245  lea     rcx, [rsp+2A8h+var_288]
0x18003024a  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18003024f  mov     eax, ebx
0x180030251  jmp     loc_180030495
0x180030256  cmp     [rsi], r15
0x180030259  jnz     loc_180030483
0x18003025f  mov     [rsp+2A8h+var_268], r15
0x180030264  mov     [rsp+2A8h+var_280], r15d
0x180030269  mov     rcx, qword ptr [rsp+2A8h+var_288]
0x18003026e  mov     rax, [rcx]
0x180030271  mov     [rsp+2A8h+var_268], r15
0x180030276  lea     rdx, [rsp+2A8h+var_268]
0x18003027b  mov     rax, [rax+58h]
0x18003027f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030284  mov     ebx, eax
0x180030286  test    eax, eax
0x180030288  jns     short loc_1800302C3
0x18003028a  mov     rcx, [rsp+2A8h]; this
0x180030292  mov     r9d, eax; char *
0x180030295  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003029c  mov     edx, 13Bh; void *
0x1800302a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302a6  nop
0x1800302a7  lea     rcx, [rsp+2A8h+var_268]
0x1800302ac  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800302b1  nop
0x1800302b2  lea     rcx, [rsp+2A8h+var_288]
0x1800302b7  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800302bc  mov     eax, ebx
0x1800302be  jmp     loc_180030495
0x1800302c3  mov     rcx, [rsp+2A8h+var_268]
0x1800302c8  mov     rax, [rcx]
0x1800302cb  lea     rdx, [rsp+2A8h+var_280]
0x1800302d0  mov     rax, [rax+38h]
0x1800302d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302d9  mov     ebx, eax
0x1800302db  test    eax, eax
0x1800302dd  jns     short loc_180030318
0x1800302df  mov     rcx, [rsp+2A8h]; this
0x1800302e7  mov     r9d, eax; char *
0x1800302ea  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800302f1  mov     edx, 13Ch; void *
0x1800302f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800302fb  nop
0x1800302fc  lea     rcx, [rsp+2A8h+var_268]
0x180030301  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030306  nop
0x180030307  lea     rcx, [rsp+2A8h+var_288]
0x18003030c  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030311  mov     eax, ebx
0x180030313  jmp     loc_180030495
0x180030318  mov     r14d, r15d
0x18003031b  cmp     r14d, [rsp+2A8h+var_280]
0x180030320  jnb     loc_180030463
0x180030326  mov     [rsp+2A8h+var_270], r15
0x18003032b  mov     rcx, [rsp+2A8h+var_268]
0x180030330  mov     rax, [rcx]
0x180030333  mov     [rsp+2A8h+var_270], r15
0x180030338  lea     r8, [rsp+2A8h+var_270]
0x18003033d  mov     edx, r14d
0x180030340  mov     rax, [rax+30h]
0x180030344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030349  mov     ebx, eax
0x18003034b  test    eax, eax
0x18003034d  jns     short loc_180030393
0x18003034f  mov     rcx, [rsp+2A8h]; this
0x180030357  mov     r9d, eax; char *
0x18003035a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030361  mov     edx, 141h; void *
0x180030366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003036b  nop
0x18003036c  lea     rcx, [rsp+2A8h+var_270]
0x180030371  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030376  nop
0x180030377  lea     rcx, [rsp+2A8h+var_268]
0x18003037c  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030381  nop
0x180030382  lea     rcx, [rsp+2A8h+var_288]
0x180030387  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18003038c  mov     eax, ebx
0x18003038e  jmp     loc_180030495
0x180030393  mov     [rsp+2A8h+string], r15
0x180030398  mov     rdi, [rsp+2A8h+var_270]
0x18003039d  mov     rax, [rdi]
0x1800303a0  mov     rbx, [rax+38h]
0x1800303a4  xor     ecx, ecx; string
0x1800303a6  call    cs:__imp_WindowsDeleteString
0x1800303ac  mov     [rsp+2A8h+string], r15
0x1800303b1  lea     rdx, [rsp+2A8h+string]
0x1800303b6  mov     rcx, rdi
0x1800303b9  mov     rax, rbx
0x1800303bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303c1  mov     ebx, eax
0x1800303c3  test    eax, eax
0x1800303c5  jns     short loc_180030418
0x1800303c7  mov     rcx, [rsp+2A8h]; this
0x1800303cf  mov     r9d, eax; char *
0x1800303d2  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800303d9  mov     edx, 144h; void *
0x1800303de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800303e3  nop
0x1800303e4  mov     rcx, [rsp+2A8h+string]; string
0x1800303e9  call    cs:__imp_WindowsDeleteString
0x1800303ef  mov     [rsp+2A8h+string], r15
0x1800303f4  lea     rcx, [rsp+2A8h+var_270]
0x1800303f9  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800303fe  nop
0x1800303ff  lea     rcx, [rsp+2A8h+var_268]
0x180030404  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030409  nop
0x18003040a  lea     rcx, [rsp+2A8h+var_288]
0x18003040f  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030414  mov     eax, ebx
0x180030416  jmp     short loc_180030495
0x180030418  xor     edx, edx; length
0x18003041a  mov     rcx, [rsp+2A8h+string]; string
0x18003041f  call    cs:__imp_WindowsGetStringRawBuffer
0x180030425  mov     rdx, rax
0x180030428  lea     rcx, [rsp+2A8h+var_238]
0x18003042d  call    cs:__imp__o__wcsicmp
0x180030433  test    eax, eax
0x180030435  jnz     loc_1800304BE
0x18003043b  mov     rax, [rsp+2A8h+var_270]
0x180030440  mov     [rsp+2A8h+var_270], r15
0x180030445  mov     [rsi], rax
0x180030448  mov     rcx, [rsp+2A8h+string]; string
0x18003044d  call    cs:__imp_WindowsDeleteString
0x180030453  mov     [rsp+2A8h+string], r15
0x180030458  lea     rcx, [rsp+2A8h+var_270]
0x18003045d  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x180030462  nop
0x180030463  lea     rcx, [rsp+2A8h+var_268]
0x180030468  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18003046d  cmp     [rsi], r15
0x180030470  jnz     short loc_180030483
0x180030472  lea     rcx, [rsp+2A8h+var_288]
0x180030477  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18003047c  mov     eax, 80070490h
0x180030481  jmp     short loc_180030495
0x180030483  lea     rcx, [rsp+2A8h+var_288]
0x180030488  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18003048d  xor     eax, eax
0x18003048f  jmp     short loc_180030495
0x180030491  mov     eax, [rsp+2A8h+var_280]
0x180030495  mov     rcx, [rsp+2A8h+var_28]
0x18003049d  xor     rcx, rsp; StackCookie
0x1800304a0  call    __security_check_cookie
0x1800304a5  lea     r11, [rsp+2A8h+var_18]
0x1800304ad  mov     rbx, [r11+28h]
0x1800304b1  mov     rsi, [r11+30h]
0x1800304b5  mov     rsp, r11
0x1800304b8  pop     r15
0x1800304ba  pop     r14
0x1800304bc  pop     rdi
0x1800304bd  retn
0x1800304be  mov     rcx, [rsp+2A8h+string]; string
0x1800304c3  call    cs:__imp_WindowsDeleteString
0x1800304c9  mov     [rsp+2A8h+string], r15
0x1800304ce  lea     rcx, [rsp+2A8h+var_270]
0x1800304d3  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800304d8  inc     r14d
0x1800304db  jmp     loc_18003031B
```
