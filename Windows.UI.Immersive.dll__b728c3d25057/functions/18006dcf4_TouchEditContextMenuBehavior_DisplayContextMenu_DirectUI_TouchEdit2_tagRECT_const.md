# TouchEditContextMenuBehavior::_DisplayContextMenu(DirectUI::TouchEdit2 *,tagRECT const &)

- ea: `0x18006dcf4`
- end: `0x18006e2c2`
- name: `?_DisplayContextMenu@TouchEditContextMenuBehavior@@AEAAJPEAVTouchEdit2@DirectUI@@AEBUtagRECT@@@Z`
- size: `1486`
- prototype: `__int64 __fastcall(TouchEditContextMenuBehavior *__hidden this, struct DirectUI::TouchEdit2 *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006d940`

## callees

- `0x180013244`
- `0x18003cfb0`
- `0x18004c1e4`
- `0x180050ba0`
- `0x180060b68`
- `0x18006d034`
- `0x18006d120`
- `0x18006d1b4`
- `0x18006d248`
- `0x18006d2dc`
- `0x18006d370`
- `0x18006d724`
- `0x18006dba8`
- `0x18006dcf4`
- `0x1800e5010`

## import_xrefs

- `SHCORE!__imp_RelativeRectFromPhysicalRectWithScale` at `0x18006e23e`
- `SHCORE!__imp_RelativeRectFromPhysicalRectWithScale` at `0x18006e23e`
- `DUI70!?GetIgnoredKeyCombos@TouchEditBase@DirectUI@@QEAA?AW4TouchEditFilteredKeyComboFlags@2@XZ` at `0x18006dd56`
- `DUI70!?GetIgnoredKeyCombos@TouchEditBase@DirectUI@@QEAA?AW4TouchEditFilteredKeyComboFlags@2@XZ` at `0x18006dd56`
- `DUI70!?GetReadOnly@TouchEditBase@DirectUI@@QEAA_NXZ` at `0x18006dd38`
- `DUI70!?GetReadOnly@TouchEditBase@DirectUI@@QEAA_NXZ` at `0x18006dd38`
- `DUI70!?HasSelection@TouchEdit2@DirectUI@@QEAA_NXZ` at `0x18006dd2c`
- `DUI70!?HasSelection@TouchEdit2@DirectUI@@QEAA_NXZ` at `0x18006dd2c`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18006e1cf`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18006e1cf`

## pseudocode

```c
__int64 __fastcall TouchEditContextMenuBehavior::_DisplayContextMenu(
        TouchEditContextMenuBehavior *this,
        struct DirectUI::TouchEdit2 *a2,
        const struct tagRECT *a3)
{
  char v4; // r12
  char IgnoredKeyCombos; // al
  __int64 v6; // rcx
  char v7; // r14
  __int64 (__fastcall *v8)(struct DirectUI::TouchEdit2 *, __int64 *); // rbx
  int v9; // edi
  char v10; // si
  bool v11; // r15
  __int64 *v12; // rax
  struct Windows::UI::Popups::IPopupMenu *v13; // rbx
  __int64 (__fastcall *v14)(struct Windows::UI::Popups::IPopupMenu *, GUID *, __int64 *); // rdi
  bool v15; // al
  struct Windows::UI::Popups::IUICommandInvokedHandler **v16; // rax
  struct Windows::UI::Popups::IUICommandInvokedHandler *v17; // rbx
  TouchEditContextMenuBehavior *v18; // rcx
  struct Windows::UI::Popups::IUICommandInvokedHandler **v19; // rax
  struct Windows::UI::Popups::IUICommandInvokedHandler *v20; // rbx
  TouchEditContextMenuBehavior *v21; // rcx
  struct Windows::UI::Popups::IUICommandInvokedHandler **v22; // rax
  struct Windows::UI::Popups::IUICommandInvokedHandler *v23; // rbx
  TouchEditContextMenuBehavior *v24; // rcx
  struct Windows::UI::Popups::IUICommandInvokedHandler **v25; // rax
  struct Windows::UI::Popups::IUICommandInvokedHandler *v26; // rbx
  TouchEditContextMenuBehavior *v27; // rcx
  struct Windows::UI::Popups::IPopupMenu *v28; // rbx
  HWND v29; // rsi
  __int64 (__fastcall *v30)(struct Windows::UI::Popups::IPopupMenu *, GUID *, __int64 *); // rdi
  struct DirectUI::Element *Root; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  enum DEVICE_SCALE_FACTOR v34; // eax
  struct Windows::UI::Popups::IPopupMenu *v35; // rdi
  __int64 (__fastcall *v36)(struct Windows::UI::Popups::IPopupMenu *, __int128 *, TouchEditContextMenuBehavior **); // rbx
  bool Only; // [rsp+30h] [rbp-69h]
  __int64 v39; // [rsp+38h] [rbp-61h] BYREF
  bool HasSelection; // [rsp+40h] [rbp-59h]
  TouchEditContextMenuBehavior *v41; // [rsp+48h] [rbp-51h] BYREF
  struct Windows::UI::Popups::IPopupMenu *v42; // [rsp+50h] [rbp-49h] BYREF
  __int64 v43; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v44[2]; // [rsp+60h] [rbp-39h] BYREF
  __int128 v45; // [rsp+70h] [rbp-29h] BYREF
  __int128 v46; // [rsp+80h] [rbp-19h] BYREF
  HSTRING string; // [rsp+90h] [rbp-9h] BYREF

  *(_QWORD *)&v45 = a3;
  *(_QWORD *)&v46 = a2;
  HasSelection = DirectUI::TouchEdit2::HasSelection(a2);
  Only = DirectUI::TouchEditBase::GetReadOnly(a2);
  v4 = (*(__int64 (__fastcall **)(struct DirectUI::TouchEdit2 *))(*(_QWORD *)a2 + 16LL))(a2);
  IgnoredKeyCombos = DirectUI::TouchEditBase::GetIgnoredKeyCombos(a2);
  v6 = *(_QWORD *)a2;
  v7 = IgnoredKeyCombos;
  v43 = 0;
  v8 = *(__int64 (__fastcall **)(struct DirectUI::TouchEdit2 *, __int64 *))(v6 + 368);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
  v9 = v8(a2, &v43);
  if ( v9 < 0 )
  {
    v11 = 0;
LABEL_11:
    v10 = 0;
    goto LABEL_12;
  }
  v39 = 0;
  v10 = 1;
  (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v43 + 24LL))(v43, 14, 0);
  v11 = (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v43 + 24LL))(
          v43,
          1074,
          0,
          0,
          &v39) >= 0
     && v39;
  if ( v4
    || (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v43 + 24LL))(
         v43,
         198,
         0,
         0,
         &v39) < 0
    || !v39 )
  {
    goto LABEL_11;
  }
LABEL_12:
  v42 = 0;
  if ( v9 < 0 )
    goto LABEL_57;
  v12 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, L"Windows.UI.Popups.PopupMenu");
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>(*v12, &v42);
  if ( v9 >= 0 )
  {
    v39 = 0;
    v13 = v42;
    v14 = **(__int64 (__fastcall ***)(struct Windows::UI::Popups::IPopupMenu *, GUID *, __int64 *))v42;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    v9 = v14(v13, &GUID_181e01e5_f091_4d6b_85d4_a35a1191709c, &v39);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    if ( v9 >= 0 )
    {
      v15 = Only;
      if ( HasSelection )
      {
        if ( Only )
        {
          if ( !v4 )
          {
LABEL_26:
            if ( (v7 & 0x11) != 0x11 )
            {
              v39 = v43;
              if ( v43 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
              v19 = (struct Windows::UI::Popups::IUICommandInvokedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler__lambda_e33c50f189b7423db4a6233779417bb5___1_Windows::UI::Popups::IUICommand_____lambda_e33c50f189b7423db4a6233779417bb5___(
                                                                               &v41,
                                                                               &v39);
              v20 = *v19;
              *v19 = 0;
              v21 = v41;
              v44[0] = v20;
              if ( v41 )
              {
                v41 = 0;
                Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
              }
              v9 = TouchEditContextMenuBehavior::_AddCommand(v21, v42, 0x2262u, v20);
              Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v44);
              Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
              if ( v9 < 0 )
                goto LABEL_49;
            }
            v15 = Only;
          }
        }
        else if ( !v4 )
        {
          if ( (v7 & 0x24) != 0x24 )
          {
            v39 = v43;
            if ( v43 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
            v16 = (struct Windows::UI::Popups::IUICommandInvokedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler__lambda_407fe2a523d125ac0dfc12da008f27b8___1_Windows::UI::Popups::IUICommand_____lambda_407fe2a523d125ac0dfc12da008f27b8___(
                                                                             &v41,
                                                                             &v39);
            v17 = *v16;
            *v16 = 0;
            v18 = v41;
            v44[0] = v17;
            if ( v41 )
            {
              v41 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
            }
            v9 = TouchEditContextMenuBehavior::_AddCommand(v18, v42, 0x2261u, v17);
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v44);
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
            if ( v9 < 0 )
              goto LABEL_49;
          }
          goto LABEL_26;
        }
      }
      if ( !v11 || v15 || (v7 & 0xA) == 0xA )
        goto LABEL_43;
      v39 = v43;
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
      v22 = (struct Windows::UI::Popups::IUICommandInvokedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler__lambda_6b207a4fc27e98e6a7c835da50fdbaa1___1_Windows::UI::Popups::IUICommand_____lambda_6b207a4fc27e98e6a7c835da50fdbaa1___(
                                                                       &v41,
                                                                       &v39);
      v23 = *v22;
      *v22 = 0;
      v24 = v41;
      v44[0] = v23;
      if ( v41 )
      {
        v41 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
      }
      v9 = TouchEditContextMenuBehavior::_AddCommand(v24, v42, 0x2263u, v23);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v44);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
      if ( v9 >= 0 )
      {
LABEL_43:
        if ( !HasSelection && !Only && v10 )
        {
          v39 = v43;
          if ( v43 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
          v25 = (struct Windows::UI::Popups::IUICommandInvokedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler__lambda_fb36a96919ef6648cbdefe112dbccf5d___1_Windows::UI::Popups::IUICommand_____lambda_fb36a96919ef6648cbdefe112dbccf5d___(
                                                                           &v41,
                                                                           &v39);
          v26 = *v25;
          *v25 = 0;
          v27 = v41;
          v44[0] = v26;
          if ( v41 )
          {
            v41 = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
          }
          v9 = TouchEditContextMenuBehavior::_AddCommand(v27, v42, 0x2264u, v26);
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v44);
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
        }
      }
    }
  }
LABEL_49:
  v28 = v42;
  if ( v9 >= 0 )
  {
    v29 = 0;
    v39 = 0;
    v30 = **(__int64 (__fastcall ***)(struct Windows::UI::Popups::IPopupMenu *, GUID *, __int64 *))v42;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    v9 = v30(v28, &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1, &v39);
    if ( v9 >= 0 )
    {
      Root = DirectUI::Element::GetRoot((DirectUI::Element *)v46);
      v32 = element_cast<DirectUI::HWNDElement>(Root);
      if ( v32 && (v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 360LL))(v32), (v29 = (HWND)v33) != 0) )
        v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 24LL))(v39, v33);
      else
        v9 = -2147418113;
    }
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    if ( v9 >= 0 )
    {
      v34 = DUIGetScaleFactorForWindow(v29);
      v46 = 0;
      RelativeRectFromPhysicalRectWithScale((unsigned int)v34, v45, &v46);
      v35 = v42;
      v41 = 0;
      v36 = *(__int64 (__fastcall **)(struct Windows::UI::Popups::IPopupMenu *, __int128 *, TouchEditContextMenuBehavior **))(*(_QWORD *)v42 + 64LL);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
      v45 = v46;
      v9 = v36(v35, &v45, &v41);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
    }
  }
LABEL_57:
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006dcf4  mov     [rsp-8+arg_0], rbx
0x18006dcf9  push    rbp
0x18006dcfa  push    rsi
0x18006dcfb  push    rdi
0x18006dcfc  push    r12
0x18006dcfe  push    r13
0x18006dd00  push    r14
0x18006dd02  push    r15
0x18006dd04  lea     rbp, [rsp-27h]
0x18006dd09  sub     rsp, 0C0h
0x18006dd10  mov     rax, cs:__security_cookie
0x18006dd17  xor     rax, rsp
0x18006dd1a  mov     [rbp+57h+var_40], rax
0x18006dd1e  mov     rcx, rdx
0x18006dd21  mov     qword ptr [rbp+57h+var_80], r8
0x18006dd25  mov     rdi, rdx
0x18006dd28  mov     qword ptr [rbp+57h+var_70], rdx
0x18006dd2c  call    cs:__imp_?HasSelection@TouchEdit2@DirectUI@@QEAA_NXZ; DirectUI::TouchEdit2::HasSelection(void)
0x18006dd32  mov     rcx, rdi
0x18006dd35  mov     [rbp+57h+var_B0], al
0x18006dd38  call    cs:__imp_?GetReadOnly@TouchEditBase@DirectUI@@QEAA_NXZ; DirectUI::TouchEditBase::GetReadOnly(void)
0x18006dd3e  mov     rcx, [rdi]
0x18006dd41  mov     [rbp+57h+var_C0], al
0x18006dd44  mov     rax, [rcx+10h]
0x18006dd48  mov     rcx, rdi
0x18006dd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd50  mov     rcx, rdi
0x18006dd53  mov     r12b, al
0x18006dd56  call    cs:__imp_?GetIgnoredKeyCombos@TouchEditBase@DirectUI@@QEAA?AW4TouchEditFilteredKeyComboFlags@2@XZ; DirectUI::TouchEditBase::GetIgnoredKeyCombos(void)
0x18006dd5c  mov     rcx, [rdi]
0x18006dd5f  mov     r14d, eax
0x18006dd62  mov     [rbp+57h+var_98], 0
0x18006dd6a  mov     rbx, [rcx+170h]
0x18006dd71  lea     rcx, [rbp+57h+var_98]
0x18006dd75  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006dd7a  lea     rdx, [rbp+57h+var_98]
0x18006dd7e  mov     rcx, rdi
0x18006dd81  mov     rax, rbx
0x18006dd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd89  mov     edi, eax
0x18006dd8b  test    eax, eax
0x18006dd8d  js      loc_18006DE44
0x18006dd93  mov     r10, [rbp+57h+var_98]
0x18006dd97  xor     r9d, r9d
0x18006dd9a  mov     [rbp+57h+var_B8], 0
0x18006dda2  xor     r8d, r8d
0x18006dda5  mov     rcx, [r10]
0x18006dda8  lea     edx, [r9+0Eh]
0x18006ddac  mov     rax, [rcx+18h]
0x18006ddb0  lea     rcx, [rbp+57h+var_B8]
0x18006ddb4  mov     [rsp+0F0h+var_D0], rcx
0x18006ddb9  mov     rcx, r10
0x18006ddbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddc1  mov     sil, 1
0x18006ddc4  test    eax, eax
0x18006ddc6  js      short loc_18006DDD4
0x18006ddc8  cmp     [rbp+57h+var_B8], 0
0x18006ddcd  jle     short loc_18006DDD4
0x18006ddcf  mov     r13b, sil
0x18006ddd2  jmp     short loc_18006DDD7
0x18006ddd4  xor     r13b, r13b
0x18006ddd7  mov     rcx, [rbp+57h+var_98]
0x18006dddb  lea     rdx, [rbp+57h+var_B8]
0x18006dddf  mov     [rsp+0F0h+var_D0], rdx
0x18006dde4  xor     r9d, r9d
0x18006dde7  xor     r8d, r8d
0x18006ddea  mov     edx, 432h
0x18006ddef  mov     rax, [rcx]
0x18006ddf2  mov     rax, [rax+18h]
0x18006ddf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddfb  test    eax, eax
0x18006ddfd  js      short loc_18006DE0B
0x18006ddff  cmp     [rbp+57h+var_B8], 0
0x18006de04  jz      short loc_18006DE0B
0x18006de06  mov     r15b, sil
0x18006de09  jmp     short loc_18006DE0E
0x18006de0b  xor     r15b, r15b
0x18006de0e  test    r12b, r12b
0x18006de11  jnz     short loc_18006DE4A
0x18006de13  mov     rcx, [rbp+57h+var_98]
0x18006de17  lea     rdx, [rbp+57h+var_B8]
0x18006de1b  mov     [rsp+0F0h+var_D0], rdx
0x18006de20  xor     r9d, r9d
0x18006de23  xor     r8d, r8d
0x18006de26  mov     edx, 0C6h
0x18006de2b  mov     rax, [rcx]
0x18006de2e  mov     rax, [rax+18h]
0x18006de32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de37  test    eax, eax
0x18006de39  js      short loc_18006DE4A
0x18006de3b  cmp     [rbp+57h+var_B8], 0
0x18006de40  jnz     short loc_18006DE4D
0x18006de42  jmp     short loc_18006DE4A
0x18006de44  xor     r13b, r13b
0x18006de47  xor     r15b, r15b
0x18006de4a  xor     sil, sil
0x18006de4d  xor     ebx, ebx
0x18006de4f  mov     [rbp+57h+var_A0], rbx
0x18006de53  test    edi, edi
0x18006de55  js      loc_18006E287
0x18006de5b  lea     rdx, ?RuntimeClass_Windows_UI_Popups_PopupMenu@@3QBGB; "Windows.UI.Popups.PopupMenu"
0x18006de62  lea     rcx, [rbp+57h+string]; string
0x18006de66  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x18006de6b  lea     rdx, [rbp+57h+var_A0]
0x18006de6f  mov     rcx, [rax]
0x18006de72  call    ??$ActivateInstance@V?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>)
0x18006de77  mov     edi, eax
0x18006de79  test    eax, eax
0x18006de7b  js      loc_18006E18E
0x18006de81  mov     [rbp+57h+var_B8], rbx
0x18006de85  lea     rcx, [rbp+57h+var_B8]
0x18006de89  mov     rbx, [rbp+57h+var_A0]
0x18006de8d  mov     rax, [rbx]
0x18006de90  mov     rdi, [rax]
0x18006de93  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006de98  lea     r8, [rbp+57h+var_B8]
0x18006de9c  mov     rcx, rbx
0x18006de9f  lea     rdx, _GUID_181e01e5_f091_4d6b_85d4_a35a1191709c
0x18006dea6  mov     rax, rdi
0x18006dea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006deae  lea     rcx, [rbp+57h+var_B8]
0x18006deb2  mov     edi, eax
0x18006deb4  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006deb9  test    edi, edi
0x18006debb  js      loc_18006E18E
0x18006dec1  cmp     [rbp+57h+var_B0], 0
0x18006dec5  mov     al, [rbp+57h+var_C0]
0x18006dec8  jz      loc_18006DFF5
0x18006dece  test    al, al
0x18006ded0  jnz     loc_18006DF67
0x18006ded6  test    r12b, r12b
0x18006ded9  jnz     loc_18006DFF5
0x18006dedf  mov     eax, r14d
0x18006dee2  and     eax, 24h
0x18006dee5  cmp     al, 24h ; '$'
0x18006dee7  jz      loc_18006DF70
0x18006deed  mov     rcx, [rbp+57h+var_98]
0x18006def1  mov     [rbp+57h+var_B8], rcx
0x18006def5  test    rcx, rcx
0x18006def8  jz      short loc_18006DF06
0x18006defa  mov     rax, [rcx]
0x18006defd  mov     rax, [rax+8]
0x18006df01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df06  lea     rdx, [rbp+57h+var_B8]
0x18006df0a  lea     rcx, [rbp+57h+var_A8]
0x18006df0e  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_407fe2a523d125ac0dfc12da008f27b8___1_Windows__UI__Popups__IUICommand_____lambda_407fe2a523d125ac0dfc12da008f27b8___
0x18006df13  mov     rbx, [rax]
0x18006df16  mov     qword ptr [rax], 0
0x18006df1d  mov     rcx, [rbp+57h+var_A8]
0x18006df21  mov     [rbp+57h+var_90], rbx
0x18006df25  test    rcx, rcx
0x18006df28  jz      short loc_18006DF37
0x18006df2a  mov     [rbp+57h+var_A8], 0
0x18006df32  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x18006df37  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x18006df3b  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x18006df3e  mov     r8d, 2261h; unsigned int
0x18006df44  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
0x18006df49  lea     rcx, [rbp+57h+var_90]
0x18006df4d  mov     edi, eax
0x18006df4f  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006df54  lea     rcx, [rbp+57h+var_B8]
0x18006df58  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006df5d  test    edi, edi
0x18006df5f  js      loc_18006E18E
0x18006df65  jmp     short loc_18006DF70
0x18006df67  test    r12b, r12b
0x18006df6a  jnz     loc_18006DFF5
0x18006df70  mov     eax, r14d
0x18006df73  and     eax, 11h
0x18006df76  cmp     al, 11h
0x18006df78  jz      short loc_18006DFF2
0x18006df7a  mov     rcx, [rbp+57h+var_98]
0x18006df7e  mov     [rbp+57h+var_B8], rcx
0x18006df82  test    rcx, rcx
0x18006df85  jz      short loc_18006DF93
0x18006df87  mov     rax, [rcx]
0x18006df8a  mov     rax, [rax+8]
0x18006df8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df93  lea     rdx, [rbp+57h+var_B8]
0x18006df97  lea     rcx, [rbp+57h+var_A8]
0x18006df9b  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_e33c50f189b7423db4a6233779417bb5___1_Windows__UI__Popups__IUICommand_____lambda_e33c50f189b7423db4a6233779417bb5___
0x18006dfa0  mov     rbx, [rax]
0x18006dfa3  mov     qword ptr [rax], 0
0x18006dfaa  mov     rcx, [rbp+57h+var_A8]
0x18006dfae  mov     [rbp+57h+var_90], rbx
0x18006dfb2  test    rcx, rcx
0x18006dfb5  jz      short loc_18006DFC4
0x18006dfb7  mov     [rbp+57h+var_A8], 0
0x18006dfbf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x18006dfc4  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x18006dfc8  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x18006dfcb  mov     r8d, 2262h; unsigned int
0x18006dfd1  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
0x18006dfd6  lea     rcx, [rbp+57h+var_90]
0x18006dfda  mov     edi, eax
0x18006dfdc  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006dfe1  lea     rcx, [rbp+57h+var_B8]
0x18006dfe5  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006dfea  test    edi, edi
0x18006dfec  js      loc_18006E18E
0x18006dff2  mov     al, [rbp+57h+var_C0]
0x18006dff5  test    r15b, r15b
0x18006dff8  jz      loc_18006E088
0x18006dffe  test    al, al
0x18006e000  jnz     loc_18006E088
0x18006e006  and     r14d, 0Ah
0x18006e00a  cmp     r14b, 0Ah
0x18006e00e  jz      short loc_18006E088
0x18006e010  mov     rcx, [rbp+57h+var_98]
0x18006e014  mov     [rbp+57h+var_B8], rcx
0x18006e018  test    rcx, rcx
0x18006e01b  jz      short loc_18006E029
0x18006e01d  mov     rax, [rcx]
0x18006e020  mov     rax, [rax+8]
0x18006e024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e029  lea     rdx, [rbp+57h+var_B8]
0x18006e02d  lea     rcx, [rbp+57h+var_A8]
0x18006e031  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_6b207a4fc27e98e6a7c835da50fdbaa1___1_Windows__UI__Popups__IUICommand_____lambda_6b207a4fc27e98e6a7c835da50fdbaa1___
0x18006e036  mov     rbx, [rax]
0x18006e039  mov     qword ptr [rax], 0
0x18006e040  mov     rcx, [rbp+57h+var_A8]
0x18006e044  mov     [rbp+57h+var_90], rbx
0x18006e048  test    rcx, rcx
0x18006e04b  jz      short loc_18006E05A
0x18006e04d  mov     [rbp+57h+var_A8], 0
0x18006e055  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x18006e05a  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x18006e05e  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x18006e061  mov     r8d, 2263h; unsigned int
0x18006e067  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
0x18006e06c  lea     rcx, [rbp+57h+var_90]
0x18006e070  mov     edi, eax
0x18006e072  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006e077  lea     rcx, [rbp+57h+var_B8]
0x18006e07b  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006e080  test    edi, edi
0x18006e082  js      loc_18006E18E
0x18006e088  mov     r14b, [rbp+57h+var_B0]
0x18006e08c  test    r14b, r14b
0x18006e08f  jnz     loc_18006E18E
0x18006e095  cmp     [rbp+57h+var_C0], r14b
0x18006e099  jnz     short loc_18006E119
0x18006e09b  test    sil, sil
0x18006e09e  jz      short loc_18006E119
0x18006e0a0  mov     rcx, [rbp+57h+var_98]
0x18006e0a4  mov     [rbp+57h+var_B8], rcx
0x18006e0a8  test    rcx, rcx
0x18006e0ab  jz      short loc_18006E0B9
0x18006e0ad  mov     rax, [rcx]
0x18006e0b0  mov     rax, [rax+8]
0x18006e0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e0b9  lea     rdx, [rbp+57h+var_B8]
0x18006e0bd  lea     rcx, [rbp+57h+var_A8]
0x18006e0c1  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_fb36a96919ef6648cbdefe112dbccf5d___1_Windows__UI__Popups__IUICommand_____lambda_fb36a96919ef6648cbdefe112dbccf5d___
0x18006e0c6  mov     rbx, [rax]
0x18006e0c9  mov     qword ptr [rax], 0
0x18006e0d0  mov     rcx, [rbp+57h+var_A8]
0x18006e0d4  mov     [rbp+57h+var_90], rbx
0x18006e0d8  test    rcx, rcx
0x18006e0db  jz      short loc_18006E0EA
0x18006e0dd  mov     [rbp+57h+var_A8], 0
0x18006e0e5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x18006e0ea  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x18006e0ee  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x18006e0f1  mov     r8d, 2264h; unsigned int
0x18006e0f7  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
0x18006e0fc  lea     rcx, [rbp+57h+var_90]
0x18006e100  mov     edi, eax
0x18006e102  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006e107  lea     rcx, [rbp+57h+var_B8]
0x18006e10b  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18006e110  test    edi, edi
0x18006e112  js      short loc_18006E18E
0x18006e114  test    r14b, r14b
0x18006e117  jnz     short loc_18006E18E
0x18006e119  test    r13b, r13b
0x18006e11c  jz      short loc_18006E18E
0x18006e11e  mov     rcx, [rbp+57h+var_98]
0x18006e122  mov     [rbp+57h+var_B8], rcx
0x18006e126  test    rcx, rcx
0x18006e129  jz      short loc_18006E137
0x18006e12b  mov     rax, [rcx]
0x18006e12e  mov     rax, [rax+8]
0x18006e132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e137  lea     rdx, [rbp+57h+var_B8]
0x18006e13b  lea     rcx, [rbp+57h+var_A8]
0x18006e13f  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler__lambda_86143fd989600146d21f638323ca6ae2___1_Windows__UI__Popups__IUICommand_____lambda_86143fd989600146d21f638323ca6ae2___
0x18006e144  mov     rbx, [rax]
0x18006e147  mov     qword ptr [rax], 0
0x18006e14e  mov     rcx, [rbp+57h+var_A8]
0x18006e152  mov     [rbp+57h+var_90], rbx
0x18006e156  test    rcx, rcx
0x18006e159  jz      short loc_18006E168
0x18006e15b  mov     [rbp+57h+var_A8], 0
0x18006e163  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x18006e168  mov     rdx, [rbp+57h+var_A0]; struct Windows::UI::Popups::IPopupMenu *
0x18006e16c  mov     r9, rbx; struct Windows::UI::Popups::IUICommandInvokedHandler *
0x18006e16f  mov     r8d, 2265h; unsigned int
0x18006e175  call    ?_AddCommand@TouchEditContextMenuBehavior@@AEAAJPEAUIPopupMenu@Popups@UI@Windows@@IPEAUIUICommandInvokedHandler@345@@Z; TouchEditContextMenuBehavior::_AddCommand(Windows::UI::Popups::IPopupMenu *,uint,Windows::UI::Popups::IUICommandInvokedHandler *)
  ... truncated ...
```
