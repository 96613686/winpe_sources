# Art::EyedropperTool::EyedropperPreviewWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180568020`
- end: `0x18056819a`
- name: `?EyedropperPreviewWndProc@EyedropperTool@Art@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `378`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180064914`
- `0x180070fe0`
- `0x180568020`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18056809e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18056809e`
- `GDI32!CreateSolidBrush` at `0x1805680f4`
- `GDI32!CreateSolidBrush` at `0x180568151`
- `GDI32!CreateSolidBrush` at `0x1805680f4`
- `GDI32!CreateSolidBrush` at `0x180568151`
- `GDI32!GetStockObject` at `0x180568119`
- `GDI32!GetStockObject` at `0x180568119`
- `GDI32!DeleteObject` at `0x180568111`
- `GDI32!DeleteObject` at `0x180568148`
- `GDI32!DeleteObject` at `0x180568180`
- `GDI32!DeleteObject` at `0x180568111`
- `GDI32!DeleteObject` at `0x180568148`
- `GDI32!DeleteObject` at `0x180568180`
- `USER32!EndPaint` at `0x18056818e`
- `USER32!EndPaint` at `0x18056818e`
- `USER32!FillRect` at `0x180568177`
- `USER32!FillRect` at `0x180568177`
- `USER32!InflateRect` at `0x18056812e`
- `USER32!InflateRect` at `0x180568166`
- `USER32!InflateRect` at `0x18056812e`
- `USER32!InflateRect` at `0x180568166`
- `USER32!FrameRect` at `0x180568108`
- `USER32!FrameRect` at `0x18056813f`
- `USER32!FrameRect` at `0x180568108`
- `USER32!FrameRect` at `0x18056813f`
- `USER32!SetRect` at `0x1805680e9`
- `USER32!SetRect` at `0x1805680e9`
- `USER32!BeginPaint` at `0x1805680c3`
- `USER32!BeginPaint` at `0x1805680c3`
- `USER32!DefWindowProcW` at `0x180568064`
- `USER32!DefWindowProcW` at `0x180568064`

## pseudocode

```c
LRESULT __fastcall Art::EyedropperTool::EyedropperPreviewWndProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  Art::EyedropperTool *v9; // rbp
  HDC v10; // rdi
  HBRUSH SolidBrush; // rbx
  HBRUSH StockObject; // rbx
  HBRUSH v13; // rbx
  struct tagRECT rc; // [rsp+30h] [rbp-A8h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-98h] BYREF

  if ( Msg == 15 || Msg == 71 )
  {
    v9 = Ofc::TSingleton<Art::EyedropperTool>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<Art::EyedropperTool>::s_pInstance > 1 )
    {
      memset_0(&Paint, 0, sizeof(Paint));
      rc = 0;
      v10 = BeginPaint(hWnd, &Paint);
      SetRect(&rc, 0, 0, 32, 32);
      SolidBrush = CreateSolidBrush(0x452F2Du);
      FrameRect(v10, &rc, SolidBrush);
      DeleteObject(SolidBrush);
      StockObject = (HBRUSH)GetStockObject(0);
      InflateRect(&rc, -1, -1);
      FrameRect(v10, &rc, StockObject);
      DeleteObject(StockObject);
      v13 = CreateSolidBrush(*((_DWORD *)v9 + 12));
      InflateRect(&rc, -1, -1);
      FillRect(v10, &rc, v13);
      DeleteObject(v13);
      EndPaint(hWnd, &Paint);
    }
    else
    {
      MsoShipAssertTagProc(591939785);
    }
  }
  return DefWindowProcW(hWnd, Msg, wParam, lParam);
}

```

## disassembly

```asm
0x180568020  push    rbx
0x180568022  push    rbp
0x180568023  push    rsi
0x180568024  push    rdi
0x180568025  push    r12
0x180568027  push    r14
0x180568029  push    r15
0x18056802b  sub     rsp, 0A0h
0x180568032  mov     rax, cs:__security_cookie
0x180568039  xor     rax, rsp
0x18056803c  mov     [rsp+0D8h+var_48], rax
0x180568044  mov     r12, r9
0x180568047  mov     r15, r8
0x18056804a  mov     esi, edx
0x18056804c  mov     r14, rcx
0x18056804f  cmp     edx, 0Fh
0x180568052  jz      short loc_18056808C
0x180568054  cmp     edx, 47h ; 'G'
0x180568057  jz      short loc_18056808C
0x180568059  mov     r9, r12; lParam
0x18056805c  mov     r8, r15; wParam
0x18056805f  mov     edx, esi; Msg
0x180568061  mov     rcx, r14; hWnd
0x180568064  call    cs:__imp_DefWindowProcW
0x18056806a  mov     rcx, [rsp+0D8h+var_48]
0x180568072  xor     rcx, rsp; StackCookie
0x180568075  call    __security_check_cookie
0x18056807a  add     rsp, 0A0h
0x180568081  pop     r15
0x180568083  pop     r14
0x180568085  pop     r12
0x180568087  pop     rdi
0x180568088  pop     rsi
0x180568089  pop     rbp
0x18056808a  pop     rbx
0x18056808b  retn
0x18056808c  mov     rbp, cs:?s_pInstance@?$TSingleton@VEyedropperTool@Art@@@Ofc@@0PEAVEyedropperTool@Art@@EA; Art::EyedropperTool * Ofc::TSingleton<Art::EyedropperTool>::s_pInstance
0x180568093  cmp     rbp, 1
0x180568097  ja      short loc_1805680A6
0x180568099  mov     ecx, 234848C9h
0x18056809e  call    cs:__imp_MsoShipAssertTagProc
0x1805680a4  jmp     short loc_180568059
0x1805680a6  test    rbp, rbp
0x1805680a9  jz      short loc_180568099
0x1805680ab  xor     edx, edx; Val
0x1805680ad  lea     rcx, [rsp+0D8h+Paint]; void *
0x1805680b2  lea     r8d, [rdx+48h]; Size
0x1805680b6  call    memset_0
0x1805680bb  lea     rdx, [rsp+0D8h+Paint]; lpPaint
0x1805680c0  mov     rcx, r14; hWnd
0x1805680c3  call    cs:__imp_BeginPaint
0x1805680c9  xorps   xmm0, xmm0
0x1805680cc  lea     rcx, [rsp+0D8h+rc]; lprc
0x1805680d1  mov     r9d, 20h ; ' '; xRight
0x1805680d7  xor     r8d, r8d; yTop
0x1805680da  xor     edx, edx; xLeft
0x1805680dc  mov     [rsp+0D8h+yBottom], r9d; yBottom
0x1805680e1  movups  xmmword ptr [rsp+0D8h+rc.left], xmm0
0x1805680e6  mov     rdi, rax
0x1805680e9  call    cs:__imp_SetRect
0x1805680ef  mov     ecx, 452F2Dh; color
0x1805680f4  call    cs:__imp_CreateSolidBrush
0x1805680fa  lea     rdx, [rsp+0D8h+rc]; lprc
0x1805680ff  mov     rcx, rdi; hDC
0x180568102  mov     r8, rax; hbr
0x180568105  mov     rbx, rax
0x180568108  call    cs:__imp_FrameRect
0x18056810e  mov     rcx, rbx; ho
0x180568111  call    cs:__imp_DeleteObject
0x180568117  xor     ecx, ecx; i
0x180568119  call    cs:__imp_GetStockObject
0x18056811f  or      r8d, 0FFFFFFFFh; dy
0x180568123  lea     rcx, [rsp+0D8h+rc]; lprc
0x180568128  or      edx, r8d; dx
0x18056812b  mov     rbx, rax
0x18056812e  call    cs:__imp_InflateRect
0x180568134  mov     r8, rbx; hbr
0x180568137  lea     rdx, [rsp+0D8h+rc]; lprc
0x18056813c  mov     rcx, rdi; hDC
0x18056813f  call    cs:__imp_FrameRect
0x180568145  mov     rcx, rbx; ho
0x180568148  call    cs:__imp_DeleteObject
0x18056814e  mov     ecx, [rbp+30h]; color
0x180568151  call    cs:__imp_CreateSolidBrush
0x180568157  or      r8d, 0FFFFFFFFh; dy
0x18056815b  lea     rcx, [rsp+0D8h+rc]; lprc
0x180568160  or      edx, r8d; dx
0x180568163  mov     rbx, rax
0x180568166  call    cs:__imp_InflateRect
0x18056816c  mov     r8, rbx; hbr
0x18056816f  lea     rdx, [rsp+0D8h+rc]; lprc
0x180568174  mov     rcx, rdi; hDC
0x180568177  call    cs:__imp_FillRect
0x18056817d  mov     rcx, rbx; ho
0x180568180  call    cs:__imp_DeleteObject
0x180568186  lea     rdx, [rsp+0D8h+Paint]; lpPaint
0x18056818b  mov     rcx, r14; hWnd
0x18056818e  call    cs:__imp_EndPaint
0x180568194  jmp     loc_180568059
```
