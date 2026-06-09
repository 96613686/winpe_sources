# COleControl::CreateControlWindow(HWND__ *,CRect const &,tagRECT const *)

- ea: `0x1800b5710`
- end: `0x1800b59fc`
- name: `?CreateControlWindow@COleControl@@MEAAHPEAUHWND__@@AEBVCRect@@PEBUtagRECT@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(COleControl *__hidden this, HWND, const struct CRect *, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180008930`
- `0x1800092d0`
- `0x18000ce50`
- `0x1800b5400`
- `0x1800b5710`
- `0x1800c4a90`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!SetWindowPos` at `0x1800b58b8`
- `USER32!SetWindowPos` at `0x1800b59b3`
- `USER32!SetWindowPos` at `0x1800b58b8`
- `USER32!SetWindowPos` at `0x1800b59b3`
- `USER32!GetParent` at `0x1800b5971`
- `USER32!GetParent` at `0x1800b5971`
- `USER32!CopyRect` at `0x1800b585e`
- `USER32!CopyRect` at `0x1800b585e`
- `USER32!SetParent` at `0x1800b588d`
- `USER32!SetParent` at `0x1800b588d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall COleControl::CreateControlWindow(
        COleControl *this,
        HWND a2,
        const RECT *a3,
        const struct tagRECT *a4)
{
  int v8; // ecx
  DWORD v9; // r15d
  int v10; // r12d
  _DWORD *v11; // rsi
  __int64 v12; // rax
  CReflectorWnd *v13; // rax
  CReflectorWnd *v14; // rsi
  const RECT *v15; // rdx
  HWND v16; // rcx
  __int64 v17; // rax
  HWND v18; // rdx
  COleControl *v19; // rsi
  struct tagRECT rcDst; // [rsp+60h] [rbp-68h] BYREF

  if ( *((_QWORD *)this + 8) )
  {
    v19 = this;
    if ( *((_QWORD *)this + 29) )
      v19 = (COleControl *)*((_QWORD *)this + 29);
    if ( GetParent(*((HWND *)v19 + 8)) != a2 )
      (*(void (__fastcall **)(COleControl *, _QWORD, HWND))(*(_QWORD *)this + 792LL))(this, *((_QWORD *)v19 + 8), a2);
    SetWindowPos(*((HWND *)v19 + 8), 0, 0, 0, 0, 0, 0x57u);
    (*(void (__fastcall **)(COleControl *, const RECT *, const struct tagRECT *))(*(_QWORD *)this + 472LL))(
      this,
      a3,
      a4);
  }
  else
  {
    v8 = *((_WORD *)this + 153) != 0 ? 1451229184 : 1442840576;
    v9 = v8 | 0x8000000;
    if ( *((_DWORD *)this + 77) )
      v9 = v8;
    v10 = *((_WORD *)this + 152) != 0 ? 0x200 : 0;
    v11 = (_DWORD *)((char *)this + 248);
    if ( (!(*(unsigned int (__fastcall **)(COleControl *))(*(_QWORD *)this + 784LL))(this) || (*v11 & 0x100000) != 0)
      && (*v11 & 0x80000) != 0 )
    {
      AfxEndDeferRegisterClass(32);
      CWnd::CreateEx(
        this,
        v10 + 4,
        L"AfxOleControl42u",
        *((const unsigned __int16 **)this + 33),
        v9,
        a3->left,
        a3->top,
        a3->right - a3->left,
        a3->bottom - a3->top,
        a2,
        0,
        0);
    }
    else
    {
      v12 = *((_QWORD *)this + 29);
      if ( v12 )
      {
        v16 = *(HWND *)(v12 + 64);
        if ( v16 )
        {
          SetParent(v16, a2);
          SetWindowPos(*(HWND *)(*((_QWORD *)this + 29) + 64LL), 0, 0, 0, 0, 0, 0x57u);
        }
      }
      else
      {
        v13 = (CReflectorWnd *)operator new(0x88u);
        *(_QWORD *)&rcDst.left = v13;
        if ( v13 )
          v14 = CReflectorWnd::CReflectorWnd(v13);
        else
          v14 = 0;
        *((_QWORD *)this + 29) = v14;
        v15 = a3;
        if ( a4 )
          v15 = a4;
        CopyRect(&rcDst, v15);
        if ( !(unsigned int)CReflectorWnd::Create(v14, (const struct CRect *)&rcDst, a2) )
          *((_QWORD *)this + 29) = 0;
      }
      v17 = *((_QWORD *)this + 29);
      if ( v17 )
      {
        v18 = *(HWND *)(v17 + 64);
        if ( v18 )
        {
          CWnd::CreateEx(
            this,
            v10 + 4,
            0,
            *((const unsigned __int16 **)this + 33),
            v9,
            *((_DWORD *)this + 54),
            *((_DWORD *)this + 55),
            a3->right - a3->left,
            a3->bottom - a3->top,
            v18,
            0,
            0);
          if ( !*((_QWORD *)this + 8) )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 29) + 192LL))(*((_QWORD *)this + 29));
            *((_QWORD *)this + 29) = 0;
          }
        }
      }
    }
    (*(void (__fastcall **)(COleControl *))(*(_QWORD *)this + 560LL))(this);
  }
  return *((_QWORD *)this + 8) != 0;
}

```

## disassembly

```asm
0x1800b5710  push    rbx
0x1800b5712  push    rbp
0x1800b5713  push    rsi
0x1800b5714  push    rdi
0x1800b5715  push    r12
0x1800b5717  push    r13
0x1800b5719  push    r14
0x1800b571b  push    r15
0x1800b571d  sub     rsp, 88h
0x1800b5724  mov     rax, cs:__security_cookie
0x1800b572b  xor     rax, rsp
0x1800b572e  mov     [rsp+0C8h+var_58], rax
0x1800b5733  mov     r14, r9
0x1800b5736  mov     rdi, r8
0x1800b5739  mov     rbp, rdx
0x1800b573c  mov     rbx, rcx
0x1800b573f  xor     r13d, r13d
0x1800b5742  cmp     [rcx+40h], r13
0x1800b5746  jnz     loc_1800B595C
0x1800b574c  movzx   eax, word ptr [rcx+132h]
0x1800b5753  neg     ax
0x1800b5756  sbb     ecx, ecx
0x1800b5758  and     ecx, 800000h
0x1800b575e  add     ecx, 56000000h
0x1800b5764  mov     r15d, ecx
0x1800b5767  bts     r15d, 1Bh
0x1800b576c  cmp     [rbx+134h], r13d
0x1800b5773  cmovnz  r15d, ecx
0x1800b5777  movzx   eax, word ptr [rbx+130h]
0x1800b577e  neg     ax
0x1800b5781  sbb     r12d, r12d
0x1800b5784  and     r12d, 200h
0x1800b578b  lea     rsi, [rbx+0F8h]
0x1800b5792  mov     rax, [rbx]
0x1800b5795  mov     rcx, rbx
0x1800b5798  mov     rax, [rax+310h]
0x1800b579f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b57a4  test    eax, eax
0x1800b57a6  jz      short loc_1800B57B0
0x1800b57a8  test    dword ptr [rsi], 100000h
0x1800b57ae  jz      short loc_1800B5818
0x1800b57b0  test    dword ptr [rsi], 80000h
0x1800b57b6  jz      short loc_1800B5818
0x1800b57b8  mov     ecx, 20h ; ' '; int
0x1800b57bd  call    ?AfxEndDeferRegisterClass@@YAHJ@Z; AfxEndDeferRegisterClass(long)
0x1800b57c2  mov     edx, [rdi+4]
0x1800b57c5  mov     r8d, [rdi]
0x1800b57c8  mov     ecx, [rdi+0Ch]
0x1800b57cb  sub     ecx, edx
0x1800b57cd  mov     eax, [rdi+8]
0x1800b57d0  sub     eax, r8d
0x1800b57d3  mov     [rsp+0C8h+var_70], r13; void *
0x1800b57d8  mov     [rsp+0C8h+var_78], r13; HMENU
0x1800b57dd  mov     [rsp+0C8h+var_80], rbp; HWND
0x1800b57e2  mov     [rsp+0C8h+var_88], ecx; int
0x1800b57e6  mov     [rsp+0C8h+var_90], eax; int
0x1800b57ea  mov     [rsp+0C8h+uFlags], edx; int
0x1800b57ee  mov     [rsp+0C8h+cy], r8d; int
0x1800b57f3  mov     [rsp+0C8h+var_A8], r15d; unsigned int
0x1800b57f8  mov     r9, [rbx+108h]; unsigned __int16 *
0x1800b57ff  lea     r8, aAfxolecontrol4; "AfxOleControl42u"
0x1800b5806  lea     edx, [r12+4]; unsigned int
0x1800b580b  mov     rcx, rbx; this
0x1800b580e  call    ?CreateEx@CWnd@@QEAAHKPEBG0KHHHHPEAUHWND__@@PEAUHMENU__@@PEAX@Z; CWnd::CreateEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,void *)
0x1800b5813  jmp     loc_1800B5948
0x1800b5818  mov     rax, [rbx+0E8h]
0x1800b581f  test    rax, rax
0x1800b5822  jnz     short loc_1800B5881
0x1800b5824  mov     ecx, 88h; Size
0x1800b5829  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b582e  mov     qword ptr [rsp+0C8h+rcDst.left], rax
0x1800b5833  test    rax, rax
0x1800b5836  jz      short loc_1800B5845
0x1800b5838  mov     rcx, rax; this
0x1800b583b  call    ??0CReflectorWnd@@QEAA@XZ; CReflectorWnd::CReflectorWnd(void)
0x1800b5840  mov     rsi, rax
0x1800b5843  jmp     short loc_1800B5848
0x1800b5845  mov     rsi, r13
0x1800b5848  mov     [rbx+0E8h], rsi
0x1800b584f  mov     rdx, rdi
0x1800b5852  test    r14, r14
0x1800b5855  cmovnz  rdx, r14; lprcSrc
0x1800b5859  lea     rcx, [rsp+0C8h+rcDst]; lprcDst
0x1800b585e  call    cs:__imp_CopyRect
0x1800b5864  mov     r8, rbp; HWND
0x1800b5867  lea     rdx, [rsp+0C8h+rcDst]; struct CRect *
0x1800b586c  mov     rcx, rsi; this
0x1800b586f  call    ?Create@CReflectorWnd@@QEAAHAEBVCRect@@PEAUHWND__@@@Z; CReflectorWnd::Create(CRect const &,HWND__ *)
0x1800b5874  test    eax, eax
0x1800b5876  jnz     short loc_1800B58BE
0x1800b5878  mov     [rbx+0E8h], r13
0x1800b587f  jmp     short loc_1800B58BE
0x1800b5881  mov     rcx, [rax+40h]; hWndChild
0x1800b5885  test    rcx, rcx
0x1800b5888  jz      short loc_1800B58BE
0x1800b588a  mov     rdx, rbp; hWndNewParent
0x1800b588d  call    cs:__imp_SetParent
0x1800b5893  mov     rcx, [rbx+0E8h]
0x1800b589a  mov     [rsp+0C8h+uFlags], 57h ; 'W'; uFlags
0x1800b58a2  mov     [rsp+0C8h+cy], r13d; cy
0x1800b58a7  mov     [rsp+0C8h+var_A8], r13d; cx
0x1800b58ac  xor     r9d, r9d; Y
0x1800b58af  xor     r8d, r8d; X
0x1800b58b2  xor     edx, edx; hWndInsertAfter
0x1800b58b4  mov     rcx, [rcx+40h]; hWnd
0x1800b58b8  call    cs:__imp_SetWindowPos
0x1800b58be  mov     rax, [rbx+0E8h]
0x1800b58c5  test    rax, rax
0x1800b58c8  jz      short loc_1800B5948
0x1800b58ca  mov     rdx, [rax+40h]
0x1800b58ce  test    rdx, rdx
0x1800b58d1  jz      short loc_1800B5948
0x1800b58d3  mov     ecx, [rdi+0Ch]
0x1800b58d6  sub     ecx, [rdi+4]
0x1800b58d9  mov     eax, [rdi+8]
0x1800b58dc  sub     eax, [rdi]
0x1800b58de  mov     [rsp+0C8h+var_70], r13; void *
0x1800b58e3  mov     [rsp+0C8h+var_78], r13; HMENU
0x1800b58e8  mov     [rsp+0C8h+var_80], rdx; HWND
0x1800b58ed  mov     [rsp+0C8h+var_88], ecx; int
0x1800b58f1  mov     [rsp+0C8h+var_90], eax; int
0x1800b58f5  mov     eax, [rbx+0DCh]
0x1800b58fb  mov     [rsp+0C8h+uFlags], eax; int
0x1800b58ff  mov     eax, [rbx+0D8h]
0x1800b5905  mov     [rsp+0C8h+cy], eax; int
0x1800b5909  mov     [rsp+0C8h+var_A8], r15d; unsigned int
0x1800b590e  mov     r9, [rbx+108h]; unsigned __int16 *
0x1800b5915  xor     r8d, r8d; unsigned __int16 *
0x1800b5918  lea     edx, [r12+4]; unsigned int
0x1800b591d  mov     rcx, rbx; this
0x1800b5920  call    ?CreateEx@CWnd@@QEAAHKPEBG0KHHHHPEAUHWND__@@PEAUHMENU__@@PEAX@Z; CWnd::CreateEx(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,void *)
0x1800b5925  cmp     [rbx+40h], r13
0x1800b5929  jnz     short loc_1800B5948
0x1800b592b  mov     rcx, [rbx+0E8h]
0x1800b5932  mov     rax, [rcx]
0x1800b5935  mov     rax, [rax+0C0h]
0x1800b593c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5941  mov     [rbx+0E8h], r13
0x1800b5948  mov     rax, [rbx]
0x1800b594b  mov     rcx, rbx
0x1800b594e  mov     rax, [rax+230h]
0x1800b5955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b595a  jmp     short loc_1800B59D1
0x1800b595c  mov     rax, [rcx+0E8h]
0x1800b5963  mov     rsi, rbx
0x1800b5966  test    rax, rax
0x1800b5969  cmovnz  rsi, rax
0x1800b596d  mov     rcx, [rsi+40h]; hWnd
0x1800b5971  call    cs:__imp_GetParent
0x1800b5977  cmp     rax, rbp
0x1800b597a  jz      short loc_1800B5995
0x1800b597c  mov     rax, [rbx]
0x1800b597f  mov     r8, rbp
0x1800b5982  mov     rdx, [rsi+40h]
0x1800b5986  mov     rcx, rbx
0x1800b5989  mov     rax, [rax+318h]
0x1800b5990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5995  mov     [rsp+0C8h+uFlags], 57h ; 'W'; uFlags
0x1800b599d  mov     [rsp+0C8h+cy], r13d; cy
0x1800b59a2  mov     [rsp+0C8h+var_A8], r13d; cx
0x1800b59a7  xor     r9d, r9d; Y
0x1800b59aa  xor     r8d, r8d; X
0x1800b59ad  xor     edx, edx; hWndInsertAfter
0x1800b59af  mov     rcx, [rsi+40h]; hWnd
0x1800b59b3  call    cs:__imp_SetWindowPos
0x1800b59b9  mov     rax, [rbx]
0x1800b59bc  mov     r8, r14
0x1800b59bf  mov     rdx, rdi
0x1800b59c2  mov     rcx, rbx
0x1800b59c5  mov     rax, [rax+1D8h]
0x1800b59cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b59d1  mov     eax, r13d
0x1800b59d4  cmp     [rbx+40h], r13
0x1800b59d8  setnz   al
0x1800b59db  mov     rcx, [rsp+0C8h+var_58]
0x1800b59e0  xor     rcx, rsp; StackCookie
0x1800b59e3  call    __security_check_cookie
0x1800b59e8  add     rsp, 88h
0x1800b59ef  pop     r15
0x1800b59f1  pop     r14
0x1800b59f3  pop     r13
0x1800b59f5  pop     r12
0x1800b59f7  pop     rdi
0x1800b59f8  pop     rsi
0x1800b59f9  pop     rbp
0x1800b59fa  pop     rbx
0x1800b59fb  retn
```
