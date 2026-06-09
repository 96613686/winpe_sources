# CAnimationScheduler::OnWindowTransitionTargetChanged(CWindowData *,DWMTRANSITION_TARGET,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &,tagRECT const &)

- ea: `0x18006692c`
- end: `0x180066bbf`
- name: `?OnWindowTransitionTargetChanged@CAnimationScheduler@@QEAAJPEAVCWindowData@@W4DWMTRANSITION_TARGET@@AEBUtagRECT@@2222@Z`
- size: `659`
- prototype: `int __high(struct CWindowData *, enum DWMTRANSITION_TARGET, const struct tagRECT *, const struct tagRECT *, const struct tagRECT *, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180066850`

## callees

- `0x18002dfa0`
- `0x18002eea0`
- `0x18002f470`
- `0x18006692c`
- `0x180066bc8`
- `0x1800689e0`
- `0x18009f308`
- `0x1800ea010`

## import_xrefs

- `USER32!CopyRect` at `0x180066966`
- `USER32!CopyRect` at `0x18006697a`
- `USER32!CopyRect` at `0x18006698e`
- `USER32!CopyRect` at `0x1800669a2`
- `USER32!CopyRect` at `0x1800669b6`
- `USER32!CopyRect` at `0x180066966`
- `USER32!CopyRect` at `0x18006697a`
- `USER32!CopyRect` at `0x18006698e`
- `USER32!CopyRect` at `0x1800669a2`
- `USER32!CopyRect` at `0x1800669b6`

## pseudocode

```c
__int64 __fastcall CAnimationScheduler::OnWindowTransitionTargetChanged(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const RECT *a4,
        RECT *lprcSrc,
        RECT *a6,
        RECT *a7,
        RECT *a8)
{
  CTopLevelWindow *v12; // rcx
  CTopLevelWindow *v13; // rcx
  CTopLevelWindow *v14; // rcx
  CTopLevelWindow *v15; // rcx
  __int64 v16; // rdx
  __int64 i; // rdi
  _DWORD *v19; // rcx
  HWND v20; // rdx
  struct _MARGINS v21; // [rsp+20h] [rbp-18h] BYREF
  struct CTransitionWindowSnapshot *v22; // [rsp+80h] [rbp+48h] BYREF

  if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
    McTemplateU0pd_EtwEventWriteTransfer(a1, &UdwmSystemAnimation_WindowTarget, *(_QWORD *)(a2 + 40), a3);
  CopyRect((LPRECT)(a2 + 748), a4);
  CopyRect((LPRECT)(a2 + 764), lprcSrc);
  CopyRect((LPRECT)(a2 + 780), a6);
  CopyRect((LPRECT)(a2 + 796), a7);
  CopyRect((LPRECT)(a2 + 812), a8);
  if ( a2 )
  {
    v12 = *(CTopLevelWindow **)(a2 + 440);
    if ( v12 )
    {
      CTopLevelWindow::GetOutsideMarginsWithDropShadow(v12, &v21);
      *(_DWORD *)(a2 + 756) -= v21.cxRightWidth;
      *(_DWORD *)(a2 + 752) += v21.cyTopHeight;
      *(_DWORD *)(a2 + 748) += v21.cxLeftWidth;
      *(_DWORD *)(a2 + 760) -= v21.cyBottomHeight;
    }
    v13 = *(CTopLevelWindow **)(a2 + 440);
    if ( v13 )
    {
      CTopLevelWindow::GetOutsideMarginsWithDropShadow(v13, &v21);
      *(_DWORD *)(a2 + 772) -= v21.cxRightWidth;
      *(_DWORD *)(a2 + 768) += v21.cyTopHeight;
      *(_DWORD *)(a2 + 764) += v21.cxLeftWidth;
      *(_DWORD *)(a2 + 776) -= v21.cyBottomHeight;
    }
    v14 = *(CTopLevelWindow **)(a2 + 440);
    if ( v14 )
    {
      CTopLevelWindow::GetOutsideMarginsWithDropShadow(v14, &v21);
      *(_DWORD *)(a2 + 788) -= v21.cxRightWidth;
      *(_DWORD *)(a2 + 784) += v21.cyTopHeight;
      *(_DWORD *)(a2 + 780) += v21.cxLeftWidth;
      *(_DWORD *)(a2 + 792) -= v21.cyBottomHeight;
    }
    v15 = *(CTopLevelWindow **)(a2 + 440);
    if ( v15 )
    {
      CTopLevelWindow::GetOutsideMarginsWithDropShadow(v15, &v21);
      *(_DWORD *)(a2 + 804) -= v21.cxRightWidth;
      *(_DWORD *)(a2 + 800) += v21.cyTopHeight;
      *(_DWORD *)(a2 + 796) += v21.cxLeftWidth;
      *(_DWORD *)(a2 + 808) -= v21.cyBottomHeight;
    }
  }
  *(_DWORD *)(a2 + 744) &= 0x2000000u;
  *(_DWORD *)(a2 + 744) |= a3;
  v16 = *(unsigned int *)(a2 + 744);
  if ( *(_QWORD *)(a2 + 440) )
  {
    if ( (v16 & 0x80000) == 0 && (v16 & 0x20000000) != 0 )
    {
      if ( (unsigned __int8)CAnimationScheduler::ShouldSnapshot(
                              *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 23),
                              v16,
                              0) )
      {
        if ( CStoryboard::ShouldAnimateShowWindow((const struct CWindowData *)a2) )
        {
          CTransitionVisualController::EnsureSnapshot(
            *((CTransitionVisualController **)CDesktopManager::s_pDesktopManagerInstance + 24),
            (struct CWindowData *)a2);
          *(_DWORD *)(a2 + 744) |= 0x4000000u;
          v20 = *(HWND *)(a2 + 40);
          v22 = 0;
          if ( (int)CTransitionVisualController::GetStoredSnapshotNoRef(
                      *((CTransitionVisualController **)CDesktopManager::s_pDesktopManagerInstance + 24),
                      v20,
                      &v22) >= 0 )
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v22 + 26) + 32LL) + 744LL) = *(_DWORD *)(a2 + 744);
        }
      }
    }
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 40); i = (unsigned int)(i + 1) )
  {
    v19 = *(_DWORD **)(*(_QWORD *)(a1 + 16) + 8 * i);
    if ( !v19[6] )
      (*(void (__fastcall **)(_DWORD *, __int64, _QWORD))(*(_QWORD *)v19 + 104LL))(v19, a2, a3);
  }
  return 0;
}

```

## disassembly

```asm
0x18006692c  push    rbp
0x18006692e  push    rbx
0x18006692f  push    rsi
0x180066930  push    rdi
0x180066931  push    r12
0x180066933  push    r13
0x180066935  push    r14
0x180066937  push    r15
0x180066939  mov     rbp, rsp
0x18006693c  sub     rsp, 38h
0x180066940  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x180066947  mov     rdi, r9
0x18006694a  mov     r12d, r8d
0x18006694d  mov     rbx, rdx
0x180066950  mov     r13, rcx
0x180066953  jnz     loc_180066B0B
0x180066959  lea     r15, [rbx+2ECh]
0x180066960  mov     rdx, rdi; lprcSrc
0x180066963  mov     rcx, r15; lprcDst
0x180066966  call    cs:__imp_CopyRect
0x18006696c  mov     rdx, [rbp+lprcSrc]; lprcSrc
0x180066970  lea     r14, [rbx+2FCh]
0x180066977  mov     rcx, r14; lprcDst
0x18006697a  call    cs:__imp_CopyRect
0x180066980  mov     rdx, [rbp+arg_28]; lprcSrc
0x180066984  lea     rsi, [rbx+30Ch]
0x18006698b  mov     rcx, rsi; lprcDst
0x18006698e  call    cs:__imp_CopyRect
0x180066994  mov     rdx, [rbp+arg_30]; lprcSrc
0x180066998  lea     rdi, [rbx+31Ch]
0x18006699f  mov     rcx, rdi; lprcDst
0x1800669a2  call    cs:__imp_CopyRect
0x1800669a8  mov     rdx, [rbp+arg_38]; lprcSrc
0x1800669af  lea     rcx, [rbx+32Ch]; lprcDst
0x1800669b6  call    cs:__imp_CopyRect
0x1800669bc  test    rbx, rbx
0x1800669bf  jz      short loc_180066A01
0x1800669c1  mov     rcx, [rbx+1B8h]; this
0x1800669c8  test    rcx, rcx
0x1800669cb  jnz     loc_180066B23
0x1800669d1  mov     rcx, [rbx+1B8h]; this
0x1800669d8  test    rcx, rcx
0x1800669db  jnz     loc_180066B4C
0x1800669e1  mov     rcx, [rbx+1B8h]; this
0x1800669e8  test    rcx, rcx
0x1800669eb  jnz     loc_180066B75
0x1800669f1  mov     rcx, [rbx+1B8h]; this
0x1800669f8  test    rcx, rcx
0x1800669fb  jnz     loc_180066B9A
0x180066a01  and     dword ptr [rbx+2E8h], 2000000h
0x180066a0b  or      [rbx+2E8h], r12d
0x180066a12  cmp     qword ptr [rbx+1B8h], 0
0x180066a1a  mov     edx, [rbx+2E8h]
0x180066a20  jnz     short loc_180066A59
0x180066a22  xor     edi, edi
0x180066a24  cmp     [r13+28h], edi
0x180066a28  ja      short loc_180066A3D
0x180066a2a  xor     eax, eax
0x180066a2c  add     rsp, 38h
0x180066a30  pop     r15
0x180066a32  pop     r14
0x180066a34  pop     r13
0x180066a36  pop     r12
0x180066a38  pop     rdi
0x180066a39  pop     rsi
0x180066a3a  pop     rbx
0x180066a3b  pop     rbp
0x180066a3c  retn
0x180066a3d  mov     rax, [r13+10h]
0x180066a41  mov     rcx, [rax+rdi*8]
0x180066a45  cmp     dword ptr [rcx+18h], 0
0x180066a49  jz      loc_180066AF4
0x180066a4f  inc     edi
0x180066a51  cmp     edi, [r13+28h]
0x180066a55  jnb     short loc_180066A2A
0x180066a57  jmp     short loc_180066A3D
0x180066a59  bt      edx, 13h
0x180066a5d  jb      short loc_180066A22
0x180066a5f  bt      edx, 1Dh
0x180066a63  jnb     short loc_180066A22
0x180066a65  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180066a6c  xor     r8d, r8d
0x180066a6f  mov     rcx, [rcx+0B8h]
0x180066a76  call    ?ShouldSnapshot@CAnimationScheduler@@QEAA_NW4DWMTRANSITION_TARGET@@PEBVCStoryboard@@@Z; CAnimationScheduler::ShouldSnapshot(DWMTRANSITION_TARGET,CStoryboard const *)
0x180066a7b  test    al, al
0x180066a7d  jz      short loc_180066A22
0x180066a7f  mov     rcx, rbx; struct CWindowData *
0x180066a82  call    ?ShouldAnimateShowWindow@CStoryboard@@SA_NPEBVCWindowData@@@Z; CStoryboard::ShouldAnimateShowWindow(CWindowData const *)
0x180066a87  test    al, al
0x180066a89  jz      short loc_180066A22
0x180066a8b  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180066a92  mov     rdx, rbx; struct CWindowData *
0x180066a95  mov     rcx, [rcx+0C0h]; this
0x180066a9c  call    ?EnsureSnapshot@CTransitionVisualController@@QEAAJPEAVCWindowData@@@Z; CTransitionVisualController::EnsureSnapshot(CWindowData *)
0x180066aa1  bts     dword ptr [rbx+2E8h], 1Ah
0x180066aa9  lea     r8, [rbp+arg_0]; struct CTransitionWindowSnapshot **
0x180066aad  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180066ab4  mov     rdx, [rbx+28h]; HWND
0x180066ab8  mov     [rbp+arg_0], 0
0x180066ac0  mov     rcx, [rcx+0C0h]; this
0x180066ac7  call    ?GetStoredSnapshotNoRef@CTransitionVisualController@@QEAAJPEAUHWND__@@PEAPEAVCTransitionWindowSnapshot@@@Z; CTransitionVisualController::GetStoredSnapshotNoRef(HWND__ *,CTransitionWindowSnapshot * *)
0x180066acc  test    eax, eax
0x180066ace  js      loc_180066A22
0x180066ad4  mov     rax, [rbp+arg_0]
0x180066ad8  mov     rcx, [rax+0D0h]
0x180066adf  mov     eax, [rbx+2E8h]
0x180066ae5  mov     rdx, [rcx+20h]
0x180066ae9  mov     [rdx+2E8h], eax
0x180066aef  jmp     loc_180066A22
0x180066af4  mov     rax, [rcx]
0x180066af7  mov     r8d, r12d
0x180066afa  mov     rdx, rbx
0x180066afd  mov     rax, [rax+68h]
0x180066b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b06  jmp     loc_180066A4F
0x180066b0b  mov     r8, [rdx+28h]
0x180066b0f  mov     r9d, r12d
0x180066b12  lea     rdx, UdwmSystemAnimation_WindowTarget
0x180066b19  call    McTemplateU0pd_EtwEventWriteTransfer
0x180066b1e  jmp     loc_180066959
0x180066b23  lea     rdx, [rbp+var_18]; retstr
0x180066b27  call    ?GetOutsideMarginsWithDropShadow@CTopLevelWindow@@QEBA?AU_MARGINS@@XZ; CTopLevelWindow::GetOutsideMarginsWithDropShadow(void)
0x180066b2c  mov     eax, [rbp+var_18.cxRightWidth]
0x180066b2f  sub     [r15+8], eax
0x180066b33  mov     eax, [rbp+var_18.cyTopHeight]
0x180066b36  add     [r15+4], eax
0x180066b3a  mov     ecx, [rbp+var_18.cxLeftWidth]
0x180066b3d  add     [r15], ecx
0x180066b40  mov     eax, [rbp+var_18.cyBottomHeight]
0x180066b43  sub     [r15+0Ch], eax
0x180066b47  jmp     loc_1800669D1
0x180066b4c  lea     rdx, [rbp+var_18]; retstr
0x180066b50  call    ?GetOutsideMarginsWithDropShadow@CTopLevelWindow@@QEBA?AU_MARGINS@@XZ; CTopLevelWindow::GetOutsideMarginsWithDropShadow(void)
0x180066b55  mov     eax, [rbp+var_18.cxRightWidth]
0x180066b58  sub     [r14+8], eax
0x180066b5c  mov     eax, [rbp+var_18.cyTopHeight]
0x180066b5f  add     [r14+4], eax
0x180066b63  mov     ecx, [rbp+var_18.cxLeftWidth]
0x180066b66  add     [r14], ecx
0x180066b69  mov     eax, [rbp+var_18.cyBottomHeight]
0x180066b6c  sub     [r14+0Ch], eax
0x180066b70  jmp     loc_1800669E1
0x180066b75  lea     rdx, [rbp+var_18]; retstr
0x180066b79  call    ?GetOutsideMarginsWithDropShadow@CTopLevelWindow@@QEBA?AU_MARGINS@@XZ; CTopLevelWindow::GetOutsideMarginsWithDropShadow(void)
0x180066b7e  mov     eax, [rbp+var_18.cxRightWidth]
0x180066b81  sub     [rsi+8], eax
0x180066b84  mov     eax, [rbp+var_18.cyTopHeight]
0x180066b87  add     [rsi+4], eax
0x180066b8a  mov     ecx, [rbp+var_18.cxLeftWidth]
0x180066b8d  add     [rsi], ecx
0x180066b8f  mov     eax, [rbp+var_18.cyBottomHeight]
0x180066b92  sub     [rsi+0Ch], eax
0x180066b95  jmp     loc_1800669F1
0x180066b9a  lea     rdx, [rbp+var_18]; retstr
0x180066b9e  call    ?GetOutsideMarginsWithDropShadow@CTopLevelWindow@@QEBA?AU_MARGINS@@XZ; CTopLevelWindow::GetOutsideMarginsWithDropShadow(void)
0x180066ba3  mov     eax, [rbp+var_18.cxRightWidth]
0x180066ba6  sub     [rdi+8], eax
0x180066ba9  mov     eax, [rbp+var_18.cyTopHeight]
0x180066bac  add     [rdi+4], eax
0x180066baf  mov     ecx, [rbp+var_18.cxLeftWidth]
0x180066bb2  add     [rdi], ecx
0x180066bb4  mov     eax, [rbp+var_18.cyBottomHeight]
0x180066bb7  sub     [rdi+0Ch], eax
0x180066bba  jmp     loc_180066A01
```
