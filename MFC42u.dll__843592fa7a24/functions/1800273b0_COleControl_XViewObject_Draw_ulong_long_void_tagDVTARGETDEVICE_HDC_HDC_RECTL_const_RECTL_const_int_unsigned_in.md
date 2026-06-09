# COleControl::XViewObject::Draw(ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,int (*)(unsigned __int64),unsigned __int64)

- ea: `0x1800273b0`
- end: `0x18002762a`
- name: `?Draw@XViewObject@COleControl@@UEAAJKJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBU_RECTL@@3P6AH_K@Z4@Z`
- size: `634`
- prototype: `__int64 __fastcall(COleControl::XViewObject *__hidden this, unsigned int, int, void *, struct tagDVTARGETDEVICE *, HDC, HDC hdc, const struct _RECTL *, const struct _RECTL *, int (*)(unsigned __int64), unsigned __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting`

## callees

- `0x18000a7d0`
- `0x18000e1a0`
- `0x180010c40`
- `0x180011480`
- `0x180012eb0`
- `0x1800166a0`
- `0x1800273b0`
- `0x18002b9a0`
- `0x18004f2a0`
- `0x18004f790`
- `0x18009424c`
- `0x1800b5bf0`
- `0x1800b6f90`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!CopyRect` at `0x18002744d`
- `USER32!CopyRect` at `0x18002744d`
- `USER32!SetRect` at `0x180027475`
- `USER32!SetRect` at `0x180027475`
- `GDI32!GetDeviceCaps` at `0x180027545`
- `GDI32!GetDeviceCaps` at `0x180027545`
- `GDI32!DeleteDC` at `0x1800275c5`
- `GDI32!DeleteDC` at `0x1800275c5`

## pseudocode

```c
__int64 __fastcall COleControl::XViewObject::Draw(
        COleControl::XViewObject *this,
        unsigned int a2,
        unsigned int a3,
        _DWORD *a4,
        struct tagDVTARGETDEVICE *a5,
        HDC a6,
        HDC hdc,
        const struct _RECTL *a8,
        const struct _RECTL *a9,
        int (*a10)(unsigned __int64),
        unsigned __int64 a11)
{
  COleControl *v11; // rdi
  __int64 v13; // rbx
  __int64 Data; // rax
  __int64 v15; // rcx
  _DWORD *v16; // rbx
  unsigned int v17; // r14d
  struct AFX_MODULE_THREAD_STATE *ModuleThreadState; // rax
  void *v19; // rcx
  void *DefHandler; // rax
  HDC DC; // rsi
  struct CDC *v22; // rax
  void **v26; // [rsp+70h] [rbp-61h] BYREF
  __int128 v27; // [rsp+78h] [rbp-59h]
  int v28; // [rsp+88h] [rbp-49h]
  int (*v29)(unsigned __int64); // [rsp+90h] [rbp-41h]
  const struct _RECTL *v30; // [rsp+98h] [rbp-39h]
  __int64 v31; // [rsp+A0h] [rbp-31h]
  __int64 v32; // [rsp+A8h] [rbp-29h]
  struct tagRECT rcDst; // [rsp+B0h] [rbp-21h] BYREF

  v11 = (COleControl::XViewObject *)((char *)this - 520);
  v13 = *((_QWORD *)this - 58);
  v30 = a9;
  v29 = a10;
  Data = CThreadLocal<_AFX_THREAD_STATE>::GetData();
  v31 = Data;
  v15 = *(_QWORD *)(Data + 8);
  *(_QWORD *)(Data + 8) = v13;
  v16 = (_DWORD *)((char *)v11 + 248);
  v32 = v15;
  if ( a8 )
  {
    SetRect(&rcDst, a8->left, a8->top, a8->right, a8->bottom);
  }
  else
  {
    if ( (*v16 & 0x400000) == 0 )
    {
      v17 = -2147024809;
      goto LABEL_22;
    }
    CopyRect(&rcDst, (const RECT *)((char *)v11 + 184));
  }
  v17 = 0;
  if ( a4 && ((*(__int64 (__fastcall **)(COleControl *))(*(_QWORD *)v11 + 800LL))(v11) & 0x20) != 0 )
    *v16 ^= (*v16 ^ (a4[1] << 24)) & 0x1000000;
  ModuleThreadState = AfxGetModuleThreadState();
  ++*((_DWORD *)ModuleThreadState + 8);
  if ( a2 == 1 )
  {
    if ( GetDeviceCaps(hdc, 2) == 5 )
    {
      if ( a6 )
        DC = a6;
      else
        DC = _AfxOleCreateDC(a5);
      v28 = 0;
      v26 = &CMetaFileDC::`vftable';
      v27 = 0;
      CDC::Attach((CDC *)&v26, hdc);
      CMetaFileDC::SetAttribDC((CMetaFileDC *)&v26, DC);
      COleControl::DrawMetafile(v11, (struct CDC *)&v26, (struct CRect *)&rcDst);
      CMetaFileDC::SetAttribDC((CMetaFileDC *)&v26, 0);
      CDC::Detach((CDC *)&v26);
      if ( !a6 )
        DeleteDC(DC);
      CMetaFileDC::~CMetaFileDC((CMetaFileDC *)&v26);
    }
    else
    {
      v22 = CDC::FromHandle(hdc);
      COleControl::DrawContent(v11, v22, (struct CRect *)&rcDst);
    }
  }
  else
  {
    v19 = (void *)*((_QWORD *)v11 + 44);
    if ( v19
      || (DefHandler = COleControl::QueryDefHandler(v11, &IID_IViewObject),
          *((_QWORD *)v11 + 44) = DefHandler,
          (v19 = DefHandler) != 0) )
    {
      v17 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, _DWORD *, struct tagDVTARGETDEVICE *, HDC, HDC, const struct _RECTL *, const struct _RECTL *, int (*)(unsigned __int64), unsigned __int64))(*(_QWORD *)v19 + 24LL))(
              v19,
              a2,
              a3,
              a4,
              a5,
              a6,
              hdc,
              a8,
              v30,
              v29,
              a11);
    }
  }
  AfxUnlockTempMaps(1);
  *v16 &= ~0x1000000u;
  Data = v31;
  v15 = v32;
LABEL_22:
  *(_QWORD *)(Data + 8) = v15;
  return v17;
}

```

## disassembly

```asm
0x1800273b0  push    rbp
0x1800273b2  push    rbx
0x1800273b3  push    rsi
0x1800273b4  push    rdi
0x1800273b5  push    r12
0x1800273b7  push    r13
0x1800273b9  push    r14
0x1800273bb  push    r15
0x1800273bd  lea     rbp, [rsp-7]
0x1800273c2  sub     rsp, 0D8h
0x1800273c9  mov     rax, cs:__security_cookie
0x1800273d0  xor     rax, rsp
0x1800273d3  mov     [rbp+3Fh+var_50], rax
0x1800273d7  mov     rax, [rbp+3Fh+arg_20]
0x1800273db  lea     rdi, [rcx-208h]
0x1800273e2  mov     rsi, [rbp+3Fh+arg_38]
0x1800273e9  mov     r13, r9
0x1800273ec  mov     r15, [rbp+3Fh+arg_28]
0x1800273f0  mov     r12, [rbp+3Fh+hdc]
0x1800273f4  mov     rbx, [rdi+38h]
0x1800273f8  mov     [rbp+3Fh+var_A8], rax
0x1800273fc  mov     rax, [rbp+3Fh+arg_40]
0x180027403  mov     [rbp+3Fh+var_78], rax
0x180027407  mov     rax, [rbp+3Fh+arg_48]
0x18002740e  mov     [rbp+3Fh+var_80], rax
0x180027412  mov     [rbp+3Fh+var_AC], r8d
0x180027416  mov     [rbp+3Fh+var_B0], edx
0x180027419  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x18002741e  mov     [rbp+3Fh+var_70], rax
0x180027422  mov     rcx, [rax+8]
0x180027426  mov     [rax+8], rbx
0x18002742a  lea     rbx, [rdi+0F8h]
0x180027431  mov     [rbp+3Fh+var_68], rcx
0x180027435  test    rsi, rsi
0x180027438  jnz     short loc_180027460
0x18002743a  test    dword ptr [rbx], 400000h
0x180027440  jz      short loc_180027455
0x180027442  lea     rdx, [rdi+0B8h]; lprcSrc
0x180027449  lea     rcx, [rbp+3Fh+rcDst]; lprcDst
0x18002744d  call    cs:__imp_CopyRect
0x180027453  jmp     short loc_18002747B
0x180027455  mov     r14d, 80070057h
0x18002745b  jmp     loc_180027603
0x180027460  mov     eax, [rsi+0Ch]
0x180027463  lea     rcx, [rbp+3Fh+rcDst]; lprc
0x180027467  mov     r9d, [rsi+8]; xRight
0x18002746b  mov     r8d, [rsi+4]; yTop
0x18002746f  mov     edx, [rsi]; xLeft
0x180027471  mov     [rsp+110h+yBottom], eax; yBottom
0x180027475  call    cs:__imp_SetRect
0x18002747b  xor     r14d, r14d
0x18002747e  test    r13, r13
0x180027481  jz      short loc_1800274A9
0x180027483  mov     rax, [rdi]
0x180027486  mov     rcx, rdi
0x180027489  mov     rax, [rax+320h]
0x180027490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027495  test    al, 20h
0x180027497  jz      short loc_1800274A9
0x180027499  mov     eax, [r13+4]
0x18002749d  shl     eax, 18h
0x1800274a0  xor     eax, [rbx]
0x1800274a2  and     eax, 1000000h
0x1800274a7  xor     [rbx], eax
0x1800274a9  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1800274ae  inc     dword ptr [rax+20h]
0x1800274b1  cmp     [rbp+3Fh+var_B0], 1
0x1800274b5  jz      loc_18002753D
0x1800274bb  mov     rcx, [rdi+160h]
0x1800274c2  test    rcx, rcx
0x1800274c5  jnz     short loc_1800274E9
0x1800274c7  lea     rdx, IID_IViewObject; struct _GUID *
0x1800274ce  mov     rcx, rdi; this
0x1800274d1  call    ?QueryDefHandler@COleControl@@IEAAPEAXAEBU_GUID@@@Z; COleControl::QueryDefHandler(_GUID const &)
0x1800274d6  mov     [rdi+160h], rax
0x1800274dd  mov     rcx, rax
0x1800274e0  test    rax, rax
0x1800274e3  jz      loc_1800275ED
0x1800274e9  mov     r10, [rbp+3Fh+arg_50]
0x1800274f0  mov     rdx, [rbp+3Fh+var_80]
0x1800274f4  mov     rax, [rcx]
0x1800274f7  mov     r9, [rbp+3Fh+var_A8]
0x1800274fb  mov     r8d, [rbp+3Fh+var_AC]
0x1800274ff  mov     [rsp+110h+var_C0], r10
0x180027504  mov     rax, [rax+18h]
0x180027508  mov     [rsp+110h+var_C8], rdx
0x18002750d  mov     rdx, [rbp+3Fh+var_78]
0x180027511  mov     [rsp+110h+var_D0], rdx
0x180027516  mov     edx, [rbp+3Fh+var_B0]
0x180027519  mov     [rsp+110h+var_D8], rsi
0x18002751e  mov     [rsp+110h+var_E0], r12
0x180027523  mov     [rsp+110h+var_E8], r15
0x180027528  mov     qword ptr [rsp+110h+yBottom], r9
0x18002752d  mov     r9, r13
0x180027530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027535  mov     r14d, eax
0x180027538  jmp     loc_1800275ED
0x18002753d  mov     edx, 2; index
0x180027542  mov     rcx, r12; hdc
0x180027545  call    cs:__imp_GetDeviceCaps
0x18002754b  cmp     eax, 5
0x18002754e  jnz     loc_1800275D6
0x180027554  test    r15, r15
0x180027557  jnz     short loc_180027567
0x180027559  mov     rcx, [rbp+3Fh+var_A8]; struct tagDVTARGETDEVICE *
0x18002755d  call    ?_AfxOleCreateDC@@YAPEAUHDC__@@PEAUtagDVTARGETDEVICE@@@Z; _AfxOleCreateDC(tagDVTARGETDEVICE *)
0x180027562  mov     rsi, rax
0x180027565  jmp     short loc_18002756A
0x180027567  mov     rsi, r15
0x18002756a  xorps   xmm0, xmm0
0x18002756d  mov     [rbp+3Fh+var_88], r14d
0x180027571  lea     rax, ??_7CMetaFileDC@@6B@; const CMetaFileDC::`vftable'
0x180027578  mov     rdx, r12; HDC
0x18002757b  lea     rcx, [rbp+3Fh+var_A0]; this
0x18002757f  mov     [rbp+3Fh+var_A0], rax
0x180027583  movdqu  [rbp+3Fh+var_98], xmm0
0x180027588  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18002758d  mov     rdx, rsi; HDC
0x180027590  lea     rcx, [rbp+3Fh+var_A0]; this
0x180027594  call    ?SetAttribDC@CMetaFileDC@@UEAAXPEAUHDC__@@@Z; CMetaFileDC::SetAttribDC(HDC__ *)
0x180027599  lea     r8, [rbp+3Fh+rcDst]; struct CRect *
0x18002759d  mov     rcx, rdi; this
0x1800275a0  lea     rdx, [rbp+3Fh+var_A0]; struct CDC *
0x1800275a4  call    ?DrawMetafile@COleControl@@IEAAXPEAVCDC@@AEAVCRect@@@Z; COleControl::DrawMetafile(CDC *,CRect &)
0x1800275a9  xor     edx, edx; HDC
0x1800275ab  lea     rcx, [rbp+3Fh+var_A0]; this
0x1800275af  call    ?SetAttribDC@CMetaFileDC@@UEAAXPEAUHDC__@@@Z; CMetaFileDC::SetAttribDC(HDC__ *)
0x1800275b4  lea     rcx, [rbp+3Fh+var_A0]; this
0x1800275b8  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1800275bd  test    r15, r15
0x1800275c0  jnz     short loc_1800275CB
0x1800275c2  mov     rcx, rsi; hdc
0x1800275c5  call    cs:__imp_DeleteDC
0x1800275cb  lea     rcx, [rbp+3Fh+var_A0]; this
0x1800275cf  call    ??1CMetaFileDC@@UEAA@XZ; CMetaFileDC::~CMetaFileDC(void)
0x1800275d4  jmp     short loc_1800275ED
0x1800275d6  mov     rcx, r12; HDC
0x1800275d9  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x1800275de  lea     r8, [rbp+3Fh+rcDst]; struct CRect *
0x1800275e2  mov     rdx, rax; struct CDC *
0x1800275e5  mov     rcx, rdi; this
0x1800275e8  call    ?DrawContent@COleControl@@IEAAXPEAVCDC@@AEAVCRect@@@Z; COleControl::DrawContent(CDC *,CRect &)
0x1800275ed  mov     ecx, 1; int
0x1800275f2  call    ?AfxUnlockTempMaps@@YAHH@Z; AfxUnlockTempMaps(int)
0x1800275f7  btr     dword ptr [rbx], 18h
0x1800275fb  mov     rax, [rbp+3Fh+var_70]
0x1800275ff  mov     rcx, [rbp+3Fh+var_68]
0x180027603  mov     [rax+8], rcx
0x180027607  mov     eax, r14d
0x18002760a  mov     rcx, [rbp+3Fh+var_50]
0x18002760e  xor     rcx, rsp; StackCookie
0x180027611  call    __security_check_cookie
0x180027616  add     rsp, 0D8h
0x18002761d  pop     r15
0x18002761f  pop     r14
0x180027621  pop     r13
0x180027623  pop     r12
0x180027625  pop     rdi
0x180027626  pop     rsi
0x180027627  pop     rbx
0x180027628  pop     rbp
0x180027629  retn
```
