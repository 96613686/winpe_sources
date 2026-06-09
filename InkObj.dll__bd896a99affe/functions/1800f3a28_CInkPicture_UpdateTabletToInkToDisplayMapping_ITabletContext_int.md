# CInkPicture::_UpdateTabletToInkToDisplayMapping(ITabletContext *,int)

- ea: `0x1800f3a28`
- end: `0x1800f3fcc`
- name: `?_UpdateTabletToInkToDisplayMapping@CInkPicture@@AEAAJPEAUITabletContext@@H@Z`
- size: `1444`
- prototype: `__int64 __fastcall(CInkPicture *__hidden this, struct ITabletContext *, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800e7eb0`
- `0x1800ec650`
- `0x1800ed700`
- `0x1800ef104`

## callees

- `0x180001c20`
- `0x1800211c0`
- `0x180026ca0`
- `0x1800365f8`
- `0x180036824`
- `0x18003821c`
- `0x1800f38a0`
- `0x1800f3a28`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f3b41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f3b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3b61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3a5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3a75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3a5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3a75`
- `USER32!IsRectEmpty` at `0x1800f3ac5`
- `USER32!IsRectEmpty` at `0x1800f3ae6`
- `USER32!IsRectEmpty` at `0x1800f3ac5`
- `USER32!IsRectEmpty` at `0x1800f3ae6`
- `USER32!GetDC` at `0x1800f3cea`
- `USER32!GetDC` at `0x1800f3cea`
- `USER32!ReleaseDC` at `0x1800f3d1f`
- `USER32!ReleaseDC` at `0x1800f3d1f`
- `USER32!MapWindowPoints` at `0x1800f3b5b`
- `USER32!MapWindowPoints` at `0x1800f3b5b`
- `USER32!GetClientRect` at `0x1800f3adb`
- `USER32!GetClientRect` at `0x1800f3adb`
- `GDI32!CombineTransform` at `0x1800f3d31`
- `GDI32!CombineTransform` at `0x1800f3d44`
- `GDI32!CombineTransform` at `0x1800f3edd`
- `GDI32!CombineTransform` at `0x1800f3d31`
- `GDI32!CombineTransform` at `0x1800f3d44`
- `GDI32!CombineTransform` at `0x1800f3edd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInkPicture::_UpdateTabletToInkToDisplayMapping(
        CInkPicture *this,
        struct ITabletContext *a2,
        int a3)
{
  int updated; // ebx
  int v8; // eax
  signed int LastError; // eax
  HDC DC; // rbx
  float v11; // xmm3_4
  float v12; // xmm2_4
  float v13; // xmm0_4
  float v14; // xmm2_4
  float v15; // xmm0_4
  int v16; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID v18; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[24]; // [rsp+38h] [rbp-C8h] BYREF
  struct tagPOINT Points[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-A0h] BYREF
  struct _XFORM v23; // [rsp+70h] [rbp-90h] BYREF
  struct tagXFORM v24; // [rsp+88h] [rbp-78h] BYREF
  XFORM v25; // [rsp+A0h] [rbp-60h] BYREF
  XFORM v26; // [rsp+B8h] [rbp-48h] BYREF
  XFORM xf1; // [rsp+D0h] [rbp-30h] BYREF
  XFORM v28; // [rsp+E8h] [rbp-18h] BYREF
  struct _XFORM xfOut; // [rsp+100h] [rbp+0h] BYREF
  struct _XFORM v30; // [rsp+118h] [rbp+18h] BYREF
  XFORM xf2; // [rsp+130h] [rbp+30h] BYREF

  updated = 0;
  if ( GetCurrentThreadId() == *((_DWORD *)this + 123) )
    return 2147746359LL;
  _InterlockedExchange((volatile __int32 *)this + 123, GetCurrentThreadId());
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v20, (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
  if ( *((_BYTE *)this + 488) )
  {
    Rect = (struct tagRECT)*((_OWORD *)this + 35);
    if ( IsRectEmpty((const RECT *)this + 35) )
    {
      GetClientRect(*((HWND *)this + 21), &Rect);
      if ( IsRectEmpty(&Rect) )
      {
        *((_DWORD *)this + 156) = 1;
        v8 = 0;
      }
      else
      {
        v8 = 0;
        if ( a3 )
        {
          v8 = (*(__int64 (__fastcall **)(struct ITabletContext *, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0);
          updated = v8;
          if ( v8 >= 0 )
            goto LABEL_17;
          *((_DWORD *)this + 156) = 1;
        }
      }
    }
    else
    {
      if ( !a3 )
        goto LABEL_17;
      *(struct tagRECT *)&Points[0].x = Rect;
      SetLastError(0);
      MapWindowPoints(*((HWND *)this + 21), 0, Points, 2u);
      LastError = GetLastError();
      updated = LastError;
      if ( LastError > 0 )
        updated = (unsigned __int16)LastError | 0x80070000;
      if ( updated < 0 )
        goto LABEL_41;
      v8 = (*(__int64 (__fastcall **)(struct ITabletContext *, struct tagPOINT *))(*(_QWORD *)a2 + 96LL))(a2, Points);
      updated = v8;
    }
    if ( v8 < 0 )
    {
LABEL_41:
      _InterlockedExchange((volatile __int32 *)this + 123, 0);
      goto LABEL_42;
    }
LABEL_17:
    if ( !*((_DWORD *)this + 156) )
    {
      *(_OWORD *)&Points[0].x = 0;
      updated = (*(__int64 (__fastcall **)(struct ITabletContext *, struct tagPOINT *))(*(_QWORD *)a2 + 112LL))(
                  a2,
                  Points);
      v17 = updated;
      if ( updated >= 0 )
      {
        CIXForm::CIXForm(&ppv, &v17);
        updated = v17;
        if ( v17 >= 0 )
        {
          CIXForm::CIXForm(&v18, &v17);
          updated = v17;
          if ( v17 >= 0 )
          {
            memset(&v26, 0, sizeof(v26));
            memset(&xf1, 0, sizeof(xf1));
            updated = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)this + 75) + 72LL))(
                        *((_QWORD *)this + 75),
                        ppv);
            if ( updated >= 0 )
            {
              v26 = *(XFORM *)CIXForm::GetXForm((CIXForm *)&ppv, (struct tagXFORM *)&xf2);
              updated = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)this + 75) + 56LL))(
                          *((_QWORD *)this + 75),
                          v18);
              if ( updated >= 0 )
              {
                xf1 = *(XFORM *)CIXForm::GetXForm((CIXForm *)&v18, &v24);
                *(_OWORD *)&xfOut.eM11 = xmmword_1801265A0;
                *(_QWORD *)&xfOut.eDx = 0;
                *(_OWORD *)&v23.eM11 = xmmword_1801265A0;
                *(_QWORD *)&v23.eDx = 0;
                *(_OWORD *)&v25.eM11 = xmmword_1801265A0;
                *(_QWORD *)&v25.eDx = 0;
                *(_OWORD *)&v28.eM11 = xmmword_1801265A0;
                *(_QWORD *)&v28.eDx = 0;
                *(_OWORD *)&v30.eM11 = xmmword_1801265A0;
                *(_QWORD *)&v30.eDx = 0;
                DC = GetDC(*((HWND *)this + 21));
                xf2 = *(XFORM *)GetHiMetricToPixelXForm(&v24, DC);
                if ( DC )
                  ReleaseDC(*((HWND *)this + 21), DC);
                CombineTransform(&xfOut, &xf1, &xf2);
                CombineTransform(&v23, &v26, &xfOut);
                v11 = (float)(v23.eM11 * v23.eM22) - (float)(v23.eM12 * v23.eM21);
                if ( v11 >= 0.000000001 || v11 <= -0.000000001 )
                {
                  v25.eM11 = v23.eM22 / v11;
                  v25.eM12 = COERCE_FLOAT(LODWORD(v23.eM12) ^ _xmm) / v11;
                  v25.eM21 = COERCE_FLOAT(LODWORD(v23.eM21) ^ _xmm) / v11;
                  v25.eM22 = v23.eM11 / v11;
                  v25.eDx = (float)((float)(v23.eDy * v23.eM21) - (float)(v23.eM22 * v23.eDx)) / v11;
                  v25.eDy = (float)((float)(v23.eM12 * v23.eDx) - (float)(v23.eDy * v23.eM11)) / v11;
                  *(_QWORD *)&v24.eM11 = 0;
                  *(_QWORD *)&v24.eM21 = 0;
                  v12 = (float)(Rect.right - Rect.left);
                  v13 = (float)(Points[1].x - Points[0].x);
                  if ( v13 >= 1.0 )
                    v12 = v12 / v13;
                  v24.eM11 = v12;
                  v24.eDx = (float)Rect.left - (float)((float)Points[0].x * v12);
                  v14 = (float)(Rect.bottom - Rect.top);
                  v15 = (float)(Points[1].y - Points[0].y);
                  if ( v15 >= 1.0 )
                    v14 = v14 / v15;
                  v24.eM22 = v14;
                  v24.eDy = (float)Rect.top - (float)((float)Points[0].y * v14);
                  v28 = (XFORM)v24;
                  CombineTransform(&v30, &v28, &v25);
                  v17 = 0;
                  updated = (*(__int64 (__fastcall **)(struct ITabletContext *, int *))(*(_QWORD *)a2 + 24LL))(a2, &v17);
                  if ( updated >= 0 )
                  {
                    updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _XFORM *))(**((_QWORD **)this + 96)
                                                                                         + 40LL))(
                                *((_QWORD *)this + 96),
                                (unsigned int)v17,
                                &v30);
                    if ( updated >= 0 )
                    {
                      updated = (*(__int64 (__fastcall **)(_QWORD, XFORM *))(**((_QWORD **)this + 101) + 56LL))(
                                  *((_QWORD *)this + 101),
                                  &v26);
                      if ( updated >= 0 )
                        updated = (*(__int64 (__fastcall **)(_QWORD, struct _XFORM *))(**((_QWORD **)this + 101) + 48LL))(
                                    *((_QWORD *)this + 101),
                                    &xfOut);
                    }
                  }
                }
                else
                {
                  updated = -2147467259;
                }
              }
            }
          }
          ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v18);
          if ( updated >= 0 )
          {
            v16 = 0;
            if ( *((_DWORD *)this + 168) != 1 )
              v16 = *((_DWORD *)this + 268);
            updated = CInkPicture::_UpdateSelectionRect(this, v16 == 2);
          }
        }
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppv);
      }
    }
    goto LABEL_41;
  }
  *((_DWORD *)this + 156) = 1;
  _InterlockedExchange((volatile __int32 *)this + 123, 0);
  updated = 0;
LABEL_42:
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v20);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800f3a28  mov     [rsp-8+arg_10], rbx
0x1800f3a2d  mov     [rsp-8+arg_18], rsi
0x1800f3a32  push    rbp
0x1800f3a33  push    rdi
0x1800f3a34  push    r14
0x1800f3a36  lea     rbp, [rsp-50h]
0x1800f3a3b  sub     rsp, 150h
0x1800f3a42  mov     rax, cs:__security_cookie
0x1800f3a49  xor     rax, rsp
0x1800f3a4c  mov     [rbp+60h+var_18], rax
0x1800f3a50  mov     r14d, r8d
0x1800f3a53  mov     rsi, rdx
0x1800f3a56  mov     rdi, rcx
0x1800f3a59  xor     ebx, ebx
0x1800f3a5b  call    cs:__imp_GetCurrentThreadId
0x1800f3a61  mov     ecx, [rdi+1ECh]
0x1800f3a67  cmp     eax, ecx
0x1800f3a69  jnz     short loc_1800F3A75
0x1800f3a6b  mov     eax, 80040237h
0x1800f3a70  jmp     loc_1800F3FA8
0x1800f3a75  call    cs:__imp_GetCurrentThreadId
0x1800f3a7b  xchg    eax, [rdi+1ECh]
0x1800f3a81  lea     rdx, [rdi+1F0h]; struct _RTL_CRITICAL_SECTION *
0x1800f3a88  lea     rcx, [rsp+160h+var_128]; this
0x1800f3a8d  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800f3a92  nop
0x1800f3a93  cmp     byte ptr [rdi+1E8h], 0
0x1800f3a9a  jnz     short loc_1800F3AB5
0x1800f3a9c  mov     dword ptr [rdi+270h], 1
0x1800f3aa6  xor     eax, eax
0x1800f3aa8  xchg    eax, [rdi+1ECh]
0x1800f3aae  xor     ebx, ebx
0x1800f3ab0  jmp     loc_1800F3F9C
0x1800f3ab5  lea     rcx, [rdi+230h]; lprc
0x1800f3abc  movups  xmm0, xmmword ptr [rcx]
0x1800f3abf  movdqu  xmmword ptr [rsp+160h+Rect.left], xmm0
0x1800f3ac5  call    cs:__imp_IsRectEmpty
0x1800f3acb  test    eax, eax
0x1800f3acd  jz      short loc_1800F3B2F
0x1800f3acf  lea     rdx, [rsp+160h+Rect]; lpRect
0x1800f3ad4  mov     rcx, [rdi+0A8h]; hWnd
0x1800f3adb  call    cs:__imp_GetClientRect
0x1800f3ae1  lea     rcx, [rsp+160h+Rect]; lprc
0x1800f3ae6  call    cs:__imp_IsRectEmpty
0x1800f3aec  test    eax, eax
0x1800f3aee  jz      short loc_1800F3B01
0x1800f3af0  mov     dword ptr [rdi+270h], 1
0x1800f3afa  xor     eax, eax
0x1800f3afc  jmp     loc_1800F3B94
0x1800f3b01  xor     eax, eax
0x1800f3b03  test    r14d, r14d
0x1800f3b06  jz      loc_1800F3B94
0x1800f3b0c  mov     rax, [rsi]
0x1800f3b0f  xor     edx, edx
0x1800f3b11  mov     rcx, rsi
0x1800f3b14  mov     rax, [rax+60h]
0x1800f3b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3b1d  mov     ebx, eax
0x1800f3b1f  test    eax, eax
0x1800f3b21  jns     short loc_1800F3B9C
0x1800f3b23  mov     dword ptr [rdi+270h], 1
0x1800f3b2d  jmp     short loc_1800F3B94
0x1800f3b2f  test    r14d, r14d
0x1800f3b32  jz      short loc_1800F3B9C
0x1800f3b34  movaps  xmm0, xmmword ptr [rsp+160h+Rect.left]
0x1800f3b39  movdqa  xmmword ptr [rsp+160h+Points.x], xmm0
0x1800f3b3f  xor     ecx, ecx; dwErrCode
0x1800f3b41  call    cs:__imp_SetLastError
0x1800f3b47  mov     r9d, 2; cPoints
0x1800f3b4d  lea     r8, [rsp+160h+Points]; lpPoints
0x1800f3b52  xor     edx, edx; hWndTo
0x1800f3b54  mov     rcx, [rdi+0A8h]; hWndFrom
0x1800f3b5b  call    cs:__imp_MapWindowPoints
0x1800f3b61  call    cs:__imp_GetLastError
0x1800f3b67  mov     ebx, eax
0x1800f3b69  test    eax, eax
0x1800f3b6b  jle     short loc_1800F3B76
0x1800f3b6d  movzx   ebx, ax
0x1800f3b70  or      ebx, 80070000h
0x1800f3b76  test    ebx, ebx
0x1800f3b78  js      loc_1800F3F94
0x1800f3b7e  mov     rax, [rsi]
0x1800f3b81  lea     rdx, [rsp+160h+Points]
0x1800f3b86  mov     rcx, rsi
0x1800f3b89  mov     rax, [rax+60h]
0x1800f3b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3b92  mov     ebx, eax
0x1800f3b94  test    eax, eax
0x1800f3b96  js      loc_1800F3F94
0x1800f3b9c  cmp     dword ptr [rdi+270h], 0
0x1800f3ba3  jnz     loc_1800F3F94
0x1800f3ba9  xorps   xmm0, xmm0
0x1800f3bac  movdqu  xmmword ptr [rsp+160h+Points.x], xmm0
0x1800f3bb2  mov     rax, [rsi]
0x1800f3bb5  lea     rdx, [rsp+160h+Points]
0x1800f3bba  mov     rcx, rsi
0x1800f3bbd  mov     rax, [rax+70h]
0x1800f3bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3bc6  mov     ebx, eax
0x1800f3bc8  mov     [rsp+160h+var_140], eax
0x1800f3bcc  test    eax, eax
0x1800f3bce  js      loc_1800F3F94
0x1800f3bd4  lea     rdx, [rsp+160h+var_140]; int *
0x1800f3bd9  lea     rcx, [rsp+160h+ppv]; ppv
0x1800f3bde  call    ??0CIXForm@@QEAA@AEAJ@Z; CIXForm::CIXForm(long &)
0x1800f3be3  nop
0x1800f3be4  mov     ebx, [rsp+160h+var_140]
0x1800f3be8  test    ebx, ebx
0x1800f3bea  js      loc_1800F3F8A
0x1800f3bf0  lea     rdx, [rsp+160h+var_140]; int *
0x1800f3bf5  lea     rcx, [rsp+160h+var_138]; ppv
0x1800f3bfa  call    ??0CIXForm@@QEAA@AEAJ@Z; CIXForm::CIXForm(long &)
0x1800f3bff  nop
0x1800f3c00  mov     ebx, [rsp+160h+var_140]
0x1800f3c04  test    ebx, ebx
0x1800f3c06  js      loc_1800F3F5C
0x1800f3c0c  xorps   xmm0, xmm0
0x1800f3c0f  xor     eax, eax
0x1800f3c11  movups  xmmword ptr [rbp+60h+var_A8.eM11], xmm0
0x1800f3c15  mov     qword ptr [rbp+60h+var_A8.eDx], rax
0x1800f3c19  xorps   xmm1, xmm1
0x1800f3c1c  movups  xmmword ptr [rbp+60h+xf1.eM11], xmm1
0x1800f3c20  mov     qword ptr [rbp+60h+xf1.eDx], rax
0x1800f3c24  mov     rcx, [rdi+258h]
0x1800f3c2b  mov     rax, [rcx]
0x1800f3c2e  mov     rdx, [rsp+160h+ppv]
0x1800f3c33  mov     rax, [rax+48h]
0x1800f3c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3c3c  mov     ebx, eax
0x1800f3c3e  test    eax, eax
0x1800f3c40  js      loc_1800F3F5C
0x1800f3c46  lea     rdx, [rbp+60h+xf2]; retstr
0x1800f3c4a  lea     rcx, [rsp+160h+ppv]; this
0x1800f3c4f  call    ?GetXForm@CIXForm@@QEBA?AUtagXFORM@@XZ; CIXForm::GetXForm(void)
0x1800f3c54  movups  xmm0, xmmword ptr [rax]
0x1800f3c57  movups  xmmword ptr [rbp+60h+var_A8.eM11], xmm0
0x1800f3c5b  movsd   xmm1, qword ptr [rax+10h]
0x1800f3c60  movsd   qword ptr [rbp+60h+var_A8.eDx], xmm1
0x1800f3c65  mov     rcx, [rdi+258h]
0x1800f3c6c  mov     rax, [rcx]
0x1800f3c6f  mov     rdx, [rsp+160h+var_138]
0x1800f3c74  mov     rax, [rax+38h]
0x1800f3c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3c7d  mov     ebx, eax
0x1800f3c7f  test    eax, eax
0x1800f3c81  js      loc_1800F3F5C
0x1800f3c87  lea     rdx, [rbp+60h+var_D8]; retstr
0x1800f3c8b  lea     rcx, [rsp+160h+var_138]; this
0x1800f3c90  call    ?GetXForm@CIXForm@@QEBA?AUtagXFORM@@XZ; CIXForm::GetXForm(void)
0x1800f3c95  movups  xmm0, xmmword ptr [rax]
0x1800f3c98  movups  xmmword ptr [rbp+60h+xf1.eM11], xmm0
0x1800f3c9c  movsd   xmm1, qword ptr [rax+10h]
0x1800f3ca1  movsd   qword ptr [rbp+60h+xf1.eDx], xmm1
0x1800f3ca6  movups  xmm2, cs:xmmword_1801265A0
0x1800f3cad  movups  xmmword ptr [rbp+60h+xfOut.eM11], xmm2
0x1800f3cb1  movsd   xmm0, cs:qword_1801265B0
0x1800f3cb9  movsd   qword ptr [rbp+60h+xfOut.eDx], xmm0
0x1800f3cbe  movups  xmmword ptr [rsp+160h+var_F0.eM11], xmm2
0x1800f3cc3  movsd   qword ptr [rbp+60h+var_F0.eDx], xmm0
0x1800f3cc8  movups  xmmword ptr [rbp+60h+var_C0.eM11], xmm2
0x1800f3ccc  movsd   qword ptr [rbp+60h+var_C0.eDx], xmm0
0x1800f3cd1  movups  xmmword ptr [rbp+60h+var_78.eM11], xmm2
0x1800f3cd5  movsd   qword ptr [rbp+60h+var_78.eDx], xmm0
0x1800f3cda  movups  xmmword ptr [rbp+60h+var_48.eM11], xmm2
0x1800f3cde  movsd   qword ptr [rbp+60h+var_48.eDx], xmm0
0x1800f3ce3  mov     rcx, [rdi+0A8h]; hWnd
0x1800f3cea  call    cs:__imp_GetDC
0x1800f3cf0  mov     rbx, rax
0x1800f3cf3  mov     rdx, rax; HDC
0x1800f3cf6  lea     rcx, [rbp+60h+var_D8]; retstr
0x1800f3cfa  call    ?GetHiMetricToPixelXForm@@YA?AUtagXFORM@@PEAUHDC__@@@Z; GetHiMetricToPixelXForm(HDC__ *)
0x1800f3cff  movups  xmm0, xmmword ptr [rax]
0x1800f3d02  movups  xmmword ptr [rbp+60h+xf2.eM11], xmm0
0x1800f3d06  movsd   xmm1, qword ptr [rax+10h]
0x1800f3d0b  movsd   qword ptr [rbp+60h+xf2.eDx], xmm1
0x1800f3d10  test    rbx, rbx
0x1800f3d13  jz      short loc_1800F3D25
0x1800f3d15  mov     rdx, rbx; hDC
0x1800f3d18  mov     rcx, [rdi+0A8h]; hWnd
0x1800f3d1f  call    cs:__imp_ReleaseDC
0x1800f3d25  lea     r8, [rbp+60h+xf2]; lpxf2
0x1800f3d29  lea     rdx, [rbp+60h+xf1]; lpxf1
0x1800f3d2d  lea     rcx, [rbp+60h+xfOut]; lpxfOut
0x1800f3d31  call    cs:__imp_CombineTransform
0x1800f3d37  lea     r8, [rbp+60h+xfOut]; lpxf2
0x1800f3d3b  lea     rdx, [rbp+60h+var_A8]; lpxf1
0x1800f3d3f  lea     rcx, [rsp+160h+var_F0]; lpxfOut
0x1800f3d44  call    cs:__imp_CombineTransform
0x1800f3d4a  movss   xmm3, [rsp+160h+var_F0.eM11]
0x1800f3d50  movss   xmm5, [rsp+160h+var_F0.eM22]
0x1800f3d56  mulss   xmm3, xmm5
0x1800f3d5a  movss   xmm4, [rsp+160h+var_F0.eM12]
0x1800f3d60  movaps  xmm0, xmm4
0x1800f3d63  mulss   xmm0, [rsp+160h+var_F0.eM21]
0x1800f3d69  subss   xmm3, xmm0
0x1800f3d6d  cvtps2pd xmm1, xmm3
0x1800f3d70  movsd   xmm0, cs:__real@3e112e0be826d695
0x1800f3d78  comisd  xmm0, xmm1
0x1800f3d7c  jbe     short loc_1800F3D92
0x1800f3d7e  comisd  xmm1, cs:__real@be112e0be826d695
0x1800f3d86  jbe     short loc_1800F3D92
0x1800f3d88  mov     ebx, 80004005h
0x1800f3d8d  jmp     loc_1800F3F5C
0x1800f3d92  movaps  xmm0, xmm5
0x1800f3d95  divss   xmm0, xmm3
0x1800f3d99  movss   [rbp+60h+var_C0.eM11], xmm0
0x1800f3d9e  movaps  xmm1, xmm4
0x1800f3da1  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x1800f3da8  divss   xmm1, xmm3
0x1800f3dac  movss   [rbp+60h+var_C0.eM12], xmm1
0x1800f3db1  movss   xmm0, [rsp+160h+var_F0.eM21]
0x1800f3db7  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x1800f3dbe  divss   xmm0, xmm3
0x1800f3dc2  movss   [rbp+60h+var_C0.eM21], xmm0
0x1800f3dc7  movss   xmm0, [rsp+160h+var_F0.eM11]
0x1800f3dcd  divss   xmm0, xmm3
0x1800f3dd1  movss   [rbp+60h+var_C0.eM22], xmm0
0x1800f3dd6  movss   xmm2, [rbp+60h+var_F0.eDy]
0x1800f3ddb  movaps  xmm1, xmm2
0x1800f3dde  mulss   xmm1, [rsp+160h+var_F0.eM21]
0x1800f3de4  mulss   xmm5, [rbp+60h+var_F0.eDx]
0x1800f3de9  subss   xmm1, xmm5
0x1800f3ded  divss   xmm1, xmm3
0x1800f3df1  movss   [rbp+60h+var_C0.eDx], xmm1
0x1800f3df6  mulss   xmm4, [rbp+60h+var_F0.eDx]
0x1800f3dfb  mulss   xmm2, [rsp+160h+var_F0.eM11]
0x1800f3e01  subss   xmm4, xmm2
0x1800f3e05  divss   xmm4, xmm3
0x1800f3e09  movss   [rbp+60h+var_C0.eDy], xmm4
0x1800f3e0e  mov     ecx, [rsp+160h+Rect.right]
0x1800f3e12  mov     edx, [rsp+160h+Rect.bottom]
0x1800f3e16  mov     eax, [rsp+160h+Points.x+8]
0x1800f3e1a  mov     r8d, [rsp+160h+Points.y+8]
0x1800f3e1f  mov     qword ptr [rbp+60h+var_D8.eM11], 0
0x1800f3e27  mov     qword ptr [rbp+60h+var_D8.eM21], 0
0x1800f3e2f  sub     ecx, [rsp+160h+Rect.left]
0x1800f3e33  movd    xmm2, ecx
0x1800f3e37  cvtdq2ps xmm2, xmm2
0x1800f3e3a  sub     eax, [rsp+160h+Points.x]
0x1800f3e3e  movd    xmm0, eax
0x1800f3e42  cvtdq2ps xmm0, xmm0
0x1800f3e45  movss   xmm3, cs:__real@3f800000
0x1800f3e4d  comiss  xmm3, xmm0
0x1800f3e50  ja      short loc_1800F3E56
0x1800f3e52  divss   xmm2, xmm0
0x1800f3e56  movss   [rbp+60h+var_D8.eM11], xmm2
0x1800f3e5b  movd    xmm1, [rsp+160h+Rect.left]
0x1800f3e61  cvtdq2ps xmm1, xmm1
0x1800f3e64  movd    xmm0, [rsp+160h+Points.x]
0x1800f3e6a  cvtdq2ps xmm0, xmm0
0x1800f3e6d  mulss   xmm0, xmm2
0x1800f3e71  subss   xmm1, xmm0
0x1800f3e75  movss   [rbp+60h+var_D8.eDx], xmm1
0x1800f3e7a  sub     edx, [rsp+160h+Rect.top]
0x1800f3e7e  movd    xmm2, edx
0x1800f3e82  cvtdq2ps xmm2, xmm2
0x1800f3e85  sub     r8d, [rsp+160h+Points.y]
0x1800f3e8a  movd    xmm0, r8d
0x1800f3e8f  cvtdq2ps xmm0, xmm0
0x1800f3e92  comiss  xmm3, xmm0
0x1800f3e95  ja      short loc_1800F3E9B
0x1800f3e97  divss   xmm2, xmm0
0x1800f3e9b  movss   [rbp+60h+var_D8.eM22], xmm2
0x1800f3ea0  movd    xmm1, [rsp+160h+Rect.top]
0x1800f3ea6  cvtdq2ps xmm1, xmm1
0x1800f3ea9  movd    xmm0, [rsp+160h+Points.y]
0x1800f3eaf  cvtdq2ps xmm0, xmm0
0x1800f3eb2  mulss   xmm0, xmm2
0x1800f3eb6  subss   xmm1, xmm0
0x1800f3eba  movss   [rbp+60h+var_D8.eDy], xmm1
0x1800f3ebf  movups  xmm0, xmmword ptr [rbp+60h+var_D8.eM11]
0x1800f3ec3  movups  xmmword ptr [rbp+60h+var_78.eM11], xmm0
0x1800f3ec7  movsd   xmm1, qword ptr [rbp+60h+var_D8.eDx]
0x1800f3ecc  movsd   qword ptr [rbp+60h+var_78.eDx], xmm1
0x1800f3ed1  lea     r8, [rbp+60h+var_C0]; lpxf2
0x1800f3ed5  lea     rdx, [rbp+60h+var_78]; lpxf1
0x1800f3ed9  lea     rcx, [rbp+60h+var_48]; lpxfOut
0x1800f3edd  call    cs:__imp_CombineTransform
0x1800f3ee3  mov     [rsp+160h+var_140], 0
0x1800f3eeb  mov     rax, [rsi]
0x1800f3eee  lea     rdx, [rsp+160h+var_140]
0x1800f3ef3  mov     rcx, rsi
0x1800f3ef6  mov     rax, [rax+18h]
0x1800f3efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3eff  mov     ebx, eax
0x1800f3f01  test    eax, eax
0x1800f3f03  js      short loc_1800F3F5C
0x1800f3f05  mov     rcx, [rdi+300h]
0x1800f3f0c  mov     rax, [rcx]
0x1800f3f0f  lea     r8, [rbp+60h+var_48]
0x1800f3f13  mov     edx, [rsp+160h+var_140]
0x1800f3f17  mov     rax, [rax+28h]
0x1800f3f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3f20  mov     ebx, eax
0x1800f3f22  test    eax, eax
0x1800f3f24  js      short loc_1800F3F5C
0x1800f3f26  mov     rcx, [rdi+328h]
0x1800f3f2d  mov     rax, [rcx]
0x1800f3f30  lea     rdx, [rbp+60h+var_A8]
0x1800f3f34  mov     rax, [rax+38h]
  ... truncated ...
```
