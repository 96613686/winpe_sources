# CActionsContextMenuProvider::_CleanMenu(IApplicationFrameInternal *,HMENU__ *)

- ea: `0x18005ee24`
- end: `0x18005ef45`
- name: `?_CleanMenu@CActionsContextMenuProvider@@AEAAJPEAUIApplicationFrameInternal@@PEAUHMENU__@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(CActionsContextMenuProvider *__hidden this, struct IApplicationFrameInternal *, HMENU)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x18005f11c`

## callees

- `0x18003fbc0`
- `0x18005ed44`
- `0x18005ee24`
- `0x18005ef4c`
- `0x180072010`

## import_xrefs

- `SHCORE!IsOS` at `0x18005ee4a`
- `SHCORE!IsOS` at `0x18005ee4a`
- `twinapi.appcore!__imp_CoreIsWindowServiceSupported` at `0x18005eeb1`
- `twinapi.appcore!__imp_CoreIsWindowServiceSupported` at `0x18005eed8`
- `twinapi.appcore!__imp_CoreIsWindowServiceSupported` at `0x18005eeb1`
- `twinapi.appcore!__imp_CoreIsWindowServiceSupported` at `0x18005eed8`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18005ef04`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18005ef04`
- `USER32!RemoveMenu` at `0x18005eec6`
- `USER32!RemoveMenu` at `0x18005eeed`
- `USER32!RemoveMenu` at `0x18005ef2d`
- `USER32!RemoveMenu` at `0x18005eec6`
- `USER32!RemoveMenu` at `0x18005eeed`
- `USER32!RemoveMenu` at `0x18005ef2d`
- `USER32!DeleteMenu` at `0x18005ee5f`
- `USER32!DeleteMenu` at `0x18005ee5f`

## pseudocode

```c
__int64 __fastcall CActionsContextMenuProvider::_CleanMenu(
        CActionsContextMenuProvider *this,
        struct IApplicationFrameInternal *a2,
        HMENU a3)
{
  const char *v6; // r9
  __int64 v8; // rax
  unsigned int PropW; // eax
  bool DoesAppImplementSearchContract; // al
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HWND hWnd; // [rsp+48h] [rbp+20h] BYREF

  if ( (!WinIsProximityProviderAvailable() || IsOS(0x1Du)) && !DeleteMenu(a3, 0x2F4Bu, 0) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x12C,
             (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\actionsmenuprovider.cpp",
             v6);
  v8 = *(_QWORD *)a2;
  hWnd = 0;
  if ( (*(int (__fastcall **)(struct IApplicationFrameInternal *, HWND *))(v8 + 40))(a2, &hWnd) >= 0 )
  {
    if ( (int)CoreIsWindowServiceSupported(hWnd, &GUID_8d844e7f_2f1b_4029_a06c_c5e27c863dbd) < 0 )
      RemoveMenu(a3, 0x2F48u, 0);
    if ( (int)CoreIsWindowServiceSupported(hWnd, &SID_EdgeGesture) < 0 )
      RemoveMenu(a3, 0x2F4Au, 0);
  }
  if ( !hWnd
    || ((PropW = (unsigned int)GetPropW(hWnd, L"Windows.ImmersiveShell.ShouldShowAppInSearchPane")) == 0
      ? (DoesAppImplementSearchContract = CActionsContextMenuProvider::_DoesAppImplementSearchContract(this))
      : (DoesAppImplementSearchContract = PropW == 1),
        !DoesAppImplementSearchContract) )
  {
    RemoveMenu(a3, 0x2F46u, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18005ee24  mov     [rsp+arg_0], rbx
0x18005ee29  mov     [rsp+arg_8], rsi
0x18005ee2e  push    rdi
0x18005ee2f  sub     rsp, 20h
0x18005ee33  mov     rbx, r8
0x18005ee36  mov     rdi, rdx
0x18005ee39  mov     rsi, rcx
0x18005ee3c  call    ?WinIsProximityProviderAvailable@@YA_NXZ; WinIsProximityProviderAvailable(void)
0x18005ee41  test    al, al
0x18005ee43  jz      short loc_18005EE54
0x18005ee45  mov     ecx, 1Dh; dwOS
0x18005ee4a  call    cs:__imp_IsOS
0x18005ee50  test    eax, eax
0x18005ee52  jz      short loc_18005EE84
0x18005ee54  xor     r8d, r8d; uFlags
0x18005ee57  mov     edx, 2F4Bh; uPosition
0x18005ee5c  mov     rcx, rbx; hMenu
0x18005ee5f  call    cs:__imp_DeleteMenu
0x18005ee65  test    eax, eax
0x18005ee67  jnz     short loc_18005EE84
0x18005ee69  mov     rcx, [rsp+28h]; this
0x18005ee6e  lea     r8, aPcshellShellAp_7; "pcshell\\shell\\applicationframe\\frame"...
0x18005ee75  mov     edx, 12Ch; void *
0x18005ee7a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005ee7f  jmp     loc_18005EF35
0x18005ee84  mov     rax, [rdi]
0x18005ee87  lea     rdx, [rsp+28h+hWnd]
0x18005ee8c  mov     rcx, rdi
0x18005ee8f  mov     [rsp+28h+hWnd], 0
0x18005ee98  mov     rax, [rax+28h]
0x18005ee9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eea1  test    eax, eax
0x18005eea3  js      short loc_18005EEF3
0x18005eea5  mov     rcx, [rsp+28h+hWnd]
0x18005eeaa  lea     rdx, _GUID_8d844e7f_2f1b_4029_a06c_c5e27c863dbd
0x18005eeb1  call    cs:__imp_CoreIsWindowServiceSupported
0x18005eeb7  test    eax, eax
0x18005eeb9  jns     short loc_18005EECC
0x18005eebb  xor     r8d, r8d; uFlags
0x18005eebe  mov     edx, 2F48h; uPosition
0x18005eec3  mov     rcx, rbx; hMenu
0x18005eec6  call    cs:__imp_RemoveMenu
0x18005eecc  mov     rcx, [rsp+28h+hWnd]
0x18005eed1  lea     rdx, SID_EdgeGesture
0x18005eed8  call    cs:__imp_CoreIsWindowServiceSupported
0x18005eede  test    eax, eax
0x18005eee0  jns     short loc_18005EEF3
0x18005eee2  xor     r8d, r8d; uFlags
0x18005eee5  mov     edx, 2F4Ah; uPosition
0x18005eeea  mov     rcx, rbx; hMenu
0x18005eeed  call    cs:__imp_RemoveMenu
0x18005eef3  mov     rcx, [rsp+28h+hWnd]; hWnd
0x18005eef8  test    rcx, rcx
0x18005eefb  jz      short loc_18005EF22
0x18005eefd  lea     rdx, aWindowsImmersi; "Windows.ImmersiveShell.ShouldShowAppInS"...
0x18005ef04  call    cs:__imp_GetPropW
0x18005ef0a  test    eax, eax
0x18005ef0c  jz      short loc_18005EF16
0x18005ef0e  cmp     eax, 1
0x18005ef11  setz    al
0x18005ef14  jmp     short loc_18005EF1E
0x18005ef16  mov     rcx, rsi; this
0x18005ef19  call    ?_DoesAppImplementSearchContract@CActionsContextMenuProvider@@AEAA_NXZ; CActionsContextMenuProvider::_DoesAppImplementSearchContract(void)
0x18005ef1e  test    al, al
0x18005ef20  jnz     short loc_18005EF33
0x18005ef22  xor     r8d, r8d; uFlags
0x18005ef25  mov     edx, 2F46h; uPosition
0x18005ef2a  mov     rcx, rbx; hMenu
0x18005ef2d  call    cs:__imp_RemoveMenu
0x18005ef33  xor     eax, eax
0x18005ef35  mov     rbx, [rsp+28h+arg_0]
0x18005ef3a  mov     rsi, [rsp+28h+arg_8]
0x18005ef3f  add     rsp, 20h
0x18005ef43  pop     rdi
0x18005ef44  retn
```
