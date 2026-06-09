# EnsureWindowIsCompletelyOnScreen

- ea: `0x180109d94`
- end: `0x180109fc3`
- name: `EnsureWindowIsCompletelyOnScreen`
- size: `559`
- prototype: `__int64 __fastcall(LPRECT lprc, HMONITOR hMonitor)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180109ca0`
- `0x180134ac0`
- `0x18019229c`
- `0x18019a3d0`

## callees

- `0x18006c3c8`
- `0x180109d94`
- `0x18013f7d0`

## import_xrefs

- `USER32!EnumDisplayMonitors` at `0x180109eaf`
- `USER32!EnumDisplayMonitors` at `0x180109eaf`
- `USER32!OffsetRect` at `0x180109e36`
- `USER32!OffsetRect` at `0x180109f49`
- `USER32!OffsetRect` at `0x180109f7a`
- `USER32!OffsetRect` at `0x180109e36`
- `USER32!OffsetRect` at `0x180109f49`
- `USER32!OffsetRect` at `0x180109f7a`
- `USER32!CopyRect` at `0x180109f67`
- `USER32!CopyRect` at `0x180109f67`
- `USER32!GetMonitorInfoW` at `0x180109df9`
- `USER32!GetMonitorInfoW` at `0x180109df9`
- `USER32!IntersectRect` at `0x180109f5a`
- `USER32!IntersectRect` at `0x180109f5a`
- `USER32!MonitorFromRect` at `0x180109dd5`
- `USER32!MonitorFromRect` at `0x180109dd5`
- `USER32!EqualRect` at `0x180109e0f`
- `USER32!EqualRect` at `0x180109e0f`
- `GDI32!CreateRectRgnIndirect` at `0x180109e87`
- `GDI32!CreateRectRgnIndirect` at `0x180109e87`
- `GDI32!CreateRectRgn` at `0x180109e46`
- `GDI32!CreateRectRgn` at `0x180109e5a`
- `GDI32!CreateRectRgn` at `0x180109e71`
- `GDI32!CreateRectRgn` at `0x180109e46`
- `GDI32!CreateRectRgn` at `0x180109e5a`
- `GDI32!CreateRectRgn` at `0x180109e71`
- `GDI32!CombineRgn` at `0x180109ee1`
- `GDI32!CombineRgn` at `0x180109ee1`
- `GDI32!EqualRgn` at `0x180109eed`
- `GDI32!EqualRgn` at `0x180109eed`
- `GDI32!SetRectRgn` at `0x180109ecb`
- `GDI32!SetRectRgn` at `0x180109ecb`

## pseudocode

```c
int __fastcall EnsureWindowIsCompletelyOnScreen(LPRECT lprc, HMONITOR hMonitor)
{
  HMONITOR v4; // rax
  int result; // eax
  int v6; // esi
  int v7; // r14d
  HRGN v8; // rdi
  HRGN v9; // rbx
  int v10; // ecx
  int v11; // r9d
  bool v12; // cc
  int v13; // ecx
  int v14; // edx
  LPARAM dwData; // [rsp+30h] [rbp-29h] BYREF
  HRGN v16; // [rsp+38h] [rbp-21h] BYREF
  HRGN RectRgn; // [rsp+40h] [rbp-19h] BYREF
  struct tagMONITORINFO mi; // [rsp+48h] [rbp-11h] BYREF
  struct tagRECT rcDst; // [rsp+70h] [rbp+17h] BYREF

  if ( hMonitor )
    v4 = hMonitor;
  else
    v4 = MonitorFromRect(lprc, 2u);
  mi.cbSize = 40;
  memset(&mi.rcMonitor, 0, 36);
  result = GetMonitorInfoW(v4, &mi);
  if ( result )
  {
    if ( EqualRect(&mi.rcMonitor, &mi.rcWork) )
    {
      v6 = 0;
      v7 = 0;
    }
    else
    {
      v6 = mi.rcWork.left - mi.rcMonitor.left;
      v7 = mi.rcWork.top - mi.rcMonitor.top;
    }
    OffsetRect(lprc, v6, v7);
    dwData = (LPARAM)CreateRectRgn(0, 0, 0, 0);
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    v8 = RectRgn;
    v16 = CreateRectRgn(0, 0, 0, 0);
    v9 = v16;
    if ( hMonitor )
    {
      *(_QWORD *)&rcDst.left = CreateRectRgnIndirect(&mi.rcWork);
      dwData = *(_QWORD *)&rcDst.left;
      wil::details::unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>(&rcDst);
    }
    else
    {
      EnumDisplayMonitors(0, 0, GetDesktopRegionEnumProc, (LPARAM)&dwData);
    }
    SetRectRgn(v9, lprc->left, lprc->top, lprc->right, lprc->bottom);
    CombineRgn(v8, (HRGN)dwData, v9, 1);
    if ( !EqualRgn(v8, v9) )
    {
      v10 = mi.rcWork.top - lprc->top;
      if ( lprc->top >= mi.rcWork.top )
        v10 = 0;
      v11 = mi.rcWork.bottom - lprc->bottom;
      v12 = lprc->bottom <= mi.rcWork.bottom;
      rcDst = 0;
      if ( v12 )
        v11 = v10;
      v13 = mi.rcWork.left - lprc->left;
      if ( lprc->left >= mi.rcWork.left )
        v13 = 0;
      v14 = mi.rcWork.right - lprc->right;
      if ( lprc->right <= mi.rcWork.right )
        v14 = v13;
      OffsetRect(lprc, v14, v11);
      IntersectRect(&rcDst, lprc, &mi.rcWork);
      CopyRect(lprc, &rcDst);
    }
    OffsetRect(lprc, -v6, -v7);
    wil::details::unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>(&v16);
    wil::details::unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>(&RectRgn);
    return wil::details::unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>(&dwData);
  }
  return result;
}

```

## disassembly

```asm
0x180109d94  mov     [rsp-8+arg_10], rbx
0x180109d99  mov     [rsp-8+arg_18], rsi
0x180109d9e  push    rbp
0x180109d9f  push    rdi
0x180109da0  push    r12
0x180109da2  push    r14
0x180109da4  push    r15
0x180109da6  lea     rbp, [rsp-37h]
0x180109dab  sub     rsp, 90h
0x180109db2  mov     rax, cs:__security_cookie
0x180109db9  xor     rax, rsp
0x180109dbc  mov     [rbp+57h+var_30], rax
0x180109dc0  mov     r12, rdx
0x180109dc3  mov     r15, rcx
0x180109dc6  test    rdx, rdx
0x180109dc9  jz      short loc_180109DD0
0x180109dcb  mov     rax, rdx
0x180109dce  jmp     short loc_180109DDB
0x180109dd0  mov     edx, 2; dwFlags
0x180109dd5  call    cs:__imp_MonitorFromRect
0x180109ddb  xor     ecx, ecx
0x180109ddd  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x180109de4  xorps   xmm0, xmm0
0x180109de7  mov     [rbp+57h+mi.dwFlags], ecx
0x180109dea  mov     rcx, rax; hMonitor
0x180109ded  lea     rdx, [rbp+57h+mi]; lpmi
0x180109df1  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm0
0x180109df5  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm0
0x180109df9  call    cs:__imp_GetMonitorInfoW
0x180109dff  test    eax, eax
0x180109e01  jz      loc_180109F9B
0x180109e07  lea     rdx, [rbp+57h+mi.rcWork]; lprc2
0x180109e0b  lea     rcx, [rbp+57h+mi.rcMonitor]; lprc1
0x180109e0f  call    cs:__imp_EqualRect
0x180109e15  test    eax, eax
0x180109e17  jnz     short loc_180109E29
0x180109e19  mov     esi, [rbp+57h+mi.rcWork.left]
0x180109e1c  sub     esi, [rbp+57h+mi.rcMonitor.left]
0x180109e1f  mov     r14d, [rbp+57h+mi.rcWork.top]
0x180109e23  sub     r14d, [rbp+57h+mi.rcMonitor.top]
0x180109e27  jmp     short loc_180109E2E
0x180109e29  xor     esi, esi
0x180109e2b  xor     r14d, r14d
0x180109e2e  mov     r8d, r14d; dy
0x180109e31  mov     edx, esi; dx
0x180109e33  mov     rcx, r15; lprc
0x180109e36  call    cs:__imp_OffsetRect
0x180109e3c  xor     r9d, r9d; y2
0x180109e3f  xor     r8d, r8d; x2
0x180109e42  xor     edx, edx; y1
0x180109e44  xor     ecx, ecx; x1
0x180109e46  call    cs:__imp_CreateRectRgn
0x180109e4c  xor     r9d, r9d; y2
0x180109e4f  xor     r8d, r8d; x2
0x180109e52  xor     edx, edx; y1
0x180109e54  mov     [rbp+57h+dwData], rax
0x180109e58  xor     ecx, ecx; x1
0x180109e5a  call    cs:__imp_CreateRectRgn
0x180109e60  xor     r9d, r9d; y2
0x180109e63  xor     r8d, r8d; x2
0x180109e66  xor     edx, edx; y1
0x180109e68  mov     [rbp+57h+var_70], rax
0x180109e6c  xor     ecx, ecx; x1
0x180109e6e  mov     rdi, rax
0x180109e71  call    cs:__imp_CreateRectRgn
0x180109e77  mov     [rbp+57h+var_78], rax
0x180109e7b  mov     rbx, rax
0x180109e7e  test    r12, r12
0x180109e81  jz      short loc_180109EA0
0x180109e83  lea     rcx, [rbp+57h+mi.rcWork]; lprect
0x180109e87  call    cs:__imp_CreateRectRgnIndirect
0x180109e8d  lea     rcx, [rbp+57h+rcDst]
0x180109e91  mov     qword ptr [rbp+57h+rcDst.left], rax
0x180109e95  mov     [rbp+57h+dwData], rax
0x180109e99  call    ??1?$unique_storage@U?$resource_policy@PEAUHBRUSH__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>(void)
0x180109e9e  jmp     short loc_180109EB5
0x180109ea0  lea     r9, [rbp+57h+dwData]; dwData
0x180109ea4  xor     edx, edx; lprcClip
0x180109ea6  lea     r8, GetDesktopRegionEnumProc; lpfnEnum
0x180109ead  xor     ecx, ecx; hdc
0x180109eaf  call    cs:__imp_EnumDisplayMonitors
0x180109eb5  mov     eax, [r15+0Ch]
0x180109eb9  mov     rcx, rbx; hrgn
0x180109ebc  mov     r9d, [r15+8]; right
0x180109ec0  mov     r8d, [r15+4]; top
0x180109ec4  mov     edx, [r15]; left
0x180109ec7  mov     [rsp+0B0h+bottom], eax; bottom
0x180109ecb  call    cs:__imp_SetRectRgn
0x180109ed1  mov     rdx, [rbp+57h+dwData]; hrgnSrc1
0x180109ed5  mov     r9d, 1; iMode
0x180109edb  mov     r8, rbx; hrgnSrc2
0x180109ede  mov     rcx, rdi; hrgnDst
0x180109ee1  call    cs:__imp_CombineRgn
0x180109ee7  mov     rdx, rbx; hrgn2
0x180109eea  mov     rcx, rdi; hrgn1
0x180109eed  call    cs:__imp_EqualRgn
0x180109ef3  test    eax, eax
0x180109ef5  jnz     short loc_180109F6D
0x180109ef7  mov     edx, [rbp+57h+mi.rcWork.top]
0x180109efa  xorps   xmm0, xmm0
0x180109efd  mov     r8d, [rbp+57h+mi.rcWork.bottom]
0x180109f01  mov     ecx, edx
0x180109f03  sub     ecx, [r15+4]
0x180109f07  mov     r9d, r8d
0x180109f0a  cmp     [r15+4], edx
0x180109f0e  mov     r10d, [rbp+57h+mi.rcWork.left]
0x180109f12  mov     r11d, [rbp+57h+mi.rcWork.right]
0x180109f16  cmovge  ecx, eax
0x180109f19  sub     r9d, [r15+0Ch]
0x180109f1d  mov     edx, r11d
0x180109f20  cmp     [r15+0Ch], r8d
0x180109f24  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180109f28  cmovle  r9d, ecx
0x180109f2c  mov     ecx, r10d
0x180109f2f  sub     ecx, [r15]
0x180109f32  mov     r8d, r9d; dy
0x180109f35  cmp     [r15], r10d
0x180109f38  cmovge  ecx, eax
0x180109f3b  sub     edx, [r15+8]
0x180109f3f  cmp     [r15+8], r11d
0x180109f43  cmovle  edx, ecx; dx
0x180109f46  mov     rcx, r15; lprc
0x180109f49  call    cs:__imp_OffsetRect
0x180109f4f  lea     r8, [rbp+57h+mi.rcWork]; lprcSrc2
0x180109f53  mov     rdx, r15; lprcSrc1
0x180109f56  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180109f5a  call    cs:__imp_IntersectRect
0x180109f60  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x180109f64  mov     rcx, r15; lprcDst
0x180109f67  call    cs:__imp_CopyRect
0x180109f6d  neg     r14d
0x180109f70  neg     esi
0x180109f72  mov     r8d, r14d; dy
0x180109f75  mov     edx, esi; dx
0x180109f77  mov     rcx, r15; lprc
0x180109f7a  call    cs:__imp_OffsetRect
0x180109f80  lea     rcx, [rbp+57h+var_78]
0x180109f84  call    ??1?$unique_storage@U?$resource_policy@PEAUHBRUSH__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>(void)
0x180109f89  lea     rcx, [rbp+57h+var_70]
0x180109f8d  call    ??1?$unique_storage@U?$resource_policy@PEAUHBRUSH__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>(void)
0x180109f92  lea     rcx, [rbp+57h+dwData]
0x180109f96  call    ??1?$unique_storage@U?$resource_policy@PEAUHBRUSH__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBRUSH__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBRUSH__ *,HBRUSH__ *,0,std::nullptr_t>>(void)
0x180109f9b  mov     rcx, [rbp+57h+var_30]
0x180109f9f  xor     rcx, rsp; StackCookie
0x180109fa2  call    __security_check_cookie
0x180109fa7  lea     r11, [rsp+0B0h+var_20]
0x180109faf  mov     rbx, [r11+40h]
0x180109fb3  mov     rsi, [r11+48h]
0x180109fb7  mov     rsp, r11
0x180109fba  pop     r15
0x180109fbc  pop     r14
0x180109fbe  pop     r12
0x180109fc0  pop     rdi
0x180109fc1  pop     rbp
0x180109fc2  retn
```
