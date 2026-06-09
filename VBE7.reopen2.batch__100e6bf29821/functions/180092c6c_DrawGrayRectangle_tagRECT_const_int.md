# DrawGrayRectangle(tagRECT const *,int)

- ea: `0x180092c6c`
- end: `0x180092d8f`
- name: `?DrawGrayRectangle@@YAXPEBUtagRECT@@H@Z`
- size: `291`
- prototype: `void __fastcall(const struct tagRECT *, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180092adc`
- `0x1800cf7f0`
- `0x1800cf8e4`
- `0x1800cfa00`
- `0x1800cfb04`
- `0x1800cfb28`

## callees

- `0x180001504`
- `0x180092b4c`
- `0x180092c6c`
- `0x180379380`

## import_xrefs

- `USER32!LockWindowUpdate` at `0x180092ca7`
- `USER32!LockWindowUpdate` at `0x180092d79`
- `USER32!LockWindowUpdate` at `0x180092ca7`
- `USER32!LockWindowUpdate` at `0x180092d79`
- `USER32!GetDesktopWindow` at `0x180092c9b`
- `USER32!GetDesktopWindow` at `0x180092c9b`
- `USER32!EqualRect` at `0x180092cf6`
- `USER32!EqualRect` at `0x180092cf6`
- `USER32!CopyRect` at `0x180092d4b`
- `USER32!CopyRect` at `0x180092d4b`
- `USER32!ReleaseDC` at `0x180092d71`
- `USER32!ReleaseDC` at `0x180092d71`
- `USER32!GetDCEx` at `0x180092cb8`
- `USER32!GetDCEx` at `0x180092cb8`
- `GDI32!SelectObject` at `0x180092cdd`
- `GDI32!SelectObject` at `0x180092cdd`

## pseudocode

```c
void __fastcall DrawGrayRectangle(const struct tagRECT *a1, int a2)
{
  HWND DesktopWindow; // rbx
  HBRUSH v5; // rax

  if ( a1 )
  {
    if ( dword_1803FABE8 )
      goto LABEL_16;
    DesktopWindow = GetDesktopWindow();
    LockWindowUpdate(DesktopWindow);
    hDC = GetDCEx(DesktopWindow, 0, 0x403u);
    if ( !hDC )
    {
LABEL_13:
      LockWindowUpdate(0);
      return;
    }
    v5 = BrHbrushDithered();
    SelectObject(hDC, v5);
    if ( dword_1803FABE8 )
    {
LABEL_16:
      if ( EqualRect(a1, &rcDst) )
        return;
    }
    DrawGrayRectangleInternal(hDC, a1, a2);
  }
  if ( dword_1803FABE8 )
  {
    DrawGrayRectangleInternal(hDC, &rcDst, dword_1803FABEC);
    dword_1803FABE8 = 0;
  }
  if ( a1 )
  {
    CopyRect(&rcDst, a1);
    dword_1803FABEC = a2;
    dword_1803FABE8 = 1;
    return;
  }
  if ( hDC )
  {
    ReleaseDC(0, hDC);
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x180092c6c  mov     [rsp+arg_0], rbx
0x180092c71  mov     [rsp+arg_8], rsi
0x180092c76  push    rdi
0x180092c77  mov     eax, 20h
0x180092c7c  call    _alloca_probe
0x180092c81  sub     rsp, rax
0x180092c84  mov     esi, edx
0x180092c86  mov     rdi, rcx
0x180092c89  test    rcx, rcx
0x180092c8c  jz      loc_180092D12
0x180092c92  cmp     cs:dword_1803FABE8, 0
0x180092c99  jnz     short loc_180092CEC
0x180092c9b  call    cs:__imp_GetDesktopWindow
0x180092ca1  mov     rcx, rax; hWndLock
0x180092ca4  mov     rbx, rax
0x180092ca7  call    cs:__imp_LockWindowUpdate
0x180092cad  xor     edx, edx; hrgnClip
0x180092caf  mov     r8d, 403h; flags
0x180092cb5  mov     rcx, rbx; hWnd
0x180092cb8  call    cs:__imp_GetDCEx
0x180092cbe  mov     cs:hDC, rax
0x180092cc5  test    rax, rax
0x180092cc8  jz      loc_180092D77
0x180092cce  call    ?BrHbrushDithered@@YAPEAUHBRUSH__@@XZ; BrHbrushDithered(void)
0x180092cd3  mov     rcx, cs:hDC; hdc
0x180092cda  mov     rdx, rax; h
0x180092cdd  call    cs:__imp_SelectObject
0x180092ce3  cmp     cs:dword_1803FABE8, 0
0x180092cea  jz      short loc_180092D00
0x180092cec  lea     rdx, rcDst; lprc2
0x180092cf3  mov     rcx, rdi; lprc1
0x180092cf6  call    cs:__imp_EqualRect
0x180092cfc  test    eax, eax
0x180092cfe  jnz     short loc_180092D7F
0x180092d00  mov     rcx, cs:hDC; HDC
0x180092d07  mov     r8d, esi; int
0x180092d0a  mov     rdx, rdi; struct tagRECT *
0x180092d0d  call    ?DrawGrayRectangleInternal@@YAXPEAUHDC__@@PEBUtagRECT@@H@Z; DrawGrayRectangleInternal(HDC__ *,tagRECT const *,int)
0x180092d12  cmp     cs:dword_1803FABE8, 0
0x180092d19  jz      short loc_180092D3C
0x180092d1b  mov     r8d, cs:dword_1803FABEC; int
0x180092d22  mov     rcx, cs:hDC; HDC
0x180092d29  lea     rdx, rcDst; struct tagRECT *
0x180092d30  call    ?DrawGrayRectangleInternal@@YAXPEAUHDC__@@PEBUtagRECT@@H@Z; DrawGrayRectangleInternal(HDC__ *,tagRECT const *,int)
0x180092d35  and     cs:dword_1803FABE8, 0
0x180092d3c  test    rdi, rdi
0x180092d3f  jz      short loc_180092D63
0x180092d41  lea     rcx, rcDst; lprcDst
0x180092d48  mov     rdx, rdi; lprcSrc
0x180092d4b  call    cs:__imp_CopyRect
0x180092d51  mov     cs:dword_1803FABEC, esi
0x180092d57  mov     cs:dword_1803FABE8, 1
0x180092d61  jmp     short loc_180092D7F
0x180092d63  mov     rdx, cs:hDC; hDC
0x180092d6a  test    rdx, rdx
0x180092d6d  jz      short loc_180092D7F
0x180092d6f  xor     ecx, ecx; hWnd
0x180092d71  call    cs:__imp_ReleaseDC
0x180092d77  xor     ecx, ecx; hWndLock
0x180092d79  call    cs:__imp_LockWindowUpdate
0x180092d7f  mov     rbx, [rsp+28h+arg_0]
0x180092d84  mov     rsi, [rsp+28h+arg_8]
0x180092d89  add     rsp, 20h
0x180092d8d  pop     rdi
0x180092d8e  retn
```
