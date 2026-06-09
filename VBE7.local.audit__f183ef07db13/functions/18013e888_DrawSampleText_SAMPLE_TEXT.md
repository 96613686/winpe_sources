# DrawSampleText(SAMPLE_TEXT *)

- ea: `0x18013e888`
- end: `0x18013ec05`
- name: `?DrawSampleText@@YAXPEAUSAMPLE_TEXT@@@Z`
- size: `893`
- prototype: `void __fastcall(struct SAMPLE_TEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18013b8c0`

## callees

- `0x18000465c`
- `0x1800e1558`
- `0x18013e670`
- `0x18013e888`
- `0x180285de4`
- `0x180379520`

## import_xrefs

- `GDI32!GetTextMetricsA` at `0x18013e8f7`
- `GDI32!GetTextMetricsA` at `0x18013e8f7`
- `GDI32!ExtTextOutA` at `0x18013eac9`
- `GDI32!ExtTextOutA` at `0x18013eba7`
- `GDI32!ExtTextOutA` at `0x18013eac9`
- `GDI32!ExtTextOutA` at `0x18013eba7`
- `GDI32!SetBkMode` at `0x18013eb08`
- `GDI32!SetBkMode` at `0x18013eb08`
- `GDI32!SelectObject` at `0x18013e9f5`
- `GDI32!SelectObject` at `0x18013eb1b`
- `GDI32!SelectObject` at `0x18013ebbf`
- `GDI32!SelectObject` at `0x18013ebd7`
- `GDI32!SelectObject` at `0x18013e9f5`
- `GDI32!SelectObject` at `0x18013eb1b`
- `GDI32!SelectObject` at `0x18013ebbf`
- `GDI32!SelectObject` at `0x18013ebd7`
- `GDI32!SetTextColor` at `0x18013e9a9`
- `GDI32!SetTextColor` at `0x18013eae6`
- `GDI32!SetTextColor` at `0x18013e9a9`
- `GDI32!SetTextColor` at `0x18013eae6`
- `GDI32!SetBkColor` at `0x18013e9b9`
- `GDI32!SetBkColor` at `0x18013ea8e`
- `GDI32!SetBkColor` at `0x18013eaf8`
- `GDI32!SetBkColor` at `0x18013e9b9`
- `GDI32!SetBkColor` at `0x18013ea8e`
- `GDI32!SetBkColor` at `0x18013eaf8`
- `GDI32!DeleteObject` at `0x18013ebea`
- `GDI32!DeleteObject` at `0x18013ebea`
- `GDI32!CreateSolidBrush` at `0x18013e9c6`
- `GDI32!CreateSolidBrush` at `0x18013e9c6`

## pseudocode

```c
void __fastcall DrawSampleText(struct SAMPLE_TEXT *a1)
{
  UINT c; // eax
  int v2; // [rsp+40h] [rbp-C0h]
  int v3; // [rsp+40h] [rbp-C0h]
  HDC hdc; // [rsp+48h] [rbp-B8h]
  int i; // [rsp+50h] [rbp-B0h]
  int y; // [rsp+58h] [rbp-A8h]
  HBRUSH h; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v8; // [rsp+68h] [rbp-98h]
  HGDIOBJ v9; // [rsp+70h] [rbp-90h]
  HGDIOBJ v10; // [rsp+78h] [rbp-88h]
  int x[4]; // [rsp+B0h] [rbp-50h] BYREF
  struct tagTEXTMETRICA tm; // [rsp+C0h] [rbp-40h] BYREF

  h = 0;
  v10 = 0;
  v9 = 0;
  hdc = *(HDC *)a1;
  *(_OWORD *)x = *(_OWORD *)*((_QWORD *)a1 + 1);
  GetTextMetricsA(hdc, &tm);
  v2 = **((_DWORD **)a1 + 1);
  y = *(_DWORD *)(*((_QWORD *)a1 + 1) + 4LL)
    + (*(_DWORD *)(*((_QWORD *)a1 + 1) + 12LL) - *(_DWORD *)(*((_QWORD *)a1 + 1) + 4LL) - tm.tmHeight) / 2;
  if ( *((_DWORD *)a1 + 7) )
  {
    DrawMarginWidgetBarBackground(hdc, *((struct tagRECT **)a1 + 1));
    for ( i = 0; i < 4 && *((_DWORD *)qword_1803F4580 + i) != *((_DWORD *)a1 + 6); ++i )
      ;
    if ( i < 4 )
    {
      SetTextColor(hdc, 0);
      SetBkColor(hdc, 0xFFFFFFu);
      h = CreateSolidBrush(*((_DWORD *)a1 + 8));
      if ( !h )
        goto LABEL_15;
      v10 = SelectObject(hdc, h);
      if ( !v10 )
        goto LABEL_15;
      BltHere((struct BLTTER *)(&g_rgpBltterMarginWidget)[i], hdc, v2 + 1, y + 1, 1);
    }
    v2 += DPIMGR::ScaleX((DPIMGR *)g_dpiMgr, 21);
  }
  x[0] = v2;
  SetBkColor(hdc, *((_DWORD *)a1 + 11));
  ExtTextOutA(hdc, v2, x[1], 2u, (const RECT *)x, 0, 0, 0);
  v3 = v2 + 11;
  SetTextColor(hdc, *((_DWORD *)a1 + 10));
  SetBkColor(hdc, *((_DWORD *)a1 + 9));
  SetBkMode(hdc, 2);
  v9 = SelectObject(hdc, *((HGDIOBJ *)a1 + 2));
  if ( v9 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(*((_QWORD *)a1 + 6) + v8) );
    c = UINT32FromUINT64(v8);
    ExtTextOutA(hdc, v3, y, 4u, (const RECT *)x, *((LPCSTR *)a1 + 6), c, 0);
  }
LABEL_15:
  if ( v9 )
    SelectObject(hdc, v9);
  if ( v10 )
    SelectObject(hdc, v10);
  if ( h )
    DeleteObject(h);
}

```

## disassembly

```asm
0x18013e888  mov     [rsp-8+arg_0], rcx
0x18013e88d  push    rbp
0x18013e88e  mov     rbp, rsp
0x18013e891  sub     rsp, 100h
0x18013e898  mov     rax, cs:__security_cookie
0x18013e89f  xor     rax, rsp
0x18013e8a2  mov     [rbp+var_8], rax
0x18013e8a6  mov     [rsp+100h+var_AC], 0
0x18013e8ae  mov     [rsp+100h+h], 0
0x18013e8b7  mov     [rsp+100h+var_88], 0
0x18013e8c0  mov     [rsp+100h+var_90], 0
0x18013e8c9  mov     rax, [rbp+arg_0]
0x18013e8cd  mov     rax, [rax]
0x18013e8d0  mov     [rsp+100h+hdc], rax
0x18013e8d5  mov     rax, [rbp+arg_0]
0x18013e8d9  mov     rax, [rax+8]
0x18013e8dd  movups  xmm0, xmmword ptr [rax]
0x18013e8e0  movdqu  [rbp+var_60], xmm0
0x18013e8e5  movups  xmm0, [rbp+var_60]
0x18013e8e9  movdqu  xmmword ptr [rbp+x], xmm0
0x18013e8ee  lea     rdx, [rbp+tm]; lptm
0x18013e8f2  mov     rcx, [rsp+100h+hdc]; hdc
0x18013e8f7  call    cs:__imp_GetTextMetricsA
0x18013e8fd  mov     eax, [rbp+tm.tmHeight]
0x18013e900  mov     [rbp+var_80], eax
0x18013e903  mov     rax, [rbp+arg_0]
0x18013e907  mov     rax, [rax+8]
0x18013e90b  mov     eax, [rax]
0x18013e90d  mov     [rsp+100h+var_C0], eax
0x18013e911  mov     rax, [rbp+arg_0]
0x18013e915  mov     rax, [rax+8]
0x18013e919  mov     rcx, [rbp+arg_0]
0x18013e91d  mov     rcx, [rcx+8]
0x18013e921  mov     ecx, [rcx+4]
0x18013e924  mov     eax, [rax+0Ch]
0x18013e927  sub     eax, ecx
0x18013e929  sub     eax, [rbp+var_80]
0x18013e92c  cdq
0x18013e92d  sub     eax, edx
0x18013e92f  sar     eax, 1
0x18013e931  mov     rcx, [rbp+arg_0]
0x18013e935  mov     rcx, [rcx+8]
0x18013e939  add     eax, [rcx+4]
0x18013e93c  mov     [rsp+100h+y], eax
0x18013e940  mov     rax, [rbp+arg_0]
0x18013e944  cmp     dword ptr [rax+1Ch], 0
0x18013e948  jz      loc_18013EA7B
0x18013e94e  mov     rax, [rbp+arg_0]
0x18013e952  mov     rdx, [rax+8]; struct tagRECT *
0x18013e956  mov     rcx, [rsp+100h+hdc]; HDC
0x18013e95b  call    ?DrawMarginWidgetBarBackground@@YAXPEAUHDC__@@PEAUtagRECT@@@Z; DrawMarginWidgetBarBackground(HDC__ *,tagRECT *)
0x18013e960  mov     [rsp+100h+var_B0], 0
0x18013e968  jmp     short loc_18013E974
0x18013e96a  mov     eax, [rsp+100h+var_B0]
0x18013e96e  inc     eax
0x18013e970  mov     [rsp+100h+var_B0], eax
0x18013e974  cmp     [rsp+100h+var_B0], 4
0x18013e979  jge     short loc_18013E997
0x18013e97b  movsxd  rax, [rsp+100h+var_B0]
0x18013e980  lea     rcx, qword_1803F4580
0x18013e987  mov     rdx, [rbp+arg_0]
0x18013e98b  mov     edx, [rdx+18h]
0x18013e98e  cmp     [rcx+rax*4], edx
0x18013e991  jnz     short loc_18013E995
0x18013e993  jmp     short loc_18013E997
0x18013e995  jmp     short loc_18013E96A
0x18013e997  cmp     [rsp+100h+var_B0], 4
0x18013e99c  jge     loc_18013EA5E
0x18013e9a2  xor     edx, edx; color
0x18013e9a4  mov     rcx, [rsp+100h+hdc]; hdc
0x18013e9a9  call    cs:__imp_SetTextColor
0x18013e9af  mov     edx, 0FFFFFFh; color
0x18013e9b4  mov     rcx, [rsp+100h+hdc]; hdc
0x18013e9b9  call    cs:__imp_SetBkColor
0x18013e9bf  mov     rax, [rbp+arg_0]
0x18013e9c3  mov     ecx, [rax+20h]; color
0x18013e9c6  call    cs:__imp_CreateSolidBrush
0x18013e9cc  mov     [rsp+100h+h], rax
0x18013e9d1  cmp     [rsp+100h+h], 0
0x18013e9d7  jnz     short loc_18013E9EB
0x18013e9d9  mov     [rsp+100h+var_AC], 8007000Eh
0x18013e9e1  jmp     loc_18013EBAD
0x18013e9e6  jmp     loc_18013EBAD
0x18013e9eb  mov     rdx, [rsp+100h+h]; h
0x18013e9f0  mov     rcx, [rsp+100h+hdc]; hdc
0x18013e9f5  call    cs:__imp_SelectObject
0x18013e9fb  mov     [rsp+100h+var_88], rax
0x18013ea00  cmp     [rsp+100h+var_88], 0
0x18013ea06  jnz     short loc_18013EA1A
0x18013ea08  mov     [rsp+100h+var_AC], 8007000Eh
0x18013ea10  jmp     loc_18013EBAD
0x18013ea15  jmp     loc_18013EBAD
0x18013ea1a  mov     eax, [rsp+100h+y]
0x18013ea1e  inc     eax
0x18013ea20  mov     ecx, [rsp+100h+var_C0]
0x18013ea24  inc     ecx
0x18013ea26  movsxd  rdx, [rsp+100h+var_B0]
0x18013ea2b  mov     [rbp+var_78], rdx
0x18013ea2f  lea     r8, ?g_rgpBltterMarginWidget@@3PAPEAVBLTTER@@A; BLTTER * near * g_rgpBltterMarginWidget
0x18013ea36  mov     [rbp+var_68], r8
0x18013ea3a  mov     dword ptr [rsp+100h+lprect], 1; int
0x18013ea42  mov     r9d, eax; int
0x18013ea45  mov     r8d, ecx; int
0x18013ea48  mov     rdx, [rsp+100h+hdc]; HDC
0x18013ea4d  mov     rcx, [rbp+var_68]
0x18013ea51  mov     rax, [rbp+var_78]
0x18013ea55  mov     rcx, [rcx+rax*8]; struct BLTTER *
0x18013ea59  call    ?BltHere@@YAXPEAVBLTTER@@PEAUHDC__@@HHH@Z; BltHere(BLTTER *,HDC__ *,int,int,int)
0x18013ea5e  mov     edx, 15h; int
0x18013ea63  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x18013ea6a  call    ?ScaleX@DPIMGR@@QEAAHH@Z; DPIMGR::ScaleX(int)
0x18013ea6f  mov     ecx, [rsp+100h+var_C0]
0x18013ea73  add     ecx, eax
0x18013ea75  mov     eax, ecx
0x18013ea77  mov     [rsp+100h+var_C0], eax
0x18013ea7b  mov     eax, [rsp+100h+var_C0]
0x18013ea7f  mov     [rbp+x], eax
0x18013ea82  mov     rax, [rbp+arg_0]
0x18013ea86  mov     edx, [rax+2Ch]; color
0x18013ea89  mov     rcx, [rsp+100h+hdc]; hdc
0x18013ea8e  call    cs:__imp_SetBkColor
0x18013ea94  mov     [rsp+100h+lpDx], 0; lpDx
0x18013ea9d  mov     [rsp+100h+c], 0; c
0x18013eaa5  mov     [rsp+100h+lpString], 0; lpString
0x18013eaae  lea     rax, [rbp+x]
0x18013eab2  mov     [rsp+100h+lprect], rax; lprect
0x18013eab7  mov     r9d, 2; options
0x18013eabd  mov     r8d, [rbp+x+4]; y
0x18013eac1  mov     edx, [rbp+x]; x
0x18013eac4  mov     rcx, [rsp+100h+hdc]; hdc
0x18013eac9  call    cs:__imp_ExtTextOutA
0x18013eacf  mov     eax, [rsp+100h+var_C0]
0x18013ead3  add     eax, 0Bh
0x18013ead6  mov     [rsp+100h+var_C0], eax
0x18013eada  mov     rax, [rbp+arg_0]
0x18013eade  mov     edx, [rax+28h]; color
0x18013eae1  mov     rcx, [rsp+100h+hdc]; hdc
0x18013eae6  call    cs:__imp_SetTextColor
0x18013eaec  mov     rax, [rbp+arg_0]
0x18013eaf0  mov     edx, [rax+24h]; color
0x18013eaf3  mov     rcx, [rsp+100h+hdc]; hdc
0x18013eaf8  call    cs:__imp_SetBkColor
0x18013eafe  mov     edx, 2; mode
0x18013eb03  mov     rcx, [rsp+100h+hdc]; hdc
0x18013eb08  call    cs:__imp_SetBkMode
0x18013eb0e  mov     rax, [rbp+arg_0]
0x18013eb12  mov     rdx, [rax+10h]; h
0x18013eb16  mov     rcx, [rsp+100h+hdc]; hdc
0x18013eb1b  call    cs:__imp_SelectObject
0x18013eb21  mov     [rsp+100h+var_90], rax
0x18013eb26  cmp     [rsp+100h+var_90], 0
0x18013eb2c  jnz     short loc_18013EB3A
0x18013eb2e  mov     [rsp+100h+var_AC], 8007000Eh
0x18013eb36  jmp     short loc_18013EBAD
0x18013eb38  jmp     short loc_18013EBAD
0x18013eb3a  mov     rax, [rbp+arg_0]
0x18013eb3e  mov     rax, [rax+30h]
0x18013eb42  mov     [rbp+var_70], rax
0x18013eb46  mov     [rsp+100h+var_98], 0FFFFFFFFFFFFFFFFh
0x18013eb4f  inc     [rsp+100h+var_98]
0x18013eb54  mov     rax, [rbp+var_70]
0x18013eb58  mov     rcx, [rsp+100h+var_98]
0x18013eb5d  cmp     byte ptr [rax+rcx], 0
0x18013eb61  jnz     short loc_18013EB4F
0x18013eb63  mov     rax, [rsp+100h+var_98]
0x18013eb68  mov     rcx, rax; unsigned __int64
0x18013eb6b  call    ?UINT32FromUINT64@@YAI_K@Z; UINT32FromUINT64(unsigned __int64)
0x18013eb70  mov     [rsp+100h+lpDx], 0; lpDx
0x18013eb79  mov     [rsp+100h+c], eax; c
0x18013eb7d  mov     rax, [rbp+arg_0]
0x18013eb81  mov     rax, [rax+30h]
0x18013eb85  mov     [rsp+100h+lpString], rax; lpString
0x18013eb8a  lea     rax, [rbp+x]
0x18013eb8e  mov     [rsp+100h+lprect], rax; lprect
0x18013eb93  mov     r9d, 4; options
0x18013eb99  mov     r8d, [rsp+100h+y]; y
0x18013eb9e  mov     edx, [rsp+100h+var_C0]; x
0x18013eba2  mov     rcx, [rsp+100h+hdc]; hdc
0x18013eba7  call    cs:__imp_ExtTextOutA
0x18013ebad  cmp     [rsp+100h+var_90], 0
0x18013ebb3  jz      short loc_18013EBC5
0x18013ebb5  mov     rdx, [rsp+100h+var_90]; h
0x18013ebba  mov     rcx, [rsp+100h+hdc]; hdc
0x18013ebbf  call    cs:__imp_SelectObject
0x18013ebc5  cmp     [rsp+100h+var_88], 0
0x18013ebcb  jz      short loc_18013EBDD
0x18013ebcd  mov     rdx, [rsp+100h+var_88]; h
0x18013ebd2  mov     rcx, [rsp+100h+hdc]; hdc
0x18013ebd7  call    cs:__imp_SelectObject
0x18013ebdd  cmp     [rsp+100h+h], 0
0x18013ebe3  jz      short loc_18013EBF0
0x18013ebe5  mov     rcx, [rsp+100h+h]; ho
0x18013ebea  call    cs:__imp_DeleteObject
0x18013ebf0  mov     rcx, [rbp+var_8]
0x18013ebf4  xor     rcx, rsp; StackCookie
0x18013ebf7  call    __security_check_cookie
0x18013ebfc  add     rsp, 100h
0x18013ec03  pop     rbp
0x18013ec04  retn
```
