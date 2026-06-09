# RequestConsentResponse

- ea: `0x1800b6080`
- end: `0x1800b643f`
- name: `RequestConsentResponse`
- size: `959`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001c5fc`
- `0x18001d00c`
- `0x180020fcc`
- `0x18002392c`
- `0x1800257ec`
- `0x18002a564`
- `0x18002a5d4`
- `0x18003cf4c`
- `0x18003e21c`
- `0x18006ca84`
- `0x18006f230`
- `0x1800b52fc`
- `0x1800b6080`
- `0x1800b6514`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b6175`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b6175`
- `FLTLIB!FilterGetDosName` at `0x1800b62d5`
- `FLTLIB!FilterGetDosName` at `0x1800b62d5`

## string_xrefs

- `0x1800b6115`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b6137`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b615b`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b6192`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b61b4`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b62ea`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall RequestConsentResponse(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        __int64 a5,
        DWORD dwProcessId,
        _DWORD *a7)
{
  int v10; // eax
  char v11; // bl
  HRESULT v12; // eax
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *v15; // rdi
  __int64 v16; // rax
  char v17; // bl
  int v18; // edi
  _BOOL8 v19; // r9
  int v21; // [rsp+20h] [rbp-318h]
  int v22; // [rsp+20h] [rbp-318h]
  int v23[2]; // [rsp+48h] [rbp-2F0h] BYREF
  std::_Ref_count_base *v24; // [rsp+50h] [rbp-2E8h]
  _QWORD v25[4]; // [rsp+58h] [rbp-2E0h] BYREF
  _BYTE v26[32]; // [rsp+78h] [rbp-2C0h] BYREF
  _BYTE v27[32]; // [rsp+98h] [rbp-2A0h] BYREF
  int v28[10]; // [rsp+B8h] [rbp-280h] BYREF
  WCHAR DosName[264]; // [rsp+E0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ba398d49f73833a47629aaaf6d810685_Traceguids);
  }
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
      (const char *)0x80070057LL,
      v21);
  if ( !a7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
      (const char *)0x80004003LL,
      v21);
  if ( !dwProcessId )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
      (const char *)0x80070057LL,
      v21);
  if ( !(unsigned int)_o__wcsicmp(a2, L"appSiloFileSystem") )
  {
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
        (const char *)0x80070057LL,
        v21);
  }
  EnsureCallerIsKernelMode();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dSSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a5, (__int64)a4);
  }
  std::wstring::wstring(v28, a2);
  if ( a3 )
  {
    v10 = std::wstring::wstring(v27, a3);
    v11 = 1;
  }
  else
  {
    v10 = std::wstring::wstring(v26);
    v11 = 2;
  }
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateWithProcessId(
    (int)v23,
    v10,
    (int)v28,
    dwProcessId,
    0,
    1);
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    std::wstring::_Tidy_deallocate(v26);
  }
  if ( (v11 & 1) != 0 )
  {
    v11 &= ~1u;
    std::wstring::_Tidy_deallocate(v27);
  }
  std::wstring::_Tidy_deallocate(v28);
  std::wstring::wstring(v25);
  if ( a4 )
  {
    memset_0(DosName, 0, 0x208u);
    v12 = FilterGetDosName(a4, DosName, 0x104u);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
        (const char *)(unsigned int)v12,
        v22);
    v13 = std::_WChar_traits<unsigned short>::length(DosName);
    std::wstring::_Assign<unsigned short>((__int64)v25, (__int64)DosName, v13);
    std::wstring::resize(v25, v25[2]);
  }
  if ( a5 )
  {
    v14 = std::_WChar_traits<unsigned short>::length(a5);
    std::wstring::_Append<unsigned short>(v25, a5, v14);
  }
  v15 = *(Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager **)v23;
  if ( a3 )
  {
    v16 = std::wstring::wstring(v26, a3);
    v17 = v11 | 4;
  }
  else
  {
    v16 = std::wstring::wstring(v27);
    v17 = v11 | 8;
  }
  v18 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::HandlePromptForUserWithAdditionalContext(
          v15,
          v16,
          (int)v25,
          0,
          3u);
  if ( (v17 & 8) != 0 )
  {
    v17 &= ~8u;
    std::wstring::_Tidy_deallocate(v27);
  }
  if ( (v17 & 4) != 0 )
    std::wstring::_Tidy_deallocate(v26);
  v19 = v18 != 1;
  *a7 = v19;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ba398d49f73833a47629aaaf6d810685_Traceguids, v19);
  }
  std::wstring::_Tidy_deallocate(v25);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  return 0;
}

```

## disassembly

```asm
0x1800b6080  push    rbx
0x1800b6082  push    rsi
0x1800b6083  push    rdi
0x1800b6084  push    r12
0x1800b6086  push    r13
0x1800b6088  push    r14
0x1800b608a  push    r15
0x1800b608c  sub     rsp, 300h
0x1800b6093  mov     rax, cs:__security_cookie
0x1800b609a  xor     rax, rsp
0x1800b609d  mov     [rsp+338h+var_48], rax
0x1800b60a5  mov     r14, r9
0x1800b60a8  mov     rsi, r8
0x1800b60ab  mov     rbx, rdx
0x1800b60ae  mov     r15d, [rsp+338h+dwProcessId]
0x1800b60b6  mov     rdi, [rsp+338h+arg_20]
0x1800b60be  mov     r12, [rsp+338h+arg_30]
0x1800b60c6  mov     [rsp+338h+var_2F8], 0
0x1800b60ce  lea     r13, WPP_GLOBAL_Control
0x1800b60d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b60dc  cmp     rcx, r13
0x1800b60df  jz      short loc_1800B6102
0x1800b60e1  test    byte ptr [rcx+1Ch], 1
0x1800b60e5  jz      short loc_1800B6102
0x1800b60e7  cmp     byte ptr [rcx+19h], 5
0x1800b60eb  jb      short loc_1800B6102
0x1800b60ed  mov     edx, 0Bh
0x1800b60f2  lea     r8, WPP_ba398d49f73833a47629aaaf6d810685_Traceguids
0x1800b60f9  mov     rcx, [rcx+10h]
0x1800b60fd  call    WPP_SF_
0x1800b6102  mov     rcx, [rsp+338h]; this
0x1800b610a  test    rbx, rbx
0x1800b610d  jnz     short loc_1800B6124
0x1800b610f  mov     r9d, 80070057h; char *
0x1800b6115  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b611c  lea     edx, [rbx+3Bh]; void *
0x1800b611f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b6124  mov     rcx, [rsp+338h]; this
0x1800b612c  test    r12, r12
0x1800b612f  jnz     short loc_1800B6148
0x1800b6131  mov     r9d, 80004003h; char *
0x1800b6137  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b613e  lea     edx, [r12+3Ch]; void *
0x1800b6143  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b6148  mov     rcx, [rsp+338h]; this
0x1800b6150  test    r15d, r15d
0x1800b6153  jnz     short loc_1800B616B
0x1800b6155  mov     r9d, 80070057h; char *
0x1800b615b  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b6162  lea     edx, [r15+3Dh]; void *
0x1800b6166  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b616b  lea     rdx, aAppsilofilesys; "appSiloFileSystem"
0x1800b6172  mov     rcx, rbx
0x1800b6175  call    cs:__imp__o__wcsicmp
0x1800b617b  test    eax, eax
0x1800b617d  jnz     short loc_1800B61C4
0x1800b617f  mov     rcx, [rsp+338h]; this
0x1800b6187  test    rdi, rdi
0x1800b618a  jnz     short loc_1800B61A1
0x1800b618c  mov     r9d, 80070057h; char *
0x1800b6192  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b6199  lea     edx, [rax+42h]; void *
0x1800b619c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b61a1  mov     rcx, [rsp+338h]; this
0x1800b61a9  test    r14, r14
0x1800b61ac  jnz     short loc_1800B61C4
0x1800b61ae  mov     r9d, 80070057h; char *
0x1800b61b4  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b61bb  lea     edx, [r14+43h]; void *
0x1800b61bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b61c4  call    ?EnsureCallerIsKernelMode@@YAXXZ; EnsureCallerIsKernelMode(void)
0x1800b61c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b61d0  cmp     rcx, r13
0x1800b61d3  jz      short loc_1800B6201
0x1800b61d5  test    byte ptr [rcx+1Ch], 1
0x1800b61d9  jz      short loc_1800B6201
0x1800b61db  cmp     byte ptr [rcx+19h], 4
0x1800b61df  jb      short loc_1800B6201
0x1800b61e1  mov     [rsp+338h+var_300], r14; __int64
0x1800b61e6  mov     [rsp+338h+var_308], rdi; __int64
0x1800b61eb  mov     qword ptr [rsp+338h+var_310], rsi; __int64
0x1800b61f0  mov     [rsp+338h+var_318], rbx; __int64
0x1800b61f5  mov     r9d, r15d
0x1800b61f8  mov     rcx, [rcx+10h]; LoggerHandle
0x1800b61fc  call    WPP_SF_dSSSS
0x1800b6201  mov     rdx, rbx
0x1800b6204  lea     rcx, [rsp+338h+var_280]
0x1800b620c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b6211  nop
0x1800b6212  test    rsi, rsi
0x1800b6215  jz      short loc_1800B622F
0x1800b6217  mov     rdx, rsi
0x1800b621a  lea     rcx, [rsp+338h+var_2A0]
0x1800b6222  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b6227  nop
0x1800b6228  mov     ebx, 1
0x1800b622d  jmp     short loc_1800B623F
0x1800b622f  lea     rcx, [rsp+338h+var_2C0]
0x1800b6234  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b6239  nop
0x1800b623a  mov     ebx, 2
0x1800b623f  mov     [rsp+338h+var_2F8], ebx
0x1800b6243  mov     [rsp+338h+var_310], 1; char
0x1800b6248  mov     dword ptr [rsp+338h+var_318], 0; int
0x1800b6250  mov     r9d, r15d; dwProcessId
0x1800b6253  lea     r8, [rsp+338h+var_280]; int
0x1800b625b  mov     rdx, rax; int
0x1800b625e  lea     rcx, [rsp+338h+var_2F0]; int
0x1800b6263  call    ?CreateWithProcessId@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0KK_N@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateWithProcessId(std::wstring const &,std::wstring const &,ulong,ulong,bool)
0x1800b6268  nop
0x1800b6269  test    bl, 2
0x1800b626c  jz      short loc_1800B627C
0x1800b626e  and     ebx, 0FFFFFFFDh
0x1800b6271  lea     rcx, [rsp+338h+var_2C0]
0x1800b6276  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b627b  nop
0x1800b627c  test    bl, 1
0x1800b627f  jz      short loc_1800B6292
0x1800b6281  and     ebx, 0FFFFFFFEh
0x1800b6284  lea     rcx, [rsp+338h+var_2A0]
0x1800b628c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6291  nop
0x1800b6292  lea     rcx, [rsp+338h+var_280]
0x1800b629a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b629f  lea     rcx, [rsp+338h+var_2E0]
0x1800b62a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b62a9  nop
0x1800b62aa  test    r14, r14
0x1800b62ad  jz      short loc_1800B632C
0x1800b62af  xor     edx, edx; Val
0x1800b62b1  mov     r8d, 208h; Size
0x1800b62b7  lea     rcx, [rsp+338h+DosName]; void *
0x1800b62bf  call    memset_0
0x1800b62c4  mov     r8d, 104h; dwDosNameBufferSize
0x1800b62ca  lea     rdx, [rsp+338h+DosName]; lpDosName
0x1800b62d2  mov     rcx, r14; lpVolumeName
0x1800b62d5  call    cs:__imp_FilterGetDosName
0x1800b62db  mov     rcx, [rsp+338h]; this
0x1800b62e3  test    eax, eax
0x1800b62e5  jns     short loc_1800B62FB
0x1800b62e7  mov     r9d, eax; char *
0x1800b62ea  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b62f1  mov     edx, 53h ; 'S'; void *
0x1800b62f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b62fb  lea     rcx, [rsp+338h+DosName]
0x1800b6303  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800b6308  mov     r8, rax
0x1800b630b  lea     rdx, [rsp+338h+DosName]
0x1800b6313  lea     rcx, [rsp+338h+var_2E0]
0x1800b6318  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800b631d  mov     rdx, [rsp+338h+var_2D0]
0x1800b6322  lea     rcx, [rsp+338h+var_2E0]
0x1800b6327  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800b632c  test    rdi, rdi
0x1800b632f  jz      short loc_1800B6349
0x1800b6331  mov     rcx, rdi
0x1800b6334  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800b6339  mov     r8, rax
0x1800b633c  mov     rdx, rdi
0x1800b633f  lea     rcx, [rsp+338h+var_2E0]
0x1800b6344  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800b6349  mov     rdi, qword ptr [rsp+338h+var_2F0]
0x1800b634e  test    rsi, rsi
0x1800b6351  jz      short loc_1800B6366
0x1800b6353  mov     rdx, rsi
0x1800b6356  lea     rcx, [rsp+338h+var_2C0]
0x1800b635b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b6360  nop
0x1800b6361  or      ebx, 4
0x1800b6364  jmp     short loc_1800B6377
0x1800b6366  lea     rcx, [rsp+338h+var_2A0]
0x1800b636e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b6373  nop
0x1800b6374  or      ebx, 8
0x1800b6377  mov     [rsp+338h+var_2F8], ebx
0x1800b637b  mov     dword ptr [rsp+338h+var_318], 3
0x1800b6383  xor     r9d, r9d
0x1800b6386  lea     r8, [rsp+338h+var_2E0]
0x1800b638b  mov     rdx, rax
0x1800b638e  mov     rcx, rdi
0x1800b6391  call    ?HandlePromptForUserWithAdditionalContext@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4CapabilityConsentValue@2345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_NW462345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::HandlePromptForUserWithAdditionalContext(std::wstring const &,std::wstring const &,bool,Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)
0x1800b6396  mov     edi, eax
0x1800b6398  test    bl, 8
0x1800b639b  jz      short loc_1800B63AE
0x1800b639d  and     ebx, 0FFFFFFF7h
0x1800b63a0  lea     rcx, [rsp+338h+var_2A0]
0x1800b63a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b63ad  nop
0x1800b63ae  test    bl, 4
0x1800b63b1  jz      short loc_1800B63BD
0x1800b63b3  lea     rcx, [rsp+338h+var_2C0]
0x1800b63b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b63bd  xor     r9d, r9d
0x1800b63c0  cmp     edi, 1
0x1800b63c3  setnz   r9b
0x1800b63c7  mov     [r12], r9d
0x1800b63cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b63d2  cmp     rcx, r13
0x1800b63d5  jz      short loc_1800B63F9
0x1800b63d7  test    byte ptr [rcx+1Ch], 1
0x1800b63db  jz      short loc_1800B63F9
0x1800b63dd  cmp     byte ptr [rcx+19h], 4
0x1800b63e1  jb      short loc_1800B63F9
0x1800b63e3  mov     edx, 0Dh
0x1800b63e8  lea     r8, WPP_ba398d49f73833a47629aaaf6d810685_Traceguids
0x1800b63ef  mov     rcx, [rcx+10h]
0x1800b63f3  call    WPP_SF_d
0x1800b63f8  nop
0x1800b63f9  lea     rcx, [rsp+338h+var_2E0]
0x1800b63fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6403  nop
0x1800b6404  mov     rcx, [rsp+338h+var_2E8]; this
0x1800b6409  test    rcx, rcx
0x1800b640c  jz      short loc_1800B6413
0x1800b640e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b6413  xor     eax, eax
0x1800b6415  jmp     short loc_1800B641B
0x1800b6417  mov     eax, [rsp+338h+var_2F8]
0x1800b641b  mov     rcx, [rsp+338h+var_48]
0x1800b6423  xor     rcx, rsp; StackCookie
0x1800b6426  call    __security_check_cookie
0x1800b642b  add     rsp, 300h
0x1800b6432  pop     r15
0x1800b6434  pop     r14
0x1800b6436  pop     r13
0x1800b6438  pop     r12
0x1800b643a  pop     rdi
0x1800b643b  pop     rsi
0x1800b643c  pop     rbx
0x1800b643d  retn
```
