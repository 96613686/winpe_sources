# CSharePickerExperienceManager::Hide(void)

- ea: `0x180218350`
- end: `0x180218559`
- name: `?Hide@CSharePickerExperienceManager@@UEAAJXZ`
- size: `521`
- prototype: `__int64 __fastcall(CSharePickerExperienceManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18021630c`

## callees

- `0x180009dfc`
- `0x18010c5a0`
- `0x180218350`
- `0x180218560`
- `0x1802186dc`
- `0x18021d338`
- `0x18021db6c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180218389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802183b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802183ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802184f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180218389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802183b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802183ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802184f8`
- `USER32!GetLastActivePopup` at `0x1802184c0`
- `USER32!GetLastActivePopup` at `0x1802184c0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x1802184ac`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x1802184cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x1802184ac`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x1802184cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180218492`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180218492`

## string_xrefs

- `0x1802183c9`: `%S(%d) No frame exists, setting state to Destroyed without transitioning through Hiding. ThreadId=%u`
- `0x18021839b`: `%S(%d) Already in Hiding state, skipping re-entrant Hide(). ThreadId=%u`
- `0x18021850a`: `%S(%d) No frame to hide. ThreadId=%u`
- `0x180218406`: `%S(%d) State set to Hiding by Hide() method (likely called from Destroy()). ThreadId=%u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSharePickerExperienceManager::Hide(HWND *this)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // eax
  DWORD v4; // eax
  HWND v5; // rdi
  __int64 (__fastcall *v6)(HWND, __int64 *); // rbx
  int v7; // eax
  int v8; // eax
  HWND LastActivePopup; // rax
  DWORD v10; // eax
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v14; // [rsp+38h] [rbp+10h] BYREF
  HWND v15; // [rsp+40h] [rbp+18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
  {
    if ( CSharePickerExperienceManager::IsDestroyInProgress((CSharePickerExperienceManager *)this) )
    {
      CurrentThreadId = GetCurrentThreadId();
      NearbyShareUXTraceLogging::TraceLoggingInfo(
        "%S(%d) Already in Hiding state, skipping re-entrant Hide(). ThreadId=%u",
        "CSharePickerExperienceManager::Hide",
        709,
        CurrentThreadId);
      return 0;
    }
    if ( !this[82] )
    {
      v3 = GetCurrentThreadId();
      NearbyShareUXTraceLogging::TraceLoggingInfo(
        "%S(%d) No frame exists, setting state to Destroyed without transitioning through Hiding. ThreadId=%u",
        (const wchar_t *)"CSharePickerExperienceManager::Hide",
        716,
        v3);
      *((_DWORD *)this + 171) = 4;
      return 0;
    }
    *((_DWORD *)this + 171) = 3;
    v4 = GetCurrentThreadId();
    NearbyShareUXTraceLogging::TraceLoggingInfo(
      "%S(%d) State set to Hiding by Hide() method (likely called from Destroy()). ThreadId=%u",
      (const wchar_t *)"CSharePickerExperienceManager::Hide",
      721,
      v4);
  }
  if ( this[82] )
  {
    CSharePickerExperienceManager::HideInternal((CSharePickerExperienceManager *)this);
    v14 = 0;
    v5 = this[82];
    v6 = *(__int64 (__fastcall **)(HWND, __int64 *))(*(_QWORD *)v5 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    v7 = v6(v5, &v14);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
        (const char *)(unsigned int)v7,
        v12);
    v15 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v14 + 24LL))(v14, &v15);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2DA,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\sharepickerexperiencemanager.cpp",
        (const char *)(unsigned int)v8,
        v12);
    if ( GetForegroundWindow() == v15 && !SetForegroundWindow(this[103]) )
    {
      LastActivePopup = GetLastActivePopup(this[12]);
      SetForegroundWindow(LastActivePopup);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl'::`2'::impl) )
  {
    v10 = GetCurrentThreadId();
    NearbyShareUXTraceLogging::TraceLoggingInfo(
      "%S(%d) No frame to hide. ThreadId=%u",
      "CSharePickerExperienceManager::Hide",
      744,
      v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180218350  mov     [rsp+arg_0], rbx
0x180218355  mov     [rsp+arg_18], rsi
0x18021835a  push    rdi; int
0x18021835b  sub     rsp, 20h
0x18021835f  mov     rsi, rcx
0x180218362  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x180218369  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x18021836e  lea     rbx, aCsharepickerex_11; "CSharePickerExperienceManager::Hide"
0x180218375  test    al, al
0x180218377  jz      loc_180218412
0x18021837d  mov     rcx, rsi; this
0x180218380  call    ?IsDestroyInProgress@CSharePickerExperienceManager@@AEBA_NXZ; CSharePickerExperienceManager::IsDestroyInProgress(void)
0x180218385  test    al, al
0x180218387  jz      short loc_1802183A7
0x180218389  call    cs:__imp_GetCurrentThreadId
0x180218390  nop     dword ptr [rax+rax+00h]
0x180218395  mov     r8d, 2C5h
0x18021839b  lea     rcx, aSDAlreadyInHid; "%S(%d) Already in Hiding state, skippin"...
0x1802183a2  jmp     loc_180218511
0x1802183a7  cmp     qword ptr [rsi+290h], 0
0x1802183af  jnz     short loc_1802183E4
0x1802183b1  call    cs:__imp_GetCurrentThreadId
0x1802183b8  nop     dword ptr [rax+rax+00h]
0x1802183bd  mov     r9d, eax
0x1802183c0  mov     r8d, 2CCh
0x1802183c6  mov     rdx, rbx
0x1802183c9  lea     rcx, aSDNoFrameExist; "%S(%d) No frame exists, setting state t"...
0x1802183d0  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x1802183d5  mov     dword ptr [rsi+2ACh], 4
0x1802183df  jmp     loc_18021851C
0x1802183e4  mov     dword ptr [rsi+2ACh], 3
0x1802183ee  call    cs:__imp_GetCurrentThreadId
0x1802183f5  nop     dword ptr [rax+rax+00h]
0x1802183fa  mov     r9d, eax
0x1802183fd  mov     r8d, 2D1h
0x180218403  mov     rdx, rbx
0x180218406  lea     rcx, aSDStateSetToHi_0; "%S(%d) State set to Hiding by Hide() me"...
0x18021840d  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x180218412  cmp     qword ptr [rsi+290h], 0
0x18021841a  jz      loc_1802184E8
0x180218420  mov     rcx, rsi; this
0x180218423  call    ?HideInternal@CSharePickerExperienceManager@@AEAAJXZ; CSharePickerExperienceManager::HideInternal(void)
0x180218428  mov     [rsp+28h+arg_8], 0
0x180218431  mov     rdi, [rsi+290h]
0x180218438  mov     rax, [rdi]
0x18021843b  mov     rbx, [rax+20h]
0x18021843f  lea     rcx, [rsp+28h+arg_8]
0x180218444  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218449  lea     rdx, [rsp+28h+arg_8]
0x18021844e  mov     rcx, rdi
0x180218451  mov     rax, rbx
0x180218454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218459  mov     rcx, [rsp+28h]; this
0x18021845e  test    eax, eax
0x180218460  js      loc_180218544
0x180218466  mov     [rsp+28h+arg_10], 0
0x18021846f  mov     rcx, [rsp+28h+arg_8]
0x180218474  mov     rax, [rcx]
0x180218477  lea     rdx, [rsp+28h+arg_10]
0x18021847c  mov     rax, [rax+18h]
0x180218480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218485  mov     rcx, [rsp+28h]; this
0x18021848a  test    eax, eax
0x18021848c  js      loc_18021852F
0x180218492  call    cs:__imp_GetForegroundWindow
0x180218499  nop     dword ptr [rax+rax+00h]
0x18021849e  cmp     rax, [rsp+28h+arg_10]
0x1802184a3  jnz     short loc_1802184DC
0x1802184a5  mov     rcx, [rsi+338h]; hWnd
0x1802184ac  call    cs:__imp_SetForegroundWindow
0x1802184b3  nop     dword ptr [rax+rax+00h]
0x1802184b8  test    eax, eax
0x1802184ba  jnz     short loc_1802184DC
0x1802184bc  mov     rcx, [rsi+60h]; hWnd
0x1802184c0  call    cs:__imp_GetLastActivePopup
0x1802184c7  nop     dword ptr [rax+rax+00h]
0x1802184cc  mov     rcx, rax; hWnd
0x1802184cf  call    cs:__imp_SetForegroundWindow
0x1802184d6  nop     dword ptr [rax+rax+00h]
0x1802184db  nop
0x1802184dc  lea     rcx, [rsp+28h+arg_8]
0x1802184e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802184e6  jmp     short loc_18021851C
0x1802184e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IVCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest> `wil::Feature<__WilFeatureTraits_Feature_IVCFTest>::GetImpl(void)'::`2'::impl
0x1802184ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IVCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IVCFTest>::__private_IsEnabled(void)
0x1802184f4  test    al, al
0x1802184f6  jz      short loc_18021851C
0x1802184f8  call    cs:__imp_GetCurrentThreadId
0x1802184ff  nop     dword ptr [rax+rax+00h]
0x180218504  mov     r8d, 2E8h
0x18021850a  lea     rcx, aSDNoFrameToHid; "%S(%d) No frame to hide. ThreadId=%u"
0x180218511  mov     r9d, eax
0x180218514  mov     rdx, rbx
0x180218517  call    ?TraceLoggingInfo@NearbyShareUXTraceLogging@@SAXPEBDZZ; NearbyShareUXTraceLogging::TraceLoggingInfo(char const *,...)
0x18021851c  xor     eax, eax
0x18021851e  mov     rbx, [rsp+28h+arg_0]
0x180218523  mov     rsi, [rsp+28h+arg_18]
0x180218528  add     rsp, 20h
0x18021852c  pop     rdi
0x18021852d  retn
0x18021852f  mov     r9d, eax; char *
0x180218532  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x180218539  mov     edx, 2DAh; void *
0x18021853e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180218544  mov     r9d, eax; char *
0x180218547  lea     r8, aShellTwinuiExp_4; "shell\\twinui\\experiencemanagers\\lib"...
0x18021854e  mov     edx, 2D8h; void *
0x180218553  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
