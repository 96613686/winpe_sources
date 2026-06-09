# _PbrsWPEditFixer(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800b5264`
- end: `0x1800b57f6`
- name: `?_PbrsWPEditFixer@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1426`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180029278`
- `0x18005a728`
- `0x18005aa40`
- `0x1800b33e4`
- `0x1800b4a90`
- `0x1800b5264`
- `0x1800b67a4`
- `0x1800b9238`
- `0x1800bb0f0`
- `0x1800bd38c`
- `0x1800bd5f0`
- `0x1800f9bd8`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!free` at `0x1800b560e`
- `MSVCR100!free` at `0x1800b560e`
- `MSVCR100!malloc` at `0x1800b559b`
- `MSVCR100!malloc` at `0x1800b559b`
- `KERNEL32!IsDBCSLeadByte` at `0x1800b55b9`
- `KERNEL32!IsDBCSLeadByte` at `0x1800b5672`
- `KERNEL32!IsDBCSLeadByte` at `0x1800b55b9`
- `KERNEL32!IsDBCSLeadByte` at `0x1800b5672`
- `KERNEL32!GlobalLock` at `0x1800b554a`
- `KERNEL32!GlobalLock` at `0x1800b554a`
- `USER32!ShowCaret` at `0x1800b57cf`
- `USER32!ShowCaret` at `0x1800b57cf`
- `USER32!CreateCaret` at `0x1800b57c6`
- `USER32!CreateCaret` at `0x1800b57c6`
- `USER32!GetDoubleClickTime` at `0x1800b5418`
- `USER32!GetDoubleClickTime` at `0x1800b5418`
- `USER32!GetMessageTime` at `0x1800b5426`
- `USER32!GetMessageTime` at `0x1800b5426`
- `USER32!GetDlgCtrlID` at `0x1800b5357`
- `USER32!GetDlgCtrlID` at `0x1800b5357`
- `USER32!IsClipboardFormatAvailable` at `0x1800b5514`
- `USER32!IsClipboardFormatAvailable` at `0x1800b5514`
- `USER32!GetClipboardData` at `0x1800b5535`
- `USER32!GetClipboardData` at `0x1800b5535`
- `USER32!CloseClipboard` at `0x1800b5614`
- `USER32!CloseClipboard` at `0x1800b5614`
- `USER32!OpenClipboard` at `0x1800b5525`
- `USER32!OpenClipboard` at `0x1800b5525`
- `USER32!CallWindowProcA` at `0x1800b56cb`
- `USER32!CallWindowProcA` at `0x1800b56cb`
- `USER32!SetRect` at `0x1800b5491`
- `USER32!SetRect` at `0x1800b5491`
- `USER32!MapWindowPoints` at `0x1800b53f8`
- `USER32!MapWindowPoints` at `0x1800b53f8`
- `USER32!SetFocus` at `0x1800b5781`
- `USER32!SetFocus` at `0x1800b5781`
- `USER32!GetParent` at `0x1800b52ef`
- `USER32!GetParent` at `0x1800b536a`
- `USER32!GetParent` at `0x1800b52ef`
- `USER32!GetParent` at `0x1800b536a`
- `USER32!SendMessageA` at `0x1800b5303`
- `USER32!SendMessageA` at `0x1800b537d`
- `USER32!SendMessageA` at `0x1800b5600`
- `USER32!SendMessageA` at `0x1800b5303`
- `USER32!SendMessageA` at `0x1800b537d`
- `USER32!SendMessageA` at `0x1800b5600`
- `USER32!PtInRect` at `0x1800b54b5`
- `USER32!PtInRect` at `0x1800b54b5`
- `USER32!MessageBeep` at `0x1800b5630`
- `USER32!MessageBeep` at `0x1800b5630`

## pseudocode

```c
LRESULT __fastcall _PbrsWPEditFixer(HWND a1, unsigned int a2, WPARAM a3, LPARAM a4)
{
  int v4; // r13d
  unsigned int v7; // r14d
  bool v9; // zf
  HWND Parent; // rax
  WPARAM v12; // rbx
  HWND v13; // rax
  int v14; // esi
  int v15; // r12d
  UINT v16; // ebx
  int yBottom; // esi
  int v18; // edi
  int v19; // ebx
  int SystemMetrics; // eax
  HANDLE ClipboardData; // rax
  BYTE *v22; // r15
  BYTE *v23; // rsi
  unsigned int EditNonVolatileCharCount; // r12d
  unsigned int v25; // r14d
  BYTE *v26; // rax
  BYTE *v27; // r12
  BOOL v28; // eax
  BYTE v29; // al
  unsigned int v30; // r14d
  struct tagPOINT Points; // [rsp+30h] [rbp-38h] BYREF
  __int64 v32; // [rsp+38h] [rbp-30h] BYREF
  POINT pt; // [rsp+40h] [rbp-28h]
  struct tagRECT rc; // [rsp+48h] [rbp-20h] BYREF

  v4 = 0;
  v7 = a2;
  if ( a2 == 123 )
  {
    if ( (unsigned int)_FNoEdit() )
    {
      Parent = GetParent(a1);
      return SendMessageA(Parent, 0x7Bu, a3, a4);
    }
  }
  else
  {
    if ( a2 == 197 )
    {
      if ( (unsigned int)IsEuroLang(Rby_lcidCur & 0x3FF) )
        goto LABEL_11;
      dword_1803FB100 = a3;
      v9 = (_DWORD)a3 == 0;
    }
    else
    {
      if ( a2 != 258 )
        goto LABEL_11;
      v9 = (unsigned int)_FNoEdit() == 0;
    }
    if ( !v9 )
      return 0;
  }
LABEL_11:
  if ( (unsigned int)FIsPbrsMessage(a1, v7, a3, a4, &v32, 0) )
    return v32;
  if ( v7 == 274 && (a3 & 0xFFF0) == 0xF100 && (_WORD)a4 == 8 )
  {
    v12 = (unsigned __int16)GetDlgCtrlID(a1) | 0x3000000LL;
    v13 = GetParent(a1);
    SendMessageA(v13, 0x111u, v12, (LPARAM)a1);
    return 0;
  }
  v14 = dword_1803FB04C;
  v15 = -__CFSHR__(dword_1803FB04C, 2);
  if ( v7 == 12 )
  {
    v14 = dword_1803FB04C | 2;
    dword_1803FB04C |= 2u;
  }
  if ( !(unsigned int)_FIsEditVisible() && (v7 == 513 || v7 == 514 || v7 == 515) )
  {
    Points.x = (__int16)a4;
    Points.y = SWORD1(a4);
    MapWindowPoints(a1, hWndTo, &Points, 1u);
    if ( v7 == 513 && dword_1803FB084 )
    {
      v16 = GetDoubleClickTime() + dword_1803FB098;
      if ( GetMessageTime() <= v16 )
      {
        yBottom = Points.y + xGetSystemMetrics(37) / 2;
        v18 = Points.x + xGetSystemMetrics(36) / 2;
        v19 = Points.y - xGetSystemMetrics(37) / 2;
        SystemMetrics = xGetSystemMetrics(36);
        SetRect(&rc, Points.x - SystemMetrics / 2, v19, v18, yBottom);
        pt.x = (__int16)qword_1803FB0A0;
        pt.y = SWORD1(qword_1803FB0A0);
        if ( PtInRect(&rc, pt) )
          v7 = 515;
      }
      dword_1803FB084 = 0;
    }
    return _PbrsWPListFixer(
             hWndTo,
             v7,
             (HDC)a3,
             (char *)(LOWORD(Points.x) | (unsigned __int64)(LOWORD(Points.y) << 16)));
  }
  if ( !Rby_fEuroLcid )
  {
    if ( v7 == 770 )
    {
      if ( IsClipboardFormatAvailable(1u) && OpenClipboard(a1) )
      {
        ClipboardData = GetClipboardData(1u);
        if ( ClipboardData )
        {
          v22 = 0;
          v23 = (BYTE *)GlobalLock(ClipboardData);
          if ( dword_1803FB100 )
          {
            EditNonVolatileCharCount = MiscGetEditNonVolatileCharCount(a1);
            if ( lstrlenchr((const char *)v23) + EditNonVolatileCharCount > dword_1803FB100 )
            {
              if ( dword_1803FB100 < EditNonVolatileCharCount )
                v25 = 0;
              else
                v25 = dword_1803FB100 - EditNonVolatileCharCount;
              v26 = (BYTE *)malloc(2LL * v25 + 1);
              v22 = v26;
              if ( v26 )
              {
                if ( v25 )
                {
                  v27 = v26;
                  do
                  {
                    *v27 = *v23;
                    v28 = IsDBCSLeadByte(*v23);
                    ++v4;
                    ++v23;
                    ++v27;
                    if ( v28 )
                    {
                      v29 = *v23;
                      ++v4;
                      ++v23;
                      *v27++ = v29;
                    }
                    --v25;
                  }
                  while ( v25 );
                }
                v22[v4] = 0;
              }
              v23 = v22;
            }
          }
          if ( v23 )
            SendMessageA(a1, 0xC2u, 1u, (LPARAM)v23);
          if ( v22 )
            free(v22);
        }
        CloseClipboard();
      }
      return 0;
    }
    if ( v7 == 258 )
    {
      if ( (v14 & 0x2000) != 0 )
      {
LABEL_54:
        MessageBeep(0);
        return 0;
      }
      if ( dword_1803FB100 )
      {
        if ( dword_1803FB0FC )
        {
          dword_1803FB0FC = 0;
          return 0;
        }
        if ( (_BYTE)a3 != 8 )
        {
          if ( MiscGetEditNonVolatileCharCount(a1) >= dword_1803FB100 )
          {
            dword_1803FB0FC = IsDBCSLeadByte(a3);
            goto LABEL_54;
          }
          v14 = dword_1803FB04C;
        }
      }
    }
  }
  if ( !Pbrs_fHostOwned )
  {
LABEL_67:
    v32 = (int)CallWindowProcA(pfnwpEdit, a1, v7, a3, a4);
    dword_1803FB04C ^= ((unsigned __int8)dword_1803FB04C ^ (unsigned __int8)(2 * v15)) & 2;
    if ( v7 == 15 )
      _PaintImeComposition(a1);
    if ( v7 == 642 )
      _PaintImeComposition(a1);
    v30 = v7 - 7;
    if ( v30 )
    {
      if ( v30 == 1 && Sys_fIsBiDi )
        BiVBADestroyCaret(a1);
    }
    else
    {
      if ( Sys_fIsBiDi )
        BiVBACreateCaret(a1, Sys_cxBorder, nHeight, 0xFFFFFFFFFFFFFFFFuLL, 0);
      else
        CreateCaret(a1, 0, Sys_cxBorder, nHeight);
      ShowCaret(a1);
    }
    return v32;
  }
  if ( v7 != 256 )
  {
    if ( v7 == 258 && (a3 == 13 || a3 == 27) )
      return 0;
    goto LABEL_67;
  }
  if ( a3 != 13 )
  {
    if ( a3 == 27 )
    {
      _Cancel();
      return 1;
    }
    goto LABEL_67;
  }
  if ( Pbrs_fMultiSelect || (unsigned int)dword_1803F33E8 > 1 )
    dword_1803FB04C = v14 | 4;
  PbrsCommit();
  SetFocus(hWndTo);
  return 1;
}

```

## disassembly

```asm
0x1800b5264  push    rbp
0x1800b5266  push    rbx
0x1800b5267  push    rsi
0x1800b5268  push    rdi
0x1800b5269  push    r12
0x1800b526b  push    r13
0x1800b526d  push    r14
0x1800b526f  push    r15
0x1800b5271  mov     rbp, rsp
0x1800b5274  mov     eax, 68h
0x1800b5279  call    _alloca_probe
0x1800b527e  sub     rsp, rax
0x1800b5281  mov     rax, cs:__security_cookie
0x1800b5288  xor     rax, rsp
0x1800b528b  mov     [rbp+var_10], rax
0x1800b528f  mov     eax, edx
0x1800b5291  xor     r13d, r13d
0x1800b5294  mov     rbx, r9
0x1800b5297  mov     r15, r8
0x1800b529a  mov     r14d, edx
0x1800b529d  mov     rdi, rcx
0x1800b52a0  sub     eax, 7Bh ; '{'
0x1800b52a3  jz      short loc_1800B52E3
0x1800b52a5  sub     eax, 4Ah ; 'J'
0x1800b52a8  jz      short loc_1800B52BF
0x1800b52aa  cmp     eax, 3Dh ; '='
0x1800b52ad  jnz     short loc_1800B530E
0x1800b52af  call    ?_FNoEdit@@YAHXZ; _FNoEdit(void)
0x1800b52b4  test    eax, eax
0x1800b52b6  jz      short loc_1800B530E
0x1800b52b8  xor     eax, eax
0x1800b52ba  jmp     loc_1800B57D9
0x1800b52bf  movzx   ecx, word ptr cs:?Rby_lcidCur@@3KA; ulong Rby_lcidCur
0x1800b52c6  mov     eax, 3FFh
0x1800b52cb  and     cx, ax; unsigned __int16
0x1800b52ce  call    ?IsEuroLang@@YAHG@Z; IsEuroLang(ushort)
0x1800b52d3  test    eax, eax
0x1800b52d5  jnz     short loc_1800B530E
0x1800b52d7  mov     cs:dword_1803FB100, r15d
0x1800b52de  test    r15d, r15d
0x1800b52e1  jmp     short loc_1800B52B6
0x1800b52e3  call    ?_FNoEdit@@YAHXZ; _FNoEdit(void)
0x1800b52e8  test    eax, eax
0x1800b52ea  jz      short loc_1800B530E
0x1800b52ec  mov     rcx, rdi; hWnd
0x1800b52ef  call    cs:__imp_GetParent
0x1800b52f5  mov     r9, rbx; lParam
0x1800b52f8  mov     r8, r15; wParam
0x1800b52fb  mov     rcx, rax; hWnd
0x1800b52fe  mov     edx, 7Bh ; '{'; Msg
0x1800b5303  call    cs:__imp_SendMessageA
0x1800b5309  jmp     loc_1800B57D9
0x1800b530e  lea     rax, [rbp+var_30]
0x1800b5312  mov     r9, rbx; __int64
0x1800b5315  mov     r8, r15; unsigned __int64
0x1800b5318  mov     edx, r14d; unsigned int
0x1800b531b  mov     rcx, rdi; HWND
0x1800b531e  mov     [rsp+68h+var_40], r13d; int
0x1800b5323  mov     qword ptr [rsp+68h+yBottom], rax; __int64 *
0x1800b5328  call    ?FIsPbrsMessage@@YAHPEAUHWND__@@I_K_JPEA_JH@Z; FIsPbrsMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 *,int)
0x1800b532d  test    eax, eax
0x1800b532f  jnz     loc_1800B57D5
0x1800b5335  cmp     r14d, 112h
0x1800b533c  jnz     short loc_1800B5388
0x1800b533e  mov     rax, r15
0x1800b5341  and     eax, 0FFF0h
0x1800b5346  cmp     rax, 0F100h
0x1800b534c  jnz     short loc_1800B5388
0x1800b534e  cmp     bx, 8
0x1800b5352  jnz     short loc_1800B5388
0x1800b5354  mov     rcx, rdi; hWnd
0x1800b5357  call    cs:__imp_GetDlgCtrlID
0x1800b535d  mov     rcx, rdi; hWnd
0x1800b5360  movzx   ebx, ax
0x1800b5363  or      rbx, 3000000h
0x1800b536a  call    cs:__imp_GetParent
0x1800b5370  lea     edx, [r14-1]; Msg
0x1800b5374  mov     r9, rdi; lParam
0x1800b5377  mov     r8, rbx; wParam
0x1800b537a  mov     rcx, rax; hWnd
0x1800b537d  call    cs:__imp_SendMessageA
0x1800b5383  jmp     loc_1800B52B8
0x1800b5388  mov     esi, cs:dword_1803FB04C
0x1800b538e  mov     r12d, esi
0x1800b5391  shr     r12d, 2
0x1800b5395  sbb     r12d, r12d
0x1800b5398  cmp     r14d, 0Ch
0x1800b539c  jnz     short loc_1800B53A7
0x1800b539e  or      esi, 2
0x1800b53a1  mov     cs:dword_1803FB04C, esi
0x1800b53a7  call    ?_FIsEditVisible@@YAHXZ; _FIsEditVisible(void)
0x1800b53ac  test    eax, eax
0x1800b53ae  jnz     loc_1800B54F3
0x1800b53b4  mov     eax, 203h
0x1800b53b9  cmp     r14d, 201h
0x1800b53c0  jz      short loc_1800B53D4
0x1800b53c2  cmp     r14d, 202h
0x1800b53c9  jz      short loc_1800B53D4
0x1800b53cb  cmp     r14d, eax
0x1800b53ce  jnz     loc_1800B54F3
0x1800b53d4  mov     rdx, cs:hWndTo; hWndTo
0x1800b53db  movsx   eax, bx
0x1800b53de  shr     rbx, 10h
0x1800b53e2  mov     [rbp+Points.x], eax
0x1800b53e5  movsx   eax, bx
0x1800b53e8  lea     r8, [rbp+Points]; lpPoints
0x1800b53ec  mov     r9d, 1; cPoints
0x1800b53f2  mov     rcx, rdi; hWndFrom
0x1800b53f5  mov     [rbp+Points.y], eax
0x1800b53f8  call    cs:__imp_MapWindowPoints
0x1800b53fe  cmp     r14d, 201h
0x1800b5405  jnz     loc_1800B54CC
0x1800b540b  cmp     cs:dword_1803FB084, r13d
0x1800b5412  jz      loc_1800B54CC
0x1800b5418  call    cs:__imp_GetDoubleClickTime
0x1800b541e  mov     ebx, cs:dword_1803FB098
0x1800b5424  add     ebx, eax
0x1800b5426  call    cs:__imp_GetMessageTime
0x1800b542c  cmp     eax, ebx
0x1800b542e  ja      loc_1800B54C5
0x1800b5434  mov     ebx, 25h ; '%'
0x1800b5439  mov     ecx, ebx; int
0x1800b543b  call    xGetSystemMetrics
0x1800b5440  lea     r12d, [rbx-1]
0x1800b5444  cdq
0x1800b5445  mov     ecx, r12d; int
0x1800b5448  sub     eax, edx
0x1800b544a  sar     eax, 1
0x1800b544c  mov     esi, eax
0x1800b544e  add     esi, [rbp+Points.y]
0x1800b5451  call    xGetSystemMetrics
0x1800b5456  mov     ecx, ebx; int
0x1800b5458  cdq
0x1800b5459  sub     eax, edx
0x1800b545b  sar     eax, 1
0x1800b545d  mov     edi, eax
0x1800b545f  add     edi, [rbp+Points.x]
0x1800b5462  call    xGetSystemMetrics
0x1800b5467  mov     ebx, [rbp+Points.y]
0x1800b546a  cdq
0x1800b546b  mov     ecx, r12d; int
0x1800b546e  sub     eax, edx
0x1800b5470  sar     eax, 1
0x1800b5472  sub     ebx, eax
0x1800b5474  call    xGetSystemMetrics
0x1800b5479  lea     rcx, [rbp+rc]; lprc
0x1800b547d  cdq
0x1800b547e  mov     r9d, edi; xRight
0x1800b5481  mov     r8d, ebx; yTop
0x1800b5484  sub     eax, edx
0x1800b5486  mov     edx, [rbp+Points.x]
0x1800b5489  mov     [rsp+68h+yBottom], esi; yBottom
0x1800b548d  sar     eax, 1
0x1800b548f  sub     edx, eax; xLeft
0x1800b5491  call    cs:__imp_SetRect
0x1800b5497  movsx   r11d, word ptr cs:qword_1803FB0A0
0x1800b549f  movsx   eax, word ptr cs:qword_1803FB0A0+2
0x1800b54a6  mov     [rbp+pt.x], r11d
0x1800b54aa  mov     [rbp+pt.y], eax
0x1800b54ad  mov     rdx, qword ptr [rbp+pt.x]; pt
0x1800b54b1  lea     rcx, [rbp+rc]; lprc
0x1800b54b5  call    cs:__imp_PtInRect
0x1800b54bb  test    eax, eax
0x1800b54bd  lea     eax, [r14+2]
0x1800b54c1  cmovnz  r14d, eax
0x1800b54c5  mov     cs:dword_1803FB084, r13d
0x1800b54cc  movzx   r9d, word ptr [rbp+Points.y]
0x1800b54d1  movzx   eax, word ptr [rbp+Points.x]
0x1800b54d5  mov     rcx, cs:hWndTo; HWND
0x1800b54dc  shl     r9d, 10h
0x1800b54e0  mov     r8, r15; unsigned __int64
0x1800b54e3  mov     edx, r14d; unsigned int
0x1800b54e6  or      r9, rax; __int64
0x1800b54e9  call    ?_PbrsWPListFixer@@YA_JPEAUHWND__@@I_K_J@Z; _PbrsWPListFixer(HWND__ *,uint,unsigned __int64,__int64)
0x1800b54ee  jmp     loc_1800B57D9
0x1800b54f3  cmp     cs:?Rby_fEuroLcid@@3HA, r13d; int Rby_fEuroLcid
0x1800b54fa  jnz     loc_1800B5686
0x1800b5500  cmp     r14d, 302h
0x1800b5507  jnz     loc_1800B561F
0x1800b550d  mov     ebx, 1
0x1800b5512  mov     ecx, ebx; format
0x1800b5514  call    cs:__imp_IsClipboardFormatAvailable
0x1800b551a  test    eax, eax
0x1800b551c  jz      loc_1800B52B8
0x1800b5522  mov     rcx, rdi; hWndNewOwner
0x1800b5525  call    cs:__imp_OpenClipboard
0x1800b552b  test    eax, eax
0x1800b552d  jz      loc_1800B52B8
0x1800b5533  mov     ecx, ebx; uFormat
0x1800b5535  call    cs:__imp_GetClipboardData
0x1800b553b  test    rax, rax
0x1800b553e  jz      loc_1800B5614
0x1800b5544  mov     rcx, rax; hMem
0x1800b5547  mov     r15, r13
0x1800b554a  call    cs:__imp_GlobalLock
0x1800b5550  cmp     cs:dword_1803FB100, r13d
0x1800b5557  mov     rsi, rax
0x1800b555a  jz      loc_1800B55ED
0x1800b5560  mov     rcx, rdi; HWND
0x1800b5563  call    ?MiscGetEditNonVolatileCharCount@@YAIPEAUHWND__@@@Z; MiscGetEditNonVolatileCharCount(HWND__ *)
0x1800b5568  mov     rcx, rsi; char *
0x1800b556b  mov     r12d, eax
0x1800b556e  call    ?lstrlenchr@@YAIPEBD@Z; lstrlenchr(char const *)
0x1800b5573  mov     r14d, cs:dword_1803FB100
0x1800b557a  lea     ecx, [rax+r12]
0x1800b557e  cmp     ecx, r14d
0x1800b5581  jbe     short loc_1800B55ED
0x1800b5583  cmp     r14d, r12d
0x1800b5586  jb      short loc_1800B558D
0x1800b5588  sub     r14d, r12d
0x1800b558b  jmp     short loc_1800B5590
0x1800b558d  mov     r14d, r13d
0x1800b5590  mov     ecx, r14d
0x1800b5593  lea     rcx, ds:1[rcx*2]; Size
0x1800b559b  call    cs:__imp_malloc
0x1800b55a1  mov     r15, rax
0x1800b55a4  test    rax, rax
0x1800b55a7  jz      short loc_1800B55EA
0x1800b55a9  test    r14d, r14d
0x1800b55ac  jz      short loc_1800B55E0
0x1800b55ae  mov     r12, rax
0x1800b55b1  mov     cl, [rsi]
0x1800b55b3  mov     [r12], cl
0x1800b55b7  mov     cl, [rsi]; TestChar
0x1800b55b9  call    cs:__imp_IsDBCSLeadByte
0x1800b55bf  add     r13d, ebx
0x1800b55c2  add     rsi, rbx
0x1800b55c5  add     r12, rbx
0x1800b55c8  test    eax, eax
0x1800b55ca  jz      short loc_1800B55DB
0x1800b55cc  mov     al, [rsi]
0x1800b55ce  add     r13d, ebx
0x1800b55d1  add     rsi, rbx
0x1800b55d4  mov     [r12], al
0x1800b55d8  add     r12, rbx
0x1800b55db  dec     r14d
0x1800b55de  jnz     short loc_1800B55B1
0x1800b55e0  mov     eax, r13d
0x1800b55e3  xor     r13d, r13d
0x1800b55e6  mov     [rax+r15], r13b
0x1800b55ea  mov     rsi, r15
0x1800b55ed  test    rsi, rsi
0x1800b55f0  jz      short loc_1800B5606
0x1800b55f2  mov     r9, rsi; lParam
0x1800b55f5  mov     r8, rbx; wParam
0x1800b55f8  mov     edx, 0C2h; Msg
0x1800b55fd  mov     rcx, rdi; hWnd
0x1800b5600  call    cs:__imp_SendMessageA
0x1800b5606  test    r15, r15
0x1800b5609  jz      short loc_1800B5614
0x1800b560b  mov     rcx, r15; Block
0x1800b560e  call    cs:__imp_free
0x1800b5614  call    cs:__imp_CloseClipboard
0x1800b561a  jmp     loc_1800B52B8
0x1800b561f  cmp     r14d, 102h
0x1800b5626  jnz     short loc_1800B5686
0x1800b5628  bt      esi, 0Dh
0x1800b562c  jnb     short loc_1800B563B
0x1800b562e  xor     ecx, ecx; uType
0x1800b5630  call    cs:__imp_MessageBeep
0x1800b5636  jmp     loc_1800B52B8
0x1800b563b  cmp     cs:dword_1803FB100, r13d
0x1800b5642  jz      short loc_1800B5686
0x1800b5644  cmp     cs:dword_1803FB0FC, r13d
0x1800b564b  jz      short loc_1800B5659
0x1800b564d  mov     cs:dword_1803FB0FC, r13d
0x1800b5654  jmp     loc_1800B52B8
0x1800b5659  cmp     r15b, 8
0x1800b565d  jz      short loc_1800B5686
0x1800b565f  mov     rcx, rdi; HWND
0x1800b5662  call    ?MiscGetEditNonVolatileCharCount@@YAIPEAUHWND__@@@Z; MiscGetEditNonVolatileCharCount(HWND__ *)
0x1800b5667  cmp     eax, cs:dword_1803FB100
0x1800b566d  jb      short loc_1800B5680
0x1800b566f  mov     cl, r15b; TestChar
0x1800b5672  call    cs:__imp_IsDBCSLeadByte
0x1800b5678  mov     cs:dword_1803FB0FC, eax
0x1800b567e  jmp     short loc_1800B562E
0x1800b5680  mov     esi, cs:dword_1803FB04C
0x1800b5686  cmp     cs:?Pbrs_fHostOwned@@3HA, r13d; int Pbrs_fHostOwned
0x1800b568d  jz      short loc_1800B56B6
0x1800b568f  mov     eax, r14d
0x1800b5692  sub     eax, 100h
0x1800b5697  jz      loc_1800B5738
0x1800b569d  cmp     eax, 2
0x1800b56a0  jnz     short loc_1800B56B6
0x1800b56a2  cmp     r15, 0Dh
0x1800b56a6  jz      loc_1800B52B8
0x1800b56ac  cmp     r15, 1Bh
0x1800b56b0  jz      loc_1800B52B8
0x1800b56b6  mov     rcx, cs:?pfnwpEdit@@3P6A_JPEAUHWND__@@I_K_J@ZEA; lpPrevWndFunc
0x1800b56bd  mov     r9, r15; wParam
0x1800b56c0  mov     r8d, r14d; Msg
0x1800b56c3  mov     rdx, rdi; hWnd
0x1800b56c6  mov     qword ptr [rsp+68h+yBottom], rbx; lParam
0x1800b56cb  call    cs:__imp_CallWindowProcA
0x1800b56d1  movsxd  rcx, eax
0x1800b56d4  mov     eax, cs:dword_1803FB04C
0x1800b56da  mov     [rbp+var_30], rcx
0x1800b56de  lea     ecx, [r12+r12]
0x1800b56e2  xor     ecx, eax
  ... truncated ...
```
