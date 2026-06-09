# InitializeObjBrwResources

- ea: `0x180204878`
- end: `0x180204bac`
- name: `InitializeObjBrwResources`
- size: `820`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1802036b4`

## callees

- `0x180017944`
- `0x1800e15d0`
- `0x180105a74`
- `0x18010682c`
- `0x1801a903c`
- `0x180204878`
- `0x180285c88`
- `0x180379520`
- `0x180379546`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x1802049b6`
- `MSVCR100!strcpy_s` at `0x1802049b6`
- `KERNEL32!MulDiv` at `0x18020499b`
- `KERNEL32!MulDiv` at `0x18020499b`
- `USER32!LoadCursorA` at `0x180204abe`
- `USER32!LoadCursorA` at `0x180204abe`
- `USER32!GetDC` at `0x1802048bc`
- `USER32!GetDC` at `0x1802048bc`
- `USER32!ReleaseDC` at `0x180204b7b`
- `USER32!ReleaseDC` at `0x180204b7b`
- `USER32!GetSysColor` at `0x180204a25`
- `USER32!GetSysColor` at `0x180204a3f`
- `USER32!GetSysColor` at `0x180204a25`
- `USER32!GetSysColor` at `0x180204a3f`
- `GDI32!GetTextMetricsA` at `0x180204a77`
- `GDI32!GetTextMetricsA` at `0x180204a77`
- `GDI32!SelectObject` at `0x180204a5e`
- `GDI32!SelectObject` at `0x180204b69`
- `GDI32!SelectObject` at `0x180204a5e`
- `GDI32!SelectObject` at `0x180204b69`
- `GDI32!CreateFontIndirectA` at `0x1802049c8`
- `GDI32!CreateFontIndirectA` at `0x1802049e9`
- `GDI32!CreateFontIndirectA` at `0x180204a0a`
- `GDI32!CreateFontIndirectA` at `0x1802049c8`
- `GDI32!CreateFontIndirectA` at `0x1802049e9`
- `GDI32!CreateFontIndirectA` at `0x180204a0a`
- `GDI32!CreateSolidBrush` at `0x180204a2d`
- `GDI32!CreateSolidBrush` at `0x180204a47`
- `GDI32!CreateSolidBrush` at `0x180204a2d`
- `GDI32!CreateSolidBrush` at `0x180204a47`

## pseudocode

```c
__int64 InitializeObjBrwResources()
{
  HDC DC; // rdi
  int FontNameAndHeightOfStrid; // ebx
  unsigned int v2; // esi
  __int64 *v3; // rbx
  struct BLTTER **Bltter; // rax
  int v5; // eax
  COLORREF SysColor; // eax
  COLORREF v7; // eax
  HGDIOBJ v8; // rsi
  LONG tmExternalLeading; // eax
  HCURSOR CursorA; // rax
  unsigned int v11; // ecx
  int *v12; // rdx
  int v13; // r8d
  __int64 v14; // rax
  __int64 v15; // r8
  _QWORD v17[2]; // [rsp+28h] [rbp-89h] BYREF
  int v18; // [rsp+3Ch] [rbp-75h]
  __int64 v19; // [rsp+40h] [rbp-71h]
  HCURSOR v20; // [rsp+50h] [rbp-61h]
  const char *v21; // [rsp+68h] [rbp-49h]
  LOGFONTA lf; // [rsp+78h] [rbp-39h] BYREF
  struct tagTEXTMETRICA tm; // [rsp+B8h] [rbp+7h] BYREF

  DC = 0;
  FontNameAndHeightOfStrid = EnsureComctlInit();
  if ( FontNameAndHeightOfStrid >= 0 )
  {
    DC = GetDC(0);
    if ( DC )
    {
      v2 = 0;
      v3 = qword_1803F5350;
      while ( 1 )
      {
        Bltter = (struct BLTTER **)CreateBltter(*((unsigned __int16 *)v3 + 2), 0);
        (&g_rgpbltter)[*(int *)v3] = Bltter;
        if ( !Bltter )
          break;
        ++v2;
        ++v3;
        if ( v2 >= 0xD )
        {
          qword_1803FF760 = (struct BLTTER *)CreateBltter(1126, 0);
          if ( !qword_1803FF760 )
            break;
          memset_0(&lf, 0, sizeof(lf));
          FontNameAndHeightOfStrid = GetFontNameAndHeightOfStrid(0xDEDDu, 0xDEDEu, &qword_1803FF728, &nNumber);
          if ( FontNameAndHeightOfStrid >= 0 )
          {
            FontNameAndHeightOfStrid = GetFontNameAndHeightOfStrid(0xDEDDu, 0xDF27u, 0, &dword_1803FF780);
            if ( FontNameAndHeightOfStrid >= 0 )
            {
              lf.lfCharSet = GetCharset();
              v5 = DPIMGR::DpiY((DPIMGR *)g_dpiMgr);
              lf.lfHeight = -MulDiv(nNumber, v5, 72);
              strcpy_s(lf.lfFaceName, 0x20u, qword_1803FF728);
              lf.lfWeight = 400;
              qword_1803FF768 = CreateFontIndirectA(&lf);
              if ( !qword_1803FF768 )
                break;
              lf.lfWeight = 700;
              qword_1803FF770 = (__int64)CreateFontIndirectA(&lf);
              if ( !qword_1803FF770 )
                break;
              lf.lfWeight = 400;
              lf.lfStrikeOut = 1;
              qword_1803FF778 = (__int64)CreateFontIndirectA(&lf);
              if ( !qword_1803FF778 )
                break;
              SysColor = GetSysColor(13);
              qword_1803FF788 = (__int64)CreateSolidBrush(SysColor);
              v7 = GetSysColor(5);
              qword_1803FF790 = (__int64)CreateSolidBrush(v7);
              v8 = SelectObject(DC, qword_1803FF768);
              if ( !v8 )
                break;
              if ( !GetTextMetricsA(DC, &tm) )
                goto LABEL_17;
              tmExternalLeading = 2;
              if ( tm.tmExternalLeading > 2 )
                tmExternalLeading = tm.tmExternalLeading;
              dword_1803FF784 = tm.tmHeight + tmExternalLeading;
              dword_1803FF798 = tm.tmHeight + tmExternalLeading + 3;
              memset_0(v17, 0, 0x48u);
              LODWORD(v17[0]) = 11;
              CursorA = LoadCursorA(0, (LPCSTR)0x7F00);
              v18 = 8;
              v20 = CursorA;
              v19 = qword_1803FDC28;
              v17[1] = ObPaneWndProc;
              v21 = "ObPaneWndClass";
              if ( (unsigned __int16)IsolationAwareRegisterClassA(v17) )
              {
                v11 = 0;
                v12 = &dword_1803BA354;
                do
                {
                  v13 = *(v12 - 1);
                  if ( v13 )
                  {
                    if ( v13 == 1 )
                    {
                      *((_DWORD *)&c_rgiTabstopOfObtbctl + *v12) = v11;
                      if ( !*v12 )
                        dword_1803FF690 = v11;
                    }
                  }
                  else
                  {
                    v14 = *v12;
                    v15 = dword_1803BA328[v14];
                    *(&c_rgiTabstopOfObjpane + v14) = v11;
                    if ( (int)v15 < 7 )
                      *((_DWORD *)&c_rgiTabstopOfBrwkind + v15) = v11;
                  }
                  ++v11;
                  v12 += 2;
                }
                while ( v11 < 0xD );
              }
              else
              {
LABEL_17:
                FontNameAndHeightOfStrid = -2147024882;
              }
              SelectObject(DC, v8);
            }
          }
          goto LABEL_28;
        }
      }
    }
    FontNameAndHeightOfStrid = -2147024882;
  }
LABEL_28:
  ReleaseDC(0, DC);
  return (unsigned int)FontNameAndHeightOfStrid;
}

```

## disassembly

```asm
0x180204878  mov     rax, rsp
0x18020487b  mov     [rax+8], rbx
0x18020487f  mov     [rax+10h], rsi
0x180204883  mov     [rax+18h], rdi
0x180204887  push    rbp
0x180204888  push    r14
0x18020488a  push    r15
0x18020488c  lea     rbp, [rax-5Fh]
0x180204890  sub     rsp, 0F0h
0x180204897  mov     rax, cs:__security_cookie
0x18020489e  xor     rax, rsp
0x1802048a1  mov     [rbp+57h+var_18], rax
0x1802048a5  xor     r14d, r14d
0x1802048a8  mov     edi, r14d
0x1802048ab  call    ?EnsureComctlInit@@YAJXZ; EnsureComctlInit(void)
0x1802048b0  mov     ebx, eax
0x1802048b2  test    eax, eax
0x1802048b4  js      loc_180204B76
0x1802048ba  xor     ecx, ecx; hWnd
0x1802048bc  call    cs:__imp_GetDC
0x1802048c2  mov     rdi, rax
0x1802048c5  test    rax, rax
0x1802048c8  jz      loc_180204B71
0x1802048ce  mov     esi, r14d
0x1802048d1  lea     rbx, qword_1803F5350
0x1802048d8  lea     r15, cs:180000000h
0x1802048df  movzx   ecx, word ptr [rbx+4]
0x1802048e3  xor     edx, edx
0x1802048e5  call    ?CreateBltter@@YAPEAVBLTTER@@GW4BLT_KIND@@@Z; CreateBltter(ushort,BLT_KIND)
0x1802048ea  movsxd  rcx, dword ptr [rbx]
0x1802048ed  mov     rva ?g_rgpbltter@@3PAPEAVBLTTER@@A[r15+rcx*8], rax; BLTTER * near * g_rgpbltter ...
0x1802048f5  test    rax, rax
0x1802048f8  jz      loc_180204B71
0x1802048fe  inc     esi
0x180204900  add     rbx, 8
0x180204904  cmp     esi, 0Dh
0x180204907  jb      short loc_1802048DF
0x180204909  mov     ecx, 466h
0x18020490e  xor     edx, edx
0x180204910  call    ?CreateBltter@@YAPEAVBLTTER@@GW4BLT_KIND@@@Z; CreateBltter(ushort,BLT_KIND)
0x180204915  mov     cs:qword_1803FF760, rax
0x18020491c  test    rax, rax
0x18020491f  jz      loc_180204B71
0x180204925  xor     edx, edx; Val
0x180204927  lea     rcx, [rbp+57h+lf]; void *
0x18020492b  lea     r8d, [rdx+3Ch]; Size
0x18020492f  call    memset_0
0x180204934  mov     edx, 0DEDEh; unsigned int
0x180204939  lea     r9, nNumber; int *
0x180204940  lea     esi, [rdx-1]
0x180204943  lea     r8, qword_1803FF728; char **
0x18020494a  mov     ecx, esi; unsigned int
0x18020494c  call    ?GetFontNameAndHeightOfStrid@@YAJIIPEAPEADPEAH@Z; GetFontNameAndHeightOfStrid(uint,uint,char * *,int *)
0x180204951  mov     ebx, eax
0x180204953  test    eax, eax
0x180204955  js      loc_180204B76
0x18020495b  lea     r9, dword_1803FF780; int *
0x180204962  lea     edx, [rsi+4Ah]; unsigned int
0x180204965  xor     r8d, r8d; char **
0x180204968  mov     ecx, esi; unsigned int
0x18020496a  call    ?GetFontNameAndHeightOfStrid@@YAJIIPEAPEADPEAH@Z; GetFontNameAndHeightOfStrid(uint,uint,char * *,int *)
0x18020496f  mov     ebx, eax
0x180204971  test    eax, eax
0x180204973  js      loc_180204B76
0x180204979  call    ?GetCharset@@YAEXZ; GetCharset(void)
0x18020497e  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x180204985  mov     [rbp+57h+lf.lfCharSet], al
0x180204988  call    ?DpiY@DPIMGR@@QEAAIXZ; DPIMGR::DpiY(void)
0x18020498d  mov     ecx, cs:nNumber; nNumber
0x180204993  mov     edx, eax; nNumerator
0x180204995  mov     r8d, 48h ; 'H'; nDenominator
0x18020499b  call    cs:__imp_MulDiv
0x1802049a1  mov     r8, cs:qword_1803FF728; Source
0x1802049a8  lea     rcx, [rbp+57h+lf.lfFaceName]; Destination
0x1802049ac  neg     eax
0x1802049ae  mov     edx, 20h ; ' '; SizeInBytes
0x1802049b3  mov     [rbp+57h+lf.lfHeight], eax
0x1802049b6  call    cs:__imp_strcpy_s
0x1802049bc  lea     rcx, [rbp+57h+lf]; lplf
0x1802049c0  mov     esi, 190h
0x1802049c5  mov     [rbp+57h+lf.lfWeight], esi
0x1802049c8  call    cs:__imp_CreateFontIndirectA
0x1802049ce  mov     cs:qword_1803FF768, rax
0x1802049d5  test    rax, rax
0x1802049d8  jz      loc_180204B71
0x1802049de  lea     rcx, [rbp+57h+lf]; lplf
0x1802049e2  mov     [rbp+57h+lf.lfWeight], 2BCh
0x1802049e9  call    cs:__imp_CreateFontIndirectA
0x1802049ef  mov     cs:qword_1803FF770, rax
0x1802049f6  test    rax, rax
0x1802049f9  jz      loc_180204B71
0x1802049ff  lea     rcx, [rbp+57h+lf]; lplf
0x180204a03  mov     [rbp+57h+lf.lfWeight], esi
0x180204a06  mov     [rbp+57h+lf.lfStrikeOut], 1
0x180204a0a  call    cs:__imp_CreateFontIndirectA
0x180204a10  mov     cs:qword_1803FF778, rax
0x180204a17  test    rax, rax
0x180204a1a  jz      loc_180204B71
0x180204a20  mov     ecx, 0Dh; nIndex
0x180204a25  call    cs:__imp_GetSysColor
0x180204a2b  mov     ecx, eax; color
0x180204a2d  call    cs:__imp_CreateSolidBrush
0x180204a33  mov     ecx, 5; nIndex
0x180204a38  mov     cs:qword_1803FF788, rax
0x180204a3f  call    cs:__imp_GetSysColor
0x180204a45  mov     ecx, eax; color
0x180204a47  call    cs:__imp_CreateSolidBrush
0x180204a4d  mov     rdx, cs:qword_1803FF768; h
0x180204a54  mov     rcx, rdi; hdc
0x180204a57  mov     cs:qword_1803FF790, rax
0x180204a5e  call    cs:__imp_SelectObject
0x180204a64  mov     rsi, rax
0x180204a67  test    rax, rax
0x180204a6a  jz      loc_180204B71
0x180204a70  lea     rdx, [rbp+57h+tm]; lptm
0x180204a74  mov     rcx, rdi; hdc
0x180204a77  call    cs:__imp_GetTextMetricsA
0x180204a7d  test    eax, eax
0x180204a7f  jz      short loc_180204B00
0x180204a81  mov     eax, 2
0x180204a86  lea     rcx, [rsp+100h+var_E0]; void *
0x180204a8b  cmp     [rbp+57h+tm.tmExternalLeading], eax
0x180204a8e  cmovg   eax, [rbp+57h+tm.tmExternalLeading]
0x180204a92  xor     edx, edx; Val
0x180204a94  add     eax, [rbp+57h+tm.tmHeight]
0x180204a97  lea     r8d, [rdx+48h]; Size
0x180204a9b  mov     cs:dword_1803FF784, eax
0x180204aa1  add     eax, 3
0x180204aa4  mov     cs:dword_1803FF798, eax
0x180204aaa  call    memset_0
0x180204aaf  mov     edx, 7F00h; lpCursorName
0x180204ab4  xor     ecx, ecx; hInstance
0x180204ab6  mov     dword ptr [rsp+100h+var_E0], 0Bh
0x180204abe  call    cs:__imp_LoadCursorA
0x180204ac4  lea     rcx, [rsp+100h+var_E0]
0x180204ac9  mov     [rbp+57h+var_CC], 8
0x180204ad0  mov     [rbp+57h+var_B8], rax
0x180204ad4  mov     rax, cs:qword_1803FDC28
0x180204adb  mov     [rbp+57h+var_C8], rax
0x180204adf  lea     rax, ObPaneWndProc
0x180204ae6  mov     [rsp+100h+var_D8], rax
0x180204aeb  lea     rax, aObpanewndclass; "ObPaneWndClass"
0x180204af2  mov     [rbp+57h+var_A0], rax
0x180204af6  call    IsolationAwareRegisterClassA
0x180204afb  test    ax, ax
0x180204afe  jnz     short loc_180204B07
0x180204b00  mov     ebx, 8007000Eh
0x180204b05  jmp     short loc_180204B63
0x180204b07  mov     ecx, r14d
0x180204b0a  lea     rdx, dword_1803BA354
0x180204b11  mov     r8d, [rdx-4]
0x180204b15  test    r8d, r8d
0x180204b18  jz      short loc_180204B37
0x180204b1a  dec     r8d
0x180204b1d  jnz     short loc_180204B58
0x180204b1f  movsxd  rax, dword ptr [rdx]
0x180204b22  mov     rva ?c_rgiTabstopOfObtbctl@@3PAIA[r15+rax*4], ecx; uint near * c_rgiTabstopOfObtbctl ...
0x180204b2a  cmp     [rdx], r14d
0x180204b2d  jnz     short loc_180204B58
0x180204b2f  mov     cs:dword_1803FF690, ecx
0x180204b35  jmp     short loc_180204B58
0x180204b37  movsxd  rax, dword ptr [rdx]
0x180204b3a  movsxd  r8, ds:rva dword_1803BA328[r15+rax*4]
0x180204b42  mov     rva ?c_rgiTabstopOfObjpane@@3PAIA[r15+rax*4], ecx; uint near * c_rgiTabstopOfObjpane ...
0x180204b4a  cmp     r8d, 7
0x180204b4e  jge     short loc_180204B58
0x180204b50  mov     rva ?c_rgiTabstopOfBrwkind@@3PAIA[r15+r8*4], ecx; uint near * c_rgiTabstopOfBrwkind ...
0x180204b58  inc     ecx
0x180204b5a  add     rdx, 8
0x180204b5e  cmp     ecx, 0Dh
0x180204b61  jb      short loc_180204B11
0x180204b63  mov     rdx, rsi; h
0x180204b66  mov     rcx, rdi; hdc
0x180204b69  call    cs:__imp_SelectObject
0x180204b6f  jmp     short loc_180204B76
0x180204b71  mov     ebx, 8007000Eh
0x180204b76  mov     rdx, rdi; hDC
0x180204b79  xor     ecx, ecx; hWnd
0x180204b7b  call    cs:__imp_ReleaseDC
0x180204b81  mov     eax, ebx
0x180204b83  mov     rcx, [rbp+57h+var_18]
0x180204b87  xor     rcx, rsp; StackCookie
0x180204b8a  call    __security_check_cookie
0x180204b8f  lea     r11, [rsp+100h+var_10]
0x180204b97  mov     rbx, [r11+20h]
0x180204b9b  mov     rsi, [r11+28h]
0x180204b9f  mov     rdi, [r11+30h]
0x180204ba3  mov     rsp, r11
0x180204ba6  pop     r15
0x180204ba8  pop     r14
0x180204baa  pop     rbp
0x180204bab  retn
```
