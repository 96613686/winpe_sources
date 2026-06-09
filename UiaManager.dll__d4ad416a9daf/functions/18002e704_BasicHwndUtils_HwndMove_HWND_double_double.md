# BasicHwndUtils::HwndMove(HWND__ *,double,double)

- ea: `0x18002e704`
- end: `0x18002ea84`
- name: `?HwndMove@BasicHwndUtils@@SAJPEAUHWND__@@NN@Z`
- size: `896`
- prototype: `__int64 __fastcall(HWND hWnd, double, double)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002e6a0`

## callees

- `0x18002e704`
- `0x18002ea8c`
- `0x180031540`
- `0x180043680`
- `0x18007c7b8`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18002e788`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18002e964`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18002e788`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18002e964`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18002e7ff`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18002e9ac`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18002e7ff`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18002e9ac`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClientRect` at `0x18002e893`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClientRect` at `0x18002e893`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowPos` at `0x18002e912`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetWindowPos` at `0x18002e912`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetAncestor` at `0x18002e7ae`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetAncestor` at `0x18002e7ae`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18002e7c7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18002e7c7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!GetWindowPlacement` at `0x18002e948`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!GetWindowPlacement` at `0x18002e9f0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!GetWindowPlacement` at `0x18002e948`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!GetWindowPlacement` at `0x18002e9f0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002e828`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002e836`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002e828`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18002e836`

## string_xrefs

- `0x18002e75e`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BasicHwndUtils::HwndMove(HWND hWnd, double a2, double a3)
{
  double y; // xmm6_8
  double x; // xmm7_8
  int CanMove; // eax
  const char *v7; // r9
  __int64 result; // rax
  HWND Ancestor; // r12
  int v10; // edi
  int v11; // esi
  int SystemMetrics; // r15d
  int v13; // eax
  int v14; // r14d
  int v15; // edi
  int v16; // esi
  int v17; // [rsp+20h] [rbp-C8h]
  struct tagPOINT Points; // [rsp+40h] [rbp-A8h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-A0h] BYREF
  WINDOWPLACEMENT wndpl; // [rsp+58h] [rbp-90h] BYREF
  struct tagRECT v21; // [rsp+88h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  y = a3;
  x = a2;
  Points.x = 0;
  CanMove = BasicHwndUtils::GetHwndCanMove(hWnd, (int *)&Points);
  try
  {
    if ( CanMove < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
        (const char *)(unsigned int)CanMove,
        v17);
    if ( !Points.x )
      return 2148734217LL;
    if ( (GetWindowLongW(hWnd, -20) & 0x40) != 0 )
    {
      Points.x = (int)a2;
      Points.y = (int)a3;
      Ancestor = GetAncestor(hWnd, 1u);
      if ( !MapWindowPoints(0, Ancestor, &Points, 1u) )
        return 2148734217LL;
      x = (double)Points.x;
      y = (double)Points.y;
      Rect = 0;
      if ( !GetWindowRect(hWnd, &Rect) )
        return 2148734217LL;
      v10 = Rect.bottom - Rect.top;
      v11 = Rect.right - Rect.left;
      SystemMetrics = GetSystemMetrics(2);
      v13 = GetSystemMetrics(3);
      v14 = v13;
      if ( (double)v11 + x < 0.0 )
        x = (double)(SystemMetrics - v11);
      if ( (double)v10 + y < 0.0 )
        y = (double)(v13 - v10);
      v21 = 0;
      if ( !GetClientRect(Ancestor, &v21) )
        return 2148734217LL;
      if ( x > (double)v21.right )
        x = (double)(v21.right - SystemMetrics);
      if ( y > (double)v21.bottom )
        y = (double)(v21.bottom - v14);
    }
    if ( !SetWindowPos(hWnd, 0, (int)x, (int)y, 0, 0, 0x15u) )
      return 2148734217LL;
    memset(&wndpl, 0, sizeof(wndpl));
    wndpl.length = 44;
    if ( !GetWindowPlacement(hWnd, &wndpl) )
      return 2148734217LL;
    if ( (GetWindowLongW(hWnd, -16) & 0x20000000) != 0 )
    {
      wndpl.ptMinPosition.y = (int)y;
      wndpl.ptMinPosition.x = (int)x;
      wndpl.flags = 1;
      if ( !BasicHwndUtils::SetWindowPlacementHelper(hWnd, &wndpl) )
        return 2148734217LL;
    }
    else
    {
      Rect = 0;
      if ( !GetWindowRect(hWnd, &Rect) )
        return 2148734217LL;
      if ( !BasicHwndUtils::SetWindowPlacementHelper(hWnd, &wndpl) )
        return 2148734217LL;
      v15 = Rect.bottom - Rect.top;
      v16 = Rect.right - Rect.left;
      if ( !GetWindowPlacement(hWnd, &wndpl) )
        return 2148734217LL;
      if ( v15 != wndpl.rcNormalPosition.bottom - wndpl.rcNormalPosition.top
        || v16 != wndpl.rcNormalPosition.right - wndpl.rcNormalPosition.left )
      {
        wndpl.rcNormalPosition.bottom = v15 + wndpl.rcNormalPosition.top;
        wndpl.rcNormalPosition.right = v16 + wndpl.rcNormalPosition.left;
        if ( !BasicHwndUtils::SetWindowPlacementHelper(hWnd, &wndpl) )
          return 2148734217LL;
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x405,
                           (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18002e704  mov     rax, rsp
0x18002e707  mov     [rax+20h], rbx
0x18002e70b  push    rsi
0x18002e70c  push    rdi
0x18002e70d  push    r12
0x18002e70f  push    r14
0x18002e711  push    r15
0x18002e713  sub     rsp, 0C0h
0x18002e71a  movaps  xmmword ptr [rax-38h], xmm6
0x18002e71e  movaps  xmmword ptr [rax-48h], xmm7
0x18002e722  mov     rax, cs:__security_cookie
0x18002e729  xor     rax, rsp
0x18002e72c  mov     [rsp+0E8h+var_50], rax
0x18002e734  movaps  xmm6, xmm2
0x18002e737  movaps  xmm7, xmm1
0x18002e73a  mov     rbx, rcx
0x18002e73d  mov     [rsp+0E8h+Points.x], 0
0x18002e745  lea     rdx, [rsp+0E8h+Points]; int *
0x18002e74a  call    ?GetHwndCanMove@BasicHwndUtils@@SAJPEAUHWND__@@PEAH@Z; BasicHwndUtils::GetHwndCanMove(HWND__ *,int *)
0x18002e74f  mov     rcx, [rsp+0E8h]; this
0x18002e757  test    eax, eax
0x18002e759  jns     short loc_18002E76F
0x18002e75b  mov     r9d, eax; char *
0x18002e75e  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x18002e765  mov     edx, 379h; void *
0x18002e76a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e76f  cmp     [rsp+0E8h+Points.x], 0
0x18002e774  jnz     short loc_18002E780
0x18002e776  mov     eax, 80131509h
0x18002e77b  jmp     loc_18002EA51
0x18002e780  mov     edx, 0FFFFFFECh; nIndex
0x18002e785  mov     rcx, rbx; hWnd
0x18002e788  call    cs:__imp_GetWindowLongW
0x18002e78e  test    al, 40h
0x18002e790  jz      loc_18002E8E7
0x18002e796  cvttsd2si eax, xmm7
0x18002e79a  mov     [rsp+0E8h+Points.x], eax
0x18002e79e  cvttsd2si eax, xmm6
0x18002e7a2  mov     [rsp+0E8h+Points.y], eax
0x18002e7a6  mov     edx, 1; gaFlags
0x18002e7ab  mov     rcx, rbx; hwnd
0x18002e7ae  call    cs:__imp_GetAncestor
0x18002e7b4  mov     r12, rax
0x18002e7b7  mov     r9d, 1; cPoints
0x18002e7bd  lea     r8, [rsp+0E8h+Points]; lpPoints
0x18002e7c2  mov     rdx, rax; hWndTo
0x18002e7c5  xor     ecx, ecx; hWndFrom
0x18002e7c7  call    cs:__imp_MapWindowPoints
0x18002e7cd  test    eax, eax
0x18002e7cf  jnz     short loc_18002E7DB
0x18002e7d1  mov     eax, 80131509h
0x18002e7d6  jmp     loc_18002EA51
0x18002e7db  movd    xmm7, [rsp+0E8h+Points.x]
0x18002e7e1  cvtdq2pd xmm7, xmm7
0x18002e7e5  movd    xmm6, [rsp+0E8h+Points.y]
0x18002e7eb  cvtdq2pd xmm6, xmm6
0x18002e7ef  xorps   xmm0, xmm0
0x18002e7f2  movups  xmmword ptr [rsp+0E8h+Rect.left], xmm0
0x18002e7f7  lea     rdx, [rsp+0E8h+Rect]; lpRect
0x18002e7fc  mov     rcx, rbx; hWnd
0x18002e7ff  call    cs:__imp_GetWindowRect
0x18002e805  test    eax, eax
0x18002e807  jnz     short loc_18002E813
0x18002e809  mov     eax, 80131509h
0x18002e80e  jmp     loc_18002EA51
0x18002e813  mov     edi, [rsp+0E8h+Rect.bottom]
0x18002e817  sub     edi, [rsp+0E8h+Rect.top]
0x18002e81b  mov     esi, [rsp+0E8h+Rect.right]
0x18002e81f  sub     esi, [rsp+0E8h+Rect.left]
0x18002e823  mov     ecx, 2; nIndex
0x18002e828  call    cs:__imp_GetSystemMetrics
0x18002e82e  mov     r15d, eax
0x18002e831  mov     ecx, 3; nIndex
0x18002e836  call    cs:__imp_GetSystemMetrics
0x18002e83c  mov     r14d, eax
0x18002e83f  movd    xmm0, esi
0x18002e843  cvtdq2pd xmm0, xmm0
0x18002e847  addsd   xmm0, xmm7
0x18002e84b  xorps   xmm1, xmm1
0x18002e84e  comisd  xmm1, xmm0
0x18002e852  jbe     short loc_18002E861
0x18002e854  mov     ecx, r15d
0x18002e857  sub     ecx, esi
0x18002e859  movd    xmm7, ecx
0x18002e85d  cvtdq2pd xmm7, xmm7
0x18002e861  movd    xmm0, edi
0x18002e865  cvtdq2pd xmm0, xmm0
0x18002e869  addsd   xmm0, xmm6
0x18002e86d  comisd  xmm1, xmm0
0x18002e871  jbe     short loc_18002E87D
0x18002e873  sub     eax, edi
0x18002e875  movd    xmm6, eax
0x18002e879  cvtdq2pd xmm6, xmm6
0x18002e87d  xorps   xmm0, xmm0
0x18002e880  movups  xmmword ptr [rsp+0E8h+var_60.left], xmm0
0x18002e888  lea     rdx, [rsp+0E8h+var_60]; lpRect
0x18002e890  mov     rcx, r12; hWnd
0x18002e893  call    cs:__imp_GetClientRect
0x18002e899  test    eax, eax
0x18002e89b  jnz     short loc_18002E8A7
0x18002e89d  mov     eax, 80131509h
0x18002e8a2  jmp     loc_18002EA51
0x18002e8a7  mov     eax, [rsp+0E8h+var_60.right]
0x18002e8ae  movd    xmm0, eax
0x18002e8b2  cvtdq2pd xmm0, xmm0
0x18002e8b6  comisd  xmm7, xmm0
0x18002e8ba  jbe     short loc_18002E8C7
0x18002e8bc  sub     eax, r15d
0x18002e8bf  movd    xmm7, eax
0x18002e8c3  cvtdq2pd xmm7, xmm7
0x18002e8c7  mov     eax, [rsp+0E8h+var_60.bottom]
0x18002e8ce  movd    xmm0, eax
0x18002e8d2  cvtdq2pd xmm0, xmm0
0x18002e8d6  comisd  xmm6, xmm0
0x18002e8da  jbe     short loc_18002E8E7
0x18002e8dc  sub     eax, r14d
0x18002e8df  movd    xmm6, eax
0x18002e8e3  cvtdq2pd xmm6, xmm6
0x18002e8e7  cvttsd2si edi, xmm6
0x18002e8eb  cvttsd2si esi, xmm7
0x18002e8ef  mov     [rsp+0E8h+uFlags], 15h; uFlags
0x18002e8f7  mov     [rsp+0E8h+cy], 0; cy
0x18002e8ff  mov     [rsp+0E8h+var_C8], 0; cx
0x18002e907  mov     r9d, edi; Y
0x18002e90a  mov     r8d, esi; X
0x18002e90d  xor     edx, edx; hWndInsertAfter
0x18002e90f  mov     rcx, rbx; hWnd
0x18002e912  call    cs:__imp_SetWindowPos
0x18002e918  test    eax, eax
0x18002e91a  jnz     short loc_18002E926
0x18002e91c  mov     eax, 80131509h
0x18002e921  jmp     loc_18002EA51
0x18002e926  xorps   xmm0, xmm0
0x18002e929  movups  xmmword ptr [rsp+0E8h+wndpl.length], xmm0
0x18002e92e  movups  xmmword ptr [rsp+0E8h+wndpl.ptMinPosition.y], xmm0
0x18002e933  movups  xmmword ptr [rsp+0E8h+wndpl.rcNormalPosition.left], xmm0
0x18002e938  mov     [rsp+0E8h+wndpl.length], 2Ch ; ','
0x18002e940  lea     rdx, [rsp+0E8h+wndpl]; lpwndpl
0x18002e945  mov     rcx, rbx; hWnd
0x18002e948  call    cs:__imp_GetWindowPlacement
0x18002e94e  test    eax, eax
0x18002e950  jnz     short loc_18002E95C
0x18002e952  mov     eax, 80131509h
0x18002e957  jmp     loc_18002EA51
0x18002e95c  mov     edx, 0FFFFFFF0h; nIndex
0x18002e961  mov     rcx, rbx; hWnd
0x18002e964  call    cs:__imp_GetWindowLongW
0x18002e96a  mov     rcx, rbx; hWnd
0x18002e96d  bt      eax, 1Dh
0x18002e971  jnb     short loc_18002E99F
0x18002e973  mov     [rsp+0E8h+wndpl.ptMinPosition.y], edi
0x18002e977  mov     [rsp+0E8h+wndpl.ptMinPosition.x], esi
0x18002e97b  mov     [rsp+0E8h+wndpl.flags], 1
0x18002e983  lea     rdx, [rsp+0E8h+wndpl]; lpwndpl
0x18002e988  call    ?SetWindowPlacementHelper@BasicHwndUtils@@SA_NPEAUHWND__@@PEBUtagWINDOWPLACEMENT@@@Z; BasicHwndUtils::SetWindowPlacementHelper(HWND__ *,tagWINDOWPLACEMENT const *)
0x18002e98d  test    al, al
0x18002e98f  jnz     loc_18002EA49
0x18002e995  mov     eax, 80131509h
0x18002e99a  jmp     loc_18002EA51
0x18002e99f  xorps   xmm0, xmm0
0x18002e9a2  movups  xmmword ptr [rsp+0E8h+Rect.left], xmm0
0x18002e9a7  lea     rdx, [rsp+0E8h+Rect]; lpRect
0x18002e9ac  call    cs:__imp_GetWindowRect
0x18002e9b2  test    eax, eax
0x18002e9b4  jnz     short loc_18002E9C0
0x18002e9b6  mov     eax, 80131509h
0x18002e9bb  jmp     loc_18002EA51
0x18002e9c0  lea     rdx, [rsp+0E8h+wndpl]; lpwndpl
0x18002e9c5  mov     rcx, rbx; hWnd
0x18002e9c8  call    ?SetWindowPlacementHelper@BasicHwndUtils@@SA_NPEAUHWND__@@PEBUtagWINDOWPLACEMENT@@@Z; BasicHwndUtils::SetWindowPlacementHelper(HWND__ *,tagWINDOWPLACEMENT const *)
0x18002e9cd  test    al, al
0x18002e9cf  jnz     short loc_18002E9D8
0x18002e9d1  mov     eax, 80131509h
0x18002e9d6  jmp     short loc_18002EA51
0x18002e9d8  mov     edi, [rsp+0E8h+Rect.bottom]
0x18002e9dc  sub     edi, [rsp+0E8h+Rect.top]
0x18002e9e0  mov     esi, [rsp+0E8h+Rect.right]
0x18002e9e4  sub     esi, [rsp+0E8h+Rect.left]
0x18002e9e8  lea     rdx, [rsp+0E8h+wndpl]; lpwndpl
0x18002e9ed  mov     rcx, rbx; hWnd
0x18002e9f0  call    cs:__imp_GetWindowPlacement
0x18002e9f6  test    eax, eax
0x18002e9f8  jnz     short loc_18002EA01
0x18002e9fa  mov     eax, 80131509h
0x18002e9ff  jmp     short loc_18002EA51
0x18002ea01  mov     eax, [rsp+0E8h+wndpl.rcNormalPosition.bottom]
0x18002ea08  mov     edx, [rsp+0E8h+wndpl.rcNormalPosition.top]
0x18002ea0c  sub     eax, edx
0x18002ea0e  mov     ecx, [rsp+0E8h+wndpl.rcNormalPosition.left]
0x18002ea12  cmp     edi, eax
0x18002ea14  jnz     short loc_18002EA20
0x18002ea16  mov     eax, [rsp+0E8h+wndpl.rcNormalPosition.right]
0x18002ea1a  sub     eax, ecx
0x18002ea1c  cmp     esi, eax
0x18002ea1e  jz      short loc_18002EA49
0x18002ea20  lea     eax, [rdi+rdx]
0x18002ea23  mov     [rsp+0E8h+wndpl.rcNormalPosition.bottom], eax
0x18002ea2a  lea     eax, [rsi+rcx]
0x18002ea2d  mov     [rsp+0E8h+wndpl.rcNormalPosition.right], eax
0x18002ea31  lea     rdx, [rsp+0E8h+wndpl]; lpwndpl
0x18002ea36  mov     rcx, rbx; hWnd
0x18002ea39  call    ?SetWindowPlacementHelper@BasicHwndUtils@@SA_NPEAUHWND__@@PEBUtagWINDOWPLACEMENT@@@Z; BasicHwndUtils::SetWindowPlacementHelper(HWND__ *,tagWINDOWPLACEMENT const *)
0x18002ea3e  test    al, al
0x18002ea40  jnz     short loc_18002EA49
0x18002ea42  mov     eax, 80131509h
0x18002ea47  jmp     short loc_18002EA51
0x18002ea49  xor     eax, eax
0x18002ea4b  jmp     short loc_18002EA51
0x18002ea4d  mov     eax, [rsp+0E8h+Points.x]
0x18002ea51  mov     rcx, [rsp+0E8h+var_50]
0x18002ea59  xor     rcx, rsp; StackCookie
0x18002ea5c  call    __security_check_cookie
0x18002ea61  lea     r11, [rsp+0E8h+var_28]
0x18002ea69  mov     rbx, [r11+48h]
0x18002ea6d  movaps  xmm6, xmmword ptr [r11-10h]
0x18002ea72  movaps  xmm7, xmmword ptr [r11-20h]
0x18002ea77  mov     rsp, r11
0x18002ea7a  pop     r15
0x18002ea7c  pop     r14
0x18002ea7e  pop     r12
0x18002ea80  pop     rdi
0x18002ea81  pop     rsi
0x18002ea82  retn
```
