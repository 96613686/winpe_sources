# MultiMonitorMoveInvalidator::MultiMonitorMoveInvalidator(HWND__ *,PointT<IntegerTypes> const &,Region *)

- ea: `0x1805433e8`
- end: `0x180543563`
- name: `??0MultiMonitorMoveInvalidator@@QEAA@PEAUHWND__@@AEBU?$PointT@UIntegerTypes@@@@PEAVRegion@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(LPARAM dwData)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180544af0`
- `0x18056021c`

## callees

- `0x18001db0c`
- `0x1805433e8`
- `0x18056bd00`

## import_xrefs

- `GDI32!CombineRgn` at `0x1805434e4`
- `GDI32!CombineRgn` at `0x180543520`
- `GDI32!CombineRgn` at `0x1805434e4`
- `GDI32!CombineRgn` at `0x180543520`
- `GDI32!GetRgnBox` at `0x1805434f9`
- `GDI32!GetRgnBox` at `0x1805434f9`
- `GDI32!CreateRectRgn` at `0x18054343d`
- `GDI32!CreateRectRgn` at `0x18054343d`
- `GDI32!DeleteObject` at `0x18054352e`
- `GDI32!DeleteObject` at `0x18054352e`
- `GDI32!CreateRectRgnIndirect` at `0x1805434cd`
- `GDI32!CreateRectRgnIndirect` at `0x1805434cd`
- `USER32!ScreenToClient` at `0x18054345d`
- `USER32!ScreenToClient` at `0x18054345d`
- `USER32!EnumDisplayMonitors` at `0x18054347e`
- `USER32!EnumDisplayMonitors` at `0x18054347e`
- `USER32!GetWindowRect` at `0x180543469`
- `USER32!GetWindowRect` at `0x180543469`

## pseudocode

```c
LPARAM __fastcall MultiMonitorMoveInvalidator::MultiMonitorMoveInvalidator(
        LPARAM dwData,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  RECT *v4; // r14
  HWND v7; // rcx
  __int64 v8; // rdx
  HRGN v9; // rbx
  struct tagRECT rc; // [rsp+20h] [rbp-30h] BYREF
  RECT rect; // [rsp+30h] [rbp-20h] BYREF

  *(_QWORD *)dwData = a2;
  v4 = (RECT *)(dwData + 24);
  *(_QWORD *)(dwData + 8) = 0;
  *(_QWORD *)(dwData + 16) = *a3;
  *(_QWORD *)(dwData + 24) = 0;
  *(_QWORD *)(dwData + 32) = 0;
  *(_QWORD *)(dwData + 40) = CreateRectRgn(0, 0, 0, 0);
  v7 = *(HWND *)dwData;
  *(_QWORD *)(dwData + 48) = a4;
  *(_DWORD *)(dwData + 56) = -1;
  *(_QWORD *)(dwData + 64) = 0;
  ScreenToClient(v7, (LPPOINT)(dwData + 8));
  GetWindowRect(*(HWND *)dwData, v4);
  EnumDisplayMonitors(0, v4, (MONITORENUMPROC)MultiMonitorMoveInvalidator::EnumDisplayCallback, dwData);
  v8 = v4->bottom - (__int64)v4->top;
  if ( (unsigned __int64)(v8 + 0x80000000LL) > 0xFFFFFFFF
    || (unsigned __int64)(v4->right - (__int64)v4->left + 0x80000000LL) > 0xFFFFFFFF )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  rect.right = v4->right - v4->left;
  *(_QWORD *)&rect.left = 0;
  rect.bottom = v8;
  v9 = CreateRectRgnIndirect(&rect);
  CombineRgn(v9, v9, *(HRGN *)(dwData + 40), 4);
  *(_QWORD *)&rc.left = 0;
  *(_QWORD *)&rc.right = 0;
  GetRgnBox(v9, &rc);
  if ( rc.left < rc.right && rc.top < rc.bottom )
    CombineRgn(**(HRGN **)(dwData + 48), **(HRGN **)(dwData + 48), v9, 2);
  if ( v9 )
    DeleteObject(v9);
  return dwData;
}

```

## disassembly

```asm
0x1805433e8  mov     [rsp-18h+arg_8], rbx
0x1805433ed  mov     [rsp-18h+arg_10], rsi
0x1805433f2  mov     [rsp-18h+arg_18], rdi
0x1805433f7  push    rbp
0x1805433f8  push    r14
0x1805433fa  push    r15
0x1805433fc  mov     rbp, rsp
0x1805433ff  sub     rsp, 50h
0x180543403  mov     rax, cs:__security_cookie
0x18054340a  xor     rax, rsp
0x18054340d  mov     [rbp+var_10], rax
0x180543411  mov     [rcx], rdx
0x180543414  lea     r14, [rcx+18h]
0x180543418  xor     r15d, r15d
0x18054341b  mov     rdi, r9
0x18054341e  mov     [rcx+8], r15
0x180543422  mov     rsi, rcx
0x180543425  mov     rax, [r8]
0x180543428  xor     r9d, r9d; y2
0x18054342b  mov     [rcx+10h], rax
0x18054342f  xor     r8d, r8d; x2
0x180543432  xor     ecx, ecx; x1
0x180543434  mov     [r14], r15
0x180543437  xor     edx, edx; y1
0x180543439  mov     [r14+8], r15
0x18054343d  call    cs:__imp_CreateRectRgn
0x180543443  mov     [rsi+28h], rax
0x180543447  lea     rdx, [rsi+8]; lpPoint
0x18054344b  mov     rcx, [rsi]; hWnd
0x18054344e  mov     [rsi+30h], rdi
0x180543452  mov     dword ptr [rsi+38h], 0FFFFFFFFh
0x180543459  mov     [rsi+40h], r15
0x18054345d  call    cs:__imp_ScreenToClient
0x180543463  mov     rcx, [rsi]; hWnd
0x180543466  mov     rdx, r14; lpRect
0x180543469  call    cs:__imp_GetWindowRect
0x18054346f  mov     r9, rsi; dwData
0x180543472  lea     r8, ?EnumDisplayCallback@MultiMonitorMoveInvalidator@@CAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x180543479  mov     rdx, r14; lprcClip
0x18054347c  xor     ecx, ecx; hdc
0x18054347e  call    cs:__imp_EnumDisplayMonitors
0x180543484  movsxd  rax, dword ptr [r14+4]
0x180543488  mov     r8d, 80000000h
0x18054348e  movsxd  rdx, dword ptr [r14+0Ch]
0x180543492  mov     r9d, 0FFFFFFFFh
0x180543498  sub     rdx, rax
0x18054349b  lea     rax, [rdx+r8]
0x18054349f  cmp     rax, r9
0x1805434a2  ja      loc_18054355D
0x1805434a8  movsxd  rax, dword ptr [r14]
0x1805434ab  movsxd  rcx, dword ptr [r14+8]
0x1805434af  sub     rcx, rax
0x1805434b2  lea     rax, [r8+rcx]
0x1805434b6  cmp     rax, r9
0x1805434b9  ja      loc_18054355D
0x1805434bf  mov     [rbp+rect.right], ecx
0x1805434c2  lea     rcx, [rbp+rect]; lprect
0x1805434c6  mov     qword ptr [rbp+rect.left], r15
0x1805434ca  mov     [rbp+rect.bottom], edx
0x1805434cd  call    cs:__imp_CreateRectRgnIndirect
0x1805434d3  mov     r8, [rsi+28h]; hrgnSrc2
0x1805434d7  lea     r9d, [r15+4]; iMode
0x1805434db  mov     rdx, rax; hrgnSrc1
0x1805434de  mov     rcx, rax; hrgnDst
0x1805434e1  mov     rbx, rax
0x1805434e4  call    cs:__imp_CombineRgn
0x1805434ea  lea     rdx, [rbp+rc]; lprc
0x1805434ee  mov     qword ptr [rbp+rc.left], r15
0x1805434f2  mov     rcx, rbx; hrgn
0x1805434f5  mov     qword ptr [rbp+rc.right], r15
0x1805434f9  call    cs:__imp_GetRgnBox
0x1805434ff  mov     eax, [rbp+rc.right]
0x180543502  cmp     [rbp+rc.left], eax
0x180543505  jge     short loc_180543526
0x180543507  mov     eax, [rbp+rc.bottom]
0x18054350a  cmp     [rbp+rc.top], eax
0x18054350d  jge     short loc_180543526
0x18054350f  mov     rax, [rsi+30h]
0x180543513  lea     r9d, [r15+2]; iMode
0x180543517  mov     r8, rbx; hrgnSrc2
0x18054351a  mov     rdx, [rax]; hrgnSrc1
0x18054351d  mov     rcx, rdx; hrgnDst
0x180543520  call    cs:__imp_CombineRgn
0x180543526  test    rbx, rbx
0x180543529  jz      short loc_180543534
0x18054352b  mov     rcx, rbx; ho
0x18054352e  call    cs:__imp_DeleteObject
0x180543534  mov     rax, rsi
0x180543537  mov     rcx, [rbp+var_10]
0x18054353b  xor     rcx, rsp; StackCookie
0x18054353e  call    __security_check_cookie
0x180543543  lea     r11, [rsp+50h+var_s0]
0x180543548  mov     rbx, [r11+28h]
0x18054354c  mov     rsi, [r11+30h]
0x180543550  mov     rdi, [r11+38h]
0x180543554  mov     rsp, r11
0x180543557  pop     r15
0x180543559  pop     r14
0x18054355b  pop     rbp
0x18054355c  retn
0x18054355d  call    ?SafeIntOnOverflow@SafeInt_InvalidParameter@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow(void)
```
