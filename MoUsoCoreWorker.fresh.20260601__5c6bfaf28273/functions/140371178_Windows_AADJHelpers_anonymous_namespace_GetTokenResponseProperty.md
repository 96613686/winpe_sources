# Windows::AADJHelpers::_anonymous_namespace_::GetTokenResponseProperty

- ea: `0x140371178`
- end: `0x140371566`
- name: `Windows::AADJHelpers::_anonymous_namespace_::GetTokenResponseProperty`
- size: `1006`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140371798`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x14012a810`
- `0x14023feb8`
- `0x140371178`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1403712e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140371420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1403712e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140371420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140371326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140371459`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140371469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140371326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140371459`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140371469`

## string_xrefs

- `0x1403714eb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x14037152a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x14037153f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1403714d6`: `C:\__w\1\s\src\orchestrator\system\windows\common\AADJHelpers.cpp`
- `0x140371500`: `C:\__w\1\s\src\orchestrator\system\windows\common\AADJHelpers.cpp`
- `0x140371515`: `C:\__w\1\s\src\orchestrator\system\windows\common\AADJHelpers.cpp`
- `0x140371554`: `C:\__w\1\s\src\orchestrator\system\windows\common\AADJHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 *__fastcall Windows::AADJHelpers::_anonymous_namespace_::GetTokenResponseProperty(
        __int64 *a1,
        __int64 *a2,
        __int128 *a3)
{
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, _QWORD **); // r14
  _QWORD *v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rcx
  void (*v23)(void); // rax
  __int64 v25; // rax
  int v26; // eax
  PCWSTR v27; // rax
  _QWORD *v28; // rcx
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-69h]
  __int128 v31; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v32[8]; // [rsp+50h] [rbp-39h] BYREF
  HSTRING string; // [rsp+58h] [rbp-31h] BYREF
  __int128 v34; // [rsp+60h] [rbp-29h] BYREF
  _QWORD *v35; // [rsp+70h] [rbp-19h] BYREF
  __int64 v36; // [rsp+78h] [rbp-11h] BYREF
  __int64 *v37; // [rsp+80h] [rbp-9h] BYREF
  HSTRING v38[2]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v37 = a1;
  v5 = *a2;
  v37 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v5 + 72))(a2, &v37);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\AADJHelpers.cpp",
      (const char *)(unsigned int)v6,
      v30);
  v36 = 0;
  v7 = *v37;
  v36 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 72))(v37, &v36);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\AADJHelpers.cpp",
      (const char *)(unsigned int)v8,
      v30);
  v38[0] = 0;
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, HSTRING *))v36)(
         v36,
         &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b,
         v38);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v9,
      v30);
  string = v38[0];
  if ( v38[0] )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v38[0] + 16LL))(v38[0]);
  v34 = 0;
  v35 = 0;
  wil::iterable_range<ABI::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::begin(
    &string,
    &v34);
  v10 = -1;
  if ( DWORD2(v34) == -1 )
  {
LABEL_21:
    v21 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    v22 = v34;
    if ( (_QWORD)v34 )
    {
      *(_QWORD *)&v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    *((_BYTE *)a1 + 32) = 0;
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v37 )
    {
      v23 = *(void (**)(void))(*v37 + 16);
LABEL_29:
      v23();
    }
  }
  else
  {
    while ( 1 )
    {
      v11 = v34;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v34 + 48LL);
      v13 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
      }
      v14 = v12(v11, &v35);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v14,
          v30);
      string = 0;
      v15 = *v35;
      string = 0;
      v16 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v15 + 48))(v35, &string);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\AADJHelpers.cpp",
          (const char *)(unsigned int)v16,
          v30);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v18 = -1;
      do
        ++v18;
      while ( StringRawBuffer[v18] );
      v31 = *a3;
      v38[0] = (HSTRING)StringRawBuffer;
      v38[1] = (HSTRING)v18;
      if ( (unsigned __int8)Strings::iequals(v38, &v31) )
        break;
      if ( string )
        WindowsDeleteString(string);
      v32[0] = 0;
      v19 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)v34 + 64LL))(v34, v32);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v19,
          v30);
      if ( v32[0] )
      {
        v20 = ++DWORD2(v34);
      }
      else
      {
        v20 = -1;
        DWORD2(v34) = -1;
      }
      if ( v20 == -1 )
        goto LABEL_21;
    }
    v38[0] = 0;
    v25 = *v35;
    v38[0] = 0;
    v26 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v25 + 56))(v35, v38);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\AADJHelpers.cpp",
        (const char *)(unsigned int)v26,
        v30);
    v27 = WindowsGetStringRawBuffer(v38[0], 0);
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
    a1[3] = 0;
    do
      ++v10;
    while ( v27[v10] );
    std::wstring::_Construct<1,wchar_t const *>(a1, v27, v10);
    *((_BYTE *)a1 + 32) = 1;
    if ( v38[0] )
      WindowsDeleteString(v38[0]);
    if ( string )
      WindowsDeleteString(string);
    v28 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
    }
    v29 = v34;
    if ( (_QWORD)v34 )
    {
      *(_QWORD *)&v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v37 )
    {
      v23 = *(void (**)(void))(*v37 + 16);
      goto LABEL_29;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140371178  push    rbp
0x14037117a  push    rbx
0x14037117b  push    rsi
0x14037117c  push    rdi
0x14037117d  push    r12
0x14037117f  push    r14
0x140371181  push    r15
0x140371183  lea     rbp, [rsp-27h]
0x140371188  sub     rsp, 0B0h
0x14037118f  mov     rax, cs:__security_cookie
0x140371196  xor     rax, rsp
0x140371199  mov     [rbp+57h+var_40], rax
0x14037119d  mov     r15, r8
0x1403711a0  mov     r9, rdx
0x1403711a3  mov     rdi, rcx
0x1403711a6  mov     [rbp+57h+var_60], rcx
0x1403711aa  xor     r12d, r12d
0x1403711ad  mov     rax, [rdx]
0x1403711b0  mov     [rbp+57h+var_60], r12
0x1403711b4  lea     rdx, [rbp+57h+var_60]
0x1403711b8  mov     rcx, r9
0x1403711bb  mov     rax, [rax+48h]
0x1403711bf  call    _guard_dispatch_icall
0x1403711c4  mov     rcx, [rbp+5Fh]; this
0x1403711c8  test    eax, eax
0x1403711ca  js      loc_1403714FD
0x1403711d0  mov     [rbp+57h+var_68], r12
0x1403711d4  mov     rcx, [rbp+57h+var_60]
0x1403711d8  mov     rax, [rcx]
0x1403711db  mov     [rbp+57h+var_68], r12
0x1403711df  lea     rdx, [rbp+57h+var_68]
0x1403711e3  mov     rax, [rax+48h]
0x1403711e7  call    _guard_dispatch_icall
0x1403711ec  mov     rcx, [rbp+5Fh]; this
0x1403711f0  test    eax, eax
0x1403711f2  js      loc_140371512
0x1403711f8  mov     rcx, [rbp+57h+var_68]
0x1403711fc  mov     [rbp+57h+var_50], r12
0x140371200  mov     rax, [rcx]
0x140371203  lea     r8, [rbp+57h+var_50]
0x140371207  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x14037120e  mov     rax, [rax]
0x140371211  call    _guard_dispatch_icall
0x140371216  mov     rcx, [rbp+5Fh]; this
0x14037121a  test    eax, eax
0x14037121c  js      loc_140371527
0x140371222  mov     rcx, [rbp+57h+var_50]
0x140371226  mov     [rbp+57h+string], rcx
0x14037122a  test    rcx, rcx
0x14037122d  jz      short loc_14037123C
0x14037122f  mov     rax, [rcx]
0x140371232  mov     rax, [rax+10h]
0x140371236  call    _guard_dispatch_icall
0x14037123b  nop
0x14037123c  xorps   xmm0, xmm0
0x14037123f  xor     eax, eax
0x140371241  movups  [rbp+57h+var_80], xmm0
0x140371245  mov     [rbp+57h+var_70], rax
0x140371249  lea     rdx, [rbp+57h+var_80]
0x14037124d  lea     rcx, [rbp+57h+string]
0x140371251  call    ?begin@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@ABI@@Uerr_exception_policy@wil@@@wil@@QEAA?AViterable_iterator@12@XZ; wil::iterable_range<ABI::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *,wil::err_exception_policy>::begin(void)
0x140371256  nop
0x140371257  xorps   xmm0, xmm0
0x14037125a  movups  [rbp+57h+var_B8], xmm0
0x14037125e  mov     qword ptr [rbp+57h+var_B8], r12
0x140371262  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140371266  mov     dword ptr [rbp+57h+var_B8+8], ebx
0x140371269  mov     [rbp+57h+var_A8], r12
0x14037126d  cmp     dword ptr [rbp+57h+var_80+8], ebx
0x140371270  jz      loc_14037136D
0x140371276  mov     rsi, qword ptr [rbp+57h+var_80]
0x14037127a  mov     rax, [rsi]
0x14037127d  mov     r14, [rax+30h]
0x140371281  mov     rcx, [rbp+57h+var_70]
0x140371285  test    rcx, rcx
0x140371288  jz      short loc_14037129B
0x14037128a  mov     [rbp+57h+var_70], r12
0x14037128e  mov     rax, [rcx]
0x140371291  mov     rax, [rax+10h]
0x140371295  call    _guard_dispatch_icall
0x14037129a  nop
0x14037129b  lea     rdx, [rbp+57h+var_70]
0x14037129f  mov     rcx, rsi
0x1403712a2  mov     rax, r14
0x1403712a5  call    _guard_dispatch_icall
0x1403712aa  mov     rcx, [rbp+5Fh]; this
0x1403712ae  test    eax, eax
0x1403712b0  js      loc_1403714E8
0x1403712b6  mov     [rbp+57h+string], r12
0x1403712ba  mov     rcx, [rbp+57h+var_70]
0x1403712be  mov     rax, [rcx]
0x1403712c1  mov     [rbp+57h+string], r12
0x1403712c5  lea     rdx, [rbp+57h+string]
0x1403712c9  mov     rax, [rax+30h]
0x1403712cd  call    _guard_dispatch_icall
0x1403712d2  mov     rcx, [rbp+5Fh]; this
0x1403712d6  test    eax, eax
0x1403712d8  js      loc_1403714D3
0x1403712de  xor     edx, edx; length
0x1403712e0  mov     rcx, [rbp+57h+string]; string
0x1403712e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1403712ea  mov     rcx, rbx
0x1403712ed  inc     rcx
0x1403712f0  cmp     [rax+rcx*2], r12w
0x1403712f5  jnz     short loc_1403712ED
0x1403712f7  movaps  xmm0, xmmword ptr [r15]
0x1403712fb  movdqa  [rbp+57h+var_A0], xmm0
0x140371300  mov     [rbp+57h+var_50], rax
0x140371304  mov     [rbp+57h+var_48], rcx
0x140371308  lea     rdx, [rbp+57h+var_A0]
0x14037130c  lea     rcx, [rbp+57h+var_50]
0x140371310  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x140371315  test    al, al
0x140371317  jnz     loc_1403713F2
0x14037131d  mov     rcx, [rbp+57h+string]; string
0x140371321  test    rcx, rcx
0x140371324  jz      short loc_14037132C
0x140371326  call    cs:__imp_WindowsDeleteString
0x14037132c  mov     [rbp+57h+var_90], r12b
0x140371330  mov     rcx, qword ptr [rbp+57h+var_80]
0x140371334  mov     rax, [rcx]
0x140371337  lea     rdx, [rbp+57h+var_90]
0x14037133b  mov     rax, [rax+40h]
0x14037133f  call    _guard_dispatch_icall
0x140371344  mov     rcx, [rbp+5Fh]; this
0x140371348  test    eax, eax
0x14037134a  js      loc_14037153C
0x140371350  cmp     [rbp+57h+var_90], r12b
0x140371354  jz      short loc_140371360
0x140371356  mov     eax, dword ptr [rbp+57h+var_80+8]
0x140371359  inc     eax
0x14037135b  mov     dword ptr [rbp+57h+var_80+8], eax
0x14037135e  jmp     short loc_140371365
0x140371360  mov     eax, ebx
0x140371362  mov     dword ptr [rbp+57h+var_80+8], ebx
0x140371365  cmp     eax, ebx
0x140371367  jnz     loc_140371276
0x14037136d  mov     rcx, [rbp+57h+var_70]
0x140371371  test    rcx, rcx
0x140371374  jz      short loc_140371387
0x140371376  mov     [rbp+57h+var_70], r12
0x14037137a  mov     rax, [rcx]
0x14037137d  mov     rax, [rax+10h]
0x140371381  call    _guard_dispatch_icall
0x140371386  nop
0x140371387  mov     rcx, qword ptr [rbp+57h+var_80]
0x14037138b  test    rcx, rcx
0x14037138e  jz      short loc_1403713A1
0x140371390  mov     qword ptr [rbp+57h+var_80], r12
0x140371394  mov     rax, [rcx]
0x140371397  mov     rax, [rax+10h]
0x14037139b  call    _guard_dispatch_icall
0x1403713a0  nop
0x1403713a1  mov     [rdi+20h], r12b
0x1403713a5  mov     rcx, [rbp+57h+var_68]
0x1403713a9  test    rcx, rcx
0x1403713ac  jz      short loc_1403713BB
0x1403713ae  mov     rax, [rcx]
0x1403713b1  mov     rax, [rax+10h]
0x1403713b5  call    _guard_dispatch_icall
0x1403713ba  nop
0x1403713bb  mov     rcx, [rbp+57h+var_60]
0x1403713bf  test    rcx, rcx
0x1403713c2  jz      short loc_1403713D1
0x1403713c4  mov     rdx, [rcx]
0x1403713c7  mov     rax, [rdx+10h]
0x1403713cb  call    _guard_dispatch_icall
0x1403713d0  nop
0x1403713d1  mov     rax, rdi
0x1403713d4  mov     rcx, [rbp+57h+var_40]
0x1403713d8  xor     rcx, rsp; StackCookie
0x1403713db  call    __security_check_cookie
0x1403713e0  add     rsp, 0B0h
0x1403713e7  pop     r15
0x1403713e9  pop     r14
0x1403713eb  pop     r12
0x1403713ed  pop     rdi
0x1403713ee  pop     rsi
0x1403713ef  pop     rbx
0x1403713f0  pop     rbp
0x1403713f1  retn
0x1403713f2  mov     [rbp+57h+var_50], r12
0x1403713f6  mov     rcx, [rbp+57h+var_70]
0x1403713fa  mov     rax, [rcx]
0x1403713fd  mov     [rbp+57h+var_50], r12
0x140371401  lea     rdx, [rbp+57h+var_50]
0x140371405  mov     rax, [rax+38h]
0x140371409  call    _guard_dispatch_icall
0x14037140e  mov     rcx, [rbp+5Fh]; this
0x140371412  test    eax, eax
0x140371414  js      loc_140371551
0x14037141a  xor     edx, edx; length
0x14037141c  mov     rcx, [rbp+57h+var_50]; string
0x140371420  call    cs:__imp_WindowsGetStringRawBuffer
0x140371426  xorps   xmm0, xmm0
0x140371429  movups  xmmword ptr [rdi], xmm0
0x14037142c  mov     [rdi+10h], r12
0x140371430  mov     [rdi+18h], r12
0x140371434  inc     rbx
0x140371437  cmp     [rax+rbx*2], r12w
0x14037143c  jnz     short loc_140371434
0x14037143e  mov     r8, rbx
0x140371441  mov     rdx, rax
0x140371444  mov     rcx, rdi
0x140371447  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14037144c  mov     byte ptr [rdi+20h], 1
0x140371450  mov     rcx, [rbp+57h+var_50]; string
0x140371454  test    rcx, rcx
0x140371457  jz      short loc_140371460
0x140371459  call    cs:__imp_WindowsDeleteString
0x14037145f  nop
0x140371460  mov     rcx, [rbp+57h+string]; string
0x140371464  test    rcx, rcx
0x140371467  jz      short loc_140371470
0x140371469  call    cs:__imp_WindowsDeleteString
0x14037146f  nop
0x140371470  mov     rcx, [rbp+57h+var_70]
0x140371474  test    rcx, rcx
0x140371477  jz      short loc_14037148A
0x140371479  mov     [rbp+57h+var_70], r12
0x14037147d  mov     rax, [rcx]
0x140371480  mov     rax, [rax+10h]
0x140371484  call    _guard_dispatch_icall
0x140371489  nop
0x14037148a  mov     rcx, qword ptr [rbp+57h+var_80]
0x14037148e  test    rcx, rcx
0x140371491  jz      short loc_1403714A4
0x140371493  mov     qword ptr [rbp+57h+var_80], r12
0x140371497  mov     rax, [rcx]
0x14037149a  mov     rax, [rax+10h]
0x14037149e  call    _guard_dispatch_icall
0x1403714a3  nop
0x1403714a4  mov     rcx, [rbp+57h+var_68]
0x1403714a8  test    rcx, rcx
0x1403714ab  jz      short loc_1403714BA
0x1403714ad  mov     rax, [rcx]
0x1403714b0  mov     rax, [rax+10h]
0x1403714b4  call    _guard_dispatch_icall
0x1403714b9  nop
0x1403714ba  mov     rcx, [rbp+57h+var_60]
0x1403714be  test    rcx, rcx
0x1403714c1  jz      loc_1403713D1
0x1403714c7  mov     rax, [rcx]
0x1403714ca  mov     rax, [rax+10h]
0x1403714ce  jmp     loc_1403713CB
0x1403714d3  mov     r9d, eax; char *
0x1403714d6  lea     r8, aCW1SSrcOrchest_80; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403714dd  mov     edx, 49h ; 'I'; void *
0x1403714e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1403714e8  mov     r9d, eax; char *
0x1403714eb  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1403714f2  mov     edx, 1C96h; void *
0x1403714f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1403714fd  mov     r9d, eax; char *
0x140371500  lea     r8, aCW1SSrcOrchest_80; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140371507  mov     edx, 41h ; 'A'; void *
0x14037150c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140371512  mov     r9d, eax; char *
0x140371515  lea     r8, aCW1SSrcOrchest_80; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14037151c  mov     edx, 44h ; 'D'; void *
0x140371521  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140371527  mov     r9d, eax; char *
0x14037152a  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140371531  mov     edx, 1C96h; void *
0x140371536  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14037153c  mov     r9d, eax; char *
0x14037153f  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140371546  mov     edx, 1C96h; void *
0x14037154b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140371551  mov     r9d, eax; char *
0x140371554  lea     r8, aCW1SSrcOrchest_80; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14037155b  mov     edx, 4Eh ; 'N'; void *
0x140371560  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
