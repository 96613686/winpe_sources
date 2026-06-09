# _anonymous_namespace_::InstallHook

- ea: `0x1800573f8`
- end: `0x1800576ae`
- name: `_anonymous_namespace_::InstallHook`
- size: `694`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180056bf0`
- `0x180057228`

## callees

- `0x18000f680`
- `0x18001c498`
- `0x180032724`
- `0x1800573f8`
- `0x1800dbd88`
- `0x18013afc8`
- `0x1801a5e30`
- `0x1801e8a1c`
- `0x1801e8a84`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180057493`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180057493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057683`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800576a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057683`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800576a3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180057449`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800574a1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180057449`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800574a1`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x18005746f`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x1800574c7`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x18005746f`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x1800574c7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x180057431`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x180057431`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowsHookExW` at `0x18005753c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowsHookExW` at `0x18005753c`

## string_xrefs

- `0x18005756d`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1800575f3`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x180057658`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18005766e`: `onecore\windows\accessibletech\uiautomationcore\crossarchitecturehelpers.cpp`
- `0x18005768e`: `onecore\windows\accessibletech\uiautomationcore\crossarchitecturehelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::InstallHook(__int64 a1, HWND a2, __int64 a3)
{
  HINSTANCE v4; // r12
  DWORD WindowThreadProcessId; // r15d
  char *v6; // rbx
  const char *v7; // r9
  unsigned __int16 v8; // si
  DWORD CurrentProcessId; // eax
  char *v10; // rbx
  const char *v11; // r9
  __int16 v12; // r14
  HHOOK v13; // rbx
  signed int LastError; // eax
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-20h]
  char *v20; // [rsp+28h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD dwProcessId; // [rsp+80h] [rbp+40h] BYREF
  int v24; // [rsp+84h] [rbp+44h]
  HHOOK v25; // [rsp+88h] [rbp+48h] BYREF

  v24 = HIDWORD(a3);
  v4 = hmod;
  dwProcessId = 0;
  WindowThreadProcessId = GetWindowThreadProcessId(a2, &dwProcessId);
  v6 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
  v20 = v6;
  v25 = 0;
  if ( !(unsigned int)GetProcessInformation(v6, 9, &v25) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\crossarchitecturehelpers.cpp",
      v7);
  v8 = (unsigned __int16)v25;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  CurrentProcessId = GetCurrentProcessId();
  v10 = (char *)OpenProcess(0x1000u, 0, CurrentProcessId);
  v20 = v10;
  v25 = 0;
  if ( !(unsigned int)GetProcessInformation(v10, 9, &v25) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\crossarchitecturehelpers.cpp",
      v11);
  v12 = (__int16)v25;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  if ( v12 == v8 )
  {
    if ( dword_1803A34A0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 88LL) )
    {
      Init_thread_header(&dword_1803A34A0);
      if ( dword_1803A34A0 == -1 )
      {
        byte_1803A34A4 = lambda_0c853f2099bf0b62b17a3d3ad9be57f2_::operator()();
        Init_thread_footer(&dword_1803A34A0);
      }
    }
    if ( !byte_1803A34A4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93B,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)0x80004005LL,
        v19);
    v13 = SetWindowsHookExW(4, HookMessageWndProc, v4, WindowThreadProcessId);
    v25 = v13;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( !v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x943,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)(unsigned int)LastError,
        v19);
    *(_QWORD *)a1 = v13;
    *(_BYTE *)(a1 + 16) = 0;
  }
  else
  {
    v16 = anonymous_namespace_::InstallCrossBitnessHook(&v20, WindowThreadProcessId, v8);
    v17 = *(_QWORD *)v16;
    *(_QWORD *)v16 = 0;
    *(_QWORD *)a1 = v17;
    *(_DWORD *)(a1 + 8) = *(_DWORD *)(v16 + 8);
    *(_BYTE *)(a1 + 16) = 1;
    if ( v20 )
    {
      v18 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v20 + 32LL))(v20, v21);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8F4,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
          (const char *)(unsigned int)v18,
          v19);
    }
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v20);
  }
  return a1;
}

```

## disassembly

```asm
0x1800573f8  mov     [rsp-28h+arg_0], rbx
0x1800573fd  mov     [rsp-28h+arg_8], rsi
0x180057402  mov     qword ptr [rsp-28h+dwProcessId], r8
0x180057407  push    rbp
0x180057408  push    rdi
0x180057409  push    r12
0x18005740b  push    r14
0x18005740d  push    r15
0x18005740f  mov     rbp, rsp
0x180057412  sub     rsp, 40h
0x180057416  mov     rax, rdx
0x180057419  mov     rdi, rcx
0x18005741c  mov     r12, cs:hmod
0x180057423  mov     [rbp+dwProcessId], 0
0x18005742a  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18005742e  mov     rcx, rax; hWnd
0x180057431  call    cs:__imp_GetWindowThreadProcessId
0x180057437  mov     r15d, eax
0x18005743a  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18005743e  xor     edx, edx; bInheritHandle
0x180057440  mov     r14d, 1000h
0x180057446  mov     ecx, r14d; dwDesiredAccess
0x180057449  call    cs:__imp_OpenProcess
0x18005744f  mov     rbx, rax
0x180057452  mov     [rbp+var_18], rax
0x180057456  mov     [rbp+arg_18], 0
0x18005745e  mov     r9d, 8
0x180057464  lea     r8, [rbp+arg_18]
0x180057468  lea     edx, [r9+1]
0x18005746c  mov     rcx, rax
0x18005746f  call    cs:__imp_GetProcessInformation
0x180057475  mov     rcx, [rbp+28h]; this
0x180057479  test    eax, eax
0x18005747b  jz      loc_18005766E
0x180057481  movzx   esi, word ptr [rbp+arg_18]
0x180057485  lea     rax, [rbx-1]
0x180057489  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005748d  jbe     loc_180057680
0x180057493  call    cs:__imp_GetCurrentProcessId
0x180057499  mov     r8d, eax; dwProcessId
0x18005749c  xor     edx, edx; bInheritHandle
0x18005749e  mov     ecx, r14d; dwDesiredAccess
0x1800574a1  call    cs:__imp_OpenProcess
0x1800574a7  mov     rbx, rax
0x1800574aa  mov     [rbp+var_18], rax
0x1800574ae  mov     [rbp+arg_18], 0
0x1800574b6  mov     r9d, 8
0x1800574bc  lea     r8, [rbp+arg_18]
0x1800574c0  lea     edx, [r9+1]
0x1800574c4  mov     rcx, rax
0x1800574c7  call    cs:__imp_GetProcessInformation
0x1800574cd  mov     rcx, [rbp+28h]; this
0x1800574d1  test    eax, eax
0x1800574d3  jz      loc_18005768E
0x1800574d9  movzx   r14d, word ptr [rbp+arg_18]
0x1800574de  lea     rax, [rbx-1]
0x1800574e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800574e6  jbe     loc_1800576A0
0x1800574ec  cmp     r14w, si
0x1800574f0  jnz     loc_1800575A0
0x1800574f6  mov     ecx, cs:_tls_index
0x1800574fc  mov     rax, gs:58h
0x180057505  mov     edx, 58h ; 'X'
0x18005750a  mov     rax, [rax+rcx*8]
0x18005750e  mov     eax, [rdx+rax]
0x180057511  cmp     cs:dword_1803A34A0, eax
0x180057517  jg      loc_180057605
0x18005751d  cmp     cs:byte_1803A34A4, 0
0x180057524  jz      loc_1800575E9
0x18005752a  mov     r9d, r15d; dwThreadId
0x18005752d  mov     r8, r12; hmod
0x180057530  lea     rdx, HookMessageWndProc; lpfn
0x180057537  mov     ecx, 4; idHook
0x18005753c  call    cs:__imp_SetWindowsHookExW
0x180057542  mov     rbx, rax
0x180057545  mov     [rbp+arg_18], rax
0x180057549  call    cs:__imp_GetLastError
0x18005754f  test    eax, eax
0x180057551  jg      loc_1800575DC
0x180057557  mov     edx, 80004005h
0x18005755c  test    eax, eax
0x18005755e  cmovns  eax, edx
0x180057561  mov     rcx, [rbp+28h]; this
0x180057565  test    rbx, rbx
0x180057568  jnz     short loc_18005757F
0x18005756a  mov     r9d, eax; char *
0x18005756d  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x180057574  mov     edx, 943h; void *
0x180057579  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005757f  mov     [rdi], rbx
0x180057582  mov     byte ptr [rdi+10h], 0
0x180057586  mov     rax, rdi
0x180057589  mov     rbx, [rsp+40h+arg_0]
0x18005758e  mov     rsi, [rsp+40h+arg_8]
0x180057593  add     rsp, 40h
0x180057597  pop     r15
0x180057599  pop     r14
0x18005759b  pop     r12
0x18005759d  pop     rdi
0x18005759e  pop     rbp
0x18005759f  retn
0x1800575a0  movzx   r8d, si
0x1800575a4  mov     edx, r15d
0x1800575a7  lea     rcx, [rbp+var_18]
0x1800575ab  call    _anonymous_namespace___InstallCrossBitnessHook
0x1800575b0  mov     rcx, [rax]
0x1800575b3  mov     qword ptr [rax], 0
0x1800575ba  mov     [rdi], rcx
0x1800575bd  mov     eax, [rax+8]
0x1800575c0  mov     [rdi+8], eax
0x1800575c3  mov     byte ptr [rdi+10h], 1
0x1800575c7  mov     rcx, [rbp+var_18]
0x1800575cb  test    rcx, rcx
0x1800575ce  jnz     short loc_18005763A
0x1800575d0  lea     rcx, [rbp+var_18]; void *
0x1800575d4  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x1800575d9  nop
0x1800575da  jmp     short loc_180057586
0x1800575dc  movzx   eax, ax
0x1800575df  or      eax, 80070000h
0x1800575e4  jmp     loc_180057557
0x1800575e9  mov     rcx, [rbp+28h]; this
0x1800575ed  mov     r9d, 80004005h; char *
0x1800575f3  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x1800575fa  mov     edx, 93Bh; void *
0x1800575ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057605  lea     rcx, dword_1803A34A0
0x18005760c  call    _Init_thread_header
0x180057611  cmp     cs:dword_1803A34A0, 0FFFFFFFFh
0x180057618  jnz     loc_18005751D
0x18005761e  call    _lambda_0c853f2099bf0b62b17a3d3ad9be57f2___operator__
0x180057623  mov     cs:byte_1803A34A4, al
0x180057629  lea     rcx, dword_1803A34A0
0x180057630  call    _Init_thread_footer
0x180057635  jmp     loc_18005751D
0x18005763a  mov     rax, [rcx]
0x18005763d  mov     edx, [rbp+var_10]
0x180057640  mov     rax, [rax+20h]
0x180057644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057649  mov     rcx, [rbp+28h]; this
0x18005764d  test    eax, eax
0x18005764f  jns     loc_1800575D0
0x180057655  mov     r9d, eax; char *
0x180057658  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x18005765f  mov     edx, 8F4h; void *
0x180057664  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057669  jmp     loc_1800575D0
0x18005766e  lea     r8, aOnecoreWindows_55; "onecore\\windows\\accessibletech\\uiaut"...
0x180057675  mov     edx, 22h ; '"'; void *
0x18005767a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180057680  mov     rcx, rbx; hObject
0x180057683  call    cs:__imp_CloseHandle
0x180057689  jmp     loc_180057493
0x18005768e  lea     r8, aOnecoreWindows_55; "onecore\\windows\\accessibletech\\uiaut"...
0x180057695  mov     edx, 22h ; '"'; void *
0x18005769a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800576a0  mov     rcx, rbx; hObject
0x1800576a3  call    cs:__imp_CloseHandle
0x1800576a9  jmp     loc_1800574EC
```
