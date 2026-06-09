# CActionsContextMenu::RunPopupMenu(tagPOINT,HWND__ *,uint *)

- ea: `0x18003f930`
- end: `0x18003fb68`
- name: `?RunPopupMenu@CActionsContextMenu@@UEAAJUtagPOINT@@PEAUHWND__@@PEAI@Z`
- size: `568`
- prototype: `int(CActionsContextMenu *__hidden this, struct tagPOINT, HWND, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002c7f0`
- `0x180031a20`
- `0x18003f930`
- `0x18003fb70`
- `0x18003fbc0`
- `0x180043c30`
- `0x1800446fc`
- `0x18006b3f8`
- `0x18006bd5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fa65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fb44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fa65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fb44`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18003f98b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18003f98b`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18003fb33`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18003fb33`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18003fa36`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18003fa36`
- `USER32!RegisterClassExW` at `0x18003f9cc`
- `USER32!RegisterClassExW` at `0x18003f9cc`
- `USER32!TrackPopupMenu` at `0x18003fb01`
- `USER32!TrackPopupMenu` at `0x18003fb01`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CActionsContextMenu::RunPopupMenu(HMENU *this, struct tagPOINT a2, HWND a3, unsigned int *a4)
{
  HWND Window; // rax
  const char *v8; // r9
  unsigned int LastError; // ebx
  HWND v11; // rbx
  int v12; // edi
  int IsThreadRTL; // eax
  HWND v14; // r8
  HWND hWnd; // [rsp+60h] [rbp-A0h] BYREF
  int x[2]; // [rsp+68h] [rbp-98h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-90h] BYREF
  _QWORD hData[5]; // [rsp+78h] [rbp-88h] BYREF
  char v19; // [rsp+A0h] [rbp-60h]
  WNDCLASSEXW v20; // [rsp+B0h] [rbp-50h] BYREF
  struct tagRECT Rect; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *(struct tagPOINT *)x = a2;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, this + 3);
  if ( a4 )
    *a4 = 0;
  Rect = 0;
  GetWindowRect(a3, &Rect);
  v20.cbSize = 80;
  memset_0(&v20.style, 0, 0x4Cu);
  v20.lpfnWndProc = (WNDPROC)CActionsContextMenu::_WndProc;
  v20.hInstance = &_ImageBase;
  v20.lpszClassName = L"ActionsMenuOwner";
  RegisterClassExW(&v20);
  Window = CreateWindowExW(
             0,
             L"ActionsMenuOwner",
             0,
             0x80000000,
             Rect.left + (Rect.right - Rect.left) / 2,
             Rect.top + (Rect.bottom - Rect.top) / 2,
             0,
             0,
             a3,
             0,
             &_ImageBase,
             0);
  hWnd = Window;
  if ( Window )
  {
    hData[4] = &hWnd;
    v19 = 1;
    memset(hData, 0, 32);
    ImmersiveContextMenuHelper::ApplyOwnerDrawToMenu(this[4], Window, (HWND)x, 1u, hData);
    v11 = hWnd;
    v12 = x[0];
    IsThreadRTL = Mirror_IsThreadRTL();
    *((_DWORD *)this + 10) = TrackPopupMenu(this[4], IsThreadRTL != 0 ? 33034 : 258, v12, x[1], 0, v11, 0);
    ImmersiveContextMenuHelper::RemoveOwnerDrawFromMenu(this[4], (HMENU)hWnd, v14);
    if ( a4 )
      *a4 = *((_DWORD *)this + 10);
    CSimplePointerArray<ContextMenuRenderingData,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>>::~CSimplePointerArray<ContextMenuRenderingData,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>>(hData);
    DestroyWindow(hWnd);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4C,
                  (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\actionsmenuprovider.cpp",
                  v8);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return LastError;
  }
}

```

## disassembly

```asm
0x18003f930  push    rbp
0x18003f932  push    rbx
0x18003f933  push    rsi
0x18003f934  push    rdi
0x18003f935  push    r14
0x18003f937  push    r15
0x18003f939  lea     rbp, [rsp-28h]
0x18003f93e  sub     rsp, 128h
0x18003f945  mov     rax, cs:__security_cookie
0x18003f94c  xor     rax, rsp
0x18003f94f  mov     [rbp+50h+var_40], rax
0x18003f953  mov     r14, r9
0x18003f956  mov     rbx, r8
0x18003f959  mov     rsi, rcx
0x18003f95c  mov     qword ptr [rsp+150h+x], rdx
0x18003f961  lea     rdx, [rcx+18h]
0x18003f965  lea     rcx, [rsp+150h+SRWLock]
0x18003f96a  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003f96f  nop
0x18003f970  test    r14, r14
0x18003f973  jz      short loc_18003F97C
0x18003f975  mov     dword ptr [r14], 0
0x18003f97c  xorps   xmm0, xmm0
0x18003f97f  movdqu  xmmword ptr [rbp+50h+Rect.left], xmm0
0x18003f984  lea     rdx, [rbp+50h+Rect]; lpRect
0x18003f988  mov     rcx, rbx; hWnd
0x18003f98b  call    cs:__imp_GetWindowRect
0x18003f991  mov     [rbp+50h+var_A0.cbSize], 50h ; 'P'
0x18003f998  xor     edx, edx; Val
0x18003f99a  lea     r8d, [rdx+4Ch]; Size
0x18003f99e  lea     rcx, [rbp+50h+var_A0.style]; void *
0x18003f9a2  call    memset_0
0x18003f9a7  lea     rax, ?_WndProc@CActionsContextMenu@@CA_JPEAUHWND__@@I_K_J@Z; CActionsContextMenu::_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18003f9ae  mov     [rbp+50h+var_A0.lpfnWndProc], rax
0x18003f9b2  lea     rdi, __ImageBase
0x18003f9b9  mov     [rbp+50h+var_A0.hInstance], rdi
0x18003f9bd  lea     r15, aActionsmenuown; "ActionsMenuOwner"
0x18003f9c4  mov     [rbp+50h+var_A0.lpszClassName], r15
0x18003f9c8  lea     rcx, [rbp+50h+var_A0]; WNDCLASSEXW *
0x18003f9cc  call    cs:__imp_RegisterClassExW
0x18003f9d2  mov     eax, [rbp+50h+Rect.bottom]
0x18003f9d5  sub     eax, [rbp+50h+Rect.top]
0x18003f9d8  cdq
0x18003f9d9  mov     r8d, 2
0x18003f9df  idiv    r8d
0x18003f9e2  mov     ecx, eax
0x18003f9e4  add     ecx, [rbp+50h+Rect.top]
0x18003f9e7  mov     eax, [rbp+50h+Rect.right]
0x18003f9ea  sub     eax, [rbp+50h+Rect.left]
0x18003f9ed  cdq
0x18003f9ee  idiv    r8d
0x18003f9f1  add     eax, [rbp+50h+Rect.left]
0x18003f9f4  mov     [rsp+150h+lpParam], 0; lpParam
0x18003f9fd  mov     [rsp+150h+hInstance], rdi; hInstance
0x18003fa02  mov     [rsp+150h+hMenu], 0; hMenu
0x18003fa0b  mov     [rsp+150h+hWndParent], rbx; hWndParent
0x18003fa10  mov     [rsp+150h+nHeight], 0; nHeight
0x18003fa18  mov     [rsp+150h+nWidth], 0; nWidth
0x18003fa20  mov     [rsp+150h+Y], ecx; Y
0x18003fa24  mov     [rsp+150h+X], eax; X
0x18003fa28  mov     r9d, 80000000h; dwStyle
0x18003fa2e  xor     r8d, r8d; lpWindowName
0x18003fa31  mov     rdx, r15; lpClassName
0x18003fa34  xor     ecx, ecx; dwExStyle
0x18003fa36  call    cs:__imp_CreateWindowExW
0x18003fa3c  mov     [rsp+150h+hWnd], rax
0x18003fa41  test    rax, rax
0x18003fa44  jnz     short loc_18003FA72
0x18003fa46  mov     rcx, [rbp+58h]; this
0x18003fa4a  lea     r8, aPcshellShellAp_7; "pcshell\\shell\\applicationframe\\frame"...
0x18003fa51  lea     edx, [rax+4Ch]; void *
0x18003fa54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003fa59  mov     ebx, eax
0x18003fa5b  mov     rcx, [rsp+150h+SRWLock]; SRWLock
0x18003fa60  test    rcx, rcx
0x18003fa63  jz      short loc_18003FA6B
0x18003fa65  call    cs:__imp_ReleaseSRWLockExclusive
0x18003fa6b  mov     eax, ebx
0x18003fa6d  jmp     loc_18003FB4C
0x18003fa72  lea     rcx, [rsp+150h+hWnd]
0x18003fa77  mov     [rbp+50h+var_B8], rcx
0x18003fa7b  mov     [rbp+50h+var_B0], 1
0x18003fa7f  mov     [rsp+150h+hData], 0
0x18003fa88  mov     [rbp+50h+var_D0], 0
0x18003fa90  mov     [rbp+50h+var_C8], 0
0x18003fa98  mov     [rbp+50h+var_C0], 0
0x18003faa0  lea     rcx, [rsp+150h+hData]
0x18003faa5  mov     qword ptr [rsp+150h+X], rcx; hData
0x18003faaa  mov     r9d, 1; int
0x18003fab0  lea     r8, [rsp+150h+x]; int
0x18003fab5  mov     rdx, rax; int
0x18003fab8  mov     rcx, [rsi+20h]; int
0x18003fabc  call    ?ApplyOwnerDrawToMenu@ImmersiveContextMenuHelper@@YAJPEAUHMENU__@@PEAUHWND__@@PEAUtagPOINT@@W4ImmersiveContextMenuOptions@@AEAV?$CSimplePointerArrayNewMem@UContextMenuRenderingData@@V?$CSimpleArrayStandardCompareHelper@PEAUContextMenuRenderingData@@@@@@@Z; ImmersiveContextMenuHelper::ApplyOwnerDrawToMenu(HMENU__ *,HWND__ *,tagPOINT *,ImmersiveContextMenuOptions,CSimplePointerArrayNewMem<ContextMenuRenderingData,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>> &)
0x18003fac1  mov     rbx, [rsp+150h+hWnd]
0x18003fac6  mov     edi, [rsp+150h+x]
0x18003faca  call    ?Mirror_IsThreadRTL@@YAHXZ; Mirror_IsThreadRTL(void)
0x18003facf  neg     eax
0x18003fad1  sbb     edx, edx
0x18003fad3  and     edx, 8008h
0x18003fad9  add     edx, 102h; uFlags
0x18003fadf  mov     qword ptr [rsp+150h+nWidth], 0; prcRect
0x18003fae8  mov     qword ptr [rsp+150h+Y], rbx; hWnd
0x18003faed  mov     [rsp+150h+X], 0; nReserved
0x18003faf5  mov     r9d, [rsp+150h+x+4]; y
0x18003fafa  mov     r8d, edi; x
0x18003fafd  mov     rcx, [rsi+20h]; hMenu
0x18003fb01  call    cs:__imp_TrackPopupMenu
0x18003fb07  mov     [rsi+28h], eax
0x18003fb0a  mov     rdx, [rsp+150h+hWnd]; hWnd
0x18003fb0f  mov     rcx, [rsi+20h]; this
0x18003fb13  call    ?RemoveOwnerDrawFromMenu@ImmersiveContextMenuHelper@@YAXPEAUHMENU__@@PEAUHWND__@@@Z; ImmersiveContextMenuHelper::RemoveOwnerDrawFromMenu(HMENU__ *,HWND__ *)
0x18003fb18  test    r14, r14
0x18003fb1b  jz      short loc_18003FB23
0x18003fb1d  mov     eax, [rsi+28h]
0x18003fb20  mov     [r14], eax
0x18003fb23  lea     rcx, [rsp+150h+hData]
0x18003fb28  call    ??1?$CSimplePointerArray@UContextMenuRenderingData@@VCTContainer_PolicyNewMem@@V?$CSimpleArrayStandardCompareHelper@PEAUContextMenuRenderingData@@@@@@QEAA@XZ; CSimplePointerArray<ContextMenuRenderingData,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>>::~CSimplePointerArray<ContextMenuRenderingData,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>>(void)
0x18003fb2d  nop
0x18003fb2e  mov     rcx, [rsp+150h+hWnd]; hWnd
0x18003fb33  call    cs:__imp_DestroyWindow
0x18003fb39  nop
0x18003fb3a  mov     rcx, [rsp+150h+SRWLock]; SRWLock
0x18003fb3f  test    rcx, rcx
0x18003fb42  jz      short loc_18003FB4A
0x18003fb44  call    cs:__imp_ReleaseSRWLockExclusive
0x18003fb4a  xor     eax, eax
0x18003fb4c  mov     rcx, [rbp+50h+var_40]
0x18003fb50  xor     rcx, rsp; StackCookie
0x18003fb53  call    __security_check_cookie
0x18003fb58  add     rsp, 128h
0x18003fb5f  pop     r15
0x18003fb61  pop     r14
0x18003fb63  pop     rdi
0x18003fb64  pop     rsi
0x18003fb65  pop     rbx
0x18003fb66  pop     rbp
0x18003fb67  retn
```
