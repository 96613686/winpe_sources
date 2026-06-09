# CMsoButtonUser::TbbodDraw(IMsoControl *,void * *,HDC__ *,tagRECT *,tagRECT *,_msoceo,int,int)

- ea: `0x1800853f8`
- end: `0x1800856cc`
- name: `?TbbodDraw@CMsoButtonUser@@UEAAHPEAUIMsoControl@@PEAPEAXPEAUHDC__@@PEAUtagRECT@@3U_msoceo@@HH@Z`
- size: `724`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001180`
- `0x180028b30`
- `0x1800853f8`
- `0x1800856d4`
- `0x1800c34fc`
- `0x1800e1558`
- `0x1800e1584`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!FillRect` at `0x1800855f3`
- `USER32!FillRect` at `0x1800855f3`
- `USER32!GetDC` at `0x180085557`
- `USER32!GetDC` at `0x180085557`
- `USER32!ReleaseDC` at `0x1800855d8`
- `USER32!ReleaseDC` at `0x1800855d8`
- `GDI32!CreateCompatibleBitmap` at `0x180085537`
- `GDI32!CreateCompatibleBitmap` at `0x1800855bb`
- `GDI32!CreateCompatibleBitmap` at `0x180085537`
- `GDI32!CreateCompatibleBitmap` at `0x1800855bb`
- `GDI32!CreateCompatibleDC` at `0x180085563`
- `GDI32!CreateCompatibleDC` at `0x180085563`
- `GDI32!StretchBlt` at `0x18008565a`
- `GDI32!StretchBlt` at `0x18008565a`
- `GDI32!DeleteDC` at `0x180085686`
- `GDI32!DeleteDC` at `0x180085686`
- `GDI32!SelectObject` at `0x18008554a`
- `GDI32!SelectObject` at `0x1800855ca`
- `GDI32!SelectObject` at `0x18008566f`
- `GDI32!SelectObject` at `0x18008554a`
- `GDI32!SelectObject` at `0x1800855ca`
- `GDI32!SelectObject` at `0x18008566f`
- `GDI32!DeleteObject` at `0x18008567d`
- `GDI32!DeleteObject` at `0x1800856a0`
- `GDI32!DeleteObject` at `0x18008567d`
- `GDI32!DeleteObject` at `0x1800856a0`

## pseudocode

```c
__int64 __fastcall CMsoButtonUser::TbbodDraw(
        CMsoButtonUser *a1,
        struct IMsoControl *a2,
        int *a3,
        HDC a4,
        __int64 a5,
        int *a6,
        __int64 a7,
        int a8,
        int a9)
{
  __int64 v13; // rcx
  __int64 v15; // rax
  unsigned int v16; // esi
  int v17; // eax
  HBITMAP CompatibleBitmap; // r12
  HDC DC; // r13
  HDC hdcSrc; // rdi
  HBITMAP v21; // rbp
  HGDIOBJ v22; // r14
  HBRUSH v23; // rax
  LONG wSrc; // [rsp+60h] [rbp-78h]
  LONG hSrc; // [rsp+64h] [rbp-74h]
  HBITMAP v26; // [rsp+68h] [rbp-70h]
  RECT rc; // [rsp+70h] [rbp-68h] BYREF

  if ( (unsigned int)CMsoButtonUser::FIsOfficeAssistant(a1, a2) )
  {
    v13 = *((_QWORD *)a1 + 1);
    if ( v13 )
      return (*(__int64 (__fastcall **)(__int64, struct IMsoControl *, int *, HDC, __int64, int *, __int64, int, int))(*(_QWORD *)v13 + 144LL))(
               v13,
               a2,
               a3,
               a4,
               a5,
               a6,
               a7,
               a8,
               a9);
  }
  v15 = *a3;
  v16 = 0;
  if ( (int)v15 >= g_iEntriesInTBitems || !a6 || (a9 & 2) != 0 )
    return 0;
  if ( word_1803AC612[3 * v15] == 131 )
  {
    if ( a2 )
      v17 = (*(__int64 (__fastcall **)(struct IMsoControl *))(*(_QWORD *)a2 + 352LL))(a2) & 3;
    else
      v17 = 0;
    if ( a2 )
    {
      if ( v17 != 3 && ((v17 & 1) != 0 && (a7 & 0x200000) != 0 || (v17 & 2) != 0) )
        return 1;
      if ( (v17 & 1) == 0 && (v17 & 3) != 0 )
        return 7;
    }
    CompatibleBitmap = CreateCompatibleBitmap(a4, a6[2] - *a6, a6[3] - a6[1]);
    v26 = (HBITMAP)SelectObject(hdcDest, CompatibleBitmap);
    DC = GetDC(0);
    hdcSrc = CreateCompatibleDC(DC);
    if ( hdcSrc )
    {
      wSrc = DPIMGR::ScaleX((DPIMGR *)g_dpiMgr, 16);
      rc.left = 0;
      rc.top = 0;
      hSrc = DPIMGR::ScaleY((DPIMGR *)g_dpiMgr, 16);
      rc.right = wSrc;
      rc.bottom = hSrc;
      v21 = CreateCompatibleBitmap(DC, wSrc, hSrc);
      v22 = SelectObject(hdcSrc, v21);
      ReleaseDC(0, DC);
      v23 = BrHbrushCreate(0x8000000F);
      FillRect(hdcSrc, &rc, v23);
      if ( (unsigned int)CProjWin::GetProjItemBitmap(CProjWin::s_pProjWin, 0, hdcSrc, 0, 0) )
      {
        StretchBlt(a4, *a6, a6[1], a6[2] - *a6, a6[3] - a6[1], hdcSrc, 0, 0, wSrc, hSrc, 0xCC0020u);
        v16 = 7;
      }
      if ( v22 )
        SelectObject(hdcSrc, v22);
      if ( v21 )
        DeleteObject(v21);
      DeleteDC(hdcSrc);
    }
    RestoreBitmap(hdcDest, v26);
    DeleteObject(CompatibleBitmap);
  }
  return v16;
}

```

## disassembly

```asm
0x1800853f8  push    rbx
0x1800853fa  push    rbp
0x1800853fb  push    rsi
0x1800853fc  push    rdi
0x1800853fd  push    r12
0x1800853ff  push    r13
0x180085401  push    r14
0x180085403  push    r15
0x180085405  mov     eax, 98h
0x18008540a  call    _alloca_probe
0x18008540f  sub     rsp, rax
0x180085412  mov     rax, cs:__security_cookie
0x180085419  xor     rax, rsp
0x18008541c  mov     [rsp+0D8h+var_58], rax
0x180085424  mov     rbp, [rsp+0D8h+arg_20]
0x18008542c  mov     rbx, [rsp+0D8h+arg_28]
0x180085434  mov     r15, r9
0x180085437  mov     r14, r8
0x18008543a  mov     rdi, rdx
0x18008543d  mov     rsi, rcx
0x180085440  call    ?FIsOfficeAssistant@CMsoButtonUser@@AEAAHPEAUIMsoControl@@@Z; CMsoButtonUser::FIsOfficeAssistant(IMsoControl *)
0x180085445  test    eax, eax
0x180085447  jz      short loc_180085497
0x180085449  mov     rcx, [rsi+8]
0x18008544d  test    rcx, rcx
0x180085450  jz      short loc_180085497
0x180085452  mov     eax, [rsp+0D8h+arg_40]
0x180085459  mov     r10, [rcx]
0x18008545c  mov     r9, r15
0x18008545f  mov     [rsp+0D8h+wSrc], eax
0x180085463  mov     eax, [rsp+0D8h+arg_38]
0x18008546a  mov     r8, r14
0x18008546d  mov     [rsp+0D8h+ySrc], eax
0x180085471  mov     rax, [rsp+0D8h+arg_30]
0x180085479  mov     rdx, rdi
0x18008547c  mov     qword ptr [rsp+0D8h+xSrc], rax
0x180085481  mov     [rsp+0D8h+hdcSrc], rbx
0x180085486  mov     qword ptr [rsp+0D8h+hDest], rbp
0x18008548b  call    qword ptr [r10+90h]
0x180085492  jmp     loc_1800856A8
0x180085497  movsxd  rax, dword ptr [r14]
0x18008549a  xor     esi, esi
0x18008549c  cmp     eax, cs:?g_iEntriesInTBitems@@3HA; int g_iEntriesInTBitems
0x1800854a2  jl      short loc_1800854AB
0x1800854a4  xor     eax, eax
0x1800854a6  jmp     loc_1800856A8
0x1800854ab  test    rbx, rbx
0x1800854ae  jz      short loc_1800854A4
0x1800854b0  test    byte ptr [rsp+0D8h+arg_40], 2
0x1800854b8  jnz     short loc_1800854A4
0x1800854ba  lea     rcx, [rax+rax*2]
0x1800854be  lea     rdx, word_1803AC612
0x1800854c5  mov     eax, 83h
0x1800854ca  cmp     [rdx+rcx*2], ax
0x1800854ce  jnz     loc_1800856A6
0x1800854d4  test    rdi, rdi
0x1800854d7  jz      short loc_1800854EA
0x1800854d9  mov     rax, [rdi]
0x1800854dc  mov     rcx, rdi
0x1800854df  call    qword ptr [rax+160h]
0x1800854e5  and     eax, 3
0x1800854e8  jmp     short loc_1800854EC
0x1800854ea  xor     eax, eax
0x1800854ec  test    rdi, rdi
0x1800854ef  jz      short loc_180085527
0x1800854f1  cmp     eax, 3
0x1800854f4  jz      short loc_180085515
0x1800854f6  test    al, 1
0x1800854f8  jz      short loc_180085507
0x1800854fa  test    dword ptr [rsp+0D8h+arg_30], 200000h
0x180085505  jnz     short loc_18008550B
0x180085507  test    al, 2
0x180085509  jz      short loc_180085515
0x18008550b  mov     eax, 1
0x180085510  jmp     loc_1800856A8
0x180085515  test    al, 1
0x180085517  jnz     short loc_180085527
0x180085519  test    al, 3
0x18008551b  jz      short loc_180085527
0x18008551d  mov     eax, 7
0x180085522  jmp     loc_1800856A8
0x180085527  mov     r8d, [rbx+0Ch]
0x18008552b  mov     edx, [rbx+8]
0x18008552e  mov     rcx, r15; hdc
0x180085531  sub     r8d, [rbx+4]; cy
0x180085535  sub     edx, [rbx]; cx
0x180085537  call    cs:__imp_CreateCompatibleBitmap
0x18008553d  mov     rcx, cs:hdcDest; hdc
0x180085544  mov     rdx, rax; h
0x180085547  mov     r12, rax
0x18008554a  call    cs:__imp_SelectObject
0x180085550  xor     ecx, ecx; hWnd
0x180085552  mov     [rsp+0D8h+var_70], rax
0x180085557  call    cs:__imp_GetDC
0x18008555d  mov     rcx, rax; hdc
0x180085560  mov     r13, rax
0x180085563  call    cs:__imp_CreateCompatibleDC
0x180085569  mov     rdi, rax
0x18008556c  test    rax, rax
0x18008556f  jz      loc_18008568C
0x180085575  mov     r14d, 10h
0x18008557b  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x180085582  mov     edx, r14d; int
0x180085585  call    ?ScaleX@DPIMGR@@QEAAHH@Z; DPIMGR::ScaleX(int)
0x18008558a  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x180085591  mov     edx, r14d; int
0x180085594  mov     ebp, eax
0x180085596  mov     [rsp+0D8h+var_78], eax
0x18008559a  call    ?ScaleY@DPIMGR@@QEAAHH@Z; DPIMGR::ScaleY(int)
0x18008559f  and     [rsp+0D8h+rc.left], esi
0x1800855a3  and     [rsp+0D8h+rc.top], esi
0x1800855a7  mov     edx, ebp; cx
0x1800855a9  mov     r8d, eax; cy
0x1800855ac  mov     rcx, r13; hdc
0x1800855af  mov     [rsp+0D8h+var_74], eax
0x1800855b3  mov     [rsp+0D8h+rc.right], ebp
0x1800855b7  mov     [rsp+0D8h+rc.bottom], eax
0x1800855bb  call    cs:__imp_CreateCompatibleBitmap
0x1800855c1  mov     rdx, rax; h
0x1800855c4  mov     rcx, rdi; hdc
0x1800855c7  mov     rbp, rax
0x1800855ca  call    cs:__imp_SelectObject
0x1800855d0  mov     rdx, r13; hDC
0x1800855d3  xor     ecx, ecx; hWnd
0x1800855d5  mov     r14, rax
0x1800855d8  call    cs:__imp_ReleaseDC
0x1800855de  mov     ecx, 8000000Fh; unsigned int
0x1800855e3  call    ?BrHbrushCreate@@YAPEAUHBRUSH__@@K@Z; BrHbrushCreate(ulong)
0x1800855e8  lea     rdx, [rsp+0D8h+rc]; lprc
0x1800855ed  mov     rcx, rdi; hDC
0x1800855f0  mov     r8, rax; hbr
0x1800855f3  call    cs:__imp_FillRect
0x1800855f9  mov     rcx, cs:?s_pProjWin@CProjWin@@2PEAV1@EA; this
0x180085600  xor     r13d, r13d
0x180085603  xor     r9d, r9d; int
0x180085606  mov     r8, rdi; HDC
0x180085609  xor     edx, edx; struct Projitem *
0x18008560b  mov     [rsp+0D8h+hDest], r13d; int
0x180085610  call    ?GetProjItemBitmap@CProjWin@@QEAAHPEAVProjitem@@PEAUHDC__@@HH@Z; CProjWin::GetProjItemBitmap(Projitem *,HDC__ *,int,int)
0x180085615  test    eax, eax
0x180085617  jz      short loc_180085664
0x180085619  mov     ecx, [rsp+0D8h+var_74]
0x18008561d  mov     r9d, [rbx+8]
0x180085621  mov     r8d, [rbx+4]; yDest
0x180085625  mov     eax, [rbx+0Ch]
0x180085628  sub     r9d, [rbx]; wDest
0x18008562b  mov     edx, [rbx]; xDest
0x18008562d  mov     [rsp+0D8h+rop], 0CC0020h; rop
0x180085635  mov     [rsp+0D8h+hSrc], ecx; hSrc
0x180085639  mov     ecx, [rsp+0D8h+var_78]
0x18008563d  mov     [rsp+0D8h+wSrc], ecx; wSrc
0x180085641  mov     [rsp+0D8h+ySrc], r13d; ySrc
0x180085646  sub     eax, r8d
0x180085649  mov     [rsp+0D8h+xSrc], r13d; xSrc
0x18008564e  mov     rcx, r15; hdcDest
0x180085651  mov     [rsp+0D8h+hdcSrc], rdi; hdcSrc
0x180085656  mov     [rsp+0D8h+hDest], eax; hDest
0x18008565a  call    cs:__imp_StretchBlt
0x180085660  lea     esi, [r13+7]
0x180085664  test    r14, r14
0x180085667  jz      short loc_180085675
0x180085669  mov     rdx, r14; h
0x18008566c  mov     rcx, rdi; hdc
0x18008566f  call    cs:__imp_SelectObject
0x180085675  test    rbp, rbp
0x180085678  jz      short loc_180085683
0x18008567a  mov     rcx, rbp; ho
0x18008567d  call    cs:__imp_DeleteObject
0x180085683  mov     rcx, rdi; hdc
0x180085686  call    cs:__imp_DeleteDC
0x18008568c  mov     rdx, [rsp+0D8h+var_70]; HBITMAP
0x180085691  mov     rcx, cs:hdcDest; HDC
0x180085698  call    ?RestoreBitmap@@YAXPEAUHDC__@@PEAUHBITMAP__@@@Z; RestoreBitmap(HDC__ *,HBITMAP__ *)
0x18008569d  mov     rcx, r12; ho
0x1800856a0  call    cs:__imp_DeleteObject
0x1800856a6  mov     eax, esi
0x1800856a8  mov     rcx, [rsp+0D8h+var_58]
0x1800856b0  xor     rcx, rsp; StackCookie
0x1800856b3  call    __security_check_cookie
0x1800856b8  add     rsp, 98h
0x1800856bf  pop     r15
0x1800856c1  pop     r14
0x1800856c3  pop     r13
0x1800856c5  pop     r12
0x1800856c7  pop     rdi
0x1800856c8  pop     rsi
0x1800856c9  pop     rbp
0x1800856ca  pop     rbx
0x1800856cb  retn
```
