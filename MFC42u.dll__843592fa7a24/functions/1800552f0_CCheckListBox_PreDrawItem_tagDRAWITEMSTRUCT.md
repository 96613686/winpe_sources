# CCheckListBox::PreDrawItem(tagDRAWITEMSTRUCT *)

- ea: `0x1800552f0`
- end: `0x1800555f7`
- name: `?PreDrawItem@CCheckListBox@@IEAAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `775`
- prototype: `void __fastcall(CCheckListBox *__hidden this, struct tagDRAWITEMSTRUCT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180054810`

## callees

- `0x18000e460`
- `0x18000e790`
- `0x180013520`
- `0x1800166a0`
- `0x180022880`
- `0x18002da20`
- `0x180032f70`
- `0x180054510`
- `0x180054780`
- `0x1800552f0`
- `0x18005d190`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!SendMessageW` at `0x180055391`
- `USER32!SendMessageW` at `0x180055391`
- `USER32!CopyRect` at `0x18005545d`
- `USER32!CopyRect` at `0x1800554ac`
- `USER32!CopyRect` at `0x18005545d`
- `USER32!CopyRect` at `0x1800554ac`
- `USER32!GetSysColor` at `0x1800553ad`
- `USER32!GetSysColor` at `0x1800553e7`
- `USER32!GetSysColor` at `0x1800553ad`
- `USER32!GetSysColor` at `0x1800553e7`
- `USER32!FillRect` at `0x18005550d`
- `USER32!FillRect` at `0x18005550d`
- `GDI32!BitBlt` at `0x18005554e`
- `GDI32!BitBlt` at `0x18005554e`
- `GDI32!SelectObject` at `0x18005544c`
- `GDI32!SelectObject` at `0x18005555c`
- `GDI32!SelectObject` at `0x18005544c`
- `GDI32!SelectObject` at `0x18005555c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CCheckListBox::PreDrawItem(HWND *this, struct tagDRAWITEMSTRUCT *a2)
{
  struct CNoTrackObject *Data; // r15
  __m128i v5; // xmm2
  struct CDC *v6; // r14
  COLORREF SysColor; // r12d
  BOOL v8; // eax
  unsigned int v9; // r13d
  int v10; // ebx
  HGDIOBJ v11; // rdi
  LONG v12; // r9d
  int v13; // r8d
  int v14; // ecx
  struct tagRECT v15; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v16[2]; // [rsp+60h] [rbp-A0h] BYREF
  void **v17; // [rsp+70h] [rbp-90h] BYREF
  HDC hdc[2]; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+88h] [rbp-78h]
  RECT v20; // [rsp+90h] [rbp-70h] BYREF
  int v21[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v22; // [rsp+B0h] [rbp-50h]
  RECT rcSrc; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v24; // [rsp+D0h] [rbp-30h]
  struct tagRECT rcDst; // [rsp+E0h] [rbp-20h] BYREF
  RECT rc; // [rsp+F0h] [rbp-10h] BYREF
  int x[4]; // [rsp+100h] [rbp+0h] BYREF

  Data = CProcessLocalObject::GetData(
           (CProcessLocalObject *)&_afxChecklistState,
           CProcessLocal<_AFX_CHECKLIST_STATE>::CreateObject);
  if ( !Data )
    AfxThrowInvalidArgException();
  v5 = *(__m128i *)&a2->CtlType;
  *(_OWORD *)v21 = *(_OWORD *)&a2->CtlType;
  v22 = *(_OWORD *)&a2->itemState;
  rcSrc = *(RECT *)&a2->hDC;
  v24 = *(_OWORD *)&a2->rcItem.right;
  if ( (a2->itemID & 0x80000000) == 0 && (_mm_srli_si128(v5, 8).m128i_i8[4] & 3) != 0 )
  {
    *(_QWORD *)&v15.left = SendMessageW(this[8], 0x1A1u, (int)a2->itemID, 0);
    v6 = CDC::FromHandle(*(HDC *)&rcSrc.left);
    SysColor = GetSysColor(5);
    v8 = !(unsigned int)CWnd::IsWindowEnabled((CWnd *)this)
      || !(unsigned int)CCheckListBox::IsEnabled((CCheckListBox *)this, v21[2]);
    if ( (v22 & 1) != 0 && !v8 )
      SysColor = GetSysColor(13);
    v9 = (*(__int64 (__fastcall **)(struct CDC *, _QWORD))(*(_QWORD *)v6 + 104LL))(v6, SysColor);
    v17 = &CDC::`vftable';
    *(_OWORD *)hdc = 0;
    v19 = 0;
    if ( (unsigned int)CDC::CreateCompatibleDC((CDC *)&v17, v6) )
    {
      v10 = CCheckListBox::GetCheck((CCheckListBox *)this, v21[2]);
      v11 = SelectObject(hdc[0], *((HGDIOBJ *)Data + 1));
      CopyRect(&rcDst, (const RECT *)&rcSrc.right);
      v12 = ++rcDst.left;
      v13 = *((_DWORD *)Data + 5);
      v14 = 0;
      if ( (v15.left - v13) / 2 >= 0 )
        v14 = (v15.left - v13) / 2;
      rcDst.top += v14 + 1;
      rcDst.right = v12 + *((_DWORD *)Data + 4);
      rcDst.bottom = rcDst.top + v13;
      CopyRect(&rc, (const RECT *)&rcSrc.right);
      rc.right = rc.left + 2 + *((_DWORD *)Data + 4);
      v15 = rcDst;
      v20 = rc;
      (*((void (__fastcall **)(HWND *, int *, RECT *, struct tagRECT *))*this + 54))(this, x, &v20, &v15);
      CBrush::CBrush((CBrush *)v16, SysColor);
      FillRect(*((HDC *)v6 + 1), &rc, (HBRUSH)v16[1]);
      BitBlt(
        *((HDC *)v6 + 1),
        x[0],
        x[1],
        *((_DWORD *)Data + 4),
        *((_DWORD *)Data + 5),
        hdc[0],
        v10 * *((_DWORD *)Data + 4),
        0,
        0xCC0020u);
      SelectObject(hdc[0], v11);
      v16[0] = &CBrush::`vftable';
      CGdiObject::~CGdiObject((CGdiObject *)v16);
    }
    (*(void (__fastcall **)(struct CDC *, _QWORD))(*(_QWORD *)v6 + 104LL))(v6, v9);
    CDC::~CDC((CDC *)&v17);
  }
  if ( (unsigned __int64)(*((_QWORD *)&v24 + 1) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    *((_QWORD *)&v24 + 1) = *(_QWORD *)(*((_QWORD *)&v24 + 1) + 8LL);
  rcSrc.right += 2 + *((_DWORD *)Data + 4);
  (*((void (__fastcall **)(HWND *, int *))*this + 48))(this, v21);
}

```

## disassembly

```asm
0x1800552f0  mov     [rsp-8+arg_10], rbx
0x1800552f5  push    rbp
0x1800552f6  push    rsi
0x1800552f7  push    rdi
0x1800552f8  push    r12
0x1800552fa  push    r13
0x1800552fc  push    r14
0x1800552fe  push    r15
0x180055300  lea     rbp, [rsp-20h]
0x180055305  sub     rsp, 120h
0x18005530c  mov     rax, cs:__security_cookie
0x180055313  xor     rax, rsp
0x180055316  mov     [rbp+50h+var_40], rax
0x18005531a  mov     rbx, rdx
0x18005531d  mov     rsi, rcx
0x180055320  lea     rdx, ?CreateObject@?$CProcessLocal@V_AFX_CHECKLIST_STATE@@@@SAPEAVCNoTrackObject@@XZ; struct CNoTrackObject *(*)(void)
0x180055327  lea     rcx, ?_afxChecklistState@@3V?$CProcessLocal@V_AFX_CHECKLIST_STATE@@@@A; this
0x18005532e  call    ?GetData@CProcessLocalObject@@QEAAPEAVCNoTrackObject@@P6APEAV2@XZ@Z; CProcessLocalObject::GetData(CNoTrackObject * (*)(void))
0x180055333  mov     r15, rax
0x180055336  test    rax, rax
0x180055339  jnz     short loc_180055341
0x18005533b  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180055341  movups  xmm2, xmmword ptr [rbx]
0x180055344  movaps  xmmword ptr [rbp+50h+var_B0], xmm2
0x180055348  movups  xmm0, xmmword ptr [rbx+10h]
0x18005534c  movaps  [rbp+50h+var_A0], xmm0
0x180055350  movups  xmm1, xmmword ptr [rbx+20h]
0x180055354  movaps  xmmword ptr [rbp+50h+rcSrc.left], xmm1
0x180055358  movups  xmm0, xmmword ptr [rbx+30h]
0x18005535c  movaps  [rbp+50h+var_80], xmm0
0x180055360  movsxd  rcx, dword ptr [rbx+8]
0x180055364  test    ecx, ecx
0x180055366  js      loc_180055595
0x18005536c  psrldq  xmm2, 8
0x180055371  movq    rax, xmm2
0x180055376  shr     rax, 20h
0x18005537a  test    al, 3
0x18005537c  jz      loc_180055595
0x180055382  mov     r8, rcx; wParam
0x180055385  xor     r9d, r9d; lParam
0x180055388  mov     edx, 1A1h; Msg
0x18005538d  mov     rcx, [rsi+40h]; hWnd
0x180055391  call    cs:__imp_SendMessageW
0x180055397  mov     qword ptr [rsp+150h+var_100], rax
0x18005539c  mov     rcx, qword ptr [rbp+50h+rcSrc.left]; HDC
0x1800553a0  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x1800553a5  mov     r14, rax
0x1800553a8  mov     ecx, 5; nIndex
0x1800553ad  call    cs:__imp_GetSysColor
0x1800553b3  mov     r12d, eax
0x1800553b6  mov     rcx, rsi; this
0x1800553b9  call    ?IsWindowEnabled@CWnd@@QEBAHXZ; CWnd::IsWindowEnabled(void)
0x1800553be  test    eax, eax
0x1800553c0  jz      short loc_1800553D5
0x1800553c2  mov     edx, [rbp+50h+var_B0+8]; int
0x1800553c5  mov     rcx, rsi; this
0x1800553c8  call    ?IsEnabled@CCheckListBox@@QEAAHH@Z; CCheckListBox::IsEnabled(int)
0x1800553cd  test    eax, eax
0x1800553cf  jz      short loc_1800553D5
0x1800553d1  xor     eax, eax
0x1800553d3  jmp     short loc_1800553DA
0x1800553d5  mov     eax, 1
0x1800553da  test    byte ptr [rbp+50h+var_A0], 1
0x1800553de  jz      short loc_1800553F0
0x1800553e0  test    eax, eax
0x1800553e2  jnz     short loc_1800553F0
0x1800553e4  lea     ecx, [rax+0Dh]; nIndex
0x1800553e7  call    cs:__imp_GetSysColor
0x1800553ed  mov     r12d, eax
0x1800553f0  mov     rax, [r14]
0x1800553f3  mov     edx, r12d
0x1800553f6  mov     rcx, r14
0x1800553f9  mov     rax, [rax+68h]
0x1800553fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055402  mov     r13d, eax
0x180055405  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18005540c  mov     [rsp+150h+var_E0], rax
0x180055411  xorps   xmm0, xmm0
0x180055414  movdqu  xmmword ptr [rsp+150h+hdc], xmm0
0x18005541a  mov     [rbp+50h+var_C8], 0
0x180055421  mov     rdx, r14; struct CDC *
0x180055424  lea     rcx, [rsp+150h+var_E0]; this
0x180055429  call    ?CreateCompatibleDC@CDC@@QEAAHPEAV1@@Z; CDC::CreateCompatibleDC(CDC *)
0x18005542e  test    eax, eax
0x180055430  jz      loc_180055578
0x180055436  mov     edx, [rbp+50h+var_B0+8]; int
0x180055439  mov     rcx, rsi; this
0x18005543c  call    ?GetCheck@CCheckListBox@@QEAAHH@Z; CCheckListBox::GetCheck(int)
0x180055441  mov     ebx, eax
0x180055443  mov     rdx, [r15+8]; h
0x180055447  mov     rcx, [rsp+150h+hdc]; hdc
0x18005544c  call    cs:__imp_SelectObject
0x180055452  mov     rdi, rax
0x180055455  lea     rdx, [rbp+50h+rcSrc.right]; lprcSrc
0x180055459  lea     rcx, [rbp+50h+rcDst]; lprcDst
0x18005545d  call    cs:__imp_CopyRect
0x180055463  mov     r9d, [rbp+50h+rcDst.left]
0x180055467  inc     r9d
0x18005546a  mov     [rbp+50h+rcDst.left], r9d
0x18005546e  mov     r8d, [r15+14h]
0x180055472  mov     rax, qword ptr [rsp+150h+var_100]
0x180055477  sub     eax, r8d
0x18005547a  cdq
0x18005547b  mov     ecx, 2
0x180055480  idiv    ecx
0x180055482  xor     ecx, ecx
0x180055484  test    eax, eax
0x180055486  cmovns  ecx, eax
0x180055489  mov     edx, [rbp+50h+rcDst.top]
0x18005548c  inc     edx
0x18005548e  add     edx, ecx
0x180055490  mov     [rbp+50h+rcDst.top], edx
0x180055493  mov     ecx, [r15+10h]
0x180055497  add     ecx, r9d
0x18005549a  mov     [rbp+50h+rcDst.right], ecx
0x18005549d  lea     eax, [rdx+r8]
0x1800554a1  mov     [rbp+50h+rcDst.bottom], eax
0x1800554a4  lea     rdx, [rbp+50h+rcSrc.right]; lprcSrc
0x1800554a8  lea     rcx, [rbp+50h+rc]; lprcDst
0x1800554ac  call    cs:__imp_CopyRect
0x1800554b2  mov     ecx, [r15+10h]
0x1800554b6  mov     eax, [rbp+50h+rc.left]
0x1800554b9  add     eax, 2
0x1800554bc  add     ecx, eax
0x1800554be  mov     [rbp+50h+rc.right], ecx
0x1800554c1  movaps  xmm0, xmmword ptr [rbp+50h+rcDst.left]
0x1800554c5  movdqa  [rsp+150h+var_100], xmm0
0x1800554cb  movaps  xmm1, xmmword ptr [rbp+50h+rc.left]
0x1800554cf  movdqa  [rbp+50h+var_C0], xmm1
0x1800554d4  mov     rax, [rsi]
0x1800554d7  lea     r9, [rsp+150h+var_100]
0x1800554dc  lea     r8, [rbp+50h+var_C0]
0x1800554e0  lea     rdx, [rbp+50h+x]
0x1800554e4  mov     rcx, rsi
0x1800554e7  mov     rax, [rax+1B0h]
0x1800554ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554f3  mov     edx, r12d; color
0x1800554f6  lea     rcx, [rsp+150h+var_F0]; this
0x1800554fb  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x180055500  mov     r8, [rsp+150h+hbr]; hbr
0x180055505  lea     rdx, [rbp+50h+rc]; lprc
0x180055509  mov     rcx, [r14+8]; hDC
0x18005550d  call    cs:__imp_FillRect
0x180055513  mov     r9d, [r15+10h]; cx
0x180055517  mov     rcx, [rsp+150h+hdc]
0x18005551c  mov     eax, r9d
0x18005551f  imul    eax, ebx
0x180055522  mov     [rsp+150h+rop], 0CC0020h; rop
0x18005552a  mov     [rsp+150h+y1], 0; y1
0x180055532  mov     [rsp+150h+x1], eax; x1
0x180055536  mov     [rsp+150h+hdcSrc], rcx; hdcSrc
0x18005553b  mov     eax, [r15+14h]
0x18005553f  mov     [rsp+150h+cy], eax; cy
0x180055543  mov     r8d, [rbp+50h+y]; y
0x180055547  mov     edx, [rbp+50h+x]; x
0x18005554a  mov     rcx, [r14+8]; hdc
0x18005554e  call    cs:__imp_BitBlt
0x180055554  mov     rdx, rdi; h
0x180055557  mov     rcx, [rsp+150h+hdc]; hdc
0x18005555c  call    cs:__imp_SelectObject
0x180055562  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x180055569  mov     [rsp+150h+var_F0], rax
0x18005556e  lea     rcx, [rsp+150h+var_F0]; this
0x180055573  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180055578  mov     rax, [r14]
0x18005557b  mov     edx, r13d
0x18005557e  mov     rcx, r14
0x180055581  mov     rax, [rax+68h]
0x180055585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005558a  nop
0x18005558b  lea     rcx, [rsp+150h+var_E0]; this
0x180055590  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x180055595  mov     rcx, qword ptr [rbp+50h+var_80+8]
0x180055599  lea     rax, [rcx-1]
0x18005559d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800555a1  ja      short loc_1800555AB
0x1800555a3  mov     rax, [rcx+8]
0x1800555a7  mov     qword ptr [rbp+50h+var_80+8], rax
0x1800555ab  mov     edx, [r15+10h]
0x1800555af  mov     eax, [rbp+50h+rcSrc.right]
0x1800555b2  add     eax, 2
0x1800555b5  add     edx, eax
0x1800555b7  mov     [rbp+50h+rcSrc.right], edx
0x1800555ba  mov     rax, [rsi]
0x1800555bd  lea     rdx, [rbp+50h+var_B0]
0x1800555c1  mov     rcx, rsi
0x1800555c4  mov     rax, [rax+180h]
0x1800555cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555d0  mov     rcx, [rbp+50h+var_40]
0x1800555d4  xor     rcx, rsp; StackCookie
0x1800555d7  call    __security_check_cookie
0x1800555dc  mov     rbx, [rsp+150h+arg_10]
0x1800555e4  add     rsp, 120h
0x1800555eb  pop     r15
0x1800555ed  pop     r14
0x1800555ef  pop     r13
0x1800555f1  pop     r12
0x1800555f3  pop     rdi
0x1800555f4  pop     rsi
0x1800555f5  pop     rbp
0x1800555f6  retn
```
