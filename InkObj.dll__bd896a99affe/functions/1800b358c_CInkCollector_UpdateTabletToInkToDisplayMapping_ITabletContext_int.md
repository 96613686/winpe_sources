# CInkCollector::_UpdateTabletToInkToDisplayMapping(ITabletContext *,int)

- ea: `0x1800b358c`
- end: `0x1800b3b01`
- name: `?_UpdateTabletToInkToDisplayMapping@CInkCollector@@AEAAJPEAUITabletContext@@H@Z`
- size: `1397`
- prototype: `__int64 __fastcall(CInkCollector *__hidden this, struct ITabletContext *, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ab360`
- `0x1800adf60`
- `0x1800aee70`
- `0x1800b08b0`

## callees

- `0x180001c20`
- `0x1800211c0`
- `0x180026ca0`
- `0x1800365f8`
- `0x180036824`
- `0x18003821c`
- `0x1800b358c`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b36a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b36a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b36bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b36bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b35bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b35d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b35bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b35d9`
- `USER32!IsRectEmpty` at `0x1800b3629`
- `USER32!IsRectEmpty` at `0x1800b3647`
- `USER32!IsRectEmpty` at `0x1800b3629`
- `USER32!IsRectEmpty` at `0x1800b3647`
- `USER32!GetDC` at `0x1800b3845`
- `USER32!GetDC` at `0x1800b3845`
- `USER32!ReleaseDC` at `0x1800b3877`
- `USER32!ReleaseDC` at `0x1800b3877`
- `USER32!MapWindowPoints` at `0x1800b36b9`
- `USER32!MapWindowPoints` at `0x1800b36b9`
- `USER32!GetClientRect` at `0x1800b363c`
- `USER32!GetClientRect` at `0x1800b363c`
- `GDI32!CombineTransform` at `0x1800b3889`
- `GDI32!CombineTransform` at `0x1800b389c`
- `GDI32!CombineTransform` at `0x1800b3a35`
- `GDI32!CombineTransform` at `0x1800b3889`
- `GDI32!CombineTransform` at `0x1800b389c`
- `GDI32!CombineTransform` at `0x1800b3a35`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInkCollector::_UpdateTabletToInkToDisplayMapping(
        CInkCollector *this,
        struct ITabletContext *a2,
        int a3)
{
  int v6; // ebx
  int v8; // eax
  signed int LastError; // eax
  HDC DC; // rbx
  float v11; // xmm3_4
  float v12; // xmm2_4
  float v13; // xmm0_4
  float v14; // xmm2_4
  float v15; // xmm0_4
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID v17; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[24]; // [rsp+38h] [rbp-C8h] BYREF
  struct tagPOINT Points[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-A0h] BYREF
  struct _XFORM v22; // [rsp+70h] [rbp-90h] BYREF
  tagXFORM v23; // [rsp+88h] [rbp-78h] BYREF
  XFORM v24; // [rsp+A0h] [rbp-60h] BYREF
  XFORM v25; // [rsp+B8h] [rbp-48h] BYREF
  XFORM xf1; // [rsp+D0h] [rbp-30h] BYREF
  XFORM v27; // [rsp+E8h] [rbp-18h] BYREF
  struct _XFORM xfOut; // [rsp+100h] [rbp+0h] BYREF
  struct _XFORM v29; // [rsp+118h] [rbp+18h] BYREF
  XFORM xf2; // [rsp+130h] [rbp+30h] BYREF

  v6 = 0;
  if ( GetCurrentThreadId() == *((_DWORD *)this + 67) )
    return 2147746359LL;
  _InterlockedExchange((volatile __int32 *)this + 67, GetCurrentThreadId());
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v19, (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
  if ( *((_BYTE *)this + 264) )
  {
    Rect = (struct tagRECT)*((_OWORD *)this + 21);
    if ( IsRectEmpty((const RECT *)this + 21) )
    {
      GetClientRect(*((HWND *)this + 7), &Rect);
      if ( IsRectEmpty(&Rect) )
      {
        *((_DWORD *)this + 100) = 1;
        v8 = 0;
      }
      else
      {
        v8 = 0;
        if ( a3 )
        {
          v8 = (*(__int64 (__fastcall **)(struct ITabletContext *, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0);
          v6 = v8;
          if ( v8 >= 0 )
            goto LABEL_17;
          *((_DWORD *)this + 100) = 1;
        }
      }
    }
    else
    {
      if ( !a3 )
        goto LABEL_17;
      *(struct tagRECT *)&Points[0].x = Rect;
      SetLastError(0);
      MapWindowPoints(*((HWND *)this + 7), 0, Points, 2u);
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_38;
      v8 = (*(__int64 (__fastcall **)(struct ITabletContext *, struct tagPOINT *))(*(_QWORD *)a2 + 96LL))(a2, Points);
      v6 = v8;
    }
    if ( v8 < 0 )
    {
LABEL_38:
      _InterlockedExchange((volatile __int32 *)this + 67, 0);
      goto LABEL_39;
    }
LABEL_17:
    if ( !*((_DWORD *)this + 100) )
    {
      *(_OWORD *)&Points[0].x = 0;
      v6 = (*(__int64 (__fastcall **)(struct ITabletContext *, struct tagPOINT *))(*(_QWORD *)a2 + 112LL))(a2, Points);
      v16 = v6;
      if ( v6 >= 0 )
      {
        CIXForm::CIXForm(&ppv, &v16);
        v6 = v16;
        if ( v16 >= 0 )
        {
          CIXForm::CIXForm(&v17, &v16);
          v6 = v16;
          if ( v16 >= 0 )
          {
            memset(&v25, 0, sizeof(v25));
            memset(&xf1, 0, sizeof(xf1));
            v6 = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)this + 47) + 72LL))(
                   *((_QWORD *)this + 47),
                   ppv);
            if ( v6 >= 0 )
            {
              v25 = *(XFORM *)CIXForm::GetXForm((CIXForm *)&ppv, (struct tagXFORM *)&xf2);
              v6 = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)this + 47) + 56LL))(
                     *((_QWORD *)this + 47),
                     v17);
              if ( v6 >= 0 )
              {
                xf1 = *(XFORM *)CIXForm::GetXForm((CIXForm *)&v17, &v23);
                *(_OWORD *)&xfOut.eM11 = xmmword_180121A30;
                *(_QWORD *)&xfOut.eDx = 0;
                *(_OWORD *)&v22.eM11 = xmmword_180121A30;
                *(_QWORD *)&v22.eDx = 0;
                *(_OWORD *)&v24.eM11 = xmmword_180121A30;
                *(_QWORD *)&v24.eDx = 0;
                *(_OWORD *)&v27.eM11 = xmmword_180121A30;
                *(_QWORD *)&v27.eDx = 0;
                *(_OWORD *)&v29.eM11 = xmmword_180121A30;
                *(_QWORD *)&v29.eDx = 0;
                DC = GetDC(*((HWND *)this + 7));
                xf2 = *(XFORM *)GetHiMetricToPixelXForm(&v23, DC);
                if ( DC )
                  ReleaseDC(*((HWND *)this + 7), DC);
                CombineTransform(&xfOut, &xf1, &xf2);
                CombineTransform(&v22, &v25, &xfOut);
                v11 = (float)(v22.eM11 * v22.eM22) - (float)(v22.eM12 * v22.eM21);
                if ( v11 >= 0.000000001 || v11 <= -0.000000001 )
                {
                  v24.eM11 = v22.eM22 / v11;
                  v24.eM12 = COERCE_FLOAT(LODWORD(v22.eM12) ^ _xmm) / v11;
                  v24.eM21 = COERCE_FLOAT(LODWORD(v22.eM21) ^ _xmm) / v11;
                  v24.eM22 = v22.eM11 / v11;
                  v24.eDx = (float)((float)(v22.eDy * v22.eM21) - (float)(v22.eM22 * v22.eDx)) / v11;
                  v24.eDy = (float)((float)(v22.eM12 * v22.eDx) - (float)(v22.eDy * v22.eM11)) / v11;
                  *(_QWORD *)&v23.eM11 = 0;
                  *(_QWORD *)&v23.eM21 = 0;
                  v12 = (float)(Rect.right - Rect.left);
                  v13 = (float)(Points[1].x - Points[0].x);
                  if ( v13 >= 1.0 )
                    v12 = v12 / v13;
                  v23.eM11 = v12;
                  v23.eDx = (float)Rect.left - (float)((float)Points[0].x * v12);
                  v14 = (float)(Rect.bottom - Rect.top);
                  v15 = (float)(Points[1].y - Points[0].y);
                  if ( v15 >= 1.0 )
                    v14 = v14 / v15;
                  v23.eM22 = v14;
                  v23.eDy = (float)Rect.top - (float)((float)Points[0].y * v14);
                  v27 = (XFORM)v23;
                  CombineTransform(&v29, &v27, &v24);
                  v16 = 0;
                  v6 = (*(__int64 (__fastcall **)(struct ITabletContext *, int *))(*(_QWORD *)a2 + 24LL))(a2, &v16);
                  if ( v6 >= 0 )
                  {
                    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _XFORM *))(**((_QWORD **)this + 68) + 40LL))(
                           *((_QWORD *)this + 68),
                           (unsigned int)v16,
                           &v29);
                    if ( v6 >= 0 )
                    {
                      v6 = (*(__int64 (__fastcall **)(_QWORD, XFORM *))(**((_QWORD **)this + 71) + 56LL))(
                             *((_QWORD *)this + 71),
                             &v25);
                      if ( v6 >= 0 )
                        v6 = (*(__int64 (__fastcall **)(_QWORD, struct _XFORM *))(**((_QWORD **)this + 71) + 48LL))(
                               *((_QWORD *)this + 71),
                               &xfOut);
                    }
                  }
                }
                else
                {
                  v6 = -2147467259;
                }
              }
            }
          }
          ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v17);
        }
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ppv);
      }
    }
    goto LABEL_38;
  }
  *((_DWORD *)this + 100) = 1;
  _InterlockedExchange((volatile __int32 *)this + 67, 0);
  v6 = 0;
LABEL_39:
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b358c  mov     [rsp-8+arg_10], rbx
0x1800b3591  mov     [rsp-8+arg_18], rsi
0x1800b3596  push    rbp
0x1800b3597  push    rdi
0x1800b3598  push    r14
0x1800b359a  lea     rbp, [rsp-50h]
0x1800b359f  sub     rsp, 150h
0x1800b35a6  mov     rax, cs:__security_cookie
0x1800b35ad  xor     rax, rsp
0x1800b35b0  mov     [rbp+60h+var_18], rax
0x1800b35b4  mov     r14d, r8d
0x1800b35b7  mov     rsi, rdx
0x1800b35ba  mov     rdi, rcx
0x1800b35bd  xor     ebx, ebx
0x1800b35bf  call    cs:__imp_GetCurrentThreadId
0x1800b35c5  mov     edx, [rdi+10Ch]
0x1800b35cb  cmp     eax, edx
0x1800b35cd  jnz     short loc_1800B35D9
0x1800b35cf  mov     eax, 80040237h
0x1800b35d4  jmp     loc_1800B3ADD
0x1800b35d9  call    cs:__imp_GetCurrentThreadId
0x1800b35df  xchg    eax, [rdi+10Ch]
0x1800b35e5  lea     rdx, [rdi+110h]; struct _RTL_CRITICAL_SECTION *
0x1800b35ec  lea     rcx, [rsp+160h+var_128]; this
0x1800b35f1  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800b35f6  nop
0x1800b35f7  cmp     byte ptr [rdi+108h], 0
0x1800b35fe  jnz     short loc_1800B3619
0x1800b3600  mov     dword ptr [rdi+190h], 1
0x1800b360a  xor     eax, eax
0x1800b360c  xchg    eax, [rdi+10Ch]
0x1800b3612  xor     ebx, ebx
0x1800b3614  jmp     loc_1800B3AD1
0x1800b3619  lea     rcx, [rdi+150h]; lprc
0x1800b3620  movups  xmm0, xmmword ptr [rcx]
0x1800b3623  movdqu  xmmword ptr [rsp+160h+Rect.left], xmm0
0x1800b3629  call    cs:__imp_IsRectEmpty
0x1800b362f  test    eax, eax
0x1800b3631  jz      short loc_1800B3690
0x1800b3633  lea     rdx, [rsp+160h+Rect]; lpRect
0x1800b3638  mov     rcx, [rdi+38h]; hWnd
0x1800b363c  call    cs:__imp_GetClientRect
0x1800b3642  lea     rcx, [rsp+160h+Rect]; lprc
0x1800b3647  call    cs:__imp_IsRectEmpty
0x1800b364d  test    eax, eax
0x1800b364f  jz      short loc_1800B3662
0x1800b3651  mov     dword ptr [rdi+190h], 1
0x1800b365b  xor     eax, eax
0x1800b365d  jmp     loc_1800B36F2
0x1800b3662  xor     eax, eax
0x1800b3664  test    r14d, r14d
0x1800b3667  jz      loc_1800B36F2
0x1800b366d  mov     rax, [rsi]
0x1800b3670  xor     edx, edx
0x1800b3672  mov     rcx, rsi
0x1800b3675  mov     rax, [rax+60h]
0x1800b3679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b367e  mov     ebx, eax
0x1800b3680  test    eax, eax
0x1800b3682  jns     short loc_1800B36FA
0x1800b3684  mov     dword ptr [rdi+190h], 1
0x1800b368e  jmp     short loc_1800B36F2
0x1800b3690  test    r14d, r14d
0x1800b3693  jz      short loc_1800B36FA
0x1800b3695  movaps  xmm0, xmmword ptr [rsp+160h+Rect.left]
0x1800b369a  movdqa  xmmword ptr [rsp+160h+Points.x], xmm0
0x1800b36a0  xor     ecx, ecx; dwErrCode
0x1800b36a2  call    cs:__imp_SetLastError
0x1800b36a8  mov     r9d, 2; cPoints
0x1800b36ae  lea     r8, [rsp+160h+Points]; lpPoints
0x1800b36b3  xor     edx, edx; hWndTo
0x1800b36b5  mov     rcx, [rdi+38h]; hWndFrom
0x1800b36b9  call    cs:__imp_MapWindowPoints
0x1800b36bf  call    cs:__imp_GetLastError
0x1800b36c5  mov     ebx, eax
0x1800b36c7  test    eax, eax
0x1800b36c9  jle     short loc_1800B36D4
0x1800b36cb  movzx   ebx, ax
0x1800b36ce  or      ebx, 80070000h
0x1800b36d4  test    ebx, ebx
0x1800b36d6  js      loc_1800B3AC9
0x1800b36dc  mov     rax, [rsi]
0x1800b36df  lea     rdx, [rsp+160h+Points]
0x1800b36e4  mov     rcx, rsi
0x1800b36e7  mov     rax, [rax+60h]
0x1800b36eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b36f0  mov     ebx, eax
0x1800b36f2  test    eax, eax
0x1800b36f4  js      loc_1800B3AC9
0x1800b36fa  cmp     dword ptr [rdi+190h], 0
0x1800b3701  jnz     loc_1800B3AC9
0x1800b3707  xorps   xmm0, xmm0
0x1800b370a  movdqu  xmmword ptr [rsp+160h+Points.x], xmm0
0x1800b3710  mov     rax, [rsi]
0x1800b3713  lea     rdx, [rsp+160h+Points]
0x1800b3718  mov     rcx, rsi
0x1800b371b  mov     rax, [rax+70h]
0x1800b371f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3724  mov     ebx, eax
0x1800b3726  mov     [rsp+160h+var_140], eax
0x1800b372a  test    eax, eax
0x1800b372c  js      loc_1800B3AC9
0x1800b3732  lea     rdx, [rsp+160h+var_140]; int *
0x1800b3737  lea     rcx, [rsp+160h+ppv]; ppv
0x1800b373c  call    ??0CIXForm@@QEAA@AEAJ@Z; CIXForm::CIXForm(long &)
0x1800b3741  nop
0x1800b3742  mov     ebx, [rsp+160h+var_140]
0x1800b3746  test    ebx, ebx
0x1800b3748  js      loc_1800B3ABF
0x1800b374e  lea     rdx, [rsp+160h+var_140]; int *
0x1800b3753  lea     rcx, [rsp+160h+var_138]; ppv
0x1800b3758  call    ??0CIXForm@@QEAA@AEAJ@Z; CIXForm::CIXForm(long &)
0x1800b375d  nop
0x1800b375e  mov     ebx, [rsp+160h+var_140]
0x1800b3762  test    ebx, ebx
0x1800b3764  js      loc_1800B3AB4
0x1800b376a  xorps   xmm0, xmm0
0x1800b376d  xor     eax, eax
0x1800b376f  movups  xmmword ptr [rbp+60h+var_A8.eM11], xmm0
0x1800b3773  mov     qword ptr [rbp+60h+var_A8.eDx], rax
0x1800b3777  xorps   xmm1, xmm1
0x1800b377a  movups  xmmword ptr [rbp+60h+xf1.eM11], xmm1
0x1800b377e  mov     qword ptr [rbp+60h+xf1.eDx], rax
0x1800b3782  mov     rcx, [rdi+178h]
0x1800b3789  mov     rax, [rcx]
0x1800b378c  mov     rdx, [rsp+160h+ppv]
0x1800b3791  mov     rax, [rax+48h]
0x1800b3795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b379a  mov     ebx, eax
0x1800b379c  test    eax, eax
0x1800b379e  js      loc_1800B3AB4
0x1800b37a4  lea     rdx, [rbp+60h+xf2]; retstr
0x1800b37a8  lea     rcx, [rsp+160h+ppv]; this
0x1800b37ad  call    ?GetXForm@CIXForm@@QEBA?AUtagXFORM@@XZ; CIXForm::GetXForm(void)
0x1800b37b2  movups  xmm0, xmmword ptr [rax]
0x1800b37b5  movups  xmmword ptr [rbp+60h+var_A8.eM11], xmm0
0x1800b37b9  movsd   xmm1, qword ptr [rax+10h]
0x1800b37be  movsd   qword ptr [rbp+60h+var_A8.eDx], xmm1
0x1800b37c3  mov     rcx, [rdi+178h]
0x1800b37ca  mov     rax, [rcx]
0x1800b37cd  mov     rdx, [rsp+160h+var_138]
0x1800b37d2  mov     rax, [rax+38h]
0x1800b37d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b37db  mov     ebx, eax
0x1800b37dd  test    eax, eax
0x1800b37df  js      loc_1800B3AB4
0x1800b37e5  lea     rdx, [rbp+60h+var_D8]; retstr
0x1800b37e9  lea     rcx, [rsp+160h+var_138]; this
0x1800b37ee  call    ?GetXForm@CIXForm@@QEBA?AUtagXFORM@@XZ; CIXForm::GetXForm(void)
0x1800b37f3  movups  xmm0, xmmword ptr [rax]
0x1800b37f6  movups  xmmword ptr [rbp+60h+xf1.eM11], xmm0
0x1800b37fa  movsd   xmm1, qword ptr [rax+10h]
0x1800b37ff  movsd   qword ptr [rbp+60h+xf1.eDx], xmm1
0x1800b3804  movups  xmm2, cs:xmmword_180121A30
0x1800b380b  movups  xmmword ptr [rbp+60h+xfOut.eM11], xmm2
0x1800b380f  movsd   xmm0, cs:qword_180121A40
0x1800b3817  movsd   qword ptr [rbp+60h+xfOut.eDx], xmm0
0x1800b381c  movups  xmmword ptr [rsp+160h+var_F0.eM11], xmm2
0x1800b3821  movsd   qword ptr [rbp+60h+var_F0.eDx], xmm0
0x1800b3826  movups  xmmword ptr [rbp+60h+var_C0.eM11], xmm2
0x1800b382a  movsd   qword ptr [rbp+60h+var_C0.eDx], xmm0
0x1800b382f  movups  xmmword ptr [rbp+60h+var_78.eM11], xmm2
0x1800b3833  movsd   qword ptr [rbp+60h+var_78.eDx], xmm0
0x1800b3838  movups  xmmword ptr [rbp+60h+var_48.eM11], xmm2
0x1800b383c  movsd   qword ptr [rbp+60h+var_48.eDx], xmm0
0x1800b3841  mov     rcx, [rdi+38h]; hWnd
0x1800b3845  call    cs:__imp_GetDC
0x1800b384b  mov     rbx, rax
0x1800b384e  mov     rdx, rax; HDC
0x1800b3851  lea     rcx, [rbp+60h+var_D8]; retstr
0x1800b3855  call    ?GetHiMetricToPixelXForm@@YA?AUtagXFORM@@PEAUHDC__@@@Z; GetHiMetricToPixelXForm(HDC__ *)
0x1800b385a  movups  xmm0, xmmword ptr [rax]
0x1800b385d  movups  xmmword ptr [rbp+60h+xf2.eM11], xmm0
0x1800b3861  movsd   xmm1, qword ptr [rax+10h]
0x1800b3866  movsd   qword ptr [rbp+60h+xf2.eDx], xmm1
0x1800b386b  test    rbx, rbx
0x1800b386e  jz      short loc_1800B387D
0x1800b3870  mov     rdx, rbx; hDC
0x1800b3873  mov     rcx, [rdi+38h]; hWnd
0x1800b3877  call    cs:__imp_ReleaseDC
0x1800b387d  lea     r8, [rbp+60h+xf2]; lpxf2
0x1800b3881  lea     rdx, [rbp+60h+xf1]; lpxf1
0x1800b3885  lea     rcx, [rbp+60h+xfOut]; lpxfOut
0x1800b3889  call    cs:__imp_CombineTransform
0x1800b388f  lea     r8, [rbp+60h+xfOut]; lpxf2
0x1800b3893  lea     rdx, [rbp+60h+var_A8]; lpxf1
0x1800b3897  lea     rcx, [rsp+160h+var_F0]; lpxfOut
0x1800b389c  call    cs:__imp_CombineTransform
0x1800b38a2  movss   xmm3, [rsp+160h+var_F0.eM11]
0x1800b38a8  movss   xmm5, [rsp+160h+var_F0.eM22]
0x1800b38ae  mulss   xmm3, xmm5
0x1800b38b2  movss   xmm4, [rsp+160h+var_F0.eM12]
0x1800b38b8  movaps  xmm0, xmm4
0x1800b38bb  mulss   xmm0, [rsp+160h+var_F0.eM21]
0x1800b38c1  subss   xmm3, xmm0
0x1800b38c5  cvtps2pd xmm1, xmm3
0x1800b38c8  movsd   xmm0, cs:__real@3e112e0be826d695
0x1800b38d0  comisd  xmm0, xmm1
0x1800b38d4  jbe     short loc_1800B38EA
0x1800b38d6  comisd  xmm1, cs:__real@be112e0be826d695
0x1800b38de  jbe     short loc_1800B38EA
0x1800b38e0  mov     ebx, 80004005h
0x1800b38e5  jmp     loc_1800B3AB4
0x1800b38ea  movaps  xmm0, xmm5
0x1800b38ed  divss   xmm0, xmm3
0x1800b38f1  movss   [rbp+60h+var_C0.eM11], xmm0
0x1800b38f6  movaps  xmm1, xmm4
0x1800b38f9  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x1800b3900  divss   xmm1, xmm3
0x1800b3904  movss   [rbp+60h+var_C0.eM12], xmm1
0x1800b3909  movss   xmm0, [rsp+160h+var_F0.eM21]
0x1800b390f  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x1800b3916  divss   xmm0, xmm3
0x1800b391a  movss   [rbp+60h+var_C0.eM21], xmm0
0x1800b391f  movss   xmm0, [rsp+160h+var_F0.eM11]
0x1800b3925  divss   xmm0, xmm3
0x1800b3929  movss   [rbp+60h+var_C0.eM22], xmm0
0x1800b392e  movss   xmm2, [rbp+60h+var_F0.eDy]
0x1800b3933  movaps  xmm1, xmm2
0x1800b3936  mulss   xmm1, [rsp+160h+var_F0.eM21]
0x1800b393c  mulss   xmm5, [rbp+60h+var_F0.eDx]
0x1800b3941  subss   xmm1, xmm5
0x1800b3945  divss   xmm1, xmm3
0x1800b3949  movss   [rbp+60h+var_C0.eDx], xmm1
0x1800b394e  mulss   xmm4, [rbp+60h+var_F0.eDx]
0x1800b3953  mulss   xmm2, [rsp+160h+var_F0.eM11]
0x1800b3959  subss   xmm4, xmm2
0x1800b395d  divss   xmm4, xmm3
0x1800b3961  movss   [rbp+60h+var_C0.eDy], xmm4
0x1800b3966  mov     ecx, [rsp+160h+Rect.right]
0x1800b396a  mov     edx, [rsp+160h+Rect.bottom]
0x1800b396e  mov     eax, [rsp+160h+Points.x+8]
0x1800b3972  mov     r8d, [rsp+160h+Points.y+8]
0x1800b3977  mov     qword ptr [rbp+60h+var_D8.eM11], 0
0x1800b397f  mov     qword ptr [rbp+60h+var_D8.eM21], 0
0x1800b3987  sub     ecx, [rsp+160h+Rect.left]
0x1800b398b  movd    xmm2, ecx
0x1800b398f  cvtdq2ps xmm2, xmm2
0x1800b3992  sub     eax, [rsp+160h+Points.x]
0x1800b3996  movd    xmm0, eax
0x1800b399a  cvtdq2ps xmm0, xmm0
0x1800b399d  movss   xmm3, cs:__real@3f800000
0x1800b39a5  comiss  xmm3, xmm0
0x1800b39a8  ja      short loc_1800B39AE
0x1800b39aa  divss   xmm2, xmm0
0x1800b39ae  movss   [rbp+60h+var_D8.eM11], xmm2
0x1800b39b3  movd    xmm1, [rsp+160h+Rect.left]
0x1800b39b9  cvtdq2ps xmm1, xmm1
0x1800b39bc  movd    xmm0, [rsp+160h+Points.x]
0x1800b39c2  cvtdq2ps xmm0, xmm0
0x1800b39c5  mulss   xmm0, xmm2
0x1800b39c9  subss   xmm1, xmm0
0x1800b39cd  movss   [rbp+60h+var_D8.eDx], xmm1
0x1800b39d2  sub     edx, [rsp+160h+Rect.top]
0x1800b39d6  movd    xmm2, edx
0x1800b39da  cvtdq2ps xmm2, xmm2
0x1800b39dd  sub     r8d, [rsp+160h+Points.y]
0x1800b39e2  movd    xmm0, r8d
0x1800b39e7  cvtdq2ps xmm0, xmm0
0x1800b39ea  comiss  xmm3, xmm0
0x1800b39ed  ja      short loc_1800B39F3
0x1800b39ef  divss   xmm2, xmm0
0x1800b39f3  movss   [rbp+60h+var_D8.eM22], xmm2
0x1800b39f8  movd    xmm1, [rsp+160h+Rect.top]
0x1800b39fe  cvtdq2ps xmm1, xmm1
0x1800b3a01  movd    xmm0, [rsp+160h+Points.y]
0x1800b3a07  cvtdq2ps xmm0, xmm0
0x1800b3a0a  mulss   xmm0, xmm2
0x1800b3a0e  subss   xmm1, xmm0
0x1800b3a12  movss   [rbp+60h+var_D8.eDy], xmm1
0x1800b3a17  movups  xmm0, xmmword ptr [rbp+60h+var_D8.eM11]
0x1800b3a1b  movups  xmmword ptr [rbp+60h+var_78.eM11], xmm0
0x1800b3a1f  movsd   xmm1, qword ptr [rbp+60h+var_D8.eDx]
0x1800b3a24  movsd   qword ptr [rbp+60h+var_78.eDx], xmm1
0x1800b3a29  lea     r8, [rbp+60h+var_C0]; lpxf2
0x1800b3a2d  lea     rdx, [rbp+60h+var_78]; lpxf1
0x1800b3a31  lea     rcx, [rbp+60h+var_48]; lpxfOut
0x1800b3a35  call    cs:__imp_CombineTransform
0x1800b3a3b  mov     [rsp+160h+var_140], 0
0x1800b3a43  mov     rax, [rsi]
0x1800b3a46  lea     rdx, [rsp+160h+var_140]
0x1800b3a4b  mov     rcx, rsi
0x1800b3a4e  mov     rax, [rax+18h]
0x1800b3a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a57  mov     ebx, eax
0x1800b3a59  test    eax, eax
0x1800b3a5b  js      short loc_1800B3AB4
0x1800b3a5d  mov     rcx, [rdi+220h]
0x1800b3a64  mov     rax, [rcx]
0x1800b3a67  lea     r8, [rbp+60h+var_48]
0x1800b3a6b  mov     edx, [rsp+160h+var_140]
0x1800b3a6f  mov     rax, [rax+28h]
0x1800b3a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a78  mov     ebx, eax
0x1800b3a7a  test    eax, eax
0x1800b3a7c  js      short loc_1800B3AB4
0x1800b3a7e  mov     rcx, [rdi+238h]
0x1800b3a85  mov     rax, [rcx]
0x1800b3a88  lea     rdx, [rbp+60h+var_A8]
0x1800b3a8c  mov     rax, [rax+38h]
  ... truncated ...
```
