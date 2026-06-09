# CInkOverlay::_UpdateTabletToInkToDisplayMapping(ITabletContext *,int)

- ea: `0x180028a98`
- end: `0x1800291a1`
- name: `?_UpdateTabletToInkToDisplayMapping@CInkOverlay@@AEAAJPEAUITabletContext@@H@Z`
- size: `1801`
- prototype: `__int64 __fastcall(CInkOverlay *__hidden this, struct ITabletContext *, int)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800d9b00`
- `0x1800dc860`
- `0x1800dd710`
- `0x1800df01c`

## callees

- `0x180001c20`
- `0x180028a98`
- `0x1800365f8`
- `0x180036824`
- `0x180037e68`
- `0x1800a6bf8`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ef3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028ad2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028aec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028ad2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028aec`
- `USER32!IsRectEmpty` at `0x180028b4c`
- `USER32!IsRectEmpty` at `0x180028b86`
- `USER32!IsRectEmpty` at `0x180028b4c`
- `USER32!IsRectEmpty` at `0x180028b86`
- `USER32!GetDC` at `0x180028d6c`
- `USER32!GetDC` at `0x180028d6c`
- `USER32!ReleaseDC` at `0x180028e3d`
- `USER32!ReleaseDC` at `0x180028e3d`
- `USER32!MapWindowPoints` at `0x180028f1c`
- `USER32!MapWindowPoints` at `0x180028f1c`
- `USER32!GetClientRect` at `0x180028b7c`
- `USER32!GetClientRect` at `0x180028b7c`
- `GDI32!CombineTransform` at `0x180028e4f`
- `GDI32!CombineTransform` at `0x180028e61`
- `GDI32!CombineTransform` at `0x1800290a5`
- `GDI32!CombineTransform` at `0x180028e4f`
- `GDI32!CombineTransform` at `0x180028e61`
- `GDI32!CombineTransform` at `0x1800290a5`
- `GDI32!GetDeviceCaps` at `0x180028d7d`
- `GDI32!GetDeviceCaps` at `0x180028d98`
- `GDI32!GetDeviceCaps` at `0x180028d7d`
- `GDI32!GetDeviceCaps` at `0x180028d98`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028bf6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028c28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028bf6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028c28`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInkOverlay::_UpdateTabletToInkToDisplayMapping(
        CInkOverlay *this,
        struct ITabletContext *a2,
        int a3)
{
  int updated; // ebx
  __int64 v8; // r15
  __int64 v9; // rcx
  __m128i si128; // xmm1
  __m128i v11; // xmm0
  __int64 v12; // rcx
  HDC DC; // r12
  int DeviceCaps; // ebx
  int v15; // eax
  float v16; // xmm1_4
  FLOAT v17; // xmm0_4
  float v18; // xmm3_4
  __int64 v19; // rcx
  signed int LastError; // eax
  float v21; // xmm2_4
  float v22; // xmm0_4
  float v23; // xmm2_4
  float v24; // xmm0_4
  int v25; // eax
  unsigned int v26; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v27; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v29[16]; // [rsp+48h] [rbp-B8h] BYREF
  XFORM v30; // [rsp+58h] [rbp-A8h] BYREF
  struct tagPOINT Points[2]; // [rsp+70h] [rbp-90h] BYREF
  struct tagRECT Rect; // [rsp+80h] [rbp-80h] BYREF
  struct _XFORM v33; // [rsp+90h] [rbp-70h] BYREF
  XFORM xf2; // [rsp+A8h] [rbp-58h] BYREF
  XFORM v35; // [rsp+C0h] [rbp-40h] BYREF
  XFORM v36; // [rsp+D8h] [rbp-28h] BYREF
  XFORM xf1; // [rsp+F0h] [rbp-10h] BYREF
  XFORM v38; // [rsp+108h] [rbp+8h] BYREF
  struct _XFORM xfOut; // [rsp+120h] [rbp+20h] BYREF
  struct _XFORM v40; // [rsp+138h] [rbp+38h] BYREF

  if ( GetCurrentThreadId() == *((_DWORD *)this + 67) )
    return 2147746359LL;
  _InterlockedExchange((volatile __int32 *)this + 67, GetCurrentThreadId());
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v29, (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
  if ( !*((_BYTE *)this + 264) )
  {
    *((_DWORD *)this + 100) = 1;
    _InterlockedExchange((volatile __int32 *)this + 67, 0);
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v29);
    return 0;
  }
  updated = 0;
  Rect = (struct tagRECT)*((_OWORD *)this + 21);
  v8 = 768;
  if ( !IsRectEmpty((const RECT *)this + 21) )
  {
    if ( a3 )
    {
      *(struct tagRECT *)&Points[0].x = Rect;
      SetLastError(0);
      v19 = 768;
      if ( *((_DWORD *)this + 213) != 1 )
        v19 = 56;
      MapWindowPoints(*(HWND *)((char *)this + v19), 0, Points, 2u);
      LastError = GetLastError();
      updated = LastError;
      if ( LastError > 0 )
        updated = (unsigned __int16)LastError | 0x80070000;
      if ( updated < 0 )
        goto LABEL_58;
      updated = (*(__int64 (__fastcall **)(struct ITabletContext *, struct tagPOINT *))(*(_QWORD *)a2 + 96LL))(
                  a2,
                  Points);
      if ( updated < 0 )
        goto LABEL_58;
    }
    goto LABEL_10;
  }
  v9 = 768;
  if ( *((_DWORD *)this + 213) != 1 )
    v9 = 56;
  GetClientRect(*(HWND *)((char *)this + v9), &Rect);
  if ( IsRectEmpty(&Rect) )
  {
    *((_DWORD *)this + 100) = 1;
    goto LABEL_10;
  }
  if ( !a3
    || (updated = (*(__int64 (__fastcall **)(struct ITabletContext *, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0),
        updated >= 0) )
  {
LABEL_10:
    if ( !*((_DWORD *)this + 100) )
    {
      *(_OWORD *)&Points[0].x = 0;
      updated = (*(__int64 (__fastcall **)(struct ITabletContext *, struct tagPOINT *))(*(_QWORD *)a2 + 112LL))(
                  a2,
                  Points);
      if ( updated >= 0 )
      {
        ppv = 0;
        updated = CoCreateInstance(&CLSID_InkTransform, 0, 1u, &GUID_615f1d43_8703_4565_88e2_8201d2ecd7b7, &ppv);
        if ( updated >= 0 )
        {
          v27 = 0;
          updated = CoCreateInstance(&CLSID_InkTransform, 0, 1u, &GUID_615f1d43_8703_4565_88e2_8201d2ecd7b7, &v27);
          if ( updated >= 0 )
          {
            memset(&v36, 0, sizeof(v36));
            memset(&xf1, 0, sizeof(xf1));
            updated = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)this + 47) + 72LL))(
                        *((_QWORD *)this + 47),
                        ppv);
            if ( updated >= 0 )
            {
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              *(__m128i *)&xf2.eM11 = si128;
              *(_QWORD *)&xf2.eDx = 0;
              if ( ppv )
              {
                (*(void (__fastcall **)(LPVOID, XFORM *))(*(_QWORD *)ppv + 216LL))(ppv, &xf2);
                si128 = *(__m128i *)&xf2.eM11;
              }
              *(__m128i *)&v36.eM11 = si128;
              *(_QWORD *)&v36.eDx = *(_QWORD *)&xf2.eDx;
              updated = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)this + 47) + 56LL))(
                          *((_QWORD *)this + 47),
                          v27);
              if ( updated >= 0 )
              {
                v11 = _mm_load_si128((const __m128i *)&_xmm);
                *(__m128i *)&v30.eM11 = v11;
                *(_QWORD *)&v30.eDx = 0;
                if ( v27 )
                {
                  (*(void (__fastcall **)(LPVOID, XFORM *))(*(_QWORD *)v27 + 216LL))(v27, &v30);
                  v11 = *(__m128i *)&v30.eM11;
                }
                *(__m128i *)&xf1.eM11 = v11;
                *(_QWORD *)&xf1.eDx = *(_QWORD *)&v30.eDx;
                *(_OWORD *)&xfOut.eM11 = xmmword_180126578;
                *(_QWORD *)&xfOut.eDx = 0;
                *(_OWORD *)&v33.eM11 = xmmword_180126578;
                *(_QWORD *)&v33.eDx = 0;
                *(_OWORD *)&v35.eM11 = xmmword_180126578;
                *(_QWORD *)&v35.eDx = 0;
                *(_OWORD *)&v38.eM11 = xmmword_180126578;
                *(_QWORD *)&v38.eDx = 0;
                *(_OWORD *)&v40.eM11 = xmmword_180126578;
                *(_QWORD *)&v40.eDx = 0;
                v12 = 768;
                if ( *((_DWORD *)this + 213) != 1 )
                  v12 = 56;
                DC = GetDC(*(HWND *)((char *)this + v12));
                DeviceCaps = GetDeviceCaps(DC, 88);
                if ( !DeviceCaps )
                  DeviceCaps = 96;
                v15 = GetDeviceCaps(DC, 90);
                if ( !v15 )
                  v15 = 96;
                v16 = (double)DeviceCaps / 2540.0;
                v17 = 1.0 / (float)(1.0 / v16);
                xf2.eM11 = v17;
                *(_QWORD *)&xf2.eM12 = 0;
                xf2.eM22 = 1.0 / (float)(1.0 / (float)((double)v15 / 2540.0));
                *(_QWORD *)&xf2.eDx = 0;
                if ( DC )
                {
                  if ( *((_DWORD *)this + 213) != 1 )
                    v8 = 56;
                  ReleaseDC(*(HWND *)((char *)this + v8), DC);
                }
                CombineTransform(&xfOut, &xf1, &xf2);
                CombineTransform(&v33, &v36, &xfOut);
                v18 = (float)(v33.eM11 * v33.eM22) - (float)(v33.eM12 * v33.eM21);
                if ( v18 >= 0.000000001 || v18 <= -0.000000001 )
                {
                  v35.eM11 = v33.eM22 / v18;
                  v35.eM12 = COERCE_FLOAT(LODWORD(v33.eM12) ^ _xmm) / v18;
                  v35.eM21 = COERCE_FLOAT(LODWORD(v33.eM21) ^ _xmm) / v18;
                  v35.eM22 = v33.eM11 / v18;
                  v35.eDx = (float)((float)(v33.eDy * v33.eM21) - (float)(v33.eM22 * v33.eDx)) / v18;
                  v35.eDy = (float)((float)(v33.eM12 * v33.eDx) - (float)(v33.eDy * v33.eM11)) / v18;
                  *(_OWORD *)&v30.eM11 = 0u;
                  v21 = (float)(Rect.right - Rect.left);
                  v22 = (float)(Points[1].x - Points[0].x);
                  if ( v22 >= 1.0 )
                    v21 = v21 / v22;
                  v30.eM11 = v21;
                  v30.eDx = (float)Rect.left - (float)((float)Points[0].x * v21);
                  v23 = (float)(Rect.bottom - Rect.top);
                  v24 = (float)(Points[1].y - Points[0].y);
                  if ( v24 >= 1.0 )
                    v23 = v23 / v24;
                  v30.eM22 = v23;
                  v30.eDy = (float)Rect.top - (float)((float)Points[0].y * v23);
                  v38 = v30;
                  CombineTransform(&v40, &v38, &v35);
                  v26 = 0;
                  updated = (*(__int64 (__fastcall **)(struct ITabletContext *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
                              a2,
                              &v26);
                  if ( updated >= 0 )
                  {
                    updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _XFORM *))(**((_QWORD **)this + 68)
                                                                                         + 40LL))(
                                *((_QWORD *)this + 68),
                                v26,
                                &v40);
                    if ( updated >= 0 )
                    {
                      updated = (*(__int64 (__fastcall **)(_QWORD, XFORM *))(**((_QWORD **)this + 73) + 56LL))(
                                  *((_QWORD *)this + 73),
                                  &v36);
                      if ( updated >= 0 )
                        updated = (*(__int64 (__fastcall **)(_QWORD, struct _XFORM *))(**((_QWORD **)this + 73) + 48LL))(
                                    *((_QWORD *)this + 73),
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
          ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v27);
          if ( updated >= 0 )
          {
            v25 = 0;
            if ( *((_DWORD *)this + 112) != 1 )
              v25 = *((_DWORD *)this + 212);
            updated = CInkOverlay::_UpdateSelectionRect(this, v25 == 2);
          }
        }
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppv);
      }
    }
    goto LABEL_58;
  }
  *((_DWORD *)this + 100) = 1;
LABEL_58:
  _InterlockedExchange((volatile __int32 *)this + 67, 0);
  if ( v29[8] )
    CInkAutoDataLock::Unlock((CInkAutoDataLock *)v29);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180028a98  mov     rax, rsp
0x180028a9b  mov     [rax+18h], rbx
0x180028a9f  push    rbp
0x180028aa0  push    rsi
0x180028aa1  push    rdi
0x180028aa2  push    r12
0x180028aa4  push    r13
0x180028aa6  push    r14
0x180028aa8  push    r15
0x180028aaa  lea     rbp, [rsp-70h]
0x180028aaf  sub     rsp, 170h
0x180028ab6  movaps  xmmword ptr [rax-48h], xmm8
0x180028abb  mov     rax, cs:__security_cookie
0x180028ac2  xor     rax, rsp
0x180028ac5  mov     [rbp+0A0h+var_50], rax
0x180028ac9  mov     r12d, r8d
0x180028acc  mov     r14, rdx
0x180028acf  mov     rdi, rcx
0x180028ad2  call    cs:__imp_GetCurrentThreadId
0x180028ad8  mov     ecx, [rdi+10Ch]
0x180028ade  cmp     eax, ecx
0x180028ae0  jnz     short loc_180028AEC
0x180028ae2  mov     eax, 80040237h
0x180028ae7  jmp     loc_180029175
0x180028aec  call    cs:__imp_GetCurrentThreadId
0x180028af2  xchg    eax, [rdi+10Ch]
0x180028af8  lea     rdx, [rdi+110h]; struct _RTL_CRITICAL_SECTION *
0x180028aff  lea     rcx, [rsp+1A0h+var_158]; this
0x180028b04  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x180028b09  nop
0x180028b0a  xor     r13d, r13d
0x180028b0d  cmp     [rdi+108h], r13b
0x180028b14  jnz     short loc_180028B3A
0x180028b16  mov     dword ptr [rdi+190h], 1
0x180028b20  mov     eax, r13d
0x180028b23  xchg    eax, [rdi+10Ch]
0x180028b29  lea     rcx, [rsp+1A0h+var_158]; this
0x180028b2e  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x180028b33  xor     eax, eax
0x180028b35  jmp     loc_180029175
0x180028b3a  mov     ebx, r13d
0x180028b3d  lea     rcx, [rdi+150h]; lprc
0x180028b44  movups  xmm0, xmmword ptr [rcx]
0x180028b47  movdqu  xmmword ptr [rbp+0A0h+Rect.left], xmm0
0x180028b4c  call    cs:__imp_IsRectEmpty
0x180028b52  mov     esi, 1
0x180028b57  lea     edx, [rsi+37h]
0x180028b5a  mov     r15d, 300h
0x180028b60  test    eax, eax
0x180028b62  jz      loc_180028EE2
0x180028b68  mov     ecx, r15d
0x180028b6b  cmp     [rdi+354h], esi
0x180028b71  cmovnz  ecx, edx
0x180028b74  lea     rdx, [rbp+0A0h+Rect]; lpRect
0x180028b78  mov     rcx, [rcx+rdi]; hWnd
0x180028b7c  call    cs:__imp_GetClientRect
0x180028b82  lea     rcx, [rbp+0A0h+Rect]; lprc
0x180028b86  call    cs:__imp_IsRectEmpty
0x180028b8c  test    eax, eax
0x180028b8e  jz      loc_180028EB3
0x180028b94  mov     [rdi+190h], esi
0x180028b9a  mov     r12d, 38h ; '8'
0x180028ba0  cmp     [rdi+190h], r13d
0x180028ba7  jnz     loc_180029159
0x180028bad  xorps   xmm0, xmm0
0x180028bb0  movdqu  xmmword ptr [rsp+1A0h+Points.x], xmm0
0x180028bb6  mov     rax, [r14]
0x180028bb9  lea     rdx, [rsp+1A0h+Points]
0x180028bbe  mov     rcx, r14
0x180028bc1  mov     rax, [rax+70h]
0x180028bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bca  mov     ebx, eax
0x180028bcc  test    eax, eax
0x180028bce  js      loc_180029159
0x180028bd4  mov     [rsp+1A0h+var_160], r13
0x180028bd9  lea     rax, [rsp+1A0h+var_160]
0x180028bde  mov     [rsp+1A0h+ppv], rax; ppv
0x180028be3  lea     r9, _GUID_615f1d43_8703_4565_88e2_8201d2ecd7b7; riid
0x180028bea  mov     r8d, esi; dwClsContext
0x180028bed  xor     edx, edx; pUnkOuter
0x180028bef  lea     rcx, CLSID_InkTransform; rclsid
0x180028bf6  call    cs:__imp_CoCreateInstance
0x180028bfc  mov     ebx, eax
0x180028bfe  test    eax, eax
0x180028c00  js      loc_18002914F
0x180028c06  mov     [rsp+1A0h+var_168], r13
0x180028c0b  lea     rax, [rsp+1A0h+var_168]
0x180028c10  mov     [rsp+1A0h+ppv], rax; ppv
0x180028c15  lea     r9, _GUID_615f1d43_8703_4565_88e2_8201d2ecd7b7; riid
0x180028c1c  mov     r8d, esi; dwClsContext
0x180028c1f  xor     edx, edx; pUnkOuter
0x180028c21  lea     rcx, CLSID_InkTransform; rclsid
0x180028c28  call    cs:__imp_CoCreateInstance
0x180028c2e  mov     ebx, eax
0x180028c30  test    eax, eax
0x180028c32  js      loc_180029121
0x180028c38  xorps   xmm0, xmm0
0x180028c3b  xor     eax, eax
0x180028c3d  movups  xmmword ptr [rbp+0A0h+var_C8.eM11], xmm0
0x180028c41  mov     qword ptr [rbp+0A0h+var_C8.eDx], rax
0x180028c45  xorps   xmm1, xmm1
0x180028c48  movups  xmmword ptr [rbp+0A0h+xf1.eM11], xmm1
0x180028c4c  mov     qword ptr [rbp+0A0h+xf1.eDx], rax
0x180028c50  mov     rcx, [rdi+178h]
0x180028c57  mov     rax, [rcx]
0x180028c5a  mov     rdx, [rsp+1A0h+var_160]
0x180028c5f  mov     rax, [rax+48h]
0x180028c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c68  mov     ebx, eax
0x180028c6a  test    eax, eax
0x180028c6c  js      loc_180029121
0x180028c72  movdqa  xmm1, cs:__xmm@3f80000000000000000000003f800000
0x180028c7a  movups  xmmword ptr [rbp+0A0h+xf2.eM11], xmm1
0x180028c7e  mov     qword ptr [rbp+0A0h+xf2.eDx], 0
0x180028c86  mov     rcx, [rsp+1A0h+var_160]
0x180028c8b  test    rcx, rcx
0x180028c8e  jz      short loc_180028CA7
0x180028c90  mov     rax, [rcx]
0x180028c93  lea     rdx, [rbp+0A0h+xf2]
0x180028c97  mov     rax, [rax+0D8h]
0x180028c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ca3  movups  xmm1, xmmword ptr [rbp+0A0h+xf2.eM11]
0x180028ca7  movups  xmmword ptr [rbp+0A0h+var_C8.eM11], xmm1
0x180028cab  movsd   xmm0, qword ptr [rbp+0A0h+xf2.eDx]
0x180028cb0  movsd   qword ptr [rbp+0A0h+var_C8.eDx], xmm0
0x180028cb5  mov     rcx, [rdi+178h]
0x180028cbc  mov     rax, [rcx]
0x180028cbf  mov     rdx, [rsp+1A0h+var_168]
0x180028cc4  mov     rax, [rax+38h]
0x180028cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ccd  mov     ebx, eax
0x180028ccf  test    eax, eax
0x180028cd1  js      loc_180029121
0x180028cd7  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180028cdf  movups  [rsp+1A0h+var_148], xmm0
0x180028ce4  mov     [rsp+1A0h+var_138], 0
0x180028ced  mov     rcx, [rsp+1A0h+var_168]
0x180028cf2  test    rcx, rcx
0x180028cf5  jz      short loc_180028D10
0x180028cf7  mov     rax, [rcx]
0x180028cfa  lea     rdx, [rsp+1A0h+var_148]
0x180028cff  mov     rax, [rax+0D8h]
0x180028d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d0b  movups  xmm0, [rsp+1A0h+var_148]
0x180028d10  movups  xmmword ptr [rbp+0A0h+xf1.eM11], xmm0
0x180028d14  movsd   xmm0, [rsp+1A0h+var_138]
0x180028d1a  movsd   qword ptr [rbp+0A0h+xf1.eDx], xmm0
0x180028d1f  movups  xmm1, cs:xmmword_180126578
0x180028d26  movups  xmmword ptr [rbp+0A0h+xfOut.eM11], xmm1
0x180028d2a  movsd   xmm0, cs:qword_180126588
0x180028d32  movsd   qword ptr [rbp+0A0h+xfOut.eDx], xmm0
0x180028d37  movups  xmmword ptr [rbp+0A0h+var_110.eM11], xmm1
0x180028d3b  movsd   qword ptr [rbp+0A0h+var_110.eDx], xmm0
0x180028d40  movups  xmmword ptr [rbp+0A0h+var_E0.eM11], xmm1
0x180028d44  movsd   qword ptr [rbp+0A0h+var_E0.eDx], xmm0
0x180028d49  movups  xmmword ptr [rbp+0A0h+var_98.eM11], xmm1
0x180028d4d  movsd   qword ptr [rbp+0A0h+var_98.eDx], xmm0
0x180028d52  movups  xmmword ptr [rbp+0A0h+var_68.eM11], xmm1
0x180028d56  movsd   qword ptr [rbp+0A0h+var_68.eDx], xmm0
0x180028d5b  mov     rcx, r15
0x180028d5e  cmp     [rdi+354h], esi
0x180028d64  cmovnz  rcx, r12
0x180028d68  mov     rcx, [rcx+rdi]; hWnd
0x180028d6c  call    cs:__imp_GetDC
0x180028d72  mov     r12, rax
0x180028d75  mov     edx, 58h ; 'X'; index
0x180028d7a  mov     rcx, rax; hdc
0x180028d7d  call    cs:__imp_GetDeviceCaps
0x180028d83  mov     ebx, eax
0x180028d85  mov     r13d, 60h ; '`'
0x180028d8b  test    eax, eax
0x180028d8d  cmovz   ebx, r13d
0x180028d91  lea     edx, [r13-6]; index
0x180028d95  mov     rcx, r12; hdc
0x180028d98  call    cs:__imp_GetDeviceCaps
0x180028d9e  test    eax, eax
0x180028da0  cmovz   eax, r13d
0x180028da4  movd    xmm0, ebx
0x180028da8  cvtdq2pd xmm0, xmm0
0x180028dac  divsd   xmm0, cs:__real@40a3d80000000000
0x180028db4  cvtpd2ps xmm1, xmm0
0x180028db8  movss   xmm8, cs:__real@3f800000
0x180028dc1  movaps  xmm0, xmm8
0x180028dc5  divss   xmm0, xmm1
0x180028dc9  cvtps2pd xmm2, xmm0
0x180028dcc  movsd   xmm4, cs:__real@3ff0000000000000
0x180028dd4  movaps  xmm1, xmm4
0x180028dd7  divsd   xmm1, xmm2
0x180028ddb  cvtpd2ps xmm0, xmm1
0x180028ddf  movss   [rbp+0A0h+xf2.eM11], xmm0
0x180028de4  mov     qword ptr [rbp+0A0h+xf2.eM12], 0
0x180028dec  movd    xmm0, eax
0x180028df0  cvtdq2pd xmm0, xmm0
0x180028df4  divsd   xmm0, cs:__real@40a3d80000000000
0x180028dfc  cvtpd2ps xmm1, xmm0
0x180028e00  movaps  xmm2, xmm8
0x180028e04  divss   xmm2, xmm1
0x180028e08  cvtps2pd xmm0, xmm2
0x180028e0b  divsd   xmm4, xmm0
0x180028e0f  cvtpd2ps xmm0, xmm4
0x180028e13  movss   [rbp+0A0h+xf2.eM22], xmm0
0x180028e18  mov     qword ptr [rbp+0A0h+xf2.eDx], 0
0x180028e20  xor     r13d, r13d
0x180028e23  test    r12, r12
0x180028e26  jz      short loc_180028E43
0x180028e28  cmp     [rdi+354h], esi
0x180028e2e  lea     eax, [r13+38h]
0x180028e32  cmovnz  r15, rax
0x180028e36  mov     rdx, r12; hDC
0x180028e39  mov     rcx, [r15+rdi]; hWnd
0x180028e3d  call    cs:__imp_ReleaseDC
0x180028e43  lea     r8, [rbp+0A0h+xf2]; lpxf2
0x180028e47  lea     rdx, [rbp+0A0h+xf1]; lpxf1
0x180028e4b  lea     rcx, [rbp+0A0h+xfOut]; lpxfOut
0x180028e4f  call    cs:__imp_CombineTransform
0x180028e55  lea     r8, [rbp+0A0h+xfOut]; lpxf2
0x180028e59  lea     rdx, [rbp+0A0h+var_C8]; lpxf1
0x180028e5d  lea     rcx, [rbp+0A0h+var_110]; lpxfOut
0x180028e61  call    cs:__imp_CombineTransform
0x180028e67  movss   xmm3, [rbp+0A0h+var_110.eM11]
0x180028e6c  movss   xmm5, [rbp+0A0h+var_110.eM22]
0x180028e71  mulss   xmm3, xmm5
0x180028e75  movss   xmm4, [rbp+0A0h+var_110.eM12]
0x180028e7a  movaps  xmm0, xmm4
0x180028e7d  mulss   xmm0, [rbp+0A0h+var_110.eM21]
0x180028e82  subss   xmm3, xmm0
0x180028e86  cvtps2pd xmm1, xmm3
0x180028e89  movsd   xmm0, cs:__real@3e112e0be826d695
0x180028e91  comisd  xmm0, xmm1
0x180028e95  jbe     loc_180028F6A
0x180028e9b  comisd  xmm1, cs:__real@be112e0be826d695
0x180028ea3  jbe     loc_180028F6A
0x180028ea9  mov     ebx, 80004005h
0x180028eae  jmp     loc_180029121
0x180028eb3  test    r12d, r12d
0x180028eb6  jz      loc_180028B9A
0x180028ebc  mov     rax, [r14]
0x180028ebf  xor     edx, edx
0x180028ec1  mov     rcx, r14
0x180028ec4  mov     rax, [rax+60h]
0x180028ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ecd  mov     ebx, eax
0x180028ecf  test    eax, eax
0x180028ed1  jns     loc_180028B9A
0x180028ed7  mov     [rdi+190h], esi
0x180028edd  jmp     loc_180029159
0x180028ee2  test    r12d, r12d
0x180028ee5  jz      short loc_180028F62
0x180028ee7  movaps  xmm0, xmmword ptr [rbp+0A0h+Rect.left]
0x180028eeb  movdqa  xmmword ptr [rsp+1A0h+Points.x], xmm0
0x180028ef1  xor     ecx, ecx; dwErrCode
0x180028ef3  call    cs:__imp_SetLastError
0x180028ef9  mov     rcx, r15
0x180028efc  cmp     [rdi+354h], esi
0x180028f02  mov     r12d, 38h ; '8'
0x180028f08  cmovnz  rcx, r12
0x180028f0c  lea     r9d, [r12-36h]; cPoints
0x180028f11  lea     r8, [rsp+1A0h+Points]; lpPoints
0x180028f16  xor     edx, edx; hWndTo
0x180028f18  mov     rcx, [rcx+rdi]; hWndFrom
0x180028f1c  call    cs:__imp_MapWindowPoints
0x180028f22  call    cs:__imp_GetLastError
0x180028f28  mov     ebx, eax
0x180028f2a  test    eax, eax
0x180028f2c  jle     short loc_180028F37
0x180028f2e  movzx   ebx, ax
0x180028f31  or      ebx, 80070000h
0x180028f37  test    ebx, ebx
0x180028f39  js      loc_180029159
0x180028f3f  mov     rax, [r14]
0x180028f42  lea     rdx, [rsp+1A0h+Points]
0x180028f47  mov     rcx, r14
0x180028f4a  mov     rax, [rax+60h]
0x180028f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f53  mov     ebx, eax
0x180028f55  test    eax, eax
0x180028f57  jns     loc_180028BA0
0x180028f5d  jmp     loc_180029159
0x180028f62  mov     r12, rdx
0x180028f65  jmp     loc_180028BA0
0x180028f6a  movaps  xmm0, xmm5
0x180028f6d  divss   xmm0, xmm3
0x180028f71  movss   [rbp+0A0h+var_E0.eM11], xmm0
0x180028f76  movaps  xmm1, xmm4
0x180028f79  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x180028f80  divss   xmm1, xmm3
0x180028f84  movss   [rbp+0A0h+var_E0.eM12], xmm1
0x180028f89  movss   xmm0, [rbp+0A0h+var_110.eM21]
0x180028f8e  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180028f95  divss   xmm0, xmm3
0x180028f99  movss   [rbp+0A0h+var_E0.eM21], xmm0
0x180028f9e  movss   xmm0, [rbp+0A0h+var_110.eM11]
0x180028fa3  divss   xmm0, xmm3
0x180028fa7  movss   [rbp+0A0h+var_E0.eM22], xmm0
0x180028fac  movss   xmm2, [rbp+0A0h+var_110.eDy]
0x180028fb1  movaps  xmm1, xmm2
0x180028fb4  mulss   xmm1, [rbp+0A0h+var_110.eM21]
0x180028fb9  mulss   xmm5, [rbp+0A0h+var_110.eDx]
0x180028fbe  subss   xmm1, xmm5
0x180028fc2  divss   xmm1, xmm3
  ... truncated ...
```
