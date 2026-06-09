# SoftwareBackBuffer::Present(void)

- ea: `0x18052ec60`
- end: `0x18052ee69`
- name: `?Present@SoftwareBackBuffer@@UEAAJXZ`
- size: `521`
- prototype: `__int64 __fastcall(SoftwareBackBuffer *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001db0c`
- `0x1803e13a4`
- `0x180521acc`
- `0x18052ec60`
- `0x18056bd00`

## import_xrefs

- `GDI32!DeleteDC` at `0x18052edf6`
- `GDI32!DeleteDC` at `0x18052edf6`
- `GDI32!CombineRgn` at `0x18052ed6d`
- `GDI32!CombineRgn` at `0x18052ed6d`
- `GDI32!FillRgn` at `0x18052edd5`
- `GDI32!FillRgn` at `0x18052edd5`
- `GDI32!GetRgnBox` at `0x18052ed9b`
- `GDI32!GetRgnBox` at `0x18052ed9b`
- `GDI32!DeleteObject` at `0x18052ed7b`
- `GDI32!DeleteObject` at `0x18052ee20`
- `GDI32!DeleteObject` at `0x18052ed7b`
- `GDI32!DeleteObject` at `0x18052ee20`
- `GDI32!CreateRectRgnIndirect` at `0x18052ed32`
- `GDI32!CreateRectRgnIndirect` at `0x18052ed55`
- `GDI32!CreateRectRgnIndirect` at `0x18052ed32`
- `GDI32!CreateRectRgnIndirect` at `0x18052ed55`
- `USER32!GetClientRect` at `0x18052ec94`
- `USER32!GetClientRect` at `0x18052ec94`
- `USER32!GetUpdateRgn` at `0x18052ed4a`
- `USER32!GetUpdateRgn` at `0x18052ed4a`
- `USER32!ReleaseDC` at `0x18052edeb`
- `USER32!ReleaseDC` at `0x18052edeb`
- `USER32!GetDC` at `0x18052edc3`
- `USER32!GetDC` at `0x18052edc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall SoftwareBackBuffer::Present(SoftwareBackBuffer *this)
{
  HRGN v2; // rbx
  HRGN v3; // rdi
  HBRUSH v4; // rdi
  HWND v5; // r15
  HDC DC; // r14
  struct tagRECT rc; // [rsp+40h] [rbp-68h] BYREF
  RECT rect; // [rsp+50h] [rbp-58h] BYREF
  RECT v10; // [rsp+60h] [rbp-48h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-38h] BYREF

  if ( GetClientRect(*((HWND *)this + 14), &Rect)
    && *((_QWORD *)this + 21)
    && *((_DWORD *)this + 30) < *((_DWORD *)this + 32)
    && *((_DWORD *)this + 31) < *((_DWORD *)this + 33) )
  {
    v10 = *(RECT *)((char *)this + 120);
    if ( (unsigned __int64)(0x80000000LL - *((int *)this + 34)) > 0xFFFFFFFF
      || (unsigned __int64)(0x80000000LL - *((int *)this + 35)) > 0xFFFFFFFF )
    {
      safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
    }
    RectT<IntegerTypes>::OffsetRect(&v10, -(__int64)*((int *)this + 34), -(__int64)*((int *)this + 35));
    *(_QWORD *)&rect.left = 0;
    *(_QWORD *)&rect.right = 0;
    v2 = CreateRectRgnIndirect(&rect);
    GetUpdateRgn(*((HWND *)this + 14), v2, 0);
    v3 = CreateRectRgnIndirect(&v10);
    CombineRgn(v2, v2, v3, 4);
    if ( v3 )
      DeleteObject(v3);
    *(_QWORD *)&rc.left = 0;
    *(_QWORD *)&rc.right = 0;
    GetRgnBox(v2, &rc);
    if ( rc.left < rc.right && rc.top < rc.bottom )
    {
      v4 = (HBRUSH)*((_QWORD *)this + 19);
      v5 = (HWND)*((_QWORD *)this + 14);
      DC = GetDC(v5);
      FillRgn(DC, v2, v4);
      if ( DC )
      {
        if ( v5 )
          ReleaseDC(v5, DC);
        else
          DeleteDC(DC);
      }
    }
    SoftwareDevice::Present(*((_QWORD *)this + 20), *((_QWORD *)this + 21), &Rect, *((_QWORD *)this + 14), v2);
    if ( v2 )
      DeleteObject(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x18052ec60  mov     [rsp+arg_8], rbx
0x18052ec65  mov     [rsp+arg_10], rsi
0x18052ec6a  push    rdi
0x18052ec6b  push    r14
0x18052ec6d  push    r15
0x18052ec6f  sub     rsp, 90h
0x18052ec76  mov     rax, cs:__security_cookie
0x18052ec7d  xor     rax, rsp
0x18052ec80  mov     [rsp+0A8h+var_28], rax
0x18052ec88  mov     rsi, rcx
0x18052ec8b  lea     rdx, [rsp+0A8h+Rect]; lpRect
0x18052ec90  mov     rcx, [rcx+70h]; hWnd
0x18052ec94  call    cs:__imp_GetClientRect
0x18052ec9a  test    eax, eax
0x18052ec9c  jz      loc_18052EE26
0x18052eca2  cmp     qword ptr [rsi+0A8h], 0
0x18052ecaa  jz      loc_18052EE26
0x18052ecb0  mov     eax, [rsi+80h]
0x18052ecb6  cmp     [rsi+78h], eax
0x18052ecb9  jge     loc_18052EE26
0x18052ecbf  mov     eax, [rsi+84h]
0x18052ecc5  cmp     [rsi+7Ch], eax
0x18052ecc8  jge     loc_18052EE26
0x18052ecce  movups  xmm0, xmmword ptr [rsi+78h]
0x18052ecd2  movdqu  xmmword ptr [rsp+0A8h+var_48.left], xmm0
0x18052ecd8  movsxd  rdx, dword ptr [rsi+88h]
0x18052ecdf  neg     rdx
0x18052ece2  mov     ecx, 80000000h
0x18052ece7  lea     rax, [rcx+rdx]
0x18052eceb  mov     r9d, 0FFFFFFFFh
0x18052ecf1  cmp     rax, r9
0x18052ecf4  ja      loc_18052EE63
0x18052ecfa  movsxd  r8, dword ptr [rsi+8Ch]
0x18052ed01  neg     r8
0x18052ed04  lea     rax, [r8+rcx]
0x18052ed08  cmp     rax, r9
0x18052ed0b  ja      loc_18052EE63
0x18052ed11  lea     rcx, [rsp+0A8h+var_48]
0x18052ed16  call    ?OffsetRect@?$RectT@UIntegerTypes@@@@QEAAXHH@Z; RectT<IntegerTypes>::OffsetRect(int,int)
0x18052ed1b  mov     qword ptr [rsp+0A8h+rect.left], 0
0x18052ed24  mov     qword ptr [rsp+0A8h+rect.right], 0
0x18052ed2d  lea     rcx, [rsp+0A8h+rect]; lprect
0x18052ed32  call    cs:__imp_CreateRectRgnIndirect
0x18052ed38  mov     rbx, rax
0x18052ed3b  mov     [rsp+0A8h+var_88], rax
0x18052ed40  xor     r8d, r8d; bErase
0x18052ed43  mov     rdx, rax; hRgn
0x18052ed46  mov     rcx, [rsi+70h]; hWnd
0x18052ed4a  call    cs:__imp_GetUpdateRgn
0x18052ed50  lea     rcx, [rsp+0A8h+var_48]; lprect
0x18052ed55  call    cs:__imp_CreateRectRgnIndirect
0x18052ed5b  mov     rdi, rax
0x18052ed5e  mov     r9d, 4; iMode
0x18052ed64  mov     r8, rax; hrgnSrc2
0x18052ed67  mov     rdx, rbx; hrgnSrc1
0x18052ed6a  mov     rcx, rbx; hrgnDst
0x18052ed6d  call    cs:__imp_CombineRgn
0x18052ed73  test    rdi, rdi
0x18052ed76  jz      short loc_18052ED81
0x18052ed78  mov     rcx, rdi; ho
0x18052ed7b  call    cs:__imp_DeleteObject
0x18052ed81  mov     qword ptr [rsp+0A8h+rc.left], 0
0x18052ed8a  mov     qword ptr [rsp+0A8h+rc.right], 0
0x18052ed93  lea     rdx, [rsp+0A8h+rc]; lprc
0x18052ed98  mov     rcx, rbx; hrgn
0x18052ed9b  call    cs:__imp_GetRgnBox
0x18052eda1  mov     eax, [rsp+0A8h+rc.right]
0x18052eda5  cmp     [rsp+0A8h+rc.left], eax
0x18052eda9  jge     short loc_18052EDFC
0x18052edab  mov     eax, [rsp+0A8h+rc.bottom]
0x18052edaf  cmp     [rsp+0A8h+rc.top], eax
0x18052edb3  jge     short loc_18052EDFC
0x18052edb5  mov     rdi, [rsi+98h]
0x18052edbc  mov     r15, [rsi+70h]
0x18052edc0  mov     rcx, r15; hWnd
0x18052edc3  call    cs:__imp_GetDC
0x18052edc9  mov     r14, rax
0x18052edcc  mov     r8, rdi; hbr
0x18052edcf  mov     rdx, rbx; hrgn
0x18052edd2  mov     rcx, rax; hdc
0x18052edd5  call    cs:__imp_FillRgn
0x18052eddb  test    r14, r14
0x18052edde  jz      short loc_18052EDFC
0x18052ede0  test    r15, r15
0x18052ede3  jz      short loc_18052EDF3
0x18052ede5  mov     rdx, r14; hDC
0x18052ede8  mov     rcx, r15; hWnd
0x18052edeb  call    cs:__imp_ReleaseDC
0x18052edf1  jmp     short loc_18052EDFC
0x18052edf3  mov     rcx, r14; hdc
0x18052edf6  call    cs:__imp_DeleteDC
0x18052edfc  mov     r9, [rsi+70h]
0x18052ee00  lea     r8, [rsp+0A8h+Rect]
0x18052ee05  mov     rdx, [rsi+0A8h]
0x18052ee0c  mov     rcx, [rsi+0A0h]
0x18052ee13  call    ?Present@SoftwareDevice@@QEAAXPEAUIImageBuffer@@AEBU?$PointT@UIntegerTypes@@@@PEAUHWND__@@@Z; SoftwareDevice::Present(IImageBuffer *,PointT<IntegerTypes> const &,HWND__ *)
0x18052ee18  test    rbx, rbx
0x18052ee1b  jz      short loc_18052EE26
0x18052ee1d  mov     rcx, rbx; ho
0x18052ee20  call    cs:__imp_DeleteObject
0x18052ee26  xor     eax, eax
0x18052ee28  jmp     short loc_18052EE3A
0x18052ee2a  mov     eax, dword ptr [rsp+0A8h+var_88]
0x18052ee2e  mov     edx, 86160101h
0x18052ee33  cmp     ax, 216h
0x18052ee37  cmovz   eax, edx
0x18052ee3a  mov     rcx, [rsp+0A8h+var_28]
0x18052ee42  xor     rcx, rsp; StackCookie
0x18052ee45  call    __security_check_cookie
0x18052ee4a  lea     r11, [rsp+0A8h+var_18]
0x18052ee52  mov     rbx, [r11+28h]
0x18052ee56  mov     rsi, [r11+30h]
0x18052ee5a  mov     rsp, r11
0x18052ee5d  pop     r15
0x18052ee5f  pop     r14
0x18052ee61  pop     rdi
0x18052ee62  retn
0x18052ee63  call    ?SafeIntOnOverflow@SafeInt_InvalidParameter@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow(void)
```
