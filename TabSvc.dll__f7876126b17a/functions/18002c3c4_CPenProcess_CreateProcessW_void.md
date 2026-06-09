# CPenProcess::CreateProcessW(void *)

- ea: `0x18002c3c4`
- end: `0x18002c73c`
- name: `?CreateProcessW@CPenProcess@@AEAAHPEAX@Z`
- size: `888`
- prototype: `__int64 __fastcall(CPenProcess *this, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013da0`

## callees

- `0x180001ec0`
- `0x1800108f0`
- `0x180010e94`
- `0x180012dc0`
- `0x180013cbc`
- `0x180015630`
- `0x18001a724`
- `0x18001bbe0`
- `0x18001bc04`
- `0x18001c684`
- `0x18002b404`
- `0x18002c3c4`
- `0x18002d8cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18002c5af`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18002c5af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c65c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c6ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c6ce`
- `USERENV!CreateEnvironmentBlock` at `0x18002c510`
- `USERENV!CreateEnvironmentBlock` at `0x18002c510`
- `USERENV!DestroyEnvironmentBlock` at `0x18002c5c1`
- `USERENV!DestroyEnvironmentBlock` at `0x18002c5c1`

## string_xrefs

- `0x18002c4cc`: `<no command line>`
- `0x18002c53b`: `PENSERVICE_CPenProcess::CreateProcessW`
- `0x18002c61e`: `PENSERVICE_CPenProcess::CreateProcessW`

## pseudocode

```c
__int64 __fastcall CPenProcess::CreateProcessW(CPenProcess *this, void *a2)
{
  unsigned __int64 v5; // rdx
  int v6; // r8d
  int v7; // r9d
  LPWSTR v8; // rdx
  char LastError; // al
  unsigned int v10; // esi
  const struct std::nothrow_t *v11; // rdx
  const struct std::nothrow_t *v12; // rdx
  char v13; // al
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const struct std::nothrow_t *v17; // rdx
  void *v18; // rcx
  const struct std::nothrow_t *v19; // rdx
  LPCWSTR lpApplicationName; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpCommandLine; // [rsp+68h] [rbp-98h] BYREF
  DWORD v22; // [rsp+70h] [rbp-90h] BYREF
  LPVOID Environment; // [rsp+78h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR *p_lpApplicationName; // [rsp+98h] [rbp-68h]
  LPWSTR *p_lpCommandLine; // [rsp+A0h] [rbp-60h]
  char v27; // [rsp+A8h] [rbp-58h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v29[8]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v30; // [rsp+130h] [rbp+30h]
  _BYTE v31[510]; // [rsp+132h] [rbp+32h] BYREF

  lpApplicationName = 0;
  lpCommandLine = 0;
  if ( !CPenProcess::CreateProcessCommandLine(this, (unsigned __int16 **)&lpApplicationName, &lpCommandLine) )
    return 0;
  p_lpApplicationName = &lpApplicationName;
  p_lpCommandLine = &lpCommandLine;
  v27 = 1;
  if ( !lpApplicationName )
  {
LABEL_26:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl'::`2'::impl) )
    {
      if ( lpApplicationName )
        operator delete((void *)lpApplicationName, v17);
      if ( lpCommandLine )
        operator delete(lpCommandLine, v17);
    }
    return 0;
  }
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  *(_OWORD *)v29 = *(_OWORD *)L"winsta0\\";
  v30 = aWinsta0[8];
  memset_0(v31, 0, 0x1F6u);
  StringCchCatW(v29, v5, (const unsigned __int16 *)this + 279);
  StartupInfo.lpDesktop = v29;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    v8 = L"<no command line>";
    if ( lpCommandLine )
      v8 = lpCommandLine;
    WPP_SF_sSSS(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      (_DWORD)v8,
      v6,
      v7,
      (__int64)lpApplicationName,
      (__int64)this + 558,
      (__int64)v8);
  }
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, a2, 0)
    && WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      17,
      (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      (unsigned int)"PENSERVICE_CPenProcess::CreateProcessW",
      LastError);
  }
  CreateTabtipRegKey(a2);
  v10 = CreateProcessAsUserW(
          a2,
          lpApplicationName,
          lpCommandLine,
          0,
          0,
          1,
          0x480u,
          Environment,
          0,
          &StartupInfo,
          &ProcessInformation);
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  SH<void *,SH_HANDLE>::Reset(&ProcessInformation.hThread);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl'::`2'::impl) )
  {
    operator delete((void *)lpApplicationName, v11);
    operator delete(lpCommandLine, v12);
  }
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        18,
        (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
        (unsigned int)"PENSERVICE_CPenProcess::CreateProcessW",
        v13);
    }
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      v22 = GetLastError();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)byte_18003B023,
        v15,
        v16,
        (__int64)&v22);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl'::`2'::impl) )
      SH<void *,SH_HANDLE>::Reset(&ProcessInformation);
    goto LABEL_26;
  }
  v18 = (void *)*((_QWORD *)this + 136);
  if ( v18 )
    CloseHandle(v18);
  *((_QWORD *)this + 136) = ProcessInformation.hProcess;
  *((_DWORD *)this + 271) = ProcessInformation.dwProcessId;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl'::`2'::impl) )
  {
    if ( lpApplicationName )
      operator delete((void *)lpApplicationName, v19);
    if ( lpCommandLine )
      operator delete(lpCommandLine, v19);
  }
  return v10;
}

```

## disassembly

```asm
0x18002c3c4  mov     [rsp-8+arg_10], rbx
0x18002c3c9  mov     [rsp-8+arg_18], rsi
0x18002c3ce  push    rbp
0x18002c3cf  push    rdi
0x18002c3d0  push    r15
0x18002c3d2  lea     rbp, [rsp-240h]
0x18002c3da  sub     rsp, 340h
0x18002c3e1  mov     rax, cs:__security_cookie
0x18002c3e8  xor     rax, rsp
0x18002c3eb  mov     [rbp+250h+var_20], rax
0x18002c3f2  mov     rbx, rdx
0x18002c3f5  mov     rdi, rcx
0x18002c3f8  mov     [rsp+350h+lpApplicationName], 0
0x18002c401  mov     [rsp+350h+lpCommandLine], 0
0x18002c40a  lea     r8, [rsp+350h+lpCommandLine]; unsigned __int16 **
0x18002c40f  lea     rdx, [rsp+350h+lpApplicationName]; unsigned __int16 **
0x18002c414  call    ?CreateProcessCommandLine@CPenProcess@@AEAAHPEAPEAG0@Z; CPenProcess::CreateProcessCommandLine(ushort * *,ushort * *)
0x18002c419  test    eax, eax
0x18002c41b  jnz     short loc_18002C424
0x18002c41d  xor     eax, eax
0x18002c41f  jmp     loc_18002C715
0x18002c424  lea     rax, [rsp+350h+lpApplicationName]
0x18002c429  mov     [rbp+250h+var_2B8], rax
0x18002c42d  lea     rax, [rsp+350h+lpCommandLine]
0x18002c432  mov     [rbp+250h+var_2B0], rax
0x18002c436  mov     [rbp+250h+var_2A8], 1
0x18002c43a  cmp     [rsp+350h+lpApplicationName], 0
0x18002c440  jnz     short loc_18002C44E
0x18002c442  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl(void)'::`2'::impl
0x18002c449  jmp     loc_18002C695
0x18002c44e  xor     edx, edx; Val
0x18002c450  lea     r8d, [rdx+64h]; Size
0x18002c454  lea     rcx, [rbp+250h+StartupInfo+4]; void *
0x18002c458  call    memset_0
0x18002c45d  mov     [rbp+250h+StartupInfo.cb], 68h ; 'h'
0x18002c464  movups  xmm0, xmmword ptr cs:aWinsta0; "winsta0\\"
0x18002c46b  movaps  xmmword ptr [rbp+250h+var_230], xmm0
0x18002c46f  movzx   eax, word ptr cs:aWinsta0+10h; ""
0x18002c476  mov     [rbp+250h+var_220], ax
0x18002c47a  xor     edx, edx; Val
0x18002c47c  mov     r8d, 1F6h; Size
0x18002c482  lea     rcx, [rbp+250h+var_21E]; void *
0x18002c486  call    memset_0
0x18002c48b  lea     rsi, [rdi+22Eh]
0x18002c492  mov     r8, rsi; unsigned __int16 *
0x18002c495  lea     rcx, [rbp+250h+var_230]; unsigned __int16 *
0x18002c499  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c49e  lea     rax, [rbp+250h+var_230]
0x18002c4a2  mov     [rbp+250h+StartupInfo.lpDesktop], rax
0x18002c4a6  xorps   xmm0, xmm0
0x18002c4a9  xor     eax, eax
0x18002c4ab  movups  xmmword ptr [rbp+250h+ProcessInformation.hProcess], xmm0
0x18002c4af  mov     qword ptr [rbp+250h+ProcessInformation.dwProcessId], rax
0x18002c4b3  lea     r15, WPP_GLOBAL_Control
0x18002c4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4c1  cmp     rcx, r15
0x18002c4c4  jz      short loc_18002C4FC
0x18002c4c6  test    byte ptr [rcx+1Ch], 10h
0x18002c4ca  jz      short loc_18002C4FC
0x18002c4cc  lea     rdx, aNoCommandLine; "<no command line>"
0x18002c4d3  mov     rax, [rsp+350h+lpCommandLine]
0x18002c4d8  test    rax, rax
0x18002c4db  cmovnz  rdx, rax
0x18002c4df  mov     qword ptr [rsp+350h+dwCreationFlags], rdx
0x18002c4e4  mov     qword ptr [rsp+350h+bInheritHandles], rsi
0x18002c4e9  mov     rax, [rsp+350h+lpApplicationName]
0x18002c4ee  mov     [rsp+350h+lpThreadAttributes], rax
0x18002c4f3  mov     rcx, [rcx+10h]
0x18002c4f7  call    WPP_SF_sSSS
0x18002c4fc  mov     [rsp+350h+Environment], 0
0x18002c505  xor     r8d, r8d; bInherit
0x18002c508  mov     rdx, rbx; hToken
0x18002c50b  lea     rcx, [rsp+350h+Environment]; lpEnvironment
0x18002c510  call    cs:__imp_CreateEnvironmentBlock
0x18002c516  test    eax, eax
0x18002c518  jnz     short loc_18002C559
0x18002c51a  mov     rax, cs:WPP_GLOBAL_Control
0x18002c521  cmp     rax, r15
0x18002c524  jz      short loc_18002C559
0x18002c526  test    byte ptr [rax+1Ch], 4
0x18002c52a  jz      short loc_18002C559
0x18002c52c  call    cs:__imp_GetLastError
0x18002c532  mov     edx, 11h
0x18002c537  mov     dword ptr [rsp+350h+lpThreadAttributes], eax
0x18002c53b  lea     r9, aPenserviceCpen_5; "PENSERVICE_CPenProcess::CreateProcessW"
0x18002c542  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002c549  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c550  mov     rcx, [rcx+10h]
0x18002c554  call    WPP_SF_sd
0x18002c559  mov     rcx, rbx; TokenHandle
0x18002c55c  call    ?CreateTabtipRegKey@@YAXPEAX@Z; CreateTabtipRegKey(void *)
0x18002c561  lea     rax, [rbp+250h+ProcessInformation]
0x18002c565  mov     [rsp+350h+lpProcessInformation], rax; lpProcessInformation
0x18002c56a  lea     rax, [rbp+250h+StartupInfo]
0x18002c56e  mov     [rsp+350h+lpStartupInfo], rax; lpStartupInfo
0x18002c573  mov     [rsp+350h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002c57c  mov     rax, [rsp+350h+Environment]
0x18002c581  mov     [rsp+350h+lpEnvironment], rax; lpEnvironment
0x18002c586  mov     [rsp+350h+dwCreationFlags], 480h; dwCreationFlags
0x18002c58e  mov     [rsp+350h+bInheritHandles], 1; bInheritHandles
0x18002c596  mov     [rsp+350h+lpThreadAttributes], 0; lpThreadAttributes
0x18002c59f  xor     r9d, r9d; lpProcessAttributes
0x18002c5a2  mov     r8, [rsp+350h+lpCommandLine]; lpCommandLine
0x18002c5a7  mov     rdx, [rsp+350h+lpApplicationName]; lpApplicationName
0x18002c5ac  mov     rcx, rbx; hToken
0x18002c5af  call    cs:__imp_CreateProcessAsUserW
0x18002c5b5  mov     esi, eax
0x18002c5b7  mov     rcx, [rsp+350h+Environment]; lpEnvironment
0x18002c5bc  test    rcx, rcx
0x18002c5bf  jz      short loc_18002C5C7
0x18002c5c1  call    cs:__imp_DestroyEnvironmentBlock
0x18002c5c7  lea     rcx, [rbp+250h+ProcessInformation.hThread]
0x18002c5cb  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002c5d0  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl(void)'::`2'::impl
0x18002c5d7  mov     rcx, rbx
0x18002c5da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(void)
0x18002c5df  test    al, al
0x18002c5e1  jnz     short loc_18002C5F7
0x18002c5e3  mov     rcx, [rsp+350h+lpApplicationName]; void *
0x18002c5e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c5ed  mov     rcx, [rsp+350h+lpCommandLine]; void *
0x18002c5f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c5f7  test    esi, esi
0x18002c5f9  jnz     loc_18002C6C2
0x18002c5ff  mov     rax, cs:WPP_GLOBAL_Control
0x18002c606  cmp     rax, r15
0x18002c609  jz      short loc_18002C63C
0x18002c60b  test    byte ptr [rax+1Ch], 4
0x18002c60f  jz      short loc_18002C63C
0x18002c611  call    cs:__imp_GetLastError
0x18002c617  lea     edx, [rsi+12h]
0x18002c61a  mov     dword ptr [rsp+350h+lpThreadAttributes], eax
0x18002c61e  lea     r9, aPenserviceCpen_5; "PENSERVICE_CPenProcess::CreateProcessW"
0x18002c625  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002c62c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c633  mov     rcx, [rcx+10h]
0x18002c637  call    WPP_SF_sd
0x18002c63c  mov     eax, cs:dword_1800411A8
0x18002c642  cmp     eax, 5
0x18002c645  jbe     short loc_18002C67C
0x18002c647  mov     edx, 4000000h
0x18002c64c  lea     rcx, dword_1800411A8
0x18002c653  call    _tlgKeywordOn
0x18002c658  test    al, al
0x18002c65a  jz      short loc_18002C67C
0x18002c65c  call    cs:__imp_GetLastError
0x18002c662  mov     [rsp+350h+var_2E0], eax
0x18002c666  lea     rax, [rsp+350h+var_2E0]
0x18002c66b  mov     [rsp+350h+lpThreadAttributes], rax
0x18002c670  lea     rdx, byte_18003B023
0x18002c677  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002c67c  mov     rcx, rbx
0x18002c67f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(void)
0x18002c684  test    al, al
0x18002c686  jz      short loc_18002C692
0x18002c688  lea     rcx, [rbp+250h+ProcessInformation]
0x18002c68c  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002c691  nop
0x18002c692  mov     rcx, rbx
0x18002c695  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(void)
0x18002c69a  test    al, al
0x18002c69c  jz      short loc_18002C6BD
0x18002c69e  mov     rcx, [rsp+350h+lpApplicationName]; void *
0x18002c6a3  test    rcx, rcx
0x18002c6a6  jz      short loc_18002C6AD
0x18002c6a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c6ad  mov     rcx, [rsp+350h+lpCommandLine]; void *
0x18002c6b2  test    rcx, rcx
0x18002c6b5  jz      short loc_18002C6BD
0x18002c6b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c6bc  nop
0x18002c6bd  jmp     loc_18002C41D
0x18002c6c2  mov     rcx, [rdi+440h]; hObject
0x18002c6c9  test    rcx, rcx
0x18002c6cc  jz      short loc_18002C6D4
0x18002c6ce  call    cs:__imp_CloseHandle
0x18002c6d4  mov     rax, [rbp+250h+ProcessInformation.hProcess]
0x18002c6d8  mov     [rdi+440h], rax
0x18002c6df  mov     eax, [rbp+250h+ProcessInformation.dwProcessId]
0x18002c6e2  mov     [rdi+43Ch], eax
0x18002c6e8  mov     rcx, rbx
0x18002c6eb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(void)
0x18002c6f0  test    al, al
0x18002c6f2  jz      short loc_18002C713
0x18002c6f4  mov     rcx, [rsp+350h+lpApplicationName]; void *
0x18002c6f9  test    rcx, rcx
0x18002c6fc  jz      short loc_18002C703
0x18002c6fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c703  mov     rcx, [rsp+350h+lpCommandLine]; void *
0x18002c708  test    rcx, rcx
0x18002c70b  jz      short loc_18002C713
0x18002c70d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c712  nop
0x18002c713  mov     eax, esi
0x18002c715  mov     rcx, [rbp+250h+var_20]
0x18002c71c  xor     rcx, rsp; StackCookie
0x18002c71f  call    __security_check_cookie
0x18002c724  lea     r11, [rsp+350h+var_10]
0x18002c72c  mov     rbx, [r11+30h]
0x18002c730  mov     rsi, [r11+38h]
0x18002c734  mov     rsp, r11
0x18002c737  pop     r15
0x18002c739  pop     rdi
0x18002c73a  pop     rbp
0x18002c73b  retn
```
