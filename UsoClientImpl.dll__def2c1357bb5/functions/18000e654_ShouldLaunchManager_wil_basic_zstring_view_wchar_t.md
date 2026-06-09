# ShouldLaunchManager(wil::basic_zstring_view<wchar_t>)

- ea: `0x18000e654`
- end: `0x18000eca0`
- name: `?ShouldLaunchManager@@YA_NV?$basic_zstring_view@_W@wil@@@Z`
- size: `1612`
- prototype: `char __fastcall(__int128 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x18000175c`
- `0x180009380`
- `0x18000a2ac`
- `0x18000ccf8`
- `0x18000d57c`
- `0x18000d6a8`
- `0x18000d948`
- `0x18000e654`
- `0x18001932c`
- `0x1800194f8`
- `0x1800332c0`
- `0x18003359c`
- `0x180033f14`
- `0x180036b10`
- `0x18003a204`
- `0x180056500`
- `0x180056524`
- `0x18005c5e0`
- `0x18005c660`

## string_xrefs

- `0x18000e6f0`: `StartOobeAppsScanAfterUpdate`
- `0x18000eb9c`: `No change in Build Number or UBR.  Ignoring Oobe Apps post update trigger.`
- `0x18000ec20`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000ec36`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000ec4c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000ec62`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000ec78`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000ec8e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall ShouldLaunchManager(__int128 *a1)
{
  __int64 traits_2_unsigned_short; // rax
  const char *v3; // r9
  __int64 v4; // r11
  __int64 v5; // rax
  __int64 v6; // rax
  const char *v7; // r9
  __int64 v8; // r11
  __int64 v9; // rax
  int *v10; // rax
  const char *v11; // r9
  __int64 v12; // rax
  int *v13; // rax
  const char *v14; // r9
  __int64 v15; // rax
  char *v16; // rdi
  __int64 v17; // rax
  const char *v18; // r9
  __int64 v19; // r11
  __int64 v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // rcx
  volatile signed __int32 *v23; // rbx
  volatile signed __int32 *v25; // rbx
  __int64 v26; // rax
  const char *v27; // r9
  __int64 v28; // r11
  __int64 v29; // rax
  _QWORD *v30; // rax
  __int64 v31[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v32[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v33; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v34[2]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE Src[32]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v36[18]; // [rsp+98h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"StartOobeScan",
                              &dword_1800682CC,
                              0);
  if ( traits_2_unsigned_short == v4 || (v5 = (traits_2_unsigned_short - (__int64)L"StartOobeScan") >> 1, v5 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v3);
  v32[0] = (__int64)L"StartOobeScan";
  v32[1] = v5;
  *(_OWORD *)v31 = *(_OWORD *)v32;
  v33 = *a1;
  if ( (unsigned __int8)Strings::iequals(&v33, v31) )
    goto LABEL_57;
  v6 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
         L"StartOobeAppsScanAfterUpdate",
         word_18006830A,
         0);
  if ( v6 == v8 || (v9 = (v6 - (__int64)L"StartOobeAppsScanAfterUpdate") >> 1, v9 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v7);
  v32[0] = (__int64)L"StartOobeAppsScanAfterUpdate";
  v32[1] = v9;
  *(_OWORD *)v31 = *(_OWORD *)v32;
  v33 = *a1;
  if ( (unsigned __int8)Strings::iequals(&v33, v31) )
    goto LABEL_57;
  v10 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                 L"StartOobeAppsScan",
                 &dword_180068334,
                 0);
  if ( v10 == &dword_180068334 || (v12 = ((char *)v10 - (char *)L"StartOobeAppsScan") >> 1, v12 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v11);
  v32[0] = (__int64)L"StartOobeAppsScan";
  v32[1] = v12;
  *(_OWORD *)v31 = *(_OWORD *)v32;
  v33 = *a1;
  if ( (unsigned __int8)Strings::iequals(&v33, v31) )
  {
LABEL_57:
    if ( OobeAppsScanIsDisabled() )
      return 0;
  }
  v13 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                 L"StartOobeAppsScan",
                 &dword_180068334,
                 0);
  if ( v13 == &dword_180068334 || (v15 = ((char *)v13 - (char *)L"StartOobeAppsScan") >> 1, v15 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v14);
  v32[0] = (__int64)L"StartOobeAppsScan";
  v32[1] = v15;
  *(_OWORD *)v31 = *(_OWORD *)v32;
  v33 = *a1;
  if ( (unsigned __int8)Strings::iequals(&v33, v31) )
  {
    v16 = (char *)operator new(0x18u);
    *(_OWORD *)v16 = 0;
    *((_DWORD *)v16 + 2) = 1;
    *((_DWORD *)v16 + 3) = 1;
    *(_QWORD *)v16 = &std::_Ref_count_obj2<Windows::Registry>::`vftable';
    *((_QWORD *)v16 + 2) = &Windows::Registry::`vftable';
    *(_QWORD *)&v33 = v16 + 16;
    *((_QWORD *)&v33 + 1) = v16;
    memset(v36, 0, sizeof(v36));
    *(_OWORD *)v32 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v16 + 2);
    v32[0] = (__int64)(v16 + 16);
    v32[1] = (__int64)v16;
    Windows::Settings::Settings(v36, v32, 0);
    v17 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"OobeAppsScanEnabled",
            L"OobeAppsScan disabled via OneSettings.",
            0);
    if ( v17 == v19 || (v20 = (v17 - (__int64)L"OobeAppsScanEnabled") >> 1, v20 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v18);
    v31[0] = (__int64)L"OobeAppsScanEnabled";
    v31[1] = v20;
    LODWORD(v34[0]) = 1;
    if ( (unsigned int)Windows::Settings::GetSettingOrDefault(v36, v31, v34) != 1 )
    {
      v34[0] = (__int64)L"OobeAppsScan disabled via OneSettings.";
      v34[1] = 38;
      *(_OWORD *)v31 = 0u;
      v21 = (_QWORD *)std::vformat<0>(Src);
      if ( v21[3] > 7u )
        v21 = (_QWORD *)*v21;
      v34[0] = (__int64)v21;
      ClientTelemetry::Message<wchar_t const *>(v34);
      std::wstring::~wstring(Src);
LABEL_25:
      std::wstring::~wstring(&v36[13]);
      v23 = (volatile signed __int32 *)v36[12];
      if ( v36[12] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v36[12] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
      if ( !_InterlockedDecrement((volatile signed __int32 *)v16 + 2) )
      {
        (**(void (__fastcall ***)(void *))v16)(v16);
        if ( !_InterlockedDecrement((volatile signed __int32 *)v16 + 3) )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
      }
      return 0;
    }
    if ( WillEulaPageBeShown() )
    {
      v22 = *((_QWORD *)ClientTelemetry::Instance() + 1);
      if ( *(_DWORD *)v22 > 5u
        && (*(_QWORD *)(v22 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v22 + 24) & 0x400000000000LL) == *(_QWORD *)(v22 + 24) )
      {
        v34[0] = (__int64)"1507.2603.28012.0";
        v32[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v22,
          (__int64)v32,
          (__int64)v34);
      }
      goto LABEL_25;
    }
    std::wstring::~wstring(&v36[13]);
    v25 = (volatile signed __int32 *)v36[12];
    if ( v36[12] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v36[12] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v16)(v16);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  v26 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
          L"StartOobeAppsScanAfterUpdate",
          word_18006830A,
          0);
  if ( v26 == v28 || (v29 = (v26 - (__int64)L"StartOobeAppsScanAfterUpdate") >> 1, v29 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v27);
  v31[0] = (__int64)L"StartOobeAppsScanAfterUpdate";
  v31[1] = v29;
  v33 = *a1;
  if ( (unsigned __int8)Strings::iequals(&v33, v31) && !HasOsRevisionIncreased() && !HasOsBuildNumberIncreased() )
  {
    *(_QWORD *)&v33 = L"No change in Build Number or UBR.  Ignoring Oobe Apps post update trigger.";
    *((_QWORD *)&v33 + 1) = 74;
    *(_OWORD *)v31 = 0u;
    v30 = (_QWORD *)std::vformat<0>(Src);
    if ( v30[3] > 7u )
      v30 = (_QWORD *)*v30;
    v32[0] = (__int64)v30;
    ClientTelemetry::Message<wchar_t const *>(v32);
    std::wstring::~wstring(Src);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000e654  mov     rax, rsp
0x18000e657  mov     [rax+10h], rbx
0x18000e65b  mov     [rax+18h], rsi
0x18000e65f  mov     [rax+20h], rdi
0x18000e663  push    rbp
0x18000e664  push    r12
0x18000e666  push    r14
0x18000e668  lea     rbp, [rax-48h]
0x18000e66c  sub     rsp, 130h
0x18000e673  mov     rax, cs:__security_cookie
0x18000e67a  xor     rax, rsp
0x18000e67d  mov     [rbp+40h+var_20], rax
0x18000e681  mov     rsi, rcx
0x18000e684  xor     r8d, r8d
0x18000e687  lea     r11, dword_1800682CC
0x18000e68e  mov     rdx, r11
0x18000e691  lea     rbx, aStartoobescan; "StartOobeScan"
0x18000e698  mov     rcx, rbx
0x18000e69b  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e6a0  cmp     rax, r11
0x18000e6a3  jz      loc_18000EC32
0x18000e6a9  sub     rax, rbx
0x18000e6ac  sar     rax, 1
0x18000e6af  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000e6b3  cmp     rax, r14
0x18000e6b6  jz      loc_18000EC32
0x18000e6bc  mov     [rsp+140h+var_108+8], rbx
0x18000e6c1  mov     qword ptr [rsp+140h+var_F8], rax
0x18000e6c6  movaps  xmm0, xmmword ptr [rsp+140h+var_108+8]
0x18000e6cb  movdqa  xmmword ptr [rsp+140h+var_118+8], xmm0
0x18000e6d1  movaps  xmm1, xmmword ptr [rsi]
0x18000e6d4  movdqa  [rsp+140h+var_F8+8], xmm1
0x18000e6da  lea     rdx, [rsp+140h+var_118+8]
0x18000e6df  lea     rcx, [rsp+140h+var_F8+8]
0x18000e6e4  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000e6e9  lea     r11, word_18006830A
0x18000e6f0  lea     r12, aStartoobeappss_0; "StartOobeAppsScanAfterUpdate"
0x18000e6f7  lea     rdi, dword_180068334
0x18000e6fe  lea     rbx, aStartoobeappss; "StartOobeAppsScan"
0x18000e705  test    al, al
0x18000e707  jnz     loc_18000E7BB
0x18000e70d  xor     r8d, r8d
0x18000e710  mov     rdx, r11
0x18000e713  mov     rcx, r12
0x18000e716  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e71b  cmp     rax, r11
0x18000e71e  jz      loc_18000EC5E
0x18000e724  sub     rax, r12
0x18000e727  sar     rax, 1
0x18000e72a  cmp     rax, r14
0x18000e72d  jz      loc_18000EC5E
0x18000e733  mov     [rsp+140h+var_108+8], r12
0x18000e738  mov     qword ptr [rsp+140h+var_F8], rax
0x18000e73d  movaps  xmm0, xmmword ptr [rsp+140h+var_108+8]
0x18000e742  movdqa  xmmword ptr [rsp+140h+var_118+8], xmm0
0x18000e748  movaps  xmm1, xmmword ptr [rsi]
0x18000e74b  movdqa  [rsp+140h+var_F8+8], xmm1
0x18000e751  lea     rdx, [rsp+140h+var_118+8]
0x18000e756  lea     rcx, [rsp+140h+var_F8+8]
0x18000e75b  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000e760  test    al, al
0x18000e762  jnz     short loc_18000E7BB
0x18000e764  xor     r8d, r8d
0x18000e767  mov     rdx, rdi
0x18000e76a  mov     rcx, rbx
0x18000e76d  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e772  cmp     rax, rdi
0x18000e775  jz      loc_18000EC48
0x18000e77b  sub     rax, rbx
0x18000e77e  sar     rax, 1
0x18000e781  cmp     rax, r14
0x18000e784  jz      loc_18000EC48
0x18000e78a  mov     [rsp+140h+var_108+8], rbx
0x18000e78f  mov     qword ptr [rsp+140h+var_F8], rax
0x18000e794  movaps  xmm0, xmmword ptr [rsp+140h+var_108+8]
0x18000e799  movdqa  xmmword ptr [rsp+140h+var_118+8], xmm0
0x18000e79f  movaps  xmm1, xmmword ptr [rsi]
0x18000e7a2  movdqa  [rsp+140h+var_F8+8], xmm1
0x18000e7a8  lea     rdx, [rsp+140h+var_118+8]
0x18000e7ad  lea     rcx, [rsp+140h+var_F8+8]
0x18000e7b2  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000e7b7  test    al, al
0x18000e7b9  jz      short loc_18000E7C8
0x18000e7bb  call    ?OobeAppsScanIsDisabled@@YA_NXZ; OobeAppsScanIsDisabled(void)
0x18000e7c0  test    al, al
0x18000e7c2  jnz     loc_18000EA78
0x18000e7c8  xor     r8d, r8d
0x18000e7cb  mov     rdx, rdi
0x18000e7ce  mov     rcx, rbx
0x18000e7d1  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e7d6  cmp     rax, rdi
0x18000e7d9  jz      loc_18000EC1C
0x18000e7df  sub     rax, rbx
0x18000e7e2  sar     rax, 1
0x18000e7e5  cmp     rax, r14
0x18000e7e8  jz      loc_18000EC1C
0x18000e7ee  mov     [rsp+140h+var_108+8], rbx
0x18000e7f3  mov     qword ptr [rsp+140h+var_F8], rax
0x18000e7f8  movaps  xmm0, xmmword ptr [rsp+140h+var_108+8]
0x18000e7fd  movdqa  xmmword ptr [rsp+140h+var_118+8], xmm0
0x18000e803  movaps  xmm1, xmmword ptr [rsi]
0x18000e806  movdqa  [rsp+140h+var_F8+8], xmm1
0x18000e80c  lea     rdx, [rsp+140h+var_118+8]
0x18000e811  lea     rcx, [rsp+140h+var_F8+8]
0x18000e816  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000e81b  test    al, al
0x18000e81d  jz      loc_18000EB24
0x18000e823  mov     ecx, 18h; Size
0x18000e828  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e82d  mov     rdi, rax
0x18000e830  mov     [rsp+140h+var_108+8], rax
0x18000e835  xorps   xmm0, xmm0
0x18000e838  movups  xmmword ptr [rax], xmm0
0x18000e83b  mov     dword ptr [rax+8], 1
0x18000e842  mov     dword ptr [rax+0Ch], 1
0x18000e849  lea     rax, ??_7?$_Ref_count_obj2@VRegistry@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Registry>::`vftable'
0x18000e850  mov     [rdi], rax
0x18000e853  lea     rbx, [rdi+10h]
0x18000e857  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x18000e85e  mov     [rbx], rax
0x18000e861  movups  [rsp+140h+var_F8+8], xmm0
0x18000e866  mov     qword ptr [rsp+140h+var_F8+8], rbx
0x18000e86b  mov     [rsp+140h+var_E8], rdi
0x18000e870  xor     edx, edx; Val
0x18000e872  mov     r8d, 90h; Size
0x18000e878  lea     rcx, [rbp+40h+var_B0]; void *
0x18000e87c  call    memset
0x18000e881  xorps   xmm0, xmm0
0x18000e884  movdqu  xmmword ptr [rsp+140h+var_108+8], xmm0
0x18000e88a  lock inc dword ptr [rdi+8]
0x18000e88e  mov     [rsp+140h+var_108+8], rbx
0x18000e893  mov     qword ptr [rsp+140h+var_F8], rdi
0x18000e898  xor     r8d, r8d
0x18000e89b  lea     rdx, [rsp+140h+var_108+8]
0x18000e8a0  lea     rcx, [rbp+40h+var_B0]
0x18000e8a4  call    ??0Settings@Windows@@QEAA@V?$shared_ptr@VRegistry@SystemInterface@@@std@@_N@Z; Windows::Settings::Settings(std::shared_ptr<SystemInterface::Registry>,bool)
0x18000e8a9  nop
0x18000e8aa  xor     r8d, r8d
0x18000e8ad  lea     r11, aOobeappsscanDi; "OobeAppsScan disabled via OneSettings."
0x18000e8b4  mov     rdx, r11
0x18000e8b7  lea     rbx, aOobeappsscanen; "OobeAppsScanEnabled"
0x18000e8be  mov     rcx, rbx
0x18000e8c1  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e8c6  cmp     rax, r11
0x18000e8c9  jz      loc_18000EC74
0x18000e8cf  sub     rax, rbx
0x18000e8d2  sar     rax, 1
0x18000e8d5  cmp     rax, r14
0x18000e8d8  jz      loc_18000EC74
0x18000e8de  mov     [rsp+140h+var_118+8], rbx
0x18000e8e3  mov     [rsp+140h+var_108], rax
0x18000e8e8  mov     dword ptr [rsp+140h+var_E8+8], 1
0x18000e8f0  movaps  xmm0, xmmword ptr [rsp+140h+var_118+8]
0x18000e8f5  movdqa  xmmword ptr [rsp+140h+var_118+8], xmm0
0x18000e8fb  lea     r8, [rsp+140h+var_E8+8]
0x18000e900  lea     rdx, [rsp+140h+var_118+8]
0x18000e905  lea     rcx, [rbp+40h+var_B0]
0x18000e909  call    ?GetSettingOrDefault@Settings@Windows@@UEAAIV?$basic_zstring_view@_W@wil@@AEBI@Z; Windows::Settings::GetSettingOrDefault(wil::basic_zstring_view<wchar_t>,uint const &)
0x18000e90e  cmp     eax, 1
0x18000e911  jz      short loc_18000E989
0x18000e913  lea     rax, aOobeappsscanDi; "OobeAppsScan disabled via OneSettings."
0x18000e91a  mov     [rsp+140h+var_E8+8], rax
0x18000e91f  mov     qword ptr [rsp+140h+var_D8], 26h ; '&'
0x18000e928  mov     [rsp+140h+var_118+8], 0
0x18000e931  mov     [rsp+140h+var_108], 0
0x18000e93a  movaps  xmm0, xmmword ptr [rsp+140h+var_118+8]
0x18000e93f  movdqa  xmmword ptr [rsp+140h+var_118+8], xmm0
0x18000e945  movaps  xmm1, xmmword ptr [rsp+140h+var_E8+8]
0x18000e94a  movdqa  xmmword ptr [rsp+140h+var_E8+8], xmm1
0x18000e950  lea     r8, [rsp+140h+var_118+8]
0x18000e955  lea     rdx, [rsp+140h+var_E8+8]
0x18000e95a  lea     rcx, [rsp+140h+Src]; Src
0x18000e95f  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18000e964  cmp     qword ptr [rax+18h], 7
0x18000e969  jbe     short loc_18000E96E
0x18000e96b  mov     rax, [rax]
0x18000e96e  mov     [rsp+140h+var_E8+8], rax
0x18000e973  lea     rcx, [rsp+140h+var_E8+8]
0x18000e978  call    ??$Message@PEB_W@ClientTelemetry@@SAX$$QEAPEB_W@Z; ClientTelemetry::Message<wchar_t const *>(wchar_t const * &&)
0x18000e97d  lea     rcx, [rsp+140h+Src]; void *
0x18000e982  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e987  jmp     short loc_18000E9F7
0x18000e989  call    ?WillEulaPageBeShown@@YA_NXZ; WillEulaPageBeShown(void)
0x18000e98e  test    al, al
0x18000e990  jz      loc_18000EAA3
0x18000e996  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000e99b  mov     rcx, [rax+8]; int
0x18000e99f  cmp     dword ptr [rcx], 5
0x18000e9a2  jbe     short loc_18000E9F7
0x18000e9a4  mov     rdx, 400000000000h
0x18000e9ae  test    [rcx+10h], rdx
0x18000e9b2  jz      short loc_18000E9F7
0x18000e9b4  mov     rax, [rcx+18h]
0x18000e9b8  and     rax, rdx
0x18000e9bb  cmp     rax, [rcx+18h]
0x18000e9bf  jnz     short loc_18000E9F7
0x18000e9c1  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18000e9c8  mov     [rsp+140h+var_E8+8], rax
0x18000e9cd  mov     [rsp+140h+var_108+8], 1000000h
0x18000e9d6  lea     rax, [rsp+140h+var_E8+8]
0x18000e9db  mov     [rsp+140h+var_118], rax; __int64
0x18000e9e0  lea     rax, [rsp+140h+var_108+8]
0x18000e9e5  mov     [rsp+140h+var_120], rax; __int64
0x18000e9ea  lea     rdx, word_1800907AA
0x18000e9f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18000e9f6  nop
0x18000e9f7  lea     rcx, [rbp+40h+var_48]; void *
0x18000e9fb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ea00  mov     rbx, [rbp+40h+var_50]
0x18000ea04  test    rbx, rbx
0x18000ea07  jz      short loc_18000EA41
0x18000ea09  mov     eax, r14d
0x18000ea0c  lock xadd [rbx+8], eax
0x18000ea11  add     eax, r14d
0x18000ea14  jnz     short loc_18000EA41
0x18000ea16  mov     rax, [rbx]
0x18000ea19  mov     rcx, rbx
0x18000ea1c  mov     rax, [rax]
0x18000ea1f  call    _guard_dispatch_icall
0x18000ea24  mov     eax, r14d
0x18000ea27  lock xadd [rbx+0Ch], eax
0x18000ea2c  add     eax, r14d
0x18000ea2f  jnz     short loc_18000EA41
0x18000ea31  mov     rax, [rbx]
0x18000ea34  mov     rcx, rbx
0x18000ea37  mov     rax, [rax+8]
0x18000ea3b  call    _guard_dispatch_icall
0x18000ea40  nop
0x18000ea41  mov     eax, r14d
0x18000ea44  lock xadd [rdi+8], eax
0x18000ea49  add     eax, r14d
0x18000ea4c  jnz     short loc_18000EA78
0x18000ea4e  mov     rax, [rdi]
0x18000ea51  mov     rcx, rdi
0x18000ea54  mov     rax, [rax]
0x18000ea57  call    _guard_dispatch_icall
0x18000ea5c  mov     eax, r14d
0x18000ea5f  lock xadd [rdi+0Ch], eax
0x18000ea64  add     eax, r14d
0x18000ea67  jnz     short loc_18000EA78
0x18000ea69  mov     rax, [rdi]
0x18000ea6c  mov     rcx, rdi
0x18000ea6f  mov     rax, [rax+8]
0x18000ea73  call    _guard_dispatch_icall
0x18000ea78  xor     al, al
0x18000ea7a  mov     rcx, [rbp+40h+var_20]
0x18000ea7e  xor     rcx, rsp; StackCookie
0x18000ea81  call    __security_check_cookie
0x18000ea86  lea     r11, [rsp+140h+var_10]
0x18000ea8e  mov     rbx, [r11+28h]
0x18000ea92  mov     rsi, [r11+30h]
0x18000ea96  mov     rdi, [r11+38h]
0x18000ea9a  mov     rsp, r11
0x18000ea9d  pop     r14
0x18000ea9f  pop     r12
0x18000eaa1  pop     rbp
0x18000eaa2  retn
0x18000eaa3  lea     rcx, [rbp+40h+var_48]; void *
0x18000eaa7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eaac  mov     rbx, [rbp+40h+var_50]
0x18000eab0  test    rbx, rbx
0x18000eab3  jz      short loc_18000EAED
0x18000eab5  mov     eax, r14d
0x18000eab8  lock xadd [rbx+8], eax
0x18000eabd  add     eax, r14d
0x18000eac0  jnz     short loc_18000EAED
0x18000eac2  mov     rax, [rbx]
0x18000eac5  mov     rcx, rbx
0x18000eac8  mov     rax, [rax]
0x18000eacb  call    _guard_dispatch_icall
0x18000ead0  mov     eax, r14d
0x18000ead3  lock xadd [rbx+0Ch], eax
0x18000ead8  add     eax, r14d
0x18000eadb  jnz     short loc_18000EAED
0x18000eadd  mov     rax, [rbx]
0x18000eae0  mov     rcx, rbx
0x18000eae3  mov     rax, [rax+8]
0x18000eae7  call    _guard_dispatch_icall
0x18000eaec  nop
0x18000eaed  mov     eax, r14d
0x18000eaf0  lock xadd [rdi+8], eax
0x18000eaf5  add     eax, r14d
0x18000eaf8  jnz     short loc_18000EB24
0x18000eafa  mov     rax, [rdi]
0x18000eafd  mov     rcx, rdi
0x18000eb00  mov     rax, [rax]
0x18000eb03  call    _guard_dispatch_icall
0x18000eb08  mov     eax, r14d
0x18000eb0b  lock xadd [rdi+0Ch], eax
0x18000eb10  add     eax, r14d
0x18000eb13  jnz     short loc_18000EB24
0x18000eb15  mov     rax, [rdi]
0x18000eb18  mov     rcx, rdi
0x18000eb1b  mov     rax, [rax+8]
0x18000eb1f  call    _guard_dispatch_icall
0x18000eb24  xor     r8d, r8d
0x18000eb27  lea     r11, word_18006830A
0x18000eb2e  mov     rdx, r11
0x18000eb31  mov     rcx, r12
0x18000eb34  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
  ... truncated ...
```
