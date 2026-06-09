# MODVWR::OnIMEWindowMessage(_EBWNDMSG *)

- ea: `0x180246308`
- end: `0x180246a14`
- name: `?OnIMEWindowMessage@MODVWR@@QEAAHPEAU_EBWNDMSG@@@Z`
- size: `1804`
- prototype: `__int64 __fastcall(MODVWR *__hidden this, struct _EBWNDMSG *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801f91e4`

## callees

- `0x1800e1af0`
- `0x18013c0c8`
- `0x1801f2ca0`
- `0x1801f3ac8`
- `0x180246308`
- `0x180246a1c`
- `0x180247438`
- `0x180247604`
- `0x180247674`
- `0x1802480c4`
- `0x180248118`
- `0x180289b60`

## import_xrefs

- `USER32!ShowCaret` at `0x18024671b`
- `USER32!ShowCaret` at `0x180246926`
- `USER32!ShowCaret` at `0x1802469f3`
- `USER32!ShowCaret` at `0x18024671b`
- `USER32!ShowCaret` at `0x180246926`
- `USER32!ShowCaret` at `0x1802469f3`
- `USER32!CreateCaret` at `0x180246703`
- `USER32!CreateCaret` at `0x18024690e`
- `USER32!CreateCaret` at `0x1802469db`
- `USER32!CreateCaret` at `0x180246703`
- `USER32!CreateCaret` at `0x18024690e`
- `USER32!CreateCaret` at `0x1802469db`
- `USER32!GetActiveWindow` at `0x1802466bd`
- `USER32!GetActiveWindow` at `0x180246995`
- `USER32!GetActiveWindow` at `0x1802466bd`
- `USER32!GetActiveWindow` at `0x180246995`

## pseudocode

```c
__int64 __fastcall MODVWR::OnIMEWindowMessage(HWND *this, struct _EBWNDMSG *a2)
{
  HWND v3; // rax
  int v4; // eax
  int CaretWidth; // eax
  HWND ActiveWindow; // rax
  int v7; // eax
  unsigned int CompositionString; // [rsp+20h] [rbp-90h]
  int v9; // [rsp+20h] [rbp-90h]
  int v10; // [rsp+20h] [rbp-90h]
  int v11; // [rsp+20h] [rbp-90h]
  CPANE *ActiveCpane; // [rsp+28h] [rbp-88h]
  int v13; // [rsp+30h] [rbp-80h]
  unsigned int v14; // [rsp+34h] [rbp-7Ch]
  __int64 Context; // [rsp+38h] [rbp-78h]
  unsigned int v16; // [rsp+44h] [rbp-6Ch]
  __int64 v17; // [rsp+50h] [rbp-60h]
  __int64 v18; // [rsp+58h] [rbp-58h]
  __int64 v19; // [rsp+60h] [rbp-50h]
  __int64 v20; // [rsp+68h] [rbp-48h]
  __int64 CurSysIMEPropNum; // [rsp+70h] [rbp-40h]

  Context = 0;
  v14 = 0;
  ActiveCpane = GetActiveCpane();
  if ( !ActiveCpane )
    return 0;
  v18 = *((_QWORD *)ActiveCpane + 33);
  v19 = *((_QWORD *)a2 + 1);
  v17 = *((_QWORD *)a2 + 2);
  v13 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 != 269 )
  {
    if ( v13 == 270 )
    {
      if ( (unsigned int)IS_LEVEL3IME() )
      {
        if ( (g_SystemLangId & 0x3FF) == 0x12 && (unsigned int)IS_IMECOMPOSITION() )
          CPANE::DoIMEComposition(ActiveCpane, 0, 0, 0);
        if ( qword_180400AA0 )
        {
          operator delete(qword_180400AA0);
          dword_180400AB0 = 0;
          qword_180400AA0 = 0;
          qword_180400AA8 = 0;
        }
        qword_180400AB8 = 0;
        qword_180400AC0 = 0;
        if ( (g_SystemLangId & 0x3FF) == 0x12 )
        {
          CaretWidth = CPANE::GetCaretWidth(ActiveCpane);
          CreateCaret(this[4], 0, CaretWidth, *(_DWORD *)(v18 + 260));
          CPANE::RefreshCursorPos(ActiveCpane);
          ShowCaret(this[4]);
          *((_DWORD *)this + 44) = 1;
        }
        return 1;
      }
      return v14;
    }
    if ( v13 != 271 )
    {
      if ( v13 == 641 )
      {
        if ( (unsigned int)IS_LEVEL3IME() )
          *((_QWORD *)a2 + 2) &= 0x7FFFFFFFuLL;
      }
      else if ( v13 == 642 && (g_SystemLangId & 0x3FF) == 0x12 && (v19 == 5 || v19 == 4) )
      {
        ActiveWindow = GetActiveWindow();
        CurSysIMEPropNum = GetCurSysIMEPropNum(ActiveWindow);
        if ( CurSysIMEPropNum == 9 || CurSysIMEPropNum == 10 )
        {
          v7 = CPANE::GetCaretWidth(ActiveCpane);
          CreateCaret(this[4], 0, v7, *(_DWORD *)(v18 + 260));
          CPANE::RefreshCursorPos(ActiveCpane);
          ShowCaret(this[4]);
          *((_DWORD *)this + 44) = 1;
        }
      }
      return v14;
    }
    if ( (unsigned int)IS_LEVEL3IME() && qword_180400AA0 )
    {
      if ( (v17 & 8) == 0 && (v17 & 0x800) == 0 )
      {
        if ( (unsigned int)IS_IMECOMPOSITION() )
        {
          if ( (unsigned int)IsIMEActive_0(this[4]) )
            CPANE::DoIMEComposition(ActiveCpane, 0, 0, 0);
          else
            CPANE::DetermineIMEComposition(ActiveCpane);
        }
LABEL_39:
        v14 = 1;
        goto LABEL_40;
      }
      v16 = (v17 & 8) != 0 ? 8 : 2048;
      Context = pImmGetContext(this[4]);
      if ( Context )
      {
        if ( (v17 & 8) == 0 || (v17 & 0x800) == 0 )
          goto LABEL_25;
        CompositionString = pImmGetCompositionString(Context, 2048, 0, 0);
        if ( CompositionString > dword_180400AB0 )
        {
          operator delete(qword_180400AA0);
          dword_180400AB0 = CompositionString + 64;
          qword_180400AA0 = (char *)operator new(2 * (CompositionString + 64));
          if ( !qword_180400AA0 )
          {
            dword_180400AB0 = 0;
            qword_180400AA8 = 0;
            goto LABEL_40;
          }
          qword_180400AA8 = (__int64)&qword_180400AA0[dword_180400AB0];
        }
        v9 = pImmGetCompositionString(Context, 2048, qword_180400AA0, CompositionString);
        if ( v9 >= 0 )
        {
          CPANE::DoIMEComposition(ActiveCpane, qword_180400AA0, v9, 1);
LABEL_25:
          v10 = pImmGetCompositionString(Context, v16, 0, 0);
          if ( v10 < 0 )
            goto LABEL_40;
          if ( v10 > (unsigned int)dword_180400AB0 )
          {
            operator delete(qword_180400AA0);
            dword_180400AB0 = v10 + 64;
            qword_180400AA0 = (char *)operator new((unsigned int)(2 * (v10 + 64)));
            if ( !qword_180400AA0 )
            {
              dword_180400AB0 = 0;
              qword_180400AA8 = 0;
              goto LABEL_40;
            }
            qword_180400AA8 = (__int64)&qword_180400AA0[dword_180400AB0];
          }
          v11 = pImmGetCompositionString(Context, v16, qword_180400AA0, (unsigned int)v10);
          dword_180400AB4 = pImmGetCompositionString(Context, 128, 0, 0);
          CPANE::DoIMEComposition(ActiveCpane, qword_180400AA0, v11, v16 == 2048);
          if ( (g_SystemLangId & 0x3FF) == 0x12 )
          {
            v3 = GetActiveWindow();
            v20 = GetCurSysIMEPropNum(v3);
            if ( v20 == 9 || v20 == 10 )
            {
              v4 = CPANE::GetCaretWidth(ActiveCpane);
              CreateCaret(this[4], 0, v4, *(_DWORD *)(v18 + 260));
              CPANE::RefreshCursorPos(ActiveCpane);
              ShowCaret(this[4]);
              *((_DWORD *)this + 44) = 1;
            }
          }
          goto LABEL_39;
        }
      }
    }
LABEL_40:
    if ( Context )
      pImmReleaseContext(this[4], Context);
    return v14;
  }
  if ( (unsigned int)IS_LEVEL3IME() )
  {
    if ( !qword_180400AA0 )
    {
      dword_180400AB0 = 64;
      qword_180400AA0 = (char *)operator new(0x80u);
      if ( !qword_180400AA0 )
      {
        dword_180400AB0 = 0;
        qword_180400AA8 = 0;
        return v14;
      }
      qword_180400AA8 = (__int64)&qword_180400AA0[dword_180400AB0];
    }
    qword_180400AB8 = 0;
    qword_180400AC0 = 0;
    return 1;
  }
  return v14;
}

```

## disassembly

```asm
0x180246308  mov     [rsp-8+arg_8], rdx
0x18024630d  mov     [rsp-8+arg_0], rcx
0x180246312  push    rbp
0x180246313  mov     rbp, rsp
0x180246316  sub     rsp, 0B0h
0x18024631d  mov     [rsp+0B0h+var_78], 0
0x180246326  mov     [rsp+0B0h+var_7C], 0
0x18024632e  call    ?GetActiveCpane@@YAPEAVCPANE@@XZ; GetActiveCpane(void)
0x180246333  mov     [rsp+0B0h+var_88], rax
0x180246338  cmp     [rsp+0B0h+var_88], 0
0x18024633e  jnz     short loc_180246347
0x180246340  xor     eax, eax
0x180246342  jmp     loc_180246A0B
0x180246347  mov     rax, [rsp+0B0h+var_88]
0x18024634c  mov     rax, [rax+108h]
0x180246353  mov     [rsp+0B0h+var_58], rax
0x180246358  mov     rax, [rbp+arg_8]
0x18024635c  mov     rax, [rax+8]
0x180246360  mov     [rsp+0B0h+var_50], rax
0x180246365  mov     rax, [rbp+arg_8]
0x180246369  mov     rax, [rax+10h]
0x18024636d  mov     [rsp+0B0h+var_60], rax
0x180246372  mov     rax, [rbp+arg_8]
0x180246376  mov     eax, [rax]
0x180246378  mov     [rsp+0B0h+var_80], eax
0x18024637c  cmp     [rsp+0B0h+var_80], 10Dh
0x180246384  jz      loc_180246791
0x18024638a  cmp     [rsp+0B0h+var_80], 10Eh
0x180246392  jz      loc_180246840
0x180246398  cmp     [rsp+0B0h+var_80], 10Fh
0x1802463a0  jz      short loc_1802463C3
0x1802463a2  cmp     [rsp+0B0h+var_80], 281h
0x1802463aa  jz      loc_180246947
0x1802463b0  cmp     [rsp+0B0h+var_80], 282h
0x1802463b8  jz      loc_180246970
0x1802463be  jmp     loc_180246A07
0x1802463c3  call    IS_LEVEL3IME
0x1802463c8  test    eax, eax
0x1802463ca  jnz     short loc_1802463D6
0x1802463cc  jmp     loc_180246771
0x1802463d1  jmp     loc_180246771
0x1802463d6  cmp     cs:qword_180400AA0, 0
0x1802463de  jnz     short loc_1802463EA
0x1802463e0  jmp     loc_180246771
0x1802463e5  jmp     loc_180246771
0x1802463ea  mov     rax, [rsp+0B0h+var_60]
0x1802463ef  and     rax, 8
0x1802463f3  test    rax, rax
0x1802463f6  jnz     short loc_18024640C
0x1802463f8  mov     rax, [rsp+0B0h+var_60]
0x1802463fd  and     rax, 800h
0x180246403  test    rax, rax
0x180246406  jz      loc_180246731
0x18024640c  mov     rax, [rsp+0B0h+var_60]
0x180246411  and     rax, 8
0x180246415  test    rax, rax
0x180246418  jz      short loc_180246424
0x18024641a  mov     [rsp+0B0h+var_6C], 8
0x180246422  jmp     short loc_18024642C
0x180246424  mov     [rsp+0B0h+var_6C], 800h
0x18024642c  mov     eax, [rsp+0B0h+var_6C]
0x180246430  mov     [rsp+0B0h+var_70], eax
0x180246434  mov     rax, [rbp+arg_0]
0x180246438  mov     rcx, [rax+20h]
0x18024643c  call    cs:pImmGetContext
0x180246442  mov     [rsp+0B0h+var_78], rax
0x180246447  cmp     [rsp+0B0h+var_78], 0
0x18024644d  jnz     short loc_180246459
0x18024644f  jmp     loc_180246771
0x180246454  jmp     loc_180246771
0x180246459  mov     rax, [rsp+0B0h+var_60]
0x18024645e  and     rax, 8
0x180246462  test    rax, rax
0x180246465  jz      loc_18024657C
0x18024646b  mov     rax, [rsp+0B0h+var_60]
0x180246470  and     rax, 800h
0x180246476  test    rax, rax
0x180246479  jz      loc_18024657C
0x18024647f  xor     r9d, r9d
0x180246482  xor     r8d, r8d
0x180246485  mov     edx, 800h
0x18024648a  mov     rcx, [rsp+0B0h+var_78]
0x18024648f  call    cs:pImmGetCompositionString
0x180246495  mov     [rsp+0B0h+var_90], eax
0x180246499  mov     eax, cs:dword_180400AB0
0x18024649f  cmp     [rsp+0B0h+var_90], eax
0x1802464a3  jbe     loc_18024652F
0x1802464a9  mov     rax, cs:qword_180400AA0
0x1802464b0  mov     [rbp+var_28], rax
0x1802464b4  mov     rcx, [rbp+var_28]; void *
0x1802464b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1802464bd  mov     eax, [rsp+0B0h+var_90]
0x1802464c1  add     eax, 40h ; '@'
0x1802464c4  mov     cs:dword_180400AB0, eax
0x1802464ca  mov     eax, cs:dword_180400AB0
0x1802464d0  shl     eax, 1
0x1802464d2  mov     eax, eax
0x1802464d4  mov     ecx, eax; unsigned __int64
0x1802464d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802464db  mov     [rsp+0B0h+var_38], rax
0x1802464e0  mov     rax, [rsp+0B0h+var_38]
0x1802464e5  mov     cs:qword_180400AA0, rax
0x1802464ec  cmp     cs:qword_180400AA0, 0
0x1802464f4  jnz     short loc_180246515
0x1802464f6  mov     cs:dword_180400AB0, 0
0x180246500  mov     cs:qword_180400AA8, 0
0x18024650b  jmp     loc_180246771
0x180246510  jmp     loc_180246771
0x180246515  mov     eax, cs:dword_180400AB0
0x18024651b  mov     rcx, cs:qword_180400AA0
0x180246522  add     rcx, rax
0x180246525  mov     rax, rcx
0x180246528  mov     cs:qword_180400AA8, rax
0x18024652f  mov     r9d, [rsp+0B0h+var_90]
0x180246534  mov     r8, cs:qword_180400AA0
0x18024653b  mov     edx, 800h
0x180246540  mov     rcx, [rsp+0B0h+var_78]
0x180246545  call    cs:pImmGetCompositionString
0x18024654b  mov     [rsp+0B0h+var_90], eax
0x18024654f  cmp     [rsp+0B0h+var_90], 0
0x180246554  jge     short loc_180246560
0x180246556  jmp     loc_180246771
0x18024655b  jmp     loc_180246771
0x180246560  mov     r9d, 1; int
0x180246566  mov     r8d, [rsp+0B0h+var_90]; int
0x18024656b  mov     rdx, cs:qword_180400AA0; char *
0x180246572  mov     rcx, [rsp+0B0h+var_88]; this
0x180246577  call    ?DoIMEComposition@CPANE@@QEAAXPEADJH@Z; CPANE::DoIMEComposition(char *,long,int)
0x18024657c  xor     r9d, r9d
0x18024657f  xor     r8d, r8d
0x180246582  mov     edx, [rsp+0B0h+var_70]
0x180246586  mov     rcx, [rsp+0B0h+var_78]
0x18024658b  call    cs:pImmGetCompositionString
0x180246591  mov     [rsp+0B0h+var_90], eax
0x180246595  cmp     [rsp+0B0h+var_90], 0
0x18024659a  jge     short loc_1802465A6
0x18024659c  jmp     loc_180246771
0x1802465a1  jmp     loc_180246771
0x1802465a6  mov     eax, cs:dword_180400AB0
0x1802465ac  cmp     [rsp+0B0h+var_90], eax
0x1802465b0  jbe     loc_18024663A
0x1802465b6  mov     rax, cs:qword_180400AA0
0x1802465bd  mov     [rbp+var_18], rax
0x1802465c1  mov     rcx, [rbp+var_18]; void *
0x1802465c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1802465ca  mov     eax, [rsp+0B0h+var_90]
0x1802465ce  add     eax, 40h ; '@'
0x1802465d1  mov     cs:dword_180400AB0, eax
0x1802465d7  mov     eax, cs:dword_180400AB0
0x1802465dd  shl     eax, 1
0x1802465df  mov     eax, eax
0x1802465e1  mov     ecx, eax; unsigned __int64
0x1802465e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802465e8  mov     [rbp+var_30], rax
0x1802465ec  mov     rax, [rbp+var_30]
0x1802465f0  mov     cs:qword_180400AA0, rax
0x1802465f7  cmp     cs:qword_180400AA0, 0
0x1802465ff  jnz     short loc_180246620
0x180246601  mov     cs:dword_180400AB0, 0
0x18024660b  mov     cs:qword_180400AA8, 0
0x180246616  jmp     loc_180246771
0x18024661b  jmp     loc_180246771
0x180246620  mov     eax, cs:dword_180400AB0
0x180246626  mov     rcx, cs:qword_180400AA0
0x18024662d  add     rcx, rax
0x180246630  mov     rax, rcx
0x180246633  mov     cs:qword_180400AA8, rax
0x18024663a  mov     r9d, [rsp+0B0h+var_90]
0x18024663f  mov     r8, cs:qword_180400AA0
0x180246646  mov     edx, [rsp+0B0h+var_70]
0x18024664a  mov     rcx, [rsp+0B0h+var_78]
0x18024664f  call    cs:pImmGetCompositionString
0x180246655  mov     [rsp+0B0h+var_90], eax
0x180246659  xor     r9d, r9d
0x18024665c  xor     r8d, r8d
0x18024665f  mov     edx, 80h
0x180246664  mov     rcx, [rsp+0B0h+var_78]
0x180246669  call    cs:pImmGetCompositionString
0x18024666f  mov     cs:dword_180400AB4, eax
0x180246675  cmp     [rsp+0B0h+var_70], 800h
0x18024667d  jnz     short loc_180246689
0x18024667f  mov     [rsp+0B0h+var_68], 1
0x180246687  jmp     short loc_180246691
0x180246689  mov     [rsp+0B0h+var_68], 0
0x180246691  mov     r9d, [rsp+0B0h+var_68]; int
0x180246696  mov     r8d, [rsp+0B0h+var_90]; int
0x18024669b  mov     rdx, cs:qword_180400AA0; char *
0x1802466a2  mov     rcx, [rsp+0B0h+var_88]; this
0x1802466a7  call    ?DoIMEComposition@CPANE@@QEAAXPEADJH@Z; CPANE::DoIMEComposition(char *,long,int)
0x1802466ac  movzx   eax, cs:g_SystemLangId
0x1802466b3  and     eax, 3FFh
0x1802466b8  cmp     eax, 12h
0x1802466bb  jnz     short loc_18024672F
0x1802466bd  call    cs:__imp_GetActiveWindow
0x1802466c3  mov     rcx, rax
0x1802466c6  call    GetCurSysIMEPropNum
0x1802466cb  mov     [rsp+0B0h+var_48], rax
0x1802466d0  cmp     [rsp+0B0h+var_48], 9
0x1802466d6  jz      short loc_1802466E0
0x1802466d8  cmp     [rsp+0B0h+var_48], 0Ah
0x1802466de  jnz     short loc_18024672F
0x1802466e0  mov     rcx, [rsp+0B0h+var_88]; this
0x1802466e5  call    ?GetCaretWidth@CPANE@@QEAAHXZ; CPANE::GetCaretWidth(void)
0x1802466ea  mov     rcx, [rsp+0B0h+var_58]
0x1802466ef  mov     r9d, [rcx+104h]; nHeight
0x1802466f6  mov     r8d, eax; nWidth
0x1802466f9  xor     edx, edx; hBitmap
0x1802466fb  mov     rax, [rbp+arg_0]
0x1802466ff  mov     rcx, [rax+20h]; hWnd
0x180246703  call    cs:__imp_CreateCaret
0x180246709  mov     rcx, [rsp+0B0h+var_88]; this
0x18024670e  call    ?RefreshCursorPos@CPANE@@QEAAXXZ; CPANE::RefreshCursorPos(void)
0x180246713  mov     rax, [rbp+arg_0]
0x180246717  mov     rcx, [rax+20h]; hWnd
0x18024671b  call    cs:__imp_ShowCaret
0x180246721  mov     rax, [rbp+arg_0]
0x180246725  mov     dword ptr [rax+0B0h], 1
0x18024672f  jmp     short loc_180246769
0x180246731  call    IS_IMECOMPOSITION
0x180246736  test    eax, eax
0x180246738  jz      short loc_180246769
0x18024673a  mov     rax, [rbp+arg_0]
0x18024673e  mov     rcx, [rax+20h]
0x180246742  call    IsIMEActive_0
0x180246747  test    eax, eax
0x180246749  jz      short loc_18024675F
0x18024674b  xor     r9d, r9d; int
0x18024674e  xor     r8d, r8d; int
0x180246751  xor     edx, edx; char *
0x180246753  mov     rcx, [rsp+0B0h+var_88]; this
0x180246758  call    ?DoIMEComposition@CPANE@@QEAAXPEADJH@Z; CPANE::DoIMEComposition(char *,long,int)
0x18024675d  jmp     short loc_180246769
0x18024675f  mov     rcx, [rsp+0B0h+var_88]; this
0x180246764  call    ?DetermineIMEComposition@CPANE@@QEAAXXZ; CPANE::DetermineIMEComposition(void)
0x180246769  mov     [rsp+0B0h+var_7C], 1
0x180246771  cmp     [rsp+0B0h+var_78], 0
0x180246777  jz      short loc_18024678C
0x180246779  mov     rdx, [rsp+0B0h+var_78]
0x18024677e  mov     rax, [rbp+arg_0]
0x180246782  mov     rcx, [rax+20h]
0x180246786  call    cs:pImmReleaseContext
0x18024678c  jmp     loc_180246A07
0x180246791  call    IS_LEVEL3IME
0x180246796  test    eax, eax
0x180246798  jnz     short loc_18024679F
0x18024679a  jmp     loc_180246A07
0x18024679f  cmp     cs:qword_180400AA0, 0
0x1802467a7  jnz     short loc_180246811
0x1802467a9  mov     cs:dword_180400AB0, 40h ; '@'
0x1802467b3  mov     eax, cs:dword_180400AB0
0x1802467b9  shl     eax, 1
0x1802467bb  mov     eax, eax
0x1802467bd  mov     ecx, eax; unsigned __int64
0x1802467bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802467c4  mov     [rbp+var_20], rax
0x1802467c8  mov     rax, [rbp+var_20]
0x1802467cc  mov     cs:qword_180400AA0, rax
0x1802467d3  cmp     cs:qword_180400AA0, 0
0x1802467db  jnz     short loc_1802467F7
0x1802467dd  mov     cs:dword_180400AB0, 0
0x1802467e7  mov     cs:qword_180400AA8, 0
0x1802467f2  jmp     loc_180246A07
0x1802467f7  mov     eax, cs:dword_180400AB0
0x1802467fd  mov     rcx, cs:qword_180400AA0
0x180246804  add     rcx, rax
0x180246807  mov     rax, rcx
0x18024680a  mov     cs:qword_180400AA8, rax
0x180246811  mov     dword ptr cs:qword_180400AB8, 0
0x18024681b  mov     dword ptr cs:qword_180400AB8+4, 0
0x180246825  mov     rax, cs:qword_180400AB8
0x18024682c  mov     cs:qword_180400AC0, rax
0x180246833  mov     [rsp+0B0h+var_7C], 1
0x18024683b  jmp     loc_180246A07
0x180246840  call    IS_LEVEL3IME
0x180246845  test    eax, eax
0x180246847  jnz     short loc_18024684E
0x180246849  jmp     loc_180246A07
0x18024684e  movzx   eax, cs:g_SystemLangId
0x180246855  and     eax, 3FFh
0x18024685a  cmp     eax, 12h
0x18024685d  jnz     short loc_18024687A
0x18024685f  call    IS_IMECOMPOSITION
0x180246864  test    eax, eax
0x180246866  jz      short loc_18024687A
0x180246868  xor     r9d, r9d; int
0x18024686b  xor     r8d, r8d; int
0x18024686e  xor     edx, edx; char *
0x180246870  mov     rcx, [rsp+0B0h+var_88]; this
0x180246875  call    ?DoIMEComposition@CPANE@@QEAAXPEADJH@Z; CPANE::DoIMEComposition(char *,long,int)
0x18024687a  cmp     cs:qword_180400AA0, 0
0x180246882  jz      short loc_1802468B8
0x180246884  mov     rax, cs:qword_180400AA0
0x18024688b  mov     [rbp+var_10], rax
0x18024688f  mov     rcx, [rbp+var_10]; void *
0x180246893  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180246898  mov     cs:dword_180400AB0, 0
0x1802468a2  mov     cs:qword_180400AA0, 0
0x1802468ad  mov     cs:qword_180400AA8, 0
0x1802468b8  mov     dword ptr cs:qword_180400AB8, 0
0x1802468c2  mov     dword ptr cs:qword_180400AB8+4, 0
  ... truncated ...
```
