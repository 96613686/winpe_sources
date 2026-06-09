# SystemSettings::DataModel::CMouseCursorHelper::SetCursorSize(ulong)

- ea: `0x180071714`
- end: `0x180071b76`
- name: `?SetCursorSize@CMouseCursorHelper@DataModel@SystemSettings@@QEAAJK@Z`
- size: `1122`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CMouseCursorHelper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800723b0`

## callees

- `0x180013170`
- `0x180013d14`
- `0x180019a00`
- `0x180019a20`
- `0x18004e918`
- `0x1800504dc`
- `0x180066808`
- `0x18006df4c`
- `0x18006fc08`
- `0x180070760`
- `0x180071714`
- `0x180072f08`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800717c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800717e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800719dc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180071a03`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800717c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800717e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800719dc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180071a03`
- `USER32!SystemParametersInfoW` at `0x180071868`
- `USER32!SystemParametersInfoW` at `0x1800718d6`
- `USER32!SystemParametersInfoW` at `0x180071a85`
- `USER32!SystemParametersInfoW` at `0x180071aec`
- `USER32!SystemParametersInfoW` at `0x180071868`
- `USER32!SystemParametersInfoW` at `0x1800718d6`
- `USER32!SystemParametersInfoW` at `0x180071a85`
- `USER32!SystemParametersInfoW` at `0x180071aec`

## string_xrefs

- `0x18007183a`: `Software\Microsoft\Accessibility`
- `0x1800718a3`: `Software\Microsoft\Accessibility`
- `0x180071a57`: `Software\Microsoft\Accessibility`
- `0x180071abe`: `Software\Microsoft\Accessibility`
- `0x18007181a`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`
- `0x18007187d`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`
- `0x1800718e6`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`
- `0x180071948`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`
- `0x180071a35`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`
- `0x180071a9a`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`
- `0x180071b01`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`
- `0x180071b51`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\mouseaid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CMouseCursorHelper::SetCursorSize(
        SystemSettings::DataModel::CMouseCursorHelper *this,
        unsigned int a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  unsigned int v5; // esi
  const WCHAR *v6; // r15
  __int64 v7; // r14
  SystemSettings::DataModel::CMouseCursorHelper *v8; // rcx
  const WCHAR *CursorColor; // rax
  LPCWCH *v10; // rdi
  SystemSettings::DataModel::CMouseCursorHelper *v11; // rcx
  int v12; // eax
  unsigned int LastError; // edi
  const char *v14; // r9
  const char *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int v19; // edi
  const WCHAR *v20; // r15
  __int64 v21; // r14
  SystemSettings::DataModel::CMouseCursorHelper *v22; // rcx
  const WCHAR *v23; // rax
  LPCWCH *v24; // rsi
  SystemSettings::DataModel::CMouseCursorHelper *v25; // rcx
  int v26; // eax
  unsigned int v27; // esi
  const char *v28; // r9
  const char *v29; // r9
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  SystemSettings::DataModel::CMouseCursorHelper *v32; // [rsp+80h] [rbp+8h] BYREF

  v32 = this;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
  {
    wil::AcquireSRWLockExclusive(&v32, &qword_18039D530);
    v5 = qword_18039D538;
    qword_18039D538 = a2;
    v6 = L"Regular";
    if ( a2 != 1 )
      v6 = L"Custom";
    v7 = 0;
    while ( 1 )
    {
      LOBYTE(v4) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCHWIF>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_MCHWIF>::GetImpl'::`2'::impl,
        v4);
      CursorColor = SystemSettings::DataModel::CMouseCursorHelper::GetCursorColor(v8);
      if ( !CursorColor )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x116,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
          (const char *)0x80004005LL,
          bIgnoreCase);
        LastError = -2147467259;
        goto LABEL_20;
      }
      v10 = (LPCWCH *)(&SystemSettings::DataModel::CMouseCursorHelper::s_rgCursorSchemes + 3 * v7);
      if ( CompareStringOrdinal(v10[1], -1, CursorColor, -1, 1) == 2 && CompareStringOrdinal(*v10, -1, v6, -1, 1) == 2 )
        break;
      if ( (unsigned __int64)++v7 >= 0xD )
        goto LABEL_13;
    }
    v12 = SystemSettings::DataModel::CMouseCursorHelper::_ApplyCursorScheme(
            v11,
            (const struct SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme *)(&SystemSettings::DataModel::CMouseCursorHelper::s_rgCursorSchemes
                                                                                             + 3 * v7));
    LastError = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11C,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
LABEL_20:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v32);
      return LastError;
    }
    SHRegSetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Accessibility", L"CursorType", v7);
LABEL_13:
    if ( !SystemParametersInfoW(0x2029u, 0, (PVOID)(int)(((32 * (qword_18039D538 - 1)) >> 1) + 32), 1u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x135,
                    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
                    v14);
      goto LABEL_20;
    }
    if ( (int)SHRegSetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Accessibility", L"CursorSize", qword_18039D538) < 0 )
    {
      qword_18039D538 = v5;
      if ( !SystemParametersInfoW(0x2029u, 0, (PVOID)(int)(((32 * v5 - 32) >> 1) + 32), 1u) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x139,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
          v15);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v32);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18039D540 + 208LL))(qword_18039D540);
    LODWORD(v32) = 3;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::CursorNotification>::Notify(v16, &v32);
  }
  else
  {
    v19 = qword_18039D538;
    qword_18039D538 = a2;
    v20 = L"Regular";
    if ( a2 != 1 )
      v20 = L"Custom";
    v21 = 0;
    while ( 1 )
    {
      LOBYTE(v3) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCHWIF>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_MCHWIF>::GetImpl'::`2'::impl,
        v3);
      v23 = SystemSettings::DataModel::CMouseCursorHelper::GetCursorColor(v22);
      if ( !v23 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x150,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
          (const char *)0x80004005LL,
          bIgnoreCase);
        return 2147500037LL;
      }
      v24 = (LPCWCH *)(&SystemSettings::DataModel::CMouseCursorHelper::s_rgCursorSchemes + 3 * v21);
      if ( CompareStringOrdinal(v24[1], -1, v23, -1, 1) == 2 && CompareStringOrdinal(*v24, -1, v20, -1, 1) == 2 )
        break;
      if ( (unsigned __int64)++v21 >= 0xD )
        goto LABEL_32;
    }
    v26 = SystemSettings::DataModel::CMouseCursorHelper::_ApplyCursorScheme(
            v25,
            (const struct SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme *)(&SystemSettings::DataModel::CMouseCursorHelper::s_rgCursorSchemes
                                                                                             + 3 * v21));
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
        (const char *)(unsigned int)v26,
        bIgnoreCase);
      return v27;
    }
    SHRegSetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Accessibility", L"CursorType", v21);
LABEL_32:
    if ( !SystemParametersInfoW(0x2029u, 0, (PVOID)(int)(((32 * (qword_18039D538 - 1)) >> 1) + 32), 1u) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x16F,
               (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
               v28);
    if ( (int)SHRegSetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Accessibility", L"CursorSize", qword_18039D538) < 0 )
    {
      qword_18039D538 = v19;
      if ( !SystemParametersInfoW(0x2029u, 0, (PVOID)(int)(((32 * v19 - 32) >> 1) + 32), 1u) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x173,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\mouseaid.cpp",
          v29);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18039D540 + 208LL))(qword_18039D540);
  }
  LODWORD(v32) = 2;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::CursorNotification>::Notify(v17, &v32);
  return 0;
}

```

## disassembly

```asm
0x180071714  mov     [rsp+arg_0], rcx
0x180071719  push    rbx
0x18007171a  push    rbp
0x18007171b  push    rsi
0x18007171c  push    rdi
0x18007171d  push    r12
0x18007171f  push    r13
0x180071721  push    r14
0x180071723  push    r15
0x180071725  sub     rsp, 38h
0x180071729  mov     ebp, edx
0x18007172b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x180071732  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x180071737  test    al, al
0x180071739  jz      loc_18007196F
0x18007173f  lea     rdx, qword_18039D530
0x180071746  lea     rcx, [rsp+78h+arg_0]
0x18007174e  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180071753  nop
0x180071754  mov     esi, dword ptr cs:qword_18039D538
0x18007175a  mov     dword ptr cs:qword_18039D538, ebp
0x180071760  lea     rax, String1; "Custom"
0x180071767  lea     r15, aRegular; "Regular"
0x18007176e  mov     ebx, 1
0x180071773  cmp     ebp, ebx
0x180071775  cmovnz  r15, rax
0x180071779  xor     r14d, r14d
0x18007177c  lea     r13, ?s_rgCursorSchemes@CMouseCursorHelper@DataModel@SystemSettings@@0QBUSMouseCursorScheme@123@B; SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme const near * const SystemSettings::DataModel::CMouseCursorHelper::s_rgCursorSchemes
0x180071783  or      ebp, 0FFFFFFFFh
0x180071786  mov     dl, bl
0x180071788  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MCHWIF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MCHWIF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCHWIF> `wil::Feature<__WilFeatureTraits_Feature_MCHWIF>::GetImpl(void)'::`2'::impl
0x18007178f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MCHWIF@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCHWIF>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180071794  call    ?GetCursorColor@CMouseCursorHelper@DataModel@SystemSettings@@QEAAPEBGXZ; SystemSettings::DataModel::CMouseCursorHelper::GetCursorColor(void)
0x180071799  test    rax, rax
0x18007179c  jz      loc_18007193B
0x1800717a2  lea     rcx, [r14+r14*2]
0x1800717a6  lea     rdi, ds:0[rcx*8]
0x1800717ae  add     rdi, r13
0x1800717b1  mov     [rsp+78h+bIgnoreCase], ebx; bIgnoreCase
0x1800717b5  mov     r9d, ebp; cchCount2
0x1800717b8  mov     r8, rax; lpString2
0x1800717bb  mov     edx, ebp; cchCount1
0x1800717bd  mov     rcx, [rdi+8]; lpString1
0x1800717c1  call    cs:__imp_CompareStringOrdinal
0x1800717c8  nop     dword ptr [rax+rax+00h]
0x1800717cd  mov     r12, 0FFFFFFFF80000001h
0x1800717d4  cmp     eax, 2
0x1800717d7  jnz     short loc_1800717F9
0x1800717d9  mov     [rsp+78h+bIgnoreCase], ebx; int
0x1800717dd  mov     r9d, ebp; cchCount2
0x1800717e0  mov     r8, r15; lpString2
0x1800717e3  mov     edx, ebp; cchCount1
0x1800717e5  mov     rcx, [rdi]; lpString1
0x1800717e8  call    cs:__imp_CompareStringOrdinal
0x1800717ef  nop     dword ptr [rax+rax+00h]
0x1800717f4  cmp     eax, 2
0x1800717f7  jz      short loc_180071804
0x1800717f9  add     r14, rbx
0x1800717fc  cmp     r14, 0Dh
0x180071800  jb      short loc_180071786
0x180071802  jmp     short loc_180071849
0x180071804  mov     rdx, rdi; struct SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme *
0x180071807  call    ?_ApplyCursorScheme@CMouseCursorHelper@DataModel@SystemSettings@@AEAAJPEBUSMouseCursorScheme@123@@Z; SystemSettings::DataModel::CMouseCursorHelper::_ApplyCursorScheme(SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme const *)
0x18007180c  mov     edi, eax
0x18007180e  test    eax, eax
0x180071810  jns     short loc_180071830
0x180071812  mov     rcx, [rsp+78h]; this
0x180071817  mov     r9d, eax; char *
0x18007181a  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x180071821  mov     edx, 11Ch; void *
0x180071826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007182b  jmp     loc_18007195B
0x180071830  mov     r9d, r14d; unsigned int
0x180071833  lea     r8, aCursortype; "CursorType"
0x18007183a  lea     rdx, aSoftwareMicros_87; "Software\\Microsoft\\Accessibility"
0x180071841  mov     rcx, r12; HKEY
0x180071844  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180071849  mov     eax, dword ptr cs:qword_18039D538
0x18007184f  dec     eax
0x180071851  shl     eax, 5
0x180071854  shr     eax, 1
0x180071856  add     eax, 20h ; ' '
0x180071859  movsxd  r8, eax; pvParam
0x18007185c  mov     r9d, ebx; fWinIni
0x18007185f  xor     edx, edx; uiParam
0x180071861  mov     ebp, 2029h
0x180071866  mov     ecx, ebp; uiAction
0x180071868  call    cs:__imp_SystemParametersInfoW
0x18007186f  nop     dword ptr [rax+rax+00h]
0x180071874  test    eax, eax
0x180071876  jnz     short loc_180071895
0x180071878  mov     rcx, [rsp+78h]; this
0x18007187d  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x180071884  mov     edx, 135h; void *
0x180071889  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007188e  mov     edi, eax
0x180071890  jmp     loc_18007195B
0x180071895  mov     r9d, dword ptr cs:qword_18039D538; unsigned int
0x18007189c  lea     r8, aCursorsize; "CursorSize"
0x1800718a3  lea     rdx, aSoftwareMicros_87; "Software\\Microsoft\\Accessibility"
0x1800718aa  mov     rcx, r12; HKEY
0x1800718ad  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800718b2  test    eax, eax
0x1800718b4  jns     short loc_1800718FB
0x1800718b6  mov     dword ptr cs:qword_18039D538, esi
0x1800718bc  mov     rdi, [rsp+78h]
0x1800718c1  shl     esi, 5
0x1800718c4  sub     esi, 20h ; ' '
0x1800718c7  shr     esi, 1
0x1800718c9  add     esi, 20h ; ' '
0x1800718cc  movsxd  r8, esi; pvParam
0x1800718cf  mov     r9d, ebx; fWinIni
0x1800718d2  xor     edx, edx; uiParam
0x1800718d4  mov     ecx, ebp; uiAction
0x1800718d6  call    cs:__imp_SystemParametersInfoW
0x1800718dd  nop     dword ptr [rax+rax+00h]
0x1800718e2  test    eax, eax
0x1800718e4  jnz     short loc_1800718FB
0x1800718e6  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x1800718ed  mov     edx, 139h; void *
0x1800718f2  mov     rcx, rdi; this
0x1800718f5  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800718fa  nop
0x1800718fb  lea     rcx, [rsp+78h+arg_0]
0x180071903  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180071908  mov     rcx, cs:qword_18039D540
0x18007190f  mov     rax, [rcx]
0x180071912  mov     rax, [rax+0D0h]
0x180071919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007191e  mov     dword ptr [rsp+78h+arg_0], 3
0x180071929  lea     rdx, [rsp+78h+arg_0]
0x180071931  call    ?Notify@?$CSingletonHelper@W4CursorNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXAEBW4CursorNotification@23@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CursorNotification>::Notify(SystemSettings::DataModel::CursorNotification const &)
0x180071936  jmp     loc_180071B28
0x18007193b  mov     rcx, [rsp+78h]; this
0x180071940  mov     ebx, 80004005h
0x180071945  mov     r9d, ebx; char *
0x180071948  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x18007194f  mov     edx, 116h; void *
0x180071954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071959  mov     edi, ebx
0x18007195b  lea     rcx, [rsp+78h+arg_0]
0x180071963  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180071968  mov     eax, edi
0x18007196a  jmp     loc_180071B64
0x18007196f  mov     edi, dword ptr cs:qword_18039D538
0x180071975  mov     dword ptr cs:qword_18039D538, ebp
0x18007197b  lea     rax, String1; "Custom"
0x180071982  lea     r15, aRegular; "Regular"
0x180071989  mov     ebx, 1
0x18007198e  cmp     ebp, ebx
0x180071990  cmovnz  r15, rax
0x180071994  xor     r14d, r14d
0x180071997  lea     r13, ?s_rgCursorSchemes@CMouseCursorHelper@DataModel@SystemSettings@@0QBUSMouseCursorScheme@123@B; SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme const near * const SystemSettings::DataModel::CMouseCursorHelper::s_rgCursorSchemes
0x18007199e  or      ebp, 0FFFFFFFFh
0x1800719a1  mov     dl, bl
0x1800719a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MCHWIF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MCHWIF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCHWIF> `wil::Feature<__WilFeatureTraits_Feature_MCHWIF>::GetImpl(void)'::`2'::impl
0x1800719aa  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MCHWIF@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCHWIF>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800719af  call    ?GetCursorColor@CMouseCursorHelper@DataModel@SystemSettings@@QEAAPEBGXZ; SystemSettings::DataModel::CMouseCursorHelper::GetCursorColor(void)
0x1800719b4  test    rax, rax
0x1800719b7  jz      loc_180071B44
0x1800719bd  lea     rcx, [r14+r14*2]
0x1800719c1  lea     rsi, ds:0[rcx*8]
0x1800719c9  add     rsi, r13
0x1800719cc  mov     [rsp+78h+bIgnoreCase], ebx; bIgnoreCase
0x1800719d0  mov     r9d, ebp; cchCount2
0x1800719d3  mov     r8, rax; lpString2
0x1800719d6  mov     edx, ebp; cchCount1
0x1800719d8  mov     rcx, [rsi+8]; lpString1
0x1800719dc  call    cs:__imp_CompareStringOrdinal
0x1800719e3  nop     dword ptr [rax+rax+00h]
0x1800719e8  mov     r12, 0FFFFFFFF80000001h
0x1800719ef  cmp     eax, 2
0x1800719f2  jnz     short loc_180071A14
0x1800719f4  mov     [rsp+78h+bIgnoreCase], ebx; int
0x1800719f8  mov     r9d, ebp; cchCount2
0x1800719fb  mov     r8, r15; lpString2
0x1800719fe  mov     edx, ebp; cchCount1
0x180071a00  mov     rcx, [rsi]; lpString1
0x180071a03  call    cs:__imp_CompareStringOrdinal
0x180071a0a  nop     dword ptr [rax+rax+00h]
0x180071a0f  cmp     eax, 2
0x180071a12  jz      short loc_180071A1F
0x180071a14  add     r14, rbx
0x180071a17  cmp     r14, 0Dh
0x180071a1b  jb      short loc_1800719A1
0x180071a1d  jmp     short loc_180071A66
0x180071a1f  mov     rdx, rsi; struct SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme *
0x180071a22  call    ?_ApplyCursorScheme@CMouseCursorHelper@DataModel@SystemSettings@@AEAAJPEBUSMouseCursorScheme@123@@Z; SystemSettings::DataModel::CMouseCursorHelper::_ApplyCursorScheme(SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme const *)
0x180071a27  mov     esi, eax
0x180071a29  test    eax, eax
0x180071a2b  jns     short loc_180071A4D
0x180071a2d  mov     rcx, [rsp+78h]; this
0x180071a32  mov     r9d, eax; char *
0x180071a35  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x180071a3c  mov     edx, 156h; void *
0x180071a41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071a46  mov     eax, esi
0x180071a48  jmp     loc_180071B64
0x180071a4d  mov     r9d, r14d; unsigned int
0x180071a50  lea     r8, aCursortype; "CursorType"
0x180071a57  lea     rdx, aSoftwareMicros_87; "Software\\Microsoft\\Accessibility"
0x180071a5e  mov     rcx, r12; HKEY
0x180071a61  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180071a66  mov     eax, dword ptr cs:qword_18039D538
0x180071a6c  dec     eax
0x180071a6e  shl     eax, 5
0x180071a71  shr     eax, 1
0x180071a73  add     eax, 20h ; ' '
0x180071a76  movsxd  r8, eax; pvParam
0x180071a79  mov     r9d, ebx; fWinIni
0x180071a7c  xor     edx, edx; uiParam
0x180071a7e  mov     ebp, 2029h
0x180071a83  mov     ecx, ebp; uiAction
0x180071a85  call    cs:__imp_SystemParametersInfoW
0x180071a8c  nop     dword ptr [rax+rax+00h]
0x180071a91  test    eax, eax
0x180071a93  jnz     short loc_180071AB0
0x180071a95  mov     rcx, [rsp+78h]; this
0x180071a9a  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x180071aa1  mov     edx, 16Fh; void *
0x180071aa6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180071aab  jmp     loc_180071B64
0x180071ab0  mov     r9d, dword ptr cs:qword_18039D538; unsigned int
0x180071ab7  lea     r8, aCursorsize; "CursorSize"
0x180071abe  lea     rdx, aSoftwareMicros_87; "Software\\Microsoft\\Accessibility"
0x180071ac5  mov     rcx, r12; HKEY
0x180071ac8  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180071acd  test    eax, eax
0x180071acf  jns     short loc_180071B12
0x180071ad1  mov     dword ptr cs:qword_18039D538, edi
0x180071ad7  shl     edi, 5
0x180071ada  sub     edi, 20h ; ' '
0x180071add  shr     edi, 1
0x180071adf  add     edi, 20h ; ' '
0x180071ae2  movsxd  r8, edi; pvParam
0x180071ae5  mov     r9d, ebx; fWinIni
0x180071ae8  xor     edx, edx; uiParam
0x180071aea  mov     ecx, ebp; uiAction
0x180071aec  call    cs:__imp_SystemParametersInfoW
0x180071af3  nop     dword ptr [rax+rax+00h]
0x180071af8  test    eax, eax
0x180071afa  jnz     short loc_180071B12
0x180071afc  mov     rcx, [rsp+78h]; this
0x180071b01  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x180071b08  mov     edx, 173h; void *
0x180071b0d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180071b12  mov     rcx, cs:qword_18039D540
0x180071b19  mov     rax, [rcx]
0x180071b1c  mov     rax, [rax+0D0h]
0x180071b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b28  mov     dword ptr [rsp+78h+arg_0], 2
0x180071b33  lea     rdx, [rsp+78h+arg_0]
0x180071b3b  call    ?Notify@?$CSingletonHelper@W4CursorNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXAEBW4CursorNotification@23@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CursorNotification>::Notify(SystemSettings::DataModel::CursorNotification const &)
0x180071b40  xor     eax, eax
0x180071b42  jmp     short loc_180071B64
0x180071b44  mov     rcx, [rsp+78h]; this
0x180071b49  mov     ebx, 80004005h
0x180071b4e  mov     r9d, ebx; char *
0x180071b51  lea     r8, aShellSystemset_53; "shell\\systemsettingsthreshold\\handler"...
0x180071b58  mov     edx, 150h; void *
0x180071b5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071b62  mov     eax, ebx
0x180071b64  add     rsp, 38h
0x180071b68  pop     r15
0x180071b6a  pop     r14
0x180071b6c  pop     r13
0x180071b6e  pop     r12
0x180071b70  pop     rdi
0x180071b71  pop     rsi
0x180071b72  pop     rbp
0x180071b73  pop     rbx
0x180071b74  retn
```
