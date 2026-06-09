# xgc::CGDIPathData::Fill(std::shared_ptr<IXpsOMSolidColorBrush> const &)

- ea: `0x1800300b8`
- end: `0x18003027c`
- name: `?Fill@CGDIPathData@xgc@@AEBAXAEBV?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@@Z`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180030284`

## callees

- `0x180009de0`
- `0x1800300b8`
- `0x180031de0`
- `0x180032a94`
- `0x180037278`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003011a`
- `KERNEL32!GetLastError` at `0x180030158`
- `KERNEL32!GetLastError` at `0x180030198`
- `KERNEL32!GetLastError` at `0x1800301de`
- `KERNEL32!GetLastError` at `0x180030215`
- `KERNEL32!GetLastError` at `0x18003024c`
- `KERNEL32!GetLastError` at `0x18003011a`
- `KERNEL32!GetLastError` at `0x180030158`
- `KERNEL32!GetLastError` at `0x180030198`
- `KERNEL32!GetLastError` at `0x1800301de`
- `KERNEL32!GetLastError` at `0x180030215`
- `KERNEL32!GetLastError` at `0x18003024c`
- `GDI32!GetPolyFillMode` at `0x180030110`
- `GDI32!GetPolyFillMode` at `0x180030110`
- `GDI32!FillPath` at `0x180030242`
- `GDI32!FillPath` at `0x180030242`
- `GDI32!BeginPath` at `0x18003018e`
- `GDI32!BeginPath` at `0x18003018e`
- `GDI32!PolyDraw` at `0x1800301d4`
- `GDI32!PolyDraw` at `0x1800301d4`
- `GDI32!SetPolyFillMode` at `0x18003014e`
- `GDI32!SetPolyFillMode` at `0x18003014e`
- `GDI32!EndPath` at `0x18003020b`
- `GDI32!EndPath` at `0x18003020b`

## pseudocode

```c
BOOL __fastcall xgc::CGDIPathData::Fill(__int64 a1, __int64 a2)
{
  int PolyFillMode; // eax
  signed int LastError; // eax
  int v6; // edx
  const char *v7; // r8
  int v8; // r9d
  __int64 v9; // rcx
  int v10; // edx
  signed int v11; // eax
  int v12; // edx
  const char *v13; // r8
  int v14; // r9d
  __int64 v15; // rcx
  signed int v16; // eax
  int v17; // edx
  const char *v18; // r8
  int v19; // r9d
  __int64 v20; // rcx
  signed int v21; // eax
  int v22; // edx
  const char *v23; // r8
  int v24; // r9d
  __int64 v25; // rcx
  signed int v26; // eax
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  __int64 v30; // rcx
  BOOL result; // eax
  signed int v32; // eax
  int v33; // edx
  const char *v34; // r8
  int v35; // r9d
  __int64 v36; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 12, WPP_00624022ad39391a483a764a1c0090f0_Traceguids);
  xgc::CDeviceContext::SelectBrush(*(_QWORD *)(a1 + 16), a2);
  PolyFillMode = GetPolyFillMode(*(HDC *)(*(_QWORD *)(a1 + 16) + 32LL));
  if ( !PolyFillMode )
  {
    LastError = GetLastError();
    v9 = (unsigned int)LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (int)v9 >= 0 )
      v9 = 2147500037LL;
    xpsrdr::ThrowHRException((xpsrdr *)v9, v6, v7, v8);
  }
  v10 = *(_DWORD *)(a1 + 96);
  if ( PolyFillMode != v10 && !SetPolyFillMode(*(HDC *)(*(_QWORD *)(a1 + 16) + 32LL), v10) )
  {
    v11 = GetLastError();
    v15 = (unsigned int)v11;
    if ( v11 > 0 )
      v15 = (unsigned __int16)v11 | 0x80070000;
    if ( (int)v15 >= 0 )
      v15 = 2147500037LL;
    xpsrdr::ThrowHRException((xpsrdr *)v15, v12, v13, v14);
  }
  xgc::CDeviceContext::SelectPen(*(xgc::CDeviceContext **)(a1 + 16));
  if ( !BeginPath(*(HDC *)(*(_QWORD *)(a1 + 16) + 32LL)) )
  {
    v16 = GetLastError();
    v20 = (unsigned int)v16;
    if ( v16 > 0 )
      v20 = (unsigned __int16)v16 | 0x80070000;
    if ( (int)v20 >= 0 )
      v20 = 2147500037LL;
    xpsrdr::ThrowHRException((xpsrdr *)v20, v17, v18, v19);
  }
  if ( !PolyDraw(
          *(HDC *)(*(_QWORD *)(a1 + 16) + 32LL),
          *(const POINT **)(a1 + 40),
          *(const BYTE **)(a1 + 64),
          *(_DWORD *)(a1 + 72) - *(_QWORD *)(a1 + 64)) )
  {
    v21 = GetLastError();
    v25 = (unsigned int)v21;
    if ( v21 > 0 )
      v25 = (unsigned __int16)v21 | 0x80070000;
    if ( (int)v25 >= 0 )
      v25 = 2147500037LL;
    xpsrdr::ThrowHRException((xpsrdr *)v25, v22, v23, v24);
  }
  if ( !EndPath(*(HDC *)(*(_QWORD *)(a1 + 16) + 32LL)) )
  {
    v26 = GetLastError();
    v30 = (unsigned int)v26;
    if ( v26 > 0 )
      v30 = (unsigned __int16)v26 | 0x80070000;
    if ( (int)v30 >= 0 )
      v30 = 2147500037LL;
    xpsrdr::ThrowHRException((xpsrdr *)v30, v27, v28, v29);
  }
  result = FillPath(*(HDC *)(*(_QWORD *)(a1 + 16) + 32LL));
  if ( !result )
  {
    v32 = GetLastError();
    v36 = (unsigned int)v32;
    if ( v32 > 0 )
      v36 = (unsigned __int16)v32 | 0x80070000;
    if ( (int)v36 >= 0 )
      v36 = 2147500037LL;
    xpsrdr::ThrowHRException((xpsrdr *)v36, v33, v34, v35);
  }
  return result;
}

```

## disassembly

```asm
0x1800300b8  mov     [rsp+arg_0], rbx
0x1800300bd  push    rdi
0x1800300be  sub     rsp, 20h
0x1800300c2  mov     rdi, rdx
0x1800300c5  mov     rbx, rcx
0x1800300c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300cf  lea     rax, WPP_GLOBAL_Control
0x1800300d6  cmp     rcx, rax
0x1800300d9  jz      short loc_1800300FC
0x1800300db  test    byte ptr [rcx+0E4h], 8
0x1800300e2  jz      short loc_1800300FC
0x1800300e4  mov     rcx, [rcx+0D8h]
0x1800300eb  lea     r8, WPP_00624022ad39391a483a764a1c0090f0_Traceguids
0x1800300f2  mov     edx, 0Ch
0x1800300f7  call    WPP_SF_
0x1800300fc  mov     rcx, [rbx+10h]
0x180030100  mov     rdx, rdi
0x180030103  call    ?SelectBrush@CDeviceContext@xgc@@QEAAXAEBV?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@@Z; xgc::CDeviceContext::SelectBrush(std::shared_ptr<IXpsOMSolidColorBrush> const &)
0x180030108  mov     rcx, [rbx+10h]
0x18003010c  mov     rcx, [rcx+20h]; hdc
0x180030110  call    cs:__imp_GetPolyFillMode
0x180030116  test    eax, eax
0x180030118  jnz     short loc_18003013F
0x18003011a  call    cs:__imp_GetLastError
0x180030120  mov     ecx, eax
0x180030122  test    eax, eax
0x180030124  jle     short loc_18003012F
0x180030126  movzx   ecx, ax
0x180030129  or      ecx, 80070000h
0x18003012f  test    ecx, ecx
0x180030131  mov     eax, 80004005h
0x180030136  cmovns  ecx, eax; this
0x180030139  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003013f  mov     edx, [rbx+60h]; mode
0x180030142  cmp     eax, edx
0x180030144  jz      short loc_18003017D
0x180030146  mov     rcx, [rbx+10h]
0x18003014a  mov     rcx, [rcx+20h]; hdc
0x18003014e  call    cs:__imp_SetPolyFillMode
0x180030154  test    eax, eax
0x180030156  jnz     short loc_18003017D
0x180030158  call    cs:__imp_GetLastError
0x18003015e  mov     ecx, eax
0x180030160  test    eax, eax
0x180030162  jle     short loc_18003016D
0x180030164  movzx   ecx, ax
0x180030167  or      ecx, 80070000h
0x18003016d  test    ecx, ecx
0x18003016f  mov     eax, 80004005h
0x180030174  cmovns  ecx, eax; this
0x180030177  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003017d  mov     rcx, [rbx+10h]; this
0x180030181  call    ?SelectPen@CDeviceContext@xgc@@QEAAXXZ; xgc::CDeviceContext::SelectPen(void)
0x180030186  mov     rcx, [rbx+10h]
0x18003018a  mov     rcx, [rcx+20h]; hdc
0x18003018e  call    cs:__imp_BeginPath
0x180030194  test    eax, eax
0x180030196  jnz     short loc_1800301BD
0x180030198  call    cs:__imp_GetLastError
0x18003019e  mov     ecx, eax
0x1800301a0  test    eax, eax
0x1800301a2  jle     short loc_1800301AD
0x1800301a4  movzx   ecx, ax
0x1800301a7  or      ecx, 80070000h
0x1800301ad  test    ecx, ecx
0x1800301af  mov     eax, 80004005h
0x1800301b4  cmovns  ecx, eax; this
0x1800301b7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800301bd  mov     rcx, [rbx+10h]
0x1800301c1  mov     r8, [rbx+40h]; aj
0x1800301c5  mov     r9d, [rbx+48h]
0x1800301c9  mov     rdx, [rbx+28h]; apt
0x1800301cd  sub     r9d, r8d; cpt
0x1800301d0  mov     rcx, [rcx+20h]; hdc
0x1800301d4  call    cs:__imp_PolyDraw
0x1800301da  test    eax, eax
0x1800301dc  jnz     short loc_180030203
0x1800301de  call    cs:__imp_GetLastError
0x1800301e4  mov     ecx, eax
0x1800301e6  test    eax, eax
0x1800301e8  jle     short loc_1800301F3
0x1800301ea  movzx   ecx, ax
0x1800301ed  or      ecx, 80070000h
0x1800301f3  test    ecx, ecx
0x1800301f5  mov     eax, 80004005h
0x1800301fa  cmovns  ecx, eax; this
0x1800301fd  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180030203  mov     rcx, [rbx+10h]
0x180030207  mov     rcx, [rcx+20h]; hdc
0x18003020b  call    cs:__imp_EndPath
0x180030211  test    eax, eax
0x180030213  jnz     short loc_18003023A
0x180030215  call    cs:__imp_GetLastError
0x18003021b  mov     ecx, eax
0x18003021d  test    eax, eax
0x18003021f  jle     short loc_18003022A
0x180030221  movzx   ecx, ax
0x180030224  or      ecx, 80070000h
0x18003022a  test    ecx, ecx
0x18003022c  mov     eax, 80004005h
0x180030231  cmovns  ecx, eax; this
0x180030234  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003023a  mov     rcx, [rbx+10h]
0x18003023e  mov     rcx, [rcx+20h]; hdc
0x180030242  call    cs:__imp_FillPath
0x180030248  test    eax, eax
0x18003024a  jnz     short loc_180030271
0x18003024c  call    cs:__imp_GetLastError
0x180030252  mov     ecx, eax
0x180030254  test    eax, eax
0x180030256  jle     short loc_180030261
0x180030258  movzx   ecx, ax
0x18003025b  or      ecx, 80070000h
0x180030261  test    ecx, ecx
0x180030263  mov     eax, 80004005h
0x180030268  cmovns  ecx, eax; this
0x18003026b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180030271  mov     rbx, [rsp+28h+arg_0]
0x180030276  add     rsp, 20h
0x18003027a  pop     rdi
0x18003027b  retn
```
