# ProviderEntryPoint::WriteElementCompletionInfo(UIAutomationCoreProto::ElementRefRetMsg &,IServerConnection *)

- ea: `0x1800d9a78`
- end: `0x1800da0ef`
- name: `?WriteElementCompletionInfo@ProviderEntryPoint@@QEAAXAEAVElementRefRetMsg@UIAutomationCoreProto@@PEAVIServerConnection@@@Z`
- size: `1655`
- prototype: `void __fastcall(ProviderEntryPoint *__hidden this, struct UIAutomationCoreProto::ElementRefRetMsg *, struct IServerConnection *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180054724`

## callees

- `0x18000f680`
- `0x18002f580`
- `0x180032724`
- `0x18003635c`
- `0x1800d9a78`
- `0x1800da0f8`
- `0x1800dad04`
- `0x1800dadfc`
- `0x1801a8cf4`
- `0x1801e8320`
- `0x1801e887c`
- `0x1801e8a1c`
- `0x1801e8a84`
- `0x1801e9258`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800da071`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800da0ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800da071`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800da0ac`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800da05e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800da099`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800da05e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800da099`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800d9b1a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800d9b1a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetAncestor` at `0x1800d9cd3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetAncestor` at `0x1800d9cd3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800d9fed`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800da001`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800d9fed`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800da001`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800d9b01`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800d9b01`

## string_xrefs

- `0x1800d9c10`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800d9c85`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800d9ecd`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800da01e`: `onecore\windows\accessibletech\uiautomationcore\providerentrypoint.cpp`
- `0x1800da057`: `user32.dll`
- `0x1800da092`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall ProviderEntryPoint::WriteElementCompletionInfo(
        ProviderEntryPoint *this,
        struct UIAutomationCoreProto::ElementRefRetMsg *a2,
        struct IServerConnection *a3)
{
  __int64 v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // rax
  __int8 v9; // bl
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  HWND v15; // rbx
  HWND Ancestor; // r14
  __int64 v17; // r15
  DWORD v18; // ebx
  DWORD v19; // eax
  char *v20; // rax
  char *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r10
  __int64 v24; // rax
  int v25; // eax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v28; // rax
  FARPROC v29; // rax
  int v30; // [rsp+20h] [rbp-138h]
  DWORD v31[2]; // [rsp+30h] [rbp-128h] BYREF
  DWORD dwProcessId[2]; // [rsp+38h] [rbp-120h] BYREF
  __int128 v33; // [rsp+40h] [rbp-118h] BYREF
  __m128i v34; // [rsp+50h] [rbp-108h]
  _OWORD v35[2]; // [rsp+60h] [rbp-F8h] BYREF
  _QWORD v36[2]; // [rsp+80h] [rbp-D8h] BYREF
  __int128 ClassName; // [rsp+90h] [rbp-C8h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-B8h]
  __int128 v39; // [rsp+B0h] [rbp-A8h]
  __m128i v40; // [rsp+C0h] [rbp-98h]
  char v41; // [rsp+D0h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v36[1] = a2;
  if ( *((_DWORD *)this + 10) )
    return;
  memset_0(&ClassName, 0, 0x80u);
  if ( GetClassNameW(*((HWND *)this + 3), (LPWSTR)&ClassName, 64) )
  {
    if ( !lstrcmpiW((LPCWSTR)&ClassName, L"ConsoleWindowClass") )
      return;
  }
  v6 = *((_QWORD *)a2 + 3);
  if ( !v6 )
  {
    v7 = (_QWORD *)(*((_QWORD *)a2 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
    if ( (*((_BYTE *)a2 + 8) & 1) != 0 )
      v7 = (_QWORD *)*v7;
    v6 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementCompletionInfoMsg,>(v7);
    *((_QWORD *)a2 + 3) = v6;
  }
  ProviderEntryPoint::TryGetInProcNativeUiaNode(this, v36, &qword_180311AB8);
  v8 = v36[0];
  if ( v36[0] )
  {
    v13 = *(_QWORD *)(v36[0] + 264LL);
    v34.m128i_i8[8] = 0;
    *(__int32 *)((char *)&v34.m128i_i32[2] + 1) = 0;
    *(__int16 *)((char *)&v34.m128i_i16[6] + 1) = 0;
    v34.m128i_i8[15] = 0;
    *(_QWORD *)&v33 = v6;
    *((_QWORD *)&v33 + 1) = a3;
    v36[0] = 0;
    v34.m128i_i64[0] = v8;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(), __int128 *, __int64))(*(_QWORD *)v13 + 24LL))(
            v13,
            anonymous_namespace_::WriteEntryPointNativeProviderInCorrectContext,
            &v33,
            500);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4FC,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
        (const char *)(unsigned int)v14,
        v30);
    v9 = v34.m128i_i8[8];
  }
  else
  {
    v9 = 0;
  }
  if ( *((_DWORD *)this + 10) )
    v10 = 0;
  else
    v10 = *((_QWORD *)this + 3);
  *(_QWORD *)dwProcessId = v10;
  MakeCom<HwndInvoker,HWND__ *>(v31, dwProcessId);
  *(_DWORD *)((char *)v35 + 1) = 0;
  *(_WORD *)((char *)v35 + 5) = 0;
  BYTE7(v35[0]) = 0;
  *(_QWORD *)&v33 = v6;
  *((_QWORD *)&v33 + 1) = a3;
  v34.m128i_i64[0] = 0x1F400000001LL;
  if ( *((_DWORD *)this + 10) )
    v11 = 0;
  else
    v11 = *((_QWORD *)this + 3);
  v34.m128i_i64[1] = v11;
  LOBYTE(v35[0]) = v9;
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(__int64), __int128 *, __int64))(**(_QWORD **)v31 + 24LL))(
          *(_QWORD *)v31,
          anonymous_namespace_::WriteEntryPointProxyProvidersInCorrectContext,
          &v33,
          500);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51A,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
      (const char *)(unsigned int)v12,
      v30);
  if ( *(_QWORD *)v31 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
  if ( *((_DWORD *)this + 10) )
    v15 = 0;
  else
    v15 = (HWND)*((_QWORD *)this + 3);
  Ancestor = GetAncestor(v15, 1u);
  if ( Ancestor )
  {
    dwProcessId[0] = 0;
    v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( dword_1803A34B0 > *(_DWORD *)(v17 + 88) )
    {
      Init_thread_header(&dword_1803A34B0);
      if ( dword_1803A34B0 == -1 )
      {
        LibraryW = LoadLibraryW(L"user32.dll");
        if ( LibraryW )
          ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0xA98);
        else
          ProcAddress = 0;
        qword_1803A34B8 = (__int64 (__fastcall *)(_QWORD))ProcAddress;
        Init_thread_footer(&dword_1803A34B0);
      }
    }
    if ( qword_1803A34B8 )
    {
      v18 = qword_1803A34B8(v15);
      dwProcessId[0] = v18;
    }
    else
    {
      GetWindowThreadProcessId(v15, dwProcessId);
      v18 = dwProcessId[0];
    }
    v31[0] = 0;
    if ( dword_1803A34B0 > *(_DWORD *)(v17 + 88) )
    {
      Init_thread_header(&dword_1803A34B0);
      if ( dword_1803A34B0 == -1 )
      {
        v28 = LoadLibraryW(L"user32.dll");
        if ( v28 )
          v29 = GetProcAddress(v28, (LPCSTR)0xA98);
        else
          v29 = 0;
        qword_1803A34B8 = (__int64 (__fastcall *)(_QWORD))v29;
        Init_thread_footer(&dword_1803A34B0);
      }
    }
    if ( qword_1803A34B8 )
    {
      v19 = qword_1803A34B8(Ancestor);
      v31[0] = v19;
    }
    else
    {
      GetWindowThreadProcessId(Ancestor, v31);
      v19 = v31[0];
    }
    if ( v18 == v19 )
    {
      *(_QWORD *)v31 = 0;
      v20 = (char *)operator new(0x160u, (const struct std::nothrow_t *)std::nothrow);
      v21 = v20;
      if ( v20 )
      {
        v41 = 0;
        *((_QWORD *)v20 + 1) = &RefcountBase::`vftable';
        *((_DWORD *)v20 + 4) = 1;
        _InterlockedIncrement(&dword_18039DE7C);
        *(_QWORD *)v20 = &ProviderEntryPoint::`vftable'{for `IUnknown'};
        *((_QWORD *)v20 + 1) = &ProviderEntryPoint::`vftable'{for `RefcountBase'};
        *(_OWORD *)(v20 + 24) = 0;
        *((_DWORD *)v20 + 10) = 0;
        *(_OWORD *)(v20 + 44) = v33;
        v20[60] = 0;
        *(_WORD *)(v20 + 61) = *(__int16 *)((char *)v34.m128i_i16 + 1);
        v20[63] = v34.m128i_i8[3];
        *((_QWORD *)v20 + 8) = 0;
        v20[216] = 0;
        v20[228] = 0;
        v20[264] = 0;
        v20[304] = 0;
        v20[344] = 0;
        if ( v41 )
        {
          v33 = ClassName;
          v34 = si128;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(ClassName) = 0;
          v35[0] = v39;
          v35[1] = v40;
          v40 = si128;
          LOWORD(v39) = 0;
          std::optional<std::wstring>::operator=<std::wstring,0>(v20 + 232, &v33);
          std::optional<std::wstring>::operator=<std::wstring,0>(v21 + 272, v35);
          AppContainerInfo::~AppContainerInfo((AppContainerInfo *)&v33);
          if ( v41 )
            AppContainerInfo::~AppContainerInfo((AppContainerInfo *)&ClassName);
        }
        *((_DWORD *)v21 + 10) = 0;
        *((_QWORD *)v21 + 3) = Ancestor;
        *((_QWORD *)v21 + 8) = 0;
        ProviderEntryPoint::TryGetInProcNativeUiaNode(v21, v31, &qword_180311AB8);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 16LL))(v21);
        v22 = *(_QWORD *)v31;
        goto LABEL_35;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
        (const char *)0x8007000ELL,
        v30);
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(v31);
    }
    else
    {
      *(_BYTE *)(v6 + 48) = 1;
    }
  }
  v22 = 0;
LABEL_35:
  if ( v22 )
  {
    v23 = *(_QWORD *)(v22 + 264);
    *(_QWORD *)&v33 = v6;
    *((_QWORD *)&v33 + 1) = a3;
    v34.m128i_i64[0] = 0x1F400000001LL;
    *(_QWORD *)v31 = 0;
    v34.m128i_i64[1] = v22;
    if ( *((_DWORD *)this + 10) )
      v24 = 0;
    else
      v24 = *((_QWORD *)this + 3);
    *(_QWORD *)&v35[0] = v24;
    v25 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(), __int128 *, __int64))(*(_QWORD *)v23 + 24LL))(
            v23,
            anonymous_namespace_::WriteParentHwndOverrideProviderInCorrectContext,
            &v33,
            500);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x53F,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\providerentrypoint.cpp",
        (const char *)(unsigned int)v25,
        v30);
  }
}

```

## disassembly

```asm
0x1800d9a78  push    rbx
0x1800d9a7a  push    rsi
0x1800d9a7b  push    rdi
0x1800d9a7c  push    r12
0x1800d9a7e  push    r13
0x1800d9a80  push    r14
0x1800d9a82  push    r15
0x1800d9a84  sub     rsp, 120h
0x1800d9a8b  mov     rax, cs:__security_cookie
0x1800d9a92  xor     rax, rsp
0x1800d9a95  mov     [rsp+158h+var_48], rax
0x1800d9a9d  mov     r12, r8
0x1800d9aa0  mov     rbx, rdx
0x1800d9aa3  mov     rdi, rcx
0x1800d9aa6  mov     [rsp+158h+var_D0], rdx
0x1800d9aae  xor     r13d, r13d
0x1800d9ab1  cmp     [rcx+28h], r13d
0x1800d9ab5  jz      short loc_1800D9ADA
0x1800d9ab7  mov     rcx, [rsp+158h+var_48]
0x1800d9abf  xor     rcx, rsp; StackCookie
0x1800d9ac2  call    __security_check_cookie
0x1800d9ac7  add     rsp, 120h
0x1800d9ace  pop     r15
0x1800d9ad0  pop     r14
0x1800d9ad2  pop     r13
0x1800d9ad4  pop     r12
0x1800d9ad6  pop     rdi
0x1800d9ad7  pop     rsi
0x1800d9ad8  pop     rbx
0x1800d9ad9  retn
0x1800d9ada  xor     edx, edx; Val
0x1800d9adc  mov     r8d, 80h; Size
0x1800d9ae2  lea     rcx, [rsp+158h+ClassName]; void *
0x1800d9aea  call    memset_0
0x1800d9aef  mov     r8d, 40h ; '@'; nMaxCount
0x1800d9af5  lea     rdx, [rsp+158h+ClassName]; lpClassName
0x1800d9afd  mov     rcx, [rdi+18h]; hWnd
0x1800d9b01  call    cs:__imp_GetClassNameW
0x1800d9b07  test    eax, eax
0x1800d9b09  jz      short loc_1800D9B28
0x1800d9b0b  lea     rdx, aConsolewindowc; "ConsoleWindowClass"
0x1800d9b12  lea     rcx, [rsp+158h+ClassName]; lpString1
0x1800d9b1a  call    cs:__imp_lstrcmpiW
0x1800d9b20  test    eax, eax
0x1800d9b22  jz      loc_1800D9F06
0x1800d9b28  mov     rsi, [rbx+18h]
0x1800d9b2c  test    rsi, rsi
0x1800d9b2f  jnz     short loc_1800D9B4F
0x1800d9b31  mov     rcx, [rbx+8]
0x1800d9b35  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800d9b39  test    byte ptr [rbx+8], 1
0x1800d9b3d  jnz     loc_1800D9FE0
0x1800d9b43  call    ??$CreateMaybeMessage@VElementCompletionInfoMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementCompletionInfoMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementCompletionInfoMsg,>(google::protobuf::Arena *)
0x1800d9b48  mov     rsi, rax
0x1800d9b4b  mov     [rbx+18h], rax
0x1800d9b4f  lea     r8, qword_180311AB8
0x1800d9b56  lea     rdx, [rsp+158h+var_D8]
0x1800d9b5e  mov     rcx, rdi
0x1800d9b61  call    ?TryGetInProcNativeUiaNode@ProviderEntryPoint@@QEAA?AV?$com_ptr_t@VUiaNode@@Uerr_exception_policy@wil@@@wil@@AEBUUIA_TIMEOUTDATA@@@Z; ProviderEntryPoint::TryGetInProcNativeUiaNode(UIA_TIMEOUTDATA const &)
0x1800d9b66  nop
0x1800d9b67  mov     rax, [rsp+158h+var_D8]
0x1800d9b6f  test    rax, rax
0x1800d9b72  jnz     loc_1800D9C22
0x1800d9b78  mov     bl, r13b
0x1800d9b7b  cmp     [rdi+28h], r13d
0x1800d9b7f  jnz     loc_1800D9C96
0x1800d9b85  mov     rax, [rdi+18h]
0x1800d9b89  mov     qword ptr [rsp+158h+dwProcessId], rax
0x1800d9b8e  lea     rdx, [rsp+158h+dwProcessId]
0x1800d9b93  lea     rcx, [rsp+158h+var_128]
0x1800d9b98  call    ??$MakeCom@VHwndInvoker@@PEAUHWND__@@@@YA?AV?$com_ptr_t@VHwndInvoker@@Uerr_exception_policy@wil@@@wil@@$$QEAPEAUHWND__@@@Z; MakeCom<HwndInvoker,HWND__ *>(HWND__ * &&)
0x1800d9b9d  nop
0x1800d9b9e  xor     eax, eax
0x1800d9ba0  mov     dword ptr [rsp+158h+var_F8+1], eax
0x1800d9ba4  mov     word ptr [rsp+158h+var_F8+5], ax
0x1800d9ba9  mov     byte ptr [rsp+158h+var_F8+7], al
0x1800d9bad  mov     qword ptr [rsp+158h+var_118], rsi
0x1800d9bb2  mov     qword ptr [rsp+158h+var_118+8], r12
0x1800d9bb7  mov     rax, cs:qword_180311AB8
0x1800d9bbe  mov     qword ptr [rsp+158h+var_108], rax
0x1800d9bc3  cmp     [rdi+28h], r13d
0x1800d9bc7  jnz     loc_1800D9C9E
0x1800d9bcd  mov     rax, [rdi+18h]
0x1800d9bd1  mov     qword ptr [rsp+158h+var_108+8], rax
0x1800d9bd6  mov     byte ptr [rsp+158h+var_F8], bl
0x1800d9bda  mov     rcx, qword ptr [rsp+158h+var_128]
0x1800d9bdf  mov     rax, [rcx]
0x1800d9be2  mov     r9d, 1F4h
0x1800d9be8  lea     r8, [rsp+158h+var_118]
0x1800d9bed  lea     rdx, _anonymous_namespace___WriteEntryPointProxyProvidersInCorrectContext
0x1800d9bf4  mov     rax, [rax+18h]
0x1800d9bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bfd  mov     rcx, [rsp+158h]; this
0x1800d9c05  test    eax, eax
0x1800d9c07  jns     loc_1800D9CA6
0x1800d9c0d  mov     r9d, eax; char *
0x1800d9c10  lea     r8, aOnecoreWindows_131; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d9c17  mov     edx, 51Ah; void *
0x1800d9c1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d9c22  mov     rcx, [rax+108h]
0x1800d9c29  mov     byte ptr [rsp+158h+var_108+8], r13b
0x1800d9c2e  xor     edx, edx
0x1800d9c30  mov     dword ptr [rsp+158h+var_108+9], edx
0x1800d9c34  mov     word ptr [rsp+158h+var_108+0Dh], dx
0x1800d9c39  mov     byte ptr [rsp+158h+var_108+0Fh], dl
0x1800d9c3d  mov     qword ptr [rsp+158h+var_118], rsi
0x1800d9c42  mov     qword ptr [rsp+158h+var_118+8], r12
0x1800d9c47  mov     [rsp+158h+var_D8], r13
0x1800d9c4f  mov     qword ptr [rsp+158h+var_108], rax
0x1800d9c54  mov     rax, [rcx]
0x1800d9c57  mov     r9d, 1F4h
0x1800d9c5d  lea     r8, [rsp+158h+var_118]
0x1800d9c62  lea     rdx, _anonymous_namespace___WriteEntryPointNativeProviderInCorrectContext
0x1800d9c69  mov     rax, [rax+18h]
0x1800d9c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9c72  mov     rcx, [rsp+158h]; this
0x1800d9c7a  test    eax, eax
0x1800d9c7c  jns     loc_1800D9EFD
0x1800d9c82  mov     r9d, eax; char *
0x1800d9c85  lea     r8, aOnecoreWindows_131; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d9c8c  mov     edx, 4FCh; void *
0x1800d9c91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d9c96  mov     rax, r13
0x1800d9c99  jmp     loc_1800D9B89
0x1800d9c9e  mov     rax, r13
0x1800d9ca1  jmp     loc_1800D9BD1
0x1800d9ca6  mov     rcx, qword ptr [rsp+158h+var_128]
0x1800d9cab  test    rcx, rcx
0x1800d9cae  jz      short loc_1800D9CBD
0x1800d9cb0  mov     rax, [rcx]
0x1800d9cb3  mov     rax, [rax+10h]
0x1800d9cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9cbc  nop
0x1800d9cbd  cmp     [rdi+28h], r13d
0x1800d9cc1  jnz     loc_1800D9EE4
0x1800d9cc7  mov     rbx, [rdi+18h]
0x1800d9ccb  mov     edx, 1; gaFlags
0x1800d9cd0  mov     rcx, rbx; hwnd
0x1800d9cd3  call    cs:__imp_GetAncestor
0x1800d9cd9  mov     r14, rax
0x1800d9cdc  test    rax, rax
0x1800d9cdf  jz      loc_1800D9EF5
0x1800d9ce5  mov     [rsp+158h+dwProcessId], r13d
0x1800d9cea  mov     edx, cs:_tls_index
0x1800d9cf0  mov     rcx, gs:58h
0x1800d9cf9  mov     eax, 58h ; 'X'
0x1800d9cfe  mov     r15, [rcx+rdx*8]
0x1800d9d02  mov     ecx, [r15+rax]
0x1800d9d06  cmp     cs:dword_1803A34B0, ecx
0x1800d9d0c  jg      loc_1800DA03E
0x1800d9d12  mov     rax, cs:qword_1803A34B8
0x1800d9d19  mov     rcx, rbx; hWnd
0x1800d9d1c  test    rax, rax
0x1800d9d1f  jz      loc_1800D9FE8
0x1800d9d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9d2a  mov     ebx, eax
0x1800d9d2c  mov     [rsp+158h+dwProcessId], eax
0x1800d9d30  mov     [rsp+158h+var_128], r13d
0x1800d9d35  mov     eax, 58h ; 'X'
0x1800d9d3a  mov     eax, [r15+rax]
0x1800d9d3e  cmp     cs:dword_1803A34B0, eax
0x1800d9d44  jg      loc_1800DA079
0x1800d9d4a  mov     rax, cs:qword_1803A34B8
0x1800d9d51  mov     rcx, r14; hWnd
0x1800d9d54  test    rax, rax
0x1800d9d57  jz      loc_1800D9FFC
0x1800d9d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9d62  mov     [rsp+158h+var_128], eax
0x1800d9d66  cmp     ebx, eax
0x1800d9d68  jnz     loc_1800D9EF1
0x1800d9d6e  mov     qword ptr [rsp+158h+var_128], r13
0x1800d9d73  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d9d7a  mov     ecx, 160h; unsigned __int64
0x1800d9d7f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d9d84  mov     rbx, rax
0x1800d9d87  test    rax, rax
0x1800d9d8a  jz      loc_1800DA010
0x1800d9d90  mov     [rsp+158h+var_88], r13b
0x1800d9d98  lea     rax, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x1800d9d9f  mov     [rbx+8], rax
0x1800d9da3  mov     dword ptr [rbx+10h], 1
0x1800d9daa  lock inc cs:dword_18039DE7C
0x1800d9db1  lea     rax, ??_7ProviderEntryPoint@@6BIUnknown@@@; const ProviderEntryPoint::`vftable'{for `IUnknown'}
0x1800d9db8  mov     [rbx], rax
0x1800d9dbb  lea     rax, ??_7ProviderEntryPoint@@6BRefcountBase@@@; const ProviderEntryPoint::`vftable'{for `RefcountBase'}
0x1800d9dc2  mov     [rbx+8], rax
0x1800d9dc6  xorps   xmm0, xmm0
0x1800d9dc9  movups  xmmword ptr [rbx+18h], xmm0
0x1800d9dcd  mov     [rbx+28h], r13d
0x1800d9dd1  movups  xmm0, [rsp+158h+var_118]
0x1800d9dd6  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x1800d9ddb  mov     [rbx+3Ch], r13b
0x1800d9ddf  movzx   eax, word ptr [rsp+158h+var_108+1]
0x1800d9de4  mov     [rbx+3Dh], ax
0x1800d9de8  mov     al, byte ptr [rsp+158h+var_108+3]
0x1800d9dec  mov     [rbx+3Fh], al
0x1800d9def  mov     [rbx+40h], r13
0x1800d9df3  mov     [rbx+0D8h], r13b
0x1800d9dfa  mov     [rbx+0E4h], r13b
0x1800d9e01  lea     rcx, [rbx+0E8h]
0x1800d9e08  mov     [rcx+20h], r13b
0x1800d9e0c  lea     r15, [rbx+110h]
0x1800d9e13  mov     [r15+20h], r13b
0x1800d9e17  mov     [rbx+158h], r13b
0x1800d9e1e  cmp     [rsp+158h+var_88], r13b
0x1800d9e26  jnz     loc_1800D9F0B
0x1800d9e2c  mov     [rbx+28h], r13d
0x1800d9e30  mov     [rbx+18h], r14
0x1800d9e34  mov     [rbx+40h], r13
0x1800d9e38  lea     r8, qword_180311AB8
0x1800d9e3f  lea     rdx, [rsp+158h+var_128]
0x1800d9e44  mov     rcx, rbx
0x1800d9e47  call    ?TryGetInProcNativeUiaNode@ProviderEntryPoint@@QEAA?AV?$com_ptr_t@VUiaNode@@Uerr_exception_policy@wil@@@wil@@AEBUUIA_TIMEOUTDATA@@@Z; ProviderEntryPoint::TryGetInProcNativeUiaNode(UIA_TIMEOUTDATA const &)
0x1800d9e4c  nop
0x1800d9e4d  mov     rax, [rbx]
0x1800d9e50  mov     rcx, rbx
0x1800d9e53  mov     rax, [rax+10h]
0x1800d9e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9e5c  nop
0x1800d9e5d  mov     rcx, qword ptr [rsp+158h+var_128]
0x1800d9e62  test    rcx, rcx
0x1800d9e65  jz      short loc_1800D9EDF
0x1800d9e67  mov     r10, [rcx+108h]
0x1800d9e6e  mov     qword ptr [rsp+158h+var_118], rsi
0x1800d9e73  mov     qword ptr [rsp+158h+var_118+8], r12
0x1800d9e78  mov     rax, cs:qword_180311AB8
0x1800d9e7f  mov     qword ptr [rsp+158h+var_108], rax
0x1800d9e84  mov     qword ptr [rsp+158h+var_128], r13
0x1800d9e89  mov     qword ptr [rsp+158h+var_108+8], rcx
0x1800d9e8e  cmp     [rdi+28h], r13d
0x1800d9e92  jnz     short loc_1800D9EEC
0x1800d9e94  mov     rax, [rdi+18h]
0x1800d9e98  mov     qword ptr [rsp+158h+var_F8], rax
0x1800d9e9d  mov     rax, [r10]
0x1800d9ea0  mov     r9d, 1F4h
0x1800d9ea6  lea     r8, [rsp+158h+var_118]
0x1800d9eab  lea     rdx, _anonymous_namespace___WriteParentHwndOverrideProviderInCorrectContext
0x1800d9eb2  mov     rcx, r10
0x1800d9eb5  mov     rax, [rax+18h]
0x1800d9eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ebe  mov     rcx, [rsp+158h]; this
0x1800d9ec6  test    eax, eax
0x1800d9ec8  jns     short loc_1800D9EDF
0x1800d9eca  mov     r9d, eax; char *
0x1800d9ecd  lea     r8, aOnecoreWindows_131; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d9ed4  mov     edx, 53Fh; void *
0x1800d9ed9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d9edf  jmp     loc_1800D9AB7
0x1800d9ee4  mov     rbx, r13
0x1800d9ee7  jmp     loc_1800D9CCB
0x1800d9eec  mov     rax, r13
0x1800d9eef  jmp     short loc_1800D9E98
0x1800d9ef1  mov     byte ptr [rsi+30h], 1
0x1800d9ef5  mov     rcx, r13
0x1800d9ef8  jmp     loc_1800D9E62
0x1800d9efd  mov     bl, byte ptr [rsp+158h+var_108+8]
0x1800d9f01  jmp     loc_1800D9B7B
0x1800d9f06  jmp     loc_1800D9AB7
0x1800d9f0b  movzx   eax, [rsp+158h+ClassName]
0x1800d9f13  mov     word ptr [rsp+158h+var_118], ax
0x1800d9f18  movsd   xmm0, [rsp+158h+var_C6]
0x1800d9f21  movsd   qword ptr [rsp+158h+var_118+2], xmm0
0x1800d9f27  mov     eax, [rsp+158h+var_BE]
0x1800d9f2e  mov     dword ptr [rsp+158h+var_118+0Ah], eax
0x1800d9f32  movzx   eax, [rsp+158h+var_BA]
0x1800d9f3a  mov     word ptr [rsp+158h+var_118+0Eh], ax
0x1800d9f3f  mov     rax, qword ptr [rsp+158h+var_B8]
0x1800d9f47  mov     qword ptr [rsp+158h+var_108], rax
0x1800d9f4c  mov     rax, qword ptr [rsp+158h+var_B8+8]
0x1800d9f54  mov     qword ptr [rsp+158h+var_108+8], rax
0x1800d9f59  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x1800d9f61  movdqu  [rsp+158h+var_B8], xmm2
0x1800d9f6a  mov     [rsp+158h+ClassName], r13w
0x1800d9f73  movups  xmm1, [rsp+158h+var_A8]
0x1800d9f7b  movups  [rsp+158h+var_F8], xmm1
0x1800d9f80  movups  xmm0, [rsp+158h+var_98]
0x1800d9f88  movups  [rsp+158h+var_E8], xmm0
0x1800d9f8d  movdqu  [rsp+158h+var_98], xmm2
0x1800d9f96  mov     word ptr [rsp+158h+var_A8], r13w
0x1800d9f9f  lea     rdx, [rsp+158h+var_118]
0x1800d9fa4  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x1800d9fa9  lea     rdx, [rsp+158h+var_F8]
0x1800d9fae  mov     rcx, r15
0x1800d9fb1  call    ??$?4V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::optional<std::wstring>::operator=<std::wstring,0>(std::wstring &&)
0x1800d9fb6  lea     rcx, [rsp+158h+var_118]; this
0x1800d9fbb  call    ??1AppContainerInfo@@QEAA@XZ; AppContainerInfo::~AppContainerInfo(void)
0x1800d9fc0  cmp     [rsp+158h+var_88], r13b
0x1800d9fc8  jz      loc_1800D9E2C
0x1800d9fce  lea     rcx, [rsp+158h+ClassName]; this
0x1800d9fd6  call    ??1AppContainerInfo@@QEAA@XZ; AppContainerInfo::~AppContainerInfo(void)
0x1800d9fdb  jmp     loc_1800D9E2C
0x1800d9fe0  mov     rcx, [rcx]
0x1800d9fe3  jmp     loc_1800D9B43
0x1800d9fe8  lea     rdx, [rsp+158h+dwProcessId]; lpdwProcessId
0x1800d9fed  call    cs:__imp_GetWindowThreadProcessId
0x1800d9ff3  mov     ebx, [rsp+158h+dwProcessId]
0x1800d9ff7  jmp     loc_1800D9D30
0x1800d9ffc  lea     rdx, [rsp+158h+var_128]; lpdwProcessId
0x1800da001  call    cs:__imp_GetWindowThreadProcessId
0x1800da007  mov     eax, [rsp+158h+var_128]
  ... truncated ...
```
