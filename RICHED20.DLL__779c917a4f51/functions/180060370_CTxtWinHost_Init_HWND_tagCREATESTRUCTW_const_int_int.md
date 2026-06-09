# CTxtWinHost::Init(HWND__ *,tagCREATESTRUCTW const *,int,int)

- ea: `0x180060370`
- end: `0x1800606e9`
- name: `?Init@CTxtWinHost@@UEAAHPEAUHWND__@@PEBUtagCREATESTRUCTW@@HH@Z`
- size: `889`
- prototype: `__int64 __usercall@<rax>(CTxtWinHost *__hidden this@<rcx>, HWND hWnd@<rdx>, const struct tagCREATESTRUCTW *@<r8>, int@<r9d>, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800417c8`
- `0x18005eaa4`
- `0x18005ff60`
- `0x180060370`
- `0x180061230`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x1800603b9`
- `USER32!SetWindowLongPtrW` at `0x1800604b5`
- `USER32!SetWindowLongPtrW` at `0x1800604fe`
- `USER32!SetWindowLongPtrW` at `0x18006050e`
- `USER32!SetWindowLongPtrW` at `0x180060653`
- `USER32!SetWindowLongPtrW` at `0x1800603b9`
- `USER32!SetWindowLongPtrW` at `0x1800604b5`
- `USER32!SetWindowLongPtrW` at `0x1800604fe`
- `USER32!SetWindowLongPtrW` at `0x18006050e`
- `USER32!SetWindowLongPtrW` at `0x180060653`
- `USER32!GetDC` at `0x180060422`
- `USER32!GetDC` at `0x180060422`
- `USER32!InvalidateRect` at `0x180060662`
- `USER32!InvalidateRect` at `0x180060662`
- `USER32!SetScrollRange` at `0x180060621`
- `USER32!SetScrollRange` at `0x180060638`
- `USER32!SetScrollRange` at `0x180060621`
- `USER32!SetScrollRange` at `0x180060638`
- `GDI32!GetBkMode` at `0x18006042b`
- `GDI32!GetBkMode` at `0x18006042b`

## pseudocode

```c
__int64 __fastcall CTxtWinHost::Init(CTxtWinHost *this, HWND hWnd, const struct tagCREATESTRUCTW *a3, int a4, int a5)
{
  int v9; // edi
  int v10; // edi
  int v11; // edi
  DWORD dwExStyle; // edx
  LONG style; // eax
  HDC DC; // rax
  int BkMode; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // r9d
  HWND v19; // rcx
  LONG_PTR v20; // r8
  int v21; // r9d
  int v22; // r8d
  int v23; // ecx
  LONG_PTR v24; // r8
  char v25; // al
  char v26; // cl
  int v27; // edx
  int v28; // ecx
  int v29; // eax
  int v30; // edx
  struct IUnknown **v31; // rdi
  struct IUnknown *v32; // rcx
  HWND v33; // rcx
  int v35; // [rsp+30h] [rbp-D8h] BYREF
  int v36; // [rsp+34h] [rbp-D4h]
  __int16 v37; // [rsp+3Ah] [rbp-CEh]
  __int16 v38; // [rsp+48h] [rbp-C0h]

  if ( !a3->lpszClass )
    return 0;
  if ( hWnd )
    SetWindowLongPtrW(hWnd, 0, (LONG_PTR)this);
  v9 = *((_DWORD *)this + 13) ^ (a4 << 18);
  *((_DWORD *)this + 11) = 4;
  v10 = *((_DWORD *)this + 13) ^ v9 & 0x40000;
  *((_QWORD *)this + 2) = hWnd;
  v11 = v10 | 0x20;
  *((_DWORD *)this + 13) = v11;
  *((_QWORD *)this + 3) = a3->hwndParent;
  dwExStyle = a3->dwExStyle;
  *((_DWORD *)this + 12) = dwExStyle;
  style = a3->style;
  *((_DWORD *)this + 11) = style;
  if ( a5 )
  {
    DC = GetDC(hWnd);
    BkMode = GetBkMode(DC);
    v16 = *((_DWORD *)this + 12);
    dwExStyle = BkMode == 1 ? v16 | 0x20 : v16 & 0xFFFFFFDF;
    *((_DWORD *)this + 12) = dwExStyle;
  }
  else
  {
    if ( (style & 0x100000) != 0 )
    {
      style |= 0x80u;
      *((_DWORD *)this + 11) = style;
    }
    if ( (style & 0x8000000) != 0 )
      *((_DWORD *)this + 13) = v11 | 0x800;
  }
  v17 = *((_DWORD *)this + 11);
  if ( (v17 & 0x200000) != 0 )
  {
    v17 |= 0x40u;
    *((_DWORD *)this + 11) = v17;
  }
  *((_DWORD *)this + 13) &= ~1u;
  *((_DWORD *)this + 13) |= (v17 >> 23) & 1;
  v18 = *((_DWORD *)this + 13);
  if ( (dwExStyle & 0x200) != 0 || (v17 & 0x4000) != 0 )
  {
    v18 |= 1u;
    *((_DWORD *)this + 13) = v18;
  }
  if ( (v17 & 0x20) != 0 )
    *((_WORD *)this + 48) = 42;
  if ( (v18 & 1) != 0 && CW32System::_dwMajorVersion >= 4 )
  {
    v19 = (HWND)*((_QWORD *)this + 2);
    v20 = dwExStyle | 0x200;
    *((_DWORD *)this + 12) = v20;
    SetWindowLongPtrW(v19, -20, v20);
  }
  v21 = *((_DWORD *)this + 12);
  if ( (v21 & 0x400000) != 0 )
  {
    v22 = *((_DWORD *)this + 11);
    v23 = ~v22 & 2;
    v24 = v22 ^ 2u;
    *((_DWORD *)this + 11) = v24;
    *((_DWORD *)this + 12) = (v21 ^ 0x2000) & 0xFFBFBFFF | (v23 << 13);
    SetWindowLongPtrW(*((HWND *)this + 2), -16, v24);
    SetWindowLongPtrW(*((HWND *)this + 2), -20, *((unsigned int *)this + 12));
  }
  if ( (int)CTxtWinHost::CreateTextServices(this) < 0 )
    return 0;
  v25 = CW32System::_cxBorder;
  v26 = CW32System::_cyBorder;
  *((_BYTE *)this + 103) = CW32System::_cxBorder;
  *((_BYTE *)this + 102) = v26;
  if ( (*((_BYTE *)this + 52) & 1) == 0 )
  {
    *((_BYTE *)this + 103) = 2 * v25;
    *((_BYTE *)this + 102) = 2 * v26;
  }
  CTxtWinHost::SetDefaultInset(this);
  memset_0(&v35, 0, 0x9Cu);
  v27 = *((_DWORD *)this + 12);
  if ( (*((_BYTE *)this + 44) & 3) == 0 && (v27 & 0x1000) == 0 )
  {
    v28 = 0;
    v29 = 0x10000;
  }
  else
  {
    v28 = 8;
    v29 = 65544;
    v36 = 8;
    v38 = 3;
    if ( (*((_BYTE *)this + 44) & 1) == 0 )
      v38 = 2;
  }
  v30 = v27 & 0x2000;
  if ( v30 )
  {
    v36 = v29;
    v37 = 1;
  }
  v31 = (struct IUnknown **)((char *)this + 32);
  if ( !v30 )
    v29 = v28;
  if ( v29 )
  {
    v32 = *v31;
    v35 = 188;
    ((void (__fastcall *)(struct IUnknown *, __int64, __int64, int *, _QWORD))v32->lpVtbl[1].QueryInterface)(
      v32,
      1095,
      4,
      &v35,
      0);
  }
  if ( a5 )
  {
    v31 = (struct IUnknown **)((char *)this + 32);
    CTxtEdit::Set10Mode(*((CTxtEdit **)this + 4));
    v33 = (HWND)*((_QWORD *)this + 2);
    if ( v33 )
    {
      if ( (*((_DWORD *)this + 11) & 0x2000) == 0 )
      {
        SetScrollRange(v33, 1, 0, 0, 1);
        SetScrollRange(*((HWND *)this + 2), 0, 0, 0, 1);
        SetWindowLongPtrW(*((HWND *)this + 2), -16, *((_DWORD *)this + 11) & 0xFFCFFFFF);
        InvalidateRect(*((HWND *)this + 2), 0, 1);
      }
    }
  }
  if ( a3->lpszName && ((int (__fastcall *)(struct IUnknown *))(*v31)->lpVtbl[4].Release)(*v31) < 0 )
  {
    SafeReleaseAndNULL(v31);
    return 0;
  }
  if ( (*((_BYTE *)this + 44) & 0x10) != 0 )
    ((void (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, _QWORD))(*v31)->lpVtbl[1].QueryInterface)(
      *v31,
      1228,
      1024,
      1536,
      0);
  return 1;
}

```

## disassembly

```asm
0x180060370  mov     [rsp+arg_18], rbx
0x180060375  push    rbp
0x180060376  push    rsi
0x180060377  push    rdi
0x180060378  push    r12
0x18006037a  push    r13
0x18006037c  sub     rsp, 0E0h
0x180060383  mov     rax, cs:__security_cookie
0x18006038a  xor     rax, rsp
0x18006038d  mov     [rsp+108h+var_38], rax
0x180060395  cmp     qword ptr [r8+40h], 0
0x18006039a  mov     edi, r9d
0x18006039d  mov     rbp, r8
0x1800603a0  mov     rsi, rdx
0x1800603a3  mov     rbx, rcx
0x1800603a6  jz      loc_18006068C
0x1800603ac  test    rdx, rdx
0x1800603af  jz      short loc_1800603BF
0x1800603b1  mov     r8, rcx; dwNewLong
0x1800603b4  xor     edx, edx; nIndex
0x1800603b6  mov     rcx, rsi; hWnd
0x1800603b9  call    cs:__imp_SetWindowLongPtrW
0x1800603bf  shl     edi, 12h
0x1800603c2  mov     r12d, 1
0x1800603c8  xor     edi, [rbx+34h]
0x1800603cb  mov     dword ptr [rbx+2Ch], 4
0x1800603d2  and     edi, 40000h
0x1800603d8  xor     edi, [rbx+34h]
0x1800603db  mov     [rbx+10h], rsi
0x1800603df  or      edi, 20h
0x1800603e2  cmp     [rsp+108h+arg_20], 0
0x1800603ea  mov     [rbx+34h], edi
0x1800603ed  mov     rax, [rbp+18h]
0x1800603f1  mov     [rbx+18h], rax
0x1800603f5  mov     edx, [rbp+48h]
0x1800603f8  mov     [rbx+30h], edx
0x1800603fb  mov     eax, [rbp+30h]
0x1800603fe  mov     [rbx+2Ch], eax
0x180060401  jnz     short loc_18006041F
0x180060403  bt      eax, 14h
0x180060407  jnb     short loc_180060410
0x180060409  bts     eax, 7
0x18006040d  mov     [rbx+2Ch], eax
0x180060410  bt      eax, 1Bh
0x180060414  jnb     short loc_180060444
0x180060416  bts     edi, 0Bh
0x18006041a  mov     [rbx+34h], edi
0x18006041d  jmp     short loc_180060444
0x18006041f  mov     rcx, rsi; hWnd
0x180060422  call    cs:__imp_GetDC
0x180060428  mov     rcx, rax; hdc
0x18006042b  call    cs:__imp_GetBkMode
0x180060431  mov     edx, [rbx+30h]
0x180060434  cmp     eax, r12d
0x180060437  jnz     short loc_18006043E
0x180060439  or      edx, 20h
0x18006043c  jmp     short loc_180060441
0x18006043e  and     edx, 0FFFFFFDFh
0x180060441  mov     [rbx+30h], edx
0x180060444  mov     r8d, [rbx+2Ch]
0x180060448  bt      r8d, 15h
0x18006044d  jnb     short loc_180060457
0x18006044f  or      r8d, 40h
0x180060453  mov     [rbx+2Ch], r8d
0x180060457  and     dword ptr [rbx+34h], 0FFFFFFFEh
0x18006045b  mov     eax, r8d
0x18006045e  shr     eax, 17h
0x180060461  and     eax, r12d
0x180060464  or      [rbx+34h], eax
0x180060467  mov     r9d, [rbx+34h]
0x18006046b  bt      edx, 9
0x18006046f  setnb   cl
0x180060472  bt      r8d, 0Eh
0x180060477  setnb   al
0x18006047a  test    al, cl
0x18006047c  jnz     short loc_180060485
0x18006047e  or      r9d, r12d
0x180060481  mov     [rbx+34h], r9d
0x180060485  test    r8b, 20h
0x180060489  jz      short loc_180060491
0x18006048b  mov     word ptr [rbx+60h], 2Ah ; '*'
0x180060491  mov     edi, 0FFFFFFECh
0x180060496  test    r12b, r9b
0x180060499  jz      short loc_1800604BB
0x18006049b  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x1800604a2  jb      short loc_1800604BB
0x1800604a4  mov     rcx, [rbx+10h]; hWnd
0x1800604a8  bts     edx, 9
0x1800604ac  mov     r8d, edx; dwNewLong
0x1800604af  mov     edx, edi; nIndex
0x1800604b1  mov     [rbx+30h], r8d
0x1800604b5  call    cs:__imp_SetWindowLongPtrW
0x1800604bb  mov     r9d, [rbx+30h]
0x1800604bf  mov     esi, 2000h
0x1800604c4  mov     r13d, 2
0x1800604ca  bt      r9d, 16h
0x1800604cf  jnb     short loc_180060514
0x1800604d1  mov     ecx, [rbx+2Ch]
0x1800604d4  lea     edx, [r13-12h]; nIndex
0x1800604d8  mov     r8d, ecx
0x1800604db  xor     r9d, esi
0x1800604de  not     ecx
0x1800604e0  and     r9d, 0FFBFBFFFh
0x1800604e7  and     ecx, r13d
0x1800604ea  xor     r8d, r13d; dwNewLong
0x1800604ed  shl     ecx, 0Dh
0x1800604f0  or      ecx, r9d
0x1800604f3  mov     [rbx+2Ch], r8d
0x1800604f7  mov     [rbx+30h], ecx
0x1800604fa  mov     rcx, [rbx+10h]; hWnd
0x1800604fe  call    cs:__imp_SetWindowLongPtrW
0x180060504  mov     r8d, [rbx+30h]; dwNewLong
0x180060508  mov     edx, edi; nIndex
0x18006050a  mov     rcx, [rbx+10h]; hWnd
0x18006050e  call    cs:__imp_SetWindowLongPtrW
0x180060514  mov     rcx, rbx; this
0x180060517  call    ?CreateTextServices@CTxtWinHost@@QEAAJXZ; CTxtWinHost::CreateTextServices(void)
0x18006051c  test    eax, eax
0x18006051e  js      loc_18006068C
0x180060524  mov     al, byte ptr cs:?_cxBorder@CW32System@@0HA; int CW32System::_cxBorder
0x18006052a  mov     cl, byte ptr cs:?_cyBorder@CW32System@@0HA; int CW32System::_cyBorder
0x180060530  mov     [rbx+67h], al
0x180060533  mov     [rbx+66h], cl
0x180060536  test    [rbx+34h], r12b
0x18006053a  jnz     short loc_180060546
0x18006053c  add     al, al
0x18006053e  add     cl, cl
0x180060540  mov     [rbx+67h], al
0x180060543  mov     [rbx+66h], cl
0x180060546  mov     rcx, rbx; this
0x180060549  call    ?SetDefaultInset@CTxtWinHost@@QEAAXXZ; CTxtWinHost::SetDefaultInset(void)
0x18006054e  xor     edx, edx; Val
0x180060550  lea     rcx, [rsp+108h+var_D8]; void *
0x180060555  mov     r8d, 9Ch; Size
0x18006055b  call    memset_0
0x180060560  mov     edx, [rbx+30h]
0x180060563  mov     r8d, 3
0x180060569  test    [rbx+2Ch], r8b
0x18006056d  setz    cl
0x180060570  bt      edx, 0Ch
0x180060574  setnb   al
0x180060577  test    al, cl
0x180060579  jz      short loc_180060584
0x18006057b  xor     ecx, ecx
0x18006057d  mov     eax, 10000h
0x180060582  jmp     short loc_1800605A4
0x180060584  mov     ecx, 8
0x180060589  mov     eax, 10008h
0x18006058e  mov     [rsp+108h+var_D4], ecx
0x180060592  mov     [rsp+108h+var_C0], r8w
0x180060598  test    [rbx+2Ch], r12b
0x18006059c  jnz     short loc_1800605A4
0x18006059e  mov     [rsp+108h+var_C0], r13w
0x1800605a4  and     edx, esi
0x1800605a6  jz      short loc_1800605B2
0x1800605a8  mov     [rsp+108h+var_D4], eax
0x1800605ac  mov     [rsp+108h+var_CE], r12w
0x1800605b2  test    edx, edx
0x1800605b4  lea     rdi, [rbx+20h]
0x1800605b8  cmovz   eax, ecx
0x1800605bb  test    eax, eax
0x1800605bd  jz      short loc_1800605EF
0x1800605bf  mov     rcx, [rdi]
0x1800605c2  lea     r9, [rsp+108h+var_D8]
0x1800605c7  mov     [rsp+108h+var_D8], 0BCh
0x1800605cf  mov     edx, 447h
0x1800605d4  mov     r8d, 4
0x1800605da  mov     qword ptr [rsp+108h+bRedraw], 0
0x1800605e3  mov     rax, [rcx]
0x1800605e6  mov     rax, [rax+18h]
0x1800605ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605ef  cmp     [rsp+108h+arg_20], 0
0x1800605f7  jz      short loc_180060668
0x1800605f9  lea     rdi, [rbx+20h]
0x1800605fd  mov     rcx, [rdi]; this
0x180060600  call    ?Set10Mode@CTxtEdit@@QEAAXXZ; CTxtEdit::Set10Mode(void)
0x180060605  mov     rcx, [rbx+10h]; hWnd
0x180060609  test    rcx, rcx
0x18006060c  jz      short loc_180060668
0x18006060e  test    [rbx+2Ch], esi
0x180060611  jnz     short loc_180060668
0x180060613  xor     r9d, r9d; nMaxPos
0x180060616  mov     [rsp+108h+bRedraw], r12d; bRedraw
0x18006061b  xor     r8d, r8d; nMinPos
0x18006061e  mov     edx, r12d; nBar
0x180060621  call    cs:__imp_SetScrollRange
0x180060627  mov     rcx, [rbx+10h]; hWnd
0x18006062b  xor     r9d, r9d; nMaxPos
0x18006062e  xor     r8d, r8d; nMinPos
0x180060631  mov     [rsp+108h+bRedraw], r12d; bRedraw
0x180060636  xor     edx, edx; nBar
0x180060638  call    cs:__imp_SetScrollRange
0x18006063e  mov     r8d, [rbx+2Ch]
0x180060642  mov     eax, 0FFCFFFFFh
0x180060647  mov     rcx, [rbx+10h]; hWnd
0x18006064b  and     r8, rax; dwNewLong
0x18006064e  mov     edx, 0FFFFFFF0h; nIndex
0x180060653  call    cs:__imp_SetWindowLongPtrW
0x180060659  mov     rcx, [rbx+10h]; hWnd
0x18006065d  mov     r8d, r12d; bErase
0x180060660  xor     edx, edx; lpRect
0x180060662  call    cs:__imp_InvalidateRect
0x180060668  mov     rdx, [rbp+38h]
0x18006066c  test    rdx, rdx
0x18006066f  jz      short loc_1800606B5
0x180060671  mov     rcx, [rdi]
0x180060674  mov     rax, [rcx]
0x180060677  mov     rax, [rax+70h]
0x18006067b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060680  test    eax, eax
0x180060682  jns     short loc_1800606B5
0x180060684  mov     rcx, rdi; struct IUnknown **
0x180060687  call    ?SafeReleaseAndNULL@@YAXPEAPEAUIUnknown@@@Z; SafeReleaseAndNULL(IUnknown * *)
0x18006068c  xor     eax, eax
0x18006068e  mov     rcx, [rsp+108h+var_38]
0x180060696  xor     rcx, rsp; StackCookie
0x180060699  call    __security_check_cookie
0x18006069e  mov     rbx, [rsp+108h+arg_18]
0x1800606a6  add     rsp, 0E0h
0x1800606ad  pop     r13
0x1800606af  pop     r12
0x1800606b1  pop     rdi
0x1800606b2  pop     rsi
0x1800606b3  pop     rbp
0x1800606b4  retn
0x1800606b5  test    byte ptr [rbx+2Ch], 10h
0x1800606b9  jz      short loc_1800606E4
0x1800606bb  mov     rcx, [rdi]
0x1800606be  mov     r9d, 600h
0x1800606c4  mov     r8d, 400h
0x1800606ca  mov     qword ptr [rsp+108h+bRedraw], 0
0x1800606d3  mov     rdx, [rcx]
0x1800606d6  mov     rax, [rdx+18h]
0x1800606da  mov     edx, 4CCh
0x1800606df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800606e4  mov     eax, r12d
0x1800606e7  jmp     short loc_18006068E
```
