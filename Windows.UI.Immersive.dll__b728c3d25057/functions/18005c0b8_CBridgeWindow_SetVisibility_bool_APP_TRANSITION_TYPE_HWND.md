# CBridgeWindow::_SetVisibility(bool,APP_TRANSITION_TYPE,HWND__ *)

- ea: `0x18005c0b8`
- end: `0x18005c38d`
- name: `?_SetVisibility@CBridgeWindow@@AEAAX_NW4APP_TRANSITION_TYPE@@PEAUHWND__@@@Z`
- size: `725`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a180`
- `0x18005be40`

## callees

- `0x180017960`
- `0x180022700`
- `0x180026658`
- `0x18002b320`
- `0x180059938`
- `0x18005b474`
- `0x18005b624`
- `0x18005bdbc`
- `0x18005bf04`
- `0x18005c000`
- `0x18005c0b8`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18005c2d4`
- `USER32!SystemParametersInfoW` at `0x18005c2d4`
- `USER32!SendMessageW` at `0x18005c254`
- `USER32!SendMessageW` at `0x18005c254`
- `USER32!PostMessageW` at `0x18005c367`
- `USER32!PostMessageW` at `0x18005c367`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x18005c103`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x18005c103`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18005c221`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18005c23a`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18005c221`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18005c23a`
- `dwmapi!__imp_DwmpEndTransitionRequest` at `0x18005c27f`
- `dwmapi!__imp_DwmpEndTransitionRequest` at `0x18005c27f`
- `dwmapi!__imp_DwmpBeginTransitionRequestWithGUID` at `0x18005c1b0`
- `dwmapi!__imp_DwmpBeginTransitionRequestWithGUID` at `0x18005c1b0`

## pseudocode

```c
void __fastcall CBridgeWindow::_SetVisibility(__int64 a1, unsigned __int8 a2, int a3, HWND a4)
{
  char v4; // r13
  int v5; // r14d
  char v9; // di
  HWND v10; // r8
  char v11; // al
  unsigned int v12; // esi
  __int64 *v13; // rdx
  int v14; // ebp
  int v15; // ecx
  char v16; // al
  int v17; // edx
  char v18; // r12
  int v19; // r15d
  bool v20; // r15
  HWND v21; // rcx
  _BYTE v22[88]; // [rsp+20h] [rbp-58h] BYREF
  int pvParam; // [rsp+80h] [rbp+8h] BYREF
  char v24; // [rsp+88h] [rbp+10h]
  int v25; // [rsp+90h] [rbp+18h]
  HDESK v26; // [rsp+98h] [rbp+20h] BYREF

  v25 = a3;
  v4 = 0;
  v5 = a2;
  v9 = 1;
  if ( *(_QWORD *)(a1 + 240) )
  {
    wil::AcquireSRWLockExclusive(v22, &g_desktopSwitchLock);
    v26 = OpenInputDesktop(0, 0, 1u);
    g_trackedDesktopStateEverEnteredSecureDesktop = v26 == 0;
    wil::details::unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&int CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&int CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>(&v26);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v22);
  }
  if ( (_BYTE)v5 )
  {
    if ( (int)_SetOwnerWindow(*(HWND *)(a1 + 112), *(HWND *)(a1 + 176)) >= 0 )
    {
      v10 = *(HWND *)(a1 + 192);
      if ( v10 )
      {
        if ( *(_BYTE *)(a1 + 147) )
          CBridgeWindow::_AttachOrDetachInputQueues((CBridgeWindow *)a1, 1, v10, 0);
      }
    }
  }
  if ( *(_BYTE *)(a1 + 142) || (v11 = 1, a3) )
    v11 = 0;
  v24 = v11;
  if ( a4 )
  {
    v12 = 75;
    v13 = qword_180101A90;
  }
  else
  {
    v13 = 0;
    v12 = (v5 ^ 1) + 4;
  }
  if ( v11 )
  {
    v14 = DwmpBeginTransitionRequestWithGUID(v12, v13);
    if ( v14 >= 0 )
    {
      switch ( v12 )
      {
        case 4u:
          v15 = 25;
          break;
        case 5u:
          v15 = 26;
          break;
        case 0x4Bu:
          v15 = v5 + 18;
          break;
        default:
          v15 = 4095;
          break;
      }
      *(_BYTE *)(a1 + 144) = v5 ^ 1;
      if ( !(_BYTE)v5 || (v16 = 1, v12 != 4) )
        v16 = 0;
      *(_BYTE *)(a1 + 145) = v16;
      v17 = 272760832;
      if ( v15 != 25 )
        v17 = 272629760;
      v14 = DwmpTransitionWindow(*(_QWORD *)(a1 + 112), v15 | (unsigned int)v17);
      if ( v14 >= 0 )
      {
        if ( a4 )
        {
          v14 = DwmpTransitionWindow(a4, 272629778);
          if ( v14 >= 0 )
            SendMessageW(a4, 0x404u, 0, 0);
        }
      }
    }
  }
  else
  {
    v14 = -2147467259;
  }
  v18 = v5 ^ 1;
  v19 = CBridgeWindow::_CloakWindow((CBridgeWindow *)a1, (unsigned __int8)v5 ^ 1u);
  if ( v14 >= 0 )
    DwmpEndTransitionRequest(v12);
  if ( !(_BYTE)v5 && (v24 && v14 < 0 || v25 == 1 || v19 < 0) )
  {
    *(_BYTE *)(a1 + 144) = 0;
    v4 = 1;
    CBridgeWindow::_RemoveOwner((CBridgeWindow *)a1, v19);
  }
  pvParam = 1;
  SystemParametersInfoW(0x1042u, 0, &pvParam, 0);
  if ( *(_QWORD *)(a1 + 240) )
  {
    Microsoft::WRL::Wrappers::SRWLock::LockShared(&v26, &g_desktopSwitchLock);
    v20 = g_trackedDesktopStateEverEnteredSecureDesktop;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v26);
  }
  else
  {
    v20 = 0;
  }
  if ( v24 && (!pvParam && v14 < 0 || v20) )
  {
    if ( v4 )
      v18 = *(_BYTE *)(a1 + 144);
    *(_BYTE *)(a1 + 144) = v18;
    if ( !(_BYTE)v5 || v12 != 4 )
      v9 = 0;
    v21 = *(HWND *)(a1 + 112);
    *(_BYTE *)(a1 + 145) = v9;
    PostMessageW(v21, 0x32Au, 0, 2);
  }
  *(_BYTE *)(a1 + 142) = 0;
  CBridgeWindow::_MaybeNotifySplashScreenDismissed((CBridgeWindow *)a1);
}

```

## disassembly

```asm
0x18005c0b8  mov     [rsp+arg_10], r8d
0x18005c0bd  push    rbx
0x18005c0be  push    rbp
0x18005c0bf  push    rsi
0x18005c0c0  push    rdi
0x18005c0c1  push    r12
0x18005c0c3  push    r13
0x18005c0c5  push    r14
0x18005c0c7  push    r15
0x18005c0c9  sub     rsp, 38h
0x18005c0cd  xor     r13d, r13d
0x18005c0d0  movzx   r14d, dl
0x18005c0d4  mov     r15, r9
0x18005c0d7  mov     esi, r8d
0x18005c0da  mov     rbx, rcx
0x18005c0dd  mov     edi, 1
0x18005c0e2  cmp     [rcx+0F0h], r13
0x18005c0e9  jz      short loc_18005C132
0x18005c0eb  lea     rdx, ?g_desktopSwitchLock@@3Vsrwlock@wil@@A; wil::srwlock g_desktopSwitchLock
0x18005c0f2  lea     rcx, [rsp+78h+var_58]
0x18005c0f7  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18005c0fc  mov     r8d, edi; dwDesiredAccess
0x18005c0ff  xor     edx, edx; fInherit
0x18005c101  xor     ecx, ecx; dwFlags
0x18005c103  call    cs:__imp_OpenInputDesktop
0x18005c109  test    rax, rax
0x18005c10c  mov     [rsp+78h+arg_18], rax
0x18005c114  lea     rcx, [rsp+78h+arg_18]
0x18005c11c  setz    cs:?g_trackedDesktopStateEverEnteredSecureDesktop@@3_NA; bool g_trackedDesktopStateEverEnteredSecureDesktop
0x18005c123  call    ??1?$unique_storage@U?$resource_policy@PEAUHDESK__@@P6AHPEAU1@@Z$1?CloseDesktop@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDESK__ *,int (*)(HDESK__ *),&CloseDesktop(HDESK__ *),wistd::integral_constant<unsigned __int64,0>,HDESK__ *,HDESK__ *,0,std::nullptr_t>>(void)
0x18005c128  lea     rcx, [rsp+78h+var_58]
0x18005c12d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005c132  test    r14b, r14b
0x18005c135  jz      short loc_18005C16E
0x18005c137  mov     rdx, [rbx+0B0h]; hWnd
0x18005c13e  mov     rcx, [rbx+70h]; hWndInsertAfter
0x18005c142  call    ?_SetOwnerWindow@@YAJPEAUHWND__@@0@Z; _SetOwnerWindow(HWND__ *,HWND__ *)
0x18005c147  test    eax, eax
0x18005c149  js      short loc_18005C16E
0x18005c14b  mov     r8, [rbx+0C0h]; HWND
0x18005c152  test    r8, r8
0x18005c155  jz      short loc_18005C16E
0x18005c157  cmp     [rbx+93h], r13b
0x18005c15e  jz      short loc_18005C16E
0x18005c160  xor     r9d, r9d; bool
0x18005c163  mov     dl, dil; bool
0x18005c166  mov     rcx, rbx; this
0x18005c169  call    ?_AttachOrDetachInputQueues@CBridgeWindow@@AEAAJ_NPEAUHWND__@@0@Z; CBridgeWindow::_AttachOrDetachInputQueues(bool,HWND__ *,bool)
0x18005c16e  cmp     [rbx+8Eh], r13b
0x18005c175  jnz     short loc_18005C17E
0x18005c177  mov     al, dil
0x18005c17a  test    esi, esi
0x18005c17c  jz      short loc_18005C181
0x18005c17e  mov     al, r13b
0x18005c181  mov     [rsp+78h+arg_8], al
0x18005c188  test    r15, r15
0x18005c18b  jz      short loc_18005C19B
0x18005c18d  mov     esi, 4Bh ; 'K'
0x18005c192  lea     rdx, qword_180101A90
0x18005c199  jmp     short loc_18005C1A6
0x18005c19b  mov     esi, r14d
0x18005c19e  mov     rdx, r13
0x18005c1a1  xor     esi, edi
0x18005c1a3  add     esi, 4
0x18005c1a6  test    al, al
0x18005c1a8  jz      loc_18005C25C
0x18005c1ae  mov     ecx, esi
0x18005c1b0  call    cs:__imp_DwmpBeginTransitionRequestWithGUID
0x18005c1b6  mov     ebp, eax
0x18005c1b8  test    eax, eax
0x18005c1ba  js      loc_18005C261
0x18005c1c0  mov     ecx, esi
0x18005c1c2  sub     ecx, 4
0x18005c1c5  jz      short loc_18005C1E4
0x18005c1c7  sub     ecx, edi
0x18005c1c9  jz      short loc_18005C1DD
0x18005c1cb  cmp     ecx, 46h ; 'F'
0x18005c1ce  jz      short loc_18005C1D7
0x18005c1d0  mov     ecx, 0FFFh
0x18005c1d5  jmp     short loc_18005C1E9
0x18005c1d7  lea     ecx, [r14+12h]
0x18005c1db  jmp     short loc_18005C1E9
0x18005c1dd  mov     ecx, 1Ah
0x18005c1e2  jmp     short loc_18005C1E9
0x18005c1e4  mov     ecx, 19h
0x18005c1e9  mov     al, r14b
0x18005c1ec  xor     al, dil
0x18005c1ef  mov     [rbx+90h], al
0x18005c1f5  test    r14b, r14b
0x18005c1f8  jz      short loc_18005C202
0x18005c1fa  mov     al, dil
0x18005c1fd  cmp     esi, 4
0x18005c200  jz      short loc_18005C205
0x18005c202  mov     al, r13b
0x18005c205  cmp     ecx, 19h
0x18005c208  mov     [rbx+91h], al
0x18005c20e  mov     eax, 10400000h
0x18005c213  mov     edx, 10420000h
0x18005c218  cmovnz  edx, eax
0x18005c21b  or      edx, ecx
0x18005c21d  mov     rcx, [rbx+70h]
0x18005c221  call    cs:__imp_DwmpTransitionWindow
0x18005c227  mov     ebp, eax
0x18005c229  test    eax, eax
0x18005c22b  js      short loc_18005C261
0x18005c22d  test    r15, r15
0x18005c230  jz      short loc_18005C261
0x18005c232  mov     edx, 10400012h
0x18005c237  mov     rcx, r15
0x18005c23a  call    cs:__imp_DwmpTransitionWindow
0x18005c240  mov     ebp, eax
0x18005c242  test    eax, eax
0x18005c244  js      short loc_18005C261
0x18005c246  xor     r9d, r9d; lParam
0x18005c249  xor     r8d, r8d; wParam
0x18005c24c  mov     edx, 404h; Msg
0x18005c251  mov     rcx, r15; hWnd
0x18005c254  call    cs:__imp_SendMessageW
0x18005c25a  jmp     short loc_18005C261
0x18005c25c  mov     ebp, 80004005h
0x18005c261  mov     al, r14b
0x18005c264  mov     rcx, rbx; this
0x18005c267  xor     al, dil
0x18005c26a  movzx   r12d, al
0x18005c26e  mov     edx, r12d; int
0x18005c271  call    ?_CloakWindow@CBridgeWindow@@AEAAJH@Z; CBridgeWindow::_CloakWindow(int)
0x18005c276  mov     r15d, eax
0x18005c279  test    ebp, ebp
0x18005c27b  js      short loc_18005C285
0x18005c27d  mov     ecx, esi
0x18005c27f  call    cs:__imp_DwmpEndTransitionRequest
0x18005c285  test    r14b, r14b
0x18005c288  jnz     short loc_18005C2BB
0x18005c28a  cmp     [rsp+78h+arg_8], r13b
0x18005c292  jz      short loc_18005C298
0x18005c294  test    ebp, ebp
0x18005c296  js      short loc_18005C2A6
0x18005c298  cmp     [rsp+78h+arg_10], edi
0x18005c29f  jz      short loc_18005C2A6
0x18005c2a1  test    r15d, r15d
0x18005c2a4  jns     short loc_18005C2BB
0x18005c2a6  mov     edx, r15d; int
0x18005c2a9  mov     byte ptr [rbx+90h], 0
0x18005c2b0  mov     rcx, rbx; this
0x18005c2b3  mov     r13b, dil
0x18005c2b6  call    ?_RemoveOwner@CBridgeWindow@@AEAAXJ@Z; CBridgeWindow::_RemoveOwner(long)
0x18005c2bb  xor     r9d, r9d; fWinIni
0x18005c2be  mov     [rsp+78h+pvParam], edi
0x18005c2c5  lea     r8, [rsp+78h+pvParam]; pvParam
0x18005c2cd  xor     edx, edx; uiParam
0x18005c2cf  mov     ecx, 1042h; uiAction
0x18005c2d4  call    cs:__imp_SystemParametersInfoW
0x18005c2da  cmp     qword ptr [rbx+0F0h], 0
0x18005c2e2  jz      short loc_18005C30E
0x18005c2e4  lea     rdx, ?g_desktopSwitchLock@@3Vsrwlock@wil@@A; wil::srwlock g_desktopSwitchLock
0x18005c2eb  lea     rcx, [rsp+78h+arg_18]
0x18005c2f3  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18005c2f8  mov     r15b, cs:?g_trackedDesktopStateEverEnteredSecureDesktop@@3_NA; bool g_trackedDesktopStateEverEnteredSecureDesktop
0x18005c2ff  lea     rcx, [rsp+78h+arg_18]
0x18005c307  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005c30c  jmp     short loc_18005C311
0x18005c30e  xor     r15b, r15b
0x18005c311  cmp     [rsp+78h+arg_8], 0
0x18005c319  jz      short loc_18005C36D
0x18005c31b  cmp     [rsp+78h+pvParam], 0
0x18005c323  jnz     short loc_18005C329
0x18005c325  test    ebp, ebp
0x18005c327  js      short loc_18005C32E
0x18005c329  test    r15b, r15b
0x18005c32c  jz      short loc_18005C36D
0x18005c32e  test    r13b, r13b
0x18005c331  jz      short loc_18005C33A
0x18005c333  mov     r12b, [rbx+90h]
0x18005c33a  mov     [rbx+90h], r12b
0x18005c341  test    r14b, r14b
0x18005c344  jz      short loc_18005C34B
0x18005c346  cmp     esi, 4
0x18005c349  jz      short loc_18005C34E
0x18005c34b  xor     dil, dil
0x18005c34e  mov     rcx, [rbx+70h]; hWnd
0x18005c352  mov     r9d, 2; lParam
0x18005c358  xor     r8d, r8d; wParam
0x18005c35b  mov     [rbx+91h], dil
0x18005c362  mov     edx, 32Ah; Msg
0x18005c367  call    cs:__imp_PostMessageW
0x18005c36d  mov     rcx, rbx; this
0x18005c370  mov     byte ptr [rbx+8Eh], 0
0x18005c377  call    ?_MaybeNotifySplashScreenDismissed@CBridgeWindow@@AEAAXXZ; CBridgeWindow::_MaybeNotifySplashScreenDismissed(void)
0x18005c37c  add     rsp, 38h
0x18005c380  pop     r15
0x18005c382  pop     r14
0x18005c384  pop     r13
0x18005c386  pop     r12
0x18005c388  pop     rdi
0x18005c389  pop     rsi
0x18005c38a  pop     rbp
0x18005c38b  pop     rbx
0x18005c38c  retn
```
