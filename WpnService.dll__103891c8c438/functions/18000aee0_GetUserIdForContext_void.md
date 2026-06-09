# GetUserIdForContext(void *)

- ea: `0x18000aee0`
- end: `0x18000b327`
- name: `?GetUserIdForContext@@YA_KPEAX@Z`
- size: `1095`
- prototype: `unsigned __int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x1800099f0`
- `0x18000a9f0`
- `0x18000abc0`
- `0x18000c410`

## callees

- `0x180006160`
- `0x18000aee0`
- `0x18000b330`
- `0x18000b6c0`
- `0x180020480`
- `0x180020598`
- `0x180021048`
- `0x1800232b4`
- `0x180023980`
- `0x180026200`
- `0x1800344d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b150`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b150`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18000b17b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18000b17b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b2af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b2af`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000b309`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000b309`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18000b2fb`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18000b2fb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b2e7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b2e7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000afe1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000afe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000afa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000afa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b1ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b1ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b0e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b0e6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000af0e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000af0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
unsigned __int64 __fastcall GetUserIdForContext(void *a1)
{
  unsigned int v1; // eax
  HRESULT v3; // eax
  unsigned int ActivationFactory; // eax
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rax
  unsigned int v11; // eax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v13; // rsi
  unsigned __int64 v14; // rbx
  size_t v15; // rbx
  _DWORD *v16; // rax
  _DWORD *v17; // rsi
  const wchar_t *v18; // rdi
  unsigned __int64 v19; // r14
  __int64 v20; // rbx
  __int64 v21; // rdx
  const char *v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v24; // rcx
  __int64 v25; // r14
  wchar_t *v26; // rdi
  size_t v27; // rbx
  int v28; // [rsp+20h] [rbp-69h]
  const char *v29; // [rsp+28h] [rbp-61h]
  const char *v30; // [rsp+28h] [rbp-61h]
  const char *v31; // [rsp+28h] [rbp-61h]
  const char *v32; // [rsp+30h] [rbp-59h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-51h] BYREF
  __int64 v34; // [rsp+40h] [rbp-49h] BYREF
  UINT32 length; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v36; // [rsp+50h] [rbp-39h] BYREF
  __int64 v37; // [rsp+58h] [rbp-31h] BYREF
  wchar_t *EndPtr; // [rsp+60h] [rbp-29h] BYREF
  wchar_t *String[2]; // [rsp+68h] [rbp-21h] BYREF
  __int128 v40; // [rsp+78h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  HSTRING string; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v37 = 0;
  v1 = UMgrQueryUserContext(a1, &v37);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x17,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\umgr\\umgrclient.cpp",
    (const char *)v1,
    (__int64)"Could not get user context",
    v29);
  if ( !v37 )
  {
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\umgr\\umgrclient.cpp",
      (const char *)0x8000FFFFLL,
      (int)"UMgr says S_OK, but returned an invalid context. Working around by returning 0",
      v30);
    return 0;
  }
  v34 = 0;
  v33 = 0;
  v32 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v33);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x27,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\umgr\\umgrclient.cpp",
    (const char *)ActivationFactory,
    (__int64)"Could not activate UserManager",
    v30);
  v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
  v6 = **v33;
  v7 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = v6(v5, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v34);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\umgr\\umgrclient.cpp",
      (const char *)(unsigned int)v8,
      v28);
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, const char **))(*(_QWORD *)v34 + 160LL))(v34, v37, &v32);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\umgr\\umgrclient.cpp",
      (const char *)(unsigned int)v9,
      v28);
  v36 = 0;
  v10 = *(_QWORD *)v32;
  v36 = 0;
  v11 = (*(__int64 (__fastcall **)(const char *, HSTRING *))(v10 + 48))(v32, &v36);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2E,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\umgr\\umgrclient.cpp",
    (const char *)v11,
    (__int64)"Could not get the non roamable id for client",
    v31);
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v36, &length);
  v13 = StringRawBuffer;
  *(_OWORD *)String = 0;
  v40 = 0;
  v14 = -1;
  do
    ++v14;
  while ( StringRawBuffer[v14] );
  if ( v14 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v14 > 7 )
  {
    v25 = std::wstring::_Calculate_growth(v14, 7);
    if ( (unsigned __int64)(v25 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      std::_Throw_bad_array_new_length();
    v26 = (wchar_t *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v25 + 1));
    String[0] = v26;
    *(_QWORD *)&v40 = v14;
    *((_QWORD *)&v40 + 1) = v25;
    v27 = v14;
    memcpy_0(v26, v13, v27 * 2);
    v26[v27] = 0;
  }
  else
  {
    *(_QWORD *)&v40 = v14;
    *((_QWORD *)&v40 + 1) = 7;
    v15 = 2 * v14;
    memcpy_0(String, StringRawBuffer, v15);
    *(_WORD *)((char *)String + v15) = 0;
  }
  v16 = (_DWORD *)_o__errno();
  v17 = v16;
  v18 = (const wchar_t *)String;
  if ( *((_QWORD *)&v40 + 1) > 7u )
    v18 = String[0];
  EndPtr = 0;
  *v16 = 0;
  v19 = wcstoull(v18, &EndPtr, 16);
  v20 = (__int64)EndPtr;
  if ( v18 == EndPtr )
  {
    std::_Xinvalid_argument("invalid stoull argument");
    __debugbreak();
  }
  if ( *v17 == 34 )
  {
    std::_Xout_of_range("stoull argument out of range");
    goto LABEL_36;
  }
  v20 = EndPtr - v18;
  v21 = *((_QWORD *)&v40 + 1);
  if ( *((_QWORD *)&v40 + 1) > 7u )
LABEL_36:
    std::_Deallocate<16>((_QWORD *)String[0], 2 * v21 + 2);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x33,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\umgr\\umgrclient.cpp",
    (const char *)0x8000FFFFLL,
    length == v20,
    (bool)"Something went wrong in parsing the NonRoamableId",
    v32);
  if ( v36 )
    WindowsDeleteString(v36);
  v22 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v33;
  if ( v33 )
  {
    v33 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
  }
  v24 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return v19;
}

```

## disassembly

```asm
0x18000aee0  push    rbp
0x18000aee2  push    rbx
0x18000aee3  push    rsi
0x18000aee4  push    rdi
0x18000aee5  push    r14
0x18000aee7  push    r15
0x18000aee9  lea     rbp, [rsp-2Fh]
0x18000aeee  sub     rsp, 0B8h
0x18000aef5  mov     rax, cs:__security_cookie
0x18000aefc  xor     rax, rsp
0x18000aeff  mov     [rbp+57h+var_38], rax
0x18000af03  xor     r15d, r15d
0x18000af06  mov     [rbp+57h+var_88], r15
0x18000af0a  lea     rdx, [rbp+57h+var_88]
0x18000af0e  call    cs:__imp_UMgrQueryUserContext
0x18000af14  mov     rcx, [rbp+5Fh]; this
0x18000af18  lea     rdx, aCouldNotGetUse; "Could not get user context"
0x18000af1f  mov     qword ptr [rsp+0E0h+var_C0], rdx; __int64
0x18000af24  mov     r9d, eax; char *
0x18000af27  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000af2e  mov     edx, 17h; void *
0x18000af33  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000af38  cmp     [rbp+57h+var_88], r15
0x18000af3c  jnz     short loc_18000AF83
0x18000af3e  mov     rcx, [rbp+5Fh]; this
0x18000af42  lea     rax, aUmgrSaysSOkBut; "UMgr says S_OK, but returned an invalid"...
0x18000af49  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18000af4e  mov     r9d, 8000FFFFh; char *
0x18000af54  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000af5b  mov     edx, 1Ch; void *
0x18000af60  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000af65  xor     eax, eax
0x18000af67  mov     rcx, [rbp+57h+var_38]
0x18000af6b  xor     rcx, rsp; StackCookie
0x18000af6e  call    __security_check_cookie
0x18000af73  add     rsp, 0B8h
0x18000af7a  pop     r15
0x18000af7c  pop     r14
0x18000af7e  pop     rdi
0x18000af7f  pop     rsi
0x18000af80  pop     rbx
0x18000af81  pop     rbp
0x18000af82  retn
0x18000af83  mov     [rbp+57h+var_A0], r15
0x18000af87  mov     [rbp+57h+var_A8], r15
0x18000af8b  mov     [rbp+57h+var_B0], r15
0x18000af8f  mov     [rbp+57h+string], r15
0x18000af93  lea     r9, [rbp+57h+string]; string
0x18000af97  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000af9b  mov     edx, 23h ; '#'; length
0x18000afa0  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18000afa7  call    cs:__imp_WindowsCreateStringReference
0x18000afad  test    eax, eax
0x18000afaf  js      loc_18000B2A2
0x18000afb5  mov     rbx, [rbp+57h+string]
0x18000afb9  mov     rcx, [rbp+57h+var_A8]
0x18000afbd  test    rcx, rcx
0x18000afc0  jz      short loc_18000AFD3
0x18000afc2  mov     [rbp+57h+var_A8], r15
0x18000afc6  mov     rax, [rcx]
0x18000afc9  mov     rax, [rax+10h]
0x18000afcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afd2  nop
0x18000afd3  lea     r8, [rbp+57h+var_A8]
0x18000afd7  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18000afde  mov     rcx, rbx
0x18000afe1  call    cs:__imp_RoGetActivationFactory
0x18000afe7  mov     rcx, [rbp+5Fh]; this
0x18000afeb  lea     rdx, aCouldNotActiva; "Could not activate UserManager"
0x18000aff2  mov     qword ptr [rsp+0E0h+var_C0], rdx; int
0x18000aff7  mov     r9d, eax; char *
0x18000affa  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b001  mov     edx, 27h ; '''; void *
0x18000b006  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000b00b  nop
0x18000b00c  mov     rbx, [rbp+57h+var_A8]
0x18000b010  mov     rax, [rbx]
0x18000b013  mov     rdi, [rax]
0x18000b016  mov     rcx, [rbp+57h+var_A0]
0x18000b01a  test    rcx, rcx
0x18000b01d  jz      short loc_18000B030
0x18000b01f  mov     [rbp+57h+var_A0], r15
0x18000b023  mov     rdx, [rcx]
0x18000b026  mov     rax, [rdx+10h]
0x18000b02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02f  nop
0x18000b030  lea     r8, [rbp+57h+var_A0]
0x18000b034  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18000b03b  mov     rcx, rbx
0x18000b03e  mov     rax, rdi
0x18000b041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b046  nop
0x18000b047  mov     rcx, [rbp+5Fh]; this
0x18000b04b  test    eax, eax
0x18000b04d  js      loc_18000B2B6
0x18000b053  mov     rbx, [rbp+57h+var_A0]
0x18000b057  mov     rax, [rbx]
0x18000b05a  mov     rdi, [rax+0A0h]
0x18000b061  mov     rcx, [rbp+57h+var_B0]
0x18000b065  test    rcx, rcx
0x18000b068  jz      short loc_18000B07B
0x18000b06a  mov     [rbp+57h+var_B0], r15
0x18000b06e  mov     rdx, [rcx]
0x18000b071  mov     rax, [rdx+10h]
0x18000b075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b07a  nop
0x18000b07b  lea     r8, [rbp+57h+var_B0]
0x18000b07f  mov     rdx, [rbp+57h+var_88]
0x18000b083  mov     rcx, rbx
0x18000b086  mov     rax, rdi
0x18000b089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b08e  mov     rcx, [rbp+5Fh]; this
0x18000b092  test    eax, eax
0x18000b094  js      loc_18000B2CB
0x18000b09a  mov     [rbp+57h+var_90], r15
0x18000b09e  mov     rcx, [rbp+57h+var_B0]
0x18000b0a2  mov     rax, [rcx]
0x18000b0a5  mov     [rbp+57h+var_90], r15
0x18000b0a9  lea     rdx, [rbp+57h+var_90]
0x18000b0ad  mov     rax, [rax+30h]
0x18000b0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b6  mov     rcx, [rbp+5Fh]; this
0x18000b0ba  lea     rdx, aCouldNotGetThe; "Could not get the non roamable id for c"...
0x18000b0c1  mov     qword ptr [rsp+0E0h+var_C0], rdx; __int64
0x18000b0c6  mov     r9d, eax; char *
0x18000b0c9  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b0d0  mov     edx, 2Eh ; '.'; void *
0x18000b0d5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000b0da  mov     [rbp+57h+length], r15d
0x18000b0de  lea     rdx, [rbp+57h+length]; length
0x18000b0e2  mov     rcx, [rbp+57h+var_90]; string
0x18000b0e6  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b0ec  mov     rsi, rax
0x18000b0ef  xorps   xmm0, xmm0
0x18000b0f2  movups  xmmword ptr [rbp+57h+String], xmm0
0x18000b0f6  xorps   xmm1, xmm1
0x18000b0f9  movdqu  [rbp+57h+var_68], xmm1
0x18000b0fe  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b105  inc     rbx
0x18000b108  cmp     word ptr [rax+rbx*2], 0
0x18000b10d  jnz     short loc_18000B105
0x18000b10f  mov     r8, 7FFFFFFFFFFFFFFEh
0x18000b119  cmp     rbx, r8
0x18000b11c  ja      loc_18000B2E0
0x18000b122  cmp     rbx, 7
0x18000b126  ja      loc_18000B249
0x18000b12c  mov     qword ptr [rbp+57h+var_68], rbx
0x18000b130  mov     qword ptr [rbp+57h+var_68+8], 7
0x18000b138  add     rbx, rbx
0x18000b13b  mov     r8, rbx; Size
0x18000b13e  mov     rdx, rsi; Src
0x18000b141  lea     rcx, [rbp+57h+String]; void *
0x18000b145  call    memcpy_0
0x18000b14a  mov     word ptr [rbp+rbx+57h+String], r15w
0x18000b150  call    cs:__imp__o__errno
0x18000b156  mov     rsi, rax
0x18000b159  lea     rdi, [rbp+57h+String]
0x18000b15d  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18000b162  cmova   rdi, [rbp+57h+String]
0x18000b167  mov     [rbp+57h+EndPtr], r15
0x18000b16b  mov     [rax], r15d
0x18000b16e  mov     r8d, 10h; Radix
0x18000b174  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x18000b178  mov     rcx, rdi; String
0x18000b17b  call    cs:__imp_wcstoull
0x18000b181  mov     r14, rax
0x18000b184  mov     rbx, [rbp+57h+EndPtr]
0x18000b188  cmp     rdi, rbx
0x18000b18b  jz      loc_18000B2F4
0x18000b191  cmp     dword ptr [rsi], 22h ; '"'
0x18000b194  jz      loc_18000B302
0x18000b19a  sub     rbx, rdi
0x18000b19d  sar     rbx, 1
0x18000b1a0  mov     rdx, qword ptr [rbp+57h+var_68+8]
0x18000b1a4  cmp     rdx, 7
0x18000b1a8  ja      loc_18000B310
0x18000b1ae  mov     eax, [rbp+57h+length]
0x18000b1b1  cmp     rax, rbx
0x18000b1b4  setz    al
0x18000b1b7  mov     rcx, [rbp+5Fh]; this
0x18000b1bb  lea     rdx, aSomethingWentW; "Something went wrong in parsing the Non"...
0x18000b1c2  mov     qword ptr [rsp+0E0h+var_B8], rdx; bool
0x18000b1c7  mov     [rsp+0E0h+var_C0], al; char
0x18000b1cb  mov     r9d, 8000FFFFh; char *
0x18000b1d1  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b1d8  mov     edx, 33h ; '3'; void *
0x18000b1dd  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000b1e2  nop
0x18000b1e3  mov     rcx, [rbp+57h+var_90]; string
0x18000b1e7  test    rcx, rcx
0x18000b1ea  jz      short loc_18000B1F3
0x18000b1ec  call    cs:__imp_WindowsDeleteString
0x18000b1f2  nop
0x18000b1f3  mov     rcx, [rbp+57h+var_B0]
0x18000b1f7  test    rcx, rcx
0x18000b1fa  jz      short loc_18000B20D
0x18000b1fc  mov     [rbp+57h+var_B0], r15
0x18000b200  mov     rax, [rcx]
0x18000b203  mov     rax, [rax+10h]
0x18000b207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b20c  nop
0x18000b20d  mov     rcx, [rbp+57h+var_A8]
0x18000b211  test    rcx, rcx
0x18000b214  jz      short loc_18000B227
0x18000b216  mov     [rbp+57h+var_A8], r15
0x18000b21a  mov     rax, [rcx]
0x18000b21d  mov     rax, [rax+10h]
0x18000b221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b226  nop
0x18000b227  mov     rcx, [rbp+57h+var_A0]
0x18000b22b  test    rcx, rcx
0x18000b22e  jz      short loc_18000B241
0x18000b230  mov     [rbp+57h+var_A0], r15
0x18000b234  mov     rax, [rcx]
0x18000b237  mov     rax, [rax+10h]
0x18000b23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b240  nop
0x18000b241  mov     rax, r14
0x18000b244  jmp     loc_18000AF67
0x18000b249  mov     edx, 7
0x18000b24e  mov     rcx, rbx
0x18000b251  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18000b256  mov     r14, rax
0x18000b259  lea     rcx, [rax+1]
0x18000b25d  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000b267  cmp     rcx, rax
0x18000b26a  ja      loc_18000B2EE
0x18000b270  add     rcx, rcx
0x18000b273  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000b278  mov     rdi, rax
0x18000b27b  mov     [rbp+57h+String], rax
0x18000b27f  mov     qword ptr [rbp+57h+var_68], rbx
0x18000b283  mov     qword ptr [rbp+57h+var_68+8], r14
0x18000b287  add     rbx, rbx
0x18000b28a  mov     r8, rbx; Size
0x18000b28d  mov     rdx, rsi; Src
0x18000b290  mov     rcx, rax; void *
0x18000b293  call    memcpy_0
0x18000b298  mov     [rbx+rdi], r15w
0x18000b29d  jmp     loc_18000B150
0x18000b2a2  xor     r9d, r9d; lpArguments
0x18000b2a5  xor     r8d, r8d; nNumberOfArguments
0x18000b2a8  mov     edx, 1; dwExceptionFlags
0x18000b2ad  mov     ecx, eax; dwExceptionCode
0x18000b2af  call    cs:__imp_RaiseException
0x18000b2b5  int     3; Trap to Debugger
0x18000b2b6  mov     r9d, eax; char *
0x18000b2b9  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b2c0  mov     edx, 29h ; ')'; void *
0x18000b2c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b2cb  mov     r9d, eax; char *
0x18000b2ce  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000b2d5  mov     edx, 2Bh ; '+'; void *
0x18000b2da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b2e0  lea     rcx, aStringTooLong; "string too long"
0x18000b2e7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000b2ee  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000b2f4  lea     rcx, aInvalidStoullA; "invalid stoull argument"
0x18000b2fb  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18000b301  int     3; Trap to Debugger
0x18000b302  lea     rcx, aStoullArgument; "stoull argument out of range"
0x18000b309  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000b30f  nop
0x18000b310  lea     rdx, ds:2[rdx*2]
0x18000b318  mov     rcx, [rbp+57h+String]
0x18000b31c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b321  jmp     loc_18000B1AE
```
