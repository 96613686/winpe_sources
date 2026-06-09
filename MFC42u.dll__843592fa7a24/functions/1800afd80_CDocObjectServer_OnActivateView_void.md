# CDocObjectServer::OnActivateView(void)

- ea: `0x1800afd80`
- end: `0x1800b022c`
- name: `?OnActivateView@CDocObjectServer@@MEAAJXZ`
- size: `1196`
- prototype: `__int64 __fastcall(CDocObjectServer *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x18000ce50`
- `0x1800122f0`
- `0x180013330`
- `0x180019290`
- `0x18001a490`
- `0x18001fdf0`
- `0x180024410`
- `0x180026a40`
- `0x1800432c0`
- `0x180071bd0`
- `0x180091af0`
- `0x1800afd80`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!CopyRect` at `0x1800affc9`
- `USER32!CopyRect` at `0x1800affda`
- `USER32!CopyRect` at `0x1800affc9`
- `USER32!CopyRect` at `0x1800affda`
- `USER32!UpdateWindow` at `0x1800b012a`
- `USER32!UpdateWindow` at `0x1800b012a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDocObjectServer::OnActivateView(CDocObjectServer *this)
{
  _QWORD *v2; // rcx
  unsigned __int16 *v4; // rbx
  struct AFX_MODULE_STATE *ModuleState; // rax
  __int64 v6; // rdi
  unsigned int v7; // r14d
  struct CWnd *v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // r15
  _QWORD *v13; // r12
  COleCntrFrameWnd *v14; // rax
  COleCntrFrameWnd *v15; // rax
  struct IUnknown *Interface; // r14
  __int64 v17; // rcx
  __int64 v18; // r8
  _QWORD *v19; // rcx
  HWND v20; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR v21; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int16 *v22; // [rsp+50h] [rbp-9h] BYREF
  COleCntrFrameWnd *v23; // [rsp+58h] [rbp-1h]
  RECT rcSrc; // [rsp+60h] [rbp+7h] BYREF
  RECT v25; // [rsp+70h] [rbp+17h] BYREF

  v2 = (_QWORD *)*((_QWORD *)this + 9);
  if ( !v2[41] )
    return 0;
  v22 = (unsigned __int16 *)_afxPchNil;
  v21 = _afxPchNil;
  if ( (*(unsigned int (__fastcall **)(_QWORD *, unsigned __int16 **))(*v2 + 624LL))(v2, &v22) )
  {
    v4 = v22;
    ModuleState = AfxGetModuleState();
    AfxFormatString2((struct CString *)&v21, 0xE005u, *((const unsigned __int16 **)ModuleState + 4), v4);
    v6 = *((_QWORD *)this + 12);
    if ( v6 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*((_QWORD *)this + 12));
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v6);
      if ( !v7 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v6 + 24LL))(v6, &v20);
        v8 = CWnd::FromHandle(v20);
        v9 = (_QWORD *)*((_QWORD *)this + 9);
        v10 = v9[45];
        if ( v10 )
        {
LABEL_18:
          Interface = CCmdTarget::GetInterface(*((CCmdTarget **)this + 9), &IID_IOleInPlaceActiveObject);
          (*(void (__fastcall **)(_QWORD, struct IUnknown *, LPCWSTR))(**(_QWORD **)(v10 + 376) + 64LL))(
            *(_QWORD *)(v10 + 376),
            Interface,
            v21);
          v17 = *(_QWORD *)(v10 + 384);
          if ( v17 )
            (*(void (__fastcall **)(__int64, struct IUnknown *, LPCWSTR))(*(_QWORD *)v17 + 64LL))(v17, Interface, v21);
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 9) + 592LL))(
            *((_QWORD *)this + 9),
            *(_QWORD *)(v10 + 392),
            1);
          if ( *(_QWORD *)(v10 + 384) )
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 9) + 592LL))(
              *((_QWORD *)this + 9),
              *(_QWORD *)(v10 + 400),
              1);
          CFrameWnd::ShowOwnedWindows((CFrameWnd *)v10, 1);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 9) + 616LL))(
            *((_QWORD *)this + 9),
            0,
            *(_QWORD *)(v10 + 376),
            1);
          v18 = *(_QWORD *)(v10 + 384);
          if ( v18 )
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 9) + 616LL))(
              *((_QWORD *)this + 9),
              0,
              v18,
              0);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v10 + 376) + 80LL))(
            *(_QWORD *)(v10 + 376),
            *(_QWORD *)(v10 + 408),
            *(_QWORD *)(v10 + 440),
            *(_QWORD *)(v10 + 64));
          CWnd::ShowWindow((CWnd *)v10, 5);
          CWnd::SetFocus((CWnd *)v10);
          UpdateWindow(*(HWND *)(v10 + 64));
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 9) + 576LL))(*((_QWORD *)this + 9), 1);
          *(_DWORD *)(v10 + 336) = 1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          CString::~CString((CString *)&v21);
          CString::~CString((CString *)&v22);
          return 0;
        }
        v11 = (*(__int64 (__fastcall **)(_QWORD *, struct CWnd *))(*v9 + 600LL))(v9, v8);
        v10 = v11;
        if ( v11 )
        {
          *(_QWORD *)(*((_QWORD *)this + 9) + 360LL) = v11;
          rcSrc = 0;
          v25 = 0;
          v12 = (_QWORD *)(v11 + 384);
          v13 = (_QWORD *)(v11 + 376);
          v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, RECT *, RECT *, __int64))(*(_QWORD *)v6 + 64LL))(
                 v6,
                 v11 + 376,
                 v11 + 384,
                 &rcSrc,
                 &v25,
                 v11 + 344);
          if ( !v7 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6);
            if ( !v7 )
            {
              if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 536LL))(v10) )
              {
                (*(void (__fastcall **)(_QWORD, HWND *))(*(_QWORD *)*v13 + 24LL))(*v13, &v20);
                v14 = (COleCntrFrameWnd *)operator new(0x158u);
                v23 = v14;
                if ( v14 )
                  v14 = COleCntrFrameWnd::COleCntrFrameWnd(v14, (struct COleIPFrameWnd *)v10);
                *(_QWORD *)(v10 + 392) = v14;
                CWnd::Attach(v14, v20);
                if ( *v12 )
                {
                  (*(void (__fastcall **)(_QWORD, HWND *))(*(_QWORD *)*v12 + 24LL))(*v12, &v20);
                  v15 = (COleCntrFrameWnd *)operator new(0x158u);
                  v23 = v15;
                  if ( v15 )
                    v15 = COleCntrFrameWnd::COleCntrFrameWnd(v15, (struct COleIPFrameWnd *)v10);
                  *(_QWORD *)(v10 + 400) = v15;
                  CWnd::Attach(v15, v20);
                }
                CopyRect((LPRECT)(v10 + 448), &rcSrc);
                CopyRect((LPRECT)(v10 + 464), &v25);
                if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v10 + 504LL))(
                       v10,
                       *(_QWORD *)(v10 + 392),
                       *(_QWORD *)(v10 + 400)) )
                {
                  goto LABEL_18;
                }
              }
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 80LL))(v6, 0);
            }
          }
          v19 = (_QWORD *)*((_QWORD *)this + 9);
          if ( !v19[45] )
            goto LABEL_29;
          (*(void (__fastcall **)(_QWORD *, __int64))(*v19 + 608LL))(v19, v10);
          *(_QWORD *)(*((_QWORD *)this + 9) + 360LL) = 0;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 88LL))(v6);
      }
LABEL_29:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      CString::~CString((CString *)&v21);
      CString::~CString((CString *)&v22);
      return v7;
    }
  }
  CString::~CString((CString *)&v21);
  CString::~CString((CString *)&v22);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800afd80  mov     [rsp-8+arg_8], rbx
0x1800afd85  mov     [rsp-8+arg_10], rsi
0x1800afd8a  push    rbp
0x1800afd8b  push    rdi
0x1800afd8c  push    r12
0x1800afd8e  push    r14
0x1800afd90  push    r15
0x1800afd92  lea     rbp, [rsp-37h]
0x1800afd97  sub     rsp, 90h
0x1800afd9e  mov     rax, cs:__security_cookie
0x1800afda5  xor     rax, rsp
0x1800afda8  mov     [rbp+57h+var_30], rax
0x1800afdac  mov     rsi, rcx
0x1800afdaf  mov     rcx, [rcx+48h]
0x1800afdb3  cmp     qword ptr [rcx+148h], 0
0x1800afdbb  jnz     short loc_1800AFDC4
0x1800afdbd  xor     eax, eax
0x1800afdbf  jmp     loc_1800B0204
0x1800afdc4  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800afdcb  mov     [rbp+57h+var_60], rax
0x1800afdcf  mov     [rbp+57h+var_68], rax
0x1800afdd3  mov     rax, [rcx]
0x1800afdd6  lea     rdx, [rbp+57h+var_60]
0x1800afdda  mov     rax, [rax+270h]
0x1800afde1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afde6  test    eax, eax
0x1800afde8  jz      loc_1800B01EC
0x1800afdee  mov     rbx, [rbp+57h+var_60]
0x1800afdf2  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1800afdf7  mov     r9, rbx; unsigned __int16 *
0x1800afdfa  mov     r8, [rax+20h]; unsigned __int16 *
0x1800afdfe  mov     edx, 0E005h; unsigned int
0x1800afe03  lea     rcx, [rbp+57h+var_68]; struct CString *
0x1800afe07  call    ?AfxFormatString2@@YAXAEAVCString@@IPEBG1@Z; AfxFormatString2(CString &,uint,ushort const *,ushort const *)
0x1800afe0c  mov     rdi, [rsi+60h]
0x1800afe10  test    rdi, rdi
0x1800afe13  jz      loc_1800B01EC
0x1800afe19  mov     rax, [rdi]
0x1800afe1c  mov     rcx, rdi
0x1800afe1f  mov     rax, [rax+8]
0x1800afe23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe28  mov     rax, [rdi]
0x1800afe2b  mov     rcx, rdi
0x1800afe2e  mov     rax, [rax+30h]
0x1800afe32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe37  mov     r14d, eax
0x1800afe3a  test    eax, eax
0x1800afe3c  jnz     loc_1800B01C4
0x1800afe42  mov     [rbp+57h+var_70], 0
0x1800afe4a  mov     rcx, [rdi]
0x1800afe4d  mov     rax, [rcx+18h]
0x1800afe51  lea     rdx, [rbp+57h+var_70]
0x1800afe55  mov     rcx, rdi
0x1800afe58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe5d  mov     rcx, [rbp+57h+var_70]; HWND
0x1800afe61  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1800afe66  mov     rdx, rax
0x1800afe69  mov     rcx, [rsi+48h]
0x1800afe6d  mov     rbx, [rcx+168h]
0x1800afe74  test    rbx, rbx
0x1800afe77  jnz     loc_1800B0008
0x1800afe7d  mov     rax, [rcx]
0x1800afe80  mov     rax, [rax+258h]
0x1800afe87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe8c  mov     rbx, rax
0x1800afe8f  test    rax, rax
0x1800afe92  jz      loc_1800B01B5
0x1800afe98  mov     rax, [rsi+48h]
0x1800afe9c  mov     [rax+168h], rbx
0x1800afea3  xorps   xmm0, xmm0
0x1800afea6  movups  xmmword ptr [rbp+57h+rcSrc.left], xmm0
0x1800afeaa  xorps   xmm1, xmm1
0x1800afead  movups  xmmword ptr [rbp+57h+var_40.left], xmm1
0x1800afeb1  lea     r15, [rbx+180h]
0x1800afeb8  lea     r12, [rbx+178h]
0x1800afebf  mov     rax, [rdi]
0x1800afec2  lea     rcx, [rbx+158h]
0x1800afec9  mov     [rsp+0B0h+var_88], rcx
0x1800afece  lea     rcx, [rbp+57h+var_40]
0x1800afed2  mov     [rsp+0B0h+var_90], rcx
0x1800afed7  lea     r9, [rbp+57h+rcSrc]
0x1800afedb  mov     r8, r15
0x1800afede  mov     rdx, r12
0x1800afee1  mov     rcx, rdi
0x1800afee4  mov     rax, [rax+40h]
0x1800afee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afeed  mov     r14d, eax
0x1800afef0  test    eax, eax
0x1800afef2  jnz     loc_1800B0186
0x1800afef8  mov     rax, [rdi]
0x1800afefb  mov     rcx, rdi
0x1800afefe  mov     rax, [rax+38h]
0x1800aff02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff07  mov     r14d, eax
0x1800aff0a  test    eax, eax
0x1800aff0c  jnz     loc_1800B0186
0x1800aff12  mov     rax, [rbx]
0x1800aff15  mov     rcx, rbx
0x1800aff18  mov     rax, [rax+218h]
0x1800aff1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff24  test    eax, eax
0x1800aff26  jz      loc_1800B0175
0x1800aff2c  mov     rcx, [r12]
0x1800aff30  mov     rax, [rcx]
0x1800aff33  lea     rdx, [rbp+57h+var_70]
0x1800aff37  mov     rax, [rax+18h]
0x1800aff3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff40  mov     r12d, 158h
0x1800aff46  mov     ecx, r12d; Size
0x1800aff49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800aff4e  mov     [rbp+57h+var_58], rax
0x1800aff52  test    rax, rax
0x1800aff55  jz      short loc_1800AFF63
0x1800aff57  mov     rdx, rbx; struct COleIPFrameWnd *
0x1800aff5a  mov     rcx, rax; this
0x1800aff5d  call    ??0COleCntrFrameWnd@@QEAA@PEAVCOleIPFrameWnd@@@Z; COleCntrFrameWnd::COleCntrFrameWnd(COleIPFrameWnd *)
0x1800aff62  nop
0x1800aff63  mov     [rbx+188h], rax
0x1800aff6a  mov     rdx, [rbp+57h+var_70]; HWND
0x1800aff6e  mov     rcx, rax; this
0x1800aff71  call    ?Attach@CWnd@@QEAAHPEAUHWND__@@@Z; CWnd::Attach(HWND__ *)
0x1800aff76  mov     rcx, [r15]
0x1800aff79  test    rcx, rcx
0x1800aff7c  jz      short loc_1800AFFBE
0x1800aff7e  mov     rax, [rcx]
0x1800aff81  lea     rdx, [rbp+57h+var_70]
0x1800aff85  mov     rax, [rax+18h]
0x1800aff89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff8e  mov     rcx, r12; Size
0x1800aff91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800aff96  mov     [rbp+57h+var_58], rax
0x1800aff9a  test    rax, rax
0x1800aff9d  jz      short loc_1800AFFAB
0x1800aff9f  mov     rdx, rbx; struct COleIPFrameWnd *
0x1800affa2  mov     rcx, rax; this
0x1800affa5  call    ??0COleCntrFrameWnd@@QEAA@PEAVCOleIPFrameWnd@@@Z; COleCntrFrameWnd::COleCntrFrameWnd(COleIPFrameWnd *)
0x1800affaa  nop
0x1800affab  mov     [rbx+190h], rax
0x1800affb2  mov     rdx, [rbp+57h+var_70]; HWND
0x1800affb6  mov     rcx, rax; this
0x1800affb9  call    ?Attach@CWnd@@QEAAHPEAUHWND__@@@Z; CWnd::Attach(HWND__ *)
0x1800affbe  lea     rcx, [rbx+1C0h]; lprcDst
0x1800affc5  lea     rdx, [rbp+57h+rcSrc]; lprcSrc
0x1800affc9  call    cs:__imp_CopyRect
0x1800affcf  lea     rcx, [rbx+1D0h]; lprcDst
0x1800affd6  lea     rdx, [rbp+57h+var_40]; lprcSrc
0x1800affda  call    cs:__imp_CopyRect
0x1800affe0  mov     rax, [rbx]
0x1800affe3  mov     r8, [rbx+190h]
0x1800affea  mov     rdx, [rbx+188h]
0x1800afff1  mov     rcx, rbx
0x1800afff4  mov     rax, [rax+1F8h]
0x1800afffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0000  test    eax, eax
0x1800b0002  jz      loc_1800B0175
0x1800b0008  lea     rdx, IID_IOleInPlaceActiveObject; void *
0x1800b000f  mov     rcx, [rsi+48h]; this
0x1800b0013  call    ?GetInterface@CCmdTarget@@QEAAPEAUIUnknown@@PEBX@Z; CCmdTarget::GetInterface(void const *)
0x1800b0018  mov     r14, rax
0x1800b001b  mov     rcx, [rbx+178h]
0x1800b0022  mov     rdx, [rcx]
0x1800b0025  mov     rax, [rdx+40h]
0x1800b0029  mov     r8, [rbp+57h+var_68]
0x1800b002d  mov     rdx, r14
0x1800b0030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0035  mov     rcx, [rbx+180h]
0x1800b003c  test    rcx, rcx
0x1800b003f  jz      short loc_1800B0054
0x1800b0041  mov     rax, [rcx]
0x1800b0044  mov     r8, [rbp+57h+var_68]
0x1800b0048  mov     rdx, r14
0x1800b004b  mov     rax, [rax+40h]
0x1800b004f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0054  mov     rcx, [rsi+48h]
0x1800b0058  mov     rax, [rcx]
0x1800b005b  mov     r14d, 1
0x1800b0061  mov     r8d, r14d
0x1800b0064  mov     rdx, [rbx+188h]
0x1800b006b  mov     rax, [rax+250h]
0x1800b0072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0077  cmp     qword ptr [rbx+180h], 0
0x1800b007f  jz      short loc_1800B009E
0x1800b0081  mov     rcx, [rsi+48h]
0x1800b0085  mov     rax, [rcx]
0x1800b0088  mov     r8d, r14d
0x1800b008b  mov     rdx, [rbx+190h]
0x1800b0092  mov     rax, [rax+250h]
0x1800b0099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b009e  mov     edx, r14d; int
0x1800b00a1  mov     rcx, rbx; this
0x1800b00a4  call    ?ShowOwnedWindows@CFrameWnd@@QEAAXH@Z; CFrameWnd::ShowOwnedWindows(int)
0x1800b00a9  mov     rcx, [rsi+48h]
0x1800b00ad  mov     rax, [rcx]
0x1800b00b0  mov     r9d, r14d
0x1800b00b3  mov     r8, [rbx+178h]
0x1800b00ba  xor     edx, edx
0x1800b00bc  mov     rax, [rax+268h]
0x1800b00c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b00c8  mov     r8, [rbx+180h]
0x1800b00cf  test    r8, r8
0x1800b00d2  jz      short loc_1800B00EC
0x1800b00d4  mov     rcx, [rsi+48h]
0x1800b00d8  mov     rax, [rcx]
0x1800b00db  xor     r9d, r9d
0x1800b00de  xor     edx, edx
0x1800b00e0  mov     rax, [rax+268h]
0x1800b00e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b00ec  mov     rcx, [rbx+178h]
0x1800b00f3  mov     rax, [rcx]
0x1800b00f6  mov     r9, [rbx+40h]
0x1800b00fa  mov     r8, [rbx+1B8h]
0x1800b0101  mov     rdx, [rbx+198h]
0x1800b0108  mov     rax, [rax+50h]
0x1800b010c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0111  mov     edx, 5; int
0x1800b0116  mov     rcx, rbx; this
0x1800b0119  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x1800b011e  mov     rcx, rbx; this
0x1800b0121  call    ?SetFocus@CWnd@@QEAAPEAV1@XZ; CWnd::SetFocus(void)
0x1800b0126  mov     rcx, [rbx+40h]; hWnd
0x1800b012a  call    cs:__imp_UpdateWindow
0x1800b0130  mov     rcx, [rsi+48h]
0x1800b0134  mov     rax, [rcx]
0x1800b0137  mov     edx, r14d
0x1800b013a  mov     rax, [rax+240h]
0x1800b0141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0146  mov     [rbx+150h], r14d
0x1800b014d  mov     rax, [rdi]
0x1800b0150  mov     rcx, rdi
0x1800b0153  mov     rax, [rax+10h]
0x1800b0157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b015c  nop
0x1800b015d  lea     rcx, [rbp+57h+var_68]; this
0x1800b0161  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800b0166  nop
0x1800b0167  lea     rcx, [rbp+57h+var_60]; this
0x1800b016b  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800b0170  jmp     loc_1800AFDBD
0x1800b0175  mov     rax, [rdi]
0x1800b0178  xor     edx, edx
0x1800b017a  mov     rcx, rdi
0x1800b017d  mov     rax, [rax+50h]
0x1800b0181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0186  mov     rcx, [rsi+48h]
0x1800b018a  cmp     qword ptr [rcx+168h], 0
0x1800b0192  jz      short loc_1800B01C4
0x1800b0194  mov     rax, [rcx]
0x1800b0197  mov     rdx, rbx
0x1800b019a  mov     rax, [rax+260h]
0x1800b01a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b01a6  mov     rax, [rsi+48h]
0x1800b01aa  mov     qword ptr [rax+168h], 0
0x1800b01b5  mov     rax, [rdi]
0x1800b01b8  mov     rcx, rdi
0x1800b01bb  mov     rax, [rax+58h]
0x1800b01bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b01c4  mov     rax, [rdi]
0x1800b01c7  mov     rcx, rdi
0x1800b01ca  mov     rax, [rax+10h]
0x1800b01ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b01d3  nop
0x1800b01d4  lea     rcx, [rbp+57h+var_68]; this
0x1800b01d8  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800b01dd  nop
0x1800b01de  lea     rcx, [rbp+57h+var_60]; this
0x1800b01e2  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800b01e7  mov     eax, r14d
0x1800b01ea  jmp     short loc_1800B0204
0x1800b01ec  lea     rcx, [rbp+57h+var_68]; this
0x1800b01f0  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800b01f5  nop
0x1800b01f6  lea     rcx, [rbp+57h+var_60]; this
0x1800b01fa  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800b01ff  mov     eax, 80004005h
0x1800b0204  mov     rcx, [rbp+57h+var_30]
0x1800b0208  xor     rcx, rsp; StackCookie
0x1800b020b  call    __security_check_cookie
0x1800b0210  lea     r11, [rsp+0B0h+var_20]
0x1800b0218  mov     rbx, [r11+38h]
0x1800b021c  mov     rsi, [r11+40h]
0x1800b0220  mov     rsp, r11
0x1800b0223  pop     r15
0x1800b0225  pop     r14
0x1800b0227  pop     r12
0x1800b0229  pop     rdi
0x1800b022a  pop     rbp
0x1800b022b  retn
```
