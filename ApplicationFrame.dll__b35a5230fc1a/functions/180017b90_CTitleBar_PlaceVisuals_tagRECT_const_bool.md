# CTitleBar::_PlaceVisuals(tagRECT const *,bool)

- ea: `0x180017b90`
- end: `0x180017e65`
- name: `?_PlaceVisuals@CTitleBar@@AEAAJPEBUtagRECT@@_N@Z`
- size: `725`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this, const struct tagRECT *, bool)`
- caller_count: `8`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180009460`
- `0x18000b080`
- `0x180024ef8`
- `0x180025614`
- `0x18003d510`
- `0x18003dc64`
- `0x180040170`
- `0x180059d80`

## callees

- `0x180015840`
- `0x1800158f0`
- `0x180017934`
- `0x180017b90`
- `0x180017e6c`
- `0x180017ef0`
- `0x180018cf0`
- `0x180018e5c`
- `0x180018f58`
- `0x1800191c0`
- `0x180024184`
- `0x180040270`
- `0x180042d7c`
- `0x180043c30`
- `0x180054940`
- `0x180055b08`
- `0x180056694`
- `0x180057140`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180017c8d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180017c9d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180017c8d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180017c9d`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180017dc8`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180017dc8`

## pseudocode

```c
__int64 __fastcall CTitleBar::_PlaceVisuals(HWND *this, const struct tagRECT *a2, char a3)
{
  __int128 *v3; // rax
  __int128 *v5; // r9
  __int64 v7; // rcx
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  LONG *v23; // rdi
  _OWORD *v24; // r14
  LONG top; // ecx
  LONG right; // edx
  LONG bottom; // r8d
  int v28; // eax
  int v29; // ecx
  int updated; // eax
  int v32; // eax
  unsigned int v33; // edi
  __int64 v34; // rax
  volatile int *v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  CTitleBar *v39; // [rsp+20h] [rbp-1B8h] BYREF
  _BYTE v40[24]; // [rsp+28h] [rbp-1B0h] BYREF
  _BYTE v41[368]; // [rsp+40h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v3 = (__int128 *)((char *)this + 884);
  v5 = (__int128 *)v41;
  v7 = 2;
  do
  {
    v5 += 8;
    v9 = *v3;
    v10 = v3[1];
    v3 += 8;
    *(v5 - 8) = v9;
    v11 = *(v3 - 6);
    *(v5 - 7) = v10;
    v12 = *(v3 - 5);
    *(v5 - 6) = v11;
    v13 = *(v3 - 4);
    *(v5 - 5) = v12;
    v14 = *(v3 - 3);
    *(v5 - 4) = v13;
    v15 = *(v3 - 2);
    *(v5 - 3) = v14;
    v16 = *(v3 - 1);
    *(v5 - 2) = v15;
    *(v5 - 1) = v16;
    --v7;
  }
  while ( v7 );
  v17 = v3[1];
  *v5 = *v3;
  v18 = v3[2];
  v5[1] = v17;
  v19 = v3[3];
  v5[2] = v18;
  v20 = v3[4];
  v5[3] = v19;
  v21 = v3[5];
  v5[4] = v20;
  v22 = v3[6];
  v5[5] = v21;
  v5[6] = v22;
  if ( !*((_BYTE *)this + 576) )
  {
    v23 = (LONG *)this + 209;
    SetRectEmpty((LPRECT)((char *)this + 836));
    v24 = (_OWORD *)((char *)this + 852);
    SetRectEmpty((LPRECT)((char *)this + 852));
    CTitleBar::UpdateBorderVisibilityAndMargins((CTitleBar *)this);
    if ( a2 )
    {
      top = a2->top;
      right = a2->right;
      bottom = a2->bottom;
      *v23 = a2->left;
      *((_DWORD *)this + 210) = top;
      *((_DWORD *)this + 211) = right;
      *((_DWORD *)this + 212) = bottom;
    }
    else
    {
      GetClientRect(this[63], (LPRECT)((char *)this + 836));
    }
    v28 = 32 * *((_DWORD *)this + 132);
    *v24 = *(_OWORD *)v23;
    *((_DWORD *)this + 216) = *((_DWORD *)this + 214) - (int)(float)((float)v28 / -100.0);
    v29 = *((_DWORD *)this + 157);
    *((_DWORD *)this + 215) -= *((_DWORD *)this + 213);
    *((_DWORD *)this + 216) += v29 - *((_DWORD *)this + 214);
    *((_DWORD *)this + 214) = v29;
    *(_DWORD *)v24 = 0;
    CTitleBar::_ComputeLayoutRects((CTitleBar *)this);
    CTitleBar::_ComputeHitTestRects((CTitleBar *)this);
    CTitleBar::_UpdateDwmFrameInset((CTitleBar *)this);
  }
  if ( *((_BYTE *)this + 558) || *((_BYTE *)this + 576) )
    return 0;
  if ( a3 )
  {
    updated = CTitleBar::_UpdateConstraints((CTitleBar *)this);
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA21,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
        (const char *)(unsigned int)updated,
        (int)v39);
  }
  v32 = CTitleBar::_ManuallyPositionElements((CTitleBar *)this);
  v33 = v32;
  if ( v32 >= 0 )
  {
    v34 = lambda_da8f0cb0d38a7c0413d97f66b7e8af4f_::_lambda_da8f0cb0d38a7c0413d97f66b7e8af4f_(v40, this, v41);
    CTitleBar::ForEachAccObject__lambda_122e5656e384625b99216853f89ea554___(this, v34);
    if ( CTitleBar::_DidReservedMetricsChange((CTitleBar *)this) )
    {
      v39 = (CTitleBar *)this;
      Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)((char *)this + 100), v35);
      v36 = lambda_fdcf2faf594359369074b2a23ff12927_::_lambda_fdcf2faf594359369074b2a23ff12927_(v40, &v39);
      Windows::Internal::ComTaskPool::QueueTask__lambda_1a983346cd6749a8040d8447a221ccd3___(
        v38,
        v37,
        *((unsigned int *)this + 374),
        v36,
        v39);
      lambda_fdcf2faf594359369074b2a23ff12927_::__lambda_fdcf2faf594359369074b2a23ff12927_(v40);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithGITSite,Microsoft::WRL::ChainInterfaces<IApplicationFrameTitleBarInternal,IApplicationFrameTitleBar2,IApplicationFrameTitleBar,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::Release(this + 2);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA25,
    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
    (const char *)(unsigned int)v32,
    (int)v39);
  return v33;
}

```

## disassembly

```asm
0x180017b90  push    rbx
0x180017b92  push    rbp
0x180017b93  sub     rsp, 1C8h
0x180017b9a  mov     rax, cs:__security_cookie
0x180017ba1  xor     rax, rsp
0x180017ba4  mov     [rsp+1D8h+var_28], rax
0x180017bac  mov     [rsp+1D8h+arg_10], rsi
0x180017bb4  lea     rax, [rcx+374h]
0x180017bbb  mov     rbx, rcx
0x180017bbe  lea     r9, [rsp+1D8h+var_198]
0x180017bc3  mov     rsi, rdx
0x180017bc6  mov     ecx, 2
0x180017bcb  movzx   ebp, r8b
0x180017bcf  lea     r9, [r9+80h]
0x180017bd6  movups  xmm0, xmmword ptr [rax]
0x180017bd9  movups  xmm1, xmmword ptr [rax+10h]
0x180017bdd  lea     rax, [rax+80h]
0x180017be4  movups  xmmword ptr [r9-80h], xmm0
0x180017be9  movups  xmm0, xmmword ptr [rax-60h]
0x180017bed  movups  xmmword ptr [r9-70h], xmm1
0x180017bf2  movups  xmm1, xmmword ptr [rax-50h]
0x180017bf6  movups  xmmword ptr [r9-60h], xmm0
0x180017bfb  movups  xmm0, xmmword ptr [rax-40h]
0x180017bff  movups  xmmword ptr [r9-50h], xmm1
0x180017c04  movups  xmm1, xmmword ptr [rax-30h]
0x180017c08  movups  xmmword ptr [r9-40h], xmm0
0x180017c0d  movups  xmm0, xmmword ptr [rax-20h]
0x180017c11  movups  xmmword ptr [r9-30h], xmm1
0x180017c16  movups  xmm1, xmmword ptr [rax-10h]
0x180017c1a  movups  xmmword ptr [r9-20h], xmm0
0x180017c1f  movups  xmmword ptr [r9-10h], xmm1
0x180017c24  sub     rcx, 1
0x180017c28  jnz     short loc_180017BCF
0x180017c2a  movups  xmm0, xmmword ptr [rax]
0x180017c2d  mov     [rsp+1D8h+arg_18], rdi
0x180017c35  movups  xmm1, xmmword ptr [rax+10h]
0x180017c39  movups  xmmword ptr [r9], xmm0
0x180017c3d  movups  xmm0, xmmword ptr [rax+20h]
0x180017c41  movups  xmmword ptr [r9+10h], xmm1
0x180017c46  movups  xmm1, xmmword ptr [rax+30h]
0x180017c4a  movups  xmmword ptr [r9+20h], xmm0
0x180017c4f  movups  xmm0, xmmword ptr [rax+40h]
0x180017c53  movups  xmmword ptr [r9+30h], xmm1
0x180017c58  movups  xmm1, xmmword ptr [rax+50h]
0x180017c5c  movups  xmmword ptr [r9+40h], xmm0
0x180017c61  movups  xmm0, xmmword ptr [rax+60h]
0x180017c65  movups  xmmword ptr [r9+50h], xmm1
0x180017c6a  movups  xmmword ptr [r9+60h], xmm0
0x180017c6f  cmp     [rbx+240h], cl
0x180017c75  jnz     loc_180017D3D
0x180017c7b  lea     rdi, [rbx+344h]
0x180017c82  mov     [rsp+1D8h+var_18], r14
0x180017c8a  mov     rcx, rdi; lprc
0x180017c8d  call    cs:__imp_SetRectEmpty
0x180017c93  lea     r14, [rbx+354h]
0x180017c9a  mov     rcx, r14; lprc
0x180017c9d  call    cs:__imp_SetRectEmpty
0x180017ca3  mov     rcx, rbx; this
0x180017ca6  call    ?UpdateBorderVisibilityAndMargins@CTitleBar@@AEAA_NXZ; CTitleBar::UpdateBorderVisibilityAndMargins(void)
0x180017cab  test    rsi, rsi
0x180017cae  jz      loc_180017DBE
0x180017cb4  mov     ecx, [rsi+4]
0x180017cb7  mov     edx, [rsi+8]
0x180017cba  mov     r8d, [rsi+0Ch]
0x180017cbe  mov     eax, [rsi]
0x180017cc0  mov     [rdi], eax
0x180017cc2  mov     [rdi+4], ecx
0x180017cc5  mov     [rdi+8], edx
0x180017cc8  mov     [rdi+0Ch], r8d
0x180017ccc  movups  xmm0, xmmword ptr [rdi]
0x180017ccf  mov     eax, [rbx+210h]
0x180017cd5  shl     eax, 5
0x180017cd8  movups  xmmword ptr [r14], xmm0
0x180017cdc  mov     ecx, [rbx+358h]
0x180017ce2  movd    xmm0, eax
0x180017ce6  cvtdq2ps xmm0, xmm0
0x180017ce9  divss   xmm0, cs:__real@c2c80000
0x180017cf1  cvttss2si eax, xmm0
0x180017cf5  sub     ecx, eax
0x180017cf7  mov     [r14+0Ch], ecx
0x180017cfb  mov     ecx, [rbx+274h]
0x180017d01  mov     eax, [r14]
0x180017d04  sub     [r14+8], eax
0x180017d08  mov     eax, ecx
0x180017d0a  sub     eax, [r14+4]
0x180017d0e  add     [r14+0Ch], eax
0x180017d12  mov     [r14+4], ecx
0x180017d16  mov     rcx, rbx; this
0x180017d19  mov     dword ptr [r14], 0
0x180017d20  call    ?_ComputeLayoutRects@CTitleBar@@AEAAXXZ; CTitleBar::_ComputeLayoutRects(void)
0x180017d25  mov     rcx, rbx; this
0x180017d28  call    ?_ComputeHitTestRects@CTitleBar@@AEAAXXZ; CTitleBar::_ComputeHitTestRects(void)
0x180017d2d  mov     rcx, rbx; this
0x180017d30  call    ?_UpdateDwmFrameInset@CTitleBar@@AEAAXXZ; CTitleBar::_UpdateDwmFrameInset(void)
0x180017d35  mov     r14, [rsp+1D8h+var_18]
0x180017d3d  cmp     byte ptr [rbx+22Eh], 0
0x180017d44  mov     rsi, [rsp+1D8h+arg_10]
0x180017d4c  jz      short loc_180017D72
0x180017d4e  xor     eax, eax
0x180017d50  mov     rdi, [rsp+1D8h+arg_18]
0x180017d58  mov     rcx, [rsp+1D8h+var_28]
0x180017d60  xor     rcx, rsp; StackCookie
0x180017d63  call    __security_check_cookie
0x180017d68  add     rsp, 1C8h
0x180017d6f  pop     rbp
0x180017d70  pop     rbx
0x180017d71  retn
0x180017d72  cmp     byte ptr [rbx+240h], 0
0x180017d79  jnz     short loc_180017D4E
0x180017d7b  test    bpl, bpl
0x180017d7e  jz      short loc_180017D90
0x180017d80  mov     rcx, rbx; this
0x180017d83  call    ?_UpdateConstraints@CTitleBar@@AEAAJXZ; CTitleBar::_UpdateConstraints(void)
0x180017d88  test    eax, eax
0x180017d8a  js      loc_180017E44
0x180017d90  mov     rcx, rbx; this
0x180017d93  call    ?_ManuallyPositionElements@CTitleBar@@AEAAJXZ; CTitleBar::_ManuallyPositionElements(void)
0x180017d98  mov     edi, eax
0x180017d9a  test    eax, eax
0x180017d9c  jns     short loc_180017DD3
0x180017d9e  mov     rcx, [rsp+1D8h]; this
0x180017da6  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180017dad  mov     r9d, eax; char *
0x180017db0  mov     edx, 0A25h; void *
0x180017db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017dba  mov     eax, edi
0x180017dbc  jmp     short loc_180017D50
0x180017dbe  mov     rcx, [rbx+1F8h]; hWnd
0x180017dc5  mov     rdx, rdi; lpRect
0x180017dc8  call    cs:__imp_GetClientRect
0x180017dce  jmp     loc_180017CCC
0x180017dd3  lea     r8, [rsp+1D8h+var_198]
0x180017dd8  mov     rdx, rbx
0x180017ddb  lea     rcx, [rsp+1D8h+var_1B0]
0x180017de0  call    _lambda_da8f0cb0d38a7c0413d97f66b7e8af4f____lambda_da8f0cb0d38a7c0413d97f66b7e8af4f_
0x180017de5  mov     rdx, rax
0x180017de8  mov     rcx, rbx
0x180017deb  call    CTitleBar__ForEachAccObject__lambda_122e5656e384625b99216853f89ea554___
0x180017df0  mov     rcx, rbx; this
0x180017df3  call    ?_DidReservedMetricsChange@CTitleBar@@AEAA_NXZ; CTitleBar::_DidReservedMetricsChange(void)
0x180017df8  test    al, al
0x180017dfa  jz      loc_180017D4E
0x180017e00  lea     rcx, [rbx+64h]; this
0x180017e04  mov     [rsp+1D8h+var_1B8], rbx
0x180017e09  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180017e0e  lea     rdx, [rsp+1D8h+var_1B8]
0x180017e13  lea     rcx, [rsp+1D8h+var_1B0]
0x180017e18  call    _lambda_fdcf2faf594359369074b2a23ff12927____lambda_fdcf2faf594359369074b2a23ff12927_
0x180017e1d  mov     r8d, [rbx+5D8h]
0x180017e24  mov     r9, rax
0x180017e27  call    Windows__Internal__ComTaskPool__QueueTask__lambda_1a983346cd6749a8040d8447a221ccd3___
0x180017e2c  lea     rcx, [rsp+1D8h+var_1B0]
0x180017e31  call    _lambda_fdcf2faf594359369074b2a23ff12927_____lambda_fdcf2faf594359369074b2a23ff12927_
0x180017e36  lea     rcx, [rbx+10h]
0x180017e3a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCWRLObjectWithGITSite@@U?$ChainInterfaces@UIApplicationFrameTitleBarInternal@@UIApplicationFrameTitleBar2@@UIApplicationFrameTitleBar@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithGITSite,Microsoft::WRL::ChainInterfaces<IApplicationFrameTitleBarInternal,IApplicationFrameTitleBar2,IApplicationFrameTitleBar,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::Release(void)
0x180017e3f  jmp     loc_180017D4E
0x180017e44  mov     rcx, [rsp+1D8h]; this
0x180017e4c  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180017e53  mov     r9d, eax; char *
0x180017e56  mov     edx, 0A21h; void *
0x180017e5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017e60  jmp     loc_180017D90
```
