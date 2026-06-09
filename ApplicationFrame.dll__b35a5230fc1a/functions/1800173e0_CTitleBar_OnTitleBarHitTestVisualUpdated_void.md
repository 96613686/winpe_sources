# CTitleBar::_OnTitleBarHitTestVisualUpdated(void)

- ea: `0x1800173e0`
- end: `0x180017636`
- name: `?_OnTitleBarHitTestVisualUpdated@CTitleBar@@AEAAJXZ`
- size: `598`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180057f98`
- `0x180059a10`

## callees

- `0x180004c98`
- `0x1800173e0`
- `0x18001763c`
- `0x1800176f8`
- `0x180024184`
- `0x180040270`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017416`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017416`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180017409`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180017409`
- `TWINAPI!__imp_QueryWindowService` at `0x18001743e`
- `TWINAPI!__imp_QueryWindowService` at `0x18001743e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CTitleBar::_OnTitleBarHitTestVisualUpdated(HWND *this)
{
  DWORD WindowThreadProcessId; // edi
  int v3; // eax
  unsigned int v4; // edi
  HWND v5; // rdx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD *); // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // rcx
  int v16; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v18; // [rsp+40h] [rbp+8h] BYREF
  __int64 v19; // [rsp+48h] [rbp+10h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp+18h] BYREF

  v20 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
  WindowThreadProcessId = GetWindowThreadProcessId(this[63], 0);
  if ( GetCurrentThreadId() == WindowThreadProcessId )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1347,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)0x80070057LL,
      v16);
  if ( (int)QueryWindowService(
              this[63],
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &v20) < 0 )
  {
LABEL_17:
    CTitleBar::_UpdateDragAreaWidthSetting((CTitleBar *)this);
    CTitleBar::_UpdateHitTestWindow((CTitleBar *)this);
    v13 = v20;
    if ( v20 )
    {
      v20 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v13)[2])(v13);
    }
    return 0;
  }
  v19 = 0;
  v3 = (**v20)(v20, &GUID_6e470d39_e79f_453c_92ef_6310edefd440, &v19);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( ((_BYTE)this[182] & 0x40) != 0 )
      v5 = 0;
    else
      v5 = this[64];
    v6 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v19 + 64LL))(v19, v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14F9,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)(unsigned int)v6,
        v16);
      v8 = v19;
      if ( v19 )
      {
        v19 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      v9 = v20;
      if ( v20 )
      {
        v20 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v9)[2])(v9);
      }
      return v7;
    }
    v18 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 80LL))(v19, &v18);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x14FC,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)(unsigned int)v11,
        v16);
    *((_BYTE *)this + 568) = v18 != 0;
    v12 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14F7,
    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
    (const char *)(unsigned int)v3,
    v16);
  v14 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v20;
  if ( v20 )
  {
    v20 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15);
  }
  return v4;
}

```

## disassembly

```asm
0x1800173e0  mov     [rsp+arg_18], rbx
0x1800173e5  push    rbp
0x1800173e6  push    rsi
0x1800173e7  push    rdi; int
0x1800173e8  sub     rsp, 20h
0x1800173ec  mov     rbx, rcx
0x1800173ef  xor     ebp, ebp
0x1800173f1  mov     [rsp+38h+arg_10], rbp
0x1800173f6  lea     rcx, [rsp+38h+arg_10]
0x1800173fb  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180017400  xor     edx, edx; lpdwProcessId
0x180017402  mov     rcx, [rbx+1F8h]; hWnd
0x180017409  call    cs:__imp_GetWindowThreadProcessId
0x18001740f  mov     edi, eax
0x180017411  mov     rsi, [rsp+38h]
0x180017416  call    cs:__imp_GetCurrentThreadId
0x18001741c  cmp     eax, edi
0x18001741e  jz      loc_180017616
0x180017424  lea     r9, [rsp+38h+arg_10]
0x180017429  lea     r8, _GUID_006d35e3_e1f1_431b_9508_29b96926ac53
0x180017430  lea     rdx, _GUID_006d35e3_e1f1_431b_9508_29b96926ac53
0x180017437  mov     rcx, [rbx+1F8h]
0x18001743e  call    cs:__imp_QueryWindowService
0x180017444  test    eax, eax
0x180017446  js      loc_180017559
0x18001744c  mov     [rsp+38h+arg_8], rbp
0x180017451  mov     rcx, [rsp+38h+arg_10]
0x180017456  mov     rax, [rcx]
0x180017459  lea     r8, [rsp+38h+arg_8]
0x18001745e  lea     rdx, _GUID_6e470d39_e79f_453c_92ef_6310edefd440
0x180017465  mov     rax, [rax]
0x180017468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001746d  mov     edi, eax
0x18001746f  test    eax, eax
0x180017471  js      loc_180017595
0x180017477  mov     rcx, [rsp+38h+arg_8]
0x18001747c  mov     rax, [rcx]
0x18001747f  test    byte ptr [rbx+5B0h], 40h
0x180017486  jnz     loc_18001758D
0x18001748c  mov     rdx, [rbx+200h]
0x180017493  mov     rax, [rax+40h]
0x180017497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001749c  mov     edi, eax
0x18001749e  test    eax, eax
0x1800174a0  jns     short loc_180017503
0x1800174a2  mov     rcx, [rsp+38h]; this
0x1800174a7  mov     r9d, eax; char *
0x1800174aa  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x1800174b1  mov     edx, 14F9h; void *
0x1800174b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174bb  nop
0x1800174bc  mov     rcx, [rsp+38h+arg_8]
0x1800174c1  test    rcx, rcx
0x1800174c4  jz      short loc_1800174D8
0x1800174c6  mov     [rsp+38h+arg_8], rbp
0x1800174cb  mov     rax, [rcx]
0x1800174ce  mov     rax, [rax+10h]
0x1800174d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174d7  nop
0x1800174d8  mov     rcx, [rsp+38h+arg_10]
0x1800174dd  test    rcx, rcx
0x1800174e0  jz      short loc_1800174F4
0x1800174e2  mov     [rsp+38h+arg_10], rbp
0x1800174e7  mov     rax, [rcx]
0x1800174ea  mov     rax, [rax+10h]
0x1800174ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174f3  nop
0x1800174f4  mov     eax, edi
0x1800174f6  mov     rbx, [rsp+38h+arg_18]
0x1800174fb  add     rsp, 20h
0x1800174ff  pop     rdi
0x180017500  pop     rsi
0x180017501  pop     rbp
0x180017502  retn
0x180017503  mov     [rsp+38h+arg_0], ebp
0x180017507  mov     rcx, [rsp+38h+arg_8]
0x18001750c  mov     rax, [rcx]
0x18001750f  lea     rdx, [rsp+38h+arg_0]
0x180017514  mov     rax, [rax+50h]
0x180017518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001751d  mov     rcx, [rsp+38h]; this
0x180017522  test    eax, eax
0x180017524  js      loc_1800175FD
0x18001752a  cmp     [rsp+38h+arg_0], 0
0x18001752f  jnz     loc_1800175F6
0x180017535  xor     al, al
0x180017537  mov     [rbx+238h], al
0x18001753d  mov     rcx, [rsp+38h+arg_8]
0x180017542  test    rcx, rcx
0x180017545  jz      short loc_180017559
0x180017547  mov     [rsp+38h+arg_8], rbp
0x18001754c  mov     rax, [rcx]
0x18001754f  mov     rax, [rax+10h]
0x180017553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017558  nop
0x180017559  mov     rcx, rbx; this
0x18001755c  call    ?_UpdateDragAreaWidthSetting@CTitleBar@@AEAAXXZ; CTitleBar::_UpdateDragAreaWidthSetting(void)
0x180017561  mov     rcx, rbx; this
0x180017564  call    ?_UpdateHitTestWindow@CTitleBar@@AEAAJXZ; CTitleBar::_UpdateHitTestWindow(void)
0x180017569  nop
0x18001756a  mov     rcx, [rsp+38h+arg_10]
0x18001756f  test    rcx, rcx
0x180017572  jz      short loc_180017586
0x180017574  mov     [rsp+38h+arg_10], rbp
0x180017579  mov     rax, [rcx]
0x18001757c  mov     rax, [rax+10h]
0x180017580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017585  nop
0x180017586  xor     eax, eax
0x180017588  jmp     loc_1800174F6
0x18001758d  mov     rdx, rbp
0x180017590  jmp     loc_180017493
0x180017595  mov     rcx, [rsp+38h]; this
0x18001759a  mov     r9d, edi; char *
0x18001759d  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x1800175a4  mov     edx, 14F7h; void *
0x1800175a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800175ae  nop
0x1800175af  mov     rcx, [rsp+38h+arg_8]
0x1800175b4  test    rcx, rcx
0x1800175b7  jz      short loc_1800175CB
0x1800175b9  mov     [rsp+38h+arg_8], rbp
0x1800175be  mov     rax, [rcx]
0x1800175c1  mov     rax, [rax+10h]
0x1800175c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ca  nop
0x1800175cb  mov     rcx, [rsp+38h+arg_10]
0x1800175d0  test    rcx, rcx
0x1800175d3  jz      short loc_1800175E7
0x1800175d5  mov     [rsp+38h+arg_10], rbp
0x1800175da  mov     rax, [rcx]
0x1800175dd  mov     rax, [rax+10h]
0x1800175e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175e6  nop
0x1800175e7  mov     eax, edi
0x1800175e9  mov     rbx, [rsp+38h+arg_18]
0x1800175ee  add     rsp, 20h
0x1800175f2  pop     rdi
0x1800175f3  pop     rsi
0x1800175f4  pop     rbp
0x1800175f5  retn
0x1800175f6  mov     al, 1
0x1800175f8  jmp     loc_180017537
0x1800175fd  mov     r9d, eax; char *
0x180017600  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180017607  mov     edx, 14FCh; void *
0x18001760c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017611  jmp     loc_18001752A
0x180017616  mov     r9d, 80070057h; char *
0x18001761c  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180017623  mov     edx, 1347h; void *
0x180017628  mov     rcx, rsi; this
0x18001762b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017630  jmp     loc_180017424
```
