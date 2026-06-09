# Art::EyedropperTool::EyedropperPreviewWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18059c770`
- end: `0x18059c8ed`
- name: `?EyedropperPreviewWndProc@EyedropperTool@Art@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `381`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180276a71`
- `0x180279030`
- `0x18059c770`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18059c7b6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18059c7b6`
- `GDI32!CreateSolidBrush` at `0x18059c81a`
- `GDI32!CreateSolidBrush` at `0x18059c877`
- `GDI32!CreateSolidBrush` at `0x18059c81a`
- `GDI32!CreateSolidBrush` at `0x18059c877`
- `GDI32!GetStockObject` at `0x18059c83f`
- `GDI32!GetStockObject` at `0x18059c83f`
- `GDI32!DeleteObject` at `0x18059c837`
- `GDI32!DeleteObject` at `0x18059c86e`
- `GDI32!DeleteObject` at `0x18059c8a6`
- `GDI32!DeleteObject` at `0x18059c837`
- `GDI32!DeleteObject` at `0x18059c86e`
- `GDI32!DeleteObject` at `0x18059c8a6`
- `USER32!EndPaint` at `0x18059c8b4`
- `USER32!EndPaint` at `0x18059c8b4`
- `USER32!FillRect` at `0x18059c89d`
- `USER32!FillRect` at `0x18059c89d`
- `USER32!InflateRect` at `0x18059c854`
- `USER32!InflateRect` at `0x18059c88c`
- `USER32!InflateRect` at `0x18059c854`
- `USER32!InflateRect` at `0x18059c88c`
- `USER32!FrameRect` at `0x18059c82e`
- `USER32!FrameRect` at `0x18059c865`
- `USER32!FrameRect` at `0x18059c82e`
- `USER32!FrameRect` at `0x18059c865`
- `USER32!SetRect` at `0x18059c80f`
- `USER32!SetRect` at `0x18059c80f`
- `USER32!BeginPaint` at `0x18059c7e9`
- `USER32!BeginPaint` at `0x18059c7e9`
- `USER32!DefWindowProcW` at `0x18059c8c5`
- `USER32!DefWindowProcW` at `0x18059c8c5`

## pseudocode

```c
LRESULT __fastcall Art::EyedropperTool::EyedropperPreviewWndProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  Art::EyedropperTool *v8; // rbp
  HDC v9; // rdi
  HBRUSH SolidBrush; // rbx
  HBRUSH StockObject; // rbx
  HBRUSH v12; // rbx
  struct tagRECT rc; // [rsp+30h] [rbp-A8h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-98h] BYREF

  if ( Msg == 15 || Msg == 71 )
  {
    v8 = Ofc::TSingleton<Art::EyedropperTool>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<Art::EyedropperTool>::s_pInstance > 1 )
    {
      memset_0(&Paint, 0, sizeof(Paint));
      rc = 0;
      v9 = BeginPaint(hWnd, &Paint);
      SetRect(&rc, 0, 0, 32, 32);
      SolidBrush = CreateSolidBrush(0x452F2Du);
      FrameRect(v9, &rc, SolidBrush);
      DeleteObject(SolidBrush);
      StockObject = (HBRUSH)GetStockObject(0);
      InflateRect(&rc, -1, -1);
      FrameRect(v9, &rc, StockObject);
      DeleteObject(StockObject);
      v12 = CreateSolidBrush(*((_DWORD *)v8 + 12));
      InflateRect(&rc, -1, -1);
      FillRect(v9, &rc, v12);
      DeleteObject(v12);
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
0x18059c770  push    rbx
0x18059c772  push    rbp
0x18059c773  push    rsi
0x18059c774  push    rdi
0x18059c775  push    r12
0x18059c777  push    r14
0x18059c779  push    r15
0x18059c77b  sub     rsp, 0A0h
0x18059c782  mov     rax, cs:__security_cookie
0x18059c789  xor     rax, rsp
0x18059c78c  mov     [rsp+0D8h+var_48], rax
0x18059c794  mov     r12, r9
0x18059c797  mov     r15, r8
0x18059c79a  mov     esi, edx
0x18059c79c  mov     r14, rcx
0x18059c79f  cmp     edx, 0Fh
0x18059c7a2  jnz     short loc_18059C7C1
0x18059c7a4  mov     rbp, cs:?s_pInstance@?$TSingleton@VEyedropperTool@Art@@@Ofc@@0PEAVEyedropperTool@Art@@EA; Art::EyedropperTool * Ofc::TSingleton<Art::EyedropperTool>::s_pInstance
0x18059c7ab  cmp     rbp, 1
0x18059c7af  ja      short loc_18059C7CC
0x18059c7b1  mov     ecx, 234848C9h
0x18059c7b6  call    cs:__imp_MsoShipAssertTagProc
0x18059c7bc  jmp     loc_18059C8BA
0x18059c7c1  cmp     esi, 47h ; 'G'
0x18059c7c4  jnz     loc_18059C8BA
0x18059c7ca  jmp     short loc_18059C7A4
0x18059c7cc  test    rbp, rbp
0x18059c7cf  jz      short loc_18059C7B1
0x18059c7d1  xor     edx, edx; Val
0x18059c7d3  lea     rcx, [rsp+0D8h+Paint]; void *
0x18059c7d8  lea     r8d, [rdx+48h]; Size
0x18059c7dc  call    memset_0
0x18059c7e1  lea     rdx, [rsp+0D8h+Paint]; lpPaint
0x18059c7e6  mov     rcx, r14; hWnd
0x18059c7e9  call    cs:__imp_BeginPaint
0x18059c7ef  xorps   xmm0, xmm0
0x18059c7f2  lea     rcx, [rsp+0D8h+rc]; lprc
0x18059c7f7  mov     r9d, 20h ; ' '; xRight
0x18059c7fd  xor     r8d, r8d; yTop
0x18059c800  xor     edx, edx; xLeft
0x18059c802  mov     [rsp+0D8h+yBottom], r9d; yBottom
0x18059c807  movups  xmmword ptr [rsp+0D8h+rc.left], xmm0
0x18059c80c  mov     rdi, rax
0x18059c80f  call    cs:__imp_SetRect
0x18059c815  mov     ecx, 452F2Dh; color
0x18059c81a  call    cs:__imp_CreateSolidBrush
0x18059c820  lea     rdx, [rsp+0D8h+rc]; lprc
0x18059c825  mov     rcx, rdi; hDC
0x18059c828  mov     r8, rax; hbr
0x18059c82b  mov     rbx, rax
0x18059c82e  call    cs:__imp_FrameRect
0x18059c834  mov     rcx, rbx; ho
0x18059c837  call    cs:__imp_DeleteObject
0x18059c83d  xor     ecx, ecx; i
0x18059c83f  call    cs:__imp_GetStockObject
0x18059c845  or      r8d, 0FFFFFFFFh; dy
0x18059c849  lea     rcx, [rsp+0D8h+rc]; lprc
0x18059c84e  or      edx, r8d; dx
0x18059c851  mov     rbx, rax
0x18059c854  call    cs:__imp_InflateRect
0x18059c85a  mov     r8, rbx; hbr
0x18059c85d  lea     rdx, [rsp+0D8h+rc]; lprc
0x18059c862  mov     rcx, rdi; hDC
0x18059c865  call    cs:__imp_FrameRect
0x18059c86b  mov     rcx, rbx; ho
0x18059c86e  call    cs:__imp_DeleteObject
0x18059c874  mov     ecx, [rbp+30h]; color
0x18059c877  call    cs:__imp_CreateSolidBrush
0x18059c87d  or      r8d, 0FFFFFFFFh; dy
0x18059c881  lea     rcx, [rsp+0D8h+rc]; lprc
0x18059c886  or      edx, r8d; dx
0x18059c889  mov     rbx, rax
0x18059c88c  call    cs:__imp_InflateRect
0x18059c892  mov     r8, rbx; hbr
0x18059c895  lea     rdx, [rsp+0D8h+rc]; lprc
0x18059c89a  mov     rcx, rdi; hDC
0x18059c89d  call    cs:__imp_FillRect
0x18059c8a3  mov     rcx, rbx; ho
0x18059c8a6  call    cs:__imp_DeleteObject
0x18059c8ac  lea     rdx, [rsp+0D8h+Paint]; lpPaint
0x18059c8b1  mov     rcx, r14; hWnd
0x18059c8b4  call    cs:__imp_EndPaint
0x18059c8ba  mov     r9, r12; lParam
0x18059c8bd  mov     r8, r15; wParam
0x18059c8c0  mov     edx, esi; Msg
0x18059c8c2  mov     rcx, r14; hWnd
0x18059c8c5  call    cs:__imp_DefWindowProcW
0x18059c8cb  mov     rcx, [rsp+0D8h+var_48]
0x18059c8d3  xor     rcx, rsp; StackCookie
0x18059c8d6  call    __security_check_cookie
0x18059c8db  add     rsp, 0A0h
0x18059c8e2  pop     r15
0x18059c8e4  pop     r14
0x18059c8e6  pop     r12
0x18059c8e8  pop     rdi
0x18059c8e9  pop     rsi
0x18059c8ea  pop     rbp
0x18059c8eb  pop     rbx
0x18059c8ec  retn
```
