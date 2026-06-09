# SetFont(char *,int,uchar,int)

- ea: `0x1801063cc`
- end: `0x18010671a`
- name: `?SetFont@@YAJPEADHEH@Z`
- size: `846`
- prototype: `__int64 __fastcall(char *, int, unsigned __int8, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180104d28`
- `0x180105ac0`

## callees

- `0x1800e15d0`
- `0x1800e6178`
- `0x1800fa5c4`
- `0x1801063cc`
- `0x1801070ec`
- `0x1801f2e70`
- `0x180379520`

## import_xrefs

- `MSVCR100!_mbscpy_s` at `0x180106666`
- `MSVCR100!_mbscpy_s` at `0x180106666`
- `KERNEL32!MulDiv` at `0x180106440`
- `KERNEL32!MulDiv` at `0x180106440`
- `GDI32!GetStockObject` at `0x180106545`
- `GDI32!GetStockObject` at `0x180106545`
- `GDI32!GetTextFaceA` at `0x18010668d`
- `GDI32!GetTextFaceA` at `0x18010668d`
- `GDI32!GetTextMetricsA` at `0x18010660d`
- `GDI32!GetTextMetricsA` at `0x18010660d`
- `GDI32!SelectObject` at `0x180106569`
- `GDI32!SelectObject` at `0x180106569`
- `GDI32!DeleteObject` at `0x180106593`
- `GDI32!DeleteObject` at `0x1801066fa`
- `GDI32!DeleteObject` at `0x180106593`
- `GDI32!DeleteObject` at `0x1801066fa`

## pseudocode

```c
__int64 __fastcall SetFont(char *a1, int a2, BYTE a3, int a4)
{
  int v4; // eax
  EBAPP *v5; // rax
  unsigned int v6; // eax
  __int64 v8; // [rsp+20h] [rbp-60h]
  HGDIOBJ h; // [rsp+28h] [rbp-58h]
  unsigned int v10; // [rsp+30h] [rbp-50h]
  int v11; // [rsp+34h] [rbp-4Ch]
  HGDIOBJ ho; // [rsp+38h] [rbp-48h]
  struct tagTEXTMETRICA tm; // [rsp+40h] [rbp-40h] BYREF
  LONG nNumber; // [rsp+98h] [rbp+18h]

  v10 = 0;
  v8 = *((_QWORD *)PebappCur() + 1);
  v11 = 1;
  v4 = DPIMGR::DpiY((DPIMGR *)g_dpiMgr);
  nNumber = MulDiv(a2, v4, 72);
  if ( nNumber > 0 )
    nNumber = -nNumber;
  if ( nNumber < -31 )
    nNumber = -31;
  if ( nNumber > -5 )
    nNumber = -5;
  if ( a4 )
  {
    h = FindFont(*(HDC *)(v8 + 168), a1, nNumber, a3);
    if ( !h )
    {
      h = FindFont(*(HDC *)(v8 + 168), a1, nNumber, 0);
      if ( !h )
        h = FindFont(*(HDC *)(v8 + 168), a1, nNumber, 0xFFu);
    }
  }
  else
  {
    h = FindFont(*(HDC *)(v8 + 168), a1, nNumber, a3);
    if ( !h )
      h = FindFont(*(HDC *)(v8 + 168), a1, nNumber, 1u);
  }
  if ( !h )
  {
    h = GetStockObject(16);
    v11 = 0;
  }
  ho = SelectObject(*(HDC *)(v8 + 168), h);
  if ( ho )
  {
    DeleteObject(ho);
    *(_QWORD *)(v8 + 176) = h;
    h = 0;
    v5 = PebappCur();
    if ( (unsigned int)EBAPP::FIsBiDi(v5) )
      BiVBAPickFont(*(struct HDC__ **)(v8 + 168), *(struct HFONT__ **)(v8 + 176), (struct HFONT__ **)(v8 + 248), 0);
    GetTextMetricsA(*(HDC *)(v8 + 168), &tm);
    *(_DWORD *)(v8 + 256) = tm.tmAveCharWidth;
    *(_DWORD *)(v8 + 260) = tm.tmHeight;
    *(_DWORD *)(v8 + 264) = tm.tmHeight - tm.tmInternalLeading;
    if ( v11 )
      _mbscpy_s((unsigned __int8 *)(v8 + 184), 0x40u, (const unsigned __int8 *)a1);
    else
      GetTextFaceA(*(HDC *)(v8 + 168), 63, (LPSTR)(v8 + 184));
    if ( (*((_DWORD *)PebappCur() + 16) & 2) != 0 )
      v6 = tm.tmPitchAndFamily & 1 | *(_DWORD *)(v8 + 160) & 0xFFFFFFFE;
    else
      v6 = *(_DWORD *)(v8 + 160) | 1;
    *(_DWORD *)(v8 + 160) = v6;
    UiNotifyFontChanged();
  }
  else
  {
    v10 = -2147024882;
  }
  if ( h )
    DeleteObject(h);
  return v10;
}

```

## disassembly

```asm
0x1801063cc  mov     [rsp-8+arg_18], r9d
0x1801063d1  mov     [rsp-8+arg_10], r8b
0x1801063d6  mov     [rsp-8+nNumber], edx
0x1801063da  mov     [rsp-8+Src], rcx
0x1801063df  push    rbp
0x1801063e0  mov     rbp, rsp
0x1801063e3  sub     rsp, 80h
0x1801063ea  mov     rax, cs:__security_cookie
0x1801063f1  xor     rax, rsp
0x1801063f4  mov     [rsp+80h+var_8], rax
0x1801063f9  mov     [rsp+80h+var_50], 0
0x180106401  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x180106406  mov     rax, [rax+8]
0x18010640a  mov     [rsp+80h+var_60], rax
0x18010640f  mov     [rsp+80h+h], 0
0x180106418  mov     [rsp+80h+ho], 0
0x180106421  mov     [rsp+80h+var_4C], 1
0x180106429  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x180106430  call    ?DpiY@DPIMGR@@QEAAIXZ; DPIMGR::DpiY(void)
0x180106435  mov     r8d, 48h ; 'H'; nDenominator
0x18010643b  mov     edx, eax; nNumerator
0x18010643d  mov     ecx, [rbp+nNumber]; nNumber
0x180106440  call    cs:__imp_MulDiv
0x180106446  mov     [rbp+nNumber], eax
0x180106449  cmp     [rbp+nNumber], 0
0x18010644d  jle     short loc_180106457
0x18010644f  mov     eax, [rbp+nNumber]
0x180106452  neg     eax
0x180106454  mov     [rbp+nNumber], eax
0x180106457  cmp     [rbp+nNumber], 0FFFFFFE1h
0x18010645b  jge     short loc_180106464
0x18010645d  mov     [rbp+nNumber], 0FFFFFFE1h
0x180106464  cmp     [rbp+nNumber], 0FFFFFFFBh
0x180106468  jle     short loc_180106471
0x18010646a  mov     [rbp+nNumber], 0FFFFFFFBh
0x180106471  cmp     [rbp+arg_18], 0
0x180106475  jz      short loc_1801064ED
0x180106477  mov     r9b, [rbp+arg_10]; unsigned __int8
0x18010647b  mov     r8d, [rbp+nNumber]; int
0x18010647f  mov     rdx, [rbp+Src]; char *
0x180106483  mov     rax, [rsp+80h+var_60]
0x180106488  mov     rcx, [rax+0A8h]; HDC
0x18010648f  call    ?FindFont@@YAPEAUHFONT__@@PEAUHDC__@@PEADHE@Z; FindFont(HDC__ *,char *,int,uchar)
0x180106494  mov     [rsp+80h+h], rax
0x180106499  cmp     [rsp+80h+h], 0
0x18010649f  jnz     short loc_1801064EB
0x1801064a1  xor     r9d, r9d; unsigned __int8
0x1801064a4  mov     r8d, [rbp+nNumber]; int
0x1801064a8  mov     rdx, [rbp+Src]; char *
0x1801064ac  mov     rax, [rsp+80h+var_60]
0x1801064b1  mov     rcx, [rax+0A8h]; HDC
0x1801064b8  call    ?FindFont@@YAPEAUHFONT__@@PEAUHDC__@@PEADHE@Z; FindFont(HDC__ *,char *,int,uchar)
0x1801064bd  mov     [rsp+80h+h], rax
0x1801064c2  cmp     [rsp+80h+h], 0
0x1801064c8  jnz     short loc_1801064EB
0x1801064ca  mov     r9b, 0FFh; unsigned __int8
0x1801064cd  mov     r8d, [rbp+nNumber]; int
0x1801064d1  mov     rdx, [rbp+Src]; char *
0x1801064d5  mov     rax, [rsp+80h+var_60]
0x1801064da  mov     rcx, [rax+0A8h]; HDC
0x1801064e1  call    ?FindFont@@YAPEAUHFONT__@@PEAUHDC__@@PEADHE@Z; FindFont(HDC__ *,char *,int,uchar)
0x1801064e6  mov     [rsp+80h+h], rax
0x1801064eb  jmp     short loc_180106538
0x1801064ed  mov     r9b, [rbp+arg_10]; unsigned __int8
0x1801064f1  mov     r8d, [rbp+nNumber]; int
0x1801064f5  mov     rdx, [rbp+Src]; char *
0x1801064f9  mov     rax, [rsp+80h+var_60]
0x1801064fe  mov     rcx, [rax+0A8h]; HDC
0x180106505  call    ?FindFont@@YAPEAUHFONT__@@PEAUHDC__@@PEADHE@Z; FindFont(HDC__ *,char *,int,uchar)
0x18010650a  mov     [rsp+80h+h], rax
0x18010650f  cmp     [rsp+80h+h], 0
0x180106515  jnz     short loc_180106538
0x180106517  mov     r9b, 1; unsigned __int8
0x18010651a  mov     r8d, [rbp+nNumber]; int
0x18010651e  mov     rdx, [rbp+Src]; char *
0x180106522  mov     rax, [rsp+80h+var_60]
0x180106527  mov     rcx, [rax+0A8h]; HDC
0x18010652e  call    ?FindFont@@YAPEAUHFONT__@@PEAUHDC__@@PEADHE@Z; FindFont(HDC__ *,char *,int,uchar)
0x180106533  mov     [rsp+80h+h], rax
0x180106538  cmp     [rsp+80h+h], 0
0x18010653e  jnz     short loc_180106558
0x180106540  mov     ecx, 10h; i
0x180106545  call    cs:__imp_GetStockObject
0x18010654b  mov     [rsp+80h+h], rax
0x180106550  mov     [rsp+80h+var_4C], 0
0x180106558  mov     rdx, [rsp+80h+h]; h
0x18010655d  mov     rax, [rsp+80h+var_60]
0x180106562  mov     rcx, [rax+0A8h]; hdc
0x180106569  call    cs:__imp_SelectObject
0x18010656f  mov     [rsp+80h+ho], rax
0x180106574  cmp     [rsp+80h+ho], 0
0x18010657a  jnz     short loc_18010658E
0x18010657c  mov     [rsp+80h+var_50], 8007000Eh
0x180106584  jmp     loc_1801066ED
0x180106589  jmp     loc_1801066ED
0x18010658e  mov     rcx, [rsp+80h+ho]; ho
0x180106593  call    cs:__imp_DeleteObject
0x180106599  mov     [rsp+80h+ho], 0
0x1801065a2  mov     rax, [rsp+80h+var_60]
0x1801065a7  mov     rcx, [rsp+80h+h]
0x1801065ac  mov     [rax+0B0h], rcx
0x1801065b3  mov     [rsp+80h+h], 0
0x1801065bc  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x1801065c1  mov     rcx, rax; this
0x1801065c4  call    ?FIsBiDi@EBAPP@@QEAAHXZ; EBAPP::FIsBiDi(void)
0x1801065c9  test    eax, eax
0x1801065cb  jz      short loc_1801065FC
0x1801065cd  mov     rax, [rsp+80h+var_60]
0x1801065d2  add     rax, 0F8h
0x1801065d8  xor     r9d, r9d
0x1801065db  mov     r8, rax
0x1801065de  mov     rax, [rsp+80h+var_60]
0x1801065e3  mov     rdx, [rax+0B0h]
0x1801065ea  mov     rax, [rsp+80h+var_60]
0x1801065ef  mov     rcx, [rax+0A8h]
0x1801065f6  call    cs:?BiVBAPickFont@@3P6AIPEAUHDC__@@PEAUHFONT__@@PEAPEAU2@I@ZEA; uint (*BiVBAPickFont)(HDC__ *,HFONT__ *,HFONT__ * *,uint)
0x1801065fc  lea     rdx, [rsp+80h+tm]; lptm
0x180106601  mov     rax, [rsp+80h+var_60]
0x180106606  mov     rcx, [rax+0A8h]; hdc
0x18010660d  call    cs:__imp_GetTextMetricsA
0x180106613  mov     rax, [rsp+80h+var_60]
0x180106618  mov     ecx, [rsp+80h+tm.tmAveCharWidth]
0x18010661c  mov     [rax+100h], ecx
0x180106622  mov     rax, [rsp+80h+var_60]
0x180106627  mov     ecx, [rsp+80h+tm.tmHeight]
0x18010662b  mov     [rax+104h], ecx
0x180106631  mov     eax, [rsp+80h+tm.tmInternalLeading]
0x180106635  mov     ecx, [rsp+80h+tm.tmHeight]
0x180106639  sub     ecx, eax
0x18010663b  mov     eax, ecx
0x18010663d  mov     rcx, [rsp+80h+var_60]
0x180106642  mov     [rcx+108h], eax
0x180106648  cmp     [rsp+80h+var_4C], 0
0x18010664d  jz      short loc_18010666E
0x18010664f  mov     rax, [rsp+80h+var_60]
0x180106654  add     rax, 0B8h
0x18010665a  mov     r8, [rbp+Src]; Src
0x18010665e  mov     edx, 40h ; '@'; SizeInBytes
0x180106663  mov     rcx, rax; Dst
0x180106666  call    cs:__imp__mbscpy_s
0x18010666c  jmp     short loc_180106693
0x18010666e  mov     rax, [rsp+80h+var_60]
0x180106673  add     rax, 0B8h
0x180106679  mov     r8, rax; lpName
0x18010667c  mov     edx, 3Fh ; '?'; c
0x180106681  mov     rax, [rsp+80h+var_60]
0x180106686  mov     rcx, [rax+0A8h]; hdc
0x18010668d  call    cs:__imp_GetTextFaceA
0x180106693  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x180106698  mov     eax, [rax+40h]
0x18010669b  shl     eax, 1Eh
0x18010669e  sar     eax, 1Fh
0x1801066a1  test    eax, eax
0x1801066a3  jz      short loc_1801066CF
0x1801066a5  movzx   eax, [rsp+80h+tm.tmPitchAndFamily]
0x1801066aa  and     eax, 1
0x1801066ad  and     eax, 1
0x1801066b0  mov     rcx, [rsp+80h+var_60]
0x1801066b5  mov     ecx, [rcx+0A0h]
0x1801066bb  and     ecx, 0FFFFFFFEh
0x1801066be  or      ecx, eax
0x1801066c0  mov     eax, ecx
0x1801066c2  mov     rcx, [rsp+80h+var_60]
0x1801066c7  mov     [rcx+0A0h], eax
0x1801066cd  jmp     short loc_1801066E8
0x1801066cf  mov     rax, [rsp+80h+var_60]
0x1801066d4  mov     eax, [rax+0A0h]
0x1801066da  or      eax, 1
0x1801066dd  mov     rcx, [rsp+80h+var_60]
0x1801066e2  mov     [rcx+0A0h], eax
0x1801066e8  call    ?UiNotifyFontChanged@@YAXXZ; UiNotifyFontChanged(void)
0x1801066ed  cmp     [rsp+80h+h], 0
0x1801066f3  jz      short loc_180106700
0x1801066f5  mov     rcx, [rsp+80h+h]; ho
0x1801066fa  call    cs:__imp_DeleteObject
0x180106700  mov     eax, [rsp+80h+var_50]
0x180106704  mov     rcx, [rsp+80h+var_8]
0x180106709  xor     rcx, rsp; StackCookie
0x18010670c  call    __security_check_cookie
0x180106711  add     rsp, 80h
0x180106718  pop     rbp
0x180106719  retn
```
