# Windows::Globalization::Spelling::ThirdPartySpellerCreator::CreateHostProviderFactory(_GUID const &,ISpellCheckProviderFactory * *)

- ea: `0x18003912c`
- end: `0x18003946f`
- name: `?CreateHostProviderFactory@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@SAJAEBU_GUID@@PEAPEAUISpellCheckProviderFactory@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(const struct _GUID *, struct ISpellCheckProviderFactory **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180039040`

## callees

- `0x18001ee7c`
- `0x1800202e4`
- `0x18003912c`
- `0x180040cc4`
- `0x18004b4e0`
- `0x180052da4`
- `0x180061320`
- `0x180062314`
- `0x18006512c`
- `0x180066168`
- `0x180066418`
- `0x1800666a4`
- `0x180067648`
- `0x180069b60`
- `0x18006a0e4`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003928c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003928c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800391f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800391f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180039282`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180039282`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180039232`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180039232`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039437`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039437`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003923a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003923a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800392e6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800392e6`

## string_xrefs

- `0x18003938f`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\hostlaunch.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Globalization::Spelling::ThirdPartySpellerCreator::CreateHostProviderFactory(
        const struct _GUID *a1,
        struct ISpellCheckProviderFactory **a2)
{
  int AppContainerSidFromMoniker; // ebx
  const char *v5; // r9
  char v6; // si
  HANDLE v7; // rdi
  signed int LastError; // eax
  LPVOID v9; // rcx
  signed int v10; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rax
  DWORD i; // edi
  __int64 v18; // r8
  int ppv; // [rsp+20h] [rbp-3B8h]
  unsigned int v21; // [rsp+30h] [rbp-3A8h]
  HANDLE hObject; // [rsp+38h] [rbp-3A0h] BYREF
  DWORD dwProcessId[2]; // [rsp+40h] [rbp-398h] BYREF
  LPVOID v25; // [rsp+48h] [rbp-390h] BYREF
  PSID pSid; // [rsp+50h] [rbp-388h] BYREF
  _QWORD Src[5]; // [rsp+58h] [rbp-380h] BYREF
  LPVOID pv[100]; // [rsp+80h] [rbp-358h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+0h]

  *a2 = 0;
  pSid = 0;
  AppContainerSidFromMoniker = ACUtil::GetAppContainerSidFromMoniker((const unsigned __int16 *)a1, &pSid);
  v21 = AppContainerSidFromMoniker;
  v6 = 0;
  if ( AppContainerSidFromMoniker < 0
    || (AppContainerSidFromMoniker = Windows::Globalization::Spelling::ThirdPartySpellerCreator::AcquireHostActivationMutex(pSid),
        v21 = AppContainerSidFromMoniker,
        AppContainerSidFromMoniker < 0) )
  {
    dwProcessId[0] = 0;
    hObject = 0;
LABEL_15:
    v9 = 0;
    v25 = 0;
    goto LABEL_16;
  }
  dwProcessId[0] = 0;
  AppContainerSidFromMoniker = Windows::Globalization::Spelling::ThirdPartySpellerCreator::EnsureHostProcessIsRunning(
                                 pSid,
                                 dwProcessId);
  v21 = AppContainerSidFromMoniker;
  v6 = 1;
  hObject = 0;
  if ( AppContainerSidFromMoniker >= 0 )
  {
    AppContainerSidFromMoniker = Windows::Globalization::Spelling::ThirdPartySpellerCreator::CreateHostRegisteredEvent(
                                   pSid,
                                   &hObject);
    v21 = AppContainerSidFromMoniker;
    v7 = hObject;
    if ( AppContainerSidFromMoniker >= 0 )
    {
      AppContainerSidFromMoniker = Windows::Globalization::Spelling::ThirdPartySpellerCreator::WaitForHostToRegister(hObject);
      v21 = AppContainerSidFromMoniker;
    }
    if ( v7 )
      CloseHandle(v7);
  }
  if ( AppContainerSidFromMoniker < 0 )
    goto LABEL_15;
  AppContainerSidFromMoniker = Windows::Globalization::Spelling::ThirdPartySpellerCreator::ImpersonateProcess(dwProcessId[0]);
  v21 = AppContainerSidFromMoniker;
  if ( AppContainerSidFromMoniker < 0 )
    goto LABEL_15;
  v25 = 0;
  AppContainerSidFromMoniker = CoCreateInstance(
                                 &GUID_f1425a67_1545_44a2_ab59_8df1020452d9,
                                 0,
                                 0x100004u,
                                 &GUID_382d337f_8ad7_41bd_9eef_e5811c3cae8a,
                                 &v25);
  if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    AppContainerSidFromMoniker = LastError;
    if ( LastError > 0 )
      AppContainerSidFromMoniker = (unsigned __int16)LastError | 0x80070000;
  }
  v21 = AppContainerSidFromMoniker;
  v9 = v25;
LABEL_16:
  if ( v6 )
  {
    if ( !ReleaseMutex(Windows::Globalization::Spelling::g_hActivationMutex) )
    {
      v10 = GetLastError();
      AppContainerSidFromMoniker = v10;
      if ( v10 > 0 )
        AppContainerSidFromMoniker = (unsigned __int16)v10 | 0x80070000;
      v21 = AppContainerSidFromMoniker;
    }
    v9 = v25;
  }
  if ( AppContainerSidFromMoniker >= 0 )
  {
    AppContainerSidFromMoniker = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, struct ISpellCheckProviderFactory **))(*(_QWORD *)v9 + 24LL))(
                                   v9,
                                   a1,
                                   a2);
    v21 = AppContainerSidFromMoniker;
    v9 = v25;
  }
  if ( v9 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  if ( pSid )
    FreeSid(pSid);
  try
  {
    if ( AppContainerSidFromMoniker < 0 || !*a2 )
      return (unsigned int)AppContainerSidFromMoniker;
    std::wstring::wstring(Src, &dword_1800D3F14);
    hObject = 0;
    v11 = (__int64 *)*a2;
    v12 = *(_QWORD *)*a2;
    hObject = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, HANDLE *))(v12 + 24))(v11, &hObject);
    v14 = retaddr;
    if ( v13 >= 0 )
    {
      dwProcessId[0] = 0;
      memset_0(pv, 0, sizeof(pv));
      v13 = (*(__int64 (__fastcall **)(HANDLE, __int64, LPVOID *, DWORD *))(*(_QWORD *)hObject + 24LL))(
              hObject,
              100,
              pv,
              dwProcessId);
      v14 = retaddr;
      if ( v13 >= 0 )
      {
        for ( i = 0; i < dwProcessId[0] && i < 0x64; ++i )
        {
          if ( pv[i] )
          {
            if ( Src[2] )
              std::wstring::_Append<unsigned short>(Src);
            v18 = -1;
            do
              ++v18;
            while ( *((_WORD *)pv[i] + v18) );
            std::wstring::_Append<unsigned short>(Src);
            CoTaskMemFree(pv[i]);
          }
        }
        goto LABEL_35;
      }
      v15 = 122;
    }
    else
    {
      v15 = 116;
    }
    wil::details::in1diag3::_Log_Hr(
      v14,
      (void *)v15,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\hostlaunch.cpp",
      (const char *)(unsigned int)v13,
      ppv);
LABEL_35:
    v16 = Src;
    if ( Src[3] > 7u )
      v16 = (_QWORD *)Src[0];
    *(_QWORD *)dwProcessId = v16;
    SpellingTelemetry::CustomSpellerUsed<unsigned short const *>(dwProcessId);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&hObject);
    std::wstring::_Tidy_deallocate(Src);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\hostlaunch.cpp",
      v5);
    return v21;
  }
  return (unsigned int)AppContainerSidFromMoniker;
}

```

## disassembly

```asm
0x18003912c  mov     [rsp+arg_10], rbx
0x180039131  push    rsi
0x180039132  push    rdi
0x180039133  push    r12
0x180039135  push    r14
0x180039137  push    r15
0x180039139  sub     rsp, 3B0h
0x180039140  mov     rax, cs:__security_cookie
0x180039147  xor     rax, rsp
0x18003914a  mov     [rsp+3D8h+var_38], rax
0x180039152  mov     r14, rdx
0x180039155  mov     r15, rcx
0x180039158  xor     r12d, r12d
0x18003915b  mov     [rdx], r12
0x18003915e  mov     [rsp+3D8h+pSid], r12
0x180039163  lea     rdx, [rsp+3D8h+pSid]; void **
0x180039168  call    ?GetAppContainerSidFromMoniker@ACUtil@@SAJPEBGPEAPEAX@Z; ACUtil::GetAppContainerSidFromMoniker(ushort const *,void * *)
0x18003916d  mov     ebx, eax
0x18003916f  mov     [rsp+3D8h+var_3A8], eax
0x180039173  mov     sil, r12b
0x180039176  test    eax, eax
0x180039178  js      loc_180039264
0x18003917e  mov     rcx, [rsp+3D8h+pSid]; Sid
0x180039183  call    ?AcquireHostActivationMutex@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAX@Z; Windows::Globalization::Spelling::ThirdPartySpellerCreator::AcquireHostActivationMutex(void *)
0x180039188  mov     ebx, eax
0x18003918a  mov     [rsp+3D8h+var_3A8], eax
0x18003918e  test    eax, eax
0x180039190  js      loc_180039264
0x180039196  mov     [rsp+3D8h+dwProcessId], r12d
0x18003919b  lea     rdx, [rsp+3D8h+dwProcessId]; unsigned int *
0x1800391a0  mov     rcx, [rsp+3D8h+pSid]; void *
0x1800391a5  call    ?EnsureHostProcessIsRunning@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAXPEAK@Z; Windows::Globalization::Spelling::ThirdPartySpellerCreator::EnsureHostProcessIsRunning(void *,ulong *)
0x1800391aa  mov     ebx, eax
0x1800391ac  mov     [rsp+3D8h+var_3A8], eax
0x1800391b0  mov     sil, 1
0x1800391b3  mov     [rsp+3D8h+hObject], r12
0x1800391b8  test    eax, eax
0x1800391ba  js      short loc_1800391F6
0x1800391bc  lea     rdx, [rsp+3D8h+hObject]; void **
0x1800391c1  mov     rcx, [rsp+3D8h+pSid]; void *
0x1800391c6  call    ?CreateHostRegisteredEvent@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAXPEAPEAX@Z; Windows::Globalization::Spelling::ThirdPartySpellerCreator::CreateHostRegisteredEvent(void *,void * *)
0x1800391cb  mov     ebx, eax
0x1800391cd  mov     [rsp+3D8h+var_3A8], eax
0x1800391d1  mov     rdi, [rsp+3D8h+hObject]
0x1800391d6  test    eax, eax
0x1800391d8  js      short loc_1800391E8
0x1800391da  mov     rcx, rdi; void *
0x1800391dd  call    ?WaitForHostToRegister@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAX@Z; Windows::Globalization::Spelling::ThirdPartySpellerCreator::WaitForHostToRegister(void *)
0x1800391e2  mov     ebx, eax
0x1800391e4  mov     [rsp+3D8h+var_3A8], eax
0x1800391e8  test    rdi, rdi
0x1800391eb  jz      short loc_1800391F6
0x1800391ed  mov     rcx, rdi; hObject
0x1800391f0  call    cs:__imp_CloseHandle
0x1800391f6  test    ebx, ebx
0x1800391f8  js      short loc_18003926E
0x1800391fa  mov     ecx, [rsp+3D8h+dwProcessId]; dwProcessId
0x1800391fe  call    ?ImpersonateProcess@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJK@Z; Windows::Globalization::Spelling::ThirdPartySpellerCreator::ImpersonateProcess(ulong)
0x180039203  mov     ebx, eax
0x180039205  mov     [rsp+3D8h+var_3A8], eax
0x180039209  test    eax, eax
0x18003920b  js      short loc_18003926E
0x18003920d  mov     [rsp+3D8h+var_390], r12
0x180039212  lea     rax, [rsp+3D8h+var_390]
0x180039217  mov     qword ptr [rsp+3D8h+ppv], rax; ppv
0x18003921c  lea     r9, _GUID_382d337f_8ad7_41bd_9eef_e5811c3cae8a; riid
0x180039223  xor     edx, edx; pUnkOuter
0x180039225  mov     r8d, 100004h; dwClsContext
0x18003922b  lea     rcx, _GUID_f1425a67_1545_44a2_ab59_8df1020452d9; rclsid
0x180039232  call    cs:__imp_CoCreateInstance
0x180039238  mov     ebx, eax
0x18003923a  call    cs:__imp_RevertToSelf
0x180039240  test    eax, eax
0x180039242  jnz     short loc_180039259
0x180039244  call    cs:__imp_GetLastError
0x18003924a  mov     ebx, eax
0x18003924c  test    eax, eax
0x18003924e  jle     short loc_180039259
0x180039250  movzx   ebx, ax
0x180039253  or      ebx, 80070000h
0x180039259  mov     [rsp+3D8h+var_3A8], ebx
0x18003925d  mov     rcx, [rsp+3D8h+var_390]
0x180039262  jmp     short loc_180039276
0x180039264  mov     [rsp+3D8h+dwProcessId], r12d
0x180039269  mov     [rsp+3D8h+hObject], r12
0x18003926e  mov     rcx, r12
0x180039271  mov     [rsp+3D8h+var_390], rcx
0x180039276  test    sil, sil
0x180039279  jz      short loc_1800392AA
0x18003927b  mov     rcx, cs:?g_hActivationMutex@Spelling@Globalization@Windows@@3PEAXEA; hMutex
0x180039282  call    cs:__imp_ReleaseMutex
0x180039288  test    eax, eax
0x18003928a  jnz     short loc_1800392A5
0x18003928c  call    cs:__imp_GetLastError
0x180039292  mov     ebx, eax
0x180039294  test    eax, eax
0x180039296  jle     short loc_1800392A1
0x180039298  movzx   ebx, ax
0x18003929b  or      ebx, 80070000h
0x1800392a1  mov     [rsp+3D8h+var_3A8], ebx
0x1800392a5  mov     rcx, [rsp+3D8h+var_390]
0x1800392aa  test    ebx, ebx
0x1800392ac  js      short loc_1800392CB
0x1800392ae  mov     rax, [rcx]
0x1800392b1  mov     r8, r14
0x1800392b4  mov     rdx, r15
0x1800392b7  mov     rax, [rax+18h]
0x1800392bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392c0  mov     ebx, eax
0x1800392c2  mov     [rsp+3D8h+var_3A8], eax
0x1800392c6  mov     rcx, [rsp+3D8h+var_390]
0x1800392cb  test    rcx, rcx
0x1800392ce  jz      short loc_1800392DC
0x1800392d0  mov     rax, [rcx]
0x1800392d3  mov     rax, [rax+10h]
0x1800392d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392dc  mov     rcx, [rsp+3D8h+pSid]; pSid
0x1800392e1  test    rcx, rcx
0x1800392e4  jz      short loc_1800392ED
0x1800392e6  call    cs:__imp_FreeSid
0x1800392ec  nop
0x1800392ed  test    ebx, ebx
0x1800392ef  js      loc_1800393D5
0x1800392f5  cmp     [r14], r12
0x1800392f8  jz      loc_1800393D5
0x1800392fe  lea     rdx, dword_1800D3F14
0x180039305  lea     rcx, [rsp+3D8h+Src]
0x18003930a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003930f  nop
0x180039310  mov     [rsp+3D8h+hObject], r12
0x180039315  mov     rcx, [r14]
0x180039318  mov     rax, [rcx]
0x18003931b  mov     [rsp+3D8h+hObject], r12
0x180039320  lea     rdx, [rsp+3D8h+hObject]
0x180039325  mov     rax, [rax+18h]
0x180039329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003932e  mov     rcx, [rsp+3D8h]
0x180039336  test    eax, eax
0x180039338  jns     short loc_180039341
0x18003933a  mov     edx, 74h ; 't'
0x18003933f  jmp     short loc_18003938F
0x180039341  mov     [rsp+3D8h+dwProcessId], r12d
0x180039346  xor     edx, edx; Val
0x180039348  mov     r8d, 320h; Size
0x18003934e  lea     rcx, [rsp+3D8h+pv]; void *
0x180039356  call    memset_0
0x18003935b  mov     rcx, [rsp+3D8h+hObject]
0x180039360  mov     rax, [rcx]
0x180039363  lea     r9, [rsp+3D8h+dwProcessId]
0x180039368  lea     r8, [rsp+3D8h+pv]
0x180039370  mov     edx, 64h ; 'd'
0x180039375  mov     rax, [rax+18h]
0x180039379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003937e  mov     rcx, [rsp+3D8h]; this
0x180039386  test    eax, eax
0x180039388  jns     short loc_1800393D7
0x18003938a  mov     edx, 7Ah ; 'z'; void *
0x18003938f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180039396  mov     r9d, eax; char *
0x180039399  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003939e  lea     rax, [rsp+3D8h+Src]
0x1800393a3  cmp     [rsp+3D8h+var_368], 7
0x1800393a9  cmova   rax, [rsp+3D8h+Src]
0x1800393af  mov     qword ptr [rsp+3D8h+dwProcessId], rax
0x1800393b4  lea     rcx, [rsp+3D8h+dwProcessId]
0x1800393b9  call    ??$CustomSpellerUsed@PEBG@SpellingTelemetry@@SAX$$QEAPEBG@Z; SpellingTelemetry::CustomSpellerUsed<ushort const *>(ushort const * &&)
0x1800393be  nop
0x1800393bf  lea     rcx, [rsp+3D8h+hObject]
0x1800393c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800393c9  nop
0x1800393ca  lea     rcx, [rsp+3D8h+Src]
0x1800393cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800393d4  nop
0x1800393d5  jmp     short loc_180039445
0x1800393d7  mov     edi, r12d
0x1800393da  cmp     edi, [rsp+3D8h+dwProcessId]
0x1800393de  jnb     short loc_18003939E
0x1800393e0  cmp     edi, 64h ; 'd'
0x1800393e3  jnb     short loc_18003939E
0x1800393e5  mov     esi, edi
0x1800393e7  cmp     [rsp+rsi*8+3D8h+pv], r12
0x1800393ef  jz      short loc_18003943D
0x1800393f1  cmp     [rsp+3D8h+var_370], r12
0x1800393f6  jbe     short loc_18003940F
0x1800393f8  mov     r8d, 1
0x1800393fe  lea     rdx, asc_1800E04E8; ","
0x180039405  lea     rcx, [rsp+3D8h+Src]; Src
0x18003940a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003940f  mov     rdx, [rsp+rsi*8+3D8h+pv]
0x180039417  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003941b  inc     r8
0x18003941e  cmp     [rdx+r8*2], r12w
0x180039423  jnz     short loc_18003941B
0x180039425  lea     rcx, [rsp+3D8h+Src]; Src
0x18003942a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003942f  mov     rcx, [rsp+rsi*8+3D8h+pv]; pv
0x180039437  call    cs:__imp_CoTaskMemFree
0x18003943d  inc     edi
0x18003943f  jmp     short loc_1800393DA
0x180039441  mov     ebx, [rsp+3D8h+var_3A8]
0x180039445  mov     eax, ebx
0x180039447  mov     rcx, [rsp+3D8h+var_38]
0x18003944f  xor     rcx, rsp; StackCookie
0x180039452  call    __security_check_cookie
0x180039457  mov     rbx, [rsp+3D8h+arg_10]
0x18003945f  add     rsp, 3B0h
0x180039466  pop     r15
0x180039468  pop     r14
0x18003946a  pop     r12
0x18003946c  pop     rdi
0x18003946d  pop     rsi
0x18003946e  retn
```
