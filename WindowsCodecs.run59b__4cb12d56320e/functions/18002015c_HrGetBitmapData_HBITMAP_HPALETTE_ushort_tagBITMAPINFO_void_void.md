# HrGetBitmapData(HBITMAP__ *,HPALETTE__ *,ushort,tagBITMAPINFO * *,void * *,void * *)

- ea: `0x18002015c`
- end: `0x180020656`
- name: `?HrGetBitmapData@@YAJPEAUHBITMAP__@@PEAUHPALETTE__@@GPEAPEAUtagBITMAPINFO@@PEAPEAX3@Z`
- size: `1274`
- prototype: `int(HBITMAP, HPALETTE, unsigned __int16, struct tagBITMAPINFO **, void **, void **)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001e7b8`
- `0x18001f244`
- `0x18001fe10`
- `0x1800c7f24`

## callees

- `0x18002015c`
- `0x1800bd9d4`
- `0x1800cbf54`
- `0x1800cc0d4`
- `0x1800e6af4`
- `0x18017dc8c`
- `0x18017dd80`
- `0x18017df54`
- `0x18017e438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800204fd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020515`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800204fd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020515`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800201fc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020310`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002048f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800201fc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020310`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002048f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020183`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002023d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020183`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002023d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205a7`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800203e3`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800203e3`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1800201ae`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1800201ae`
- `ext-ms-win-gdi-dc-l1-2-0!GetPaletteEntries` at `0x180020534`
- `ext-ms-win-gdi-dc-l1-2-0!GetPaletteEntries` at `0x180020534`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x180020269`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x180020391`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x180020269`
- `ext-ms-win-gdi-draw-l1-1-0!GetDIBits` at `0x180020391`

## pseudocode

```c
__int64 __fastcall HrGetBitmapData(
        HBITMAP a1,
        HPALETTE a2,
        unsigned __int16 biBitCount,
        struct tagBITMAPINFO **a4,
        void **a5,
        void **a6)
{
  UINT PaletteEntries; // r14d
  HDC CompatibleDC; // r13
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // ebx
  struct tagPALETTEENTRY *v13; // rbx
  struct tagBITMAPINFO *v14; // rax
  struct tagBITMAPINFO *lpbmi; // rdi
  void *v16; // r15
  int biHeight; // ecx
  unsigned int biWidth; // r8d
  int v19; // eax
  unsigned int v20; // r8d
  void *v21; // rax
  void *lpvBits; // rbp
  bool v24; // zf
  struct tagPALETTEENTRY *v25; // rax
  signed int v26; // eax
  signed int v27; // eax

  SetLastError(0);
  PaletteEntries = 0;
  if ( !(unsigned __int8)IsDeleteDCPresent() || !(unsigned __int8)IsDeleteDCPresent() )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147467263);
    return (unsigned int)-2147467263;
  }
  CompatibleDC = CreateCompatibleDC(0);
  if ( !CompatibleDC )
  {
    LastError = GetLastError();
    v11 = LastError < 0;
    if ( LastError > 0 )
      v11 = 1;
    if ( v11 )
    {
      v12 = CheckGdiHandlesNearLimit();
      if ( v12 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
        {
          DoStackCapture(v12);
          if ( (_DWORD)g_doStackCaptures )
            DoStackCapture(v12);
        }
        return (unsigned int)v12;
      }
    }
  }
  if ( a2 )
  {
    v25 = (struct tagPALETTEENTRY *)malloc(0x400u);
    v13 = v25;
    if ( v25 )
      memset_0(v25, 0, 0x400u);
    if ( !(unsigned __int8)IsGetObjectAPresent() )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147467263);
      v12 = -2147467263;
      goto LABEL_35;
    }
    PaletteEntries = GetPaletteEntries(a2, 0, 0x100u, v13);
  }
  else
  {
    v13 = 0;
  }
  v14 = (struct tagBITMAPINFO *)malloc(0x42Cu);
  lpbmi = v14;
  if ( v14 )
  {
    v16 = 0;
    memset_0(&v14->bmiHeader.biWidth, 0, 0x428u);
    lpbmi->bmiHeader.biSize = 40;
    if ( !(unsigned __int8)IsSetDIBitsPresent() )
      goto LABEL_66;
    SetLastError(0);
    if ( !GetDIBits(CompatibleDC, a1, 0, 0, 0, lpbmi, 0) )
    {
      v26 = GetLastError();
      v12 = v26;
      if ( v26 > 0 )
        v12 = (unsigned __int16)v26 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2003292268;
      v24 = (_DWORD)g_doStackCaptures == 0;
      goto LABEL_60;
    }
    if ( !biBitCount )
    {
      biBitCount = lpbmi->bmiHeader.biBitCount;
      if ( biBitCount )
        goto LABEL_15;
      biBitCount = 32;
    }
    lpbmi->bmiHeader.biBitCount = biBitCount;
LABEL_15:
    lpbmi->bmiHeader.biPlanes = 1;
    if ( a2 )
    {
      memcpy_0(lpbmi->bmiColors, v13, 4LL * PaletteEntries);
      if ( PaletteEntries > 2 )
      {
        if ( PaletteEntries > 0x10 )
        {
          if ( PaletteEntries <= 0x100 )
            lpbmi->bmiHeader.biBitCount = 8;
        }
        else
        {
          lpbmi->bmiHeader.biBitCount = 4;
        }
      }
      else
      {
        lpbmi->bmiHeader.biBitCount = 2;
      }
      biBitCount = lpbmi->bmiHeader.biBitCount;
    }
    else
    {
      lpbmi->bmiHeader.biCompression = 0;
    }
    biHeight = lpbmi->bmiHeader.biHeight;
    if ( biHeight > 0 )
    {
      biHeight = -biHeight;
      lpbmi->bmiHeader.biHeight = biHeight;
    }
    if ( biBitCount )
    {
      biWidth = lpbmi->bmiHeader.biWidth;
      if ( biWidth <= 0x7FFFFFF8u / biBitCount )
      {
        v19 = -biHeight;
        if ( biHeight > 0 )
          v19 = biHeight;
        if ( v19
          && (v20 = (((biBitCount * biWidth + 7) >> 3) + 3) & 0xFFFFFFFC) != 0
          && v20 < 0xFFFFFFFFFFFFFF7FuLL / v19 )
        {
          v21 = malloc(v19 * (unsigned __int64)v20 + 128);
          v16 = v21;
          if ( v21 )
          {
            v12 = 0;
            lpvBits = (void *)(((unsigned __int64)v21 + 127) & 0xFFFFFFFFFFFFFF80uLL);
            if ( (unsigned __int8)IsSetDIBitsPresent() )
            {
              if ( GetDIBits(CompatibleDC, a1, 0, -lpbmi->bmiHeader.biHeight, lpvBits, lpbmi, a2 != 0) )
                goto LABEL_34;
              v27 = GetLastError();
              v12 = v27;
              if ( v27 > 0 )
                v12 = (unsigned __int16)v27 | 0x80070000;
              if ( v12 >= 0 )
              {
LABEL_34:
                lpbmi->bmiHeader.biHeight = -lpbmi->bmiHeader.biHeight;
                *a4 = lpbmi;
                *a5 = lpvBits;
                *a6 = v16;
                goto LABEL_35;
              }
              if ( !(_DWORD)g_doStackCaptures )
                goto LABEL_62;
LABEL_61:
              DoStackCapture(v12);
LABEL_62:
              free(lpbmi);
              if ( v16 )
                free(v16);
              goto LABEL_35;
            }
LABEL_66:
            if ( (_DWORD)g_doStackCaptures )
              DoStackCapture(-2147467263);
            v12 = -2147467263;
            goto LABEL_62;
          }
          v12 = -2147024882;
        }
        else
        {
          v16 = 0;
          v12 = -2147024809;
        }
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v12);
        goto LABEL_62;
      }
    }
    v12 = -2147024362;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_62;
    DoStackCapture(-2147024362);
    v24 = (_DWORD)g_doStackCaptures == 0;
LABEL_60:
    if ( v24 )
      goto LABEL_62;
    goto LABEL_61;
  }
  v12 = -2147024882;
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(-2147024882);
LABEL_35:
  if ( !CompatibleDC )
    return (unsigned int)v12;
  if ( (unsigned __int8)IsDeleteDCPresent() )
  {
    DeleteDC(CompatibleDC);
    return (unsigned int)v12;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return 2147500033LL;
}

```

## disassembly

```asm
0x18002015c  mov     [rsp+arg_8], rbx
0x180020161  mov     [rsp+arg_18], r9
0x180020166  mov     [rsp+hbm], rcx
0x18002016b  push    rbp
0x18002016c  push    rsi
0x18002016d  push    rdi
0x18002016e  push    r12
0x180020170  push    r13
0x180020172  push    r14
0x180020174  push    r15
0x180020176  sub     rsp, 40h
0x18002017a  xor     ecx, ecx; dwErrCode
0x18002017c  movzx   ebp, r8w
0x180020180  mov     r12, rdx
0x180020183  call    cs:__imp_SetLastError
0x18002018a  nop     dword ptr [rax+rax+00h]
0x18002018f  call    IsDeleteDCPresent
0x180020194  xor     r14d, r14d
0x180020197  test    al, al
0x180020199  jz      loc_18002046C
0x18002019f  call    IsDeleteDCPresent
0x1800201a4  test    al, al
0x1800201a6  jz      loc_18002046C
0x1800201ac  xor     ecx, ecx; hdc
0x1800201ae  call    cs:__imp_CreateCompatibleDC
0x1800201b5  nop     dword ptr [rax+rax+00h]
0x1800201ba  mov     r13, rax
0x1800201bd  test    rax, rax
0x1800201c0  jnz     short loc_1800201E7
0x1800201c2  call    cs:__imp_GetLastError
0x1800201c9  nop     dword ptr [rax+rax+00h]
0x1800201ce  test    eax, eax
0x1800201d0  jg      loc_180020552
0x1800201d6  jns     short loc_1800201E7
0x1800201d8  call    ?CheckGdiHandlesNearLimit@@YAJXZ; CheckGdiHandlesNearLimit(void)
0x1800201dd  mov     ebx, eax
0x1800201df  test    eax, eax
0x1800201e1  js      loc_180020421
0x1800201e7  mov     esi, 80004001h
0x1800201ec  test    r12, r12
0x1800201ef  jnz     loc_180020488
0x1800201f5  xor     ebx, ebx
0x1800201f7  mov     ecx, 42Ch; Size
0x1800201fc  call    cs:__imp_malloc
0x180020203  nop     dword ptr [rax+rax+00h]
0x180020208  mov     rdi, rax
0x18002020b  test    rax, rax
0x18002020e  jz      loc_180020586
0x180020214  lea     rcx, [rax+4]; void *
0x180020218  xor     edx, edx; Val
0x18002021a  mov     r8d, 428h; Size
0x180020220  xor     r15d, r15d
0x180020223  call    memset_0
0x180020228  mov     dword ptr [rdi], 28h ; '('
0x18002022e  call    IsSetDIBitsPresent
0x180020233  test    al, al
0x180020235  jz      loc_1800205F6
0x18002023b  xor     ecx, ecx; dwErrCode
0x18002023d  call    cs:__imp_SetLastError
0x180020244  nop     dword ptr [rax+rax+00h]
0x180020249  mov     rdx, [rsp+78h+hbm]; hbm
0x180020251  xor     r9d, r9d; cLines
0x180020254  mov     [rsp+78h+usage], r15d; usage
0x180020259  xor     r8d, r8d; start
0x18002025c  mov     [rsp+78h+lpbmi], rdi; lpbmi
0x180020261  mov     rcx, r13; hdc
0x180020264  mov     [rsp+78h+lpvBits], r15; lpvBits
0x180020269  call    cs:__imp_GetDIBits
0x180020270  nop     dword ptr [rax+rax+00h]
0x180020275  test    eax, eax
0x180020277  jz      loc_1800204C7
0x18002027d  test    bp, bp
0x180020280  jz      loc_18002040A
0x180020286  mov     [rdi+0Eh], bp
0x18002028a  mov     word ptr [rdi+0Ch], 1
0x180020290  test    r12, r12
0x180020293  jnz     loc_1800205FE
0x180020299  xor     r14d, r14d
0x18002029c  mov     [rdi+10h], r14d
0x1800202a0  mov     ecx, [rdi+8]
0x1800202a3  test    ecx, ecx
0x1800202a5  jle     short loc_1800202AC
0x1800202a7  neg     ecx
0x1800202a9  mov     [rdi+8], ecx
0x1800202ac  movzx   r9d, bp
0x1800202b0  test    r9d, r9d
0x1800202b3  jz      loc_180020445
0x1800202b9  mov     r8d, [rdi+4]
0x1800202bd  xor     edx, edx
0x1800202bf  mov     eax, 7FFFFFF8h
0x1800202c4  div     r9d
0x1800202c7  cmp     r8d, eax
0x1800202ca  ja      loc_180020445
0x1800202d0  mov     eax, ecx
0x1800202d2  neg     eax
0x1800202d4  cmovs   eax, ecx
0x1800202d7  movsxd  r10, eax
0x1800202da  test    eax, eax
0x1800202dc  jz      short loc_180020335
0x1800202de  imul    r8d, r9d
0x1800202e2  add     r8d, 7
0x1800202e6  shr     r8d, 3
0x1800202ea  add     r8d, 3
0x1800202ee  and     r8d, 0FFFFFFFCh
0x1800202f2  jz      short loc_180020335
0x1800202f4  xor     edx, edx
0x1800202f6  mov     ecx, r8d
0x1800202f9  mov     rax, 0FFFFFFFFFFFFFF7Fh
0x180020300  div     r10
0x180020303  cmp     rcx, rax
0x180020306  jnb     short loc_180020335
0x180020308  imul    rcx, r10
0x18002030c  sub     rcx, 0FFFFFFFFFFFFFF80h; Size
0x180020310  call    cs:__imp_malloc
0x180020317  nop     dword ptr [rax+rax+00h]
0x18002031c  mov     r15, rax
0x18002031f  test    rax, rax
0x180020322  jz      loc_180020548
0x180020328  lea     rbp, [rax+7Fh]
0x18002032c  mov     ebx, r14d
0x18002032f  and     rbp, 0FFFFFFFFFFFFFF80h
0x180020333  jmp     short loc_180020358
0x180020335  mov     r15, r14
0x180020338  mov     ebx, 80070057h
0x18002033d  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180020344  mov     rbp, r14
0x180020347  jz      short loc_180020350
0x180020349  mov     ecx, ebx; int
0x18002034b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020350  test    ebx, ebx
0x180020352  js      loc_1800204FA
0x180020358  call    IsSetDIBitsPresent
0x18002035d  test    al, al
0x18002035f  jz      loc_18002056F
0x180020365  mov     r9d, [rdi+8]
0x180020369  mov     eax, r14d
0x18002036c  mov     rdx, [rsp+78h+hbm]; hbm
0x180020374  test    r12, r12
0x180020377  mov     rcx, r13; hdc
0x18002037a  setnz   al
0x18002037d  neg     r9d; cLines
0x180020380  mov     [rsp+78h+usage], eax; usage
0x180020384  xor     r8d, r8d; start
0x180020387  mov     [rsp+78h+lpbmi], rdi; lpbmi
0x18002038c  mov     [rsp+78h+lpvBits], rbp; lpvBits
0x180020391  call    cs:__imp_GetDIBits
0x180020398  nop     dword ptr [rax+rax+00h]
0x18002039d  test    eax, eax
0x18002039f  jz      loc_1800205A7
0x1800203a5  mov     eax, [rdi+8]
0x1800203a8  neg     eax
0x1800203aa  mov     [rdi+8], eax
0x1800203ad  mov     rax, [rsp+78h+arg_18]
0x1800203b5  mov     [rax], rdi
0x1800203b8  mov     rax, [rsp+78h+arg_20]
0x1800203c0  mov     [rax], rbp
0x1800203c3  mov     rax, [rsp+78h+arg_28]
0x1800203cb  mov     [rax], r15
0x1800203ce  test    r13, r13
0x1800203d1  jz      short loc_1800203EF
0x1800203d3  call    IsDeleteDCPresent
0x1800203d8  test    al, al
0x1800203da  jz      loc_18002064A
0x1800203e0  mov     rcx, r13; hdc
0x1800203e3  call    cs:__imp_DeleteDC
0x1800203ea  nop     dword ptr [rax+rax+00h]
0x1800203ef  mov     eax, ebx
0x1800203f1  mov     rbx, [rsp+78h+arg_8]
0x1800203f9  add     rsp, 40h
0x1800203fd  pop     r15
0x1800203ff  pop     r14
0x180020401  pop     r13
0x180020403  pop     r12
0x180020405  pop     rdi
0x180020406  pop     rsi
0x180020407  pop     rbp
0x180020408  retn
0x18002040a  movzx   ebp, word ptr [rdi+0Eh]
0x18002040e  test    bp, bp
0x180020411  jnz     loc_18002028A
0x180020417  mov     ebp, 20h ; ' '
0x18002041c  jmp     loc_180020286
0x180020421  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180020427  test    eax, eax
0x180020429  jz      short loc_1800203EF
0x18002042b  mov     ecx, ebx; int
0x18002042d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020432  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180020438  test    eax, eax
0x18002043a  jz      short loc_1800203EF
0x18002043c  mov     ecx, ebx; int
0x18002043e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020443  jmp     short loc_1800203EF
0x180020445  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18002044b  mov     ebx, 80070216h
0x180020450  test    eax, eax
0x180020452  jz      loc_1800204FA
0x180020458  mov     ecx, ebx; int
0x18002045a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002045f  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180020465  test    eax, eax
0x180020467  jmp     loc_1800204F1
0x18002046c  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180020473  mov     esi, 80004001h
0x180020478  jz      short loc_180020481
0x18002047a  mov     ecx, esi; int
0x18002047c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020481  mov     ebx, esi
0x180020483  jmp     loc_1800203EF
0x180020488  mov     edi, 400h
0x18002048d  mov     ecx, edi; Size
0x18002048f  call    cs:__imp_malloc
0x180020496  nop     dword ptr [rax+rax+00h]
0x18002049b  mov     rbx, rax
0x18002049e  test    rax, rax
0x1800204a1  jnz     loc_1800205E4
0x1800204a7  call    IsGetObjectAPresent
0x1800204ac  test    al, al
0x1800204ae  jnz     short loc_180020526
0x1800204b0  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800204b7  jz      short loc_1800204C0
0x1800204b9  mov     ecx, esi; int
0x1800204bb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800204c0  mov     ebx, esi
0x1800204c2  jmp     loc_1800203CE
0x1800204c7  call    cs:__imp_GetLastError
0x1800204ce  nop     dword ptr [rax+rax+00h]
0x1800204d3  xor     r14d, r14d
0x1800204d6  mov     ebx, eax
0x1800204d8  test    eax, eax
0x1800204da  jg      loc_180020561
0x1800204e0  test    ebx, ebx
0x1800204e2  mov     eax, 88982F94h
0x1800204e7  cmovns  ebx, eax
0x1800204ea  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800204f1  jz      short loc_1800204FA
0x1800204f3  mov     ecx, ebx; int
0x1800204f5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800204fa  mov     rcx, rdi; Block
0x1800204fd  call    cs:__imp_free
0x180020504  nop     dword ptr [rax+rax+00h]
0x180020509  test    r15, r15
0x18002050c  jz      loc_1800203CE
0x180020512  mov     rcx, r15; Block
0x180020515  call    cs:__imp_free
0x18002051c  nop     dword ptr [rax+rax+00h]
0x180020521  jmp     loc_1800203CE
0x180020526  mov     r9, rbx; pPalEntries
0x180020529  xor     edx, edx; iStart
0x18002052b  mov     r8d, 100h; cEntries
0x180020531  mov     rcx, r12; hpal
0x180020534  call    cs:__imp_GetPaletteEntries
0x18002053b  nop     dword ptr [rax+rax+00h]
0x180020540  mov     r14d, eax
0x180020543  jmp     loc_1800201F7
0x180020548  mov     ebx, 8007000Eh
0x18002054d  jmp     loc_18002033D
0x180020552  movzx   eax, ax
0x180020555  or      eax, 80070000h
0x18002055a  test    eax, eax
0x18002055c  jmp     loc_1800201D6
0x180020561  movzx   ebx, ax
0x180020564  or      ebx, 80070000h
0x18002056a  jmp     loc_1800204E0
0x18002056f  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180020576  jz      short loc_18002057F
0x180020578  mov     ecx, esi; int
0x18002057a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002057f  mov     ebx, esi
0x180020581  jmp     loc_1800204FA
0x180020586  xor     r14d, r14d
0x180020589  mov     ebx, 8007000Eh
0x18002058e  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180020595  jz      loc_1800203CE
0x18002059b  mov     ecx, ebx; int
0x18002059d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800205a2  jmp     loc_1800203CE
0x1800205a7  call    cs:__imp_GetLastError
0x1800205ae  nop     dword ptr [rax+rax+00h]
0x1800205b3  mov     ebx, eax
0x1800205b5  test    eax, eax
0x1800205b7  jle     short loc_1800205C2
0x1800205b9  movzx   ebx, ax
0x1800205bc  or      ebx, 80070000h
0x1800205c2  test    ebx, ebx
0x1800205c4  jns     loc_1800203A5
0x1800205ca  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800205d1  jnz     loc_1800204F3
0x1800205d7  test    ebx, ebx
0x1800205d9  js      loc_1800204FA
0x1800205df  jmp     loc_1800203A5
0x1800205e4  mov     r8, rdi; Size
0x1800205e7  xor     edx, edx; Val
0x1800205e9  mov     rcx, rbx; void *
0x1800205ec  call    memset_0
0x1800205f1  jmp     loc_1800204A7
0x1800205f6  xor     r14d, r14d
0x1800205f9  jmp     loc_18002056F
0x1800205fe  mov     r8d, r14d
0x180020601  lea     rcx, [rdi+28h]; void *
  ... truncated ...
```
