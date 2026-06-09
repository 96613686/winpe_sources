# CXAMLHostWindow::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800300e0`
- end: `0x1800306db`
- name: `?v_WndProc@CXAMLHostWindow@@EEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1531`
- prototype: `__int64(CXAMLHostWindow *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005eb0`
- `0x180007b3c`
- `0x180007b68`
- `0x1800109b0`
- `0x180010a10`
- `0x18001285c`
- `0x180018ad8`
- `0x18002a464`
- `0x18002a748`
- `0x18002a8ec`
- `0x18002de8c`
- `0x18002f6a4`
- `0x18002fb9c`
- `0x18002fd74`
- `0x18002fe14`
- `0x1800300e0`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003056b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003056b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030328`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030328`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800305b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800305b4`
- `SHCORE!IUnknown_QueryService` at `0x1800302bf`
- `SHCORE!IUnknown_QueryService` at `0x1800302bf`
- `SHCORE!SHTaskPoolQueueTask` at `0x180030343`
- `SHCORE!SHTaskPoolQueueTask` at `0x180030343`
- `ntdll!RtlQueryResourcePolicy` at `0x180030287`
- `ntdll!RtlQueryResourcePolicy` at `0x180030287`
- `USER32!IsWindowInDestroy` at `0x1800304d5`
- `USER32!IsWindowInDestroy` at `0x1800304d5`
- `USER32!GetQueueStatus` at `0x180030535`
- `USER32!GetQueueStatus` at `0x180030535`
- `USER32!PostMessageW` at `0x1800303b8`
- `USER32!PostMessageW` at `0x180030556`
- `USER32!PostMessageW` at `0x1800303b8`
- `USER32!PostMessageW` at `0x180030556`
- `USER32!SystemParametersInfoW` at `0x18003064c`
- `USER32!SystemParametersInfoW` at `0x18003064c`
- `USER32!DefWindowProcW` at `0x1800303fb`
- `USER32!DefWindowProcW` at `0x1800303fb`
- `UxTheme!__imp_RefreshImmersiveColorPolicyState` at `0x1800305bf`
- `UxTheme!__imp_RefreshImmersiveColorPolicyState` at `0x1800305bf`
- `UxTheme!__imp_GetIsImmersiveColorUsingHighContrast` at `0x1800305cc`
- `UxTheme!__imp_GetIsImmersiveColorUsingHighContrast` at `0x180030611`
- `UxTheme!__imp_GetIsImmersiveColorUsingHighContrast` at `0x1800305cc`
- `UxTheme!__imp_GetIsImmersiveColorUsingHighContrast` at `0x180030611`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LRESULT __fastcall CXAMLHostWindow::v_WndProc(CXAMLHostWindow *this, HWND a2, UINT a3, WPARAM a4, LPARAM lParam)
{
  WPARAM v5; // r12
  LPARAM v8; // r13
  CXAMLHostWindow *v9; // r15
  unsigned __int64 v10; // r14
  unsigned __int64 i; // rbx
  __int64 v12; // rcx
  unsigned __int8 v13; // bl
  __int64 v14; // rcx
  char *v15; // r12
  __int64 v16; // rcx
  int v17; // r15d
  __int64 *v18; // rax
  __int64 v19; // r15
  __int64 v20; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v22; // rcx
  __int64 v24; // rbx
  __int64 v25; // rcx
  char v26; // bl
  __int64 v27; // rcx
  int (__fastcall ***v28)(_QWORD, GUID *, void **); // rdi
  int (__fastcall *v29)(_QWORD, GUID *, void **); // rbx
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-91h]
  char *v31; // [rsp+28h] [rbp-89h]
  bool v32[8]; // [rsp+40h] [rbp-71h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-69h] BYREF
  int v34; // [rsp+50h] [rbp-61h]
  void *v35; // [rsp+58h] [rbp-59h] BYREF
  WPARAM v36; // [rsp+60h] [rbp-51h] BYREF
  _BYTE pvParam[12]; // [rsp+68h] [rbp-49h] BYREF
  int v38; // [rsp+74h] [rbp-3Dh]
  WPARAM *v39; // [rsp+80h] [rbp-31h] BYREF
  void **v40; // [rsp+88h] [rbp-29h]
  HWND hWnd; // [rsp+90h] [rbp-21h]
  __int64 v42; // [rsp+98h] [rbp-19h]
  __int64 v43; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-9h]

  v5 = a4;
  v36 = a4;
  hWnd = a2;
  v8 = lParam;
  *(_QWORD *)pvParam = lParam;
  v9 = (CXAMLHostWindow *)((char *)this - 184);
  v10 = *((_QWORD *)this + 21);
  v42 = 0;
  v34 = 0;
  HIDWORD(v40) = 0;
  for ( i = 0; i < v10; ++i )
  {
    v43 = 0;
    v44 = 0;
    v12 = *(_QWORD *)(*((_QWORD *)this + 20) + 8 * i);
    (*(void (__fastcall **)(__int64, HWND, _QWORD, WPARAM, LPARAM, __int64 *))(*(_QWORD *)v12 + 24LL))(
      v12,
      a2,
      a3,
      v5,
      lParam,
      &v43);
    if ( (_DWORD)v44 )
    {
      v42 = v43;
      v34 = v44;
      break;
    }
    a2 = hWnd;
  }
  switch ( a3 )
  {
    case 0x47u:
      if ( ((*(_DWORD *)(lParam + 32) & 0x40) == 0 || (*(_BYTE *)(lParam + 32) & 0x10) != 0)
        && *(char *)(lParam + 32) >= 0 )
      {
        goto LABEL_38;
      }
      v13 = (*(_DWORD *)(lParam + 32) & 0x40) != 0;
      goto LABEL_14;
    case 0x270u:
      if ( (lParam & 8) == 0 )
      {
        v13 = lParam & 1;
LABEL_14:
        if ( *((_BYTE *)this + 232) != v13 )
        {
          v14 = *((_QWORD *)this + 3);
          if ( v14 && !v13 && *((_QWORD *)this + 8) )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 104LL))(v14);
          *((_BYTE *)this + 232) = v13;
          v15 = (char *)this - 56;
          if ( v13 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 240);
            CXAMLHostWindow::_AcquireLightDismiss(v9);
          }
          else
          {
            CXAMLHostWindow::_ReleaseLightDismiss(v9);
            (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 64LL))((char *)this - 56);
            v16 = *((_QWORD *)this + 3);
            if ( v16 && *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16) + 44) != -1 )
            {
              LODWORD(v35) = 0;
              RtlQueryResourcePolicy(0, 0, &v35, 4);
              ppvOut = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
              if ( IUnknown_QueryService(
                     *((IUnknown **)this - 9),
                     &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                     &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                     &ppvOut) >= 0 )
              {
                v17 = *((_DWORD *)this + 62);
                v39 = (WPARAM *)ppvOut;
                if ( ppvOut )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 8LL))(ppvOut);
                LODWORD(v40) = v17;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 240);
                v18 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_c591d59d8b44f1cd49b9c379e68531fb_____lambda_c591d59d8b44f1cd49b9c379e68531fb___(
                                   &v43,
                                   &v39);
                v19 = *v18;
                *v18 = 0;
                v20 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Xaml::IRoutedEventHandler>::Release(v20);
                }
                CurrentThreadId = GetCurrentThreadId();
                v31 = (char *)this + 240;
                *(_QWORD *)bIgnoreCase = v19;
                SHTaskPoolQueueTask(1, 0, CurrentThreadId);
                if ( v19 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v39);
                v9 = (CXAMLHostWindow *)((char *)this - 184);
                v8 = *(_QWORD *)pvParam;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
            }
          }
          CXAMLHostWindow::_UpdateXAMLSuspendState(v9);
          if ( v13 && *((_BYTE *)this + 264) )
            (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v15 + 24LL))((char *)this - 56, 1);
          PostMessageW(*((HWND *)this + 1), *((_DWORD *)this + 71), v13, 0);
          if ( (Microsoft_Windows_UI_SearchEnableBits & 1) != 0 )
            McTemplateU0qq_EventWriteTransfer(
              v22,
              XamlHostWindow_VisibilityChanged,
              v13,
              *((unsigned int *)this + 62),
              *(_QWORD *)bIgnoreCase,
              v31);
          v5 = v36;
        }
        goto LABEL_38;
      }
      break;
    case 0x10u:
      return v42;
  }
  if ( a3 == *((_DWORD *)this + 71) )
  {
    ppvOut = 0;
    v32[0] = v5 != 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    if ( (int)Microsoft::WRL::Details::MakeAndInitialize<CViewVisibleEventArgs,Windows::UI::Search::Internal::Common::IViewVisibiltyChangedEventArgs,bool>(
                &ppvOut,
                v32) >= 0 )
    {
      v35 = ppvOut;
      v36 = 0;
      v43 = 0;
      wil::AcquireSRWLockExclusive(pvParam, (char *)this + 296);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v43, (char *)this + 288);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)pvParam);
      v24 = v43;
      if ( v43 )
      {
        v39 = &v36;
        v40 = &v35;
        Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_24115faddddd4761b62940e1faa8a8ba_,Windows::UI::Search::Internal::Common::IViewVisibilityChangedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(
          &v39,
          v43,
          (__int64)this + 288);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v24);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  }
  else if ( a3 == 6 )
  {
    if ( *((_BYTE *)this + 264) && !(unsigned int)IsWindowInDestroy(*((_QWORD *)this + 1)) )
      (*(void (__fastcall **)(char *, bool))(*((_QWORD *)this - 7) + 24LL))((char *)this - 56, (_WORD)v5 == 0);
    if ( (_WORD)v5 )
    {
      v25 = *((_QWORD *)this + 3);
      if ( v25 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 112LL))(v25, *((_QWORD *)this + 8));
    }
  }
  else if ( a3 == *((_DWORD *)this + 49) )
  {
    if ( !(GetQueueStatus(0x48u) >> 16) || !PostMessageW(*((HWND *)this + 1), *((_DWORD *)this + 49), 0, 0) )
      SetEvent(*((HANDLE *)this + 25));
  }
  else
  {
    if ( a3 == *((_DWORD *)this + 68) )
    {
      CXAMLHostWindow::_UpdatePosition(v9);
      goto LABEL_38;
    }
    if ( a3 == 26 )
    {
      v26 = 0;
      if ( lParam && CompareStringOrdinal((LPCWCH)lParam, -1, L"ImmersiveColorSet", -1, 1) == 2 )
      {
        RefreshImmersiveColorPolicyState();
        v26 = 1;
      }
      GetIsImmersiveColorUsingHighContrast(1);
      if ( v26 )
      {
        CXAMLHostWindow::_UpdateAccentPolicy(v9);
      }
      else
      {
        if ( v5 != 67 )
          goto LABEL_38;
        GetIsImmersiveColorUsingHighContrast(1);
      }
      v27 = *((_QWORD *)this + 3);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 144LL))(v27);
    }
    else if ( a3 == 800 )
    {
      if ( *((_QWORD *)this + 8) )
      {
        *(_DWORD *)pvParam = 16;
        *(_QWORD *)&pvParam[4] = 0;
        v38 = 0;
        if ( !SystemParametersInfoW(0x42u, 0x10u, pvParam, 0) || (pvParam[4] & 1) == 0 )
        {
          ppvOut = 0;
          v28 = (int (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 8);
          v29 = **v28;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
          if ( v29(v28, &GUID_46b7f8b4_7994_436d_9454_7966bb126d03, &ppvOut) >= 0 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 48LL))(ppvOut);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
        }
      }
    }
  }
LABEL_38:
  if ( !v34 )
    return DefWindowProcW(hWnd, a3, v5, v8);
  return v42;
}

```

## disassembly

```asm
0x1800300e0  push    rbp
0x1800300e2  push    rbx
0x1800300e3  push    rsi
0x1800300e4  push    rdi
0x1800300e5  push    r12
0x1800300e7  push    r13
0x1800300e9  push    r14
0x1800300eb  push    r15
0x1800300ed  lea     rbp, [rsp-17h]
0x1800300f2  sub     rsp, 0C8h
0x1800300f9  mov     rax, cs:__security_cookie
0x180030100  xor     rax, rsp
0x180030103  mov     [rbp+4Fh+var_50], rax
0x180030107  mov     r12, r9
0x18003010a  mov     [rbp+4Fh+var_A0], r9
0x18003010e  mov     esi, r8d
0x180030111  mov     [rbp+4Fh+hWnd], rdx
0x180030115  mov     rdi, rcx
0x180030118  mov     r13, [rbp+4Fh+lParam]
0x18003011c  mov     qword ptr [rbp+4Fh+pvParam], r13
0x180030120  lea     r15, [rcx-0B8h]
0x180030127  mov     r14, [r15+160h]
0x18003012e  xor     r8d, r8d
0x180030131  mov     [rbp+4Fh+var_68], r8
0x180030135  mov     [rbp+4Fh+var_B0], r8d
0x180030139  xor     eax, eax
0x18003013b  mov     dword ptr [rbp+4Fh+var_78+4], eax
0x18003013e  mov     ebx, r8d
0x180030141  cmp     rbx, r14
0x180030144  jnb     short loc_18003019B
0x180030146  mov     [rbp+4Fh+var_60], r8
0x18003014a  mov     [rbp+4Fh+var_58], 0
0x180030152  mov     rax, [rdi+0A0h]
0x180030159  mov     rcx, [rax+rbx*8]
0x18003015d  mov     rax, [rcx]
0x180030160  lea     r8, [rbp+4Fh+var_60]
0x180030164  mov     [rsp+100h+var_D8], r8
0x180030169  mov     qword ptr [rsp+100h+bIgnoreCase], r13
0x18003016e  mov     r9, r12
0x180030171  mov     r8d, esi
0x180030174  mov     rax, [rax+18h]
0x180030178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003017d  mov     eax, dword ptr [rbp+4Fh+var_58]
0x180030180  xor     r8d, r8d
0x180030183  test    eax, eax
0x180030185  jnz     short loc_180030190
0x180030187  inc     rbx
0x18003018a  mov     rdx, [rbp+4Fh+hWnd]
0x18003018e  jmp     short loc_180030141
0x180030190  mov     rcx, [rbp+4Fh+var_60]
0x180030194  mov     [rbp+4Fh+var_68], rcx
0x180030198  mov     [rbp+4Fh+var_B0], eax
0x18003019b  cmp     esi, 47h ; 'G'
0x18003019e  jnz     short loc_1800301C2
0x1800301a0  mov     eax, [r13+20h]
0x1800301a4  and     eax, 40h
0x1800301a7  jz      short loc_1800301B0
0x1800301a9  test    byte ptr [r13+20h], 10h
0x1800301ae  jz      short loc_1800301BB
0x1800301b0  test    byte ptr [r13+20h], 80h
0x1800301b5  jz      loc_1800303E2
0x1800301bb  test    eax, eax
0x1800301bd  setnz   bl
0x1800301c0  jmp     short loc_1800301DE
0x1800301c2  cmp     esi, 270h
0x1800301c8  jnz     loc_180030406
0x1800301ce  test    r13b, 8
0x1800301d2  jnz     loc_18003040F
0x1800301d8  mov     bl, r13b
0x1800301db  and     bl, 1
0x1800301de  cmp     [rdi+0E8h], bl
0x1800301e4  jz      loc_1800303E2
0x1800301ea  mov     rcx, [rdi+18h]
0x1800301ee  test    rcx, rcx
0x1800301f1  jz      short loc_18003020C
0x1800301f3  test    bl, bl
0x1800301f5  jnz     short loc_18003020C
0x1800301f7  mov     rdx, [rdi+40h]
0x1800301fb  test    rdx, rdx
0x1800301fe  jz      short loc_18003020C
0x180030200  mov     rax, [rcx]
0x180030203  mov     rax, [rax+68h]
0x180030207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003020c  mov     [rdi+0E8h], bl
0x180030212  lea     r12, [rdi-38h]
0x180030216  test    bl, bl
0x180030218  jz      short loc_180030233
0x18003021a  lea     rcx, [rdi+0F0h]
0x180030221  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030226  mov     rcx, r15; this
0x180030229  call    ?_AcquireLightDismiss@CXAMLHostWindow@@AEAAJXZ; CXAMLHostWindow::_AcquireLightDismiss(void)
0x18003022e  jmp     loc_18003037C
0x180030233  mov     rcx, r15; this
0x180030236  call    ?_ReleaseLightDismiss@CXAMLHostWindow@@AEAAXXZ; CXAMLHostWindow::_ReleaseLightDismiss(void)
0x18003023b  mov     rax, [r12]
0x18003023f  mov     rcx, r12
0x180030242  mov     rax, [rax+40h]
0x180030246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003024b  mov     rcx, [rdi+18h]
0x18003024f  test    rcx, rcx
0x180030252  jz      loc_18003037C
0x180030258  mov     rax, [rcx]
0x18003025b  mov     rax, [rax+18h]
0x18003025f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030264  mov     r14d, [rax+2Ch]
0x180030268  cmp     r14d, 0FFFFFFFFh
0x18003026c  jz      loc_18003037C
0x180030272  mov     dword ptr [rbp+4Fh+var_A8], 0
0x180030279  mov     r9d, 4
0x18003027f  lea     r8, [rbp+4Fh+var_A8]
0x180030283  xor     edx, edx
0x180030285  xor     ecx, ecx
0x180030287  call    cs:__imp_RtlQueryResourcePolicy
0x18003028d  xor     ecx, ecx
0x18003028f  test    eax, eax
0x180030291  js      short loc_1800302A0
0x180030293  mov     eax, 1D4C0h
0x180030298  cmp     dword ptr [rbp+4Fh+var_A8], 0Ah
0x18003029c  cmovle  r14d, eax
0x1800302a0  mov     [rbp+4Fh+ppvOut], rcx
0x1800302a4  lea     rcx, [rbp+4Fh+ppvOut]
0x1800302a8  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800302ad  lea     r9, [rbp+4Fh+ppvOut]; ppvOut
0x1800302b1  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x1800302b8  mov     r8, rdx; riid
0x1800302bb  mov     rcx, [rdi-48h]; punk
0x1800302bf  call    cs:__imp_IUnknown_QueryService
0x1800302c5  test    eax, eax
0x1800302c7  js      loc_180030373
0x1800302cd  mov     r15d, [rdi+0F8h]
0x1800302d4  mov     rcx, [rbp+4Fh+ppvOut]
0x1800302d8  mov     [rbp+4Fh+var_80], rcx
0x1800302dc  test    rcx, rcx
0x1800302df  jz      short loc_1800302EE
0x1800302e1  mov     rax, [rcx]
0x1800302e4  mov     rax, [rax+8]
0x1800302e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302ed  nop
0x1800302ee  mov     dword ptr [rbp+4Fh+var_78], r15d
0x1800302f2  lea     r13, [rdi+0F0h]
0x1800302f9  mov     rcx, r13
0x1800302fc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030301  lea     rdx, [rbp+4Fh+var_80]
0x180030305  lea     rcx, [rbp+4Fh+var_60]
0x180030309  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_c591d59d8b44f1cd49b9c379e68531fb_____lambda_c591d59d8b44f1cd49b9c379e68531fb___
0x18003030e  mov     r15, [rax]
0x180030311  xor     edx, edx
0x180030313  mov     [rax], rdx
0x180030316  mov     rcx, [rbp+4Fh+var_60]
0x18003031a  test    rcx, rcx
0x18003031d  jz      short loc_180030328
0x18003031f  mov     [rbp+4Fh+var_60], rdx
0x180030323  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRoutedEventHandler@Xaml@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Xaml::IRoutedEventHandler>::Release(void)
0x180030328  call    cs:__imp_GetCurrentThreadId
0x18003032e  mov     [rsp+100h+var_D8], r13
0x180030333  mov     qword ptr [rsp+100h+bIgnoreCase], r15
0x180030338  mov     r9d, r14d
0x18003033b  mov     r8d, eax
0x18003033e  xor     edx, edx
0x180030340  lea     ecx, [rdx+1]
0x180030343  call    cs:__imp_SHTaskPoolQueueTask
0x180030349  nop
0x18003034a  test    r15, r15
0x18003034d  jz      short loc_18003035F
0x18003034f  mov     rax, [r15]
0x180030352  mov     rcx, r15
0x180030355  mov     rax, [rax+10h]
0x180030359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003035e  nop
0x18003035f  lea     rcx, [rbp+4Fh+var_80]
0x180030363  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030368  lea     r15, [rdi-0B8h]
0x18003036f  mov     r13, qword ptr [rbp+4Fh+pvParam]
0x180030373  lea     rcx, [rbp+4Fh+ppvOut]
0x180030377  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003037c  mov     rcx, r15; this
0x18003037f  call    ?_UpdateXAMLSuspendState@CXAMLHostWindow@@AEAAXXZ; CXAMLHostWindow::_UpdateXAMLSuspendState(void)
0x180030384  xor     eax, eax
0x180030386  test    bl, bl
0x180030388  jz      short loc_1800303A7
0x18003038a  cmp     [rdi+108h], al
0x180030390  jz      short loc_1800303A7
0x180030392  mov     rax, [r12]
0x180030396  mov     edx, 1
0x18003039b  mov     rcx, r12
0x18003039e  mov     rax, [rax+18h]
0x1800303a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303a7  movzx   r8d, bl; wParam
0x1800303ab  xor     r9d, r9d; lParam
0x1800303ae  mov     edx, [rdi+11Ch]; Msg
0x1800303b4  mov     rcx, [rdi+8]; hWnd
0x1800303b8  call    cs:__imp_PostMessageW
0x1800303be  test    byte ptr cs:Microsoft_Windows_UI_SearchEnableBits, 1
0x1800303c5  jz      short loc_1800303DE
0x1800303c7  movzx   r8d, bl
0x1800303cb  mov     r9d, [rdi+0F8h]
0x1800303d2  lea     rdx, XamlHostWindow_VisibilityChanged
0x1800303d9  call    McTemplateU0qq_EventWriteTransfer
0x1800303de  mov     r12, [rbp+4Fh+var_A0]
0x1800303e2  xor     r14d, r14d
0x1800303e5  cmp     [rbp+4Fh+var_B0], r14d
0x1800303e9  jnz     loc_1800306B7
0x1800303ef  mov     r9, r13; lParam
0x1800303f2  mov     r8, r12; wParam
0x1800303f5  mov     edx, esi; Msg
0x1800303f7  mov     rcx, [rbp+4Fh+hWnd]; hWnd
0x1800303fb  call    cs:__imp_DefWindowProcW
0x180030401  jmp     loc_1800306BB
0x180030406  cmp     esi, 10h
0x180030409  jz      loc_1800306B7
0x18003040f  cmp     esi, [rdi+11Ch]
0x180030415  jnz     loc_1800304C3
0x18003041b  mov     [rbp+4Fh+ppvOut], r8
0x18003041f  test    r12, r12
0x180030422  setnz   [rbp+4Fh+var_C0]
0x180030426  lea     rcx, [rbp+4Fh+ppvOut]
0x18003042a  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003042f  lea     rdx, [rbp+4Fh+var_C0]
0x180030433  lea     rcx, [rbp+4Fh+ppvOut]
0x180030437  call    ??$MakeAndInitialize@VCViewVisibleEventArgs@@UIViewVisibiltyChangedEventArgs@Common@Internal@Search@UI@Windows@@_N@Details@WRL@Microsoft@@YAJPEAPEAUIViewVisibiltyChangedEventArgs@Common@Internal@Search@UI@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<CViewVisibleEventArgs,Windows::UI::Search::Internal::Common::IViewVisibiltyChangedEventArgs,bool>(Windows::UI::Search::Internal::Common::IViewVisibiltyChangedEventArgs * *,bool &&)
0x18003043c  xor     ecx, ecx
0x18003043e  test    eax, eax
0x180030440  js      short loc_1800304B5
0x180030442  mov     rax, [rbp+4Fh+ppvOut]
0x180030446  mov     [rbp+4Fh+var_A8], rax
0x18003044a  mov     [rbp+4Fh+var_A0], rcx
0x18003044e  mov     [rbp+4Fh+var_60], rcx
0x180030452  lea     rdx, [rdi+128h]
0x180030459  lea     rcx, [rbp+4Fh+pvParam]
0x18003045d  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180030462  lea     rdx, [rdi+120h]
0x180030469  lea     rcx, [rbp+4Fh+var_60]
0x18003046d  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x180030472  lea     rcx, [rbp+4Fh+pvParam]; this
0x180030476  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18003047b  mov     rbx, [rbp+4Fh+var_60]
0x18003047f  test    rbx, rbx
0x180030482  jz      short loc_1800304B5
0x180030484  lea     rax, [rbp+4Fh+var_A0]
0x180030488  mov     [rbp+4Fh+var_80], rax
0x18003048c  lea     rax, [rbp+4Fh+var_A8]
0x180030490  mov     [rbp+4Fh+var_78], rax
0x180030494  lea     r8, [rdi+120h]
0x18003049b  mov     rdx, rbx
0x18003049e  lea     rcx, [rbp+4Fh+var_80]
0x1800304a2  call    ??$InvokeDelegates@V_lambda_24115faddddd4761b62940e1faa8a8ba_@@UIViewVisibilityChangedEventHandler@Common@Internal@Search@UI@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_24115faddddd4761b62940e1faa8a8ba_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@UIViewVisibilityChangedEventHandler@Common@Internal@Search@UI@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_24115faddddd4761b62940e1faa8a8ba_,Windows::UI::Search::Internal::Common::IViewVisibilityChangedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_24115faddddd4761b62940e1faa8a8ba_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::UI::Search::Internal::Common::IViewVisibilityChangedEventHandler,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x1800304a7  test    rbx, rbx
0x1800304aa  jz      short loc_1800304B5
0x1800304ac  mov     rcx, rbx
0x1800304af  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x1800304b4  nop
0x1800304b5  lea     rcx, [rbp+4Fh+ppvOut]
0x1800304b9  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800304be  jmp     loc_1800303E2
0x1800304c3  cmp     esi, 6
0x1800304c6  jnz     short loc_180030528
0x1800304c8  cmp     [rdi+108h], r8b
0x1800304cf  jz      short loc_1800304FC
0x1800304d1  mov     rcx, [rdi+8]
0x1800304d5  call    cs:__imp_IsWindowInDestroy
0x1800304db  xor     r8d, r8d
0x1800304de  test    eax, eax
0x1800304e0  jnz     short loc_1800304FC
0x1800304e2  lea     rcx, [rdi-38h]
0x1800304e6  mov     rax, [rcx]
0x1800304e9  mov     edx, r8d
0x1800304ec  test    r12w, r12w
0x1800304f0  setz    dl
0x1800304f3  mov     rax, [rax+18h]
0x1800304f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304fc  test    r12w, r12w
0x180030500  jz      loc_1800303E2
0x180030506  mov     rcx, [rdi+18h]
0x18003050a  test    rcx, rcx
0x18003050d  jz      loc_1800303E2
0x180030513  mov     rax, [rcx]
0x180030516  mov     rdx, [rdi+40h]
0x18003051a  mov     rax, [rax+70h]
0x18003051e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030523  jmp     loc_1800303E2
0x180030528  cmp     esi, [rdi+0C4h]
0x18003052e  jnz     short loc_180030576
0x180030530  mov     ecx, 48h ; 'H'; flags
0x180030535  call    cs:__imp_GetQueueStatus
0x18003053b  shr     eax, 10h
0x18003053e  xor     r14d, r14d
0x180030541  test    ax, ax
0x180030544  jz      short loc_180030564
0x180030546  xor     r9d, r9d; lParam
0x180030549  xor     r8d, r8d; wParam
0x18003054c  mov     edx, [rdi+0C4h]; Msg
0x180030552  mov     rcx, [rdi+8]; hWnd
0x180030556  call    cs:__imp_PostMessageW
0x18003055c  test    eax, eax
0x18003055e  jnz     loc_1800303E5
0x180030564  mov     rcx, [rdi+0C8h]; hEvent
0x18003056b  call    cs:__imp_SetEvent
0x180030571  jmp     loc_1800303E5
0x180030576  cmp     esi, [rdi+110h]
0x18003057c  jnz     short loc_18003058B
  ... truncated ...
```
