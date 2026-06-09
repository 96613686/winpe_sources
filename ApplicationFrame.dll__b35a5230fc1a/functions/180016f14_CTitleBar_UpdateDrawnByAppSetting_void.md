# CTitleBar::_UpdateDrawnByAppSetting(void)

- ea: `0x180016f14`
- end: `0x1800173d3`
- name: `?_UpdateDrawnByAppSetting@CTitleBar@@AEAAJXZ`
- size: `1215`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180057964`
- `0x180057ee8`
- `0x180057f98`

## callees

- `0x180004c98`
- `0x180008d90`
- `0x180015964`
- `0x180016590`
- `0x180016f14`
- `0x18001763c`
- `0x1800176f8`
- `0x180017934`
- `0x180017e6c`
- `0x180023cdc`
- `0x180024184`
- `0x180040270`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017203`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017203`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017082`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017082`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017131`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017131`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180017125`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180017125`
- `TWINAPI!__imp_QueryWindowService` at `0x180017154`
- `TWINAPI!__imp_QueryWindowService` at `0x180017154`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CTitleBar::_UpdateDrawnByAppSetting(CTitleBar *this)
{
  char *v3; // rcx
  __int64 v4; // r9
  int v5; // ebx
  char v6; // r14
  __int64 v7; // rcx
  bool v8; // al
  __int64 v9; // rcx
  int updated; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  DWORD WindowThreadProcessId; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  char *v28; // [rsp+60h] [rbp+40h] BYREF
  int v29; // [rsp+68h] [rbp+48h] BYREF
  __int64 v30; // [rsp+70h] [rbp+50h] BYREF
  __int64 v31; // [rsp+78h] [rbp+58h] BYREF

  if ( *((_BYTE *)this + 558) || *((_BYTE *)this + 576) )
    return 0;
  v29 = 1;
  v30 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
  v30 = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
  v3 = 0;
  v28 = 0;
  v4 = *((_QWORD *)this + 13);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, char **))(*(_QWORD *)v4 + 24LL))(
           *((_QWORD *)this + 13),
           &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
           &v28);
    v3 = v28;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 >= 0 )
  {
    if ( v3 )
    {
      v5 = (**(__int64 (__fastcall ***)(char *, GUID *, __int64 *))v3)(
             v3,
             &GUID_2420fd9d_4ff9_4924_b94b_eef7c60d5511,
             &v30);
      v3 = v28;
    }
    else
    {
      v5 = -2147467259;
    }
  }
  if ( v3 )
  {
    v28 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15F8,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v5,
      savedregs);
  }
  else if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 64LL))(v30, &v29) >= 0 && v29 == 2 )
  {
LABEL_32:
    v12 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return 0;
  }
  v6 = *((_BYTE *)this + 566);
  v7 = *((_QWORD *)this + 53);
  if ( v7 )
  {
    LODWORD(v28) = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v7 + 24LL))(v7, &v28);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10F5,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)(unsigned int)v18,
        savedregs);
    v8 = (_DWORD)v28 != 0;
  }
  else
  {
    v8 = 0;
  }
  *((_BYTE *)this + 566) = v8;
  CTitleBar::_UpdateDragAreaWidthSetting(this);
  v31 = 0;
  if ( !*((_BYTE *)this + 567) )
    goto LABEL_69;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v31);
  WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 63), 0);
  if ( GetCurrentThreadId() == WindowThreadProcessId )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1347,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)0x80070057LL,
      savedregs);
  if ( (int)QueryWindowService(
              *((_QWORD *)this + 63),
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
              &v31) >= 0 )
  {
    LOBYTE(v28) = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v31 + 56LL))(v31, &v28);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1103,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)(unsigned int)v14,
        savedregs);
      v16 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v17 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      return v15;
    }
    *((_BYTE *)this + 566) = (_BYTE)v28 != 0;
  }
  else
  {
LABEL_69:
    if ( !*((_BYTE *)this + 571) )
      *((_BYTE *)this + 566) = 0;
  }
  CTitleBar::_UpdateHitTestWindow(this);
  if ( v6 == *((_BYTE *)this + 566) )
  {
LABEL_22:
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
    v28 = (char *)this + 584;
    v9 = *((_QWORD *)this + 53);
    if ( v9 )
    {
      if ( v30 )
      {
        if ( !v29 )
        {
          if ( *((_BYTE *)this + 624) )
          {
            *((_BYTE *)this + 624) = 0;
            v23 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 32LL))(
                    v9,
                    *((unsigned __int8 *)this + 566));
            if ( v23 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1135,
                (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
                (const char *)(unsigned int)v23,
                savedregs);
          }
        }
      }
    }
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::GetImpl'::`2'::impl);
    updated = CTitleBar::_UpdateMica(this);
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x113A,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)(unsigned int)updated,
        savedregs);
    if ( this != (CTitleBar *)-584LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
    v11 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_32;
  }
  v19 = CTitleBar::_Cloak(this, *((_DWORD *)this + 138) == 1, 0, 1);
  v15 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111B,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v19,
      savedregs);
    v24 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
  }
  else
  {
    CTitleBar::_UpdateDwmFrameInset(this);
    if ( v30 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v30 + 272LL))(v30, 0);
    if ( !CTitleBar::_DidReservedMetricsChange(this) )
      goto LABEL_22;
    v20 = CTitleBar::_NotifyReservedMetricsChanged(this);
    v15 = v20;
    if ( v20 >= 0 )
      goto LABEL_22;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1127,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)v20,
      savedregs);
    v21 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180016f14  push    rbp
0x180016f16  push    rbx
0x180016f17  push    rsi
0x180016f18  push    rdi
0x180016f19  push    r12
0x180016f1b  push    r14
0x180016f1d  push    r15; int
0x180016f1f  mov     rbp, rsp
0x180016f22  sub     rsp, 20h
0x180016f26  mov     rdi, rcx
0x180016f29  xor     r15d, r15d
0x180016f2c  cmp     [rcx+22Eh], r15b
0x180016f33  jz      short loc_180016F46
0x180016f35  xor     eax, eax
0x180016f37  add     rsp, 20h
0x180016f3b  pop     r15
0x180016f3d  pop     r14
0x180016f3f  pop     r12
0x180016f41  pop     rdi
0x180016f42  pop     rsi
0x180016f43  pop     rbx
0x180016f44  pop     rbp
0x180016f45  retn
0x180016f46  cmp     [rcx+240h], r15b
0x180016f4d  jnz     short loc_180016F35
0x180016f4f  mov     [rbp+arg_8], 1
0x180016f56  mov     [rbp+arg_10], r15
0x180016f5a  lea     rcx, [rbp+arg_10]
0x180016f5e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180016f63  mov     [rbp+arg_10], r15
0x180016f67  mov     [rbp+arg_0], r15
0x180016f6b  lea     rcx, [rbp+arg_0]
0x180016f6f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180016f74  nop
0x180016f75  mov     rcx, r15
0x180016f78  mov     [rbp+arg_0], rcx
0x180016f7c  mov     r9, [rdi+68h]
0x180016f80  test    r9, r9
0x180016f83  jz      loc_18001738A
0x180016f89  mov     rax, [r9]
0x180016f8c  lea     r8, [rbp+arg_0]
0x180016f90  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180016f97  mov     rcx, r9
0x180016f9a  mov     rax, [rax+18h]
0x180016f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fa3  mov     ebx, eax
0x180016fa5  mov     rcx, [rbp+arg_0]
0x180016fa9  test    ebx, ebx
0x180016fab  js      short loc_180016FCE
0x180016fad  test    rcx, rcx
0x180016fb0  jz      short loc_180017016
0x180016fb2  mov     rax, [rcx]
0x180016fb5  lea     r8, [rbp+arg_10]
0x180016fb9  lea     rdx, _GUID_2420fd9d_4ff9_4924_b94b_eef7c60d5511
0x180016fc0  mov     rax, [rax]
0x180016fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc8  mov     ebx, eax
0x180016fca  mov     rcx, [rbp+arg_0]
0x180016fce  test    rcx, rcx
0x180016fd1  jz      short loc_180016FE4
0x180016fd3  mov     [rbp+arg_0], r15
0x180016fd7  mov     rax, [rcx]
0x180016fda  mov     rax, [rax+10h]
0x180016fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe3  nop
0x180016fe4  lea     r12, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180016feb  test    ebx, ebx
0x180016fed  js      loc_180017392
0x180016ff3  mov     rcx, [rbp+arg_10]
0x180016ff7  mov     rax, [rcx]
0x180016ffa  lea     rdx, [rbp+arg_8]
0x180016ffe  mov     rax, [rax+40h]
0x180017002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017007  test    eax, eax
0x180017009  js      short loc_18001701D
0x18001700b  cmp     [rbp+arg_8], 2
0x18001700f  jnz     short loc_18001701D
0x180017011  jmp     loc_1800170F4
0x180017016  mov     ebx, 80004005h
0x18001701b  jmp     short loc_180016FCE
0x18001701d  mov     r14b, [rdi+236h]
0x180017024  mov     rcx, [rdi+1A8h]
0x18001702b  test    rcx, rcx
0x18001702e  jnz     loc_1800171D4
0x180017034  mov     al, r15b
0x180017037  mov     [rdi+236h], al
0x18001703d  mov     rcx, rdi; this
0x180017040  call    ?_UpdateDragAreaWidthSetting@CTitleBar@@AEAAXXZ; CTitleBar::_UpdateDragAreaWidthSetting(void)
0x180017045  mov     [rbp+arg_18], r15
0x180017049  cmp     [rdi+237h], r15b
0x180017050  jnz     loc_180017113
0x180017056  cmp     [rdi+23Bh], r15b
0x18001705d  jz      loc_1800173C6
0x180017063  mov     rcx, rdi; this
0x180017066  call    ?_UpdateHitTestWindow@CTitleBar@@AEAAJXZ; CTitleBar::_UpdateHitTestWindow(void)
0x18001706b  cmp     r14b, [rdi+236h]
0x180017072  jnz     loc_18001720E
0x180017078  lea     rbx, [rdi+248h]
0x18001707f  mov     rcx, rbx; lpCriticalSection
0x180017082  call    cs:__imp_EnterCriticalSection
0x180017088  mov     [rbp+arg_0], rbx
0x18001708c  mov     rcx, [rdi+1A8h]
0x180017093  test    rcx, rcx
0x180017096  jz      short loc_1800170B1
0x180017098  cmp     [rbp+arg_10], r15
0x18001709c  jz      short loc_1800170B1
0x18001709e  cmp     [rbp+arg_8], r15d
0x1800170a2  jnz     short loc_1800170B1
0x1800170a4  cmp     [rdi+270h], r15b
0x1800170ab  jnz     loc_1800172C5
0x1800170b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar> `wil::Feature<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::GetImpl(void)'::`2'::impl
0x1800170b8  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800170bd  mov     rcx, rdi; this
0x1800170c0  call    ?_UpdateMica@CTitleBar@@AEAAJXZ; CTitleBar::_UpdateMica(void)
0x1800170c5  mov     rcx, [rbp+38h]; this
0x1800170c9  test    eax, eax
0x1800170cb  js      loc_180017375
0x1800170d1  test    rbx, rbx
0x1800170d4  jnz     loc_180017200
0x1800170da  mov     rcx, [rbp+arg_18]
0x1800170de  test    rcx, rcx
0x1800170e1  jz      short loc_1800170F4
0x1800170e3  mov     [rbp+arg_18], r15
0x1800170e7  mov     rax, [rcx]
0x1800170ea  mov     rax, [rax+10h]
0x1800170ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170f3  nop
0x1800170f4  mov     rcx, [rbp+arg_10]
0x1800170f8  test    rcx, rcx
0x1800170fb  jz      short loc_18001710E
0x1800170fd  mov     [rbp+arg_10], r15
0x180017101  mov     rax, [rcx]
0x180017104  mov     rax, [rax+10h]
0x180017108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001710d  nop
0x18001710e  jmp     loc_180016F35
0x180017113  lea     rcx, [rbp+arg_18]
0x180017117  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001711c  xor     edx, edx; lpdwProcessId
0x18001711e  mov     rcx, [rdi+1F8h]; hWnd
0x180017125  call    cs:__imp_GetWindowThreadProcessId
0x18001712b  mov     ebx, eax
0x18001712d  mov     rsi, [rbp+38h]
0x180017131  call    cs:__imp_GetCurrentThreadId
0x180017137  cmp     eax, ebx
0x180017139  jz      loc_1800173AB
0x18001713f  lea     r9, [rbp+arg_18]
0x180017143  lea     rdx, _GUID_006d35e3_e1f1_431b_9508_29b96926ac53
0x18001714a  mov     r8, rdx
0x18001714d  mov     rcx, [rdi+1F8h]
0x180017154  call    cs:__imp_QueryWindowService
0x18001715a  test    eax, eax
0x18001715c  js      loc_180017056
0x180017162  mov     byte ptr [rbp+arg_0], r15b
0x180017166  mov     rcx, [rbp+arg_18]
0x18001716a  mov     rax, [rcx]
0x18001716d  lea     rdx, [rbp+arg_0]
0x180017171  mov     rax, [rax+38h]
0x180017175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001717a  mov     ebx, eax
0x18001717c  test    eax, eax
0x18001717e  jns     loc_180017300
0x180017184  mov     rcx, [rbp+38h]; this
0x180017188  mov     r9d, eax; char *
0x18001718b  mov     r8, r12; unsigned int
0x18001718e  mov     edx, 1103h; void *
0x180017193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017198  nop
0x180017199  mov     rcx, [rbp+arg_18]
0x18001719d  test    rcx, rcx
0x1800171a0  jz      short loc_1800171B3
0x1800171a2  mov     [rbp+arg_18], r15
0x1800171a6  mov     rax, [rcx]
0x1800171a9  mov     rax, [rax+10h]
0x1800171ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171b2  nop
0x1800171b3  mov     rcx, [rbp+arg_10]
0x1800171b7  test    rcx, rcx
0x1800171ba  jz      short loc_1800171CD
0x1800171bc  mov     [rbp+arg_10], r15
0x1800171c0  mov     rax, [rcx]
0x1800171c3  mov     rax, [rax+10h]
0x1800171c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171cc  nop
0x1800171cd  mov     eax, ebx
0x1800171cf  jmp     loc_180016F37
0x1800171d4  mov     dword ptr [rbp+arg_0], r15d
0x1800171d8  mov     rax, [rcx]
0x1800171db  lea     rdx, [rbp+arg_0]
0x1800171df  mov     rax, [rax+18h]
0x1800171e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e8  mov     rcx, [rbp+38h]; this
0x1800171ec  test    eax, eax
0x1800171ee  js      loc_180017312
0x1800171f4  cmp     dword ptr [rbp+arg_0], r15d
0x1800171f8  setnz   al
0x1800171fb  jmp     loc_180017037
0x180017200  mov     rcx, rbx; lpCriticalSection
0x180017203  call    cs:__imp_LeaveCriticalSection
0x180017209  jmp     loc_1800170DA
0x18001720e  mov     edx, r15d
0x180017211  cmp     dword ptr [rdi+228h], 1
0x180017218  setz    dl; int
0x18001721b  mov     r9b, 1; bool
0x18001721e  xor     r8d, r8d; bool
0x180017221  mov     rcx, rdi; this
0x180017224  call    ?_Cloak@CTitleBar@@AEAAJH_N0@Z; CTitleBar::_Cloak(int,bool,bool)
0x180017229  mov     ebx, eax
0x18001722b  test    eax, eax
0x18001722d  js      loc_180017327
0x180017233  mov     rcx, rdi; this
0x180017236  call    ?_UpdateDwmFrameInset@CTitleBar@@AEAAXXZ; CTitleBar::_UpdateDwmFrameInset(void)
0x18001723b  mov     rcx, [rbp+arg_10]
0x18001723f  test    rcx, rcx
0x180017242  jz      short loc_180017255
0x180017244  mov     rax, [rcx]
0x180017247  xor     edx, edx
0x180017249  mov     rax, [rax+110h]
0x180017250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017255  mov     rcx, rdi; this
0x180017258  call    ?_DidReservedMetricsChange@CTitleBar@@AEAA_NXZ; CTitleBar::_DidReservedMetricsChange(void)
0x18001725d  test    al, al
0x18001725f  jz      loc_180017078
0x180017265  mov     rcx, rdi; this
0x180017268  call    ?_NotifyReservedMetricsChanged@CTitleBar@@AEAAJXZ; CTitleBar::_NotifyReservedMetricsChanged(void)
0x18001726d  mov     ebx, eax
0x18001726f  test    eax, eax
0x180017271  jns     loc_180017078
0x180017277  mov     rcx, [rbp+38h]; this
0x18001727b  mov     r9d, eax; char *
0x18001727e  mov     r8, r12; unsigned int
0x180017281  mov     edx, 1127h; void *
0x180017286  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001728b  nop
0x18001728c  mov     rcx, [rbp+arg_18]
0x180017290  test    rcx, rcx
0x180017293  jz      short loc_1800172A6
0x180017295  mov     [rbp+arg_18], r15
0x180017299  mov     rax, [rcx]
0x18001729c  mov     rax, [rax+10h]
0x1800172a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a5  nop
0x1800172a6  mov     rcx, [rbp+arg_10]
0x1800172aa  test    rcx, rcx
0x1800172ad  jz      short loc_1800172C0
0x1800172af  mov     [rbp+arg_10], r15
0x1800172b3  mov     rax, [rcx]
0x1800172b6  mov     rax, [rax+10h]
0x1800172ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172bf  nop
0x1800172c0  jmp     loc_1800171CD
0x1800172c5  mov     [rdi+270h], r15b
0x1800172cc  mov     rax, [rcx]
0x1800172cf  movzx   edx, byte ptr [rdi+236h]
0x1800172d6  mov     rax, [rax+20h]
0x1800172da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172df  mov     rcx, [rbp+38h]; this
0x1800172e3  test    eax, eax
0x1800172e5  jns     loc_1800170B1
0x1800172eb  mov     r9d, eax; char *
0x1800172ee  mov     r8, r12; unsigned int
0x1800172f1  mov     edx, 1135h; void *
0x1800172f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800172fb  jmp     loc_1800170B1
0x180017300  cmp     byte ptr [rbp+arg_0], r15b
0x180017304  setnz   al
0x180017307  mov     [rdi+236h], al
0x18001730d  jmp     loc_180017063
0x180017312  mov     r9d, eax; char *
0x180017315  mov     r8, r12; unsigned int
0x180017318  mov     edx, 10F5h; void *
0x18001731d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017322  jmp     loc_1800171F4
0x180017327  mov     rcx, [rbp+38h]; this
0x18001732b  mov     r9d, ebx; char *
0x18001732e  mov     r8, r12; unsigned int
0x180017331  mov     edx, 111Bh; void *
0x180017336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001733b  nop
0x18001733c  mov     rcx, [rbp+arg_18]
0x180017340  test    rcx, rcx
0x180017343  jz      short loc_180017356
0x180017345  mov     [rbp+arg_18], r15
0x180017349  mov     rax, [rcx]
0x18001734c  mov     rax, [rax+10h]
0x180017350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017355  nop
0x180017356  mov     rcx, [rbp+arg_10]
0x18001735a  test    rcx, rcx
0x18001735d  jz      short loc_180017370
0x18001735f  mov     [rbp+arg_10], r15
0x180017363  mov     rax, [rcx]
0x180017366  mov     rax, [rax+10h]
0x18001736a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001736f  nop
0x180017370  jmp     loc_1800171CD
0x180017375  mov     r9d, eax; char *
0x180017378  mov     r8, r12; unsigned int
0x18001737b  mov     edx, 113Ah; void *
0x180017380  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
  ... truncated ...
```
