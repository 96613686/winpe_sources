# CRectTracker::TrackHandle(int,CWnd *,CPoint,CWnd *)

- ea: `0x180050a20`
- end: `0x180050d52`
- name: `?TrackHandle@CRectTracker@@IEAAHHPEAVCWnd@@VCPoint@@0@Z`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800509c0`
- `0x180050d60`

## callees

- `0x180010c40`
- `0x180012eb0`
- `0x1800166a0`
- `0x180022800`
- `0x1800441c0`
- `0x180050380`
- `0x180050590`
- `0x180050a20`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!GetCapture` at `0x180050a5e`
- `USER32!GetCapture` at `0x180050a5e`
- `USER32!EqualRect` at `0x180050c08`
- `USER32!EqualRect` at `0x180050c6f`
- `USER32!EqualRect` at `0x180050d23`
- `USER32!EqualRect` at `0x180050c08`
- `USER32!EqualRect` at `0x180050c6f`
- `USER32!EqualRect` at `0x180050d23`
- `USER32!DispatchMessageW` at `0x180050b8b`
- `USER32!DispatchMessageW` at `0x180050b8b`
- `USER32!UpdateWindow` at `0x180050a9c`
- `USER32!UpdateWindow` at `0x180050aab`
- `USER32!UpdateWindow` at `0x180050a9c`
- `USER32!UpdateWindow` at `0x180050aab`
- `USER32!ReleaseCapture` at `0x180050cfa`
- `USER32!ReleaseCapture` at `0x180050cfa`
- `USER32!GetMessageW` at `0x180050b51`
- `USER32!GetMessageW` at `0x180050b51`
- `USER32!ReleaseDC` at `0x180050cf4`
- `USER32!ReleaseDC` at `0x180050cf4`
- `USER32!GetDCEx` at `0x180050b19`
- `USER32!GetDCEx` at `0x180050b19`

## pseudocode

```c
_BOOL8 __fastcall CRectTracker::TrackHandle(__int64 a1, int a2, HWND *a3, __int64 a4, __int64 a5)
{
  int v5; // ebx
  struct AFX_MODULE_THREAD_STATE *ModuleThreadState; // rax
  RECT v11; // xmm0
  int v12; // ebx
  HDC DCEx; // rax
  struct CDC *DC; // rax
  struct CDC *v15; // r12
  int v16; // esi
  __int64 v17; // rdx
  void (__fastcall **v18)(__int64, RECT *, __int64, struct CDC *, HWND *); // rax
  HWND v19; // rcx
  int v20; // [rsp+30h] [rbp-71h] BYREF
  int v21; // [rsp+34h] [rbp-6Dh] BYREF
  unsigned int v22; // [rsp+38h] [rbp-69h]
  int v23; // [rsp+3Ch] [rbp-65h]
  int v24; // [rsp+40h] [rbp-61h]
  int *v25; // [rsp+48h] [rbp-59h] BYREF
  int *v26; // [rsp+50h] [rbp-51h] BYREF
  struct tagMSG Msg; // [rsp+58h] [rbp-49h] BYREF
  RECT rc1; // [rsp+88h] [rbp-19h] BYREF
  RECT v29; // [rsp+98h] [rbp-9h] BYREF
  int v30; // [rsp+11Ch] [rbp+7Bh]

  v30 = HIDWORD(a4);
  v5 = a4;
  v22 = a2;
  if ( GetCapture() )
    return 0;
  ModuleThreadState = AfxGetModuleThreadState();
  ++*((_DWORD *)ModuleThreadState + 8);
  v23 = *(_DWORD *)(a1 + 20) - *(_DWORD *)(a1 + 12);
  v24 = *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16);
  CWnd::SetCapture((CWnd *)a3);
  UpdateWindow(a3[8]);
  if ( a5 )
    UpdateWindow(*(HWND *)(a5 + 64));
  v11 = *(RECT *)(a1 + 12);
  v25 = 0;
  v26 = 0;
  v21 = 0;
  v20 = 0;
  v29 = v11;
  CRectTracker::GetModifyPointers((CRectTracker *)a1, a2, &v25, &v26, &v21, &v20);
  v12 = v5 - v21;
  v20 = v30 - v20;
  if ( a5 )
  {
    DCEx = GetDCEx(*(HWND *)(a5 + 64), 0, 2u);
    DC = CDC::FromHandle(DCEx);
  }
  else
  {
    DC = CWnd::GetDC((CWnd *)a3);
  }
  v15 = DC;
  v16 = 0;
  while ( 1 )
  {
    memset(&Msg, 0, sizeof(Msg));
    GetMessageW(&Msg, 0, 0, 0);
    if ( CWnd::GetCapture() != (struct CWnd *)a3 )
      break;
    switch ( Msg.message )
    {
      case 0x100u:
        if ( Msg.wParam == 27 )
        {
LABEL_31:
          if ( v16 )
          {
            *(_DWORD *)(a1 + 72) = 1;
            *(_DWORD *)(a1 + 68) = 1;
            (**(void (__fastcall ***)(__int64, __int64, __int64, struct CDC *, HWND *))a1)(a1, a1 + 12, a5, v15, a3);
          }
          *(RECT *)(a1 + 12) = v29;
          goto LABEL_34;
        }
        break;
      case 0x200u:
      case 0x202u:
        rc1 = *(RECT *)(a1 + 12);
        if ( v25 )
          *v25 = SLOWORD(Msg.lParam) - v12;
        if ( v26 )
          *v26 = SWORD1(Msg.lParam) - v20;
        v17 = v22;
        if ( v22 == 8 )
        {
          *(_DWORD *)(a1 + 20) = *(_DWORD *)(a1 + 12) + v23;
          *(_DWORD *)(a1 + 24) = *(_DWORD *)(a1 + 16) + v24;
        }
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, v17, a1 + 12);
        *(_DWORD *)(a1 + 72) = Msg.message == 514;
        if ( !EqualRect(&rc1, (const RECT *)(a1 + 12)) || *(_DWORD *)(a1 + 72) )
        {
          if ( v16 )
          {
            v18 = *(void (__fastcall ***)(__int64, RECT *, __int64, struct CDC *, HWND *))a1;
            *(_DWORD *)(a1 + 68) = 1;
            (*v18)(a1, &rc1, a5, v15, a3);
          }
          (*(void (__fastcall **)(__int64, RECT *))(*(_QWORD *)a1 + 16LL))(a1, &rc1);
          if ( Msg.message != 514 )
            v16 = 1;
          if ( *(_DWORD *)(a1 + 72) )
            goto LABEL_34;
        }
        if ( !EqualRect(&rc1, (const RECT *)(a1 + 12)) )
        {
          *(_DWORD *)(a1 + 68) = 0;
          (**(void (__fastcall ***)(__int64, __int64, __int64, struct CDC *, HWND *))a1)(a1, a1 + 12, a5, v15, a3);
        }
        break;
      case 0x204u:
        goto LABEL_31;
      default:
        DispatchMessageW(&Msg);
        break;
    }
  }
LABEL_34:
  if ( a5 )
    v19 = *(HWND *)(a5 + 64);
  else
    v19 = a3[8];
  ReleaseDC(v19, *((HDC *)v15 + 1));
  ReleaseCapture();
  AfxUnlockTempMaps(0);
  if ( !v16 )
    *(RECT *)(a1 + 12) = v29;
  *(_QWORD *)(a1 + 68) = 0;
  return !EqualRect(&v29, (const RECT *)(a1 + 12));
}

```

## disassembly

```asm
0x180050a20  mov     [rsp-8+arg_18], r9
0x180050a25  push    rbp
0x180050a26  push    rbx
0x180050a27  push    rsi
0x180050a28  push    rdi
0x180050a29  push    r12
0x180050a2b  push    r13
0x180050a2d  push    r14
0x180050a2f  push    r15
0x180050a31  lea     rbp, [rsp-17h]
0x180050a36  sub     rsp, 0B8h
0x180050a3d  mov     rax, cs:__security_cookie
0x180050a44  xor     rax, rsp
0x180050a47  mov     [rbp+4Fh+var_48], rax
0x180050a4b  mov     r14, [rbp+4Fh+arg_20]
0x180050a4f  mov     rbx, r9
0x180050a52  mov     r15, r8
0x180050a55  mov     [rbp+4Fh+var_B8], edx
0x180050a58  mov     r12d, edx
0x180050a5b  mov     rdi, rcx
0x180050a5e  call    cs:__imp_GetCapture
0x180050a64  test    rax, rax
0x180050a67  jz      short loc_180050A70
0x180050a69  xor     eax, eax
0x180050a6b  jmp     loc_180050D32
0x180050a70  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180050a75  lea     r13, [rdi+0Ch]
0x180050a79  mov     rcx, r15; this
0x180050a7c  inc     dword ptr [rax+20h]
0x180050a7f  mov     eax, [r13+8]
0x180050a83  sub     eax, [r13+0]
0x180050a87  mov     [rbp+4Fh+var_B4], eax
0x180050a8a  mov     eax, [rdi+18h]
0x180050a8d  sub     eax, [rdi+10h]
0x180050a90  mov     [rbp+4Fh+var_B0], eax
0x180050a93  call    ?SetCapture@CWnd@@QEAAPEAV1@XZ; CWnd::SetCapture(void)
0x180050a98  mov     rcx, [r15+40h]; hWnd
0x180050a9c  call    cs:__imp_UpdateWindow
0x180050aa2  test    r14, r14
0x180050aa5  jz      short loc_180050AB1
0x180050aa7  mov     rcx, [r14+40h]; hWnd
0x180050aab  call    cs:__imp_UpdateWindow
0x180050ab1  movups  xmm0, xmmword ptr [r13+0]
0x180050ab6  lea     rax, [rbp+4Fh+var_C0]
0x180050aba  mov     [rbp+4Fh+var_A8], 0
0x180050ac2  mov     [rsp+0F0h+var_C8], rax; int *
0x180050ac7  lea     r9, [rbp+4Fh+var_A0]; int **
0x180050acb  lea     rax, [rbp+4Fh+var_BC]
0x180050acf  mov     [rbp+4Fh+var_A0], 0
0x180050ad7  lea     r8, [rbp+4Fh+var_A8]; int **
0x180050adb  mov     [rsp+0F0h+var_D0], rax; int *
0x180050ae0  mov     edx, r12d; int
0x180050ae3  mov     [rbp+4Fh+var_BC], 0
0x180050aea  mov     rcx, rdi; this
0x180050aed  mov     [rbp+4Fh+var_C0], 0
0x180050af4  movdqu  xmmword ptr [rbp+4Fh+var_58.left], xmm0
0x180050af9  call    ?GetModifyPointers@CRectTracker@@IEAAXHPEAPEAH0PEAH1@Z; CRectTracker::GetModifyPointers(int,int * *,int * *,int *,int *)
0x180050afe  mov     eax, dword ptr [rbp+4Fh+arg_18+4]
0x180050b01  sub     eax, [rbp+4Fh+var_C0]
0x180050b04  sub     ebx, [rbp+4Fh+var_BC]
0x180050b07  mov     [rbp+4Fh+var_C0], eax
0x180050b0a  test    r14, r14
0x180050b0d  jz      short loc_180050B29
0x180050b0f  mov     rcx, [r14+40h]; hWnd
0x180050b13  xor     edx, edx; hrgnClip
0x180050b15  lea     r8d, [rdx+2]; flags
0x180050b19  call    cs:__imp_GetDCEx
0x180050b1f  mov     rcx, rax; HDC
0x180050b22  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x180050b27  jmp     short loc_180050B31
0x180050b29  mov     rcx, r15; this
0x180050b2c  call    ?GetDC@CWnd@@QEAAPEAVCDC@@XZ; CWnd::GetDC(void)
0x180050b31  mov     r12, rax
0x180050b34  xor     esi, esi
0x180050b36  xorps   xmm0, xmm0
0x180050b39  lea     rcx, [rbp+4Fh+Msg]; lpMsg
0x180050b3d  xor     r9d, r9d; wMsgFilterMax
0x180050b40  xor     r8d, r8d; wMsgFilterMin
0x180050b43  xor     edx, edx; hWnd
0x180050b45  movups  xmmword ptr [rbp+4Fh+Msg.hwnd], xmm0
0x180050b49  movups  xmmword ptr [rbp+4Fh+Msg.wParam], xmm0
0x180050b4d  movups  xmmword ptr [rbp+4Fh+Msg.time], xmm0
0x180050b51  call    cs:__imp_GetMessageW
0x180050b57  call    ?GetCapture@CWnd@@SAPEAV1@XZ; CWnd::GetCapture(void)
0x180050b5c  cmp     rax, r15
0x180050b5f  jnz     loc_180050CE0
0x180050b65  mov     eax, [rbp+4Fh+Msg.message]
0x180050b68  mov     ecx, 100h
0x180050b6d  sub     eax, ecx
0x180050b6f  jz      loc_180050CA1
0x180050b75  sub     eax, ecx
0x180050b77  jz      short loc_180050B93
0x180050b79  sub     eax, 2
0x180050b7c  jz      short loc_180050B93
0x180050b7e  cmp     eax, 2
0x180050b81  jz      loc_180050CAC
0x180050b87  lea     rcx, [rbp+4Fh+Msg]; lpMsg
0x180050b8b  call    cs:__imp_DispatchMessageW
0x180050b91  jmp     short loc_180050B36
0x180050b93  movups  xmm0, xmmword ptr [rdi+0Ch]
0x180050b97  mov     rcx, [rbp+4Fh+var_A8]
0x180050b9b  movdqu  xmmword ptr [rbp+4Fh+rc1.left], xmm0
0x180050ba0  test    rcx, rcx
0x180050ba3  jz      short loc_180050BAD
0x180050ba5  movsx   eax, word ptr [rbp+4Fh+Msg.lParam]
0x180050ba9  sub     eax, ebx
0x180050bab  mov     [rcx], eax
0x180050bad  mov     rdx, [rbp+4Fh+var_A0]
0x180050bb1  test    rdx, rdx
0x180050bb4  jz      short loc_180050BC6
0x180050bb6  mov     rax, [rbp+4Fh+Msg.lParam]
0x180050bba  shr     rax, 10h
0x180050bbe  movsx   ecx, ax
0x180050bc1  sub     ecx, [rbp+4Fh+var_C0]
0x180050bc4  mov     [rdx], ecx
0x180050bc6  mov     edx, [rbp+4Fh+var_B8]
0x180050bc9  cmp     edx, 8
0x180050bcc  jnz     short loc_180050BE0
0x180050bce  mov     ecx, [rbp+4Fh+var_B4]
0x180050bd1  add     ecx, [rdi+0Ch]
0x180050bd4  mov     [rdi+14h], ecx
0x180050bd7  mov     ecx, [rbp+4Fh+var_B0]
0x180050bda  add     ecx, [rdi+10h]
0x180050bdd  mov     [rdi+18h], ecx
0x180050be0  mov     rax, [rdi]
0x180050be3  mov     r8, r13
0x180050be6  mov     rcx, rdi
0x180050be9  mov     rax, [rax+8]
0x180050bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bf2  xor     eax, eax
0x180050bf4  lea     rcx, [rbp+4Fh+rc1]; lprc1
0x180050bf8  cmp     [rbp+4Fh+Msg.message], 202h
0x180050bff  mov     rdx, r13; lprc2
0x180050c02  setz    al
0x180050c05  mov     [rdi+48h], eax
0x180050c08  call    cs:__imp_EqualRect
0x180050c0e  test    eax, eax
0x180050c10  jz      short loc_180050C18
0x180050c12  cmp     dword ptr [rdi+48h], 0
0x180050c16  jz      short loc_180050C68
0x180050c18  test    esi, esi
0x180050c1a  jz      short loc_180050C40
0x180050c1c  mov     rax, [rdi]
0x180050c1f  lea     rdx, [rbp+4Fh+rc1]
0x180050c23  mov     r9, r12
0x180050c26  mov     dword ptr [rdi+44h], 1
0x180050c2d  mov     r8, r14
0x180050c30  mov     [rsp+0F0h+var_D0], r15
0x180050c35  mov     rcx, rdi
0x180050c38  mov     rax, [rax]
0x180050c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c40  mov     rax, [rdi]
0x180050c43  lea     rdx, [rbp+4Fh+rc1]
0x180050c47  mov     rcx, rdi
0x180050c4a  mov     rax, [rax+10h]
0x180050c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c53  cmp     [rbp+4Fh+Msg.message], 202h
0x180050c5a  mov     eax, 1
0x180050c5f  cmovnz  esi, eax
0x180050c62  cmp     dword ptr [rdi+48h], 0
0x180050c66  jnz     short loc_180050CE0
0x180050c68  mov     rdx, r13; lprc2
0x180050c6b  lea     rcx, [rbp+4Fh+rc1]; lprc1
0x180050c6f  call    cs:__imp_EqualRect
0x180050c75  test    eax, eax
0x180050c77  jnz     loc_180050B36
0x180050c7d  mov     [rdi+44h], eax
0x180050c80  mov     r9, r12
0x180050c83  mov     rax, [rdi]
0x180050c86  mov     r8, r14
0x180050c89  mov     rdx, r13
0x180050c8c  mov     [rsp+0F0h+var_D0], r15
0x180050c91  mov     rcx, rdi
0x180050c94  mov     rax, [rax]
0x180050c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c9c  jmp     loc_180050B36
0x180050ca1  cmp     [rbp+4Fh+Msg.wParam], 1Bh
0x180050ca6  jnz     loc_180050B36
0x180050cac  test    esi, esi
0x180050cae  jz      short loc_180050CD7
0x180050cb0  mov     eax, 1
0x180050cb5  mov     [rsp+0F0h+var_D0], r15
0x180050cba  mov     [rdi+48h], eax
0x180050cbd  mov     r9, r12
0x180050cc0  mov     [rdi+44h], eax
0x180050cc3  mov     r8, r14
0x180050cc6  mov     rax, [rdi]
0x180050cc9  mov     rdx, r13
0x180050ccc  mov     rcx, rdi
0x180050ccf  mov     rax, [rax]
0x180050cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050cd7  movups  xmm0, xmmword ptr [rbp+4Fh+var_58.left]
0x180050cdb  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x180050ce0  mov     rdx, [r12+8]; hDC
0x180050ce5  test    r14, r14
0x180050ce8  jz      short loc_180050CF0
0x180050cea  mov     rcx, [r14+40h]
0x180050cee  jmp     short loc_180050CF4
0x180050cf0  mov     rcx, [r15+40h]; hWnd
0x180050cf4  call    cs:__imp_ReleaseDC
0x180050cfa  call    cs:__imp_ReleaseCapture
0x180050d00  xor     ecx, ecx; int
0x180050d02  call    ?AfxUnlockTempMaps@@YAHH@Z; AfxUnlockTempMaps(int)
0x180050d07  test    esi, esi
0x180050d09  jnz     short loc_180050D14
0x180050d0b  movups  xmm0, xmmword ptr [rbp+4Fh+var_58.left]
0x180050d0f  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x180050d14  mov     rdx, r13; lprc2
0x180050d17  mov     qword ptr [rdi+44h], 0
0x180050d1f  lea     rcx, [rbp+4Fh+var_58]; lprc1
0x180050d23  call    cs:__imp_EqualRect
0x180050d29  xor     ecx, ecx
0x180050d2b  test    eax, eax
0x180050d2d  setz    cl
0x180050d30  mov     eax, ecx
0x180050d32  mov     rcx, [rbp+4Fh+var_48]
0x180050d36  xor     rcx, rsp; StackCookie
0x180050d39  call    __security_check_cookie
0x180050d3e  add     rsp, 0B8h
0x180050d45  pop     r15
0x180050d47  pop     r14
0x180050d49  pop     r13
0x180050d4b  pop     r12
0x180050d4d  pop     rdi
0x180050d4e  pop     rsi
0x180050d4f  pop     rbx
0x180050d50  pop     rbp
0x180050d51  retn
```
