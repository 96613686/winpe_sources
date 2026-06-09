# CFrameWnd::SetHelpCapture(tagPOINT,int *)

- ea: `0x18002fc20`
- end: `0x18002fd49`
- name: `?SetHelpCapture@CFrameWnd@@IEAAPEAUHWND__@@UtagPOINT@@PEAH@Z`
- size: `297`
- prototype: `HWND(CFrameWnd *__hidden this, struct tagPOINT, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180043ae0`
- `0x180043f20`

## callees

- `0x180013a90`
- `0x180014310`
- `0x180019ca0`
- `0x18002fc20`
- `0x18002fd50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fc88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fc88`
- `USER32!GetCapture` at `0x18002fc4a`
- `USER32!GetCapture` at `0x18002fc4a`
- `USER32!ReleaseCapture` at `0x18002fd0c`
- `USER32!ReleaseCapture` at `0x18002fd1a`
- `USER32!ReleaseCapture` at `0x18002fd0c`
- `USER32!ReleaseCapture` at `0x18002fd1a`
- `USER32!SetCursor` at `0x18002fd27`
- `USER32!SetCursor` at `0x18002fd27`
- `USER32!GetDesktopWindow` at `0x18002fcac`
- `USER32!GetDesktopWindow` at `0x18002fcac`
- `USER32!SetCapture` at `0x18002fceb`
- `USER32!SetCapture` at `0x18002fceb`
- `USER32!GetWindowThreadProcessId` at `0x18002fc9b`
- `USER32!GetWindowThreadProcessId` at `0x18002fc9b`

## pseudocode

```c
HWND __fastcall CFrameWnd::SetHelpCapture(CFrameWnd *this, struct tagPOINT a2, int *a3)
{
  HWND Capture; // rsi
  struct CWnd *v8; // rax
  HWND v9; // rbx
  CWnd *ActiveWindow; // rax
  struct CWnd *v11; // r15
  int v12; // r12d
  DWORD CurrentThreadId; // r13d
  DWORD WindowThreadProcessId; // ebp
  HWND v15; // rcx
  HCURSOR v16; // rcx
  HWND v17; // rax
  struct CWnd *TopLevelParent; // [rsp+70h] [rbp+8h]

  if ( !*((_DWORD *)this + 39) )
    return 0;
  Capture = GetCapture();
  v8 = CWnd::WindowFromPoint(a2);
  if ( v8 )
    v9 = (HWND)*((_QWORD *)v8 + 8);
  else
    v9 = 0;
  TopLevelParent = CWnd::GetTopLevelParent(v8);
  ActiveWindow = CWnd::GetActiveWindow();
  v11 = CWnd::GetTopLevelParent(ActiveWindow);
  v12 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( v9 )
    WindowThreadProcessId = GetWindowThreadProcessId(v9, 0);
  else
    WindowThreadProcessId = 0;
  if ( !v11 || v9 == GetDesktopWindow() )
  {
    if ( Capture == *((HWND *)this + 8) )
      ReleaseCapture();
    v16 = qword_180131A10;
    goto LABEL_26;
  }
  if ( !v9 || CurrentThreadId != WindowThreadProcessId || !AfxIsDescendant(*((HWND *)this + 8), v9) )
  {
    v17 = 0;
    if ( CurrentThreadId == WindowThreadProcessId )
      v17 = v9;
    v9 = v17;
    if ( Capture == *((HWND *)this + 8) )
      ReleaseCapture();
    goto LABEL_27;
  }
  v12 = 1;
  if ( v11 == TopLevelParent )
  {
    v15 = (HWND)*((_QWORD *)this + 8);
    if ( Capture != v15 )
      SetCapture(v15);
    v16 = hCursor;
LABEL_26:
    SetCursor(v16);
    goto LABEL_27;
  }
  v9 = 0;
LABEL_27:
  if ( a3 )
    *a3 = v12;
  return v9;
}

```

## disassembly

```asm
0x18002fc20  push    rbx
0x18002fc22  push    rbp
0x18002fc23  push    rsi
0x18002fc24  push    rdi
0x18002fc25  push    r12
0x18002fc27  push    r13
0x18002fc29  push    r14
0x18002fc2b  push    r15
0x18002fc2d  sub     rsp, 28h
0x18002fc31  cmp     dword ptr [rcx+9Ch], 0
0x18002fc38  mov     r14, r8
0x18002fc3b  mov     rbx, rdx
0x18002fc3e  mov     rdi, rcx
0x18002fc41  jnz     short loc_18002FC4A
0x18002fc43  xor     eax, eax
0x18002fc45  jmp     loc_18002FD38
0x18002fc4a  call    cs:__imp_GetCapture
0x18002fc50  mov     rcx, rbx; struct tagPOINT
0x18002fc53  mov     rsi, rax
0x18002fc56  call    ?WindowFromPoint@CWnd@@SAPEAV1@UtagPOINT@@@Z; CWnd::WindowFromPoint(tagPOINT)
0x18002fc5b  test    rax, rax
0x18002fc5e  jnz     short loc_18002FC64
0x18002fc60  xor     ebx, ebx
0x18002fc62  jmp     short loc_18002FC68
0x18002fc64  mov     rbx, [rax+40h]
0x18002fc68  mov     rcx, rax; this
0x18002fc6b  call    ?GetTopLevelParent@CWnd@@QEBAPEAV1@XZ; CWnd::GetTopLevelParent(void)
0x18002fc70  mov     [rsp+68h+arg_0], rax
0x18002fc75  call    ?GetActiveWindow@CWnd@@SAPEAV1@XZ; CWnd::GetActiveWindow(void)
0x18002fc7a  mov     rcx, rax; this
0x18002fc7d  call    ?GetTopLevelParent@CWnd@@QEBAPEAV1@XZ; CWnd::GetTopLevelParent(void)
0x18002fc82  mov     r15, rax
0x18002fc85  xor     r12d, r12d
0x18002fc88  call    cs:__imp_GetCurrentThreadId
0x18002fc8e  mov     r13d, eax
0x18002fc91  test    rbx, rbx
0x18002fc94  jz      short loc_18002FCA5
0x18002fc96  xor     edx, edx; lpdwProcessId
0x18002fc98  mov     rcx, rbx; hWnd
0x18002fc9b  call    cs:__imp_GetWindowThreadProcessId
0x18002fca1  mov     ebp, eax
0x18002fca3  jmp     short loc_18002FCA7
0x18002fca5  xor     ebp, ebp
0x18002fca7  test    r15, r15
0x18002fcaa  jz      short loc_18002FD14
0x18002fcac  call    cs:__imp_GetDesktopWindow
0x18002fcb2  cmp     rbx, rax
0x18002fcb5  jz      short loc_18002FD14
0x18002fcb7  test    rbx, rbx
0x18002fcba  jz      short loc_18002FCFA
0x18002fcbc  cmp     r13d, ebp
0x18002fcbf  jnz     short loc_18002FCFA
0x18002fcc1  mov     rcx, [rdi+40h]; HWND
0x18002fcc5  mov     rdx, rbx; HWND
0x18002fcc8  call    ?AfxIsDescendant@@YAHPEAUHWND__@@0@Z; AfxIsDescendant(HWND__ *,HWND__ *)
0x18002fccd  test    eax, eax
0x18002fccf  jz      short loc_18002FCFA
0x18002fcd1  mov     r12d, 1
0x18002fcd7  cmp     r15, [rsp+68h+arg_0]
0x18002fcdc  jz      short loc_18002FCE2
0x18002fcde  xor     ebx, ebx
0x18002fce0  jmp     short loc_18002FD2D
0x18002fce2  mov     rcx, [rdi+40h]; hWnd
0x18002fce6  cmp     rsi, rcx
0x18002fce9  jz      short loc_18002FCF1
0x18002fceb  call    cs:__imp_SetCapture
0x18002fcf1  mov     rcx, cs:hCursor
0x18002fcf8  jmp     short loc_18002FD27
0x18002fcfa  xor     eax, eax
0x18002fcfc  cmp     r13d, ebp
0x18002fcff  cmovz   rax, rbx
0x18002fd03  mov     rbx, rax
0x18002fd06  cmp     rsi, [rdi+40h]
0x18002fd0a  jnz     short loc_18002FD2D
0x18002fd0c  call    cs:__imp_ReleaseCapture
0x18002fd12  jmp     short loc_18002FD2D
0x18002fd14  cmp     rsi, [rdi+40h]
0x18002fd18  jnz     short loc_18002FD20
0x18002fd1a  call    cs:__imp_ReleaseCapture
0x18002fd20  mov     rcx, cs:qword_180131A10; hCursor
0x18002fd27  call    cs:__imp_SetCursor
0x18002fd2d  test    r14, r14
0x18002fd30  jz      short loc_18002FD35
0x18002fd32  mov     [r14], r12d
0x18002fd35  mov     rax, rbx
0x18002fd38  add     rsp, 28h
0x18002fd3c  pop     r15
0x18002fd3e  pop     r14
0x18002fd40  pop     r13
0x18002fd42  pop     r12
0x18002fd44  pop     rdi
0x18002fd45  pop     rsi
0x18002fd46  pop     rbp
0x18002fd47  pop     rbx
0x18002fd48  retn
```
