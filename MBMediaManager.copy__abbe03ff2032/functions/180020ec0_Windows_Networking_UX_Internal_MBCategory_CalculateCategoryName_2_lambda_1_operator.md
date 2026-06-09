# _Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName_::_2_::_lambda_1_::operator()

- ea: `0x180020ec0`
- end: `0x180021167`
- name: `_Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName_::_2_::_lambda_1_::operator()`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c724`

## callees

- `0x180006748`
- `0x180009150`
- `0x18000ad20`
- `0x18000bde0`
- `0x18000e538`
- `0x180011414`
- `0x1800116e0`
- `0x180011be0`
- `0x1800148b8`
- `0x1800148f0`
- `0x18001ad74`
- `0x180020ec0`
- `0x180026380`
- `0x18002cd20`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021134`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021134`

## string_xrefs

- `0x1800210c9`: `GUID=%hs, DataClassName=%ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName_::_2_::_lambda_1_::operator()(
        _QWORD **a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned __int16 *v5; // rsi
  int InterfaceName; // ebx
  __int64 v7; // rdi
  __int64 v8; // r15
  __int64 (__fastcall *v9)(__int64, _QWORD *, LPVOID *, __int16 *); // rbx
  int v10; // eax
  __int64 v11; // rax
  bool v12; // zf
  char v13; // al
  _DWORD *v14; // rcx
  int CategoryDataClassName; // eax
  __int64 v16; // rax
  const WCHAR *v17; // r8
  LPVOID v18; // rdx
  __int16 v20; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  char v27[40]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v28; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v29[2]; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v30[264]; // [rsp+C0h] [rbp-40h] BYREF

  pv = 0;
  v22 = 0;
  v23 = 0;
  v5 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  InterfaceName = 0;
  v7 = -1;
  if ( *((_DWORD *)*a1 + 151) == 2 )
    goto LABEL_11;
  v8 = (*a1)[34];
  if ( !v8 )
    goto LABEL_11;
  v20 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD *, LPVOID *, __int16 *))(*(_QWORD *)v8 + 56LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  v22 = -1;
  v23 = -1;
  v10 = v9(v8, *a1 + 3, &pv, &v20);
  InterfaceName = v10;
  if ( v10 < 0 )
  {
    MBSettingUXLogging::Warn(
      "Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName::<lambda_1>::operator ()",
      3187,
      "GetMbnInterfaceFriendlyName: failed 0x%x",
      v10);
    goto LABEL_7;
  }
  if ( v20 == -1 )
  {
    v11 = MbLoggingHelperGuidToString(v27);
    v28 = *(_OWORD *)v11;
    v29[0] = *(_OWORD *)(v11 + 16);
    *(_DWORD *)((char *)v29 + 15) = *(_DWORD *)(v11 + 31);
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName::<lambda_1>::operator ()",
      3181,
      "GetMbnInterfaceFriendlyName: default name for adapter. Device GUID=%hs",
      (const char *)&v28);
LABEL_7:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::SecureFree(&pv);
  }
  if ( !pv
    || !*(_WORD *)pv
    || (v12 = (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_IsOnlyWhitespace(&pv) == 0,
        v13 = 0,
        !v12) )
  {
LABEL_11:
    v13 = 1;
  }
  v14 = *a1;
  if ( v13 )
  {
    InterfaceName = Windows::Networking::UX::Internal::CategoryBase::GetInterfaceName(
                      (Windows::Networking::UX::Internal::CategoryBase *)v14,
                      (const struct _GUID *)(v14 + 6),
                      v30,
                      a4);
    if ( InterfaceName >= 0 )
      InterfaceName = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                        &pv,
                        v30,
                        -1);
  }
  else
  {
    v25 = -1;
    v26 = -1;
    CategoryDataClassName = Windows::Networking::UX::Internal::MBCategory::tp_GetCategoryDataClassName(
                              (Windows::Networking::UX::Internal::MBCategory *)v14,
                              &v24);
    v5 = v24;
    if ( CategoryDataClassName >= 0 )
    {
      do
        ++v7;
      while ( v24[v7] );
      std::wstring::_Assign<unsigned short>(*a1 + 100, v24);
      if ( !(unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(&v24) )
      {
        v16 = MbLoggingHelperGuidToString(v27);
        v28 = *(_OWORD *)v16;
        v29[0] = *(_OWORD *)(v16 + 16);
        *(_DWORD *)((char *)v29 + 15) = *(_DWORD *)(v16 + 31);
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName::<lambda_1>::operator ()",
          3208,
          "GUID=%hs, DataClassName=%ls",
          (const char *)&v28,
          v5);
        v17 = &sourceString;
        if ( v5 )
          v17 = v5;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
          &pv,
          L" (%ls)",
          v17);
      }
    }
  }
  v18 = pv;
  pv = 0;
  v23 = 0;
  v22 = 0;
  *a1[1] = v18;
  if ( v5 )
    CoTaskMemFree(v5);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)InterfaceName;
}

```

## disassembly

```asm
0x180020ec0  mov     [rsp-8+arg_8], rbx
0x180020ec5  mov     [rsp-8+arg_10], rsi
0x180020eca  push    rbp
0x180020ecb  push    rdi
0x180020ecc  push    r12
0x180020ece  push    r14
0x180020ed0  push    r15
0x180020ed2  lea     rbp, [rsp-1E0h]
0x180020eda  sub     rsp, 2E0h
0x180020ee1  mov     rax, cs:__security_cookie
0x180020ee8  xor     rax, rsp
0x180020eeb  mov     [rbp+200h+var_30], rax
0x180020ef2  mov     r14, rcx
0x180020ef5  xor     r12d, r12d
0x180020ef8  mov     [rsp+300h+pv], r12
0x180020efd  mov     [rsp+300h+var_2C0], r12
0x180020f02  mov     [rsp+300h+var_2B8], r12
0x180020f07  mov     esi, r12d
0x180020f0a  mov     [rsp+300h+var_2B0], r12
0x180020f0f  mov     [rsp+300h+var_2A8], r12
0x180020f14  mov     [rsp+300h+var_2A0], r12
0x180020f19  mov     ebx, r12d
0x180020f1c  mov     rax, [rcx]
0x180020f1f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180020f23  cmp     dword ptr [rax+25Ch], 2
0x180020f2a  jz      loc_180021014
0x180020f30  mov     r15, [rax+110h]
0x180020f37  test    r15, r15
0x180020f3a  jz      loc_180021014
0x180020f40  mov     [rsp+300h+var_2D0], r12w
0x180020f46  mov     rax, [r15]
0x180020f49  mov     rbx, [rax+38h]
0x180020f4d  lea     rcx, [rsp+300h+pv]
0x180020f52  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180020f57  mov     [rsp+300h+var_2C0], rdi
0x180020f5c  mov     [rsp+300h+var_2B8], rdi
0x180020f61  mov     rdx, [r14]
0x180020f64  add     rdx, 18h
0x180020f68  lea     r9, [rsp+300h+var_2D0]
0x180020f6d  lea     r8, [rsp+300h+pv]
0x180020f72  mov     rcx, r15
0x180020f75  mov     rax, rbx
0x180020f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f7d  mov     ebx, eax
0x180020f7f  test    eax, eax
0x180020f81  js      short loc_180020FCE
0x180020f83  cmp     [rsp+300h+var_2D0], di
0x180020f88  jnz     short loc_180020FF3
0x180020f8a  mov     rdx, [r14]
0x180020f8d  add     rdx, 18h
0x180020f91  lea     rcx, [rsp+300h+var_298]; char *
0x180020f96  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x180020f9b  movups  xmm0, xmmword ptr [rax]
0x180020f9e  movups  [rbp+200h+var_270], xmm0
0x180020fa2  movups  xmm1, xmmword ptr [rax+10h]
0x180020fa6  movups  xmmword ptr [rbp+200h+var_260], xmm1
0x180020faa  mov     eax, [rax+1Fh]
0x180020fad  mov     dword ptr [rbp+200h+var_260+0Fh], eax
0x180020fb0  lea     r9, [rbp+200h+var_270]
0x180020fb4  lea     r8, aGetmbninterfac_0; "GetMbnInterfaceFriendlyName: default na"...
0x180020fbb  mov     edx, 0C6Dh; unsigned int
0x180020fc0  lea     rcx, aWindowsNetwork_112; "Windows::Networking::UX::Internal::MBCa"...
0x180020fc7  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180020fcc  jmp     short loc_180020FE9
0x180020fce  mov     r9d, eax
0x180020fd1  lea     r8, aGetmbninterfac; "GetMbnInterfaceFriendlyName: failed 0x%"...
0x180020fd8  mov     edx, 0C73h; unsigned int
0x180020fdd  lea     rcx, aWindowsNetwork_112; "Windows::Networking::UX::Internal::MBCa"...
0x180020fe4  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x180020fe9  lea     rcx, [rsp+300h+pv]
0x180020fee  call    ?SecureFree@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::SecureFree(void)
0x180020ff3  mov     rax, [rsp+300h+pv]
0x180020ff8  test    rax, rax
0x180020ffb  jz      short loc_180021014
0x180020ffd  cmp     [rax], r12w
0x180021001  jz      short loc_180021014
0x180021003  lea     rcx, [rsp+300h+pv]
0x180021008  call    ?_IsOnlyWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_IsOnlyWhitespace(void)
0x18002100d  test    al, al
0x18002100f  mov     al, r12b
0x180021012  jz      short loc_180021016
0x180021014  mov     al, 1
0x180021016  mov     rcx, [r14]; this
0x180021019  test    al, al
0x18002101b  jz      short loc_18002104C
0x18002101d  lea     rdx, [rcx+18h]; struct _GUID *
0x180021021  lea     r8, [rbp+200h+var_240]; unsigned __int16 *
0x180021025  call    ?GetInterfaceName@CategoryBase@Internal@UX@Networking@Windows@@IEAAJAEBU_GUID@@PEAGI@Z; Windows::Networking::UX::Internal::CategoryBase::GetInterfaceName(_GUID const &,ushort *,uint)
0x18002102a  mov     ebx, eax
0x18002102c  test    eax, eax
0x18002102e  js      loc_180021100
0x180021034  mov     r8, rdi
0x180021037  lea     rdx, [rbp+200h+var_240]
0x18002103b  lea     rcx, [rsp+300h+pv]
0x180021040  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180021045  mov     ebx, eax
0x180021047  jmp     loc_180021100
0x18002104c  mov     [rsp+300h+var_2A8], rdi
0x180021051  mov     [rsp+300h+var_2A0], rdi
0x180021056  lea     rdx, [rsp+300h+var_2B0]; unsigned __int16 **
0x18002105b  call    ?tp_GetCategoryDataClassName@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEAPEAG@Z; Windows::Networking::UX::Internal::MBCategory::tp_GetCategoryDataClassName(ushort * *)
0x180021060  mov     rsi, [rsp+300h+var_2B0]
0x180021065  test    eax, eax
0x180021067  js      loc_180021100
0x18002106d  mov     rcx, [r14]
0x180021070  add     rcx, 320h
0x180021077  inc     rdi
0x18002107a  cmp     [rsi+rdi*2], r12w
0x18002107f  jnz     short loc_180021077
0x180021081  mov     r8, rdi
0x180021084  mov     rdx, rsi
0x180021087  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002108c  lea     rcx, [rsp+300h+var_2B0]
0x180021091  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x180021096  test    al, al
0x180021098  jnz     short loc_180021100
0x18002109a  mov     rdx, [r14]
0x18002109d  add     rdx, 18h
0x1800210a1  lea     rcx, [rsp+300h+var_298]; char *
0x1800210a6  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x1800210ab  movups  xmm0, xmmword ptr [rax]
0x1800210ae  movups  [rbp+200h+var_270], xmm0
0x1800210b2  movups  xmm1, xmmword ptr [rax+10h]
0x1800210b6  movups  xmmword ptr [rbp+200h+var_260], xmm1
0x1800210ba  mov     eax, [rax+1Fh]
0x1800210bd  mov     dword ptr [rbp+200h+var_260+0Fh], eax
0x1800210c0  mov     [rsp+300h+var_2E0], rsi
0x1800210c5  lea     r9, [rbp+200h+var_270]
0x1800210c9  lea     r8, aGuidHsDataclas; "GUID=%hs, DataClassName=%ls"
0x1800210d0  mov     edx, 0C88h; unsigned int
0x1800210d5  lea     rcx, aWindowsNetwork_112; "Windows::Networking::UX::Internal::MBCa"...
0x1800210dc  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800210e1  lea     r8, sourceString
0x1800210e8  test    rsi, rsi
0x1800210eb  cmovnz  r8, rsi
0x1800210ef  lea     rdx, aLs; " (%ls)"
0x1800210f6  lea     rcx, [rsp+300h+pv]
0x1800210fb  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180021100  mov     rdx, [rsp+300h+pv]
0x180021105  mov     [rsp+300h+pv], r12
0x18002110a  mov     [rsp+300h+var_2B8], r12
0x18002110f  mov     [rsp+300h+var_2C0], r12
0x180021114  mov     rax, [r14+8]
0x180021118  mov     [rax], rdx
0x18002111b  test    rsi, rsi
0x18002111e  jz      short loc_18002112A
0x180021120  mov     rcx, rsi; pv
0x180021123  call    cs:__imp_CoTaskMemFree
0x180021129  nop
0x18002112a  mov     rcx, [rsp+300h+pv]; pv
0x18002112f  test    rcx, rcx
0x180021132  jz      short loc_18002113A
0x180021134  call    cs:__imp_CoTaskMemFree
0x18002113a  mov     eax, ebx
0x18002113c  mov     rcx, [rbp+200h+var_30]
0x180021143  xor     rcx, rsp; StackCookie
0x180021146  call    __security_check_cookie
0x18002114b  lea     r11, [rsp+300h+var_20]
0x180021153  mov     rbx, [r11+38h]
0x180021157  mov     rsi, [r11+40h]
0x18002115b  mov     rsp, r11
0x18002115e  pop     r15
0x180021160  pop     r14
0x180021162  pop     r12
0x180021164  pop     rdi
0x180021165  pop     rbp
0x180021166  retn
```
