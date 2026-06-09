# LineScroller::OnEvent(DirectUI::Event *)

- ea: `0x18007c460`
- end: `0x18007c83e`
- name: `?OnEvent@LineScroller@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `990`
- prototype: `void __fastcall(LineScroller *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800174e8`
- `0x180049c08`
- `0x18004c82c`
- `0x18007bc74`
- `0x18007bdf8`
- `0x18007bfa4`
- `0x18007c460`
- `0x18007c844`
- `0x18007c8d8`
- `0x18007c944`
- `0x18007ca08`
- `0x18007ca84`
- `0x1800a0848`
- `0x1800a08a8`
- `0x1800a0908`
- `0x1800a0968`
- `0x1801e4538`
- `0x1801e8e84`
- `0x1801e990c`
- `0x1801e9960`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18007c829`
- `SHCORE!SHCreateThread` at `0x18007c829`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18007c53d`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18007c53d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c513`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c513`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007c7c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007c7c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007c7b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007c7ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007c7b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007c7ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c833`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007c7ef`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007c7ef`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007c7ae`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007c7ae`
- `USER32!RedrawWindow` at `0x18007c6ca`
- `USER32!RedrawWindow` at `0x18007c6ca`
- `DUI70!?KeyboardNavigate@Element@DirectUI@@SA?AVUID@@XZ` at `0x18007c492`
- `DUI70!?KeyboardNavigate@Element@DirectUI@@SA?AVUID@@XZ` at `0x18007c492`
- `DUI70!?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18007c4be`
- `DUI70!?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18007c4be`
- `DUI70!?IsHosted@Element@DirectUI@@QEAA_NXZ` at `0x18007c574`
- `DUI70!?IsHosted@Element@DirectUI@@QEAA_NXZ` at `0x18007c574`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007c690`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18007c690`
- `DUI70!?Scroll@BaseScrollBar@DirectUI@@SA?AVUID@@XZ` at `0x18007c4ee`
- `DUI70!?Scroll@BaseScrollBar@DirectUI@@SA?AVUID@@XZ` at `0x18007c4ee`

## pseudocode

```c
void __fastcall LineScroller::OnEvent(LineScroller *this, struct DirectUI::Event *a2)
{
  int v2; // eax
  char **v5; // rax
  unsigned int v6; // edx
  char *v7; // rcx
  __int16 **v8; // rax
  __int16 *v9; // rcx
  bool v10; // zf
  __int16 *v11; // rax
  struct DirectUI::Element *v12; // rbx
  int v13; // edx
  __int64 v14; // rax
  int v15; // edx
  struct DirectUI::Element *Root; // rax
  __int64 v17; // rax
  HWND v18; // rax
  __int64 v19; // rax
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // r8
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v26; // rax
  _QWORD pData[2]; // [rsp+40h] [rbp-10h] BYREF
  int Data; // [rsp+88h] [rbp+38h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+40h] BYREF

  v2 = *((_DWORD *)a2 + 5);
  if ( v2 != 1 )
  {
    if ( v2 )
    {
      if ( v2 != 2 )
        goto LABEL_4;
      v8 = (__int16 **)DirectUI::BaseScrollBar::Scroll(&Data);
      v9 = (__int16 *)*((_QWORD *)a2 + 1);
      if ( v9 == *v8 )
      {
        v13 = *((_DWORD *)this + 152);
        v14 = 336;
        if ( v13 != 2 )
          v14 = 368;
        if ( *(_QWORD *)a2 == *(_QWORD *)((char *)this + v14) )
        {
          LineScroller::_UpdateAnchorFromScrollbar(this);
          if ( *((_DWORD *)this + 144) )
            LineScroller::_UpdateScrollTips(this);
          LineScroller::_DeferPaintAfterUpdate(this);
        }
        else
        {
          if ( v13 == 2 )
            LineScroller::SetRealXTarget(this, 0);
          else
            LineScroller::SetRealYTarget(this, 0);
          v15 = *((_DWORD *)a2 + 8);
          if ( *((_DWORD *)this + 152) == 2 )
            LineScroller::SetRealXAnchor(this, v15);
          else
            LineScroller::SetRealYAnchor(this, v15);
        }
        if ( *((_DWORD *)this + 152) == 2 && *(_QWORD *)a2 == *((_QWORD *)this + 46) )
          LineScroller::_SyncHeaderToScrollbar(this);
        *((_DWORD *)this + 161) = 0;
        goto LABEL_16;
      }
      v10 = v9 == (__int16 *)UIBase::LayoutChange[0];
    }
    else
    {
      if ( !DirectUI::Element::IsHosted(this) )
        goto LABEL_4;
      v11 = (__int16 *)*((_QWORD *)a2 + 1);
      if ( v11 == (__int16 *)LineScroller::PaintAfterUpdate )
      {
        *((_DWORD *)this + 140) = 0;
        Root = DirectUI::Element::GetRoot(this);
        v17 = element_cast<DirectUI::HWNDElement>(Root);
        if ( v17 )
        {
          v18 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 360LL))(v17);
          RedrawWindow(v18, 0, 0, 0x180u);
        }
        goto LABEL_16;
      }
      if ( v11 == (__int16 *)LineScroller::DelayMakeVisibleEvent )
      {
        LineScroller::_OnDelayMakeVisible(this);
LABEL_16:
        *((_BYTE *)a2 + 16) = 1;
        goto LABEL_4;
      }
      v10 = v11 == (__int16 *)UIBase::LayoutChange[0];
    }
    if ( !v10 )
      goto LABEL_4;
    if ( *((_DWORD *)this + 141) )
    {
      g_dwReentrantThreadId = GetCurrentThreadId();
      g_ReentrantCheck = 2;
      if ( !SHRegGetBoolUSValueW(
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
              L"ShellViewReentered",
              0,
              0) )
      {
        Data = 1;
        RegSetKeyValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
          L"ShellViewReentered",
          4u,
          &Data,
          4u);
        TargetHandle = 0;
        CurrentProcess = GetCurrentProcess();
        CurrentThread = GetCurrentThread();
        v26 = GetCurrentProcess();
        if ( DuplicateHandle(v26, CurrentThread, CurrentProcess, &TargetHandle, 0x1FFFFFu, 1, 0) )
        {
          pData[0] = TargetHandle;
          pData[1] = ComputeStackHash();
          SHCreateThread(
            DirectUI::PatternProvider<UIItemsViewScrollProvider,IScrollProvider,5>::GetProxyCreator,
            pData,
            0x200u,
            s_SendWERForReentrancy);
          CloseHandle(TargetHandle);
        }
      }
    }
    if ( *((_DWORD *)a2 + 8) == 1 )
    {
      *((_QWORD *)this + 62) = 0;
      *((_QWORD *)this + 63) = 0;
      LineScroller::_EnsureRealizePass(this);
    }
    else if ( !*((_DWORD *)a2 + 8) )
    {
      LineScroller::_OnScrollTickCountChanged(this);
    }
    goto LABEL_16;
  }
  v5 = (char **)((__int64 (__fastcall *)(int *))DirectUI::Element::KeyboardNavigate)(&Data);
  v7 = (char *)*((_QWORD *)a2 + 1);
  if ( v7 == *v5 )
  {
    v12 = *(struct DirectUI::Element **)a2;
    *((_DWORD *)this + 143) = 0;
    CSafeElementPtr<ItemRowLayout>::Unassign((char *)this + 544);
    *((_QWORD *)this + 67) = 0;
    *((_DWORD *)this + 143) = 1;
    LineScroller::_RecordMakeVisible(this, v12);
    LineScroller::EndMakeVisibleBatch(this);
  }
  else if ( v7 == CountedScrollEventType )
  {
    v19 = 336;
    if ( *((_DWORD *)this + 152) != 2 )
      v19 = 368;
    if ( *(_QWORD *)a2 == *(_QWORD *)((char *)this + v19) )
    {
      v20 = *((_DWORD *)a2 + 9);
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            if ( v22 == 1 )
              LineScroller::ScrollPageDown(this, v6);
          }
          else
          {
            LineScroller::ScrollPageUp(this, v6);
          }
          goto LABEL_53;
        }
        v23 = 1;
      }
      else
      {
        v23 = 0xFFFFFFFFLL;
      }
      LineScroller::_ScrollLineUpDown(this, *((unsigned int *)a2 + 8), v23);
LABEL_53:
      LineScroller::_DeferPaintAfterUpdate(this);
      goto LABEL_16;
    }
  }
LABEL_4:
  if ( !*((_BYTE *)a2 + 16) )
    DirectUI::Element::OnEvent(this, a2);
}

```

## disassembly

```asm
0x18007c460  mov     [rsp-28h+arg_0], rbx
0x18007c465  mov     [rsp-28h+arg_18], rsi
0x18007c46a  push    rbp
0x18007c46b  push    rdi
0x18007c46c  push    r12
0x18007c46e  push    r14
0x18007c470  push    r15
0x18007c472  mov     rbp, rsp
0x18007c475  sub     rsp, 50h
0x18007c479  mov     eax, [rdx+14h]
0x18007c47c  xor     r15d, r15d
0x18007c47f  mov     r14, rdx
0x18007c482  mov     rsi, rcx
0x18007c485  lea     r12d, [r15+1]
0x18007c489  cmp     eax, r12d
0x18007c48c  jnz     short loc_18007C4DD
0x18007c48e  lea     rcx, [rbp+Data]
0x18007c492  call    cs:__imp_?KeyboardNavigate@Element@DirectUI@@SA?AVUID@@XZ; DirectUI::Element::KeyboardNavigate(void)
0x18007c498  mov     rcx, [r14+8]
0x18007c49c  cmp     rcx, [rax]
0x18007c49f  jz      loc_18007C5AC
0x18007c4a5  cmp     rcx, cs:?CountedScrollEventType@@3VUID@@A; UID CountedScrollEventType
0x18007c4ac  jz      loc_18007C708
0x18007c4b2  cmp     [r14+10h], r15b
0x18007c4b6  jnz     short loc_18007C4C4
0x18007c4b8  mov     rdx, r14
0x18007c4bb  mov     rcx, rsi
0x18007c4be  call    cs:__imp_?OnEvent@Element@DirectUI@@UEAAXPEAUEvent@2@@Z; DirectUI::Element::OnEvent(DirectUI::Event *)
0x18007c4c4  lea     r11, [rsp+50h+var_s0]
0x18007c4c9  mov     rbx, [r11+30h]
0x18007c4cd  mov     rsi, [r11+48h]
0x18007c4d1  mov     rsp, r11
0x18007c4d4  pop     r15
0x18007c4d6  pop     r14
0x18007c4d8  pop     r12
0x18007c4da  pop     rdi
0x18007c4db  pop     rbp
0x18007c4dc  retn
0x18007c4dd  test    eax, eax
0x18007c4df  jz      loc_18007C574
0x18007c4e5  cmp     eax, 2
0x18007c4e8  jnz     short loc_18007C4B2
0x18007c4ea  lea     rcx, [rbp+Data]
0x18007c4ee  call    cs:__imp_?Scroll@BaseScrollBar@DirectUI@@SA?AVUID@@XZ; DirectUI::BaseScrollBar::Scroll(void)
0x18007c4f4  mov     rcx, [r14+8]
0x18007c4f8  cmp     rcx, [rax]
0x18007c4fb  jz      loc_18007C5FF
0x18007c501  cmp     rcx, cs:?LayoutChange@UIBase@@2VUID@@A; UID UIBase::LayoutChange
0x18007c508  jnz     short loc_18007C4B2
0x18007c50a  cmp     [rsi+234h], r15d
0x18007c511  jz      short loc_18007C54B
0x18007c513  call    cs:__imp_GetCurrentThreadId
0x18007c519  mov     cs:?g_dwReentrantThreadId@@3KC, eax; ulong volatile g_dwReentrantThreadId
0x18007c51f  xor     r9d, r9d; fDefault
0x18007c522  lea     rdx, ValueName; "ShellViewReentered"
0x18007c529  mov     cs:?g_ReentrantCheck@@3W4REENTRANCYCHECKTHATFAILED@@C, 2; REENTRANCYCHECKTHATFAILED volatile g_ReentrantCheck
0x18007c533  xor     r8d, r8d; fIgnoreHKCU
0x18007c536  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007c53d  call    cs:__imp_SHRegGetBoolUSValueW
0x18007c543  test    eax, eax
0x18007c545  jz      loc_18007C781
0x18007c54b  cmp     [r14+20h], r12d
0x18007c54f  jnz     loc_18007C5E8
0x18007c555  mov     [rsi+1F0h], r15
0x18007c55c  mov     rcx, rsi; this
0x18007c55f  mov     [rsi+1F8h], r15
0x18007c566  call    ?_EnsureRealizePass@LineScroller@@AEAAXXZ; LineScroller::_EnsureRealizePass(void)
0x18007c56b  mov     [r14+10h], r12b
0x18007c56f  jmp     loc_18007C4B2
0x18007c574  call    cs:__imp_?IsHosted@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsHosted(void)
0x18007c57a  test    al, al
0x18007c57c  jz      loc_18007C4B2
0x18007c582  mov     rax, [r14+8]
0x18007c586  cmp     rax, cs:?PaintAfterUpdate@LineScroller@@0VUID@@A; UID LineScroller::PaintAfterUpdate
0x18007c58d  jz      loc_18007C686
0x18007c593  cmp     rax, cs:?DelayMakeVisibleEvent@LineScroller@@0VUID@@A; UID LineScroller::DelayMakeVisibleEvent
0x18007c59a  jz      loc_18007C652
0x18007c5a0  cmp     rax, cs:?LayoutChange@UIBase@@2VUID@@A; UID UIBase::LayoutChange
0x18007c5a7  jmp     loc_18007C508
0x18007c5ac  mov     rbx, [r14]
0x18007c5af  lea     rcx, [rsi+220h]
0x18007c5b6  mov     [rsi+23Ch], r15d
0x18007c5bd  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x18007c5c2  mov     rdx, rbx; struct DirectUI::Element *
0x18007c5c5  mov     [rsi+218h], r15
0x18007c5cc  mov     rcx, rsi; this
0x18007c5cf  mov     [rsi+23Ch], r12d
0x18007c5d6  call    ?_RecordMakeVisible@LineScroller@@AEAAXPEAVElement@DirectUI@@@Z; LineScroller::_RecordMakeVisible(DirectUI::Element *)
0x18007c5db  mov     rcx, rsi; this
0x18007c5de  call    ?EndMakeVisibleBatch@LineScroller@@QEAAXXZ; LineScroller::EndMakeVisibleBatch(void)
0x18007c5e3  jmp     loc_18007C4B2
0x18007c5e8  cmp     [r14+20h], r15d
0x18007c5ec  jnz     loc_18007C56B
0x18007c5f2  mov     rcx, rsi; this
0x18007c5f5  call    ?_OnScrollTickCountChanged@LineScroller@@AEAAXXZ; LineScroller::_OnScrollTickCountChanged(void)
0x18007c5fa  jmp     loc_18007C56B
0x18007c5ff  mov     edx, [rsi+260h]
0x18007c605  mov     eax, 150h
0x18007c60a  cmp     edx, 2
0x18007c60d  lea     ecx, [rax+20h]
0x18007c610  cmovnz  eax, ecx
0x18007c613  mov     rcx, rsi; this
0x18007c616  mov     rax, [rax+rsi]
0x18007c61a  cmp     [r14], rax
0x18007c61d  jnz     short loc_18007C65F
0x18007c61f  call    ?_UpdateAnchorFromScrollbar@LineScroller@@AEAAXXZ; LineScroller::_UpdateAnchorFromScrollbar(void)
0x18007c624  cmp     [rsi+240h], r15d
0x18007c62b  jnz     loc_18007C774
0x18007c631  mov     rcx, rsi; this
0x18007c634  call    ?_DeferPaintAfterUpdate@LineScroller@@AEAAXXZ; LineScroller::_DeferPaintAfterUpdate(void)
0x18007c639  cmp     dword ptr [rsi+260h], 2
0x18007c640  jz      loc_18007C6D5
0x18007c646  mov     [rsi+284h], r15d
0x18007c64d  jmp     loc_18007C56B
0x18007c652  mov     rcx, rsi; this
0x18007c655  call    ?_OnDelayMakeVisible@LineScroller@@AEAAXXZ; LineScroller::_OnDelayMakeVisible(void)
0x18007c65a  jmp     loc_18007C56B
0x18007c65f  cmp     edx, 2
0x18007c662  jnz     loc_18007C6F2
0x18007c668  xor     edx, edx; int
0x18007c66a  call    ?SetRealXTarget@LineScroller@@QEAAJH@Z; LineScroller::SetRealXTarget(int)
0x18007c66f  cmp     dword ptr [rsi+260h], 2
0x18007c676  mov     rcx, rsi; this
0x18007c679  mov     edx, [r14+20h]; int
0x18007c67d  jnz     short loc_18007C6FE
0x18007c67f  call    ?SetRealXAnchor@LineScroller@@QEAAJH@Z; LineScroller::SetRealXAnchor(int)
0x18007c684  jmp     short loc_18007C639
0x18007c686  mov     rcx, rsi
0x18007c689  mov     [rsi+230h], r15d
0x18007c690  call    cs:__imp_?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetRoot(void)
0x18007c696  mov     rcx, rax
0x18007c699  call    ??$element_cast@VHWNDElement@DirectUI@@@@YAPEAVHWNDElement@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::HWNDElement>(DirectUI::Element *)
0x18007c69e  mov     rdx, rax
0x18007c6a1  test    rax, rax
0x18007c6a4  jz      loc_18007C56B
0x18007c6aa  mov     rcx, [rax]
0x18007c6ad  mov     rax, [rcx+168h]
0x18007c6b4  mov     rcx, rdx
0x18007c6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c6bc  mov     rcx, rax; hWnd
0x18007c6bf  mov     r9d, 180h; flags
0x18007c6c5  xor     r8d, r8d; hrgnUpdate
0x18007c6c8  xor     edx, edx; lprcUpdate
0x18007c6ca  call    cs:__imp_RedrawWindow
0x18007c6d0  jmp     loc_18007C56B
0x18007c6d5  mov     rax, [rsi+170h]
0x18007c6dc  cmp     [r14], rax
0x18007c6df  jnz     loc_18007C646
0x18007c6e5  mov     rcx, rsi; this
0x18007c6e8  call    ?_SyncHeaderToScrollbar@LineScroller@@AEAAXXZ; LineScroller::_SyncHeaderToScrollbar(void)
0x18007c6ed  jmp     loc_18007C646
0x18007c6f2  xor     edx, edx; int
0x18007c6f4  call    ?SetRealYTarget@LineScroller@@QEAAJH@Z; LineScroller::SetRealYTarget(int)
0x18007c6f9  jmp     loc_18007C66F
0x18007c6fe  call    ?SetRealYAnchor@LineScroller@@QEAAJH@Z; LineScroller::SetRealYAnchor(int)
0x18007c703  jmp     loc_18007C639
0x18007c708  cmp     dword ptr [rsi+260h], 2
0x18007c70f  mov     eax, 150h
0x18007c714  lea     ecx, [rax+20h]
0x18007c717  cmovnz  eax, ecx
0x18007c71a  mov     rax, [rax+rsi]
0x18007c71e  cmp     [r14], rax
0x18007c721  jnz     loc_18007C4B2
0x18007c727  mov     ecx, [r14+24h]
0x18007c72b  test    ecx, ecx
0x18007c72d  jz      short loc_18007C748
0x18007c72f  sub     ecx, r12d
0x18007c732  jz      short loc_18007C765
0x18007c734  sub     ecx, r12d
0x18007c737  jz      short loc_18007C76A
0x18007c739  cmp     ecx, r12d
0x18007c73c  jnz     short loc_18007C758
0x18007c73e  mov     rcx, rsi; this
0x18007c741  call    ?ScrollPageDown@LineScroller@@QEAAXI@Z; LineScroller::ScrollPageDown(uint)
0x18007c746  jmp     short loc_18007C758
0x18007c748  or      r8d, 0FFFFFFFFh
0x18007c74c  mov     edx, [r14+20h]
0x18007c750  mov     rcx, rsi
0x18007c753  call    ?_ScrollLineUpDown@LineScroller@@AEAAXHW4SCROLLDIR@@@Z; LineScroller::_ScrollLineUpDown(int,SCROLLDIR)
0x18007c758  mov     rcx, rsi; this
0x18007c75b  call    ?_DeferPaintAfterUpdate@LineScroller@@AEAAXXZ; LineScroller::_DeferPaintAfterUpdate(void)
0x18007c760  jmp     loc_18007C56B
0x18007c765  mov     r8d, r12d
0x18007c768  jmp     short loc_18007C74C
0x18007c76a  mov     rcx, rsi; this
0x18007c76d  call    ?ScrollPageUp@LineScroller@@QEAAXI@Z; LineScroller::ScrollPageUp(uint)
0x18007c772  jmp     short loc_18007C758
0x18007c774  mov     rcx, rsi; this
0x18007c777  call    ?_UpdateScrollTips@LineScroller@@AEAAXXZ; LineScroller::_UpdateScrollTips(void)
0x18007c77c  jmp     loc_18007C631
0x18007c781  mov     r9d, 4; dwType
0x18007c787  mov     [rbp+Data], r12d
0x18007c78b  lea     rax, [rbp+Data]
0x18007c78f  mov     [rsp+50h+cbData], r9d; cbData
0x18007c794  lea     r8, ValueName; "ShellViewReentered"
0x18007c79b  mov     [rsp+50h+lpData], rax; lpData
0x18007c7a0  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007c7a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007c7ae  call    cs:__imp_RegSetKeyValueW
0x18007c7b4  mov     [rbp+TargetHandle], r15
0x18007c7b8  call    cs:__imp_GetCurrentProcess
0x18007c7be  mov     rdi, rax
0x18007c7c1  call    cs:__imp_GetCurrentThread
0x18007c7c7  mov     rbx, rax
0x18007c7ca  call    cs:__imp_GetCurrentProcess
0x18007c7d0  mov     [rsp+50h+dwOptions], r15d; dwOptions
0x18007c7d5  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18007c7d9  mov     rcx, rax; hSourceProcessHandle
0x18007c7dc  mov     [rsp+50h+cbData], r12d; bInheritHandle
0x18007c7e1  mov     r8, rdi; hTargetProcessHandle
0x18007c7e4  mov     dword ptr [rsp+50h+lpData], 1FFFFFh; dwDesiredAccess
0x18007c7ec  mov     rdx, rbx; hSourceHandle
0x18007c7ef  call    cs:__imp_DuplicateHandle
0x18007c7f5  test    eax, eax
0x18007c7f7  jz      loc_18007C54B
0x18007c7fd  mov     rax, [rbp+TargetHandle]
0x18007c801  mov     [rbp+pData], rax
0x18007c805  mov     [rbp+var_8], r15
0x18007c809  call    ?ComputeStackHash@@YAKXZ; ComputeStackHash(void)
0x18007c80e  lea     r9, ?s_SendWERForReentrancy@@YAKPEAX@Z; pfnCallback
0x18007c815  mov     dword ptr [rbp+var_8], eax
0x18007c818  mov     r8d, 200h; flags
0x18007c81e  lea     rdx, [rbp+pData]; pData
0x18007c822  lea     rcx, ?GetProxyCreator@?$PatternProvider@VUIItemsViewScrollProvider@@UIScrollProvider@@$04@DirectUI@@UEAAP6APEAVProviderProxy@2@PEAVElement@2@@ZXZ; pfnThreadProc
0x18007c829  call    cs:__imp_SHCreateThread
0x18007c82f  mov     rcx, [rbp+TargetHandle]; hObject
0x18007c833  call    cs:__imp_CloseHandle
0x18007c839  jmp     loc_18007C54B
```
